---
title: Relatório de & dispositivo - Central de segurança
description: Descreve como você pode manter seus dispositivos seguros, atualizados e possíveis ameaças em sua organização
keywords: segurança, malware, Microsoft 365, M365, centro de segurança, monitorar, relatório, dispositivos
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: b9580f904f9cc5043fa3e825007339ce66daaa72
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930493"
---
# <a name="device-monitoring-and-reporting-in-the-microsoft-365-security-center"></a>Monitoramento e relatório de dispositivos no centro de segurança do Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


Mantenha seus dispositivos seguros, atualizados e possíveis ameaças na central de segurança do Microsoft 365.

## <a name="view-device-alerts"></a>Exibir alertas de dispositivo

Receba alertas atualizados sobre atividades de violação e outras ameaças em seus dispositivos do Microsoft Defender para Ponto de Extremidade (disponível com uma licença E5). O centro de segurança do Microsoft 365 monitora efetivamente esses alertas em um alto nível usando seu fluxo de trabalho preferido.

### <a name="monitor-high-impact-alerts"></a>Monitorar alertas de alto impacto

Cada alerta do Microsoft Defender para Ponto de Extremidade tem uma gravidade correspondente (alta, média, baixa ou informacional). Isso indica um possível impacto em sua rede, caso não seja autônoma.  

Use o **cartão de severidade de alerta** do dispositivo para se concentrar especificamente em alertas que são mais graves e podem exigir resposta imediata. Neste cartão, você pode exibir mais informações no portal da Central de Segurança do Microsoft Defender.

![Cartão de gravidade de alertas de dispositivo](../../media/device-alerts-severity.png)

### <a name="understand-sources-of-alerts"></a>Compreender as fontes de alertas

O Microsoft Defender para Ponto de Extremidade aproveita os dados de uma ampla variedade de sensores de segurança e fontes de inteligência para gerar alertas. Por exemplo, ele pode usar informações de detecção do Microsoft Defender Antivírus e antimalware de terceiros. Ele também pode usar sua própria inteligência de ameaça personalizada fornecida por meio da API do serviço Web.

O **cartão de fontes de detecção** de alerta do dispositivo mostra a distribuição de alertas por origem. Acompanhe as atividades relacionadas a determinadas fontes, especialmente suas fontes personalizadas. Você também pode usar o cartão para se concentrar em alertas provenientes de sensores que não estão configurados para bloquear automaticamente atividades ou componentes mal-intencionados.

![Cartão de fontes de detecção de alerta de dispositivo](../../media/device-alert-detection-sources.png)

Neste cartão, você pode exibir mais informações no portal da Central de Segurança do Microsoft Defender.

### <a name="understand-the-types-of-threats-that-trigger-alerts"></a>Compreender os tipos de ameaças que disparam alertas

O Microsoft Defender para Ponto de Extremidade classifica cada alerta em uma categoria que representa um determinado estágio na cadeia de ataque ou tipo de componente de ameaça. Por exemplo, uma atividade de ameaça detectada pode ser categorizada como "movimento lateral" para indicar que houve uma tentativa de alcançar outros dispositivos na rede. A atividade provavelmente ocorreu após os invasores ganharem um rodapé inicial. Quando detectado, um componente de ameaça pode ser amplamente classificado como malware ou especificamente como um tipo de ameaça específico. As especificidades incluem ransomware, roubo de credenciais ou outros tipos de software mal-intencionado ou indesejado.

O **cartão de categorias de ameaças** do dispositivo mostra a distribuição de alertas nessas categorias. Use essas informações para identificar a atividade de ameaças, como tentativas de roubo de credenciais, que geralmente têm um impacto maior do que as tentativas de engenharia social. Você também pode monitorar ameaças potencialmente destrutivas, como ransomware.

![Cartão de categorias de ameaças do dispositivo](../../media/device-threat-categories.png)

### <a name="monitor-active-alerts"></a>Monitorar alertas ativos

O **cartão de status do alerta** do dispositivo indica o número de alertas que não foram resolvidos e podem exigir atenção. Neste cartão, você pode exibir mais informações no portal da Central de Segurança do Microsoft Defender.

