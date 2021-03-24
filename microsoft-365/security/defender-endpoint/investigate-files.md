---
title: Investigar arquivos do Microsoft Defender para o Ponto de Extremidade
description: Use as opções de investigação para obter detalhes sobre arquivos associados a alertas, comportamentos ou eventos.
keywords: investigar, investigar, arquivo, atividade mal-intencionada, motivação de ataque, análise profunda, relatório de análise profunda
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: a801b6153cf3f273290721756440cfe974103e92
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053476"
---
# <a name="investigate-a-file-associated-with-a-microsoft-defender-for-endpoint-alert"></a><span data-ttu-id="9dc89-104">Investigar um arquivo associado a um alerta do Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="9dc89-104">Investigate a file associated with a Microsoft Defender for Endpoint alert</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9dc89-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="9dc89-105">**Applies to:**</span></span>
- [<span data-ttu-id="9dc89-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="9dc89-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="9dc89-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9dc89-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="9dc89-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="9dc89-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="9dc89-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="9dc89-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatefiles-abovefoldlink)

<span data-ttu-id="9dc89-110">Investigue os detalhes de um arquivo associado a um alerta, comportamento ou evento específico para ajudar a determinar se o arquivo exibe atividades mal-intencionadas, identificar a motivação de ataque e entender o escopo potencial da violação.</span><span class="sxs-lookup"><span data-stu-id="9dc89-110">Investigate the details of a file associated with a specific alert, behavior, or event to help determine if the file exhibits malicious activities, identify the attack motivation, and understand the potential scope of the breach.</span></span>

<span data-ttu-id="9dc89-111">Há muitas maneiras de acessar a página de perfil detalhada de um arquivo específico.</span><span class="sxs-lookup"><span data-stu-id="9dc89-111">There are many ways to access the detailed profile page of a specific file.</span></span> <span data-ttu-id="9dc89-112">Por exemplo, você pode usar o recurso de pesquisa, clicar em um link da árvore de processo **alerta,** gráfico de **incidentes,** linha do tempo de artefato **ou** selecionar um evento listado na linha do tempo **do dispositivo.**</span><span class="sxs-lookup"><span data-stu-id="9dc89-112">For example, you can  use the search feature, click on a link from the **Alert process tree**, **Incident graph**, **Artifact timeline**, or select an event listed in the **Device timeline**.</span></span>

<span data-ttu-id="9dc89-113">Uma vez na página de perfil detalhada, você pode alternar entre os layouts de página novo e antigo, alternando a **nova página Arquivo.**</span><span class="sxs-lookup"><span data-stu-id="9dc89-113">Once on the detailed profile page, you can switch between the new and old page layouts by toggling **new File page**.</span></span> <span data-ttu-id="9dc89-114">O restante deste artigo descreve o layout da página mais recente.</span><span class="sxs-lookup"><span data-stu-id="9dc89-114">The rest of this article describes the newer page layout.</span></span>

<span data-ttu-id="9dc89-115">Você pode obter informações das seções a seguir no exibição de arquivo:</span><span class="sxs-lookup"><span data-stu-id="9dc89-115">You can get information from the following sections in the file view:</span></span>

- <span data-ttu-id="9dc89-116">Detalhes do arquivo, detecção de malware, prevalência de arquivo</span><span class="sxs-lookup"><span data-stu-id="9dc89-116">File details, Malware detection, File prevalence</span></span>
- <span data-ttu-id="9dc89-117">Análise profunda</span><span class="sxs-lookup"><span data-stu-id="9dc89-117">Deep analysis</span></span>
- <span data-ttu-id="9dc89-118">Alertas</span><span class="sxs-lookup"><span data-stu-id="9dc89-118">Alerts</span></span>
- <span data-ttu-id="9dc89-119">Observado na organização</span><span class="sxs-lookup"><span data-stu-id="9dc89-119">Observed in organization</span></span>
- <span data-ttu-id="9dc89-120">Análise profunda</span><span class="sxs-lookup"><span data-stu-id="9dc89-120">Deep analysis</span></span>
- <span data-ttu-id="9dc89-121">Nomes de arquivos</span><span class="sxs-lookup"><span data-stu-id="9dc89-121">File names</span></span>

<span data-ttu-id="9dc89-122">Você também pode tomar medidas em um arquivo desta página.</span><span class="sxs-lookup"><span data-stu-id="9dc89-122">You can also take action on a file from this page.</span></span>

## <a name="file-actions"></a><span data-ttu-id="9dc89-123">Ações de arquivo</span><span class="sxs-lookup"><span data-stu-id="9dc89-123">File actions</span></span>

<span data-ttu-id="9dc89-124">Na parte superior da página de perfil, acima dos cartões de informações do arquivo.</span><span class="sxs-lookup"><span data-stu-id="9dc89-124">Along the top of the profile page, above the file information cards.</span></span> <span data-ttu-id="9dc89-125">As ações que você pode executar aqui incluem:</span><span class="sxs-lookup"><span data-stu-id="9dc89-125">Actions you can perform here include:</span></span>

- <span data-ttu-id="9dc89-126">Parar e colocar em quarentena</span><span class="sxs-lookup"><span data-stu-id="9dc89-126">Stop and quarantine</span></span>
- <span data-ttu-id="9dc89-127">Indicador de adicionar/editar</span><span class="sxs-lookup"><span data-stu-id="9dc89-127">Add/edit indicator</span></span>
- <span data-ttu-id="9dc89-128">Baixar o arquivo</span><span class="sxs-lookup"><span data-stu-id="9dc89-128">Download file</span></span>
- <span data-ttu-id="9dc89-129">Consultar um especialista em ameaças</span><span class="sxs-lookup"><span data-stu-id="9dc89-129">Consult a threat expert</span></span>
- <span data-ttu-id="9dc89-130">Central de ações</span><span class="sxs-lookup"><span data-stu-id="9dc89-130">Action center</span></span>

<span data-ttu-id="9dc89-131">Para obter mais informações sobre essas ações, consulte [Take response action on a file](respond-file-alerts.md).</span><span class="sxs-lookup"><span data-stu-id="9dc89-131">For more information on these actions, see [Take response action on a file](respond-file-alerts.md).</span></span>

## <a name="file-details-malware-detection-and-file-prevalence"></a><span data-ttu-id="9dc89-132">Detalhes do arquivo, detecção de malware e prevalência de arquivo</span><span class="sxs-lookup"><span data-stu-id="9dc89-132">File details, Malware detection, and File prevalence</span></span>

<span data-ttu-id="9dc89-133">Os detalhes do arquivo, incidente, detecção de malware e cartões de prevalência de arquivo exibem vários atributos sobre o arquivo.</span><span class="sxs-lookup"><span data-stu-id="9dc89-133">The file details, incident, malware detection, and file prevalence cards display various attributes about the file.</span></span>

<span data-ttu-id="9dc89-134">Você verá detalhes como o MD5 do arquivo, a taxa de detecção total de vírus e a detecção do Microsoft Defender AV, se disponível, e a prevalência do arquivo.</span><span class="sxs-lookup"><span data-stu-id="9dc89-134">You'll see details such as the file’s MD5, the Virus Total detection ratio, and Microsoft Defender AV detection if available, and the file’s prevalence.</span></span>

<span data-ttu-id="9dc89-135">O cartão de prevalência de arquivo mostra onde o arquivo foi visto em dispositivos na organização e em todo o mundo.</span><span class="sxs-lookup"><span data-stu-id="9dc89-135">The file prevalence card shows where the file was seen in devices in the organization and worldwide.</span></span> 

> [!NOTE] 
> <span data-ttu-id="9dc89-136">Diferentes usuários podem ver valores diferentes nos dispositivos na seção *organização* do cartão de prevalência do arquivo.</span><span class="sxs-lookup"><span data-stu-id="9dc89-136">Different users may see dissimilar values in the *devices in organization* section of the file prevalence card.</span></span> <span data-ttu-id="9dc89-137">Isso porque o cartão exibe informações com base no escopo RBAC que um usuário tem.</span><span class="sxs-lookup"><span data-stu-id="9dc89-137">This is because the card displays information based on the RBAC scope that a user has.</span></span> <span data-ttu-id="9dc89-138">Ou seja, se um usuário tiver sido concedido visibilidade em um conjunto específico de dispositivos, ele verá apenas a prevalência organizacional do arquivo nesses dispositivos.</span><span class="sxs-lookup"><span data-stu-id="9dc89-138">Meaning, if a user has been granted visibility on a specific set of devices, they will only see the file organizational prevalence on those devices.</span></span>

![Imagem das informações do arquivo](images/atp-file-information.png)

## <a name="alerts"></a><span data-ttu-id="9dc89-140">Alertas</span><span class="sxs-lookup"><span data-stu-id="9dc89-140">Alerts</span></span>

<span data-ttu-id="9dc89-141">A **guia Alertas** fornece uma lista de alertas associados ao arquivo.</span><span class="sxs-lookup"><span data-stu-id="9dc89-141">The **Alerts** tab provides a list of alerts that are associated with the file.</span></span> <span data-ttu-id="9dc89-142">Esta lista abrange grande parte das mesmas informações que a fila de Alertas, exceto para o grupo de dispositivos, se algum, o dispositivo afetado pertence.</span><span class="sxs-lookup"><span data-stu-id="9dc89-142">This list covers much of the same information as the Alerts queue, except for the device group, if any, the affected device belongs to.</span></span> <span data-ttu-id="9dc89-143">Você pode escolher que tipo de informação é mostrada selecionando **Personalizar colunas** na barra de ferramentas acima dos headers da coluna.</span><span class="sxs-lookup"><span data-stu-id="9dc89-143">You can choose what kind of information is shown by selecting **Customize columns** from the toolbar above the column headers.</span></span>

![Imagem de alertas relacionados à seção arquivo](images/atp-alerts-related-to-file.png)

## <a name="observed-in-organization"></a><span data-ttu-id="9dc89-145">Observado na organização</span><span class="sxs-lookup"><span data-stu-id="9dc89-145">Observed in organization</span></span>

<span data-ttu-id="9dc89-146">A **guia Observado na organização** permite que você especifique um intervalo de datas para ver quais dispositivos foram observados com o arquivo.</span><span class="sxs-lookup"><span data-stu-id="9dc89-146">The **Observed in organization** tab allows you to specify a date range to see which devices have been observed with the file.</span></span>

>[!NOTE]
><span data-ttu-id="9dc89-147">Esta guia mostrará um número máximo de 100 dispositivos.</span><span class="sxs-lookup"><span data-stu-id="9dc89-147">This tab will show a maximum number of 100 devices.</span></span> <span data-ttu-id="9dc89-148">Para ver _todos os_ dispositivos com o arquivo, exporte a guia para um arquivo CSV, selecionando **Exportar** no menu ação acima dos headers da coluna da guia.</span><span class="sxs-lookup"><span data-stu-id="9dc89-148">To see _all_ devices with the file, export the tab to a CSV file, by selecting **Export** from the action menu above the tab's column headers.</span></span>

![Imagem do dispositivo observado mais recente com o arquivo](images/atp-observed-machines.png)

<span data-ttu-id="9dc89-150">Use o controle deslizante ou o seletor de intervalo para especificar rapidamente um período de tempo que você deseja verificar se há eventos envolvendo o arquivo.</span><span class="sxs-lookup"><span data-stu-id="9dc89-150">Use the slider or the range selector to quickly specify a time period that you want to check for events involving the file.</span></span> <span data-ttu-id="9dc89-151">Você pode especificar uma janela de tempo tão pequena quanto um único dia.</span><span class="sxs-lookup"><span data-stu-id="9dc89-151">You can specify a time window as small as a single day.</span></span> <span data-ttu-id="9dc89-152">Isso permitirá que você veja apenas arquivos que se comunicaram com esse Endereço IP naquele momento, reduzindo drasticamente a rolagem e a pesquisa desnecessárias.</span><span class="sxs-lookup"><span data-stu-id="9dc89-152">This will allow you to see only files that communicated with that IP Address at that time, drastically reducing unnecessary scrolling and searching.</span></span>

## <a name="deep-analysis"></a><span data-ttu-id="9dc89-153">Análise profunda</span><span class="sxs-lookup"><span data-stu-id="9dc89-153">Deep analysis</span></span>

<span data-ttu-id="9dc89-154">A **guia** Análise Profunda permite que você envie o arquivo para análise [profunda,](respond-file-alerts.md#deep-analysis)para descobrir mais detalhes sobre o comportamento do arquivo, bem como o efeito que ele está tendo em suas organizações.</span><span class="sxs-lookup"><span data-stu-id="9dc89-154">The **Deep analysis** tab allows you to [submit the file for deep analysis](respond-file-alerts.md#deep-analysis), to uncover more details about the file's behavior, as well as the effect it is having within your organizations.</span></span> <span data-ttu-id="9dc89-155">Depois de enviar o arquivo, o relatório de análise profunda aparecerá nesta guia quando os resultados estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="9dc89-155">After you submit the file, the deep analysis report will appear in this tab once results are available.</span></span> <span data-ttu-id="9dc89-156">Se a análise profunda não encontrar nada, o relatório ficará vazio e o espaço de resultados permanecerá em branco.</span><span class="sxs-lookup"><span data-stu-id="9dc89-156">If deep analysis did not find anything, the report will be empty and the results space will remain blank.</span></span>

![Imagem da guia análise profunda](images/submit-file.png)

## <a name="file-names"></a><span data-ttu-id="9dc89-158">Nomes de arquivos</span><span class="sxs-lookup"><span data-stu-id="9dc89-158">File names</span></span>

<span data-ttu-id="9dc89-159">A **guia Nomes de** arquivo lista todos os nomes que o arquivo foi observado para usar em suas organizações.</span><span class="sxs-lookup"><span data-stu-id="9dc89-159">The **File names** tab lists all names the file has been observed to use, within your organizations.</span></span>

![Guia Imagem de nomes de arquivo](images/atp-file-names.png)

## <a name="related-topics"></a><span data-ttu-id="9dc89-161">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="9dc89-161">Related topics</span></span>

- [<span data-ttu-id="9dc89-162">Exibir e organizar a fila do Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="9dc89-162">View and organize the Microsoft Defender for Endpoint queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="9dc89-163">Gerenciar alertas do Microsoft Defender para Pontos de Extremidade</span><span class="sxs-lookup"><span data-stu-id="9dc89-163">Manage Microsoft Defender for Endpoint alerts</span></span>](manage-alerts.md)
- [<span data-ttu-id="9dc89-164">Investigar alertas do Microsoft Defender para Pontos de Extremidade</span><span class="sxs-lookup"><span data-stu-id="9dc89-164">Investigate Microsoft Defender for Endpoint alerts</span></span>](investigate-alerts.md)
- [<span data-ttu-id="9dc89-165">Investigar dispositivos na lista do Microsoft Defender for Endpoint Devices</span><span class="sxs-lookup"><span data-stu-id="9dc89-165">Investigate devices in the Microsoft Defender for Endpoint Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="9dc89-166">Investigar um endereço IP associado a um alerta do Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="9dc89-166">Investigate an IP address associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-ip.md)
- [<span data-ttu-id="9dc89-167">Investigar um domínio associado a um alerta do Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="9dc89-167">Investigate a domain associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-domain.md)
- [<span data-ttu-id="9dc89-168">Investigar uma conta de usuário no Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="9dc89-168">Investigate a user account in Microsoft Defender for Endpoint</span></span>](investigate-user.md)
- [<span data-ttu-id="9dc89-169">Tomar ações de resposta em um arquivo</span><span class="sxs-lookup"><span data-stu-id="9dc89-169">Take response actions on a file</span></span>](respond-file-alerts.md)
