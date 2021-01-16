---
title: Capacidades de Mobilidade e Segurança Básica
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
description: A Mobilidade Básica e Segurança pode ajudá-lo a proteger e gerenciar dispositivos móveis.
ms.openlocfilehash: 746131e90e207d7b888a3ddcaf4ff0656606a2c7
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "49877111"
---
# <a name="capabilities-of-basic-mobility-and-security"></a>Capacidades de Mobilidade e Segurança Básica

A Mobilidade Básica e Segurança pode ajudá-lo a proteger e gerenciar dispositivos móveis como iPhones, iPads, Androids e Windows Phones usados por usuários licenciados do Microsoft 365 em sua organização. Você pode criar políticas de gerenciamento de dispositivo móvel com configurações que podem ajudar a controlar o acesso aos emails e documentos do Microsoft 365 da sua organização para dispositivos móveis e aplicativos compatíveis. Se um dispositivo for perdido ou roubado, você poderá apagar remotamente os dados do dispositivo para remover informações organizacionais confidenciais.

## <a name="supported-devices"></a>Dispositivos suportados

Você pode usar o Basic Mobility and Security para proteger e gerenciar os seguintes dispositivos.

- iOS 11.0 ou versões posteriores

- Android 5.0 ou versões posteriores<sup>3</sup>

- Windows 8.1<sup>1</sup>

- Windows 8.1 RT<sup>1</sup>

- Windows 10<sup>2</sup>

- Windows 10 Mobile<sup>2</sup>

<sup>1</sup> O controle de acesso para dispositivos Windows 8.1 RT está limitado ao Exchange ActiveSync.

<sup>2</sup> O controle de acesso para dispositivos Windows 8.1 RT está limitado ao Exchange ActiveSync.
O controle de acesso para o Windows 10 requer uma assinatura que inclua o Azure AD Premium e o dispositivo precisa ser ingressado no Azure Active Directory.

<sup>3</sup> O controle de acesso para dispositivos Windows 8.1 RT está limitado ao Exchange ActiveSync.
Após junho de 2020, as versões do Android posteriores às 9 não poderão gerenciar as configurações de senha, exceto em dispositivos Samsung Knox.

>[!NOTE]
>Os dispositivos já inscritos em versões anteriores do sistema operacional continuam funcionando, embora os recursos possam mudar sem aviso prévio.

Se as pessoas em sua organização usam dispositivos móveis que não são suportados pelo Basic Mobility and Security, você pode bloquear o acesso do aplicativo Exchange ActiveSync ao email do Microsoft 365 para esses dispositivos, para ajudar a tornar os dados da sua organização mais seguros. Para ver as etapas para bloquear o Exchange ActiveSync, consulte Gerenciar configurações de acesso [do dispositivo em Mobilidade e Segurança Básica.](manage-device-access-settings.md)

## <a name="access-control-for-microsoft-365-email-and-documents"></a>Controle de acesso para emails e documentos do Microsoft 365

Os aplicativos com suporte para os diferentes tipos de dispositivos móveis na tabela a seguir solicitam que os usuários se inscrevam na Mobilidade Básica e Segurança, onde há uma nova política de gerenciamento de dispositivo móvel que se aplica ao dispositivo de um usuário e o usuário ainda não registrou o dispositivo. Se o dispositivo de um usuário não estiver em conformidade com uma política, dependendo de como você configurar a política, um usuário poderá ser impedido de acessar os recursos do Microsoft 365 nesses aplicativos ou poderá ter acesso, mas o Microsoft 365 relata uma violação de política.

|**Product**|**iOS 10.0 ou posterior**|**Android 5.0 ou posterior**|
|:-----|:-----|:-----|
|**Exchange** O Exchange ActiveSync inclui emails e aplicativos de terceiros, como o TouchDown, que usam o Exchange ActiveSync versão 14.1 ou posterior. |Email |Email |
|**Office**   e  **OneDrive for Business** |Outlook </br>OneDrive </br>Word </br>Excel </br>PowerPoint|**Em telefones e tablets:**<br/>Outlook <br/> OneDrive <br/> Word <br/> Excel <br/> PowerPoint <br/> **Apenas para telefones:** <br/> Office Mobile |

