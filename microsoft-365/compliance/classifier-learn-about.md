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
description: Um classificador do Microsoft 365 treinado é uma ferramenta que você pode treinar para reconhecer vários tipos de conteúdo dando amostras positivas e negativas. Depois que o classificador for treinado, você confirmará que os resultados são precisos. Em seguida, use-o para pesquisar o conteúdo da sua organização e classificá-lo para aplicar os rótulos de retenção ou confidencialidade ou incluí-lo em políticas de retenção ou prevenção de perda de dados (DLP).
ms.openlocfilehash: 0e5f712b76af2fba3d456997a47352773d92d766
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/06/2021
ms.locfileid: "49759895"
---
# <a name="learn-about-trainable-classifiers"></a>Saiba mais sobre classificadores treináveis

Classificar e rotular o conteúdo para que ele possa ser protegido e manipulado adequadamente é o local inicial da disciplina de proteção de informações. O Microsoft 365 tem três maneiras de classificar conteúdo.

## <a name="manually"></a>Manualmente

Esse método requer ações e julgamento humana. Um administrador pode usar os rótulos preexistentes e os tipos de informações confidenciais ou criar seus próprios e publicá-los. Os usuários e administradores aplicam-se ao conteúdo à medida que encontrá-lo. Você pode proteger o conteúdo e gerenciar sua disposição.

## <a name="automated-pattern-matching"></a>Correspondência de padrões automatizados

Esta categoria de mecanismos de classificação inclui localizar conteúdo por:

- Palavras-chave ou valores de metadados (idioma de consulta de palavra-chave).
- Usando padrões identificados anteriormente de informações confidenciais, como segurança social, cartão de crédito ou números de contas bancárias [(definições de entidade de tipo de informação confidencial)](sensitive-information-type-entity-definitions.md).
- Reconhecendo um item porque ele é uma variação em um modelo [(impressão digital de documento)](document-fingerprinting.md).
- Usando a presença de cadeias de caracteres exatas [(correspondência exata de dados)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).

Os rótulos de confidencialidade e retenção podem ser automaticamente aplicados para tornar o conteúdo disponível para uso na [prevenção de perda de dados (DLP)](data-loss-prevention-policies.md) e [aplicar políticas para os rótulos de retenção](apply-retention-labels-automatically.md).

## <a name="classifiers"></a>Classificadores

Esse método de classificação é especialmente adequado ao conteúdo que não é facilmente identificado pelos métodos de correspondência de padrões manuais ou automatizados. Esse método de classificação é mais sobre o treinamento de um classificador para identificar um item com base no que o item é, não por elementos que estão no item (correspondência de padrão). Um classificador aprende como identificar um tipo de conteúdo observando centenas de exemplos do conteúdo que você está interessado em classificar. Comece por alimentar exemplos de ti que são definitivamente na categoria. Depois de processar esses, você o testará dando um mix de exemplos de correspondência e de não correspondência. Em seguida, o classificador faz previsões como se um determinado item está na categoria que você está criando. Em seguida, você confirma seus resultados, classificando os positivos verdadeiros, verdadeiros negativos, falsos positivos e falsos negativos para ajudar a aumentar a precisão de suas previsões. 

Quando você publica o classificador, ele classifica itens em locais como o SharePoint Online, o Exchange e o OneDrive e classifica o conteúdo. Após publicar o classificador, você pode continuar a treiná-lo usando um processo de feedback semelhante ao processo de treinamento inicial.

### <a name="where-you-can-use-trainable-classifiers"></a>Onde você pode usar os classificadores estagiários
Tanto classificadores internos quanto classificadores estagiários estão disponíveis como uma condição para o [Office autolabeling com rótulos de sensibilidade](apply-sensitivity-label-automatically.md), [aplicar automaticamente a política de rótulo de retenção com base em uma condição](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) e em [conformidade de comunicação](communication-compliance.md). 

Os rótulos de confidencialidade podem usar classificadores como condições, consulte [aplicar um rótulo de confidencialidade ao conteúdo automaticamente](apply-sensitivity-label-automatically.md).

> [!IMPORTANT]
> Os classificadores só funcionam com itens não criptografados e estão em inglês.

## <a name="types-of-classifiers"></a>Tipos de classificadores

- **classificadores já treinados** -a Microsoft criou e treinava um número de classificadores que você pode começar a usar sem treinar. Esses classificadores serão exibidos com o status de `Ready to use` .
- **classificadores personalizados** : se você tiver necessidades de classificação que vão além do que os classificadores já treinados cobrem, você pode criar e treinar seus próprios classificadores.

### <a name="pre-trained-classifiers"></a>Classificadores pré-qualificados

A Microsoft 365 vem com cinco classificadores pré-qualificados:

