---
title: Criar, editar ou excluir uma exibição personalizada do usuário
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 4fe7f6ac-be8e-4b57-9e13-24ff889a4b28
description: Saiba como usar filtros para criar, editar ou excluir o modo de exibição do usuário personalizado no Microsoft 365.
ms.openlocfilehash: 598a167b9845f763ddab57d3c5ba36e431aa751c
ms.sourcegitcommit: a3ec91423c352cd5fbf79b46ccd9c169455a03ba
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/09/2020
ms.locfileid: "44664569"
---
# <a name="create-edit-or-delete-a-custom-user-view"></a>Criar, editar ou excluir uma exibição personalizada do usuário

Se você é um administrador de gerenciamento global ou de usuário de uma assinatura do Microsoft 365 for Business, você pode criar modos de exibição de usuário personalizados para exibir um subconjunto específico de usuários. Esses modos de exibição são adicionais ao conjunto padrão de modos de exibição. Você pode criar, editar ou excluir modos de exibição de usuário personalizados, e os modos de exibição personalizados que você cria estão disponíveis para todos os administradores.
  
## <a name="custom-user-views-in-the-admin-center"></a>Exibições de usuário personalizadas no centro de administração

::: moniker range="o365-worldwide"

Ao criar, editar ou excluir um modo de exibição de usuário personalizado, as alterações serão mostradas na lista de **filtros** que todos os administradores da sua empresa veem quando acessam a página **usuários** . Você pode criar até 50 modos de exibição personalizados. 

::: moniker-end

::: moniker range="o365-germany"

Quando você cria, edita ou exclui um modo de exibição de usuário personalizado, as alterações serão mostradas na lista de **exibições** que todos os administradores da sua empresa veem quando acessam a página **usuários** . Você pode criar até 50 modos de exibição personalizados. 

::: moniker-end

::: moniker range="o365-21vianet"

Quando você cria, edita ou exclui um modo de exibição de usuário personalizado, as alterações serão mostradas na lista de **exibições** que todos os administradores da sua empresa veem quando acessam a página **usuários** . Você pode criar até 50 modos de exibição personalizados. 

::: moniker-end

> [!TIP]
>  Os modos de exibição de usuário padrão são exibidos por padrão na lista suspensa **filtros** . Os filtros padrão incluem **todos os usuários**, **usuários licenciados**, **usuários convidados**, **logon permitido**, **logon bloqueado**, usuários não **licenciados**, **usuários com erros**, administradores de **cobrança**, **administradores globais**, **Administradores de assistência técnica**, administradores de **Serviços**e administradores de **Gerenciamento de usuários**. Não é possível editar ou excluir modos de exibição padrão. 

Algumas coisas a serem observadas sobre os modos de exibição padrão: 

- Alguns modos de exibição padrão exibem uma lista não classificada se houver mais de 2.000 usuários na lista. Para localizar usuários específicos nesta lista, use a caixa de pesquisa. 
- Se você não comprou o Microsoft 365 da Microsoft, os **Administradores de cobrança** não aparecerão na lista de modos de exibição padrão. Para saber mais, veja [Atribuindo funções de administrador](assign-admin-roles.md). 
  
## <a name="choose-the-filters-for-your-custom-user-view"></a>Escolha os filtros para o modo de exibição de usuário personalizado

Você pode criar e editar seus modos de exibição personalizados no painel de **filtro personalizado** . Se você selecionar várias opções de filtro, receberá resultados que contenham usuários que correspondam a todos os critérios selecionados. O exemplo a seguir mostra como criar um modo de exibição personalizado chamado "usuários canadenses" que mostra todos os usuários em um domínio específico que estão no Canadá. 

  
 **A-Domain** Se você tiver vários domínios para sua organização, poderá escolher em uma lista suspensa de domínios disponíveis. 
  
 **Status de entrada B** Escolha usuários que são permitidos ou bloqueados. 
  
 **C-local** Escolha um local em uma lista suspensa de países. 
  
 **Licença de produto atribuída D** Escolha em uma lista suspensa de licenças disponíveis em sua organização. Use este filtro para mostrar os usuários que têm a licença selecionada atribuída a eles. Os usuários também podem ter licenças adicionais. 
  
Você também pode filtrar por detalhes adicionais de perfil de usuário usados na organização, como departamento, cidade, estado ou província, país ou região, ou cargo.
  
 **Outras condições:**
  
- **Somente usuários sincronizados** Selecione esta caixa para mostrar todos os usuários que foram sincronizados com o Active Directory local, independentemente se os usuários foram ativados ou não. 
    
- **Usuários com erros** Selecione esta caixa para mostrar aos usuários que podem ter o provisionamento de erros. 
    
