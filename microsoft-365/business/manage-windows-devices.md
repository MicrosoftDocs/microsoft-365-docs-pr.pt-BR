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
ms.openlocfilehash: 6275c6c4be9cd9631ab095f8b0e1b39683022bb2
ms.sourcegitcommit: d988faa292c2661ffea43c7161aef92b2b4b99bc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "46560834"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a><span data-ttu-id="c1fe2-103">Habilitar dispositivos Windows 10 associados ao domínio para serem gerenciados pelo Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="c1fe2-103">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium</span></span>

<span data-ttu-id="c1fe2-104">Se sua organização usa o Windows Server Active Directory no local, você pode configurar o Microsoft 365 Business Premium para proteger seus dispositivos Windows 10, mantendo ainda a manutenção do acesso a recursos locais que exigem autenticação local.</span><span class="sxs-lookup"><span data-stu-id="c1fe2-104">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business Premium to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span>
<span data-ttu-id="c1fe2-105">Para configurar essa proteção, é possível implementar **dispositivos híbridos associados ao AD do Azure**.</span><span class="sxs-lookup"><span data-stu-id="c1fe2-105">To set up this protection, you can implement **Hybrid Azure AD joined devices**.</span></span> <span data-ttu-id="c1fe2-106">Esses dispositivos fazem parte de seu Active Directory local e do Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c1fe2-106">These devices are joined to both your on-premises Active Directory and your Azure Active Directory.</span></span>

<span data-ttu-id="c1fe2-107">Este vídeo descreve as etapas para configurar isso para o cenário mais comum, que também é detalhado nas etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="c1fe2-107">This video describes the steps for how to set this up for the most common scenario, which is also detailed in the steps that follow.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="before-you-get-started-make-sure-you-complete-these-steps"></a><span data-ttu-id="c1fe2-108">Antes de começar, certifique-se de concluir estas etapas:</span><span class="sxs-lookup"><span data-stu-id="c1fe2-108">Before you get started, make sure you complete these steps:</span></span>
- <span data-ttu-id="c1fe2-109">Sincronizar os usuários com o Azure AD com o Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="c1fe2-109">Synchronize users to Azure AD with Azure AD Connect.</span></span>
- <span data-ttu-id="c1fe2-110">Concluir a sincronização da unidade organizacional (OU) do Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="c1fe2-110">Complete Azure AD Connect Organizational Unit (OU) sync.</span></span>
- <span data-ttu-id="c1fe2-111">Certifique-se de que todos os usuários de domínio sincronizados têm licenças para o Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="c1fe2-111">Make sure all the domain users you sync have licenses to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="c1fe2-112">Consulte [Synchronize Domain Users to Microsoft](manage-domain-users.md) para obter as etapas.</span><span class="sxs-lookup"><span data-stu-id="c1fe2-112">See [Synchronize domain users to Microsoft](manage-domain-users.md) for the steps.</span></span>

## <a name="1-verify-mdm-authority-in-intune"></a><span data-ttu-id="c1fe2-113">1. Verifique a autoridade MDM no Intune</span><span class="sxs-lookup"><span data-stu-id="c1fe2-113">1. Verify MDM Authority in Intune</span></span>

<span data-ttu-id="c1fe2-114">Vá para o [Gerenciador de pontos de extremidade](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview) e, na página do Microsoft Intune, selecione registro de **dispositivo**e, na página **visão geral** , verifique se a **autoridade MDM** é o **Intune**.</span><span class="sxs-lookup"><span data-stu-id="c1fe2-114">Go to [Endpoint Manager](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview) and on the Microsoft Intune page, select **Device enrollment**, then on the **Overview** page, make sure **MDM authority** is **Intune**.</span></span>

- <span data-ttu-id="c1fe2-115">Se **MDM Authority** for **None**, clique na **autoridade MDM** para defini-la como **Intune**.</span><span class="sxs-lookup"><span data-stu-id="c1fe2-115">If **MDM authority** is **None**, click the **MDM authority** to set it to **Intune**.</span></span>
- <span data-ttu-id="c1fe2-116">Se o **MDM Authority** for o **Microsoft Office 365**, acesse **dispositivos**  >  **inscrever dispositivos** e usar a caixa de diálogo **Adicionar autoridade MDM** no direito de adicionar autoridade **MDM do Intune** (a caixa de diálogo **Adicionar autoridade MDM** só estará disponível se a **autoridade MDM** estiver definida como Microsoft Office 365).</span><span class="sxs-lookup"><span data-stu-id="c1fe2-116">If **MDM authority** is **Microsoft Office 365**,go to **Devices** > **Enroll devices** and use the **Add MDM authority** dialog on the right to add **Intune MDM** authority (the **Add MDM Authority** dialog is only available if the **MDM Authority** is set to Microsoft Office 365).</span></span>

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a><span data-ttu-id="c1fe2-117">2. Verifique se o Azure AD está habilitado para ingressar em computadores</span><span class="sxs-lookup"><span data-stu-id="c1fe2-117">2. Verify Azure AD is enabled for joining computers</span></span>

