---
title: Ativar a aposentadoria por definição para Microsoft Defender Antivírus
description: Ativar a aposentadoria de definição para Microsoft Defender Antivírus.
keywords: Microsoft Defender Antivírus, antimalware, segurança, defensor, aposentadoria de definição
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.date: 06/10/2021
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 505270d319a78de20bf6fed01b7ca79c9fc2b400
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/11/2021
ms.locfileid: "52903799"
---
# <a name="turn-on-definition-retirement"></a>Ativar a aposentadoria de definição

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)

Você pode configurar a aposentadoria de definição usando a Política de Grupo. A aposentadoria de definição verifica se um computador tem as atualizações de segurança necessárias para protegê-lo contra uma vulnerabilidade específica. Se o sistema não estiver vulnerável à exploração detectada por uma definição, essa definição será "retirada". Se toda a inteligência de segurança de um determinado protocolo for retirada, esse protocolo não será mais analisado. Habilenciar esse recurso ajuda a melhorar o desempenho. Em um computador atualizado com todas as atualizações de segurança mais recentes, a proteção de rede não terá impacto no desempenho da rede.

## <a name="use-group-policy-to-configure-definition-retirement"></a>Usar a Política de Grupo para configurar a aposentadoria de definição

1. No ponto de extremidade de gerenciamento da Política de Grupo, abra o Console de Gerenciamento de Política [de Grupo.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))

2. Vá para **Configuração do** Computador  >  **Modelos Administrativos Windows**  >  **Componentes**  >  **Microsoft Defender Antivírus**  >  Sistema **de** Inspeção de Rede . 

3. Selecione **Ativar a aposentadoria de definição**. Por padrão, essa diretiva está habilitada. Se definido **Não configurado,** a aposentadoria de definição será habilitada. 

4. Para editar a política, selecione o **link de configuração de política de** edição.

5. Selecione **Habilitado** e, em seguida, selecione **OK**.

6. Implante seu objeto de Política de Grupo atualizado. Consulte [Console de Gerenciamento de Política de Grupo](/windows/win32/srvnodes/group-policy).

> [!TIP]
> Você está usando Objetos de Política de Grupo no local? Veja como eles se traduzem na nuvem. [Analisar seus objetos de política de grupo local usando a análise da](/mem/intune/configuration/group-policy-analytics)Política de Grupo em Microsoft Endpoint Manager - Visualização . 
  
