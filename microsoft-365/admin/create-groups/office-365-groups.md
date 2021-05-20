---
title: Visão geral dos Grupos do Microsoft 365 para administradores
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
description: Com Microsoft 365 Grupos, você pode conduzir o trabalho em equipe em Microsoft 365 dando a um grupo de pessoas acesso a uma coleção de recursos compartilhados.
ms.openlocfilehash: bfcd2d27bc1d63fcc8b306267efe21c3f9564522
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2021
ms.locfileid: "52582735"
---
# <a name="overview-of-microsoft-365-groups-for-administrators"></a>Visão geral dos Grupos do Microsoft 365 para administradores

Microsoft 365 Grupos é o serviço de associação fundamental que orienta todo o trabalho em equipe em Microsoft 365. Com Microsoft 365 grupos, você pode dar a um grupo de pessoas acesso a uma coleção de recursos compartilhados. Esses recursos incluem:

- Uma caixa de Outlook de entrada compartilhada
- Um calendário compartilhado
- Uma SharePoint de documentos
- Um Planner
- Um bloco de anotações do OneNote
- Power BI
- Yammer (se o grupo foi criado a partir Yammer)
- Uma equipe (se o grupo foi criado a partir Teams)
- Roteiro (se você tiver Project para a Web)
- Stream

Com um Microsoft 365, você não precisa atribuir permissões manualmente a cada um desses recursos. Adicionar pessoas ao grupo fornece automaticamente as permissões de que precisam.

Qualquer usuário pode criar um grupo, a menos que você limite a criação [de grupo a um conjunto específico de pessoas](../../solutions/manage-creation-of-groups.md). Se você limitar a criação de grupo, os usuários que não puderem criar grupos não poderão criar SharePoint sites, Planners ou equipes. Esses serviços exigem que as pessoas que os criem sejam capazes de criar um grupo. Os usuários ainda podem participar de atividades de grupo, como criar tarefas no Planner ou usar Teams chat, desde que sejam membros do grupo.

Os grupos têm as seguintes funções:

- **Proprietários** - Os proprietários do grupo podem adicionar ou remover membros e ter permissões exclusivas, como a capacidade de excluir conversas da caixa de entrada compartilhada ou alterar configurações diferentes sobre o grupo. Os proprietários do grupo podem renomear o grupo, atualizar a descrição ou a imagem e muito mais.
- **Membros** - Os membros podem acessar tudo no grupo, mas não podem alterar as configurações de grupo. Por padrão, os membros do grupo podem convidar convidados para ingressar em seu grupo, embora você possa [controlar essa configuração](manage-guest-access-in-groups.md).
- **Convidados** - Os convidados do grupo são membros de fora da sua organização.

Somente administradores globais, administradores de usuários e grupos podem criar e gerenciar grupos no Microsoft 365 de administração. Não é possível ser um administrador delegado (por exemplo, um consultor que é administrador em nome de outra pessoa).

Como administrador, você pode:

- [Especificar quem pode criar grupos](../../solutions/manage-creation-of-groups.md)
- [Criar uma política de nomen por grupos em sua organização](../../solutions/groups-naming-policy.md)
- [Escolha qual domínio usar ao criar um grupo](../../solutions/choose-domain-to-create-groups.md)
- [Gerenciar o acesso de convidado a grupos](manage-guest-access-in-groups.md)
- [Recuperar um grupo excluído](restore-deleted-group.md) (dentro de 30 dias após a exclusão)

Se você preferir uma maneira mais automatizada de gerenciar o ciclo de vida de seus grupos Microsoft 365, você pode usar políticas de expiração para expirar grupos em um intervalo de tempo específico. Os proprietários do grupo receberão um email 30, 15 e 1 dia antes da expiração do grupo que permite que eles renovem o grupo se ainda for necessário. Consulte: Microsoft 365 [política de expiração de grupo.](../../solutions/microsoft-365-groups-expiration-policy.md)

Você pode administrar seus grupos do centro de administração Microsoft 365 ou [usando o PowerShell](../../enterprise/manage-microsoft-365-groups-with-powershell.md).

Se você tiver muitos usuários, como em uma grande empresa ou empresa, poderá ter muitos usuários que criam grupos para várias finalidades. É altamente recomendável que você revise [Plan for governance in Microsoft 365 grupos](../../solutions/collaboration-governance-overview.md) para práticas recomendadas.

## <a name="group-limits"></a>Limites de grupo

Os seguintes limites se aplicam a Microsoft 365 Grupos:

