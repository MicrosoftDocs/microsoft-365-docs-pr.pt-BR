---
title: Enviar e-mail criptografado
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.date: 9/20/2018
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 496e690b-b75d-4ff5-bf34-cc32905d0364
description: Saiba como enviar emails criptografados usando o Outlook.
ms.openlocfilehash: af34d632ead2ae1e6ed81845c56b95b95af1dc51
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911969"
---
# <a name="encrypt-or-label-your-sensitive-email"></a><span data-ttu-id="d0cfb-103">Criptografe ou rotule emails confidenciais</span><span class="sxs-lookup"><span data-stu-id="d0cfb-103">Encrypt or label your sensitive email</span></span>

<span data-ttu-id="d0cfb-104">Seus dados e informações de campanha são importantes e geralmente confidenciais.</span><span class="sxs-lookup"><span data-stu-id="d0cfb-104">Your data and campaign information is important and often confidential.</span></span> <span data-ttu-id="d0cfb-105">Ajude a proteger essas informações confidenciais usando rótulos de criptografia e sensibilidade para que você e seus destinatários de email tratem as informações com a sensibilidade necessária.</span><span class="sxs-lookup"><span data-stu-id="d0cfb-105">Help protect this sensitive information by using encryption and sensitivity labels so you and your email recipients treat the information with the sensitivity it requires.</span></span>

## <a name="best-practices"></a><span data-ttu-id="d0cfb-106">Práticas recomendadas</span><span class="sxs-lookup"><span data-stu-id="d0cfb-106">Best practices</span></span>

<span data-ttu-id="d0cfb-107">Antes de enviar emails com informações confidenciais ou confidenciais, considere a possibilidade de ligar:</span><span class="sxs-lookup"><span data-stu-id="d0cfb-107">Before you send email with confidential or sensitive information, consider turning on:</span></span>

- <span data-ttu-id="d0cfb-108">**Criptografia:** Você pode criptografar seu email para proteger a privacidade das informações no email.</span><span class="sxs-lookup"><span data-stu-id="d0cfb-108">**Encryption:** You can encrypt your email to protect the privacy of the information in the email.</span></span> <span data-ttu-id="d0cfb-109">Quando você criptografa uma mensagem de email, ela é convertida de texto simples aceitável em texto cifrado embaralhado.</span><span class="sxs-lookup"><span data-stu-id="d0cfb-109">When you encrypt an email message, it's converted from readable plain text into scrambled cypher text.</span></span> <span data-ttu-id="d0cfb-110">Somente o destinatário que tem a chave privada que corresponde à chave pública usada para criptografar a mensagem pode decifrar a mensagem para leitura.</span><span class="sxs-lookup"><span data-stu-id="d0cfb-110">Only the recipient who has the private key that matches the public key used to encrypt the message can decipher the message for reading.</span></span> <span data-ttu-id="d0cfb-111">No entanto, qualquer destinatário sem a chave privada correspondente vê texto indecifrável.</span><span class="sxs-lookup"><span data-stu-id="d0cfb-111">Any recipient without the corresponding private key, however, sees indecipherable text.</span></span> <span data-ttu-id="d0cfb-112">O administrador pode definir regras para criptografar automaticamente mensagens que atendem a determinados critérios.</span><span class="sxs-lookup"><span data-stu-id="d0cfb-112">Your admin can define rules to automatically encrypt messages that meet certain criteria.</span></span> <span data-ttu-id="d0cfb-113">Por exemplo, seu administrador pode criar uma regra que criptografa todas as mensagens enviadas fora da sua organização ou todas as mensagens que mencionam palavras ou frases específicas.</span><span class="sxs-lookup"><span data-stu-id="d0cfb-113">For instance, your admin can create a rule that encrypts all messages sent outside your organization or all messages that mention specific words or phrases.</span></span> <span data-ttu-id="d0cfb-114">Todas as regras de criptografia serão aplicadas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="d0cfb-114">Any encryption rules will be applied automatically.</span></span>
- <span data-ttu-id="d0cfb-115">**Rótulos de sensibilidade:** Sua campanha também pode configurar rótulos de sensibilidade que você pode aplicar aos seus arquivos e emails para mantê-los em conformidade com as políticas de proteção de informações da campanha.</span><span class="sxs-lookup"><span data-stu-id="d0cfb-115">**Sensitivity labels:** Your campaign can also set up sensitivity labels that you can apply to your files and email to keep them compliant with your campaign's information protection policies.</span></span> <span data-ttu-id="d0cfb-116">Quando você definir um rótulo, o rótulo persiste com seu email, mesmo quando é enviado - por exemplo, aparecendo como um header para sua mensagem.</span><span class="sxs-lookup"><span data-stu-id="d0cfb-116">When you set a label, the label persists with your email, even when it's sent - for example, by appearing as a header to your message.</span></span>

![Diagrama de um email com explicações explicativas para rótulos e criptografia](../media/m365-campaign-email-encrypt.png)

## <a name="set-it-up"></a><span data-ttu-id="d0cfb-118">Configuração</span><span class="sxs-lookup"><span data-stu-id="d0cfb-118">Set it up</span></span>

