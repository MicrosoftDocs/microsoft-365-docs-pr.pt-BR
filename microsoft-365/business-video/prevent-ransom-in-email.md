---
title: Criar regras de e-mail para ransomware
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Saiba como criar regras de email para evitar ransomware.
ms.openlocfilehash: 96822916753f2f70d481c213e7e31046f7081446
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580493"
---
# <a name="create-email-rules-to-prevent-ransomware"></a><span data-ttu-id="7e4b7-103">Criar regras de email para evitar ransomware</span><span class="sxs-lookup"><span data-stu-id="7e4b7-103">Create email rules to prevent ransomware</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWrWGt?autoplay=false]

<span data-ttu-id="7e4b7-104">O Microsoft 365 ajuda a proteger sua empresa contra ransomware, impedindo que arquivos potencialmente perigosos, como JavaScript, lote e executáveis, seja aberto no Outlook.</span><span class="sxs-lookup"><span data-stu-id="7e4b7-104">Microsoft 365 helps protect your business against ransomware by preventing potentially dangerous files, like JavaScript, batch, and executables, from being opened in Outlook.</span></span> <span data-ttu-id="7e4b7-105">Para aumentar esse nível de proteção adicionando regras que bloqueiam ou avisam sobre tipos adicionais de arquivos, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="7e4b7-105">To increase this level of protection by adding rules that block or warn you of additional types of files, follow these steps.</span></span>

## <a name="try-it"></a><span data-ttu-id="7e4b7-106">Experimente!</span><span class="sxs-lookup"><span data-stu-id="7e4b7-106">Try it!</span></span>

1. <span data-ttu-id="7e4b7-107">No centro de administração em [https://admin.microsoft.com](https://admin.microsoft.com) , escolha **Exchange** em Centros **de administração**.</span><span class="sxs-lookup"><span data-stu-id="7e4b7-107">From the admin center at [https://admin.microsoft.com](https://admin.microsoft.com), choose **Exchange** under **Admin centers**.</span></span>
1. <span data-ttu-id="7e4b7-108">No menu à esquerda, escolha **fluxo de emails**.</span><span class="sxs-lookup"><span data-stu-id="7e4b7-108">From the menu on the left, choose **mail flow**.</span></span>
1. <span data-ttu-id="7e4b7-109">Na guia regras, escolha a seta ao lado do símbolo de mais (+) e escolha **Criar uma nova regra**.</span><span class="sxs-lookup"><span data-stu-id="7e4b7-109">On the rules tab, choose the arrow next to the plus (+) symbol, and then choose **Create a new rule**.</span></span>
1. <span data-ttu-id="7e4b7-110">Na nova **página de** regra, insira um nome para sua regra, role até a parte inferior e escolha **Mais opções**.</span><span class="sxs-lookup"><span data-stu-id="7e4b7-110">On the **new rule** page, enter a name for your rule, scroll to the bottom, and then choose **More options**.</span></span>
1. <span data-ttu-id="7e4b7-111">Em **Aplicar esta regra se**, selecione Qualquer **anexo** e selecione extensão de arquivo inclui **essas palavras**.</span><span class="sxs-lookup"><span data-stu-id="7e4b7-111">Under **Apply this rule if**, select **Any attachment**, and then select **file extension includes these words**.</span></span>
1. <span data-ttu-id="7e4b7-112">Na caixa em especificar palavras ou **frases,** insira as extensões de arquivo às quais você deseja que a regra seja aplicada, como extensões de arquivo que podem conter macros.</span><span class="sxs-lookup"><span data-stu-id="7e4b7-112">In the box under **specify words or phrases**, enter the file extensions that you want the rule to be applied to, such as file extensions that can contain macros.</span></span> <span data-ttu-id="7e4b7-113">Use o símbolo plus (+) para adicioná-los um por vez.</span><span class="sxs-lookup"><span data-stu-id="7e4b7-113">Use the plus (+) symbol to add them one at a time.</span></span>

    <span data-ttu-id="7e4b7-114">Saiba mais sobre tipos de arquivo lendo [Proteger contra ransomware](../admin/security-and-compliance/secure-your-business-data.md#ransomware).</span><span class="sxs-lookup"><span data-stu-id="7e4b7-114">Learn more about file types by reading [Protect against ransomware](../admin/security-and-compliance/secure-your-business-data.md#ransomware).</span></span>

1. <span data-ttu-id="7e4b7-115">Role para baixo para revisar sua lista e escolha **OK**.</span><span class="sxs-lookup"><span data-stu-id="7e4b7-115">Scroll down to review your list, and then choose **OK**.</span></span>
1. <span data-ttu-id="7e4b7-116">Na nova **página de** regra, escolha **adicionar condição** e escolha uma condição em Fazer **o seguinte.**</span><span class="sxs-lookup"><span data-stu-id="7e4b7-116">On the **new rule** page, choose **add condition**, and then choose a condition under **Do the following**.</span></span>
1. <span data-ttu-id="7e4b7-117">Você tem muitas opções de regra para escolher, mas neste exemplo, optaremos por **Notificar** o destinatário com uma mensagem .</span><span class="sxs-lookup"><span data-stu-id="7e4b7-117">You have many rule options to choose from, but in this example we'll choose to **Notify the recipient with a message**.</span></span>
1. <span data-ttu-id="7e4b7-118">Insira o texto da mensagem para sua notificação e escolha **OK**.</span><span class="sxs-lookup"><span data-stu-id="7e4b7-118">Enter message text for your notification, and then chose **OK**.</span></span>
1. <span data-ttu-id="7e4b7-119">Opcional: na nova página **de** regra, escolha **adicionar** exceção e insira qualquer detalhe para exceções à sua regra, como mensagens de senders confiáveis.</span><span class="sxs-lookup"><span data-stu-id="7e4b7-119">Optional: On the **new rule** page, choose **add exception**, and enter any details for exceptions to your rule, such as messages from trusted senders.</span></span>
1. <span data-ttu-id="7e4b7-120">Na nova página de regra, escolha **Salvar** e revise as informações de resumo de regras fornecidas.</span><span class="sxs-lookup"><span data-stu-id="7e4b7-120">On the new rule page, choose **Save**, and review the rule summary information provided.</span></span>