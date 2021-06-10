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
ms.openlocfilehash: 27426a26befab85bf62a0a143861e447dd722724
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861294"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="8cec1-103">Informações adicionais do dispositivo para a migração do Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="8cec1-103">Additional device information for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="8cec1-104">Os dispositivos ingressados e registrados no Azure AD conectados ao Microsoft Cloud Deutschland devem ser migrados após a fase 9 e antes da fase 10.</span><span class="sxs-lookup"><span data-stu-id="8cec1-104">Azure AD joined and registered devices connected to Microsoft Cloud Deutschland must be migrated after phase 9 and before phase 10.</span></span> <span data-ttu-id="8cec1-105">A migração de um dispositivo depende do tipo de dispositivo, sistema operacional e relação AAD.</span><span class="sxs-lookup"><span data-stu-id="8cec1-105">The migration of a device depends on the devices type, operating system and AAD relation.</span></span> 

## <a name="frequently-asked-questions"></a><span data-ttu-id="8cec1-106">Perguntas frequentes</span><span class="sxs-lookup"><span data-stu-id="8cec1-106">Frequently asked questions</span></span>

<span data-ttu-id="8cec1-107">**Como posso saber se minha organização foi afetada?**</span><span class="sxs-lookup"><span data-stu-id="8cec1-107">**How can I tell if my organization is affected?**</span></span>

<span data-ttu-id="8cec1-108">Os administradores devem verificar se eles têm dispositivos registrados ou `https://portal.microsoftazure.de` ingressados no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="8cec1-108">Administrators should check `https://portal.microsoftazure.de` to determine if they have any registered or Azure AD joined devices.</span></span> <span data-ttu-id="8cec1-109">Se sua organização tiver dispositivos registrados, você será afetado.</span><span class="sxs-lookup"><span data-stu-id="8cec1-109">If your organization has registered devices, you're affected.</span></span>

<span data-ttu-id="8cec1-110">**Qual é o impacto nos meus usuários?**</span><span class="sxs-lookup"><span data-stu-id="8cec1-110">**What is the impact on my users?**</span></span>

<span data-ttu-id="8cec1-111">Os usuários de um dispositivo registrado não poderão mais entrar após a conclusão da fase [10](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) de migração e os pontos de extremidade do Microsoft Cloud Deutschland foram desabilitados.</span><span class="sxs-lookup"><span data-stu-id="8cec1-111">Users from a registered device will no longer be able to sign in after [migration phase 10](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) has been completed and the endpoints for Microsoft Cloud Deutschland have been disabled.</span></span>  

<span data-ttu-id="8cec1-112">Verifique se todos os seus dispositivos estão registrados com o ponto de extremidade em todo o mundo antes que sua organização seja desconectada do Microsoft Cloud Deutschland.</span><span class="sxs-lookup"><span data-stu-id="8cec1-112">Ensure that all of your devices are registered with the worldwide endpoint before your organization is disconnected from Microsoft Cloud Deutschland.</span></span>
  
<span data-ttu-id="8cec1-113">**Quando meus usuários registram seus dispositivos de novo?**</span><span class="sxs-lookup"><span data-stu-id="8cec1-113">**When do my users re-register their devices?**</span></span>

<span data-ttu-id="8cec1-114">É fundamental para o seu sucesso que você apenas não registre e registre seus dispositivos após a conclusão da [fase 9.](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization)</span><span class="sxs-lookup"><span data-stu-id="8cec1-114">It's critical to your success that you only unregister and re-register your devices after [phase 9](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) has been completed.</span></span> <span data-ttu-id="8cec1-115">Você deve concluir o recadastramento antes da fase 10 ser iniciada, caso contrário, poderá perder o acesso ao dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8cec1-115">You must finish the re-registration before phase 10 starts, otherwise you could lose access to your device.</span></span>

<span data-ttu-id="8cec1-116">**Como restaurar meu estado de dispositivo após a migração?**</span><span class="sxs-lookup"><span data-stu-id="8cec1-116">**How do I restore my device state after migration?**</span></span>

