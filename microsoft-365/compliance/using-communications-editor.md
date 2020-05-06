---
title: Usar o editor de comunicações
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
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Use o editor de comunicações para alterar o texto e as variáveis de campo de mesclagem ao Formatar o conteúdo.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 0cb415da9aa09452176bd8aa9be4575cfc827582
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034473"
---
# <a name="use-the-communications-editor"></a><span data-ttu-id="aebc8-103">Usar o editor de comunicações</span><span class="sxs-lookup"><span data-stu-id="aebc8-103">Use the communications editor</span></span>

<span data-ttu-id="aebc8-104">À medida que você define o conteúdo do seu conteúdo de portal, as notificações de retenção legal e lembretes/rementeções relacionados, você pode aproveitar o editor de comunicações para formatar e personalizar dinamicamente o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="aebc8-104">As you define the content of your portal content, legal hold notifications, and related reminders/escalations, you can leverage the Communications Editor to format and dynamically customize your content.</span></span>

## <a name="rich-text-editor"></a><span data-ttu-id="aebc8-105">Editor de Rich Text</span><span class="sxs-lookup"><span data-stu-id="aebc8-105">Rich text editor</span></span> 

<span data-ttu-id="aebc8-106">O editor de comunicações permite que o usuário personalize o texto usando as opções do editor.</span><span class="sxs-lookup"><span data-stu-id="aebc8-106">The Communications Editor allows user to customize the text using the editor options.</span></span> <span data-ttu-id="aebc8-107">Por exemplo, os usuários podem alterar os tipos de fonte, criar listas com marcadores, destacar conteúdo e muito mais.</span><span class="sxs-lookup"><span data-stu-id="aebc8-107">For example, users can change font types, create bulleted lists, highlight content, and more.</span></span> 

## <a name="merge-field-variables"></a><span data-ttu-id="aebc8-108">Mesclar variáveis de campo</span><span class="sxs-lookup"><span data-stu-id="aebc8-108">Merge field variables</span></span>

<span data-ttu-id="aebc8-109">Você pode aproveitar as variáveis de mala direta por email do editor de comunicações para inserir atributos de responsáveis personalizados no corpo de texto de uma comunicação.</span><span class="sxs-lookup"><span data-stu-id="aebc8-109">You can leverage email merge variables from the Communications Editor to embed customized custodian attributes into a communication's body text.</span></span> <span data-ttu-id="aebc8-110">Quando enviado para os responsáveis, o campo de mesclagem será preenchido com o campo correspondente.</span><span class="sxs-lookup"><span data-stu-id="aebc8-110">When sent to the custodian, the merge field will be populated with the corresponding field.</span></span> <span data-ttu-id="aebc8-111">Por exemplo, quando enviado para os responsáveis John Smith, o campo de mesclagem [nome do responsáveis] seria convertido com o nome correspondente.</span><span class="sxs-lookup"><span data-stu-id="aebc8-111">For example, when sent to custodian John Smith, the merge field [Custodian Name] would be translated with the corresponding name.</span></span> 

<span data-ttu-id="aebc8-112">Você pode usar campos de mala direta por email selecionando os ícones do **campo de mesclagem** na parte superior do controle do editor de Rich Text.</span><span class="sxs-lookup"><span data-stu-id="aebc8-112">You can use email merge fields by selecting the **Merge field** icons on the top of the rich-text editor control.</span></span> <span data-ttu-id="aebc8-113">O espaço reservado será adicionado com base no local do cursor dos usuários.</span><span class="sxs-lookup"><span data-stu-id="aebc8-113">The placeholder will be added based off the location of the users' cursor.</span></span> 

### <a name="list-of-merge-field-variables"></a><span data-ttu-id="aebc8-114">Lista de variáveis de campo de mesclagem</span><span class="sxs-lookup"><span data-stu-id="aebc8-114">List of merge field variables</span></span>

| <span data-ttu-id="aebc8-115">Nome do campo</span><span class="sxs-lookup"><span data-stu-id="aebc8-115">Field name</span></span>                  | <span data-ttu-id="aebc8-116">Detalhes do campo</span><span class="sxs-lookup"><span data-stu-id="aebc8-116">Field details</span></span> | 
| :------------------- | :------------------- |
| <span data-ttu-id="aebc8-117">Nome de exibição</span><span class="sxs-lookup"><span data-stu-id="aebc8-117">Display Name</span></span>  | <span data-ttu-id="aebc8-118">O nome e o sobrenome do responsáveis.</span><span class="sxs-lookup"><span data-stu-id="aebc8-118">The custodian's first and last name.</span></span> | 
| <span data-ttu-id="aebc8-119">Link de confirmação</span><span class="sxs-lookup"><span data-stu-id="aebc8-119">Acknowledgement Link</span></span> | <span data-ttu-id="aebc8-120">Um link personalizado para registrar a confirmação de cada um dos responsáveis.</span><span class="sxs-lookup"><span data-stu-id="aebc8-120">A customized link to record each custodian's acknowledgement.</span></span>|                 |
| <span data-ttu-id="aebc8-121">Link do portal</span><span class="sxs-lookup"><span data-stu-id="aebc8-121">Portal Link</span></span>     | <span data-ttu-id="aebc8-122">Um link personalizado para o portal de conformidade do responsáveis.</span><span class="sxs-lookup"><span data-stu-id="aebc8-122">A customized link for the custodian's Compliance Portal.</span></span>|                |
| <span data-ttu-id="aebc8-123">Responsável pela emissão</span><span class="sxs-lookup"><span data-stu-id="aebc8-123">Issuing Officer</span></span>                   | <span data-ttu-id="aebc8-124">O endereço de email do responsável pela emissão especificado.</span><span class="sxs-lookup"><span data-stu-id="aebc8-124">The email address of the specified issuing officer.</span></span>|                   |
| <span data-ttu-id="aebc8-125">Data de emissão</span><span class="sxs-lookup"><span data-stu-id="aebc8-125">Issuing Date</span></span>                   | <span data-ttu-id="aebc8-126">A data em que o aviso foi emitido (UTC).</span><span class="sxs-lookup"><span data-stu-id="aebc8-126">The date that the notice was issued (UTC).</span></span>              |
