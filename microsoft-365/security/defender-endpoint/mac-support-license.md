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
ms.openlocfilehash: 1f8428c2995eec2dece290049eda67a3683b4c1e
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244975"
---
# <a name="troubleshoot-license-issues-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="a743d-104">Solucionar problemas de licença do Microsoft Defender para Ponto de Extremidade no macOS</span><span class="sxs-lookup"><span data-stu-id="a743d-104">Troubleshoot license issues for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a743d-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="a743d-105">**Applies to:**</span></span>

- [<span data-ttu-id="a743d-106">Microsoft Defender para Ponto de Extremidade no macOS</span><span class="sxs-lookup"><span data-stu-id="a743d-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="a743d-107">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="a743d-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a743d-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a743d-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="a743d-109">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="a743d-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a743d-110">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="a743d-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="a743d-111">Enquanto você estiver passando pelo Microsoft Defender para Ponto de Extremidade no [macOS](microsoft-defender-endpoint-mac.md) e teste de implantação [manual](mac-install-manually.md) ou em um PoC (Proof Of Concept), você pode obter o seguinte erro:</span><span class="sxs-lookup"><span data-stu-id="a743d-111">While you are going through [Microsoft Defender for Endpoint on macOS](microsoft-defender-endpoint-mac.md) and [Manual deployment](mac-install-manually.md) testing or a Proof Of Concept (PoC), you might get the following error:</span></span>

![Imagem de erro de licença](images/no-license-found.png)

<span data-ttu-id="a743d-113&quot;>**Mensagem:**</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;a743d-113&quot;>**Message:**</span></span> 

<span data-ttu-id=&quot;a743d-114&quot;>Nenhuma licença encontrada</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;a743d-114&quot;>No license found</span></span>

<span data-ttu-id=&quot;a743d-115&quot;>Parece que sua organização não tem uma licença para Microsoft 365 Enterprise assinatura.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;a743d-115&quot;>Looks like your organization does not have a license for Microsoft 365 Enterprise subscription.</span></span>

<span data-ttu-id=&quot;a743d-116&quot;>Entre em contato com o administrador para obter ajuda.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;a743d-116&quot;>Contact your administrator for help.</span></span>

<span data-ttu-id=&quot;a743d-117&quot;>**Causa:**</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;a743d-117&quot;>**Cause:**</span></span> 

<span data-ttu-id=&quot;a743d-118&quot;>Você implantou e/ou instalou o pacote do Microsoft Defender for Endpoint para macOS (&quot;Baixar pacote de instalação"), mas pode ter executado o script de configuração ("Baixar pacote de integração"), ou não atribuiu uma licença ao usuário.</span><span class="sxs-lookup"><span data-stu-id="a743d-118">You deployed and/or installed the Microsoft Defender for Endpoint for macOS package ("Download installation package"), but you might have run the configuration script ("Download onboarding package"), or you have not assigned a license to the user.</span></span>

<span data-ttu-id="a743d-119">**Solução:**</span><span class="sxs-lookup"><span data-stu-id="a743d-119">**Solution:**</span></span>

<span data-ttu-id="a743d-120">Siga as instruções MicrosoftDefenderATPOnboardingMacOs.py documentadas aqui: [Configuração do cliente](mac-install-manually.md#client-configuration)</span><span class="sxs-lookup"><span data-stu-id="a743d-120">Follow the MicrosoftDefenderATPOnboardingMacOs.py instructions documented here: [Client configuration](mac-install-manually.md#client-configuration)</span></span>
