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
# <a name="turn-off-directory-synchronization-for-microsoft-365"></a><span data-ttu-id="cfb59-103">Desativar a sincronização de diretórios para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cfb59-103">Turn off directory synchronization for Microsoft 365</span></span>
<span data-ttu-id="cfb59-104">Você pode usar o PowerShell para desativar a sincronização de diretórios.</span><span class="sxs-lookup"><span data-stu-id="cfb59-104">You can use PowerShell to turn off directory synchronization.</span></span> <span data-ttu-id="cfb59-105">No entanto, não é recomendável que você desative a sincronização de diretório como uma etapa de solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="cfb59-105">However, it is not recommended that you turn off directory synchronization as a troubleshooting step.</span></span> <span data-ttu-id="cfb59-106">Se precisar de ajuda para solucionar problemas de sincronização de diretórios, consulte o artigo [corrigindo problemas com a sincronização de diretórios para o Microsoft 365](fix-problems-with-directory-synchronization.md) .</span><span class="sxs-lookup"><span data-stu-id="cfb59-106">If you need assistance with troubleshooting directory synchronization, see the [Fixing problems with directory synchronization for Microsoft 365](fix-problems-with-directory-synchronization.md) article.</span></span> 
  
<span data-ttu-id="cfb59-107">[Entre em contato com o suporte](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) para produtos de negócios, se necessário.</span><span class="sxs-lookup"><span data-stu-id="cfb59-107">[Contact support](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) for business products if needed.</span></span>
  
## <a name="turn-off-directory-synchronization"></a><span data-ttu-id="cfb59-108">Desativar a sincronização de diretórios</span><span class="sxs-lookup"><span data-stu-id="cfb59-108">Turn off directory synchronization</span></span>  
<span data-ttu-id="cfb59-109">Para desativar a sincronização de diretórios:</span><span class="sxs-lookup"><span data-stu-id="cfb59-109">To turn off Directory synchronization:</span></span>
  
1. <span data-ttu-id="cfb59-110">Primeiro, instale o software necessário e conecte-se à sua assinatura do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cfb59-110">First, install the required software and connect to your Microsoft 365 subscription.</span></span> <span data-ttu-id="cfb59-111">Para obter instruções, consulte [conectar-se com o módulo Microsoft Azure Active Directory para Windows PowerShell](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="cfb59-111">For instructions, see [Connect with the Microsoft Azure Active Directory Module for Windows PowerShell](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
    
2. <span data-ttu-id="cfb59-112">Use [set-MsolDirSyncEnabled](https://go.microsoft.com/fwlink/p/?LinkId=821939) para desabilitar a sincronização de diretórios:</span><span class="sxs-lookup"><span data-stu-id="cfb59-112">Use [Set-MsolDirSyncEnabled](https://go.microsoft.com/fwlink/p/?LinkId=821939) to disable directory synchronization:</span></span> 
    
  ```powershell
  Set-MsolDirSyncEnabled -EnableDirSync $false
  ```

>[!Note]
><span data-ttu-id="cfb59-113">Se você usar esse comando, deverá aguardar 72 horas para que possa ativar novamente a sincronização de diretório.</span><span class="sxs-lookup"><span data-stu-id="cfb59-113">If you use this command, you must wait 72 hours before you can turn directory synchronization back on.</span></span>
>
 
