---
title: Monitorar e exibir relatórios - Central de segurança
description: Descreve como a central de segurança do Microsoft 365 fornece um resumo resumido do status de proteção e segurança.
keywords: segurança, malware, Microsoft 365, M365, centro de segurança, monitorar, relatório, status
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: 4667c39a8d416d7e186d41063d7057109758cd33
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930397"
---
# <a name="monitor-and-view-reports-in-the-microsoft-365-security-center"></a><span data-ttu-id="6b1d4-104">Monitorar e exibir relatórios no centro de segurança do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6b1d4-104">Monitor and view reports in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> <span data-ttu-id="6b1d4-105">Deseja experimentar o Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="6b1d4-105">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="6b1d4-106">Você pode [avaliá-lo em um ambiente de laboratório](https://aka.ms/mtp-trial-lab) ou executar seu projeto piloto em [produção.](https://aka.ms/m365d-pilotplaybook)</span><span class="sxs-lookup"><span data-stu-id="6b1d4-106">You can [evaluate it in a lab environment](https://aka.ms/mtp-trial-lab) or [run your pilot project in production](https://aka.ms/m365d-pilotplaybook).</span></span>
>

<span data-ttu-id="6b1d4-107">A central de segurança do Microsoft 365 fornece um resumo dos status de proteção e segurança em seu ambiente do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6b1d4-107">The Microsoft 365 security center provides a summary of protection and security statuses across your Microsoft 365 environment.</span></span>

<span data-ttu-id="6b1d4-108">A central de segurança inclui uma **seção Relatórios** que apresenta uma série de cartões que abrangem uma variedade de áreas.</span><span class="sxs-lookup"><span data-stu-id="6b1d4-108">The security center includes a **Reports** section which features a host of cards covering a variety of areas.</span></span> <span data-ttu-id="6b1d4-109">Analistas de segurança e administradores podem acompanhar os cartões como parte de suas operações diárias.</span><span class="sxs-lookup"><span data-stu-id="6b1d4-109">Security analysts and administrators can track the cards as part of their day-to-day operations.</span></span> <span data-ttu-id="6b1d4-110">No detalhamento, os cartões fornecem relatórios detalhados e, em alguns casos, opções de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="6b1d4-110">On drill-down, cards provide detailed reports and, in some cases, management options.</span></span>

## <a name="customize-views"></a><span data-ttu-id="6b1d4-111">Personalizar exibições</span><span class="sxs-lookup"><span data-stu-id="6b1d4-111">Customize views</span></span>

<span data-ttu-id="6b1d4-112">Por padrão, os cartões são agrupados nestas categorias:</span><span class="sxs-lookup"><span data-stu-id="6b1d4-112">By default, cards are grouped into these categories:</span></span>
  
* <span data-ttu-id="6b1d4-113">[Identidades](monitor-and-report-identities.md) - contas de usuário e credenciais</span><span class="sxs-lookup"><span data-stu-id="6b1d4-113">[Identities](monitor-and-report-identities.md) - user accounts and credentials</span></span>
* <span data-ttu-id="6b1d4-114">[Dados](monitor-data.md) - email e conteúdo do documento</span><span class="sxs-lookup"><span data-stu-id="6b1d4-114">[Data](monitor-data.md) - email and document contents</span></span>
* <span data-ttu-id="6b1d4-115">[Dispositivos](monitor-devices.md) - computadores, celulares e outros dispositivos</span><span class="sxs-lookup"><span data-stu-id="6b1d4-115">[Devices](monitor-devices.md) - computers, mobile phones, and other devices</span></span>
* <span data-ttu-id="6b1d4-116">[Aplicativos](monitor-apps.md) - programas e serviços online anexados</span><span class="sxs-lookup"><span data-stu-id="6b1d4-116">[Apps](monitor-apps.md) - programs and attached online services</span></span>

<span data-ttu-id="6b1d4-117">Alternar **para Grupo por tópico,** para reorganizar os cartões e a groupá-los nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="6b1d4-117">Switch to **Group by topic**, to rearrange the cards and group them into the following topics:</span></span>

* <span data-ttu-id="6b1d4-118">**Risco** – cartões que realçam entidades, como contas e dispositivos, que podem estar em risco.</span><span class="sxs-lookup"><span data-stu-id="6b1d4-118">**Risk** - cards that highlight entities, such as accounts and devices, that might be at risk.</span></span> <span data-ttu-id="6b1d4-119">Esses cartões também destacam possíveis fontes de risco, como novas campanhas de ameaças e aplicativos de nuvem privilegiados</span><span class="sxs-lookup"><span data-stu-id="6b1d4-119">These cards also highlight possible sources of risk, such as new threat campaigns and privileged cloud apps</span></span>  
* <span data-ttu-id="6b1d4-120">**Tendências de** detecção - cartões que destacam novas detecções de ameaças, anomalias e violações de política</span><span class="sxs-lookup"><span data-stu-id="6b1d4-120">**Detection trends** - cards that highlight new threat detections, anomalies, and policy violations</span></span>
* <span data-ttu-id="6b1d4-121">**Configuração e saúde** - cartões que abrangem a configuração e implantação de controles de segurança, incluindo estados de integração de dispositivos a serviços de gerenciamento</span><span class="sxs-lookup"><span data-stu-id="6b1d4-121">**Configuration and health** - cards that cover the configuration and deployment of security controls, including device onboarding states to management services</span></span>
* <span data-ttu-id="6b1d4-122">**Outros** - todos os outros cartões não categorizados em outros tópicos</span><span class="sxs-lookup"><span data-stu-id="6b1d4-122">**Other** - all other cards not categorized under other topics</span></span>
