---
title: Recursos de mobilidade básica e segurança
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
description: Mobilidade e segurança básica podem ajudá-lo a proteger e gerenciar dispositivos móveis.
ms.openlocfilehash: 32393f39655b81313f6592936c55e36ffe029a27
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/02/2020
ms.locfileid: "47336726"
---
# <a name="capabilities-of-basic-mobility-and-security"></a>Recursos de mobilidade básica e segurança

A mobilidade básica e a segurança podem ajudá-lo a proteger e gerenciar dispositivos móveis como iPhones, iPads, Androids e Windows phones usados por usuários do Microsoft 365 licenciados em sua organização. Você pode criar políticas de gerenciamento de dispositivos móveis com configurações que podem ajudar a controlar o acesso a emails e documentos do Microsoft 365 da sua organização para dispositivos móveis e aplicativos compatíveis. Se um dispositivo for perdido ou roubado, você poderá apagar remotamente os dados do dispositivo para remover informações organizacionais confidenciais.

## <a name="supported-devices"></a>Dispositivos suportados

Você pode usar mobilidade básica e segurança para proteger e gerenciar os dispositivos a seguir.

- iOS 11,0 ou versões posteriores
    
- Android 5,0 ou versões posteriores<sup>3</sup>
    
- Windows 8,1<sup>1</sup>
    
- Windows 8,1 RT<sup>1</sup>
    
- Windows 10<sup>2</sup>
    
- Windows 10 Mobile<sup>2</sup>   

<sup>1</sup> O controle de acesso para dispositivos Windows 8,1 RT está limitado ao Exchange ActiveSync.

<sup>2</sup> O controle de acesso para dispositivos Windows 8,1 RT está limitado ao Exchange ActiveSync.
O controle de acesso para o Windows 10 requer uma assinatura que inclua o Azure AD Premium e o dispositivo precisa ser associado ao Azure Active Directory.

<sup>3</sup> O controle de acesso para dispositivos Windows 8,1 RT está limitado ao Exchange ActiveSync.
Após junho de 2020, as versões do Android posteriores a 9 não podem gerenciar configurações de senha, exceto nos dispositivos Samsung Knox.

>[!NOTE]
>Os dispositivos já registrados com versões anteriores do sistema operacional continuam funcionando, embora os recursos possam ser alterados sem aviso prévio.

Se as pessoas em sua organização usarem dispositivos móveis que não são suportados pela mobilidade básica e segurança, convém bloquear o acesso do aplicativo Exchange ActiveSync ao email da Microsoft 365 para esses dispositivos, para ajudar a tornar os dados da sua organização mais seguros. Para obter etapas para bloquear o Exchange ActiveSync, consulte [Manage Device Access Settings in Basic Mobility and Security](manage-device-access-settings-in-basic-mobility-and-security.md).

## <a name="access-control-for-microsoft-365-email-and-documents"></a>Controle de acesso para emails e documentos do Microsoft 365

Os aplicativos com suporte para os diferentes tipos de dispositivos móveis na tabela a seguir solicitam que os usuários entrem em mobilidade básica e segurança, onde há uma nova política de gerenciamento de dispositivo móvel que se aplica ao dispositivo de um usuário e o usuário não registrou anteriormente o dispositivo. Se o dispositivo de um usuário não estiver em conformidade com uma política, dependendo de como você configurou a política, um usuário pode estar bloqueado de acessar os recursos do Microsoft 365 nesses aplicativos ou pode ter acesso, mas a Microsoft 365 relata uma violação de política.

|**Produto**|**iOS 10,0 ou posterior**|**Android 5,0 ou posterior**|
|:-----|:-----|:-----|
|**Exchange** O Exchange ActiveSync inclui emails internos e aplicativos de terceiros, como o TouchDown, que usam o Exchange ActiveSync versão 14,1 ou posterior. |Email |Email |
|**Office**   e **onedrive for Business** |Outlook </br>OneDrive </br>Word </br>Excel </br>PowerPoint|**Em telefones e tablets**:<br/>Outlook <br/> OneDrive <br/> Word <br/> Excel <br/> PowerPoint <br/> **Apenas para telefones:** <br/> Office Mobile |

>[!NOTE]
- >O suporte para o iOS 10,0 e versões posteriores inclui dispositivos iPhone e iPad.
- >O gerenciamento de dispositivos do sistema operacional BlackBerry não é suportado pelo gerenciamento de dispositivos móveis para o Microsoft 365. Use o BlackBerry Business Cloud Services (BBCS) do BlackBerry para gerenciar dispositivos do sistema operacional BlackBerry. Dispositivos BlackBerry executando o SO Android são suportados como dispositivos Android padrão
- >Os usuários não serão solicitados a inscrever-se e não serão bloqueados ou relatados para violação de política se usarem o navegador móvel para acessar sites do Microsoft 365 SharePoint, documentos no Office Online ou email no Outlook Web App.
    