![Cartão de status do alerta do dispositivo](../../media/device-alert-status.png)

### <a name="monitor-classification-of-resolved-alerts"></a>Monitorar a classificação de alertas resolvidos

Ao resolver um alerta do Microsoft Defender para Ponto de Extremidade, sua equipe de segurança pode especificar se um alerta foi verificado como:

* Um alerta verdadeiro que identifica a atividade de violação real ou os componentes de ameaças
* Um alerta falso que detectou incorretamente a atividade normal

O **cartão de classificação de alerta** do dispositivo mostra se os alertas resolvidos foram classificados como alertas verdadeiros ou falsos. Neste cartão, você pode exibir mais informações no portal da Central de Segurança do Microsoft Defender.

Observação: em alguns casos, as informações de classificação não estão disponíveis para determinados alertas.

![Cartão de classificação de alerta do dispositivo](../../media/device-alert-classification.png)

### <a name="monitor-determination-of-resolved-alerts"></a>Monitorar a determinação de alertas resolvidos

Além de classificar se um alerta é verdadeiro ou falso durante a resolução, sua equipe de segurança pode fornecer uma determinação. Uma determinação indica o tipo de atividade normal ou mal-intencionada encontrada durante a validação do alerta.

O **cartão de determinação do alerta** do dispositivo mostra a determinação fornecida para cada alerta.

* **APT**: ameaça persistente avançada, indicando que a atividade detectada ou componente de ameaça faz parte de uma violação sofisticada projetada para obter um rodapé na rede afetada  
* **Malware**: arquivo ou código mal-intencionado
* **Equipe de segurança:** atividade normal executada pela equipe de segurança
* **Teste de segurança:** atividade ou componentes projetados para simular ameaças reais e esperado acionar sensores de segurança e gerar alertas
* **Software indesejado:** aplicativos e outros softwares que não são considerados mal-intencionados, mas que violam a política ou padrões de uso aceitável
* **Outros:** qualquer outra determinação que não se enquadra nos tipos fornecidos

Neste cartão, você pode exibir mais informações na Central de Segurança do Microsoft Defender.

![Cartão de determinação do alerta do dispositivo](../../media/device-alert-determination.png)

### <a name="understand-which-devices-are-at-risk"></a>Entender quais dispositivos estão em risco

**A proteção de** dispositivo mostra o nível de risco para dispositivos. O nível de risco é baseado em fatores como o tipo e a gravidade dos alertas no dispositivo.

![Cartão de proteção do dispositivo](../../media/device-protection.png)

## <a name="monitor-and-report-status-of-intune-managed-devices"></a>Monitorar e relatar o status de dispositivos gerenciados pelo Intune

Os relatórios a seguir contêm dados de dispositivos inscritos no Intune. Os dados de dispositivos não conectados não estão incluídos. Somente administradores globais podem exibir esses cartões.

Os dados de dispositivos inscritos no Intune incluem:

* Conformidade do dispositivo
* Dispositivos com malware ativo
* Tipos de malware em dispositivos
* Malware em dispositivos
* Dispositivos com detecções de malware
* Usuários com detecções de malware

### <a name="monitor-device-compliance"></a>Monitorar a conformidade do dispositivo

**A conformidade do** dispositivo mostra quantos dispositivos estão inscritos no Intune estão em conformidade com as políticas de configuração.

![Cartão de conformidade do dispositivo](../../media/device-compliance.png)

### <a name="discover-devices-with-malware-detections"></a>Descobrir dispositivos com detecções de malware

**As detecções de malware de** dispositivo fornecem o número de dispositivos inscritos no Intune com malware que não foram totalmente resolvidos. A falta de resolução pode ser devido a ações pendentes, uma reinicialização, uma verificação completa, ações manuais do usuário ou se a ação de correção não foi concluída com êxito.

![Cartão de detecções de malware do dispositivo](../../media/device-malware-detections.png)

### <a name="understand-the-types-of-malware-detected"></a>Compreender os tipos de malware detectados

