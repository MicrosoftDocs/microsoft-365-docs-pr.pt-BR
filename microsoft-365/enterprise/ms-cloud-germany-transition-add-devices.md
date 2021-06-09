---
title: Informações adicionais do dispositivo para a migração do Microsoft Cloud Deutschland
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
description: 'Resumo: Informações adicionais sobre os serviços do dispositivo ao mudar do Microsoft Cloud Germany (Microsoft Cloud Deutschland) para Office 365 serviços na nova região do datacenter alemão.'
ms.openlocfilehash: 21188372f03af394fe1c0e227c1adeabbad02a85
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928151"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="6acee-103">Informações adicionais do dispositivo para a migração do Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="6acee-103">Additional device information for the migration from Microsoft Cloud Deutschland</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="6acee-104">Perguntas frequentes</span><span class="sxs-lookup"><span data-stu-id="6acee-104">Frequently asked questions</span></span>

<span data-ttu-id="6acee-105">**Como posso saber se minha organização foi afetada?**</span><span class="sxs-lookup"><span data-stu-id="6acee-105">**How can I tell if my organization is affected?**</span></span>

<span data-ttu-id="6acee-106">Os administradores devem `https://portal.microsoftazure.de` verificar para determinar se eles têm dispositivos registrados.</span><span class="sxs-lookup"><span data-stu-id="6acee-106">Administrators should check `https://portal.microsoftazure.de` to determine if they have any registered devices.</span></span> <span data-ttu-id="6acee-107">Se sua organização tiver dispositivos registrados, você será afetado.</span><span class="sxs-lookup"><span data-stu-id="6acee-107">If your organization has registered devices, you're affected.</span></span>

<span data-ttu-id="6acee-108">**Qual é o impacto nos meus usuários?**</span><span class="sxs-lookup"><span data-stu-id="6acee-108">**What is the impact on my users?**</span></span>

