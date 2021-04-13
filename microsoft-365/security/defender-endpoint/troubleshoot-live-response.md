---
title: Solucionar problemas de resposta ao vivo do Microsoft Defender para o Ponto de Extremidade
description: Solucionar problemas que podem surgir ao usar a resposta ao vivo no Microsoft Defender para Ponto de Extremidade
keywords: solução de problemas de resposta ao vivo, ao vivo, resposta, bloqueado, arquivo
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
ms.openlocfilehash: 2601001687fc22da98ca3cd81010237d12705ea4
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687406"
---
# <a name="troubleshoot-microsoft-defender-for-endpoint-live-response-issues"></a><span data-ttu-id="e3f78-104">Solucionar problemas de resposta ao vivo do Microsoft Defender para o Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="e3f78-104">Troubleshoot Microsoft Defender for Endpoint live response issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e3f78-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="e3f78-105">**Applies to:**</span></span>
- [<span data-ttu-id="e3f78-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="e3f78-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e3f78-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e3f78-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="e3f78-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="e3f78-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="e3f78-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="e3f78-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

<span data-ttu-id="e3f78-110">Esta página fornece etapas detalhadas para solucionar problemas de resposta ao vivo.</span><span class="sxs-lookup"><span data-stu-id="e3f78-110">This page provides detailed steps to troubleshoot live response issues.</span></span>

## <a name="file-cannot-be-accessed-during-live-response-sessions"></a><span data-ttu-id="e3f78-111">O arquivo não pode ser acessado durante sessões de resposta ao vivo</span><span class="sxs-lookup"><span data-stu-id="e3f78-111">File cannot be accessed during live response sessions</span></span>
<span data-ttu-id="e3f78-112">Se ao tentar tomar uma ação durante uma sessão de resposta ao vivo, você encontrar uma mensagem de erro informando que o arquivo não pode ser acessado, você precisará usar as etapas abaixo para resolver o problema.</span><span class="sxs-lookup"><span data-stu-id="e3f78-112">If while trying to take an action during a live response session, you encounter an error message stating that the file can't be accessed, you'll need to use the steps below to address the issue.</span></span>

1. <span data-ttu-id="e3f78-113">Copie o seguinte trecho de código de script e salve-o como um arquivo PS1:</span><span class="sxs-lookup"><span data-stu-id="e3f78-113">Copy the following script code snippet and save it as a PS1 file:</span></span>

    ```
    $copied_file_path=$args[0] 
    $action=Copy-Item $copied_file_path -Destination $env:TEMP -PassThru -ErrorAction silentlyContinue
        
    if ($action){
         Write-Host "You copied the file specified in $copied_file_path to $env:TEMP Succesfully"
    }
    
    else{
        Write-Output "Error occoured while trying to copy a file, details:"
        Write-Output  $error[0].exception.message
 
    }
    ```


2. <span data-ttu-id="e3f78-114">Adicione o script à biblioteca de resposta ao vivo.</span><span class="sxs-lookup"><span data-stu-id="e3f78-114">Add the script to the live response library.</span></span>
3. <span data-ttu-id="e3f78-115">Execute o script com um parâmetro: o caminho do arquivo a ser copiado.</span><span class="sxs-lookup"><span data-stu-id="e3f78-115">Run the script with one parameter: the file path of the file to be copied.</span></span>
4. <span data-ttu-id="e3f78-116">Navegue até sua pasta TEMP.</span><span class="sxs-lookup"><span data-stu-id="e3f78-116">Navigate to your TEMP folder.</span></span>
5. <span data-ttu-id="e3f78-117">Execute a ação que você queria executar no arquivo copiado.</span><span class="sxs-lookup"><span data-stu-id="e3f78-117">Run the action you wanted to take on the copied file.</span></span>

## <a name="slow-live-response-sessions-or-delays-during-initial-connections"></a><span data-ttu-id="e3f78-118">Lentas sessões de resposta ao vivo ou atrasos durante as conexões iniciais</span><span class="sxs-lookup"><span data-stu-id="e3f78-118">Slow live response sessions or delays during initial connections</span></span>
<span data-ttu-id="e3f78-119">A resposta ao vivo aproveita o registro do sensor do Defender para Ponto de Extremidade com o serviço WNS no Windows.</span><span class="sxs-lookup"><span data-stu-id="e3f78-119">Live response leverages Defender for Endpoint sensor registration with WNS service in Windows.</span></span> <span data-ttu-id="e3f78-120">Se você estiver tendo problemas de conectividade com a resposta ao vivo, confirme os seguintes detalhes:</span><span class="sxs-lookup"><span data-stu-id="e3f78-120">If you are having connectivity issues with live response, confirm the following details:</span></span>
1. <span data-ttu-id="e3f78-121">`notify.windows.com` não está bloqueado em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="e3f78-121">`notify.windows.com` is not blocked in your environment.</span></span> <span data-ttu-id="e3f78-122">Para obter mais informações, consulte [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span><span class="sxs-lookup"><span data-stu-id="e3f78-122">For more information, see, [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span>
2. <span data-ttu-id="e3f78-123">WpnService (Serviço do Sistema de Notificações por Push do Windows) não está desabilitado.</span><span class="sxs-lookup"><span data-stu-id="e3f78-123">WpnService (Windows Push Notifications System Service) is not disabled.</span></span>

<span data-ttu-id="e3f78-124">Consulte os artigos abaixo para entender totalmente o comportamento e os requisitos do serviço WpnService:</span><span class="sxs-lookup"><span data-stu-id="e3f78-124">Refer to the articles below to fully understand the WpnService service behavior and requirements:</span></span>
- [<span data-ttu-id="e3f78-125">Visão geral do Windows Push Notification Services (WNS)</span><span class="sxs-lookup"><span data-stu-id="e3f78-125">Windows Push Notification Services (WNS) overview</span></span>](https://docs.microsoft.com/windows/uwp/design/shell/tiles-and-notifications/windows-push-notification-services--wns--overview)
- [<span data-ttu-id="e3f78-126">Configurações de Firewall Empresarial e Proxy para dar suporte ao tráfego WNS</span><span class="sxs-lookup"><span data-stu-id="e3f78-126">Enterprise Firewall and Proxy Configurations to Support WNS Traffic</span></span>](https://docs.microsoft.com/windows/uwp/design/shell/tiles-and-notifications/firewall-allowlist-config)
- [<span data-ttu-id="e3f78-127">Intervalos ip públicos do Serviço de Notificações por Push da Microsoft (MPNS)</span><span class="sxs-lookup"><span data-stu-id="e3f78-127">Microsoft Push Notifications Service (MPNS) Public IP ranges</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=44535)

