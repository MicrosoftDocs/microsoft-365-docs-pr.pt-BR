---
title: Implantar atualizações do Microsoft Defender ATP para Mac
description: Controlar atualizações do Microsoft Defender ATP para Mac em ambientes corporativos.
keywords: microsoft, defender, atp, mac, atualizações, implantar
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 3321c1bd181b89c53e2618fc20fa7f733a20cfc1
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689048"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-on-macos"></a>Implantar atualizações do Microsoft Defender para Ponto de Extremidade no macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade no macOS](microsoft-defender-endpoint-mac.md)
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

A Microsoft publica regularmente atualizações de software para melhorar o desempenho, a segurança e fornecer novos recursos.

Para atualizar o Microsoft Defender para Ponto de Extremidade no macOS, um programa chamado Microsoft AutoUpdate (MAU) é usado. Por padrão, o MAU verifica automaticamente as atualizações diariamente, mas você pode alterá-la para semanal, mensal ou manualmente.

![Captura de tela MAU](images/MDATP-34-MAU.png)

Se você decidir implantar atualizações usando suas ferramentas de distribuição de software, configure o MAU para verificar manualmente as atualizações de software. Você pode implantar preferências para configurar como e quando o MAU verifica se há atualizações para os Macs em sua organização.

## <a name="use-msupdate"></a>Usar o msupdate

