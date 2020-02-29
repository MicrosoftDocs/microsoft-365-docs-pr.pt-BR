---
title: Percepções de atualização da segurança do Windows
description: ''
keywords: Área de trabalho gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: ef2d5c897709e7f7d2484d032b7471031be77d74
ms.sourcegitcommit: cf07dfccec476ac2526a6171ec6b6365686f759f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/29/2020
ms.locfileid: "42341262"
---
# <a name="windows-security-update-insights"></a><span data-ttu-id="7dd23-103">Percepções de atualização da segurança do Windows</span><span class="sxs-lookup"><span data-stu-id="7dd23-103">Windows security update insights</span></span>
<span data-ttu-id="7dd23-104">Este modo de exibição fornece uma visão geral do status das atualizações de segurança para seus dispositivos de área de trabalho gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7dd23-104">This view provides an overview of the status of security updates for your Microsoft Managed Desktop devices.</span></span> 

<span data-ttu-id="7dd23-105">Para exibir os dados de uso, selecione a guia <strong>atualizações de segurança do Windows</strong> .</span><span class="sxs-lookup"><span data-stu-id="7dd23-105">To view usage data, select the <strong>Windows security updates</strong> tab.</span></span>

![Painel de atualizações de segurança do Windows: barras de gráfico de status do dispositivo e versão de atualização na coluna à esquerda, atualizar o progresso da implantação ao longo do tempo na coluna central e a porcentagem de dispositivos ativos por grupo de implantação, bem como o número de dias obtidos para chegar à implantação de 95% destino na coluna direita.](../../media/update-insights.jpg)

## <a name="device-status"></a><span data-ttu-id="7dd23-107">Status do dispositivo</span><span class="sxs-lookup"><span data-stu-id="7dd23-107">Device status</span></span>

<span data-ttu-id="7dd23-108">Para que os dispositivos sejam atualizados pelo Windows Update, eles devem estar conectados à Internet e não em hibernação por um mínimo de seis horas, dois dos quais devem ser contínuos.</span><span class="sxs-lookup"><span data-stu-id="7dd23-108">For devices to be updated by Windows Update, they must be connected to the Internet and not hibernating for a minimum of six hours, two of which must be continuous.</span></span> <span data-ttu-id="7dd23-109">Contanto que um dispositivo esteja conectado e não em hibernação, ele será considerado como "em uso".</span><span class="sxs-lookup"><span data-stu-id="7dd23-109">As long as a device is connected and not hibernating, it's considered to be "in use."</span></span> <span data-ttu-id="7dd23-110">Embora seja possível que um dispositivo que não atenda a esses requisitos seja atualizado, os dispositivos que atendem a eles têm a maior possibilidade de ser atualizado.</span><span class="sxs-lookup"><span data-stu-id="7dd23-110">Although it's possible that a device that doesn't meet these requirements will be updated, devices that meet them have the highest likelihood of being updated.</span></span> 

<span data-ttu-id="7dd23-111">Categorizamos a atividade do dispositivo no contexto do Windows Update com estes termos:</span><span class="sxs-lookup"><span data-stu-id="7dd23-111">We categorize device activity in the context of Windows Update with these terms:</span></span>

- <span data-ttu-id="7dd23-112"><strong>Ativo:</strong> Dispositivos que atenderam aos critérios de uso mínimo (seis horas, dois contínuos) para a versão mais recente da atualização de segurança e fizeram check-in com o Microsoft Intune pelo menos a cada cinco dias</span><span class="sxs-lookup"><span data-stu-id="7dd23-112"><strong>Active:</strong> Devices that have met the minimum usage criteria (six hours, two continuous) for the most recent security update release and have checked in with Microsoft Intune at least every five days</span></span>
- <span data-ttu-id="7dd23-113"><strong>Sincronizado:</strong> Dispositivos com check-in no Intune nos últimos 28 dias</span><span class="sxs-lookup"><span data-stu-id="7dd23-113"><strong>Synced:</strong> Devices that have checked in with Intune within the last 28 days</span></span>
- <span data-ttu-id="7dd23-114"><strong>Fora de sincronização:</strong> Dispositivos que <i>não</i> fizeram check-in com o Intune nos últimos 28 dias</span><span class="sxs-lookup"><span data-stu-id="7dd23-114"><strong>Out of sync:</strong> Devices that have <i>not</i> checked in with Intune in the last 28 days</span></span>




