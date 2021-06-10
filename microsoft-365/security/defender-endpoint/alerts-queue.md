---
title: Exibir e organizar a fila de alertas do Microsoft Defender for Endpoint
description: Saiba como funcionam as filas de alertas do Microsoft Defender para Ponto de Extremidade e como classificar e filtrar listas de alertas.
keywords: alertas, filas, filas de alertas, classificação, ordem, filtro, gerenciar alertas, novos, em andamento, resolvidos, mais novos, tempo na fila, gravidade, período de tempo, alertas de especialistas em ameaças da Microsoft
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 03/27/2020
ms.technology: mde
ms.openlocfilehash: 48a3ff8dba5bccd62d7d43b295c136a814056a15
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934328"
---
# <a name="view-and-organize-the-microsoft-defender-for-endpoint-alerts-queue"></a>Exibir e organizar a fila de alertas do Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)

>Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-alertsq-abovefoldlink) 

A **fila Alertas** mostra uma lista de alertas que foram sinalizados de dispositivos em sua rede. Por padrão, a fila exibe alertas vistos nos últimos 30 dias em um modo de exibição agrupado. Os alertas mais recentes são mostrados na parte superior da lista, ajudando você a ver os alertas mais recentes primeiro.

> [!NOTE]
> A fila de alertas é significativamente reduzida com investigação e correção automatizadas, permitindo que especialistas em operações de segurança se concentrem em ameaças mais sofisticadas e em outras iniciativas de alto valor. Quando um alerta contém uma entidade com suporte para investigação automatizada (por exemplo, um arquivo) em um dispositivo com um sistema operacional com suporte para ele, uma investigação e correção automatizadas podem começar. Para obter mais informações sobre investigações automatizadas, consulte [Overview of Automated investigations](automated-investigations.md).

Há várias opções que você pode escolher para personalizar o exibição de fila de alertas. 

Na navegação superior, você pode:

- Selecionar exibição agrupada ou exibição de lista
- Personalizar colunas para adicionar ou remover colunas 
- Selecione os itens a mostrar por página
- Navegar entre páginas
- Aplicar filtros

![Imagem da fila de alertas](images/alerts-queue-list.png)

## <a name="sort-filter-and-group-the-alerts-queue"></a>Classificar, filtrar e agrupar a fila de alertas

Você pode aplicar os filtros a seguir para limitar a lista de alertas e obter uma exibição mais focada dos alertas.

### <a name="severity"></a>Severity

Gravidade do alerta | Descrição
:---|:---
Alto </br>(Vermelho) | Alertas comumente vistos associados a ameaças persistentes avançadas (APT). Esses alertas indicam um alto risco devido à gravidade dos danos que podem causar em dispositivos. Alguns exemplos são: atividades de ferramentas de roubo de credenciais, atividades de ransomware não associadas a nenhum grupo, adulteração de sensores de segurança ou atividades mal-intencionadas indicando um adversário humano.
Médio </br>(Laranja) | Alertas de detecção e resposta de ponto de extremidade comportamentos pós-violação que podem fazer parte de uma ameaça persistente avançada (APT). Isso inclui comportamentos observados típicos de estágios de ataque, alteração anômala do registro, execução de arquivos suspeitos e assim por diante. Embora alguns possam fazer parte de testes internos de segurança, ele requer investigação, pois também pode fazer parte de um ataque avançado.
Baixo </br>(Amarelo) | Alertas sobre ameaças associadas ao malware predominante. Por exemplo, ferramentas de hack, ferramentas de hack não malware, como a execução de comandos de exploração, a limpeza de logs, etc., que muitas vezes não indicam uma ameaça avançada visando a organização. Ele também pode vir de um teste de ferramenta de segurança isolado por um usuário em sua organização.
Informativo </br>(Cinza) | Alertas que podem não ser considerados prejudiciais para a rede, mas podem impulsionar a conscientização de segurança organizacional sobre possíveis problemas de segurança.

