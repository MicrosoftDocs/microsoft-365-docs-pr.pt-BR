---
title: Exibir erros de sincronização de diretórios Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- GPA150
ms.assetid: b4fc07a5-97ea-4ca6-9692-108acab74067
description: Saiba como exibir erros de sincronização de diretório e possíveis correções Microsoft 365 centro de administração.
ms.openlocfilehash: 76717fc158aa0cee47f784919f19a295378bbd5b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907499"
---
# <a name="view-directory-synchronization-errors-in-microsoft-365"></a><span data-ttu-id="69fdd-103">Exibir erros de sincronização de diretórios Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="69fdd-103">View directory synchronization errors in Microsoft 365</span></span>

<span data-ttu-id="69fdd-104">Você pode exibir erros de sincronização de diretório no Microsoft 365 de administração.</span><span class="sxs-lookup"><span data-stu-id="69fdd-104">You can view directory synchronization errors in the Microsoft 365 admin center.</span></span> <span data-ttu-id="69fdd-105">Somente os erros do objeto User são exibidos.</span><span class="sxs-lookup"><span data-stu-id="69fdd-105">Only the User object errors are displayed.</span></span> <span data-ttu-id="69fdd-106">Para exibir erros com o PowerShell, consulte [Identificar objetos com DirSyncProvisioningErrors](/azure/active-directory/hybrid/how-to-connect-syncservice-duplicate-attribute-resiliency).</span><span class="sxs-lookup"><span data-stu-id="69fdd-106">To view errors with PowerShell, see [Identify objects with DirSyncProvisioningErrors](/azure/active-directory/hybrid/how-to-connect-syncservice-duplicate-attribute-resiliency).</span></span>

## <a name="view-directory-synchronization-errors-in-the-microsoft-365-admin-center"></a><span data-ttu-id="69fdd-107">Exibir erros de sincronização de diretório no Microsoft 365 de administração</span><span class="sxs-lookup"><span data-stu-id="69fdd-107">View directory synchronization errors in the Microsoft 365 admin center</span></span>

<span data-ttu-id="69fdd-108">Para exibir quaisquer erros no Microsoft 365 de administração:</span><span class="sxs-lookup"><span data-stu-id="69fdd-108">To view any errors in the Microsoft 365 admin center:</span></span>
  
1. <span data-ttu-id="69fdd-109">Entre no centro de administração [Microsoft 365 com](https://admin.microsoft.com) uma conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="69fdd-109">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with a global administrator account.</span></span> 
    
2. <span data-ttu-id="69fdd-110">Na **home** page, você verá o **cartão de gerenciamento do** usuário.</span><span class="sxs-lookup"><span data-stu-id="69fdd-110">On the **Home** page, you'll see the **User management** card.</span></span> 
    
    ![O cartão de gerenciamento do usuário no Microsoft 365 de administração](../media/060006e9-de61-49d5-8979-e77cda198e71.png)
  
3. <span data-ttu-id="69fdd-112">No cartão, escolha **Sincronizar erros** em **Azure AD Conexão** para ver os erros na página **Erros de** sincronização de diretório.</span><span class="sxs-lookup"><span data-stu-id="69fdd-112">On the card, choose **Sync errors** under **Azure AD Connect** to see the errors on the **Directory sync errors** page.</span></span>   
    
    ![Um exemplo da página Erros de sincronização de diretório](../media/882094a3-80d3-4aae-b90b-78b27047974c.png)

4. <span data-ttu-id="69fdd-114">Escolha qualquer um dos erros para exibir o painel de detalhes com informações sobre o erro e dicas sobre como corrigi-lo.</span><span class="sxs-lookup"><span data-stu-id="69fdd-114">Choose any of the errors to display the details pane with information about the error and tips on how to fix it.</span></span>

   ![Exemplo dos detalhes de um erro de sincronização de diretório](../media/a6e302d4-6be7-4e3a-b4b5-81c5a2c02952.png)
  
<span data-ttu-id="69fdd-116">Após a exibição, consulte [corrigir problemas com a sincronização](fix-problems-with-directory-synchronization.md) de diretórios Microsoft 365 corrigir quaisquer problemas identificados.</span><span class="sxs-lookup"><span data-stu-id="69fdd-116">After viewing, see [fixing problems with directory synchronization for Microsoft 365](fix-problems-with-directory-synchronization.md) to correct any identified issues.</span></span>