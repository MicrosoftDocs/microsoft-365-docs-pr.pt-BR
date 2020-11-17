---
title: Iniciar o portal usando o Agendador de lançamento do portal
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
description: Este artigo descreve como você pode iniciar seu portal usando o Agendador de lançamento do portal
ms.openlocfilehash: a7a007fdd95638109830a8e3689232060f2b9d8b
ms.sourcegitcommit: 2d3e85173c65a9e0ce92624a80ed7a9839f5b8bd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "49123578"
---
# <a name="launch-your-portal-using-the-portal-launch-scheduler"></a>Iniciar o portal usando o Agendador de lançamento do portal

Um portal é um site do SharePoint na intranet que tem um grande número de visualizadores de site que consomem o conteúdo dele. Iniciar seu portal em ondas é uma parte importante da garantia de que os usuários tenham uma experiência suave e de baixo desempenho acessando um novo portal do SharePoint Online. 

A inicialização em ondas é uma maneira principal de distribuir seu portal, conforme detalhado no [planejamento do plano de distribuição de lançamento do portal no SharePoint Online](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out?view=o365-worldwide). O Agendador de lançamento do portal foi projetado para ajudá-lo a seguir uma abordagem de distribuição ondulada por fases, gerenciando os redirecionamentos para o novo Portal. Durante cada uma das ondas, você pode coletar comentários do usuário e monitorar o desempenho durante cada onda de implantação. Isso tem a vantagem de apresentar lentamente o portal, dando a você a opção de pausar e resolver problemas antes de prosseguir com a próxima onda e, por fim, garantir uma experiência positiva para seus usuários. 

Há dois tipos de redirecionamento: 
- bidirecional: iniciar um novo portal moderno do SharePoint Online para substituir um portal clássico ou moderno do SharePoint existente 
- redirecionamento de página temporário: Inicie um novo portal moderno do SharePoint Online com nenhum portal do SharePoint existente

