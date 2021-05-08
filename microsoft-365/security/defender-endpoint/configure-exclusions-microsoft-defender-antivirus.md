---
title: Configurar exclusões para Microsoft Defender Antivírus verificações
description: Você pode excluir arquivos (incluindo arquivos modificados por processos especificados) e pastas de serem verificados por Microsoft Defender Antivírus. Valide suas exclusões com o PowerShell.
keywords: ''
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ksarens
manager: dansimp
ms.technology: mde
ms.audience: ITPro
ms.topic: how-to
ms.openlocfilehash: 7065aa7cd1975b2f5a38e79da8618ba3efdcdac5
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275115"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-antivirus-scans"></a>Configurar e validar exclusões para Microsoft Defender Antivírus verificações

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)

Você pode excluir determinados arquivos, pastas, processos e arquivos abertos por processo de Microsoft Defender Antivírus verificações. Essas exclusões se aplicam [](run-scan-microsoft-defender-antivirus.md)a [verificações agendadas,](scheduled-catch-up-scans-microsoft-defender-antivirus.md)verificações sob demanda e proteção e monitoramento sempre em [tempo real.](configure-real-time-protection-microsoft-defender-antivirus.md) As exclusões para arquivos abertos pelo processo só se aplicam à proteção em tempo real.

## <a name="configure-and-validate-exclusions"></a>Configurar e validar exclusões

Para configurar e validar exclusões, consulte o seguinte:

- [Configure e valide exclusões com base no nome do arquivo, extensão e local da pasta.](configure-extension-file-exclusions-microsoft-defender-antivirus.md) Você pode excluir arquivos de Microsoft Defender Antivírus com base em sua extensão de arquivo, nome de arquivo ou local.

- [Configurar e validar exclusões para arquivos abertos por processos](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md). Você pode excluir arquivos de verificações que foram abertas por um processo específico.

## <a name="recommendations-for-defining-exclusions"></a>Recomendações para definir exclusões

> [!IMPORTANT]
> Microsoft Defender Antivírus inclui muitas exclusões automáticas com base em comportamentos conhecidos do sistema operacional e arquivos de gerenciamento típicos, como aqueles usados no gerenciamento empresarial, gerenciamento de banco de dados e outros cenários e situações empresariais.  
> 
> Definir exclusões reduz a proteção oferecida por Microsoft Defender Antivírus. Você sempre deve avaliar os riscos associados à implementação de exclusões, e você deve excluir apenas arquivos que você tem certeza de que não são mal-intencionados.

Lembre-se dos seguintes pontos ao definir exclusões:  

- As exclusões são tecnicamente uma lacuna de proteção. Sempre considere mitigações ao definir exclusões. Outras mitigações podem ser tão simples quanto garantir que o local excluído tenha as listas de controle de acesso (ACLs) apropriadas, a política de auditoria, seja processada por um software atualizado, etc.

- Revise as exclusões periodicamente. Verifique novamente e reaplicação das mitigações como parte do processo de revisão.

- O ideal é evitar a definição de exclusões que pretendem ser proativas. Por exemplo, não exclua algo apenas porque você acha que pode ser um problema no futuro. Use exclusões apenas para problemas específicos, como aqueles relacionados ao desempenho ou à compatibilidade de aplicativos que as exclusões podem atenuar.

- Audite as alterações na lista de exclusão. O administrador de segurança deve preservar o contexto suficiente em torno do motivo pelo qual uma determinada exclusão foi adicionada. Você deve ser capaz de fornecer resposta com um raciocínio específico sobre o motivo pelo qual um determinado caminho foi excluído.

## <a name="related-articles"></a>Artigos relacionados

- [Microsoft Defender Antivírus exclusões no Windows Server 2016](configure-server-exclusions-microsoft-defender-antivirus.md)
- [Erros comuns a evitar ao definir exclusões](common-exclusion-mistakes-microsoft-defender-antivirus.md)
