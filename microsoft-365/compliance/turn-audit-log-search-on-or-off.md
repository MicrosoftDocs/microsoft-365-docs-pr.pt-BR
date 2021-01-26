---
title: Ativar ou desativar a pesquisa de log de auditoria
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: e893b19a-660c-41f2-9074-d3631c95a014
ms.custom: seo-marvel-apr2020
description: Como ativar ou desativar o recurso de pesquisa de log de auditoria no Centro de Conformidade e Segurança & para habilitar ou desabilitar a capacidade dos administradores de pesquisar o log de auditoria.
ms.openlocfilehash: 1f3da9671b9e5287d715a438a11b0a0eef164584
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/25/2021
ms.locfileid: "49976324"
---
# <a name="turn-audit-log-search-on-or-off"></a><span data-ttu-id="5f6ec-103">Ativar ou desativar a pesquisa de log de auditoria</span><span class="sxs-lookup"><span data-stu-id="5f6ec-103">Turn audit log search on or off</span></span>

<span data-ttu-id="5f6ec-104">O log de auditoria está ligado por padrão para organizações empresariais do Microsoft 365 e Office 365.</span><span class="sxs-lookup"><span data-stu-id="5f6ec-104">Audit logging is turned on by default for Microsoft 365 and Office 365 enterprise organizations.</span></span> <span data-ttu-id="5f6ec-105">Isso inclui organizações com assinaturas E3/G3 ou E5/G5.</span><span class="sxs-lookup"><span data-stu-id="5f6ec-105">This includes organizations with E3/G3 or E5/G5 subscriptions.</span></span> <span data-ttu-id="5f6ec-106">Quando a pesquisa de log de auditoria no centro de conformidade é 2013, a atividade de usuários e administradores da sua organização é registrada no log de auditoria e retida por 90 dias e até um ano, dependendo da licença atribuída aos usuários.</span><span class="sxs-lookup"><span data-stu-id="5f6ec-106">When audit log search in the compliance center is turned on, user and admin activity from your organization is recorded in the audit log and retained for 90 days, and up to one year depending on the license assigned to users.</span></span> <span data-ttu-id="5f6ec-107">No entanto, sua organização pode ter motivos para não desejar registrar e reter dados de log de auditoria.</span><span class="sxs-lookup"><span data-stu-id="5f6ec-107">However, your organization may have reasons for not wanting to record and retain audit log data.</span></span> <span data-ttu-id="5f6ec-108">Nesses casos, um administrador global pode optar por desativar a auditoria no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5f6ec-108">In those cases, a global admin may decide to turn off auditing in Microsoft 365.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5f6ec-109">Se você desativar a pesquisa de log de auditoria no Microsoft 365, não poderá usar a API da Atividade de Gerenciamento do Office 365 ou o Azure Sentinel para acessar os dados de auditoria da sua organização.</span><span class="sxs-lookup"><span data-stu-id="5f6ec-109">If you turn off audit log search in Microsoft 365, you can't use the Office 365 Management Activity API or Azure Sentinel to access auditing data for your organization.</span></span> <span data-ttu-id="5f6ec-110">Ao desligar a pesquisa de log de auditoria seguindo as etapas deste artigo, significa que nenhum resultado será retornado quando você pesquisar o log de auditoria usando o Centro de Conformidade do & de Segurança ou quando executar o cmdlet **Search-UnifiedAuditLog** no PowerShell do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="5f6ec-110">Turning off audit log search by following the steps in this article means that no results will be returned when you search the audit log using the Security & Compliance Center or when you run the **Search-UnifiedAuditLog** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="5f6ec-111">Isso também significa que os logs de auditoria não estarão disponíveis por meio da API da Atividade de Gerenciamento do Office 365 ou do Azure Sentinel.</span><span class="sxs-lookup"><span data-stu-id="5f6ec-111">This also means that audit logs won't be available through the Office 365 Management Activity API or Azure Sentinel.</span></span>
  
## <a name="before-you-turn-audit-log-search-on-or-off"></a><span data-ttu-id="5f6ec-112">Antes de ativar ou desativar a pesquisa de log de auditoria</span><span class="sxs-lookup"><span data-stu-id="5f6ec-112">Before you turn audit log search on or off</span></span>

