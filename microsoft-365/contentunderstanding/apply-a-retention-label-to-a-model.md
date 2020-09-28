---
title: Aplicar um rótulo de retenção a um documento entendendo o modelo
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 10/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Este artigo descreve como aplicar um rótulo de retenção a um documento entendendo o modelo
ms.openlocfilehash: 26ad64906c0e2a311d8b244e8e1596a8b975cc15
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294909"
---
# <a name="apply-a-retention-label-to-a-document-understanding-model"></a>Aplicar um rótulo de retenção a um documento entendendo o modelo

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

Você pode facilmente aplicar um [rótulo de retenção](https://docs.microsoft.com/microsoft-365/compliance/retention) a um documento entendendo o modelo no Microsoft SharePoint Syntex.

Os rótulos de retenção permitem que você aplique as configurações de retenção aos documentos que o documento entende modelos Identify.  Por exemplo, você deseja que seu modelo não apenas identifique os documentos de *aviso de seguros* que são carregados para sua biblioteca de documentos, mas também para aplicar uma marca de retenção de *negócios* a eles, para que esses documentos não possam ser excluídos da biblioteca de documentos para o período de tempo especificado (os próximos cinco meses, por exemplo).

Você pode aplicar um rótulo de retenção pré-existente ao documento entendendo o modelo por meio de suas configurações de modelo na home page do seu modelo. 

> [!Important]
> Para que os rótulos de retenção estejam disponíveis para aplicar ao modelo de compreensão do conteúdo, eles precisam ser [criados e publicados no centro de conformidade da Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/create-apply-retention-labels#how-to-create-and-publish-retention-labels).

## <a name="to-add-a-retention-label-to-a-document-understanding-model"></a>Para adicionar um rótulo de retenção a um documento entendendo o modelo

1. Na página inicial do modelo, selecione **configurações de modelo**.</br>
2. Em **configurações de modelo**, na seção **segurança e conformidade** , selecione o menu **rótulo de retenção** para ver uma lista de rótulos de retenção que estão disponíveis para seu para se aplicar ao modelo.</br>
 ![Menu rótulo de retenção](../media/content-understanding/retention-labels-menu.png)</br> 
3. Selecione o rótulo de retenção que você deseja aplicar ao modelo e, em seguida, selecione **salvar**.</br>

Depois de aplicar o rótulo de retenção ao modelo, você poderá aplicá-lo a:
- Nova biblioteca de documentos
- Biblioteca de documentos para a qual o modelo já está aplicado
 
## <a name="apply-the-retention-label-to-a-document-library-to-which-the-model-is-already-applied"></a>Aplicar o rótulo de retenção a uma biblioteca de documentos à qual o modelo já está aplicado

Se o documento que entende o modelo já tiver sido aplicado a uma biblioteca de documentos, você poderá fazer o seguinte para sincronizar sua atualização de etiqueta de retenção para aplicá-la à biblioteca de documentos:</br>

1. Na home page do modelo, na seção **bibliotecas com este modelo** , selecione a biblioteca de documentos à qual você deseja aplicar a atualização do rótulo de retenção. </br> 
2. Selecione **sincronizar**. </br>
 ![Modelo de sincronização](../media/content-understanding/sync-model.png)</br> 


Depois de aplicar a atualização e sincronizá-la ao seu modelo, você pode confirmar se ela foi aplicada fazendo o seguinte:

1. No centro de conteúdo, na seção **bibliotecas com este modelo** , clique na biblioteca à qual o modelo atualizado foi aplicado. </br>
2. No modo de exibição de biblioteca de documentos, selecione o ícone de informações para verificar as propriedades do modelo.</br>  
3. Na lista de **modelos ativos** , selecione o modelo atualizado.</br>
4. Na seção **rótulo de retenção** , você verá o nome do rótulo de retenção aplicado.</br>


Na página de exibição do seu modelo na biblioteca de documentos, uma nova coluna de **rótulo de retenção** será exibida.  À medida que o modelo classifica arquivos que ele identifica como pertencente ao tipo de conteúdo e o lista no modo de exibição de biblioteca, a coluna rótulo de retenção também exibirá o nome do rótulo de retenção que foi aplicado a ele por meio do modelo.


Por exemplo, todos os documentos de *aviso de seguro* que seu modelo identifica também terão o rótulo de retenção de *negócios* aplicado a eles, impedindo que eles sejam excluídos da biblioteca de documentos por cinco meses. Se for feita uma tentativa de excluir o arquivo da biblioteca de documentos, um erro será exibido dizendo que não é permitido por causa do rótulo de retenção aplicado.

## <a name="see-also"></a>Confira também
[Criar um classificador](create-a-classifier.md)</br>
[Criar um extrator](create-an-extractor.md)</br>
[Visão geral da compreensão do documento](document-understanding-overview.md)</br>
[Criar um modelo de processamento de formulários](create-a-form-processing-model.md)  
