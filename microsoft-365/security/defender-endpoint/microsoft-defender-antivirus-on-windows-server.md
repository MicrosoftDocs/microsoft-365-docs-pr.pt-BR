---
title: Microsoft Defender Antivírus no Windows Server
description: Saiba como habilitar e configurar o Microsoft Defender Antivírus no Windows Server 2016 e no Windows Server 2019.
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
ms.openlocfilehash: d9452b6d2eeaad3880894b9ec66c8bc71797b429
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764598"
---
# <a name="microsoft-defender-antivirus-on-windows-server"></a>Microsoft Defender Antivírus no Windows Server

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)

O Microsoft Defender Antivírus está disponível nas seguintes edições/versões do Windows Server:
- Windows Server 2019
- Windows Server, versão 1803 ou posterior
- Windows Server 2016. 

Em algumas instâncias, o Microsoft Defender Antivírus é conhecido como *Proteção do Ponto de Extremidade;* no entanto, o mecanismo de proteção é o mesmo. Embora a funcionalidade, a configuração e o gerenciamento sejam amplamente os mesmos para o Microsoft Defender Antivírus no [Windows 10,](microsoft-defender-antivirus-in-windows-10.md)há algumas diferenças importantes no Windows Server:

- No Windows Server, [as exclusões automáticas](configure-server-exclusions-microsoft-defender-antivirus.md) são aplicadas com base na função de servidor definida.
- No Windows Server, o Microsoft Defender Antivírus não se desabilita automaticamente se você estiver executando outro produto antivírus.

## <a name="the-process-at-a-glance"></a>O processo em um relance

O processo de configuração e execução do Microsoft Defender Antivírus em uma plataforma de servidor inclui várias etapas:

