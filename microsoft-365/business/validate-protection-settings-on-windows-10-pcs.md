---
title: Validar as configurações de proteção de aplicativo em computadores Windows 10
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Saiba como validar as configurações de proteção do Microsoft 365 Business app em dispositivos Windows 10.
ms.openlocfilehash: 4f1f0993dff0ef8d3f6858a3749e063c7b5579c7
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32279922"
---
# <a name="validate-app-protection-settings-on-windows-10-pcs"></a><span data-ttu-id="21c12-103">Validar as configurações de proteção de aplicativo em computadores Windows 10</span><span class="sxs-lookup"><span data-stu-id="21c12-103">Validate app protection settings on Windows 10 PCs</span></span>

## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-corporate-devices"></a><span data-ttu-id="21c12-104">Verifique se os usuários não podem copiar dados da empresa para arquivos pessoais em dispositivos corporativos</span><span class="sxs-lookup"><span data-stu-id="21c12-104">Verify that users cannot copy company data to personal files on corporate devices</span></span>

<span data-ttu-id="21c12-p101">Depois de [configurar políticas de proteção do aplicativo](protection-settings-for-windows-10-devices.md), pode levar algumas horas para que a política entre em vigor nos dispositivos dos usuários. Se você **ativou** a configuração **Impedir os usuários de copiar dados da empresa para arquivos pessoais e forçá-los a salvar arquivos de trabalho no OneDrive for Business** para dispositivos de propriedade da empresa, poderá verificar isso nos dispositivos dos usuários quando eles se conectarem e entrarem no Microsoft Azure AD.</span><span class="sxs-lookup"><span data-stu-id="21c12-p101">After you [set up app protection policies](protection-settings-for-windows-10-devices.md), it may take up to a few hours for the policy to take effect on users' devices. If you turned **On** the **Prevent users from copying company data to personal files and force them to save work files to OneDrive for Business** setting for company owned devices, you can check this on the user's device after they have connected to Azure AD and signed in.</span></span> 
  
 <span data-ttu-id="21c12-107">**Verificar configurações de conexão**</span><span class="sxs-lookup"><span data-stu-id="21c12-107">**Verify connection settings**</span></span>
  
1. <span data-ttu-id="21c12-p102">After you sign in with Microsoft 365 Business credentials and connect to Azure AD as described in [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md), go to **Windows Settings** \> **Accounts** \> **Access work or school**. Choose **Connected to \<tenant name\> Azure AD**, and then choose **Info**.</span><span class="sxs-lookup"><span data-stu-id="21c12-p102">After you sign in with Microsoft 365 Business credentials and connect to Azure AD as described in [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md), go to **Windows Settings** \> **Accounts** \> **Access work or school**. Choose **Connected to \<tenant name\> Azure AD**, and then choose **Info**.</span></span>
    
    ![Click or tap Info on the Connected to Azure AD dialog.](media/a36ede2b-d1a0-4d4e-8ea7-af39b4b63890.png)
  
2. <span data-ttu-id="21c12-111">Na página **Gerenciado por** \<nome do locatário\>, você pode ver as **Informações de conexão**, que incluem um **Endereço de Servidor de Gerenciamento**, como mostrado na figura a seguir.</span><span class="sxs-lookup"><span data-stu-id="21c12-111">On the **Managed by** \<tenant name\> page you can see the **Connection info** that includes a **Management Server Address** like the one shown in the following figure.</span></span> 
    
    ![Managed by page shows connection info of the device manager URL.](media/47515a8e-2d0c-4bea-99f0-6b2545b88a11.png)
  
 <span data-ttu-id="21c12-113">**Verifique se você não pode colar dados da empresa em um aplicativo não gerenciado**</span><span class="sxs-lookup"><span data-stu-id="21c12-113">**Verify that you cannot paste company data to a non-managed app**</span></span>
  
1. <span data-ttu-id="21c12-114">Abra o Outlook 2016 que foi instalado por Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="21c12-114">Open Outlook 2016 that was installed by Microsoft 365 Business.</span></span>
    
2. <span data-ttu-id="21c12-115">Abra um email e copie algum conteúdo dele.</span><span class="sxs-lookup"><span data-stu-id="21c12-115">Open an email and copy some content from it.</span></span>
    
    <span data-ttu-id="21c12-116">Abra o Bloco de Notas e tente colar conteúdo.</span><span class="sxs-lookup"><span data-stu-id="21c12-116">Open Notepad and attempt to paste the content in.</span></span>
    
    <span data-ttu-id="21c12-117">Você receberá um erro indicando que o aplicativo não pode acessar conteúdo.</span><span class="sxs-lookup"><span data-stu-id="21c12-117">You will receive an error that states App can't access content.</span></span>
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    <span data-ttu-id="21c12-119">No entanto, você pode colar o mesmo conteúdo no Word 2016.</span><span class="sxs-lookup"><span data-stu-id="21c12-119">You can, however, paste the same content into Word 2016.</span></span>
    
## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-personal-devices"></a><span data-ttu-id="21c12-120">Verifique se os usuários não podem copiar dados da empresa para arquivos pessoais em dispositivos pessoais</span><span class="sxs-lookup"><span data-stu-id="21c12-120">Verify that users cannot copy company data to personal files on personal devices</span></span>

 <span data-ttu-id="21c12-121">**Verificar configurações de conexão**</span><span class="sxs-lookup"><span data-stu-id="21c12-121">**Verify connection settings**</span></span>
  
1. <span data-ttu-id="21c12-122">Em seu dispositivo Windows 10 pessoal em que você está conectado como um usuário local, acesse **Configurações do Windows** e clique ou toque em **Contas** \> **Acessar trabalho ou escola**.</span><span class="sxs-lookup"><span data-stu-id="21c12-122">On your Windows 10 personal device where you are logged in as a local user, go to **Windows Settings** and click or tap **Accounts** \> **Access work or school**.</span></span>
    
2. <span data-ttu-id="21c12-123">Em **Acessar trabalho ou escola**, escolha **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="21c12-123">Under the **Access work or school**, choose **Connect**.</span></span>
    
3. <span data-ttu-id="21c12-124">Insira sua credencial do Microsoft 365 Business na **caixa de diálogo Configurar uma conta corporativa ou de estudante** \> **Entrar**.</span><span class="sxs-lookup"><span data-stu-id="21c12-124">Enter your Microsoft 365 Business credential into the **Set up a work or school account dialog** \> **Sign in**.</span></span>
    
4. <span data-ttu-id="21c12-125">Na página **Acessar trabalho ou escola**, escolha a **Conta corporativa ou de estudante** e escolha **Informações**.</span><span class="sxs-lookup"><span data-stu-id="21c12-125">On the **Access work or school** page, choose the **Work or school account**, and then choose **Info**.</span></span>
    
    ![Click or tap Info on the Work or school account dalog.](media/63bd8b32-cb32-4afa-8ce0-6070ac403abc.png)
  
5. <span data-ttu-id="21c12-127">Na página **Acessar trabalho ou escola**, você pode ver as **Informações de Conexão**, que incluem um **Endereço de Servidor de Gerenciamento** igual ao mostrado na figura a seguir e incluem as palavras  *wip*  e  *mam*  .</span><span class="sxs-lookup"><span data-stu-id="21c12-127">On the **Access work or school** page you can see the **Connection info** that includes a **Management Server Address** like the one shown in the following figure, and includes the words  *wip*  and  *mam*  within.</span></span> 
    
    ![Managed by page shows connection info URL that includes the words mam and wpi.](media/abd4eaf4-44fa-4538-a3e8-1e0d331dfe1e.png)
  
 <span data-ttu-id="21c12-129">**Verifique se você não pode colar dados da empresa em um aplicativo não gerenciado**</span><span class="sxs-lookup"><span data-stu-id="21c12-129">**Verify that you cannot paste company data to a non-managed app**</span></span>
  
1. <span data-ttu-id="21c12-130">Abra o Outlook 2016, adicione sua conta do Microsoft 365 Business, se necessário, e entre com suas credenciais do Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="21c12-130">Open Outlook 2016 and add your Microsoft 365 Business account if necessary and sign in with your Microsoft 365 Business credentials.</span></span>
    
2. <span data-ttu-id="21c12-131">Abra um email e copie algum conteúdo dele.</span><span class="sxs-lookup"><span data-stu-id="21c12-131">Open an email and copy some content from it.</span></span>
    
    <span data-ttu-id="21c12-132">Abra o Bloco de Notas e tente colar conteúdo.</span><span class="sxs-lookup"><span data-stu-id="21c12-132">Open Notepad and attempt to paste the content in.</span></span>
    
    <span data-ttu-id="21c12-133">Você receberá um erro indicando que o aplicativo não pode acessar conteúdo.</span><span class="sxs-lookup"><span data-stu-id="21c12-133">You will receive an error that states App can't access content.</span></span>
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    <span data-ttu-id="21c12-135">No entanto, você pode colar o mesmo conteúdo no Word 2016.</span><span class="sxs-lookup"><span data-stu-id="21c12-135">You can, however, paste the same content into Word 2016.</span></span>
    

