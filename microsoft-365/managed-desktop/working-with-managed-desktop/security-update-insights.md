---
title: Percepções de atualização da segurança do Windows
description: ''
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: b3b1f43217b3be285f20925065bf9710a38f9606
ms.sourcegitcommit: 36795a6735cd3fc678c7d5db71ddc97fac3f6f8a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/06/2020
ms.locfileid: "48941436"
---
# <a name="windows-security-update-insights"></a><span data-ttu-id="ae9a1-103">Percepções de atualização da segurança do Windows</span><span class="sxs-lookup"><span data-stu-id="ae9a1-103">Windows security update insights</span></span>
<span data-ttu-id="ae9a1-104">Esta exibição fornece uma visão geral do status das atualizações de segurança para seus dispositivos da Área de Trabalho Gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ae9a1-104">This view provides an overview of the status of security updates for your Microsoft Managed Desktop devices.</span></span> 

<span data-ttu-id="ae9a1-105">Para exibir dados de uso, selecione a <strong>guia Atualizações de segurança do Windows.</strong></span><span class="sxs-lookup"><span data-stu-id="ae9a1-105">To view usage data, select the <strong>Windows security updates</strong> tab.</span></span>

![Painel de atualizações de segurança do Windows: gráficos de barra de status do dispositivo e versão de atualização na coluna esquerda, progresso da implantação de atualização ao longo do tempo na coluna central e porcentagem de dispositivos ativos por grupo de implantação, bem como o número de dias que levar para alcançar o destino de implantação de 95% na coluna direita.](../../media/update-insights.jpg)

## <a name="device-status"></a><span data-ttu-id="ae9a1-107">Status do dispositivo</span><span class="sxs-lookup"><span data-stu-id="ae9a1-107">Device status</span></span>

<span data-ttu-id="ae9a1-108">Para que os dispositivos sejam atualizados pelo Windows Update, eles devem estar conectados à Internet e não hibernar por no mínimo seis horas, dois dos quais devem ser contínuos.</span><span class="sxs-lookup"><span data-stu-id="ae9a1-108">For devices to be updated by Windows Update, they must be connected to the Internet and not hibernating for a minimum of six hours, two of which must be continuous.</span></span> <span data-ttu-id="ae9a1-109">Embora seja possível que um dispositivo que não atender a esses requisitos seja atualizado, os dispositivos que atenderem a eles têm a maior probabilidade de serem atualizados.</span><span class="sxs-lookup"><span data-stu-id="ae9a1-109">Although it's possible that a device that doesn't meet these requirements will be updated, devices that meet them have the highest likelihood of being updated.</span></span> 

<span data-ttu-id="ae9a1-110">Categorizamos a atividade do dispositivo no contexto do Windows Update com estes termos:</span><span class="sxs-lookup"><span data-stu-id="ae9a1-110">We categorize device activity in the context of Windows Update with these terms:</span></span>

- <span data-ttu-id="ae9a1-111"><strong>Ativo:</strong> Dispositivos que atendiam aos critérios mínimos de atividade (seis horas, duas horas contínuas) para o lançamento mais recente da atualização de segurança e fizeram check-in com o Microsoft Intune pelo menos a cada cinco dias</span><span class="sxs-lookup"><span data-stu-id="ae9a1-111"><strong>Active:</strong> Devices that have met the minimum activity criteria (six hours, two continuous) for the most recent security update release and have checked in with Microsoft Intune at least every five days</span></span>
- <span data-ttu-id="ae9a1-112"><strong>Sincronizado:</strong> Dispositivos que entraram com o Intune nos últimos 28 dias</span><span class="sxs-lookup"><span data-stu-id="ae9a1-112"><strong>Synced:</strong> Devices that have checked in with Intune within the last 28 days</span></span>
- <span data-ttu-id="ae9a1-113"><strong>Fora de sincronia:</strong> Dispositivos que <i>não</i> entraram com o Intune nos últimos 28 dias</span><span class="sxs-lookup"><span data-stu-id="ae9a1-113"><strong>Out of sync:</strong> Devices that have <i>not</i> checked in with Intune in the last 28 days</span></span>




