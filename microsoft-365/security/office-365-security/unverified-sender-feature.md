---
title: Remetente não verificado
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Para impedir que mensagens de phishing acessem sua caixa de correio, o Outlook.com e o Outlook na Web verificam se o remetente é quem dizem eles e marcam mensagens suspeitas como lixo eletrônico.
ms.openlocfilehash: a6ae80adb9ddae2c675e75d747dda27f09a404fb
ms.sourcegitcommit: 4986032867b8664a215178b5e095cbda021f3450
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2020
ms.locfileid: "41957246"
---
# <a name="unverified-sender"></a><span data-ttu-id="2d82e-103">Remetente não verificado</span><span class="sxs-lookup"><span data-stu-id="2d82e-103">Unverified Sender</span></span>

> [!NOTE]
> <span data-ttu-id="2d82e-104">Essas atualizações estão sendo lançadas agora e podem não estar disponíveis para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="2d82e-104">These updates are rolling out now, and might not be available for all users.</span></span> <span data-ttu-id="2d82e-105">Esse recurso tem suporte para usuários da área de trabalho do Enterprise Outlook.com e Enterprise Outlook.</span><span class="sxs-lookup"><span data-stu-id="2d82e-105">This feature is supported for Enterprise Outlook.com and Enterprise Outlook Win32 desktop users.</span></span> <span data-ttu-id="2d82e-106">No momento, ele não está disponível para usuários do Office 365 do consumidor.</span><span class="sxs-lookup"><span data-stu-id="2d82e-106">It is not currently available for consumer Office 365 users.</span></span>

<span data-ttu-id="2d82e-107">Para impedir que mensagens de phishing acessem sua caixa de correio, o Office 365 verifica se os remetentes são quem eles dizem ser e marcam mensagens suspeitas como lixo eletrônico.</span><span class="sxs-lookup"><span data-stu-id="2d82e-107">To prevent phishing messages from reaching your mailbox, Office 365 verifies that the senders are who they say they are and mark suspicious messages as junk email.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2d82e-108">Quando uma mensagem é marcada como um golpe de phishing, o Outlook exibe um aviso na parte superior da página, mas todos os links na mensagem ainda podem ser abertos.</span><span class="sxs-lookup"><span data-stu-id="2d82e-108">When a message is marked as a phishing scam, Outlook displays a warning at the top of the page, but any links in the message can still be opened.</span></span>

## <a name="how-can-i-identify-a-suspicious-message-in-my-inbox"></a><span data-ttu-id="2d82e-109">Como identificar uma mensagem suspeita em minha caixa de entrada?</span><span class="sxs-lookup"><span data-stu-id="2d82e-109">How can I identify a suspicious message in my inbox?</span></span>

<span data-ttu-id="2d82e-110">O Outlook mostra indicadores quando o remetente de uma mensagem não pode ser identificado ou sua identidade é diferente da que você vê no endereço de.</span><span class="sxs-lookup"><span data-stu-id="2d82e-110">Outlook shows indicators when the sender of a message either can't be identified or their identity is different from what you see in the From address.</span></span>

## <a name="you-see-a--in-the-sender-image"></a><span data-ttu-id="2d82e-111">Você vê um '? ' na imagem do remetente</span><span class="sxs-lookup"><span data-stu-id="2d82e-111">You see a '?' in the sender image</span></span>

<span data-ttu-id="2d82e-112">Quando o Office 365 não pode verificar a identidade do remetente usando técnicas de autenticação de email, um '? ' é exibido na imagem do remetente.</span><span class="sxs-lookup"><span data-stu-id="2d82e-112">When Office 365 can't verify the identity of the sender using email authentication techniques, a '?' is displayed in the sender image.</span></span>

![A mensagem não passou na verificação](../media/message-did-not-pass-verification.jpg)

<span data-ttu-id="2d82e-114">Nem todas as mensagens que não são autenticadas são mal-intencionadas.</span><span class="sxs-lookup"><span data-stu-id="2d82e-114">Not every message that fails to authenticate is malicious.</span></span> <span data-ttu-id="2d82e-115">No entanto, você deve ter cuidado para interagir com mensagens que não são autenticadas se você não reconhece o remetente.</span><span class="sxs-lookup"><span data-stu-id="2d82e-115">However, you should be careful about interacting with messages that don't authenticate if you don't recognize the sender.</span></span> <span data-ttu-id="2d82e-116">Ou, se você reconhece um remetente que normalmente não tem um '? ' na imagem do remetente, mas, repentinamente, você começa a vê-lo, que pode ser um sinal de que o remetente está sendo falsificado.</span><span class="sxs-lookup"><span data-stu-id="2d82e-116">Or, if you recognize a sender that normally doesn't have a '?' in the sender image, but you suddenly start seeing it, that could be a sign the sender is being spoofed.</span></span>

## <a name="how-to-manage-which-messages-receive-the-unverified-sender-treatment"></a><span data-ttu-id="2d82e-117">Como gerenciar quais mensagens recebem o tratamento de remetentes não verificados</span><span class="sxs-lookup"><span data-stu-id="2d82e-117">How to manage which messages receive the unverified sender treatment</span></span> 

