---
title: Solucionar problemas de instalação do Microsoft Defender para Ponto de Extremidade no Mac
description: Solucionar problemas de instalação no Microsoft Defender para Ponto de Extremidade no Mac.
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, install
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
ms.openlocfilehash: 5166de3a7c7017979a93ac7026636ba24671892e
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935144"
---
# <a name="troubleshoot-installation-issues-for-microsoft-defender-for-endpoint-on-macos"></a>Solucionar problemas de instalação do Microsoft Defender para Ponto de Extremidade no macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade no macOS](microsoft-defender-endpoint-mac.md)
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="installation-failed"></a>Falha na instalação

Para instalação manual, a página Resumo do assistente de instalação diz: "Ocorreu um erro durante a instalação. O Instalador encontrou um erro que causou a falha da instalação. Entre em contato com o fabricante do software para assistência." Para implantações MDM, ele também é exibido como uma falha de instalação genérica.

Embora não seja exibido um erro exato para o usuário final, manteremos um arquivo de log com o progresso da instalação em `/Library/Logs/Microsoft/mdatp/install.log` . Cada sessão de instalação é anexada a esse arquivo de log. Você só pode `sed` usar para saída da última sessão de instalação:

```bash
sed -n 'H; /^preinstall com.microsoft.wdav begin/h; ${g;p;}' /Library/Logs/Microsoft/mdatp/install.log
```
```Output
preinstall com.microsoft.wdav begin [2020-03-11 13:08:49 -0700] 804
INSTALLER_SECURE_TEMP=/Library/InstallerSandboxes/.PKInstallSandboxManager/CB509765-70FC-4679-866D-8A14AD3F13CC.activeSandbox/89FA879B-971B-42BF-B4EA-7F5BB7CB5695
correlation id=CB509765-70FC-4679-866D-8A14AD3F13CC
[ERROR] Downgrade from 100.88.54 to 100.87.80 is not permitted
preinstall com.microsoft.wdav end [2020-03-11 13:08:49 -0700] 804 => 1
```

Neste exemplo, o motivo real é prefixado com `[ERROR]` .
A instalação falhou porque não há suporte para uma rebaixamento entre essas versões.

## <a name="mdatp-install-log-missing-or-not-updated"></a>Log de instalação MDATP ausente ou não atualizado

Em casos raros, a instalação não deixa nenhum rastreamento no arquivo /Library/Logs/Microsoft/mdatp/install.log do MDATP.
Você pode verificar se ocorreu uma instalação e analisar possíveis erros consultando logs macOS (isso é útil na implantação do MDM, quando não há interface do usuário do cliente). Recomendamos que você use uma janela de tempo estreita para executar uma consulta e filtre pelo nome do processo de registro em log, pois haverá uma grande quantidade de informações.

```bash
grep '^2020-03-11 13:08' /var/log/install.log
```
```Output
log show --start '2020-03-11 13:00:00' --end '2020-03-11 13:08:50' --info --debug --source --predicate 'processImagePath CONTAINS[C] "install"' --style syslog
```
