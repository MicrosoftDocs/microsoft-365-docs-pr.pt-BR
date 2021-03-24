---
title: Solucionar problemas de licença do Microsoft Defender ATP para Mac
description: Solucionar problemas de licença no Microsoft Defender ATP para Mac.
keywords: microsoft, defender, atp, mac, performance
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
ms.openlocfilehash: 44105ae8d1872c3ecefcf84a5e2efef122849b8c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053952"
---
# <a name="troubleshoot-license-issues-for-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="792d2-104">Solucionar problemas de licença do Microsoft Defender para Ponto de Extremidade para Mac</span><span class="sxs-lookup"><span data-stu-id="792d2-104">Troubleshoot license issues for Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="792d2-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="792d2-105">**Applies to:**</span></span>

- [<span data-ttu-id="792d2-106">Microsoft Defender para Ponto de Extremidade para Mac</span><span class="sxs-lookup"><span data-stu-id="792d2-106">Microsoft Defender for Endpoint for Mac</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="792d2-107">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="792d2-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="792d2-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="792d2-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="792d2-109">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="792d2-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="792d2-110">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="792d2-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="792d2-111">Enquanto você estiver passando pelo [Microsoft Defender para o Ponto](microsoft-defender-endpoint-mac.md) de Extremidade para Mac e teste de implantação [manual](mac-install-manually.md) ou um Teste de Prova de Conceito (PoC), você pode obter o seguinte erro:</span><span class="sxs-lookup"><span data-stu-id="792d2-111">While you are going through [Microsoft Defender for Endpoint for Mac](microsoft-defender-endpoint-mac.md) and [Manual deployment](mac-install-manually.md) testing or a Proof Of Concept (PoC), you might get the following error:</span></span>

![Imagem de erro de licença](images/no-license-found.png)

<span data-ttu-id="792d2-113">**Mensagem:**</span><span class="sxs-lookup"><span data-stu-id="792d2-113">**Message:**</span></span> 

<span data-ttu-id="792d2-114">Nenhuma licença encontrada</span><span class="sxs-lookup"><span data-stu-id="792d2-114">No license found</span></span>

<span data-ttu-id="792d2-115">Parece que sua organização não tem uma licença para assinatura do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="792d2-115">Looks like your organization does not have a license for Microsoft 365 Enterprise subscription.</span></span>

<span data-ttu-id="792d2-116">Entre em contato com o administrador para obter ajuda.</span><span class="sxs-lookup"><span data-stu-id="792d2-116">Contact your administrator for help.</span></span>

<span data-ttu-id="792d2-117">**Causa:**</span><span class="sxs-lookup"><span data-stu-id="792d2-117">**Cause:**</span></span> 

<span data-ttu-id="792d2-118">Você implantou e/ou instalou o pacote do Microsoft Defender for Endpoint para macOS ("Baixar pacote de instalação") mas pode ter executado o script de configuração ("Baixar pacote de integração").</span><span class="sxs-lookup"><span data-stu-id="792d2-118">You deployed and/or installed the Microsoft Defender for Endpoint for macOS package ("Download installation package") but you might have run the configuration script ("Download onboarding package").</span></span>

<span data-ttu-id="792d2-119">**Solução:**</span><span class="sxs-lookup"><span data-stu-id="792d2-119">**Solution:**</span></span>

<span data-ttu-id="792d2-120">Siga as instruções MicrosoftDefenderATPOnboardingMacOs.py documentadas aqui: [Configuração do cliente](mac-install-manually.md#client-configuration)</span><span class="sxs-lookup"><span data-stu-id="792d2-120">Follow the MicrosoftDefenderATPOnboardingMacOs.py instructions documented here: [Client configuration](mac-install-manually.md#client-configuration)</span></span>

