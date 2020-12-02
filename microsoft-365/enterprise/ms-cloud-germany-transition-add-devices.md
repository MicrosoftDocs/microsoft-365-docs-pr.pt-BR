---
title: Informações adicionais sobre o dispositivo para a migração do Microsoft Cloud Alemanha
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 'Resumo: informações adicionais sobre o dispositivo em serviços ao migrar do Microsoft Cloud Alemanha (Microsoft Cloud Alemanha) para os serviços do Office 365 na nova região do datacenter alemão.'
ms.openlocfilehash: da05a3c2eb6a8d579c53d403a1ef575c389eda12
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2020
ms.locfileid: "49551948"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="948e6-103">Informações adicionais sobre o dispositivo para a migração do Microsoft Cloud Alemanha</span><span class="sxs-lookup"><span data-stu-id="948e6-103">Additional device information for the migration from Microsoft Cloud Deutschland</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="948e6-104">Perguntas frequentes</span><span class="sxs-lookup"><span data-stu-id="948e6-104">Frequently asked questions</span></span>

<span data-ttu-id="948e6-105">**Como saber se minha organização é afetada?**</span><span class="sxs-lookup"><span data-stu-id="948e6-105">**How can I tell if my organization is affected?**</span></span>

<span data-ttu-id="948e6-106">Os administradores devem verificar `https://portal.microsoftazure.de` se possuem dispositivos registrados.</span><span class="sxs-lookup"><span data-stu-id="948e6-106">Administrators should check `https://portal.microsoftazure.de` to determine if they have any registered devices.</span></span> <span data-ttu-id="948e6-107">Se sua organização tiver dispositivos registrados, você será afetado.</span><span class="sxs-lookup"><span data-stu-id="948e6-107">If your organization has registered devices, you're affected.</span></span>

<span data-ttu-id="948e6-108">**Qual é o impacto nos meus usuários?**</span><span class="sxs-lookup"><span data-stu-id="948e6-108">**What is the impact on my users?**</span></span>

