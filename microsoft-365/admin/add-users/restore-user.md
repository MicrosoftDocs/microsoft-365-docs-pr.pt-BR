---
title: Restaurar um usuário
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
ms.openlocfilehash: 9cdc4100f963ed450b50caa0f07a3863bc87992d
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244027"
---
# <a name="restore-a-user"></a>Restaurar um usuário
   
Quando você restaura uma conta de usuário dentro de 30 dias após sua exclusão, nosso sistema restaura a conta e todos os dados associados a ela. O usuário pode entrar com a mesma conta corporativa ou de estudante. A caixa de correio será totalmente restaurada. Para saber até quando uma determinada conta de usuário poderá ser restaurada, [entre em contato conosco](../contact-support-for-business-products.md).
  
Aqui estão algumas dicas:
  
- Certifique-se de que as licenças estão disponíveis para atribuir à conta.
    
- Se sua empresa usar o Active Directory, confira [Como solucionar problemas de contas de usuário excluídas no Office 365](/office365/troubleshoot/active-directory/restore-deleted-user-accounts.md) para obter instruções sobre como restaurar uma conta de usuário. 
    
## <a name="restore-one-or-more-user-accounts"></a>Restaurar uma ou mais contas de usuário

Você deve ser um administrador global Microsoft 365 gerenciamento de usuários ou administrador global para fazer essas etapas. 

1. No centro de administração, vá para a **página Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">Excluídos.</a>

2. Na página **Usuários Excluídos,** selecione os nomes dos usuários que você deseja restaurar e selecione **Restaurar**.
    
3. Siga os prompts para definir sua senha e selecione **Restaurar**.
    
4. Se o usuário for restaurado com êxito, selecione **Enviar email e fechar**. Se ocorrer um conflito de nome ou de endereço proxy, confira as instruções abaixo para saber como restaurar essas contas.
    
Depois de restaurar um usuário, certifique-se de notificá-lo de que a senha foi alterada e que você o acompanha.
  
## <a name="restore-a-user-that-has-a-user-name-conflict"></a>Restaurar um usuário com um conflito de nome de usuário

Um conflito de nome de usuário ocorre quando você exclui uma conta de usuário, cria uma nova conta com o mesmo nome de usuário (para o mesmo usuário ou outro com um nome semelhante) e, posteriormente, tenta restaurar a conta excluída.
  
Para resolver isso, você pode substituir a conta de usuário ativa por uma que esteja restaurando ou atribuir um nome de usuário diferente à conta que está restaurando para que não existam duas contas com o mesmo nome de usuário. Siga as seguintes etapas.

1. No centro de administração, vá para a **página Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">Excluídos.</a>
  
2. Na página **Usuários Excluídos,** selecione os nomes dos usuários que você deseja restaurar e selecione **Restaurar**.
    
    > [!NOTE]
    > Se houver falha na restauração de dois ou mais usuários, uma mensagem de erro o avisará que houve falha na operação de restauração para alguns usuários. Você pode exibir o log para ver se os usuários foram ou não restaurados e restaurar uma conta com falha de cada vez. 
  
3. Siga os prompts para definir a senha e selecione **Restaurar**.
    
4. Uma mensagem aparece informando que ocorreu um problema ao restaurar a conta. Siga um destes procedimentos:
    
  - Cancele a restauração e renomeie o usuário ativo atual. Em seguida, tente restaurar novamente.
    
  - OR, digite um novo endereço de email principal para o usuário e selecione **Restaurar**.
    
5. Examine os resultados e selecione **Fechar**.
    
## <a name="restore-a-user-that-has-a-proxy-address-conflict"></a>Restaurar um usuário que tenha um conflito de endereço de proxy

Um conflito de endereço proxy ocorre quando você exclui uma conta de usuário que contém um endereço proxy, atribui esse mesmo endereço proxy a outra conta e tenta restaurar a conta excluída. Para corrigir esse problema, siga as etapas a seguir.
  
Você deve ter [permissões de](about-admin-roles.md) administrador Microsoft 365 fazer isso. 

1. No centro de administração, vá para a **página Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">Excluídos.</a>

2. Na página **Usuários excluídos**, selecione o usuário que você deseja restaurar e selecione **Restaurar**. 
    
3. Na página **Restaurar,** siga as instruções para definir a senha e selecione **Restaurar**. Os endereços proxy conflitantes são automaticamente removidos do usuário que você está restaurando.
    
4. Examine os resultados e selecione **Fechar**.

## <a name="related-articles"></a>Artigos relacionados

[Excluir um usuário](delete-a-user.md)
