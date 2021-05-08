---
title: Microsoft Defender Offline no Windows 10
description: Você pode usar Microsoft Defender Offline diretamente do aplicativo Windows Defender Antivírus aplicativo. Você também pode gerenciar como ele é implantado em sua rede.
keywords: scan, defender, offline
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: a25a2ec513cd7c25f9f6ddf3d5e328928837bf2d
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275139"
---
# <a name="run-and-review-the-results-of-a-microsoft-defender-offline-scan"></a>Executar e revisar os resultados de uma verificação do Microsoft Defender Offline

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)

Microsoft Defender Offline é uma ferramenta de verificação antimalware que permite inicializar e executar uma verificação de um ambiente confiável. A verificação é executado de fora do kernel normal Windows para que ele possa direcionar malware que tenta ignorar o shell Windows, como vírus e rootkits que infectam ou sobrescrevem o registro de inicialização mestre (MBR).

Você pode usar Microsoft Defender Offline se suspeitar de uma infecção por malware ou se deseja confirmar uma limpeza completa do ponto de extremidade após um surto de malware.

Em Windows 10, Microsoft Defender Offline pode ser executado com um clique diretamente no Segurança do Windows [app](microsoft-defender-security-center-antivirus.md). Nas versões anteriores do Windows, um usuário precisava instalar Microsoft Defender Offline mídia inicializável, reiniciar o ponto de extremidade e carregar a mídia inicializável.

## <a name="prerequisites-and-requirements"></a>pré-requisitos e requisitos

Microsoft Defender Offline no Windows 10 tem os mesmos requisitos de hardware que Windows 10. 

Para obter mais informações sobre Windows 10 requisitos, consulte os seguintes tópicos:

- [Requisitos mínimos de hardware](/windows-hardware/design/minimum/minimum-hardware-requirements-overview)

- [Diretrizes de componentes de hardware](/windows-hardware/design/component-guidelines/components)

> [!NOTE]
> Microsoft Defender Offline não é suportado em máquinas com processadores ARM ou em unidades de manutenção de Windows Servidor.

Para executar Microsoft Defender Offline ponto de extremidade, o usuário deve estar conectado com privilégios de administrador.
 
## <a name="microsoft-defender-offline-updates"></a>Microsoft Defender Offline atualizações

Microsoft Defender Offline usa as atualizações de proteção mais recentes disponíveis no ponto de extremidade; ele é atualizado sempre que Windows Defender Antivírus é atualizado. 

> [!NOTE]
> Antes de executar uma verificação offline, você deve tentar atualizar a proteção do Microsoft Defender AV. Você pode forçar uma atualização com a Política de Grupo ou, no entanto, normalmente implantar atualizações nos pontos de extremidade ou baixar manualmente e instalar as atualizações de proteção mais recentes do [Centro de Proteção contra Malware da Microsoft](https://www.microsoft.com/security/portal/definitions/adl.aspx).

Consulte o [tópico Gerenciar Microsoft Defender Antivírus de](manage-protection-updates-microsoft-defender-antivirus.md) inteligência de segurança para obter mais informações.

## <a name="usage-scenarios"></a>Cenários de uso

No Windows 10, versão 1607, você pode forçar manualmente uma verificação offline. Como alternativa, se Windows Defender determinar que o Microsoft Defender Offline precisa ser executado, ele solicitará ao usuário no ponto de extremidade. 

A necessidade de executar uma verificação offline também será revelada Microsoft Endpoint Manager se você estiver usando-a para gerenciar seus pontos de extremidade.

O prompt pode ocorrer por meio de uma notificação, semelhante ao seguinte:

![Windows notificação mostrando o requisito para executar Microsoft Defender Offline](images/defender/notification.png)

O usuário também será notificado dentro do Windows Defender cliente.

No Configuration Manager, você pode identificar o status dos pontos de extremidade navegando até **Monitoring > Overview > Security > Endpoint Protection Status > System Center Endpoint Protection Status**. 

Microsoft Defender Offline as verificações são indicadas em **Status de correção de malware** conforme a verificação offline **necessária**.

![Microsoft Endpoint Manager indicando que uma Microsoft Defender Offline de verificação é necessária](images/defender/sccm-wdo.png)

## <a name="configure-notifications"></a>Configurar notificações

Microsoft Defender Offline as notificações são configuradas na mesma configuração de política que outras notificações do Microsoft Defender AV.

Para obter mais informações sobre notificações Windows Defender, consulte o tópico Configurar as notificações que [aparecem nos pontos de](configure-notifications-microsoft-defender-antivirus.md) extremidade.

## <a name="run-a-scan"></a>Executar uma verificação 

> [!IMPORTANT]
> Antes de usar Microsoft Defender Offline, salve todos os arquivos e desligue os programas em execução. A Microsoft Defender Offline de verificação leva cerca de 15 minutos para ser executado. Ele reiniciará o ponto de extremidade quando a verificação for concluída. A verificação é realizada fora do ambiente operacional Windows normal. A interface do usuário aparecerá diferente de uma verificação normal realizada por Windows Defender. Depois que a verificação for concluída, o ponto de extremidade será reiniciado e Windows carregará normalmente.

Você pode executar uma Microsoft Defender Offline com o seguinte:

- PowerShell
- Windows Instrumentação de Gerenciamento (WMI)
- O Segurança do Windows app



### <a name="use-powershell-cmdlets-to-run-an-offline-scan"></a>Usar cmdlets do PowerShell para executar uma verificação offline

Use os seguintes cmdlets:

```PowerShell
Start-MpWDOScan
```

Consulte [Usar cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) do PowerShell para configurar e executar [cmdlets](/powershell/module/defender/) Microsoft Defender Antivírus e Defender para obter mais informações sobre como usar o PowerShell com Microsoft Defender Antivírus.

### <a name="use-windows-management-instruction-wmi-to-run-an-offline-scan"></a>Use Windows Instrução de Gerenciamento (WMI) para executar uma verificação offline

Use a [**MSFT_MpWDOScan**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para executar uma verificação offline.

O trecho de script WMI a seguir executará imediatamente uma verificação de Microsoft Defender Offline, o que fará com que o ponto de extremidade seja reiniciado, execute a verificação offline e, em seguida, reinicie e inicializar em Windows.

```console
wmic /namespace:\\root\Microsoft\Windows\Defender path MSFT_MpWDOScan call Start 
```

Confira o seguinte para obter mais informações:
- [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


### <a name="use-the-windows-defender-security-app-to-run-an-offline-scan"></a>Usar o Windows Defender de segurança para executar uma verificação offline

1. Abra o Segurança do Windows aplicativo clicando no ícone de escudo na barra de tarefas ou pesquisando o menu inicial do **Defender**.

2. Clique no **&** proteção contra ameaças (ou o ícone de escudo na barra de menus esquerda) e, em seguida, o **rótulo de verificação** avançado:
    
3. Selecione **Microsoft Defender Offline examinar e** clique em Examinar **agora**.

    > [!NOTE]
    > No Windows 10, versão 1607, a verificação offline poderia ser executado em **Windows Configurações** Atualização & segurança Windows Defender ou do  >    >   cliente Windows Defender.


## <a name="review-scan-results"></a>Revisar resultados da verificação

Microsoft Defender Offline os resultados da verificação serão listados na seção Histórico de verificação [do Segurança do Windows app](microsoft-defender-security-center-antivirus.md). 


## <a name="related-articles"></a>Artigos relacionados

- [Personalizar, iniciar e revisar os resultados de verificações e correção](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivírus no Windows 10](microsoft-defender-antivirus-in-windows-10.md)