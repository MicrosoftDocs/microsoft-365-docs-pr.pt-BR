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
ms.openlocfilehash: cdb3278e1d96b2ebdced122ab53db716c3195d8c
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/11/2021
ms.locfileid: "52903860"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="4eebd-103">Informações adicionais do dispositivo para a migração do Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="4eebd-103">Additional device information for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="4eebd-104">Os dispositivos ingressados e registrados no Azure AD conectados ao Microsoft Cloud Deutschland devem ser migrados após a fase 9 e antes da fase 10.</span><span class="sxs-lookup"><span data-stu-id="4eebd-104">Azure AD joined and registered devices connected to Microsoft Cloud Deutschland must be migrated after phase 9 and before phase 10.</span></span> <span data-ttu-id="4eebd-105">A migração de um dispositivo depende do tipo de dispositivo, do sistema operacional e da relação do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="4eebd-105">The migration of a device depends on the devices type, operating system and Azure AD relation.</span></span> 

## <a name="azure-ad-joined-windows-10-devices"></a><span data-ttu-id="4eebd-106">Dispositivos Windows 10 Azure AD</span><span class="sxs-lookup"><span data-stu-id="4eebd-106">Azure AD Joined Windows 10 devices</span></span>
<span data-ttu-id="4eebd-107">Se um Windows 10 for ingressado no Azure AD, ele deverá ser desconectado do Azure AD e deverá ser conectado novamente.</span><span class="sxs-lookup"><span data-stu-id="4eebd-107">If a Windows 10 device is Azure AD joined, it must be disconnected from Azure AD and must be connected again.</span></span> 

