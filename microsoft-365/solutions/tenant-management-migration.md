---
title: Etapa 4. Migração para seu Microsoft 365 para locatários corporativos
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
- tenant-management
- m365solution-scenario
ms.custom:
- Ent_Solutions
description: Migre seus Windows, aplicativos Office cliente e Office servidores para seus Microsoft 365 locatários.
ms.openlocfilehash: 336dee2e62c6d0917c437252ba1d741c304998fa
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929139"
---
# <a name="step-4-migration-for-your-microsoft-365-for-enterprise-tenants"></a>Etapa 4. Migração para seu Microsoft 365 para locatários corporativos

A maioria das organizações corporativas tem um ambiente heterogêneo que inclui várias versões de sistemas operacionais, software cliente e software de servidor. Microsoft 365 para empresas inclui as versões mais seguras dos principais componentes da infraestrutura de TI. Ele também inclui recursos de produtividade projetados para tirar proveito das tecnologias de nuvem.

Para maximizar o valor comercial do Microsoft 365 de produtos integrados para empresas, comece a planejar e implementar uma estratégia para migrar essas versões:

| From | Para |
|:-------|:-----|
| Windows 7 e Windows 8.1 | Windows 10 Enterprise |
| Office produtos cliente instalados nos dispositivos do seu funcionário | Microsoft 365 Apps para empresas |
| Office de servidor instalados em servidores locais | Seus serviços equivalentes baseados em nuvem no Microsoft 365 |
|  |  |

## <a name="migrating-to-windows-10"></a>Migrando para Windows 10

Cada Microsoft 365 para licença corporativa inclui uma licença para Windows 10 Enterprise. Para migrar seus dispositivos que Windows 7 ou Windows 8.1, você pode fazer uma atualização in-locar. O suporte terminou para Windows 7 em *14 de janeiro de 2020*. 

Para obter métodos adicionais de instalação Windows 10 Enterprise além de uma atualização in-locar, [consulte Windows 10 cenários de implantação.](/windows/deployment/windows-10-deployment-scenarios) Você também pode [planejar a implantação do Windows 10](/windows/deployment/planning/) por conta própria.

## <a name="migrating-to-microsoft-365-apps-for-enterprise"></a>Migrando para Microsoft 365 Apps para Grandes Empresas

Microsoft 365 para empresas inclui Microsoft 365 Apps para Grandes Empresas, uma versão dos produtos cliente do Office (Word, PowerPoint, Excel e Outlook) instalados e atualizados da nuvem da Microsoft. Para obter mais informações, consulte [Sobre Microsoft 365 Apps para Grandes Empresas](/deployoffice/about-microsoft-365-apps).

Em vez de manter seus computadores atualizados para Office 2019 ou versões anteriores, tome as seguintes etapas:

1. Obter e atribuir uma Microsoft 365 para seus usuários.
2. Desinstale Office 2013 ou Office 2016 em seus computadores.
3. Instale Microsoft 365 Apps para Grandes Empresas, individualmente ou durante uma implantação de IT. Para obter mais informações, veja o [Guia de implantação para o Microsoft 365 Apps](/deployoffice/deployment-guide-microsoft-365-apps).

Microsoft 365 Apps para Grandes Empresas instala atualizações de segurança e novas atualizações de recursos automaticamente e pode tirar proveito dos serviços baseados em nuvem no Microsoft 365 para aumentar a segurança e a produtividade.

## <a name="migrating-on-premises-servers-and-data-to-microsoft-365"></a>Migrando servidores e dados locais para Microsoft 365

O Microsoft 365 para empresas inclui versões baseadas em nuvem de serviços de servidor Office que usam algumas das mesmas ferramentas que as versões locais do software de servidor Office, como navegadores da Web e o cliente Outlook. Esses serviços baseados em nuvem são atualizados automaticamente para segurança e novos recursos. Após a migração, seu departamento de IT pode economizar o tempo necessário para manter e atualizar servidores locais.

Use os seguintes recursos para obter informações sobre como migrar usuários e dados para cargas de trabalho Microsoft 365 específicas:

- [Mover caixas de correio de caixas de correio locais Exchange Server para Exchange Online](/exchange/hybrid-deployment/move-mailboxes)
- [Migrar SharePoint dados do SharePoint Server para SharePoint Online](/sharepointmigration/migrate-to-sharepoint-online)
- [Migrar Skype for Business Online para Microsoft Teams](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

## <a name="transition-your-entire-organization"></a>Transição para toda a organização

Para obter uma imagem melhor de como mover toda a sua organização para os produtos e serviços Microsoft 365 para empresas, baixe este cartaz de transição:

[![Imagem mostrando o cartaz Transição para Microsoft 365.](../media/microsoft-365-overview/transition-org-to-m365.png)](https://download.microsoft.com/download/2/c/7/2c7bcc04-aae3-4604-9707-1ffff66b9851/transition-org-to-m365.pdf)

Esse pôster de duas páginas é uma maneira rápida de fazer o inventário da infraestrutura existente. Use-o para obter orientações para mover para um produto ou serviço Microsoft 365 para empresas. Ele mostra Windows e Office produtos e outros elementos de infraestrutura e segurança, como gerenciamento de dispositivos, proteção contra ameaças e identidade e proteção de informações e conformidade.

## <a name="results-of-step-4"></a>Resultados da Etapa 4

Para migração para seu Microsoft 365 locatário, você determinou:

- Quais dispositivos estão executando Windows 7 ou Windows 8.1 e o plano para atualizá-los para Windows 10 Enterprise.
- Quais dispositivos estão executando os aplicativos Office cliente e o plano para atualizá-los para Microsoft 365 aplicativos para empresas.
- Quais serviços de servidor Office local devem ser migrados para seu equivalente Microsoft 365 e o plano para migrar eles e seus dados.

Aqui está um exemplo de um locatário com uma migração concluída de servidores locais.

![Exemplo de um locatário com uma migração concluída de servidores locais](../media/tenant-management-overview/tenant-management-tenant-build-step4.png)

Nesta ilustração, a organização tem:

- Migrou suas caixas de correio Exchange Server local para Exchange Online.
- Migrou seus sites e dados locais SharePoint Server para SharePoint no Microsoft 365.

## <a name="ongoing-maintenance-for-migration"></a>Manutenção contínua para migração

Em uma base contínua, talvez seja necessário:

- Dependendo do estado da migração Exchange caixa de correio, continue a rolar a transição para Exchange Online para sua organização.
- Dependendo do estado de sua migração de site SharePoint local, continue a rolagem da transição para SharePoint em Microsoft 365 para sua organização.

## <a name="next-step"></a>Próxima etapa

[![Etapa 5. Implantar o gerenciamento de dispositivos e aplicativos](../media/tenant-management-overview/tenant-management-step-grid-device-mgmt.png)](tenant-management-device-management.md)

Continue com [o gerenciamento de dispositivos e aplicativos](tenant-management-device-management.md) para implantar o gerenciamento de dispositivos e aplicativos.