---
title: Tipos de explicação
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: Saiba mais sobre tipos de explicação no Microsoft SharePoint Syntex
ms.openlocfilehash: 4fe13a35757807e08638f68259ccd24a59a97460
ms.sourcegitcommit: 0f48beaca3afa4df12d41847014975d50a4ebe7d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2020
ms.locfileid: "48338656"
---
# <a name="introduction-to-explanation-types"></a>Introdução aos tipos de explicação

As explicações são usadas para ajudar a definir as informações que você deseja rotular e extrai para seus modelos de compreensão de documentos no Microsoft SharePoint Syntex. Ao criar uma explicação, você precisa selecionar um tipo de explicação. Este artigo vai ajudá-lo a entender melhor os diferentes tipos de explicação e como eles são usados. 

   ![Tipos de explicação](../media/content-understanding/explanation-types.png) 
   
Esses tipos de explicação estão disponíveis:

- **Lista de frases**: lista de palavras, frases, números ou outros caracteres que você pode usar no documento ou informações que você está extraindo. Por exemplo, a cadeia de texto **Médico encaminhador** está em todos os documentos de Encaminhamento Médico que você está identificando.</br>

- **Lista de padrões**: lista padrões de números, letras ou outros caracteres que você pode usar para identificar as informações que você está extraindo. Por exemplo, você pode extrair o **Número de telefone** do médico encaminhador de todos os documentos de Encaminhamento Médico que você está identificando.</br>

- **Proximidade**: descreve a proximidade das explicações entre si.  Por exemplo, uma lista de padrões de *número da rua* fica antes da lista de frases de *nome da rua*, sem tokens entre elas (você aprenderá sobre tokens mais adiante neste artigo). Usar o tipo de proximidade exige que você tenha pelo menos duas explicações em seu modelo, ou a opção será desabilitada. 
 
## <a name="phrase-list"></a>Lista de frases

Um tipo de explicação de lista de frases geralmente é usado para identificar e classificar um documento por meio do seu modelo. Conforme descrito no exemplo de rótulo *Médico encaminhador*, é uma cadeia de cadeia de palavras, frases, números ou caracteres que está de maneira consistente nos documentos que você está identificando.

Embora não seja um requisito, você pode obter um sucesso melhor com a sua explicação se a frase que está capturando estiver localizada em um local consistente no documento. Por exemplo, o rótulo *Médico encaminhador* pode estar localizado, de maneira consistente, no primeiro parágrafo do documento.

Se a diferenciação de maiúsculas e minúsculas for um requisito para a identificação do seu rótulo, usar o tipo de lista de frases permite que você o especifique na sua explicação selecionando a caixa de seleção **Somente maiúsculas**.

   ![Diferenciação de maiúsculas e minúsculas](../media/content-understanding/case-sensitivity.png) 

## <a name="pattern-lists"></a>Listas de padrões

Um tipo de lista de padrões é especialmente útil quando você cria uma explicação que identifica e extrai informações de um documento. Geralmente, é apresentado em formatos diferentes, como datas, números de telefone ou de cartão de crédito. Por exemplo, um data pode ser exibida em diversos formatos (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, 1º de janeiro de 2020, etc.). A definição de uma lista de padrões torna suas explicações mais eficientes, capturando todas as variações possíveis nos dados que você está tentando identificar e extrair. 

Para obter o exemplo de **Número de telefone**, extraia o número de telefone de cada médico encaminhador de todos os documentos de Encaminhamento Médico identificados pelo modelo. Ao criar a explicação, selecione o tipo de lista de padrões para permitir que os diferentes formados esperados sejam retornados.

   ![Lista de padrões de número de telefone](../media/content-understanding/pattern-list.png)

Para este exemplo, selecione a caixa de seleção **Qualquer dígito de 0-9**. Selecionar isso reconhece todos os valores “0” usado na sua lista de padrões como qualquer dígito de 0 a 9.

   ![Qualquer dígito de 0-9](../media/content-understanding/digit-identity.png)

Da mesma forma, se você criar uma lista de padrões que inclui caracteres de texto, selecione a caixa de seleção **Qualquer letra de a-z**. Selecionar isso reconhecer todos os caracteres “a” usados na lista de padrões como qualquer caractere de “a” a “z”.

Por exemplo, se você criar uma lista de padrões **Data** e desejar verificar se um formato de data como * 1º de janeiro de 2020* é reconhecido, será necessário:
- Adicionar *aaa 0, 0000* e *aaa 00, 0000* à sua lista de padrões.
- Verificar se **Qualquer letra de a-z** também está selecionada.

   ![Qualquer letra de a-z](../media/content-understanding/any-letter.png)

Além disso, se você tiver requisitos de uso de maiúsculas na sua lista de padrões, você tem a opção de selecionar a caixa de seleção **Somente maiúsculas**. Para o exemplo de Data, se for necessário que a primeira letra do mês seja maiúscula, você precisará:

- Adicionar *Aaa 0, 0000* e *Aaa 00, 0000* à sua lista de padrões.
- Verificar se **Somente maiúsculas** também está selecionada.

   ![Somente maiúsculas](../media/content-understanding/exact-caps.png)

> [!NOTE]
> Em vez de criar a explicação da lista de padrões manualmente, use a [biblioteca de explicações](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-explanation-templates) para usar modelos de lista de padrões predefinidos para lista de padrões comuns, como *data*, *número de telefone*, *número de cartão de crédito*, etc... 

## <a name="proximity"></a>Proximidade 

O tipo de explicação da proximidade ajuda seu modelo a identificar dados definindo a proximidade dos dados entre si. Por exemplo, em seu modelo, você definiu duas explicações que rotulam o *Número da rua* e *Número de telefone*. 

Você também percebe que os números de telefone do cliente sempre aparecem antes do número da rua. 

Alex Wilburn<br>
555-555-5555<br>
One Microsoft Way<br>
Redmond, WA 98034<br>

Use a explicação de proximidade para definir a distância da explicação do número de telefone para identificar melhor o número da rua em seus documentos.

   ![Explicação de proximidade](../media/content-understanding/proximity.png)</br>

#### <a name="what-are-tokens"></a>O que são tokens?

Para usar o tipo de explicação de proximidade, entenda o que é um token, uma vez que o número de tokens é como a explicação de proximidade mede a distância de uma explicação para a outra.  

Um token é um intervalo contínuo (sem espaços ou pontuação) de letras e números. Um espaço NÃO é um token. Cada caractere de pontuação é um token. A tabela a segui mostra alguns exemplos de como determinar o número de tokens em uma frase.

|Frase|Número de tokens|Explicação|
|--|--|--|
|`Dog`|1|Uma única palavra sem pontuação ou espaços.|
|`RMT33W`|1|Um número de localizador de registro. Pode ter números e letras, mas não tem nenhuma pontuação.|
|`425-555-5555`|5|Um número de telefone. Todos os sinais de pontuação são um único token, então  `425-555-5555` seria 5 tokens:<br>`425`<br>`-`<br>`555`<br>`-`<br>`5555` |
|`https://luis.ai`|7|`https`<br>`:`<br>`/`<br>`/`<br>`luis`<br>`.`<br>`ai`<br>|

#### <a name="configure-the-proximity-explanation-type"></a>Configurar o tipo de explicação de proximidade

Para o exemplo, defina a configuração de proximidade para que possamos definir o intervalo do número de tokens que a explicação do *Número de telefone* entre a explicação do *Número da rua*.

Você deve ver que o intervalo mínimo é “0”, uma vez que não há nenhum token entre o número de telefone e o número da rua.

No entanto, alguns números de telefone nos documentos de exemplo são anexados com *(móvel)*.

Nestor Wilke<br>
111-111-1111 (móvel)<br>
One Microsoft Way<br>
Redmond, WA 98034<br>

Há três tokens em *(móvel)*:

|Frase|Contagem de tokens|
|--|--|
|(|1|
|móvel|2|
|)|3|

Definir a configuração de proximidade para ter um intervalo de 0 a 3.

   ![Exemplo de proximidade](../media/content-understanding/proximity-example.png)</br>

## <a name="use-explanation-templates"></a>Usar modelos de explicação

Embora seja possível adicionar vários valores da lista de padrões para a explicação, é muito mais fácil usar os modelos predefinidos fornecidos na biblioteca de explicações.

Por exemplo, em vez de adicionar manualmente todas as variações para *Data*, você pode usar o modelo de lista de padrões para *Data*, que já inclui diversos valores de listas de padrões:</br>

   ![Biblioteca de explicações](../media/content-understanding/explanation-template.png)</br>
 
A biblioteca de explicações inclui diversas explicações de lista de padrões usadas com frequência, incluindo:</br>

- Data</br>
- Data (numérico)</br>
- Hora</br>
- Número</br>
- Número de telefone</br>
- Código postal</br>
- Primeira palavra da frase</br>
- Cartão de crédito</br>
- Cadastro de pessoas físicas</br>

Observe que a biblioteca de explicações também inclui modelos para explicações de lista de frases, incluindo:
- Fim da frase
- Moeda

#### <a name="to-use-a-template-from-the-explanation-library"></a>Para usar um modelo da biblioteca de explicações

1. Na seção **Explicações** da página de **Treinamento** do seu modelo, selecione **Novo** e, em seguida, selecione **De um modelo**.</br>

   ![Criar do modelo](../media/content-understanding/from-template.png)</br>

2.  Na página **Modelos de explicação**, selecione a explicação que você deseja usar e, em seguida, selecione **Adicionar**.</br>

       ![Selecionar um modelo](../media/content-understanding/phone-template.png)</br>

3. As informações do modelo que você selecionou serão exibidas na página **Criar uma explicação**. Se necessário, edite o nome da explicação e adicione ou remova itens da lista de padrões. </br> 

   ![Editar modelo](../media/content-understanding/phone-template-live.png)</br>

4. Quando concluir, selecione **Salvar**.
