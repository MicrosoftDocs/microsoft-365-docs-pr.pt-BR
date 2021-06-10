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
# <a name="manage-automation-file-uploads"></a>Gerenciar uploads de arquivo de automação

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-automationefileuploads-abovefoldlink)

Habilita o recurso de análise de conteúdo para que determinados arquivos e anexos de email possam ser carregados automaticamente na nuvem para inspeção adicional na investigação automatizada.

Identifique os arquivos e anexos de email especificando os nomes de extensão de arquivo e nomes de extensão de anexo de email. 

Por exemplo, se você adicionar *exe* e *bat* como nomes de extensão de arquivo ou anexo, todos os arquivos ou anexos com essas extensões serão enviados automaticamente para a nuvem para inspeção adicional durante a investigação automatizada. 

## <a name="add-file-extension-names-and-attachment-extension-names"></a>Adicione nomes de extensão de arquivo e nomes de extensão de anexo.

1. No painel de navegação, **selecione** Configurações  >  **de automação carrega**. 

2. Alterne a configuração de análise de conteúdo **entre On** e **Off**.

3. Configure os seguintes nomes de extensão e nomes de extensão separados com uma vírgula:
   - **Nomes de extensão de arquivo** - Arquivos suspeitos, exceto anexos de email, serão enviados para inspeção adicional
  

## <a name="related-topics"></a>Tópicos relacionados
- [Gerenciar exclusões de pasta de automação](manage-automation-folder-exclusions.md)
