---
title: Política de expiração de grupos
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Saiba mais sobre as políticas de expiração de grupos do Microsoft 365.
ms.openlocfilehash: bda4bfbbef4e0d145c55b2a49b4d1203c6a7b1f0
ms.sourcegitcommit: 4f82fa7270e7ec6c6dd80329f28612e1f3289b22
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "46572134"
---
# <a name="microsoft-365-group-expiration-policy"></a>Política de expiração de grupo do Microsoft 365

Com o aumento no uso de grupos do Microsoft 365, os administradores e usuários precisam de uma maneira de limpar os grupos não utilizados. As políticas de expiração podem ajudar a remover grupos inativos do sistema e tornar as coisas mais claras.

Quando um grupo expira, todos os seus serviços associados (a caixa de correio, o Planner, o site do SharePoint, a equipe, etc.) também são excluídos.

Quando um grupo expira, ele é "excluído de forma reversível", o que significa que ele ainda pode ser recuperado por até 30 dias.

Os administradores podem especificar um período de expiração e qualquer grupo inativo que atinja o final do período, e que não seja renovado, será excluído. O período de expiração começa quando o grupo é criado ou na data da última renovar. Os proprietários de grupo receberão automaticamente um email antes da expiração, permitindo que eles renovem o grupo para outro intervalo de expiração. Os usuários do teams verão as notificações persistentes no Teams.

Os grupos que estão ativamente em uso são renovados automaticamente. Qualquer uma das ações a seguir irá renovar automaticamente um grupo:
- SharePoint – exibir, editar, baixar, mover, compartilhar ou carregar arquivos.
- Outlook-ingressar no grupo, ler ou gravar mensagem de grupo do grupo e como uma mensagem (Outlook na Web).
- Teams – visitando um canal do teams.

> [!IMPORTANT]
> Quando você altera a política de expiração, o serviço recalcula a data de expiração de cada grupo. Ele sempre inicia a contagem a partir da data em que o grupo foi criado e, em seguida, aplica a nova política de expiração.

É importante saber que a expiração está desativada por padrão. Os administradores terão que habilitá-lo para sua organização se desejarem usá-lo.

> [!NOTE]
> Configurar e usar a política de expiração para grupos do Microsoft 365 requer que você tenha, mas não necessariamente, atribui licenças do Azure AD Premium para os membros de todos os grupos aos quais a política de expiração é aplicada. Para obter mais informações, consulte [Getting Started with Azure Active Directory Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium).

## <a name="who-can-configure-and-use-the-microsoft-365-groups-expiration-policy"></a>Quem pode configurar e usar a política de expiração de grupos do Microsoft 365?

|Role|O que eles podem fazer|
|---------|---------|
|Administrador global (no Azure, administrador da empresa), administrador do usuário|Criar, ler, atualizar ou excluir as configurações da política de expiração do Microsoft 365 groups.|
|Usuário|Renovar ou [restaurar](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-restore-deleted) um grupo do Microsoft 365 de sua propriedade|

## <a name="how-to-set-the-expiration-policy"></a>Como definir a política de expiração

Conforme observado acima, a expiração é desativada por padrão. Um administrador precisará habilitar a política de expiração e definir as propriedades para que ela entre em vigor. Para habilitá-lo, vá para a expiração dos grupos **do Azure Active Directory (AAD)**  >  **Groups**  >  **Expiration**. Aqui você pode definir o tempo de vida do grupo padrão e especificar até que ponto de antecedência você deseja que a primeira e a segunda notificações de expiração acessem o proprietário do grupo.

O tempo de vida do grupo é especificado em dias e pode ser definido como 180, 365 ou como um valor personalizado que você especificar. O valor personalizado deve ser pelo menos 30 dias.

Se o grupo não tiver um proprietário, os emails de expiração serão direcionados para um administrador especificado.

Você pode definir a política para todos os seus grupos, apenas grupos selecionados ou desativá-lo completamente selecionando **nenhum**. Observe que, no momento, não é possível ter políticas diferentes para grupos diferentes.

![Captura de tela de configurações de expiração de grupos no Azure Active Directory](../../media/azure-groups-expiration-settings.png)

## <a name="how-expiration-and-renewal-work"></a>Como funciona a expiração e a renovação

A política de expiração funciona da seguinte maneira: 

- Cerca de um mês antes da expiração, o sistema verificará se houve alguma atividade de grupo desde que o grupo foi criado ou desde o início do ciclo de renovação atual.

- Se a atividade anterior for detectada, a data de vencimento será avançada no momento do número de dias especificado na política de expiração.

- Se a atividade anterior não for detectada, o sistema continuará a observar a atividade até a data de vencimento. Se a atividade for detectada, o sistema avançará a data de expiração pelo valor especificado nesse momento.

30 dias antes do vencimento do grupo, os proprietários do grupo (ou os endereços de email que você especificou para os grupos que não têm um proprietário) receberão um email, permitindo que eles renovem facilmente o grupo. Se ele não renová-lo, receberá outra renovação de email 15 dias antes da expiração. Se eles ainda não foram renovados, receberão uma notificação por email o dia antes da expiração. (Depois que o grupo for renovado, não serão enviados mais lembretes de email até 30 dias antes da nova data de validade.)

Os proprietários do grupo serão notificados por email. Se o grupo foi criado via Planner, SharePoint ou qualquer outro aplicativo, as notificações de expiração sempre serão fornecidas por email. Se o grupo foi criado via Teams, o proprietário do grupo receberá uma notificação para renovar através da seção atividade. Não é recomendável habilitar a expiração em um grupo se o proprietário do grupo não tiver um endereço de email válido.

Se, por algum motivo, nenhum dos proprietários ou administradores renovar o grupo antes de expirar, e a renovação automática não ocorrer devido ao grupo não atender aos requisitos para ser renovado automaticamente, o administrador ainda poderá restaurar o grupo por até 30 dias após a expiração. Para obter detalhes, consulte: [restaurar um grupo do Microsoft 365 excluído](https://docs.microsoft.com/microsoft-365/admin/create-groups/restore-deleted-group).

## <a name="how-expiry-works-with-retention-policies"></a>Como a expiração funciona com políticas de retenção

Se você tiver a política de retenção de configuração no centro de conformidade e segurança para grupos, a política de expiração funcionará perfeitamente com a política de retenção. Quando um grupo expira, as conversas do grupo na caixa de correio e os arquivos no site do grupo são mantidos no contêiner de retenção para o número específico de dias definido na política de retenção. No entanto, os usuários não verão o grupo ou seu conteúdo após a expiração.

## <a name="related-articles"></a>Artigos relacionados

[Visão geral de políticas de retenção](https://docs.microsoft.com/microsoft-365/compliance/retention-policies)

[Atribuir um novo proprietário a um grupo órfão](https://support.microsoft.com/office/86bb3db6-8857-45d1-95c8-f6d540e45732)

[Configurar a validade de grupos do Microsoft 365](https://docs.microsoft.com/azure/active-directory/active-directory-groups-lifecycle-azure-portal)

[Renovação automática baseada na atividade](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-lifecycle)