- <span data-ttu-id="5f6ec-113">Você precisa ter a função Logs de Auditoria no Exchange Online para ativar ou desativar a pesquisa de log de auditoria em sua organização do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5f6ec-113">You have to be assigned the Audit Logs role in Exchange Online to turn audit log search on or off in your Microsoft 365 organization.</span></span> <span data-ttu-id="5f6ec-114">Por padrão, essa função é atribuída aos grupos de função Gerenciamento de Conformidade e Gerenciamento da Organização na página **Permissões** no Centro de administração do Exchange.</span><span class="sxs-lookup"><span data-stu-id="5f6ec-114">By default, this role is assigned to the Compliance Management and Organization Management role groups on the **Permissions** page in the Exchange admin center.</span></span> <span data-ttu-id="5f6ec-115">Os administradores globais no Microsoft 365 são membros do grupo de função Gerenciamento da Organização no Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="5f6ec-115">Global admins in Microsoft 365 are members of the Organization Management role group in Exchange Online.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="5f6ec-116">Os usuários devem ter permissões no Exchange Online para ativar ou desativar a pesquisa de log de auditoria.</span><span class="sxs-lookup"><span data-stu-id="5f6ec-116">Users have to be assigned permissions in Exchange Online to turn audit log search on or off.</span></span> <span data-ttu-id="5f6ec-117">Se você atribuir aos usuários  a função & Logs de Auditoria na página Permissões, no Centro de Conformidade e Segurança, eles não poderão ativar ou desativar a pesquisa de log de auditoria.</span><span class="sxs-lookup"><span data-stu-id="5f6ec-117">If you assign users the Audit Logs role on the **Permissions** page in the Security & Compliance Center, they won't be able to turn audit log search on or off.</span></span> <span data-ttu-id="5f6ec-118">Isso porque o cmdlet subjacente é um cmdlet do PowerShell do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="5f6ec-118">This is because the underlying cmdlet is an Exchange Online PowerShell cmdlet.</span></span> 
    
