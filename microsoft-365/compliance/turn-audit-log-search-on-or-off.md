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
description: Você pode ativar o recurso de pesquisa de log de auditoria no centro de conformidade de & de segurança. Se você mudar de ideia, poderá desativar se estiver desligado a qualquer momento. Quando a pesquisa de log de auditoria está desativada, os administradores não podem pesquisar o log de auditoria do Microsoft 365 para atividades de usuário e administrador em sua organização.
ms.openlocfilehash: f3d88f62f466d9c868dfc6addb5865e144f5223b
ms.sourcegitcommit: 56772bed89516cebc5eb370e292ccfbb4889cb38
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2020
ms.locfileid: "44330785"
---
# <a name="turn-audit-log-search-on-or-off"></a><span data-ttu-id="67ced-105">Ativar ou desativar a pesquisa de log de auditoria</span><span class="sxs-lookup"><span data-stu-id="67ced-105">Turn audit log search on or off</span></span>

<span data-ttu-id="67ced-106">Você (ou outro administrador) deve ativar o log de auditoria antes de começar a pesquisar o log de auditoria.</span><span class="sxs-lookup"><span data-stu-id="67ced-106">You (or another admin) must turn on audit logging before you can start searching the audit log.</span></span> <span data-ttu-id="67ced-107">Quando a pesquisa de log de auditoria no centro de conformidade do & de segurança está ativada, a atividade do usuário e do administrador de sua organização é registrada no log de auditoria e mantida por 90 dias, e até um ano, dependendo da licença atribuída aos usuários.</span><span class="sxs-lookup"><span data-stu-id="67ced-107">When audit log search in the Security & Compliance Center is turned on, user and admin activity from your organization is recorded in the audit log and retained for 90 days, and up to one year depending on the license assigned to users.</span></span> <span data-ttu-id="67ced-108">No entanto, sua organização pode ter motivos para não querer gravar e reter dados de log de auditoria.</span><span class="sxs-lookup"><span data-stu-id="67ced-108">However, your organization may have reasons for not wanting to record and retain audit log data.</span></span> <span data-ttu-id="67ced-109">Nesses casos, um administrador global pode decidir desativar a auditoria no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="67ced-109">In those cases, a global admin may decide to turn off auditing in Microsoft 365.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="67ced-110">Se você desativar a pesquisa de log de auditoria no Microsoft 365, não será possível usar a API da atividade de gerenciamento do Office 365 ou o Azure Sentinel para acessar os dados de auditoria da sua organização.</span><span class="sxs-lookup"><span data-stu-id="67ced-110">If you turn off audit log search in Microsoft 365, you can't use the Office 365 Management Activity API or Azure Sentinel to access auditing data for your organization.</span></span> <span data-ttu-id="67ced-111">Desativando a pesquisa de log de auditoria seguindo as etapas deste artigo significa que nenhum resultado será retornado quando você pesquisar o log de auditoria usando o centro de conformidade de & de segurança ou quando executar o cmdlet **Search-UnifiedAuditLog** no PowerShell do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="67ced-111">Turning off audit log search by following the steps in this article means that no results will be returned when you search the audit log using the Security & Compliance Center or when you run the **Search-UnifiedAuditLog** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="67ced-112">Isso também significa que os logs de auditoria não estarão disponíveis por meio da API de atividade de gerenciamento do Office 365 ou do Azure Sentinel.</span><span class="sxs-lookup"><span data-stu-id="67ced-112">This also means that audit logs won't be available through the Office 365 Management Activity API or Azure Sentinel.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="67ced-113">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="67ced-113">Before you begin</span></span>