#### <a name="understanding-alert-severity"></a>Noções básicas sobre a gravidade do alerta

Microsoft Defender Antivírus (Microsoft Defender AV) e gravidades de alerta do Defender for Endpoint são diferentes porque representam escopos diferentes.

A gravidade da ameaça av do Microsoft Defender representa a gravidade absoluta da ameaça detectada (malware) e é atribuída com base no risco potencial para o dispositivo individual, se infectado.

A gravidade do alerta do Defender para Ponto de Extremidade representa a gravidade do comportamento detectado, o risco real para o dispositivo, mas, mais importante, o risco potencial para a organização.

Portanto, por exemplo:

- A gravidade de um alerta do Defender for Endpoint sobre uma ameaça detectada pelo Microsoft Defender AV que foi totalmente impedida e não infectou o dispositivo é categorizada como "Informacional" porque não houve danos reais.
- Um alerta sobre um malware comercial foi detectado durante a execução, mas bloqueado e remediado pelo Microsoft Defender AV, é categorizado como "Baixo" porque pode ter causado alguns danos ao dispositivo individual, mas não representa nenhuma ameaça organizacional.
- Um alerta sobre malware detectado durante a execução que pode representar uma ameaça não apenas para o dispositivo individual, mas para a organização, independentemente se ele foi bloqueado eventualmente, pode ser classificado como "Médio" ou "Alto".
- Alertas comportamentais suspeitos, que não foram bloqueados ou remediados, serão classificados como "Baixo", "Médio" ou "Alto" seguindo as mesmas considerações de ameaça organizacional.

#### <a name="understanding-alert-categories"></a>Noções básicas sobre categorias de alerta

