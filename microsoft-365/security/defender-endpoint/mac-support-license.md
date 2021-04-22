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
ms.openlocfilehash: e8084fab434246a5c9f12af40872ade66e6fa163
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934256"
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

Parece que sua organização não tem uma licença para assinatura do Microsoft 365 Enterprise.

Entre em contato com o administrador para obter ajuda.

**Causa:** 

Você implantou e/ou instalou o Microsoft Defender para Ponto de Extremidade no pacote macOS ("Baixar pacote de instalação") mas pode ter executado o script de configuração ("Baixar pacote de integração").

**Solução:**

Siga as instruções MicrosoftDefenderATPOnboardingMacOs.py documentadas aqui: [Configuração do cliente](mac-install-manually.md#client-configuration)

