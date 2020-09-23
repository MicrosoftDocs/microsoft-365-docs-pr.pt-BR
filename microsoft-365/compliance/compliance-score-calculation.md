---
title: Cálculo da Pontuação de conformidade
f1.keywords:
- NOCSH
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
description: Entenda como o Microsoft Compliance Manager calcula uma pontuação personalizada com base nas ações tomadas para lidar com riscos e aprimorar a postura de conformidade.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9fd71b4953dc40a3c1e7601f42f595488fcef98b
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48204263"
---
# <a name="compliance-score-calculation"></a>Cálculo da Pontuação de conformidade

> [!IMPORTANT]
> As recomendações do Gerenciador de conformidade não devem ser interpretadas como garantia de conformidade. Você pode avaliar e validar a eficácia dos controles de clientes por seu ambiente normativo. Esses serviços estão sujeitos aos termos e condições nos [termos dos serviços online](https://go.microsoft.com/fwlink/?linkid=2108910). Confira também [orientações de licenciamento da Microsoft 365 para segurança e conformidade](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).

## <a name="how-to-read-your-compliance-score"></a>Como ler a pontuação de conformidade

O painel do Gerenciador de conformidade exibe sua pontuação geral de conformidade. Esta Pontuação mede seu progresso ao concluir as ações de melhoria recomendadas nos controles. Sua pontuação pode ajudá-lo a entender a postura de conformidade atual. Também pode ajudá-lo a priorizar ações com base em seu potencial para reduzir o risco.

Um valor de pontuação é atribuído em três níveis:

1. **Pontuação de ação de melhoria**: cada ação tem um impacto diferente na sua pontuação, dependendo do risco potencial envolvido

2. **Pontuação de controle**: Esta pontuação é a soma dos pontos obtidos por meio da conclusão de ações de aperfeiçoamento no controle. Essa soma é aplicada integralmente à sua pontuação de conformidade geral quando o controle atende a ambas as condições a seguir:
    - **Status de implementação** igual a **implementação** **implementada** ou alternativa, e
    - O **resultado do teste** é **passado**.

3. **Pontuação de avaliação**: essa pontuação é a soma de suas pontuações de controle. É calculado usando pontuações de ação. Cada ação da Microsoft e cada ação de melhorias gerenciadas pela sua organização são contadas uma vez, independentemente da frequência de referência em um controle.

A pontuação de conformidade geral é calculada usando pontuações de ação, em que cada ação da Microsoft é contada uma vez, cada ação técnica que você gerencia é contada uma vez, e cada ação não-técnica gerenciada é contada uma vez por grupo. Essa lógica foi projetada para fornecer as estatísticas mais precisas de como as ações são implementadas e testadas em sua organização. Você pode notar que isso pode fazer com que sua pontuação de conformidade geral difira da média de suas pontuações de avaliação. Leia mais sobre [como as ações são pontuadas](#action-types-and-points).

## <a name="initial-score-based-on-microsoft-365-data-protection-baseline"></a>Pontuação inicial com base na linha de base de proteção de dados da Microsoft 365
  
O Gerenciador de conformidade fornece uma pontuação inicial com base na linha de base de proteção de dados da Microsoft 365. Essa linha de base é um conjunto de controles que inclui normas e padrões fundamentais para proteção de dados e governança de dados gerais. Essa linha de base desenha elementos primariamente da NIST CSF (National Institute of Standards and Technology cybersecurity Framework) e ISO (International Organization for Standardization), bem como do FedRAMP (programa de gerenciamento de riscos e autorização federal) e RGPD (regulamentação geral de proteção de dados da União Europeia).

Sua pontuação inicial é calculada de acordo com a avaliação da linha de base da proteção de dados padrão fornecida para todas as organizações. Na sua primeira visita, o gerente de conformidade já está coletando sinais de suas soluções 365 da Microsoft. Você verá rapidamente como sua organização está realizando em relação aos principais padrões e regulamentos de proteção de dados e veja as ações sugeridas de melhoria a serem tomadas.

Como cada organização tem necessidades específicas, o Gerenciador de conformidade depende de você configurar e gerenciar avaliações para ajudar a minimizar e reduzir o risco da forma mais abrangente possível.

## <a name="how-compliance-manager-continuously-assesses-controls"></a>Como o gerente de conformidade avalia os controles continuamente

O Gerenciador de conformidade verifica automaticamente o ambiente Microsoft 365 e detecta as configurações do sistema, atualizando continuamente e automaticamente o status da ação técnica. A pontuação segura da Microsoft é o mecanismo subjacente que realiza o monitoramento.

O status da ação é atualizado no painel a cada 24 horas. Depois de seguir uma recomendação para implementar um controle, você verá normalmente o status do controle atualizado no dia seguinte.

Por exemplo, se você ativar a MFA (autenticação multifator) no portal do Azure AD, o Gerenciador de conformidade detectará a configuração e a refletirá nos detalhes da solução de acesso de controle. Por outro lado, se você não tiver ativado a MFA, o Gerenciador de conformidade sinalizará como uma ação recomendada para você realizar.

Saiba mais sobre [a pontuação segura e como ela funciona](../security/mtp/microsoft-secure-score-new.md).
  
## <a name="action-types-and-points"></a>Pontos e tipos de ação

O Gerenciador de conformidade rastreia dois tipos de ações:

1. **Suas ações de melhoria**: ações que sua organização gerencia.
2. **Ações da Microsoft**: ações que a Microsoft gerencia.

Ambos os tipos de ações têm pontos que contam com relação à sua pontuação geral quando concluída.

### <a name="technical-and-non-technical-actions"></a>Ações técnicas e não técnicas

As ações são agrupadas de acordo com a natureza técnica ou não técnica. O impacto de Pontuação de cada ação difere por tipo.

- As **ações técnicas** são implementadas por meio da interação com a tecnologia de uma solução (por exemplo, alterar uma configuração). Os pontos de ações técnicas são concedidos uma vez por ação, independentemente de quantos grupos pertence.

- **Ações não técnicas** são gerenciadas pela sua organização e implementadas de maneiras diferentes de trabalhar com a tecnologia de uma solução. Há dois tipos de ações não técnicas: **documentação** e **operacional**. Os pontos dessas ações são aplicados à sua pontuação de conformidade em um nível de grupo. Isso significa que, se houver uma ação em vários grupos, você receberá o valor do ponto da ação sempre que implementá-lo dentro de um grupo.

**Exemplo de como as ações técnicas e não técnicas são classificadas:**

Digamos que você tenha uma ação técnica vale 3 pontos que existam em 5 grupos e que você tem uma ação não técnica vale 3 pontos que existem nos mesmos cinco grupos.

Se você implementar a ação técnica com êxito, o número total de pontos que você receberá é 3. Isso ocorre porque você só precisa implementar a ação uma vez para o seu locatário. A implementação e o status do teste para a ação técnica mostrarão o mesmo em todas as instâncias dessa ação, em todos os grupos aos quais ele pertence.

Se você implementar com êxito a ação não técnica em cada um dos cinco grupos, o número total de pontos recebidos será 15. Isso ocorre porque você precisa implementar a ação em cada grupo. A implementação e o status do teste para a ação não técnica serão diferentes nos grupos, pois a ação é implementada separadamente em cada um de seus grupos.

Essa lógica de pontuação foi projetada para fornecer as estatísticas mais precisas de como as ações são implementadas e testadas em sua organização.

### <a name="how-score-values-are-determined"></a>Como os valores de pontuação são determinados
 
As ações são atribuídas a um valor de pontuação com base no fato de serem obrigatórias ou discricionárias, e se são preventivas, de detecção ou corretivas.

### <a name="mandatory-and-discretionary-actions"></a>Ações obrigatórias e discricionárias

 - As **ações obrigatórias** não podem ser ignoradas intencionalmente ou acidentalmente. Um exemplo de uma ação obrigatória é uma política de senha gerenciada centralmente que define os requisitos de tamanho, complexidade e validade da senha. Os usuários devem seguir estes requisitos para acessar o sistema.
  
 - **Ações discricionárias** dependem de usuários para entender e aderir a uma política. Por exemplo, uma política que exige que os usuários bloqueiem o computador quando deixam de ser uma ação arbitrária, pois ele se baseia no usuário.
  
### <a name="preventative-detective-and-corrective-actions"></a>Ações preventivas, de detecção e corretivas
  
 - **Ações preventivas** tratam de riscos específicos. Por exemplo, a proteção de informações em repouso usando a criptografia é uma ação preventiva contra ataques e violações. A separação de tarefas é uma ação preventiva para gerenciar o conflito de interesse e proteção contra fraudes.
  
 - **Ações de detecção** monitoram ativamente os sistemas para identificar condições ou comportamentos irregulares que representam riscos ou que podem ser usados para detectar invasões ou violações. Os exemplos incluem auditoria de acesso do sistema e ações administrativas privilegiadas. Auditorias de conformidade normativa são um tipo de ação de detecção usada para encontrar problemas de processo.
  
- As **ações corretivas** tentam manter os efeitos adversos de um incidente de segurança para um mínimo, realizar ações corretivas para reduzir o efeito imediato e reverter os danos, se possível. Privacy incidente Response é uma ação corretiva para limitar danos e restaurar sistemas para um estado operacional após uma violação.
  
Cada ação tem um valor atribuído no gerente de conformidade com base no risco que representa:

|**Tipo**|**Pontuação atribuída**|
|:-----|:-----|
| Obrigatórios preventivos | 27 |
| Discricionários preventivos | 9  |
| Detecção obrigatória | 3D |
| Detecção arbitrária | 1 |
| Obrigatório corretivo | 3D |
| Condicionalmente | 1 |
  
![Valores de ponto de ação do gerente de conformidade](../media/compliance-score-action-scoring.png "Valores de ponto de ação do gerente de conformidade")