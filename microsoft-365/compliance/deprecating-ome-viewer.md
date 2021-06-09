---
title: Preterindo o aplicativo visualizador de criptografia de mensagens
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6336cabb-b06e-402f-9e85-8bb9eb4ce68f
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: O Criptografia de Mensagens do Office 365 (OME) Viewer foi removido das lojas Android e Apple em 2018.
ms.openlocfilehash: bb96601a8a542d53f6732ab9316051c1a820ba46
ms.sourcegitcommit: 06d9e056eabfbac8fafe66cc32907b33d4ae8253
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/12/2021
ms.locfileid: "50741518"
---
# <a name="deprecating-message-encryption-viewer-app"></a><span data-ttu-id="e60ea-103">Preterindo o aplicativo visualizador de criptografia de mensagens</span><span class="sxs-lookup"><span data-stu-id="e60ea-103">Deprecating Message Encryption Viewer App</span></span>

<span data-ttu-id="e60ea-104">Em 15 de agosto de 2018, removemos o aplicativo móvel do visualizador de Criptografia de Mensagens do Office 365 (OME) das lojas Android e Apple.</span><span class="sxs-lookup"><span data-stu-id="e60ea-104">On August 15, 2018, we removed the Office 365 Message Encryption (OME) Viewer mobile app from Android and Apple stores.</span></span> <span data-ttu-id="e60ea-105">O Visualizador de Criptografia de Mensagens do Office 365 aplicativo móvel foi necessário para ler mensagens de email e anexos que foram criptografados com a versão anterior do OME em telefones Apple e Android.</span><span class="sxs-lookup"><span data-stu-id="e60ea-105">The Office 365 Message Encryption Viewer mobile app was required to read email messages and attachments that were encrypted with the previous version of OME on Apple and Android phones.</span></span> <span data-ttu-id="e60ea-106">Além de remover o aplicativo visualizador OME, não estamos fazendo outras alterações na versão anterior do OME.</span><span class="sxs-lookup"><span data-stu-id="e60ea-106">Apart from removing the OME Viewer app, we are not making any other changes to the previous version of OME.</span></span>
  
## <a name="changes-from-august-2018"></a><span data-ttu-id="e60ea-107">Alterações de agosto de 2018</span><span class="sxs-lookup"><span data-stu-id="e60ea-107">Changes from August 2018</span></span>

