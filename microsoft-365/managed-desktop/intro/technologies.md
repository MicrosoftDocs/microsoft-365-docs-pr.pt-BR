---
title: Tecnologias de Área de Trabalho Gerenciada da Microsoft
description: Este artigo lista as tecnologias e os aplicativos usados na Área de Trabalho Gerenciada da Microsoft.
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: cb368939e87ddbbfc8f5386c6fc5d6bff110a7ec
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840896"
---
# <a name="microsoft-managed-desktop-technologies"></a>Tecnologias de Área de Trabalho Gerenciada da Microsoft

Este artigo lista as tecnologias e os aplicativos usados na Área de Trabalho Gerenciada da Microsoft.

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

O licenciamento do Microsoft 365 Enterprise é necessário para todos os usuários da Área de Trabalho Gerenciada da Microsoft. Para obter mais informações sobre os requisitos de licenciamento para o serviço, consulte [Pré-requisitos para a Área de Trabalho Gerenciada da Microsoft.](../get-ready/prerequisites.md)

Este artigo resume os componentes incluídos nas licenças Enterprise necessárias, com uma descrição de como o serviço usa cada componente com dispositivos da Área de Trabalho Gerenciada da Microsoft. Funções e responsabilidades específicas para cada área são detalhadas em toda a documentação da Área de Trabalho Gerenciada da Microsoft. 

## <a name="office-365-e3-or-e5"></a>Office 365 E3 ou E5
 |
 --- | ---
Aplicativos do Microsoft 365 para empresas (64 bits) | Esses aplicativos do Office serão fornecidos com o dispositivo: Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for Business, OneNote.<br><br>As versões completas de 64 bits do Microsoft Project e do Microsoft Visio não estão incluídas. No entanto, como a instalação desses aplicativos depende da instalação do Microsoft 365 Apps para empresas, a Área de Trabalho Gerenciada da Microsoft criou implantações padrão do Microsoft Intune e grupos de segurança que você pode usar para implantar esses aplicativos para usuários licenciados. Para obter mais informações, consulte [Instalar o Microsoft Project ou o Microsoft Visio em dispositivos da Área de Trabalho Gerenciada da Microsoft.](../get-started/project-visio.md)
OneDrive |O Logor Único do Azure Active Directory está habilitado para os usuários quando eles fazem o primeiro login no OneDrive.<br><br>O Redirecionamento de Pasta Conhecida para pastas "Área de Trabalho", "Documento" e "Imagens" está incluído; habilitado e configurado pela Área de Trabalho Gerenciada da Microsoft.
Aplicativos da Loja |    O Microsoft Sway e o Power BI não são fornecidos com o dispositivo. Esses aplicativos estão disponíveis para download na Microsoft Store.
Aplicativos Win32 |    O Teams não é fornecido com o dispositivo, mas é empacotado e fornecido pela Microsoft para dispositivos da Área de Trabalho Gerenciada da Microsoft. O Cliente de Proteção de Informações do Azure não é fornecido com o dispositivo, mas você pode empacotá-lo para implantação.
Aplicativos Web |  O Yammer, o Office em um navegador, o Delve, o Flow, o StaffHub, o PowerApps e o Planner não são fornecidos com o dispositivo. Os usuários podem acessar a versão web desses aplicativos com um navegador.


## <a name="windows-10-enterprise-e5-or-e3-with-microsoft-defender-for-endpoint"></a>Windows 10 Enterprise E5 ou E3 com o Microsoft Defender para Ponto de Extremidade

 |
 --- | ---
Application Virtualization (App-V) |    Os clientes podem implantar pacotes do App-V usando o cliente de gerenciamento de aplicativos Win32 do Intune.
Microsoft Defender para Ponto de Extremidade |    A Área de Trabalho Gerenciada da Microsoft usa esse produto para monitorar a segurança do dispositivo. 

## <a name="enterprise-mobility--security-e5"></a>Enterprise Mobility + Security E5

 |
 --- | ---
Enterprise Mobility + Security E3<br>Azure Active Directory Premium P2 |    Você pode usar todos os recursos do Enterprise Mobility + Security E3 e do Azure Active Directory Premium P2 para gerenciar dispositivos MDM.
Microsoft Cloud App Security |  Você pode usar esse recurso opcional com a Área de Trabalho Gerenciada da Microsoft.
Proteção de Informações do Azure P2  | Você pode usar esse recurso opcional com a Área de Trabalho Gerenciada da Microsoft.
