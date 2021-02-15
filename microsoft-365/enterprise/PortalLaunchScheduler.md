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
ms.openlocfilehash: 66912f5730c580bd75282a64124fefcdf262d738
ms.sourcegitcommit: cc354fd54400be0ff0401f60bbe68ed975b69cda
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/14/2021
ms.locfileid: "49864871"
---
# <a name="launch-your-portal-using-the-portal-launch-scheduler"></a>Iniciar seu portal usando o Agendador de Início do Portal

Um portal é um site do SharePoint na intranet que tem um grande número de visualizadores de site que consomem o conteúdo dele. Iniciar seu portal em ondas é uma parte importante de garantir que os usuários tenham uma experiência suave e de desempenho acessando um novo portal do SharePoint Online. 

Iniciar em ondas é uma maneira importante de lançar seu portal, conforme detalhado no Planejamento do seu plano de lançamento de lançamento do portal no [SharePoint Online.](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out?view=o365-worldwide) O Agendador de Início do Portal foi projetado para ajudá-lo a seguir uma abordagem de lançamento em fases/onda gerenciando os redirecionamentos para o novo portal. Durante cada uma das ondas, você pode coletar comentários do usuário e monitorar o desempenho durante cada onda de implantação. Isso tem a vantagem de introduzir lentamente o portal, dando a opção de pausar e resolver problemas antes de prosseguir com a próxima onda e, em última análise, garantir uma experiência positiva para seus usuários. 

Há dois tipos de redirecionamento: 
- bidirecional: iniciar um novo portal moderno do SharePoint Online para substituir um portal clássico ou moderno existente do SharePoint 
- redirecionamento temporário de página: iniciar um novo portal moderno do SharePoint Online sem portal existente do SharePoint

O agendador de lançamento do portal só está disponível para iniciar portais modernos do SharePoint Online (ou seja, sites de comunicação). As iniciações devem ser agendadas com pelo menos sete dias de antecedência. O número de ondas necessárias é determinado pelo número esperado de usuários. Antes de agendar um lançamento do portal, a ferramenta Diagnóstico de Página para [SharePoint](https://aka.ms/perftool) deve ser executado para verificar se a home page no portal está confira. No final do lançamento do portal, todos os usuários com permissões para o site poderão acessar o novo site. 

Para obter mais informações sobre como iniciar um portal bem-sucedido, siga os princípios básicos, práticas e recomendações detalhados na criação, lançamento e manutenção [de um portal saudável.](https://docs.microsoft.com/sharepoint/portal-health) 

> [!NOTE]
> Esse recurso não está disponível para planos do Office 365 Germany, Office 365 operado pela 21Vianet (China) ou Microsoft 365 US Government.

## <a name="app-setup-and-connecting-to-sharepoint-online"></a>Configuração e conexão de aplicativos com o SharePoint Online
1. [Baixe o Shell de Gerenciamento do SharePoint Online mais recente](https://go.microsoft.com/fwlink/p/?LinkId=255251).

    > [!NOTE]
    > Se você instalou uma versão anterior do Shell de Gerenciamento do SharePoint Online, vá até Adicionar ou remover programas e desinstale o "Shell de Gerenciamento do SharePoint Online".<br>Na página Centro de Downloads, selecione seu idioma e clique no botão Download. Você deverá escolher entre baixar um arquivo x64 e x86 .msi. Baixe o arquivo x64 se estiver executando a versão de 64 bits do Windows ou o arquivo x86 se estiver executando a versão de 32 bits. Se você não souber, consulte [Qual versão do sistema operacional Windows estou executando?](https://support.microsoft.com/help/13443/windows-which-operating-system). Depois de baixar o arquivo, execute-o e siga as etapas do assistente de configuração.

2. Conecte-se ao SharePoint como um [administrador global ou administrador do SharePoint](/sharepoint/sharepoint-admin-role) no Microsoft 365. Para saber como, consulte [Introdução ao Shell de Gerenciamento do SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).


## <a name="view-any-existing-portal-launch-setups"></a>Exibir quaisquer configurações de início de portal existentes

Para ver se há configurações de início de portal existentes:

   ```PowerShell
   Get-SPOPortalLaunchWaves -LaunchSiteUrl <object> -DisplayFormat <object>
   ```

## <a name="schedule-a-portal-launch-on-the-site"></a>Agendar um lançamento do portal no site

O número de ondas necessárias depende do tamanho de lançamento esperado. 
- Menos de 10 mil usuários: 1 onda
- 10 mil a 30 mil usuários: 3 ondas 
- 30k+ a 100 mil usuários: 5 ondas
- Mais de 100 mil usuários: cinco ondas e contate sua equipe de conta da Microsoft

### <a name="steps-for-bidirectional-redirection"></a>Etapas para redirecionamento bidirecional

O redirecionamento bidirecional envolve iniciar um novo portal moderno do SharePoint Online para substituir um portal clássico ou moderno existente do SharePoint. Os usuários em ondas ativas serão redirecionados para o novo site, independentemente de eles navegarem para o site antigo ou novo. Os usuários em uma onda não lançada que tentar acessar o novo site serão redirecionados de volta para o site antigo até que sua onda seja lançada. 

Suportamos apenas o redirecionamento entre a home page padrão no site antigo e a home page padrão no novo site. Caso tenha administradores ou proprietários que precisem acessar os sites antigos e novos sem serem redirecionados, verifique se eles estão listados usando o `WaveOverrideUsers` parâmetro.

Para migrar usuários de um site existente do SharePoint para um novo site do SharePoint em estágios:

1. Execute o seguinte comando para designar ondas de início do portal.
   
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

2. Validação completa. Pode levar de 5 a 10 minutos para que o redirecionamento conclua sua configuração no serviço. 

### <a name="steps-for-redirection-to-temporary-page"></a>Etapas para redirecionamento para página temporária

O redirecionamento de página temporário deve ser usado quando nenhum portal existente do SharePoint existe. Os usuários são direcionados para um novo portal moderno do SharePoint Online em estágios. Se um usuário estiver em uma onda que não foi lançada, ele será redirecionado para uma página temporária (qualquer URL). 

1. Execute o seguinte comando para designar ondas de início do portal.
   
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

2. Validação completa. Pode levar de 5 a 10 minutos para que o redirecionamento conclua sua configuração no serviço. 

## <a name="pause-or-restart-a-portal-launch-on-the-site"></a>Pausar ou reiniciar uma início de portal no site

1. Para pausar uma iniciação de portal em andamento e impedir temporariamente que próximas progressões de onda ocorram, execute o seguinte comando:

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl <object>
   ```
2. Valide se todos os usuários são redirecionados para o site antigo. 

3. Para reiniciar uma reinicialização do portal que foi pausada, execute o seguinte comando:

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl <object>
   ```
   
4. Valide se o redirecionamento agora foi restaurado. 

## <a name="delete-a-portal-launch-on-the-site"></a>Excluir uma iniciação de portal no site

1. Execute o seguinte comando para excluir uma início de portal agendada ou em andamento para um site.

   ```PowerShell
   Remove-SPOPortalLaunchWaves -LaunchSiteUrl <object>
   ```

2. Valide que nenhum redirecionamento acontece para todos os usuários.

## <a name="learn-more"></a>Saiba mais
[Planejamento do seu plano de lançamento do portal no SharePoint Online](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out)
