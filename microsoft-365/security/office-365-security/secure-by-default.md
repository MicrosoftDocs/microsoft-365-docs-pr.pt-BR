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
description: Saiba mais sobre a configuração segura por padrão no Exchange Online Protection (EOP)
ms.openlocfilehash: 8db8e7af569114e5829d24d65b8eee89c9dce8c3
ms.sourcegitcommit: a76de3d1604d755b29053e7bf557c0008be6ad23
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2021
ms.locfileid: "49787968"
---
# <a name="secure-by-default-in-office-365"></a>Seguro por padrão no Office 365

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

"Seguro por padrão" é um termo usado para definir as configurações padrão mais seguras possíveis.

No entanto, a segurança precisa ser balanceada com a produtividade. Isso pode incluir o balanceamento entre:

- **Usabilidade:** as configurações não devem ficar no caminho da produtividade do usuário.
- **Risco:** a segurança pode bloquear atividades importantes.
- **Configurações herdadas:** algumas configurações para produtos e recursos mais antigos talvez precisem ser mantidas por motivos comerciais, mesmo que configurações novas e modernas sejam aprimoradas.

As organizações do Microsoft 365 com caixas de correio no Exchange Online são protegidas pelo Exchange Online Protection (EOP). Essa proteção inclui:

- Emails com malware suspeito serão automaticamente colocados em quarentena e os destinatários serão notificados. Consulte [Configurar políticas anti-malware no EOP.](configure-anti-malware-policies.md)
- Os emails identificados como phishing de alta confiança serão tratados de acordo com a ação da política anti-spam. Consulte [Configurar políticas anti-spam no EOP.](configure-your-spam-filter-policies.md)

Para obter mais informações sobre o EOP, consulte a [visão geral do Exchange Online Protection.](exchange-online-protection-overview.md)

Como a Microsoft deseja manter nossos clientes seguros por padrão, algumas substituições de locatários não são aplicadas para malware ou phishing de alta confiança. Essas substituições incluem:

- Listas de remetentes permitidos ou listas de domínios permitidos (políticas anti-spam)
- Outlook Safe Senders
- Lista de IIs (filtragem de conexão)

Mais informações sobre essas substituições podem ser encontradas em [Criar listas de remetentes seguros.](create-safe-sender-lists-in-office-365.md)

Por padrão, a segurança não é uma configuração que pode ser 1000 por padrão, mas é a maneira como a filtragem funciona para manter mensagens potencialmente perigosas ou indesejadas fora de suas caixas de correio. Mensagens de phishing de malware e alta confiança devem ser colocadas em quarentena. Somente os administradores podem gerenciar mensagens que estão em quarentena como malware ou phishing de alta confiança, e eles também podem relatar falsos positivos para a Microsoft a partir daí. Para obter mais informações, consulte Gerenciar mensagens e arquivos em [quarentena como administrador no EOP](manage-quarantined-messages-and-files.md)

## <a name="more-on-why-were-doing-this"></a>Mais informações sobre por que estamos fazendo isso

O problema de ser seguro por padrão é: estamos tomando a mesma ação na mensagem que você tomaria se tivesse a mensagem mal-intencionada, mesmo que houvesse uma autorização no local. Essa é a mesma abordagem usada no malware e, agora, estamos estendendo esse mesmo comportamento para mensagens de phishing de alta confiança. Nossos dados indicam que a taxa de falsos positivos para mensagens de phishing de alta confiança é muito baixa e os administradores podem resolver falsos positivos com envios de administrador. Nossos dados também indicam que as listas de remetentes permitidos e listas de domínios permitidos em políticas anti-spam e remetentes seguros no Outlook eram muito amplas e causando mais danos do que o bem.

Para colocá-lo de outra maneira: como um serviço de segurança, estamos agindo em seu nome para impedir que seus usuários seja comprometidos. Além disso, a segurança por padrão não é uma adoção total de suas opções disponíveis para mensagens de phishing de alta confiança em políticas anti-spam. Embora recomendemos a Quarentena, as outras ações que sempre estavam disponíveis ainda estão disponíveis (Mover para a pasta Lixo Eletrônico ou Redirecionar para um endereço de email).

## <a name="exceptions"></a>Exceptions

A única substituição que permite que mensagens de phishing de alta confiança ignorem a filtragem são as regras de fluxo de emails do Exchange (também conhecidas como regras de transporte). Para usar regras de fluxo de emails para ignorar a filtragem, consulte Usar regras de fluxo de email [para definir o SCL em mensagens.](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)

Você só deve considerar o uso de substituições nos seguintes cenários:

- Simulações de phishing: ataques simulados podem ajudá-lo a identificar usuários vulneráveis antes de um ataque real afetar sua organização.
- Caixas de correio de Segurança/SecOps: caixas de correio dedicadas usadas por equipes de segurança para receber mensagens não filtradas (boas e ruins). Em seguida, o Teams pode analisar para ver se eles contêm conteúdo mal-intencionado.
- Filtros de terceiros: Seguro por padrão não se aplica quando o registro MX do domínio não aponta para o Office 365.
- Falsos positivos: talvez você queira permitir temporariamente determinadas mensagens que ainda estão sendo analisadas pela Microsoft por meio de [envios de administrador.](admin-submission.md) Assim como em todas as substituições, é recomendável que elas sejam temporárias.
