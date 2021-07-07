---
title: Upload Binários de aplicativo
description: Como começar a usar a Base de Teste para M365
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: 1c4ff6ac03989cc9be70e18a1b8634f2da11e721
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322472"
---
# <a name="step-3-upload-your-binaries-dependencies-and-scripts"></a>Etapa 3: Upload binários, dependências e scripts

Nesta guia, você carregará um único pacote zip contendo seus binários, dependências e scripts usados para executar seu pacote de teste.

## <a name="upload-package-zip-file"></a>Upload arquivo zip do pacote

![Upload binários](Media/AddBinaries.png)

  - As dependências carregadas podem incluir estruturas de teste, mecanismos de script ou dados que serão acessados para executar seu aplicativo ou casos de teste. Por exemplo, você pode carregar Selenium e um instalador webdriver para ajudar a executar testes baseados no navegador.
  - É prática prática garantir que suas atividades de script sejam mantidas modulares ou seja. 
    - O ```Install``` script executa apenas operações de instalação.
    - O ```Launch``` script só inicia o aplicativo.
    - O ```Close``` script apenas fecha o aplicativo.
    - O ```Uninstall``` script opcional apenas desinstala o aplicativo.

**Atualmente, o portal só dá suporte a scripts do PowerShell.**


## <a name="next-steps"></a>Próximas etapas 

Avance para o próximo artigo para ir para a Etapa 4: **Definir suas Tarefas de Teste**.
> [!div class="nextstepaction"]
> [Voltar](uploadApplication.md)
> [!div class="nextstepaction"]
> [Próxima etapa](testtask.md)

