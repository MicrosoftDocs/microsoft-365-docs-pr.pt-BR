---
title: Obter detalhes sobre dispositivos gerenciados básicos de mobilidade e segurança
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: Use o Windows PowerShell para obter detalhes sobre dispositivos básicos de mobilidade e segurança em sua organização.
ms.openlocfilehash: 7c6a0365dfd573377c3675bbcee8ee8280e33816
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876883"
---
# <a name="get-details-about-basic-mobility-and-security-managed-devices"></a>Obter detalhes sobre dispositivos gerenciados básicos de mobilidade e segurança

Este artigo mostra como usar o Windows PowerShell para obter detalhes sobre os dispositivos em sua organização que você configura para Mobilidade Básica e Segurança.

Veja um detalhamento dos detalhes do dispositivo disponíveis para você.

|**Ver os detalhes**|**O que procurar no PowerShell**|
|:----------------|:------------------------------------------------------------------------------|
|O dispositivo está inscrito no Basic Mobility and Security. Para obter mais informações, consulte [Registrar seu dispositivo móvel usando Mobilidade Básica e Segurança](enroll-your-mobile-device.md)|O valor do *parâmetro isManaged*   é:<br/>**True**= o dispositivo está inscrito.<br/>**False**= o dispositivo não está inscrito. |
|O dispositivo é compatível com as políticas de segurança do dispositivo. Para obter mais informações, consulte [Criar políticas de segurança do dispositivo](create-device-security-policies.md)|O valor do parâmetro *isCompliant*   é:<br/>**True**   = o dispositivo é compatível com políticas.<br/>**False**   = o dispositivo não está em conformidade com políticas.|

:::image type="content" source="../../media/basic-mobility-security/bms-7-powershell-parameters.png" alt-text="Parâmetros básicos de Mobilidade e Segurança do PowerShell":::

