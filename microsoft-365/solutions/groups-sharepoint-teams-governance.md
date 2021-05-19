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
recommendations: false
description: Saiba mais sobre as interações de configurações entre Microsoft 365 Grupos, Teams e SharePoint
ms.openlocfilehash: 14a21cd34fe38b47d93d0cbcec5e9cb2a3bc49c7
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52539078"
---
# <a name="settings-interactions-between-microsoft-365-groups-teams-and-sharepoint"></a>Configurações de interações entre Grupos do Microsoft 365, Teams e SharePoint

Algumas configurações para Microsoft 365 Grupos, Microsoft Teams e SharePoint no Microsoft 365, particularmente relacionadas ao compartilhamento e à criação de SharePoint de grupo e de SharePoint, se sobrepõem umas às outras. Este artigo fornece descrições dessas interações e práticas recomendadas para como trabalhar com essas configurações.

![Diagrama venn de SharePoint, Teams e recursos de grupos](../media/teams-groups-sharepoint-venn.png)

## <a name="the-effects-of-sharepoint-settings-on-groups-and-teams"></a>Os efeitos das configurações SharePoint grupos e equipes

|SharePoint configuração|Descrição|Efeito sobre Microsoft 365 grupos e Teams|Recomendação|
|:-----------------|:----------|:---------------------------------------|:-------------|
|Compartilhamento externo para organização e site|Determina se sites, arquivos e pastas podem ser compartilhados com pessoas de fora da organização.|Se SharePoint, grupos e Teams configurações não corresponderem, os convidados da equipe poderão ser impedidos de acessar o site, ou poderá ocorrer um acesso externo inesperado.|Ao alterar as configurações de compartilhamento, verifique configurações de grupos, Teams configurações SharePoint site para sites de equipe conectados a grupos.<br><br> Consulte [Colaborar com convidados em uma equipe](./collaborate-as-team.md)|
|Domínio allow/block|Permite ou impede que o conteúdo seja compartilhado com domínios especificados.|Grupos e Teams não reconhecem SharePoint listas de bloqueio ou permitir. Os usuários de domínios não permitidos em SharePoint podem obter acesso SharePoint sites ou conteúdo por meio de uma equipe.|Gerenciar listas de permitir/bloquear domínio para o Azure AD e SharePoint juntos. Crie um processo de governança em toda a organização para permitir e bloquear domínios.<br><br>Consulte [SharePoint configurações de domínio e](/sharepoint/restricted-domains-sharing) configurações de domínio do [Azure AD](/azure/active-directory/b2b/allow-deny-list)|
|Permita que somente os usuários de grupos específicos de segurança compartilhem externamente|Especifica grupos de segurança que podem compartilhar SharePoint sites, pastas e arquivos externamente.|Essa configuração não impede que os proprietários de equipe compartilhem equipes externamente. Os convidados da equipe têm acesso ao site SharePoint associado.||
|SharePoint configurações de compartilhamento de site|Determina quem pode compartilhar o site diretamente fora da associação de equipe. Isso é configurado pela equipe ou proprietário do site.|Essa configuração não afeta diretamente a equipe, mas pode permitir que os usuários sejam adicionados a um site e não tenham acesso à própria equipe ou a outros recursos Teams.|Considere usar essa configuração para limitar o compartilhamento do site diretamente e gerenciar o acesso ao site por meio da equipe.|
|Permitir que os usuários criem sites SharePoint página inicial e OneDrive|Especifica se os usuários podem criar novos SharePoint sites.|Se essa configuração estiver desligada, os usuários ainda poderão criar sites de equipe conectados a grupos criando uma equipe.||

## <a name="the-effects-of-groups-settings-on-teams"></a>Os efeitos das configurações de grupos nas equipes

|Microsoft 365 de grupos|Descrição|Efeito sobre Teams|Recomendação|
|:---------------------------|:----------|:--------------|:-------------|
|Políticas de nomenclatura|Especifica prefixos e sufixos de nome de grupo e palavras bloqueadas para criação de grupo|As políticas são impostas aos usuários que criam equipes.||
|Acesso de convidados de grupo|Especifica se pessoas de fora da organização podem ser adicionadas a grupos.|Se os grupos ou Teams configurações de compartilhamento de convidados estão desligadas, a equipe não pode ser compartilhada com convidados.|Ao alterar as configurações de compartilhamento de convidados, verifique as configurações Teams, grupos e o site SharePoint associado à equipe.<br><br> Consulte [Colaborar com convidados em uma equipe](./collaborate-as-team.md)|
|Criação de grupo por grupo de segurança|Os grupos só podem ser criados por membros de um grupo de segurança específico.|Os usuários que não são membros do grupo de segurança não poderão criar uma equipe.|Certifique-se de que o processo de solicitação de um grupo inclua instruções para solicitar uma equipe ou um SharePoint site.|
|Política de expiração de grupo|Especifica um período de tempo após o qual os grupos que não são usados ativamente serão excluídos automaticamente.|Quando o grupo é excluído, a equipe e o site SharePoint associados também são excluídos. O conteúdo protegido por políticas de retenção é mantido.|Use políticas de expiração para evitar a expansão de equipes, grupos e sites não usado.|

## <a name="related-topics"></a>Tópicos relacionados

[Planejamento de governança de colaboração passo a passo](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Criar seu plano de governança de colaboração](collaboration-governance-first.md)

[Colaborar com pessoas de fora da sua organização](./collaborate-with-people-outside-your-organization.md)

[Gerenciar a criação de sites no SharePoint](/sharepoint/manage-site-creation)