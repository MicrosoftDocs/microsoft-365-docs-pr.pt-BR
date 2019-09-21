---
title: Monitoramento de dispositivos e relatórios no centro de segurança do Microsoft 365
description: Descreve como você pode manter seus dispositivos seguros, atualizados e identificar possíveis ameaças em sua organização
keywords: segurança, malware, Microsoft 365, M365, central de segurança, monitor, relatório, dispositivos
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.openlocfilehash: 71bdb350e8e166e9ccd6a303c7ef7bdde943e79c
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37073932"
---
# <a name="device-monitoring-and-reporting-in-microsoft-365-security-center"></a>Monitoramento de dispositivos e relatórios no centro de segurança do Microsoft 365

Mantenha seus dispositivos seguros, atualizados e identifique as possíveis ameaças no centro de segurança do Microsoft 365.

## <a name="view-device-alerts"></a>Exibir alertas de dispositivo

Obtenha alertas atualizados sobre a atividade de violação e outras ameaças em seus dispositivos do Microsoft defender ATP (disponível com uma licença E5). O Microsoft 365 Security Center monitora efetivamente esses alertas em um nível alto usando seu fluxo de trabalho preferido.

### <a name="monitor-high-impact-alerts"></a>Monitorar alertas de alto impacto

Cada alerta ATP do Microsoft defender tem uma severidade correspondente, alta, média, baixa ou informativa — que indica o impacto em potencial para a sua rede, se for deixado autônomo.  

Use o cartão de **severidade de alerta de dispositivo** para se concentrar especificamente nos alertas que são mais graves e podem exigir resposta imediata. Neste cartão, você pode exibir mais informações no portal da central de segurança do Microsoft defender.

![Cartão de severidade de alertas de dispositivo](../media/security-docs/device-alerts-severity.png)

### <a name="understand-sources-of-alerts"></a>Entender fontes de alertas

O Microsoft defender ATP aproveita dados de uma ampla variedade de sensores de segurança e fontes de inteligência para gerar alertas. Por exemplo, ele pode usar informações de detecção do Windows Defender Antivirus e antimalware de terceiros, bem como sua própria inteligência de ameaças personalizada fornecida por meio da API do serviço Web.

O cartão de fontes de **detecção de alerta de dispositivo** mostra a distribuição de alertas por fonte. Este cartão pode ajudá-lo a controlar atividades relacionadas a determinadas fontes, particularmente suas fontes personalizadas. Você também pode usá-lo para se concentrar nos alertas provenientes de sensores que não estão configurados para bloquear automaticamente atividades ou componentes mal-intencionados.

![Cartão de fontes de detecção de alerta de dispositivo](../media/security-docs/device-alert-detection-sources.png)

Neste cartão, você pode exibir mais informações no portal da central de segurança do Microsoft defender.

### <a name="understand-the-types-of-threats-that-trigger-alerts"></a>Compreender os tipos de ameaças que acionam alertas

O Microsoft defender ATP classifica cada alerta em uma categoria que representa um determinado estágio na cadeia de ataque ou um tipo de componente de ameaça. Por exemplo, as atividades de ameaça detectadas podem ser categorizadas em "movimento lateral" para indicar que a atividade envolvia uma tentativa de alcançar outros dispositivos na rede e que provavelmente ocorreu após os invasores terem um incorrido inicial. Quando detectado, um componente de ameaça pode ser classificado amplamente como "malware" ou mais especificamente como "ransomware", "roubo de credenciais" ou outros tipos de softwares mal-intencionados ou indesejados.

O cartão de **categorias de ameaça de dispositivo** mostra a distribuição de alertas nessas categorias. Você pode usar essas informações para identificar a atividade de ameaças, como tentativas de roubo de credenciais, que podem ter um impacto mais significativo em comparação às tentativas da engenharia social, por exemplo. Você também pode usar isso para monitorar ameaças potencialmente destrutivas, como ransomware.

![Cartão de categorias de ameaças de dispositivos](../media/security-docs/device-threat-categories.png)

### <a name="monitor-active-alerts"></a>Monitorar alertas ativos

