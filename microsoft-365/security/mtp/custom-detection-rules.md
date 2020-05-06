---
title: Criar e gerenciar regras de detecção personalizadas no Microsoft Threat Protection
description: Saiba como criar e gerenciar regras de detecções personalizadas com base em consultas de busca avançada
keywords: caça avançada, busca de ameaças, caça à Cyber Threat, proteção contra ameaças da Microsoft, Microsoft 365, MTP, M365, pesquisa, consulta, telemetria, detecções personalizadas, regras, esquema, Kusto, Microsoft 365, proteção contra ameaças da Microsoft, RBAC, permissões, Microsoft defender ATP
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: cdfc23f34d90c9d725ec6fb314728553a987c025
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034859"
---
# <a name="create-and-manage-custom-detections-rules"></a>Criar e gerenciar regras de detecções personalizadas

**Aplica-se a:**
- Proteção contra Ameaças da Microsoft

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Regras de detecção personalizadas criadas a partir de consultas de [busca avançada](advanced-hunting-overview.md) permitem monitorar proativamente vários eventos e Estados do sistema, incluindo a suspeita de falha na atividade e os pontos de extremidade configurados incorretamente. Você pode defini-los para executar em intervalos regulares, gerar alertas e realizar ações de resposta sempre que houver correspondências.

## <a name="required-permissions-for-managing-custom-detections"></a>Permissões necessárias para o gerenciamento de detecções personalizadas

Para gerenciar detecções personalizadas, você precisa ter uma destas funções:

- **Administrador** de segurança — a função Administrador de segurança ou administrador de segurança é uma [função do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) para gerenciar várias configurações de segurança no centro de segurança do Microsoft 365 e vários portais e serviços.

- **Operador de segurança** — a função do operador de segurança é uma [função do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) para gerenciar alertas e tem acesso global somente leitura em recursos relacionados à segurança, incluindo todas as informações no centro de segurança do Microsoft 365. Essa função é suficiente para gerenciar detecções personalizadas somente se o controle de acesso baseado em função (RBAC) estiver desativado no Microsoft defender ATP. Se o RBAC estiver configurado, você também precisará da permissão **gerenciar configurações de segurança** para o Microsoft defender ATP.

Para gerenciar as permissões necessárias, um **administrador global** pode fazer o seguinte:

