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
description: Saiba mais sobre os Grupos do Microsoft 365.
ms.openlocfilehash: 5d5c15c13d46738ac9de701b5a39f47274b9f1e5
ms.sourcegitcommit: c0cfb9b354db56fdd329aec2a89a9b2cf160c4b0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2021
ms.locfileid: "50094728"
---
# <a name="overview-of-microsoft-365-groups-for-administrators"></a>Visão geral dos Grupos do Microsoft 365 para administradores

Os Grupos do Microsoft 365 são o serviço de associação fundamental que orienta todo o trabalho em equipe no Microsoft 365. Com os Grupos do Microsoft 365, você pode dar a um grupo de pessoas acesso a uma coleção de recursos compartilhados. Esses recursos incluem:

- Uma caixa de entrada compartilhada do Outlook
- Um calendário compartilhado
- Uma biblioteca de documentos do SharePoint
- Um Planejador
- Um bloco de anotações do OneNote
- Power BI
- Yammer (se o grupo foi criado a partir do Yammer)
- Uma equipe (se o grupo foi criado a partir do Teams)
- Mapa (se você tiver o Project para a Web)

Com um grupo do Microsoft 365, você não precisa atribuir permissões manualmente a cada um desses recursos. Adicionar pessoas ao grupo fornece automaticamente as permissões de que precisam.

Qualquer usuário pode criar um grupo, a menos que você limite a criação de [um conjunto específico de pessoas.](manage-creation-of-groups.md) Se você limitar a criação de grupos, os usuários que não puderem criar grupos não poderão criar sites, Planejadores ou equipes do SharePoint. Esses serviços exigem que as pessoas que as criam sejam capazes de criar um grupo. Os usuários ainda podem participar de atividades de grupo, como criar tarefas no Planner ou usar o chat do Teams, desde que sejam membros do grupo.

Os grupos têm as seguintes funções:

- **Proprietários** – os proprietários do grupo podem adicionar ou remover membros e ter permissões exclusivas, como a capacidade de excluir conversas da caixa de entrada compartilhada ou alterar configurações diferentes sobre o grupo. Os proprietários do grupo podem renomear o grupo, atualizar a descrição ou a imagem e muito mais.
- **Membros** - Os membros podem acessar tudo no grupo, mas não podem alterar as configurações do grupo. Por padrão, os membros do grupo podem convidar convidados para ingressar em seu grupo, embora você possa [controlar essa configuração.](manage-guest-access-in-groups.md)
- **Convidados** - Os convidados do grupo são membros que são de fora da sua organização.

Somente administradores globais, administradores de usuários e administradores de grupos podem criar e gerenciar grupos no Centro de administração do Microsoft 365. Não é possível ser um administrador delegado (por exemplo, um consultor que é administrador em nome de outra pessoa).

Como administrador, você pode:

- [Especificar quem pode criar grupos](manage-creation-of-groups.md)
- [Criar uma política de nomeação para grupos em sua organização](groups-naming-policy.md)
- [Escolher qual domínio usar ao criar um grupo](choose-domain-to-create-groups.md)
- [Gerenciar o acesso de convidado a grupos](manage-guest-access-in-groups.md)
- [Recuperar um grupo excluído](restore-deleted-group.md) (dentro de 30 dias após a exclusão)

Se você preferir uma maneira mais automatizada de gerenciar o ciclo de vida dos grupos do Microsoft 365, poderá usar políticas de expiração para expirar grupos em um intervalo de tempo específico. Os proprietários do grupo receberão um email 30, 15 e 1 dia antes da expiração do grupo, permitindo que eles renovem o grupo, caso ainda seja necessário. Confira: Política de Expiração de Grupo do [Microsoft 365.](office-365-groups-expiration-policy.md)

Você pode administrar seus grupos no centro de administração do Microsoft 365 [ou usando o PowerShell.](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell)

Se você tiver muitos usuários, como em uma grande corporação ou empresa, talvez tenha muitos usuários que criem grupos para várias finalidades. É altamente recomendável que você revise [o Plano de governança nos grupos do Microsoft 365](plan-for-groups-governance.md) para práticas recomendadas.

## <a name="group-limits"></a>Limites de grupo

Os seguintes limites se aplicam aos Grupos do Microsoft 365:

