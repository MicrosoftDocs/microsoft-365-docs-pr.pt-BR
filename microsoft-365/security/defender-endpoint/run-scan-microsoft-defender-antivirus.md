---
title: Executar e personalizar verificações sob demanda em Microsoft Defender Antivírus
description: Executar e configurar verificações sob demanda usando o PowerShell, Windows Instrumentação de Gerenciamento ou individualmente nos pontos de extremidade com o aplicativo Segurança do Windows de gerenciamento
keywords: verificação, sob demanda, dos, intune, verificação instantânea
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/04/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: fdca059633ab0993e07b5b1be0c6f33cfe327fcf
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789166"
---
# <a name="configure-and-run-on-demand-microsoft-defender-antivirus-scans"></a>Configurar e executar verificações do Microsoft Defender Antivírus sob demanda

**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)

Você pode executar uma verificação sob demanda em pontos de extremidade individuais. Essas verificações serão iniciais imediatamente e você pode definir parâmetros para a verificação, como o local ou o tipo.

## <a name="quick-scan-versus-full-scan"></a>Verificação rápida versus verificação completa

A verificação rápida analisa todos os locais onde pode haver malware registrado para começar com o sistema, como chaves do Registro e pastas de inicialização Windows conhecidas.

> [!IMPORTANT]
> Microsoft Defender Antivírus é executado no contexto da conta [LocalSystem](/windows/win32/services/localsystem-account) ao executar uma verificação local. Para verificações de rede, ele usa o contexto da conta do dispositivo. Se a conta do dispositivo de domínio não tiver permissões apropriadas para acessar o compartilhamento, a verificação não funcionará. Verifique se o dispositivo tem permissões para o compartilhamento de rede de acesso.

Combinado com a funcionalidade de proteção sempre em [tempo real,](configure-real-time-protection-microsoft-defender-antivirus.md)uma verificação rápida ajuda a fornecer uma cobertura forte para malware que começa com o sistema e malware no nível do kernel. A proteção sempre em tempo real revisa arquivos quando eles são abertos e fechados e sempre que um usuário navega para uma pasta. Por padrão, verificações rápidas são executados em dispositivos removíveis montados, como unidades USB. Na maioria dos casos, uma verificação rápida é adequada para encontrar malware que não foi escolhido pela proteção em tempo real.

Uma verificação completa pode ser útil quando uma ameaça de malware é relatada em um ponto de extremidade. A verificação pode identificar se há componentes inativos que exigem uma limpeza mais completa. No entanto, a Microsoft geralmente recomenda usar verificações rápidas em vez de verificações completas. Uma verificação completa pode levar algumas horas ou dias para ser concluída, dependendo da quantidade e do tipo de dados que precisam ser verificados. 

> [!TIP]
> Para saber mais sobre as diferenças entre verificações rápidas e completas, consulte Verificação rápida versus verificação [completa e verificação personalizada.](scheduled-catch-up-scans-microsoft-defender-antivirus.md#quick-scan-versus-full-scan-and-custom-scan)

## <a name="use-microsoft-endpoint-manager-to-run-a-scan"></a>Usar Microsoft Endpoint Manager para executar uma verificação

1. Vá para o Microsoft Endpoint Manager de administração ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) e faça logoff.
2. Escolha **Endpoint security**  >  **Antivírus**.
3. Na lista de guias, selecione Windows 10 pontos de extremidade **não salubres**.
4. Na lista de ações fornecidas, selecione **Verificação Rápida** ou **Verificação Completa**.

[![IMAGE ](images/mem-antivirus-scan-on-demand.png)](images/mem-antivirus-scan-on-demand.png#lightbox)

> [!TIP]
> Para obter mais informações sobre como Microsoft Endpoint Manager executar uma verificação, consulte [Tarefas de antimalware](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers)e firewall: como executar uma verificação sob demanda.

## <a name="use-the-mpcmdrunexe-command-line-utility-to-run-a-scan"></a>Use o mpcmdrun.exe de linha de comando para executar uma verificação

Use o seguinte `-scan` parâmetro:

```console
mpcmdrun.exe -scan -scantype 1
```

Para obter mais informações sobre como usar a ferramenta e parâmetros adicionais, incluindo iniciar uma verificação completa ou definir caminhos, consulte [Usar a](command-line-arguments-microsoft-defender-antivirus.md)ferramenta de linha de comando mpcmdrun.exe para configurar e gerenciar Microsoft Defender Antivírus .

## <a name="use-microsoft-intune-to-run-a-scan"></a>Usar Microsoft Intune para executar uma verificação

1. Vá para o Microsoft Endpoint Manager de administração ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) e faça logoff.
2. Na barra lateral, selecione **Dispositivos > Todos os** Dispositivos e escolha o dispositivo que você deseja examinar.
3. Selecione **... Mais**. Nas opções, selecione **Verificação Rápida** ou **Verificação Completa.**

## <a name="use-the-windows-security-app-to-run-a-scan"></a>Usar o Segurança do Windows para executar uma verificação

Consulte [Executar uma verificação no aplicativo Segurança do Windows para](microsoft-defender-security-center-antivirus.md) obter instruções sobre como executar uma verificação em pontos de extremidade individuais.

## <a name="use-powershell-cmdlets-to-run-a-scan"></a>Usar cmdlets do PowerShell para executar uma verificação

Use o seguinte cmdlet:

```PowerShell
Start-MpScan
```

Para obter mais informações sobre como usar o PowerShell com Microsoft Defender Antivírus, consulte [Usar cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) do PowerShell para configurar e executar [cmdlets](/powershell/module/defender/)Microsoft Defender Antivírus e Defender.

## <a name="use-windows-management-instruction-wmi-to-run-a-scan"></a>Use Windows Instrução de Gerenciamento (WMI) para executar uma verificação

Use o [ **método Start**](/previous-versions/windows/desktop/defender/start-msft-mpscan) da **classe MSFT_MpScan.**

Para obter mais informações sobre quais parâmetros são permitidos, [consulte Windows Defender APIs WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="related-articles"></a>Artigos relacionados

- [Configurar opções de verificação do Microsoft Defender Antivírus](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [Configurar verificações Microsoft Defender Antivírus agendadas](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus no Windows 10](microsoft-defender-antivirus-in-windows-10.md)