---
title: Planejar o gerenciamento de riscos internos
description: Saiba como planejar o uso de políticas de gerenciamento de riscos insider em sua organização.
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
ms.openlocfilehash: f2581c4756a57926ab4a4539be8c383b0479e567
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126620"
---
# <a name="plan-for-insider-risk-management"></a>Planejar o gerenciamento de riscos internos

Antes de começar a trabalhar com o gerenciamento de riscos [insider](insider-risk-management.md) em sua organização, há importantes atividades de planejamento e considerações que devem ser analisadas por suas equipes de gerenciamento de conformidade e tecnologia da informação. A compreensão e o planejamento completos para implantação nas áreas a seguir ajudarão a garantir que sua implementação e o uso de recursos de gerenciamento de riscos insider vão bem e estão alinhados com as práticas recomendadas para a solução.

## <a name="work-with-stakeholders-in-your-organization"></a>Trabalhar com stakeholders em sua organização

Identifique os participantes apropriados em sua organização para colaborar para a tomada de ações em alertas e casos de gerenciamento de riscos insider. Algumas partes interessadas recomendadas a considerar, incluindo [](insider-risk-management.md#workflow) no planejamento inicial e no fluxo de trabalho de gerenciamento de risco interno de ponta a ponta, são pessoas das seguintes áreas da sua organização:

- Tecnologia da informação
- Conformidade
- Privacidade
- Segurança
- Recursos humanos
- Jurídico

## <a name="determine-any-regional-compliance-requirements"></a>Determinar os requisitos de conformidade regionais

Áreas geográficas e organizacionais diferentes podem ter requisitos de conformidade e privacidade diferentes de outras áreas da sua organização. Trabalhe com os participantes nessas áreas para garantir que eles entendam os controles de conformidade e privacidade no gerenciamento de riscos internos e como eles devem ser usados em diferentes áreas da sua organização. Em alguns cenários, os requisitos de conformidade e privacidade podem exigir políticas que designem ou restrinjam algumas partes interessadas de investigações e casos com base no caso de um usuário ou requisitos regulatórios ou de política para a área.

Se você tiver requisitos para que as partes interessadas específicas sejam envolvidas em investigações de caso que [](insider-risk-management-policies.md) envolvam usuários em determinadas regiões, funções ou divisões, talvez você queira implementar políticas de gerenciamento de riscos internas separadas (mesmo que idênticas) voltadas para as diferentes regiões e populações. Essa configuração facilitará a triagem e o gerenciamento de casos relevantes para suas funções e regiões para os participantes certos. Além disso, talvez você queira considerar a criação de processos e políticas para regiões onde investigadores e revisadores falam o mesmo idioma que os usuários para ajudar a simplificar o processo de escalonamento para alertas e casos de gerenciamento de riscos internos.

## <a name="plan-for-the-review-and-investigation-workflow"></a>Planejar o fluxo de trabalho de revisão e investigação

Selecione participantes dedicados para monitorar e analisar os alertas e ocorrências regularmente no centro de conformidade do [Microsoft 365.](https://compliance.microsoft.com/) Certifique-se de entender como você atribuirá diferentes participantes aos diferentes grupos de função disponíveis no gerenciamento de riscos insider.

Dependendo da estrutura da sua equipe de gerenciamento de conformidade, você tem opções para atribuir usuários a grupos de função específicos para gerenciar diferentes conjuntos de recursos de gerenciamento de riscos insider. Escolha entre essas opções de grupo de função ao configurar o gerenciamento de riscos insider:

| **Default management role assignments for this role** | **Permissões de função** |
| :---- | :---------------- |
| **Gerenciamento de riscos do Insider** | Use esse grupo de função para gerenciar o gerenciamento de riscos insider para sua organização em um único grupo. Ao adicionar todas as contas de usuário para administradores designados, analistas e investigadores, você pode configurar permissões de gerenciamento de riscos interno em um único grupo. Esse grupo de funções contém todas as funções de permissão de gerenciamento de risco interno. Essa configuração é a maneira mais fácil de começar rapidamente com o gerenciamento de riscos insider e é uma boa opção para organizações que não precisam de permissões separadas definidas para grupos separados de usuários.|
| **Administrador de Gerenciamento de Riscos Insider** | Use esse grupo de função para configurar inicialmente o gerenciamento de riscos insider e posteriormente segregar os administradores de risco interno em um grupo definido.  Os usuários desse grupo de função podem criar, ler, atualizar e excluir políticas de gerenciamento de riscos insider, configurações globais e atribuições de grupo de função. |
| **Analistas do Gerenciamento de Risco Interno** | Use esse grupo para atribuir permissões aos usuários que atuarão como analistas de caso de risco interno. Os usuários desse grupo de função podem acessar todos os alertas, ocorrências e modelos de avisos de gerenciamento de riscos insider. Eles não podem acessar o Explorador de Conteúdo de risco interno. |
| **Investigadores do Gerenciamento de Risco Interno** | Use esse grupo para atribuir permissões aos usuários que atuarão como investigadores de dados de risco interno. Os usuários desse grupo de função podem acessar todos os alertas, casos, modelos de avisos e o Explorador de Conteúdo para todos os casos. |

## <a name="understand-requirements-and-dependencies"></a>Compreender os requisitos e dependências

Dependendo de como você planeja implementar políticas de gerenciamento de riscos insider, você precisa ter as assinaturas de licenciamento adequadas do Microsoft 365 e entender e planejar alguns pré-requisitos de solução.

**Licenciamento:** O gerenciamento de riscos insider está disponível como parte de uma ampla seleção de assinaturas de licenciamento do Microsoft 365. Para obter detalhes, consulte [o artigo Sobre como começar a trabalhar com o gerenciamento de riscos insider.](insider-risk-management-configure.md#subscriptions-and-licensing)

Se você não tiver um plano existente do Microsoft 365 Enterprise E5 e quiser experimentar o gerenciamento de riscos [](https://www.microsoft.com/microsoft-365/enterprise) insider, adicione o [Microsoft 365](/office365/admin/try-or-buy-microsoft-365) à sua assinatura existente ou inscreva-se para uma avaliação do Microsoft 365 Enterprise E5.

**Requisitos de modelo de política:** Dependendo do modelo de política escolhido, há requisitos que você precisa entender e planejar antes de configurar o gerenciamento de riscos insider em sua organização:

- Ao usar **o** modelo roubo de dados de usuários, você deve configurar um conector de RH do Microsoft 365 para importar periodicamente informações de datas de término e de término para usuários em sua organização. Consulte o [artigo Importar dados com o](import-hr-data.md) conector de RH para obter orientação passo a passo para configurar o conector de RH do Microsoft 365 para sua organização.
- Ao usar modelos de vazamento **de** dados, você deve configurar pelo menos uma política de Prevenção contra Perda de Dados (DLP) para definir informações confidenciais em sua organização e receber alertas de risco interno para alertas de política de DLP de alta gravidade. Consulte o [artigo Criar, testar](create-test-tune-dlp-policy.md) e ajustar um artigo de política de DLP para obter orientação passo a passo sobre como configurar políticas DLP para sua organização.
- Ao usar **modelos de violação** de política de segurança, você deve habilitar o Microsoft Defender for Endpoint para integração de gerenciamento de riscos insider na Central de Segurança do Defender para importar alertas de violação de segurança. Consulte o [artigo Configurar recursos](/windows/security/threat-protection/microsoft-defender-atp/advanced-features) avançados do Microsoft Defender para obter orientação passo a passo para habilitar a integração do Defender para Ponto de Extremidade com o gerenciamento de riscos insider.
- Ao usar **modelos de** usuário nãogrunados, você deve configurar um conector de RH do Microsoft 365 para importar periodicamente informações de status de desempenho ou rebaixamento para usuários em sua organização. Consulte o [artigo Importar dados com o](import-hr-data.md) conector de RH para obter orientação passo a passo para configurar o conector de RH do Microsoft 365 para sua organização.

## <a name="test-with-a-small-group-of-users-in-a-production-environment"></a>Testar com um pequeno grupo de usuários em um ambiente de produção

Antes de ativar a solução amplamente em seu ambiente de produção, você pode considerar testar as políticas com um pequeno conjunto de usuários de produção durante a realização das avaliações legais, de conformidade e privacidade necessárias em sua organização. Avaliar o gerenciamento de risco interno em um ambiente de teste exigiria que você gerasse ações simuladas do usuário e outros sinais para criar alertas para triagem e casos para processamento. Essa abordagem não é prática para a maioria das organizações, portanto, é preferível testar o gerenciamento de riscos internos com um pequeno grupo de usuários em um ambiente de produção.

Mantenha o recurso de anonimato nas configurações de política habilitadas para anonimizar nomes de exibição de usuários no console de gerenciamento de riscos internos durante esse teste para manter a privacidade dentro da ferramenta. Essa configuração ajuda a proteger a privacidade dos usuários que têm as políticas de acordo e pode ajudar a promover a o objectivity na investigação de dados e revisões de análise para alertas de risco interno.

Se você não vir alertas imediatamente após a configuração de uma política de gerenciamento de riscos interno, isso pode significar que o limite mínimo de risco ainda não foi atendido. Uma boa maneira de verificar se a política está disparada e funcionando conforme o esperado é ver se o usuário está no escopo da política na **página Usuários.**

## <a name="resources-for-stakeholders"></a>Recursos para stakeholders

Compartilhe a documentação de gerenciamento de riscos interno com os participantes da sua organização incluídos no seu fluxo de trabalho de gerenciamento e correção:

- [Criar e gerenciar políticas de riscos internos](insider-risk-management-policies.md)
- [Investigar alertas de riscos internos](insider-risk-management-alerts.md)
- [Tomar medidas em casos de riscos internos](insider-risk-management-cases.md)
- [Analisar dados de caso com o Explorador de Conteúdo de risco interno](insider-risk-management-content-explorer.md)
- [Criar modelos de aviso de riscos internos](insider-risk-management-notices.md)

## <a name="ready-to-get-started"></a>Pronto para começar?

Pronto para configurar o gerenciamento de riscos insider para sua organização? Revise os seguintes artigos:

- [Começar a trabalhar com as configurações de gerenciamento de risco interno](insider-risk-management-settings.md) para definir as configurações de política global.
- [Comece a trabalhar com o gerenciamento de riscos insider](insider-risk-management-configure.md) para configurar pré-requisitos, criar políticas e começar a receber alertas.
