---
title: Interações de configurações entre grupos do Microsoft 365 e SharePoint
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
description: Saiba mais sobre as interações de configurações entre os Grupos do Microsoft 365 e o SharePoint
ms.openlocfilehash: a00e863fead8e74cf0f169471ebb36f9539ed103
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613485"
---
# <a name="settings-interactions-between-microsoft-365-groups-and-sharepoint"></a>Interações de configurações entre grupos do Microsoft 365 e SharePoint

Algumas configurações dos Grupos do Microsoft 365 e do SharePoint no Microsoft 365, particularmente relacionadas ao compartilhamento e à criação de sites de equipe e de grupo, se sobrepõem entre si. Este artigo fornece descrições dessas interações e práticas recomendadas sobre como trabalhar com essas configurações.

![Venn diagram of SharePoint, Yammer, and groups features](../media/groups-sharepoint-venn.png)

## <a name="the-effects-of-sharepoint-settings-on-microsoft-365-groups"></a>Os efeitos das configurações do SharePoint nos grupos do Microsoft 365

|Configuração do SharePoint|Descrição|Efeito sobre grupos do Microsoft 365|Recomendação|
|:-----------------|:----------|:-----------------------------|:-------------|
|Compartilhamento externo para organização e site|Determina se sites, arquivos e pastas podem ser compartilhados com pessoas de fora da organização.|Se as configurações do SharePoint e de grupos não corresponderem, os convidados no grupo poderão ser impedidos de acessar o site ou o acesso externo poderá estar disponível no site, mas não no grupo.|Ao alterar as configurações de compartilhamento, verifique as configurações de Grupos e do site do SharePoint para sites de equipe conectados ao grupo.<br><br>Consulte [Colaborar com convidados em um site.](https://docs.microsoft.com/microsoft-365/solutions/collaborate-in-site)|
|Domínio permitir/bloquear|Permite ou impede que o conteúdo seja compartilhado com domínios especificados.|Os grupos não reconhecem listas de bloqueio ou de autorização do SharePoint. Os usuários de domínios não permitidos no SharePoint podem obter acesso ao SharePoint por meio de um grupo.|Gerenciar listas de bloqueio/autorização de domínio para o Azure AD e o SharePoint juntos. Crie um processo de governança em toda a organização para permitir e bloquear domínios.<br><br>Ver [configurações de domínio do SharePoint](https://docs.microsoft.com/sharepoint/restricted-domains-sharing) e configurações de domínio [do Azure AD](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)|
|Permitir que somente os usuários de grupos específicos de segurança compartilhem externamente|Especifica grupos de segurança que podem compartilhar sites, pastas e arquivos externamente.|Essa configuração não afeta os proprietários do grupo que compartilham grupos externamente. Os convidados do grupo têm acesso ao site do SharePoint associado.||
|Configurações de compartilhamento de site do SharePoint|Determina quem pode compartilhar o site diretamente fora da associação de grupo. Isso é configurado pelo grupo ou proprietário do site.|Essa configuração não afeta o grupo diretamente, mas pode permitir que os usuários sejam adicionados a um site e não tenham acesso a outros recursos do grupo|Considere usar essa configuração para limitar o compartilhamento do site diretamente e gerenciar o acesso ao site por meio do grupo.|
|Permitir que os usuários criem sites na página inicial do SharePoint e no OneDrive|Especifica se os usuários podem criar novos sites do SharePoint.|Se essa configuração estiver desligada, os usuários ainda poderão criar sites de equipe conectados ao grupo criando um grupo.||

## <a name="the-effects-of-microsoft-365-groups-setting-on-sharepoint"></a>Os efeitos da configuração de grupos do Microsoft 365 no SharePoint

|Configuração de grupos do Microsoft 365|Descrição|Efeito no SharePoint|Recomendação|
|:---------------------------|:----------|:-------------------|:-------------|
|Políticas de nomenclatura|Especifica prefixos e sufixos de nome de grupo e palavras bloqueadas para criação de grupo|As políticas são impostas para usuários que criam sites de equipe conectados ao grupo, mas não sites de comunicação ou sites com outros modelos.|Crie uma orientação de nomen por nomeação separada para sites de comunicação, se necessário.|
|Acesso de convidados do grupo|Especifica se pessoas de fora da organização podem ser adicionadas a grupos.|Se as configurações do SharePoint e de grupos não corresponderem, os convidados no grupo poderão ser impedidos de acessar o site ou o acesso externo poderá estar disponível no site, mas não no grupo.|Ao alterar as configurações de compartilhamento, verifique as configurações de Grupos e do site do SharePoint para sites de equipe conectados ao grupo.<br><br>Ver [Colaborar com convidados em um site](https://docs.microsoft.com/microsoft-365/solutions/collaborate-in-site)|
|Criação de grupo por grupo de segurança|Os grupos só podem ser criados por membros de um grupo de segurança específico.|Os usuários que não são membros do grupo de segurança não poderão criar um site de equipe conectado ao grupo.|Certifique-se de que seu processo de solicitação de um grupo inclua instruções para solicitar um site.|
|Política de expiração de grupo|Especifica um período após o qual os grupos que não são usados ativamente serão automaticamente excluídos.|Quando o grupo é excluído, o site do SharePoint associado também é excluído. O conteúdo protegido por políticas de retenção é mantido.|Use políticas de expiração para evitar a expansão de grupos e sites não usado.|

## <a name="related-topics"></a>Tópicos relacionados

[Planejamento de governança de colaboração passo a passo](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Criar seu plano de governança de colaboração](collaboration-governance-first.md)

[Colaborar com pessoas de fora da sua organização](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization)

[Gerenciar a criação de sites no SharePoint](https://docs.microsoft.com/sharepoint/manage-site-creation)