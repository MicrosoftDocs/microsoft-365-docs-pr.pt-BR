---
title: Criar regras de detecção personalizadas no Microsoft Defender ATP
ms.reviewer: ''
description: Saiba como criar regras de detecção personalizadas com base em consultas de busca avançadas
keywords: detecções personalizadas, criar, gerenciar, alertas, editar, executar sob demanda, frequência, intervalo, regras de detecção, busca avançada, busca, consulta, ações de resposta, mdatp, microsoft defender atp
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 09/20/2020
ms.technology: mde
ms.openlocfilehash: 48b1f1bf9506acc8491887fca49295d5e4ccbd69
ms.sourcegitcommit: ef98b8a18d275e5b5961e63d2b0743d046321737
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/26/2021
ms.locfileid: "51382704"
---
# <a name="create-custom-detection-rules"></a>Criar regras de detecção personalizadas

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

As regras de [](advanced-hunting-overview.md) detecção personalizadas criadas a partir de consultas avançadas de busca permitem monitorar proativamente vários eventos e estados do sistema, incluindo atividades suspeitas de violação e dispositivos configurados incorretamente. Você pode defini-los para executar em intervalos regulares, gerando alertas e tomando ações de resposta sempre que houver corresponde.

Leia este artigo para saber como criar novas regras de detecção personalizadas. Ou [consulte exibindo e gerenciando regras existentes.](custom-detections-manage.md)

> [!NOTE]
> Para criar ou gerenciar detecções personalizadas, [sua função](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group) precisa ter a permissão **gerenciar configurações de** segurança.

## <a name="1-prepare-the-query"></a>1. Preparar a consulta.

No Centro de Segurança do Microsoft Defender, vá para **Busca** Avançada e selecione uma consulta existente ou crie uma nova consulta. Ao usar uma nova consulta, execute a consulta para identificar erros e compreender possíveis resultados.

>[!IMPORTANT]
>Para impedir que o serviço retorne alertas demais, cada regra é limitada à geração de apenas 100 alertas sempre que ele é executado. Antes de criar uma regra, ajuste sua consulta para evitar alertas para atividades normais do dia a dia.

### <a name="required-columns-in-the-query-results"></a>Colunas necessárias nos resultados da consulta

Para usar uma consulta para uma regra de detecção personalizada, a consulta deve retornar as seguintes colunas:

- `Timestamp`
- `DeviceId`
- `ReportId`

Consultas simples, como aquelas que não usam o operador ou para personalizar ou agregar resultados, normalmente `project` `summarize` retornam essas colunas comuns.

Há várias maneiras de garantir que consultas mais complexas retornem essas colunas. Por exemplo, se você preferir agregar e contar por , ainda poderá retornar e consegui-los do evento mais recente envolvendo `DeviceId` `Timestamp` cada `ReportId` dispositivo.

A consulta de exemplo a seguir conta o número de dispositivos exclusivos ( ) com detecções antivírus e usa isso para encontrar apenas os dispositivos com mais de `DeviceId` cinco detecções. Para retornar o mais `Timestamp` recente e o correspondente , ele usa o operador com a `ReportId` `summarize` `arg_max` função.

```kusto
DeviceEvents
| where Timestamp > ago(7d)
| where ActionType == "AntivirusDetection"
| summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count() by DeviceId
| where count_ > 5
```

> [!TIP]
> Para melhorar o desempenho da consulta, de definir um filtro de tempo que corresponde à frequência de execução pretendido para a regra. Como a duração menos frequente é a cada 24 horas, a filtragem do último dia abrangerá todos os novos dados.

## <a name="2-create-a-new-rule-and-provide-alert-details"></a>2. Crie uma nova regra e forneça detalhes de alerta.

Com a consulta no editor de consulta, selecione **Criar regra de** detecção e especifique os seguintes detalhes de alerta:

