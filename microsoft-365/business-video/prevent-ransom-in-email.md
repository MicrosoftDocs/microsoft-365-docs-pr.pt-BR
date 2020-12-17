---
title: Criar regras de email para ransomware
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
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
description: Saiba como criar regras de email para impedir o ransomware.
ms.openlocfilehash: 85898480438225848fc09db9a9c507045f8a182c
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701420"
---
# <a name="create-email-rules-to-prevent-ransomware"></a><span data-ttu-id="7c2a3-103">Criar regras de email para impedir o ransomware</span><span class="sxs-lookup"><span data-stu-id="7c2a3-103">Create email rules to prevent ransomware</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWrWGt?autoplay=false]

<span data-ttu-id="7c2a3-104">A Microsoft 365 ajuda a proteger sua empresa contra o ransomware, impedindo que arquivos potencialmente perigosos, como JavaScript, lote e executáveis, sejam abertos no Outlook.</span><span class="sxs-lookup"><span data-stu-id="7c2a3-104">Microsoft 365 helps protect your business against ransomware by preventing potentially dangerous files, like JavaScript, batch, and executables, from being opened in Outlook.</span></span> <span data-ttu-id="7c2a3-105">Para aumentar esse nível de proteção adicionando regras que bloqueiem ou avisem sobre tipos adicionais de arquivos, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="7c2a3-105">To increase this level of protection by adding rules that block or warn you of additional types of files, follow these steps.</span></span>

## <a name="try-it"></a><span data-ttu-id="7c2a3-106">Experimente!</span><span class="sxs-lookup"><span data-stu-id="7c2a3-106">Try it!</span></span>

1. <span data-ttu-id="7c2a3-107">No centro de administração [https://admin.microsoft.com](https://admin.microsoft.com) , escolha **Exchange** em **centros de administração**.</span><span class="sxs-lookup"><span data-stu-id="7c2a3-107">From the admin center at [https://admin.microsoft.com](https://admin.microsoft.com), choose **Exchange** under **Admin centers**.</span></span>
1. <span data-ttu-id="7c2a3-108">No menu à esquerda, escolha fluxo de **email**.</span><span class="sxs-lookup"><span data-stu-id="7c2a3-108">From the menu on the left, choose **mail flow**.</span></span>
1. <span data-ttu-id="7c2a3-109">Na guia regras, escolha a seta ao lado do símbolo de adição (+) e, em seguida, escolha **criar uma nova regra**.</span><span class="sxs-lookup"><span data-stu-id="7c2a3-109">On the rules tab, choose the arrow next to the plus (+) symbol, and then choose **Create a new rule**.</span></span>
1. <span data-ttu-id="7c2a3-110">Na página **nova regra** , insira um nome para a regra, role até a parte inferior e, em seguida, escolha **mais opções**.</span><span class="sxs-lookup"><span data-stu-id="7c2a3-110">On the **new rule** page, enter a name for your rule, scroll to the bottom, and then choose **More options**.</span></span>
1. <span data-ttu-id="7c2a3-111">Em **aplicar esta regra se**, selecione **qualquer anexo** e, em seguida, selecione **extensão de arquivo inclui essas palavras**.</span><span class="sxs-lookup"><span data-stu-id="7c2a3-111">Under **Apply this rule if**, select **Any attachment**, and then select **file extension includes these words**.</span></span>
1. <span data-ttu-id="7c2a3-112">Na caixa em **especificar palavras ou frases**, insira as extensões de arquivo às quais você deseja aplicar a regra, como extensões de arquivo que podem conter macros.</span><span class="sxs-lookup"><span data-stu-id="7c2a3-112">In the box under **specify words or phrases**, enter the file extensions that you want the rule to be applied to, such as file extensions that can contain macros.</span></span> <span data-ttu-id="7c2a3-113">Use o símbolo de adição (+) para adicionar um de cada vez.</span><span class="sxs-lookup"><span data-stu-id="7c2a3-113">Use the plus (+) symbol to add them one at a time.</span></span>

    <span data-ttu-id="7c2a3-114">Saiba mais sobre tipos de arquivo lendo [proteger contra ransomware](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/secure-your-business-data#ransomware).</span><span class="sxs-lookup"><span data-stu-id="7c2a3-114">Learn more about file types by reading [Protect against ransomware](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/secure-your-business-data#ransomware).</span></span>

1. <span data-ttu-id="7c2a3-115">Role para baixo para revisar sua lista e, em seguida, escolha **OK**.</span><span class="sxs-lookup"><span data-stu-id="7c2a3-115">Scroll down to review your list, and then choose **OK**.</span></span>
1. <span data-ttu-id="7c2a3-116">Na página **nova regra** , escolha **Adicionar condição** e, em seguida, escolha uma condição em **faça o seguinte**.</span><span class="sxs-lookup"><span data-stu-id="7c2a3-116">On the **new rule** page, choose **add condition**, and then choose a condition under **Do the following**.</span></span>
1. <span data-ttu-id="7c2a3-117">Você tem muitas opções de regra para escolher, mas neste exemplo, vamos optar por **notificar o destinatário com uma mensagem**.</span><span class="sxs-lookup"><span data-stu-id="7c2a3-117">You have many rule options to choose from, but in this example we'll choose to **Notify the recipient with a message**.</span></span>
1. <span data-ttu-id="7c2a3-118">Insira o texto da mensagem para sua notificação e, em seguida, escolha **OK**.</span><span class="sxs-lookup"><span data-stu-id="7c2a3-118">Enter message text for your notification, and then chose **OK**.</span></span>
1. <span data-ttu-id="7c2a3-119">Opcional: na página **nova regra** , escolha **Adicionar exceção** e insira os detalhes para exceções à regra, como mensagens de remetentes confiáveis.</span><span class="sxs-lookup"><span data-stu-id="7c2a3-119">Optional: On the **new rule** page, choose **add exception**, and enter any details for exceptions to your rule, such as messages from trusted senders.</span></span>
1. <span data-ttu-id="7c2a3-120">Na página nova regra, escolha **salvar** e revise as informações de resumo da regra fornecidas.</span><span class="sxs-lookup"><span data-stu-id="7c2a3-120">On the new rule page, choose **Save**, and review the rule summary information provided.</span></span>