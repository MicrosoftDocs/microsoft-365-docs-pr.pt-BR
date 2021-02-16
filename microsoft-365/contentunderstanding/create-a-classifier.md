---
title: Criar um classificador
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Aprenda a criar um classificador
ms.openlocfilehash: bff23807fce18bf4a585dbb1ec47c1502ab686f6
ms.sourcegitcommit: 78f48304f990e969a052fe6536b2e8d6856e1086
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2021
ms.locfileid: "50242683"
---
# <a name="create-a-classifier-in-microsoft-sharepoint-syntex"></a>Criar um classificador no Microsoft SharePoint Syntex


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL0R]  

</br>

Um classificador é um tipo de modelo que você pode usar para automatizar a identificação e a classificação de um tipo de documento. Por exemplo, talvez você queira identificar toda os documentos de *Renovação de Contrato* que são adicionados à biblioteca de documentos, como o é mostrado na ilustração a seguir.

![Documento de Renovação de Contrato](../media/content-understanding/contract-renewal.png)

A criação de um classificador permite criar um novo [tipo de conteúdo do Microsoft Office SharePoint Online](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) que será associado ao modelo.

Ao criar o classificador, você precisa criar *explicações* para definir o modelo. Isso permite que você observe dados comuns que esperaria encontrar esse tipo de documento. 

Use exemplos do tipo de documento ("arquivos de exemplo") para "treinar" seu modelo para identificar arquivos que têm o mesmo tipo de conteúdo.

Para criar um classificador, você precisa:
1. Nomear seu modelo.
2. Adicionar os arquivos de exemplo.
3. Rotular os arquivos de exemplo.
4. Criar uma explicação.
5. Testar seu modelo.

> [!NOTE]
> Enquanto o modelo usa um classificador para identificar e classificar os tipos de documento, você também pode optar por extrair informações específicas de cada arquivo identificado pelo modelo. Para fazer isso, crie um **extrator** para adicionar ao seu modelo. Confira [Criar um extrator](create-an-extractor.md).

## <a name="name-your-model"></a>Nomeie seu modelo

A primeira etapa para criar seu modelo é dar um nome a ele:

1. No centro de conteúdo, selecione **Novo**, e depois **Criar um modelo**.
2. No painel **Novo modelo de compreensão de documentos**, no campo **Nome**, digite o nome do modelo. Por exemplo, se você deseja identificar documentos de renovação de contrato, nomeie o modelo como *Renovação de Contrato*.
3. Escolha **Criar**. Isso cria uma página inicial para o modelo.</br>

    ![Home page do modelo de classificação](../media/content-understanding/model-home.png)

Ao criar um modelo, você também cria um novo tipo de conteúdo de site. Um tipo de conteúdo representa uma categoria de documentos que tem características comuns e compartilha um conjunto de propriedades de colunas ou metadados para esse conteúdo específico. Os tipos de conteúdo do Microsoft Office SharePoint Online são gerenciados através da [Galeria de tipos de conteúdos](https://support.microsoft.com/office/create-or-customize-a-site-content-type-27eb6551-9867-4201-a819-620c5658a60f). Neste exemplo, quando você cria o modelo, está criando um novo tipo de conteúdo de *Renovação de Contrato*.

Selecione **Configurações avançadas** se desejar mapear esse modelo para um tipo de conteúdo empresarial existente na Galeria de Tipos de conteúdo do SharePoint para usar o esquema. Os tipos de conteúdo corporativo são armazenados no Hub de Tipo de Conteúdo no centro de administração do SharePoint e são agregados a todos os sites no locatário. Observe que, embora você possa usar um tipo de conteúdo existente para aproveitar o esquema para ajudar na identificação e classificação, ainda é necessário treinar o seu modelo para extrair informações de arquivos que ele identifica.</br>

![Configurações avançadas](../media/content-understanding/advanced-settings.png)

## <a name="add-your-example-files"></a>Adicionar arquivos de exemplo

Na página inicial do modelo, adicione os arquivos de exemplo que você precisa para ajudar a treinar o seu tipo de documento. </br>
</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4D0iX] 

</br>

> [!NOTE]
> Você deve usar os mesmos arquivos tanto para o classificador quanto para o [ Treinamento do extrator](create-an-extractor.md). Você tem a opção de adicionar mais tarde, mas normalmente adicionará um conjunto completo de arquivos de exemplo. Rotule alguns para treinar o seu modelo e testar as restantes não-rotulados para avaliar a adequação do modelo. 

Para seu conjunto de treinamento, você vai querer usar exemplos positivos e negativos:
- Exemplo positivo: documentos que representam o tipo de documento. Eles contêm cadeias de caracteres e informações que estarão sempre neste tipo de documento.
- Exemplo negativo: qualquer outro documento que não representa o documento que você deseja classificar. 

Use pelo menos cinco exemplos positivos e pelo menos um exemplo negativo para treinar o seu modelo.  Você vai precisar criar outras para testar o seu modelo após o processo de treinamento.

Para adicionar arquivos de exemplo:

