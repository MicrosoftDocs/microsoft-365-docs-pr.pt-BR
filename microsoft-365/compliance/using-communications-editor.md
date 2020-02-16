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
description: ''
ms.openlocfilehash: 2f445e4449fb20f0d13d857bb83d3dc85d7b7387
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42069198"
---
# <a name="use-the-communications-editor"></a><span data-ttu-id="3392d-102">Usar o editor de comunicações</span><span class="sxs-lookup"><span data-stu-id="3392d-102">Use the communications editor</span></span>

<span data-ttu-id="3392d-103">À medida que você define o conteúdo do seu conteúdo de portal, as notificações de retenção legal e lembretes/rementeções relacionados, você pode aproveitar o editor de comunicações para formatar e personalizar dinamicamente o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="3392d-103">As you define the content of your portal content, legal hold notifications, and related reminders/escalations, you can leverage the Communications Editor to format and dynamically customize your content.</span></span>

## <a name="rich-text-editor"></a><span data-ttu-id="3392d-104">Editor de Rich Text</span><span class="sxs-lookup"><span data-stu-id="3392d-104">Rich text editor</span></span> 

<span data-ttu-id="3392d-105">O editor de comunicações permite que o usuário personalize o texto usando as opções do editor.</span><span class="sxs-lookup"><span data-stu-id="3392d-105">The Communications Editor allows user to customize the text using the editor options.</span></span> <span data-ttu-id="3392d-106">Por exemplo, os usuários podem alterar os tipos de fonte, criar listas com marcadores, destacar conteúdo e muito mais.</span><span class="sxs-lookup"><span data-stu-id="3392d-106">For example, users can change font types, create bulleted lists, highlight content, and more.</span></span> 

## <a name="merge-field-variables"></a><span data-ttu-id="3392d-107">Mesclar variáveis de campo</span><span class="sxs-lookup"><span data-stu-id="3392d-107">Merge field variables</span></span>

<span data-ttu-id="3392d-108">Você pode aproveitar as variáveis de mala direta por email do editor de comunicações para inserir atributos de responsáveis personalizados no corpo de texto de uma comunicação.</span><span class="sxs-lookup"><span data-stu-id="3392d-108">You can leverage email merge variables from the Communications Editor to embed customized custodian attributes into a communication's body text.</span></span> <span data-ttu-id="3392d-109">Quando enviado para os responsáveis, o campo de mesclagem será preenchido com o campo correspondente.</span><span class="sxs-lookup"><span data-stu-id="3392d-109">When sent to the custodian, the merge field will be populated with the corresponding field.</span></span> <span data-ttu-id="3392d-110">Por exemplo, quando enviado para os responsáveis John Smith, o campo de mesclagem [nome do responsáveis] seria convertido com o nome correspondente.</span><span class="sxs-lookup"><span data-stu-id="3392d-110">For example, when sent to custodian John Smith, the merge field [Custodian Name] would be translated with the corresponding name.</span></span> 

<span data-ttu-id="3392d-111">Você pode usar campos de mala direta por email selecionando os ícones do **campo de mesclagem** na parte superior do controle do editor de Rich Text.</span><span class="sxs-lookup"><span data-stu-id="3392d-111">You can use email merge fields by selecting the **Merge field** icons on the top of the rich-text editor control.</span></span> <span data-ttu-id="3392d-112">O espaço reservado será adicionado com base no local do cursor dos usuários.</span><span class="sxs-lookup"><span data-stu-id="3392d-112">The placeholder will be added based off the location of the users' cursor.</span></span> 

### <a name="list-of-merge-field-variables"></a><span data-ttu-id="3392d-113">Lista de variáveis de campo de mesclagem</span><span class="sxs-lookup"><span data-stu-id="3392d-113">List of merge field variables</span></span>

| <span data-ttu-id="3392d-114">Nome do campo</span><span class="sxs-lookup"><span data-stu-id="3392d-114">Field name</span></span>                  | <span data-ttu-id="3392d-115">Detalhes do campo</span><span class="sxs-lookup"><span data-stu-id="3392d-115">Field details</span></span> | 
| :------------------- | :------------------- |
| <span data-ttu-id="3392d-116">Nome de exibição</span><span class="sxs-lookup"><span data-stu-id="3392d-116">Display Name</span></span>  | <span data-ttu-id="3392d-117">O nome e o sobrenome do responsáveis.</span><span class="sxs-lookup"><span data-stu-id="3392d-117">The custodian's first and last name.</span></span> | 
| <span data-ttu-id="3392d-118">Link de confirmação</span><span class="sxs-lookup"><span data-stu-id="3392d-118">Acknowledgement Link</span></span> | <span data-ttu-id="3392d-119">Um link personalizado para registrar a confirmação de cada um dos responsáveis.</span><span class="sxs-lookup"><span data-stu-id="3392d-119">A customized link to record each custodian's acknowledgement.</span></span>|                 |
| <span data-ttu-id="3392d-120">Link do portal</span><span class="sxs-lookup"><span data-stu-id="3392d-120">Portal Link</span></span>     | <span data-ttu-id="3392d-121">Um link personalizado para o portal de conformidade do responsáveis.</span><span class="sxs-lookup"><span data-stu-id="3392d-121">A customized link for the custodian's Compliance Portal.</span></span>|                |
| <span data-ttu-id="3392d-122">Responsável pela emissão</span><span class="sxs-lookup"><span data-stu-id="3392d-122">Issuing Officer</span></span>                   | <span data-ttu-id="3392d-123">O endereço de email do responsável pela emissão especificado.</span><span class="sxs-lookup"><span data-stu-id="3392d-123">The email address of the specified issuing officer.</span></span>|                   |
| <span data-ttu-id="3392d-124">Data de emissão</span><span class="sxs-lookup"><span data-stu-id="3392d-124">Issuing Date</span></span>                   | <span data-ttu-id="3392d-125">A data em que o aviso foi emitido (UTC).</span><span class="sxs-lookup"><span data-stu-id="3392d-125">The date that the notice was issued (UTC).</span></span>              |
