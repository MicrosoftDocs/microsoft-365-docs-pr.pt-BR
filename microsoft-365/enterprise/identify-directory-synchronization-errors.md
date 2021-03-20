---
title: Exibir erros de sincronização de diretório no Microsoft 365
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
description: Saiba como exibir erros de sincronização de diretório e possíveis correções no Centro de administração do Microsoft 365.
ms.openlocfilehash: 76717fc158aa0cee47f784919f19a295378bbd5b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907499"
---
# <a name="view-directory-synchronization-errors-in-microsoft-365"></a>Exibir erros de sincronização de diretório no Microsoft 365

Você pode exibir erros de sincronização de diretório no Centro de administração do Microsoft 365. Somente os erros do objeto User são exibidos. Para exibir erros com o PowerShell, consulte [Identificar objetos com DirSyncProvisioningErrors](/azure/active-directory/hybrid/how-to-connect-syncservice-duplicate-attribute-resiliency).

## <a name="view-directory-synchronization-errors-in-the-microsoft-365-admin-center"></a>Exibir erros de sincronização de diretório no centro de administração do Microsoft 365

Para exibir quaisquer erros no centro de administração do Microsoft 365:
  
1. Entre no Centro de administração do [Microsoft 365](https://admin.microsoft.com) com uma conta de administrador global. 
    
2. Na **home** page, você verá o **cartão de gerenciamento do** usuário. 
    
    ![O cartão de gerenciamento do usuário no centro de administração do Microsoft 365](../media/060006e9-de61-49d5-8979-e77cda198e71.png)
  
3. No cartão, escolha **Sincronizar erros** em **Azure AD Connect** para ver os erros na página **Erros de** sincronização de diretório.   
    
    ![Um exemplo da página Erros de sincronização de diretório](../media/882094a3-80d3-4aae-b90b-78b27047974c.png)

4. Escolha qualquer um dos erros para exibir o painel de detalhes com informações sobre o erro e dicas sobre como corrigi-lo.

   ![Exemplo dos detalhes de um erro de sincronização de diretório](../media/a6e302d4-6be7-4e3a-b4b5-81c5a2c02952.png)
  
Após a exibição, consulte a correção de problemas com a sincronização de diretórios do [Microsoft 365](fix-problems-with-directory-synchronization.md) para corrigir quaisquer problemas identificados.