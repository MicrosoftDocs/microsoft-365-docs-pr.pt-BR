---
title: Criar um classificador
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
description: Saiba como criar um classificador
ms.openlocfilehash: 29b2a4775bec12649c66b4cb4a07fe5f0fc93ae2
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294897"
---
# <a name="create-a-classifier-in-microsoft-sharepoint-syntex"></a>Criar um classificador no Microsoft SharePoint Syntex

O conteúdo deste artigo é para a visualização privada do projeto Cortex. [Saiba mais sobre o Project Cortex](https://aka.ms/projectcortex).

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL0R]  

</br>

Um classificador é um tipo de modelo que você pode usar para automatizar a identificação e a classificação de um tipo de documento. Por exemplo, talvez você queira identificar todos os documentos de *renovação de contrato* que são adicionados à sua biblioteca de documentos, como é mostrado na ilustração a seguir.

![Documento de renovação do contrato](../media/content-understanding/contract-renewal.png)

A criação de um classificador permite que você crie um novo [tipo de conteúdo do SharePoint](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) que será associado ao modelo.

Ao criar o classificador, você precisa criar *explicações* para definir o modelo. Isso permite que você observe dados comuns que você espera que encontrem consistentemente esse tipo de documento. 

Use exemplos do tipo de documento ("exemplos de arquivos") para "treinar" seu modelo para identificar arquivos que possuem o mesmo tipo de conteúdo.

Para criar um classificador, você precisa:
1. Nomeie seu modelo.
2. Adicione seus arquivos de exemplo.
3. Rotular seus arquivos de exemplo.
4. Criar uma explicação.
5. Teste seu modelo.

> [!NOTE]
> Enquanto o modelo usa um classificador para identificar e classificar tipos de documento, você também pode optar por extrair partes específicas de informações de cada arquivo identificado pelo modelo. Faça isso criando um **extrator** para adicionar ao seu modelo. Confira [criar um extrator](create-an-extractor.md).

## <a name="name-your-model"></a>Nomear seu modelo

A primeira etapa para criar seu modelo é dar um nome a ele:

1. No centro de conteúdo, selecione **novo**e, em seguida, **crie um modelo**.
2. No painel **novo documento entendendo o modelo** , no campo **nome** , digite o nome do modelo. Por exemplo, se você quiser identificar documentos de renovação de contrato, poderá nomear a *renovação do contrato*de modelo.
3. Escolha **Criar**. Isso cria uma home page para o modelo.</br>

    ![Home Page do modelo do classificador](../media/content-understanding/model-home.png)

Ao criar um modelo, você também cria um novo tipo de conteúdo do SharePoint. Um tipo de conteúdo do SharePoint representa uma categoria de documentos que têm características comuns e compartilham uma coleção de colunas ou propriedades de metadados para esse conteúdo específico. Os tipos de conteúdo do SharePoint são gerenciados por meio da [Galeria de tipos de conteúdo](https://support.microsoft.com/office/create-or-customize-a-site-content-type-27eb6551-9867-4201-a819-620c5658a60f). Para este exemplo, ao criar o modelo, você está criando um novo tipo de conteúdo de *renovação de contrato* .

Selecione **Configurações avançadas** se quiser mapear esse modelo para um tipo de conteúdo existente na Galeria de tipos de conteúdo do SharePoint para usar seu esquema. Observe que, embora você possa usar um tipo de conteúdo existente para aproveitar o esquema para ajudar com a identificação e a classificação, ainda precisará treinar seu modelo para extrair informações de arquivos que ele identifica.</br>

![Configurações avançadas](../media/content-understanding/advanced-settings.png)

## <a name="add-your-example-files"></a>Adicionar seus arquivos de exemplo

Na home page do modelo, adicione seus arquivos de exemplos que você precisará para ajudar a treinar o modelo para identificar o tipo de documento. </br>
</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4D0iX] 

</br>

> [!NOTE]
> Você deve usar os mesmos arquivos para o treinamento de classificador e [extrador](create-an-extractor.md). Você sempre tem a opção de adicionar mais tarde, mas normalmente adiciona um conjunto completo de arquivos de amostra. Rotule alguns para treinar seu modelo e testar os itens não rotulados restantes para avaliar a ADEQÜAÇÃO do modelo. 

Para o seu conjunto de treinamento, você deseja usar exemplos positivos e negativos:
- Exemplo positivo: documentos que representam o tipo de documento. Eles contêm cadeias de caracteres e informações que sempre serão desse tipo de documento.
- Exemplo negativo: documentos que não representam o tipo de documento. Essas são as cadeias de caracteres e informações que precisam estar presentes neste tipo de documento.

Certifique-se de usar pelo menos cinco exemplos positivos e pelo menos um exemplo negativo para treinar seu modelo.  Você deseja criar outros para testar o modelo após o processo de treinamento.

Para adicionar arquivos de exemplo:

