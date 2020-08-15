---
title: Desativar a sincronização de diretórios para o Microsoft 365
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
ms.assetid: ee5f861e-bd48-4267-83d1-a4ead4b4a00d
description: Neste artigo, Encontre informações sobre como usar o PowerShell para desativar a sincronização de diretório para o Microsoft 365.
ms.openlocfilehash: 0bd8591f91dcf20cb1061b3cd93f69511027bab1
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686890"
---
# <a name="turn-off-directory-synchronization-for-microsoft-365"></a>Desativar a sincronização de diretórios para o Microsoft 365
Você pode usar o PowerShell para desativar a sincronização de diretórios. No entanto, não é recomendável que você desative a sincronização de diretório como uma etapa de solução de problemas. Se precisar de ajuda para solucionar problemas de sincronização de diretórios, consulte o artigo [corrigindo problemas com a sincronização de diretórios para o Microsoft 365](fix-problems-with-directory-synchronization.md) . 
  
[Entre em contato com o suporte](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) para produtos de negócios, se necessário.
  
## <a name="turn-off-directory-synchronization"></a>Desativar a sincronização de diretórios  
Para desativar a sincronização de diretórios:
  
1. Primeiro, instale o software necessário e conecte-se à sua assinatura do Microsoft 365. Para obter instruções, consulte [conectar-se com o módulo Microsoft Azure Active Directory para Windows PowerShell](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).
    
2. Use [set-MsolDirSyncEnabled](https://go.microsoft.com/fwlink/p/?LinkId=821939) para desabilitar a sincronização de diretórios: 
    
  ```powershell
  Set-MsolDirSyncEnabled -EnableDirSync $false
  ```

>[!Note]
>Se você usar esse comando, deverá aguardar 72 horas para que possa ativar novamente a sincronização de diretório.
>
 
