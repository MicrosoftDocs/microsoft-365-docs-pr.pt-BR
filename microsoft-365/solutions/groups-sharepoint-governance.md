---
title: Configurações interações entre Microsoft 365 Grupos e SharePoint
ms.reviewer: mmclean
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
description: Saiba mais sobre as interações de configurações entre Microsoft 365 Grupos e SharePoint
ms.openlocfilehash: 23e9553ce07514b18bafada5c93bcadab19806fe
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538154"
---
# <a name="settings-interactions-between-microsoft-365-groups-and-sharepoint"></a>Configurações interações entre Microsoft 365 Grupos e SharePoint

Algumas configurações para Microsoft 365 Grupos e SharePoint no Microsoft 365, particularmente relacionadas ao compartilhamento e criação de sites de grupo e equipe, se sobrepõem entre si. Este artigo fornece descrições dessas interações e práticas recomendadas para como trabalhar com essas configurações.

![Diagrama venn de SharePoint, Yammer e recursos de grupos](../media/groups-sharepoint-venn.png)

## <a name="the-effects-of-sharepoint-settings-on-microsoft-365-groups"></a>Os efeitos das SharePoint configurações em Microsoft 365 grupos

|SharePoint configuração|Descrição|Efeito sobre Microsoft 365 grupos|Recomendação|
|:-----------------|:----------|:-----------------------------|:-------------|
|Compartilhamento externo para organização e site|Determina se sites, arquivos e pastas podem ser compartilhados com pessoas de fora da organização.|Se SharePoint e grupos não corresponderem, os convidados no grupo poderão ser impedidos de acessar o site ou o acesso externo poderá estar disponível no site, mas não no grupo.|Ao alterar as configurações de compartilhamento, verifique as configurações de grupos e SharePoint de site para sites de equipe conectados a grupos.<br><br>Consulte [Colaborar com convidados em um site](./collaborate-in-site.md).|
|Domínio allow/block|Permite ou impede que o conteúdo seja compartilhado com domínios especificados.|Os grupos não reconhecem SharePoint listas de bloqueio ou de permitir. Os usuários de domínios não permitidos em SharePoint podem obter acesso a SharePoint por meio de um grupo.|Gerenciar listas de permitir/bloquear domínio para o Azure AD e SharePoint juntos. Crie um processo de governança em toda a organização para permitir e bloquear domínios.<br><br>Consulte [SharePoint configurações de domínio e](/sharepoint/restricted-domains-sharing) configurações de domínio do [Azure AD](/azure/active-directory/b2b/allow-deny-list)|
|Permita que somente os usuários de grupos específicos de segurança compartilhem externamente|Especifica grupos de segurança que podem compartilhar sites, pastas e arquivos externamente.|Essa configuração não afeta os proprietários de grupos que compartilham grupos externamente. Os convidados do grupo têm acesso ao site SharePoint associado.||
|SharePoint configurações de compartilhamento de site|Determina quem pode compartilhar o site diretamente fora da associação ao grupo. Isso é configurado pelo grupo ou proprietário do site.|Essa configuração não afeta diretamente o grupo, mas pode permitir que os usuários sejam adicionados a um site e não tenham acesso a outros recursos de grupo|Considere usar essa configuração para limitar o compartilhamento do site diretamente e gerenciar o acesso ao site por meio do grupo.|
|Permitir que os usuários criem sites SharePoint página inicial e OneDrive|Especifica se os usuários podem criar novos SharePoint sites.|Se essa configuração estiver desligada, os usuários ainda poderão criar sites de equipe conectados a grupos criando um grupo.||

## <a name="the-effects-of-microsoft-365-groups-setting-on-sharepoint"></a>Os efeitos da configuração Microsoft 365 grupos no SharePoint

|Microsoft 365 de grupos|Descrição|Efeito sobre SharePoint|Recomendação|
|:---------------------------|:----------|:-------------------|:-------------|
|Políticas de nomenclatura|Especifica prefixos e sufixos de nome de grupo e palavras bloqueadas para criação de grupo|As políticas são impostas aos usuários que criam sites de equipe conectados a grupos, mas não sites de comunicação ou sites com outros modelos.|Crie diretrizes de nomenização separadas para sites de comunicação, se necessário.|
|Acesso de convidados de grupo|Especifica se pessoas de fora da organização podem ser adicionadas a grupos.|Se SharePoint e grupos não corresponderem, os convidados no grupo poderão ser impedidos de acessar o site ou o acesso externo poderá estar disponível no site, mas não no grupo.|Ao alterar as configurações de compartilhamento, verifique as configurações de grupos e SharePoint de site para sites de equipe conectados a grupos.<br><br>Consulte [Colaborar com convidados em um site](./collaborate-in-site.md)|
|Criação de grupo por grupo de segurança|Os grupos só podem ser criados por membros de um grupo de segurança específico.|Os usuários que não são membros do grupo de segurança não poderão criar um site de equipe conectado ao grupo.|Certifique-se de que o processo de solicitação de um grupo inclua instruções para solicitar um site.|
|Política de expiração de grupo|Especifica um período de tempo após o qual os grupos que não são usados ativamente serão excluídos automaticamente.|Quando o grupo é excluído, o site SharePoint associado também é excluído. O conteúdo protegido por políticas de retenção é mantido.|Use políticas de expiração para evitar a expansão de grupos e sites não usado.|

## <a name="related-topics"></a>Tópicos relacionados

[Planejamento de governança de colaboração passo a passo](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Criar seu plano de governança de colaboração](collaboration-governance-first.md)

[Colaborar com pessoas de fora da sua organização](./collaborate-with-people-outside-your-organization.md)

[Gerenciar a criação de sites no SharePoint](/sharepoint/manage-site-creation)