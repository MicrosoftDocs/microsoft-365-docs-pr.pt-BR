---
title: Validar as configurações de proteção de aplicativo em computadores Windows 10
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
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
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Valide as configurações de proteção de aplicativo do Microsoft 365 Business Premium em dispositivos Windows 10 e verifique se os usuários não podem copiar dados da empresa para arquivos pessoais ou aplicativos não gerenciados.
ms.openlocfilehash: 589d2fc25cc1425a775523595881660cc03e152e
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44403381"
---
# <a name="validate-app-protection-settings-on-windows-10-pcs"></a><span data-ttu-id="b0e5d-103">Validar as configurações de proteção de aplicativo em computadores Windows 10</span><span class="sxs-lookup"><span data-stu-id="b0e5d-103">Validate app protection settings on Windows 10 PCs</span></span>

## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-corporate-devices"></a><span data-ttu-id="b0e5d-104">Verifique se os usuários não podem copiar dados da empresa para arquivos pessoais em dispositivos corporativos</span><span class="sxs-lookup"><span data-stu-id="b0e5d-104">Verify that users cannot copy company data to personal files on corporate devices</span></span>

<span data-ttu-id="b0e5d-105">Depois de [configurar políticas de proteção do aplicativo](protection-settings-for-windows-10-devices.md), pode levar algumas horas para que a política entre em vigor nos dispositivos dos usuários.</span><span class="sxs-lookup"><span data-stu-id="b0e5d-105">After you [set up app protection policies](protection-settings-for-windows-10-devices.md), it may take up to a few hours for the policy to take effect on users' devices.</span></span> <span data-ttu-id="b0e5d-106">Se você  tiver a opção Impedir que os usuários copiem dados da empresa para arquivos pessoais e forçar-os a salvar arquivos de trabalho na configuração do **OneDrive for Business** para dispositivos de propriedade da empresa, você poderá verificar isso no dispositivo do usuário depois que eles se conectarem ao Azure AD e se conectarem.</span><span class="sxs-lookup"><span data-stu-id="b0e5d-106">If you turned **On** the **Prevent users from copying company data to personal files and force them to save work files to OneDrive for Business** setting for company owned devices, you can check this on the user's device after they've connected to Azure AD and signed in.</span></span> 
  
 <span data-ttu-id="b0e5d-107">**Verificar configurações de conexão**</span><span class="sxs-lookup"><span data-stu-id="b0e5d-107">**Verify connection settings**</span></span>
  
1. <span data-ttu-id="b0e5d-108">Depois de entrar com as credenciais do Microsoft 365 Business Premium e conectar-se ao Azure AD conforme descrito em Configurar dispositivos Windows para usuários do [Microsoft 365 Business Premium,](set-up-windows-devices.md)vá para o Windows **Settings** Accounts Access no trabalho ou \>  \> **na escola.**</span><span class="sxs-lookup"><span data-stu-id="b0e5d-108">After you sign in with Microsoft 365 Business Premium credentials and connect to Azure AD as described in [Set up Windows devices for Microsoft 365 Business Premium users](set-up-windows-devices.md), go to **Windows Settings** \> **Accounts** \> **Access work or school**.</span></span> <span data-ttu-id="b0e5d-109">Escolha **Conectado ao \<tenant name\> Azure AD** e, em seguida, escolha **Informações.**</span><span class="sxs-lookup"><span data-stu-id="b0e5d-109">Choose **Connected to \<tenant name\> Azure AD**, and then choose **Info**.</span></span>
    
    ![Click or tap Info on the Connected to Azure AD dialog.](../media/a36ede2b-d1a0-4d4e-8ea7-af39b4b63890.png)
  
2. <span data-ttu-id="b0e5d-111">Na página **Gerenciado por,** você pode ver as informações de conexão que incluem um endereço de servidor de gerenciamento como o \<tenant name\> mostrado na figura a  seguir. </span><span class="sxs-lookup"><span data-stu-id="b0e5d-111">On the **Managed by** \<tenant name\> page, you can see the **Connection info** that includes a **Management Server Address** like the one shown in the following figure.</span></span> 
    
    ![Managed by page shows connection info of the device manager URL.](../media/47515a8e-2d0c-4bea-99f0-6b2545b88a11.png)
  
 <span data-ttu-id="b0e5d-113">**Verifique se você não pode colar dados da empresa em um aplicativo não gerenciado**</span><span class="sxs-lookup"><span data-stu-id="b0e5d-113">**Verify that you cannot paste company data in a non-managed app**</span></span>
  
1. <span data-ttu-id="b0e5d-114">Abra o Outlook 2016 que foi instalado pelo Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="b0e5d-114">Open Outlook 2016 that was installed by Microsoft 365 Business Premium.</span></span>
    
