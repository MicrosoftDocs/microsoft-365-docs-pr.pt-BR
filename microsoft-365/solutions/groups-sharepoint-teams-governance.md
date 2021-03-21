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
description: Saiba mais sobre as interações de configurações entre Grupos do Microsoft 365, Teams e SharePoint
ms.openlocfilehash: ba3578903731a66d66c943f8daaec1a61943228c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921007"
---
# <a name="settings-interactions-between-microsoft-365-groups-teams-and-sharepoint"></a>Configurações de interações entre Grupos do Microsoft 365, Teams e SharePoint

Algumas configurações para Grupos do Microsoft 365, Microsoft Teams e SharePoint no Microsoft 365, particularmente relacionadas ao compartilhamento e criação de grupo/equipe e site do SharePoint, se sobrepõem entre si. Este artigo fornece descrições dessas interações e práticas recomendadas para como trabalhar com essas configurações.

![Diagrama de Venn dos recursos do SharePoint, Teams e grupos](../media/teams-groups-sharepoint-venn.png)

## <a name="the-effects-of-sharepoint-settings-on-groups-and-teams"></a>Os efeitos das configurações do SharePoint em grupos e equipes

|Configuração do SharePoint|Descrição|Efeito nos grupos do Microsoft 365 e no Teams|Recomendação|
|:-----------------|:----------|:---------------------------------------|:-------------|
|Compartilhamento externo para organização e site|Determina se sites, arquivos e pastas podem ser compartilhados com pessoas de fora da organização.|Se as configurações do SharePoint, grupos e Teams não corresponderem, os convidados da equipe poderão ser impedidos de acessar o site, ou poderá ocorrer um acesso externo inesperado.|Ao alterar as configurações de compartilhamento, verifique Configurações de grupos, configurações do Teams e configurações de site do SharePoint para sites de equipe conectados a grupos.<br><br> Consulte [Colaborar com convidados em uma equipe](./collaborate-as-team.md)|
|Domínio allow/block|Permite ou impede que o conteúdo seja compartilhado com domínios especificados.|Os grupos e o Teams não reconhecem listas de permitir ou bloquear o SharePoint. Os usuários de domínios não permitidos no SharePoint podem obter acesso a sites ou conteúdo do SharePoint por meio de uma equipe.|Gerenciar listas de permitir/bloquear domínios para o Azure AD e o SharePoint juntos. Crie um processo de governança em toda a organização para permitir e bloquear domínios.<br><br>Consulte [Configurações de domínio do SharePoint](/sharepoint/restricted-domains-sharing) e configurações de domínio [do Azure AD](/azure/active-directory/b2b/allow-deny-list)|
|Permitir que somente os usuários de grupos específicos de segurança compartilhem externamente|Especifica grupos de segurança que podem compartilhar sites, pastas e arquivos do SharePoint externamente.|Essa configuração não impede que os proprietários de equipe compartilhem equipes externamente. Os convidados da equipe têm acesso ao site do SharePoint associado.||
|Configurações de compartilhamento de site do SharePoint|Determina quem pode compartilhar o site diretamente fora da associação de equipe. Isso é configurado pela equipe ou proprietário do site.|Essa configuração não afeta diretamente a equipe, mas pode permitir que os usuários sejam adicionados a um site e não tenham acesso à própria equipe ou a outros recursos do Teams|Considere usar essa configuração para limitar o compartilhamento do site diretamente e gerenciar o acesso ao site por meio da equipe.|
|Permitir que os usuários criem sites da página inicial do SharePoint e do OneDrive|Especifica se os usuários podem criar novos sites do SharePoint.|Se essa configuração estiver desligada, os usuários ainda poderão criar sites de equipe conectados a grupos criando uma equipe.||

## <a name="the-effects-of-groups-settings-on-teams"></a>Os efeitos das configurações de grupos nas equipes

|Configuração de grupos do Microsoft 365|Descrição|Efeito no Teams|Recomendação|
|:---------------------------|:----------|:--------------|:-------------|
|Políticas de nomenclatura|Especifica prefixos e sufixos de nome de grupo e palavras bloqueadas para criação de grupo|As políticas são impostas aos usuários que criam equipes.||
|Acesso de convidados de grupo|Especifica se pessoas de fora da organização podem ser adicionadas a grupos.|Se as configurações de compartilhamento de convidados do Teams ou grupos estão desligadas, a equipe não pode ser compartilhada com convidados.|Ao alterar as configurações de compartilhamento de convidados, verifique as configurações do Teams, grupos e do site do SharePoint associado à equipe.<br><br> Consulte [Colaborar com convidados em uma equipe](./collaborate-as-team.md)|
|Criação de grupo por grupo de segurança|Os grupos só podem ser criados por membros de um grupo de segurança específico.|Os usuários que não são membros do grupo de segurança não poderão criar uma equipe.|Certifique-se de que o processo de solicitação de um grupo inclua instruções para solicitar uma equipe ou um site do SharePoint.|
|Política de expiração de grupo|Especifica um período de tempo após o qual os grupos que não são usados ativamente serão excluídos automaticamente.|Quando o grupo é excluído, a equipe e o site associado do SharePoint também são excluídos. O conteúdo protegido por políticas de retenção é mantido.|Use políticas de expiração para evitar a expansão de equipes, grupos e sites não usado.|

## <a name="related-topics"></a>Tópicos relacionados

[Planejamento de governança de colaboração passo a passo](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Criar seu plano de governança de colaboração](collaboration-governance-first.md)

[Colaborar com pessoas de fora da sua organização](./collaborate-with-people-outside-your-organization.md)

[Gerenciar a criação de sites no SharePoint](/sharepoint/manage-site-creation)