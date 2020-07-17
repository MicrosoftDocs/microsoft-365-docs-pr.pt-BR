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
description: Como ativar ou desativar o recurso de pesquisa de log de auditoria no centro de conformidade do & de segurança para habilitar ou desabilitar a capacidade dos administradores de Pesquisar o log de auditoria.
ms.openlocfilehash: 4571c90c4fa680acd8925e83e32ffcf07de7d626
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819131"
---
# <a name="turn-audit-log-search-on-or-off"></a><span data-ttu-id="1ae77-103">Ativar ou desativar a pesquisa de log de auditoria</span><span class="sxs-lookup"><span data-stu-id="1ae77-103">Turn audit log search on or off</span></span>

<span data-ttu-id="1ae77-104">Você (ou outro administrador) deve ativar o log de auditoria antes de começar a pesquisar o log de auditoria.</span><span class="sxs-lookup"><span data-stu-id="1ae77-104">You (or another admin) must turn on audit logging before you can start searching the audit log.</span></span> <span data-ttu-id="1ae77-105">Quando a pesquisa de log de auditoria no centro de conformidade do & de segurança está ativada, a atividade do usuário e do administrador de sua organização é registrada no log de auditoria e mantida por 90 dias, e até um ano, dependendo da licença atribuída aos usuários.</span><span class="sxs-lookup"><span data-stu-id="1ae77-105">When audit log search in the Security & Compliance Center is turned on, user and admin activity from your organization is recorded in the audit log and retained for 90 days, and up to one year depending on the license assigned to users.</span></span> <span data-ttu-id="1ae77-106">No entanto, sua organização pode ter motivos para não querer gravar e reter dados de log de auditoria.</span><span class="sxs-lookup"><span data-stu-id="1ae77-106">However, your organization may have reasons for not wanting to record and retain audit log data.</span></span> <span data-ttu-id="1ae77-107">Nesses casos, um administrador global pode decidir desativar a auditoria no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1ae77-107">In those cases, a global admin may decide to turn off auditing in Microsoft 365.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1ae77-108">Se você desativar a pesquisa de log de auditoria no Microsoft 365, não será possível usar a API da atividade de gerenciamento do Office 365 ou o Azure Sentinel para acessar os dados de auditoria da sua organização.</span><span class="sxs-lookup"><span data-stu-id="1ae77-108">If you turn off audit log search in Microsoft 365, you can't use the Office 365 Management Activity API or Azure Sentinel to access auditing data for your organization.</span></span> <span data-ttu-id="1ae77-109">Desativando a pesquisa de log de auditoria seguindo as etapas deste artigo significa que nenhum resultado será retornado quando você pesquisar o log de auditoria usando o centro de conformidade de & de segurança ou quando executar o cmdlet **Search-UnifiedAuditLog** no PowerShell do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="1ae77-109">Turning off audit log search by following the steps in this article means that no results will be returned when you search the audit log using the Security & Compliance Center or when you run the **Search-UnifiedAuditLog** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="1ae77-110">Isso também significa que os logs de auditoria não estarão disponíveis por meio da API de atividade de gerenciamento do Office 365 ou do Azure Sentinel.</span><span class="sxs-lookup"><span data-stu-id="1ae77-110">This also means that audit logs won't be available through the Office 365 Management Activity API or Azure Sentinel.</span></span>
  
## <a name="before-you-turn-audit-log-search-on-or-off"></a><span data-ttu-id="1ae77-111">Antes de ativar ou desativar a pesquisa de log de auditoria</span><span class="sxs-lookup"><span data-stu-id="1ae77-111">Before you turn audit log search on or off</span></span>

