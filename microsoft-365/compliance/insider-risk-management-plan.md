---
title: Planejar o gerenciamento de riscos internos
description: Saiba como planejar o uso de políticas de gerenciamento de risco do insider em sua organização.
keywords: Microsoft 365, risco de insider, gerenciamento de riscos, conformidade
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: 5944439da4c4df9253e5c6d67944ccc1a7339e71
ms.sourcegitcommit: a08103bc120bdec7cfeaf67c1be4e221241e69ad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/21/2020
ms.locfileid: "45199767"
---
# <a name="plan-for-insider-risk-management"></a>Planejar o gerenciamento de riscos internos

Antes de começar a usar o [Gerenciamento de risco do insider](insider-risk-management.md) em sua organização, há importantes atividades de planejamento e considerações que devem ser revisadas por suas equipes de gerenciamento de conformidade e tecnologia de informação. A compreensão e o planejamento minuciosos para implantação nas áreas a seguir ajudarão a garantir que a implementação e o uso dos recursos de gerenciamento de risco do insider sejam fáceis e que sejam alinhados com as práticas recomendadas para a solução.

## <a name="work-with-stakeholders-in-your-organization"></a>Trabalhar com participantes em sua organização

Identifique os participantes apropriados em sua organização para colaborar para executar ações nos alertas e casos de gerenciamento de risco do insider. Alguns dos participantes recomendados que devem ser considerados, incluindo o planejamento inicial e o fluxo de [trabalho de gerenciamento de risco do insider](insider-risk-management.md#workflow) de ponta a ponta, são pessoas das seguintes áreas da organização:

- Tecnologia de informações
- Conformidade
- Privacidade
- Segurança
- Recursos humanos
- Jurídico

## <a name="determine-any-regional-compliance-requirements"></a>Determinar os requisitos regionais de conformidade

Diferentes áreas geográficas e organizacionais podem ter requisitos de conformidade e privacidade diferentes das outras áreas da sua organização. Trabalhe com os participantes nessas áreas para garantir que eles compreendam os controles de conformidade e privacidade no gerenciamento de risco do insider e como eles devem ser usados em diferentes áreas da organização. Em alguns cenários, os requisitos de conformidade e privacidade podem exigir políticas que designam ou restrinjam alguns participantes de investigações e casos com base no caso de requisitos de usuário ou de política ou de conformidade da área.

Se você tiver requisitos para que os stakeholders específicos estejam envolvidos nas investigações de casos que envolvem usuários em determinadas regiões, funções ou divisões, convém implementar [políticas de gerenciamento de riscos](insider-risk-management-policies.md) separadas (mesmo se idênticas) que direcionam as diferentes regiões e populações. Essa configuração facilitará a triagem e gerenciar os casos que sejam relevantes para suas funções e regiões. Além disso, talvez você queira considerar a criação de processos e políticas para regiões em que os investigadores e os revisores falam o mesmo idioma que os usuários para ajudar a simplificar o processo de escalação para alertas e casos de gerenciamento de risco do insider.

## <a name="plan-for-the-review-and-investigation-workflow"></a>Planejar o fluxo de trabalho de análise e investigação

Selecione participantes dedicados para monitorar e revisar os alertas e casos em uma cadência regular no [centro de conformidade da Microsoft 365](https://compliance.microsoft.com/). Certifique-se de entender como você atribuirá diferentes participantes aos diferentes grupos de função disponíveis no gerenciamento de risco do insider.

Dependendo da estrutura da sua equipe de gerenciamento de conformidade, você tem opções para atribuir usuários a grupos de função específicos para gerenciar diferentes conjuntos de recursos de gerenciamento de risco do insider. Escolha uma destas opções de grupo de funções ao configurar o gerenciamento de risco do insider:

| **Default management role assignments for this role** | **Permissões de função** |
| :---- | :---------------- |
| **Gerenciamento de risco do insider** | Use esse grupo de funções para gerenciar o gerenciamento de riscos do insider para sua organização em um único grupo. Ao adicionar todas as contas de usuário para administradores, analistas e investigadores designados, você pode configurar permissões de gerenciamento de risco do insider em um único grupo. Esse grupo de função contém todas as funções de permissão de gerenciamento de risco do insider. Essa configuração é a maneira mais fácil de começar rapidamente com o gerenciamento de risco do insider e é uma boa opção para organizações que não precisam de permissões separadas definidas para grupos de usuários separados.|
| **Administrador de gerenciamento de risco do insider** | Use esse grupo de funções para configurar inicialmente o gerenciamento de riscos de insider e depois para separar os administradores de risco internos em um grupo definido.  Os usuários desse grupo de funções podem criar, ler, atualizar e excluir políticas de gerenciamento de risco do Insider, configurações globais e atribuições de grupos de função. |
| **Analistas de gerenciamento de risco do insider** | Use esse grupo para atribuir permissões a usuários que atuarão como analistas de caso de risco do insider. Os usuários desse grupo de funções podem acessar todos os modelos de alerta, casos e avisos de gerenciamento de risco do insider. Eles não podem acessar o Gerenciador de conteúdo de risco do insider. |
| **Investigadores de gerenciamento de risco do insider** | Use esse grupo para atribuir permissões a usuários que atuarão como investigadores de dados de risco do insider. Os usuários desse grupo de funções podem acessar todos os alertas de gerenciamento de risco do Insider, casos, modelos de avisos e o Gerenciador de conteúdo para todos os casos. |

## <a name="understand-requirements-and-dependencies"></a>Entender os requisitos e dependências

Dependendo de como você planeja implementar políticas de gerenciamento de risco do Insider, você precisa ter as assinaturas de licenciamento do Microsoft 365 e compreender e planejar alguns pré-requisitos de solução.

**Licenciamento:** O gerenciamento de riscos do insider está disponível como parte da seleção ampla de assinaturas de licenciamento da Microsoft 365. Para obter detalhes, consulte o artigo sobre [como começar a usar o gerenciamento de riscos do insider](insider-risk-management-configure.md#before-you-begin) .

Se você não tiver um plano existente do Microsoft 365 Enterprise E5 e quiser experimentar o gerenciamento de risco do Insider, você pode [Adicionar o microsoft 365](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) à sua assinatura existente ou [inscrever-se em uma avaliação](https://www.microsoft.com/microsoft-365/enterprise) do Microsoft 365 Enterprise e5.

**Requisitos de modelo de política:** Dependendo do modelo de política escolhido, há requisitos que você precisa entender e planejar antes de configurar o gerenciamento de risco do insider em sua organização:

- Ao usar o **roubo de dados por** meio do modelo de usuários, você deve configurar um conector de RH da Microsoft 365 para importar periodicamente informações de recisão e de data de término para usuários em sua organização. Consulte o artigo [importar dados com o conector de RH](import-hr-data.md) para obter orientações passo a passo para configurar o Microsoft 365 HR Connector para sua organização.
- Ao usar modelos de **vazamentos de dados** , você deve configurar pelo menos uma política de prevenção de perda de dados (DLP) para definir informações confidenciais em sua organização e receber alertas de risco do insider para alertas de política de DLP de alta gravidade. Consulte o artigo [criar, testar e ajustar uma política de DLP](create-test-tune-dlp-policy.md) para obter orientações passo a passo para configurar as políticas de DLP para sua organização.
- Ao usar modelos de **violação de política de segurança** , você deve habilitar a proteção avançada contra ameaças do Microsoft defender (ATP) para integração de gerenciamento de risco do insider na central de segurança do defender para importar alertas de violação de segurança. Consulte o artigo [configurar recursos avançados no Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-features) para obter orientações passo a passo para habilitar a integração do Microsoft defender ATP com o gerenciamento de risco do insider.
- Ao usar modelos de **usuário descontentes** , você deve configurar um conector de RH da Microsoft 365 para importar periodicamente informações de status de desempenho ou rebaixamento para usuários em sua organização. Consulte o artigo [importar dados com o conector de RH](import-hr-data.md) para obter orientações passo a passo para configurar o Microsoft 365 HR Connector para sua organização.

## <a name="test-with-a-small-group-of-users-in-a-production-environment"></a>Teste com um pequeno grupo de usuários em um ambiente de produção

Antes de habilitar a solução amplamente em seu ambiente de produção, você pode considerar testar as políticas com um pequeno conjunto de usuários de produção ao conduzir a conformidade, a privacidade e as avaliações legais necessárias em sua organização. Avaliar o gerenciamento de riscos do insider em um ambiente de teste exigiria que você gere ações simuladas do usuário e outros sinais para criar alertas de triagem e casos para processamento. Essa abordagem não é prática para a maioria das organizações, portanto, é preferível testar o gerenciamento de riscos do insider com um pequeno grupo de usuários em um ambiente de produção.

Mantenha o recurso de anonimato em configurações de política habilitados para tornar anônimos os nomes de exibição do usuário no console de gerenciamento de risco do insider durante este teste para manter a privacidade dentro da ferramenta. Essa configuração ajuda a proteger a privacidade de usuários que têm correspondências de política e podem ajudar a promover Objectivity em análises de investigação de dados e análise de alertas de risco do insider.

Se você não vir alertas imediatamente após a configuração de uma política de gerenciamento de risco do Insider, pode significar que o limite de riscos mínimo ainda não foi atingido. Uma boa maneira de verificar se a política é disparada e funcionando conforme o esperado é verificar se o usuário está no escopo da política na página de **usuários** .

## <a name="resources-for-stakeholders"></a>Recursos para participantes

Compartilhe a documentação de gerenciamento de risco do insider com os participantes da sua organização que estão incluídos em seu fluxo de trabalho de gerenciamento e correção:

- [Criar e gerenciar políticas de riscos internos](insider-risk-management-policies.md)
- [Investigar alertas de riscos internos](insider-risk-management-alerts.md)
- [Tomar medidas em casos de riscos internos](insider-risk-management-cases.md)
- [Revisar dados de caso com o Gerenciador de conteúdo do insider](insider-risk-management-content-explorer.md)
- [Criar modelos de aviso de riscos internos](insider-risk-management-notices.md)

## <a name="ready-to-get-started"></a>Pronto para começar?

Pronto para configurar o gerenciamento de risco do insider para sua organização? Confira os seguintes artigos:

- [Introdução às configurações de gerenciamento de risco do insider](insider-risk-management-settings.md) para definir as configurações de política global.
- Comece a usar o [Gerenciamento de risco do insider](insider-risk-management-configure.md) para configurar os pré-requisitos, criar políticas e começar a receber alertas.
