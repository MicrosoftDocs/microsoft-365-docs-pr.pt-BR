---
title: Use o DKIM para emails em seu domínio personalizado no Office 365
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 09/27/2019, 10/8/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 56fee1c7-dc37-470e-9b09-33fff6d94617
ms.collection:
- M365-security-compliance
description: 'Resumo: este artigo descreve como usar o DomainKeys Identified Mail (DKIM) com o Office 365 para garantir que os sistemas de email de destino confiem em mensagens enviadas de seu domínio personalizado.'
ms.openlocfilehash: bebbc355e6d16d5571733295ce0e48b91332f863
ms.sourcegitcommit: 0d423b50d2f1f4eccd64e35e00f67313244efba9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2019
ms.locfileid: "37424227"
---
# <a name="use-dkim-to-validate-outbound-email-sent-from-your-custom-domain-in-office-365"></a><span data-ttu-id="1fcfb-103">Use o DKIM para validar emails enviados de seu domínio personalizado no Office 365</span><span class="sxs-lookup"><span data-stu-id="1fcfb-103">Use DKIM to validate outbound email sent from your custom domain in Office 365</span></span>

 <span data-ttu-id="1fcfb-104">**Resumo:** Este artigo descreve como você usa o DomainKeys Identified Mail (DKIM) com o Office 365 para garantir que os sistemas de email de destino confiem em mensagens enviadas de saída de seu domínio personalizado.</span><span class="sxs-lookup"><span data-stu-id="1fcfb-104">**Summary:** This article describes how you use DomainKeys Identified Mail (DKIM) with Office 365 to ensure that destination email systems trust messages sent from your custom domain.</span></span>
  
<span data-ttu-id="1fcfb-105">Você deve usar o DKIM, além do SPF e do DMARC, para ajudar a evitar que spoofers enviem mensagens que pareçam que são provenientes de seu domínio.</span><span class="sxs-lookup"><span data-stu-id="1fcfb-105">You should use DKIM in addition to SPF and DMARC to help prevent spoofers from sending messages that look like they are coming from your domain.</span></span> <span data-ttu-id="1fcfb-106">O DKIM possibilita adicionar uma assinatura digital no cabeçalho de mensagens de email enviadas.</span><span class="sxs-lookup"><span data-stu-id="1fcfb-106">DKIM lets you add a digital signature to email messages in the message header.</span></span> <span data-ttu-id="1fcfb-107">Parece complicado, mas não é.</span><span class="sxs-lookup"><span data-stu-id="1fcfb-107">It may sound complicated, but it's really not.</span></span> <span data-ttu-id="1fcfb-108">Quando você configura o DKIM, autoriza seu domínio a associar, ou fazer login, seu nome a uma mensagem de email usando a autenticação de criptografia.</span><span class="sxs-lookup"><span data-stu-id="1fcfb-108">When you configure DKIM, you authorize your domain to associate, or sign, its name to an email message by using cryptographic authentication.</span></span> <span data-ttu-id="1fcfb-109">Sistemas de email que recebem emails de seu domínio podem usar essa assinatura digital para ajudar a determinar se os emails recebidos são legítimos.</span><span class="sxs-lookup"><span data-stu-id="1fcfb-109">Email systems that receive email from your domain can use this digital signature to help determine if incoming email that they receive is legitimate.</span></span>
  
<span data-ttu-id="1fcfb-110">Basicamente, você usa uma chave privada para criptografar o cabeçalho no email de saída do seu domínio.</span><span class="sxs-lookup"><span data-stu-id="1fcfb-110">Basically, you use a private key to encrypt the header in your domain's outgoing email.</span></span> <span data-ttu-id="1fcfb-111">Publique uma chave pública nos registros DNS do seu domínio que os servidores de recebimento possam então usar para decodificar a assinatura.</span><span class="sxs-lookup"><span data-stu-id="1fcfb-111">You publish a public key to your domain's DNS records that receiving servers can then use to decode the signature.</span></span> <span data-ttu-id="1fcfb-112">Eles usam a chave pública para confirmar que as mensagens realmente vêm de você e não de alguém que está *falsificando* seu domínio.</span><span class="sxs-lookup"><span data-stu-id="1fcfb-112">They use the public key to verify that the messages are really coming from you and not coming from someone spoofing your domain.</span></span>
  