- <span data-ttu-id="c1fe2-118">Vá para o centro de administração em <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> e selecione **Azure Active Directory** (selecione Mostrar tudo se o Azure Active Directory não estiver visível) na lista de **centros de administração** .</span><span class="sxs-lookup"><span data-stu-id="c1fe2-118">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select **Azure Active Directory** (select Show all if Azure Active Directory is not visible) in the **Admin centers** list.</span></span> 
- <span data-ttu-id="c1fe2-119">No **centro de administração do Azure Active Directory**, vá para **Azure Active Directory** , escolha **dispositivos** e **configurações de dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="c1fe2-119">In the **Azure Active Directory admin center**, go to **Azure Active Directory** , choose **Devices** and then **Device settings**.</span></span>
- <span data-ttu-id="c1fe2-120">Verifique se**os usuários podem ingressar em dispositivos no Azure ad** está habilitado</span><span class="sxs-lookup"><span data-stu-id="c1fe2-120">Verify**Users may join devices to Azure AD** is enabled</span></span> 
    1. <span data-ttu-id="c1fe2-121">Para habilitar todos os usuários, defina como **todos**.</span><span class="sxs-lookup"><span data-stu-id="c1fe2-121">To enable all users, set to **All**.</span></span>
    2. <span data-ttu-id="c1fe2-122">Para habilitar usuários específicos, defina como **selecionado** para habilitar um grupo específico de usuários.</span><span class="sxs-lookup"><span data-stu-id="c1fe2-122">To enable specific users, set to **Selected** to enable a specific group of users.</span></span>
        - <span data-ttu-id="c1fe2-123">Adicione os usuários de domínio desejados sincronizados no Azure AD para um [grupo de segurança](../admin/create-groups/create-groups.md).</span><span class="sxs-lookup"><span data-stu-id="c1fe2-123">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        - <span data-ttu-id="c1fe2-124">Escolha **Selecionar grupos** para habilitar o escopo de usuário MDM para esse grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="c1fe2-124">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a><span data-ttu-id="c1fe2-125">3. Verifique se o Azure AD está habilitado para MDM</span><span class="sxs-lookup"><span data-stu-id="c1fe2-125">3. Verify Azure AD is enabled for MDM</span></span>

- <span data-ttu-id="c1fe2-126">Vá para o centro de administração em <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> e selecione Selecionar **ponto de extremidade gerenciar**o t (selecionar **Mostrar tudo** se o **Endpoint Manager** não estiver visível)</span><span class="sxs-lookup"><span data-stu-id="c1fe2-126">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select select **Endpoint Managemen**t (select **Show all** if **Endpoint Manager** is not visible)</span></span>
- <span data-ttu-id="c1fe2-127">No **centro de administração do Gerenciador de pontos de extremidade da Microsoft**, vá para **dispositivos**  >  **Windows**  >  **Windows Enrollment**  >  **registro automático**do registro do Windows do Windows.</span><span class="sxs-lookup"><span data-stu-id="c1fe2-127">In the **Microsoft Endpoint Manager admin center**, go to **Devices** > **Windows** > **Windows Enrollment** > **Automatic Enrollment**.</span></span>
- <span data-ttu-id="c1fe2-128">Verifique se o escopo de usuário MDM está habilitado.</span><span class="sxs-lookup"><span data-stu-id="c1fe2-128">Verify MDM user scope is enabled.</span></span>

    1. <span data-ttu-id="c1fe2-129">Para inscrever todos os computadores, defina como **todos** para registrar automaticamente todos os computadores de usuários que ingressaram no Azure AD e em novos computadores quando os usuários adicionam uma conta de trabalho ao Windows.</span><span class="sxs-lookup"><span data-stu-id="c1fe2-129">To enroll all computers, set to **All** to automatically enroll all user computers that are joined to Azure AD and new computers  when the users add a work account to Windows.</span></span>
    2. <span data-ttu-id="c1fe2-130">Definido como **alguns** para registrar os computadores de um grupo específico de usuários.</span><span class="sxs-lookup"><span data-stu-id="c1fe2-130">Set to **Some** to enroll the computers of a specific group of users.</span></span>
        -  <span data-ttu-id="c1fe2-131">Adicione os usuários de domínio desejados sincronizados no Azure AD para um [grupo de segurança](../admin/create-groups/create-groups.md).</span><span class="sxs-lookup"><span data-stu-id="c1fe2-131">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        -  <span data-ttu-id="c1fe2-132">Escolha **Selecionar grupos** para habilitar o escopo de usuário MDM para esse grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="c1fe2-132">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="4-create-the-required-resources"></a><span data-ttu-id="c1fe2-133">4. criar os recursos necessários</span><span class="sxs-lookup"><span data-stu-id="c1fe2-133">4. Create the required resources</span></span> 