O cartão de **status de alerta de dispositivo** indica o número de alertas que não foram resolvidos e podem exigir atenção. Neste cartão, você pode exibir mais informações no portal da central de segurança do Microsoft defender.

![Cartão de status de alerta de dispositivos](../media/security-docs/device-alert-status.png)

### <a name="monitor-classification-of-resolved-alerts"></a>Monitorar a classificação de alertas resolvidos

Ao resolver um alerta ATP do Microsoft defender, sua equipe de segurança pode especificar se um alerta foi verificado como:

* Um alerta verdadeiro que identifica atividade de violação real ou componentes de ameaça
* Um alerta falso que foi detectado incorretamente uma atividade normal

O cartão de **classificação de alerta de dispositivo** mostra se seus alertas resolvidos foram classificados como verdadeiros ou falsos alertas. Neste cartão, você pode exibir mais informações no portal da central de segurança do Microsoft defender.

Observação: em alguns casos, as informações de classificação não estão disponíveis para determinados alertas.

![Cartão de classificação de alerta de dispositivo](../media/security-docs/device-alert-classification.png)

### <a name="monitor-determination-of-resolved-alerts"></a>Monitorar a determinação dos alertas resolvidos

Além de classificar se um alerta é verdadeiro ou falso durante a resolução, sua equipe de segurança pode fornecer uma determinação, indicando o tipo de atividade normal ou mal-intencionada encontrada durante a validação do alerta.

O cartão de **determinação de alerta de dispositivo** mostra a determinação oferecida para cada alerta, especificamente:

* **Apt** – ameaça persistente avançada, indicando que a atividade detectada ou o componente de ameaça faz parte de uma violação sofisticada projetada para obter uma brecha na rede afetada  
* **Malware** – arquivo mal-intencionado ou código
* **Equipe de segurança** – atividade normal realizada pela equipe de segurança
* **Teste de segurança** – atividade ou componentes projetados para simular ameaças reais e que devem disparar sensores de segurança e gerar alertas
* **Software indesejado** – aplicativos e outros softwares que não são considerados mal-intencionados, mas que, de outra forma, violam os padrões de política ou de uso aceitáveis
* **Outros** – qualquer outra determinação que não se enquadr nos tipos fornecidos

Neste cartão, você pode exibir mais informações na central de segurança do Microsoft defender.

![Cartão de determinação de alerta do dispositivo](../media/security-docs/device-alert-determination.png)

### <a name="understand-which-devices-are-at-risk"></a>Entender quais dispositivos estão em risco

**Proteção de dispositivo** mostra o nível de risco para dispositivos. O nível de risco é baseado em fatores como o tipo e a gravidade de alertas no dispositivo.

![Cartão de proteção de dispositivos](../media/security-docs/device-protection.png)

## <a name="monitor-and-report-status-of-intune-managed-devices"></a>Monitorar e relatar o status dos dispositivos gerenciados pelo Intune

Os relatórios a seguir contêm dados de dispositivos registrados no Intune. Dados de dispositivos não registrados não estão incluídos. Somente os administradores globais podem exibir esses cartões.

Os dados do dispositivo registrados do Intune incluem:

* Conformidade do dispositivo
* Dispositivos com malware ativo
* Tipos de malware em dispositivos
* Malware em dispositivos
* Dispositivos com detecções de malware
* Usuários com detecções de malware

### <a name="monitor-device-compliance"></a>Monitorar a conformidade do dispositivo

A **conformidade do dispositivo** mostra quantos dispositivos estão registrados no Intune em conformidade com as políticas de configuração.

![Cartão de conformidade do dispositivo](../media/security-docs/device-compliance.png)

### <a name="discover-devices-with-malware-detections"></a>Descobrir dispositivos com detecções de malware

As **detecções de malware de dispositivo** fornecem o número de dispositivos registrados do Intune com malware que não foram totalmente resolvidos devido a ações pendentes, uma reinicialização, uma ação de usuário manual ou de verificação completa, ou se a ação de correção não for concluída com êxito.

![Cartão de detecções de malware de dispositivo](../media/security-docs/device-malware-detections.png)

### <a name="understand-the-types-of-malware-detected"></a>Compreender os tipos de malware detectados

