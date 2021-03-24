---
title: Política de expiração de grupo do Microsoft 365
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
description: Saiba mais sobre políticas de expiração de grupos do Microsoft 365.
ms.openlocfilehash: 65a746751cd523a5dadce3eca573e6a9bfce0166
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51052297"
---
# <a name="microsoft-365-group-expiration-policy"></a>Política de expiração de grupo do Microsoft 365

Com o aumento do uso de grupos do Microsoft 365 e do Microsoft Teams, os administradores e usuários precisam de uma maneira de limpar grupos e equipes nãousados. Uma política de expiração de grupos do Microsoft 365 pode ajudar a remover grupos inativos do sistema e tornar as coisas mais limpas.

Quando um grupo expira, todos os seus serviços associados (caixa de correio, Planner, site do SharePoint, equipe etc.) também são excluídos.

Quando um grupo expira, ele é "excluído suavemente" o que significa que ele ainda pode ser recuperado por até 30 dias.

Os administradores podem especificar um período de expiração e qualquer grupo inativo que atingir o final desse período e não for renovado, será excluído. (Isso inclui equipes arquivadas.) O período de expiração começa quando o grupo é criado ou na data em que foi renovado pela última vez. Os proprietários do grupo serão enviados automaticamente um email antes da expiração que permite que eles renovem o grupo para outro intervalo de expiração. Os usuários do Teams verão notificações persistentes no Teams.

Os grupos que estão em uso ativamente são renovados automaticamente. Qualquer uma das seguintes ações renovará automaticamente um grupo:
- SharePoint - exibir, editar, baixar, mover, compartilhar ou carregar arquivos. (A exibição de uma página do SharePoint não conta como uma ação para renovação automática.)
- Outlook - ingressar em grupo, ler ou gravar mensagem de grupo do grupo e como uma mensagem (Outlook na Web).
- Teams - visitando um canal do Teams.

Observe que a única atividade do Yammer que disparará uma renovação automática de grupo é o carregamento de um documento no SharePoint dentro da comunidade.

> [!IMPORTANT]
> Quando você altera a política de expiração, o serviço recalcula a data de expiração para cada grupo. Ele sempre começa a contar a partir da data em que o grupo foi criado e aplica a nova política de expiração.

É importante saber que a expiração está desligada por padrão. Os administradores devem habilita-lo para sua organização se quiserem usá-lo.

> [!NOTE]
> Configurar e usar a política de expiração para grupos do Microsoft 365 exige que você possua, mas não necessariamente atribua licenças do Azure AD Premium para os membros de todos os grupos aos quais a política de expiração é aplicada. Para obter mais informações, [consulte Getting started with Azure Active Directory Premium](/azure/active-directory/active-directory-get-started-premium).

## <a name="who-can-configure-and-use-the-microsoft-365-groups-expiration-policy"></a>Quem pode configurar e usar a política de expiração de grupos do Microsoft 365?

|Role|O que eles podem fazer|
|---------|---------|
|Administrador global do Office 365 (no Azure, o administrador da empresa), Administrador do usuário|Crie, leia, atualize ou exclua as configurações de política de expiração de grupos do Microsoft 365.|
|User|Renovar ou [restaurar](/azure/active-directory/users-groups-roles/groups-restore-deleted) um grupo do Microsoft 365 que eles próprios|

## <a name="how-to-set-the-expiration-policy"></a>Como definir a política de expiração

Conforme mencionado acima, a expiração é desligada por padrão. Um administrador terá que habilitar a política de expiração e definir as propriedades para que ela entre em vigor. Para habilita-lo, vá para Expiração de Grupos do **Azure Active Directory**  >    >  . Aqui, você pode definir o tempo de vida do grupo padrão e especificar com que antecedência deseja que as primeiras e segunda notificações de expiração vão para o proprietário do grupo.

O tempo de vida do grupo é especificado em dias e pode ser definido como 180, 365 ou como um valor personalizado especificado. O valor personalizado deve ser pelo menos 30 dias.

Se o grupo não tiver um proprietário, os emails de expiração serão para o administrador especificado.

Você pode definir a política para todos os seus grupos, somente grupos selecionados ou a desativar completamente selecionando **Nenhum**. Observe que atualmente você não pode ter políticas diferentes para grupos diferentes.

![Captura de tela das configurações de expiração de grupos no Azure Active Directory](../media/azure-groups-expiration-settings.png)

## <a name="how-expiry-works-with-the-retention-policy"></a>Como a expiração funciona com a política de retenção

Se você tiver criado uma política de retenção para grupos no Centro de Segurança e Conformidade, a política de expiração funcionará perfeitamente com a política de retenção. Quando um grupo expira, as conversas e arquivos de caixa de correio do grupo no site do grupo são mantidos no contêiner de retenção para o número específico de dias definido na política de retenção. No entanto, os usuários não verão o grupo ou seu conteúdo após a expiração.

## <a name="how-and-when-a-group-owner-learns-if-their-groups-are-going-to-expire"></a>Como e quando um proprietário de grupo aprenderá se seus grupos vão expirar

Os proprietários do grupo só serão notificados por email. Se o grupo foi criado por meio do Planner, do SharePoint ou de qualquer outro aplicativo, as notificações de expiração sempre virão por email. Se o grupo foi criado por meio do Teams, o proprietário do grupo receberá uma notificação para renovar por meio da seção atividade. Não é recomendável que você habilita a expiração em um grupo se o proprietário do grupo não tiver um endereço de email válido.

Trinta dias antes do grupo expirar, os proprietários do grupo (ou os endereços de email especificados para grupos que não têm um proprietário) receberão um email permitindo que eles renovem facilmente o grupo. Se eles não o renovarem, receberão outro email de renovação 15 dias antes da expiração. Se ainda não a renovarem, receberão mais uma notificação de email no dia anterior à expiração.

Se, por algum motivo, nenhum dos proprietários ou administradores renovar o grupo antes de expirar, o administrador ainda poderá restaurar o grupo por até 30 dias após a expiração. Para obter detalhes, consulte: Restaurar um grupo excluído do [Microsoft 365](https://support.office.com/article/restore-a-deleted-office-365-group-b7c66b59-657a-4e1a-8aa0-8163b1f4eb54).

## <a name="archiving-group-contents"></a>Conteúdo do grupo de arquivamento

Se você tiver um grupo que não planeja mais usar, mas deseja manter seu conteúdo, consulte [Arquivar grupos,](end-life-cycle-groups-teams-sites-yammer.md) equipes e Yammer para obter informações sobre como exportar informações dos diferentes serviços de grupos.

## <a name="related-topics"></a>Tópicos relacionados

[Planejamento de governança de colaboração passo a passo](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Criar seu plano de governança de colaboração](collaboration-governance-first.md)

[Visão geral de políticas de retenção](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423)

[Atribuir um novo proprietário a um grupo órfão](https://support.office.com/article/86bb3db6-8857-45d1-95c8-f6d540e45732)

[Configurar a expiração de grupos do Microsoft 365](/azure/active-directory/active-directory-groups-lifecycle-azure-portal)