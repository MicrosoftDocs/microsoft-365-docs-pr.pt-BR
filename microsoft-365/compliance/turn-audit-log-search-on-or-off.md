---
title: Ativar ou desativar a auditoria
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
description: Como ativar ou desativar o recurso de pesquisa de log de auditoria no centro de conformidade do Microsoft 365 para habilitar ou desabilitar a capacidade dos administradores de pesquisar o log de auditoria.
ms.openlocfilehash: 091331a40a2ab6bf3c05bb289d49f63ab2dd2794
ms.sourcegitcommit: 4f6ef4cd09c3ed36dc0be3702b0636bad6cff8a9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/26/2021
ms.locfileid: "52657724"
---
# <a name="turn-auditing-on-or-off"></a><span data-ttu-id="d00ed-103">Ativar ou desativar a auditoria</span><span class="sxs-lookup"><span data-stu-id="d00ed-103">Turn auditing on or off</span></span>

<span data-ttu-id="d00ed-104">O log de Auditoria é ativado por padrão para organizações empresariais Microsoft 365 e Office 365.</span><span class="sxs-lookup"><span data-stu-id="d00ed-104">Audit logging is turned on by default for Microsoft 365 and Office 365 enterprise organizations.</span></span> <span data-ttu-id="d00ed-105">Isto inclui organizações com assinaturas E3/G3 ou E5/G5.</span><span class="sxs-lookup"><span data-stu-id="d00ed-105">This includes organizations with E3/G3 or E5/G5 subscriptions.</span></span> <span data-ttu-id="d00ed-106">Quando a auditoria no centro de conformidade é ativeda, a atividade do usuário e do administrador da sua organização é registrada no log de auditoria e mantida por 90 dias e até um ano, dependendo da licença atribuída aos usuários.</span><span class="sxs-lookup"><span data-stu-id="d00ed-106">When auditing in the compliance center is turned on, user and admin activity from your organization is recorded in the audit log and retained for 90 days, and up to one year depending on the license assigned to users.</span></span> <span data-ttu-id="d00ed-107">No entanto, sua organização pode ter motivos para não querer registrar e reter dados de log de auditoria.</span><span class="sxs-lookup"><span data-stu-id="d00ed-107">However, your organization may have reasons for not wanting to record and retain audit log data.</span></span> <span data-ttu-id="d00ed-108">Nesses casos, um administrador global pode decidir desativar a auditoria no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d00ed-108">In those cases, a global admin may decide to turn off auditing in Microsoft 365.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d00ed-109">Se você desativar a auditoria no Microsoft 365, não poderá usar a API de Atividade de Gerenciamento Office 365 ou o Azure Sentinel para acessar dados de auditoria para sua organização.</span><span class="sxs-lookup"><span data-stu-id="d00ed-109">If you turn off auditing in Microsoft 365, you can't use the Office 365 Management Activity API or Azure Sentinel to access auditing data for your organization.</span></span> <span data-ttu-id="d00ed-110">Desligar a auditoria seguindo as etapas deste artigo significa que nenhum resultado será retornado quando você pesquisar o log de auditoria usando o Centro de Conformidade do & de Segurança ou quando você executar o cmdlet **Search-UnifiedAuditLog** no Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d00ed-110">Turning off auditing by following the steps in this article means that no results will be returned when you search the audit log using the Security & Compliance Center or when you run the **Search-UnifiedAuditLog** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="d00ed-111">Isso também significa que os logs de auditoria não estarão disponíveis por meio da API de Atividade de Gerenciamento Office 365 ou do Azure Sentinel.</span><span class="sxs-lookup"><span data-stu-id="d00ed-111">This also means that audit logs won't be available through the Office 365 Management Activity API or Azure Sentinel.</span></span>
  
## <a name="before-you-turn-auditing-on-or-off"></a><span data-ttu-id="d00ed-112">Antes de ativar ou desativar a auditoria</span><span class="sxs-lookup"><span data-stu-id="d00ed-112">Before you turn auditing on or off</span></span>

