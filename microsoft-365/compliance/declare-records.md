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
ms.openlocfilehash: c8024cf08be2259ffa8b6747bebf4943e11e4d60
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695228"
---
# <a name="declare-records-by-using-retention-labels"></a><span data-ttu-id="e502b-103">Declarar registros usando rótulos de retenção</span><span class="sxs-lookup"><span data-stu-id="e502b-103">Declare records by using retention labels</span></span>

><span data-ttu-id="e502b-104">*[Diretrizes de licenciamento do Microsoft 365 para segurança e conformidade](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="e502b-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="e502b-105">Você usa [rótulos de retenção](retention.md#retention-labels) para marcar conteúdos como registros.</span><span class="sxs-lookup"><span data-stu-id="e502b-105">You use [retention labels](retention.md#retention-labels) to mark content as a record.</span></span> <span data-ttu-id="e502b-106">É possível publicar esses rótulos para que usuários e administradores possam aplicá-los manualmente ou automaticamente ao conteúdo que você deseja classificar como registro.</span><span class="sxs-lookup"><span data-stu-id="e502b-106">You can either publish those labels so that users and administrators can manually apply them to content, or auto-apply those labels to content that you want to mark as a record.</span></span>

## <a name="configuring-retention-labels-to-declare-records"></a><span data-ttu-id="e502b-107">Configurar rótulos de retenção para declarar registros</span><span class="sxs-lookup"><span data-stu-id="e502b-107">Configuring retention labels to declare records</span></span>

<span data-ttu-id="e502b-108">Ao criar um [rótulo de retenção](retention.md#retention-labels), escolha a opção de marcar o conteúdo como um registro.</span><span class="sxs-lookup"><span data-stu-id="e502b-108">When you create a [retention label](retention.md#retention-labels), select the option to mark the content as a record.</span></span>

>[!NOTE] 
> <span data-ttu-id="e502b-109">A opção de marcar o conteúdo como registro não está disponível quando você cria ou configura rótulos de retenção da **Governança de Informações** no Centro de conformidade do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e502b-109">The option to mark the content as a record is not available when you create or configure retention labels from **Information Governance** in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="e502b-110">Em vez disso, você deve usar o **Gerenciamento de Registros**.</span><span class="sxs-lookup"><span data-stu-id="e502b-110">Instead, you must use **Records Management**.</span></span>

1. <span data-ttu-id="e502b-111">No [Centro de conformidade do Microsoft 365](https://compliance.microsoft.com), vá para **Gerenciamento de Registros** \> **Plano de Arquivo**.</span><span class="sxs-lookup"><span data-stu-id="e502b-111">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Records Management** \> **File Plan**.</span></span> <span data-ttu-id="e502b-112">Na página **Planejamento de arquivos**, clique em **Criar um rótulo**.</span><span class="sxs-lookup"><span data-stu-id="e502b-112">On the **File plan** page, select **Create a label**.</span></span>

2. <span data-ttu-id="e502b-113">Na página **Configurações de rótulo** no assistente, escolha a opção para classificar o conteúdo como registro.</span><span class="sxs-lookup"><span data-stu-id="e502b-113">On the **Label settings** page in the wizard, choose the option to classify content as a record.</span></span>
    
   ![Clique em Usar rótulo para classificar o conteúdo como uma caixa de seleção de Registro](../media/recordversioning6.png)

3. <span data-ttu-id="e502b-115">Aplique o rótulo de retenção aos documentos do SharePoint ou OneDrive e emails do Exchange, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="e502b-115">Apply the retention label to SharePoint or OneDrive documents and Exchange emails, as needed.</span></span> <span data-ttu-id="e502b-116">Para obter instruções:</span><span class="sxs-lookup"><span data-stu-id="e502b-116">For instructions:</span></span>
    
    - [<span data-ttu-id="e502b-117">Criar rótulos de retenção e aplicá-los em aplicativos</span><span class="sxs-lookup"><span data-stu-id="e502b-117">Create retention labels and apply them in apps</span></span>](create-apply-retention-labels.md)
    
    - [<span data-ttu-id="e502b-118">Aplicar um rótulo de retenção automaticamente ao conteúdo</span><span class="sxs-lookup"><span data-stu-id="e502b-118">Apply a retention label to content automatically</span></span>](apply-retention-labels-automatically.md)

## <a name="applying-the-configured-retention-label-to-content"></a><span data-ttu-id="e502b-119">Aplicando o rótulo de retenção configurado ao conteúdo</span><span class="sxs-lookup"><span data-stu-id="e502b-119">Applying the configured retention label to content</span></span>

<span data-ttu-id="e502b-120">Quando os rótulos de retenção que marcam o conteúdo como registro são disponibilizados para os usuários aplicá-los nos aplicativos:</span><span class="sxs-lookup"><span data-stu-id="e502b-120">When retention labels that mark content as a record are made available for users to apply them in apps:</span></span>

- <span data-ttu-id="e502b-121">Para o Exchange, qualquer usuário com acesso de gravação à caixa de correio pode aplicar esses rótulos.</span><span class="sxs-lookup"><span data-stu-id="e502b-121">For Exchange, any user with write-access to the mailbox can apply these labels.</span></span> 
- <span data-ttu-id="e502b-122">Para o SharePoint e OneDrive, qualquer usuário no grupo Membros padrão (o nível de permissão de Contribuição) pode aplicar esses rótulos.</span><span class="sxs-lookup"><span data-stu-id="e502b-122">For SharePoint and OneDrive, any user in the default Members group (the Contribute permission level) can apply these labels.</span></span>

<span data-ttu-id="e502b-123">Exemplo de um documento marcado como registro usando um rótulo de retenção:</span><span class="sxs-lookup"><span data-stu-id="e502b-123">Example of a document marked as record by using a retention label:</span></span>

![Painel de detalhes do documento marcado como um registro](../media/recordversioning7.png)

## <a name="next-steps"></a><span data-ttu-id="e502b-125">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="e502b-125">Next steps</span></span>

<span data-ttu-id="e502b-126">Se você precisar atualizar documentos que são registros, confira [Usar controle de versão de registro para atualizar registros armazenados no SharePoint ou no OneDrive](record-versioning.md).</span><span class="sxs-lookup"><span data-stu-id="e502b-126">If you need to update documents that are records, see [Use record versioning to update records stored in SharePoint or OneDrive](record-versioning.md).</span></span>

<span data-ttu-id="e502b-127">Para saber mais sobre a disposição de registros, confira [Descarte de conteúdo](disposition.md).</span><span class="sxs-lookup"><span data-stu-id="e502b-127">To learn about the disposition of records, see [Disposing of content](disposition.md).</span></span>
