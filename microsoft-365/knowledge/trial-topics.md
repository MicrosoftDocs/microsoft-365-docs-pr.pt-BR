---
title: Executar uma avaliação de tópicos do Microsoft Viva
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: lauris; jaeccles
ms.date: ''
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.custom: ''
search.appverid: ''
localization_priority: Normal
description: Saiba como planejar e executar um programa piloto de avaliação para Tópicos do Microsoft Viva em sua organização.
ms.openlocfilehash: 128e82e7664a76baa55d37e983319c9f344624fd
ms.sourcegitcommit: 53aebd492a4b998805c70c8e06a2cfa5d453905c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2021
ms.locfileid: "53327070"
---
# <a name="run-a-trial-of-microsoft-viva-topics"></a>Executar uma avaliação de tópicos do Microsoft Viva

Este artigo descreve como configurar e executar um programa piloto de avaliação para implantar o Viva Topics em sua organização. Este artigo também recomenda as práticas recomendadas para a avaliação.

## <a name="sign-up-for-a-trial"></a>Inscrever-se para uma avaliação

As avaliação estão disponíveis publicamente em uma das fontes a seguir. Essas avaliação oferecem 25 usuários acesso aos Tópicos do Viva por 30 dias.

- A [página do produto Tópicos do Viva](https://www.microsoft.com/microsoft-viva/topics?activetab=pivot:overviewtab)

- O [Centro de administração do Microsoft 365](https://admin.microsoft.com)
    1.  Entre no [Centro de administração do Microsoft 365](https://admin.microsoft.com).
    2.  Vá para **Serviços de Compra de**  >  **Cobrança.**
    3.  Role para baixo até a seção **Complementos**.
    4.  No tópico **Experiências,** selecione **Detalhes**.
    5.  Selecione **Obter avaliação gratuita**.
    6.  Siga as etapas restantes do assistente para confirmar a avaliação.

Você deve ser um administrador Microsoft 365 global ou administrador de cobrança para ativar uma avaliação.

> [!NOTE]
> As avaliações públicas só podem ser adicionadas uma vez para cada Microsoft 365 locatário.

### <a name="who-should-be-involved-in-a-trial"></a>Who deve estar envolvido em uma avaliação

|Função  |Atividade  |
|---------|---------|
|Microsoft 365 administrador global ou administrador de cobrança  |   Ativar a avaliação e atribuir licenças      |
|Microsoft 365 administrador global ou SharePoint administrador    |       Configurar tópicos do Viva e criar centros de tópicos  |
|Usuário comercial     |   Executar funções de consumidor do gerenciador de conhecimento, colaborador de tópicos e tópicos      |

### <a name="before-you-activate-a-trial"></a>Antes de ativar uma avaliação

O planejamento é essencial para uma avaliação eficaz dos Tópicos do Viva. O período de avaliação é limitado e deve incluir a descoberta de tópicos e explorar a qualidade, o gerenciamento e as experiências do usuário final.

#### <a name="discovery"></a>Descoberta

Há duas opções de estratégia de alto nível para a configuração da descoberta de tópicos durante uma avaliação:

- Indexe todo ou a maior parte do conteúdo SharePoint Online.
   - Locatários grandes podem levar até duas semanas para indexar totalmente. Embora os tópicos sejam gerados incrementalmente durante esse período, a indexação completa pode consumir até metade do período de avaliação.
   - Para locatários com um volume significativo de dados, essa opção pode produzir um número muito grande de tópicos, talvez dezenas de milhares.

- Identifique um subconjunto dos sites SharePoint para indexação.

A escolha dessas estratégias é um equilíbrio dos dois fatores a seguir:

- Ter dados suficientes para gerar tópicos significativos. A IA em Tópicos do Viva é ajustada para trabalhar em conjuntos de dados grandes, idealmente aqueles que têm mais de 10.000 documentos.
- Não gerar tantos tópicos durante o período de avaliação que avalia-los durante o período de tempo disponível é avassalador.

Para a maioria das organizações, a segunda estratégia produz o melhor resultado.

> [!NOTE]
> Devido ao número de documentos exigidos pela AI, recomendamos que você execute as avaliação do Viva Topics em um locatário de produção. Não há impacto no desempenho do locatário durante esse período. Somente usuários com uma licença de avaliação podem acessar as experiências de usuário do Viva Topics.

#### <a name="roles"></a>Funções

Durante a avaliação, há três funções que devem estar ativas, descritas na tabela a seguir.

|Função  |Atividade  |
|---------|---------|
|Gerente de conhecimento     |   Controlar os estágios de ciclo de vida dos tópicos; confirmar e remover tópicos; atuar como um gerente de comunidade para colaboradores de tópicos      |
|Colaborador de tópicos    |      Especialistas em assuntos de conteúdo, que podem:<br> Revisar tópicos para avaliar a qualidade do conteúdo definido pela IA<br>Cura tópicos descobertos com conteúdo adicional<br>Criar tópicos adicionais que não foram descobertos pela AI   |
|Consumidor de tópicos    |     Consumir tópicos por meio de destaques de página e pesquisa<br>Fornecer comentários sobre o valor dos tópicos apresentados    |

#### <a name="expected-topics"></a>Tópicos esperados

Pode ser útil documentar os tópicos que você espera que sejam gerados pela IA, mesmo que isso se basee apenas em suposições. Essa tarefa é concluída com mais facilidade quando você indexa um subconjunto definido de seus sites SharePoint para os quais as SMEs podem ser facilmente identificadas.

Ter uma lista documentada ajudará você a:

- Revise a lista de tópicos gerados por AI, que podem ser maiores do que você espera.
- Conheça os tópicos que você pode precisar criar manualmente ou que são prioridades para a cura.

Sempre haverá uma necessidade de uma mistura de tópicos definidos por AI e criados por humanos em uma implantação bem-sucedida ou avaliação de Tópicos do Viva.

## <a name="activate-a-trial"></a>Ativar uma avaliação

Ao iniciar uma avaliação, você precisa:

- Atribua licenças aos usuários relevantes.
- Execute [a instalação adicional](set-up-topic-experiences.md) de Tópicos do Viva.

Quando a avaliação é ativada, o processo de descoberta de tópicos começa.

## <a name="during-a-trial"></a>Durante uma avaliação

O período de avaliação deve ser usado para avaliar os seguintes componentes de Tópicos do Viva:

- Os tópicos sugeridos pela AI e o conteúdo do tópico
- As experiências do usuário final, cartões de tópicos de surfacing em páginas SharePoint modernas e em Pesquisa da Microsoft

Considere estes fatores:

- Para que os Tópicos do Viva entreguem o valor máximo, o conteúdo em tópicos precisa ser uma combinação de conteúdo definido por AI e conteúdo com cura humana.
- Todas as experiências do usuário são "recortadas de permissão" (incluindo a exibição do gerente de conhecimento na página **Gerenciar tópicos).** Os usuários verão apenas um tópico se eles têm permissões para exibir alguns dos recursos usados para gerar o tópico. Isso significa que diferentes usuários podem ver conteúdo diferente na mesma página de tópico.
- Os usuários podem ver vários tópicos com o mesmo nome na página **Gerenciar** tópicos. Esses tópicos não são necessariamente duplicados, mas podem ser devido a um único termo usado em vários contextos nos dados, como um nome de código de projeto que é usado por dois projetos distintos.

## <a name="after-a-trial"></a>Após uma avaliação

Com base no resultado da avaliação, você pode decidir se deve prosseguir com o uso de produção de Tópicos do Viva.

### <a name="proceed-to-production-use"></a>Prossiga para o uso de produção

Para garantir a continuidade do serviço, você deve comprar o número necessário de licenças e atribuir essas licenças aos usuários. Os usuários de avaliação que não têm uma licença completa no final do período de avaliação não poderão acessar as experiências do Viva Topics.

### <a name="dont-proceed-to-production-use"></a>Não prossiga para uso de produção

Se você não comprar licenças após a avaliação:

- A descoberta de tópicos será parada.
- Os usuários não verão mais destaques de tópicos ou cartões.
- O centro de tópicos não será excluído, mas os tópicos sugeridos e gerenciar experiências de tópicos não estarão disponíveis.
- Todos os tópicos definidos pela AI serão perdidos.
- Os tópicos que foram editados por um colaborador de tópicos permanecerão na biblioteca de páginas do centro de tópicos. Somente o conteúdo fornecido manualmente permanecerá nessas páginas, não qualquer conteúdo sugerido por AI.

## <a name="see-also"></a>Confira também

[Começar a impulsionar a adoção de tópicos do Microsoft Viva](topics-adoption-getstarted.md)

