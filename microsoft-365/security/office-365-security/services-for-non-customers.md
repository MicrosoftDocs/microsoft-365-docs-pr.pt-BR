---
title: Serviços para não clientes enviando emails para a Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 19fd3e0f-8dbf-4049-a810-2c8ee6cefd48
ms.collection:
- M365-security-compliance
description: Para ajudar a manter a confiança do usuário no uso de email, a Microsoft colocou várias políticas e tecnologias para ajudar a proteger os usuários.
ms.openlocfilehash: 74389d3b975a0ffaebdc1619be40fd3ac74d72f4
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2020
ms.locfileid: "46652652"
---
# <a name="services-for-non-customers-sending-mail-to-microsoft-365"></a><span data-ttu-id="ae4e8-103">Serviços para não clientes enviando emails para a Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ae4e8-103">Services for non-customers sending mail to Microsoft 365</span></span>

<span data-ttu-id="ae4e8-104">O abuso por email, lixo eletrônico e emails fraudulentos (phishing) continuam a sobrecarregar todo o ecossistema de email.</span><span class="sxs-lookup"><span data-stu-id="ae4e8-104">Email abuse, junk email, and fraudulent emails (phishing) continue to burden the entire email ecosystem.</span></span> <span data-ttu-id="ae4e8-105">Para ajudar a manter a confiança do usuário no uso de email, a Microsoft colocou várias políticas e tecnologias em vigor para ajudar a proteger os usuários.</span><span class="sxs-lookup"><span data-stu-id="ae4e8-105">To help maintain user trust in the use of email, Microsoft has put various policies and technologies in place to help protect our users.</span></span> <span data-ttu-id="ae4e8-106">No entanto, a Microsoft reconhece que os emails legítimos não devem ser afetados negativamente.</span><span class="sxs-lookup"><span data-stu-id="ae4e8-106">However, Microsoft understands that legitimate email should not be negatively affected.</span></span> <span data-ttu-id="ae4e8-107">Portanto, estabelecemos um pacote de serviços para ajudar os remetentes a aprimorar a capacidade de entregar emails aos usuários da Microsoft 365, gerenciando proativamente sua reputação de envio.</span><span class="sxs-lookup"><span data-stu-id="ae4e8-107">Therefore, we have established a suite of services to help senders improve their ability to deliver email to Microsoft 365 users by proactively managing their sending reputation.</span></span>

<span data-ttu-id="ae4e8-108">Esta visão geral fornece informações sobre os benefícios que fornecemos à sua organização, mesmo que você não seja um cliente.</span><span class="sxs-lookup"><span data-stu-id="ae4e8-108">This overview provides information about benefits we provide to your organization even if you aren't a customer.</span></span>

## <a name="sender-solutions"></a><span data-ttu-id="ae4e8-109">Soluções de remetente</span><span class="sxs-lookup"><span data-stu-id="ae4e8-109">Sender solutions</span></span>

****