> [!CAUTION]
> Estamos preterindo o classificador de **idiomas ofensivos** antes de produzir um grande número de falsos positivos. Não usá-lo e, se estiver usando, você deverá mover seus processos de negócios para fora dele. É recomendável usar os classificadores treinados **contra ameaças**, **profanação** e **assédio** .

- **Currículos**: detecta itens que são contas de texto das qualificações pessoais, educacionais, profissionais, experiência de trabalho e outras informações de identificação pessoal de um candidato
- **Código-fonte**: detecta itens que contêm um conjunto de instruções e instruções escritas nas principais linguagens de programação de computador usadas no github
    - Código
    - C
    - C#
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
    - Scale
    - Shell
    - Swift
    - Tex
    - Script vim

> [!NOTE]
> O código-fonte é treinado para detectar quando a maior parte do texto é o código-fonte. Ele não detecta o texto do código-fonte que é intercalado com texto sem formatação.

- **Assédio**: detecta uma categoria específica de itens de texto de linguagem ofensiva relacionadas à conduta ofensiva direcionando uma ou várias pessoas com base nas seguintes características: corrida, étnica, Religion, origem nacional, sexo, orientação sexual, idade, deficiência
- **Profanação**: detecta uma categoria específica de itens de texto de idioma ofensivo que contêm expressões que constrangim a maioria das pessoas
- **Ameaça**: detecta uma categoria específica de itens de texto de linguagem ofensiva relacionadas a ameaças para confirmar a violência ou danos físicos ou danos a uma pessoa ou a uma propriedade

Eles aparecem na classificação de dados do **centro de conformidade da Microsoft 365**  >    >  exibição de **classificadores estagiários** com o status de `Ready to use` .

![classificadores-classificadores pré treinado](../media/classifiers-ready-to-use-classifiers.png)

> [!IMPORTANT]
> Observe que a linguagem ofensiva, assédio, profanação e classificadores de ameaças só funcionam com o texto pesquisável não é completo nem completo.  Além disso, os padrões culturais e de idioma mudam continuamente e, em claro, a Microsoft reserva-se o direito de atualizar esses classificadores em seu critério. Embora os classificadores possam ajudar sua organização a monitorar ofensivas e outros idiomas usados, os classificadores não resolvem as conseqüências de tal linguagem e não se destinam a fornecer o único meio de monitoramento ou resposta ao uso dessa linguagem. Sua organização, e não a Microsoft ou suas subsidiárias, permanece responsável por todas as decisões relacionadas ao monitoramento, imposição, bloqueio, remoção e retenção de qualquer conteúdo identificado por um classificador treinado.

### <a name="custom-classifiers"></a>Classificadores personalizados

Quando os classificadores treinados não atenderem às suas necessidades, você poderá criar e treinar seus próprios classificadores. Há muito mais trabalho envolvido na criação de suas próprias, mas eles serão muito mais adequados às suas necessidades de organizações. 

Por exemplo, você poderia criar classificadores estagiários para:
 
- Documentos legais, como privilégio de cliente de advogados, conjuntos de fechamento, proposta de serviço
- Documentos estratégicos de negócios, como Press Releases, fusão e aquisição, negócios, planos de negócios ou marketing, propriedade intelectual, patentes, documentos de design
- Informações sobre preços-como faturas, cotações de preços, pedidos de trabalho, documentos de apostas 
- Informações financeiras – como investimentos organizacionais, resultados trimestrais ou anuais    

#### <a name="process-flow-for-creating-custom-classifiers"></a>Fluxo do processo de criação de classificadores personalizados

A criação e publicação de um classificador para uso em soluções de conformidade, como políticas de retenção e supervisão de comunicação, segue este fluxo. Para obter mais detalhes sobre como criar um classificador treinado personalizado, consulte [criando um classificador personalizado](classifier-get-started-with.md).

![classificador personalizado de fluxo de processo](../media/classifier-trainable-classifier-flow.png)

### <a name="retraining-classifiers"></a>Retreinando classificadores

Você pode ajudar a melhorar a precisão de todos os classificadores personalizados e alguns classificadores pré-qualificados, fornecendo comentários sobre a precisão da classificação que eles executam. Isso é chamado de retreinamento e acompanhamento deste fluxo de trabalho.

![fluxo de trabalho de retreinamento do classificador](../media/classifier-retraining-workflow.png)

## <a name="see-also"></a>Confira também

- [Rótulos de retenção](retention.md)
- [DLP (Prevenção contra perda de dados)](data-loss-prevention-policies.md)
- [Rótulos de confidencialidade](sensitivity-labels.md)
- [Definições da entidade do tipo de informações confidenciais](sensitive-information-type-entity-definitions.md)
- [Impressão digital do documento](document-fingerprinting.md)
- [Correspondência de dados exata](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
