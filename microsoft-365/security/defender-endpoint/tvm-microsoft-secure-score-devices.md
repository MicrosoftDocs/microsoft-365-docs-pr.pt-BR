---
title: Microsoft Secure Score para dispositivos
description: Sua pontuação para dispositivos mostra o estado de configuração de segurança coletiva de seus dispositivos em aplicativos, sistema operacional, rede, contas e controles de segurança.
keywords: Microsoft Secure Score for Devices, mdatp Microsoft Secure Score for Devices, secure score, configuration score, threat and vulnerability management, security controls, improvement opportunities, security configuration score over time, security posture, baseline
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
ms.openlocfilehash: fcf33b309045b9ca763b0d3cabc44fb13505ee0b
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500049"
---
# <a name="microsoft-secure-score-for-devices"></a><span data-ttu-id="91423-104">Microsoft Secure Score para dispositivos</span><span class="sxs-lookup"><span data-stu-id="91423-104">Microsoft Secure Score for Devices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="91423-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="91423-105">**Applies to:**</span></span>

- [<span data-ttu-id="91423-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="91423-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="91423-107">Gerenciamento de ameaças e vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="91423-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="91423-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="91423-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="91423-109">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="91423-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="91423-110">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="91423-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


>[!NOTE]
> <span data-ttu-id="91423-111">A pontuação de configuração agora faz parte do gerenciamento de ameaças e vulnerabilidades como Pontuação Segura da Microsoft para Dispositivos.</span><span class="sxs-lookup"><span data-stu-id="91423-111">Configuration score is now part of threat and vulnerability management as Microsoft Secure Score for Devices.</span></span>

<span data-ttu-id="91423-112">Sua pontuação para dispositivos está visível no painel de gerenciamento de ameaças e [vulnerabilidades](tvm-dashboard-insights.md) do Centro de Segurança do Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="91423-112">Your score for devices is visible in the [threat and vulnerability management dashboard](tvm-dashboard-insights.md) of the Microsoft Defender Security Center.</span></span> <span data-ttu-id="91423-113">Uma pontuação segura da Microsoft mais alta para dispositivos significa que seus pontos de extremidade são mais resilientes contra ataques de ameaças de segurança cibernética.</span><span class="sxs-lookup"><span data-stu-id="91423-113">A higher Microsoft Secure Score for Devices means your endpoints are more resilient from cybersecurity threat attacks.</span></span> <span data-ttu-id="91423-114">Ele reflete o estado de configuração de segurança coletiva de seus dispositivos nas seguintes categorias:</span><span class="sxs-lookup"><span data-stu-id="91423-114">It reflects the collective security configuration state of your devices across the following categories:</span></span>

- <span data-ttu-id="91423-115">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="91423-115">Application</span></span>
- <span data-ttu-id="91423-116">Sistema operacional</span><span class="sxs-lookup"><span data-stu-id="91423-116">Operating system</span></span>
- <span data-ttu-id="91423-117">Rede</span><span class="sxs-lookup"><span data-stu-id="91423-117">Network</span></span>
- <span data-ttu-id="91423-118">Contas</span><span class="sxs-lookup"><span data-stu-id="91423-118">Accounts</span></span>
- <span data-ttu-id="91423-119">Controles de segurança</span><span class="sxs-lookup"><span data-stu-id="91423-119">Security controls</span></span>

<span data-ttu-id="91423-120">Selecione uma categoria para ir até a página [**Recomendações de**](tvm-security-recommendation.md) segurança e exibir as recomendações relevantes.</span><span class="sxs-lookup"><span data-stu-id="91423-120">Select a category to go to the [**Security recommendations**](tvm-security-recommendation.md) page and view the relevant recommendations.</span></span>

## <a name="turn-on-the-microsoft-secure-score-connector"></a><span data-ttu-id="91423-121">Ativar o conector de Pontuação Segura da Microsoft</span><span class="sxs-lookup"><span data-stu-id="91423-121">Turn on the Microsoft Secure Score connector</span></span>

<span data-ttu-id="91423-122">Encaminhe o Microsoft Defender para sinais de ponto de extremidade, dando visibilidade da Pontuação Segura da Microsoft para a postura de segurança do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="91423-122">Forward Microsoft Defender for Endpoint signals, giving Microsoft Secure Score visibility into the device security posture.</span></span> <span data-ttu-id="91423-123">Os dados encaminhados são armazenados e processados no mesmo local que seus dados de Pontuação Segura da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="91423-123">Forwarded data is stored and processed in the same location as your Microsoft Secure Score data.</span></span>

<span data-ttu-id="91423-124">As alterações podem levar até algumas horas para refletir no painel.</span><span class="sxs-lookup"><span data-stu-id="91423-124">Changes might take up to a few hours to reflect in the dashboard.</span></span>

1. <span data-ttu-id="91423-125">No painel de navegação, acesse **Configurações**  >  **Recursos avançados**</span><span class="sxs-lookup"><span data-stu-id="91423-125">In the navigation pane, go to **Settings** > **Advanced features**</span></span> 

2. <span data-ttu-id="91423-126">Role para baixo até **Microsoft Secure Score** e alterne a configuração para **On**.</span><span class="sxs-lookup"><span data-stu-id="91423-126">Scroll down to **Microsoft Secure Score** and toggle the setting to **On**.</span></span>

3. <span data-ttu-id="91423-127">Selecione **Salvar preferências**.</span><span class="sxs-lookup"><span data-stu-id="91423-127">Select **Save preferences**.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="91423-128">Como funciona</span><span class="sxs-lookup"><span data-stu-id="91423-128">How it works</span></span>

>[!NOTE]
> <span data-ttu-id="91423-129">A Pontuação Segura da Microsoft para Dispositivos atualmente dá suporte a configurações definidas por meio da Política de Grupo.</span><span class="sxs-lookup"><span data-stu-id="91423-129">Microsoft Secure Score for Devices currently supports configurations set via Group Policy.</span></span> <span data-ttu-id="91423-130">Devido ao suporte parcial atual do Intune, as configurações que podem ter sido definidas por meio do Intune podem aparecer como mal configuradas.</span><span class="sxs-lookup"><span data-stu-id="91423-130">Due to the current partial Intune support, configurations which might have been set through Intune might show up as misconfigured.</span></span> <span data-ttu-id="91423-131">Entre em contato com o administrador de IT para verificar o status real da configuração caso sua organização use o Intune para gerenciamento de configuração seguro.</span><span class="sxs-lookup"><span data-stu-id="91423-131">Contact your IT Administrator to verify the actual configuration status in case your organization is using Intune for secure configuration management.</span></span>

<span data-ttu-id="91423-132">Os dados no cartão Microsoft Secure Score for Devices são o produto do processo de descoberta de vulnerabilidades meticulosa e contínua.</span><span class="sxs-lookup"><span data-stu-id="91423-132">The data in the Microsoft Secure Score for Devices card is the product of meticulous and ongoing vulnerability discovery process.</span></span> <span data-ttu-id="91423-133">Ele é agregado com avaliações de descoberta de configuração que continuamente:</span><span class="sxs-lookup"><span data-stu-id="91423-133">It is aggregated with configuration discovery assessments that continuously:</span></span>

- <span data-ttu-id="91423-134">Compare as configurações coletadas com os parâmetros de referência coletados para descobrir ativos mal configurados</span><span class="sxs-lookup"><span data-stu-id="91423-134">Compare collected configurations to the collected benchmarks to discover misconfigured assets</span></span>
- <span data-ttu-id="91423-135">Mapear configurações para vulnerabilidades que podem ser remediadas ou parcialmente remediadas (redução de risco)</span><span class="sxs-lookup"><span data-stu-id="91423-135">Map configurations to vulnerabilities that can be remediated or partially remediated (risk reduction)</span></span>
- <span data-ttu-id="91423-136">Coletar e manter os parâmetros de configuração de práticas (fornecedores, feeds de segurança, equipes de pesquisa internas)</span><span class="sxs-lookup"><span data-stu-id="91423-136">Collect and maintain best practice configuration benchmarks (vendors, security feeds, internal research teams)</span></span>
- <span data-ttu-id="91423-137">Coletar e monitorar alterações do estado de configuração do controle de segurança de todos os ativos</span><span class="sxs-lookup"><span data-stu-id="91423-137">Collect and monitor changes of security control configuration state from all assets</span></span>

## <a name="improve-your-security-configuration"></a><span data-ttu-id="91423-138">Melhorar sua configuração de segurança</span><span class="sxs-lookup"><span data-stu-id="91423-138">Improve your security configuration</span></span>

<span data-ttu-id="91423-139">Aprimora sua configuração de segurança, remediando problemas da lista de recomendações de segurança.</span><span class="sxs-lookup"><span data-stu-id="91423-139">Improve your security configuration by remediating issues from the security recommendations list.</span></span> <span data-ttu-id="91423-140">À medida que você faz isso, a Pontuação Segura da Microsoft para Dispositivos melhora e sua organização se torna mais resiliente contra ameaças e vulnerabilidades de segurança cibernética.</span><span class="sxs-lookup"><span data-stu-id="91423-140">As you do so, your Microsoft Secure Score for Devices improves and your organization becomes more resilient against cybersecurity threats and vulnerabilities.</span></span>

1. <span data-ttu-id="91423-141">No cartão Pontuação Segura da Microsoft para Dispositivos no painel de gerenciamento de ameaças e vulnerabilidades, selecione uma das categorias.</span><span class="sxs-lookup"><span data-stu-id="91423-141">From the Microsoft Secure Score for Devices card in the threat and vulnerability management dashboard, select the one of the categories.</span></span> <span data-ttu-id="91423-142">Você exibirá a lista de recomendações relacionadas a essa categoria.</span><span class="sxs-lookup"><span data-stu-id="91423-142">You'll view the list of recommendations related to that category.</span></span> <span data-ttu-id="91423-143">Ele levará você para a página [**Recomendações de**](tvm-security-recommendation.md) segurança.</span><span class="sxs-lookup"><span data-stu-id="91423-143">It will take you to the [**Security recommendations**](tvm-security-recommendation.md) page.</span></span> <span data-ttu-id="91423-144">Se você quiser ver todas as recomendações de segurança, depois de chegar à página Recomendações de segurança, desempure o campo de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="91423-144">If you want to see all security recommendations, once you get to the Security recommendations page, clear the search field.</span></span>

2. <span data-ttu-id="91423-145">Selecione um item na lista.</span><span class="sxs-lookup"><span data-stu-id="91423-145">Select an item on the list.</span></span> <span data-ttu-id="91423-146">O painel de sobremenu será aberto com detalhes relacionados à recomendação.</span><span class="sxs-lookup"><span data-stu-id="91423-146">The flyout panel will open with details related to the recommendation.</span></span> <span data-ttu-id="91423-147">Selecione **Opções de correção**.</span><span class="sxs-lookup"><span data-stu-id="91423-147">Select **Remediation options**.</span></span>

   ![Recomendações de segurança relacionadas a controles de segurança](images/tvm_security_controls.png)

3. <span data-ttu-id="91423-149">Leia a descrição para entender o contexto do problema e o que fazer em seguida.</span><span class="sxs-lookup"><span data-stu-id="91423-149">Read the description to understand the context of the issue and what to do next.</span></span> <span data-ttu-id="91423-150">Selecione uma data de vencimento, adicione anotações e selecione Exportar todos os dados de atividade de correção para **CSV** para que você possa anexá-los a um email para acompanhamento.</span><span class="sxs-lookup"><span data-stu-id="91423-150">Select a due date, add notes, and select **Export all remediation activity data to CSV** so you can attach it to an email for follow-up.</span></span>

4. <span data-ttu-id="91423-151">**Enviar solicitação**.</span><span class="sxs-lookup"><span data-stu-id="91423-151">**Submit request**.</span></span> <span data-ttu-id="91423-152">Você verá uma mensagem de confirmação de que a tarefa de correção foi criada.</span><span class="sxs-lookup"><span data-stu-id="91423-152">You'll see a confirmation message that the remediation task has been created.</span></span>
   <span data-ttu-id="91423-153">![Confirmação da criação de tarefas de correção](images/tvm_remediation_task_created.png)</span><span class="sxs-lookup"><span data-stu-id="91423-153">![Remediation task creation confirmation](images/tvm_remediation_task_created.png)</span></span>

5. <span data-ttu-id="91423-154">Salve seu arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="91423-154">Save your CSV file.</span></span>
   <span data-ttu-id="91423-155">![Salvar arquivo csv](images/tvm_save_csv_file.png)</span><span class="sxs-lookup"><span data-stu-id="91423-155">![Save csv file](images/tvm_save_csv_file.png)</span></span>

6. <span data-ttu-id="91423-156">Envie um email de acompanhamento para o administrador de TI e permita o tempo que você aloca para que a correção se propague no sistema.</span><span class="sxs-lookup"><span data-stu-id="91423-156">Send a follow-up email to your IT Administrator and allow the time that you've allotted for the remediation to propagate in the system.</span></span>

7. <span data-ttu-id="91423-157">Revise novamente **a Pontuação Segura da Microsoft para** Dispositivos no painel.</span><span class="sxs-lookup"><span data-stu-id="91423-157">Review the **Microsoft Secure Score for Devices** card again on the dashboard.</span></span> <span data-ttu-id="91423-158">O número de recomendações de controles de segurança diminuirá.</span><span class="sxs-lookup"><span data-stu-id="91423-158">The number of security controls recommendations will decrease.</span></span> <span data-ttu-id="91423-159">Quando você selecionar **Controles** de  segurança para voltar para a página Recomendações de segurança, o item que você endereça não será mais listado lá.</span><span class="sxs-lookup"><span data-stu-id="91423-159">When you select **Security controls** to go back to the **Security recommendations** page, the item that you've addressed won't be listed there anymore.</span></span> <span data-ttu-id="91423-160">A Pontuação Segura da Microsoft para Dispositivos deve aumentar.</span><span class="sxs-lookup"><span data-stu-id="91423-160">Your Microsoft Secure Score for Devices should increase.</span></span>

>[!IMPORTANT]
><span data-ttu-id="91423-161">Para aumentar suas taxas de detecção de avaliação de vulnerabilidade, baixe as seguintes atualizações de segurança obrigatórias e implante-as em sua rede:</span><span class="sxs-lookup"><span data-stu-id="91423-161">To boost your vulnerability assessment detection rates, download the following mandatory security updates and deploy them in your network:</span></span>
>- <span data-ttu-id="91423-162">Clientes 19H1 | [KB 4512941](https://support.microsoft.com/help/4512941/windows-10-update-kb4512941)</span><span class="sxs-lookup"><span data-stu-id="91423-162">19H1 customers | [KB 4512941](https://support.microsoft.com/help/4512941/windows-10-update-kb4512941)</span></span>
>- <span data-ttu-id="91423-163">Clientes RS5 | [KB 4516077](https://support.microsoft.com/help/4516077/windows-10-update-kb4516077)</span><span class="sxs-lookup"><span data-stu-id="91423-163">RS5 customers | [KB 4516077](https://support.microsoft.com/help/4516077/windows-10-update-kb4516077)</span></span>
>- <span data-ttu-id="91423-164">Clientes RS4 | [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)</span><span class="sxs-lookup"><span data-stu-id="91423-164">RS4 customers | [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)</span></span>
>- <span data-ttu-id="91423-165">Clientes RS3 | [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)</span><span class="sxs-lookup"><span data-stu-id="91423-165">RS3 customers | [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)</span></span>
>
><span data-ttu-id="91423-166">Para baixar as atualizações de segurança:</span><span class="sxs-lookup"><span data-stu-id="91423-166">To download the security updates:</span></span>
>1. <span data-ttu-id="91423-167">Vá para [o Catálogo de Atualizações da Microsoft.](https://www.catalog.update.microsoft.com/home.aspx)</span><span class="sxs-lookup"><span data-stu-id="91423-167">Go to [Microsoft Update Catalog](https://www.catalog.update.microsoft.com/home.aspx).</span></span>
>2. <span data-ttu-id="91423-168">Key-in the security update KB number that you need to download, then click **Search**.</span><span class="sxs-lookup"><span data-stu-id="91423-168">Key-in the security update KB number that you need to download, then click **Search**.</span></span>  

## <a name="related-topics"></a><span data-ttu-id="91423-169">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="91423-169">Related topics</span></span>

- [<span data-ttu-id="91423-170">Visão geral do gerenciamento de ameaças e vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="91423-170">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="91423-171">Painel</span><span class="sxs-lookup"><span data-stu-id="91423-171">Dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="91423-172">Pontuação de exposição</span><span class="sxs-lookup"><span data-stu-id="91423-172">Exposure score</span></span>](tvm-exposure-score.md)
- [<span data-ttu-id="91423-173">Recomendações de segurança</span><span class="sxs-lookup"><span data-stu-id="91423-173">Security recommendations</span></span>](tvm-security-recommendation.md)
