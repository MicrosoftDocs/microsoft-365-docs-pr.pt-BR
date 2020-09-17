---
title: Criar um classificador (visualização)
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
description: Saiba como criar um classificador
ms.openlocfilehash: 718d904ca397d43644c578ff6f589b5e5b043e5a
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950151"
---
# <a name="create-a-classifier-preview"></a>Criar um classificador (visualização)

> [!Note] 
> O conteúdo deste artigo é para a visualização privada do Project Cortex. [Saiba mais sobre o Project Cortex](https://aka.ms/projectcortex).

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL0R]  

</br>

Um classificador é um tipo de modelo que automatiza a identificação e a classificação de um tipo de documento. Por exemplo, talvez você queira identificar todos os documentos de *renovação de contrato* que são adicionados à sua biblioteca de documentos, como o seguinte.

![Documento de renovação do contrato](../media/content-understanding/contract-renewal.png)

A criação de um classificador criará um novo [tipo de conteúdo do SharePoint](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) que será associado ao modelo.

Ao criar o classificador, você precisa criar *explicações* que ajudam a definir o modelo, observando dados comuns que você espera localizar de forma consistente para esse tipo de documento. 

Você usa exemplos do tipo de documento ("arquivos de exemplo") para ajudar a "treinar" seu modelo para identificar arquivos que possuem o mesmo tipo de conteúdo.

Para criar um classificador, você precisa:
1. Nomear seu modelo
2. Adicionar seus arquivos de exemplo
3. Rotular seus arquivos de exemplo
4. Criar uma explicação
5. Testar seu modelo 

> [!Note]
> Embora um classificador seja usado pelo modelo para identificar e classificar tipos de documento, você também pode optar por extrair partes específicas de informações de cada arquivo identificado pelo modelo. Você faz isso criando um **extrator** para adicionar ao seu modelo, e isso é descrito em [criar um extrator](create-an-extractor.md).

## <a name="name-your-model"></a>Nomear seu modelo

A primeira etapa é criar seu modelo no seu centro de conteúdo dando a ele um nome:

1. No centro de conteúdo, clique em **novo**e em **criar um modelo**.
2. No painel **novo documento entendendo o modelo** , no campo **nome** , digite o nome do modelo. No nosso exemplo, se quisermos identificar documentos de renovação de contrato, podemos nomear essa *renovação de contrato*de modelo.
3. Clique em **Criar**. Isso criará uma home page para o modelo.</br>

    ![Home Page do modelo do classificador](../media/content-understanding/model-home.png)

Ao criar um modelo, você está criando um novo tipo de conteúdo do SharePoint. Um tipo de conteúdo do SharePoint representa uma categoria de documentos que têm características comuns e compartilham uma coleção de colunas ou propriedades de metadados para esse conteúdo específico. Os tipos de conteúdo do SharePoint são gerenciados por meio da [Galeria de tipos de conteúdo](). No nosso exemplo, quando criamos o modelo, criaremos um novo tipo de conteúdo de *renovação de contrato* .

Selecione **Configurações avançadas** se quiser mapear esse modelo para um tipo de conteúdo existente na Galeria de tipos de conteúdo do SharePoint para usar seu esquema. Observe que, embora você possa usar um tipo de conteúdo existente para aproveitar o esquema para ajudar com a identificação e a classificação, ainda será necessário treinar o modelo para extrair informações de arquivos que ele identifica.</br>

![Configurações avançadas](../media/content-understanding/advanced-settings.png)

## <a name="add-your-example-files"></a>Adicionar seus arquivos de exemplo

Na home page do modelo, você pode adicionar seus arquivos de exemplos, será necessário para ajudar a treinar o modelo para identificar o tipo de documento. </br>
</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4D0iX] 

</br>

> [!Note]
> Os mesmos arquivos devem ser usados para o treinamento de classificador e [extrador](create-an-extractor.md). Você sempre tem a opção de adicionar mais tarde, mas normalmente deve adicionar um conjunto completo de arquivos de exemplo. Você será rotulado algumas para treinar seu modelo e testar os itens não rotulados restantes para avaliar a ADEQÜAÇÃO do modelo. 

Para seu conjunto de treinamento, você vai querer usar exemplos positivos e exemplos negativos:
- Exemplo positivo: documentos que representam o tipo de documento. Eles contêm cadeias de caracteres e informações que sempre serão desse tipo de documento.
- Exemplo negativo: documentos que não representam o tipo de documento.  Estão faltando cadeias de caracteres e informações que precisam estar presentes neste tipo de documento.

Você vai querer usar pelo menos cinco exemplos positivos e um dos exemplos negativos para treinar seu modelo.  Você deverá ter outros para testar seu modelo após o treinamento.

Para adicionar arquivos de exemplo:

