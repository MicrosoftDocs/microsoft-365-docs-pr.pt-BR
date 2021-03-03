---
title: Etapa 4. Migração para seu Microsoft 365 para locatários corporativos
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
- tenant-management
- m365solution-scenario
ms.custom:
- Ent_Solutions
description: Migre seus dispositivos Windows, aplicativos cliente do Office e servidores do Office para seus locatários do Microsoft 365.
ms.openlocfilehash: 85f1c0d927b881c4d1526ce538ae54f5954a0664
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406355"
---
# <a name="step-4-migration-for-your-microsoft-365-for-enterprise-tenants"></a><span data-ttu-id="5037b-104">Etapa 4.</span><span class="sxs-lookup"><span data-stu-id="5037b-104">Step 4.</span></span> <span data-ttu-id="5037b-105">Migração para seu Microsoft 365 para locatários corporativos</span><span class="sxs-lookup"><span data-stu-id="5037b-105">Migration for your Microsoft 365 for enterprise tenants</span></span>

<span data-ttu-id="5037b-106">A maioria das organizações corporativas tem um ambiente heterogêneo que inclui várias versões de sistemas operacionais, software cliente e software de servidor.</span><span class="sxs-lookup"><span data-stu-id="5037b-106">Most enterprise organizations have a heterogeneous environment that includes multiple releases of operating systems, client software, and server software.</span></span> <span data-ttu-id="5037b-107">O Microsoft 365 para empresas inclui as versões mais seguras dos principais componentes da infraestrutura de TI.</span><span class="sxs-lookup"><span data-stu-id="5037b-107">Microsoft 365 for enterprise includes the most secure versions of the key components of your IT infrastructure.</span></span> <span data-ttu-id="5037b-108">Ele também inclui recursos de produtividade projetados para tirar proveito das tecnologias de nuvem.</span><span class="sxs-lookup"><span data-stu-id="5037b-108">It also includes productivity features that are designed to take advantage of cloud technologies.</span></span>

<span data-ttu-id="5037b-109">Para maximizar o valor de negócios do Microsoft 365 para o pacote de produtos integrados da empresa, comece a planejar e implementar uma estratégia para migrar essas versões:</span><span class="sxs-lookup"><span data-stu-id="5037b-109">To maximize the business value of the Microsoft 365 for enterprise integrated suite of products, begin planning and implementing a strategy to migrate these releases:</span></span>

| <span data-ttu-id="5037b-110">De</span><span class="sxs-lookup"><span data-stu-id="5037b-110">From</span></span> | <span data-ttu-id="5037b-111">Para</span><span class="sxs-lookup"><span data-stu-id="5037b-111">To</span></span> |
|:-------|:-----|
| <span data-ttu-id="5037b-112">Windows 7 e Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="5037b-112">Windows 7 and Windows 8.1</span></span> | <span data-ttu-id="5037b-113">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="5037b-113">Windows 10 Enterprise</span></span> |
| <span data-ttu-id="5037b-114">Produtos do cliente do Office instalados nos dispositivos do seu funcionário</span><span class="sxs-lookup"><span data-stu-id="5037b-114">Office client products installed on your worker's devices</span></span> | <span data-ttu-id="5037b-115">Microsoft 365 Apps para empresas</span><span class="sxs-lookup"><span data-stu-id="5037b-115">Microsoft 365 Apps for enterprise</span></span> |
| <span data-ttu-id="5037b-116">Produtos do servidor do Office instalados em servidores locais</span><span class="sxs-lookup"><span data-stu-id="5037b-116">Office server products installed on on-premises servers</span></span> | <span data-ttu-id="5037b-117">Seus serviços equivalentes baseados em nuvem no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5037b-117">Their equivalent cloud-based services in Microsoft 365</span></span> |
|  |  |

## <a name="migrating-to-windows-10"></a><span data-ttu-id="5037b-118">Migrando para o Windows 10</span><span class="sxs-lookup"><span data-stu-id="5037b-118">Migrating to Windows 10</span></span>

<span data-ttu-id="5037b-119">Cada licença do Microsoft 365 para empresas inclui uma licença para o Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="5037b-119">Each Microsoft 365 for enterprise license includes a license for Windows 10 Enterprise.</span></span> <span data-ttu-id="5037b-120">Para migrar seus dispositivos que executem o Windows 7 ou o Windows 8.1, você pode fazer uma atualização in-locar.</span><span class="sxs-lookup"><span data-stu-id="5037b-120">To migrate your devices that run Windows 7 or Windows 8.1, you can do an in-place upgrade.</span></span> <span data-ttu-id="5037b-121">O suporte terminou para o Windows 7 em *14 de janeiro de 2020*.</span><span class="sxs-lookup"><span data-stu-id="5037b-121">Support ended for Windows 7 on *January 14, 2020*.</span></span> 

