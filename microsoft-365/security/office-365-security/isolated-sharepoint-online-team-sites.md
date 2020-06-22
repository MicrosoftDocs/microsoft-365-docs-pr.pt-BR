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
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 71250a04-fd2d-4c3c-a32b-b8a838b19a54
description: Saiba mais sobre os sites de equipe isolados do SharePoint Online, incluindo os usos, os requisitos e os recursos com os quais podem ser usados.
ms.openlocfilehash: 0646ffc37256702844b550fd1beb841944b2d509
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819528"
---
# <a name="isolated-sharepoint-online-team-sites"></a>Sites de equipe isolados do SharePoint Online

 **Resumo:** conheça as utilizações dos sites de equipe do SharePoint Online isolados.
  
SharePoint Online team sites are an easy way to quickly create a space for collaboration of notes, documents, articles, a calendar, and other resources in Microsoft Office 365. SharePoint Online team sites are based on a Microsoft 365 group and have a simplified administration model to allow open collaboration with a private set of group members or the entire organization. A default SharePoint Online team site allows members of the Microsoft 365 group to invite other users and control permissions settings.
  
However, in some cases, you want to create a SharePoint Online team site for collaboration where the permissions of that site are more tightly controlled through group membership and SharePoint Online permission levels, which are only managed by SharePoint administrators. We call this an isolated site, which is isolated to the set of users that are either collaborating, viewing its contents, or administering the site. You might need an isolated site for the following:
  
- Um projeto secreto em sua organização.
    
- O local da propriedade intelectual altamente confidencial ou valiosa para sua organização.
    
- Os recursos de uma ação judicial iniciada por sua organização ou à qual a empresa está sendo submetida.
    
- Para compartilhar uma assinatura do Microsoft 365 entre várias organizações que possuem alguma sobreposição, mas, para a maioria delas, existem como entidades de negócios separadas.
    
Veja os requisitos de um site isolado:
  
- Apenas os administradores do SharePoint Online podem realizar a administração de sites, o que inclui a associação ao grupo para acessar o site e a configuração de permissões personalizadas.
    
- Os membros do site não podem convidar outros membros para o site de equipe.
    
- Users who are not members of the isolated site cannot request access to the site. They will receive an access denied web page when they attempt to access any URL associated with the site.
    
The tradeoff of requiring centralized access control and custom permissions by SharePoint Online administrators is that the site remains isolated over time. For example, current members cannot, either intentionally or accidentally, invite or configure custom permissions for other users within the Microsoft 365 subscription who should not be members of the site.
  
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


