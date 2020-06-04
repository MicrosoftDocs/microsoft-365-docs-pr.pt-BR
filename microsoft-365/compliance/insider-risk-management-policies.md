---
title: Políticas de gerenciamento de risco do insider
description: Saiba mais sobre as políticas de gerenciamento de risco do insider no Microsoft 365
keywords: Microsoft 365, gerenciamento de risco do Insider, gerenciamento de riscos, conformidade
localization_priority: Normal
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: 827cffde0ff719d133830e10e958f04fe70fc9d6
ms.sourcegitcommit: 416a4b87bfd7e5aff80194b59b2776f054aa8eb5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2020
ms.locfileid: "44534923"
---
# <a name="insider-risk-management-policies"></a>Políticas de gerenciamento de risco do insider

As políticas de gerenciamento de risco do insider determinam quais funcionários estão no escopo e quais tipos de indicadores de risco estão configurados para alertas. Você pode criar rapidamente uma política que se aplica a todos os usuários em sua organização ou definir usuários individuais ou grupos para gerenciamento em uma política. As políticas dão suporte a prioridades de conteúdo para concentrar as condições de política em várias ou em Microsoft Teams, sites do SharePoint, tipos de confidencialidade de dados e rótulos de dados. Usando modelos, eles incluem indicadores de risco específicos e quanto peso são atribuídos dentro de uma política, determinando efetivamente o peso de cada gatilho de alerta na política. Políticas o Windows permite que você defina o intervalo de tempo para aplicar a política às atividades de alerta e é usado para determinar a duração da política após a ativação. O limite máximo de políticas é de cinco políticas ativas ao mesmo tempo. No entanto, é possível configurar políticas adicionais e ativar e desativar políticas, conforme necessário.

## <a name="policy-dashboard"></a>Painel de políticas

O **painel de políticas** permite ver rapidamente as políticas em sua organização e o status atual dos alertas associados a cada política.

- **Nome da política**: o nome atribuído à política no assistente de política.
- **Alertas ativos**: o número de alertas ativos para cada política.
- **Alertas confirmados**: o número total de alertas que resultaram em casos da política nos últimos 365 dias.
- **Ações executadas em alertas**: o número total de alertas que foram confirmados ou descartados pelos últimos 365 dias.
- **Eficácia da política**: a porcentagem determinada pelo total de alertas confirmados dividido pelo total de ações realizadas em alertas (que é a soma dos alertas que foram confirmados ou ignorados no último ano).
- **Ativo**: o status da ocorrência, *Sim* ou *não*.

![Painel de política de gerenciamento de risco do insider](../media/insider-risk-policy-dashboard.png)

## <a name="policy-templates"></a>Modelos de política

Os modelos de gerenciamento de risco do insider são condições de política predefinidas que definem os tipos de indicadores de risco monitorados por uma política. Cada política deve ter um modelo atribuído no assistente de criação de política antes que a política seja criada. Ao criar uma nova política de risco de insider, você escolherá um dos modelos a seguir.

### <a name="departing-employee-data-theft"></a>Como a parte do roubo de dados do funcionário

Quando os funcionários saem da sua organização, há indicadores de risco específicos geralmente associados ao roubo de dados por parte dos funcionários. Este modelo de política prioriza esses indicadores e focaliza a detecção e os alertas nessa área de risco. O roubo de dados para os funcionários de parte pode incluir o download de arquivos do SharePoint Online, a cópia de arquivos para dispositivos portáteis, como unidades USB, impressão de arquivos e cópia de dados para serviços de armazenamento e mensagens na nuvem pessoal próximo de suas datas de demissão e término de emprego. Este modelo prioriza os indicadores de risco relacionados a essas atividades e como eles se correlacionam com o status de emprego do funcionário.

>[!IMPORTANT]
>Ao usar esse modelo, você deve configurar um conector de RH da Microsoft 365 para importar periodicamente informações de data de demissão e de término para os funcionários de sua organização. Consulte o tópico [importar dados com o conector de RH](import-hr-data.md) para obter orientações passo a passo para configurar o Microsoft 365 HR Connector para sua organização.

### <a name="data-leaks"></a>Vazamentos de dados