Redefinimos as categorias de alerta [](https://attack.mitre.org/tactics/enterprise/) para alinhar às táticas de ataque empresariais na matriz de [CK mitre att&CK](https://attack.mitre.org/). Novos nomes de categoria se aplicam a todos os novos alertas. Os alertas existentes manterão os nomes de categorias anteriores.

A tabela abaixo lista as categorias atuais e como elas geralmente mapeiam para categorias anteriores. 

| Nova categoria       | Nome da categoria da API   | Atividade ou componente de ameaça detectado                                                                                                 |
|----------------------|---------------------|-----------------------------------------------------------------------------------------------------------------------------------------|
| Coleção           | Coleção          | Localizando e coletando dados para exfiltração                                                                                         |
| Comando e controle  | CommandAndControl   | Conectar-se à infraestrutura de rede controlada pelo invasor para retransmitir dados ou receber comandos                                          |
| Acesso a credenciais    | CredentialAccess    | Obtendo credenciais válidas para estender o controle sobre dispositivos e outros recursos na rede                                       |
| Evasão de defesa      | DefenseEvasion      | Evitando controles de segurança, por exemplo, desligando aplicativos de segurança, excluindo implantes e executando rootkits                        |
| Descoberta            | Descoberta           | Coletando informações sobre dispositivos e recursos importantes, como computadores administradores, controladores de domínio e servidores de arquivos  |
| Execução            | Execução           | Iniciando ferramentas de invasor e código mal-intencionado, incluindo RATs e backdoors                                                             |
| Exfiltração         | Exfiltração        | Extrair dados da rede para um local externo controlado pelo invasor                                                         |
| Exploit              | Exploit             | Explorar o código e a possível atividade de exploração                                                                                       |
| Acesso inicial       | InitialAccess       | Obter entrada inicial na rede de destino, geralmente envolvendo a adivinhação de senha, explorações ou emails de phishing                      |
| Movimento lateral     | LateralMovement     | Mover-se entre dispositivos na rede de destino para alcançar recursos críticos ou obter persistência de rede                                |
| Malware              | Malware             | Backdoors, trojans e outros tipos de código mal-intencionado                                                                                 |
| Persistência          | Persistência         | Criando pontos de extensibilidade de início automático (ASEPs) para permanecer ativo e sobreviver a reinicializações do sistema                                        |
| Escalonamento de privilégios | PrivilegeEscalation | Obtendo níveis de permissão mais altos para código executando-o no contexto de um processo privilegiado ou conta                         |
| Ransomware           | Ransomware          | Malware que criptografa arquivos e extortas pagamento para restaurar o acesso                                                                     |
| Atividade Suspeita  | SuspiciousActivity  | Atividade atípica que pode ser atividade de malware ou parte de um ataque                                                                 |
| Software indesejado    | UnwantedSoftware    | Aplicativos e aplicativos de baixa reputação que impactam a produtividade e a experiência do usuário; detectados como aplicativos potencialmente indesejados (PUAs) |

### <a name="status"></a>Status

Você pode optar por limitar a lista de alertas com base em seu status.

### <a name="investigation-state"></a>Estado da investigação

Corresponde ao estado de investigação automatizada.

### <a name="category"></a>Categoria

Você pode optar por filtrar a fila para exibir tipos específicos de atividade mal-intencionada.

### <a name="assigned-to"></a>Atribuído a

Você pode escolher entre mostrar alertas atribuídos a você ou automação.

### <a name="detection-source"></a>Fonte de detecção

Selecione a origem que disparou a detecção de alerta. Especialistas em Ameaças da Microsoft participantes de visualização agora podem filtrar e ver detecções do novo serviço de busca gerenciado por especialistas em ameaças.

>[!NOTE]
>O filtro Antivírus só aparecerá se os dispositivos estão usando Microsoft Defender Antivírus como o produto antimalware de proteção em tempo real padrão.

| Fonte de detecção                  | Valor da API                  |
|-----------------------------------|----------------------------|
| Sensores de terceiros                 | ThirdPartySensors          |
| Antivírus                         | WindowsDefenderAv          |
| Investigação automatizada           | AutomatedInvestigation     |
| Detecção personalizada                  | CustomDetection            |
| TI personalizada                         | CustomerTI                 |
| EDR                               | WindowsDefenderAtp         |
| Microsoft 365 Defender            | MTP                        |
| Microsoft Defender para Office 365 | OfficeATP                  |
| Especialistas em Ameaças da Microsoft          | ThreatExperts              |
| SmartScreen                       | WindowsDefenderSmartScreen |

### <a name="os-platform"></a>Plataforma do sistema operacional

Limite a exibição de fila de alertas selecionando a plataforma do sistema operacional que você está interessado em investigar.

### <a name="device-group"></a>Grupo de dispositivos

Se você tem grupos de dispositivos específicos que você está interessado em verificar, você pode selecionar os grupos para limitar o exibição de fila de alertas. 

### <a name="associated-threat"></a>Ameaça associada

Use esse filtro para se concentrar em alertas relacionados a ameaças de alto perfil. Você pode ver a lista completa de ameaças de alto perfil na [análise de ameaças.](threat-analytics.md)

## <a name="related-topics"></a>Tópicos relacionados

- [Gerenciar alertas do Microsoft Defender para Pontos de Extremidade](manage-alerts.md)
- [Investigar alertas do Microsoft Defender para Pontos de Extremidade](investigate-alerts.md)
- [Investigar um arquivo associado a um alerta do Microsoft Defender para Ponto de Extremidade](investigate-files.md)
- [Investigar dispositivos na lista do Microsoft Defender for Endpoint Devices](investigate-machines.md)
- [Investigar um endereço IP associado a um alerta do Microsoft Defender para Ponto de Extremidade](investigate-ip.md)
- [Investigar um domínio associado a um alerta do Microsoft Defender para Ponto de Extremidade](investigate-domain.md)
- [Investigar uma conta de usuário no Microsoft Defender para Ponto de Extremidade](investigate-user.md)
