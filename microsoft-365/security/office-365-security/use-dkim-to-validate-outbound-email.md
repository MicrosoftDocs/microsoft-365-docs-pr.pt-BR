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
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Aprenda a usar o e-mail Identificado DomainKeys (DKIM) com o Microsoft 365 para garantir que as mensagens enviadas de seu domínio personalizado sejam confiadas pelos sistemas de e-mail de destino.
ms.openlocfilehash: 66f352b6c3a5d3b3beff3043a3f0d1a435d1e5d1
ms.sourcegitcommit: ff1f0a97e9d43bc786f04d2ea7e01695531b9f28
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2020
ms.locfileid: "49560879"
---
# <a name="use-dkim-to-validate-outbound-email-sent-from-your-custom-domain"></a><span data-ttu-id="2b8e8-103">Usar o DKIM para validar emails enviados de seu domínio personalizado</span><span class="sxs-lookup"><span data-stu-id="2b8e8-103">Use DKIM to validate outbound email sent from your custom domain</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


 <span data-ttu-id="2b8e8-104">**Resumo:** este artigo descreve como você usa o DomainKeys Identified Mail (DKIM) com o Microsoft 365 para garantir que os sistemas de email de destino confiem em mensagens enviadas de saída de seu domínio personalizado.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-104">**Summary:** This article describes how you use DomainKeys Identified Mail (DKIM) with Microsoft 365 to ensure that destination email systems trust messages sent outbound from your custom domain.</span></span>

<span data-ttu-id="2b8e8-105">Você deve usar o DKIM, além do SPF e do DMARC, para ajudar a evitar que spoofers enviem mensagens que pareçam que são provenientes de seu domínio.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-105">You should use DKIM in addition to SPF and DMARC to help prevent spoofers from sending messages that look like they are coming from your domain.</span></span> <span data-ttu-id="2b8e8-106">O DKIM possibilita adicionar uma assinatura digital no cabeçalho de mensagens de email enviadas.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-106">DKIM lets you add a digital signature to outbound email messages in the message header.</span></span> <span data-ttu-id="2b8e8-107">Parece complicado, mas não é.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-107">It may sound complicated, but it's really not.</span></span> <span data-ttu-id="2b8e8-108">Quando você configura o DKIM, autoriza seu domínio a associar, ou fazer login, seu nome a uma mensagem de email usando a autenticação de criptografia.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-108">When you configure DKIM, you authorize your domain to associate, or sign, its name to an email message by using cryptographic authentication.</span></span> <span data-ttu-id="2b8e8-109">Sistemas de email que recebem emails de seu domínio podem usar essa assinatura digital para ajudar a determinar se os emails recebidos são legítimos.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-109">Email systems that receive email from your domain can use this digital signature to help determine if incoming email that they receive is legitimate.</span></span>

<span data-ttu-id="2b8e8-110">Basicamente, você usa uma chave privada para criptografar o cabeçalho no email de saída do seu domínio.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-110">Basically, you use a private key to encrypt the header in your domain's outgoing email.</span></span> <span data-ttu-id="2b8e8-111">Publique uma chave pública nos registros DNS do seu domínio que os servidores de recebimento possam então usar para decodificar a assinatura.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-111">You publish a public key to your domain's DNS records that receiving servers can then use to decode the signature.</span></span> <span data-ttu-id="2b8e8-112">Eles usam a chave pública para confirmar que as mensagens realmente vêm de você e não de alguém que está *falsificando* seu domínio.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-112">They use the public key to verify that the messages are really coming from you and not coming from someone *spoofing* your domain.</span></span>

<span data-ttu-id="2b8e8-113">O Microsoft 365 configura automaticamente o DKIM para domínios iniciais de “onmicrosoft.com”.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-113">Microsoft 365 automatically sets up DKIM for its initial 'onmicrosoft.com' domains.</span></span> <span data-ttu-id="2b8e8-114">Isso significa que não é preciso fazer nada para configurar o DKIM para qualquer nome de domínio inicial (por exemplo, litware.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="2b8e8-114">That means you don't need to do anything to set up DKIM for any initial domain names (for example, litware.onmicrosoft.com).</span></span> <span data-ttu-id="2b8e8-115">Para saber mais sobre domínios, confira [Perguntas frequentes sobre domínios](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain).</span><span class="sxs-lookup"><span data-stu-id="2b8e8-115">For more information about domains, see [Domains FAQ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain).</span></span>

<span data-ttu-id="2b8e8-116">Você também pode optar por não fazer nada sobre o DKIM em relação ao seu domínio personalizado.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-116">You can choose to do nothing about DKIM for your custom domain too.</span></span> <span data-ttu-id="2b8e8-117">Se o DKIM não for configurado para o seu domínio personalizado, o Microsoft 365 criará um par de chaves privada e pública, habilitará a assinatura do DKIM e configurará a política padrão do Microsoft 365 para o seu domínio personalizado.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-117">If you don't set up DKIM for your custom domain, Microsoft 365 creates a private and public key pair, enables DKIM signing, and then configures the Microsoft 365 default policy for your custom domain.</span></span> <span data-ttu-id="2b8e8-118">Embora isso seja abrangente o suficiente para a maioria dos clientes, você deve configurar manualmente o DKIM para o seu domínio personalizado nas seguintes circunstâncias:</span><span class="sxs-lookup"><span data-stu-id="2b8e8-118">While this is sufficient coverage for most customers, you should manually configure DKIM for your custom domain in the following circumstances:</span></span>

- <span data-ttu-id="2b8e8-119">Você tem mais de um domínio personalizado no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2b8e8-119">You have more than one custom domain in Microsoft 365</span></span>

- <span data-ttu-id="2b8e8-120">For configurar o DMARC também (recomendado)</span><span class="sxs-lookup"><span data-stu-id="2b8e8-120">You're going to set up DMARC too (recommended)</span></span>

- <span data-ttu-id="2b8e8-121">Quiser ter controle sobre sua chave privada</span><span class="sxs-lookup"><span data-stu-id="2b8e8-121">You want control over your private key</span></span>

- <span data-ttu-id="2b8e8-122">Quiser personalizar seus registros CNAME</span><span class="sxs-lookup"><span data-stu-id="2b8e8-122">You want to customize your CNAME records</span></span>

