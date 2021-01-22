---
title: Criar e gerenciar regras de detecção personalizadas no Microsoft 365 Defender
description: Saiba como criar e gerenciar regras de detecções personalizadas com base em consultas de busca avançada
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, proteção contra ameaças da Microsoft, microsoft 365, mtp, m365, pesquisa, consulta, telemetria, detecções personalizadas, regras, esquema, kusto, microsoft 365, Proteção contra Ameaças da Microsoft, RBAC, permissões, Microsoft Defender ATP
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 8c7e47e66f9e5543cc122c5b5154207cae836d2a
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932917"
---
# <a name="create-and-manage-custom-detections-rules"></a>Criar e gerenciar regras de detecções personalizadas

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

Regras de detecção personalizadas são regras que você pode projetar e ajustar usando [consultas de busca](advanced-hunting-overview.md) avançada. Essas regras permitem monitorar proativamente vários eventos e estados do sistema, incluindo atividades suspeitas de violação e pontos de extremidade configurados incorretamente. Você pode defini-los para que sejam executados em intervalos regulares, gerando alertas e tomando ações de resposta sempre que houver resultados.

## <a name="required-permissions-for-managing-custom-detections"></a>Permissões necessárias para gerenciar detecções personalizadas

Para gerenciar detecções personalizadas, você precisa ter uma destas funções atribuídas:

- **Administrador de** segurança — os usuários com essa função [do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) podem gerenciar as configurações de segurança no centro de segurança do Microsoft 365 e em outros portais e serviços.

- **Operador** de segurança — Os usuários com essa função [do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) podem gerenciar alertas e ter acesso global somente leitura a recursos relacionados à segurança, incluindo todas as informações na central de segurança do Microsoft 365. Essa função é suficiente para gerenciar detecções personalizadas somente se o controle de acesso baseado em função (RBAC) estiver desligado no Microsoft Defender para Ponto de Extremidade. Se o RBAC estiver configurado, você também precisará da permissão gerenciar configurações **de** segurança do Defender para Ponto de Extremidade.

Para gerenciar as permissões necessárias, um **administrador global** pode:

