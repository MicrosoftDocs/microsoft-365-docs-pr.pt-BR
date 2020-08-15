---
title: Usar Lean pop-ups para reduzir a memória usada ao ler mensagens de email
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/3/2019
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a6d6ba01-2562-4c3d-a8f1-78748dd506cf
f1.keywords:
- NOCSH
description: Este artigo contém informações sobre como usar o Lean pop-ups para melhorar o desempenho de download de mensagens no Outlook na Web.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7bf53464ac6b2783fbbfc335fd4ff73dbe4435fb
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687408"
---
# <a name="use-lean-popouts-to-reduce-memory-used-when-reading-mail-messages"></a><span data-ttu-id="f83a8-103">Usar Lean pop-ups para reduzir a memória usada ao ler mensagens de email</span><span class="sxs-lookup"><span data-stu-id="f83a8-103">Use lean popouts to reduce memory used when reading mail messages</span></span>

<span data-ttu-id="f83a8-104">Este artigo contém informações para melhorar o desempenho de download de mensagens no Outlook na Web.</span><span class="sxs-lookup"><span data-stu-id="f83a8-104">This article contains information for improving message download performance in Outlook on the web.</span></span> <span data-ttu-id="f83a8-105">Este artigo faz parte do [planejamento de rede e ajuste de desempenho para o projeto do Office 365](https://aka.ms/tune) .</span><span class="sxs-lookup"><span data-stu-id="f83a8-105">This article is part of the [Network planning and performance tuning for Office 365](https://aka.ms/tune) project.</span></span>
  
<span data-ttu-id="f83a8-106">Como administrador global do Office 365, você pode configurar o Outlook na Web para fornecer _Lean pop-ups_, uma versão menor e menos intensa de memória de determinadas mensagens de email no Microsoft Edge ou no Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="f83a8-106">As an Office 365 global administrator, you can configure Outlook on the web to deliver _lean popouts_, a smaller, less memory-intensive version of certain email messages in Microsoft Edge or Internet Explorer.</span></span> <span data-ttu-id="f83a8-107">Quando o Lean pop-ups é configurado para o Outlook na Web, os componentes renderizados no servidor são carregados que otimizam o desempenho.</span><span class="sxs-lookup"><span data-stu-id="f83a8-107">When lean popouts are configured for Outlook on the web, server-side rendered components are loaded that optimize performance.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f83a8-108">A partir de março de 2018, Lean pop-ups não estão disponíveis para mensagens que especificam restrições de direitos de uso, como gerenciamento de direitos de informação (IRM).</span><span class="sxs-lookup"><span data-stu-id="f83a8-108">As of March 2018, lean popouts are not available for messages that specify usage rights restrictions, such as Information Rights Management (IRM).</span></span>
  
<span data-ttu-id="f83a8-109">Esses recursos continuarão a funcionar na janela principal, mas não estão disponíveis no Lean pop-ups:</span><span class="sxs-lookup"><span data-stu-id="f83a8-109">These features will continue to work in the main window but are not available in lean popouts:</span></span>
  
- <span data-ttu-id="f83a8-110">Suplementos do Outlook</span><span class="sxs-lookup"><span data-stu-id="f83a8-110">Outlook add-ins</span></span>
  
- <span data-ttu-id="f83a8-111">Presença do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="f83a8-111">Skype for Business presence</span></span>
  
## <a name="to-configure-lean-popouts-for-all-users-within-your-office-365-organization"></a><span data-ttu-id="f83a8-112">Para configurar o Lean pop-ups para todos os usuários na sua organização do Office 365</span><span class="sxs-lookup"><span data-stu-id="f83a8-112">To configure lean popouts for all users within your Office 365 organization</span></span>
  
1. <span data-ttu-id="f83a8-113">[Conecte-se ao Exchange Online usando o PowerShell remoto](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx ).</span><span class="sxs-lookup"><span data-stu-id="f83a8-113">[Connect to Exchange Online Using Remote PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx ).</span></span>
  
2. <span data-ttu-id="f83a8-114">Execute o cmdlet [Set-OrganizationConfig](https://technet.microsoft.com/library/aa997443%28v=exchg.160%29.aspx) com o parâmetro LeanPopoutEnabled da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="f83a8-114">Run the [Set-OrganizationConfig](https://technet.microsoft.com/library/aa997443%28v=exchg.160%29.aspx) cmdlet with the LeanPopoutEnabled parameter as follows:</span></span>

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled <$true |$false >
  ```

  <span data-ttu-id="f83a8-115">Por exemplo, para habilitar o Lean pop-ups para todos os usuários em sua organização:</span><span class="sxs-lookup"><span data-stu-id="f83a8-115">For example, to enable lean popouts for all users in your organization:</span></span>
  
  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $true
  ```

  <span data-ttu-id="f83a8-116">Para desabilitar o Lean pop-ups para todos os usuários em sua organização:</span><span class="sxs-lookup"><span data-stu-id="f83a8-116">To disable lean popouts for all users in your organization:</span></span>

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $false
  ```
