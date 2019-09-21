---
title: Reprovando o aplicativo visualizador de criptografia de mensagens do Office 365
ms.author: krowley
author: kccross
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
description: No dia 15 de agosto de 2018, iremos remover o aplicativo móvel do Visualizador de criptografia de mensagens do Office 365 (OME) do Android e dos repositórios da Apple. O aplicativo móvel Office 365 Message Encryption Viewer era necessário para ler mensagens de email e anexos que foram criptografados com a versão anterior do OME em telefones Apple e Android. Além de remover o aplicativo OME Viewer, não estamos fazendo outras alterações na versão anterior do OME.
ms.openlocfilehash: 3b5c92d4fa700a1ae8d7b104e33100301cf43506
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37071956"
---
# <a name="deprecating-office-365-message-encryption-viewer-app"></a><span data-ttu-id="f9fb7-105">Reprovando o aplicativo visualizador de criptografia de mensagens do Office 365</span><span class="sxs-lookup"><span data-stu-id="f9fb7-105">Deprecating Office 365 Message Encryption Viewer App</span></span>

<span data-ttu-id="f9fb7-106">No dia 15 de agosto de 2018, removemos o aplicativo móvel do Visualizador de criptografia de mensagens do Office 365 (OME) do Android e dos repositórios da Apple.</span><span class="sxs-lookup"><span data-stu-id="f9fb7-106">On August 15, 2018, we removed the Office 365 Message Encryption (OME) Viewer mobile app from Android and Apple stores.</span></span> <span data-ttu-id="f9fb7-107">O aplicativo móvel Office 365 Message Encryption Viewer era necessário para ler mensagens de email e anexos que foram criptografados com a versão anterior do OME em telefones Apple e Android.</span><span class="sxs-lookup"><span data-stu-id="f9fb7-107">The Office 365 Message Encryption Viewer mobile app was required to read email messages and attachments that were encrypted with the previous version of OME on Apple and Android phones.</span></span> <span data-ttu-id="f9fb7-108">Além de remover o aplicativo OME Viewer, não estamos fazendo outras alterações na versão anterior do OME.</span><span class="sxs-lookup"><span data-stu-id="f9fb7-108">Apart from removing the OME Viewer app, we are not making any other changes to the previous version of OME.</span></span>
  
## <a name="changes-from-august-2018"></a><span data-ttu-id="f9fb7-109">Alterações de agosto de 2018</span><span class="sxs-lookup"><span data-stu-id="f9fb7-109">Changes from August 2018</span></span>

