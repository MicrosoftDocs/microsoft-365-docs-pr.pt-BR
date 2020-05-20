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
ms.openlocfilehash: 5318fbe045c909e3b7f81d195a8e6b4d5eb96dc1
ms.sourcegitcommit: 5c43e89ed94ad9fd1db049446383c65e548189b7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2020
ms.locfileid: "44322142"
---
# <a name="encrypt-or-label-your-sensitive-email"></a><span data-ttu-id="562c3-103">Criptografar ou rotular seus emails confidenciais</span><span class="sxs-lookup"><span data-stu-id="562c3-103">Encrypt or label your sensitive email</span></span>

<span data-ttu-id="562c3-104">Suas informações de dados e de campanha são importantes e freqüentemente confidenciais.</span><span class="sxs-lookup"><span data-stu-id="562c3-104">Your data and campaign information is important and often confidential.</span></span> <span data-ttu-id="562c3-105">Ajude a proteger essas informações confidenciais usando a criptografia e os rótulos de confidencialidade para que você e seus destinatários de email tratem as informações com a confidencialidade exigida.</span><span class="sxs-lookup"><span data-stu-id="562c3-105">Help protect this sensitive information by using encryption and sensitivity labels so you and your email recipients treat the information with the sensitivity it requires.</span></span>


## <a name="best-practices"></a><span data-ttu-id="562c3-106">Práticas recomendadas</span><span class="sxs-lookup"><span data-stu-id="562c3-106">Best practices</span></span>

<span data-ttu-id="562c3-107">Antes de enviar emails com informações confidenciais ou confidenciais, considere ativar:</span><span class="sxs-lookup"><span data-stu-id="562c3-107">Before you send email with confidential or sensitive information, consider turning on:</span></span>

- <span data-ttu-id="562c3-108">**Criptografia:** Você pode criptografar seu email para proteger a privacidade das informações no email.</span><span class="sxs-lookup"><span data-stu-id="562c3-108">**Encryption:** You can encrypt your email to protect the privacy of the information in the email.</span></span> <span data-ttu-id="562c3-109">Quando você criptografa uma mensagem de email, ela é convertida de texto sem formatação legível em texto Cypher embaralhado.</span><span class="sxs-lookup"><span data-stu-id="562c3-109">When you encrypt an email message, it's converted from readable plain text into scrambled cypher text.</span></span> <span data-ttu-id="562c3-110">Somente o destinatário que tem a chave privada que corresponde à chave pública usada para criptografar a mensagem pode decifrar a mensagem para leitura.</span><span class="sxs-lookup"><span data-stu-id="562c3-110">Only the recipient who has the private key that matches the public key used to encrypt the message can decipher the message for reading.</span></span> <span data-ttu-id="562c3-111">No entanto, qualquer destinatário sem a chave privada correspondente vê o texto indecifrável.</span><span class="sxs-lookup"><span data-stu-id="562c3-111">Any recipient without the corresponding private key, however, sees indecipherable text.</span></span> <span data-ttu-id="562c3-112">O administrador pode definir regras para criptografar automaticamente as mensagens que atendem a determinados critérios.</span><span class="sxs-lookup"><span data-stu-id="562c3-112">Your admin can define rules to automatically encrypt messages that meet certain criteria.</span></span> <span data-ttu-id="562c3-113">Por exemplo, o administrador pode criar uma regra que criptografe todas as mensagens enviadas fora da sua organização ou todas as mensagens que mencionam palavras ou frases específicas.</span><span class="sxs-lookup"><span data-stu-id="562c3-113">For instance, your admin can create a rule that encrypts all messages sent outside your organization or all messages that mention specific words or phrases.</span></span> <span data-ttu-id="562c3-114">Qualquer regra de criptografia será aplicada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="562c3-114">Any encryption rules will be applied automatically.</span></span>
- <span data-ttu-id="562c3-115">**Rótulos de sensibilidade:** Sua campanha também pode configurar rótulos de confidencialidade que você pode aplicar aos seus arquivos e email para mantê-los em conformidade com as políticas de proteção de informações da sua campanha.</span><span class="sxs-lookup"><span data-stu-id="562c3-115">**Sensitivity labels:** Your campaign can also set up sensitivity labels that you can apply to your files and email to keep them compliant with your campaign's information protection policies.</span></span> <span data-ttu-id="562c3-116">Quando você define um rótulo, o rótulo persiste com seu email, mesmo quando ele é enviado por exemplo, aparecendo como um cabeçalho para sua mensagem.</span><span class="sxs-lookup"><span data-stu-id="562c3-116">When you set a label, the label persists with your email, even when it's sent - for example, by appearing as a header to your message.</span></span>

![Diagrama de um email com textos explicativos para rótulos e criptografia](../media/m365-campaign-email-encrypt.png)


## <a name="set-it-up"></a><span data-ttu-id="562c3-118">Configuração</span><span class="sxs-lookup"><span data-stu-id="562c3-118">Set it up</span></span>

