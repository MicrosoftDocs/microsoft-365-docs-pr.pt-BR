---
title: Microsoft Defender Antivírus
description: Saiba como gerenciar, configurar e usar o Microsoft Defender Antivírus, a proteção antimalware e antivírus integrada.
keywords: Microsoft Defender Antivírus, windows defender, antimalware, scep, system center endpoint protection, system center configuration manager, vírus, malware, ameaça, detecção, proteção, segurança
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Priority
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.reviewer: mkaminska
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: ceaf694d8b81e6b06ffe74efc4ad3d4d73471752
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322453"
---
# <a name="microsoft-defender-antivirus-in-windows"></a>Microsoft Defender Antivírus no Windows

**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)

O Microsoft Defender Antivírus é um componente importante da sua proteção da próxima geração no Microsoft Defender para Ponto de Extremidade. Essa proteção reúne o aprendizado de máquina, análise de big data, pesquisa aprofundada de resistência a ameaças e a infraestrutura de nuvem da Microsoft para proteger dispositivos (ou pontos de extremidade) em sua organização. O Microsoft Defender Antivírus está integrado ao Windows, e funciona com o Microsoft Defender para Ponto de Extremidade para fornecer proteção ao seu dispositivo e na nuvem. 

## <a name="compatibility-with-other-antivirus-products"></a>Compatibilidade com outros produtos antivírus

Se estiver usando, em seu dispositivo, um produto antivírus/antimalware que não seja da Microsoft, você poderá executar o Microsoft Defender Antivírus no modo passivo junto com a solução de antivírus que não seja da Microsoft. Depende do sistema operacional utilizado e se seu dispositivo está integrado ao Defender para Ponto de extremidade. Para saber mais, consulte [Compatibilidade do Microsoft Defender Antivírus](microsoft-defender-antivirus-compatibility.md).

## <a name="comparing-active-mode-passive-mode-and-disabled-mode"></a>Comparando o modo ativo, modo passivo e modo desabilitado

A tabela a seguir descreve o que esperar quando o Microsoft Defender Antivírus está em modo ativo, modo passivo ou desativado.

| Modo  | O que acontece  |
|---------|---------|
| Modo ativo | No modo ativo, o Microsoft Defender Antivírus é usado como o principal aplicativo antivírus no dispositivo. Os arquivos são verificados, as ameaças são corrigidas e as ameaças detectadas são listadas nos relatórios de segurança da sua organização e no seu aplicativo de Segurança do Windows. |
| Modo passivo | No modo passivo, o Microsoft Defender Antivírus não é usado como o principal aplicativo antivírus no dispositivo. Os arquivos são verificados e as ameaças detectadas são relatadas, mas as ameaças não são corrigidas pelo Microsoft Defender Antivírus.   |
| Desativado ou desinstalado  | Quando desabilitado ou desinstalado, o Microsoft Defender Antivírus não é utilizado. Os arquivos não são verificados e as ameaças não são corrigidas. Em geral, não recomendamos desativar ou desinstalar o Microsoft Defender Antivírus.  |

Para saber mais, consulte [Compatibilidade do Microsoft Defender Antivírus](microsoft-defender-antivirus-compatibility.md).

## <a name="check-the-state-of-microsoft-defender-antivirus-on-your-device"></a>Verifique o estado do Microsoft Defender Antivírus no seu dispositivo

Se quiser verificar o estado do Microsoft Defender Antivírus em seu dispositivo, você pode usar um dos vários métodos, como o aplicativo de Segurança do Windows ou o Windows PowerShell.

### <a name="use-the-windows-security-app-to-check-status-of-microsoft-defender-antivirus"></a>Use o aplicativo de Segurança do Windows para verificar o status do Microsoft Defender Antivírus

1. Em seu dispositivo Windows, selecione o menu Iniciar e comece a digitar `Security`. Em seguida, abra o aplicativo de Segurança do Windows nos resultados.

2. Select **Proteção contra vírus e ameaças**.

3. Em **Configurações de proteção contra vírus e ameaças**, escolha **Gerenciar configurações**.

Você verá o nome de sua solução de antivírus/antimalware na página de configurações.

### <a name="use-powershell-to-check-status-of-microsoft-defender-antivirus"></a>Use o PowerShell para verificar o status do Microsoft Defender Antivírus

1. Selecione o menu Iniciar e comece a digitar `PowerShell`. Em seguida, abra o Windows PowerShell nos resultados.

2. Digitar `Get-MpComputerStatus`.

3. Na lista de resultados, observe a linha **AMRunningMode**.

   - **Normal** significa que o Microsoft Defender Antivírus está sendo executado no modo ativo.
   - **Modo passivo** significa que o Microsoft Defender Antivírus está em execução, mas não é o principal produto antivírus/antimalware do seu dispositivo.
   - **Modo de Bloqueio EDR** significa que o Microsoft Defender Antivírus está em execução e uma funcionalidade no Microsoft Defender para Ponto de Extremidade chamada "EDR em modo de bloco" está habilitada. (Consulte [Detecção e resposta do ponto de extremidade (EDR) no modo de bloqueio](edr-in-block-mode.md).)
   - **Modo Passivo SxS** significa que o Microsoft Defender Antivírus está sendo executado em modo passivo junto com outro produto antivírus/antimalware e seu dispositivo não está integrado ao Microsoft Defender para Ponto de Extremidade. Nesse caso, uma verificação periódica limitada é usada para o Microsoft Defender Antivírus. Para saber mais, consulte [Usar a verificação periódica limitada no Microsoft Defender Antivírus](limited-periodic-scanning-microsoft-defender-antivirus.md).

Para saber mais sobre o cmdlet do PowerShell Get-MpComputerStatus, consulte o artigo de referência [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus).

## <a name="get-your-antivirusantimalware-platform-updates"></a>Obtenha atualizações da plataforma de antivírus/antimalware

É importante manter o Microsoft Defender Antivírus, ou qualquer solução antivírus/antimalware, atualizado. A Microsoft lança atualizações regulares para ajudar a garantir que seus dispositivos tenham a tecnologia mais recente para proteção contra novos malwares e técnicas de ataque. Para saber mais, consulte [Gerenciar atualizações do Microsoft Defender Antivírus e aplicar linhas de base](manage-updates-baselines-microsoft-defender-antivirus.md). 

## <a name="see-also"></a>Confira também

- [Microsoft Defender Antivírus no Windows Server](microsoft-defender-antivirus-on-windows-server.md)
- [Gerenciamento e configuração do Microsoft Defender Antivírus](configuration-management-reference-microsoft-defender-antivirus.md)
- [Avaliar a proteção do Microsoft Defender Antivírus](evaluate-microsoft-defender-antivirus.md)
