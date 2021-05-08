---
title: Solucionar problemas de licença do Microsoft Defender para Ponto de Extremidade no Mac
description: Solucionar problemas de licença no Microsoft Defender para Ponto de Extremidade no Mac.
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, performance
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
ms.openlocfilehash: 1f8428c2995eec2dece290049eda67a3683b4c1e
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244975"
---
# <a name="troubleshoot-license-issues-for-microsoft-defender-for-endpoint-on-macos"></a>Solucionar problemas de licença do Microsoft Defender para Ponto de Extremidade no macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade no macOS](microsoft-defender-endpoint-mac.md)
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Enquanto você estiver passando pelo Microsoft Defender para Ponto de Extremidade no [macOS](microsoft-defender-endpoint-mac.md) e teste de implantação [manual](mac-install-manually.md) ou em um PoC (Proof Of Concept), você pode obter o seguinte erro:

![Imagem de erro de licença](images/no-license-found.png)

**Mensagem:** 

Nenhuma licença encontrada

Parece que sua organização não tem uma licença para Microsoft 365 Enterprise assinatura.

Entre em contato com o administrador para obter ajuda.

**Causa:** 

Você implantou e/ou instalou o pacote do Microsoft Defender for Endpoint para macOS ("Baixar pacote de instalação"), mas pode ter executado o script de configuração ("Baixar pacote de integração"), ou não atribuiu uma licença ao usuário.

**Solução:**

Siga as instruções MicrosoftDefenderATPOnboardingMacOs.py documentadas aqui: [Configuração do cliente](mac-install-manually.md#client-configuration)
