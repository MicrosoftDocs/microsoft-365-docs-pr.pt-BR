---
title: Coletar logs de suporte no Microsoft Defender para Pontos de Extremidade usando a resposta ao vivo
description: Saiba como coletar logs usando a resposta ao vivo para solucionar problemas do Microsoft Defender para Pontos de Extremidade
keywords: support, log, collect, troubleshoot, live response, liveanalyzer, analyzer, live, response
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
ms.collection: M365-security-compliance
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: 07593fac6ed9a3fbc00d904718380b386f31dba3
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893408"
---
# <a name="collect-support-logs-in-microsoft-defender-for-endpoint-using-live-response"></a><span data-ttu-id="b1cd4-104">Coletar logs de suporte no Microsoft Defender para Ponto de Extremidade usando a resposta ao vivo</span><span class="sxs-lookup"><span data-stu-id="b1cd4-104">Collect support logs in Microsoft Defender for Endpoint using live response</span></span> 


<span data-ttu-id="b1cd4-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="b1cd4-105">**Applies to:**</span></span>
- [<span data-ttu-id="b1cd4-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="b1cd4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b1cd4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b1cd4-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="b1cd4-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="b1cd4-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b1cd4-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


<span data-ttu-id="b1cd4-110">Ao contatar o suporte, você pode ser solicitado a fornecer o pacote de saída da ferramenta Analisador de Cliente do Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-110">When contacting support, you may be asked to provide the output package of the Microsoft Defender for Endpoint Client Analyzer tool.</span></span>

<span data-ttu-id="b1cd4-111">Este tópico fornece instruções sobre como executar a ferramenta por meio do Live Response.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-111">This topic provides instructions on how to run the tool via Live Response.</span></span>

1. <span data-ttu-id="b1cd4-112">Baixar o script apropriado</span><span class="sxs-lookup"><span data-stu-id="b1cd4-112">Download the appropriate script</span></span>
    * <span data-ttu-id="b1cd4-113">O Microsoft Defender for Endpoint client logs only: [LiveAnalyzer.ps1 script](https://aka.ms/MDELiveAnalyzer).</span><span class="sxs-lookup"><span data-stu-id="b1cd4-113">Microsoft Defender for Endpoint client sensor logs only: [LiveAnalyzer.ps1 script](https://aka.ms/MDELiveAnalyzer).</span></span>
      - <span data-ttu-id="b1cd4-114">Tamanho aproximado do pacote de resultados: ~100Kb</span><span class="sxs-lookup"><span data-stu-id="b1cd4-114">Result package approximate size: ~100Kb</span></span> 
    *  <span data-ttu-id="b1cd4-115">Sensor de cliente do Microsoft Defender para Ponto de Extremidade e logs antivírus: [LiveAnalyzer+MDAV.ps1 script](https://aka.ms/MDELiveAnalyzerAV).</span><span class="sxs-lookup"><span data-stu-id="b1cd4-115">Microsoft Defender for Endpoint client sensor and Antivirus logs: [LiveAnalyzer+MDAV.ps1 script](https://aka.ms/MDELiveAnalyzerAV).</span></span>
       - <span data-ttu-id="b1cd4-116">Tamanho aproximado do pacote de resultados: ~10 Mb</span><span class="sxs-lookup"><span data-stu-id="b1cd4-116">Result package approximate size: ~10Mb</span></span> 
 
2.  <span data-ttu-id="b1cd4-117">Inicie uma [sessão de Resposta Ao](live-response.md#initiate-a-live-response-session-on-a-device) Vivo no computador que você precisa investigar.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-117">Initiate a [Live Response session](live-response.md#initiate-a-live-response-session-on-a-device) on the machine you need to investigate.</span></span>

3.  <span data-ttu-id="b1cd4-118">Selecione **Upload arquivo para biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-118">Select **Upload file to library**.</span></span>

    ![Imagem do arquivo de carregamento](images/upload-file.png)

4. <span data-ttu-id="b1cd4-120">Selecione **Escolher arquivo**.</span><span class="sxs-lookup"><span data-stu-id="b1cd4-120">Select **Choose file**.</span></span>

    ![Imagem do botão escolher arquivo1](images/choose-file.png)

5. <span data-ttu-id="b1cd4-122">Selecione o arquivo baixado chamado MDELiveAnalyzer.ps1 e clique em **Confirmar**</span><span class="sxs-lookup"><span data-stu-id="b1cd4-122">Select the downloaded file named MDELiveAnalyzer.ps1 and then click on **Confirm**</span></span>


   ![Imagem do botão escolher arquivo2](images/analyzer-file.png)


6. <span data-ttu-id="b1cd4-124">Enquanto ainda estiver na sessão LiveResponse, use os comandos abaixo para executar o analisador e coletar o arquivo de resultados:</span><span class="sxs-lookup"><span data-stu-id="b1cd4-124">While still in the LiveResponse session, use the commands below to run the analyzer and collect the result file:</span></span>

    ```console
    Run MDELiveAnalyzer.ps1
    GetFile "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\MDEClientAnalyzerResult.zip" -auto
    ```

    <span data-ttu-id="b1cd4-125">[![Imagem de comandos ](images/analyzer-commands.png)](images/analyzer-commands.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="b1cd4-125">[ ![Image of commands](images/analyzer-commands.png) ](images/analyzer-commands.png#lightbox)</span></span>


>[!NOTE]
> - <span data-ttu-id="b1cd4-126">A versão de visualização mais recente do MDEClientAnalyzer pode ser baixada aqui: [https://aka.ms/Betamdeanalyzer](https://aka.ms/Betamdeanalyzer) .</span><span class="sxs-lookup"><span data-stu-id="b1cd4-126">The latest preview version of MDEClientAnalyzer can be downloaded here: [https://aka.ms/Betamdeanalyzer](https://aka.ms/Betamdeanalyzer).</span></span>
> 
> - <span data-ttu-id="b1cd4-127">O script LiveAnalyzer baixa o pacote de solução de problemas no computador de destino de: https://mdatpclientanalyzer.blob.core.windows.net .</span><span class="sxs-lookup"><span data-stu-id="b1cd4-127">The LiveAnalyzer script downloads the troubleshooting package on the destination machine from: https://mdatpclientanalyzer.blob.core.windows.net.</span></span>
> 
>   <span data-ttu-id="b1cd4-128">Se você não puder permitir que o computador alcance a URL acima, carregue MDEClientAnalyzerPreview.zip arquivo na biblioteca antes de executar o script LiveAnalyzer:</span><span class="sxs-lookup"><span data-stu-id="b1cd4-128">If you cannot allow the machine to reach the above URL, then upload MDEClientAnalyzerPreview.zip file to the library before running the LiveAnalyzer script:</span></span>
>
>   ```console
>   PutFile MDEClientAnalyzerPreview.zip -overwrite
>   Run MDELiveAnalyzer.ps1
>   GetFile "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\MDEClientAnalyzerResult.zip" -auto
>   ```
> 
> - <span data-ttu-id="b1cd4-129">Para obter mais informações sobre como coletar dados localmente em um computador caso o computador não se comunique com o Microsoft Defender para serviços de nuvem do Ponto de Extremidade ou não apareça no portal do Microsoft Defender para Ponto de Extremidade, conforme esperado, consulte [Verify client connectivity to Microsoft Defender for Endpoint service URLs](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls).</span><span class="sxs-lookup"><span data-stu-id="b1cd4-129">For more information on gathering data locally on a machine in case the machine isn't communicating with Microsoft Defender for Endpoint cloud services, or does not appear in Microsoft Defender for Endpoint portal as expected, see [Verify client connectivity to Microsoft Defender for Endpoint service URLs](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls).</span></span>
