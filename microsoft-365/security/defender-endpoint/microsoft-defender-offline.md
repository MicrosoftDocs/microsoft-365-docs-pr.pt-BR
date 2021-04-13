---
title: Microsoft Defender Offline no Windows 10
description: Você pode usar o Microsoft Defender Offline diretamente do aplicativo Windows Defender Antivírus. Você também pode gerenciar como ele é implantado em sua rede.
keywords: scan, defender, offline
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 44a0e78ecfe3854a070831bf01a012c2cec06ce7
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689798"
---
# <a name="run-and-review-the-results-of-a-microsoft-defender-offline-scan"></a>Executar e revisar os resultados de uma verificação offline do Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)

O Microsoft Defender Offline é uma ferramenta de verificação antimalware que permite inicializar e executar uma verificação de um ambiente confiável. A verificação é executado de fora do kernel normal do Windows para que ele possa direcionar o malware que tenta ignorar o shell do Windows, como vírus e rootkits que infectam ou sobrescrevem o registro de inicialização mestre (MBR).

Você pode usar o Microsoft Defender Offline se suspeitar de uma infecção por malware ou se deseja confirmar uma limpeza completa do ponto de extremidade após uma epidemia de malware.

No Windows 10, o Microsoft Defender Offline pode ser executado com um clique diretamente no aplicativo [segurança do Windows.](microsoft-defender-security-center-antivirus.md) Nas versões anteriores do Windows, um usuário precisava instalar o Microsoft Defender Offline para a mídia inicializável, reiniciar o ponto de extremidade e carregar a mídia inicializável.

## <a name="prerequisites-and-requirements"></a>pré-requisitos e requisitos

O Microsoft Defender Offline no Windows 10 tem os mesmos requisitos de hardware do Windows 10. 

Para obter mais informações sobre os requisitos do Windows 10, consulte os seguintes tópicos:

- [Requisitos mínimos de hardware](/windows-hardware/design/minimum/minimum-hardware-requirements-overview)

- [Diretrizes de componentes de hardware](/windows-hardware/design/component-guidelines/components)

> [!NOTE]
> O Microsoft Defender Offline não é suportado em computadores com processadores ARM ou em Unidades de Manutenção de Ações do Windows Server.

Para executar o Microsoft Defender Offline no ponto de extremidade, o usuário deve estar conectado com privilégios de administrador.
 
## <a name="microsoft-defender-offline-updates"></a>Atualizações offline do Microsoft Defender

O Microsoft Defender Offline usa as atualizações de proteção mais recentes disponíveis no ponto de extremidade; ele é atualizado sempre que Windows Defender Antivírus é atualizado. 