<span data-ttu-id="f9fb7-110">Conforme anunciado em setembro de 2017, lançamos uma nova versão da [criptografia de mensagem do Office 365](https://aka.ms/ome2017) para que os usuários possam enviar mensagens criptografadas e protegidas para qualquer pessoa dentro ou fora da organização, sem a necessidade do aplicativo móvel.</span><span class="sxs-lookup"><span data-stu-id="f9fb7-110">As announced September 2017, we have released a new version of [Office 365 Message Encryption](https://aka.ms/ome2017) so that users can send encrypted and protected messages to anyone inside or outside the organization without the requirement of the mobile app.</span></span> <span data-ttu-id="f9fb7-111">Desde então, adicionamos recursos adicionais:</span><span class="sxs-lookup"><span data-stu-id="f9fb7-111">Since then, we've added additional capabilities:</span></span>
  
- [<span data-ttu-id="f9fb7-112">Modelo somente criptografia</span><span class="sxs-lookup"><span data-stu-id="f9fb7-112">Encrypt-only template</span></span>](https://aka.ms/encryptonly)

- [<span data-ttu-id="f9fb7-113">Controle para descriptografar anexos</span><span class="sxs-lookup"><span data-stu-id="f9fb7-113">Control to decrypt attachments</span></span>](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Admin-control-for-attachments-now-available-in-Office-365/ba-p/204007)
    
<span data-ttu-id="f9fb7-114">Com essa alteração, os usuários não poderão mais baixar o aplicativo móvel do Office 365 Message Encryption Viewer, começando em 1º de agosto.</span><span class="sxs-lookup"><span data-stu-id="f9fb7-114">With this change, users will no longer be able to download the Office 365 Message Encryption Viewer mobile app beginning August 1.</span></span> <span data-ttu-id="f9fb7-115">Como resultado, os destinatários de email podem não conseguir ler mensagens criptografadas com a versão anterior do OME em alguns dispositivos móveis Android e Apple.</span><span class="sxs-lookup"><span data-stu-id="f9fb7-115">As a result, mail recipients may not be able to read messages encrypted with the previous version of OME on some Android and Apple mobile devices.</span></span> <span data-ttu-id="f9fb7-116">No entanto, eles ainda poderão ler essas mensagens em computadores pessoais (por meio de navegadores da área de trabalho).</span><span class="sxs-lookup"><span data-stu-id="f9fb7-116">However, they will still be able to read these messages on personal computers (via desktop browsers).</span></span> <span data-ttu-id="f9fb7-117">Os usuários que já baixaram o aplicativo continuarão a ser capazes de usá-lo.</span><span class="sxs-lookup"><span data-stu-id="f9fb7-117">Users who have already downloaded the app will continue to be able to use it.</span></span>
  
## <a name="why-this-change-was-made"></a><span data-ttu-id="f9fb7-118">Por que essa alteração foi feita</span><span class="sxs-lookup"><span data-stu-id="f9fb7-118">Why this change was made</span></span>

<span data-ttu-id="f9fb7-119">A nova versão do OME não requer mais um aplicativo móvel para ler mensagens de email e anexos protegidos.</span><span class="sxs-lookup"><span data-stu-id="f9fb7-119">The new version of OME no longer requires a mobile app to read protected email messages and attachments.</span></span> <span data-ttu-id="f9fb7-120">Os clientes do Office 365 que usam os novos recursos do OME podem exibir a mensagem protegida no Outlook Mobile e os clientes não-Office 365 podem exibir mensagens protegidas em um navegador.</span><span class="sxs-lookup"><span data-stu-id="f9fb7-120">Office 365 customers using the new OME capabilities can view the protected message in Outlook mobile and non-Office 365 customers can view protected messages in a browser.</span></span>
  
<span data-ttu-id="f9fb7-121">Exigir que os usuários baixem um aplicativo móvel é outro obstáculo para os clientes exibirem mensagens protegidas.</span><span class="sxs-lookup"><span data-stu-id="f9fb7-121">Requiring users to download a mobile app is another hurdle for customers to view protected messages.</span></span> <span data-ttu-id="f9fb7-122">Os novos recursos de criptografia de mensagem do Office 365 oferecem uma experiência móvel melhor.</span><span class="sxs-lookup"><span data-stu-id="f9fb7-122">The new Office 365 Message Encryption capabilities provide a better mobile experience.</span></span>
  
## <a name="can-i-still-use-the-previous-version-of-office-365-message-encryption"></a><span data-ttu-id="f9fb7-123">Ainda posso usar a versão anterior da criptografia de mensagem do Office 365</span><span class="sxs-lookup"><span data-stu-id="f9fb7-123">Can I still use the previous version of Office 365 Message Encryption</span></span>

<span data-ttu-id="f9fb7-124">A versão anterior da criptografia de mensagem do Office 365 não será preterida no momento, no entanto, fizemos melhorias significativas na nova versão da criptografia de mensagem do Office 365, o que facilita a criptografia e os direitos de proteção de dados confidenciais para qualquer pessoa e, em qualquer dispositivo, incluindo a capacidade de os usuários do Office 365 lerem mensagens protegidas diretamente no Outlook (desktop, Mobile e Web).</span><span class="sxs-lookup"><span data-stu-id="f9fb7-124">The previous version of Office 365 Message Encryption will not be deprecated at this time, however, we have made significant enhancements to the new version of Office 365 Message Encryption, which make it easier to encrypt and rights protect sensitive data to anyone and on any device - including the ability for Office 365 users to read protected messages directly in Outlook (desktop, mobile, and web).</span></span> 
  
## <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a><span data-ttu-id="f9fb7-125">O que eu preciso fazer para se preparar para essa alteração</span><span class="sxs-lookup"><span data-stu-id="f9fb7-125">What do I need to do to prepare for this change</span></span>

<span data-ttu-id="f9fb7-126">Se sua organização envia atualmente anexos criptografados para destinatários que exigem o aplicativo visualizador do OME, você deve atualizar a documentação e os recursos de treinamento.</span><span class="sxs-lookup"><span data-stu-id="f9fb7-126">If your organization currently sends encrypted attachments to recipients that require the OME Viewer app, you should update your documentation and training resources.</span></span>
  
<span data-ttu-id="f9fb7-127">Recomendamos a atualização de regras de fluxo de emails existentes do Exchange para usar a versão atual do OME para que sua organização possa aproveitar os recursos novos e aprimorados.</span><span class="sxs-lookup"><span data-stu-id="f9fb7-127">We recommend updating existing Exchange mail flow rules to use the current version of OME so that your organization can take advantage of the new and improved capabilities.</span></span> <span data-ttu-id="f9fb7-128">Depois de configurar os novos recursos do OME, os destinatários não precisarão que o aplicativo do OME Viewer Leia mensagens criptografadas em dispositivos móveis.</span><span class="sxs-lookup"><span data-stu-id="f9fb7-128">Once you have set up the new OME capabilities, recipients won't need the OME Viewer app to read encrypted messages on mobile devices.</span></span>
  
<span data-ttu-id="f9fb7-129">A Microsoft recomenda que você faça um plano para migrar para os novos recursos do OME assim que for razoável para sua organização.</span><span class="sxs-lookup"><span data-stu-id="f9fb7-129">Microsoft recommends that you make a plan to move to the new OME capabilities as soon as it is reasonable for your organization.</span></span> <span data-ttu-id="f9fb7-130">Para obter instruções, consulte [configurar novos recursos de criptografia de mensagem do Office 365](set-up-new-message-encryption-capabilities.md).</span><span class="sxs-lookup"><span data-stu-id="f9fb7-130">For instructions, see [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md).</span></span> <span data-ttu-id="f9fb7-131">Se quiser saber mais sobre como os novos recursos funcionam primeiro, confira criptografia de [mensagem do Office 365](ome.md).</span><span class="sxs-lookup"><span data-stu-id="f9fb7-131">If you want to find out more about how the new capabilities work first, see [Office 365 Message Encryption](ome.md).</span></span>
  

