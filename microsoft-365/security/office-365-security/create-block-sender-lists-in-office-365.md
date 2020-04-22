---
title: Criar listas de remetentes bloqueados
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150s
description: Os administradores podem aprender sobre as opções disponíveis no Microsoft 365 e EOP para bloquear mensagens de entrada.
ms.openlocfilehash: 626eff3a1ea28cc16b12acaaa2ba52f7d094a347
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637683"
---
# <a name="create-blocked-sender-lists"></a>Criar listas de remetentes bloqueados

Se você for um cliente Microsoft 365 com caixas de correio no Exchange Online ou um cliente autônomo do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, o EOP oferece várias maneiras de bloquear emails de remetentes indesejados. Essas opções incluem remetentes bloqueados do Outlook, listas de remetentes bloqueados ou listas de domínios bloqueados em políticas antispam, regras de fluxo de emails do Exchange (também conhecidas como regras de transporte) e a lista de IPs bloqueados (filtragem de conexão). Coletivamente, você pode imaginar essas opções como _listas de remetentes bloqueados_.

O melhor método para bloquear remetentes varia de acordo com o escopo do impacto. Para um único usuário, a solução certa pode ser remetentes bloqueados do Outlook. Para muitos usuários, uma das outras opções seria mais apropriada. As opções a seguir são classificadas pelo escopo de impacto e por amplitude. A lista vai de estreito a amplo, mas *Leia as especificações* de recomendações completas.

1. Remetentes bloqueados do Outlook (a lista de remetentes bloqueados que está armazenada em cada caixa de correio)

2. Listas de remetentes bloqueados ou listas de domínios bloqueados (políticas antispam)

3. Regras do fluxo de email

4. A lista de bloqueios de IP (filtragem de conexão)

> [!NOTE]
> Embora você possa usar as configurações de bloco em toda a organização para tratar de falsos negativos (spam perdido), você também deve enviar essas mensagens para a Microsoft para análise. O gerenciamento de falsos negativos usando listas de bloqueio aumenta significativamente a sobrecarga administrativa. Se você usar listas de bloqueio para desviar o spam perdido, precisará manter o tópico [relatar mensagens e arquivos para a Microsoft](report-junk-email-messages-to-microsoft.md) em mãos.

Por outro lado, você também tem várias opções para sempre permitir emails de fontes específicas usando _listas de remetentes seguros_. Para obter mais informações, consulte [criar listas de remetentes seguros](create-safe-sender-lists-in-office-365.md).

## <a name="use-outlook-blocked-senders"></a>Usar remetentes bloqueados do Outlook

Quando apenas um pequeno número de usuários recebe emails indesejados, os usuários ou administradores podem adicionar os endereços de email do remetente à lista de remetentes bloqueados na caixa de correio. Para obter instruções, consulte [definir configurações de lixo eletrônico em caixas de correio do Exchange Online](configure-junk-email-settings-on-exo-mailboxes.md).

Quando as mensagens são bloqueadas com êxito devido à lista de remetentes bloqueados de um usuário, o campo de cabeçalho **X-Forefront-antispam-Report** conterá o valor `SFV:BLK`.

> [!NOTE]
> Se as mensagens indesejadas forem boletins informativos de uma fonte confiável e reconhecível, a cancelamento do email é outra opção para impedir que o usuário receba as mensagens.

## <a name="use-blocked-sender-lists-or-blocked-domain-lists"></a>Usar listas de remetentes bloqueados ou listas de domínios bloqueados

Quando vários usuários são afetados, o escopo é mais largo, portanto, a melhor opção é bloquear listas de remetentes bloqueados ou listas de domínios bloqueados em políticas antispam. As mensagens de remetentes nas listas são marcadas como **spam**e a ação que você configurou para o filtro de **spam** veredicto é tomada na mensagem. Para obter mais informações, consulte [Configure anti-spam Policies](configure-your-spam-filter-policies.md).

O limite máximo para essas listas é de aproximadamente 1000 entradas.

## <a name="use-mail-flow-rules"></a>Usar regras de fluxo de email

Se você precisar bloquear mensagens enviadas para usuários específicos ou em toda a organização, você pode usar regras de fluxo de emails. As regras de fluxo de emails são mais flexíveis do que as listas de remetentes bloqueados ou remetentes bloqueados, pois também podem procurar palavras-chave ou outras propriedades nas mensagens indesejadas.

Independentemente das condições ou exceções que você usa para identificar as mensagens, você configura a ação para definir o nível de confiança de spam (SCL) da mensagem como 9, que marca uma mensagem de **spam de alta confiança**. Para obter mais informações, consulte [use Mail Flow rules to set the SCL in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).

> [!IMPORTANT]
> É fácil criar regras *que são muito* agressivas, portanto, é importante que você identifique apenas as mensagens que deseja bloquear usando critérios muito específicos. Além disso, certifique-se de habilitar a auditoria na regra e testar os resultados da regra para garantir que tudo funcione conforme o esperado.

## <a name="use-the-ip-block-list"></a>Usar a lista de IPs bloqueados

Quando não é possível usar uma das outras opções para bloquear um *remetente, você deve usar* a lista de IPs bloqueados na política de filtro de conexão. Para obter mais informações, consulte [Configurar a política de filtro de conexão](configure-the-connection-filter-policy.md). É importante manter o número mínimo de IPs bloqueados, portanto, *não* é recomendável bloquear intervalos de endereços IP inteiros.

Você deve *especialmente* evitar a adição de intervalos de endereços IP que pertençam aos serviços de consumidor (por exemplo, Outlook.com) ou infraestruturas compartilhadas, e também garantir que você revise a lista de endereços IP bloqueados como parte da manutenção normal.
