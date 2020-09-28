---
title: Criar um extrator
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
description: Saiba como criar um extrator no Microsoft SharePoint Syntex.
ms.openlocfilehash: 740df6769b3a1675e4e1691f84d164312b15567c
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295451"
---
# <a name="create-an-extractor-preview"></a>Criar um extrator (versão prévia)

O conteúdo deste artigo é para a visualização privada do projeto Cortex. [Saiba mais sobre o Project Cortex](https://aka.ms/projectcortex).

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL2G]

</br> 

Antes ou depois de criar um modelo de classificador para automatizar a identificação e a classificação de tipos de documento específicos, você pode optar por adicionar extratores ao modelo para extrair informações específicas desses documentos. Por exemplo, você pode querer que seu modelo não apenas identifique todos os documentos de *renovação de contrato* adicionados à sua biblioteca de documentos, mas também para exibir a data de *início do serviço* para cada documento como uma coluna na biblioteca de documentos.

Você precisa criar um extrator para cada entidade no documento que você deseja extrair. No exemplo, você deseja extrair a data de *início do serviço* para cada documento de *renovação de contrato* identificado pelo modelo. Isso deve acontecer quando você quiser ver um modo de exibição na biblioteca de documentos de todos os documentos de *renovação de contrato* com uma coluna mostrando o valor de data de início do serviço para cada documento.

