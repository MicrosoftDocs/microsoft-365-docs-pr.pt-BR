---
title: Etapa 1 - Impedir que um funcionário entre no Microsoft 365
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
- SPO_Content
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Impedir que um ex-funcionário entre e bloqueie o acesso aos Microsoft 365 serviços.
ms.openlocfilehash: 58b65a0a886460e8be01635c857433773cfc9059
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177112"
---
# <a name="step-1---prevent-a-former-employee-from-logging-in-and-block-access-to-microsoft-365-services"></a>Etapa 1 - Impedir que um ex-funcionário entre e bloqueie o acesso aos serviços Microsoft 365 serviços

Se você precisar impedir imediatamente o acesso de entrada de um usuário, você deve redefinir a senha. Nesta etapa, force uma saída do usuário do Microsoft 365.

> [!NOTE]
> Você precisa ser um administrador global para iniciar a saída para outros administradores. Para usuários que não são administradores, você pode usar um Administrador de Usuário ou um usuário do Administrador do Helpdesk para executar essa ação. [Saiba mais sobre as Funções de Administrador](about-admin-roles.md)

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.
2. Selecione a caixa ao lado do nome do usuário e selecione **Redefinir senha**.
3. Insira uma nova senha e selecione **Redefinir**. (Não envie para eles.)
4. Selecione o nome do usuário para ir para o  painel de propriedades e, na guia Conta, selecione **Sair de todas as sessões**.

Dentro de uma hora - ou depois de sair da página Microsoft 365 atual em que estão - eles são solicitados a entrar novamente. Um token de acesso é bom para uma hora, portanto, a linha do tempo depende de quanto tempo resta nesse token e se eles navegam para fora de sua página da Web atual.
  
> [!IMPORTANT]
> Se o usuário estiver em Outlook na Web, basta clicar em sua caixa de correio, ele pode não ser colocado para fora imediatamente. Assim que eles selecionam um OneDrive, ou atualizem o navegador, a saída é iniciada.
  
Para usar o PowerShell para sair imediatamente de um usuário, consulte o cmdlet [Revoke-AzureADUserAllRefreshToken.](/powershell/module/azuread/revoke-azureaduserallrefreshtoken)
  
Para saber mais sobre quanto tempo é preciso para excluir alguém do email, confira [O que você precisa saber sobre o encerramento da sessão de email de um funcionário](remove-former-employee-step-7.md#what-you-need-to-know-about-terminating-an-employees-email-session).

## <a name="block-a-former-employees-access-to-microsoft-365-services"></a>Bloquear o acesso de um ex-funcionário a serviços Microsoft 365 serviços

> [!IMPORTANT]
 > O bloqueio de uma conta pode levar até 24 horas para ter efeito. Se você precisar impedir imediatamente o acesso de entrada de um usuário, siga as etapas acima e redefinir a senha.

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.
2. Selecione o nome do funcionário que você deseja bloquear e, sob o nome do usuário, selecione o símbolo para **Bloquear este usuário**.
3. Selecione **Bloquear o usuário de entrar** e, em seguida, selecione **Salvar**.

## <a name="block-a-former-employees-access-to-email-exchange-online"></a>Bloquear o acesso de um ex-funcionário ao email (Exchange Online)

Se você tiver emails como parte da sua assinatura Microsoft 365, entre no centro de administração Exchange e siga estas etapas para impedir que seu ex-funcionário acesse seus emails.
  
1. Vá até o <a href="https://admin.exchange.microsoft.com/" target="_blank">Centro de administração do Exchange</a>.
2. No Centro de administração do Exchange, navegue até **Destinatários** \> **Caixas de Correio**.
3. Clique duas vezes no usuário e vá para **Gerenciar configurações de aplicativos de email** em **Aplicativos de email.** Desativar **o** controle deslizante para todas as opções; **Mobile (Exchange ActiveSync)**, **Outlook na Web**, Outlook **desktop (MAPI)**, **Exchange web services,** **POP3** e **IMAP**.
4. Selecione **Salvar**.
