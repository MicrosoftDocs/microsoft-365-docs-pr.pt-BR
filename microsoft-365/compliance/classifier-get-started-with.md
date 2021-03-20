---
title: Comece com classificadores treináveis
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
description: Um classificador do Microsoft 365 é uma ferramenta que você pode treinar para reconhecer vários tipos de conteúdo, dando a ele exemplos para ver. Este artigo mostra como criar e treinar um classificador personalizado e como retreiná-los para aumentar a precisão.
ms.openlocfilehash: 90e47ec94528bbadeb98dc9eb590929e25ae6ff1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918175"
---
# <a name="get-started-with-trainable-classifiers"></a>Comece com classificadores treináveis

Um classificador de treinamento do Microsoft 365 é uma ferramenta que você pode treinar para reconhecer vários tipos de conteúdo, dando a ele exemplos para ver. Depois de treinado, você pode usá-lo para identificar o item para a aplicação de rótulos de sensibilidade do Office, políticas de conformidade de comunicações e políticas de rótulo de retenção.

A criação de um classificador treinável personalizado primeiro envolve dar a ele exemplos que são escolhidos por humanos e que corresponderão positivamente à categoria. Em seguida, depois de processá-los, você testa a capacidade dos classificadores de prever, dando a ele uma mistura de exemplos positivos e negativos. Este artigo mostra como criar e treinar um classificador personalizado e como melhorar o desempenho de classificadores treinados personalizados e classificadores pré-treinados ao longo da vida através da retreinamento.

Para saber mais sobre os diferentes tipos de classificadores, consulte [Learn about trainable classifiers](classifier-learn-about.md).

Assista a este vídeo para um resumo rápido da criação de um classificador treinável. Você ainda precisará ler este artigo completo para obter os detalhes.

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWyGL7]


## <a name="prerequisites"></a>Pré-requisitos

### <a name="licensing-requirements"></a>Requisitos de licença

Classificadores são um recurso de Conformidade do Microsoft 365 E5 ou E5. Você deve ter uma dessas assinaturas para usá-las.

### <a name="permissions"></a>Permissões

Para acessar classificadores na interface do usuário: 

- o administrador global precisa optar pelo locatário para criar classificadores personalizados.
- A função administrador de conformidade é necessária para treinar um classificador.

Você precisará de contas com essas permissões para usar classificadores nesses cenários:

- Cenário de política de rótulo de retenção: funções de Gerenciamento de Registros e Gerenciamento de Retenção 
- Cenário de política de rótulo de sensibilidade: Administrador de Segurança, Administrador de Conformidade, Administrador de Dados de Conformidade
- Cenário de política de conformidade de comunicação: Administrador de Gerenciamento de Riscos do Insider, Administrador de Revisão de Supervisão 

> [!IMPORTANT]
> Por padrão, somente o usuário que cria um classificador personalizado pode treinar e revisar previsões feitas por esse classificador.

## <a name="prepare-for-a-custom-trainable-classifier"></a>Preparar para um classificador de treinamento personalizado 

É útil entender o que está envolvido na criação de um classificador de treinamento personalizado antes de entrar. 

### <a name="timeline"></a>Linha do tempo

Essa linha do tempo reflete uma implantação de exemplo de classificadores treináveis.

![trainable-classifier-timeline](../media/trainable-classifier-deployment-timeline_border.png)

> [!TIP]
> A aceitação é necessária pela primeira vez para classificadores que podem treinar. Leva doze dias para o Microsoft 365 concluir uma avaliação de linha de base do conteúdo de suas organizações. Entre em contato com o administrador global para dar início ao processo de aceitação.

### <a name="overall-workflow"></a>Fluxo de trabalho geral