O diagrama a seguir mostra o que acontece quando um usuário com um novo dispositivo entra em um aplicativo que dá suporte ao controle de acesso com mobilidade básica e segurança. O usuário é bloqueado de acessar os recursos do Microsoft 365 no aplicativo até que eles registrem seus dispositivos.

:::image type="content" source="../../media/basic-mobility-security/bms-1-access-control.png" alt-text="Mobilidade básica e controle de acesso de segurança":::

Observação: as políticas e regras de acesso criadas no MDM para o Microsoft 365 Business Standard substituirão as políticas de caixa de correio do dispositivo móvel do Exchange ActiveSync e as regras de acesso do dispositivo criadas no centro de administração do Exchange. Após um dispositivo ser inscrito no MDM para o Microsoft 365 Business Standard, qualquer política de caixa de correio de dispositivo móvel do Exchange ActiveSync ou regra de acesso de dispositivo aplicada ao dispositivo será ignorada. Para saber mais sobre o Exchange ActiveSync, confira [Exchange ActiveSync in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=524380).

## <a name="policy-settings-for-mobile-devices"></a>Configurações de política para dispositivos móveis

Se você criar uma política para bloquear o acesso com determinadas configurações ativadas, os usuários serão impedidos de acessar os recursos do Microsoft 365 ao usar um aplicativo suportado listado no [controle de acesso de emails e documentos da Microsoft 365](https://support.microsoft.com/office/capabilities-of-basic-mobility-and-security-a1da44e5-7475-4992-be91-9ccec25905b0?ui=en-us&rs=en-us&ad=us#bkmk_accesscontrol). 

As configurações que podem impedir que os usuários acessem os recursos do Microsoft 365 estão nestas seções:

- Segurança
    
- Criptografia
    
- Desbloqueado
    
- Perfil de email gerenciado  

Por exemplo, o diagrama a seguir mostra o que acontece quando um usuário com um dispositivo registrado não está em conformidade com uma configuração de segurança em uma política de gestão de dispositivos móveis que se aplica ao seu dispositivo. O usuário entra em um aplicativo que oferece suporte ao controle de acesso com mobilidade básica e segurança. Eles são impedidos de acessar os recursos do Microsoft 365 no aplicativo até que o dispositivo esteja em conformidade com a configuração de segurança.

:::image type="content" source="../../media/basic-mobility-security/bms-2-device-not-compliant.png" alt-text="Mobilidade básica e mensagem de conformidade de segurança":::

As seções a seguir listam as configurações de política que você pode usar para ajudar a proteger e gerenciar dispositivos móveis que se conectam aos seus recursos de organização do Microsoft 365.

## <a name="security-settings"></a>Configurações de segurança

|**Nome da configuração**|**iOS 7,1 e posterior**|**Android 5 e posterior**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|Exigir uma senha|Sim|Sim|Sim|
|Impedir senha simples|Sim|Não|Não|
|Exigir uma senha alfanumérica|Sim|Não|Não|
|Tamanho mínimo da senha |Sim|Sim|Sim|
|Número de falhas na entrada antes de o dispositivo ser apagado |Sim|Sim|Sim|
|Minutos de inatividade antes de o dispositivo ser bloqueado |Sim|Sim|Sim|
|Vencimento da senha (dias) |Sim|Sim|Sim|
|Lembrar histórico de senhas e impedir reutilização |Sim|Sim|Sim|

## <a name="encryption-settings"></a>Configurações de criptografia 

|**Nome da configuração**|**iOS 7,1 e posterior**|**Android 5 e posterior**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|Exigir criptografia de dados nos dispositivos<sup>1</sup> |Não|Sim|Sim|

<sup>1</sup> Com o Samsung Knox, você também pode exigir a criptografia em cartões de armazenamento. 

## <a name="jail-broken-setting"></a>Configuração de desbloqueio 

|**Nome da configuração**|**iOS 7,1 e posterior**|**Android 5 e posterior**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|O dispositivo não pode ser desbloqueado ou modificado |Sim|Sim|Sim|

## <a name="managed-email-profile-option"></a>Opção de perfil de email gerenciado 

A opção a seguir pode impedir que os usuários acessem seus emails do Microsoft 365 se estiverem usando um perfil de email criado manualmente. Usuários em dispositivos iOS devem excluir o perfil de email criado manualmente antes de poderem acessar seus emails. Depois de excluir o perfil, um novo perfil é criado automaticamente no dispositivo. Para obter instruções sobre como os usuários finais podem obter conformidade, consulte [uma conta de email existente foi encontrada](https://docs.microsoft.com/intune-user-help/existing-company-email-account-found).

|**Nome da configuração**|**iOS 7,1 e posterior**|**Android 5 e posterior**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|Perfil de email gerenciado |Sim|Não|Não|

## <a name="cloud-settings"></a>Configurações de nuvem 

|**Nome da configuração**|**iOS 7,1 e posterior**|**Android 5 e posterior**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|Exige backup criptografado |Sim|Não|Não|
|Bloquear backup em nuvem |Sim|Não|Não|
|Bloquear sincronização de documento |Sim|Não|Não|
|Bloquear sincronização de fotos  |Sim|Não|Não|
|Permitir backup do Google  |Não disponível|Não|Sim|
|Permitir a sincronização automática de conta do Google  |Não disponível|Não|Sim|

## <a name="system-settings"></a>Configurações do sistema 

|**Nome da configuração**|**iOS 7,1 e posterior**|**Android 5 e posterior**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|Bloquear captura de tela |Sim|Não|Sim|
|Bloquear o envio de dados de diagnóstico do dispositivo |Sim|Não|Sim|

## <a name="application-settings"></a>Configurações de aplicativo 

|**Nome da configuração**|**iOS 7,1 e posterior**|**Android 5 e posterior**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|Bloquear videoconferências no dispositivo |Sim|Não|Não|
|Bloquear acesso ao repositório de aplicativos |Sim|Não|Sim|
|Exigir senha ao acessar o repositório de aplicativos |Não|Sim|Sim|

## <a name="device-capabilities-settings"></a>Configurações de recursos do dispositivo 

|**Nome da configuração**|**iOS 7,1 e posterior**|**Android 5 e posterior**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|Bloquear conexão com armazenamento removível |Sim|Sim|Não|
|Bloquear conexão Bluetooth |Sim|Sim|Não|

##  <a name="additional-settings"></a>Configurações adicionais 

Você pode definir as seguintes configurações de política adicionais usando cmdlets do PowerShell. Para obter mais informações, consulte [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps).

|**Nome da configuração**|**iOS 7,1 e posterior**|**Android 5 e posterior**|
|:-----|:-----|:-----|
|CameraEnabled|Sim|Sim|
|RegionRatings|Sim|Não|
|MoviesRatings|Sim|Não|
|TVShowsRating |Sim|Não|
|AppsRatings |Sim|Não|
|AllowVoiceDialing |Sim|Não|
|AllowVoiceAssistant |Sim|Não|
|AllowAssistantWhileLocked  |Sim|Não|
|AllowPassbookWhileLocked |Sim|Não|
|MaxPasswordGracePeriod |Sim|Não|
|PasswordQuality |Não|Sim|
|SystemSecurityTLS  |Sim|Não|
|WLANEnabled  |Não|Não|

## <a name="settings-supported-by-windows"></a>Configurações compatíveis com o Windows 

Você pode gerenciar os dispositivos do Windows 10, registrando-os como dispositivos móveis. Após a implantação de uma política aplicável, os usuários com dispositivos Windows 10 serão solicitados a se inscrever na mobilidade básica e segurança na primeira vez que usarem o aplicativo de email interno para acessar seus emails do Microsoft 365 (requer a assinatura do Azure AD Premium).

As configurações a seguir são suportadas para dispositivos Windows 10 registrados como dispositivos móveis. Essa configuração não impede que os usuários acessem os recursos do Microsoft 365.

### <a name="security-settings"></a>Configurações de segurança

- Exigir uma senha alfanumérica

- Tamanho mínimo da senha
    
- Número de falhas de entrada antes de o dispositivo ser apagado
    
- Minutos de inatividade antes de o dispositivo ser bloqueado
    
- Vencimento da senha (dias)
    
- Lembrar histórico de senhas e impedir reutilização   

>[!NOTE]
>As configurações a seguir regulam senhas apenas controlam as contas locais do Windows. As contas do Windows fornecidas através de ingressar em um domínio ou Active Directory do Azure não são afetadas por essas configurações.

### <a name="system-settings"></a>Configurações do sistema

Bloquear o envio de dados de diagnóstico do dispositivo.

### <a name="additional-settings"></a>Configurações adicionais

Você pode definir essas configurações de política adicionais usando cmdlets do PowerShell:

- AllowConvenienceLogon
    
- UserAccountControlStatus
    
- FirewallStatus
    
- AutoUpdateStatus
    
- AntiVirusStatus   

- AntiVirusSignatureStatus
    
- SmartScreenEnabled
    
- WorkFoldersSyncUrl
    

## <a name="remotely-wipe-a-mobile-device"></a>Apagar remotamente um dispositivo móvel

Se um dispositivo for perdido ou roubado, você poderá remover dados organizacionais confidenciais e ajudar a impedir o acesso aos seus recursos de organização do Microsoft 365, fazendo uma limpeza do centro de conformidade & o gerenciamento de dispositivos de **prevenção de perda de dados**>  >  **Device management**. Você pode fazer um apagamento seletivo para remover apenas os dados organizacionais ou um apagamento de dados completo para excluir todas as informações de um dispositivo e restaurá-lo para suas configurações de fábrica.

Para obter mais informações, consulte [apagar um dispositivo móvel em mobilidade básica e segurança](wipe-mobile-device.md).

## <a name="related-topics"></a>Tópicos relacionados

[Visão geral da mobilidade básica e segurança para o Microsoft 365](overview-of-basic-mobility-and-security-for-microsoft-365.md)

[Criar políticas de segurança de dispositivo na mobilidade básica e segurança](create-device-security-policies-in-basic-mmobility-and-security.md)