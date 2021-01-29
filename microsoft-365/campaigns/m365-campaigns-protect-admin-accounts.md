---
title: Proteger suas contas de administrador
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
description: Saiba como configurar e proteger suas contas de administrador.
ms.openlocfilehash: 73e4b69571b1e1d0a4d1585224fe256ff135c40a
ms.sourcegitcommit: 1b30ac6e05906c8a014b1fed33fc71e1821f6ad2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2021
ms.locfileid: "50044483"
---
# <a name="protect-your-administrator-accounts"></a>Proteger suas contas de administrador

Como as contas de administrador vêm com privilégios elevados, elas são alvos valiosos para hackers e ciberataques. Este artigo descreve:

- Como configurar uma conta de administrador adicional para emergências.
- Como proteger essas contas.

Ao se inscrever no Microsoft 365 e inserir suas informações, você se tornará automaticamente o administrador global. Um administrador global tem o controle final das contas de usuário e todas as outras configurações no centro de administração da Microsoft, mas há muitos tipos diferentes de contas de administrador com graus variáveis de acesso. Consulte [as funções de administrador](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) para obter informações sobre os diferentes níveis de acesso para cada tipo de função de administrador.

## <a name="create-additional-admin-accounts"></a>Criar contas de administrador adicionais

Use contas de administrador somente para administração. Os administradores devem ter uma conta de usuário separada para uso regular de aplicativos do Office e usar sua conta administrativa somente quando necessário para gerenciar contas e dispositivos e enquanto trabalham em outras funções de administrador. Também é uma boa ideia remover a licença do Microsoft 365 das contas de administrador para que você não tenha que pagar por elas.

Você vai querer configurar pelo menos uma conta de administrador global adicional para dar acesso de administrador a outro funcionário confiável. Você também pode criar contas de administrador separadas para gerenciamento de usuários (essa função é chamada **de Administrador de gerenciamento de usuários).** Para obter mais informações, consulte [as funções de administrador.](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)

Para criar contas de administrador adicionais:

 1. Vá para o <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">centro de administração</a> e escolha **Usuários** \> **Ativos na** entrada esquerda.

    ![Choose Users and then Active users in the left nav](../media/Activeusers.png)

 2. Na página **Usuários ativos,** selecione Adicionar um usuário na  parte superior da página e, no painel Novo usuário, insira o nome e outras informações. 
 3. Expanda **a seção** Funções e escolha Administrador **global** para dar a esse usuário acesso de administrador global. Você também pode escolher **Administrador personalizado** e escolher qualquer uma das funções exibidas.

    Insira um email alternativo na caixa **de texto Endereço de email** alternativo. Você pode usar esse endereço para recuperar suas informações de senha se for bloqueado. Para administradores globais, um extrato de cobrança também será enviado para esse endereço.

    ![Escolher a função de administrador](../media/adminroles.png)

 4. Na seção **Licenças de produto,** mova o seletor  do **Microsoft 365 Business** para Desligado e o usuário Criar sem licença de produto **para** **On**.

    ![Escolher a licença do produto](../media/productlicense.png)

## <a name="create-an-emergency-admin-account"></a>Criar uma conta de administrador de emergência

Você também deve criar uma conta de backup que não esteja configurada com a autenticação multifatória (MFA) para que você não se bloqueie acidentalmente (por exemplo, se você perder o telefone que está usando como uma segunda forma de verificação). Certifique-se de que a senha dessa conta seja uma frase ou pelo menos 16 caracteres. Isso geralmente é conhecido como uma "conta de vidro de vidro".

## <a name="create-a-user-account-for-yourself"></a>Criar uma conta de usuário para si mesmo

Use sua conta de usuário para participar da colaboração com sua organização, incluindo a verificação de emails. Isso significa que suas credenciais de administrador podem ser semelhantes a  *Alice.Contoso.org <span></span> e* sua conta de usuário normal pode ser semelhante a *Alice <span></span> @Contoso.com*.

Para criar uma nova conta de usuário:

1. Vá para o <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">centro de administração</a> e escolha **Usuários** \> **Ativos na** entrada esquerda.
2. Na página **Usuários ativos,** selecione Adicionar um usuário na  parte superior da página e, no painel Novo usuário, insira o nome e outras informações. 
3. Expanda **a seção** Funções e escolha Usuário **(sem acesso administrativo).**
4. Na seção **Licenças de produto,** mova o seletor do **Microsoft 365 Business** para **On.**

## <a name="register-each-of-these-accounts-for-multi-factor-authentication"></a>Registre cada uma dessas contas para autenticação multifa factor

Certifique-se de que essas contas estão usando [a autenticação multifator.](m365-campaigns-multifactor-authenication.md)

## <a name="additional-recommendations"></a>Recomendações adicionais

- Certifique-se de que as contas de administrador também estão configuradas para autenticação multifa factor. Mostraremos como fazer isso em Configurar políticas de [acesso condicional.](m365-campaigns-conditional-access.md)
- Antes de usar contas de administrador, feche todas as sessões de navegador e aplicativos não relacionados, incluindo contas de email pessoais. Você também pode usar em janelas de navegador privadas ou anônimas.
- Depois de concluir as tarefas de administrador, saia da sessão do navegador.
