---
title: Monitorar a conectividade do Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 8/4/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 53cdb60c-a6b2-4848-b3ff-e7b75dc3fd1f
description: Neste artigo, você aprenderá sobre as ferramentas e técnicas que você pode usar para monitorar e manter a conectividade do Microsoft 365.
ms.openlocfilehash: db3811b70f91efb9fd1e9f023df12d0852ce0189
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920771"
---
# <a name="monitor-microsoft-365-connectivity"></a><span data-ttu-id="9d8a6-103">Monitorar a conectividade do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9d8a6-103">Monitor Microsoft 365 connectivity</span></span>

<span data-ttu-id="9d8a6-104">Depois de ter implantado o Microsoft 365, você pode manter a conectividade do Microsoft 365 usando algumas das ferramentas e técnicas abaixo.</span><span class="sxs-lookup"><span data-stu-id="9d8a6-104">Once you've deployed Microsoft 365, you can maintain Microsoft 365 connectivity using some of the tools and techniques below.</span></span> <span data-ttu-id="9d8a6-105">Você vai querer entender as diretrizes oficiais de Continuidade e [Saúde](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity) do Serviço, bem como nossas Práticas Recomendadas para usar [o Microsoft 365 em uma rede lenta.](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166)</span><span class="sxs-lookup"><span data-stu-id="9d8a6-105">You'll want to understand the official [Service Health and Continuity](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity) guidelines as well as our [Best practices for using Microsoft 365 on a slow network](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166).</span></span> <span data-ttu-id="9d8a6-106">Você também vai querer pegar o aplicativo de administração do [Microsoft 365](https://blogs.office.com/2015/03/13/administer-on-the-go-with-the-updated-office-365-admin-app/) e marcar nosso [Microsoft 365 para](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791)empresas - Ajuda do administrador .</span><span class="sxs-lookup"><span data-stu-id="9d8a6-106">You'll also want to grab the [Microsoft 365 admin app](https://blogs.office.com/2015/03/13/administer-on-the-go-with-the-updated-office-365-admin-app/) and bookmark our [Microsoft 365 for business - Admin Help](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791).</span></span>
  
## <a name="monitoring-microsoft-365-connectivity"></a><span data-ttu-id="9d8a6-107">Monitorando a conectividade do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9d8a6-107">Monitoring Microsoft 365 Connectivity</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="9d8a6-108">**Recebendo notificado dos novos pontos de extremidade do Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="9d8a6-108">**Getting notified of new Microsoft 365 endpoints**</span></span> <br/> |<span data-ttu-id="9d8a6-109">Se você estiver gerenciando pontos de extremidade do [Microsoft 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a), receberá notificações quando publicarmos novos pontos de extremidade, você pode assinar nosso feed RSS usando seu leitor RSS favorito.</span><span class="sxs-lookup"><span data-stu-id="9d8a6-109">If you're [Managing Microsoft 365 endpoints](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a), you'll want to receive notifications when we publish new endpoints, you can subscribe to our RSS feed using your favorite RSS reader.</span></span> <span data-ttu-id="9d8a6-110">Veja como se inscrever [por meio do Outlook](https://go.microsoft.com/fwlink/p/?LinkId=532416) ou você pode enviar as atualizações de feed [RSS por email para você.](https://go.microsoft.com/fwlink/p/?LinkId=532417)</span><span class="sxs-lookup"><span data-stu-id="9d8a6-110">Here is how to [subscribe via Outlook](https://go.microsoft.com/fwlink/p/?LinkId=532416) or you can [have the RSS feed updates emailed to you](https://go.microsoft.com/fwlink/p/?LinkId=532417).</span></span>  <br/> |
|<span data-ttu-id="9d8a6-111">**Usar o System Center para monitorar o Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="9d8a6-111">**Use System Center to Monitor Microsoft 365**</span></span> <br/> |<span data-ttu-id="9d8a6-112">Se você estiver usando o Microsoft System Center, poderá baixar o [System Center Management Pack para Office 365](https://www.microsoft.com/download/details.aspx?id=43708) para começar a monitorar o Microsoft 365 hoje.</span><span class="sxs-lookup"><span data-stu-id="9d8a6-112">If you're using Microsoft System Center, you can download the [System Center Management Pack for Office 365](https://www.microsoft.com/download/details.aspx?id=43708) to begin monitoring Microsoft 365 today.</span></span> <span data-ttu-id="9d8a6-113">Para obter orientações mais detalhadas, consulte o guia de operações do pacote de gerenciamento ou este blog poste Monitoramento [do Office365 usando o System Center Operations Manager](https://blogs.msdn.com/b/mvpawardprogram/archive/2015/07/08/office365-monitoring-using-system-centre-operations-manager.aspx)</span><span class="sxs-lookup"><span data-stu-id="9d8a6-113">For more detailed guidance, please see the management pack operations guide or this blog post [Office365 Monitoring using System Centre Operations Manager](https://blogs.msdn.com/b/mvpawardprogram/archive/2015/07/08/office365-monitoring-using-system-centre-operations-manager.aspx)</span></span> <br/> |
|<span data-ttu-id="9d8a6-114">**Monitorar a integridade do Azure ExpressRoute**</span><span class="sxs-lookup"><span data-stu-id="9d8a6-114">**Monitoring the health of Azure ExpressRoute**</span></span> <br/> |<span data-ttu-id="9d8a6-115">Se você estiver se conectando ao Microsoft 365 usando o Azure ExpressRoute para o Microsoft 365, você vai querer garantir que esteja usando o Painel de Saúde do Serviço do Microsoft 365, bem como o Azure [Reducing troubleshooting time with Azure Resource health](https://azure.microsoft.com/blog/reduce-troubleshooting-time-with-azure-resource-health/)</span><span class="sxs-lookup"><span data-stu-id="9d8a6-115">If you are connecting to Microsoft 365 using Azure ExpressRoute for Microsoft 365, you'll want to ensure that you're using both the Microsoft 365 Service Health Dashboard as well as the Azure [Reducing troubleshooting time with Azure Resource health](https://azure.microsoft.com/blog/reduce-troubleshooting-time-with-azure-resource-health/)</span></span> <br/> |
|<span data-ttu-id="9d8a6-116">**Usar o Azure AD Connect Health com o AD FS**</span><span class="sxs-lookup"><span data-stu-id="9d8a6-116">**Using Azure AD Connect Health with AD FS**</span></span> <br/> |<span data-ttu-id="9d8a6-117">Se você estiver usando o AD FS para um único Sign-On com o Microsoft 365, você vai querer começar a usar o [Azure AD Connect Health](/azure/active-directory/hybrid/how-to-connect-health-adfs)para monitorar sua infraestrutura do AD FS.</span><span class="sxs-lookup"><span data-stu-id="9d8a6-117">If you're using AD FS for Single Sign-On with Microsoft 365, you'll want to begin [using Azure AD Connect Health to monitor your AD FS infrastructure](/azure/active-directory/hybrid/how-to-connect-health-adfs).</span></span>  <br/> |
|<span data-ttu-id="9d8a6-118">**Monitorar programaticamente o Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="9d8a6-118">**Programmatically monitor Microsoft 365**</span></span> <br/> |<span data-ttu-id="9d8a6-119">Consulte nossas diretrizes sobre a API de Gerenciamento [do Microsoft 365.](/office/office-365-management-api/office-365-management-apis-overview)</span><span class="sxs-lookup"><span data-stu-id="9d8a6-119">Refer to our guidance on the [Microsoft 365 Management API](/office/office-365-management-api/office-365-management-apis-overview).</span></span>  <br/> |

<span data-ttu-id="9d8a6-120">Aqui está um link curto que você pode usar para voltar: [https://aka.ms/monitorconnectivity365]()</span><span class="sxs-lookup"><span data-stu-id="9d8a6-120">Here's a short link you can use to come back: [https://aka.ms/monitorconnectivity365]()</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="9d8a6-121">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="9d8a6-121">Related topics</span></span>

[<span data-ttu-id="9d8a6-122">Configurar serviços e aplicativos do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="9d8a6-122">Configure Microsoft 365 Enterprise services and applications</span></span>](configure-services-and-applications.md)
  
[<span data-ttu-id="9d8a6-123">Preparar sua organização para o Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="9d8a6-123">Get your organization ready for Microsoft 365 Enterprise</span></span>](get-your-organization-ready-for-office-365.md)
  
[<span data-ttu-id="9d8a6-124">Planejamento de rede e ajuste de desempenho para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9d8a6-124">Network planning and performance tuning for Microsoft 365</span></span>](network-planning-and-performance.md)
  
[<span data-ttu-id="9d8a6-125">Integração do Microsoft 365 com ambientes locais</span><span class="sxs-lookup"><span data-stu-id="9d8a6-125">Microsoft 365 integration with on-premises environments</span></span>](microsoft-365-integration.md)
  
[<span data-ttu-id="9d8a6-126">Gerenciando pontos de extremidade do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9d8a6-126">Managing Microsoft 365 endpoints</span></span>](managing-office-365-endpoints.md)