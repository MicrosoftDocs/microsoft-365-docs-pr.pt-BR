---
title: Conecte-se ao Microsoft 365 com o PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- LIL_Placement
- O365ITProTrain
- Ent_Office_Other
ms.assetid: 5ebc0e21-b72d-46d8-96fa-00643b18eaec
description: Conecte-se ao seu locatário do Microsoft 365 usando o Windows PowerShell para Microsoft 365 para fazer as tarefas do centro de administração a partir da linha de comando.
ms.openlocfilehash: 6b8f98441c7d727984bde8775dea496a9324d50c
ms.sourcegitcommit: 4d26a57c37ff7efbb8d235452c78498b06a59714
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/22/2021
ms.locfileid: "53053054"
---
# <a name="connect-to-microsoft-365-with-powershell"></a>Conecte-se ao Microsoft 365 com o PowerShell

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

O Windows PowerShell para Microsoft 365 permite que você gerencie suas configurações do Microsoft 365 a partir da linha de comando. Para se conectar ao Windows PowerShell, basta instalar o software necessário e conectar-se à sua organização Microsoft 365.

Existem duas versões do módulo Windows PowerShell que você pode usar para se conectar ao Microsoft 365 e administrar contas de usuário, grupos e licenças:

- O Azure Active Directory Windows PowerShell para Microsoft Graph, cujo nome dos cmdlets inclui *AzureAD*
- O Módulo Microsoft Azure Active Directory para Windows PowerShell, cujo nome dos cmdlets inclui *MSol*

Atualmente, o módulo Azure Active Directory Windows PowerShell para Microsoft Graph não substitui completamente a funcionalidade do Módulo Microsoft Azure Active Directory para Windows PowerShell para administração de usuários, grupos e licenças. Em alguns casos, você precisa usar ambas as versões. As duas versões podem ser instaladas com segurança no mesmo computador.

