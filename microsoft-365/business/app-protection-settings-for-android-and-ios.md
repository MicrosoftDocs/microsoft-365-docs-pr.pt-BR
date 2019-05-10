---
title: Defina configurações de proteção de aplicativo para dispositivos Android ou iOS
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 6f2b80b4-81c3-4714-a7bc-ae69313e8a33
description: Saiba como criar, editar ou excluir uma política de gerenciamento de aplicativos e proteger arquivos de trabalho em dispositivos Android ou iOS.
ms.openlocfilehash: 04479360bf13a8ff685a91ed95440c08f8cf80b4
ms.sourcegitcommit: db1dfb2df2c2f7beced3b57bc772d106c189e88a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2019
ms.locfileid: "33660489"
---
# <a name="set-app-protection-settings-for-android-or-ios-devices"></a><span data-ttu-id="1d7df-103">Defina configurações de proteção de aplicativo para dispositivos Android ou iOS</span><span class="sxs-lookup"><span data-stu-id="1d7df-103">Set app protection settings for Android or iOS devices</span></span>

![Faixa que aponta para https://aka.ms/aboutM365preview.](media/m365admincenterchanging.png)

## <a name="create-an-app-management-policy"></a><span data-ttu-id="1d7df-105">Criar uma política de gerenciamento de aplicativos</span><span class="sxs-lookup"><span data-stu-id="1d7df-105">Create an app management policy</span></span>

1. <span data-ttu-id="1d7df-106">Vá para o centro de administração <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>em.</span><span class="sxs-lookup"><span data-stu-id="1d7df-106">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span> 
    
2. <span data-ttu-id="1d7df-107">Na navegação à esquerda, escolha \*\*\*\* \> **políticas** \> de dispositivos **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="1d7df-107">In the left nav, choose **Devices** \> **Policies** \> **Add**.</span></span>
  
3. <span data-ttu-id="1d7df-108">No painel **Adicionar política**, insira um nome exclusivo para essa política.</span><span class="sxs-lookup"><span data-stu-id="1d7df-108">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
    
4. <span data-ttu-id="1d7df-109">Em **Tipo de política**, escolha **Gerenciamento de Aplicativos para Android** ou **Gerenciamento de Aplicativos para iOS**, dependendo de qual conjunto de políticas que você deseja criar.</span><span class="sxs-lookup"><span data-stu-id="1d7df-109">Under **Policy type**, choose **Application Management for Android** or **Application Management for iOS** depending on which set of policies you want to create.</span></span> 
    
5. <span data-ttu-id="1d7df-110">Expanda **Proteger arquivos de trabalho quando dispositivos forem perdidos ou roubados** e **Gerenciar como os usuários acessam arquivos do Office em dispositivos móveis** \> defina as configurações como desejar.</span><span class="sxs-lookup"><span data-stu-id="1d7df-110">Expand **Protect work files when devices are lost or stolen** and **Manage how users access Office files on mobile devices** \> configure the settings how you would like.</span></span> <span data-ttu-id="1d7df-111">A opção **Gerenciar como os usuários acessam arquivos do Office em dispositivos móveis** é **Desativada** por padrão, mas recomenda-se que ela seja **Ativada** e que os valores padrão sejam aceitos.</span><span class="sxs-lookup"><span data-stu-id="1d7df-111">The **Manage how users access Office files on mobile devices** is **Off** by default, but it is recommended that you turn it **On** and accept the default values.</span></span> <span data-ttu-id="1d7df-112">Confira [configurações disponíveis](#available-settings) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="1d7df-112">See [Available settings](#available-settings)  for more information.</span></span> 
    
    <span data-ttu-id="1d7df-113">Você sempre poderá usar o link **Redefinir as configurações padrão** para voltar para a configuração padrão.</span><span class="sxs-lookup"><span data-stu-id="1d7df-113">You can always use the **Reset default settings** link to return to the default setting.</span></span> 
    
    ![Screenshot of Create a policy with Application management for Android selected](media/eabbe06d-ac0a-4f3a-8630-68c808b1e662.png)
  
6. <span data-ttu-id="1d7df-p102">Em seguida, decida **Quem receberá estas configurações?** Se não quiser usar o grupo de segurança padrão **Todos os Usuários**, escolha **Alterar**, escolha o grupo de segurança que deverá receber essas configurações \> **Selecionar**.</span><span class="sxs-lookup"><span data-stu-id="1d7df-p102">Next decide **Who will get these settings?** If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.</span></span>
    
7. <span data-ttu-id="1d7df-117">Por fim, escolha **Concluído** para salvar a política e atribui-la a dispositivos.</span><span class="sxs-lookup"><span data-stu-id="1d7df-117">Finally, choose **Done** to save the policy, and assign it to devices.</span></span> 
    
## <a name="edit-an-app-management-policy"></a><span data-ttu-id="1d7df-118">Editar uma política de gerenciamento de aplicativos</span><span class="sxs-lookup"><span data-stu-id="1d7df-118">Edit an app management policy</span></span>

1. <span data-ttu-id="1d7df-119">No cartão **políticas** , escolha **Editar política**.</span><span class="sxs-lookup"><span data-stu-id="1d7df-119">On the **Policies** card, choose **Edit policy**.</span></span>
    
2. <span data-ttu-id="1d7df-120">No painel **Editar política**, escolha a política que você deseja alterar</span><span class="sxs-lookup"><span data-stu-id="1d7df-120">On the **Edit policy** pane, choose the policy you want to change</span></span> 
    
3. <span data-ttu-id="1d7df-p103">Escolha **Editar** ao lado de cada configuração para alterar os valores na política. Quando você altera um valor, ele é salvo automaticamente na política</span><span class="sxs-lookup"><span data-stu-id="1d7df-p103">Choose **Edit** next to each setting to change the values in the policy. When you change a value, it is automatically saved into the policy</span></span> 
    
4. <span data-ttu-id="1d7df-123">Quando terminar, feche o painel **Editar política**.</span><span class="sxs-lookup"><span data-stu-id="1d7df-123">When you are finished, close the **Edit policy** pane.</span></span> 
    
## <a name="delete-an-app-management-policy"></a><span data-ttu-id="1d7df-124">Excluir uma política de gerenciamento de aplicativos</span><span class="sxs-lookup"><span data-stu-id="1d7df-124">Delete an app management policy</span></span>

1. <span data-ttu-id="1d7df-125">Na página **políticas** , escolha uma política e, em \*\*\*\* seguida, exclua.</span><span class="sxs-lookup"><span data-stu-id="1d7df-125">On the **Policies** page, choose a policy and then **Delete**.</span></span>
    
2. <span data-ttu-id="1d7df-126">No painel **excluir política** , escolha **confirmar** para excluir a política ou as políticas escolhidas.</span><span class="sxs-lookup"><span data-stu-id="1d7df-126">On the **Delete policy** pane choose **Confirm** to delete the policy or policies you chose.</span></span> 
    
## <a name="available-settings"></a><span data-ttu-id="1d7df-127">Configurações disponíveis</span><span class="sxs-lookup"><span data-stu-id="1d7df-127">Available settings</span></span>

<span data-ttu-id="1d7df-128">As tabelas a seguir fornecem informações detalhadas sobre as configurações disponíveis para proteger os arquivos de trabalho em dispositivos e as configurações que controlam como os usuários acessam arquivos do Office em seus dispositivos móveis.</span><span class="sxs-lookup"><span data-stu-id="1d7df-128">The following tables give detailed information about the available settings to protect work files on devices and the settings that control how users access Office files from their mobile devices.</span></span>
  
 <span data-ttu-id="1d7df-129">Confira [Como os recursos de proteção no Microsoft 365 Business são mapeados para as configurações do Intune](map-protection-features-to-intune-settings.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="1d7df-129">See [How do protection features in Microsoft 365 Business map to Intune settings](map-protection-features-to-intune-settings.md) for more information.</span></span> 
  
### <a name="settings-that-protect-work-files"></a><span data-ttu-id="1d7df-130">Configurações que protegem os arquivos de trabalho</span><span class="sxs-lookup"><span data-stu-id="1d7df-130">Settings that protect work files</span></span>

<span data-ttu-id="1d7df-131">As configurações a seguir estão disponíveis para proteger os arquivos de trabalho se o dispositivo do usuário for perdido ou roubado:</span><span class="sxs-lookup"><span data-stu-id="1d7df-131">The following settings are available to protect work files if a user's device is lost or stolen:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="1d7df-132">Setting</span><span class="sxs-lookup"><span data-stu-id="1d7df-132">Setting</span></span>  <br/> |<span data-ttu-id="1d7df-133">Descrição</span><span class="sxs-lookup"><span data-stu-id="1d7df-133">Description</span></span>  <br/> |
|<span data-ttu-id="1d7df-134">Excluir arquivos de trabalho de um dispositivo inativo após determinada quantidade de dias</span><span class="sxs-lookup"><span data-stu-id="1d7df-134">Delete work files from an inactive device after this many days</span></span>  <br/> |<span data-ttu-id="1d7df-135">Se um dispositivo não for usado pela quantidade de dias que você especificar aqui, quaisquer arquivos de trabalho armazenados nele serão excluídos automaticamente.</span><span class="sxs-lookup"><span data-stu-id="1d7df-135">If a device is not used for the number of days that you specify here, any work files stored on the device will automatically be deleted.</span></span>  <br/> |
|<span data-ttu-id="1d7df-136">Forçar os usuários a salvar todos os arquivos de trabalho no OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="1d7df-136">Force users to save all work files to OneDrive for Business</span></span>  <br/> |<span data-ttu-id="1d7df-137">Se essa configuração estiver **Ativada**, o único local disponível para salvar arquivos de trabalho será o OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="1d7df-137">If this setting is **On**, the only available save location for work files will be OneDrive for Business.</span></span>  <br/> |
|<span data-ttu-id="1d7df-138">Criptografar arquivos de trabalho</span><span class="sxs-lookup"><span data-stu-id="1d7df-138">Encrypt work files</span></span>  <br/> |<span data-ttu-id="1d7df-p104">Mantenha essa configuração **Ativada** para que os arquivos de trabalho sejam protegidos por criptografia. Mesmo que o dispositivo seja perdido ou roubado, ninguém poderá ler os dados da empresa.  </span><span class="sxs-lookup"><span data-stu-id="1d7df-p104">Keep this setting **On** so that work files are protected by encryption. Even if the device is lost or stolen, no one will be able to read your company data.  </span></span><br/> |
   
### <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a><span data-ttu-id="1d7df-141">Configurações que controlam como os usuários acessam arquivos do Office em dispositivos móveis</span><span class="sxs-lookup"><span data-stu-id="1d7df-141">Settings that control how users access Office files on mobile devices</span></span>

<span data-ttu-id="1d7df-142">As configurações a seguir estão disponíveis para gerenciar como os usuários acessam arquivos de trabalho do Office:</span><span class="sxs-lookup"><span data-stu-id="1d7df-142">The following settings are available to manage how users access Office work files:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="1d7df-143">Setting</span><span class="sxs-lookup"><span data-stu-id="1d7df-143">Setting</span></span>  <br/> |<span data-ttu-id="1d7df-144">Descrição</span><span class="sxs-lookup"><span data-stu-id="1d7df-144">Description</span></span>  <br/> |
|<span data-ttu-id="1d7df-145">Exigir um PIN ou uma impressão digital para acessar aplicativos do Office</span><span class="sxs-lookup"><span data-stu-id="1d7df-145">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="1d7df-146">Se essa configuração estiver **Ativada**, os usuários precisarão fornecer outra forma de autenticação, além de seu nome de usuário e senha, para poderem usar os aplicativos do Office em seus dispositivos móveis.</span><span class="sxs-lookup"><span data-stu-id="1d7df-146">If this settings is **On** users have to provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile device.</span></span>  <br/> |
|<span data-ttu-id="1d7df-147">Redefinir o PIN quando houver muitas falhas de logon</span><span class="sxs-lookup"><span data-stu-id="1d7df-147">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="1d7df-148">Para impedir que um usuário não autorizado adivinhe um PIN, o PIN será redefinido após determinado número de tentativas incorretas.</span><span class="sxs-lookup"><span data-stu-id="1d7df-148">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="1d7df-149">Exigir que os usuários entrem novamente depois que os aplicativos do Office ficarem ociosos</span><span class="sxs-lookup"><span data-stu-id="1d7df-149">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="1d7df-150">Esta configuração determina quanto tempo o usuário pode ficar ocioso antes de ser solicitado a entrar novamente.</span><span class="sxs-lookup"><span data-stu-id="1d7df-150">This setting determines how long a user can be idle before they are prompted to sign in again.</span></span>  <br/> |
|<span data-ttu-id="1d7df-151">Negar o acesso aos arquivos de trabalho em dispositivos com jailbreak ou com acesso raiz</span><span class="sxs-lookup"><span data-stu-id="1d7df-151">Deny access to work files on jailbroken or rooted devices</span></span>  <br/> |<span data-ttu-id="1d7df-p105">Os usuários inteligentes podem ter dispositivos com jailbreak ou com acesso raiz. Isso significa que o usuário pode modificar o sistema operacional, deixando o dispositivo mais sujeito a malware. Os dispositivos são bloqueados quando essa configuração está **Ativada**.  </span><span class="sxs-lookup"><span data-stu-id="1d7df-p105">Clever users may have a device that is jailbroken or rooted. This means that the user can modify the operating system, which can make the device more subject to malware. These devices are blocked when this setting is **On**.  </span></span><br/> |
|<span data-ttu-id="1d7df-155">Permitir que os usuários copiem o conteúdo dos aplicativos do Office para os aplicativos pessoais</span><span class="sxs-lookup"><span data-stu-id="1d7df-155">Allow users to copy content from Office apps into personal apps</span></span>  <br/> |<span data-ttu-id="1d7df-156">Permitimos isso por padrão, mas se a configuração estiver **Ativada**, o usuário poderá copiar informações de uma pasta de trabalho para um arquivo pessoal.</span><span class="sxs-lookup"><span data-stu-id="1d7df-156">We do allow this by default, but if the setting is **On**, the user could copy information in a work file to a personal file.</span></span> <span data-ttu-id="1d7df-157">Quando a configuração está **Desativada**, o usuário não pode copiar informações de uma conta corporativa para um aplicativo pessoal ou uma conta pessoal.</span><span class="sxs-lookup"><span data-stu-id="1d7df-157">If the setting is **Off**, the user will be unable to copy information from a work account into a personal app or personal account.</span></span>  <br/> |
   

  

