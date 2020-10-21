---
title: Usando a conexão de domínio
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ec6f4bd8-5996-4505-ba68-afaf8a141fb9
description: Saiba como trabalhar com os registradores de conexão de domínio habilitado e adicione seu domínio ao Microsoft 365.
ms.openlocfilehash: e907317ec5b606c2fe73232a73c9abdfce26feea
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645342"
---
# <a name="using-domain-connect"></a><span data-ttu-id="b39c7-103">Usando a conexão de domínio</span><span class="sxs-lookup"><span data-stu-id="b39c7-103">Using Domain Connect</span></span>

 <span data-ttu-id="b39c7-104">Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="b39c7-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="b39c7-105">Os registradores habilitados para [conexão de domínio](https://www.domainconnect.org/) permitem que você adicione seu domínio ao Microsoft 365 em um processo de três etapas que leva minutos.</span><span class="sxs-lookup"><span data-stu-id="b39c7-105">[Domain Connect ](https://www.domainconnect.org/) enabled registrars let you add your domain to Microsoft 365 in a three-step process that takes minutes.</span></span> 
  
<span data-ttu-id="b39c7-106">No assistente, apenas confirmará que você é o proprietário do domínio e, em seguida, configurar automaticamente os registros do seu domínio, para que os emails sejam da Microsoft 365 e de outros serviços da Microsoft 365, como o Teams, trabalhem com seu domínio.</span><span class="sxs-lookup"><span data-stu-id="b39c7-106">In the wizard, we'll just confirm that you own the domain, and then automatically set up your domain's records, so email comes to Microsoft 365 and other Microsoft 365 services, like Teams, work with your domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b39c7-107">Desative os bloqueadores de pop-up em seu navegador antes de iniciar o assistente de configuração.</span><span class="sxs-lookup"><span data-stu-id="b39c7-107">Make sure you disable any popup blockers in your browser before you start the setup wizard.</span></span>
  
## <a name="domain-connect-registrars-integrating-with-microsoft-365"></a><span data-ttu-id="b39c7-108">Registradores de conexão de domínio que se integram ao Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b39c7-108">Domain Connect registrars integrating with Microsoft 365</span></span>

- [<span data-ttu-id="b39c7-109">1 &amp; 1 IONOS</span><span class="sxs-lookup"><span data-stu-id="b39c7-109">1&amp;1 IONOS</span></span>](https://www.1and1.com/)
- [<span data-ttu-id="b39c7-110">123Reg</span><span class="sxs-lookup"><span data-stu-id="b39c7-110">123Reg</span></span>](https://www.123-reg.co.uk/)
- [<span data-ttu-id="b39c7-111">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="b39c7-111">GoDaddy</span></span>](https://www.godaddy.com/)
- [<span data-ttu-id="b39c7-112">WordPress</span><span class="sxs-lookup"><span data-stu-id="b39c7-112">WordPress</span></span>](https://wordpress.com/)
- [<span data-ttu-id="b39c7-113">Plesk</span><span class="sxs-lookup"><span data-stu-id="b39c7-113">Plesk</span></span>](https://www.plesk.com/)
- [<span data-ttu-id="b39c7-114">MediaTemple</span><span class="sxs-lookup"><span data-stu-id="b39c7-114">MediaTemple</span></span>](https://mediatemple.net/)
- <span data-ttu-id="b39c7-115">SecureServer ou WildWestDomains (GoDaddy revendedores usando o SecureServer de Hospedagem de DNS)</span><span class="sxs-lookup"><span data-stu-id="b39c7-115">SecureServer or WildWestDomains (GoDaddy resellers using SecureServer DNS hosting)</span></span>
    - [<span data-ttu-id="b39c7-116">Domínios MadDog</span><span class="sxs-lookup"><span data-stu-id="b39c7-116">MadDog Domains</span></span>](https://www.maddogdomains.com/)
    - [<span data-ttu-id="b39c7-117">Baratosnames</span><span class="sxs-lookup"><span data-stu-id="b39c7-117">CheapNames</span></span>](https://www.cheapnames.com)

## <a name="what-happens-to-my-email-and-website"></a><span data-ttu-id="b39c7-118">O que acontece com meus emails e sites?</span><span class="sxs-lookup"><span data-stu-id="b39c7-118">What happens to my email and website?</span></span>

<span data-ttu-id="b39c7-119">Depois que você concluir a instalação, o registro MX do seu domínio será atualizado para apontar para o Microsoft 365 e todos os emails do seu domínio serão iniciados no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b39c7-119">After you finish setup, the MX record for your domain is updated to point to Microsoft 365 and all email for your domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="b39c7-120">Verifique se você adicionou usuários e configurou caixas de correio no Microsoft 365 para todas as pessoas que recebem emails no seu domínio!</span><span class="sxs-lookup"><span data-stu-id="b39c7-120">Make sure you've added users and set up mailboxes in Microsoft 365 for everyone who gets email on your domain!</span></span>
  
<span data-ttu-id="b39c7-121">Se você tiver um site que usa com a empresa, ele continuará funcionando onde está.</span><span class="sxs-lookup"><span data-stu-id="b39c7-121">If you have a website that you use with your business, it will keep working where it is.</span></span> <span data-ttu-id="b39c7-122">As etapas de configuração de conexão de domínio não afetam o site.</span><span class="sxs-lookup"><span data-stu-id="b39c7-122">The Domain Connect setup steps don't affect your website.</span></span>
