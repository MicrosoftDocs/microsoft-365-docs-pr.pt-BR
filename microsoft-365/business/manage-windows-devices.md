---
title: Habilitar dispositivos Windows 10 associados a um domínio para serem gerenciados pelo Microsoft 365 for Business
f1.keywords:
- CSH
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
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: Saiba como habilitar o Microsoft 365 para proteger dispositivos do Windows 10 locais associados ao Active Directory em apenas algumas etapas.
ms.openlocfilehash: 857651081fb10856d28dd419333ebef655388407
ms.sourcegitcommit: e6e704cbd9a50fc7db1e6a0cf5d3f8c6cbb94363
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2020
ms.locfileid: "44564916"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a><span data-ttu-id="0e98f-103">Habilitar dispositivos Windows 10 associados ao domínio para serem gerenciados pelo Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="0e98f-103">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium</span></span>

<span data-ttu-id="0e98f-104">Se sua organização usa o Windows Server Active Directory no local, você pode configurar o Microsoft 365 Business Premium para proteger seus dispositivos Windows 10, mantendo ainda a manutenção do acesso a recursos locais que exigem autenticação local.</span><span class="sxs-lookup"><span data-stu-id="0e98f-104">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business Premium to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span>
<span data-ttu-id="0e98f-105">Para configurar essa proteção, é possível implementar **dispositivos híbridos associados ao AD do Azure**.</span><span class="sxs-lookup"><span data-stu-id="0e98f-105">To set up this protection, you can implement **Hybrid Azure AD joined devices**.</span></span> <span data-ttu-id="0e98f-106">Esses dispositivos fazem parte de seu Active Directory local e do Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0e98f-106">These devices are joined to both your on-premises Active Directory and your Azure Active Directory.</span></span>

<span data-ttu-id="0e98f-107">Este vídeo descreve as etapas para configurar isso para o cenário mais comum, que também é detalhado nas etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="0e98f-107">This video describes the steps for how to set this up for the most common scenario, which is also detailed in the steps that follow.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="before-you-get-started-make-sure-you-complete-these-steps"></a><span data-ttu-id="0e98f-108">Antes de começar, certifique-se de concluir estas etapas:</span><span class="sxs-lookup"><span data-stu-id="0e98f-108">Before you get started, make sure you complete these steps:</span></span>
- <span data-ttu-id="0e98f-109">Sincronizar os usuários com o Azure AD com o Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="0e98f-109">Synchronize users to Azure AD with Azure AD Connect.</span></span>
- <span data-ttu-id="0e98f-110">Concluir a sincronização da unidade organizacional (OU) do Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="0e98f-110">Complete Azure AD Connect Organizational Unit (OU) sync.</span></span>
- <span data-ttu-id="0e98f-111">Certifique-se de que todos os usuários de domínio sincronizados têm licenças para o Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="0e98f-111">Make sure all the domain users you sync have licenses to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="0e98f-112">Consulte [Synchronize Domain Users to Microsoft](manage-domain-users.md) para obter as etapas.</span><span class="sxs-lookup"><span data-stu-id="0e98f-112">See [Synchronize domain users to Microsoft](manage-domain-users.md) for the steps.</span></span>

## <a name="1-verify-mdm-authority-in-intune"></a><span data-ttu-id="0e98f-113">1. Verifique a autoridade MDM no Intune</span><span class="sxs-lookup"><span data-stu-id="0e98f-113">1. Verify MDM Authority in Intune</span></span>

<span data-ttu-id="0e98f-114">Vá até portal.azure.com e na parte superior da pesquisa de página do Intune.</span><span class="sxs-lookup"><span data-stu-id="0e98f-114">Go to portal.azure.com and on the top of the page search for Intune.</span></span>
<span data-ttu-id="0e98f-115">Na página do Microsoft Intune, selecione **registro de dispositivo** e, na página **visão geral** , verifique se a **autoridade MDM** é o **Intune**.</span><span class="sxs-lookup"><span data-stu-id="0e98f-115">On the Microsoft Intune page, select **Device enrollment** and on the **Overview** page make sure **MDM authority** is **Intune**.</span></span>

