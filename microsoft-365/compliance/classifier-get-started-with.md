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
description: Um classificador do Microsoft 365 é uma ferramenta que você pode treinar para reconhecer vários tipos de conteúdo, dando a ele exemplos para olhar. Este artigo mostra como criar e treinar um classificador personalizado e como restringi-los para aumentar a precisão.
ms.openlocfilehash: bca1de5edc3efd38f943b02091c3f47d832e6a19
ms.sourcegitcommit: 54d1a2f363b2d5b63aae258c3cec0573a08f2866
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/05/2021
ms.locfileid: "49752655"
---
# <a name="get-started-with-trainable-classifiers"></a>Comece com classificadores treináveis

Um classificador de treinamento do Microsoft 365 é uma ferramenta que você pode treinar para reconhecer vários tipos de conteúdo, dando a ele exemplos para olhar. Depois de treinado, você pode usá-lo para identificar o item para a aplicação de rótulos de sensibilidade do Office, políticas de conformidade de comunicações e políticas de rótulo de retenção.

A criação de um classificador de treinamento personalizado primeiro envolve dar a ele amostras que são escolhidas por humanos e que são positivas se igualam à categoria. Em seguida, depois de processá-los, teste a capacidade dos classificadores de prever, dando a ele uma mistura de amostras positivas e negativas. Este artigo mostra como criar e treinar um classificador personalizado e como melhorar o desempenho de classificadores de treinamento personalizados e classificadores previamente treinados durante sua vida útil por meio de treinamento.

Para saber mais sobre os diferentes tipos de classificadores, consulte Saiba mais [sobre classificadores de](classifier-learn-about.md)treinamento.

## <a name="prerequisites"></a>Pré-requisitos

### <a name="licensing-requirements"></a>Requisitos de licença

Classificadores são um recurso de Conformidade do Microsoft 365 E5 ou E5. Você deve ter uma dessas assinaturas para usá-las.

### <a name="permissions"></a>Permissions

Para acessar classificadores na interface do usuário: 

- o administrador global precisa optar pelo locatário para criar classificadores personalizados.
- A função administrador de conformidade é necessária para treinar um classificador.

Você precisará de contas com essas permissões para usar classificadores nestes cenários:

- Cenário de política de rótulo de retenção: funções de Gerenciamento de Registros e Gerenciamento de Retenção 
- Cenário de política de rótulo de sensibilidade: Administrador de Segurança, Administrador de Conformidade, Administrador de Dados de Conformidade
- Cenário de política de conformidade de comunicação: Administrador de Gerenciamento de Riscos Insider, Administrador de Revisão de Supervisão 

> [!IMPORTANT]
> Por padrão, somente o usuário que cria um classificador personalizado pode treinar e revisar as previsões feitas por esse classificador.

## <a name="prepare-for-a-custom-trainable-classifier"></a>Preparar para um classificador de treinamento personalizado 

É útil entender o que está envolvido na criação de um classificador de treinamento personalizado antes de entrar. 

### <a name="timeline"></a>Linha do tempo

Essa linha do tempo reflete uma implantação de exemplo de classificadores de treinamento.

![trainable-classifier-timeline](../media/trainable-classifier-deployment-timeline_border.png)

> [!TIP]
> A aceitação é necessária pela primeira vez para classificadores de treinamento. O Microsoft 365 leva doze dias para concluir uma avaliação de linha de base do conteúdo de suas organizações. Entre em contato com seu administrador global para dar início ao processo de aceitação.

### <a name="overall-workflow"></a>Fluxo de trabalho geral

