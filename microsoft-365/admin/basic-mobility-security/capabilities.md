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
description: A Mobilidade Básica e a Segurança podem ajudá-lo a proteger e gerenciar dispositivos móveis.
ms.openlocfilehash: 41df5bfba7362d9c2b3a47deca4e4586902bbd98
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706173"
---
# <a name="capabilities-of-basic-mobility-and-security"></a>Capacidades de Mobilidade e Segurança Básica

O Basic Mobility and Security pode ajudá-lo a proteger e gerenciar dispositivos móveis como iPhones, iPads, Androids e telefones Windows usados por usuários licenciados Microsoft 365 em sua organização. Você pode criar políticas de gerenciamento de dispositivo Microsoft 365 móvel com configurações que podem ajudar a controlar o acesso aos emails e documentos da sua organização para dispositivos móveis e aplicativos compatíveis. Se um dispositivo for perdido ou roubado, você poderá apagar remotamente os dados do dispositivo para remover informações organizacionais confidenciais.

## <a name="supported-devices"></a>Dispositivos suportados

Você pode usar o Basic Mobility and Security para proteger e gerenciar os seguintes dispositivos.

- Versões do iOS 11.0 ou posteriores

- Android 5.0 ou versões<sup>posteriores 3</sup>

- Windows 8.1<sup>1</sup>

- Windows 8.1 RT<sup>1</sup>

- Windows 10<sup>2</sup>

- Windows 10 Mobile<sup>2</sup>

<sup>1</sup> O controle de acesso Windows 8.1 dispositivos RT está limitado a Exchange ActiveSync.

<sup>2</sup> O controle de acesso para Windows 10 requer uma assinatura que inclui o Azure AD Premium e o dispositivo precisa ser ingressado no Azure Active Directory.

<sup>3</sup> Após junho de 2020, as versões do Android posteriores a 9 não podem gerenciar configurações de senha, exceto em dispositivos Samsung Knox.

>[!NOTE]
>Os dispositivos já inscritos com versões anteriores do sistema operacional continuam funcionando, embora os recursos possam mudar sem aviso prévio.

Se as pessoas em sua organização usam dispositivos móveis que não são compatíveis com a Mobilidade Básica e Segurança, talvez você queira bloquear o acesso do aplicativo Exchange ActiveSync a emails Microsoft 365 para esses dispositivos, para ajudar a tornar os dados da sua organização mais seguros. Para etapas para bloquear Exchange ActiveSync, consulte [Manage device access settings in Basic Mobility and Security](manage-device-access-settings.md).

## <a name="access-control-for-microsoft-365-email-and-documents"></a>Controle de acesso para Microsoft 365 email e documentos

Os aplicativos com suporte para os diferentes tipos de dispositivos móveis na tabela a seguir solicitam que os usuários se inscrevam no Basic Mobility and Security, onde há uma nova política de gerenciamento de dispositivo móvel que se aplica ao dispositivo de um usuário e o usuário não registrou o dispositivo anteriormente. Se o dispositivo de um usuário não estiver em conformidade com uma política, dependendo de como você configurar a política, um usuário poderá ser impedido de acessar recursos Microsoft 365 nesses aplicativos, ou ele poderá ter acesso, mas Microsoft 365 relata uma violação de política.

|**Produto**|**iOS 10.0 ou posterior**|**Android 5.0 ou posterior**|
|:-----|:-----|:-----|
|**Exchange** Exchange ActiveSync inclui aplicativos de email e de terceiros, como o TouchDown, que usam Exchange ActiveSync versão 14.1 ou posterior. |Email |Email |
|**Office**   e  **OneDrive for Business** |Outlook </br>OneDrive </br>Word </br>Excel </br>PowerPoint|**Em telefones e tablets**:<br/>Outlook <br/> OneDrive <br/> Word <br/> Excel <br/> PowerPoint <br/> **Apenas para telefones:** <br/> Office Mobile |

>[!NOTE]
- >O suporte para iOS 10.0 e versões posteriores inclui iPhone e iPad dispositivos.
- >O gerenciamento de dispositivos BLACKBerry OS não é suportado pela Segurança Básica e Mobilidade. Use o BlackBerry Business Cloud Services (BBCS) do BlackBerry para gerenciar dispositivos blackberry do sistema operacional. Os dispositivos Blackberry que executam o sistema operacional Android têm suporte como dispositivos Android padrão
- >Os usuários não serão solicitados a se inscrever e não serão bloqueados ou relatados por violação de política se usarem o navegador móvel para acessar sites Microsoft 365 SharePoint, documentos no Office Online ou emails no Outlook Web App.

O diagrama a seguir mostra o que acontece quando um usuário com um novo dispositivo acessa um aplicativo que dá suporte ao controle de acesso com Mobilidade Básica e Segurança. O usuário é impedido de acessar Microsoft 365 recursos no aplicativo até que ele inscreva seu dispositivo.

:::image type="content" source="../../media/basic-mobility-security/bms-1-access-control.png" alt-text="Controle básico de acesso de mobilidade e segurança":::