<span data-ttu-id="d0cfb-119">Se você quiser criptografar uma mensagem que não atender a uma regra pré-definida ou se o administrador não tiver definido nenhuma regra, poderá aplicar uma variedade de regras de criptografia diferentes antes de enviar a mensagem.</span><span class="sxs-lookup"><span data-stu-id="d0cfb-119">If you want to encrypt a message that doesn't meet a pre-defined rule or your admin hasn't set up any rules, you can apply a variety of different encryption rules before you send the message.</span></span> <span data-ttu-id="d0cfb-120">Para enviar uma mensagem criptografada do Outlook 2013 ou 2016 ou do Outlook 2016 para Mac, selecione **Opções > Permissões** e selecione a opção de proteção de que você precisa.</span><span class="sxs-lookup"><span data-stu-id="d0cfb-120">To send an encrypted message from Outlook 2013 or 2016, or Outlook 2016 for Mac, select **Options > Permissions**, then select the protection option you need.</span></span> <span data-ttu-id="d0cfb-121">Você também pode enviar uma mensagem criptografada selecionando o **botão Proteger** no Outlook na Web.</span><span class="sxs-lookup"><span data-stu-id="d0cfb-121">You can also send an encrypted message by selecting the **Protect** button in Outlook on the web.</span></span> <span data-ttu-id="d0cfb-122">Para obter mais informações, [consulte Send, view, and reply to encrypted messages in Outlook for PC](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980).</span><span class="sxs-lookup"><span data-stu-id="d0cfb-122">For more information, see [Send, view, and reply to encrypted messages in Outlook for PC](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980).</span></span>

## <a name="admin-settings"></a><span data-ttu-id="d0cfb-123">Configurações do administrador</span><span class="sxs-lookup"><span data-stu-id="d0cfb-123">Admin settings</span></span>

<span data-ttu-id="d0cfb-124">Você pode aprender tudo sobre como configurar a criptografia de email na [criptografia de email no Microsoft 365](../compliance/email-encryption.md).</span><span class="sxs-lookup"><span data-stu-id="d0cfb-124">You can learn all about setting up email encryption at [Email encryption in Microsoft 365](../compliance/email-encryption.md).</span></span>

### <a name="automatically-encrypt-email-messages"></a><span data-ttu-id="d0cfb-125">Criptografar automaticamente mensagens de email</span><span class="sxs-lookup"><span data-stu-id="d0cfb-125">Automatically encrypt email messages</span></span>

<span data-ttu-id="d0cfb-126">Os administradores podem criar regras de fluxo de emails para proteger automaticamente as mensagens de email enviadas e recebidas de sua campanha.</span><span class="sxs-lookup"><span data-stu-id="d0cfb-126">Admins can create mail flow rules to automatically protect email messages that are sent and received from your campaign.</span></span> <span data-ttu-id="d0cfb-127">Configurar regras para criptografar qualquer mensagem de email de saída e remover a criptografia de mensagens criptografadas provenientes de dentro da sua organização ou de respostas a mensagens criptografadas enviadas de sua organização.</span><span class="sxs-lookup"><span data-stu-id="d0cfb-127">Set up rules to encrypt any outgoing email messages, and remove encryption from encrypted messages coming from inside your organization or from replies to encrypted messages sent from your organization.</span></span>

<span data-ttu-id="d0cfb-128">Você cria regras de fluxo de emails para criptografar mensagens de email com os novos recursos de Criptografia de Mensagens (OME) do Office 365.</span><span class="sxs-lookup"><span data-stu-id="d0cfb-128">You create mail flow rules to encrypt email messages with the new Office 365 Message Encryption (OME) capabilities.</span></span> <span data-ttu-id="d0cfb-129">Defina regras de fluxo de emails para disparar a criptografia de mensagens com os novos recursos OME usando o Centro de Administração do Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="d0cfb-129">Define mail flow rules for triggering message encryption with the new OME capabilities by using the Exchange Admin Center (EAC).</span></span> 

1. <span data-ttu-id="d0cfb-130">Em um navegador da Web, usando uma conta de trabalho ou de estudante que recebeu permissões de administrador global, entre.</span><span class="sxs-lookup"><span data-stu-id="d0cfb-130">In a web browser, using a work or school account that has been granted global administrator permissions, sign in.</span></span>
2. <span data-ttu-id="d0cfb-131">Escolha o painel Administrador.</span><span class="sxs-lookup"><span data-stu-id="d0cfb-131">Choose the Admin tile.</span></span>
3. <span data-ttu-id="d0cfb-132">No centro de administração, escolha **Centros de administração > Exchange**.</span><span class="sxs-lookup"><span data-stu-id="d0cfb-132">In the admin center, choose **Admin centers > Exchange**.</span></span>

<span data-ttu-id="d0cfb-133">Para obter mais informações, consulte [Definir regras de fluxo de emails para criptografar mensagens de email](../compliance/define-mail-flow-rules-to-encrypt-email.md).</span><span class="sxs-lookup"><span data-stu-id="d0cfb-133">For more information, see [Define mail flow rules to encrypt email messages](../compliance/define-mail-flow-rules-to-encrypt-email.md).</span></span>

### <a name="brand-your-encryption-messages"></a><span data-ttu-id="d0cfb-134">Marca suas mensagens de criptografia</span><span class="sxs-lookup"><span data-stu-id="d0cfb-134">Brand your encryption messages</span></span>

<span data-ttu-id="d0cfb-135">Você também pode aplicar sua identidade visual de campanha para personalizar a aparência e o texto nas mensagens de email.</span><span class="sxs-lookup"><span data-stu-id="d0cfb-135">You can also apply your campaign branding to customize the look and the text in the email messages.</span></span> <span data-ttu-id="d0cfb-136">Para obter mais informações, [consulte Add your organization's brand to your encrypted messages](../compliance/email-encryption.md).</span><span class="sxs-lookup"><span data-stu-id="d0cfb-136">For more information, see [Add your organization's brand to your encrypted messages](../compliance/email-encryption.md).</span></span>