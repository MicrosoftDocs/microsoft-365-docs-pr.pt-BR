---
title: Microsoft Defender para Ponto de Extremidade em recursos Linux
ms.reviewer: ''
description: Descreve os recursos do Microsoft Defender para Ponto de Extremidade no Linux, incluindo como desinstalar, como coletar logs de diagnóstico, comandos CLI e problemas conhecidos com o produto.
keywords: microsoft, defender, Microsoft Defender for Endpoint, linux, installation, deploy, uninstallation, puppet, ansible, linux, redhat, ubuntu, debian, sles, suse, centos
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 176ee89c8d60a1515855296e2565f0649f908a33
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933320"
---
# <a name="resources"></a>Recursos

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="collect-diagnostic-information"></a>Coletar informações de diagnóstico

Se você puder reproduzir um problema, primeiro aumente o nível de registro em log, execute o sistema por algum tempo e restaure o nível de registro em log como padrão.

1. Aumentar o nível de registro em log:

   ```bash
   mdatp log level set --level debug
   ```

   ```Output
   Log level configured successfully
   ```

2. Reproduza o problema.

3. Execute o seguinte comando para fazer o back-up do Defender para logs do Endpoint. Os arquivos serão armazenados dentro de um arquivo .zip.

   ```bash
   sudo mdatp diagnostic create
   ```

    Esse comando também imprimirá o caminho do arquivo para o backup depois que a operação for bem-sucedida:

   ```Output
   Diagnostic file created: <path to file>
   ```

4. Restaurar o nível de registro em log:

   ```bash
   mdatp log level set --level info
   ```
   ```Output
   Log level configured successfully
   ```

## <a name="log-installation-issues"></a>Problemas de instalação de log

Se ocorrer um erro durante a instalação, o instalador relatará apenas uma falha geral.

O log detalhado será salvo em `/var/log/microsoft/mdatp_install.log` . Se você tiver problemas durante a instalação, envie-nos esse arquivo para que possamos ajudar a diagnosticar a causa.

## <a name="uninstall"></a>Uninstall

Há várias maneiras de desinstalar o Defender para o Ponto de Extremidade no Linux. Se você estiver usando uma ferramenta de configuração como o Puppet, siga as instruções de desinstalação do pacote para a ferramenta de configuração.

### <a name="manual-uninstallation"></a>Desinstalação manual

- `sudo yum remove mdatp` para o RHEL e variantes(CentOS e Oracle Linux).
- `sudo zypper remove mdatp` para SLES e variantes.
- `sudo apt-get purge mdatp` para sistemas Ubuntu e Debian.

## <a name="configure-from-the-command-line"></a>Configurar a partir da linha de comando

Tarefas importantes, como controlar as configurações do produto e disparar verificações sob demanda, podem ser feitas a partir da linha de comando.

### <a name="global-options"></a>Opções globais

Por padrão, a ferramenta de linha de comando resulta no formato aceitável para humanos. Além disso, a ferramenta também dá suporte à saída do resultado como JSON, que é útil para cenários de automação. Para alterar a saída para JSON, passe `--output json` para qualquer um dos comandos abaixo.

### <a name="supported-commands"></a>Comandos com suporte

A tabela a seguir lista comandos para alguns dos cenários mais comuns. Execute `mdatp help` a partir do Terminal para exibir a lista completa de comandos com suporte.

