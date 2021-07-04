---
title: Recuperar dados de relatório de locatários do cliente com Windows PowerShell para parceiros DAP
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: 893e5275-30b3-433f-8ecd-644f78f513e2
description: 'Resumo: use o Windows PowerShell remoto para Microsoft Exchange Online para recuperar os relatórios de locatários individuais do cliente.'
ms.openlocfilehash: 8a244e1178e64d27d5e0f061d094dccd39bb8275
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53290070"
---
# <a name="retrieve-customer-tenant-reporting-data-with-windows-powershell-for-delegated-access-permissions-dap-partners"></a><span data-ttu-id="985c3-103">Recuperar dados de relatório do locatário do cliente com o Windows PowerShell para parceiros com permissões de acesso delegado (DAP)</span><span class="sxs-lookup"><span data-stu-id="985c3-103">Retrieve customer tenant reporting data with Windows PowerShell for Delegated Access Permissions (DAP) partners</span></span>

<span data-ttu-id="985c3-104">*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="985c3-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="985c3-105">Use o Windows PowerShell remoto para Microsoft Exchange Online para recuperar relatórios de locatários de clientes individuais.</span><span class="sxs-lookup"><span data-stu-id="985c3-105">Use remote Windows PowerShell for Microsoft Exchange Online to retrieve reports from individual customer tenants.</span></span>

<span data-ttu-id="985c3-106">Os parceiros de Provedor de Soluções na Nuvem (CSP) podem acessar os dados que comem os relatórios de locatários do cliente diretamente por meio do Windows PowerShell remoto para Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="985c3-106">Syndication and Cloud Solution Provider (CSP) partners can access the data that makes up customer tenant reports directly via remote Windows PowerShell for Exchange Online PowerShell.</span></span> <span data-ttu-id="985c3-107">Isso permite aos parceiros coletar e salvar os dados dos relatórios e, em seguida, realizar outras operações neles.</span><span class="sxs-lookup"><span data-stu-id="985c3-107">This lets partners collect and save the reporting data and then perform other operations on it.</span></span> <span data-ttu-id="985c3-108">Depois de abrir uma conexão remota, recuperar dados de relatório de uma locação é o mesmo que executar qualquer cmdlet em uma locação do cliente.</span><span class="sxs-lookup"><span data-stu-id="985c3-108">After you open a remote connection, retrieving reporting data about a customer tenancy is identical to running any cmdlet against a customer tenancy.</span></span>

<span data-ttu-id="985c3-109">Neste artigo, você usa o Windows PowerShell remoto para Exchange Online se conectar a um único cliente e recuperar um relatório.</span><span class="sxs-lookup"><span data-stu-id="985c3-109">In this article, you use remote Windows PowerShell for Exchange Online to connect to a single customer tenancy and retrieve a report.</span></span> <span data-ttu-id="985c3-110">Por padrão, o Windows PowerShell não tem suporte para agregar dados de relatórios de várias locações do cliente.</span><span class="sxs-lookup"><span data-stu-id="985c3-110">By default, Windows PowerShell does not support aggregating reporting data from multiple customer tenancies.</span></span> <span data-ttu-id="985c3-111">Os relatórios que você recuperar com esse procedimento são destinados apenas ao  _DelegatedOrg_ para o qual você se conectar.</span><span class="sxs-lookup"><span data-stu-id="985c3-111">The reports you retrieve with this procedure are only for the  _DelegatedOrg_ that you connect to.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="985c3-112">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="985c3-112">Before you begin</span></span>

- <span data-ttu-id="985c3-p103">Você deve se conectar ao seu locatário do Exchange Online usando o Windows PowerShell remoto. Para obter instruções, confira [Conectar-se aos locatários do Exchange Online com o Windows PowerShell remoto para parceiros com permissões de acesso delegado (DAP)](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="985c3-p103">You need to connect to your Exchange Online tenant by using remote Windows PowerShell. For instructions, see [Connect to Exchange Online tenants with remote Windows PowerShell for Delegated Access Permissions (DAP) partners](/powershell/exchange/connect-to-exchange-online-powershell)</span></span>

## <a name="run-the-get-stalemailboxreport-sample"></a><span data-ttu-id="985c3-115">Executar a amostra do Get-StaleMailboxReport</span><span class="sxs-lookup"><span data-stu-id="985c3-115">Run the Get-StaleMailboxReport sample</span></span>

<span data-ttu-id="985c3-116">Após abrir uma sessão remota do Exchange Online, execute este comando para recuperar o **Get-StaleMailboxReport** para o intervalo de datas de 25/03/2015 a 31/03/2015.</span><span class="sxs-lookup"><span data-stu-id="985c3-116">After you have opened a remote session to Exchange Online, run this command to retrieve the **Get-StaleMailboxReport** for the date range 03/25/2015 through 03/31/2015.</span></span>

```powershell
Get-StaleMailboxReport -StartDate 03/25/2015 -EndDate 03/31/2015
```

<span data-ttu-id="985c3-p104">Há vários outros cmdlets de relatório disponíveis para o Exchange Online, para o Lync Online e para o SharePoint Online, dentre outros, que você pode usar para rastreamento de mensagens. Para saber mais sobre os cmdlets de relatórios disponíveis e sobre o Serviço Web de Relatório do Office 365, confira os tópicos da seção a seguir.</span><span class="sxs-lookup"><span data-stu-id="985c3-p104">There are many other reporting cmdlets available for Exchange Online, Lync Online, and SharePoint Online as well as others for message tracing that you can use. To find out more about the available reporting cmdlets and the Office 365 Reporting web service, see the topics in the following section.</span></span>

## <a name="see-also"></a><span data-ttu-id="985c3-119">Confira também</span><span class="sxs-lookup"><span data-stu-id="985c3-119">See also</span></span>

<span data-ttu-id="985c3-120">[Serviço Web de Relatório do Office 365](/previous-versions/office/developer/o365-enterprise-developers/jj984325(v=office.15))</span><span class="sxs-lookup"><span data-stu-id="985c3-120">[Office 365 Reporting web service](/previous-versions/office/developer/o365-enterprise-developers/jj984325(v=office.15))</span></span>

[<span data-ttu-id="985c3-121">Cmdlets de criação de relatórios no Exchange Online</span><span class="sxs-lookup"><span data-stu-id="985c3-121">Reporting cmdlets in Exchange Online</span></span>](/powershell/module/exchange/get-csclientdevicedetailreport)

[<span data-ttu-id="985c3-122">Ajuda para parceiros</span><span class="sxs-lookup"><span data-stu-id="985c3-122">Help for partners</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=533477)
