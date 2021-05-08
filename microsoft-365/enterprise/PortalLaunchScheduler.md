---
title: Iniciar seu portal usando o agendador de início do portal
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
description: Este artigo descreve como você pode iniciar seu portal usando o agendador de início do portal
ms.openlocfilehash: d7ea64b3a9fef25ddfde43e61624e49d2b7d4352
ms.sourcegitcommit: 8e4c107e4da3a00be0511b05bc655a98fe871a54
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52280964"
---
# <a name="launch-your-portal-using-the-sharepoint-portal-launch-scheduler"></a>Iniciar seu portal usando o agendador de SharePoint portal

Um portal é um site SharePoint de comunicação em sua intranet que é de alto tráfego – um site que tem de 10.000 a mais de 100.000 visualizadores ao longo de várias semanas. Use o agendador de início do Portal para iniciar seu portal para garantir que os usuários tenham uma experiência de visualização suave ao acessar seu novo portal SharePoint portal.
<br>
<br>
O agendador de início do Portal foi projetado para ajudá-lo a seguir uma abordagem de lançamento em fases, direcionando os visualizadores em lotes em ondas e gerenciando os redirecionamentos de URL para o novo portal. Durante o início de cada onda, você pode coletar comentários do usuário, monitorar o desempenho do portal e pausar o lançamento para resolver problemas antes de prosseguir com a próxima onda. Saiba mais sobre como planejar [um lançamento de portal em SharePoint](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out?view=o365-worldwide). 

**Há dois tipos de redirecionamentos:**

- **Bidirecional**: iniciar um novo portal SharePoint moderno para substituir um portal SharePoint clássico ou moderno existente
- **Redirecionar para uma página temporária**: iniciar um novo portal SharePoint moderno sem nenhum portal SharePoint existente

As permissões de site devem ser configuradas separadamente das ondas como parte do lançamento. Por exemplo, se você estiver liberando um portal de toda a organização, poderá definir permissões como "Todos, exceto usuários externos", em seguida, separe seus usuários em ondas usando grupos de segurança. Adicionar um grupo de segurança a uma onda não dá acesso a esse grupo de segurança ao site. 


