---
title: Microsoft Defender Antivírus no Windows Server
description: Saiba como habilitar e configurar Microsoft Defender Antivírus no Windows Server 2016 e Windows Server 2019.
keywords: windows defender, server, scep, system center endpoint protection, server 2016, branch atual, server 2012
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.reviewer: pahuijbr, shwjha
manager: dansimp
ms.technology: mde
ms.topic: article
ms.date: 04/23/2021
ms.openlocfilehash: fde1e20eedc50b37fca17dc9dc17dc1c9f1373fa
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52246435"
---
# <a name="microsoft-defender-antivirus-on-windows-server"></a>Microsoft Defender Antivírus no Windows Server

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)

Microsoft Defender Antivírus está disponível nas seguintes edições/versões do Windows Server:
- Windows Server 2019
- Windows Servidor, versão 1803 ou posterior
- Windows Server 2016. 

Em alguns casos, Microsoft Defender Antivírus é chamado de *Endpoint Protection;* no entanto, o mecanismo de proteção é o mesmo. Embora a funcionalidade, a configuração e o gerenciamento sejam amplamente os mesmos para Microsoft Defender Antivírus no Windows 10 [,](microsoft-defender-antivirus-in-windows-10.md)há algumas diferenças importantes no Windows Server:

- No Windows Server, [as exclusões automáticas](configure-server-exclusions-microsoft-defender-antivirus.md) são aplicadas com base na função de servidor definida.
 
- No Windows Server, se você estiver executando uma solução de antivírus/antimalware que não seja da Microsoft, o Microsoft Defender Antivírus não entra no modo passivo ou desabilitado automaticamente. No entanto, você pode definir Microsoft Defender Antivírus modo passivo ou desabilitado manualmente.

## <a name="setting-up-microsoft-defender-antivirus-on-windows-server"></a>Configurando o Microsoft Defender Antivírus no Windows Server

O processo de configuração e execução de Microsoft Defender Antivírus em uma plataforma de servidor inclui várias etapas:

