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
ms.openlocfilehash: 490f81ba9c1d2d291539107650ec3c3f5938eba8
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198916"
---
# <a name="declare-records-by-using-retention-labels"></a><span data-ttu-id="7286a-103">Declarar registros usando rótulos de retenção</span><span class="sxs-lookup"><span data-stu-id="7286a-103">Declare records by using retention labels</span></span>

><span data-ttu-id="7286a-104">*[Diretrizes de licenciamento do Microsoft 365 para segurança e conformidade](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="7286a-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="7286a-105">Para declarar documentos e emails como [registros](records-management.md#records), use [rótulos de retenção](retention.md#retention-labels) que marquem o conteúdo como um **registro** ou um **registro regulatório**.</span><span class="sxs-lookup"><span data-stu-id="7286a-105">To declare documents and emails as [records](records-management.md#records), you use [retention labels](retention.md#retention-labels) that mark the content as a **record** or a **regulatory record**.</span></span>

> [!NOTE]
> <span data-ttu-id="7286a-106">Os registros regulatórios estão no modo de visualização.</span><span class="sxs-lookup"><span data-stu-id="7286a-106">Regulatory records are currently in preview.</span></span>

<span data-ttu-id="7286a-107">Se você não tiver certeza se deseja usar um registro ou um registro normativo, confira [Comparar restrições para quais ações são permitidas ou bloqueadas](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked).</span><span class="sxs-lookup"><span data-stu-id="7286a-107">If you're not sure whether to use a record or a regulatory record, see [Compare restrictions for what actions are allowed or blocked](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked).</span></span> <span data-ttu-id="7286a-108">Se precisar usar registros regulatórios, primeiro você deve executar um comando do Windows PowerShell, conforme descrito na próxima seção.</span><span class="sxs-lookup"><span data-stu-id="7286a-108">If you need to use regulatory records, you must first run a PowerShell command, as described in the next section.</span></span>

<span data-ttu-id="7286a-109">Em seguida, você pode publicar esses rótulos em uma política de rótulo de retenção para que os usuários e administradores possam aplicá-los ao conteúdo ou a rótulos que marcam itens como registros (mas não registros regulatórios), aplicam automaticamente esses rótulos ao conteúdo desejado para declarar um registro.</span><span class="sxs-lookup"><span data-stu-id="7286a-109">You can then either publish those labels in a retention label policy so that users and administrators can apply them to content, or for labels that mark items as records (but not regulatory records), auto-apply those labels to content that you want to declare a record.</span></span>

## <a name="how-to-display-the-option-to-mark-content-as-a-regulatory-record"></a><span data-ttu-id="7286a-110">Como exibir a opção para marcar o conteúdo como um registro regulatório</span><span class="sxs-lookup"><span data-stu-id="7286a-110">How to display the option to mark content as a regulatory record</span></span>

>[!NOTE] 
> <span data-ttu-id="7286a-111">O procedimento a seguir é uma ação auditável, registrar em log \*\* Opção de registro regulatório habilitado para rótulos de retenção\*\* na seção [Política de retenção e atividades de rótulo de retenção](search-the-audit-log-in-security-and-compliance.md#retention-policy-and-retention-label-activities) do log de auditoria.</span><span class="sxs-lookup"><span data-stu-id="7286a-111">The following procedure is an auditable action, logging **Enabled regulatory record option for retention labels** in the [Retention policy and retention label activities](search-the-audit-log-in-security-and-compliance.md#retention-policy-and-retention-label-activities) section of the audit log.</span></span>

<span data-ttu-id="7286a-112">Por padrão, a opção de rótulo de retenção para marcar o conteúdo como um registro regulatório não é exibida no assistente de etiqueta de retenção.</span><span class="sxs-lookup"><span data-stu-id="7286a-112">By default, the retention label option to mark content as a regulatory record isn't displayed in the retention label wizard.</span></span> <span data-ttu-id="7286a-113">Para exibir essa opção, você deve primeiro executar um comando do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="7286a-113">To display this option, you must first run a PowerShell command:</span></span>

1. <span data-ttu-id="7286a-114">[Conecte-se ao Centro de Segurança e Conformidade do Office 365 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="7286a-114">[Connect to the Office 365 Security & Compliance Center Powershell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="7286a-115">Execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="7286a-115">Run the following cmdlet:</span></span>
    
    ```powershell
    Set-RegulatoryComplianceUI -Enabled $true
    ````
    <span data-ttu-id="7286a-116">Não há uma solicitação para confirmar e a configuração tem efeito imediatamente.</span><span class="sxs-lookup"><span data-stu-id="7286a-116">There is no prompt to confirm and the setting takes effect immediately.</span></span>

<span data-ttu-id="7286a-117">Se você mudar de ideia sobre como ver essa opção no assistente de etiqueta de retenção, é possível ocultá-la novamente executando o mesmo cmdlet com o **falso** valor: `Set-RegulatoryComplianceUI -Enabled $false`</span><span class="sxs-lookup"><span data-stu-id="7286a-117">If you change your mind about seeing this option in the retention label wizard, you can hide it again by running the same cmdlet with the **false** value: `Set-RegulatoryComplianceUI -Enabled $false`</span></span> 

## <a name="configuring-retention-labels-to-declare-records"></a><span data-ttu-id="7286a-118">Configurar rótulos de retenção para declarar registros</span><span class="sxs-lookup"><span data-stu-id="7286a-118">Configuring retention labels to declare records</span></span>

<span data-ttu-id="7286a-119">Ao criar ou editar um rótulo de retenção na solução **Gerenciamento de Registros** no Centro de conformidade do Microsoft 365, você tem a opção de marcar os itens como um registro.</span><span class="sxs-lookup"><span data-stu-id="7286a-119">When you create or edit a retention label from the **Records Management** solution in the Microsoft 365 compliance center, you have the option to mark items as a record.</span></span> <span data-ttu-id="7286a-120">Caso tenha executado o comando do Windows PowerShell da seção anterior, você pode marcar os itens como um registro regulatório.</span><span class="sxs-lookup"><span data-stu-id="7286a-120">If you ran the PowerShell command from the previous section, you can alternatively mark items as a regulatory record.</span></span>

<span data-ttu-id="7286a-121">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="7286a-121">For example:</span></span>

![Configurar um rótulo de retenção para marcar o conteúdo como um registro ou uma regulamentação](../media/recordversioning6.png)

<span data-ttu-id="7286a-123">Usando esse rótulo de retenção, você pode aplicá-lo a documentos do Microsoft Office SharePoint Online ou do Microsoft OneDrive e a emails do Exchange, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="7286a-123">Using this retention label, you can now apply it to SharePoint or OneDrive documents and Exchange emails, as needed.</span></span> 

<span data-ttu-id="7286a-124">Para obter instruções completas:</span><span class="sxs-lookup"><span data-stu-id="7286a-124">For full instructions:</span></span>

- [<span data-ttu-id="7286a-125">Criar rótulos de retenção e aplicá-los em aplicativos</span><span class="sxs-lookup"><span data-stu-id="7286a-125">Create retention labels and apply them in apps</span></span>](create-apply-retention-labels.md)

- <span data-ttu-id="7286a-126">[Aplicar um rótulo de retenção ao conteúdo automaticamente](apply-retention-labels-automatically.md) (sem suporte para registros regulatórios)</span><span class="sxs-lookup"><span data-stu-id="7286a-126">[Apply a retention label to content automatically](apply-retention-labels-automatically.md) (not supported for regulatory records)</span></span>


## <a name="applying-the-configured-retention-label-to-content"></a><span data-ttu-id="7286a-127">Aplicando o rótulo de retenção configurado ao conteúdo</span><span class="sxs-lookup"><span data-stu-id="7286a-127">Applying the configured retention label to content</span></span>

<span data-ttu-id="7286a-128">Quando os rótulos de retenção que marcam itens como registro ou registro regulatório estão disponíveis para os usuários aplicá-los em aplicativos:</span><span class="sxs-lookup"><span data-stu-id="7286a-128">When retention labels that mark items as a record or regulatory record are made available for users to apply them in apps:</span></span>

- <span data-ttu-id="7286a-129">Para o Exchange, qualquer usuário com acesso de gravação à caixa de correio pode aplicar esses rótulos.</span><span class="sxs-lookup"><span data-stu-id="7286a-129">For Exchange, any user with write-access to the mailbox can apply these labels.</span></span> 
- <span data-ttu-id="7286a-130">Para o SharePoint e OneDrive, qualquer usuário no grupo Membros padrão (o nível de permissão de Contribuição) pode aplicar esses rótulos.</span><span class="sxs-lookup"><span data-stu-id="7286a-130">For SharePoint and OneDrive, any user in the default Members group (the Contribute permission level) can apply these labels.</span></span>

<span data-ttu-id="7286a-131">Exemplo de um documento marcado como registro usando um rótulo de retenção:</span><span class="sxs-lookup"><span data-stu-id="7286a-131">Example of a document marked as record by using a retention label:</span></span>

![Painel de detalhes do documento marcado como um registro](../media/recordversioning7.png)

## <a name="next-steps"></a><span data-ttu-id="7286a-133">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="7286a-133">Next steps</span></span>

<span data-ttu-id="7286a-134">Para obter uma lista dos cenários com suporte para o gerenciamento de registros, confira [Cenários comuns para o gerenciamento de registros](get-started-with-records-management.md#common-scenarios-for-records-management).</span><span class="sxs-lookup"><span data-stu-id="7286a-134">For a list of scenarios supported by records management, see [Common scenarios for records management](get-started-with-records-management.md#common-scenarios-for-records-management).</span></span>