<span data-ttu-id="2d82e-118">Se você for um cliente do Office 365, poderá gerenciar esse recurso através do centro de conformidade & segurança do Office 365.</span><span class="sxs-lookup"><span data-stu-id="2d82e-118">If you are an Office 365 customer you can manage this feature through the Office 365 Security & Compliance Center.</span></span>

- <span data-ttu-id="2d82e-119">No centro de conformidade & segurança, os administradores globais ou de segurança podem ativar ou desativar o recurso, através da proteção contra falsificação na política de anti-golpes.</span><span class="sxs-lookup"><span data-stu-id="2d82e-119">In the Security & Compliance Center, global or security administrators can turn the feature on or off, through anti-spoofing protection under the Anti-Phish policy.</span></span> <span data-ttu-id="2d82e-120">Além disso, você pode usar o cmdlet **set-AntiPhishPolicy** no PowerShell do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="2d82e-120">Additionally, you can use the **Set-AntiPhishPolicy** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="2d82e-121">Para obter detalhes, consulte [proteção contra phishing no Office 365](anti-phishing-protection.md) e [set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-antiphishpolicy).</span><span class="sxs-lookup"><span data-stu-id="2d82e-121">For details, see [Anti-phishing protection in Office 365](anti-phishing-protection.md) and [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-antiphishpolicy).</span></span>

    ![Edição de remetentes não autenticados na interface gráfica.](../media/unverified-sender-article-editing-unauthenticated-senders.jpg)

