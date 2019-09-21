---
title: Correção de erros durante o processamento de dados
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
description: ''
ms.openlocfilehash: 02fa8870d6edb4e1a6616604ee0e98638b217237
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37072762"
---
# <a name="error-remediation-when-processing-data"></a>Correção de erros durante o processamento de dados

A correção de erros permite que os administradores de descoberta eletrônica corrijam problemas de dados que impedem a descoberta eletrônica avançada do processamento adequado do conteúdo. Por exemplo, os arquivos protegidos por senha não podem ser processados, já que os arquivos são bloqueados ou criptografados. Usando a correção de erros, os administradores de descoberta eletrônica podem baixar arquivos com esses erros, remover a proteção por senha e carregar os arquivos corrigidos.

Use o fluxo de trabalho a seguir para corrigir arquivos com erros em casos de descoberta eletrônica avançada.

## <a name="create-an-error-remediation-session-to-remediate-files-with-processing-errors"></a>Criar uma sessão de correção de erro para corrigir arquivos com erros de processamento

>[!NOTE]
>Se o assistente de correção de erros for fechado a qualquer momento durante o procedimento a seguir, você poderá retornar à sessão de correção de erro na guia **processamento** selecionando as **correções** no menu suspenso **Exibir** .

1. Na guia **processamento** da caixa de descoberta eletrônica avançada, selecione **erros** no menu suspenso **Exibir** e, em seguida, selecione um conjunto de revisão ou o caso inteiro no menu suspenso **escopo** . Esta seção exibe todos os erros do caso ou erro de um conjunto de revisão específico.

   ![Correção de erro](media/8c2faf1a-834b-44fc-b418-6a18aed8b81a.png)

2. Selecione os erros que você deseja corrigir clicando no botão de opção ao lado do tipo de erro ou tipo de arquivo.  No exemplo a seguir, estamos corrigindo um arquivo protegido por senha.

3. Clique em **nova correção de erro**.

    O fluxo de trabalho de correção de erro é iniciado com um estágio de preparação em que os arquivos com erros são copiados para um local de armazenamento do Azure fornecido pela Microsoft para que você possa baixá-los para o computador local para correção.

    ![Preparando correção de erro](media/390572ec-7012-47c4-a6b6-4cbb5649e8a8.png)

4. Após a conclusão da preparação, clique em **Avançar: baixar arquivos** para continuar com o download.

    ![Baixar arquivos](media/6ac04b09-8e13-414a-9e24-7c75ba586363.png)

5. Para baixar arquivos, especifique o **caminho de destino para download**. Este é o caminho para a pasta pai no computador local em que o arquivo será baixado.  O caminho padrão,%USERPROFILE%\Downloads\errors, aponta para a pasta downloads do usuário conectado. Você pode alterar esse caminho, se desejado. Se você alterar, recomendamos que você use um caminho de arquivo local para o melhor desempenho. Não use um caminho de rede remoto. Por exemplo, você poderia usar o caminho **C:\Remediation**. 

   O caminho para a pasta pai é automaticamente adicionado ao comando AzCopy (como o valor do parâmetro **/dest** ).

6. Copie o comando predefinido clicando em **copiar para área de transferência**. Abra um prompt de comando do Windows, Cole o comando AzCopy e pressione **Enter**.  

    ![Preparar para correção de erros](media/f364ab4d-31c5-4375-b69f-650f694a2f69.png)    

    > [!NOTE]
    > Você deve usar o AzCopy v 8.1 para usar com êxito o comando fornecido na página **baixar arquivos** . Você também deve usar o AzCopy v 8.1 para carregar os arquivos na etapa 10. Para instalar esta versão do AzCopy, confira [transferir dados com o AzCopy v 8.1 no Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy). Se o comando AzCopy fornecido falhar, confira [solucionar problemas de AzCopy na descoberta eletrônica avançada](troubleshooting-azcopy.md).

    Os arquivos que você selecionou são baixados para o local que você especificou na etapa 5. Na pasta pai (por exemplo, **C:\Remediation**), a seguinte estrutura de subpastas é criada automaticamente:

    `<Parent folder>\Subfolder 1\Subfolder 2\<file>`

    - A *subpasta 1* é nomeada com a ID do caso ou do conjunto de revisão, dependendo do escopo selecionado na etapa 1.

    - A *subpasta 2* é nomeada com a ID de arquivo do arquivo baixado

    - O arquivo baixado está localizado na *subpasta 2* e também é chamado de ID de arquivo.

    Veja um exemplo do caminho da pasta e o nome do arquivo de erro que é criado quando os itens são baixados para a pasta pai **C:\Remediation** :

    `C:\Remediation\232f8b7e-089c-4781-88c6-210da0615d32\d1459499146268a096ea20202cd029857d64087706e6d6ca2a224970ae3b8938\d1459499146268a096ea20202cd029857d64087706e6d6ca2a224970ae3b8938.docx`

    Se vários arquivos forem baixados, cada um é baixado para uma subpasta nomeada com a ID de arquivo.

    > [!IMPORTANT]
    > Ao carregar arquivos na etapa 9 e na etapa 10, os arquivos corrigidos devem ter o mesmo nome de arquivo e estar localizados na mesma estrutura de subpastas. Os nomes de subpasta e de arquivo são usados para associar o arquivo corrigido ao arquivo de erro original. Se a estrutura de pastas ou os nomes de arquivo forem alterados, você receberá o `Cannot apply Error Remediation to the current Workingset`seguinte erro:. Para evitar problemas, recomendamos que você mantenha os arquivos corrigidos na mesma estrutura de pastas e subpastas pai.

7. Depois de baixar os arquivos, você pode corrigi-los com uma ferramenta apropriada. Para arquivos protegidos por senha, há várias ferramentas de quebra de senha que você pode usar. Se você souber as senhas dos arquivos, poderá abri-las e remover a proteção por senha.

8. Retorne à descoberta eletrônica avançada e o assistente de correção de erros e clique em **Avançar: carregar arquivos**.  Isso é movido para a próxima página onde você pode carregar os arquivos.

    ![Carregar arquivos](media/af3d8617-1bab-4ecd-8de0-22e53acba240.png)

9. Especifique a pasta pai onde os arquivos corrigidos estão localizados na caixa de texto **caminho para o local de arquivos** . Novamente, a pasta pai deve ter a mesma estrutura de subpasta que foi criada quando você baixou os arquivos.

    O caminho para a pasta pai é automaticamente adicionado ao comando AzCopy (como o valor do parâmetro **/Source** ).

10. Copie o comando predefinido clicando em **copiar para área de transferência**. Abra um prompt de comando do Windows, Cole o comando AzCopy e pressione **Enter**. carregar os arquivos.

    ![ff2ff691-629f-4065-9b37-5333f937daf6. png](media/ff2ff691-629f-4065-9b37-5333f937daf6.png)

11. Depois de executar o comando AzCopy, clique em **Avançar: processar arquivos**.

    Quando o processamento estiver concluído, você poderá ir para a revisão definir e exibir os arquivos corrigidos. 

## <a name="what-happens-when-files-are-remediated"></a>O que acontece quando os arquivos são corrigidos

Quando os arquivos corrigidos são carregados, os metadados originais são preservados, exceto os seguintes campos: 

- ExtractedTextSize
- HasText
- IsErrorRemediate
- Loadid
- ProcessingErrorMessage
- ProcessingStatus
- Texto
- WordCount
- WorkingsetId

Para obter uma definição de todos os campos de metadados na descoberta eletrônica avançada, confira [campos de metadados do documento](document-metadata-fields.md).