O Agendador de lançamento do portal só está disponível para iniciar portais modernos do SharePoint Online, como sites de comunicação e sites de equipe modernos. Os lançamentos devem ser agendados pelo menos 7 dias antes. O número de ondas necessárias é determinado pelo número esperado de usuários. Antes de agendar um lançamento de portal, a [ferramenta diagnóstico de página para SharePoint](https://aka.ms/perftool) deve ser executada para verificar se a Home Page no portal está íntegra. No final do lançamento do portal, todos os usuários com permissões para o site poderão acessar o novo site. 

Para obter mais informações sobre como iniciar um portal bem-sucedido, siga os princípios básicos, as práticas e as recomendações detalhadas sobre como [criar, iniciar e manter um portal saudável](https://docs.microsoft.com/sharepoint/portal-health). 

> [!NOTE]
> Este recurso não está disponível para o Office 365 Alemanha, Office 365 operado pela 21Vianet (China) ou planos do governo dos EUA da Microsoft 365.

## <a name="app-setup-and-connecting-to-sharepoint-online"></a>Configuração do aplicativo e conexão ao SharePoint Online
1. [Baixe o Shell de Gerenciamento do SharePoint Online mais recente](https://go.microsoft.com/fwlink/p/?LinkId=255251).

    > [!NOTE]
    > Se você instalou uma versão anterior do Shell de Gerenciamento do SharePoint Online, vá até Adicionar ou remover programas e desinstale o "Shell de Gerenciamento do SharePoint Online".<br>Na página Centro de Downloads, selecione seu idioma e clique no botão Download. Você deverá escolher entre baixar um arquivo x64 e x86 .msi. Baixe o arquivo x64 se estiver executando a versão de 64 bits do Windows ou o arquivo x86 se estiver executando a versão de 32 bits. Se você não souber, consulte [Qual versão do sistema operacional Windows estou executando?](https://support.microsoft.com/help/13443/windows-which-operating-system). Depois de baixar o arquivo, execute-o e siga as etapas do assistente de configuração.

2. Conecte-se ao SharePoint como um [administrador global ou administrador do SharePoint](/sharepoint/sharepoint-admin-role) no Microsoft 365. Para saber como, consulte [Introdução ao Shell de Gerenciamento do SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).


## <a name="view-any-existing-portal-launch-setups"></a>Exibir configurações de início de portal existentes

Para ver se há configurações de lançamento de portal existentes:

   ```PowerShell
   Get-SPOPortalLaunchWaves -LaunchSiteUrl <object> -DisplayFormat <object>
   ```

## <a name="schedule-a-portal-launch-on-the-site"></a>Agendar um lançamento do portal no site

O número de ondas necessárias depende do tamanho esperado do lançamento. 
- Menos de 10k usuários: 1 onda
- 10K para usuários do 30K: 3 ondas 
- 30K + 100.000 usuários: 5 ondas
- Mais de 100.000 usuários: 5 ondas e contate a equipe de conta da Microsoft

### <a name="steps-for-bi-directional-redirection"></a>Etapas para redirecionamento bidirecional

O redirecionamento bidirecional envolve a inicialização de um novo portal moderno do SharePoint Online para substituir um portal clássico ou moderno do SharePoint existente. Os usuários em ondas ativas serão redirecionados para o novo site, independentemente de eles navegarem para o site antigo ou novo. Os usuários em uma onda não iniciada que tentar acessar o novo site serão redirecionados de volta para o site antigo até que a onda seja iniciada. Se você tiver administradores ou proprietários que precisam acessar os sites antigos e novos sem serem redirecionados, verifique se estão listados usando o `WaveOverrideUsers` parâmetro. 

Para migrar usuários de um site do SharePoint existente para um novo site do SharePoint de uma maneira em estágios:

1. Execute o comando a seguir para designar ondas de lançamento do Portal.
   
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

2. Concluir a validação. Pode levar de 5-10 minutos para o redirecionamento concluir sua configuração no serviço. 

### <a name="steps-for-redirection-to-temporary-page"></a>Etapas para redirecionamento para página temporária

O redirecionamento de página temporária deve ser usado quando não existir nenhum portal do SharePoint existente. Os usuários são direcionados para um novo portal moderno do SharePoint Online de uma maneira em estágios. Se um usuário estiver em uma onda que não foi iniciada, ele será redirecionado para uma página temporária (qualquer URL). 

1. Execute o comando a seguir para designar ondas de lançamento do Portal.
   
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

2. Concluir a validação. Pode levar de 5-10 minutos para o redirecionamento concluir sua configuração no serviço. 
   - `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/newsite" -RedirectionType Bidirectional -RedirectUrl "https://*.sharepoint.com/sites/oldsite" -ExpectedNumberOfUsers LessThan10kUsers -WaveOverrideUsers "*@microsoft.com" -Waves ' [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

## <a name="pause-or-restart-a-portal-launch-on-the-site"></a>Pausar ou reiniciar um lançamento do portal no site

1. Para pausar o lançamento de um portal em andamento e impedir temporariamente a ocorrência de progressos de ondas futuras, execute o seguinte comando:

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl <object>
   ```
2. Validar que todos os usuários são redirecionados para o site antigo. 

3. Para reiniciar um lançamento de portal que tenha sido pausado, execute o seguinte comando:

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl <object>
   ```
   
4. Valide se o redirecionamento agora é restaurado. 

## <a name="delete-a-portal-launch-on-the-site"></a>Excluir um lançamento de portal no site
1. Criar uma onda de lançamento do Portal.
  - `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/NewSite" -RedirectionType ToTemporaryPage -RedirectUrl "https://*.sharepoint.com/sites/OldSite" -ExpectedNumberOfUsers From10kTo30kUsers -WaveOverrideUsers *@microsoft.com -Waves [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

2. Execute o comando a seguir para excluir um lançamento de portal agendado ou em andamento para um site.

   ```PowerShell
   Remove-SPOPortalLaunchWaves -LaunchSiteUrl <object>
   ```

3. Validar que nenhum redirecionamento ocorre para todos os usuários.

## <a name="learn-more"></a>Saiba mais
[Planejando o plano de distribuição de início do portal no SharePoint Online](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out)
