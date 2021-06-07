---
title: Compatibilidade de solução antivírus com o Defender para Ponto de Extremidade
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
ms.date: 05/06/2021
ms.technology: mde
ms.openlocfilehash: f5a0db755f919cb47c4cd284857ddf4e27d16996
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782880"
---
# <a name="antivirus-solution-compatibility-with-microsoft-defender-for-endpoint"></a>Compatibilidade de soluções antivírus com o Microsoft Defender para Ponto de Extremidade

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-defendercompat-abovefoldlink)

O agente do Microsoft Defender para Ponto de Extremidade depende Microsoft Defender Antivírus alguns recursos, como a verificação de arquivos.

>[!IMPORTANT]
>O Defender para Ponto de Extremidade não segue as configurações Microsoft Defender Antivírus Exclusões. 

Você deve configurar atualizações de inteligência de segurança no Defender para dispositivos de ponto de extremidade, Microsoft Defender Antivírus o antimalware ativo ou não. Para obter mais informações, consulte [Manage Microsoft Defender Antivírus updates and apply baselines](manage-updates-baselines-microsoft-defender-antivirus.md).

Se um dispositivo conectado estiver protegido por um cliente antimalware de terceiros, Microsoft Defender Antivírus nesse ponto de extremidade entrará no modo passivo.

Microsoft Defender Antivírus continuará a receber atualizações, e  o processomspeng.exeserá listado como um serviço em execução, mas ele não executará verificações e não substituirá o cliente antimalware de terceiros em execução.

A Microsoft Defender Antivírus interface do usuário será desabilitada e os usuários no dispositivo não poderão usar o Microsoft Defender Antivírus para executar verificações sob demanda ou configurar a maioria das opções.

Para obter mais informações, consulte o [tópico Microsoft Defender Antivírus e Defender for Endpoint compatibility](microsoft-defender-antivirus-compatibility.md).
