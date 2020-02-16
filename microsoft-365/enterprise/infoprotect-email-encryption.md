---
title: 'Etapa 6: configurar criptografia de email'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom: ''
description: Entenda e configure o gerenciamento de acesso privilegiado do Office 365.
ms.openlocfilehash: d678c109f42901be2413c2b33e362d6796be96b7
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42067168"
---
# <a name="step-6-configure-email-encryption"></a><span data-ttu-id="00b4f-103">Etapa 6: configurar criptografia de email</span><span class="sxs-lookup"><span data-stu-id="00b4f-103">Step 6: Configure email encryption</span></span>

<span data-ttu-id="00b4f-104">*Esta etapa é opcional e se aplica às versões E3 e E5 do Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="00b4f-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![Fase 6: proteção de informações](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="00b4f-106">Há três tipos de criptografia de email no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="00b4f-106">There are three types of email encryption in Microsoft 365.</span></span>

|||
|:-------|:-----|
| <span data-ttu-id="00b4f-107">Criptografia de Mensagem do Office (OME)</span><span class="sxs-lookup"><span data-stu-id="00b4f-107">Office Message Encryption (OME)</span></span> | <span data-ttu-id="00b4f-108">Criptografia para email do Exchange Online enviado fora da sua organização.</span><span class="sxs-lookup"><span data-stu-id="00b4f-108">Encryption for Exchange Online email sent outside your organization.</span></span> |
| <span data-ttu-id="00b4f-109">Gerenciamento de Direitos de Informação (IRM)</span><span class="sxs-lookup"><span data-stu-id="00b4f-109">Information Rights Management (IRM)</span></span> | <span data-ttu-id="00b4f-110">Criptografia e permissões que trafegam com o email.</span><span class="sxs-lookup"><span data-stu-id="00b4f-110">Encryption and permissions that travel with the email.</span></span> |
| <span data-ttu-id="00b4f-111">S/MIME (Secure/Multipurpose Internet Mail Extensions)</span><span class="sxs-lookup"><span data-stu-id="00b4f-111">Secure/Multipurpose Internet Mail Extensions (S/MIME)</span></span> | <span data-ttu-id="00b4f-112">Proteção de email com criptografia e assinaturas digitais.</span><span class="sxs-lookup"><span data-stu-id="00b4f-112">Email protection with encryption and digital signatures.</span></span> |
|||

## <a name="office-365-message-encryption"></a><span data-ttu-id="00b4f-113">Criptografia de Mensagem do Office 365</span><span class="sxs-lookup"><span data-stu-id="00b4f-113">Office 365 Message Encryption</span></span>

<span data-ttu-id="00b4f-114">Com o OME, sua organização pode enviar e receber mensagens de email criptografadas entre pessoas dentro e fora da sua organização.</span><span class="sxs-lookup"><span data-stu-id="00b4f-114">With OME, your organization can send and receive encrypted email messages between people inside and outside your organization.</span></span> <span data-ttu-id="00b4f-115">O OME funciona com o Outlook.com, o Yahoo!, o Gmail e outros serviços de email.</span><span class="sxs-lookup"><span data-stu-id="00b4f-115">OME works with Outlook.com, Yahoo!, Gmail, and other email services.</span></span> <span data-ttu-id="00b4f-116">A criptografia de mensagens de email ajuda a garantir que apenas destinatários pretendidos possam exibir a mensagem.</span><span class="sxs-lookup"><span data-stu-id="00b4f-116">Email message encryption helps ensure that only intended recipients can view the message.</span></span>

![Criptografia OME de mensagens de email](../media/infoprotect-email-encryption/ome-encryption.png)

<span data-ttu-id="00b4f-118">Você configura regras de transporte que definem as condições de criptografia.</span><span class="sxs-lookup"><span data-stu-id="00b4f-118">You set up transport rules that define the conditions for encryption.</span></span> <span data-ttu-id="00b4f-119">Quando um usuário envia uma mensagem que corresponde a uma regra, a criptografia é aplicada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="00b4f-119">When a user sends a message that matches a rule, encryption is applied automatically.</span></span>

