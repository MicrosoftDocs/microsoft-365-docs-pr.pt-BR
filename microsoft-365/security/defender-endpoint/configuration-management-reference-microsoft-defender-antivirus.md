---
title: Gerenciar Windows Defender em sua empresa
description: Saiba como usar a Política de Grupo, o Gerenciador de Configurações, o PowerShell, o WMI, o Intune e a linha de comando para gerenciar o Microsoft Defender AV
keywords: política de grupo, gpo, gerente de configuração, sccm, scep, powershell, wmi, intune, defender, antivírus, antimalware, segurança, proteção
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/06/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 2265f3680e425ade062d444685fbd8873eaa02ca
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274959"
---
# <a name="manage-microsoft-defender-antivirus-in-your-business"></a>Gerenciar Microsoft Defender Antivírus em sua empresa

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)

Você pode gerenciar e configurar Microsoft Defender Antivírus com as seguintes ferramentas:

- [Microsoft Intune](/mem/intune/protect/endpoint-security-antivirus-policy) (agora parte do Microsoft Endpoint Manager)
- [Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection-configure) (agora parte do Microsoft Endpoint Manager)
- [Política de grupo](./use-group-policy-microsoft-defender-antivirus.md)
- [Cmdlets do PowerShell](./use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [Windows Instrumentação de Gerenciamento (WMI)](./use-wmi-microsoft-defender-antivirus.md)
- O [Utilitário de Linha](./command-line-arguments-microsoft-defender-antivirus.md) de Comando da Proteção de Malware da Microsoft (conhecido como utilitário *de* mpcmdrun.exede segurança)

Os artigos a seguir fornecem mais informações, links e recursos para usar essas ferramentas para gerenciar e configurar Microsoft Defender Antivírus.

| Artigo | Descrição |
|:---|:---|
|[Gerenciar Microsoft Defender Antivírus com Microsoft Intune e Microsoft Endpoint Configuration Manager](use-intune-config-manager-microsoft-defender-antivirus.md)|Informações sobre como usar o Intune e o Configuration Manager para implantar, gerenciar, relatar e configurar Microsoft Defender Antivírus |
|[Gerenciar Microsoft Defender Antivírus com configurações de Política de Grupo](use-group-policy-microsoft-defender-antivirus.md)|Lista de todas as configurações de Política de Grupo localizadas em modelos ADMX |
|[Gerenciar Microsoft Defender Antivírus com cmdlets do PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md)|Instruções para usar cmdlets do PowerShell para gerenciar Microsoft Defender Antivírus, além de links para a documentação de todos os cmdlets e parâmetros permitidos |
|[Gerenciar Microsoft Defender Antivírus com Windows Instrumentação de Gerenciamento (WMI)](use-wmi-microsoft-defender-antivirus.md)| Instruções para usar o WMI para gerenciar Microsoft Defender Antivírus, além de links para documentação das APIs WMIv2 (incluindo todas as classes, métodos e propriedades) |
|[Gerenciar Microsoft Defender Antivírus com a ferramenta mpcmdrun.exe linha de comando](command-line-arguments-microsoft-defender-antivirus.md)|Instruções sobre como usar a ferramenta de linha de comando dedicada para gerenciar e usar Microsoft Defender Antivírus |