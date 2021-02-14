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
ms.openlocfilehash: d64edc9d80722080db18c45127bfc82110d1ea9e
ms.sourcegitcommit: fdb5f9d865037c0ae23aae34a5c0f06b625b2f69
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2020
ms.locfileid: "48131533"
---
# <a name="plan-for-communication-compliance"></a>Planejar a conformidade em comunicações

Antes de começar a [trabalhar](communication-compliance.md) com a conformidade de comunicação em sua organização, há importantes atividades de planejamento e considerações que devem ser analisadas por suas equipes de gerenciamento de conformidade e tecnologia da informação. A compreensão e o planejamento completos da implantação nas seguintes áreas ajudarão a garantir que sua implementação e o uso de recursos de conformidade de comunicação estejam bem e alinhados com as práticas recomendadas para a solução.

## <a name="work-with-stakeholders-in-your-organization"></a>Trabalhar com stakeholders em sua organização

Identifique os participantes apropriados em sua organização para colaborar para a tomada de ações em alertas de conformidade de comunicação. Algumas partes interessadas recomendadas a considerar, incluindo [](communication-compliance.md#workflow) no planejamento inicial e no fluxo de trabalho de conformidade de comunicação de ponta a ponta, são pessoas das seguintes áreas da sua organização:

- Tecnologia da informação
- Conformidade
- Privacidade
- Segurança
- Recursos humanos
- Jurídico

## <a name="plan-for-the-investigation-and-remediation-workflow"></a>Planejar o fluxo de trabalho de investigação e correção

Selecione participantes dedicados para monitorar e analisar os alertas e ocorrências regularmente no centro de conformidade do [Microsoft 365.](https://compliance.microsoft.com/) Certifique-se de entender como você atribuirá usuários e participantes a diferentes grupos de função de conformidade de comunicação em sua organização.

Dependendo de como você deseja gerenciar políticas e alertas de comunicação, você precisará atribuir usuários a um ou mais grupos de função para administradores, revisadores e investigadores. Você tem a opção de atribuir usuários a grupos de função específicos para gerenciar diferentes conjuntos de recursos de conformidade de comunicação. Ou você pode optar por atribuir todos os usuários de conformidade de comunicação ao grupo de função conformidade de comunicação. Use um único grupo de função ou vários grupos para melhor se ajustar aos seus requisitos de gerenciamento de conformidade.

Planeje escolher entre essas opções de grupo de função ao configurar a conformidade de comunicação:

|**Função**|**Permissões de função**|
|:-----|:-----|
| **Conformidade de comunicação** | Use esse grupo de função para gerenciar a conformidade de comunicação para sua organização em um único grupo. Ao adicionar todas as contas de usuário para administradores designados, analistas, investigadores e visualizadores, você pode configurar permissões de conformidade de comunicação em um único grupo. Esse grupo de função contém todas as funções de permissão de conformidade de comunicação. Essa configuração é a maneira mais fácil de começar rapidamente com a conformidade de comunicação e é uma boa opção para organizações que não precisam de permissões separadas definidas para grupos separados de usuários. |
| **Administrador de Conformidade de Comunicação** | Use esse grupo de função para configurar inicialmente a conformidade de comunicação e posteriormente segregar os administradores de conformidade de comunicação em um grupo definido. Os usuários atribuídos a esse grupo de funções podem criar, ler, atualizar e excluir políticas de conformidade de comunicação, configurações globais e atribuições de grupo de função. Os usuários atribuídos a esse grupo de funções não podem exibir alertas de mensagem. |
| **Analista de Conformidade de Comunicação** | Use esse grupo para atribuir permissões aos usuários que atuarão como analistas de conformidade de comunicação. Os usuários atribuídos a esse grupo de funções podem exibir políticas às quais são atribuídos como Revisadores, exibir metadados de mensagem (não conteúdo de mensagem), escalonar para revistores adicionais ou enviar notificações aos usuários. Os analistas não podem resolver alertas pendentes. |
| **Investigador de conformidade de comunicação** | Use esse grupo para atribuir permissões aos usuários que atuarão como investigadores de conformidade de comunicação. Os usuários atribuídos a esse grupo de funções podem exibir metadados e conteúdo de mensagens, escalonar para revistores adicionais, escalonar para um caso de Descoberta Avançada, enviar notificações aos usuários e resolver o alerta. |
| **Visualizador de Conformidade de Comunicação** | Use esse grupo para atribuir permissões a usuários que gerenciarão relatórios de comunicação. Os usuários atribuídos a esse grupo de função podem acessar todos os widgets de relatórios na home page de conformidade de comunicação e podem exibir todos os relatórios de conformidade de comunicação. |

## <a name="plan-for-policies"></a>Planejar políticas

Criar políticas de conformidade de comunicação é rápido e fácil com os modelos [predefinidas](communication-compliance-feature-reference.md#policy-templates) para linguagem ofensiva, informações confidenciais e conformidade regulatória. As políticas de conformidade de comunicação personalizada permitem a flexibilidade para detectar e investigar problemas específicos da sua organização e requisitos.

Ao planejar políticas de conformidade de comunicação, considere as seguintes áreas:

- Considere a adição de todos os usuários em sua organização no escopo das políticas de conformidade de comunicação. Identificar usuários específicos como no escopo de políticas individuais é útil em algumas circunstâncias, no entanto, a maioria das organizações deve incluir todos os usuários em políticas de conformidade de comunicação otimizadas para detecção de abuso ou detecção de detecção.
- Para simplificar sua configuração, considere criar grupos para pessoas que precisam de suas comunicações revisadas. Se você estiver usando grupos; você pode precisar de vários. Por exemplo, se você quiser verificar as comunicações entre dois grupos distintos de pessoas ou se quiser especificar um grupo que não seja supervisionado.
- Configure o percentual de comunicações a ser revisado em 100% para garantir que as políticas capturam todos os problemas de preocupação nas comunicações da sua organização.
- Você pode verificar comunicações de [fontes de](communication-compliance-feature-reference.md#supported-communication-types) terceiros em busca de dados importados para caixas de correio em sua organização do Microsoft 365. Para incluir a revisão das comunicações nessas plataformas, você precisará configurar um conector para esses serviços antes que as mensagens que atenderem às condições da política sejam monitoradas pela política de comunicação.
- As políticas podem dar suporte a idiomas de monitoramento diferentes do inglês em políticas de conformidade de comunicação personalizadas. Crie um [dicionário](communication-compliance-feature-reference.md#custom-keyword-dictionaries) de palavras-chave personalizado de palavras [ofensivas](classifier-get-started-with.md) na linguagem de sua escolha ou crie seu próprio modelo de aprendizado de máquina usando classificadores de treinamento no Microsoft 365.
- Todas as organizações têm padrões de comunicação e necessidades de política diferentes. Monitore palavras-chave específicas usando condições de política de conformidade [de](communication-compliance-feature-reference.md#conditional-settings) comunicação ou monitore tipos específicos de informações com [tipos personalizados de informações confidenciais.](create-a-custom-sensitive-information-type.md)

## <a name="ready-to-get-started"></a>Pronto para começar?

Para configurar a conformidade de comunicação para sua organização do Microsoft 365, confira Configurar a conformidade de comunicação com o [Microsoft 365](communication-compliance-configure.md) ou confira o estudo de caso da [Contoso](communication-compliance-case-study.md) e como eles configuraram rapidamente uma política de conformidade de comunicação para monitorar o idioma ofensivo nas comunicações do Microsoft Teams, do Exchange Online e do Yammer.