- <span data-ttu-id="d00ed-113">Você precisa ter a função Logs de Auditoria Exchange Online ativar ou desativar a auditoria em sua Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d00ed-113">You have to be assigned the Audit Logs role in Exchange Online to turn auditing on or off in your Microsoft 365 organization.</span></span> <span data-ttu-id="d00ed-114">Por padrão, essa função é atribuída aos grupos de  função Gerenciamento de Conformidade e Gerenciamento de Organização na página Permissões no Exchange de administração.</span><span class="sxs-lookup"><span data-stu-id="d00ed-114">By default, this role is assigned to the Compliance Management and Organization Management role groups on the **Permissions** page in the Exchange admin center.</span></span> <span data-ttu-id="d00ed-115">Os administradores globais no Microsoft 365 são membros do grupo de função Gerenciamento da Organização no Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="d00ed-115">Global admins in Microsoft 365 are members of the Organization Management role group in Exchange Online.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="d00ed-116">Os usuários devem ter permissões atribuídas Exchange Online ativar ou desativar a auditoria.</span><span class="sxs-lookup"><span data-stu-id="d00ed-116">Users have to be assigned permissions in Exchange Online to turn auditing on or off.</span></span> <span data-ttu-id="d00ed-117">Se você atribuir aos usuários  a função Logs de Auditoria na página Permissões no Centro de Conformidade & Segurança, eles não poderão ativar ou desativar a auditoria.</span><span class="sxs-lookup"><span data-stu-id="d00ed-117">If you assign users the Audit Logs role on the **Permissions** page in the Security & Compliance Center, they won't be able to turn auditing on or off.</span></span> <span data-ttu-id="d00ed-118">Isso porque o cmdlet subjacente é um cmdlet Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d00ed-118">This is because the underlying cmdlet is an Exchange Online PowerShell cmdlet.</span></span> 