- <span data-ttu-id="0e98f-116">Se **MDM Authority** for **None**, clique na **autoridade MDM** para defini-la como **Intune**.</span><span class="sxs-lookup"><span data-stu-id="0e98f-116">If **MDM authority** is **None**, click the **MDM authority** to set it to **Intune**.</span></span>
- <span data-ttu-id="0e98f-117">Se o **MDM Authority** for o **Microsoft Office 365**, acesse **dispositivos**  >  **inscrever dispositivos** e usar a caixa de diálogo **Adicionar autoridade MDM** no direito de adicionar autoridade **MDM do Intune** (a caixa de diálogo **Adicionar autoridade MDM** só estará disponível se a **autoridade MDM** estiver definida como Microsoft Office 365).</span><span class="sxs-lookup"><span data-stu-id="0e98f-117">If **MDM authority** is **Microsoft Office 365**,go to **Devices** > **Enroll devices** and use the **Add MDM authority** dialog on the right to add **Intune MDM** authority (the **Add MDM Authority** dialog is only available if the **MDM Authority** is set to Microsoft Office 365).</span></span>

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a><span data-ttu-id="0e98f-118">2. Verifique se o Azure AD está habilitado para ingressar em computadores</span><span class="sxs-lookup"><span data-stu-id="0e98f-118">2. Verify Azure AD is enabled for joining computers</span></span>

- <span data-ttu-id="0e98f-119">Vá para o centro de administração em <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> e selecione **Azure Active Directory** (selecione Mostrar tudo se o Azure Active Directory não estiver visível) na lista de **centros de administração** .</span><span class="sxs-lookup"><span data-stu-id="0e98f-119">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select **Azure Active Directory** (select Show all if Azure Active Directory is not visible) in the **Admin centers** list.</span></span> 
- <span data-ttu-id="0e98f-120">No **centro de administração do Azure Active Directory**, vá para **Azure Active Directory** , escolha **dispositivos** e **configurações de dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="0e98f-120">In the **Azure Active Directory admin center**, go to **Azure Active Directory** , choose **Devices** and then **Device settings**.</span></span>
- <span data-ttu-id="0e98f-121">Verifique se**os usuários podem ingressar em dispositivos no Azure ad** está habilitado</span><span class="sxs-lookup"><span data-stu-id="0e98f-121">Verify**Users may join devices to Azure AD** is enabled</span></span> 
    1. <span data-ttu-id="0e98f-122">Para habilitar todos os usuários, defina como **todos**.</span><span class="sxs-lookup"><span data-stu-id="0e98f-122">To enable all users, set to **All**.</span></span>
    2. <span data-ttu-id="0e98f-123">Para habilitar usuários específicos, defina como **selecionado** para habilitar um grupo específico de usuários.</span><span class="sxs-lookup"><span data-stu-id="0e98f-123">To enable specific users, set to **Selected** to enable a specific group of users.</span></span>
        - <span data-ttu-id="0e98f-124">Adicione os usuários de domínio desejados sincronizados no Azure AD para um [grupo de segurança](../admin/create-groups/create-groups.md).</span><span class="sxs-lookup"><span data-stu-id="0e98f-124">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        - <span data-ttu-id="0e98f-125">Escolha **Selecionar grupos** para habilitar o escopo de usuário MDM para esse grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="0e98f-125">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a><span data-ttu-id="0e98f-126">3. Verifique se o Azure AD está habilitado para MDM</span><span class="sxs-lookup"><span data-stu-id="0e98f-126">3. Verify Azure AD is enabled for MDM</span></span>

- <span data-ttu-id="0e98f-127">Vá para o centro de administração em <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> e selecione Selecionar **ponto de extremidade gerenciar**o t (selecionar **Mostrar tudo** se o **Endpoint Manager** não estiver visível)</span><span class="sxs-lookup"><span data-stu-id="0e98f-127">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select select **Endpoint Managemen**t (select **Show all** if **Endpoint Manager** is not visible)</span></span>
- <span data-ttu-id="0e98f-128">No **centro de administração do Gerenciador de pontos de extremidade da Microsoft**, vá para **dispositivos**  >  **Windows**  >  **Windows Enrollment**  >  **registro automático**do registro do Windows do Windows.</span><span class="sxs-lookup"><span data-stu-id="0e98f-128">In the **Microsoft Endpoint Manager admin center**, go to **Devices** > **Windows** > **Windows Enrollment** > **Automatic Enrollment**.</span></span>
- <span data-ttu-id="0e98f-129">Verifique se o escopo de usuário MDM está habilitado.</span><span class="sxs-lookup"><span data-stu-id="0e98f-129">Verify MDM user scope is enabled.</span></span>

    1. <span data-ttu-id="0e98f-130">Para inscrever todos os computadores, defina como **todos** para registrar automaticamente todos os computadores de usuários que ingressaram no Azure AD e em novos computadores quando os usuários adicionam uma conta de trabalho ao Windows.</span><span class="sxs-lookup"><span data-stu-id="0e98f-130">To enroll all computers, set to **All** to automatically enroll all user computers that are joined to Azure AD and new computers  when the users add a work account to Windows.</span></span>
    2. <span data-ttu-id="0e98f-131">Definido como **alguns** para registrar os computadores de um grupo específico de usuários.</span><span class="sxs-lookup"><span data-stu-id="0e98f-131">Set to **Some** to enroll the computers of a specific group of users.</span></span>
        -  <span data-ttu-id="0e98f-132">Adicione os usuários de domínio desejados sincronizados no Azure AD para um [grupo de segurança](../admin/create-groups/create-groups.md).</span><span class="sxs-lookup"><span data-stu-id="0e98f-132">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        -  <span data-ttu-id="0e98f-133">Escolha **Selecionar grupos** para habilitar o escopo de usuário MDM para esse grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="0e98f-133">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="4-set-up-service-connection-point-scp"></a><span data-ttu-id="0e98f-134">4. configurar ponto de conexão de serviço (SCP)</span><span class="sxs-lookup"><span data-stu-id="0e98f-134">4. Set up Service connection point (SCP)</span></span>

