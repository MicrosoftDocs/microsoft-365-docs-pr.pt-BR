---
title: Configurar o Microsoft Defender Antivírus com WMI
description: Saiba como configurar e gerenciar o Microsoft Defender Antivírus usando scripts WMI para recuperar, modificar e atualizar configurações no Microsoft Defender para Ponto de Extremidade.
keywords: wmi, scripts, instrumentação de gerenciamento do Windows, configuração
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 8d24a08ae3b8db710ca1727821690e5c87f056c3
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689844"
---
# <a name="use-windows-management-instrumentation-wmi-to-configure-and-manage-microsoft-defender-antivirus"></a>Use a Instrumentação de Gerenciamento do Windows (WMI) para configurar e gerenciar o Microsoft Defender Antivírus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)

A Instrumentação de Gerenciamento do Windows (WMI) é uma interface de script que permite recuperar, modificar e atualizar configurações.

Leia mais sobre o WMI na biblioteca Administração do Sistema de Rede de Desenvolvedores [da Microsoft.](/windows/win32/wmisdk/wmi-start-page)

O Microsoft Defender Antivírus tem várias classes WMI específicas que podem ser usadas para executar a maioria das mesmas funções que a Política de Grupo e outras ferramentas de gerenciamento. Muitas das classes são análogas aos [cmdlets do Defender PowerShell.](use-powershell-cmdlets-microsoft-defender-antivirus.md)

A biblioteca de referência do [provedor WMIv2 Windows Defender MSDN](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) lista as classes WMI disponíveis para o Microsoft Defender Antivírus e inclui scripts de exemplo.

As alterações feitas com o WMI afetarão as configurações locais no ponto de extremidade onde as alterações são implantadas ou feitas. Isso significa que as implantações de política com a Política de Grupo, o Microsoft Endpoint Configuration Manager ou o Microsoft Intune podem substituir as alterações feitas com o WMI. 

Você pode [configurar quais configurações podem ser substituidas localmente com substituições de política local.](configure-local-policy-overrides-microsoft-defender-antivirus.md)

## <a name="related-topics"></a>Tópicos relacionados

- [Tópicos de referência para ferramentas de gerenciamento e configuração](configuration-management-reference-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivírus no Windows 10](microsoft-defender-antivirus-in-windows-10.md)