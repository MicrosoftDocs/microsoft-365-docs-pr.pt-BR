---
title: Visão geral dos grupos do Office 365 para administradores
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
description: Saiba mais sobre os grupos do Office 365.
ms.openlocfilehash: 2257af16106e47b490beebd6d48e566bb3c07ca6
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/21/2020
ms.locfileid: "42894486"
---
# <a name="overview-of-office-365-groups-for-administrators"></a>Visão geral dos grupos do Office 365 para administradores

O Office 365 groups é o serviço de associação de base que orienta todo o trabalho em equipe no Microsoft 365. Com grupos do Office 365, você pode dar a um grupo de pessoas acesso a uma coleção de recursos de colaboração para que as pessoas compartilhem. Esses recursos incluem:

- Uma caixa de entrada do Outlook compartilhada
- Um calendário compartilhado
- Uma biblioteca de documentos do SharePoint
- Um planejador
- Power BI
- Yammer (se o grupo foi criado do Yammer)
- Uma equipe (se o grupo foi criado no Teams)
- Roteiro (se você tiver o Project para a Web)

Com um grupo do Office 365, você não precisa atribuir permissões manualmente a cada um desses recursos, pois adicionar pessoas ao grupo fornece automaticamente as permissões necessárias para as ferramentas que o grupo fornece.

Qualquer usuário do Office 365 pode criar um grupo, a menos que você [limite a criação de grupos a um conjunto específico de pessoas](manage-creation-of-groups.md). Observe que, se você limitar a criação de grupo, os usuários que não puderem criar grupos não poderão criar sites, planejadores ou equipes do SharePoint. Esses serviços exigem que as pessoas os criem para poder criar um grupo. Os usuários ainda podem participar de atividades de grupo, como a criação de tarefas no Planner ou o uso do teams chat, contanto que sejam membros do grupo.

Os grupos têm as seguintes funções:

- **Proprietários** -os proprietários do grupo podem adicionar ou remover membros e ter permissões exclusivas como a capacidade de excluir conversas da caixa de entrada compartilhada ou alterar configurações diferentes sobre o grupo. Os proprietários do grupo podem renomear o grupo, atualizar a descrição ou a imagem e muito mais.
- **Membros** -os membros podem acessar tudo no grupo, mas não podem alterar as configurações de grupo. Por padrão, os membros do grupo podem convidar convidados para ingressar no seu grupo, embora você possa [controlar essa configuração](manage-guest-access-in-groups.md).
- **Convidados** -grupos convidados são membros de fora da sua organização.

Somente administradores globais, administradores de usuários e administradores de grupos podem criar e gerenciar grupos no centro de administração do Microsoft 365. Não é possível ser um administrador delegado (por exemplo, um consultor que é administrador em nome de outra pessoa).

Como administrador, você pode:

- [Especificar quem pode criar grupos](manage-creation-of-groups.md)
- [Criar uma política de nomenclatura para grupos na sua organização](groups-naming-policy.md)
- [Escolha o domínio a ser usado ao criar um grupo](choose-domain-to-create-groups.md)
- [Gerenciar o acesso de convidados aos grupos](manage-guest-access-in-groups.md)
- [Recuperar um grupo excluído](restore-deleted-group.md) (dentro de 30 dias de exclusão)

Se preferir um modo mais automatizado de gerenciar o ciclo de vida de seus grupos do Office 365, você poderá usar as políticas de expiração para expirar grupos em um intervalo de tempo específico. Os proprietários do grupo receberão um email 30, 15 e 1 dia antes da expiração do grupo, permitindo que eles renovem facilmente o grupo se ainda forem necessários. Confira: [política de expiração de grupo do Office 365](office-365-groups-expiration-policy.md).

Você pode administrar seus grupos no centro de administração do Microsoft 365 ou [usando o PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell).

Se você tiver muitos usuários, como em uma grande empresa ou empresa, poderá ter muitos usuários que criam grupos para vários propósitos. É altamente recomendável revisar o [plano de governança nos grupos do Office 365](plan-for-groups-governance.md) para obter as práticas recomendadas.

