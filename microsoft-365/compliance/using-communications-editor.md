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
description: Use o Editor de Comunicações para alterar o texto e mesclar variáveis de campo ao formatar seu conteúdo.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6dcfb58dff3a3acf99340895872bb2da9795d9c8
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769156"
---
# <a name="use-the-communications-editor"></a><span data-ttu-id="56794-103">Usar o editor de comunicações</span><span class="sxs-lookup"><span data-stu-id="56794-103">Use the communications editor</span></span>

<span data-ttu-id="56794-104">À medida que você define o conteúdo do seu conteúdo de portal, notificações de responsabilidade legal e lembretes/escalações relacionados, você pode usar o Editor de Comunicações para formatar e personalizar dinamicamente seu conteúdo.</span><span class="sxs-lookup"><span data-stu-id="56794-104">As you define the content of your portal content, legal hold notifications, and related reminders/escalations, you can use the Communications Editor to format and dynamically customize your content.</span></span>

## <a name="rich-text-editor"></a><span data-ttu-id="56794-105">Editor de texto rich</span><span class="sxs-lookup"><span data-stu-id="56794-105">Rich text editor</span></span>

<span data-ttu-id="56794-106">O Editor de Comunicações permite que o usuário personalize o texto usando as opções do editor.</span><span class="sxs-lookup"><span data-stu-id="56794-106">The Communications Editor allows user to customize the text using the editor options.</span></span> <span data-ttu-id="56794-107">Por exemplo, os usuários podem alterar tipos de fonte, criar listas com marcador, realçar conteúdo e muito mais.</span><span class="sxs-lookup"><span data-stu-id="56794-107">For example, users can change font types, create bulleted lists, highlight content, and more.</span></span>

## <a name="merge-field-variables"></a><span data-ttu-id="56794-108">Mesclar variáveis de campo</span><span class="sxs-lookup"><span data-stu-id="56794-108">Merge field variables</span></span>

<span data-ttu-id="56794-109">Você pode usar variáveis de mesclagem de email do Editor de Comunicações para incorporar atributos de custodiante personalizados no texto do corpo de uma comunicação.</span><span class="sxs-lookup"><span data-stu-id="56794-109">You can use email merge variables from the Communications Editor to embed customized custodian attributes into a communication's body text.</span></span> <span data-ttu-id="56794-110">Quando enviado para o custodiante, o campo de mesclagem será preenchido com o campo correspondente.</span><span class="sxs-lookup"><span data-stu-id="56794-110">When sent to the custodian, the merge field will be populated with the corresponding field.</span></span> <span data-ttu-id="56794-111">Por exemplo, quando enviado para o custodiante John Smith, o campo de mesclagem [Nome da Custodiação] seria convertido com o nome correspondente.</span><span class="sxs-lookup"><span data-stu-id="56794-111">For example, when sent to custodian John Smith, the merge field [Custodian Name] would be translated with the corresponding name.</span></span>

<span data-ttu-id="56794-112">Você pode usar campos de mala direta selecionando os ícones do campo **Mesclar** na parte superior do controle editor de rich-text.</span><span class="sxs-lookup"><span data-stu-id="56794-112">You can use email merge fields by selecting the **Merge field** icons on the top of the rich-text editor control.</span></span> <span data-ttu-id="56794-113">O espaço reservado será adicionado com base no local do cursor dos usuários.</span><span class="sxs-lookup"><span data-stu-id="56794-113">The placeholder will be added based off the location of the users' cursor.</span></span>

### <a name="list-of-merge-field-variables"></a><span data-ttu-id="56794-114">Lista de variáveis de campo de mesclagem</span><span class="sxs-lookup"><span data-stu-id="56794-114">List of merge field variables</span></span>

| <span data-ttu-id="56794-115">Nome do campo</span><span class="sxs-lookup"><span data-stu-id="56794-115">Field name</span></span>                  | <span data-ttu-id="56794-116">Detalhes de campo</span><span class="sxs-lookup"><span data-stu-id="56794-116">Field details</span></span> |
| :------------------- | :------------------- |
| <span data-ttu-id="56794-117">Nome de exibição</span><span class="sxs-lookup"><span data-stu-id="56794-117">Display Name</span></span>  | <span data-ttu-id="56794-118">O nome e o sobrenome do custodiado.</span><span class="sxs-lookup"><span data-stu-id="56794-118">The custodian's first and last name.</span></span> | 
| <span data-ttu-id="56794-119">Link de Confirmação</span><span class="sxs-lookup"><span data-stu-id="56794-119">Acknowledgment Link</span></span> | <span data-ttu-id="56794-120">Um link personalizado para registrar o reconhecimento de cada custodiado.</span><span class="sxs-lookup"><span data-stu-id="56794-120">A customized link to record each custodian's acknowledgment.</span></span>|                 |
| <span data-ttu-id="56794-121">Portal Link</span><span class="sxs-lookup"><span data-stu-id="56794-121">Portal Link</span></span>     | <span data-ttu-id="56794-122">Um link personalizado para o Portal de Conformidade do custodiado.</span><span class="sxs-lookup"><span data-stu-id="56794-122">A customized link for the custodian's Compliance Portal.</span></span>|                |
| <span data-ttu-id="56794-123">Diretor de emissão</span><span class="sxs-lookup"><span data-stu-id="56794-123">Issuing Officer</span></span>                   | <span data-ttu-id="56794-124">O endereço de email do oficial de emissão especificado.</span><span class="sxs-lookup"><span data-stu-id="56794-124">The email address of the specified issuing officer.</span></span>|                   |
| <span data-ttu-id="56794-125">Data de emissão</span><span class="sxs-lookup"><span data-stu-id="56794-125">Issuing Date</span></span>                   | <span data-ttu-id="56794-126">A data em que o aviso foi emitido (UTC).</span><span class="sxs-lookup"><span data-stu-id="56794-126">The date that the notice was issued (UTC).</span></span>              |
|||
