---
title: Qual é o propósito do registro CNAME no Office 365 para MSOID?
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.collection:
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- BCS160
- MET150
- MOE150
ROBOTS: NOINDEX
description: Saiba mais sobre o registro CNAME 'MSOID' no Office 365 que direciona você para o melhor servidor para processos de autenticação, para obter uma resposta mais rápida.
monikerRange: o365-21vianet
ms.openlocfilehash: a1d587abc9db03c9a1f7c5f66711fde3648a0e96
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914301"
---
# <a name="whats-the-purpose-of-the-office-365-cname-record-for-msoid"></a><span data-ttu-id="cdd47-103">Qual é o propósito do registro CNAME no Office 365 para MSOID?</span><span class="sxs-lookup"><span data-stu-id="cdd47-103">What's the purpose of the Office 365 CNAME record for MSOID?</span></span>

 <span data-ttu-id="cdd47-104">Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="cdd47-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
> [!NOTE]
> <span data-ttu-id="cdd47-105">O seguinte aplica-se somente a \*\*Office 365 operado pela 21Vianet.</span><span class="sxs-lookup"><span data-stu-id="cdd47-105">The following only Applies to \*\*Office 365 operated by 21Vianet.</span></span>
  
<span data-ttu-id="cdd47-p101">Você pode estar se perguntando por que precisa adicionar o registro CNAME "MSOID" no Office 365. Este é um registro que deve ser adicionado para todos os domínios personalizados, independentemente de qual assinatura você usa. Por que você precisa disso? É um pouco técnico, mas essencialmente isso ocorre para que você seja direcionado para o melhor servidor melhor para certos processos de autenticação, a fim de receber respostas mais rápidas.</span><span class="sxs-lookup"><span data-stu-id="cdd47-p101">You may wonder why you need to add the "MSOID" CNAME record in Office 365. This is a record that has to be added for all custom domains, no matter which subscription you use. Why do you need it? It's a little technical, but essentially, it's so that you'll be directed to the best server for certain authentication processes, so you'll get faster response.</span></span>
  
<span data-ttu-id="cdd47-p102">Detalhes técnicos: ao executar um aplicativo cliente que funciona com o Office 365, como o Skype for Business Online, o Outlook, o Windows PowerShell ou a ferramenta de sincronização do Microsoft Azure Active Directory, suas credenciais devem ser autenticadas. O Office 365 usa um registro CNAME para apontar para o ponto de extremidade de autenticação adequado ao seu local, o que garante tempos de resposta de autenticação rápidos.</span><span class="sxs-lookup"><span data-stu-id="cdd47-p102">Technical details: When you run a client application that works with Office 365 such as Skype for Business Online, Outlook, Windows PowerShell or Microsoft Azure Active Directory Sync tool, your credentials must be authenticated. Office 365 uses a CNAME record to point to the correct authentication endpoint for your location, which ensures rapid authentication response times.</span></span>
  
<span data-ttu-id="cdd47-p103">Se o registro CNAME estiver faltando em seu domínio, esses aplicativos usarão um ponto final de autenticação padrão nos Estados Unidos, e a autenticação pode ficar mais lenta. Se este registro CNAME não estiver configurado adequadamente, estes aplicativos não poderão fazer a autenticação; por exemplo se houver um erro de digitação em **Pontos de endereçamento**.</span><span class="sxs-lookup"><span data-stu-id="cdd47-p103">If this CNAME record is missing for your domain, these applications will use a default authentication endpoint in the United States, which means authentication might be slower. If this CNAME record isn't configured properly—for example, if you have a typo in the **Points to address**—these applications won't be able to authenticate.</span></span>
  
 <span data-ttu-id="cdd47-114">**Se o Office 365 gerenciar os registros DNS do seu domínio,** O Office 365 configura esse registro CNAME para você.</span><span class="sxs-lookup"><span data-stu-id="cdd47-114">**If Office 365 manages your domain's DNS records,** Office 365 sets up this CNAME record for you.</span></span> 
  
 <span data-ttu-id="cdd47-115">**Se você estiver gerenciando registros DNS para** seu domínio em seu host DNS, crie esse registro por conta própria seguindo as instruções para seu [host DNS](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span><span class="sxs-lookup"><span data-stu-id="cdd47-115">**If you are managing DNS records for your domain at your DNS host,** you create this record yourself by [following the instructions for your DNS host](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span>
  
<span data-ttu-id="cdd47-116">Se você estiver planejando uma implantação do Office 365 e quiser saber mais sobre todos os registros DNS que talvez seja necessário adicionar ou atualizar, leia sobre eles em Referência: Registros do Sistema de Nomes de Domínio Externo para [o Office 365](../../enterprise/external-domain-name-system-records.md).</span><span class="sxs-lookup"><span data-stu-id="cdd47-116">If you're planning an Office 365 deployment and want to learn more about all the DNS records that you may need to add or update, read about them in [Reference: External Domain Name System records for Office 365](../../enterprise/external-domain-name-system-records.md).</span></span>
