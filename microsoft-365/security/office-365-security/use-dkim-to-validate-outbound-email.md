---
title: Use o DKIM para e-mails em seu domínio personalizado
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 10/8/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 56fee1c7-dc37-470e-9b09-33fff6d94617
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Aprenda a usar o e-mail Identificado DomainKeys (DKIM) com o Microsoft 365 para garantir que as mensagens enviadas de seu domínio personalizado sejam confiadas pelos sistemas de e-mail de destino.
ms.openlocfilehash: 4ec5f7c8779e9d6b6709c8fc3311ec9c0e99b680
ms.sourcegitcommit: 2acd9ec5e9d150389975e854c7883efc186a9432
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754839"
---
# <a name="use-dkim-to-validate-outbound-email-sent-from-your-custom-domain"></a><span data-ttu-id="7d431-103">Usar o DKIM para validar emails enviados de seu domínio personalizado</span><span class="sxs-lookup"><span data-stu-id="7d431-103">Use DKIM to validate outbound email sent from your custom domain</span></span>

 <span data-ttu-id="7d431-104">**Resumo:** este artigo descreve como você usa o DomainKeys Identified Mail (DKIM) com o Microsoft 365 para garantir que os sistemas de email de destino confiem em mensagens enviadas de saída de seu domínio personalizado.</span><span class="sxs-lookup"><span data-stu-id="7d431-104">**Summary:** This article describes how you use DomainKeys Identified Mail (DKIM) with Microsoft 365 to ensure that destination email systems trust messages sent outbound from your custom domain.</span></span>

<span data-ttu-id="7d431-105">Você deve usar o DKIM, além do SPF e do DMARC, para ajudar a evitar que spoofers enviem mensagens que pareçam que são provenientes de seu domínio.</span><span class="sxs-lookup"><span data-stu-id="7d431-105">You should use DKIM in addition to SPF and DMARC to help prevent spoofers from sending messages that look like they are coming from your domain.</span></span> <span data-ttu-id="7d431-106">O DKIM possibilita adicionar uma assinatura digital no cabeçalho de mensagens de email enviadas.</span><span class="sxs-lookup"><span data-stu-id="7d431-106">DKIM lets you add a digital signature to outbound email messages in the message header.</span></span> <span data-ttu-id="7d431-107">Parece complicado, mas não é.</span><span class="sxs-lookup"><span data-stu-id="7d431-107">It may sound complicated, but it's really not.</span></span> <span data-ttu-id="7d431-108">Quando você configura o DKIM, autoriza seu domínio a associar, ou fazer login, seu nome a uma mensagem de email usando a autenticação de criptografia.</span><span class="sxs-lookup"><span data-stu-id="7d431-108">When you configure DKIM, you authorize your domain to associate, or sign, its name to an email message by using cryptographic authentication.</span></span> <span data-ttu-id="7d431-109">Sistemas de email que recebem emails de seu domínio podem usar essa assinatura digital para ajudar a determinar se os emails recebidos são legítimos.</span><span class="sxs-lookup"><span data-stu-id="7d431-109">Email systems that receive email from your domain can use this digital signature to help determine if incoming email that they receive is legitimate.</span></span>

<span data-ttu-id="7d431-110">Basicamente, você usa uma chave privada para criptografar o cabeçalho no email de saída do seu domínio.</span><span class="sxs-lookup"><span data-stu-id="7d431-110">Basically, you use a private key to encrypt the header in your domain's outgoing email.</span></span> <span data-ttu-id="7d431-111">Publique uma chave pública nos registros DNS do seu domínio que os servidores de recebimento possam então usar para decodificar a assinatura.</span><span class="sxs-lookup"><span data-stu-id="7d431-111">You publish a public key to your domain's DNS records that receiving servers can then use to decode the signature.</span></span> <span data-ttu-id="7d431-112">Eles usam a chave pública para confirmar que as mensagens realmente vêm de você e não de alguém que está *falsificando* seu domínio.</span><span class="sxs-lookup"><span data-stu-id="7d431-112">They use the public key to verify that the messages are really coming from you and not coming from someone *spoofing* your domain.</span></span>

