---
title: Solucionar problemas de serviço do Microsoft 365 Defender
description: Encontre soluções e soluções alternativas para problemas conhecidos do Microsoft 365 Defender
keywords: solucionar problemas do Microsoft 365 Defender, solução de problemas, Microsoft Defender para Identidade, problemas, complemento, página de configurações
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 0c933edfe80275dbfa60464ff862a7609b269332
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933392"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a>Solucionar problemas de serviço do Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

Esta seção aborda problemas que podem surgir à medida que você usa o serviço do Microsoft 365 Defender.

## <a name="i-dont-see-microsoft-365-defender-content"></a>Não vejo conteúdo do Microsoft 365 Defender

Se você não vir recursos no painel de navegação, como Incidentes, Centro de Ações ou Busca em seu portal, precisará verificar se seu locatário tem as licenças apropriadas.

Para obter mais informações, confira [Pré-requisitos](prerequisites.md).

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a>Os alertas do Microsoft Defender para Identidade não estão sendo exibidos nos incidentes do Microsoft 365 Defender

Se você tiver o Microsoft Defender para Identidade implantado em seu ambiente, mas não estiver vendo alertas do Defender para Identidade como parte dos incidentes do Microsoft 365 Defender, você precisará garantir que a integração do Microsoft Cloud App Security e o Defender for Identity esteja habilitada.

Para obter mais informações, consulte [Integração do Microsoft Defender for Identity](/cloud-app-security/mdi-integration).

## <a name="where-is-the-settings-page-for-turning-on-the-service"></a>Onde está a página de configurações para ligar o serviço?

Para ativar o Microsoft 365 Defender, acesse **Configurações** do painel de navegação no centro de segurança do Microsoft 365. Esse item de navegação só será visível se você tiver as permissões e licenças de [pré-requisito.](m365d-enable.md#check-license-eligibility-and-required-permissions)

## <a name="how-do-i-create-an-exception-for-my-fileurl"></a>Como criar uma exceção para meu arquivo/URL?

Um falso positivo é um arquivo ou URL que é detectado como mal-intencionado, mas não é uma ameaça. Você pode criar indicadores e definir exclusões para desbloquear e permitir determinados arquivos/URLs. Consulte [Address false positives/negatives in Defender for Endpoint](/microsoft-365/security/defender-endpoint/defender-endpoint-false-positives-negatives).


