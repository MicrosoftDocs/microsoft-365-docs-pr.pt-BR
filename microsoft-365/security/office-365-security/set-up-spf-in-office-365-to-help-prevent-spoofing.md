---
title: Configure o SPF para ajudar a evitar falsificações
f1.keywords:
- CSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/21/2019
audience: ITPro
ms.topic: how-to
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 71373291-83d2-466f-86ea-fc61493743a6
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Este artigo descreve como atualizar um registro de Serviço de Nome de Domínio (DNS) para que você possa usar a Sender Policy Framework (SPF) com seu domínio personalizado no Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1d200c4cf17a3d42ddafca301fecbf18c249ac37
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245679"
---
# <a name="set-up-spf-to-help-prevent-spoofing"></a><span data-ttu-id="76a03-103">Configure o SPF para ajudar a evitar falsificações</span><span class="sxs-lookup"><span data-stu-id="76a03-103">Set up SPF to help prevent spoofing</span></span>

- [<span data-ttu-id="76a03-104">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="76a03-104">Prerequisites</span></span>](#prerequisites)
- [<span data-ttu-id="76a03-105">Criar ou atualizar seu registro TXT da SPF</span><span class="sxs-lookup"><span data-stu-id="76a03-105">Create or update your SPF TXT record</span></span>](#create-or-update-your-spf-txt-record)
- [<span data-ttu-id="76a03-106">Como lidar com subdomínios?</span><span class="sxs-lookup"><span data-stu-id="76a03-106">How to handle subdomains?</span></span>](#how-to-handle-subdomains)
- [<span data-ttu-id="76a03-107">Solução de problemas da SPF</span><span class="sxs-lookup"><span data-stu-id="76a03-107">Troubleshooting SPF</span></span>](#troubleshooting-spf)

<!--
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Applies to**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 plan 1 and plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)
-->

<span data-ttu-id="76a03-108">Este artigo descreve como atualizar um registro DNS (Serviço de Nomes de Domínio) para que você possa usar a autenticação de email SPF (Sender Policy Framework) com o seu domínio personalizado no Office 365.</span><span class="sxs-lookup"><span data-stu-id="76a03-108">This article describes how to update a Domain Name Service (DNS) record so that you can use Sender Policy Framework (SPF)  email authentication with your custom domain in Office 365.</span></span>

<span data-ttu-id="76a03-109">A SPF ajuda a *validar* emails de saída enviados de seu domínio personalizado (são provenientes de quem diz que ele é).</span><span class="sxs-lookup"><span data-stu-id="76a03-109">SPF helps *validate* outbound email sent from your custom domain (is coming from who it says it is).</span></span> <span data-ttu-id="76a03-110">É a primeira etapa na configuração dos métodos de autenticação de email completos recomendados da SPF, do [DKIM](use-dkim-to-validate-outbound-email.md)e do [DMARC](use-dmarc-to-validate-email.md).</span><span class="sxs-lookup"><span data-stu-id="76a03-110">It's a first step in setting up the full recommended email authentication methods of SPF, [DKIM](use-dkim-to-validate-outbound-email.md), and [DMARC](use-dmarc-to-validate-email.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="76a03-111">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="76a03-111">Prerequisites</span></span>

> [!IMPORTANT]
> <span data-ttu-id="76a03-112">Se você for uma **pequena empresa** ou não estiver familiarizado com endereços IP ou configuração de DNS, ligue para o registrador de domínios da Internet (por exemplo,</span><span class="sxs-lookup"><span data-stu-id="76a03-112">If you are a **small business**, or are unfamiliar with IP addresses or DNS configuration, call your Internet domain registrar (ex.</span></span> <span data-ttu-id="76a03-113">GoDaddy, Bluehost, web.com) e peça ajuda com a *Configuração DNS do SPF* (e qualquer outro método de autenticação de email).</span><span class="sxs-lookup"><span data-stu-id="76a03-113">GoDaddy, Bluehost, web.com) & ask for help with *DNS configuration of SPF* (and any other email authentication method).</span></span> <p> <span data-ttu-id="76a03-114">**Se você não usar uma URL personalizada** (e a URL usada para o Office 365 termina em **onmicrosoft.com**), a SPF já foi configurada para você no serviço do Office 365.</span><span class="sxs-lookup"><span data-stu-id="76a03-114">**If you don't use a custom URL** (and the URL used for Office 365 ends in **onmicrosoft.com**), SPF has already been set up for you in the Office 365 service.</span></span>

<span data-ttu-id="76a03-115">Vamos começar.</span><span class="sxs-lookup"><span data-stu-id="76a03-115">Let's get started.</span></span>

<span data-ttu-id="76a03-116">O registro TXT SPF para o Office 365 será feito em DNS externo para qualquer domínio personalizado ou subdomínios.</span><span class="sxs-lookup"><span data-stu-id="76a03-116">The SPF TXT record for Office 365 will be made in external DNS for any custom domains or subdomains.</span></span> <span data-ttu-id="76a03-117">Você precisa de algumas informações para fazer o registro.</span><span class="sxs-lookup"><span data-stu-id="76a03-117">You need some information to make the record.</span></span> <span data-ttu-id="76a03-118">Reúna essas informações:</span><span class="sxs-lookup"><span data-stu-id="76a03-118">Gather this information:</span></span>

- <span data-ttu-id="76a03-119">O registro TXT SPF do seu domínio personalizado, se houver.</span><span class="sxs-lookup"><span data-stu-id="76a03-119">The SPF TXT record for your custom domain, if one exists.</span></span> <span data-ttu-id="76a03-120">Para obter instruções, confira [Reúna as informações necessárias para criar registros DNS do Office 365](../../admin/get-help-with-domains/information-for-dns-records.md).</span><span class="sxs-lookup"><span data-stu-id="76a03-120">For instructions, see [Gather the information you need to create Office 365 DNS records](../../admin/get-help-with-domains/information-for-dns-records.md).</span></span>

- <span data-ttu-id="76a03-121">Vá para o(s) seu(s) servidor(es) de mensagens e descubra os endereços IP externos (necessários de todos os servidores de mensagens locais).</span><span class="sxs-lookup"><span data-stu-id="76a03-121">Go to your messaging server(s) and find out the External IP addresses (needed from all on-premises messaging servers).</span></span> <span data-ttu-id="76a03-122">Por exemplo, **131.107.2.200**.</span><span class="sxs-lookup"><span data-stu-id="76a03-122">For example, **131.107.2.200**.</span></span>

- <span data-ttu-id="76a03-p106">Os nomes de domínio a serem usados para todos os domínios de terceiros que você precisa para incluir em seu registro TXT da SPF. Alguns provedores de email em massa configuraram subdomínios a serem usados para seus clientes. Por exemplo, a empresa MailChimp configurou **servers.mcsv.net**.</span><span class="sxs-lookup"><span data-stu-id="76a03-p106">Domain names to use for all third-party domains that you need to include in your SPF TXT record. Some bulk mail providers have set up subdomains to use for their customers. For example, the company MailChimp has set up **servers.mcsv.net**.</span></span>

- <span data-ttu-id="76a03-126">Descubra qual regra de aplicação você deseja usar para o seu registro SPF TXT.</span><span class="sxs-lookup"><span data-stu-id="76a03-126">Figure out what enforcement rule you want to use for your SPF TXT record.</span></span> <span data-ttu-id="76a03-127">A regra **-all** é recomendada.</span><span class="sxs-lookup"><span data-stu-id="76a03-127">The **-all** rule is recommended.</span></span> <span data-ttu-id="76a03-128">Para obter informações detalhadas sobre outras opções de sintaxe, confira [Sintaxe de registro SPF TXT para Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFSyntaxO365).</span><span class="sxs-lookup"><span data-stu-id="76a03-128">For detailed information about other syntax options, see [SPF TXT record syntax for Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFSyntaxO365).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="76a03-129">Para usar um domínio personalizado, o Office 365 exige que você adicione um registro TXT da Sender Policy Framework (SPF) ao registro DNS para ajudar a evitar falsificações.</span><span class="sxs-lookup"><span data-stu-id="76a03-129">In order to use a custom domain, Office 365 requires that you add a Sender Policy Framework (SPF) TXT record to your DNS record to help prevent spoofing.</span></span>

## <a name="create-or-update-your-spf-txt-record"></a><span data-ttu-id="76a03-130">Criar ou atualizar seu registro TXT da SPF</span><span class="sxs-lookup"><span data-stu-id="76a03-130">Create or update your SPF TXT record</span></span>

1. <span data-ttu-id="76a03-131">Verifique se está familiarizado com a sintaxe SPF na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="76a03-131">Ensure that you're familiar with the SPF syntax in the following table.</span></span>

   ****

   |<span data-ttu-id="76a03-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="76a03-132">Element</span></span>|<span data-ttu-id="76a03-133">Se você estiver usando...</span><span class="sxs-lookup"><span data-stu-id="76a03-133">If you're using...</span></span>|<span data-ttu-id="76a03-134">Comum para clientes?</span><span class="sxs-lookup"><span data-stu-id="76a03-134">Common for customers?</span></span>|<span data-ttu-id="76a03-135">Adicione este...</span><span class="sxs-lookup"><span data-stu-id="76a03-135">Add this...</span></span>|
   |---|---|---|---|
   |<span data-ttu-id="76a03-136">1</span><span class="sxs-lookup"><span data-stu-id="76a03-136">1</span></span>|<span data-ttu-id="76a03-137">Qualquer sistema de email (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="76a03-137">Any email system (required)</span></span>|<span data-ttu-id="76a03-p108">Comum. Todos os registros TXT da SPF começam com esse valor</span><span class="sxs-lookup"><span data-stu-id="76a03-p108">Common. All SPF TXT records start with this value</span></span>|`v=spf1`|
   |<span data-ttu-id="76a03-140">2</span><span class="sxs-lookup"><span data-stu-id="76a03-140">2</span></span>|<span data-ttu-id="76a03-141">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="76a03-141">Exchange Online</span></span>|<span data-ttu-id="76a03-142">Comum</span><span class="sxs-lookup"><span data-stu-id="76a03-142">Common</span></span>|`include:spf.protection.outlook.com`|
   |<span data-ttu-id="76a03-143">3</span><span class="sxs-lookup"><span data-stu-id="76a03-143">3</span></span>|<span data-ttu-id="76a03-144">Somente Exchange Online dedicado</span><span class="sxs-lookup"><span data-stu-id="76a03-144">Exchange Online dedicated only</span></span>|<span data-ttu-id="76a03-145">Incomum</span><span class="sxs-lookup"><span data-stu-id="76a03-145">Not common</span></span>|`ip4:23.103.224.0/19` <br> `ip4:206.191.224.0/19` <br> `ip4:40.103.0.0/16` <br> `include:spf.protection.outlook.com`|
   |<span data-ttu-id="76a03-146">4</span><span class="sxs-lookup"><span data-stu-id="76a03-146">4</span></span>|<span data-ttu-id="76a03-147">Office 365 Alemanha, Microsoft Cloud Alemanha apenas</span><span class="sxs-lookup"><span data-stu-id="76a03-147">Office 365 Germany, Microsoft Cloud Germany only</span></span>|<span data-ttu-id="76a03-148">Incomum</span><span class="sxs-lookup"><span data-stu-id="76a03-148">Not common</span></span>|`include:spf.protection.outlook.de`|
   |<span data-ttu-id="76a03-149">5</span><span class="sxs-lookup"><span data-stu-id="76a03-149">5</span></span>|<span data-ttu-id="76a03-150">Sistema de email de terceiros</span><span class="sxs-lookup"><span data-stu-id="76a03-150">Third-party email system</span></span>|<span data-ttu-id="76a03-151">Incomum</span><span class="sxs-lookup"><span data-stu-id="76a03-151">Not common</span></span>|`include:<domain_name>` <p> <span data-ttu-id="76a03-152">O \<domain_name\> é o domínio do sistema de email de terceiros.</span><span class="sxs-lookup"><span data-stu-id="76a03-152">\<domain_name\> is the domain of the third-party email system.</span></span>|
   |<span data-ttu-id="76a03-153">6</span><span class="sxs-lookup"><span data-stu-id="76a03-153">6</span></span>|<span data-ttu-id="76a03-p109">Sistema de emails local. Por exemplo, o Proteção do Exchange Online mais outro sistema de email</span><span class="sxs-lookup"><span data-stu-id="76a03-p109">On-premises email system. For example, Exchange Online Protection plus another email system</span></span>|<span data-ttu-id="76a03-156">Incomum</span><span class="sxs-lookup"><span data-stu-id="76a03-156">Not common</span></span>|<span data-ttu-id="76a03-157">Use um destes procedimentos para cada sistema de email adicional:</span><span class="sxs-lookup"><span data-stu-id="76a03-157">Use one of these for each additional mail system:</span></span> <p> `ip4:<IP_address>` <br> `ip6:<IP_address>` <br> `include:<domain_name>` <p> <span data-ttu-id="76a03-158">O \<IP_address\> e o \<domain_name\> são o endereço IP e o domínio do sistema de emails que enviam emails em nome de seu domínio.</span><span class="sxs-lookup"><span data-stu-id="76a03-158">\<IP_address\> and \<domain_name\> are the IP address and domain of the other email system that sends mail on behalf of your domain.</span></span>|
   |<span data-ttu-id="76a03-159">7</span><span class="sxs-lookup"><span data-stu-id="76a03-159">7</span></span>|<span data-ttu-id="76a03-160">Qualquer sistema de email (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="76a03-160">Any email system (required)</span></span>|<span data-ttu-id="76a03-p110">Comum. Todos os registros TXT da SPF terminam com esse valor</span><span class="sxs-lookup"><span data-stu-id="76a03-p110">Common. All SPF TXT records end with this value</span></span>|`<enforcement rule>` <p> <span data-ttu-id="76a03-163">Este pode ser um dos vários valores.</span><span class="sxs-lookup"><span data-stu-id="76a03-163">This can be one of several values.</span></span> <span data-ttu-id="76a03-164">Recomendamos o valor `-all`</span><span class="sxs-lookup"><span data-stu-id="76a03-164">We recommend the value `-all`.</span></span>|
   |

2. <span data-ttu-id="76a03-165">Se ainda não tiver feito isso, crie seu registro TXT SPF usando a sintaxe da tabela.</span><span class="sxs-lookup"><span data-stu-id="76a03-165">If you haven't already done so, form your SPF TXT record by using the syntax from the table.</span></span>

   <span data-ttu-id="76a03-166">Por exemplo, se você estiver totalmente hospedado no Office 365, ou seja, se você não tiver servidores de email locais, seu registro TXT SPF incluiria as linhas 1, 2 e 7 e teria esta aparência:</span><span class="sxs-lookup"><span data-stu-id="76a03-166">For example, if you are hosted entirely in Office 365, that is, you have no on-premises mail servers, your SPF TXT record would include rows 1, 2, and 7 and would look like this:</span></span>

   ```text
   v=spf1 include:spf.protection.outlook.com -all
   ```

   <span data-ttu-id="76a03-167">**O exemplo acima é o registro TXT SPF mais comum**.</span><span class="sxs-lookup"><span data-stu-id="76a03-167">**The example above is the most common SPF TXT record**.</span></span> <span data-ttu-id="76a03-168">Esse registro funciona para praticamente todas as pessoas, independentemente de seu data center da Microsoft estar localizado nos Estados Unidos ou na Europa (incluindo a Alemanha) ou em outro local.</span><span class="sxs-lookup"><span data-stu-id="76a03-168">This record works for just about everyone, regardless of whether your Microsoft datacenter is located in the United States, or in Europe (including Germany), or in another location.</span></span>

   <span data-ttu-id="76a03-p113">No entanto, se você comprou o Microsoft Office 365 Germany, parte do Microsoft Cloud Germany, você deverá usar a instrução incluir na linha 4, em vez de na linha 2. Por exemplo, se você estiver totalmente hospedado no Office 365 Alemanha, ou seja, se você não tiver servidores de email locais, seu registro TXT SPF incluiria as linhas 1, 4 e 7 e teria esta aparência:</span><span class="sxs-lookup"><span data-stu-id="76a03-p113">However, if you bought Office 365 Germany, part of Microsoft Cloud Germany, you should use the include statement from line 4 instead of line 2. For example, if you are hosted entirely in Office 365 Germany, that is, you have no on-premises mail servers, your SPF TXT record would include rows 1, 4, and 7 and would look like this:</span></span>

   ```text
   v=spf1 include:spf.protection.outlook.de -all
   ```

   <span data-ttu-id="76a03-171">Se você já implementou no Office 365 e configurou seus registros TXT SPF para o seu domínio personalizado e estiver migrando para o Office 365 Germany, será preciso atualizar o registro TXT SPF.</span><span class="sxs-lookup"><span data-stu-id="76a03-171">If you're already deployed in Office 365 and have set up your SPF TXT records for your custom domain, and you're migrating to Office 365 Germany, you need to update your SPF TXT record.</span></span> <span data-ttu-id="76a03-172">Para fazer isso, altere `include:spf.protection.outlook.com` para `include:spf.protection.outlook.de`.</span><span class="sxs-lookup"><span data-stu-id="76a03-172">To do this, change `include:spf.protection.outlook.com` to `include:spf.protection.outlook.de`.</span></span>

3. <span data-ttu-id="76a03-173">Depois que você formar seu registro TXT SPF, precisará atualizar o registro no DNS.</span><span class="sxs-lookup"><span data-stu-id="76a03-173">Once you have formed your SPF TXT record, you need to update the record in DNS.</span></span> <span data-ttu-id="76a03-174">**Você só pode ter um registro TXT SPF para um domínio.**</span><span class="sxs-lookup"><span data-stu-id="76a03-174">**You can only have one SPF TXT record for a domain.**</span></span> <span data-ttu-id="76a03-175">Se houver um registro TXT SPF, em vez de adicionar um novo registro, você precisa atualizar o registro existente.</span><span class="sxs-lookup"><span data-stu-id="76a03-175">If an SPF TXT record exists, instead of adding a new record, you need to update the existing record.</span></span> <span data-ttu-id="76a03-176">Acesse [Criar registros de DNS para o Office 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md) e, em seguida, selecionar no link do seu host DNS.</span><span class="sxs-lookup"><span data-stu-id="76a03-176">Go to [Create DNS records for Office 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md), and then select the link for your DNS host.</span></span>

4. <span data-ttu-id="76a03-177">Testar o registro do SPF TXT.</span><span class="sxs-lookup"><span data-stu-id="76a03-177">Test your SPF TXT record.</span></span>

## <a name="how-to-handle-subdomains"></a><span data-ttu-id="76a03-178">Como lidar com subdomínios?</span><span class="sxs-lookup"><span data-stu-id="76a03-178">How to handle subdomains?</span></span>

<span data-ttu-id="76a03-179">É importante observar que *você precisa criar um registro separado para cada subdomínio, pois os subdomínios não herdam o registro SPF de seu domínio de nível superior*.</span><span class="sxs-lookup"><span data-stu-id="76a03-179">It's important to note that *you need to create a separate record for each subdomain as subdomains don't inherit the SPF record of their top-level domain*.</span></span>

<span data-ttu-id="76a03-180">Um registro SPF curinga (`*.`) é necessário para todos os domínios e subdomínios para impedir que os ataques por envio de emails que alegam ser de subdomínios não existentes.</span><span class="sxs-lookup"><span data-stu-id="76a03-180">A wildcard SPF record (`*.`) is required for every domain and subdomain to prevent attackers from sending email claiming to be from non-existent subdomains.</span></span> <span data-ttu-id="76a03-181">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="76a03-181">For example:</span></span>

```text
*.subdomain.contoso.com. IN TXT "v=spf1 -all"
```

## <a name="troubleshooting-spf"></a><span data-ttu-id="76a03-182">Solução de problemas da SPF</span><span class="sxs-lookup"><span data-stu-id="76a03-182">Troubleshooting SPF</span></span>

<span data-ttu-id="76a03-p117">Algum problema com seu registro TXT da SPF? Leia [Solução de problemas: Práticas recomendadas para a SPF no Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot).</span><span class="sxs-lookup"><span data-stu-id="76a03-p117">Having trouble with your SPF TXT record? Read [Troubleshooting: Best practices for SPF in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot).</span></span>


## <a name="what-does-spf-email-authentication-actually-do"></a><span data-ttu-id="76a03-185">O que a autenticação de email SPF realmente faz?</span><span class="sxs-lookup"><span data-stu-id="76a03-185">What does SPF email authentication actually do?</span></span>

<span data-ttu-id="76a03-p118">A SPF identifica quais servidores de email têm permissão para enviar emails em seu nome. Basicamente, a SPF, juntamente com DKIM, DMARC e outras tecnologias com suporte np Office 365 ajudam a evitar falsificações e phishing. A SPF é adicionada como um registro TXT que é usado pelo DNS para identificar quais servidores de email podem enviar emails em nome do seu domínio personalizado. Os sistemas de email dos destinatários referem-se ao registro TXT SPF para determinar se uma mensagem de seu domínio personalizado vem de um servidor de mensagens autorizado.</span><span class="sxs-lookup"><span data-stu-id="76a03-p118">SPF identifies which mail servers are allowed to send mail on your behalf. Basically, SPF, along with DKIM, DMARC, and other technologies supported by Office 365, help prevent spoofing and phishing. SPF is added as a TXT record that is used by DNS to identify which mail servers can send mail on behalf of your custom domain. Recipient mail systems refer to the SPF TXT record to determine whether a message from your custom domain comes from an authorized messaging server.</span></span>

<span data-ttu-id="76a03-p119">Por exemplo, digamos que seu domínio personalizado contoso.com usa o Office 365. Você adiciona um registro TXT SPF que lista os servidores de mensagens do Office 365 como servidores de email legítimos para seu domínio. Quando o servidor de mensagens de recebimento recebe uma mensagem de joe@contoso.com, o servidor procura pelo registro TXT SPF para contoso.com e descobre se a mensagem é válida. Se o servidor de recebimento descobrir que a mensagem é proveniente de um servidor diferente dos servidores de mensagens do Office 365 listados no registro SPF, o servidor de email de recebimento pode optar por rejeitar a mensagem como spam.</span><span class="sxs-lookup"><span data-stu-id="76a03-p119">For example, let's say that your custom domain contoso.com uses Office 365. You add an SPF TXT record that lists the Office 365 messaging servers as legitimate mail servers for your domain. When the receiving messaging server gets a message from joe@contoso.com, the server looks up the SPF TXT record for contoso.com and finds out whether the message is valid. If the receiving server finds out that the message comes from a server other than the Office 365 messaging servers listed in the SPF record, the receiving mail server can choose to reject the message as spam.</span></span>

<span data-ttu-id="76a03-p120">Além disso, se o seu domínio personalizado não tiver um registro TXT SPF, alguns servidores de recebimento poderão rejeitar a mensagem imediatamente. Isso ocorre porque o servidor de recebimento não consegue validar se a mensagem vem de um servidor de mensagens autorizado.</span><span class="sxs-lookup"><span data-stu-id="76a03-p120">Also, if your custom domain does not have an SPF TXT record, some receiving servers may reject the message outright. This is because the receiving server cannot validate that the message comes from an authorized messaging server.</span></span>

<span data-ttu-id="76a03-p121">Se você já configurou o email do Office 365, então você já incluiu os servidores de mensagens da Microsoft no DNS como um registro TXT SPF. No entanto, há alguns casos em que talvez você precise atualizar seu registro TXT SPF no DNS. Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="76a03-p121">If you've already set up mail for Office 365, then you have already included Microsoft's messaging servers in DNS as an SPF TXT record. However, there are some cases where you may need to update your SPF TXT record in DNS. For example:</span></span>

- <span data-ttu-id="76a03-p122">Antes, era necessário adicionar um registro TXT SPF diferente para o seu domínio personalizado se você estivesse usando o SharePoint Online. Isso não é mais necessário. Essa alteração deve reduzir o risco de mensagens de notificação do SharePoint Online acabarem na pasta Lixo Eletrônico. Atualize seu registro TXT SPF se você estiver atingindo o limite de 10 pesquisas e recebendo mensagens de erros que informam coisas como "excedeu o limite de pesquisa" e "excesso de saltos".</span><span class="sxs-lookup"><span data-stu-id="76a03-p122">Previously, you had to add a different SPF TXT record to your custom domain if you were using SharePoint Online. This is no longer required. This change should reduce the risk of SharePoint Online notification messages ending up in the Junk Email folder. Update your SPF TXT record if you are hitting the 10 lookup limit and receiving errors that say things like, "exceeded the lookup limit" and "too many hops".</span></span>

- <span data-ttu-id="76a03-203">Se você tiver um ambiente híbrido com o Office 365 e o Exchange locais.</span><span class="sxs-lookup"><span data-stu-id="76a03-203">If you have a hybrid environment with Office 365 and Exchange on-premises.</span></span>

- <span data-ttu-id="76a03-204">Você pretende configurar o DKIM e o DMARC (recomendado).</span><span class="sxs-lookup"><span data-stu-id="76a03-204">You intend to set up DKIM and DMARC (recommended).</span></span>

## <a name="more-information-about-spf"></a><span data-ttu-id="76a03-205">Mais informações sobre a SPF</span><span class="sxs-lookup"><span data-stu-id="76a03-205">More information about SPF</span></span>

<span data-ttu-id="76a03-206">Para exemplos avançados, uma discussão mais detalhada sobre sintaxe de SPF compatível, falsificação, solução de problemas e como o Office 365 oferece suporte à SPF, confira [Como a SPF funciona para evitar a falsificação e o phishing no Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks).</span><span class="sxs-lookup"><span data-stu-id="76a03-206">For advanced examples, a more detailed discussion about supported SPF syntax, spoofing, troubleshooting, and how Office 365 supports SPF, see [How SPF works to prevent spoofing and phishing in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks).</span></span>

## <a name="next-steps-dkim-and-dmarc"></a><span data-ttu-id="76a03-207">Próximas etapas: DKIM e DMARC</span><span class="sxs-lookup"><span data-stu-id="76a03-207">Next Steps: DKIM and DMARC</span></span>

 <span data-ttu-id="76a03-208">O SPF foi projetado para ajudar a evitar falsificação, mas existem técnicas de falsificação contra as quais o SPF não pode proteger.</span><span class="sxs-lookup"><span data-stu-id="76a03-208">SPF is designed to help prevent spoofing, but there are spoofing techniques that SPF can't protect against.</span></span> <span data-ttu-id="76a03-209">Para se defender deles, depois de configurar o SPF, você deve configurar o DKIM e o DMARC para o Office 365.</span><span class="sxs-lookup"><span data-stu-id="76a03-209">To defend against these, once you've set up SPF, you should configure DKIM and DMARC for Office 365.</span></span>

<span data-ttu-id="76a03-210">O objetivo da autenticação de email [DKIM](use-dkim-to-validate-outbound-email.md) é provar que o conteúdo do email não foi adulterado.</span><span class="sxs-lookup"><span data-stu-id="76a03-210">[DKIM](use-dkim-to-validate-outbound-email.md) email authentication's goal is to prove the contents of the mail haven't been tampered with.</span></span>

<span data-ttu-id="76a03-211">O objetivo da autenticação de email [DMARC](use-dmarc-to-validate-email.md) é garantir que as informações SPF e DKIM correspondam ao endereço De.</span><span class="sxs-lookup"><span data-stu-id="76a03-211">[DMARC](use-dmarc-to-validate-email.md) email authentication's goal is to make sure that SPF and DKIM information matches the From address.</span></span>

 <span data-ttu-id="76a03-212">Para obter exemplos avançados e uma discussão mais detalhada sobre a sintaxe SPF com suporte, confira [Como funciona o SPF para evitar spoofing e phishing no Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks).</span><span class="sxs-lookup"><span data-stu-id="76a03-212">For advanced examples and a more detailed discussion about supported SPF syntax, see [How SPF works to prevent spoofing and phishing in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks).</span></span>

<span data-ttu-id="76a03-213">*Selecione "Esta página" em "Comentários" se você tiver comentários sobre esta documentação.*</span><span class="sxs-lookup"><span data-stu-id="76a03-213">*Select 'This page' under 'Feedback' if you have feedback on this documentation.*</span></span>
