---
title: Diretrizes de pacote de teste
description: Revisar as diretrizes em torno do pacote de teste
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
ms.openlocfilehash: b6842f793627bddeab842bbd9570c9c3481699a6
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322452"
---
# <a name="test-package-guidelines"></a>Diretrizes de pacote de teste

## <a name="1---script-referencing"></a>1. Referência de script

Quando você carrega um arquivo .zip no portal, descompaímos todo o conteúdo desse arquivo em uma pasta raiz. Você não precisa escrever nenhum código para fazer essa operação inicial de descomplável. Você também pode fazer referência a qualquer arquivo no .zip usando o caminho em relação ao arquivo zip carregado.

No exemplo abaixo, mostramos como você pode fazer referência aos binários/scripts do campo de entrada na guia Tarefas. O texto em azul deve ser inserido no campo **Caminho do script** sem **aspas.**

É importante que você esteja ciente do conteúdo em seu arquivo zip antes de carregar. Muitas vezes, ao fazer o zipping de uma pasta, o computador local criará uma pasta principal sob o arquivo zip. Nesse caso, a referência será mostrada em **negrito** abaixo:

 **Contoso_App_Folder.zip**
~~~ 
├── Contoso_App_Folder

│   ├── file1.exe

│   ├── ScriptX.ps1

│   ├── folder1

│        ├── file3.exe

│        ├── script.ps1
~~~

  - ScriptX.ps1 – **"Contoso_App_Folder/ScriptX.ps1"**
  - Script.ps1 – **"Contoso_App_Folder/folder1/script.ps1"**

Outras vezes, seu arquivo zip pode ter seus arquivos ou conteúdo logo abaixo dele ou seja, nenhuma pasta de nível 2nd:

 **Zip_file_uploaded.zip**
~~~ 
├── file1.exe

├── ScriptX.ps1

├── folder1

│   ├── file3.exe

│   ├── script.ps1
~~~
  - ScriptX.ps1 – **"ScriptX.ps1"**
  - Script.ps1 – **"folder1/script.ps1"**
  
## <a name="2---script-execution"></a>2. Execução de script

**Testes in-locar:** O pacote de aplicativos precisa conter pelo menos três scripts do PowerShell que executarão a instalação autônoma, o lançamento e o fechamento do aplicativo e suas dependências. Cada script deve manipular a verificação de seus próprios pré-requisitos, validando-o com êxito, bem como limpando depois de si mesmo (se necessário).

**Testes funcionais:** O pacote do aplicativo precisa conter pelo menos um script do PowerShell. Quando mais de um script é fornecido, os scripts são executados em sequência de carregamento e uma falha em um script específico impedirá a execução de scripts subsequentes.

### <a name="script-requirements"></a>Requisitos de script

• PowerShell Versão 5.1+     

• Execução autônoma    

• Código de retorno de erro               

• Validar o sucesso            

• Fazer logoff para a pasta de log específica do script

Cada script precisa ser executado completamente sem supervisão para executar com êxito no pipeline de teste.

> [!Note]
> Os scripts devem retornar "0" na conclusão bem-sucedida e um código de erro diferente de zero se ocorrer algum erro durante a execução.

Cada script deve validar se ele foi realizado com êxito. Por exemplo o script de instalação deve verificar a existência de determinados binários e/ou chaves de registro no sistema, depois que o binário do instalador terminar de executar para garantir com um grau razoável de confiança de que a instalação foi bem-sucedida. 

Isso é necessário para diagnosticar corretamente onde ocorrem erros durante uma executar um teste, por exemplo, não é possível instalar o aplicativo com êxito em vez de não poder iniciar o aplicativo.

> [!Important]
> **Evite o seguinte:** Os scripts não devem reiniciar o computador, se uma reinicialização for necessária, especifique isso durante o carregamento de seus scripts.

## <a name="3---log-collection"></a>3. Coleção Log

Cada script deve gerar todos os logs gerados em uma pasta chamada ```logs``` . Todas as pastas no diretório nomeado serão copiadas e ```logs``` apresentadas para download na ```Test Results``` página.

Por exemplo, o script de instalação (que pode estar localizado no diretório **App/scripts/install)** pode fazer seus logs para: **logs/install.log**, de forma que o log final estará em: **Apps/scripts/install/logs/install.log**

O sistema irá buscar o arquivo juntamente com outros arquivos em outras pastas e ```install.log``` ```logs``` colá-lo para download.


## <a name="4---application-binaries"></a>4. Binários de aplicativo

Quaisquer binários e dependências devem ser incluídos no arquivo zip único. 

Eles devem incluir tudo o que é necessário para a instalação do aplicativo (por exemplo, o instalador de aplicativos); se o aplicativo tiver uma dependência de quaisquer estruturas, como .NET Core/Standard ou .NET Framework, elas devem ser incluídas no arquivo e referenciadas corretamente nos scripts fornecidos.


> [!Note]
> O arquivo zip carregado não pode ter espaços ou caracteres especiais em seu nome

## <a name="next-steps"></a>Próximas etapas

Avance para o próximo artigo para exibir algumas **perguntas frequentes (perguntas frequentes)**
> [!div class="nextstepaction"]
> [Próxima etapa](faq.md)