**Os tipos de malware em dispositivos** mostram diferentes tipos de malware que foram detectados em dispositivos inscritos no Intune. Você pode investigar cada tipo no centro de segurança do Microsoft 365.

![Tipos de malware no cartão de dispositivos](../../media/types-of-malware-on-devices.png)

### <a name="understand-the-specific-malware-detected-on-your-devices"></a>Entenda o malware específico detectado em seus dispositivos

**Malware em dispositivos** fornece uma lista do malware específico detectado em seus dispositivos.

![Cartão de malware em dispositivos](../../media/malware-on-devices.png)

### <a name="understand-which-devices-have-the-most-malware"></a>Entender quais dispositivos têm mais malware

**Dispositivos com detecções de malware** mostram quais dispositivos têm mais detecções de malware. no centro de segurança do Microsoft 365, você pode investigar se o malware está ativo, quem usa o dispositivo e seu status de gerenciamento no Intune.

![Dispositivos com cartão de detecções de malware](../../media/devices-with-malware-detections.png)

### <a name="understand-which-users-have-devices-with-the-most-malware"></a>Entender quais usuários têm dispositivos com mais malware

**Os usuários com detecções de malware** mostram os usuários com dispositivos que tiveram a maioria das detecções de malware. Na central de segurança do Microsoft 365, você pode ver quantos dispositivos estão atribuídos a cada usuário e mais informações sobre cada dispositivo e o tipo de malware.

![Usuários com cartão de detecção de malware](../../media/users-with-malware-detections.png)

## <a name="monitor-and-manage-attack-surface-reduction-rule-deployment-and-detections"></a>Monitorar e gerenciar detecções e implantação de regras de redução de superfície de ataque

As regras de Redução de Superfície de Ataque [(ASR)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction) ajudam a evitar ações e aplicativos que normalmente são usados por malware em busca de exploração para infectar dispositivos. Essas regras controlam quando e como os executáveis podem ser executados. Por exemplo, você pode impedir que o JavaScript ou o VBScript inicializem um item executável baixado, bloqueie chamadas de API do Win32 recebidas de macros do Office ou bloqueie processos executados em unidades USB.

![Cartão de reduções de superfície de ataque](../../media/attack-surface-reduction-rules.png)

O cartão de **Regras de redução de superfície de ataque** fornece uma visão geral da implantação de regras nos seus dispositivos.

A barra superior do cartão mostra o número total de dispositivos que estão nos seguintes modos de implantação:

* **Modo de bloqueio:** dispositivos com pelo menos uma regra configurada para bloquear a atividade detectada
* **Modo de** auditoria: dispositivos sem regras definidas para bloquear atividade detectada, mas tem pelo menos uma regra definida para auditar a atividade detectada  
* **Desligado:** dispositivos com todas as regras ASR desligadas

A parte inferior do cartão mostra as configurações da regra em todos os seus dispositivos. Cada barra indica o número de dispositivos definidos para bloquear, detectar auditoria ou ter a regra completamente desligada.

### <a name="view-asr-detections"></a>Exibir detecções de ASR

Para exibir informações **detalhadas** sobre detecções de regra ASR em sua rede, selecione Exibir detecções no cartão de regras de **Redução de superfície de** ataque. A **guia Detecções** na página de relatório detalhado será aberta.

![Guia Detecções](../../media/detections-tab.png)

O gráfico na parte superior da página mostra detecções ao longo do tempo empilhando detecções que foram bloqueadas ou auditadas. A tabela na parte inferior lista as detecções mais recentes. Confira as seguintes informações na tabela para entender a natureza das detecções:

* **Arquivo detectado:** o arquivo, normalmente um script ou documento, cujo conteúdo disparou a atividade suspeita de ataque
* **Regra**: nome que descreve as atividades de ataque que a regra foi projetada para capturar. Ler sobre regras ASR existentes
* **Aplicativo de** origem : o aplicativo que carregou ou executou conteúdo disparando a atividade suspeita de ataque. Pode ser um aplicativo legítimo, como um navegador da Web, um aplicativo do Office ou uma ferramenta do sistema, como o PowerShell
* **Fornecedor**: o fornecedor que lançou o aplicativo de origem