1. [Habilitar a interface](#enable-the-user-interface-on-windows-server).
2. [Instalar o Microsoft Defender Antivírus](#install-microsoft-defender-antivirus-on-windows-server).
3. [Verifique se o Microsoft Defender Antivírus está em execução.](#verify-microsoft-defender-antivirus-is-running)
4. [Atualize sua inteligência de segurança antimalware.](#update-antimalware-security-intelligence)
5. (Conforme necessário) [Enviar amostras](#submit-samples).
6. (Conforme necessário) [Configurar exclusões automáticas](#configure-automatic-exclusions).
7. (Somente se necessário) [De definir o Microsoft Defender Antivírus para o modo passivo](#need-to-set-microsoft-defender-antivirus-to-passive-mode).

## <a name="enable-the-user-interface-on-windows-server"></a>Habilitar a interface do usuário no Windows Server

Por padrão, o Microsoft Defender Antivírus é instalado e funcional no Windows Server. A interface do usuário (GUI) é instalada por padrão em alguns SKUs, mas não é necessária porque você pode usar o PowerShell ou outros métodos para gerenciar o Microsoft Defender Antivírus. Se a GUI não estiver instalada em seu servidor, você poderá adicioná-la usando o assistente **Adicionar Funções** e Recursos ou usando cmdlets do PowerShell.

### <a name="turn-on-the-gui-using-the-add-roles-and-features-wizard"></a>Ativar a GUI usando o Assistente de Adicionar Funções e Recursos

1. Consulte [Install roles, role services, and features by using the add Roles and Features Wizard](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard), and use the Add Roles and Features **Wizard**.

2. Quando você chegar à etapa **Recursos** do assistente, em Windows Defender **Recursos,** selecione a **opção GUI para** Windows Defender.

   No Windows Server 2016, o **Assistente para** Adicionar Funções e Recursos tem esta aparência:

   ![Adicionar funções e assistente de recurso mostrando a gui para Windows Defender opção](images/server-add-gui.png)

   No Windows Server 2019, o **Assistente para Adicionar Funções** e Recursos é semelhante.

### <a name="turn-on-the-gui-using-powershell"></a>Ativar a GUI usando o PowerShell

O seguinte cmdlet do PowerShell habilita a interface: 

```PowerShell
Install-WindowsFeature -Name Windows-Defender-GUI
```

## <a name="install-microsoft-defender-antivirus-on-windows-server"></a>Instalar o Microsoft Defender Antivírus no Windows Server

Você pode usar o Assistente para Adicionar **Funções e Recursos** ou o PowerShell para instalar o Microsoft Defender Antivírus.

### <a name="use-the-add-roles-and-features-wizard"></a>Usar o Assistente adicionar funções e recursos

1. Consulte este [artigo](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard)e use o **Assistente para Adicionar Funções e Recursos.**

2. Quando você chegar à etapa **Recursos** do assistente, selecione a opção Microsoft Defender Antivírus. Selecione também a **gui para Windows Defender** opção.

### <a name="use-powershell"></a>Usar o Windows PowerShell!

Para usar o PowerShell para instalar o Microsoft Defender Antivírus, execute o seguinte cmdlet:

```PowerShell
Install-WindowsFeature -Name Windows-Defender
```

As mensagens de evento para o mecanismo antimalware incluído no Microsoft Defender Antivírus podem ser encontradas em [Eventos av do Microsoft Defender.](troubleshoot-microsoft-defender-antivirus.md)


## <a name="verify-microsoft-defender-antivirus-is-running"></a>Verificar se o Microsoft Defender Antivírus está em execução

Para verificar se o Microsoft Defender Antivírus está em execução no seu servidor, execute o seguinte cmdlet do PowerShell:

```PowerShell
Get-Service -Name windefend
```

Para verificar se a proteção de firewall está ativado, execute o seguinte cmdlet do PowerShell:

```PowerShell 
Get-Service -Name mpssvc
```

Como alternativa ao PowerShell, você pode usar o Prompt de Comando para verificar se o Microsoft Defender Antivírus está em execução. Para fazer isso, execute o seguinte comando de um prompt de comando: 

```console
sc query Windefend
```

O `sc query` comando retorna informações sobre o serviço Microsoft Defender Antivírus. Quando o Microsoft Defender Antivírus está em execução, `STATE` o valor é exibido `RUNNING` .

## <a name="update-antimalware-security-intelligence"></a>Atualizar inteligência de segurança antimalware 

Para obter a inteligência de segurança antimalware atualizada, você deve ter o serviço Windows Update em execução. Se você usar um serviço de gerenciamento de atualizações, como o Windows Server Update Services (WSUS), certifique-se de que as atualizações do Microsoft Defender Antivírus Security intelligence sejam aprovadas para os computadores que você gerencia.

Por padrão, o Windows Update não baixa e instala atualizações automaticamente no Windows Server 2019 ou no Windows Server 2016. Você pode alterar essa configuração usando um dos seguintes métodos:


|Método  |Descrição  |
|---------|---------|
|**Windows Update** no Painel de Controle     |- **Instalar atualizações resulta automaticamente** em todas as atualizações que estão sendo instaladas automaticamente, incluindo Windows Defender de inteligência de segurança. <br/>- **Baixe atualizações,** mas deixe-me escolher se instalá-las permite Windows Defender baixar e instalar atualizações de inteligência de segurança automaticamente, mas outras atualizações não são instaladas automaticamente.       |
|**Política de grupo**     | Você pode configurar e gerenciar o Windows Update usando as configurações disponíveis na Política de Grupo, no seguinte caminho: Modelos **Administrativos\Componentes do Windows\Windows Update\Configurar Atualizações Automáticas**         |
|A **chave do Registro AUOptions**     |Os dois valores a seguir permitem que o Windows Update baixe e instale automaticamente atualizações de inteligência de segurança: <br/>- **4**  -  **Instalar atualizações automaticamente**. Esse valor resulta em todas as atualizações sendo instaladas automaticamente, incluindo Windows Defender de inteligência de segurança. <br/>- **3**  -  **Baixe atualizações, mas deixe-me escolher se deve instalá-las.**  Esse valor permite Windows Defender baixar e instalar atualizações de inteligência de segurança automaticamente, mas outras atualizações não são instaladas automaticamente.         |

Para garantir que a proteção contra malware seja mantida, recomendamos que você habilita os seguintes serviços:

- Serviço de Relatório de Erros do Windows

- Serviço Windows Update

A tabela a seguir lista os serviços do Microsoft Defender Antivírus e os serviços dependentes.

|Nome do Serviço|Local do arquivo|Descrição|
|--------|---------|--------|
|Windows Defender Service (WinDefend)|`C:\Program Files\Windows Defender\MsMpEng.exe`|Este é o principal serviço do Microsoft Defender Antivírus que precisa estar em execução o tempo todo.|
|Serviço de Relatório de Erros do Windows (Wersvc)|`C:\WINDOWS\System32\svchost.exe -k WerSvcGroup`|Este serviço envia relatórios de erro de volta para a Microsoft.|
|Windows Defender Firewall (MpsSvc)|`C:\WINDOWS\system32\svchost.exe -k LocalServiceNoNetwork`|Recomendamos deixar o serviço Windows Defender Firewall habilitado.|
|Windows Update (Wuauserv)|`C:\WINDOWS\system32\svchost.exe -k netsvcs`|O Windows Update é necessário para obter atualizações de inteligência de segurança e atualizações do mecanismo antimalware|

## <a name="submit-samples"></a>Enviar amostras

O envio de exemplo permite que a Microsoft colete amostras de software potencialmente mal-intencionado. Para ajudar a fornecer proteção contínua e atualizada, os pesquisadores da Microsoft usam esses exemplos para analisar atividades suspeitas e produzir inteligência de segurança antimalware atualizada. Coletamos arquivos executáveis do programa, como arquivos .exe e arquivos .dll. Não coletamos arquivos que contêm dados pessoais, como documentos do Microsoft Word e arquivos PDF.

### <a name="submit-a-file"></a>Enviar um arquivo

1. Revise o [guia de envio](/windows/security/threat-protection/intelligence/submission-guide).

2. Visite o [portal de envio de exemplo](https://www.microsoft.com/wdsi/filesubmission)e envie seu arquivo.


### <a name="enable-automatic-sample-submission"></a>Habilitar envio automático de exemplo

Para habilitar o envio automático de exemplo, inicie um console Windows PowerShell como administrador e desmarcar os dados de valor **SubmitSamplesConsent** de acordo com uma das seguintes configurações:

|Setting  |Descrição  |
|---------|---------|
|**0**  -  **Sempre prompt**     |O serviço Microsoft Defender Antivírus solicita que você confirme o envio de todos os arquivos necessários. Essa é a configuração padrão para o Microsoft Defender Antivírus, mas não é recomendada para instalações no Windows Server 2016 ou 2019 sem uma GUI.         |
|**1**   -  **Enviar amostras seguras automaticamente**     |O serviço Microsoft Defender Antivírus envia todos os arquivos marcados como "seguros" e solicita o restante dos arquivos.         |
|**2**  -  **Nunca enviar**      |O serviço Microsoft Defender Antivírus não solicita e não envia arquivos.         |
|**3**  -  **Enviar todos os exemplos automaticamente**     |O serviço Microsoft Defender Antivírus envia todos os arquivos sem um prompt para confirmação.         |

## <a name="configure-automatic-exclusions"></a>Configurar exclusões automáticas

Para ajudar a garantir a segurança e o desempenho, determinadas exclusões são adicionadas automaticamente com base nas funções e recursos que você instala ao usar o Microsoft Defender Antivírus no Windows Server 2016 ou 2019.

Consulte [Configurar exclusões no Microsoft Defender Antivírus no Windows Server](configure-server-exclusions-microsoft-defender-antivirus.md). 

## <a name="need-to-set-microsoft-defender-antivirus-to-passive-mode"></a>Precisa definir o Microsoft Defender Antivírus como modo passivo?

Se você estiver usando um produto antivírus que não seja da Microsoft como sua solução antivírus principal, de definir o Microsoft Defender Antivírus como modo passivo.  

### <a name="set-microsoft-defender-antivirus-to-passive-mode-using-a-registry-key"></a>Definir o Microsoft Defender Antivírus como modo passivo usando uma chave do Registro

Se você estiver usando o Windows Server, versão 1803 ou Windows Server 2019, poderá definir o Microsoft Defender Antivírus como modo passivo definindo a seguinte chave do Registro:
- Caminho: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`
- Nome: `ForcePassiveMode`
- Digite: `REG_DWORD`
- Valor: `1`

### <a name="disable-microsoft-defender-antivirus-using-the-remove-roles-and-features-wizard"></a>Desabilitar o Microsoft Defender Antivírus usando o assistente Remover Funções e Recursos

1. Consulte [Install or Uninstall Roles, Role Services, or Features](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#remove-roles-role-services-and-features-by-using-the-remove-roles-and-features-wizard), and use the Remove Roles and Features **Wizard**. 

2. Quando você chegar à etapa **Recursos** do assistente, des limpar a opção Windows Defender **Recursos.** 

    Se você limpar **Windows Defender** por conta própria na seção recursos do **Windows Defender,** será solicitado a remover a **GUI** de opção de interface para Windows Defender . 
    
    O Microsoft Defender Antivírus ainda será executado normalmente sem a interface do usuário, mas a interface do usuário não poderá ser habilitada se você desabilitar o recurso **Windows Defender** principal.

### <a name="turn-off-the-microsoft-defender-antivirus-user-interface-using-powershell"></a>Desativar a interface do usuário do Microsoft Defender Antivírus usando o PowerShell

Para desativar a GUI do Microsoft Defender Antivírus, use o seguinte cmdlet do PowerShell:

```PowerShell
Uninstall-WindowsFeature -Name Windows-Defender-GUI
```

### <a name="are-you-using-windows-server-2016"></a>Você está usando o Windows Server 2016?

Se você estiver usando o Windows Server 2016 e um produto antimalware/antivírus de terceiros que não é oferecido ou desenvolvido pela Microsoft, você precisará desabilitar/desinstalar o Microsoft Defender Antivírus. 

> [!NOTE]
> Não é possível desinstalar o aplicativo segurança do Windows, mas é possível desabilitar a interface com essas instruções.

O seguinte cmdlet do PowerShell desinstala o Microsoft Defender Antivírus no Windows Server 2016:

```PowerShell
Uninstall-WindowsFeature -Name Windows-Defender
```

## <a name="see-also"></a>Confira também

- [Microsoft Defender Antivírus no Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Compatibilidade com o Microsoft Defender Antivírus](microsoft-defender-antivirus-compatibility.md)