1. Na home page do modelo, no bloco **biblioteca de amostra de compilação** , clique em **Adicionar arquivos**.
2. Na página **selecionar arquivos de exemplo para o modelo** , selecione seus arquivos de exemplo na biblioteca arquivos de exemplo no centro de conteúdo. Se você ainda não o tiver carregado, poderá optar por carregá-los agora clicando em **carregar** para movê-los para a biblioteca de arquivos de exemplo.
3. Depois de selecionar os arquivos de exemplo a serem usados para treinar o modelo, clique em **Adicionar**.

    ![Selecionar arquivos de exemplo](../media/content-understanding/select-sample.png) 

## <a name="label-your-example-files"></a>Rotular seus arquivos de exemplo

Após adicionar seus arquivos de exemplo, você precisa rotulá-los como exemplos positivos ou como exemplos negativos.

1. Na home page do modelo, no bloco **classificar arquivos e executar treinamento** , clique em **treinar classificador**.
   Isso exibirá a página de etiquetas que mostra uma listagem de seus arquivos de exemplo, com o primeiro arquivo visível no visualizador.
2. No visualizador, na parte superior do primeiro arquivo de exemplo, você verá um texto perguntando se o arquivo é um exemplo do modelo que você acabou de criar. Se for um exemplo positivo, selecione **Sim**. Se for um exemplo negativo, selecione **não**.
3. Na lista de **exemplos rotulados** à esquerda, selecione arquivos adicionais que você deseja usar como exemplos e etiquete-os também. 

    ![Home Page do modelo do classificador](../media/content-understanding/classifier-home-page.png) 


> [!Note]
> Rotule pelo menos cinco exemplos positivos e um exemplo negativo. 

## <a name="create-an-explanation"></a>Criar uma explicação

A próxima etapa é criar uma explicação na página de treinamento.  Uma explicação é uma dica ou pista para ajudar o modelo a entender como reconhecer este documento. Por exemplo, nossos documentos de renovação de contrato sempre contêm uma *solicitação para uma cadeia de texto de divulgação adicional* .

> [!Note]
> Quando usada com extratores, uma explicação é usada para identificar a cadeia de caracteres que você deseja extrair do documento. 

Para criar uma explicação:

1. Na página inicial do modelo, clique na guia **treinamento** para ir para a página de treinamento.
2. Na página treinamento, na seção **arquivos treinados** , você verá uma lista dos arquivos de exemplo que você tinha rotulado anteriormente. Selecione um dos arquivos positivos da lista e ele será exibido no visualizador.
3. Na seção explicação, clique em **novo**e em **em branco**.
4. Na página **criar uma explicação** :</br>
    a. Digite o **nome** (por exemplo, "bloqueio de revelação").</br>
    b. Selecione o **tipo**. No nosso exemplo, selecionaremos a **lista de frases**, já que estamos adicionando uma cadeia de caracteres de texto.</br>
    c. Na caixa **Digite aqui** , digite a cadeia de caracteres.  No nosso exemplo, adicionaremos "solicitação para divulgação adicional". Você pode selecionar diferenciar **maiúsculas de minúsculas** se a cadeia de caracteres precisa diferenciar maiúsculas de minúscula.</br>
    d. Clique em **Salvar**.

    ![Criar explicação](../media/content-understanding/explanation.png) 
    
 
5.  O modelo agora verificará se a explicação que você criou era suficientemente boa para identificar seus arquivos de exemplo rotulados remanescentes corretamente como exemplos positivos e negativos. Na seção arquivos treinados, verifique a coluna **avaliação** após a conclusão do treinamento para ver os resultados.  Os arquivos mostrarão um valor de **correspondência** se a explicação que você criou for suficiente para coincidir com o que foi rotulado como (positivo ou negativo).

    ![Criar explicação](../media/content-understanding/match.png) 

Se você receber uma **incompatibilidade** nos arquivos rotulados, talvez seja necessário criar uma explicação adicional para fornecer ao modelo mais informações para identificar o tipo de documento. Você pode clicar no arquivo para obter mais informações sobre por que a incompatibilidade ocorreu.

## <a name="test-your-model"></a>Testar seu modelo

Se você recebeu uma correspondência em seus arquivos de exemplo rotulados, agora você pode testar seu modelo em seus arquivos de exemplo não rotulados restantes.

1. Na home page do modelo, clique na guia **testar** .  Isso executará o modelo em seus arquivos de exemplo sem rótulo.
2. Na lista de **arquivos de teste** , seus arquivos de exemplo serão exibidos e mostrará se o modelo prevê que eles são positivos ou negativos. Você pode usar essas informações para ajudar a determinar a eficácia do seu classificador na identificação de seus documentos.

    ![Teste de arquivos sem rótulo](../media/content-understanding/test-on-files.png) 



## <a name="see-also"></a>Confira também
[Criar um extrator](create-an-extractor.md)</br>
[Visão geral da compreensão do documento](document-understanding-overview.md)</br>
[Criar um modelo de processamento de formulários](create-a-form-processing-model.md)</br>
[Aplicar um modelo](apply-a-model.md) 




