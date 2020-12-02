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
ms.openlocfilehash: 1a68c14a2d37f1fc3bfb032c4d3ca34c09a89890
ms.sourcegitcommit: 4cbb4ec26f022f5f9d9481f55a8a6ee8406968d2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/01/2020
ms.locfileid: "49527764"
---
# <a name="secure-by-default-in-office-365"></a>Seguro por padrão no Office 365

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

"Seguro por padrão" é um termo usado para definir as configurações padrão mais seguras possível.

No entanto, a segurança precisa ser balanceada com produtividade. Isso pode incluir o equilíbrio entre:

- Usabilidade: as configurações não devem obter o modo de produtividade do usuário.
- Risco: a segurança pode bloquear atividades importantes.
- Configurações herdadas: algumas configurações de produtos e recursos antigos podem precisar ser mantidas por motivos comerciais, mesmo se novas configurações modernas forem aprimoradas.

As organizações 365 da Microsoft com caixas de correio no Exchange Online são protegidas pela proteção do Exchange Online (EOP). Esta proteção inclui:

1. Email com malware suspeito será automaticamente colocado em quarentena e os destinatários serão notificados. Consulte [Configure anti-malware Policies in EOP](configure-anti-malware-policies.md).
1. O email de phishing identificado como "alta confiança" será tratado de acordo com a ação da política antispam. Consulte [Configure anti-spam Policies in EOP](configure-your-spam-filter-policies.md).

Como a Microsoft deseja manter nossos clientes seguros por padrão, alguns locatários substituídos não são aplicados a malware ou phishing de alta confiança. Essas substituições incluem:

- Listas de remetentes permitidos ou listas de domínios permitidos (políticas antispam)
- Remetentes confiáveis do Outlook
- Lista de permissões de IP (filtragem de conexão)

Mais informações sobre essas substituições podem ser encontradas em [criar listas de remetentes seguros](create-safe-sender-lists-in-office-365.md).

A segurança por padrão aqui não é uma configuração que possa ser ativada ou desativada, mas o modo como nossa filtragem funciona para manter mensagens potencialmente perigosas ou indesejadas fora de suas caixas de correio. Malware e phishing de alta confiança devem ser enviados para a quarentena. Somente os administradores podem gerenciar mensagens que foram colocadas em quarentena como malware ou phishing de alta confiança e também podem relatar falsos positivos para a Microsoft. Para obter mais informações, consulte [gerenciar mensagens em quarentena e arquivos como um administrador no EOP](manage-quarantined-messages-and-files.md)

## <a name="exceptions"></a>Exceptions

A única substituição que permite que a mensagem de phishing de alta confiança seja ignorada é as regras de fluxo de email do Exchange (também conhecidas como regras de transporte). Para usar regras de fluxo de email para ignorar a filtragem, confira [usar regras de fluxo de emails para definir o SCL em mensagens](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).

Substituições só devem ser usadas para:

- Simulações de phishing: ataques simulados podem ajudá-lo a identificar usuários vulneráveis antes que um ataque real afete sua organização.
- Segurança/caixas de correio do SecOps: caixas de correio dedicadas usadas pelo Security Teams para obter mensagens não filtradas (tanto boas quanto ruins). O Microsoft Teams pode então revisar para ver se eles contêm conteúdo mal-intencionado.
- Filtros de terceiros: alguns fornecedores terceirizados recomendarão a desativação do EOP (SCL =-1), pois o filtro de terceiros gerenciará a filtragem de email. A Microsoft não recomenda desativar o EOP como EOP é necessário para o defender para Office 365. Em vez disso, a recomendação aqui é ativar a [filtragem avançada de conectores](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) .
- Falsos positivos: Talvez você queira permitir determinadas mensagens que ainda estão sendo analisadas pela Microsoft [por meio de envios de administrador](admin-submission.md). Assim como ocorre com todas as substituições, é recomendável que elas sejam temporárias.
