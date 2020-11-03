---
title: Solucionar problemas do Microsoft 365 defender Service
description: Encontre soluções e contornos para problemas conhecidos do Microsoft 365 defender
keywords: solução de problemas da proteção contra ameaças da Microsoft, solução de problemas, ATP, problemas, complemento, página de configurações do Azure
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 16cb1116f400c8d0a83ccc4cac23da06cd1be2a4
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844663"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a>Solucionar problemas do Microsoft 365 defender Service

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 defender

Esta seção aborda os problemas que podem surgir quando você usa o serviço Microsoft 365 defender.


## <a name="i-dont-see-microsoft-365-defender-content"></a>Não vejo o conteúdo do Microsoft 365 defender
Se você não vir recursos no painel de navegação, como incidentes, central de ações ou busca em seu portal, você precisará verificar se o seu locatário tem as licenças apropriadas. 

Para obter mais informações, confira [Pré-requisitos](prerequisites.md).

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a>Os alertas do Microsoft defender for Identity não estão aparecendo nos incidentes do Microsoft 365 defender
Se você tiver o Microsoft defender para identidade implantado em seu ambiente, mas não estiver vendo o defender para alertas de identidade como parte dos incidentes do Microsoft 365 defender, será necessário garantir que o Microsoft Cloud app Security e o defender para integração de identidade estejam habilitados. 

Para obter mais informações, consulte [Microsoft defender para integração de identidades](https://docs.microsoft.com/cloud-app-security/aatp-integration).

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a>Onde está a página de configurações para ativar o serviço?
Para ativar o Microsoft 365 defender, acesse **configurações** do painel de navegação na central de segurança do Microsoft 365. Esse item de navegação só será visível se você tiver as [permissões e as licenças de pré-requisito](mtp-enable.md#check-license-eligibility-and-required-permissions).
 

