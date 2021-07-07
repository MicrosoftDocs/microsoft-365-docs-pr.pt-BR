---
title: Definir suas tarefas de teste
description: Definir suas tarefas de teste
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
ms.openlocfilehash: 64abb5b10e3dc1d52b6baf8ceccd5aff2baacefe
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322433"
---
# <a name="step-4-the-tasks-tab"></a>Etapa 4: a guia Tarefas

Na guia tarefas, você deve fornecer os caminhos para seus scripts de teste que estão na pasta zip que você carregou na guia binários.

  - **Scripts de teste de caixa in-locar:** Digite os caminhos relativos para a instalação, início, fechamento e desinstalação de scripts. Você também tem a opção de selecionar configurações adicionais para o script de instalação.
  - **Scripts de teste funcionais:** Digite o caminho relativo para cada script de teste funcional carregado. Scripts de teste funcionais adicionais podem ser adicionados usando o ```Add Script``` botão. Você precisa de no mínimo um (1) script e pode adicionar até oito (8) scripts de teste funcionais. 
  
    Os scripts são executados em sequência de carregamento e uma falha em um script específico impedirá a execução de scripts subsequentes.
    Você também tem a opção de selecionar configurações adicionais para cada script fornecido.

## <a name="set-script-path"></a>Definir caminho de script

![Imagem da tarefa de teste](Media/testtask.png)

Exemplo de como fornecer o caminho relativo em uma estrutura de pastas está abaixo:

_**Zip_file_uploaded**_
~~~
├── file1.exe

├── ScriptX.ps1

├── folder1

│   ├── file3.exe

│   ├── script.ps1
~~~
  - **ScriptX.ps1** teria. _ScriptX.ps1_ como o caminho relativo.
  - **Script.ps1** teria _folder1/script.ps1_ como o caminho relativo.


## <a name="next-steps"></a>Próximas etapas

Exibir detalhes da guia Opções de Teste no próximo artigo 
> [!div class="nextstepaction"]
> [Próxima etapa](testoptions.md)
