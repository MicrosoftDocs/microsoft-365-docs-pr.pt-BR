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
description: Saiba como fornecer comentários a um classificador treinável em conformidade com comunicações.
ms.openlocfilehash: 75fff8220b052618c70a6490b8c3569c11ecc861
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918142"
---
# <a name="how-to-retrain-a-classifier-in-communications-compliance"></a>Como treinar novamente um classificador em conformidade de comunicações

Um classificador de treinamento do Microsoft 365 é uma ferramenta que você pode treinar para reconhecer vários tipos de conteúdo, dando a ele exemplos para ver. Depois de treinado, você pode usá-lo para identificar o item para a aplicação de rótulos de sensibilidade do Office, políticas de conformidade de comunicações e políticas de rótulo de retenção.

Este artigo mostra como melhorar o desempenho de classificadores treinados personalizados e alguns classificadores pré-treinados fornecendo comentários adicionais.

Para saber mais sobre os diferentes tipos de classificadores, consulte [Learn about trainable classifiers](classifier-learn-about.md).

## <a name="permissions"></a>Permissões

Para acessar classificadores no Centro de Conformidade do Microsoft 365:

- a função de administrador de conformidade ou Administrador de Dados de Conformidade é necessária para treinar um classificador

Você precisará de contas com essas permissões para usar classificadores nesses cenários:

- Cenário de política de conformidade de comunicação: Administrador de Gerenciamento de Riscos do Insider, Administrador de Revisão de Supervisão 

## <a name="overall-workflow"></a>Fluxo de trabalho geral

> [!IMPORTANT]
> Você fornece comentários na solução de conformidade que está usando o classificador como uma condição. **Se você não tiver uma política de conformidade de comunicações que use um classificador como condição, pare aqui.**

À medida que você usa seus classificadores, talvez você queira aumentar a precisão das classificações que eles estão fazendo. Você faz isso avaliando a qualidade das classificações feitas para itens identificados como sendo uma combinação ou não uma combinação. Depois de fazer 30 avaliações para um classificador, ele recebe os comentários e se retreina automaticamente.

Para entender mais sobre o fluxo de trabalho geral de retreinamento de um classificador, consulte Fluxo de processos para [retreinar um classificador](classifier-learn-about.md#retraining-classifiers).

> [!NOTE]
> Um classificador já deve ser publicado e em uso antes de poder ser retreinado.

## <a name="how-to-retrain-a-classifier-in-communication-compliance-policies"></a>Como retreinar um classificador em políticas de conformidade de comunicação

1. Abra a política de conformidade de comunicação que usa um classificador como uma condição e escolha um dos itens identificados na lista **Pendente.**
2. Escolha as releições e **Melhorar a classificação.**
3. No painel **comentários detalhados,** se o item for um verdadeiro positivo, escolha, **Corresponder**.  Se o item for um falso positivo, ou seja, ele foi incluído incorretamente na categoria, escolha **Não uma combinação**.
4. Se houver outro classificador que seria mais apropriado para o item, você pode escolher-o na lista Sugerir outros classificadores **treináveis.** Isso disparará o outro classificador para avaliar o item.

> [!TIP]
> Você pode fornecer comentários sobre vários itens simultaneamente escolhendo-os todos e escolhendo Fornecer **comentários** detalhados na barra de comandos.

5. Escolha **Enviar comentários** para enviar sua avaliação das `match` classificações , e sugerir outros `not a match` classificadores com treinamento. Quando você forneceu 30 instâncias de comentários para um classificador, ele será retreinado automaticamente. A retreinamento pode levar de 1 a 4 horas. Os classificadores só podem ser retreinados duas vezes por dia.

> [!IMPORTANT]
> Essas informações vão para o classificador em seu locatário, **ela não volta para a Microsoft**.

6.  Abra a **página classificação de** dados no centro de conformidade do Microsoft **365.**
7. Abra **classificadores com treinamento.**
8. O classificador que foi usado em sua política de conformidade de Comunicações aparecerá sob o **título Re-training.**

![classificador no status de retreinamento](../media/classifier-retraining.png)

9. Depois de concluir a retreinamento, escolha o classificador para abrir a visão geral de retreinamento.

![visão geral dos resultados de retreinamento do classificador](../media/classifier-retraining-overview.png)

10. Revise a ação recomendada e as comparações de previsão das versões retreinadas e publicadas no momento do classificador.
11. Se você estiver satisfeito com os resultados da retreinamento, escolha **Publicar de novo.**
12. Se você não estiver satisfeito com os resultados do retreinamento, poderá optar por fornecer comentários adicionais ao classificador na interface de conformidade de comunicações e iniciar outro ciclo de retreinamento ou não fazer nada nesse caso, caso em que a versão publicada no momento do classificador continuará a ser usada. 

## <a name="details-on-republishing-recommendations"></a>Detalhes sobre recomendações de redação

Aqui estão algumas informações sobre como formulamos a recomendação para publicar um classificador retreinado ou sugerir um novo treinamento. Isso requer uma compreensão um pouco mais profunda de como os classificadores treináveis funcionam.

Após um retreinamento, avaliamos o desempenho do classificador nos itens com comentários, bem como em todos os itens originalmente usados para treinar o classificador. 

- Para modelos integrados, os itens usados para treinar o classificador são os itens usados pela Microsoft para criar o modelo.
- Para modelos personalizados, os itens usados no treinamento original do classificador são dos sites que você adicionou para teste e revisão.

Comparamos os números de desempenho em ambos os conjuntos de itens para o classificador retreinado e publicado para fornecer uma recomendação sobre se houve melhoria para republicar. 

## <a name="see-also"></a>Confira também

- [Saiba mais sobre classificadores treináveis](classifier-learn-about.md)
- [Extensões de nome de arquivo rastreado padrão e tipos de arquivos analisados no SharePoint Server Server](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)