- **Usuários não licenciados** Selecione esta caixa para localizar todos os usuários que não receberam uma licença. Os resultados desse modo de exibição também podem incluir usuários que tenham uma caixa de correio do Exchange, mas não tenham uma licença. Para controlar esses usuários especificamente, use o filtro **usuários não licenciados com caixas de correio do Exchange ou arquivos mortos**. Os resultados desse modo de exibição também podem incluir usuários que têm um arquivo morto do Exchange, mas não têm uma licença.
    
- **Usuários não licenciados com caixas de correio ou arquivos mortos do Exchange** Selecione esta caixa para mostrar as contas de usuário que foram criadas no Exchange Online e ter uma caixa de correio do Exchange, mas não foi atribuída uma licença do Microsoft 365. Os resultados desse filtro incluem usuários que tenham ou quem foram atribuídos a um arquivo morto do Exchange. 

> [!NOTE]
> O filtro **usuários não licenciados com caixas de correio do Exchange** funciona quando:
1. A caixa de correio foi convertida recentemente de **compartilhada** para **usuário** e não tem licença.
2. A caixa de correio foi migrada recentemente para a Microsoft 365, mas não foi atribuída uma licença.
3. A caixa de correio foi criada usando o PowerShell e não foi atribuída uma licença.
4. Uma nova caixa de correio criada no local com um cmdlet New-RemoteMailbox é provisionada para o usuário.
    
> [!TIP]
> Se você criar um modo de exibição personalizado que retorna mais de 2.000 usuários, a lista de usuários resultante não será classificada. Nesse caso, use a caixa Pesquisar para localizar usuários ou editar o modo de exibição personalizado para refinar sua pesquisa. 
  
## <a name="create-a-custom-user-view"></a>Criar um modo de exibição de usuário personalizado

::: moniker range="o365-worldwide"

1. No centro de administração, vá para usuários ativos do **usuário** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a>.
    
2. Na página **usuários ativos** , selecione **filtros** e selecione **novo filtro**.
  
3. Na página **filtro personalizado** , digite o nome do filtro, escolha as condições para o filtro personalizado e, em seguida, selecione **Adicionar**. O modo de exibição personalizado agora está incluído na lista suspensa de filtros.
    
::: moniker-end

::: moniker range="o365-germany"

1. No centro de administração, vá para usuários ativos do **usuário** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a>.  

2. Na página **usuários ativos** , selecione **modos** de exibição e selecione **Adicionar modo de exibição personalizado**.
  
3. Na página **modo de exibição personalizado** , digite o nome para o filtro, escolha as condições para o filtro personalizado e, em seguida, selecione **Adicionar**. O modo de exibição personalizado agora está incluído na lista suspensa de filtros.

::: moniker-end


::: moniker range="o365-21vianet"

1. No centro de administração, vá para usuários ativos do **usuário** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a>. 

2. Na página **usuários ativos** , selecione **modos** de exibição e selecione **Adicionar modo de exibição personalizado**.
  
3. Na página **modo de exibição personalizado** , digite o nome para o filtro, escolha as condições para o filtro personalizado e, em seguida, selecione **Adicionar**. O modo de exibição personalizado agora está incluído na lista suspensa de filtros.

::: moniker-end
    

## <a name="edit-or-delete-a-custom-user-view"></a>Editar ou excluir um modo de exibição de usuário personalizado

::: moniker range="o365-worldwide"

1. No centro de administração, vá para usuários ativos do **usuário** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a>.
    
2. Na página **usuários ativos** , selecione **filtro**, selecione o filtro que você deseja alterar e, em seguida, selecione **Editar Filtro**. 
    
    > [!TIP]
    > Você pode editar somente modos de exibição personalizados. 
  
3. Na página **filtro personalizado** , edite as informações conforme necessário e, em seguida, selecione **salvar**. Ou, para excluir o filtro, na parte inferior da página, selecione **excluir**. 
    
::: moniker-end

::: moniker range="o365-germany"

1. No centro de administração, vá para usuários ativos do **usuário** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a>.  

2. Na página **usuários ativos** , selecione **modos**de exibição, selecione o filtro que você deseja alterar e, em seguida, selecione **Editar este modo de exibição**. 
    
    > [!TIP]
    > Você pode editar somente modos de exibição personalizados. 
  
3. Na página **modo de exibição personalizado** , edite as informações conforme o necessário e, em seguida, selecione **salvar**. Ou, para excluir o filtro, na parte inferior da página, selecione **excluir modo de exibição personalizado**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. No centro de administração, vá para usuários ativos do **usuário** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a>. 

2. Na página **usuários ativos** , selecione **modos**de exibição, selecione o filtro que você deseja alterar e, em seguida, selecione **Editar este modo de exibição**. 
    
    > [!TIP]
    > Você pode editar somente modos de exibição personalizados. 
  
3. Na página **modo de exibição personalizado** , edite as informações conforme o necessário e, em seguida, selecione **salvar**. Ou, para excluir o filtro, na parte inferior da página, selecione **excluir modo de exibição personalizado**. 

::: moniker-end


     