<span data-ttu-id="e60ea-108">Conforme anunciado em setembro de 2017, lançamos uma nova versão do [Criptografia de Mensagens do Office 365](https://aka.ms/ome2017) para que os usuários possam enviar mensagens criptografadas e protegidas para qualquer pessoa dentro ou fora da organização sem o requisito do aplicativo móvel.</span><span class="sxs-lookup"><span data-stu-id="e60ea-108">As announced September 2017, we have released a new version of [Office 365 Message Encryption](https://aka.ms/ome2017) so that users can send encrypted and protected messages to anyone inside or outside the organization without the requirement of the mobile app.</span></span> <span data-ttu-id="e60ea-109">Desde então, adicionamos recursos adicionais:</span><span class="sxs-lookup"><span data-stu-id="e60ea-109">Since then, we've added additional capabilities:</span></span>
  
- [<span data-ttu-id="e60ea-110">Modelo somente criptografia</span><span class="sxs-lookup"><span data-stu-id="e60ea-110">Encrypt-only template</span></span>](https://aka.ms/encryptonly)

- [<span data-ttu-id="e60ea-111">Controle para descriptografar anexos</span><span class="sxs-lookup"><span data-stu-id="e60ea-111">Control to decrypt attachments</span></span>](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Admin-control-for-attachments-now-available-in-Office-365/ba-p/204007)

<span data-ttu-id="e60ea-112">Com essa alteração, os usuários não poderão mais baixar o aplicativo Visualizador de Criptografia de Mensagens do Office 365 móvel a partir de 1º de agosto.</span><span class="sxs-lookup"><span data-stu-id="e60ea-112">With this change, users will no longer be able to download the Office 365 Message Encryption Viewer mobile app beginning August 1.</span></span> <span data-ttu-id="e60ea-113">Como resultado, os destinatários de email podem não conseguir ler mensagens criptografadas com a versão anterior do OME em alguns dispositivos móveis Android e Apple.</span><span class="sxs-lookup"><span data-stu-id="e60ea-113">As a result, mail recipients may not be able to read messages encrypted with the previous version of OME on some Android and Apple mobile devices.</span></span> <span data-ttu-id="e60ea-114">No entanto, eles ainda poderão ler essas mensagens em computadores pessoais (por meio de navegadores da área de trabalho).</span><span class="sxs-lookup"><span data-stu-id="e60ea-114">However, they will still be able to read these messages on personal computers (via desktop browsers).</span></span> <span data-ttu-id="e60ea-115">Os usuários que já baixaram o aplicativo continuarão a usá-lo.</span><span class="sxs-lookup"><span data-stu-id="e60ea-115">Users who have already downloaded the app will continue to be able to use it.</span></span>
  
## <a name="why-this-change-was-made"></a><span data-ttu-id="e60ea-116">Por que essa alteração foi feita</span><span class="sxs-lookup"><span data-stu-id="e60ea-116">Why this change was made</span></span>

<span data-ttu-id="e60ea-117">A nova versão do OME não exige mais um aplicativo móvel para ler mensagens de email e anexos protegidos.</span><span class="sxs-lookup"><span data-stu-id="e60ea-117">The new version of OME no longer requires a mobile app to read protected email messages and attachments.</span></span> <span data-ttu-id="e60ea-118">Os clientes que usam os novos recursos OME podem exibir a mensagem protegida no Outlook móveis e não clientes podem exibir mensagens protegidas em um navegador.</span><span class="sxs-lookup"><span data-stu-id="e60ea-118">Customers using the new OME capabilities can view the protected message in Outlook mobile and non-customers can view protected messages in a browser.</span></span>
  
<span data-ttu-id="e60ea-119">Exigir que os usuários baixem um aplicativo móvel é outro obstáculo para os clientes exibirem mensagens protegidas.</span><span class="sxs-lookup"><span data-stu-id="e60ea-119">Requiring users to download a mobile app is another hurdle for customers to view protected messages.</span></span> <span data-ttu-id="e60ea-120">Os novos Criptografia de Mensagens do Office 365 oferecem uma experiência móvel melhor.</span><span class="sxs-lookup"><span data-stu-id="e60ea-120">The new Office 365 Message Encryption capabilities provide a better mobile experience.</span></span>
  
## <a name="can-i-still-use-the-previous-version-of-office-365-message-encryption"></a><span data-ttu-id="e60ea-121">Ainda posso usar a versão anterior do Criptografia de Mensagens do Office 365</span><span class="sxs-lookup"><span data-stu-id="e60ea-121">Can I still use the previous version of Office 365 Message Encryption</span></span>

<span data-ttu-id="e60ea-122">A versão anterior do Criptografia de Mensagens do Office 365 não será preterida no momento, no entanto, fizemos melhorias significativas na nova versão do Criptografia de Mensagens do Office 365, o que facilita a criptografia e os direitos de proteger dados confidenciais para qualquer pessoa e em qualquer dispositivo , incluindo a capacidade dos usuários de ler mensagens protegidas diretamente no Outlook (desktop, móvel e web).</span><span class="sxs-lookup"><span data-stu-id="e60ea-122">The previous version of Office 365 Message Encryption will not be deprecated at this time, however, we have made significant enhancements to the new version of Office 365 Message Encryption, which make it easier to encrypt and rights protect sensitive data to anyone and on any device - including the ability for users to read protected messages directly in Outlook (desktop, mobile, and web).</span></span> 
  
## <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a><span data-ttu-id="e60ea-123">O que preciso fazer para me preparar para essa mudança</span><span class="sxs-lookup"><span data-stu-id="e60ea-123">What do I need to do to prepare for this change</span></span>

<span data-ttu-id="e60ea-124">Se sua organização atualmente envia anexos criptografados para destinatários que exigem o aplicativo Visualizador OME, você deve atualizar sua documentação e recursos de treinamento.</span><span class="sxs-lookup"><span data-stu-id="e60ea-124">If your organization currently sends encrypted attachments to recipients that require the OME Viewer app, you should update your documentation and training resources.</span></span>
  
<span data-ttu-id="e60ea-125">Recomendamos atualizar as regras de fluxo de email existentes Exchange para usar a versão atual do OME para que sua organização possa aproveitar os recursos novos e aprimorados.</span><span class="sxs-lookup"><span data-stu-id="e60ea-125">We recommend updating existing Exchange mail flow rules to use the current version of OME so that your organization can take advantage of the new and improved capabilities.</span></span> <span data-ttu-id="e60ea-126">Depois de configurar os novos recursos OME, os destinatários não precisarão do aplicativo visualizador OME para ler mensagens criptografadas em dispositivos móveis.</span><span class="sxs-lookup"><span data-stu-id="e60ea-126">Once you have set up the new OME capabilities, recipients won't need the OME Viewer app to read encrypted messages on mobile devices.</span></span>
  
<span data-ttu-id="e60ea-127">A Microsoft recomenda que você faça um plano para mover para os novos recursos OME assim que for razoável para sua organização.</span><span class="sxs-lookup"><span data-stu-id="e60ea-127">Microsoft recommends that you make a plan to move to the new OME capabilities as soon as it is reasonable for your organization.</span></span> <span data-ttu-id="e60ea-128">Para obter instruções, [consulte Set up new Criptografia de Mensagens do Office 365 capabilities](set-up-new-message-encryption-capabilities.md).</span><span class="sxs-lookup"><span data-stu-id="e60ea-128">For instructions, see [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md).</span></span> <span data-ttu-id="e60ea-129">Se você quiser saber mais sobre como os novos recursos funcionam primeiro, [consulte Criptografia de Mensagens do Office 365](ome.md).</span><span class="sxs-lookup"><span data-stu-id="e60ea-129">If you want to find out more about how the new capabilities work first, see [Office 365 Message Encryption](ome.md).</span></span>
  

