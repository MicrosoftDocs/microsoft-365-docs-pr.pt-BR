---
title: Usando domínio Conexão
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
description: Saiba como trabalhar com registradores Conexão domínio habilitados e adicionar seu domínio a Microsoft 365.
ms.openlocfilehash: 12e1f227c0a157414b56fd04f99e5460a1eb05d4
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/30/2021
ms.locfileid: "53227999"
---
# <a name="using-domain-connect"></a><span data-ttu-id="74c92-103">Usando domínio Conexão</span><span class="sxs-lookup"><span data-stu-id="74c92-103">Using Domain Connect</span></span>

 <span data-ttu-id="74c92-104">Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="74c92-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span>

<span data-ttu-id="74c92-105">[Os Conexão](https://www.domainconnect.org/) de domínio habilitados permitem que você adicione seu domínio Microsoft 365 em um processo de três etapas que leva minutos.</span><span class="sxs-lookup"><span data-stu-id="74c92-105">[Domain Connect](https://www.domainconnect.org/) enabled registrars let you add your domain to Microsoft 365 in a three-step process that takes minutes.</span></span>

<span data-ttu-id="74c92-106">No assistente, apenas confirmaremos se você é o próprio domínio e configurará automaticamente os registros do seu domínio, para que o email venha para o Microsoft 365 e outros serviços Microsoft 365, como Teams, trabalhem com seu domínio.</span><span class="sxs-lookup"><span data-stu-id="74c92-106">In the wizard, we'll just confirm that you own the domain, and then automatically set up your domain's records, so email comes to Microsoft 365 and other Microsoft 365 services, like Teams, work with your domain.</span></span>

> [!NOTE]
> <span data-ttu-id="74c92-107">Desative os bloqueadores de pop-up em seu navegador antes de iniciar o assistente de configuração.</span><span class="sxs-lookup"><span data-stu-id="74c92-107">Make sure you disable any popup blockers in your browser before you start the setup wizard.</span></span>

## <a name="domain-connect-registrars-integrating-with-microsoft-365"></a><span data-ttu-id="74c92-108">Registradores Conexão de domínio integrando-se com Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="74c92-108">Domain Connect registrars integrating with Microsoft 365</span></span>

- [<span data-ttu-id="74c92-109">1 &amp; 1 IONOS</span><span class="sxs-lookup"><span data-stu-id="74c92-109">1&amp;1 IONOS</span></span>](https://www.1and1.com/)
- [<span data-ttu-id="74c92-110">123Reg</span><span class="sxs-lookup"><span data-stu-id="74c92-110">123Reg</span></span>](https://www.123-reg.co.uk/)
- [<span data-ttu-id="74c92-111">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="74c92-111">GoDaddy</span></span>](https://www.godaddy.com/)
- [<span data-ttu-id="74c92-112">WordPress</span><span class="sxs-lookup"><span data-stu-id="74c92-112">WordPress</span></span>](https://wordpress.com/)
- [<span data-ttu-id="74c92-113">Plesk</span><span class="sxs-lookup"><span data-stu-id="74c92-113">Plesk</span></span>](https://www.plesk.com/)
- [<span data-ttu-id="74c92-114">MediaTemple</span><span class="sxs-lookup"><span data-stu-id="74c92-114">MediaTemple</span></span>](https://mediatemple.net/)
- <span data-ttu-id="74c92-115">SecureServer ou WildWestDomains (revendedores godaddy usando hospedagem DNS do SecureServer)</span><span class="sxs-lookup"><span data-stu-id="74c92-115">SecureServer or WildWestDomains (GoDaddy resellers using SecureServer DNS hosting)</span></span>
  - [<span data-ttu-id="74c92-116">Hospedagem da Web MadDog</span><span class="sxs-lookup"><span data-stu-id="74c92-116">MadDog Web Hosting</span></span>](https://maddogwebhosting.com/domains/)
  - [<span data-ttu-id="74c92-117">CheapNames</span><span class="sxs-lookup"><span data-stu-id="74c92-117">CheapNames</span></span>](https://www.cheapnames.com)

## <a name="what-happens-to-my-email-and-website"></a><span data-ttu-id="74c92-118">O que acontece com meu email e site?</span><span class="sxs-lookup"><span data-stu-id="74c92-118">What happens to my email and website?</span></span>

<span data-ttu-id="74c92-119">Depois de concluir a instalação, o registro MX do seu domínio é atualizado para apontar para Microsoft 365 e todos os emails para seu domínio começarão a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="74c92-119">After you finish setup, the MX record for your domain is updated to point to Microsoft 365 and all email for your domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="74c92-120">Certifique-se de adicionar usuários e configurar caixas de correio no Microsoft 365 para todos que receberem emails em seu domínio!</span><span class="sxs-lookup"><span data-stu-id="74c92-120">Make sure you've added users and set up mailboxes in Microsoft 365 for everyone who gets email on your domain!</span></span>

<span data-ttu-id="74c92-121">Se você tiver um site que usa com a empresa, ele continuará funcionando onde está.</span><span class="sxs-lookup"><span data-stu-id="74c92-121">If you have a website that you use with your business, it will keep working where it is.</span></span> <span data-ttu-id="74c92-122">As etapas Conexão de configuração de domínio não afetam seu site.</span><span class="sxs-lookup"><span data-stu-id="74c92-122">The Domain Connect setup steps don't affect your website.</span></span>
