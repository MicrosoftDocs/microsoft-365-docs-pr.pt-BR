---
title: Gerenciar o Microsoft 365 com o Windows PowerShell para parceiros DAP
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- M365-subscription-management
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: be497751-596f-431d-b256-0a89d36a47ce
description: Como os parceiros de distribuição e provedor de soluções em nuvem (CSP) podem usar o Windows PowerShell para gerenciar os locatários do cliente Microsoft 365.
ms.openlocfilehash: a7b2fbb5423e3b923e17aa2d9c488e7dd085be35
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/10/2020
ms.locfileid: "47429873"
---
# <a name="how-to-manage-microsoft-365-with-windows-powershell-for-delegated-access-permissions-partners"></a><span data-ttu-id="30ed9-103">Como gerenciar o Microsoft 365 com o Windows PowerShell para parceiros com permissões de acesso delegado</span><span class="sxs-lookup"><span data-stu-id="30ed9-103">How to manage Microsoft 365 with Windows PowerShell for Delegated Access Permissions partners</span></span>

<span data-ttu-id="30ed9-104">*Este artigo se aplica tanto ao Microsoft 365 Enterprise quanto ao Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="30ed9-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="30ed9-105">Os Parceiros com Permissão de Acesso Delegada (DAP) são parceiros da Agregação e dos Provedores de Soluções em Nuvem (CSP).</span><span class="sxs-lookup"><span data-stu-id="30ed9-105">Delegated Access Permission (DAP) partners are Syndication and Cloud Solution Providers (CSP) Partners.</span></span> <span data-ttu-id="30ed9-106">Muitos são provedores de rede ou de telecomunicações.</span><span class="sxs-lookup"><span data-stu-id="30ed9-106">Many are network or telecom providers.</span></span> <span data-ttu-id="30ed9-107">Eles agrupam assinaturas do Microsoft 365 em suas ofertas de serviço.</span><span class="sxs-lookup"><span data-stu-id="30ed9-107">They bundle Microsoft 365 subscriptions into their service offerings.</span></span> <span data-ttu-id="30ed9-108">Ao vender uma assinatura do Microsoft 365, elas recebem automaticamente permissões de administração em nome de (AOBO) para o locações do cliente, para que possam administrar e relatar esses locações.</span><span class="sxs-lookup"><span data-stu-id="30ed9-108">When they sell a Microsoft 365 subscription, they're automatically granted Administer On Behalf Of (AOBO) permissions to the customer's tenancies so they can administer and report on those tenancies.</span></span> <span data-ttu-id="30ed9-109">Essas tarefas são difíceis de fazer no centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="30ed9-109">These tasks are difficult to do in the Microsoft 365 admin center.</span></span> <span data-ttu-id="30ed9-110">É muito mais fácil usar o PowerShell para a Microsoft 365 para realizar tarefas administrativas, como:</span><span class="sxs-lookup"><span data-stu-id="30ed9-110">It's much easier to use PowerShell for Microsoft 365 to do administrative tasks such as:</span></span>
- <span data-ttu-id="30ed9-111">Listar todos os **TenantIds** do cliente e seus domínios</span><span class="sxs-lookup"><span data-stu-id="30ed9-111">List all the customer **TenantIds** and their domains</span></span> 
- <span data-ttu-id="30ed9-112">Identificar todos os usuários em um locatário do cliente e suas licenças atribuídas</span><span class="sxs-lookup"><span data-stu-id="30ed9-112">Identify all users in a customer tenancy and their assigned licenses</span></span>
> [!NOTE]
> <span data-ttu-id="30ed9-113">Algumas tarefas administrativas só podem ser feitas no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="30ed9-113">Some administrative tasks can only be done in PowerShell.</span></span>

<span data-ttu-id="30ed9-114">Os artigos a seguir mostram como os parceiros de agregação e CSP usam o PowerShell para administrar seus locações de cliente:</span><span class="sxs-lookup"><span data-stu-id="30ed9-114">The following articles show how Syndication and CSP partners use PowerShell to administer their customer tenancies:</span></span>
  
- [<span data-ttu-id="30ed9-115">Gerenciar locatários do Microsoft 365 com o Windows PowerShell para parceiros com permissões de acesso delegado (DAP)</span><span class="sxs-lookup"><span data-stu-id="30ed9-115">Manage Microsoft 365 tenants with Windows PowerShell for Delegated Access Permissions (DAP) partners</span></span>](manage-microsoft-365-tenants-with-windows-powershell-for-delegated-access-permissio.md)
    
- [<span data-ttu-id="30ed9-116">Adicionar um domínio a uma locação do cliente com o Windows PowerShell para parceiros com permissão de acesso delegado (DAP)</span><span class="sxs-lookup"><span data-stu-id="30ed9-116">Add a domain to a client tenancy with Windows PowerShell for Delegated Access Permission (DAP) partners</span></span>](add-a-domain-to-a-client-tenancy-with-windows-powershell-for-delegated-access-pe.md)
    
- [<span data-ttu-id="30ed9-117">Conectar-se ao PowerShell do Exchange Online </span><span class="sxs-lookup"><span data-stu-id="30ed9-117">Connect to Exchange Online PowerShell</span></span>](connect-to-exchange-online-tenants-with-remote-windows-powershell-for-delegated.md)
    
- [<span data-ttu-id="30ed9-118">Recuperar dados de relatório do locatário do cliente com o Windows PowerShell para parceiros com permissões de acesso delegado (DAP)</span><span class="sxs-lookup"><span data-stu-id="30ed9-118">Retrieve customer tenant reporting data with Windows PowerShell for Delegated Access Permissions (DAP) partners</span></span>](retrieve-customer-tenant-reporting-data-with-windows-powershell-for-delegated-ac.md)
   