O MAU inclui uma ferramenta de linha de comando, chamada *msupdate*, projetada para administradores de IT para que eles tenham um controle mais preciso sobre quando as atualizações são aplicadas. As instruções sobre como usar essa ferramenta podem ser encontradas em [Atualizar o Office para Mac usando msupdate](https://docs.microsoft.com/deployoffice/mac/update-office-for-mac-using-msupdate).

No MAU, o identificador de aplicativo do Microsoft Defender para Ponto de Extremidade no macOS é *WDAV00*. Para baixar e instalar as atualizações mais recentes do Microsoft Defender para Ponto de Extremidade no macOS, execute o seguinte comando de uma janela de Terminal:

```
./msupdate --install --apps wdav00
```

## <a name="set-preferences-for-microsoft-autoupdate"></a>Definir preferências para o Microsoft AutoUpdate

Esta seção descreve as preferências mais comuns que podem ser usadas para configurar o MAU. Essas configurações podem ser implantadas como um perfil de configuração por meio do console de gerenciamento que sua empresa está usando. Um exemplo de perfil de configuração é mostrado nas seções a seguir.

### <a name="set-the-channel-name"></a>Definir o nome do canal

O canal determina o tipo e a frequência de atualizações oferecidas por meio do MAU. Os `Beta` dispositivos em podem experimentar novos recursos antes dos dispositivos `Preview` e `Current` . 

O `Current` canal contém a versão mais estável do produto.

>[!IMPORTANT]
> Antes do Microsoft AutoUpdate versão 4.29, os canais tinham nomes diferentes: 
> 
> - `Beta` foi nomeado `InsiderFast` (Insider Fast)
> - `Preview` foi nomeado `External` (Insider Slow)
> - `Current` foi nomeado `Production`

>[!TIP]
>Para visualizar novos recursos e fornecer comentários antecipados, é recomendável configurar alguns dispositivos em sua empresa para `Beta` ou `Preview` .

|Section|Valor|
|:--|:--|
| **Domínio** | com.microsoft.autoupdate2 |
| **Tecla** | ChannelName |
| **Tipo de dados** | Cadeia de caracteres |
| **Valores possíveis** | Beta <br/> Visualização <br/> Atual |
|||

>[!WARNING]
>Essa configuração altera o canal para todos os aplicativos que são atualizados por meio do Microsoft AutoUpdate. Para alterar o canal somente para o Microsoft Defender para Ponto de Extremidade no macOS, execute o seguinte comando após substituir `[channel-name]` pelo canal desejado:
> ```bash
> defaults write com.microsoft.autoupdate2 Applications -dict-add "/Applications/Microsoft Defender ATP.app" " { 'Application ID' = 'WDAV00' ; 'App Domain' = 'com.microsoft.wdav' ; LCID = 1033 ; ChannelName = '[channel-name]' ; }"
> ```

### <a name="set-update-check-frequency"></a>Definir a frequência de verificação de atualização

Altere a frequência com que o MAU pesquisa atualizações.

|Section|Valor|
|:--|:--|
| **Domínio** | com.microsoft.autoupdate2 |
| **Tecla** | UpdateCheckFrequency |
| **Tipo de dados** | Inteiro |
| **Valor padrão** | 720 (minutos) |
| **Comment** | Esse valor é definido em minutos. |


### <a name="change-how-mau-interacts-with-updates"></a>Alterar como o MAU interage com atualizações

Altere como o MAU pesquisa atualizações.

|Section|Valor|
|:--|:--|
| **Domínio** | com.microsoft.autoupdate2 |
| **Tecla** | HowToCheck |
| **Tipo de dados** | Cadeia de caracteres |
| **Valores possíveis** | Manual <br/> AutomaticCheck <br/> AutomaticDownload |
| **Comment** |  Observe que AutomaticDownload fará um download e instalará silenciosamente, se possível. |


### <a name="change-whether-the-check-for-updates-button-is-enabled"></a>Alterar se o botão "Verificar atualizações" está habilitado

Altere se os usuários locais poderão clicar na opção "Verificar atualizações" na interface do usuário Microsoft AutoUpdate.

|Section|Valor|
|:--|:--|
| **Domínio** | com.microsoft.autoupdate2 |
| **Tecla** | EnableCheckForUpdatesButton |
| **Tipo de dados** | Booliano |
| **Valores possíveis** | True (padrão) <br/> Falso |


### <a name="disable-insider-checkbox"></a>Desabilitar a caixa de seleção Insider

Definir como true para tornar o "Ingressar no Programa Office Insider..." caixa de seleção indisponível/esvazada para os usuários.

|Section|Valor|
|:--|:--|
| **Domínio** | com.microsoft.autoupdate2 |
| **Tecla** | DisableInsiderCheckbox |
| **Tipo de dados** | Booliano |
| **Valores possíveis** | False (padrão) <br/> Verdadeiro |


### <a name="limit-the-telemetry-that-is-sent-from-mau"></a>Limitar a telemetria enviada do MAU

De definida como false para enviar dados mínimos de pulsação, sem uso de aplicativo e sem detalhes do ambiente.

|Section|Valor|
|:--|:--|
| **Domínio** | com.microsoft.autoupdate2 |
| **Tecla** | SendAllTelemetryEnabled |
| **Tipo de dados** | Booliano |
| **Valores possíveis** | True (padrão) <br/> Falso |


## <a name="example-configuration-profile"></a>Exemplo de perfil de configuração

O seguinte perfil de configuração é usado para:
- Colocar o dispositivo no canal Beta
- Baixar e instalar atualizações automaticamente
- Habilitar o botão "Verificar atualizações" na interface do usuário
- Permitir que os usuários no dispositivo se inscrevam nos canais Insider

### <a name="jamf"></a>JAMF

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>ChannelName</key>
    <string>Beta</string>
    <key>HowToCheck</key>
    <string>AutomaticDownload</string>
    <key>EnableCheckForUpdatesButton</key>
    <true/>
    <key>DisableInsiderCheckbox</key>
    <false/>
    <key>SendAllTelemetryEnabled</key>
    <true/>
</dict>
</plist>
```

### <a name="intune"></a>Intune

```XML
<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1">
    <dict>
        <key>PayloadUUID</key>
        <string>B762FF60-6ACB-4A72-9E72-459D00C936F3</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>com.microsoft.autoupdate2</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft AutoUpdate settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft AutoUpdate configuration settings</string>
        <key>PayloadVersion</key>
        <integer>1</integer>
        <key>PayloadEnabled</key>
        <true/>
        <key>PayloadRemovalDisallowed</key>
        <true/>
        <key>PayloadScope</key>
        <string>System</string>
        <key>PayloadContent</key>
        <array>
            <dict>
            <key>PayloadUUID</key>
            <string>5A6F350A-CC2C-440B-A074-68E3F34EBAE9</string>
            <key>PayloadType</key>
            <string>com.microsoft.autoupdate2</string>
            <key>PayloadOrganization</key>
            <string>Microsoft</string>
            <key>PayloadIdentifier</key>
            <string>com.microsoft.autoupdate2</string>
            <key>PayloadDisplayName</key>
            <string>Microsoft AutoUpdate configuration settings</string>
            <key>PayloadDescription</key>
            <string/>
            <key>PayloadVersion</key>
            <integer>1</integer>
            <key>PayloadEnabled</key>
            <true/>
            <key>ChannelName</key>
            <string>Beta</string>
            <key>HowToCheck</key>
            <string>AutomaticDownload</string>
            <key>EnableCheckForUpdatesButton</key>
            <true/>
            <key>DisableInsiderCheckbox</key>
            <false/>
            <key>SendAllTelemetryEnabled</key>
            <true/>
            </dict>
        </array>
    </dict>
</plist>
```

Para configurar o MAU, você pode implantar esse perfil de configuração a partir da ferramenta de gerenciamento que sua empresa está usando:
- No JAMF, carregue esse perfil de configuração e de definir o Domínio de Preferência *como com.microsoft.autoupdate2*.
- No Intune, carregue esse perfil de configuração e defina o nome do perfil de configuração personalizado *como com.microsoft.autoupdate2*.

## <a name="resources"></a>Recursos

- [referência msupdate](https://docs.microsoft.com/deployoffice/mac/update-office-for-mac-using-msupdate)