Para entender mais sobre o fluxo de trabalho geral de criação de classificadores de treinamento personalizados, consulte o fluxo de processo para criar classificadores de treinamento [do cliente.](classifier-learn-about.md#process-flow-for-creating-custom-classifiers)

### <a name="seed-content"></a>Conteúdo da semente

Quando você quiser que um classificador de treinamento identifique de forma independente e precisa um item como estando em uma categoria específica de conteúdo, primeiro você precisa apresentá-lo com muitos exemplos do tipo de conteúdo que está na categoria. Essa alimentação de amostras para o classificador de treinamento é conhecida *como a semeação.* O conteúdo da semente é selecionado por um humano e é destruído a representar a categoria de conteúdo.

> [!TIP]
> Você precisa ter pelo menos 50 amostras positivas e até 500. O classificador de treinamento processará até os 500 exemplos criados mais recentes (por carimbo de data/hora criado pelo arquivo). Quanto mais amostras você fornecer, mais precisa será a previsão que o classificador fará.

### <a name="testing-content"></a>Testando conteúdo

Depois que o classificador de treinamento tiver processado amostras positivas suficientes para criar um modelo de previsão, você precisará testar as previsões que ele faz para ver se o classificador pode distinguir corretamente entre itens que corresponderem à categoria e itens que não fazem isso. Você pode fazer isso selecionando outro conjunto maior, com certeza, de conteúdo escolhido por humanos que consiste em exemplos que devem se enquadrar na categoria e em amostras que não se enquadram. Você deve testar com dados diferentes dos dados de pesquisa iniciais fornecidos pela primeira vez. Depois de processá-los, você passa manualmente pelos resultados e verifica se cada previsão está correta, incorreta ou se não tem certeza. O classificador de treinamento usa esse feedback para melhorar seu modelo de previsão.

> [!TIP]
> Para melhores resultados, tenha pelo menos 200 itens no conjunto de amostras de teste com uma distribuição uniforme de resultados positivos e negativos.

## <a name="how-to-create-a-trainable-classifier"></a>Como criar um classificador de treinamento

1. Coletar entre 50 e 500 itens de conteúdo de semente. Esses devem ser apenas exemplos que representam fortemente o tipo de conteúdo que você deseja que o classificador de treinamento identifique positivamente como estando na categoria de classificação. Consulte [extensões de nome de arquivo rastreado padrão](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) e tipos de arquivo analisados no SharePoint Server para os tipos de arquivo com suporte.

   > [!IMPORTANT]
   > Os itens de exemplo de teste e de semente não devem ser criptografados e devem estar em inglês.

   > [!IMPORTANT]
   > Certifique-se de que os itens em seu conjunto de dados **sejam exemplos** fortes da categoria. O classificador inicializável cria seu modelo com base no que você o comou. O classificador supõe que todas as amostras de semente são fortes positivos e não tem como saber se uma amostra é uma combinação fraca ou negativa com a categoria.

2. Coloque o conteúdo de semente em uma pasta do SharePoint Online que seja dedicada a manter o *conteúdo somente de dados.* Anote o site, a biblioteca e a URL da pasta.

   > [!TIP]
   > Se você criar um novo site e pasta para os dados de sua pesquisa, permita que, pelo menos, uma hora para esse local seja indexado antes de criar o classificador de treinamento que usará esses dados de pesquisa.

3. Entre no Centro de conformidade do Microsoft 365 com acesso à função de administrador de conformidade ou administrador de segurança e abra o Centro de conformidade do **Microsoft 365** ou centro de segurança do **Microsoft 365** Classificação de  >  **dados.**

4. Escolha a **guia Classificadores De treinamento.**

5. Choose **Create trainable classifier**.

6. Preencha os valores apropriados para os campos e a categoria de itens que você deseja que esse classificador de treinamento `Name` `Description` identifique.

7. Escolha o site, a biblioteca e a URL da pasta do SharePoint Online para o site de conteúdo de dados de dados na etapa 2. Escolha `Add` .

8. Revise as configurações e escolha `Create trainable classifier` .

9. Dentro de 24 horas, o classificador de treinamento processará os dados de pesquisa e criará um modelo de previsão. O status do classificador é `In progress` enquanto ele processa os dados de pesquisa. Quando o classificador terminar de processar os dados de semente, o status muda para `Need test items` .

10. Agora você pode exibir a página de detalhes escolhendo o classificador.

    > [!div class="mx-imgBorder"]
    > ![classificador de treinamento pronto para teste](../media/classifier-trainable-ready-to-test-detail.png)

11. Coletar pelo menos 200 itens de conteúdo de teste (10.000 máx. ) para melhores resultados. Eles devem ser uma mistura de itens que são fortes positivos, negativos fortes e alguns que são um pouco menos óbvios em sua natureza. Consulte [extensões de nome de arquivo rastreado padrão](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) e tipos de arquivo analisados no SharePoint Server para os tipos de arquivo com suporte.

    > [!IMPORTANT]
    > Os itens de exemplo não devem ser criptografados e devem estar em inglês.

12. Coloque o conteúdo de teste em uma pasta do SharePoint Online dedicada a manter *somente o conteúdo de teste.* Anote o site, a biblioteca e a URL da pasta do SharePoint Online.

    > [!TIP]
    > Se você criar um novo site e uma pasta para seus dados de teste, permita que pelo menos uma hora para esse local seja indexado antes de criar o classificador de treinamento que usará esses dados de pesquisa.

13. Escolha `Add items to test` .

14. Escolha o site, a biblioteca e a URL da pasta do SharePoint Online para o site de conteúdo de teste na etapa 12. Escolha `Add` .

15. Termine o assistente escolhendo `Done` . O classificador de treinamento levará até uma hora para processar os arquivos de teste.

16. Quando o classificador de treinamento terminar de processar seus arquivos de teste, o status na página de detalhes mudará para `Ready to review` . Se você precisar aumentar o tamanho da amostra de teste, escolha e permita que o classificador de treinamento `Add items to test` processe os itens adicionais.

    > [!div class="mx-imgBorder"]
    > ![pronto para revisar a captura de tela](../media/classifier-trainable-ready-to-review-detail.png)

17. Escolha `Tested items to review` a guia para revisar itens.

18. O Microsoft 365 apresentará 30 itens por vez. Revise-os e na `We predict this item is "Relevant". Do you agree?` caixa escolha um ou ou `Yes` `No` `Not sure, skip to next item` . A precisão do modelo é atualizada automaticamente após cada 30 itens.

    > [!div class="mx-imgBorder"]
    > ![review items box](../media/classifier-trainable-review-detail.png)

19. Revise *pelo menos* 200 itens. Depois que a pontuação de precisão está estabilizada, a opção **de** publicação se tornará disponível e o status do classificador dirá `Ready to use` .

    > [!div class="mx-imgBorder"]
    > ![pontuação de precisão e pronto para publicação](../media/classifier-trainable-review-ready-to-publish.png)

20. Publique o classificador.

21. Depois de publicado, o classificador estará disponível como uma condição na rotulagem automática do [Office](apply-sensitivity-label-automatically.md)com rótulos de [sensibilidade,](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) aplicar automaticamente a política de rótulo de retenção com base em uma condição e na conformidade [de comunicação.](communication-compliance.md)
