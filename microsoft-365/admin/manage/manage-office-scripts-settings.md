---
title: Gerenciar configurações dos Scripts do Office
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid: MET150
description: Saiba como gerenciar as configurações de Scripts do Office para usuários em sua organização.
ms.openlocfilehash: 75d0a9d9e98652fc11eab7e8a7d6c826be031f6e
ms.sourcegitcommit: 50f10d83fa21db8572adab90784146e5231e3321
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/30/2021
ms.locfileid: "50058418"
---
# <a name="manage-office-scripts-settings"></a><span data-ttu-id="4798d-103">Gerenciar configurações dos Scripts do Office</span><span class="sxs-lookup"><span data-stu-id="4798d-103">Manage Office Scripts settings</span></span>

<span data-ttu-id="4798d-104">Os scripts do Office permitem que os usuários automatizem tarefas gravando, editando e executando scripts no Excel na Web.</span><span class="sxs-lookup"><span data-stu-id="4798d-104">Office Scripts‎ allows users to automate tasks by recording, editing, and running scripts in ‎Excel‎ on the web.</span></span> <span data-ttu-id="4798d-105">Os scripts do Office funcionam com o Power Automate, e os usuários executarão scripts em planilhas usando o conector do Excel Online (Negócios).</span><span class="sxs-lookup"><span data-stu-id="4798d-105">‎Office Scripts‎ works with Power Automate, and users run scripts on workbooks by using the ‎Excel‎ Online (Business) connector.</span></span> <span data-ttu-id="4798d-106">Os administradores do Microsoft 365 podem gerenciar as configurações de Scripts do Office no Centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4798d-106">Microsoft 365 admins can manage Office Scripts settings from the Microsoft 365 admin center.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="4798d-107">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="4798d-107">Before you begin</span></span>

