---
title: Como treinar novamente um classificador em conformidade de comunicações
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
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Saiba como fornecer comentários a um classificador de treinamento em conformidade com as comunicações.
ms.openlocfilehash: cdb8787715c3e022dfa0aa17cd83cc405aeef955
ms.sourcegitcommit: 54d1a2f363b2d5b63aae258c3cec0573a08f2866
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/05/2021
ms.locfileid: "49752645"
---
# <a name="how-to-retrain-a-classifier-in-communications-compliance"></a>Como treinar novamente um classificador em conformidade de comunicações

Um classificador de treinamento do Microsoft 365 é uma ferramenta que você pode treinar para reconhecer vários tipos de conteúdo, dando a ele exemplos para olhar. Depois de treinado, você pode usá-lo para identificar o item para a aplicação de rótulos de sensibilidade do Office, políticas de conformidade de comunicações e políticas de rótulos de retenção.

Este artigo mostra como melhorar o desempenho de classificadores de treinamento personalizados e alguns classificadores pré-treinados fornecendo comentários adicionais.

Para saber mais sobre os diferentes tipos de classificadores, consulte Saiba mais [sobre classificadores de](classifier-learn-about.md)treinamento.

## <a name="permissions"></a>Permissions

Para acessar classificadores no Centro de Conformidade do Microsoft 365:

- a função de administrador de Conformidade ou Administrador de Dados de Conformidade é necessária para treinar um classificador

Você precisará de contas com essas permissões para usar classificadores nestes cenários:

- Cenário de política de conformidade de comunicação: Administrador de Gerenciamento de Riscos Insider, Administrador de Revisão de Supervisão 

## <a name="overall-workflow"></a>Fluxo de trabalho geral

> [!IMPORTANT]
> Você fornece comentários na solução de conformidade que está usando o classificador como uma condição. **Se você não tiver uma política de conformidade de comunicações que use um classificador como uma condição, pare aqui.**

À medida que você usa seus classificadores, talvez você queira aumentar a precisão das classificações que eles estão fazendo. Faça isso avaliando a qualidade das classificações feitas para itens que ele identificou como sendo uma combinação ou não. Depois de fazer 30 avaliações para um classificador, ele recebe esse feedback e se restringe automaticamente.

Para entender mais sobre o fluxo de trabalho geral de restrição de um classificador, consulte o fluxo de processo para [restringir um classificador.](classifier-learn-about.md#retraining-classifiers)

> [!NOTE]
> Um classificador já deve ser publicado e em uso antes de poder ser restringido.

## <a name="how-to-retrain-a-classifier-in-communication-compliance-policies"></a>Como restringir um classificador em políticas de conformidade de comunicação

1. Abra a política de conformidade de comunicação que usa um classificador como uma condição e escolha um dos itens identificados **na** lista Pendente.
2. Escolha as reellipses e **melhore a classificação.**
3. No painel **de comentários detalhado,** se o item for um verdadeiro positivo, escolha, **Corresponder.**  Se o item for um falso positivo, ou seja, foi incluído incorretamente na categoria, escolha **Não uma combinação.**
4. Se houver outro classificador que seria mais apropriado para o item, você pode escolher na lista Sugerir **outros classificadores** que possam ser treinar. Isso disparará o outro classificador para avaliar o item.

> [!TIP]
> Você pode fornecer comentários sobre vários itens simultaneamente escolhendo todos eles e escolhendo Fornecer comentários detalhados **na** barra de comandos.

5. Escolha **Enviar comentários** para enviar sua avaliação das `match` classificações , e sugerir outros `not a match` classificadores de treinamento. Quando você forneceu 30 instâncias de comentários para um classificador, ele será automaticamente restrito. O retraining pode levar de 1 a 4 horas. Os classificadores só podem ser restringidos duas vezes por dia.

> [!IMPORTANT]
> Essas informações vão para o classificador em seu locatário, **ela não volta para a Microsoft**.

6.  Abra a **página Classificação de** dados no centro de conformidade do Microsoft **365.**
7. Open **Trainable classifiers**.
8. O classificador que foi usado em sua política de conformidade de comunicações será exibido sob o título **de Re-treinamento.**

![classificador no status de restrição](../media/classifier-retraining.png)

9. Depois que o retraining for concluído, escolha o classificador para abrir a visão geral de restrição.

![visão geral dos resultados de retraining do classificador](../media/classifier-retraining-overview.png)

10. Revise a ação recomendada e as comparações de previsão das versões restritas e publicadas no momento do classificador.
11. Se você estiver satisfeito com os resultados da restrição, escolha **Re-publicar.**
12. Se você não estiver satisfeito com os resultados da restrição, você pode optar por fornecer comentários adicionais ao classificador na interface de conformidade de comunicações e iniciar outro ciclo de restrição ou não fazer nada nesse caso, a versão publicada no momento do classificador continuará a ser usada. 

## <a name="details-on-republishing-recommendations"></a>Detalhes sobre recomendações de publicação

Aqui estão algumas informações sobre como formular a recomendação para publicar um classificador retrained ou sugerir mais restrições. Isso requer uma compreensão um pouco mais profunda de como os classificadores de treinamento funcionam.

Após um novo treinamento, avaliamos o desempenho do classificador nos itens com comentários, bem como em todos os itens originalmente usados para treinar o classificador. 

- Para modelos integrados, os itens usados para treinar o classificador são os itens usados pela Microsoft para criar o modelo.
- Para modelos personalizados, os itens usados no treinamento original são dos sites que você adicionou para teste e revisão.

Comparamos os números de desempenho em ambos os conjuntos de itens do classificador retrained e published para fornecer uma recomendação sobre se houve melhoria para republicar. 

## <a name="see-also"></a>Confira também

- [Saiba mais sobre classificadores treináveis](classifier-learn-about.md)
- [Extensões de nome de arquivo rastreado padrão e tipos de arquivos analisados no SharePoint Server Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)
