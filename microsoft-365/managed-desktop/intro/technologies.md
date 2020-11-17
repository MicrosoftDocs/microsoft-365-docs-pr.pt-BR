---
title: Tecnologias de Área de Trabalho Gerenciada da Microsoft
description: Este tópico lista as tecnologias e os aplicativos usados na área de trabalho gerenciada da Microsoft.
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 9ec6f73996b2626ef62d33435ed88fb08dfc1a16
ms.sourcegitcommit: 0402d3275632fceda9137b6abc3ce48c8020172a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "49126574"
---
# <a name="microsoft-managed-desktop-technologies"></a>Tecnologias de Área de Trabalho Gerenciada da Microsoft

Este tópico lista as tecnologias e os aplicativos usados na área de trabalho gerenciada da Microsoft.

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

O Microsoft 365 Enterprise Licensing é necessário para todos os usuários da área de trabalho gerenciada da Microsoft. Para obter mais informações sobre requisitos de licenciamento para o serviço, consulte [pré-requisitos para a área de trabalho gerenciada da Microsoft](../get-ready/prerequisites.md).

Este tópico resume os componentes incluídos nas licenças corporativas necessárias, com uma descrição de como o serviço usa cada componente com os dispositivos de área de trabalho gerenciada da Microsoft. Funções e responsabilidades específicas de cada área são detalhadas em toda a documentação da área de trabalho gerenciada da Microsoft. 

## <a name="office-365-e3-or-e5"></a>Office 365 E3 ou e5
 |
 --- | ---
Aplicativos da Microsoft 365 para empresas (64 bits) | Esses aplicativos do Office serão enviados com o dispositivo: Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for Business, OneNote.<br><br>As versões completas de 64 bits do Microsoft Project e do Microsoft Visio não estão incluídas. No entanto, como a instalação desses aplicativos depende da instalação dos aplicativos do Microsoft 365 para Enterprise, a área de trabalho gerenciada da Microsoft criou implantações e grupos de segurança padrão do Microsoft Intune que você pode usar para implantar esses aplicativos para usuários licenciados. Para obter mais informações, consulte [instalar o Microsoft Project ou o Microsoft Visio em dispositivos de área de trabalho gerenciada da Microsoft](../get-started/project-visio.md).
OneDrive |O logon único do Azure Active Directory está habilitado para usuários no primeiro logon no OneDrive.<br><br>O redirecionamento de pasta conhecida para as pastas "área de trabalho", "documento" e "imagens" está incluído; habilitado e configurado pela área de trabalho gerenciada da Microsoft.
Armazenar aplicativos |    O Microsoft Sway e o Power BI não são fornecidos com o dispositivo. Esses aplicativos estão disponíveis para download na Microsoft Store.
Aplicativos Win32 |    O Teams não é fornecido com o dispositivo, mas é empacotado e fornecido pela Microsoft para os dispositivos de área de trabalho gerenciada da Microsoft. O cliente de proteção de informações do Azure não é fornecido com o dispositivo, mas você pode ter esse pacote para implantação.
Aplicativos Web |  O Yammer, o Office em um navegador, o Delve, o fluxo, o StaffHub, o PowerApps e o Planner não são fornecidos com o dispositivo. Os usuários podem acessar a versão da Web desses aplicativos com um navegador.


## <a name="windows-10-enterprise-e5-or-e3-with-microsoft-defender-for-endpoint"></a>Windows 10 Enterprise E5 ou E3 com Microsoft defender para ponto de extremidade

 |
 --- | ---
Virtualização de aplicativos (App-V) |    Os clientes podem implantar pacotes do App-V usando o cliente de gerenciamento de aplicativos do Win32 do Intune.
Microsoft Defender para Ponto de Extremidade |    O Microsoft Managed desktop usa isso para monitorar a segurança de dispositivos. 

## <a name="enterprise-mobility--security-e5"></a>Enterprise Mobility + Security e5

 |
 --- | ---
Mobilidade corporativa + segurança E3<br>Azure Active Directory Premium P2 |    Você pode usar todos os recursos do Enterprise Mobility + Security E3 e o Azure Active Directory Premium P2 para gerenciar dispositivos MDM.
Segurança no aplicativo na nuvem da Microsoft |  Você pode usar esse recurso opcional com a área de trabalho gerenciada da Microsoft.
Proteção de informações do Azure P2  | Você pode usar esse recurso opcional com a área de trabalho gerenciada da Microsoft.
