---
title: Ativar e desativar a Pesquisa de log de auditoria do Office 365
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
description: Você pode ativar o recurso de pesquisa de log de auditoria no centro de conformidade de & de segurança. Se você mudar de ideia, poderá desativar se estiver desligado a qualquer momento. Quando a pesquisa de log de auditoria está desativada, os administradores não podem pesquisar o log de auditoria do Office 365 para atividades de usuário e administrador em sua organização.
ms.openlocfilehash: 83ef355c4acd5e0af4fd7ffbf13157307bcac930
ms.sourcegitcommit: 53d848ebd4799b285d0f67c49b0aa24c88bd0e23
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2019
ms.locfileid: "37334241"
---
# <a name="turn-office-365-audit-log-search-on-or-off"></a><span data-ttu-id="a871d-105">Ativar e desativar a Pesquisa de log de auditoria do Office 365</span><span class="sxs-lookup"><span data-stu-id="a871d-105">Turn Office 365 audit log search on or off</span></span>

<span data-ttu-id="a871d-106">Você (ou outro administrador) deve ativar o log de auditoria antes de começar a pesquisar o log de auditoria do Office 365.</span><span class="sxs-lookup"><span data-stu-id="a871d-106">You (or another admin) must turn on audit logging before you can start searching the Office 365 audit log.</span></span> <span data-ttu-id="a871d-107">Quando a pesquisa de log de auditoria no centro de conformidade do & de segurança está ativada, a atividade do usuário e do administrador de sua organização é registrada no log de auditoria e mantida por 90 dias.</span><span class="sxs-lookup"><span data-stu-id="a871d-107">When audit log search in the Security & Compliance Center is turned on, user and admin activity from your organization is recorded in the audit log and retained for 90 days.</span></span> <span data-ttu-id="a871d-108">No entanto, sua organização pode não querer gravar e reter dados de log de auditoria.</span><span class="sxs-lookup"><span data-stu-id="a871d-108">However, your organization may not want to record and retain audit log data.</span></span> <span data-ttu-id="a871d-109">Ou você pode estar usando um aplicativo de gerenciamento de eventos e informações de segurança (SIEM) de terceiros para acessar seus dados de auditoria.</span><span class="sxs-lookup"><span data-stu-id="a871d-109">Or you may be using a third-party security information and event management (SIEM) application to access your auditing data.</span></span> <span data-ttu-id="a871d-110">Nesses casos, um administrador global pode desativar a pesquisa de log de auditoria no Office 365.</span><span class="sxs-lookup"><span data-stu-id="a871d-110">In those cases, a global admin can turn off audit log search in Office 365.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="a871d-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="a871d-111">Before you begin</span></span>

- <span data-ttu-id="a871d-112">Você precisa receber a função de logs de auditoria no Exchange Online para ativar ou desativar a pesquisa de log de auditoria na sua organização do Office 365.</span><span class="sxs-lookup"><span data-stu-id="a871d-112">You have to be assigned the Audit Logs role in Exchange Online to turn audit log search on or off in your Office 365 organization.</span></span> <span data-ttu-id="a871d-113">Por padrão, essa função é atribuída aos grupos de função gerenciamento de conformidade e gerenciamento da organização na página **permissões** no centro de administração do Exchange.</span><span class="sxs-lookup"><span data-stu-id="a871d-113">By default, this role is assigned to the Compliance Management and Organization Management role groups on the **Permissions** page in the Exchange admin center.</span></span> <span data-ttu-id="a871d-114">Os administradores globais no Office 365 são membros do grupo de funções Gerenciamento da organização no Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="a871d-114">Global admins in Office 365 are members of the Organization Management role group in Exchange Online.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="a871d-115">Os usuários precisam receber permissões no Exchange Online para ativar ou desativar a pesquisa de log de auditoria.</span><span class="sxs-lookup"><span data-stu-id="a871d-115">Users have to be assigned permissions in Exchange Online to turn audit log search on or off.</span></span> <span data-ttu-id="a871d-116">Se você atribuir aos usuários a função logs de auditoria na página **permissões** no centro de conformidade & segurança, não será possível ativar ou desativar a pesquisa de log de auditoria.</span><span class="sxs-lookup"><span data-stu-id="a871d-116">If you assign users the Audit Logs role on the **Permissions** page in the Security & Compliance Center, they won't be able to turn audit log search on or off.</span></span> <span data-ttu-id="a871d-117">Isso ocorre porque o cmdlet subjacente é um cmdlet do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="a871d-117">This is because the underlying cmdlet is an Exchange Online cmdlet.</span></span> 
  