<span data-ttu-id="0e98f-135">Essas etapas são simplificadas para [Configurar a União híbrida do Azure ad](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join).</span><span class="sxs-lookup"><span data-stu-id="0e98f-135">These steps are simplified from [configure hybrid azure AD join](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join).</span></span> <span data-ttu-id="0e98f-136">Para concluir as etapas de que você precisa para usar o Azure AD Connect e suas senhas de administrador global do Microsoft 365 Business Premium e do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0e98f-136">To complete the steps you need to use Azure AD Connect and your Microsoft 365 Business Premium global admin and Active Directory admin passwords.</span></span>

1.  <span data-ttu-id="0e98f-137">Inicie o Azure AD Connect e selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="0e98f-137">Start Azure AD Connect, and then select **Configure**.</span></span>
2.  <span data-ttu-id="0e98f-138">Na página **tarefas adicionais** , selecione **Configurar opções de dispositivo**e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0e98f-138">On the **Additional tasks**  page, select **Configure device options**, and then select **Next**.</span></span>
3.  <span data-ttu-id="0e98f-139">Na página **visão geral** , selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0e98f-139">On the **Overview** page, select **Next**.</span></span>
4.  <span data-ttu-id="0e98f-140">Na página **conectar ao Azure ad** , insira as credenciais de um administrador global para o Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="0e98f-140">On the **Connect to Azure AD** page, enter the credentials of a global administrator for Microsoft 365 Business Premium.</span></span>
5.  <span data-ttu-id="0e98f-141">Na página **Opções de dispositivo** , selecione **Configurar ingresso híbrida do Azure ad**e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0e98f-141">On the **Device options** page, select **Configure Hybrid Azure AD join**, and then select **Next**.</span></span>
6.  <span data-ttu-id="0e98f-142">Na página **SCP** , para cada floresta onde você deseja que o Azure ad Connect configure o SCP, conclua as seguintes etapas e selecione **Avançar**:</span><span class="sxs-lookup"><span data-stu-id="0e98f-142">On the **SCP** page, for each forest where you want Azure AD Connect to configure the SCP, complete the following steps, and then select **Next**:</span></span>
    - <span data-ttu-id="0e98f-143">Marque a caixa ao lado do nome da floresta.</span><span class="sxs-lookup"><span data-stu-id="0e98f-143">Check the box beside the forest name.</span></span> <span data-ttu-id="0e98f-144">A floresta deve ser o nome de domínio do AD.</span><span class="sxs-lookup"><span data-stu-id="0e98f-144">The forest should be your AD domain name.</span></span>
    - <span data-ttu-id="0e98f-145">Na coluna **serviço de autenticação** , abra o menu suspenso e selecione nome de domínio correspondente (deve haver apenas uma opção).</span><span class="sxs-lookup"><span data-stu-id="0e98f-145">Under the **Authentication Service** column, open the dropdown and select matching domain name (there should only be one only option).</span></span>
    - <span data-ttu-id="0e98f-146">Selecione **Adicionar** para inserir as credenciais de administrador de domínio.</span><span class="sxs-lookup"><span data-stu-id="0e98f-146">Select **Add** to enter the domain administrator credentials.</span></span>  
7.  <span data-ttu-id="0e98f-147">Na página **sistemas operacionais de dispositivos** , selecione somente dispositivos associados ao domínio Windows 10 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="0e98f-147">On the **Device operating systems** page, select Windows 10 or later domain-joined devices only.</span></span>
8.  <span data-ttu-id="0e98f-148">Na página **pronto para configurar** , selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="0e98f-148">On the **Ready to configure** page, select **Configure**.</span></span>
9.  <span data-ttu-id="0e98f-149">Na página **configuração concluída** , selecione **sair**.</span><span class="sxs-lookup"><span data-stu-id="0e98f-149">On the **Configuration complete** page, select **Exit**.</span></span>


