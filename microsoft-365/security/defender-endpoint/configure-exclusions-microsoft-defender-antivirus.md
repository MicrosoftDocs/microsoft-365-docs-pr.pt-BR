---
title: Configurar exclusões para verificações do Microsoft Defender AV
description: Você pode excluir arquivos (incluindo arquivos modificados por processos especificados) e pastas de serem verificados pelo Microsoft Defender AV. Valide suas exclusões com o PowerShell.
keywords: ''
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 47db9b4451a885c92ca4fda0f87f0150415d3338
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690003"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-antivirus-scans"></a>Configurar e validar exclusões para verificações do Microsoft Defender Antivírus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)

Você pode excluir determinados arquivos, pastas, processos e arquivos abertos por processo de verificações do Microsoft Defender Antivírus. Essas exclusões se aplicam [](run-scan-microsoft-defender-antivirus.md)a [verificações agendadas,](scheduled-catch-up-scans-microsoft-defender-antivirus.md)verificações sob demanda e proteção e monitoramento sempre em [tempo real.](configure-real-time-protection-microsoft-defender-antivirus.md) As exclusões para arquivos abertos pelo processo só se aplicam à proteção em tempo real.

## <a name="configure-and-validate-exclusions"></a>Configurar e validar exclusões

Para configurar e validar exclusões, consulte o seguinte:

- [Configure e valide exclusões com base no nome do arquivo, extensão e local da pasta.](configure-extension-file-exclusions-microsoft-defender-antivirus.md) Isso permite excluir arquivos das verificações do Microsoft Defender Antivírus com base em sua extensão de arquivo, nome de arquivo ou local.

- [Configurar e validar exclusões para arquivos abertos por processos](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md). Isso permite excluir arquivos de verificações que foram abertas por um processo específico.

## <a name="recommendations-for-defining-exclusions"></a>Recomendações para definir exclusões

Definir exclusões reduz a proteção oferecida pelo Microsoft Defender Antivírus. Você sempre deve avaliar os riscos associados à implementação de exclusões, e você deve excluir apenas arquivos que você tem certeza de que não são mal-intencionados.

Veja a seguir uma lista de recomendações que você deve ter em mente ao definir exclusões:  

- As exclusões são tecnicamente uma lacuna de proteção, sempre considerem mitigações adicionais ao definir exclusões. Mitigações adicionais podem ser tão simples quanto garantir que o local excluído tenha as listas de controle de acesso (ACLs) apropriadas, a política de auditoria, seja processada por um software atualizado, etc.

- Revise as exclusões periodicamente. Verifique e reaplicação das mitigações como parte do processo de revisão.

- O ideal é evitar definir exclusões proativas. Por exemplo, não exclua algo apenas porque você acha que pode ser um problema no futuro. Use exclusões apenas para problemas específicos, principalmente em torno do desempenho ou, às vezes, em torno da compatibilidade de aplicativos que as exclusões podem atenuar.

- Audite as alterações na lista de exclusão. O administrador de segurança deve preservar o contexto suficiente em torno do motivo pelo qual uma determinada exclusão foi adicionada. Você deve ser capaz de fornecer resposta com um raciocínio específico sobre o motivo pelo qual um determinado caminho foi excluído.

## <a name="related-articles"></a>Artigos relacionados

- [Exclusões do Microsoft Defender Antivírus no Windows Server 2016](configure-server-exclusions-microsoft-defender-antivirus.md)
- [Erros comuns a evitar ao definir exclusões](common-exclusion-mistakes-microsoft-defender-antivirus.md)