- <span data-ttu-id="d00ed-119">Para obter instruções passo a passo sobre como pesquisar o log de auditoria, consulte Pesquisar o log de auditoria no Centro de Conformidade & [Segurança.](search-the-audit-log-in-security-and-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="d00ed-119">For step-by-step instructions on searching the audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span> <span data-ttu-id="d00ed-120">Para obter mais informações sobre a API Microsoft 365 Atividade de Gerenciamento, consulte [Get started with Microsoft 365 Management APIs](/office/office-365-management-api/get-started-with-office-365-management-apis).</span><span class="sxs-lookup"><span data-stu-id="d00ed-120">For more information about the Microsoft 365 Management Activity API, see [Get started with Microsoft 365 Management APIs](/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span>

- <span data-ttu-id="d00ed-121">Para verificar se a auditoria está 100%, você pode executar o seguinte comando Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d00ed-121">To verify that auditing is turned on, you can run the following command in Exchange Online PowerShell:</span></span>

    ```powershell
    Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
    ```

    <span data-ttu-id="d00ed-122">O valor da  `True` propriedade  _UnifiedAuditLogIngestionEnabled_ indica que a auditoria está ativa.</span><span class="sxs-lookup"><span data-stu-id="d00ed-122">The value of  `True` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that auditing is turned on.</span></span> 

## <a name="turn-on-auditing"></a><span data-ttu-id="d00ed-123">Ativar a auditoria</span><span class="sxs-lookup"><span data-stu-id="d00ed-123">Turn on auditing</span></span>

<span data-ttu-id="d00ed-124">Se a auditoria não estiver Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d00ed-124">If auditing is not turned on for your organization, you can turn it on in the compliance center or by using Exchange Online PowerShell.</span></span> <span data-ttu-id="d00ed-125">Pode levar várias horas após ativar a auditoria antes de poder retornar resultados ao pesquisar o log de auditoria.</span><span class="sxs-lookup"><span data-stu-id="d00ed-125">It may take several hours after you turn on auditing before you can return results when you search the audit log.</span></span>
  
### <a name="use-the-compliance-center-to-turn-on-auditing"></a><span data-ttu-id="d00ed-126">Usar o centro de conformidade para ativar a auditoria</span><span class="sxs-lookup"><span data-stu-id="d00ed-126">Use the compliance center to turn on auditing</span></span>

1. <span data-ttu-id="d00ed-127">Acesse <https://compliance.microsoft.com> e entre.</span><span class="sxs-lookup"><span data-stu-id="d00ed-127">Go to <https://compliance.microsoft.com> and sign in.</span></span>

2. <span data-ttu-id="d00ed-128">No painel de navegação esquerdo do centro de conformidade Microsoft 365, clique em **Mostrar tudo** e clique em **Auditoria**.</span><span class="sxs-lookup"><span data-stu-id="d00ed-128">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **Audit**.</span></span>

   <span data-ttu-id="d00ed-129">Se a auditoria não estiver 100% 100%, um banner será exibido solicitando que você inicie a gravação da atividade de usuário e administrador.</span><span class="sxs-lookup"><span data-stu-id="d00ed-129">If auditing is not turned on for your organization, a banner is displayed prompting you start recording user and admin activity.</span></span>

   ![Banner na página auditoria](../media/39a9d35f-88d0-4bbe-a962-0be2f838e2bf.png)

3. <span data-ttu-id="d00ed-131">Clique no **banner Iniciar gravação do usuário e da atividade do** administrador.</span><span class="sxs-lookup"><span data-stu-id="d00ed-131">Click the **Start recording user and admin activity** banner.</span></span>

   <span data-ttu-id="d00ed-132">Pode levar até 60 minutos para que a alteração entre em vigor.</span><span class="sxs-lookup"><span data-stu-id="d00ed-132">It may take up to 60 minutes for the change to take effect.</span></span>

### <a name="use-powershell-to-turn-on-auditing"></a><span data-ttu-id="d00ed-133">Usar o PowerShell para ativar a auditoria</span><span class="sxs-lookup"><span data-stu-id="d00ed-133">Use PowerShell to turn on auditing</span></span>

1. [<span data-ttu-id="d00ed-134">Conectar-se ao PowerShell do Exchange Online </span><span class="sxs-lookup"><span data-stu-id="d00ed-134">Connect to Exchange Online PowerShell</span></span>](/powershell/exchange/connect-to-exchange-online-powershell)

2. <span data-ttu-id="d00ed-135">Execute o seguinte comando do PowerShell para ativar a auditoria no Office 365.</span><span class="sxs-lookup"><span data-stu-id="d00ed-135">Run the following PowerShell command to turn on auditing in Office 365.</span></span>

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    <span data-ttu-id="d00ed-136">Uma mensagem é exibida dizendo que pode levar até 60 minutos para que a alteração entre em vigor.</span><span class="sxs-lookup"><span data-stu-id="d00ed-136">A message is displayed saying that it may take up to 60 minutes for the change to take effect.</span></span>
  
## <a name="turn-off-auditing"></a><span data-ttu-id="d00ed-137">Desativar a auditoria</span><span class="sxs-lookup"><span data-stu-id="d00ed-137">Turn off auditing</span></span>

<span data-ttu-id="d00ed-138">Você precisa usar o Exchange Online PowerShell para desativar a auditoria.</span><span class="sxs-lookup"><span data-stu-id="d00ed-138">You have to use Exchange Online PowerShell to turn off auditing.</span></span>
  
1. [<span data-ttu-id="d00ed-139">Conectar-se ao PowerShell do Exchange Online </span><span class="sxs-lookup"><span data-stu-id="d00ed-139">Connect to Exchange Online PowerShell</span></span>](/powershell/exchange/connect-to-exchange-online-powershell)

2. <span data-ttu-id="d00ed-140">Execute o seguinte comando do PowerShell para desativar a auditoria.</span><span class="sxs-lookup"><span data-stu-id="d00ed-140">Run the following PowerShell command to turn off auditing.</span></span>

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. <span data-ttu-id="d00ed-141">Depois de um tempo, verifique se a auditoria está desativada (desabilitada).</span><span class="sxs-lookup"><span data-stu-id="d00ed-141">After a while, verify that auditing is turned off (disabled).</span></span> <span data-ttu-id="d00ed-142">Há duas maneiras de fazer isso:</span><span class="sxs-lookup"><span data-stu-id="d00ed-142">There are two ways to do this:</span></span>

    - <span data-ttu-id="d00ed-143">No Exchange Online PowerShell, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="d00ed-143">In Exchange Online PowerShell, run the following command:</span></span>

      ```powershell
      Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
      ```

      <span data-ttu-id="d00ed-144">O valor da  `False`  _propriedade UnifiedAuditLogIngestionEnabled_ indica que a auditoria está desligada.</span><span class="sxs-lookup"><span data-stu-id="d00ed-144">The value of  `False` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that auditing is turned off.</span></span>

    - <span data-ttu-id="d00ed-145">Vá para a **página Auditoria** no centro Microsoft 365 conformidade.</span><span class="sxs-lookup"><span data-stu-id="d00ed-145">Go to the **Audit** page in the Microsoft 365 compliance center.</span></span>

      <span data-ttu-id="d00ed-146">Se a auditoria não estiver 100% 100%, um banner será exibido solicitando que você inicie a gravação da atividade de usuário e administrador.</span><span class="sxs-lookup"><span data-stu-id="d00ed-146">If auditing is not turned on for your organization, a banner is displayed prompting you start recording user and admin activity.</span></span>
