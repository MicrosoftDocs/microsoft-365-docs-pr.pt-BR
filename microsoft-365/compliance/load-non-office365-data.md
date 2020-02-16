---
title: Carregar dados que não sejam do Office 365 em evidência
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
description: ''
ms.openlocfilehash: 4db0b40d485c4c1107bdcb0d49616cadb15b1915
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42072139"
---
# <a name="load-non-office-365-data-into-evidence"></a>Carregar dados que não sejam do Office 365 em evidência

Nem todos os documentos que você pode precisar analisar em uma investigação de dados estarão localizados no Office 365. Com o recurso de importação de conteúdo que não é do Office 365, você pode carregar documentos que não residem no Office 365 em evidência para que eles possam ser analisados em uma investigação de dados.

>[!Note]
>A investigação de dados requer um Office 365 E3 com o complemento de conformidade avançada ou uma assinatura E5 para sua organização. Se você não tiver esse plano e quiser tentar a descoberta eletrônica avançada, poderá se inscrever para uma avaliação do Office 365 Enterprise e5.

## <a name="before-you-begin"></a>Antes de começar

O uso do recurso de upload que não é do Office 365 conforme descrito neste procedimento exige que você tenha:

- Um Office 365 E3 com um complemento de conformidade avançada ou uma assinatura e5.

- Todos os responsáveis cujo conteúdo que não seja do Office 365 será carregado precisarão ter E3 com o complemento de conformidade avançada ou com licenças e5.

- Uma ocorrência de descoberta eletrônica existente.

- Todos os arquivos para carregamento são coletados em pastas onde há uma pasta por responsáveis e o nome das pastas está nesse formato *alias@domainname*. O *alias@domainname* deve ser Users alias e Domain do Office 365. Você pode coletar todas as pastas de *alias@domainname* em uma pasta raiz. A pasta raiz pode conter apenas as pastas *alias@domainname* , não deve haver arquivos soltos na pasta raiz.

- Uma conta que seja um Gerenciador de descoberta eletrônica ou ferramentas de armazenamento do Microsoft Azure administrador instaladas em um computador que tenha acesso à estrutura de pasta de conteúdo não-Office 365.

- Instale o AzCopy, que pode ser feito aqui:https://docs.microsoft.com/azure/storage/common/storage-use-azcopy

## <a name="upload-non-office-365-content-in-to-a-data-investigation"></a>Carregar conteúdo não-Office 365 em uma investigação de dados

1. * * * * As investigações de dados * *, então a investigação de onde os dados não-Office 365 serão carregados.  Clique na guia **evidência** e selecione o conjunto de evidências para o qual você deseja carregar os dados que não são do Office 365.  Se você ainda não criou um conjunto de evidências, é possível fazer isso agora.  Por fim, clique em **gerenciar evidências** e, em seguida, **Exibir uploads** na seção de dados não-Office 365

2. Clique no botão **carregar arquivos** para iniciar o assistente de importação de dados não-Office 365.

![Carregar arquivos](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

3. A primeira etapa no assistente simplesmente prepara um blob do Azure seguro para os arquivos a serem carregados.  Após a conclusão da preparação, clique no botão **próximo: carregar arquivos** .

![Preparar a importação de dados não-Office 365](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
4. Na etapa **carregar arquivos** , especifique o **caminho para o local dos arquivos**, onde os dados não-Office 365 que você planeja importar estão localizados.  Definir o local correto garante que o comando AzCopy seja atualizado corretamente.

> [!NOTE]
> Se você ainda não tiver instalado o AzCopy, poderá fazer isso daqui:https://docs.microsoft.com/azure/storage/common/storage-use-azcopy

5. Copie o comando predefinido clicando no link **copiar para a área de transferência** . Inicie um prompt de comando do Windows, Cole o comando e pressione Enter.  Os arquivos serão carregados para o armazenamento de blob do Azure seguro para a próxima etapa.

![Carregar arquivos para importação de dados não-Office 365](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

![Usar o AzCopy para importar dados que não sejam do Office 365](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

6. Por fim, volte para a segurança & conformidade e clique no botão **próximo: processar arquivos** .  Isso inicia o processamento, extração de texto e indexação de arquivos carregados.  Você pode acompanhar o progresso do processamento aqui ou na guia **trabalhos** .  Após a conclusão, os novos arquivos estarão disponíveis no conjunto de evidências.  Após a conclusão do processamento, você pode ignorar o assistente.

![Arquivos de processo de importação não-Office 365](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

