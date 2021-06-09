---
title: Aplicativos conectados no Microsoft Defender para Ponto de Extremidade
ms.reviewer: ''
description: Exibir aplicativos parceiros conectados que usam o protocolo OAuth 2.0 padrão para autenticar e fornecer tokens para uso com o Microsoft Defender para APIs de Ponto de Extremidade.
keywords: parceiros, aplicativos, terceiros, conexões, sentinelone, mirante, bitdefender, corrata, morphisec, paloalto, ziften, melhor móvel
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 06ef716e9deee7b20e8615bd22c93130ee18b77f
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845577"
---
# <a name="connected-applications-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="fc9b2-104">Aplicativos conectados no Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="fc9b2-104">Connected applications in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="fc9b2-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="fc9b2-105">**Applies to:**</span></span>
- [<span data-ttu-id="fc9b2-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="fc9b2-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="fc9b2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fc9b2-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="fc9b2-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="fc9b2-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="fc9b2-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="fc9b2-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="fc9b2-110">Aplicativos conectados se integram à plataforma Defender para Ponto de Extremidade usando APIs.</span><span class="sxs-lookup"><span data-stu-id="fc9b2-110">Connected applications integrates with the Defender for Endpoint platform using APIs.</span></span> 

<span data-ttu-id="fc9b2-111">Os aplicativos usam o protocolo OAuth 2.0 padrão para autenticar e fornecer tokens para uso com o Microsoft Defender para APIs de Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="fc9b2-111">Applications use standard OAuth 2.0 protocol to authenticate and provide tokens for use with Microsoft Defender for Endpoint APIs.</span></span>  <span data-ttu-id="fc9b2-112">Além disso, Azure Active Directory aplicativos (Azure AD) permitem que os administradores de locatários deem um controle explícito sobre quais APIs podem ser acessadas usando o aplicativo correspondente.</span><span class="sxs-lookup"><span data-stu-id="fc9b2-112">In addition, Azure Active Directory (Azure AD) applications allow tenant admins to set explicit control over which APIs can be accessed using the corresponding app.</span></span>
 
<span data-ttu-id="fc9b2-113">Você precisará seguir estas etapas [para](/microsoft-365/security/defender-endpoint/apis-intro) usar as APIs com o aplicativo conectado.</span><span class="sxs-lookup"><span data-stu-id="fc9b2-113">You'll need to follow [these steps](/microsoft-365/security/defender-endpoint/apis-intro) to use the APIs with the connected application.</span></span>
 
## <a name="access-the-connected-application-page"></a><span data-ttu-id="fc9b2-114">Acessar a página de aplicativo conectado</span><span class="sxs-lookup"><span data-stu-id="fc9b2-114">Access the connected application page</span></span>
<span data-ttu-id="fc9b2-115">No menu de navegação esquerdo, selecione **Parceiros & APIs**  >  **aplicativos AAD conectados.**</span><span class="sxs-lookup"><span data-stu-id="fc9b2-115">From the left navigation menu, select **Partners & APIs** > **Connected AAD applications**.</span></span>

 
## <a name="view-connected-application-details"></a><span data-ttu-id="fc9b2-116">Exibir detalhes do aplicativo conectado</span><span class="sxs-lookup"><span data-stu-id="fc9b2-116">View connected application details</span></span>
<span data-ttu-id="fc9b2-117">A página Aplicativos Conectados fornece informações sobre os aplicativos do Azure AD conectados ao Microsoft Defender para Ponto de Extremidade em sua organização.</span><span class="sxs-lookup"><span data-stu-id="fc9b2-117">The Connected applications page provides information about the Azure AD applications connected to Microsoft Defender for Endpoint in your organization.</span></span> <span data-ttu-id="fc9b2-118">Você pode revisar o uso dos aplicativos conectados: visto pela última vez, número de solicitações nas últimas 24 horas e solicitar tendências nos últimos 30 dias.</span><span class="sxs-lookup"><span data-stu-id="fc9b2-118">You can review the usage of the connected applications: last seen, number of requests in the past 24 hours, and request trends in the last 30 days.</span></span>

![Imagem de aplicativos conectados](images/connected-apps.png)
 
## <a name="edit-reconfigure-or-delete-a-connected-application"></a><span data-ttu-id="fc9b2-120">Editar, reconfigurar ou excluir um aplicativo conectado</span><span class="sxs-lookup"><span data-stu-id="fc9b2-120">Edit, reconfigure, or delete a connected application</span></span>
<span data-ttu-id="fc9b2-121">O **link Abrir configurações do** aplicativo abre a página de gerenciamento de aplicativos do Azure AD correspondente no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="fc9b2-121">The **Open application settings** link opens the corresponding Azure AD application management page in the Azure portal.</span></span> <span data-ttu-id="fc9b2-122">No portal do Azure, você pode gerenciar permissões, reconfigurar ou excluir os aplicativos conectados.</span><span class="sxs-lookup"><span data-stu-id="fc9b2-122">From the Azure portal, you can manage permissions, reconfigure, or delete the connected applications.</span></span>
