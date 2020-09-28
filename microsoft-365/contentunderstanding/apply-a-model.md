---
title: Aplicar um documento entendendo o modelo a uma biblioteca de documentos
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Saiba como aplicar um modelo publicado a uma biblioteca de documentos do SharePoint
ms.openlocfilehash: c693fa08bf3103eca01e01774e8f8b1d9e783b07
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295485"
---
# <a name="apply-a-document-understanding-model-in-microsoft-sharepoint-syntex"></a>Aplicar um documento entendendo o modelo no Microsoft SharePoint Syntex

O conteúdo deste artigo refere-se à visualização privada do projeto Cortex. [Saiba mais sobre o Project Cortex](https://aka.ms/projectcortex).

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

Após publicar seu documento entendendo o modelo, você pode aplicá-lo a uma biblioteca de documentos do SharePoint em seu locatário do Microsoft 365.

> [!NOTE]
> Você só pode aplicar o modelo às bibliotecas de documentos às quais você tem acesso.


## <a name="apply-your-model-to-a-document-library"></a>Aplique o modelo a uma biblioteca de documentos.

Para aplicar o modelo a uma biblioteca de documentos do SharePoint:

1. Na página inicial do modelo, no bloco **aplicar modelo para bibliotecas** , selecione **Publicar modelo**. Ou você pode selecionar  **+ Adicionar biblioteca** na seção **bibliotecas com este modelo** . </br>

    ![Adicionar modelo à biblioteca](../media/content-understanding/apply-to-library.png)</br>

2. Selecione o site do SharePoint que contém a biblioteca de documentos à qual você deseja aplicar o modelo. Se o site não aparecer na lista, use a caixa Pesquisar para encontrá-lo.</br>

    ![Selecionar um site](../media/content-understanding/site-search.png)</br>

    > [!NOTE]
    > Você deve ter permissões de *lista* ou *Editar* direitos para a biblioteca de documentos à qual você está aplicando o modelo.</br>

3. Depois de selecionar o site, selecione a biblioteca de documentos à qual você deseja aplicar o modelo. No exemplo, selecione a biblioteca de documentos *documentos* do site de *acompanhamento de casos da Contoso* .</br>

    ![Selecionar uma biblioteca de documentos](../media/content-understanding/select-doc-library.png)</br>

4. Como o modelo é associado a um tipo de conteúdo, quando você o aplica à biblioteca, ele cria um modo de exibição para o tipo de conteúdo com os rótulos que você extraiu mostrando como colunas. Este modo de exibição é o modo de exibição padrão da biblioteca por padrão, mas você pode optar por não ser o modo de exibição padrão selecionando **Configurações avançadas** e desmarcando **definir este novo modo de exibição como padrão**.</br>

    ![Exibição de biblioteca](../media/content-understanding/library-view.png)</br>

5. Selecione **Adicionar** para aplicar o modelo à biblioteca. 
6. Na página inicial do modelo, na seção **bibliotecas com este modelo** , você deve ver a URL do site do SharePoint listado.</br>

    ![Biblioteca selecionada](../media/content-understanding/selected-library.png)</br>

7. Vá para a biblioteca de documentos e verifique se você está no modo de exibição de biblioteca de documentos do modelo. Observe que, se você selecionar o botão de informações ao lado do nome da biblioteca de documentos, uma mensagem notará que o modelo foi aplicado à biblioteca de documentos.

    ![Exibição de informações](../media/content-understanding/info-du.png)</br> 


Depois de aplicar o modelo à biblioteca de documentos, você pode começar a carregar documentos no site e ver os resultados.

O modelo identifica qualquer arquivo com o tipo de conteúdo associado ao modelo e o lista no modo de exibição. Se o modelo tiver qualquer extrador, o modo de exibição exibirá colunas para os dados que você está extraindo de cada arquivo.

### <a name="apply-the-model-to-files-already-in-the-document-library"></a>Aplicar o modelo aos arquivos que já estão na biblioteca de documentos

Enquanto um modelo aplicado processa todos os arquivos carregados na biblioteca de documentos após a aplicação, você também pode fazer o seguinte para executar o modelo em arquivos que já existem na biblioteca de documentos antes do modelo que está sendo aplicado:

1. Na biblioteca de documentos, selecione os arquivos que você deseja que sejam processados pelo modelo.
2. Depois de selecionar seus arquivos, **classificar e extrair** aparecerão na faixa de opções da biblioteca de documentos. Selecione **classificar e extrair**.
3. Os arquivos selecionados serão adicionados à fila para serem processados.

      ![Classificar e extrair](../media/content-understanding/extract-classify.png)</br> 

## <a name="see-also"></a>Confira também
[Criar um classificador](create-a-classifier.md)</br>
[Criar um extrator](create-an-extractor.md)</br>
[Visão geral da compreensão do documento](document-understanding-overview.md)</br>
[Criar um modelo de processamento de formulários](create-a-form-processing-model.md)  
