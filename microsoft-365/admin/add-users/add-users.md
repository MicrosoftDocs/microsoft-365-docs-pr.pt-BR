---
title: Adicionar usuários e atribuir licenças
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365_Setup
- Adm_O365_TOC
ms.custom:
- okr_smb
- AdminSurgePortfolio
- manage_licenses
search.appverid:
- MET150
description: Saiba como adicionar usuários e atribuir licenças ao Microsoft 365 ao mesmo tempo.
ms.date: 07/01/2020
ms.openlocfilehash: 412774c9786abc01e94c5a350871f9d34586cce4
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114148"
---
# <a name="add-users-and-assign-licenses-at-the-same-time"></a>Adicionar usuários e atribuir licenças ao mesmo tempo

::: moniker range="o365-21vianet"

> [!NOTE]
> O centro de administração está mudando. Se a sua experiência não corresponder aos detalhes apresentados aqui, consulte [Sobre o novo centro de administração do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).

::: moniker-end

As pessoas da sua equipe precisam de uma conta de usuário para poder entrar e acessar o [Microsoft 365 para empresas.](https://www.microsoft.com/microsoft-365/business) A maneira mais fácil de adicionar contas de usuário é adicioná-las uma de cada vez no centro de administração do Microsoft 365. Depois que você fizer essa etapa, os usuários terão licenças do Microsoft 365, credenciais de entrada e caixas de correio do Microsoft 365.

## <a name="before-you-begin"></a>Antes de começar

Você deve ser um administrador global, de licença ou de usuário para adicionar usuários e atribuir licenças. Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).

## <a name="watch-add-users-in-the-admin-center"></a>Assista: Adicionar usuários no centro de administração

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfN?autoplay=false]

> [!NOTE]
> As etapas usadas no vídeo mostram um ponto de partida diferente para adicionar usuários, mas as etapas restantes são as mesmas do procedimento a seguir.

## <a name="add-users-one-at-a-time"></a>Adicionar usuários um de cada vez

::: moniker range="o365-worldwide"

1. Vá para o centro de administração do<https://admin.microsoft.com>.
2. Vá para **usuários** > **ativos e** selecione Adicionar um **usuário.**
3. In the **Set up the basics** pane, fill in the basic user information, and then select **Next**.
    - **Nome** Preencha o nome e o sobrenome, o nome de exibição e o nome de usuário.
    - **Domínio** Escolha o domínio da conta do usuário. Por exemplo, se o nome de usuário do usuário for Henrique e o domínio for contoso.com, ele entrará usando o jakob@contoso.com.
    - **Configurações de senha** Escolha usar a senha gerado automaticamente ou para criar sua própria senha forte para o usuário.
    - O usuário deve alterar a senha após 90 dias. Ou você pode optar por **Exigir que esse usuário altere a senha ao entrar pela primeira vez.**
    - Escolha se deseja enviar a senha por email quando o usuário for adicionado.
4. No painel **Atribuir licenças de** produto, selecione o local e a licença apropriada para o usuário. Caso não haja licenças disponíveis, você pode comprar mais licenças e adicionar usuários. Expanda **Aplicativos** e selecione ou desmarque aplicativos para limitar os aplicativos para os quais o usuário tem uma licença. Selecione **Avançar**.
5. No painel **Configurações opcionais,** **expanda Funções** para tornar esse usuário um administrador. Expanda **as informações do** Perfil para adicionar informações adicionais sobre o usuário.
6. Select **Next**, review your new user's settings, make any changes you like, then select **Finish adding**, then **Close**.

::: moniker-end

::: moniker range="o365-germany"

1. Vá para o centro de administração do<https://portal.office.de/adminportal>.
2. Vá para **usuários** > **ativos e** selecione Adicionar um **usuário.**
3. No painel **Novo** usuário, preencha as informações a seguir. Quando terminar, selecione **Adicionar**.
    - **Nome** Preencha o nome, o sobrenome, o nome para exibição e o nome de usuário.
    - **Domínio** Por exemplo, se o nome de usuário do usuário for Contoso.com, ele entrará digitando jakob@contoso.com.
    - **Informações de contato** Expanda para preencher um número de telefone celular, endereço e assim por diante.
    - **Senha** Use a senha gerado automaticamente ou expanda para especificar uma senha forte para o usuário. Eles devem alterar a senha após 90 dias. Além disso, você pode optar por **Permitir que esse usuário altere a senha quando entrar pela primeira vez**.
    - **Funções** Expanda, caso precise tornar esse usuário um administrador.
    - **Licenças de produto** Expanda esta seção e escolha a licença apropriada. Caso não haja licenças disponíveis, você pode comprar mais licenças e adicionar usuários.