A proteção de dados e a prevenção de vazamentos de dados é um desafio constante para a maioria das organizações, especialmente com o rápido aumento de novos dados criados por funcionários, dispositivos e serviços. Os funcionários são capacitados a criar, armazenar e compartilhar informações entre serviços e dispositivos que tornam o gerenciamento de vazamentos de dados cada vez mais complexo e difícil. Os vazamentos de dados podem incluir o compartilhamento acidental de informações fora de sua organização ou roubo de dados com más intenções. Em conjunto com uma política de prevenção de perda de dados (DLP) atribuída, esse modelo prioriza a detecção em tempo real de downloads suspeitos de dados do SharePoint Online, compartilhamento de arquivos e pastas, cópia de arquivos para dispositivos portáteis, como unidades USB, impressão de arquivos e cópia de dados para serviços de armazenamento e mensagens na nuvem pessoal.

Ao usar o modelo de **vazamentos de dados** , você deve atribuir uma política de DLP para acionar indicadores na política de risco do insider para alertas de alta gravidade em sua organização. Sempre que um alerta de alta gravidade é gerado por uma regra de política de DLP é adicionada ao log de auditoria do Office 365, as políticas de risco do insider criadas com esse modelo examinam automaticamente o alerta de DLP de alta gravidade. Se o alerta contiver um usuário de escopo definido na política de risco Insider, o alerta será processado pela política de risco Insider como um novo alerta e receberá uma severidade de risco e uma pontuação de risco do insider. Este alerta pode ser avaliado como parte do fluxo de trabalho de gerenciamento de risco do insider e adicionado a um caso de gerenciamento de risco do Insider, se necessário.

Ao criar ou modificar políticas de DLP para uso com políticas de gerenciamento de risco do Insider, considere as seguintes diretrizes:

- Priorizar eventos de exfiltration de dados e ser seletivo ao atribuir configurações de **relatórios de incidentes** como *alto* ao configurar regras em suas políticas de DLP. Por exemplo, o envio de documentos confidenciais por email para um concorrente conhecido deve *ser um evento* de nível de alerta exfiltration. A atribuição de excesso no nível *alto* nas configurações de **relatórios de incidentes** em outras regras de política de DLP pode aumentar o ruído no fluxo de trabalho de alerta de gerenciamento de risco do insider e dificultar a avaliação adequada desses alertas. Por exemplo, a atribuição de *altos* níveis de alerta ao bloqueio de atividades nas políticas de DLP torna mais desafiador avaliar o comportamento e as atividades do usuário verdadeiramente arriscados.
- Verifique se você entendeu e configurou corretamente os usuários no escopo nas políticas de gerenciamento de risco do DLP e do insider. Somente os usuários definidos como dentro do escopo para políticas de gerenciamento de risco do insider usando o modelo de **vazamentos de dados** terão alertas de política de DLP de alta gravidade processados. Além disso, somente usuários definidos como dentro do escopo em uma regra para um alerta de DLP de alta gravidade serão examinados pela política de gerenciamento de risco do insider para fins de avaliação. É importante que você não configure de forma desconhecida os usuários no escopo em suas políticas de risco do DLP e do insider de uma maneira conflitante.

     Por exemplo, se suas regras de política de DLP têm o escopo para apenas os usuários da equipe de vendas e a política de risco do insider criada a partir do modelo de **vazamentos de dados** tiver definido todos os usuários como dentro do escopo, a política de risco do insider só processará alertas de DLP de alta gravidade para os usuários da equipe de vendas. A política de risco Insider não receberá alertas de DLP de alta prioridade para que os usuários processem que não estejam definidos nas regras de DLP neste exemplo. Por outro lado, se sua política de gerenciamento de risco do insider criada a partir do modelo de **vazamentos de dados** tiver escopo somente para os usuários da equipe de vendas e a política de DLP atribuída estiver delimitada a todos os usuários, a política de risco de insider só processará alertas de DLP de alta gravidade para membros da equipe de vendas. A política de gerenciamento de risco do insider ignorará alertas de DLP de alta gravidade para todos os usuários que não estão na equipe de vendas.

