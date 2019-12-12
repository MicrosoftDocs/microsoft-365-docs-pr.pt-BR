---
title: Perguntas frequentes sobre administração delegada
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 8/28/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: d6a87ce8-2c22-433a-b430-5eab14f6afdc
description: Este tópico fornece perguntas frequentes e suas respostas para parceiros e revendedores Microsoft que desejam executar tarefas de administração delegadas do Office 365, incluindo a habilidade de gerenciar o Exchange Online Protection (EOP) para outros locatários (empresas).
ms.openlocfilehash: 4e2548ebe52926e00269615a436662183ec5bd2a
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/11/2019
ms.locfileid: "39970747"
---
# <a name="delegated-administration-faq"></a><span data-ttu-id="dc33d-103">Perguntas frequentes sobre administração delegada</span><span class="sxs-lookup"><span data-stu-id="dc33d-103">Delegated administration FAQ</span></span>

<span data-ttu-id="dc33d-104">Este tópico fornece perguntas frequentes e suas respostas para parceiros e revendedores Microsoft que desejam executar tarefas de administração delegadas do Office 365, incluindo a habilidade de gerenciar o Exchange Online Protection (EOP) para outros locatários (empresas).</span><span class="sxs-lookup"><span data-stu-id="dc33d-104">This topic provides frequently asked questions and answers for Microsoft partners and resellers who want to perform delegated Office 365 administration tasks, including the ability to manage Exchange Online Protection (EOP) for other tenants (companies).</span></span>

<span data-ttu-id="dc33d-105">**P. Sou revendedor e preciso gerenciar os locatários do meu cliente. Como isso funciona?**</span><span class="sxs-lookup"><span data-stu-id="dc33d-105">**Q. I'm a reseller and I need to manage my customer's tenants; how does this work?**</span></span>

<span data-ttu-id="dc33d-106">R.</span><span class="sxs-lookup"><span data-stu-id="dc33d-106">A.</span></span> <span data-ttu-id="dc33d-107">Se você for um parceiro da Microsoft ou revendedor e se inscrever em um Microsoft Advisor, você pode solicitar permissão para administrar o locatário dentro do centro de administração.</span><span class="sxs-lookup"><span data-stu-id="dc33d-107">If you are a Microsoft partner or reseller, and you've signed up to be a Microsoft advisor, you can request permission to administer their tenant within the admin center.</span></span> <span data-ttu-id="dc33d-108">Isso é conhecido como administração delegada e permite que você gerencie os locatários do Office 365 (incluindo configurações de EOP) como se você fosse um administrador dentro da organização deles.</span><span class="sxs-lookup"><span data-stu-id="dc33d-108">This is known as delegated administration, and it allows you to manage their Office 365 tenant (including EOP settings) as if you were an administrator within their organization.</span></span> <span data-ttu-id="dc33d-109">Veja a seguir as etapas para execução da administração delegada:</span><span class="sxs-lookup"><span data-stu-id="dc33d-109">The steps for performing delegated administration are as follows:</span></span>

