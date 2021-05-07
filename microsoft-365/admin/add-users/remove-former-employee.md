---
title: Remover um ex-funcionário - Visão geral
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
description: Siga as etapas nesta solução para remover um ex-funcionário do Microsoft 365 e proteger os dados da sua organização.
ms.openlocfilehash: 4b4cf59fdce81b3098ee333095daa8e1af1cd5c5
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52241731"
---
# <a name="overview-remove-a-former-employee-and-secure-data"></a>Visão geral: remover um ex-funcionário e proteger dados

Uma pergunta que muitas vezes fazemos é: "O que devo fazer para proteger os dados e proteger o acesso quando um funcionário sai da minha organização?" Esta série de artigos explica como bloquear o acesso ao Microsoft 365, as etapas que você deve seguir para proteger seus dados e como permitir que outros funcionários acessem os dados.

Assista a um breve vídeo sobre como remover um funcionário. <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfR] 

Se você achou este vídeo útil, consulte as [séries completas de treinamento para pequenas empresas e as novidades para o Microsoft 365](../../business-video/index.yml).

Para impedir que um funcionário entre em log:

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.
2. Selecione a caixa ao lado do nome do usuário e selecione **Redefinir senha**.
3. Insira uma nova senha e selecione **Redefinir**. (Não envie para eles.)
4. Selecione o nome do usuário para ir para o  painel de propriedades e, na guia Conta, selecione **Iniciar saída**.

> [!NOTE]
> Você precisa ser um administrador global para iniciar a saída.

Dentro de uma hora - ou depois de sair da página Microsoft 365 atual em que estão - eles são solicitados a entrar novamente. Um token de acesso é bom para uma hora, portanto, a linha do tempo depende de quanto tempo resta nesse token e se eles navegam para fora de sua página da Web atual.

> [!IMPORTANT]
> Embora nós numeramos as etapas desta solução e você não precisa concluir a solução usando a ordem exata, recomendamos fazer as etapas dessa maneira.

## <a name="before-you-begin"></a>Antes de começar

Você precisa ser um administrador global para concluir as etapas nesta solução.

|||
|:-----|:-----|
|**Etapa** <br/> |**Por que fazer isso** <br/> |
|[Etapa 1 - Impedir que um ex-funcionário entre e bloqueie o acesso aos serviços Microsoft 365 serviços](remove-former-employee-step-1.md) <br/> |Isso impede que seu ex-funcionário entre no Microsoft 365 e impede que a pessoa acesse Microsoft 365 serviços. <br/> |
|[Etapa 2 : Salvar o conteúdo da caixa de correio de um ex-funcionário](remove-former-employee-step-2.md) <br/> |Isso é útil para a pessoa que assumirá o trabalho do funcionário ou se houver litígio. <br/> |
|[Etapa 3 - Encaminhar o email de um ex-funcionário para outro funcionário ou converter em uma caixa de correio compartilhada](remove-former-employee-step-3.md) <br/> |Isso permite manter o endereço de email do ex-funcionário ativo. Se clientes ou parceiros ainda enviarem emails ao endereço de email do ex-funcionário, isso os encaminhará para a pessoa que assumir o trabalho. <br/> |
|[Etapa 4 - Dar a outro funcionário acesso aos OneDrive e Outlook dados](remove-former-employee-step-6.md) <br/> |Quando você remove apenas a licença e não exclui a conta do usuário, o conteúdo do OneDrive permanece acessível para você mesmo após os 30 dias. <br/><br/> Antes de excluir a conta, você deve dar acesso às OneDrive e Outlook a outro usuário. Depois de excluir a conta de um funcionário, o conteúdo no OneDrive e Outlook é mantido por **30** dias. Durante esses 30 dias, no entanto, você pode restaurar a conta do usuário e obter acesso ao conteúdo. Se você restaurar a conta do usuário, o OneDrive e Outlook conteúdo permanecerá acessível a você mesmo após 30 dias. <br/> |
|[Etapa 5 - Apagar e bloquear o dispositivo móvel de um ex-funcionário](remove-former-employee-step-4.md) <br/> |Remove seus dados comerciais do telefone ou tablet.  <br/> |
|[Etapa 6 - Remover e excluir a Microsoft 365 de um ex-funcionário](remove-former-employee-step-7.md) <br/> |Ao remover uma licença, você pode atribuí-la a outra pessoa. Ou pode excluir a licença para não pagar por ela até contratar outra pessoa.  <br/><br/> Quando você remove ou exclui uma licença, o antigo email, contatos e calendário do usuário são mantidos por **30 dias** e, em seguida, excluídos permanentemente. Se você remover ou excluir a licença, mas não excluir a conta do usuário, o conteúdo do OneDrive permanecerá acessível para você mesmo após os 30 dias.  <br/> |
|[Etapa 7 - Excluir a conta de usuário de um ex-funcionário](remove-former-employee-step-7.md) <br/> |Isso remove a conta do centro de administração. Mantenha as coisas organizadas. <br/> |

## <a name="related-articles"></a>Artigos relacionados

[Restaurar um usuário](restore-user.md)