### <a name="review-device-asr-rule-settings"></a>Revisar as configurações de regra ASR do dispositivo

Na página **Relatório de regras de Redução de superfície** de ataque, vá para a guia Configuração para revisar as configurações de regra para dispositivos individuais.  Selecione um dispositivo para obter informações detalhadas sobre se cada regra está no modo de bloqueio, no modo de auditoria ou totalmente desligada.

![Guia Configuração](../../media/configuration-tab.png)

O Microsoft Intune fornece funcionalidade de gerenciamento para suas regras asR. Se você quiser atualizar suas configurações,  selecione **Começar** em Configurar dispositivos na guia para abrir o gerenciamento de dispositivos no Intune.

### <a name="exclude-files-from-asr-rules"></a>Excluir arquivos de regras ASR

O centro de segurança do Microsoft 365 coleta os nomes dos arquivos que talvez você queira excluir das detecções pelas regras de redução de superfície de ataque. [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/enable-attack-surface-reduction#exclude-files-and-folders-from-asr-rules) Ao excluir arquivos, você pode reduzir detecções de falsos positivos e implantar com mais confiança regras de redução de superfície de ataque no modo de bloqueio.

As exclusões são gerenciadas no Microsoft Intune, mas o centro de segurança do Microsoft 365 fornece uma ferramenta de análise para ajudá-lo a entender os arquivos. Para começar a coletar arquivos para exclusão, vá para a **guia Adicionar exclusões** na página relatório de regras de **Redução de superfície de** ataque.

>[!NOTE]  
>A ferramenta analisa detecções por todas as regras de redução de superfície de ataque, mas [apenas algumas regras suportam exclusões.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-asr)

![Guia Adicionar exclusões](../../media/add-exclusions-tab.png)

A tabela lista todos os nomes de arquivo detectados pelas regras de redução de superfície de ataque. Você pode selecionar arquivos para revisar o impacto de excluí-los:

* Quantas detecções menos
* Quantos menos dispositivos relatam as detecções

Para obter uma lista dos arquivos selecionados com seus caminhos completos para exclusão, selecione **Obter caminhos de exclusão.**

Logs para a regra ASR Bloquear roubo de credenciais do subsistema de autoridade de segurança **local do Windows (lsass.exe)** capturam o aplicativo de origem **lsass.exe**. É um arquivo normal do sistema, mas capturado como o arquivo detectado. Como resultado, a lista gerada de caminhos de exclusão incluirá esse arquivo. Para excluir o arquivo que disparou essa regra em vez **delsass.exe**, use o caminho para o aplicativo de origem em vez do arquivo detectado.

Para localizar o aplicativo de [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting) origem, execute a seguinte consulta de busca avançada para esta regra específica (identificada pela regra ID 9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2):

```kusto
DeviceEvents
| where Timestamp > ago(7d)
| where ActionType startswith "Asr"
| where AdditionalFields contains "9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2"
| project InitiatingProcessFolderPath, InitiatingProcessFileName
```

#### <a name="check-files-for-exclusion"></a>Verificar arquivos para exclusão

Antes de excluir um arquivo do ASR, recomendamos que você inspecione o arquivo para determinar se ele realmente não é mal-intencionado.

Para revisar um arquivo, use a página [de informações do arquivo](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-files) na Central de Segurança do Microsoft Defender. A página fornece informações de prevalência e a taxa de detecção de antivírus VirusTotal. Você também pode usar a página para enviar o arquivo para uma análise profunda.

Para localizar um arquivo detectado na Central de Segurança do Microsoft Defender, procure todas as detecções de ASR usando a seguinte consulta de busca avançada:

```kusto
MiscEvents
| where EventTime > ago(7d)
| where ActionType startswith "Asr"
| project FolderPath, FileName, SHA1, InitiatingProcessFolderPath, InitiatingProcessFileName, InitiatingProcessSHA1
```

Use **SHA1 ou** **InitiatingProcessSHA1** nos resultados para pesquisar o arquivo usando a barra de pesquisa universal na Central de Segurança do Microsoft Defender.