## <a name="update-version-status"></a><span data-ttu-id="7dd23-115">Atualizar status da versão</span><span class="sxs-lookup"><span data-stu-id="7dd23-115">Update version status</span></span>

<span data-ttu-id="7dd23-116">A Microsoft lança atualizações de segurança a cada segunda terça-feira do mês.</span><span class="sxs-lookup"><span data-stu-id="7dd23-116">Microsoft releases security updates every second Tuesday of the month.</span></span> <span data-ttu-id="7dd23-117">Cada versão adiciona atualizações importantes para vulnerabilidades de segurança conhecidas.</span><span class="sxs-lookup"><span data-stu-id="7dd23-117">Each release adds important updates for known security vulnerabilities.</span></span> <span data-ttu-id="7dd23-118">A área de trabalho gerenciada da Microsoft garante que 95% dos seus dispositivos gerenciados sejam atualizados com a atualização de segurança mais recente disponível a cada mês.</span><span class="sxs-lookup"><span data-stu-id="7dd23-118">Microsoft Managed Desktop ensures that 95% of its managed devices are updated with the latest available security update every month.</span></span> <span data-ttu-id="7dd23-119">As atualizações de segurança às vezes são lançadas em outros horários para lidar com urgência novas ameaças.</span><span class="sxs-lookup"><span data-stu-id="7dd23-119">Security updates are sometimes released at other times to urgently address new threats.</span></span> <span data-ttu-id="7dd23-120">O Microsoft Managed desktop implanta essas atualizações de maneira semelhante.</span><span class="sxs-lookup"><span data-stu-id="7dd23-120">Microsoft Managed Desktop deploys these updates in a similar fashion.</span></span>

<span data-ttu-id="7dd23-121">Categorizamos o status das versões de atualização de segurança com estes termos:</span><span class="sxs-lookup"><span data-stu-id="7dd23-121">We categorize the status of security update versions with these terms:</span></span>

- <span data-ttu-id="7dd23-122"><strong>Atual:</strong> Dispositivos que estão executando a atualização liberada no mês atual</span><span class="sxs-lookup"><span data-stu-id="7dd23-122"><strong>Current:</strong> Devices that are running the update released in the current month</span></span>
- <span data-ttu-id="7dd23-123"><strong>Anterior:</strong> Dispositivos executando a atualização lançada no mês anterior</span><span class="sxs-lookup"><span data-stu-id="7dd23-123"><strong>Previous:</strong> Devices running the update that was released in the previous month</span></span>
- <span data-ttu-id="7dd23-124"><strong>Mais antigo:</strong> Dispositivos executando qualquer atualização de segurança lançada antes do mês anterior</span><span class="sxs-lookup"><span data-stu-id="7dd23-124"><strong>Older:</strong> Devices running any security update released prior to the previous month</span></span>

<span data-ttu-id="7dd23-125">Você deve ver alguns dispositivos na categoria <strong>antigo</strong> – uma população grande ou crescente provavelmente indica um problema do sistema que você deve relatar à área de trabalho gerenciada da Microsoft para que possamos investigar.</span><span class="sxs-lookup"><span data-stu-id="7dd23-125">You should see few devices in the <strong>Older</strong> category--a large or growing population probably indicates a systemic problem that you should report to Microsoft Managed Desktop so we can investigate.</span></span>


## <a name="deployment-progress"></a><span data-ttu-id="7dd23-126">Progresso da implantação</span><span class="sxs-lookup"><span data-stu-id="7dd23-126">Deployment progress</span></span>