<span data-ttu-id="7d431-113">O Microsoft 365 configura automaticamente o DKIM para domínios iniciais de “onmicrosoft.com”.</span><span class="sxs-lookup"><span data-stu-id="7d431-113">Microsoft 365 automatically sets up DKIM for its initial 'onmicrosoft.com' domains.</span></span> <span data-ttu-id="7d431-114">Isso significa que não é preciso fazer nada para configurar o DKIM para qualquer nome de domínio inicial (por exemplo, litware.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="7d431-114">That means you don't need to do anything to set up DKIM for any initial domain names (for example, litware.onmicrosoft.com).</span></span> <span data-ttu-id="7d431-115">Para saber mais sobre domínios, confira [Perguntas frequentes sobre domínios](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain).</span><span class="sxs-lookup"><span data-stu-id="7d431-115">For more information about domains, see [Domains FAQ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain).</span></span>

<span data-ttu-id="7d431-116">Você também pode optar por não fazer nada sobre o DKIM em relação ao seu domínio personalizado.</span><span class="sxs-lookup"><span data-stu-id="7d431-116">You can choose to do nothing about DKIM for your custom domain too.</span></span> <span data-ttu-id="7d431-117">Se o DKIM não for configurado para o seu domínio personalizado, o Microsoft 365 criará um par de chaves privada e pública, habilitará a assinatura do DKIM e configurará a política padrão do Microsoft 365 para o seu domínio personalizado.</span><span class="sxs-lookup"><span data-stu-id="7d431-117">If you don't set up DKIM for your custom domain, Microsoft 365 creates a private and public key pair, enables DKIM signing, and then configures the Microsoft 365 default policy for your custom domain.</span></span> <span data-ttu-id="7d431-118">Embora isso seja abrangente o suficiente para a maioria dos clientes, você deve configurar manualmente o DKIM para o seu domínio personalizado nas seguintes circunstâncias:</span><span class="sxs-lookup"><span data-stu-id="7d431-118">While this is sufficient coverage for most customers, you should manually configure DKIM for your custom domain in the following circumstances:</span></span>

- <span data-ttu-id="7d431-119">Você tem mais de um domínio personalizado no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7d431-119">You have more than one custom domain in Microsoft 365</span></span>

- <span data-ttu-id="7d431-120">For configurar o DMARC também (recomendado)</span><span class="sxs-lookup"><span data-stu-id="7d431-120">You're going to set up DMARC too (recommended)</span></span>

- <span data-ttu-id="7d431-121">Quiser ter controle sobre sua chave privada</span><span class="sxs-lookup"><span data-stu-id="7d431-121">You want control over your private key</span></span>

- <span data-ttu-id="7d431-122">Quiser personalizar seus registros CNAME</span><span class="sxs-lookup"><span data-stu-id="7d431-122">You want to customize your CNAME records</span></span>

- <span data-ttu-id="7d431-123">Configure as chaves do DKIM para emails provenientes de um domínio de terceiros, por exemplo, se você usar um programa de email em massa terceirizado.</span><span class="sxs-lookup"><span data-stu-id="7d431-123">You want to set up DKIM keys for email originating out of a third-party domain, for example, if you use a third-party bulk mailer.</span></span>

<span data-ttu-id="7d431-124">Neste artigo:</span><span class="sxs-lookup"><span data-stu-id="7d431-124">In this article:</span></span>

- [<span data-ttu-id="7d431-125">Como o DKIM funciona melhor do que o SPF para evitar a falsificação maliciosa</span><span class="sxs-lookup"><span data-stu-id="7d431-125">How DKIM works better than SPF alone to prevent malicious spoofing</span></span>](use-dkim-to-validate-outbound-email.md#HowDKIMWorks)

- [<span data-ttu-id="7d431-126">Atualize manualmente as chaves de 1024 bits para chaves de criptografia DKIM de 2048 bits</span><span class="sxs-lookup"><span data-stu-id="7d431-126">Manually upgrade your 1024-bit keys to 2048-bit DKIM encryption keys</span></span>](use-dkim-to-validate-outbound-email.md#1024to2048DKIM)

- [<span data-ttu-id="7d431-127">O que é necessário fazer para configurar manualmente o DKIM</span><span class="sxs-lookup"><span data-stu-id="7d431-127">Steps you need to do to manually set up DKIM</span></span>](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365)

- [<span data-ttu-id="7d431-128">Para configurar o DKIM para mais de um domínio personalizado</span><span class="sxs-lookup"><span data-stu-id="7d431-128">To configure DKIM for more than one custom domain</span></span>](use-dkim-to-validate-outbound-email.md#DKIMMultiDomain)

- [<span data-ttu-id="7d431-129">Desabilitar a política de assinatura do DKIM para um domínio personalizado</span><span class="sxs-lookup"><span data-stu-id="7d431-129">Disabling the DKIM signing policy for a custom domain</span></span>](use-dkim-to-validate-outbound-email.md#DisableDKIMSigningPolicy)

- [<span data-ttu-id="7d431-130">Comportamento padrão para o DKIM e o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7d431-130">Default behavior for DKIM and Microsoft 365</span></span>](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior)

- [<span data-ttu-id="7d431-131">Configurar o DKIM de forma que um serviço terceirizado possa enviar, ou fazer spoof de, emails em nome de seu domínio personalizado</span><span class="sxs-lookup"><span data-stu-id="7d431-131">Set up DKIM so that a third-party service can send, or spoof, email on behalf of your custom domain</span></span>](use-dkim-to-validate-outbound-email.md#SetUp3rdPartyspoof)

- [<span data-ttu-id="7d431-132">Próximas etapas: após configurar o DKIM para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7d431-132">Next steps: After you set up DKIM for Microsoft 365</span></span>](use-dkim-to-validate-outbound-email.md#DKIMNextSteps)

## <a name="how-dkim-works-better-than-spf-alone-to-prevent-malicious-spoofing"></a><span data-ttu-id="7d431-133">Como o DKIM funciona melhor do que o SPF para evitar a falsificação maliciosa</span><span class="sxs-lookup"><span data-stu-id="7d431-133">How DKIM works better than SPF alone to prevent malicious spoofing</span></span>
<span data-ttu-id="7d431-134"><a name="HowDKIMWorks"> </a></span><span class="sxs-lookup"><span data-stu-id="7d431-134"><a name="HowDKIMWorks"> </a></span></span>

<span data-ttu-id="7d431-135">SPF adds information to a message envelope but DKIM actually encrypts a signature within the message header.</span><span class="sxs-lookup"><span data-stu-id="7d431-135">SPF adds information to a message envelope but DKIM actually encrypts a signature within the message header.</span></span> <span data-ttu-id="7d431-136">When you forward a message, portions of that message's envelope can be stripped away by the forwarding server.</span><span class="sxs-lookup"><span data-stu-id="7d431-136">When you forward a message, portions of that message's envelope can be stripped away by the forwarding server.</span></span> <span data-ttu-id="7d431-137">Since the digital signature stays with the email message because it's part of the email header, DKIM works even when a message has been forwarded as shown in the following example.</span><span class="sxs-lookup"><span data-stu-id="7d431-137">Since the digital signature stays with the email message because it's part of the email header, DKIM works even when a message has been forwarded as shown in the following example.</span></span>

![Diagrama que mostra uma mensagem encaminhada passando pela autenticação DKIM onde a verificação de SPF falha](../../media/28f93b4c-97e7-4309-acc4-fd0d2e0e3377.jpg)

<span data-ttu-id="7d431-139">In this example, if you had only published an SPF TXT record for your domain, the recipient's mail server could have marked your email as spam and generated a false positive result.</span><span class="sxs-lookup"><span data-stu-id="7d431-139">In this example, if you had only published an SPF TXT record for your domain, the recipient's mail server could have marked your email as spam and generated a false positive result.</span></span> <span data-ttu-id="7d431-140">The addition of DKIM in this scenario reduces false positive spam reporting.</span><span class="sxs-lookup"><span data-stu-id="7d431-140">The addition of DKIM in this scenario reduces false positive spam reporting.</span></span> <span data-ttu-id="7d431-141">Because DKIM relies on public key cryptography to authenticate and not just IP addresses, DKIM is considered a much stronger form of authentication than SPF.</span><span class="sxs-lookup"><span data-stu-id="7d431-141">Because DKIM relies on public key cryptography to authenticate and not just IP addresses, DKIM is considered a much stronger form of authentication than SPF.</span></span> <span data-ttu-id="7d431-142">We recommend using both SPF and DKIM, as well as DMARC in your deployment.</span><span class="sxs-lookup"><span data-stu-id="7d431-142">We recommend using both SPF and DKIM, as well as DMARC in your deployment.</span></span>

<span data-ttu-id="7d431-143">The nitty gritty: DKIM uses a private key to insert an encrypted signature into the message headers.</span><span class="sxs-lookup"><span data-stu-id="7d431-143">The nitty gritty: DKIM uses a private key to insert an encrypted signature into the message headers.</span></span> <span data-ttu-id="7d431-144">The signing domain, or outbound domain, is inserted as the value of the **d=** field in the header.</span><span class="sxs-lookup"><span data-stu-id="7d431-144">The signing domain, or outbound domain, is inserted as the value of the **d=** field in the header.</span></span> <span data-ttu-id="7d431-145">The verifying domain, or recipient's domain, then use the **d=** field to look up the public key from DNS and authenticate the message.</span><span class="sxs-lookup"><span data-stu-id="7d431-145">The verifying domain, or recipient's domain, then use the **d=** field to look up the public key from DNS and authenticate the message.</span></span> <span data-ttu-id="7d431-146">If the message is verified, the DKIM check passes.</span><span class="sxs-lookup"><span data-stu-id="7d431-146">If the message is verified, the DKIM check passes.</span></span>

## <a name="manually-upgrade-your-1024-bit-keys-to-2048-bit-dkim-encryption-keys"></a><span data-ttu-id="7d431-147">Atualize manualmente as chaves de 1024 bits para chaves de criptografia DKIM de 2048 bits</span><span class="sxs-lookup"><span data-stu-id="7d431-147">Manually upgrade your 1024-bit keys to 2048-bit DKIM encryption keys</span></span>
<span data-ttu-id="7d431-148"><a name="1024to2048DKIM"> </a></span><span class="sxs-lookup"><span data-stu-id="7d431-148"><a name="1024to2048DKIM"> </a></span></span>

<span data-ttu-id="7d431-149">Já que tanto o número de bits 1024 e o 2048 têm suporte para chaves DKIM, essas instruções mostrarão como atualizar a chave de 1024 para 2048 bits.</span><span class="sxs-lookup"><span data-stu-id="7d431-149">Since both 1024 and 2048 bitness are supported for DKIM keys, these directions will tell you how to upgrade your 1024-bit key to 2048.</span></span> <span data-ttu-id="7d431-150">As etapas a seguir são para dois casos de uso, escolha o que melhor se adapta à sua configuração.</span><span class="sxs-lookup"><span data-stu-id="7d431-150">The steps below are for two use-cases, please choose the one that best fits your configuration.</span></span>

1. <span data-ttu-id="7d431-151">Quando você **já tiver o DKIM configurado**, alterne o número de bits da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="7d431-151">When you **already have DKIM configured**, you rotate bitness as follows:</span></span>

   1. <span data-ttu-id="7d431-152">[Conecte-se às cargas de trabalho do Office 365 pelo PowerShell ](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="7d431-152">[Connect to Office 365 workloads via PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span> <span data-ttu-id="7d431-153">(O cmdlet é proveniente do Exchange Online.)</span><span class="sxs-lookup"><span data-stu-id="7d431-153">(The cmdlet comes from Exchange Online.)</span></span>
   1. <span data-ttu-id="7d431-154">Execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="7d431-154">Run the following command:</span></span>

      ```powershell 
      Rotate-DkimSigningConfig -KeySize 2048 -Identity {Guid of the existing Signing Config}
      ```

1. <span data-ttu-id="7d431-155">Ou para uma **nova implementação do DKIM**:</span><span class="sxs-lookup"><span data-stu-id="7d431-155">Or for a **new implementation of DKIM**:</span></span>

   1. <span data-ttu-id="7d431-156">[Conecte-se às cargas de trabalho do Office 365 pelo PowerShell ](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="7d431-156">[Connect to Office 365 workloads via PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span> <span data-ttu-id="7d431-157">(Este é um cmdlet do Exchange Online.)</span><span class="sxs-lookup"><span data-stu-id="7d431-157">(This is an Exchange Online cmdlet.)</span></span>
   1. <span data-ttu-id="7d431-158">Execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="7d431-158">Run the following command:</span></span>

      ```powershell
      New-DkimSigningConfig -DomainName {Domain for which config is to be created} -KeySize 2048 -Enabled $True
      ```

<span data-ttu-id="7d431-159">Mantenha-se conectado ao Microsoft 365 para *verificar* a configuração.</span><span class="sxs-lookup"><span data-stu-id="7d431-159">Stay connected to Microsoft 365 to *verify* the configuration.</span></span>

1. <span data-ttu-id="7d431-160">Execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="7d431-160">Run the following command:</span></span>

   ```powershell
   Get-DkimSigningConfig -Identity {Domain for which the configuration was set} | Format-List
   ```

> [!TIP]
> <span data-ttu-id="7d431-161">Essa nova chave de 2048 bits entra em vigor no RotateOnDate e enviará emails com a chave 1024 bits provisoriamente.</span><span class="sxs-lookup"><span data-stu-id="7d431-161">This new 2048-bit key takes effect on the RotateOnDate, and will send emails with the 1024-bit key in the interim.</span></span> <span data-ttu-id="7d431-162">Após quatro dias, você poderá testar novamente com a chave de 2048 bits (ou seja, quando a rotação entrar em vigor no segundo seletor).</span><span class="sxs-lookup"><span data-stu-id="7d431-162">After four days, you can test again with the 2048-bit key (that is, once the rotation takes effect to the second selector).</span></span>

<span data-ttu-id="7d431-163">Se deseja alternar para o segundo seletor, as opções são: a) permitir que o serviço do Microsoft 365 alterne o seletor e atualize para o número 2048 de bits nos próximos 6 meses, ou b) após 4 dias confirmado que número 2048 de bits está em uso, alterne manualmente a segunda chave de seletor usando o cmdlet apropriado listado acima.</span><span class="sxs-lookup"><span data-stu-id="7d431-163">If you want to rotate to the second selector, your options are a) let the Microsoft 365 service rotate the selector and upgrade to 2048-bitness within the next 6 months, or b) after 4 days and confirming that 2048-bitness is in use, manually rotate the second selector key by using the appropriate cmdlet listed above.</span></span>

## <a name="steps-you-need-to-do-to-manually-set-up-dkim"></a><span data-ttu-id="7d431-164">O que é necessário fazer para configurar manualmente o DKIM</span><span class="sxs-lookup"><span data-stu-id="7d431-164">Steps you need to do to manually set up DKIM</span></span>
<span data-ttu-id="7d431-165"><a name="SetUpDKIMO365"> </a></span><span class="sxs-lookup"><span data-stu-id="7d431-165"><a name="SetUpDKIMO365"> </a></span></span>

<span data-ttu-id="7d431-166">Para configurar o DKIM, execute estas etapas:</span><span class="sxs-lookup"><span data-stu-id="7d431-166">To configure DKIM, you will complete these steps:</span></span>

- [<span data-ttu-id="7d431-167">Publicar dois registros CNAME para o seu domínio personalizado no DNS</span><span class="sxs-lookup"><span data-stu-id="7d431-167">Publish two CNAME records for your custom domain in DNS</span></span>](use-dkim-to-validate-outbound-email.md#Publish2CNAME)

- [<span data-ttu-id="7d431-168">Habilitar a assinatura DKIM para o seu domínio personalizado</span><span class="sxs-lookup"><span data-stu-id="7d431-168">Enable DKIM signing for your custom domain</span></span>](use-dkim-to-validate-outbound-email.md#EnableDKIMinO365)

### <a name="publish-two-cname-records-for-your-custom-domain-in-dns"></a><span data-ttu-id="7d431-169">Publicar dois registros CNAME para o seu domínio personalizado no DNS</span><span class="sxs-lookup"><span data-stu-id="7d431-169">Publish two CNAME records for your custom domain in DNS</span></span>
<span data-ttu-id="7d431-170"><a name="Publish2CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="7d431-170"><a name="Publish2CNAME"> </a></span></span>

<span data-ttu-id="7d431-171">Para cada domínio para o qual você deseja adicionar uma assinatura de DKIM no DNS, é preciso publicar dois registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="7d431-171">For each domain for which you want to add a DKIM signature in DNS, you need to publish two CNAME records.</span></span>

<span data-ttu-id="7d431-172">Execute os seguintes comandos para criar os registros do seletor:</span><span class="sxs-lookup"><span data-stu-id="7d431-172">Run the following commands to create the selector records:</span></span>

```powershell
New-DkimSigningConfig -DomainName <domain> -Enabled $false
Get-DkimSigningConfig -Identity <domain> | Format-List Selector1CNAME, Selector2CNAME
```

<span data-ttu-id="7d431-173">Se provisionou domínios personalizados além do domínio inicial no Microsoft 365, é necessário publicar dois registros CNAME para cada domínio adicional.</span><span class="sxs-lookup"><span data-stu-id="7d431-173">If you have provisioned custom domains in addition to the initial domain in Microsoft 365, you must publish two CNAME records for each additional domain.</span></span> <span data-ttu-id="7d431-174">Portanto, se tem dois domínios, deve publicar dois registros CNAME no total, e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="7d431-174">So, if you have two domains, you must publish two additional CNAME records, and so on.</span></span>

<span data-ttu-id="7d431-175">Use o seguinte formato para os registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="7d431-175">Use the following format for the CNAME records.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7d431-176">Se você for um dos nossos clientes GCC High, nós calculamos o _domainGuid_ de maneira diferente!</span><span class="sxs-lookup"><span data-stu-id="7d431-176">If you are one of our GCC High customers, we calculate _domainGuid_ differently!</span></span> <span data-ttu-id="7d431-177">Em vez de procurar o registro MX do seu _initialDomain_ para calcular o _domainGuid_, ele é calculado diretamente a partir do domínio personalizado.</span><span class="sxs-lookup"><span data-stu-id="7d431-177">Instead of looking up the MX record for your _initialDomain_ to calculate _domainGuid_, instead we calculate it directly from the customized domain.</span></span> <span data-ttu-id="7d431-178">Por exemplo, se seu domínio personalizado for "contoso.com", o domainGuid vai se tornar "contoso-com", os pontos serão substituídos por um traço.</span><span class="sxs-lookup"><span data-stu-id="7d431-178">For example, if your customized domain is "contoso.com" your domainGuid becomes "contoso-com", any periods are replaced with a dash.</span></span> <span data-ttu-id="7d431-179">Portanto, independentemente de qual registro MX seu initialDomain apontar, você sempre usará o método acima para calcular o domainGuid para usar em seus registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="7d431-179">So, regardless of what MX record your initialDomain points to, you'll always use the above method to calculate the domainGuid to use in your CNAME records.</span></span>

```console
Host name:            selector1._domainkey
Points to address or value:    selector1-<domainGUID>._domainkey.<initialDomain>
TTL:                3600

Host name:            selector2._domainkey
Points to address or value:    selector2-<domainGUID>._domainkey.<initialDomain>
TTL:                3600
```

<span data-ttu-id="7d431-180">Onde:</span><span class="sxs-lookup"><span data-stu-id="7d431-180">Where:</span></span>

- <span data-ttu-id="7d431-181">Para o Microsoft 365, os seletores sempre serão "seletor1" ou "seletor2".</span><span class="sxs-lookup"><span data-stu-id="7d431-181">For Microsoft 365, the selectors will always be "selector1" or "selector2".</span></span>

- <span data-ttu-id="7d431-182">O _domainGUID_ é igual ao _domainGUID_ no registro MX personalizado para o seu domínio personalizado, que aparece antes de mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="7d431-182">_domainGUID_ is the same as the _domainGUID_ in the customized MX record for your custom domain that appears before mail.protection.outlook.com.</span></span> <span data-ttu-id="7d431-183">Por exemplo, no seguinte registro MX para o domínio contoso.com, o _domainGUID_ é contoso-com:</span><span class="sxs-lookup"><span data-stu-id="7d431-183">For example, in the following MX record for the domain contoso.com, the _domainGUID_ is contoso-com:</span></span>

  > <span data-ttu-id="7d431-184">contoso.com.</span><span class="sxs-lookup"><span data-stu-id="7d431-184">contoso.com.</span></span>  <span data-ttu-id="7d431-185">3600  IN  MX   5 contoso-com.mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="7d431-185">3600  IN  MX   5 contoso-com.mail.protection.outlook.com</span></span>

- <span data-ttu-id="7d431-186">O _initialDomain_ foi o domínio usado quando se inscreveu no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7d431-186">_initialDomain_ is the domain that you used when you signed up for Microsoft 365.</span></span> <span data-ttu-id="7d431-187">Os domínios iniciais sempre terminam em onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="7d431-187">Initial domains always end in onmicrosoft.com.</span></span> <span data-ttu-id="7d431-188">Para saber mais sobre como determinar seu domínio inicial, confira [Perguntas frequentes sobre domínios](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain).</span><span class="sxs-lookup"><span data-stu-id="7d431-188">For information about determining your initial domain, see [Domains FAQ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain).</span></span>

<span data-ttu-id="7d431-189">Por exemplo, se você tiver o domínio inicial cohovineyardandwinery.onmicrosoft.com e dois domínios personalizados, cohovineyard.com e cohowinery.com, precisará configurar dois registros CNAME para cada domínio adicional, totalizando quatro registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="7d431-189">For example, if you have an initial domain of cohovineyardandwinery.onmicrosoft.com, and two custom domains cohovineyard.com and cohowinery.com, you would need to set up two CNAME records for each additional domain, for a total of four CNAME records.</span></span>

```console
Host name:            selector1._domainkey
Points to address or value:    selector1-cohovineyard-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:            selector2._domainkey
Points to address or value:    selector2-cohovineyard-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:            selector1._domainkey
Points to address or value:    selector1-cohowinery-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:            selector2._domainkey
Points to address or value:    selector2-cohowinery-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600
```

> [!NOTE]
> <span data-ttu-id="7d431-190">É importante criar o segundo registro, mas apenas um dos seletores pode estar disponível no momento da criação.</span><span class="sxs-lookup"><span data-stu-id="7d431-190">It's important to create the second record, but only one of the selectors may be available at the time of creation.</span></span> <span data-ttu-id="7d431-191">Em essência, o segundo seletor pode apontar para um endereço que ainda não foi criado.</span><span class="sxs-lookup"><span data-stu-id="7d431-191">In essence, the second selector might point to an address that hasn't been created yet.</span></span> <span data-ttu-id="7d431-192">Ainda recomendamos que você crie o segundo registro CNAME, pois a rotação de chaves será contínua.</span><span class="sxs-lookup"><span data-stu-id="7d431-192">We still recommended that you create the second CNAME record, because your key rotation will be seamless.</span></span>

> [!CAUTION]
> <span data-ttu-id="7d431-193">A rotação automática de chaves foi temporariamente desativada, à medida que implementamos algumas alterações de design no modo como criamos as chaves.</span><span class="sxs-lookup"><span data-stu-id="7d431-193">Automatic key rotation has been temporarily disabled as we implement some design changes in how we create keys.</span></span> <span data-ttu-id="7d431-194">É uma boa prática ter várias chaves para que você possa alterná-las periodicamente.</span><span class="sxs-lookup"><span data-stu-id="7d431-194">It's a good practice to have multiple keys so that you can rotate them periodically.</span></span> <span data-ttu-id="7d431-195">Embora seja difícil de decifrar, ainda é uma estratégia de mitigação prática para se proteger de coisas como imitação.</span><span class="sxs-lookup"><span data-stu-id="7d431-195">Although it's hard to crack, it's still a practical mitigation strategy to protect against things like impersonation.</span></span> <span data-ttu-id="7d431-196">Você pode seguir o documento [Rotate-DkimSigningConfig](https://docs.microsoft.com/powershell/module/exchange/rotate-dkimsigningconfig) para ajudar a fazer isso em sua organização.</span><span class="sxs-lookup"><span data-stu-id="7d431-196">You can follow the [Rotate-DkimSigningConfig](https://docs.microsoft.com/powershell/module/exchange/rotate-dkimsigningconfig) document to help do this for your organization.</span></span> <span data-ttu-id="7d431-197">Esperamos que a rotação automática seja ativada novamente em agosto de 2020.</span><span class="sxs-lookup"><span data-stu-id="7d431-197">We expect that automatic rotation will be enabled again by August 2020.</span></span>

### <a name="enable-dkim-signing-for-your-custom-domain"></a><span data-ttu-id="7d431-198">Habilitar a assinatura DKIM para o seu domínio personalizado</span><span class="sxs-lookup"><span data-stu-id="7d431-198">Enable DKIM signing for your custom domain</span></span>
<span data-ttu-id="7d431-199"><a name="EnableDKIMinO365"> </a></span><span class="sxs-lookup"><span data-stu-id="7d431-199"><a name="EnableDKIMinO365"> </a></span></span>

<span data-ttu-id="7d431-200">Após publicar os registros CNAME no DNS, você está pronto para habilitar a assinatura de DKIM através do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7d431-200">Once you have published the CNAME records in DNS, you are ready to enable DKIM signing through Microsoft 365.</span></span> <span data-ttu-id="7d431-201">É possível fazer isso por meio do centro de administração do Microsoft 365 ou usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7d431-201">You can do this either through the Microsoft 365 admin center or by using PowerShell.</span></span>

#### <a name="to-enable-dkim-signing-for-your-custom-domain-through-the-admin-center"></a><span data-ttu-id="7d431-202">Para habilitar a assinatura DKIM para o seu domínio personalizado por meio do centro de administração</span><span class="sxs-lookup"><span data-stu-id="7d431-202">To enable DKIM signing for your custom domain through the admin center</span></span>

1. <span data-ttu-id="7d431-203">[Entre no Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4) com a sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="7d431-203">[Sign in to Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4) with your work or school account.</span></span>

2. <span data-ttu-id="7d431-204">Selecione o ícone do inicializador de aplicativos no canto superior esquerdo e escolha **Administrador**.</span><span class="sxs-lookup"><span data-stu-id="7d431-204">Select the app launcher icon in the upper-left and choose **Admin**.</span></span>

3. <span data-ttu-id="7d431-205">No painel de navegação inferior à esquerda, expanda **Administrador** e escolha **Exchange**.</span><span class="sxs-lookup"><span data-stu-id="7d431-205">In the lower-left navigation, expand **Admin** and choose **Exchange**.</span></span>

4. <span data-ttu-id="7d431-206">Vá para **Proteção** \> **DKIM**.</span><span class="sxs-lookup"><span data-stu-id="7d431-206">Go to **Protection** \> **dkim**.</span></span>

5. <span data-ttu-id="7d431-207">Select the domain for which you want to enable DKIM and then, for **Sign messages for this domain with DKIM signatures**, choose **Enable**.</span><span class="sxs-lookup"><span data-stu-id="7d431-207">Select the domain for which you want to enable DKIM and then, for **Sign messages for this domain with DKIM signatures**, choose **Enable**.</span></span> <span data-ttu-id="7d431-208">Repeat this step for each custom domain.</span><span class="sxs-lookup"><span data-stu-id="7d431-208">Repeat this step for each custom domain.</span></span>

#### <a name="to-enable-dkim-signing-for-your-custom-domain-by-using-powershell"></a><span data-ttu-id="7d431-209">Para habilitar a assinatura DKIM para o seu domínio personalizado usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="7d431-209">To enable DKIM signing for your custom domain by using PowerShell</span></span>

1. <span data-ttu-id="7d431-210">[Conectar-se ao Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="7d431-210">[Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="7d431-211">Execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="7d431-211">Run the following command:</span></span>

   ```powershell
   Set-DkimSigningConfig -Identity <domain> -Enabled $true
   ```

   <span data-ttu-id="7d431-212">Em que _domínio_ é o nome do domínio personalizado para o qual você deseja habilitar a assinatura DKIM.</span><span class="sxs-lookup"><span data-stu-id="7d431-212">Where _domain_ is the name of the custom domain that you want to enable DKIM signing for.</span></span>

   <span data-ttu-id="7d431-213">Por exemplo, para o domínio contoso.com:</span><span class="sxs-lookup"><span data-stu-id="7d431-213">For example, for the domain contoso.com:</span></span>

   ```powershell
   Set-DkimSigningConfig -Identity contoso.com -Enabled $true
   ```

#### <a name="to-confirm-dkim-signing-is-configured-properly-for-microsoft-365"></a><span data-ttu-id="7d431-214">Para confirmar que a assinatura de DKIM está configurada adequadamente no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7d431-214">To Confirm DKIM signing is configured properly for Microsoft 365</span></span>

<span data-ttu-id="7d431-215">Wait a few minutes before you follow these steps to confirm that you have properly configured DKIM.</span><span class="sxs-lookup"><span data-stu-id="7d431-215">Wait a few minutes before you follow these steps to confirm that you have properly configured DKIM.</span></span> <span data-ttu-id="7d431-216">This allows time for the DKIM information about the domain to be spread throughout the network.</span><span class="sxs-lookup"><span data-stu-id="7d431-216">This allows time for the DKIM information about the domain to be spread throughout the network.</span></span>

- <span data-ttu-id="7d431-217">Envie uma mensagem de uma conta do seu domínio do Microsoft 365 habilitado com DKIM para outra conta de email, como outlook.com ou Hotmail.com.</span><span class="sxs-lookup"><span data-stu-id="7d431-217">Send a message from an account within your Microsoft 365 DKIM-enabled domain to another email account such as outlook.com or Hotmail.com.</span></span>

- <span data-ttu-id="7d431-218">Do not use an aol.com account for testing purposes.</span><span class="sxs-lookup"><span data-stu-id="7d431-218">Do not use an aol.com account for testing purposes.</span></span> <span data-ttu-id="7d431-219">AOL may skip the DKIM check if the SPF check passes.</span><span class="sxs-lookup"><span data-stu-id="7d431-219">AOL may skip the DKIM check if the SPF check passes.</span></span> <span data-ttu-id="7d431-220">This will nullify your test.</span><span class="sxs-lookup"><span data-stu-id="7d431-220">This will nullify your test.</span></span>

- <span data-ttu-id="7d431-221">Open the message and look at the header.</span><span class="sxs-lookup"><span data-stu-id="7d431-221">Open the message and look at the header.</span></span> <span data-ttu-id="7d431-222">Instructions for viewing the header for the message will vary depending on your messaging client.</span><span class="sxs-lookup"><span data-stu-id="7d431-222">Instructions for viewing the header for the message will vary depending on your messaging client.</span></span> <span data-ttu-id="7d431-223">For instructions on viewing message headers in Outlook, see [View internet message headers in Outlook](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c).</span><span class="sxs-lookup"><span data-stu-id="7d431-223">For instructions on viewing message headers in Outlook, see [View internet message headers in Outlook](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c).</span></span>

  <span data-ttu-id="7d431-224">The DKIM-signed message will contain the host name and domain you defined when you published the CNAME entries.</span><span class="sxs-lookup"><span data-stu-id="7d431-224">The DKIM-signed message will contain the host name and domain you defined when you published the CNAME entries.</span></span> <span data-ttu-id="7d431-225">The message will look something like this example:</span><span class="sxs-lookup"><span data-stu-id="7d431-225">The message will look something like this example:</span></span>

  ```console
    From: Example User <example@contoso.com>
    DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed;
        s=selector1; d=contoso.com; t=1429912795;
        h=From:To:Message-ID:Subject:MIME-Version:Content-Type;
        bh=<body hash>;
        b=<signed field>;
  ```

- <span data-ttu-id="7d431-226">Look for the Authentication-Results header.</span><span class="sxs-lookup"><span data-stu-id="7d431-226">Look for the Authentication-Results header.</span></span> <span data-ttu-id="7d431-227">While each receiving service uses a slightly different format to stamp the incoming mail, the result should include something like **DKIM=pass** or **DKIM=OK**.</span><span class="sxs-lookup"><span data-stu-id="7d431-227">While each receiving service uses a slightly different format to stamp the incoming mail, the result should include something like **DKIM=pass** or **DKIM=OK**.</span></span>

## <a name="to-configure-dkim-for-more-than-one-custom-domain"></a><span data-ttu-id="7d431-228">Para configurar o DKIM em mais de um domínio personalizado</span><span class="sxs-lookup"><span data-stu-id="7d431-228">To configure DKIM for more than one custom domain</span></span>
<span data-ttu-id="7d431-229"><a name="DKIMMultiDomain"> </a></span><span class="sxs-lookup"><span data-stu-id="7d431-229"><a name="DKIMMultiDomain"> </a></span></span>

<span data-ttu-id="7d431-230">Se em algum momento no futuro você decidir adicionar outro domínio personalizado e quiser habilitar o DKIM para o novo domínio, deve executar as etapas deste artigo para cada domínio.</span><span class="sxs-lookup"><span data-stu-id="7d431-230">If at some point in the future you decide to add another custom domain and you want to enable DKIM for the new domain, you must complete the steps in this article for each domain.</span></span> <span data-ttu-id="7d431-231">Especificamente, execute todas as etapas em [O que é necessário fazer para configurar manualmente o DKIM](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365).</span><span class="sxs-lookup"><span data-stu-id="7d431-231">Specifically, complete all steps in [What you need to do to manually set up DKIM](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365).</span></span>

## <a name="disabling-the-dkim-signing-policy-for-a-custom-domain"></a><span data-ttu-id="7d431-232">Desabilitar a política de assinatura do DKIM para um domínio personalizado</span><span class="sxs-lookup"><span data-stu-id="7d431-232">Disabling the DKIM signing policy for a custom domain</span></span> 
<span data-ttu-id="7d431-233"><a name="DisableDKIMSigningPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="7d431-233"><a name="DisableDKIMSigningPolicy"> </a></span></span>

<span data-ttu-id="7d431-234">Desabilitar a política de assinatura não desabilita completamente o DKIM.</span><span class="sxs-lookup"><span data-stu-id="7d431-234">Disabling the signing policy does not completely disable DKIM.</span></span> <span data-ttu-id="7d431-235">Após um período de tempo, o Microsoft 365 aplicará automaticamente a política padrão ao seu domínio.</span><span class="sxs-lookup"><span data-stu-id="7d431-235">After a period of time, Microsoft 365 will automatically apply the default policy for your domain.</span></span> <span data-ttu-id="7d431-236">Para saber mais, confira [Comportamento padrão do DKIM e do Microsoft 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior).</span><span class="sxs-lookup"><span data-stu-id="7d431-236">For more information, see [Default behavior for DKIM and Microsoft 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior).</span></span>

### <a name="to-disable-the-dkim-signing-policy-by-using-windows-powershell"></a><span data-ttu-id="7d431-237">Para desabilitar a política de assinatura do DKIM usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7d431-237">To disable the DKIM signing policy by using Windows PowerShell</span></span>

1. <span data-ttu-id="7d431-238">[Conectar-se ao Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="7d431-238">[Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="7d431-239">Execute um dos seguintes comandos para cada domínio para o qual você deseja desabilitar a assinatura de DKIM.</span><span class="sxs-lookup"><span data-stu-id="7d431-239">Run one of the following commands for each domain for which you want to disable DKIM signing.</span></span>

   ```powershell
   $p = Get-DkimSigningConfig -Identity <domain>
   $p[0] | Set-DkimSigningConfig -Enabled $false
   ```

   <span data-ttu-id="7d431-240">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="7d431-240">For example:</span></span>

   ```powershell
   $p = Get-DkimSigningConfig -Identity contoso.com
   $p[0] | Set-DkimSigningConfig -Enabled $false
   ```

   <span data-ttu-id="7d431-241">Ou</span><span class="sxs-lookup"><span data-stu-id="7d431-241">Or</span></span>

   ```powershell
   Set-DkimSigningConfig -Identity $p[<number>].Identity -Enabled $false
   ```

   <span data-ttu-id="7d431-242">Em que o _número_ é o índice da política.</span><span class="sxs-lookup"><span data-stu-id="7d431-242">Where _number_ is the index of the policy.</span></span> <span data-ttu-id="7d431-243">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="7d431-243">For example:</span></span>

   ```powershell
   Set-DkimSigningConfig -Identity $p[0].Identity -Enabled $false
   ```

## <a name="default-behavior-for-dkim-and-microsoft-365"></a><span data-ttu-id="7d431-244">Comportamento padrão do DKIM e do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7d431-244">Default behavior for DKIM and Microsoft 365</span></span>
<span data-ttu-id="7d431-245"><a name="DefaultDKIMbehavior"> </a></span><span class="sxs-lookup"><span data-stu-id="7d431-245"><a name="DefaultDKIMbehavior"> </a></span></span>

<span data-ttu-id="7d431-246">Se o DKIM não for habilitado, o Microsoft 365 cria automaticamente uma chave pública de DKIM de 1024 bits para seu domínio padrão e a chave privada associada que é armazenada internamente em nosso datacenter.</span><span class="sxs-lookup"><span data-stu-id="7d431-246">If you do not enable DKIM, Microsoft 365 automatically creates a 1024-bit DKIM public key for your default domain and the associated private key which we store internally in our datacenter.</span></span> <span data-ttu-id="7d431-247">Por padrão, o Microsoft 365 usa uma configuração de assinatura padrão para domínios que não tem uma política aplicada.</span><span class="sxs-lookup"><span data-stu-id="7d431-247">By default, Microsoft 365 uses a default signing configuration for domains that do not have a policy in place.</span></span> <span data-ttu-id="7d431-248">Isso significa que se você não configurar o DKIM, o Microsoft 365 usará a política e as chaves padrão que ele cria para habilitar o DKIM em seu domínio.</span><span class="sxs-lookup"><span data-stu-id="7d431-248">This means that if you do not set up DKIM yourself, Microsoft 365 will use its default policy and keys it creates to enable DKIM for your domain.</span></span>

<span data-ttu-id="7d431-249">Além disso, se desabilitar a assinatura DKIM após ativá-la, após um período de tempo o Microsoft 365 aplicará automaticamente a política padrão em seu domínio.</span><span class="sxs-lookup"><span data-stu-id="7d431-249">Also, if you disable DKIM signing after enabling it, after a period of time, Microsoft 365 will automatically apply the default policy for your domain.</span></span>

<span data-ttu-id="7d431-250">No exemplo a seguir, suponha que o DKIM de fabrikam.com foi habilitado pelo Microsoft 365, não pelo administrador do domínio.</span><span class="sxs-lookup"><span data-stu-id="7d431-250">In the following example, suppose that DKIM for fabrikam.com was enabled by Microsoft 365, not by the administrator of the domain.</span></span> <span data-ttu-id="7d431-251">Isso significa que os CNAMEs necessários não existem no DNS.</span><span class="sxs-lookup"><span data-stu-id="7d431-251">This means that the required CNAMEs do not exist in DNS.</span></span> <span data-ttu-id="7d431-252">Assinaturas DKIM para email deste domínio terão uma aparência similar a esta:</span><span class="sxs-lookup"><span data-stu-id="7d431-252">DKIM signatures for email from this domain will look something like this:</span></span>

```console
From: Second Example <second.example@fabrikam.com>
DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed;
    s=selector1-fabrikam-com; d=contoso.onmicrosoft.com; t=1429912795;
    h=From:To:Message-ID:Subject:MIME-Version:Content-Type;
    bh=<body hash>;
    b=<signed field>;
```

<span data-ttu-id="7d431-253">Neste exemplo, o nome de host e o domínio contêm os valores para os quais o CNAME apontaria se a assinatura de DKIM para fabrikam.com tivesse sido ativada pelo administrador do domínio.</span><span class="sxs-lookup"><span data-stu-id="7d431-253">In this example, the host name and domain contain the values to which the CNAME would point if DKIM-signing for fabrikam.com had been enabled by the domain administrator.</span></span> <span data-ttu-id="7d431-254">Eventualmente, cada mensagem enviada do Microsoft 365 será assinada com DKIM.</span><span class="sxs-lookup"><span data-stu-id="7d431-254">Eventually, every single message sent from Microsoft 365 will be DKIM-signed.</span></span> <span data-ttu-id="7d431-255">Se você mesmo habilitar o DKIM, o domínio será o mesmo que o do campo de endereço From:, neste caso fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="7d431-255">If you enable DKIM yourself, the domain will be the same as the domain in the From: address, in this case fabrikam.com.</span></span> <span data-ttu-id="7d431-256">Caso contrário, os domínios não corresponderão entre si e, em vez disso, será usado o domínio inicial da sua organização.</span><span class="sxs-lookup"><span data-stu-id="7d431-256">If you don't, it will not align and instead will use your organization's initial domain.</span></span> <span data-ttu-id="7d431-257">Para saber mais sobre como determinar seu domínio inicial, confira [Perguntas frequentes sobre domínios](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain).</span><span class="sxs-lookup"><span data-stu-id="7d431-257">For information about determining your initial domain, see [Domains FAQ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain).</span></span>

## <a name="set-up-dkim-so-that-a-third-party-service-can-send-or-spoof-email-on-behalf-of-your-custom-domain"></a><span data-ttu-id="7d431-258">Configurar o DKIM de forma que um serviço terceirizado possa enviar, ou fazer falsificar, emails em nome de seu domínio personalizado</span><span class="sxs-lookup"><span data-stu-id="7d431-258">Set up DKIM so that a third-party service can send, or spoof, email on behalf of your custom domain</span></span>
<span data-ttu-id="7d431-259"><a name="SetUp3rdPartyspoof"> </a></span><span class="sxs-lookup"><span data-stu-id="7d431-259"><a name="SetUp3rdPartyspoof"> </a></span></span>

<span data-ttu-id="7d431-260">Some bulk email service providers, or software-as-a-service providers, let you set up DKIM keys for email that originates from their service.</span><span class="sxs-lookup"><span data-stu-id="7d431-260">Some bulk email service providers, or software-as-a-service providers, let you set up DKIM keys for email that originates from their service.</span></span> <span data-ttu-id="7d431-261">This requires coordination between yourself and the third-party in order to set up the necessary DNS records.</span><span class="sxs-lookup"><span data-stu-id="7d431-261">This requires coordination between yourself and the third-party in order to set up the necessary DNS records.</span></span> <span data-ttu-id="7d431-262">No two organizations do it exactly the same way.</span><span class="sxs-lookup"><span data-stu-id="7d431-262">No two organizations do it exactly the same way.</span></span> <span data-ttu-id="7d431-263">Instead, the process depends entirely on the organization.</span><span class="sxs-lookup"><span data-stu-id="7d431-263">Instead, the process depends entirely on the organization.</span></span>

<span data-ttu-id="7d431-264">Um exemplo de mensagem mostrando um DKIM configurado adequadamente para contoso.com e bulkemailprovider.com pode parecer com este:</span><span class="sxs-lookup"><span data-stu-id="7d431-264">An example message showing a properly configured DKIM for contoso.com and bulkemailprovider.com might look like this:</span></span>

```console
Return-Path: <communication@bulkemailprovider.com>
 From: <sender@contoso.com>
 DKIM-Signature: s=s1024; d=contoso.com
 Subject: Here is a message from Bulk Email Provider's infrastructure, but with a DKIM signature authorized by contoso.com
```

<span data-ttu-id="7d431-265">Neste exemplo, para obter este resultado:</span><span class="sxs-lookup"><span data-stu-id="7d431-265">In this example, in order to achieve this result:</span></span>

1. <span data-ttu-id="7d431-266">O provedor de email em massa deu à Contoso uma chave pública de DKIM.</span><span class="sxs-lookup"><span data-stu-id="7d431-266">Bulk Email Provider gave Contoso a public DKIM key.</span></span>

2. <span data-ttu-id="7d431-267">A Contoso publicou a chave de DKIM em seu registro DNS.</span><span class="sxs-lookup"><span data-stu-id="7d431-267">Contoso published the DKIM key to its DNS record.</span></span>

3. <span data-ttu-id="7d431-268">When sending email, Bulk Email Provider signs the key with the corresponding private key.</span><span class="sxs-lookup"><span data-stu-id="7d431-268">When sending email, Bulk Email Provider signs the key with the corresponding private key.</span></span> <span data-ttu-id="7d431-269">By doing so, Bulk Email Provider attached the DKIM signature to the message header.</span><span class="sxs-lookup"><span data-stu-id="7d431-269">By doing so, Bulk Email Provider attached the DKIM signature to the message header.</span></span>

4. <span data-ttu-id="7d431-270">Sistemas de recebimento de email executam uma verificação de DKIM autenticando o valor DKIM-Signature d=\<domain\> em relação ao domínio no campo de endereço From: (5322.From) da mensagem.</span><span class="sxs-lookup"><span data-stu-id="7d431-270">Receiving email systems perform a DKIM check by authenticating the DKIM-Signature d=\<domain\> value against the domain in the From: (5322.From) address of the message.</span></span> <span data-ttu-id="7d431-271">Neste exemplo, os valores são correspondentes:</span><span class="sxs-lookup"><span data-stu-id="7d431-271">In this example, the values match:</span></span>

   > <span data-ttu-id="7d431-272">remetente@**contoso.com**</span><span class="sxs-lookup"><span data-stu-id="7d431-272">sender@**contoso.com**</span></span>

   > <span data-ttu-id="7d431-273">d=**contoso.com**</span><span class="sxs-lookup"><span data-stu-id="7d431-273">d=**contoso.com**</span></span>

## <a name="next-steps-after-you-set-up-dkim-for-microsoft-365"></a><span data-ttu-id="7d431-274">Próximas etapas: depois de configurar o DKIM no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7d431-274">Next steps: After you set up DKIM for Microsoft 365</span></span>
<span data-ttu-id="7d431-275"><a name="DKIMNextSteps"> </a></span><span class="sxs-lookup"><span data-stu-id="7d431-275"><a name="DKIMNextSteps"> </a></span></span>

<span data-ttu-id="7d431-276">Embora o DKIM tenha sido projetado para ajudar a evitar a falsificação, ele funciona melhor com SPF e DMARC.</span><span class="sxs-lookup"><span data-stu-id="7d431-276">Although DKIM is designed to help prevent spoofing, DKIM works better with SPF and DMARC.</span></span> <span data-ttu-id="7d431-277">Depois que você configurar o DKIM, se já não tiver configurado o SPF, deve fazê-lo.</span><span class="sxs-lookup"><span data-stu-id="7d431-277">Once you have set up DKIM, if you have not already set up SPF you should do so.</span></span> <span data-ttu-id="7d431-278">Para obter uma introdução rápida à SPF e para configurá-la rapidamente, confira [Configurar a SPF no Microsoft 365 para ajudar a evitar falsificação](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span><span class="sxs-lookup"><span data-stu-id="7d431-278">For a quick introduction to SPF and to get it configured quickly, see [Set up SPF in Microsoft 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span> <span data-ttu-id="7d431-279">Para compreender melhor como o Microsoft 365 usa a SPF, para solucionar problemas ou para implantações fora do padrão, como as implantações híbridas, comece com [Como o Microsoft 365 usa a estrutura de política do remetente (SPF) para evitar a falsificação](how-office-365-uses-spf-to-prevent-spoofing.md).</span><span class="sxs-lookup"><span data-stu-id="7d431-279">For a more in-depth understanding of how Microsoft 365 uses SPF, or for troubleshooting or non-standard deployments such as hybrid deployments, start with [How Microsoft 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span> <span data-ttu-id="7d431-280">A seguir, confira [Usar DMARC para validar emails](use-dmarc-to-validate-email.md).</span><span class="sxs-lookup"><span data-stu-id="7d431-280">Next, see [Use DMARC to validate email](use-dmarc-to-validate-email.md).</span></span> <span data-ttu-id="7d431-281">[Cabeçalhos de mensagem antispam](anti-spam-message-headers.md) inclui a sintaxe e os campos de cabeçalho usados pelo Microsoft 365 para verificações de DKIM.</span><span class="sxs-lookup"><span data-stu-id="7d431-281">[Anti-spam message headers](anti-spam-message-headers.md) includes the syntax and header fields used by Microsoft 365 for DKIM checks.</span></span>