- Certifique-se de que a configuração de regra **relatórios de incidentes** na política de DLP usada para este modelo de gerenciamento de risco do insider está configurada para alertas de *alto* nível O nível de severidade *alto* é o indicador de acionamento e os alertas de gerenciamento de risco do insider não serão gerados de regras nas políticas de DLP com o conjunto de campos **relatórios de incidentes** em *baixo* ou *médio*.

    ![Configuração de alerta de política DLP](../media/insider-risk-DLP-policy-high-severity.png)

     >[!NOTE]
     >Ao criar uma nova política de DLP usando os modelos internos, você precisará selecionar a opção **criar ou personalizar regras de DLP avançadas** para definir a configuração de **relatórios de incidentes** para o nível de severidade *alto* .

Cada política de gerenciamento de risco do insider criada a partir do modelo de **vazamentos de dados** pode ter apenas uma política de DLP atribuída. Considere a criação de uma política de DLP dedicada que combine as diferentes atividades que você deseja detectar e atuar como indicadores de acionamento para políticas de risco de insider que usam o modelo de **vazamento de dados** .

Consulte o tópico [criar, testar e ajustar uma política de DLP](create-test-tune-dlp-policy.md) para obter orientações passo a passo para configurar as políticas de DLP para sua organização.

### <a name="offensive-language-in-email"></a>Idioma ofensivo no email

Detectar e realizar ações para impedir o comportamento ofensivo e abusivo é um componente essencial da prevenção de riscos. Os classificadores de idiomas ofensivos internos no Microsoft 365 podem examinar mensagens de email enviadas de caixas de correio do Exchange Online em sua organização para diferentes tipos de problemas de conformidade. Esses classificadores usam uma combinação de inteligência artificial e palavras-chave para identificar o idioma em que o email provavelmente viola as políticas antiassédio. Use este modelo para criar rapidamente uma política que use esses classificadores para detectar automaticamente o conteúdo de mensagens de email que pode ser considerado abusivo ou ofensivo. O gerenciamento de risco do insider usa classificadores que verificam as mensagens de email enviadas para termos do idioma inglês e uma inversão para linguagem ofensiva.

## <a name="policy-settings"></a>Configurações de política

As configurações de risco do insider são aplicadas a todas as políticas de gerenciamento de risco do Insider, independentemente do modelo que você escolheu ao criar uma política. As configurações são definidas usando o controle de **configurações de risco do insider** localizado na parte superior de todas as guias de gerenciamento de risco do insider Essas configurações controlam a privacidade, indicadores, monitoramento de janelas e detecções inteligentes.

### <a name="privacy"></a>Privacidade

A proteção da privacidade dos usuários que têm correspondências de política é importante e pode ajudar a promover o Objectivity em análises de investigação e análise de dados para alertas de risco do insider. Para usuários com uma política de risco de insider correspondência, você pode escolher uma das seguintes configurações:

- **Mostrar versões anonimato de nomes de**usuário: os nomes de usuários são anônimos para impedir que administradores, investigadores de dados e revisores vejam quem está associado a alertas de política. Por exemplo, um "Taylor de cortesia" do usuário apareceria com um pseudonym aleatório, como "AnonIS8-988" em todas as áreas da experiência de gerenciamento de risco do insider. A escolha dessa configuração anonymizes todos os usuários com correspondências de política atuais e anteriores e se aplicam a todas as políticas. As informações de perfil de usuário no alerta de risco do insider e os detalhes do caso não estarão disponíveis quando essa opção for escolhida. No entanto, os nomes de usuário são exibidos ao adicionar novos usuários às políticas existentes ou ao atribuir usuários a novas políticas. Se você optar por desativar essa configuração, os nomes de usuário serão exibidos para todos os usuários que têm correspondências de política atuais ou antigas.
- **Não mostrar versões anonimato de nomes de usernames**: os nomes de usernames são exibidos para todas as correspondências de política atuais e anteriores para alertas e casos. As informações de perfil de usuário (o nome, título, alias e organização ou departamento) são exibidas para o usuário para todos os alertas e casos de gerenciamento de risco do insider.

### <a name="indicators"></a>Indicadores

Os modelos de política de risco do insider definem o tipo de atividades de risco que você deseja detectar e investigar. Cada modelo de política é baseado em indicadores específicos que correspondem a atividades e alertas de risco específicos são acionados por políticas quando os usuários executam atividades relacionadas a esses indicadores. Em alguns casos, talvez você queira limitar os indicadores aplicados às políticas de risco do insider em sua organização. Você pode desativar os indicadores para áreas específicas desabilitando-os de todas as políticas de risco do insider.