1. Na página inicial do modelo, no bloco **Adicionar arquivos de exemplo**, clique em **Adicionar arquivos**.
2. Na página **selecione arquivos de exemplo para sua página de modelo**, selecione os arquivos de exemplo da biblioteca Arquivos de treinamento no centro de conteúdo. Se você ainda não tiver carregado esses arquivos, clique em **Carregar** para copiá-los para a Biblioteca de arquivos de treinamento.
3. Depois de selecionar os arquivos de exemplo que deseja usar para treinar o modelo, clique em **Adicionar**.

    ![Selecione arquivos de exemplo](../media/content-understanding/select-sample.png) 

## <a name="label-your-example-files"></a>Rotule os arquivos de exemplo

Depois de adicionar os arquivos de exemplo, é necessário rotulá-los como exemplos positivos ou negativos.

1. A partir da página inicial do modelo, no bloco **Classificar arquivos e executar treinamento**, clique em **Treinar classificador**.
   Isso exibe a página de etiquetas que mostra uma lista de arquivos de exemplo, com o primeiro arquivo visível no visualizador.
2. No visualizador, na parte superior do primeiro arquivo de exemplo, você deve ver o texto perguntando se o arquivo é um exemplo do modelo que você acabou de criar. Se for um exemplo positivo, selecione **Sim**. Se for um exemplo negativo, selecione **Não**.
3. Na lista de **Exemplos rotulados** à esquerda, selecione arquivos adicionais que você deseja usar como exemplos e etiquete-los. 

    ![Página inicial do classificador](../media/content-understanding/classifier-home-page.png) 


> [!NOTE]
> Rotule pelo menos cinco exemplos positivos. Você também deve rotular pelo menos um exemplo negativo. 

## <a name="create-an-explanation"></a>Criar uma explicação

A próxima etapa é criar uma explicação na Página de treinamento. Uma explicação ajuda o modelo a entender como reconhecer o documento. Por exemplo, os documentos de Renovação de Contrato sempre contêm um cadeia de texto de *Solicitação de divulgação*.

> [!Note]
> Quando usado com extratores, uma explicação identifica a cadeia que você deseja extrair do documento. 

Para criar uma explicação:

1. Na página inicial do modelo, selecione a guia **Treinar** para ir para a página de treinamento.
2. Na página Treinar, na seção **Arquivos treinados**, você verá uma lista dos arquivos de exemplo que você rotulou anteriormente. Selecione um dos arquivos positivos na lista, e ele será exibido no visualizador.
3. Na seção Explicação, selecione **Nova** e, em seguida, **Em branco**.
4. Na página **Criar uma explicação**:</br>
    a. Digite o **Nome** (por exemplo, "Bloqueio de Divulgação").</br>
    b. Selecione o **Tipo**. Para o exemplo, selecione **Lista de frases**, já que você adiciona uma cadeia de texto.</br>
    c. Na caixa **Digite aqui**, digite a cadeia. Para o exemplo, adicione "Solicitar divulgação adicional". Você pode selecionar **Diferenciar maiúsculas de minúsculas** se a cadeia precisar diferenciar maiúsculas de minúsculas.</br>
    d. Clique em **Salvar**.

    ![Criar explicação](../media/content-understanding/explanation.png) 
    
5. O Centro de Conteúdo agora verifica se a explicação que você criou está completa o suficiente para identificar corretamente os demais arquivos de exemplo rotulados, como exemplos positivos e negativos. Na seção Arquivos Treinados, marque a coluna **Avaliação** após concluir o treinamento para ver os resultados. Os arquivos mostram um valor de **Correspondência**, se as explicações que você criou foram o suficiente para corresponder ao que foi rotulado como positivo ou negativo.

    ![Valor de correspondência](../media/content-understanding/match.png) 

Se você receber uma **incompatibilidade** nos arquivos rotulados, talvez seja necessário criar uma explicação adicional para fornecer informações sobre o modelo ao tipo de documento. Se isso acontecer, clique no arquivo para saber mais sobre o motivo pelo qual a incompatibilidade ocorreu.

## <a name="test-your-model"></a>Testar seu modelo

Se você recebeu uma correspondência em seus arquivos de exemplo rotulados, agora você pode testar seu modelo em seus arquivos de exemplo não rotulados restantes que o modelo não tenha visto anteriormente.  Isso é opcional, mas uma etapa útil para avaliar a "adequação" ou prontidão do modelo antes de usá-lo, testando-o em arquivos que o modelo nunca viu antes.

1. Na página inicial do modelo, selecione a guia **Testar**.  Isso executará o modelo em seus arquivos de exemplo não rotulados.
2. Na lista **Arquivos de teste**, os arquivos de exemplo são exibidos e mostram se o modelo os previu como positivos ou negativos. Use essas informações para ajudá-lo a determinar a eficácia do seu classificador na identificação de seus documentos.

    ![Teste de arquivos não-rotulados](../media/content-understanding/test-on-files.png) 

## <a name="see-also"></a>Confira também
[Criar um extrator](create-an-extractor.md)

[Visão geral sobre Compreensão de Documentos](document-understanding-overview.md).

[Tipos de explicação](explanation-types-overview.md)

[Aplicar um modelo](apply-a-model.md) 

[Modo de Acessibilidade do SharePoint Syntex](accessibility-mode.md)
