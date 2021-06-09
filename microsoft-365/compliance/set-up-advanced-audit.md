---
title: Configurar Auditoria Avançada no Microsoft 365
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
- M365-security-compliance
- m365solution-audit
- m365initiative-compliance
- m365solution-scenario
search.appverid:
- MOE150
- MET150
description: Este artigo descreve como configurar a Auditoria Avançada para que você possa realizar investigações forenses quando contas de usuário são comprometidas ou para investigar outros incidentes relacionados à segurança.
ms.openlocfilehash: d1752ee7714056254a6c0e5c009aa9aa79ddff3b
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "52314256"
---
# <a name="set-up-advanced-audit-in-microsoft-365"></a><span data-ttu-id="b137f-103">Configurar Auditoria Avançada no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b137f-103">Set up Advanced Audit in Microsoft 365</span></span>

<span data-ttu-id="b137f-104">Se sua organização tiver uma assinatura e um licenciamento de usuário final compatível com Auditoria Avançada, execute as etapas a seguir para configurar e usar os recursos adicionais na Auditoria Avançada.</span><span class="sxs-lookup"><span data-stu-id="b137f-104">If your organization has a subscription and end user licensing that supports Advanced Audit, perform the following steps to set up and use the additional capabilities in Advanced Audit.</span></span>

![Fluxo de trabalho para configurar a Auditoria Avançada](../media/AdvancedAuditWorkflow.png)

## <a name="step1-set-up-advanced-audit-for-users"></a><span data-ttu-id="b137f-106">Etapa1: Configurar a Auditoria Avançada para usuários</span><span class="sxs-lookup"><span data-stu-id="b137f-106">Step1: Set up Advanced Audit for users</span></span>

<span data-ttu-id="b137f-107">Recursos de Auditoria Avançada, como a capacidade de registrar eventos cruciais, como MailItemsAccessed e Send, exigem uma licença E5 apropriada atribuída aos usuários.</span><span class="sxs-lookup"><span data-stu-id="b137f-107">Advanced Audit features such as the ability to log crucial events such as MailItemsAccessed and Send require an appropriate E5 license assigned to users.</span></span> <span data-ttu-id="b137f-108">Além disso, o aplicativo/plano de serviço de Auditoria Avançada deve ser habilitado para esses usuários.</span><span class="sxs-lookup"><span data-stu-id="b137f-108">Additionally, the Advanced Auditing app/service plan must be enabled for those users.</span></span> <span data-ttu-id="b137f-109">Para verificar se o aplicativo Auditoria Avançada está atribuído aos usuários, execute as seguintes etapas para cada usuário:</span><span class="sxs-lookup"><span data-stu-id="b137f-109">To verify that the Advanced Auditing app is assigned to users, perform the following steps for each user:</span></span>

