---
title: Visão geral da integração do Microsoft Cloud App Security
ms.reviewer: ''
description: O Microsoft Defender para Ponto de Extremidade se integra ao Cloud App Security encaminhando todas as atividades de rede de aplicativos na nuvem.
keywords: nuvem, aplicativo, rede, visibilidade, uso
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
ms.date: 10/18/2018
ms.technology: mde
ms.openlocfilehash: 5a5a81bde283a9eba4d5db77ed7e4c0b7567abc9
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844725"
---
# <a name="microsoft-cloud-app-security-in-defender-for-endpoint-overview"></a><span data-ttu-id="6ecb7-104">Microsoft Cloud App Security visão geral do Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="6ecb7-104">Microsoft Cloud App Security in Defender for Endpoint overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="6ecb7-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="6ecb7-105">**Applies to:**</span></span>
- [<span data-ttu-id="6ecb7-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="6ecb7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6ecb7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6ecb7-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="6ecb7-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="6ecb7-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6ecb7-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="6ecb7-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="6ecb7-110">Microsoft Cloud App Security (Cloud App Security) é uma solução abrangente que dá visibilidade aos aplicativos e serviços de nuvem, permitindo controlar e limitar o acesso a aplicativos de nuvem, ao mesmo tempo em que aplica os requisitos de conformidade aos dados armazenados na nuvem.</span><span class="sxs-lookup"><span data-stu-id="6ecb7-110">Microsoft Cloud App Security (Cloud App Security) is a comprehensive solution that gives visibility into cloud apps and services by allowing you to control and limit access to cloud apps, while enforcing compliance requirements on data stored in the cloud.</span></span> <span data-ttu-id="6ecb7-111">Para obter mais informações, [consulte Cloud App Security](/cloud-app-security/what-is-cloud-app-security).</span><span class="sxs-lookup"><span data-stu-id="6ecb7-111">For more information, see [Cloud App Security](/cloud-app-security/what-is-cloud-app-security).</span></span>

>[!NOTE]
><span data-ttu-id="6ecb7-112">Esse recurso está disponível com uma licença E5 para Enterprise Mobility + Security [em](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) dispositivos que executam Windows 10 versão 1809 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="6ecb7-112">This feature is available with an E5 license for [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) on devices running Windows 10 version 1809 or later.</span></span>

## <a name="microsoft-defender-for-endpoint-and-cloud-app-security-integration"></a><span data-ttu-id="6ecb7-113">Microsoft Defender para Endpoint e Cloud App Security integração</span><span class="sxs-lookup"><span data-stu-id="6ecb7-113">Microsoft Defender for Endpoint and Cloud App Security integration</span></span> 

<span data-ttu-id="6ecb7-114">Cloud App Security descoberta depende de logs de tráfego na nuvem que estão sendo encaminhados para ele a partir de servidores proxy e firewall corporativos.</span><span class="sxs-lookup"><span data-stu-id="6ecb7-114">Cloud App Security discovery relies on cloud traffic logs being forwarded to it from enterprise firewall and proxy servers.</span></span> <span data-ttu-id="6ecb7-115">O Microsoft Defender for Endpoint se integra ao Cloud App Security coletando e encaminhando todas as atividades de rede de aplicativos de nuvem, fornecendo visibilidade incomparável ao uso do aplicativo na nuvem.</span><span class="sxs-lookup"><span data-stu-id="6ecb7-115">Microsoft Defender for Endpoint integrates with Cloud App Security by collecting and forwarding all cloud app networking activities, providing unparalleled visibility to cloud app usage.</span></span> <span data-ttu-id="6ecb7-116">A funcionalidade de monitoramento é interna no dispositivo, fornecendo cobertura completa da atividade de rede.</span><span class="sxs-lookup"><span data-stu-id="6ecb7-116">The monitoring functionality is built into the device, providing complete coverage of network activity.</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r4yQ]


<span data-ttu-id="6ecb7-117">A integração fornece as seguintes melhorias principais para a descoberta Cloud App Security existente:</span><span class="sxs-lookup"><span data-stu-id="6ecb7-117">The integration provides the following major improvements to the existing Cloud App Security discovery:</span></span> 

- <span data-ttu-id="6ecb7-118">Disponível em todos os lugares – como a atividade de rede é coletada diretamente do ponto de extremidade, ela está disponível onde quer que o dispositivo esteja, na rede corporativa ou fora, pois não depende mais do tráfego roteado pelo firewall corporativo ou servidores proxy.</span><span class="sxs-lookup"><span data-stu-id="6ecb7-118">Available everywhere - Since the network activity is collected directly from the endpoint, it's available wherever the device is, on or off corporate network, as it's no longer depended on traffic routed through the enterprise firewall or proxy servers.</span></span> 

- <span data-ttu-id="6ecb7-119">Funciona fora da caixa, nenhuma configuração necessária - Encaminhar logs de tráfego de nuvem para Cloud App Security requer configuração de servidor proxy e firewall.</span><span class="sxs-lookup"><span data-stu-id="6ecb7-119">Works out of the box, no configuration required - Forwarding cloud traffic logs to Cloud App Security requires firewall and proxy server configuration.</span></span> <span data-ttu-id="6ecb7-120">Com o Defender para Endpoint e Cloud App Security integração, não há nenhuma configuração necessária.</span><span class="sxs-lookup"><span data-stu-id="6ecb7-120">With the Defender for Endpoint and Cloud App Security integration, there's no configuration required.</span></span> <span data-ttu-id="6ecb7-121">Basta a opção Central de Segurança do Microsoft Defender configurações e você pode ir.</span><span class="sxs-lookup"><span data-stu-id="6ecb7-121">Just switch it on in Microsoft Defender Security Center settings and you're good to go.</span></span> 

- <span data-ttu-id="6ecb7-122">Contexto do dispositivo - Os logs de tráfego de nuvem não têm contexto de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6ecb7-122">Device context - Cloud traffic logs lack device context.</span></span> <span data-ttu-id="6ecb7-123">A atividade de rede do Defender for Endpoint é relatada com o contexto do dispositivo (qual dispositivo acessou o aplicativo de nuvem), para que você possa entender exatamente onde (dispositivo) a atividade de rede ocorreu, além de quem (usuário) a realizou.</span><span class="sxs-lookup"><span data-stu-id="6ecb7-123">Defender for Endpoint network activity is reported with the device context (which device accessed the cloud app), so you are able to understand exactly where (device) the network activity took place, in addition to who (user) performed it.</span></span> 

<span data-ttu-id="6ecb7-124">Para obter mais informações sobre descoberta na nuvem, consulte [Trabalhando com aplicativos descobertos.](/cloud-app-security/discovered-apps)</span><span class="sxs-lookup"><span data-stu-id="6ecb7-124">For more information about cloud discovery, see [Working with discovered apps](/cloud-app-security/discovered-apps).</span></span>

## <a name="related-topic"></a><span data-ttu-id="6ecb7-125">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="6ecb7-125">Related topic</span></span>

- [<span data-ttu-id="6ecb7-126">Configurar a integração do Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="6ecb7-126">Configure Microsoft Cloud App Security integration</span></span>](microsoft-cloud-app-security-config.md)
