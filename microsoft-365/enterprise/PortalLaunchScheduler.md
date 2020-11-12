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
ms.openlocfilehash: 929492742fd140654bd13be8165093ee10647c6d
ms.sourcegitcommit: da34ac08c7d029c2c42d4428d0bb03fd57c448be
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/12/2020
ms.locfileid: "48999560"
---
# <a name="launch-your-portal-using-the-portal-launch-scheduler"></a>Iniciar o portal usando o Agendador de lançamento do portal

Você pode iniciar o portal usando o Agendador de lançamento do portal primeiro validando a capacidade do administrador de locatários de configurar uma ondas para um novo Portal. Em seguida, o administrador pode validar um redirecionamento de solicitações, com base na existência de um usuário nas ondas ativas.

Para obter mais informações sobre como iniciar um portal bem-sucedido, siga os princípios básicos, as práticas e as recomendações detalhadas na [criação, inicialização e manutenção de um portal saudável](https://go.microsoft.com/fwlink/?linkid=2105838). 

## <a name="app-setup"></a>Configuração do aplicativo
1. Desinstale-o se existir um `Microsoft.Online.SharePoint.PowerShell` no seu computador por meio do painel de controle.
2. Na passagem do PowerShell `Install-Module -Name Microsoft.Online.SharePoint.PowerShell` .

## <a name="connect-to-sharepoint-online"></a>Conectar ao SharePoint Online
1. Abra o [Shell de gerenciamento do SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) no Windows.
2. Conecte-se ao seu locatário como administrador.
   - `Connect-SPOService -Url "https://*-admin.sharepoint.com" -Credential "username”`
3.  Forneça sua senha quando solicitado.

## <a name="command-to-get-an-existing-setup"></a>Comando para obter uma configuração existente

Para exibir as configurações de lançamento de portal existentes:

1. Passagem `Get-SPOPortalLaunchWaves  -LaunchSiteUrl  https://*.sharepoint.com/sites/newsite` .
2. Passe o parâmetro adicional `-DisplayFormat Raw` se você quiser ver a coleção Wave formatada como um formato de entrada bruto.

## <a name="commands-for-bi-directional-redirection"></a>Comandos para redirecionamento bidirecional

Para migrar usuários antigos do site para o novo site de uma maneira em estágios:

1. Criar ondas de lançamento do Portal.
   - Isso só é aplicável na fase de teste de versão inicial.
   - Para testar o impacto da alteração imediatamente, certifique-se de que a primeira onda `LaunchDateUtc` está definida como a data atual. Se você não fornecer esse sinalizador, receberá uma mensagem de erro. Esse erro ocorre porque o lançamento em produção deve ser agendado pelo menos 7 dias antes.

  `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/newsite" -RedirectionType Bidirectional -RedirectUrl "https://*.sharepoint.com/sites/oldsite" -ExpectedNumberOfUsers LessThan10kUsers -WaveOverrideUsers "*@microsoft.com" -Waves ' [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

2. Concluir a validação.
  - Pode levar até 5 minutos para que o redirecionamento conclua sua configuração no serviço, portanto, aguarde antes de continuar.
  - Se você efetuar logon com o usuário especificado como `WaveOverrideUsers` , então nada será alterado. Você deve permanecer no site para o qual navegou.
  - Faça logon com um usuário que faz parte dos *visualizadores SG1*.
    - Navegue até o site antigo e você deve ser redirecionado para o novo site.
    - Navegue até o novo site e você deverá permanecer no novo site.
    - Faça logon com user em *visualizadores SG2* e navegue até o site antigo e permaneça no site antigo.
    - Navegue até o novo site e você deve ser redirecionado para o site antigo.

3. Pausar o lançamento do Portal.
  - Se for necessário pausar as ondas de lançamento, você poderá pausá-las por número de dias. Definir o `Status` sinalizador para pausa impede que todos os futuros progressos da onda. 
  - `Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.
  - Isso valida que todos os usuários são redirecionados para o site antigo.

4. Reinicie o andamento do lançamento do Portal. 
  - `Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.
  - Valide se o redirecionamento agora é restaurado.

5. Excluir uma configuração de início de Portal.
  - `Remove-SPOPortalLaunchWaves -LaunchSiteUrl https://*.sharepoint.com/sites/NewSite`.
  - Validar que nenhum redirecionamento ocorre para todos os usuários.

## <a name="commands-for-redirection-to-temporary-page"></a>Comandos de redirecionamento para página temporária

Siga estas etapas se você não tiver um site anterior e deseja omitir usuários que não estão no pouso da onda na nova página do Portal.

Para criar uma página temporária em qualquer um dos sites:

1. Criar uma onda de lançamento do Portal.
   - `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/NewSite" -RedirectionType ToTemporaryPage -RedirectUrl "https://*.sharepoint.com/sites/OldSite" -ExpectedNumberOfUsers From10kTo30kUsers -WaveOverrideUsers *@microsoft.com -Waves [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

2. Concluir a validação.

  - Aguarde cinco minutos antes de continuar, pois a ação pode levar até cinco minutos para ser concluída.
  - Faça logon com o usuário que faz parte dos *visualizadores SG1* e:
     - Navegue até o novo site e você deve estar no novo site.
     - Navegue até a página temporária e você deve estar na página Temp.
  - Faça logon com o usuário que faz parte dos *visualizadores SG2* e:
     - Navegue até o novo site, e você deve ser redirecionado para a página Temp.
     - Navegue até a página temporária e você deve permanecer na página Temp.

3. Excluir uma configuração de início de Portal.
  - `Remove-SPOPortalLaunchWaves - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.
  - Validar que nenhum redirecionamento ocorre para todos os usuários.

## <a name="learn-more"></a>Saiba mais
[Planejando o plano de distribuição de início do portal no SharePoint Online](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out)