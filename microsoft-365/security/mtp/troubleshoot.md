---
title: À procura de soluções para os problemas de serviço da Proteção contra Ameaças da Microsoft
description: Encontre soluções e contorne problemas conhecidos da Proteção contra Ameaças da Microsoft
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
ms.openlocfilehash: e19e5758f4d42799c96ecec51fd6295e3da19f9b
ms.sourcegitcommit: bd5a08785b5ec320b04b02f8776e28bce5fb448f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/23/2020
ms.locfileid: "44844913"
---
# <a name="troubleshoot-microsoft-threat-protection-service-issues"></a>À procura de soluções para os problemas de serviço da Proteção contra Ameaças da Microsoft

**Aplica-se a:**
- Proteção contra Ameaças da Microsoft

Esta seção aborda os problemas que podem surgir quando você usa o serviço de Proteção contra Ameaças da Microsoft.


## <a name="i-dont-see-microsoft-threat-protection-content"></a>Não vejo o conteúdo da proteção contra ameaças da Microsoft
Se você não vir recursos no painel de navegação, como incidentes, central de ações ou busca em seu portal, você precisará verificar se o seu locatário tem as licenças apropriadas. 

Para obter mais informações, confira [Pré-requisitos](prerequisites.md).

## <a name="azure-atp-alerts-are-not-showing-up-in-the-microsoft-threat-protection-incidents"></a>Os alertas ATP do Azure não estão aparecendo nos incidentes da Proteção contra Ameaças da Microsoft
Se você tiver o Azure ATP implantado em seu ambiente, mas não estiver vendo os alertas ATP do Azure como parte dos incidentes de Proteção contra Ameaças da Microsoft, você precisará verificar se o Microsoft Cloud app Security e a integração ATP do Azure estão habilitados. 

Para obter mais informações, consulte [ integração da ATP do Azure](https://docs.microsoft.com/cloud-app-security/aatp-integration).

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a>Onde está a página de configurações para ativar o serviço?
Para ativar a proteção contra ameaças da Microsoft, acesse **configurações** do painel de navegação na central de segurança do Microsoft 365. Esse item de navegação só será visível se você tiver as [permissões e as licenças de pré-requisito](mtp-enable.md#check-license-eligibility-and-required-permissions).
 