>[!NOTE]
>Os comandos e scripts neste artigo também retornam detalhes sobre todos os dispositivos gerenciados pelo [Microsoft Intune.](https://www.microsoft.com/cloud-platform/microsoft-intune)

## <a name="before-you-begin"></a>Antes de começar

Há algumas coisas que você precisa configurar para executar os comandos e scripts descritos neste artigo.

### <a name="step-1-download-and-install-the-azure-active-directory-module-for-windows-powershell"></a>Etapa 1: Baixar e instalar o Módulo Azure Active Directory para Windows PowerShell

Para saber mais sobre essas etapas, confira [Conectar-se ao Microsoft 365 com o PowerShell.](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell)

1. Vá para o Assistente de Sign-In Microsoft Online Services para Profissionais de [TI RTWl](https://www.microsoft.com/download/details.aspx?id=41950)e selecione Download para o Assistente de Login do   Microsoft Online  **Services.**   

2. Instale o Módulo Microsoft Azure Active Directory para Windows PowerShell seguindo estas etapas:

    1. Abra um prompt de comando do PowerShell do nível de administrador.  

    2. Execute o comando Install-Module MSOnline.

    3. Se solicitado a instalar o provedor de NuGet, digite Y e pressione Enter.

    4. Se solicitado a instalar o módulo de PSGallery, digite Y e pressione Enter.

    5. Após a instalação, feche a janela de comando do PowerShell.

### <a name="step-2-connect-to-your-microsoft-365-subscription"></a>Etapa 2: Conectar-se à sua assinatura do Microsoft 365

1. No Módulo Windows Azure Active Directory para Windows PowerShell, execute o seguinte comando.  

    $UserCredential = Get-Credential

2. Na caixa de diálogo Solicitação de Credencial do Windows PowerShell, digite o nome de usuário e a senha da sua conta de administrador global do Microsoft 365 e selecione **OK.**

3. Execute o seguinte comando.

    Connect-MsolService -Credential $UserCredential

### <a name="step-3-make-sure-youre-able-to-run-powershell-scripts"></a>Etapa 3: Certifique-se de poder executar scripts do PowerShell

>[!NOTE]
>Você pode ignorar esta etapa se já estiver pronto para executar scripts do PowerShell.

Para executar o Get-MsolUserDeviceComplianceStatus.ps1 script, você precisa habilitar a execução de scripts do PowerShell.

1. Na área de trabalho do Windows, **selecione Iniciar** e digite Windows PowerShell. Clique com o botão direito do mouse no Windows PowerShell e selecione **Executar como administrador.**

2. Execute o seguinte comando.

    Set-ExecutionPolicy RemoteSigned

3. Quando solicitado, digite S e pressione Enter.

**Execute o Get-MsolDevice cmdlet para exibir detalhes de todos os dispositivos em sua organização**

1. Abra o Módulo Microsoft Azure Active Directory para Windows PowerShell.  

2. Execute o seguinte comando.

    Get-MsolDevice -All -ReturnRegisteredOwners | Where-Object {$_. RegisteredOwners.Count -gt 0}

Para obter mais exemplos,  [consulte Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=841721).

## <a name="run-a-script-to-get-device-details"></a>Executar um script para obter detalhes do dispositivo

Primeiro, salve o script no computador.

1. Copie e colar o texto a seguir no Bloco de Notas.  

2.  param (

3.  [PSObject[]]$users = @(),

4.  [Switch]$export,

5.  [String]$exportFileName = "UserDeviceComplianceStatus_" + (Get-Date -Format "yyMMdd_HHMMss") + ".csv",

6.  [String]$exportPath = [Environment]::GetFolderPath("Desktop")

7.  )

9.  [System.Collections.IDictionary]$script:schema = @{

11.  DeviceId = ''

12.  DeviceOSType = ''

13.  DeviceOSVersion = ''

14.  DeviceTrustLevel = ''

15.  DisplayName = ''

16.  IsCompliant = ''

17.  IsManaged = ''

18.  ApproximateLastLogonTimestamp = ''

19.  DeviceObjectId = ''

20.  RegisteredOwnerUpn = ''

21.  RegisteredOwnerObjectId = ''
    

22.  RegisteredOwnerDisplayName = ''
    

23.  }
    

25.  function createResultObject
    

26.  {
    

28.  [PSObject]$resultObject = New-Object -TypeName PSObject -Property $script:schema
    

30.  retornar $resultObject
    

31.  }
    

33.  If ($users. Count -eq 0)
    

34.  {
    

35.  $users = Get-MsolUser
    

36.  }
    

38.  [PSObject[]]$result = foreach ($u in $users)
    

39.  {
    

41.  [PSObject]$devices = get-msoldevice -RegisteredOwnerUpn $u.UserPrincipalName
    

42.  foreach ($d in $devices)
    

43.  {
    

44.  [PSObject]$deviceResult = createResultObject
    

45.  $deviceResult.DeviceId = $d.DeviceId
    

46.  $deviceResult.DeviceOSType = $d.DeviceOSType
    

47.  $deviceResult.DeviceOSVersion = $d.DeviceOSVersion
    

48.  $deviceResult.DeviceTrustLevel = $d.DeviceTrustLevel
    

49.  $deviceResult.DisplayName = $d.DisplayName
    

50.  $deviceResult.IsCompliant = $d.GraphDeviceObject.IsCompliant
    

51.  $deviceResult.IsManaged = $d.GraphDeviceObject.IsManaged
    

52.  $deviceResult.DeviceObjectId = $d.ObjectId
    

53.  $deviceResult.RegisteredOwnerUpn = $u.UserPrincipalName
    

54.  $deviceResult.RegisteredOwnerObjectId = $u.ObjectId
    

55.  $deviceResult.RegisteredOwnerDisplayName = $u.DisplayName
    

56.  $deviceResult.ApproximateLastLogonTimestamp = $d.ApproximateLastLogonTimestamp
    

58.  $deviceResult
    

59.  }
    

61.  }
    

63.  If ($export)
    

64.  {
    

65.  $result | Export-Csv -path ($exportPath + " \" + $exportFileName) -NoTypeInformation
    

66.  }
    

67.  Else
    

68.  {
    

69.  $result
    

70.  }
    

71.  Salve-o como um arquivo de script do Windows PowerShell usando a extensão de arquivo .ps1; por exemplo, Get-MsolUserDeviceComplianceStatus.ps1.   

## <a name="run-the-script-to-get-device-information-for-a-single-user-account"></a>Executar o script para obter informações de dispositivo para uma única conta de usuário

1. Abra o Módulo Microsoft Azure Active Directory para Windows PowerShell.
    
2. Vá para a pasta onde você salvou o script. Por exemplo, se você salvou em C:\PS-Scripts, execute o seguinte comando.
    
    cd C:\PS-Scripts

3. Execute o seguinte comando para identificar o usuário para o qual você deseja obter detalhes do dispositivo. Este exemplo obtém detalhes sobre bar@example.com.
    
    $u = Get-MsolUser -UserPrincipalName bar@example.com

4. Execute o seguinte comando para iniciar o script.

    .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export

As informações são exportadas para a área de trabalho do Windows como um arquivo CSV. Você pode usar parâmetros adicionais para especificar o nome do arquivo e o caminho do CSV.

## <a name="run-the-script-to-get-device-information-for-a-group-of-users"></a>Executar o script para obter informações de dispositivo para um grupo de usuários

1. Abra o Módulo Microsoft Azure Active Directory para Windows PowerShell.
    
2. Vá para a pasta onde você salvou o script. Por exemplo, se você salvou em C:\PS-Scripts, execute o seguinte comando.   

    cd C:\PS-Scripts

3. Execute o seguinte comando para identificar o grupo para o qual você deseja obter detalhes do dispositivo. Este exemplo obtém detalhes para usuários no grupo FinanceStaff. 

    $u = Get-MsolGroupMember -SearchString "FinanceStaff" | % { Get-MsolUser -ObjectId $_. ObjectId }

4. Execute o seguinte comando para iniciar o script.   

    .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export

As informações são exportadas para a área de trabalho do Windows como um arquivo CSV. Você pode usar parâmetros adicionais para especificar o nome do arquivo e o caminho do CSV.

## <a name="related-topics"></a>Tópicos relacionados

[O Microsoft Connect foi retirado](https://docs.microsoft.com/collaborate/connect-redirect)

[Visão geral da Mobilidade e Segurança Básicas](overview.md)

[Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=841721)