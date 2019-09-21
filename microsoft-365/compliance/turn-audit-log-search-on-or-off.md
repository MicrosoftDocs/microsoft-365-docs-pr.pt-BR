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
ms.openlocfilehash: c5e1106617aa4828ec2db5afcc44ac55e91f2383
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37073744"
---
# <a name="turn-office-365-audit-log-search-on-or-off"></a><span data-ttu-id="7478a-105">Ativar e desativar a Pesquisa de log de auditoria do Office 365</span><span class="sxs-lookup"><span data-stu-id="7478a-105">Turn Office 365 audit log search on or off</span></span>

<span data-ttu-id="7478a-106">Você (ou outro administrador) deve ativar o log de auditoria antes de começar a pesquisar o log de auditoria do Office 365.</span><span class="sxs-lookup"><span data-stu-id="7478a-106">You (or another admin) must turn on audit logging before you can start searching the Office 365 audit log.</span></span> <span data-ttu-id="7478a-107">Quando a pesquisa de log de auditoria no centro de conformidade do & de segurança está ativada, a atividade do usuário e do administrador de sua organização é registrada no log de auditoria e mantida por 90 dias.</span><span class="sxs-lookup"><span data-stu-id="7478a-107">When audit log search in the Security & Compliance Center is turned on, user and admin activity from your organization is recorded in the audit log and retained for 90 days.</span></span> <span data-ttu-id="7478a-108">No entanto, sua organização pode não querer gravar e reter dados de log de auditoria.</span><span class="sxs-lookup"><span data-stu-id="7478a-108">However, your organization might not want to record and retain audit log data.</span></span> <span data-ttu-id="7478a-109">Ou você pode estar usando um aplicativo de gerenciamento de eventos e informações de segurança (SIEM) de terceiros para acessar seus dados de auditoria.</span><span class="sxs-lookup"><span data-stu-id="7478a-109">Or you might be using a third-party security information and event management (SIEM) application to access your auditing data.</span></span> <span data-ttu-id="7478a-110">Nesses casos, um administrador global pode desativar a pesquisa de log de auditoria no Office 365.</span><span class="sxs-lookup"><span data-stu-id="7478a-110">In those cases, a global admin can turn off audit log search in Office 365.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="7478a-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="7478a-111">Before you begin</span></span>

- <span data-ttu-id="7478a-112">Você precisa receber a função de logs de auditoria no Exchange Online para ativar ou desativar a pesquisa de log de auditoria na sua organização do Office 365.</span><span class="sxs-lookup"><span data-stu-id="7478a-112">You have to be assigned the Audit Logs role in Exchange Online to turn audit log search on or off in your Office 365 organization.</span></span> <span data-ttu-id="7478a-113">Por padrão, essa função é atribuída aos grupos de função gerenciamento de conformidade e gerenciamento da organização na página **permissões** no centro de administração do Exchange.</span><span class="sxs-lookup"><span data-stu-id="7478a-113">By default, this role is assigned to the Compliance Management and Organization Management role groups on the **Permissions** page in the Exchange admin center.</span></span> <span data-ttu-id="7478a-114">Os administradores globais no Office 365 são membros do grupo de funções Gerenciamento da organização no Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="7478a-114">Global admins in Office 365 are members of the Organization Management role group in Exchange Online.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="7478a-115">Os usuários precisam receber permissões no Exchange Online para ativar ou desativar a pesquisa de log de auditoria.</span><span class="sxs-lookup"><span data-stu-id="7478a-115">Users have to be assigned permissions in Exchange Online to turn audit log search on or off.</span></span> <span data-ttu-id="7478a-116">Se você atribuir aos usuários a função logs de auditoria na página **permissões** no centro de conformidade & segurança, não será possível ativar ou desativar a pesquisa de log de auditoria.</span><span class="sxs-lookup"><span data-stu-id="7478a-116">If you assign users the Audit Logs role on the **Permissions** page in the Security & Compliance Center, they won't be able to turn audit log search on or off.</span></span> <span data-ttu-id="7478a-117">Isso ocorre porque o cmdlet subjacente é um cmdlet do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="7478a-117">This is because the underlying cmdlet is an Exchange Online cmdlet.</span></span> 
  