- <span data-ttu-id="2b8e8-123">Configure as chaves do DKIM para emails provenientes de um domínio de terceiros, por exemplo, se você usar um programa de email em massa terceirizado.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-123">You want to set up DKIM keys for email originating out of a third-party domain, for example, if you use a third-party bulk mailer.</span></span>

<span data-ttu-id="2b8e8-124">Neste artigo:</span><span class="sxs-lookup"><span data-stu-id="2b8e8-124">In this article:</span></span>

- [<span data-ttu-id="2b8e8-125">Como o DKIM funciona melhor do que o SPF para evitar a falsificação maliciosa</span><span class="sxs-lookup"><span data-stu-id="2b8e8-125">How DKIM works better than SPF alone to prevent malicious spoofing</span></span>](use-dkim-to-validate-outbound-email.md#HowDKIMWorks)

- [<span data-ttu-id="2b8e8-126">Atualize manualmente as chaves de 1024 bits para chaves de criptografia DKIM de 2048 bits</span><span class="sxs-lookup"><span data-stu-id="2b8e8-126">Manually upgrade your 1024-bit keys to 2048-bit DKIM encryption keys</span></span>](use-dkim-to-validate-outbound-email.md#1024to2048DKIM)

- [<span data-ttu-id="2b8e8-127">O que é necessário fazer para configurar manualmente o DKIM</span><span class="sxs-lookup"><span data-stu-id="2b8e8-127">Steps you need to do to manually set up DKIM</span></span>](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365)

- [<span data-ttu-id="2b8e8-128">Para configurar o DKIM para mais de um domínio personalizado</span><span class="sxs-lookup"><span data-stu-id="2b8e8-128">To configure DKIM for more than one custom domain</span></span>](use-dkim-to-validate-outbound-email.md#DKIMMultiDomain)

- [<span data-ttu-id="2b8e8-129">Desabilitar a política de assinatura do DKIM para um domínio personalizado</span><span class="sxs-lookup"><span data-stu-id="2b8e8-129">Disabling the DKIM signing policy for a custom domain</span></span>](use-dkim-to-validate-outbound-email.md#DisableDKIMSigningPolicy)

- [<span data-ttu-id="2b8e8-130">Comportamento padrão para o DKIM e o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2b8e8-130">Default behavior for DKIM and Microsoft 365</span></span>](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior)

- [<span data-ttu-id="2b8e8-131">Configurar o DKIM de forma que um serviço terceirizado possa enviar, ou fazer spoof de, emails em nome de seu domínio personalizado</span><span class="sxs-lookup"><span data-stu-id="2b8e8-131">Set up DKIM so that a third-party service can send, or spoof, email on behalf of your custom domain</span></span>](use-dkim-to-validate-outbound-email.md#SetUp3rdPartyspoof)

- [<span data-ttu-id="2b8e8-132">Próximas etapas: após configurar o DKIM para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2b8e8-132">Next steps: After you set up DKIM for Microsoft 365</span></span>](use-dkim-to-validate-outbound-email.md#DKIMNextSteps)

## <a name="how-dkim-works-better-than-spf-alone-to-prevent-malicious-spoofing"></a><span data-ttu-id="2b8e8-133">Como o DKIM funciona melhor do que o SPF para evitar a falsificação maliciosa</span><span class="sxs-lookup"><span data-stu-id="2b8e8-133">How DKIM works better than SPF alone to prevent malicious spoofing</span></span>
<span data-ttu-id="2b8e8-134"><a name="HowDKIMWorks"> </a></span><span class="sxs-lookup"><span data-stu-id="2b8e8-134"><a name="HowDKIMWorks"> </a></span></span>

<span data-ttu-id="2b8e8-p105">A SPF adiciona informações a um envelope de mensagem, mas o DKIM realmente criptografa uma assinatura dentro do cabeçalho da mensagem. Ao encaminhar uma mensagem, partes de seu envelope podem ser removidas pelo servidor de encaminhamento. Como a assinatura digital permanece com a mensagem de email porque faz parte do cabeçalho do email, o DKIM funciona mesmo quando uma mensagem é encaminhada conforme mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-p105">SPF adds information to a message envelope but DKIM actually encrypts a signature within the message header. When you forward a message, portions of that message's envelope can be stripped away by the forwarding server. Since the digital signature stays with the email message because it's part of the email header, DKIM works even when a message has been forwarded as shown in the following example.</span></span>

![Diagrama que mostra uma mensagem encaminhada passando pela autenticação DKIM onde a verificação de SPF falha](../../media/28f93b4c-97e7-4309-acc4-fd0d2e0e3377.jpg)

<span data-ttu-id="2b8e8-p106">Neste exemplo, se você tivesse apenas publicado um registro TXT SPF do seu domínio, o servidor de email do destinatário poderia ter marcado seu email como spam e gerado um resultado positivo falso. A adição do DKIM neste cenário reduz o resultado positivo falso de spam. Como o DKIM depende de criptografia de chave pública para autenticar, e não apenas de endereços IP, é considerado uma forma muito mais forte de autenticação que o SPF. Recomendamos usar o SPF e o DKIM, bem como o DMARC, em sua implantação.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-p106">In this example, if you had only published an SPF TXT record for your domain, the recipient's mail server could have marked your email as spam and generated a false positive result. The addition of DKIM in this scenario reduces false positive spam reporting. Because DKIM relies on public key cryptography to authenticate and not just IP addresses, DKIM is considered a much stronger form of authentication than SPF. We recommend using both SPF and DKIM, as well as DMARC in your deployment.</span></span>

<span data-ttu-id="2b8e8-p107">Detalhes fundamentais: o DKIM usa uma chave privada para inserir uma assinatura criptografada nos cabeçalhos das mensagens. A domínio que assina, ou domínio de saída, é inserido como o valor do campo **d=** no cabeçalho. O domínio que verifica, ou domínio do destinatário, usa esse campo **d=** para procurar a chave pública no DNS e autenticar a mensagem. Se a mensagem for verificada, passa na verificação do DKIM.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-p107">The nitty gritty: DKIM uses a private key to insert an encrypted signature into the message headers. The signing domain, or outbound domain, is inserted as the value of the **d=** field in the header. The verifying domain, or recipient's domain, then use the **d=** field to look up the public key from DNS and authenticate the message. If the message is verified, the DKIM check passes.</span></span>

## <a name="manually-upgrade-your-1024-bit-keys-to-2048-bit-dkim-encryption-keys"></a><span data-ttu-id="2b8e8-147">Atualize manualmente as chaves de 1024 bits para chaves de criptografia DKIM de 2048 bits</span><span class="sxs-lookup"><span data-stu-id="2b8e8-147">Manually upgrade your 1024-bit keys to 2048-bit DKIM encryption keys</span></span>
<span data-ttu-id="2b8e8-148"><a name="1024to2048DKIM"> </a></span><span class="sxs-lookup"><span data-stu-id="2b8e8-148"><a name="1024to2048DKIM"> </a></span></span>

<span data-ttu-id="2b8e8-149">Já que tanto o número de bits 1024 e o 2048 têm suporte para chaves DKIM, essas instruções mostrarão como atualizar a chave de 1024 para 2048 bits.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-149">Since both 1024 and 2048 bitness are supported for DKIM keys, these directions will tell you how to upgrade your 1024-bit key to 2048.</span></span> <span data-ttu-id="2b8e8-150">As etapas a seguir são para dois casos de uso, escolha o que melhor se adapta à sua configuração.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-150">The steps below are for two use-cases, please choose the one that best fits your configuration.</span></span>

1. <span data-ttu-id="2b8e8-151">Quando você **já tiver o DKIM configurado**, alterne o número de bits da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="2b8e8-151">When you **already have DKIM configured**, you rotate bitness as follows:</span></span>

   1. <span data-ttu-id="2b8e8-152">[Conecte-se às cargas de trabalho do Office 365 pelo PowerShell ](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="2b8e8-152">[Connect to Office 365 workloads via PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window).</span></span> <span data-ttu-id="2b8e8-153">(O cmdlet é proveniente do Exchange Online.)</span><span class="sxs-lookup"><span data-stu-id="2b8e8-153">(The cmdlet comes from Exchange Online.)</span></span>
   1. <span data-ttu-id="2b8e8-154">Execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="2b8e8-154">Run the following command:</span></span>

      ```powershell 
      Rotate-DkimSigningConfig -KeySize 2048 -Identity {Guid of the existing Signing Config}
      ```

1. <span data-ttu-id="2b8e8-155">Ou para uma **nova implementação do DKIM**:</span><span class="sxs-lookup"><span data-stu-id="2b8e8-155">Or for a **new implementation of DKIM**:</span></span>

   1. <span data-ttu-id="2b8e8-156">[Conecte-se às cargas de trabalho do Office 365 pelo PowerShell ](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="2b8e8-156">[Connect to Office 365 workloads via PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window).</span></span> <span data-ttu-id="2b8e8-157">(Este é um cmdlet do Exchange Online.)</span><span class="sxs-lookup"><span data-stu-id="2b8e8-157">(This is an Exchange Online cmdlet.)</span></span>
   1. <span data-ttu-id="2b8e8-158">Execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="2b8e8-158">Run the following command:</span></span>

      ```powershell
      New-DkimSigningConfig -DomainName {Domain for which config is to be created} -KeySize 2048 -Enabled $True
      ```

<span data-ttu-id="2b8e8-159">Mantenha-se conectado ao Microsoft 365 para *verificar* a configuração.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-159">Stay connected to Microsoft 365 to *verify* the configuration.</span></span>

1. <span data-ttu-id="2b8e8-160">Execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="2b8e8-160">Run the following command:</span></span>

   ```powershell
   Get-DkimSigningConfig -Identity {Domain for which the configuration was set} | Format-List
   ```

> [!TIP]
> <span data-ttu-id="2b8e8-161">Essa nova chave de 2048 bits entra em vigor no RotateOnDate e enviará emails com a chave 1024 bits provisoriamente.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-161">This new 2048-bit key takes effect on the RotateOnDate, and will send emails with the 1024-bit key in the interim.</span></span> <span data-ttu-id="2b8e8-162">Após quatro dias, você poderá testar novamente com a chave de 2048 bits (ou seja, quando a rotação entrar em vigor no segundo seletor).</span><span class="sxs-lookup"><span data-stu-id="2b8e8-162">After four days, you can test again with the 2048-bit key (that is, once the rotation takes effect to the second selector).</span></span>

<span data-ttu-id="2b8e8-163">Se deseja alternar para o segundo seletor, as opções são: a) permitir que o serviço do Microsoft 365 alterne o seletor e atualize para o número 2048 de bits nos próximos 6 meses, ou b) após 4 dias confirmado que número 2048 de bits está em uso, alterne manualmente a segunda chave de seletor usando o cmdlet apropriado listado acima.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-163">If you want to rotate to the second selector, your options are a) let the Microsoft 365 service rotate the selector and upgrade to 2048-bitness within the next 6 months, or b) after 4 days and confirming that 2048-bitness is in use, manually rotate the second selector key by using the appropriate cmdlet listed above.</span></span>

## <a name="steps-you-need-to-do-to-manually-set-up-dkim"></a><span data-ttu-id="2b8e8-164">O que é necessário fazer para configurar manualmente o DKIM</span><span class="sxs-lookup"><span data-stu-id="2b8e8-164">Steps you need to do to manually set up DKIM</span></span>
<span data-ttu-id="2b8e8-165"><a name="SetUpDKIMO365"> </a></span><span class="sxs-lookup"><span data-stu-id="2b8e8-165"><a name="SetUpDKIMO365"> </a></span></span>

<span data-ttu-id="2b8e8-166">Para configurar o DKIM, execute estas etapas:</span><span class="sxs-lookup"><span data-stu-id="2b8e8-166">To configure DKIM, you will complete these steps:</span></span>

- [<span data-ttu-id="2b8e8-167">Publicar dois registros CNAME para o seu domínio personalizado no DNS</span><span class="sxs-lookup"><span data-stu-id="2b8e8-167">Publish two CNAME records for your custom domain in DNS</span></span>](use-dkim-to-validate-outbound-email.md#Publish2CNAME)

- [<span data-ttu-id="2b8e8-168">Habilitar a assinatura DKIM para o seu domínio personalizado</span><span class="sxs-lookup"><span data-stu-id="2b8e8-168">Enable DKIM signing for your custom domain</span></span>](use-dkim-to-validate-outbound-email.md#EnableDKIMinO365)

### <a name="publish-two-cname-records-for-your-custom-domain-in-dns"></a><span data-ttu-id="2b8e8-169">Publicar dois registros CNAME para o seu domínio personalizado no DNS</span><span class="sxs-lookup"><span data-stu-id="2b8e8-169">Publish two CNAME records for your custom domain in DNS</span></span>
<span data-ttu-id="2b8e8-170"><a name="Publish2CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="2b8e8-170"><a name="Publish2CNAME"> </a></span></span>

<span data-ttu-id="2b8e8-171">Para cada domínio para o qual você deseja adicionar uma assinatura de DKIM no DNS, é preciso publicar dois registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-171">For each domain for which you want to add a DKIM signature in DNS, you need to publish two CNAME records.</span></span>

> [!NOTE]
> <span data-ttu-id="2b8e8-172">Se você ainda não leu o artigo, pode ter perdido essas informações de conexão do Windows PowerShell que estão prestes a economizar tempo: [Conectar-se às cargas de trabalho do Office 365 por meio do Windows PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="2b8e8-172">If you haven't read the full article, you may have missed this time-saving PowerShell connection information: [Connect to Office 365 workloads via PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window).</span></span> <span data-ttu-id="2b8e8-173">(O cmdlet é proveniente do Exchange Online.)</span><span class="sxs-lookup"><span data-stu-id="2b8e8-173">(The cmdlet comes from Exchange Online.)</span></span> 

<span data-ttu-id="2b8e8-174">Execute os seguintes comandos para criar os registros do seletor:</span><span class="sxs-lookup"><span data-stu-id="2b8e8-174">Run the following commands to create the selector records:</span></span>

```powershell
New-DkimSigningConfig -DomainName <domain> -Enabled $false
Get-DkimSigningConfig -Identity <domain> | Format-List Selector1CNAME, Selector2CNAME
```

<span data-ttu-id="2b8e8-175">Se provisionou domínios personalizados além do domínio inicial no Microsoft 365, é necessário publicar dois registros CNAME para cada domínio adicional.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-175">If you have provisioned custom domains in addition to the initial domain in Microsoft 365, you must publish two CNAME records for each additional domain.</span></span> <span data-ttu-id="2b8e8-176">Portanto, se tem dois domínios, deve publicar dois registros CNAME no total, e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-176">So, if you have two domains, you must publish two additional CNAME records, and so on.</span></span>

<span data-ttu-id="2b8e8-177">Use o seguinte formato para os registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-177">Use the following format for the CNAME records.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2b8e8-178">Se você for um dos nossos clientes GCC High, nós calculamos o _domainGuid_ de maneira diferente!</span><span class="sxs-lookup"><span data-stu-id="2b8e8-178">If you are one of our GCC High customers, we calculate _domainGuid_ differently!</span></span> <span data-ttu-id="2b8e8-179">Em vez de procurar o registro MX do seu _initialDomain_ para calcular o _domainGuid_, ele é calculado diretamente a partir do domínio personalizado.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-179">Instead of looking up the MX record for your _initialDomain_ to calculate _domainGuid_, instead we calculate it directly from the customized domain.</span></span> <span data-ttu-id="2b8e8-180">Por exemplo, se seu domínio personalizado for "contoso.com", o domainGuid vai se tornar "contoso-com", os pontos serão substituídos por um traço.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-180">For example, if your customized domain is "contoso.com" your domainGuid becomes "contoso-com", any periods are replaced with a dash.</span></span> <span data-ttu-id="2b8e8-181">Portanto, independentemente de qual registro MX seu initialDomain apontar, você sempre usará o método acima para calcular o domainGuid para usar em seus registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-181">So, regardless of what MX record your initialDomain points to, you'll always use the above method to calculate the domainGuid to use in your CNAME records.</span></span>

```console
Host name:            selector1._domainkey
Points to address or value:    selector1-<domainGUID>._domainkey.<initialDomain>
TTL:                3600

Host name:            selector2._domainkey
Points to address or value:    selector2-<domainGUID>._domainkey.<initialDomain>
TTL:                3600
```

<span data-ttu-id="2b8e8-182">Onde:</span><span class="sxs-lookup"><span data-stu-id="2b8e8-182">Where:</span></span>

- <span data-ttu-id="2b8e8-183">Para o Microsoft 365, os seletores sempre serão "seletor1" ou "seletor2".</span><span class="sxs-lookup"><span data-stu-id="2b8e8-183">For Microsoft 365, the selectors will always be "selector1" or "selector2".</span></span>

- <span data-ttu-id="2b8e8-184">O _domainGUID_ é igual ao _domainGUID_ no registro MX personalizado para o seu domínio personalizado, que aparece antes de mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-184">_domainGUID_ is the same as the _domainGUID_ in the customized MX record for your custom domain that appears before mail.protection.outlook.com.</span></span> <span data-ttu-id="2b8e8-185">Por exemplo, no seguinte registro MX para o domínio contoso.com, o _domainGUID_ é contoso-com:</span><span class="sxs-lookup"><span data-stu-id="2b8e8-185">For example, in the following MX record for the domain contoso.com, the _domainGUID_ is contoso-com:</span></span>

  > <span data-ttu-id="2b8e8-186">contoso.com.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-186">contoso.com.</span></span>  <span data-ttu-id="2b8e8-187">3600  IN  MX   5 contoso-com.mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="2b8e8-187">3600  IN  MX   5 contoso-com.mail.protection.outlook.com</span></span>

- <span data-ttu-id="2b8e8-188">O _initialDomain_ foi o domínio usado quando se inscreveu no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-188">_initialDomain_ is the domain that you used when you signed up for Microsoft 365.</span></span> <span data-ttu-id="2b8e8-189">Os domínios iniciais sempre terminam em onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-189">Initial domains always end in onmicrosoft.com.</span></span> <span data-ttu-id="2b8e8-190">Para saber mais sobre como determinar seu domínio inicial, confira [Perguntas frequentes sobre domínios](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain).</span><span class="sxs-lookup"><span data-stu-id="2b8e8-190">For information about determining your initial domain, see [Domains FAQ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain).</span></span>

<span data-ttu-id="2b8e8-191">Por exemplo, se você tiver o domínio inicial cohovineyardandwinery.onmicrosoft.com e dois domínios personalizados, cohovineyard.com e cohowinery.com, precisará configurar dois registros CNAME para cada domínio adicional, totalizando quatro registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-191">For example, if you have an initial domain of cohovineyardandwinery.onmicrosoft.com, and two custom domains cohovineyard.com and cohowinery.com, you would need to set up two CNAME records for each additional domain, for a total of four CNAME records.</span></span>

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
> <span data-ttu-id="2b8e8-192">É importante criar o segundo registro, mas apenas um dos seletores pode estar disponível no momento da criação.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-192">It's important to create the second record, but only one of the selectors may be available at the time of creation.</span></span> <span data-ttu-id="2b8e8-193">Em essência, o segundo seletor pode apontar para um endereço que ainda não foi criado.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-193">In essence, the second selector might point to an address that hasn't been created yet.</span></span> <span data-ttu-id="2b8e8-194">Ainda recomendamos que você crie o segundo registro CNAME, pois a rotação de chaves será contínua.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-194">We still recommended that you create the second CNAME record, because your key rotation will be seamless.</span></span>


### <a name="enable-dkim-signing-for-your-custom-domain"></a><span data-ttu-id="2b8e8-195">Habilitar a assinatura DKIM para o seu domínio personalizado</span><span class="sxs-lookup"><span data-stu-id="2b8e8-195">Enable DKIM signing for your custom domain</span></span>
<span data-ttu-id="2b8e8-196"><a name="EnableDKIMinO365"> </a></span><span class="sxs-lookup"><span data-stu-id="2b8e8-196"><a name="EnableDKIMinO365"> </a></span></span>

<span data-ttu-id="2b8e8-197">Após publicar os registros CNAME no DNS, você está pronto para habilitar a assinatura de DKIM através do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-197">Once you have published the CNAME records in DNS, you are ready to enable DKIM signing through Microsoft 365.</span></span> <span data-ttu-id="2b8e8-198">É possível fazer isso por meio do centro de administração do Microsoft 365 ou usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-198">You can do this either through the Microsoft 365 admin center or by using PowerShell.</span></span>

#### <a name="to-enable-dkim-signing-for-your-custom-domain-through-the-admin-center"></a><span data-ttu-id="2b8e8-199">Para habilitar a assinatura DKIM para o seu domínio personalizado por meio do centro de administração</span><span class="sxs-lookup"><span data-stu-id="2b8e8-199">To enable DKIM signing for your custom domain through the admin center</span></span>

1. <span data-ttu-id="2b8e8-200">[Entre no Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4) com a sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-200">[Sign in to Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4) with your work or school account.</span></span>

2. <span data-ttu-id="2b8e8-201">Selecione o ícone do inicializador de aplicativos no canto superior esquerdo e escolha **Administrador**.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-201">Select the app launcher icon in the upper-left and choose **Admin**.</span></span>

3. <span data-ttu-id="2b8e8-202">No painel de navegação inferior à esquerda, expanda **Administrador** e escolha **Exchange**.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-202">In the lower-left navigation, expand **Admin** and choose **Exchange**.</span></span>

4. <span data-ttu-id="2b8e8-203">Vá para **Proteção** \> **DKIM**.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-203">Go to **Protection** \> **dkim**.</span></span>

5. <span data-ttu-id="2b8e8-p120">Selecione o domínio para o qual você deseja habilitar o DKIM e, para **Assinar mensagens deste domínio com assinaturas DKIM**, escolha **Habilitar**. Repita essa etapa para cada domínio personalizado.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-p120">Select the domain for which you want to enable DKIM and then, for **Sign messages for this domain with DKIM signatures**, choose **Enable**. Repeat this step for each custom domain.</span></span>

#### <a name="to-enable-dkim-signing-for-your-custom-domain-by-using-powershell"></a><span data-ttu-id="2b8e8-206">Para habilitar a assinatura DKIM para o seu domínio personalizado usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="2b8e8-206">To enable DKIM signing for your custom domain by using PowerShell</span></span>

1. <span data-ttu-id="2b8e8-207">[Conectar-se ao Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="2b8e8-207">[Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="2b8e8-208">Execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="2b8e8-208">Run the following command:</span></span>

   ```powershell
   Set-DkimSigningConfig -Identity <domain> -Enabled $true
   ```

   <span data-ttu-id="2b8e8-209">Em que _domínio_ é o nome do domínio personalizado para o qual você deseja habilitar a assinatura DKIM.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-209">Where _domain_ is the name of the custom domain that you want to enable DKIM signing for.</span></span>

   <span data-ttu-id="2b8e8-210">Por exemplo, para o domínio contoso.com:</span><span class="sxs-lookup"><span data-stu-id="2b8e8-210">For example, for the domain contoso.com:</span></span>

   ```powershell
   Set-DkimSigningConfig -Identity contoso.com -Enabled $true
   ```

#### <a name="to-confirm-dkim-signing-is-configured-properly-for-microsoft-365"></a><span data-ttu-id="2b8e8-211">Para confirmar que a assinatura de DKIM está configurada adequadamente no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2b8e8-211">To Confirm DKIM signing is configured properly for Microsoft 365</span></span>

<span data-ttu-id="2b8e8-p121">Aguarde alguns minutos antes de prosseguir com essas etapas para confirmar que você configurou o DKIM corretamente. Isso permite que as informações do DKIM sobre o domínio sejam distribuídas por toda a rede.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-p121">Wait a few minutes before you follow these steps to confirm that you have properly configured DKIM. This allows time for the DKIM information about the domain to be spread throughout the network.</span></span>

- <span data-ttu-id="2b8e8-214">Envie uma mensagem de uma conta do seu domínio do Microsoft 365 habilitado com DKIM para outra conta de email, como outlook.com ou Hotmail.com.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-214">Send a message from an account within your Microsoft 365 DKIM-enabled domain to another email account such as outlook.com or Hotmail.com.</span></span>

- <span data-ttu-id="2b8e8-p122">Não use uma conta aol.com para fins de teste. A AOL pode ignorar a verificação de DKIM se a verificação de SPF passar. Isso anula o teste.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-p122">Do not use an aol.com account for testing purposes. AOL may skip the DKIM check if the SPF check passes. This will nullify your test.</span></span>

- <span data-ttu-id="2b8e8-p123">Abra a mensagem e veja o cabeçalho. As instruções para exibir o cabeçalho da mensagem variam dependendo do seu cliente de mensagens. Para obter instruções sobre como exibir cabeçalhos de mensagens no Outlook, consulte [Exibir cabeçalhos de mensagens da Internet no Outlook](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c).</span><span class="sxs-lookup"><span data-stu-id="2b8e8-p123">Open the message and look at the header. Instructions for viewing the header for the message will vary depending on your messaging client. For instructions on viewing message headers in Outlook, see [View internet message headers in Outlook](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c).</span></span>

  <span data-ttu-id="2b8e8-p124">A mensagem assinada com DKIM conterá o nome do host e o domínio definidos quando você publicou as entradas CNAME. A mensagem terá uma aparência similar à do exemplo:</span><span class="sxs-lookup"><span data-stu-id="2b8e8-p124">The DKIM-signed message will contain the host name and domain you defined when you published the CNAME entries. The message will look something like this example:</span></span>

  ```console
    From: Example User <example@contoso.com>
    DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed;
        s=selector1; d=contoso.com; t=1429912795;
        h=From:To:Message-ID:Subject:MIME-Version:Content-Type;
        bh=<body hash>;
        b=<signed field>;
  ```

- <span data-ttu-id="2b8e8-p125">Procure pelo cabeçalho Authentication-Results. Embora cada serviço receptor use um formato ligeiramente diferente para carimbar as mensagens recebidas, o resultado deve incluir algo parecido com **DKIM=pass** ou **DKIM=OK**.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-p125">Look for the Authentication-Results header. While each receiving service uses a slightly different format to stamp the incoming mail, the result should include something like **DKIM=pass** or **DKIM=OK**.</span></span>

## <a name="to-configure-dkim-for-more-than-one-custom-domain"></a><span data-ttu-id="2b8e8-225">Para configurar o DKIM em mais de um domínio personalizado</span><span class="sxs-lookup"><span data-stu-id="2b8e8-225">To configure DKIM for more than one custom domain</span></span>
<span data-ttu-id="2b8e8-226"><a name="DKIMMultiDomain"> </a></span><span class="sxs-lookup"><span data-stu-id="2b8e8-226"><a name="DKIMMultiDomain"> </a></span></span>

<span data-ttu-id="2b8e8-227">Se em algum momento no futuro você decidir adicionar outro domínio personalizado e quiser habilitar o DKIM para o novo domínio, deve executar as etapas deste artigo para cada domínio.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-227">If at some point in the future you decide to add another custom domain and you want to enable DKIM for the new domain, you must complete the steps in this article for each domain.</span></span> <span data-ttu-id="2b8e8-228">Especificamente, execute todas as etapas em [O que é necessário fazer para configurar manualmente o DKIM](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365).</span><span class="sxs-lookup"><span data-stu-id="2b8e8-228">Specifically, complete all steps in [What you need to do to manually set up DKIM](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365).</span></span>

## <a name="disabling-the-dkim-signing-policy-for-a-custom-domain"></a><span data-ttu-id="2b8e8-229">Desabilitar a política de assinatura do DKIM para um domínio personalizado</span><span class="sxs-lookup"><span data-stu-id="2b8e8-229">Disabling the DKIM signing policy for a custom domain</span></span> 
<span data-ttu-id="2b8e8-230"><a name="DisableDKIMSigningPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="2b8e8-230"><a name="DisableDKIMSigningPolicy"> </a></span></span>

<span data-ttu-id="2b8e8-231">Desabilitar a política de assinatura não desabilita completamente o DKIM.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-231">Disabling the signing policy does not completely disable DKIM.</span></span> <span data-ttu-id="2b8e8-232">Após um período de tempo, o Microsoft 365 aplicará automaticamente a política padrão ao seu domínio.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-232">After a period of time, Microsoft 365 will automatically apply the default policy for your domain.</span></span> <span data-ttu-id="2b8e8-233">Para saber mais, confira [Comportamento padrão do DKIM e do Microsoft 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior).</span><span class="sxs-lookup"><span data-stu-id="2b8e8-233">For more information, see [Default behavior for DKIM and Microsoft 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior).</span></span>

### <a name="to-disable-the-dkim-signing-policy-by-using-windows-powershell"></a><span data-ttu-id="2b8e8-234">Para desabilitar a política de assinatura do DKIM usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2b8e8-234">To disable the DKIM signing policy by using Windows PowerShell</span></span>

1. <span data-ttu-id="2b8e8-235">[Conectar-se ao Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="2b8e8-235">[Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="2b8e8-236">Execute um dos seguintes comandos para cada domínio para o qual você deseja desabilitar a assinatura de DKIM.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-236">Run one of the following commands for each domain for which you want to disable DKIM signing.</span></span>

   ```powershell
   $p = Get-DkimSigningConfig -Identity <domain>
   $p[0] | Set-DkimSigningConfig -Enabled $false
   ```

   <span data-ttu-id="2b8e8-237">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="2b8e8-237">For example:</span></span>

   ```powershell
   $p = Get-DkimSigningConfig -Identity contoso.com
   $p[0] | Set-DkimSigningConfig -Enabled $false
   ```

   <span data-ttu-id="2b8e8-238">Ou</span><span class="sxs-lookup"><span data-stu-id="2b8e8-238">Or</span></span>

   ```powershell
   Set-DkimSigningConfig -Identity $p[<number>].Identity -Enabled $false
   ```

   <span data-ttu-id="2b8e8-239">Em que o _número_ é o índice da política.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-239">Where _number_ is the index of the policy.</span></span> <span data-ttu-id="2b8e8-240">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="2b8e8-240">For example:</span></span>

   ```powershell
   Set-DkimSigningConfig -Identity $p[0].Identity -Enabled $false
   ```

## <a name="default-behavior-for-dkim-and-microsoft-365"></a><span data-ttu-id="2b8e8-241">Comportamento padrão do DKIM e do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2b8e8-241">Default behavior for DKIM and Microsoft 365</span></span>
<span data-ttu-id="2b8e8-242"><a name="DefaultDKIMbehavior"> </a></span><span class="sxs-lookup"><span data-stu-id="2b8e8-242"><a name="DefaultDKIMbehavior"> </a></span></span>

<span data-ttu-id="2b8e8-243">Se o DKIM não for habilitado, o Microsoft 365 cria automaticamente uma chave pública de DKIM de 1024 bits para seu domínio padrão e a chave privada associada que é armazenada internamente em nosso datacenter.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-243">If you do not enable DKIM, Microsoft 365 automatically creates a 1024-bit DKIM public key for your default domain and the associated private key which we store internally in our datacenter.</span></span> <span data-ttu-id="2b8e8-244">Por padrão, o Microsoft 365 usa uma configuração de assinatura padrão para domínios que não tem uma política aplicada.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-244">By default, Microsoft 365 uses a default signing configuration for domains that do not have a policy in place.</span></span> <span data-ttu-id="2b8e8-245">Isso significa que se você não configurar o DKIM, o Microsoft 365 usará a política e as chaves padrão que ele cria para habilitar o DKIM em seu domínio.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-245">This means that if you do not set up DKIM yourself, Microsoft 365 will use its default policy and keys it creates to enable DKIM for your domain.</span></span>

<span data-ttu-id="2b8e8-246">Além disso, se desabilitar a assinatura DKIM após ativá-la, após um período de tempo o Microsoft 365 aplicará automaticamente a política padrão em seu domínio.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-246">Also, if you disable DKIM signing after enabling it, after a period of time, Microsoft 365 will automatically apply the default policy for your domain.</span></span>

<span data-ttu-id="2b8e8-247">No exemplo a seguir, suponha que o DKIM de fabrikam.com foi habilitado pelo Microsoft 365, não pelo administrador do domínio.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-247">In the following example, suppose that DKIM for fabrikam.com was enabled by Microsoft 365, not by the administrator of the domain.</span></span> <span data-ttu-id="2b8e8-248">Isso significa que os CNAMEs necessários não existem no DNS.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-248">This means that the required CNAMEs do not exist in DNS.</span></span> <span data-ttu-id="2b8e8-249">Assinaturas DKIM para email deste domínio terão uma aparência similar a esta:</span><span class="sxs-lookup"><span data-stu-id="2b8e8-249">DKIM signatures for email from this domain will look something like this:</span></span>

```console
From: Second Example <second.example@fabrikam.com>
DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed;
    s=selector1-fabrikam-com; d=contoso.onmicrosoft.com; t=1429912795;
    h=From:To:Message-ID:Subject:MIME-Version:Content-Type;
    bh=<body hash>;
    b=<signed field>;
```

<span data-ttu-id="2b8e8-250">Neste exemplo, o nome de host e o domínio contêm os valores para os quais o CNAME apontaria se a assinatura de DKIM para fabrikam.com tivesse sido ativada pelo administrador do domínio.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-250">In this example, the host name and domain contain the values to which the CNAME would point if DKIM-signing for fabrikam.com had been enabled by the domain administrator.</span></span> <span data-ttu-id="2b8e8-251">Eventualmente, cada mensagem enviada do Microsoft 365 será assinada com DKIM.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-251">Eventually, every single message sent from Microsoft 365 will be DKIM-signed.</span></span> <span data-ttu-id="2b8e8-252">Se você mesmo habilitar o DKIM, o domínio será o mesmo que o do campo de endereço From:, neste caso fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-252">If you enable DKIM yourself, the domain will be the same as the domain in the From: address, in this case fabrikam.com.</span></span> <span data-ttu-id="2b8e8-253">Caso contrário, os domínios não corresponderão entre si e, em vez disso, será usado o domínio inicial da sua organização.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-253">If you don't, it will not align and instead will use your organization's initial domain.</span></span> <span data-ttu-id="2b8e8-254">Para saber mais sobre como determinar seu domínio inicial, confira [Perguntas frequentes sobre domínios](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain).</span><span class="sxs-lookup"><span data-stu-id="2b8e8-254">For information about determining your initial domain, see [Domains FAQ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain).</span></span>

## <a name="set-up-dkim-so-that-a-third-party-service-can-send-or-spoof-email-on-behalf-of-your-custom-domain"></a><span data-ttu-id="2b8e8-255">Configurar o DKIM de forma que um serviço terceirizado possa enviar, ou fazer falsificar, emails em nome de seu domínio personalizado</span><span class="sxs-lookup"><span data-stu-id="2b8e8-255">Set up DKIM so that a third-party service can send, or spoof, email on behalf of your custom domain</span></span>
<span data-ttu-id="2b8e8-256"><a name="SetUp3rdPartyspoof"> </a></span><span class="sxs-lookup"><span data-stu-id="2b8e8-256"><a name="SetUp3rdPartyspoof"> </a></span></span>

<span data-ttu-id="2b8e8-257">Alguns provedores de serviço de hospedagem de email em massa, ou provedores de software como serviço, permitem que você configure as chaves DKIM para o email originado de seu serviço.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-257">Some bulk email service providers, or software-as-a-service providers, let you set up DKIM keys for email that originates from their service.</span></span> <span data-ttu-id="2b8e8-258">Isso requer coordenação entre você e o terceiro para configurar os registros DNS necessários.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-258">This requires coordination between yourself and the third-party in order to set up the necessary DNS records.</span></span> <span data-ttu-id="2b8e8-259">Alguns servidores de terceiros podem ter seus próprios registros CNAME com seletores diferentes.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-259">Some third-party servers can have their own CNAME records with different selectors.</span></span> <span data-ttu-id="2b8e8-260">Não há duas organizações que fazem isso exatamente da mesma maneira.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-260">No two organizations do it exactly the same way.</span></span> <span data-ttu-id="2b8e8-261">Em vez disso, o processo depende totalmente da organização.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-261">Instead, the process depends entirely on the organization.</span></span>

<span data-ttu-id="2b8e8-262">Um exemplo de mensagem mostrando um DKIM configurado adequadamente para contoso.com e bulkemailprovider.com pode parecer com este:</span><span class="sxs-lookup"><span data-stu-id="2b8e8-262">An example message showing a properly configured DKIM for contoso.com and bulkemailprovider.com might look like this:</span></span>

```console
Return-Path: <communication@bulkemailprovider.com>
 From: <sender@contoso.com>
 DKIM-Signature: s=s1024; d=contoso.com
 Subject: Here is a message from Bulk Email Provider's infrastructure, but with a DKIM signature authorized by contoso.com
```

<span data-ttu-id="2b8e8-263">Neste exemplo, para obter este resultado:</span><span class="sxs-lookup"><span data-stu-id="2b8e8-263">In this example, in order to achieve this result:</span></span>

1. <span data-ttu-id="2b8e8-264">O provedor de email em massa deu à Contoso uma chave pública de DKIM.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-264">Bulk Email Provider gave Contoso a public DKIM key.</span></span>

2. <span data-ttu-id="2b8e8-265">A Contoso publicou a chave de DKIM em seu registro DNS.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-265">Contoso published the DKIM key to its DNS record.</span></span>

3. <span data-ttu-id="2b8e8-p133">Ao enviar emails, o Provedor de Email em Massa assina a chave com a chave privada correspondente. Ao fazer isso, o Provedor de Email em Massa anexa a assinatura DKIM ao cabeçalho da mensagem.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-p133">When sending email, Bulk Email Provider signs the key with the corresponding private key. By doing so, Bulk Email Provider attached the DKIM signature to the message header.</span></span>

4. <span data-ttu-id="2b8e8-268">Sistemas de recebimento de email executam uma verificação de DKIM autenticando o valor DKIM-Signature d=\<domain\> em relação ao domínio no campo de endereço From: (5322.From) da mensagem.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-268">Receiving email systems perform a DKIM check by authenticating the DKIM-Signature d=\<domain\> value against the domain in the From: (5322.From) address of the message.</span></span> <span data-ttu-id="2b8e8-269">Neste exemplo, os valores são correspondentes:</span><span class="sxs-lookup"><span data-stu-id="2b8e8-269">In this example, the values match:</span></span>

   > <span data-ttu-id="2b8e8-270">remetente@**contoso.com**</span><span class="sxs-lookup"><span data-stu-id="2b8e8-270">sender@**contoso.com**</span></span>

   > <span data-ttu-id="2b8e8-271">d=**contoso.com**</span><span class="sxs-lookup"><span data-stu-id="2b8e8-271">d=**contoso.com**</span></span>
   
## <a name="identify-domains-that-do-not-send-email"></a><span data-ttu-id="2b8e8-272">Identificar domínios que não enviam email</span><span class="sxs-lookup"><span data-stu-id="2b8e8-272">Identify domains that do not send email</span></span>

<span data-ttu-id="2b8e8-273">As organizações devem declarar explicitamente se um domínio não envia email especificando `v=DKIM1; p=`estes domínios no registro DKIM.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-273">Organizations should explicitly state if a domain does not send email by specifying `v=DKIM1; p=` in the DKIM record for those domains.</span></span> <span data-ttu-id="2b8e8-274">Isto sugere aos servidores receptores de email que não há chaves públicas válidas para o domínio, e que qualquer email que declara ser desse domínio deve ser rejeitada.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-274">This advises receiving email servers that there are no valid public keys for the domain, and any email claiming to be from that domain should be rejected.</span></span> <span data-ttu-id="2b8e8-275">Você deve fazer isto para cada domínio e subdomínio usando um DKIM curinga.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-275">You should do this for each domain and subdomain using a wildcard DKIM.</span></span>

<span data-ttu-id="2b8e8-276">Por exemplo, o registro DKIM ficaria assim:</span><span class="sxs-lookup"><span data-stu-id="2b8e8-276">For example, the DKIM record would look like this:</span></span>

```console
*._domainkey.SubDomainThatShouldntSendMail.contoso.com. TXT "v=DKIM1; p="
```

## <a name="next-steps-after-you-set-up-dkim-for-microsoft-365"></a><span data-ttu-id="2b8e8-277">Próximas etapas: depois de configurar o DKIM no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2b8e8-277">Next steps: After you set up DKIM for Microsoft 365</span></span>
<span data-ttu-id="2b8e8-278"><a name="DKIMNextSteps"> </a></span><span class="sxs-lookup"><span data-stu-id="2b8e8-278"><a name="DKIMNextSteps"> </a></span></span>

<span data-ttu-id="2b8e8-279">Embora o DKIM tenha sido projetado para ajudar a evitar a falsificação, ele funciona melhor com SPF e DMARC.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-279">Although DKIM is designed to help prevent spoofing, DKIM works better with SPF and DMARC.</span></span> <span data-ttu-id="2b8e8-280">Depois que você configurar o DKIM, se já não tiver configurado o SPF, deve fazê-lo.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-280">Once you have set up DKIM, if you have not already set up SPF you should do so.</span></span> <span data-ttu-id="2b8e8-281">Para obter uma introdução rápida à SPF e para configurá-la rapidamente, confira [Configurar a SPF no Microsoft 365 para ajudar a evitar falsificação](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span><span class="sxs-lookup"><span data-stu-id="2b8e8-281">For a quick introduction to SPF and to get it configured quickly, see [Set up SPF in Microsoft 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span> <span data-ttu-id="2b8e8-282">Para compreender melhor como o Microsoft 365 usa a SPF, para solucionar problemas ou para implantações fora do padrão, como as implantações híbridas, comece com [Como o Microsoft 365 usa a estrutura de política do remetente (SPF) para evitar a falsificação](how-office-365-uses-spf-to-prevent-spoofing.md).</span><span class="sxs-lookup"><span data-stu-id="2b8e8-282">For a more in-depth understanding of how Microsoft 365 uses SPF, or for troubleshooting or non-standard deployments such as hybrid deployments, start with [How Microsoft 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span> <span data-ttu-id="2b8e8-283">A seguir, confira [Usar DMARC para validar emails](use-dmarc-to-validate-email.md).</span><span class="sxs-lookup"><span data-stu-id="2b8e8-283">Next, see [Use DMARC to validate email](use-dmarc-to-validate-email.md).</span></span> <span data-ttu-id="2b8e8-284">[Cabeçalhos de mensagem antispam](anti-spam-message-headers.md) inclui a sintaxe e os campos de cabeçalho usados pelo Microsoft 365 para verificações de DKIM.</span><span class="sxs-lookup"><span data-stu-id="2b8e8-284">[Anti-spam message headers](anti-spam-message-headers.md) includes the syntax and header fields used by Microsoft 365 for DKIM checks.</span></span>

## <a name="more-information"></a><span data-ttu-id="2b8e8-285">Mais informações</span><span class="sxs-lookup"><span data-stu-id="2b8e8-285">More information</span></span>

<span data-ttu-id="2b8e8-286">Rotação de teclas via Windows PowerShell [Girar DkimSigningConfig](https://docs.microsoft.com/powershell/module/exchange/rotate-dkimsigningconfig)</span><span class="sxs-lookup"><span data-stu-id="2b8e8-286">Key rotation via PowerShell [Rotate-DkimSigningConfig](https://docs.microsoft.com/powershell/module/exchange/rotate-dkimsigningconfig)</span></span>
