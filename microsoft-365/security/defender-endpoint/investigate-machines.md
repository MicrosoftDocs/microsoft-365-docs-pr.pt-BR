---
title: Investigar dispositivos na lista Defender for Endpoint Defender ATP Devices
description: Investigue os dispositivos afetados revisando alertas, informações de conexão de rede, adicionando marcas de dispositivo e grupos e verificando a saúde do serviço.
keywords: devices, tags, groups, endpoint, alerts queue, alerts, device name, domain, last seen, internal IP, active alerts, threat category, filter, sort, review alerts, network, connection, type, password stealer, ransomware, exploit, threat, low severity, service health
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 8873177f13ebe8d60533877fa9b8dc0be96a66f9
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054080"
---
# <a name="investigate-devices-in-the-microsoft-defender-for-endpoint-devices-list"></a>Investigar dispositivos na lista do Microsoft Defender for Endpoint Devices

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatemachines-abovefoldlink)

Investigue os detalhes de um alerta gerado em um dispositivo específico para identificar outros comportamentos ou eventos que possam estar relacionados ao alerta ou ao escopo potencial da violação.

> [!NOTE]
> Como parte do processo de investigação ou resposta, você pode coletar um pacote de investigação de um dispositivo. Veja como: Coletar o pacote [de investigação de dispositivos](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/respond-machine-alerts#collect-investigation-package-from-devices).

Você pode clicar em dispositivos afetados sempre que os vir no portal para abrir um relatório detalhado sobre esse dispositivo. Os dispositivos afetados são identificados nas seguintes áreas:

- [Lista de dispositivos](investigate-machines.md)
- [Fila de alertas](alerts-queue.md)
- [Painel de operações de segurança](security-operations-dashboard.md)
- Qualquer alerta individual
- Qualquer exibição de detalhes de arquivo individual
- Qualquer endereço IP ou exibição de detalhes de domínio

Ao investigar um dispositivo específico, você verá:

- Detalhes do dispositivo
- Ações de resposta
- Guias (visão geral, alertas, linha do tempo, recomendações de segurança, inventário de software, vulnerabilidades descobertas, KBs ausentes)
- Cartões (alertas ativos, usuários conectados, avaliação de segurança)

![Imagem do visualização do dispositivo](images/specific-device.png)

## <a name="device-details"></a>Detalhes do dispositivo

A seção detalhes do dispositivo fornece informações como o domínio, o sistema operacional e o estado de saúde do dispositivo. Se houver um pacote de investigação disponível no dispositivo, você verá um link que permite baixar o pacote.

## <a name="response-actions"></a>Ações de resposta

As ações de resposta são executados ao longo da parte superior de uma página de dispositivo específica e incluem:

- Gerenciar marcas
- Isolar dispositivo
- Restringir a execução do aplicativo
- Executar verificação antivírus
- Coletar pacote de investigação
- Iniciar sessão de resposta ao vivo
- Iniciar investigação automatizada
- Consultar um especialista em ameaças
- Central de ações

Você pode tomar ações de resposta no Centro de Ações, em uma página de dispositivo específica ou em uma página de arquivo específica.

Para obter mais informações sobre como agir em um dispositivo, consulte [Take response action on a device](respond-machine-alerts.md).

Para obter mais informações, consulte [Investigar entidades do usuário](investigate-user.md).

## <a name="tabs"></a>Guias

As guias fornecem informações relevantes de prevenção de ameaças e segurança relacionadas ao dispositivo. Em cada guia, você pode personalizar as colunas mostradas selecionando **Personalizar colunas** da barra acima dos headers da coluna.

### <a name="overview"></a>Visão geral
A **guia Visão** geral exibe os cartões [para](#cards) alertas ativos, conectados aos usuários e avaliação de segurança.

![Imagem da guia visão geral na página do dispositivo](images/overview-device.png)

### <a name="alerts"></a>Alertas

A **guia Alertas** fornece uma lista de alertas associados ao dispositivo. Esta lista é uma versão filtrada da fila de [Alertas](alerts-queue.md)e mostra uma breve descrição do alerta, gravidade (alto, médio, baixo, informacional), status na fila (novo, em andamento, resolvido), classificação (não definido, alerta falso, alerta verdadeiro), estado de investigação, categoria de alerta, quem está abordando o alerta e a última atividade. Você também pode filtrar os alertas.

![Imagem de alertas relacionados ao dispositivo](images/alerts-device.png)

Quando o ícone de círculo à esquerda de um alerta é selecionado, um sub-menu é exibido. Neste painel, você pode gerenciar o alerta e exibir mais detalhes, como número de incidentes e dispositivos relacionados. Vários alertas podem ser selecionados por vez.

Para ver uma exibição de página completa de um alerta, incluindo gráfico de incidentes e árvore de processo, selecione o título do alerta.

### <a name="timeline"></a>Linha do tempo

A **guia Linha** do Tempo fornece uma exibição cronológica dos eventos e alertas associados que foram observados no dispositivo. Isso pode ajudá-lo a correlacionar quaisquer eventos, arquivos e endereços IP em relação ao dispositivo.

A linha do tempo também permite que você faça uma análise seletiva de eventos que ocorreram dentro de um determinado período de tempo. Você pode exibir a sequência temporal de eventos que ocorreram em um dispositivo durante um período de tempo selecionado. Para controlar ainda mais sua exibição, você pode filtrar por grupos de eventos ou personalizar as colunas.

>[!NOTE]
> Para que os eventos de firewall sejam exibidos, você precisará habilitar a política de auditoria, consulte [Audit Filtering Platform connection](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-filtering-platform-connection).
>O firewall abrange os seguintes eventos
>
>- [5025](https://docs.microsoft.com/windows/security/threat-protection/auditing/event-5025) - serviço de firewall interrompido
>- [5031](https://docs.microsoft.com/windows/security/threat-protection/auditing/event-5031) - aplicativo impedido de aceitar conexões de entrada na rede
>- [5157](https://docs.microsoft.com/windows/security/threat-protection/auditing/event-5157) - conexão bloqueada

![Imagem da linha do tempo do dispositivo com eventos](images/timeline-device.png)

Algumas das funcionalidades incluem:

- Pesquisar eventos específicos
  - Use a barra de pesquisa para procurar eventos de linha do tempo específicos.
- Filtrar eventos de uma data específica
  - Selecione o ícone de calendário no canto superior esquerdo da tabela para exibir eventos no último dia, semana, 30 dias ou intervalo personalizado. Por padrão, a linha do tempo do dispositivo é definida para exibir os eventos dos últimos 30 dias.
  - Use a linha do tempo para pular para um momento específico no tempo realçando a seção. As setas na linha do tempo apontam investigações automatizadas
- Exportar eventos de linha do tempo detalhados do dispositivo
  - Exporte a linha do tempo do dispositivo para a data atual ou um intervalo de data especificado até sete dias.

Mais detalhes sobre determinados eventos são fornecidos na **seção Informações** adicionais. Esses detalhes variam dependendo do tipo de evento, por exemplo: 

- Contido pelo Application Guard - o evento do navegador da Web foi restrito por um contêiner isolado
- Ameaça ativa detectada - a detecção de ameaça ocorreu enquanto a ameaça estava em execução
- Correção malsucedida - uma tentativa de correção da ameaça detectada foi invocada, mas falhou
- Correção bem-sucedida - a ameaça detectada foi interrompida e limpa
- Aviso ignorado pelo usuário - o aviso Windows Defender SmartScreen foi ignorado e substituído por um usuário
- Script suspeito detectado - um script potencialmente mal-intencionado foi encontrado em execução
- A categoria de alerta - se o evento levou à geração de um alerta, a categoria de alerta ("Movimento Lateral", por exemplo) é fornecida

#### <a name="event-details"></a>Detalhes do evento
Selecione um evento para exibir detalhes relevantes sobre esse evento. Um painel é exibido para mostrar informações gerais do evento. Quando aplicável e os dados estão disponíveis, um gráfico mostrando entidades relacionadas e suas relações também são mostrados.

Para inspecionar ainda mais o evento e [](advanced-hunting-overview.md) os eventos relacionados, você pode executar rapidamente uma consulta de busca avançada selecionando **Hunt para eventos relacionados.** A consulta retornará o evento selecionado e a lista de outros eventos que ocorreram ao mesmo tempo no mesmo ponto de extremidade.

![Imagem do painel de detalhes do evento](images/event-details.png)

### <a name="security-recommendations"></a>Recomendações de segurança

**As recomendações de segurança** são geradas do Microsoft Defender para o recurso de Gerenciamento de [Vulnerabilidades](tvm-dashboard-insights.md) & Ameaças do Ponto de Extremidade. Selecionar uma recomendação mostrará um painel onde você pode exibir detalhes relevantes, como a descrição da recomendação e os riscos potenciais associados à não decretação. Consulte [Recomendação de segurança](tvm-security-recommendation.md) para obter detalhes.

![Guia De recomendações de segurança](images/security-recommendations-device.png)

### <a name="software-inventory"></a>Inventário de software

A **guia Inventário de** software permite que você veja o software no dispositivo, juntamente com quaisquer pontos fracos ou ameaças. Selecionar o nome do software levará você para a página de detalhes do software onde você pode exibir recomendações de segurança, vulnerabilidades descobertas, dispositivos instalados e distribuição de versão. Consulte [Inventário de software](tvm-software-inventory.md) para obter detalhes

![Imagem da guia inventário de software](images/software-inventory-device.png)

### <a name="discovered-vulnerabilities"></a>Vulnerabilidades descobertas

A **guia Vulnerabilidades Descobertas** mostra o nome, a gravidade e as percepções de ameaça das vulnerabilidades descobertas no dispositivo. Selecionar vulnerabilidades específicas mostrará uma descrição e detalhes.

![Imagem da guia vulnerabilidades descobertas](images/discovered-vulnerabilities-device.png)

### <a name="missing-kbs"></a>KBs ausentes
A **guia KBs ausentes** lista as atualizações de segurança ausentes para o dispositivo.

![Imagem da guia kbs ausente](images/missing-kbs-device.png)

## <a name="cards"></a>Cartões

### <a name="active-alerts"></a>Alertas ativos

O cartão proteção avançada contra ameaças do **Azure** exibirá uma visão geral de alto nível dos alertas relacionados ao dispositivo e seu nível de risco, se você tiver habilitado o recurso ATP do Azure e houver alertas ativos. Mais informações estão disponíveis na sonda "Alertas".

![Imagem do cartão de alertas ativos](images/risk-level-small.png)

>[!NOTE]
>Você precisará habilitar a integração no Azure ATP e no Defender for Endpoint para usar esse recurso. No Defender para Ponto de Extremidade, você pode habilitar esse recurso em recursos avançados. Para obter mais informações sobre como habilitar recursos avançados, consulte [Ativar recursos avançados](advanced-features.md).

### <a name="logged-on-users"></a>Usuários conectados

O **cartão Usuários** Conectados mostra quantos usuários entraram nos últimos 30 dias, juntamente com os usuários mais e menos frequentes. Selecionar o link "Ver todos os usuários" abre o painel de detalhes, que exibe informações como tipo de usuário, tipo de logoff e quando o usuário foi visto pela primeira e última vez. Para obter mais informações, consulte [Investigar entidades do usuário](investigate-user.md).

![Imagem do painel de detalhes do usuário](images/logged-on-users.png)

### <a name="security-assessments"></a>Avaliações de segurança

O **cartão de avaliações de** segurança mostra o nível geral de exposição, recomendações de segurança, software instalado e vulnerabilidades descobertas. O nível de exposição de um dispositivo é determinado pelo impacto acumulado de suas recomendações de segurança pendentes.

![Imagem do cartão de avaliações de segurança](images/security-assessments.png)

## <a name="related-topics"></a>Tópicos relacionados

- [Exibir e organizar a fila de alertas do Microsoft Defender for Endpoint](alerts-queue.md)
- [Gerenciar alertas do Microsoft Defender para Pontos de Extremidade](manage-alerts.md)
- [Investigar alertas do Microsoft Defender para Pontos de Extremidade](investigate-alerts.md)
- [Investigar um arquivo associado a um alerta do Defender para Ponto de Extremidade](investigate-files.md)
- [Investigar um endereço IP associado a um alerta do Defender para Ponto de Extremidade](investigate-ip.md)
- [Investigar um domínio associado a um alerta do Defender para Ponto de Extremidade](investigate-domain.md)
- [Investigar uma conta de usuário no Defender para Ponto de Extremidade](investigate-user.md)
- [Recomendação de segurança](tvm-security-recommendation.md)
- [Inventário de software](tvm-software-inventory.md)