- <span data-ttu-id="7478a-118">Se você desativar a pesquisa de log de auditoria no Office 365, não será possível usar a API da atividade de gerenciamento do Office 365 para acessar os dados de auditoria da sua organização.</span><span class="sxs-lookup"><span data-stu-id="7478a-118">If you turn off audit log search in Office 365, you won't be able to use the Office 365 Management Activity API to access auditing data for your organization.</span></span> <span data-ttu-id="7478a-119">Desativando a pesquisa de log de auditoria seguindo as etapas deste artigo significa que nenhum resultado será retornado quando você pesquisar o log de auditoria usando o centro de conformidade de & de segurança ou quando executar o cmdlet **Search-UnifiedAuditLog** no PowerShell do Exchange Online .</span><span class="sxs-lookup"><span data-stu-id="7478a-119">Turning off audit log search by following the steps in this article means that no results will be returned when you search the audit log using the Security & Compliance Center or when you run the **Search-UnifiedAuditLog** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="7478a-120">Isso também significa que seus logs de auditoria não estarão disponíveis por meio da API de atividade de gerenciamento do Office 365.</span><span class="sxs-lookup"><span data-stu-id="7478a-120">This also means that your audit logs won't be available through the Office 365 Management Activity API.</span></span>  
    
- <span data-ttu-id="7478a-121">Para obter instruções passo a passo sobre como pesquisar o log de auditoria do Office 365, consulte [Pesquisar o log de auditoria no centro de conformidade do & de segurança](search-the-audit-log-in-security-and-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="7478a-121">For step-by-step instructions on searching the Office 365 audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span>
    
## <a name="turn-on-audit-log-search"></a><span data-ttu-id="7478a-122">Ativar pesquisa de log de auditoria</span><span class="sxs-lookup"><span data-stu-id="7478a-122">Turn on audit log search</span></span>

<span data-ttu-id="7478a-123">Você pode usar o centro de conformidade & segurança ou o PowerShell para ativar a pesquisa de log de auditoria no Office 365.</span><span class="sxs-lookup"><span data-stu-id="7478a-123">You can use the Security & Compliance Center or PowerShell to turn on audit log search in Office 365.</span></span> <span data-ttu-id="7478a-124">Pode levar várias horas após você ativar a pesquisa de log de auditoria antes de poder retornar os resultados ao pesquisar o log de auditoria.</span><span class="sxs-lookup"><span data-stu-id="7478a-124">It might take several hours after you turn on audit log search before you can return results when you search the audit log.</span></span> <span data-ttu-id="7478a-125">Você precisa receber a função de logs de auditoria no Exchange Online para ativar a pesquisa de log de auditoria.</span><span class="sxs-lookup"><span data-stu-id="7478a-125">You have to be assigned the Audit Logs role in Exchange Online to turn on audit log search.</span></span>
  
### <a name="use-the-security--compliance-center-to-turn-on-audit-log-search"></a><span data-ttu-id="7478a-126">Usar o centro de conformidade de & de segurança para ativar a pesquisa de log de auditoria</span><span class="sxs-lookup"><span data-stu-id="7478a-126">Use the Security & Compliance Center to turn on audit log search</span></span>

1. <span data-ttu-id="7478a-127">No centro de conformidade & segurança, vá para pesquisa de **log de auditoria**de **pesquisa** \> .</span><span class="sxs-lookup"><span data-stu-id="7478a-127">In the Security & Compliance Center, go to **Search** \> **Audit log search**.</span></span>
    
2. <span data-ttu-id="7478a-128">Clique em **Iniciar gravação de atividades do usuário e do administrador**.</span><span class="sxs-lookup"><span data-stu-id="7478a-128">Click **Start recording user and admin activities**.</span></span>
    
    ![Clique em Iniciar gravação de atividades de administrador e usuário para ativar a auditoria](media/39a9d35f-88d0-4bbe-a962-0be2f838e2bf.png)
  
    <span data-ttu-id="7478a-130">Uma caixa de diálogo é exibida informando que a atividade de usuário e administrador em sua organização será registrada no log de auditoria do Office 365 e disponível para exibição em um relatório.</span><span class="sxs-lookup"><span data-stu-id="7478a-130">A dialog box is displayed saying that user and admin activity in your organization will be recorded to the Office 365 audit log and available to view in a report.</span></span> 
    
3. <span data-ttu-id="7478a-131">Clique em **Ativar**.</span><span class="sxs-lookup"><span data-stu-id="7478a-131">Click **Turn on**.</span></span>
    
    <span data-ttu-id="7478a-132">Uma mensagem é exibida dizendo que o log de auditoria está sendo preparado e que você pode executar uma pesquisa em algumas horas após a conclusão da preparação.</span><span class="sxs-lookup"><span data-stu-id="7478a-132">A message is displayed that says the audit log is being prepared and that you can run a search in a couple of hours after the preparation is complete.</span></span>
    
### <a name="use-powershell-to-turn-on-audit-log-search"></a><span data-ttu-id="7478a-133">Usar o PowerShell para ativar a pesquisa de log de auditoria</span><span class="sxs-lookup"><span data-stu-id="7478a-133">Use PowerShell to turn on audit log search</span></span>

1. [<span data-ttu-id="7478a-134">Conectar-se ao PowerShell do Exchange Online </span><span class="sxs-lookup"><span data-stu-id="7478a-134">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=396554)
    
2. <span data-ttu-id="7478a-135">Execute o seguinte comando do PowerShell para ativar a pesquisa de log de auditoria no Office 365.</span><span class="sxs-lookup"><span data-stu-id="7478a-135">Run the following PowerShell command to turn on audit log search in Office 365.</span></span>
    
    ```
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    <span data-ttu-id="7478a-136">Uma mensagem é exibida dizendo que pode levar até 60 minutos para que a alteração entre em vigor.</span><span class="sxs-lookup"><span data-stu-id="7478a-136">A message is displayed saying that it might take up to 60 minutes for the change to take effect.</span></span>
  
## <a name="turn-off-audit-log-search"></a><span data-ttu-id="7478a-137">Desativar pesquisa de log de auditoria</span><span class="sxs-lookup"><span data-stu-id="7478a-137">Turn off audit log search</span></span>

<span data-ttu-id="7478a-138">Você precisa usar o PowerShell remoto conectado à sua organização do Exchange Online para desativar a pesquisa de log de auditoria.</span><span class="sxs-lookup"><span data-stu-id="7478a-138">You have to use remote PowerShell connected to your Exchange Online organization to turn off audit log search.</span></span> <span data-ttu-id="7478a-139">Semelhante à ativação da pesquisa de log de auditoria, você precisa ter atribuído a função de logs de auditoria no Exchange Online para desativar a pesquisa de log de auditoria.</span><span class="sxs-lookup"><span data-stu-id="7478a-139">Similar to turning on audit log search, you have to be assigned the Audit Logs role in Exchange Online to turn off audit log search.</span></span>
  
1. [<span data-ttu-id="7478a-140">Conectar-se ao PowerShell do Exchange Online </span><span class="sxs-lookup"><span data-stu-id="7478a-140">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=396554)
    
2. <span data-ttu-id="7478a-141">Execute o seguinte comando do PowerShell para desativar a pesquisa de log de auditoria no Office 365.</span><span class="sxs-lookup"><span data-stu-id="7478a-141">Run the following PowerShell command to turn off audit log search in Office 365.</span></span>
    
    ```
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. <span data-ttu-id="7478a-142">Após um tempo, verifique se a pesquisa de log de auditoria está desativada (desabilitada).</span><span class="sxs-lookup"><span data-stu-id="7478a-142">After a while, verify that audit log search is turned off (disabled).</span></span> <span data-ttu-id="7478a-143">Há duas maneiras de fazer isso:</span><span class="sxs-lookup"><span data-stu-id="7478a-143">There are two ways to do this:</span></span>
    
    - <span data-ttu-id="7478a-144">No PowerShell, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="7478a-144">In PowerShell, run the following command:</span></span>

        ```
        Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
        ```

        <span data-ttu-id="7478a-145">O valor da `False` propriedade _UnifiedAuditLogIngestionEnabled_ indica que a pesquisa de log de auditoria está desativada.</span><span class="sxs-lookup"><span data-stu-id="7478a-145">The value of  `False` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that audit log search is turned off.</span></span> 
    
    - <span data-ttu-id="7478a-146">No centro de conformidade & segurança, vá para pesquisa de **log de auditoria**de **pesquisa** \> e clique em **Pesquisar**.</span><span class="sxs-lookup"><span data-stu-id="7478a-146">In the Security & Compliance Center, go to **Search** \> **Audit log search**, and then click **Search**.</span></span>
    
      <span data-ttu-id="7478a-147">Uma mensagem é exibida dizendo que a pesquisa de log de auditoria não está ativada.</span><span class="sxs-lookup"><span data-stu-id="7478a-147">A message is displayed saying that audit log search isn't turned on.</span></span> 
    
      ![Uma mensagem será exibida se A auditoria estiver desativada](media/dca53da6-1cbe-4fa3-9860-f0d674de9538.png)
