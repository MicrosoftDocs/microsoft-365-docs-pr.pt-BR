---
title: Defina configurações de proteção de aplicativo para dispositivos Android ou iOS
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
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
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 6f2b80b4-81c3-4714-a7bc-ae69313e8a33
description: Saiba como criar, editar ou excluir uma política de gerenciamento de aplicativos e proteger arquivos de trabalho em dispositivos Android ou iOS.
ms.openlocfilehash: 2e157737990c7aca6e87a676e90f62f0d40ad372
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580285"
---
# <a name="set-app-protection-settings-for-android-or-ios-devices"></a><span data-ttu-id="669b7-103">Defina configurações de proteção de aplicativo para dispositivos Android ou iOS</span><span class="sxs-lookup"><span data-stu-id="669b7-103">Set app protection settings for Android or iOS devices</span></span>

<span data-ttu-id="669b7-104">Este artigo se aplica a Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="669b7-104">This article applies to Microsoft 365 Business Premium.</span></span>

## <a name="create-an-app-management-policy"></a><span data-ttu-id="669b7-105">Criar uma política de gerenciamento de aplicativos</span><span class="sxs-lookup"><span data-stu-id="669b7-105">Create an app management policy</span></span>

1. <span data-ttu-id="669b7-106">Vá para o centro de administração do<a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="669b7-106">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span> 
    
2. <span data-ttu-id="669b7-107">Na nav esquerda, escolha **Políticas** de \>  \> **Dispositivos Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="669b7-107">In the left nav, choose **Devices** \> **Policies** \> **Add**.</span></span>
  
3. <span data-ttu-id="669b7-108">No painel **Adicionar política**, insira um nome exclusivo para essa política.</span><span class="sxs-lookup"><span data-stu-id="669b7-108">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
    
4. <span data-ttu-id="669b7-109">Em **Tipo de Política**, escolha Gerenciamento de **Aplicativos para Android** ou Gerenciamento de Aplicativos para **iOS,** dependendo do conjunto de políticas que você deseja criar.</span><span class="sxs-lookup"><span data-stu-id="669b7-109">Under **Policy type**, choose **Application Management for Android** or **Application Management for iOS**, depending on which set of policies you want to create.</span></span> 
    
