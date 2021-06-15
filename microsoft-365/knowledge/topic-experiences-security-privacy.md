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
ms.openlocfilehash: b8c82b1914df739ea9086a4ce1585733a7b6d854
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925486"
---
# <a name="microsoft-viva-topics-security-and-privacy"></a>Segurança e privacidade dos Tópicos do Microsoft Viva

Os tópicos usam recursos de segurança de conteúdo existentes no Microsoft 365, juntamente com controles administrativos, para controlar o conteúdo gerado pela IA aos usuários em sua organização. É a combinação de Microsoft 365 de segurança (permissões para sites, arquivos e pastas) e configurações de administrador de Tópicos que determinam o que um determinado usuário pode ver nos tópicos.

Configurar Tópicos não modifica nenhum controle de acesso existente sobre o conteúdo da sua organização. Os usuários verão apenas o conteúdo ao qual têm acesso.

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

- As informações de um tópico adicionado pela AI só são visíveis para as pessoas que têm acesso ao conteúdo da origem.
- O texto adicionado manualmente ou editado por um colaborador de tópicos ou gerente de conhecimento fica visível para todos os que podem ver o tópico.

Os visualizadores de tópicos e colaboradores podem ver a lista de tópicos confirmados e publicados no centro de tópicos, mas os detalhes do tópico que uma determinada pessoa pode ver dependem das permissões que elas têm para o material de origem e se o tópico foi editado manualmente.

A tabela a seguir descreve o que os usuários - visualizadores de tópicos, colaboradores e gerentes de conhecimento - podem ver em um determinado tópico com base em suas permissões.

|Item de tópico|O que os usuários podem ver|
|:---------|:------------------|
|Nome do tópico|Os usuários podem ver o nome do tópico de tópicos no centro de tópicos. Alguns tópicos podem não estar visíveis se os usuários não têm permissões para o conteúdo de origem ou têm baixa relevância para o usuário.|
|Descrição do tópico|As descrições geradas por AI são visíveis apenas para os usuários que têm permissões para o conteúdo de origem. As descrições inseridas ou editadas manualmente ficam visíveis para todos os usuários.|
|Pessoas|As pessoas fixadas ficam visíveis para todos os usuários. As pessoas sugeridas só ficam visíveis para os usuários que têm permissões para o conteúdo de origem.|
|Arquivos|Os arquivos só ficam visíveis para os usuários que têm permissões para o conteúdo de origem.|
|Páginas|As páginas só ficam visíveis para os usuários que têm permissões para o conteúdo de origem.|
|Sites|Os sites só ficam visíveis para os usuários que têm permissões para o conteúdo de origem.|

## <a name="users-personal-and-private-data"></a>Dados pessoais e privados dos usuários

Os Tópicos do Viva só descobrirão tópicos no SharePoint que você especificar. O armazenamento pessoal dos usuários, como emails pessoais ou OneDrive não está incluído.

## <a name="best-practices"></a>Práticas recomendadas

Os tópicos apresentam informações aos usuários com base em suas permissões existentes para o conteúdo. Microsoft 365 fornece várias maneiras de garantir que o conteúdo confidenciais seja restrito aos usuários apropriados. Além das permissões padrão de equipe [](../compliance/sensitivity-labels.md) ou site, você pode usar rótulos de sensibilidade ou prevenção contra perda de dados para restringir o acesso ao conteúdo e acessar análises para revisar periodicamente o acesso do usuário a informações confidenciais. [](../compliance/dlp-learn-about-dlp.md) [](/azure/active-directory/governance/access-reviews-overview)

Recomendamos que você use essas ferramentas para garantir que suas permissões de conteúdo sejam definidas adequadamente dentro da sua organização. As experiências de tópico podem, então, fornecer informações úteis e apropriadas aos seus usuários.

Se houver tópicos que você deseja excluir inteiramente das experiências de tópicos, você também pode:

- [Excluir sites SharePoint confidenciais da descoberta de tópicos.](topic-experiences-discovery.md#select-sharepoint-topic-sources) O conteúdo desses sites não aparecerá nas experiências de tópico.

- [Excluir tópicos pelo nome](topic-experiences-discovery.md#exclude-topics-by-name). Os tópicos explicitamente excluídos não aparecerão nas experiências de tópicos.

- Fazer com que os gerentes de conhecimento removam os tópicos na central de tópicos.

Além disso, recomendamos estas práticas recomendadas:

- Recrutar gerentes de conhecimento de diferentes áreas da sua organização. Ter gerentes de conhecimento com uma variedade de experiência - e acesso ao conteúdo subjacente usado pela AI - pode ajudá-lo a recuperar o conhecimento mais útil para seus usuários e remover informações confidenciais se encontrado.

- Configure um fluxo de trabalho para solicitar alterações. Gerentes de conhecimento ou proprietários de equipe ou site devem ter um processo pelo qual eles podem solicitar a exclusão de tópicos ou sites à medida que novos projetos são iniciados em sua organização ou se eles encontram conteúdo com configurações de permissões inadequadas.

- Esteja ciente do público e da confidencialidade das informações ao criar descrições de tópicos. Essas descrições podem ser visíveis para usuários que não têm permissão para acessar o conteúdo de origem do tópico.

Embora você possa alterar as permissões em páginas de tópicos individuais para restringir o acesso a um grupo específico de usuários, não recomendamos essa abordagem devido ao alto grau de esforço administrativo necessário.

## <a name="see-also"></a>Confira também

[Configure o Teams com três camadas de proteção](../solutions/configure-teams-three-tiers-protection.md)

[Planejar Experiências de tópico](plan-topic-experiences.md)

[Configurar Experiências de tópico](set-up-topic-experiences.md)
