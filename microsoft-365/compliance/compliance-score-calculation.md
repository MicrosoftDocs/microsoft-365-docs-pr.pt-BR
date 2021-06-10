---
title: Cálculo da pontuação de conformidade
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
description: Entenda como o Microsoft Compliance Manager calcula uma pontuação personalizada com base em ações tomadas para resolver riscos e melhorar sua postura de conformidade.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 756ce207b1e9583bf63f19351e85955950487404
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51052109"
---
# <a name="compliance-score-calculation"></a>Cálculo da pontuação de conformidade

**Neste artigo:** Saiba como o Gerenciador de Conformidade calcula uma pontuação de conformidade para sua organização. Este artigo explica como **interpretar** sua pontuação , o que a avaliação da Linha de **Base** de Proteção de Dados **inclui,** monitoramento contínuo e como diferentes tipos de ações são gerenciados e **pontuados.**

> [!IMPORTANT]
> As recomendações do Gerenciador de Conformidade não devem ser interpretadas como uma garantia de conformidade. Você deve avaliar e validar a eficácia dos controles do cliente de acordo com seu ambiente regulatório. Esses serviços estão sujeitos aos termos e condições nos Termos [de Serviços Online.](https://go.microsoft.com/fwlink/?linkid=2108910) Consulte também [Microsoft 365 de licenciamento para segurança e conformidade.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)

## <a name="how-to-read-your-compliance-score"></a>Como ler sua pontuação de conformidade

O painel do Gerenciador de Conformidade exibe sua pontuação geral de conformidade. Essa pontuação mede seu progresso na conclusão das ações de melhoria recomendadas nos controles. Sua pontuação pode ajudá-lo a entender sua postura de conformidade atual. Ele também pode ajudá-lo a priorizar ações com base no potencial de reduzir o risco.

Um valor de pontuação é atribuído a três níveis:

1. **Pontuação da ação de** melhoria: cada ação tem um impacto diferente em sua pontuação, dependendo do risco potencial envolvido

2. **Pontuação de** controle : essa pontuação é a soma de pontos obtidos concluindo ações de melhoria dentro do controle. Essa soma é aplicada em sua totalidade à sua pontuação geral de conformidade quando o controle atende a ambas as seguintes condições:
    - **O Status da Implementação** é **igual a Implementação** Implementada **ou Alternativa** e
    - **Resultado do teste** é igual **a Passado**.

3. **Pontuação de** avaliação : essa pontuação é a soma de suas pontuações de controle. Ele é calculado usando pontuações de ação. Cada ação da Microsoft e cada ação de aperfeiçoamento gerenciada por sua organização é contada uma vez, independentemente da frequência com que ela é referenciada em um controle.

A pontuação geral de conformidade é calculada usando pontuações de ação, onde cada ação da Microsoft é contada uma vez, cada ação técnica gerenciada é contada uma vez e cada ação não técnica gerenciada é contada uma vez por grupo. Essa lógica foi projetada para fornecer a contabilidade mais precisa de como as ações são implementadas e testadas em sua organização. Você pode observar que isso pode fazer com que sua pontuação geral de conformidade seja diferente da média de suas pontuações de avaliação. Leia mais abaixo sobre [como as ações são pontuadas.](#action-types-and-points)

## <a name="initial-score-based-on-microsoft-365-data-protection-baseline"></a>Pontuação inicial com base Microsoft 365 de proteção de dados
  
O Gerenciador de Conformidade fornece uma pontuação inicial com base na linha de base Microsoft 365 proteção de dados. Essa linha de base é um conjunto de controles que inclui os principais regulamentos e padrões para proteção de dados e governança geral de dados. Essa linha de base desenha elementos principalmente do NIST CSF (National Institute of Standards and Technology Cybersecurity Framework) e ISO (International Organization for Standardization), bem como do FedRAMP (Programa Federal de Gerenciamento de Riscos e Autorizações) e do RGPD (Regulamento Geral de Proteção de Dados da União Europeia).

Sua pontuação inicial é calculada de acordo com a avaliação padrão da Linha de Base de Proteção de Dados fornecida a todas as organizações. Na primeira visita, o Gerenciador de Conformidade já está coletando sinais de suas soluções Microsoft 365 de segurança. Você verá rapidamente como sua organização está se portando em relação aos principais padrões e regulamentos de proteção de dados e verá ações de melhoria sugeridas a executar.

Como todas as organizações têm necessidades específicas, o Gerenciador de Conformidade depende de você para configurar e gerenciar avaliações para ajudar a minimizar e reduzir o risco da forma mais abrangente possível.

## <a name="how-compliance-manager-continuously-assesses-controls"></a>Como o Gerenciador de Conformidade avalia continuamente os controles

O Gerenciador de Conformidade verifica automaticamente seu ambiente de Microsoft 365 e detecta as configurações do sistema, atualizando continuamente e automaticamente seu status de ação técnica. A Pontuação Segura da Microsoft é o mecanismo subjacente que executa o monitoramento.

Seu status de ação é atualizado no painel a cada 24 horas. Depois de seguir uma recomendação para implementar um controle, normalmente você verá o status de controle atualizado no dia seguinte.

Por exemplo, se você ativar a autenticação multifator (MFA) no portal do Azure AD, o Gerenciador de Conformidade detectará a configuração e a refletirá nos detalhes da solução de acesso ao controle. Por outro lado, se você não a ativar o MFA, o Gerenciador de Conformidade sinaliza como uma ação recomendada a ser tomada.

Saiba mais sobre [a Pontuação Segura e como ela funciona.](../security/defender/microsoft-secure-score.md)
  
## <a name="action-types-and-points"></a>Tipos e pontos de ação

O Gerenciador de Conformidade rastreia dois tipos de ações:

1. **Suas ações de melhoria**: ações que sua organização gerencia.
2. **Ações da Microsoft**: ações gerenciadas pela Microsoft.

Ambos os tipos de ações têm pontos que contam para sua pontuação geral quando concluída.

### <a name="technical-and-non-technical-actions"></a>Ações técnicas e não técnicas

As ações são agrupadas por natureza técnica ou não técnica. O impacto de pontuação de cada ação difere por tipo.

- **As ações técnicas** são implementadas interagindo com a tecnologia de uma solução (por exemplo, alterando uma configuração). Os pontos para ações técnicas são concedidos uma vez por ação, independentemente de quantos grupos ele pertence.

- **Ações não técnicas são** gerenciadas por sua organização e implementadas de maneiras diferentes de trabalhar com a tecnologia de uma solução. Há dois tipos de ações não técnicas: **documentação** e **operacional**. Os pontos dessas ações são aplicados à pontuação de conformidade em um nível de grupo. Isso significa que, se uma ação existir em vários grupos, você receberá o valor de ponto da ação sempre que implementá-la em um grupo.

**Exemplo de como ações técnicas e não técnicas são pontuadas:**

Digamos que você tenha uma ação técnica no valor de 3 pontos existentes em 5 grupos e que tenha uma ação não técnica no valor de 3 pontos que existe nos mesmos 5 grupos.

Se você implementar com êxito a ação técnica, o número total de pontos recebidos será 3. Isso ocorre porque você só precisa implementar a ação uma vez para seu locatário. O status de implementação e teste para a ação técnica mostrará o mesmo em todas as instâncias dessa ação, em cada grupo ao que pertence.

Se você implementar com êxito a ação não técnica em cada um dos 5 grupos, o número total de pontos recebidos será 15. Isso ocorre porque você precisa implementar a ação em cada grupo. O status de implementação e teste para a ação não técnica será diferente entre grupos porque a ação é implementada separadamente em cada um de seus grupos.

Essa lógica de pontuação foi projetada para fornecer a contabilidade mais precisa de como as ações são implementadas e testadas em sua organização.

### <a name="how-score-values-are-determined"></a>Como os valores de pontuação são determinados
 
As ações são atribuídas a um valor de pontuação com base em se elas são obrigatórias ou discricionárias e se são preventivas, detetives ou corretivas.

### <a name="mandatory-and-discretionary-actions"></a>Ações obrigatórias e discricionárias

 - **As ações obrigatórias** não podem ser ignoradas, intencionalmente ou acidentalmente. Um exemplo de uma ação obrigatória é uma política de senha gerenciada centralmente que define os requisitos de comprimento, complexidade e expiração da senha. Os usuários devem seguir estes requisitos para acessar o sistema.
  
 - **As ações discricionárias** dependem dos usuários para entender e aderir a uma política. Por exemplo, uma política que exige o bloqueio do computador pelo usuário quando ele se ausenta é um controle opcional porque depende do usuário.
  
### <a name="preventative-detective-and-corrective-actions"></a>Ações preventivas, de detetives e corretivas
  
 - **Ações preventivas** abordam riscos específicos. Por exemplo, proteger as informações em repouso usando criptografia é um controle preventivo contra ataques e violações. A separação de funções é uma ação preventiva para gerenciar conflitos de interesse e proteger contra fraudes.
  
 - **Ações de detetive** monitoram ativamente sistemas para identificar condições irregulares ou comportamentos que representam riscos ou que podem ser usados para detectar invasões ou violações. Exemplos incluem auditoria de acesso ao sistema e ações administrativas privilegiadas. As auditorias de conformidade regulamentar são um tipo de ação de detetive usada para encontrar problemas de processo.
  
- **As ações corretivas** tentam manter os efeitos adversos de um incidente de segurança no mínimo, tomar medidas corretivas para reduzir o efeito imediato e reverter os danos, se possível. A resposta a incidentes de privacidade é uma ação corretiva para limitar os danos e restaurar os sistemas a um estado operacional após uma violação.
  
Cada ação tem um valor atribuído no Gerenciador de Conformidade com base no risco que representa:

|**Tipo**|**Pontuação atribuída**|
|:-----|:-----|
| Preventivo obrigatório | 27 |
| Discricionárias preventivas | 9  |
| Detetive obrigatório | 3 |
| Detetive discricionário | 1 |
| Obrigatória corretiva | 3 |
| Discricionário corretivo | 1 |
  
![Valores de ponto de ação do Gerenciador de Conformidade](../media/compliance-score-action-scoring.png "Valores de ponto de ação do Gerenciador de Conformidade")