**Tipos de malware em dispositivos** mostra diferentes tipos de malware detectados em dispositivos registrados no Intune. Você pode investigar cada tipo no centro de segurança do Microsoft 365.

![Tipos de malware no cartão de dispositivos](../media/security-docs/types-of-malware-on-devices.png)

### <a name="understand-the-specific-malware-detected-on-your-devices"></a>Entender o malware específico detectado em seus dispositivos

**Malware em dispositivos** fornece uma lista de malware específico detectado em seus dispositivos.

![Placa de malware em dispositivos](../media/security-docs/malware-on-devices.png)

### <a name="understand-which-devices-have-the-most-malware"></a>Entender quais dispositivos têm mais malware

**Dispositivos com detecções de malware** mostram quais dispositivos têm a maior quantidade de detecções de malware. No centro de segurança do Microsoft 365, você pode investigar se o malware está ativo, quem usa o dispositivo e seu status de gerenciamento no Intune.

![Dispositivos com cartão de detecções de malware](../media/security-docs/devices-with-malware-detections.png)

### <a name="understand-which-users-have-devices-with-the-most-malware"></a>Entender quais usuários têm dispositivos com mais malware

**Os usuários com detecções de malware** mostram aos usuários dispositivos com mais detecções de malware. No centro de segurança do Microsoft 365, você pode ver quantos dispositivos são atribuídos a cada usuário e mais informações sobre cada dispositivo e o tipo de malware.

![Usuários com cartão de detecção de malware](../media/security-docs/users-with-malware-detections.png)

## <a name="monitor-and-manage-asr-rule-deployment-and-detections"></a>Monitorar e gerenciar a implantação e as detecções de regras ASR

[As regras de redução da superfície de ataque (ASR)](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard) ajudam a evitar ações e aplicativos normalmente usados por malware de busca de exploração para infectar máquinas. Essas regras controlam quando e como os executáveis podem ser executados. Por exemplo, você pode impedir que JavaScript ou VBScript inicie um executável baixado, bloqueie as chamadas da API Win32 de macros do Office ou bloqueie processos executados a partir de unidades USB.

![Cartão de redução de superfície de ataque](../media/security-docs/attack-surface-reduction-rules.png)

O cartão de **regras de redução da superfície de ataque** fornece uma visão geral da implantação de regras nos seus dispositivos.

A barra superior do cartão mostra o número total de dispositivos que estão nos seguintes modos de implantação:

* **Modo de bloqueio** – dispositivos com pelo menos uma regra configurada para bloquear a atividade detectada
* **Modo de auditoria** – dispositivos sem regras definidas para bloquear a atividade detectada, mas tem pelo menos um conjunto de regras para auditar a atividade detectada  
* **Desligado** – dispositivos com todas as regras ASR desativadas

A parte inferior deste cartão mostra as configurações por regra em seus dispositivos. Cada barra indica o número de dispositivos que estão configurados para bloquear ou auditar a detecção ou a regra completamente desativada.

### <a name="view-asr-detections"></a>Exibir detecções ASR

Para exibir informações detalhadas sobre detecções de regra ASR em sua rede, selecione **Exibir detecções** no cartão de **regras de redução de superfície de ataque** . A guia **detecções** da página relatório detalhado será aberta.

![Guia detecções](../media/security-docs/detections-tab.png)

O gráfico na parte superior da página mostra as detecções com as detecções de empilhamento de tempo que foram bloqueadas ou auditadas. A tabela na parte inferior lista as detecções mais recentes. Use as seguintes informações na tabela para entender a natureza das detecções:

* **Arquivo detectado** – o arquivo, geralmente um script ou um documento, cujo conteúdo disparou a atividade de ataque suspeito
* **Regra** – nome que descreve as atividades de ataque que a regra foi projetada para capturar. Leia sobre regras de ASR existentes
* **Aplicativo de origem** – o aplicativo que carregou ou executou o conteúdo que está disparando a atividade de ataque suspeita. Pode ser um aplicativo legítimo, como navegador da Web, um aplicativo do Office ou uma ferramenta do sistema, como o PowerShell
* **Publisher** – o fornecedor que liberou o aplicativo de origem

