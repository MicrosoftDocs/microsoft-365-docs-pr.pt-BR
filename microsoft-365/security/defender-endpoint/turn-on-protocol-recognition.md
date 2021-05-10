---
title: Ativar o reconhecimento de protocolo para Microsoft Defender Antivírus
description: Ativar o reconhecimento de protocolo para Microsoft Defender Antivírus.
keywords: Microsoft Defender Antivírus, antimalware, segurança, defensor, reconhecimento de protocolo
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.date: 05/07/2021
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 890303a15618a0318db0421c9c80f270583e19bf
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/10/2021
ms.locfileid: "52296462"
---
# <a name="turn-on-protocol-recognition"></a>Ativar o reconhecimento de protocolo 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)

Essa configuração de política permite configurar o reconhecimento de protocolo para proteção de rede contra explorações de vulnerabilidades conhecidas. Se você habilitar ou não definir essa configuração, o reconhecimento de protocolo será habilitado. Se você desabilitar essa configuração, o reconhecimento de protocolo será desabilitado.

## <a name="use-group-policy-to-configure-protocol-recognition"></a>Usar a Política de Grupo para configurar o reconhecimento de protocolo

1. No ponto de extremidade de gerenciamento da Política de Grupo, abra o Console de Gerenciamento de Política [de Grupo.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))

2. Vá para **Configuração do** Computador  >  **Modelos Administrativos Windows**  >  **Componentes**  >  **Microsoft Defender Antivírus**  >  Sistema **de** Inspeção de Rede . 

3. Selecione **reconhecimento de protocolo**. Por padrão, essa diretiva está habilitada. Se definido **Não configurado,** a aposentadoria de definição será habilitada. 

4. Para editar a política, selecione o **link de configuração de política de** edição.

5. Selecione **Habilitado** e, em seguida, selecione **OK**.

6. Implante seu objeto de Política de Grupo atualizado. Consulte [Console de Gerenciamento de Política de Grupo](/windows/win32/srvnodes/group-policy).

> [!TIP]
> Você está usando Objetos de Política de Grupo no local? Veja como eles se traduzem na nuvem. [Analisar seus objetos de política de grupo local usando a análise da](/mem/intune/configuration/group-policy-analytics)Política de Grupo em Microsoft Endpoint Manager - Visualização . 
  
## <a name="related-articles"></a>Artigos relacionados

- [Microsoft Defender Antivirus no Windows 10](microsoft-defender-antivirus-in-windows-10.md)
 
- [Ativar proteção fornecida pela nuvem](enable-cloud-protection-microsoft-defender-antivirus.md)

- [Como criar e implantar políticas antimalware: serviço de proteção na nuvem](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)