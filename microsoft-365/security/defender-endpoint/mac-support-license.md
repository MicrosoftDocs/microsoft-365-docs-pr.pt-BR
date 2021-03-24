---
title: Solucionar problemas de licença do Microsoft Defender ATP para Mac
description: Solucionar problemas de licença no Microsoft Defender ATP para Mac.
keywords: microsoft, defender, atp, mac, performance
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
ms.openlocfilehash: 44105ae8d1872c3ecefcf84a5e2efef122849b8c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053952"
---
# <a name="troubleshoot-license-issues-for-microsoft-defender-for-endpoint-for-mac"></a>Solucionar problemas de licença do Microsoft Defender para Ponto de Extremidade para Mac

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade para Mac](microsoft-defender-endpoint-mac.md)
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Enquanto você estiver passando pelo [Microsoft Defender para o Ponto](microsoft-defender-endpoint-mac.md) de Extremidade para Mac e teste de implantação [manual](mac-install-manually.md) ou um Teste de Prova de Conceito (PoC), você pode obter o seguinte erro:

![Imagem de erro de licença](images/no-license-found.png)

**Mensagem:** 

Nenhuma licença encontrada

Parece que sua organização não tem uma licença para assinatura do Microsoft 365 Enterprise.

Entre em contato com o administrador para obter ajuda.

**Causa:** 

Você implantou e/ou instalou o pacote do Microsoft Defender for Endpoint para macOS ("Baixar pacote de instalação") mas pode ter executado o script de configuração ("Baixar pacote de integração").

**Solução:**

Siga as instruções MicrosoftDefenderATPOnboardingMacOs.py documentadas aqui: [Configuração do cliente](mac-install-manually.md#client-configuration)

