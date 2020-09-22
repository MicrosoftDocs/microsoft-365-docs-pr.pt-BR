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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150s
ms.assetid: 9721b46d-cbea-4121-be51-542395e6fd21
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem saber mais sobre as opções disponíveis e preferidas para permitir mensagens de entrada no Exchange Online Protection (EOP).
ms.openlocfilehash: b1eda98e081338a981be1d1f5991578b49c574fd
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203162"
---
# <a name="create-safe-sender-lists-in-eop"></a>Criar listas de remetentes seguros no EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Se você é um cliente Microsoft 365 com caixas de correio no Exchange Online ou um cliente autônomo do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, o EOP oferece várias maneiras de garantir que os usuários recebam emails de remetentes confiáveis. Essas opções incluem regras de fluxo de emails do Exchange (também conhecidas como regras de transporte), remetentes confiáveis do Outlook, a lista de permissões de IP (filtragem de conexão) e listas de remetentes permitidos ou listas de domínio permitidas em políticas antispam. Coletivamente, você pode imaginar essas opções como _listas de remetentes seguros_.

As listas de remetentes seguros disponíveis são descritas na lista a seguir na ordem da mais recomendada para a menos recomendada:

1. Regras do fluxo de email
2. Remetentes confiáveis do Outlook
3. Lista de permissões de IP (filtragem de conexão)
4. Listas de remetentes permitidos ou listas de domínios permitidos (políticas antispam)

As regras de fluxo de emails permitem maior flexibilidade para garantir que apenas as mensagens corretas sejam permitidas. As listas de domínios permitidos e remetentes permitidos em políticas antispam não são tão seguras quanto a lista de permissões de IP, porque o domínio de email do remetente é facilmente falsificado. No entanto, a lista de IPs permitidos também apresenta um risco, pois o email de _qualquer_ domínio enviado desse endereço IP ignorará a filtragem de spam.

