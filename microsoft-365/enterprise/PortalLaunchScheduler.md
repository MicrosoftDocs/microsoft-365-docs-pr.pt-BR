---
title: Iniciar seu portal usando o Agendador de Início do Portal
ms.author: jhendr
author: jhendr
manager: pamgreen
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
description: Este artigo descreve como você pode iniciar seu portal usando o Agendador de Início do Portal
ms.openlocfilehash: e39f00dbc63ae7f1dcaf907d9c67df2c1683efc6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926137"
---
# <a name="launch-your-portal-using-the-portal-launch-scheduler"></a>Iniciar seu portal usando o Agendador de Início do Portal

Um portal é um site do SharePoint na intranet que tem um grande número de visualizadores de site que consomem o conteúdo dele. Iniciar seu portal em ondas é uma parte importante para garantir que os usuários tenham uma experiência suave e performante acessando um novo portal do SharePoint Online. 

Iniciar em ondas é uma maneira fundamental de lançar seu portal, conforme detalhado em Planejamento do seu plano de lançamento de [portal no SharePoint Online](./planportallaunchroll-out.md?view=o365-worldwide). O Agendador de Início de Portal foi projetado para ajudá-lo a seguir uma abordagem de lançamento em fases/onda gerenciando os redirecionamentos para o novo portal. Durante cada uma das ondas, você pode coletar comentários do usuário e monitorar o desempenho durante cada onda de implantação. Isso tem a vantagem de introduzir lentamente o portal, dando a você a opção de pausar e resolver problemas antes de prosseguir com a próxima onda e, finalmente, garantir uma experiência positiva para seus usuários. 

Há dois tipos de redirecionamento: 
- bidirecional: iniciar um novo portal moderno do SharePoint Online para substituir um portal clássico ou moderno existente do SharePoint 
- redirecionamento de página temporária: iniciar um novo portal moderno do SharePoint Online sem portal existente do SharePoint

O agendador de início do portal só está disponível para iniciar portais modernos do SharePoint Online (ou seja, sites de comunicação). Os lançamentos devem ser agendados com pelo menos 7 dias de antecedência. O número de ondas necessárias é determinado pelo número esperado de usuários. Antes de agendar um lançamento de portal, a ferramenta Diagnóstico de Página para [SharePoint](./page-diagnostics-for-spo.md) deve ser executado para verificar se a home page no portal está bem. No final do início do portal, todos os usuários com permissões para o site poderão acessar o novo site. 

Para obter mais informações sobre como iniciar um portal bem-sucedido, siga os princípios básicos, práticas e recomendações detalhados em Criação, lançamento e manutenção de [um portal saudável.](/sharepoint/portal-health) 

> [!NOTE]
> Esse recurso não está disponível para planos do Office 365 Germany, Office 365 operado pela 21Vianet (China) ou Microsoft 365 US Government.

