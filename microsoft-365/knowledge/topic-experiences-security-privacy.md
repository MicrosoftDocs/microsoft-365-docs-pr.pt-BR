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
ms.openlocfilehash: be5be01bce117a80bd95ee268c193889eccea67f
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2021
ms.locfileid: "50107787"
---
# <a name="microsoft-viva-topics-security-and-privacy"></a>Segurança e privacidade dos Tópicos do Microsoft Viva

Os tópicos usam recursos de segurança de conteúdo existentes no Microsoft 365, juntamente com controles administrativos, para controlar qual conteúdo gerado por IA é exibido aos usuários em sua organização. É a combinação das configurações de segurança do Microsoft 365 (permissões para sites, arquivos e pastas) e configurações de administração de Tópicos que determinam o que um determinado usuário pode ver nos tópicos.

A configuração de Tópicos não modifica os controles de acesso existentes no conteúdo da sua organização. Os usuários verão apenas o que já têm acesso.

Este artigo descreve como os tópicos funcionam de uma perspectiva de segurança e as opções que os administradores de conhecimento e gerentes de conhecimento têm para controlar a visibilidade do tópico. Leia este artigo como parte do [seu planejamento para tópicos.](plan-topic-experiences.md)

Você deve estar familiarizado com o [](topic-center-overview.md)que é [Topics](topic-experiences-overview.md), o centro de tópicos e como trabalhar com tópicos no centro de [tópicos](manage-topics.md) antes de ler este artigo.

## <a name="what-users-can-see-in-topics"></a>O que os usuários podem ver nos tópicos

Para ver tópicos, um usuário deve:

- Ter uma licença de Tópicos do Viva
- Ser um [visualizador de tópicos,](topic-experiences-knowledge-rules.md#change-who-can-see-topics-in-your-organization) [colaborador ou gerente de conhecimento](topic-experiences-user-permissions.md)

Essas duas coisas dão aos usuários acesso de exibição ao centro de tópicos e permitem que eles vejam destaques e cartões de tópico.

Os colaboradores de tópicos também [têm permissões](topic-experiences-user-permissions.md) de criação e edição para tópicos, e os gerentes de conhecimento podem confirmar ou remover tópicos.

Quando um tópico é descoberto pela primeira vez, os gerentes de conhecimento podem vê-lo no centro de tópicos. Dependendo da totalidade e relevância do tópico, os visitantes do tópico podem ou não ver o tópico apresentado nos cartões de tópico.

Os tópicos podem conter informações geradas por IA e informações adicionadas ou editadas por colaboradores de tópicos ou gerentes de conhecimento.

- As informações em um tópico que foi adicionado pela ia só são visíveis para as pessoas que têm acesso ao conteúdo de origem.
- O texto adicionado ou editado manualmente por um colaborador de tópico ou gerente de conhecimento fica visível para todos que podem ver o tópico.

Os visualizadores e colaboradores de tópicos podem ver a lista de tópicos confirmados e publicados no centro de tópicos, mas os detalhes do tópico que uma determinada pessoa pode ver dependem das permissões que ela tem para o material de origem e se o tópico foi editado manualmente.

A tabela a seguir descreve o que os usuários ( visualizadores de tópicos, colaboradores e gerentes de conhecimento ) podem ver em um determinado tópico com base em suas permissões.

|Item de tópico|O que os usuários podem ver|
|:---------|:------------------|
|Nome do tópico|Os usuários podem ver o nome do tópico de todos os tópicos no centro de tópicos. Alguns tópicos podem não estar visíveis se eles têm uma baixa relevância para o usuário.|
|Descrição do tópico|As descrições geradas por IA são visíveis apenas para usuários que têm permissões para o conteúdo de origem. As descrições inseridas ou editadas manualmente ficam visíveis para todos os usuários.|
|Pessoas|As pessoas fixadas ficam visíveis para todos os usuários. As pessoas sugeridas só ficam visíveis para os usuários que têm permissões para o conteúdo de origem.|
|Arquivos|Os arquivos só ficam visíveis para os usuários que têm permissões para o conteúdo de origem.|
|Páginas|As páginas só ficam visíveis para os usuários que têm permissões para o conteúdo de origem.|
|Sites|Os sites ficam visíveis apenas para os usuários que têm permissões para o conteúdo de origem.|

## <a name="best-practices"></a>Práticas recomendadas

Os tópicos apresentam informações aos usuários com base em suas permissões existentes para o conteúdo. O Microsoft 365 oferece várias maneiras de garantir que o conteúdo sensível seja restrito aos usuários apropriados. Além das permissões padrão de equipe [](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) ou site, você pode usar rótulos de sensibilidade ou prevenção contra perda de dados para restringir o acesso ao conteúdo e acessar revisões para revisar periodicamente o acesso do usuário a informações confidenciais. [](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies) [](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)

Recomendamos que você use essas ferramentas para garantir que suas permissões de conteúdo sejam definidas adequadamente dentro da sua organização. As experiências de tópico podem fornecer informações úteis e apropriadas aos seus usuários.

Se houver tópicos que você deseja excluir inteiramente das experiências de tópico, você também pode:

- [Exclua sites confidenciais do SharePoint da descoberta de tópico.](topic-experiences-discovery.md#select-sharepoint-topic-sources) O conteúdo desses sites não será exibido nas experiências de tópico.

- [Excluir tópicos por nome.](topic-experiences-discovery.md#exclude-topics-by-name) Os tópicos explicitamente excluídos não aparecerão nas experiências de tópico.

- Fazer com que os gerentes de conhecimento removam os tópicos no centro de tópicos.

Além disso, recomendamos estas práticas recomendadas:

- Recrutar gerentes de conhecimento de diferentes áreas da sua organização. Ter gerentes de conhecimento com uma variedade de experiência e acesso ao conteúdo subjacente usado pela IA pode ajudá-lo a obter o conhecimento mais útil para seus usuários e remover informações confidenciais, se encontradas.

- Configurar um fluxo de trabalho para solicitar alterações. Gerentes de conhecimento ou proprietários de equipe ou site devem ter um processo pelo qual podem solicitar a exclusão de tópicos ou sites à medida que novos projetos são iniciados em sua organização ou se encontram conteúdo com configurações de permissões inadequadas.

- Esteja ciente da audiência e da sensibilidade das informações ao criar descrições de tópicos. Essas descrições podem estar visíveis para os usuários que não têm permissões para o conteúdo de origem do tópico.

Embora você possa alterar as permissões em páginas de tópico individuais para restringir o acesso a um grupo específico de usuários, não recomendamos essa abordagem devido ao alto grau de esforço administrativo necessário.

## <a name="see-also"></a>Confira também

[Configure equipes com três níveis de proteção](../solutions/configure-teams-three-tiers-protection.md)

[Planejar Experiências de tópico](plan-topic-experiences.md)

[Configurar Experiências de tópico](set-up-topic-experiences.md)
