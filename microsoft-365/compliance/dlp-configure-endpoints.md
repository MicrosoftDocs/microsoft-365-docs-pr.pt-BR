---
title: Ferramentas e métodos de integração para computadores Windows 10
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
description: Integrando dispositivos Windows 10 para que eles possam enviar dados do sensor para as soluções de Conformidade do Microsoft 365
ms.openlocfilehash: 7cbadc343c5cee1aa7704bcb9da8be2a152726ab
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917847"
---
# <a name="onboarding-tools-and-methods-for-windows-10-devices"></a>Ferramentas e métodos de integração para computadores Windows 10

**Aplica-se a:**
- [Prevenção contra perda de dados do Microsoft 365 Endpoint (DLP)](./endpoint-dlp-learn-about.md)

Os dispositivos em sua organização devem ser configurados para que o serviço de prevenção contra perda de dados do Microsoft 365 Endpoint possa obter dados do sensor deles. Há vários métodos e ferramentas de implantação que você pode usar para configurar os dispositivos em sua organização.

As seguintes ferramentas de implantação e métodos são suportados:

- política de grupo
- Gerenciador de Configuração do Microsoft Endpoint
- Gerenciamento de dispositivo móvel (incluindo o Microsoft Intune)
- script local

## <a name="in-this-section"></a>Nesta seção
Tópico | Descrição
:---|:---
[Integração de dispositivos Windows 10 usando a Política de Grupo](dlp-configure-endpoints-gp.md) | Use a Política de Grupo para implantar o pacote de configuração em dispositivos.
[Integração de dispositivos Windows usando o Microsoft Endpoint Configuration Manager](dlp-configure-endpoints-sccm.md) | Você pode usar o Microsoft Endpoint Configuration Manager (branch atual) versão 1606 ou o Microsoft Endpoint Configuration Manager (branch atual) versão 1602 ou anterior para implantar o pacote de configuração em dispositivos.
[Integrar dispositivo Windows 10 usando as ferramentas de Gerenciamento de Dispositivo Móvel](dlp-configure-endpoints-mdm.md) | Use as ferramentas de Gerenciamento de Dispositivo Móvel ou o Microsoft Intune para implantar o pacote de configuração no dispositivo.
[Integrar dispositivos Windows 10 usando um script local](dlp-configure-endpoints-script.md) | Saiba como usar o script local para implantar o pacote de configuração nos pontos de extremidade.
[Integrar dispositivos não persistentes de VDI (virtual desktop infrastructure)](dlp-configure-endpoints-vdi.md) | Saiba como usar o pacote de configuração para configurar dispositivos VDI.