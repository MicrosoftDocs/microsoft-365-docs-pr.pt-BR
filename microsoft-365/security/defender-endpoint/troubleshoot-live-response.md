---
title: Solucionar problemas de resposta ao vivo do Microsoft Defender ATP
description: Solucionar problemas que podem surgir ao usar a resposta ao vivo no Microsoft Defender ATP
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
ms.openlocfilehash: 27f2c7eb01a857ec38b11797c0703710c02ac1bc
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054535"
---
# <a name="troubleshoot-microsoft-defender-for-endpoint-live-response-issues"></a>Solucionar problemas de resposta ao vivo do Microsoft Defender para o Ponto de Extremidade

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

Esta página fornece etapas detalhadas para solucionar problemas de resposta ao vivo.

## <a name="file-cannot-be-accessed-during-live-response-sessions"></a>O arquivo não pode ser acessado durante sessões de resposta ao vivo
Se ao tentar tomar uma ação durante uma sessão de resposta ao vivo, você encontrar uma mensagem de erro informando que o arquivo não pode ser acessado, você precisará usar as etapas abaixo para resolver o problema.

1. Copie o seguinte trecho de código de script e salve-o como um arquivo PS1:

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


2. Adicione o script à biblioteca de resposta ao vivo.
3. Execute o script com um parâmetro: o caminho do arquivo a ser copiado.
4. Navegue até sua pasta TEMP.
5. Execute a ação que você queria executar no arquivo copiado.

## <a name="slow-live-response-sessions-or-delays-during-initial-connections"></a>Lentas sessões de resposta ao vivo ou atrasos durante as conexões iniciais
A resposta ao vivo aproveita o registro do sensor do Defender para Ponto de Extremidade com o serviço WNS no Windows. Se você estiver tendo problemas de conectividade com a resposta ao vivo, confirme os seguintes detalhes:
1. `notify.windows.com` não está bloqueado em seu ambiente. Para obter mais informações, consulte [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).
2. WpnService (Serviço do Sistema de Notificações por Push do Windows) não está desabilitado.

Consulte os artigos abaixo para entender totalmente o comportamento e os requisitos do serviço WpnService:
- [Visão geral do Windows Push Notification Services (WNS)](https://docs.microsoft.com/windows/uwp/design/shell/tiles-and-notifications/windows-push-notification-services--wns--overview)
- [Configurações de Firewall Empresarial e Proxy para dar suporte ao tráfego WNS](https://docs.microsoft.com/windows/uwp/design/shell/tiles-and-notifications/firewall-allowlist-config)
- [Intervalos ip públicos do Serviço de Notificações por Push da Microsoft (MPNS)](https://www.microsoft.com/en-us/download/details.aspx?id=44535)

