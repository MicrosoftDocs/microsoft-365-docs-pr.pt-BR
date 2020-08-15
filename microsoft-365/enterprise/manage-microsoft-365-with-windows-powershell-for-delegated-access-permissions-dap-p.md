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
description: 'Resumo: os parceiros de distribuição e provedor de soluções em nuvem (CSP) podem usar o Windows PowerShell para gerenciar os locatários do cliente Microsoft 365.'
ms.openlocfilehash: d4109c09a14fb5644d34daf24383053536440871
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687380"
---
# <a name="manage-microsoft-365-with-windows-powershell-for-delegated-access-permissions-dap-partners"></a><span data-ttu-id="4a1a0-103">Gerenciar o Microsoft 365 com o Windows PowerShell para parceiros com permissões de acesso delegado (DAP)</span><span class="sxs-lookup"><span data-stu-id="4a1a0-103">Manage Microsoft 365 with Windows PowerShell for Delegated Access Permissions (DAP) partners</span></span>

<span data-ttu-id="4a1a0-104">*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="4a1a0-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="4a1a0-105">Os Parceiros com Permissão de Acesso Delegada (DAP) são parceiros da Agregação e dos Provedores de Soluções em Nuvem (CSP).</span><span class="sxs-lookup"><span data-stu-id="4a1a0-105">Delegated Access Permission (DAP) partners are Syndication and Cloud Solution Providers (CSP) Partners.</span></span> <span data-ttu-id="4a1a0-106">Muitas vezes, eles são provedores de rede ou de telecomunicações para outras empresas.</span><span class="sxs-lookup"><span data-stu-id="4a1a0-106">They are frequently network or telecom providers to other companies.</span></span> <span data-ttu-id="4a1a0-107">Eles agrupam assinaturas do Microsoft 365 em suas ofertas de serviço para seus clientes.</span><span class="sxs-lookup"><span data-stu-id="4a1a0-107">They bundle Microsoft 365 subscriptions into their service offerings to their customers.</span></span> <span data-ttu-id="4a1a0-108">Ao vender uma assinatura do Microsoft 365, elas recebem automaticamente as permissões de administração em nome de (AOBO) para o cliente locações, para que possam administrar e relatar o locações do cliente.</span><span class="sxs-lookup"><span data-stu-id="4a1a0-108">When they sell a Microsoft 365 subscription, they are automatically granted Administer On Behalf Of (AOBO) permissions to the customer tenancies so they can administer and report on the customer tenancies.</span></span> <span data-ttu-id="4a1a0-109">Na melhor das hipóteses, isso é difícil e demorado para fazer no centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4a1a0-109">At best, this is difficult and time consuming to do in the Microsoft 365 admin center.</span></span> <span data-ttu-id="4a1a0-110">É muito mais fácil realizar tarefas administrativas, como listar todos os **TenantIds** do cliente e seus domínios ou identificar todos os usuários em um locatário do cliente e quais licenças são atribuídas usando o PowerShell para Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4a1a0-110">It is much easier to do administrative tasks like listing all the customer **TenantIds** and their domains or identifying all users in a customer tenancy and what licenses they are assigned by using PowerShell for Microsoft 365.</span></span> <span data-ttu-id="4a1a0-111">Em alguns casos, é possível executar essas tarefas administrativas somente no PowerShell para o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4a1a0-111">In some cases, it is possible to do these administrative tasks only in PowerShell for Microsoft 365.</span></span> <span data-ttu-id="4a1a0-112">Veja alguns exemplos de cenários cujos parceiros de agregação e CSP utilizam com mais frequência para administrar as locações de clientes:</span><span class="sxs-lookup"><span data-stu-id="4a1a0-112">Here are samples of scenarios that Syndication and CSP partners most frequently use to administer their customer tenancies:</span></span>
  
## 

- [<span data-ttu-id="4a1a0-113">Gerenciar locatários do Microsoft 365 com o Windows PowerShell para parceiros com permissões de acesso delegado (DAP)</span><span class="sxs-lookup"><span data-stu-id="4a1a0-113">Manage Microsoft 365 tenants with Windows PowerShell for Delegated Access Permissions (DAP) partners</span></span>](manage-microsoft-365-tenants-with-windows-powershell-for-delegated-access-permissio.md)
    
- [<span data-ttu-id="4a1a0-114">Adicionar um domínio a uma locação do cliente com o Windows PowerShell para parceiros com permissão de acesso delegado (DAP)</span><span class="sxs-lookup"><span data-stu-id="4a1a0-114">Add a domain to a client tenancy with Windows PowerShell for Delegated Access Permission (DAP) partners</span></span>](add-a-domain-to-a-client-tenancy-with-windows-powershell-for-delegated-access-pe.md)
    
- [<span data-ttu-id="4a1a0-115">Conectar-se aos locatários do Exchange Online com o Windows PowerShell remoto para parceiros com permissões de acesso delegado (DAP)</span><span class="sxs-lookup"><span data-stu-id="4a1a0-115">Connect to Exchange Online tenants with remote Windows PowerShell for Delegated Access Permissions (DAP) partners</span></span>](connect-to-exchange-online-tenants-with-remote-windows-powershell-for-delegated.md)
    
- [<span data-ttu-id="4a1a0-116">Recuperar dados de relatório do locatário do cliente com o Windows PowerShell para parceiros com permissões de acesso delegado (DAP)</span><span class="sxs-lookup"><span data-stu-id="4a1a0-116">Retrieve customer tenant reporting data with Windows PowerShell for Delegated Access Permissions (DAP) partners</span></span>](retrieve-customer-tenant-reporting-data-with-windows-powershell-for-delegated-ac.md)
    

    

