---
title: Obter detalhes sobre dispositivos gerenciados de Mobilidade Básica e Segurança
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
description: Use Windows PowerShell para obter detalhes sobre dispositivos Básicos de Mobilidade e Segurança em sua organização.
ms.openlocfilehash: 2edee1b08f137d3e4f977b4d6800c1b0fc0e0473
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228166"
---
# <a name="get-details-about-basic-mobility-and-security-managed-devices"></a>Obter detalhes sobre dispositivos gerenciados de Mobilidade Básica e Segurança

Este artigo mostra como usar o Windows PowerShell para obter detalhes sobre os dispositivos em sua organização que você definiu para Mobilidade Básica e Segurança.

Aqui está uma análise dos detalhes do dispositivo disponíveis para você.

|**Ver os detalhes**|**O que procurar no PowerShell**|
|:----------------|:------------------------------------------------------------------------------|
|O dispositivo está inscrito no Basic Mobility and Security. Para obter mais informações, consulte [Registrar seu dispositivo móvel usando o Basic Mobility and Security](enroll-your-mobile-device.md)|O valor do parâmetro *isManaged*   é:<br/>**True**= dispositivo está inscrito.<br/>**False**= dispositivo não está inscrito. |
|O dispositivo está em conformidade com as políticas de segurança do dispositivo. Para obter mais informações, consulte [Create device security policies](create-device-security-policies.md)|O valor do parâmetro *isCompliant*   é:<br/>**True**   = o dispositivo está em conformidade com as políticas.<br/>**False**   = o dispositivo não está em conformidade com as políticas.|

:::image type="content" source="../../media/basic-mobility-security/bms-7-powershell-parameters.png" alt-text="Parâmetros básicos de Mobilidade e Segurança do PowerShell":::

> [!NOTE]
> Os comandos e scripts deste artigo também retornam detalhes sobre todos os dispositivos gerenciados [por Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune).

## <a name="before-you-begin"></a>Antes de começar

Há algumas coisas que você precisa configurar para executar os comandos e scripts descritos neste artigo.

### <a name="step-1-download-and-install-the-azure-active-directory-module-for-windows-powershell"></a>Etapa 1: Baixar e instalar o módulo Azure Active Directory para Windows PowerShell

Para obter mais informações sobre essas etapas, [consulte Conexão Microsoft 365 com o PowerShell](/office365/enterprise/powershell/connect-to-office-365-powershell).