- <span data-ttu-id="67ced-114">Você precisa receber a função de logs de auditoria no Exchange Online para ativar ou desativar a pesquisa de log de auditoria na sua organização do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="67ced-114">You have to be assigned the Audit Logs role in Exchange Online to turn audit log search on or off in your Microsoft 365 organization.</span></span> <span data-ttu-id="67ced-115">Por padrão, essa função é atribuída aos grupos de função gerenciamento de conformidade e gerenciamento da organização na página **permissões** no centro de administração do Exchange.</span><span class="sxs-lookup"><span data-stu-id="67ced-115">By default, this role is assigned to the Compliance Management and Organization Management role groups on the **Permissions** page in the Exchange admin center.</span></span> <span data-ttu-id="67ced-116">Os administradores globais no Microsoft 365 são membros do grupo de funções Gerenciamento da organização no Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="67ced-116">Global admins in Microsoft 365 are members of the Organization Management role group in Exchange Online.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="67ced-117">Os usuários precisam receber permissões no Exchange Online para ativar ou desativar a pesquisa de log de auditoria.</span><span class="sxs-lookup"><span data-stu-id="67ced-117">Users have to be assigned permissions in Exchange Online to turn audit log search on or off.</span></span> <span data-ttu-id="67ced-118">Se você atribuir aos usuários a função logs de auditoria na página **permissões** no centro de conformidade & segurança, não será possível ativar ou desativar a pesquisa de log de auditoria.</span><span class="sxs-lookup"><span data-stu-id="67ced-118">If you assign users the Audit Logs role on the **Permissions** page in the Security & Compliance Center, they won't be able to turn audit log search on or off.</span></span> <span data-ttu-id="67ced-119">Isso ocorre porque o cmdlet subjacente é um cmdlet do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="67ced-119">This is because the underlying cmdlet is an Exchange Online cmdlet.</span></span> 
    