- <span data-ttu-id="1ae77-112">Você precisa receber a função de logs de auditoria no Exchange Online para ativar ou desativar a pesquisa de log de auditoria na sua organização do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1ae77-112">You have to be assigned the Audit Logs role in Exchange Online to turn audit log search on or off in your Microsoft 365 organization.</span></span> <span data-ttu-id="1ae77-113">Por padrão, essa função é atribuída aos grupos de função gerenciamento de conformidade e gerenciamento da organização na página **permissões** no centro de administração do Exchange.</span><span class="sxs-lookup"><span data-stu-id="1ae77-113">By default, this role is assigned to the Compliance Management and Organization Management role groups on the **Permissions** page in the Exchange admin center.</span></span> <span data-ttu-id="1ae77-114">Os administradores globais no Microsoft 365 são membros do grupo de funções Gerenciamento da organização no Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="1ae77-114">Global admins in Microsoft 365 are members of the Organization Management role group in Exchange Online.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="1ae77-115">Os usuários precisam receber permissões no Exchange Online para ativar ou desativar a pesquisa de log de auditoria.</span><span class="sxs-lookup"><span data-stu-id="1ae77-115">Users have to be assigned permissions in Exchange Online to turn audit log search on or off.</span></span> <span data-ttu-id="1ae77-116">Se você atribuir aos usuários a função logs de auditoria na página **permissões** no centro de conformidade & segurança, não será possível ativar ou desativar a pesquisa de log de auditoria.</span><span class="sxs-lookup"><span data-stu-id="1ae77-116">If you assign users the Audit Logs role on the **Permissions** page in the Security & Compliance Center, they won't be able to turn audit log search on or off.</span></span> <span data-ttu-id="1ae77-117">Isso ocorre porque o cmdlet subjacente é um cmdlet do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="1ae77-117">This is because the underlying cmdlet is an Exchange Online cmdlet.</span></span> 
    