>[!NOTE]
- >O suporte para iOS 10.0 e versões posteriores inclui dispositivos iPhone e iPad.
- >O gerenciamento de dispositivos BlackBerry OS não é suportado pela Segurança Básica e Mobilidade. Use o BlackBerry Business Cloud Services (BBCS) da BlackBerry para gerenciar dispositivos BlackBerry OS. Os dispositivos Blackberry que executam o sistema operacional Android têm suporte como dispositivos Android padrão
- >Os usuários não serão solicitados a se inscrever e não serão bloqueados ou relatados por violação de política se usarem o navegador móvel para acessar sites do Microsoft 365 SharePoint, documentos no Office Online ou email no Outlook Web App.

O diagrama a seguir mostra o que acontece quando um usuário com um novo dispositivo se conectado a um aplicativo que dá suporte ao controle de acesso com Mobilidade Básica e Segurança. O usuário é impedido de acessar os recursos do Microsoft 365 no aplicativo até registrar o dispositivo.

:::image type="content" source="../../media/basic-mobility-security/bms-1-access-control.png" alt-text="Basic Mobility and Security access control":::

> [!NOTE]
> Políticas e regras de acesso criadas no Basic Mobility and Security para o Microsoft 365 Business Standard substituirão as políticas de caixa de correio de dispositivo móvel do Exchange ActiveSync e as regras de acesso a dispositivo criadas no Centro de administração do Exchange. Depois que um dispositivo for inscrito no Basic Mobility and Security para o Microsoft 365 Business Standard, qualquer política de caixa de correio de dispositivo móvel do Exchange ActiveSync ou regra de acesso ao dispositivo aplicada ao dispositivo será ignorada. Para saber mais sobre o Exchange ActiveSync, consulte [Exchange ActiveSync no Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=524380).

## <a name="policy-settings-for-mobile-devices"></a>Configurações de política para dispositivos móveis

Se você criar uma política para bloquear o acesso com determinadas configurações, os usuários serão impedidos de acessar os recursos do Microsoft 365 ao usar um aplicativo com suporte listado no Controle de acesso para emails e documentos do [Microsoft 365.](capabilities.md) 

As configurações que podem impedir que os usuários acessem os recursos do Microsoft 365 estão nestas seções:

- Segurança

- Criptografia

- Desbloqueado

- Perfil de email gerenciado  

Por exemplo, o diagrama a seguir mostra o que acontece quando um usuário com um dispositivo registrado não está em conformidade com uma configuração de segurança em uma política de gestão de dispositivos móveis que se aplica ao seu dispositivo. O usuário faz o acesso a um aplicativo que dá suporte ao controle de acesso com Mobilidade Básica e Segurança. Eles são impedidos de acessar recursos do Microsoft 365 no aplicativo até que seus dispositivos sejam de acordo com a configuração de segurança.

:::image type="content" source="../../media/basic-mobility-security/bms-2-device-not-compliant.png" alt-text="Mensagem de conformidade básica de mobilidade e segurança":::

As seções a seguir listam as configurações de política que você pode usar para ajudar a proteger e gerenciar dispositivos móveis que se conectam aos recursos da sua organização do Microsoft 365.

## <a name="security-settings"></a>Configurações de segurança

|**Nome da configuração**|**iOS 7.1 e posterior**|**Android 5 e posterior**|**Samsung Knox**|
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

|**Nome da configuração**|**iOS 7.1 e posterior**|**Android 5 e posterior**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|Exigir criptografia de dados em dispositivos<sup>1</sup> |Não|Sim|Sim|

<sup>1</sup> Com Samsung Knox, você também pode exigir criptografia em cartões de armazenamento. 

## <a name="jail-broken-setting"></a>Configuração de desbloqueio 

|**Nome da configuração**|**iOS 7.1 e posterior**|**Android 5 e posterior**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|O dispositivo não pode ser desbloqueado ou modificado |Sim|Sim|Sim|

## <a name="managed-email-profile-option"></a>Opção de perfil de email gerenciado 

