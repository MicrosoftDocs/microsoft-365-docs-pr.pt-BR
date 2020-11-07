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
description: Saiba como localizar e usar relatórios de segurança de email da sua organização. Relatórios de segurança de email estão disponíveis no centro de conformidade e segurança &.
ms.openlocfilehash: 0e38091981cd379dfc912be429c00d168dff775c
ms.sourcegitcommit: dab50e1cc5bba920720b80033c93457f5ca1c330
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2020
ms.locfileid: "48944408"
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
1. Email com malware suspeito será automaticamente colocado em quarentena e os destinatários serão notificados. Consulte [Configure anti-malware Policies in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-anti-malware-policies?view=o365-worldwide).
1. O email de phishing identificado como "alta confiança" será tratado de acordo com a ação da política antispam. Consulte [Configure anti-spam Policies in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-your-spam-filter-policies?view=o365-worldwide).

Como a Microsoft deseja manter nossos clientes seguros por padrão, alguns locatários substituídos não são aplicados para phishing ou golpe de alta confiança. Essas substituições incluem:
- Listas de remetentes permitidos ou listas de domínios permitidos (políticas antispam)
- Remetentes confiáveis do Outlook
- Lista de permissões de IP (filtragem de conexão)

Mais informações sobre essas substituições podem ser encontradas em [criar listas de remetentes seguros](https://docs.microsoft.com/microsoft-365/security/office-365-security/create-safe-sender-lists-in-office-365).

A segurança por padrão aqui não é uma configuração que possa ser ativada ou desativada, mas o modo como nossa filtragem funciona para manter mensagens potencialmente perigosas ou indesejadas fora de suas caixas de correio. O malware e o Phish de alta confiança devem ser enviados para a quarentena. Somente os administradores podem gerenciar mensagens que foram colocadas em quarentena como malware ou phishing de alta confiança e também podem relatar falsos positivos para a Microsoft. Para obter mais informações, consulte [gerenciar mensagens em quarentena e arquivos como um administrador no EOP](manage-quarantined-messages-and-files.md)

## <a name="exceptions"></a>Exceptions
As substituições que serão ignoradas por todos os filtros incluem:
- Regras de fluxo de transporte do Exchange (ETR)/mail.  Use regras de fluxo de emails para definir o nível de confiança de spam (SCL) em mensagens no EOP.
- Lista de permissões/bloqueios de locatários: gerenciar URLs e arquivos na lista de permissões/bloqueios de locatários.


Esses tipos de substituições são úteis para:
- Simulações de phishing: ataques simulados podem ajudá-lo a identificar usuários vulneráveis antes que um ataque real afete sua organização.
- Segurança/caixas de correio do SecOps: caixas de correio dedicadas usadas pelo Security Teams para obter mensagens não filtradas (tanto boas quanto ruins). O Microsoft Teams pode então revisar para ver se eles contêm conteúdo mal-intencionado.
- Filtros de terceiros: alguns fornecedores terceirizados recomendarão a desativação do EOP (SCL =-1), pois o filtro de terceiros gerenciará a filtragem de email.  A Microsoft não recomenda desativar o EOP como EOP é necessário para o defender para Office 365. 
- Falsos positivos: Talvez você queira permitir determinadas mensagens que ainda estão sendo analisadas pela Microsoft [por meio de envios de administrador](admin-submission.md). Assim como ocorre com todas as substituições, é recomendável que elas sejam temporárias.