|<span data-ttu-id="ae4e8-110">Serviço</span><span class="sxs-lookup"><span data-stu-id="ae4e8-110">Service</span></span>|<span data-ttu-id="ae4e8-111">Benefícios</span><span class="sxs-lookup"><span data-stu-id="ae4e8-111">Benefits</span></span>|
|---|---|
|<span data-ttu-id="ae4e8-112">Este conteúdo da ajuda online</span><span class="sxs-lookup"><span data-stu-id="ae4e8-112">This online help content</span></span>|<span data-ttu-id="ae4e8-113">Lhe</span><span class="sxs-lookup"><span data-stu-id="ae4e8-113">Provides:</span></span> <br/> <span data-ttu-id="ae4e8-114">Um ponto de partida para qualquer dúvida relacionada ao envio de comunicações para usuários do EOP.</span><span class="sxs-lookup"><span data-stu-id="ae4e8-114">A starting point for any questions related to delivering communications to EOP users.</span></span> <br/><br/> <span data-ttu-id="ae4e8-115">O inclui um guia online simples com nossas políticas e requisitos.</span><span class="sxs-lookup"><span data-stu-id="ae4e8-115">Includes a simple online guide with our policies and requirements.</span></span> <br/><br/> <span data-ttu-id="ae4e8-116">Uma visão geral dos filtros de lixo eletrônico e tecnologias de autenticação empregadas pela Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ae4e8-116">An overview of the junk email filters and authentication technologies employed by Microsoft.</span></span>|
|[<span data-ttu-id="ae4e8-117">Suporte da Microsoft</span><span class="sxs-lookup"><span data-stu-id="ae4e8-117">Microsoft support</span></span>](#microsoft-support)|<span data-ttu-id="ae4e8-118">Fornece suporte a auto-ajuda e escalonamento para problemas de entrega.</span><span class="sxs-lookup"><span data-stu-id="ae4e8-118">Provides self-help and escalation support for delivery issues.</span></span>|
|[<span data-ttu-id="ae4e8-119">Portal de deslista de IPS antispam</span><span class="sxs-lookup"><span data-stu-id="ae4e8-119">Anti-Spam IP Delist Portal</span></span>](#anti-spam-ip-delist-portal)|<span data-ttu-id="ae4e8-120">Uma ferramenta para enviar a solicitação de deslistação de IP.</span><span class="sxs-lookup"><span data-stu-id="ae4e8-120">A tool to submit IP delist request.</span></span> <span data-ttu-id="ae4e8-121">Antes de enviar essa solicitação, é responsabilidade do remetente garantir que qualquer email proveniente do IP em questão não seja abusiva ou mal-intencionada.</span><span class="sxs-lookup"><span data-stu-id="ae4e8-121">Before submitting this request it is the sender's responsibility to ensure that any further mail originating from the IP in question is not abusive or malicious.</span></span>|
|[<span data-ttu-id="ae4e8-122">Relatórios de abuso e spam para lixo eletrônico originado do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="ae4e8-122">Abuse and spam reporting for junk email originating from Exchange Online</span></span>](#abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online)|<span data-ttu-id="ae4e8-123">Mantém spam e outras mensagens indesejadas enviadas do Exchange Online e truncando a Internet e seu sistema de email.</span><span class="sxs-lookup"><span data-stu-id="ae4e8-123">Keeps spam and other unwanted mail from being sent from Exchange Online and cluttering up the internet and your mail system.</span></span>|
|

## <a name="microsoft-support"></a><span data-ttu-id="ae4e8-124">Suporte da Microsoft</span><span class="sxs-lookup"><span data-stu-id="ae4e8-124">Microsoft support</span></span>

<span data-ttu-id="ae4e8-125">A Microsoft oferece várias opções de suporte para pessoas com problemas de envio de email para destinatários do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ae4e8-125">Microsoft offers several support options for people having trouble sending mail to Microsoft 365 recipients.</span></span> <span data-ttu-id="ae4e8-126">Recomendamos que você:</span><span class="sxs-lookup"><span data-stu-id="ae4e8-126">We recommend that you:</span></span>

- <span data-ttu-id="ae4e8-127">Siga as instruções em qualquer notificação de falha na entrega que você receber.</span><span class="sxs-lookup"><span data-stu-id="ae4e8-127">Follow the instructions in any non-delivery report you receive.</span></span>

- <span data-ttu-id="ae4e8-128">Confira os problemas mais comuns que não os clientes encontram na [solução de problemas de email enviados para o Office 365](troubleshooting-mail-sent-to-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="ae4e8-128">Check out the most common problems that non-customers encounter in [Troubleshooting mail sent to Office 365](troubleshooting-mail-sent-to-office-365.md).</span></span>

- <span data-ttu-id="ae4e8-129">Use o [portal de deslista da Microsoft 365](https://sender.office.com) para enviar uma solicitação para que o seu IP seja removido da lista do remetente bloqueado.</span><span class="sxs-lookup"><span data-stu-id="ae4e8-129">Use the [Microsoft 365 delist portal](https://sender.office.com) to submit a request to have your IP removed from the blocked sender's list.</span></span>

- <span data-ttu-id="ae4e8-130">Leia os [fóruns da Comunidade da Microsoft](https://community.office365.com/f/).</span><span class="sxs-lookup"><span data-stu-id="ae4e8-130">Read the [Microsoft community forums](https://community.office365.com/f/).</span></span>

- <span data-ttu-id="ae4e8-131">Entre em contato com o cliente em que você está tentando enviar um email usando outro método e peça a ele para entrar em contato com o suporte da Microsoft e abrir um tíquete de suporte em seu nome.</span><span class="sxs-lookup"><span data-stu-id="ae4e8-131">Contact the customer you're trying to email using another method and ask them to contact Microsoft Support and open a support ticket on your behalf.</span></span> <span data-ttu-id="ae4e8-132">Em alguns casos, por motivos legais, o suporte da Microsoft deve se comunicar diretamente com o remetente que possui o espaço IP que está sendo bloqueado.</span><span class="sxs-lookup"><span data-stu-id="ae4e8-132">In some cases, for legal reasons, Microsoft Support must communicate directly with the sender who owns the IP space that is being blocked.</span></span> <span data-ttu-id="ae4e8-133">No entanto, os usuários que não são normalmente não podem abrir tíquetes de suporte.</span><span class="sxs-lookup"><span data-stu-id="ae4e8-133">However, non-customers typically can't open support tickets.</span></span>

  <span data-ttu-id="ae4e8-134">Para obter mais informações sobre o suporte técnico da Microsoft para o Office 365, consulte [support](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/support).</span><span class="sxs-lookup"><span data-stu-id="ae4e8-134">For more information about Microsoft Technical support for Office 365, see [Support](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/support).</span></span>

## <a name="anti-spam-ip-delist-portal"></a><span data-ttu-id="ae4e8-135">Portal de deslista de IPS antispam</span><span class="sxs-lookup"><span data-stu-id="ae4e8-135">Anti-Spam IP Delist Portal</span></span>

<span data-ttu-id="ae4e8-136">Este é um portal de autoatendimento que você pode usar para ser removido da lista de remetentes bloqueados do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ae4e8-136">This is a self-service portal you can use to remove yourself from the Microsoft 365 blocked senders list.</span></span> <span data-ttu-id="ae4e8-137">Use este portal se você estiver recebendo uma mensagem de erro ao tentar enviar um email para um destinatário cujo endereço de email está no Microsoft 365 e você não achar que deve ser.</span><span class="sxs-lookup"><span data-stu-id="ae4e8-137">Use this portal if you are you getting an error message when you try to send an email to a recipient whose email address is in Microsoft 365 and you don't think you should be.</span></span> <span data-ttu-id="ae4e8-138">Para obter mais informações, veja [Usar o portal de remoção para remover seu nome na lista de remetentes bloqueados](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).</span><span class="sxs-lookup"><span data-stu-id="ae4e8-138">For more information, see [Use the delist portal to remove yourself from the blocked senders list](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).</span></span>

## <a name="abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online"></a><span data-ttu-id="ae4e8-139">Relatórios de abuso e spam para lixo eletrônico originado do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="ae4e8-139">Abuse and spam reporting for junk email originating from Exchange Online</span></span>

<span data-ttu-id="ae4e8-140">Às vezes, o Microsoft365 é usado por terceiros para enviar lixo eletrônico, violando nossos termos de uso e políticas.</span><span class="sxs-lookup"><span data-stu-id="ae4e8-140">Sometimes Microsoft365 is used by third parties to send junk email, in violation of our terms of use and policy.</span></span> <span data-ttu-id="ae4e8-141">Se você receber uma mensagem de lixo eletrônico do Office 365, é possível relatar essas mensagens à Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ae4e8-141">If you receive any junk email from Office 365, you can report these messages to Microsoft.</span></span> <span data-ttu-id="ae4e8-142">Para obter instruções, consulte [relatar mensagens e arquivos para a Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="ae4e8-142">For instructions, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>
