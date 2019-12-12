---
title: Criar listas de remetentes seguros no Office 365
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 4/29/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150s
ms.assetid: 9721b46d-cbea-4121-be51-542395e6fd21
description: Se você quiser ter certeza de que recebeu emails de um remetente específico, porque confia neles e suas mensagens, é possível ajustar a lista de permissões em uma política de filtro de spam no centro de administração do Exchange.
ms.openlocfilehash: 1e804e73b8e2b98107c955004bac240793375ab9
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/11/2019
ms.locfileid: "39970847"
---
# <a name="create-safe-sender-lists-in-office-365"></a>Criar listas de remetentes seguros no Office 365

Se você quiser garantir que os usuários recebam emails de um remetente ou remetentes específicos porque você confia neles e suas mensagens, há vários métodos disponíveis que você pode escolher. Essas opções incluem regras de transporte do Exchange (ETRs), remetentes confiáveis do Outlook, listas de permissões de IP, listas de permissões de remetente/domínio antispam.

> [!IMPORTANT]
> Enquanto as listas de permissões da organização podem ser usadas para tratar de falsos positivos, isso deve ser considerado como uma solução temporária e evitada se possível. O gerenciamento de falsos positivos usando listas de permissões não é recomendável, pois pode abrir inadvertidamente sua organização para falsificação, representação e outros ataques. Se você usar uma lista de permissões para essa finalidade, precisará estar atento e manter o artigo para [enviar emails de spam, não spam e phishing para a Microsoft para análise](https://docs.microsoft.com/office365/SecurityCompliance/submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis), no Ready.

O método recomendado para configurar uma lista de remetentes confiáveis é usar as regras de transporte do Exchange (ETRs), já que isso apresenta a maior flexibilidade para garantir que apenas as mensagens corretas sejam permitidas. O *endereço de email da política* antispam e as listas de *permissões baseadas no domínio* não são tão seguras quanto as *listas baseadas em endereço IP* , pois os domínios podem ser falsificados facilmente. Mas as listas de permissões baseadas em IP de política antispam também apresentam riscos, pois eles permitirão que qualquer domínio enviado através desse IP ignore a filtragem de spam. Tenha cuidado e monitore *as* exceções feitas com cuidado.

> [!IMPORTANT]
> As informações sobre como criar uma **lista de remetentes bloqueados** estão [aqui](create-block-sender-lists-in-office-365.md).

## <a name="options-from-most-to-least-recommended"></a>Opções do máximo para o menos recomendado

Você sempre deve restringir suas listas de permissões porque elas ignoram muitas medidas de segurança. Você deve verificar novamente todas as listas de permissões como parte de sua manutenção padrão, para que você tenha conhecimento de quem tem permissão para ignorar. A recomendação é usar o ETRs restritivo, sempre que possível.

- Regras de transporte do Exchange (ETRs também chamadas de regras de fluxo de emails)
- Remetentes confiáveis do Outlook
- Política antispam: listas de IPs permitidos
- Política antispam: listas de permissões de remetente/domínio

## <a name="using-exchange-transport-rules-etrs-to-allow-specific-senders-recommended"></a>Usando regras de transporte do Exchange (ETRs) para permitir remetentes específicos (recomendado)

Para garantir que apenas mensagens legítimas sejam permitidas para sua organização, a condição deve ser uma das seguintes:

- Use o status de autenticação do remetente do domínio de envio. Isso é feito verificando o cabeçalho Authentication-Results para garantir que ele contenha "dMarc = Pass" ou "dMarc = bestguesspass". Isso garante que o domínio de envio tenha sido autenticado e não esteja sendo falsificado. Clique para saber mais sobre a autenticação de email [SPF](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing), [DKIM](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)e [DMARC](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email) .

- Ou, se o domínio de envio não tiver autenticação, use o domínio de envio *mais* um IP de envio (ou intervalo IP). Certifique-se de que você é o mais *restritivo possível*, o objetivo é fazer isso o mais seguro possível. Um intervalo IP maior do que/24 *não* é recomendado. Evite adicionar intervalos de endereços IP que pertençam a serviços de consumidor ou infraestruturas compartilhadas.

> [!IMPORTANT]
> Se você permitir um endereço IP que seja NATted, deverá saber as máquinas envolvidas nesse pool NAT para saber o escopo do seu permitido. Lembre-se de que os endereços IP podem ser alterados e os participantes de NAT também podem. Você deve verificar novamente todas as listas de permissões, incluindo IP, como parte da sua manutenção padrão.

- *Opcionalmente*, adicione uma condição de que a mensagem se origine de fora da organização (isso é implícito, mas é bom adicioná-la como uma condição de conta para servidores locais que podem não estar corretamente configurados).

- *Opcionalmente*, se você puder identificar palavras-chave ou frases exclusivas no assunto ou no corpo do email, use essas informações como uma condição adicional para restringir ainda mais as mensagens de email permitidas pela regra de fluxo de emails.

A ação na regra deve seguir este padrão:

1. Defina o nível de confiança de spam (SCL) como-1 (ignorar filtragem de spam).

2. Adicione um cabeçalho X para dizer o que a regra faz. No exemplo abaixo, você pode adicionar um cabeçalho simples "X-ETR: ignorar a filtragem de spam para o remetente `contoso.com`autenticado". Se você tiver mais de um domínio nesta regra, você pode alterar o texto do cabeçalho conforme apropriado. **Quando uma mensagem ignora a filtragem devido a um ETR, ela carimba SFV: skn no cabeçalho X-Forefront-antispam-Report** (**se ele estiver em uma lista de permissões de IP, ele também carimba IPV: Cal**). Isso ajudará na solução de problemas.

![GUI para ignorar a filtragem de spam.](../media/1-AllowList-SkipFilteringFromContoso.png)

> [!CAUTION]
> Não configure regras de fluxo de email somente com *o domínio do remetente* como uma condição para ignorar a filtragem de spam. Esse método aumenta significativamente os spammers de risco podem falsificar o domínio de envio (ou representar o endereço de email completo) ignorar todos os filtros de spam, verificações de autenticação de remetentes e a mensagem chegará à caixa de entrada de uma pessoa.

![Como definir o SCL como menos um.](../media/2-AllowList-SetsSCLMinus1.png)

Não adicione domínios que você possui ou domínios populares (por exemplo, `microsoft.com`) à regra de fluxo de emails como uma condição. Isso é considerado de alto risco, pois cria oportunidades de atores incorretos para enviar emails que seriam filtrados de outra forma.

[Clique para obter as etapas para criar um ETR, também conhecido como regras de fluxo de emails](https://docs.microsoft.com/office365/SecurityCompliance/use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages).

## <a name="use-outlook-safe-senders-end-user-managed"></a>Usar remetentes confiáveis do Outlook (gerenciado pelo usuário final)

Em vez de autorizar um endereço, um domínio ou um endereço IP globalmente, os usuários finais também podem permitir o envio de endereços por meio de remetentes confiáveis do Outlook. As etapas para configurar isso diferem entre o [Outlook na Web](https://support.office.com/article/48c9f6f7-2309-4f95-9a4d-de987e880e46) e o [cliente do Outlook](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089). **Quando as mensagens são autorizadas com êxito devido a remetentes confiáveis, você verá SFV: SFE no X-Forefront-antispam-Report** , que indica que a filtragem de spam/spoof/Phish será ignorada.

## <a name="use-anti-spam-policy-ip-allow-lists"></a>Usar listas de permissões de IP de política antispam

Quando não é possível usar o ETRs para permitir globalmente um remetente específico durante a validação da autenticação do remetente ou por meio da ligação de um domínio e IP juntos, a melhor opção é adicionar o remetente à *lista de IPs permitidos da política*antispam. [As etapas detalhadas podem ser encontradas em configurar o documento da política de filtro de conexão](https://docs.microsoft.com/office365/securitycompliance/configure-the-connection-filter-policy). É importante manter a lista de endereços IP permitidos no mínimo e evitar usar intervalos de endereços IP. Evite adicionar intervalos de endereços IP que pertençam a serviços de consumidor ou infraestruturas compartilhadas e *Verifique* também se você revisar a lista de endereços IP permitidos regularmente e remover os que não são mais necessários.

> [!CAUTION]
> A configuração de políticas antispam para permitir com base no endereço IP do remetente resultará em ignorar a filtragem de spam para todas as mensagens desse endereço IP na regra de permissão. Isso cria um alto risco de atores defeituosos enviando emails que seriam filtrados de outra forma. Esse método também ignora todos os filtros de spam, as verificações de autenticação do remetente e os territórios da mensagem na caixa de entrada do usuário, aumentando o risco.

## <a name="use-anti-spam-policy-senderdomain-allow-lists"></a>Usar listas de permissões de remetente/domínio de política antispam

A opção menos desejável é autorizar por remetente/domínio. Essa opção deve ser evitada *se for possível* que ela ignore a proteção de spam/spoof/Phish completamente e não avalie a autenticação do remetente. Esse método aumenta o risco de receber emails de atores incorretos e é melhor recomendável temporariamente e somente durante o teste. As etapas detalhadas podem ser encontradas em [configurar seu documento de políticas de filtro de spam](https://docs.microsoft.com/office365/securitycompliance/configure-your-spam-filter-policies) .

O limite máximo para essas listas é de aproximadamente 1000 entradas; no entanto, você poderá inserir 30 entradas no Portal. Você deve usar o PowerShell para adicionar mais de 30 entradas.

> [!CAUTION]
> A configuração de políticas antispam para *permitir o domínio remetente/permitido* resultará em mensagens que ignoram a filtragem de spam para uma) de mensagens de remetentes na lista de permissões, ou b, todos os remetentes de um domínio permitido. Esse método aumenta significativamente os spammers de risco podem falsificar o domínio de envio (ou representar o endereço de email completo) que ignora todos os filtros de spam, verificações de autenticação de remetentes e envia a mensagem diretamente para a caixa de entrada de uma pessoa.
> 
> Não adicione domínios que você possui ou domínios populares (por exemplo `microsoft.com`,) à regra de fluxo de emails como uma condição. Esse método é considerado de alto risco, uma vez que cria oportunidades de atores incorretos para enviar emails que, de outra forma, seriam filtrados, aumentando o risco.

> [!IMPORTANT]
> As informações sobre como criar uma **lista de remetentes bloqueados** estão [aqui](create-block-sender-lists-in-office-365.md).