<span data-ttu-id="6acee-109">Os usuários de um dispositivo registrado não poderão mais entrar depois que a migração entrar na fase de migração finalizar o [Azure AD.](ms-cloud-germany-transition.md#how-is-the-migration-organized)</span><span class="sxs-lookup"><span data-stu-id="6acee-109">Users from a registered device will no longer be able to sign in after your migration enters the [Finalize Azure AD](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>  

<span data-ttu-id="6acee-110">Verifique se todos os seus dispositivos estão registrados com o ponto de extremidade em todo o mundo antes que sua organização seja desconectada do Microsoft Cloud Deutschland.</span><span class="sxs-lookup"><span data-stu-id="6acee-110">Ensure that all of your devices are registered with the worldwide endpoint before your organization is disconnected from Microsoft Cloud Deutschland.</span></span>
  
<span data-ttu-id="6acee-111">**Quando meus usuários registram seus dispositivos de novo?**</span><span class="sxs-lookup"><span data-stu-id="6acee-111">**When do my users re-register their devices?**</span></span>

<span data-ttu-id="6acee-112">É fundamental para o seu sucesso que você apenas não registre e registre seus dispositivos durante a fase de migração [Separate from Microsoft Cloud Deutschland.](ms-cloud-germany-transition.md#how-is-the-migration-organized)</span><span class="sxs-lookup"><span data-stu-id="6acee-112">It's critical to your success that you only unregister and re-register your devices during the [Separate from Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>

<span data-ttu-id="6acee-113">**Como restaurar meu estado de dispositivo após a migração?**</span><span class="sxs-lookup"><span data-stu-id="6acee-113">**How do I restore my device state after migration?**</span></span>

<span data-ttu-id="6acee-114">Para dispositivos híbridos do Azure AD-joined e de propriedade da empresa Windows registrados no Azure AD, os administradores poderão gerenciar a migração desses dispositivos por meio de fluxos de trabalho disparados remotamente que não registrarão os estados do dispositivo antigo.</span><span class="sxs-lookup"><span data-stu-id="6acee-114">For hybrid Azure AD–joined and company-owned Windows devices that are registered with Azure AD, administrators will be able to manage the migration of these devices through remotely triggered workflows that will unregister the old device states.</span></span>
  
<span data-ttu-id="6acee-115">Para todos os outros dispositivos, incluindo Windows pessoais registrados no Azure AD, o usuário final deve executar essas etapas manualmente.</span><span class="sxs-lookup"><span data-stu-id="6acee-115">For all other devices, including personal Windows devices that are registered in Azure AD, the end user must perform these steps manually.</span></span> <span data-ttu-id="6acee-116">Para dispositivos ingressados no Azure AD, os usuários precisam ter uma conta de administrador local para não registrar e, em seguida, registrar seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="6acee-116">For Azure AD–joined devices, users need to have a local administrator account to unregister and then re-register their devices.</span></span>

<span data-ttu-id="6acee-117">A Microsoft publicará instruções sobre como restaurar com êxito o estado do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6acee-117">Microsoft will publish instructions for how to successfully restore device state.</span></span> 
 
<span data-ttu-id="6acee-118">**Como saber se todos os meus dispositivos estão registrados na nuvem pública?**</span><span class="sxs-lookup"><span data-stu-id="6acee-118">**How do I know that all my devices are registered in the public cloud?**</span></span>

<span data-ttu-id="6acee-119">Para verificar se seus dispositivos estão registrados na nuvem pública, você deve exportar e baixar a lista de dispositivos do portal do Azure AD para uma planilha Excel.</span><span class="sxs-lookup"><span data-stu-id="6acee-119">To check whether your devices are registered in the public cloud, you should export and download the list of devices from the Azure AD portal to an Excel spreadsheet.</span></span> <span data-ttu-id="6acee-120">Em seguida, filtre os dispositivos registrados (usando a coluna _registeredTime)_ após a fase de migração [Separate from Microsoft Cloud Deutschland.](ms-cloud-germany-transition.md#how-is-the-migration-organized)</span><span class="sxs-lookup"><span data-stu-id="6acee-120">Then, filter the devices that are registered (by using the _registeredTime_ column) after the [Separate from Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>

<span data-ttu-id="6acee-121">O registro do dispositivo é desativado após a migração do locatário e não pode ser habilitado ou desabilitado.</span><span class="sxs-lookup"><span data-stu-id="6acee-121">Device registration is deactivated after migration of the tenant and cannot be enabled or disabled.</span></span> <span data-ttu-id="6acee-122">Se o Intune não for usado, entre em sua assinatura e execute este comando para reativá-lo:</span><span class="sxs-lookup"><span data-stu-id="6acee-122">If Intune is not used, sign in to your subscription and run this command to re-activate the option:</span></span>

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

## <a name="hybrid-azure-ad-join"></a><span data-ttu-id="6acee-123">Ingresso no Azure AD híbrido</span><span class="sxs-lookup"><span data-stu-id="6acee-123">Hybrid Azure AD join</span></span>

### <a name="windows-down-level"></a><span data-ttu-id="6acee-124">Windows nível inferior</span><span class="sxs-lookup"><span data-stu-id="6acee-124">Windows down-level</span></span>

<span data-ttu-id="6acee-125">_Windows dispositivos_ de nível inferior são Windows dispositivos que atualmente são executados versões anteriores do Windows (como Windows 8.1 ou Windows 7) ou que executem versões do Windows Server anteriores a 2019 e 2016.</span><span class="sxs-lookup"><span data-stu-id="6acee-125">_Windows down-level devices_ are Windows devices that currently run earlier versions of Windows (such as Windows 8.1 or Windows 7), or that run Windows Server versions earlier than 2019 and 2016.</span></span> <span data-ttu-id="6acee-126">Se esses dispositivos tiverem sido registrados anteriormente, você precisará deso registrar e registrar esses dispositivos.</span><span class="sxs-lookup"><span data-stu-id="6acee-126">If such devices were registered before, you'll need to unregister and re-register those devices.</span></span> 

<span data-ttu-id="6acee-127">Para determinar se um Windows de nível inferior foi ingressado anteriormente no Azure AD, use o seguinte comando no dispositivo:</span><span class="sxs-lookup"><span data-stu-id="6acee-127">To determine whether a Windows down-level device was previously joined to Azure AD, use following command on the device:</span></span>

```console
%programfiles%\Microsoft Workplace Join\autoworkplace /status
```

<span data-ttu-id="6acee-128">Se o dispositivo tiver sido ingressado anteriormente no Azure AD e se o dispositivo tiver conectividade de rede com pontos de extremidade globais do Azure AD, você verá a seguinte saída:</span><span class="sxs-lookup"><span data-stu-id="6acee-128">If the device was previously joined to Azure AD, and if the device has network connectivity to global Azure AD endpoints, you would see the following output:</span></span>

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

<span data-ttu-id="6acee-129">Os dispositivos afetados terão o "estado do dispositivo" com o valor "Desconhecido".</span><span class="sxs-lookup"><span data-stu-id="6acee-129">The affected devices will have the "Device state" with value of "Unknown".</span></span> <span data-ttu-id="6acee-130">Se a saída for "Dispositivo não ingressado" ou cujo valor "Estado do dispositivo" for "Ok", ignore as seguintes diretrizes.</span><span class="sxs-lookup"><span data-stu-id="6acee-130">If the output is "Device not joined" or whose "Device state" value is "Okay", ignore the following guidance.</span></span>

<span data-ttu-id="6acee-131">Somente para dispositivos que mostram que o dispositivo está ingressado (em virtude de deviceId, impressão digital e assim por diante) e cujo valor "Estado do dispositivo" é "Desconhecido", os administradores devem executar o seguinte comando no contexto de um usuário de domínio que faz logon em um dispositivo de nível inferior:</span><span class="sxs-lookup"><span data-stu-id="6acee-131">Only for devices that show that the device is joined (by virtue of deviceId, thumbprint, and so on) and whose "Device state" value is "Unknown", admins should run the following command in the context of a domain user signing in on such a down-level device:</span></span>

```console
"%programfiles%\Microsoft Workplace Join\autoworkplace /leave"
```

<span data-ttu-id="6acee-132">O comando anterior só precisa ser executado uma vez por usuário de domínio que está Windows dispositivo de nível inferior.</span><span class="sxs-lookup"><span data-stu-id="6acee-132">The preceding command only needs to be run once per domain user signing in on the Windows down-level device.</span></span> <span data-ttu-id="6acee-133">Esse comando deve ser executado no contexto da sessão do usuário de domínio.</span><span class="sxs-lookup"><span data-stu-id="6acee-133">This command should be run in the context of the domain user signing in.</span></span> 

<span data-ttu-id="6acee-134">É necessário ter cuidado suficiente para não executar esse comando quando o usuário entrar posteriormente.</span><span class="sxs-lookup"><span data-stu-id="6acee-134">Sufficient care must be taken to not run this command when the user subsequently signs in.</span></span> <span data-ttu-id="6acee-135">Quando o comando anterior for executado, ele limpará o estado ingressado do computador híbrido local do Azure AD ingressado para o usuário que entrou.</span><span class="sxs-lookup"><span data-stu-id="6acee-135">When the preceding command runs, it will clear the joined state of the local hybrid Azure AD–joined computer for the user who signed in.</span></span> <span data-ttu-id="6acee-136">E, se o computador ainda estiver configurado para ser híbrido do Azure AD- ingressado no locatário, ele tentará ingressar quando o usuário entrar novamente.</span><span class="sxs-lookup"><span data-stu-id="6acee-136">And, if the computer is still configured to be hybrid Azure AD–joined in the tenant, it will attempt to join when the user signs in again.</span></span>

### <a name="windows-current"></a><span data-ttu-id="6acee-137">Windows Current</span><span class="sxs-lookup"><span data-stu-id="6acee-137">Windows Current</span></span>

#### <a name="unjoin"></a><span data-ttu-id="6acee-138">Unjoin</span><span class="sxs-lookup"><span data-stu-id="6acee-138">Unjoin</span></span>

<span data-ttu-id="6acee-139">Para determinar se o dispositivo Windows 10 foi ingressado anteriormente no Azure AD, execute o seguinte comando no dispositivo:</span><span class="sxs-lookup"><span data-stu-id="6acee-139">To determine whether the Windows 10 device was previously joined to Azure AD, run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="6acee-140">Se o dispositivo for híbrido ingressado no Azure AD, o administrador verá a seguinte saída:</span><span class="sxs-lookup"><span data-stu-id="6acee-140">If the device is hybrid Azure AD–joined, the admin would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : YES
```

<span data-ttu-id="6acee-141">Se a saída for "AzureAdJoined : Não", ignore as seguintes diretrizes.</span><span class="sxs-lookup"><span data-stu-id="6acee-141">If the output is "AzureAdJoined : No", ignore the following guidance.</span></span>

<span data-ttu-id="6acee-142">Somente para dispositivos que mostram que o dispositivo está ingressado no Azure AD, execute o seguinte comando como administrador para remover o estado ingressado do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6acee-142">Only for devices that show that the device is joined to Azure AD, run the following command as an admin to remove the joined state of the device.</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

<span data-ttu-id="6acee-143">O comando anterior só precisa ser executado uma vez em um contexto administrativo no Windows dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6acee-143">The preceding command only needs to be run once in an administrative context on the Windows device.</span></span>

#### <a name="hybrid-ad-joinre-registration"></a><span data-ttu-id="6acee-144">Junção AD Híbrida\Recadastramento</span><span class="sxs-lookup"><span data-stu-id="6acee-144">Hybrid AD Join\Re-Registration</span></span>

<span data-ttu-id="6acee-145">O dispositivo é automaticamente ingressado no Azure AD sem intervenção de usuário ou administrador, desde que o dispositivo tenha conectividade de rede com pontos de extremidade globais do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="6acee-145">The device is automatically joined to Azure AD without user or admin intervention as long as the device has network connectivity to global Azure AD endpoints.</span></span> 


## <a name="azure-ad-join"></a><span data-ttu-id="6acee-146">Ingressar no Azure AD</span><span class="sxs-lookup"><span data-stu-id="6acee-146">Azure AD Join</span></span>

<span data-ttu-id="6acee-147">**IMPORTANTE:** A entidade de serviço do Intune será habilitada após a migração do comércio, o que implica na ativação do Registro de Dispositivo do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="6acee-147">**IMPORTANT:** The Intune service principal will be enabled after commerce migration, which implies the activation of Azure AD Device Registration.</span></span> <span data-ttu-id="6acee-148">Se você bloqueou o Registro de Dispositivo do Azure AD antes da migração, deverá desabilitar a entidade de serviço do Intune com o PowerShell para desabilitar o Registro de Dispositivo do Azure AD com o portal do Azure AD novamente.</span><span class="sxs-lookup"><span data-stu-id="6acee-148">If you blocked Azure AD Device Registration before migration, you must disable the Intune service principal with PowerShell to disable Azure AD Device Registration with the Azure AD portal again.</span></span> <span data-ttu-id="6acee-149">Você pode desabilitar a entidade de serviço do Intune com esse comando no Azure Active Directory PowerShell para Graph módulo.</span><span class="sxs-lookup"><span data-stu-id="6acee-149">You can disable the Intune service principal with this command in the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

### <a name="unjoin"></a><span data-ttu-id="6acee-150">Unjoin</span><span class="sxs-lookup"><span data-stu-id="6acee-150">Unjoin</span></span>

<span data-ttu-id="6acee-151">Para determinar se o dispositivo Windows 10 foi ingressado anteriormente no Azure AD, o usuário ou administrador pode executar o seguinte comando no dispositivo:</span><span class="sxs-lookup"><span data-stu-id="6acee-151">To determine whether the Windows 10 device was previously joined to Azure AD, the user or admin can run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="6acee-152">Se o dispositivo for ingressado no Azure AD, o usuário ou administrador verá a seguinte saída:</span><span class="sxs-lookup"><span data-stu-id="6acee-152">If the device is joined to Azure AD, the user or admin would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : NO
```

<span data-ttu-id="6acee-153">Se a saída for "AzureAdJoined : NO", ignore as seguintes diretrizes.</span><span class="sxs-lookup"><span data-stu-id="6acee-153">If the output is "AzureAdJoined : NO", ignore the following guidance.</span></span>

<span data-ttu-id="6acee-154">Usuário: se o dispositivo for ingressado no Azure AD, um usuário poderá desagrecar o dispositivo das configurações.</span><span class="sxs-lookup"><span data-stu-id="6acee-154">User: If the device is Azure AD joined, a user can unjoin the device from the settings.</span></span> <span data-ttu-id="6acee-155">Verifique se há uma conta de administrador local no dispositivo antes de desatar o dispositivo do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="6acee-155">Verify that there is a local administrator account on the device before unjoining the device from Azure AD.</span></span> <span data-ttu-id="6acee-156">A conta de administrador local é necessária para entrar novamente no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6acee-156">The local administrator account is required to sign back into the device.</span></span>

<span data-ttu-id="6acee-157">Administrador: se o administrador da organização quiser desagrecar os dispositivos dos usuários que estão ingressados no Azure AD, eles poderão fazer isso executando o seguinte comando em cada um dos dispositivos usando um mecanismo como a Política de Grupo.</span><span class="sxs-lookup"><span data-stu-id="6acee-157">Admin: If the organization's admin wants to unjoin the users' devices that are Azure AD–joined, they can do so by running the following command on each of the devices by using a mechanism such as Group Policy.</span></span> <span data-ttu-id="6acee-158">O administrador deve verificar se há uma conta de administrador local no dispositivo antes de desatar o dispositivo do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="6acee-158">The admin must verify that there is a local administrator account on the device before unjoining the device from Azure AD.</span></span> <span data-ttu-id="6acee-159">A conta de administrador local é necessária para entrar novamente no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6acee-159">The local administrator account is needed to sign back into the device.</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

<span data-ttu-id="6acee-160">O comando anterior só precisa ser executado uma vez em um contexto administrativo no Windows dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6acee-160">The preceding command only needs to be run once in an administrative context on the Windows device.</span></span> 

### <a name="azure-ad-joinre-registration"></a><span data-ttu-id="6acee-161">Azure AD Join/Re-Registration</span><span class="sxs-lookup"><span data-stu-id="6acee-161">Azure AD Join/Re-Registration</span></span>

<span data-ttu-id="6acee-162">O usuário pode ingressar o dispositivo no Azure AD Windows configurações: **Configurações > Contas > Access Work or School > Conexão**.</span><span class="sxs-lookup"><span data-stu-id="6acee-162">The user can join the device to Azure AD from Windows settings: **Settings > Accounts > Access Work Or School > Connect**.</span></span>
 

## <a name="azure-ad-registered-company-owned"></a><span data-ttu-id="6acee-163">Azure AD Registered (Empresa de propriedade)</span><span class="sxs-lookup"><span data-stu-id="6acee-163">Azure AD Registered (Company owned)</span></span>

<span data-ttu-id="6acee-164">Para determinar se o dispositivo Windows 10 é registrado no Azure AD, execute o seguinte comando no dispositivo:</span><span class="sxs-lookup"><span data-stu-id="6acee-164">To determine whether the Windows 10 device is Azure AD–registered, run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="6acee-165">Se o dispositivo for Registrado no Azure AD, você verá a seguinte saída:</span><span class="sxs-lookup"><span data-stu-id="6acee-165">If the device is Azure AD Registered, you would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| User State                                                           |
+----------------------------------------------------------------------+
           WorkplaceJoined : YES
          WamDefaultSet : NO
          WamDefaultAuthority : organizations
```

<span data-ttu-id="6acee-166">Para remover a conta existente registrada no Azure AD no dispositivo:</span><span class="sxs-lookup"><span data-stu-id="6acee-166">To remove the existing Azure AD-registered account on the device:</span></span>

- <span data-ttu-id="6acee-167">Para remover a conta registrada no Azure AD no dispositivo, use CleanupWPJ, uma ferramenta que você pode baixar [ aqui:CleanupWPJ.zip](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip).</span><span class="sxs-lookup"><span data-stu-id="6acee-167">To remove the Azure AD–registered account on the device, use CleanupWPJ, a tool that you can download from here: [CleanupWPJ.zip](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip).</span></span>

- <span data-ttu-id="6acee-168">Extraia o arquivo ZIP e execute **WPJCleanup.cmd**.</span><span class="sxs-lookup"><span data-stu-id="6acee-168">Extract the ZIP file and run **WPJCleanup.cmd**.</span></span> <span data-ttu-id="6acee-169">Esta ferramenta iniciará o executável correto com base na versão Windows no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6acee-169">This tool will launch the right executable based on the version of Windows on the device.</span></span>

- <span data-ttu-id="6acee-170">Usando um mecanismo como a Política de Grupo, o administrador pode executar o comando no dispositivo no contexto de qualquer usuário conectado ao dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6acee-170">By using a mechanism like Group Policy, the admin can run the command on the device in the context of any user who is signed in on the device.</span></span>

<span data-ttu-id="6acee-171">Para desabilitar solicitações do Gerenciador de Contas da Web para registrar o dispositivo no Azure AD, adicione esse valor do Registro:</span><span class="sxs-lookup"><span data-stu-id="6acee-171">To disable Web Account Manager prompts to register the device in Azure AD, add this registry value:</span></span> 

- <span data-ttu-id="6acee-172">Local: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin</span><span class="sxs-lookup"><span data-stu-id="6acee-172">Location: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin</span></span>
- <span data-ttu-id="6acee-173">Tipo: DWORD (32 bits)</span><span class="sxs-lookup"><span data-stu-id="6acee-173">Type: DWORD (32 bit)</span></span>
- <span data-ttu-id="6acee-174">Nome: BlockAADWorkplaceJoin</span><span class="sxs-lookup"><span data-stu-id="6acee-174">Name: BlockAADWorkplaceJoin</span></span>
- <span data-ttu-id="6acee-175">Dados de valor: 1</span><span class="sxs-lookup"><span data-stu-id="6acee-175">Value data: 1</span></span>

<span data-ttu-id="6acee-176">A presença desse valor do Registro deve bloquear a participação no local de trabalho e impedir que os usuários visem prompts para ingressar no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6acee-176">The presence of this registry value should block workplace join and prevent users from seeing prompts to join the device.</span></span>

## <a name="android"></a><span data-ttu-id="6acee-177">Android</span><span class="sxs-lookup"><span data-stu-id="6acee-177">Android</span></span>

<span data-ttu-id="6acee-178">Para Android, os usuários precisarão registrar e registrar seus dispositivos de novo.</span><span class="sxs-lookup"><span data-stu-id="6acee-178">For Android, users will need to unregister and re-register their devices.</span></span> <span data-ttu-id="6acee-179">Isso pode ser feito por meio do aplicativo Microsoft Authenticator ou do Portal da Empresa aplicativo.</span><span class="sxs-lookup"><span data-stu-id="6acee-179">This can be done via the Microsoft Authenticator app or the Company Portal app.</span></span> 

- <span data-ttu-id="6acee-180">No aplicativo Microsoft Authenticator, os usuários podem ir **Configurações > Registro de Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="6acee-180">From the Microsoft Authenticator app, users can go to **Settings > Device Registration**.</span></span> <span data-ttu-id="6acee-181">A partir daí, os usuários podem se registrar e registrar seus dispositivos de novo.</span><span class="sxs-lookup"><span data-stu-id="6acee-181">From there users can unregister and re-register their device.</span></span>
 
- <span data-ttu-id="6acee-182">Na Portal da Empresa, os usuários podem ir até a guia **Dispositivos** e remover o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6acee-182">From the Company Portal, users can go to **Devices** tab and remove the device.</span></span> <span data-ttu-id="6acee-183">Depois disso, re-inscreva o dispositivo usando Portal da Empresa.</span><span class="sxs-lookup"><span data-stu-id="6acee-183">After that, re-enroll the device by using Company Portal.</span></span>
 
- <span data-ttu-id="6acee-184">Os usuários também podem registrar-se e re-registrar removendo a conta da página de configurações da conta e, em seguida, adicionando a conta de trabalho.</span><span class="sxs-lookup"><span data-stu-id="6acee-184">Users can also unregister and re-register by removing the account from the account settings page and then re-adding the work account.</span></span>

<span data-ttu-id="6acee-185">Para não registrar e registrar o dispositivo no Android usando o Microsoft Authenticator app:</span><span class="sxs-lookup"><span data-stu-id="6acee-185">To unregister and re-register the device on Android by using the Microsoft Authenticator app:</span></span>

1.  <span data-ttu-id="6acee-186">Abra o Microsoft Authenticator aplicativo e vá para **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="6acee-186">Open the Microsoft Authenticator app and go to **Settings**.</span></span>
2.  <span data-ttu-id="6acee-187">Selecione **Registro de dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="6acee-187">Select **Device registration**.</span></span>
3.  <span data-ttu-id="6acee-188">Desaconselhe o dispositivo **selecionando Unregister**.</span><span class="sxs-lookup"><span data-stu-id="6acee-188">Unregister the device by selecting **Unregister**.</span></span>
4.  <span data-ttu-id="6acee-189">Para **registro de dispositivo,** registre o dispositivo digitando seu endereço de email e selecione **Registrar**.</span><span class="sxs-lookup"><span data-stu-id="6acee-189">For **Device registration**, re-register the device by typing your email address, and then select **Register**.</span></span>

<span data-ttu-id="6acee-190">Para não registrar e registrar um dispositivo Android com a página Configurações Android:</span><span class="sxs-lookup"><span data-stu-id="6acee-190">To unregister and re-register an Android device with the Android Settings page:</span></span>

1.  <span data-ttu-id="6acee-191">Abra **o dispositivo Configurações** e vá para **Contas**.</span><span class="sxs-lookup"><span data-stu-id="6acee-191">Open **Device Settings** and go to **Accounts**.</span></span>
2.  <span data-ttu-id="6acee-192">Selecione a conta de trabalho que você deseja registrar e selecione **Remover conta**.</span><span class="sxs-lookup"><span data-stu-id="6acee-192">Select the work account that you want to re-register and select **Remove account**.</span></span>
3.  <span data-ttu-id="6acee-193">Depois que a conta for removida, na página **Contas,** selecione **Adicionar Conta > Conta de Trabalho**.</span><span class="sxs-lookup"><span data-stu-id="6acee-193">After the account is removed, from the **Accounts** page, select **Add Account > Work account**.</span></span>
4.  <span data-ttu-id="6acee-194">Para **Ingressar no Local de Trabalho,** digite seu endereço de email e selecione **Ingressar** para concluir o registro do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6acee-194">For **Workplace Join**, type your email address and select **Join** to complete registering the device.</span></span>

<span data-ttu-id="6acee-195">Para não registrar e registrar o dispositivo no Android de Portal da Empresa:</span><span class="sxs-lookup"><span data-stu-id="6acee-195">To unregister and re-register the device on Android from Company Portal:</span></span>

1.  <span data-ttu-id="6acee-196">Iniciar Portal da Empresa e vá para **a guia Dispositivos.**</span><span class="sxs-lookup"><span data-stu-id="6acee-196">Launch Company Portal and go to **Devices** tab.</span></span>
2.  <span data-ttu-id="6acee-197">Selecione o dispositivo para ver os detalhes do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6acee-197">Select the device to see the device details.</span></span>
3.  <span data-ttu-id="6acee-198">No menu releitos (três pontos), selecione **Remover** Dispositivo e conclua a remoção confirmando na caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="6acee-198">From the ellipses (three dots) menu, select **Remove Device**, and complete the removal by confirming in the dialog.</span></span>
4.  <span data-ttu-id="6acee-199">Agora você deve estar conectado ao aplicativo Portal da Empresa.</span><span class="sxs-lookup"><span data-stu-id="6acee-199">You should now be logged out of the Company Portal app.</span></span> <span data-ttu-id="6acee-200">Selecione **Entrar para** registrar o dispositivo de novo.</span><span class="sxs-lookup"><span data-stu-id="6acee-200">Select **Sign in** to re-register the device.</span></span>

<span data-ttu-id="6acee-201">Para obter mais informações sobre as ações necessárias durante a fase de migração dessa carga de trabalho ou impacto na administração ou no uso, revise as informações sobre o Azure Active Directory [(Azure AD)](ms-cloud-germany-transition-azure-ad.md)em Informações adicionais do Azure AD para a migração do Microsoft Cloud Deutschland .</span><span class="sxs-lookup"><span data-stu-id="6acee-201">For more information about any actions required during the migration phase of this workload, or impact to administration or usage, review the information about Azure Active Directory (Azure AD) in [Additional Azure AD information for the migration from Microsoft Cloud Deutschland](ms-cloud-germany-transition-azure-ad.md).</span></span>

## <a name="ios"></a><span data-ttu-id="6acee-202">iOS</span><span class="sxs-lookup"><span data-stu-id="6acee-202">iOS</span></span>

<span data-ttu-id="6acee-203">Em dispositivos iOS, um usuário precisará remover manualmente todas as contas armazenadas em cache do Microsoft Authenticator, desa inscrever o dispositivo e sair de qualquer aplicativo nativo no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6acee-203">On iOS devices, a user will need to manually remove any cached accounts from the Microsoft Authenticator, unregister the device, and sign out from any native apps on the device.</span></span>

### <a name="step-1-if-present-remove-the-account-from-the-microsoft-authenticator-app"></a><span data-ttu-id="6acee-204">Etapa 1: se presente, remova a conta do Microsoft Authenticator app</span><span class="sxs-lookup"><span data-stu-id="6acee-204">Step 1: If present, remove the account from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="6acee-205">Toque na conta no aplicativo Microsoft Authenticator.</span><span class="sxs-lookup"><span data-stu-id="6acee-205">Tap the account in the Microsoft Authenticator app.</span></span>
2. <span data-ttu-id="6acee-206">Toque no **Configurações** no canto superior direito.</span><span class="sxs-lookup"><span data-stu-id="6acee-206">Tap the **Settings** icon in the top-right corner.</span></span> <span data-ttu-id="6acee-207">Se você não vir o **ícone** Configurações, talvez não use a versão mais recente do Microsoft Authenticator.</span><span class="sxs-lookup"><span data-stu-id="6acee-207">If you don't see the **Settings** icon, you might not be using the latest version of Microsoft Authenticator.</span></span>
3. <span data-ttu-id="6acee-208">Toque no **botão Remover conta.**</span><span class="sxs-lookup"><span data-stu-id="6acee-208">Tap the **Remove account** button.</span></span>
4. <span data-ttu-id="6acee-209">Toque **em Todos os aplicativos neste dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="6acee-209">Tap **All apps on this device**.</span></span>
 
### <a name="step-2-unregister-the-device-from-the-microsoft-authenticator-app"></a><span data-ttu-id="6acee-210">Etapa 2: Desaconselhe o dispositivo do Microsoft Authenticator app</span><span class="sxs-lookup"><span data-stu-id="6acee-210">Step 2: Unregister the device from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="6acee-211">Toque no ícone de menu no canto superior direito.</span><span class="sxs-lookup"><span data-stu-id="6acee-211">Tap the menu icon in the top-right corner.</span></span>
2. <span data-ttu-id="6acee-212">Toque **Configurações** e, em seguida, **Registro de Dispositivo.**</span><span class="sxs-lookup"><span data-stu-id="6acee-212">Tap **Settings** and then **Device Registration**.</span></span>
4. <span data-ttu-id="6acee-213">Se sua conta for mostrada, toque em Dispositivo de Registro **Não-Registro** e **Continue** na caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="6acee-213">If your account is shown, tap **Unregister device** and **Continue** in the dialog.</span></span> <span data-ttu-id="6acee-214">Você não deve ver nenhuma conta depois disso.</span><span class="sxs-lookup"><span data-stu-id="6acee-214">You should see no account after that.</span></span>
 
### <a name="step-3-sign-out-from-individual-apps-if-necessary"></a><span data-ttu-id="6acee-215">Etapa 3: Sair de aplicativos individuais, se necessário</span><span class="sxs-lookup"><span data-stu-id="6acee-215">Step 3: Sign out from individual apps if necessary</span></span>

<span data-ttu-id="6acee-216">Os usuários podem ir para aplicativos individuais como Outlook, Teams e OneDrive e remover contas desses aplicativos.</span><span class="sxs-lookup"><span data-stu-id="6acee-216">Users can go to individual apps like Outlook, Teams, and OneDrive, and remove accounts from those apps.</span></span>

## <a name="more-information"></a><span data-ttu-id="6acee-217">Mais informações</span><span class="sxs-lookup"><span data-stu-id="6acee-217">More information</span></span>

<span data-ttu-id="6acee-218">Como começar:</span><span class="sxs-lookup"><span data-stu-id="6acee-218">Getting started:</span></span>

- [<span data-ttu-id="6acee-219">Migração do Microsoft Cloud Deutschland para serviços Office 365 nas novas regiões do datacenter alemão</span><span class="sxs-lookup"><span data-stu-id="6acee-219">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="6acee-220">Assistência de Migração do Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="6acee-220">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="6acee-221">Como aceitar a migração</span><span class="sxs-lookup"><span data-stu-id="6acee-221">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="6acee-222">Experiência do cliente durante a migração</span><span class="sxs-lookup"><span data-stu-id="6acee-222">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="6acee-223">Movendo-se pela transição:</span><span class="sxs-lookup"><span data-stu-id="6acee-223">Moving through the transition:</span></span>

- [<span data-ttu-id="6acee-224">Ações e impactos das fases de migração</span><span class="sxs-lookup"><span data-stu-id="6acee-224">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="6acee-225">Pré-trabalho adicional</span><span class="sxs-lookup"><span data-stu-id="6acee-225">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="6acee-226">Informações adicionais para [o Azure AD,](ms-cloud-germany-transition-azure-ad.md) [dispositivos, experiências](ms-cloud-germany-transition-add-experience.md)e [AD FS](ms-cloud-germany-transition-add-adfs.md). [](ms-cloud-germany-transition-add-devices.md)</span><span class="sxs-lookup"><span data-stu-id="6acee-226">Additional information for [Azure AD](ms-cloud-germany-transition-azure-ad.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="6acee-227">Aplicativos de nuvem:</span><span class="sxs-lookup"><span data-stu-id="6acee-227">Cloud apps:</span></span>

- [<span data-ttu-id="6acee-228">Informações do programa de migração do Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="6acee-228">Dynamics 365 migration program information</span></span>](/dynamics365/get-started/migrate-data-german-region)
- [<span data-ttu-id="6acee-229">Informações do programa de migração do Power BI</span><span class="sxs-lookup"><span data-stu-id="6acee-229">Power BI migration program information</span></span>](/power-bi/admin/service-admin-migrate-data-germany)
- [<span data-ttu-id="6acee-230">Introdução à atualização do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6acee-230">Getting started with your Microsoft Teams upgrade</span></span>](/microsoftteams/upgrade-start-here)