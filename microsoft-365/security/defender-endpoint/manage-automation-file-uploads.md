---
title: Gerenciar uploads de arquivo de automação
description: Habilitar a análise de conteúdo e configurar a extensão de arquivo e as extensões de anexo de email que serão enviadas para análise
keywords: automação, arquivo, carregamentos, conteúdo, análise, arquivo, extensão, email, anexo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: c8935368e4439221f2ce21cfa620e540c02165f8
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185844"
---
# <a name="manage-automation-file-uploads"></a><span data-ttu-id="816be-104">Gerenciar uploads de arquivo de automação</span><span class="sxs-lookup"><span data-stu-id="816be-104">Manage automation file uploads</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="816be-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="816be-105">**Applies to:**</span></span>
- [<span data-ttu-id="816be-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="816be-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="816be-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="816be-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="816be-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="816be-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="816be-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="816be-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-automationefileuploads-abovefoldlink)

<span data-ttu-id="816be-110">Habilita o recurso de análise de conteúdo para que determinados arquivos e anexos de email possam ser carregados automaticamente na nuvem para inspeção adicional na investigação automatizada.</span><span class="sxs-lookup"><span data-stu-id="816be-110">Enable the content analysis capability so that certain files and email attachments can automatically be uploaded to the cloud for additional inspection in Automated investigation.</span></span>

<span data-ttu-id="816be-111">Identifique os arquivos e anexos de email especificando os nomes de extensão de arquivo e nomes de extensão de anexo de email.</span><span class="sxs-lookup"><span data-stu-id="816be-111">Identify the files and email attachments by specifying the file extension names and email attachment extension names.</span></span> 

<span data-ttu-id="816be-112">Por exemplo, se você adicionar *exe* e *bat* como nomes de extensão de arquivo ou anexo, todos os arquivos ou anexos com essas extensões serão enviados automaticamente para a nuvem para inspeção adicional durante a investigação automatizada.</span><span class="sxs-lookup"><span data-stu-id="816be-112">For example, if you add *exe* and *bat* as file or attachment extension names, then all files or attachments with those extensions will automatically be sent to the cloud for additional inspection during Automated investigation.</span></span> 

## <a name="add-file-extension-names-and-attachment-extension-names"></a><span data-ttu-id="816be-113">Adicione nomes de extensão de arquivo e nomes de extensão de anexo.</span><span class="sxs-lookup"><span data-stu-id="816be-113">Add file extension names and attachment extension names.</span></span>

1. <span data-ttu-id="816be-114">No painel de navegação, **selecione** Configurações  >  **de automação carrega**.</span><span class="sxs-lookup"><span data-stu-id="816be-114">In the navigation pane, select **Settings** > **Automation file uploads**.</span></span> 

2. <span data-ttu-id="816be-115">Alterne a configuração de análise de conteúdo **entre On** e **Off**.</span><span class="sxs-lookup"><span data-stu-id="816be-115">Toggle the content analysis setting between **On** and **Off**.</span></span>

3. <span data-ttu-id="816be-116">Configure os seguintes nomes de extensão e nomes de extensão separados com uma vírgula:</span><span class="sxs-lookup"><span data-stu-id="816be-116">Configure the following extension names and separate extension names with a comma:</span></span>
   - <span data-ttu-id="816be-117">**Nomes de extensão de arquivo** - Arquivos suspeitos, exceto anexos de email, serão enviados para inspeção adicional</span><span class="sxs-lookup"><span data-stu-id="816be-117">**File extension names** -  Suspicious files except email attachments will be submitted for additional inspection</span></span>
  

## <a name="related-topics"></a><span data-ttu-id="816be-118">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="816be-118">Related topics</span></span>
- [<span data-ttu-id="816be-119">Gerenciar exclusões de pasta de automação</span><span class="sxs-lookup"><span data-stu-id="816be-119">Manage automation folder exclusions</span></span>](manage-automation-folder-exclusions.md)