<span data-ttu-id="8cec1-117">Para dispositivos de Windows de propriedade da empresa registrados no Azure AD, os administradores poderão gerenciar a migração desses dispositivos por meio de fluxos de trabalho disparados remotamente que não registrarão os estados do dispositivo antigo.</span><span class="sxs-lookup"><span data-stu-id="8cec1-117">For company-owned Windows devices that are registered with Azure AD, administrators will be able to manage the migration of these devices through remotely triggered workflows that will unregister the old device states.</span></span>
  
<span data-ttu-id="8cec1-118">Para todos os outros dispositivos, incluindo Windows pessoais registrados no Azure AD, o usuário final deve executar essas etapas manualmente.</span><span class="sxs-lookup"><span data-stu-id="8cec1-118">For all other devices, including personal Windows devices that are registered in Azure AD, the end user must perform these steps manually.</span></span> <span data-ttu-id="8cec1-119">Para dispositivos ingressados no Azure AD, os usuários precisam ter uma conta de administrador local para não registrar e, em seguida, registrar seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="8cec1-119">For Azure AD–joined devices, users need to have a local administrator account to unregister and then re-register their devices.</span></span>

<span data-ttu-id="8cec1-120">Consulte instruções detalhadas sobre como restaurar com êxito os estados do dispositivo abaixo.</span><span class="sxs-lookup"><span data-stu-id="8cec1-120">Please refer to detailed instructions for how to successfully restore device states below.</span></span> 
 
<span data-ttu-id="8cec1-121">**Como saber se todos os meus dispositivos estão registrados na nuvem pública?**</span><span class="sxs-lookup"><span data-stu-id="8cec1-121">**How do I know that all my devices are registered in the public cloud?**</span></span>