- <span data-ttu-id="1ae77-118">Para obter instruções passo a passo sobre como pesquisar o log de auditoria, consulte [Pesquisar o log de auditoria no centro de conformidade do & de segurança](search-the-audit-log-in-security-and-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="1ae77-118">For step-by-step instructions on searching the audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span> <span data-ttu-id="1ae77-119">Para obter mais informações sobre a API de atividade de gerenciamento do Microsoft 365, confira [introdução às APIs de gerenciamento do microsoft 365](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span><span class="sxs-lookup"><span data-stu-id="1ae77-119">For more information about the Microsoft 365 Management Activity API, see [Get started with Microsoft 365 Management APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span>
    
## <a name="turn-on-audit-log-search"></a><span data-ttu-id="1ae77-120">Ativar pesquisa de log de auditoria</span><span class="sxs-lookup"><span data-stu-id="1ae77-120">Turn on audit log search</span></span>

<span data-ttu-id="1ae77-121">Você pode usar o centro de conformidade & segurança ou o PowerShell para ativar a pesquisa de log de auditoria no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1ae77-121">You can use the Security & Compliance Center or PowerShell to turn on audit log search in Microsoft 365.</span></span> <span data-ttu-id="1ae77-122">Pode levar várias horas após você ativar a pesquisa de log de auditoria antes de poder retornar os resultados ao pesquisar o log de auditoria.</span><span class="sxs-lookup"><span data-stu-id="1ae77-122">It may take several hours after you turn on audit log search before you can return results when you search the audit log.</span></span> <span data-ttu-id="1ae77-123">Você precisa receber a função de logs de auditoria no Exchange Online para ativar a pesquisa de log de auditoria.</span><span class="sxs-lookup"><span data-stu-id="1ae77-123">You have to be assigned the Audit Logs role in Exchange Online to turn on audit log search.</span></span>
  
### <a name="use-the-security--compliance-center-to-turn-on-audit-log-search"></a><span data-ttu-id="1ae77-124">Usar o centro de conformidade de & de segurança para ativar a pesquisa de log de auditoria</span><span class="sxs-lookup"><span data-stu-id="1ae77-124">Use the Security & Compliance Center to turn on audit log search</span></span>

1. <span data-ttu-id="1ae77-125">[Vá para o centro de conformidade & segurança](https://protection.office.com) e entre.</span><span class="sxs-lookup"><span data-stu-id="1ae77-125">[Go to the Security & Compliance Center](https://protection.office.com) and sign in.</span></span>

2. <span data-ttu-id="1ae77-126">No centro de conformidade & segurança, vá para pesquisa de log de auditoria de **pesquisa** \> **Audit log search**.</span><span class="sxs-lookup"><span data-stu-id="1ae77-126">In the Security & Compliance Center, go to **Search** \> **Audit log search**.</span></span>

   <span data-ttu-id="1ae77-127">Uma faixa é exibida informando que a auditoria deve ser ativada para registrar a atividade do usuário e do administrador.</span><span class="sxs-lookup"><span data-stu-id="1ae77-127">A banner is displayed saying that auditing has to be turned on to record user and admin activity.</span></span>

3. <span data-ttu-id="1ae77-128">Clique em **ativar a auditoria**.</span><span class="sxs-lookup"><span data-stu-id="1ae77-128">Click **Turn on auditing**.</span></span>

    ![Clique em ativar auditoria](../media/39a9d35f-88d0-4bbe-a962-0be2f838e2bf.png)
  
    <span data-ttu-id="1ae77-130">A faixa é atualizada para dizer que o log de auditoria está sendo preparado e que você pode pesquisar a atividade de usuário e administrador em algumas horas.</span><span class="sxs-lookup"><span data-stu-id="1ae77-130">The banner is updated to say the audit log is being prepared and that you can search for user and admin activity in a few hours.</span></span>

### <a name="use-powershell-to-turn-on-audit-log-search"></a><span data-ttu-id="1ae77-131">Usar o PowerShell para ativar a pesquisa de log de auditoria</span><span class="sxs-lookup"><span data-stu-id="1ae77-131">Use PowerShell to turn on audit log search</span></span>

1. [<span data-ttu-id="1ae77-132">Conectar-se ao PowerShell do Exchange Online </span><span class="sxs-lookup"><span data-stu-id="1ae77-132">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=396554)

2. <span data-ttu-id="1ae77-133">Execute o seguinte comando do PowerShell para ativar a pesquisa de log de auditoria no Office 365.</span><span class="sxs-lookup"><span data-stu-id="1ae77-133">Run the following PowerShell command to turn on audit log search in Office 365.</span></span>

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    <span data-ttu-id="1ae77-134">Uma mensagem é exibida dizendo que pode levar até 60 minutos para que a alteração entre em vigor.</span><span class="sxs-lookup"><span data-stu-id="1ae77-134">A message is displayed saying that it may take up to 60 minutes for the change to take effect.</span></span>
  
## <a name="turn-off-audit-log-search"></a><span data-ttu-id="1ae77-135">Desativar pesquisa de log de auditoria</span><span class="sxs-lookup"><span data-stu-id="1ae77-135">Turn off audit log search</span></span>

<span data-ttu-id="1ae77-136">Você precisa usar o PowerShell remoto conectado à sua organização do Exchange Online para desativar a pesquisa de log de auditoria.</span><span class="sxs-lookup"><span data-stu-id="1ae77-136">You have to use remote PowerShell connected to your Exchange Online organization to turn off audit log search.</span></span> <span data-ttu-id="1ae77-137">Semelhante à ativação da pesquisa de log de auditoria, você precisa ter atribuído a função de logs de auditoria no Exchange Online para desativar a pesquisa de log de auditoria.</span><span class="sxs-lookup"><span data-stu-id="1ae77-137">Similar to turning on audit log search, you have to be assigned the Audit Logs role in Exchange Online to turn off audit log search.</span></span>
  
1. [<span data-ttu-id="1ae77-138">Conectar-se ao PowerShell do Exchange Online </span><span class="sxs-lookup"><span data-stu-id="1ae77-138">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=396554)

2. <span data-ttu-id="1ae77-139">Execute o seguinte comando do PowerShell para desativar a pesquisa de log de auditoria no Office 365.</span><span class="sxs-lookup"><span data-stu-id="1ae77-139">Run the following PowerShell command to turn off audit log search in Office 365.</span></span>

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. <span data-ttu-id="1ae77-140">Após um tempo, verifique se a pesquisa de log de auditoria está desativada (desabilitada).</span><span class="sxs-lookup"><span data-stu-id="1ae77-140">After a while, verify that audit log search is turned off (disabled).</span></span> <span data-ttu-id="1ae77-141">Há duas maneiras de fazer isso:</span><span class="sxs-lookup"><span data-stu-id="1ae77-141">There are two ways to do this:</span></span>

    - <span data-ttu-id="1ae77-142">No PowerShell, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="1ae77-142">In PowerShell, run the following command:</span></span>

    ```powershell
    Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
    ```

      <span data-ttu-id="1ae77-143">O valor da `False` propriedade _UnifiedAuditLogIngestionEnabled_ indica que a pesquisa de log de auditoria está desativada.</span><span class="sxs-lookup"><span data-stu-id="1ae77-143">The value of  `False` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that audit log search is turned off.</span></span> 

    - <span data-ttu-id="1ae77-144">No [centro de conformidade & segurança](https://protection.office.com), vá para pesquisa de log de auditoria de **pesquisa** \> **Audit log search**.</span><span class="sxs-lookup"><span data-stu-id="1ae77-144">In the [Security & Compliance Center](https://protection.office.com), go to **Search** \> **Audit log search**.</span></span>

      <span data-ttu-id="1ae77-145">Uma faixa é exibida dizendo que a auditoria deve ser ativada para registrar a atividade de usuário e administrador.</span><span class="sxs-lookup"><span data-stu-id="1ae77-145">A banner is displayed saying that auditing has to be turned on in order to record user and admin activity.</span></span>