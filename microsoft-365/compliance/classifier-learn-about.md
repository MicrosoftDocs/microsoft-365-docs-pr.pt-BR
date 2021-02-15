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
description: Um classificador de treinamento do Microsoft 365 é uma ferramenta que você pode treinar para reconhecer vários tipos de conteúdo, dando a ele exemplos positivos e negativos para olhar. Depois que o classificador for treinado, confirme se seus resultados são precisos. Em seguida, use-o para pesquisar o conteúdo da sua organização e classificá-lo para aplicar rótulos de retenção ou sensibilidade ou incluí-lo em políticas de retenção ou prevenção contra perda de dados (DLP).
ms.openlocfilehash: 0e5f712b76af2fba3d456997a47352773d92d766
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/06/2021
ms.locfileid: "49759895"
---
# <a name="learn-about-trainable-classifiers"></a>Saiba mais sobre classificadores treináveis

Classificar e rotular o conteúdo para que ele possa ser protegido e manipulado corretamente é o ponto de partida para a disciplina de proteção de informações. O Microsoft 365 tem três maneiras de classificar o conteúdo.

## <a name="manually"></a>Manualmente

Esse método requer críticas e ações humanas. Um administrador pode usar os rótulos pré-existentes e tipos de informações confidenciais ou criar seus próprios e publicá-los. Os usuários e administradores os aplicam ao conteúdo à medida que o encontram. Em seguida, você pode proteger o conteúdo e gerenciar sua disposição.

## <a name="automated-pattern-matching"></a>Correspondência automatizada de padrões

Essa categoria de mecanismos de classificação inclui localizar conteúdo por:

- Palavras-chave ou valores de metadados (linguagem de consulta de palavra-chave).
- Usando padrões identificados anteriormente de informações confidenciais, como seguro social, cartão de crédito ou números de contas [bancárias (definições de](sensitive-information-type-entity-definitions.md)entidade de tipo de informação confidenciais).
- Reconhecer um item porque é uma variação em um modelo [(impressão digital de documento).](document-fingerprinting.md)
- Usando a presença de cadeias de caracteres [exatas (exact data match)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).

Os rótulos de retenção e sensibilidade podem ser aplicados automaticamente para disponibilizar o conteúdo para uso na prevenção de perda de dados [(DLP)](data-loss-prevention-policies.md) e políticas de aplicação automática para rótulos de [retenção.](apply-retention-labels-automatically.md)

## <a name="classifiers"></a>Classificadores

Esse método de classificação é particularmente adequado ao conteúdo que não é facilmente identificado pelos métodos de correspondência de padrões manuais ou automatizados. Esse método de classificação é mais sobre o treinamento de um classificador para identificar um item com base no que é o item, não por elementos que estão no item (correspondência de padrões). Um classificador aprende a identificar um tipo de conteúdo analisando centenas de exemplos do conteúdo que você tem interesse em classificar. Você começa alimentando exemplos que definitivamente estão na categoria. Depois de processá-los, você o testará, dando a ele uma mistura de exemplos correspondentes e não correspondentes. Em seguida, o classificador faz previsões sobre se um determinado item se enquadra na categoria que você está criando. Em seguida, confirme seus resultados, ordenando os verdadeiros positivos, verdadeiros negativos, falsos positivos e falsos negativos para ajudar a aumentar a precisão de suas previsões. 

Quando você publica o classificador, ele classifica os itens em locais como SharePoint Online, Exchange e OneDrive e classifica o conteúdo. Depois de publicar o classificador, você pode continuar a treiná-lo usando um processo de feedback semelhante ao processo de treinamento inicial.

### <a name="where-you-can-use-trainable-classifiers"></a>Onde você pode usar classificadores de treinamento
Os classificadores integrados e os classificadores de treinamento estão disponíveis como uma condição para rotular automaticamente o [Office](apply-sensitivity-label-automatically.md)com rótulos de [sensibilidade,](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) aplicar automaticamente a política de rótulo de retenção com base em uma condição e na conformidade de [comunicação.](communication-compliance.md) 

Os rótulos de sensibilidade podem usar classificadores como condições, consulte Aplicar um [rótulo de sensibilidade ao conteúdo automaticamente.](apply-sensitivity-label-automatically.md)

> [!IMPORTANT]
> Classificadores só funcionam com itens que não são criptografados e estão em inglês.

## <a name="types-of-classifiers"></a>Tipos de classificadores

- **classificadores previamente** treinados - A Microsoft criou e treinamentou previamente vários classificadores que você pode começar a usar sem treinamento. Esses classificadores aparecerão com o status de `Ready to use` .
- **classificadores personalizados** - Se você tiver necessidades de classificação que vão além do que os classificadores previamente treinados cobrem, você pode criar e treinar seus próprios classificadores.

### <a name="pre-trained-classifiers"></a>Classificadores previamente treinados