A opção a seguir pode impedir que os usuários acessem seus emails do Microsoft 365 se eles estão usando um perfil de email criado manualmente. Usuários em dispositivos iOS devem excluir o perfil de email criado manualmente antes de poderem acessar seus emails. Depois que eles excluíem o perfil, um novo perfil é criado automaticamente no dispositivo. Para obter instruções sobre como os usuários finais podem ficar em conformidade, consulte [Uma conta de email existente foi encontrada.](https://docs.microsoft.com/intune-user-help/existing-company-email-account-found)

|**Nome da configuração**|**iOS 7.1 e posterior**|**Android 5 e posterior**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|Perfil de email gerenciado |Sim|Não|Não|

## <a name="cloud-settings"></a>Configurações de nuvem

|**Nome da configuração**|**iOS 7.1 e posterior**|**Android 5 e posterior**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|Exige backup criptografado |Sim|Não|Não|
|Bloquear backup em nuvem |Sim|Não|Não|
|Bloquear sincronização de documento |Sim|Não|Não|
|Bloquear sincronização de fotos  |Sim|Não|Não|
|Permitir backup do Google  |N/D|Não|Sim|
|Permitir sincronização automática de conta do Google  |N/D|Não|Sim|

## <a name="system-settings"></a>Configurações do sistema

|**Nome da configuração**|**iOS 7.1 e posterior**|**Android 5 e posterior**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|Bloquear captura de tela |Sim|Não|Sim|
|Bloquear o envio de dados de diagnóstico do dispositivo |Sim|Não|Sim|

## <a name="application-settings"></a>Configurações de aplicativo

|**Nome da configuração**|**iOS 7.1 e posterior**|**Android 5 e posterior**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|Bloquear videoconferências no dispositivo |Sim|Não|Não|
|Bloquear acesso ao repositório de aplicativos |Sim|Não|Sim|
|Exigir senha ao acessar o repositório de aplicativos |Não|Sim|Sim|

## <a name="device-capabilities-settings"></a>Configurações de recursos do dispositivo

|**Nome da configuração**|**iOS 7.1 e posterior**|**Android 5 e posterior**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|Bloquear conexão com armazenamento removível |Sim|Sim|Não|
|Bloquear conexão Bluetooth |Sim|Sim|Não|

## <a name="additional-settings"></a>Configurações adicionais

Você pode definir as seguintes configurações de política adicionais usando & os cmdlets do PowerShell do Centro de Conformidade e Segurança. Para obter mais informações, consulte [o PowerShell & Centro de Conformidade e Segurança.](https://docs.microsoft.com/powershell/exchange/scc-powershell)

|**Nome da configuração**|**iOS 7.1 e posterior**|**Android 5 e posterior**|
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

## <a name="settings-supported-by-windows"></a>Configurações com suporte no Windows

Você pode gerenciar dispositivos Windows 10 registrando-os como dispositivos móveis. Depois que uma política aplicável for implantada, os usuários com dispositivos Windows 10 precisarão se inscrever na Mobilidade Básica e Segurança na primeira vez que usarem o aplicativo de email interno para acessar seus emails do Microsoft 365 (requer a assinatura do Azure AD Premium).

As configurações a seguir são compatíveis com dispositivos Windows 10 que estão inscritos como dispositivos móveis. Essa configuração não impedirá que os usuários acessem os recursos do Microsoft 365.

### <a name="security-settings"></a>Configurações de segurança

- Exigir uma senha alfanumérica

- Tamanho mínimo da senha

- Número de falhas de entrada antes de o dispositivo ser apagado

- Minutos de inatividade antes de o dispositivo ser bloqueado

- Vencimento da senha (dias)

- Lembrar histórico de senhas e impedir reutilização

>[!NOTE]
>As configurações a seguir que regulam senhas controlam apenas contas locais do Windows. As contas do Windows fornecidas por meio da junção de um domínio ou do Azure Active Directory não são afetadas por essas configurações.

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

Se um dispositivo for perdido ou roubado, você poderá remover dados organizacionais confidenciais e ajudar a impedir o acesso aos recursos da sua organização do Microsoft 36 & 5 fazendo uma limpeza no Centro de Conformidade e Segurança do > Gerenciamento de dispositivos de prevenção de perda de  >  dados. Você pode fazer um apagamento seletivo para remover apenas os dados organizacionais ou um apagamento de dados completo para excluir todas as informações de um dispositivo e restaurá-lo para suas configurações de fábrica.

Para obter mais informações, [consulte Apagar um dispositivo móvel em Basic Mobility and Security](wipe-mobile-device.md).

## <a name="related-topics"></a>Tópicos relacionados

[Visão geral da Mobilidade Básica e Segurança do Microsoft 365](overview.md)

[Criar políticas de segurança de dispositivos em Mobilidade Básica e Segurança](create-device-security-policies.md)