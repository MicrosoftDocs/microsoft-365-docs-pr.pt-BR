---
title: Adicionar registros DNS para conectar seu domínio
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
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
ms.openlocfilehash: d3a9e3787afc30b33122edf91c1cf9e3dd84b847
ms.sourcegitcommit: 7c1b34205746ff0690ffc774a74bdfd434256cf5
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "45049661"
---
# <a name="add-dns-records-to-connect-your-domain"></a><span data-ttu-id="5f6af-103">Adicionar registros DNS para conectar seu domínio</span><span class="sxs-lookup"><span data-stu-id="5f6af-103">Add DNS records to connect your domain</span></span>

<span data-ttu-id="5f6af-104">Caso tenha comprado um domínio de um provedor de hospedagem de terceiros, você poderá conectá-lo ao Microsoft 365 atualizando os registros DNS na conta do seu registrador.</span><span class="sxs-lookup"><span data-stu-id="5f6af-104">If you purchased a domain from a third-party hosting provider, you can connect it to Microsoft 365 by updating the DNS records in your registrar’s account.</span></span>

<span data-ttu-id="5f6af-105">Ao concluir essas etapas, seu domínio permanecerá registrado no host do qual você comprou o domínio, mas o Microsoft 365 poderá usá-lo para seus endereços de email (como user@yourdomain.com) e outros serviços.</span><span class="sxs-lookup"><span data-stu-id="5f6af-105">At the end of these steps, your domain will stay registered with the host that you purchased the domain from, but Microsoft 365 can use it for you email addresses (like user@yourdomain.com) and other services.</span></span>

<span data-ttu-id="5f6af-106">Se você não adicionar um domínio, as pessoas da sua organização usarão o domínio onmicrosoft.com para os endereços de email deles até que você o faça.</span><span class="sxs-lookup"><span data-stu-id="5f6af-106">If you don't add a domain, people in your organization will use the onmicrosoft.com domain for their email addresses until you do.</span></span> <span data-ttu-id="5f6af-107">É importante adicionar seu domínio antes de adicionar usuários, para que você não precise configurá-los duas vezes.</span><span class="sxs-lookup"><span data-stu-id="5f6af-107">It's important to add your domain before you add users, so you don't have to set them up twice.</span></span>

<span data-ttu-id="5f6af-108">[Verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md) se você não encontrar o que está procurando abaixo.</span><span class="sxs-lookup"><span data-stu-id="5f6af-108">[Check the Domains FAQ](../setup/domains-faq.md) if you don't find what you're looking for below.</span></span>

## <a name="step-1-add-a-txt-record-to-verify-you-own-the-domain"></a><span data-ttu-id="5f6af-109">Etapa 1: adicionar um registro TXT para verificar se você é proprietário do domínio</span><span class="sxs-lookup"><span data-stu-id="5f6af-109">Step 1: Add a TXT record to verify you own the domain</span></span>

<span data-ttu-id="5f6af-110">Primeiro, você precisa provar que é o proprietário do domínio que deseja adicionar ao Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5f6af-110">First, you need to prove you own the domain you want to add to Microsoft 365.</span></span>