1. <span data-ttu-id="dc33d-110">Inscreva-se para ser um [Consultor do Microsoft Office 365](https://aka.ms/cloudbenefits).</span><span class="sxs-lookup"><span data-stu-id="dc33d-110">Sign up to be a [Microsoft Office 365 Advisor](https://aka.ms/cloudbenefits).</span></span>

2. <span data-ttu-id="dc33d-p102">Inscreva-se para a administração delegada do Office 365. Para que você possa começar a administrar a conta de um cliente, ele deverá autorizá-lo como um administrador delegado. Para obter a aprovação dele, é necessário [enviar primeiro uma oferta para administração delegada](https://support.office.com/article/26530dc0-ebba-415b-86b1-b55bc06b073e). (Você também pode oferecer posteriormente a administração delegada ao seu cliente.)</span><span class="sxs-lookup"><span data-stu-id="dc33d-p102">Sign up for Office 365 delegated administration. Before you can start administering a customer's account, they must authorize you as a delegated administrator. To obtain their approval, you first [send them an offer for delegated administration](https://support.office.com/article/26530dc0-ebba-415b-86b1-b55bc06b073e). (You can also offer delegated administration to your customer at a later time.)</span></span>

3. <span data-ttu-id="dc33d-115">Crie a conta de administração delegada usando as etapas em [Adicionar, alterar ou excluir um parceiro de supervisor de assinatura](https://docs.microsoft.com/office365/admin/misc/add-partner).</span><span class="sxs-lookup"><span data-stu-id="dc33d-115">Create the delegated admin account using the steps in [Add, change, or delete a subscription advisor partner](https://docs.microsoft.com/office365/admin/misc/add-partner).</span></span>

<span data-ttu-id="dc33d-116">Visite [parceiros: Crie sua empresa e administre sua assinatura de parceiro do office 365](https://support.office.com/article/30dd1681-47e0-4cbc-abfe-a222cd111319) para obter mais informações sobre como configurar a administração delegada do Office 365.</span><span class="sxs-lookup"><span data-stu-id="dc33d-116">Visit [Partners: Build your business and administer your Office 365 partner subscription](https://support.office.com/article/30dd1681-47e0-4cbc-abfe-a222cd111319) for more information about how to set up Office 365 delegated administration.</span></span>

<span data-ttu-id="dc33d-117">**P. Sou um cliente, não é um revendedor, como posso configurar o administrador delegado para meus sublocatários?**</span><span class="sxs-lookup"><span data-stu-id="dc33d-117">**Q. I'm a customer, not a reseller, how can set up delegated administrator for my sub-tenants?**</span></span>

<span data-ttu-id="dc33d-p103">R. A administração delegada só está disponível para parceiros e revendedores no momento. No entanto, fornecemos um script de amostra do Windows PowerShell que ajudará você a aplicar políticas aos seus sublocatários (empresas). Para obter mais informações, consulte [Amostra de script para aplicação de configurações de EOP a vários locatários](sample-script-for-applying-eop-settings-to-multiple-tenants.md).</span><span class="sxs-lookup"><span data-stu-id="dc33d-p103">A. Delegated administration is only available for resellers and partners at this time. However, we've provided a sample Windows PowerShell script that will help you apply policies to your sub-tenants (companies). For more information, see [Sample script for applying EOP settings to multiple tenants](sample-script-for-applying-eop-settings-to-multiple-tenants.md).</span></span>

<span data-ttu-id="dc33d-122">**P. Posso impedir que a administração de sublocatário modifique minha política?**</span><span class="sxs-lookup"><span data-stu-id="dc33d-122">**Q. Can I prevent my sub-tenant admin from modifying my policy?**</span></span>

<span data-ttu-id="dc33d-p104">R. O Office 365 não tem esse recurso no momento.</span><span class="sxs-lookup"><span data-stu-id="dc33d-p104">A. Office 365 does not currently have this capability.</span></span>

<span data-ttu-id="dc33d-125">**P. Posso obter um relatório consolidado em todos os meus sublocatários?**</span><span class="sxs-lookup"><span data-stu-id="dc33d-125">**Q. Can I get consolidated reporting across all of my sub-tenants?**</span></span>

<span data-ttu-id="dc33d-126">R.</span><span class="sxs-lookup"><span data-stu-id="dc33d-126">A.</span></span> <span data-ttu-id="dc33d-127">O relatório consolidado nas empresas que você gerencia não está disponível para os relatórios do centro de administração do Microsoft 365 no momento.</span><span class="sxs-lookup"><span data-stu-id="dc33d-127">Consolidated reporting across the companies you manage is not available for the Microsoft 365 admin center reports at this time.</span></span> <span data-ttu-id="dc33d-128">No entanto, você pode fazer isso usando [o Microsoft Graph](https://docs.microsoft.com/graph/overview).</span><span class="sxs-lookup"><span data-stu-id="dc33d-128">However, you can do this by using [Microsoft Graph](https://docs.microsoft.com/graph/overview).</span></span>
