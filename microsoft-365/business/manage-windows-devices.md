---
title: Habilitar dispositivos Windows 10 de domínio a serem gerenciados pelo Microsoft 365 para empresas
f1.keywords:
- CSH
ms.author: efrene
author: efrene
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
description: Saiba como habilitar Microsoft 365 proteger os dispositivos locais ingressados no Active-Directory Windows 10 em apenas algumas etapas.
ms.openlocfilehash: f16962dd3c33c3c228da507bc5c4a902d76a8a08
ms.sourcegitcommit: b0d3abbccf4dd37e32d69664d3ebc9ab8dea760d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/21/2021
ms.locfileid: "52593884"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a><span data-ttu-id="b9ce0-103">Habilitar dispositivos Windows 10 de domínio a serem gerenciados por Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="b9ce0-103">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium</span></span>

<span data-ttu-id="b9ce0-104">Se a sua organização usa o Windows Active Directory no local, você pode configurar um Microsoft 365 Business Premium para proteger seus dispositivos Windows 10, enquanto ainda mantém o acesso a recursos locais que exigem autenticação local.</span><span class="sxs-lookup"><span data-stu-id="b9ce0-104">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business Premium to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span>
<span data-ttu-id="b9ce0-105">Para configurar essa proteção, você pode implementar **dispositivos ingressados no Azure AD híbridos.**</span><span class="sxs-lookup"><span data-stu-id="b9ce0-105">To set up this protection, you can implement **Hybrid Azure AD joined devices**.</span></span> <span data-ttu-id="b9ce0-106">Esses dispositivos são ingressados no Active Directory local e no Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b9ce0-106">These devices are joined to both your on-premises Active Directory and your Azure Active Directory.</span></span>

<span data-ttu-id="b9ce0-107">Este vídeo descreve as etapas de como configurar isso para o cenário mais comum, que também é detalhado nas etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="b9ce0-107">This video describes the steps for how to set this up for the most common scenario, which is also detailed in the steps that follow.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="before-you-get-started-make-sure-you-complete-these-steps"></a><span data-ttu-id="b9ce0-108">Antes de começar, certifique-se de concluir estas etapas:</span><span class="sxs-lookup"><span data-stu-id="b9ce0-108">Before you get started, make sure you complete these steps:</span></span>
- <span data-ttu-id="b9ce0-109">Sincronizar usuários com o Azure AD com o Azure AD Conexão.</span><span class="sxs-lookup"><span data-stu-id="b9ce0-109">Synchronize users to Azure AD with Azure AD Connect.</span></span>
- <span data-ttu-id="b9ce0-110">Conclua a sincronização da UO (Unidade Organizacional) do Azure A Conexão D.</span><span class="sxs-lookup"><span data-stu-id="b9ce0-110">Complete Azure AD Connect Organizational Unit (OU) sync.</span></span>
- <span data-ttu-id="b9ce0-111">Certifique-se de que todos os usuários de domínio sincronizados tenham licenças para Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="b9ce0-111">Make sure all the domain users you sync have licenses to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="b9ce0-112">Consulte [Sincronizar usuários de domínio com a Microsoft](manage-domain-users.md) para ver as etapas.</span><span class="sxs-lookup"><span data-stu-id="b9ce0-112">See [Synchronize domain users to Microsoft](manage-domain-users.md) for the steps.</span></span>

## <a name="1-verify-mdm-authority-in-intune"></a><span data-ttu-id="b9ce0-113">1. Verifique a autoridade MDM no Intune</span><span class="sxs-lookup"><span data-stu-id="b9ce0-113">1. Verify MDM Authority in Intune</span></span>

<span data-ttu-id="b9ce0-114">Vá para [Endpoint Manager](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview) e, na página Microsoft Intune, selecione Registro de  dispositivo **,** em seguida, na página Visão geral, certifique-se de que a autoridade **MDM** seja **o Intune**.</span><span class="sxs-lookup"><span data-stu-id="b9ce0-114">Go to [Endpoint Manager](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview) and on the Microsoft Intune page, select **Device enrollment**, then on the **Overview** page, make sure **MDM authority** is **Intune**.</span></span>

