---
title: Tecnologias de área de trabalho gerenciada da Microsoft
description: Este tópico lista as tecnologias e os aplicativos usados na área de trabalho gerenciada da Microsoft.
keywords: Área de trabalho gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.collection: M365-modern-desktop
ms.openlocfilehash: 843a8cd066bbaf87a8b2b7cc74d8817207e47153
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283463"
---
# <a name="microsoft-managed-desktop-technologies"></a>Tecnologias de área de trabalho gerenciada da Microsoft

Este tópico lista as tecnologias e os aplicativos usados na área de trabalho gerenciada da Microsoft.

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

O Microsoft 365 Enterprise Licensing é necessário para todos os usuários da área de trabalho gerenciada da Microsoft. Para obter mais informações sobre requisitos de licenciamento para o serviço, consulte [pré-requisitos para a área de trabalho gerenciada da Microsoft](../get-ready/prerequisites.md).

Estes são os componentes incluídos nas licenças corporativas necessárias e como o serviço usa cada componente com os dispositivos de área de trabalho gerenciada da Microsoft. As funções e responsabilidades específicas de cada área são detalhadas em todo o tópico da área de trabalho gerenciada da Microsoft. 

## <a name="office-365-e3"></a>Office 365 E3
 |
 --- | ---
Pacote standard do Office 365 (64 bits) * | O pacote de aplicativos do Office padrão será enviado com o dispositivo: Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for Business, OneNote.<br><br>Os 64 bits Click para executar (C2R) versões completas do Microsoft Project e Microsoft Visio não estão incluídos no pacote standard do Office 365.  No enTanto, como a instalação desses aplicativos depende da instalação padrão do pacote do Office, a área de trabalho gerenciada da Microsoft criou os grupos de segurança e implantações do Intune padrão que o cliente usará para implantar esses aplicativos em usuários finais licenciados.  
Armazenar aplicativos |    O Microsoft Sway, o Desktop Power BI não é fornecido com o dispositivo. Esses aplicativos estão disponíveis para download na Microsoft Store.
Aplicativos Win32 |    O Power BI pro, o cliente do Azure Information Protection e o Microsoft Planner não são fornecidos com o dispositivo e podem ser empacotados para implantação pelo cliente. 
Aplicativos Web |  Yammer, Office Online, Delve, Flow, StaffHub, PowerApps não são entregues com o dispositivo. Os usuários podem acessar a versão da Web desses aplicativos com um navegador.
Cloud PBX do Skype for Business Online | Este recurso está disponível por meio do Office 365. O Microsoft Managed desktop não configura nenhum aspecto desse serviço

## <a name="windows-10-enterprise-e5"></a>Windows 10 Enterprise e5

 |
 --- | ---
Credential Guard |  A Microsoft fornecerá orientações e gerenciará os aspectos de nuvem desse recurso.
Device Guard (controle de aplicativo do Windows Defender) | A área de trabalho gerenciada da Microsoft criará a política. <br><br>O cliente gerenciará as assinaturas.
Gerenciamento do AppLocker |  A Microsoft criará a política. <br><br>O cliente gerenciará as assinaturas.
Virtualização de aplicativos (App-V) |    A área de trabalho gerenciada da Microsoft não oferece suporte a esse tipo de implantação, pois ela não é suportada no Intune.
User Experience Virtualization (UE-V) | Isso não é usado com dispositivos gerenciados pelo Microsoft Managed desktop.
Experiência do usuário gerenciado  | Isso não é usado com dispositivos gerenciados pelo Microsoft Managed desktop. O MDM é usado como uma solução para o gerenciamento de dispositivos.
Proteção Avançada Contra Ameaças do Windows Defender |   Isso é usado pelo Microsoft Managed desktop para gerenciar políticas de segurança de dispositivos. 

## <a name="enterprise-mobility--security-e5"></a>Enterprise Mobility + Security e5

 |
 --- | ---
Mobilidade corporativa + segurança E3<br>Microsoft Azure Active Directory Premium P2 |    Todos os aspectos da Enterprise Mobility + Security E3 e do AADP podem ser usados para gerenciar dispositivos MDM.
Microsoft Cloud App Security |  Este é um recurso opcional que os clientes podem usar com o serviço de área de trabalho gerenciada da Microsoft.
Proteção de informações do Azure P2  |Este é um recurso opcional que os clientes podem usar com o serviço de área de trabalho gerenciada da Microsoft.