1. Vá para Microsoft Online Services Sign-In Assistente para Profissionais de [TI RTWl](https://download.microsoft.com/download/7/1/E/71EF1D05-A42C-4A1F-8162-96494B5E615C/msoidcli_32bit.msi)e selecione Baixar para Microsoft Online Services   Assistente de  **Login.**

2. Instale o Módulo Microsoft Azure Active Directory para Windows PowerShell seguindo estas etapas:

    1. Abra um prompt de comando do PowerShell do nível de administrador.

    2. Execute o comando `Install-Module MSOnline`.

    3. Se solicitado a instalar o provedor de NuGet, digite Y e pressione Enter.

    4. Se solicitado a instalar o módulo de PSGallery, digite Y e pressione Enter.

    5. Após a instalação, feche a janela de comando do PowerShell.

### <a name="step-2-connect-to-your-microsoft-365-subscription"></a>Etapa 2: Conexão para sua assinatura Microsoft 365 assinatura

1. No módulo Windows Azure Active Directory para Windows PowerShell, execute o seguinte comando.

   ```powershell
   $UserCredential = Get-Credential
   ```

2. Na caixa Windows PowerShell caixa de diálogo Solicitação de Credencial, digite o nome de usuário e a senha da sua conta de administrador global Microsoft 365 e selecione **OK**.

3. Execute o seguinte comando:

   ```powershell
   Connect-MsolService -Credential $UserCredential
   ```

### <a name="step-3-make-sure-youre-able-to-run-powershell-scripts"></a>Etapa 3: certifique-se de que você é capaz de executar scripts do PowerShell

> [!NOTE]
> Você pode ignorar essa etapa se já estiver configurada para executar scripts do PowerShell.

Para executar o Get-MsolUserDeviceComplianceStatus.ps1, você precisa habilitar a execução de scripts do PowerShell.

1. Na sua Windows Desktop, selecione **Iniciar** e digite Windows PowerShell. Clique com o botão Windows PowerShell e selecione **Executar como administrador**.

2. Execute o seguinte comando:

   ```powershell
   Set-ExecutionPolicy  RemoteSigned
   ```

3. Quando solicitado, digite Y e pressione Enter.

#### <a name="run-the-get-msoldevice-cmdlet-to-display-details-for-all-devices-in-your-organization"></a>Execute o cmdlet Get-MsolDevice para exibir detalhes de todos os dispositivos em sua organização

1. Abra o Módulo Microsoft Azure Active Directory para Windows PowerShell.

2. Execute o seguinte comando:

   ```powershell
   Get-MsolDevice -All -ReturnRegisteredOwners | Where-Object {$_.RegisteredOwners.Count -gt 0}
   ```

Para obter mais exemplos, consulte  [Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=2157939).

## <a name="run-a-script-to-get-device-details"></a>Executar um script para obter detalhes do dispositivo

Primeiro, salve o script no computador.

1. Copie e colar o texto a seguir em Bloco de notas.

   ```powershell
   param (
   [PSObject[]]$users = @(),
   [Switch]$export,
   [String]$exportFileName = "UserDeviceComplianceStatus_" + (Get-Date -Format "yyMMdd_HHMMss") + ".csv",
   [String]$exportPath = [Environment]::GetFolderPath("Desktop")
   )
   [System.Collections.IDictionary]$script:schema = @{
   DeviceId = ''
   DeviceOSType = ''
   DeviceOSVersion = ''
   DeviceTrustLevel = ''
   DisplayName = ''
   IsCompliant = ''
   IsManaged = ''
   ApproximateLastLogonTimestamp = ''
   DeviceObjectId = ''
   RegisteredOwnerUpn = ''
   RegisteredOwnerObjectId = ''
   RegisteredOwnerDisplayName = ''
   }
   function createResultObject
   {
   [PSObject]$resultObject = New-Object -TypeName PSObject -Property $script:schema
   return $resultObject
   }
   If ($users.Count -eq 0)
   {
   $users = Get-MsolUser
   }
   [PSObject[]]$result = foreach ($u in $users)
   {
   [PSObject]$devices = get-msoldevice -RegisteredOwnerUpn $u.UserPrincipalName
   foreach ($d in $devices)
   {
   [PSObject]$deviceResult = createResultObject
   $deviceResult.DeviceId = $d.DeviceId
   $deviceResult.DeviceOSType = $d.DeviceOSType
   $deviceResult.DeviceOSVersion = $d.DeviceOSVersion
   $deviceResult.DeviceTrustLevel = $d.DeviceTrustLevel
   $deviceResult.DisplayName = $d.DisplayName
   $deviceResult.IsCompliant = $d.GraphDeviceObject.IsCompliant
   $deviceResult.IsManaged = $d.GraphDeviceObject.IsManaged
   $deviceResult.DeviceObjectId = $d.ObjectId
   $deviceResult.RegisteredOwnerUpn = $u.UserPrincipalName
   $deviceResult.RegisteredOwnerObjectId = $u.ObjectId
   $deviceResult.RegisteredOwnerDisplayName = $u.DisplayName
   $deviceResult.ApproximateLastLogonTimestamp = $d.ApproximateLastLogonTimestamp
   $deviceResult
   }
   }
   If ($export)
   {
   $result | Export-Csv -path ($exportPath + "\" + $exportFileName) -NoTypeInformation
   }
   Else
   {
   $result
   }
   ```

2. Salve-o como um arquivo Windows PowerShell script usando a extensão de arquivo .ps1; por exemplo, Get-MsolUserDeviceComplianceStatus.ps1.

## <a name="run-the-script-to-get-device-information-for-a-single-user-account"></a>Execute o script para obter informações do dispositivo para uma única conta de usuário

1. Abra o Módulo Microsoft Azure Active Directory para Windows PowerShell.

2. Vá para a pasta onde você salvou o script. Por exemplo, se você o salvou em C:\PS-Scripts, execute o seguinte comando.

   ```powershell
   cd C:\PS-Scripts
   ```

3. Execute o seguinte comando para identificar o usuário para o qual você deseja obter detalhes do dispositivo. Este exemplo obtém detalhes para bar@example.com.

   ```powershell
   $u = Get-MsolUser -UserPrincipalName bar@example.com
   ```

4. Execute o seguinte comando para iniciar o script.

   ```powershell
   .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export
   ```

As informações são exportadas para sua área de trabalho Windows como um arquivo CSV. Você pode usar parâmetros adicionais para especificar o nome de arquivo e o caminho do CSV.

## <a name="run-the-script-to-get-device-information-for-a-group-of-users"></a>Execute o script para obter informações do dispositivo para um grupo de usuários

1. Abra o Módulo Microsoft Azure Active Directory para Windows PowerShell.

2. Vá para a pasta onde você salvou o script. Por exemplo, se você o salvou em C:\PS-Scripts, execute o seguinte comando.

   ```powershell
   cd C:\PS-Scripts
   ```

3. Execute o seguinte comando para identificar o grupo para o qual você deseja obter detalhes do dispositivo. Este exemplo obtém detalhes para os usuários no grupo FinanceStaff.

   ```powershell
   $u = Get-MsolGroupMember -SearchString "FinanceStaff" | % { Get-MsolUser -ObjectId $_.ObjectId }
   ```

4. Execute o seguinte comando para iniciar o script.

   ```powershell
   .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export
   ```

As informações são exportadas para sua área de trabalho Windows como um arquivo CSV. Você pode usar parâmetros adicionais para especificar o nome de arquivo e o caminho do CSV.

## <a name="related-topics"></a>Tópicos relacionados

[O Microsoft Conexão foi retirado](/collaborate/connect-redirect)

[Visão geral da Mobilidade e Segurança Básicas](overview.md)

[Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=2157939)
