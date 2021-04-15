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
description: Aprenda a usar filtros para criar, editar ou excluir o modo de exibição de usuário personalizado no Microsoft 365.
ms.openlocfilehash: 4bd4ea351612c2ae5175cd27fa7a689d671a8b62
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51755567"
---
# <a name="create-edit-or-delete-a-custom-user-view"></a>Criar, editar ou excluir uma exibição personalizada do usuário

Se você for um administrador de gerenciamento de usuário ou global de uma assinatura do Microsoft 365 para empresas, poderá criar exibições de usuário personalizadas para exibir um subconjunto específico de usuários. Essas exibições são além do conjunto padrão de exibições. Você pode criar, editar ou excluir exibições de usuário personalizadas e as exibições personalizadas que você criar estão disponíveis para todos os administradores.
  
## <a name="custom-user-views-in-the-admin-center"></a>Exibições de usuário personalizadas no centro de administração

Quando você cria, edita ou exclui um modo de  exibição de usuário personalizado, as alterações serão mostradas na lista Filtro que todos os administradores da sua empresa veem quando vão para a página **Usuários.** Você pode criar até 50 exibições personalizadas. 

> [!TIP]
>  As exibições padrão do usuário são exibidas por padrão **na** listada Filtros. Os  **filtros** padrão incluem Todos os usuários , Usuários **licenciados,** Usuários convidados **,** Entrada **permitida,** Entrada **bloqueada,** usuários não **licenciados,** Usuários com **erros,** administradores de cobrança, administradores globais, administradores do **Helpdesk,** administradores de **serviço** e administradores de gerenciamento do usuário.   Não é possível editar ou excluir exibições padrão. 

Algumas coisas a observar sobre exibições padrão: 

- Algumas exibições padrão exibem uma lista não ressutada se houver mais de 2.000 usuários na lista. Para localizar usuários específicos nesta lista, use a caixa de pesquisa. 
- Se você não tiver comprado o Microsoft 365 da **Microsoft,** os administradores de cobrança não aparecerão na lista de exibições padrão. Para saber mais, veja [Atribuindo funções de administrador](assign-admin-roles.md). 
  
## <a name="choose-the-filters-for-your-custom-user-view"></a>Escolha os filtros para o seu exibição de usuário personalizado

Você pode criar e editar seus exibições personalizadas no **painel Filtro** personalizado. Se você selecionar várias opções de filtro, obterá resultados que contêm usuários que corresponderem a todos os critérios selecionados. O exemplo a seguir mostra como criar uma exibição personalizada chamada "Usuários canadenses" que mostra todos os usuários em um domínio específico que estão no Canadá. 

  
 **A - Domínio** Se você tiver vários domínios para sua organização, poderá escolher em uma listada de domínios disponíveis. 
  
 **B - Status de login** Escolha usuários permitidos ou bloqueados. 
  
 **C - Local** Escolha um local em uma listada de países. 
  
 **D - Licença de produto atribuída** Escolha em uma lista lista listada de licenças que estão disponíveis em sua organização. Use esse filtro para mostrar aos usuários que têm a licença selecionada atribuída a eles. Os usuários também podem ter licenças adicionais. 
  
Você também pode filtrar por detalhes de perfil de usuário adicionais usados em sua organização, como departamento, cidade, estado ou província, país ou região ou cargo.
  
 **Outras condições:**
  
- **Somente usuários sincronizados** Marque essa caixa para mostrar todos os usuários que foram sincronizados com o Active Directory local, independentemente de os usuários ter sido ativados ou não. 
    
- **Usuários com erros** Marque esta caixa para mostrar aos usuários que podem ter erros de provisionamento. 
    
- **Usuários não-licenças** Selecione essa caixa para encontrar todos os usuários que não foram atribuídos a uma licença. Os resultados dessa exibição também podem incluir usuários que têm uma caixa de correio do Exchange, mas não têm uma licença. Para rastrear esses usuários especificamente, use o filtro Usuários sem licença com caixas de correio **ou arquivos do Exchange.** Os resultados dessa exibição também podem incluir usuários que têm um arquivo morto do Exchange, mas não têm uma licença.
    
