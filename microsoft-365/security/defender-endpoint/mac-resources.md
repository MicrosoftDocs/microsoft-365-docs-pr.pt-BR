---
title: Recursos para o Microsoft Defender para Ponto de Extremidade no Mac
description: Recursos para o Microsoft Defender para Ponto de Extremidade no Mac, incluindo como desinstalar, como coletar logs de diagnóstico, comandos CLI e problemas conhecidos com o produto.
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, installation, deploy, uninstallation, intune, jamf, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: fa5d5b4470644e1ff50af46a8dd3f035cd9b3184
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842861"
---
# <a name="resources-for-microsoft-defender-for-endpoint-on-macos"></a>Recursos para o Microsoft Defender para Ponto de Extremidade no macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="collecting-diagnostic-information"></a>Coletando informações de diagnóstico

Se você puder reproduzir um problema, aumente o nível de registro em log, execute o sistema por algum tempo e restaure o nível de log para o padrão.

1. Aumentar o nível de registro em log:

   ```bash
   mdatp log level set --level verbose
   ```

   ```Output
   Log level configured successfully
   ```

2. Reproduzir o problema

3. Execute `sudo mdatp diagnostic create` para fazer o back up dos logs do Microsoft Defender para Pontos de Extremidade. Os arquivos serão armazenados dentro de um arquivo .zip arquivo morto. Esse comando também imprimirá o caminho do arquivo para o backup depois que a operação for bem-sucedida.

   > [!TIP]
   > Por padrão, os logs de diagnóstico são salvos em `/Library/Application Support/Microsoft/Defender/wdavdiag/` . Para alterar o diretório onde os logs de diagnóstico são salvos, passe para o `--path [directory]` comando abaixo, substituindo `[directory]` pelo diretório desejado.

   ```bash
   sudo mdatp diagnostic create
   ```

   ```console
   Diagnostic file created: "/Library/Application Support/Microsoft/Defender/wdavdiag/932e68a8-8f2e-4ad0-a7f2-65eb97c0de01.zip"
   ```

4. Restaurar o nível de registro em log:

   ```bash
   mdatp log level set --level info
   ```

   ```console
   Log level configured successfully
   ```

## <a name="logging-installation-issues"></a>Problemas de instalação de log

Se ocorrer um erro durante a instalação, o instalador relatará apenas uma falha geral.

O log detalhado será salvo em `/Library/Logs/Microsoft/mdatp/install.log` . Se você tiver problemas durante a instalação, envie-nos esse arquivo para que possamos ajudar a diagnosticar a causa.

## <a name="uninstalling"></a>Desinstalação

Há várias maneiras de desinstalar o Microsoft Defender para o Ponto de Extremidade no macOS. Observe que, embora a desinstalação gerenciada centralmente está disponível no JAMF, ela ainda não está disponível para Microsoft Intune.

### <a name="interactive-uninstallation"></a>Desinstalação interativa

- Abra **o Finder > Aplicativos**. Clique com o botão direito do **mouse no Microsoft Defender para Endpoint > Mover para Lixo**.

### <a name="from-the-command-line"></a>Da linha de comando

- ```sudo '/Library/Application Support/Microsoft/Defender/uninstall/uninstall'```

## <a name="configuring-from-the-command-line"></a>Configurando a partir da linha de comando

Tarefas importantes, como controlar as configurações do produto e disparar verificações sob demanda, podem ser feitas a partir da linha de comando:

|Group        |Cenário                                   |Comando                                                                           |
|-------------|-------------------------------------------|----------------------------------------------------------------------------------|
|Configuração|Ativar/desativar a proteção em tempo real           |`mdatp config real-time-protection --value [enabled/disabled]`                    |
|Configuração|Ativar/desativar a proteção de nuvem               |`mdatp config cloud --value [enabled/disabled]`                                   |
|Configuração|Ativar/desativar diagnósticos de produto            |`mdatp config cloud-diagnostic --value [enabled/disabled]`                        |
|Configuração|Ativar/desativar envio automático de exemplo    |`mdatp config cloud-automatic-sample-submission --value [enabled/disabled]`       |
|Configuração|Adicionar um nome de ameaça à lista permitida      |`mdatp threat allowed add --name [threat-name]`                                   |
|Configuração|Remover um nome de ameaça da lista permitida |`mdatp threat allowed remove --name [threat-name]`                                |
|Configuração|Listar todos os nomes de ameaça permitidos              |`mdatp threat allowed list`                                                       |
|Configuração|Ativar a proteção pua                     |`mdatp threat policy set --type potentially_unwanted_application -- action block` |
|Configuração|Desativar a proteção PUA                    |`mdatp threat policy set --type potentially_unwanted_application -- action off`   |
|Configuração|Ativar o modo de auditoria para proteção pua      |`mdatp threat policy set --type potentially_unwanted_application -- action audit` |
|Configuração|Ativar/desativar passiveMode                    |`mdatp config passive-mode --value enabled [enabled/disabled]`                    |
|Diagnostics  |Alterar o nível de log                       |`mdatp log level set --level [error/warning/info/verbose]`                        |
|Diagnostics  |Gerar logs de diagnóstico                   |`mdatp diagnostic create --path [directory]`                                      |
|Integridade       |Verificar a saúde do produto                 |`mdatp health`                                                                    |
|Integridade       |Verifique se há um atributo de produto esefico       |`mdatp health --field [attribute: healthy/licensed/engine_version...]`            |
|Proteção   |Examinar um caminho                                |`mdatp scan custom --path [path] [--ignore-exclusions]`                           |
|Proteção   |Fazer uma verificação rápida                            |`mdatp scan quick`                                                                |
|Proteção   |Fazer uma verificação completa                             |`mdatp scan full`                                                                 |
|Proteção   |Cancelar uma verificação contínua sob demanda           |`mdatp scan cancel`                                                               |
|Proteção   |Solicitar uma atualização de inteligência de segurança     |`mdatp definitions update`                                                        |
|EDR          |Adicione a marca de grupo ao dispositivo. EDR marcas são usadas para gerenciar grupos de dispositivos. Para obter mais informações, visite /microsoft-365/security/defender-endpoint/machine-groups |`mdatp edr tag set --name GROUP --value [name]` |
|EDR          |Remover a marca de grupo do dispositivo               |`mdatp edr tag remove --tag-name [name]`                                          |
|EDR          |Adicionar ID de Grupo                               |`mdatp edr group-ids --group-id [group]`                                          |

### <a name="how-to-enable-autocompletion"></a>Como habilitar a comcompleção automática

Para habilitar a comcompleção automática em bash, execute o seguinte comando e reinicie a sessão terminal:

```bash
echo "source /Applications/Microsoft\ Defender\ ATP.app/Contents/Resources/Tools/mdatp_completion.bash" >> ~/.bash_profile
```

Para habilitar a comcompleção automática em zsh:

- Verifique se a comcompleção automática está habilitada em seu dispositivo:

   ```zsh
   cat ~/.zshrc | grep autoload
   ```

- Se o comando anterior não produzir nenhuma saída, você poderá habilitar a comcompleção automática usando o seguinte comando:

   ```zsh
   echo "autoload -Uz compinit && compinit" >> ~/.zshrc
   ```

- Execute os seguintes comandos para habilitar a composição automática do Microsoft Defender para Ponto de Extremidade no macOS e reinicie a sessão terminal:

   ```zsh
   sudo mkdir -p /usr/local/share/zsh/site-functions
   ```
   ```zsh
   sudo ln -svf "/Applications/Microsoft Defender ATP.app/Contents/Resources/Tools/mdatp_completion.zsh" /usr/local/share/zsh/site-functions/_mdatp
   ```

## <a name="client-microsoft-defender-for-endpoint-quarantine-directory"></a>Diretório de quarentena do Microsoft Defender para Ponto de Extremidade cliente

`/Library/Application Support/Microsoft/Defender/quarantine/` contém os arquivos em quarentena por `mdatp` . Os arquivos são nomeados após o trackingId de ameaças. Os trackingIds atuais são mostrados com `mdatp threat list` .

## <a name="microsoft-defender-for-endpoint-portal-information"></a>Informações do portal do Microsoft Defender para Ponto de Extremidade

EDR recursos para [macOS](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/edr-capabilities-for-macos-have-now-arrived/ba-p/1047801)chegaram , no blog do Microsoft Defender para Ponto de Extremidade, fornece orientações detalhadas sobre o que esperar no Centro de Segurança do Microsoft Defender para Ponto de Extremidade.