> [!NOTE]
> Antes de executar uma verificação offline, você deve tentar atualizar a proteção do Microsoft Defender AV. Você pode forçar uma atualização com a Política de Grupo ou, no entanto, normalmente implantar atualizações nos pontos de extremidade ou baixar manualmente e instalar as atualizações de proteção mais recentes do [Centro de Proteção contra Malware da Microsoft](https://www.microsoft.com/security/portal/definitions/adl.aspx).

Consulte o tópico Gerenciar atualizações de inteligência [de segurança do Microsoft Defender Antivírus](manage-protection-updates-microsoft-defender-antivirus.md) para obter mais informações.

## <a name="usage-scenarios"></a>Cenários de uso

No Windows 10, versão 1607, você pode forçar manualmente uma verificação offline. Como alternativa, se Windows Defender determinar que o Microsoft Defender Offline precisa ser executado, ele solicitará ao usuário no ponto de extremidade. 

A necessidade de executar uma verificação offline também será revelada no Microsoft Endpoint Manager se você estiver usando-a para gerenciar seus pontos de extremidade.

O prompt pode ocorrer por meio de uma notificação, semelhante ao seguinte:

![Notificação do Windows mostrando o requisito para executar o Microsoft Defender Offline](images/defender/notification.png)

O usuário também será notificado dentro do Windows Defender cliente.

No Configuration Manager, você pode identificar o status dos pontos de extremidade navegando até **Monitoring > Overview > Security > Endpoint Protection Status > System Center Endpoint Protection Status**. 

As verificações offline do Microsoft Defender são indicadas em **Status de correção de malware** conforme a verificação offline **necessária**.

![O Microsoft Endpoint Manager indicando que uma verificação offline do Microsoft Defender é necessária](images/defender/sccm-wdo.png)

## <a name="configure-notifications"></a>Configurar notificações

As notificações offline do Microsoft Defender são configuradas na mesma configuração de política que outras notificações do Microsoft Defender AV.

Para obter mais informações sobre notificações Windows Defender, consulte [o tópico Configurar](configure-notifications-microsoft-defender-antivirus.md) as notificações que aparecem nos pontos de extremidade.

## <a name="run-a-scan"></a>Executar uma verificação 

> [!IMPORTANT]
> Antes de usar o Microsoft Defender Offline, salve todos os arquivos e desligue os programas em execução. A verificação offline do Microsoft Defender leva cerca de 15 minutos para ser executado. Ele reiniciará o ponto de extremidade quando a verificação for concluída. A verificação é realizada fora do ambiente operacional Windows normal. A interface do usuário aparecerá diferente de uma verificação normal realizada por Windows Defender. Depois que a verificação for concluída, o ponto de extremidade será reiniciado e o Windows será carregado normalmente.

Você pode executar uma verificação offline do Microsoft Defender com o seguinte:

- PowerShell
- Instrumentação de Gerenciamento do Windows (WMI)
- O aplicativo segurança do Windows



### <a name="use-powershell-cmdlets-to-run-an-offline-scan"></a>Usar cmdlets do PowerShell para executar uma verificação offline

Use os seguintes cmdlets:

```PowerShell
Start-MpWDOScan
```

Consulte [Usar cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) do PowerShell para configurar e executar [cmdlets](/powershell/module/defender/) do Microsoft Defender Antivírus e do Defender para obter mais informações sobre como usar o PowerShell com o Microsoft Defender Antivírus.

### <a name="use-windows-management-instruction-wmi-to-run-an-offline-scan"></a>Usar a Instrução de Gerenciamento do Windows (WMI) para executar uma verificação offline

Use a [**MSFT_MpWDOScan**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para executar uma verificação offline.

O trecho de script WMI a seguir executará imediatamente uma verificação offline do Microsoft Defender, que fará com que o ponto de extremidade seja reiniciado, execute a verificação offline e, em seguida, reinicie e inicializar no Windows.

```console
wmic /namespace:\\root\Microsoft\Windows\Defender path MSFT_MpWDOScan call Start 
```

Confira o seguinte para obter mais informações:
- [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


### <a name="use-the-windows-defender-security-app-to-run-an-offline-scan"></a>Usar o Windows Defender de segurança para executar uma verificação offline

1. Abra o aplicativo segurança do Windows clicando no ícone de escudo na barra de tarefas ou pesquisando o menu inicial do **Defender**.

2. Clique no **&** proteção contra ameaças (ou o ícone de escudo na barra de menus esquerda) e, em seguida, o **rótulo de verificação** avançado:
    
3. Selecione **a verificação offline do Microsoft Defender e** clique em Examinar **agora**.

    > [!NOTE]
    > No Windows 10, versão 1607, a verificação offline poderia ser executado em **Windows Settings** Update & segurança Windows Defender ou do  >    >   cliente Windows Defender.


## <a name="review-scan-results"></a>Revisar resultados da verificação

Os resultados da verificação offline do Microsoft Defender serão listados na seção Histórico de verificação [do aplicativo segurança do Windows.](microsoft-defender-security-center-antivirus.md) 


## <a name="related-articles"></a>Artigos relacionados

- [Personalizar, iniciar e revisar os resultados de verificações e correção](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivírus no Windows 10](microsoft-defender-antivirus-in-windows-10.md)