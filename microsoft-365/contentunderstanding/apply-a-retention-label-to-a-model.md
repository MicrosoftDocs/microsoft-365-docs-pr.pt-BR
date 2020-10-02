---
title: Aplicar um rótulo de retenção a um modelo de compreensão de documentos
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: Este artigo discute a aplicação de um rótulo de retenção a um modelo de compreensão de documentos
ms.openlocfilehash: 6b42f7df5e14f57f3754e7d65c5f4cf2e8fab6a0
ms.sourcegitcommit: f7ca339bdcad38796c550064fb152ea09687d0f3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2020
ms.locfileid: "48321840"
---
# <a name="apply-a-retention-label-to-a-document-understanding-model"></a>Aplicar um rótulo de retenção a um modelo de compreensão de documentos

Você pode aplicar facilmente um [rótulo de retenção](https://docs.microsoft.com/microsoft-365/compliance/retention) a um modelo de compreensão de documentos no Microsoft SharePoint Syntex.

Os rótulos de retenção permitem aplicar as configurações de retenção aos documentos que o modelo de compreensão de documentos identifica.  Por exemplo, você deseja que o seu modelo não só identifique todos os documentos de *Aviso de seguro* que são carregados na biblioteca de documentos, mas também aplique uma marca de retenção de *Negócios* a eles para que esses documentos não possam ser excluídos da biblioteca de documentos no período de tempo especificado (os próximos cinco meses, por exemplo).

Você pode aplicar um rótulo de retenção preexistente ao seu modelo de compreensão de documentos por meio das configurações de modelo na página inicial do seu modelo. 

> [!Important]
> Para que os rótulos de retenção estejam disponíveis para se aplicar ao seu modelo de compreensão de conteúdo, eles precisam ser [criados e publicados no Centro de Conformidade do Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/create-apply-retention-labels#how-to-create-and-publish-retention-labels).

## <a name="to-add-a-retention-label-to-a-document-understanding-model"></a>Para adicionar um rótulo de retenção a um modelo de compreensão de documentos

1. Na página inicial do modelo, selecione **Configurações de modelo**.</br>
2. Em **Configurações de modelo**, na seção **Segurança e conformidade**, selecione o menu **Rótulo de retenção** para ver uma lista de rótulos de retenção que estão disponíveis para serem aplicados ao modelo.</br>
 ![Menu rótulo de retenção](../media/content-understanding/retention-labels-menu.png)</br> 
3. Selecione o rótulo de retenção que você deseja aplicar ao modulo e, em seguida, selecione **Salvar**.</br>

Depois de aplicar o rótulo de retenção ao seu modelo, você pode aplicá-lo a:
- Nova biblioteca de documentos
- Biblioteca de documentos para a qual o modelo já foi aplicado
 
## <a name="apply-the-retention-label-to-a-document-library-to-which-the-model-is-already-applied"></a>Aplicar o rótulo de retenção a uma biblioteca de documentos para a qual o modelo já foi aplicado

Se seu modelo de compreensão de documentos já foi aplicado a uma biblioteca de documentos, você pode fazer o seguinte para sincronizar sua atualização de rótulo de retenção para aplicá-la à biblioteca de documentos:</br>

1. Na página inicial do seu modelo, na seção **Bibliotecas com esse modelo**, selecione a biblioteca de documentos à qual você deseja aplicar a atualização de rótulo de retenção. </br> 
2. Selecione **Sincronizar**. </br>
 ![Modelo de sincronização](../media/content-understanding/sync-model.png)</br> 


Depois de aplicar a atualização e sincronizá-la com o seu modelo, você pode confirmar se ela foi aplicada da seguinte maneira:

1. No centro de conteúdo, na seção **Bibliotecas com esse modelo**, clique na biblioteca à qual o modelo atualizado foi aplicado. </br>
2. No modo de exibição da biblioteca de documentos, selecione o ícone de informações para verificar as propriedades do modelo.</br>  
3. Na lista **Modelos ativos**, selecione o modelo atualizado.</br>
4. Na seção **Rótulo de retenção**, você verá o nome do rótulo de retenção aplicado.</br>


Na página de exibição do seu modelo na biblioteca de documentos, uma nova coluna do **Rótulo de retenção** será exibida.  Conforme seu modelo classifica os arquivos, eles os identifica como pertencentes ao seu tipo de conteúdo e os lista no modo de exibição de biblioteca, a coluna rótulo de retenção também exibirá o nome do rótulo de retenção que foi aplicado a ela por meio do modelo.


Por exemplo, todos os documentos de *Aviso de seguro* identificados pelo seu modelo também têm o rótulo de retenção *Negócios* aplicado a eles, impedindo que eles sejam excluídos da biblioteca de documentos por cinco meses. Se você tentar excluir o arquivo da biblioteca de documentos, o programa exibirá um erro informando que isso não é permitido por causa do rótulo de retenção aplicado.

## <a name="see-also"></a>Confira também
[Criar um classificador](create-a-classifier.md)

[Criar um extrator](create-an-extractor.md)

[Visão geral da Compreensão de Documentos](document-understanding-overview.md)

[Criar um modelo de processamento de formulário](create-a-form-processing-model.md)  
