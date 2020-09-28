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
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: aaed88463f690853672780b48a8ee3857a956847
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295724"
---
# <a name="import-a-term-set-using-a-skos-based-format"></a>Importar um conjunto de termos usando um formato baseado em SKOS

Você pode importar um conjunto de termos usando um formato baseado em SKOS. Para obter detalhes sobre o formato, consulte [referência de formato skos de taxonomia do SharePoint](skos-format-reference.md).

Recomendamos manter seus arquivos de importação para menos de 20.000 termos. Arquivos maiores podem aumentar o tempo gasto para validação e importação.

1. No centro de administração do SharePoint, expanda **serviços de conteúdo**e clique em **repositório de termos**.

2. Selecione o grupo de termos em que você deseja importar o conjunto de termos.

3. Na barra de comandos, clique em **Importar conjunto de termos**.
 
4.  Se você deseja baixar um arquivo de exemplo para usar como modelo, clique em **Sample-Metadata. TTL** para obter um arquivo de exemplo que usa o formato baseado em skos.
 
5.  Crie o arquivo de importação que contém os conjuntos de termos & termos que você deseja importar.

6.  Em **formato de arquivo**, selecione **skos (*. TTL)**.

7.  Clique em **procurar** e navegue até e adicione o arquivo de importação.

8.  Clique em **Importar **. Não feche o painel até que a importação seja concluída.

Após a importação bem-sucedida do arquivo, será exibida uma mensagem de êxito, e o repositório de termos será atualizado e você poderá navegar até os conjuntos de termos recém-criados.

## <a name="see-also"></a>Confira também

[Introdução a metadados gerenciados](https://docs.microsoft.com/sharepoint/managed-metadata)

[Visão geral da compreensão do documento](document-understanding-overview.md)

[Importar conjuntos de termos (nível de site)](https://support.microsoft.com/office/168fbc86-7fce-4288-9a1f-b83fc3921c18)