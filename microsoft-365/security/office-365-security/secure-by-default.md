---
title: Seguro por padrão no Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Saiba mais sobre a configuração de segurança por padrão no Exchange Online Protection (EOP)
ms.openlocfilehash: 758d2169d80630a38c0b498e8c1848568e5ec941
ms.sourcegitcommit: 1beaf89d2faa32f11fe1613be2fa2b31c4bc4a91
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/08/2020
ms.locfileid: "49602026"
---
# <a name="secure-by-default-in-office-365"></a>Seguro por padrão no Office 365

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

"Seguro por padrão" é um termo usado para definir as configurações padrão mais seguras possível.

No entanto, a segurança precisa ser balanceada com produtividade. Isso pode incluir o equilíbrio entre:

- **Usabilidade**: as configurações não devem obter o modo de produtividade do usuário.
- **Risco**: a segurança pode bloquear atividades importantes.
- **Configurações herdadas**: algumas configurações de produtos e recursos antigos podem precisar ser mantidas por motivos comerciais, mesmo se novas configurações modernas forem aprimoradas.

As organizações 365 da Microsoft com caixas de correio no Exchange Online são protegidas pela proteção do Exchange Online (EOP). Esta proteção inclui:

- Email com malware suspeito será automaticamente colocado em quarentena e os destinatários serão notificados. Consulte [Configure anti-malware Policies in EOP](configure-anti-malware-policies.md).
- Os emails identificados como phishing de alta confiança serão manipulados de acordo com a ação da política antispam. Consulte [Configure anti-spam Policies in EOP](configure-your-spam-filter-policies.md).

Para obter mais informações sobre o EOP, consulte [Exchange Online Protection Overview](exchange-online-protection-overview.md).

Como a Microsoft deseja manter nossos clientes seguros por padrão, alguns locatários substituídos não são aplicados a malware ou phishing de alta confiança. Essas substituições incluem:

- Listas de remetentes permitidos ou listas de domínios permitidos (políticas antispam)
- Remetentes confiáveis do Outlook
- Lista de permissões de IP (filtragem de conexão)

Mais informações sobre essas substituições podem ser encontradas em [criar listas de remetentes seguros](create-safe-sender-lists-in-office-365.md).

A segurança por padrão não é uma configuração que possa ser ativada ou desativada, mas é a maneira como nossa filtragem funciona para manter mensagens potencialmente perigosas ou indesejadas fora de suas caixas de correio. Mensagens de phishing de malware e de alta confiança devem ser colocadas em quarentena. Somente os administradores podem gerenciar mensagens colocadas em quarentena como phishing de malware ou de alta confiança, e também podem relatar falsos positivos para a Microsoft. Para obter mais informações, consulte [gerenciar mensagens em quarentena e arquivos como um administrador no EOP](manage-quarantined-messages-and-files.md)

## <a name="more-on-why-were-doing-this"></a>Saiba mais sobre por que estamos fazendo isso

O espírito de ser seguro por padrão é: estamos executando a mesma ação na mensagem que você usaria se você soubesse a mensagem mal-intencionada, mesmo se houvesse permissão no local. Essa é a mesma abordagem que usamos em malware, e agora estamos estendendo esse comportamento para mensagens de phishing de alta confiança. Nossos dados indicam que a taxa de falsos positivos para mensagens de phishing de alta confiança é muito baixa, e os administradores podem resolver qualquer falso positivo com os envios de administrador. Nossos dados também indicam que as listas de remetentes permitidos e as listas de domínio permitidas em políticas antispam e remetentes confiáveis no Outlook eram muito largas e causam mais danos do que bom.

Para colocá-lo de outra maneira: como um serviço de segurança, estamos agindo em seu nome para impedir que os usuários sejam comprometidos. Além disso, a segurança por padrão não é uma tomada completa das opções disponíveis para mensagens de phishing de alta confiança em políticas antispam. Embora seja recomendável colocar em quarentena, as outras ações que sempre estão disponíveis estão ainda disponíveis (mover para a pasta lixo eletrônico ou redirecionar para um endereço de email).

## <a name="exceptions"></a>Exceptions

A única substituição que permite que a mensagem de phishing de alta confiança seja ignorada é as regras de fluxo de email do Exchange (também conhecidas como regras de transporte). Para usar regras de fluxo de email para ignorar a filtragem, confira [usar regras de fluxo de emails para definir o SCL em mensagens](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).

Você deve considerar apenas o uso de substituições nos seguintes cenários:

- Simulações de phishing: ataques simulados podem ajudá-lo a identificar usuários vulneráveis antes que um ataque real afete sua organização.
- Segurança/caixas de correio do SecOps: caixas de correio dedicadas usadas pelo Security Teams para obter mensagens não filtradas (tanto boas quanto ruins). O Microsoft Teams pode então revisar para ver se eles contêm conteúdo mal-intencionado.
- Filtros de terceiros: alguns fornecedores terceirizados recomendarão a desativação do EOP (SCL =-1), pois o filtro de terceiros gerenciará a filtragem de email. A Microsoft não recomenda desativar o EOP como EOP é necessário para [o Microsoft defender para Office 365](office-365-atp.md). Em vez disso, a recomendação aqui é ativar a [filtragem avançada de conectores](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).
- Falsos positivos: Talvez você queira permitir temporariamente determinadas mensagens que ainda estão sendo analisadas pela Microsoft [por meio de envios de administrador](admin-submission.md). Assim como ocorre com todas as substituições, é recomendável que elas sejam temporárias.
