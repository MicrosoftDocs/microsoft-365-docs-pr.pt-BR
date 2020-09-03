---
title: Microsoft 365 lidando com corrupção de dados
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
description: Este artigo explica a corrupção de dados no Microsoft 365 e os esforços feitos pela Microsoft para impedir e recuperar dados.
ms.openlocfilehash: 767be71bb08c49070488cc965165ac86e98836bd
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/02/2020
ms.locfileid: "47331867"
---
# <a name="dealing-with-data-corruption-in-microsoft-365"></a><span data-ttu-id="1a0fe-103">Lidando com corrupção de dados no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1a0fe-103">Dealing with Data Corruption in Microsoft 365</span></span>

<span data-ttu-id="1a0fe-104">Um dos aspectos desafiadores de execução de um serviço de nuvem em larga escala é como lidar com a corrupção de dados, considerando o grande volume de dados e sistemas independentes.</span><span class="sxs-lookup"><span data-stu-id="1a0fe-104">One of the challenging aspects of running a large-scale cloud service is how to handle data corruption, given the large volume of data and independent systems.</span></span> <span data-ttu-id="1a0fe-105">A corrupção dos dados pode ser causada por:</span><span class="sxs-lookup"><span data-stu-id="1a0fe-105">Data corruption can be caused by:</span></span>

- <span data-ttu-id="1a0fe-106">Erros de infraestrutura ou aplicativo, corrompendo parte ou todo o estado do aplicativo</span><span class="sxs-lookup"><span data-stu-id="1a0fe-106">Application or infrastructure bugs, corrupting some or all of the application state</span></span>
- <span data-ttu-id="1a0fe-107">Problemas de hardware que resultam em perda de dados ou incapacidade de ler dados</span><span class="sxs-lookup"><span data-stu-id="1a0fe-107">Hardware issues that result in lost data or an inability to read data</span></span>
- <span data-ttu-id="1a0fe-108">Erros operacionais humanos</span><span class="sxs-lookup"><span data-stu-id="1a0fe-108">Human operational errors</span></span>
- <span data-ttu-id="1a0fe-109">Hackers mal-intencionados e funcionários descontentes</span><span class="sxs-lookup"><span data-stu-id="1a0fe-109">Malicious hackers and disgruntled employees</span></span>
- <span data-ttu-id="1a0fe-110">Incidentes em serviços externos que resultam em alguma perda de dados</span><span class="sxs-lookup"><span data-stu-id="1a0fe-110">Incidents in external services that result in some loss of data</span></span>

<span data-ttu-id="1a0fe-111">Como a maior resiliência na integridade dos dados significa menos incidentes de corrupção de dados, a Microsoft criou os mecanismos de proteção da Microsoft 365 para evitar que os danos ocorram, bem como sistemas e processos que nos permitem recuperar dados, se o fizer.</span><span class="sxs-lookup"><span data-stu-id="1a0fe-111">Because greater resiliency in data integrity means fewer data corruption incidents, Microsoft has built into Microsoft 365 protection mechanisms to prevent corruption from happening, as well as systems and processes that enable us to recover data if it does.</span></span> <span data-ttu-id="1a0fe-112">Os cheques e processos existem dentro dos vários estágios do processo de lançamento da engenharia para aumentar a resiliência contra corrupção de dados, incluindo:</span><span class="sxs-lookup"><span data-stu-id="1a0fe-112">Checks and processes exist within the various stages of the engineering release process to increase resiliency against data corruption, including:</span></span>

- <span data-ttu-id="1a0fe-113">Design de sistema</span><span class="sxs-lookup"><span data-stu-id="1a0fe-113">System Design</span></span>
- <span data-ttu-id="1a0fe-114">Organização e estrutura de código</span><span class="sxs-lookup"><span data-stu-id="1a0fe-114">Code organization and structure</span></span>
- <span data-ttu-id="1a0fe-115">Revisão de código</span><span class="sxs-lookup"><span data-stu-id="1a0fe-115">Code review</span></span>
- <span data-ttu-id="1a0fe-116">Testes de unidade, testes de integração e testes de sistema</span><span class="sxs-lookup"><span data-stu-id="1a0fe-116">Unit tests, integration tests, and system tests</span></span>
- <span data-ttu-id="1a0fe-117">Testes/Gates dos fios de viagem</span><span class="sxs-lookup"><span data-stu-id="1a0fe-117">Trip wires tests/gates</span></span>

<span data-ttu-id="1a0fe-118">Nos ambientes de produção do Microsoft 365, a replicação de mesmo nível entre datacenters garante que haja sempre várias cópias ao vivo de qualquer dado.</span><span class="sxs-lookup"><span data-stu-id="1a0fe-118">Within Microsoft 365 production environments, peer replication between datacenters ensures that there are always multiple live copies of any data.</span></span> <span data-ttu-id="1a0fe-119">Imagens e scripts padrão são usados para recuperar servidores perdidos e dados replicados são usados para restaurar dados do cliente.</span><span class="sxs-lookup"><span data-stu-id="1a0fe-119">Standard images and scripts are used to recover lost servers, and replicated data is used to restore customer data.</span></span> <span data-ttu-id="1a0fe-120">Devido às verificações e processos de resiliência de dados internos, a Microsoft mantém backups somente da documentação do sistema de informações da Microsoft 365 (incluindo a documentação relacionada à segurança), usando a replicação interna do SharePoint Online e nossa ferramenta de repositório de código interno, depósito de origem.</span><span class="sxs-lookup"><span data-stu-id="1a0fe-120">Because of the built-in data resiliency checks and processes, Microsoft maintains backups only of Microsoft 365 information system documentation (including security-related documentation), using built-in replication in SharePoint Online and our internal code repository tool, Source Depot.</span></span> <span data-ttu-id="1a0fe-121">A documentação do sistema está armazenada no SharePoint Online e o depósito de origem contém imagens de sistema e de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="1a0fe-121">System documentation is stored in SharePoint Online, and Source Depot contains system and application images.</span></span> <span data-ttu-id="1a0fe-122">O SharePoint Online e o Source Depot usam o controle de versão e são replicados praticamente em tempo real.</span><span class="sxs-lookup"><span data-stu-id="1a0fe-122">Both SharePoint Online and Source Depot use versioning and are replicated in near real time.</span></span>