Para definir os indicadores habilitados em todas as políticas, navegue até indicadores de **configurações de risco do insider**  >  **Indicators** e selecione um ou mais indicadores. Os indicadores selecionados na página de configurações de **indicadores** não podem ser configurados individualmente ao criar ou editar uma política de risco Insider no assistente de política.

>[!IMPORTANT]
>Para receber alertas para atividades arriscadas definidas em suas políticas, você deve selecionar um ou mais indicadores antes de configurar uma política de risco de insider.

### <a name="policy-timeframes"></a>Cronogramas de política

Os cronogramas de política permitem definir períodos de revisão passados e futuros que são disparados após as correspondências de política com base em eventos e atividades para os modelos de política de gerenciamento de risco do insider. Dependendo do modelo de política escolhido, os seguintes cronogramas de política estão disponíveis:

- **Janela de ativação**: disponível para todos os modelos de política, a *janela de ativação* é o número definido de dias que a janela é ativada **após** um evento de acionamento. A janela é ativada por 1 a 30 dias após a ocorrência de um evento de acionamento para qualquer usuário atribuído à política. Por exemplo, você configurou uma política de gerenciamento de risco do insider e definiu a *janela de ativação* para 30 dias. Vários meses passaram desde que você configurou a política e um evento de acionamento ocorre para um dos usuários incluídos na política. O evento de acionamento ativa a *janela de ativação* e a política fica ativa para esse usuário por 30 dias após o evento de acionamento ter ocorrido.
- **Detecção de atividade passada**: disponível para todos os modelos de política, a *detecção de atividade passada* é o número definido de dias que a janela é ativada **antes** de um evento de acionamento. A janela é ativada para 0 a 180 dias antes da ocorrência de um evento de acionamento para qualquer usuário atribuído à política. Por exemplo, você configurou uma política de gerenciamento de risco do insider e definiu a *detecção de atividades passadas* para 90 dias. Vários meses passaram desde que você configurou a política e um evento de acionamento ocorre para um dos usuários incluídos na política. O evento de acionamento ativa a *detecção de atividade passada* e a política reúne as atividades históricas para esse usuário por 90 dias antes do evento de acionamento.

### <a name="intelligent-detections"></a>Detecções inteligentes

As configurações inteligentes de detecção ajudam a refinar o modo como as detecções de atividades arriscadas são processadas para alertas. Em determinadas circunstâncias, talvez seja necessário definir tipos de arquivos a serem ignorados ou você deseja impor um nível de detecção de arquivos para ajudar a definir uma barra mínima para alertas. Ao usar políticas de linguagem ofensivas, talvez seja necessário aumentar ou diminuir a sensibilidade à detecção para controlar a quantidade de correspondências de política relatadas. Use estas configurações para controlar o volume de alerta geral, as exclusões de tipo de arquivo, os limites de volume de arquivo e a confidencialidade da detecção de idioma ofensivo.

#### <a name="anomaly-detections"></a>Detecções de anomalias

As detecções anômalas incluem configurações de exclusões de tipo de arquivo e limites de volume de arquivo.

- **Exclusões de tipo de arquivo**: para excluir tipos de arquivo específicos de todas as políticas de gerenciamento de risco do Insider, insira as extensões de tipo de arquivo separadas por vírgulas. Por exemplo, para excluir determinados tipos de arquivos de música de correspondências de política, você pode inserir *AAC, mp3, WAV, WMA* no campo de **exclusões de tipo de arquivo** . Arquivos com essas extensões seriam ignorados por todas as políticas de gerenciamento de risco do insider.
- **Limite de corte de volume de arquivo**: para definir um nível mínimo de arquivo antes que os alertas de atividade sejam relatados nas políticas de risco do Insider, insira o número de arquivos. Por exemplo, você digitaria ' 10 ' se não quiser gerar alertas de risco Insider quando um usuário baixar 10 arquivos ou menos, mesmo que as políticas considerem uma anomalia.

#### <a name="offensive-language-detections"></a>Detecções de idiomas ofensivos

Para ajustar a sensibilidade do classificador de idiomas ofensivo para políticas usando o *idioma ofensivo no modelo de email* , escolha uma das seguintes configurações:

