---
title: Planejar a administração da organização e do ciclo de vida de grupos do Microsoft 365 e do Microsoft Teams
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
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Saiba mais sobre as opções de governança de ciclo de vida para ferramentas de colaboração no Microsoft 365
ms.openlocfilehash: 2a2f14bf439ec69e4609d22783fb14d1d5cb8e70
ms.sourcegitcommit: 66f1f430b3dcae5f46cb362a32d6fb7da4cff5c1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662461"
---
# <a name="plan-organization-and-lifecycle-governance-for-microsoft-365-groups-and-microsoft-teams"></a>Planejar a administração da organização e do ciclo de vida de grupos do Microsoft 365 e do Microsoft Teams

O Microsoft 365 groups tem um conjunto avançado de ferramentas para implementar os recursos de governança necessários para sua organização. 

A seção a seguir descreve os recursos, recomenda as práticas recomendadas e fornece orientações para fazer as perguntas certas para determinar os requisitos de governança e como atendê-las.

## <a name="control-who-can-create-microsoft-365-groups"></a>Controlar quem pode criar grupos do Microsoft 365

Os grupos podem ser criados por usuários finais de vários pontos de extremidade, incluindo Outlook, SharePoint, equipes e outros ambientes.

![DESC de imagem](../media/04.png)

É altamente recomendável que o autoatendimento permita proprietários de grupo e ajude os usuários a realizar seu trabalho com mais facilidade. Limitar o grupo e a criação de equipe pode reduzir a produtividade dos usuários, pois muitos serviços do Microsoft 365 exigem que os grupos sejam criados para que o serviço funcione.

Considere as seguintes opções de governança para a criação de grupos:

- Para limitar a proliferação de grupo, use [as políticas de expiração de grupos](microsoft-365-groups-expiration-policy.md) para excluir automaticamente os grupos que não estão sendo usados.
- Limitar a criação de grupos aos membros de um grupo de [segurança com associação dinâmica](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule) contendo, por exemplo, todos os funcionários em tempo integral.
- Limitar a criação de grupos a um grupo de segurança e exigir que os usuários concluam o treinamento nas políticas de uso de grupos da sua organização para se tornarem membros do grupo de segurança.

Se quiser limitar quem pode criar grupos, confira [gerenciar quem pode criar grupos da Microsoft 365](manage-creation-of-groups.md) para obter informações sobre como configurar isso.

## <a name="group-delete-restore-and-archiving"></a>Exclusão, restauração e arquivamento de grupo

Quando um grupo do Microsoft 365 é excluído, por padrão, ele é mantido por 30 dias. Esse período de 30 dias é denominado "exclusão temporária" porque ainda é possível restaurar o grupo. Após 30 dias, o grupo e o conteúdo associado são excluídos permanentemente e não podem mais ser restaurados.

Se você tiver políticas de retenção in-loco para reter chat, arquivos ou email, esses itens serão preservados depois que o grupo for excluído. Consulte [saiba mais sobre políticas de retenção](https://docs.microsoft.com/microsoft-365/compliance/retention-policies) para obter detalhes.

Se você quiser excluir um grupo, mas preservar o conteúdo de um ou mais serviços conectados ao grupo, consulte [Archive Groups, Teams e Yammer](end-life-cycle-groups-teams-sites-yammer.md) para obter informações.

## <a name="group-naming-policy"></a>Política de nomeação de grupo

Uma política de nomenclatura de grupos pode ajudá-lo a controlar grupos de duas maneiras:

- Uma política de nomenclatura de prefixo/sufixo pode ser usada para impor cadeias de caracteres fixas ou atributos do Azure AD no início ou no final de um nome de grupo e seu endereço de email associado. Ao fazer isso, você pode garantir a inclusão de, por exemplo, nomes de departamentos ou regiões em nomes de grupo.
- Uma política de palavras bloqueadas pode garantir que determinadas palavras, como os nomes de executivos, não sejam usadas em nomes de grupo.

As políticas de nomenclatura são aplicadas quando os grupos são criados a partir de qualquer um dos serviços conectados ao grupo.

Se você decidir usar políticas de nomeação para grupos, consulte [política de nomenclatura de grupos do Microsoft 365](groups-naming-policy.md).

## <a name="group-expiration-policy"></a>Política de expiração de grupo

Você pode especificar um período de expiração e qualquer grupo que atinja o final desse período, e que não seja renovado, será excluído. O período de expiração começa quando o grupo é criado ou na data da última renovar.

Depois de definir os grupos para expirar:
- Os proprietários do grupo são notificados a renovar o grupo como a expiração é próxima.
- Os grupos ativos são renovados automaticamente.
- Qualquer grupo não renovado é excluído.
- Qualquer grupo excluído pode ser restaurado dentro de 30 dias pelos proprietários do grupo ou pelo administrador.

As políticas de expiração são uma boa maneira de limitar a proliferação de grupos, assegurando que os grupos que não estão mais em uso sejam excluídos. Se você deseja criar uma política de expiração de grupo, consulte [política de expiração de grupo do Microsoft 365](microsoft-365-groups-expiration-policy.md).