O Microsoft 365 vem com cinco classificadores previamente treinados:

> [!CAUTION]
> Estamos preterindo  o classificador de Linguagem Ofensiva previamente treinado porque ele está produzindo um grande número de falsos positivos. Não use-o e, se você estiver usando-o no momento, deverá tirar seus processos de negócios dele. Em vez **disso,** **recomendamos** o  uso dos classificadores Ameaças , Profanação e Profanação.

- **Currículos:** detecta itens que são contas textuais de qualificações pessoais, educacionais, profissionais, profissionais e outras informações de identificação pessoal de um candidato
- **Código-fonte**: detecta itens que contêm um conjunto de instruções e instruções escritas nas 25 principais linguagens de programação de computador usadas no GitHub
    - ActionScript
    - C
    - C#
    - C++
    - Tamajure
    - CoffeeScript
    - Ir
    - Hascall
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
> O Código-fonte é treinado para detectar quando a maior parte do texto é o código-fonte. Ele não detecta o texto do código-fonte que é intercalado com texto sem texto simples.

- **Abuso**: detecta uma categoria específica de itens de texto de linguagem ofensiva relacionados à conduta ofensiva, direcionando um ou vários indivíduos com base nas seguintes características: corrida, racial, país de origem, origem nacional, sexo, orientação sexual, idade, deficiência
- **Profanidade**: detecta uma categoria específica de itens de texto de idioma ofensivo que contêm expressões que a maioria das pessoas
- **Ameaça**: detecta uma categoria específica de itens de texto de idioma ofensivos relacionados a ameaças para comprometer a violência ou fazer danos físicos ou danos a uma pessoa ou propriedade

Eles aparecem no centro de **conformidade do Microsoft 365, na** exibição classificadores de classificação de dados  >    >  **tremíveis** com o status de `Ready to use` .

![classificadores-pre-trained-classifiers](../media/classifiers-ready-to-use-classifiers.png)

> [!IMPORTANT]
> Observe que os classificadores de linguagem ofensiva, ofensivo, profanação e ameaças só funcionam com texto pesquisável não são completos ou completos.  Além disso, os padrões de idioma e cultura mudam continuamente e, à luz dessas pessoas, a Microsoft reserva-se o direito de atualizar esses classificadores a seu critério. Embora os classificadores possam ajudar sua organização no monitoramento ofensivo e em outros idiomas usados, os classificadores não abordam as consequências desse idioma e não têm a intenção de fornecer o único meio de monitoramento ou resposta da sua organização ao uso desse idioma. Sua organização, e não a Microsoft ou suas subsidiárias, permanece responsável por todas as decisões relacionadas ao monitoramento, imposição, bloqueio, remoção e retenção de qualquer conteúdo identificado por um classificador previamente treinado.

### <a name="custom-classifiers"></a>Classificadores personalizados

Quando os classificadores previamente treinados não atenderem às suas necessidades, você poderá criar e treinar seus próprios classificadores. Há muito mais trabalho envolvido na criação de suas próprias, mas elas serão muito mais adaptadas às suas necessidades de organizações. 

Por exemplo, você pode criar classificadores de treinamento para:
 
- Documentos jurídicos - como privilégio de advogado cliente, conjuntos de fechamento, declaração de trabalho
- Documentos estratégicos de negócios, como comunicados de imprensa, fusão e aquisição, ofertas, planos de negócios ou marketing, propriedade intelectual, patentes, documentos de design
- Informações de preço - como faturas, cotações, pedidos de trabalho, documentos de documentos de negociação 
- Informações financeiras – como investimentos organizacionais, resultados trimestrais ou anuais    

#### <a name="process-flow-for-creating-custom-classifiers"></a>Fluxo de processo para a criação de classificadores personalizados

A criação e publicação de um classificador para uso em soluções de conformidade, como políticas de retenção e supervisão de comunicação, segue esse fluxo. For more detail on creating a custom trainable classifier see, [Creating a custom classifier](classifier-get-started-with.md).

![classificador personalizado de fluxo de processo](../media/classifier-trainable-classifier-flow.png)

### <a name="retraining-classifiers"></a>Retraining classifiers

Você pode ajudar a melhorar a precisão de todos os classificadores personalizados e alguns classificadores pré-treinados, fornecendo comentários sobre a precisão da classificação que eles executam. Isso é chamado de restrição e siga este fluxo de trabalho.

![fluxo de trabalho de retraining do classificador](../media/classifier-retraining-workflow.png)

## <a name="see-also"></a>Confira também

- [Rótulos de retenção](retention.md)
- [DLP (Prevenção contra perda de dados)](data-loss-prevention-policies.md)
- [Rótulos de confidencialidade](sensitivity-labels.md)
- [Definições da entidade do tipo de informações confidenciais](sensitive-information-type-entity-definitions.md)
- [Impressão digital de documento](document-fingerprinting.md)
- [Exact data match](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
