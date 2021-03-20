---
title: Segurança e privacidade dos Tópicos do Microsoft Viva
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye, cjtan
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: Saiba como planejar a segurança e a privacidade dos Tópicos do Microsoft Viva
ms.openlocfilehash: 9ac7ea085be115ef06244422713099c01ec50a36
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917339"
---
# <a name="microsoft-viva-topics-security-and-privacy"></a>Segurança e privacidade dos Tópicos do Microsoft Viva

Os tópicos usam recursos de segurança de conteúdo existentes no Microsoft 365, juntamente com controles administrativos, para controlar qual conteúdo gerado por IA é mostrado aos usuários em sua organização. É a combinação de configurações de segurança do Microsoft 365 (permissões para sites, arquivos e pastas) e configurações de administrador de Tópicos que determinam o que um determinado usuário pode ver nos tópicos.

Configurar Tópicos não modifica controles de acesso existentes em conteúdo em sua organização. Os usuários só verão ao que já têm acesso.

Este artigo descreve como os Tópicos funcionam de uma perspectiva de segurança e as opções que os administradores de conhecimento e gerentes de conhecimento têm para controlar a visibilidade do tópico. Leia este artigo como parte do [seu planejamento para Tópicos.](plan-topic-experiences.md)

Você deve estar familiarizado com o que é [Tópicos](topic-experiences-overview.md), o centro de tópicos [e](topic-center-overview.md)como trabalhar com tópicos no centro de [tópicos](manage-topics.md) antes de ler este artigo.

## <a name="what-users-can-see-in-topics"></a>O que os usuários podem ver em tópicos

Para ver tópicos, um usuário deve:

- Ter uma licença de Tópicos do Viva
- Ser um [visualizador de tópicos,](topic-experiences-knowledge-rules.md#change-who-can-see-topics-in-your-organization) [colaborador ou gerente de conhecimento](topic-experiences-user-permissions.md)

Essas duas coisas dão aos usuários acesso ao centro de tópicos e permitem que eles vejam destaques e cartões de tópicos.

Os colaboradores de tópicos também têm [permissões de](topic-experiences-user-permissions.md) criação e edição para tópicos, e os gerentes de conhecimento podem confirmar ou remover tópicos.

Quando um tópico é descoberto pela primeira vez, os gerentes de conhecimento podem vê-lo no centro de tópicos. Dependendo da totalidade e relevância do tópico, os visualizadores de tópicos podem ou não ver o tópico apresentado nos cartões de tópicos.

Os tópicos podem conter informações geradas pela IA e informações adicionadas ou editadas por colaboradores de tópicos ou gerentes de conhecimento.

- As informações em um tópico adicionado pela AI só são visíveis para as pessoas que têm acesso ao conteúdo de origem.
- O texto adicionado manualmente ou editado por um colaborador de tópicos ou gerente de conhecimento fica visível para todos os que podem ver o tópico.

Os visualizadores de tópicos e colaboradores podem ver a lista de tópicos confirmados e publicados no centro de tópicos, mas os detalhes do tópico que uma determinada pessoa pode ver dependem das permissões que elas têm para o material de origem e se o tópico foi editado manualmente.

A tabela a seguir descreve o que os usuários - visualizadores de tópicos, colaboradores e gerentes de conhecimento - podem ver em um determinado tópico com base em suas permissões.

|Item de tópico|O que os usuários podem ver|
|:---------|:------------------|
|Nome do tópico|Os usuários podem ver o nome do tópico de todos os tópicos no centro de tópicos. Alguns tópicos podem não estar visíveis se eles têm baixa relevância para o usuário.|
|Descrição do tópico|As descrições geradas por IA ficam visíveis apenas para usuários que têm permissões para o conteúdo de origem. As descrições inseridas ou editadas manualmente ficam visíveis para todos os usuários.|
|Pessoas|As pessoas fixadas ficam visíveis para todos os usuários. As pessoas sugeridas só ficam visíveis para usuários que têm permissões para o conteúdo de origem.|
|Arquivos|Os arquivos só ficam visíveis para os usuários que têm permissões para o conteúdo de origem.|
|Páginas|As páginas só ficam visíveis para os usuários que têm permissões para o conteúdo de origem.|
|Sites|Os sites só ficam visíveis para os usuários que têm permissões para o conteúdo de origem.|

## <a name="best-practices"></a>Práticas recomendadas

Os tópicos apresentam informações aos usuários com base em suas permissões existentes para o conteúdo. O Microsoft 365 fornece várias maneiras de garantir que o conteúdo confidenciais seja restrito aos usuários apropriados. Além das permissões padrão de equipe [](../compliance/sensitivity-labels.md) ou site, você pode usar rótulos de sensibilidade ou prevenção contra perda de dados para restringir o acesso ao conteúdo e acessar análises para revisar periodicamente o acesso do usuário a informações confidenciais. [](../compliance/data-loss-prevention-policies.md) [](/azure/active-directory/governance/access-reviews-overview)

Recomendamos que você use essas ferramentas para garantir que suas permissões de conteúdo sejam definidas adequadamente dentro da sua organização. As experiências de tópicos podem fornecer informações úteis e apropriadas aos usuários.

Se houver tópicos que você deseja excluir inteiramente das experiências de tópicos, você também pode:

- [Excluir sites confidenciais do SharePoint da descoberta de tópicos.](topic-experiences-discovery.md#select-sharepoint-topic-sources) O conteúdo nesses sites não aparecerá em experiências de tópicos.

- [Excluir tópicos pelo nome](topic-experiences-discovery.md#exclude-topics-by-name). Os tópicos explicitamente excluídos não serão exibidos em experiências de tópicos.

- Fazer com que os gerentes de conhecimento removam os tópicos na central de tópicos.

Além disso, recomendamos estas práticas recomendadas:

- Recrutar gerentes de conhecimento de diferentes áreas da sua organização. Ter gerentes de conhecimento com uma variedade de experiência - e acesso ao conteúdo subjacente usado pela AI - pode ajudá-lo a recuperar o conhecimento mais útil para seus usuários e remover informações confidenciais se encontrado.

- Configurar um fluxo de trabalho para solicitar alterações. Gerentes de conhecimento ou proprietários de equipe ou site devem ter um processo pelo qual eles podem solicitar a exclusão de tópicos ou sites à medida que novos projetos são iniciados em sua organização ou se eles encontram conteúdo com configurações de permissões inadequadas.

- Esteja ciente da audiência e da sensibilidade das informações ao criar descrições de tópicos. Essas descrições podem estar visíveis para os usuários que não têm permissões para o conteúdo de origem do tópico.

Embora você possa alterar as permissões em páginas de tópicos individuais para restringir o acesso a um grupo específico de usuários, não recomendamos essa abordagem devido ao alto grau de esforço administrativo necessário.

## <a name="see-also"></a>Confira também

[Configure equipes com três níveis de proteção](../solutions/configure-teams-three-tiers-protection.md)

[Planejar Experiências de tópico](plan-topic-experiences.md)

[Configurar Experiências de tópico](set-up-topic-experiences.md)