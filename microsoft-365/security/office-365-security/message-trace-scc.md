---
title: Rastreamento de mensagens no Centro de Conformidade e Segurança
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 3e64f99d-ac33-4aba-91c5-9cb4ca476803
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem usar o rastreamento de mensagens no Centro de Conformidade & segurança para descobrir o que aconteceu com as mensagens.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1b0c27d8e0f43557be537d6e7c9fa096441cc229
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150274"
---
# <a name="message-trace-in-the-security--compliance-center"></a>Rastreamento de mensagens no Centro de Conformidade e Segurança

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender para Office 365 plano 1 e plano 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="message-trace-features"></a>Recursos de rastreamento de mensagens

O rastreamento de mensagens no Centro de Conformidade e Segurança & segue as mensagens de email conforme elas passam pela sua organização do Exchange Online. Você pode determinar se uma mensagem foi recebida, rejeitada, adiada ou entregue pelo serviço. Também mostra as ações feitas na mensagem antes de ela chegar em seu status final.

O rastreamento de mensagens no Centro de Conformidade e Segurança & aprimora o rastreamento de mensagens original que estava disponível no Centro de administração do Exchange (EAC). Você pode usar as informações do rastreamento de mensagens para responder com eficiência às perguntas do usuário sobre o que aconteceu com as mensagens, solucionar problemas de fluxo de emails e validar alterações de política.

