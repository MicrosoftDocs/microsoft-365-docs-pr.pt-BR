---
title: Criar um extrator (versão prévia)
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
description: Saiba como criar um extrator
ms.openlocfilehash: 7219726fb385d0b67f7ee0614f5075ba226140ab
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950079"
---
# <a name="create-an-extractor-preview"></a>Criar um extrator (versão prévia)
> [!Note] 
> O conteúdo deste artigo é para a visualização privada do Project Cortex. [Saiba mais sobre o Project Cortex](https://aka.ms/projectcortex).

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL2G]

</br> 

Antes ou depois de criar um modelo de classificador para automatizar a identificação e a classificação de tipos de documento específicos, você pode optar por adicionar extratores ao modelo para extrair informações específicas desses documentos. Por exemplo, você pode querer que seu modelo não apenas identifique todos os documentos de *renovação de contrato* que são adicionados à sua biblioteca de documentos, mas também para exibir a data de *início do serviço* para cada documento como uma coluna na biblioteca de documentos.

Você precisa criar um extrator para cada entidade no documento que você deseja extrair. No nosso exemplo, queremos extrair a data de *início do serviço* para cada documento de *renovação de contrato* identificado pelo modelo. Queremos ver um modo de exibição na biblioteca de documentos de todos os documentos de *renovação de contrato* , com uma coluna que mostra o valor da data de início do serviço de cada documento.