- **Usuários sem licença com caixas de correio ou arquivos do Exchange** Marque essa caixa para mostrar contas de usuário criadas no Exchange Online e ter uma caixa de correio do Exchange, mas não foi atribuída uma licença do Microsoft 365. Os resultados desse filtro incluem usuários que têm ou que foram atribuídos a um arquivo morto do Exchange. 

> [!NOTE]
> O **filtro Usuários sem licença com caixas de correio** do Exchange funciona quando:
1. A caixa de correio foi convertida recentemente **de compartilhada** para **usuário** e não tem licença.
2. A caixa de correio foi migrada recentemente para o Microsoft 365, mas uma licença não foi atribuída.
3. A caixa de correio foi criada usando o PowerShell e uma licença não foi atribuída.
4. Uma nova caixa de correio que foi criada no local com um cmdlet New-RemoteMailbox é provisionada para o usuário.
    
> [!TIP]
> Se você criar uma exibição personalizada que retorne mais de 2.000 usuários, a lista de usuários resultante não será classificação. Nesse caso, use a caixa de pesquisa para encontrar usuários ou editar seu modo de exibição personalizado para refinar sua pesquisa. 
  
## <a name="create-a-custom-user-view"></a>Criar uma exibição de usuário personalizada

::: moniker range="o365-worldwide"

1. No centro de administração, vá para **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos.</a>
    
2. Na página **Usuários ativos,** selecione **Filtros** e selecione **Novo filtro**.
  
3. Na página **Filtro personalizado,** digite o nome do filtro, escolha as condições do filtro personalizado e selecione **Adicionar**. Sua exibição personalizada agora está incluída na lista de filtros listada.
    
::: moniker-end

::: moniker range="o365-germany"

1. No centro de administração, vá para **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos.</a>  

2. Na página **Usuários ativos,** selecione **Exibir e** selecione **Adicionar exibição personalizada**.
  
3. Na página **Exibição** personalizada, insira o nome do filtro, escolha as condições do filtro personalizado e selecione **Adicionar**. Sua exibição personalizada agora está incluída na lista de filtros listada.

::: moniker-end


::: moniker range="o365-21vianet"

1. No centro de administração, vá para **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos.</a> 

2. Na página **Usuários ativos,** selecione **Exibir e** selecione **Adicionar exibição personalizada**.
  
3. Na página **Exibição** personalizada, insira o nome do filtro, escolha as condições do filtro personalizado e selecione **Adicionar**. Sua exibição personalizada agora está incluída na lista de filtros listada.

::: moniker-end
    

## <a name="edit-or-delete-a-custom-user-view"></a>Editar ou excluir um modo de exibição de usuário personalizado

::: moniker range="o365-worldwide"

1. No centro de administração, vá para **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos.</a>
    
2. Na página **Usuários ativos,** selecione **Filtrar**, selecione o filtro que você deseja alterar e selecione **Editar filtro**. 
    
    > [!TIP]
    > Você pode editar somente exibições personalizadas. 
  
3. Na página **Filtro** personalizado, edite as informações conforme necessário e selecione **Salvar**. Ou, para excluir o filtro, na parte inferior da página selecione **Excluir**. 
    
::: moniker-end

::: moniker range="o365-germany"

1. No centro de administração, vá para **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos.</a>  

2. Na página **Usuários ativos,** selecione **Exibir**, selecione o filtro que você deseja alterar e selecione **Editar este modo de exibição**. 
    
    > [!TIP]
    > Você pode editar somente exibições personalizadas. 
  
3. Na página **Modo de exibição** personalizado, edite as informações conforme necessário e selecione **Salvar**. Ou, para excluir o filtro, na parte inferior da página, selecione **Excluir exibição personalizada**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. No centro de administração, vá para **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos.</a> 

2. Na página **Usuários ativos,** selecione **Exibir**, selecione o filtro que você deseja alterar e selecione **Editar este modo de exibição**. 
    
    > [!TIP]
    > Você pode editar somente exibições personalizadas. 
  
3. Na página **Modo de exibição** personalizado, edite as informações conforme necessário e selecione **Salvar**. Ou, para excluir o filtro, na parte inferior da página, selecione **Excluir exibição personalizada**. 

::: moniker-end


     