- <span data-ttu-id="4798d-108">Para gerenciar as configurações de Scripts do Office, você deve ser um administrador global. Para obter mais informações, consulte [Sobre funções de administrador.](../add-users/about-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="4798d-108">To manage Office Scripts settings, you must be a Global admin. For more information, see [About admin roles](../add-users/about-admin-roles.md).</span></span>

- <span data-ttu-id="4798d-109">Certifique-se de que os usuários em sua organização tenham uma licença válida para um plano comercial ou EDU do Microsoft 365 ou Office 365 que inclua acesso a aplicativos da área de trabalho do Office, como um dos seguintes planos:</span><span class="sxs-lookup"><span data-stu-id="4798d-109">Ensure users in your organization have a valid license for a Microsoft 365 or Office 365 commercial or EDU plan that includes access to Office desktop apps, such as one of the following plans:</span></span>

    - <span data-ttu-id="4798d-110">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="4798d-110">Microsoft 365 Business Standard</span></span>
    - <span data-ttu-id="4798d-111">Aplicativos do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="4798d-111">Microsoft 365 Apps for business</span></span>
    - <span data-ttu-id="4798d-112">Microsoft 365 Apps para empresas</span><span class="sxs-lookup"><span data-stu-id="4798d-112">Microsoft 365 Apps for enterprise</span></span>
    - <span data-ttu-id="4798d-113">Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="4798d-113">Office 365 E3</span></span>
    - <span data-ttu-id="4798d-114">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="4798d-114">Office 365 E5</span></span>
    - <span data-ttu-id="4798d-115">Office 365 A3</span><span class="sxs-lookup"><span data-stu-id="4798d-115">Office 365 A3</span></span>
    - <span data-ttu-id="4798d-116">Office 365 A5</span><span class="sxs-lookup"><span data-stu-id="4798d-116">Office 365 A5</span></span>

## <a name="manage-availability-of-office-scripts-and-sharing-of-scripts"></a><span data-ttu-id="4798d-117">Gerenciar a disponibilidade de scripts do Office e o compartilhamento de scripts</span><span class="sxs-lookup"><span data-stu-id="4798d-117">Manage availability of Office Scripts and sharing of scripts</span></span>

1. <span data-ttu-id="4798d-118">No Centro de administração do Microsoft 365, vá para a guia **Serviços** de Configurações da Organização \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">de Configurações.</a></span><span class="sxs-lookup"><span data-stu-id="4798d-118">In the Microsoft 365 admin center, go to the **Settings** \> **Org settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Services</a> tab.</span></span>

2. <span data-ttu-id="4798d-119">Selecione **Scripts do Office.**</span><span class="sxs-lookup"><span data-stu-id="4798d-119">Select **Office Scripts**.</span></span>

3. <span data-ttu-id="4798d-120">Os Scripts do Office estão ligado por padrão, e todos em sua organização podem acessar e usar o recurso e compartilhar scripts.</span><span class="sxs-lookup"><span data-stu-id="4798d-120">Office Scripts is turned on by default, and everyone in your organization can access and use the feature and share scripts.</span></span> <span data-ttu-id="4798d-121">Para desativar os Scripts do Office para sua organização, des limpe a caixa de seleção Permitir que os usuários automatizem suas tarefas no **Excel na Web.**</span><span class="sxs-lookup"><span data-stu-id="4798d-121">To turn off Office Scripts for your organization, clear the **Let users automate their tasks in Excel on the web** check box.</span></span>

4. <span data-ttu-id="4798d-122">Se você tiver desligado anteriormente os Scripts do Office para sua organização e quiser acioná-los novamente, selecione Permitir que os usuários automatizem suas tarefas no **Excel na Web** e especifique quem pode acessar e usar o recurso:</span><span class="sxs-lookup"><span data-stu-id="4798d-122">If you previously turned off Office Scripts for your organization and you want to turn it back on, select **Let users automate their tasks in Excel on the web**, and then specify who can access and use the feature:</span></span>

    - <span data-ttu-id="4798d-123">Para permitir que todos os usuários em sua organização acessem e usem scripts do Office, deixe **Todos** (o padrão) selecionado.</span><span class="sxs-lookup"><span data-stu-id="4798d-123">To allow all users in your organization to access and use Office Scripts, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="4798d-124">Para permitir que apenas membros de um grupo específico acessem e usem scripts do Office, selecione Grupo específico e insira o nome ou alias de email do grupo para adicioná-lo à lista de autorizações.</span><span class="sxs-lookup"><span data-stu-id="4798d-124">To allow only members of a specific group to access and use Office Scripts, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="4798d-125">Você pode adicionar apenas um grupo à lista de autorizações, e ele deve ser um dos seguintes tipos:</span><span class="sxs-lookup"><span data-stu-id="4798d-125">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="4798d-126">Grupo do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4798d-126">Microsoft 365 group</span></span>
        - <span data-ttu-id="4798d-127">Grupo de distribuição</span><span class="sxs-lookup"><span data-stu-id="4798d-127">Distribution group</span></span>
        - <span data-ttu-id="4798d-128">Grupo de segurança</span><span class="sxs-lookup"><span data-stu-id="4798d-128">Security group</span></span>
        - <span data-ttu-id="4798d-129">Grupo de segurança habilitado para email</span><span class="sxs-lookup"><span data-stu-id="4798d-129">Mail-enabled security group</span></span>
    
        <span data-ttu-id="4798d-130">Para saber mais sobre os diferentes tipos de grupos, consulte [Comparar grupos.](../create-groups/compare-groups.md)</span><span class="sxs-lookup"><span data-stu-id="4798d-130">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

5. <span data-ttu-id="4798d-131">Para permitir que os usuários com acesso aos Scripts do Office compartilhem seus scripts com outras pessoas em sua organização, selecione Permitir que os usuários com acesso aos scripts do Office compartilhem seus scripts com outras pessoas na **organização.**</span><span class="sxs-lookup"><span data-stu-id="4798d-131">To allow users with access to Office Scripts to share their scripts with others in your organization, select **Let users with access to Office Scripts share their scripts with others in the organization**.</span></span> <span data-ttu-id="4798d-132">O compartilhamento de scripts fora de uma organização não é permitido.</span><span class="sxs-lookup"><span data-stu-id="4798d-132">Sharing scripts outside of an organization is not allowed.</span></span>
 
    > [!NOTE]
    > <span data-ttu-id="4798d-133">Se você posteriormente desativar o compartilhamento de scripts para sua organização, os usuários ainda poderão executar scripts compartilhados anteriormente.</span><span class="sxs-lookup"><span data-stu-id="4798d-133">If you later turn off script sharing for your organization, users will still be able to run previously-shared scripts.</span></span>
 
6. <span data-ttu-id="4798d-134">Especifique quais usuários com acesso aos scripts do Office podem compartilhar seus scripts:</span><span class="sxs-lookup"><span data-stu-id="4798d-134">Specify which users with access to Office Scripts can share their scripts:</span></span>
    
    - <span data-ttu-id="4798d-135">Para permitir que todos os usuários com acesso aos Scripts do Office compartilhem seus scripts, deixe **Todos** (o padrão) selecionado.</span><span class="sxs-lookup"><span data-stu-id="4798d-135">To allow all users with access to Office Scripts to share their scripts, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="4798d-136">Para permitir que apenas membros de um grupo específico com acesso aos scripts do Office compartilhem seus scripts, selecione Grupo específico e insira o nome ou alias de email do grupo para adicioná-lo à lista de autorizações.</span><span class="sxs-lookup"><span data-stu-id="4798d-136">To allow only members of a specific group with access to Office Scripts to share their scripts, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="4798d-137">Você pode adicionar apenas um grupo à lista de autorizações, e ele deve ser um dos seguintes tipos:</span><span class="sxs-lookup"><span data-stu-id="4798d-137">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="4798d-138">Grupo do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4798d-138">Microsoft 365 group</span></span>
        - <span data-ttu-id="4798d-139">Grupo de distribuição</span><span class="sxs-lookup"><span data-stu-id="4798d-139">Distribution group</span></span>
        - <span data-ttu-id="4798d-140">Grupo de segurança</span><span class="sxs-lookup"><span data-stu-id="4798d-140">Security group</span></span>
        - <span data-ttu-id="4798d-141">Grupo de segurança habilitado para email</span><span class="sxs-lookup"><span data-stu-id="4798d-141">Mail-enabled security group</span></span>
    
        <span data-ttu-id="4798d-142">Para saber mais sobre os diferentes tipos de grupos, consulte [Comparar grupos.](../create-groups/compare-groups.md)</span><span class="sxs-lookup"><span data-stu-id="4798d-142">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

7. <span data-ttu-id="4798d-143">Para permitir que os usuários executem seus scripts do Office dentro de fluxos do Power Automate, selecione Permitir que os usuários com acesso aos scripts do Office executem **seus scripts com o Power Automate.**</span><span class="sxs-lookup"><span data-stu-id="4798d-143">To allow users to run their Office Scripts inside Power Automate flows, select **Let users with access to Office Scripts run their scripts with Power Automate**.</span></span> <span data-ttu-id="4798d-144">Isso permite que os usuários adicionem etapas de fluxo com a opção de **script Executar** do Conector do Excel [Online (Business).](/connectors/excelonlinebusiness)</span><span class="sxs-lookup"><span data-stu-id="4798d-144">This allows users to add flow steps with the [Excel Online (Business) Connector's](/connectors/excelonlinebusiness) **Run script** option.</span></span>

    - <span data-ttu-id="4798d-145">Para permitir que todos os usuários com acesso aos Scripts do Office usem seus scripts em fluxos, deixe **Todos** (o padrão) selecionado.</span><span class="sxs-lookup"><span data-stu-id="4798d-145">To allow all users with access to Office Scripts to use their scripts in flows, leave **Everyone** (the default) selected.</span></span>

    - <span data-ttu-id="4798d-146">Para permitir que apenas membros de um grupo específico com acesso aos Scripts do Office usem seus scripts em fluxos, selecione Grupo específico e insira o nome ou alias de email do grupo para adicioná-lo à lista de autorizações.</span><span class="sxs-lookup"><span data-stu-id="4798d-146">To allow only members of a specific group with access to Office Scripts to use their scripts in flows, select **Specific group**, and then enter the name or email alias of the group to add it to the allow list.</span></span> <span data-ttu-id="4798d-147">Você pode adicionar apenas um grupo à lista de autorizações, e ele deve ser um dos seguintes tipos:</span><span class="sxs-lookup"><span data-stu-id="4798d-147">You may add only one group to the allow list, and it must be one of the following types:</span></span>
        - <span data-ttu-id="4798d-148">Grupo do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4798d-148">Microsoft 365 group</span></span>
        - <span data-ttu-id="4798d-149">Grupo de distribuição</span><span class="sxs-lookup"><span data-stu-id="4798d-149">Distribution group</span></span>
        - <span data-ttu-id="4798d-150">Grupo de segurança</span><span class="sxs-lookup"><span data-stu-id="4798d-150">Security group</span></span>
        - <span data-ttu-id="4798d-151">Grupo de segurança habilitado para email</span><span class="sxs-lookup"><span data-stu-id="4798d-151">Mail-enabled security group</span></span>

        <span data-ttu-id="4798d-152">Para saber mais sobre os diferentes tipos de grupos, consulte [Comparar grupos.](../create-groups/compare-groups.md)</span><span class="sxs-lookup"><span data-stu-id="4798d-152">To learn more about the different types of groups, see [Compare groups](../create-groups/compare-groups.md).</span></span>

    - <span data-ttu-id="4798d-153">Para saber mais sobre como usar scripts do Office com o Power Automate, incluindo como suas políticas de prevenção contra perda de dados podem ser impactadas, confira Executar scripts do Office com [o Power Automate.](/office/dev/scripts/develop/power-automate-integration)</span><span class="sxs-lookup"><span data-stu-id="4798d-153">To learn more about using Office Scripts with Power Automate, including how your data loss prevention policies may be impacted, see [Run Office Scripts with Power Automate](/office/dev/scripts/develop/power-automate-integration).</span></span>

8. <span data-ttu-id="4798d-154">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="4798d-154">Select **Save**.</span></span>

    <span data-ttu-id="4798d-155">Pode levar até 48 horas para que as alterações nas configurações de Scripts do Office entre em vigor.</span><span class="sxs-lookup"><span data-stu-id="4798d-155">It can take up to 48 hours for changes to Office Scripts settings to take effect.</span></span>

## <a name="next-steps"></a><span data-ttu-id="4798d-156">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="4798d-156">Next steps</span></span>

<span data-ttu-id="4798d-157">Como os Scripts do Office funcionam com o Power Automate, recomendamos que você revise suas políticas de prevenção contra perda de dados (DLP) existentes para garantir que os dados da sua organização permaneçam protegidos enquanto os usuários usam scripts do Office.</span><span class="sxs-lookup"><span data-stu-id="4798d-157">Because Office Scripts works with Power Automate, we recommend that you review your existing data loss prevention (DLP) policies to ensure your organization's data remains protected while users use ‎Office Scripts‎.</span></span> <span data-ttu-id="4798d-158">Para obter mais informações, consulte [Políticas de prevenção contra perda de dados (DLP).](/power-automate/prevent-data-loss)</span><span class="sxs-lookup"><span data-stu-id="4798d-158">For more information, see [Data loss prevention (DLP) policies](/power-automate/prevent-data-loss).</span></span>

## <a name="related-content"></a><span data-ttu-id="4798d-159">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="4798d-159">Related content</span></span>

<span data-ttu-id="4798d-160">[Documentação técnica de Scripts do Office](/office/dev/scripts/) (página de link)</span><span class="sxs-lookup"><span data-stu-id="4798d-160">[Office Scripts technical documentation](/office/dev/scripts/) (link page)</span></span>\
<span data-ttu-id="4798d-161">[Introdução aos scripts do Office no Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (artigo)</span><span class="sxs-lookup"><span data-stu-id="4798d-161">[Introduction to Office Scripts in Excel](https://support.microsoft.com/office/9fbe283d-adb8-4f13-a75b-a81c6baf163a) (article)</span></span>\
<span data-ttu-id="4798d-162">[Compartilhando scripts do Office no Excel para a Web](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (artigo)</span><span class="sxs-lookup"><span data-stu-id="4798d-162">[Sharing Office Scripts in Excel for the Web](https://support.microsoft.com/office/226eddbc-3a44-4540-acfe-fccda3d1122b) (article)</span></span>\
<span data-ttu-id="4798d-163">[Gravar, editar e criar scripts do Office no Excel na Web](/office/dev/scripts/tutorials/excel-tutorial) (artigo)</span><span class="sxs-lookup"><span data-stu-id="4798d-163">[Record, edit, and create Office Scripts in Excel on the web](/office/dev/scripts/tutorials/excel-tutorial) (article)</span></span>