> [!Note]
> Antes de criar um extrator, você precisa [adicionar os arquivos de exemplo](https://docs.microsoft.com/microsoft-365/contentunderstanding/create-a-classifier?view=o365-worldwide#add-your-example-files) necessários para ajudar a treinar o modelo para identificar as informações que você deseja extrair. Use os mesmos arquivos de exemplo usados para criar seu classificador.


## <a name="name-your-extractor"></a>Nomear seu extrator

1. Na home page do modelo, no bloco **criar e treinar extratores** , clique em **treinar extrator**.
2. Na tela **novo extrator de entidade** , digite o nome do extrator no campo **nome do novo extrator** . Por exemplo, podemos nomear a **data de início do serviço** de ti se quisermos extrair a data de início do serviço de cada documento de renovação de contrato.
3. Clique em **Criar**.

## <a name="add-a-label"></a>Adicionar um rótulo

A próxima etapa é identificar as informações que você deseja extrair nos seus arquivos de treinamento de exemplo.

A criação do extrator abrirá a página do extrator em que você verá uma lista de seus arquivos de exemplo, com o primeiro arquivo na lista exibido no visualizador.

1. No visualizador, selecione os dados que você deseja extrair dos arquivos. Por exemplo, se quiser extrair a data de *início do serviço*, você irá destacar o valor de data dele no primeiro arquivo (*segunda-feira, 14 de outubro de 2019*). Em seguida, clique em **Salvar**.  Você verá a exibição do valor para o arquivo na lista de exemplos rotulados abaixo da coluna **rótulo** .
2. Selecione **próximo arquivo** para salvamento automático e abra o próximo arquivo na lista no visualizador ou selecione **salvar** e selecione outro arquivo na lista **exemplos rotulados** .
3. No visualizador, repita as etapas 1 e 2 e faça isso até salvar o rótulo em cinco arquivos.

    ![Configurações avançadas](../media/content-understanding/select-service-start-date.png) 


### <a name="add-a-negative-example"></a>Adicionar um exemplo negativo

Semelhante à forma como você adicionaria um arquivo de exemplo negativo ao criar um classificador, precisa adicionar um exemplo negativo para o extrator. Para o nosso exemplo, ele deve ser um arquivo que não contém um valor de data de início do serviço.

1. Na lista **exemplos rotulados** , selecione um exemplo negativo.
2. No visualizador, na parte superior do artigo, selecione **nenhum rótulo presente**.
3. Clique em **Salvar**.
 
Depois de rotular cinco arquivos, uma faixa de notificação será exibida informando que você vai para o treinamento. Você pode optar por mais documentos ou avançar no treinamento. 

## <a name="add-an-explanation"></a>Adicionar uma explicação

Para nosso exemplo, vamos criar uma explicação que forneça uma dica sobre o próprio formato de entidade e variações que ela pode ter nos documentos de exemplo. Por exemplo, um valor de data pode estar em vários formatos diferentes, como:
- 10/14/2019
- 14 de outubro de 2019
- Segunda-feira, 14 de outubro de 2019
 

Para ajudar a identificar a *data de início do serviço* , você pode criar uma explicação de padrão.

1. Na seção explicação, selecione **novo**e digite um nome (por exemplo, *Data*).
2. Para o tipo, selecione **lista padrão**.
3. Para o valor, você precisa fornecer a variação de data, conforme aparecem nos arquivos de amostra. Por exemplo, se você tiver formatos de data que aparecem como 0/00/0000, você inseriria qualquer variação que possa aparecer em seus documentos, como:
    - 0/0/0000
    - 0/00/0000
    - 00/0/0000
    - 00/00/0000
4. Clique em **Salvar**.


### <a name="use-the-explanation-library"></a>Usar a biblioteca de explicação

Para criar explicações para coisas como datas, é muito mais fácil usar a biblioteca de explicação do que inserir manualmente todas as variações. A biblioteca de explicação é um conjunto de explicações predefinidas de frases e padrões. A biblioteca tenta fornecer todos os formatos de frases comuns ou listas de padrões, como datas, números de telefone, CEP e muitas outras. 

Para nosso exemplo de *data de início do serviço* , é mais eficiente usar a explicação previamente criada para *Data* na biblioteca de explicação:

1. Na **seção explicação**, * * selecione **novo**e selecione **na biblioteca explicação**.
2. Na biblioteca explicação, selecione **Data**. Você pode exibir todas as variações de data que serão reconhecidas.
3. Clique em **Adicionar**.</br>

    ![Biblioteca de explicação](../media/content-understanding/explanation-library.png) 

4. Na página **criar uma explicação** , as informações de *Data* da biblioteca explicação farão preenchimento automático dos campos. Clique em **Salvar**.</br>

    ![Biblioteca de explicação](../media/content-understanding/date-explanation-library.png) 

 
## <a name="train-the-model"></a>Treinar o modelo 

Salvar sua explicação começará o treinamento. Se o modelo tiver informações suficientes para extrair os dados dos arquivos de exemplo rotulados, você verá cada arquivo rotulado com **correspondência**.  

![Biblioteca de explicação](../media/content-understanding/match2.png) 

Se a explicação não tiver informações suficientes para localizar os dados que você deseja extrair, cada arquivo será rotulado com **incompatibilidade**. Você pode clicar nos arquivos incompatíveis para ver mais informações sobre o motivo pelo qual houve uma incompatibilidade.


## <a name="add-another-explanation"></a>Adicionar outra explicação

Em geral, a incompatibilidade é uma indicação de que a explicação fornecida não forneceu informações suficientes para extrair o valor de data de início do serviço para corresponder aos nossos arquivos rotulados. Talvez seja necessário editá-lo ou adicionar outra explicação.

Para o nosso exemplo, percebemos que a *data de início do serviço de sequência de texto de* sempre precede o valor real. Para ajudar a identificar a data de início do serviço, podemos criar uma explicação de frase.

1. Na seção explicação, selecione **novo**e digite um nome (por exemplo, *cadeia de caracteres de prefixo*).
2. Para o tipo, selecione **lista de frases**.
3. Use a *data de início do serviço* como o valor.
4. Clique em **Salvar**.

    ![Biblioteca de explicação](../media/content-understanding/prefix-string.png) 


## <a name="train-the-model"></a>Treinar o modelo

Salvar sua explicação iniciará o treinamento novamente, desta vez usando as duas explicações em nosso exemplo. Se o modelo tiver informações suficientes para extrair os dados dos arquivos de exemplo rotulados, você verá cada arquivo rotulado com **correspondência**. 

Se você receber **incompatibilidades** novamente em seus arquivos rotulados, talvez seja necessário criar outra explicação para fornecer o modelo mais informações para identificar o tipo de documento ou Confira como fazer alterações nos existentes.

## <a name="test-your-model"></a>Testar seu modelo

Se você recebeu uma correspondência em seus arquivos de exemplo rotulados, agora você pode testar seu modelo em seus arquivos de exemplo não rotulados restantes.

1. Na home page do modelo, clique na guia **testar** .  Isso executará o modelo em seus arquivos de exemplo sem rótulo.
2. Na lista de **arquivos de teste** , seus arquivos de exemplo serão exibidos e mostrarão se o modelo é capaz de extrair as informações necessárias. Você pode usar essas informações para ajudar a determinar a eficácia do seu classificador na identificação de seus documentos.

    ![Teste em seus arquivos](../media/content-understanding/test-filies-extractor.png) 

## <a name="see-also"></a>Confira também
  




