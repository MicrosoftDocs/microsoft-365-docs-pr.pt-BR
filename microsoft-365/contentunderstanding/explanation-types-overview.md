---
title: Tipos de explicação
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
description: Saiba mais sobre tipos de explicação no Microsoft SharePoint Syntex
ms.openlocfilehash: a5404230a59d1740a2b855527229a7aca92195a8
ms.sourcegitcommit: dc1ac43a57fac6f57438859dd668f927d94fdf34
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/07/2021
ms.locfileid: "51604400"
---
# <a name="introduction-to-explanation-types"></a>Introdução aos tipos de explicação

As explicações são usadas para ajudar a definir as informações que você deseja rotular e extrai para seus modelos de compreensão de documentos no Microsoft SharePoint Syntex. Ao criar uma explicação, você precisa selecionar um tipo de explicação. Este artigo ajuda você a entender os diferentes tipos de explicação e como eles são usados. 

![Tipos de explicação](../media/content-understanding/explanation-types.png) 
   
Esses tipos de explicação estão disponíveis:

- **Lista de frases**: lista de palavras, frases, números ou outros caracteres que você pode usar no documento ou informações que você está extraindo. Por exemplo, a cadeia de texto **Médico encaminhador** está em todos os documentos de Encaminhamento Médico que você está identificando. Ou o **Número de telefone** do médico de referência de todos os documentos de referência médica que você está identificando.

- **Proximidade**: Descreve como as explicações são próximas umas das outras. Por exemplo, um *número da rua* lista de frases vai logo antes do *nome da rua* lista de frases, sem tokens entre eles (você aprenderá sobre tokens posteriormente neste artigo). Usar o tipo de proximidade exige que você tenha pelo menos duas explicações em seu modelo, ou a opção será desabilitada. 
 
## <a name="phrase-list"></a>Lista de frases

Um tipo de explicação de lista de frases geralmente é usado para identificar e classificar um documento por meio do seu modelo. Conforme descrito no exemplo de rótulo *Médico encaminhador*, é uma cadeia de cadeia de palavras, frases, números ou caracteres que está de maneira consistente nos documentos que você está identificando.