5. <span data-ttu-id="669b7-110">Expanda **Proteger arquivos de trabalho quando dispositivos são perdidos ou roubados** e Gerenciar como os usuários **acessam Office arquivos em dispositivos móveis**.</span><span class="sxs-lookup"><span data-stu-id="669b7-110">Expand **Protect work files when devices are lost or stolen** and **Manage how users access Office files on mobile devices**.</span></span> <span data-ttu-id="669b7-111">Configure as configurações como você gostaria.</span><span class="sxs-lookup"><span data-stu-id="669b7-111">Configure the settings how you would like.</span></span> <span data-ttu-id="669b7-112">**Gerenciar como os usuários acessam Office**  arquivos em dispositivos móveis está  Desligado por padrão, mas recomendamos que você a a ligue e aceite os valores padrão.</span><span class="sxs-lookup"><span data-stu-id="669b7-112">**Manage how users access Office files on mobile devices** is **Off** by default, but we recommend that you turn it **On** and accept the default values.</span></span> <span data-ttu-id="669b7-113">Para obter mais informações, consulte [Configurações disponíveis](#available-settings).</span><span class="sxs-lookup"><span data-stu-id="669b7-113">For more information, see [Available settings](#available-settings).</span></span> 
    
    <span data-ttu-id="669b7-114">Você sempre poderá usar o link **Redefinir as configurações padrão** para voltar para a configuração padrão.</span><span class="sxs-lookup"><span data-stu-id="669b7-114">You can always use the **Reset default settings** link to return to the default setting.</span></span> 
    
    ![Screenshot of Create a policy with Application management for Android selected](../media/eabbe06d-ac0a-4f3a-8630-68c808b1e662.png)
  
6. <span data-ttu-id="669b7-116">Em seguida, decida **Quem receberá estas configurações?**</span><span class="sxs-lookup"><span data-stu-id="669b7-116">Next decide **Who will get these settings?**</span></span> <span data-ttu-id="669b7-117">Se você não quiser usar o grupo de segurança padrão **Todos** os Usuários, escolha **Alterar**, escolha os grupos de segurança que obterão essas configurações \> **Selecione**.</span><span class="sxs-lookup"><span data-stu-id="669b7-117">If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups that get these settings \> **Select**.</span></span>
    
7. <span data-ttu-id="669b7-118">Por fim, escolha **Concluído** para salvar a política e atribui-la a dispositivos.</span><span class="sxs-lookup"><span data-stu-id="669b7-118">Finally, choose **Done** to save the policy, and assign it to devices.</span></span> 
    
## <a name="edit-an-app-management-policy"></a><span data-ttu-id="669b7-119">Editar uma política de gerenciamento de aplicativos</span><span class="sxs-lookup"><span data-stu-id="669b7-119">Edit an app management policy</span></span>

1. <span data-ttu-id="669b7-120">No cartão **Políticas,** escolha **Editar política**.</span><span class="sxs-lookup"><span data-stu-id="669b7-120">On the **Policies** card, choose **Edit policy**.</span></span>
    
2. <span data-ttu-id="669b7-121">No painel **Editar política**, escolha a política que você deseja alterar</span><span class="sxs-lookup"><span data-stu-id="669b7-121">On the **Edit policy** pane, choose the policy you want to change</span></span> 
    
3. <span data-ttu-id="669b7-122">Escolha **Editar** ao lado de cada configuração para alterar os valores na política.</span><span class="sxs-lookup"><span data-stu-id="669b7-122">Choose **Edit** next to each setting to change the values in the policy.</span></span> <span data-ttu-id="669b7-123">Quando você altera um valor, ele é salvo automaticamente na política.</span><span class="sxs-lookup"><span data-stu-id="669b7-123">When you change a value, it's automatically saved in the policy.</span></span>
    
4. <span data-ttu-id="669b7-124">Quando terminar, feche o painel **Editar política.**</span><span class="sxs-lookup"><span data-stu-id="669b7-124">When you're finished, close the **Edit policy** pane.</span></span> 
    
## <a name="delete-an-app-management-policy"></a><span data-ttu-id="669b7-125">Excluir uma política de gerenciamento de aplicativos</span><span class="sxs-lookup"><span data-stu-id="669b7-125">Delete an app management policy</span></span>

1. <span data-ttu-id="669b7-126">Na página **Políticas,** escolha uma política e **exclua**.</span><span class="sxs-lookup"><span data-stu-id="669b7-126">On the **Policies** page, choose a policy and then **Delete**.</span></span>
    
2. <span data-ttu-id="669b7-127">No painel **Excluir política,** escolha **Confirmar** para excluir a política ou as políticas escolhidas.</span><span class="sxs-lookup"><span data-stu-id="669b7-127">On the **Delete policy** pane, choose **Confirm** to delete the policy or policies you chose.</span></span> 
    
## <a name="available-settings"></a><span data-ttu-id="669b7-128">Configurações disponíveis</span><span class="sxs-lookup"><span data-stu-id="669b7-128">Available settings</span></span>

<span data-ttu-id="669b7-129">As tabelas a seguir dão informações detalhadas sobre as configurações disponíveis para proteger arquivos de trabalho em dispositivos e as configurações que controlam como os usuários acessam Office arquivos de seus dispositivos móveis.</span><span class="sxs-lookup"><span data-stu-id="669b7-129">The following tables give detailed information about settings available to protect work files on devices and the settings that control how users access Office files from their mobile devices.</span></span>
  
 <span data-ttu-id="669b7-130">Para obter mais informações, consulte [How do protection features in Microsoft 365 Business Premium map to Intune settings](map-protection-features-to-intune-settings.md).</span><span class="sxs-lookup"><span data-stu-id="669b7-130">For more information, see [How do protection features in Microsoft 365 Business Premium map to Intune settings](map-protection-features-to-intune-settings.md).</span></span> 
  
### <a name="settings-that-protect-work-files"></a><span data-ttu-id="669b7-131">Configurações que protegem os arquivos de trabalho</span><span class="sxs-lookup"><span data-stu-id="669b7-131">Settings that protect work files</span></span>

<span data-ttu-id="669b7-132">As configurações a seguir estão disponíveis para proteger os arquivos de trabalho se o dispositivo do usuário for perdido ou roubado:</span><span class="sxs-lookup"><span data-stu-id="669b7-132">The following settings are available to protect work files if a user's device is lost or stolen:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="669b7-133">Configuração</span><span class="sxs-lookup"><span data-stu-id="669b7-133">Setting</span></span>  <br/> |<span data-ttu-id="669b7-134">Descrição</span><span class="sxs-lookup"><span data-stu-id="669b7-134">Description</span></span>  <br/> |
|<span data-ttu-id="669b7-135">Excluir arquivos de trabalho de um dispositivo inativo após determinada quantidade de dias</span><span class="sxs-lookup"><span data-stu-id="669b7-135">Delete work files from an inactive device after this many days</span></span>  <br/> |<span data-ttu-id="669b7-136">Se um dispositivo não for usado para o número de dias especificado aqui, todos os arquivos de trabalho armazenados no dispositivo serão excluídos automaticamente.</span><span class="sxs-lookup"><span data-stu-id="669b7-136">If a device isn't used for the number of days that you specify here, any work files stored on the device will be deleted automatically.</span></span>  <br/> |
|<span data-ttu-id="669b7-137">Forçar os usuários a salvar todos os arquivos de trabalho no OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="669b7-137">Force users to save all work files to OneDrive for Business</span></span>  <br/> |<span data-ttu-id="669b7-138">Se essa configuração for **On**, o único local de salvação disponível para arquivos de trabalho será OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="669b7-138">If this setting is **On**, the only available save location for work files is OneDrive for Business.</span></span>  <br/> |
|<span data-ttu-id="669b7-139">Criptografar arquivos de trabalho</span><span class="sxs-lookup"><span data-stu-id="669b7-139">Encrypt work files</span></span>  <br/> |<span data-ttu-id="669b7-140">Mantenha essa configuração **Ativada** para que os arquivos de trabalho sejam protegidos por criptografia.</span><span class="sxs-lookup"><span data-stu-id="669b7-140">Keep this setting **On** so that work files are protected by encryption.</span></span> <span data-ttu-id="669b7-141">Mesmo que o dispositivo seja perdido ou roubado, ninguém poderá ler os dados da empresa.</span><span class="sxs-lookup"><span data-stu-id="669b7-141">Even if the device is lost or stolen, no one can read your company data.</span></span>  <br/> |
   
### <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a><span data-ttu-id="669b7-142">Configurações que controlam como os usuários acessam arquivos do Office em dispositivos móveis</span><span class="sxs-lookup"><span data-stu-id="669b7-142">Settings that control how users access Office files on mobile devices</span></span>

<span data-ttu-id="669b7-143">As configurações a seguir estão disponíveis para gerenciar como os usuários acessam arquivos de trabalho do Office:</span><span class="sxs-lookup"><span data-stu-id="669b7-143">The following settings are available to manage how users access Office work files:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="669b7-144">Configuração</span><span class="sxs-lookup"><span data-stu-id="669b7-144">Setting</span></span>  <br/> |<span data-ttu-id="669b7-145">Descrição</span><span class="sxs-lookup"><span data-stu-id="669b7-145">Description</span></span>  <br/> |
|<span data-ttu-id="669b7-146">Exigir um PIN ou uma impressão digital para acessar aplicativos do Office</span><span class="sxs-lookup"><span data-stu-id="669b7-146">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="669b7-147">Se essa configuração for **On,** os usuários devem fornecer outra forma de autenticação, além de seu nome de usuário e senha, para que eles possam usar Office aplicativos em seus dispositivos móveis.</span><span class="sxs-lookup"><span data-stu-id="669b7-147">If this setting is **On** users must provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile devices.</span></span><br/> |
|<span data-ttu-id="669b7-148">Redefinir o PIN quando houver muitas falhas de logon</span><span class="sxs-lookup"><span data-stu-id="669b7-148">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="669b7-149">Para impedir que um usuário não autorizado adivinhe um PIN, o PIN será redefinido após determinado número de tentativas incorretas.</span><span class="sxs-lookup"><span data-stu-id="669b7-149">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="669b7-150">Exigir que os usuários entrem novamente depois que os aplicativos do Office ficarem ociosos</span><span class="sxs-lookup"><span data-stu-id="669b7-150">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="669b7-151">Essa configuração determina por quanto tempo um usuário pode ficar ocioso antes de ser solicitado a entrar novamente.</span><span class="sxs-lookup"><span data-stu-id="669b7-151">This setting determines how long a user can be idle before they're prompted to sign in again.</span></span>  <br/> |
|<span data-ttu-id="669b7-152">Negar o acesso aos arquivos de trabalho em dispositivos com jailbreak ou com acesso raiz</span><span class="sxs-lookup"><span data-stu-id="669b7-152">Deny access to work files on jailbroken or rooted devices</span></span>  <br/> |<span data-ttu-id="669b7-p105">Os usuários inteligentes podem ter dispositivos com jailbreak ou com acesso raiz. Isso significa que o usuário pode modificar o sistema operacional, deixando o dispositivo mais sujeito a malware. Os dispositivos são bloqueados quando essa configuração está **Ativada**.  </span><span class="sxs-lookup"><span data-stu-id="669b7-p105">Clever users may have a device that is jailbroken or rooted. This means that the user can modify the operating system, which can make the device more subject to malware. These devices are blocked when this setting is **On**.  </span></span><br/> |
|<span data-ttu-id="669b7-156">Não permita que os usuários copiem conteúdo de aplicativos Office aplicativos pessoais</span><span class="sxs-lookup"><span data-stu-id="669b7-156">Don't allow users to copy content from Office apps into personal apps</span></span>  <br/> |<span data-ttu-id="669b7-157">Permitimos isso por padrão, mas se a configuração estiver **Ativada**, o usuário poderá copiar informações de uma pasta de trabalho para um arquivo pessoal.</span><span class="sxs-lookup"><span data-stu-id="669b7-157">We do allow this by default, but if the setting is **On**, the user could copy information in a work file to a personal file.</span></span> <span data-ttu-id="669b7-158">Quando a configuração está **Desativada**, o usuário não pode copiar informações de uma conta corporativa para um aplicativo pessoal ou uma conta pessoal.</span><span class="sxs-lookup"><span data-stu-id="669b7-158">If the setting is **Off**, the user will be unable to copy information from a work account into a personal app or personal account.</span></span>  <br/> |
