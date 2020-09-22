---
title: Rastreamento de mensagens no Centro de Conformidade e Segurança
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 3e64f99d-ac33-4aba-91c5-9cb4ca476803
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem usar o rastreamento de mensagens no centro de conformidade & segurança para descobrir o que aconteceu com as mensagens.
ms.openlocfilehash: 1e9f5e21655e55f711997defcb7ace0319ff4be6
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48197532"
---
# <a name="message-trace-in-the-security--compliance-center"></a>Rastreamento de mensagens no Centro de Conformidade e Segurança

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="message-trace-features"></a>Recursos de rastreamento de mensagens

O rastreamento de mensagens no centro de conformidade & de segurança segue as mensagens de email à medida que elas viajam pela sua organização do Exchange Online. Você pode determinar se uma mensagem foi recebida, rejeitada, adiada ou entregue pelo serviço. Também mostra as ações feitas na mensagem antes de ela chegar em seu status final.

O rastreamento de mensagens no centro de conformidade & segurança aprimora o rastreamento de mensagem original que estava disponível no centro de administração do Exchange (Eat). Você pode usar as informações do rastreamento de mensagens para responder com eficiência às perguntas do usuário sobre o que aconteceu com as mensagens, solucionar problemas de fluxo de emails e validar as alterações na política.