|Group                 |Cenário                                                |Comando                                                                |
|----------------------|--------------------------------------------------------|-----------------------------------------------------------------------|
|Configuração         |Ativar/desativar a proteção em tempo real                        |`mdatp config real-time-protection --value [enabled\|disabled]`        |
|Configuração         |Ativar/desativar o monitoramento de comportamento                         |`mdatp config behavior-monitoring --value [enabled\|disabled]` 
|Configuração         |Ativar/desativar a proteção de nuvem                            |`mdatp config cloud --value [enabled\|disabled]`                       |
|Configuração         |Ativar/desativar diagnósticos de produto                         |`mdatp config cloud-diagnostic --value [enabled\|disabled]`            |
|Configuração         |Ativar/desativar envio automático de exemplo                 |`mdatp config cloud-automatic-sample-submission [enabled\|disabled]`   |
|Configuração         |Ativar/desativar o modo passivo AV                             |`mdatp config passive-mode --value [enabled\|disabled]`                |
|Configuração         |Adicionar/remover uma exclusão de antivírus para uma extensão de arquivo  |`mdatp exclusion extension [add\|remove] --name [extension]`           |
|Configuração         |Adicionar/remover uma exclusão de antivírus para um arquivo            |`mdatp exclusion file [add\|remove] --path [path-to-file]`             |
|Configuração         |Adicionar/remover uma exclusão de antivírus para um diretório       |`mdatp exclusion folder [add\|remove] --path [path-to-directory]`      |
|Configuração         |Adicionar/remover uma exclusão de antivírus para um processo         |`mdatp exclusion process [add\|remove] --path [path-to-process]`<br/>`mdatp exclusion process [add\|remove] --name [process-name]` |
|Configuração         |Listar todas as exclusões de antivírus                           |`mdatp exclusion list`                                                 |
|Configuração         |Adicionar um nome de ameaça à lista permitida                   |`mdatp threat allowed add --name [threat-name]`                        |
|Configuração         |Remover um nome de ameaça da lista permitida              |`mdatp threat allowed remove --name [threat-name]`                     |
|Configuração         |Listar todos os nomes de ameaça permitidos                           |`mdatp threat allowed list`                                            |
|Configuração         |Ativar a proteção pua                                  |`mdatp threat policy set --type potentially_unwanted_application --action block` |
|Configuração         |Desativar a proteção PUA                                 |`mdatp threat policy set --type potentially_unwanted_application --action off` |
|Configuração         |Ativar o modo de auditoria para proteção pua                   |`mdatp threat policy set --type potentially_unwanted_application --action audit` |
|Diagnóstico           |Alterar o nível de log                                    |`mdatp log level set --level verbose [error|warning|info|verbose]`     |
|Diagnóstico           |Gerar logs de diagnóstico                                |`mdatp diagnostic create --path [directory]`                           |
|Integridade                |Verificar a saúde do produto                              |`mdatp health`                                                         |
|Proteção            |Examinar um caminho                                             |`mdatp scan custom --path [path] [--ignore-exclusions]`                |
|Proteção            |Fazer uma verificação rápida                                         |`mdatp scan quick`                                                     |
|Proteção            |Fazer uma verificação completa                                          |`mdatp scan full`                                                      |
|Proteção            |Cancelar uma verificação contínua sob demanda                        |`mdatp scan cancel`                                                    |
|Proteção            |Solicitar uma atualização de inteligência de segurança                  |`mdatp definitions update`                                             |
|Histórico de proteção    |Imprimir o histórico de proteção completo                       |`mdatp threat list`                                                    |
|Histórico de proteção    |Obter detalhes da ameaça                                      |`mdatp threat get --id [threat-id]`                                    |
|Gerenciamento de quarentena |Listar todos os arquivos em quarentena                              |`mdatp threat quarantine list`                                         |
|Gerenciamento de quarentena |Remover todos os arquivos da quarentena                    |`mdatp threat quarantine remove-all`                                   |
|Gerenciamento de quarentena |Adicionar um arquivo detectado como uma ameaça à quarentena       |`mdatp threat quarantine add --id [threat-id]`                         |
|Gerenciamento de quarentena |Remover um arquivo detectado como uma ameaça da quarentena  |`mdatp threat quarantine remove --id [threat-id]`                      |
|Gerenciamento de quarentena |Restaurar um arquivo da quarentena                      |`mdatp threat quarantine restore --id [threat-id]`                     |
|Detecção e resposta do ponto de extremidade |Definir visualização antecipada (nãousada)                    |`mdatp edr early-preview [enable|disable]`                             |
|Detecção e resposta do ponto de extremidade |Definir id de grupo                                  |`mdatp edr group-ids --group-id [group-id]`                            |
|Detecção e resposta do ponto de extremidade |Marca Set/Remove, com `GROUP` suporte apenas        |`mdatp edr tag set --name GROUP --value [tag]`                         |
|Detecção e resposta do ponto de extremidade |exclusões de lista (raiz)                        |`mdatp edr exclusion list [processes|paths|extensions|all]`            |

## <a name="microsoft-defender-for-endpoint-portal-information"></a>Informações do portal do Microsoft Defender para Ponto de Extremidade

No portal Defender para Ponto de Extremidade, você verá duas categorias de informações:

- Alertas antivírus, incluindo:
  - Severity
  - Tipo de verificação
  - Informações do dispositivo (nome do host, identificador de dispositivo, identificador de locatário, versão do aplicativo e tipo de sistema operacional)
  - Informações do arquivo (nome, caminho, tamanho e hash)
  - Informações sobre ameaças (nome, tipo e estado)
- Informações do dispositivo, incluindo:
  - Identificador de dispositivo
  - Identificador de locatário
  - Versão do Aplicativo
  - Nome do host
  - Tipo de sistema operacional
  - Versão do sistema operacional
  - Modelo de computador
  - Arquitetura do processador
  - Se o dispositivo é uma máquina virtual

### <a name="known-issues"></a>Problemas conhecidos

- Você pode ver "Sem dados do sensor, comunicações prejudicadas" na página de informações do computador do portal do Centro de Segurança do Microsoft Defender, mesmo que o produto está funcionando conforme esperado. Estamos trabalhando para resolver esse problema.
- Usuários conectados não aparecem no portal do Centro de Segurança do Microsoft Defender.
- Em distribuições SUSE, se a instalação de *liúndice1* falhar, você deve validar que seu sistema operacional está registrado:

   ```bash
   sudo SUSEConnect --status-text
   ```