## <a name="5-create-a-gpo-for-intune-enrollment--admx-method"></a><span data-ttu-id="0e98f-150">5. criar um GPO para registro do Intune – método ADMX</span><span class="sxs-lookup"><span data-stu-id="0e98f-150">5. Create a GPO for Intune Enrollment – ADMX method</span></span>

<span data-ttu-id="0e98f-151">Use. Arquivo de modelo ADMX.</span><span class="sxs-lookup"><span data-stu-id="0e98f-151">Use .ADMX template file.</span></span>

1.  <span data-ttu-id="0e98f-152">Faça logon no servidor do AD, pesquise e abra o gerenciamento de política de grupo de ferramentas **do Gerenciador de servidores**  >  **Tools**  >  **Group Policy Management**.</span><span class="sxs-lookup"><span data-stu-id="0e98f-152">Log on to AD server, search and open **Server Manager** > **Tools** > **Group Policy Management**.</span></span>
2.  <span data-ttu-id="0e98f-153">Selecione seu nome de domínio em **domínios** e clique com o botão direito do mouse em **objetos de política de grupo** para selecionar **novo**.</span><span class="sxs-lookup"><span data-stu-id="0e98f-153">Select your domain name under **Domains** and right-click **Group Policy Objects** to select **New**.</span></span>
3.  <span data-ttu-id="0e98f-154">Dê um nome ao novo GPO, por exemplo "*Cloud_Enrollment*" e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="0e98f-154">Give the new GPO an name, for example “*Cloud_Enrollment*” and then select **OK**.</span></span>
4.  <span data-ttu-id="0e98f-155">Clique com o botão direito do mouse no novo GPO em **objetos de política de grupo** e selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="0e98f-155">Right-click the new GPO under **Group Policy Objects** and select **Edit**.</span></span>
5.  <span data-ttu-id="0e98f-156">No **Editor de gerenciamento de política de grupo**, vá para configurações do **computador**  >  **Policies**  >  **modelos administrativos**do  >  **Windows**  >  **MDM**</span><span class="sxs-lookup"><span data-stu-id="0e98f-156">In the **Group Policy Management Editor**, go to **Computer Configuration** > **Policies** > **Administrative Templates** > **Windows Components** > **MDM**.</span></span>
6. <span data-ttu-id="0e98f-157">Clique com o botão direito do mouse em **habilitar o registro MDM automático usando as credenciais padrão do Azure ad** e selecione **habilitado**  >  **OK**.</span><span class="sxs-lookup"><span data-stu-id="0e98f-157">Right-click **Enable automatic MDM enrollment using default Azure AD credentials** and then select **Enabled** > **OK**.</span></span> <span data-ttu-id="0e98f-158">Feche a janela do editor.</span><span class="sxs-lookup"><span data-stu-id="0e98f-158">Close the editor window.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0e98f-159">Se você não vir a política **habilitar o registro MDM automático usando as credenciais padrão do Azure ad**, confira [obter os modelos administrativos mais recentes](#get-the-latest-administrative-templates).</span><span class="sxs-lookup"><span data-stu-id="0e98f-159">If you do not see the policy **Enable automatic MDM enrollment using default Azure AD credentials**, see [Get the latest Administrative Templates](#get-the-latest-administrative-templates).</span></span>

## <a name="6-deploy-the-group-policy"></a><span data-ttu-id="0e98f-160">6. implantar a política de grupo</span><span class="sxs-lookup"><span data-stu-id="0e98f-160">6. Deploy the Group Policy</span></span>

1.  <span data-ttu-id="0e98f-161">No Gerenciador de servidores, em **domínios** > objetos de política de grupo, selecione o GPO da etapa 3 acima, por exemplo "Cloud_Enrollment".</span><span class="sxs-lookup"><span data-stu-id="0e98f-161">In the Server Manager, under **Domains** > Group Policy objects, select the GPO from Step 3 above, for example “Cloud_Enrollment”.</span></span>
2.  <span data-ttu-id="0e98f-162">Selecione a guia **escopo** do GPO.</span><span class="sxs-lookup"><span data-stu-id="0e98f-162">Select the **Scope** tab for your GPO.</span></span>
3.  <span data-ttu-id="0e98f-163">Na guia escopo do GPO, clique com o botão direito do mouse no link para o domínio em **links**.</span><span class="sxs-lookup"><span data-stu-id="0e98f-163">In the GPO’s Scope tab, right-click the link to the domain under **Links**.</span></span>
4.  <span data-ttu-id="0e98f-164">Selecione **Enforced** para implantar o GPO e, em seguida, **OK** na tela de confirmação.</span><span class="sxs-lookup"><span data-stu-id="0e98f-164">Select **Enforced** to deploy the GPO and then **OK** in the confirmation screen.</span></span>

