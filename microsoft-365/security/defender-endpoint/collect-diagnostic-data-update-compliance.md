---
title: Coletar dados de diagnóstico para Atualização de Conformidade e Windows Defender Microsoft Defender Antivírus
description: Use uma ferramenta para coletar dados para solucionar problemas de Conformidade de Atualização ao usar o complemento da Avaliação do Microsoft Defender Antivírus
keywords: solução de problemas, erro, correção, conformidade de atualização, oms, monitor, relatório, Microsoft Defender AV
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: f2b3060d7f0d9daf0f923c674f2fe45ba976fdfc
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764730"
---
# <a name="collect-update-compliance-diagnostic-data-for-microsoft-defender-av-assessment"></a><span data-ttu-id="d7dd7-104">Coletar dados de diagnóstico de Conformidade de Atualização para Avaliação do Microsoft Defender AV</span><span class="sxs-lookup"><span data-stu-id="d7dd7-104">Collect Update Compliance diagnostic data for Microsoft Defender AV Assessment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="d7dd7-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="d7dd7-105">**Applies to:**</span></span>

- [<span data-ttu-id="d7dd7-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="d7dd7-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="d7dd7-107">Este artigo descreve como coletar dados de diagnóstico que podem ser usados pelas equipes de suporte e engenharia da Microsoft para ajudar a solucionar problemas que você pode encontrar ao usar a seção Avaliação do Microsoft Defender AV no complemento Conformidade de Atualização.</span><span class="sxs-lookup"><span data-stu-id="d7dd7-107">This article describes how to collect diagnostic data that can be used by Microsoft support and engineering teams to help troubleshoot issues you may encounter when using the Microsoft Defender AV Assessment section in the Update Compliance add-in.</span></span>

<span data-ttu-id="d7dd7-108">Antes de tentar esse processo, verifique se você leu Solucionar problemas de relatórios do [Microsoft Defender Antivírus](troubleshoot-reporting.md), atendeu a todos os pré-requisitos necessários e tomou todas as outras etapas sugeridas de solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="d7dd7-108">Before attempting this process, ensure you have read [Troubleshoot Microsoft Defender Antivirus reporting](troubleshoot-reporting.md), met all require prerequisites, and taken any other suggested troubleshooting steps.</span></span>

<span data-ttu-id="d7dd7-109">Em pelo menos dois dispositivos que não estão relatando ou aparecendo em Conformidade de Atualização, obtenha o arquivo de diagnóstico .cab seguindo as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="d7dd7-109">On at least two devices that are not reporting or showing up in Update Compliance, obtain the .cab diagnostic file by taking the following steps:</span></span>

1. <span data-ttu-id="d7dd7-110">Abra uma versão no nível de administrador do prompt de comando da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="d7dd7-110">Open an administrator-level version of the command prompt as follows:</span></span>
        
    <span data-ttu-id="d7dd7-111">a.</span><span class="sxs-lookup"><span data-stu-id="d7dd7-111">a.</span></span> <span data-ttu-id="d7dd7-112">Abra o menu **Iniciar.**</span><span class="sxs-lookup"><span data-stu-id="d7dd7-112">Open the **Start** menu.</span></span>

    <span data-ttu-id="d7dd7-113">b.</span><span class="sxs-lookup"><span data-stu-id="d7dd7-113">b.</span></span> <span data-ttu-id="d7dd7-114">Digite **cmd**.</span><span class="sxs-lookup"><span data-stu-id="d7dd7-114">Type **cmd**.</span></span> <span data-ttu-id="d7dd7-115">Clique com o botão direito do mouse **no Prompt de** Comando e clique em Executar como **administrador**.</span><span class="sxs-lookup"><span data-stu-id="d7dd7-115">Right-click on **Command Prompt** and click **Run as administrator**.</span></span>

    <span data-ttu-id="d7dd7-116">c.</span><span class="sxs-lookup"><span data-stu-id="d7dd7-116">c.</span></span> <span data-ttu-id="d7dd7-117">Insira credenciais de administrador ou aprove o prompt.</span><span class="sxs-lookup"><span data-stu-id="d7dd7-117">Enter administrator credentials or approve the prompt.</span></span>
        
2. <span data-ttu-id="d7dd7-118">Navegue até o Windows Defender diretório.</span><span class="sxs-lookup"><span data-stu-id="d7dd7-118">Navigate to the Windows Defender directory.</span></span> <span data-ttu-id="d7dd7-119">Por padrão, é `C:\Program Files\Windows Defender`</span><span class="sxs-lookup"><span data-stu-id="d7dd7-119">By default, this is `C:\Program Files\Windows Defender`.</span></span>

3. <span data-ttu-id="d7dd7-120">Digite o seguinte comando e pressione **Enter**</span><span class="sxs-lookup"><span data-stu-id="d7dd7-120">Type the following command, and then press **Enter**</span></span>
        
    ```Dos
    mpcmdrun -getfiles
    ```
    
4. <span data-ttu-id="d7dd7-121">Um arquivo .cab será gerado que contém vários logs de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="d7dd7-121">A .cab file will be generated that contains various diagnostic logs.</span></span> <span data-ttu-id="d7dd7-122">O local do arquivo será especificado na saída no prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="d7dd7-122">The location of the file will be specified in the output in the command prompt.</span></span> <span data-ttu-id="d7dd7-123">Por padrão, o local é `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab` .</span><span class="sxs-lookup"><span data-stu-id="d7dd7-123">By default, the location is `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab`.</span></span>

5. <span data-ttu-id="d7dd7-124">Copie esses arquivos .cab para um local que pode ser acessado pelo suporte da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d7dd7-124">Copy these .cab files to a location that can be accessed by Microsoft support.</span></span> <span data-ttu-id="d7dd7-125">Um exemplo pode ser uma pasta do OneDrive protegida por senha que você pode compartilhar conosco.</span><span class="sxs-lookup"><span data-stu-id="d7dd7-125">An example could be a password-protected OneDrive folder that you can share with us.</span></span>

6. <span data-ttu-id="d7dd7-126">Envie um email usando o modelo de email de suporte de Conformidade <a href="mailto:ucsupport@microsoft.com?subject=WDAV assessment issue&body=I%20am%20encountering%20the%20following%20issue%20when%20using%20Windows%20Defender%20AV%20in%20Update%20Compliance%3a%20%0d%0aI%20have%20provided%20at%20least%202%20support%20.cab%20files%20at%20the%20following%20location%3a%20%3Caccessible%20share%2c%20including%20access%20details%20such%20as%20password%3E%0d%0aMy%20OMS%20workspace%20ID%20is%3a%20%0d%0aPlease%20contact%20me%20at%3a">de</a>Atualização e preencha o modelo com as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="d7dd7-126">Send an email using the <a href="mailto:ucsupport@microsoft.com?subject=WDAV assessment issue&body=I%20am%20encountering%20the%20following%20issue%20when%20using%20Windows%20Defender%20AV%20in%20Update%20Compliance%3a%20%0d%0aI%20have%20provided%20at%20least%202%20support%20.cab%20files%20at%20the%20following%20location%3a%20%3Caccessible%20share%2c%20including%20access%20details%20such%20as%20password%3E%0d%0aMy%20OMS%20workspace%20ID%20is%3a%20%0d%0aPlease%20contact%20me%20at%3a">Update Compliance support email template</a>, and fill out the template with the following information:</span></span>
  
    ```
    I am encountering the following issue when using Microsoft Defender Antivirus in Update Compliance:
    
    I have provided at least 2 support .cab files at the following location: <accessible share, including access details such as password>

    My OMS workspace ID is:

    Please contact me at:
    ```

## <a name="see-also"></a><span data-ttu-id="d7dd7-127">Confira também</span><span class="sxs-lookup"><span data-stu-id="d7dd7-127">See also</span></span>

- [<span data-ttu-id="d7dd7-128">Solucionar problemas Windows Defender relatórios do Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="d7dd7-128">Troubleshoot Windows Defender Microsoft Defender Antivirus reporting</span></span>](troubleshoot-reporting.md)