- <span data-ttu-id="a871d-118">Se você desativar a pesquisa de log de auditoria no Office 365, não poderá usar a API da atividade de gerenciamento do Office 365 para acessar os dados de auditoria da sua organização.</span><span class="sxs-lookup"><span data-stu-id="a871d-118">If you turn off audit log search in Office 365, you can't use the Office 365 Management Activity API to access auditing data for your organization.</span></span> <span data-ttu-id="a871d-119">Desativando a pesquisa de log de auditoria seguindo as etapas deste artigo significa que nenhum resultado será retornado quando você pesquisar o log de auditoria usando o centro de conformidade de & de segurança ou quando executar o cmdlet **Search-UnifiedAuditLog** no PowerShell do Exchange Online .</span><span class="sxs-lookup"><span data-stu-id="a871d-119">Turning off audit log search by following the steps in this article means that no results will be returned when you search the audit log using the Security & Compliance Center or when you run the **Search-UnifiedAuditLog** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="a871d-120">Isso também significa que seus logs de auditoria não estarão disponíveis por meio da API de atividade de gerenciamento do Office 365.</span><span class="sxs-lookup"><span data-stu-id="a871d-120">This also means that your audit logs won't be available through the Office 365 Management Activity API.</span></span>  
    
- <span data-ttu-id="a871d-121">Para obter instruções passo a passo sobre como pesquisar o log de auditoria do Office 365, consulte [Pesquisar o log de auditoria no centro de conformidade do & de segurança](search-the-audit-log-in-security-and-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="a871d-121">For step-by-step instructions on searching the Office 365 audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span>
    
## <a name="turn-on-audit-log-search"></a><span data-ttu-id="a871d-122">Ativar pesquisa de log de auditoria</span><span class="sxs-lookup"><span data-stu-id="a871d-122">Turn on audit log search</span></span>

<span data-ttu-id="a871d-123">Você pode usar o centro de conformidade & segurança ou o PowerShell para ativar a pesquisa de log de auditoria no Office 365.</span><span class="sxs-lookup"><span data-stu-id="a871d-123">You can use the Security & Compliance Center or PowerShell to turn on audit log search in Office 365.</span></span> <span data-ttu-id="a871d-124">Pode levar várias horas após você ativar a pesquisa de log de auditoria antes de poder retornar os resultados ao pesquisar o log de auditoria.</span><span class="sxs-lookup"><span data-stu-id="a871d-124">It may take several hours after you turn on audit log search before you can return results when you search the audit log.</span></span> <span data-ttu-id="a871d-125">Você precisa receber a função de logs de auditoria no Exchange Online para ativar a pesquisa de log de auditoria.</span><span class="sxs-lookup"><span data-stu-id="a871d-125">You have to be assigned the Audit Logs role in Exchange Online to turn on audit log search.</span></span>
  
### <a name="use-the-security--compliance-center-to-turn-on-audit-log-search"></a><span data-ttu-id="a871d-126">Usar o centro de conformidade de & de segurança para ativar a pesquisa de log de auditoria</span><span class="sxs-lookup"><span data-stu-id="a871d-126">Use the Security & Compliance Center to turn on audit log search</span></span>

1. <span data-ttu-id="a871d-127">No centro de conformidade & segurança, vá para pesquisa de **log de auditoria**de **pesquisa** \> .</span><span class="sxs-lookup"><span data-stu-id="a871d-127">In the Security & Compliance Center, go to **Search** \> **Audit log search**.</span></span>
    
   <span data-ttu-id="a871d-128">Uma faixa é exibida informando que a auditoria deve ser ativada para registrar a atividade do usuário e do administrador.</span><span class="sxs-lookup"><span data-stu-id="a871d-128">A banner is displayed saying that auditing has to be turned on to record user and admin activity.</span></span>

2. <span data-ttu-id="a871d-129">Clique em **ativar a auditoria**.</span><span class="sxs-lookup"><span data-stu-id="a871d-129">Click **Turn on auditing**.</span></span>
    
    ![Clique em ativar auditoria](media/39a9d35f-88d0-4bbe-a962-0be2f838e2bf.png)
  
    <span data-ttu-id="a871d-131">A faixa é atualizada para dizer que o log de auditoria está sendo preparado e que você pode pesquisar a atividade de usuário e administrador em algumas horas.</span><span class="sxs-lookup"><span data-stu-id="a871d-131">The banner is updated to say the audit log is being prepared and that you can search for user and admin activity in a few hours.</span></span>
    
### <a name="use-powershell-to-turn-on-audit-log-search"></a><span data-ttu-id="a871d-132">Usar o PowerShell para ativar a pesquisa de log de auditoria</span><span class="sxs-lookup"><span data-stu-id="a871d-132">Use PowerShell to turn on audit log search</span></span>

1. [<span data-ttu-id="a871d-133">Conectar-se ao PowerShell do Exchange Online </span><span class="sxs-lookup"><span data-stu-id="a871d-133">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=396554)
    
2. <span data-ttu-id="a871d-134">Execute o seguinte comando do PowerShell para ativar a pesquisa de log de auditoria no Office 365.</span><span class="sxs-lookup"><span data-stu-id="a871d-134">Run the following PowerShell command to turn on audit log search in Office 365.</span></span>
    
    ```
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    <span data-ttu-id="a871d-135">Uma mensagem é exibida dizendo que pode levar até 60 minutos para que a alteração entre em vigor.</span><span class="sxs-lookup"><span data-stu-id="a871d-135">A message is displayed saying that it may take up to 60 minutes for the change to take effect.</span></span>
  
## <a name="turn-off-audit-log-search"></a><span data-ttu-id="a871d-136">Desativar pesquisa de log de auditoria</span><span class="sxs-lookup"><span data-stu-id="a871d-136">Turn off audit log search</span></span>

<span data-ttu-id="a871d-137">Você precisa usar o PowerShell remoto conectado à sua organização do Exchange Online para desativar a pesquisa de log de auditoria.</span><span class="sxs-lookup"><span data-stu-id="a871d-137">You have to use remote PowerShell connected to your Exchange Online organization to turn off audit log search.</span></span> <span data-ttu-id="a871d-138">Semelhante à ativação da pesquisa de log de auditoria, você precisa ter atribuído a função de logs de auditoria no Exchange Online para desativar a pesquisa de log de auditoria.</span><span class="sxs-lookup"><span data-stu-id="a871d-138">Similar to turning on audit log search, you have to be assigned the Audit Logs role in Exchange Online to turn off audit log search.</span></span>
  
1. [<span data-ttu-id="a871d-139">Conectar-se ao PowerShell do Exchange Online </span><span class="sxs-lookup"><span data-stu-id="a871d-139">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=396554)
    
2. <span data-ttu-id="a871d-140">Execute o seguinte comando do PowerShell para desativar a pesquisa de log de auditoria no Office 365.</span><span class="sxs-lookup"><span data-stu-id="a871d-140">Run the following PowerShell command to turn off audit log search in Office 365.</span></span>
    
    ```
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. <span data-ttu-id="a871d-141">Após um tempo, verifique se a pesquisa de log de auditoria está desativada (desabilitada).</span><span class="sxs-lookup"><span data-stu-id="a871d-141">After a while, verify that audit log search is turned off (disabled).</span></span> <span data-ttu-id="a871d-142">Há duas maneiras de fazer isso:</span><span class="sxs-lookup"><span data-stu-id="a871d-142">There are two ways to do this:</span></span>
    
    - <span data-ttu-id="a871d-143">No PowerShell, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="a871d-143">In PowerShell, run the following command:</span></span>

            ```
            Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
            ```

           The value of  `False` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that audit log search is turned off. 
    
    - <span data-ttu-id="a871d-144">No centro de conformidade & segurança, vá para pesquisa de **log de auditoria**de **pesquisa** \> .</span><span class="sxs-lookup"><span data-stu-id="a871d-144">In the Security & Compliance Center, go to **Search** \> **Audit log search**.</span></span>
    
           A banner is displayed saying that auditing has to be turned on in order to record user and admin activity.
