---
title: Solucionar problemas de conectividade na nuvem para o Microsoft Defender para Ponto de Extremidade no macOS
description: Este tópico descreve como solucionar problemas de conectividade de nuvem para o Microsoft Defender para Ponto de Extremidade no macOS
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, installation, deploy, uninstallation, intune, jamf, macos, catalina, mojave, high sierra
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-lsaldanha
author: lovina-saldanha
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 291cd3016dcb4e1a321f39b4d2731ce2068b6544
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935204"
---
# <a name="troubleshoot-cloud-connectivity-issues-for-microsoft-defender-for-endpoint-on-macos"></a>Solucionar problemas de conectividade na nuvem para o Microsoft Defender para Ponto de Extremidade no macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**Plataforma** macOS

Este tópico descreve como solucionar problemas de conectividade de nuvem para o Microsoft Defender para Ponto de Extremidade no macOS.

## <a name="run-the-connectivity-test"></a>Executar o teste de conectividade
Para testar se o Defender para Ponto de Extremidade no Mac pode se comunicar com a nuvem com as configurações de rede atuais, execute um teste de conectividade da linha de comando:

```Bash
mdatp connectivity test
```

saída esperada:
```Bash
Testing connection with https://cdn.x.cp.wd.microsoft.com/ping ... [OK]
Testing connection with https://eu-cdn.x.cp.wd.microsoft.com/ping ... [OK]
Testing connection with https://wu-cdn.x.cp.wd.microsoft.com/ping ... [OK]
Testing connection with https://x.cp.wd.microsoft.com/api/report ... [OK]
Testing connection with https://winatp-gw-cus.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-eus.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-weu.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-neu.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-ukw.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-uks.microsoft.com/test ... [OK]
Testing connection with https://eu-v20.events.data.microsoft.com/ping ... [OK]
Testing connection with https://us-v20.events.data.microsoft.com/ping ... [OK]
Testing connection with https://uk-v20.events.data.microsoft.com/ping ... [OK]
Testing connection with https://v20.events.data.microsoft.com/ping ... [OK]
```

Se o teste de conectividade falhar, verifique se o dispositivo tem acesso à Internet e se algum dos pontos de extremidade exigidos pelo produto são [bloqueados](microsoft-defender-endpoint-mac.md#network-connections) por um proxy ou firewall.

Falhas com o erro de curvamento 35 ou 60 indicam rejeição de pinamento de certificado, o que indica um possível problema com a inspeção SSL ou HTTPS. Consulte instruções abaixo sobre a configuração de inspeção SSL.

## <a name="troubleshooting-steps-for-environments-without-proxy-or-with-proxy-autoconfig-pac-or-with-web-proxy-autodiscovery-protocol-wpad"></a>Etapas de solução de problemas para ambientes sem proxy ou com PAC (Configuração Automática de Proxy) ou com o Protocolo de Descoberta Automática de Proxy da Web (WPAD)
Use o procedimento a seguir para testar se uma conexão não está bloqueada em um ambiente sem um proxy ou com PAC (Autoconfig de Proxy) ou com o Protocolo de Descoberta Automática de Proxy da Web (WPAD).

Se um proxy ou firewall estiver bloqueando o tráfego anônimo, certifique-se de que o tráfego anônimo seja permitido nas URLs listadas anteriormente.

> [!WARNING]
> Proxies autenticados não são suportados. Verifique se apenas PAC, WPAD ou um proxy estático estão sendo usados. Os proxies de inspeção e interceptação de SSL também não são suportados por motivos de segurança. Configure uma exceção para a inspeção SSL e seu servidor proxy passar diretamente os dados do Microsoft Defender para o Ponto de Extremidade no macOS para as URLs relevantes sem interceptação. Adicionar seu certificado de interceptação ao armazenamento global não permitirá interceptação.
Para testar se uma conexão não está bloqueada: em um navegador como o Microsoft Edge para Mac ou Safari aberto https://x.cp.wd.microsoft.com/api/report e https://cdn.x.cp.wd.microsoft.com/ping .

Opcionalmente, no Terminal, execute o seguinte comando:

```Bash
curl -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping' 
```

A saída deste comando deve ser semelhante a:
```bash
OK https://x.cp.wd.microsoft.com/api/report
OK https://cdn.x.cp.wd.microsoft.com/ping
```
