---
title: Desativar os relatórios de lixo eletrônico no Outlook na Web
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 8d57fe9e-57b8-4884-9317-80b380804b4a
ms.collection:
- M365-security-compliance
description: Como um administrador do Office 365, você pode desativar a capacidade de os usuários reportarem email como lixo eletrônico.
ms.openlocfilehash: a2a8c2f9120ff4b1d2efab4d7ae63294ce7f923b
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37073858"
---
# <a name="turn-off-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="22d33-103">Desativar os relatórios de lixo eletrônico no Outlook na Web</span><span class="sxs-lookup"><span data-stu-id="22d33-103">Turn off junk email reporting in Outlook on the web</span></span>

<span data-ttu-id="22d33-104">Você pode enviar mensagens de lixo eletrônico, phishing e não é lixo eletrônico para a Microsoft para análise usando as opções de relatório de lixo eletrônico do Outlook na Web (anteriormente conhecido como Outlook Web App), conforme descrito em [relatar lixo eletrônico e golpes de phishing no Outlook na Web ](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md).</span><span class="sxs-lookup"><span data-stu-id="22d33-104">You can send junk, phishing, and not junk messages to Microsoft for analysis using the Outlook on the web (formerly known as Outlook Web App) junk email reporting options, as described in [Report junk email and phishing scams in Outlook on the web ](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md).</span></span> <span data-ttu-id="22d33-105">Se você não quiser usar essas opções, os administradores podem desativá-las por meio do cmdlet [Set-OwaMailboxPolicy](http://technet.microsoft.com/library/530166f7-ab42-4609-ba73-9b5a39b567be.aspx) .</span><span class="sxs-lookup"><span data-stu-id="22d33-105">If you don't want to use these options,admins can turn them off via the [Set-OwaMailboxPolicy](http://technet.microsoft.com/library/530166f7-ab42-4609-ba73-9b5a39b567be.aspx) cmdlet.</span></span> 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="22d33-106">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="22d33-106">What do you need to know before you begin?</span></span>
<span data-ttu-id="22d33-107"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="22d33-107"></span></span>

- <span data-ttu-id="22d33-108">Tempo estimado para conclusão: 5 minutos</span><span class="sxs-lookup"><span data-stu-id="22d33-108">Estimated time to complete: 5 minutes</span></span>
    
- <span data-ttu-id="22d33-109">Para executar este procedimento ou estes procedimentos, você precisa receber permissões.</span><span class="sxs-lookup"><span data-stu-id="22d33-109">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="22d33-110">Para ver de que permissões você precisa, consulte o entrada "diretivas de caixa de correio do Outlook na Web" no tópico [Outlook na Web Permissions](http://technet.microsoft.com/library/57eca42a-5a7f-4c65-89f0-7a84f2dbea19.aspx#OutlookWebApp) .</span><span class="sxs-lookup"><span data-stu-id="22d33-110">To see what permissions you need, see the "Outlook on the web mailbox policies" entry in the [Outlook on the web permissions](http://technet.microsoft.com/library/57eca42a-5a7f-4c65-89f0-7a84f2dbea19.aspx#OutlookWebApp) topic.</span></span> 

- <span data-ttu-id="22d33-111">Para se conectar ao Exchange Online PowerShell, confira [Conectar ao Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="22d33-111">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

## <a name="turn-off-junk-phishing-and-not-junk-reporting-to-microsoft"></a><span data-ttu-id="22d33-112">Desativar os relatórios de lixo eletrônico, phishing e não lixo eletrônico para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="22d33-112">Turn off junk, phishing, and not junk reporting to Microsoft</span></span>
<span data-ttu-id="22d33-113"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="22d33-113"></span></span>

<span data-ttu-id="22d33-114">Primeiro, execute o seguinte comando para obter os nomes das políticas de caixa de correio do Outlook disponíveis na Web:</span><span class="sxs-lookup"><span data-stu-id="22d33-114">First, run the following command to get the names of your available Outlook on the web mailbox policies:</span></span>
  
```
Get-OwaMailboxPolicy | Format-Table Name
```

<span data-ttu-id="22d33-115">Em seguida, use a seguinte sintaxe para habilitar ou desabilitar o lixo eletrônico e não os relatórios de lixo eletrônico para a Microsoft no Outlook na Web:</span><span class="sxs-lookup"><span data-stu-id="22d33-115">Next, use the following syntax to enable or disable junk and not junk reporting to Microsoft in Outlook on the web:</span></span>
  
```
Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
```

<span data-ttu-id="22d33-116">Este exemplo desativa o relatório na política de caixa de correio padrão do Outlook Web App:</span><span class="sxs-lookup"><span data-stu-id="22d33-116">This example turns off reporting in the default Outlook web app mailbox policy:</span></span>
  
```
Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
```

<span data-ttu-id="22d33-117">Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-OwaMailboxPolicy](http://technet.microsoft.com/library/bdd580d3-8812-4b4a-93e8-c6401b0d2f0f.aspx) e [Set-OwaMailboxPolicy](http://technet.microsoft.com/library/530166f7-ab42-4609-ba73-9b5a39b567be.aspx).</span><span class="sxs-lookup"><span data-stu-id="22d33-117">For detailed syntax and parameter information, see [Get-OwaMailboxPolicy](http://technet.microsoft.com/library/bdd580d3-8812-4b4a-93e8-c6401b0d2f0f.aspx) and [Set-OwaMailboxPolicy](http://technet.microsoft.com/library/530166f7-ab42-4609-ba73-9b5a39b567be.aspx).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="22d33-118">Como saber se funcionou?</span><span class="sxs-lookup"><span data-stu-id="22d33-118">How do you know this worked?</span></span>
<span data-ttu-id="22d33-119"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="22d33-119"></span></span>

<span data-ttu-id="22d33-120">Execute **Get-OwaMailboxPolicy** para verificar os valores de parâmetro e, em seguida, abra o Outlook na Web para um usuário afetado (que tenha a política de caixa de correio do Outlook na Web aplicada a eles) e verifique se as opções de relatório de lixo eletrônico, phishing e não estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="22d33-120">Run **Get-OWAMailboxPolicy** to check the parameter values, and then open Outlook on the web for an affected user (who has the Outlook on the web mailbox policy applied to them) and verify that the options to report junk, phishing, and not junk are not available.</span></span> <span data-ttu-id="22d33-121">Você ainda poderá marcar mensagens como lixo eletrônico, phishing e não lixo eletrônico, mas não poderá relatá-las.</span><span class="sxs-lookup"><span data-stu-id="22d33-121">You'll still be able to mark messages as junk, phishing, and not junk, but you won't be able to report them.</span></span> 
