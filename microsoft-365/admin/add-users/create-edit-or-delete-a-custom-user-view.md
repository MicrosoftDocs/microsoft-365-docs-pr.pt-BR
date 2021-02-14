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
ms.openlocfilehash: 598a167b9845f763ddab57d3c5ba36e431aa751c
ms.sourcegitcommit: a3ec91423c352cd5fbf79b46ccd9c169455a03ba
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/09/2020
ms.locfileid: "44664569"
---
# <a name="create-edit-or-delete-a-custom-user-view"></a>Criar, editar ou excluir uma exibição personalizada do usuário

Se você for um administrador global ou de gerenciamento de usuários de uma assinatura do Microsoft 365 para empresas, poderá criar exibições de usuário personalizadas para exibir um subconjunto específico de usuários. Esses visualizações são além do conjunto padrão de exibições. Você pode criar, editar ou excluir exibições de usuário personalizadas, e as exibições personalizadas que você criar estão disponíveis para todos os administradores.
  
## <a name="custom-user-views-in-the-admin-center"></a>Exibições personalizadas do usuário no centro de administração

::: moniker range="o365-worldwide"

Quando você cria, edita ou exclui um modo de  exibição de usuário personalizado, as alterações serão mostradas na lista de filtros que todos os administradores em sua empresa veem quando vão para a página **Usuários.** Você pode criar até 50 exibições personalizadas. 

::: moniker-end

::: moniker range="o365-germany"

Quando você cria, edita ou exclui um modo de  exibição de usuário personalizado, as alterações serão mostradas na lista Exibições que todos os administradores em sua empresa veem quando vão para a página **Usuários.** Você pode criar até 50 exibições personalizadas. 

::: moniker-end

::: moniker range="o365-21vianet"

Quando você cria, edita ou exclui um modo de  exibição de usuário personalizado, as alterações serão mostradas na lista Exibições que todos os administradores em sua empresa veem quando vão para a página **Usuários.** Você pode criar até 50 exibições personalizadas. 

::: moniker-end

> [!TIP]
>  As exibições padrão do usuário são exibidas por padrão **na** lista de filtros. Os filtros padrão incluem Todos os usuários **,** Usuários **licenciados** **,** usuários convidados **,** entrada permitida **,** entrada bloqueada **,** usuários não **licenciados**, usuários com erros **,** administradores de cobrança , administradores globais , administradores de **helpdesk**, administradores de **serviço** e administradores de gerenciamento de **usuários**. Não é possível editar nem excluir exibições padrão. 

Algumas coisas a observar sobre exibições padrão: 

- Alguns exibições padrão exibem uma lista não-formatada se houver mais de 2.000 usuários na lista. Para localizar usuários específicos nessa lista, use a caixa de pesquisa. 
- Se você não tiver comprado o Microsoft 365 da **Microsoft,** os administradores de cobrança não aparecerão na lista de exibições padrão. Para saber mais, veja [Atribuindo funções de administrador](assign-admin-roles.md). 
  
## <a name="choose-the-filters-for-your-custom-user-view"></a>Escolha os filtros para sua exibição de usuário personalizada

Você pode criar e editar seus exibições personalizadas no **painel Filtro** personalizado. Se você selecionar várias opções de filtro, obterá resultados que contenham usuários que corresponderem a todos os critérios selecionados. O exemplo a seguir mostra como criar uma exibição personalizada chamada "Usuários canadenses" que mostra todos os usuários em um domínio específico que estão no Canadá. 

  
 **A - Domínio** Se você tiver vários domínios para sua organização, poderá escolher em uma lista lista de domínios disponíveis. 
  
 **B - Status de login** Escolha os usuários permitidos ou bloqueados. 
  
 **C - Local** Escolha um local em uma lista lista de países. 
  
 **D - Licença de produto atribuída** Escolha em uma lista drop-down de licenças que estão disponíveis em sua organização. Use esse filtro para mostrar aos usuários que têm a licença que você selecionou atribuída a eles. Os usuários também podem ter licenças adicionais. 
  
Você também pode filtrar por detalhes de perfil de usuário adicionais usados em sua organização, como departamento, cidade, estado ou província, país ou região ou cargo.
  
 **Outras condições:**
  
- **Somente usuários sincronizados** Marque essa caixa para mostrar todos os usuários que foram sincronizados com o Active Directory local, independentemente de os usuários ter sido ativados ou não. 
    
- **Usuários com erros** Marque essa caixa para mostrar aos usuários que podem ter erros de provisionamento. 
    
