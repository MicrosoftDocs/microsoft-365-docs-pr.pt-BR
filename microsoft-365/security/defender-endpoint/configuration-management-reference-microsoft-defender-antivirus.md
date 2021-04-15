---
title: Gerenciar Windows Defender em sua empresa
description: Saiba como usar a Política de Grupo, o Gerenciador de Configurações, o PowerShell, o WMI, o Intune e a linha de comando para gerenciar o Microsoft Defender AV
keywords: política de grupo, gpo, gerente de configuração, sccm, scep, powershell, wmi, intune, defender, antivírus, antimalware, segurança, proteção
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 12/16/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 6b9845812763f9e3f1fdecf5566824eb76971dad
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764862"
---
# <a name="manage-microsoft-defender-antivirus-in-your-business"></a>Gerenciar o Microsoft Defender Antivírus em sua empresa

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)

Você pode gerenciar e configurar o Microsoft Defender Antivírus com as seguintes ferramentas:

- [Microsoft Intune](/mem/intune/protect/endpoint-security-antivirus-policy) (agora parte do Microsoft Endpoint Manager)
- [Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection-configure) (agora parte do Microsoft Endpoint Manager)
- [Política de grupo](./use-group-policy-microsoft-defender-antivirus.md)
- [Cmdlets do PowerShell](./use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [Instrumentação de Gerenciamento do Windows (WMI)](./use-wmi-microsoft-defender-antivirus.md)
- O [Utilitário de Linha](./command-line-arguments-microsoft-defender-antivirus.md) de Comando da Proteção de Malware da Microsoft (conhecido como utilitário *de* mpcmdrun.exede segurança)

Os artigos a seguir fornecem mais informações, links e recursos para usar essas ferramentas para gerenciar e configurar o Microsoft Defender Antivírus.

| Artigo | Descrição |
|:---|:---|
|[Gerenciar o Microsoft Defender Antivírus com o Microsoft Intune e o Microsoft Endpoint Configuration Manager](use-intune-config-manager-microsoft-defender-antivirus.md)|Informações sobre como usar o Intune e o Configuration Manager para implantar, gerenciar, relatar e configurar o Microsoft Defender Antivírus |
|[Gerenciar o Microsoft Defender Antivírus com configurações de Política de Grupo](use-group-policy-microsoft-defender-antivirus.md)|Lista de todas as configurações de Política de Grupo localizadas em modelos ADMX |
|[Gerenciar o Microsoft Defender Antivírus com cmdlets do PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md)|Instruções para usar cmdlets do PowerShell para gerenciar o Microsoft Defender Antivírus, além de links para a documentação de todos os cmdlets e parâmetros permitidos |
|[Gerenciar o Microsoft Defender Antivírus com Instrumentação de Gerenciamento do Windows (WMI)](use-wmi-microsoft-defender-antivirus.md)| Instruções para usar o WMI para gerenciar o Microsoft Defender Antivírus, além de links para a documentação das APIs WMIv2 (incluindo todas as classes, métodos e propriedades) |
|[Gerenciar o Microsoft Defender Antivírus com a mpcmdrun.exe de linha de comando](command-line-arguments-microsoft-defender-antivirus.md)|Instruções sobre como usar a ferramenta de linha de comando dedicada para gerenciar e usar o Microsoft Defender Antivírus |