---
title: Configurações de interações entre o Microsoft 365 grupos e o SharePoint
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
description: Saiba mais sobre as interações de configurações entre os grupos do Microsoft 365 e o SharePoint
ms.openlocfilehash: e8d4189c2d945d5a6d2aa78bd7ea980a77360ce0
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377552"
---
# <a name="settings-interactions-between-microsoft-365-groups-and-sharepoint"></a>Configurações de interações entre o Microsoft 365 grupos e o SharePoint

Algumas configurações dos grupos do Microsoft 365 e do SharePoint no Microsoft 365, especialmente relacionadas ao compartilhamento e à criação de um grupo e de um site de equipe, se sobrepõem. Este artigo fornece descrições dessas interações e práticas recomendadas sobre como trabalhar com essas configurações.

![Diagrama de Venn dos recursos do SharePoint, do Yammer e dos grupos](../media/groups-sharepoint-venn.png)

## <a name="the-effects-of-sharepoint-settings-on-microsoft-365-groups"></a>Os efeitos das configurações do SharePoint nos grupos do Microsoft 365

|Configuração do SharePoint|Descrição|Efeito nos grupos do Microsoft 365|Recomendação|
|:-----------------|:----------|:-----------------------------|:-------------|
|Compartilhamento externo para organização e site|Determina se sites, arquivos e pastas podem ser compartilhados com pessoas de fora da organização.|Se as configurações do SharePoint e dos grupos não forem correspondentes, os convidados no grupo poderão ser impedidos de acessar o site ou o acesso externo poderá estar disponível no site, mas não no grupo.|Ao alterar as configurações de compartilhamento, verifique as configurações de grupos e de site do SharePoint para sites de equipe conectados ao grupo.<br><br>Consulte [colaborar com convidados em um site](https://docs.microsoft.com/microsoft-365/solutions/collaborate-in-site).|
|Permissão/bloqueio de domínio|Permite ou impede que o conteúdo seja compartilhado com domínios especificados.|Grupos não reconhece listas de permissões ou bloqueios do SharePoint. Os usuários de domínios despermitidos no SharePoint podem obter acesso ao SharePoint por meio de um grupo.|Gerenciar listas de permissões/bloqueios de domínio para o Azure AD e o SharePoint juntos. Criar um processo de governança de toda a organização para permitir e bloquear domínios.<br><br>Confira configurações de [domínio do SharePoint](https://docs.microsoft.com/sharepoint/restricted-domains-sharing) e [configurações de domínio do Azure ad](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)|
|Permitir que somente usuários em grupos de segurança específicos compartilhem externamente|Especifica grupos de segurança que podem compartilhar sites, pastas e arquivos externamente.|Essa configuração não afeta os grupos de compartilhamento de proprietários de grupo externamente. Os convidados de grupo têm acesso ao site do SharePoint associado.||
|Configurações de compartilhamento de site do SharePoint|Determina quem pode compartilhar o site diretamente fora da Associação de grupo. Isso é configurado pelo proprietário do grupo ou site.|Essa configuração não afeta o grupo diretamente, mas pode permitir que os usuários sejam adicionados a um site e não tenham acesso a outros recursos de grupo|Considere usar essa configuração para limitar o compartilhamento do site diretamente e gerenciar o acesso ao site por meio do grupo.|
|Permitir que os usuários criem sites da página inicial do SharePoint e do OneDrive|Especifica se os usuários podem criar novos sites do SharePoint.|Se essa configuração estiver desativada, os usuários ainda poderão criar sites de equipe conectados ao grupo criando um grupo.||

## <a name="the-effects-of-microsoft-365-groups-setting-on-sharepoint"></a>A configuração dos efeitos da Microsoft 365 groups no SharePoint

|Configuração de grupos do Microsoft 365|Descrição|Efeito no SharePoint|Recomendação|
|:---------------------------|:----------|:-------------------|:-------------|
|Políticas de nomenclatura|Especifica prefixos e sufixos de nome de grupo e palavras bloqueadas para a criação de grupo|As políticas são aplicadas aos usuários que criam sites de equipe conectados ao grupo, mas não sites de comunicação ou sites com outros modelos.|Crie orientações de nomenclatura separadas para sites de comunicação, se necessário.|
|Acesso de convidado de grupo|Especifica se pessoas de fora da organização podem ser adicionadas a grupos.|Se as configurações do SharePoint e dos grupos não forem correspondentes, os convidados no grupo poderão ser impedidos de acessar o site ou o acesso externo poderá estar disponível no site, mas não no grupo.|Ao alterar as configurações de compartilhamento, verifique as configurações de grupos e de site do SharePoint para sites de equipe conectados ao grupo.<br><br>Consulte [colaborar com convidados em um site](https://docs.microsoft.com/microsoft-365/solutions/collaborate-in-site)|
|Criação de grupo por grupo de segurança|Os grupos só podem ser criados por membros de um grupo de segurança específico.|Os usuários que não forem membros do grupo de segurança não poderão criar um site de equipe conectado ao grupo.|Certifique-se de que o processo de solicitação de um grupo inclua instruções para solicitar um site.|
|Política de expiração de grupo|Especifica um período de tempo após o qual os grupos que não são ativamente usados serão excluídos automaticamente.|Quando o grupo é excluído, o site associado do SharePoint também é excluído. O conteúdo protegido por políticas de retenção é mantido.|Use as políticas de expiração para evitar a desorganização de grupos e sites não utilizados.|

## <a name="related-topics"></a>Tópicos relacionados

[Colaborar com pessoas de fora da sua organização](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization)

[Gerenciar a criação de sites no SharePoint](https://docs.microsoft.com/sharepoint/manage-site-creation)