- Atribua a função de **administrador de segurança** ou **operador de segurança** no [centro de administração do Microsoft 365](https://admin.microsoft.com/) em **funções** > **administrador de segurança**.
- Verifique as configurações RBAC do Microsoft defender ATP [na central de segurança do Microsoft defender](https://securitycenter.windows.com/) em**funções**de**permissões** > de **configurações** > . Selecione a função correspondente para atribuir a permissão **gerenciar configurações de segurança** .

> [!NOTE]
> Para gerenciar detecções personalizadas, os **operadores de segurança** precisarão da permissão **gerenciar configurações de segurança** no Microsoft defender ATP se o RBAC estiver ativado.

## <a name="create-a-custom-detection-rule"></a>Criar uma regra de detecção personalizada
### <a name="1-prepare-the-query"></a>1. Prepare a consulta.

No centro de segurança do Microsoft 365, vá para a **busca avançada** e selecione uma consulta existente ou crie uma nova consulta. Ao usar uma nova consulta, execute a consulta para identificar erros e compreender possíveis resultados.

#### <a name="required-columns-in-the-query-results"></a>Colunas obrigatórias nos resultados da consulta
Para criar uma regra de detecção personalizada, a consulta deve retornar as seguintes colunas:

- `Timestamp`
- Uma das seguintes colunas de dispositivo, usuário ou caixa de correio:
    - `DeviceId`
    - `DeviceName`
    - `RemoteDeviceName`
    - `RecipientEmailAddress`
    - `SenderFromAddress`(remetente de envelope ou endereço do caminho de retorno)
    - `SenderMailFromAddress`(endereço do remetente exibido pelo cliente de email)
    - `RecipientObjectId`
    - `AccountSid`
    - `InitiatingProcessAccountSid`
    - `InitiatingProcessAccountUpn`
    - `InitiatingProcessAccountObjectId`
>[!NOTE]
>O suporte para entidades adicionais será adicionado à medida que novas tabelas forem adicionadas ao [esquema de busca avançada](advanced-hunting-schema-tables.md).

Consultas simples, como as que não usam o `project` operador or `summarize` para personalizar ou agregar resultados, normalmente retornam essas colunas comuns.

Há várias maneiras de garantir que consultas mais complexas retornem essas colunas. Por exemplo, se você preferir agregar e contar por entidade em uma coluna como `DeviceId`, você ainda pode retornar `Timestamp` ao obtê-lo do evento mais recente envolvendo cada exclusivo. `DeviceId`

A consulta de exemplo abaixo conta o número de máquinas exclusivas (`DeviceId`) com detecções de antivírus e usa essa contagem para localizar apenas as máquinas com mais de cinco detecções. Para retornar o mais `Timestamp`recente, ele usa `summarize` o operador com `arg_max` a função.

```kusto
DeviceEvents
| where Timestamp > ago(7d)
| where ActionType == "AntivirusDetection"
| summarize Timestamp = max(Timestamp), count() by DeviceId
| where count_ > 5
```
### <a name="2-create-new-rule-and-provide-alert-details"></a>2. Crie uma nova regra e forneça detalhes do alerta.

Com a consulta no editor de consultas, selecione **criar regra de detecção** e especifique os seguintes detalhes de alerta:

- **Nome da detecção** — nome da regra de detecção
- **Frequência** – intervalo para executar a consulta e executar a ação. [Veja orientações adicionais abaixo](#rule-frequency)
- **Título do alerta** — título exibido com alertas disparados pela regra
- **Severidade** — risco potencial do componente ou atividade identificado pela regra
- **Categoria** — componente de ameaça ou atividade identificada pela regra
- **Mitre ATT&Reck Techniques** — uma ou mais técnicas de ataque identificadas pela regra conforme documentadas na [estrutura Mitre ATT&CK](https://attack.mitre.org/)
- **Descrição** — mais informações sobre o componente ou atividade identificada pela regra 
- **Ações recomendadas** — ações adicionais que os respondentes podem executar em resposta a um alerta

#### <a name="rule-frequency"></a>Frequência da regra
Quando salvo, uma regra de detecção personalizada nova ou editada é executada imediatamente e verifica se há correspondências dos últimos 30 dias de dados. A regra então é executada novamente em intervalos fixos e durações de lookback com base na frequência que você escolher:

- A **cada 24 horas** — é executado a cada 24 horas, verificando os dados dos últimos 30 dias
- A **cada 12 horas** — é executado a cada 12 horas, verificando os dados das últimas 24 horas
- A **cada 3 horas** — é executado a cada 3 horas, verificando os dados das últimas 6 horas
- A **cada hora** — é executado a cada hora, verificando os dados das últimas 2 horas

Selecione a frequência que corresponde à aparência que você deseja monitorar as detecções e considere a capacidade da sua organização para responder aos alertas.

### <a name="3-choose-the-impacted-entities"></a>3. escolha as entidades impactadas.
Identifique as colunas nos resultados de consulta onde você espera encontrar a entidade principal afetada ou afetada. Por exemplo, uma consulta pode retornar endereços de`SenderFromAddress` remetente `SenderMailFromAddress`(ou) e`RecipientEmailAddress`destinatário (). Identificar quais dessas colunas representam a principal entidade afetada ajuda o serviço a agregar alertas relevantes, correlacionar incidentes e ações de resposta de destino.

Você pode selecionar apenas uma coluna para cada tipo de entidade (caixa de correio, usuário ou dispositivo). As colunas que não são retornadas pela consulta não podem ser selecionadas.

### <a name="4-specify-actions-on-files-or-machines"></a>4. Especifique ações em arquivos ou máquinas.
Sua regra de detecção personalizada pode executar automaticamente ações em arquivos ou máquinas que são retornadas pela consulta.

#### <a name="actions-on-machines"></a>Ações em máquinas
Essas ações são aplicadas às máquinas na `DeviceId` coluna dos resultados da consulta:
- **Isolate Machine** — usa o Microsoft defender ATP para aplicar o isolamento completo da rede, impedindo o computador de se conectar a qualquer aplicativo ou serviço. [Saiba mais sobre o isolamento de máquina ATP do Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-machines-from-the-network)
- **Coletar pacote de investigação** — coleta informações de máquina em um arquivo zip. [Saiba mais sobre o pacote de investigação ATP do Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-machines)
- **Executar verificação antivírus** — realiza uma verificação completa do Windows Defender antivírus na máquina
- **Iniciar investigação** — inicia uma [investigação automatizada](mtp-autoir.md) no computador

#### <a name="actions-on-files"></a>Ações em arquivos
Quando selecionada, a ação de **arquivo de quarentena** é executada nos arquivos da `SHA1`coluna `InitiatingProcessSHA1`, `SHA256`, ou `InitiatingProcessSHA256` dos resultados da consulta. Esta ação exclui o arquivo de seu local atual e coloca uma cópia em quarentena.

> [!NOTE]
> A ação de permissão ou bloqueio para regras de detecção personalizada atualmente não é suportada no Microsoft Threat Protection.

### <a name="5-set-the-rule-scope"></a>5. defina o escopo da regra.
Defina o escopo para especificar quais dispositivos são cobertos pela regra. O escopo influencia as regras que verificam dispositivos e não afetam as regras que verificam apenas caixas de correio e contas de usuário e identidades.

Ao configurar o escopo, você pode selecionar:

- Todos os dispositivos
- Grupos de dispositivos específicos

Somente os dados de dispositivos no escopo serão consultados. Além disso, as ações serão executadas apenas nesses dispositivos.

### <a name="6-review-and-turn-on-the-rule"></a>6. revise e ative a regra.
Após a revisão da regra, clique em **criar** para salvá-la. A regra de detecção personalizada é executada imediatamente. Ele é executado novamente com base na frequência configurada para verificar correspondências, gerar alertas e realizar ações de resposta.

## <a name="manage-existing-custom-detection-rules"></a>Gerenciar regras de detecção personalizadas existentes
Você pode exibir a lista de regras de detecção personalizadas existentes, verificar suas execuções anteriores e revisar os alertas que eles acionaram. Você também pode executar uma regra por demanda e modificá-la.

### <a name="view-existing-rules"></a>Exibir regras existentes

Para exibir todas as regras de detecção personalizadas existentes, navegue até **buscar** > **detecções personalizadas**. A página lista todas as regras com as seguintes informações de execução:

- **Última execução** — quando uma regra foi executada pela última vez para verificar correspondências de consulta e gerar alertas
- **Status da última execução** — se uma regra foi executada com êxito
- **Próxima execução** : a próxima execução agendada
- **Status** — se uma regra foi ativada ou desativada

### <a name="view-rule-details-modify-rule-and-run-rule"></a>Exibir detalhes da regra, modificar regra e executar regra

Para exibir informações abrangentes sobre uma regra de detecção personalizada, selecione o nome da regra na lista de regras em**detecções personalizadas**de **busca** > . Isso abre uma página sobre a regra de detecção personalizada com informações gerais sobre a regra, incluindo os detalhes do alerta, o status de execução e o escopo. Também fornece a lista de alertas disparados e ações disparadas.

![Página de detalhes da regra de detecção personalizada](../../media/custom-detection-details.png)<br>
*Detalhes da regra de detecção personalizada*

Você também pode executar as seguintes ações na regra nesta página:

- **Executar** — execute a regra imediatamente. Isso também redefine o intervalo para a próxima execução.
- **Editar** — modificar a regra sem alterar a consulta
- **Modificar consulta** — editar a consulta em busca avançada
- **Ativar**desativar, habilitar a regra ou impedir que ela seja executada**Turn off**  / 
- **Excluir** — desativar a regra e removê-la

### <a name="view-and-manage-triggered-alerts"></a>Exibir e gerenciar alertas disparados

Na tela detalhes da regra (**busca** > de**detecções** > personalizadas **[nome da regra]**), acesse **alertas** disparados para exibir a lista de alertas gerados por correspondências com a regra. Selecione um alerta para exibir informações detalhadas sobre esse alerta e realizar as seguintes ações no alerta:

- Gerenciar o alerta definindo seu status e classificação (alerta verdadeiro ou falso)
- Vincular o alerta a um incidente
- Executar a consulta que disparou o alerta na busca avançada

### <a name="review-actions"></a>Ações de revisão
Na tela detalhes da regra (**busca** > de**detecções** > personalizadas **[nome da regra]**), vá para **ações** disparadas para exibir a lista de ações executadas com base em correspondências com a regra.

>[!TIP]
>Para exibir rapidamente as informações e executar ações em um item em uma tabela, use a coluna seleção [&#10003;] à esquerda da tabela.

## <a name="related-topic"></a>Tópico relacionado
- [Visão geral de detecções personalizadas](custom-detections-overview.md)
- [Visão geral da caça avançada](advanced-hunting-overview.md)
- [Conhecer a linguagem de consulta de busca avançada](advanced-hunting-query-language.md)