Embora não seja um requisito, você pode obter um sucesso melhor com a sua explicação se a frase que está capturando estiver localizada em um local consistente no documento. Por exemplo, o rótulo *Médico encaminhador* pode estar localizado, de maneira consistente, no primeiro parágrafo do documento. Você também pode usar o **[Configurar onde as frases ocorrem no documento](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#configure-where-phrases-occur-in-the-document)** configuração avançada para selecionar áreas específicas onde a frase está localizada, especialmente se houver uma chance de que a frase possa ocorrer em vários locais em seu documento.

Se a diferenciação de maiúsculas e minúsculas for um requisito para a identificação do seu rótulo, usar o tipo de lista de frases permite que você o especifique na sua explicação selecionando a caixa de seleção **Somente maiúsculas**.

![Diferenciação de maiúsculas e minúsculas](../media/content-understanding/case-sensitivity.png) 

Um tipo de frase é especialmente útil quando você cria uma explicação que identifica e extrai informações em diferentes formatos, como datas, números de telefone e números de cartão de crédito. Por exemplo, uma data pode ser exibida em vários formatos diferentes (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, Jan 1,2020, etc.). Definir uma lista de frases torna sua explicação mais eficiente, capturando quaisquer variações possíveis nos dados que você está tentando identificar e extrair. 

Para o **Número de telefone** Por exemplo, você extrai o número de telefone de cada médico de referência de todos os documentos de referência médica que o modelo identifica. Ao criar a explicação, digite os diferentes formatos que um número de telefone pode exibir em seu documento para que você possa capturar possíveis variações. 

![Padrões de frase de número de telefone](../media/content-understanding/pattern-list.png)

Para este exemplo, em **Configurações avançadas** selecione os **Qualquer dígito de 0-9** caixa de seleção para reconhecer cada valor "0" usado em sua lista de frases como qualquer dígito de 0 a 9.

![Qualquer dígito de 0-9](../media/content-understanding/digit-identity.png)

Da mesma forma, se você criar uma lista de frases que inclua caracteres de texto, selecione o **Qualquer letra de a-z** caixa de seleção para reconhecer cada caractere "a" usado na lista de frases como qualquer caractere de "a" a "z".

Por exemplo, se você criar um **Data** lista de frases e você deseja ter certeza de que um formato de data como *Jan 1, 2020* é reconhecido, você precisa:
- Adicionar *aaa 0, 0000* e *aaa 00, 0000* para sua lista de frases.
- Verificar se **Qualquer letra de a-z** também está selecionada.

![Qualquer letra de a-z](../media/content-understanding/any-letter.png)

Além disso, se houver requisitos de letras maiúsculas em sua lista de frases, você terá a opção de selecionar o **Apenas letras maiúsculas exatas** caixa de seleção. Para o exemplo de data, se você quiser que a primeira letra do mês seja maiúscula, você precisa:

- Adicionar *Aaa 0, 0000* and *Aaa 00, 0000* para sua lista de frases.
- Verificar se **Somente maiúsculas** também está selecionada.

![Somente maiúsculas](../media/content-understanding/exact-caps.png)

> [!NOTE]
> Em vez de criar manualmente uma explicação de lista de frases, use o [biblioteca de explicação](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-explanation-templates) para usar modelos de lista de frases para uma lista de frases comum, como *data*, *número de telefone*, *número do cartão de crédito*, etc.

## <a name="proximity"></a>Proximidade 

O tipo de explicação da proximidade ajuda seu modelo a identificar dados definindo a proximidade dos dados entre si. Por exemplo, em seu modelo, você definiu duas explicações que rotulam o *Número da rua* e *Número de telefone* do cliente. 

Observe que os números de telefone do cliente sempre aparecem antes do número da rua. 

Alex Wilburn<br>
555-555-5555<br>
One Microsoft Way<br>
Redmond, WA 98034<br>

Use a explicação de proximidade para definir a distância da explicação do número de telefone para identificar melhor o número da rua em seus documentos.

![Explicação de proximidade](../media/content-understanding/proximity.png)

#### <a name="what-are-tokens"></a>O que são tokens?

Para usar o tipo de explicação de proximidade, você precisa entender o que é um token, uma vez que o número de tokens é como a explicação de proximidade mede a distância de uma explicação para a outra. Um token é um intervalo contínuo (sem incluir espaços ou pontuação) de letras e números. 

A tabela a seguir mostra exemplos de como determinar o número de tokens em uma frase.

|Frase|Número de tokens|Explicação|
|--|--|--|
|`Dog`|1|Uma única palavra sem pontuação ou espaços.|
|`RMT33W`|1|Um número de localizador de registro. Pode incluir números e letras, mas não tem pontuação.|
|`425-555-5555`|5|Um número de telefone. Cada sinal de pontuação é um único token, assim `425-555-5555` equivale a 5 tokens:<br>`425`<br>`-`<br>`555`<br>`-`<br>`5555` |
|`https://luis.ai`|7|`https`<br>`:`<br>`/`<br>`/`<br>`luis`<br>`.`<br>`ai`<br>|

#### <a name="configure-the-proximity-explanation-type"></a>Configurar o tipo de explicação de proximidade

Para o exemplo, defina a configuração de proximidade para definir o intervalo do número de tokens na explicação do *Número de telefone* da explicação do *Número da rua*. Observe que o intervalo mínimo é “0”, pois não há nenhum token entre o número de telefone e o número da rua.

No entanto, alguns números de telefone nos documentos de exemplo são acrescentados no *(telefone)*.

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

![Exemplo de proximidade](../media/content-understanding/proximity-example.png)


## <a name="configure-where-phrases-occur-in-the-document"></a>Configurar onde as frases ocorrem no documento

Quando você cria uma explicação, por padrão, todo o documento é pesquisado pela frase que você está tentando extrair. No entanto, você pode usar a configuração avançada **Onde essas frases ocorrem** para ajudar a isolar um local específico do documento em que ocorre uma frase. Isso é útil em situações em que instâncias semelhantes de uma frase podem aparecer em outro lugar no documento e você deseja ter certeza de que a correta está selecionada. Ao se referir ao nosso exemplo de documento de Referência Médica, o **Médico Encaminhador** sempre é mencionado no primeiro parágrafo do documento. Com a configuração ** Onde essas frases ocorrem, neste exemplo, você pode configurar sua explicação para pesquisar esse rótulo apenas na seção inicial do documento ou em qualquer outro local em que possa ocorrer.

![Configuração de onde essas frases ocorrem](../media/content-understanding/phrase-location.png)

Você pode escolher uma das três opções para esta configuração:

- Em qualquer lugar no arquivo: o documento inteiro é pesquisado pela frase.

- Início do arquivo: o documento é pesquisado do início até o local da frase.

   ![Início do arquivo](../media/content-understanding/beginning-of-file.png)

    No visualizador, você pode ajustar manualmente a caixa de seleção para incluir o local onde a fase ocorre. O valor **Posição final** será atualizado para mostrar o número de tokens que sua área selecionada inclui. Observe que você também pode atualizar o valor da Posição final para ajustar a área selecionada.

   ![Início da caixa de posição do arquivo](../media/content-understanding/beginning-box.png)

- Fim do arquivo: O documento é pesquisado desde o final até a localização da frase.

   ![Fim do arquivo](../media/content-understanding/end-of-file.png)

    No visualizador, você pode ajustar manualmente a caixa de seleção para incluir o local onde a fase ocorre. O valor **Posição incial** será atualizado para mostrar o número de tokens que sua área selecionada inclui. Observe que você também pode atualizar o valor da Posição inicial para ajustar a área selecionada.

   ![Fim da caixa de fim do arquivo](../media/content-understanding/end-box.png)

- Intervalo personalizado: O documento é pesquisado em um intervalo especificado dentro dele para a localização da frase.

   ![Intervalo personalizado](../media/content-understanding/custom-file.png)

    No visualizador, você pode ajustar manualmente a caixa de seleção para incluir o local onde a fase ocorre. Para essa configuração, você precisa selecionar uma posição **Inicial** e uma **Final**. Esses valores representam o número de tokens do início do documento. Embora seja possível inserir manualmente esses valores, é mais fácil ajustar manualmente a caixa de seleção no visualizador. 
   
## <a name="use-explanation-templates"></a>Usar modelos de explicação

Embora você possa adicionar manualmente vários valores da lista de frases para sua explicação, pode ser mais fácil usar os modelos fornecidos a você na biblioteca de explicação.

Por exemplo, em vez de adicionar manualmente todas as variações de *Data*, você pode usar o modelo de lista de frases para *Data*, pois já inclui vários valores da listas de frases:

![Biblioteca de explicações](../media/content-understanding/explanation-template.png)
 
A biblioteca de explicação inclui explicações da lista de frases comumente usadas, incluindo:

- Data: datas do Calendário do Outlook, todos os formatos. Inclui texto e números (por exemplo, "9 de dezembro de 2020").
- Data (numérico): datas do Calendário do Outlook, todos os formatos. Inclui números (por exemplo, 1-11-2020).
- Relógio: formatos de 12 e 24 horas.
- Número: números positivos e negativos até 2 decimais. 
- Porcentagem: uma lista de padrões que representam uma porcentagem. Por exemplo, 1%, 11%, 100%, 11,11%, etc.
- Número de telefone: formatos comuns nos EUA e internacionais. Por exemplo, 000 000 0000, 000-000-0000, (000) 000-0000, (000) 000-0000, etc.
- Código postal: formatos de código postal dos EUA. Por exemplo, 11111, 11111-1111.
- Primeira palavra da frase: padrões comuns para palavras de até 9 caracteres. 
- Fim da frase: pontuação comum para o final de uma frase
- Cartão de crédito: formatos comuns de número de cartão de crédito. Por exemplo, 1111-1111-1111-1111. 
- Número da previdência social: formato do número da previdência social dos EUA. Por exemplo, 111-11-1111. 
- Caixa de seleção: uma lista de frases que representa variações de uma caixa de seleção preenchida. Por exemplo, _X_, _ _X_, etc.
- Moeda: principais símbolos internacionais. Por exemplo, $. 
- CC de email: uma lista de frases com o termo 'CC:', geralmente encontrada perto dos nomes ou endereços de email de outras pessoas ou grupos para os quais a mensagem foi enviada.
- Data do email: uma lista de frases com o termo 'Enviado em:', geralmente encontrada próximo à data em que o email foi enviado.
- Saudação por email: linhas de abertura comuns para emails.
- Destinatário do email: uma lista de frases com o termo 'Para:', geralmente encontrada próximo aos nomes ou endereços de email de pessoas ou grupos para os quais a mensagem foi enviada. 
- Remetente do email: uma lista de frases com o termo 'De:', geralmente encontrada próximo ao nome ou endereço de email do remetente. 
- Assunto do email: uma lista de frases com o termo 'Assunto:', geralmente encontrada próximo ao assunto do email. 

A biblioteca de explicação também inclui três tipos de modelos automáticos que funcionam com os dados que você rotulou em seus arquivos de exemplo:

- Depois do rótulo: As palavras ou caracteres que ocorrem após os rótulos nos arquivos de exemplo.
- Antes do rótulo: As palavras ou caracteres que ocorrem antes dos rótulos nos arquivos de exemplo.
- Rótulos: Até os primeiros 10 rótulos dos arquivos de exemplo.

Para lhe dar um exemplo de como os modelos automáticos funcionam, no arquivo de exemplo a seguir, usaremos o modelo de explicação Antes do rótulo para ajudar a fornecer ao modelo mais informações para obter uma correspondência mais precisa.

![Arquivo de exemplo](../media/content-understanding/before-label.png)

Quando você seleciona o modelo de explicação Antes do Rótulo, ele procura o primeiro conjunto de palavras que aparece antes do rótulo em seus arquivos de exemplo. No exemplo, as palavras identificadas no primeiro arquivo de exemplo são "A partir de".

![Antes do Modelo do Rótulo](../media/content-understanding/before-label-explanation.png)

Você pode selecionar **Adicionar** para criar uma explicação a partir do modelo.  Conforme você adiciona mais arquivos de exemplo, palavras adicionais serão identificadas e adicionadas à lista de frases.

![Adicionar o rótulo](../media/content-understanding/before-label-add.png)
 
#### <a name="to-use-a-template-from-the-explanation-library"></a>Para usar um modelo da biblioteca de explicações

1. Na seção **Explicações** da página de **Treinamento** do seu modelo, selecione **Novo** e, em seguida, selecione **De um modelo**.

   ![Adicionar Antes do Rótulo](../media/content-understanding/from-template.png)

2.  Na página **Modelos de explicação**, selecione a explicação que você deseja usar e, em seguida, selecione **Adicionar**.

    ![Selecionar um modelo](../media/content-understanding/phone-template.png)

3. As informações do modelo que você selecionou são exibidas na página **Criar uma explicação**. Se necessário, edite o nome da explicação e adicione ou remova itens da lista de frases.  

    ![Editar modelo](../media/content-understanding/phone-template-live.png)

4. Quando concluir, selecione **Salvar**.