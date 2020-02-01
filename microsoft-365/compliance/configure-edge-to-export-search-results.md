---
title: Usar a ferramenta de exportação de descoberta eletrônica do Office 365 no Microsoft Edge
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ROBOTS: NOINDEX, NOFOLLOW
description: Você precisa habilitar o suporte do ClickOnce para usar o Microsoft Edge para exportar os resultados da pesquisa da pesquisa de conteúdo e da descoberta eletrônica no centro de segurança e conformidade.
ms.openlocfilehash: 896d39d81fa56b3a118b2bee450476e422ac3921
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595728"
---
# <a name="use-the-office-365-ediscovery-export-tool-in-microsoft-edge"></a><span data-ttu-id="dfaed-103">Usar a ferramenta de exportação de descoberta eletrônica do Office 365 no Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="dfaed-103">Use the Office 365 eDiscovery Export Tool in Microsoft Edge</span></span>

<span data-ttu-id="dfaed-104">Como resultado de alterações recentes no Microsoft Edge, o suporte do ClickOnce não está mais habilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="dfaed-104">As a result of recent changes to Microsoft Edge, ClickOnce support is no longer enabled by default.</span></span> <span data-ttu-id="dfaed-105">Para continuar a usar a ferramenta de exportação de descoberta eletrônica do Microsoft Office 365 para baixar os resultados de pesquisa de descoberta eletrônica ou pesquisa de conteúdo, você precisa usar [o Microsoft Internet Explorer](https://support.microsoft.com/help/17621/internet-explorer-downloads) ou habilitar o suporte do ClickOnce no Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="dfaed-105">To continue using the Microsoft Office 365 eDiscovery Export Tool to download Content Search or eDiscovery search results, you either need to use [Microsoft Internet Explorer](https://support.microsoft.com/help/17621/internet-explorer-downloads) or enable ClickOnce support in Microsoft Edge.</span></span>

## <a name="how-to-enable-clickonce-support-in-microsoft-edge"></a><span data-ttu-id="dfaed-106">Como habilitar o suporte do ClickOnce no Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="dfaed-106">How to enable ClickOnce support in Microsoft Edge</span></span>

1. <span data-ttu-id="dfaed-107">No Microsoft Edge, navegue até **edge://flags/#edge-Once**.</span><span class="sxs-lookup"><span data-stu-id="dfaed-107">In Microsoft Edge, navigate to **edge://flags/#edge-click-once**.</span></span>

2. <span data-ttu-id="dfaed-108">Se o valor existente for definido como **padrão** ou **desabilitado** na lista suspensa, altere-o para **habilitado**.</span><span class="sxs-lookup"><span data-stu-id="dfaed-108">If the existing value is set to **Default** or **Disabled** in the dropdown list, change it to **Enabled**.</span></span>
    
   ![](media/ClickOnceimage1.png)

3. <span data-ttu-id="dfaed-109">Role para baixo até a parte inferior da janela do navegador e clique em **reiniciar** para reiniciar a borda.</span><span class="sxs-lookup"><span data-stu-id="dfaed-109">Scroll down to the bottom of the browser window and click **Restart** to restart Edge.</span></span>

   ![](media/ClickOnceimage2.png)

<span data-ttu-id="dfaed-110">**Observação:** As organizações podem usar a política de grupo para desabilitar o suporte do ClickOnce.</span><span class="sxs-lookup"><span data-stu-id="dfaed-110">**Note:** Organizations can use Group Policy to disable ClickOnce support.</span></span> <span data-ttu-id="dfaed-111">Para verificar se há uma política organizacional para o suporte do ClickOnce, navegue até **Edge://Policy**.</span><span class="sxs-lookup"><span data-stu-id="dfaed-111">To check if there is an organizational policy for ClickOnce support, navigate to **edge://policy**.</span></span> <span data-ttu-id="dfaed-112">A captura de tela a seguir mostra que o ClickOnce está habilitado em toda a organização.</span><span class="sxs-lookup"><span data-stu-id="dfaed-112">The following screenshot shows that ClickOnce is enabled across the entire organization.</span></span> <span data-ttu-id="dfaed-113">Se esse valor de política for definido como **false**, você precisará entrar em contato com um administrador na sua organização.</span><span class="sxs-lookup"><span data-stu-id="dfaed-113">If this policy value is set to **false**, you will need to contact an admin in your organization.</span></span>

![](media/ClickOnceimage3.png)

## <a name="install-and-run-the-office-365-ediscovery-export-tool"></a><span data-ttu-id="dfaed-114">Instalar e executar a ferramenta de exportação de descoberta eletrônica do Office 365</span><span class="sxs-lookup"><span data-stu-id="dfaed-114">Install and run the Office 365 eDiscovery Export Tool</span></span>

1. <span data-ttu-id="dfaed-115">Clique em **baixar resultados** na página de menu suspenso de uma exportação na pesquisa de conteúdo ou em um caso de descoberta eletrônica.</span><span class="sxs-lookup"><span data-stu-id="dfaed-115">Click **Download results** on the flyout page of an export in Content Search or an eDiscovery case.</span></span>

   ![Clique em baixar resultados na página do menu de atalho para baixar os resultados da pesquisa](media/ClickOnceExport1.png)

2. <span data-ttu-id="dfaed-117">Você será solicitado a confirmar a inicialização da ferramenta, clique em **abrir**.</span><span class="sxs-lookup"><span data-stu-id="dfaed-117">You will be prompted with a confirmation to launch the tool, Click **Open**.</span></span>

   ![Clique em abrir para iniciar a ferramenta de exportação de descoberta eletrônica](media/ClickOnceimage4.png)

   <span data-ttu-id="dfaed-119">Se a ferramenta de exportação de descoberta eletrônica do Microsoft Office 365 não estiver instalada, você receberá um aviso de segurança</span><span class="sxs-lookup"><span data-stu-id="dfaed-119">If the Microsoft Office 365 eDiscovery Export Tool isn't installed, you will be prompted with a Security Warning,</span></span> 

   ![Clique em instalar para instalar a ferramenta de exportação de descoberta eletrônica](media/ClickOnceimage5.png)

3. <span data-ttu-id="dfaed-121">Clique em **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="dfaed-121">Click **Install**.</span></span> <span data-ttu-id="dfaed-122">Após a instalação, a ferramenta de exportação será iniciada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="dfaed-122">After it's installed, the export tool will launch automatically.</span></span>

<span data-ttu-id="dfaed-123">Para obter mais informações, consulte os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="dfaed-123">For more information, see the following topics:</span></span>

- [<span data-ttu-id="dfaed-124">Exportar resultados de Pesquisa de Conteúdo</span><span class="sxs-lookup"><span data-stu-id="dfaed-124">Export Content Search results</span></span>](export-search-results.md)

- [<span data-ttu-id="dfaed-125">Como habilitar os sinalizadores de experimento no Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="dfaed-125">How to enable experiment flags in Microsoft Edge</span></span>](https://microsoftedgesupport.microsoft.com/hc/articles/360034075294-How-to-enable-experiment-flags-in-Microsoft-Edge-Insider-channels)