<span data-ttu-id="00b4f-120">Para exibir mensagens criptografadas, os destinatários podem obter uma senha de uso único, entrar com uma conta da Microsoft ou entrar com uma conta corporativa ou de estudante associada ao Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="00b4f-120">To view encrypted messages, recipients can either get a one-time passcode, sign in with a Microsoft account, or sign in with a work or school account associated with Microsoft 365.</span></span> <span data-ttu-id="00b4f-121">Os destinatários também podem enviar respostas criptografadas.</span><span class="sxs-lookup"><span data-stu-id="00b4f-121">Recipients can also send encrypted replies.</span></span> <span data-ttu-id="00b4f-122">Eles não precisam de sua própria assinatura do Microsoft 365 para exibir mensagens criptografadas ou enviar respostas criptografadas.</span><span class="sxs-lookup"><span data-stu-id="00b4f-122">They don't need their own Microsoft 365 subscription to view encrypted messages or send encrypted replies.</span></span>

<span data-ttu-id="00b4f-123">Para saber mais, veja [Criptografia de Mensagens do Office 365](https://docs.microsoft.com/Office365/SecurityCompliance/ome).</span><span class="sxs-lookup"><span data-stu-id="00b4f-123">For more information, see [Office 365 Message Encryption](https://docs.microsoft.com/Office365/SecurityCompliance/ome).</span></span>

## <a name="irm"></a><span data-ttu-id="00b4f-124">IRM</span><span class="sxs-lookup"><span data-stu-id="00b4f-124">IRM</span></span>

<span data-ttu-id="00b4f-125">O IRM no Microsoft 365 ajuda você a proteger suas informações com criptografia adicional e aplicando uma política inteligente que especifica quem tem acesso ao que eles podem fazer.</span><span class="sxs-lookup"><span data-stu-id="00b4f-125">IRM in Microsoft 365 helps you secure your information with additional encryption and by applying an intelligent policy that specifies who has access what they can do.</span></span> <span data-ttu-id="00b4f-126">Para mensagens de email, você pode usar o IRM para criptografia e aplicar restrições de uso.</span><span class="sxs-lookup"><span data-stu-id="00b4f-126">For email messages, you can use IRM for encryption and to apply usage restrictions.</span></span> <span data-ttu-id="00b4f-127">Por exemplo, você pode especificar que alguns destinatários tenham todos os recursos para gerenciar o email e alguns não tenham a capacidade de imprimir ou encaminhar o email.</span><span class="sxs-lookup"><span data-stu-id="00b4f-127">For example, you can specify that some recipients have all abilities to manage the email and some do not have the ability to print or forward the email.</span></span> 

<span data-ttu-id="00b4f-128">As políticas de IRM são configuradas no Microsoft 365 e podem ser aplicadas a documentos no SharePoint Online e mensagens de email.</span><span class="sxs-lookup"><span data-stu-id="00b4f-128">IRM policies are configured within Microsoft 365 and can apply to documents in SharePoint Online and email messages.</span></span> <span data-ttu-id="00b4f-129">Um email protegido por IRM inclui as configurações de política aplicadas aplicadas e viajar com ela.</span><span class="sxs-lookup"><span data-stu-id="00b4f-129">An IRM-protected email includes the applied policy settings applied and travel with it.</span></span> 

![Proteção do IRM de mensagens de email](../media/infoprotect-email-encryption/irm-protection.png)

<span data-ttu-id="00b4f-131">Quando o destinatário abre o email com a política incluída, as configurações de política são usadas para descriptografar a mensagem e determinar o que o destinatário pode fazer com ele.</span><span class="sxs-lookup"><span data-stu-id="00b4f-131">When the recipient opens the email with the included policy, the policy settings are used to decrypt the message and determine what the recipient can do with it.</span></span> 

<span data-ttu-id="00b4f-132">Confira mais informações em [Gerenciamento de Direitos de Informação no Exchange Online]( https://docs.microsoft.com/office365/SecurityCompliance/information-rights-management-in-exchange-online).</span><span class="sxs-lookup"><span data-stu-id="00b4f-132">For more information, see [Information Rights Management in Exchange Online]( https://docs.microsoft.com/office365/SecurityCompliance/information-rights-management-in-exchange-online).</span></span>

## <a name="smime"></a><span data-ttu-id="00b4f-133">S/MIME</span><span class="sxs-lookup"><span data-stu-id="00b4f-133">S/MIME</span></span>

<span data-ttu-id="00b4f-134">O S/MIME é uma solução de proteção baseada em email digital baseada em certificado que permite criptografar e assinar digitalmente uma mensagem.</span><span class="sxs-lookup"><span data-stu-id="00b4f-134">S/MIME is a digital certificate-based email-based protection solution that allows you to both encrypt and digitally sign a message.</span></span> <span data-ttu-id="00b4f-135">A criptografia de mensagem ajuda a garantir que somente o destinatário pretendido poderá abrir e ler a mensagem.</span><span class="sxs-lookup"><span data-stu-id="00b4f-135">The message encryption helps ensure that only the intended recipient can open and read the message.</span></span> <span data-ttu-id="00b4f-136">Uma assinatura digital ajuda o destinatário a validar a identidade do remetente e a determinar que apenas o remetente poderia enviá-lo.</span><span class="sxs-lookup"><span data-stu-id="00b4f-136">A digital signature helps the recipient validate the identity of the sender and determine that only the sender could have sent it.</span></span>

![Proteção S/MIME de mensagens de email](../media/infoprotect-email-encryption/smime-protection.png)

<span data-ttu-id="00b4f-138">O S/MIME pode ser usado para emails para outras caixas de correio em sua assinatura do Microsoft 365 ou para usuários externos.</span><span class="sxs-lookup"><span data-stu-id="00b4f-138">S/MIME can be used for email to other mailboxes in your Microsoft 365 subscription or to external users.</span></span>
<span data-ttu-id="00b4f-139">Tanto a criptografia de mensagens quanto as assinaturas digitais são possibilitadas por meio do uso de certificados digitais que contenham as chaves pública e privada para criptografar ou descriptografar mensagens e criar e verificar assinaturas digitais.</span><span class="sxs-lookup"><span data-stu-id="00b4f-139">Both message encryption and digital signatures are made possible through the use of digital certificates that contain the public and private keys for encrypting or decrypting messages and creating and verifying digital signatures.</span></span>
<span data-ttu-id="00b4f-140">Para usar S/MIME, você deve ter as chaves públicas para cada destinatário.</span><span class="sxs-lookup"><span data-stu-id="00b4f-140">To use S/MIME, you must have the public keys for each recipient.</span></span> <span data-ttu-id="00b4f-141">Os destinatários mantêm suas próprias chaves privadas, o que deve permanecer seguro.</span><span class="sxs-lookup"><span data-stu-id="00b4f-141">Recipients maintain their own private keys, which must remain secure.</span></span> <span data-ttu-id="00b4f-142">Se sua chave privada estiver comprometida, você precisará obter um novo certificado digital e redistribuir as chaves públicas para todos os remetentes potenciais.</span><span class="sxs-lookup"><span data-stu-id="00b4f-142">If your private key is compromised, you need to get a new digital certificate and redistribute public keys to all potential senders.</span></span>

<span data-ttu-id="00b4f-143">Para obter mais informações, consulte [S/MIME para assinatura e criptografia de mensagens](https://docs.microsoft.com/Exchange/policy-and-compliance/smime).</span><span class="sxs-lookup"><span data-stu-id="00b4f-143">For more information, see [S/MIME for message signing and encryption](https://docs.microsoft.com/Exchange/policy-and-compliance/smime).</span></span>


<span data-ttu-id="00b4f-144">Como um ponto de verificação provisório, confira o [Critério de saída](infoprotect-exit-criteria.md#crit-infoprotect-step6) correspondente desta etapa.</span><span class="sxs-lookup"><span data-stu-id="00b4f-144">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step6) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="00b4f-145">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="00b4f-145">Next step</span></span>

|||
|:-------|:-----|
|![Etapa 7](../media/stepnumbers/Step7.png)|[<span data-ttu-id="00b4f-147">Configurar o gerenciamento de acesso privilegiado do Office 365</span><span class="sxs-lookup"><span data-stu-id="00b4f-147">Configure privileged access management for Office 365</span></span>](infoprotect-configure-privileged-access-management.md)|
