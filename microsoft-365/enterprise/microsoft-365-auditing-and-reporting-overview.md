---
title: Auditoria e relatórios nos serviços em nuvem da Microsoft
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- M365-analytics
- SPO_Content
f1.keywords:
- NOCSH
description: Uma visão geral dos recursos de auditoria e relatórios no Office 365, no Microsoft 365 e no serviço Assurance.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 89c7ff3556e71ead8ced94bdc396da1c862c2f57
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695343"
---
# <a name="auditing-and-reporting-in-microsoft-cloud-services"></a>Auditoria e relatórios nos serviços em nuvem da Microsoft

Os serviços de nuvem da Microsoft incluem vários recursos de auditoria e de relatórios que você pode usar para controlar as atividades de usuário e administrativas dentro de seus locatários, exemplos incluem alterações feitas nas definições de configuração do locatário do Exchange Online e do SharePoint Online e alterações feitas por usuários em documentos e outros itens. Você pode usar as informações de auditoria e os relatórios disponíveis nos serviços de nuvem da Microsoft para gerenciar com mais eficácia a experiência do usuário, reduzir os riscos e cumprir as obrigações de conformidade.

## <a name="security--compliance-centers"></a>Centros de segurança & conformidade

O centro de [conformidade & segurança da microsoft 365](https://protection.office.com), a [central de segurança da Microsoft 365](https://security.microsoft.com)e [o centro de conformidade da Microsoft 365](https://compliance.microsoft.com) são portais de um único ponto para proteger os dados em sua organização e incluem vários recursos de auditoria e relatórios. Esses centros ajudam com suas necessidades de proteção e conformidade de dados e auditoria de usuário e atividade de administrador. Você pode acessar esses centros usando sua conta de administrador de assinatura.

Esses centros incluem painéis de navegação para o acesso a vários recursos:

- **Alertas:** Permite gerenciar alertas, exibir alertas relacionados à segurança e gerenciar alertas avançados usando o [Cloud app Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security).
- **Permissões:** Permite que você [atribua permissões](https://docs.microsoft.com/microsoft-365/security/office-365-security/grant-access-to-the-security-and-compliance-center) como o administrador de conformidade, o Gerenciador de descoberta eletrônica e outros usuários em sua organização para que eles possam realizar tarefas nesses centros. Você atribui permissões para a maioria dos recursos em cada centro, mas outras permissões devem ser configuradas usando o centro de administração do Exchange e o centro de administração do SharePoint.
- **Gerenciamento de ameaças:** Permite que você crie e aplique políticas de gerenciamento de dispositivos usando o [Gerenciamento de dispositivos móveis do Microsoft 365](https://support.microsoft.com/office/overview-of-mobile-device-management-mdm-for-microsoft-365-faa7d8e5-645d-4d59-839c-c8d4c1869e4a), para configurar políticas de [prevenção de perda de dados](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies) (DLP) para sua organização, para configurar o filtro de emails, o anti-malware, o DomainKeys identificad mail (DKIM), anexos seguros, links seguros e aplicativos OAuth.
- **Governança de dados:** Permite que você [importe dados de email ou do SharePoint de outros sistemas para o Microsoft 365](https://support.office.com/article/Import-PST-files-or-SharePoint-data-to-Office-365-ba688e0a-0fcb-4bd7-8e57-2b669564ea84), [Configure caixas de correio de arquivo morto](https://support.office.com/article/Enable-archive-mailboxes-in-the-Office-365-Security-Compliance-Center-268a109e-7843-405b-bb3d-b9393b2342ce)e defina [as políticas de retenção](https://docs.microsoft.com/microsoft-365/compliance/retention-policies) para email e outros conteúdos dentro da sua organização.
- **Investigação de & de pesquisa:** Fornece ferramentas de [pesquisa de conteúdo](https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a), [log de auditoria](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c), quarentena e gerenciamento de [casos de descoberta eletrônica](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da) para rapidamente analisar a atividade nas caixas de correio do Exchange Online, grupos e pastas públicas, SharePoint Online e onedrive for Business.
- **Relatórios:** Permite acessar rapidamente [relatórios](https://support.office.com/article/Reports-in-the-Office-365-Security-Compliance-Center-7acd33ce-1ec8-49fb-b625-43bac7b58c5a) do SharePoint Online, onedrive for Business, Exchange Online e Azure AD.
- **Garantia de serviço:** Fornece informações sobre como a Microsoft mantém segurança, privacidade e conformidade com padrões globais para o Microsoft 365, Azure, Microsoft Dynamics CRM Online, Microsoft Intune e outros serviços de nuvem. O também inclui acesso a aplicativos ISO, SOC e outros relatórios de auditoria de terceiros, além de controles auditados, que fornece detalhes sobre os vários controles que foram testados e verificados por auditores de terceiros do Microsoft 365.

## <a name="service-assurance"></a>Garantia de serviço

Muitas organizações em setores regulamentados estão sujeitas a grandes requisitos de conformidade. Para realizar suas próprias avaliações de risco, os clientes normalmente precisam de informações detalhadas sobre como o Microsoft 365 mantém a segurança e a privacidade de seus dados. A Microsoft está comprometida com a segurança e a privacidade dos dados do cliente em seus serviços de nuvem e para obter a confiança do cliente fornecendo uma visão transparente de suas operações e acesso fácil a relatórios e avaliações de conformidade independentes.

A garantia de serviço oferece transparência de operações e informações sobre como a Microsoft mantém a segurança, a privacidade e a conformidade dos dados do cliente no Microsoft 365. Ele inclui relatórios de auditoria de terceiros junto com uma biblioteca de White papers, perguntas frequentes e outros materiais nos tópicos da Microsoft 365, como criptografia de dados, resiliência de dados, gerenciamento de incidentes de segurança e muito mais. Os clientes podem usar essas informações para realizar suas próprias avaliações de riscos regulamentares. Os gerentes de conformidade podem atribuir a função "usuário de garantia de serviço" para conceder aos usuários acesso à garantia de serviço. O administrador de locatários também pode fornecer usuários externos, como auditores independentes, com acesso a informações no painel de garantia de serviço por meio do [Microsoft Cloud Service Trust portal](https://aka.ms/STP) (STP).

## <a name="onedrive-for-business-admin-center"></a>Centro de administração do OneDrive for Business

O centro de administração do Microsoft OneDrive ajuda você a gerenciar de forma rápida e fácil as configurações do OneDrive for Business de sua organização em um só lugar. Para usar o centro de administração do OneDrive, é necessário o acesso ao onedrive.com. Você também deve ser um administrador global para sua organização ou um administrador personalizado com a função de administrador do SharePoint. Acessar o centro de administração do OneDrive for Business em [https://admin.onedrive.com](https://admin.onedrive.com/) .

Os principais recursos incluem uma área de conformidade que oferece aos administradores links para o centro de gerenciamento apropriado para cenários principais, como pesquisar o log de auditoria, trabalhar com DLP, retenção, eDiscovery e alertas.

## <a name="related-links"></a>Links relacionados

- [Recursos de pesquisa e descoberta eletrônica](microsoft-365-ediscovery-and-search-features.md)
- [Recursos de relatório do Microsoft 365](microsoft-365-reporting-features.md)
- [API da atividade de gerenciamento do Microsoft 365](microsoft-365-management-activity-api.md)
- [Migrações de caixas de correio do Microsoft 365](microsoft-365-mailbox-migrations.md)
- [Log interno para engenharia do Microsoft 365](microsoft-365-internal-logging.md)
