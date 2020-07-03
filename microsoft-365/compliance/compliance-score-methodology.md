---
title: Cálculo da Pontuação de conformidade da Microsoft (visualização)
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
description: Entenda como a pontuação de conformidade da Microsoft calcula uma pontuação personalizada com base nas ações tomadas para lidar com riscos e aprimorar a postura de conformidade.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 69b631dc355ff497d0f6042e0cce6aff3d70e557
ms.sourcegitcommit: 51a9f34796535309b8ca8b52da92da0a3621327b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2020
ms.locfileid: "45024671"
---
# <a name="compliance-score-preview-calculation"></a>Cálculo da Pontuação de conformidade (visualização)

> [!IMPORTANT]
> As recomendações da Pontuação de conformidade e do Gerente de conformidade não devem ser interpretadas como garantia de conformidade. Você pode avaliar e validar a eficácia dos controles de clientes por seu ambiente normativo. Esses serviços estão atualmente em versão prévia e sujeitos aos termos e condições nos [termos dos serviços online](https://go.microsoft.com/fwlink/?linkid=2108910). Confira também [orientações de licenciamento da Microsoft 365 para segurança e conformidade](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).

## <a name="how-compliance-score-works"></a>Como a pontuação de conformidade funciona

O painel de Pontuação de conformidade exibe uma pontuação que mede seu progresso ao concluir ações de aperfeiçoamento nos controles. Cada ação tem um impacto diferente na sua pontuação, dependendo dos possíveis riscos envolvidos. Sua pontuação pode ajudar a priorizar a ação a ser focalizada para melhorar a postura geral de conformidade.

Os valores de Pontuação de conformidade exibidos para o controle são aplicados *em sua totalidade* à sua pontuação total em uma base de aprovação/falha. O controle é implementado e passa o teste de avaliação subsequente ou não. 

Os pontos são adicionados à sua pontuação de conformidade quando o controle tem:

- **Status de implementação** igual a **implementação** **implementada** ou alternativa, e
- O **resultado do teste** é **passado**.

Uma pontuação de controle é a soma dos pontos obtidos por meio de ações aprimoradas. A soma de suas pontuações de controle é a pontuação de avaliação. **A soma de suas pontuações de avaliação é a pontuação de conformidade geral.**

## <a name="initial-score-based-on-microsoft-365-data-protection-baseline"></a>Pontuação inicial com base na linha de base de proteção de dados da Microsoft 365
  
A pontuação de conformidade fornece uma pontuação inicial com base na linha de base de proteção de dados da Microsoft 365. Essa linha de base é um conjunto de controles que inclui normas e padrões fundamentais para proteção de dados e governança de dados gerais. Essa linha de base desenha elementos primariamente da NIST CSF (National Institute of Standards and Technology cybersecurity Framework) e ISO (International Organization for Standardization), bem como do FedRAMP (programa de gerenciamento de riscos e autorização federal) e RGPD (regulamentação geral de proteção de dados da União Europeia).

A avaliação da linha de base de proteção de dados (fornecida por padrão para todas as organizações) é usada para calcular sua pontuação inicial antes de configurar qualquer outra avaliação. Na sua primeira visita, a pontuação de conformidade já está coletando sinais de suas soluções 365 da Microsoft. Você verá rapidamente como sua organização está realizando em relação aos principais padrões e regulamentos de proteção de dados e veja as ações sugeridas de melhoria a serem tomadas.

Como cada organização tem necessidades específicas, a pontuação de conformidade depende de você configurar e gerenciar suas próprias avaliações para ajudar a minimizar e reduzir o risco da maneira mais abrangente possível.

## <a name="how-compliance-score-continuously-assesses-controls"></a>Como a pontuação de conformidade avalia os controles continuamente

A pontuação de conformidade verifica automaticamente o ambiente Microsoft 365 e detecta as configurações do sistema, atualizando continuamente e automaticamente o status do controle técnico. A pontuação segura é o mecanismo de base que realiza o monitoramento.

Seu status de controle é atualizado no painel de Pontuação de conformidade a cada 24 horas. Depois de seguir uma recomendação para implementar um controle, você verá o status do controle atualizado no dia seguinte.

Por exemplo, se você ativar a MFA (autenticação multifator) no portal do Azure AD, a pontuação de conformidade detectará a configuração e refletirá isso nos detalhes da solução de acesso de controle. Por outro lado, se você não tiver ativado o MFA, os sinalizadores de Pontuação de conformidade que são uma ação recomendada para você realizar.

Durante a visualização pública, a avaliação contínua está disponível para uma parte dos controles, mas não todos.

#### <a name="learn-more"></a>Saiba mais
[Leia sobre a pontuação segura e como ela funciona](../security/mtp/microsoft-secure-score-new.md).
  
## <a name="action-types-and-points"></a>Pontos e tipos de ação

A pontuação de conformidade controla dois tipos de ações: ações gerenciadas e ações que a Microsoft gerencia. Ambos os tipos de ações têm pontos que contam com relação à sua pontuação geral quando concluídas:

1. **Seus pontos** contribuem para sua pontuação de conformidade com base em controles gerenciados pela sua organização.
2. Os **pontos gerenciados da Microsoft** contribuem para sua pontuação de conformidade com base em ações gerenciadas pela Microsoft como um provedor de serviços de nuvem.

As ações são atribuídas a um valor de pontuação com base no fato de serem obrigatórias ou discricionárias, e se são preventivas, de detecção ou corretivas.

### <a name="mandatory-and-discretionary-actions"></a>Ações obrigatórias e discricionárias

 - As **ações obrigatórias** não podem ser ignoradas intencionalmente ou acidentalmente. Um exemplo é uma política de senha gerenciada centralmente que define os requisitos de tamanho, complexidade e validade da senha. Os usuários devem seguir estes requisitos para acessar o sistema.
  
 - **Ações discricionárias** dependem de usuários para entender a política e agir de acordo. Por exemplo, uma política que exige que os usuários bloqueiem o computador quando deixam de ser uma ação arbitrária, pois ele se baseia no usuário.
  
### <a name="preventative-detective-and-corrective-actions"></a>Ações preventivas, de detecção e corretivas
  
 - **Ações preventivas** tratam de riscos específicos. Por exemplo, a proteção de informações em repouso usando a criptografia é uma ação preventiva contra ataques e violações. A separação de tarefas é uma ação preventiva para gerenciar o conflito de interesse e proteção contra fraudes.
  
 - **Ações de detecção** monitoram ativamente os sistemas para identificar condições ou comportamentos irregulares que representam riscos ou que podem ser usados para detectar invasões ou violações. Os exemplos incluem auditoria de acesso do sistema e ações administrativas privilegiadas. Auditorias de conformidade normativa são um tipo de ação de detecção usada para encontrar problemas de processo.
  
- As **ações corretivas** tentam manter os efeitos adversos de um incidente de segurança para um mínimo, realizar ações corretivas para reduzir o efeito imediato e reverter os danos, se possível. Privacy incidente Response é uma ação corretiva para limitar danos e restaurar sistemas para um estado operacional após uma violação.
  
Cada ação tem um valor atribuído na pontuação de conformidade com base no risco que representa:

|**Tipo**|**Pontuação atribuída**|
|:-----|:-----|
| Obrigatórios preventivos | 27 |
| Discricionários preventivos | 9  |
| Detecção obrigatória | 3  |
| Detecção arbitrária | 1  |
| Obrigatório corretivo | 3  |
| Condicionalmente | 1  |
  
![Valores de pontos de controles de Pontuação de conformidade](../media/compliance-score-controls-scoring.png "Valores de pontos de controles de Pontuação de conformidade")