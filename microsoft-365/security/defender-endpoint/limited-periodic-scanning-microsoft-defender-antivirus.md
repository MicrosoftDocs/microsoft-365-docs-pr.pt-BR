---
title: Habilitar o recurso de verificação periódica limitada do Microsoft Defender Antivírus
description: A verificação periódica limitada permite que você use o Microsoft Defender Antivírus, além de outros provedores AV instalados
keywords: lps, limited, periodic, scan, scanning, compatibility, 3rd party, other av, disable
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: b2ae56c0f67501eb8603d5d28c4ed0c4af01a8c9
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274587"
---
# <a name="use-limited-periodic-scanning-in-microsoft-defender-antivirus"></a><span data-ttu-id="67a06-104">Usar uma verificação periódica limitada no Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="67a06-104">Use limited periodic scanning in Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="67a06-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="67a06-105">**Applies to:**</span></span>

- [<span data-ttu-id="67a06-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="67a06-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="67a06-107">A verificação periódica limitada é um tipo especial de detecção e correção de ameaças que pode ser habilitado quando você instalou outro produto antivírus em um dispositivo Windows 10.</span><span class="sxs-lookup"><span data-stu-id="67a06-107">Limited periodic scanning is a special type of threat detection and remediation that can be enabled when you have installed another antivirus product on a Windows 10 device.</span></span>

<span data-ttu-id="67a06-108">Ele só pode ser habilitado em determinadas situações.</span><span class="sxs-lookup"><span data-stu-id="67a06-108">It can only be enabled in certain situations.</span></span> <span data-ttu-id="67a06-109">Para obter mais informações sobre a verificação periódica limitada e como o Microsoft Defender Antivírus funciona com outros produtos antivírus, consulte [Microsoft Defender Antivírus compatibility](microsoft-defender-antivirus-compatibility.md).</span><span class="sxs-lookup"><span data-stu-id="67a06-109">For more information about limited periodic scanning and how Microsoft Defender Antivirus works with other antivirus products, see [Microsoft Defender Antivirus compatibility](microsoft-defender-antivirus-compatibility.md).</span></span>

<span data-ttu-id="67a06-110">**A Microsoft não recomenda usar esse recurso em ambientes corporativos. Esse é um recurso destinado principalmente aos consumidores.**</span><span class="sxs-lookup"><span data-stu-id="67a06-110">**Microsoft does not recommend using this feature in enterprise environments. This is a feature primarily intended for consumers.**</span></span> <span data-ttu-id="67a06-111">Esse recurso usa apenas um subconjunto limitado dos recursos do Microsoft Defender Antivírus para detectar malware e não será capaz de detectar a maioria dos malwares e softwares potencialmente indesejados.</span><span class="sxs-lookup"><span data-stu-id="67a06-111">This feature only uses a limited subset of the Microsoft Defender Antivirus capabilities to detect malware, and will not be able to detect most malware and potentially unwanted software.</span></span> <span data-ttu-id="67a06-112">Além disso, os recursos de gerenciamento e relatório serão limitados.</span><span class="sxs-lookup"><span data-stu-id="67a06-112">Also, management and reporting capabilities will be limited.</span></span> <span data-ttu-id="67a06-113">A Microsoft recomenda que as empresas escolham sua solução antivírus principal e a usem exclusivamente.</span><span class="sxs-lookup"><span data-stu-id="67a06-113">Microsoft recommends enterprises choose their primary antivirus solution and use it exclusively.</span></span>

## <a name="how-to-enable-limited-periodic-scanning"></a><span data-ttu-id="67a06-114">Como habilitar a verificação periódica limitada</span><span class="sxs-lookup"><span data-stu-id="67a06-114">How to enable limited periodic scanning</span></span>

<span data-ttu-id="67a06-115">Por padrão, o Microsoft Defender Antivírus se habilitará em um dispositivo Windows 10 se não houver outro produto antivírus instalado, ou se o outro produto estiver desaprivado, expirado ou não funcionando corretamente.</span><span class="sxs-lookup"><span data-stu-id="67a06-115">By default, Microsoft Defender Antivirus will enable itself on a Windows 10 device if there is no other antivirus product installed, or if the other product is out-of-date, expired, or not working correctly.</span></span>

<span data-ttu-id="67a06-116">Se o Microsoft Defender Antivírus estiver habilitado, as opções usuais aparecerão para configurá-lo nesse dispositivo:</span><span class="sxs-lookup"><span data-stu-id="67a06-116">If Microsoft Defender Antivirus is enabled, the usual options will appear to configure it on that device:</span></span>

![Aplicativo de Segurança do Windows mostrando opções do Microsoft Defender AV, incluindo opções de verificação, configurações e opções de atualização](images/vtp-wdav.png)

<span data-ttu-id="67a06-118">Se outro produto antivírus estiver instalado e funcionando corretamente, o Microsoft Defender Antivírus se desabilitará.</span><span class="sxs-lookup"><span data-stu-id="67a06-118">If another antivirus product is installed and working correctly, Microsoft Defender Antivirus will disable itself.</span></span> <span data-ttu-id="67a06-119">O aplicativo segurança do Windows alterará a seção Proteção contra **&** vírus para mostrar o status sobre o produto AV e fornecerá um link para as opções de configuração do produto.</span><span class="sxs-lookup"><span data-stu-id="67a06-119">The Windows Security app will change the **Virus & threat protection** section to show status about the AV product, and provide a link to the product's configuration options.</span></span>

<span data-ttu-id="67a06-120">Sob qualquer produto AV de terceiros, um novo link aparecerá como opções do **Microsoft Defender Antivírus.**</span><span class="sxs-lookup"><span data-stu-id="67a06-120">Underneath any third party AV products, a new link will appear as **Microsoft Defender Antivirus options**.</span></span> <span data-ttu-id="67a06-121">Clicar neste link será expandido para mostrar a alternância que permite a verificação periódica limitada.</span><span class="sxs-lookup"><span data-stu-id="67a06-121">Clicking this link will expand to show the toggle that enables limited periodic scanning.</span></span> <span data-ttu-id="67a06-122">Observe que a opção periódica limitada é uma alternância para habilitar ou desabilitar a verificação periódica.</span><span class="sxs-lookup"><span data-stu-id="67a06-122">Note that the limited periodic option is a toggle to enable or disable periodic scanning.</span></span> 

<span data-ttu-id="67a06-123">Deslizar a opção para **On** mostrará as opções padrão do Microsoft Defender AV abaixo do produto AV de terceiros.</span><span class="sxs-lookup"><span data-stu-id="67a06-123">Sliding the switch to **On** will show the standard Microsoft Defender AV options underneath the third party AV product.</span></span> <span data-ttu-id="67a06-124">A opção de verificação periódica limitada aparecerá na parte inferior da página.</span><span class="sxs-lookup"><span data-stu-id="67a06-124">The limited periodic scanning option will appear at the bottom of the page.</span></span>

## <a name="related-articles"></a><span data-ttu-id="67a06-125">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="67a06-125">Related articles</span></span>

- [<span data-ttu-id="67a06-126">Configurar a proteção comportamental, heurística e em tempo real</span><span class="sxs-lookup"><span data-stu-id="67a06-126">Configure behavioral, heuristic, and real-time protection</span></span>](configure-protection-features-microsoft-defender-antivirus.md)
- [<span data-ttu-id="67a06-127">Microsoft Defender Antivírus no Windows 10</span><span class="sxs-lookup"><span data-stu-id="67a06-127">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)