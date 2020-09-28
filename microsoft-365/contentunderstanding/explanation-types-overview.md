---
title: Tipos de explicação
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
description: Saiba mais sobre tipos de explicação no Microsoft SharePoint Syntex
ms.openlocfilehash: f4f5dbc24bef57b1801f7df1b7e2fc7ef9b08116
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295708"
---
# <a name="introduction-to-explanation-types"></a>Introdução aos tipos de explicação

Use explicações para ajudar a definir as informações que você deseja rotular e extrair no documento os modelos de compreensão para o Microsoft SharePoint Syntex. Ao criar uma explicação, certifique-se de selecionar um tipo de explicação. 

Este artigo ajuda você a compreender os diferentes tipos de explicação e como eles são usados.

   ![Tipos de explicação](../media/content-understanding/explanation-types.png) 
   
Estes tipos de explicação estão disponíveis:

- **Lista de frases**: lista de palavras, frases, números ou outros caracteres que você pode usar no documento ou informações que você está extraindo. Por exemplo, a cadeia de caracteres de texto que **faz referência ao doutor** está em todos os documentos de referência médica que você está identificando.</br>

- **Lista padrão**: padrões de lista de números, letras ou outros caracteres que você pode usar para identificar as informações que você está extraindo. Por exemplo, você pode extrair o **número de telefone** do médico de referência de todos os documentos de referência médica que está identificando.</br>

- **Proximidade**: descreve como as explicações de fechamento estão entre si. Por exemplo, uma lista de padrões de *números de rua* fica correta antes da lista de frases de *nome de rua* , sem tokens entre (você aprenderá tokens mais adiante neste artigo). 
 
## <a name="phrase-list"></a>Lista de frases

Uma lista de frases o tipo explicação geralmente é usado para identificar e classificar um documento por meio do modelo. Conforme descrito no exemplo de etiqueta de *referência médica* , é uma cadeia de caracteres de palavras, frases, números ou caracteres que é consistentemente nos documentos que você está identificando.

Embora não seja um requisito, você pode obter um sucesso melhor com sua explicação se a frase que você está capturando estiver localizada em um local consistente no seu documento. Por exemplo, a etiqueta de *referência médica* pode ser localizada de forma consistente no primeiro parágrafo do documento.

Se a diferenciação de maiúsculas e minúsculas for um requisito para identificar seu rótulo, usar o tipo de lista de frases permite que você o especifique em sua explicação, marcando a caixa de seleção **somente maiúscula exata** .

   ![Diferenciação de maiúsculas e minúsculas](../media/content-understanding/case-sensitivity.png) 

## <a name="pattern-lists"></a>Listas de padrões

Um tipo de lista padrão é especialmente útil quando você cria uma explicação que identifica e extrai informações de um documento. Geralmente, ele é apresentado em formatos diferentes, como datas, números de telefone ou números de cartão de crédito. Por exemplo, uma data pode ser exibida em vários formatos diferentes (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, Jan 1, 2020, etc.). A definição de uma lista de padrões torna sua explicação mais eficiente, capturando quaisquer variações possíveis nos dados que você está tentando identificar e extrair. 

Para o exemplo de **número de telefone** , extraia o número de telefone de cada referência médica de todos os documentos de referência médica que o modelo identifica. Ao criar a explicação, selecione o tipo de lista padrão para permitir que os diferentes formatos que você espera que sejam retornados.

   ![Lista de padrões de números de telefone](../media/content-understanding/pattern-list.png)

Para este exemplo, selecione a caixa de seleção **qualquer dígito de 0-9** . Selecionar isso reconhece cada valor "0" usado na sua lista de padrões para ser qualquer dígito de 0 a 9.

   ![Qualquer dígito de 0-9](../media/content-understanding/digit-identity.png)

Da mesma forma, se você criar uma lista de padrões que inclua caracteres de texto, selecione a **letra qualquer da** caixa de seleção-z. Selecionar isso reconhece cada caractere "a" usado na lista padrão como qualquer caractere de "a" a "z".

Por exemplo, se você criar uma lista de padrões de **datas** e quiser certificar-se de que um formato de data como *1 Jan 2020* seja reconhecido, você precisará:
- Adicione *AAA 0, 0000* e *AAA 00, 0000* à sua lista padrão.
- Verifique se **qualquer letra de a-z** também está selecionada.

   ![Qualquer letra de a a z](../media/content-understanding/any-letter.png)

Além disso, se você tiver requisitos de capitalização em sua lista padrão, terá a opção de selecionar somente a caixa de seleção **exata maiúscula** . Para o exemplo de data, se você precisar que a primeira letra do mês seja capitalizada, será necessário:

- Adicione *AAA 0, 0000* e *AAA 00, 0000* à sua lista padrão.
- Certifique-se de que **apenas a capitalização exata** também esteja selecionada.

   ![Apenas maiúscula exata](../media/content-understanding/exact-caps.png)

