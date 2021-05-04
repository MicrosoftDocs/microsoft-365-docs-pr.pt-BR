---
title: Saiba mais sobre classificadores treináveis
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Um Microsoft 365 classificador treinável é uma ferramenta que você pode treinar para reconhecer vários tipos de conteúdo, dando a ele exemplos positivos e negativos a ser olhado. Depois que o classificador for treinado, confirme se seus resultados são precisos. Em seguida, use-o para pesquisar o conteúdo da sua organização e classificá-lo para aplicar rótulos de retenção ou de sensibilidade ou incluí-lo em políticas de prevenção contra perda de dados (DLP) ou retenção.
ms.openlocfilehash: 1881e4de87fd41f21bb1f2236d46391b3a1ed785
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114047"
---
# <a name="learn-about-trainable-classifiers"></a>Saiba mais sobre classificadores treináveis

Classificar e rotular o conteúdo para que ele possa ser protegido e manipulado corretamente é o ponto de partida para a disciplina de proteção de informações. Microsoft 365 tem três maneiras de classificar o conteúdo.

## <a name="manually"></a>Manualmente

Esse método requer julgamento e ação humanos. Um administrador pode usar os rótulos pré-existentes e tipos de informações confidenciais ou criar seus próprios e publicá-los. Os usuários e administradores aplicam-os ao conteúdo conforme o encontram. Em seguida, você pode proteger o conteúdo e gerenciar sua disposição.

## <a name="automated-pattern-matching"></a>Correspondência de padrões automatizados

Essa categoria de mecanismos de classificação inclui localizar conteúdo por:

- Palavras-chave ou valores de metadados (linguagem de consulta de palavra-chave).
- Usando padrões identificados anteriormente de informações confidenciais, como previdência social, cartão de crédito ou números de conta bancária [(definições de](sensitive-information-type-entity-definitions.md)entidade de tipo de informação confidenciais) .
- Reconhecendo um item porque é uma variação em um modelo [(impressão digital de documento)](document-fingerprinting.md).
- Usando a presença de cadeias de caracteres [exatas (combinação de dados exatos)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).

Os rótulos de sensibilidade e retenção podem ser aplicados automaticamente para disponibilizar o conteúdo para uso em Saiba mais sobre prevenção contra perda de dados [)](dlp-learn-about-dlp.md)e aplicar automaticamente políticas para [rótulos de retenção.](apply-retention-labels-automatically.md)

## <a name="classifiers"></a>Classificadores

Esse método de classificação é particularmente adequado ao conteúdo que não é facilmente identificado pelos métodos de correspondência de padrões manuais ou automatizados. Este método de classificação é mais para treinar um classificador para identificar um item com base no que o item é, não por elementos que estão no item (correspondência de padrões). Um classificador aprende a identificar um tipo de conteúdo analisando centenas de exemplos do conteúdo que você está interessado em classificar. Você começa alimentando-o com exemplos que estão definitivamente na categoria. Depois de processá-los, você testá-lo, dando a ele uma mistura de exemplos correspondentes e não correspondentes. Em seguida, o classificador faz previsões sobre se um determinado item se enquadra na categoria que você está criando. Em seguida, você confirma seus resultados, classificação dos verdadeiros positivos, verdadeiros negativos, falsos positivos e falsos negativos para ajudar a aumentar a precisão de suas previsões. 

Quando você publica o classificador, ele classifica por meio de itens em locais como SharePoint Online, Exchange e OneDrive e classifica o conteúdo. Depois de publicar o classificador, você pode continuar a treiná-lo usando um processo de feedback semelhante ao processo de treinamento inicial.

### <a name="where-you-can-use-trainable-classifiers"></a>Onde você pode usar classificadores treináveis
Os classificadores integrados e os classificadores com treinamento estão disponíveis como uma condição para Office [auto-rotulagem](apply-sensitivity-label-automatically.md)com rótulos de [sensibilidade,](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) aplicar automaticamente a política de rótulo de retenção com base em uma condição e em conformidade com a [comunicação.](communication-compliance.md) 

Rótulos de sensibilidade podem usar classificadores como condições, consulte Aplicar um rótulo de [sensibilidade ao conteúdo automaticamente](apply-sensitivity-label-automatically.md).

> [!IMPORTANT]
> Os classificadores só funcionam com itens que não são criptografados e estão em inglês.

## <a name="types-of-classifiers"></a>Tipos de classificadores

- **classificadores pré-treinados** – a Microsoft criou e treinou previamente vários classificadores que você pode começar a usar sem trodá-los. Esses classificadores aparecerão com o status `Ready to use` de .
- **classificadores personalizados** - Se você tiver necessidades de classificação que vão além do que os classificadores pré-treinados abrangem, você pode criar e treinar seus próprios classificadores.

### <a name="pre-trained-classifiers"></a>Classificadores pré-treinados

Microsoft 365 vem com cinco classificadores pré-treinados:

> [!CAUTION]
> Estamos preterindo  o classificador de Idioma Ofensivo pré-treinado porque ele vem produzindo um alto número de falsos positivos. Não use-o e, se estiver usando-o no momento, você deve mover seus processos de negócios para fora dele. Recomendamos o uso dos classificadores **Ameaça,** **Profanidade** e **Assédio** pré-treinados.

- **Currículos**: detecta itens que são contas textuais das qualificações pessoais, educacionais, profissionais, de um candidato, da experiência de trabalho e de outras informações de identificação pessoal de um candidato
- **Código-fonte**: detecta itens que contêm um conjunto de instruções e instruções escritas nas 25 principais linguagens de programação de computador usadas em GitHub
    - ActionScript
    - C
    - C #
    - C++
    - Clojure
    - CoffeeScript
    - Ir
    - Haskell
    - Java
    - JavaScript
    - Lua
    - MATLAB
    - Objective-C
    - Perl
    - PHP
    - Python
    - R
    - Ruby
    - Scala
    - Shell
    - Swift
    - Tex
    - Vim Script

> [!NOTE]
> O Código-fonte é treinado para detectar quando a maior parte do texto é o código-fonte. Ele não detecta texto de código-fonte intercalado com texto sem texto.

- **Assédio**: detecta uma categoria específica de itens de texto de linguagem ofensiva relacionados a conduta ofensiva voltada para um ou vários indivíduos com base nos seguintes traços: raça, etnidade, religião, origem nacional, gênero, orientação sexual, idade, deficiência
- **Profanidade**: detecta uma categoria específica de itens de texto de linguagem ofensiva que contêm expressões que constrangem a maioria das pessoas
- **Ameaça**: detecta uma categoria específica de itens de texto de linguagem ofensiva relacionados a ameaças para cometer violência ou causar danos físicos ou danos físicos a uma pessoa ou propriedade

Elas aparecem no Microsoft 365 **de classificação** de dados Classificação de dados  >    >  **Classificadores** com o status `Ready to use` de .

![classificadores-pré-treinados-classificadores](../media/classifiers-ready-to-use-classifiers.png)

> [!IMPORTANT]
> Observe que os classificadores de linguagem ofensiva, assédio, profanidade e ameaça só funcionam com texto pesquisável não são exaustivos ou completos.  Além disso, os padrões de idioma e cultura mudam continuamente e, à luz dessas realidades, a Microsoft se reserva o direito de atualizar esses classificadores a seu critério. Embora os classificadores possam ajudar sua organização no monitoramento ofensivo e em outros idiomas usados, os classificadores não abordam as consequências desse idioma e não se destinam a fornecer o único meio de monitoramento ou resposta da sua organização ao uso desse idioma. Sua organização, e não a Microsoft ou suas subsidiárias, permanece responsável por todas as decisões relacionadas ao monitoramento, imposição, bloqueio, remoção e retenção de qualquer conteúdo identificado por um classificador pré-treinado.

### <a name="custom-classifiers"></a>Classificadores personalizados

Quando os classificadores pré-treinados não atendem às suas necessidades, você pode criar e treinar seus próprios classificadores. Há muito mais trabalho envolvido na criação do seu próprio, mas eles serão muito melhor adaptados às suas necessidades de organizações. 

Por exemplo, você pode criar classificadores com treinamento para:
 
- Documentos legais - como privilégio do cliente advogado, conjuntos de fechamento, instrução de trabalho
- Documentos de negócios estratégicos - como comunicados de imprensa, fusão e aquisição, negócios, planos de negócios ou marketing, propriedade intelectual, patentes, documentos de design
- Informações sobre preços - como faturas, cotações de preço, ordens de trabalho, documentos de oferta 
- Informações financeiras - como investimentos organizacionais, resultados trimestrais ou anuais    

#### <a name="process-flow-for-creating-custom-classifiers"></a>Fluxo de processos para a criação de classificadores personalizados

A criação e publicação de um classificador para uso em soluções de conformidade, como políticas de retenção e supervisão de comunicação, segue esse fluxo. Para obter mais detalhes sobre a criação de um classificador de treinamento personalizado, consulte Criar [um classificador personalizado.](classifier-get-started-with.md)

![classificador personalizado de fluxo de processo](../media/classifier-trainable-classifier-flow.png)

### <a name="retraining-classifiers"></a>Classificadores de retreinamento

Você pode ajudar a melhorar a precisão de todos os classificadores personalizados e alguns classificadores pré-treinados fornecendo comentários sobre a precisão da classificação que eles realizam. Isso é chamado de retreinamento e segue esse fluxo de trabalho.

![classifier retraining workflow](../media/classifier-retraining-workflow.png)

## <a name="see-also"></a>Confira também

- [Rótulos de retenção](retention.md)
- [Saiba mais sobre a prevenção contra perda de dados do ponto de extremidade](dlp-learn-about-dlp.md)
- [Rótulos de confidencialidade](sensitivity-labels.md)
- [Definições da entidade do tipo de informações confidenciais](sensitive-information-type-entity-definitions.md)
- [Impressão digital de documento](document-fingerprinting.md)
- [Match de dados exatos](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