- <span data-ttu-id="2d82e-123">Se um administrador identificou um falso positivo e um remetente não deve receber o tratamento de remetentes não verificados, uma das ações a seguir pode ser executada para adicionar o remetente à lista de permissões de falsificação de inteligência de falsificação:</span><span class="sxs-lookup"><span data-stu-id="2d82e-123">If an admin has identified a false positive, and a sender should not be receiving the unverified sender treatment, one of the following actions can be taken to add the sender to the Spoof Intelligence spoof allow list:</span></span>

  - <span data-ttu-id="2d82e-124">Adicionar o par de domínios por meio da compreensão de inteligência de falsificação.</span><span class="sxs-lookup"><span data-stu-id="2d82e-124">Add the domain pair through the Spoof Intelligence Insight.</span></span> <span data-ttu-id="2d82e-125">Para obter detalhes, consulte [Walkthrough: spoof Intelligence percepção](walkthrough-spoof-intelligence-insight.md).</span><span class="sxs-lookup"><span data-stu-id="2d82e-125">For details, see [Walkthrough: spoof intelligence insight](walkthrough-spoof-intelligence-insight.md).</span></span>

  - <span data-ttu-id="2d82e-126">Adicione o par de domínios por meio do cmdlet **set-PhishFilterPolicy** no PowerShell do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="2d82e-126">Add the domain pair through the **Set-PhishFilterPolicy** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="2d82e-127">Para obter detalhes, consulte [set-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-phishfilterpolicy) e [set up Office 365 ATP anti-phishing and anti-phishing Policies](set-up-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="2d82e-127">For details, see [Set-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-phishfilterpolicy) and [Set up Office 365 ATP anti-phishing and anti-phishing policies](set-up-anti-phishing-policies.md).</span></span>

<span data-ttu-id="2d82e-128">Além disso, não aplicamos o tratamento de remetentes não verificados se a mensagem foi entregue à caixa de entrada via regras de fluxo de emails (também conhecidas como regras de transporte) ou à lista de domínios seguros (políticas antispam).</span><span class="sxs-lookup"><span data-stu-id="2d82e-128">Additionally, we don't apply the unverified sender treatment if the message was delivered to the Inbox via mail flow rules (also known as transport rules) or the Safe Domain List (anti-spam policies).</span></span>

## <a name="how-to-manage-the-via-tag"></a><span data-ttu-id="2d82e-129">Como gerenciar a marca "via"</span><span class="sxs-lookup"><span data-stu-id="2d82e-129">How to manage the 'via' tag</span></span> 

<span data-ttu-id="2d82e-130">Se você for um cliente do Office 365, poderá gerenciar esse recurso através do centro de conformidade & segurança do Office 365, da mesma maneira que você gerencia o tratamento de remetentes não verificados.</span><span class="sxs-lookup"><span data-stu-id="2d82e-130">If you are an Office 365 customer you can manage this feature through the Office 365 Security & Compliance center, the same way that you manage the unverified sender treatment.</span></span> <span data-ttu-id="2d82e-131">Se você adicionar o remetente à lista de permissões de spoof de spoof Intelligence, o tratamento ' via ' não será aplicado.</span><span class="sxs-lookup"><span data-stu-id="2d82e-131">If you add the sender to the Spoof Intelligence spoof allow list, the 'via' treatment will not be applied.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="2d82e-132">Perguntas frequentes</span><span class="sxs-lookup"><span data-stu-id="2d82e-132">Frequently asked questions</span></span>

### <a name="what-criteria-does-outlookcom-and-outlook-win32-desktop-use-to-add-the--and-the-via-properties"></a><span data-ttu-id="2d82e-133">Que critérios o Outlook.com e a área de trabalho Win32 do Outlook usam para adicionar as propriedades '? ' e ' via '?</span><span class="sxs-lookup"><span data-stu-id="2d82e-133">What criteria does Outlook.com and Outlook Win32 desktop use to add the '?' and the 'via' properties?</span></span>

<span data-ttu-id="2d82e-134">Para o '? ' na imagem do remetente: Outlook.com requer que a mensagem passe o SPF ou a autenticação do DKIM e receba uma passagem dMarc ou uma passagem de autenticação composta da Office 365 spoof Intelligence.</span><span class="sxs-lookup"><span data-stu-id="2d82e-134">For the '?' in the sender image:  Outlook.com requires that the message pass either SPF or DKIM authentication and receive either a dmarc pass, or a composite authentication pass from Office 365 Spoof Intelligence.</span></span> <span data-ttu-id="2d82e-135">Para obter detalhes, consulte [set up SPF in Office 365 para ajudar a impedir a falsificação](set-up-spf-in-office-365-to-help-prevent-spoofing.md) e [uso do DKIM para validar emails de saída enviados do seu domínio personalizado no Office 365](use-dkim-to-validate-outbound-email.md).</span><span class="sxs-lookup"><span data-stu-id="2d82e-135">For details, see [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md) and [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md).</span></span>

<span data-ttu-id="2d82e-136">Para o via Tag: se o domínio no endereço de for diferente do domínio na assinatura do DKIM ou do email SMTP de, Outlook.com exibe o domínio em um desses dois campos (preferência à assinatura DKIM).</span><span class="sxs-lookup"><span data-stu-id="2d82e-136">For the via tag: If the domain in the From address is different from the domain in the DKIM signature or the SMTP MAIL FROM, Outlook.com displays the domain in one of those two fields (preferring the DKIM signature).</span></span>

### <a name="how-do-i-remove-the--without-utilizing-the-spoof-intelligence-spoof-allow-list"></a><span data-ttu-id="2d82e-137">Como faço para remover o '? ' sem usar a lista de permissões de falsificação de spoof Intelligence?</span><span class="sxs-lookup"><span data-stu-id="2d82e-137">How do I remove the '?' without utilizing the Spoof Intelligence spoof allow list?</span></span>

<span data-ttu-id="2d82e-138">Para o '? ' na imagem do remetente: como um remetente, você deve autenticar sua mensagem com o SPF ou o DKIM.</span><span class="sxs-lookup"><span data-stu-id="2d82e-138">For the '?' in the sender image: As a sender, you should authenticate your message with either SPF or DKIM.</span></span>

<span data-ttu-id="2d82e-139">Para o via Tag: como um remetente, você deve garantir que o domínio na assinatura DKIM ou o email SMTP de seja o mesmo que ou seja um subdomínio de, o domínio no endereço de.</span><span class="sxs-lookup"><span data-stu-id="2d82e-139">For the via tag: As a sender, you should ensure that either the domain in the DKIM signature or the SMTP MAIL FROM is the same as, or is a subdomain of, the domain in the From address.</span></span>

### <a name="do-outlookcom-and-outlook-win32-desktop-show-this-for-every-message-that-doesnt-pass-authentication"></a><span data-ttu-id="2d82e-140">O Outlook.com e o Outlook Win32 desktop mostram isso para cada mensagem que não aprova a autenticação?</span><span class="sxs-lookup"><span data-stu-id="2d82e-140">Do Outlook.com and Outlook Win32 desktop show this for every message that doesn't pass authentication?</span></span>

<span data-ttu-id="2d82e-141">Não necessariamente.</span><span class="sxs-lookup"><span data-stu-id="2d82e-141">Not necessarily.</span></span> <span data-ttu-id="2d82e-142">O Office 365 pode ter outras propriedades dentro da mensagem para autenticar o remetente.</span><span class="sxs-lookup"><span data-stu-id="2d82e-142">Office 365 may have other properties within the message to authenticate the sender.</span></span>

## <a name="related-topics"></a><span data-ttu-id="2d82e-143">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="2d82e-143">Related topics</span></span>

[<span data-ttu-id="2d82e-144">Ajudar a proteger sua conta de email do Outlook.com</span><span class="sxs-lookup"><span data-stu-id="2d82e-144">Help protect your Outlook.com email account</span></span>](https://support.office.com/article/a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)

[<span data-ttu-id="2d82e-145">Lidar com phishing ou falsificação no Outlook.com</span><span class="sxs-lookup"><span data-stu-id="2d82e-145">Deal with phishing or spoofing in Outlook.com</span></span>](https://support.office.com/article/0d882ea5-eedc-4bed-aebc-079ffa1105a3)

[<span data-ttu-id="2d82e-146">Filtrar lixo eletrônico e spam no Outlook na Web</span><span class="sxs-lookup"><span data-stu-id="2d82e-146">Filter junk email and spam in Outlook on the web</span></span>](https://support.office.com/article/db786e79-54e2-40cc-904f-d89d57b7f41d)