1. [Habilitar a interface](#enable-the-user-interface-on-windows-server).
2. [Instale Microsoft Defender Antivírus](#install-microsoft-defender-antivirus-on-windows-server).
3. [Verifique Microsoft Defender Antivírus está sendo executado](#verify-microsoft-defender-antivirus-is-running).
4. [Atualize sua inteligência de segurança antimalware.](#update-antimalware-security-intelligence)
5. (Conforme necessário) [Enviar amostras](#submit-samples).
6. (Conforme necessário) [Configurar exclusões automáticas](#configure-automatic-exclusions).
7. (Somente se necessário) [Definir Microsoft Defender Antivírus modo passivo](#need-to-set-microsoft-defender-antivirus-to-passive-mode).

## <a name="enable-the-user-interface-on-windows-server"></a>Habilitar a interface do usuário no Windows Server

Por padrão, Microsoft Defender Antivírus é instalado e funcional no Windows Server. Às vezes, a interface do usuário (GUI) é instalada por padrão, mas a GUI não é necessária. Você pode usar o PowerShell, a Política de Grupo ou outros métodos para gerenciar Microsoft Defender Antivírus. 

Se a GUI não estiver instalada no servidor e você quiser instalá-la, o assistente **Adicionar Funções** e Recursos ou cmdlets do PowerShell.

### <a name="turn-on-the-gui-using-the-add-roles-and-features-wizard"></a>Ativar a GUI usando o Assistente de Adicionar Funções e Recursos

1. Consulte [Install roles, role services, and features by using the add Roles and Features Wizard](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard), and use the Add Roles and Features **Wizard**.

2. Quando você chegar à etapa **Recursos** do assistente, em Windows Defender **Recursos,** selecione a **opção GUI para** Windows Defender.

   No Windows Server 2016, o **Assistente de** Adicionar Funções e Recursos tem esta aparência:

   ![Adicionar funções e assistente de recurso mostrando a gui para Windows Defender opção](images/server-add-gui.png)

   No Windows Server 2019, **o Assistente para Adicionar Funções** e Recursos é semelhante.

### <a name="turn-on-the-gui-using-powershell"></a>Ativar a GUI usando o PowerShell

O seguinte cmdlet do PowerShell habilita a interface: 

```PowerShell
Install-WindowsFeature -Name Windows-Defender-GUI
```

## <a name="install-microsoft-defender-antivirus-on-windows-server"></a>Instalar Microsoft Defender Antivírus no Windows Server

Se você precisar instalar ou reinstalar Microsoft Defender Antivírus no Windows Server, poderá fazer isso usando o Assistente para Adicionar Funções e Recursos **ou** o PowerShell.

### <a name="use-the-add-roles-and-features-wizard-to-install-microsoft-defender-antivirus"></a>Use o Assistente para Adicionar Funções e Recursos para instalar Microsoft Defender Antivírus

1. Consulte este [artigo](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard)e use o **Assistente para Adicionar Funções e Recursos.**

2. Quando você chegar à etapa **Recursos** do assistente, selecione a opção Microsoft Defender Antivírus. Selecione também a **opção GUI para Windows Defender.**

### <a name="use-powershell-to-install-microsoft-defender-antivirus"></a>Use o PowerShell para instalar Microsoft Defender Antivírus

Para usar o PowerShell para instalar Microsoft Defender Antivírus, execute o seguinte cmdlet:

```PowerShell
Install-WindowsFeature -Name Windows-Defender
```

As mensagens de evento para o mecanismo de antimalware incluídas Microsoft Defender Antivírus podem ser encontradas em [Eventos av do Microsoft Defender.](troubleshoot-microsoft-defender-antivirus.md)


## <a name="verify-microsoft-defender-antivirus-is-running"></a>Verificar Microsoft Defender Antivírus está sendo executado

Depois Microsoft Defender Antivírus estiver instalado, a próxima etapa é verificar se ele está em execução. No ponto de extremidade Windows Servidor do Windows, execute o seguinte cmdlet do PowerShell:

```PowerShell
Get-Service -Name windefend
```

Para verificar se a proteção de firewall está ativado, execute o seguinte cmdlet do PowerShell:

```PowerShell 
Get-Service -Name mpssvc
```

Como alternativa ao PowerShell, você pode usar o Prompt de Comando para verificar se Microsoft Defender Antivírus está em execução. Para fazer isso, execute o seguinte comando de um prompt de comando: 

```console
sc query Windefend
```

O `sc query` comando retorna informações sobre o Microsoft Defender Antivírus serviço. Quando Microsoft Defender Antivírus estiver em execução, `STATE` o valor será exibido `RUNNING` .

## <a name="update-antimalware-security-intelligence"></a>Atualizar inteligência de segurança antimalware 

Para obter a inteligência de segurança antimalware atualizada, você deve ter o serviço Windows Update em execução. Se você usar um serviço de gerenciamento de atualizações, como o Windows Server Update Services (WSUS), certifique-se de que as atualizações para o Microsoft Defender Antivírus de segurança sejam aprovadas para os computadores que você gerencia.

Por padrão, Windows Update não baixa e instala atualizações automaticamente no Windows Server 2019 ou Windows Server 2016. Você pode alterar essa configuração usando um dos seguintes métodos:


|Método  |Descrição  |
|---------|---------|
|**Windows Atualização** no Painel de Controle     |- **Instalar atualizações resulta automaticamente** em todas as atualizações que estão sendo instaladas automaticamente, incluindo Windows Defender atualizações de inteligência de segurança. <br/>- **Baixe atualizações,** mas deixe-me escolher se instalá-las permite Windows Defender baixar e instalar atualizações de inteligência de segurança automaticamente, mas outras atualizações não são instaladas automaticamente.       |
|**Política de grupo**     | Você pode configurar e gerenciar o Windows Update usando as configurações disponíveis na Política de Grupo, no seguinte caminho: Modelos **Administrativos\Windows Componentes\Windows Atualização\Configurar** Atualizações Automáticas         |
|A **chave do Registro AUOptions**     |Os dois valores a seguir permitem que Windows Atualização baixe e instale automaticamente atualizações de inteligência de segurança: <br/>- **4**  -  **Instalar atualizações automaticamente**. Esse valor resulta em todas as atualizações sendo instaladas automaticamente, incluindo Windows Defender de inteligência de segurança. <br/>- **3**  -  **Baixe atualizações, mas deixe-me escolher se deve instalá-las.**  Esse valor permite Windows Defender baixar e instalar atualizações de inteligência de segurança automaticamente, mas outras atualizações não são instaladas automaticamente.         |

Para garantir que a proteção contra malware seja mantida, recomendamos que você habilita os seguintes serviços:

- Relatório de Erros do Windows serviço

- Windows Atualizar serviço

A tabela a seguir lista os serviços para Microsoft Defender Antivírus e os serviços dependentes.

|Nome do Serviço|Local do arquivo|Descrição|
|--------|---------|--------|
|Windows Defender Serviço (WinDefend)|`C:\Program Files\Windows Defender\MsMpEng.exe`|Esse é o serviço Microsoft Defender Antivírus principal que precisa estar em execução o tempo todo.|
|Relatório de Erros do Windows Serviço (Wersvc)|`C:\WINDOWS\System32\svchost.exe -k WerSvcGroup`|Este serviço envia relatórios de erro de volta para a Microsoft.|
|Windows Defender Firewall (MpsSvc)|`C:\WINDOWS\system32\svchost.exe -k LocalServiceNoNetwork`|Recomendamos deixar o serviço Windows Defender Firewall habilitado.|
|Windows Atualização (Wuauserv)|`C:\WINDOWS\system32\svchost.exe -k netsvcs`|Windows A atualização é necessária para obter atualizações de inteligência de segurança e atualizações do mecanismo antimalware|

## <a name="submit-samples"></a>Enviar amostras

O envio de exemplo permite que a Microsoft colete amostras de software potencialmente mal-intencionado. Para ajudar a fornecer proteção contínua e atualizada, os pesquisadores da Microsoft usam esses exemplos para analisar atividades suspeitas e produzir inteligência de segurança antimalware atualizada. Coletamos arquivos executáveis do programa, como arquivos .exe arquivos .dll arquivos. Não coletamos arquivos que contêm dados pessoais, como Microsoft Word documentos e arquivos PDF.

### <a name="submit-a-file"></a>Enviar um arquivo

1. Revise o [guia de envio](/windows/security/threat-protection/intelligence/submission-guide).

2. Visite o [portal de envio de exemplo](https://www.microsoft.com/wdsi/filesubmission)e envie seu arquivo.


### <a name="enable-automatic-sample-submission"></a>Habilitar envio automático de exemplo

Para habilitar o envio automático de exemplo, inicie um console Windows PowerShell como administrador e desmarcar os dados de valor **SubmitSamplesConsent** de acordo com uma das seguintes configurações:

|Configuração  |Descrição  |
|---------|---------|
|**0**  -  **Sempre prompt**     |O Microsoft Defender Antivírus solicita que você confirme o envio de todos os arquivos necessários. Essa é a configuração padrão para Microsoft Defender Antivírus, mas não é recomendada para instalações em Windows Server 2016 ou 2019 sem uma GUI.         |
|**1**   -  **Enviar amostras seguras automaticamente**     |O Microsoft Defender Antivírus envia todos os arquivos marcados como "seguros" e solicita o restante dos arquivos.         |
|**2**  -  **Nunca enviar**      |O Microsoft Defender Antivírus serviço não solicita e não envia arquivos.         |
|**3**  -  **Enviar todos os exemplos automaticamente**     |O Microsoft Defender Antivírus envia todos os arquivos sem um prompt para confirmação.         |

## <a name="configure-automatic-exclusions"></a>Configurar exclusões automáticas

Para ajudar a garantir a segurança e o desempenho, determinadas exclusões são adicionadas automaticamente com base nas funções e recursos que você instala ao usar o Microsoft Defender Antivírus no Windows Server 2016 ou 2019.

Consulte [Configure exclusions in Microsoft Defender Antivírus on Windows Server](configure-server-exclusions-microsoft-defender-antivirus.md). 

## <a name="need-to-set-microsoft-defender-antivirus-to-passive-mode"></a>Precisa definir Microsoft Defender Antivírus modo passivo?

Se você estiver usando um produto antivírus que não seja da Microsoft como sua solução antivírus principal no Windows Server, você deve definir Microsoft Defender Antivírus modo passivo ou desabilitado.

- No Windows Server, versão 1803 ou mais recente ou Windows Server 2019, você pode definir Microsoft Defender Antivírus modo passivo.  

- No Windows Server 2016, Microsoft Defender Antivírus não é suportado juntamente com um produto antivírus/antimalware que não seja da Microsoft. Nesses casos, você deve definir Microsoft Defender Antivírus modo desabilitado.

### <a name="set-microsoft-defender-antivirus-to-passive-mode-using-powershell"></a>Definir Microsoft Defender Antivírus modo passivo usando o PowerShell

Se você estiver usando o Windows Server, versão 1803 ou Windows Server 2019, poderá definir o Microsoft Defender Antivírus para o modo passivo usando o seguinte cmdlet do PowerShell:

`CMDLET NEEDED`

### <a name="set-microsoft-defender-antivirus-to-passive-mode-using-group-policy"></a>Definir Microsoft Defender Antivírus modo passivo usando a Política de Grupo

PROCEDIMENTO NECESSÁRIO

### <a name="set-microsoft-defender-antivirus-to-passive-mode-using-a-registry-key"></a>Definir Microsoft Defender Antivírus modo passivo usando uma chave do Registro

Se você estiver usando o Windows Server, versão 1803 ou Windows Server 2019, poderá definir o Microsoft Defender Antivírus para o modo passivo definindo a seguinte chave do Registro:
- Caminho: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`
- Nome: `ForceDefenderPassiveMode`
- Digite: `REG_DWORD`
- Valor: `1`

### <a name="disable-microsoft-defender-antivirus-using-the-remove-roles-and-features-wizard"></a>Desabilitar Microsoft Defender Antivírus usando o assistente Remover Funções e Recursos

1. Consulte [Install or Uninstall Roles, Role Services, or Features](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#remove-roles-role-services-and-features-by-using-the-remove-roles-and-features-wizard), and use the Remove Roles and Features **Wizard**. 

2. Quando você chegar à etapa **Recursos** do assistente, des limpar a opção Windows Defender **Recursos.** 

    Se você limpar **Windows Defender** por conta própria na seção recursos Windows Defender, será solicitado a remover **a** **GUI** de opção de interface para Windows Defender . 
    
    Microsoft Defender Antivírus funcionará normalmente sem a interface do usuário, mas a interface do usuário não poderá ser habilitada se você desabilitar o recurso **Windows Defender** principal.

### <a name="turn-off-the-microsoft-defender-antivirus-user-interface-using-powershell"></a>Desativar a interface do Microsoft Defender Antivírus usando o PowerShell

Para desativar a GUI Microsoft Defender Antivírus, use o seguinte cmdlet do PowerShell:

```PowerShell
Uninstall-WindowsFeature -Name Windows-Defender-GUI
```

### <a name="are-you-using-windows-server-2016"></a>Você está usando Windows Server 2016?

Se você estiver usando Windows Server 2016 e um produto antimalware/antivírus de terceiros que não seja oferecido ou desenvolvido pela Microsoft, você precisará desabilitar/desinstalar Microsoft Defender Antivírus. 

> [!NOTE]
> Você não pode desinstalar o aplicativo Segurança do Windows, mas pode desabilitar a interface com essas instruções.

O seguinte cmdlet do PowerShell desinstala Microsoft Defender Antivírus no Windows Server 2016:

```PowerShell
Uninstall-WindowsFeature -Name Windows-Defender
```

Para desabilitar Microsoft Defender Antivírus no Windows Server 2016, use o seguinte cmdlet do PowerShell:

```PowerShell
Set-MpPreference -DisableRealtimeMonitoring $true
```

## <a name="see-also"></a>Confira também

- [Microsoft Defender Antivírus no Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Microsoft Defender Antivírus compatibilidade](microsoft-defender-antivirus-compatibility.md)
