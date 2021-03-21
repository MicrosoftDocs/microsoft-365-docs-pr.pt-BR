---
title: Usar pop-outs enxutos para reduzir a memória usada ao ler mensagens de email
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
description: Este artigo contém informações para usar pop-outs enxutos para melhorar o desempenho de download de mensagens no Outlook na Web.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0fec3e0267b7299e34de541a184cf92e99e260f1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925251"
---
# <a name="use-lean-popouts-to-reduce-memory-used-when-reading-mail-messages"></a><span data-ttu-id="0af86-103">Usar pop-outs enxutos para reduzir a memória usada ao ler mensagens de email</span><span class="sxs-lookup"><span data-stu-id="0af86-103">Use lean popouts to reduce memory used when reading mail messages</span></span>

<span data-ttu-id="0af86-104">Este artigo contém informações para melhorar o desempenho de download de mensagens no Outlook na Web.</span><span class="sxs-lookup"><span data-stu-id="0af86-104">This article contains information for improving message download performance in Outlook on the web.</span></span> <span data-ttu-id="0af86-105">Este artigo faz parte do projeto [Planejamento de rede e ajuste de desempenho do Office 365.](./network-planning-and-performance.md)</span><span class="sxs-lookup"><span data-stu-id="0af86-105">This article is part of the [Network planning and performance tuning for Office 365](./network-planning-and-performance.md) project.</span></span>
  
<span data-ttu-id="0af86-106">Como administrador global do Office 365, você pode configurar o Outlook na Web para fornecer _pop-outs enxutos,_ uma versão menor e menos intensa de memória de determinadas mensagens de email no Microsoft Edge ou no Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="0af86-106">As an Office 365 global administrator, you can configure Outlook on the web to deliver _lean popouts_, a smaller, less memory-intensive version of certain email messages in Microsoft Edge or Internet Explorer.</span></span> <span data-ttu-id="0af86-107">Quando os pop-outs enxutos são configurados para o Outlook na Web, os componentes renderizados do lado do servidor são carregados que otimizam o desempenho.</span><span class="sxs-lookup"><span data-stu-id="0af86-107">When lean popouts are configured for Outlook on the web, server-side rendered components are loaded that optimize performance.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0af86-108">A partir de março de 2018, os pop-outs enxutos não estão disponíveis para mensagens que especificam restrições de direitos de uso, como o Gerenciamento de Direitos de Informação (IRM).</span><span class="sxs-lookup"><span data-stu-id="0af86-108">As of March 2018, lean popouts are not available for messages that specify usage rights restrictions, such as Information Rights Management (IRM).</span></span>
  
<span data-ttu-id="0af86-109">Esses recursos continuarão a funcionar na janela principal, mas não estão disponíveis em pop-outs enxutos:</span><span class="sxs-lookup"><span data-stu-id="0af86-109">These features will continue to work in the main window but are not available in lean popouts:</span></span>
  
- <span data-ttu-id="0af86-110">Suplementos do Outlook</span><span class="sxs-lookup"><span data-stu-id="0af86-110">Outlook add-ins</span></span>
  
- <span data-ttu-id="0af86-111">Presença do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="0af86-111">Skype for Business presence</span></span>
  
## <a name="to-configure-lean-popouts-for-all-users-within-your-office-365-organization"></a><span data-ttu-id="0af86-112">Para configurar pop-outs enxutos para todos os usuários em sua organização do Office 365</span><span class="sxs-lookup"><span data-stu-id="0af86-112">To configure lean popouts for all users within your Office 365 organization</span></span>
  
1. <span data-ttu-id="0af86-113">[Conectar-se ao Exchange Online usando o PowerShell Remoto.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="0af86-113">[Connect to Exchange Online Using Remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>
  
2. <span data-ttu-id="0af86-114">Execute o cmdlet [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) com o parâmetro LeanPopoutEnabled da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="0af86-114">Run the [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) cmdlet with the LeanPopoutEnabled parameter as follows:</span></span>

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled <$true |$false >
  ```

  <span data-ttu-id="0af86-115">Por exemplo, para habilitar pop-outs enxutos para todos os usuários em sua organização:</span><span class="sxs-lookup"><span data-stu-id="0af86-115">For example, to enable lean popouts for all users in your organization:</span></span>
  
  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $true
  ```

  <span data-ttu-id="0af86-116">Para desabilitar os pop-outs enxutos para todos os usuários em sua organização:</span><span class="sxs-lookup"><span data-stu-id="0af86-116">To disable lean popouts for all users in your organization:</span></span>

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $false
  ```