>[!Note]
>Você também pode se conectar com o [Azure Cloud Shell](#connect-with-the-azure-cloud-shell) do Centro de administração do Microsoft 365.
>


## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?


**Sistema operacional**

Você deve usar uma versão de 64 bits do Windows porque o suporte para a versão de 32 bits do Módulo Microsoft Azure Active Directory para Windows PowerShell foi encerrado em 2014.

Você pode usar as seguintes versões do Windows:
    
  - Windows 10, Windows 8.1, Windows 8 ou Windows 7 Service Pack 1 (SP1) 
    
  - Windows Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012, or Windows Server 2008 R2 SP1

>[!Note]
>Para Windows 8.1, Windows 8, Windows 7 Service Pack 1 (SP1), Windows Server 2012 R2, Windows Server 2012, e Windows Server 2008 R2 SP1, baixe e instale o [Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616).

**PowerShell**

- Para o módulo do Windows PowerShell do Azure Active Directory para Graph, você deve usar o Windows PowerShell versão 5.1 ou posterior.

- Para o Módulo Microsoft Azure Active Directory para Windows PowerShell, você deve usar o PowerShell versão 5.1 ou posterior, até o PowerShell versão 6. Você não pode usar o PowerShell versão 7.
       
>[!Note]
>Esses procedimentos são destinados aos usuários que são membros de uma função de administrador do Microsoft 365. Para obter mais informações, confira [Sobre funções de administrador](../admin/add-users/about-admin-roles.md).


## <a name="connect-with-the-azure-active-directory-powershell-for-graph-module"></a>Conecte-se ao Azure Active Directory PowerShell para o módulo do Graph.

Os comandos no módulo do PowerShell do Azure Active Directory para Graph têm o *AzureAD* no nome do cmdlet. Você pode instalar o módulo do [PowerShell do Azure Active Directory para Graph](/powershell/azure/active-directory/install-adv2) ou o [Azure PowerShell](/powershell/azure/install-az-ps).

Para procedimentos que exigem os novos cmdlets no módulo Azure Active Directory Windows PowerShell para Graph, siga estas etapas para instalar o módulo e conectar-se à sua assinatura do Microsoft 365.

> [!Note]
> Confira o [Azure Active Directory PowerShell para o módulo do Graph](/powershell/azure/active-directory/install-adv2) para obter mais informações sobre o suporte a diferentes versões do Microsoft Windows.

### <a name="step-1-install-the-required-software"></a>Etapa 1: instalar o software necessário

Estas etapas são necessárias apenas uma vez em seu computador. Mas provavelmente você precisará atualizar o software periodicamente.
  
1. Abra uma janela elevada do Prompt de Comando do Windows PowerShell (execute o Windows PowerShell como administrador).
    
2. Execute este comando:
    
    ```powershell
    Install-Module -Name AzureAD
    ```

  Por padrão, o PowerShell Gallery (PSGallery) não está configurado como um repositório confiável para **PowerShellGet**. Na primeira vez que usar o PSGallery, você verá a seguinte mensagem:

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

Responda **Sim** ou **Sim** para todos para continuar com a instalação.


### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a>Etapa 2: Conectar-se ao Azure AD da sua assinatura do Microsoft 365

Para se conectar ao Azure Active Directory (Azure AD) da sua assinatura do Microsoft 365 com um nome de usuário e senha, ou com a autenticação multifator (MFA), execute um destes comandos de um prompt de comando do Windows PowerShell (não é necessário ser privilegiado).

| Nuvem do Office 365 | Comando |
|:-------|:-----|
| Office 365 no Mundo (+GCC) | `Connect-AzureAD` |
| Office 365 operado pela 21 Vianet | `Connect-AzureAD -AzureEnvironmentName AzureChinaCloud` |
| Office 365 Germany | `Connect-AzureAD -AzureEnvironmentName AzureGermanyCloud` |
| Office 365 U.S. Government DoD e Office 365 U.S. Government GCC High | `Connect-AzureAD -AzureEnvironmentName AzureUSGovernment` |
|||

Na caixa de diálogo **Entrar na sua conta**, digite seu nome de usuário e senha da conta corporativa ou de estudante do Microsoft 365 e selecione **OK**.

Se você estiver usando a autenticação multifator, siga as instruções para fornecer informações adicionais de autenticação, como um código de verificação.

Depois de se conectar, você pode usar os cmdlets para o [módulo Azure Active Directory Windows PowerShell para Graph](/powershell/module/azuread).

## <a name="connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Conecte com o Módulo Microsoft Azure Active Directory para Windows PowerShell

>[!Note]
>Os cmdlets no Módulo Microsoft Azure Active Directory para Windows PowerShell têm *Msol* em seus nomes.

O PowerShell versão 7 e posterior não oferece suporte ao Módulo Microsoft Azure Active Directory para Windows PowerShell e cmdlets com *Msol* em seus nomes. Para o PowerShell versão 7 e posterior, você deve usar o módulo do PowerShell do Azure Active Directory para Graph ou o Azure PowerShell.

O PowerShell Core não oferece suporte ao Módulo Microsoft Azure Active Directory para Windows PowerShell para o módulo do Windows PowerShell e cmdlets com *Msol* em seus nomes. Execute esses cmdlets do Windows PowerShell.
    
### <a name="step-1-install-the-required-software"></a>Etapa 1: instalar o software necessário

Estas etapas são necessárias apenas uma vez em seu computador. Mas provavelmente você precisará atualizar o software periodicamente.
  
1.  Se você não estiver executando o Windows 10, instale a versão de 64 bits do Assistente de Conexão do Microsoft Online Services: [Assistente de Conexão do Microsoft Online Services para Profissionais de TI RTW](https://download.microsoft.com/download/7/1/E/71EF1D05-A42C-4A1F-8162-96494B5E615C/msoidcli_32bit.msi).
    
2. Siga estas etapas para instalar o Módulo Microsoft Azure Active Directory para Windows PowerShell:
    
   1. Abra um prompt de comando privilegiado do Windows PowerShell (execute o Windows PowerShell como administrador).
   1.  Execute o comando **Install-Module MSOnline**.
   1. Se você for solicitado a instalar o provedor NuGet, digite **S** e pressione Enter.
   1. Se você for solicitado a instalar o módulo do PSGallery, digite **S** e pressione Enter.
    
### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a>Etapa 2: Conectar-se ao Azure AD da sua assinatura do Microsoft 365

Para se conectar ao Azure AD da sua assinatura do Microsoft 365 com um nome de usuário e senha, ou com a autenticação multifator (MFA), execute um destes comandos de um prompt de comando do Windows PowerShell (não é necessário ser privilegiado).

| Nuvem do Office 365 | Comando |
|:-------|:-----|
| Office 365 no Mundo (+GCC) | `Connect-MsolService` |
| Office 365 operado pela 21 Vianet | `Connect-MsolService -AzureEnvironment AzureChinaCloud` |
| Office 365 Germany | `Connect-MsolService -AzureEnvironment AzureGermanyCloud` |
| Office 365 U.S. Government DoD e Office 365 U.S. Government GCC High | `Connect-MsolService -AzureEnvironment USGovernment` |
|||

Na caixa de diálogo **Entrar na sua conta**, digite seu nome de usuário e senha da conta corporativa ou de estudante do Microsoft 365 e selecione **OK**.

Se você estiver usando a autenticação multifator, siga as instruções para fornecer informações adicionais de autenticação, como um código de verificação.

### <a name="how-do-you-know-it-worked"></a>Como saber se funcionou?

Se você não receber uma mensagem de erro, você se conectou com êxito. Para um teste rápido, execute um cmdlet do Microsoft 365, como **Get-MsolUser**, e confira os resultados.
  
Se você receber uma mensagem de erro, cheque os seguintes problemas:
  
- **Senha incorreta é um problema comum**. Execute a [Etapa 2](#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) novamente e preste muita atenção ao nome de usuário e senha que você inserir.
    
- **O Módulo Microsoft Azure Active Directory para Windows PowerShell requer o Microsoft .NET Framework 3.5.* x* está ativado em seu computador **. É provável que seu computador tenha uma versão mais recente instalada (por exemplo, 4 ou 4.5.* x*). Mas a compatibilidade com versões anteriores do .NET Framework pode ser habilitada ou desabilitada. Para saber mais, confira os seguintes artigos:
    
  - Para Windows Server 2012 ou Windows Server 2012 R2, confira [Habilitar o .NET Framework 3.5 usando o Assistente de Adição de Funções e Recursos](/previous-versions/windows/it-pro/windows-8.1-and-8/dn482071(v=win.10)).
    
  - Para Windows 7 ou Windows Server 2008 R2, confira [Não é possível abrir o Módulo Azure Active Directory para Windows PowerShell](/troubleshoot/azure/active-directory/cant-open-aad-module-powershell).

  - Para Windows 10, Windows 8.1 e Windows 8, confira [Instalar o .NET Framework 3.5 no Windows 10, Windows 8.1 e Windows 8](/dotnet/framework/install/dotnet-35-windows-10)

  
- **Sua versão do Módulo Microsoft Azure Active Directory para Windows PowerShell pode estar desatualizada.** Para verificar, execute o seguinte comando no PowerShell para o Microsoft 365 ou no Módulo Microsoft Azure Active Directory para Windows PowerShell :
    
  ```powershell
  (Get-Item C:\Windows\System32\WindowsPowerShell\v1.0\Modules\MSOnline\Microsoft.Online.Administration.Automation.PSModule.dll).VersionInfo.FileVersion
  ```

    Se o número da versão retornado for inferior a *1.0.8070.2*, desinstale o Módulo Microsoft Azure Active Directory para Windows PowerShell e instale a partir da [Etapa 1](#step-1-install-the-required-software), acima.

- **Se você receber uma mensagem de erro de conexão**, confira [o erro "Connect-MsolService: Exceção de tipo lançada"](/office365/troubleshoot/active-directory/connect-msoservice-throw-exception).
    
- **Se você receber uma mensagem de erro "Get-Item: Não é possível encontrar o caminho"**, execute este comando:


   ```powershell
     (dir "C:\Program Files\WindowsPowerShell\Modules\MSOnline").Name
   ```

## <a name="connect-with-the-azure-cloud-shell"></a>Conecte-se com o Azure Cloud Shell

Para se conectar e usar o Azure Cloud Shell no Centro de administração do Microsoft 365, selecione o ícone da janela do PowerShell no canto superior direito da barra de tarefas. No painel **Bem-vindo ao Azure Cloud Shell**, selecione **PowerShell**.

Você precisará de uma assinatura ativa do Azure para sua organização que esteja vinculada à sua assinatura do Microsoft 365. Se você ainda não tiver, poderá criar uma. Depois que tiver uma assinatura do Azure, uma janela do PowerShell é aberta na qual você pode executar comandos e scripts do PowerShell.

Para obter mais informações, consulte [Azure Cloud Shell](/azure/cloud-shell/overview).

## <a name="see-also"></a>Confira também

- [Gerenciar o Microsoft 365 com o PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
- [Introdução ao Windows PowerShell para o Microsoft 365](getting-started-with-microsoft-365-powershell.md)
- [Conectar-se a todos os serviços do Microsoft 365 usando uma única janela do Windows PowerShell](connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window.md)
