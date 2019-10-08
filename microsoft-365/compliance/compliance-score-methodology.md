---
title: Metodologia de Pontuação de conformidade
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: O Gerenciador de conformidade da Microsoft é uma ferramenta de avaliação de riscos gratuita baseada em fluxo de trabalho no portal de confiança do serviço Microsoft. O Gerenciador de conformidade permite que você rastreie, atribua e verifique as atividades de conformidade normativa relacionadas aos serviços em nuvem da Microsoft.
ms.openlocfilehash: eb6e79d840439acec007fef54bf6cb5ca5633f1e
ms.sourcegitcommit: 15173ab87325b7d79bab683702b35d77a355cd6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/08/2019
ms.locfileid: "37417490"
---
# <a name="compliance-score-methodology-preview"></a>Metodologia de Pontuação de conformidade (prévia)

> [!NOTE]
> A Pontuação de Conformidade não expressa uma medida absoluta da conformidade organizacional em relação a qualquer padrão ou regulamentação específicos. Ela expressa até que ponto você adotou os controles que podem reduzir os riscos aos dados pessoais e à privacidade individual. Nenhum serviço pode garantir que você esteja em conformidade com um padrão ou regulamentação e a Pontuação de Conformidade não deve ser interpretada como uma garantia de forma alguma.

O painel do Gerenciador de conformidade exibe uma pontuação total de conformidade para avaliações em cada bloco de avaliação. Esta é a pontuação de conformidade geral para a avaliação e é o acúmulo de pontos recebidos para cada controle implementado e testado na avaliação. Para uma nova avaliação, a pontuação de conformidade tem um valor inicial para os controles gerenciados pela Microsoft testados por terceiros independentes. A pontuação de conformidade é calculada com base em pontuações de ação gerenciada pela Microsoft e pontuações de ação gerenciada pelo cliente. A pontuação de conformidade pode ajudar a priorizar quais avaliações e controles focalizar para melhorar a postura geral de conformidade.

Os valores de Pontuação de conformidade exibidos para o controle são aplicados *totalmente* à pontuação total de conformidade, em uma base de aprovação/falha. O controle é implementado e passa o teste de avaliação subsequente ou não. Os pontos atribuídos são adicionados à pontuação de conformidade quando o controle tem:

- **Status de implementação** igual a **implementação** **implementada** ou alternativa,
- O **resultado do teste** é **passado**.

## <a name="compliance-score"></a>Pontuação de conformidade
  
No gerente de conformidade, as pontuações da linha de base movem do nível de controle para o nível do item de ação. As pontuações se baseiam na finalidade (detecção, prevenção ou correção) e na imposição (discricionária ou obrigatória) do item de ação.

Itens de ação são mapeados para controles e quando um controle é mapeado para vários itens de ação, a soma das pontuações de item de ação é a pontuação de controle. A soma da Pontuação de controle de todos os controles em uma determinada avaliação é a pontuação de avaliação. A pontuação média de todas as avaliações em um grupo é a pontuação de conformidade desse grupo.
  
### <a name="mandatory-or-discretionary-controls"></a>Controles obrigatórios ou discricionários
  
 Os **controles obrigatórios** são ações que não podem ser ignoradas intencionalmente ou acidentalmente. Um exemplo de um controle obrigatório comum é uma política de senha gerenciada centralmente que define os requisitos de tamanho, complexidade e validade da senha. Os usuários devem cumprir esses requisitos para acessar o sistema.
  
 Os **controles discricionários** dependem dos usuários para entender a política e agir de acordo. Por exemplo, uma política que exija que os usuários bloqueiem seu computador quando deixam de ser um controle discricionário, pois ele se baseia no usuário.
  
### <a name="preventative-detective-or-corrective-controls"></a>Controles de prevenção, detecção ou correção
  
 Os **controles preventivos** são ações que impedem riscos específicos. Por exemplo, a proteção de informações em repouso usando criptografia é um controle preventivo contra ataques, violações. A separação de direitos é um controle preventivo para gerenciar o conflito de interesses e para proteger contra fraudes.
  
 Os **controles de detecção** são ações que monitoram ativamente os sistemas para identificar condições ou comportamentos irregulares que representam riscos ou que podem ser usados para detectar intrusões ou determinar se ocorreu uma violação. Auditoria de acesso do sistema e auditorias de ações administrativas privilegiadas são tipos de controles de monitoramento de detecção. Auditorias de conformidade normativa são um tipo de controle de detecção usado para encontrar problemas de processo.
  
Os **controles corretivos** são controles que tentam manter os efeitos adversos de um incidente de segurança para um mínimo, realizar ações corretivas para reduzir o efeito imediato e reverter os danos, se possível. Privacy incidente Response é um controle corretivo para limitar danos e restaurar sistemas para um estado operacional após uma violação.
  
Cada controle tem um valor atribuído no gerente de conformidade com base no risco que ele representa:

|**Tipo**|**Pontuação atribuída**|
|:-----|:-----|
| Obrigatórios preventivos | 27 |
| Discricionários preventivos | 9  |
| Detecção obrigatória | 3D |
| Detecção arbitrária | 1 |
| Obrigatório corretivo | 3D |
| Condicionalmente | 1 |
  
## <a name="action-item-workflow"></a>Fluxo de trabalho do item de ação

Este é o fluxo de trabalho básico de um item de ação típico:
  
1. O gerente de conformidade, risco, privacidade e/ou proteção de dados de uma organização atribui uma tarefa a alguém na organização para implementar um controle. Essa pessoa pode ser:

    - Um proprietário de política de negócios.
    - Um implementador de ti.
    - Outra pessoa na organização com responsabilidade de realizar a tarefa.

2. Essa pessoa realiza as tarefas necessárias para implementar o controle, carrega evidências de implementação no Gerenciador de conformidade e marca o controle vinculado ao item de ação conforme implementado. Após a conclusão dessas tarefas, elas atribuem o item de ação a um consultor para validação.

    Os avaliadores podem ser:

    - Avaliadores internos que realizam a validação de controles em uma organização.
    - Avaliadores externos que examinam, verificam e certificam a conformidade, como as organizações independentes de terceiros que auditam os serviços de nuvem da Microsoft.

3. O consultor valida o controle e examina a evidência e marca o controle como avaliado e os resultados da avaliação.

Depois que todos os controles associados a uma avaliação forem avaliados, a avaliação estará concluída.