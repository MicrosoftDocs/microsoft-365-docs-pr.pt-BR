---
title: Planejar a governança da organização e do ciclo de vida para grupos do Microsoft 365 e Microsoft Teams
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
description: Saber mais sobre as opções de governança do ciclo de vida para ferramentas de colaboração no Microsoft 365
ms.openlocfilehash: 4d779701d241fc7178ab759063be1b8cdf2e960c
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613015"
---
# <a name="plan-organization-and-lifecycle-governance-for-microsoft-365-groups-and-microsoft-teams"></a>Planejar a governança da organização e do ciclo de vida para grupos do Microsoft 365 e Microsoft Teams

Os grupos do Microsoft 365 têm um conjunto rico de ferramentas para implementar os recursos de governança necessários para sua organização. 

A seção a seguir descreve os recursos, recomenda as práticas recomendadas e fornece orientações para fazer as perguntas certas para determinar os requisitos de governança e como atender a eles.

## <a name="control-who-can-create-microsoft-365-groups"></a>Controlar quem pode criar grupos do Microsoft 365

Os grupos podem ser criados por usuários finais de vários pontos de extremidade, incluindo o Outlook, o SharePoint, o Teams e outros ambientes.

![desc de imagem](../media/04.png)

É altamente recomendável que o autoatendado capacite os proprietários do grupo e ajude os usuários a fazer seu trabalho com mais facilidade. Limitar a criação de grupos e equipes pode reduzir a produtividade dos usuários porque muitos serviços do Microsoft 365 exigem que os grupos sejam criados para que o serviço funcione.

Considere as seguintes opções de governança para a criação de grupos:

- Para limitar a expansão do grupo, use as políticas [de expiração de](microsoft-365-groups-expiration-policy.md) grupos para excluir automaticamente os grupos que não estão sendo usados.
- Limitar a criação de grupos a membros de grupos [de segurança com](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule) associação dinâmica contendo, por exemplo, todos os funcionários em tempo integral.
- Limite a criação de grupos a um grupo de segurança e exige que os usuários concluam o treinamento nas políticas de uso de grupo da sua organização para se tornarem membros do grupo de segurança.

Se você quiser limitar quem pode criar grupos, confira Gerenciar quem pode criar grupos do [Microsoft 365](manage-creation-of-groups.md) para obter informações sobre como configurar isso.

## <a name="group-delete-restore-and-archiving"></a>Exclusão, restauração e arquivamento de grupo

Quando um grupo do Microsoft 365 é excluído, por padrão, ele é mantido por 30 dias. Esse período de 30 dias é denominado "exclusão temporária" porque ainda é possível restaurar o grupo. Após 30 dias, o grupo e o conteúdo associado são excluídos permanentemente e não podem mais ser restaurados.

Se você tiver políticas de retenção para reter chat, arquivos ou emails, esses itens serão preservados depois que o grupo for excluído. Para [saber mais sobre políticas de retenção,](https://docs.microsoft.com/microsoft-365/compliance/retention-policies) confira.

Se você quiser excluir um grupo, mas preservar o conteúdo de um ou mais serviços conectados ao grupo, confira Grupos de arquivamento, equipes e [Yammer](end-life-cycle-groups-teams-sites-yammer.md) para saber mais.

## <a name="group-naming-policy"></a>Política de nomeação de grupo

Uma política de nomeação de grupos pode ajudá-lo a governá-los de duas maneiras:

- Uma política de nomeação de prefixo/sufixo pode ser usada para impor cadeias de caracteres fixas ou atributos do Azure AD no início ou no final de um nome de grupo e seu endereço de email associado. Ao fazer isso, você pode garantir a inclusão, por exemplo, de nomes de departamento ou regiões em nomes de grupo.
- Uma política de palavras bloqueadas pode garantir que determinadas palavras, como os nomes de executivos, não sejam usadas em nomes de grupo.

As políticas de nomeação são aplicadas quando grupos são criados a partir de qualquer um dos serviços conectados ao grupo.

Se você decidir usar políticas de nomeação para grupos, confira a política de nomen por grupos [do Microsoft 365.](groups-naming-policy.md)

## <a name="group-expiration-policy"></a>Política de expiração de grupo

Você pode especificar um período de expiração e qualquer grupo que atinja o final desse período, e não for renovado, será excluído. O período de expiração começa quando o grupo é criado ou na data em que foi renovado pela última vez.

Depois de definir os grupos para expirarem:
- Os proprietários do grupo são notificados para renovar o grupo à medida que a expiração se aproxima.
- Os grupos ativos são renovados automaticamente.
- Qualquer grupo que não for renovado será excluído.
- Qualquer grupo excluído pode ser restaurado dentro de 30 dias pelos proprietários do grupo ou pelo administrador.

As políticas de expiração são uma boa maneira de limitar a expansão do grupo, garantindo que os grupos que não estão mais em uso sejam excluídos. Se você quiser criar uma política de expiração de grupo, confira a Política de Expiração de Grupo do [Microsoft 365.](microsoft-365-groups-expiration-policy.md)

## <a name="related-topics"></a>Tópicos relacionados

[Planejamento de governança de colaboração passo a passo](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Criar seu plano de governança de colaboração](collaboration-governance-first.md)
