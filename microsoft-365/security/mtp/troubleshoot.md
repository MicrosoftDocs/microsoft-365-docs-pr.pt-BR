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
ms.openlocfilehash: bbc7d5d434765b94b0b2707605be2edfbbc8e423
ms.sourcegitcommit: 2913fd74ad5086c7cac6388447285be9aa5a8e44
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/01/2020
ms.locfileid: "41661977"
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

## <a name="is-microsoft-threat-protection-available-for-us-government-community-cloud-gcc-or-gcc-high"></a>A Proteção contra Ameaças da Microsoft está disponível para a nuvem governamental de comunidade dos EUA (GCC) ou para a GCC High (de alta confidencialidade)?
No momento, ela não está disponível.

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a>Onde está a página de configurações para ativar o serviço?
Para ativar a proteção contra ameaças da Microsoft, acesse **configurações** do painel de navegação na central de segurança do Microsoft 365. Esse item de navegação só será visível se você tiver as [permissões e as licenças de pré-requisito](mtp-enable.md#check-license-eligibility-and-required-permissions).

## <a name="can-i-use-an-add-on-instead-of-the-required-e5-licenses"></a>Posso usar um complemento em vez das licenças E5 necessárias?
No momento, não há Complementos para a proteção contra ameaças da Microsoft. [Confira requisitos de licenciamento](prerequisites.md) 