<span data-ttu-id="7dd23-127">No início de cada ciclo de lançamento de atualização de segurança, a área de trabalho gerenciada da Microsoft faz um instantâneo da população de dispositivos e define seu destino de implantação em 95% dessa população.</span><span class="sxs-lookup"><span data-stu-id="7dd23-127">At the beginning of each security update release cycle, Microsoft Managed Desktop takes a snapshot of the device population and sets its deployment target at 95% of that population.</span></span> <span data-ttu-id="7dd23-128">A área de <strong>progresso da implantação</strong> mostra uma tendência histórica, atualizada diariamente, controlando o quanto a implantação da atualização atende a esse destino para cada versão.</span><span class="sxs-lookup"><span data-stu-id="7dd23-128">The <strong>Deployment progress</strong> area shows a historical trend, updated daily, tracking how closely the update deployment meets this target for each release.</span></span> <span data-ttu-id="7dd23-129">Este gráfico mostra apenas dispositivos com status ativo.</span><span class="sxs-lookup"><span data-stu-id="7dd23-129">This graph only shows devices with Active status.</span></span>

<span data-ttu-id="7dd23-130">Você pode exibir esses dados para ciclos de atualização anteriores usando o menu suspenso no canto superior direito.</span><span class="sxs-lookup"><span data-stu-id="7dd23-130">You can view this data for previous update cycles by using the dropdown menu in the upper right.</span></span> <span data-ttu-id="7dd23-131">O período selecionado neste menu aplica-se a todas as informações na página inteira.</span><span class="sxs-lookup"><span data-stu-id="7dd23-131">The period you select in this menu applies to all of the information on the whole page.</span></span>

<span data-ttu-id="7dd23-132">A área atualização de <strong>dispositivos ativos por grupo de implantação</strong> oferece um modo de exibição diferente mostrando o progresso da instalação da atualização para cada um dos grupos de implantação de área de trabalho gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7dd23-132">The <strong>Updated active devices by deployment group</strong> area offers a different view by showing the progress of the update installation for each of the Microsoft Managed Desktop deployment groups.</span></span>

<span data-ttu-id="7dd23-133">Os <strong>dias para atingir a área de destino</strong> exibe quanto tempo levou para 95% do número total de dispositivos a serem atualizados com a atualização de segurança atual.</span><span class="sxs-lookup"><span data-stu-id="7dd23-133">The <strong>Days to reach target</strong> area displays how long it took for 95% of the total number of devices to be updated with the current security update.</span></span> <span data-ttu-id="7dd23-134">Enquanto a implantação estiver em andamento, esta área exibirá a <strong>atualização ainda</strong> até que o destino de 95% seja alcançado para a atualização selecionada.</span><span class="sxs-lookup"><span data-stu-id="7dd23-134">While deployment is underway, this area displays <strong>Still updating</strong> until the 95% target is reached for the selected update.</span></span>

## <a name="device-details-area"></a><span data-ttu-id="7dd23-135">Área de detalhes do dispositivo</span><span class="sxs-lookup"><span data-stu-id="7dd23-135">Device details area</span></span>

<span data-ttu-id="7dd23-136">A parte inferior do painel é uma tabela que mostra informações detalhadas para seus dispositivos, incluindo o [status do dispositivo](#device-status) e o status da versão da [atualização](#update-version-status).</span><span class="sxs-lookup"><span data-stu-id="7dd23-136">The bottom of the dashboard is a table showing detailed information for your devices, including the [Device status](#device-status) and the [Update version status](#update-version-status).</span></span> <span data-ttu-id="7dd23-137">Você pode pesquisar esta lista ou filtrá-la por qualquer valor listado.</span><span class="sxs-lookup"><span data-stu-id="7dd23-137">You can search this list or filter it by any listed value.</span></span>


![Tabela de detalhes do dispositivo mostrando colunas para nome do dispositivo, usuário atribuído, status do dispositivo, versão da atualização, versão do sistema operacional e a data em que o dispositivo foi sincronizado pela última vez.](../../media/security-update-insights-device-table-sterile.png)
