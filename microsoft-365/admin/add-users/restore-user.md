---
title: Restaurar um usuário
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 2c261e42-5dd1-48b0-845f-2a016d29cfc1
description: Saiba como restaurar contas de usuário excluídas e todos os dados associados.
ms.openlocfilehash: 27b3f4a0077b5ef0dcfaef1dbe5019a5d69652f2
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44386992"
---
# <a name="restore-a-user"></a>Restaurar um usuário

::: moniker range="o365-21vianet"

> [!NOTE]
> O centro de administração está mudando. Se a sua experiência não corresponder aos detalhes apresentados aqui, consulte [Sobre o novo centro de administração do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end
   
Quando você restaura uma conta de usuário dentro de 30 dias após sua exclusão, nosso sistema restaura a conta e todos os dados associados a ela. O usuário pode entrar com a mesma conta corporativa ou de estudante. A caixa de correio será totalmente restaurada. Para saber até quando uma determinada conta de usuário poderá ser restaurada, [entre em contato conosco](../contact-support-for-business-products.md).
  
Aqui estão algumas dicas:
  
- Certifique-se de que as licenças estão disponíveis para atribuir à conta.
    
- Se sua empresa usar o Active Directory, confira [Como solucionar problemas de contas de usuário excluídas no Office 365](https://support.microsoft.com/kb/2619308) para obter instruções sobre como restaurar uma conta de usuário. 
    
## <a name="restore-one-or-more-user-accounts"></a>Restaurar uma ou mais contas de usuário

Você deve ser um administrador global do Microsoft 365 ou administrador de gerenciamento de usuários para executar estas etapas. 
  
 
::: moniker range="o365-worldwide"

1. No centro de administração, vá **para a** \> página usuários <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">excluídos</a> usuários.

::: moniker-end

::: moniker range="o365-germany"

1. Vá para o [centro de administração](https://go.microsoft.com/fwlink/p/?linkid=848041) **e selecione usuários** \> **excluídos**.

::: moniker-end

::: moniker range="o365-21vianet"

1. Vá para o [centro de administração](https://go.microsoft.com/fwlink/p/?linkid=850627) **e selecione usuários** \> **excluídos**.

::: moniker-end

2. Na página **usuários excluídos** , selecione os nomes dos usuários que você deseja restaurar e, em seguida, selecione **restaurar**.
    
 
3. Siga as instruções para definir a senha e, em seguida, selecione **restaurar**.
    
4. Se o usuário for restaurado com êxito, selecione **Enviar email e fechar**. Se ocorrer um conflito de nome ou de endereço proxy, confira as instruções abaixo para saber como restaurar essas contas.
    
Depois de restaurar um usuário, certifique-se de notificá-los de que sua senha foi alterada e faça o acompanhamento deles.
  
## <a name="restore-a-user-that-has-a-user-name-conflict"></a>Restaurar um usuário com um conflito de nome de usuário
<a name="RestoreUserNameConflict"> </a>

Um conflito de nome de usuário ocorre quando você exclui uma conta de usuário, cria uma nova conta com o mesmo nome de usuário (para o mesmo usuário ou outro com um nome semelhante) e, posteriormente, tenta restaurar a conta excluída.
  
Para resolver isso, você pode substituir a conta de usuário ativa por uma que esteja restaurando ou atribuir um nome de usuário diferente à conta que está restaurando para que não existam duas contas com o mesmo nome de usuário. Siga as seguintes etapas.
  

::: moniker range="o365-worldwide"

1. No centro de administração, vá **para a** \> página usuários <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">excluídos</a> usuários.

::: moniker-end

::: moniker range="o365-germany"

1. Vá para o [centro de administração](https://go.microsoft.com/fwlink/p/?linkid=848041) **e selecione usuários** \> **excluídos**.

::: moniker-end

::: moniker range="o365-21vianet"

1. Vá para o [centro de administração](https://go.microsoft.com/fwlink/p/?linkid=850627) **e selecione usuários** \> **excluídos**.

::: moniker-end

  
2. Na página **usuários excluídos** , selecione os nomes dos usuários que você deseja restaurar e, em seguida, selecione **restaurar**.
    
    > [!NOTE]
    > Se houver falha na restauração de dois ou mais usuários, uma mensagem de erro o avisará que houve falha na operação de restauração para alguns usuários. Você pode exibir o log para ver se os usuários foram ou não restaurados e restaurar uma conta com falha de cada vez. 
  
3. Siga as instruções para definir a senha e selecionar **restaurar**.
    
4. Uma mensagem aparece informando que ocorreu um problema ao restaurar a conta. Siga um destes procedimentos:
    
  - Cancele a restauração e renomeie o usuário ativo atual. Em seguida, tente restaurar novamente.
    
  - OU digite um novo endereço de email principal para o usuário e selecione **restaurar**.
    
5. Examine os resultados e selecione **Fechar**.
    
## <a name="restore-a-user-that-has-a-proxy-address-conflict"></a>Restaurar um usuário que tenha um conflito de endereço de proxy

Um conflito de endereço proxy ocorre quando você exclui uma conta de usuário que contém um endereço proxy, atribui esse mesmo endereço proxy a outra conta e tenta restaurar a conta excluída. Para corrigir esse problema, siga as etapas a seguir.
  
Você deve ter [permissões de administrador](about-admin-roles.md) no Microsoft 365 para fazer isso. 
  

::: moniker range="o365-worldwide"

1. No centro de administração, vá **para a** \> página usuários <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">excluídos</a> usuários.

::: moniker-end

::: moniker range="o365-germany"

Vá para o [centro de administração](https://go.microsoft.com/fwlink/p/?linkid=848041) **e selecione usuários** \> **excluídos**.

::: moniker-end

::: moniker range="o365-21vianet"

1. Vá para o [centro de administração](https://go.microsoft.com/fwlink/p/?linkid=850627) **e selecione usuários** \> **excluídos**.

::: moniker-end

2. Na página **Usuários excluídos**, selecione o usuário que você deseja restaurar e selecione **Restaurar**. 
    
3. Na página **restaurar** , siga as instruções para definir a senha e selecionar **restaurar**. Os endereços proxy conflitantes são automaticamente removidos do usuário que você está restaurando.
    
4. Examine os resultados e selecione **Fechar**.

## <a name="related-articles"></a>Artigos relacionados

[Excluir um usuário](delete-a-user.md)
  