<span data-ttu-id="1fcfb-113">O Office 365 configura automaticamente o DKIM para domínios iniciais de “onmicrosoft.com”.</span><span class="sxs-lookup"><span data-stu-id="1fcfb-113">Office 365 automatically sets up DKIM for initial domains.</span></span> <span data-ttu-id="1fcfb-114">Isso significa que não é preciso fazer nada para configurar o DKIM para qualquer nome de domínio inicial (ex.</span><span class="sxs-lookup"><span data-stu-id="1fcfb-114">That means you don't need to do anything to set up DKIM for any initial domain names (ex.</span></span> <span data-ttu-id="1fcfb-115">litware.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="1fcfb-115">litware.onmicrosoft.com).</span></span> <span data-ttu-id="1fcfb-116">Para saber mais sobre domínios, confira [Perguntas frequentes sobre domínios](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a#bkmk_whydoihaveanonmicrosoft.comdomain).</span><span class="sxs-lookup"><span data-stu-id="1fcfb-116">For more information about domains, see [Domains FAQ](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a#bkmk_whydoihaveanonmicrosoft.comdomain).</span></span>

<span data-ttu-id="1fcfb-117">Você também pode optar por não fazer nada sobre o DKIM em relação ao seu domínio personalizado.</span><span class="sxs-lookup"><span data-stu-id="1fcfb-117">You can choose to do nothing about DKIM for your custom domain too.</span></span> <span data-ttu-id="1fcfb-118">Se você não configurar o DKIM para o seu domínio personalizado, o Office 365 criará um par de chaves privada e pública, habilitará a assinatura do DKIM e configurará a política padrão do Office 365 para o seu domínio personalizado.</span><span class="sxs-lookup"><span data-stu-id="1fcfb-118">If you do not set up DKIM for your custom domain, Office 365 creates a private and public key pair, enables DKIM signing, and then configures the Office 365 default policy for your custom domain.</span></span> <span data-ttu-id="1fcfb-119">Embora isso seja abrangente o suficiente para a maioria dos clientes do Office 365, você deve configurar manualmente o DKIM para o seu domínio personalizado nas seguintes circunstâncias:</span><span class="sxs-lookup"><span data-stu-id="1fcfb-119">While this is sufficient coverage for most Office 365 customers, you should manually configure DKIM for your custom domain in the following circumstances:</span></span>
  
- <span data-ttu-id="1fcfb-120">Você tem mais de um domínio personalizado no Office 365</span><span class="sxs-lookup"><span data-stu-id="1fcfb-120">You have more than one custom domain in Office 365</span></span>

- <span data-ttu-id="1fcfb-121">For configurar o DMARC também (recomendado)</span><span class="sxs-lookup"><span data-stu-id="1fcfb-121">You're going to set up DMARC too (recommended)</span></span>

- <span data-ttu-id="1fcfb-122">Quiser ter controle sobre sua chave privada</span><span class="sxs-lookup"><span data-stu-id="1fcfb-122">You want control over your private key</span></span>

- <span data-ttu-id="1fcfb-123">Quiser personalizar seus registros CNAME</span><span class="sxs-lookup"><span data-stu-id="1fcfb-123">You want to customize your CNAME records</span></span>

- <span data-ttu-id="1fcfb-124">Configure as chaves do DKIM para emails provenientes de um domínio de terceiros, por exemplo, se você usar um programa de email em massa terceirizado.</span><span class="sxs-lookup"><span data-stu-id="1fcfb-124">You want to set up DKIM keys for email originating out of a third-party domain, for example, if you use a third-party bulk mailer.</span></span>

<span data-ttu-id="1fcfb-125">Neste artigo:</span><span class="sxs-lookup"><span data-stu-id="1fcfb-125">In this article:</span></span>
  
- [<span data-ttu-id="1fcfb-126">Como o DKIM funciona melhor do que a SPF para evitar a falsificação maliciosa no Office 365</span><span class="sxs-lookup"><span data-stu-id="1fcfb-126">How DKIM works better than SPF alone to prevent malicious spoofing in Office 365</span></span>](use-dkim-to-validate-outbound-email.md#HowDKIMWorks)

- [<span data-ttu-id="1fcfb-127">Atualize manualmente as chaves de 1024 bits para chaves de criptografia DKIM de 2048 bits</span><span class="sxs-lookup"><span data-stu-id="1fcfb-127">Manually upgrade your 1024-bit keys to 2048-bit DKIM encryption keys</span></span>](use-dkim-to-validate-outbound-email.md#1024to2048DKIM)

- [<span data-ttu-id="1fcfb-128">O que você precisa fazer para configurar manualmente o DKIM no Office 365</span><span class="sxs-lookup"><span data-stu-id="1fcfb-128">What you need to do to manually set up DKIM in Office 365</span></span>](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365)

- [<span data-ttu-id="1fcfb-129">Para configurar o DKIM para mais de um domínio personalizado no Office 365</span><span class="sxs-lookup"><span data-stu-id="1fcfb-129">To configure DKIM for more than one custom domain in Office 365</span></span>](use-dkim-to-validate-outbound-email.md#DKIMMultiDomain)

- [<span data-ttu-id="1fcfb-130">Desabilitar a política de assinatura do DKIM para um domínio personalizado no Office 365</span><span class="sxs-lookup"><span data-stu-id="1fcfb-130">Disabling the DKIM signing policy for a custom domain in Office 365</span></span>](use-dkim-to-validate-outbound-email.md#DisableDKIMSigningPolicy)

- [<span data-ttu-id="1fcfb-131">Comportamento padrão para o DKIM e o Office 365</span><span class="sxs-lookup"><span data-stu-id="1fcfb-131">Default behavior for DKIM and Office 365</span></span>](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior)

- [<span data-ttu-id="1fcfb-132">Configurar o DKIM de forma que um serviço terceirizado possa enviar, ou fazer spoof de, emails em nome de seu domínio personalizado</span><span class="sxs-lookup"><span data-stu-id="1fcfb-132">Set up DKIM so that a third-party service can send, or spoof, email on behalf of your custom domain</span></span>](use-dkim-to-validate-outbound-email.md#SetUp3rdPartyspoof)

- [<span data-ttu-id="1fcfb-133">Próximas etapas: depois de configurar o DKIM para o Office 365</span><span class="sxs-lookup"><span data-stu-id="1fcfb-133">Next steps: After you set up DKIM for Office 365</span></span>](use-dkim-to-validate-outbound-email.md#DKIMNextSteps)

> [!NOTE]
> <span data-ttu-id="1fcfb-134">O Microsoft 365 oferece suporte ao usuário de DKIM de 1024 ou 2048 bits.</span><span class="sxs-lookup"><span data-stu-id="1fcfb-134">Microsoft 365 supports the user of either 1024- or 2048-bit DKIM.</span></span> <span data-ttu-id="1fcfb-135">Se você estiver usando o DKIM de 1024 bits e desejar configurar para o de 2048 bits, siga as etapas deste artigo para alternar sua configuração de assinatura DKIM.</span><span class="sxs-lookup"><span data-stu-id="1fcfb-135">If you're using 1024- and want to configure 2048-bit DKIM stay tuned for steps to rotate your DKIM signing configuration in this article.</span></span> <span data-ttu-id="1fcfb-136">Até o final de 2019, a Microsoft terá suporte para chaves de 2048 bits por padrão, para todos os clientes.</span><span class="sxs-lookup"><span data-stu-id="1fcfb-136">By the end of 2019, Microsoft will support 2048-bit keys by default, for all customers.</span></span> 

## <a name="how-dkim-works-better-than-spf-alone-to-prevent-malicious-spoofing-in-office-365"></a><span data-ttu-id="1fcfb-137">Como o DKIM funciona melhor do que o SPF para evitar a falsificação maliciosa no Office 365</span><span class="sxs-lookup"><span data-stu-id="1fcfb-137">How DKIM works better than SPF alone to prevent malicious spoofing in Office 365</span></span>
<span data-ttu-id="1fcfb-138"><a name="HowDKIMWorks"> </a></span><span class="sxs-lookup"><span data-stu-id="1fcfb-138"></span></span>

<span data-ttu-id="1fcfb-p106">A SPF adiciona informações a um envelope de mensagem, mas o DKIM realmente criptografa uma assinatura dentro do cabeçalho da mensagem. Ao encaminhar uma mensagem, partes de seu envelope podem ser removidas pelo servidor de encaminhamento. Como a assinatura digital permanece com a mensagem de email porque faz parte do cabeçalho do email, o DKIM funciona mesmo quando uma mensagem é encaminhada conforme mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="1fcfb-p106">SPF adds information to a message envelope but DKIM actually encrypts a signature within the message header. When you forward a message, portions of that message's envelope can be stripped away by the forwarding server. Since the digital signature stays with the email message because it's part of the email header, DKIM works even when a message has been forwarded as shown in the following example.</span></span>
  
![Diagrama que mostra uma mensagem encaminhada passando pela autenticação DKIM onde a verificação de SPF falha](../media/28f93b4c-97e7-4309-acc4-fd0d2e0e3377.jpg)
  
<span data-ttu-id="1fcfb-p107">Neste exemplo, se você tivesse apenas publicado um registro TXT SPF do seu domínio, o servidor de email do destinatário poderia ter marcado seu email como spam e gerado um resultado positivo falso. A adição do DKIM neste cenário reduz o resultado positivo falso de spam. Como o DKIM depende de criptografia de chave pública para autenticar, e não apenas de endereços IP, é considerado uma forma muito mais forte de autenticação que o SPF. Recomendamos usar o SPF e o DKIM, bem como o DMARC, em sua implantação.</span><span class="sxs-lookup"><span data-stu-id="1fcfb-p107">In this example, if you had only published an SPF TXT record for your domain, the recipient's mail server could have marked your email as spam and generated a false positive result. The addition of DKIM in this scenario reduces false positive spam reporting. Because DKIM relies on public key cryptography to authenticate and not just IP addresses, DKIM is considered a much stronger form of authentication than SPF. We recommend using both SPF and DKIM, as well as DMARC in your deployment.</span></span>
  
<span data-ttu-id="1fcfb-p108">Detalhes fundamentais: o DKIM usa uma chave privada para inserir uma assinatura criptografada nos cabeçalhos das mensagens. A domínio que assina, ou domínio de saída, é inserido como o valor do campo **d=** no cabeçalho. O domínio que verifica, ou domínio do destinatário, usa esse campo **d=** para procurar a chave pública no DNS e autenticar a mensagem. Se a mensagem for verificada, passa na verificação do DKIM.</span><span class="sxs-lookup"><span data-stu-id="1fcfb-p108">The nitty gritty: DKIM uses a private key to insert an encrypted signature into the message headers. The signing domain, or outbound domain, is inserted as the value of the **d=** field in the header. The verifying domain, or recipient's domain, then use the **d=** field to look up the public key from DNS and authenticate the message. If the message is verified, the DKIM check passes.</span></span> 

## <a name="manually-upgrade-your-1024-bit-keys-to-2048-bit-dkim-encryption-keys"></a><span data-ttu-id="1fcfb-151">Atualize manualmente as chaves de 1024 bits para chaves de criptografia DKIM de 2048 bits</span><span class="sxs-lookup"><span data-stu-id="1fcfb-151">Manually upgrade your 1024-bit keys to 2048-bit DKIM encryption keys</span></span>
<span data-ttu-id="1fcfb-152"><a name="1024to2048DKIM"> </a></span><span class="sxs-lookup"><span data-stu-id="1fcfb-152"></span></span>

<span data-ttu-id="1fcfb-153">Já que tanto o número de bits 1024 e o 2048 têm suporte para chaves DKIM, essas instruções mostrarão como atualizar a chave de 1024 para 2048 bits.</span><span class="sxs-lookup"><span data-stu-id="1fcfb-153">Since both 1024 and 2048 bitness are supported for DKIM keys, these directions will tell you how to upgrade your 1024-bit key to 2048.</span></span> <span data-ttu-id="1fcfb-154">As etapas a seguir são para dois casos de uso, escolha o que melhor se adapta à sua configuração.</span><span class="sxs-lookup"><span data-stu-id="1fcfb-154">The steps below are for two use-cases, please choose the one that best fits your configuration.</span></span>

1. <span data-ttu-id="1fcfb-155">Quando você **já tiver o DKIM configurado**, alterne o número de bits da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="1fcfb-155">When you **already have DKIM configured**, you rotate bitness as follows:</span></span>
    1. <span data-ttu-id="1fcfb-156">[Conecte-se às cargas de trabalho do Office 365 pelo PowerShell ](https://docs.microsoft.com/pt-BR/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="1fcfb-156">[Connect to Office 365 PowerShell](https://docs.microsoft.com/pt-BR/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)</span></span> <span data-ttu-id="1fcfb-157">(O cmdlet é proveniente do Exchange Online.)</span><span class="sxs-lookup"><span data-stu-id="1fcfb-157">(The cmdlet comes from Exchange Online.)</span></span>
    1. <span data-ttu-id="1fcfb-158">E, em seguida, execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="1fcfb-158">And then execute the following cmdlet:</span></span>

<span data-ttu-id="1fcfb-159">&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`Rotate-DkimSigningConfig -KeySize 2048 -Identity {Guid of the existing Signing Config}`</span><span class="sxs-lookup"><span data-stu-id="1fcfb-159"></span></span>

1. <span data-ttu-id="1fcfb-160">Ou para uma **nova implementação do DKIM**:</span><span class="sxs-lookup"><span data-stu-id="1fcfb-160">Or for a **new implementation of DKIM**:</span></span>
    1. <span data-ttu-id="1fcfb-161">[Conecte-se às cargas de trabalho do Office 365 pelo PowerShell ](https://docs.microsoft.com/pt-BR/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="1fcfb-161">[Connect to Office 365 PowerShell](https://docs.microsoft.com/pt-BR/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)</span></span> <span data-ttu-id="1fcfb-162">(Este é um cmdlet do Exchange Online.)</span><span class="sxs-lookup"><span data-stu-id="1fcfb-162">(This is an Exchange Online cmdlet.)</span></span>
    1. <span data-ttu-id="1fcfb-163">Execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="1fcfb-163">Run the following cmdlet:</span></span>

<span data-ttu-id="1fcfb-164">&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; `New-DkimSigningConfig -DomainName {Domain for which config is to be created} -KeySize 2048 -Enabled $True`</span><span class="sxs-lookup"><span data-stu-id="1fcfb-164"></span></span>

<span data-ttu-id="1fcfb-165">Mantenha-se conectado ao Office 365 para *verificar* a configuração.</span><span class="sxs-lookup"><span data-stu-id="1fcfb-165">Stay connected to Office 365 to *verify* the configuration.</span></span>

2. <span data-ttu-id="1fcfb-166">Execute o cmdlet:</span><span class="sxs-lookup"><span data-stu-id="1fcfb-166">Execute the cmdlet:</span></span>

<span data-ttu-id="1fcfb-167">&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; `Get-DkimSigningConfig | fl`</span><span class="sxs-lookup"><span data-stu-id="1fcfb-167"></span></span>

> [!TIP]
><span data-ttu-id="1fcfb-168">Essa nova chave de 2048 bits entra em vigor no RotateOnDate e enviará emails com a chave 1024 bits provisoriamente.</span><span class="sxs-lookup"><span data-stu-id="1fcfb-168">This new 2048-bit key takes effect on the RotateOnDate, and will send emails with the 1024-bit key in the interim.</span></span> <span data-ttu-id="1fcfb-169">Após quatro dias, você poderá testar novamente com a chave de 2048 bits (ou seja, quando a rotação entrar em vigor no segundo seletor).</span><span class="sxs-lookup"><span data-stu-id="1fcfb-169">After four days, you can test again with the 2048-bit key (that is, once the rotation takes effect to the second selector).</span></span> 

<span data-ttu-id="1fcfb-170">Se você deseja alternar para o segundo seletor, suas opções são: a) permitir que o serviço do Office 365 alterne o seletor e atualize para o número de bits 2048 nos próximos 6 meses, ou b) após 4 dias confirmando que número de bits 2048 está em uso, manualmente alterne a segunda chave de seletor usando o cmdlet apropriado listado acima.</span><span class="sxs-lookup"><span data-stu-id="1fcfb-170">If you want to rotate to the second selector, your options are a) let the Office 365 service rotate the selector and upgrade to 2048-bitness within the next 6 months, or b) after 4 days and confirming that 2048-bitness is in use, manually rotate the second selector key by using the appropriate cmdlet listed above.</span></span>

## <a name="steps-you-need-to-do-to-manually-set-up-dkim-in-office-365"></a><span data-ttu-id="1fcfb-171">O que você precisa fazer para configurar manualmente o DKIM no Office 365</span><span class="sxs-lookup"><span data-stu-id="1fcfb-171">What you need to do to manually set up DKIM in Office 365</span></span>
<span data-ttu-id="1fcfb-172"><a name="SetUpDKIMO365"> </a></span><span class="sxs-lookup"><span data-stu-id="1fcfb-172"></span></span>

<span data-ttu-id="1fcfb-173">Para configurar o DKIM, execute estas etapas:</span><span class="sxs-lookup"><span data-stu-id="1fcfb-173">To configure DKIM, you will complete these steps:</span></span>
  
- [<span data-ttu-id="1fcfb-174">Publicar dois registros CNAME para o seu domínio personalizado no DNS</span><span class="sxs-lookup"><span data-stu-id="1fcfb-174">Publish two CNAME records for your custom domain in DNS</span></span>](use-dkim-to-validate-outbound-email.md#Publish2CNAME)

- [<span data-ttu-id="1fcfb-175">Habilitar a assinatura DKIM para o seu domínio personalizado no Office 365</span><span class="sxs-lookup"><span data-stu-id="1fcfb-175">Enable DKIM signing for your custom domain in Office 365</span></span>](use-dkim-to-validate-outbound-email.md#EnableDKIMinO365)

### <a name="publish-two-cname-records-for-your-custom-domain-in-dns"></a><span data-ttu-id="1fcfb-176">Publicar dois registros CNAME para o seu domínio personalizado no DNS</span><span class="sxs-lookup"><span data-stu-id="1fcfb-176">Publish two CNAME records for your custom domain in DNS</span></span>
<span data-ttu-id="1fcfb-177"><a name="Publish2CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="1fcfb-177"></span></span>

<span data-ttu-id="1fcfb-178">Para cada domínio para o qual você deseja adicionar uma assinatura de DKIM no DNS, é preciso publicar dois registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="1fcfb-178">For each domain for which you want to add a DKIM signature in DNS, you need to publish two CNAME records.</span></span> 

<span data-ttu-id="1fcfb-179">Execute os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="1fcfb-179">Run the following commands:</span></span>

```powershell
    New-DkimSigningConfig -DomainName <domain> -Enabled $false   
    Get-DkimSigningConfig -Identity <domain> | fl Selector1CNAME, Selector2CNAME
```

<span data-ttu-id="1fcfb-180">Crie CNAMEs referenciados na saída Get-DkimSigningConfig</span><span class="sxs-lookup"><span data-stu-id="1fcfb-180">Create CNAMEs referenced in Get-DkimSigningConfig output</span></span>

```powershell
    Set-DkimSigningConfig -Identity <domain> -Enabled $true
```
<span data-ttu-id="1fcfb-181">Os registros CNAME em seu DNS indicarão que já criaram registros A que existem no DNS nos servidores DNS da Microsoft para o Office 365.</span><span class="sxs-lookup"><span data-stu-id="1fcfb-181">The CNAME records in your DNS will point to already created A records that exist in DNS on the Microsoft DNS servers for Office 365.</span></span>
  
<span data-ttu-id="1fcfb-p113">O Office 365 executa a rotação de chaves automática usando os dois registros estabelecidos. Se você provisionou domínios personalizados em adição ao domínio inicial no Office 365, deve publicar dois registros CNAME para cada domínio adicional. Portanto, se você tem dois domínios, deve publicar dois registros CNAME adicionais e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="1fcfb-p113">Office 365 performs automatic key rotation using the two records that you establish. If you have provisioned custom domains in addition to the initial domain in Office 365, you must publish two CNAME records for each additional domain. So, if you have two domains, you must publish two additional CNAME records, and so on.</span></span>
  
<span data-ttu-id="1fcfb-185">Use o seguinte formato para os registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="1fcfb-185">Use the following format for the CNAME records:</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1fcfb-186">Se você for um dos nossos clientes GCC High, nós calculamos o _domainGuid_ de maneira diferente!</span><span class="sxs-lookup"><span data-stu-id="1fcfb-186">If you are one of our GCC High customers, we calculate _domainGuid_ differently!</span></span> <span data-ttu-id="1fcfb-187">Em vez de procurar o registro MX do seu _initialDomain_ para calcular o _domainGuid_, ele é calculado diretamente a partir do domínio personalizado.</span><span class="sxs-lookup"><span data-stu-id="1fcfb-187">Instead of looking up the MX record for your _initialDomain_ to calculate _domainGuid_, instead we calculate it directly from the customized domain.</span></span> <span data-ttu-id="1fcfb-188">Por exemplo, se seu domínio personalizado for "contoso.com", o domainGuid vai se tornar "contoso-com", os pontos serão substituídos por um traço.</span><span class="sxs-lookup"><span data-stu-id="1fcfb-188">For example, if your customized domain is "contoso.com" your domainGuid becomes "contoso-com", any periods are replaced with a dash.</span></span> <span data-ttu-id="1fcfb-189">Portanto, independentemente de qual registro MX seu initialDomain apontar, você sempre usará o método acima para calcular o domainGuid para usar em seus registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="1fcfb-189">So, regardless of what MX record your initialDomain points to, you’ll always use the above method to calculate the domainGuid to use in your CNAME records.</span></span>

```text
Host name:          selector1._domainkey
Points to address or value: selector1-<domainGUID>._domainkey.<initialDomain> 
TTL:                3600

Host name:          selector2._domainkey
Points to address or value: selector2-<domainGUID>._domainkey.<initialDomain> 
TTL:                3600
```

<span data-ttu-id="1fcfb-190">Onde:</span><span class="sxs-lookup"><span data-stu-id="1fcfb-190">Where:</span></span>
  
- <span data-ttu-id="1fcfb-191">Para o Office 365, os seletores sempre serão "seletor1" ou "seletor2".</span><span class="sxs-lookup"><span data-stu-id="1fcfb-191">For Office 365, the selectors will always be "selector1" or "selector2".</span></span>

- <span data-ttu-id="1fcfb-192">O _domainGUID_ é igual ao _domainGUID_ no registro MX personalizado para o seu domínio personalizado, que aparece antes de mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="1fcfb-192">_domainGUID_ is the same as the  _domainGUID_ in the customized MX record for your custom domain that appears before mail.protection.outlook.com.</span></span> <span data-ttu-id="1fcfb-193">Por exemplo, no seguinte registro MX para o domínio contoso.com, o _domainGUID_ é contoso-com:</span><span class="sxs-lookup"><span data-stu-id="1fcfb-193">For example, in the following MX record for the domain contoso.com, the  _domainGUID_ is contoso-com:</span></span> 
    
    ```text
    contoso.com.  3600  IN  MX   5 contoso-com.mail.protection.outlook.com
    ```

- <span data-ttu-id="1fcfb-194">O _initialDomain_ é o domínio que você usou quando se inscreveu no Office 365.</span><span class="sxs-lookup"><span data-stu-id="1fcfb-194">_initialDomain_ is the domain that you used when you signed up for Office 365.</span></span> <span data-ttu-id="1fcfb-195">Os domínios iniciais sempre terminam em onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="1fcfb-195">Initial domains always end in onmicrosoft.com.</span></span> <span data-ttu-id="1fcfb-196">Para saber mais sobre como determinar seu domínio inicial, confira [Perguntas frequentes sobre domínios](https://support.office.com/article/1272bad0-4bd4-4796-8005-67d6fb3afc5a#bkmk_whydoihaveanonmicrosoft.comdomain).</span><span class="sxs-lookup"><span data-stu-id="1fcfb-196">For information about determining your initial domain, see [Domains FAQ](https://support.office.com/article/1272bad0-4bd4-4796-8005-67d6fb3afc5a#bkmk_whydoihaveanonmicrosoft.comdomain).</span></span>

<span data-ttu-id="1fcfb-197">Por exemplo, se você tiver o domínio inicial cohovineyardandwinery.onmicrosoft.com e dois domínios personalizados, cohovineyard.com e cohowinery.com, precisará configurar dois registros CNAME para cada domínio adicional, totalizando quatro registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="1fcfb-197">For example, if you have an initial domain of cohovineyardandwinery.onmicrosoft.com, and two custom domains cohovineyard.com and cohowinery.com, you would need to set up two CNAME records for each additional domain, for a total of four CNAME records.</span></span>
  
```text
Host name:          selector1._domainkey
Points to address or value: selector1-cohovineyard-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:          selector2._domainkey
Points to address or value: selector2-cohovineyard-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:          selector1._domainkey
Points to address or value: selector1-cohowinery-com._domainkey.cohovineyardandwinery.onmicrosoft.com 
TTL:                3600

Host name:          selector2._domainkey
Points to address or value: selector2-cohowinery-com._domainkey.cohovineyardandwinery.onmicrosoft.com 
TTL:                3600
```

### <a name="enable-dkim-signing-for-your-custom-domain-in-office-365"></a><span data-ttu-id="1fcfb-198">Habilitar a assinatura DKIM para o seu domínio personalizado no Office 365</span><span class="sxs-lookup"><span data-stu-id="1fcfb-198">Enable DKIM signing for your custom domain in Office 365</span></span>
<span data-ttu-id="1fcfb-199"><a name="EnableDKIMinO365"> </a></span><span class="sxs-lookup"><span data-stu-id="1fcfb-199"></span></span>

<span data-ttu-id="1fcfb-200">Depois de publicar os registros CNAME no DNS, você está pronto para habilitar a assinatura de DKIM através do Office 365.</span><span class="sxs-lookup"><span data-stu-id="1fcfb-200">Once you have published the CNAME records in DNS, you are ready to enable DKIM signing through Office 365.</span></span> <span data-ttu-id="1fcfb-201">É possível fazer isso por meio do centro de administração do Microsoft 365 ou usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1fcfb-201">You can do this either through the Office 365 admin center or by using PowerShell.</span></span>
  
#### <a name="to-enable-dkim-signing-for-your-custom-domain-through-the-admin-center"></a><span data-ttu-id="1fcfb-202">Para habilitar a assinatura DKIM para o seu domínio personalizado por meio do centro de administração</span><span class="sxs-lookup"><span data-stu-id="1fcfb-202">To enable DKIM signing for your custom domain through the Office 365 admin center</span></span>

1. <span data-ttu-id="1fcfb-203">[Entrar no Office 365](https://support.office.microsoft.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4) com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="1fcfb-203">[Sign in to Office 365](https://support.office.microsoft.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4) with your work or school account.</span></span> 

2. <span data-ttu-id="1fcfb-204">Selecione o ícone do inicializador de aplicativos no canto superior esquerdo e escolha **Administrador**.</span><span class="sxs-lookup"><span data-stu-id="1fcfb-204">Select the app launcher icon in the upper-left and choose **Admin**.</span></span>

3. <span data-ttu-id="1fcfb-205">No painel de navegação inferior à esquerda, expanda **Administrador** e escolha **Exchange**.</span><span class="sxs-lookup"><span data-stu-id="1fcfb-205">In the lower-left navigation, expand **Admin** and choose **Exchange**.</span></span>

4. <span data-ttu-id="1fcfb-206">Vá para **Proteção** \> **DKIM**.</span><span class="sxs-lookup"><span data-stu-id="1fcfb-206">Go to **Protection** \> **dkim**.</span></span>

5. <span data-ttu-id="1fcfb-p118">Selecione o domínio para o qual você deseja habilitar o DKIM e, para **Assinar mensagens deste domínio com assinaturas DKIM**, escolha **Habilitar**. Repita essa etapa para cada domínio personalizado.</span><span class="sxs-lookup"><span data-stu-id="1fcfb-p118">Select the domain for which you want to enable DKIM and then, for **Sign messages for this domain with DKIM signatures**, choose **Enable**. Repeat this step for each custom domain.</span></span>

#### <a name="to-enable-dkim-signing-for-your-custom-domain-by-using-powershell"></a><span data-ttu-id="1fcfb-209">Para habilitar a assinatura DKIM para o seu domínio personalizado usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="1fcfb-209">To enable DKIM signing for your custom domain by using PowerShell</span></span>

1. <span data-ttu-id="1fcfb-210">[Conectar-se ao Exchange Online PowerShell](https://technet.microsoft.com/library/jj984289.aspx).</span><span class="sxs-lookup"><span data-stu-id="1fcfb-210">[Connect to Exchange Online PowerShell](https://technet.microsoft.com/library/jj984289.aspx).</span></span>

2. <span data-ttu-id="1fcfb-211">Execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="1fcfb-211">Run the following command:</span></span>

    ```powershell
    Set-DkimSigningConfig -Identity <domain> -Enabled $true
    ```

   <span data-ttu-id="1fcfb-212">Em que _domínio_ é o nome do domínio personalizado para o qual você deseja habilitar a assinatura DKIM.</span><span class="sxs-lookup"><span data-stu-id="1fcfb-212">Where _domain_ is the name of the custom domain for which you want to enable DKIM signing.</span></span> 

   <span data-ttu-id="1fcfb-213">Por exemplo, para o domínio contoso.com:</span><span class="sxs-lookup"><span data-stu-id="1fcfb-213">For example, for the domain contoso.com:</span></span>
   
   ```powershell
    Set-DkimSigningConfig -Identity contoso.com -Enabled $true
    ```

#### <a name="to-confirm-dkim-signing-is-configured-properly-for-office-365"></a><span data-ttu-id="1fcfb-214">Para confirmar que a assinatura de DKIM está configurada adequadamente para o Office 365</span><span class="sxs-lookup"><span data-stu-id="1fcfb-214">To Confirm DKIM signing is configured properly for Office 365</span></span>

<span data-ttu-id="1fcfb-p119">Aguarde alguns minutos antes de prosseguir com essas etapas para confirmar que você configurou o DKIM corretamente. Isso permite que as informações do DKIM sobre o domínio sejam distribuídas por toda a rede.</span><span class="sxs-lookup"><span data-stu-id="1fcfb-p119">Wait a few minutes before you follow these steps to confirm that you have properly configured DKIM. This allows time for the DKIM information about the domain to be spread throughout the network.</span></span>
  
- <span data-ttu-id="1fcfb-217">Envie uma mensagem de uma conta do seu domínio do Office 365 habilitado com DKIM para outra conta de email, como outlook.com ou Hotmail.com.</span><span class="sxs-lookup"><span data-stu-id="1fcfb-217">Send a message from an account within your Office 365 DKIM-enabled domain to another email account such as outlook.com or Hotmail.com.</span></span>

- <span data-ttu-id="1fcfb-p120">Não use uma conta aol.com para fins de teste. A AOL pode ignorar a verificação de DKIM se a verificação de SPF passar. Isso anula o teste.</span><span class="sxs-lookup"><span data-stu-id="1fcfb-p120">Do not use an aol.com account for testing purposes. AOL may skip the DKIM check if the SPF check passes. This will nullify your test.</span></span>

- <span data-ttu-id="1fcfb-p121">Abra a mensagem e examine o cabeçalho. Instruções para exibir o cabeçalho da mensagem variam dependendo do seu cliente de mensagens. Para instruções sobre como visualizar cabeçalhos de mensagens no Outlook, confira [Visualizar cabeçalhos de mensagens de email](https://support.office.com/article/CD039382-DC6E-4264-AC74-C048563D212C).</span><span class="sxs-lookup"><span data-stu-id="1fcfb-p121">Open the message and look at the header. Instructions for viewing the header for the message will vary depending on your messaging client. For instructions on viewing message headers in Outlook, see [View e-mail message headers](https://support.office.com/article/CD039382-DC6E-4264-AC74-C048563D212C).</span></span>

  <span data-ttu-id="1fcfb-p122">A mensagem assinada com DKIM conterá o nome do host e o domínio definidos quando você publicou as entradas CNAME. A mensagem terá uma aparência similar à do exemplo:</span><span class="sxs-lookup"><span data-stu-id="1fcfb-p122">The DKIM-signed message will contain the host name and domain you defined when you published the CNAME entries. The message will look something like this example:</span></span>
    
    ```text
    From: Example User <example@contoso.com>
    DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed;
        s=selector1; d=contoso.com; t=1429912795;
        h=From:To:Message-ID:Subject:MIME-Version:Content-Type;
        bh=<body hash>;
        b=<signed field>;
    ```

- <span data-ttu-id="1fcfb-p123">Procure pelo cabeçalho Authentication-Results. Embora cada serviço receptor use um formato ligeiramente diferente para carimbar as mensagens recebidas, o resultado deve incluir algo parecido com **DKIM=pass** ou **DKIM=OK**.</span><span class="sxs-lookup"><span data-stu-id="1fcfb-p123">Look for the Authentication-Results header. While each receiving service uses a slightly different format to stamp the incoming mail, the result should include something like **DKIM=pass** or **DKIM=OK**.</span></span>

## <a name="to-configure-dkim-for-more-than-one-custom-domain-in-office-365"></a><span data-ttu-id="1fcfb-228">Para configurar o DKIM para mais de um domínio personalizado no Office 365</span><span class="sxs-lookup"><span data-stu-id="1fcfb-228">To configure DKIM for more than one custom domain in Office 365</span></span>
<span data-ttu-id="1fcfb-229"><a name="DKIMMultiDomain"> </a></span><span class="sxs-lookup"><span data-stu-id="1fcfb-229"></span></span>

<span data-ttu-id="1fcfb-p124">Se em algum momento no futuro você decidir adicionar outro domínio personalizado e quiser habilitar o DKIM para o novo domínio, deve executar as etapas deste artigo para cada domínio. Especificamente, execute todas as etapas em [O que você precisa fazer para configurar manualmente o DKIM no Office 365](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365).</span><span class="sxs-lookup"><span data-stu-id="1fcfb-p124">If at some point in the future you decide to add another custom domain and you want to enable DKIM for the new domain, you must complete the steps in this article for each domain. Specifically, complete all steps in [What you need to do to manually set up DKIM in Office 365](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365).</span></span>
  
## <a name="disabling-the-dkim-signing-policy-for-a-custom-domain-in-office-365"></a><span data-ttu-id="1fcfb-232">Desabilitar a política de assinatura do DKIM para um domínio personalizado no Office 365</span><span class="sxs-lookup"><span data-stu-id="1fcfb-232">Disabling the DKIM signing policy for a custom domain in Office 365</span></span>
<span data-ttu-id="1fcfb-233"><a name="DisableDKIMSigningPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="1fcfb-233"></span></span>

<span data-ttu-id="1fcfb-p125">Desabilitar a política de assinatura não desabilita completamente o DKIM. Após um período de tempo, o Office 365 aplicará automaticamente a política padrão do Office 365 ao seu domínio. Para saber mais, confira [Comportamento padrão para o DKIM e o Office 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior).</span><span class="sxs-lookup"><span data-stu-id="1fcfb-p125">Disabling the signing policy does not completely disable DKIM. After a period of time, Office 365 will automatically apply the default Office 365 policy for your domain. For more information, see [Default behavior for DKIM and Office 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior).</span></span>
  
### <a name="to-disable-the-dkim-signing-policy-by-using-windows-powershell"></a><span data-ttu-id="1fcfb-237">Para desabilitar a política de assinatura do DKIM usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1fcfb-237">To disable the DKIM signing policy by using Windows PowerShell</span></span>

1. <span data-ttu-id="1fcfb-238">[Conectar-se ao Exchange Online PowerShell](https://technet.microsoft.com/library/jj984289.aspx).</span><span class="sxs-lookup"><span data-stu-id="1fcfb-238">[Connect to Exchange Online PowerShell](https://technet.microsoft.com/library/jj984289.aspx).</span></span>

2. <span data-ttu-id="1fcfb-239">Execute um dos seguintes comandos para cada domínio para o qual você deseja desabilitar a assinatura de DKIM.</span><span class="sxs-lookup"><span data-stu-id="1fcfb-239">Run one of the following commands for each domain for which you want to disable DKIM signing.</span></span>
    
    ```powershell
    $p = Get-DkimSigningConfig -Identity <domain>
    $p[0] | Set-DkimSigningConfig -Enabled $false
    ```
   
   <span data-ttu-id="1fcfb-240">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="1fcfb-240">For example:</span></span>
    
    ```powershell
    $p = Get-DkimSigningConfig -Identity contoso.com
    $p[0] | Set-DkimSigningConfig -Enabled $false
    ```

   <span data-ttu-id="1fcfb-241">Ou</span><span class="sxs-lookup"><span data-stu-id="1fcfb-241">Or</span></span>
    
    ```powershell
    Set-DkimSigningConfig -Identity $p[<number>].Identity -Enabled $false
    ```

    <span data-ttu-id="1fcfb-242">Em que o _número_ é o índice da política.</span><span class="sxs-lookup"><span data-stu-id="1fcfb-242">Where  _number_ is the index of the policy.</span></span> <span data-ttu-id="1fcfb-243">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="1fcfb-243">For example:</span></span>
    
    ```powershell
    Set-DkimSigningConfig -Identity $p[0].Identity -Enabled $false
    ```

## <a name="default-behavior-for-dkim-and-office-365"></a><span data-ttu-id="1fcfb-244">Comportamento padrão para o DKIM e o Office 365</span><span class="sxs-lookup"><span data-stu-id="1fcfb-244">Default behavior for DKIM and Office 365</span></span>
<span data-ttu-id="1fcfb-245"><a name="DefaultDKIMbehavior"> </a></span><span class="sxs-lookup"><span data-stu-id="1fcfb-245"></span></span>

<span data-ttu-id="1fcfb-246">Se você não habilitar o DKIM, o Office 365 cria automaticamente uma chave pública de DKIM de 1024 bits para seu domínio padrão e a chave privada associada que é armazenada internamente em nosso datacenter.</span><span class="sxs-lookup"><span data-stu-id="1fcfb-246">If you do not enable DKIM, Office 365 automatically creates a 1024-bit DKIM public key for your custom domain and the associated private key which we store internally in our datacenter.</span></span> <span data-ttu-id="1fcfb-247">Por padrão, o Office 365 usa uma configuração de assinatura padrão para domínios que não tem uma política aplicada.</span><span class="sxs-lookup"><span data-stu-id="1fcfb-247">By default, Office 365 uses a default signing configuration for domains that do not have a policy in place.</span></span> <span data-ttu-id="1fcfb-248">Isso significa que se você não configurar o DKIM por conta própria, o Office 365 usa a política e as chaves padrão que ele cria para habilitar o DKIM para seu domínio.</span><span class="sxs-lookup"><span data-stu-id="1fcfb-248">This means that if you do not set up DKIM yourself, Office 365 will use its default policy and keys it creates in order to enable DKIM for your domain.</span></span>
  
<span data-ttu-id="1fcfb-249">Além disso, se você desabilitar a assinatura DKIM após ativá-la, depois de um período de tempo o Office 365 aplicará automaticamente a política padrão do Office 365 para o seu domínio.</span><span class="sxs-lookup"><span data-stu-id="1fcfb-249">Also, if you disable DKIM signing after enabling it, after a period of time, Office 365 will automatically apply the Office 365 default policy for your domain.</span></span>
  
<span data-ttu-id="1fcfb-p128">No exemplo a seguir, suponha que o DKIM de fabrikam.com foi habilitado pelo Office 365, não pelo administrador do domínio. Isso significa que os CNAMEs necessários não existem no DNS. Assinaturas DKIM para email deste domínio terão uma aparência similar a esta:</span><span class="sxs-lookup"><span data-stu-id="1fcfb-p128">In the following example, suppose that DKIM for fabrikam.com was enabled by Office 365, not by the administrator of the domain. This means that the required CNAMEs do not exist in DNS. DKIM signatures for email from this domain will look something like this:</span></span>
  
```text
From: Second Example <second.example@fabrikam.com>
DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed;
    s=selector1-fabrikam-com; d=contoso.onmicrosoft.com; t=1429912795;
    h=From:To:Message-ID:Subject:MIME-Version:Content-Type;
    bh=<body hash>;
    b=<signed field>;
```

<span data-ttu-id="1fcfb-p129">Neste exemplo, o nome de host e o domínio contêm os valores para os quais o CNAME apontaria se a assinatura de DKIM para fabrikam.com tivesse sido ativada pelo administrador do domínio. Eventualmente, cada mensagem enviada do Office 365 será assinada com DKIM. Se você mesmo habilitar o DKIM, o domínio será o mesmo que o do campo de endereço De:, neste caso fabrikam.com. Caso contrário, os domínios não corresponderão entre si e, em vez disso, será usado o domínio inicial da sua organização. Para saber mais sobre como determinar seu domínio inicial, confira [Perguntas frequentes sobre domínios](https://support.office.com/article/1272bad0-4bd4-4796-8005-67d6fb3afc5a#bkmk_whydoihaveanonmicrosoft.comdomain).</span><span class="sxs-lookup"><span data-stu-id="1fcfb-p129">In this example, the host name and domain contain the values to which the CNAME would point if DKIM-signing for fabrikam.com had been enabled by the domain administrator. Eventually, every single message sent from Office 365 will be DKIM-signed. If you enable DKIM yourself, the domain will be the same as the domain in the From: address, in this case fabrikam.com. If you don't, it will not align and instead will use your organization's initial domain. For information about determining your initial domain, see [Domains FAQ](https://support.office.com/article/1272bad0-4bd4-4796-8005-67d6fb3afc5a#bkmk_whydoihaveanonmicrosoft.comdomain).</span></span>
  
## <a name="set-up-dkim-so-that-a-third-party-service-can-send-or-spoof-email-on-behalf-of-your-custom-domain"></a><span data-ttu-id="1fcfb-258">Configurar o DKIM de forma que um serviço terceirizado possa enviar, ou fazer falsificar, emails em nome de seu domínio personalizado</span><span class="sxs-lookup"><span data-stu-id="1fcfb-258">Set up DKIM so that a third-party service can send, or spoof, email on behalf of your custom domain</span></span>
<span data-ttu-id="1fcfb-259"><a name="SetUp3rdPartyspoof"> </a></span><span class="sxs-lookup"><span data-stu-id="1fcfb-259"></span></span>

<span data-ttu-id="1fcfb-p130">Alguns provedores de serviço de email em massa, ou provedores de software como serviço, permitem que você configure as chaves DKIM para o email originado de seu serviço. Isso exige a coordenação entre sua empresa e a empresa terceirizada para configurar os registros DNS necessários. Não há duas organizações que fazem isso exatamente da mesma maneira. Em vez disso, o processo depende totalmente da organização.</span><span class="sxs-lookup"><span data-stu-id="1fcfb-p130">Some bulk email service providers, or software-as-a-service providers, let you set up DKIM keys for email that originates from their service. This requires coordination between yourself and the third-party in order to set up the necessary DNS records. No two organizations do it exactly the same way. Instead, the process depends entirely on the organization.</span></span>
  
<span data-ttu-id="1fcfb-264">Um exemplo de mensagem mostrando um DKIM configurado adequadamente para contoso.com e bulkemailprovider.com pode parecer com este:</span><span class="sxs-lookup"><span data-stu-id="1fcfb-264">An example message showing a properly configured DKIM for contoso.com and bulkemailprovider.com might look like this:</span></span>
  
```text
Return-Path: <communication@bulkemailprovider.com>
 From: <sender@contoso.com>
 DKIM-Signature: s=s1024; d=contoso.com
 Subject: Here is a message from Bulk Email Provider's infrastructure, but with a DKIM signature authorized by contoso.com
```

<span data-ttu-id="1fcfb-265">Neste exemplo, para obter este resultado:</span><span class="sxs-lookup"><span data-stu-id="1fcfb-265">In this example, in order to achieve this result:</span></span>
  
1. <span data-ttu-id="1fcfb-266">O provedor de email em massa deu à Contoso uma chave pública de DKIM.</span><span class="sxs-lookup"><span data-stu-id="1fcfb-266">Bulk Email Provider gave Contoso a public DKIM key.</span></span>

2. <span data-ttu-id="1fcfb-267">A Contoso publicou a chave de DKIM em seu registro DNS.</span><span class="sxs-lookup"><span data-stu-id="1fcfb-267">Contoso published the DKIM key to its DNS record.</span></span>

3. <span data-ttu-id="1fcfb-p131">Ao enviar emails, o Provedor de Email em Massa assina a chave com a chave privada correspondente. Ao fazer isso, o Provedor de Email em Massa anexa a assinatura DKIM ao cabeçalho da mensagem.</span><span class="sxs-lookup"><span data-stu-id="1fcfb-p131">When sending email, Bulk Email Provider signs the key with the corresponding private key. By doing so, Bulk Email Provider attached the DKIM signature to the message header.</span></span>

4. <span data-ttu-id="1fcfb-p132">Sistemas de recebimento de email executam uma verificação de DKIM autenticando o valor DKIM-Signature d=\<domínio\> em relação ao domínio no campo de endereço From: (5322.From) da mensagem. Neste exemplo, os valores são correspondentes:</span><span class="sxs-lookup"><span data-stu-id="1fcfb-p132">Receiving email systems perform a DKIM check by authenticating the DKIM-Signature d=\<domain\> value against the domain in the From: (5322.From) address of the message. In this example, the values match:</span></span>

    <span data-ttu-id="1fcfb-272">remetente@**contoso.com**</span><span class="sxs-lookup"><span data-stu-id="1fcfb-272">sender@**contoso.com**</span></span>

    <span data-ttu-id="1fcfb-273">d=**contoso.com**</span><span class="sxs-lookup"><span data-stu-id="1fcfb-273">d=**contoso.com**</span></span>

## <a name="next-steps-after-you-set-up-dkim-for-office-365"></a><span data-ttu-id="1fcfb-274">Próximas etapas: depois de configurar o DKIM para o Office 365</span><span class="sxs-lookup"><span data-stu-id="1fcfb-274">Next steps: After you set up DKIM for Office 365</span></span>
<span data-ttu-id="1fcfb-275"><a name="DKIMNextSteps"> </a></span><span class="sxs-lookup"><span data-stu-id="1fcfb-275"></span></span>

<span data-ttu-id="1fcfb-276">Embora o DKIM tenha sido projetado para ajudar a evitar a falsificação, ele funciona melhor com SPF e DMARC.</span><span class="sxs-lookup"><span data-stu-id="1fcfb-276">Although DKIM is designed to help prevent spoofing, DKIM works better with SPF and DMARC.</span></span> <span data-ttu-id="1fcfb-277">Depois que você configurar o DKIM, se já não tiver configurado o SPF, deve fazê-lo.</span><span class="sxs-lookup"><span data-stu-id="1fcfb-277">Once you have set up DKIM, if you have not already set up SPF you should do so.</span></span> <span data-ttu-id="1fcfb-278">Para obter uma introdução rápida à SPF e para configurá-la rapidamente, veja [Configurar a SPF no Office 365 para ajudar a evitar falsificação](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span><span class="sxs-lookup"><span data-stu-id="1fcfb-278">For a quick introduction to SPF and to get it configured quickly, see [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span> <span data-ttu-id="1fcfb-279">Para compreender melhor como o Office 365 usa SPF, para solucionar problemas, ou para saber mais sobre implantações incomuns, como implantações híbridas, comece com [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).</span><span class="sxs-lookup"><span data-stu-id="1fcfb-279">For a more in-depth understanding of how Office 365 uses SPF, or for troubleshooting or non-standard deployments such as hybrid deployments, start with [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span> <span data-ttu-id="1fcfb-280">A seguir, confira [Usar DMARC para validar emails no Office 365](use-dmarc-to-validate-email.md).</span><span class="sxs-lookup"><span data-stu-id="1fcfb-280">Next, see [Use DMARC to validate email in Office 365](use-dmarc-to-validate-email.md).</span></span> <span data-ttu-id="1fcfb-281">[Cabeçalhos de mensagem antispam](anti-spam-message-headers.md), que inclui a sintaxe e os campos de cabeçalho usados pelo Office 365 para verificações de DKIM.</span><span class="sxs-lookup"><span data-stu-id="1fcfb-281">[Anti-spam message headers](anti-spam-message-headers.md) includes the syntax and header fields used by Office 365 for DKIM checks.</span></span>
