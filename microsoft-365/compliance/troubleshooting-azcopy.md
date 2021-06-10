---
title: Solucionar problemas do AzCopy no Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Solucionar erros do Azure AzCopy ao carregar dados não Office 365 para correção de erros no Advanced eDiscovery.
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: f34b47762601a3cc66b46fd8a2691c0fb87d3354
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919287"
---
# <a name="troubleshoot-azcopy-in-advanced-ediscovery"></a>Solucionar problemas do AzCopy no Advanced eDiscovery

Ao carregar dados ou documentos que não sejam Microsoft 365 para correção de erros no Advanced eDiscovery, a interface do usuário fornece um comando do Azure AzCopy que contém parâmetros com o local de onde os arquivos que você deseja carregar são armazenados e o local de armazenamento do Azure para o qual os arquivos serão carregados. Para carregar seus documentos, copie esse comando e execute-o em um Prompt de Comando no computador local.  A captura de tela a seguir mostra um exemplo de um comando do AzCopy:

![Upload arquivos não Microsoft 365](../media/46ba68f6-af11-4e70-bb91-5fc7973516e3.png)

Normalmente, o comando fornecido funciona quando você o executar. No entanto, pode haver casos em que o comando exibido não será executado com êxito. Aqui estão alguns motivos possíveis.

## <a name="the-supported-version-of-azcopy-isnt-installed-on-the-local-computer"></a>A versão com suporte do AzCopy não está instalada no computador local

Neste momento, você deve usar o AzCopy v8.1 para carregar dados não Microsoft 365 no Advanced eDiscovery. O comando AzCopy exibido na  página arquivos Upload mostrado na captura de tela anterior retornará um erro se você não estiver usando o AzCopy v8.1. Para instalar essa versão, consulte [Transfer data with the AzCopy v8.1 on Windows](/previous-versions/azure/storage/storage-use-azcopy).

## <a name="azcopy-isnt-installed-on-the-local-computer-or-its-not-installed-in-the-default-location"></a>O AzCopy não está instalado no computador local ou não está instalado no local padrão

Se o AzCopy não estiver instalado ou ele estiver instalado em um local diferente do local de instalação padrão (que é ), você poderá receber o seguinte erro ao executar o comando `%ProgramFiles(x86)%` do AzCopy:

> O sistema não pode encontrar o caminho especificado.

Se o AzCopy não estiver instalado no computador local, você poderá encontrar informações de instalação em Transferir dados com o [AzCopy v8.1 no Windows](/previous-versions/azure/storage/storage-use-azcopy). Certifique-se de instalá-lo no local padrão.

Se o AzCopy estiver instalado, mas estiver instalado em um local diferente do local padrão, você poderá copiar o comando, colá-lo em um arquivo de texto e, em seguida, alterar o caminho para o local onde o AzCopy está instalado. Por exemplo, se o Azcopy estiver localizado em , você poderá alterar a `%ProgramFiles%` primeira parte do comando de para `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe` `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy` . Depois de fazer essa alteração, copie-a do arquivo de texto e execute-a em um Prompt de Comando.

> [!TIP]
> Se o AzCopy estiver instalado em outro local, o local de instalação padrão, considere desinstalá-lo e reinstalá-lo no local padrão. Isso ajudará a evitar esse problema no futuro.