2. <span data-ttu-id="b0e5d-115">Abra um email e copie algum conteúdo dele.</span><span class="sxs-lookup"><span data-stu-id="b0e5d-115">Open an email and copy some content from it.</span></span>
    
    <span data-ttu-id="b0e5d-116">Abra o Bloco de Notas e tente colar conteúdo.</span><span class="sxs-lookup"><span data-stu-id="b0e5d-116">Open Notepad and attempt to paste the content in.</span></span>
    
    <span data-ttu-id="b0e5d-117">Você receberá um erro informando que o aplicativo não pode acessar o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="b0e5d-117">You'll receive an error that states the app can't access content.</span></span>
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](../media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    <span data-ttu-id="b0e5d-119">No entanto, você pode colar o mesmo conteúdo no Word 2016.</span><span class="sxs-lookup"><span data-stu-id="b0e5d-119">You can, however, paste the same content into Word 2016.</span></span>
    
## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-personal-devices"></a><span data-ttu-id="b0e5d-120">Verifique se os usuários não podem copiar dados da empresa para arquivos pessoais em dispositivos pessoais</span><span class="sxs-lookup"><span data-stu-id="b0e5d-120">Verify that users cannot copy company data to personal files on personal devices</span></span>

 <span data-ttu-id="b0e5d-121">**Verificar configurações de conexão**</span><span class="sxs-lookup"><span data-stu-id="b0e5d-121">**Verify connection settings**</span></span>
  
1. <span data-ttu-id="b0e5d-122">Em seu dispositivo pessoal do Windows 10 em que você está conectado como um usuário local, vá para Configurações do **Windows** e clique ou toque em **Contas** do Access no trabalho \> **ou na escola.**</span><span class="sxs-lookup"><span data-stu-id="b0e5d-122">On your Windows 10 personal device where you're logged in as a local user, go to **Windows Settings**, and click or tap **Accounts** \> **Access work or school**.</span></span>
    
2. <span data-ttu-id="b0e5d-123">Em **Acessar trabalho ou escola**, escolha **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="b0e5d-123">Under the **Access work or school**, choose **Connect**.</span></span>
    
3. <span data-ttu-id="b0e5d-124">Insira sua credencial do Microsoft 365 Business Premium na caixa de diálogo Configurar uma conta comercial ou **de** \> **estudante.**</span><span class="sxs-lookup"><span data-stu-id="b0e5d-124">Enter your Microsoft 365 Business Premium credential into the **Set up a work or school account dialog** \> **Sign in**.</span></span>
    
4. <span data-ttu-id="b0e5d-125">Na página **Acessar trabalho ou escola**, escolha a **Conta corporativa ou de estudante** e escolha **Informações**.</span><span class="sxs-lookup"><span data-stu-id="b0e5d-125">On the **Access work or school** page, choose the **Work or school account**, and then choose **Info**.</span></span>
    
    ![Clique ou toque em Informações na caixa de diálogo Conta de trabalho ou de estudante.](../media/63bd8b32-cb32-4afa-8ce0-6070ac403abc.png)
  
5. <span data-ttu-id="b0e5d-127">Na página de trabalho ou escola  do **Access,** você pode ver as informações de conexão que incluem um endereço de servidor de gerenciamento como o mostrado na figura **a** seguir e inclui as palavras *wip* e *mam* dentro.</span><span class="sxs-lookup"><span data-stu-id="b0e5d-127">On the **Access work or school** page, you can see the **Connection info** that includes a **Management Server Address** like the one shown in the following figure, and includes the words  *wip*  and  *mam*  within.</span></span> 
    
    ![Managed by page shows connection info URL that includes the words mam and wpi.](../media/abd4eaf4-44fa-4538-a3e8-1e0d331dfe1e.png)
  
 <span data-ttu-id="b0e5d-129">**Verifique se você não pode colar dados da empresa em um aplicativo não gerenciado**</span><span class="sxs-lookup"><span data-stu-id="b0e5d-129">**Verify that you cannot paste company data in a non-managed app**</span></span>
  
1. <span data-ttu-id="b0e5d-130">Abra o Outlook 2016 e adicione sua conta do Microsoft 365 Business Premium, se necessário, e entre com suas credenciais do Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="b0e5d-130">Open Outlook 2016 and add your Microsoft 365 Business Premium account if necessary and sign in with your Microsoft 365 Business Premium credentials.</span></span>
    
2. <span data-ttu-id="b0e5d-131">Abra um email e copie algum conteúdo dele.</span><span class="sxs-lookup"><span data-stu-id="b0e5d-131">Open an email and copy some content from it.</span></span>
    
    <span data-ttu-id="b0e5d-132">Abra o Bloco de Notas e tente colar conteúdo.</span><span class="sxs-lookup"><span data-stu-id="b0e5d-132">Open Notepad and attempt to paste the content in.</span></span>
    
    <span data-ttu-id="b0e5d-133">Você receberá um erro informando que o aplicativo não pode acessar o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="b0e5d-133">You'll receive an error that states App can't access content.</span></span>
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](../media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    <span data-ttu-id="b0e5d-135">No entanto, você pode colar o mesmo conteúdo no Word 2016.</span><span class="sxs-lookup"><span data-stu-id="b0e5d-135">You can, however, paste the same content into Word 2016.</span></span>
    

