---
title: Implantar aplicativos para dispositivos de área de trabalho gerenciada da Microsoft
description: Informações para adicionar e implantar aplicativos em dispositivos de área de trabalho gerenciada da Microsoft.
keywords: Área de trabalho gerenciada da Microsoft, Microsoft 365, serviço, documentação, aplicativos, aplicativos de linha de negócios, aplicativos LOB
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 5ccb240460958d5978f4fd19e08652123790784e
ms.sourcegitcommit: 2211f57c268754d242d6331c188143f818f5a9f4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2019
ms.locfileid: "31039590"
---
# <a name="deploy-apps-to-microsoft-managed-desktop-devices"></a>Implantar aplicativos em dispositivos de área de trabalho gerenciada da Microsoft
Parte da integração com a área de trabalho gerenciada da Microsoft inclui a adição e implantação de aplicativos aos dispositivos do usuário. Quando estiver usando o portal de área de trabalho gerenciada da Microsoft, você poderá adicionar e implantar seus aplicativos. 

O processo geral tem a seguinte aparência:
1. [Adicionar aplicativos ao Microsoft Managed desktop portal](#1) – pode ser aplicativos LOB (linha de negócios) existentes ou aplicativos da Microsoft Store para empresas que você sincronizou com o Intune. 
2. [Criar grupos do Azure Active Directory (AD) para a atribuição de aplicativos](#2) -você usará esses grupos para gerenciar a atribuição de aplicativos.
3. [Atribuir aplicativos aos usuários](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a>Etapa 1: adicionar aplicativos ao portal de área de trabalho gerenciada da Microsoft
Você pode adicionar [aplicativos baseados em Win32 ou Windows MSI](#lob-apps), ou [Microsoft Store para aplicativos de negócios](#msfb-apps) à área de trabalho gerenciada da Microsoft e implantá-los em dispositivos de área de trabalho gerenciada da Microsoft.

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a>Aplicativos baseados em Win32 ou Windows MSI para a área de trabalho gerenciada da Microsoft

Você pode adicionar seus aplicativos de linha de negócios (LOB) ao portal de área de trabalho gerenciada da Microsoft. Para obter informações sobre os requisitos para aplicativos instalados em dispositivos de área de trabalho gerenciada da Microsoft, consulte [requisitos de aplicativos de área de trabalho gerenciado da Microsoft](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements)

Neste procedimento, você selecionará o tipo de aplicativo que você deseja adicionar e, em seguida, configurar e carregar a origem do aplicativo. 

**Para adicionar seu aplicativo LOB ou aplicativo do Windows ao portal de área de trabalho gerenciada da Microsoft**

Você pode entrar no portal de área de trabalho gerenciada da Microsoft ou entrar no Intune e, em seguida, procurar pela área de trabalho gerenciada da Microsoft. Mostraremos a entrada no portal de área de trabalho gerenciada da Microsoft. 

1.  Entre no [portal de administração de área de trabalho gerenciaDa da Microsoft](http://aka.ms/mmdportal). 
2.  Em **inventário**, selecione **aplicativos**.
3.  Na carga de trabalho aplicativos, selecione **Adicionar**.
4.  Em **Adicionar aplicativo**, selecione **aplicativo de linha de negócios** ou **aplicativo Windows (Win32)-visualização**.
    - Se você selecionou o **aplicativo de linha de negócios**, consulte [Adicionar um aplicativo de linha de negócios do Windows ao Microsoft Intune](https://docs.microsoft.com/intune/lob-apps-windows) para obter instruções sobre como adicionar e configurar aplicativos de linha de negócios.
    - Se você selecionou **Windows app (Win32) – Preview**, conFira o [Win32 app Management](https://docs.microsoft.com/intune/apps-win32-app-management) para instruções sobre como adicionar e configurar aplicativos do Windows.

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a>Aplicativos da Microsoft Store para empresas
Se você ainda não se inscreveu na Microsoft Store para empresas, você pode se inscrever ao comprar aplicativos. Depois de ter seus aplicativos, você pode sincronizá-los com a área de trabalho gerenciada da Microsoft. 

**Comprar aplicativos da Microsoft Store para empresas**

1. Entre na [Microsoft Store para empresas](https://businessstore.microsoft.com) com sua conta de administrador do Microsoft Store para empresas.
2. Selecione **comprar para meu grupo**.
3. Use a pesquisa para encontrar o aplicativo desejado e selecione o aplicativo.
4. Nos detalhes do produto, selecione **obter o aplicativo**. A Microsoft Store adiciona o aplicativo aos **Serviços do & de produtos** para sua organização.

**Para forçar uma sincronização entre o Intune e a Microsoft Store para empresas**
1. Entrar no [portal do Azure](https://portal.azure.com/) como administrador do Intune ou administrador global para o locatário
2. Selecione **todos os serviços _GT_ Intune**. O Intune está na seção monitoramento + gerenciamento.
3. No painel do Intune, selecione **aplicativos cliente**e, em seguida, selecione **Microsoft Store para empresas**.
4. Selecione **habilitar** para sincronizar seus aplicativos da Microsoft Store para empresas com o Intune.
    - Se você ainda não tiver feito isso, Inscreva-se e associe sua conta da Microsoft Store para empresas com o Intune
    - Selecione o idioma no qual os aplicativos da Microsoft Store para empresas serão exibidos no seu console do Intune
    - Selecione **sincronizar** para sincronizar seus aplicativos da Microsoft Store para empresas com o Intune.
    - Verifique se a sincronização entre a Microsoft Store para empresas e o Intune está ativa (próxima etapa). 

**Para verificar se uma sincronização entre o Intune e a Microsoft Store para empresas está ativa**
1. Entre na [Microsoft Store para empresas](https://businessstore.microsoft.com) com sua conta de administrador do Microsoft Store para empresas.
2. Selecione **gerenciar**.
3. Selecione **configurações** e, em seguida, **distribuir**.
4. Em **ferramentas de gerenciamento**, verifique se o Intune está listado e se o status está **ativo**.  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a>Etapa 2: criar grupos do Azure AD

Crie três grupos do Azure AD para cada aplicativo. Esta tabela descreve os grupos que você precisará (disponível, obrigatório e desInstalação). 

Tipo de atribuição de aplicativo |   Uso de grupo   | Exemplo de nome do Azure AD
--- | --- | ---
Disponível |  O aplicativo estará disponível no site ou aplicativo do portal da empresa. | MMD – *nome do aplicativo* – disponível
Obrigatório |  O aplicativo é instalado em dispositivos nos grupos selecionados. | MMD – *nome do aplicativo* – obrigatório
Uninstall |  O aplicativo especifica é desinstalado dos dispositivos nos grupos selecionados. | MMD – *nome do aplicativo* – desinstalar

Adicione seus usuários a esses grupos para fazer com que o aplicativo disponibilize, instalar o aplicativo ou remover o aplicativo do dispositivo de área de trabalho gerenciado da Microsoft. 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a>Etapa 3: atribuir aplicativos aos seus usuários

**Para atribuir o aplicativo aos seus usuários**

1. Entre no [portal de administração de área de trabalho gerenciaDa da Microsoft](http://aka.ms/mmdportal).
2. No painel da área de trabalho gerenciada, selecione **aplicativos**.
3. Na carga de trabalho aplicativos, selecione o aplicativo para o qual você deseja atribuir usuários e selecione **atribuir usuários grupos**.
4. Para o aplicativo específico, selecione um tipo de atribuição (disponível, obrigatório, desInstalação) e atribua o grupo apropriado.
5. No painel atribuir aplicativos, selecione **OK**.

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