---
title: Aplicar um documento entendendo o modelo a uma biblioteca de documentos (visualização)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Saiba como aplicar um modelo publicado a uma biblioteca de documentos do SharePoint.
ms.openlocfilehash: 8a4931f4b7a936caeb99d7f8c07deefdac62919b
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950243"
---
# <a name="apply-a-document-understanding-model-preview"></a>Aplicar um documento entendendo o modelo (visualização)

> [!Note] 
> O conteúdo deste artigo é para a visualização privada do Project Cortex. [Saiba mais sobre o Project Cortex](https://aka.ms/projectcortex).

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

Após publicar seu documento entendendo o modelo, você pode aplicá-lo a uma biblioteca de documentos do SharePoint em seu locatário do Microsoft 365.

> [!Note]
> Você só poderá aplicar o modelo às bibliotecas de documentos às quais você tem acesso.


## <a name="apply-your-model-to-a-document-library"></a>Aplique o modelo a uma biblioteca de documentos.

Para aplicar o modelo a uma biblioteca de documentos do SharePoint:

1. Na home page do modelo, no bloco **aplicar modelo para bibliotecas** , selecione **Publicar modelo**. Ou você pode selecionar  **+ Adicionar biblioteca** na seção **bibliotecas com este modelo** . </br>

    ![Adicionar modelo à biblioteca](../media/content-understanding/apply-to-library.png)</br>

2. Em seguida, você pode selecionar o site do SharePoint que contém a biblioteca de documentos à qual você deseja aplicar o modelo. Se o site não aparecer na lista, use a caixa Pesquisar para encontrá-lo.</br>

    ![Selecionar um site](../media/content-understanding/site-search.png)</br>

    > [!Note]
    > Você deve ter permissões de *lista* ou *Editar* direitos para a biblioteca de documentos à qual você está aplicando o modelo.</br>

3. Depois de selecionar o site, você precisará selecionar a biblioteca de documentos à qual você deseja aplicar o modelo. No exemplo, estamos selecionando *a biblioteca de documentos Documents* no site de acompanhamento de *casos da Contoso* .</br>

    ![Selecionar uma biblioteca de documentos](../media/content-understanding/select-doc-library.png)</br>

4. Como o modelo é associado a um tipo de conteúdo, quando você o aplica à biblioteca, ele criará um modo de exibição para o tipo de conteúdo com os rótulos que você extraiu mostrando como colunas. Este modo de exibição será o modo de exibição padrão da biblioteca por padrão, mas você pode optar por não ser o modo de exibição padrão selecionando **Configurações avançadas** e desmarcando **definir este novo modo de exibição como padrão**.</br>

    ![Exibição de biblioteca](../media/content-understanding/library-view.png)</br>

5. Selecione **Adicionar** para aplicar o modelo à biblioteca. 
6. Na página inicial do modelo, na seção **bibliotecas com este modelo** , você verá a URL para o site do SharePoint listado.</br>

    ![Exibição de biblioteca](../media/content-understanding/selected-library.png)</br>

7. Vá para a biblioteca de documentos e verifique se você está no modo de exibição de biblioteca de documentos do modelo. Você verá que, se você selecionar o botão de informações ao lado do nome da biblioteca de documentos, uma mensagem notará que o modelo foi aplicado à biblioteca de documentos.

    ![Exibição de biblioteca](../media/content-understanding/info-du.png)</br> 


Depois de aplicar o modelo à biblioteca de documentos, você pode começar a carregar documentos no site e ver os resultados.

O modelo identificará todos os arquivos com o tipo de conteúdo associado ao modelo e os listará em seu modo de exibição. Se o modelo tiver quaisquer extratores, o modo de exibição exibirá colunas para os dados que você está extraindo de cada arquivo.

### <a name="apply-the-model-to-files-already-in-the-document-library"></a>Aplicar o modelo aos arquivos que já estão na biblioteca de documentos

Embora um modelo aplicado processe todos os arquivos carregados na biblioteca de documentos após a aplicação, você também pode fazer o seguinte para executar o modelo em arquivos que já existiam na biblioteca de documentos antes do modelo que está sendo aplicado:

1. Na biblioteca de documentos, selecione os arquivos que você deseja que sejam processados pelo modelo.
2. Depois de selecionar seus arquivos, **classificar e extrair** aparecerão na faixa de opções da biblioteca de documentos. Selecione **classificar e extrair**.
3. Os arquivos selecionados serão adicionados à fila para serem processados.

      ![Classificar e extrair](../media/content-understanding/extract-classify.png)</br> 





## <a name="see-also"></a>Confira também
[Criar um classificador](create-a-classifier.md)</br>
[Criar um extrator](create-an-extractor.md)</br>
[Visão geral da compreensão do documento](document-understanding-overview.md)</br>
[Criar um modelo de processamento de formulários](create-a-form-processing-model.md)  




