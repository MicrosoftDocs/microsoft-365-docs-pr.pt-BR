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
ms.openlocfilehash: 1bbb4bf39db61a93844c21cd6062a70699b5d6d7
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688648"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="6bf95-103">Informações adicionais sobre o dispositivo para a migração do Microsoft Cloud Alemanha</span><span class="sxs-lookup"><span data-stu-id="6bf95-103">Additional device information for the migration from Microsoft Cloud Deutschland</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="6bf95-104">Perguntas frequentes</span><span class="sxs-lookup"><span data-stu-id="6bf95-104">Frequently asked questions</span></span>

<span data-ttu-id="6bf95-105">**Como saber se minha organização é afetada?**</span><span class="sxs-lookup"><span data-stu-id="6bf95-105">**How can I tell if my organization is affected?**</span></span>

<span data-ttu-id="6bf95-106">Os administradores devem verificar `https://portal.microsoftazure.de` se possuem dispositivos registrados.</span><span class="sxs-lookup"><span data-stu-id="6bf95-106">Administrators should check `https://portal.microsoftazure.de` to determine if they have any registered devices.</span></span> <span data-ttu-id="6bf95-107">Se sua organização tiver dispositivos registrados, você será afetado.</span><span class="sxs-lookup"><span data-stu-id="6bf95-107">If your organization has registered devices, you're affected.</span></span>

<span data-ttu-id="6bf95-108">**Qual é o impacto nos meus usuários?**</span><span class="sxs-lookup"><span data-stu-id="6bf95-108">**What is the impact on my users?**</span></span>

