---
title: Localizar e corrigir problemas após a adição do seu domínio ou de registros DNS
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 40398b0b-bdd0-4afd-ab5e-b5ae6b7990bf
description: Saiba como rastrear quaisquer problemas que você encontrar durante a configuração de um domínio personalizado, certifique-se de que os registros DNS estão definidos corretamente.
ms.openlocfilehash: 786df75f3f8a514e9b3c2a7666d715c9abd082bd
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926385"
---
# <a name="find-and-fix-issues-after-adding-your-domain-or-dns-records"></a><span data-ttu-id="7d0b1-103">Localizar e corrigir problemas após a adição do seu domínio ou de registros DNS</span><span class="sxs-lookup"><span data-stu-id="7d0b1-103">Find and fix issues after adding your domain or DNS records</span></span>

 <span data-ttu-id="7d0b1-104">Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="7d0b1-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="7d0b1-105">Fazer seu domínio se configurar para trabalhar com o Microsoft 365 pode ser um desafio.</span><span class="sxs-lookup"><span data-stu-id="7d0b1-105">Getting your domain set up to work with Microsoft 365 can be challenging.</span></span> <span data-ttu-id="7d0b1-106">É complicado trabalhar com o sistema DNS, e a configuração DNS do seu domínio afeta atividades comerciais importantes, como o email!</span><span class="sxs-lookup"><span data-stu-id="7d0b1-106">The DNS system is nitpicky to work with, and the DNS setup for your domain affects important business activities, like email!</span></span>

> [!NOTE]
> <span data-ttu-id="7d0b1-107">Você pode verificar se há problemas com seu domínio verificando seu status.</span><span class="sxs-lookup"><span data-stu-id="7d0b1-107">You can check for problems with your domain by checking its status.</span></span> <span data-ttu-id="7d0b1-108">Vá para  >  **Domínios da Instalação** e veja as notificações na coluna **Status.**</span><span class="sxs-lookup"><span data-stu-id="7d0b1-108">Go to **Setup** > **Domains** and view the notifications in the **Status** column.</span></span> <span data-ttu-id="7d0b1-109">Se você vir um problema, selecione Mais ações (três pontos) e escolha **Verificar a saúde.**</span><span class="sxs-lookup"><span data-stu-id="7d0b1-109">If you see an issue, select More actions (three dots), and then choose **Check health**.</span></span> <span data-ttu-id="7d0b1-110">O painel que é aberto descreverá todos os problemas que ocorrem com seu domínio.</span><span class="sxs-lookup"><span data-stu-id="7d0b1-110">The pane that opens will describe any issues occurring with your domain.</span></span>
  
## <a name="whats-going-on"></a><span data-ttu-id="7d0b1-111">O que está acontecendo?</span><span class="sxs-lookup"><span data-stu-id="7d0b1-111">What's going on?</span></span>

