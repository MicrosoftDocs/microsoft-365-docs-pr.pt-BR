---
title: Conectar seu domínio ao Microsoft 365
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- MET150
ROBOTS: NOINDEX, NOFOLLOW
description: Aprenda a verificar seu domínio e criar registros DNS com o Microsoft 365.
ms.custom:
- AdminSurgePortfolio
ms.openlocfilehash: c5c33af8a5635d1092aec2f1bffdfc942f2e4851
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126330"
---
# <a name="connect-your-domain-to-microsoft-365"></a><span data-ttu-id="df0df-103">Conectar seu domínio ao Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="df0df-103">Connect your domain to Microsoft 365</span></span>

> [!NOTE]
> <span data-ttu-id="df0df-104">Se você não adicionar um domínio, as pessoas da sua organização usarão o domínio onmicrosoft.com para os endereços de email deles até que você o faça.</span><span class="sxs-lookup"><span data-stu-id="df0df-104">If you don't add a domain, people in your organization will use the onmicrosoft.com domain for their email addresses until you do.</span></span> <span data-ttu-id="df0df-105">É importante adicionar seu domínio antes de adicionar usuários, para que você não precise configurá-los duas vezes.</span><span class="sxs-lookup"><span data-stu-id="df0df-105">It's important to add your domain before you add users, so you don't have to set them up twice.</span></span>

<span data-ttu-id="df0df-106">[Verifique as perguntas frequentes sobre domínios](../setup/domains-faq.yml) se você não encontrar o que está procurando abaixo.</span><span class="sxs-lookup"><span data-stu-id="df0df-106">[Check the Domains FAQ](../setup/domains-faq.yml) if you don't find what you're looking for below.</span></span>

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="df0df-107">Adicione um registro MX para que o email do domínio vá para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="df0df-107">Add an MX record so email for your domain will come to Microsoft</span></span>

<span data-ttu-id="df0df-108">Você obterá informações sobre o registro MX no assistente de configuração de domínio do centro de administração.</span><span class="sxs-lookup"><span data-stu-id="df0df-108">You'll get the information for the MX record from the admin center domain setup wizard.</span></span>

<span data-ttu-id="df0df-109">No site do provedor de hospedagem, crie um novo registro MX.</span><span class="sxs-lookup"><span data-stu-id="df0df-109">On your hosting provider's website, add a new MX record.</span></span>
<span data-ttu-id="df0df-110">Verifique se os campos estão definidos para os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="df0df-110">Make sure that the fields are set to the following values:</span></span>

- <span data-ttu-id="df0df-111">Tipo de Registro: `MX`</span><span class="sxs-lookup"><span data-stu-id="df0df-111">Record Type: `MX`</span></span>
- <span data-ttu-id="df0df-112">Prioridade: definir para o maior valor disponível, geralmente `0`.</span><span class="sxs-lookup"><span data-stu-id="df0df-112">Priority: Set to the highest value available, typically `0`.</span></span>
- <span data-ttu-id="df0df-113">Nome do Host: `@`</span><span class="sxs-lookup"><span data-stu-id="df0df-113">Host Name: `@`</span></span>
- <span data-ttu-id="df0df-114">Pontos de endereçamento: copie o valor do centro de administração e cole-o aqui.</span><span class="sxs-lookup"><span data-stu-id="df0df-114">Points to address: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="df0df-115">TTL: `3600‎` (ou seu provedor padrão)</span><span class="sxs-lookup"><span data-stu-id="df0df-115">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="df0df-116">Salve o registro e remova todos os outros registros MX.</span><span class="sxs-lookup"><span data-stu-id="df0df-116">Save the record, and then remove any other MX records.</span></span>

## <a name="add-a-cname-record-to-connect-users-to-their-mailboxes"></a><span data-ttu-id="df0df-117">Adicionar um registro CNAME para conectar os usuários às suas caixas de correio</span><span class="sxs-lookup"><span data-stu-id="df0df-117">Add a CNAME record to connect users to their mailboxes</span></span>
<span data-ttu-id="df0df-118">Você obterá informações sobre os registros CNAME no assistente de configuração de domínio do centro de administração.</span><span class="sxs-lookup"><span data-stu-id="df0df-118">You'll get the information for the CNAME records from the admin center domain setup wizard.</span></span>

<span data-ttu-id="df0df-119">No site do seu provedor de hospedagem, adicione o registro CNAME a seguir.</span><span class="sxs-lookup"><span data-stu-id="df0df-119">On your hosting provider's website, add the following CNAME record.</span></span> <span data-ttu-id="df0df-120">Verifique se os campos estão definidos para os seguintes valores para cada:</span><span class="sxs-lookup"><span data-stu-id="df0df-120">Make sure that the fields are set to the following values for each:</span></span>