- Baixo: o nível mais baixo de sensibilidade com a mais ampla variedade de idiomas de detecção e de **insuficiência**ofensivas. A probabilidade de falsos positivos para a correspondência de linguagem ofensiva é elevada.
- **Médio**: o nível de sensibilidade de nível médio com um intervalo balanceado para detectar a linguagem e o inofensivos. A probabilidade de falsos positivos para a correspondência de linguagem ofensiva é média.
- **Alta**: o nível mais alto de sensibilidade com um intervalo estreito para detectar a linguagem e o indutos ofensivos. A probabilidade de falsos positivos para a correspondência de linguagem ofensiva é baixa.

#### <a name="alert-volume"></a>Volume do alerta

As atividades do usuário detectadas pelas políticas de risco do insider recebem uma pontuação de risco específica, que, por sua vez, determina a severidade do alerta (baixa, média, alta). Por padrão, geraremos uma determinada quantidade de alertas de severidade Baixa, média e alta, mas você pode aumentar ou diminuir o volume para atender às suas necessidades. Para ajustar o volume de alertas de todas as políticas de gerenciamento de risco do Insider, escolha uma das seguintes configurações:

- **Menos alertas**: você verá todos os alertas de alta gravidade, menos alertas de severidade médias e nenhuma severidade baixa. Esse nível de configuração significa que você pode perder alguns verdadeiros positivos.
- **Volume padrão**: você verá todos os alertas de alta gravidade e uma quantidade equilibrada de alertas de severidade médio e baixa.
- **Mais alertas**: você verá todos os alertas de severidade média e alta e os alertas de severidade mais baixos. Esse nível de configuração pode resultar em mais falsos positivos.

## <a name="create-a-new-policy"></a>Criar uma nova política

Para criar uma nova política de gerenciamento de risco do Insider, você usará o assistente de política na solução de **Gerenciamento de risco do insider** no centro de conformidade da Microsoft 365.

Conclua as seguintes etapas para criar uma nova política:

