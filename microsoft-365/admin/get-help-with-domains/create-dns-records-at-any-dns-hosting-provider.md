---
title: Adicionar registros DNS para conectar seu domínio
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
description: Aprenda a verificar seu domínio e criar registros DNS em qualquer provedor de hospedagem de DNS para o Microsoft 365.
ms.custom:
- okr_smb
- AdminSurgePortfolio
ms.openlocfilehash: 06a5e7d081a16cd8d5aae28268b3aaf737981a43
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051037"
---
# <a name="add-dns-records-to-connect-your-domain"></a><span data-ttu-id="387ec-103">Adicionar registros DNS para conectar seu domínio</span><span class="sxs-lookup"><span data-stu-id="387ec-103">Add DNS records to connect your domain</span></span>

<span data-ttu-id="387ec-104">Caso tenha comprado um domínio de um provedor de hospedagem de terceiros, você poderá conectá-lo ao Microsoft 365 atualizando os registros DNS na conta do seu registrador.</span><span class="sxs-lookup"><span data-stu-id="387ec-104">If you purchased a domain from a third-party hosting provider, you can connect it to Microsoft 365 by updating the DNS records in your registrar’s account.</span></span>

<span data-ttu-id="387ec-105">Ao concluir essas etapas, seu domínio permanecerá registrado no host do qual você comprou o domínio, mas o Microsoft 365 poderá usá-lo para seus endereços de email (como user@yourdomain.com) e outros serviços.</span><span class="sxs-lookup"><span data-stu-id="387ec-105">At the end of these steps, your domain will stay registered with the host that you purchased the domain from, but Microsoft 365 can use it for your email addresses (like user@yourdomain.com) and other services.</span></span>

<span data-ttu-id="387ec-106">Se você não adicionar um domínio, as pessoas da sua organização usarão o domínio onmicrosoft.com para os endereços de email deles até que você o faça.</span><span class="sxs-lookup"><span data-stu-id="387ec-106">If you don't add a domain, people in your organization will use the onmicrosoft.com domain for their email addresses until you do.</span></span> <span data-ttu-id="387ec-107">É importante adicionar seu domínio antes de adicionar usuários, para que você não precise configurá-los duas vezes.</span><span class="sxs-lookup"><span data-stu-id="387ec-107">It's important to add your domain before you add users, so you don't have to set them up twice.</span></span>

<span data-ttu-id="387ec-108">[Verifique as perguntas frequentes sobre domínios](../setup/domains-faq.yml) se você não encontrar o que está procurando abaixo.</span><span class="sxs-lookup"><span data-stu-id="387ec-108">[Check the Domains FAQ](../setup/domains-faq.yml) if you don't find what you're looking for below.</span></span>

## <a name="step-1-add-a-txt-or-mx-record-to-verify-you-own-the-domain"></a><span data-ttu-id="387ec-109">Etapa 1: adicionar um registro TXT ou MX para verificar se você é proprietário do domínio</span><span class="sxs-lookup"><span data-stu-id="387ec-109">Step 1: Add a TXT or MX record to verify you own the domain</span></span>

### <a name="recommended-verify-with-a-txt-record"></a><span data-ttu-id="387ec-110">Recomendado: verificar com um registro TXT</span><span class="sxs-lookup"><span data-stu-id="387ec-110">Recommended: Verify with a TXT record</span></span>

<span data-ttu-id="387ec-111">Primeiro, você precisa provar que é o proprietário do domínio que deseja adicionar ao Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="387ec-111">First, you need to prove you own the domain you want to add to Microsoft 365.</span></span>