## <a name="update-version-status"></a><span data-ttu-id="ae9a1-114">Atualizar status da versão</span><span class="sxs-lookup"><span data-stu-id="ae9a1-114">Update version status</span></span>

<span data-ttu-id="ae9a1-115">A Microsoft lança atualizações de segurança toda segunda terça-feira do mês.</span><span class="sxs-lookup"><span data-stu-id="ae9a1-115">Microsoft releases security updates every second Tuesday of the month.</span></span> <span data-ttu-id="ae9a1-116">Cada versão adiciona atualizações importantes para vulnerabilidades de segurança conhecidas.</span><span class="sxs-lookup"><span data-stu-id="ae9a1-116">Each release adds important updates for known security vulnerabilities.</span></span> <span data-ttu-id="ae9a1-117">A Área de Trabalho Gerenciada da Microsoft garante que 95% de seus dispositivos gerenciados sejam atualizados com a atualização de segurança mais recente disponível todos os meses.</span><span class="sxs-lookup"><span data-stu-id="ae9a1-117">Microsoft Managed Desktop ensures that 95% of its managed devices are updated with the latest available security update every month.</span></span> <span data-ttu-id="ae9a1-118">Às vezes, as atualizações de segurança são lançadas em outras ocasiões para tratar urgentemente de novas ameaças.</span><span class="sxs-lookup"><span data-stu-id="ae9a1-118">Security updates are sometimes released at other times to urgently address new threats.</span></span> <span data-ttu-id="ae9a1-119">A Área de Trabalho Gerenciada da Microsoft implanta essas atualizações de maneira semelhante.</span><span class="sxs-lookup"><span data-stu-id="ae9a1-119">Microsoft Managed Desktop deploys these updates in a similar fashion.</span></span>

<span data-ttu-id="ae9a1-120">Categorizamos o status das versões de atualização de segurança com estes termos:</span><span class="sxs-lookup"><span data-stu-id="ae9a1-120">We categorize the status of security update versions with these terms:</span></span>

- <span data-ttu-id="ae9a1-121"><strong>Atual:</strong> Dispositivos que estão executando a atualização lançada no mês atual</span><span class="sxs-lookup"><span data-stu-id="ae9a1-121"><strong>Current:</strong> Devices that are running the update released in the current month</span></span>
- <span data-ttu-id="ae9a1-122"><strong>Anterior:</strong> Dispositivos executando a atualização que foi lançada no mês anterior</span><span class="sxs-lookup"><span data-stu-id="ae9a1-122"><strong>Previous:</strong> Devices running the update that was released in the previous month</span></span>
- <span data-ttu-id="ae9a1-123"><strong>Mais antigo:</strong> Dispositivos executando qualquer atualização de segurança lançada antes do mês anterior</span><span class="sxs-lookup"><span data-stu-id="ae9a1-123"><strong>Older:</strong> Devices running any security update released prior to the previous month</span></span>

<span data-ttu-id="ae9a1-124">Você deve ver alguns <strong></strong> dispositivos na categoria Mais antiga – uma população grande ou crescente provavelmente indica um problema sério que você deve relatar à Área de Trabalho Gerenciada da Microsoft para que possamos investigar.</span><span class="sxs-lookup"><span data-stu-id="ae9a1-124">You should see few devices in the <strong>Older</strong> category--a large or growing population probably indicates a systemic problem that you should report to Microsoft Managed Desktop so we can investigate.</span></span>


## <a name="deployment-progress"></a><span data-ttu-id="ae9a1-125">Progresso da implantação</span><span class="sxs-lookup"><span data-stu-id="ae9a1-125">Deployment progress</span></span>

