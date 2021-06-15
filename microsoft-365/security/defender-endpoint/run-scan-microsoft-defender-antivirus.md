---
title: Executar e personalizar verificações sob demanda em Microsoft Defender Antivírus
description: Executar e configurar verificações sob demanda usando o PowerShell, Windows Instrumentação de Gerenciamento ou individualmente nos pontos de extremidade com o aplicativo Segurança do Windows de gerenciamento
keywords: verificação, sob demanda, dos, intune, verificação instantânea
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/10/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: b2910f9fe1c49178b8696d1a421248156b0fc4c2
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925726"
---
# <a name="configure-and-run-on-demand-microsoft-defender-antivirus-scans"></a>Configurar e executar verificações do Microsoft Defender Antivírus sob demanda

**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)

Você pode executar uma verificação sob demanda em pontos de extremidade individuais. Essas verificações serão iniciais imediatamente e você pode definir parâmetros para a verificação, como o local ou o tipo. Ao executar uma verificação, você pode escolher entre três tipos: verificação rápida, verificação completa e verificação personalizada. Na maioria dos casos, use uma verificação rápida. Uma verificação rápida analisa todos os locais onde pode haver malware registrado para começar com o sistema, como chaves de registro e pastas de inicialização Windows conhecidas. 

Combinado com a proteção sempre em tempo real, que revisa arquivos quando eles são abertos e fechados e sempre que um usuário navega para uma pasta, uma verificação rápida ajuda a fornecer uma proteção forte contra malware que começa com o sistema e malware no nível do kernel. Na maioria dos casos, uma verificação rápida é suficiente e é a opção recomendada para verificações agendadas ou sob demanda.  [Saiba mais sobre tipos de verificação](schedule-antivirus-scans.md#quick-scan-full-scan-and-custom-scan).

> [!IMPORTANT]
> Microsoft Defender Antivírus é executado no contexto da conta [LocalSystem](/windows/win32/services/localsystem-account) ao executar uma verificação local. Para verificações de rede, ele usa o contexto da conta do dispositivo. Se a conta do dispositivo de domínio não tiver permissões apropriadas para acessar o compartilhamento, a verificação não funcionará. Verifique se o dispositivo tem permissões para o compartilhamento de rede de acesso.

## <a name="use-microsoft-endpoint-manager-to-run-a-scan"></a>Usar Microsoft Endpoint Manager para executar uma verificação

1. Vá para o Microsoft Endpoint Manager de administração ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) e faça logoff.

2. Escolha **Endpoint security**  >  **Antivírus**.

3. Na lista de guias, selecione Windows 10 pontos de extremidade **não salubres**.

4. Na lista de ações fornecidas, selecione **Verificação Rápida** (recomendado) ou **Verificação Completa.**

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

2. Na barra lateral, selecione **Dispositivos**  >  **Todos os Dispositivos** e escolha o dispositivo que você deseja examinar.

3. Selecione **... Mais**. Nas opções, selecione **Verificação Rápida** (recomendado) ou **Verificação Completa**.

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