> [!NOTE]
> Políticas e regras de acesso criadas no Basic Mobility and Security for Microsoft 365 Business Standard substituirão Exchange ActiveSync políticas de caixa de correio de dispositivo móvel e regras de acesso a dispositivo criadas no centro de administração Exchange. Depois que um dispositivo for inscrito no Basic Mobility and Security for Microsoft 365 Business Standard Exchange ActiveSync, qualquer política de caixa de correio de dispositivo móvel ou regra de acesso a dispositivo móvel aplicada ao dispositivo será ignorada. Para saber mais sobre Exchange ActiveSync, [consulte Exchange ActiveSync em Exchange Online](/exchange/clients-and-mobile-in-exchange-online/exchange-activesync/exchange-activesync).

## <a name="policy-settings-for-mobile-devices"></a>Configurações de política para dispositivos móveis

Se você criar uma política para bloquear o acesso com determinadas configurações ativas, os usuários serão impedidos de acessar Microsoft 365 recursos ao usar um aplicativo com suporte listado no controle do Access para emails e documentos do [Microsoft 365.](capabilities.md) 

As configurações que podem impedir que os usuários acessem Microsoft 365 recursos estão nessas seções:

- Segurança

- Criptografia

- Desbloqueado

- Perfil de email gerenciado  

Por exemplo, o diagrama a seguir mostra o que acontece quando um usuário com um dispositivo registrado não está em conformidade com uma configuração de segurança em uma política de gestão de dispositivos móveis que se aplica ao seu dispositivo. O usuário faz o acesso a um aplicativo que oferece suporte ao controle de acesso com Mobilidade Básica e Segurança. Eles são impedidos de acessar Microsoft 365 recursos no aplicativo até que seu dispositivo seja de acordo com a configuração de segurança.

:::image type="content" source="../../media/basic-mobility-security/bms-2-device-not-compliant.png" alt-text="Mensagem de conformidade básica de mobilidade e segurança":::

As seções a seguir listam as configurações de política que você pode usar para ajudar a proteger e gerenciar dispositivos móveis que se conectam aos recursos Microsoft 365 sua organização.

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
|Exigir criptografia de dados em<sup>dispositivos 1</sup> |Não|Sim|Sim|

<sup>1</sup> Com o Samsung Knox, você também pode exigir criptografia em cartões de armazenamento. 

## <a name="jail-broken-setting"></a>Configuração de desbloqueio 

|**Nome da configuração**|**iOS 7.1 e posterior**|**Android 5 e posterior**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|O dispositivo não pode ser desbloqueado ou modificado |Sim|Sim|Sim|

## <a name="managed-email-profile-option"></a>Opção de perfil de email gerenciado 

A opção a seguir pode impedir que os usuários acessem seus Microsoft 365 email se eles estão usando um perfil de email criado manualmente. Usuários em dispositivos iOS devem excluir o perfil de email criado manualmente antes de poderem acessar seus emails. Depois de excluir o perfil, um novo perfil é criado automaticamente no dispositivo. Para obter instruções sobre como os usuários finais podem ser compatíveis, consulte [Uma conta de email existente foi encontrada](/intune-user-help/existing-company-email-account-found).

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
|Permitir backup do Google  |N/A|Não|Sim|
|Permitir sincronização automática de conta do Google  |N/A|Não|Sim|

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

Você pode definir as seguintes configurações de política adicionais usando cmdlets do Centro de Conformidade e Segurança & PowerShell. Para obter mais informações, consulte [Security & Compliance Center PowerShell](/powershell/exchange/scc-powershell).

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

## <a name="settings-supported-by-windows"></a>Configurações suportado por Windows

Você pode gerenciar Windows 10 dispositivos registrando-os como dispositivos móveis. Após a implantação de uma política aplicável, os usuários com dispositivos Windows 10 serão obrigados a se inscrever no Basic Mobility and Security na primeira vez que usarem o aplicativo de email interno para acessar seus emails Microsoft 365 (exige a assinatura premium do Azure AD).

As configurações a seguir são suportadas para Windows 10 dispositivos que estão inscritos como dispositivos móveis. Essa configuração não impedirá que os usuários acessem Microsoft 365 recursos.

### <a name="security-settings"></a>Configurações de segurança

- Exigir uma senha alfanumérica

- Tamanho mínimo da senha

- Número de falhas de entrada antes de o dispositivo ser apagado

- Minutos de inatividade antes de o dispositivo ser bloqueado

- Vencimento da senha (dias)

- Lembrar histórico de senhas e impedir reutilização

>[!NOTE]
>As configurações a seguir que regulamentam senhas controlam apenas contas Windows locais. Windows contas fornecidas por meio da junção de um domínio ou Azure Active Directory não são afetadas por essas configurações.

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

Se um dispositivo for perdido ou roubado, você poderá remover dados organizacionais confidenciais e ajudar a impedir o acesso aos recursos da sua organização Microsoft 365, fazendo uma limpeza do Centro de Conformidade & segurança > Prevenção contra perda de dados Gerenciamento de  >  dispositivos . Você pode fazer um apagamento seletivo para remover apenas os dados organizacionais ou um apagamento de dados completo para excluir todas as informações de um dispositivo e restaurá-lo para suas configurações de fábrica.

Para obter mais informações, [consulte Wipe a mobile device in Basic Mobility and Security](wipe-mobile-device.md).

## <a name="related-content"></a>Conteúdo relacionado

[Visão geral da Mobilidade Básica e Segurança para Microsoft 365](overview.md) (artigo)\
[Criar políticas de segurança de dispositivos no Basic Mobility and Security](create-device-security-policies.md) (artigo)