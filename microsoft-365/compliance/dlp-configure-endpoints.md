---
title: Ferramentas e métodos de integração para dispositivos Windows 10 (versão prévia)
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Dispositivos integrados do Windows 10 para que eles possam enviar dados de sensor para as soluções de conformidade da Microsoft 365
ms.openlocfilehash: 5f5a777d11dda900116b6095166ffffed6efa31b
ms.sourcegitcommit: bd36c88e731e3fee2a3a5cb3564fdc94f11bab94
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769638"
---
# <a name="onboarding-tools-and-methods-for-windows-10-devices-preview"></a>Ferramentas e métodos de integração para dispositivos Windows 10 (versão prévia)

**Aplica-se a:**
- [Prevenção de perda de dados do Microsoft 365 EndPoint (DLP)](/microsoft-365/compliance/endpoint-dlp-learn-about)

Os dispositivos de sua organização devem estar configurados para que o serviço de prevenção de perda de dados de ponto de extremidade do Microsoft 365 possa obter dados de sensor deles. Há vários métodos e ferramentas de implantação que você pode usar para configurar os dispositivos em sua organização.

As seguintes ferramentas e métodos de implantação têm suporte:

- política de grupo
- Microsoft Endpoint Configuration Manager
- Gerenciamento de dispositivos móveis (incluindo o Microsoft Intune)
- script local

## <a name="in-this-section"></a>Nesta seção
Tópico | Descrição
:---|:---
[Dispositivos Windows 10 integrados usando a política de grupo](dlp-configure-endpoints-gp.md) | Use a política de grupo para implantar o pacote de configuração em dispositivos.
[Dispositivos do Windows integrados usando o Microsoft Endpoint Configuration Manager](dlp-configure-endpoints-sccm.md) | Você pode usar o Microsoft Endpoint Configuration Manager (Branch atual) versão 1606 ou o Microsoft Endpoint Configuration Manager (Branch atual) versão 1602 ou anterior para implantar o pacote de configuração em dispositivos.
[Dispositivos do Windows 10 integrados usando ferramentas de gerenciamento de dispositivos móveis](dlp-configure-endpoints-mdm.md) | Use as ferramentas de gerenciamento de dispositivo móvel ou o Microsoft Intune para implantar o pacote de configuração no dispositivo.
[Dispositivos integrados do Windows 10 usando um script local](dlp-configure-endpoints-script.md) | Saiba como usar o script local para implantar o pacote de configuração em pontos de extremidade.
[Dispositivos não persistentes de infraestrutura de área de trabalho virtual (VDI)](dlp-configure-endpoints-vdi.md) | Saiba como usar o pacote de configuração para configurar dispositivos VDI.
