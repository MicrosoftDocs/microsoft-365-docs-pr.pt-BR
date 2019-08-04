---
title: Instalar o Microsoft Project ou o Microsoft Visio em dispositivos de área de trabalho gerenciada da Microsoft
description: Informações sobre como instalar o Microsoft Project ou o Microsoft Visio em dispositivos de área de trabalho gerenciada da Microsoft
keywords: Área de trabalho gerenciada da Microsoft, Microsoft 365, Microsoft Project, Microsoft Visio
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 203db332e1fcd7861f40c69b138ac8274544dceb
ms.sourcegitcommit: 6cabf0226de1c95bff6ddb1852dac5ecdb2d6b96
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/23/2019
ms.locfileid: "35830469"
---
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a>Instalar o Microsoft Project ou o Microsoft Visio em dispositivos de área de trabalho gerenciada da Microsoft

O Microsoft Project e o Microsoft Visio exigem que etapas específicas sejam instaladas em dispositivos de área de trabalho gerenciada da Microsoft. Este tópico documenta os pré-requisitos e o processo de instalação desses aplicativos.

## <a name="prerequisites"></a>Pré-requisitos

Os administradores devem verificar se eles atendem a estes pré-requisitos:
- **Quantidade de licenças** -a quantidade correta de licenças do Microsoft Project e do Microsoft Visio deve estar disponível para os usuários. Atualmente, a área de trabalho gerenciada da Microsoft dá suporte apenas a versões de 64 bits desses aplicativos. 
- **Nomes de licença** : os nomes de licença apropriados para esses aplicativos são:
    - **Microsoft Project** -Project online Professional ou Project Online Premium
    - **Microsoft Visio** -Visio online plano 2
- **Portal da empresa** -o portal da empresa deve estar disponível em seu locatário para que os usuários instalem esses aplicativos. Se o portal da empresa não estiver implantado em seu locatário, confira [portal da empresa](company-portal.md).

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a>Implantar o Project e o Visio para dispositivos de área de trabalho gerenciada da Microsoft
Depois de enviar sua solicitação de suporte, a área de trabalho gerenciada da Microsoft criará três grupos do Azure AD e três implantações de aplicativos por meio do Microsoft Intune para implantar os aplicativos em seu locatário.  

**Para implantar o Project e o Visio**
1. **Arquivo uma solicitação de suporte** Os administradores de ti precisam arquivar uma solicitação de suporte para disponibilizar esses aplicativos aos usuários. Para obter informações sobre como entrar em contato com a área de trabalho gerenciada da Microsoft, consulte [admin support for Microsoft Managed desktop](../working-with-managed-desktop/admin-support.md).
2. **Atribuir usuários a novos grupos do Azure ad** A área de trabalho gerenciada da Microsoft criará 3 grupos do Azure AD no locatário e 3 implantações de aplicativo correspondentes. Os administradores de ti precisam atribuir os usuários aos grupos apropriados.

>[!NOTE]
>Atribuir usuários a apenas um desses grupos do Azure AD. 

Nome do grupo do Azure AD | Quais usuários serão atribuídos?   
 --- | ---
Área de trabalho moderna – Office – instalação do Project | Usuários que precisam apenas de projeto
Local de trabalho moderno – Office-Visio-install | Usuários que precisam apenas do Visio
Local de trabalho moderno – Office-instalação do Visio | Usuários que precisam do Project e do Visio

Uma vez atribuídos a esses grupos, os aplicativos estarão disponíveis no portal da empresa. Pode levar alguns minutos para sincronizar, mas os usuários podem instalar os aplicativos do portal da empresa. 

## <a name="communicate-changes"></a>Comunicar alterações
É importante para os administradores de ti permitir que seus usuários saibam como instalar o Project e o Visio. Isso inclui: 
- Notificar os usuários quando esses aplicativos estiverem disponíveis para eles. 
- Instruções sobre como instalar esses aplicativos do portal da empresa.

>[!NOTE]
>Os usuários devem fechar todos os aplicativos do Office antes de instalar o Microsoft Project ou o Microsoft Visio no portal da empresa. 