- <span data-ttu-id="b9ce0-115">Se **a autoridade MDM** for **None**, clique na **autoridade MDM** para defini-la como **Intune**.</span><span class="sxs-lookup"><span data-stu-id="b9ce0-115">If **MDM authority** is **None**, click the **MDM authority** to set it to **Intune**.</span></span>
- <span data-ttu-id="b9ce0-116">Se **a autoridade MDM** for Microsoft Office 365 ,vá para Dispositivos Registrar dispositivos e use **a** caixa de diálogo Adicionar autoridade MDM à direita para adicionar autoridade  >   MDM do **Intune** (a caixa de diálogo **Adicionar Autoridade MDM** só estará disponível se a **Autoridade MDM** estiver definida como Microsoft Office 365). </span><span class="sxs-lookup"><span data-stu-id="b9ce0-116">If **MDM authority** is **Microsoft Office 365**,go to **Devices** > **Enroll devices** and use the **Add MDM authority** dialog on the right to add **Intune MDM** authority (the **Add MDM Authority** dialog is only available if the **MDM Authority** is set to Microsoft Office 365).</span></span>

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a><span data-ttu-id="b9ce0-117">2. Verifique se o Azure AD está habilitado para ingressar em computadores</span><span class="sxs-lookup"><span data-stu-id="b9ce0-117">2. Verify Azure AD is enabled for joining computers</span></span>

- <span data-ttu-id="b9ce0-118">Vá para o centro de administração em e selecione Azure Active Directory (selecione Mostrar tudo se Azure Active Directory não estiver visível) na <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> lista Centros **de** administração. </span><span class="sxs-lookup"><span data-stu-id="b9ce0-118">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select **Azure Active Directory** (select Show all if Azure Active Directory is not visible) in the **Admin centers** list.</span></span> 
- <span data-ttu-id="b9ce0-119">No centro **Azure Active Directory de administração,** vá **para Azure Active Directory,** escolha **Dispositivos** e, em seguida, **Configurações do dispositivo.**</span><span class="sxs-lookup"><span data-stu-id="b9ce0-119">In the **Azure Active Directory admin center**, go to **Azure Active Directory** , choose **Devices** and then **Device settings**.</span></span>
- <span data-ttu-id="b9ce0-120">Verificar **se os usuários podem ingressar em dispositivos no Azure AD** está habilitado</span><span class="sxs-lookup"><span data-stu-id="b9ce0-120">Verify **Users may join devices to Azure AD** is enabled</span></span> 
    1. <span data-ttu-id="b9ce0-121">Para habilitar todos os usuários, de acordo com **All**.</span><span class="sxs-lookup"><span data-stu-id="b9ce0-121">To enable all users, set to **All**.</span></span>
    2. <span data-ttu-id="b9ce0-122">Para habilitar usuários específicos, de acordo **com Selected** para habilitar um grupo específico de usuários.</span><span class="sxs-lookup"><span data-stu-id="b9ce0-122">To enable specific users, set to **Selected** to enable a specific group of users.</span></span>
        - <span data-ttu-id="b9ce0-123">Adicione os usuários de domínio desejados sincronizados no Azure AD a um grupo [de segurança](../admin/create-groups/create-groups.md).</span><span class="sxs-lookup"><span data-stu-id="b9ce0-123">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        - <span data-ttu-id="b9ce0-124">Escolha **Selecionar grupos** para habilitar o escopo de usuário MDM para esse grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="b9ce0-124">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a><span data-ttu-id="b9ce0-125">3. Verifique se o Azure AD está habilitado para o MDM</span><span class="sxs-lookup"><span data-stu-id="b9ce0-125">3. Verify Azure AD is enabled for MDM</span></span>

