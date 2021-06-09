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

Antes de começar [a](communication-compliance.md) conformidade com a comunicação em sua organização, há atividades de planejamento e considerações importantes que devem ser revisadas por suas equipes de gerenciamento de conformidade e tecnologia da informação. A compreensão completa e o planejamento da implantação nas seguintes áreas ajudarão a garantir que sua implementação e uso de recursos de conformidade de comunicação vá bem e esteja alinhada com as práticas recomendadas para a solução.

## <a name="work-with-stakeholders-in-your-organization"></a>Trabalhar com as partes interessadas em sua organização

Identifique os participantes apropriados em sua organização para colaborar para a tomada de ações em alertas de conformidade de comunicação. Algumas partes interessadas recomendadas a considerar, incluindo [](communication-compliance.md#workflow) no planejamento inicial e no fluxo de trabalho de conformidade de comunicação de ponta a ponta, são pessoas das seguintes áreas da sua organização:

- Tecnologia da informação
- Conformidade
- Privacidade
- Segurança
- Recursos humanos
- Jurídico

## <a name="plan-for-the-investigation-and-remediation-workflow"></a>Planejar o fluxo de trabalho de investigação e correção

Selecione participantes dedicados para monitorar e revisar os alertas e casos em uma cadência regular no centro de conformidade [Microsoft 365.](https://compliance.microsoft.com/) Certifique-se de entender como você atribuirá usuários e participantes a diferentes grupos de função de conformidade de comunicação em sua organização.

Dependendo de como você deseja gerenciar políticas de comunicação e alertas, você precisará atribuir usuários a um ou mais grupos de funções para administradores, revisadores e investigadores. Você tem a opção de atribuir usuários a grupos de função específicos para gerenciar diferentes conjuntos de recursos de conformidade de comunicação. Ou você pode optar por atribuir todos os usuários de conformidade de comunicação ao grupo de função Conformidade de Comunicação. Use um único grupo de funções ou vários grupos para se ajustar melhor aos seus requisitos de gerenciamento de conformidade.

Planeje escolher entre essas opções de grupo de função ao configurar a conformidade de comunicação:

|**Função**|**Permissões de função**|
|:-----|:-----|
| **Conformidade de comunicação** | Use esse grupo de funções para gerenciar a conformidade de comunicação para sua organização em um único grupo. Ao adicionar todas as contas de usuário para administradores designados, analistas, investigadores e visualizadores, você pode configurar permissões de conformidade de comunicação em um único grupo. Esse grupo de função contém todas as funções de permissão de conformidade de comunicação. Essa configuração é a maneira mais fácil de começar rapidamente com a conformidade de comunicação e é um bom ajuste para organizações que não precisam de permissões separadas definidas para grupos separados de usuários. |
| **Administrador de Conformidade de Comunicação** | Use esse grupo de funções para configurar inicialmente a conformidade de comunicação e posteriormente para segregar os administradores de conformidade de comunicação em um grupo definido. Os usuários atribuídos a esse grupo de funções podem criar, ler, atualizar e excluir políticas de conformidade de comunicação, configurações globais e atribuições de grupo de função. Os usuários atribuídos a esse grupo de funções não podem exibir alertas de mensagens. |
| **Analista de Conformidade de Comunicação** | Use esse grupo para atribuir permissões aos usuários que atuarão como analistas de conformidade de comunicação. Os usuários atribuídos a esse grupo de funções podem exibir políticas nas quais são atribuídos como Revistores, exibir metadados de mensagens (não conteúdo de mensagem), escalonar para revisadores adicionais ou enviar notificações aos usuários. Os analistas não podem resolver alertas pendentes. |
| **Pesquisador de Conformidade de Comunicação** | Use esse grupo para atribuir permissões aos usuários que atuarão como investigadores de conformidade de comunicação. Os usuários atribuídos a esse grupo de funções podem exibir metadados de mensagens e conteúdo, escalonar para revisadores adicionais, escalonar para um caso Advanced eDiscovery, enviar notificações aos usuários e resolver o alerta. |
| **Visualizador de Conformidade de Comunicação** | Use esse grupo para atribuir permissões aos usuários que gerenciarão relatórios de comunicação. Os usuários atribuídos a esse grupo de funções podem acessar todos os widgets de relatório na home page de conformidade de comunicação e podem exibir todos os relatórios de conformidade de comunicação. |

## <a name="plan-for-policies"></a>Planejar políticas

A criação de políticas de conformidade de comunicação é rápida e fácil com os modelos [pré-definidos](communication-compliance-feature-reference.md#policy-templates) para linguagem ofensiva, informações confidenciais e conformidade regulamentar. As políticas de conformidade de comunicação personalizadas permitem a flexibilidade para detectar e investigar problemas específicos de sua organização e requisitos.

Ao planejar políticas de conformidade de comunicação, considere as seguintes áreas:

- Considere adicionar todos os usuários em sua organização como no escopo para suas políticas de conformidade de comunicação. Identificar usuários específicos como no escopo de políticas individuais é útil em algumas circunstâncias, no entanto, a maioria das organizações deve incluir todos os usuários em políticas de conformidade de comunicação otimizadas para detecção de assédio ou discriminação.
- Para simplificar sua instalação, considere a criação de grupos para pessoas que precisam de suas comunicações revisadas. Se você estiver usando grupos; você pode precisar de vários. Por exemplo, se você quiser verificar as comunicações entre dois grupos distintos de pessoas ou se quiser especificar um grupo que não é supervisionado.
- Configure a porcentagem de comunicações a ser revisa em 100% para garantir que as políticas estão recuperando todos os problemas de preocupação nas comunicações da sua organização.
- Você pode verificar comunicações de [fontes de](communication-compliance-feature-reference.md#supported-communication-types) terceiros para dados importados para caixas de correio em sua Microsoft 365 organização. Para incluir a revisão das comunicações nessas plataformas, você precisará configurar um conector para esses serviços antes que as condições da política de reunião de mensagens sejam monitoradas pela política de comunicação.
- As políticas podem dar suporte a idiomas de monitoramento diferentes do inglês em políticas de conformidade de comunicação personalizadas. Crie um [dicionário de palavras-chave](communication-compliance-feature-reference.md#custom-keyword-dictionaries) personalizado de palavras [ofensivas](classifier-get-started-with.md) no idioma de sua escolha ou crie seu próprio modelo de aprendizado de máquina usando classificadores treináveis no Microsoft 365.
- Todas as organizações têm padrões de comunicação e necessidades de política diferentes. Monitore palavras-chave específicas usando condições de [política](communication-compliance-feature-reference.md#conditional-settings) de conformidade de comunicação ou monitore tipos específicos de informações com [tipos de informações confidenciais personalizados.](create-a-custom-sensitive-information-type.md)

## <a name="ready-to-get-started"></a>Pronto para começar?

Para configurar a conformidade de comunicação para sua organização Microsoft 365, consulte Configure communication [compliance for Microsoft 365](communication-compliance-configure.md) or check out the case study for [Contoso](communication-compliance-case-study.md) and how they quickly configured a communication compliance policy to monitor for offensive language in Microsoft Teams, Exchange Online, and Yammer communications.
