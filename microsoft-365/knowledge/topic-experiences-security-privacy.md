---
title: Tópico experiências de segurança e privacidade
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye, cjtan
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Saiba como planejar a experiência de tópicos de segurança e privacidade no Microsoft 365
ms.openlocfilehash: 7b88e5bbc8158ebd7dea65b2ecbf77085651b439
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/14/2020
ms.locfileid: "49668088"
---
# <a name="topic-experiences-security-and-privacy"></a>Tópico experiências de segurança e privacidade

A experiência do tópico usa recursos de segurança de conteúdo existentes no Microsoft 365, junto com os controles de rede de conhecimento, para controlar o conteúdo gerado pelo AI que será exibido aos usuários em sua organização. É a combinação das configurações de segurança do Microsoft 365 (permissões para sites, arquivos e pastas) e o tópico experiências de administração que determinam o que um usuário pode ver nos tópicos.

A configuração da rede de conhecimento não modifica qualquer controle de acesso existente no conteúdo da sua organização. Os usuários verão apenas o que eles já têm acesso.

Este artigo descreve como as experiências de tópicos funcionam de uma perspectiva de segurança e as opções que os administradores de conhecimento e os gerentes de conhecimento precisam controlar a visibilidade do tópico. Leia este artigo como parte do [planejamento de experiências de tópico](plan-topic-experiences.md).

Você deve estar familiarizado com [experiências de tópicos](knowledge-management-overview.md), o [centro de tópicos](topic-center-overview.md)e como [trabalhar com tópicos no centro](work-with-topics.md) de tópicos antes de ler este artigo.

## <a name="what-users-can-see-in-topics"></a>O que os usuários podem ver nos tópicos

Para ver os tópicos, um usuário deve:

- Tem uma licença de experiência do tópico
- Ser um [Visualizador de tópicos](topic-experiences-knowledge-rules.md#change-who-can-see-topics-in-your-organization), [Contribuidor ou gerente de conhecimento](topic-experiences-user-permissions.md)

Essas duas coisas permitem que os usuários exibam o acesso ao centro de tópicos e permitem que eles vejam destaques e cartões de tópico.

Os colaboradores de tópico também têm permissões [criar e editar](topic-experiences-user-permissions.md#change-who-has permissions-to-update-topic-details) para tópicos, e os gerentes de conhecimento podem confirmar ou remover tópicos.

Quando um tópico é descoberto pela primeira vez, os gerentes de conhecimento podem vê-lo no centro de tópicos. Dependendo da integridade e da relevância do tópico, os visualizadores de tópico podem ou não ver o tópico apresentado nos cartões de tópico.

Os tópicos podem conter informações geradas pelo AI e informações adicionadas ou editadas por colaboradores de tópico ou gerentes de conhecimento.

- As informações de um tópico que foram adicionadas pelo AI são visíveis apenas para pessoas que têm acesso ao conteúdo de origem.
- O texto que foi adicionado ou editado manualmente por um tópico Contribuidor ou gerente de conhecimento é visível para todas as pessoas que podem ver o tópico.

Os visualizadores de tópicos e colaboradores podem ver a lista de tópicos confirmados e publicados no centro de tópicos, mas os detalhes do tópico que uma determinada pessoa pode ver dependem das permissões que eles têm para o material de origem e sobre se o tópico foi editado manualmente.

A tabela a seguir descreve quais usuários – visualizadores de tópicos, colaboradores e gerentes de conhecimento-podem ver em um determinado tópico com base em suas permissões.

|Item de tópico|O que os usuários podem ver|
|:---------|:------------------|
|Nome do tópico|Os usuários podem ver o nome do tópico de todos os tópicos no centro de tópicos. Alguns tópicos podem não estar visíveis se tiverem uma relevância baixa para o usuário.|
|Descrição do tópico|As descrições geradas pelo AI são visíveis apenas para os usuários que têm permissões para o conteúdo de origem. Descrições inseridas ou editadas manualmente são visíveis para todos os usuários.|
|Pessoas|Pessoas fixas estão visíveis para todos os usuários. As pessoas sugeridas são visíveis apenas para os usuários que têm permissões para o conteúdo de origem.|
|Arquivos|Os arquivos são visíveis apenas para os usuários que têm permissões para o conteúdo de origem.|
|Páginas|As páginas são visíveis apenas para os usuários que têm permissões para o conteúdo de origem.|
|Sites|Os sites são visíveis apenas para os usuários que têm permissões para o conteúdo de origem.|

## <a name="best-practices"></a>Práticas recomendadas

A experiência do tópico apresenta informações aos usuários com base em suas permissões existentes para o conteúdo. A Microsoft 365 oferece várias maneiras de garantir que o conteúdo confidencial seja restrito aos usuários apropriados. Além da equipe ou das permissões de site padrão, você pode usar [Rótulos de confidencialidade](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) ou [prevenção de perda de dados](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies) para restringir o acesso a revisões de conteúdo e de [acesso](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview) para rever periodicamente o acesso de usuários a informações confidenciais.

Recomendamos que você use essas ferramentas para garantir que as permissões de conteúdo sejam definidas apropriadamente dentro da sua organização. As experiências de tópicos podem fornecer informações úteis e apropriadas para seus usuários.

Se houver tópicos que você deseja excluir inteiramente das experiências de tópico, você também pode:

- [Excluir sites confidenciais do SharePoint da descoberta de tópicos](topic-experiences-discovery.md#select-sharepoint-topic-sources). O conteúdo desses sites não aparecerá em experiências de tópico.

- [Exclua os tópicos por nome](topic-experiences-discovery.md#exclude-topics-by-name). Os tópicos explicitamente excluídos não aparecerão em experiências de tópico.

- Os gerentes de conhecimento removem tópicos no centro de tópicos.

Além disso, recomendamos estas práticas recomendadas:

- Recrutar gerentes de conhecimento de diferentes áreas da sua organização. Ter gerentes de conhecimento com uma variedade de especialização e acesso ao conteúdo subjacente usado pelo AI-pode ajudá-lo a obter o conhecimento mais útil para seus usuários e remover informações confidenciais, se encontrado.

- Configurar um fluxo de trabalho para solicitar alterações. Os gerentes de conhecimento ou os proprietários do site devem ter um processo pelo qual eles podem solicitar a exclusão de tópicos ou sites à medida que novos projetos são iniciados na sua organização ou quando eles encontram conteúdo com configurações de permissões inadequadas.

- Esteja ciente da audiência e a confidencialidade das informações ao criar descrições de tópicos. Essas descrições podem ser visíveis para os usuários que não têm permissões para o conteúdo de origem do tópico.

Embora você possa alterar as permissões em páginas de tópicos individuais para restringir o acesso a um grupo específico de usuários, não recomendamos essa abordagem devido ao alto grau de esforço administrativo necessário.

## <a name="see-also"></a>Também consulte

[Configurar equipes com três camadas de proteção](../solutions/configure-teams-three-tiers-protection.md)

[Planejar experiências de tópico](plan-topic-experiences.md)

[Configurar experiências de tópico](set-up-topic-experiences.md)
