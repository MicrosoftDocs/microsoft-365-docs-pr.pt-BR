---
title: Carregar dados que não sejam do Office 365 em evidência
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
ms.openlocfilehash: ee1e6f8a064567126d75b099cc3003e8a4d6a020
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37072831"
---
# <a name="load-non-office-365-data-into-evidence"></a>Carregar dados que não sejam do Office 365 em evidência

Nem todos os documentos que você pode precisar analisar com a descoberta eletrônica avançada do Office 365 residirão no Office 365. Com o recurso de importação de conteúdo não-Office 365 na descoberta eletrônica avançada, é possível carregar documentos que não residem no Office 365 em um conjunto de trabalho para que seja analisado com a descoberta eletrônica avançada. Este procedimento mostra como trazer documentos não-Office 365 para a descoberta eletrônica avançada para análise.

>[!Note]
>A descoberta eletrônica avançada requer um Office 365 E3 com o complemento de conformidade avançada ou uma assinatura E5 para sua organização. Se você não tiver esse plano e quiser tentar a descoberta eletrônica avançada, poderá se inscrever para uma avaliação do Office 365 Enterprise e5.

## <a name="before-you-begin"></a>Antes de começar
O uso do recurso de upload que não é do Office 365 conforme descrito neste procedimento exige que você tenha:

- Um Office 365 E3 com um complemento de conformidade avançada ou uma assinatura e5.

- Todos os responsáveis cujo conteúdo que não seja do Office 365 será carregado precisarão ter E3 com o complemento de conformidade avançada ou com licenças e5.

- Uma ocorrência de descoberta eletrônica existente.

- Todos os arquivos para carregamento são coletados em pastas onde há uma pasta por responsáveis e o nome das pastas está neste formato *alias @ nome_do_domínio* . O *alias @ nome_do_domínio* deve ser Users Office 365 alias and Domain. Você pode coletar todas as pastas *alias @ DomainName* em uma pasta raiz. A pasta raiz pode conter apenas as pastas *alias @ DomainName* , não deve haver arquivos soltos na pasta raiz.

- Uma conta que seja um Gerenciador de descoberta eletrônica ou ferramentas de armazenamento do Microsoft Azure administrador instaladas em um computador que tenha acesso à estrutura de pasta de conteúdo não-Office 365.

- Instale o AzCopy, que pode ser feito aqui:https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy

## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a>Carregar conteúdo que não seja do Office 365 na descoberta eletrônica avançada

1. Como um gerente de descoberta eletrônica ou administrador de descoberta eletrônica, abra a descoberta eletrônica avançada e, em seguida, o caso em que os dados que não sejam do Office 365 serão carregados.  Clique na guia **conjuntos de trabalho** e selecione o conjunto de trabalho para o qual você deseja carregar os dados não-Office 365.  Se você ainda não criou um conjunto de trabalho, você pode fazer isso agora.  Por fim, clique em **gerenciar conjunto de trabalho** , **Exibir uploads** na seção de dados não-Office 365

2. Clique no botão **carregar arquivos** para iniciar o assistente de importação de dados não-Office 365.

![Carregar arquivos](media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

3. A primeira etapa no assistente simplesmente prepara um blob do Azure seguro para os arquivos a serem carregados.  Após a preparação ser compelted, clique no botão **próximo: carregar arquivos** .

![Não-Office 365 Import-Prepare](media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
4. Na etapa **carregar arquivos** , especifique o **caminho para o local dos arquivos**, onde os dados não-Office 365 que você planeja importar estão localizados.  Definir o local correto garante que o comando AzCopy seja atualizado corretamente.

> [!NOTE]
> Se você ainda não tiver instalado o AzCopy, poderá fazer isso daqui:https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy

5. Copie o comando predefinido clicando no link **copiar para a área de transferência** . Inicie um prompt de comando do Windows, Cole o comando e pressione Enter.  Os arquivos serão carregados para o armazenamento de blob do Azure seguro para a próxima etapa.

![Arquivos não-Office 365 Import-upload](media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

![Importação de AzCopy não-Office 365](media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

6. Por fim, volte para a segurança & conformidade e clique no botão **próximo: processar arquivos** .  Isso iniciará o processamento, a extração de texto e a indexação de arquivos carregados.  Você pode acompanhar o progresso do processamento aqui ou na guia **trabalhos** .  Depois de concluído, os novos arquivos estarão disponíveis no conjunto de trabalho.  Quando o processamento estiver concluído, você poderá ignorar o assistente.

![Arquivos de processo de importação e não-Office 365](media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