1. Na página inicial do modelo, no bloco **biblioteca de amostra de compilação** , clique em **Adicionar arquivos**.
2. Na página **selecionar arquivos de exemplo para o modelo** , selecione seus arquivos de exemplo na biblioteca arquivos de exemplo no centro de conteúdo. Se você ainda não o carregou, clique em **carregar** para movê-los para a biblioteca de arquivos de amostra.
3. Depois de selecionar os arquivos de exemplo a serem usados para treinar o modelo, clique em **Adicionar**.

    ![Selecionar arquivos de exemplo](../media/content-understanding/select-sample.png) 

## <a name="label-your-example-files"></a>Rotular seus arquivos de exemplo

Após adicionar seus arquivos de exemplo, você precisa rotulá-los como exemplos positivos ou negativos.

1. Na página inicial do modelo, no bloco **classificar arquivos e executar treinamento** , clique em **treinar classificador**.
   Isso exibe a página de etiquetas que mostra uma listagem de seus arquivos de exemplo, com o primeiro arquivo visível no visualizador.
2. No visualizador na parte superior do primeiro arquivo de exemplo, você deve ver o texto perguntando se o arquivo é um exemplo do modelo que você acabou de criar. Se for um exemplo positivo, selecione **Sim**. Se for um exemplo negativo, selecione **não**.
3. Na lista de **exemplos rotulados** à esquerda, selecione arquivos adicionais que você deseja usar como exemplos e etiquete-los. 

    ![Home Page do classificador](../media/content-understanding/classifier-home-page.png) 


> [!NOTE]
> Rotule pelo menos cinco exemplos positivos e um exemplo negativo. 

## <a name="create-an-explanation"></a>Criar uma explicação

A próxima etapa é criar uma explicação na página de treinamento. Uma explicação ajuda o modelo a entender como reconhecer o documento. Por exemplo, os documentos de renovação de contrato sempre contêm uma *solicitação para uma cadeia de texto de divulgação adicional* .

> [!Note]
> Quando usada com extratores, uma explicação identifica a cadeia de caracteres que você deseja extrair do documento. 

Para criar uma explicação:

1. Na página inicial do modelo, selecione a guia **treinamento** para ir para a página de treinamento.
2. Na página treinar, na seção **arquivos treinados** , você verá uma lista dos arquivos de exemplo que você nomeou anteriormente. Selecione um dos arquivos positivos da lista e exibido no visualizador.
3. Na seção explicação, selecione **novo** e em **branco**.
4. Na página **criar uma explicação** :</br>
    a. Digite o **nome** (por exemplo, "bloqueio de revelação").</br>
    b. Selecione o **tipo**. Para o exemplo, selecione **lista de frases**, pois você adiciona uma cadeia de caracteres de texto.</br>
    c. Na caixa **Digite aqui** , digite a cadeia de caracteres. Para o exemplo, adicione "solicitação para divulgação adicional". Você pode selecionar diferenciar **maiúsculas de minúsculas** se a cadeia de caracteres precisa diferenciar maiúsculas de minúscula.</br>
    d. Clique em **Salvar**.

    ![Criar explicação](../media/content-understanding/explanation.png) 
    
 
5. O modelo agora verifica se a explicação que você criou era suficientemente boa para identificar os arquivos de exemplo rotulados restantes corretamente, como exemplos positivos e negativos. Na seção arquivos treinados, verifique a coluna **avaliação** após a conclusão do treinamento para ver os resultados. Os arquivos mostrarão um valor de **correspondência**, se as explicações que você criou forem suficientes para coincidir com o que foi rotulado como positivo ou negativo.

    ![Valor de correspondência](../media/content-understanding/match.png) 

Se você receber uma **incompatibilidade** nos arquivos rotulados, talvez seja necessário criar uma explicação adicional para fornecer ao modelo mais informações para identificar o tipo de documento. Se isso acontecer, clique no arquivo para obter mais informações sobre por que a incompatibilidade ocorreu.

## <a name="test-your-model"></a>Testar seu modelo

Se você recebeu uma correspondência em seus arquivos de amostra rotulados, agora você pode testar seu modelo em seus arquivos de exemplo não rotulados restantes.

1. Na página inicial do modelo, selecione a guia **teste** .  Isso executa o modelo em seus arquivos de amostra sem rótulo.
2. Na lista **arquivos de teste** , seus arquivos de exemplo são exibidos e mostra se o modelo prevê que eles sejam positivos ou negativos. Use essas informações para ajudar a determinar a eficácia do seu classificador na identificação de seus documentos.

    ![Teste de arquivos sem rótulo](../media/content-understanding/test-on-files.png) 

## <a name="see-also"></a>Confira também
[Criar um extrator](create-an-extractor.md)</br>
[Visão geral da compreensão do documento](document-understanding-overview.md)</br>
[Criar um modelo de processamento de formulários](create-a-form-processing-model.md)</br>
[Aplicar um modelo](apply-a-model.md) 