1. No [centro de conformidade da Microsoft 365](https://compliance.microsoft.com), vá para gerenciamento de **risco do insider** e selecione a guia **políticas** .
2. Selecione **criar política** para abrir o assistente de política
3. Na página **nomear sua política e escolher um modelo** , preencha os seguintes campos:
    - **Nome (obrigatório)**: Insira um nome amigável para a política
    - **Descrição (opcional)**: Insira uma descrição para a política.
    - **Escolher modelo de política (obrigatório)**: selecione um dos [modelos de política](insider-risk-management-policies.md#policy-templates) para definir os tipos de indicadores de risco são monitorados pela política.

    >[!IMPORTANT]
    >Se você selecionar o modelo *vazamentos de dados* , precisará configurar pelo menos uma política DLP que será atribuída posteriormente no assistente. Se você selecionar o modelo de *roubo de dados do funcionário de parte* , precisará configurar o conector de RH para usar os recursos de detecção de sinal completo do modelo de política.

4. Selecione **Avançar** para continuar.
5. Na página **escolher usuários e grupos** , selecione **escolher usuários ou grupos** para definir quais usuários estão incluídos na política ou selecione a caixa de seleção **todos os usuários e grupos habilitados para email** . Selecione **Avançar** para continuar.
6. Na página **especificar qual conteúdo priorizar (opcional)** , você pode atribuir pontuações de risco mais altos à atividade detectada com base em onde o conteúdo relacionado está localizado, quais informações confidenciais estão incluídas e quais rótulos de confidencialidade são aplicados:
    - Sites do SharePoint: selecione **escolher sites do SharePoint** e selecione as organizações do SharePoint que você deseja priorizar. Por exemplo, *"group1@contoso.sharepoint.com/sites/group1"*.
    - Tipo de informação confidencial: selecione **escolher tipos de informações confidenciais** e selecione os tipos de sensibilidade que você deseja priorizar. Por exemplo, *"número de conta bancária dos EUA"* e *"número do cartão de crédito"*.
    - Rótulos de sensibilidade: selecione **escolher rótulos de sensibilidade** e selecione os rótulos que você deseja priorizar. Por exemplo, *"confidencial"* e *"segredo"*.
7. Selecione **Avançar** para continuar.
8. Na página **indicadores de alerta** , você verá os indicadores definidos na página de indicadores de **configurações de risco do insider**  >  **Indicators** . Se você selecionou o modelo *vazamentos de dados* no início do assistente, deverá selecionar uma política de DLP na lista suspensa **política de DLP** .
9. Na página **selecionar janela de monitoramento** , você verá as [condições da janela de monitoramento](insider-risk-management-policies.md#policy-timeframes) da política que você configurou nas configurações de risco do insider. Se você tiver selecionado o modelo de política de *roubo de dados do funcionário* de cancelamento de parte, poderá marcar a caixa de seleção *verificar término da postagem de atividade* para detectar a atividade após a data de término importada do conector de RH da Microsoft 365.
10. Selecione **Avançar** para continuar.
11. Na página **revisão** , revise as configurações escolhidas para a política. Selecione **Editar** para alterar qualquer um dos valores da política ou selecione **Enviar** para criar e ativar a política.

## <a name="update-a-policy"></a>Atualizar uma política

Para atualizar uma política de gerenciamento de risco do insider existente, você usará o assistente de política na solução de **Gerenciamento de risco do insider** no centro de conformidade da Microsoft 365.

Conclua as seguintes etapas para gerenciar uma política existente:

1. No [centro de conformidade da Microsoft 365](https://compliance.microsoft.com), vá para gerenciamento de **risco do insider** e selecione a guia **políticas** .
2. No painel de políticas, selecione a política que você deseja gerenciar.
3. Na página detalhes da política, selecione **Editar política**
4. No assistente de política, não é possível editar os seguintes campos:
    - **Nome**: o nome amigável da política
    - **Selecione o guia estratégico**: o modelo usado para definir os tipos de indicadores de risco monitorados pela política.
5. Insira uma nova descrição para a política no campo **Descrição** . Selecione **Avançar** para continuar.
6. Na página **escolher usuários e grupos** , selecione **escolher usuários ou grupos** para definir quais usuários estão incluídos na política ou selecione a caixa de seleção **todos os usuários e grupos habilitados para email** . Selecione **Avançar** para continuar
7. Na página **especificar qual conteúdo priorizar (opcional)** , atualize as fontes para priorizar as atividades arriscadas do usuário:
    - Sites do SharePoint: selecione **escolher sites do SharePoint** e selecione as organizações do SharePoint que você deseja priorizar. Por exemplo, *"group1@contoso.sharepoint.com/sites/group1"*.
    - Tipo de informação confidencial: selecione **escolher tipos de informações confidenciais** e selecione os tipos de sensibilidade que você deseja priorizar. Por exemplo, *"número de conta bancária dos EUA"* e *"número do cartão de crédito"*.
    - Rótulos de sensibilidade: selecione **escolher rótulos de sensibilidade** e selecione os rótulos que você deseja priorizar. Por exemplo, *"confidencial"* e *"segredo"*.
8. Selecione **Avançar** para continuar.
9. Na página **indicadores de alerta** , você verá os indicadores definidos na página de indicadores de **configurações de risco do insider**  >  **Indicators** . Se você selecionou o modelo *vazamentos de dados* no início do assistente, deverá selecionar uma política de DLP na lista suspensa **política de DLP** .
10. Na página **selecionar janela de monitoramento** , você verá as [condições da janela de monitoramento](insider-risk-management-policies.md#policy-timeframes) da política que você configurou nas configurações de risco do insider. Se você tiver selecionado o modelo de política de *roubo de dados do funcionário* de cancelamento de parte, poderá marcar a caixa de seleção *verificar término da postagem de atividade* para detectar a atividade após a data de término importada do conector de RH da Microsoft 365.
11. Na página **revisão** , revise as configurações escolhidas para a política. Selecione **Editar** para alterar qualquer um dos valores da política ou selecione **Enviar** para atualizar e ative as alterações na política.

## <a name="delete-a-policy"></a>Excluir uma política

>[!NOTE]
>A exclusão de uma política não exclui alertas ativos ou arquivados gerados da política.

Para excluir uma política de gerenciamento de risco do insider existente, conclua as seguintes etapas:

1. No [centro de conformidade da Microsoft 365](https://compliance.microsoft.com), vá para gerenciamento de **risco do insider** e selecione a guia **políticas** .
2. No painel de políticas, selecione a política que você deseja gerenciar.
3. Selecione **excluir** na barra de ferramentas do painel.
4. Na caixa de diálogo **excluir** , selecione **Sim** para excluir a política ou selecione **Cancelar** para fechar a caixa de diálogo.