> [!NOTE]
> - Esse recurso será acessível a partir do painel **Configurações** na home page de sites de comunicação do SharePoint para clientes de versão direcionada a partir de maio de 2021 e ficará disponível para todos os clientes até julho de 2021
> - A versão do PowerShell desta ferramenta está disponível hoje
> - Esse recurso só pode ser usado em sites de SharePoint de comunicação modernos
> - Você deve ter permissões de proprietário do site para que o site personalize e agende o lançamento de um portal
> - Os lançamentos devem ser agendados com pelo menos sete dias de antecedência e cada onda pode durar de um a sete dias
> - O número de ondas necessárias é determinado automaticamente pelo número esperado de usuários 
> - Antes de agendar um lançamento de portal, a ferramenta Diagnóstico de Página para SharePoint [deve](https://aka.ms/perftool) ser executado para verificar se a home page do site é saudável
> - No final do lançamento, todos os usuários com permissões para o site poderão acessar o novo site
> - Se sua organização estiver usando o [Viva Connections](https://docs.microsoft.com/SharePoint/viva-connections), os usuários poderão ver o ícone da sua organização na barra de aplicativos Microsoft Teams, no entanto, quando o ícone estiver selecionado, os usuários não poderão acessar o portal até que sua onda seja lançada
> - Esse recurso não está disponível para Office 365 Alemanha, Office 365 operado pela 21Vianet (China) ou Microsoft 365 do Governo dos EUA

### <a name="understand-the-differences-between-portal-launch-scheduler-options"></a>Entenda as diferenças entre as opções do agendador de início do portal:

Anteriormente, os lançamentos de portal só podiam ser agendados por meio SharePoint PowerShell. Agora, você tem duas opções para ajudá-lo a agendar e gerenciar o lançamento do portal. Saiba mais sobre as principais diferenças entre ambas as ferramentas:

**SharePoint Versão do PowerShell:**

- As credenciais de administrador são necessárias para usar [SharePoint PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell?view=sharepoint-ps) 
- Requisito mínimo de uma onda 
- Agendar seu lançamento com base no fuso horário UTC (Tempo Universal Coordenado)

**Versão no produto:**

- As credenciais do proprietário do site são necessárias 
- Requisito mínimo de duas ondas
- Agende seu lançamento com base no fuso horário local do portal, conforme indicado nas configurações regionais



## <a name="get-started-using-the-portal-launch-scheduler"></a>Começar a usar o agendador de início do portal

1.  Antes de usar a ferramenta agendador de início do Portal, adicione todos os usuários que precisarão de acesso a esse site por meio de permissões de [site](https://support.microsoft.com/office/share-a-site-958771a8-d041-4eb8-b51c-afea2eae3658) como proprietário do site, membro do site ou visitante. 

2.  Em seguida, comece a agendar o lançamento do portal acessando o agendador de início do Portal de duas maneiras:

    **Opção 1**: Nas primeiras vezes que você editar e republicar alterações na home page - ou até a home page versão 3.0 - você será solicitado a usar a ferramenta agendador de início do Portal. Selecione **Agendar o início** para avançar com o agendamento. Ou selecione **Republicar para** republicar suas edições de página sem agendar o lançamento.
    
    ![Imagem do prompt para usar o agendador de início do portal ao publicar a home page](../media/portal-launch-republish-2.png)
    
    **Opção 2:** **a** qualquer momento, você pode navegar até a home page do site de comunicação SharePoint, selecione Configurações e agende o início do **site** para agendar o lançamento do portal.
    
    ![Imagem do painel Configurações agendar um lançamento de site realçada](../media/portal-launch-settings-2.png)

3.  Em seguida, confirme a pontuação de saúde do portal e faça [melhorias](https://aka.ms/perftool) no portal, se necessário, usando a ferramenta Diagnóstico de Página para SharePoint até que seu portal receba uma **pontuação** Saudável. Em seguida, selecione **Avançar**.

    ![Imagem da ferramenta agendador de início do portal](../media/portal-launch-panel-2.png)
       
    > [!NOTE] 
    > O nome e **a descrição** do site não podem ser editados a partir do agendador de início do Portal e, em vez disso, podem ser alterados selecionando Configurações e, em seguida, informações **do** site na home page.
 
4.  Selecione o **Número de usuários esperados** no drop-down. Essa figura representa o número de usuários que provavelmente precisarão de acesso ao site. O agendador de início do Portal determinará automaticamente o número ideal de ondas, dependendo dos usuários esperados como este:
    
    - Menos de 10 mil usuários: Duas ondas
    - Usuários de 10 mil a 30 mil: três ondas 
    - 30k+ a 100 mil usuários: Cinco ondas
    - Mais de 100 mil usuários: cinco ondas e contate sua equipe de conta da Microsoft

5.  Em seguida, determine **o Tipo de redirecionamento** necessário:

    Opção 1: Enviar usuários para uma página de SharePoint **existente (bidirecional)** – Use essa opção ao iniciar um novo portal SharePoint moderno para substituir um portal SharePoint existente. Os usuários em ondas ativas serão redirecionados para o novo site, independentemente de navegar para o site antigo ou novo. Os usuários em uma onda não lançada que tentam acessar o novo site serão redirecionados de volta para o site antigo até que sua onda seja lançada.
    
    > [!NOTE] 
    > Ao usar a opção bidirecional, a pessoa que está agendando o lançamento também deve ter permissões de proprietário do site para o outro portal SharePoint site.
       
    **Opção 2: Enviar** usuários para uma página temporária de geração automática (redirecionamento temporário de página) – Use um redirecionamento de página temporário deve ser usado quando não houver um portal SharePoint existente. Os usuários são direcionados para um novo portal de SharePoint moderno e, se um usuário estiver em uma onda que não foi lançada, eles serão redirecionados para uma página temporária.
    
    **Opção 3: Enviar usuários** para uma página externa – Fornecer uma URL externa para uma experiência de página de aterrissagem temporária até que a onda do usuário seja lançada.
    
6.  Separar sua audiência em ondas. Adicione até 20 grupos de segurança por onda. Os detalhes da onda podem ser editados até o início de cada onda. Cada onda pode durar pelo menos um dia (24 horas) e, no máximo, sete dias. Isso permite SharePoint e seu ambiente técnico uma oportunidade de se aclimatar e dimensionar para o grande volume de usuários do site. Ao agendar um lançamento pela interface do usuário, o fuso horário se baseia nas configurações regionais do site. 

    >[!NOTE] 
    > - O agendador de início do Portal será automaticamente padrão para um mínimo de 2 ondas. No entanto, a versão do PowerShell desta ferramenta permitirá 1 onda.
    >  - Microsoft 365 grupos não são suportados por esta versão do agendador de início do Portal.

7. Determine quem precisa exibir o site imediatamente e insira suas informações no **campo Usuários isentos de** ondas. Esses usuários são excluídos das ondas e não serão redirecionados antes, durante ou após o início.

8.  Confirme os detalhes de início do portal e selecione **Agendar**. Depois que o lançamento tiver sido agendado, quaisquer alterações na home page do portal SharePoint precisarão receber um resultado de diagnóstico saudável antes que o início do portal seja retomado.


## <a name="make-changes-to-a-scheduled-portal-launch"></a>Fazer alterações em um lançamento de portal agendado

Os detalhes de início podem ser editados para cada onda até a data de início da onda. 

1.  Para editar detalhes de início do portal, navegue **até Configurações** e selecione **Agendar o início do site.**
2.  Em seguida, selecione **Editar**.
3.  Quando terminar de fazer suas edições, selecione **Atualizar**.


## <a name="delete-a-scheduled-portal-launch"></a>Excluir um lançamento de portal agendado

As iniciações agendadas usando a ferramenta agendador de início do Portal podem ser canceladas ou excluídas a qualquer momento, mesmo que algumas ondas já tenham sido lançadas.

1.  Para cancelar o lançamento do seu portal, navegue até **Configurações** **e Agende o início do site.**

2.  Em seguida, selecione **Excluir** e, em seguida, quando você vir a mensagem abaixo, selecione **Excluir** novamente.

    ![Imagem da ferramenta agendador de início do portal](../media/portal-launch-delete-2.png)


## <a name="use-the-powershell-portal-launch-scheduler"></a>Usar o agendador de início do Portal do PowerShell

A SharePoint do agendador de início do Portal estava originalmente disponível apenas por meio do [SharePoint PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell?view=sharepoint-ps) e continuará a ter suporte por meio do PowerShell para clientes que preferem esse método. As mesmas anotações no início deste artigo se aplicam às duas versões do agendador de início do Portal. 

>[!NOTE]
> Você precisa de permissões de administrador para usar SharePoint PowerShell.
> Os detalhes de início do portal para lançamentos criados no PowerShell serão exibidos e poderão ser gerenciados na nova ferramenta de agendador de início do Portal SharePoint.


### <a name="app-setup-and-connecting-to-sharepoint-online"></a>Configuração de aplicativo e conexão com SharePoint Online
1. [Baixe o Shell de Gerenciamento do SharePoint Online mais recente](https://go.microsoft.com/fwlink/p/?LinkId=255251).

    > [!NOTE]
    > Se você instalou uma versão anterior do Shell de Gerenciamento do SharePoint Online, vá até Adicionar ou remover programas e desinstale o "Shell de Gerenciamento do SharePoint Online".<br>Na página Centro de Downloads, selecione seu idioma e clique no botão Download. Você deverá escolher entre baixar um arquivo x64 e x86 .msi. Baixe o arquivo x64 se estiver executando a versão de 64 bits do Windows ou o arquivo x86 se estiver executando a versão de 32 bits. Se você não souber, consulte [Qual versão do sistema operacional Windows estou executando?](https://support.microsoft.com/help/13443/windows-which-operating-system). Depois de baixar o arquivo, execute-o e siga as etapas do assistente de configuração.

2. Conecte-se ao SharePoint como um [administrador global ou administrador do SharePoint](/sharepoint/sharepoint-admin-role) no Microsoft 365. Para saber como, consulte [Introdução ao Shell de Gerenciamento do SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).


### <a name="view-any-existing-portal-launch-setups"></a>Exibir quaisquer configurações de início de portal existentes

Para ver se há configurações de início de portal existentes:

   ```PowerShell
   Get-SPOPortalLaunchWaves -LaunchSiteUrl <object> -DisplayFormat <object>
   ```

### <a name="schedule-a-portal-launch-on-the-site"></a>Agendar um início de portal no site

O número de ondas necessárias depende do tamanho de lançamento esperado. 
- Menos de 10 mil usuários: uma onda
- Usuários de 10 mil a 30 mil: três ondas 
- 30k+ a 100 mil usuários: Cinco ondas
- Mais de 100 mil usuários: cinco ondas e contate sua equipe de conta da Microsoft

#### <a name="steps-for-bidirectional-redirection"></a>Etapas para redirecionamento bidirecional

O redirecionamento bidirecional envolve o lançamento de um novo portal SharePoint Online moderno para substituir um portal SharePoint clássico ou moderno existente. Os usuários em ondas ativas serão redirecionados para o novo site, independentemente de navegar para o site antigo ou novo. Os usuários em uma onda não lançada que tentam acessar o novo site serão redirecionados de volta para o site antigo até que sua onda seja lançada. 

Só há suporte para redirecionamento entre a home page padrão no site antigo e a home page padrão no novo site. Se você tiver administradores ou proprietários que precisem de acesso aos sites antigos e novos sem serem redirecionados, verifique se eles estão listados usando o `WaveOverrideUsers` parâmetro.

Para migrar usuários de um site SharePoint existente para um novo site SharePoint em estágios:

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

#### <a name="steps-for-redirection-to-temporary-page"></a>Etapas para redirecionamento para página temporária

O redirecionamento temporário de página deve ser usado quando nenhum portal SharePoint existente. Os usuários são direcionados para um novo portal SharePoint Online em estágios. Se um usuário estiver em uma onda que não foi lançada, ele será redirecionado para uma página temporária (qualquer URL). 

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

### <a name="pause-or-restart-a-portal-launch-on-the-site"></a>Pausar ou reiniciar um início de portal no site

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

### <a name="delete-a-portal-launch-on-the-site"></a>Excluir um início de portal no site

1. Execute o seguinte comando para excluir um início de portal agendado ou em andamento para um site.

   ```PowerShell
   Remove-SPOPortalLaunchWaves -LaunchSiteUrl <object>
   ```

2. Valide se nenhum redirecionamento acontece para todos os usuários.

## <a name="learn-more"></a>Saiba mais

[Planejando seu plano de lançamento do portal no SharePoint Online](./planportallaunchroll-out.md)

[Planejar seu site de comunicação](https://support.microsoft.com/office/plan-your-sharepoint-communication-site-35d9adfe-d5cc-462f-a63a-bae7f2529182)