<span data-ttu-id="8cec1-122">Para verificar se seus dispositivos estão registrados na nuvem pública, você deve exportar e baixar a lista de dispositivos do portal do Azure AD para uma planilha Excel.</span><span class="sxs-lookup"><span data-stu-id="8cec1-122">To check whether your devices are registered in the public cloud, you should export and download the list of devices from the Azure AD portal to an Excel spreadsheet.</span></span> <span data-ttu-id="8cec1-123">Em seguida, filtre os dispositivos registrados (usando a coluna _registeredTime)_ após a fase de migração [Separate from Microsoft Cloud Deutschland.](ms-cloud-germany-transition.md#how-is-the-migration-organized)</span><span class="sxs-lookup"><span data-stu-id="8cec1-123">Then, filter the devices that are registered (by using the _registeredTime_ column) after the [Separate from Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>

## <a name="additional-considerations"></a><span data-ttu-id="8cec1-124">Considerações adicionais</span><span class="sxs-lookup"><span data-stu-id="8cec1-124">Additional considerations</span></span>
<span data-ttu-id="8cec1-125">O registro do dispositivo é desativado após a migração do locatário e não pode ser habilitado ou desabilitado.</span><span class="sxs-lookup"><span data-stu-id="8cec1-125">Device registration is deactivated after migration of the tenant and cannot be enabled or disabled.</span></span> 

<span data-ttu-id="8cec1-126">Se o Intune não for usado, entre em sua assinatura e execute este comando para reativá-lo:</span><span class="sxs-lookup"><span data-stu-id="8cec1-126">If Intune is not used, sign in to your subscription and run this command to re-activate the option:</span></span>

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```
<span data-ttu-id="8cec1-127">**IMPORTANTE:** A entidade de serviço do Intune será habilitada após a migração do comércio, o que implica na ativação do Registro de Dispositivo do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="8cec1-127">**IMPORTANT:** The Intune service principal will be enabled after commerce migration, which implies the activation of Azure AD Device Registration.</span></span> <span data-ttu-id="8cec1-128">Se você bloqueou o Registro de Dispositivo do Azure AD antes da migração, deverá desabilitar a entidade de serviço do Intune com o PowerShell para desabilitar o Registro de Dispositivo do Azure AD com o portal do Azure AD novamente.</span><span class="sxs-lookup"><span data-stu-id="8cec1-128">If you blocked Azure AD Device Registration before migration, you must disable the Intune service principal with PowerShell to disable Azure AD Device Registration with the Azure AD portal again.</span></span> <span data-ttu-id="8cec1-129">Você pode desabilitar a entidade de serviço do Intune com esse comando no Azure Active Directory PowerShell para Graph módulo.</span><span class="sxs-lookup"><span data-stu-id="8cec1-129">You can disable the Intune service principal with this command in the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```


## <a name="azure-ad-join"></a><span data-ttu-id="8cec1-130">Ingressar no Azure AD</span><span class="sxs-lookup"><span data-stu-id="8cec1-130">Azure AD Join</span></span>
<span data-ttu-id="8cec1-131">Isso se aplica a Windows 10 dispositivos.</span><span class="sxs-lookup"><span data-stu-id="8cec1-131">This applies to Windows 10 devices.</span></span> 

<span data-ttu-id="8cec1-132">Se um dispositivo for ingressado no Azure AD, ele deverá ser desconectado do Azure AD e ser conectado novamente.</span><span class="sxs-lookup"><span data-stu-id="8cec1-132">If a device is Azure AD joined, it must be disconnected from Azure AD and be connected again.</span></span> 

<span data-ttu-id="8cec1-133">[![Dispositivo do Azure AD Re-Join Flow ](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png)](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="8cec1-133">[ ![Azure AD Device Re-Join Flow](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png) ](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png#lightbox)</span></span>


<span data-ttu-id="8cec1-134">Se o usuário for um administrador no dispositivo Windows 10, o usuário poderá desaconselhá-lo do Azure AD e jun-lo novamente.</span><span class="sxs-lookup"><span data-stu-id="8cec1-134">If the user is an administrator on the Windows 10 device, the user can unregister the device from Azure AD and re-join it again.</span></span> <span data-ttu-id="8cec1-135">Se ele não tiver privilégios de administrador, o usuário precisará de credenciais de uma conta de administrador local neste computador.</span><span class="sxs-lookup"><span data-stu-id="8cec1-135">If he has no administrator privileges, the user needs credentials of a local administrator account on this machine.</span></span> 


<span data-ttu-id="8cec1-136">Um Administrador pode criar uma conta de administrador local no dispositivo seguindo este caminho de configuração:</span><span class="sxs-lookup"><span data-stu-id="8cec1-136">An Administrator can create an local administrator account on the device following this configuration path:</span></span>

<span data-ttu-id="8cec1-137">*Configurações > Contas > Outras Contas > Credenciais desconhecidas > Adicionar usuário sem Microsoft-Account*</span><span class="sxs-lookup"><span data-stu-id="8cec1-137">*Settings > Accounts > Other Accounts > Credentials unknown > Add user without Microsoft-Account*</span></span>

### <a name="step-1-determine-if-the-device-is-azure-id-joined"></a><span data-ttu-id="8cec1-138">Etapa 1: Determinar se o dispositivo está ingressado no Azure ID</span><span class="sxs-lookup"><span data-stu-id="8cec1-138">Step 1: Determine if the device is Azure ID joined</span></span>
1.  <span data-ttu-id="8cec1-139">Entre com usuários Email e senha.</span><span class="sxs-lookup"><span data-stu-id="8cec1-139">Sign In with users E-mail and password.</span></span>
2.  <span data-ttu-id="8cec1-140">Vá para Configurações > Contas > Acessar Trabalho ou Escola.</span><span class="sxs-lookup"><span data-stu-id="8cec1-140">Go to Settings > Accounts > Access Work Or School.</span></span> 
3.  <span data-ttu-id="8cec1-141">Procure um usuário na lista com **conectado a ... 's Azure AD**.</span><span class="sxs-lookup"><span data-stu-id="8cec1-141">Look for a user in the list with **connected to … ‘s Azure AD**.</span></span> 
4.  <span data-ttu-id="8cec1-142">Se houver um usuário conectado, prossiga com a Etapa 2.</span><span class="sxs-lookup"><span data-stu-id="8cec1-142">If a connected user exists, proceed with Step 2.</span></span> <span data-ttu-id="8cec1-143">Caso não seja necessário, nenhuma ação será necessária.</span><span class="sxs-lookup"><span data-stu-id="8cec1-143">If not, no further action is required.</span></span>
### <a name="step-2-disconnect-the-device-from-azure-ad"></a><span data-ttu-id="8cec1-144">Etapa 2: desconectar o dispositivo do Azure AD</span><span class="sxs-lookup"><span data-stu-id="8cec1-144">Step 2: Disconnect the device from Azure AD</span></span>
1.  <span data-ttu-id="8cec1-145">Toque **em Desconectar** na conta de trabalho ou de estudante conectada.</span><span class="sxs-lookup"><span data-stu-id="8cec1-145">Tap **Disconnect** on the connected work or School Account.</span></span> 
2.  <span data-ttu-id="8cec1-146">Confirme a desconexão duas vezes.</span><span class="sxs-lookup"><span data-stu-id="8cec1-146">Confirm the disconnect twice.</span></span> 
3.  <span data-ttu-id="8cec1-147">Insira o nome de usuário e a senha do administrador local.</span><span class="sxs-lookup"><span data-stu-id="8cec1-147">Enter the local administrator username and password.</span></span> <span data-ttu-id="8cec1-148">O dispositivo está desconectado.</span><span class="sxs-lookup"><span data-stu-id="8cec1-148">The device is disconnected.</span></span>
4.  <span data-ttu-id="8cec1-149">Reinicie o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8cec1-149">Restart the device.</span></span>
### <a name="step-3-join-the-device-to-azure-ad"></a><span data-ttu-id="8cec1-150">Etapa 3: Associar o dispositivo ao Azure AD</span><span class="sxs-lookup"><span data-stu-id="8cec1-150">Step 3: Join the device to Azure AD</span></span>
1.  <span data-ttu-id="8cec1-151">o usuário entrar com as credenciais do administrador local</span><span class="sxs-lookup"><span data-stu-id="8cec1-151">the user signs in with the credentials of the local administrator</span></span>
2.  <span data-ttu-id="8cec1-152">Vá para o **Configurações** **contas em seguida,** **acesse Trabalho ou Escola**</span><span class="sxs-lookup"><span data-stu-id="8cec1-152">Go to **Settings** then **Accounts** then **Access Work Or School**</span></span>
3.  <span data-ttu-id="8cec1-153">Toque **Conexão**</span><span class="sxs-lookup"><span data-stu-id="8cec1-153">Tap **Connect**</span></span>
4.  <span data-ttu-id="8cec1-154">**IMPORTANTE**: Toque **em Ingressar no Azure AD**</span><span class="sxs-lookup"><span data-stu-id="8cec1-154">**IMPORTANT**: Tap **Join to Azure AD**</span></span>
5.  <span data-ttu-id="8cec1-155">Insira o endereço de email e a senha do usuário.</span><span class="sxs-lookup"><span data-stu-id="8cec1-155">Enter the e-mail address and password of the user.</span></span> <span data-ttu-id="8cec1-156">O dispositivo está conectado</span><span class="sxs-lookup"><span data-stu-id="8cec1-156">The device is connected</span></span>
6.  <span data-ttu-id="8cec1-157">Reiniciar o dispositivo</span><span class="sxs-lookup"><span data-stu-id="8cec1-157">Restart the device</span></span> 
7.  <span data-ttu-id="8cec1-158">entrar com seu endereço de email e senha</span><span class="sxs-lookup"><span data-stu-id="8cec1-158">sign with your e-mail address and password</span></span>

## <a name="azure-ad-registered-company-owned"></a><span data-ttu-id="8cec1-159">Azure AD Registered (Empresa de propriedade)</span><span class="sxs-lookup"><span data-stu-id="8cec1-159">Azure AD Registered (Company owned)</span></span>

<span data-ttu-id="8cec1-160">Para determinar se o dispositivo Windows 10 é registrado no Azure AD, execute o seguinte comando no dispositivo:</span><span class="sxs-lookup"><span data-stu-id="8cec1-160">To determine whether the Windows 10 device is Azure AD–registered, run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="8cec1-161">Se o dispositivo for Registrado no Azure AD, você verá a seguinte saída:</span><span class="sxs-lookup"><span data-stu-id="8cec1-161">If the device is Azure AD Registered, you would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| User State                                                           |
+----------------------------------------------------------------------+
           WorkplaceJoined : YES
          WamDefaultSet : NO
          WamDefaultAuthority : organizations
```

<span data-ttu-id="8cec1-162">Para remover a conta existente registrada no Azure AD no dispositivo:</span><span class="sxs-lookup"><span data-stu-id="8cec1-162">To remove the existing Azure AD-registered account on the device:</span></span>

- <span data-ttu-id="8cec1-163">Para remover a conta registrada no Azure AD no dispositivo, use CleanupWPJ, uma ferramenta que você pode baixar [ aqui:CleanupWPJ.zip](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip).</span><span class="sxs-lookup"><span data-stu-id="8cec1-163">To remove the Azure AD–registered account on the device, use CleanupWPJ, a tool that you can download from here: [CleanupWPJ.zip](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip).</span></span>

- <span data-ttu-id="8cec1-164">Extraia o arquivo ZIP e execute **WPJCleanup.cmd**.</span><span class="sxs-lookup"><span data-stu-id="8cec1-164">Extract the ZIP file and run **WPJCleanup.cmd**.</span></span> <span data-ttu-id="8cec1-165">Esta ferramenta iniciará o executável correto com base na versão Windows no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8cec1-165">This tool will launch the right executable based on the version of Windows on the device.</span></span>

- <span data-ttu-id="8cec1-166">Usando um mecanismo como a Política de Grupo, o administrador pode executar o comando no dispositivo no contexto de qualquer usuário conectado ao dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8cec1-166">By using a mechanism like Group Policy, the admin can run the command on the device in the context of any user who is signed in on the device.</span></span>

<span data-ttu-id="8cec1-167">Para desabilitar solicitações do Gerenciador de Contas da Web para registrar o dispositivo no Azure AD, adicione esse valor do Registro:</span><span class="sxs-lookup"><span data-stu-id="8cec1-167">To disable Web Account Manager prompts to register the device in Azure AD, add this registry value:</span></span> 

- <span data-ttu-id="8cec1-168">Local: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin</span><span class="sxs-lookup"><span data-stu-id="8cec1-168">Location: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin</span></span>
- <span data-ttu-id="8cec1-169">Tipo: DWORD (32 bits)</span><span class="sxs-lookup"><span data-stu-id="8cec1-169">Type: DWORD (32 bit)</span></span>
- <span data-ttu-id="8cec1-170">Nome: BlockAADWorkplaceJoin</span><span class="sxs-lookup"><span data-stu-id="8cec1-170">Name: BlockAADWorkplaceJoin</span></span>
- <span data-ttu-id="8cec1-171">Dados de valor: 1</span><span class="sxs-lookup"><span data-stu-id="8cec1-171">Value data: 1</span></span>

<span data-ttu-id="8cec1-172">A presença desse valor do Registro deve bloquear a participação no local de trabalho e impedir que os usuários visem prompts para ingressar no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8cec1-172">The presence of this registry value should block workplace join and prevent users from seeing prompts to join the device.</span></span>

## <a name="android"></a><span data-ttu-id="8cec1-173">Android</span><span class="sxs-lookup"><span data-stu-id="8cec1-173">Android</span></span>

<span data-ttu-id="8cec1-174">Para Android, os usuários precisarão registrar e registrar seus dispositivos de novo.</span><span class="sxs-lookup"><span data-stu-id="8cec1-174">For Android, users will need to unregister and re-register their devices.</span></span> <span data-ttu-id="8cec1-175">Isso pode ser feito por meio do aplicativo Microsoft Authenticator ou do Portal da Empresa aplicativo.</span><span class="sxs-lookup"><span data-stu-id="8cec1-175">This can be done via the Microsoft Authenticator app or the Company Portal app.</span></span> 

- <span data-ttu-id="8cec1-176">No aplicativo Microsoft Authenticator, os usuários podem ir **Configurações > Registro de Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="8cec1-176">From the Microsoft Authenticator app, users can go to **Settings > Device Registration**.</span></span> <span data-ttu-id="8cec1-177">A partir daí, os usuários podem se registrar e registrar seus dispositivos de novo.</span><span class="sxs-lookup"><span data-stu-id="8cec1-177">From there users can unregister and re-register their device.</span></span>
 
- <span data-ttu-id="8cec1-178">Na Portal da Empresa, os usuários podem ir até a guia **Dispositivos** e remover o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8cec1-178">From the Company Portal, users can go to **Devices** tab and remove the device.</span></span> <span data-ttu-id="8cec1-179">Depois disso, re-inscreva o dispositivo usando Portal da Empresa.</span><span class="sxs-lookup"><span data-stu-id="8cec1-179">After that, re-enroll the device by using Company Portal.</span></span>
 
- <span data-ttu-id="8cec1-180">Os usuários também podem registrar-se e re-registrar removendo a conta da página de configurações da conta e, em seguida, adicionando a conta de trabalho.</span><span class="sxs-lookup"><span data-stu-id="8cec1-180">Users can also unregister and re-register by removing the account from the account settings page and then re-adding the work account.</span></span>

<span data-ttu-id="8cec1-181">Para não registrar e registrar o dispositivo no Android usando o Microsoft Authenticator app:</span><span class="sxs-lookup"><span data-stu-id="8cec1-181">To unregister and re-register the device on Android by using the Microsoft Authenticator app:</span></span>

1.  <span data-ttu-id="8cec1-182">Abra o Microsoft Authenticator aplicativo e vá para **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="8cec1-182">Open the Microsoft Authenticator app and go to **Settings**.</span></span>
2.  <span data-ttu-id="8cec1-183">Selecione **Registro de dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="8cec1-183">Select **Device registration**.</span></span>
3.  <span data-ttu-id="8cec1-184">Desaconselhe o dispositivo **selecionando Unregister**.</span><span class="sxs-lookup"><span data-stu-id="8cec1-184">Unregister the device by selecting **Unregister**.</span></span>
4.  <span data-ttu-id="8cec1-185">Para **registro de dispositivo,** registre o dispositivo digitando seu endereço de email e selecione **Registrar**.</span><span class="sxs-lookup"><span data-stu-id="8cec1-185">For **Device registration**, re-register the device by typing your email address, and then select **Register**.</span></span>

<span data-ttu-id="8cec1-186">Para não registrar e registrar um dispositivo Android com a página Configurações Android:</span><span class="sxs-lookup"><span data-stu-id="8cec1-186">To unregister and re-register an Android device with the Android Settings page:</span></span>

1.  <span data-ttu-id="8cec1-187">Abra **o dispositivo Configurações** e vá para **Contas**.</span><span class="sxs-lookup"><span data-stu-id="8cec1-187">Open **Device Settings** and go to **Accounts**.</span></span>
2.  <span data-ttu-id="8cec1-188">Selecione a conta de trabalho que você deseja registrar e selecione **Remover conta**.</span><span class="sxs-lookup"><span data-stu-id="8cec1-188">Select the work account that you want to re-register and select **Remove account**.</span></span>
3.  <span data-ttu-id="8cec1-189">Depois que a conta for removida, na página **Contas,** selecione **Adicionar Conta > Conta de Trabalho**.</span><span class="sxs-lookup"><span data-stu-id="8cec1-189">After the account is removed, from the **Accounts** page, select **Add Account > Work account**.</span></span>
4.  <span data-ttu-id="8cec1-190">Para **Ingressar no Local de Trabalho,** digite seu endereço de email e selecione **Ingressar** para concluir o registro do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8cec1-190">For **Workplace Join**, type your email address and select **Join** to complete registering the device.</span></span>

<span data-ttu-id="8cec1-191">Para não registrar e registrar o dispositivo no Android de Portal da Empresa:</span><span class="sxs-lookup"><span data-stu-id="8cec1-191">To unregister and re-register the device on Android from Company Portal:</span></span>

1.  <span data-ttu-id="8cec1-192">Iniciar Portal da Empresa e vá para **a guia Dispositivos.**</span><span class="sxs-lookup"><span data-stu-id="8cec1-192">Launch Company Portal and go to **Devices** tab.</span></span>
2.  <span data-ttu-id="8cec1-193">Selecione o dispositivo para ver os detalhes do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8cec1-193">Select the device to see the device details.</span></span>
3.  <span data-ttu-id="8cec1-194">No menu releitos (três pontos), selecione **Remover** Dispositivo e conclua a remoção confirmando na caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="8cec1-194">From the ellipses (three dots) menu, select **Remove Device**, and complete the removal by confirming in the dialog.</span></span>
4.  <span data-ttu-id="8cec1-195">Agora você deve estar conectado ao aplicativo Portal da Empresa.</span><span class="sxs-lookup"><span data-stu-id="8cec1-195">You should now be logged out of the Company Portal app.</span></span> <span data-ttu-id="8cec1-196">Selecione **Entrar para** registrar o dispositivo de novo.</span><span class="sxs-lookup"><span data-stu-id="8cec1-196">Select **Sign in** to re-register the device.</span></span>

<span data-ttu-id="8cec1-197">Para obter mais informações sobre as ações necessárias durante a fase de migração dessa carga de trabalho ou impacto na administração ou no uso, revise as informações sobre o Azure Active Directory [(Azure AD)](ms-cloud-germany-transition-azure-ad.md)em Informações adicionais do Azure AD para a migração do Microsoft Cloud Deutschland .</span><span class="sxs-lookup"><span data-stu-id="8cec1-197">For more information about any actions required during the migration phase of this workload, or impact to administration or usage, review the information about Azure Active Directory (Azure AD) in [Additional Azure AD information for the migration from Microsoft Cloud Deutschland](ms-cloud-germany-transition-azure-ad.md).</span></span>

## <a name="ios"></a><span data-ttu-id="8cec1-198">iOS</span><span class="sxs-lookup"><span data-stu-id="8cec1-198">iOS</span></span>

<span data-ttu-id="8cec1-199">Em dispositivos iOS, um usuário precisará remover manualmente todas as contas armazenadas em cache do Microsoft Authenticator, desa inscrever o dispositivo e sair de qualquer aplicativo nativo no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8cec1-199">On iOS devices, a user will need to manually remove any cached accounts from the Microsoft Authenticator, unregister the device, and sign out from any native apps on the device.</span></span>

### <a name="step-1-if-present-remove-the-account-from-the-microsoft-authenticator-app"></a><span data-ttu-id="8cec1-200">Etapa 1: se presente, remova a conta do Microsoft Authenticator app</span><span class="sxs-lookup"><span data-stu-id="8cec1-200">Step 1: If present, remove the account from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="8cec1-201">Toque na conta no aplicativo Microsoft Authenticator.</span><span class="sxs-lookup"><span data-stu-id="8cec1-201">Tap the account in the Microsoft Authenticator app.</span></span>
2. <span data-ttu-id="8cec1-202">Toque no **Configurações** no canto superior direito.</span><span class="sxs-lookup"><span data-stu-id="8cec1-202">Tap the **Settings** icon in the top-right corner.</span></span> <span data-ttu-id="8cec1-203">Se você não vir o **ícone** Configurações, talvez não use a versão mais recente do Microsoft Authenticator.</span><span class="sxs-lookup"><span data-stu-id="8cec1-203">If you don't see the **Settings** icon, you might not be using the latest version of Microsoft Authenticator.</span></span>
3. <span data-ttu-id="8cec1-204">Toque no **botão Remover conta.**</span><span class="sxs-lookup"><span data-stu-id="8cec1-204">Tap the **Remove account** button.</span></span>
4. <span data-ttu-id="8cec1-205">Toque **em Todos os aplicativos neste dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="8cec1-205">Tap **All apps on this device**.</span></span>
 
### <a name="step-2-unregister-the-device-from-the-microsoft-authenticator-app"></a><span data-ttu-id="8cec1-206">Etapa 2: Desaconselhe o dispositivo do Microsoft Authenticator app</span><span class="sxs-lookup"><span data-stu-id="8cec1-206">Step 2: Unregister the device from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="8cec1-207">Toque no ícone de menu no canto superior direito.</span><span class="sxs-lookup"><span data-stu-id="8cec1-207">Tap the menu icon in the top-right corner.</span></span>
2. <span data-ttu-id="8cec1-208">Toque **Configurações** e, em seguida, **Registro de Dispositivo.**</span><span class="sxs-lookup"><span data-stu-id="8cec1-208">Tap **Settings** and then **Device Registration**.</span></span>
4. <span data-ttu-id="8cec1-209">Se sua conta for mostrada, toque em Dispositivo de Registro **Não-Registro** e **Continue** na caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="8cec1-209">If your account is shown, tap **Unregister device** and **Continue** in the dialog.</span></span> <span data-ttu-id="8cec1-210">Você não deve ver nenhuma conta depois disso.</span><span class="sxs-lookup"><span data-stu-id="8cec1-210">You should see no account after that.</span></span>
 
### <a name="step-3-sign-out-from-individual-apps-if-necessary"></a><span data-ttu-id="8cec1-211">Etapa 3: Sair de aplicativos individuais, se necessário</span><span class="sxs-lookup"><span data-stu-id="8cec1-211">Step 3: Sign out from individual apps if necessary</span></span>

<span data-ttu-id="8cec1-212">Os usuários podem ir para aplicativos individuais como Outlook, Teams e OneDrive e remover contas desses aplicativos.</span><span class="sxs-lookup"><span data-stu-id="8cec1-212">Users can go to individual apps like Outlook, Teams, and OneDrive, and remove accounts from those apps.</span></span>

## <a name="more-information"></a><span data-ttu-id="8cec1-213">Mais informações</span><span class="sxs-lookup"><span data-stu-id="8cec1-213">More information</span></span>

<span data-ttu-id="8cec1-214">Como começar:</span><span class="sxs-lookup"><span data-stu-id="8cec1-214">Getting started:</span></span>

- [<span data-ttu-id="8cec1-215">Migração do Microsoft Cloud Deutschland para serviços Office 365 nas novas regiões do datacenter alemão</span><span class="sxs-lookup"><span data-stu-id="8cec1-215">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="8cec1-216">Assistência de Migração do Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="8cec1-216">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="8cec1-217">Como aceitar a migração</span><span class="sxs-lookup"><span data-stu-id="8cec1-217">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="8cec1-218">Experiência do cliente durante a migração</span><span class="sxs-lookup"><span data-stu-id="8cec1-218">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="8cec1-219">Movendo-se pela transição:</span><span class="sxs-lookup"><span data-stu-id="8cec1-219">Moving through the transition:</span></span>

- [<span data-ttu-id="8cec1-220">Ações e impactos das fases de migração</span><span class="sxs-lookup"><span data-stu-id="8cec1-220">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="8cec1-221">Pré-trabalho adicional</span><span class="sxs-lookup"><span data-stu-id="8cec1-221">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="8cec1-222">Informações adicionais para [o Azure AD,](ms-cloud-germany-transition-azure-ad.md) [dispositivos, experiências](ms-cloud-germany-transition-add-experience.md)e [AD FS](ms-cloud-germany-transition-add-adfs.md). [](ms-cloud-germany-transition-add-devices.md)</span><span class="sxs-lookup"><span data-stu-id="8cec1-222">Additional information for [Azure AD](ms-cloud-germany-transition-azure-ad.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="8cec1-223">Aplicativos de nuvem:</span><span class="sxs-lookup"><span data-stu-id="8cec1-223">Cloud apps:</span></span>

- [<span data-ttu-id="8cec1-224">Informações do programa de migração do Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="8cec1-224">Dynamics 365 migration program information</span></span>](/dynamics365/get-started/migrate-data-german-region)
- [<span data-ttu-id="8cec1-225">Informações do programa de migração do Power BI</span><span class="sxs-lookup"><span data-stu-id="8cec1-225">Power BI migration program information</span></span>](/power-bi/admin/service-admin-migrate-data-germany)
- [<span data-ttu-id="8cec1-226">Introdução à atualização do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8cec1-226">Getting started with your Microsoft Teams upgrade</span></span>](/microsoftteams/upgrade-start-here)