<span data-ttu-id="948e6-109">Os usuários de um dispositivo registrado não poderão mais entrar depois que sua migração entrar na fase [finalizar migração do Azure ad](ms-cloud-germany-transition.md#how-is-the-migration-organized) .</span><span class="sxs-lookup"><span data-stu-id="948e6-109">Users from a registered device will no longer be able to sign in after your migration enters the [Finalize Azure AD](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>  

<span data-ttu-id="948e6-110">Verifique se todos os seus dispositivos estão registrados com o ponto de extremidade Mundial antes que sua organização seja desconectada do Microsoft Cloud Alemanha.</span><span class="sxs-lookup"><span data-stu-id="948e6-110">Ensure that all of your devices are registered with the worldwide endpoint before your organization is disconnected from Microsoft Cloud Deutschland.</span></span>
  
<span data-ttu-id="948e6-111">**Quando meus usuários registrarem seus dispositivos novamente?**</span><span class="sxs-lookup"><span data-stu-id="948e6-111">**When do my users re-register their devices?**</span></span>

<span data-ttu-id="948e6-112">É fundamental para o seu sucesso que você só cancele o registro e registre novamente os dispositivos durante a fase [separada da migração do Microsoft Cloud Alemanha](ms-cloud-germany-transition.md#how-is-the-migration-organized) .</span><span class="sxs-lookup"><span data-stu-id="948e6-112">It's critical to your success that you only unregister and re-register your devices during the [Separate from Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>

<span data-ttu-id="948e6-113">**Como faço para restaurar o estado do dispositivo após a migração?**</span><span class="sxs-lookup"><span data-stu-id="948e6-113">**How do I restore my device state after migration?**</span></span>

<span data-ttu-id="948e6-114">Para dispositivos do Windows híbridos associados do Azure AD e de propriedade da empresa registrados no Azure AD, os administradores poderão gerenciar a migração desses dispositivos por meio de fluxos de trabalho acionados remotamente que cancelarão o registro dos Estados de dispositivos antigos.</span><span class="sxs-lookup"><span data-stu-id="948e6-114">For hybrid Azure AD–joined and company-owned Windows devices that are registered with Azure AD, administrators will be able to manage the migration of these devices through remotely triggered workflows that will unregister the old device states.</span></span>
  
<span data-ttu-id="948e6-115">Para todos os outros dispositivos, incluindo dispositivos do Windows pessoais registrados no Azure AD, o usuário final deve executar essas etapas manualmente.</span><span class="sxs-lookup"><span data-stu-id="948e6-115">For all other devices, including personal Windows devices that are registered in Azure AD, the end user must perform these steps manually.</span></span> <span data-ttu-id="948e6-116">Para dispositivos associados ao Azure AD, os usuários precisam ter uma conta de administrador local para cancelar o registro e, em seguida, registrar novamente seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="948e6-116">For Azure AD–joined devices, users need to have a local administrator account to unregister and then re-register their devices.</span></span>

<span data-ttu-id="948e6-117">A Microsoft publicará instruções sobre como restaurar o estado do dispositivo com êxito.</span><span class="sxs-lookup"><span data-stu-id="948e6-117">Microsoft will publish instructions for how to successfully restore device state.</span></span> 
 
<span data-ttu-id="948e6-118">**Como saber se todos os meus dispositivos estão registrados na nuvem pública?**</span><span class="sxs-lookup"><span data-stu-id="948e6-118">**How do I know that all my devices are registered in the public cloud?**</span></span>

<span data-ttu-id="948e6-119">Para verificar se seus dispositivos estão registrados na nuvem pública, você deve exportar e baixar a lista de dispositivos do portal do Azure AD para uma planilha do Excel.</span><span class="sxs-lookup"><span data-stu-id="948e6-119">To check whether your devices are registered in the public cloud, you should export and download the list of devices from the Azure AD portal to an Excel spreadsheet.</span></span> <span data-ttu-id="948e6-120">Em seguida, filtre os dispositivos registrados (usando a coluna _registeredtime_ ) depois da fase [separada da migração do Microsoft Cloud Alemanha](ms-cloud-germany-transition.md#how-is-the-migration-organized) .</span><span class="sxs-lookup"><span data-stu-id="948e6-120">Then, filter the devices that are registered (by using the _registeredTime_ column) after the [Separate from Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>

<span data-ttu-id="948e6-121">O registro do dispositivo é desativado após a migração do locatário e não pode ser habilitado ou desabilitado.</span><span class="sxs-lookup"><span data-stu-id="948e6-121">Device registration is deactivated after migration of the tenant and cannot be enabled or disabled.</span></span> <span data-ttu-id="948e6-122">Se o Intune não for usado, entre na sua assinatura e execute este comando para reativar a opção:</span><span class="sxs-lookup"><span data-stu-id="948e6-122">If Intune is not used, sign in to your subscription and run this command to re-activate the option:</span></span>

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

## <a name="windows-hybrid-azure-ad-join"></a><span data-ttu-id="948e6-123">Ingresso no Azure AD híbrido do Windows</span><span class="sxs-lookup"><span data-stu-id="948e6-123">Windows Hybrid Azure AD join</span></span>

### <a name="windows-down-level"></a><span data-ttu-id="948e6-124">Nível inferior do Windows</span><span class="sxs-lookup"><span data-stu-id="948e6-124">Windows down-level</span></span>

<span data-ttu-id="948e6-125">Os _dispositivos de nível inferior do Windows_ são dispositivos do Windows que atualmente executam versões anteriores do Windows (como o Windows 8,1 ou Windows 7) ou que executam versões anteriores ao 2019 e 2016 do Windows Server.</span><span class="sxs-lookup"><span data-stu-id="948e6-125">_Windows down-level devices_ are Windows devices that currently run earlier versions of Windows (such as Windows 8.1 or Windows 7), or that run Windows Server versions earlier than 2019 and 2016.</span></span> <span data-ttu-id="948e6-126">Se esses dispositivos foram registrados antes, você precisará cancelar o registro e registrar novamente esses dispositivos.</span><span class="sxs-lookup"><span data-stu-id="948e6-126">If such devices were registered before, you'll need to unregister and re-register those devices.</span></span> 

<span data-ttu-id="948e6-127">Para determinar se um dispositivo de nível inferior do Windows foi previamente Unido ao Azure AD, use o seguinte comando no dispositivo:</span><span class="sxs-lookup"><span data-stu-id="948e6-127">To determine whether a Windows down-level device was previously joined to Azure AD, use following command on the device:</span></span>

```console
%programfiles%\Microsoft Workplace Join\autoworkplace /status
```

<span data-ttu-id="948e6-128">Se o dispositivo tiver ingressado anteriormente no Azure AD e se o dispositivo tiver conectividade de rede para os pontos de extremidade globais do Azure AD, você verá o seguinte resultado:</span><span class="sxs-lookup"><span data-stu-id="948e6-128">If the device was previously joined to Azure AD, and if the device has network connectivity to global Azure AD endpoints, you would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| Device Details                                                       |
+----------------------------------------------------------------------+
         DeviceId : AEE2B956-DA62-48D0-BB47-046DD992A110
       Thumbprint : 00fdfa2de5c32feae57489873a13aa6a3ff7433b
             User : user1@<tenantname>.de
Private key state : Okay
     Device state : Unknown
```

<span data-ttu-id="948e6-129">Os dispositivos afetados terão o "estado do dispositivo" com o valor "desconhecido".</span><span class="sxs-lookup"><span data-stu-id="948e6-129">The affected devices will have the "Device state" with value of "Unknown".</span></span> <span data-ttu-id="948e6-130">Se a saída for "dispositivo não Unido" ou cujo valor "estado do dispositivo" for "OK", ignore as orientações a seguir.</span><span class="sxs-lookup"><span data-stu-id="948e6-130">If the output is "Device not joined" or whose "Device state" value is "Okay", ignore the following guidance.</span></span>

<span data-ttu-id="948e6-131">Somente para dispositivos que mostram que o dispositivo é associado (por meio de DeviceID, impressão digital e assim por diante) e cujo valor de "estado do dispositivo" é "desconhecido", os administradores devem executar o seguinte comando no contexto de um usuário de domínio que faz logon em um dispositivo de nível inferior:</span><span class="sxs-lookup"><span data-stu-id="948e6-131">Only for devices that show that the device is joined (by virtue of deviceId, thumbprint, and so on) and whose "Device state" value is "Unknown", admins should run the following command in the context of a domain user signing in on such a down-level device:</span></span>

```console
"%programfiles%\Microsoft Workplace Join\autoworkplace /leave"
```

<span data-ttu-id="948e6-132">O comando anterior só precisa ser executado uma vez por usuário de logon no dispositivo de nível inferior do Windows.</span><span class="sxs-lookup"><span data-stu-id="948e6-132">The preceding command only needs to be run once per domain user signing in on the Windows down-level device.</span></span> <span data-ttu-id="948e6-133">Este comando deve ser executado no contexto da entrada de usuário do domínio.</span><span class="sxs-lookup"><span data-stu-id="948e6-133">This command should be run in the context of the domain user signing in.</span></span> 

<span data-ttu-id="948e6-134">Deve-se ter cuidado para não executar este comando quando o usuário entrar subsequentemente.</span><span class="sxs-lookup"><span data-stu-id="948e6-134">Sufficient care must be taken to not run this command when the user subsequently signs in.</span></span> <span data-ttu-id="948e6-135">Quando o comando anterior é executado, ele limpa o estado de ingresso do computador local híbrido do Azure AD associado para o usuário que entrou.</span><span class="sxs-lookup"><span data-stu-id="948e6-135">When the preceding command runs, it will clear the joined state of the local hybrid Azure AD–joined computer for the user who signed in.</span></span> <span data-ttu-id="948e6-136">E, se o computador ainda estiver configurado para ser híbrido o Azure AD – Unido no locatário, ele tentará ingressar quando o usuário entrar novamente.</span><span class="sxs-lookup"><span data-stu-id="948e6-136">And, if the computer is still configured to be hybrid Azure AD–joined in the tenant, it will attempt to join when the user signs in again.</span></span>

### <a name="windows-current"></a><span data-ttu-id="948e6-137">Windows atual</span><span class="sxs-lookup"><span data-stu-id="948e6-137">Windows Current</span></span>

#### <a name="unjoin"></a><span data-ttu-id="948e6-138">Não ingressar</span><span class="sxs-lookup"><span data-stu-id="948e6-138">Unjoin</span></span>

<span data-ttu-id="948e6-139">Para determinar se o dispositivo Windows 10 foi previamente Unido ao Azure AD, execute o seguinte comando no dispositivo:</span><span class="sxs-lookup"><span data-stu-id="948e6-139">To determine whether the Windows 10 device was previously joined to Azure AD, run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="948e6-140">Se o dispositivo for associado ao Azure AD – híbrido, o administrador veria o seguinte resultado:</span><span class="sxs-lookup"><span data-stu-id="948e6-140">If the device is hybrid Azure AD–joined, the admin would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : YES
```

<span data-ttu-id="948e6-141">Se a saída for "AzureAdJoined: no", ignore as orientações a seguir.</span><span class="sxs-lookup"><span data-stu-id="948e6-141">If the output is "AzureAdJoined : No", ignore the following guidance.</span></span>

<span data-ttu-id="948e6-142">Somente para dispositivos que mostram que o dispositivo está associado ao Azure AD, execute o seguinte comando como administrador para remover o estado de ingresso do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="948e6-142">Only for devices that show that the device is joined to Azure AD, run the following command as an admin to remove the joined state of the device.</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

<span data-ttu-id="948e6-143">O comando anterior só precisa ser executado uma vez em um contexto administrativo no dispositivo Windows.</span><span class="sxs-lookup"><span data-stu-id="948e6-143">The preceding command only needs to be run once in an administrative context on the Windows device.</span></span>

#### <a name="hybrid-ad-joinre-registration"></a><span data-ttu-id="948e6-144">ANÚNCIO híbrido Join\Re-Registration</span><span class="sxs-lookup"><span data-stu-id="948e6-144">Hybrid AD Join\Re-Registration</span></span>

<span data-ttu-id="948e6-145">O dispositivo é automaticamente Unido ao Azure AD sem intervenção de usuário ou administrador, desde que o dispositivo tenha conectividade de rede para pontos de extremidade globais do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="948e6-145">The device is automatically joined to Azure AD without user or admin intervention as long as the device has network connectivity to global Azure AD endpoints.</span></span> 


## <a name="windows-azure-ad-join"></a><span data-ttu-id="948e6-146">Ingresso no Windows Azure AD</span><span class="sxs-lookup"><span data-stu-id="948e6-146">Windows Azure AD Join</span></span>

### <a name="unjoin"></a><span data-ttu-id="948e6-147">Não ingressar</span><span class="sxs-lookup"><span data-stu-id="948e6-147">Unjoin</span></span>

<span data-ttu-id="948e6-148">Para determinar se o dispositivo Windows 10 foi previamente Unido ao Azure AD, o usuário ou administrador pode executar o seguinte comando no dispositivo:</span><span class="sxs-lookup"><span data-stu-id="948e6-148">To determine whether the Windows 10 device was previously joined to Azure AD, the user or admin can run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="948e6-149">Se o dispositivo estiver Unido ao Azure AD, o usuário ou administrador veria o seguinte resultado:</span><span class="sxs-lookup"><span data-stu-id="948e6-149">If the device is joined to Azure AD, the user or admin would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : NO
```

<span data-ttu-id="948e6-150">Se a saída for "AzureAdJoined: NO", ignore as orientações a seguir.</span><span class="sxs-lookup"><span data-stu-id="948e6-150">If the output is "AzureAdJoined : NO", ignore the following guidance.</span></span>

<span data-ttu-id="948e6-151">Usuário: se o dispositivo for associado ao Azure AD, um usuário pode sair do dispositivo das configurações.</span><span class="sxs-lookup"><span data-stu-id="948e6-151">User: If the device is Azure AD joined, a user can unjoin the device from the settings.</span></span> <span data-ttu-id="948e6-152">Verifique se há uma conta de administrador local no dispositivo antes de não ingressar no dispositivo do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="948e6-152">Verify that there is a local administrator account on the device before unjoining the device from Azure AD.</span></span> <span data-ttu-id="948e6-153">A conta de administrador local é necessária para entrar no dispositivo novamente.</span><span class="sxs-lookup"><span data-stu-id="948e6-153">The local administrator account is required to sign back into the device.</span></span>

<span data-ttu-id="948e6-154">Administrador: se o administrador da organização quiser desassociar os dispositivos dos usuários que estão associados ao Azure AD, eles poderão fazê-lo executando o seguinte comando em cada um dos dispositivos usando um mecanismo como diretiva de grupo.</span><span class="sxs-lookup"><span data-stu-id="948e6-154">Admin: If the organization's admin wants to unjoin the users' devices that are Azure AD–joined, they can do so by running the following command on each of the devices by using a mechanism such as Group Policy.</span></span> <span data-ttu-id="948e6-155">O administrador deve verificar se há uma conta de administrador local no dispositivo antes de sair do dispositivo do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="948e6-155">The admin must verify that there is a local administrator account on the device before unjoining the device from Azure AD.</span></span> <span data-ttu-id="948e6-156">A conta de administrador local é necessária para entrar no dispositivo novamente.</span><span class="sxs-lookup"><span data-stu-id="948e6-156">The local administrator account is needed to sign back into the device.</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

<span data-ttu-id="948e6-157">O comando anterior só precisa ser executado uma vez em um contexto administrativo no dispositivo Windows.</span><span class="sxs-lookup"><span data-stu-id="948e6-157">The preceding command only needs to be run once in an administrative context on the Windows device.</span></span> 

### <a name="azure-ad-joinre-registration"></a><span data-ttu-id="948e6-158">Ingresso/reinscrição do Azure AD</span><span class="sxs-lookup"><span data-stu-id="948e6-158">Azure AD Join/Re-Registration</span></span>

<span data-ttu-id="948e6-159">O usuário pode ingressar no dispositivo no Azure AD de configurações do Windows: **configurações > contas > acessar o trabalho ou escola > se conectar**.</span><span class="sxs-lookup"><span data-stu-id="948e6-159">The user can join the device to Azure AD from Windows settings: **Settings > Accounts > Access Work Or School > Connect**.</span></span>
 

## <a name="windows-azure-ad-registered-company-owned"></a><span data-ttu-id="948e6-160">Windows Azure AD registrado (pertencente à empresa)</span><span class="sxs-lookup"><span data-stu-id="948e6-160">Windows Azure AD Registered (Company owned)</span></span>

<span data-ttu-id="948e6-161">Para determinar se o dispositivo Windows 10 está registrado no Azure AD –, execute o seguinte comando no dispositivo:</span><span class="sxs-lookup"><span data-stu-id="948e6-161">To determine whether the Windows 10 device is Azure AD–registered, run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="948e6-162">Se o dispositivo for do Azure AD registrado, você verá o seguinte resultado:</span><span class="sxs-lookup"><span data-stu-id="948e6-162">If the device is Azure AD Registered, you would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| User State                                                           |
+----------------------------------------------------------------------+
           WorkplaceJoined : YES
          WamDefaultSet : NO
          WamDefaultAuthority : organizations
```

<span data-ttu-id="948e6-163">Para remover a conta do Azure AD registrada existente no dispositivo:</span><span class="sxs-lookup"><span data-stu-id="948e6-163">To remove the existing Azure AD-registered account on the device:</span></span>

- <span data-ttu-id="948e6-164">Para remover a conta registrada do Azure AD no dispositivo, use o CleanupWPJ, uma ferramenta para a qual você pode baixar aqui: [CleanupWPJ.zip](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip).</span><span class="sxs-lookup"><span data-stu-id="948e6-164">To remove the Azure AD–registered account on the device, use CleanupWPJ, a tool that you can download from here: [CleanupWPJ.zip](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip).</span></span>

- <span data-ttu-id="948e6-165">Extraia o arquivo ZIP e execute o **WPJCleanup. cmd**.</span><span class="sxs-lookup"><span data-stu-id="948e6-165">Extract the ZIP file and run **WPJCleanup.cmd**.</span></span> <span data-ttu-id="948e6-166">Essa ferramenta iniciará o executável correto com base na versão do Windows no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="948e6-166">This tool will launch the right executable based on the version of Windows on the device.</span></span>

- <span data-ttu-id="948e6-167">Usando um mecanismo como diretiva de grupo, o administrador pode executar o comando no dispositivo no contexto de qualquer usuário que esteja conectado ao dispositivo.</span><span class="sxs-lookup"><span data-stu-id="948e6-167">By using a mechanism like Group Policy, the admin can run the command on the device in the context of any user who is signed in on the device.</span></span>

<span data-ttu-id="948e6-168">Para desabilitar o Gerenciador de contas da Web solicita o registro do dispositivo no Azure AD, adicione esse valor do registro:</span><span class="sxs-lookup"><span data-stu-id="948e6-168">To disable Web Account Manager prompts to register the device in Azure AD, add this registry value:</span></span> 

- <span data-ttu-id="948e6-169">Local: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin</span><span class="sxs-lookup"><span data-stu-id="948e6-169">Location: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin</span></span>
- <span data-ttu-id="948e6-170">Tipo: DWORD (32 bits)</span><span class="sxs-lookup"><span data-stu-id="948e6-170">Type: DWORD (32 bit)</span></span>
- <span data-ttu-id="948e6-171">Nome: BlockAADWorkplaceJoin</span><span class="sxs-lookup"><span data-stu-id="948e6-171">Name: BlockAADWorkplaceJoin</span></span>
- <span data-ttu-id="948e6-172">Dados do valor: 1</span><span class="sxs-lookup"><span data-stu-id="948e6-172">Value data: 1</span></span>

<span data-ttu-id="948e6-173">A presença desse valor do registro deve bloquear o Workplace Join e impedir que os usuários vejam as solicitações para ingressar no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="948e6-173">The presence of this registry value should block workplace join and prevent users from seeing prompts to join the device.</span></span>

## <a name="android"></a><span data-ttu-id="948e6-174">Android</span><span class="sxs-lookup"><span data-stu-id="948e6-174">Android</span></span>

<span data-ttu-id="948e6-175">Para Android, os usuários precisarão cancelar o registro e registrar novamente seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="948e6-175">For Android, users will need to unregister and re-register their devices.</span></span> <span data-ttu-id="948e6-176">Isso pode ser feito por meio do aplicativo Microsoft Authenticator ou do portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="948e6-176">This can be done via the Microsoft Authenticator app or the Company Portal app.</span></span> 

- <span data-ttu-id="948e6-177">No aplicativo Microsoft Authenticator, os usuários podem acessar **configurações > registro de dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="948e6-177">From the Microsoft Authenticator app, users can go to **Settings > Device Registration**.</span></span> <span data-ttu-id="948e6-178">A partir daí, os usuários podem cancelar o registro e registrar novamente o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="948e6-178">From there users can unregister and re-register their device.</span></span>
 
- <span data-ttu-id="948e6-179">No portal da empresa, os usuários podem ir para a guia **dispositivos** e remover o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="948e6-179">From the Company Portal, users can go to **Devices** tab and remove the device.</span></span> <span data-ttu-id="948e6-180">Depois, registre novamente o dispositivo usando o portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="948e6-180">After that, re-enroll the device by using Company Portal.</span></span>
 
- <span data-ttu-id="948e6-181">Os usuários também podem cancelar o registro e registrar-se novamente, removendo a conta da página de configurações de conta e, em seguida, adicionando novamente a conta de trabalho.</span><span class="sxs-lookup"><span data-stu-id="948e6-181">Users can also unregister and re-register by removing the account from the account settings page and then re-adding the work account.</span></span>

<span data-ttu-id="948e6-182">Para cancelar o registro e registrar novamente o dispositivo no Android usando o aplicativo Microsoft Authenticator:</span><span class="sxs-lookup"><span data-stu-id="948e6-182">To unregister and re-register the device on Android by using the Microsoft Authenticator app:</span></span>

1.  <span data-ttu-id="948e6-183">Abra o aplicativo Microsoft Authenticator e vá para **configurações**.</span><span class="sxs-lookup"><span data-stu-id="948e6-183">Open the Microsoft Authenticator app and go to **Settings**.</span></span>
2.  <span data-ttu-id="948e6-184">Selecione **registro de dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="948e6-184">Select **Device registration**.</span></span>
3.  <span data-ttu-id="948e6-185">Cancele o registro do dispositivo selecionando **cancelar o registro**.</span><span class="sxs-lookup"><span data-stu-id="948e6-185">Unregister the device by selecting **Unregister**.</span></span>
4.  <span data-ttu-id="948e6-186">Para **registro de dispositivo**, registre novamente o dispositivo digitando seu endereço de email e, em seguida, selecione **registrar**.</span><span class="sxs-lookup"><span data-stu-id="948e6-186">For **Device registration**, re-register the device by typing your email address, and then select **Register**.</span></span>

<span data-ttu-id="948e6-187">Para cancelar o registro e registrar novamente um dispositivo Android com a página Configurações de Android:</span><span class="sxs-lookup"><span data-stu-id="948e6-187">To unregister and re-register an Android device with the Android Settings page:</span></span>

1.  <span data-ttu-id="948e6-188">Abra **configurações de dispositivo** e vá para **contas**.</span><span class="sxs-lookup"><span data-stu-id="948e6-188">Open **Device Settings** and go to **Accounts**.</span></span>
2.  <span data-ttu-id="948e6-189">Selecione a conta de trabalho que você deseja registrar novamente e selecione **remover conta**.</span><span class="sxs-lookup"><span data-stu-id="948e6-189">Select the work account that you want to re-register and select **Remove account**.</span></span>
3.  <span data-ttu-id="948e6-190">Depois que a conta for removida, na página **contas** , selecione **adicionar conta > conta de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="948e6-190">After the account is removed, from the **Accounts** page, select **Add Account > Work account**.</span></span>
4.  <span data-ttu-id="948e6-191">Para **ingresso no local de trabalho**, digite seu endereço de email e selecione **ingressar** para concluir o registro do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="948e6-191">For **Workplace Join**, type your email address and select **Join** to complete registering the device.</span></span>

<span data-ttu-id="948e6-192">Para cancelar o registro e registrar novamente o dispositivo no Android do portal da empresa:</span><span class="sxs-lookup"><span data-stu-id="948e6-192">To unregister and re-register the device on Android from Company Portal:</span></span>

1.  <span data-ttu-id="948e6-193">Inicie o portal da empresa e vá para a guia **dispositivos** .</span><span class="sxs-lookup"><span data-stu-id="948e6-193">Launch Company Portal and go to **Devices** tab.</span></span>
2.  <span data-ttu-id="948e6-194">Selecione o dispositivo para ver os detalhes do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="948e6-194">Select the device to see the device details.</span></span>
3.  <span data-ttu-id="948e6-195">No menu reticências (três pontos), selecione **remover dispositivo** e concluir a remoção confirmando na caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="948e6-195">From the ellipses (three dots) menu, select **Remove Device**, and complete the removal by confirming in the dialog.</span></span>
4.  <span data-ttu-id="948e6-196">Agora você deve estar desconectado do aplicativo portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="948e6-196">You should now be logged out of the Company Portal app.</span></span> <span data-ttu-id="948e6-197">Selecione **entrar** para registrar novamente o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="948e6-197">Select **Sign in** to re-register the device.</span></span>

<span data-ttu-id="948e6-198">Para obter mais informações sobre as ações necessárias durante a fase de migração dessa carga de trabalho ou o impacto na administração ou no uso, revise as informações sobre o Azure Active Directory em [informações gerais adicionais para a migração do Microsoft Cloud Alemanha](ms-cloud-germany-transition-add-general.md#azure-active-directory).</span><span class="sxs-lookup"><span data-stu-id="948e6-198">For more information about any actions required during the migration phase of this workload, or impact to administration or usage, review the information about Azure Active Directory in [Additional general information for the migration from Microsoft Cloud Deutschland](ms-cloud-germany-transition-add-general.md#azure-active-directory).</span></span>

## <a name="ios"></a><span data-ttu-id="948e6-199">iOS</span><span class="sxs-lookup"><span data-stu-id="948e6-199">iOS</span></span>

<span data-ttu-id="948e6-200">Em dispositivos iOS, um usuário precisará remover manualmente todas as contas em cache do Microsoft Authenticator, cancelar o registro do dispositivo e sair de qualquer aplicativo nativo no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="948e6-200">On iOS devices, a user will need to manually remove any cached accounts from the Microsoft Authenticator, unregister the device, and sign out from any native apps on the device.</span></span>

### <a name="step-1-if-present-remove-the-account-from-the-microsoft-authenticator-app"></a><span data-ttu-id="948e6-201">Etapa 1: se presente, remova a conta do aplicativo Microsoft Authenticator</span><span class="sxs-lookup"><span data-stu-id="948e6-201">Step 1: If present, remove the account from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="948e6-202">Toque na conta no aplicativo Microsoft Authenticator.</span><span class="sxs-lookup"><span data-stu-id="948e6-202">Tap the account in the Microsoft Authenticator app.</span></span>
2. <span data-ttu-id="948e6-203">Toque no ícone **configurações** no canto superior direito.</span><span class="sxs-lookup"><span data-stu-id="948e6-203">Tap the **Settings** icon in the top-right corner.</span></span> <span data-ttu-id="948e6-204">Se você não vir o ícone de **configurações** , talvez não esteja usando a versão mais recente do Microsoft Authenticator.</span><span class="sxs-lookup"><span data-stu-id="948e6-204">If you don't see the **Settings** icon, you might not be using the latest version of Microsoft Authenticator.</span></span>
3. <span data-ttu-id="948e6-205">Toque no botão **remover conta** .</span><span class="sxs-lookup"><span data-stu-id="948e6-205">Tap the **Remove account** button.</span></span>
4. <span data-ttu-id="948e6-206">Toque **em todos os aplicativos neste dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="948e6-206">Tap **All apps on this device**.</span></span>
 
### <a name="step-2-unregister-the-device-from-the-microsoft-authenticator-app"></a><span data-ttu-id="948e6-207">Etapa 2: cancelar o registro do dispositivo do aplicativo Microsoft Authenticator</span><span class="sxs-lookup"><span data-stu-id="948e6-207">Step 2: Unregister the device from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="948e6-208">Toque no ícone de menu no canto superior direito.</span><span class="sxs-lookup"><span data-stu-id="948e6-208">Tap the menu icon in the top-right corner.</span></span>
2. <span data-ttu-id="948e6-209">Toque em **configurações** e em **registro do dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="948e6-209">Tap **Settings** and then **Device Registration**.</span></span>
4. <span data-ttu-id="948e6-210">Se sua conta for exibida, toque em **Cancelar registro de dispositivo** e **continuar** na caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="948e6-210">If your account is shown, tap **Unregister device** and **Continue** in the dialog.</span></span> <span data-ttu-id="948e6-211">Você não deve ver nenhuma conta após isso.</span><span class="sxs-lookup"><span data-stu-id="948e6-211">You should see no account after that.</span></span>
 
### <a name="step-3-sign-out-from-individual-apps-if-necessary"></a><span data-ttu-id="948e6-212">Etapa 3: sair de aplicativos individuais, se necessário</span><span class="sxs-lookup"><span data-stu-id="948e6-212">Step 3: Sign out from individual apps if necessary</span></span>

<span data-ttu-id="948e6-213">Os usuários podem acessar aplicativos individuais, como o Outlook, o Teams e o OneDrive, e remover contas desses aplicativos.</span><span class="sxs-lookup"><span data-stu-id="948e6-213">Users can go to individual apps like Outlook, Teams, and OneDrive, and remove accounts from those apps.</span></span>

## <a name="more-information"></a><span data-ttu-id="948e6-214">Mais informações</span><span class="sxs-lookup"><span data-stu-id="948e6-214">More information</span></span>

<span data-ttu-id="948e6-215">Introdução:</span><span class="sxs-lookup"><span data-stu-id="948e6-215">Getting started:</span></span>

- [<span data-ttu-id="948e6-216">Migração do Microsoft Cloud Alemanha para os serviços do Office 365 nas novas regiões do datacenter alemão</span><span class="sxs-lookup"><span data-stu-id="948e6-216">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="948e6-217">Assistência de Migração do Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="948e6-217">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="948e6-218">Como aceitar a migração</span><span class="sxs-lookup"><span data-stu-id="948e6-218">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="948e6-219">Experiência do cliente durante a migração</span><span class="sxs-lookup"><span data-stu-id="948e6-219">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="948e6-220">Mover-se pela transição:</span><span class="sxs-lookup"><span data-stu-id="948e6-220">Moving through the transition:</span></span>

- [<span data-ttu-id="948e6-221">Ações e impactos das fases de migração</span><span class="sxs-lookup"><span data-stu-id="948e6-221">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="948e6-222">Pré-trabalho adicional</span><span class="sxs-lookup"><span data-stu-id="948e6-222">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="948e6-223">Informações adicionais para [Serviços](ms-cloud-germany-transition-add-general.md), [dispositivos](ms-cloud-germany-transition-add-devices.md), [experiências](ms-cloud-germany-transition-add-experience.md)e [AD FS](ms-cloud-germany-transition-add-adfs.md).</span><span class="sxs-lookup"><span data-stu-id="948e6-223">Additional information for [services](ms-cloud-germany-transition-add-general.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="948e6-224">Aplicativos de nuvem:</span><span class="sxs-lookup"><span data-stu-id="948e6-224">Cloud apps:</span></span>

- [<span data-ttu-id="948e6-225">Informações do programa de migração do Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="948e6-225">Dynamics 365 migration program information</span></span>](https://aka.ms/d365ceoptin)
- [<span data-ttu-id="948e6-226">Informações do programa de migração do Power BI</span><span class="sxs-lookup"><span data-stu-id="948e6-226">Power BI migration program information</span></span>](https://aka.ms/pbioptin)
- [<span data-ttu-id="948e6-227">Introdução à atualização do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="948e6-227">Getting started with your Microsoft Teams upgrade</span></span>](https://aka.ms/SkypeToTeams-Home)
