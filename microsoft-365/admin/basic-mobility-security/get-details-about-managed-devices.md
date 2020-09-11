---
title: Obter detalhes sobre dispositivos de mobilidade e gerenciamento de segurança básicos
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
description: Use o Windows PowerShell para obter detalhes sobre dispositivos de segurança e mobilidade básicos em sua organização.
ms.openlocfilehash: d34263ee215c568834034f2735bb69d9cef9ac6d
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430067"
---
# <a name="get-details-about-basic-mobility-and-security-managed-devices"></a>Obter detalhes sobre dispositivos de mobilidade e gerenciamento de segurança básicos

Este artigo mostra como usar o Windows PowerShell para obter detalhes sobre os dispositivos em sua organização que você configurou para mobilidade básica e segurança.

Aqui está uma divisão dos detalhes do dispositivo disponíveis para você.

|**Ver os detalhes**|**O que procurar no PowerShell**|
|:----------------|:------------------------------------------------------------------------------|
|O dispositivo está inscrito em mobilidade básica e segurança. Para saber mais, confira [registrar seu dispositivo móvel usando mobilidade básica e segurança](enroll-your-mobile-device.md)|O valor do parâmetro *IsManaged*   é:<br/>**True**= o dispositivo está inscrito.<br/>**False**= o dispositivo não está inscrito. |
|O dispositivo é compatível com suas políticas de segurança de dispositivo. Para saber mais, confira [criar políticas de segurança de dispositivo](create-device-security-policies.md)|O valor do parâmetro *IsCompliant*   é:<br/>**True**   = o dispositivo é compatível com políticas.<br/>**False**   = o dispositivo não é compatível com políticas.|

:::image type="content" source="../../media/basic-mobility-security/bms-7-powershell-parameters.png" alt-text="Parâmetros básicos de mobilidade e segurança do PowerShell":::

>[!NOTE]
>Os comandos e scripts neste artigo também retornam detalhes sobre qualquer dispositivo gerenciado pelo [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune).

## <a name="before-you-begin"></a>Antes de começar

Há algumas coisas que você precisa configurar para executar os comandos e scripts descritos neste artigo.

### <a name="step-1-download-and-install-the-azure-active-directory-module-for-windows-powershell"></a>Etapa 1: baixar e instalar o módulo Azure Active Directory para Windows PowerShell

Para obter mais informações sobre essas etapas, consulte [conectar-se ao Microsoft 365 com o PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell).

1. Vá para [Assistente de conexão do Microsoft Online Services para profissionais de ti RTWl](https://www.microsoft.com/download/details.aspx?id=41950)   e selecione  **download para assistente de conexão do Microsoft Online Services**.   

2. Instale o Módulo Microsoft Azure Active Directory para Windows PowerShell seguindo estas etapas:   

    1. Abra um prompt de comando do PowerShell do nível de administrador.  

    2. Execute o comando Install-Module MSOnline.
    
    3. Se solicitado a instalar o provedor de NuGet, digite Y e pressione Enter.   

    4. Se solicitado a instalar o módulo de PSGallery, digite Y e pressione Enter.   

    5. Após a instalação, feche a janela de comando do PowerShell.
    
### <a name="step-2-connect-to-your-microsoft-365-subscription"></a>Etapa 2: conectar-se à sua assinatura do Microsoft 365

1. No módulo do Windows Azure Active Directory para Windows PowerShell, execute o seguinte comando.  

    $UserCredential = Get-Credential

2. Na caixa de diálogo solicitação de credencial do Windows PowerShell, digite o nome de usuário e a senha da sua conta de administrador global do Microsoft 365 e, em seguida, selecione **OK**.
    
3. Execute o seguinte comando.
    
    Connect-MsolService-Credential $UserCredential

### <a name="step-3-make-sure-youre-able-to-run-powershell-scripts"></a>Etapa 3: Verifique se é possível executar scripts do PowerShell

>[!NOTE]
>Você pode ignorar esta etapa se já estiver configurado para executar scripts do PowerShell.

Para executar o script Get-MsolUserDeviceComplianceStatus.ps1, você precisa habilitar a execução de scripts do PowerShell.

1. Na área de trabalho do Windows, selecione **Iniciar**e digite Windows PowerShell. Clique com o botão direito do mouse em Windows PowerShell e selecione **Executar como administrador**.

2. Execute o seguinte comando.
    
    Set-ExecutionPolicy RemoteSigned

3. Quando solicitado, digite s e pressione Enter.
    
**Execute o cmdlet Get-MsolDevice para exibir detalhes de todos os dispositivos em sua organização**

1. Abra o Módulo Microsoft Azure Active Directory para Windows PowerShell.  

2. Execute o seguinte comando.
    
    Get-MsolDevice-All-ReturnRegisteredOwners | Em que-Object {$ _. RegisteredOwners. Count-gt 0}

Para obter mais exemplos, consulte  [Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=841721).

## <a name="run-a-script-to-get-device-details"></a>Executar um script para obter detalhes do dispositivo

Primeiro, salve o script no seu computador.

1. Copie e cole o texto a seguir no bloco de notas.  

2.  parâmetros
    

3.  [PSObject []] $users = @ (),
    

4.  [Opção] $export,
    

5.  [Cadeia de caracteres] $exportFileName = "UserDeviceComplianceStatus_" + (Get-Date-Format "yyMMdd_HHMMss") + ". csv",
    

6.  [Cadeia de caracteres] $exportPath = [ambiente]:: GetFolderPath ("área de trabalho")
    

7.  )
    