> [!NOTE]
>
> - Para fazer um rastreamento de mensagens, você precisa ser membro dos grupos de função Gerenciamento da Organização, Gerenciamento de Conformidade ou Help Desk. Para saber mais, confira [Permissões no Centro de Conformidade de Segurança](permissions-in-the-security-and-compliance-center.md).
>
> - O número máximo de mensagens exibidas nos resultados depende do tipo de relatório selecionado (consulte a seção Escolher tipo [de](#choose-report-type) relatório para obter detalhes). O cmdlet [Get-HistoricalSearch](https://docs.microsoft.com/powershell/module/exchange/get-historicalsearch) no PowerShell do Exchange Online ou no PowerShell do EOP autônomo retorna todas as mensagens nos resultados.

## <a name="open-message-trace"></a>Abrir rastreamento de mensagens

1. Abra o Centro de Conformidade & segurança em <https://protection.office.com> .

2. Expanda **o fluxo de** emails e selecione Rastreamento de **mensagens.**

## <a name="message-trace-page"></a>Página de rastreamento de mensagens

A partir daqui, você pode iniciar um novo rastreamento padrão clicando no **botão Iniciar um** rastreamento. Isso procurará todas as mensagens para todos os destinatários e os destinatários nos últimos dois dias. Ou você pode usar uma das consultas armazenadas das categorias de consulta disponíveis e usá-las como estão ou usá-las como pontos de partida para suas próprias consultas:

- **Consultas padrão:** consultas integrados fornecidas pelo Microsoft 365.

- **Consultas personalizadas:** consultas salvas por administradores em sua organização para uso futuro.

- **Consultas autosaved:** as dez últimas consultas mais recentemente. Essa lista torna mais simples de reacarcar de onde você saiu.

Também nesta página  há uma seção de relatórios baixáveis para as solicitações que você enviou, bem como os relatórios em si quando há disponíveis para download.

## <a name="options-for-a-new-message-trace"></a>Opções para um novo rastreamento de mensagens

### <a name="filter-by-senders-and-recipients"></a>Filtrar por destinatários e por destinatários

Os valores padrão são **Todos os destinatários e** os **destinatários,** mas você pode usar os seguintes campos para filtrar os resultados:

- **Por essas pessoas:** clique neste campo para selecionar um ou mais senders da sua organização. Você também pode começar a digitar um nome e os itens na lista serão filtrados pelo que você digitou, bem parecido com o comportamento de uma página de pesquisa.

- **Para essas pessoas:** clique neste campo para selecionar um ou mais destinatários em sua organização.

> [!NOTE]
>
> - Você também pode digitar os endereços de email de destinatários e destinatários externos. Há suporte para curingas (por exemplo), mas você não pode usar várias entradas curinga no mesmo campo `*@contoso.com` ao mesmo tempo.
>
> - Você pode colar várias listas de destinatários ou de envios separadas por ponto-e-vírgula ( `;` ). espaços ( `\s` ), retornos de carro ( `\r` ) ou próximas linhas ( `\n` ).

### <a name="time-range"></a>Intervalo de tempo

O valor padrão é **2 dias,** mas você pode especificar intervalos de data/hora de até 90 dias. Ao usar intervalos de data/hora, considere estes problemas:

- Por padrão, você seleciona o intervalo de tempo no modo **de exibição de controle** deslizante usando uma linha de tempo. Você só pode selecionar as configurações de dia ou hora que são exibidas. Tentar selecionar um valor entre eles ajustará a bolha inicial/final à configuração exibida mais próxima.

  ![Um intervalo de tempo do Controle Deslizante em um novo rastreamento de mensagens no Centro de Conformidade e & Segurança](../../media/55a9e9c1-f7d5-4047-b217-824e8b976bcb.png)

  Porém, você também  pode alternar para o  exibição Personalizado, onde você pode especificar  os valores de data de início e de término (incluindo horas) e também pode selecionar o fuso horário para o intervalo de data/hora.  Observe que a **configuração fuso** horário se aplica às entradas de consulta e aos resultados da consulta.

  ![Um intervalo de tempo personalizado em um novo rastreamento de mensagens no Centro de Conformidade & Segurança](../../media/ed4c8d50-9ea5-4694-93f9-ee3ab6660b4f.png)

  Por 10 dias ou menos, os resultados ficam disponíveis instantaneamente como um relatório **de** Resumo. Se você especificar um intervalo de tempo que seja um pouco maior do que 10 dias, os resultados serão atrasados,  pois só estarão disponíveis como um arquivo CSV para download **(resumo** aprimorado ou relatórios estendidos).

  Para obter mais informações sobre os diferentes tipos de relatório, consulte a [seção](#choose-report-type) Escolher tipo de relatório neste artigo.

  > [!NOTE]
  > Os relatórios estendidos e de resumo aprimorados são preparados usando dados de rastreamento de mensagens arquivados e podem levar várias horas até que o relatório esteja disponível para download. Dependendo de quantos outros administradores também enviaram solicitações de relatório ao mesmo tempo, você também pode notar um atraso antes do início do processamento para sua solicitação na fila.

- Salvar uma consulta no controle **deslizante** salva o intervalo de tempo relativo (por exemplo, 3 dias a partir de hoje). Salvar uma consulta  no exibição Personalizado salva o intervalo absoluto de data/hora (por exemplo, 2018-05-06 13:00 a 2018-05-08 18:00).

### <a name="more-search-options"></a>Mais opções de pesquisa

#### <a name="delivery-status"></a>Status de entrega

Você pode deixar o valor padrão **Todos** selecionados ou pode selecionar um dos seguintes valores para filtrar os resultados:

- **Entregue:** a mensagem foi entregue com êxito ao destino pretendido.

- **Pendente:** a tentativa de entrega da mensagem está sendo tentada ou tentada outra vez.

- **Expandido:** um destinatário do grupo de distribuição foi expandido antes da entrega aos membros individuais do grupo.

- **Falha:** a mensagem não foi entregue.

- **Em quarentena:** a mensagem foi colocada em quarentena (como spam, email em massa ou phishing). Para obter mais informações, consulte [Mensagens de email em quarentena no EOP.](quarantine-email-messages.md)

- **Filtrado como spam:** a mensagem foi identificada como spam e foi rejeitada ou bloqueada (não colocada em quarentena).

- **Obter status:** A mensagem foi recebida recentemente pelo Microsoft 365, mas nenhum outro dado de status ainda está disponível. Verifique novamente em alguns minutos.

> [!NOTE]
> Os valores **Pendente, Em** **Quarentena** e Filtrar **como spam** só estão disponíveis para pesquisas com menos de 10 dias. Além disso, pode haver um atraso de 5 a 10 minutos entre o status de entrega real e relatado.

#### <a name="message-id"></a>ID da mensagem

Essa é a ID de mensagem da Internet (também conhecida como ID do Cliente) encontrada no campo De **mensagem-ID:** no header da mensagem. Os usuários podem lhe dar esse valor para investigar mensagens específicas.

Esse valor é constante durante o tempo de vida da mensagem. Para mensagens criadas no Microsoft 365 ou Exchange, o valor está no formato `<GUID@ServerFQDN>` , incluindo os colchetes angulares ( \< \> ). Por exemplo, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`. Outros sistemas de mensagens podem usar sintaxe ou valores diferentes. Esse valor deve ser exclusivo, mas nem todos os sistemas de email seguem estritamente esse requisito. Se o campo de cabeça **Message-ID:** não existir ou estiver em branco para mensagens de entrada de fontes externas, um valor arbitrário será atribuído.

Ao usar a **ID da Mensagem** para filtrar os resultados, certifique-se de incluir a cadeia de caracteres completa, incluindo colchetes angulares.

#### <a name="direction"></a>Direção

Você pode deixar  o valor padrão Todos selecionados ou pode selecionar Entrada **(mensagens** enviadas a destinatários em sua organização) ou Saída **(mensagens** enviadas de usuários em sua organização) para filtrar os resultados.

#### <a name="original-client-ip-address"></a>Endereço IP do cliente original

Você pode arquivar os resultados pelo endereço IP do cliente para investigar computadores criminosos que estão enviando grandes quantidades de spam ou malware. Embora as mensagens possam parecer vir de vários senders, é provável que o mesmo computador está gerando todas as mensagens.

> [!NOTE]
> As informações do endereço IP do cliente só estão disponíveis por  10  dias e só estão disponíveis nos relatórios de Resumo aprimorado ou Estendido (arquivos CSV baixáveis).

### <a name="choose-report-type"></a>Escolher tipo de relatório

Os tipos de relatório disponíveis são:

- **Resumo:** Disponível se o intervalo de tempo for menor que 10 dias e não exigir opções de filtragem adicionais. Os resultados estão disponíveis quase imediatamente após você clicar em **Pesquisar.** O relatório retorna até 20.000 resultados.

-  Resumo aprimorado ou **Estendido:** esses relatórios estão disponíveis apenas como arquivos CSV baixáveis e exigem uma ou mais das seguintes opções de filtragem, independentemente do intervalo de **tempo:** Por essas **pessoas,** para essas pessoas ou **ID** da Mensagem. Você pode usar curingas para os destinatários ou os destinatários (por exemplo, \* @contoso.com). O relatório de resumo aprimorado retorna até 50.000 resultados. O relatório Estendido retorna até 1.000 resultados.

> [!NOTE]
> 
> - Os relatórios estendidos e de resumo aprimorados são preparados usando dados de rastreamento de mensagens arquivados e podem levar várias horas até que o relatório esteja disponível para download. Dependendo de quantos outros administradores também enviaram solicitações de relatório ao mesmo tempo, você também pode notar um atraso antes que sua solicitação na fila comece a ser processada.
> 
> - Embora você possa selecionar um resumo aprimorado ou um relatório estendido para qualquer intervalo de data/hora, normalmente as últimas quatro horas de dados arquivados ainda não estarão disponíveis para esses dois tipos de relatórios.

Ao clicar em **Próximo,** você recebe uma página de resumo que lista as opções de filtragem selecionadas, um título exclusivo (editável) para o relatório e o endereço de email que recebe a notificação quando o rastreamento de mensagem é concluído (também editável e deve estar em um dos domínios aceitos da sua organização). Clique **em Preparar relatório** para enviar o rastreamento de mensagem. Na página principal **Rastreamento de** mensagens, você pode ver o status do relatório na seção **Relatórios Baixáveis.**

Para obter mais informações sobre as informações retornadas nos diferentes tipos de relatório, consulte a próxima seção.

## <a name="message-trace-results"></a>Resultados de rastreamento de mensagens

Os diferentes tipos de relatório retornam diferentes níveis de informações. As informações disponíveis nos diferentes relatórios são descritas nas seções a seguir.

### <a name="summary-report-output"></a>Saída do relatório de resumo

Depois de executar o rastreamento de mensagens, os resultados serão listados, organizados por data/hora decrescente (a primeira mais recente).

![Resultados de relatório resumido para rastreamento de mensagens no Centro de Conformidade & segurança](../../media/0664bafe-0b03-477b-b571-0b046ac8c977.png)

O relatório resumido contém as seguintes informações:

- **Data**: a data e a hora em que a mensagem foi recebida pelo serviço, usando o fuso horário UTC configurado.

- **Remetente**: o endereço de email do remetente *(domínio de* @ alias).

- **Destinatário**: o endereço de email do destinatário ou destinatários. Para uma mensagem enviada a vários destinatários, há uma linha por destinatário. Se o destinatário for um grupo de distribuição, um grupo dinâmico de distribuição ou um grupo de segurança habilitado para email, o grupo será o primeiro destinatário e, em seguida, cada membro do grupo estará em uma linha separada.

- **Assunto**: os primeiros 256 caracteres do campo **Assunto: da** mensagem.

- **Status:** esses valores são descritos na seção [Status de](#delivery-status) entrega.

Por padrão, os primeiros 250 resultados são carregados e prontamente disponíveis. Quando você rola para baixo, há uma pequena pausa à medida que o próximo lote de resultados é carregado. Em vez de rolar,  você pode clicar em Carregar tudo para carregar todos os resultados até um máximo de 10.000.

Você pode clicar nos headers das colunas para classificar os resultados pelos valores dessa coluna em ordem crescente ou decrescente.

Você pode clicar **nos resultados de** Filtro para filtrar os resultados por uma ou mais colunas.

Você pode exportar os resultados depois de selecionar uma  ou mais linhas clicando em Exportar resultados e, em seguida, selecionando Exportar todos os resultados **,** Exportar resultados carregados ou **Exportar selecionado.**

#### <a name="find-related-records-for-this-message"></a>Encontrar registros relacionados para esta mensagem

Registros de mensagens relacionados são registros que compartilharam a mesma ID de Mensagem. Lembre-se de que até mesmo uma única mensagem enviada entre duas pessoas pode gerar vários registros. O número de registros aumenta quando a mensagem é afetada pela expansão, encaminhamento, regras de fluxo de emails (também conhecidas como regras de transporte), etc.

Depois de marcar a caixa de seleção de uma linha, você  pode encontrar registros relacionados  para a mensagem clicando no botão Encontrar relacionado que aparece ou selecionando Mais opções Mais opções Encontre registros relacionados para esta ![ ](../../media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **mensagem).**

Para obter mais informações sobre a ID da Mensagem, consulte a seção ID da Mensagem anteriormente neste artigo.

#### <a name="message-trace-details"></a>Detalhes do rastreamento de mensagens

Na saída do relatório resumido, você pode exibir detalhes sobre uma mensagem usando um dos seguintes métodos:

- Selecione a linha (clique em qualquer lugar da linha, exceto na caixa de seleção).

- Marque a caixa de seleção da linha e clique em **Mais opções** Mais Exibir detalhes da ![ ](../../media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **mensagem.**

   ![Detalhes depois de clicar duas vezes em uma linha no relatório resumido resultados de rastreamento de mensagem no Centro de Conformidade & segurança](../../media/e50ee7cd-810a-4c06-8b58-e56ffd7028d1.png)

Os detalhes do rastreamento de mensagens contêm as seguintes informações adicionais que não estão presentes no relatório resumido:

- **Eventos de** mensagem: Esta seção contém classificações que ajudam a categorizar as ações que o serviço toma em mensagens. **Alguns dos eventos mais interessantes** que você pode encontrar são:

  - **Receive**: The message was received by the service.

  - **Enviar**: a mensagem foi enviada pelo serviço.

  - **Falha:** A mensagem não foi entregue.

  - **Entregar**: a mensagem foi entregue a uma caixa de correio.

  - **Expanda**: a mensagem foi enviada para um grupo de distribuição que foi expandido.

  - **Transferência:** os destinatários foram movidos para uma mensagem bifurcada devido à conversão de conteúdo, limites de destinatário da mensagem ou agentes.

  - **Adiamento**: a entrega da mensagem foi adiada e pode ser tentada novamente mais tarde.

  - **Resolvido:** a mensagem foi redirecionada para um novo endereço de destinatário com base em uma busca no Active Directory. Quando isso acontece, o endereço original de destinatário é listado em uma linha separada no rastreamento de mensagem junto com o status final de entrega da mensagem.

  > [!NOTE]
  > 
  > - Uma mensagem sem eventos entregue com êxito gerará várias entradas **de** evento no rastreamento de mensagens.
  > 
  > - Essa lista não deve ser exaustiva. Para obter descrições de mais eventos, consulte [Tipos de eventos no log de controle de mensagens.](https://docs.microsoft.com/Exchange/mail-flow/transport-logs/message-tracking#event-types-in-the-message-tracking-log) Observe que esse link é um tópico do Exchange Server (Exchange local).

- **Mais informações:** Esta seção contém os seguintes detalhes:

  - **ID da** mensagem: esse valor é descrito na seção [ID da](#message-id) mensagem anteriormente neste artigo. Por exemplo, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.

  - **Tamanho da mensagem**

  - **De IP**: o endereço IP do computador que enviou a mensagem. Para as mensagens de saída enviadas a partir do Exchange Online, o valor é nulo.

  - **Para IP:** o endereço IP ou endereços em que o serviço tentou entregar a mensagem. Se a mensagem tiver vários destinatários, eles serão exibidos. Para mensagens de entrada enviadas para o Exchange Online, o valor é nulo.

### <a name="enhanced-summary-reports"></a>Relatórios de resumo aprimorados

Relatórios de resumo aprimorados disponíveis (concluídos) estão disponíveis na seção **Relatórios baixáveis** no rastreamento de mensagens inicial. As seguintes informações estão disponíveis no relatório:

- **origin_timestamp**: a data e hora em que a mensagem foi inicialmente recebida pelo serviço, usando o <sup>*</sup> fuso horário UTC configurado.

- **sender_address**: o endereço de email do remetente *(domínio do* @ alias).

- **Recipient_status**: o status da entrega da mensagem para o destinatário. Se a mensagem foi enviada para vários destinatários, ela mostrará todos os destinatários e o status correspondente para cada um, no formato: \<*email address*\> ## \<*status*\> . Por exemplo:

  - **##Receive, Send** significa que a mensagem foi recebida pelo serviço e enviada para o destino pretendido.

  - **##Receive, Fail** significa que a mensagem foi recebida pelo serviço, mas a entrega ao destino pretendido falhou.

  - **##Receive, Entrega significa** que a mensagem foi recebida pelo serviço e entregue à caixa de correio do destinatário.

- **message_subject**: os primeiros 256 caracteres do campo **Assunto da** mensagem.

- **total_bytes**: o tamanho da mensagem em bytes, incluindo anexos.

- **message_id**: esse valor é descrito na seção [ID](#message-id) da mensagem anteriormente neste artigo. Por exemplo, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.

- **network_message_id**: um valor de ID de mensagem exclusivo que persiste em todas as cópias da mensagem que podem ser criadas devido à bifurcação ou à expansão do grupo de distribuição. Um valor de exemplo é `1341ac7b13fb42ab4d4408cf7f55890f` .

- **original_client_ip**: o endereço IP do cliente do remetente.

- **directionality**: Indica se a mensagem foi enviada de entrada (1) para sua organização ou se foi enviada de saída (2) da sua organização.

- **connector_id**: o nome do conector de origem ou de destino. Para saber mais sobre conectores no Exchange Online, confira Configurar o fluxo de [emails usando conectores no Office 365.](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)

- **delivery_priority**: se a mensagem foi enviada com prioridade <sup>*</sup> **Alta,** Baixa ou **Normal.** 

<sup>*</sup> Essas propriedades só estão disponíveis em relatórios de resumo aprimorados.

### <a name="extended-reports"></a>Relatórios estendidos

Relatórios estendidos disponíveis (concluídos) estão disponíveis na seção Relatórios **baixáveis** no início do rastreamento de mensagens. Praticamente todas as informações de um relatório de resumo aprimorado estão  disponíveis em um relatório estendido (com exceção de origin_timestamp e **delivery_priority**). As seguintes informações adicionais só estão disponíveis em um relatório Estendido:

- **client_ip**: o endereço IP do servidor de email ou do cliente de mensagens que enviou a mensagem.

- **client_hostname:** o nome do host ou FQDN do servidor de email ou do cliente de mensagens que enviou a mensagem.

- **server_ip**: o endereço IP do servidor de origem ou de destino.

- **server_hostname:** o nome do host ou FQDN do servidor de destino.

- **source_context:** informações extras associadas ao campo **de origem.** Por exemplo:

  - `Protocol Filter Agent`

  - `3489061114359050000`

- **origem**: o componente do Exchange Online responsável pelo evento. Por exemplo:

  - `AGENT`

  - `MAILBOXRULE`

  - `SMTP`

- **event_id**: eles correspondem aos valores **de** evento Message que são explicados na seção "Encontrar [registros relacionados".](#find-related-records-for-this-message)

- **internal_message_id**: um identificador de mensagem atribuído pelo servidor do Exchange Online que está processando a mensagem no momento.

- **recipient_address:** os endereços de email dos destinatários da mensagem. Vários endereços de email são separados pelo caractere de ponto-e-vírgula (;).

- **recipient_count**: o número total de destinatários na mensagem.

- **related_recipient_address**: usado com , e eventos para exibir outros endereços de email de destinatário `EXPAND` que estão `REDIRECT` `RESOLVE` associados à mensagem.

- **referência:** este campo contém informações adicionais para tipos específicos de eventos. Por exemplo:

  - **DSN**: contém o link do relatório, que é o valor **de message_id** da notificação de status de entrega associada (também conhecida como DSN, relatório de não entrega, NDR ou mensagem de rejeição) se uma DSN for gerada após esse evento. Se for uma mensagem DSN, esse campo conterá o **message_id** da mensagem original para a que a DSN foi gerada.

  - **EXPAND:** contém o **related_recipient_address** valor das mensagens relacionadas.

  - **RECEIVE**: pode conter o **message_id** da mensagem relacionada se a mensagem tiver sido gerada por outros processos (por exemplo, regras de Caixa de Entrada).

  - **SEND**: contém o **internal_message_id** de todas as mensagens DSN.

  - **TRANSFER**: contém **o internal_message_id** da mensagem que está sendo bifurcada (por exemplo, por conversão de conteúdo, limites de destinatário de mensagem ou agentes).

  - **MAILBOXRULE**: contém o **internal_message_id** da mensagem de entrada que fez com que a regra de Caixa de Entrada gerava a mensagem de saída.

    Para outros tipos de eventos, esse campo geralmente fica em branco.

- **return_path**: o endereço de email de retorno especificado pelo comando **MAIL FROM** que enviou a mensagem. Embora esse campo nunca seja vazio, ele pode ter o valor nulo do endereço do remetente representado como `<>` .

- **message_info:** informações adicionais sobre a mensagem. Por exemplo:

  - A data e a hora de origem da mensagem em UTC `DELIVER` para `SEND` eventos. A data e a hora de origem é a hora em que a mensagem entrou pela primeira vez na organização do Exchange Online. A data e a hora UTC são representadas no formato de data e hora ISO 8601: , onde = ano, = mês, = dia, indica o início do componente de `yyyy-mm-ddThh:mm:ss.fffZ` `yyyy` `mm` `dd` `T` hora, `hh` = hora, `mm` = minuto, = segundo, `ss` `fff` = `Z` `Zulu` frações de um segundo e significa , que é outra maneira de indicar UTC.

  - Erros de autenticação. Por exemplo, você pode ver o valor `11a` e o tipo de autenticação que foi usado quando o erro de autenticação ocorreu.

- **tenant_id**: um valor GUID que representa a organização do Exchange Online (por exemplo, `39238e87-b5ab-4ef6-a559-af54c6b07b42` ).

- **original_server_ip**: o endereço IP do servidor original.

- **custom_data**: contém dados relacionados a tipos de eventos específicos. Para obter mais informações, consulte as seções a seguir.

#### <a name="custom_data-values"></a>custom_data valores

O **custom_data** de um evento é usado por vários agentes do Exchange Online para registrar detalhes `AGENTINFO` de processamento de mensagens. Alguns dos agentes mais interessantes são descritos nas seções a seguir.

#### <a name="spam-filter-agent"></a>Agente de filtro de spam

Um **custom_data** valor que começa com `S:SFA` é do agente de filtro de spam. Os principais detalhes são descritos na tabela a seguir:

****

|Valor|Descrição|
|---|---|
|`SFV=NSPM`|A mensagem foi marcada como não spam e enviada aos destinatários pretendidos.|
|`SFV=SPM`|A mensagem foi marcada como spam pela filtragem anti-spam (também conhecida como filtragem de conteúdo).|
|`SFV=BLK`|A filtragem foi ignorada e a mensagem foi bloqueada, pois originou-se em um remetente bloqueado.|
|`SFV=SKS`|A mensagem foi marcada como spam antes de ser processada pela filtragem anti-spam. Isso inclui mensagens que atenderam a uma regra de fluxo de emails (também conhecida como uma regra de Transporte) para marcá-la automaticamente como spam e ignorar toda filtragem adicional.|
|`SCL=<number>`|Para saber mais sobre os diferentes valores SCL e seu significado, veja [Níveis de confiança de spam](spam-confidence-levels.md).|
|`PCL=<number>`|O valor do Nível de confiança de phishing (PCL) da mensagem. Podem ser interpretados da mesma maneira que os valores de SCL documentados em [Níveis de confiança de spam](spam-confidence-levels.md).  |
|`DI=SB`|O remetente da mensagem foi bloqueado.|
|`DI=SQ`|A mensagem foi colocada em quarentena.|
|`DI=SD`|A mensagem foi excluída.|
|`DI=SJ`|A mensagem foi enviada para a pasta de lixo eletrônico do destinatário.|
|`DI=SN`|A mensagem foi roteada através do pool normal de entrega de saída.|
|`DI=SO`|A mensagem foi roteada através do pool de entrega de risco mais alto. Para saber mais, confira [Pool de entrega com maior risco em mensagens de saída](high-risk-delivery-pool-for-outbound-messages.md).|
|`SFS=[a]|SFS=[b]`|Isso indica que houve correspondência com regras de spam.|
|`IPV=CAL`|A mensagem foi permitida pelos filtros de spam porque o endereço IP estava especificado em uma Lista de Permissões de IP do filtro de conexão.|
|`H=<EHLOstring>`|A sequência HELO ou EHLO do servidor de emails de conexão.|
|`PTR=<ReverseDNS>`|O registro PTR do endereço IP de envio, também conhecido como o endereço de DNS reverso.|
|

Um exemplo **custom_data** valor de uma mensagem filtrada por spam como esta:

`S:SFA=SUM|SFV=SPM|IPV=CAL|SRV=BULK|SFS=470454002|SFS=349001|SCL=9|SCORE=-1|LIST=0|DI=SN|RD=ftmail.inc.com|H=ftmail.inc.com|CIP=98.129.140.74|SFP=1501|ASF=1|CTRY=US|CLTCTRY=|LANG=en|LAT=287|LAT=260|LAT=18;`

#### <a name="malware-filter-agent"></a>Agente de filtro de malware

Um **custom_data** valor que começa com `S:AMA` é do agente de filtro de malware. Os principais detalhes são descritos na tabela a seguir:

****

|Valor|Descrição|
|---|---|
|`AMA=SUM|v=1|` ou `AMA=EV|v=1`|Foi determinado que a mensagem contém malware. `SUM` indica que o malware pode ter sido detectado por qualquer número de mecanismos. `EV` indica que o malware foi detectado por um mecanismo específico. Quando um mecanismo detecta malware, isto aciona as ações subseqüentes.|
|`Action=r`|A mensagem foi substituída.|
|`Action=p`|A mensagem foi ignorada.|
|`Action=d`|A mensagem foi adiada.|
|`Action=s`|A mensagem foi excluída.|
|`Action=st`|A mensagem foi ignorada.|
|`Action=sy`|A mensagem foi ignorada.|
|`Action=ni`|A mensagem foi rejeitada.|
|`Action=ne`|A mensagem foi rejeitada.|
|`Action=b`|A mensagem foi bloqueada.|
|`Name=<malware>`|O nome do malware foi detectado.|
|`File=<filename>`|O nome do arquivo que continha o malware.|
|

Um exemplo **custom_data** valor de uma mensagem que contém malware tem esta aparência:

`S:AMA=SUM|v=1|action=b|error=|atch=1;S:AMA=EV|engine=M|v=1|sig=1.155.974.0|name=DOS/Test_File|file=filename;S:AMA=EV|engine=A|v=1|sig=201707282038|name=Test_File|file=filename`

#### <a name="transport-rule-agent"></a>Agente de Regra de Transporte

Um **custom_data** que começa com é do agente de Regra de Transporte para regras de fluxo de emails `S:TRA` (também conhecidas como regras de transporte). Os principais detalhes são descritos na tabela a seguir:

****

|Valor|Descrição|
|---|---|
|`ETR|ruleId=<guid>`|A identificação da regra encontrou uma correspondência.|
|`St=<datetime>`|A data e a hora em UTC em que a regra de match ocorreu.|
|`Action=<ActionDefinition>`|A ação que foi aplicada. Para ver uma lista de ações disponíveis, confira [Ações de regra de fluxo de emails no Exchange Online.](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)|
|`Mode=<Mode>`|O modo da regra. Os valores válidos são:<ul><li>**Impor:** todas as ações na regra serão impostas.</li><li>**Teste com Dicas de Política:**: Todas as ações de Dica de Política serão enviadas, mas outras ações impositivas não serão realizadas.</li><li>**Teste sem Dicas de Política:** as ações serão listadas em um arquivo de log, mas os envios não serão notificados de nenhuma maneira e as ações impositivas não serão realizadas.</li></ul>|
|

Um exemplo **custom_data** valor de uma mensagem que corresponde às condições de uma regra de fluxo de emails tem esta aparência:

`S:TRA=ETR|ruleId=19a25eb2-3e43-4896-ad9e-47b6c359779d|st=7/17/2017 12:31:25 AM|action=ApplyHtmlDisclaimer|sev=1|mode=Enforce`
