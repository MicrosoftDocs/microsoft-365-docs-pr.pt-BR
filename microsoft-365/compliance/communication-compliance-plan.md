---
title: Planejar a conformidade em comunicações
description: Saiba mais sobre como planejar o uso da conformidade de comunicação em sua organização.
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: 4c44610f4d74fe9ebf3c8e549692d9cc7cc6cb34
ms.sourcegitcommit: 9550298946f8accb90cd59be7b46b71d4bf4f8cc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/08/2020
ms.locfileid: "46597418"
---
# <a name="plan-for-communication-compliance"></a>Planejar a conformidade em comunicações

Antes de começar a usar a [conformidade de comunicação](communication-compliance.md) em sua organização, há importantes atividades de planejamento e considerações que devem ser revisadas por suas equipes de gerenciamento de conformidade e tecnologia de informação. A compreensão e o planejamento minuciosos para implantação nas áreas a seguir ajudarão a garantir que a implementação e o uso de recursos de conformidade de comunicação sejam adequados e estejam alinhados com as práticas recomendadas para a solução.

## <a name="work-with-stakeholders-in-your-organization"></a>Trabalhar com participantes em sua organização

Identifique os participantes apropriados em sua organização para colaborar para executar ações nos alertas de conformidade de comunicação. Alguns participantes recomendados que devem ser considerados, incluindo o planejamento inicial e o [fluxo de trabalho de conformidade de comunicação](communication-compliance.md#workflow) de ponta a ponta são pessoas das seguintes áreas da sua organização:

- Tecnologia de informações
- Conformidade
- Privacidade
- Segurança
- Recursos humanos
- Jurídico

## <a name="plan-for-the-investigation-and-remediation-workflow"></a>Planejar o fluxo de trabalho de investigação e correção

Selecione participantes dedicados para monitorar e revisar os alertas e casos em uma cadência regular no [centro de conformidade da Microsoft 365](https://compliance.microsoft.com/). Certifique-se de entender como você atribuirá diferentes funções de conformidade de comunicação aos participantes da sua organização.

Dependendo de como você deseja gerenciar políticas e alertas de comunicação, você precisará criar um ou mais novos grupos de função para administradores, revisores e investigadores. Você tem a opção de atribuir usuários a grupos de função específicos para gerenciar diferentes conjuntos de recursos de conformidade de comunicação. Ou você pode decidir criar um grupo de função e atribuir todas as funções de conformidade de comunicação ao grupo. Crie um único grupo de função ou vários grupos para atender melhor aos seus requisitos de gerenciamento de conformidade.

Planeje escolher entre estas opções de função ao configurar seus grupos de função de conformidade de comunicação:

|**Função**|**Permissões de função**|
|:-----|:-----|
| **Administração de conformidade de comunicação** | Os usuários atribuídos a essa função podem criar, ler, atualizar e excluir políticas de conformidade de comunicação, configurações globais e atribuições de grupos de função. Os usuários atribuídos a essa função não podem exibir alertas de mensagem. |
| **Análise de conformidade de comunicação** | Os usuários atribuídos a essa função podem exibir as políticas em que foram atribuídas como revisores, Exibir metadados de mensagem (não o conteúdo da mensagem), escalonar para revisores adicionais ou enviar notificações aos usuários. Os analistas não podem resolver alertas pendentes. |
| **Investigação de conformidade de comunicação** | Os usuários atribuídos a essa função podem exibir metadados e conteúdo de mensagens, escalonar para revisores adicionais, escalonar para uma ocorrência de descoberta eletrônica avançada, enviar notificações aos usuários e resolver o alerta. |
| **Visualizador de conformidade de comunicação** | Os usuários atribuídos a essa função podem acessar todos os widgets de relatório na home page de conformidade de comunicação e podem exibir todos os relatórios de conformidade de comunicação. |
| **Gerenciamento de casos de conformidade de comunicação** | Os usuários atribuídos a essa função podem gerenciar casos e agir em alertas. Essa função é necessária para criar grupos de funções personalizados para administradores, analistas e investigadores. Os grupos personalizados para visualizadores não precisam dessa função atribuída. |

## <a name="plan-for-policies"></a>Planejar políticas

A criação de políticas de conformidade de comunicação é rápida e fácil com os [modelos predefinidos](communication-compliance-feature-reference.md#policy-templates) para linguagem ofensiva, informações confidenciais e conformidade normativa. As políticas de conformidade de comunicação personalizadas permitem a flexibilidade para detectar e investigar problemas específicos da sua organização e seus requisitos.

Ao planejar políticas de conformidade de comunicação, considere o seguinte:

- Considere a adição de todos os usuários em sua organização como dentro do escopo para suas políticas de conformidade de comunicação. A identificação de usuários específicos como dentro do escopo para políticas individuais é útil em algumas circunstâncias, no entanto, a maioria das organizações deve incluir todos os usuários em políticas de conformidade de comunicação otimizadas para detecção de discriminação ou assédio.
- Para simplificar a configuração, considere a criação de grupos para pessoas que precisam de suas comunicações revisadas. Se você estiver usando grupos; Você pode precisar de vários. Por exemplo, se você quiser examinar as comunicações entre dois grupos distintos de pessoas ou se quiser especificar um grupo que não é supervisionado.
- Configure a porcentagem de comunicação a ser revisada às 100% para garantir que as políticas estejam decorrendo todos os problemas de interesse nas comunicações da sua organização.
- Você pode verificar as comunicações de [fontes de terceiros](communication-compliance-feature-reference.md#supported-communication-types) para dados importados em caixas de correio em sua organização do Microsoft 365. Para incluir a análise das comunicações nessas plataformas, você precisará configurar um conector para esses serviços antes que as condições da política de reunião de mensagens sejam monitoradas pela política de comunicação.
- As políticas podem suportar idiomas de monitoramento diferentes do inglês em políticas de conformidade de comunicação personalizadas. Crie um [dicionário de palavra-chave personalizado](communication-compliance-feature-reference.md#custom-keyword-dictionaries) de palavras ofensivas no idioma de sua escolha ou crie seu próprio modelo de aprendizado de máquina usando [classificadores destreinados](classifier-getting-started-with.md) no Microsoft 365.
- Todas as organizações têm padrões de comunicação e necessidades de política diferentes. Monitorar palavras-chave específicas usando [condições de política](communication-compliance-feature-reference.md#conditional-settings) de conformidade de comunicação ou monitorar tipos específicos de informações com [tipos de informações confidenciais personalizados](create-a-custom-sensitive-information-type.md).

## <a name="ready-to-get-started"></a>Pronto para começar?

Para configurar a conformidade de comunicação para sua organização do Microsoft 365, consulte [Configurar a conformidade de comunicação para o microsoft 365](communication-compliance-configure.md) ou confira o [estudo de caso para contoso](communication-compliance-case-study.md) e como configurou rapidamente uma política de conformidade de comunicação para monitorar a linguagem ofensiva no Microsoft Teams, Exchange Online e comunicações do Yammer.