## <a name="group-limits"></a>Limites de grupo

Os seguintes limites se aplicam aos grupos do Office 365:

|Máximo...|Valor|
|:---------|:----|
|Owners per group|100|
|Groups a user can create|250|
|Grupos que um administrador pode criar|Até o limite padrão de locatário do com 500 mil|
|Number of members |Mais de 1.000, embora apenas 1.000 possa acessar as conversas de grupo simultaneamente. <br>Os usuários podem notar atrasos ao acessar o calendário e conversas em grupos muito grandes no Outlook.|
|Número de grupos dos quais um usuário pode ser membro|1.000|
|Armazenamento de arquivos|1 terabyte + 10 GB por usuário inscrito + qualquer armazenamento adicional adquirido. Você pode adquirir uma quantidade ilimitada de armazenamento adicional.|
|Tamanho da caixa de correio de grupo|50 GB|

O número máximo padrão de grupos do Office 365 que uma organização do Office 365 pode ter é 500.000, mas pode ser aumentado por solicitação. Para obter mais informações sobre os limites de grupos do Office 365, consulte [office 365 groups-ajuda para administradores](https://support.office.com/article/3f780e8e-61aa-4287-830d-ff6209cbc192.aspx).

Gerenciar seus grupos do Office 365 é mais eficaz quando você tem informações acionáveis sobre o uso de grupos. O centro de administração do Microsoft 365 tem uma ferramenta de relatório que pode permitir que você veja coisas como o uso de armazenamento, quantos grupos ativos você tem e até mesmo como seus usuários estão usando os grupos. Confira: [Office 365 Reports no centro de administração](../activity-reports/office-365-groups.md) para obter mais informações.

## <a name="which-office-365-plans-include-groups"></a>Quais planos do Office 365 incluem grupos?

Qualquer assinatura do Office 365 que tenha o Exchange Online e o SharePoint Online oferecerá suporte a grupos. Isso inclui os planos Business Essentials e Business Premium e os planos Enterprise E1, E3 e e5. O grupo assume o licenciamento da pessoa que cria o grupo (também conhecido como o "organizador" do grupo). Contanto que o organizador tenha a licença adequada para qualquer recurso que você deseja que o grupo tenha, essa licença será envidará para o grupo.

> [!NOTE]
> Para obter mais detalhes sobre os planos e as famílias de serviços do Office 365, confira [Opções de plano do office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options)

Se você tiver um plano somente do Exchange, ainda poderá obter os recursos de caixa de entrada compartilhada e calendário compartilhado do grupo no Outlook, mas não obterá a biblioteca de documentos, o Planner ou qualquer um dos outros recursos.

Os grupos do Office 365 funcionam com o Azure Active Directory (AAD). Os recursos de grupos que você obtém dependem de qual assinatura do Azure Active Directory você tem e que licença (s) é atribuída ao organizador do grupo.

> [!IMPORTANT]
> Para todos os recursos de grupos, se você tiver uma assinatura do Azure AD Premium, os usuários poderão ingressar no grupo, estando ou não uma licença do AAD P1 atribuída a eles. O licenciamento não é imposto.
> Periodicamente, geraremos relatórios de uso que informam quais usuários estão faltando uma licença e precisam de um atribuído para eles serem compatíveis com os requisitos de licenciamento. Por exemplo, digamos que um usuário não tenha uma licença e que seja adicionado a um grupo em que a política de nomenclatura é imposta. O relatório será sinalizado para você de que eles precisam de uma licença.

## <a name="related-articles"></a>Artigos relacionados

[Saiba mais sobre grupos do Office 365](https://support.office.com/article/learn-about-office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[Atualizar listas de distribuição para grupos do Office 365](../manage/upgrade-distribution-lists.md)

[Gerenciar Grupos do Office 365 com o PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell)

[Limites do SharePoint Online](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)