- **Nome da detecção**— nome da regra de detecção
- **Frequência**— intervalo para executar a consulta e executar a ação. [Consulte orientações adicionais abaixo](#rule-frequency)
- **Título do** alerta — título exibido com alertas disparados pela regra
- **Severidade**— risco potencial do componente ou atividade identificado pela regra. [Ler sobre gravidades de alerta](alerts-queue.md#severity)
- **Categoria**— tipo de componente ou atividade de ameaça, se for o caso. [Ler sobre categorias de alerta](alerts-queue.md#understanding-alert-categories)
- **O MITRE ATT&** técnicas de CK — uma ou mais técnicas de ataque identificadas pela regra como documentadas na estrutura de CK do MITRE ATT&CK. Esta seção não está disponível com determinadas categorias de alerta, como malware, ransomware, atividade suspeita e software indesejado
- **Descrição**— mais informações sobre o componente ou atividade identificada pela regra 
- **Ações recomendadas**— ações adicionais que os respondentes podem tomar em resposta a um alerta

Para obter mais informações sobre como os detalhes do alerta são exibidos, [leia sobre a fila de alertas](alerts-queue.md).

### <a name="rule-frequency"></a>Frequência de regra

Quando salva, uma nova regra de detecção personalizada é imediatamente executado e verifica se há combinações dos últimos 30 dias de dados. Em seguida, a regra é executado novamente em intervalos fixos e durações de retorno com base na frequência escolhida:

- **A cada 24 horas**— é executado a cada 24 horas, verificando dados dos últimos 30 dias
- **A cada 12 horas**— é executado a cada 12 horas, verificando dados das últimas 24 horas
- **A cada 3 horas**— é executado a cada 3 horas, verificando dados das últimas 6 horas
- **A cada hora**— é executado por hora, verificando dados das últimas 2 horas

Quando você editar uma regra, ela será executado com as alterações aplicadas no próximo tempo de executar agendado de acordo com a frequência definida.


> [!TIP]
> Match the time filters in your query with the lookback duration. Os resultados fora da duração do retorno de pesquisa são ignorados.

Selecione a frequência que corresponde à proximidade com que você deseja monitorar detecções e considere a capacidade da sua organização de responder aos alertas.

## <a name="3-choose-the-impacted-entities"></a>3. Escolha as entidades impactadas.

Identifique as colunas nos resultados da consulta onde você espera encontrar a entidade principal afetada ou afetada. Por exemplo, uma consulta pode retornar IDs de dispositivo e de usuário. Identificar qual dessas colunas representa a entidade principal impactada ajuda o serviço a agregar alertas relevantes, correlacionar incidentes e ações de resposta de destino.

Você pode selecionar apenas uma coluna para cada tipo de entidade. As colunas que não são retornadas pela consulta não podem ser selecionadas.

## <a name="4-specify-actions"></a>4. Especifique ações.

Sua regra de detecção personalizada pode tomar ações automaticamente em arquivos ou dispositivos retornados pela consulta.

### <a name="actions-on-devices"></a>Ações em dispositivos

Essas ações são aplicadas a dispositivos na `DeviceId` coluna dos resultados da consulta:

- **Isolar dispositivo** aplica isolamento total de rede, impedindo que o dispositivo se conecte a qualquer aplicativo ou serviço, exceto para o serviço Defender para Ponto de Extremidade. [Saiba mais sobre isolamento de dispositivos](respond-machine-alerts.md#isolate-devices-from-the-network)
- **Coletar pacote de investigação**— coleta informações do dispositivo em um arquivo ZIP. [Saiba mais sobre o pacote de investigação](respond-machine-alerts.md#collect-investigation-package-from-devices)
- **Executar a verificação antivírus** executa uma verificação completa do Microsoft Defender Antivírus no dispositivo
- **Iniciar investigação**— inicia [uma investigação](automated-investigations.md) automatizada no dispositivo
- **Restringir a execução de** aplicativos define restrições no dispositivo para permitir que apenas arquivos assinados com um certificado emitido pela Microsoft sejam executados. [Saiba mais sobre como restringir a execução de aplicativos](respond-machine-alerts.md#restrict-app-execution)

### <a name="actions-on-files"></a>Ações em arquivos

Essas ações são aplicadas a arquivos na coluna ou nos `SHA1` `InitiatingProcessSHA1` resultados da consulta:

- **Allow/Block**— adiciona automaticamente [](manage-indicators.md) o arquivo à sua lista de indicadores personalizados para que ele sempre seja permitido para ser executado ou impedido de ser executado. Você pode definir o escopo dessa ação para que ela seja tomada somente em grupos de dispositivos selecionados. Esse escopo é independente do escopo da regra.
- **Arquivo de quarentena**— exclui o arquivo de seu local atual e coloca uma cópia em quarentena

### <a name="actions-on-users"></a>Ações em usuários

- **Marcar o usuário como comprometido** define o nível de risco do usuário como "alto" no Azure Active Directory, disparando as políticas de proteção de identidade [correspondentes.](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection#risk-levels)

## <a name="5-set-the-rule-scope"></a>5. De definir o escopo da regra.

De definir o escopo para especificar quais dispositivos são abordados pela regra:

- Todos os dispositivos
- Grupos de dispositivos específicos

Somente os dados de dispositivos no escopo serão consultados. Além disso, as ações serão realizadas somente nesses dispositivos.

## <a name="6-review-and-turn-on-the-rule"></a>6. Revise e a turn on the rule.

Depois de revisar a regra, selecione **Criar** para salvá-la. A regra de detecção personalizada é imediatamente executado. Ele é executado novamente com base na frequência configurada para verificar se há resultados, gerar alertas e tomar ações de resposta.

Você pode [exibir e gerenciar regras de detecção personalizadas,](custom-detections-manage.md)verificar suas versões anteriores e revisar os alertas disparados. Você também pode executar uma regra sob demanda e modificá-la.

## <a name="related-topics"></a>Tópicos relacionados

- [Exibir e gerenciar regras de detecção personalizadas](custom-detections-manage.md)
- [Visão geral de detecções personalizadas](overview-custom-detections.md)
- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Conhecer a linguagem de consulta de busca avançada](advanced-hunting-query-language.md)
- [Exibir e organizar alertas](alerts-queue.md)
