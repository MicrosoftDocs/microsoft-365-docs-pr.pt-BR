---
title: Importar um conjunto de termos usando um formato baseado em SKOS
description: Saiba como importar um conjunto de termos usando um formato baseado em SKOS
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: Priority
ms.openlocfilehash: 318497b8b1815b281eff7d781820616c9be9d5ed
ms.sourcegitcommit: f7ca339bdcad38796c550064fb152ea09687d0f3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2020
ms.locfileid: "48321236"
---
# <a name="import-a-term-set-using-a-skos-based-format"></a>Importar um conjunto de termos usando um formato baseado em SKOS

Você pode importar um conjunto de termos usando um formato baseado em SKOS. Para obter detalhes sobre o formato, confira [referência do formato SKOS da taxonomia do SharePoint](skos-format-reference.md).

É recomendável manter seus arquivos de importação para menos de 20.000 termos. Arquivos maiores podem aumentar o tempo necessário para a validação e a importação.

1. No Centro de administração do SharePoint, expanda **Serviços de conteúdo** e, em seguida, clique em **Repositório de termos**.

2. Selecione o grupo de termos do qual você deseja importar o conjunto de termos.

3. Na barra de comandos, clique em **Importar conjunto de termos**.
 
4.  Se você quiser baixar um arquivo de exemplo para usar como modelo, clique em **sample-metadata.ttl** para obter um arquivo de exemplo que usa o formato baseado em SKOS.
 
5.  Crie o arquivo de importação que contém os conjuntos de termos e termos que você deseja importar.

6.  Em **Formato de arquivo**, selecione **SKOS (*.ttl)**.

7.  Clique em **Procurar**, navegue até o arquivo de importação e o adicione.

8.  Clique em **Importar**. Não feche o painel até que a importação seja concluída.

Na importação bem-sucedida do arquivo, uma mensagem de êxito será exibida, e o repositório de termos será atualizado, e você poderá navegar até os conjuntos de termos criados recentemente.

## <a name="see-also"></a>Confira também

[Introdução a metadados gerenciados](https://docs.microsoft.com/sharepoint/managed-metadata)

[Visão geral da compreensão de documentos](document-understanding-overview.md)

[Importar conjuntos de termos (nível do site)](https://support.microsoft.com/office/168fbc86-7fce-4288-9a1f-b83fc3921c18)