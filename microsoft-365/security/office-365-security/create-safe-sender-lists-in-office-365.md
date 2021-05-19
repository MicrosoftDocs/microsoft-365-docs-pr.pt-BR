---
title: Criar listas de remetentes confiáveis
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150s
ms.assetid: 9721b46d-cbea-4121-be51-542395e6fd21
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem aprender sobre as opções disponíveis e preferenciais para permitir mensagens de entrada no Proteção do Exchange Online (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f76b34a439d2eaf2c8315d174483b0b30d3b3b0b
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538754"
---
# <a name="create-safe-sender-lists-in-eop"></a>Criar listas de remetentes seguros no EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Se você for um cliente Microsoft 365 com caixas de correio no Exchange Online ou um cliente autônomo Proteção do Exchange Online (EOP) sem caixas de correio Exchange Online, o EOP oferece várias maneiras de garantir que os usuários recebam emails de destinatários confiáveis. Essas opções incluem Exchange de fluxo de emails (também conhecidas como regras de transporte), Outlook Cofre Remetentes, Lista de ID Permitidos (filtragem de conexão) e listas de remetentes permitidos ou listas de domínio permitidos em políticas anti-spam. Coletivamente, você pode pensar nessas opções como listas _de remetentes seguros._

As listas de remetentes seguros disponíveis são descritas na lista a seguir para o mais recomendado para o menos recomendado:

1. Regras do fluxo de email
2. Outlook Cofre Senders
3. Lista de IDS (filtragem de conexão)
4. Listas de remetentes permitidas ou listas de domínio permitidos (políticas anti-spam)

As regras de fluxo de emails permitem a maior flexibilidade para garantir que apenas as mensagens certas sejam permitidas. As listas de domínio permitidas e de remetente em políticas anti-spam não são tão seguras quanto a Lista de Permissão de IP, pois o domínio de email do remetente é facilmente spoofado. Porém, a Lista de IDS  também apresenta um risco, pois os emails de qualquer domínio que são enviados desse endereço IP ignorarão a filtragem de spam.

> [!IMPORTANT]
>
> - Tenha cuidado para monitorar de perto *todas as* exceções que você fizer para a filtragem de spam usando listas de remetentes seguros.
>
> - Embora você possa usar listas de remetentes seguros para ajudar com falsos positivos (bons emails marcados como ruins), considere o uso de listas de remetentes seguros como uma solução temporária que deve ser evitada, se possível. Não recomendamos o gerenciamento de falsos positivos usando listas de remetentes seguros, pois as exceções à filtragem de spam podem abrir sua organização para a spoofing e outros ataques. Se você insistir em usar listas de remetentes seguros para gerenciar falsos positivos, você precisa estar atento e manter o tópico Relatar mensagens e arquivos para a [Microsoft](report-junk-email-messages-to-microsoft.md) em condições prontas.
>
> - Para permitir que um domínio envie emails não autenticados (ignore a proteção anti-spoofing), mas não ignore as verificações anti-spam e anti-malware, você pode usar o insight de inteligência de [spoof](learn-about-spoof-intelligence.md) e a Lista de Locatários [Permitir/Bloquear.](tenant-allow-block-list.md)
>
> - EOP e Outlook inspecionar diferentes propriedades de mensagem para determinar o remetente da mensagem. Para obter mais informações, consulte a [seção Considerações para email](#considerations-for-bulk-email) em massa posteriormente neste artigo.

Por outro lado, você também tem várias opções para bloquear emails de fontes específicas usando _listas de remetentes bloqueados._ Para obter mais informações, confira [Criar listas de bloqueios de remetentes no EOP](create-block-sender-lists-in-office-365.md).

## <a name="recommended-use-mail-flow-rules"></a>(Recomendado) Usar regras de fluxo de emails

As regras de fluxo de email Exchange Online EOP autônoma e usam condições e exceções para identificar mensagens e ações para especificar o que deve ser feito com essas mensagens. Para obter mais informações, consulte Regras de fluxo de email [(regras de transporte) em Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).

O exemplo a seguir supõe que você precisa de email contoso.com para ignorar a filtragem de spam. Para fazer isso, configure as seguintes configurações:

1. **Condição**: **o domínio do** remetente \> **é** \> contoso.com.

2. Configure uma das seguintes configurações:

   - **Condição da regra de** fluxo de email : um **header** de mensagem inclui qualquer uma dessas palavras Nome do \>  \> **header**: `Authentication-Results` \> **valor do header**: `dmarc=pass` ou `dmarc=bestguesspass` .

     Essa condição verifica o status de autenticação de email do domínio de email de envio para garantir que o domínio de envio não está sendo falsos. Para obter mais informações sobre autenticação de email, consulte [SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md)e [DMARC](use-dmarc-to-validate-email.md).

   - **Lista de IDS**: Especifique o endereço IP de origem ou o intervalo de endereços na política de filtro de conexão.

     Use essa configuração se o domínio de envio não usar autenticação de email. Seja o mais restritivo possível quando se trata dos endereços IP de origem na Lista de Ip Allow. Recomendamos um intervalo de endereços IP de /24 ou menos (menos é melhor). Não use intervalos de endereços IP que pertencem a serviços de consumidor (por exemplo, outlook.com) ou infraestruturas compartilhadas.

   > [!IMPORTANT]
   >
   > - Nunca configure regras de fluxo de emails *com apenas* o domínio do remetente como condição para ignorar a filtragem de spam. Isso aumentará significativamente a probabilidade de que os invasores possam imitar o domínio de envio (ou representar o endereço de email completo), ignorar toda a filtragem de spam e ignorar verificações de autenticação de remetente para que a mensagem chegue na Caixa de Entrada do destinatário. 
   >
   > - Não use domínios que você possui (também conhecidos como domínios aceitos) ou domínios populares (por exemplo, microsoft.com) como condições em regras de fluxo de emails. Isso é considerado de alto risco porque cria oportunidades para os invasores enviarem emails que, de outra forma, seriam filtrados.
   >
   > - Se você permitir um endereço IP que está atrás de um gateway NAT (conversão de endereço de rede), você precisará conhecer os servidores que estão envolvidos no pool NAT para saber o escopo de sua Lista de IDS. Endereços IP e participantes NAT podem mudar. Você precisa verificar periodicamente suas entradas de Lista de IDS como parte de seus procedimentos de manutenção padrão.

3. **Condições opcionais**:

   - **O remetente** \> **é interno/externo** \> **Fora da organização**: essa condição está implícita, mas não há problema em usá-la para contabilar servidores de email locais que podem não estar configurados corretamente.

   - **O assunto ou o corpo** \> **subject ou body inclui qualquer uma dessas palavras** \> : Se você puder restringir ainda mais as mensagens por palavras-chave ou frases na linha de assunto ou no corpo da mensagem, você poderá usar essas palavras \<keywords\> como uma condição.

4. **Ação**: Configure ambas as ações na regra:

   a. **Modificar as propriedades da mensagem** \> **definir o nível de confiança de spam (SCL)** \> **Ignorar a filtragem de spam**.

   b. **Modificar as propriedades da mensagem** \> **definir um header de mensagem:** **de definir o header da mensagem** como o \<CustomHeaderName\> **valor** \<CustomHeaderValue\> .

      Por exemplo, `X-ETR: Bypass spam filtering for authenticated sender 'contoso.com'`. Se você tiver mais de um domínio na regra, poderá personalizar o texto do header conforme apropriado.

      Quando uma mensagem ignora a filtragem de spam devido a uma regra de fluxo de emails, o valor é carimbado no `SFV:SKN` header **X-Forefront-Antispam-Report.** Se a mensagem for de uma fonte que está na Lista de IDS, o valor `IPV:CAL` também será adicionado. Esses valores podem ajudá-lo na solução de problemas.

![Configurações de regra de fluxo de emails no EAC para ignorar a filtragem de spam.](../../media/1-AllowList-SkipFilteringFromContoso.png)

## <a name="use-outlook-safe-senders"></a>Usar Outlook Cofre Senders

> [!CAUTION]
> Esse método cria um alto risco de invasores entregarem emails com êxito à Caixa de Entrada que, de outra forma, seriam filtrados; no entanto, as listas de Cofre ou domínios Cofre do usuário não impedem a filtragem de malware ou mensagens de phishing de alta confiança.

Em vez de uma configuração organizacional, os usuários ou administradores podem adicionar os endereços de email do remetente à lista Cofre Remetentes na caixa de correio. Para obter instruções, consulte [Configure junk email settings on Exchange Online mailboxes in Office 365](configure-junk-email-settings-on-exo-mailboxes.md). Isso não é desejável na maioria das situações, pois os envios ignorarão partes da pilha de filtragem. Embora você confie no remetente, o remetente ainda pode ser comprometido e enviar conteúdo mal-intencionado. É melhor que você deixe nossos filtros fazer o que é necessário para verificar todas as mensagens e, em seguida, relatar o [falso positivo/negativo](report-junk-email-messages-to-microsoft.md) para a Microsoft se nossos filtros errarem. Ignorar a pilha de filtragem também interfere no [ZAP](zero-hour-auto-purge.md).

Quando as mensagens ignoram a filtragem de spam devido à lista de remetentes Cofre do usuário, o campo de header **X-Forefront-Antispam-Report** conterá o valor , o que indica que a filtragem de `SFV:SFE` spam, spoof e phishing foi ignorada.

## <a name="use-the-ip-allow-list"></a>Usar a Lista de IDS

Se você não puder usar regras de fluxo de emails conforme descrito anteriormente, a próxima melhor opção é adicionar o servidor de email de origem ou servidores à Lista de IDS na política de filtro de conexão. Para obter detalhes, consulte [Configure connection filtering in EOP](configure-the-connection-filter-policy.md).

**Observações**:

- É importante que você mantenha o número mínimo de endereços IP permitidos, portanto, evite usar intervalos de endereços IP inteiros sempre que possível.

- Não use intervalos de endereços IP que pertencem a serviços de consumidor (por exemplo, outlook.com) ou infraestruturas compartilhadas.

- Revise regularmente as entradas na Lista de Permitir IP e remova as entradas que você não precisa mais.

> [!CAUTION]
> Sem verificação adicional, como regras de fluxo de emails, o email de fontes na Lista de IPs Permite ignorar verificações de filtragem de spam e de remetente (SPF, DKIM, DMARC). Isso cria um alto risco de invasores entregarem emails com êxito à Caixa de Entrada que, de outra forma, seriam filtrados; no entanto, a Lista de IDS não impede que mensagens de phishing de malware ou de alta confiança seja filtrada.

## <a name="use-allowed-sender-lists-or-allowed-domain-lists"></a>Usar listas de remetentes permitidos ou listas de domínio permitidos

A opção menos desejável é usar a lista de remetentes permitidos ou a lista de domínios permitidos em políticas anti-spam. Você deve evitar  essa opção, se possível, porque os remetentes ignoram toda a proteção contra spam, spoof e phishing e autenticação de remetente (SPF, DKIM, DMARC). Esse método é melhor usado apenas para testes temporários. As etapas detalhadas podem ser encontradas em [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md) topic.

O limite máximo para essas listas é de aproximadamente 1.000 entradas; embora, você só poderá inserir 30 entradas no portal. Você deve usar o PowerShell para adicionar mais de 30 entradas.

> [!CAUTION]
>
> - Esse método cria um alto risco de invasores entregarem emails com êxito à Caixa de Entrada que, de outra forma, seriam filtrados; no entanto, as listas de senders ou domínios permitidos não impedem que as mensagens de phishing de malware ou de alta confiança seja filtrada.
>
> - Não use domínios que você possui (também conhecidos como domínios aceitos) ou domínios populares (por exemplo, microsoft.com) em listas de domínio permitidos.

## <a name="considerations-for-bulk-email"></a>Considerações sobre email em massa

Uma mensagem de email SMTP padrão consiste em um *envelope de mensagem* e conteúdo de mensagem. O envelope de mensagem contém informações necessárias para transmitir e entregar a mensagem entre servidores SMTP. O conteúdo da mensagem contém campos de header de mensagem (coletivamente chamado de *header* da mensagem ) e o corpo da mensagem. O envelope de mensagem é descrito no RFC 5321 e o header da mensagem é descrito no RFC 5322. Os destinatários nunca veem o envelope de mensagem real porque ele é gerado pelo processo de transmissão de mensagens e não faz parte da mensagem.

- O endereço (também conhecido como endereço MAIL FROM, remetente P1 ou remetente de envelope) é o endereço de email usado na transmissão `5321.MailFrom` SMTP  da mensagem. Esse endereço de email normalmente é registrado no campo de header **Return-Path** no header da mensagem (embora seja possível que o remetente designe um endereço de email **return-path** diferente). Se a mensagem não puder ser entregue, será o destinatário do relatório de não entrega (também conhecido como NDR ou mensagem de rejeição).

- O (também conhecido como o endereço De ou remetente P2) é o endereço de email no campo de header From e é o endereço de email do remetente exibido em clientes de `5322.From` email.  

Frequentemente, os `5321.MailFrom` `5322.From` endereços e são os mesmos (comunicação de pessoa para pessoa). No entanto, quando o email é enviado em nome de outra pessoa, os endereços podem ser diferentes. Isso acontece com mais frequência para mensagens de email em massa.

Por exemplo, suponha que a Blue Yonder Airlines tenha contratado Margie's Travel para enviar sua publicidade por email. A mensagem que você recebe em sua Caixa de Entrada tem as seguintes propriedades:

- O `5321.MailFrom` endereço é blueyonder.airlines@margiestravel.com.

- O `5322.From` endereço é blueyonder@news.blueyonderairlines.com, que é o que você verá no Outlook.

Cofre listas de remetentes e listas de domínios seguros em políticas anti-spam no EOP inspecionam apenas os endereços, isso é semelhante Outlook Cofre remetentes que `5322.From` usam o `5322.From` endereço.

Para evitar que essa mensagem seja filtrada, você pode seguir as seguintes etapas:

- Adicione blueyonder@news.blueyonderairlines.com (o `5322.From` endereço) como um Outlook Cofre Remetente.

- [Use uma regra de fluxo de](#recommended-use-mail-flow-rules) emails com uma condição que procura mensagens de blueyonder@news.blueyonderairlines.com (o endereço, blueyonder.airlines@margiestravel.com `5322.From` `5321.MailFrom` (o ), ou ambos.

Para obter mais informações, consulte [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).
