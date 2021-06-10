---
title: Proteger suas contas de administrador
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
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
ms.openlocfilehash: 0d687407fad1cec5da49dbc33ffeb84366f1c309
ms.sourcegitcommit: c5d1528559953c6db7dca1d5cb453e0aa3215f02
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2021
ms.locfileid: "51398236"
---
# <a name="protect-your-administrator-accounts"></a>Proteger suas contas de administrador

Como as contas de administrador vêm com privilégios elevados, elas são alvos valiosos para hackers e criminosos cibernéticos. Este artigo descreve:

- Como configurar uma conta de administrador adicional para emergências.
- Como proteger essas contas.

Ao se inscrever no Microsoft 365 e inserir suas informações, você se tornará automaticamente o administrador global. Um administrador global tem o controle final de contas de usuário e todas as outras configurações no centro de administração da Microsoft, mas há muitos tipos diferentes de contas de administrador com graus variáveis de acesso. Consulte [sobre funções de administrador](/office365/admin/add-users/about-admin-roles) para obter informações sobre os diferentes níveis de acesso para cada tipo de função de administrador.

## <a name="create-additional-admin-accounts"></a>Criar contas de administrador adicionais

Use contas de administrador somente para administração. Os administradores devem ter uma conta de usuário separada para uso regular de aplicativos Office e usar apenas sua conta administrativa quando necessário para gerenciar contas e dispositivos e enquanto trabalham em outras funções de administrador. Também é uma boa ideia remover a licença de Microsoft 365 das contas de administrador para que você não tenha que pagar por elas.

Você vai querer configurar pelo menos uma conta de administrador global adicional para dar acesso ao administrador a outro funcionário confiável. Você também pode criar contas de administrador separadas para gerenciamento de usuários (essa função é chamada **de Administrador de gerenciamento de usuário**). Para obter mais informações, consulte [sobre funções de administrador](/office365/admin/add-users/about-admin-roles).

Para criar contas de administrador adicionais:

 1. Vá para o <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">centro de administração</a> e escolha **Usuários** \> **Usuários ativos** na nav esquerda.

    ![Escolha Usuários e usuários ativos na nav esquerda](../media/Activeusers.png)

 2. Na página **Usuários ativos,** selecione **Adicionar** um usuário na parte superior da página e, no painel **Novo** usuário, insira o nome e outras informações.
 3. Expanda **a seção Funções** e escolha Administrador **Global** para dar a esse usuário acesso de administrador global. Você também pode escolher **Administrador personalizado** e escolher qualquer uma das funções exibidas.

    Insira um email alternativo na caixa **de texto Endereço de email** alternativo. Você pode usar esse endereço para recuperar suas informações de senha se for bloqueado. Para administradores globais, uma instrução de cobrança também será enviada para esse endereço.

    ![Escolha a função de administrador](../media/adminroles.png)

 4. Na seção **Licenças do produto,**  mova o seletor para Microsoft 365 Business **para Off** e o usuário Criar sem licença **de produto** para **On**.

    ![Escolha a licença do produto](../media/productlicense.png)

## <a name="create-an-emergency-admin-account"></a>Criar uma conta de administrador de emergência

Você também deve criar uma conta de backup que não esteja configurada com autenticação multifafatória (MFA) para que você não se bloqueie acidentalmente (por exemplo, se você perder o telefone que está usando como uma segunda forma de verificação). Certifique-se de que a senha dessa conta seja uma frase ou pelo menos 16 caracteres de comprimento. Isso é geralmente chamado de "conta de vidro quebrado".

## <a name="create-a-user-account-for-yourself"></a>Criar uma conta de usuário para si mesmo

Use sua conta de usuário para participar da colaboração com sua organização, incluindo a verificação de emails. Isso significa que suas credenciais de administrador podem ser semelhantes  *a Alice.Chávez <span></span> @Contoso.org* e sua conta de usuário regular pode ser semelhante *a Alice <span></span> @Contoso.com*.

Para criar uma nova conta de usuário:

1. Vá para o <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">centro de administração</a> e escolha **Usuários** \> **Usuários ativos** na nav esquerda.
2. Na página **Usuários ativos,** selecione **Adicionar** um usuário na parte superior da página e, no painel **Novo** usuário, insira o nome e outras informações.
3. Expanda **a seção Funções** e escolha Usuário **(sem acesso administrativo)**.
4. Na seção **Licenças do produto,** mova o seletor para **Microsoft 365 Business** para **On**.

## <a name="turn-on-security-defaults"></a>Ativar padrões de segurança

Os padrões de segurança ajudam a proteger sua organização contra ataques relacionados à identidade fornecendo configurações de segurança pré-configuradas que a Microsoft gerencia em nome da sua organização. Essas configurações incluem a habilitação da autenticação multifafação (MFA) para todos os administradores e contas de usuário. Para obter mais informações sobre os padrões de segurança e saber como habilita-los, consulte [Ativar padrões de segurança](m365-campaigns-conditional-access.md).

## <a name="additional-recommendations"></a>Recomendações adicionais

- Antes de usar contas de administrador, feche todas as sessões e aplicativos do navegador não relacionados, incluindo contas de email pessoais. Você também pode usar em janelas de navegador privadas ou anônimas.
- Depois de concluir tarefas de administrador, certifique-se de sair da sessão do navegador.