<span data-ttu-id="ae9a1-126">No início de cada ciclo de lançamento de atualização de segurança, a Área de Trabalho Gerenciada da Microsoft tira um instantâneo da população de dispositivos e define sua meta de implantação em 95% dessa população.</span><span class="sxs-lookup"><span data-stu-id="ae9a1-126">At the beginning of each security update release cycle, Microsoft Managed Desktop takes a snapshot of the device population and sets its deployment target at 95% of that population.</span></span> <span data-ttu-id="ae9a1-127">A <strong>área de progresso</strong> de Implantação mostra uma tendência histórica, atualizada diariamente, acompanhando a proximidade com que a implantação de atualização atende a essa meta para cada versão.</span><span class="sxs-lookup"><span data-stu-id="ae9a1-127">The <strong>Deployment progress</strong> area shows a historical trend, updated daily, tracking how closely the update deployment meets this target for each release.</span></span> <span data-ttu-id="ae9a1-128">Este gráfico mostra apenas dispositivos com status Ativo.</span><span class="sxs-lookup"><span data-stu-id="ae9a1-128">This graph only shows devices with Active status.</span></span>

<span data-ttu-id="ae9a1-129">Você pode exibir esses dados para ciclos de atualização anteriores usando o menu suspenso no canto superior direito.</span><span class="sxs-lookup"><span data-stu-id="ae9a1-129">You can view this data for previous update cycles by using the dropdown menu in the upper right.</span></span> <span data-ttu-id="ae9a1-130">O período selecionado neste menu se aplica a todas as informações na página inteira.</span><span class="sxs-lookup"><span data-stu-id="ae9a1-130">The period you select in this menu applies to all of the information on the whole page.</span></span>

<span data-ttu-id="ae9a1-131">Os <strong>dispositivos ativos atualizados</strong> pela área de grupo de implantação oferecem uma exibição diferente, mostrando o progresso da instalação da atualização para cada um dos grupos de implantação da Área de Trabalho Gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ae9a1-131">The <strong>Updated active devices by deployment group</strong> area offers a different view by showing the progress of the update installation for each of the Microsoft Managed Desktop deployment groups.</span></span>

<span data-ttu-id="ae9a1-132">The <strong>Days to reach target</strong> area displays how long it took for 95% of the total number of devices to be updated with the current security update.</span><span class="sxs-lookup"><span data-stu-id="ae9a1-132">The <strong>Days to reach target</strong> area displays how long it took for 95% of the total number of devices to be updated with the current security update.</span></span> <span data-ttu-id="ae9a1-133">Enquanto a implantação está em andamento, essa área exibe <strong>Ainda</strong> atualizando até que o destino de 95% seja atingido para a atualização selecionada.</span><span class="sxs-lookup"><span data-stu-id="ae9a1-133">While deployment is underway, this area displays <strong>Still updating</strong> until the 95% target is reached for the selected update.</span></span>

## <a name="device-details-area"></a><span data-ttu-id="ae9a1-134">Área de detalhes do dispositivo</span><span class="sxs-lookup"><span data-stu-id="ae9a1-134">Device details area</span></span>

<span data-ttu-id="ae9a1-135">A parte inferior do painel é uma tabela mostrando informações detalhadas para seus dispositivos, incluindo o status do dispositivo e o [status](#device-status) da [versão de atualização.](#update-version-status)</span><span class="sxs-lookup"><span data-stu-id="ae9a1-135">The bottom of the dashboard is a table showing detailed information for your devices, including the [Device status](#device-status) and the [Update version status](#update-version-status).</span></span> <span data-ttu-id="ae9a1-136">Você pode pesquisar essa lista ou filtre-a por qualquer valor listado.</span><span class="sxs-lookup"><span data-stu-id="ae9a1-136">You can search this list or filter it by any listed value.</span></span>


![Tabela de detalhes do dispositivo mostrando colunas para nome do dispositivo, usuário atribuído, status do dispositivo, versão de atualização, versão do sistema operacional e a data em que o dispositivo foi sincronizado pela última vez.](../../media/security-update-insights-device-table-sterile.png)
