---
title: Implantar aplicativos para dispositivos Microsoft Desktop gerenciados
description: Informações de adição e implantar aplicativos Microsoft Desktop gerenciados dispositivos.
keywords: Microsoft Desktop gerenciados, Microsoft 365, serviço, documentação, aplicativos, aplicativos de linha de negócios, aplicativos LOB
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 01/17/2019
ms.openlocfilehash: 65d45be5ddb21d8f2cac876a1c8f93b2bbddf7b8
ms.sourcegitcommit: 0fc00286d7dc8cafddf9d17a98a375503b9551e6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/18/2019
ms.locfileid: "29341594"
---
# <a name="deploy-apps-to-microsoft-managed-desktop-devices"></a>Implantar aplicativos em dispositivos Microsoft Desktop gerenciados
Parte da inclusão à área de trabalho gerenciada do Microsoft inclui adicionando e implantar aplicativos dispositivos do seu usuário. Depois que você estiver usando o portal do Microsoft Desktop gerenciados, você pode adicionar e implantar seus aplicativos. 

O processo geral tem esta aparência:
1. [Adicionar aplicativos ao portal do Microsoft Desktop gerenciados](#1) - isso pode ser existentes aplicativos da Microsoft Store for Business que você tiver sincronizados com Intune ou aplicativos de linha de negócios (LOB). 
2. [Grupos de criar Azure AD (Active Directory) para atribuição de app](#2) - você utilizará esses grupos para gerenciar a atribuição de aplicativo.
3. [Atribuir aplicativos para seus usuários](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a>Etapa 1: Adicionar aplicativos ao portal do Microsoft Desktop gerenciados
Você pode adicionar [Win32, aplicativos baseados no Windows MSI](#lob-apps)ou [Armazenamento da Microsoft para aplicativos de negócios](#msfb-apps) para o Microsoft Desktop gerenciados e, em seguida, implantá-los nos dispositivos de área de trabalho gerenciada do Microsoft.

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a>Win32 ou Windows aplicativos baseados em MSI à Microsoft gerenciados da área de trabalho

Você pode adicionar seus aplicativos de linha de negócios (LOB) ao portal do Microsoft Desktop gerenciados. Para obter informações sobre requisitos de aplicativos, instalados nos dispositivos de área de trabalho gerenciada do Microsoft, consulte [requisitos de aplicativo do Microsoft Desktop gerenciados](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements).

Neste procedimento, você selecionará o tipo de aplicativo que deseja adicionar e, em seguida, configurar e carregar a fonte do aplicativo. 

**Para adicionar seu aplicativo LOB ou aplicativo do Windows ao portal do Microsoft Desktop gerenciados**

Você pode entre no portal do Microsoft Desktop gerenciados, ou entrar em Intune e procure Microsoft Desktop gerenciados. Mostraremos entrando no portal do Microsoft Desktop gerenciados. 

1.  Faça logon no [portal de administração de área de trabalho gerenciada da Microsoft](http://aka.ms/mmdportal). 
2.  Em **inventário**, selecione **aplicativos**.
3.  Em que a carga de trabalho de aplicativos, selecione **Adicionar**.
4.  No **aplicativo de adicionar**, selecione **o aplicativo de linha de negócios** ou **a visualização do aplicativo do Windows (Win32)**.
    - Se você selecionou um **aplicativo de linha de negócios**, consulte [Adicionar um aplicativo de linha de negócios do Windows para Microsoft Intune](https://docs.microsoft.com/intune/lob-apps-windows) para obter instruções sobre como adicionar e configurar aplicativos de linha de negócios.
    - Se você selecionou **a visualização do aplicativo do Windows (Win32 -)**, consulte o [Win32 app management](https://docs.microsoft.com/intune/apps-win32-app-management) para obter instruções sobre como adicionar e configurar aplicativos do Windows.

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a>Armazenamento da Microsoft para aplicativos de negócios
Se você ainda não se inscreveu com Microsoft Store for Business, você pode inscrever-se quando você faz compras para aplicativos. Depois de ter seus aplicativos, eles podem ser sincronizados com Microsoft Desktop gerenciados. 

**Comprar aplicativos a partir do Microsoft Store for Business**

1. Entrar no [Microsoft Store for Business](https://businessstore.microsoft.com) com seu Store Microsoft para a conta de administrador de negócios.
2. Selecione a **loja para o meu grupo**.
3. Usar a pesquisa para localizar a que o aplicativo desejado e selecione o aplicativo.
4. Os detalhes do produto, selecione **obter o aplicativo**. Microsoft Store adiciona o aplicativo para **produtos e serviços &** para sua organização.

**Para forçar uma sincronização entre Intune e Microsoft Store for Business**
1. Entre no [Portal do Windows Azure](https://portal.azure.com/) como Intune Admin ou Administrador Global para seu locatário
2. Selecione **todos os serviços gt _ Intune**. Intune estiver no monitoramento + gerenciamento seção.
3. No painel Intune, selecione **Os aplicativos cliente**e selecione **Microsoft Store for Business**.
4. Selecione **Habilitar** para sincronizar seu Store Microsoft para aplicativos de negócios com Intune.
    - Se você ainda não estiver, sign up e associe o Microsoft armazenar para a conta de negócios com Intune
    - Selecione o idioma no qual os aplicativos a partir do Microsoft Store for Business serão exibidos no seu console Intune
    - Selecione **sincronização** para sincronizar seu Store Microsoft para aplicativos de negócios com Intune.
    - Verifique se a sincronização entre o Microsoft Store for Business e Intune é ativa (próxima etapa). 

**Para verificar se uma sincronização entre Intune e Microsoft Store for Business está ativa**
1. Entrar no [Microsoft Store for Business](https://businessstore.microsoft.com) com seu Store Microsoft para a conta de administrador de negócios.
2. Selecione **Gerenciar**.
3. Selecione **configurações** e selecione **Distribute**.
4. Em **Ferramentas de gerenciamento**, verifique se que Intune está listado e se o status está **ativa**.  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a>Etapa 2: Criar grupos do Azure AD.

Crie três grupos do Azure AD para cada aplicativo. Esta tabela descreve os grupos que você precisará (disponível, necessário e desinstalação). 

Tipo de atribuição de aplicativo |   Uso de grupo   | Nome do exemplo Azure AD.
--- | --- | ---
Disponível |  O aplicativo estará disponível no aplicativo do Portal da empresa ou site. | MMD – *nome do aplicativo* – disponível
Obrigatório |  O aplicativo está instalado nos dispositivos nos grupos selecionados. | MMD – *nome do aplicativo* – necessário
Desinstalar |  TThe app é desinstalado de dispositivos nos grupos selecionados. | MMD – *nome do aplicativo* – desinstalação

Adicione os usuários a esses grupos para tornar o app vem incluído, instale o aplicativo ou remover o aplicativo do seu dispositivo Microsoft Desktop gerenciados. 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a>Etapa 3: Atribuir aplicativos para seus usuários

**Para atribuir o aplicativo para seus usuários**

1. Faça logon no [portal de administração de área de trabalho gerenciada da Microsoft](http://aka.ms/mmdportal).
2. No painel de área de trabalho gerenciado, selecione **aplicativos**.
3. Em que a carga de trabalho de aplicativos, selecione o aplicativo que você deseja atribuir aos usuários e selecione **atribuir grupos de usuários**.
4. Para o aplicativo específico, selecione um tipo de atribuição (disponível, necessário, desinstalar) e atribuir o grupo apropriado.
5. No painel de atribuir aplicativos, selecione **Okey**.

<!--# Preparing apps for Microsoft Managed Desktop

This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.

Applications: supported/onboard/deployment
 
Microsoft and Microsoft Managed Desktop customers have equally critical, yet different responsibilities around applications used with Microsoft Managed Desktop.

## Microsoft responsibilities
**Office 365 apps**
Microsoft will provide full service for the deployment, update, and support of specific Office 365 apps. All users will receive the base set of Office 365 click to run, 64 bit version of applications included in the device’s image so that a user can quickly become productive. The Project and Visio applications in of the Office 365 suite are licensed separately.  Microsoft Managed Desktop will provide deployment groups allowing the IT Administrator to manage licenses and deploy these applications appropriately for their organization. Microsoft will support end users of these applications through the Microsoft Managed Desktop Support channels.

**Line-of-business apps**
Microsoft provides tooling for IT Administrators to manage and deploy their line-of-business (LOB) applications to end users as a part of the Intune product. Microsoft will support application deployment issues as detailed in [Line-of-business applications](#line-of-business-applications) 

**Deploy with Intune**
Intune will be linked to the **Microsoft Store for Business** during Microsoft Managed Desktop onboarding allowing procured apps to be deployed through Intune. Microsoft will also deploy the web-based version of the Company Portal to end users so that IT Administrators can provide a self-service experience for end users.

**App management**
Microsoft may identify restricted applications which are not suitable for the modern workplace because of their system impact. When such an application is identified Microsoft will notify the customer and that application will need to be removed from the tenant. 

For more information on restricted app behaviors and app requirements, see [Microsoft Managed Desktop app requirements](../service-description/mmd-app-requirements.md)

## Customer responsibilities
The Office 365 Suite is core to Microsoft’s productivity offerings and is included in the Microsoft 365 License for all Microsoft Managed Desktop users. While Microsoft deploys, updates, and supports Office Applications to Microsoft Managed Desktop Devices there are still some areas for which the customer is responsible.
- **Assign licenses** - Customers are responsible for assigning the appropriate licenses to end users for Office 365. 
- **Add users to security groups** - For customers with users who need Project or Visio, the IT administrator must add those users to the appropriate deployment groups. IT administrators are also responsible for managing end of life for those users. 
- **Deploy Office 365 Add Ons** - Customers are responsible for deploying any plugins to the Office 365 suite which are deemed necessary. 

Since line-of-business (LOB) apps are unique for each customer, customers are responsible for managing all applications within their organization not deployed by Microsoft. This includes:
- Deciding which apps are needed and who needs them
- Assigning apps to those users
- Create and maintain Azure Active Directory (AD) groups for managing app assignments 

The customer must upload LOB apps to Intune. They are then responsible for deploying, updating, and decommissioning those applications over their respective lifecycles, as well as managing support for these apps for their users.

## Office applications
As part of the Microsoft 365 E5 license, Office 365 Standard Suite (64 Bit) is deployed by Microsoft. 

For details, see [Microsoft Managed Desktop technologies](../intro/technologies.md) <!--- and the other applications licensed under Office 365 E5 may be deployed by the customer using Intune’s deployment tools.

## Line-of-business applications
This table summarizes responsibilities across the different phases for line-of-business (LOB) applications. 

Application work items |    Customer    | Microsoft
--- | --- | ---
**Onboarding apps** |  |
Identify applications needed for targeted user groups   | ![yes](images/checkmark.png)  |
Create and manage Azure AD groups for app deployment | ![yes](images/checkmark.png) |   
**App Packaging** |  |
Package apps to meet Intune deployment standards |  ![yes](images/checkmark.png) |  
Upload apps to Intune | ![yes](images/checkmark.png)     |
Test apps in Microsoft Managed Desktop environment |    ![yes](images/checkmark.png) |  
Test apps with end users    | ![yes](images/checkmark.png) |    
**Deployment** | |
Manage and assign users to applications  | ![yes](images/checkmark.png)  |
Intune deployment tools delivers application to remote clients| |   ![yes](images/checkmark.png)
Identify and deploy application updates through Intune | ![yes](images/checkmark.png)    |
Unistall and remove applications when they have been retired    | ![yes](images/checkmark.png) |    
**Management** | |
Procure and assign licenses |   ![yes](images/checkmark.png)     |
Provide end-user support for line-of-business apps  | ![yes](images/checkmark.png) |
Manage app settings remotely    | ![yes](images/checkmark.png) |

For information on LOB application requirements, see [Microsoft Managed Desktop application requirements](../service-description/mmd-app-requirements.md)


## Intune application deployment
Application management can be handled through the Microsoft Managed Desktop Admin portal, or through the Intune portal. Intune’s app management portal shows applications deployed for Windows, Android, and iOS. Microsoft Managed Desktop Admin portal limits the view to Windows 10 applications. Both are available through the Azure Portal. 
* [Intune app management basics](https://docs.microsoft.com/intune/app-management)
* [Add apps to Intune](https://docs.microsoft.com/intune/app-management)
   * [Add a line-of-business App](https://docs.microsoft.com/intune/lob-apps-windows)
   * [Add Win32 apps to Intune](https://docs.microsoft.com/intune/apps-win32-app-management)
   * [Add web applications](https://docs.microsoft.com/intune/web-app)
* [Deploy apps](https://docs.microsoft.com/intune/apps-deploy)
   * [Deploy apps to Windows 10](https://docs.microsoft.com/intune/apps-windows-10-app-deploy)
* Company Portal
   * [Deploy the Company Portal](https://docs.microsoft.com/intune/store-apps-company-portal-app)
   * [Configure the Company Portal app](https://docs.microsoft.com/intune/company-portal-app)-->