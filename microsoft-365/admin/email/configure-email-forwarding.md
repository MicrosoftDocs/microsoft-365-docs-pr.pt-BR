---
title: Configurar encaminhamento de email
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ab5eb117-0f22-4fa7-a662-3a6bdb0add74
description: O encaminhamento de email permite encaminhar mensagens de email enviadas para uma caixa de correio de usuário Microsoft 365 para outra caixa de correio dentro ou fora da sua organização.
ms.openlocfilehash: 1d16a44749b51b582b7198cb331edf7faf3cf1f8
ms.sourcegitcommit: 4bcac4cb4f9399ebbd7c8cff0abb4d6ecedb731e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/28/2021
ms.locfileid: "52698911"
---
# <a name="configure-email-forwarding-in-microsoft-365"></a>Configurar o encaminhamento de email em Microsoft 365

Como administrador de uma organização, você pode ter requisitos da empresa para configurar o encaminhamento de email para a caixa de correio de um usuário. O encaminhamento de email permite encaminhar mensagens de email enviadas para a caixa de correio de um usuário para a caixa de correio de outro usuário dentro ou fora de sua organização.

> [!IMPORTANT]
> Você pode usar políticas de filtro de spam de saída para controlar o encaminhamento automático para destinatários externos. Para obter mais informações, consulte [Control automatic external email forwarding in Microsoft 365](/microsoft-365/security/office-365-security/external-email-forwarding?view=o365-worldwide&preserve-view=true#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls).

## <a name="configure-email-forwarding"></a>Configurar encaminhamento de email

Antes de configurar o encaminhamento de email, observe o seguinte:

- Permitir que mensagens encaminhadas automaticamente sejam enviadas para pessoas no domínio remoto. Consulte [Gerenciar domínios remotos](/exchange/mail-flow-best-practices/remote-domains/manage-remote-domains) para obter detalhes.

- Depois de configurar o encaminhamento de email, somente **os** novos emails enviados para a caixa  *de*  correio da caixa de correio serão encaminhados.

- O encaminhamento de email exige que  *a conta de*  a partir tenha uma licença. Se você estiver configurando o encaminhamento de email porque o usuário deixou sua organização, outra opção é converter sua caixa de correio [em uma caixa de correio compartilhada.](convert-user-mailbox-to-shared-mailbox.md) Dessa forma, várias pessoas podem acessá-lo. No entanto, uma caixa de correio compartilhada não pode exceder 50 GB.

Você deve ser um administrador Exchange ou administrador global no Microsoft 365 para fazer essas etapas. Para obter mais informações, consulte o tópico [Sobre funções de administrador](../add-users/about-admin-roles.md).

1. No centro de administração, vá para a página **Usuários** \> **[Usuários ativos.](https://go.microsoft.com/fwlink/p/?linkid=834822)**

2. Selecione o nome do usuário cujo email você deseja encaminhar e abra a página de propriedades.

3. Na guia **Email,** selecione **Gerenciar encaminhamento de email**.

4. Na página de encaminhamento de email, selecione Encaminhar todos os **emails** enviados para essa caixa de correio, insira o endereço de encaminhamento e escolha se deseja manter uma cópia dos emails encaminhados. Se você não vir essa opção, certifique-se de que uma licença seja atribuída à conta de usuário. Selecione **Salvar alterações**.

    **Para encaminhar para vários endereços de email,** você pode pedir ao usuário para configurar uma regra Outlook encaminhar para os endereços. Para saber mais, confira [Usar regras para encaminhar automaticamente mensagens](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).

     Ou, no centro de administração, crie um grupo de [distribuição,](add-user-or-contact-to-distribution-list.md)adicione os endereços a ele e, em seguida, defina o encaminhamento para apontar para [a](../setup/create-distribution-lists.md)DL usando as instruções neste artigo.

5. Não exclua a conta do usuário que está encaminhando ou remova sua licença!  Se você fizer isso, o encaminhamento de email será parado.

::: moniker-end

::: moniker range="o365-germany"

1. No centro de administração, vá para a página **Usuários** \> **[Usuários ativos.](https://go.microsoft.com/fwlink/p/?linkid=847686)**

2. Selecione o nome do usuário cujo email você deseja encaminhar para abrir a página de propriedades.

3. Expanda **configurações de** email e, em seguida, na seção **Encaminhamento de email,** selecione **Editar**.

4. Na página de encaminhamento de email, de definir a alternância como **On**, insira o endereço de encaminhamento e escolha se deseja manter uma cópia dos emails encaminhados. Se você não vir essa opção, certifique-se de que uma licença seja atribuída à conta de usuário. Selecione **Salvar**.

   **Para encaminhar para vários endereços de email,** você pode pedir ao usuário para configurar uma regra Outlook encaminhar para os endereços. Para saber mais, confira [Usar regras para encaminhar automaticamente mensagens](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).

   Ou, no centro de administração, crie um grupo de [distribuição,](add-user-or-contact-to-distribution-list.md)adicione os endereços a ele e, em seguida, defina o encaminhamento para apontar para [a](../setup/create-distribution-lists.md)DL usando as instruções neste artigo.

5. Não exclua a conta do usuário que está encaminhando ou remova sua licença!  Se você fizer isso, o encaminhamento de email será parado.

::: moniker-end

::: moniker range="o365-21vianet"

1. No centro de administração, vá para a página **Usuários** \> **[Usuários ativos.](https://go.microsoft.com/fwlink/p/?linkid=850628)**

2. Selecione o nome do usuário cujo email você deseja encaminhar para abrir a página de propriedades.

3. Expanda **configurações de** email e, em seguida, na seção **Encaminhamento de email,** selecione **Editar**.

4. Na página de encaminhamento de email, de definir a alternância como **On**, insira o endereço de encaminhamento e escolha se deseja manter uma cópia dos emails encaminhados. Se você não vir essa opção, certifique-se de que uma licença seja atribuída à conta de usuário. Selecione **Salvar**.

   **Para encaminhar para vários endereços de email,** você pode pedir ao usuário para configurar uma regra Outlook encaminhar para os endereços. Para saber mais, confira [Usar regras para encaminhar automaticamente mensagens](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).

   Ou, no centro de administração, crie um grupo de [distribuição,](add-user-or-contact-to-distribution-list.md)adicione os endereços a ele e, em seguida, defina o encaminhamento para apontar para [a](../setup/create-distribution-lists.md)DL usando as instruções neste artigo.

5. Não exclua a conta do usuário que está encaminhando ou remova sua licença! Se você fizer isso, o encaminhamento de email será parado.

::: moniker-end

## <a name="related-content"></a>Conteúdo relacionado 

[Criar uma caixa de correio compartilhada](../email/create-a-shared-mailbox.md) (artigo)\
[Enviar email de um endereço](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e) diferente (artigo)\
[Alterar um nome de usuário e um endereço de email](../add-users/change-a-user-name-and-email-address.md) (artigo)
