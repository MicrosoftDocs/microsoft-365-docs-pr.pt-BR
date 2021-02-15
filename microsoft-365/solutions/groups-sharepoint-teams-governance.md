---
title: Configurações de interações entre Grupos do Microsoft 365, Teams e SharePoint
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Saiba mais sobre as interações de configurações entre grupos do Microsoft 365, Teams e SharePoint
ms.openlocfilehash: 23ef7a316417109ae51c221f1a25524dea3abeca
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613661"
---
# <a name="settings-interactions-between-microsoft-365-groups-teams-and-sharepoint"></a>Configurações de interações entre Grupos do Microsoft 365, Teams e SharePoint

Algumas configurações dos Grupos do Microsoft 365, do Microsoft Teams e do SharePoint no Microsoft 365, particularmente relacionadas ao compartilhamento e à criação de grupos/equipes e sites do SharePoint, se sobrepõem entre si. Este artigo fornece descrições dessas interações e práticas recomendadas sobre como trabalhar com essas configurações.

![Diagrama de Venn dos recursos do SharePoint, Teams e grupos](../media/teams-groups-sharepoint-venn.png)

## <a name="the-effects-of-sharepoint-settings-on-groups-and-teams"></a>Os efeitos das configurações do SharePoint em grupos e equipes

|Configuração do SharePoint|Descrição|Efeito nos grupos do Microsoft 365 e no Teams|Recomendação|
|:-----------------|:----------|:---------------------------------------|:-------------|
|Compartilhamento externo para organização e site|Determina se sites, arquivos e pastas podem ser compartilhados com pessoas de fora da organização.|Se as configurações do SharePoint, grupos e Equipes não corresponderem, os convidados da equipe poderão ser impedidos de acessar o site, ou poderá ocorrer um acesso externo inesperado.|Ao alterar as configurações de compartilhamento, verifique as configurações de Grupos, as configurações do Teams e as configurações de site do SharePoint para sites de equipe conectados ao grupo.<br><br> Ver [Colaborar com convidados em uma equipe](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)|
|Domínio permitir/bloquear|Permite ou impede que o conteúdo seja compartilhado com domínios especificados.|Os grupos e o Teams não reconhecem as listas de bloqueio ou de autorização do SharePoint. Os usuários de domínios não permitidos no SharePoint podem obter acesso a sites ou conteúdo do SharePoint por meio de uma equipe.|Gerenciar listas de bloqueio/autorização de domínio para o Azure AD e o SharePoint juntos. Crie um processo de governança em toda a organização para permitir e bloquear domínios.<br><br>Ver [configurações de domínio do SharePoint](https://docs.microsoft.com/sharepoint/restricted-domains-sharing) e configurações de domínio [do Azure AD](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)|
|Permitir que somente os usuários de grupos específicos de segurança compartilhem externamente|Especifica grupos de segurança que podem compartilhar sites, pastas e arquivos do SharePoint externamente.|Essa configuração não impede que os proprietários de equipe compartilhem equipes externamente. Os convidados da equipe têm acesso ao site do SharePoint associado.||
|Configurações de compartilhamento de site do SharePoint|Determina quem pode compartilhar o site diretamente fora da associação da equipe. Isso é configurado pela equipe ou pelo proprietário do site.|Essa configuração não afeta a equipe diretamente, mas pode permitir que os usuários sejam adicionados a um site e não tenham acesso à própria equipe ou a outros recursos do Teams|Considere usar essa configuração para limitar o compartilhamento do site diretamente e gerenciar o acesso ao site por meio da equipe.|
|Permitir que os usuários criem sites na página inicial do SharePoint e no OneDrive|Especifica se os usuários podem criar novos sites do SharePoint.|Se essa configuração estiver desligada, os usuários ainda poderão criar sites de equipe conectados ao grupo criando uma equipe.||

## <a name="the-effects-of-groups-settings-on-teams"></a>Os efeitos das configurações de grupos em equipes

|Configuração de grupos do Microsoft 365|Descrição|Efeito no Teams|Recomendação|
|:---------------------------|:----------|:--------------|:-------------|
|Políticas de nomenclatura|Especifica prefixos e sufixos de nome de grupo e palavras bloqueadas para criação de grupo|As políticas são impostas para os usuários que criam equipes.||
|Acesso de convidados do grupo|Especifica se pessoas de fora da organização podem ser adicionadas a grupos.|Se os grupos ou as configurações de compartilhamento de convidados do Teams não estão compartilhamentos, a equipe não pode ser compartilhada com convidados.|Ao alterar as configurações de compartilhamento de convidados, verifique as configurações do Teams, Grupos e do site do SharePoint associado à equipe.<br><br> Ver [Colaborar com convidados em uma equipe](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)|
|Criação de grupo por grupo de segurança|Os grupos só podem ser criados por membros de um grupo de segurança específico.|Os usuários que não são membros do grupo de segurança não poderão criar uma equipe.|Certifique-se de que seu processo de solicitação de um grupo inclui instruções para solicitar uma equipe ou um site do SharePoint.|
|Política de expiração de grupo|Especifica um período após o qual os grupos que não são usados ativamente serão automaticamente excluídos.|Quando o grupo é excluído, a equipe e o site do SharePoint associado também são excluídos. O conteúdo protegido por políticas de retenção é mantido.|Use políticas de expiração para evitar o redesesso de equipes, grupos e sites não usado.|

## <a name="related-topics"></a>Tópicos relacionados

[Planejamento de governança de colaboração passo a passo](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Criar seu plano de governança de colaboração](collaboration-governance-first.md)

[Colaborar com pessoas de fora da sua organização](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization)

[Gerenciar a criação de sites no SharePoint](https://docs.microsoft.com/sharepoint/manage-site-creation)