- <span data-ttu-id="b9ce0-126">Vá para o centro de administração em e selecione Gerenciar Pontos de Extremidade t (selecione Mostrar tudo se Endpoint Manager <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> não estiver visível)   </span><span class="sxs-lookup"><span data-stu-id="b9ce0-126">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select select **Endpoint Managemen** t (select **Show all** if **Endpoint Manager** is not visible)</span></span>
- <span data-ttu-id="b9ce0-127">No centro **de administração Microsoft Endpoint Manager**, vá para **Dispositivos**  >  **Windows**  >  **Windows Registro** Automático de  >  **Registro.**</span><span class="sxs-lookup"><span data-stu-id="b9ce0-127">In the **Microsoft Endpoint Manager admin center**, go to **Devices** > **Windows** > **Windows Enrollment** > **Automatic Enrollment**.</span></span>
- <span data-ttu-id="b9ce0-128">Verifique se o escopo do usuário do MDM está habilitado.</span><span class="sxs-lookup"><span data-stu-id="b9ce0-128">Verify MDM user scope is enabled.</span></span>

    1. <span data-ttu-id="b9ce0-129">Para registrar todos os  computadores, desmarco como Todos para registrar automaticamente todos os computadores de usuários que estão ingressados no Azure AD e novos computadores quando os usuários adicionarem uma conta de trabalho a Windows.</span><span class="sxs-lookup"><span data-stu-id="b9ce0-129">To enroll all computers, set to **All** to automatically enroll all user computers that are joined to Azure AD and new computers  when the users add a work account to Windows.</span></span>
    2. <span data-ttu-id="b9ce0-130">De definida **como Alguns** para registrar os computadores de um grupo específico de usuários.</span><span class="sxs-lookup"><span data-stu-id="b9ce0-130">Set to **Some** to enroll the computers of a specific group of users.</span></span>
        -  <span data-ttu-id="b9ce0-131">Adicione os usuários de domínio desejados sincronizados no Azure AD a um grupo [de segurança](../admin/create-groups/create-groups.md).</span><span class="sxs-lookup"><span data-stu-id="b9ce0-131">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        -  <span data-ttu-id="b9ce0-132">Escolha **Selecionar grupos** para habilitar o escopo de usuário MDM para esse grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="b9ce0-132">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="4-create-the-required-resources"></a><span data-ttu-id="b9ce0-133">4. Crie os recursos necessários</span><span class="sxs-lookup"><span data-stu-id="b9ce0-133">4. Create the required resources</span></span> 