> [!NOTE]
>
> - Para fazer um rastreamento de mensagem, você precisa ser membro dos grupos de função de gerenciamento de organização, de conformidade ou de suporte técnico. Para saber mais, confira [Permissões no Centro de Conformidade de Segurança](permissions-in-the-security-and-compliance-center.md).
>
> - O número máximo de mensagens exibidas nos resultados depende do tipo de relatório selecionado (consulte a seção [escolher tipo de relatório](#choose-report-type) para obter detalhes). O cmdlet [Get-HistoricalSearch](https://docs.microsoft.com/powershell/module/exchange/get-historicalsearch) no PowerShell do Exchange Online ou no PowerShell do EOP autônomo retorna todas as mensagens nos resultados.

## <a name="open-message-trace"></a>Abrir rastreamento de mensagens

1. Abra o centro de conformidade & segurança em <https://protection.office.com> .

2. Expanda **fluxo de email**e selecione **rastreamento de mensagens**.

## <a name="message-trace-page"></a>Página rastreamento de mensagens

Aqui você pode iniciar um novo rastreamento padrão clicando no botão **Iniciar um rastreamento** . Isso pesquisará todas as mensagens de todos os remetentes e destinatários pelos últimos dois dias. Ou você pode usar uma das consultas armazenadas das categorias de consulta disponíveis e executá-las como estão ou usá-las como pontos de partida para suas próprias consultas:

- **Consultas padrão**: consultas internas fornecidas pelo Microsoft 365.

- **Consultas personalizadas**: consultas salvas por administradores em sua organização para uso futuro.

- **Consultas salvas**: as últimas dez consultas mais recentes. Essa lista simplifica a retirada de onde você parou.

Além disso, esta página é uma seção de **relatórios que podem ser baixados** para as solicitações que você enviou, bem como os relatórios em si, quando estão disponíveis para download.

## <a name="options-for-a-new-message-trace"></a>Opções para um novo rastreamento de mensagem

### <a name="filter-by-senders-and-recipients"></a>Filtrar por remetentes e destinatários

Os valores padrão são **todos os remetentes** e **todos os destinatários**, mas você pode usar os seguintes campos para filtrar os resultados:

- **Por estas pessoas**: clique neste campo para selecionar um ou mais remetentes da sua organização. Você também pode começar a digitar um nome e os itens da lista serão filtrados pelo que você digitou, de forma semelhante à forma como uma página de pesquisa se comporta.

- **Para estas pessoas**: clique neste campo para selecionar um ou mais destinatários em sua organização.

> [!NOTE]
> Você também pode digitar os endereços de email de remetentes e destinatários externos. Há suporte para curingas (por exemplo, `*@contoso.com` ), mas não é possível usar várias entradas curinga no mesmo campo ao mesmo tempo. <br/><br/> Você pode colar vários remetentes ou listas de destinatários separados por ponto-e-vírgula ( `;` ). espaços ( `\s` ), retornos de carro ( `\r` ) ou linhas de próximo ( `\n` ).

### <a name="time-range"></a>Intervalo de tempo

O valor padrão é **2 dias**, mas você pode especificar intervalos de data/hora de até 90 dias. Ao usar intervalos de data/hora, considere estes problemas:

- Por padrão, você seleciona o intervalo de tempo no modo de exibição **Slider** usando uma linha de tempo. Você só pode selecionar as configurações de dia ou hora exibidas. Tentar selecionar um valor entre-between ajustará a bolha de início/término à configuração mais próxima.

  ![Um intervalo de tempo de controle deslizante em um novo rastreamento de mensagem no centro de conformidade & segurança](../../media/55a9e9c1-f7d5-4047-b217-824e8b976bcb.png)

  No entanto, você também pode alternar para o modo de exibição **personalizado** onde você pode especificar os valores de **data de início** e **data de término** (incluindo horas) e também pode selecionar o **fuso horário** para o intervalo de data/hora. Observe que a configuração de **fuso horário** se aplica às suas entradas de consulta e aos resultados de consulta.

  ![Um intervalo de tempo personalizado em um novo rastreamento de mensagem no centro de conformidade & segurança](../../media/ed4c8d50-9ea5-4694-93f9-ee3ab6660b4f.png)

  Por 10 dias ou menos, os resultados estão disponíveis instantaneamente como um relatório de **Resumo** . Se você especificar um intervalo de tempo que é um pouco maior do que 10 dias, os resultados serão atrasados, já que estão disponíveis apenas como um arquivo CSV que pode ser baixado ( **Resumo avançado** ou relatórios **estendidos** ).

  Para obter mais informações sobre os diferentes tipos de relatórios, consulte a seção [escolher tipo de relatório](#choose-report-type) neste tópico.

  **Observação**: o resumo avançado e os relatórios estendidos são preparados usando dados de rastreamento de mensagem arquivados e pode levar várias horas para que o relatório fique disponível para download. Dependendo de quantos outros administradores também tiverem enviado solicitações de relatório ao mesmo tempo, você também pode notar um atraso antes de o processamento começar para sua solicitação em fila.

- Salvar uma consulta no modo de exibição **Slider** salva o intervalo de tempo relativo (por exemplo, 3 dias a partir de hoje). Salvar uma consulta no modo de exibição **personalizado** salva o intervalo de data/hora absoluto (por exemplo, 2018-05-06 13:00 a 2018-05-08 18:00).

### <a name="more-search-options"></a>Mais opções de pesquisa

#### <a name="delivery-status"></a>Status de entrega

Você pode deixar o valor padrão **todos** selecionado ou pode selecionar um dos seguintes valores para filtrar os resultados:

- **Entregue**: a mensagem foi entregue com êxito ao destino desejado.

- **Pendente**: a entrega da mensagem está sendo tentada ou tentada novamente.

- **Expandido**: um destinatário de grupo de distribuição foi expandido antes da entrega para os membros individuais do grupo.

- **Falha**: a mensagem não foi entregue.

- Em **quarentena**: a mensagem foi colocada em quarentena (como spam, email em massa ou phishing). Para obter mais informações, consulte [mensagens de email em quarentena no EOP](quarantine-email-messages.md).

- **Filtrado como spam**: a mensagem foi identificada como spam e foi rejeitada ou bloqueada (não foi colocada em quarentena).

- **Obtendo status:** A mensagem foi recebida recentemente pelo Microsoft 365, mas nenhum outro dado de status ainda está disponível. Verifique novamente em alguns minutos.

**Observação**: os valores **pendentes,** em **quarentena**e o **filtro como spam** só estão disponíveis para pesquisas com menos de 10 dias. Além disso, pode haver um atraso de 5 a 10 minutos entre o status de entrega real e relatado.

#### <a name="message-id"></a>ID da mensagem

Esta é a ID de mensagem da Internet (também conhecida como ID do cliente) encontrada no campo de cabeçalho **Message-ID:** no cabeçalho da mensagem. Os usuários podem fornecer esse valor para investigar mensagens específicas.

Esse valor é constante durante o tempo de vida da mensagem. Para mensagens criadas no Microsoft 365 ou Exchange, o valor está no formato `<GUID@ServerFQDN>` , incluindo os colchetes angulares ( \< \> ). Por exemplo, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`. Outros sistemas de mensagens podem usar sintaxes ou valores diferentes. Esse valor deve ser exclusivo, mas nem todos os sistemas de email seguem estritamente esse requisito. Se o campo **ID da mensagem:** cabeçalho não existir ou estiver em branco para mensagens de entrada de fontes externas, um valor arbitrário é atribuído.

Ao usar **ID de mensagem** para filtrar os resultados, certifique-se de incluir a cadeia de caracteres completa, incluindo colchetes angulares.

#### <a name="direction"></a>Direção

Você pode deixar o valor padrão **todos** selecionado, ou pode selecionar **entrada** (mensagens enviadas a destinatários em sua organização) ou de **saída** (mensagens enviadas de usuários na sua organização) para filtrar os resultados.

#### <a name="original-client-ip-address"></a>Endereço IP do cliente original

Você pode arquivar os resultados pelo endereço IP do cliente para investigar os computadores de hackers que estão enviando grandes quantidades de spam ou malware. Embora as mensagens possam parecer provenientes de vários remetentes, é provável que o mesmo computador esteja gerando todas as mensagens.

**Observação**: as informações de endereço IP do cliente só estão disponíveis por 10 dias e só estão disponíveis no **Resumo avançado** ou nos relatórios **estendidos** (arquivos CSV para download).

### <a name="choose-report-type"></a>Escolher tipo de relatório

Os tipos de relatórios disponíveis são:

- **Resumo**: disponível se o intervalo de tempo for inferior a 10 dias e não requer opções de filtragem adicionais. Os resultados estão disponíveis quase imediatamente após você clicar em **Pesquisar**. O relatório retorna até 20000 resultados.

- **Resumo avançado** ou **estendido**: esses relatórios só estão disponíveis como arquivos CSV que podem ser baixados e exigem uma ou mais das seguintes opções de filtragem, independentemente do intervalo de tempo: **To these people** **por essas pessoas**, ou **ID da mensagem**. Você pode usar caracteres curinga para os remetentes ou destinatários (por exemplo, \* @contoso. com). O relatório de resumo avançado retorna até 50000 resultados. O relatório estendido retorna até 1000 resultados.

**Observações**:

- Resumo avançado e relatórios estendidos são preparados usando dados arquivados de rastreamento de mensagens, e pode levar várias horas antes que seu relatório esteja disponível para download. Dependendo de quantos outros administradores também tiverem enviado solicitações de relatório ao mesmo tempo, você também poderá observar um atraso antes de a solicitação em fila começar a ser processada.

- Embora você possa selecionar um resumo avançado ou um relatório estendido para qualquer intervalo de data/hora, normalmente as últimas quatro horas de dados arquivados ainda não estarão disponíveis para esses dois tipos de relatórios.

Ao clicar em **Avançar**, você verá uma página de resumo que lista as opções de filtragem selecionadas, um título exclusivo (editável) para o relatório e o endereço de email que recebe a notificação quando o rastreamento de mensagem é concluído (também editável e deve estar em um dos domínios aceitos de sua organização). Clique em **preparar relatório** para enviar o rastreamento de mensagem. Na página principal de **rastreamento de mensagem** , você pode ver o status do relatório na seção **relatórios baixáveis** .

Para obter mais informações sobre as informações que são retornadas nos diferentes tipos de relatório, consulte a próxima seção.

## <a name="message-trace-results"></a>Resultados do rastreamento de mensagens

Os diferentes tipos de relatório retornam diferentes níveis de informações. As informações disponíveis nos diferentes relatórios são descritas nas seções a seguir.

### <a name="summary-report-output"></a>Saída do relatório de resumo

Após a execução do rastreamento de mensagens, os resultados serão listados, classificados por data/hora decrescente (mais recentes primeiro).

![Resultados do relatório de resumo para rastreamento de mensagens no centro de conformidade & segurança](../../media/0664bafe-0b03-477b-b571-0b046ac8c977.png)

O relatório de Resumo contém as seguintes informações:

- **Date**: a data e a hora em que a mensagem foi recebida pelo serviço, usando o fuso horário UTC configurado.

- **Remetente**: o endereço de email do remetente (*alias* @ *domínio*de alias).

- **Destinatário**: o endereço de email do destinatário ou dos destinatários. Para uma mensagem enviada para vários destinatários, há uma linha por destinatário. Se o destinatário for um grupo de distribuição, um grupo dinâmico de distribuição ou um grupo de segurança habilitado para email, o grupo será o primeiro destinatário e, em seguida, cada membro do grupo estará em uma linha separada.

- **Subject**: os primeiros 256 caracteres do campo Subject da mensagem **:** .

- **Status**: esses valores são descritos na seção [status de entrega](#delivery-status) .

Por padrão, os primeiros resultados 250 são carregados e prontamente disponíveis. Quando você rola para baixo, há uma ligeira pausa à medida que o próximo lote de resultados é carregado. Em vez de rolagem, você pode clicar em **carregar todos** para carregar todos os resultados até o máximo de 10.000.

Você pode clicar nos cabeçalhos de coluna para classificar os resultados pelos valores dessa coluna em ordem crescente ou decrescente.

Você pode clicar em **filtrar resultados** para filtrar os resultados por uma ou mais colunas.

Você pode exportar os resultados depois de ter selecionado uma ou mais linhas clicando em **Exportar resultados** e, em seguida, selecionando **exportar todos os resultados**, **Exportar resultados carregados**ou **Exportar selecionados**.

#### <a name="find-related-records-for-this-message"></a>Localizar registros relacionados para esta mensagem

Registros de mensagens relacionados são registros que compartilhavam a mesma ID de mensagem. Lembre-se, mesmo uma única mensagem enviada entre duas pessoas podem gerar vários registros. O número de registros aumenta quando a mensagem é afetada por expansão de grupo de distribuição, encaminhamento, regras de fluxo de emails (também conhecidas como regras de transporte), etc.

Após selecionar a caixa de seleção de uma linha, você pode encontrar registros relacionados para a mensagem clicando no botão **Localizar relacionado** exibido ou selecionando **mais opções** ![ mais ](../../media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **localizar registros relacionados para esta mensagem**.

Para obter mais informações sobre a ID da mensagem, consulte a seção ID da mensagem anteriormente neste tópico.

#### <a name="message-trace-details"></a>Detalhes de rastreamento de mensagem

Na saída do relatório de resumo, é possível exibir detalhes sobre uma mensagem usando um dos seguintes métodos:

- Selecione a linha (clique em qualquer lugar na linha, exceto a caixa de seleção).

- Marque a caixa de seleção da linha e clique em **mais opções** ![ mais ](../../media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **Exibir detalhes da mensagem**.

   ![Detalhes depois de clicar duas vezes em uma linha no relatório de resumo Message Trace Results no centro de conformidade de segurança &](../../media/e50ee7cd-810a-4c06-8b58-e56ffd7028d1.png)

Os detalhes de rastreamento de mensagem contêm as seguintes informações adicionais que não estão presentes no relatório de Resumo:

- **Eventos de mensagem**: Esta seção contém classificações que ajudam a categorizar as ações que o serviço executa em mensagens. **Alguns dos eventos mais interessantes** que você pode encontrar são:

  - **Receive**: a mensagem foi recebida pelo serviço.

  - **Enviar**: a mensagem foi enviada pelo serviço.

  - **Falha**: a mensagem falhou ao ser entregue.

  - **Entregar**: a mensagem foi entregue a uma caixa de correio.

  - **Expand**: a mensagem foi enviada a um grupo de distribuição que foi expandido.

  - **Transferência**: os destinatários foram movidos para uma mensagem bifurcada por causa de conversão de conteúdo, limites de destinatário de mensagem ou agentes.

  - **Defer**: a entrega da mensagem foi adiada e pode ser tentada novamente mais tarde.

  - **Resolvido**: a mensagem foi redirecionada para um novo endereço de destinatário com base em uma pesquisa do Active Directory. Quando isso acontece, o endereço original de destinatário é listado em uma linha separada no rastreamento de mensagem junto com o status final de entrega da mensagem.

  Observações:

  - Uma mensagem sem erro entregue com êxito irá gerar várias entradas de **evento** no rastreamento de mensagens.

  - Essa lista não deve ser exaustiva. Para obter descrições de mais eventos, confira [tipos de eventos no log de controle de mensagens](https://docs.microsoft.com/Exchange/mail-flow/transport-logs/message-tracking#event-types-in-the-message-tracking-log). Observe que esse link é um tópico do Exchange Server (Exchange local).

- **Mais informações**: Esta seção contém os seguintes detalhes:

  - **ID da mensagem**: esse valor é descrito na seção [ID da mensagem](#message-id) anteriormente neste tópico. Por exemplo, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.

  - **Tamanho da mensagem**

  - **De IP**: o endereço IP do computador que enviou a mensagem. Para as mensagens de saída enviadas a partir do Exchange Online, o valor é nulo.

  - **Para IP**: o endereço IP ou endereços onde o serviço tentou entregar a mensagem. Se a mensagem tiver vários destinatários, eles serão exibidos. Para mensagens de entrada enviadas para o Exchange Online, o valor é nulo.

### <a name="enhanced-summary-reports"></a>Relatórios de resumo aprimorados

Disponível (concluído) relatórios de resumo aprimorados estão disponíveis na seção de **relatórios que podem ser baixados** no rastreamento de mensagem de início. As informações a seguir estão disponíveis no relatório:

- **origin_timestamp** <sup>*</sup> : a data e a hora em que a mensagem foi inicialmente recebida pelo serviço, usando o fuso horário UTC configurado.

- **sender_address**: o endereço de email do remetente (domínio do*alias* @ *domain*).

- **Recipient_status**: o status da entrega da mensagem para o destinatário. Se a mensagem foi enviada para vários destinatários, mostrará todos os destinatários e o status correspondente de cada um, no formato: \<*email address*\> ## \<*status*\> . Por exemplo:

  - **# #Receive, Send** significa que a mensagem foi recebida pelo serviço e foi enviada para o destino desejado.

  - **# #Receive, Fail** significa que a mensagem foi recebida pelo serviço, mas a entrega ao destino pretendido falhou.

  - **# #Receive, entregar** significa que a mensagem foi recebida pelo serviço e foi entregue à caixa de correio do destinatário.

- **message_subject**: os primeiros 256 caracteres do campo **assunto** da mensagem.

- **TOTAL_BYTES**: o tamanho da mensagem em bytes, incluindo os anexos.

- **message_id**: esse valor é descrito na seção [ID da mensagem](#message-id) anteriormente neste tópico. Por exemplo, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.

- **network_message_id**: um valor de ID de mensagem exclusivo que persiste em todas as cópias da mensagem que podem ser criadas devido ao bifurcação ou à expansão do grupo de distribuição. Um valor de exemplo é `1341ac7b13fb42ab4d4408cf7f55890f` .

- **original_client_ip**: o endereço IP do cliente do remetente.

- **direcionalidade**: indica se a mensagem foi enviada de entrada (1) para a sua organização ou se foi enviada de saída (2) da sua organização.

- **connector_id**: o nome do conector de origem ou de destino. Para obter mais informações sobre conectores no Exchange Online, consulte [Configure Mail Flow using Connectors in Office 365](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).

- **delivery_priority** <sup>*</sup> : se a mensagem foi enviada com prioridade **alta**, **baixa**ou **normal** .

<sup>*</sup>Essas propriedades estão disponíveis somente em relatórios de resumo aprimorados.

### <a name="extended-reports"></a>Relatórios estendidos

Relatórios estendidos disponíveis (concluídos) estão disponíveis na seção **relatórios baixáveis** no início de rastreamento de mensagem. Praticamente todas as informações de um relatório de resumo avançado estão disponíveis em um relatório estendido (com exceção de **origin_timestamp** e **delivery_priority**). As seguintes informações adicionais estão disponíveis apenas em um relatório estendido:

- **client_ip**: o endereço IP do servidor de email ou cliente de mensagens que enviou a mensagem.

- **client_hostname**: o nome do host ou o FQDN do servidor de email ou cliente de mensagens que enviou a mensagem.

- **server_IP**: o endereço IP do servidor de origem ou de destino.

- **server_hostname**: o nome do host ou FQDN do servidor de destino.

- **source_context**: informações adicionais associadas ao campo **Source** . Por exemplo:

  - `Protocol Filter Agent`

  - `3489061114359050000`

- **origem**: o componente do Exchange Online responsável pelo evento. Por exemplo:

  - `AGENT`

  - `MAILBOXRULE`

  - `SMTP`

- **event_id**: elas correspondem aos valores de **eventos da mensagem** que são explicados na seção [localizar registros relacionados para esta mensagem](#find-related-records-for-this-message) .

- **internal_message_id**: um identificador de mensagem atribuído pelo servidor do Exchange Online que está processando a mensagem no momento.

- **recipient_address**: os endereços de email dos destinatários da mensagem. Vários endereços de email são separados pelo caractere de ponto-e-vírgula (;).

- **recipient_count**: o número total de destinatários na mensagem.

- **related_recipient_address**: usado com `EXPAND` , `REDIRECT` e `RESOLVE` eventos para exibir outros endereços de email de destinatário associados à mensagem.

- **referência**: Este campo contém informações adicionais para tipos específicos de eventos. Por exemplo:

  - **DSN**: contém o link de relatório, que é o valor de **message_id** da notificação de status de entrega associada (também conhecida como DSN, notificação de falha na entrega, NDR ou mensagem de devolução) se um DSN é gerado subsequentemente para esse evento. Se esta for uma mensagem DSN, este campo conterá o valor **message_id** da mensagem original para a qual o DSN foi gerado.

  - **Expand**: contém o valor **related_recipient_address** das mensagens relacionadas.

  - **Receive**: pode conter o valor de **message_id** da mensagem relacionada se a mensagem foi gerada por outros processos (por exemplo, regras de caixa de entrada).

  - **Send**: contém o valor de **internal_message_id** de qualquer mensagem de DSN.

  - **Transfer**: contém o valor de **internal_message_id** da mensagem que está sendo bifurcada (por exemplo, por conversão de conteúdo, limites de destinatário de mensagem ou agentes).

  - **MAILBOXRULE**: contém o valor de **internal_message_id** da mensagem de entrada que causou a regra de caixa de entrada gerar a mensagem de saída.

    Para outros tipos de eventos, esse campo geralmente está em branco.

- **return_path**: o endereço de email de retorno especificado pelo comando **mail from** que enviou a mensagem. Embora esse campo nunca fique vazio, ele pode ter o valor de endereço de remetente nulo representado como `<>` .

- **message_info**: informações adicionais sobre a mensagem. Por exemplo:

  - A data/hora de origem da mensagem em UTC para `DELIVER` e `SEND` eventos. A data/hora da origem é a hora em que a mensagem entrou pela primeira vez na organização do Exchange Online. O UTC data-hora é representado no formato de data e hora ISO 8601: `yyyy-mm-ddThh:mm:ss.fffZ` , onde `yyyy` = ano, `mm` = mês, `dd` = dia, `T` indica o início do componente de tempo, `hh` = hora, `mm` = minuto, `ss` = segundo, `fff` = frações de segundo e `Z` significa `Zulu` , que é outra maneira de indicar o UTC.

  - Erros de autenticação. Por exemplo, você pode ver o valor `11a` e o tipo de autenticação que foi usado quando ocorreu o erro de autenticação.

- **tenant_id**: um valor de GUID que representa a organização do Exchange Online (por exemplo, `39238e87-b5ab-4ef6-a559-af54c6b07b42` ).

- **original_server_ip**: o endereço IP do servidor original.

- **custom_data**: contém dados relacionados a tipos de eventos específicos. Para obter mais informações, consulte as seções a seguir.

#### <a name="custom_data-values"></a>custom_data valores

O campo **custom_data** de um `AGENTINFO` evento é usado por uma variedade de agentes do Exchange Online para registrar detalhes do processamento de mensagens. Alguns dos agentes mais interessantes são descritos nas seções a seguir.

#### <a name="spam-filter-agent"></a>Agente de filtro de spam

Um valor **custom_data** que começa com `S:SFA` é do agente Filtro de spam. Os principais detalhes são descritos na tabela a seguir:

****

|Valor|Descrição|
|---|---|
|`SFV=NSPM`|A mensagem foi marcada como não spam e enviada aos destinatários pretendidos.|
|`SFV=SPM`|A mensagem foi marcada como spam por filtragem antispam (também conhecida como filtragem de conteúdo).|
|`SFV=BLK`|A filtragem foi ignorada e a mensagem foi bloqueada, pois originou-se em um remetente bloqueado.|
|`SFV=SKS`|A mensagem foi marcada como spam antes de ser processada pela filtragem antispam. Isso inclui mensagens que atenderam a uma regra de fluxo de emails (também conhecida como uma regra de Transporte) para marcá-la automaticamente como spam e ignorar toda filtragem adicional.|
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

Um exemplo **custom_data** valor de uma mensagem filtrada para spam como este:

`S:SFA=SUM|SFV=SPM|IPV=CAL|SRV=BULK|SFS=470454002|SFS=349001|SCL=9|SCORE=-1|LIST=0|DI=SN|RD=ftmail.inc.com|H=ftmail.inc.com|CIP=98.129.140.74|SFP=1501|ASF=1|CTRY=US|CLTCTRY=|LANG=en|LAT=287|LAT=260|LAT=18;`

#### <a name="malware-filter-agent"></a>Agente de filtro de malware

Um valor **custom_data** que começa com `S:AMA` é do agente de filtro de malware. Os principais detalhes são descritos na tabela a seguir:

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

Um exemplo **custom_data** valor de uma mensagem que contém malware tem a seguinte aparência:

`S:AMA=SUM|v=1|action=b|error=|atch=1;S:AMA=EV|engine=M|v=1|sig=1.155.974.0|name=DOS/Test_File|file=filename;S:AMA=EV|engine=A|v=1|sig=201707282038|name=Test_File|file=filename`

#### <a name="transport-rule-agent"></a>Agente de regra de transporte

Um valor de **custom_data** que começa com `S:TRA` é do agente de regra de transporte para regras de fluxo de emails (também conhecidas como regras de transporte). Os principais detalhes são descritos na tabela a seguir:

****

|Valor|Descrição|
|---|---|
|`ETR|ruleId=<guid>`|A identificação da regra encontrou uma correspondência.|
|`St=<datetime>`|A data e a hora no UTC quando a correspondência da regra ocorreu.|
|`Action=<ActionDefinition>`|A ação que foi aplicada. Para obter uma lista de ações disponíveis, consulte [Mail Flow Rule Actions in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).|
|`Mode=<Mode>`|O modo da regra. Os valores válidos são:<ul><li>**Impor**: todas as ações da regra serão impostas.</li><li>**Testar com dicas de política:**: qualquer ação de dica de política será enviada, mas outras ações de imposição não serão aplicadas.</li><li>**Teste sem dicas de política**: as ações serão listadas em um arquivo de log, mas os remetentes não serão notificados de nenhuma maneira e as ações de imposição não serão aplicadas.</li></ul>|
|

Um exemplo **custom_data** valor de uma mensagem que coincida com as condições de uma regra de fluxo de emails tem a seguinte aparência:

`S:TRA=ETR|ruleId=19a25eb2-3e43-4896-ad9e-47b6c359779d|st=7/17/2017 12:31:25 AM|action=ApplyHtmlDisclaimer|sev=1|mode=Enforce`
