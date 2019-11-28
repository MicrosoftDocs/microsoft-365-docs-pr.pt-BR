---
title: Criar um classificador treinado (visualização)
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Use classificadores treinados quando um dos classificadores de caixa pronto para usar não atender às suas necessidades. Um classificador da Microsoft 365 é uma ferramenta que você pode treinar para reconhecer vários tipos de conteúdo fornecendo amostras de ti para ver. Este tópico mostra como criar um classificador personalizado.
ms.openlocfilehash: 2b1955a2079a26792e973eec1848fcdac8c58218
ms.sourcegitcommit: e386037c9cc335c86896dc153344850735afbccd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/27/2019
ms.locfileid: "39633978"
---
# <a name="creating-a-trainable-classifier-preview"></a>Criar um classificador treinado (visualização)

Use classificadores treinados quando um dos classificadores prontos para uso não atender às suas necessidades. Um classificador da Microsoft 365 é uma ferramenta que você pode treinar para reconhecer vários tipos de conteúdo fornecendo amostras de ti para ver. O treinamento do classificador envolve primeiro a atribuição de exemplos de ti que são separados e positivamente correspondem à categoria. Depois de ter processado esses, você testará as previsões dando uma mistura de amostras positivas e negativas.

Para saber mais sobre os diferentes tipos de classificadores, confira [introdução aos classificadores ferroviárias (visualização)](classifier-getting-started-with.md)

Esta linha do tempo reflete uma implantação de amostra.

![Estagiário-classificador-linha do tempo](media/trainable-classifier-deployment-timeline_border.png)

## <a name="seed-content"></a>Conteúdo semente

Quando você quiser um classificador treinado para identificar de forma independente e precisa um item como estando em uma categoria específica de conteúdo, primeiro é preciso apresentá-lo com vários exemplos do tipo de conteúdo que está na categoria. Esta alimentação de amostras para o classificador treinado é conhecida como *propagação*. O conteúdo semente é selecionado por uma pessoa e é julgada para representar a categoria do conteúdo.

> [!TIP]
> Você precisa ter pelo menos 50 amostras positivas e até 500. O classificador treinado será processado até os 500 exemplos criados mais recentes (por data de criação do arquivo/carimbo de hora). Quanto mais amostras você fornecer, mais precisará das previsões que o classificador fará.

## <a name="testing-content"></a>Testando conteúdo

Depois que o classificador treinado tiver processado exemplos positivos suficientes para criar um modelo de previsão, você precisará testar as previsões feitas para ver se o classificador pode distinguir corretamente os itens que correspondem à categoria e aos itens que não estão. Você faz isso alimentando o outro, espero maior, um conjunto de conteúdo separado para o homem que consiste em exemplos que devem se enquadrar na categoria e exemplos que não. Depois de processá-los, você passará manualmente pelos resultados e verificará se cada previsão está correta, incorreta ou se não tem certeza. O classificador treinado usa esse feedback para melhorar seu modelo de previsão.

> [!TIP]
> Para obter melhores resultados, tenha 10.000 itens em seu conjunto de amostra de teste com uma distribuição uniforme de correspondências positivas e negativas.

> [!TIP]
> O consentimento é obrigatório pela primeira vez para os classificadores treináveis. O Microsoft 365 leva 12 dias para concluir a avaliação da linha de base do conteúdo da sua organização.

## <a name="how-to-create-a-trainable-classifier"></a>Como criar um classificador treinado

1. Coleta entre 50-500 itens de conteúdo semente. Eles devem ser apenas exemplos que representam fortemente o tipo de conteúdo que você deseja que o classificador treinado identifique positivamente como estando na categoria de classificação. Consulte, [extensões de nome de arquivo rastreado padrão e tipos de arquivo analisados no SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) para os tipos de arquivo com suporte.

> [!IMPORTANT]
> Os itens de amostra de propagação e teste não devem ser criptografados e devem estar em inglês.

> [!IMPORTANT]
> Certifique-se de que os itens em seu conjunto de propagação são exemplos **fortes** da categoria. O classificador treinado inicialmente cria seu modelo com base no que você propaga com ele. O classificador supõe que todos os exemplos de propagação são positivos fortes e não têm como saber se uma amostra é uma correspondência fraca ou negativa à categoria.

2. Coloque o conteúdo semente em uma pasta do SharePoint Online que seja dedicada a manter *somente o conteúdo semente*. Anote o site, a biblioteca e a URL da pasta.