<span data-ttu-id="c1fe2-134">A execução das tarefas necessárias para [Configurar o Azure ad Join híbrido](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) foi simplificada por meio do uso do cmdlet [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) encontrado no módulo [SecMgmt](https://www.powershellgallery.com/packages/SecMgmt) PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c1fe2-134">Performing the required tasks to [configure hybrid Azure AD join](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) has been simplified through the use of the [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet found in the [SecMgmt](https://www.powershellgallery.com/packages/SecMgmt) PowerShell module.</span></span> <span data-ttu-id="c1fe2-135">Quando você invocar este cmdlet, ele criará e configurará o ponto de conexão de serviço e a política de grupo necessários.</span><span class="sxs-lookup"><span data-stu-id="c1fe2-135">When you invoke this cmdlet it will create and configure the required service connection point and group policy.</span></span>

<span data-ttu-id="c1fe2-136">Você pode instalar este módulo chamando o seguinte em uma instância do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="c1fe2-136">You can install this module by invoking the following from an instance of PowerShell:</span></span>

```powershell
Install-Module SecMgmt
```

> [!IMPORTANT]
> <span data-ttu-id="c1fe2-137">É recomendável que você instale este módulo no Windows Server que executa o Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="c1fe2-137">It is recommended that you install this module on the Windows Server running Azure AD Connect.</span></span>

<span data-ttu-id="c1fe2-138">Para criar o ponto de conexão de serviço necessário e a política de grupo, você chamará o cmdlet [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) .</span><span class="sxs-lookup"><span data-stu-id="c1fe2-138">To create the required service connection point and group policy, you will invoke the  [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet.</span></span> <span data-ttu-id="c1fe2-139">Você precisará de suas credenciais de administrador global do Microsoft 365 Business Premium ao executar essa tarefa.</span><span class="sxs-lookup"><span data-stu-id="c1fe2-139">You will need your Microsoft 365 Business Premium global admin credentials when performing this task.</span></span> <span data-ttu-id="c1fe2-140">Quando estiver pronto para criar os recursos, chame o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c1fe2-140">When you are ready to create the resources, invoke the following:</span></span>

```powershell
PS C:\> Connect-SecMgmtAccount
PS C:\> Initialize-SecMgmtHybirdDeviceEnrollment -GroupPolicyDisplayName 'Device Management'
```

<span data-ttu-id="c1fe2-141">O primeiro comando estabelecerá uma conexão com a nuvem da Microsoft e, quando for solicitado, especifique suas credenciais de administrador global do Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="c1fe2-141">The first command will establish a connection with the Microsoft cloud, and when you are prompted, specify your Microsoft 365 Business Premium global admin credentials.</span></span>

## <a name="5-link-the-group-policy"></a><span data-ttu-id="c1fe2-142">5. vincular a política de grupo</span><span class="sxs-lookup"><span data-stu-id="c1fe2-142">5. Link the Group Policy</span></span>

1. <span data-ttu-id="c1fe2-143">No GPMC (console de gerenciamento de política de grupo), clique com o botão direito do mouse no local onde você deseja vincular a política e selecione *vincular um GPO existente...* no menu de contexto.</span><span class="sxs-lookup"><span data-stu-id="c1fe2-143">In the Group Policy Management Console (GPMC), right-click on the location where you want to link the policy and select *Link an existing GPO...* from the context menu.</span></span>
2. <span data-ttu-id="c1fe2-144">Selecione a política criada na etapa acima e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c1fe2-144">Select the policy created in the above step, then click **OK**.</span></span>

## <a name="get-the-latest-administrative-templates"></a><span data-ttu-id="c1fe2-145">Obter os modelos administrativos mais recentes</span><span class="sxs-lookup"><span data-stu-id="c1fe2-145">Get the latest Administrative Templates</span></span>

<span data-ttu-id="c1fe2-146">Se você não vir a política **habilitar o registro MDM automático usando as credenciais padrão do Azure ad**, talvez você não tenha o ADMX instalado para o Windows 10, a versão 1803, a versão 1809 ou a versão 1903.</span><span class="sxs-lookup"><span data-stu-id="c1fe2-146">If you do not see the policy **Enable automatic MDM enrollment using default Azure AD credentials**, it may be because you don’t have the ADMX installed for Windows 10, version 1803, version 1809, or version 1903.</span></span> <span data-ttu-id="c1fe2-147">Para corrigir o problema, siga estas etapas (Observação: o MDM. admx mais recente é compatível com versões anteriores):</span><span class="sxs-lookup"><span data-stu-id="c1fe2-147">To fix the issue, follow these steps (Note: the latest MDM.admx is backwards compatible):</span></span>

1.  <span data-ttu-id="c1fe2-148">Download: [modelos administrativos (. admx) para Windows 10 pode 2019 atualização (1903)](https://www.microsoft.com/download/details.aspx?id=58495&WT.mc_id=rss_alldownloads_all).</span><span class="sxs-lookup"><span data-stu-id="c1fe2-148">Download: [Administrative Templates (.admx) for Windows 10 May 2019 Update (1903)](https://www.microsoft.com/download/details.aspx?id=58495&WT.mc_id=rss_alldownloads_all).</span></span>
2.  <span data-ttu-id="c1fe2-149">Instale o pacote no controlador de domínio primário (PDC).</span><span class="sxs-lookup"><span data-stu-id="c1fe2-149">Install the package on the Primary Domain Controller (PDC).</span></span>
3.  <span data-ttu-id="c1fe2-150">Navegue, dependendo da versão para a pasta: C:\Arquivos de **programas (x86) \Microsoft Group Policy\Windows 10 de maio de 2019 Update (1903) v3**.</span><span class="sxs-lookup"><span data-stu-id="c1fe2-150">Navigate, depending on the version to the folder: **C:\Program Files (x86)\Microsoft Group Policy\Windows 10 May 2019 Update (1903) v3**.</span></span>
4.  <span data-ttu-id="c1fe2-151">Renomeie a pasta de **definições de política** no caminho acima para **PolicyDefinitions,**.</span><span class="sxs-lookup"><span data-stu-id="c1fe2-151">Rename the **Policy Definitions** folder in the above path to **PolicyDefinitions**.</span></span>
5.  <span data-ttu-id="c1fe2-152">Copie a pasta **PolicyDefinitions,** para **C:\Windows\SYSVOL\domain\Policies**.</span><span class="sxs-lookup"><span data-stu-id="c1fe2-152">Copy **PolicyDefinitions** folder to **C:\Windows\SYSVOL\domain\Policies**.</span></span> 
    -   <span data-ttu-id="c1fe2-153">Se você planeja usar um repositório de política central para o seu domínio inteiro, adicione o conteúdo de PolicyDefinitions, ali.</span><span class="sxs-lookup"><span data-stu-id="c1fe2-153">If you plan to use a central policy store for your entire domain, add the contents of PolicyDefinitions there.</span></span>
6.  <span data-ttu-id="c1fe2-154">Reinicie o controlador de domínio primário para que a política fique disponível.</span><span class="sxs-lookup"><span data-stu-id="c1fe2-154">Restart the Primary Domain Controller for the policy to be available.</span></span> <span data-ttu-id="c1fe2-155">Este procedimento também funcionará para qualquer versão futura.</span><span class="sxs-lookup"><span data-stu-id="c1fe2-155">This procedure will work for any future version as well.</span></span>

<span data-ttu-id="c1fe2-156">Neste ponto, você deve ser capaz de ver a política **habilitar o registro MDM automático usando as credenciais padrão do Azure ad** disponíveis.</span><span class="sxs-lookup"><span data-stu-id="c1fe2-156">At this point you should be able to see the policy **Enable automatic MDM enrollment using default Azure AD credentials** available.</span></span>