9.  [System. Collections. IDictionary] $script: Schema = @ {
    

11.  DeviceID = ' '
    

12.  DeviceOSType = ' '
    

13.  DeviceOSVersion = ' '
    

14.  DeviceTrustLevel = ' '
    

15.  DisplayName = ' '
    

16.  IsCompliant = ' '
    

17.  IsManaged = ' '
    

18.  ApproximateLastLogonTimestamp = ' '
    

19.  DeviceObjectId = ' '
    

20.  RegisteredOwnerUpn = ' '
    

21.  RegisteredOwnerObjectId = ' '
    

22.  RegisteredOwnerDisplayName = ' '
    

23.  }
    

25.  função createresultobject
    

26.  {
    

28.  [PSObject] $resultObject = New-Object-TypeName PSObject-Property $script: Schema
    

30.  retornar $resultObject
    

31.  }
    

33.  If ($users. Count-eq 0)
    

34.  {
    

35.  $users = Get-MsolUser
    

36.  }
    

38.  [PSObject []] $result = foreach ($u em $users)
    

39.  {
    

41.  [PSObject] $devices = Get-msoldevice-RegisteredOwnerUpn $u. UserPrincipalName
    

42.  foreach ($d em $devices)
    

43.  {
    

44.  [PSObject] $deviceResult = createresultobject
    

45.  $deviceResult. DeviceID = $d. DeviceID
    

46.  $deviceResult. DeviceOSType = $d. DeviceOSType
    

47.  $deviceResult. DeviceOSVersion = $d. DeviceOSVersion
    

48.  $deviceResult. DeviceTrustLevel = $d. DeviceTrustLevel
    

49.  $deviceResult. DisplayName = $d. DisplayName
    

50.  $deviceResult. IsCompliant = $d. GraphDeviceObject. IsCompliant
    

51.  $deviceResult. isgerencied = $d. GraphDeviceObject. isgerencied
    

52.  $deviceResult. DeviceObjectId = $d. ObjectId
    

53.  $deviceResult. RegisteredOwnerUpn = $u. UserPrincipalName
    

54.  $deviceResult. RegisteredOwnerObjectId = $u. ObjectId
    

55.  $deviceResult. RegisteredOwnerDisplayName = $u. DisplayName
    

56.  $deviceResult. ApproximateLastLogonTimestamp = $d. ApproximateLastLogonTimestamp
    

58.  $deviceResult
    

59.  }
    

61.  }
    

63.  If ($export)
    

64.  {
    

65.  $result | Export-CSV-Path ($exportPath + " \" + $exportFileName)-NoTypeInformation
    

66.  }
    

67.  Else
    

68.  {
    

69.  $result
    

70.  }
    

71.  Salve-o como um arquivo de script do Windows PowerShell usando a extensão de arquivo. ps1; por exemplo, Get-MsolUserDeviceComplianceStatus.ps1.   

## <a name="run-the-script-to-get-device-information-for-a-single-user-account"></a>Executar o script para obter informações de dispositivo para uma única conta de usuário

1. Abra o Módulo Microsoft Azure Active Directory para Windows PowerShell.
    
2. Vá para a pasta onde você salvou o script. Por exemplo, se você salvou-o no C:\PS-Scripts, execute o seguinte comando.
    
    CD C:\PS-Scripts

3. Execute o seguinte comando para identificar o usuário para o qual você deseja obter detalhes de dispositivo. Este exemplo obtém detalhes de bar@example.com.
    
    $u = get-MsolUser-UserPrincipalName bar@example.com

4. Execute o seguinte comando para iniciar o script.

    .\Get-MsolUserDeviceComplianceStatus.ps1-user $u-Export

As informações são exportadas para a área de trabalho do Windows como um arquivo CSV. Você pode usar parâmetros adicionais para especificar o nome do arquivo e o caminho do CSV.

## <a name="run-the-script-to-get-device-information-for-a-group-of-users"></a>Executar o script para obter informações de dispositivo para um grupo de usuários

1. Abra o Módulo Microsoft Azure Active Directory para Windows PowerShell.
    
2. Vá para a pasta onde você salvou o script. Por exemplo, se você salvou-o no C:\PS-Scripts, execute o seguinte comando.   

    CD C:\PS-Scripts

3. Execute o seguinte comando para identificar o grupo para o qual você deseja obter detalhes de dispositivo. Este exemplo obtém detalhes para usuários no grupo FinanceStaff. 

    $u = get-MsolGroupMember-searchString "FinanceStaff" | % {Get-MsolUser-ObjectId $ _. IDs

4. Execute o seguinte comando para iniciar o script.   

    .\Get-MsolUserDeviceComplianceStatus.ps1-user $u-Export

As informações são exportadas para a área de trabalho do Windows como um arquivo CSV. Você pode usar parâmetros adicionais para especificar o nome do arquivo e o caminho do CSV.

## <a name="related-topics"></a>Tópicos relacionados

[O Microsoft Connect foi desativado](https://docs.microsoft.com/collaborate/connect-redirect)

[Visão geral da mobilidade básica e segurança](overview.md)

[Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=841721)