|Máximo...|Valor|
|:---------|:----|
|Owners per group|100|
|Groups a user can create|250|
|Grupos que um administrador pode criar|Até o limite de locatário padrão de 500 K|
|Number of members |Mais de 1.000, embora apenas 1.000 possam acessar as conversas em grupo simultaneamente. <br>Os usuários podem notar atrasos ao acessar o calendário e as conversas em grupos grandes no Outlook.|
|Número de grupos dos que um usuário pode ser membro|7,000|
|Armazenamento de arquivos|1 Terabyte + 10 GB por usuário inscrito + qualquer outro armazenamento comprado. Você pode comprar uma quantidade ilimitada de armazenamento extra.|
|Tamanho da Caixa de Correio de Grupo|50 GB|

O número máximo padrão de grupos do Microsoft 365 que uma organização pode ter é 500.000. Para ir além do limite padrão, entre em contato com o Suporte da Microsoft. Para saber mais sobre os limites dos Grupos do Microsoft 365, confira Grupos do [Microsoft 365 - Ajuda para administradores.](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

Gerenciar seus grupos do Microsoft 365 é mais eficaz quando você tem informações a actionable sobre o uso de grupos. O Centro de administração do Microsoft 365 tem uma ferramenta de relatório que permite que você veja o uso de armazenamento, quantos grupos ativos você tem e como os usuários estão usando os grupos. Confira: [Relatórios do Microsoft 365 no centro de administração](../activity-reports/office-365-groups.md) para obter mais informações.

## <a name="sensitivity-labels"></a>Rótulos de confidencialidade

Você pode criar rótulos de sensibilidade que os usuários em sua organização podem definir ao criar um grupo do Microsoft 365. Com os rótulos de sensibilidade, você pode configurar: 

- Privacidade (pública ou privada)
- Acesso de usuários externos
- Acesso nãomanagedo a dispositivos

Por exemplo, você pode criar um rótulo chamado *Altamente* Confidencial e especificar que qualquer grupo criado com esse rótulo será privado e não permitirá usuários externos. Quando os usuários em sua organização selecionam esse rótulo durante a criação do grupo, o grupo será definido como privado e os membros do grupo não poderão adicionar usuários externos ao grupo.

> [!IMPORTANT]
> Se você estiver usando rótulos de classificação no momento, eles não estarão mais disponíveis para usuários que criam grupos depois que os rótulos de sensibilidade são habilitados. 

Para saber mais sobre como criar, gerenciar e usar rótulos de sensibilidade, confira Usar rótulos de sensibilidade para proteger o conteúdo no Microsoft Teams, grupos do [Microsoft 365 e sites do SharePoint.](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

## <a name="which-microsoft-365-plans-include-groups"></a>Quais planos do Microsoft 365 incluem grupos?

Qualquer assinatura do Microsoft 365 que tenha o Exchange Online e o SharePoint Online dará suporte a grupos. Isso inclui os planos Business Essentials e Business Premium e os planos Enterprise E1, E3 e E5. O grupo assume o licenciamento da pessoa que cria o grupo (também conhecido como "organizador" do grupo). Desde que o organizador tenha a licença adequada para os recursos que você deseja que o grupo tenha, essa licença será transmitida ao grupo.

> [!NOTE]
> Para obter mais detalhes sobre famílias de serviços e planos do Microsoft 365, confira as opções de planos [do Microsoft 365.](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options)

Se você tiver um plano somente do Exchange, ainda poderá obter a caixa de entrada compartilhada e os recursos de calendário compartilhados de grupos no Outlook, mas não obterá a biblioteca de documentos, o Planner ou qualquer um dos outros recursos.

Os grupos do Microsoft 365 funcionam com o Azure Active Directory. Os recursos de grupos que você recebe depende de qual assinatura do Azure Active Directory você tem e quais licenças são atribuídas ao organizador do grupo.

> [!IMPORTANT]
> Para todos os recursos de grupos, se você tiver uma assinatura do Azure AD Premium, os usuários poderão ingressar no grupo independentemente de eles ter ou não uma licença do AAD P1 atribuída a eles. O licenciamento não é imposto.
> Periodicamente, geraremos relatórios de uso que informam quais usuários estão sem uma licença e precisam de uma atribuída para que sejam compatíveis com os requisitos de licenciamento. Por exemplo, digamos que um usuário não tenha uma licença e eles são adicionados a um grupo em que a política de nomen por nomeação é imposta. O relatório sinaliza para você que eles precisam de uma licença.

## <a name="related-articles"></a>Artigos relacionados

[Saiba mais sobre os Grupos do Microsoft 365](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[Atualizar listas de distribuição para Grupos do Microsoft 365](../manage/upgrade-distribution-lists.md)

[Gerenciar grupos do Microsoft 365 com o PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell)

[Limites do SharePoint Online](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)
