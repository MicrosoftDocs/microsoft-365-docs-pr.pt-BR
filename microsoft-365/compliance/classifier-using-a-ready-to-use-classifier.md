---
title: Usando um classificador interno (visualização)
f1.keywords:
- NOCSH
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
description: A Microsoft 365 vem com uma série de classificadores internos que você pode usar para identificar e rotular o conteúdo em sua organização. Este tópico mostra como se preparar para usar esses classificadores.
ms.openlocfilehash: 2bd36ac42278cfe7b015d03caf2d9e1958908f8f
ms.sourcegitcommit: 13f28aa762e467bab8ab1e95e1917b3ac28931da
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/08/2020
ms.locfileid: "43193499"
---
# <a name="using-a-built-in-classifier-preview"></a>Usando um classificador interno (visualização)

A Microsoft treinou e testou cinco classificadores usando conjuntos de dados de amostra muito grandes, que podem ajudar a identificar determinadas categorias de conteúdo. Confira introdução [aos classificadores estagiários (visualização)](classifier-getting-started-with.md). Esses classificadores aparecem no `Ready to use` grupo por padrão.

A Microsoft 365 vem com cinco classificadores internos recomendados:

> [!CAUTION]
> Estamos preterindo o classificador interno de **idioma ofensivo** , pois ele está produzindo um grande número de falsos positivos. Não usá-lo e, se estiver usando, você deverá mover seus processos de negócios para fora dele. Recomendamos o uso de classificadores internos **contra ameaças**, **profanação**e **assédio** .

- **Currículos**: detecta itens que são contas de texto das qualificações pessoais, educacionais, profissionais, experiência de trabalho e outras informações de identificação pessoal de um candidato.
- **Código-fonte**: detecta itens que contêm um conjunto de instruções e instruções escritas nos 25 idiomas principais de programação de computador usados no github.

|nome do idioma|||||
|---------|---------|---------|---------|---------|
|Código|C        |Unidade #       |C++     |Clojure  |
|CoffeeScript|CSS     |Ir       |Haskell |HTML     |
|Java     |JavaScript|Lua      |MATLAB   |Objective-C|
|Perl     |PHP      |Python   |R        |Ruby     |
|Scale    |Shell    |Swift    |Tex      |Script vim|

- **Assédio**: detecta uma categoria específica de itens de texto de linguagem ofensiva relacionadas à conduta ofensiva direcionada uma ou várias pessoas com base nas seguintes características: raça, étnica, Religion, origem nacional, sexo, orientação sexual, idade, deficiência.
- **Profanação**: detecta uma categoria específica de itens de texto de idioma ofensivo que contêm expressões que constrangim a maioria das pessoas.
- **Ameaça**: detecta uma categoria específica de itens de texto de linguagem ofensiva relacionadas a ameaças para confirmar a violência ou danos físicos ou danos a uma pessoa ou a uma propriedade,

> [!NOTE]
> Antes de usar classificadores internos em seu fluxo de trabalho de classificação e rotulação, você deve testá-lo em uma amostra do conteúdo da sua organização que você sente que se sinta à categoria para verificar se suas previsões de classificação atendem às suas expectativas.

> [!IMPORTANT]
> Observe que a linguagem ofensiva, assédio, profanação e classificadores de ameaças só funcionam com o texto pesquisável não é completo nem completo. Além disso, os padrões culturais e de idioma mudam continuamente e, em claro, a Microsoft reserva-se o direito de atualizar esses classificadores em seu critério. Embora os classificadores possam ajudar sua organização a monitorar ofensivas e outros idiomas usados, os classificadores não resolvem as conseqüências de tal linguagem e não se destinam a fornecer o único meio de monitoramento ou resposta ao uso dessa linguagem. Sua organização, e não a Microsoft ou suas subsidiárias, permanece responsável por todas as decisões relacionadas ao monitoramento, imposição, bloqueio, remoção e retenção de qualquer conteúdo identificado por um classificador treinado.

## <a name="how-to-prepare-for-and-use-a-built-in-classifier"></a>Como preparar e usar um classificador interno

1. Coletar itens de conteúdo de teste descartáveis que você sente que pertencem à categoria do classificador interno (correspondências positivas) e aqueles que não devem ser incluídos (correspondências negativas) na categoria que você está testando.

> [!IMPORTANT]
> Os itens de exemplo não devem ser criptografados e devem estar em inglês.

2. Criar uma pasta dedicada do SharePoint Online; Aguarde pelo menos uma hora para a pasta a ser adicionada ao índice de pesquisa. Anote a URL da pasta.

3. Entre no centro de conformidade da Microsoft 365 com administrador de conformidade ou acesso à função de administrador de segurança e abra a guia de**políticas**  > **de gerenciamento de registros** > do **centro de conformidade da Microsoft 365**(visualização).

4. Escolha `Auto-apply a label`.

5. Escolha `Choose a label to auto-apply`.

6. Escolha `Create new labels` e crie um rótulo para uso apenas com este teste. Ao fazer isso, deixe `Retention` definido como desativado. Você não deseja ativar nenhuma retenção ou outras ações. Nesse caso, você usará o rótulo de retenção simplesmente como um rótulo de texto, sem impor qualquer ação. Por exemplo, você pode criar um rótulo de retenção chamado "teste de classificador SourceCode" sem ações e, em seguida, aplicar automaticamente esse rótulo de retenção ao conteúdo que tenha classificador de código-fonte como uma condição. Para saber mais sobre a criação de rótulos de retenção, confira [visão geral dos rótulos de retenção](labels.md).
  
7. Escolha `Auto-apply a label` e, `Choose a label to auto-apply`em seguida. Para saber mais sobre como usar a condição com base em aplicar automaticamente um rótulo, confira [aplicar automaticamente a política de rótulo de retenção com base em uma condição](labels.md#applying-a-retention-label-automatically-based-on-conditions).

8. Escolha seu rótulo de teste na lista e escolha `Next`.

9. Escolha `Apply label to content that matches a trainable classifier`.

![selecionar classificador como uma condição](../media/classifier-pre-trained-apply-label-match-trainable-classifier.png).

10. Escolha seu classificador na lista, neste caso`Source Code`

11. Nomeie a política, por exemplo, "teste de classificador interno de código-fonte".

12. Escolha `Let me choose specific locations`.

13. Desative todos os locais `SharePoint sites` , exceto `Choose sites`e escolha.

14. Insira a URL do site na etapa 2.

15. Finalize o assistente e escolha`Auto-apply`

16. Coloque os itens de teste na pasta dedicada do SharePoint Online.

17. Permite que uma hora para o rótulo seja aplicada.

18. Verifique as propriedades dos documentos do rótulo para ver se o classificador incluiu e excluiu o conteúdo de teste conforme o esperado.

19. Revise os itens que foram rotulados.

20. Exclua o conteúdo e a política de rótulo se você tiver feito o teste.

Confira também:

- [Introdução aos classificadores de treinamento (visualização)](classifier-getting-started-with.md)
- [Visão geral de rótulos de retenção](labels.md)
- [Aplicar automaticamente a política de rótulo de retenção com base em uma condição](labels.md#applying-a-retention-label-automatically-based-on-conditions)
