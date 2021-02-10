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
description: Os administradores podem saber mais sobre as opções disponíveis e preferenciais para permitir mensagens de entrada no Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 92229f0324eb9c05b233e5c4b0bc9f1bd7ab2e39
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165554"
---
# <a name="create-safe-sender-lists-in-eop"></a>Criar listas de remetentes seguros no EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender para Office 365 plano 1 e plano 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Se você for um cliente do Microsoft 365 com caixas de correio no Exchange Online ou um cliente autônomo do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, o EOP oferece várias maneiras de garantir que os usuários receberão emails de destinatários confiáveis. Essas opções incluem regras de fluxo de emails do Exchange (também conhecidas como regras de transporte), Remetentes Seguros do Outlook, Lista de IIs Permitidos (filtragem de conexão) e listas de remetentes permitidos ou listas de domínios permitidos em políticas anti-spam. Coletivamente, você pode pensar nessas opções como listas _de remetentes seguros._

As listas de remetentes seguros disponíveis são descritas na lista a seguir, em ordem das mais recomendadas para as menos recomendadas:

1. Regras do fluxo de email
2. Outlook Safe Senders
3. Lista de IIs (filtragem de conexão)
4. Listas de remetentes permitidos ou listas de domínios permitidos (políticas anti-spam)

As regras de fluxo de emails permitem a maior flexibilidade para garantir que apenas as mensagens certas sejam permitidas. Listas de domínio permitidos e remetentes permitidos em políticas anti-spam não são tão seguras quanto a Lista de IIs Permitidos, porque o domínio de email do remetente é facilmente spoofado. Porém, a Lista de I Ip  Permitir também apresenta um risco, porque os emails de qualquer domínio enviado desse endereço IP ignorarão a filtragem de spam.