## <a name="app-setup-and-connecting-to-sharepoint-online"></a>Configuração de aplicativo e conexão com o SharePoint Online
1. [Baixe o Shell de Gerenciamento do SharePoint Online mais recente](https://go.microsoft.com/fwlink/p/?LinkId=255251).

    > [!NOTE]
    > Se você instalou uma versão anterior do Shell de Gerenciamento do SharePoint Online, vá até Adicionar ou remover programas e desinstale o "Shell de Gerenciamento do SharePoint Online".<br>Na página Centro de Downloads, selecione seu idioma e clique no botão Download. Você deverá escolher entre baixar um arquivo x64 e x86 .msi. Baixe o arquivo x64 se estiver executando a versão de 64 bits do Windows ou o arquivo x86 se estiver executando a versão de 32 bits. Se você não souber, consulte [Qual versão do sistema operacional Windows estou executando?](https://support.microsoft.com/help/13443/windows-which-operating-system). Depois de baixar o arquivo, execute-o e siga as etapas do assistente de configuração.

2. Conecte-se ao SharePoint como um [administrador global ou administrador do SharePoint](/sharepoint/sharepoint-admin-role) no Microsoft 365. Para saber como, consulte [Introdução ao Shell de Gerenciamento do SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).


## <a name="view-any-existing-portal-launch-setups"></a>Exibir quaisquer configurações de início de portal existentes

Para ver se há configurações de início de portal existentes:

   ```PowerShell
   Get-SPOPortalLaunchWaves -LaunchSiteUrl <object> -DisplayFormat <object>
   ```

## <a name="schedule-a-portal-launch-on-the-site"></a>Agendar um início de portal no site

O número de ondas necessárias depende do tamanho de lançamento esperado. 
- Menos de 10 mil usuários: 1 onda
- Usuários de 10 mil a 30 mil: 3 ondas 
- 30k+ a 100 mil usuários: 5 ondas
- Mais de 100 mil usuários: 5 ondas e contate sua equipe de conta da Microsoft

### <a name="steps-for-bidirectional-redirection"></a>Etapas para redirecionamento bidirecional

O redirecionamento bidirecional envolve o lançamento de um novo portal moderno do SharePoint Online para substituir um portal clássico ou moderno existente do SharePoint. Os usuários em ondas ativas serão redirecionados para o novo site, independentemente de navegar para o site antigo ou novo. Os usuários em uma onda não lançada que tentam acessar o novo site serão redirecionados de volta para o site antigo até que sua onda seja lançada. 

Só há suporte para redirecionamento entre a home page padrão no site antigo e a home page padrão no novo site. Se você tiver administradores ou proprietários que precisem de acesso aos sites antigos e novos sem serem redirecionados, verifique se eles estão listados usando o `WaveOverrideUsers` parâmetro.

Para migrar usuários de um site existente do SharePoint para um novo site do SharePoint em estágios:

1. Execute o seguinte comando para designar as ondas de início do portal.
   
   ```PowerShell
    New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType Bidirectional -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
    ```

Exemplo:
   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType Bidirectional -RedirectUrl "https://contoso.sharepoint.com/teams/oldsite" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
[{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
{Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"}, 
{Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. Validação completa. Pode levar de 5 a 10 minutos para que o redirecionamento conclua sua configuração em todo o serviço. 

### <a name="steps-for-redirection-to-temporary-page"></a>Etapas para redirecionamento para página temporária

O redirecionamento temporário de página deve ser usado quando nenhum portal existente do SharePoint existir. Os usuários são direcionados para um novo portal moderno do SharePoint Online em estágios. Se um usuário estiver em uma onda que não foi lançada, ele será redirecionado para uma página temporária (qualquer URL). 

1. Execute o seguinte comando para designar as ondas de início do portal.
   
      ```PowerShell
    New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType ToTemporaryPage -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
    ```

Exemplo:
   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType ToTemporaryPage -RedirectUrl "https://portal.contoso.com/UnderConstruction.aspx" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
[{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
{Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"}, 
{Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. Validação completa. Pode levar de 5 a 10 minutos para que o redirecionamento conclua sua configuração em todo o serviço. 

## <a name="pause-or-restart-a-portal-launch-on-the-site"></a>Pausar ou reiniciar um início de portal no site

1. Para pausar um lançamento de portal em andamento e impedir temporariamente que as progressões de onda futuras ocorram, execute o seguinte comando:

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl <object>
   ```
2. Valide se todos os usuários são redirecionados para o site antigo. 

3. Para reiniciar um lançamento de portal que foi pausado, execute o seguinte comando:

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl <object>
   ```
   
4. Valide se o redirecionamento foi restaurado. 

## <a name="delete-a-portal-launch-on-the-site"></a>Excluir um início de portal no site

1. Execute o seguinte comando para excluir um início de portal agendado ou em andamento para um site.

   ```PowerShell
   Remove-SPOPortalLaunchWaves -LaunchSiteUrl <object>
   ```

2. Valide se nenhum redirecionamento acontece para todos os usuários.

## <a name="learn-more"></a>Saiba mais
[Planejando seu plano de lançamento do portal no SharePoint Online](./planportallaunchroll-out.md)