- **Usuários não licençados** Marque essa caixa para encontrar todos os usuários que não foram atribuídos a uma licença. Os resultados para essa exibição também podem incluir usuários que têm uma caixa de correio do Exchange, mas não têm uma licença. Para rastrear esses usuários especificamente, use o filtro Usuários não licençados com **caixas de correio ou arquivos do Exchange.** Os resultados dessa exibição também podem incluir usuários que têm um arquivo morto do Exchange, mas não têm uma licença.
    
- **Usuários não-licenças com caixas de correio ou arquivos do Exchange** Marque essa caixa para mostrar as contas de usuário que foram criadas no Exchange Online e têm uma caixa de correio do Exchange, mas que não foram atribuídas com uma licença do Microsoft 365. Os resultados desse filtro incluem usuários que têm ou que foram atribuídos a um arquivo morto do Exchange. 

> [!NOTE]
> Os **usuários não licençados com filtro de caixas de correio do Exchange** funcionam quando:
1. A caixa de correio foi convertida recentemente **de compartilhada** **para** usuário e não tem licença.
2. A caixa de correio foi migrada recentemente para o Microsoft 365, mas uma licença não foi atribuída.
3. A caixa de correio foi criada usando o PowerShell e uma licença não foi atribuída.
4. Uma nova caixa de correio que foi criada no local com um New-RemoteMailbox cmdlet é provisionado para o usuário.
    
> [!TIP]
> Se você criar uma exibição personalizada que retorne mais de 2.000 usuários, a lista de usuários resultante não será ordenada. Nesse caso, use a caixa de pesquisa para encontrar usuários ou edite seu modo de exibição personalizado para refinar sua pesquisa. 
  
## <a name="create-a-custom-user-view"></a>Criar uma exibição de usuário personalizada

::: moniker range="o365-worldwide"

1. No centro de administração, vá para **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Ativos.</a>
    
2. Na página **Usuários ativos,** selecione **Filtros** e selecione **Novo filtro.**
  
3. Na página **Filtro personalizado,** insira o nome do filtro, escolha as condições para o filtro personalizado e selecione **Adicionar**. Sua exibição personalizada agora está incluída na lista de filtros.
    
::: moniker-end

::: moniker range="o365-germany"

1. No centro de administração, vá para **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Ativos.</a>  

2. Na página **Usuários ativos,** selecione **Exibições** e **selecione Adicionar exibição personalizada.**
  
3. Na página **Exibição personalizada,** insira o nome do filtro, escolha as condições para o filtro personalizado e selecione **Adicionar**. Sua exibição personalizada agora está incluída na lista de filtros.

::: moniker-end


::: moniker range="o365-21vianet"

1. No centro de administração, vá para **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Ativos.</a> 

2. Na página **Usuários ativos,** selecione **Exibições** e **selecione Adicionar exibição personalizada.**
  
3. Na página **Exibição personalizada,** insira o nome do filtro, escolha as condições para o filtro personalizado e selecione **Adicionar**. Sua exibição personalizada agora está incluída na lista de filtros.

::: moniker-end
    

## <a name="edit-or-delete-a-custom-user-view"></a>Editar ou excluir um modo de exibição de usuário personalizado

::: moniker range="o365-worldwide"

1. No centro de administração, vá para **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Ativos.</a>
    
2. Na página **Usuários ativos,** selecione **Filtrar**, selecione o filtro que você deseja alterar e, em seguida, selecione **Editar filtro**. 
    
    > [!TIP]
    > Você só pode editar exibições personalizadas. 
  
3. Na página **Filtro personalizado,** edite as informações conforme necessário e selecione **Salvar**. Ou, para excluir o filtro, na parte inferior da página, selecione **Excluir**. 
    
::: moniker-end

::: moniker range="o365-germany"

1. No centro de administração, vá para **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Ativos.</a>  

2. Na página **Usuários ativos,** selecione **Exibições,** selecione o filtro que deseja alterar e selecione **Editar este modo de exibição.** 
    
    > [!TIP]
    > Você só pode editar exibições personalizadas. 
  
3. Na página **Modo de Exibição** Personalizado, edite as informações conforme necessário e selecione **Salvar.** Ou, para excluir o filtro, na parte inferior da página, selecione **Excluir exibição personalizada.** 

::: moniker-end

::: moniker range="o365-21vianet"

1. No centro de administração, vá para **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Ativos.</a> 

2. Na página **Usuários ativos,** selecione **Exibições,** selecione o filtro que deseja alterar e selecione **Editar este modo de exibição.** 
    
    > [!TIP]
    > Você só pode editar exibições personalizadas. 
  
3. Na página **Modo de Exibição** Personalizado, edite as informações conforme necessário e selecione **Salvar.** Ou, para excluir o filtro, na parte inferior da página, selecione **Excluir exibição personalizada.** 

::: moniker-end


     