<span data-ttu-id="5037b-122">Para obter métodos adicionais de instalação do Windows 10 Enterprise além de uma atualização in-locar, consulte Cenários de implantação [do Windows 10.](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios)</span><span class="sxs-lookup"><span data-stu-id="5037b-122">For additional methods of installing Windows 10 Enterprise beyond an in-place upgrade, see [Windows 10 deployment scenarios](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios).</span></span> <span data-ttu-id="5037b-123">Você também pode [planejar a implantação do Windows 10](https://aka.ms/planforwin10deployment) por conta própria.</span><span class="sxs-lookup"><span data-stu-id="5037b-123">You can also [plan for Windows 10 deployment](https://aka.ms/planforwin10deployment) on your own.</span></span>

## <a name="migrating-to-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="5037b-124">Migrando para o Microsoft 365 Apps para empresas</span><span class="sxs-lookup"><span data-stu-id="5037b-124">Migrating to Microsoft 365 Apps for enterprise</span></span>

<span data-ttu-id="5037b-125">O Microsoft 365 para empresas inclui o Microsoft 365 Apps para empresas, uma versão dos produtos cliente do Office (Word, PowerPoint, Excel e Outlook) que é instalado e atualizado a partir da nuvem da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5037b-125">Microsoft 365 for enterprise includes Microsoft 365 Apps for enterprise, a version of the Office client products (Word, PowerPoint, Excel, and Outlook) that is installed and updated from the Microsoft cloud.</span></span> <span data-ttu-id="5037b-126">Para obter mais informações, consulte [About Microsoft 365 Apps for enterprise](https://docs.microsoft.com/deployoffice/about-microsoft-365-apps).</span><span class="sxs-lookup"><span data-stu-id="5037b-126">For more information, see [About Microsoft 365 Apps for enterprise](https://docs.microsoft.com/deployoffice/about-microsoft-365-apps).</span></span>

<span data-ttu-id="5037b-127">Em vez de manter seus computadores atualizados para o Office 2019 ou versões anteriores, tome as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="5037b-127">Rather than keeping your computers current for Office 2019 or older versions, take the following steps:</span></span>

1. <span data-ttu-id="5037b-128">Obter e atribuir uma licença do Microsoft 365 para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="5037b-128">Get and assign a Microsoft 365 license for your users.</span></span>
2. <span data-ttu-id="5037b-129">Desinstale o Office 2013 ou o Office 2016 em seus computadores.</span><span class="sxs-lookup"><span data-stu-id="5037b-129">Uninstall Office 2013 or Office 2016 on their computers.</span></span>
3. <span data-ttu-id="5037b-130">Instale o Microsoft 365 Apps para empresas, individualmente ou durante uma implantação de IT.</span><span class="sxs-lookup"><span data-stu-id="5037b-130">Install Microsoft 365 Apps for enterprise, either individually or during an IT rollout.</span></span> <span data-ttu-id="5037b-131">Para obter mais informações, consulte [Guia de implantação para Aplicativos do Microsoft 365.](https://docs.microsoft.com/deployoffice/deployment-guide-microsoft-365-apps)</span><span class="sxs-lookup"><span data-stu-id="5037b-131">For more information, see [Deployment guide for Microsoft 365 Apps](https://docs.microsoft.com/deployoffice/deployment-guide-microsoft-365-apps).</span></span>

<span data-ttu-id="5037b-132">O Microsoft 365 Apps for enterprise instala atualizações de segurança e novas atualizações de recursos automaticamente e pode aproveitar os serviços baseados em nuvem no Microsoft 365 para aumentar a segurança e a produtividade.</span><span class="sxs-lookup"><span data-stu-id="5037b-132">Microsoft 365 Apps for enterprise installs both security updates and new feature updates automatically and can take advantage of cloud-based services in Microsoft 365 for enhanced security and productivity.</span></span>

## <a name="migrating-on-premises-servers-and-data-to-microsoft-365"></a><span data-ttu-id="5037b-133">Migrando servidores e dados locais para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5037b-133">Migrating on-premises servers and data to Microsoft 365</span></span>

<span data-ttu-id="5037b-134">O Microsoft 365 para empresas inclui versões baseadas em nuvem dos serviços de servidor do Office que usam algumas das mesmas ferramentas que as versões locais do software do servidor do Office, como navegadores da Web e o cliente do Outlook.</span><span class="sxs-lookup"><span data-stu-id="5037b-134">Microsoft 365 for enterprise includes cloud-based versions of Office server services that use some of the same tools as on-premises versions of Office server software, such as web browsers and the Outlook client.</span></span> <span data-ttu-id="5037b-135">Esses serviços baseados em nuvem são atualizados automaticamente para segurança e novos recursos.</span><span class="sxs-lookup"><span data-stu-id="5037b-135">These cloud-based services are automatically updated for security and new features.</span></span> <span data-ttu-id="5037b-136">Após a migração, seu departamento de IT pode economizar o tempo necessário para manter e atualizar servidores locais.</span><span class="sxs-lookup"><span data-stu-id="5037b-136">After migration, your IT department can save the time it takes to maintain and update on-premises servers.</span></span>

<span data-ttu-id="5037b-137">Use os seguintes recursos para obter informações sobre como migrar usuários e dados para cargas de trabalho específicas do Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="5037b-137">Use the following resources for information about migrating users and data for specific Microsoft 365 workloads:</span></span>

- [<span data-ttu-id="5037b-138">Mover caixas de correio de caixas de correio locais Exchange Server para o Exchange Online</span><span class="sxs-lookup"><span data-stu-id="5037b-138">Move mailboxes from on-premises Exchange Server to Exchange Online</span></span>](https://docs.microsoft.com/exchange/hybrid-deployment/move-mailboxes)
- [<span data-ttu-id="5037b-139">Migrar dados do SharePoint Do SharePoint Server para o SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="5037b-139">Migrate SharePoint data from SharePoint Server to SharePoint Online</span></span>](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online)
- [<span data-ttu-id="5037b-140">Migrar o Skype for Business Online para o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5037b-140">Migrate Skype for Business Online to Microsoft Teams</span></span>](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)

## <a name="transition-your-entire-organization"></a><span data-ttu-id="5037b-141">Transição para toda a organização</span><span class="sxs-lookup"><span data-stu-id="5037b-141">Transition your entire organization</span></span>

<span data-ttu-id="5037b-142">Para obter uma imagem melhor de como mover toda a organização para os produtos e serviços no Microsoft 365 para empresas, baixe este cartaz de transição:</span><span class="sxs-lookup"><span data-stu-id="5037b-142">To get a better picture of how to move your entire organization to the products and services in Microsoft 365 for enterprise, download this transition poster:</span></span>

<span data-ttu-id="5037b-143">[![Imagem mostrando o cartaz Transição para o Microsoft 365.](../media/microsoft-365-overview/transition-org-to-m365.png)](https://download.microsoft.com/download/2/c/7/2c7bcc04-aae3-4604-9707-1ffff66b9851/transition-org-to-m365.pdf)</span><span class="sxs-lookup"><span data-stu-id="5037b-143">[![Image showing the Transition to Microsoft 365 poster.](../media/microsoft-365-overview/transition-org-to-m365.png)](https://download.microsoft.com/download/2/c/7/2c7bcc04-aae3-4604-9707-1ffff66b9851/transition-org-to-m365.pdf)</span></span>

<span data-ttu-id="5037b-144">Esse pôster de duas páginas é uma maneira rápida de fazer o inventário da infraestrutura existente.</span><span class="sxs-lookup"><span data-stu-id="5037b-144">This two-page poster is a quick way to inventory your existing infrastructure.</span></span> <span data-ttu-id="5037b-145">Use-o para obter orientações para mover para um produto ou serviço no Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="5037b-145">Use it to get guidance for moving to a product or service in Microsoft 365 for enterprise.</span></span> <span data-ttu-id="5037b-146">Ele mostra produtos do Windows e do Office e outros elementos de infraestrutura e segurança, como gerenciamento de dispositivos, proteção contra identidade e ameaças e proteção e conformidade de informações.</span><span class="sxs-lookup"><span data-stu-id="5037b-146">It shows Windows and Office products and other infrastructure and security elements such as device management, identity and threat protection, and information protection and compliance.</span></span>

## <a name="results-of-step-4"></a><span data-ttu-id="5037b-147">Resultados da Etapa 4</span><span class="sxs-lookup"><span data-stu-id="5037b-147">Results of Step 4</span></span>

<span data-ttu-id="5037b-148">Para migração para seu locatário do Microsoft 365, você determinou:</span><span class="sxs-lookup"><span data-stu-id="5037b-148">For migration for your Microsoft 365 tenant, you have determined:</span></span>

- <span data-ttu-id="5037b-149">Quais dispositivos estão executando o Windows 7 ou Windows 8.1 e o plano para atualizá-los para o Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="5037b-149">Which devices are running Windows 7 or Windows 8.1 and the plan to update them to Windows 10 Enterprise.</span></span>
- <span data-ttu-id="5037b-150">Quais dispositivos estão executando os aplicativos cliente do Office e o plano para atualizá-los para aplicativos do Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="5037b-150">Which devices are running the Office client apps and the plan to update them to Microsoft 365 apps for enterprise.</span></span>
- <span data-ttu-id="5037b-151">Quais serviços de servidor do Office locais devem ser migrados para o equivalente do Microsoft 365 e o plano para migrar eles e seus dados.</span><span class="sxs-lookup"><span data-stu-id="5037b-151">Which on-premises Office server services should be migrated to their Microsoft 365 equivalent and the plan to migrate them and their data.</span></span>

<span data-ttu-id="5037b-152">Aqui está um exemplo de um locatário com uma migração concluída de servidores locais.</span><span class="sxs-lookup"><span data-stu-id="5037b-152">Here is an example of a tenant with a completed migration of on-premises servers.</span></span>

![Exemplo de um locatário com uma migração concluída de servidores locais](../media/tenant-management-overview/tenant-management-tenant-build-step4.png)

<span data-ttu-id="5037b-154">Nesta ilustração, a organização tem:</span><span class="sxs-lookup"><span data-stu-id="5037b-154">In this illustration, the organization has:</span></span>

- <span data-ttu-id="5037b-155">Migrou suas caixas de correio Exchange Server local para o Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="5037b-155">Migrated its on-premises Exchange Server mailboxes to Exchange Online.</span></span>
- <span data-ttu-id="5037b-156">Migrou seus sites e dados locais do SharePoint Server para o SharePoint no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5037b-156">Migrated its on-premises SharePoint Server sites and data to SharePoint in Microsoft 365.</span></span>

## <a name="ongoing-maintenance-for-migration"></a><span data-ttu-id="5037b-157">Manutenção contínua para migração</span><span class="sxs-lookup"><span data-stu-id="5037b-157">Ongoing maintenance for migration</span></span>

<span data-ttu-id="5037b-158">Em uma base contínua, talvez seja necessário:</span><span class="sxs-lookup"><span data-stu-id="5037b-158">On an ongoing basis, you might need to:</span></span>

- <span data-ttu-id="5037b-159">Dependendo do estado da migração de caixa de correio do Exchange, continue a rolar a transição para o Exchange Online para sua organização.</span><span class="sxs-lookup"><span data-stu-id="5037b-159">Depending on the state of your Exchange mailbox migration, continue rolling the transition to Exchange Online out to your organization.</span></span>
- <span data-ttu-id="5037b-160">Dependendo do estado da migração do site local do SharePoint, continue a rolar a transição para o SharePoint no Microsoft 365 para sua organização.</span><span class="sxs-lookup"><span data-stu-id="5037b-160">Depending on the state of your on-premises SharePoint site migration, continue rolling the transition to SharePoint in Microsoft 365 out to your organization.</span></span>

## <a name="next-step"></a><span data-ttu-id="5037b-161">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="5037b-161">Next step</span></span>

<span data-ttu-id="5037b-162">[![Etapa 5. Implantar o gerenciamento de dispositivos e aplicativos](../media/tenant-management-overview/tenant-management-step-grid-device-mgmt.png)](tenant-management-device-management.md)</span><span class="sxs-lookup"><span data-stu-id="5037b-162">[![Step 5. Deploy device and app management](../media/tenant-management-overview/tenant-management-step-grid-device-mgmt.png)](tenant-management-device-management.md)</span></span>

<span data-ttu-id="5037b-163">Continue com [o gerenciamento de dispositivos e aplicativos](tenant-management-device-management.md) para implantar o gerenciamento de dispositivos e aplicativos.</span><span class="sxs-lookup"><span data-stu-id="5037b-163">Continue with [device and app management](tenant-management-device-management.md) to deploy device and app management.</span></span>