- Atribua **a função de administrador de** segurança **ou** operador de segurança no Centro de administração do [Microsoft 365](https://admin.microsoft.com/) sob **o administrador de Segurança** de  >  **Funções.**
- Verifique as configurações do RBAC para o Microsoft Defender para o ponto de extremidade na Central de Segurança do [Microsoft Defender](https://securitycenter.windows.com/) em **Funções** de  >  **Permissões de**  >  **Configurações.** Selecione a função correspondente para atribuir a **permissão gerenciar configurações de** segurança.

> [!NOTE]
> Para gerenciar detecções personalizadas,   os operadores de segurança precisarão da permissão gerenciar configurações de segurança no Microsoft Defender para Ponto de Extremidade se o RBAC estiver ligado.

## <a name="create-a-custom-detection-rule"></a>Criar uma regra de detecção personalizada
### <a name="1-prepare-the-query"></a>1. Prepare a consulta.

No centro de segurança do Microsoft  365, vá para a Busca Avançada e selecione uma consulta existente ou crie uma nova consulta. Ao usar uma nova consulta, execute a consulta para identificar erros e entender os possíveis resultados.

>[!IMPORTANT]
>Para impedir que o serviço retorne muitos alertas, cada regra está limitada a gerar apenas 100 alertas sempre que for executado. Antes de criar uma regra, ajuste sua consulta para evitar alertas para atividades normais do dia a dia.


#### <a name="required-columns-in-the-query-results"></a>Colunas necessárias nos resultados da consulta
Para criar uma regra de detecção personalizada, a consulta deve retornar as seguintes colunas:

- `Timestamp`— usado para definir o timestamp para alertas gerados
- `ReportId`— habilita as buscas para os registros originais
- Uma das seguintes colunas que identificam dispositivos, usuários ou caixas de correio específicos:
    - `DeviceId`
    - `DeviceName`
    - `RemoteDeviceName`
    - `RecipientEmailAddress`
    - `SenderFromAddress` (remetente de envelope ou Return-Path endereço)
    - `SenderMailFromAddress` (endereço do remetente exibido pelo cliente de email)
    - `RecipientObjectId`
    - `AccountObjectId`
    - `AccountSid`
    - `AccountUpn`
    - `InitiatingProcessAccountSid`
    - `InitiatingProcessAccountUpn`
    - `InitiatingProcessAccountObjectId`

>[!NOTE]
>O suporte para entidades adicionais será adicionado à medida que novas tabelas são adicionadas ao [esquema de busca avançada.](advanced-hunting-schema-tables.md)

Consultas simples, como aquelas que não usam o operador ou para personalizar ou agregar resultados, normalmente `project` `summarize` retornam essas colunas comuns.

Há várias maneiras de garantir que consultas mais complexas retornem essas colunas. Por exemplo, se você preferir agregar e contar por entidade sob uma coluna, como , você ainda pode retornar e recebendo-o do evento mais recente envolvendo `DeviceId` `Timestamp` cada exclusivo `ReportId` `DeviceId` .

A consulta de exemplo abaixo conta o número de dispositivos exclusivos ( ) com detecções antivírus e usa essa contagem para encontrar apenas os dispositivos com mais de `DeviceId` cinco detecções. Para retornar o mais `Timestamp` recente e o `ReportId` correspondente, ele usa o operador com `summarize` a `arg_max` função.

```kusto
DeviceEvents
| where Timestamp > ago(1d)
| where ActionType == "AntivirusDetection"
| summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count() by DeviceId
| where count_ > 5
```

> [!TIP]
> Para melhorar o desempenho da consulta, de definir um filtro de tempo que corresponde à frequência de execução pretendido para a regra. Como a menor frequência de run é _a cada 24 horas,_ a filtragem do dia anterior abrangerá todos os novos dados.

### <a name="2-create-new-rule-and-provide-alert-details"></a>2. Crie uma nova regra e forneça detalhes de alerta.

Com a consulta no editor de consulta, selecione **Criar regra de** detecção e especifique os seguintes detalhes de alerta:

- **Nome da detecção**— nome da regra de detecção
- **Frequência**— intervalo para executar a consulta e executar uma ação. [Consulte as diretrizes adicionais abaixo](#rule-frequency)
- **Título do** alerta – título exibido com alertas disparados pela regra
- **Gravidade —** risco potencial do componente ou da atividade identificado pela regra
- **Categoria**— componente de ameaça ou atividade identificado pela regra
- **TÉCNICAS CK mitRE ATT&** uma ou mais técnicas de ataque identificadas pela regra, conforme documentado na estrutura [MITRE ATT&CK](https://attack.mitre.org/). Esta seção está oculta para determinadas categorias de alerta, incluindo malware, ransomware, atividade suspeita e software indesejado
- **Descrição**– mais informações sobre o componente ou a atividade identificada pela regra 
- **Ações recomendadas**— ações adicionais que os respondentes podem tomar em resposta a um alerta

#### <a name="rule-frequency"></a>Frequência de regra
Quando você salva ou edita uma nova regra, ela é executado e verifica se há combinações dos últimos 30 dias de dados. Em seguida, a regra é executado novamente em intervalos fixos, aplicando uma duração de retorno com base na frequência escolhida:

- **A cada 24 horas**— é executado a cada 24 horas, verificando os dados dos últimos 30 dias
- **A cada 12 horas**— é executado a cada 12 horas, verificando dados das últimas 24 horas
- **A cada 3 horas**— é executado a cada 3 horas, verificando dados das últimas 6 horas
- **A cada hora**— é executado a cada hora, verificando dados das últimas 2 horas

>[!TIP]
> Corresponder os filtros de tempo em sua consulta com a duração de retorno. Os resultados fora da duração de pesquisa são ignorados.  

Selecione a frequência que corresponde à proximidade com que você deseja monitorar detecções. Considere a capacidade da sua organização de responder aos alertas.

### <a name="3-choose-the-impacted-entities"></a>3. Escolha as entidades impactadas.
Identifique as colunas nos resultados da consulta onde você espera encontrar a entidade principal afetada ou afetada. Por exemplo, uma consulta pode retornar endereços de remetente ( `SenderFromAddress` ou ) e de destinatário ( `SenderMailFromAddress` `RecipientEmailAddress` ). Identificar quais dessas colunas representam a entidade principal impactada ajuda o serviço a agregar alertas relevantes, correlacionar incidentes e ações de resposta de destino.

Você pode selecionar apenas uma coluna para cada tipo de entidade (caixa de correio, usuário ou dispositivo). Colunas que não são retornadas por sua consulta não podem ser selecionadas.

### <a name="4-specify-actions"></a>4. Especifique as ações.
Sua regra de detecção personalizada pode automaticamente tomar ações em dispositivos, arquivos ou usuários retornados pela consulta.

#### <a name="actions-on-devices"></a>Ações em dispositivos
Essas ações são aplicadas a dispositivos na `DeviceId` coluna dos resultados da consulta:
- **Isole o** dispositivo — usa o Microsoft Defender para o Ponto de Extremidade para aplicar o isolamento de rede completo, impedindo que o dispositivo se conecte a qualquer aplicativo ou serviço. [Saiba mais sobre o Microsoft Defender para isolamento de máquina de ponto de extremidade](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-devices-from-the-network)
- **Coletar pacote de investigação**– coleta informações do dispositivo em um arquivo ZIP. [Saiba mais sobre o pacote de investigação do Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices)
- **Executar a verificação antivírus**— executa uma verificação completa do Windows Defender Antivírus no dispositivo
- **Iniciar investigação**— inicia uma [investigação automatizada](mtp-autoir.md) no dispositivo
- **Restringir a execução do** aplicativo — define restrições no dispositivo para permitir que somente arquivos assinados com um certificado emitido pela Microsoft sejam executados. [Saiba mais sobre restrições de aplicativos com o Microsoft Defender para Ponto de Extremidade](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#restrict-app-execution)

#### <a name="actions-on-files"></a>Ações em arquivos
Quando selecionado, você pode optar por aplicar a ação **de** arquivo de quarentena em arquivos na coluna , ou nos `SHA1` resultados da `InitiatingProcessSHA1` `SHA256` `InitiatingProcessSHA256` consulta. Essa ação exclui o arquivo de seu local atual e coloca uma cópia em quarentena.

#### <a name="actions-on-users"></a>Ações em usuários
Quando selecionado, a **ação marcar o usuário** como comprometida é realizada para os usuários na coluna , ou nos resultados da `AccountObjectId` `InitiatingProcessAccountObjectId` `RecipientObjectId` consulta. Essa ação define o nível de risco dos usuários como "alto" no Azure Active Directory, disparando as políticas de [proteção de identidade correspondentes.](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection)

> [!NOTE]
> No momento, a ação de permitir ou bloquear regras de detecção personalizadas não é suportada no Microsoft 365 Defender.

### <a name="5-set-the-rule-scope"></a>5. Definir o escopo da regra.
Definir o escopo para especificar quais dispositivos são cobertos pela regra. O escopo influencia regras que verificam dispositivos e não afeta regras que verificam apenas caixas de correio e contas de usuário ou identidades.

Ao definir o escopo, você pode selecionar:

- Todos os dispositivos
- Grupos de dispositivos específicos

Somente os dados de dispositivos no escopo serão consultados. Além disso, as ações serão realizadas apenas nesses dispositivos.

### <a name="6-review-and-turn-on-the-rule"></a>6. Revise e a a turn on the rule.
Depois de analisar a regra, selecione **Criar** para salvá-la. A regra de detecção personalizada é imediatamente executado. Ele é executado novamente com base na frequência configurada para verificar se há resultados, gerar alertas e tomar ações de resposta.

## <a name="manage-existing-custom-detection-rules"></a>Gerenciar regras de detecção personalizadas existentes
Você pode exibir a lista de regras de detecção personalizadas existentes, verificar suas versões anteriores e revisar os alertas disparados. Você também pode executar uma regra sob demanda e modificá-la.

### <a name="view-existing-rules"></a>Exibir regras existentes

Para exibir todas as regras de detecção personalizadas existentes, navegue até  >  **Detecções personalizadas de Busca.** A página lista todas as regras com as seguintes informações de executar:

- **Última vez —** quando uma regra foi executado pela última vez para verificar se há consultas e gerar alertas
- **Status da última vez**— se uma regra foi executado com êxito
- **Próxima sequência —** a próxima sequência agendada
- **Status**— se uma regra foi 2013 ou não

### <a name="view-rule-details-modify-rule-and-run-rule"></a>Exibir detalhes da regra, modificar regra e executar regra

Para exibir informações abrangentes sobre uma regra de detecção personalizada, vá para **Detecções** de Busca Personalizada  >  **e** selecione o nome da regra. Em seguida, você pode exibir informações gerais sobre a regra, incluindo informações sobre seu status de executar e escopo. A página também fornece a lista de alertas e ações disparados.

![Página de detalhes da regra de detecção personalizada](../../media/custom-detection-details.png)<br>
*Detalhes da regra de detecção personalizada*

Você também pode tomar as seguintes ações na regra desta página:

- **Executar**— execute a regra imediatamente. Isso também redefine o intervalo para a próxima sequência.
- **Editar**— modifique a regra sem alterar a consulta
- **Modificar consulta —** editar a consulta na busca avançada
- **Ativar**  /  **Desativar — habilitar** a regra ou impedi-la de ser executado
- **Excluir**— desativar a regra e removê-la

### <a name="view-and-manage-triggered-alerts"></a>Exibir e gerenciar alertas disparados

Na tela de detalhes da regra **(** Detecções personalizadas de busca [nome da regra] ), vá para  >    >   **alertas disparados,** que lista os alertas gerados por corresponde à regra. Selecione um alerta para exibir informações detalhadas sobre ele e tomar as seguintes ações:

- Gerenciar o alerta definindo seu status e classificação (alerta verdadeiro ou falso)
- Vincular o alerta a um incidente
- Executar a consulta que disparou o alerta na busca avançada

### <a name="review-actions"></a>Revisar ações
Na tela de detalhes da regra **(** Detecções personalizadas de busca [nome da regra] ), vá para ações disparadas, que lista as ações tomadas com base  >    >  nas combinações com a regra.

>[!TIP]
>Para exibir rapidamente informações e tomar medidas em um item em uma tabela, use a coluna de seleção [&#10003;] à esquerda da tabela.

## <a name="related-topic"></a>Tópico relacionado
- [Visão geral de detecções personalizadas](custom-detections-overview.md)
- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Conhecer a linguagem de consulta de busca avançada](advanced-hunting-query-language.md)