Para entender mais sobre o fluxo de trabalho geral da criação de classificadores treináveis personalizados, consulte Fluxo de processos para criar classificadores de treinamento [do cliente.](classifier-learn-about.md#process-flow-for-creating-custom-classifiers)

### <a name="seed-content"></a>Conteúdo de sementes

Quando você deseja que um classificador treinável identifique de forma independente e precisa um item como sendo uma categoria específica de conteúdo, primeiro você precisa apresentá-lo com muitos exemplos do tipo de conteúdo que estão na categoria. Essa alimentação de amostras para o classificador treinável é conhecida como *semeamento*. O conteúdo de semente é selecionado por um humano e é considerado para representar a categoria de conteúdo.

> [!TIP]
> Você precisa ter pelo menos 50 amostras positivas e até 500. O classificador treinável processará até os 500 exemplos criados mais recentes (por arquivo criado data/carimbo de hora). Quanto mais amostras você fornecer, mais precisas serão as previsões que o classificador fará.

### <a name="testing-content"></a>Testar conteúdo

Depois que o classificador treinável tiver processado amostras positivas suficientes para criar um modelo de previsão, você precisará testar as previsões que ele faz para ver se o classificador pode distinguir corretamente entre itens que corresponderem à categoria e itens que não são. Você faz isso selecionando outro conjunto, com sorte maior, de conteúdo escolhido humano que consiste em amostras que devem se enquadrar na categoria e em exemplos que não. Você deve testar com dados diferentes dos dados de semente iniciais fornecidos pela primeira vez. Depois de processá-los, você passa manualmente pelos resultados e verifica se cada previsão está correta, incorreta ou não. O classificador treinável usa esse feedback para melhorar seu modelo de previsão.

> [!TIP]
> Para melhores resultados, tenha pelo menos 200 itens no conjunto de amostras de teste com uma distribuição uniforme de resultados positivos e negativos.

## <a name="how-to-create-a-trainable-classifier"></a>Como criar um classificador treinável

1. Coletar entre 50 e 500 itens de conteúdo de semente. Esses devem ser apenas exemplos que representam fortemente o tipo de conteúdo que você deseja que o classificador treinável identifique positivamente como estando na categoria de classificação. Consulte [Extensões de nome de arquivo](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) rastreado padrão e tipos de arquivo analisados no SharePoint Server para os tipos de arquivo com suporte.

   > [!IMPORTANT]
   > Os itens de amostra de semente e teste não devem ser criptografados e devem estar em inglês.

   > [!IMPORTANT]
   > Certifique-se de que os itens no conjunto de sementes sejam **exemplos** fortes da categoria. O classificador treinável cria inicialmente seu modelo com base no que você o semeou. O classificador supõe que todos os exemplos de semente são positivos fortes e não têm como saber se uma amostra é uma combinação fraca ou negativa com a categoria.

2. Coloque o conteúdo de semente em uma pasta do SharePoint Online dedicada a manter o *conteúdo de semente somente*. Anote a URL do site, biblioteca e pasta.

   > [!TIP]
   > Se você criar um novo site e pasta para seus dados de semente, permita pelo menos uma hora para que esse local seja indexado antes de criar o classificador treinável que usará esses dados de semente.

3. Entre no Centro de conformidade do Microsoft 365 com acesso a funções de administrador de conformidade ou de administrador de segurança e abra o Centro de conformidade do **Microsoft 365** ou a classificação de dados do Centro de Segurança do **Microsoft 365.**  >  

4. Escolha a **guia Classificadores treináveis.**

5. Escolha **Criar classificador treinável**.

6. Preencha os valores apropriados para os campos e da categoria de itens que você deseja que esse `Name` `Description` classificador treinável identifique.

7. Escolha a URL de site, biblioteca e pasta do SharePoint Online para o site de conteúdo de semente na etapa 2. Escolha `Add` .

8. Revise as configurações e escolha `Create trainable classifier` .

9. Dentro de 24 horas, o classificador treinável processará os dados de semente e criará um modelo de previsão. O status do classificador é `In progress` enquanto processa os dados de semente. Quando o classificador terminar de processar os dados de semente, o status muda para `Need test items` .

10. Agora você pode exibir a página de detalhes escolhendo o classificador.

    > [!div class="mx-imgBorder"]
    > ![classificador treinável pronto para teste](../media/classifier-trainable-ready-to-test-detail.png)

11. Colete pelo menos 200 itens de conteúdo de teste (10.000 no máximo) para melhores resultados. Eles devem ser uma mistura de itens que são positivos fortes, negativos fortes e alguns que são um pouco menos óbvios em sua natureza. Consulte [Extensões de nome de arquivo](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) rastreado padrão e tipos de arquivo analisados no SharePoint Server para os tipos de arquivo com suporte.

    > [!IMPORTANT]
    > Os itens de exemplo não devem ser criptografados e devem estar em inglês.

12. Coloque o conteúdo de teste em uma pasta do SharePoint Online dedicada a manter *o conteúdo de teste somente*. Anote a URL de site, biblioteca e pasta do SharePoint Online.

    > [!TIP]
    > Se você criar um novo site e uma pasta para seus dados de teste, permita pelo menos uma hora para que esse local seja indexado antes de criar o classificador treinável que usará esses dados de semente.

13. Escolha `Add items to test` .

14. Escolha a URL de site, biblioteca e pasta do SharePoint Online para o site de conteúdo de teste na etapa 12. Escolha `Add` .

15. Termine o assistente escolhendo `Done` . O classificador treinável levará até uma hora para processar os arquivos de teste.

16. Quando o classificador treinável terminar de processar seus arquivos de teste, o status na página de detalhes será alterado para `Ready to review` . Se você precisar aumentar o tamanho do exemplo de teste, escolha e permita que o classificador treinável `Add items to test` processe os itens adicionais.

    > [!div class="mx-imgBorder"]
    > ![pronto para revisar captura de tela](../media/classifier-trainable-ready-to-review-detail.png)

17. Escolha `Tested items to review` a guia para revisar itens.

18. O Microsoft 365 apresentará 30 itens por vez. Revise-os `We predict this item is "Relevant". Do you agree?` e, na caixa, escolha `Yes` um ou ou `No` `Not sure, skip to next item` . A precisão do modelo é atualizada automaticamente após cada 30 itens.

    > [!div class="mx-imgBorder"]
    > ![caixa de itens de revisão](../media/classifier-trainable-review-detail.png)

19. Revise *pelo menos* 200 itens. Depois que a pontuação de precisão tiver estabilizado, a opção **de** publicação ficará disponível e o status do classificador dirá `Ready to use` .

    > [!div class="mx-imgBorder"]
    > ![pontuação de precisão e pronto para publicação](../media/classifier-trainable-review-ready-to-publish.png)

20. Publique o classificador.

21. Depois de publicado, o classificador estará disponível como uma condição na rotulagem automática do [Office](apply-sensitivity-label-automatically.md)com rótulos de [sensibilidade,](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) aplicar automaticamente a política de rótulo de retenção com base em uma condição e em Conformidade com [a comunicação.](communication-compliance.md)