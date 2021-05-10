---
title: Especificar conjuntos de definições adicionais para inspeção de tráfego de rede para Microsoft Defender Antivírus
description: Especifique conjuntos de definições adicionais para inspeção de tráfego de rede para Microsoft Defender Antivírus.
keywords: Microsoft Defender Antivírus, antimalware, segurança, defensor, inspeção de tráfego de rede
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
ms.openlocfilehash: 82568df0a6ad2225fd31b4c0fa4a654710f1e98b
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/10/2021
ms.locfileid: "52300102"
---
# <a name="specify-additional-definition-sets-for-network-traffic-inspection"></a>Especificar conjuntos de definições adicionais para inspeção de tráfego de rede

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)

Você pode especificar conjuntos de definições adicionais para inspeção de tráfego de rede usando a Política de Grupo.

## <a name="use-group-policy-to-specify-additional-definition-sets-for-network-traffic-inspection"></a>Usar a Política de Grupo para especificar conjuntos de definições adicionais para inspeção de tráfego de rede

1. No ponto de extremidade de gerenciamento da Política de Grupo, abra o Console de Gerenciamento de Política [de Grupo.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))

2. Vá para **Windows Componentes**  >  **Microsoft Defender Antivírus**  >  **Sistema de Inspeção de Rede.** 

3. Selecione **Especificar conjuntos de definições adicionais para inspeção de tráfego de rede.** Por padrão, essa política é definida como **Não configurada**. 

4. Para editar a política, selecione o **link de configuração de política de** edição.

5. Selecione **Habilitado** e, em seguida, na seção **Opções,** selecione **Mostrar...**.

6. Adicione entradas à lista e selecione **OK**. 

   Cada entrada deve ser listada como um par de valores de nome, onde o nome é uma representação de cadeia de caracteres de um GUID de conjunto de definições. Como exemplo, o GUID do conjunto de definições para habilitar a inteligência de segurança de teste é definido como: `{b54b6ac9-a737-498e-9120-6616ad3bf590}` . O valor não é usado, portanto, recomendamos defini-lo como `0` . 

7. Selecione **OK** e, em seguida, implante seu Objeto de Política de Grupo atualizado. Consulte [Console de Gerenciamento de Política de Grupo](/windows/win32/srvnodes/group-policy).

> [!TIP]
> Você está usando Objetos de Política de Grupo no local? Veja como eles se traduzem na nuvem. [Analisar seus objetos de política de grupo local usando a análise da](/mem/intune/configuration/group-policy-analytics)Política de Grupo em Microsoft Endpoint Manager - Visualização . 
  
## <a name="related-articles"></a>Artigos relacionados

- [Microsoft Defender Antivirus no Windows 10](microsoft-defender-antivirus-in-windows-10.md)
 
- [Ativar proteção fornecida pela nuvem](enable-cloud-protection-microsoft-defender-antivirus.md)

- [Como criar e implantar políticas antimalware: serviço de proteção na nuvem](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)