---
title: Tecnologias Microsoft Desktop gerenciados
description: Este tópico lista as tecnologias e os aplicativos usados no Microsoft Desktop gerenciados.
keywords: Serviço Microsoft Managed Desktop, 365 da Microsoft, documentação
ms.service: m365-md
author: jdeckerms
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: da0268c6b0eddbd44cf62de2a95b963a443c3278
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26864884"
---
# <a name="microsoft-managed-desktop-technologies"></a>Tecnologias Microsoft Desktop gerenciados

Este tópico lista as tecnologias e os aplicativos usados no Microsoft Desktop gerenciados.

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

Licença da Microsoft 365 E5 (ou equivalente) é necessário para o serviço de Microsoft Desktop gerenciados. A seguir são todos os componentes que estão incluídos nessa licença e como o Microsoft Desktop gerenciados usa cada componente com dispositivos Microsoft Desktop gerenciados.  Funções específicas e responsabilidades para cada área são detalhadas ao longo de tópicos do Microsoft Desktop gerenciados. 

Microsoft 365 E5 é composto por componentes de 3: E5 do Office 365, Windows 10 Enterprise e E5, Enterprise mobilidade + E5 de segurança.  

## <a name="office-365-e5"></a>O Office 365 E5
 |
 --- | ---
O Office 365 Standard Suite (64 bits) * | O conjunto do Office standard dos aplicativos será fornecido com o dispositivo: Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype para os negócios, OneNote.<br><br>Clique para executar de 64 bits (C2R) de versões completas do Microsoft Project e o Microsoft Visio não são incluídas no Office 365 Standard Suite.  No entanto, desde a instalação desses aplicativos são dependentes da instalação do pacote do Office standard, Microsoft Desktop gerenciados tiver criado implantações de Intune padrão e grupos de segurança que o cliente usará para implantar esses aplicativos para licenciado a usuários finais.  
Aplicativos do repositório |    Microsoft Sway, Teams da Microsoft, a área de trabalho do Power BI (não Pro) não são fornecidos com o dispositivo. Esses aplicativos estão disponíveis para download no Microsoft Store.
Aplicativos Win32 |    Power BI Pro, cliente de proteção de informações do Windows Azure e Microsoft Planner não são fornecidos com o dispositivo e podem ser empacotados para implantação pelo cliente. 
Aplicativos Web |  Yammer, Office Online, Delve, fluxo, StaffHub, PowerApps não são fornecidos com o dispositivo. Os usuários podem acessar o versão desses aplicativos com um navegador da web.
Skype para nuvem Online de negócios PBX | Este recurso está disponível por meio do Office 365 E5. Microsoft Desktop gerenciados não irá configurar qualquer aspecto desse serviço

## <a name="windows-10-enterprise-e5"></a>Windows 10 Enterprise E5

 |
 --- | ---
Protetor de credencial |  Microsoft Desktop gerenciados fornecerá orientações e gerenciar aspectos de nuvem desse recurso
Dispositivo Guard (controle de aplicativo do Windows Defender)   | Microsoft Desktop gerenciados criará a política. Cliente irá gerenciar assinaturas
Gerenciamento de AppLocker |  Microsoft Desktop gerenciados criará a política. Cliente irá gerenciar assinaturas
Application Virtualization (App-V) |    Microsoft Desktop gerenciados não oferece suporte a esse tipo de implantação, conforme ele não é suportado em Intune.
Virtualização de experiência do usuário (UE-V) | Isso não é usado com dispositivos Microsoft gerenciado Desktop gerenciados
Experiência do usuário gerenciada  | Isso não é usado com dispositivos Microsoft gerenciado Desktop gerenciados. MDM é usado como uma solução de gerenciamento de dispositivos
Proteção Avançada Contra Ameaças do Windows Defender |   Isso é usado pelo Microsoft Desktop gerenciados para gerenciar diretivas de segurança de dispositivo. 

## <a name="enterprise-mobility--security"></a>Enterprise Mobility + Security 

 |
 --- | ---
Mobilidade corporativos + E3 de segurança<br>Azure Active Directory Premium P2 |    Todos os aspectos da empresa mobilidade + E3 de segurança e AADP podem ser usados para gerenciar dispositivos MDM
Microsoft Cloud App Security |  Este é um recurso opcional que os clientes podem ser usados com o serviço Microsoft Desktop gerenciados.
P2 de proteção de informações do Azure  |Este é um recurso opcional que os clientes podem ser usados com o serviço Microsoft Desktop gerenciados.