> [!TIP]
> Se você criar um novo site e pasta para seus dados semente, permita que pelo menos uma hora para esse local seja indexado antes de criar o classificador treinado que usará esses dados de propagação.

3. Entre no centro de conformidade da Microsoft 365 com administrador de conformidade ou acesso à função de administrador de segurança e abra **o centro de conformidade** da Microsoft 365 ou a**classificação de dados** **do centro** > de segurança da Microsoft 365

4. Escolha a guia **classificadores estagiários** .

5. Escolha **criar classificador treinado**.

6. Preencha os valores apropriados para o `Name`e `Description` os campos da categoria de itens que você deseja que esse classificador seja identificado.

7. Insira o site, a biblioteca e a URL exata do SharePoint Online para o site de conteúdo semente da etapa 2. Escolha `Add`.

8. Revise as configurações e `Create trainable classifier`escolha.

9. Dentro de 24 horas, o classificador treinado processará os dados semente e criará um modelo de previsão. O status do classificador é `In progress` enquanto processa os dados semente. Quando o classificador terminar o processamento dos dados semente, o status mudará para `Need test items`.

10. Agora você pode exibir a página de detalhes escolhendo o classificador.


![classificador de estagiário pronto para teste](media/classifier-trainable-ready-to-test-detail.png)

11. Colete pelo menos 200 itens de conteúdo de teste. A Microsoft recomenda 10.000 para obter os melhores resultados. Eles devem ser uma mistura de itens que são positivos fortes, negativos fortes e outros que são um pouco menos óbvios em sua natureza. Consulte, [extensões de nome de arquivo rastreado padrão e tipos de arquivo analisados no SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) para os tipos de arquivo com suporte.

> [!IMPORTANT]
> Os itens de exemplo não devem ser criptografados e devem estar em inglês.

12. Coloque o conteúdo de teste em uma pasta do SharePoint Online que seja dedicada a conter *somente o conteúdo de teste*. Anote o site, a biblioteca e a URL da pasta do SharePoint Online.

> [!TIP]
> Se você criar um novo site e uma pasta para seus dados de teste, permita que pelo menos uma hora para esse local seja indexado antes de criar o classificador treinado que usará esses dados semente.

13. Escolha `Add items to test`.

14. Insira o site, a biblioteca e a URL exata do SharePoint Online para o site de conteúdo de teste da etapa 12. Escolha `Add`.

15. Finalize o assistente escolhendo `Done`. Seu classificador treinado levará até uma hora para processar os arquivos de teste.

16. Quando o classificador treinado termina de processar seus arquivos de teste, o status da página de detalhes será alterado `Ready to review`para. Se você precisar aumentar o tamanho da amostra de teste, `Add items to test` escolha e permitir que o classificador treinado processe os itens adicionais.

![Pronto para revisar captura de tela](media/classifier-trainable-ready-to-review-detail.png)

17. Escolha `Tested items to review` Tab para revisar itens.

18. A Microsoft 365 apresentará 30 itens por vez. Examine-os e, `We predict this item is "Relevant". Do you agree?` na caixa, `Yes` escolha `No` ou `Not sure, skip to next item`ou. A precisão do modelo é atualizada automaticamente após cada 30 itens.

![caixa examinar itens](media/classifier-trainable-review-detail.png)

19. Revise *pelo menos* 200 itens.

20. Continue a revisar até que a precisão alcance pelo menos 70 `Publish the classifier` % e `Ready to use`o status é.

![precisão e pronto para publicar](media/classifier-trainable-review-ready-to-publish.png)

21. Publicar o classificador.

22. Depois de publicado, seu classificador estará disponível como uma condição na [política de rótulo de retenção de aplicação automática com base em uma condição](labels.md#applying-a-retention-label-automatically-based-on-conditions) e em conformidade de [comunicação](communication-compliance.md).

> [!CAUTION]
> Após a publicação de um classificador, ele não poderá passar por nenhum treinamento adicional, portanto, certifique-se de que você testou e analisou o máximo de itens possível para garantir que a precisão seja a mais alta possível.

## <a name="see-also"></a>Confira também

- [Introdução aos classificadores de treinamento (visualização)](classifier-getting-started-with.md)
- [Extensões de nome de arquivo rastreado padrão e tipos de arquivos analisados no SharePoint Server Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)
