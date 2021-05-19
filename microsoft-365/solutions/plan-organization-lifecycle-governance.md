---
title: Planejar a governança da organização e do ciclo de vida para Microsoft 365 grupos e Microsoft Teams
ms.reviewer: arvaradh
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
description: Incline-se sobre as opções de governança do ciclo de vida para ferramentas de colaboração Microsoft 365
ms.openlocfilehash: 7d88618b75ef731bf38df029970efdc05f3eea5a
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538814"
---
# <a name="plan-organization-and-lifecycle-governance-for-microsoft-365-groups-and-microsoft-teams"></a>Planejar a governança da organização e do ciclo de vida para Microsoft 365 grupos e Microsoft Teams

Microsoft 365 grupos têm um conjunto rico de ferramentas para implementar os recursos de governança necessários para sua organização. 

A seção a seguir descreve os recursos, recomenda as práticas recomendadas e fornece orientações para fazer as perguntas corretas para determinar os requisitos de governança e como atender a eles.

## <a name="control-who-can-create-microsoft-365-groups"></a>Controlar quem pode criar Microsoft 365 grupos

Os grupos podem ser criados por usuários finais de vários pontos de extremidade, incluindo Outlook, SharePoint, Teams e outros ambientes.

![desc de imagem](../media/04.png)

É altamente recomendável que o autoatendam capacitar os proprietários do grupo e ajudar os usuários a fazer seu trabalho com mais facilidade. Limitar a criação de grupo e equipe pode reduzir a produtividade dos usuários porque muitos serviços Microsoft 365 exigem que os grupos sejam criados para que o serviço funcione.

Considere as seguintes opções de governança para criação de grupos:

- Para limitar a expansão de grupo, use políticas [de](microsoft-365-groups-expiration-policy.md) expiração de grupos para excluir automaticamente grupos que não estão sendo usados.
- Limitar a criação de grupo aos membros de um grupo [de segurança](/azure/active-directory/users-groups-roles/groups-create-rule) com associação dinâmica contendo, por exemplo, todos os funcionários em tempo integral.
- Limite a criação de grupo a um grupo de segurança e exige que os usuários concluam o treinamento nas políticas de uso de grupo da sua organização para se tornarem membros do grupo de segurança.

Se você quiser limitar quem pode criar grupos, consulte Gerenciar quem pode criar Microsoft 365 [grupos](manage-creation-of-groups.md) para obter informações sobre como configurar isso.

## <a name="group-delete-restore-and-archiving"></a>Excluir, restaurar e arquivar grupos

Quando um Microsoft 365 grupo é excluído, por padrão, ele é mantido por 30 dias. Esse período de 30 dias é denominado "exclusão temporária" porque ainda é possível restaurar o grupo. Após 30 dias, o grupo e o conteúdo associado são excluídos permanentemente e não podem mais ser restaurados.

Se você tiver políticas de retenção no local para reter chat, arquivos ou email, esses itens serão preservados depois que o grupo for excluído. Consulte [Saiba mais sobre políticas de retenção](../compliance/retention.md) para obter detalhes.

Se você quiser excluir um grupo, mas preservar o conteúdo de um ou mais serviços conectados ao grupo, consulte [Archive groups, teams e Yammer](end-life-cycle-groups-teams-sites-yammer.md) para obter informações.

## <a name="group-naming-policy"></a>Política de nomenis de grupo

Uma política de nomenrção de grupos pode ajudá-lo a governar grupos de duas maneiras:

- Uma política de nomenização de prefixo/sufixo pode ser usada para impor cadeias de caracteres fixas ou atributos do Azure AD no início ou no fim de um nome de grupo e seu endereço de email associado. Ao fazer isso, você pode garantir a inclusão, por exemplo, de nomes de departamentos ou regiões em nomes de grupo.
- Uma política de palavras bloqueadas pode garantir que determinadas palavras, como nomes de executivos, não sejam usadas em nomes de grupo.

As políticas de nomenização são aplicadas quando os grupos são criados a partir de qualquer um dos serviços conectados ao grupo.

Se você decidir usar políticas de nomenização para grupos, [consulte Microsoft 365 política de nomenis de grupos.](groups-naming-policy.md)

## <a name="group-expiration-policy"></a>Política de expiração de grupo

Você pode especificar um período de expiração e qualquer grupo que atingir o final desse período e não for renovado, será excluído. O período de expiração começa quando o grupo é criado ou na data em que foi renovado pela última vez.

Depois de definir grupos para expirar:
- Os proprietários do grupo são notificados para renovar o grupo à medida que a expiração se aproxima.
- Os grupos ativos são renovados automaticamente.
- Qualquer grupo que não for renovado será excluído.
- Qualquer grupo excluído pode ser restaurado dentro de 30 dias pelos proprietários do grupo ou pelo administrador.

As políticas de expiração são uma boa maneira de limitar a expansão de grupo, garantindo que os grupos que não estão mais em uso sejam excluídos. Se você quiser criar uma política de expiração de grupo, [consulte Microsoft 365 Política de Expiração de Grupo.](microsoft-365-groups-expiration-policy.md)

## <a name="related-topics"></a>Tópicos relacionados

[Planejamento de governança de colaboração passo a passo](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Criar seu plano de governança de colaboração](collaboration-governance-first.md)

[Remover um ex-funcionário e proteger dados](/microsoft-365/admin/add-users/remove-former-employee)