1. <span data-ttu-id="387ec-112">Entre no [Centro de administração do Microsoft 365](https://admin.microsoft.com/) e selecione **Mostrar tudo > \*\*\*\*Configurações** > **Domínios**.</span><span class="sxs-lookup"><span data-stu-id="387ec-112">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com/) and select **Show all** > **Settings** > **Domains**.</span></span>
2. <span data-ttu-id="387ec-113">Em uma nova janela ou guia do navegador, entre no seu provedor de hospedagem de DNS e, em seguida, localize o local em que você gerencia suas configurações de DNS (por exemplo, Configurações de Arquivo de Zona, Gerenciar Domínios, Gerenciador de Domínio, Gerenciador de DNS).</span><span class="sxs-lookup"><span data-stu-id="387ec-113">In a new browser tab or window, sign in to your DNS hosting provider, and then find where you manage your DNS settings (e.g., Zone File Settings, Manage Domains, Domain Manager, DNS Manager).</span></span>
3. <span data-ttu-id="387ec-114">Vá para a página do Gerenciador DNS do seu provedor e adicione o registro TXT indicado no centro de administração ao seu domínio.</span><span class="sxs-lookup"><span data-stu-id="387ec-114">Go to your provider's DNS Manager page, and add the TXT record indicated in the admin center to your domain.</span></span>

<span data-ttu-id="387ec-115">A adição desse registro não afetará o seu email existente ou outros serviços e você poderá removê-lo com segurança logo que o seu domínio esteja conectado ao Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="387ec-115">Adding this record won't affect your existing email or other services and you can safely remove it once your domain is connected to Microsoft 365.</span></span>

<span data-ttu-id="387ec-116">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="387ec-116">Example:</span></span>
- <span data-ttu-id="387ec-117">Nome do TXT: `@`</span><span class="sxs-lookup"><span data-stu-id="387ec-117">TXT Name: `@`</span></span>
- <span data-ttu-id="387ec-118">Valor do TXT: MS=ms######## (ID exclusivo do centro de administração)</span><span class="sxs-lookup"><span data-stu-id="387ec-118">TXT Value: MS=ms######## (unique ID from the admin center)</span></span>
- <span data-ttu-id="387ec-119">TTL: `3600‎` (ou seu provedor padrão)</span><span class="sxs-lookup"><span data-stu-id="387ec-119">TTL: `3600‎` (or your provider default)</span></span>

4. <span data-ttu-id="387ec-120">Salve o registro, volte para o centro de administração e, em seguida, selecione **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="387ec-120">Save the record, go back to the admin center, and then select **Verify**.</span></span> <span data-ttu-id="387ec-121">Geralmente, leva cerca de 15 minutos para que as alterações de registro sejam registradas, mas, às vezes, pode ser mais demorado.</span><span class="sxs-lookup"><span data-stu-id="387ec-121">It typically takes around 15 minutes for record changes to register, but sometimes it can take longer.</span></span> <span data-ttu-id="387ec-122">Dê algum tempo e algumas tentativas para a mudança pegar.</span><span class="sxs-lookup"><span data-stu-id="387ec-122">Give it some time and a few tries to pick up the change.</span></span>

<span data-ttu-id="387ec-123">Quando a Microsoft encontrar o registro TXT correto, seu domínio estará verificado.</span><span class="sxs-lookup"><span data-stu-id="387ec-123">When Microsoft finds the correct TXT record, your domain is verified.</span></span>

### <a name="verify-with-an-mx-record"></a><span data-ttu-id="387ec-124">Verificar com um registro MX</span><span class="sxs-lookup"><span data-stu-id="387ec-124">Verify with an MX record</span></span>

<span data-ttu-id="387ec-125">Se seu registrador não for compatível com a adição de registros TXT, é possível verificar adicionando um registro MX.</span><span class="sxs-lookup"><span data-stu-id="387ec-125">If your registrar doesn't support adding TXT records, you can verify by adding an MX record.</span></span>

1. <span data-ttu-id="387ec-126">Entre no [Centro de administração do Microsoft 365](https://admin.microsoft.com/) e selecione **Mostrar tudo > \*\*\*\*Configurações** > **Domínios**.</span><span class="sxs-lookup"><span data-stu-id="387ec-126">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com/) and select **Show all** > **Settings** > **Domains**.</span></span>
2. <span data-ttu-id="387ec-127">Em uma nova janela ou guia do navegador, entre no seu provedor de hospedagem de DNS e, em seguida, localize o local em que você gerencia suas configurações de DNS (por exemplo, Configurações de Arquivo de Zona, Gerenciar Domínios, Gerenciador de Domínio, Gerenciador de DNS).</span><span class="sxs-lookup"><span data-stu-id="387ec-127">In a new browser tab or window, sign in to your DNS hosting provider, and then find where you manage your DNS settings (e.g., Zone File Settings, Manage Domains, Domain Manager, DNS Manager).</span></span>
3. <span data-ttu-id="387ec-128">Vá para a página do Gerenciador DNS do seu provedor e adicione o registro MX indicado no centro de administração ao seu domínio.</span><span class="sxs-lookup"><span data-stu-id="387ec-128">Go to your provider's DNS Manager page, and add the MX record indicated in the admin center to your domain.</span></span>

<span data-ttu-id="387ec-129">A **Prioridade** do registro MX deve ser o maior de todos os registros MX existentes do domínio.</span><span class="sxs-lookup"><span data-stu-id="387ec-129">This MX record's **Priority** must be the highest of all existing MX records for the domain.</span></span> <span data-ttu-id="387ec-130">Caso contrário, isso pode interferir no envio e recebimento de emails.</span><span class="sxs-lookup"><span data-stu-id="387ec-130">Otherwise, it can interfere with sending and receiving email.</span></span> <span data-ttu-id="387ec-131">Você deve excluir esses registros assim que a verificação de domínio concluir.</span><span class="sxs-lookup"><span data-stu-id="387ec-131">You should delete this records as soon as domain verification is complete.</span></span>

<span data-ttu-id="387ec-132">Verifique se os campos estão definidos para os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="387ec-132">Make sure that the fields are set to the following values:</span></span>

- <span data-ttu-id="387ec-133">Tipo de Registro: `MX`</span><span class="sxs-lookup"><span data-stu-id="387ec-133">Record Type: `MX`</span></span>
- <span data-ttu-id="387ec-134">Prioridade: definir para o maior valor disponível, geralmente `0`.</span><span class="sxs-lookup"><span data-stu-id="387ec-134">Priority: Set to the highest value available, typically `0`.</span></span>
- <span data-ttu-id="387ec-135">Nome do Host: `@`</span><span class="sxs-lookup"><span data-stu-id="387ec-135">Host Name: `@`</span></span>
- <span data-ttu-id="387ec-136">Pontos de endereçamento: copie o valor do centro de administração e cole-o aqui.</span><span class="sxs-lookup"><span data-stu-id="387ec-136">Points to address: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="387ec-137">TTL: `3600‎` (ou seu provedor padrão)</span><span class="sxs-lookup"><span data-stu-id="387ec-137">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="387ec-138">Quando a Microsoft encontrar o registro MX correto, seu domínio será verificado.</span><span class="sxs-lookup"><span data-stu-id="387ec-138">When Microsoft finds the correct MX record, your domain is verified.</span></span>

## <a name="step-2-add-dns-records-to-connect-microsoft-services"></a><span data-ttu-id="387ec-139">Etapa 2: adicionar registros DNS para conectar os serviços Microsoft</span><span class="sxs-lookup"><span data-stu-id="387ec-139">Step 2: Add DNS records to connect Microsoft services</span></span>

<span data-ttu-id="387ec-140">Em uma nova janela ou guia do navegador, entre no seu provedor de hospedagem de DNS e localize o local em que você gerencia suas configurações de DNS (por exemplo, Configurações de Arquivo de Zona, Gerenciar Domínios, Gerenciador de Domínio, Gerenciador de DNS).</span><span class="sxs-lookup"><span data-stu-id="387ec-140">In a new browser tab or window, sign in to your DNS hosting provider, and find where you manage your DNS settings (e.g., Zone File Settings, Manage Domains, Domain Manager, DNS Manager).</span></span>

<span data-ttu-id="387ec-141">Você adicionará vários tipos diferentes de registros DNS dependendo dos serviços que deseja habilitar.</span><span class="sxs-lookup"><span data-stu-id="387ec-141">You'll be adding several different types of DNS records depending on the services you want to enable.</span></span> 

### <a name="add-an-mx-record-for-email-outlook-exchange-online"></a><span data-ttu-id="387ec-142">Adicionar um registro MX para email (Outlook, Exchange Online)</span><span class="sxs-lookup"><span data-stu-id="387ec-142">Add an MX record for email (Outlook, Exchange Online)</span></span>
<span data-ttu-id="387ec-143">**Antes de começar:** se os usuários já têm um email com seu domínio (como user@yourdomain.com), crie suas contas no centro de administração antes de configurar seus registros MX.</span><span class="sxs-lookup"><span data-stu-id="387ec-143">**Before you begin:** If users already have email with your domain (such as user@yourdomain.com), create their accounts in the admin center before you set up your MX records.</span></span> <span data-ttu-id="387ec-144">Dessa forma, eles continuarão a receber emails.</span><span class="sxs-lookup"><span data-stu-id="387ec-144">That way, they’ll continue to receive email.</span></span> <span data-ttu-id="387ec-145">Quando você atualiza o registro MX do domínio, todos os novos emails das pessoas que usam esse domínio agora vão para o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="387ec-145">When you update your domain's MX record, all new email for anyone who uses your domain will now come to Microsoft 365.</span></span> <span data-ttu-id="387ec-146">Todos os e-mails existentes permanecem no organizador atual, a menos que você decida [migrar e-mails e contato para o Microsoft 365.](../setup/migrate-email-and-contacts-admin.md)</span><span class="sxs-lookup"><span data-stu-id="387ec-146">Any email you already have will stay at your current email host, unless you decide to [migrate email and contacts to Microsoft 365.](../setup/migrate-email-and-contacts-admin.md)</span></span>

<span data-ttu-id="387ec-147">Você obterá informações sobre o registro MX no assistente de configuração de domínio do centro de administração.</span><span class="sxs-lookup"><span data-stu-id="387ec-147">You'll get the information for the MX record from the admin center domain setup wizard.</span></span>

<span data-ttu-id="387ec-148">No site do provedor de hospedagem, crie um novo registro MX.</span><span class="sxs-lookup"><span data-stu-id="387ec-148">On your hosting provider's website, add a new MX record.</span></span>
<span data-ttu-id="387ec-149">Verifique se os campos estão definidos para os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="387ec-149">Make sure that the fields are set to the following values:</span></span>

- <span data-ttu-id="387ec-150">Tipo de Registro: `MX`</span><span class="sxs-lookup"><span data-stu-id="387ec-150">Record Type: `MX`</span></span>
- <span data-ttu-id="387ec-151">Prioridade: definir para o maior valor disponível, geralmente `0`.</span><span class="sxs-lookup"><span data-stu-id="387ec-151">Priority: Set to the highest value available, typically `0`.</span></span>
- <span data-ttu-id="387ec-152">Nome do Host: `@`</span><span class="sxs-lookup"><span data-stu-id="387ec-152">Host Name: `@`</span></span>
- <span data-ttu-id="387ec-153">Pontos de endereçamento: copie o valor do centro de administração e cole-o aqui.</span><span class="sxs-lookup"><span data-stu-id="387ec-153">Points to address: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="387ec-154">TTL: `3600‎` (ou seu provedor padrão)</span><span class="sxs-lookup"><span data-stu-id="387ec-154">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="387ec-155">Salve o registro e remova todos os outros registros MX.</span><span class="sxs-lookup"><span data-stu-id="387ec-155">Save the record, and then remove any other MX records.</span></span>

### <a name="add-cname-records-to-connect-other-services-teams-exchange-online-aad-mdm"></a><span data-ttu-id="387ec-156">Adicionar registros CNAME para conectar outros serviços (Teams, Exchange Online, AAD, MDM)</span><span class="sxs-lookup"><span data-stu-id="387ec-156">Add CNAME records to connect other services (Teams, Exchange Online, AAD, MDM)</span></span>
<span data-ttu-id="387ec-157">Você obterá informações sobre os registros CNAME no assistente de configuração de domínio do centro de administração.</span><span class="sxs-lookup"><span data-stu-id="387ec-157">You'll get the information for the CNAME records from the admin center domain setup wizard.</span></span>

<span data-ttu-id="387ec-158">No site do seu provedor de hospedagem, adicione registros CNAME para cada serviço que você deseja conectar.</span><span class="sxs-lookup"><span data-stu-id="387ec-158">On your hosting provider's website, add CNAME records for each service that you want to connect.</span></span>
<span data-ttu-id="387ec-159">Verifique se os campos estão definidos para os seguintes valores para cada:</span><span class="sxs-lookup"><span data-stu-id="387ec-159">Make sure that the fields are set to the following values for each:</span></span>

- <span data-ttu-id="387ec-160">Tipo de Registro: `CNAME (Alias)`</span><span class="sxs-lookup"><span data-stu-id="387ec-160">Record Type: `CNAME (Alias)`</span></span>
- <span data-ttu-id="387ec-161">Host: cole os valores copiados do centro de administração aqui.</span><span class="sxs-lookup"><span data-stu-id="387ec-161">Host: Paste the values you copy from the admin center here.</span></span>
- <span data-ttu-id="387ec-162">Pontos de endereçamento: copie o valor do centro de administração e cole-o aqui.</span><span class="sxs-lookup"><span data-stu-id="387ec-162">Points to address: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="387ec-163">TTL: `3600‎` (ou seu provedor padrão)</span><span class="sxs-lookup"><span data-stu-id="387ec-163">TTL: `3600‎` (or your provider default)</span></span>


### <a name="add-or-edit-an-spf-txt-record-to-help-prevent-email-spam-outlook-exchange-online"></a><span data-ttu-id="387ec-164">Adicionar ou editar um registro SPF TXT para ajudar a evitar spam de email (Outlook, Exchange Online)</span><span class="sxs-lookup"><span data-stu-id="387ec-164">Add or edit an SPF TXT record to help prevent email spam (Outlook, Exchange Online)</span></span>
<span data-ttu-id="387ec-165">**Antes de começar:** se você já possui um registro SPF para seu domínio, não crie um novo para o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="387ec-165">**Before you begin:** If you already have an SPF record for your domain, don't create a new one for Microsoft 365.</span></span> <span data-ttu-id="387ec-166">Em vez disso, adicione os valores necessários do Microsoft 365 ao registro atual para que você tenha um *único* registro SPF que inclua os dois conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="387ec-166">Instead, add the required Microsoft 365 values to the current record on your hosting providers website so that you have a *single* SPF record that includes both sets of values.</span></span>

<span data-ttu-id="387ec-167">No site do seu host DNS, edite o registro SPF existente ou crie um.</span><span class="sxs-lookup"><span data-stu-id="387ec-167">On your hosting provider's website, edit the existing SPF record or create an SPF record.</span></span>
<span data-ttu-id="387ec-168">Verifique se os campos estão definidos para os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="387ec-168">Make sure that the fields are set to the following values:</span></span>

- <span data-ttu-id="387ec-169">Tipo de Registro: `TXT (Text)`</span><span class="sxs-lookup"><span data-stu-id="387ec-169">Record Type: `TXT (Text)`</span></span>
- <span data-ttu-id="387ec-170">Host: `@`</span><span class="sxs-lookup"><span data-stu-id="387ec-170">Host: `@`</span></span>
- <span data-ttu-id="387ec-171">Valor do TXT: `v=spf1 include:spf.protection.outlook.com -all`</span><span class="sxs-lookup"><span data-stu-id="387ec-171">TXT Value: `v=spf1 include:spf.protection.outlook.com -all`</span></span>
- <span data-ttu-id="387ec-172">TTL: `3600‎` (ou seu provedor padrão)</span><span class="sxs-lookup"><span data-stu-id="387ec-172">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="387ec-173">Salve o registro.</span><span class="sxs-lookup"><span data-stu-id="387ec-173">Save the record.</span></span>

<span data-ttu-id="387ec-174">Valide seu registro SPF usando uma destas [ferramentas de validação de SPF](/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain).</span><span class="sxs-lookup"><span data-stu-id="387ec-174">Validate your SPF record by using one of these [SPF validation tools](/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain)</span></span>

<span data-ttu-id="387ec-175">O SPF foi projetado para ajudar a evitar a falsificação, mas há técnicas de falsificação contra as quais o SPF não pode protegê-lo.</span><span class="sxs-lookup"><span data-stu-id="387ec-175">SPF is designed to help prevent spoofing, but there are spoofing techniques that SPF cannot protect against.</span></span> <span data-ttu-id="387ec-176">Para se proteger contra isso, depois de configurar o SPF, você também deve configurar o DKIM e o DMARC para o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="387ec-176">To protect against these, once you've set up SPF, you should also set up DKIM and DMARC for Microsoft 365.</span></span> 

<span data-ttu-id="387ec-177">Para começar, consulte [Usar DKIM para validar emails de saída enviados do seu domínio no Microsoft 365](../../security/defender-365-security/use-dkim-to-validate-outbound-email.md) e [Usar DMARC para validar emails no Microsoft 365](../../security/defender-365-security/use-dmarc-to-validate-email.md).</span><span class="sxs-lookup"><span data-stu-id="387ec-177">To get started, see [Use DKIM to validate outbound email sent from your domain in Microsoft 365](../../security/defender-365-security/use-dkim-to-validate-outbound-email.md) and [Use DMARC to validate email in Microsoft 365](../../security/defender-365-security/use-dmarc-to-validate-email.md).</span></span>

### <a name="add-srv-records-for-communications-services-teams-skype-for-business"></a><span data-ttu-id="387ec-178">Adicionar registros SRV para serviços de communications (Teams, Skype for Business)</span><span class="sxs-lookup"><span data-stu-id="387ec-178">Add SRV records for communications services (Teams, Skype for Business)</span></span>

<span data-ttu-id="387ec-179">No site do seu provedor de hospedagem, adicione registros SRV para cada serviço que você deseja conectar.</span><span class="sxs-lookup"><span data-stu-id="387ec-179">On your hosting provider's website, add SRV records for each service you want to connect.</span></span>
<span data-ttu-id="387ec-180">Verifique se os campos estão definidos para os seguintes valores para cada:</span><span class="sxs-lookup"><span data-stu-id="387ec-180">Make sure that the fields are set to the following values for each:</span></span>

- <span data-ttu-id="387ec-181">Tipo de Registro: `SRV (Service)`</span><span class="sxs-lookup"><span data-stu-id="387ec-181">Record Type: `SRV (Service)`</span></span>
- <span data-ttu-id="387ec-182">Nome: `@`</span><span class="sxs-lookup"><span data-stu-id="387ec-182">Name: `@`</span></span>
- <span data-ttu-id="387ec-183">Destino: copie o valor do centro de administração e cole-o aqui.</span><span class="sxs-lookup"><span data-stu-id="387ec-183">Target: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="387ec-184">Protocolo: copie o valor do centro de administração e cole-o aqui.</span><span class="sxs-lookup"><span data-stu-id="387ec-184">Protocol: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="387ec-185">Serviço: copie o valor do centro de administração e cole-o aqui.</span><span class="sxs-lookup"><span data-stu-id="387ec-185">Service: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="387ec-186">Prioridade: `100`</span><span class="sxs-lookup"><span data-stu-id="387ec-186">Priority: `100`</span></span>
- <span data-ttu-id="387ec-187">Espessura: `1`</span><span class="sxs-lookup"><span data-stu-id="387ec-187">Weight: `1`</span></span>
- <span data-ttu-id="387ec-188">Porta: copie o valor do centro de administração e cole-o aqui.</span><span class="sxs-lookup"><span data-stu-id="387ec-188">Port: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="387ec-189">TTL: `3600‎` (ou seu provedor padrão)</span><span class="sxs-lookup"><span data-stu-id="387ec-189">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="387ec-190">Salve o registro.</span><span class="sxs-lookup"><span data-stu-id="387ec-190">Save the record.</span></span>

#### <a name="srv-record-field-restrictions-and-workarounds"></a><span data-ttu-id="387ec-191">Restrições e soluções alternativas para campos de registro SRV</span><span class="sxs-lookup"><span data-stu-id="387ec-191">SRV record field restrictions and workarounds</span></span>
<span data-ttu-id="387ec-192">Alguns provedores de hospedagem impõem restrições aos valores dos campos dentro de registros SRV.</span><span class="sxs-lookup"><span data-stu-id="387ec-192">Some hosting providers impose restrictions on field values within SRV records.</span></span> <span data-ttu-id="387ec-193">Aqui estão algumas soluções alternativas comuns para essas restrições.</span><span class="sxs-lookup"><span data-stu-id="387ec-193">Here are some common workarounds for these restrictions.</span></span>

##### <a name="name"></a><span data-ttu-id="387ec-194">Nome</span><span class="sxs-lookup"><span data-stu-id="387ec-194">Name</span></span>
<span data-ttu-id="387ec-195">Se o seu provedor de hospedagem não permitir a definição desse campo como **@**, deixe-o em branco.</span><span class="sxs-lookup"><span data-stu-id="387ec-195">If your hosting provider doesn't allow setting this field to **@**, leave it blank.</span></span> <span data-ttu-id="387ec-196">Use esta abordagem *apenas* quando o provedor de hospedagem tiver campos separados para os valores de Serviço e Protocolo.</span><span class="sxs-lookup"><span data-stu-id="387ec-196">Use this approach *only* when your hosting provider has separate fields for the Service and Protocol values.</span></span> <span data-ttu-id="387ec-197">Caso contrário, consulte as observações a seguir sobre Serviço e Protocolo.</span><span class="sxs-lookup"><span data-stu-id="387ec-197">Otherwise, see the Service and Protocol notes below.</span></span>

##### <a name="service-and-protocol"></a><span data-ttu-id="387ec-198">Serviço e Protocolo</span><span class="sxs-lookup"><span data-stu-id="387ec-198">Service and Protocol</span></span>
<span data-ttu-id="387ec-199">Caso seu provedor de hospedagem não forneça esses campos para registros SRV, você deve especificar os valores **Serviço** e **Protocolo** no campo **Nome** do registro.</span><span class="sxs-lookup"><span data-stu-id="387ec-199">If your hosting provider doesn't provide these fields for SRV records, you must specify the **Service** and **Protocol** values in the record's **Name** field.</span></span> <span data-ttu-id="387ec-200">(Observação: dependendo do seu provedor de hospedagem, o campo **Nome** pode ser chamado de algo mais, como: **Host**, **Hostname** ou **Subdomínio**.) Para adicionar esses valores, crie uma única cadeia de caracteres e separe os valores com um ponto.</span><span class="sxs-lookup"><span data-stu-id="387ec-200">(Note: Depending on your hosting provider, the **Name** field might be called something else, like: **Host**, **Hostname**, or **Subdomain**.) To add these values, you create a single string, separating the values with a dot.</span></span> 

<span data-ttu-id="387ec-201">Exemplo: `_sip._tls`</span><span class="sxs-lookup"><span data-stu-id="387ec-201">Example: `_sip._tls`</span></span>

##### <a name="priority-weight-and-port-br"></a><span data-ttu-id="387ec-202">Prioridade, Espessura e Porta</span><span class="sxs-lookup"><span data-stu-id="387ec-202">Priority, Weight, and Port</span></span> <br>
<span data-ttu-id="387ec-203">Se o seu provedor de hospedagem não oferecer esses campos para registros SRV, você deve especificá-los no campo **Destino** do registro.</span><span class="sxs-lookup"><span data-stu-id="387ec-203">If your hosting provider doesn't provide these fields for SRV records, you must specify them in the record's **Target** field.</span></span> <span data-ttu-id="387ec-204">(Observação: dependendo do seu provedor de hospedagem, o campo **Destino** pode ter outro nome, como: **Conteúdo**, **Endereço IP** ou **Host de Destino**.)</span><span class="sxs-lookup"><span data-stu-id="387ec-204">(Note: Depending on your hosting provider, the **Target** field might be called something else, like: **Content**, **IP Address**, or **Target Host**.)</span></span> 

<span data-ttu-id="387ec-205">Para adicionar esses valores, crie uma única cadeia de caracteres, separando os valores com espaços e *às vezes terminando com um ponto* (verifique com o seu provedor se não tiver certeza).</span><span class="sxs-lookup"><span data-stu-id="387ec-205">To add these values, create a single string, separating the values with spaces and *sometimes ending with a dot* (check with your provider if you are unsure).</span></span> <span data-ttu-id="387ec-206">Os valores devem ser incluídos nesta ordem: Prioridade, Peso, Porta, Destino.</span><span class="sxs-lookup"><span data-stu-id="387ec-206">The values must be included in this order: Priority, Weight, Port, Target.</span></span> 

- <span data-ttu-id="387ec-207">Exemplo 1: `100 1 443 sipdir.online.lync.com.`</span><span class="sxs-lookup"><span data-stu-id="387ec-207">Example 1: `100 1 443 sipdir.online.lync.com.`</span></span>
- <span data-ttu-id="387ec-208">Exemplo 2: `100 1 443 sipdir.online.lync.com`</span><span class="sxs-lookup"><span data-stu-id="387ec-208">Example 2: `100 1 443 sipdir.online.lync.com`</span></span>