> [!IMPORTANT]
>
> - Tenha cuidado para monitorar atentamente *todas as* exceções que você deseja filtrar usando as listas de remetentes seguros.
>
> - Embora você possa usar listas de remetentes confiáveis para ajudar com falsos positivos (bons emails marcados como spam), considere o uso de listas de remetentes seguros como uma solução temporária que deve ser evitada, se possível. Não recomendamos o gerenciamento de falsos positivos usando as listas de remetentes seguros, pois as exceções à filtragem de spam podem abrir sua organização para falsificar e outros ataques. Se você insistir em usar listas de remetentes confiáveis para gerenciar falsos positivos, precisará estar atento e manter o tópico [relatar mensagens e arquivos para a Microsoft](report-junk-email-messages-to-microsoft.md) em mãos.
>
> - Para permitir que um domínio envie emails não autenticados (ignora a proteção contra falsificação), mas não ignore verificações antispam e antimalware, você pode adicioná-lo à [lista de remetentes confiáveis do AllowedToSpoof](walkthrough-spoof-intelligence-insight.md)
>
> - EOP e Outlook inspecionam Propriedades de mensagem diferentes para determinar o remetente da mensagem. Para obter mais informações, consulte a seção [Considerações sobre email em massa](#considerations-for-bulk-email) , posteriormente neste tópico.

Por outro lado, você também tem várias opções para bloquear emails de fontes específicas usando _listas de remetentes bloqueados_. Para obter mais informações, confira [Criar listas de bloqueios de remetentes no EOP](create-block-sender-lists-in-office-365.md).

## <a name="recommended-use-mail-flow-rules"></a>Recomenda Usar regras de fluxo de email

Regras de fluxo de emails no Exchange Online e autônomo EOP usam condições e exceções para identificar mensagens e ações para especificar o que deve ser feito para essas mensagens. Para obter mais informações, consulte [regras de fluxo de emails (regras de transporte) no Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).

O exemplo a seguir supõe que você precisa de emails do contoso.com para ignorar a filtragem de spam. Para fazer isso, defina as seguintes configurações:

1. **Condição**: **o domínio do remetente** \> **é** \> contoso.com.

2. Configure qualquer uma das seguintes configurações:

   - **Condição de regra de fluxo de emails**: **um cabeçalho** \> **de mensagem inclui qualquer uma destas palavras** \> **nome do cabeçalho**: valor do `Authentication-Results` \> **cabeçalho**: `dmarc=pass` ou `dmarc=bestguesspass` .

     Esta condição verifica o status de autenticação do remetente do domínio de envio de email para garantir que o domínio de envio não está sendo falsificado. Para obter mais informações sobre autenticação de email, consulte [SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md)e [DMARC](use-dmarc-to-validate-email.md).

   - **Lista de permissões de IP**: especifique o endereço IP de origem ou o intervalo de endereços na política de filtro de conexão.
  
     Use essa configuração se o domínio de envio não tiver autenticação. Seja o mais restritivo possível quando se trata dos endereços IP de origem na lista de IPs permitidos. Recomendamos um intervalo de endereços IP de/24 ou menos (menos é melhor). Não use intervalos de endereços IP que pertençam aos serviços de consumidor (por exemplo, outlook.com) ou infraestruturas compartilhadas.

   > [!IMPORTANT]
   >
   > - Nunca configure as regras de fluxo de email configurar *somente* com o domínio do remetente como a condição de ignorar a filtragem de spam. Isso aumentará *significativamente* a probabilidade de que os atacantes possam falsificar o domínio de envio (ou representar o endereço de email completo), ignorar todos os filtros de spam e ignorar as verificações de autenticação do remetente para que a mensagem chegue na caixa de entrada do destinatário.
   >
   > - Não use domínios que você possui (também conhecidos como domínios aceitos) ou domínios populares (por exemplo, microsoft.com) como condições em regras de fluxo de email. Isso é considerado alto risco, pois cria oportunidades para que os invasores enviem emails que, caso contrário, seriam filtrados.
   >
   > - Se você permitir um endereço IP que está atrás de um gateway NAT (conversão de endereço de rede), precisará saber os servidores envolvidos no pool NAT para saber o escopo da lista de IPs permitidos. Os endereços IP e os participantes de NAT podem alterar. Você precisa verificar periodicamente suas entradas da lista de IPs permitidos como parte de seus procedimentos de manutenção padrão.

3. **Condições opcionais**:

   - **O remetente** \> **é interno/externo** \> **Fora da organização**: essa condição é implícita, mas é possível usá-la para considerar os servidores de email locais que podem não estar configurados corretamente.

   - **O assunto ou corpo** \> **assunto ou corpo inclui qualquer uma destas palavras** \> \<keywords\>: Se você pode restringir ainda mais as mensagens por palavras-chave ou frases na linha de assunto ou no corpo da mensagem, você pode usar essas palavras como uma condição.

4. **Ação**: Configure ambas as ações na regra:

   a. **Modificar as propriedades** \> da mensagem **definir o nível de confiança de spam (SCL)** \> **Ignorar a filtragem de spam**.

   b. **Um cabeçalho** \> de mensagem **inclui qualquer uma destas palavras** \> **Nome do cabeçalho**: \<CustomHeaderName\> **valor do cabeçalho**: \<CustomHeaderValue\> .

      Por exemplo, `X-ETR: Bypass spam filtering for authenticated sender 'contoso.com'`. Se você tiver mais de um domínio na regra, você pode personalizar o texto do cabeçalho conforme apropriado.

      Quando uma mensagem ignora a filtragem de spam devido a uma regra de fluxo de email, o `SFV:SKN` valor valor é carimbado no cabeçalho **X-Forefront-antispam-Report** . Se a mensagem for de uma fonte na lista de IPs permitidos, o valor `IPV:CAL` também será adicionado. Esses valores podem ajudá-lo com a solução de problemas.

![Configurações de regra de fluxo de emails no Eat para ignorar a filtragem de spam.](../../media/1-AllowList-SkipFilteringFromContoso.png)

## <a name="use-outlook-safe-senders"></a>Usar remetentes confiáveis do Outlook

Em vez de uma configuração organizacional, os usuários ou administradores podem adicionar os endereços de email do remetente à lista de remetentes confiáveis na caixa de correio. Para obter instruções, consulte [definir configurações de lixo eletrônico em caixas de correio do Exchange Online no Office 365](configure-junk-email-settings-on-exo-mailboxes.md). Isso não é desejável na maioria das situações, já que os remetentes ignorarão partes da pilha de filtragem. Embora você confie no remetente, as latas do remetente ainda serão comprometidas e poderão enviar conteúdo mal-intencionado. É melhor que nossos filtros façam o que é necessário para verificar cada mensagem e, em seguida, [relatar o falso positivo/negativo para a Microsoft](report-junk-email-messages-to-microsoft.md) se nossos filtros erram. Ignorar a pilha de filtragem também interfere em [zap](zero-hour-auto-purge.md).

Quando as mensagens ignoram a filtragem de spam devido à lista de remetentes confiáveis de um usuário, o campo de cabeçalho **X-Forefront-antispam-Report** conterá o valor `SFV:SFE` , que indica que a filtragem de spam, spoof e phishing foi ignorada.

## <a name="use-the-ip-allow-list"></a>Usar a lista de IPs permitidos

Se você não pode usar regras de fluxo de emails conforme descrito anteriormente, a melhor opção é adicionar o servidor de email de origem ou servidores à lista de IPs permitidos na política de filtro de conexão. Para obter detalhes, consulte [Configure Connection Filtering in EOP](configure-the-connection-filter-policy.md).

**Observações**:

- É importante que você mantenha o número de endereços IP permitidos no mínimo, portanto, evite usar intervalos de endereços IP inteiros sempre que possível.

- Não use intervalos de endereços IP que pertençam aos serviços de consumidor (por exemplo, outlook.com) ou infraestruturas compartilhadas.

- Examine regularmente as entradas na lista de permissões de IP e remova as entradas que não são mais necessárias.

> [!CAUTION]
> Sem verificação adicional, como regras de fluxo de emails, o email de fontes na lista de IPs permitidos ignora as verificações de filtragem de spam e autenticação de remetente (SPF, DKIM, DMARC). Isso cria um alto risco de invasores enviando emails com êxito para a caixa de entrada que seria filtrada.

## <a name="use-allowed-sender-lists-or-allowed-domain-lists"></a>Usar listas de remetentes permitidos ou listas de domínios permitidos

A opção menos desejável é usar a lista de remetentes permitidos ou a lista de domínios permitidos em políticas antispam. *Se possível* , você deve evitar essa opção, pois os remetentes ignoram todas as proteções de spam, falsificação e phishing, e autenticação de remetente (SPF, DKIM, DMARC). Esse método é melhor usado apenas para testes temporários. As etapas detalhadas podem ser encontradas em [Configurar políticas antispam no tópico EOP](configure-your-spam-filter-policies.md) .

O limite máximo para essas listas é de aproximadamente 1000 entradas; no entanto, você poderá inserir 30 entradas no Portal. Você deve usar o PowerShell para adicionar mais de 30 entradas.

> [!CAUTION]
>
> - Este método cria um alto risco de invasores enviando emails com êxito para a caixa de entrada que seria filtrada.
>
> - Não use domínios que você possui (também conhecidos como domínios aceitos) ou domínios populares (por exemplo, microsoft.com) em listas de domínios permitidos.

## <a name="considerations-for-bulk-email"></a>Considerações para email em massa

Uma mensagem de email SMTP padrão consiste em um *envelope de mensagem* e um conteúdo de mensagem. O envelope da mensagem contém informações necessárias para transmitir e entregar a mensagem entre os servidores SMTP. O conteúdo da mensagem contém os campos de cabeçalho da mensagem (coletivamente chamados de *cabeçalho da mensagem*) e o corpo da mensagem. O envelope da mensagem é descrito em RFC 5321, e o cabeçalho da mensagem é descrito em RFC 5322. Os destinatários nunca veem o envelope de mensagem real porque é gerado pelo processo de transmissão de mensagens e, na verdade, não faz parte da mensagem.

- O `5321.MailFrom` Endereço (também conhecido como o endereço **de email de** remetente, o remetente P1 ou o remetente do envelope) é o endereço de email que é usado na transmissão SMTP da mensagem. Esse endereço de email geralmente é registrado no campo de cabeçalho de **retorno de caminho** no cabeçalho da mensagem (embora seja possível que o remetente designe um endereço de email de **devolução** diferente). Se a mensagem não puder ser entregue, ela é o destinatário da notificação de falha na entrega (também conhecida como notificação de falha na entrega ou mensagem de devolução).

- O `5322.From` (também conhecido como o endereço **de** ou o remetente P2) é o endereço de email no campo **de cabeçalho de** e é o endereço de email do remetente que é exibido em clientes de email.

Frequentemente, os `5321.MailFrom` `5322.From` endereços e são iguais (comunicação pessoa a pessoa). No entanto, quando o email é enviado em nome de outra pessoa, os endereços podem ser diferentes. Isso acontece com mais frequência para mensagens de email em massa.

Por exemplo, suponha que as companhias aéreas Yonder azuis contratam a viagem da Margie para enviar seu anúncio de email. A mensagem recebida na caixa de entrada tem as seguintes propriedades:

- O `5321.MailFrom` endereço é blueyonder.Airlines@margiestravel.com.

- O `5322.From` endereço é blueyonder@news.blueyonderairlines.com, que é o que você verá no Outlook.

Listas de remetentes seguros e listas de domínios seguros em políticas antispam no EOP inspecionar apenas os `5322.From` endereços, isso é semelhante aos remetentes confiáveis do Outlook que usam o `5322.From` endereço.

Para impedir que esta mensagem seja filtrada, você pode executar as seguintes etapas:

- Adicione blueyonder@news.blueyonderairlines.com (o `5322.From` endereço) como um remetente seguro do Outlook.

- [Use uma regra de fluxo de emails](#recommended-use-mail-flow-rules) com uma condição que procura mensagens de blueyonder@news.blueyonderairlines.com (o `5322.From` endereço, blueyonder.Airlines@margiestravel.com (o `5321.MailFrom` ) ou ambos.

Para obter mais informações, consulte [criar listas de remetentes seguros no EOP](create-safe-sender-lists-in-office-365.md).
