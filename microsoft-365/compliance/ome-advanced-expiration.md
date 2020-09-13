---
title: Definir uma data de vencimento para o email criptografado pela Criptografia de Mensagem Avançada do Office 365
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/8/2019
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Use a criptografia de mensagem avançada do Office 365 para estender sua segurança de email Configurando uma data de expiração em emails por meio de um modelo personalizado com marca.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0dcf9c82f9204f1357b49411d0ca87e87007eb96
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546155"
---
# <a name="set-an-expiration-date-for-email-encrypted-by-office-365-advanced-message-encryption"></a><span data-ttu-id="add67-103">Definir uma data de vencimento para o email criptografado pela Criptografia de Mensagem Avançada do Office 365</span><span class="sxs-lookup"><span data-stu-id="add67-103">Set an expiration date for email encrypted by Office 365 Advanced Message Encryption</span></span>

<span data-ttu-id="add67-104">O Office 365 Advanced Message Encryption está incluído no [microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 e5, Microsoft 365 E5 (precificação de pessoas sem fins lucrativos), Office 365 Enterprise E5 (precificação de pessoas sem fins lucrativos) e Office 365 Education a5.</span><span class="sxs-lookup"><span data-stu-id="add67-104">Office 365 Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (Nonprofit Staff Pricing), Office 365 Enterprise E5 (Nonprofit Staff Pricing), and Office 365 Education A5.</span></span> <span data-ttu-id="add67-105">Se sua organização tem uma assinatura que não inclui a criptografia de mensagem avançada do Office 365, você pode comprá-la com o complemento de SKU de conformidade da Microsoft 365 E5 para Microsoft 365 E3, Microsoft 365 E3 (preço de equipe sem fins lucrativos) ou o complemento avançado de SKU de conformidade avançada do Office para a Microsoft 365 E3, Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="add67-105">If your organization has a subscription that does not include Office 365 Advanced Message Encryption, you can purchase it with the Microsoft 365 E5 Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or the Office 365 Advanced Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or Office 365 SKUs.</span></span>

<span data-ttu-id="add67-106">Você pode usar a expiração de mensagens em emails enviados por seus usuários para destinatários externos que usam o portal do OME para acessar emails criptografados.</span><span class="sxs-lookup"><span data-stu-id="add67-106">You can use message expiration on emails that your users send to external recipients who use the OME Portal to access encrypted emails.</span></span> <span data-ttu-id="add67-107">Você força os destinatários a usar o portal do OME para exibir e responder a emails criptografados enviados pela sua organização usando um modelo personalizado com marca que especifica uma data de expiração no Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="add67-107">You force recipients to use the OME portal to view and reply to encrypted emails sent by your organization by using a custom branded template that specifies an expiration date in Windows Powershell.</span></span>

<span data-ttu-id="add67-108">Como administrador global do O365, quando você aplica a marca da empresa para personalizar a aparência das mensagens de email da sua organização, você também pode especificar uma expiração para essas mensagens de email.</span><span class="sxs-lookup"><span data-stu-id="add67-108">As an O365 global administrator, when you apply your company brand to customize the look of your organization's email messages, you can also specify an expiration for these email messages.</span></span> <span data-ttu-id="add67-109">Com a criptografia de mensagem avançada do Office 365, você pode criar vários modelos para emails criptografados originados em sua organização.</span><span class="sxs-lookup"><span data-stu-id="add67-109">With Office 365 Advanced Message Encryption, you can create multiple templates for encrypted emails that originate from your organization.</span></span> <span data-ttu-id="add67-110">Usando um modelo, você pode controlar por quanto tempo os destinatários têm acesso a emails enviados por seus usuários.</span><span class="sxs-lookup"><span data-stu-id="add67-110">Using a template, you can control how long recipients have access to mail sent by your users.</span></span>

<span data-ttu-id="add67-111">Quando um usuário final recebe emails com uma data de expiração definida, o usuário vê a data de expiração no email de conteúdo adicional.</span><span class="sxs-lookup"><span data-stu-id="add67-111">When an end user receives mail that has an expiration date set, the user sees the expiration date in the wrapper email.</span></span> <span data-ttu-id="add67-112">Se um usuário tentar abrir um email expirado, um erro aparecerá no portal do OME.</span><span class="sxs-lookup"><span data-stu-id="add67-112">If a user tries to open an expired mail, an error appears in the OME portal.</span></span>

<span data-ttu-id="add67-113">Você só pode definir datas de expiração para emails para destinatários externos.</span><span class="sxs-lookup"><span data-stu-id="add67-113">You can only set expiration dates for emails to external recipients.</span></span>

<span data-ttu-id="add67-114">Com a criptografia de mensagem avançada do Office 365, sempre que você aplicar a identidade visual personalizada, o Office 365 aplica o wrapper a emails que se ajustam à regra de fluxo de emails para a qual você aplica o modelo.</span><span class="sxs-lookup"><span data-stu-id="add67-114">With Office 365 Advanced Message Encryption, anytime you apply custom branding, the Office 365 applies the wrapper to email that fits the mail flow rule to which you apply the template.</span></span> <span data-ttu-id="add67-115">Além disso, você só poderá usar a expiração se usar identidade visual personalizada.</span><span class="sxs-lookup"><span data-stu-id="add67-115">In addition, you can only use expiration if you use custom branding.</span></span>

## <a name="create-a-custom-branding-template-to-force-mail-expiration-by-using-powershell"></a><span data-ttu-id="add67-116">Criar um modelo de identidade visual personalizado para forçar a expiração de email usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="add67-116">Create a custom branding template to force mail expiration by using PowerShell</span></span>

1. <span data-ttu-id="add67-117">[Conecte-se ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) com uma conta que tenha permissões de administrador global em sua organização.</span><span class="sxs-lookup"><span data-stu-id="add67-117">[Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) with an account that has global administrator permissions in your organization.</span></span>

2. <span data-ttu-id="add67-118">Execute o cmdlet New-OMEConfiguration.</span><span class="sxs-lookup"><span data-stu-id="add67-118">Run the New-OMEConfiguration cmdlet.</span></span>

     ```powershell
     New-OMEConfiguration -Identity "Expire in 7 days" -ExternalMailExpiryInDays 7
     ```

<span data-ttu-id="add67-119">Onde:</span><span class="sxs-lookup"><span data-stu-id="add67-119">Where:</span></span>

- <span data-ttu-id="add67-120">`Identity` é o nome do modelo personalizado.</span><span class="sxs-lookup"><span data-stu-id="add67-120">`Identity` is the name of the custom template.</span></span>

- <span data-ttu-id="add67-121">`ExternalMailExpiryInDays` Identifica o número de dias que os destinatários podem manter os emails antes de expirarem.</span><span class="sxs-lookup"><span data-stu-id="add67-121">`ExternalMailExpiryInDays` identifies the number of days that recipients can keep mail before it expires.</span></span> <span data-ttu-id="add67-122">Você pode usar qualquer valor entre 1 a 730 dias.</span><span class="sxs-lookup"><span data-stu-id="add67-122">You can use any value between 1–730 days.</span></span>

## <a name="more-information-about-office-365-advanced-message-encryption"></a><span data-ttu-id="add67-123">Mais informações sobre a criptografia de mensagem avançada do Office 365</span><span class="sxs-lookup"><span data-stu-id="add67-123">More information about Office 365 Advanced Message Encryption</span></span>

- [<span data-ttu-id="add67-124">Criptografia de Mensagem Avançada do 365 Office</span><span class="sxs-lookup"><span data-stu-id="add67-124">Office 365 Advanced Message Encryption</span></span>](ome-advanced-message-encryption.md)

- [<span data-ttu-id="add67-125">Revogar email criptografado pelo a Criptografia de Mensagem Avançada do Office 365</span><span class="sxs-lookup"><span data-stu-id="add67-125">Revoke email encrypted by Office 365 Advanced Message Encryption</span></span>](revoke-ome-encrypted-mail.md)

- [<span data-ttu-id="add67-126">Descrição do serviço de conformidade e política de mensagens</span><span class="sxs-lookup"><span data-stu-id="add67-126">Message policy and compliance service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