> [!NOTE]
> Antes de criar um extrator, você precisa [adicionar seus arquivos de exemplo](https://docs.microsoft.com/microsoft-365/contentunderstanding/create-a-classifier#add-your-example-files) para ajudar a treinar o modelo para identificar as informações que você deseja extrair. Use os mesmos arquivos de exemplo usados para criar seu classificador.

## <a name="name-your-extractor"></a>Nomear seu extrator

1. Na página inicial do modelo, no bloco **criar e treinar extratores** , clique em **treinar extrator**.
2. Na tela **novo extrator de entidade** , digite o nome do extrator no campo **nome do novo extrator** . Por exemplo, nomeie a **data de início do serviço** , se você quiser extrair a data de início do serviço de cada documento de renovação de contrato.
3. Clique em **Criar**.

## <a name="add-a-label"></a>Adicionar um rótulo

A próxima etapa é rotular as informações que você deseja extrair em seus arquivos de treinamento de amostra.

A criação do extrator abre a página do extrator. Veja aqui uma lista de seus arquivos de exemplo, com o primeiro arquivo na lista exibida no visualizador.

1. No visualizador, selecione os dados que você deseja extrair dos arquivos. Por exemplo, se você quiser extrair a *data de início do serviço*, destaque o valor de data no primeiro arquivo (*segunda-feira, 14 de outubro de 2019*). e clique em **salvar**.  Você deve ver o valor exibir do arquivo na lista de exemplos rotulados, abaixo da coluna **rótulo** .
2. Selecione **Avançar arquivo** para salvar automaticamente e abra o próximo arquivo na lista no visualizador. Ou selecione **salvar** e, em seguida, selecione outro arquivo na lista **exemplos rotulados** .
3. No visualizador, repita as etapas 1 e 2 e, em seguida, repita até salvar o rótulo em todos os cinco arquivos.

    ![Configurações avançadas](../media/content-understanding/select-service-start-date.png) 

### <a name="add-a-negative-example"></a>Adicionar um exemplo negativo

Semelhante à forma como você adiciona um arquivo de amostra negativo ao criar um classificador, você precisa adicionar uma amostra negativa para o extrator. Deve ser um arquivo que não contenha um valor de data de "início de serviço".

1. Na lista **exemplos rotulados** , selecione um exemplo negativo.
2. No visualizador na parte superior do artigo, selecione **nenhum rótulo presente**.
3. Clique em **Salvar**.
 
Depois de rotular cinco arquivos, uma faixa de notificação é exibida informando que você vá para o treinamento. Você pode optar por mais documentos ou avançar no treinamento. 

## <a name="add-an-explanation"></a>Adicionar uma explicação

Para o exemplo, você cria uma explicação que fornece uma dica sobre o próprio formato de entidade e variações que ela pode ter nos documentos de amostra. Por exemplo, um valor de data pode estar em vários formatos diferentes, como:
- 10/14/2019
- 14 de outubro de 2019
- Segunda-feira, 14 de outubro de 2019
 

Para ajudar a identificar a *data de início do serviço* , você cria uma explicação de padrão.

1. Na seção explicação, selecione **novo** e digite um nome (por exemplo, *Data*).
2. Em tipo, selecione **lista padrão**.
3. Para o valor, forneça a variação de data, conforme aparecem nos arquivos de exemplo. Por exemplo, se você tiver formatos de data que aparecem como 0/00/0000, você insere qualquer variação que aparece em seus documentos, como:
    - 0/0/0000
    - 0/00/0000
    - 00/0/0000
    - 00/00/0000
4. Selecione **Salvar**.

### <a name="use-the-explanation-library"></a>Usar a biblioteca de explicação

Para criar explicações para itens como datas, é mais fácil usar a biblioteca de explicação do que inserir manualmente todas as variações. A biblioteca de explicação é um conjunto de explicações predefinidas de frases e padrões. A biblioteca fornece todos os formatos para frases comuns ou listas de padrões, como datas, números de telefone, CEP, etc. 

Para o exemplo de *data de início do serviço* , é mais eficiente usar a explicação previamente criada para *Data* na biblioteca de explicação:

1. Na **seção explicação**, selecione **novo**e selecione **na biblioteca explicação**.
2. Na biblioteca explicação, selecione **Data**. Você pode exibir todas as variações de data que são reconhecidas.
3. Clique em **Adicionar**.</br>

    ![Biblioteca de explicação](../media/content-understanding/explanation-library.png) 

4. Na página **criar uma explicação** , as informações de *Data* da biblioteca explicação automática preencherão os campos. Selecione **Salvar**.</br>

    ![Data](../media/content-understanding/date-explanation-library.png) 

## <a name="train-the-model"></a>Treinar o modelo 

Salvando sua explicação inicie o treinamento. Se o modelo tiver informações suficientes para extrair os dados dos arquivos de exemplo rotulados, você verá cada arquivo rotulado com **correspondência**.  

![Match](../media/content-understanding/match2.png) 

Se a explicação não tiver informações suficientes para localizar os dados que você deseja extrair, cada arquivo será rotulado com **incompatibilidade**. Você pode clicar nos arquivos **incompatíveis** para ver mais informações sobre o motivo pelo qual houve uma incompatibilidade.


## <a name="add-another-explanation"></a>Adicionar outra explicação

Em geral, a incompatibilidade é uma indicação de que a explicação fornecida não forneceu informações suficientes para extrair o valor de data de início do serviço para corresponder aos nossos arquivos rotulados. Talvez seja necessário editá-lo ou adicionar outra explicação.

Para o exemplo, observe que a *data de início do serviço de sequência de texto de* sempre precede o valor real. Para ajudar a identificar a data de início do serviço, você precisa de OT criar uma explicação de frase.

1. Na seção explicação, selecione **novo**e digite um nome (por exemplo, *cadeia de caracteres de prefixo*).
2. Para o tipo, selecione **lista de frases**.
3. Use a *data de início do serviço* como o valor.
4. Selecione **Salvar**.

    ![Cadeia de caracteres de prefixo](../media/content-understanding/prefix-string.png) 

## <a name="train-the-model-again"></a>Treine o modelo novamente

Salvar a explicação inicia o treinamento novamente, desta vez usando as duas explicações no exemplo. Se o modelo tiver informações suficientes para extrair os dados dos arquivos de amostra rotulados, você verá cada arquivo rotulado com **correspondência**. 

Se você receber **incompatibilidades** novamente em seus arquivos rotulados, provavelmente precisará criar outra explicação para fornecer o modelo mais informações para identificar o tipo de documento ou considere fazer alterações no modelo de amostra.

## <a name="test-your-model"></a>Testar seu modelo

Se você receber uma correspondência em seus arquivos de amostra rotulados, agora você pode testar o modelo nos arquivos de amostra não rotulados restantes.

1. Na página inicial do modelo, clique na guia **testar** .  Isso executa o modelo em seus arquivos de amostra sem rótulo.
2. Na lista **testar arquivos** , seus arquivos de exemplo são exibidos para mostrar se o modelo é capaz de extrair as informações necessárias. Use essas informações para ajudar a determinar a eficácia do seu classificador na identificação de seus documentos.

    ![Teste em seus arquivos](../media/content-understanding/test-filies-extractor.png) 