<span data-ttu-id="562c3-119">Se você deseja criptografar uma mensagem que não atende a uma regra predefinida ou seu administrador não configurou nenhuma regra, você pode aplicar uma variedade de regras de criptografia diferentes antes de enviar a mensagem.</span><span class="sxs-lookup"><span data-stu-id="562c3-119">If you want to encrypt a message that doesn't meet a pre-defined rule or your admin hasn't set up any rules, you can apply a variety of different encryption rules before you send the message.</span></span> <span data-ttu-id="562c3-120">Para enviar uma mensagem criptografada do Outlook 2013 ou 2016 ou do Outlook 2016 para Mac, selecione **opções > permissões**e, em seguida, selecione a opção de proteção necessária.</span><span class="sxs-lookup"><span data-stu-id="562c3-120">To send an encrypted message from Outlook 2013 or 2016, or Outlook 2016 for Mac, select **Options > Permissions**, then select the protection option you need.</span></span> <span data-ttu-id="562c3-121">Você também pode enviar uma mensagem criptografada selecionando o botão **proteger** no Outlook na Web.</span><span class="sxs-lookup"><span data-stu-id="562c3-121">You can also send an encrypted message by selecting the **Protect** button in Outlook on the web.</span></span> <span data-ttu-id="562c3-122">Para obter mais informações, consulte [enviar, exibir e responder a mensagens criptografadas no Outlook para PC](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980).</span><span class="sxs-lookup"><span data-stu-id="562c3-122">For more information, see [Send, view, and reply to encrypted messages in Outlook for PC](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980).</span></span>

## <a name="admin-settings"></a><span data-ttu-id="562c3-123">Configurações de administrador</span><span class="sxs-lookup"><span data-stu-id="562c3-123">Admin settings</span></span>

<span data-ttu-id="562c3-124">Você pode aprender tudo sobre como configurar a criptografia de email em [criptografia de email no Office 365](https://docs.microsoft.com/microsoft-365/compliance/email-encryption).</span><span class="sxs-lookup"><span data-stu-id="562c3-124">You can learn all about setting up email encryption at [Email encryption in Office 365](https://docs.microsoft.com/microsoft-365/compliance/email-encryption).</span></span>

### <a name="automatically-encrypt-email-messages"></a><span data-ttu-id="562c3-125">Criptografar mensagens de email automaticamente</span><span class="sxs-lookup"><span data-stu-id="562c3-125">Automatically encrypt email messages</span></span>

<span data-ttu-id="562c3-126">Os administradores podem criar regras de fluxo de email para proteger automaticamente as mensagens de email enviadas e recebidas de sua campanha.</span><span class="sxs-lookup"><span data-stu-id="562c3-126">Admins can create mail flow rules to automatically protect email messages that are sent and received from your campaign.</span></span> <span data-ttu-id="562c3-127">Configurar regras para criptografar qualquer mensagem de email de saída e remover a criptografia de mensagens criptografadas de dentro da sua organização ou de respostas para mensagens criptografadas enviadas da sua organização.</span><span class="sxs-lookup"><span data-stu-id="562c3-127">Set up rules to encrypt any outgoing email messages, and remove encryption from encrypted messages coming from inside your organization or from replies to encrypted messages sent from your organization.</span></span> 

<span data-ttu-id="562c3-128">Você cria regras de fluxo de email para criptografar mensagens de email com os novos recursos de criptografia de mensagens do Office 365 (OME).</span><span class="sxs-lookup"><span data-stu-id="562c3-128">You create mail flow rules to encrypt email messages with the new Office 365 Message Encryption (OME) capabilities.</span></span> <span data-ttu-id="562c3-129">Definir regras de fluxo de email para acionar a criptografia de mensagens com os novos recursos do OME usando o centro de administração do Exchange (Eat).</span><span class="sxs-lookup"><span data-stu-id="562c3-129">Define mail flow rules for triggering message encryption with the new OME capabilities by using the Exchange Admin Center (EAC).</span></span> 

1. <span data-ttu-id="562c3-130">Em um navegador da Web, usando uma conta corporativa ou de estudante que recebeu permissões de administrador global, entre no Office 365.</span><span class="sxs-lookup"><span data-stu-id="562c3-130">In a web browser, using a work or school account that has been granted global administrator permissions, sign in to Office 365.</span></span> 
2. <span data-ttu-id="562c3-131">Escolha o bloco administrador.</span><span class="sxs-lookup"><span data-stu-id="562c3-131">Choose the Admin tile.</span></span> 
3. <span data-ttu-id="562c3-132">No centro de administração, escolha **centros de administração > Exchange**.</span><span class="sxs-lookup"><span data-stu-id="562c3-132">In the admin center, choose **Admin centers > Exchange**.</span></span> 

<span data-ttu-id="562c3-133">Para obter mais informações, consulte [definir regras de fluxo de email para criptografar mensagens de email no Office 365](https://docs.microsoft.com/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email).</span><span class="sxs-lookup"><span data-stu-id="562c3-133">For more information, see [Define mail flow rules to encrypt email messages in Office 365](https://docs.microsoft.com/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email).</span></span>

### <a name="brand-your-encryption-messages"></a><span data-ttu-id="562c3-134">Marcar suas mensagens de criptografia</span><span class="sxs-lookup"><span data-stu-id="562c3-134">Brand your encryption messages</span></span>

<span data-ttu-id="562c3-135">Você também pode aplicar a sua marca de campanha para personalizar a aparência e o texto nas mensagens de email.</span><span class="sxs-lookup"><span data-stu-id="562c3-135">You can also apply your campaign branding to customize the look and the text in the email messages.</span></span> <span data-ttu-id="562c3-136">Para obter mais informações, consulte [Adicionar a marca da sua organização às mensagens criptografadas](https://docs.microsoft.com/microsoft-365/compliance/email-encryption).</span><span class="sxs-lookup"><span data-stu-id="562c3-136">For more information, see [Add your organization's brand to your encrypted messages](https://docs.microsoft.com/microsoft-365/compliance/email-encryption).</span></span>