- [<span data-ttu-id="7d0b1-112">Não é possível verificar seu domínio?</span><span class="sxs-lookup"><span data-stu-id="7d0b1-112">Can't verify your domain?</span></span>](#cant-verify-your-domain)
    
- [<span data-ttu-id="7d0b1-113">O Outlook não está funcionando?</span><span class="sxs-lookup"><span data-stu-id="7d0b1-113">Outlook isn't working?</span></span>](#outlook-isnt-working)
    
- [<span data-ttu-id="7d0b1-114">Os emails de todos foram trocados para o Microsoft 365 e você só queria que seu email mudava?</span><span class="sxs-lookup"><span data-stu-id="7d0b1-114">Everyone's email got switched to Microsoft 365 and you only wanted YOUR email to switch?</span></span>](#everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch)

- [<span data-ttu-id="7d0b1-115">Não é possível confirmar o status da conta sem fins lucrativos ou da escola?</span><span class="sxs-lookup"><span data-stu-id="7d0b1-115">Can't confirm non-profit or school account status?</span></span>](#cant-confirm-non-profit-or-school-account-status)

- [<span data-ttu-id="7d0b1-116">Os serviços não estão funcionando com seu domínio?</span><span class="sxs-lookup"><span data-stu-id="7d0b1-116">Services not working with your domain?</span></span>](#services-not-working-with-your-domain)
    
- [<span data-ttu-id="7d0b1-117">Acessar seu site não está funcionando?</span><span class="sxs-lookup"><span data-stu-id="7d0b1-117">Accessing your website isn't working?</span></span>](#accessing-your-website-isnt-working)

## <a name="cant-verify-your-domain"></a><span data-ttu-id="7d0b1-118">Não consegue verificar o seu domínio?</span><span class="sxs-lookup"><span data-stu-id="7d0b1-118">Can't verify your domain?</span></span>
<span data-ttu-id="7d0b1-119"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="7d0b1-119"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="7d0b1-120">Há alguns motivos comuns para a verificação de domínios não funcionar como deveria:</span><span class="sxs-lookup"><span data-stu-id="7d0b1-120">There are a couple of common reasons that domain verification doesn't work as it should:</span></span>
  
1. <span data-ttu-id="7d0b1-p103">**O valor de registro da verificação não está correto.** Verifique se você copiou e colou o valor exato no registro de verificação TXT no seu host DNS. Um problema comum é não incluir a parte "MS=" no registro. Precisamos disso também!</span><span class="sxs-lookup"><span data-stu-id="7d0b1-p103">**The verification record value isn't quite correct.** Doublecheck that you've copied and pasted the exact value into the TXT verification record at your DNS host. One common issue is not including the "MS=" part of the record. We need that too!</span></span> 
    
2. <span data-ttu-id="7d0b1-125">**O registro não foi salvo.**</span><span class="sxs-lookup"><span data-stu-id="7d0b1-125">**The record hasn't been saved.**</span></span> <span data-ttu-id="7d0b1-126">Em alguns hosts DNS, você pode ter que executar uma etapa extra para salvar o arquivo de zona (local em que o registro DNS é armazenado) para que o registro seja atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="7d0b1-126">At some DNS hosts, you have to take an extra step to save the zone file (where the DNS record is stored) so that it will update across the Internet.</span></span> <span data-ttu-id="7d0b1-127">Verifique se você salvou suas alterações para que o Microsoft 365 possa ver e verificar o registro.</span><span class="sxs-lookup"><span data-stu-id="7d0b1-127">Make sure you've saved your changes so Microsoft 365 can see and verify the record.</span></span> 
    
3. <span data-ttu-id="7d0b1-128">**O registro não foi atualizado na Internet.**</span><span class="sxs-lookup"><span data-stu-id="7d0b1-128">**The record hasn't updated across the Internet.**</span></span> <span data-ttu-id="7d0b1-129">Normalmente, leva apenas alguns minutos para que possamos ver o novo registro, mas ocasionalmente pode levar até algumas horas.</span><span class="sxs-lookup"><span data-stu-id="7d0b1-129">It typically only takes a few minutes for us to be able to see the new record, but occasionally it can take as long as a few hours.</span></span> 
    
## <a name="outlook-isnt-working"></a><span data-ttu-id="7d0b1-130">O Outlook não está funcionando?</span><span class="sxs-lookup"><span data-stu-id="7d0b1-130">Outlook isn't working?</span></span>
<span data-ttu-id="7d0b1-131"><a name="BKMK_OutlookBroken"> </a></span><span class="sxs-lookup"><span data-stu-id="7d0b1-131"><a name="BKMK_OutlookBroken"> </a></span></span>

<span data-ttu-id="7d0b1-132">Se você configurou o registro MX e os outros registros DNS corretamente para o seu domínio, mas o seu email não funciona, deixe-nos ajudá-lo a [corrigir os problemas do Outlook](https://docs.microsoft.com/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues).</span><span class="sxs-lookup"><span data-stu-id="7d0b1-132">If you've set up your MX record and other DNS records correctly for your domain, but mail doesn't work, let us help you [fix your Outlook problems](https://docs.microsoft.com/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues).</span></span>
  
## <a name="everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch"></a><span data-ttu-id="7d0b1-133">Os emails de todos foram trocados para o Microsoft 365 e você só queria que seu email mudava?</span><span class="sxs-lookup"><span data-stu-id="7d0b1-133">Everyone's email got switched to Microsoft 365 and you only wanted YOUR email to switch?</span></span>
<span data-ttu-id="7d0b1-134"><a name="BKMK_EmailSwitched"> </a></span><span class="sxs-lookup"><span data-stu-id="7d0b1-134"><a name="BKMK_EmailSwitched"> </a></span></span>

<span data-ttu-id="7d0b1-135">Quando você adiciona seu domínio ao Microsoft 365, normalmente o registro MX do seu domínio é atualizado (por você ou microsoft 365) para apontar para o Microsoft 365, e todos os emails enviados para esse domínio começarão a chegar no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7d0b1-135">When you add your domain to Microsoft 365, typically your domain's MX record is updated (by you or Microsoft 365) to point to Microsoft 365, and ALL email sent to that domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="7d0b1-136">Certifique-se de ter criado caixas de correio no Microsoft 365 para todos que têm email em seu domínio ANTES de alterar o registro MX.</span><span class="sxs-lookup"><span data-stu-id="7d0b1-136">Make sure you've created mailboxes in Microsoft 365 for everyone who has email on your domain BEFORE you change the MX record.</span></span>
  
<span data-ttu-id="7d0b1-137">E se você não quiser mover emails de todos em seu domínio para o Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="7d0b1-137">What if you don't want to move email for everyone on your domain to Microsoft 365?</span></span> <span data-ttu-id="7d0b1-138">Você pode seguir etapas para [fazer o piloto do Microsoft 365 com apenas alguns endereços de email.](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="7d0b1-138">You can take steps to [pilot Microsoft 365 with just a few email addresses instead](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq).</span></span>
  
## <a name="cant-confirm-non-profit-or-school-account-status"></a><span data-ttu-id="7d0b1-139">Não é possível confirmar o status da conta sem fins lucrativos ou da escola?</span><span class="sxs-lookup"><span data-stu-id="7d0b1-139">Can't confirm non-profit or school account status?</span></span>
<span data-ttu-id="7d0b1-140"><a name="BKMK_validateAcct"> </a></span><span class="sxs-lookup"><span data-stu-id="7d0b1-140"><a name="BKMK_validateAcct"> </a></span></span>

<span data-ttu-id="7d0b1-141">Há alguns cenários em que você só precisa verificar o domínio da sua organização e não configurar nenhum serviço.</span><span class="sxs-lookup"><span data-stu-id="7d0b1-141">There are a couple of scenarios when you just need to verify your organization's domain and not set up any services.</span></span> <span data-ttu-id="7d0b1-142">Por exemplo, para provar ao Microsoft 365 que sua organização se qualifica para uma assinatura escolar.</span><span class="sxs-lookup"><span data-stu-id="7d0b1-142">For example, to prove to Microsoft 365 that your organization qualifies for a school subscription.</span></span>
  
<span data-ttu-id="7d0b1-143">Confira as orientações em Verificar seu domínio do [Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) para comprovar o status de propriedade, instituições sem fins lucrativos ou education ou para ativar o Yammer para garantir que você concluiu todas as etapas necessárias.</span><span class="sxs-lookup"><span data-stu-id="7d0b1-143">Check out the guidance in [Verify your Microsoft 365 domain to prove ownership, nonprofit or education status, or to activate Yammer](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) to make sure you've completed all the required steps.</span></span> <span data-ttu-id="7d0b1-144">É um pouco diferente para cada situação.</span><span class="sxs-lookup"><span data-stu-id="7d0b1-144">It's a little different for each situation.</span></span> 
  
## <a name="services-not-working-with-your-domain"></a><span data-ttu-id="7d0b1-145">Os serviços não estão funcionando com o seu domínio?</span><span class="sxs-lookup"><span data-stu-id="7d0b1-145">Services not working with your domain?</span></span>
<span data-ttu-id="7d0b1-146"><a name="BKMK_Test"> </a></span><span class="sxs-lookup"><span data-stu-id="7d0b1-146"><a name="BKMK_Test"> </a></span></span>

<span data-ttu-id="7d0b1-147">Podemos ajudá-lo a corrigir problemas com a configuração de DNS do seu domínio.</span><span class="sxs-lookup"><span data-stu-id="7d0b1-147">We can help you track down issues with your domain's DNS setup.</span></span> <span data-ttu-id="7d0b1-148">A solução de problemas de domínios no Microsoft 365 mostrará todos os registros que precisam de correção e exatamente para que os registros precisam ser definidos.</span><span class="sxs-lookup"><span data-stu-id="7d0b1-148">The domains troubleshooter in Microsoft 365 will show you any records that need fixing, and exactly what the records need to be set to.</span></span> 

> [!TIP]
> <span data-ttu-id="7d0b1-149">O DNS foi configurado corretamente, mas o email não funciona no Outlook na sua área de trabalho?</span><span class="sxs-lookup"><span data-stu-id="7d0b1-149">Got your DNS set up correctly, but mail doesn't work in Outlook on your desktop?</span></span> <span data-ttu-id="7d0b1-150">Confira os diferentes cenários de fluxo de emails que você pode ter com o [Microsoft 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/mail-flow-best-practices) para garantir que você tenha tudo pronto corretamente para sua empresa.</span><span class="sxs-lookup"><span data-stu-id="7d0b1-150">Check out the [different mail flow scenarios you can have with Microsoft 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/mail-flow-best-practices) to make sure you've got things set up correctly for your business.</span></span> <span data-ttu-id="7d0b1-151">Se preferir, obtenha mais soluções de problemas com email aqui: [Corrigir problemas do Outlook](https://docs.microsoft.com/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues).</span><span class="sxs-lookup"><span data-stu-id="7d0b1-151">Or get more troubleshooting help with email here: [Fix Outlook problems](https://docs.microsoft.com/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues).</span></span> 
  
## <a name="accessing-your-website-isnt-working"></a><span data-ttu-id="7d0b1-152">Não consegue acessar o seu site?</span><span class="sxs-lookup"><span data-stu-id="7d0b1-152">Accessing your website isn't working?</span></span>
<span data-ttu-id="7d0b1-153"><a name="BKMK_Website"> </a></span><span class="sxs-lookup"><span data-stu-id="7d0b1-153"><a name="BKMK_Website"> </a></span></span>

<span data-ttu-id="7d0b1-154">Caso tenha corrigido os problemas de DNS, mas ainda esteja com dificuldades, tente um dos seguintes procedimentos.</span><span class="sxs-lookup"><span data-stu-id="7d0b1-154">If you've fixed any DNS issues and you're still having trouble, try one of the following.</span></span>
  
- <span data-ttu-id="7d0b1-155">As pessoas não conseguem acessar seu site em www.mydomain.com: [Rastrear problemas do site](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)</span><span class="sxs-lookup"><span data-stu-id="7d0b1-155">People can't get to your website at www.mydomain.com: [Track down website issues](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)</span></span>
    
- <span data-ttu-id="7d0b1-156">Você não pode atualizar seu registro A ou CNAME para apontar para seu site: atualizar registros DNS personalizados [no Microsoft 365](../dns/add-or-edit-custom-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="7d0b1-156">You can't update your A record or CNAME record to point to your website: [Update custom DNS records in Microsoft 365](../dns/add-or-edit-custom-dns-records.md)</span></span>

## <a name="related-content"></a><span data-ttu-id="7d0b1-157">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="7d0b1-157">Related content</span></span>

[<span data-ttu-id="7d0b1-158">Solução de problemas: Auditar dados em alteração de domínio verificada</span><span class="sxs-lookup"><span data-stu-id="7d0b1-158">Troubleshoot: Audit data on verified domain change</span></span>](https://docs.microsoft.com/azure/active-directory/reports-monitoring/troubleshoot-audit-data-verified-domain)

    
