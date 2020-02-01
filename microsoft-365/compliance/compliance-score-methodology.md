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
description: Entenda como a pontuação de conformidade da Microsoft calcula uma pontuação personalizada com base nas ações tomadas para lidar com riscos e aprimorar a postura de conformidade.
ms.openlocfilehash: 1ee9410e3b40a8180d768945a643d3e52c29046b
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41596238"
---
# <a name="microsoft-compliance-score-preview-calculation"></a>Cálculo da Pontuação de conformidade da Microsoft (visualização)

> [!IMPORTANT]
> A pontuação de conformidade não expressa uma medida absoluta da conformidade organizacional com qualquer padrão ou regulamentação específico. Ele expressa a extensão para a qual você adotou controles que podem reduzir os riscos para dados pessoais e privacidade individual. As recomendações de Pontuação de conformidade e gerente de conformidade não devem ser interpretados como garantia de conformidade. Este serviço está atualmente em versão prévia e está sujeito aos termos e condições nos [termos dos serviços online](https://go.microsoft.com/fwlink/?linkid=2108910).

## <a name="overview"></a>Visão Geral

O painel de Pontuação de conformidade exibe uma pontuação que mede seu progresso ao concluir ações de aperfeiçoamento nos controles. Seus pontos são acumulados ao concluir ações.

Sua pontuação é calculada com base na conclusão de ações gerenciadas pela Microsoft e ações gerenciadas pelo cliente. Cada ação tem um impacto diferente na sua pontuação, dependendo dos possíveis riscos envolvidos, portanto, a pontuação pode ajudar a priorizar a ação a ser focalizada para melhorar a postura geral de conformidade.

Os valores de Pontuação de conformidade exibidos para o controle são aplicados *em sua totalidade* à sua pontuação total em uma base de aprovação/falha. O controle é implementado e passa o teste de avaliação subsequente ou não. Os pontos atribuídos são adicionados à pontuação de conformidade quando o controle tem:

- **Status de implementação** igual a **implementação** **implementada** ou alternativa,
- O **resultado do teste** é **passado**.

A soma dos pontos obtidos por meio de ações de melhoria é a pontuação de controle. A soma de suas pontuações de controle é a pontuação de avaliação. A soma de suas pontuações de avaliação é a pontuação de conformidade geral

## <a name="initial-score-based-on-microsoft-365-data-protection-baseline"></a>Pontuação inicial com base na linha de base de proteção de dados da Microsoft 365
  
A pontuação de conformidade fornece uma pontuação pronta para uso com base na linha de base de proteção de dados do Microsoft 365, que é um conjunto de controles que inclui normas e padrões de proteção de dados e governança de dados gerais. Essa linha de base desenha elementos primariamente da NIST CSF (National Institute of Standards and Technology cybersecurity Framework) e ISO (International Organization for Standardization), bem como de FedRAMP (Federal Risk and Authorization Management Program) e RGPD (regulamentação geral de proteção de dados da União Europeia).

## <a name="how-compliance-score-continuously-assesses-controls"></a>Como a pontuação de conformidade avalia os controles continuamente

A pontuação de conformidade verifica automaticamente o ambiente Microsoft 365 e detecta as configurações do sistema, atualizando continuamente e automaticamente o status do controle técnico. A pontuação de conformidade usa a pontuação segura como o mecanismo subjacente que realiza o monitoramento. [Saiba mais sobre a pontuação segura e como ela funciona](../security/mtp/microsoft-secure-score.md).

Seu status de controle é atualizado no painel de Pontuação de conformidade a cada 24 horas. Depois de seguir uma recomendação para implementar um controle, você verá o status do controle atualizado no dia seguinte.

Por exemplo, se você ativar a MFA (autenticação multifator) no portal do Azure AD, a pontuação de conformidade detectará a configuração e refletirá isso nos detalhes da solução de acesso de controle. Por outro lado, se você não tiver ativado o MFA, os sinalizadores de Pontuação de conformidade que são uma ação recomendada para você realizar.

Durante a visualização pública, a avaliação contínua está disponível para uma parte dos controles, mas não todos.
  
## <a name="control-types-and-points"></a>Tipos de controle e pontos

A pontuação de conformidade controla dois tipos de controles, gerenciados pela Microsoft e pelo cliente, cada um deles com pontos que contribuem para sua pontuação geral:

1. Os **pontos gerenciados pelo cliente** contribuem para sua pontuação de conformidade com base em controles gerenciados pela sua organização.
2. Os **pontos gerenciados pela Microsoft** contribuem para sua pontuação de conformidade com base em controles gerenciados pela Microsoft como um provedor de serviços de nuvem.

Os controles recebem um valor de pontuação com base no fato de serem obrigatórios ou discricionários, e se são preventivos, de detecção ou corretivas, conforme descrito abaixo.

### <a name="mandatory-and-discretionary-controls"></a>Controles obrigatórios e discricionários

 - Os **controles obrigatórios** são ações que não podem ser ignoradas intencionalmente ou acidentalmente. Um exemplo é uma política de senha gerenciada centralmente que define os requisitos de tamanho, complexidade e validade da senha. Os usuários devem cumprir esses requisitos para acessar o sistema.
  
 - Os **controles discricionários** dependem dos usuários para entender a política e agir de acordo. Por exemplo, uma política que exija que os usuários bloqueiem seu computador quando deixam de ser um controle discricionário, pois ele se baseia no usuário.
  
### <a name="preventative-detective-and-corrective-controls"></a>Controles de prevenção, detecção e correção
  
 - Os **controles preventivos** tratam de riscos específicos. Por exemplo, a proteção de informações em repouso usando criptografia é um controle preventivo contra ataques e violações. A separação de direitos é um controle preventivo para gerenciar o conflito de interesse e proteção contra fraudes.
  
 - Os **controles de detecção** monitoram ativamente os sistemas para identificar condições ou comportamentos irregulares que representam riscos ou que podem ser usados para detectar intrusões ou determinar se ocorre uma violação. Auditoria de acesso do sistema e auditorias de ações administrativas privilegiadas são tipos de controles de monitoramento de detecção. Auditorias de conformidade normativa são um tipo de controle de detecção usado para encontrar problemas de processo.
  
- Os **controles corretivos** tentam manter os efeitos adversos de um incidente de segurança para um mínimo, realizar ações corretivas para reduzir o efeito imediato e reverter os danos, se possível. Privacy incidente Response é um controle corretivo para limitar danos e restaurar sistemas para um estado operacional após uma violação.
  
Cada controle tem um valor atribuído em Pontuação de conformidade com base no risco que representa:

|**Tipo**|**Pontuação atribuída**|
|:-----|:-----|
| Obrigatórios preventivos | 27 |
| Discricionários preventivos | 9  |
| Detecção obrigatória | 3D |
| Detecção arbitrária | 1 |
| Obrigatório corretivo | 3D |
| Condicionalmente | 1 |
  