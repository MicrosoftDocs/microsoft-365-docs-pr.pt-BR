---
title: Carregar dados que não sejam da Microsoft 365 em um conjunto de revisão
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
description: Saiba como importar dados que não são da Microsoft 365 para uma análise definida para análise em um caso de descoberta eletrônica avançada.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f9b506edc55da1916ae908eaa7ca619ba7300f87
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44815458"
---
# <a name="load-non-microsoft-365-data-into-a-review-set"></a>Carregar dados que não sejam da Microsoft 365 em um conjunto de revisão

Nem todos os documentos que você precisa analisar na descoberta eletrônica avançada estão localizados no Microsoft 365. Com o recurso de importação de dados não-Microsoft 365 na descoberta eletrônica avançada, você pode carregar documentos que não estão localizados no Microsoft 365 em um conjunto de revisão. Este artigo mostra como trazer documentos que não são da Microsoft 365 para a descoberta eletrônica avançada para análise.

## <a name="requirements-to-upload-non-office-365-content"></a>Requisitos para carregar conteúdo não-Office 365

O uso do recurso de upload que não é da Microsoft 365 descrito neste artigo requer que você tenha o seguinte:

- Todos os responsáveis que você deseja associar conteúdo que não seja da Microsoft 365 devem receber a licença apropriada. Para obter mais informações, consulte [introdução à descoberta eletrônica avançada](get-started-with-advanced-ediscovery.md#step-1-verify-and-assign-appropriate-licenses).

- Uma ocorrência de descoberta eletrônica avançada existente.

- Os responsáveis devem ser adicionados ao caso antes que você possa carregar e associar os dados que não são da Microsoft 365 a eles.

- Dados que não são da Microsoft 365 devem ser um tipo de arquivo com suporte da descoberta eletrônica avançada. Para saber mais, confira [tipos de arquivo com suporte na descoberta eletrônica avançada](supported-filetypes-ediscovery20.md).

- Todos os arquivos carregados em um conjunto de revisão devem estar localizados em pastas, onde cada pasta é associada a um determinado local. Os nomes dessas pastas devem usar o seguinte formato de nome: *alias@domainname*. O alias@domainname deve ser o alias e o domínio do Microsoft 365 do usuário. Você pode coletar todas as pastas de alias@domainname em uma pasta raiz. A pasta raiz pode conter apenas as pastas alias@domainname. Não há suporte para arquivos soltos na pasta raiz.

   A estrutura de pastas para os dados que não são da Microsoft 365 que você deseja carregar seria semelhante ao exemplo a seguir:

   - c:\nonO365\abraham.mcmahon@contoso.com
   - c:\nonO365\jewell.gordon@contoso.com
   - c:\nonO365\staci.gonzalez@contoso.com

   Onde abraham.mcmahon@contoso.com, jewell.gordon@contoso.com e staci.gonzalez@contoso.com são os endereços SMTP dos responsáveis no caso.

   ![Estrutura de pastas de carregamento de dados não-Microsoft 365](../media/3f2dde84-294e-48ea-b44b-7437bd25284c.png)

- Uma conta atribuída ao grupo de função Gerenciador de descoberta eletrônica (e adicionada como administrador de descoberta eletrônica).

- A ferramenta AzCopy v 8.1 instalada em um computador que tem acesso à estrutura de pasta de conteúdo não-Microsoft 365. Para instalar o AzCopy, confira [transferir dados com o AzCopy v 8.1 no Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy). Certifique-se de instalar o AzCopy no local padrão, que é **% ProgramFiles (x86)% \ Microsoft SDKs\Azure\AzCopy**. Você deve usar o AzCopy v 8.1. Outras versões do AzCopy podem não funcionar ao carregar dados que não sejam da Microsoft 365 na descoberta eletrônica avançada.


## <a name="upload-non-microsoft-365-content-into-advanced-ediscovery"></a>Carregar conteúdo não-Microsoft 365 na descoberta eletrônica avançada

1. Como um gerente de descoberta eletrônica ou administrador de descoberta eletrônica, abra descoberta eletrônica avançada e vá para o caso em que os dados não-Microsoft 365 serão carregados.  

2. Clique em **revisar conjuntos**e selecione o conjunto de revisão para carregar os dados que não são da Microsoft 365 para o.  Se você não tiver um conjunto de revisão, você pode criar um. 
 
3. No conjunto de revisão, clique em **gerenciar o conjunto de revisão**e, em seguida, clique em **Exibir carregamentos** no bloco de **dados não-Microsoft 365** .

4. Clique em **carregar arquivos** para iniciar o assistente de importação de dados.

   ![Carregar arquivos](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

   A primeira etapa do assistente prepara um local de armazenamento do Azure seguro fornecido pela Microsoft para carregar os arquivos.  Quando a preparação estiver concluída, o botão **Avançar: carregar arquivos** se tornará ativo.

   ![Importação não-Microsoft 365: preparar](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
5. Clique em **Avançar: carregar arquivos**.

6. Na página **carregar arquivos** , faça o seguinte:

   ![Importação não-Microsoft 365: carregar arquivos](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

   a. Na caixa **caminho para o local dos arquivos** , verifique ou digite o local da pasta raiz onde você armazenou os dados que não são da Microsoft 365 que você deseja carregar. Por exemplo, para o local dos arquivos de exemplo mostrados na **seção antes de começar**, digite **%USERPROFILE\Downloads\nonO365**. Fornecer o local correto garante que o comando AzCopy exibido em caixa abaixo do caminho seja atualizado corretamente.

   b. Clique em **copiar para área de transferência** para copiar o comando exibido na caixa.

7. Inicie um prompt de comando do Windows, Cole o comando copiado na etapa anterior e pressione **Enter** para iniciar o comando AzCopy.  Depois de iniciar o comando, os arquivos que não são da Microsoft 365 serão carregados no local de armazenamento do Azure que foi preparado na etapa 4.

   ![Importação não-Microsoft 365: AzCopy](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

   > [!NOTE]
   > Conforme mencionado anteriormente, você deve usar o AzCopy v 8.1 para usar com êxito o comando fornecido na página **carregar arquivos** . Se o comando AzCopy fornecido falhar, confira [solucionar problemas de AzCopy na descoberta eletrônica avançada](troubleshooting-azcopy.md).

8. Volte para o centro de conformidade & segurança e clique em **Avançar: processar arquivos** no assistente.  Isso inicia o processamento, extração de texto e indexação de arquivos que não são da Microsoft 365 que foram carregados no local de armazenamento do Azure.  

9. Acompanhe o progresso do processamento dos arquivos na página **arquivos de processo** ou na guia **trabalhos** , exibindo um trabalho chamado **adição de dados que não são da Microsoft 365 a um conjunto de revisão**.  Depois que o trabalho for concluído, os novos arquivos estarão disponíveis no conjunto de revisão.

   ![Importação não-Microsoft 365: processar arquivos](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

10. Depois que o processamento for concluído, você poderá fechar o assistente.
