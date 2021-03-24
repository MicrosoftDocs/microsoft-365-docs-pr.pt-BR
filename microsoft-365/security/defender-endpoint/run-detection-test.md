---
title: Executar um teste de detecção em um dispositivo Microsoft Defender ATP recém-conectado
description: Execute o script de detecção em um dispositivo recém-integrado para verificar se ele está corretamente conectado ao serviço Microsoft Defender ATP.
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
ms.openlocfilehash: 10154a734bb4c3d8b26fffb8618484aeb11f907a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053868"
---
# <a name="run-a-detection-test-on-a-newly-onboarded-microsoft-defender-for-endpoint-device"></a>Executar um teste de detecção em um dispositivo recém-integrado do Microsoft Defender para Ponto de Extremidade 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**
- Versões com suporte do Windows 10
- Windows Server 2012 R2
- Windows Server 2016
- Windows Server, versão 1803
- Windows Server, 2019
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Execute o seguinte script do PowerShell em um dispositivo recém-conectado para verificar se ele está relatando corretamente para o serviço Defender para Ponto de Extremidade.

1. Crie uma pasta: 'C:\test-MDATP-test'.
2. Abra um prompt de linha de comando elevada no dispositivo e execute o script:

   1. Vá para **Iniciar** e digite **cmd**.

   1. Clique com o botão direito do mouse **em Prompt de Comando** e selecione Executar como **administrador**.

      ![Menu Iniciar janela apontando para Executar como administrador](images/run-as-admin.png)

3. No prompt, copie e execute o seguinte comando:

   ```powershell
   powershell.exe -NoExit -ExecutionPolicy Bypass -WindowStyle Hidden $ErrorActionPreference= 'silentlycontinue';(New-Object System.Net.WebClient).DownloadFile('http://127.0.0.1/1.exe', 'C:\\test-MDATP-test\\invoice.exe');Start-Process 'C:\\test-MDATP-test\\invoice.exe'
   ```

A janela prompt de comando será fechada automaticamente. Se bem-sucedido, o teste de detecção será marcado como concluído e um novo alerta aparecerá no portal do dispositivo conectado em aproximadamente 10 minutos.

## <a name="related-topics"></a>Tópicos relacionados
- [Integração de dispositivos Windows 10](configure-endpoints.md)
- [Servidores de integração](configure-server-endpoints.md)
- [Solucionar problemas de integração do Microsoft Defender para pontos de extremidade](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/troubleshoot-onboarding)
