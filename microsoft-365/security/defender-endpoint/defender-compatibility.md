---
title: Compatibilidade do Microsoft Defender Antivírus com o Defender para Ponto de Extremidade
description: Saiba como o Windows Defender funciona com o Microsoft Defender para Ponto de Extremidade e como ele funciona quando um cliente antimalware de terceiros é usado.
keywords: Compatibilidade com o Windows Defender, Defender, Microsoft Defender para Ponto de Extremidade, Defender para ponto de extremidade, antivírus, mde
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: a8dca4a80385fabcdc64a5584474214d05be4a6c
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935372"
---
# <a name="microsoft-defender-antivirus-compatibility-with-microsoft-defender-for-endpoint"></a>Compatibilidade do Microsoft Defender Antivírus com o Microsoft Defender para Ponto de Extremidade

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-defendercompat-abovefoldlink)

O agente do Microsoft Defender para Ponto de Extremidade depende do Microsoft Defender Antivírus para alguns recursos, como a verificação de arquivos.

>[!IMPORTANT]
>O Defender para Ponto de Extremidade não está de acordo com as configurações de Exclusão do Microsoft Defender Antivírus. 

Você deve configurar atualizações de inteligência de segurança no Defender para dispositivos de ponto de extremidade, se o Microsoft Defender Antivírus é o antimalware ativo ou não. Para obter mais informações, consulte [Manage Microsoft Defender Antivírus updates and apply baselines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus.md).

Se um dispositivo conectado estiver protegido por um cliente antimalware de terceiros, o Microsoft Defender Antivírus nesse ponto de extremidade entrará no modo passivo.

O Microsoft Defender Antivírus continuará a  receber atualizações, e o processo demspeng.exeserá listado como um serviço em execução, mas ele não executará verificações e não substituirá o cliente antimalware de terceiros em execução.

A interface do Microsoft Defender Antivírus será desabilitada e os usuários no dispositivo não poderão usar o Microsoft Defender Antivírus para executar verificações sob demanda ou configurar a maioria das opções.

Para obter mais informações, consulte o tópico de compatibilidade do Microsoft Defender Antivírus e [do Defender for Endpoint.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)
