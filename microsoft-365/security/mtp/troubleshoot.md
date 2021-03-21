---
title: Solucionar problemas de serviço do Microsoft 365 Defender
description: Encontre soluções e soluções para problemas conhecidos do Microsoft 365 Defender
keywords: solucionar problemas da Proteção contra Ameaças da Microsoft, solucionar problemas, Azure ATP, problemas, complemento, página de configurações
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: d01912532ad2a00abbecee0d0a337be7baf87017
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918661"
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

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a>Onde está a página de configurações para ligar o serviço?

Para ativar o Microsoft 365 Defender, acesse **Configurações** do painel de navegação no centro de segurança do Microsoft 365. Esse item de navegação só será visível se você tiver as permissões e licenças de [pré-requisito.](mtp-enable.md#check-license-eligibility-and-required-permissions)