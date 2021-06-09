---
title: Use a Ferramenta de Exportação de Descoberta Microsoft Edge
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Você precisa habilitar ClickOnce suporte para usar a versão mais recente do Microsoft Edge para baixar os resultados da pesquisa de Pesquisa de Conteúdo e Descoberta Digital no centro de segurança e conformidade.
ms.openlocfilehash: 60f42d2884c56aaff40bc0a6a979e99698a3cd2e
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546815"
---
# <a name="use-the-ediscovery-export-tool-in-microsoft-edge"></a><span data-ttu-id="0edc9-103">Use a Ferramenta de Exportação de Descoberta Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="0edc9-103">Use the eDiscovery Export Tool in Microsoft Edge</span></span>

<span data-ttu-id="0edc9-104">Como resultado de alterações recentes na versão mais recente do Microsoft Edge, ClickOnce suporte não está mais habilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="0edc9-104">As a result of recent changes to the newest version of Microsoft Edge, ClickOnce support is no longer enabled by default.</span></span> <span data-ttu-id="0edc9-105">Para continuar usando a Ferramenta de Exportação de Descoberta Digital para baixar os resultados da Pesquisa de Conteúdo ou da Pesquisa de Descoberta ClickOnce, você precisa usar o [Microsoft Internet Explorer](https://support.microsoft.com/help/17621/internet-explorer-downloads) ou habilitar o suporte ClickOnce na versão mais recente do Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="0edc9-105">To continue using the eDiscovery Export Tool to download Content Search or eDiscovery search results, you either need to use [Microsoft Internet Explorer](https://support.microsoft.com/help/17621/internet-explorer-downloads) or enable ClickOnce support in the newest version of Microsoft Edge.</span></span>

## <a name="enable-clickonce-support-in-microsoft-edge"></a><span data-ttu-id="0edc9-106">Habilitar ClickOnce suporte em Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="0edc9-106">Enable ClickOnce support in Microsoft Edge</span></span>

1. <span data-ttu-id="0edc9-107">Em Microsoft Edge, vá para **edge://flags/#edge-click-once**.</span><span class="sxs-lookup"><span data-stu-id="0edc9-107">In Microsoft Edge, go to **edge://flags/#edge-click-once**.</span></span>

2. <span data-ttu-id="0edc9-108">Se o valor existente estiver definido como **Padrão** ou **Desabilitado** na lista de menus suspenso, altere-o para **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="0edc9-108">If the existing value is set to **Default** or **Disabled** in the dropdown list, change it to **Enabled**.</span></span>

   ![Selecionar Habilitado na lista suspenso](../media/ClickOnceimage1.png)

3. <span data-ttu-id="0edc9-110">Role para baixo até a parte inferior da janela do navegador e clique em **Reiniciar** para reiniciar Borda.</span><span class="sxs-lookup"><span data-stu-id="0edc9-110">Scroll down to the bottom of the browser window and click **Restart** to restart Edge.</span></span>

   ![Clique em Reiniciar](../media/ClickOnceimage2.png)

<span data-ttu-id="0edc9-112">**Observação:** As organizações podem usar a Política de Grupo para desabilitar ClickOnce suporte.</span><span class="sxs-lookup"><span data-stu-id="0edc9-112">**Note:** Organizations can use Group Policy to disable ClickOnce support.</span></span> <span data-ttu-id="0edc9-113">Para verificar se há uma política organizacional para suporte ClickOnce, vá para **edge://policy**.</span><span class="sxs-lookup"><span data-stu-id="0edc9-113">To check if there is an organizational policy for ClickOnce support, go to **edge://policy**.</span></span> <span data-ttu-id="0edc9-114">A captura de tela a seguir mostra que ClickOnce está habilitado em toda a organização.</span><span class="sxs-lookup"><span data-stu-id="0edc9-114">The following screenshot shows that ClickOnce is enabled across the entire organization.</span></span> <span data-ttu-id="0edc9-115">Se esse valor de política for definido como **false,** você precisará entrar em contato com um administrador em sua organização.</span><span class="sxs-lookup"><span data-stu-id="0edc9-115">If this policy value is set to **false**, you will need to contact an admin in your organization.</span></span>

![Lista de políticas organizacionais de Borda](../media/ClickOnceimage3.png)

## <a name="install-and-run-the-ediscovery-export-tool"></a><span data-ttu-id="0edc9-117">Instalar e executar a Ferramenta de Exportação de Descoberta Digital</span><span class="sxs-lookup"><span data-stu-id="0edc9-117">Install and run the eDiscovery Export Tool</span></span>

1. <span data-ttu-id="0edc9-118">Clique **em Baixar resultados** na página de sobrevoo de uma exportação na Pesquisa de Conteúdo ou em um caso de Descoberta eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="0edc9-118">Click **Download results** on the flyout page of an export in Content Search or an eDiscovery case.</span></span>

   ![Clique em Baixar resultados na página de sobrevoo para baixar resultados da pesquisa](../media/ClickOnceExport1.png)

2. <span data-ttu-id="0edc9-120">Você será solicitado com uma confirmação para iniciar a ferramenta, Clique em **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="0edc9-120">You will be prompted with a confirmation to launch the tool, Click **Open**.</span></span>

   ![Clique em Abrir para iniciar a Ferramenta de Exportação de Descoberta Digital](../media/ClickOnceimage4.png)

   <span data-ttu-id="0edc9-122">Se a Ferramenta de Exportação de Descoberta Digital não estiver instalada, você será solicitado com um Aviso de Segurança,</span><span class="sxs-lookup"><span data-stu-id="0edc9-122">If the eDiscovery Export Tool isn't installed, you will be prompted with a Security Warning,</span></span> 

   ![Clique em Instalar para instalar a Ferramenta de Exportação de Descoberta Digital](../media/ClickOnceimage5.png)

3. <span data-ttu-id="0edc9-124">Clique em **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="0edc9-124">Click **Install**.</span></span> <span data-ttu-id="0edc9-125">Depois de instalada, a ferramenta de exportação será lançada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="0edc9-125">After it's installed, the export tool will launch automatically.</span></span>

<span data-ttu-id="0edc9-126">Para mais informações, confira os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="0edc9-126">For more information, see the following topics:</span></span>

- [<span data-ttu-id="0edc9-127">Exportar resultados de Pesquisa de Conteúdo</span><span class="sxs-lookup"><span data-stu-id="0edc9-127">Export Content Search results</span></span>](export-search-results.md)

- [<span data-ttu-id="0edc9-128">Como habilitar sinalizadores de experimento em Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="0edc9-128">How to enable experiment flags in Microsoft Edge</span></span>](https://microsoftedgesupport.microsoft.com/hc/articles/360034075294-How-to-enable-experiment-flags-in-Microsoft-Edge-Insider-channels)
