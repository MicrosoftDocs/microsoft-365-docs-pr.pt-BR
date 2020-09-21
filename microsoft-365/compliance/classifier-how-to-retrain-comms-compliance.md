---
title: Como treinar novamente um classificador em conformidade de comunicações (visualização)
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
description: Saiba como fornecer comentários para um classificador treinado em conformidade com comunicações.
ms.openlocfilehash: 1466c211e3a4958f58a7c1f1a6a5a77bed881d60
ms.sourcegitcommit: fdb5f9d865037c0ae23aae34a5c0f06b625b2f69
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2020
ms.locfileid: "48132293"
---
# <a name="how-to-retrain-a-classifier-in-communications-compliance-preview"></a>Como treinar novamente um classificador em conformidade de comunicações (visualização)

Um classificador Microsoft 365 treinado é uma ferramenta que você pode treinar para reconhecer vários tipos de conteúdo dando amostras a eles. Depois de treinado, você pode usá-lo para identificar o item para a aplicação de rótulos de confidencialidade do Office, políticas de conformidade de comunicações e políticas de rótulo de retenção.

Este artigo mostra como melhorar o desempenho de classificadores treinados personalizados e alguns classificadores pré-qualificados, fornecendo comentários adicionais.

Para saber mais sobre os diferentes tipos de classificadores, confira [saiba mais sobre classificadores estagiários (visualização)](classifier-learn-about.md).

## <a name="permissions"></a>Permissões

Para acessar classificadores no centro de conformidade da Microsoft 365:

- a função de administrador de conformidade ou o administrador de dados de conformidade é necessário para treinar um classificador

Você precisará de contas com essas permissões para usar classificadores nestes cenários:

- Cenário de política de conformidade de comunicação: administração de gerenciamento de risco do Insider, administrador de análise de supervisão 

## <a name="overall-workflow"></a>Fluxo de trabalho geral

> [!IMPORTANT]
> Você fornece comentários na solução de conformidade que está usando o classificador como uma condição. **Se você não tiver uma política de conformidade de comunicações que usa um classificador como condição, pare aqui.**

Ao usar seus classificadores, convém aumentar a precisão das classificações que eles estão fazendo. Para fazer isso, avalie a qualidade das classificações feitas para os itens identificados como uma correspondência ou não com uma correspondência. Depois de fazer 30 avaliações de um classificador, o resultado é que ele se retreina automaticamente.

Para entender mais sobre o fluxo de trabalho geral do retreinamento de um classificador, confira o [fluxo de processo para treinar novamente um classificador](classifier-learn-about.md#retraining-classifiers).

> [!NOTE]
> Um classificador já deve estar publicado e em uso para que possa ser retreinado.

## <a name="how-to-retrain-a-classifier-in-communication-compliance-policies-preview"></a>Como treinar novamente um classificador em políticas de conformidade de comunicação (visualização)

1. Abra a política de conformidade de comunicação que usa um classificador como uma condição e escolha um dos itens identificados da lista **pendente** .
2. Escolha as reticências e **aprimore a classificação**.
3. No painel de **comentários detalhado** , se o item for um verdadeiro positivo, escolha, **corresponder**.  Se o item for um falso positivo, ele foi incorretamente incluído na categoria, escolha **não uma correspondência**.
4. Se houver outro classificador que seria mais apropriado para o item, você pode escolher a partir da lista **sugerir outros classificadores estagiários** . Isso disparará o outro classificador para avaliar o item.

> [!TIP]
> Você pode fornecer comentários sobre vários itens simultaneamente escolhendo todos eles e escolhendo **fornecer comentários detalhados** na barra de comandos.

5. Escolha **enviar comentários** para enviar sua avaliação do `match` , `not a match` classificações e sugerir outros classificadores estagiários. Quando você fornecer 30 instâncias de comentários para um classificador, ele será automaticamente retreinada. O retreinamento pode levar de 1-4 horas. Os classificadores só podem ser retreinados duas vezes por dia.

> [!IMPORTANT]
> Essas informações vão para o classificador no locatário, **não volta para a Microsoft**.

6.  Abra a página de **classificação de dados** no centro de **conformidade da Microsoft 365**.
7. Abra **classificadores estagiários (visualização)**.
8. O classificador que foi usado na política de conformidade de comunicações aparecerá sob o título de **novo treinamento** .

![classificador no status de retreinamento](../media/classifier-retraining.png)

9. Após o destreinamento ser concluído, escolha o classificador para abrir a visão geral do retreinamento.

![Visão geral dos resultados do retreinamento do classificador](../media/classifier-retraining-overview.png)

10. Revise a ação recomendada e as comparações de previsão das versões retreinadas e publicadas atualmente do classificador.
11. Se você estiver satisfeito com os resultados do novo treinamento, escolha **republicar**.
12. Se você não estiver satisfeito com os resultados do retreinamento, poderá optar por fornecer comentários adicionais para o classificador na interface de conformidade de comunicações e iniciar outro ciclo de treinamento ou não fazer nada, caso a versão atualmente publicada do classificador continue a ser usada. 

## <a name="details-on-republishing-recommendations"></a>Detalhes sobre como republicar recomendações

Veja aqui algumas informações sobre como formulamos a recomendação para republicar um classificador retreinado ou sugerir um novo treinamento. Isso requer uma compreensão mais profunda de como os classificadores de treinamento funcionam.

Após um retreinamento, avaliamos o desempenho do classificador nos dois itens com comentários, bem como qualquer item usado originalmente para treinar o classificador. 

- Para os modelos internos, os itens usados para treinar o classificador são os itens usados pela Microsoft para criar o modelo.
- Para modelos personalizados, os itens usados no treinamento original o classificador são dos sites que você adicionou para teste e análise.

Comparamos os números de desempenho em ambos os conjuntos de itens para o classificador retreinado e publicado para fornecer uma recomendação sobre se houvesse melhorias na republicação. 

## <a name="see-also"></a>Confira também

- [Saiba mais sobre classificadores estagiários (visualização)](classifier-learn-about.md)
- [Extensões de nome de arquivo rastreado padrão e tipos de arquivos analisados no SharePoint Server Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)