> [!NOTE]
> Em vez de criar a explicação da lista de padrões manualmente, use a [biblioteca explicação]() para usar modelos de lista de padrões predefinidos para lista de padrões comuns, como *Data*, *número de telefone*, *número de cartão de crédito*, etc.. 

## <a name="proximity"></a>Proximidade 

O tipo de explicação de proximidade ajuda seu modelo a identificar dados por meio da definição de como fechar outros dados. Por exemplo, em seu modelo, você definiu duas explicações que rotulam o *número de endereço* e número de *telefone*do cliente. 

Observe também que os números de telefone do cliente sempre aparecem antes do número de endereço. 

Alex Wilburn<br>
555-555-5555<br>
One Microsoft Way<br>
Redmond, WA 98034<br>

Use a explicação de proximidade para definir o quanto longe a explicação do número de telefone é para identificar melhor o número de endereço dos seus documentos.

   ![Explicação de proximidade](../media/content-understanding/proximity.png)</br>

#### <a name="what-are-tokens"></a>O que são tokens?

Para usar o tipo de explicação de proximidade, entenda o que é um token, como o número de tokens é como a explicação de proximidade mede a distância de uma explicação para outra.  

Um token é uma extensão contínua (sem espaços ou pontuação) de letras e números. Um espaço não é um token. Cada caractere de pontuação é um token. A tabela a seguir mostra alguns exemplos de como determinar o número de tokens em uma frase.

|Faça|Número de tokens|Explicação|
|--|--|--|
|`Dog`|1 |Uma única palavra sem pontuação ou espaços.|
|`RMT33W`|1 |Um número de localizador de registro. Ele pode ter números e letras, mas não tem pontuação.|
|`425-555-5555`|5 |Um número de telefone. Cada marca de pontuação é um único token, portanto,  `425-555-5555` deve ser de 5 tokens:<br>`425`<br>`-`<br>`555`<br>`-`<br>`5555` |
|`https://luis.ai`|7 |`https`<br>`:`<br>`/`<br>`/`<br>`luis`<br>`.`<br>`ai`<br>|

#### <a name="configure-the-proximity-explanation-type"></a>Configurar o tipo de explicação de proximidade

Para o exemplo, configure a configuração de proximidade para que possamos definir o intervalo do número de tokens que o *número de telefone* explicação é da explicação de número de endereço de *rua* .

Você deve ver que o intervalo mínimo é "0", já que não há tokens entre o número de telefone e o número de endereço.

No entanto, alguns números de telefone nos documentos de exemplo são acrescentados com *(móvel)*.

Marcos Wilke<br>
111-111-1111 (celular)<br>
One Microsoft Way<br>
Redmond, WA 98034<br>

Há três tokens no *(celular)*:

|Faça|Contagem de tokens|
|--|--|
|(|1 |
|processadores|2 |
|)|3 |

Defina a configuração de proximidade para ter um intervalo de 0 a 3.

   ![Exemplo de proximidade](../media/content-understanding/proximity-example.png)</br>

## <a name="use-the-explanation-library"></a>Usar a biblioteca de explicação

Embora você possa adicionar manualmente vários valores de lista padrão para sua explicação, é muito mais fácil usar os modelos pré-criados fornecidos na biblioteca de explicação.

Por exemplo, em vez de adicionar manualmente todas as variações para *Data*, use o modelo de lista de padrões para *Data*, que já inclua um número de padrões de listas:</br>

   ![Biblioteca de explicação](../media/content-understanding/explanation-template.png)</br>
 
A biblioteca explicação inclui uma série de explicações de lista de padrões comumente usadas, incluindo:</br>

- Data</br>
- Data (numérico)</br>
- Time</br>
- Número</br>
- Número de telefone</br>
- Código Postal</br>
- Primeira palavra da frase</br>
- Cartão de crédito</br>
- Número de seguro social</br>

Observe que a biblioteca de explicação também inclui modelos para explicações de lista de frases, incluindo:
- Fim da frase
- Moeda

#### <a name="to-use-a-template-from-the-explanation-library"></a>Para usar um modelo da biblioteca de explicação

1. Na seção **explicações** da página de **treinamento** do seu modelo, selecione **novo**e, em seguida, selecione **a partir de um modelo**.</br>

   ![Criar do modelo](../media/content-understanding/from-template.png)</br>

2.  Na página **modelos de explicação** , selecione a explicação que você deseja usar e, em seguida, selecione **Adicionar**.</br>

       ![Selecionar um modelo](../media/content-understanding/phone-template.png)</br>

3. As informações do modelo selecionado serão exibidas na página **criar uma explicação** . Se necessário, edite o nome da explicação e adicione ou remova itens da lista padrão. </br> 

   ![Editar modelo](../media/content-understanding/phone-template-live.png)</br>

4. Quando terminar, selecione **salvar**.