1. <span data-ttu-id="b137f-110">No [Centro de administração do Microsoft 365](https://admin.microsoft.com/Adminportal), acesse **Usuários** > **Ativar usuários** e selecione um usuário.</span><span class="sxs-lookup"><span data-stu-id="b137f-110">In the [Microsoft 365 admin center](https://admin.microsoft.com/Adminportal), go to **Users** > **Active users**, and select a user.</span></span>

2. <span data-ttu-id="b137f-111">Na página flyout de propriedades do usuário, clique em **Licenças e aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="b137f-111">On the user properties flyout page, click **Licenses and apps**.</span></span>

3. <span data-ttu-id="b137f-112">Na seção **Licenças,** verifique se o usuário recebe uma licença E5 ou recebe uma licença de complemento apropriada.</span><span class="sxs-lookup"><span data-stu-id="b137f-112">In the **Licenses** section, verify that the user is assigned an E5 license or is assigned an appropriate add-on license.</span></span> <span data-ttu-id="b137f-113">Para ver uma lista de licenças que suportam Auditoria Avançada, consulte [Requisitos avançados de licenciamento de auditoria.](auditing-solutions-overview.md#advanced-audit-1)</span><span class="sxs-lookup"><span data-stu-id="b137f-113">For a list of licenses that support Advanced Audit, see [Advanced Audit licensing requirements](auditing-solutions-overview.md#advanced-audit-1).</span></span>

4. <span data-ttu-id="b137f-114">Expanda a seção **Aplicativos** e verifique se a caixa de seleção **Auditoria Avançada do Microsoft 365** está marcada.</span><span class="sxs-lookup"><span data-stu-id="b137f-114">Expand the **Apps** section, and verify that the **Microsoft 365 Advanced Auditing** checkbox is selected.</span></span>

5. <span data-ttu-id="b137f-115">Se a caixa de seleção não estiver selecionada, selecione-a e clique em **Salvar alterações.**</span><span class="sxs-lookup"><span data-stu-id="b137f-115">If the checkbox isn't selected, select it, and then click **Save changes.**</span></span>

   <span data-ttu-id="b137f-116">O registro em log de registros de auditoria para MailItemsAccessed e Send começará dentro de 24 horas.</span><span class="sxs-lookup"><span data-stu-id="b137f-116">The logging of audit records for MailItemsAccessed and Send will begin within 24 hours.</span></span> <span data-ttu-id="b137f-117">Você precisa executar a Etapa 3 para iniciar o log de dois outros eventos cruciais de Auditoria Avançada: SearchQueryInitiatedExchange e SearchQueryInitiatedSharePoint.</span><span class="sxs-lookup"><span data-stu-id="b137f-117">You have to perform Step 3 to start logging of two other Advanced Audit crucial events: SearchQueryInitiatedExchange and SearchQueryInitiatedSharePoint.</span></span>

<span data-ttu-id="b137f-118">Para organizações que atribuem licenças a grupos de usuários usando o licenciamento baseado em grupo, é necessário desativar a atribuição de licenciamento da Auditoria avançada do Microsoft 365 do grupo.</span><span class="sxs-lookup"><span data-stu-id="b137f-118">For organizations that assign licenses to groups of users by using group-based licensing, you have to turn off the licensing assignment for Microsoft 365 Advanced Auditing for the group.</span></span> <span data-ttu-id="b137f-119">Depois de salvar as alterações, verifique se a Auditoria Avançada do Microsoft 365 está desativada para o grupo.</span><span class="sxs-lookup"><span data-stu-id="b137f-119">After you save your changes, verify that Microsoft 365 Advanced Auditing is turned off for the group.</span></span> <span data-ttu-id="b137f-120">Em seguida, ative novamente a atribuição de licenciamento do grupo.</span><span class="sxs-lookup"><span data-stu-id="b137f-120">Then turn the licensing assignment for the group back on.</span></span> <span data-ttu-id="b137f-121">Para obter mais instruções do licenciamento baseado em grupo, consulte [Atribuir licenças a usuários por membro de grupo no Azure Active Directory](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span><span class="sxs-lookup"><span data-stu-id="b137f-121">For instructions about group-based licensing, see [Assign licenses to users by group membership in Azure Active Directory](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>

<span data-ttu-id="b137f-122">Além disso, se você tiver personalizado as ações de caixa de correio que estão registradas em caixas de correio de usuário ou caixas de correio compartilhadas, quaisquer novos eventos cruciais lançados pela Microsoft não serão auditados automaticamente nessas caixas de correio.</span><span class="sxs-lookup"><span data-stu-id="b137f-122">Also, if you have customized the mailbox actions that are logged on user mailboxes or shared mailboxes, any new crucial events released by Microsoft will not be automatically audited on those mailboxes.</span></span> <span data-ttu-id="b137f-123">Para obter informações sobre como alterar as ações da caixa de correio que são auditadas para cada tipo de logon, confira a seção "Alterar ou restaurar ações da caixa de correio registradas por padrão" em [Gerenciar auditoria de caixa de correio](enable-mailbox-auditing.md#change-or-restore-mailbox-actions-logged-by-default).</span><span class="sxs-lookup"><span data-stu-id="b137f-123">For information about changing the mailbox actions that are audited for each logon type, see the "Change or restore mailbox actions logged by default" section in [Manage mailbox auditing](enable-mailbox-auditing.md#change-or-restore-mailbox-actions-logged-by-default).</span></span>

## <a name="step-2-enable-crucial-events"></a><span data-ttu-id="b137f-124">Etapa 2: Habilitar eventos cruciais</span><span class="sxs-lookup"><span data-stu-id="b137f-124">Step 2: Enable crucial events</span></span>

<span data-ttu-id="b137f-125">Você precisa habilitar dois eventos cruciais (SearchQueryInitiatedExchange e SearchQueryInitiatedSharePoint) a serem registrados quando os usuários realizam pesquisas no Exchange Online e SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="b137f-125">You have to enable two crucial events (SearchQueryInitiatedExchange and SearchQueryInitiatedSharePoint) to be logged when users perform searches in Exchange Online and SharePoint Online.</span></span> <span data-ttu-id="b137f-126">Para permitir que esses dois eventos sejam auditados para usuários, execute o seguinte comando (para cada usuário) no [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell):</span><span class="sxs-lookup"><span data-stu-id="b137f-126">To enable these two events to be audited for users, run the following command (for each user) in [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell):</span></span>

```powershell
Set-Mailbox <user> -AuditOwner @{Add="SearchQueryInitiated"}
```

<span data-ttu-id="b137f-127">Em um ambiente multi-geo, você deve executar o comando **Set-Mailbox** anterior na floresta onde a caixa de correio do usuário está localizada.</span><span class="sxs-lookup"><span data-stu-id="b137f-127">In a multi-geo environment, you must run the previous **Set-Mailbox** command in the forest where the user's mailbox is located.</span></span> <span data-ttu-id="b137f-128">Para identificar o local da caixa de correio do usuário, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="b137f-128">To identify the user's mailbox location, run the following command:</span></span> 

```powershell
Get-Mailbox <user identity> | FL MailboxLocations
```

<span data-ttu-id="b137f-129">Se o comando para habilitar a auditoria de consultas de pesquisa foi executado anteriormente em uma floresta diferente da que a caixa de correio do usuário está localizada, você deve remover o valor SearchQueryInitiated da caixa de correio do usuário executando e, em seguida, adicioná-lo à caixa de correio do usuário na floresta onde a caixa de correio do usuário está `Set-Mailbox -AuditOwner @{Remove="SearchQueryInitiated"}` localizada.</span><span class="sxs-lookup"><span data-stu-id="b137f-129">If the command to enable the auditing of search queries was previously run in a forest that's different than the one the user's mailbox is located in, then you must remove the SearchQueryInitiated value from the user's mailbox by running `Set-Mailbox -AuditOwner @{Remove="SearchQueryInitiated"}` and then add it to the user's mailbox in the forest where the user's mailbox is located.</span></span>

## <a name="step-3-set-up-audit-retention-policies"></a><span data-ttu-id="b137f-130">Etapa 3: Configurar políticas de retenção de auditoria</span><span class="sxs-lookup"><span data-stu-id="b137f-130">Step 3: Set up audit retention policies</span></span>

<span data-ttu-id="b137f-131">Além da política padrão que retém os registros de auditoria do Exchange, SharePoint e Azure AD por um ano, você pode criar políticas adicionais de retenção do log de auditoria para atender aos requisitos das operações de segurança, TI e das equipes de conformidade de sua organização.</span><span class="sxs-lookup"><span data-stu-id="b137f-131">In additional to the default policy that retains Exchange, SharePoint, and Azure AD audit records for one year, you can create additional audit log retention policies to meet the requirements of your organization's security operations, IT, and compliance teams.</span></span> <span data-ttu-id="b137f-132">Para saber mais, confira [Gerenciar políticas de retenção de log de auditoria](audit-log-retention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="b137f-132">For more information, see [Manage audit log retention policies](audit-log-retention-policies.md).</span></span>

## <a name="step-4-search-for-crucial-events"></a><span data-ttu-id="b137f-133">Etapa 4: Pesquisar eventos cruciais</span><span class="sxs-lookup"><span data-stu-id="b137f-133">Step 4: Search for crucial events</span></span>

<span data-ttu-id="b137f-134">Agora que você tem a Auditoria Avançada configurada para sua organização, você pode pesquisar eventos cruciais e outras atividades ao conduzir investigações forenses.</span><span class="sxs-lookup"><span data-stu-id="b137f-134">Now that you have Advanced Audit set up for your organization, you can search for crucial events and other activities when conducting forensic investigations.</span></span> <span data-ttu-id="b137f-135">Após concluir a Etapa 1 e a Etapa 2, você pode pesquisar no log de auditoria eventos cruciais e outras atividades durante investigações forenses de contas comprometidas e outros tipos de investigações de segurança ou conformidade.</span><span class="sxs-lookup"><span data-stu-id="b137f-135">After completing Step 1 and Step 2, you can search the audit log for crucial events and other activities during forensic investigations of compromised accounts and other types of security or compliance investigations.</span></span> <span data-ttu-id="b137f-136">Para obter mais informações sobre como conduzir uma investigação forense de contas de usuário comprometidas usando o evento crucial MailItemsAccessed, consulte [Use Advanced Audit to investigate compromised accounts](mailitemsaccessed-forensics-investigations.md).</span><span class="sxs-lookup"><span data-stu-id="b137f-136">For more information about conducting a forensics investigation of compromised user accounts by using the MailItemsAccessed crucial event, see [Use Advanced Audit to investigate compromised accounts](mailitemsaccessed-forensics-investigations.md).</span></span>