- <span data-ttu-id="67ced-120">Para obter instruções passo a passo sobre como pesquisar o log de auditoria, consulte [Pesquisar o log de auditoria no centro de conformidade do & de segurança](search-the-audit-log-in-security-and-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="67ced-120">For step-by-step instructions on searching the audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span> <span data-ttu-id="67ced-121">Para obter mais informações sobre a API de atividade de gerenciamento do Microsoft 365, confira [introdução às APIs de gerenciamento do microsoft 365](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span><span class="sxs-lookup"><span data-stu-id="67ced-121">For more information about the Microsoft 365 Management Activity API, see [Get started with Microsoft 365 Management APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span>
    
## <a name="turn-on-audit-log-search"></a><span data-ttu-id="67ced-122">Ativar pesquisa de log de auditoria</span><span class="sxs-lookup"><span data-stu-id="67ced-122">Turn on audit log search</span></span>

<span data-ttu-id="67ced-123">Você pode usar o centro de conformidade & segurança ou o PowerShell para ativar a pesquisa de log de auditoria no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="67ced-123">You can use the Security & Compliance Center or PowerShell to turn on audit log search in Microsoft 365.</span></span> <span data-ttu-id="67ced-124">Pode levar várias horas após você ativar a pesquisa de log de auditoria antes de poder retornar os resultados ao pesquisar o log de auditoria.</span><span class="sxs-lookup"><span data-stu-id="67ced-124">It may take several hours after you turn on audit log search before you can return results when you search the audit log.</span></span> <span data-ttu-id="67ced-125">Você precisa receber a função de logs de auditoria no Exchange Online para ativar a pesquisa de log de auditoria.</span><span class="sxs-lookup"><span data-stu-id="67ced-125">You have to be assigned the Audit Logs role in Exchange Online to turn on audit log search.</span></span>
  
### <a name="use-the-security--compliance-center-to-turn-on-audit-log-search"></a><span data-ttu-id="67ced-126">Usar o centro de conformidade de & de segurança para ativar a pesquisa de log de auditoria</span><span class="sxs-lookup"><span data-stu-id="67ced-126">Use the Security & Compliance Center to turn on audit log search</span></span>

1. <span data-ttu-id="67ced-127">[Vá para o centro de conformidade & segurança](https://protection.office.com) e entre.</span><span class="sxs-lookup"><span data-stu-id="67ced-127">[Go to the Security & Compliance Center](https://protection.office.com) and sign in.</span></span>

2. <span data-ttu-id="67ced-128">No centro de conformidade & segurança, vá para pesquisa de log de auditoria de **pesquisa** \> **Audit log search**.</span><span class="sxs-lookup"><span data-stu-id="67ced-128">In the Security & Compliance Center, go to **Search** \> **Audit log search**.</span></span>

   <span data-ttu-id="67ced-129">Uma faixa é exibida informando que a auditoria deve ser ativada para registrar a atividade do usuário e do administrador.</span><span class="sxs-lookup"><span data-stu-id="67ced-129">A banner is displayed saying that auditing has to be turned on to record user and admin activity.</span></span>

3. <span data-ttu-id="67ced-130">Clique em **ativar a auditoria**.</span><span class="sxs-lookup"><span data-stu-id="67ced-130">Click **Turn on auditing**.</span></span>

    ![Clique em ativar auditoria](../media/39a9d35f-88d0-4bbe-a962-0be2f838e2bf.png)
  
    <span data-ttu-id="67ced-132">A faixa é atualizada para dizer que o log de auditoria está sendo preparado e que você pode pesquisar a atividade de usuário e administrador em algumas horas.</span><span class="sxs-lookup"><span data-stu-id="67ced-132">The banner is updated to say the audit log is being prepared and that you can search for user and admin activity in a few hours.</span></span>

### <a name="use-powershell-to-turn-on-audit-log-search"></a><span data-ttu-id="67ced-133">Usar o PowerShell para ativar a pesquisa de log de auditoria</span><span class="sxs-lookup"><span data-stu-id="67ced-133">Use PowerShell to turn on audit log search</span></span>

1. [<span data-ttu-id="67ced-134">Conectar-se ao PowerShell do Exchange Online </span><span class="sxs-lookup"><span data-stu-id="67ced-134">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=396554)

2. <span data-ttu-id="67ced-135">Execute o seguinte comando do PowerShell para ativar a pesquisa de log de auditoria no Office 365.</span><span class="sxs-lookup"><span data-stu-id="67ced-135">Run the following PowerShell command to turn on audit log search in Office 365.</span></span>

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    <span data-ttu-id="67ced-136">Uma mensagem é exibida dizendo que pode levar até 60 minutos para que a alteração entre em vigor.</span><span class="sxs-lookup"><span data-stu-id="67ced-136">A message is displayed saying that it may take up to 60 minutes for the change to take effect.</span></span>
  
## <a name="turn-off-audit-log-search"></a><span data-ttu-id="67ced-137">Desativar pesquisa de log de auditoria</span><span class="sxs-lookup"><span data-stu-id="67ced-137">Turn off audit log search</span></span>

<span data-ttu-id="67ced-138">Você precisa usar o PowerShell remoto conectado à sua organização do Exchange Online para desativar a pesquisa de log de auditoria.</span><span class="sxs-lookup"><span data-stu-id="67ced-138">You have to use remote PowerShell connected to your Exchange Online organization to turn off audit log search.</span></span> <span data-ttu-id="67ced-139">Semelhante à ativação da pesquisa de log de auditoria, você precisa ter atribuído a função de logs de auditoria no Exchange Online para desativar a pesquisa de log de auditoria.</span><span class="sxs-lookup"><span data-stu-id="67ced-139">Similar to turning on audit log search, you have to be assigned the Audit Logs role in Exchange Online to turn off audit log search.</span></span>
  
1. [<span data-ttu-id="67ced-140">Conectar-se ao PowerShell do Exchange Online </span><span class="sxs-lookup"><span data-stu-id="67ced-140">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=396554)

2. <span data-ttu-id="67ced-141">Execute o seguinte comando do PowerShell para desativar a pesquisa de log de auditoria no Office 365.</span><span class="sxs-lookup"><span data-stu-id="67ced-141">Run the following PowerShell command to turn off audit log search in Office 365.</span></span>

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. <span data-ttu-id="67ced-142">Após um tempo, verifique se a pesquisa de log de auditoria está desativada (desabilitada).</span><span class="sxs-lookup"><span data-stu-id="67ced-142">After a while, verify that audit log search is turned off (disabled).</span></span> <span data-ttu-id="67ced-143">Há duas maneiras de fazer isso:</span><span class="sxs-lookup"><span data-stu-id="67ced-143">There are two ways to do this:</span></span>

    - <span data-ttu-id="67ced-144">No PowerShell, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="67ced-144">In PowerShell, run the following command:</span></span>

    ```powershell
    Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
    ```

      <span data-ttu-id="67ced-145">O valor da `False` propriedade _UnifiedAuditLogIngestionEnabled_ indica que a pesquisa de log de auditoria está desativada.</span><span class="sxs-lookup"><span data-stu-id="67ced-145">The value of  `False` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that audit log search is turned off.</span></span> 

    - <span data-ttu-id="67ced-146">No [centro de conformidade & segurança](https://protection.office.com), vá para pesquisa de log de auditoria de **pesquisa** \> **Audit log search**.</span><span class="sxs-lookup"><span data-stu-id="67ced-146">In the [Security & Compliance Center](https://protection.office.com), go to **Search** \> **Audit log search**.</span></span>

      <span data-ttu-id="67ced-147">Uma faixa é exibida dizendo que a auditoria deve ser ativada para registrar a atividade de usuário e administrador.</span><span class="sxs-lookup"><span data-stu-id="67ced-147">A banner is displayed saying that auditing has to be turned on in order to record user and admin activity.</span></span>