## <a name="get-the-latest-administrative-templates"></a><span data-ttu-id="0e98f-165">Obter os modelos administrativos mais recentes</span><span class="sxs-lookup"><span data-stu-id="0e98f-165">Get the latest Administrative Templates</span></span>

<span data-ttu-id="0e98f-166">Se você não vir a política **habilitar o registro MDM automático usando as credenciais padrão do Azure ad**, talvez você não tenha o ADMX instalado para o Windows 10, a versão 1803, a versão 1809 ou a versão 1903.</span><span class="sxs-lookup"><span data-stu-id="0e98f-166">If you do not see the policy **Enable automatic MDM enrollment using default Azure AD credentials**, it may be because you don’t have the ADMX installed for Windows 10, version 1803, version 1809, or version 1903.</span></span> <span data-ttu-id="0e98f-167">Para corrigir o problema, siga estas etapas (Observação: o MDM. admx mais recente é compatível com versões anteriores):</span><span class="sxs-lookup"><span data-stu-id="0e98f-167">To fix the issue, follow these steps (Note: the latest MDM.admx is backwards compatible):</span></span>

1.  <span data-ttu-id="0e98f-168">Download: [modelos administrativos (. admx) para Windows 10 pode 2019 atualização (1903)](https://www.microsoft.com/download/details.aspx?id=58495&WT.mc_id=rss_alldownloads_all).</span><span class="sxs-lookup"><span data-stu-id="0e98f-168">Download: [Administrative Templates (.admx) for Windows 10 May 2019 Update (1903)](https://www.microsoft.com/download/details.aspx?id=58495&WT.mc_id=rss_alldownloads_all).</span></span>
2.  <span data-ttu-id="0e98f-169">Instale o pacote no controlador de domínio primário (PDC).</span><span class="sxs-lookup"><span data-stu-id="0e98f-169">Install the package on the Primary Domain Controller (PDC).</span></span>
3.  <span data-ttu-id="0e98f-170">Navegue, dependendo da versão para a pasta: C:\Arquivos de **programas (x86) \Microsoft Group Policy\Windows 10 de maio de 2019 Update (1903) v3**.</span><span class="sxs-lookup"><span data-stu-id="0e98f-170">Navigate, depending on the version to the folder: **C:\Program Files (x86)\Microsoft Group Policy\Windows 10 May 2019 Update (1903) v3**.</span></span>
4.  <span data-ttu-id="0e98f-171">Renomeie a pasta de **definições de política** no caminho acima para **PolicyDefinitions,**.</span><span class="sxs-lookup"><span data-stu-id="0e98f-171">Rename the **Policy Definitions** folder in the above path to **PolicyDefinitions**.</span></span>
5.  <span data-ttu-id="0e98f-172">Copie a pasta **PolicyDefinitions,** para **C:\Windows\SYSVOL\domain\Policies**.</span><span class="sxs-lookup"><span data-stu-id="0e98f-172">Copy **PolicyDefinitions** folder to **C:\Windows\SYSVOL\domain\Policies**.</span></span> 
    -   <span data-ttu-id="0e98f-173">Se você planeja usar um repositório de política central para o seu domínio inteiro, adicione o conteúdo de PolicyDefinitions, ali.</span><span class="sxs-lookup"><span data-stu-id="0e98f-173">If you plan to use a central policy store for your entire domain, add the contents of PolicyDefinitions there.</span></span>
6.  <span data-ttu-id="0e98f-174">Reinicie o controlador de domínio primário para que a política fique disponível.</span><span class="sxs-lookup"><span data-stu-id="0e98f-174">Restart the Primary Domain Controller for the policy to be available.</span></span> <span data-ttu-id="0e98f-175">Este procedimento também funcionará para qualquer versão futura.</span><span class="sxs-lookup"><span data-stu-id="0e98f-175">This procedure will work for any future version as well.</span></span>

<span data-ttu-id="0e98f-176">Neste ponto, você deve ser capaz de ver a política **habilitar o registro MDM automático usando as credenciais padrão do Azure ad** disponíveis.</span><span class="sxs-lookup"><span data-stu-id="0e98f-176">At this point you should be able to see the policy **Enable automatic MDM enrollment using default Azure AD credentials** available.</span></span>