### <a name="review-device-asr-rule-settings"></a>Examinar as configurações de regra ASR do dispositivo

Na página relatório de **regras de redução da superfície de ataque** , vá para a guia **configuração** para analisar as configurações de regra para dispositivos individuais. Selecione um dispositivo para obter informações detalhadas sobre se cada regra está no modo de bloqueio, modo de auditoria ou desativada inteiramente.

![Guia Configuração](../media/security-docs/configuration-tab.png)

O Microsoft Intune fornece funcionalidade de gerenciamento para suas regras ASR. Se você quiser atualizar suas configurações, selecione **começar** em **configurar dispositivos** na guia para abrir o gerenciamento de dispositivos no Intune.

### <a name="exclude-files-from-asr-rules"></a>Excluir arquivos de regras ASR

A central de segurança do Microsoft 365 coleta os nomes dos [arquivos que você pode querer excluir](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/troubleshoot-asr#add-exclusions-for-a-false-positive) das detecções por regras de redução de superfície de ataque. Ao excluir arquivos, você pode reduzir as detecções de falsos positivos e implantar com segurança as regras de redução de superfície de ataque no modo de bloqueio.

As exclusões são gerenciadas no Microsoft Intune, mas o centro de segurança do Microsoft 365 oferece uma ferramenta de análise para ajudá-lo a entender os arquivos. Para começar a coletar arquivos para exclusão, vá para a guia **adicionar exclusões** na página relatório de **regras de redução de superfície de ataque** .

>[!NOTE]  
>A ferramenta analisa as detecções por todas as regras de redução da superfície de ataque, mas [apenas algumas regras dão suporte a exclusões](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard#attack-surface-reduction-rules).

![Adicionar guia exclusões](../media/security-docs/add-exclusions-tab.png)

A tabela lista todos os nomes de arquivo detectados por suas regras de redução de superfície de ataque. Você pode selecionar arquivos para revisar o impacto da exclusão deles:

* Quantas detecções menos
* Quantos dispositivos menos relatam as detecções

Para obter uma lista dos arquivos selecionados com seus caminhos completos para exclusão, selecione **obter caminhos de exclusão**.

Os logs para o bloqueio de credenciais de bloqueio de regra ASR **do subsistema de autoridade de segurança local (Lsass. exe) do Windows** capturam o aplicativo de origem **LSASS. exe**, um arquivo de sistema normal, como o arquivo detectado. Como resultado, a lista gerada de caminhos de exclusão incluirá esse arquivo. Para excluir o arquivo que disparou essa regra em vez de **LSASS. exe**, use o caminho para o aplicativo de origem em vez do arquivo detectado.

Para localizar o aplicativo de origem, execute a seguinte [consulta de busca avançada](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting) para esta regra específica (identificada por ID de regra 9e6c4e1f-7d60-472F-ba1a-a39ef669e4b2):

```MiscEvents
| where EventTime > ago(7d)
| where ActionType startswith "Asr"
| where AdditionalFields contains "9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2"
| project InitiatingProcessFolderPath, InitiatingProcessFileName
```

#### <a name="check-files-for-exclusion"></a>Verificar arquivos para exclusão
Antes de excluir um arquivo do ASR, recomendamos inspecionar o arquivo para determinar se ele não é mal-intencionado.

Para revisar um arquivo, use a [página informações do arquivo](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-files) no centro de segurança do Microsoft defender. A página fornece informações de prevalência, bem como a taxa de detecção de antivírus do VirusTotal. Você também pode usar a página para enviar o arquivo para análise profunda.

Para localizar um arquivo detectado no centro de segurança do Microsoft defender, procure todas as detecções de ASR usando a seguinte consulta de busca avançada:

```MiscEvents
| where EventTime > ago(7d)
| where ActionType startswith "Asr"
| project FolderPath, FileName, SHA1, InitiatingProcessFolderPath, InitiatingProcessFileName, InitiatingProcessSHA1
```

Use o **SHA1** ou o **InitiatingProcessSHA1** nos resultados para pesquisar o arquivo usando a barra de pesquisa universal na central de segurança do Microsoft defender.
