---
title: Declarar registros usando rótulos de retenção
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 'Declarar registros usando rótulos de retenção. '
ms.openlocfilehash: ba0587619609adba2d7746a45a3b24008a4a00be
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226990"
---
# <a name="declare-records-by-using-retention-labels"></a><span data-ttu-id="cffd9-103">Declarar registros usando rótulos de retenção</span><span class="sxs-lookup"><span data-stu-id="cffd9-103">Declare records by using retention labels</span></span>

><span data-ttu-id="cffd9-104">*[Diretrizes de licenciamento do Microsoft 365 para segurança e conformidade](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span><span class="sxs-lookup"><span data-stu-id="cffd9-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

<span data-ttu-id="cffd9-105">Para declarar documentos e emails como [registros](records-management.md#records), use [rótulos de retenção](retention.md#retention-labels) que marquem o conteúdo como um **registro** ou um **registro regulatório**.</span><span class="sxs-lookup"><span data-stu-id="cffd9-105">To declare documents and emails as [records](records-management.md#records), you use [retention labels](retention.md#retention-labels) that mark the content as a **record** or a **regulatory record**.</span></span>

<span data-ttu-id="cffd9-106">Se você não tiver certeza se deseja usar um registro ou um registro normativo, confira [Comparar restrições para quais ações são permitidas ou bloqueadas](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked).</span><span class="sxs-lookup"><span data-stu-id="cffd9-106">If you're not sure whether to use a record or a regulatory record, see [Compare restrictions for what actions are allowed or blocked](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked).</span></span> <span data-ttu-id="cffd9-107">Se precisar usar registros regulatórios, primeiro você deve executar um comando do Windows PowerShell, conforme descrito na próxima seção.</span><span class="sxs-lookup"><span data-stu-id="cffd9-107">If you need to use regulatory records, you must first run a PowerShell command, as described in the next section.</span></span>

<span data-ttu-id="cffd9-108">Em seguida, você pode publicar esses rótulos em uma política de rótulo de retenção para que os usuários e administradores possam aplicá-los ao conteúdo ou a rótulos que marcam itens como registros (mas não registros regulatórios), aplicam automaticamente esses rótulos ao conteúdo desejado para declarar um registro.</span><span class="sxs-lookup"><span data-stu-id="cffd9-108">You can then either publish those labels in a retention label policy so that users and administrators can apply them to content, or for labels that mark items as records (but not regulatory records), auto-apply those labels to content that you want to declare a record.</span></span>

## <a name="how-to-display-the-option-to-mark-content-as-a-regulatory-record"></a><span data-ttu-id="cffd9-109">Como exibir a opção para marcar o conteúdo como um registro regulatório</span><span class="sxs-lookup"><span data-stu-id="cffd9-109">How to display the option to mark content as a regulatory record</span></span>

> [!NOTE]
> <span data-ttu-id="cffd9-110">O procedimento a seguir é uma ação auditável, registrar em log **Opção de registro regulatório habilitado para rótulos de retenção** na seção [Política de retenção e atividades de rótulo de retenção](search-the-audit-log-in-security-and-compliance.md#retention-policy-and-retention-label-activities) do log de auditoria.</span><span class="sxs-lookup"><span data-stu-id="cffd9-110">The following procedure is an auditable action, logging **Enabled regulatory record option for retention labels** in the [Retention policy and retention label activities](search-the-audit-log-in-security-and-compliance.md#retention-policy-and-retention-label-activities) section of the audit log.</span></span>

<span data-ttu-id="cffd9-111">Por padrão, a opção de rótulo de retenção para marcar o conteúdo como um registro regulatório não é exibida no assistente de etiqueta de retenção.</span><span class="sxs-lookup"><span data-stu-id="cffd9-111">By default, the retention label option to mark content as a regulatory record isn't displayed in the retention label wizard.</span></span> <span data-ttu-id="cffd9-112">Para exibir essa opção, você deve primeiro executar um comando do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="cffd9-112">To display this option, you must first run a PowerShell command:</span></span>

1. <span data-ttu-id="cffd9-113">[Conecte-se ao Centro de Segurança e Conformidade do Office 365 PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="cffd9-113">[Connect to the Office 365 Security & Compliance Center PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="cffd9-114">Execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="cffd9-114">Run the following cmdlet:</span></span>

    ```powershell
    Set-RegulatoryComplianceUI -Enabled $true
    ````

    <span data-ttu-id="cffd9-115">Não há uma solicitação para confirmar e a configuração tem efeito imediatamente.</span><span class="sxs-lookup"><span data-stu-id="cffd9-115">There is no prompt to confirm and the setting takes effect immediately.</span></span>

<span data-ttu-id="cffd9-116">Se você mudar de ideia sobre como ver essa opção no assistente de etiqueta de retenção, é possível ocultá-la novamente executando o mesmo cmdlet com o **falso** valor: `Set-RegulatoryComplianceUI -Enabled $false`</span><span class="sxs-lookup"><span data-stu-id="cffd9-116">If you change your mind about seeing this option in the retention label wizard, you can hide it again by running the same cmdlet with the **false** value: `Set-RegulatoryComplianceUI -Enabled $false`</span></span>

## <a name="configuring-retention-labels-to-declare-records"></a><span data-ttu-id="cffd9-117">Configurar rótulos de retenção para declarar registros</span><span class="sxs-lookup"><span data-stu-id="cffd9-117">Configuring retention labels to declare records</span></span>

<span data-ttu-id="cffd9-118">Ao criar um rótulo de retenção na solução **Gerenciamento de Registros** no Centro de conformidade do Microsoft 365, você tem a opção de marcar os itens como um registro.</span><span class="sxs-lookup"><span data-stu-id="cffd9-118">When you create a retention label from the **Records Management** solution in the Microsoft 365 compliance center, you have the option to mark items as a record.</span></span> <span data-ttu-id="cffd9-119">Caso tenha executado o comando do Windows PowerShell da seção anterior, você pode marcar os itens como um registro regulatório.</span><span class="sxs-lookup"><span data-stu-id="cffd9-119">If you ran the PowerShell command from the previous section, you can alternatively mark items as a regulatory record.</span></span>

<span data-ttu-id="cffd9-120">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="cffd9-120">For example:</span></span>

![Configurar um rótulo de retenção para marcar o conteúdo como um registro ou uma regulamentação](../media/recordversioning6.png)

<span data-ttu-id="cffd9-122">Usando esse rótulo de retenção, você pode aplicá-lo a documentos do Microsoft Office SharePoint Online ou do Microsoft OneDrive e a emails do Exchange, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="cffd9-122">Using this retention label, you can now apply it to SharePoint or OneDrive documents and Exchange emails, as needed.</span></span>

<span data-ttu-id="cffd9-123">Para obter instruções completas:</span><span class="sxs-lookup"><span data-stu-id="cffd9-123">For full instructions:</span></span>

- [<span data-ttu-id="cffd9-124">Criar rótulos de retenção e aplicá-los em aplicativos</span><span class="sxs-lookup"><span data-stu-id="cffd9-124">Create retention labels and apply them in apps</span></span>](create-apply-retention-labels.md)

- <span data-ttu-id="cffd9-125">[Aplicar um rótulo de retenção ao conteúdo automaticamente](apply-retention-labels-automatically.md) (sem suporte para registros regulatórios)</span><span class="sxs-lookup"><span data-stu-id="cffd9-125">[Apply a retention label to content automatically](apply-retention-labels-automatically.md) (not supported for regulatory records)</span></span>


## <a name="applying-the-configured-retention-label-to-content"></a><span data-ttu-id="cffd9-126">Aplicando o rótulo de retenção configurado ao conteúdo</span><span class="sxs-lookup"><span data-stu-id="cffd9-126">Applying the configured retention label to content</span></span>

<span data-ttu-id="cffd9-127">Quando os rótulos de retenção que marcam itens como registro ou registro regulatório estão disponíveis para os usuários aplicá-los em aplicativos:</span><span class="sxs-lookup"><span data-stu-id="cffd9-127">When retention labels that mark items as a record or regulatory record are made available for users to apply them in apps:</span></span>

- <span data-ttu-id="cffd9-128">Para o Exchange, qualquer usuário com acesso de gravação à caixa de correio pode aplicar esses rótulos.</span><span class="sxs-lookup"><span data-stu-id="cffd9-128">For Exchange, any user with write-access to the mailbox can apply these labels.</span></span>
- <span data-ttu-id="cffd9-129">Para o SharePoint e OneDrive, qualquer usuário no grupo Membros padrão (o nível de permissão de Contribuição) pode aplicar esses rótulos.</span><span class="sxs-lookup"><span data-stu-id="cffd9-129">For SharePoint and OneDrive, any user in the default Members group (the Contribute permission level) can apply these labels.</span></span>

<span data-ttu-id="cffd9-130">Exemplo de um documento marcado como registro usando um rótulo de retenção:</span><span class="sxs-lookup"><span data-stu-id="cffd9-130">Example of a document marked as record by using a retention label:</span></span>

![Painel de detalhes do documento marcado como um registro](../media/recordversioning7.png)

## <a name="searching-the-audit-log-for-labeled-items-that-were-declared-records"></a><span data-ttu-id="cffd9-132">Pesquisando o log de auditoria em itens rotulados que foram declarados registros</span><span class="sxs-lookup"><span data-stu-id="cffd9-132">Searching the audit log for labeled items that were declared records</span></span>

<span data-ttu-id="cffd9-133">As ações de rotulação para declarar itens como registros são registradas no log de auditoria.</span><span class="sxs-lookup"><span data-stu-id="cffd9-133">The actions of labeling to declare items as records are logged in the audit log.</span></span>

<span data-ttu-id="cffd9-134">Para itens do SharePoint:</span><span class="sxs-lookup"><span data-stu-id="cffd9-134">For SharePoint items:</span></span>
- <span data-ttu-id="cffd9-135">Nas **Atividades de arquivo e páginas**, selecione **Rótulo de retenção alterado para um arquivo**.</span><span class="sxs-lookup"><span data-stu-id="cffd9-135">From **File and page activities**, select **Changed retention label for a file**.</span></span> <span data-ttu-id="cffd9-136">Esse evento de auditoria é para rótulos de retenção que marcam itens como registros, registros regulamentais ou que são rótulos de retenção padrão.</span><span class="sxs-lookup"><span data-stu-id="cffd9-136">This audit event is for retention labels that mark items as records, regulatory records, or that are standard retention labels.</span></span>

<span data-ttu-id="cffd9-137">Para itens do Exchange:</span><span class="sxs-lookup"><span data-stu-id="cffd9-137">For Exchange items:</span></span>
- <span data-ttu-id="cffd9-138">Nas **Atividades de correio do Exchange**, selecione **Mensagem rotulada como um registro**.</span><span class="sxs-lookup"><span data-stu-id="cffd9-138">From **Exchange mailbox activities**, select **Labeled message as a record**.</span></span> <span data-ttu-id="cffd9-139">Esse evento de auditoria é para rótulos de retenção que marcam itens como registros ou registros regulamentais.</span><span class="sxs-lookup"><span data-stu-id="cffd9-139">This audit event is for retention labels that mark items as records or regulatory records.</span></span>

<span data-ttu-id="cffd9-140">Para obter mais informações sobre a pesquisa desses eventos, confira [Pesquisar o log de auditoria no Centro de Conformidade e Segurança](search-the-audit-log-in-security-and-compliance.md#file-and-page-activities).</span><span class="sxs-lookup"><span data-stu-id="cffd9-140">For more information about searching for these events, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md#file-and-page-activities).</span></span>

## <a name="next-steps"></a><span data-ttu-id="cffd9-141">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="cffd9-141">Next steps</span></span>

<span data-ttu-id="cffd9-142">Para obter uma lista dos cenários com suporte para o gerenciamento de registros, confira [Cenários comuns para o gerenciamento de registros](get-started-with-records-management.md#common-scenarios-for-records-management).</span><span class="sxs-lookup"><span data-stu-id="cffd9-142">For a list of scenarios supported by records management, see [Common scenarios for records management](get-started-with-records-management.md#common-scenarios-for-records-management).</span></span>
