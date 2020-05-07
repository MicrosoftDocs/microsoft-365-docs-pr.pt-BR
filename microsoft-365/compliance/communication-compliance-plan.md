---
title: Planejar a conformidade com comunicações
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
ms.openlocfilehash: 214c5376d4c074525253707e181eee69cefff85e
ms.sourcegitcommit: eb3c7f473e8fe62624f52c9bb38dcd6a96fa58a3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44045843"
---
# <a name="plan-for-communication-compliance"></a>Planejar a conformidade com comunicações

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

Selecione revisores dedicados para monitorar e revisar os alertas em uma cadência regular no [centro de conformidade da Microsoft 365](https://compliance.microsoft.com/). Lembre-se de que você precisará [criar um novo grupo de função](communication-compliance-configure.md#step-1-required-enable-permissions-for-communication-compliance) para habilitar permissões para revisores com o **administrador de análise de supervisão**, o gerenciamento de **casos**, o **administrador de conformidade**e as funções de **revisão** para investigar e corrigir mensagens com correspondências de política.

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
