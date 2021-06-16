---
title: Avaliar o Microsoft Defender Antivírus
description: Empresas de todos os tamanhos podem usar este guia para avaliar e testar a proteção oferecida Microsoft Defender Antivírus em Windows 10.
keywords: Microsoft Defender Antivírus, proteção de nuvem, nuvem, antimalware, segurança, defender, avaliar, testar, proteger, comparar, proteção em tempo real
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
ms.topic: conceptual
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 5c558a7799bff61a0ee80db31ee476ad611053c0
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926614"
---
# <a name="evaluate-microsoft-defender-antivirus"></a><span data-ttu-id="63b4a-104">Avaliar o Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="63b4a-104">Evaluate Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="63b4a-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="63b4a-105">**Applies to:**</span></span>

- [<span data-ttu-id="63b4a-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="63b4a-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="63b4a-107">Use este guia para determinar a Microsoft Defender Antivírus protege contra vírus, malware e aplicativos potencialmente indesejados.</span><span class="sxs-lookup"><span data-stu-id="63b4a-107">Use this guide to determine how well Microsoft Defender Antivirus protects you from viruses, malware, and potentially unwanted applications.</span></span>

>[!TIP]
><span data-ttu-id="63b4a-108">Você também pode visitar o site de demonstração do Microsoft Defender para Ponto de Extremidade no [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) para confirmar que os seguintes recursos estão funcionando e ver como eles funcionam:</span><span class="sxs-lookup"><span data-stu-id="63b4a-108">You can also visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the following features are working and see how they work:</span></span>
>- <span data-ttu-id="63b4a-109">Proteção fornecida na nuvem</span><span class="sxs-lookup"><span data-stu-id="63b4a-109">Cloud-delivered protection</span></span>
>- <span data-ttu-id="63b4a-110">Aprendizado rápido (incluindo Bloquear à primeira vista)</span><span class="sxs-lookup"><span data-stu-id="63b4a-110">Fast learning (including Block at first sight)</span></span>
>- <span data-ttu-id="63b4a-111">Bloqueio de aplicativo potencialmente indesejado</span><span class="sxs-lookup"><span data-stu-id="63b4a-111">Potentially unwanted application blocking</span></span>

<span data-ttu-id="63b4a-112">Ele explica os recursos importantes de proteção de próxima geração Microsoft Defender Antivírus disponíveis para pequenas e grandes empresas e como eles aumentam a detecção e a proteção de malware em toda a sua rede.</span><span class="sxs-lookup"><span data-stu-id="63b4a-112">It explains the important next-generation protection features of Microsoft Defender Antivirus available for both small and large enterprises, and how they increase malware detection and protection across your network.</span></span>

<span data-ttu-id="63b4a-113">Você pode optar por configurar e avaliar cada configuração independentemente ou tudo de uma vez.</span><span class="sxs-lookup"><span data-stu-id="63b4a-113">You can choose to configure and evaluate each setting independently, or all at once.</span></span> <span data-ttu-id="63b4a-114">Agrupamos configurações semelhantes com base em cenários de avaliação típicos e incluímos instruções para usar o PowerShell para habilitar as configurações.</span><span class="sxs-lookup"><span data-stu-id="63b4a-114">We have grouped similar settings based upon typical evaluation scenarios, and include instructions for using PowerShell to enable the settings.</span></span>

<span data-ttu-id="63b4a-115">O guia está disponível no formato PDF para exibição offline:</span><span class="sxs-lookup"><span data-stu-id="63b4a-115">The guide is available in PDF format for offline viewing:</span></span>

- [<span data-ttu-id="63b4a-116">Baixar o guia no formato PDF</span><span class="sxs-lookup"><span data-stu-id="63b4a-116">Download the guide in PDF format</span></span>](https://www.microsoft.com/download/details.aspx?id=54795)

<span data-ttu-id="63b4a-117">Você também pode baixar um PowerShell que habilita todas as configurações descritas no guia automaticamente.</span><span class="sxs-lookup"><span data-stu-id="63b4a-117">You can also download a PowerShell that will enable all the settings described in the guide automatically.</span></span> <span data-ttu-id="63b4a-118">Você pode obter o script juntamente com o download em PDF acima ou individualmente na Galeria do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="63b4a-118">You can obtain the script alongside the PDF download above, or individually from PowerShell Gallery:</span></span>

- [<span data-ttu-id="63b4a-119">Baixe o script do PowerShell para configurar automaticamente as configurações</span><span class="sxs-lookup"><span data-stu-id="63b4a-119">Download the PowerShell script to automatically configure the settings</span></span>](https://www.powershellgallery.com/packages/WindowsDefender_InternalEvaluationSettings)

> [!IMPORTANT]
> <span data-ttu-id="63b4a-120">No momento, o guia destina-se à avaliação de máquina única Microsoft Defender Antivírus.</span><span class="sxs-lookup"><span data-stu-id="63b4a-120">The guide is currently intended for single-machine evaluation of Microsoft Defender Antivirus.</span></span> <span data-ttu-id="63b4a-121">A habilitação de todas as configurações neste guia pode não ser adequada para implantação no mundo real.</span><span class="sxs-lookup"><span data-stu-id="63b4a-121">Enabling all of the settings in this guide may not be suitable for real-world deployment.</span></span>
>
> <span data-ttu-id="63b4a-122">Para saber mais sobre as recomendações mais recentes para implantação e monitoramento do Microsoft Defender Antivírus em uma rede, consulte [Deploy Microsoft Defender Antivírus](deploy-manage-report-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="63b4a-122">For the latest recommendations for real-world deployment and monitoring of Microsoft Defender Antivirus across a network, see [Deploy Microsoft Defender Antivirus](deploy-manage-report-microsoft-defender-antivirus.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="63b4a-123">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="63b4a-123">Related topics</span></span>

- [<span data-ttu-id="63b4a-124">Microsoft Defender Antivirus no Windows 10</span><span class="sxs-lookup"><span data-stu-id="63b4a-124">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="63b4a-125">Implantar Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="63b4a-125">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)