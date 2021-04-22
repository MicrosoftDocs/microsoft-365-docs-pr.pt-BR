---
title: Solucionar problemas de conectividade na nuvem para o Microsoft Defender para Ponto de Extremidade no Linux
ms.reviewer: ''
description: Solucionar problemas de conectividade na nuvem para o Microsoft Defender para Ponto de Extremidade no Linux
keywords: microsoft, defender, Microsoft Defender para Endpoint, linux, nuvem, conectividade, comunicação
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 0345d7f88d147abb750e66a5e61f516abf38d553
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933104"
---
# <a name="troubleshoot-cloud-connectivity-issues-for-microsoft-defender-for-endpoint-on-linux"></a>Solucionar problemas de conectividade na nuvem para o Microsoft Defender para Ponto de Extremidade no Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="run-the-connectivity-test"></a>Executar o teste de conectividade

Para testar se o Defender para Ponto de Extremidade no Linux pode se comunicar com a nuvem com as configurações de rede atuais, execute um teste de conectividade da linha de comando:

```bash
mdatp connectivity test
```

saída esperada:

```output
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

Se o teste de conectividade falhar, verifique se o dispositivo tem acesso à Internet e se algum dos pontos de extremidade exigidos pelo produto são [bloqueados](microsoft-defender-endpoint-linux.md#network-connections) por um proxy ou firewall.

Falhas com erro de curvaagem 35 ou 60 indicam rejeição de pinamento de certificado. Verifique se a conexão está em inspeção SSL ou HTTPS. Em caso afirmado, adicione o Microsoft Defender para Ponto de Extremidade à lista de permitir.

## <a name="troubleshooting-steps-for-environments-without-proxy-or-with-transparent-proxy"></a>Etapas de solução de problemas para ambientes sem proxy ou com proxy transparente

Para testar se uma conexão não está bloqueada em um ambiente sem um proxy ou com um proxy transparente, execute o seguinte comando no terminal:

```bash
curl -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

A saída deste comando deve ser semelhante a:

```Output
OK https://x.cp.wd.microsoft.com/api/report
OK https://cdn.x.cp.wd.microsoft.com/ping
```

## <a name="troubleshooting-steps-for-environments-with-static-proxy"></a>Etapas de solução de problemas para ambientes com proxy estático

> [!WARNING]
> Pac, WPAD e proxies autenticados não são suportados. Verifique se apenas um proxy estático ou um proxy transparente está sendo usado.
>
> Os proxies de inspeção e interceptação de SSL também não são suportados por motivos de segurança. Configure uma exceção para a inspeção SSL e seu servidor proxy passar diretamente os dados do Defender para o Ponto de Extremidade no Linux para as URLs relevantes sem interceptação. Adicionar seu certificado de interceptação ao armazenamento global não permitirá interceptação.

Se for necessário um proxy estático, adicione um parâmetro proxy ao comando acima, onde corresponde `proxy_address:port` ao endereço de proxy e à porta:

```bash
curl -x http://proxy_address:port -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

Certifique-se de usar o mesmo endereço proxy e porta configurados no `/lib/system/system/mdatp.service` arquivo. Verifique sua configuração de proxy se houver erros nos comandos acima.

> [!WARNING]
> O proxy estático não pode ser configurado por meio de uma variável de ambiente em todo `HTTPS_PROXY` o sistema. Em vez disso, `HTTPS_PROXY` certifique-se de que está corretamente definido no `/lib/system/system/mdatp.service` arquivo.

Para usar um proxy estático, `mdatp.service` o arquivo deve ser modificado. Certifique-se de que a parte de frente foi removida `#` para descompactar a seguinte linha de `/lib/systemd/system/mdatp.service` :

```bash
#Environment="HTTPS_PROXY=http://address:port"
```

Certifique-se também de que o endereço proxy estático correto seja preenchido para substituir `address:port` .

Se esse arquivo estiver correto, tente executar o seguinte comando no terminal para recarregar o Defender para Ponto de Extremidade no Linux e propagar a configuração:

```bash
sudo systemctl daemon-reload; sudo systemctl restart mdatp
```

Após o sucesso, tente outro teste de conectividade da linha de comando:

```bash
mdatp connectivity test
```

Se o problema persistir, contate o suporte ao cliente.

## <a name="resources"></a>Recursos

- Para obter mais informações sobre como configurar o produto para usar um proxy estático, consulte [Configure Microsoft Defender for Endpoint for Endpoint for static proxy discovery](linux-static-proxy-configuration.md).