1. <span data-ttu-id="5f6af-111">Entre no [Centro de administração do Microsoft 365](https://admin.microsoft.com/) e selecione **Mostrar tudo > \*\*\*\*Configurações** > **Domínios**.</span><span class="sxs-lookup"><span data-stu-id="5f6af-111">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com/) and select **Show all** > **Settings** > **Domains**.</span></span>
2. <span data-ttu-id="5f6af-112">Em uma nova janela ou guia do navegador, entre no seu provedor de hospedagem de DNS e, em seguida, localize o local em que você gerencia suas configurações de DNS (por exemplo, Configurações de Arquivo de Zona, Gerenciar Domínios, Gerenciador de Domínio, Gerenciador de DNS).</span><span class="sxs-lookup"><span data-stu-id="5f6af-112">In a new browser tab or window, sign in to your DNS hosting provider, and then find where you manage your DNS settings (e.g., Zone File Settings, Manage Domains, Domain Manager, DNS Manager).</span></span>
3. <span data-ttu-id="5f6af-113">Vá para a página do Gerenciador DNS do seu provedor e adicione o registro TXT indicado no centro de administração ao seu domínio.</span><span class="sxs-lookup"><span data-stu-id="5f6af-113">Go to your provider's DNS Manager page, and add the TXT record indicated in the admin center to your domain.</span></span>

<span data-ttu-id="5f6af-114">A adição desse registro não afetará o seu email existente ou outros serviços e você poderá removê-lo com segurança logo que o seu domínio esteja conectado ao Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5f6af-114">Adding this record won't affect your existing email or other services and you can safely remove it once your domain is connected to Microsoft 365.</span></span>

<span data-ttu-id="5f6af-115">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="5f6af-115">Example:</span></span>
- <span data-ttu-id="5f6af-116">Nome do TXT: `@`</span><span class="sxs-lookup"><span data-stu-id="5f6af-116">TXT Name: `@`</span></span>
- <span data-ttu-id="5f6af-117">Valor do TXT: MS=ms######## (ID exclusivo do centro de administração)</span><span class="sxs-lookup"><span data-stu-id="5f6af-117">TXT Value: MS=ms######## (unique ID from the admin center)</span></span>
- <span data-ttu-id="5f6af-118">TTL: `3600‎` (ou seu provedor padrão)</span><span class="sxs-lookup"><span data-stu-id="5f6af-118">TTL: `3600‎` (or your provider default)</span></span>

4. <span data-ttu-id="5f6af-119">Salve o registro, volte para o centro de administração e, em seguida, selecione **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="5f6af-119">Save the record, go back to the admin center, and then select **Verify**.</span></span> <span data-ttu-id="5f6af-120">Geralmente, leva cerca de 15 minutos para que as alterações de registro sejam registradas, mas, às vezes, pode ser mais demorado.</span><span class="sxs-lookup"><span data-stu-id="5f6af-120">It typically takes around 15 minutes for record changes to register, but sometimes it can take longer.</span></span> <span data-ttu-id="5f6af-121">Dê algum tempo e algumas tentativas para a mudança pegar.</span><span class="sxs-lookup"><span data-stu-id="5f6af-121">Give it some time and a few tries to pick up the change.</span></span>

<span data-ttu-id="5f6af-122">Quando a Microsoft encontrar o registro TXT correto, seu domínio estará verificado.</span><span class="sxs-lookup"><span data-stu-id="5f6af-122">When Microsoft finds the correct TXT record, your domain is verified.</span></span>


## <a name="step-2-add-dns-records-to-connect-microsoft-services"></a><span data-ttu-id="5f6af-123">Etapa 2: adicionar registros DNS para conectar os serviços Microsoft</span><span class="sxs-lookup"><span data-stu-id="5f6af-123">Step 2: Add DNS records to connect Microsoft services</span></span>

<span data-ttu-id="5f6af-124">Em uma nova janela ou guia do navegador, entre no seu provedor de hospedagem de DNS e localize o local em que você gerencia suas configurações de DNS (por exemplo, Configurações de Arquivo de Zona, Gerenciar Domínios, Gerenciador de Domínio, Gerenciador de DNS).</span><span class="sxs-lookup"><span data-stu-id="5f6af-124">In a new browser tab or window, sign in to your DNS hosting provider, and find where you manage your DNS settings (e.g., Zone File Settings, Manage Domains, Domain Manager, DNS Manager).</span></span>

<span data-ttu-id="5f6af-125">Você adicionará vários tipos diferentes de registros DNS dependendo dos serviços que deseja habilitar.</span><span class="sxs-lookup"><span data-stu-id="5f6af-125">You'll be adding several different types of DNS records depending on the services you want to enable.</span></span> 

### <a name="add-an-mx-record-for-email-outlook-exchange-online"></a><span data-ttu-id="5f6af-126">Adicionar um registro MX para email (Outlook, Exchange Online)</span><span class="sxs-lookup"><span data-stu-id="5f6af-126">Add an MX record for email (Outlook, Exchange Online)</span></span>
<span data-ttu-id="5f6af-127">**Antes de começar:** se os usuários já têm um email com seu domínio (como user@yourdomain.com), crie suas contas no centro de administração antes de configurar seus registros MX.</span><span class="sxs-lookup"><span data-stu-id="5f6af-127">**Before you begin:** If users already have email with your domain (such as user@yourdomain.com), create their accounts in the admin center before you set up your MX records.</span></span> <span data-ttu-id="5f6af-128">Dessa forma, eles continuarão a receber emails.</span><span class="sxs-lookup"><span data-stu-id="5f6af-128">That way, they’ll continue to receive email.</span></span> <span data-ttu-id="5f6af-129">Quando você atualiza o registro MX do domínio, todos os novos emails das pessoas que usam esse domínio agora vão para o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5f6af-129">When you update your domain's MX record, all new email for anyone who uses your domain will now come to Microsoft 365.</span></span> <span data-ttu-id="5f6af-130">Todos os e-mails existentes permanecem no organizador atual, a menos que você decida [migrar e-mails e contato para o Microsoft 365.](../setup/migrate-email-and-contacts-admin.md)</span><span class="sxs-lookup"><span data-stu-id="5f6af-130">Any email you already have will stay at your current email host, unless you decide to [migrate email and contacts to Microsoft 365.](../setup/migrate-email-and-contacts-admin.md)</span></span>

<span data-ttu-id="5f6af-131">Você obterá informações sobre o registro MX no assistente de configuração de domínio do centro de administração.</span><span class="sxs-lookup"><span data-stu-id="5f6af-131">You'll get the information for the MX record from the admin center domain setup wizard.</span></span>

<span data-ttu-id="5f6af-132">No site do provedor de hospedagem, crie um novo registro MX.</span><span class="sxs-lookup"><span data-stu-id="5f6af-132">On your hosting provider's website, add a new MX record.</span></span>
<span data-ttu-id="5f6af-133">Verifique se os campos estão definidos para os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="5f6af-133">Make sure that the fields are set to the following values:</span></span>

- <span data-ttu-id="5f6af-134">Tipo de Registro: `MX`</span><span class="sxs-lookup"><span data-stu-id="5f6af-134">Record Type: `MX`</span></span>
- <span data-ttu-id="5f6af-135">Prioridade: definir para o maior valor disponível, geralmente `0`.</span><span class="sxs-lookup"><span data-stu-id="5f6af-135">Priority: Set to the highest value available, typically `0`.</span></span>
- <span data-ttu-id="5f6af-136">Nome do Host: `@`</span><span class="sxs-lookup"><span data-stu-id="5f6af-136">Host Name: `@`</span></span>
- <span data-ttu-id="5f6af-137">Pontos de endereçamento: copie o valor do centro de administração e cole-o aqui.</span><span class="sxs-lookup"><span data-stu-id="5f6af-137">Points to address: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="5f6af-138">TTL: `3600‎` (ou seu provedor padrão)</span><span class="sxs-lookup"><span data-stu-id="5f6af-138">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="5f6af-139">Salve o registro e remova todos os outros registros MX.</span><span class="sxs-lookup"><span data-stu-id="5f6af-139">Save the record, and then remove any other MX records.</span></span>

### <a name="add-cname-records-to-connect-other-services-teams-exchange-online-aad-mdm"></a><span data-ttu-id="5f6af-140">Adicionar registros CNAME para conectar outros serviços (Teams, Exchange Online, AAD, MDM)</span><span class="sxs-lookup"><span data-stu-id="5f6af-140">Add CNAME records to connect other services (Teams, Exchange Online, AAD, MDM)</span></span>
<span data-ttu-id="5f6af-141">Você obterá informações sobre os registros CNAME no assistente de configuração de domínio do centro de administração.</span><span class="sxs-lookup"><span data-stu-id="5f6af-141">You'll get the information for the CNAME records from the admin center domain setup wizard.</span></span>

<span data-ttu-id="5f6af-142">No site do seu provedor de hospedagem, adicione registros CNAME para cada serviço que você deseja conectar.</span><span class="sxs-lookup"><span data-stu-id="5f6af-142">On your hosting provider's website, add CNAME records for each service that you want to connect.</span></span>
<span data-ttu-id="5f6af-143">Verifique se os campos estão definidos para os seguintes valores para cada:</span><span class="sxs-lookup"><span data-stu-id="5f6af-143">Make sure that the fields are set to the following values for each:</span></span>

- <span data-ttu-id="5f6af-144">Tipo de Registro: `CNAME (Alias)`</span><span class="sxs-lookup"><span data-stu-id="5f6af-144">Record Type: `CNAME (Alias)`</span></span>
- <span data-ttu-id="5f6af-145">Host: cole os valores copiados do centro de administração aqui.</span><span class="sxs-lookup"><span data-stu-id="5f6af-145">Host: Paste the values you copy from the admin center here.</span></span>
- <span data-ttu-id="5f6af-146">Pontos de endereçamento: copie o valor do centro de administração e cole-o aqui.</span><span class="sxs-lookup"><span data-stu-id="5f6af-146">Points to address: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="5f6af-147">TTL: `3600‎` (ou seu provedor padrão)</span><span class="sxs-lookup"><span data-stu-id="5f6af-147">TTL: `3600‎` (or your provider default)</span></span>


### <a name="add-or-edit-an-spf-txt-record-to-help-prevent-email-spam-outlook-exchange-online"></a><span data-ttu-id="5f6af-148">Adicionar ou editar um registro SPF TXT para ajudar a evitar spam de email (Outlook, Exchange Online)</span><span class="sxs-lookup"><span data-stu-id="5f6af-148">Add or edit an SPF TXT record to help prevent email spam (Outlook, Exchange Online)</span></span>
<span data-ttu-id="5f6af-149">**Antes de começar:** se você já possui um registro SPF para seu domínio, não crie um novo para o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5f6af-149">**Before you begin:** If you already have an SPF record for your domain, don't create a new one for Microsoft 365.</span></span> <span data-ttu-id="5f6af-150">Em vez disso, adicione os valores necessários do Microsoft 365 ao registro atual para que você tenha um *único* registro SPF que inclua os dois conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="5f6af-150">Instead, add the required Microsoft 365 values to the current record on your hosting providers website so that you have a *single* SPF record that includes both sets of values.</span></span>

<span data-ttu-id="5f6af-151">No site do seu host DNS, edite o registro SPF existente ou crie um.</span><span class="sxs-lookup"><span data-stu-id="5f6af-151">On your hosting provider's website, edit the existing SPF record or create an SPF record.</span></span>
<span data-ttu-id="5f6af-152">Verifique se os campos estão definidos para os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="5f6af-152">Make sure that the fields are set to the following values:</span></span>

- <span data-ttu-id="5f6af-153">Tipo de Registro: `TXT (Text)`</span><span class="sxs-lookup"><span data-stu-id="5f6af-153">Record Type: `TXT (Text)`</span></span>
- <span data-ttu-id="5f6af-154">Host: `@`</span><span class="sxs-lookup"><span data-stu-id="5f6af-154">Host: `@`</span></span>
- <span data-ttu-id="5f6af-155">Valor do TXT: `v=spf1 include:spf.protection.outlook.com -all`</span><span class="sxs-lookup"><span data-stu-id="5f6af-155">TXT Value: `v=spf1 include:spf.protection.outlook.com -all`</span></span>
- <span data-ttu-id="5f6af-156">TTL: `3600‎` (ou seu provedor padrão)</span><span class="sxs-lookup"><span data-stu-id="5f6af-156">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="5f6af-157">Salve o registro.</span><span class="sxs-lookup"><span data-stu-id="5f6af-157">Save the record.</span></span>

<span data-ttu-id="5f6af-158">Valide seu registro SPF usando uma destas [ferramentas de validação de SPF](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain).</span><span class="sxs-lookup"><span data-stu-id="5f6af-158">Validate your SPF record by using one of these [SPF validation tools](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain)</span></span>

<span data-ttu-id="5f6af-159">O SPF foi projetado para ajudar a evitar a falsificação, mas há técnicas de falsificação contra as quais o SPF não pode protegê-lo.</span><span class="sxs-lookup"><span data-stu-id="5f6af-159">SPF is designed to help prevent spoofing, but there are spoofing techniques that SPF cannot protect against.</span></span> <span data-ttu-id="5f6af-160">Para se proteger contra isso, depois de configurar o SPF, você também deve configurar o DKIM e o DMARC para o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5f6af-160">To protect against these, once you've set up SPF, you should also set up DKIM and DMARC for Microsoft 365.</span></span> 

<span data-ttu-id="5f6af-161">Para começar, consulte [Usar DKIM para validar emails de saída enviados do seu domínio no Microsoft 365](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx) e [Usar DMARC para validar emails no Microsoft 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="5f6af-161">To get started, see [Use DKIM to validate outbound email sent from your domain in Microsoft 365](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx) and [Use DMARC to validate email in Microsoft 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx).</span></span>

### <a name="add-srv-records-for-communications-services-teams-skype-for-business"></a><span data-ttu-id="5f6af-162">Adicionar registros SRV para serviços de communications (Teams, Skype for Business)</span><span class="sxs-lookup"><span data-stu-id="5f6af-162">Add SRV records for communications services (Teams, Skype for Business)</span></span>

<span data-ttu-id="5f6af-163">No site do seu provedor de hospedagem, adicione registros SRV para cada serviço que você deseja conectar.</span><span class="sxs-lookup"><span data-stu-id="5f6af-163">On your hosting provider's website, add SRV records for each service you want to connect.</span></span>
<span data-ttu-id="5f6af-164">Verifique se os campos estão definidos para os seguintes valores para cada:</span><span class="sxs-lookup"><span data-stu-id="5f6af-164">Make sure that the fields are set to the following values for each:</span></span>

- <span data-ttu-id="5f6af-165">Tipo de Registro: `SRV (Service)`</span><span class="sxs-lookup"><span data-stu-id="5f6af-165">Record Type: `SRV (Service)`</span></span>
- <span data-ttu-id="5f6af-166">Nome: `@`</span><span class="sxs-lookup"><span data-stu-id="5f6af-166">Name: `@`</span></span>
- <span data-ttu-id="5f6af-167">Destino: copie o valor do centro de administração e cole-o aqui.</span><span class="sxs-lookup"><span data-stu-id="5f6af-167">Target: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="5f6af-168">Protocolo: copie o valor do centro de administração e cole-o aqui.</span><span class="sxs-lookup"><span data-stu-id="5f6af-168">Protocol: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="5f6af-169">Serviço: copie o valor do centro de administração e cole-o aqui.</span><span class="sxs-lookup"><span data-stu-id="5f6af-169">Service: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="5f6af-170">Prioridade: `100`</span><span class="sxs-lookup"><span data-stu-id="5f6af-170">Priority: `100`</span></span>
- <span data-ttu-id="5f6af-171">Espessura: `1`</span><span class="sxs-lookup"><span data-stu-id="5f6af-171">Weight: `1`</span></span>
- <span data-ttu-id="5f6af-172">Porta: copie o valor do centro de administração e cole-o aqui.</span><span class="sxs-lookup"><span data-stu-id="5f6af-172">Port: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="5f6af-173">TTL: `3600‎` (ou seu provedor padrão)</span><span class="sxs-lookup"><span data-stu-id="5f6af-173">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="5f6af-174">Salve o registro.</span><span class="sxs-lookup"><span data-stu-id="5f6af-174">Save the record.</span></span>

#### <a name="srv-record-field-restrictions-and-workarounds"></a><span data-ttu-id="5f6af-175">Restrições e soluções alternativas para campos de registro SRV</span><span class="sxs-lookup"><span data-stu-id="5f6af-175">SRV record field restrictions and workarounds</span></span>
<span data-ttu-id="5f6af-176">Alguns provedores de hospedagem impõem restrições aos valores dos campos dentro de registros SRV.</span><span class="sxs-lookup"><span data-stu-id="5f6af-176">Some hosting providers impose restrictions on field values within SRV records.</span></span> <span data-ttu-id="5f6af-177">Aqui estão algumas soluções alternativas comuns para essas restrições.</span><span class="sxs-lookup"><span data-stu-id="5f6af-177">Here are some common workarounds for these restrictions.</span></span>

##### <a name="name"></a><span data-ttu-id="5f6af-178">Nome</span><span class="sxs-lookup"><span data-stu-id="5f6af-178">Name</span></span>
<span data-ttu-id="5f6af-179">Se o seu provedor de hospedagem não permitir a definição desse campo como **@**, deixe-o em branco.</span><span class="sxs-lookup"><span data-stu-id="5f6af-179">If your hosting provider doesn't allow setting this field to **@**, leave it blank.</span></span> <span data-ttu-id="5f6af-180">Use esta abordagem *apenas* quando o provedor de hospedagem tiver campos separados para os valores de Serviço e Protocolo.</span><span class="sxs-lookup"><span data-stu-id="5f6af-180">Use this approach *only* when your hosting provider has separate fields for the Service and Protocol values.</span></span> <span data-ttu-id="5f6af-181">Caso contrário, consulte as observações a seguir sobre Serviço e Protocolo.</span><span class="sxs-lookup"><span data-stu-id="5f6af-181">Otherwise, see the Service and Protocol notes below.</span></span>

##### <a name="service-and-protocol"></a><span data-ttu-id="5f6af-182">Serviço e Protocolo</span><span class="sxs-lookup"><span data-stu-id="5f6af-182">Service and Protocol</span></span>
<span data-ttu-id="5f6af-183">Caso seu provedor de hospedagem não forneça esses campos para registros SRV, você deve especificar os valores **Serviço** e **Protocolo** no campo **Nome** do registro.</span><span class="sxs-lookup"><span data-stu-id="5f6af-183">If your hosting provider doesn't provide these fields for SRV records, you must specify the **Service** and **Protocol** values in the record's **Name** field.</span></span> <span data-ttu-id="5f6af-184">(Observação: dependendo do seu provedor de hospedagem, o campo **Nome** pode ser chamado de algo mais, como: **Host**, **Hostname** ou **Subdomínio**.) Para adicionar esses valores, crie uma única cadeia de caracteres e separe os valores com um ponto.</span><span class="sxs-lookup"><span data-stu-id="5f6af-184">(Note: Depending on your hosting provider, the **Name** field might be called something else, like: **Host**, **Hostname**, or **Subdomain**.) To add these values, you create a single string, separating the values with a dot.</span></span> 

<span data-ttu-id="5f6af-185">Exemplo: `_sip._tls`</span><span class="sxs-lookup"><span data-stu-id="5f6af-185">Example: `_sip._tls`</span></span>

##### <a name="priority-weight-and-port-br"></a><span data-ttu-id="5f6af-186">Prioridade, Espessura e Porta</span><span class="sxs-lookup"><span data-stu-id="5f6af-186">Priority, Weight, and Port</span></span> <br>
<span data-ttu-id="5f6af-187">Se o seu provedor de hospedagem não oferecer esses campos para registros SRV, você deve especificá-los no campo **Destino** do registro.</span><span class="sxs-lookup"><span data-stu-id="5f6af-187">If your hosting provider doesn't provide these fields for SRV records, you must specify them in the record's **Target** field.</span></span> <span data-ttu-id="5f6af-188">(Observação: dependendo do seu provedor de hospedagem, o campo **Destino** pode ter outro nome, como: **Conteúdo**, **Endereço IP** ou **Host de Destino**.)</span><span class="sxs-lookup"><span data-stu-id="5f6af-188">(Note: Depending on your hosting provider, the **Target** field might be called something else, like: **Content**, **IP Address**, or **Target Host**.)</span></span> 

<span data-ttu-id="5f6af-189">Para adicionar esses valores, crie uma única cadeia de caracteres, separando os valores com espaços e \* às vezes terminando com um ponto\* (verifique com o seu provedor se não tiver certeza).</span><span class="sxs-lookup"><span data-stu-id="5f6af-189">To add these values, create a single string, separating the values with spaces and *sometimes ending with a dot* (check with your provider if you are unsure).</span></span> <span data-ttu-id="5f6af-190">Os valores devem ser incluídos nesta ordem: Prioridade, Peso, Porta, Destino.</span><span class="sxs-lookup"><span data-stu-id="5f6af-190">The values must be included in this order: Priority, Weight, Port, Target.</span></span> 

- <span data-ttu-id="5f6af-191">Exemplo 1: `100 1 443 sipdir.online.lync.com.`</span><span class="sxs-lookup"><span data-stu-id="5f6af-191">Example 1: `100 1 443 sipdir.online.lync.com.`</span></span>
- <span data-ttu-id="5f6af-192">Exemplo 2: `100 1 443 sipdir.online.lync.com`</span><span class="sxs-lookup"><span data-stu-id="5f6af-192">Example 2: `100 1 443 sipdir.online.lync.com`</span></span>
