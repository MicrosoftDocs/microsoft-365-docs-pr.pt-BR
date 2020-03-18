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
description: Você precisa habilitar o suporte do ClickOnce para usar a versão mais recente do Microsoft Edge para baixar os resultados da pesquisa da pesquisa de conteúdo e da descoberta eletrônica no centro de segurança e conformidade.
ms.openlocfilehash: 80924b124521b24ffabf1e0273802265cd715500
ms.sourcegitcommit: 01ead889086ecc7dcf5d10244bcf67c5a33c8114
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/17/2020
ms.locfileid: "42710340"
---
# <a name="use-the-office-365-ediscovery-export-tool-in-microsoft-edge"></a><span data-ttu-id="aad98-103">Usar a ferramenta de exportação de descoberta eletrônica do Office 365 no Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="aad98-103">Use the Office 365 eDiscovery Export Tool in Microsoft Edge</span></span>

<span data-ttu-id="aad98-104">Como resultado de alterações recentes na versão mais recente do Microsoft Edge, o suporte do ClickOnce não está mais habilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="aad98-104">As a result of recent changes to the newest version of Microsoft Edge, ClickOnce support is no longer enabled by default.</span></span> <span data-ttu-id="aad98-105">Para continuar a usar a ferramenta de exportação de descoberta eletrônica do Microsoft Office 365 para baixar os resultados de pesquisa de descoberta eletrônica ou pesquisa de conteúdo, você precisa usar o [Microsoft Internet Explorer](https://support.microsoft.com/help/17621/internet-explorer-downloads) ou habilitar o suporte do ClickOnce na versão mais recente do Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="aad98-105">To continue using the Microsoft Office 365 eDiscovery Export Tool to download Content Search or eDiscovery search results, you either need to use [Microsoft Internet Explorer](https://support.microsoft.com/help/17621/internet-explorer-downloads) or enable ClickOnce support in the newest version of Microsoft Edge.</span></span>

## <a name="enable-clickonce-support-in-microsoft-edge"></a><span data-ttu-id="aad98-106">Habilitar o suporte do ClickOnce no Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="aad98-106">Enable ClickOnce support in Microsoft Edge</span></span>

1. <span data-ttu-id="aad98-107">No Microsoft Edge, vá para **edge://flags/#edge-Click-Once**.</span><span class="sxs-lookup"><span data-stu-id="aad98-107">In Microsoft Edge, go to **edge://flags/#edge-click-once**.</span></span>

2. <span data-ttu-id="aad98-108">Se o valor existente for definido como **padrão** ou **desabilitado** na lista suspensa, altere-o para **habilitado**.</span><span class="sxs-lookup"><span data-stu-id="aad98-108">If the existing value is set to **Default** or **Disabled** in the dropdown list, change it to **Enabled**.</span></span>

   ![](../media/ClickOnceimage1.png)

3. <span data-ttu-id="aad98-109">Role para baixo até a parte inferior da janela do navegador e clique em **reiniciar** para reiniciar a borda.</span><span class="sxs-lookup"><span data-stu-id="aad98-109">Scroll down to the bottom of the browser window and click **Restart** to restart Edge.</span></span>

   ![](../media/ClickOnceimage2.png)

<span data-ttu-id="aad98-110">**Observação:** As organizações podem usar a política de grupo para desabilitar o suporte do ClickOnce.</span><span class="sxs-lookup"><span data-stu-id="aad98-110">**Note:** Organizations can use Group Policy to disable ClickOnce support.</span></span> <span data-ttu-id="aad98-111">Para verificar se há uma política organizacional para o suporte do ClickOnce, acesse **Edge://Policy**.</span><span class="sxs-lookup"><span data-stu-id="aad98-111">To check if there is an organizational policy for ClickOnce support, go to **edge://policy**.</span></span> <span data-ttu-id="aad98-112">A captura de tela a seguir mostra que o ClickOnce está habilitado em toda a organização.</span><span class="sxs-lookup"><span data-stu-id="aad98-112">The following screenshot shows that ClickOnce is enabled across the entire organization.</span></span> <span data-ttu-id="aad98-113">Se esse valor de política for definido como **false**, você precisará entrar em contato com um administrador na sua organização.</span><span class="sxs-lookup"><span data-stu-id="aad98-113">If this policy value is set to **false**, you will need to contact an admin in your organization.</span></span>

![](../media/ClickOnceimage3.png)

## <a name="install-and-run-the-ediscovery-export-tool"></a><span data-ttu-id="aad98-114">Instalar e executar a ferramenta de exportação de descoberta eletrônica</span><span class="sxs-lookup"><span data-stu-id="aad98-114">Install and run the eDiscovery Export Tool</span></span>

1. <span data-ttu-id="aad98-115">Clique em **baixar resultados** na página de menu suspenso de uma exportação na pesquisa de conteúdo ou em um caso de descoberta eletrônica.</span><span class="sxs-lookup"><span data-stu-id="aad98-115">Click **Download results** on the flyout page of an export in Content Search or an eDiscovery case.</span></span>

   ![Clique em baixar resultados na página do menu de atalho para baixar os resultados da pesquisa](../media/ClickOnceExport1.png)

2. <span data-ttu-id="aad98-117">Você será solicitado a confirmar a inicialização da ferramenta, clique em **abrir**.</span><span class="sxs-lookup"><span data-stu-id="aad98-117">You will be prompted with a confirmation to launch the tool, Click **Open**.</span></span>

   ![Clique em abrir para iniciar a ferramenta de exportação de descoberta eletrônica](../media/ClickOnceimage4.png)

   <span data-ttu-id="aad98-119">Se a ferramenta de exportação de descoberta eletrônica do Microsoft Office 365 não estiver instalada, você receberá um aviso de segurança</span><span class="sxs-lookup"><span data-stu-id="aad98-119">If the Microsoft Office 365 eDiscovery Export Tool isn't installed, you will be prompted with a Security Warning,</span></span> 

   ![Clique em instalar para instalar a ferramenta de exportação de descoberta eletrônica](../media/ClickOnceimage5.png)

3. <span data-ttu-id="aad98-121">Clique em **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="aad98-121">Click **Install**.</span></span> <span data-ttu-id="aad98-122">Após a instalação, a ferramenta de exportação será iniciada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="aad98-122">After it's installed, the export tool will launch automatically.</span></span>

<span data-ttu-id="aad98-123">Para mais informações, confira os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="aad98-123">For more information, see the following topics:</span></span>

- [<span data-ttu-id="aad98-124">Exportar resultados de Pesquisa de Conteúdo</span><span class="sxs-lookup"><span data-stu-id="aad98-124">Export Content Search results</span></span>](export-search-results.md)

- [<span data-ttu-id="aad98-125">Como habilitar os sinalizadores de experimento no Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="aad98-125">How to enable experiment flags in Microsoft Edge</span></span>](https://microsoftedgesupport.microsoft.com/hc/articles/360034075294-How-to-enable-experiment-flags-in-Microsoft-Edge-Insider-channels)
