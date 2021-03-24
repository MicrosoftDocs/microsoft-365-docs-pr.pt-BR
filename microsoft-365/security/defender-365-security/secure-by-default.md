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
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Saiba mais sobre a configuração segura por padrão no Exchange Online Protection (EOP)
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f1b495a9c985077dfc88d1da7a221bb60ca10df9
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054241"
---
# <a name="secure-by-default-in-office-365"></a>Seguro por padrão no Office 365

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

"Seguro por padrão" é um termo usado para definir as configurações padrão mais seguras possíveis.

No entanto, a segurança precisa ser equilibrada com a produtividade. Isso pode incluir o balanceamento entre:

- **Usabilidade**: as configurações não devem ficar no caminho da produtividade do usuário.
- **Risco**: a segurança pode bloquear atividades importantes.
- **Configurações herdadas**: Algumas configurações para produtos e recursos mais antigos podem precisar ser mantidas por motivos comerciais, mesmo que novas configurações modernas sejam aprimoradas.

As organizações do Microsoft 365 com caixas de correio no Exchange Online são protegidas pela Proteção do Exchange Online (EOP). Essa proteção inclui:

- Email com malware suspeito será automaticamente colocado em quarentena e os destinatários serão notificados. Consulte [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).
- Os emails identificados como phishing de alta confiança serão manipulados de acordo com a ação de política anti-spam. Consulte [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).

Para obter mais informações sobre o EOP, consulte [Visão geral da Proteção do Exchange Online.](exchange-online-protection-overview.md)

Como a Microsoft deseja manter nossos clientes seguros por padrão, algumas substituições de locatários não são aplicadas a malware ou phishing de alta confiança. Essas substituições incluem:

- Listas de remetentes permitidas ou listas de domínio permitidos (políticas anti-spam)
- Senders seguros do Outlook
- Lista de IDS (filtragem de conexão)

Mais informações sobre essas substituições podem ser encontradas em [Criar listas de remetentes seguros.](create-safe-sender-lists-in-office-365.md)

> [!NOTE]
> Estamos no processo de preterindo  a ação Mover mensagem para Lixo Eletrônico para um veredito de email de **phishing** de alta confiança em políticas anti-spam do EOP. Políticas anti-spam que usam essa ação para mensagens de phishing de alta confiança serão convertidas em **mensagem de quarentena**. A **ação Redirecionar mensagem para endereço de email** para mensagens de phishing de alta confiança não é afetada.

A segurança por padrão não é uma configuração que pode ser ativas ou desligadas, mas é a maneira como nossa filtragem funciona fora da caixa para manter mensagens potencialmente perigosas ou indesejadas fora de suas caixas de correio. As mensagens de malware e phishing de alta confiança devem ser colocadas em quarentena. Somente os administradores podem gerenciar mensagens que estão em quarentena como malware ou phishing de alta confiança e também podem relatar falsos positivos para a Microsoft a partir daí. Para obter mais informações, consulte [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md)

## <a name="more-on-why-were-doing-this"></a>Mais informações sobre o motivo pelo qual estamos fazendo isso

O espírito de estar seguro por padrão é: estamos tomando a mesma ação na mensagem que você tomaria se você sabia que a mensagem era mal-intencionada, mesmo quando uma exceção configurada permitia que a mensagem fosse entregue. Essa é a mesma abordagem que sempre fizemos em malware e agora estamos estendendo esse mesmo comportamento para mensagens de phishing de alta confiança.

Nossos dados indicam que um usuário tem 30 vezes mais probabilidade de clicar em um link mal-intencionado em mensagens na pasta Lixo Eletrônico versus Quarentena. Nossos dados também indicam que a taxa de falsos positivos (boas mensagens marcadas como ruins) para mensagens de phishing de alta confiança é muito baixa, e os administradores podem resolver falsos positivos com envios de administrador.

Também determinamos que os remetentes permitidos e listas de domínio permitidos em políticas anti-spam e Remetentes Seguros no Outlook eram muito amplos e estavam causando mais danos do que bons.

Para colocá-lo de outra maneira: como um serviço de segurança, estamos agindo em seu nome para impedir que seus usuários seja comprometidos. 

## <a name="exceptions"></a>Exceptions

A única substituição que permite que a mensagem de phishing de alta confiança ignore a filtragem são as regras de fluxo de emails do Exchange (também conhecidas como regras de transporte). Para usar regras de fluxo de emails para ignorar a filtragem, consulte [Use mail flow rules to set the SCL in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).

Você só deve considerar o uso de substituições nos seguintes cenários:

- Simulações de phishing: ataques simulados podem ajudá-lo a identificar usuários vulneráveis antes de um ataque real afetar sua organização.
- Caixas de correio de Segurança/SecOps: caixas de correio dedicadas usadas pelas equipes de segurança para receber mensagens não filtradas (boas e ruins). Em seguida, o Teams pode revisar para ver se eles contêm conteúdo mal-intencionado.
- Filtros de terceiros: Seguro por padrão não se aplica quando o registro MX do domínio não aponta para o Office 365.
- Falsos positivos: talvez você queira permitir temporariamente determinadas mensagens que ainda estão sendo analisadas pela Microsoft [por meio de envios de administrador.](admin-submission.md) Como com todas as substituições, é recomendável que sejam temporárias.
