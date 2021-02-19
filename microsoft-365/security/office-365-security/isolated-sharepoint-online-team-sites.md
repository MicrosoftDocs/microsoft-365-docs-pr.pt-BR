---
title: Sites de equipe isolados do SharePoint Online
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: overview
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 71250a04-fd2d-4c3c-a32b-b8a838b19a54
description: Saiba mais sobre os sites de equipe isolados do SharePoint Online, incluindo os usos, os requisitos e os recursos com os quais podem ser usados.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 056c6f2a463d38dd27b26d484995280dddedf436
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286580"
---
# <a name="isolated-sharepoint-online-team-sites"></a>Sites de equipe isolados do SharePoint Online

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Microsoft Defender para Office 365 Plano 1](office-365-atp.md)
- SharePoint Online 

 **Resumo:** conheça as utilizações dos sites de equipe do SharePoint Online isolados.

Os sites de equipe do Microsoft Office SharePoint Online são uma maneira fácil de criar rapidamente um espaço para colaboração. Os usuários podem trabalhar juntos em notas, documentos, artigos, um calendário e outros recursos no Microsoft Office 365. Os sites de equipe do Microsoft Office SharePoint Online são baseados em um grupo do Microsoft 365 e têm um modelo de administração simplificado para permitir a colaboração aberta com um conjunto privado de membros do grupo ou toda a organização. Um site de equipe do Microsoft Office SharePoint Online padrão permite que os membros do grupo Microsoft 365 convidem outros usuários e controlem as configurações de permissões.

No entanto, às vezes você precisará que o acesso ao site seja controlado por associações de grupo e níveis de permissão do Microsoft Office SharePoint Online gerenciados por administradores do Microsoft Office SharePoint Online. Chamamos isso de site isolado, que é isolado para o conjunto de usuários que estão colaborando, visualizando o seu conteúdo ou administrando o site. Talvez você precise de um site isolado para o seguinte:

- Um projeto secreto em sua organização.

- O local da propriedade intelectual altamente confidencial ou valiosa para sua organização.

- Os recursos de uma ação judicial iniciada por sua organização ou à qual a empresa está sendo submetida.

- Para compartilhar uma assinatura do Microsoft 365 entre várias organizações que possuem alguma sobreposição, mas, para a maioria delas, existem como entidades de negócios separadas.

Veja os requisitos de um site isolado:

- Apenas os administradores do SharePoint Online podem realizar a administração de sites, o que inclui a associação ao grupo para acessar o site e a configuração de permissões personalizadas.

- Os membros do site não podem convidar outros membros para o site de equipe.

- Os usuários que não são membros do site isolado não podem solicitar acesso ao site e verão uma página da Web de acesso negado ao tentar acessar qualquer URL associada ao site.

A desvantagem de exigir controle de acesso centralizado e permissões personalizadas pelos administradores do Microsoft Office SharePoint Online é que o site manterá-se isolado ao longo do tempo. Por exemplo, os membros atuais não poderão, intencionalmente ou acidentalmente, convidar ou configurar permissões personalizadas para outros usuários na assinatura do Microsoft 365 que não sejam membros do site.

Um site isolado pode ser usado com outros recursos, como:

- Gerenciamento de Direitos de Informação para garantir que os recursos do site permaneçam criptografados, mesmo que eles sejam baixados localmente e carregados em outro site que esteja disponível para toda a organização.

- Prevenção contra a perda de dados para evitar que os usuários enviem os recursos do site, como arquivos, por email.

## <a name="next-steps"></a>Próximas etapas

Para experimentar um site de equipe do SharePoint Online isolado em uma assinatura de avaliação, confira as instruções passo a passo no [Site de equipe do SharePoint Online isolado no seu ambiente de desenvolvimento/teste](isolated-sharepoint-online-team-site-dev-test-environment.md).

Quando estiver pronto para implantar um site de equipe do SharePoint Online isolado na produção, confira as considerações de design passo a passo no [Projetar um site de equipe do SharePoint Online isolado](design-an-isolated-sharepoint-online-team-site.md).

## <a name="related-topics"></a>Tópicos relacionados

[Projetar um site de equipe do SharePoint Online isolado](design-an-isolated-sharepoint-online-team-site.md)

[Gerenciar um site de equipe do SharePoint Online isolado](manage-an-isolated-sharepoint-online-team-site.md)

[Implantar um site de equipe do SharePoint Online isolado](deploy-an-isolated-sharepoint-online-team-site.md)
