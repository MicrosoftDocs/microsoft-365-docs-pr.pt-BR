---
title: Monitorar e exibir relatórios-central de segurança
description: Descreve como a central de segurança da Microsoft 365 fornece um resumo rápido de proteção e status de segurança.
keywords: segurança, malware, Microsoft 365, M365, central de segurança, monitor, relatório, status
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: d52c401c4b2e995e5ec18895c158f77ce0fce746
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/19/2020
ms.locfileid: "49356878"
---
# <a name="monitor-and-view-reports-in-the-microsoft-365-security-center"></a><span data-ttu-id="645f9-104">Monitorar e exibir relatórios no centro de segurança do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="645f9-104">Monitor and view reports in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> <span data-ttu-id="645f9-105">Quer experimentar o Microsoft 365 defender?</span><span class="sxs-lookup"><span data-stu-id="645f9-105">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="645f9-106">Você pode [avaliá-lo em um ambiente de laboratório](https://aka.ms/mtp-trial-lab) ou [executar o projeto piloto em produção](https://aka.ms/m365d-pilotplaybook).</span><span class="sxs-lookup"><span data-stu-id="645f9-106">You can [evaluate it in a lab environment](https://aka.ms/mtp-trial-lab) or [run your pilot project in production](https://aka.ms/m365d-pilotplaybook).</span></span>
>

<span data-ttu-id="645f9-107">O centro de segurança do Microsoft 365 fornece um resumo de status de proteção e segurança em seu ambiente do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="645f9-107">The Microsoft 365 security center provides a summary of protection and security statuses across your Microsoft 365 environment.</span></span>

<span data-ttu-id="645f9-108">A central de segurança inclui uma seção de **relatórios** que apresenta um host de cartões que cobrem uma variedade de áreas.</span><span class="sxs-lookup"><span data-stu-id="645f9-108">The security center includes a **Reports** section which features a host of cards covering a variety of areas.</span></span> <span data-ttu-id="645f9-109">Os analistas e administradores de segurança podem acompanhar os cartões como parte de suas operações diárias.</span><span class="sxs-lookup"><span data-stu-id="645f9-109">Security analysts and administrators can track the cards as part of their day-to-day operations.</span></span> <span data-ttu-id="645f9-110">Em busca detalhada, os cartões fornecem relatórios detalhados e, em alguns casos, opções de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="645f9-110">On drill-down, cards provide detailed reports and, in some cases, management options.</span></span>

## <a name="customize-views"></a><span data-ttu-id="645f9-111">Personalizar modos de exibição</span><span class="sxs-lookup"><span data-stu-id="645f9-111">Customize views</span></span>

<span data-ttu-id="645f9-112">Por padrão, os cartões são agrupados nessas categorias:</span><span class="sxs-lookup"><span data-stu-id="645f9-112">By default, cards are grouped into these categories:</span></span>
  
* <span data-ttu-id="645f9-113">[Identities](monitor-and-report-identities.md) -contas de usuário e credenciais</span><span class="sxs-lookup"><span data-stu-id="645f9-113">[Identities](monitor-and-report-identities.md) - user accounts and credentials</span></span>
* <span data-ttu-id="645f9-114">[Dados](monitor-data.md) – email e conteúdo do documento</span><span class="sxs-lookup"><span data-stu-id="645f9-114">[Data](monitor-data.md) - email and document contents</span></span>
* <span data-ttu-id="645f9-115">[Dispositivos](monitor-devices.md) -computadores, telefones celulares e outros dispositivos</span><span class="sxs-lookup"><span data-stu-id="645f9-115">[Devices](monitor-devices.md) - computers, mobile phones, and other devices</span></span>
* <span data-ttu-id="645f9-116">[Aplicativos](monitor-apps.md) -programas e serviços online anexados</span><span class="sxs-lookup"><span data-stu-id="645f9-116">[Apps](monitor-apps.md) - programs and attached online services</span></span>

<span data-ttu-id="645f9-117">Alterne para **Agrupar por tópico** para reorganizar os cartões e agrupá-los nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="645f9-117">Switch to **Group by topic**, to rearrange the cards and group them into the following topics:</span></span>

* <span data-ttu-id="645f9-118">Cartões de **risco** que realçam entidades, como contas e dispositivos, que podem estar em risco.</span><span class="sxs-lookup"><span data-stu-id="645f9-118">**Risk** - cards that highlight entities, such as accounts and devices, that might be at risk.</span></span> <span data-ttu-id="645f9-119">Esses cartões também realçam possíveis fontes de risco, como novas campanhas de ameaças e aplicativos de nuvem privilegiados</span><span class="sxs-lookup"><span data-stu-id="645f9-119">These cards also highlight possible sources of risk, such as new threat campaigns and privileged cloud apps</span></span>  
* <span data-ttu-id="645f9-120">**Tendências de detecção** -cartões que realçam novas detecções de ameaças, anomalias e violações de política</span><span class="sxs-lookup"><span data-stu-id="645f9-120">**Detection trends** - cards that highlight new threat detections, anomalies, and policy violations</span></span>
* <span data-ttu-id="645f9-121">**Configuração e** cartões de integridade que abrangem a configuração e a implantação de controles de segurança, incluindo Estados de integração de dispositivos para serviços de gerenciamento</span><span class="sxs-lookup"><span data-stu-id="645f9-121">**Configuration and health** - cards that cover the configuration and deployment of security controls, including device onboarding states to management services</span></span>
* <span data-ttu-id="645f9-122">**Outros** -todos os outros cartões não categorizados em outros tópicos</span><span class="sxs-lookup"><span data-stu-id="645f9-122">**Other** - all other cards not categorized under other topics</span></span>
