---
title: Tecnologias de área de trabalho gerenciada da Microsoft
description: Este tópico lista as tecnologias e os aplicativos usados na área de trabalho gerenciada da Microsoft.
keywords: Área de trabalho gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 9f3094b1a1272b0c200271b8d5703fe7173683a6
ms.sourcegitcommit: 6b5370cded5d8259c9ed561eed324227f74c410b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/03/2019
ms.locfileid: "36171731"
---
# <a name="microsoft-managed-desktop-technologies"></a>Tecnologias de área de trabalho gerenciada da Microsoft

Este tópico lista as tecnologias e os aplicativos usados na área de trabalho gerenciada da Microsoft.

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

O Microsoft 365 Enterprise Licensing é necessário para todos os usuários da área de trabalho gerenciada da Microsoft. Para obter mais informações sobre requisitos de licenciamento para o serviço, consulte [pré-requisitos para a área de trabalho gerenciada da Microsoft](../get-ready/prerequisites.md).

Este tópico resume os componentes incluídos nas licenças corporativas necessárias, com uma descrição de como o serviço usa cada componente com os dispositivos de área de trabalho gerenciada da Microsoft. Funções e responsabilidades específicas de cada área são detalhadas em toda a documentação da área de trabalho gerenciada da Microsoft. 

## <a name="office-365-e3"></a>Office 365 E3
 |
 --- | ---
Pacote standard do Office 365 (64 bits) | O pacote de aplicativos do Office padrão será enviado com o dispositivo: Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for Business, OneNote.<br><br>Os C2R (clique para executar) 64 as versões completas do Microsoft Project e do Microsoft Visio não estão incluídas no Office 365. No entanto, como a instalação desses aplicativos depende da instalação padrão do pacote do Office, a área de trabalho gerenciada da Microsoft criou implantações e grupos de segurança padrão do Microsoft Intune que você pode usar para implantar esses aplicativos em usuários finais licenciados. Para obter mais informações, consulte [instalar o Microsoft Project ou o Microsoft Visio em dispositivos de área de trabalho gerenciada da Microsoft](../get-started/project-visio.md)  
Armazenar aplicativos |    O Microsoft Sway e o Power BI não são fornecidos com o dispositivo. Esses aplicativos estão disponíveis para download na Microsoft Store.
Aplicativos Win32 |    O Teams não é fornecido com o dispositivo, mas é empacotado e fornecido pela Microsoft para os dispositivos de área de trabalho gerenciada da Microsoft. O cliente de proteção de informações do Azure não é fornecido com o dispositivo, mas você pode ter esse pacote para implantação. 
Aplicativos Web |  O Yammer, o Office em um navegador, o Delve, o fluxo, o StaffHub, o PowerApps e o Planner não são fornecidos com o dispositivo. Os usuários podem acessar a versão da Web desses aplicativos com um navegador.


## <a name="windows-10-enterprise-e5"></a>Windows 10 Enterprise e5

 |
 --- | ---
Virtualização de aplicativos (App-V) |    A área de trabalho gerenciada da Microsoft não oferece suporte a esse tipo de implantação, já que ele não é suportado pelo Microsoft Intune.
Proteção avançada contra ameaças do Microsoft defender |  O Microsoft Managed desktop usa isso para monitorar a segurança de dispositivos. 

## <a name="enterprise-mobility--security-e5"></a>Enterprise Mobility + Security e5

 |
 --- | ---
Mobilidade corporativa + segurança E3<br>Microsoft Azure Active Directory Premium P2 |    Você pode usar todos os recursos do Enterprise Mobility + Security E3 e o Azure Active Directory Premium P2 para gerenciar dispositivos MDM.
Microsoft Cloud App Security |  Você pode usar esse recurso opcional com a área de trabalho gerenciada da Microsoft.
Proteção de informações do Azure P2  | Você pode usar esse recurso opcional com a área de trabalho gerenciada da Microsoft.
