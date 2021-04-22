---
title: Solucionar problemas de licença do Microsoft Defender para Ponto de Extremidade no Mac
description: Solucionar problemas de licença no Microsoft Defender para Ponto de Extremidade no Mac.
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, performance
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: e8084fab434246a5c9f12af40872ade66e6fa163
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934256"
---
# <a name="troubleshoot-license-issues-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="ba5bc-104">Solucionar problemas de licença do Microsoft Defender para Ponto de Extremidade no macOS</span><span class="sxs-lookup"><span data-stu-id="ba5bc-104">Troubleshoot license issues for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="ba5bc-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="ba5bc-105">**Applies to:**</span></span>

- [<span data-ttu-id="ba5bc-106">Microsoft Defender para Ponto de Extremidade no macOS</span><span class="sxs-lookup"><span data-stu-id="ba5bc-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="ba5bc-107">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="ba5bc-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ba5bc-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ba5bc-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="ba5bc-109">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="ba5bc-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ba5bc-110">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="ba5bc-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="ba5bc-111">Enquanto você estiver passando pelo Microsoft Defender para Ponto de Extremidade no [macOS](microsoft-defender-endpoint-mac.md) e teste de implantação [manual](mac-install-manually.md) ou em um PoC (Proof Of Concept), você pode obter o seguinte erro:</span><span class="sxs-lookup"><span data-stu-id="ba5bc-111">While you are going through [Microsoft Defender for Endpoint on macOS](microsoft-defender-endpoint-mac.md) and [Manual deployment](mac-install-manually.md) testing or a Proof Of Concept (PoC), you might get the following error:</span></span>

![Imagem de erro de licença](images/no-license-found.png)

<span data-ttu-id="ba5bc-113&quot;>**Mensagem:**</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;ba5bc-113&quot;>**Message:**</span></span> 

<span data-ttu-id=&quot;ba5bc-114&quot;>Nenhuma licença encontrada</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;ba5bc-114&quot;>No license found</span></span>

<span data-ttu-id=&quot;ba5bc-115&quot;>Parece que sua organização não tem uma licença para assinatura do Microsoft 365 Enterprise.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;ba5bc-115&quot;>Looks like your organization does not have a license for Microsoft 365 Enterprise subscription.</span></span>

<span data-ttu-id=&quot;ba5bc-116&quot;>Entre em contato com o administrador para obter ajuda.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;ba5bc-116&quot;>Contact your administrator for help.</span></span>

<span data-ttu-id=&quot;ba5bc-117&quot;>**Causa:**</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;ba5bc-117&quot;>**Cause:**</span></span> 

<span data-ttu-id=&quot;ba5bc-118&quot;>Você implantou e/ou instalou o Microsoft Defender para Ponto de Extremidade no pacote macOS (&quot;Baixar pacote de instalação") mas pode ter executado o script de configuração ("Baixar pacote de integração").</span><span class="sxs-lookup"><span data-stu-id="ba5bc-118">You deployed and/or installed the Microsoft Defender for Endpoint on macOS package ("Download installation package") but you might have run the configuration script ("Download onboarding package").</span></span>

<span data-ttu-id="ba5bc-119">**Solução:**</span><span class="sxs-lookup"><span data-stu-id="ba5bc-119">**Solution:**</span></span>

<span data-ttu-id="ba5bc-120">Siga as instruções MicrosoftDefenderATPOnboardingMacOs.py documentadas aqui: [Configuração do cliente](mac-install-manually.md#client-configuration)</span><span class="sxs-lookup"><span data-stu-id="ba5bc-120">Follow the MicrosoftDefenderATPOnboardingMacOs.py instructions documented here: [Client configuration](mac-install-manually.md#client-configuration)</span></span>

