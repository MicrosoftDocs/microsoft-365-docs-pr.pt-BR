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
ms.openlocfilehash: 841c5197addff704016e344ba7ae44355c872f72
ms.sourcegitcommit: 9f5b136b96b3af4db4cc6f5b1f35130ae60d6b12
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47817094"
---
# <a name="declare-records-by-using-retention-labels"></a><span data-ttu-id="52a2c-103">Declarar registros usando rótulos de retenção</span><span class="sxs-lookup"><span data-stu-id="52a2c-103">Declare records by using retention labels</span></span>

><span data-ttu-id="52a2c-104">*[Diretrizes de licenciamento do Microsoft 365 para segurança e conformidade](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="52a2c-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="52a2c-105">Para declarar documentos e emails como um registro, use [rótulos de retenção](retention.md#retention-labels) que identificam itens como registros.</span><span class="sxs-lookup"><span data-stu-id="52a2c-105">To declare documents and emails as a record, you use [retention labels](retention.md#retention-labels) that mark items as a record.</span></span> <span data-ttu-id="52a2c-106">É possível publicar esses rótulos para que usuários e administradores possam aplicá-los manualmente ou automaticamente ao conteúdo que você deseja classificar como registro.</span><span class="sxs-lookup"><span data-stu-id="52a2c-106">You can either publish those labels so that users and administrators can manually apply them to content, or auto-apply those labels to content that you want to mark as a record.</span></span>

## <a name="configuring-retention-labels-to-declare-records"></a><span data-ttu-id="52a2c-107">Configurar rótulos de retenção para declarar registros</span><span class="sxs-lookup"><span data-stu-id="52a2c-107">Configuring retention labels to declare records</span></span>

<span data-ttu-id="52a2c-108">Quando você criar ou configurar um rótulo de retenção, selecione a opção para marcar os itens como registros.</span><span class="sxs-lookup"><span data-stu-id="52a2c-108">When you create or configure a retention label, select the option to mark items as a record.</span></span>

>[!NOTE] 
> <span data-ttu-id="52a2c-109">A opção de marcar o conteúdo como registro não está disponível quando você cria ou configura rótulos de retenção da **Governança de Informações** no Centro de conformidade do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="52a2c-109">The option to mark the content as a record is not available when you create or configure retention labels from **Information Governance** in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="52a2c-110">Em vez disso, você deve usar o **Gerenciamento de Registros**.</span><span class="sxs-lookup"><span data-stu-id="52a2c-110">Instead, you must use **Records Management**.</span></span>

<span data-ttu-id="52a2c-111">Para criar um novo rótulo de retenção que marque o conteúdo como um registro:</span><span class="sxs-lookup"><span data-stu-id="52a2c-111">To create a new retention label that marks the content as a record:</span></span>

1. <span data-ttu-id="52a2c-112">No [Centro de conformidade do Microsoft 365](https://compliance.microsoft.com), vá para **Gerenciamento de Registros** \> **Plano de Arquivo**.</span><span class="sxs-lookup"><span data-stu-id="52a2c-112">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Records Management** \> **File Plan**.</span></span> <span data-ttu-id="52a2c-113">Na página **Planejamento de arquivos**, clique em **Criar um rótulo**.</span><span class="sxs-lookup"><span data-stu-id="52a2c-113">On the **File plan** page, select **Create a label**.</span></span>

2. <span data-ttu-id="52a2c-114">Na página **Definir configurações de retenção** no assistente, escolha a opção para marcar itens como registros:</span><span class="sxs-lookup"><span data-stu-id="52a2c-114">On the **Define retention settings** page in the wizard, choose the option to mark items as records:</span></span>
    
   ![Selecione a configuração de retenção para marcar os itens como um registro](../media/recordversioning6.png)

3. <span data-ttu-id="52a2c-116">Aplique o rótulo de retenção aos documentos do SharePoint ou OneDrive e emails do Exchange, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="52a2c-116">Apply the retention label to SharePoint or OneDrive documents and Exchange emails, as needed.</span></span> <span data-ttu-id="52a2c-117">Para obter instruções:</span><span class="sxs-lookup"><span data-stu-id="52a2c-117">For instructions:</span></span>
    
    - [<span data-ttu-id="52a2c-118">Criar rótulos de retenção e aplicá-los em aplicativos</span><span class="sxs-lookup"><span data-stu-id="52a2c-118">Create retention labels and apply them in apps</span></span>](create-apply-retention-labels.md)
    
    - [<span data-ttu-id="52a2c-119">Aplicar um rótulo de retenção automaticamente ao conteúdo</span><span class="sxs-lookup"><span data-stu-id="52a2c-119">Apply a retention label to content automatically</span></span>](apply-retention-labels-automatically.md)

## <a name="applying-the-configured-retention-label-to-content"></a><span data-ttu-id="52a2c-120">Aplicando o rótulo de retenção configurado ao conteúdo</span><span class="sxs-lookup"><span data-stu-id="52a2c-120">Applying the configured retention label to content</span></span>

<span data-ttu-id="52a2c-121">Quando os rótulos de retenção que marcam o conteúdo como registro são disponibilizados para os usuários aplicá-los nos aplicativos:</span><span class="sxs-lookup"><span data-stu-id="52a2c-121">When retention labels that mark content as a record are made available for users to apply them in apps:</span></span>

- <span data-ttu-id="52a2c-122">Para o Exchange, qualquer usuário com acesso de gravação à caixa de correio pode aplicar esses rótulos.</span><span class="sxs-lookup"><span data-stu-id="52a2c-122">For Exchange, any user with write-access to the mailbox can apply these labels.</span></span> 
- <span data-ttu-id="52a2c-123">Para o SharePoint e OneDrive, qualquer usuário no grupo Membros padrão (o nível de permissão de Contribuição) pode aplicar esses rótulos.</span><span class="sxs-lookup"><span data-stu-id="52a2c-123">For SharePoint and OneDrive, any user in the default Members group (the Contribute permission level) can apply these labels.</span></span>

<span data-ttu-id="52a2c-124">Exemplo de um documento marcado como registro usando um rótulo de retenção:</span><span class="sxs-lookup"><span data-stu-id="52a2c-124">Example of a document marked as record by using a retention label:</span></span>

![Painel de detalhes do documento marcado como um registro](../media/recordversioning7.png)

## <a name="next-steps"></a><span data-ttu-id="52a2c-126">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="52a2c-126">Next steps</span></span>

<span data-ttu-id="52a2c-127">Para obter uma lista dos cenários com suporte para o gerenciamento de registros, confira [Cenários comuns para o gerenciamento de registros](get-started-with-records-management.md#common-scenarios-for-records-management).</span><span class="sxs-lookup"><span data-stu-id="52a2c-127">For a list of scenarios supported by records management, see [Common scenarios for records management](get-started-with-records-management.md#common-scenarios-for-records-management).</span></span>
