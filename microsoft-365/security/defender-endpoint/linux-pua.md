---
title: Detectar e bloquear aplicativos potencialmente indesejados com o Microsoft Defender ATP para Linux
description: Detectar e bloquear Aplicativos Potencialmente Indesejados (PUA) usando o Microsoft Defender ATP para Linux.
keywords: microsoft, defender, atp, linux, pua, pus
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
ms.openlocfilehash: 40e6099349ff6c62c5e0b6c35fd9940cb9200f05
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187764"
---
# <a name="detect-and-block-potentially-unwanted-applications-with-microsoft-defender-for-endpoint-for-linux"></a>Detectar e bloquear aplicativos potencialmente indesejados com o Microsoft Defender para Endpoint para Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

O recurso de proteção de aplicativo potencialmente indesejado (PUA) no Defender for Endpoint para Linux pode detectar e bloquear arquivos PUA em pontos de extremidade em sua rede.

Esses aplicativos não são considerados vírus, malware ou outros tipos de ameaças, mas podem executar ações em pontos de extremidade que afetam adversamente seu desempenho ou uso. A PUA também pode se referir a aplicativos considerados com má reputação.

Esses aplicativos podem aumentar o risco de sua rede ser infectado por malware, fazer com que as infecções de malware sejam mais difíceis de identificar e podem desperdiçar recursos de IT na limpeza dos aplicativos.

## <a name="how-it-works"></a>Como funciona

O Defender para Ponto de Extremidade para Linux pode detectar e relatar arquivos PUA. Quando configurados no modo de bloqueio, os arquivos PUA são movidos para a quarentena.

Quando um PUA é detectado em um ponto de extremidade, o Defender for Endpoint para Linux mantém um registro da infecção no histórico de ameaças. O histórico pode ser visualizado no portal do Centro de Segurança do Microsoft Defender ou por meio da `mdatp` ferramenta de linha de comando. O nome da ameaça conterá a palavra "Application".

## <a name="configure-pua-protection"></a>Configurar a proteção pua

A proteção PUA no Defender para Ponto de Extremidade para Linux pode ser configurada de uma das seguintes maneiras:

- **Desativado**: a proteção pua está desabilitada.
- **Auditoria**: os arquivos PUA são relatados nos logs do produto, mas não no Centro de Segurança do Microsoft Defender. Nenhum registro da infecção é armazenado no histórico de ameaças e nenhuma ação é tomada pelo produto.
- **Bloquear**: os arquivos PUA são relatados nos logs do produto e no Centro de Segurança do Microsoft Defender. Um registro da infecção é armazenado no histórico de ameaças e a ação é tomada pelo produto.

>[!WARNING]
>Por padrão, a proteção pua é configurada no **modo auditoria.**

Você pode configurar como os arquivos PUA são manipulados da linha de comando ou do console de gerenciamento.

### <a name="use-the-command-line-tool-to-configure-pua-protection"></a>Use a ferramenta de linha de comando para configurar a proteção PUA:

No Terminal, execute o seguinte comando para configurar a proteção PUA:

```bash
mdatp threat policy set --type potentially_unwanted_application --action [off|audit|block]
```

### <a name="use-the-management-console-to-configure-pua-protection"></a>Use o console de gerenciamento para configurar a proteção pua:

Em sua empresa, você pode configurar a proteção PUA de um console de gerenciamento, como o Puppet ou Ansible, da mesma forma como outras configurações de produto são configuradas. Para obter mais informações, consulte a seção [Configurações do tipo](linux-preferences.md#threat-type-settings) Ameaça do artigo [Definir preferências para Defender para Ponto de](linux-preferences.md) Extremidade para Linux.

## <a name="related-articles"></a>Artigos relacionados

- [Definir preferências para Defender para Ponto de Extremidade para Linux](linux-preferences.md)
