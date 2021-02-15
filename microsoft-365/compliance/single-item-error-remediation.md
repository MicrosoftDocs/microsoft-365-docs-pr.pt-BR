---
title: Correção de erros de item único
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Você pode corrigir um erro de processamento em um documento em uma revisão definida na Descoberta eDiscovery Avançada sem ter que seguir o processo de correção de erros em massa.
ms.openlocfilehash: 8e5d8d00f507dc5792a1beda018d4c76632b82f7
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751578"
---
# <a name="single-item-error-remediation-in-advanced-ediscovery"></a>Correção de erro de item único na Descoberta Avançada

A correção de erros oferece aos usuários da Descoberta eDiscovery Avançada a capacidade de corrigir problemas de dados que impedem que a Descoberta Avançada processe corretamente o conteúdo. Por exemplo, os arquivos protegidos por senha não podem ser processados porque esses arquivos estão bloqueados ou criptografados. Anteriormente, você só podia corrigir erros em massa usando esse [fluxo de trabalho.](error-remediation-when-processing-data-in-advanced-ediscovery.md) Mas, às vezes, não faz sentido corrigir erros em vários arquivos quando você não tem certeza se algum desses arquivos responde ao caso que você está investigando. Também pode não fazer sentido corrigir erros antes de você ter a chance de revisar os metadados do arquivo (como o local do arquivo ou quem tinha acesso) para ajudá-lo a tomar decisões de frente sobre a capacidade de resposta. Um novo recurso chamado correção de erros de *item* único oferece aos gerentes de Descobertas Digitais a capacidade de exibir os metadados dos arquivos com um erro de processamento e, se necessário, corrigir o erro diretamente no conjunto de revisão. O artigo aborda como identificar, ignorar e corrigir arquivos com erros de processamento em um conjunto de revisão.

## <a name="identify-documents-with-errors"></a>Identificar documentos com erros

Documentos com erros de processamento em um conjunto de revisão agora são identificados (com uma faixa). Você pode corrigir ou ignorar o erro. A captura de tela a seguir mostra a faixa de erro de processamento de um documento do Word em um conjunto de revisão protegido por senha. Observe também que você pode exibir os metadados de arquivo de documentos com erros de processamento.

![Faixa exibida para o documento com erro de processamento](../media/SIERimage1.png)

Você também pode procurar documentos com erros de processamento usando a condição de **status** de processamento ao consultar os documentos em um [conjunto de revisão.](review-set-search.md)

![Usar a condição de status de processamento para procurar documentos de erro](../media/SIERimage2.png)

### <a name="ignore-errors"></a>Ignorar erros

Você pode ignorar um erro de processamento clicando em **Ignorar** na faixa de erro de processamento. Quando você ignora um erro, o documento é removido do fluxo de trabalho de [correção de erros em massa.](error-remediation-when-processing-data-in-advanced-ediscovery.md) Depois que um erro é ignorado, a faixa do documento muda de cor e indica que o erro de processamento foi ignorado. A qualquer momento, você pode reverter a decisão de ignorar o erro clicando em **Reverter.**

![Clique em Ignorar para ignorar o erro de processamento](../media/SIERimage3.png)

Você também pode procurar todos os documentos que tiveram um erro de processamento que foi ignorado usando a condição de erros de processamento *ignorados* ao consultar documentos em um conjunto de revisão.

![Usar a condição de erros de processamento ignorados para procurar documentos de erro ignorados](../media/SIERimage4.png)

## <a name="remediate-a-document-with-errors"></a>Corrigir um documento com erros

Às vezes, pode ser necessário corrigir um erro de processamento em documentos (removendo uma senha, descriptografando um arquivo criptografado ou recuperando um documento corrompido) e, em seguida, adicionar o documento remediado ao conjunto de revisão. Isso permite que você revise e exporte o documento de erro junto com os outros documentos no conjunto de revisão. 

Para remediar um único documento, siga estas etapas:

1. Clique **em**  >  **Baixar original** para baixar uma cópia do arquivo para um computador local.

   ![Baixar o documento com o erro de processamento](../media/SIERimage5.png)

2. Corrigir o erro no arquivo offline. Para arquivos criptografados, isso exigiria software de descriptografia para remover a proteção por senha, forneça a senha e salve o arquivo ou use um nome de senha. Depois de remediar o arquivo, vá para a próxima etapa.

3. No conjunto de revisão, selecione o arquivo com o erro de processamento que você remediado e clique em **Correção.**

   ![Click Remediation in the banner of the document with processing error](../media/SIERimage6.png)


4. Clique **em** Procurar, vá até o local do arquivo remediado no computador local e selecione o arquivo.

   ![Clique em Procurar e selecione o arquivo remediado no computador local](../media/SIERimage7.png)

    Depois de selecionar o arquivo remediado, ele será carregado automaticamente no conjunto de revisão. Você pode acompanhar o status de processamento do arquivo.

    ![O status do processo de correção é exibido](../media/SIERimage8.png)

   Depois que o processamento for concluído, você poderá exibir o documento remediado.

    ![Você pode exibir o arquivo remediado no formato nativo no conjunto de revisão](../media/SIERimage9.png)

Para obter mais informações sobre o que acontece quando um documento é remediado, consulte o que acontece [quando os arquivos são remediados.](error-remediation-when-processing-data-in-advanced-ediscovery.md#what-happens-when-files-are-remediated)

## <a name="search-for-remediated-documents"></a>Procurar documentos remediados

Você pode pesquisar todos os documentos em um conjunto de revisão que foram remediados usando a condição **Palavras-chave** e especificando o seguinte par de propriedade:valor: **IsFromErrorRemediation:true**. Essa propriedade também está disponível no arquivo de carregamento de exportação quando você exporta documentos de um conjunto de revisão.