- <span data-ttu-id="5f6ec-119">Para obter instruções passo a passo sobre como pesquisar o log de auditoria, consulte Pesquisar o log de auditoria no Centro de Conformidade & [Segurança.](search-the-audit-log-in-security-and-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="5f6ec-119">For step-by-step instructions on searching the audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span> <span data-ttu-id="5f6ec-120">Para saber mais sobre a API da Atividade de Gerenciamento do Microsoft 365, confira Começar a trabalhar com APIs de Gerenciamento do [Microsoft 365.](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)</span><span class="sxs-lookup"><span data-stu-id="5f6ec-120">For more information about the Microsoft 365 Management Activity API, see [Get started with Microsoft 365 Management APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span>

- <span data-ttu-id="5f6ec-121">Para verificar se a pesquisa de log de auditoria está turned on, você pode executar o seguinte comando no PowerShell do Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="5f6ec-121">To verify that audit log search is turned on, you can run the following command in Exchange Online PowerShell:</span></span>

    ```powershell
    Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
    ```

    <span data-ttu-id="5f6ec-122">O valor da  `True` propriedade  _UnifiedAuditLogIngestionEnabled_ indica que a pesquisa de log de auditoria está acessível.</span><span class="sxs-lookup"><span data-stu-id="5f6ec-122">The value of  `True` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that audit log search is turned on.</span></span> 
    
## <a name="turn-on-audit-log-search"></a><span data-ttu-id="5f6ec-123">Ativar a pesquisa de log de auditoria</span><span class="sxs-lookup"><span data-stu-id="5f6ec-123">Turn on audit log search</span></span>

<span data-ttu-id="5f6ec-124">Se a pesquisa de log de auditoria não estiver ativar a sua organização, você poderá agará-la no centro de conformidade ou usando o PowerShell do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="5f6ec-124">If audit log search is not turned on for your organization, you can turn it on in the compliance center or by using Exchange Online PowerShell.</span></span> <span data-ttu-id="5f6ec-125">Pode levar várias horas depois de ativar a pesquisa de log de auditoria antes de poder retornar resultados ao pesquisar o log de auditoria.</span><span class="sxs-lookup"><span data-stu-id="5f6ec-125">It may take several hours after you turn on audit log search before you can return results when you search the audit log.</span></span>
  
### <a name="use-the-compliance-center-to-turn-on-audit-log-search"></a><span data-ttu-id="5f6ec-126">Usar o centro de conformidade para ativar a pesquisa de log de auditoria</span><span class="sxs-lookup"><span data-stu-id="5f6ec-126">Use the compliance center to turn on audit log search</span></span>

1. <span data-ttu-id="5f6ec-127">[Vá para o centro de conformidade](https://protection.office.com) e entre.</span><span class="sxs-lookup"><span data-stu-id="5f6ec-127">[Go to the compliance center](https://protection.office.com) and sign in.</span></span>

2. <span data-ttu-id="5f6ec-128">No centro de conformidade, vá para a **pesquisa**  >  **de log de Auditoria de Pesquisa.**</span><span class="sxs-lookup"><span data-stu-id="5f6ec-128">In the compliance center, go to **Search** > **Audit log search**.</span></span>

   <span data-ttu-id="5f6ec-129">Se a pesquisa de log de auditoria não estiver turned on para sua organização, uma faixa será exibida dizendo que a auditoria deve ser responsabilidade para registrar a atividade de usuários e administradores.</span><span class="sxs-lookup"><span data-stu-id="5f6ec-129">If audit log search is not turned on for your organization, a banner is displayed saying that auditing has to be turned on to record user and admin activity.</span></span>

3. <span data-ttu-id="5f6ec-130">Clique **em Ativar auditoria.**</span><span class="sxs-lookup"><span data-stu-id="5f6ec-130">Click **Turn on auditing**.</span></span>

    ![Clique em Ativar auditoria](../media/39a9d35f-88d0-4bbe-a962-0be2f838e2bf.png)
  
    <span data-ttu-id="5f6ec-132">A faixa é atualizada para dizer que o log de auditoria está sendo preparado e que você pode pesquisar a atividade de usuários e administradores em algumas horas.</span><span class="sxs-lookup"><span data-stu-id="5f6ec-132">The banner is updated to say the audit log is being prepared and that you can search for user and admin activity in a few hours.</span></span>

### <a name="use-powershell-to-turn-on-audit-log-search"></a><span data-ttu-id="5f6ec-133">Usar o PowerShell para ativar a pesquisa de log de auditoria</span><span class="sxs-lookup"><span data-stu-id="5f6ec-133">Use PowerShell to turn on audit log search</span></span>

1. [<span data-ttu-id="5f6ec-134">Conectar-se ao PowerShell do Exchange Online </span><span class="sxs-lookup"><span data-stu-id="5f6ec-134">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=396554)

2. <span data-ttu-id="5f6ec-135">Execute o seguinte comando do PowerShell para ativar a pesquisa de log de auditoria no Office 365.</span><span class="sxs-lookup"><span data-stu-id="5f6ec-135">Run the following PowerShell command to turn on audit log search in Office 365.</span></span>

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    <span data-ttu-id="5f6ec-136">Uma mensagem é exibida dizendo que pode levar até 60 minutos para que a alteração entre em vigor.</span><span class="sxs-lookup"><span data-stu-id="5f6ec-136">A message is displayed saying that it may take up to 60 minutes for the change to take effect.</span></span>
  
## <a name="turn-off-audit-log-search"></a><span data-ttu-id="5f6ec-137">Desativar a pesquisa de log de auditoria</span><span class="sxs-lookup"><span data-stu-id="5f6ec-137">Turn off audit log search</span></span>

<span data-ttu-id="5f6ec-138">Você precisa usar o PowerShell do Exchange Online para desativar a pesquisa de log de auditoria.</span><span class="sxs-lookup"><span data-stu-id="5f6ec-138">You have to use Exchange Online PowerShell to turn off audit log search.</span></span>
  
1. [<span data-ttu-id="5f6ec-139">Conectar-se ao PowerShell do Exchange Online </span><span class="sxs-lookup"><span data-stu-id="5f6ec-139">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=396554)

2. <span data-ttu-id="5f6ec-140">Execute o seguinte comando do PowerShell para desativar a pesquisa de log de auditoria.</span><span class="sxs-lookup"><span data-stu-id="5f6ec-140">Run the following PowerShell command to turn off audit log search.</span></span>

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. <span data-ttu-id="5f6ec-141">Após algum tempo, verifique se a pesquisa de log de auditoria está desativada (desabilitada).</span><span class="sxs-lookup"><span data-stu-id="5f6ec-141">After a while, verify that audit log search is turned off (disabled).</span></span> <span data-ttu-id="5f6ec-142">Há duas maneiras de fazer isso:</span><span class="sxs-lookup"><span data-stu-id="5f6ec-142">There are two ways to do this:</span></span>

    - <span data-ttu-id="5f6ec-143">No PowerShell do Exchange Online, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="5f6ec-143">In Exchange Online PowerShell, run the following command:</span></span>

      ```powershell
      Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
      ```

      <span data-ttu-id="5f6ec-144">O valor da  `False` propriedade  _UnifiedAuditLogIngestionEnabled_ indica que a pesquisa de log de auditoria está desligada.</span><span class="sxs-lookup"><span data-stu-id="5f6ec-144">The value of  `False` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that audit log search is turned off.</span></span> 

    - <span data-ttu-id="5f6ec-145">No centro [de conformidade,](https://protection.office.com)vá para pesquisa  \> **de log de auditoria de pesquisa.**</span><span class="sxs-lookup"><span data-stu-id="5f6ec-145">In the [compliance center](https://protection.office.com), go to **Search** \> **Audit log search**.</span></span>

      <span data-ttu-id="5f6ec-146">Uma faixa é exibida dizendo que a auditoria deve ser tiva para registrar a atividade do usuário e do administrador.</span><span class="sxs-lookup"><span data-stu-id="5f6ec-146">A banner is displayed saying that auditing has to be turned on in order to record user and admin activity.</span></span>
