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
description: Use o Editor de Comunicações para alterar variáveis de campo de texto e mesclagem ao formatar o conteúdo.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6dcfb58dff3a3acf99340895872bb2da9795d9c8
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769156"
---
# <a name="use-the-communications-editor"></a><span data-ttu-id="c93da-103">Usar o editor de comunicações</span><span class="sxs-lookup"><span data-stu-id="c93da-103">Use the communications editor</span></span>

<span data-ttu-id="c93da-104">À medida que você define o conteúdo do conteúdo do portal, as notificações de responsabilidade legal e os lembretes/escalonamentos relacionados, você pode usar o Editor de Comunicações para formatar e personalizar dinamicamente o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="c93da-104">As you define the content of your portal content, legal hold notifications, and related reminders/escalations, you can use the Communications Editor to format and dynamically customize your content.</span></span>

## <a name="rich-text-editor"></a><span data-ttu-id="c93da-105">Editor de rich text</span><span class="sxs-lookup"><span data-stu-id="c93da-105">Rich text editor</span></span>

<span data-ttu-id="c93da-106">O Editor de Comunicações permite que o usuário personalize o texto usando as opções do editor.</span><span class="sxs-lookup"><span data-stu-id="c93da-106">The Communications Editor allows user to customize the text using the editor options.</span></span> <span data-ttu-id="c93da-107">Por exemplo, os usuários podem alterar tipos de fonte, criar listas com marcador, realçar o conteúdo e muito mais.</span><span class="sxs-lookup"><span data-stu-id="c93da-107">For example, users can change font types, create bulleted lists, highlight content, and more.</span></span>

## <a name="merge-field-variables"></a><span data-ttu-id="c93da-108">Mesclar variáveis de campo</span><span class="sxs-lookup"><span data-stu-id="c93da-108">Merge field variables</span></span>

<span data-ttu-id="c93da-109">Você pode usar variáveis de mala direta de email do Editor de Comunicações para incorporar atributos custodiantes personalizados no corpo do texto de uma comunicação.</span><span class="sxs-lookup"><span data-stu-id="c93da-109">You can use email merge variables from the Communications Editor to embed customized custodian attributes into a communication's body text.</span></span> <span data-ttu-id="c93da-110">Quando enviado para o custodiante, o campo de mesclagem será preenchido com o campo correspondente.</span><span class="sxs-lookup"><span data-stu-id="c93da-110">When sent to the custodian, the merge field will be populated with the corresponding field.</span></span> <span data-ttu-id="c93da-111">Por exemplo, quando enviado para o custodiante John Smith, o campo de mesclagem [Nome custodiante] seria traduzido com o nome correspondente.</span><span class="sxs-lookup"><span data-stu-id="c93da-111">For example, when sent to custodian John Smith, the merge field [Custodian Name] would be translated with the corresponding name.</span></span>

<span data-ttu-id="c93da-112">Você pode usar campos de mala direta selecionando **os** ícones do campo Mesclar na parte superior do controle do editor de rich text.</span><span class="sxs-lookup"><span data-stu-id="c93da-112">You can use email merge fields by selecting the **Merge field** icons on the top of the rich-text editor control.</span></span> <span data-ttu-id="c93da-113">O espaço reservado será adicionado com base no local do cursor do usuário.</span><span class="sxs-lookup"><span data-stu-id="c93da-113">The placeholder will be added based off the location of the users' cursor.</span></span>

### <a name="list-of-merge-field-variables"></a><span data-ttu-id="c93da-114">Lista de variáveis de campo de mesclagem</span><span class="sxs-lookup"><span data-stu-id="c93da-114">List of merge field variables</span></span>

| <span data-ttu-id="c93da-115">Nome do campo</span><span class="sxs-lookup"><span data-stu-id="c93da-115">Field name</span></span>                  | <span data-ttu-id="c93da-116">Detalhes do campo</span><span class="sxs-lookup"><span data-stu-id="c93da-116">Field details</span></span> |
| :------------------- | :------------------- |
| <span data-ttu-id="c93da-117">Nome de exibição</span><span class="sxs-lookup"><span data-stu-id="c93da-117">Display Name</span></span>  | <span data-ttu-id="c93da-118">O nome e o sobrenome do custodiatário.</span><span class="sxs-lookup"><span data-stu-id="c93da-118">The custodian's first and last name.</span></span> | 
| <span data-ttu-id="c93da-119">Link de confirmação</span><span class="sxs-lookup"><span data-stu-id="c93da-119">Acknowledgment Link</span></span> | <span data-ttu-id="c93da-120">Um link personalizado para registrar a confirmação de cada custodiado.</span><span class="sxs-lookup"><span data-stu-id="c93da-120">A customized link to record each custodian's acknowledgment.</span></span>|                 |
| <span data-ttu-id="c93da-121">Portal Link</span><span class="sxs-lookup"><span data-stu-id="c93da-121">Portal Link</span></span>     | <span data-ttu-id="c93da-122">Um link personalizado para o Portal de Conformidade do custodiatário.</span><span class="sxs-lookup"><span data-stu-id="c93da-122">A customized link for the custodian's Compliance Portal.</span></span>|                |
| <span data-ttu-id="c93da-123">Diretor de emissão</span><span class="sxs-lookup"><span data-stu-id="c93da-123">Issuing Officer</span></span>                   | <span data-ttu-id="c93da-124">O endereço de email do responsável pela emissão especificado.</span><span class="sxs-lookup"><span data-stu-id="c93da-124">The email address of the specified issuing officer.</span></span>|                   |
| <span data-ttu-id="c93da-125">Data de emissão</span><span class="sxs-lookup"><span data-stu-id="c93da-125">Issuing Date</span></span>                   | <span data-ttu-id="c93da-126">A data em que o aviso foi emitido (UTC).</span><span class="sxs-lookup"><span data-stu-id="c93da-126">The date that the notice was issued (UTC).</span></span>              |
|||
