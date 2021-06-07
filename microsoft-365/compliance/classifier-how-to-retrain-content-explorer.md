---
title: Como treinar novamente um classificador no explorador de conteúdo
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
description: Saiba como fornecer comentários a um classificador treinável no Explorador de conteúdo.
ms.openlocfilehash: ef0539a3d474ffecaeac8633b4a58aa068a5c182
ms.sourcegitcommit: f3d1009840513703c38bab99a6e13a3656eae5ee
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/07/2021
ms.locfileid: "52793059"
---
# <a name="how-to-retrain-a-classifier-in-content-explorer"></a>Como treinar novamente um classificador no explorador de conteúdo

Um Microsoft 365 classificador treinável é uma ferramenta que você pode treinar para reconhecer vários tipos de conteúdo, dando a ele exemplos para ver. Depois de treinado, você pode usá-lo para identificar o item para a aplicação de rótulos de Office de sensibilidade, políticas de conformidade de comunicações e políticas de rótulo de retenção.

Este artigo mostra como melhorar o desempenho de classificadores treinados personalizados e alguns classificadores pré-treinados fornecendo comentários adicionais.

Para saber mais sobre os diferentes tipos de classificadores, consulte [Learn about trainable classifiers](classifier-learn-about.md).

Assista a este vídeo para um resumo rápido do processo de ajuste e retreinamento. Você ainda precisará ler este artigo completo para obter os detalhes.

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWyGMs]


## <a name="permissions"></a>Permissões

Para acessar classificadores no centro Microsoft 365 Conformidade:

- a função de administrador de conformidade ou Administrador de Dados de Conformidade é necessária para treinar um classificador

Você precisará de contas com essas permissões para usar classificadores nesses cenários:

- Cenário de política de rótulo de retenção: funções de Gerenciamento de Registros e Gerenciamento de Retenção 

## <a name="overall-workflow"></a>Fluxo de trabalho geral

> [!IMPORTANT]
> Você fornece comentários no explorador de conteúdo para aplicar automaticamente políticas de rótulo de retenção Exchange itens e usa o classificador como uma condição. **Se você não tiver uma política de retenção que aplique automaticamente um rótulo de retenção Exchange itens e use um classificador como condição, pare aqui.**

À medida que você usa seus classificadores, talvez você queira aumentar a precisão das classificações que eles estão fazendo. Você faz isso avaliando a qualidade das classificações feitas para itens identificados como sendo uma combinação ou não uma combinação. Depois de fazer 30 avaliações para um classificador, ele recebe os comentários e se retreina automaticamente.

Para entender mais sobre o fluxo de trabalho geral de retreinamento de um classificador, consulte Fluxo de processos para [retreinar um classificador](classifier-learn-about.md#retraining-classifiers).

> [!NOTE]
> Um classificador já deve ser publicado e em uso antes de poder ser retreinado.

## <a name="how-to-retrain-a-classifier-in-content-explorer"></a>Como treinar novamente um classificador no explorador de conteúdo

1. Entre no centro Microsoft 365 de conformidade com o administrador de conformidade ou acesso **à** função de administrador de segurança e abra Microsoft 365 centro de conformidade  >  **Data classification**  >  **Data classification Explorador de conteúdo**. 
2. Na lista **Filtrar rótulos, tipos de informações ou** **categorias,** expanda classificadores com treinamento.

> [!IMPORTANT]
> Pode levar até oito dias para que os itens agregados apareçam sob o título de classificadores treináveis.

3. Escolha o classificador treinável que você usou em sua política de rótulo de retenção de aplicação automática. Este é o classificador treinável sobre o que você dará comentários.

> [!NOTE]
> Se um item tiver uma entrada na coluna **Rótulo de** retenção, isso significa que o item foi classificado como `match` um .  Se um item não tiver uma entrada na coluna **Rótulo** de retenção, isso significa que ele foi classificado como `close match` um . Você pode melhorar mais a precisão do classificador fornecendo comentários sobre `close match` itens. 

4. Escolha um item e abra-o.
 
 > [!TIP]
> Você pode fornecer comentários sobre vários itens simultaneamente escolhendo-os todos e escolhendo **Melhorar a classificação** na barra de comandos.

5. Escolha **Fornecer comentários**.
6. No painel **comentários detalhados,** se o item for um verdadeiro positivo, escolha, **Corresponder**.  Se o item for um falso positivo, ou seja, ele foi incluído incorretamente na categoria, escolha **Não uma combinação**.
7. Se houver outro classificador que seria mais apropriado para o item, você pode escolher-o na lista Sugerir outros classificadores **treináveis.** Isso disparará o outro classificador para avaliar o item.
8. Escolha **Enviar comentários** para enviar sua avaliação das `match` classificações , e sugerir outros `not a match` classificadores com treinamento. Quando você forneceu 30 instâncias de comentários para um classificador, ele será retreinado automaticamente. A retreinamento pode levar de uma a quatro horas. Os classificadores só podem ser retreinados duas vezes por dia.

> [!IMPORTANT]
> Essas informações vão para o classificador em seu locatário, **ela não volta para a Microsoft**.

9. Abra **classificadores com treinamento.**
10. O classificador que foi usado em sua política de conformidade de Comunicações aparecerá sob o **título Re-training.**

![classificador no status de retreinamento](../media/classifier-retraining.png)

11. Depois de concluir a retreinamento, escolha o classificador para abrir a visão geral de retreinamento.

![visão geral dos resultados de retreinamento do classificador](../media/classifier-retraining-overview.png)

12. Revise a ação recomendada e as comparações de previsão das versões retreinadas e publicadas no momento do classificador.
13. Se você estiver satisfeito com os resultados da retreinamento, escolha **Publicar de novo.**
14. Se você não estiver satisfeito com os resultados do retreinamento, poderá optar por fornecer comentários adicionais ao classificador na interface do Explorador de Conteúdo e iniciar outro ciclo de retreinamento ou não fazer nada nesse caso, caso em que a versão publicada no momento do classificador continuará a ser usada. 

## <a name="details-on-republishing-recommendations"></a>Detalhes sobre recomendações de redação

Aqui estão algumas informações sobre como formulamos a recomendação para publicar um classificador retreinado ou sugerir um novo treinamento. Isso requer uma compreensão um pouco mais profunda de como os classificadores treináveis funcionam.

Após um retreinamento, avaliamos o desempenho do classificador nos itens com comentários, bem como em todos os itens originalmente usados para treinar o classificador. 

- Para modelos integrados, os itens usados para treinar o classificador são os itens usados pela Microsoft para criar o modelo.
- Para modelos personalizados, os itens usados no treinamento original do classificador são dos sites que você adicionou para teste e revisão.

Comparamos os números de desempenho em ambos os conjuntos de itens para o classificador retreinado e publicado para fornecer uma recomendação sobre se houve melhoria para republicar. 

## <a name="see-also"></a>Confira também

- [Saiba mais sobre classificadores treináveis](classifier-learn-about.md)
- [Extensões de nome de arquivo rastreado padrão e tipos de arquivos analisados no SharePoint Server Server](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)