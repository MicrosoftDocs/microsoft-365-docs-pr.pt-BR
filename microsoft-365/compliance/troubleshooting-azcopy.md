---
title: Solucionar problemas de AzCopy na descoberta eletrônica avançada
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: o365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 8033ad24d4e2fd742d5e66f75f6bca77d4796d1d
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37073053"
---
# <a name="troubleshoot-azcopy-in-advanced-ediscovery"></a>Solucionar problemas de AzCopy na descoberta eletrônica avançada

Ao carregar dados não-Office 365 ou documentos para correção de erros na descoberta eletrônica avançada, a interface do usuário fornece um comando do AzCopy do Azure que contém parâmetros com o local onde os arquivos que você deseja carregar estão armazenados e o armazenamento do Azure local para o qual os arquivos serão carregados. Para carregar seus documentos, copie esse comando e execute-o em um prompt de comando no computador local.  A captura de tela a seguir mostra um exemplo de um comando do AzCopy:

![Carregar arquivos que não são do Office 365](media/46ba68f6-af11-4e70-bb91-5fc7973516e3.png)

Normalmente, o comando fornecido funciona quando você o executa. No entanto, pode haver casos em que o comando exibido não seja executado com êxito. Veja alguns motivos possíveis.

## <a name="the-supported-version-of-azcopy-isnt-installed-on-the-local-computer"></a>A versão suportada do AzCopy não está instalada no computador local

Neste momento, você deve usar o AzCopy v 8.1 para carregar dados que não sejam do Office 365 na descoberta eletrônica avançada. O comando AzCopy exibido na página **carregar arquivos** mostrados na captura de tela anterior retornará um erro se você não estiver usando o AzCopy v 8.1. Para instalar essa versão, consulte [transferir dados com o AzCopy v 8.1 no Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).

## <a name="azcopy-isnt-installed-on-the-local-computer-or-its-not-installed-in-the-default-location"></a>O AzCopy não está instalado no computador local ou não está instalado no local padrão

Se o AzCopy não estiver instalado ou estiver instalado em um local diferente do local de instalação padrão (ou `%ProgramFiles(x86)%`seja), você pode receber o seguinte erro ao executar o comando AzCopy:

    The system cannot find the path specified.

Se o AzCopy não estiver instalado no computador local, você poderá instalar [daqui.](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy) Certifique-se de instalá-lo no local padrão.

Se o AzCopy estiver instalado, mas estiver instalado em um local diferente do local padrão, você poderá copiar o comando, colá-lo em um arquivo de texto e alterar o caminho para o local onde o AzCopy está instalado. Por exemplo, se Azcopy estiver localizado em `%ProgramFiles%`, então você poderá alterar a primeira parte do comando de `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe` para. `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy` Após fazer essa alteração, copie-a do arquivo de texto e, em seguida, execute um prompt de comando.

> [!TIP]
> Se o AzCopy estiver instalado em um local diferente do local de instalação padrão, considere desinstalá-lo e, em seguida, instale-o novamente no local padrão. Isso ajudará a evitar esse problema no futuro.
