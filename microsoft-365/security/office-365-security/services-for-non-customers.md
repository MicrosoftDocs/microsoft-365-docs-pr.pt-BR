---
title: Serviços para não clientes que enviam emails para Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 19fd3e0f-8dbf-4049-a810-2c8ee6cefd48
ms.collection:
- M365-security-compliance
description: Para ajudar a manter a confiança do usuário no uso de email, a Microsoft colocou em uso várias políticas e tecnologias para ajudar a proteger nossos usuários.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3213cae1b04b3f1a1b861e8f2cfc698576013546
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203321"
---
# <a name="services-for-non-customers-sending-mail-to-microsoft-365"></a><span data-ttu-id="70b50-103">Serviços para não clientes que enviam emails para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="70b50-103">Services for non-customers sending mail to Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="70b50-104">O abuso de email, lixo eletrônico e emails fraudulentos (phishing) continuam a sobrecarregar todo o ecossistema de email.</span><span class="sxs-lookup"><span data-stu-id="70b50-104">Email abuse, junk email, and fraudulent emails (phishing) continue to burden the entire email ecosystem.</span></span> <span data-ttu-id="70b50-105">Para ajudar a manter a confiança do usuário no uso de email, a Microsoft colocou várias políticas e tecnologias para ajudar a proteger nossos usuários.</span><span class="sxs-lookup"><span data-stu-id="70b50-105">To help maintain user trust in the use of email, Microsoft has put various policies and technologies in place to help protect our users.</span></span> <span data-ttu-id="70b50-106">No entanto, a Microsoft entende que o email legítimo não deve ser afetado negativamente.</span><span class="sxs-lookup"><span data-stu-id="70b50-106">However, Microsoft understands that legitimate email should not be negatively affected.</span></span> <span data-ttu-id="70b50-107">Portanto, estabelecemos um pacote de serviços para ajudar os enviadores a melhorar a capacidade de entregar emails para Microsoft 365 usuários gerenciando proativamente sua reputação de envio.</span><span class="sxs-lookup"><span data-stu-id="70b50-107">Therefore, we have established a suite of services to help senders improve their ability to deliver email to Microsoft 365 users by proactively managing their sending reputation.</span></span>

<span data-ttu-id="70b50-108">Esta visão geral fornece informações sobre os benefícios que fornecemos à sua organização, mesmo que você não seja um cliente.</span><span class="sxs-lookup"><span data-stu-id="70b50-108">This overview provides information about benefits we provide to your organization even if you aren't a customer.</span></span>

## <a name="sender-solutions"></a><span data-ttu-id="70b50-109">Soluções de remetente</span><span class="sxs-lookup"><span data-stu-id="70b50-109">Sender solutions</span></span>

****

