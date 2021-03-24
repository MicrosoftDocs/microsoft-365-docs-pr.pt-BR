---
title: Solucionar problemas com regras de redução de superfície de ataque
description: Recursos e código de exemplo para solucionar problemas com regras de redução de superfície de ataque no Microsoft Defender para Ponto de Extremidade.
keywords: solução de problemas, erro, correção, windows defender por exemplo, asr, regras, quadris, solução de problemas, auditoria, exclusão, falso positivo, quebrado, bloqueado, microsoft defender para ponto de extremidade, proteção avançada contra ameaças do Microsoft Defender
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.date: 03/27/2019
ms.reviewer: ''
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.openlocfilehash: d090c82e8c76da8f2e19dc9189006fdea3d6990d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054047"
---
# <a name="troubleshoot-attack-surface-reduction-rules"></a>Solucionar problemas de regras de redução de superfície de ataque

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


Quando você usa regras [de redução de superfície de](attack-surface-reduction.md) ataque, você pode ter problemas, como:

- Uma regra bloqueia um arquivo, um processo ou executa alguma outra ação que não deve (falso positivo)

- Uma regra não funciona conforme descrito ou não bloqueia um arquivo ou processo que deve (falso negativo)

Há quatro etapas para solucionar esses problemas:

1. [Confirmar pré-requisitos](#confirm-prerequisites)

2. [Usar o modo de auditoria para testar a regra](#use-audit-mode-to-test-the-rule)

3. [Adicionar exclusões para a regra especificada](#add-exclusions-for-a-false-positive) (para falsos positivos)

4. [Enviar logs de suporte](#collect-diagnostic-data-for-file-submissions)

## <a name="confirm-prerequisites"></a>Confirmar pré-requisitos

As regras de redução de superfície de ataque funcionarão apenas em dispositivos com as seguintes condições:

- Os pontos de extremidade estão executando o Windows 10 Enterprise, versão 1709 (também conhecido como Fall Creators Update).

- Os pontos de extremidade estão usando o Microsoft Defender Antivírus como o único aplicativo de proteção antivírus. [O uso de qualquer outro aplicativo antivírus fará com que o Microsoft Defender AV se desabilite](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility).

- [A proteção em tempo real](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) está habilitada.

- O modo de auditoria não está habilitado. Use a Política de Grupo para definir a regra como **Desabilitada** (valor: **0**) conforme descrito em [Habilitar regras de](enable-attack-surface-reduction.md)redução de superfície de ataque .

Se todos esses pré-requisitos foram atendidos, prossiga para a próxima etapa para testar a regra no modo de auditoria.

## <a name="use-audit-mode-to-test-the-rule"></a>Usar o modo de auditoria para testar a regra

Você pode visitar o site do Windows Defender Test ground no [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) para confirmar que as regras de redução de superfície de ataque geralmente estão funcionando para cenários e processos pré-configurados em um dispositivo ou você pode usar o modo de auditoria, que permite regras somente para relatórios.

Siga estas instruções em [Usar a ferramenta de demonstração](evaluate-attack-surface-reduction.md) para ver como funcionam as regras de redução de superfície de ataque para testar a regra específica com a qual você está encontrando problemas.

1. Habilitar o modo de auditoria para a regra específica que você deseja testar. Use a Política de Grupo para definir a regra como **Modo de** Auditoria (valor: **2**) conforme descrito em [Habilitar regras de](enable-attack-surface-reduction.md)redução de superfície de ataque . O modo de auditoria permite que a regra reporte o arquivo ou o processo, mas ainda permitirá que ele seja executado.

2. Execute a atividade que está causando um problema (por exemplo, abra ou execute o arquivo ou processo que deve ser bloqueado, mas está sendo permitido).

3. [Revise os logs de](attack-surface-reduction.md) eventos de regra de redução de superfície de ataque para ver se a regra teria bloqueado o arquivo ou o processo se a regra tivesse sido definida como **Enabled**.

Se uma regra não estiver bloqueando um arquivo ou processo que você espera que ele bloqueie, primeiro verifique se o modo de auditoria está habilitado.

O modo de auditoria pode ter sido habilitado para testar outro recurso ou por um script do PowerShell automatizado e pode não ter sido desabilitado após a conclusão dos testes.

Se você testou a regra com a ferramenta de demonstração e com o modo de auditoria, e as regras de redução de superfície de ataque estão funcionando em cenários pré-configurados, mas a regra não está funcionando conforme esperado, prossiga para uma das seções a seguir com base em sua situação:

1. Se a regra de redução de superfície de ataque estiver bloqueando algo que não deve ser bloqueado (também conhecido como falso positivo), primeiro você poderá adicionar uma exclusão de regra de redução de superfície [de ataque.](#add-exclusions-for-a-false-positive)

2. Se a regra de redução de superfície de ataque não estiver bloqueando algo que ela deve bloquear (também conhecido como falso negativo), você poderá prosseguir imediatamente para a última etapa, coletando dados de diagnóstico e enviando o problema para [nós](#collect-diagnostic-data-for-file-submissions).

## <a name="add-exclusions-for-a-false-positive"></a>Adicionar exclusões para um falso positivo

Se a regra de redução de superfície de ataque estiver bloqueando algo que não deve ser bloqueado (também conhecido como falso positivo), você poderá adicionar exclusões para impedir que as regras de redução de superfície de ataque avaliam os arquivos ou pastas excluídos.

Para adicionar uma exclusão, consulte [Customize Attack surface reduction](customize-attack-surface-reduction.md).

>[!IMPORTANT]
>Você pode especificar arquivos e pastas individuais a serem excluídos, mas não pode especificar regras individuais.
>Isso significa que todos os arquivos ou pastas excluídos serão excluídos de todas as regras ASR.

## <a name="report-a-false-positive-or-false-negative"></a>Relatar um falso positivo ou falso negativo

Use o [Windows Defender de](https://www.microsoft.com/wdsi/filesubmission) envio baseado na Web de Inteligência de Segurança para relatar um falso negativo ou falso positivo para proteção de rede. Com uma assinatura do Windows E5, você também pode fornecer um [link para qualquer alerta associado.](alerts-queue.md)

## <a name="collect-diagnostic-data-for-file-submissions"></a>Coletar dados de diagnóstico para envios de arquivos

Quando você relata um problema com regras de redução de superfície de ataque, é solicitado a coletar e enviar dados de diagnóstico que podem ser usados pelo suporte da Microsoft e equipes de engenharia para ajudar a solucionar problemas.

1. Abra um prompt de comando elevado e altere para o Windows Defender diretório:

   ```console
   cd "c:\program files\windows defender"
   ```

2. Execute este comando para gerar os logs de diagnóstico:

   ```console
   mpcmdrun -getfiles
   ```

3. Por padrão, eles são salvos em `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab` . Anexe o arquivo ao formulário de envio.

## <a name="related-articles"></a>Artigos relacionados

- [Regras de redução de superfície de ataque](attack-surface-reduction.md)

- [Habilitar regras de redução de superfície de ataque](enable-attack-surface-reduction.md)

- [Avaliar regras de redução de superfície de ataque](evaluate-attack-surface-reduction.md)