- <span data-ttu-id="df0df-121">Tipo de Registro: `CNAME (Alias)`</span><span class="sxs-lookup"><span data-stu-id="df0df-121">Record Type: `CNAME (Alias)`</span></span>
- <span data-ttu-id="df0df-122">Host: cole os valores copiados do centro de administração aqui.</span><span class="sxs-lookup"><span data-stu-id="df0df-122">Host: Paste the values you copy from the admin center here.</span></span>
- <span data-ttu-id="df0df-123">Pontos de endereçamento: copie o valor do centro de administração e cole-o aqui.</span><span class="sxs-lookup"><span data-stu-id="df0df-123">Points to address: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="df0df-124">TTL: `3600‎` (ou seu provedor padrão)</span><span class="sxs-lookup"><span data-stu-id="df0df-124">TTL: `3600‎` (or your provider default)</span></span>

## <a name="add-a-txt-record-to-help-prevent-spam"></a><span data-ttu-id="df0df-125">Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail</span><span class="sxs-lookup"><span data-stu-id="df0df-125">Add a TXT record to help prevent spam</span></span>
<span data-ttu-id="df0df-126">**Antes de começar:** se você já possui um registro SPF para seu domínio, não crie um novo para o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="df0df-126">**Before you begin:** If you already have an SPF record for your domain, don't create a new one for Microsoft 365.</span></span> <span data-ttu-id="df0df-127">Em vez disso, adicione os valores necessários do Microsoft 365 ao registro atual para que você tenha um *único* registro SPF que inclua os dois conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="df0df-127">Instead, add the required Microsoft 365 values to the current record on your hosting providers website so that you have a *single* SPF record that includes both sets of values.</span></span>

<span data-ttu-id="df0df-128">No site do seu host DNS, edite o registro SPF existente ou crie um.</span><span class="sxs-lookup"><span data-stu-id="df0df-128">On your hosting provider's website, edit the existing SPF record or create an SPF record.</span></span>
<span data-ttu-id="df0df-129">Verifique se os campos estão definidos para os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="df0df-129">Make sure that the fields are set to the following values:</span></span>

- <span data-ttu-id="df0df-130">Tipo de Registro: `TXT (Text)`</span><span class="sxs-lookup"><span data-stu-id="df0df-130">Record Type: `TXT (Text)`</span></span>
- <span data-ttu-id="df0df-131">Host: `@`</span><span class="sxs-lookup"><span data-stu-id="df0df-131">Host: `@`</span></span>
- <span data-ttu-id="df0df-132">Valor do TXT: `v=spf1 include:spf.protection.outlook.com -all`</span><span class="sxs-lookup"><span data-stu-id="df0df-132">TXT Value: `v=spf1 include:spf.protection.outlook.com -all`</span></span>
- <span data-ttu-id="df0df-133">TTL: `3600‎` (ou seu provedor padrão)</span><span class="sxs-lookup"><span data-stu-id="df0df-133">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="df0df-134">Salve o registro.</span><span class="sxs-lookup"><span data-stu-id="df0df-134">Save the record.</span></span>

<span data-ttu-id="df0df-135">Valide seu registro SPF usando uma destas [ferramentas de validação de SPF](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain).</span><span class="sxs-lookup"><span data-stu-id="df0df-135">Validate your SPF record by using one of these [SPF validation tools](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain)</span></span>

<span data-ttu-id="df0df-136">O SPF foi projetado para ajudar a evitar a falsificação, mas há técnicas de falsificação contra as quais o SPF não pode protegê-lo.</span><span class="sxs-lookup"><span data-stu-id="df0df-136">SPF is designed to help prevent spoofing, but there are spoofing techniques that SPF cannot protect against.</span></span> <span data-ttu-id="df0df-137">Para se proteger contra isso, depois de configurar o SPF, você também deve configurar o DKIM e o DMARC para o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="df0df-137">To protect against these, once you've set up SPF, you should also set up DKIM and DMARC for Microsoft 365.</span></span>

<span data-ttu-id="df0df-138">Para começar, consulte [Usar DKIM para validar emails de saída enviados do seu domínio no Microsoft 365](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx) e [Usar DMARC para validar emails no Microsoft 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="df0df-138">To get started, see [Use DKIM to validate outbound email sent from your domain in Microsoft 365](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx) and [Use DMARC to validate email in Microsoft 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx).</span></span>

<span data-ttu-id="df0df-139">Por fim, volte para o assistente de configuração de domínio do centro de administração para concluir a configuração.</span><span class="sxs-lookup"><span data-stu-id="df0df-139">Finally, head back to the admin center domain setup wizard to complete your setup.</span></span>