|<span data-ttu-id="70b50-110">Serviço</span><span class="sxs-lookup"><span data-stu-id="70b50-110">Service</span></span>|<span data-ttu-id="70b50-111">Benefícios</span><span class="sxs-lookup"><span data-stu-id="70b50-111">Benefits</span></span>|
|---|---|
|<span data-ttu-id="70b50-112">Este conteúdo de ajuda online</span><span class="sxs-lookup"><span data-stu-id="70b50-112">This online help content</span></span>|<span data-ttu-id="70b50-113">Fornece:</span><span class="sxs-lookup"><span data-stu-id="70b50-113">Provides:</span></span> <ul><li><span data-ttu-id="70b50-114">Um ponto de partida para quaisquer perguntas relacionadas à entrega de comunicações aos usuários do EOP.</span><span class="sxs-lookup"><span data-stu-id="70b50-114">A starting point for any questions related to delivering communications to EOP users.</span></span></li><li><span data-ttu-id="70b50-115">Inclui um guia online simples com nossas políticas e requisitos.</span><span class="sxs-lookup"><span data-stu-id="70b50-115">Includes a simple online guide with our policies and requirements.</span></span></li><li><span data-ttu-id="70b50-116">Uma visão geral dos filtros de lixo eletrônico e das tecnologias de autenticação empregadas pela Microsoft.</span><span class="sxs-lookup"><span data-stu-id="70b50-116">An overview of the junk email filters and authentication technologies employed by Microsoft.</span></span></li><ul>|
|[<span data-ttu-id="70b50-117">Suporte da Microsoft</span><span class="sxs-lookup"><span data-stu-id="70b50-117">Microsoft support</span></span>](#microsoft-support)|<span data-ttu-id="70b50-118">Fornece suporte de auto-ajuda e escalonamento para problemas de entrega.</span><span class="sxs-lookup"><span data-stu-id="70b50-118">Provides self-help and escalation support for delivery issues.</span></span>|
|[<span data-ttu-id="70b50-119">Portal de Lista de IP Anti-Spam</span><span class="sxs-lookup"><span data-stu-id="70b50-119">Anti-Spam IP Delist Portal</span></span>](#anti-spam-ip-delist-portal)|<span data-ttu-id="70b50-120">Uma ferramenta para enviar solicitação de lista de IP.</span><span class="sxs-lookup"><span data-stu-id="70b50-120">A tool to submit IP delist request.</span></span> <span data-ttu-id="70b50-121">Antes de enviar essa solicitação, é responsabilidade do remetente garantir que qualquer email que se origine do IP em questão não seja abusivo ou mal-intencionado.</span><span class="sxs-lookup"><span data-stu-id="70b50-121">Before submitting this request it is the sender's responsibility to ensure that any further mail originating from the IP in question is not abusive or malicious.</span></span>|
|[<span data-ttu-id="70b50-122">Relatórios de spam e abuso de lixo eletrônico provenientes de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="70b50-122">Abuse and spam reporting for junk email originating from Exchange Online</span></span>](#abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online)|<span data-ttu-id="70b50-123">Impede que o spam e outros emails indesejados seja enviado Exchange Online e atrapalhando a Internet e seu sistema de email.</span><span class="sxs-lookup"><span data-stu-id="70b50-123">Keeps spam and other unwanted mail from being sent from Exchange Online and cluttering up the internet and your mail system.</span></span>|
|

## <a name="microsoft-support"></a><span data-ttu-id="70b50-124">Suporte da Microsoft</span><span class="sxs-lookup"><span data-stu-id="70b50-124">Microsoft support</span></span>

<span data-ttu-id="70b50-125">A Microsoft oferece várias opções de suporte para pessoas com problemas para enviar emails Microsoft 365 destinatários.</span><span class="sxs-lookup"><span data-stu-id="70b50-125">Microsoft offers several support options for people having trouble sending mail to Microsoft 365 recipients.</span></span> <span data-ttu-id="70b50-126">Recomendamos que você:</span><span class="sxs-lookup"><span data-stu-id="70b50-126">We recommend that you:</span></span>

- <span data-ttu-id="70b50-127">Siga as instruções em qualquer relatório que não seja de entrega recebido.</span><span class="sxs-lookup"><span data-stu-id="70b50-127">Follow the instructions in any non-delivery report you receive.</span></span>

- <span data-ttu-id="70b50-128">Confira os problemas mais comuns encontrados por não clientes em Solução de problemas [de emails enviados para Office 365](troubleshooting-mail-sent-to-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="70b50-128">Check out the most common problems that non-customers encounter in [Troubleshooting mail sent to Office 365](troubleshooting-mail-sent-to-office-365.md).</span></span>

- <span data-ttu-id="70b50-129">Use o [Microsoft 365 de lista](https://sender.office.com) de usuários para enviar uma solicitação para que seu IP seja removido da lista de remetentes bloqueados.</span><span class="sxs-lookup"><span data-stu-id="70b50-129">Use the [Microsoft 365 delist portal](https://sender.office.com) to submit a request to have your IP removed from the blocked sender's list.</span></span>

- <span data-ttu-id="70b50-130">Leia os fóruns [da comunidade microsoft](https://community.office365.com/f/).</span><span class="sxs-lookup"><span data-stu-id="70b50-130">Read the [Microsoft community forums](https://community.office365.com/f/).</span></span>

- <span data-ttu-id="70b50-131">Entre em contato com o cliente que você está tentando enviar por email usando outro método e peça que contate o Suporte da Microsoft e abra um tíquete de suporte em seu nome.</span><span class="sxs-lookup"><span data-stu-id="70b50-131">Contact the customer you're trying to email using another method and ask them to contact Microsoft Support and open a support ticket on your behalf.</span></span> <span data-ttu-id="70b50-132">Em alguns casos, por motivos legais, o Suporte da Microsoft deve se comunicar diretamente com o remetente que possui o espaço IP que está sendo bloqueado.</span><span class="sxs-lookup"><span data-stu-id="70b50-132">In some cases, for legal reasons, Microsoft Support must communicate directly with the sender who owns the IP space that is being blocked.</span></span> <span data-ttu-id="70b50-133">No entanto, não clientes normalmente não podem abrir tíquetes de suporte.</span><span class="sxs-lookup"><span data-stu-id="70b50-133">However, non-customers typically can't open support tickets.</span></span>

  <span data-ttu-id="70b50-134">Para obter mais informações sobre o suporte técnico da Microsoft para Office 365, consulte [Support](/office365/servicedescriptions/office-365-platform-service-description/support).</span><span class="sxs-lookup"><span data-stu-id="70b50-134">For more information about Microsoft Technical support for Office 365, see [Support](/office365/servicedescriptions/office-365-platform-service-description/support).</span></span>

## <a name="anti-spam-ip-delist-portal"></a><span data-ttu-id="70b50-135">Portal de Lista de IP Anti-Spam</span><span class="sxs-lookup"><span data-stu-id="70b50-135">Anti-Spam IP Delist Portal</span></span>

<span data-ttu-id="70b50-136">Este é um portal de autoatendir que você pode usar para remover a si mesmo da lista de Microsoft 365 de envios bloqueados.</span><span class="sxs-lookup"><span data-stu-id="70b50-136">This is a self-service portal you can use to remove yourself from the Microsoft 365 blocked senders list.</span></span> <span data-ttu-id="70b50-137">Use este portal se você estiver recebendo uma mensagem de erro ao tentar enviar um email para um destinatário cujo endereço de email está no Microsoft 365 e você não acha que deveria estar.</span><span class="sxs-lookup"><span data-stu-id="70b50-137">Use this portal if you are you getting an error message when you try to send an email to a recipient whose email address is in Microsoft 365 and you don't think you should be.</span></span> <span data-ttu-id="70b50-138">Para obter mais informações, veja [Usar o portal de remoção para remover seu nome na lista de remetentes bloqueados](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).</span><span class="sxs-lookup"><span data-stu-id="70b50-138">For more information, see [Use the delist portal to remove yourself from the blocked senders list](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).</span></span>

## <a name="abuse-and-spam-reporting-for-junk-email-originating-from-exchange-online"></a><span data-ttu-id="70b50-139">Relatórios de spam e abuso de lixo eletrônico provenientes de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="70b50-139">Abuse and spam reporting for junk email originating from Exchange Online</span></span>

<span data-ttu-id="70b50-140">Às vezes, o Microsoft365 é usado por terceiros para enviar lixo eletrônico, violando nossos termos de uso e política.</span><span class="sxs-lookup"><span data-stu-id="70b50-140">Sometimes Microsoft365 is used by third parties to send junk email, in violation of our terms of use and policy.</span></span> <span data-ttu-id="70b50-141">Se você receber qualquer lixo eletrônico do Office 365, poderá relatar essas mensagens à Microsoft.</span><span class="sxs-lookup"><span data-stu-id="70b50-141">If you receive any junk email from Office 365, you can report these messages to Microsoft.</span></span> <span data-ttu-id="70b50-142">Para obter instruções, consulte [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="70b50-142">For instructions, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>