> [!IMPORTANT]
>
> - Tenha cuidado para monitorar de perto *todas as* exceções que você fizer à filtragem de spam usando listas de remetentes seguros.
>
> - Embora você possa usar listas de remetentes seguros para ajudar com falsos positivos (emails bons marcados como ruins), considere o uso de listas de remetentes seguros como uma solução temporária que deve ser evitada, se possível. Não recomendamos o gerenciamento de falsos positivos usando listas de remetentes seguros, pois as exceções à filtragem de spam podem abrir sua organização para falsos e outros ataques. Se você continuar usando listas de remetentes seguros para gerenciar falsos positivos, precisará estar atento e manter o tópico Relatar mensagens e arquivos para a [Microsoft](report-junk-email-messages-to-microsoft.md) quando estiver pronto.
>
> - Para permitir que um domínio envie emails não autenticados (ignorar a proteção anti-spoofing), mas não ignorar verificações anti-spam e anti-malware, você pode adicioná-lo à lista de remetentes seguros [AllowedToSpoof](walkthrough-spoof-intelligence-insight.md)
>
> - O EOP e o Outlook inspecionam propriedades de mensagem diferentes para determinar o remetente da mensagem. Para obter mais informações, consulte [a seção Considerações para email](#considerations-for-bulk-email) em massa posteriormente neste artigo.

Por outro lado, você também tem várias opções para bloquear emails de fontes específicas usando _listas de remetentes bloqueados._ Para obter mais informações, confira [Criar listas de bloqueios de remetentes no EOP](create-block-sender-lists-in-office-365.md).

## <a name="recommended-use-mail-flow-rules"></a>(Recomendado) Usar regras de fluxo de emails

As regras de fluxo de emails no Exchange Online e no EOP autônomo usam condições e exceções para identificar mensagens e ações para especificar o que deve ser feito para essas mensagens. Para saber mais, confira [Regras de fluxo de emails (regras de transporte) no Exchange Online.](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

O exemplo a seguir presume que você precisa de email contoso.com ignorar a filtragem de spam. Para fazer isso, de configure as seguintes configurações:

1. **Condição:** **o domínio do** remetente \> **é** \> contoso.com.

2. Configure uma das seguintes configurações:

   - **Condição de regra de fluxo de** emails: um **header** de mensagem inclui qualquer uma destas palavras Nome do \>  \> **header:** `Authentication-Results` \> **valor do header**: `dmarc=pass` ou `dmarc=bestguesspass` .

     Esta condição verifica o status de autenticação de email do domínio de email de envio para garantir que o domínio de envio não está sendo falsos. Para obter mais informações sobre autenticação de email, [consulte SPF,](set-up-spf-in-office-365-to-help-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md)e [DMARC.](use-dmarc-to-validate-email.md)

   - **Lista de Ip Allow:** especifique o endereço IP de origem ou o intervalo de endereços na política de filtro de conexão.

     Use essa configuração se o domínio de envio não usar autenticação de email. Seja o mais restritivo possível quando se trata dos endereços IP de origem na Lista de I Ip Permitir. Recomendamos um intervalo de endereços IP de /24 ou menos (menos é melhor). Não use intervalos de endereços IP que pertencem a serviços de consumidor (por exemplo, outlook.com) ou infraestruturas compartilhadas.

   > [!IMPORTANT]
   >
   > - Nunca configure regras de fluxo *de* emails com apenas o domínio do remetente como condição para ignorar a filtragem de spam. Isso aumentará significativamente a probabilidade de que os invasores possam imitar o domínio de envio (ou representar o endereço de email completo), ignorar toda a filtragem de spam e ignorar as verificações de autenticação de remetente para que a mensagem chegue na Caixa de Entrada do destinatário. 
   >
   > - Não use domínios que você possui (também conhecidos como domínios aceitos) ou domínios populares (por exemplo, microsoft.com) como condições em regras de fluxo de emails. Isso é considerado alto risco porque cria oportunidades para os invasores enviarem emails que, de outra forma, seriam filtrados.
   >
   > - Se você permitir um endereço IP que está atrás de um gateway NAT (conversão de endereços de rede), precisará conhecer os servidores envolvidos no pool NAT para saber o escopo da lista de IIs. Endereços IP e participantes NAT podem mudar. Você precisa verificar periodicamente suas entradas da Lista de IIs De IIs como parte dos seus procedimentos de manutenção padrão.

3. **Condições opcionais:**

   - **O remetente** \> **é interno/externo** \> **Fora da organização:** essa condição é implícita, mas não há problema em usá-la para levar em conta servidores de email locais que podem não estar configurados corretamente.

   - **O assunto ou corpo** \> **assunto ou corpo inclui qualquer uma destas palavras** \> : Se você puder restringir ainda mais as mensagens por palavras-chave ou frases na linha de assunto ou no corpo da mensagem, poderá usar essas palavras \<keywords\> como uma condição.

4. **Ação:** configure essas duas ações na regra:

   a. **Modificar as propriedades da mensagem** \> **definir o nível de confiança de spam (SCL)** \> **Ignorar filtragem de spam.**

   b. **Modificar as propriedades da mensagem** \> **set a message header**: **Set the message header** \<CustomHeaderName\> **to the value** \<CustomHeaderValue\> .

      Por exemplo, `X-ETR: Bypass spam filtering for authenticated sender 'contoso.com'`. Se você tiver mais de um domínio na regra, poderá personalizar o texto do header conforme apropriado.

      Quando uma mensagem ignora a filtragem de spam devido a uma regra de fluxo de emails, o valor é carimbado no `SFV:SKN` header **X-Forefront-Antispam-Report.** Se a mensagem for de uma fonte que está na Lista de I Ip Allow, o valor `IPV:CAL` também será adicionado. Esses valores podem ajudá-lo com a solução de problemas.

![Configurações de regra de fluxo de emails no EAC para ignorar a filtragem de spam.](../../media/1-AllowList-SkipFilteringFromContoso.png)

## <a name="use-outlook-safe-senders"></a>Usar o Outlook Safe Senders

> [!CAUTION]
> Esse método cria um alto risco de invasores entregarem com êxito emails para a Caixa de Entrada que, de outra forma, seriam filtrados; No entanto, as listas de Envios Seguros ou Domínios Seguros do usuário não impedem que mensagens de phishing de malware ou alta confiança seja filtrada.

Em vez de uma configuração organizacional, os usuários ou administradores podem adicionar os endereços de email do remetente à lista de Remetentes Seguros na caixa de correio. Para obter instruções, confira [Definir configurações de lixo eletrônico nas caixas de correio do Exchange Online no Office 365.](configure-junk-email-settings-on-exo-mailboxes.md) Isso não é desejável na maioria das situações, pois os envios ignorarão partes da pilha de filtragem. Embora você confie no remetente, o remetente ainda pode ser comprometido e enviar conteúdo mal-intencionado. É melhor que você deixe nossos filtros fazer o que for necessário para verificar cada mensagem e, em seguida, relatar o falso [positivo/negativo](report-junk-email-messages-to-microsoft.md) para a Microsoft se nossos filtros fizerem errado. Ignorar a pilha de filtragem também interfere com [a ZAP.](zero-hour-auto-purge.md)

Quando as mensagens ignoram a filtragem de spam devido à lista de Remetentes Seguros de um usuário, o campo de header **X-Forefront-Antispam-Report** conterá o valor , que indica que a filtragem de `SFV:SFE` spam, spoof e phishing foi ignorada.

## <a name="use-the-ip-allow-list"></a>Usar a Lista de I Ip Permitir

Se você não puder usar regras de fluxo de emails conforme descrito anteriormente, a próxima melhor opção é adicionar o servidor de email de origem ou servidores à Lista de IIs De autorização de IP na política de filtro de conexão. Para obter detalhes, [consulte Configurar filtragem de conexão no EOP](configure-the-connection-filter-policy.md).

**Observações**:

- É importante que você mantenha o número mínimo de endereços IP permitidos, portanto, evite usar intervalos de endereços IP inteiros sempre que possível.

- Não use intervalos de endereços IP que pertencem a serviços de consumidor (por exemplo, outlook.com) ou infraestruturas compartilhadas.

- Revise regularmente as entradas na Lista de I Ip Permitir e remova as entradas de que você não precisa mais.

> [!CAUTION]
> Sem verificação adicional, como regras de fluxo de emails, os emails de fontes na Lista de IPs Permitires ignoram as verificações de filtragem de spam e de autenticação de remetente (SPF, DKIM, DMARC). Isso cria um alto risco de invasores entregarem com êxito emails para a Caixa de Entrada que, de outra forma, seriam filtrados; No entanto, a Lista de I Ip Allow não impede que mensagens de phishing de malware ou alta confiança seja filtrada.

## <a name="use-allowed-sender-lists-or-allowed-domain-lists"></a>Usar listas de remetentes permitidos ou listas de domínios permitidos

A opção menos desejável é usar a lista de remetentes permitidos ou a lista de domínios permitidos em políticas anti-spam. Você deve evitar  essa opção, se possível, porque os remetentes ignoram toda a proteção contra spam, spoof e phishing e autenticação de remetente (SPF, DKIM, DMARC). Esse método é melhor usado apenas para testes temporários. As etapas detalhadas podem ser encontradas no [tópico Configurar políticas anti-spam no tópico EOP.](configure-your-spam-filter-policies.md)

O limite máximo para essas listas é de aproximadamente 1.000 entradas; embora você só consiga inserir 30 entradas no portal. Você deve usar o PowerShell para adicionar mais de 30 entradas.

> [!CAUTION]
>
> - Esse método cria um alto risco de invasores entregarem com êxito emails para a Caixa de Entrada que, de outra forma, seriam filtrados; No entanto, as listas de domínios permitidos ou de envios permitidos não impedem a filtragem de mensagens de phishing de malware ou de alta confiança.
>
> - Não use domínios que você possui (também conhecidos como domínios aceitos) ou domínios populares (por exemplo, microsoft.com) em listas de domínios permitidos.

## <a name="considerations-for-bulk-email"></a>Considerações para email em massa

Uma mensagem de email SMTP padrão consiste em um *envelope de mensagem* e conteúdo de mensagem. O envelope da mensagem contém informações necessárias para transmitir e entregar a mensagem entre servidores SMTP. O conteúdo da mensagem contém campos de título da mensagem (coletivamente chamado de título da *mensagem)* e o corpo da mensagem. O envelope da mensagem é descrito na RFC 5321 e o header da mensagem é descrito na RFC 5322. Os destinatários nunca veem o envelope real da mensagem porque ele é gerado pelo processo de transmissão da mensagem e não faz parte realmente da mensagem.

- O endereço (também conhecido como endereço MAIL FROM, remetente P1 ou remetente de envelope) é o endereço de email usado na transmissão `5321.MailFrom` SMTP  da mensagem. Esse endereço de email normalmente é registrado no campo de título **Return-Path** no título da mensagem (embora seja possível para o remetente designar um endereço de email **return-path** diferente). Se a mensagem não puder ser entregue, será o destinatário do relatório de não entrega (também conhecido como NDR ou mensagem de rejeição).

- O (também conhecido como endereço De ou remetente P2) é o endereço de email no campo de título De e é o endereço de email do remetente exibido nos clientes de `5322.From` email.  

Frequentemente, os `5321.MailFrom` `5322.From` endereços e os endereços são os mesmos (comunicação de pessoa para pessoa). No entanto, quando o email é enviado em nome de outra pessoa, os endereços podem ser diferentes. Isso acontece com mais frequência para mensagens de email em massa.

Por exemplo, suponha que a Blue Yonder Airlines contratou Margie's Travel para enviar seu anúncio por email. A mensagem que você recebe em sua Caixa de Entrada tem as seguintes propriedades:

- O `5321.MailFrom` endereço é blueyonder.airlines@margiestravel.com.

- O `5322.From` endereço é blueyonder@news.blueyonderairlines.com, que é o que você verá no Outlook.

Listas de remetentes seguros e listas de domínios seguros em políticas anti-spam no EOP inspecionam apenas os endereços, isso é semelhante aos Remetentes Seguros do Outlook que `5322.From` usam o `5322.From` endereço.

Para impedir que essa mensagem seja filtrada, você pode seguir as seguintes etapas:

- Adicione blueyonder@news.blueyonderairlines.com (o `5322.From` endereço) como um Remetente Seguro do Outlook.

- [Use uma regra de fluxo de](#recommended-use-mail-flow-rules) emails com uma condição que procura mensagens de blueyonder@news.blueyonderairlines.com (o `5322.From` endereço, blueyonder.airlines@margiestravel.com (o `5321.MailFrom` ), ou ambos.

Para obter mais informações, [consulte Criar listas de remetentes seguros no EOP.](create-safe-sender-lists-in-office-365.md)
