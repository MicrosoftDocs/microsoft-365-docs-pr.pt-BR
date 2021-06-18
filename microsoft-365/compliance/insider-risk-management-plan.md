---
title: Planejar o gerenciamento de riscos internos
description: Saiba como planejar o uso de políticas de gerenciamento de riscos internas em sua organização.
keywords: Microsoft 365, risco interno, gerenciamento de riscos, conformidade
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
ms.openlocfilehash: 6884ec3b2bc7c24e4f7f6e62d9b24add3aeee2c0
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007340"
---
# <a name="plan-for-insider-risk-management"></a>Planejar o gerenciamento de riscos internos

Antes de começar a trabalhar com o gerenciamento de riscos [insider](insider-risk-management.md) em sua organização, há importantes atividades de planejamento e considerações que devem ser revisadas por suas equipes de gerenciamento de conformidade e tecnologia da informação. O entendimento e o planejamento completos da implantação nas seguintes áreas ajudarão a garantir que a implementação e o uso de recursos de gerenciamento de riscos insider vão bem e estão alinhados com as práticas recomendadas para a solução.

## <a name="work-with-stakeholders-in-your-organization"></a>Trabalhar com as partes interessadas em sua organização

Identifique os participantes apropriados em sua organização para colaborar para a tomada de ações em alertas e casos de gerenciamento de riscos insider. Algumas partes interessadas recomendadas a considerar, incluindo [](insider-risk-management.md#workflow) no planejamento inicial e no fluxo de trabalho de gerenciamento de risco interno de ponta a ponta, são pessoas das seguintes áreas da sua organização:

- Tecnologia da informação
- Conformidade
- Privacidade
- Segurança
- Recursos humanos
- Jurídico

## <a name="determine-any-regional-compliance-requirements"></a>Determinar quaisquer requisitos de conformidade regional

Áreas geográficas e organizacionais diferentes podem ter requisitos de conformidade e privacidade diferentes de outras áreas da sua organização. Trabalhe com as partes interessadas nessas áreas para garantir que eles entendam os controles de conformidade e privacidade no gerenciamento de riscos internos e como eles devem ser usados em diferentes áreas da sua organização. Em alguns cenários, os requisitos de conformidade e privacidade podem exigir políticas que designem ou restrinjam algumas partes interessadas de investigações e casos com base no caso de um usuário ou requisitos regulatórios ou de política para a área.

Se você tiver requisitos para que as partes interessadas específicas sejam envolvidas em investigações de caso que [](insider-risk-management-policies.md) envolvam usuários em determinadas regiões, funções ou divisões, talvez você queira implementar políticas de gerenciamento de riscos internas separadas (mesmo que idênticas) voltadas para as diferentes regiões e populações. Essa configuração facilitará a triagem e gerenciará casos relevantes para suas funções e regiões. Além disso, talvez você queira considerar a criação de processos e políticas para regiões onde os investigadores e revisadores falam o mesmo idioma que os usuários para ajudar a simplificar o processo de escalonamento para alertas e casos de gerenciamento de riscos internos.

## <a name="plan-for-the-review-and-investigation-workflow"></a>Planejar o fluxo de trabalho de revisão e investigação

Selecione participantes dedicados para monitorar e revisar os alertas e casos em uma cadência regular no Centro de conformidade [do Microsoft 365.](https://compliance.microsoft.com/) Certifique-se de entender como você atribuirá diferentes participantes aos diferentes grupos de função disponíveis no gerenciamento de riscos insider.

Dependendo da estrutura da sua equipe de gerenciamento de conformidade, você tem opções para atribuir usuários a grupos de funções específicos para gerenciar diferentes conjuntos de recursos de gerenciamento de risco interno. Para exibir  a guia Permissões no Centro de Conformidade e Conformidade do Office 365 Security  & e gerenciar grupos de funções, você precisa ser atribuído ao grupo de função Gerenciamento da Organização ou precisa ter a função gerenciamento de *função.* Escolha entre essas opções de grupo de função ao configurar o gerenciamento de riscos insider:

| **Default management role assignments for this role** | **Permissões de função** |
| :------------- | :------------------- |
| **Gerenciamento de riscos do Insider** | Use este grupo de função para gerenciar o gerenciamento de risco inerno da sua organização em um único grupo. Ao adicionar todas as contas de usuário para administradores designados, analistas, investigadores e auditores, você pode configurar permissões de gerenciamento de riscos internas em um único grupo. Este grupo de funções contém todas as funções de permissão de gerenciamento de risco interno e permissões associadas. Essa configuração é a maneira mais fácil de começar rapidamente com o gerenciamento de riscos insider e é um bom ajuste para organizações que não precisam de permissões separadas definidas para grupos separados de usuários. Ao usar essa configuração, você deve ter sempre pelo menos um usuário atribuído a esse grupo de funções para garantir que suas políticas funcionem conforme o esperado e para que o usuário possa criar e editar políticas, definir configurações de solução e revisar os avisos de saúde da política. |
| **Administrador de Gerenciamento de Riscos do Insider** | Use esse grupo de funções para configurar inicialmente o gerenciamento de riscos insider e, posteriormente, separar administradores de risco interno em um grupo definido. Os usuários neste grupo de funções podem habilitar e exibir insights de análise e criar, ler, atualizar e excluir políticas de gerenciamento de riscos insider, configurações globais e atribuições de grupo de função. Ao usar essa configuração, você deve ter sempre pelo menos um usuário atribuído a esse grupo de funções para garantir que suas políticas funcionem conforme o esperado e para que o usuário possa criar e editar políticas, definir configurações de solução e revisar os avisos de saúde da política. |
| **Analistas do Gerenciamento de Risco Interno** | Use este grupo para atribuir permissões aos usuários que atuarão como analistas de casos de risco internos. Os usuários neste grupo de funções podem acessar e exibir todos os alertas de gerenciamento de riscos insider, casos, insights de análise e modelos de avisos. Eles não podem acessar o explorador de conteúdo de risco interno. |
| **Investigadores do Gerenciamento de Risco Interno** | Use este grupo para atribuir permissões aos usuários que atuarão como investigadores de dados do risco interno. Os usuários neste grupo de funções podem acessar todos os alertas, casos, modelos de avisos e o explorador de conteúdo para todos os casos. |
| **Auditores de Gerenciamento de Riscos do Insider** | Use esse grupo para atribuir permissões aos usuários que auditarão atividades de gerenciamento de riscos insider. Os usuários neste grupo de funções podem acessar o log de auditoria de risco interno. |

## <a name="understand-requirements-and-dependencies"></a>Compreender requisitos e dependências

Dependendo de como você planeja implementar políticas de gerenciamento de riscos insider, você precisa ter as assinaturas de licenciamento adequadas do Microsoft 365 e entender e planejar alguns pré-requisitos de solução.

**Licenciamento:** O gerenciamento de riscos insider está disponível como parte de uma ampla seleção de assinaturas de licenciamento do Microsoft 365. Para obter detalhes, consulte o artigo Sobre como começar com o gerenciamento de riscos [insider.](insider-risk-management-configure.md#subscriptions-and-licensing)

Se você não tiver um plano existente do Microsoft 365 Enterprise E5 e quiser tentar o gerenciamento de riscos [](https://www.microsoft.com/microsoft-365/enterprise) insider, adicione o [Microsoft 365](/office365/admin/try-or-buy-microsoft-365) à sua assinatura existente ou inscreva-se para uma avaliação do Microsoft 365 Enterprise E5.

**Requisitos de modelo de política:** Dependendo do modelo de política escolhido, há requisitos que você precisa entender e planejar antes de configurar o gerenciamento de riscos insider em sua organização:

- Ao usar o **modelo de** roubo de dados ao separar usuários, você deve configurar um conector de RH do Microsoft 365 para importar periodicamente informações de data de demissão e término para usuários em sua organização. Consulte o artigo [Importar dados com o conector de RH ](import-hr-data.md) para obter orientações passo a passo para configurar o conector de RH do Microsoft 365 para sua organização.
- Ao usar modelos de **vazamentos** de dados, você deve configurar pelo menos uma política de Prevenção contra Perda de Dados (DLP) para definir informações confidenciais em sua organização e receber alertas de risco interno para alertas de política DLP de alta gravidade. Consulte o artigo [Criar, testar e afinar uma política DLP](create-test-tune-dlp-policy.md) para orientação passo a passo para configurar políticas DLP para sua organização.
- Ao usar **modelos de** violação de política de segurança, você deve habilitar o Microsoft Defender for Endpoint para integração de gerenciamento de riscos insider no Defender Security Center para importar alertas de violação de segurança. Consulte o [artigo Configurar recursos avançados](/windows/security/threat-protection/microsoft-defender-atp/advanced-features) no Microsoft Defender para obter orientações passo a passo para habilitar a integração do Defender para Ponto de Extremidade com o gerenciamento de riscos insider.
- Ao usar **modelos de** usuário insatisfeitos, você deve configurar um conector de RH do Microsoft 365 para importar periodicamente informações de status de desempenho ou rebaixamento para usuários em sua organização. Consulte o artigo [Importar dados com o conector de RH ](import-hr-data.md) para obter orientações passo a passo para configurar o conector de RH do Microsoft 365 para sua organização.

## <a name="test-with-a-small-group-of-users-in-a-production-environment"></a>Testar com um pequeno grupo de usuários em um ambiente de produção

Antes de habiligá-la amplamente em seu ambiente de produção, você pode considerar testar as políticas com um pequeno conjunto de usuários de produção durante a realização das avaliações necessárias de conformidade, privacidade e jurídico em sua organização. Avaliar o gerenciamento de risco interno em um ambiente de teste exigiria que você gerasse ações de usuário simuladas e outros sinais para criar alertas para triagem e casos para processamento. Essa abordagem não é prática para a maioria das organizações, portanto, é preferível testar o gerenciamento de riscos internos com um pequeno grupo de usuários em um ambiente de produção.

Mantenha o recurso de anonimização nas configurações de política habilitadas para anonimizar nomes de exibição do usuário no console de gerenciamento de riscos internos durante esse teste para manter a privacidade dentro da ferramenta. Essa configuração ajuda a proteger a privacidade dos usuários que têm as visões de política e pode ajudar a promover a objetividade em análises de análise e investigação de dados para alertas de risco insider.

Se você não vir nenhum alerta imediatamente após a configuração de uma política de gerenciamento de riscos insider, isso pode significar que o limite mínimo de risco ainda não foi atendido. Uma boa maneira de verificar se a política foi acionada e funcionando conforme o esperado é ver se o usuário está no escopo da política na **página Usuários.**

## <a name="resources-for-stakeholders"></a>Recursos para participantes

Compartilhe a documentação de gerenciamento de riscos insider com as partes interessadas em sua organização incluídas no fluxo de trabalho de gerenciamento e correção:

- [Criar e gerenciar políticas de riscos internos](insider-risk-management-policies.md)
- [Investigar alertas de riscos internos](insider-risk-management-alerts.md)
- [Tomar medidas em casos de riscos internos](insider-risk-management-cases.md)
- [Analisar dados de caso com o explorador de conteúdo de risco interno](insider-risk-management-content-explorer.md)
- [Criar modelos de aviso de riscos internos](insider-risk-management-notices.md)

## <a name="ready-to-get-started"></a>Pronto para começar?

Pronto para configurar o gerenciamento de riscos insider para sua organização? Revise os seguintes artigos:

- [Para começar, você pode começar com as configurações](insider-risk-management-settings.md) de gerenciamento de riscos internas para definir as configurações de política global.
- [Comece com o gerenciamento de riscos insider](insider-risk-management-configure.md) para configurar pré-requisitos, criar políticas e começar a receber alertas.