::: moniker-end

::: moniker range="o365-21vianet"

1. Vá para o centro de administração do<https://portal.partner.microsoftonline.cn>.
2. Vá para **usuários** > **ativos e** selecione Adicionar um **usuário.**
3. No painel **Novo** usuário, preencha as informações a seguir. Quando terminar, selecione **Adicionar**.
    - **Nome** Preencha o nome, o sobrenome, o nome para exibição e o nome de usuário.
    - **Domínio** Por exemplo, se o nome de usuário do usuário for Contoso.com, ele entrará digitando jakob@contoso.com.
    - **Informações de contato** Expanda para preencher um número de telefone celular, endereço e assim por diante.
    - **Senha** Use a senha gerado automaticamente ou expanda para especificar uma senha forte para o usuário. Eles devem alterar a senha após 90 dias. Além disso, você pode optar por **Permitir que esse usuário altere a senha quando entrar pela primeira vez**.
    - **Funções** Expanda, caso precise tornar esse usuário um administrador.
    - **Licenças de produto** Expanda esta seção e escolha a licença apropriada. Caso não haja licenças disponíveis, você pode comprar mais licenças e adicionar usuários.

::: moniker-end

## <a name="add-multiple-users-at-the-same-time"></a>Adicionar vários usuários ao mesmo tempo

Você pode usar qualquer um dos métodos a seguir para adicionar vários usuários ao mesmo tempo:

- **Usar uma planilha para adicionar pessoas em massa.** Consulte [Adicionar vários usuários ao mesmo tempo.](https://docs.microsoft.com/microsoft-365/enterprise/add-several-users-at-the-same-time)
- **Automatizar a adição de contas e a atribuição de licenças.** Confira [Criar contas de usuário com o Microsoft 365 PowerShell.](https://docs.microsoft.com/microsoft-365/enterprise/create-user-accounts-with-microsoft-365-powershell) Escolha esse método se você já estiver familiarizado com o uso de cmdlets do Windows PowerShell.
- **Usando o ActiveDirectory?** [Configurar a sincronização de diretórios para o Microsoft 365.](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization) Use a ferramenta Azure AD Connect para replicar contas de usuário do Active Directory (e outros objetos do Active Directory) no Microsoft 365. A sincronização apenas adiciona as contas de usuário. Você deve atribuir licenças aos usuários sincronizados antes que eles possam usar email e outros aplicativos do Office.
- **Migrando do Exchange?** Veja [maneiras de migrar várias contas de email para o Office 365.](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration) Ao migrar várias caixas de correio para o Microsoft 365 usando o método de transferência, em estágios ou híbrido do Exchange, você adiciona usuários automaticamente como parte da migração. A migração apenas adiciona as contas de usuário. Você deve atribuir licenças aos usuários antes que eles possam usar email e outros aplicativos do Office. Se você não atribuir uma licença a um usuário, sua caixa de correio será desabilitada após um período de carência de 30 dias. Saiba como atribuir [licenças a usuários no](../manage/assign-licenses-to-users.md) Centro de administração do Microsoft 365.

## <a name="next-steps"></a>Próximas etapas

Depois de adicionar um usuário, você recebe uma notificação por email da Microsoft. O email contém a ID de usuário e a senha da pessoa para que ela possa entrar no Microsoft 365. Use seu processo normal para comunicar as novas senhas. Compartilhe [](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f) o guia de início rápido de funcionários com seus novos usuários para configurar coisas, como baixar e instalar aplicativos do Office em um PC ou [Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) e como configurar aplicativos do Office e [email](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f)em um dispositivo móvel.

## <a name="related-content"></a>Conteúdo relacionado

[Adicionar um novo funcionário ao Microsoft 365](add-new-employee.md) (artigo)\
[Adicionar vários usuários ao mesmo tempo ao Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/add-several-users-at-the-same-time) (artigo)\
[Restaurar um usuário no Microsoft 365](restore-user.md) (artigo)\
[Atribuir licenças a usuários](../manage/assign-licenses-to-users.md) (artigo)\
[Excluir um usuário da sua organização](delete-a-user.md) (artigo)