<span data-ttu-id="6bf95-109">Os usuários de um dispositivo registrado não poderão mais entrar depois que sua migração entrar na fase [finalizar migração do Azure ad](ms-cloud-germany-transition.md#how-is-the-migration-organized) .</span><span class="sxs-lookup"><span data-stu-id="6bf95-109">Users from a registered device will no longer be able to sign in after your migration enters the [Finalize Azure AD](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>  

<span data-ttu-id="6bf95-110">Verifique se todos os seus dispositivos estão registrados com o ponto de extremidade Mundial antes que sua organização seja desconectada do Microsoft Cloud Alemanha.</span><span class="sxs-lookup"><span data-stu-id="6bf95-110">Ensure that all of your devices are registered with the worldwide endpoint before your organization is disconnected from Microsoft Cloud Deutschland.</span></span>
  
<span data-ttu-id="6bf95-111">**Quando meus usuários registrarem seus dispositivos novamente?**</span><span class="sxs-lookup"><span data-stu-id="6bf95-111">**When do my users re-register their devices?**</span></span>

<span data-ttu-id="6bf95-112">É fundamental para o seu sucesso que você só cancele o registro e registre novamente os dispositivos durante a fase [separada da migração do Microsoft Cloud Alemanha](ms-cloud-germany-transition.md#how-is-the-migration-organized) .</span><span class="sxs-lookup"><span data-stu-id="6bf95-112">It's critical to your success that you only unregister and re-register your devices during the [Separate from Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>

<span data-ttu-id="6bf95-113">**Como faço para restaurar o estado do dispositivo após a migração?**</span><span class="sxs-lookup"><span data-stu-id="6bf95-113">**How do I restore my device state after migration?**</span></span>

<span data-ttu-id="6bf95-114">Para dispositivos do Windows híbridos associados do Azure AD e de propriedade da empresa registrados no Azure AD, os administradores poderão gerenciar a migração desses dispositivos por meio de fluxos de trabalho acionados remotamente que cancelarão o registro dos Estados de dispositivos antigos.</span><span class="sxs-lookup"><span data-stu-id="6bf95-114">For hybrid Azure AD–joined and company-owned Windows devices that are registered with Azure AD, administrators will be able to manage the migration of these devices through remotely triggered workflows that will unregister the old device states.</span></span>
  
<span data-ttu-id="6bf95-115">Para todos os outros dispositivos, incluindo dispositivos do Windows pessoais registrados no Azure AD, o usuário final deve executar essas etapas manualmente.</span><span class="sxs-lookup"><span data-stu-id="6bf95-115">For all other devices, including personal Windows devices that are registered in Azure AD, the end user must perform these steps manually.</span></span> <span data-ttu-id="6bf95-116">Para dispositivos associados ao Azure AD, os usuários precisam ter uma conta de administrador local para cancelar o registro e, em seguida, registrar novamente seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="6bf95-116">For Azure AD–joined devices, users need to have a local administrator account to unregister and then re-register their devices.</span></span>

<span data-ttu-id="6bf95-117">A Microsoft publicará instruções sobre como restaurar o estado do dispositivo com êxito.</span><span class="sxs-lookup"><span data-stu-id="6bf95-117">Microsoft will publish instructions for how to successfully restore device state.</span></span> 
 
<span data-ttu-id="6bf95-118">**Como saber se todos os meus dispositivos estão registrados na nuvem pública?**</span><span class="sxs-lookup"><span data-stu-id="6bf95-118">**How do I know that all my devices are registered in the public cloud?**</span></span>

<span data-ttu-id="6bf95-119">Para verificar se seus dispositivos estão registrados na nuvem pública, você deve exportar e baixar a lista de dispositivos do portal do Azure AD para uma planilha do Excel.</span><span class="sxs-lookup"><span data-stu-id="6bf95-119">To check whether your devices are registered in the public cloud, you should export and download the list of devices from the Azure AD portal to an Excel spreadsheet.</span></span> <span data-ttu-id="6bf95-120">Em seguida, filtre os dispositivos registrados (usando a coluna _registeredtime_ ) depois da fase [separada da migração do Microsoft Cloud Alemanha](ms-cloud-germany-transition.md#how-is-the-migration-organized) .</span><span class="sxs-lookup"><span data-stu-id="6bf95-120">Then, filter the devices that are registered (by using the _registeredTime_ column) after the [Separate from Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>

<span data-ttu-id="6bf95-121">O registro do dispositivo é desativado após a migração do locatário e não pode ser habilitado ou desabilitado.</span><span class="sxs-lookup"><span data-stu-id="6bf95-121">Device registration is deactivated after migration of the tenant and cannot be enabled or disabled.</span></span> <span data-ttu-id="6bf95-122">Se o Intune não for usado, entre na sua assinatura e execute este comando para reativar a opção:</span><span class="sxs-lookup"><span data-stu-id="6bf95-122">If Intune is not used, sign in to your subscription and run this command to re-activate the option:</span></span>

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

## <a name="windows-hybrid-azure-ad-join"></a><span data-ttu-id="6bf95-123">Ingresso no Azure AD híbrido do Windows</span><span class="sxs-lookup"><span data-stu-id="6bf95-123">Windows Hybrid Azure AD join</span></span>

### <a name="windows-down-level"></a><span data-ttu-id="6bf95-124">Nível inferior do Windows</span><span class="sxs-lookup"><span data-stu-id="6bf95-124">Windows down-level</span></span>

<span data-ttu-id="6bf95-125">Os _dispositivos de nível inferior do Windows_ são dispositivos do Windows que atualmente executam versões anteriores do Windows (como o Windows 8,1 ou Windows 7) ou que executam versões anteriores ao 2019 e 2016 do Windows Server.</span><span class="sxs-lookup"><span data-stu-id="6bf95-125">_Windows down-level devices_ are Windows devices that currently run earlier versions of Windows (such as Windows 8.1 or Windows 7), or that run Windows Server versions earlier than 2019 and 2016.</span></span> <span data-ttu-id="6bf95-126">Se esses dispositivos foram registrados antes, você precisará cancelar o registro e registrar novamente esses dispositivos.</span><span class="sxs-lookup"><span data-stu-id="6bf95-126">If such devices were registered before, you'll need to unregister and re-register those devices.</span></span> 

<span data-ttu-id="6bf95-127">Para determinar se um dispositivo de nível inferior do Windows foi previamente Unido ao Azure AD, use o seguinte comando no dispositivo:</span><span class="sxs-lookup"><span data-stu-id="6bf95-127">To determine whether a Windows down-level device was previously joined to Azure AD, use following command on the device:</span></span>

```console
%programfiles%\Microsoft Workplace Join\autoworkplace /status
```

<span data-ttu-id="6bf95-128">Se o dispositivo tiver ingressado anteriormente no Azure AD e se o dispositivo tiver conectividade de rede para os pontos de extremidade globais do Azure AD, você verá o seguinte resultado:</span><span class="sxs-lookup"><span data-stu-id="6bf95-128">If the device was previously joined to Azure AD, and if the device has network connectivity to global Azure AD endpoints, you would see the following output:</span></span>

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

<span data-ttu-id="6bf95-129">Os dispositivos afetados terão o "estado do dispositivo" com o valor "desconhecido".</span><span class="sxs-lookup"><span data-stu-id="6bf95-129">The affected devices will have the "Device state" with value of "Unknown".</span></span> <span data-ttu-id="6bf95-130">Se a saída for "dispositivo não Unido" ou cujo valor "estado do dispositivo" for "OK", ignore as orientações a seguir.</span><span class="sxs-lookup"><span data-stu-id="6bf95-130">If the output is "Device not joined" or whose "Device state" value is "Okay", ignore the following guidance.</span></span>

<span data-ttu-id="6bf95-131">Somente para dispositivos que mostram que o dispositivo é associado (por meio de DeviceID, impressão digital e assim por diante) e cujo valor de "estado do dispositivo" é "desconhecido", os administradores devem executar o seguinte comando no contexto de um usuário de domínio que faz logon em um dispositivo de nível inferior:</span><span class="sxs-lookup"><span data-stu-id="6bf95-131">Only for devices that show that the device is joined (by virtue of deviceId, thumbprint, and so on) and whose "Device state" value is "Unknown", admins should run the following command in the context of a domain user signing in on such a down-level device:</span></span>

```console
"%programfiles%\Microsoft Workplace Join\autoworkplace /leave"
```

<span data-ttu-id="6bf95-132">O comando anterior só precisa ser executado uma vez por usuário de logon no dispositivo de nível inferior do Windows.</span><span class="sxs-lookup"><span data-stu-id="6bf95-132">The preceding command only needs to be run once per domain user signing in on the Windows down-level device.</span></span> <span data-ttu-id="6bf95-133">Este comando deve ser executado no contexto da entrada de usuário do domínio.</span><span class="sxs-lookup"><span data-stu-id="6bf95-133">This command should be run in the context of the domain user signing in.</span></span> 

<span data-ttu-id="6bf95-134">Deve-se ter cuidado para não executar este comando quando o usuário entrar subsequentemente.</span><span class="sxs-lookup"><span data-stu-id="6bf95-134">Sufficient care must be taken to not run this command when the user subsequently signs in.</span></span> <span data-ttu-id="6bf95-135">Quando o comando anterior é executado, ele limpa o estado de ingresso do computador local híbrido do Azure AD associado para o usuário que entrou.</span><span class="sxs-lookup"><span data-stu-id="6bf95-135">When the preceding command runs, it will clear the joined state of the local hybrid Azure AD–joined computer for the user who signed in.</span></span> <span data-ttu-id="6bf95-136">E, se o computador ainda estiver configurado para ser híbrido o Azure AD – Unido no locatário, ele tentará ingressar quando o usuário entrar novamente.</span><span class="sxs-lookup"><span data-stu-id="6bf95-136">And, if the computer is still configured to be hybrid Azure AD–joined in the tenant, it will attempt to join when the user signs in again.</span></span>

### <a name="windows-current"></a><span data-ttu-id="6bf95-137">Windows atual</span><span class="sxs-lookup"><span data-stu-id="6bf95-137">Windows Current</span></span>

#### <a name="unjoin"></a><span data-ttu-id="6bf95-138">Não ingressar</span><span class="sxs-lookup"><span data-stu-id="6bf95-138">Unjoin</span></span>

<span data-ttu-id="6bf95-139">Para determinar se o dispositivo Windows 10 foi previamente Unido ao Azure AD, execute o seguinte comando no dispositivo:</span><span class="sxs-lookup"><span data-stu-id="6bf95-139">To determine whether the Windows 10 device was previously joined to Azure AD, run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="6bf95-140">Se o dispositivo for associado ao Azure AD – híbrido, o administrador veria o seguinte resultado:</span><span class="sxs-lookup"><span data-stu-id="6bf95-140">If the device is hybrid Azure AD–joined, the admin would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : YES
```

<span data-ttu-id="6bf95-141">Se a saída for "AzureAdJoined: no", ignore as orientações a seguir.</span><span class="sxs-lookup"><span data-stu-id="6bf95-141">If the output is "AzureAdJoined : No", ignore the following guidance.</span></span>

<span data-ttu-id="6bf95-142">Somente para dispositivos que mostram que o dispositivo está associado ao Azure AD, execute o seguinte comando como administrador para remover o estado de ingresso do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6bf95-142">Only for devices that show that the device is joined to Azure AD, run the following command as an admin to remove the joined state of the device.</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

<span data-ttu-id="6bf95-143">O comando anterior só precisa ser executado uma vez em um contexto administrativo no dispositivo Windows.</span><span class="sxs-lookup"><span data-stu-id="6bf95-143">The preceding command only needs to be run once in an administrative context on the Windows device.</span></span>

#### <a name="hybrid-ad-joinre-registration"></a><span data-ttu-id="6bf95-144">ANÚNCIO híbrido Join\Re-Registration</span><span class="sxs-lookup"><span data-stu-id="6bf95-144">Hybrid AD Join\Re-Registration</span></span>

<span data-ttu-id="6bf95-145">O dispositivo é automaticamente Unido ao Azure AD sem intervenção de usuário ou administrador, desde que o dispositivo tenha conectividade de rede para pontos de extremidade globais do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="6bf95-145">The device is automatically joined to Azure AD without user or admin intervention as long as the device has network connectivity to global Azure AD endpoints.</span></span> 


## <a name="windows-azure-ad-join"></a><span data-ttu-id="6bf95-146">Ingresso no Windows Azure AD</span><span class="sxs-lookup"><span data-stu-id="6bf95-146">Windows Azure AD Join</span></span>

<span data-ttu-id="6bf95-147">**Importante:** A entidade de serviço do Intune será habilitada após a migração do Commerce, que envolve a ativação do registro de dispositivos do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="6bf95-147">**IMPORTANT:** The Intune service principal will be enabled after commerce migration, which implies the activation of Azure AD Device Registration.</span></span> <span data-ttu-id="6bf95-148">Se você bloqueou o registro de dispositivos do Azure AD antes da migração, você deve desabilitar a entidade de serviço do Intune com o PowerShell para desabilitar o registro de dispositivos do Azure AD com o portal do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="6bf95-148">If you blocked Azure AD Device Registration before migration, you must disable the Intune service principal with PowerShell to disable Azure AD Device Registration with the Azure AD portal again.</span></span> <span data-ttu-id="6bf95-149">Você pode desabilitar a entidade de serviço do Intune com este comando no módulo PowerShell do Azure Active Directory para Graph.</span><span class="sxs-lookup"><span data-stu-id="6bf95-149">You can disable the Intune service principal with this command in the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

### <a name="unjoin"></a><span data-ttu-id="6bf95-150">Não ingressar</span><span class="sxs-lookup"><span data-stu-id="6bf95-150">Unjoin</span></span>

<span data-ttu-id="6bf95-151">Para determinar se o dispositivo Windows 10 foi previamente Unido ao Azure AD, o usuário ou administrador pode executar o seguinte comando no dispositivo:</span><span class="sxs-lookup"><span data-stu-id="6bf95-151">To determine whether the Windows 10 device was previously joined to Azure AD, the user or admin can run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="6bf95-152">Se o dispositivo estiver Unido ao Azure AD, o usuário ou administrador veria o seguinte resultado:</span><span class="sxs-lookup"><span data-stu-id="6bf95-152">If the device is joined to Azure AD, the user or admin would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : NO
```

<span data-ttu-id="6bf95-153">Se a saída for "AzureAdJoined: NO", ignore as orientações a seguir.</span><span class="sxs-lookup"><span data-stu-id="6bf95-153">If the output is "AzureAdJoined : NO", ignore the following guidance.</span></span>

<span data-ttu-id="6bf95-154">Usuário: se o dispositivo for associado ao Azure AD, um usuário pode sair do dispositivo das configurações.</span><span class="sxs-lookup"><span data-stu-id="6bf95-154">User: If the device is Azure AD joined, a user can unjoin the device from the settings.</span></span> <span data-ttu-id="6bf95-155">Verifique se há uma conta de administrador local no dispositivo antes de não ingressar no dispositivo do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="6bf95-155">Verify that there is a local administrator account on the device before unjoining the device from Azure AD.</span></span> <span data-ttu-id="6bf95-156">A conta de administrador local é necessária para entrar no dispositivo novamente.</span><span class="sxs-lookup"><span data-stu-id="6bf95-156">The local administrator account is required to sign back into the device.</span></span>

<span data-ttu-id="6bf95-157">Administrador: se o administrador da organização quiser desassociar os dispositivos dos usuários que estão associados ao Azure AD, eles poderão fazê-lo executando o seguinte comando em cada um dos dispositivos usando um mecanismo como diretiva de grupo.</span><span class="sxs-lookup"><span data-stu-id="6bf95-157">Admin: If the organization's admin wants to unjoin the users' devices that are Azure AD–joined, they can do so by running the following command on each of the devices by using a mechanism such as Group Policy.</span></span> <span data-ttu-id="6bf95-158">O administrador deve verificar se há uma conta de administrador local no dispositivo antes de sair do dispositivo do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="6bf95-158">The admin must verify that there is a local administrator account on the device before unjoining the device from Azure AD.</span></span> <span data-ttu-id="6bf95-159">A conta de administrador local é necessária para entrar no dispositivo novamente.</span><span class="sxs-lookup"><span data-stu-id="6bf95-159">The local administrator account is needed to sign back into the device.</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

<span data-ttu-id="6bf95-160">O comando anterior só precisa ser executado uma vez em um contexto administrativo no dispositivo Windows.</span><span class="sxs-lookup"><span data-stu-id="6bf95-160">The preceding command only needs to be run once in an administrative context on the Windows device.</span></span> 

### <a name="azure-ad-joinre-registration"></a><span data-ttu-id="6bf95-161">Ingresso/reinscrição do Azure AD</span><span class="sxs-lookup"><span data-stu-id="6bf95-161">Azure AD Join/Re-Registration</span></span>

<span data-ttu-id="6bf95-162">O usuário pode ingressar no dispositivo no Azure AD de configurações do Windows: **configurações > contas > acessar o trabalho ou escola > se conectar**.</span><span class="sxs-lookup"><span data-stu-id="6bf95-162">The user can join the device to Azure AD from Windows settings: **Settings > Accounts > Access Work Or School > Connect**.</span></span>
 

## <a name="windows-azure-ad-registered-company-owned"></a><span data-ttu-id="6bf95-163">Windows Azure AD registrado (pertencente à empresa)</span><span class="sxs-lookup"><span data-stu-id="6bf95-163">Windows Azure AD Registered (Company owned)</span></span>

<span data-ttu-id="6bf95-164">Para determinar se o dispositivo Windows 10 está registrado no Azure AD –, execute o seguinte comando no dispositivo:</span><span class="sxs-lookup"><span data-stu-id="6bf95-164">To determine whether the Windows 10 device is Azure AD–registered, run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="6bf95-165">Se o dispositivo for do Azure AD registrado, você verá o seguinte resultado:</span><span class="sxs-lookup"><span data-stu-id="6bf95-165">If the device is Azure AD Registered, you would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| User State                                                           |
+----------------------------------------------------------------------+
           WorkplaceJoined : YES
          WamDefaultSet : NO
          WamDefaultAuthority : organizations
```

<span data-ttu-id="6bf95-166">Para remover a conta do Azure AD registrada existente no dispositivo:</span><span class="sxs-lookup"><span data-stu-id="6bf95-166">To remove the existing Azure AD-registered account on the device:</span></span>

- <span data-ttu-id="6bf95-167">Para remover a conta registrada do Azure AD no dispositivo, use o CleanupWPJ, uma ferramenta para a qual você pode baixar aqui: [CleanupWPJ.zip](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip).</span><span class="sxs-lookup"><span data-stu-id="6bf95-167">To remove the Azure AD–registered account on the device, use CleanupWPJ, a tool that you can download from here: [CleanupWPJ.zip](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip).</span></span>

- <span data-ttu-id="6bf95-168">Extraia o arquivo ZIP e execute o **WPJCleanup. cmd**.</span><span class="sxs-lookup"><span data-stu-id="6bf95-168">Extract the ZIP file and run **WPJCleanup.cmd**.</span></span> <span data-ttu-id="6bf95-169">Essa ferramenta iniciará o executável correto com base na versão do Windows no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6bf95-169">This tool will launch the right executable based on the version of Windows on the device.</span></span>

- <span data-ttu-id="6bf95-170">Usando um mecanismo como diretiva de grupo, o administrador pode executar o comando no dispositivo no contexto de qualquer usuário que esteja conectado ao dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6bf95-170">By using a mechanism like Group Policy, the admin can run the command on the device in the context of any user who is signed in on the device.</span></span>

<span data-ttu-id="6bf95-171">Para desabilitar o Gerenciador de contas da Web solicita o registro do dispositivo no Azure AD, adicione esse valor do registro:</span><span class="sxs-lookup"><span data-stu-id="6bf95-171">To disable Web Account Manager prompts to register the device in Azure AD, add this registry value:</span></span> 

- <span data-ttu-id="6bf95-172">Local: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin</span><span class="sxs-lookup"><span data-stu-id="6bf95-172">Location: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin</span></span>
- <span data-ttu-id="6bf95-173">Tipo: DWORD (32 bits)</span><span class="sxs-lookup"><span data-stu-id="6bf95-173">Type: DWORD (32 bit)</span></span>
- <span data-ttu-id="6bf95-174">Nome: BlockAADWorkplaceJoin</span><span class="sxs-lookup"><span data-stu-id="6bf95-174">Name: BlockAADWorkplaceJoin</span></span>
- <span data-ttu-id="6bf95-175">Dados do valor: 1</span><span class="sxs-lookup"><span data-stu-id="6bf95-175">Value data: 1</span></span>

<span data-ttu-id="6bf95-176">A presença desse valor do registro deve bloquear o Workplace Join e impedir que os usuários vejam as solicitações para ingressar no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6bf95-176">The presence of this registry value should block workplace join and prevent users from seeing prompts to join the device.</span></span>

## <a name="android"></a><span data-ttu-id="6bf95-177">Android</span><span class="sxs-lookup"><span data-stu-id="6bf95-177">Android</span></span>

<span data-ttu-id="6bf95-178">Para Android, os usuários precisarão cancelar o registro e registrar novamente seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="6bf95-178">For Android, users will need to unregister and re-register their devices.</span></span> <span data-ttu-id="6bf95-179">Isso pode ser feito por meio do aplicativo Microsoft Authenticator ou do portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="6bf95-179">This can be done via the Microsoft Authenticator app or the Company Portal app.</span></span> 

- <span data-ttu-id="6bf95-180">No aplicativo Microsoft Authenticator, os usuários podem acessar **configurações > registro de dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="6bf95-180">From the Microsoft Authenticator app, users can go to **Settings > Device Registration**.</span></span> <span data-ttu-id="6bf95-181">A partir daí, os usuários podem cancelar o registro e registrar novamente o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6bf95-181">From there users can unregister and re-register their device.</span></span>
 
- <span data-ttu-id="6bf95-182">No portal da empresa, os usuários podem ir para a guia **dispositivos** e remover o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6bf95-182">From the Company Portal, users can go to **Devices** tab and remove the device.</span></span> <span data-ttu-id="6bf95-183">Depois, registre novamente o dispositivo usando o portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="6bf95-183">After that, re-enroll the device by using Company Portal.</span></span>
 
- <span data-ttu-id="6bf95-184">Os usuários também podem cancelar o registro e registrar-se novamente, removendo a conta da página de configurações de conta e, em seguida, adicionando novamente a conta de trabalho.</span><span class="sxs-lookup"><span data-stu-id="6bf95-184">Users can also unregister and re-register by removing the account from the account settings page and then re-adding the work account.</span></span>

<span data-ttu-id="6bf95-185">Para cancelar o registro e registrar novamente o dispositivo no Android usando o aplicativo Microsoft Authenticator:</span><span class="sxs-lookup"><span data-stu-id="6bf95-185">To unregister and re-register the device on Android by using the Microsoft Authenticator app:</span></span>

1.  <span data-ttu-id="6bf95-186">Abra o aplicativo Microsoft Authenticator e vá para **configurações**.</span><span class="sxs-lookup"><span data-stu-id="6bf95-186">Open the Microsoft Authenticator app and go to **Settings**.</span></span>
2.  <span data-ttu-id="6bf95-187">Selecione **registro de dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="6bf95-187">Select **Device registration**.</span></span>
3.  <span data-ttu-id="6bf95-188">Cancele o registro do dispositivo selecionando **cancelar o registro**.</span><span class="sxs-lookup"><span data-stu-id="6bf95-188">Unregister the device by selecting **Unregister**.</span></span>
4.  <span data-ttu-id="6bf95-189">Para **registro de dispositivo**, registre novamente o dispositivo digitando seu endereço de email e, em seguida, selecione **registrar**.</span><span class="sxs-lookup"><span data-stu-id="6bf95-189">For **Device registration**, re-register the device by typing your email address, and then select **Register**.</span></span>

<span data-ttu-id="6bf95-190">Para cancelar o registro e registrar novamente um dispositivo Android com a página Configurações de Android:</span><span class="sxs-lookup"><span data-stu-id="6bf95-190">To unregister and re-register an Android device with the Android Settings page:</span></span>

1.  <span data-ttu-id="6bf95-191">Abra **configurações de dispositivo** e vá para **contas**.</span><span class="sxs-lookup"><span data-stu-id="6bf95-191">Open **Device Settings** and go to **Accounts**.</span></span>
2.  <span data-ttu-id="6bf95-192">Selecione a conta de trabalho que você deseja registrar novamente e selecione **remover conta**.</span><span class="sxs-lookup"><span data-stu-id="6bf95-192">Select the work account that you want to re-register and select **Remove account**.</span></span>
3.  <span data-ttu-id="6bf95-193">Depois que a conta for removida, na página **contas** , selecione **adicionar conta > conta de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="6bf95-193">After the account is removed, from the **Accounts** page, select **Add Account > Work account**.</span></span>
4.  <span data-ttu-id="6bf95-194">Para **ingresso no local de trabalho**, digite seu endereço de email e selecione **ingressar** para concluir o registro do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6bf95-194">For **Workplace Join**, type your email address and select **Join** to complete registering the device.</span></span>

<span data-ttu-id="6bf95-195">Para cancelar o registro e registrar novamente o dispositivo no Android do portal da empresa:</span><span class="sxs-lookup"><span data-stu-id="6bf95-195">To unregister and re-register the device on Android from Company Portal:</span></span>

1.  <span data-ttu-id="6bf95-196">Inicie o portal da empresa e vá para a guia **dispositivos** .</span><span class="sxs-lookup"><span data-stu-id="6bf95-196">Launch Company Portal and go to **Devices** tab.</span></span>
2.  <span data-ttu-id="6bf95-197">Selecione o dispositivo para ver os detalhes do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6bf95-197">Select the device to see the device details.</span></span>
3.  <span data-ttu-id="6bf95-198">No menu reticências (três pontos), selecione **remover dispositivo** e concluir a remoção confirmando na caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="6bf95-198">From the ellipses (three dots) menu, select **Remove Device**, and complete the removal by confirming in the dialog.</span></span>
4.  <span data-ttu-id="6bf95-199">Agora você deve estar desconectado do aplicativo portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="6bf95-199">You should now be logged out of the Company Portal app.</span></span> <span data-ttu-id="6bf95-200">Selecione **entrar** para registrar novamente o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6bf95-200">Select **Sign in** to re-register the device.</span></span>

<span data-ttu-id="6bf95-201">Para obter mais informações sobre as ações necessárias durante a fase de migração dessa carga de trabalho ou o impacto na administração ou no uso, revise as informações sobre o Azure Active Directory (Azure AD) em [informações adicionais sobre o Azure ad para a migração do Microsoft Cloud Alemanha](ms-cloud-germany-transition-azure-ad.md).</span><span class="sxs-lookup"><span data-stu-id="6bf95-201">For more information about any actions required during the migration phase of this workload, or impact to administration or usage, review the information about Azure Active Directory (Azure AD) in [Additional Azure AD information for the migration from Microsoft Cloud Deutschland](ms-cloud-germany-transition-azure-ad.md).</span></span>

## <a name="ios"></a><span data-ttu-id="6bf95-202">iOS</span><span class="sxs-lookup"><span data-stu-id="6bf95-202">iOS</span></span>

<span data-ttu-id="6bf95-203">Em dispositivos iOS, um usuário precisará remover manualmente todas as contas em cache do Microsoft Authenticator, cancelar o registro do dispositivo e sair de qualquer aplicativo nativo no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6bf95-203">On iOS devices, a user will need to manually remove any cached accounts from the Microsoft Authenticator, unregister the device, and sign out from any native apps on the device.</span></span>

### <a name="step-1-if-present-remove-the-account-from-the-microsoft-authenticator-app"></a><span data-ttu-id="6bf95-204">Etapa 1: se presente, remova a conta do aplicativo Microsoft Authenticator</span><span class="sxs-lookup"><span data-stu-id="6bf95-204">Step 1: If present, remove the account from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="6bf95-205">Toque na conta no aplicativo Microsoft Authenticator.</span><span class="sxs-lookup"><span data-stu-id="6bf95-205">Tap the account in the Microsoft Authenticator app.</span></span>
2. <span data-ttu-id="6bf95-206">Toque no ícone **configurações** no canto superior direito.</span><span class="sxs-lookup"><span data-stu-id="6bf95-206">Tap the **Settings** icon in the top-right corner.</span></span> <span data-ttu-id="6bf95-207">Se você não vir o ícone de **configurações** , talvez não esteja usando a versão mais recente do Microsoft Authenticator.</span><span class="sxs-lookup"><span data-stu-id="6bf95-207">If you don't see the **Settings** icon, you might not be using the latest version of Microsoft Authenticator.</span></span>
3. <span data-ttu-id="6bf95-208">Toque no botão **remover conta** .</span><span class="sxs-lookup"><span data-stu-id="6bf95-208">Tap the **Remove account** button.</span></span>
4. <span data-ttu-id="6bf95-209">Toque **em todos os aplicativos neste dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="6bf95-209">Tap **All apps on this device**.</span></span>
 
### <a name="step-2-unregister-the-device-from-the-microsoft-authenticator-app"></a><span data-ttu-id="6bf95-210">Etapa 2: cancelar o registro do dispositivo do aplicativo Microsoft Authenticator</span><span class="sxs-lookup"><span data-stu-id="6bf95-210">Step 2: Unregister the device from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="6bf95-211">Toque no ícone de menu no canto superior direito.</span><span class="sxs-lookup"><span data-stu-id="6bf95-211">Tap the menu icon in the top-right corner.</span></span>
2. <span data-ttu-id="6bf95-212">Toque em **configurações** e em **registro do dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="6bf95-212">Tap **Settings** and then **Device Registration**.</span></span>
4. <span data-ttu-id="6bf95-213">Se sua conta for exibida, toque em **Cancelar registro de dispositivo** e **continuar** na caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="6bf95-213">If your account is shown, tap **Unregister device** and **Continue** in the dialog.</span></span> <span data-ttu-id="6bf95-214">Você não deve ver nenhuma conta após isso.</span><span class="sxs-lookup"><span data-stu-id="6bf95-214">You should see no account after that.</span></span>
 
### <a name="step-3-sign-out-from-individual-apps-if-necessary"></a><span data-ttu-id="6bf95-215">Etapa 3: sair de aplicativos individuais, se necessário</span><span class="sxs-lookup"><span data-stu-id="6bf95-215">Step 3: Sign out from individual apps if necessary</span></span>

<span data-ttu-id="6bf95-216">Os usuários podem acessar aplicativos individuais, como o Outlook, o Teams e o OneDrive, e remover contas desses aplicativos.</span><span class="sxs-lookup"><span data-stu-id="6bf95-216">Users can go to individual apps like Outlook, Teams, and OneDrive, and remove accounts from those apps.</span></span>

## <a name="more-information"></a><span data-ttu-id="6bf95-217">Mais informações</span><span class="sxs-lookup"><span data-stu-id="6bf95-217">More information</span></span>

<span data-ttu-id="6bf95-218">Introdução:</span><span class="sxs-lookup"><span data-stu-id="6bf95-218">Getting started:</span></span>

- [<span data-ttu-id="6bf95-219">Migração do Microsoft Cloud Alemanha para os serviços do Office 365 nas novas regiões do datacenter alemão</span><span class="sxs-lookup"><span data-stu-id="6bf95-219">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="6bf95-220">Assistência de Migração do Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="6bf95-220">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="6bf95-221">Como aceitar a migração</span><span class="sxs-lookup"><span data-stu-id="6bf95-221">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="6bf95-222">Experiência do cliente durante a migração</span><span class="sxs-lookup"><span data-stu-id="6bf95-222">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="6bf95-223">Mover-se pela transição:</span><span class="sxs-lookup"><span data-stu-id="6bf95-223">Moving through the transition:</span></span>

- [<span data-ttu-id="6bf95-224">Ações e impactos das fases de migração</span><span class="sxs-lookup"><span data-stu-id="6bf95-224">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="6bf95-225">Pré-trabalho adicional</span><span class="sxs-lookup"><span data-stu-id="6bf95-225">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="6bf95-226">Informações adicionais para o [Azure ad](ms-cloud-germany-transition-azure-ad.md), [dispositivos](ms-cloud-germany-transition-add-devices.md), [experiências](ms-cloud-germany-transition-add-experience.md)e [AD FS](ms-cloud-germany-transition-add-adfs.md).</span><span class="sxs-lookup"><span data-stu-id="6bf95-226">Additional information for [Azure AD](ms-cloud-germany-transition-azure-ad.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="6bf95-227">Aplicativos de nuvem:</span><span class="sxs-lookup"><span data-stu-id="6bf95-227">Cloud apps:</span></span>

- [<span data-ttu-id="6bf95-228">Informações do programa de migração do Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="6bf95-228">Dynamics 365 migration program information</span></span>](https://aka.ms/d365ceoptin)
- [<span data-ttu-id="6bf95-229">Informações do programa de migração do Power BI</span><span class="sxs-lookup"><span data-stu-id="6bf95-229">Power BI migration program information</span></span>](https://aka.ms/pbioptin)
- [<span data-ttu-id="6bf95-230">Introdução à atualização do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6bf95-230">Getting started with your Microsoft Teams upgrade</span></span>](https://aka.ms/SkypeToTeams-Home)