|Máximo...|Valor|
|:---------|:----|
|Owners per group|100|
|Groups a user can create|250|
|Grupos que um administrador pode criar|Até o limite de locatário padrão de 500 K|
|Number of members |Mais de 1.000, embora apenas 1.000 possam acessar as conversas de Grupo simultaneamente. <br>Os usuários podem notar atrasos ao acessar o calendário e as conversas em grupos grandes Outlook.|
|Número de grupos de que um usuário pode ser membro|7,000|
|Armazenamento de arquivos|1 Terabyte + 10 GB por usuário inscrito + qualquer outro armazenamento adquirido. Você pode comprar uma quantidade ilimitada de armazenamento extra.|
|Tamanho da Caixa de Correio de Grupo|50 GB|

O número máximo padrão de grupos Microsoft 365 que uma organização pode ter é 500.000. Para ir além do limite padrão, você deve entrar em contato com o Suporte da Microsoft. Para obter mais informações sobre Microsoft 365 de grupos, [consulte Microsoft 365 Grupos - Ajuda do administrador](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2).

Gerenciar seus grupos Microsoft 365 é mais eficaz quando você tem informações a actionable sobre o uso de grupos. O Microsoft 365 de administração tem uma ferramenta de relatório que permite que você veja o uso de armazenamento, quantos grupos ativos você tem e como os usuários estão usando os grupos. Confira: [Microsoft 365 relatórios no centro de administração para](../activity-reports/office-365-groups.md) obter mais informações.

## <a name="sensitivity-labels"></a>Rótulos de confidencialidade

Você pode criar rótulos de sensibilidade que os usuários em sua organização podem definir quando eles criam um Microsoft 365 grupo. Com rótulos de sensibilidade, você pode configurar: 

- Privacidade (pública ou privada)
- Acesso de usuários externos
- Acesso de dispositivo sem controle

Por exemplo, você pode criar um rótulo chamado *Altamente Confidencial* e especificar que qualquer grupo criado com esse rótulo será privado e não permitirá usuários externos. Quando os usuários em sua organização selecionam esse rótulo durante a criação do grupo, o grupo será definido como privado e os membros do grupo não terão permissão para adicionar usuários externos ao grupo.

> [!IMPORTANT]
> Se você estiver usando rótulos de classificação no momento, eles não estarão mais disponíveis para usuários que criam grupos depois que os rótulos de sensibilidade estão habilitados. 

Para obter informações sobre como criar, gerenciar e usar rótulos de sensibilidade, consulte Usar rótulos de sensibilidade para proteger o conteúdo em Microsoft Teams, grupos Microsoft 365 [e sites SharePoint.](../../compliance/sensitivity-labels-teams-groups-sites.md)

## <a name="which-microsoft-365-plans-include-groups"></a>Quais Microsoft 365 planos incluem grupos?

Qualquer Microsoft 365 assinatura que tenha Exchange Online e SharePoint Online dará suporte a grupos. Isso inclui os planos Business Essentials e Business Premium e os planos Enterprise E1, E3 e E5. O grupo assume o licenciamento da pessoa que cria o grupo (também conhecido como "organizador" do grupo). Contanto que o organizador tenha a licença adequada para os recursos que você deseja que o grupo tenha, essa licença será transmitida para o grupo.

> [!NOTE]
> Para obter mais detalhes sobre Microsoft 365 e planos de serviço, [consulte Microsoft 365 opções de plano.](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options)

Se você tiver um plano somente Exchange, ainda poderá obter a caixa de entrada compartilhada e os recursos de calendário compartilhados de grupos no Outlook, mas não obterá a biblioteca de documentos, o Planner ou qualquer um dos outros recursos.

Microsoft 365 grupos trabalham com Azure Active Directory. Os recursos de grupos que você recebe dependem de qual assinatura Azure Active Directory você tem e quais licenças são atribuídas ao organizador do grupo.

> [!IMPORTANT]
> Para todos os recursos de grupos, se você tiver uma assinatura do Azure AD Premium, os usuários poderão ingressar no grupo se eles têm ou não uma licença AAD P1 atribuída a eles. O licenciamento não é imposto.
> Periodicamente, geraremos relatórios de uso que informam quais usuários estão ausentes de uma licença e precisam de um atribuído a eles para estar em conformidade com os requisitos de licenciamento. Por exemplo, digamos que um usuário não tem uma licença e ele é adicionado a um grupo em que a política de nomen náutico é imposta. O relatório sinaliza que eles precisam de uma licença.

## <a name="related-content"></a>Conteúdo relacionado

[Saiba mais Microsoft 365 Grupos](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2) (artigo)

[Atualizar listas de distribuição para Microsoft 365 Grupos](../manage/upgrade-distribution-lists.md) (artigo)

[Gerenciar Microsoft 365 grupos com o PowerShell](../../enterprise/manage-microsoft-365-groups-with-powershell.md) (artigo)

[SharePoint Online](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits) (artigo)

[Organizar grupos e canais no Microsoft Stream](/stream/groups-channels-organization) (artigo)