<span data-ttu-id="4eebd-108">[![Dispositivo do Azure AD Re-Join Flow ](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png)](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="4eebd-108">[ ![Azure AD Device Re-Join Flow](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png) ](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png#lightbox)</span></span>


<span data-ttu-id="4eebd-109">Se o usuário for um administrador no dispositivo Windows 10, o usuário poderá desemitir o dispositivo do Azure AD e jun-lo novamente em três etapas.</span><span class="sxs-lookup"><span data-stu-id="4eebd-109">If the user is an administrator on the Windows 10 device, the user can unregister the device from Azure AD and re-join it again in three steps.</span></span> 

### <a name="step-1-determine-if-the-device-is-azure-id-joined"></a><span data-ttu-id="4eebd-110">Etapa 1: Determinar se o dispositivo está ingressado no Azure ID</span><span class="sxs-lookup"><span data-stu-id="4eebd-110">Step 1: Determine if the device is Azure ID joined</span></span>
1.  <span data-ttu-id="4eebd-111">Entre com sua conta corporativa.</span><span class="sxs-lookup"><span data-stu-id="4eebd-111">Sign in with your work account.</span></span>
2.  <span data-ttu-id="4eebd-112">Vá para o **Configurações**  >  **contas acessar** o trabalho ou a  >  **escola.**</span><span class="sxs-lookup"><span data-stu-id="4eebd-112">Go to **Settings** > **Accounts** > **Access Work Or School**.</span></span> 
3.  <span data-ttu-id="4eebd-113">Procure uma conta na lista com **[...]' s Azure AD**.</span><span class="sxs-lookup"><span data-stu-id="4eebd-113">Look for an account in the list with **connected to […]‘s Azure AD**.</span></span> 
4.  <span data-ttu-id="4eebd-114">Se houver uma conta conectada, prossiga com a Etapa 2.</span><span class="sxs-lookup"><span data-stu-id="4eebd-114">If a connected account exists, proceed with Step 2.</span></span> 
### <a name="step-2-disconnect-the-device-from-azure-ad"></a><span data-ttu-id="4eebd-115">Etapa 2: desconectar o dispositivo do Azure AD</span><span class="sxs-lookup"><span data-stu-id="4eebd-115">Step 2: Disconnect the device from Azure AD</span></span>
1.  <span data-ttu-id="4eebd-116">Clique **em Desconectar** no trabalho conectado ou conta escolar.</span><span class="sxs-lookup"><span data-stu-id="4eebd-116">Click **Disconnect** on the connected work or School Account.</span></span> 
2.  <span data-ttu-id="4eebd-117">Confirme a desconexão duas vezes.</span><span class="sxs-lookup"><span data-stu-id="4eebd-117">Confirm the disconnect twice.</span></span> 
3.  <span data-ttu-id="4eebd-118">Insira um nome de usuário e senha de administrador local.</span><span class="sxs-lookup"><span data-stu-id="4eebd-118">Enter a local administrator username and password.</span></span> <span data-ttu-id="4eebd-119">O dispositivo está desconectado.</span><span class="sxs-lookup"><span data-stu-id="4eebd-119">The device is disconnected.</span></span>
4.  <span data-ttu-id="4eebd-120">Reinicie o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4eebd-120">Restart the device.</span></span>
### <a name="step-3-join-the-device-to-azure-ad"></a><span data-ttu-id="4eebd-121">Etapa 3: Associar o dispositivo ao Azure AD</span><span class="sxs-lookup"><span data-stu-id="4eebd-121">Step 3: Join the device to Azure AD</span></span>
1.  <span data-ttu-id="4eebd-122">Entre com as credenciais do administrador local.</span><span class="sxs-lookup"><span data-stu-id="4eebd-122">Sign in with the credentials of the local administrator.</span></span>
2.  <span data-ttu-id="4eebd-123">Vá para o **Configurações**  >  **contas acessar** o trabalho ou a  >  **escola.**</span><span class="sxs-lookup"><span data-stu-id="4eebd-123">Go to **Settings** > **Accounts** > **Access Work Or School**.</span></span>
3.  <span data-ttu-id="4eebd-124">Clique em **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="4eebd-124">Click **Connect**.</span></span>
4.  <span data-ttu-id="4eebd-125">**IMPORTANTE**: Clique **em Ingressar no Azure AD**.</span><span class="sxs-lookup"><span data-stu-id="4eebd-125">**IMPORTANT**: Click **Join to Azure AD**.</span></span>
5.  <span data-ttu-id="4eebd-126">Insira o endereço de email e a senha da sua conta de trabalho.</span><span class="sxs-lookup"><span data-stu-id="4eebd-126">Enter the e-mail address and password of your work account.</span></span> <span data-ttu-id="4eebd-127">O dispositivo está conectado.</span><span class="sxs-lookup"><span data-stu-id="4eebd-127">The device is connected.</span></span>
6.  <span data-ttu-id="4eebd-128">Reinicie o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4eebd-128">Restart the device.</span></span>
7.  <span data-ttu-id="4eebd-129">Entre com o endereço de email e a senha da sua conta de trabalho.</span><span class="sxs-lookup"><span data-stu-id="4eebd-129">Sign in with the email address and password of your work account.</span></span>

<span data-ttu-id="4eebd-130">Se o usuário não for um administrador do dispositivo, um administrador global do Azure AD poderá criar a conta de administrador local no dispositivo seguindo esse caminho de configuração e desatar o dispositivo:</span><span class="sxs-lookup"><span data-stu-id="4eebd-130">If the user is not an administrator of the device, an Azure AD global administrator can create the local administrator account on the device following this configuration path and unjoin the device:</span></span>

<span data-ttu-id="4eebd-131">*Configurações > Contas > Outras Contas > Credenciais desconhecidas > Adicionar usuário sem Microsoft-Account*</span><span class="sxs-lookup"><span data-stu-id="4eebd-131">*Settings > Accounts > Other Accounts > Credentials unknown > Add user without Microsoft-Account*</span></span>

<span data-ttu-id="4eebd-132">Para ingressar outra vez, as credenciais de qualquer conta de trabalho de sua organização podem ser usadas nesta etapa.</span><span class="sxs-lookup"><span data-stu-id="4eebd-132">For re-joining, the credentials of any work account from your organization can be used in this step.</span></span> 

<span data-ttu-id="4eebd-133">Considere que a conta de trabalho usada para ingressar no dispositivo será automaticamente promovida como administrador do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4eebd-133">Please consider that the work account used to join the device will be automatically promoted as an Administrator of the device.</span></span>
<span data-ttu-id="4eebd-134">Qualquer outra conta de trabalho da organização pode entrar no dispositivo, mas não tem privilégios de administrador.</span><span class="sxs-lookup"><span data-stu-id="4eebd-134">Any other work account from the organization can sign in to the device, but has no administrator privileges.</span></span>

## <a name="azure-ad-registered-workplace-joined-windows-10-devices"></a><span data-ttu-id="4eebd-135">Azure AD registrado (ingressado no local de trabalho) Windows 10 dispositivos</span><span class="sxs-lookup"><span data-stu-id="4eebd-135">Azure AD registered (workplace-joined) Windows 10 devices</span></span>
<span data-ttu-id="4eebd-136">Se um Windows 10 for registrado no Azure AD, ele precisará ser desconectado do Azure AD e conectado novamente.</span><span class="sxs-lookup"><span data-stu-id="4eebd-136">If a Windows 10 device is Azure AD registered, it needs to be disconnected from the Azure AD and connected again.</span></span>

<span data-ttu-id="4eebd-137">[![Dispositivo do Azure AD Re-Registration Flow ](../media/ms-cloud-germany-migration-opt-in/AAD-ReRegistration-flow.png)](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="4eebd-137">[ ![Azure AD Device Re-Registration Flow](../media/ms-cloud-germany-migration-opt-in/AAD-ReRegistration-flow.png) ](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png#lightbox)</span></span>

### <a name="step-1-determine-if-the-device-is-azure-id-registered"></a><span data-ttu-id="4eebd-138">Etapa 1: Determinar se o dispositivo é Azure ID registrado</span><span class="sxs-lookup"><span data-stu-id="4eebd-138">Step 1: Determine if the device is Azure ID registered</span></span>
1.  <span data-ttu-id="4eebd-139">Entre com seu usuário.</span><span class="sxs-lookup"><span data-stu-id="4eebd-139">Sign in with your user.</span></span>
2.  <span data-ttu-id="4eebd-140">Vá para o **Configurações**  >  **contas acessar** o trabalho ou a  >  **escola.**</span><span class="sxs-lookup"><span data-stu-id="4eebd-140">Go to **Settings** > **Accounts** > **Access Work Or School**.</span></span> 
3.  <span data-ttu-id="4eebd-141">Descubra sua conta de trabalho na lista e verifique se ela está **conectada a [...]' s Azure AD**.</span><span class="sxs-lookup"><span data-stu-id="4eebd-141">Discover your work account in the list and check if it is **connected to […]‘s Azure AD**.</span></span>

    <span data-ttu-id="4eebd-142">Se sua conta de trabalho estiver na lista, mas NÃO conectada a um Azure AD, prossiga com a etapa 2.</span><span class="sxs-lookup"><span data-stu-id="4eebd-142">If your work account is in the list but NOT connected to an Azure AD, proceed with step 2.</span></span>

    <span data-ttu-id="4eebd-143">Caso contrário, seu dispositivo é um dispositivo ingressado no Azure AD e você precisa se referir a dispositivos Windows 10 [Azure AD .](#azure-ad-joined-windows-10-devices)</span><span class="sxs-lookup"><span data-stu-id="4eebd-143">Otherwise, your device is an Azure AD joined device and you have to refer to [Azure AD Joined Windows 10 devices](#azure-ad-joined-windows-10-devices).</span></span>

### <a name="step-2-disconnect-the-device-from-azure-ad"></a><span data-ttu-id="4eebd-144">Etapa 2: desconectar o dispositivo do Azure AD</span><span class="sxs-lookup"><span data-stu-id="4eebd-144">Step 2: Disconnect the device from Azure AD</span></span>
1.  <span data-ttu-id="4eebd-145">Clique em sua conta de trabalho.</span><span class="sxs-lookup"><span data-stu-id="4eebd-145">Click on your work account.</span></span> <span data-ttu-id="4eebd-146">Os botões *Informações* e *Desconectar* aparecem.</span><span class="sxs-lookup"><span data-stu-id="4eebd-146">The buttons *Info* and *Disconnect* appear.</span></span>
2.  <span data-ttu-id="4eebd-147">Clique **em Desconectar**.</span><span class="sxs-lookup"><span data-stu-id="4eebd-147">Click **Disconnect**.</span></span> 
3.  <span data-ttu-id="4eebd-148">Confirme a remoção da conta do dispositivo clicando em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="4eebd-148">Confirm account removal from the device by clicking **Yes**.</span></span>
### <a name="step-3-connect-the-device-to-azure-ad"></a><span data-ttu-id="4eebd-149">Etapa 3: Conexão o dispositivo para o Azure AD</span><span class="sxs-lookup"><span data-stu-id="4eebd-149">Step 3: Connect the device to Azure AD</span></span>
1.  <span data-ttu-id="4eebd-150">Clique em **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="4eebd-150">Click **Connect**.</span></span>
2.  <span data-ttu-id="4eebd-151">Insira o endereço de email da sua conta de trabalho e clique em **Next**.</span><span class="sxs-lookup"><span data-stu-id="4eebd-151">Enter the email address of your work account and click **Next**.</span></span>
3.  <span data-ttu-id="4eebd-152">Insira a senha da sua conta de trabalho e clique **em Entrar**.</span><span class="sxs-lookup"><span data-stu-id="4eebd-152">Enter the password of your work account and click **Sign in**.</span></span>
4.  <span data-ttu-id="4eebd-153">Confirme clicando em **Done**.</span><span class="sxs-lookup"><span data-stu-id="4eebd-153">Confirm by clicking **Done**.</span></span> <span data-ttu-id="4eebd-154">Sua conta de trabalho está listada novamente.</span><span class="sxs-lookup"><span data-stu-id="4eebd-154">Your work account is listed again.</span></span>

## <a name="android"></a><span data-ttu-id="4eebd-155">Android</span><span class="sxs-lookup"><span data-stu-id="4eebd-155">Android</span></span>

<span data-ttu-id="4eebd-156">Para Android, os usuários precisarão registrar e registrar seus dispositivos de novo.</span><span class="sxs-lookup"><span data-stu-id="4eebd-156">For Android, users will need to unregister and re-register their devices.</span></span> <span data-ttu-id="4eebd-157">Isso pode ser feito por meio do aplicativo Microsoft Authenticator ou do Portal da Empresa aplicativo.</span><span class="sxs-lookup"><span data-stu-id="4eebd-157">This can be done via the Microsoft Authenticator app or the Company Portal app.</span></span> 

- <span data-ttu-id="4eebd-158">No aplicativo Microsoft Authenticator, os usuários podem ir **Configurações > Registro de Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="4eebd-158">From the Microsoft Authenticator app, users can go to **Settings > Device Registration**.</span></span> <span data-ttu-id="4eebd-159">A partir daí, os usuários podem se registrar e registrar seus dispositivos de novo.</span><span class="sxs-lookup"><span data-stu-id="4eebd-159">From there users can unregister and re-register their device.</span></span>
 
- <span data-ttu-id="4eebd-160">Na Portal da Empresa, os usuários podem ir até a guia **Dispositivos** e remover o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4eebd-160">From the Company Portal, users can go to **Devices** tab and remove the device.</span></span> <span data-ttu-id="4eebd-161">Depois disso, re-inscreva o dispositivo usando Portal da Empresa.</span><span class="sxs-lookup"><span data-stu-id="4eebd-161">After that, re-enroll the device by using Company Portal.</span></span>
 
- <span data-ttu-id="4eebd-162">Os usuários também podem registrar-se e re-registrar removendo a conta da página de configurações da conta e, em seguida, adicionando a conta de trabalho.</span><span class="sxs-lookup"><span data-stu-id="4eebd-162">Users can also unregister and re-register by removing the account from the account settings page and then re-adding the work account.</span></span>

<span data-ttu-id="4eebd-163">Para não registrar e registrar o dispositivo no Android usando o Microsoft Authenticator app:</span><span class="sxs-lookup"><span data-stu-id="4eebd-163">To unregister and re-register the device on Android by using the Microsoft Authenticator app:</span></span>

1.  <span data-ttu-id="4eebd-164">Abra o Microsoft Authenticator aplicativo e vá para **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="4eebd-164">Open the Microsoft Authenticator app and go to **Settings**.</span></span>
2.  <span data-ttu-id="4eebd-165">Selecione **Registro de dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="4eebd-165">Select **Device registration**.</span></span>
3.  <span data-ttu-id="4eebd-166">Desaconselhe o dispositivo **selecionando Unregister**.</span><span class="sxs-lookup"><span data-stu-id="4eebd-166">Unregister the device by selecting **Unregister**.</span></span>
4.  <span data-ttu-id="4eebd-167">Para **registro de dispositivo,** registre o dispositivo digitando seu endereço de email e selecione **Registrar**.</span><span class="sxs-lookup"><span data-stu-id="4eebd-167">For **Device registration**, re-register the device by typing your email address, and then select **Register**.</span></span>

<span data-ttu-id="4eebd-168">Para não registrar e registrar um dispositivo Android com a página Configurações Android:</span><span class="sxs-lookup"><span data-stu-id="4eebd-168">To unregister and re-register an Android device with the Android Settings page:</span></span>

1.  <span data-ttu-id="4eebd-169">Abra **o dispositivo Configurações** e vá para **Contas**.</span><span class="sxs-lookup"><span data-stu-id="4eebd-169">Open **Device Settings** and go to **Accounts**.</span></span>
2.  <span data-ttu-id="4eebd-170">Selecione a conta de trabalho que você deseja registrar e selecione **Remover conta**.</span><span class="sxs-lookup"><span data-stu-id="4eebd-170">Select the work account that you want to re-register and select **Remove account**.</span></span>
3.  <span data-ttu-id="4eebd-171">Depois que a conta for removida, na página **Contas,** selecione **Adicionar Conta > Conta de Trabalho**.</span><span class="sxs-lookup"><span data-stu-id="4eebd-171">After the account is removed, from the **Accounts** page, select **Add Account > Work account**.</span></span>
4.  <span data-ttu-id="4eebd-172">Para **Ingressar no Local de Trabalho,** digite seu endereço de email e selecione **Ingressar** para concluir o registro do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4eebd-172">For **Workplace Join**, type your email address and select **Join** to complete registering the device.</span></span>

<span data-ttu-id="4eebd-173">Para não registrar e registrar o dispositivo no Android de Portal da Empresa:</span><span class="sxs-lookup"><span data-stu-id="4eebd-173">To unregister and re-register the device on Android from Company Portal:</span></span>

1.  <span data-ttu-id="4eebd-174">Iniciar Portal da Empresa e vá para **a guia Dispositivos.**</span><span class="sxs-lookup"><span data-stu-id="4eebd-174">Launch Company Portal and go to **Devices** tab.</span></span>
2.  <span data-ttu-id="4eebd-175">Selecione o dispositivo para ver os detalhes do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4eebd-175">Select the device to see the device details.</span></span>
3.  <span data-ttu-id="4eebd-176">No menu releitos (três pontos), selecione **Remover** Dispositivo e conclua a remoção confirmando na caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="4eebd-176">From the ellipses (three dots) menu, select **Remove Device**, and complete the removal by confirming in the dialog.</span></span>
4.  <span data-ttu-id="4eebd-177">Agora você deve estar conectado ao aplicativo Portal da Empresa.</span><span class="sxs-lookup"><span data-stu-id="4eebd-177">You should now be logged out of the Company Portal app.</span></span> <span data-ttu-id="4eebd-178">Selecione **Entrar para** registrar o dispositivo de novo.</span><span class="sxs-lookup"><span data-stu-id="4eebd-178">Select **Sign in** to re-register the device.</span></span>

<span data-ttu-id="4eebd-179">Para obter mais informações sobre as ações necessárias durante a fase de migração dessa carga de trabalho ou impacto na administração ou no uso, revise as informações sobre o Azure Active Directory [(Azure AD)](ms-cloud-germany-transition-azure-ad.md)em Informações adicionais do Azure AD para a migração do Microsoft Cloud Deutschland .</span><span class="sxs-lookup"><span data-stu-id="4eebd-179">For more information about any actions required during the migration phase of this workload, or impact to administration or usage, review the information about Azure Active Directory (Azure AD) in [Additional Azure AD information for the migration from Microsoft Cloud Deutschland](ms-cloud-germany-transition-azure-ad.md).</span></span>

## <a name="ios"></a><span data-ttu-id="4eebd-180">iOS</span><span class="sxs-lookup"><span data-stu-id="4eebd-180">iOS</span></span>

<span data-ttu-id="4eebd-181">Em dispositivos iOS, um usuário precisará remover manualmente todas as contas armazenadas em cache do Microsoft Authenticator, desa inscrever o dispositivo e sair de qualquer aplicativo nativo no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4eebd-181">On iOS devices, a user will need to manually remove any cached accounts from the Microsoft Authenticator, unregister the device, and sign out from any native apps on the device.</span></span>

### <a name="step-1-if-present-remove-the-account-from-the-microsoft-authenticator-app"></a><span data-ttu-id="4eebd-182">Etapa 1: se presente, remova a conta do Microsoft Authenticator app</span><span class="sxs-lookup"><span data-stu-id="4eebd-182">Step 1: If present, remove the account from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="4eebd-183">Toque na conta no aplicativo Microsoft Authenticator.</span><span class="sxs-lookup"><span data-stu-id="4eebd-183">Tap the account in the Microsoft Authenticator app.</span></span>
2. <span data-ttu-id="4eebd-184">Toque no **Configurações** no canto superior direito.</span><span class="sxs-lookup"><span data-stu-id="4eebd-184">Tap the **Settings** icon in the top-right corner.</span></span> <span data-ttu-id="4eebd-185">Se você não vir o **ícone** Configurações, talvez não use a versão mais recente do Microsoft Authenticator.</span><span class="sxs-lookup"><span data-stu-id="4eebd-185">If you don't see the **Settings** icon, you might not be using the latest version of Microsoft Authenticator.</span></span>
3. <span data-ttu-id="4eebd-186">Toque no **botão Remover conta.**</span><span class="sxs-lookup"><span data-stu-id="4eebd-186">Tap the **Remove account** button.</span></span>
4. <span data-ttu-id="4eebd-187">Toque **em Todos os aplicativos neste dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="4eebd-187">Tap **All apps on this device**.</span></span>
 
### <a name="step-2-unregister-the-device-from-the-microsoft-authenticator-app"></a><span data-ttu-id="4eebd-188">Etapa 2: Desaconselhe o dispositivo do Microsoft Authenticator app</span><span class="sxs-lookup"><span data-stu-id="4eebd-188">Step 2: Unregister the device from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="4eebd-189">Toque no ícone de menu no canto superior direito.</span><span class="sxs-lookup"><span data-stu-id="4eebd-189">Tap the menu icon in the top-right corner.</span></span>
2. <span data-ttu-id="4eebd-190">Toque **Configurações** e, em seguida, **Registro de Dispositivo.**</span><span class="sxs-lookup"><span data-stu-id="4eebd-190">Tap **Settings** and then **Device Registration**.</span></span>
4. <span data-ttu-id="4eebd-191">Se sua conta for mostrada, toque em Dispositivo de Registro **Não-Registro** e **Continue** na caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="4eebd-191">If your account is shown, tap **Unregister device** and **Continue** in the dialog.</span></span> <span data-ttu-id="4eebd-192">Você não deve ver nenhuma conta depois disso.</span><span class="sxs-lookup"><span data-stu-id="4eebd-192">You should see no account after that.</span></span>
 
### <a name="step-3-sign-out-from-individual-apps-if-necessary"></a><span data-ttu-id="4eebd-193">Etapa 3: Sair de aplicativos individuais, se necessário</span><span class="sxs-lookup"><span data-stu-id="4eebd-193">Step 3: Sign out from individual apps if necessary</span></span>

<span data-ttu-id="4eebd-194">Os usuários podem ir para aplicativos individuais como Outlook, Teams e OneDrive e remover contas desses aplicativos.</span><span class="sxs-lookup"><span data-stu-id="4eebd-194">Users can go to individual apps like Outlook, Teams, and OneDrive, and remove accounts from those apps.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="4eebd-195">Perguntas frequentes</span><span class="sxs-lookup"><span data-stu-id="4eebd-195">Frequently asked questions</span></span>

<span data-ttu-id="4eebd-196">**Como posso saber se minha organização foi afetada?**</span><span class="sxs-lookup"><span data-stu-id="4eebd-196">**How can I tell if my organization is affected?**</span></span>

<span data-ttu-id="4eebd-197">Os administradores devem `https://portal.microsoftazure.de` verificar para determinar se eles têm algum Azure AD registrado ou dispositivos ingressados no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="4eebd-197">Administrators should check `https://portal.microsoftazure.de` to determine if they have any Azure AD registered or Azure AD joined devices.</span></span> <span data-ttu-id="4eebd-198">Se sua organização tiver dispositivos registrados no Azure AD ou no Azure AD, sua organização terá que seguir as instruções nesta página.</span><span class="sxs-lookup"><span data-stu-id="4eebd-198">If your organization has Azure AD registered or Azure AD joined devices, your organization has to follow the instructions on this page.</span></span>

<span data-ttu-id="4eebd-199">**Quando meus usuários registram seus dispositivos de novo?**</span><span class="sxs-lookup"><span data-stu-id="4eebd-199">**When do my users re-register their devices?**</span></span>

<span data-ttu-id="4eebd-200">É fundamental para o seu sucesso que você apenas não registre e registre seus dispositivos após a conclusão da [fase 9.](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization)</span><span class="sxs-lookup"><span data-stu-id="4eebd-200">It's critical to your success that you only unregister and re-register your devices after [phase 9](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) has been completed.</span></span> <span data-ttu-id="4eebd-201">Você deve concluir o recadastramento antes da fase 10 ser iniciada, caso contrário, poderá perder o acesso ao dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4eebd-201">You must finish the re-registration before phase 10 starts, otherwise you could lose access to your device.</span></span>

<span data-ttu-id="4eebd-202">**Como saber se todos os meus dispositivos estão registrados na nuvem pública?**</span><span class="sxs-lookup"><span data-stu-id="4eebd-202">**How do I know that all my devices are registered in the public cloud?**</span></span>

<span data-ttu-id="4eebd-203">Para verificar se seus dispositivos estão registrados na nuvem pública, você deve exportar e baixar a lista de dispositivos do portal do Azure AD para uma planilha Excel.</span><span class="sxs-lookup"><span data-stu-id="4eebd-203">To check whether your devices are registered in the public cloud, you should export and download the list of devices from the Azure AD portal to an Excel spreadsheet.</span></span> <span data-ttu-id="4eebd-204">Em seguida, filtre os dispositivos registrados (usando a coluna _registeredTime)_ após a data em que sua organização passou a [fase 9 do](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization)processo de migração .</span><span class="sxs-lookup"><span data-stu-id="4eebd-204">Then, filter the devices that are registered (by using the _registeredTime_ column) after the date when your organization has passed [phase 9 of the migration process](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization).</span></span>

## <a name="additional-considerations"></a><span data-ttu-id="4eebd-205">Considerações adicionais</span><span class="sxs-lookup"><span data-stu-id="4eebd-205">Additional considerations</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4eebd-206">A entidade de serviço do Intune será habilitada após a [fase 3](ms-cloud-germany-transition-phases.md#phase-3-subscription-transfer)do processo de migração , o que implica na ativação do Registro de Dispositivo do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="4eebd-206">The Intune service principal will be enabled after [phase 3 of the migration process](ms-cloud-germany-transition-phases.md#phase-3-subscription-transfer), which implies the activation of Azure AD Device Registration.</span></span> <span data-ttu-id="4eebd-207">Se você bloqueou o Registro de Dispositivo do Azure AD antes da migração, deverá desabilitar a entidade de serviço do Intune com o PowerShell para desabilitar o Registro de Dispositivo do Azure AD com o portal do Azure AD novamente.</span><span class="sxs-lookup"><span data-stu-id="4eebd-207">If you blocked Azure AD Device Registration before migration, you must disable the Intune service principal with PowerShell to disable Azure AD Device Registration with the Azure AD portal again.</span></span> <span data-ttu-id="4eebd-208">Você pode desabilitar a entidade de serviço do Intune com esse comando no Azure Active Directory PowerShell para Graph módulo.</span><span class="sxs-lookup"><span data-stu-id="4eebd-208">You can disable the Intune service principal with this command in the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

## <a name="more-information"></a><span data-ttu-id="4eebd-209">Mais Informações</span><span class="sxs-lookup"><span data-stu-id="4eebd-209">More information</span></span>

<span data-ttu-id="4eebd-210">Como começar:</span><span class="sxs-lookup"><span data-stu-id="4eebd-210">Getting started:</span></span>

- [<span data-ttu-id="4eebd-211">Migração do Microsoft Cloud Deutschland para serviços Office 365 nas novas regiões do datacenter alemão</span><span class="sxs-lookup"><span data-stu-id="4eebd-211">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="4eebd-212">Assistência de Migração do Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="4eebd-212">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="4eebd-213">Como aceitar a migração</span><span class="sxs-lookup"><span data-stu-id="4eebd-213">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="4eebd-214">Experiência do cliente durante a migração</span><span class="sxs-lookup"><span data-stu-id="4eebd-214">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="4eebd-215">Movendo-se pela transição:</span><span class="sxs-lookup"><span data-stu-id="4eebd-215">Moving through the transition:</span></span>

- [<span data-ttu-id="4eebd-216">Ações e impactos das fases de migração</span><span class="sxs-lookup"><span data-stu-id="4eebd-216">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="4eebd-217">Pré-trabalho adicional</span><span class="sxs-lookup"><span data-stu-id="4eebd-217">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="4eebd-218">Informações adicionais para [o Azure AD,](ms-cloud-germany-transition-azure-ad.md) [dispositivos, experiências](ms-cloud-germany-transition-add-experience.md)e [AD FS](ms-cloud-germany-transition-add-adfs.md). [](ms-cloud-germany-transition-add-devices.md)</span><span class="sxs-lookup"><span data-stu-id="4eebd-218">Additional information for [Azure AD](ms-cloud-germany-transition-azure-ad.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="4eebd-219">Aplicativos de nuvem:</span><span class="sxs-lookup"><span data-stu-id="4eebd-219">Cloud apps:</span></span>

- [<span data-ttu-id="4eebd-220">Informações do programa de migração do Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="4eebd-220">Dynamics 365 migration program information</span></span>](/dynamics365/get-started/migrate-data-german-region)
- [<span data-ttu-id="4eebd-221">Informações do programa de migração do Power BI</span><span class="sxs-lookup"><span data-stu-id="4eebd-221">Power BI migration program information</span></span>](/power-bi/admin/service-admin-migrate-data-germany)
- [<span data-ttu-id="4eebd-222">Introdução à atualização do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4eebd-222">Getting started with your Microsoft Teams upgrade</span></span>](/microsoftteams/upgrade-start-here)