---
title: Configurar Microsoft Defender Antivírus usando Microsoft Endpoint Manager
description: Use Microsoft Endpoint Manager e Microsoft Intune configurar o Microsoft Defender AV e Endpoint Protection
keywords: scep, intune, proteção de ponto de extremidade, configuração
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/24/2021
ms.reviewer: phuijbr, oogunrinde
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.openlocfilehash: ab77f3ab5ac9385d1ce049061730d2192e3bcb0c
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683746"
---
# <a name="use-microsoft-endpoint-manager-to-configure-and-manage-microsoft-defender-antivirus"></a>Use Microsoft Endpoint Manager para configurar e gerenciar Microsoft Defender Antivírus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)

Você pode usar [Microsoft Endpoint Manager](/mem/endpoint-manager-overview) para configurar Microsoft Defender Antivírus verificações. [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) e [o Configuration Manager](/mem/configmgr/core/understand/introduction) agora fazem parte Endpoint Manager.  

## <a name="configure-microsoft-defender-antivirus-scans-in-endpoint-manager"></a>Configurar Microsoft Defender Antivírus verificações em Endpoint Manager

1. Vá para o Microsoft Endpoint Manager de administração ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ), e entre.

2. Navegue até **Endpoint Security**.

3. Em **Gerenciar**, escolha **Antivírus**.

4. Selecione sua Microsoft Defender Antivírus de segurança. 

5. Em **Gerenciar**, escolha **Propriedades**.

6. Ao lado de **Definições de configuração**, escolha **Editar**.

7. Expanda **a seção Examinar** e revise ou edite suas configurações de verificação.

8. Escolha **Revisar + salvar**


> [!TIP]
> Precisa de ajuda? Consulte [Gerenciar a segurança do ponto de extremidade Microsoft Intune](/mem/intune/protect/endpoint-security).


## <a name="related-articles"></a>Artigos relacionados

- [Artigos de referência para ferramentas de gerenciamento e configuração](configuration-management-reference-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus no Windows 10](microsoft-defender-antivirus-in-windows-10.md)