<span data-ttu-id="b9ce0-134">A execução das tarefas necessárias para configurar a junção híbrida do [Azure AD](/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) foi simplificada por meio do uso do cmdlet [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) encontrado no módulo [SecMgmt](https://www.powershellgallery.com/packages/SecMgmt) PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b9ce0-134">Performing the required tasks to [configure hybrid Azure AD join](/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) has been simplified through the use of the [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet found in the [SecMgmt](https://www.powershellgallery.com/packages/SecMgmt) PowerShell module.</span></span> <span data-ttu-id="b9ce0-135">Quando você invocar esse cmdlet, ele criará e configurará o ponto de conexão de serviço necessário e a política de grupo.</span><span class="sxs-lookup"><span data-stu-id="b9ce0-135">When you invoke this cmdlet it will create and configure the required service connection point and group policy.</span></span>

<span data-ttu-id="b9ce0-136">Você pode instalar este módulo invocando o seguinte de uma instância do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b9ce0-136">You can install this module by invoking the following from an instance of PowerShell:</span></span>

```powershell
Install-Module SecMgmt
```

> [!IMPORTANT]
> <span data-ttu-id="b9ce0-137">É recomendável instalar esse módulo no servidor Windows que executa o Azure AD Conexão.</span><span class="sxs-lookup"><span data-stu-id="b9ce0-137">It is recommended that you install this module on the Windows Server running Azure AD Connect.</span></span>

<span data-ttu-id="b9ce0-138">Para criar o ponto de conexão de serviço necessário e a política de grupo, você invocará o cmdlet [Initialize-SecMgmtHybirdDeviceEnrollment.](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md)</span><span class="sxs-lookup"><span data-stu-id="b9ce0-138">To create the required service connection point and group policy, you will invoke the  [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet.</span></span> <span data-ttu-id="b9ce0-139">Você precisará de suas Microsoft 365 Business Premium de administrador global ao executar essa tarefa.</span><span class="sxs-lookup"><span data-stu-id="b9ce0-139">You will need your Microsoft 365 Business Premium global admin credentials when performing this task.</span></span> <span data-ttu-id="b9ce0-140">Quando estiver pronto para criar os recursos, invoque o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b9ce0-140">When you are ready to create the resources, invoke the following:</span></span>

```powershell
PS C:\> Connect-SecMgmtAccount
PS C:\> Initialize-SecMgmtHybirdDeviceEnrollment -GroupPolicyDisplayName 'Device Management'
```

<span data-ttu-id="b9ce0-141">O primeiro comando estabelecerá uma conexão com a nuvem da Microsoft e, quando você for solicitado, especifique suas Microsoft 365 Business Premium de administrador global.</span><span class="sxs-lookup"><span data-stu-id="b9ce0-141">The first command will establish a connection with the Microsoft cloud, and when you are prompted, specify your Microsoft 365 Business Premium global admin credentials.</span></span>

## <a name="5-link-the-group-policy"></a><span data-ttu-id="b9ce0-142">5. Vincular a Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="b9ce0-142">5. Link the Group Policy</span></span>

1. <span data-ttu-id="b9ce0-143">No Console de Gerenciamento de Política de Grupo (GPMC), clique com o botão direito do mouse no local onde você deseja vincular a política e selecione Vincular um *GPO existente...* no menu de contexto.</span><span class="sxs-lookup"><span data-stu-id="b9ce0-143">In the Group Policy Management Console (GPMC), right-click on the location where you want to link the policy and select *Link an existing GPO...* from the context menu.</span></span>
2. <span data-ttu-id="b9ce0-144">Selecione a política criada na etapa acima e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="b9ce0-144">Select the policy created in the above step, then click **OK**.</span></span>

## <a name="get-the-latest-administrative-templates"></a><span data-ttu-id="b9ce0-145">Obter os modelos administrativos mais recentes</span><span class="sxs-lookup"><span data-stu-id="b9ce0-145">Get the latest Administrative Templates</span></span>

<span data-ttu-id="b9ce0-146">Se você não vir a política Habilitar o registro automático do MDM usando credenciais padrão do **Azure AD**, pode ser porque você não tem o ADMX instalado para Windows 10, versão 1803 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="b9ce0-146">If you do not see the policy **Enable automatic MDM enrollment using default Azure AD credentials**, it may be because you don’t have the ADMX installed for Windows 10, version 1803, or later.</span></span> <span data-ttu-id="b9ce0-147">Para corrigir o problema, siga estas etapas (Observação: o MDM.admx mais recente é compatível com versões anteriores):</span><span class="sxs-lookup"><span data-stu-id="b9ce0-147">To fix the issue, follow these steps (Note: the latest MDM.admx is backwards compatible):</span></span>

1.  <span data-ttu-id="b9ce0-148">Download: Modelos Administrativos (.admx) para Windows 10 atualização de outubro de [2020 (20H2)](https://www.microsoft.com/download/102157).</span><span class="sxs-lookup"><span data-stu-id="b9ce0-148">Download: [Administrative Templates (.admx) for Windows 10 October 2020 Update (20H2)](https://www.microsoft.com/download/102157).</span></span>
2.  <span data-ttu-id="b9ce0-149">Instale o pacote em um Controlador de Domínio.</span><span class="sxs-lookup"><span data-stu-id="b9ce0-149">Install the package on a Domain Controller.</span></span>
3.  <span data-ttu-id="b9ce0-150">Navegue, dependendo da versão Modelos Administrativos para a pasta: C:\Arquivos de Programas (x86)\Política de Grupo da Microsoft\Windows 10 atualização de outubro de **2020 (20H2)**.</span><span class="sxs-lookup"><span data-stu-id="b9ce0-150">Navigate, depending on the Administrative Templates version to the folder: **C:\Program Files (x86)\Microsoft Group Policy\Windows 10 October 2020 Update (20H2)**.</span></span>
4.  <span data-ttu-id="b9ce0-151">Renomeie a **pasta Definições de** Política no caminho acima para **PolicyDefinitions**.</span><span class="sxs-lookup"><span data-stu-id="b9ce0-151">Rename the **Policy Definitions** folder in the above path to **PolicyDefinitions**.</span></span>
5.  <span data-ttu-id="b9ce0-152">Copie a **pasta PolicyDefinitions** para seu compartilhamento SYSVOL, por padrão localizado em **C:\Windows\SYSVOL\domain\Policies**.</span><span class="sxs-lookup"><span data-stu-id="b9ce0-152">Copy the **PolicyDefinitions** folder to your SYSVOL share, by default located at **C:\Windows\SYSVOL\domain\Policies**.</span></span> 
    -   <span data-ttu-id="b9ce0-153">Se você planeja usar um armazenamento de política central para todo o seu domínio, adicione o conteúdo de PolicyDefinitions lá.</span><span class="sxs-lookup"><span data-stu-id="b9ce0-153">If you plan to use a central policy store for your entire domain, add the contents of PolicyDefinitions there.</span></span>
6.  <span data-ttu-id="b9ce0-154">Caso você tenha vários Controladores de Domínio, aguarde que o SYSVOL replique para que as políticas sejam disponibilizadas.</span><span class="sxs-lookup"><span data-stu-id="b9ce0-154">In case you have several Domain Controllers, wait for SYSVOL to replicate for the policies to be available.</span></span> <span data-ttu-id="b9ce0-155">Este procedimento funcionará para qualquer versão futura dos Modelos Administrativos também.</span><span class="sxs-lookup"><span data-stu-id="b9ce0-155">This procedure will work for any future version of the Administrative Templates as well.</span></span>

<span data-ttu-id="b9ce0-156">Neste ponto, você deve ser capaz de ver a política Habilitar o registro automático do MDM usando credenciais padrão do **Azure AD** disponíveis.</span><span class="sxs-lookup"><span data-stu-id="b9ce0-156">At this point you should be able to see the policy **Enable automatic MDM enrollment using default Azure AD credentials** available.</span></span>

## <a name="related-content"></a><span data-ttu-id="b9ce0-157">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="b9ce0-157">Related content</span></span>

<span data-ttu-id="b9ce0-158">[Sincronizar usuários de domínio para Microsoft 365](manage-domain-users.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="b9ce0-158">[Synchronize domain users to Microsoft 365](manage-domain-users.md) (article)</span></span>

<span data-ttu-id="b9ce0-159">[Criar um grupo no centro de administração](../admin/create-groups/create-groups.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="b9ce0-159">[Create a group in the admin center](../admin/create-groups/create-groups.md) (article)</span></span>

<span data-ttu-id="b9ce0-160">[Tutorial: Configure hybrid Azure Active Directory join for managed domains](/azure/active-directory/devices/hybrid-azuread-join-managed-domains.md) (article)</span><span class="sxs-lookup"><span data-stu-id="b9ce0-160">[Tutorial: Configure hybrid Azure Active Directory join for managed domains](/azure/active-directory/devices/hybrid-azuread-join-managed-domains.md) (article)</span></span>