---
title: Configurações de gerenciamento de risco do insider
description: Saiba mais sobre as configurações de gerenciamento de risco do insider no Microsoft 365
keywords: Microsoft 365, gerenciamento de risco do Insider, gerenciamento de riscos, conformidade
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: 8c56b7b597ea76c74412f49afa896a0d2f1b69a1
ms.sourcegitcommit: 4ee683c18442386f6fc5c76ffabfad2c28b81d42
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48214900"
---
# <a name="get-started-with-insider-risk-management-settings"></a>Introdução às configurações de gerenciamento de risco do insider

As configurações de gerenciamento de riscos do insider aplicam-se a todas as políticas de gerenciamento de risco do Insider, independentemente do modelo escolhido durante a criação As configurações são definidas usando o controle de **configurações de risco do insider** localizado na parte superior de todas as guias de gerenciamento de risco do insider Estas configurações controlam componentes de política para as seguintes áreas:

- Privacidade
- Indicadores
- Cronogramas de política
- Detecções inteligentes
- Exportar alertas (versão prévia)
- Grupos de usuários de prioridade (visualização)
- Prioridade de ativos físicos (versão prévia)
- Fluxos automatizados de energia (visualização)
- Microsoft Teams (visualização)

Antes de começar e criar políticas de gerenciamento de risco do Insider, é importante entender essas configurações e escolher a configuração dos níveis mais adequados para as necessidades de conformidade da sua organização.

## <a name="privacy"></a>Privacidade

A proteção da privacidade dos usuários que têm correspondências de política é importante e pode ajudar a promover o Objectivity em análises de investigação e análise de dados para alertas de risco do insider. Para usuários com uma política de risco de insider correspondência, você pode escolher uma das seguintes configurações:

- **Mostrar versões de nomes de usuário anônimos**: os nomes de usuários são anônimos para impedir que administradores, investigadores de dados e revisores vejam quem está associado aos alertas de política. Por exemplo, um "Taylor de cortesia" do usuário apareceria com um pseudonym aleatório, como "AnonIS8-988" em todas as áreas da experiência de gerenciamento de risco do insider. A escolha dessa configuração anonymizes todos os usuários com correspondências de política atuais e anteriores e se aplicam a todas as políticas. As informações de perfil de usuário no alerta de risco do insider e os detalhes do caso não estarão disponíveis quando essa opção for escolhida. No entanto, os nomes de usuário são exibidos ao adicionar novos usuários às políticas existentes ou ao atribuir usuários a novas políticas. Se você optar por desativar essa configuração, os nomes de usuário serão exibidos para todos os usuários que têm correspondências de política atuais ou antigas.
- **Não mostrar versões anonimato de nomes de usernames**: os nomes de usernames são exibidos para todas as correspondências de política atuais e anteriores para alertas e casos. As informações de perfil de usuário (o nome, título, alias e organização ou departamento) são exibidas para o usuário para todos os alertas e casos de gerenciamento de risco do insider.

![Configurações de privacidade de gerenciamento de risco do insider](../media/insider-risk-settings-privacy.png)

## <a name="indicators"></a>Indicadores

Os modelos de política de risco do insider definem o tipo de atividades de risco que você deseja detectar e investigar. Cada modelo de política é baseado em indicadores específicos que correspondem a gatilhos e atividades de risco específicos. Todos os indicadores estão desabilitados por padrão e você deve selecionar um ou mais indicadores de política antes de configurar uma política de gerenciamento de risco do insider.

Os alertas são acionados por políticas quando os usuários executam atividades relacionadas a indicadores de política que atendem a um limite obrigatório. O gerenciamento de riscos do insider usa dois tipos de indicadores:

- **Eventos de acionamento**: eventos que determinam se um usuário está ativo para uma política de gerenciamento de risco do insider. Se um usuário é adicionado a uma política de gerenciamento de risco do insider não tem um evento de disparo, a atividade do usuário não é avaliada pela política. Por exemplo, o usuário A é adicionado a uma política criada a partir do *roubo de dados por* meio do modelo de política de usuários, e a política e o conector de RH da Microsoft 365 estão configurados corretamente. Até que o usuário A tenha uma data de término relatada pelo conector de RH, as atividades do usuário A não são avaliadas por essa política de gerenciamento de risco do insider. Outro exemplo de evento de acionamento é se um usuário tem um alerta de política de DLP de *alta* gravidade ao usar políticas de *vazamentos de dados* .
- **Indicadores de política**: indicadores incluídos nas políticas de gerenciamento de risco do insider usados para determinar a pontuação de risco de um usuário no escopo. Estes indicadores de política são ativados somente depois que ocorre um evento de acionamento para um usuário. Alguns exemplos de indicadores de política são quando um usuário copia dados para os serviços de armazenamento em nuvem pessoal ou dispositivos de armazenamento portátil, ou se um usuário compartilha arquivos e pastas internos com partes externas não autorizadas.

Os indicadores de política são segmentados nas seguintes áreas. Você pode escolher os indicadores para ativar e personalizar limites de eventos de indicador para cada nível de indicador ao criar uma política de risco de insider:

- **Indicadores do Office**: eles incluem indicadores de política para sites, equipes e mensagens de email do SharePoint.
- **Indicadores de dispositivo**: incluem indicadores de política para atividades como compartilhamento de arquivos pela rede ou com dispositivos. Os indicadores incluem atividade envolvendo arquivos do Microsoft Office. Arquivos CSV e. Arquivos PDF. Se você selecionar **indicadores de dispositivo**, Activity será processada somente para dispositivos com o Windows 10 Build 1809 ou superior. Para obter mais informações sobre a configuração de dispositivos para integração com o Insider, consulte [Getting Started with Endpoint DLP](endpoint-dlp-getting-started.md).
- **Indicador de violação de política de segurança**: isso inclui indicadores do Microsoft defender ATP relacionados à instalação de software mal-intencionado ou não aprovado ou bypass de controles de segurança. Para receber alertas no gerenciamento de risco do Insider, você deve ter uma licença do Microsoft defender ATP ativa e uma integração de risco Insider habilitada. Para obter mais informações sobre como configurar o Microsoft defender ATP para integração do gerenciamento de risco do Insider, consulte [configurar recursos avançados no Microsoft defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-features\#share-endpoint-alerts-with-microsoft-compliance-center).
- **Aceleradores de Pontuação de risco**: isso inclui elevar a pontuação de risco de atividades incomuns ou violações de política passadas. Habilitar os aceleradores de Pontuação de risco aumentam as pontuações de risco e a probabilidade de alertas desses tipos de atividades. Os aumentos de Pontuação de risco só poderão ser selecionados se um ou mais indicadores acima estiverem selecionados.

![Configurações do indicador de gerenciamento de risco do insider](../media/insider-risk-settings-indicators.png)

Em alguns casos, talvez você queira limitar os indicadores de política de risco do insider aplicados às políticas de risco do insider em sua organização. Você pode desativar os indicadores de política para áreas específicas desabilitando-os de todas as políticas de risco do insider. Eventos de acionamento não podem ser modificados para modelos de política de risco do insider.

Para definir os indicadores de política de risco do insider habilitados em todas as políticas de riscos Insider, navegue até indicadores de **configurações de risco**do insider  >  **Indicators** e selecione um ou mais indicadores de política. Os indicadores selecionados na página de configurações de indicadores não podem ser configurados individualmente ao criar ou editar uma política de risco Insider no assistente de política.

>[!NOTE]
>Pode levar várias horas para que novos usuários adicionados manualmente apareçam no **painel usuários**. As atividades dos últimos 90 dias para esses usuários podem levar até 24 horas para serem exibidas. Para exibir as atividades de usuários adicionados manualmente, selecione o usuário no **painel usuários** e abra a guia **atividade do usuário** no painel de detalhes.

### <a name="indicator-level-settings-preview"></a>Configurações de nível de indicador (versão prévia)

Ao criar uma política no assistente de política, você pode configurar como o número diário de eventos de risco deve influenciar a pontuação de risco dos alertas de risco do insider. Essas configurações do indicador ajudam a controlar como o número de ocorrências de eventos de risco em sua organização deve afetar a pontuação de risco e, conseqüentemente, a severidade de alerta associada a esses eventos. Se preferir, você também pode optar por manter os níveis de limite de eventos padrão recomendados pela Microsoft para todos os indicadores habilitados.

Por exemplo, você decide habilitar os indicadores do SharePoint nas configurações de política de risco do insider e definir limites personalizados para eventos do SharePoint ao configurar indicadores para uma nova política de *vazamento de dados* de risco Insider. Enquanto estiver no assistente de política de risco do Insider, você configurará três diferentes níveis de eventos diários para cada indicador do SharePoint para influenciar a pontuação de risco dos alertas associados a esses eventos.

![Configurações do indicador personalizado de gerenciamento de risco do insider](../media/insider-risk-custom-indicators.png)

Para o primeiro nível de evento diário, você define o limite em *10 ou mais eventos por dia* para um impacto menor na pontuação de risco dos eventos, *20 ou mais eventos por dia* para um impacto médio na pontuação de risco dos eventos e *30 ou mais eventos por dia* um impacto maior na pontuação de risco dos eventos. Essas configurações significam efetivamente:

- Se houver 1-9 eventos do SharePoint que ocorrem após o evento de acionamento, as pontuações de risco são impactados minimamente e tendem a não gerar um alerta.
- Se houver 10-19 eventos do SharePoint que ocorrem após um evento de acionamento, a pontuação de risco será inerentemente inferior, e os níveis de severidade de alerta tendem a estar em um nível baixo.
- Se houver 20-29 eventos do SharePoint que ocorrem após um disparador, a pontuação de risco é inerentemente superior, e os níveis de severidade de alerta tendem a estar em um nível médio.
- Se houver 30 ou mais eventos do SharePoint que ocorrem depois de um disparador, a pontuação de risco será inerentemente superior, e os níveis de severidade de alerta tendem a estar em um nível alto.

## <a name="policy-timeframes"></a>Cronogramas de política

Os cronogramas de política permitem definir períodos de revisão passados e futuros que são disparados após as correspondências de política com base em eventos e atividades para os modelos de política de gerenciamento de risco do insider. Dependendo do modelo de política escolhido, os seguintes cronogramas de política estão disponíveis:

- **Janela de ativação**: disponível para todos os modelos de política, a *janela de ativação* é o número definido de dias que a janela é ativada **após** um evento de acionamento. A janela é ativada por 1 a 30 dias após a ocorrência de um evento de acionamento para qualquer usuário atribuído à política. Por exemplo, você configurou uma política de gerenciamento de risco do insider e definiu a *janela de ativação* para 30 dias. Vários meses passaram desde que você configurou a política e um evento de acionamento ocorre para um dos usuários incluídos na política. O evento de acionamento ativa a *janela de ativação* e a política fica ativa para esse usuário por 30 dias após o evento de acionamento ter ocorrido.
- **Detecção de atividade passada**: disponível para todos os modelos de política, a *detecção de atividade passada* é o número definido de dias que a janela é ativada **antes** de um evento de acionamento. A janela é ativada para 0 a 180 dias antes da ocorrência de um evento de acionamento para qualquer usuário atribuído à política. Por exemplo, você configurou uma política de gerenciamento de risco do insider e definiu a *detecção de atividades passadas* para 90 dias. Vários meses passaram desde que você configurou a política e um evento de acionamento ocorre para um dos usuários incluídos na política. O evento de acionamento ativa a *detecção de atividade passada* e a política reúne as atividades históricas para esse usuário por 90 dias antes do evento de acionamento.

![Configurações de período de gerenciamento de risco do insider](../media/insider-risk-settings-timeframes.png)

## <a name="intelligent-detections"></a>Detecções inteligentes

As configurações inteligentes de detecção ajudam a refinar o modo como as detecções de atividades arriscadas são processadas para alertas. Em determinadas circunstâncias, talvez seja necessário definir tipos de arquivos a serem ignorados ou você deseja impor um nível de detecção de arquivos para ajudar a definir uma barra mínima para alertas. Ao usar políticas de linguagem ofensivas, talvez seja necessário aumentar ou diminuir a sensibilidade à detecção para controlar a quantidade de correspondências de política relatadas. Use estas configurações para controlar o volume de alerta geral, as exclusões de tipo de arquivo, os limites de volume de arquivo e a confidencialidade da detecção de idioma ofensivo.

![Configurações de detecções inteligentes de gerenciamento de risco do insider](../media/insider-risk-settings-detections.png)

### <a name="anomaly-detections"></a>Detecções de anomalias

As detecções anômalas incluem configurações de exclusões de tipo de arquivo e limites de volume de arquivo.

- **Exclusões de tipo de arquivo**: para excluir tipos de arquivo específicos de todas as políticas de gerenciamento de risco do Insider, insira as extensões de tipo de arquivo separadas por vírgulas. Por exemplo, para excluir determinados tipos de arquivos de música de correspondências de política, você pode inserir *AAC, mp3, WAV, WMA* no campo de **exclusões de tipo de arquivo** . Arquivos com essas extensões seriam ignorados por todas as políticas de gerenciamento de risco do insider.
- **Limite de recorte de volume de arquivo**: para definir um nível mínimo de arquivo antes que os alertas de atividade sejam relatados nas políticas de risco do Insider, insira o número de arquivos. Por exemplo, você digitaria ' 10 ' se não quiser gerar alertas de risco Insider quando um usuário baixar 10 arquivos ou menos, mesmo que as políticas considerem uma anomalia.

### <a name="offensive-language-detections"></a>Detecções de idiomas ofensivos

>[!IMPORTANT]
>A partir de 16 de outubro de 2020, você não poderá mais criar políticas usando esse modelo. As políticas ativas que usam esse modelo funcionarão até que sejam permanentemente removidas em janeiro de 2021. Estamos preterindo o classificador interno de idioma ofensivo que oferece suporte a esse modelo, pois ele está produzindo um grande número de falsos positivos. Para resolver problemas de risco para linguagem ofensiva, recomendamos o uso de políticas de [conformidade de Comunicação](communication-compliance.md) do Microsoft 365. Para obter mais informações sobre classificadores internos, confira [introdução aos classificadores estagiários](classifier-get-started-with.md).

Para ajustar a sensibilidade do classificador de idiomas ofensivo para políticas usando o *idioma ofensivo no modelo de email* , escolha uma das seguintes configurações:

- Baixo: o nível mais baixo de sensibilidade com a mais ampla variedade de idiomas de detecção e de **insuficiência**ofensivas. A probabilidade de falsos positivos para a correspondência de linguagem ofensiva é elevada.
- **Médio**: o nível de sensibilidade de nível médio com um intervalo balanceado para detectar a linguagem e o inofensivos. A probabilidade de falsos positivos para a correspondência de linguagem ofensiva é média.
- **Alta**: o nível mais alto de sensibilidade com um intervalo estreito para detectar a linguagem e o indutos ofensivos. A probabilidade de falsos positivos para a correspondência de linguagem ofensiva é baixa.

### <a name="alert-volume"></a>Volume do alerta

As atividades do usuário detectadas pelas políticas de risco do insider recebem uma pontuação de risco específica, que, por sua vez, determina a severidade do alerta (baixa, média, alta). Por padrão, geraremos uma determinada quantidade de alertas de severidade Baixa, média e alta, mas você pode aumentar ou diminuir o volume para atender às suas necessidades. Para ajustar o volume de alertas de todas as políticas de gerenciamento de risco do Insider, escolha uma das seguintes configurações:

- **Menos alertas**: você verá todos os alertas de alta gravidade, menos alertas de severidade médias e nenhuma severidade baixa. Esse nível de configuração significa que você pode perder alguns verdadeiros positivos.
- **Volume padrão**: você verá todos os alertas de alta gravidade e uma quantidade equilibrada de alertas de severidade médio e baixa.
- **Mais alertas**: você verá todos os alertas de severidade média e alta e os alertas de severidade mais baixos. Esse nível de configuração pode resultar em mais falsos positivos.

### <a name="microsoft-defender-advanced-threat-protection-preview"></a>Proteção avançada contra ameaças do Microsoft defender (versão prévia)

A [proteção avançada contra ameaças do Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) (ATP) é uma plataforma de segurança de ponto de extremidade empresarial projetada para ajudar as redes corporativas a prevenir, detectar, investigar e responder a ameaças avançadas. Para ter melhor visibilidade da violação de segurança em sua organização, você pode importar e filtrar os alertas do Microsoft defender ATP para atividades usadas em políticas criadas a partir de modelos de política de violação de segurança de gerenciamento de risco do insider.

Dependendo dos tipos de sinais nos quais você está interessado, você pode optar por importar alertas para o gerenciamento de risco do insider com base no status de triagem de alerta do Microsoft defender ATP. Você pode definir um ou mais dos seguintes status de triagem de alerta nas configurações globais para importar:

- Desconhecido
- Novo
- Em andamento
- Resolvido

Os alertas do Microsoft defender ATP são importados diariamente. Dependendo do status de triagem escolhido, você poderá ver várias atividades do usuário para o mesmo alerta, pois o status da triagem será alterado no Microsoft defender ATP.

Por exemplo, se você selecionar *novo*, *em andamento*e *resolvido* para esta configuração, quando um alerta ATP do Microsoft defender for gerado e o status for *novo*, uma atividade de alerta inicial será importada para o usuário em risco de insider. Quando o status de triagem do Microsoft defender ATP é alterado para *em andamento*, uma segunda atividade para este alerta é importada para o usuário em risco do insider. Quando o status de triagem do Microsoft defender ATP é definido, uma terceira atividade desse *alerta é* importada para o usuário em risco do insider. Essa funcionalidade permite que os investigadores sigam a progressão dos alertas do Microsoft defender ATP e escolha o nível de visibilidade exigido por sua investigação.

>[!IMPORTANT]
>Você precisará ter o Microsoft defender ATP configurado em sua organização e habilitar o Microsoft defender ATP para integração de gerenciamento de risco do insider na central de segurança do defender para importar alertas de violação de segurança. Para obter mais informações sobre como configurar o Microsoft defender ATP para integração do gerenciamento de risco do Insider, consulte [configurar recursos avançados no Microsoft defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-features\#share-endpoint-alerts-with-microsoft-compliance-center).

### <a name="domains-preview"></a>Domínios (versão prévia)

As configurações de domínio ajudam a definir níveis de risco para comunicações com domínios específicos. Essas comunicações incluem compartilhamento de arquivos, mensagens de email ou download de conteúdo. Ao especificar domínios nessas configurações, você pode aumentar ou diminuir a pontuação de risco para atividades que ocorrem com esses domínios. Por exemplo, para especificar o contoso.com e o sales.wingtiptoys.com como domínios permitidos, você irá inserir ' contoso.com sales.wingtiptoys.com ' no campo **domínios permitidos** .

Para cada uma das seguintes configurações de domínio, você pode inserir até 500 domínios:

- **Domínios não permitidos:** Ao especificar domínios não permitidos, a atividade que ocorre com esses domínios terá uma pontuação *maior* de riscos.
- **Domínios permitidos:** Especificando domínios permitidos em configurações, a atividade que ocorre com esses domínios terá uma pontuação de risco *menor* e será tratada da mesma forma que a atividade de organização interna é tratada. Por exemplo, as atividades de email para esses domínios são analisadas da mesma forma que a atividade de email interno é analisada.
- **Domínios de terceiros:** Domínios de terceiros são domínios usados para fins de negócios em sua organização e conteúdo confidencial pode ser armazenado nesses locais. Ao especificar um domínio de terceiros, você pode receber alertas para qualquer atividade arriscada nesses domínios.

## <a name="export-alerts-preview"></a>Exportar alertas (versão prévia)

As informações de alerta do insider Risk Management são exportáveis para serviços de informações de segurança e SIEM (gerenciamento de eventos) por meio do [esquema da API da atividade de gerenciamento do Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#security-and-compliance-alerts-schema). Você pode usar as APIs de atividade de gerenciamento do Office 365 para exportar informações de alerta para outros aplicativos que sua organização pode usar para gerenciar ou agregar informações de risco do insider.

Para usar as APIs para analisar informações de alerta de risco do insider:

1. Habilitar o suporte à API de gerenciamento do Office 365 na exportação de configurações de **Gerenciamento de risco do insider**  >  **Settings**  >  **Export**. Por padrão, essa configuração é desabilitada para sua organização do Microsoft 365.
2. Filtrar as atividades de auditoria comuns do Office 365 por *SecurityComplianceAlerts*.
3. Filtra *SecurityComplianceAlerts* pela categoria *InsiderRiskManagement* .

![Configurações de alerta de exportação do insider Risk Management](../media/insider-risk-settings-export.png)

As informações de alerta contêm informações sobre o esquema de alerta de segurança e conformidade e o esquema comum da API da atividade de gerenciamento do Office 365.

Os seguintes campos e valores são exportados para alertas de gerenciamento de risco do insider para o esquema de alerta de conformidade de & de segurança:

| **Parâmetro de alerta** | **Descrição** |
|:------------------|:----------------|
| AlertType | O tipo do alerta é *personalizado*.  |
| AlertId | O GUID do alerta. Os alertas de gerenciamento de risco do insider são mutáveis. À medida que o status do alerta é alterado, um novo log com o mesmo Alertid é gerado. Este Alertid pode ser usado para correlacionar as atualizações de um alerta. |
| Categoria | A categoria do alerta é *InsiderRiskManagement*. Essa categoria pode ser usada para distinguir esses alertas de outros alertas de segurança & de conformidade. |
| Comentários | Comentários padrão para o alerta. Os valores são um *alerta novo* (registrado quando um alerta é criado) e o *alerta é atualizado* (registrado quando há uma atualização para um alerta). Use o Alertid para correlacionar as atualizações de um alerta. |
| Dados | Os dados para o alerta incluem a ID de usuário exclusiva, o nome principal do usuário e a data e hora (UTC) quando o usuário foi disparado em uma política. |
| Nome | Nome da política para a política de gerenciamento de risco do insider que gerou o alerta. |
| PolicyId | O GUID da política de gerenciamento de risco do insider que disparou o alerta. |
| Severity | A gravidade do alerta. Os valores são *alto*, *médio*ou *baixo*. |
| Origem | A origem do alerta. O valor é o *Office 365 Security & Compliance*. |
| Status | O status do alerta. Os valores estão *ativos* (*precisa de revisão* em risco do insider), *investigando* (*confirmado* em risco do insider), *resolvidos* (*resolvidos* no risco do insider), *ignorados* (*descartados* em risco do insider). |
| Versão | A versão do esquema de alerta de segurança e conformidade. |

Os seguintes campos e valores são exportados para alertas de gerenciamento de risco do insider para o [esquema comum da API da atividade de gerenciamento do Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema).

- UserId
- Id
- RecordType
- CreationTime
- Operação
- OrganizationId
- UserType
- UserKey

## <a name="priority-user-groups-preview"></a>Grupos de usuários de prioridade (visualização)

Os usuários da sua organização podem ter níveis diferentes de risco dependendo da sua posição, nível de acesso a informações confidenciais ou histórico de riscos. A priorização do exame e da Pontuação das atividades desses usuários pode ajudar a alertá-lo sobre possíveis riscos que podem ter conseqüências maiores para a sua organização. Os grupos de usuários de prioridade na ajuda do gerenciamento de risco do insider definem os usuários em sua organização que precisam de inspeção mais próxima e uma pontuação de risco mais confidencial Em conjunto com as *violações de política de segurança por usuários de prioridade* e *vazamentos de dados por* modelos de política de usuários de prioridade, os usuários adicionados a um grupo de usuários de prioridade têm uma maior probabilidade de alertas de risco e alertas do insider com níveis de severidade mais altos.

![Configurações de grupo de usuários de prioridade de gerenciamento de risco](../media/insider-risk-settings-priority-users.png)

Por exemplo, você precisa se proteger contra vazamentos de dados para um projeto altamente confidencial, onde os usuários têm acesso a informações confidenciais. Você opta por criar um grupo de usuários de prioridade de *usuários* *confidenciais do projeto* para usuários em sua organização que funcionem neste projeto. Usando o assistente de política e o modelo de política de *perda de dados por usuários de prioridade* , você cria uma nova política e atribui o grupo usuários de prioridade usuários de *projetos confidenciais* à política. As atividades examinadas pela política para os membros do grupo de usuário de prioridade de *usuários confidenciais do projeto* são mais confidenciais em risco e atividades por esses usuários terão mais chances de gerar um alerta e ter alertas com níveis de severidade mais altos.

### <a name="create-a-priority-user-group"></a>Criar um grupo de usuários de prioridade

Para criar um novo grupo de usuários de prioridade, você usará os controles de configuração na solução de **Gerenciamento de risco do insider** no centro de conformidade do Microsoft 365. Para criar um grupo de usuários de prioridade, você deve ser membro do grupo de função *Gerenciamento de risco do insider* ou *administrador de gerenciamento de risco do insider* .

Conclua as etapas a seguir para criar um grupo de usuários de prioridade:

1. No [centro de conformidade da Microsoft 365](https://compliance.microsoft.com), vá para gerenciamento de **risco do insider** e selecione **configurações de risco do insider**.
2. Selecionar a guia **grupos de usuários de prioridade**
3. Na guia **grupos de usuários de prioridade** , selecione **Criar grupo de prioridade de usuário** para iniciar o assistente de criação de grupo.
4. Na página **definir grupo** , preencha os seguintes campos:
    - **Nome (obrigatório)**: Insira um nome amigável para o grupo de usuários de prioridade. Você não pode alterar o nome do grupo de usuários de prioridade após concluir o assistente.
    - **Descrição (opcional)**: Insira uma descrição para o grupo de usuários de prioridade.
5. Selecione **Avançar** para continuar.
6. Na página **escolher Membros** , selecione **escolher Membros** para pesquisar e selecionar quais contas de usuário habilitadas para email estão incluídas no grupo ou marque a caixa de seleção **selecionar tudo** para adicionar todos os usuários da sua organização ao grupo. Selecione **Adicionar** para continuar ou **Cancelar** para fechar sem adicionar usuários ao grupo.
7. Selecione **Avançar** para continuar.
8. Na página **revisão** , revise as configurações escolhidas para o grupo de usuários de prioridade. Selecione **Editar** para alterar qualquer um dos valores de grupo ou selecione **Enviar** para criar e ativar o grupo de usuários de prioridade.
9. Na página de confirmação, selecione **concluído** para sair do assistente.

### <a name="update-a-priority-user-group"></a>Atualizar um grupo de usuários de prioridade

Para atualizar um grupo de usuários de prioridade existente, você usará os controles de configuração na solução de **Gerenciamento de risco do insider** no centro de conformidade do Microsoft 365. Para atualizar um grupo de usuários de prioridade, você deve ser membro do grupo de funções de *Gerenciamento de risco do insider* ou *administrador de gerenciamento de risco do insider* .

Conclua as seguintes etapas para editar um grupo de usuários de prioridade:

1. No [centro de conformidade da Microsoft 365](https://compliance.microsoft.com), vá para gerenciamento de **risco do insider** e selecione **configurações de risco do insider**.
2. Selecionar a guia **grupos de usuários de prioridade**
3. Selecione o grupo de usuários de prioridade que você deseja editar e selecione **Editar grupo**.
4. Na página **definir grupo** , atualize o campo Descrição, se necessário. Não é possível atualizar o nome do grupo de usuários de prioridade. Selecione **Avançar** para continuar.
5. Na página **escolher Membros** , adicione novos membros ao grupo usando o controle **escolher Membros** . Para remover um usuário do grupo, selecione ' X ' ao lado do usuário que você deseja remover. Selecione **Avançar** para continuar.
6. Na página **revisão** , revise as configurações de atualização escolhidas para o grupo de usuários de prioridade. Selecione **Editar** para alterar qualquer um dos valores de grupo ou selecione **Enviar** para atualizar o grupo de usuários de prioridade.
7. Na página de confirmação, selecione **concluído** para sair do assistente.

### <a name="delete-a-priority-user-group"></a>Excluir um grupo de usuários de prioridade

Para excluir um grupo de usuários de prioridade existente, você usará os controles de configuração na solução de **Gerenciamento de risco do insider** no centro de conformidade do Microsoft 365. Para excluir um grupo de usuários de prioridade, você deve ser membro do grupo de função *Gerenciamento de risco do insider* ou *administrador de gerenciamento de risco do insider* .

>[!IMPORTANT]
>A exclusão de um grupo de usuários de prioridade o removerá de qualquer política ativa à qual esteja atribuída. Se você excluir um grupo de usuários de prioridade atribuído a uma política ativa, a política não conterá nenhum usuário dentro do escopo e será efetivamente ociosa e não criará alertas.

Conclua as seguintes etapas para excluir um grupo de usuários de prioridade:

1. No [centro de conformidade da Microsoft 365](https://compliance.microsoft.com), vá para gerenciamento de **risco do insider** e selecione **configurações de risco do insider**.
2. Selecionar a guia **grupos de usuários de prioridade**
3. Selecione o grupo de usuários de prioridade que você deseja editar e selecione **excluir** no menu do painel.
4. Na caixa de diálogo **excluir** , selecione **Sim** para excluir o grupo de usuários de prioridade ou selecione **Cancelar** para retornar ao painel.

## <a name="priority-physical-assets-preview"></a>Prioridade de ativos físicos (versão prévia)

Identificar o acesso aos ativos físicos de prioridade e correlacionar a atividade de acesso aos eventos do usuário é um componente importante de sua infraestrutura de conformidade. Esses ativos físicos representam locais de prioridade em sua organização, como prédios da empresa, data centers ou salas de servidor. As atividades de risco do insider podem ser associadas aos usuários que trabalham em horas incomuns, tentando acessar essas áreas confidenciais não autorizadas ou seguras e solicitações de acesso a áreas de alto nível sem necessidades legítimas.

Com os ativos físicos de prioridade habilitados e o [conector de dados do símbolos físico](import-physical-badging-data.md) configurados, o gerenciamento de riscos do insider integra sinais do controle físico e dos sistemas de acesso com outras atividades de risco do usuário. Examinando padrões de comportamento nos sistemas de acesso físico e correlacionando essas atividades com outros eventos de risco do Insider, o gerenciamento de riscos do insider pode ajudar os investigadores e analistas de conformidade a tomar decisões de resposta mais embasadas para alertas. O acesso aos ativos físicos de prioridade é pontuado e identificado em insights de forma diferente do acesso a ativos que não são de prioridade.

Por exemplo, sua organização tem um sistema símbolos para usuários que monitoram e aprovam o acesso físico a áreas de projeto confidenciais e de trabalho normais. Você tem vários usuários trabalhando em um projeto confidencial e esses usuários retornarão a outras áreas da sua organização quando o projeto for concluído. Como o projeto confidencial é quase de conclusão, você deseja garantir que o trabalho do projeto permaneça confidencial e que o acesso às áreas do projeto seja totalmente controlado.

Você opta por habilitar o conector de dados do símbolos físico no Microsoft 365 para importar informações de acesso do seu sistema de símbolos físico e especificar os ativos físicos de prioridade no gerenciamento de risco do insider. Ao importar informações do seu sistema do símbolos e correlacionar informações de acesso físico com outras atividades de risco identificadas no gerenciamento de risco do Insider, você percebe que um dos usuários no projeto está acessando os escritórios do projeto após o horário normal e também está exportando grandes quantidades de dados para um serviço de armazenamento em nuvem pessoal de sua área de trabalho normal. Esta atividade de acesso físico associada à atividade online pode apontar para possíveis ladrões de roubo de dados, e os analistas podem tomar as ações apropriadas, conforme determinado pelas circunstâncias desse usuário.

### <a name="configure-priority-physical-assets"></a>Configurar os ativos físicos de prioridade

Para configurar os ativos físicos de prioridade, você irá configurar o conector do símbolos físico e usar os controles de configuração na solução de **Gerenciamento de risco do insider** no centro de conformidade do Microsoft 365. Para configurar os ativos físicos de prioridade, você deve ser membro do grupo de função de *Gerenciamento de risco do insider* ou do *administrador de gerenciamento de risco do insider*.

Conclua as seguintes etapas para configurar os ativos físicos de prioridade:

1. Siga as etapas de configuração do gerenciamento de risco do insider no artigo [introdução ao Insider Risk Management](insider-risk-management-configure.md) . Na etapa 3, certifique-se de configurar o conector de símbolos físico.

    >[!IMPORTANT]
    >Para políticas de gerenciamento de risco do insider para usar e correlacionar dados de sinal relacionados a cancelamento e usuários demitidos com dados de evento de suas plataformas de controle e de acesso físico, você também deve configurar o Microsoft 365 HR Connector. Se você habilitar o conector símbolos físico sem habilitar o conector de RH da Microsoft 365, as políticas de gerenciamento de risco do insider só processarão os eventos para as atividades de acesso físico dos usuários em sua organização.

2. No [centro de conformidade da Microsoft 365](https://compliance.microsoft.com), vá para gerenciamento de **risco do insider** e selecione ativos físicos de prioridade de **configurações de risco do insider**  >  **Priority physical assets**.
3. Na página de **recursos físicos de prioridade** , você pode adicionar manualmente as IDs de ativos físicos que você deseja monitorar para os eventos de ativo importados pelo conector símbolos físico ou importar um. Arquivo CSV de todas as IDs de ativos físicos importadas pelo conector símbolos físico: a) para adicionar manualmente IDs de ativos físicos, escolha **Adicionar prioridade de ativos físicos**, insira uma ID de ativo físico e, em seguida, selecione **Adicionar**. Insira IDs de ativos físicos adicionais e selecione **Adicionar prioridade aos ativos físicos** para salvar todos os ativos inseridos.
    b) para adicionar uma lista de IDs de ativos físicos de um. CSV, escolha **importar ativos físicos de prioridade**. Na caixa de diálogo explorador de arquivos, selecione o. CSV arquivo que você deseja importar e, em seguida, selecione **abrir**. As IDs de ativos físicos do. Arquivos CSV são adicionados à lista.
4. Navegue até a guia **indicadores de política** em configurações.
5. Na página **indicadores de política** , navegue até a seção **indicadores de acesso físico** e marque a caixa de seleção para **acesso físico após o término ou falha no acesso ao ativo confidencial**.
6. Selecione **salvar** para configurar e sair.

### <a name="delete-a-priority-physical-asset"></a>Excluir um ativo físico de prioridade

Para excluir um ativo físico de prioridade existente, você usará os controles de configuração na solução de gerenciamento de risco do insider no centro de conformidade do Microsoft 365. Para excluir um ativo físico de prioridade, você deve ser membro do grupo de função gerenciamento de risco do insider ou administrador de gerenciamento de risco do insider.

>[!IMPORTANT]
>A exclusão de um ativo físico de prioridade remove-o da verificação de qualquer política ativa para a qual foi incluído anteriormente. Os alertas gerados por atividades associadas ao ativo físico de prioridade não são excluídos.

Conclua as seguintes etapas para excluir um ativo físico de prioridade:

1. No [centro de conformidade da Microsoft 365](https://compliance.microsoft.com), vá para gerenciamento de **risco do insider** e selecione ativos físicos de prioridade de **configurações de risco do insider**  >  **Priority physical assets**.
2. Na página **prioridade física dos ativos** , selecione o ativo que você deseja excluir.
3. Selecione **excluir** no menu Ação para excluir o ativo.

## <a name="power-automate-flows-preview"></a>Fluxos automatizados de energia (visualização)

[O Microsoft Power Automate](https://docs.microsoft.com/power-automate/getting-started) é um serviço de fluxo de trabalho que automatiza ações entre aplicativos e serviços. Usando fluxos de modelos ou criados manualmente, é possível automatizar tarefas comuns associadas a esses aplicativos e serviços. Ao habilitar os fluxos de energia automatizada para o gerenciamento de risco do Insider, você pode automatizar tarefas importantes para casos e usuários. Você pode configurar fluxos de energia automatizada para recuperar as informações de usuário, alerta e caso e compartilhar essas informações com participantes e outros aplicativos, além de automatizar ações no gerenciamento de risco do Insider, como postar em notas de caso. Os fluxos de automatização de energia são aplicáveis para casos e qualquer usuário no escopo para uma política.

Os clientes com assinaturas do Microsoft 365 que incluem o gerenciamento de risco do insider não precisam de automatizar as licenças para usar os modelos de automatização de recursos de automação de gerenciamento de risco do insider recomendado. Esses modelos podem ser personalizados para dar suporte à sua organização e cobrir os principais cenários de gerenciamento de risco do insider. Se você optar por usar os recursos de automatização de energia Premium nesses modelos, crie um modelo personalizado usando o conector de conformidade da Microsoft 365 ou use os modelos de automatização de energia para outras áreas de conformidade no Microsoft 365, talvez você precise de energia adicional automatizar as licenças.

Os modelos de automatização de energia a seguir são fornecidos aos clientes para oferecer suporte à automação de processos para usuários e casos de gerenciamento de risco do insider:

- **Notificar os usuários quando eles forem adicionados a uma política de risco Insider**: esse modelo é para organizações que têm políticas internas, privacidade ou requisitos normativos que os usuários devem ser notificados quando estão sujeitos às políticas de gerenciamento de risco do insider. Quando esse fluxo é configurado e selecionado para um usuário na página usuários, os usuários e seus gerentes são enviados uma mensagem de email quando o usuário é adicionado a uma política de gerenciamento de risco do insider. Este modelo também oferece suporte à atualização de uma lista do SharePoint hospedada em um site do SharePoint para ajudar a rastrear detalhes da mensagem de notificação, como data/hora e o destinatário da mensagem. Os fluxos de automatização de energia usando esse modelo estão disponíveis no **painel usuários**.
- **Solicitar informações de RH ou de negócios sobre um usuário em um caso de risco do insider**: ao atuar em um caso, os analistas e investigadores de risco do insider podem precisar consultar o RH ou outros participantes para entender o contexto das atividades de caso. Quando esse fluxo é configurado e selecionado para um caso, os analistas e investigadores enviam uma mensagem de email para os participantes de RH e comerciais configurados para esse fluxo. Cada destinatário recebe uma mensagem com opções de resposta pré-configuradas ou personalizáveis. Quando os destinatários selecionam uma opção de resposta, a resposta é registrada como uma nota de caso e inclui informações de destinatário e data/hora. Os fluxos de automatização de energia usando esse modelo estão disponíveis no **painel de casos**.
- **Notificar o gerente quando um usuário tiver um alerta de risco do insider**: algumas organizações podem precisar ter uma notificação de gerenciamento imediata quando um usuário tiver um alerta de gerenciamento de risco do insider. Quando esse fluxo é configurado e selecionado, o gerente para o usuário caso é enviado uma mensagem de email com as seguintes informações sobre todos os alertas de caso: 
    - Política aplicável para o alerta
    - Data/hora do alerta
    - Nível de severidade do alerta

    O fluxo atualiza automaticamente as notas de caso em que a mensagem foi enviada e que o fluxo foi ativado. Os fluxos de automatização de energia usando esse modelo estão disponíveis no **painel de casos**.

- **Adicionar Lembrete de calendário para acompanhar um caso de risco do insider**: este modelo permite que investigadores de risco e analistares adicionem lembretes de calendário para casos ao seu calendário do Office 365 Outlook. Esse fluxo elimina a necessidade de que os usuários saiam ou saiam do fluxo de trabalho de gerenciamento de risco do insider ao processar os alertas de ocorrências e de triagem. Quando esse fluxo é configurado e selecionado, um lembrete é adicionado ao calendário do Office 365 Outlook para o usuário que está executando o fluxo. Os fluxos de automatização de energia usando esse modelo estão disponíveis no **painel de casos**.

### <a name="create-a-power-automate-flow-from-insider-risk-management-template"></a>Criar um fluxo automatizado de energia do modelo de gerenciamento de risco do insider

Para criar um fluxo automatizado de energia de um modelo de gerenciamento de risco do insider recomendado, você usará os controles de configurações na solução de **Gerenciamento de risco do insider** no centro de conformidade da Microsoft 365 ou a opção **gerenciar fluxos de energia automatizada** do controle **automatizado** ao trabalhar diretamente nos painéis **casos** ou **usuários**.

Para criar um fluxo automatizado de energia na área configurações, você deve ser membro do grupo de função *Gerenciamento de risco do insider* ou *administrador de gerenciamento de risco do insider* . Para criar um fluxo automatizado de energia com a opção **gerenciar fluxos de automatização de energia** , você deve ser membro de pelo menos um grupo de funções de gerenciamento de risco do insider.

Conclua as etapas a seguir para criar um fluxo automatizado de energia de um modelo de gerenciamento de risco do insider recomendado:

1. No [centro de conformidade da Microsoft 365](https://compliance.microsoft.com/), vá para gerenciamento de **risco do insider** e selecione **configurações de risco do insider**  >  **fluxos automáticos de energia**. Você também pode acessar as páginas de painéis de **casos** ou de **usuários** , escolhendo **automatizar**  >  **gerenciar fluxos automáticos de energia**.
2. Na página **fluxos automáticos de energia** , selecione um modelo recomendado na seção **modelos de gerenciamento de risco do insider que você deseja** usar na página.
3. O fluxo lista as conexões inseridas necessárias para o fluxo e notará se os status de conexão estão disponíveis. Se necessário, atualize as conexões que não são exibidas como disponíveis. Selecione **continuar**.
4. Por padrão, os fluxos recomendados são pré-configurados com os campos de dados de serviço de ingestão de riscos do insider e Microsoft 365 necessários para concluir a tarefa atribuída para o fluxo. Se necessário, personalize os componentes de fluxo usando o controle **Mostrar opções avançadas** e configurando as propriedades disponíveis para o componente de fluxo.
5. Se necessário, adicione as etapas adicionais ao fluxo selecionando o botão **nova etapa** . Na maioria dos casos, isso não deve ser necessário para os modelos padrão recomendados.
6. Selecione **salvar rascunho** para salvar o fluxo para configuração adicional ou selecione **salvar** para concluir a configuração para o fluxo.
7. Selecione **fechar** para retornar à página **fluxo automatizado de energia** . O novo modelo será listado como um fluxo nas guias **meus fluxos** e estará automaticamente disponível no controle suspenso **automatizado** ao trabalhar com casos de gerenciamento de risco do insider para o usuário que está criando o fluxo.

>[!IMPORTANT]
>Se outros usuários em sua organização precisarem acessar o fluxo, o fluxo deve ser compartilhado.

### <a name="create-a-custom-power-automate-flow-for-insider-risk-management"></a>Criar um fluxo automatizado de energia personalizada para o gerenciamento de risco do insider

Alguns processos e fluxos de trabalho de sua organização podem estar fora dos modelos de fluxo de gerenciamento de risco do insider recomendados e você pode ter a necessidade de criar fluxos de automatização de energia personalizada para áreas de gerenciamento de risco do insider. Os fluxos de automatização de energia são flexíveis e dão suporte à personalização abrangente, mas há etapas que precisam ser tomadas para integração com os recursos de gerenciamento de risco do insider.

Conclua as etapas a seguir para criar um modelo de automatização de energia personalizado para o gerenciamento de risco do insider:

1. **Verifique a sua licença de fluxo automatizado de energia**: para criar fluxos de alimentação personalizados automatizados que usam gatilhos de gerenciamento de risco do Insider, você precisará de uma licença de automatização de energia. Os modelos de fluxo de gerenciamento de risco do insider recomendados não exigem licenciamento adicional e são incluídos como parte da sua licença de gerenciamento de risco do insider.
2. **Criar um fluxo automatizado**: Crie um fluxo que execute uma ou mais tarefas após ele ser disparado por um evento de gerenciamento de risco do insider. Para obter detalhes sobre como criar um fluxo automatizado, confira [criar um fluxo na energia automatizada](https://docs.microsoft.com/power-automate/get-started-logic-flow).
3. **Selecione o conector de conformidade da microsoft 365**: Procure e selecione o conector de conformidade da Microsoft 365. Esse conector permite ações e gatilhos de gerenciamento de risco do insider. Para obter mais informações sobre conectores, consulte o artigo [visão geral da referência do conector](https://docs.microsoft.com/connectors/connector-reference/) .
4. **Escolha os gatilhos de gerenciamento de risco do insider para seu fluxo: o**gerenciamento de risco do insider tem dois gatilhos disponíveis para fluxos de automatização
    - **Para um caso de gerenciamento de risco do insider selecionado**: fluxos com este gatilho podem ser selecionados na página de painel de casos de gerenciamento de risco do insider.
    - **Para um usuário de gerenciamento de risco do insider selecionado**: fluxos com este gatilho podem ser selecionados na página do painel usuários de gerenciamento de risco do insider.
5. Escolha ações de gerenciamento de risco do insider para o seu fluxo: você pode escolher entre várias ações para o gerenciamento de risco do insider incluir em seu fluxo personalizado:
    - Obter alerta de gerenciamento de risco do insider
    - Obter o caso de gerenciamento de risco do insider
    - Obter usuário de gerenciamento de risco do insider
    - Obter alertas de gerenciamento de risco do insider para um caso
    - Adicionar nota de caso de gerenciamento de risco do insider

### <a name="share-a-power-automate-flow"></a>Compartilhar um fluxo automatizado de energia

Por padrão, os fluxos de energia automatizados criados por um usuário só estão disponíveis para esse usuário. Para que outros usuários de gerenciamento de risco do insider tenham acesso e usem um fluxo, o fluxo deve ser compartilhado pelo criador do fluxo. Para compartilhar um fluxo, você usará os controles de configurações na **solução de gerenciamento de risco do insider** no centro de conformidade do Microsoft 365 ou a opção **gerenciar fluxos de energia automatizada** do controle automatizado ao trabalhar diretamente nas páginas de painel de **casos** ou **usuários** . Depois de compartilhar um fluxo, **todos os usuários** com quem ele tenha sido compartilhado poderão acessar o fluxo no menu suspenso de controle automático, nos painéis de **caso** e de **usuário**.

Para compartilhar um fluxo automatizado de energia na área configurações, você deve ser membro do grupo de função *Gerenciamento de risco do insider* ou *administrador de gerenciamento de risco do insider* . Para compartilhar um fluxo automatizado de energia com a opção **gerenciar fluxos de automatização de energia** , você deve ser membro de pelo menos um grupo de funções de gerenciamento de risco do insider.

Conclua as seguintes etapas para compartilhar um fluxo automatizado de energia:

1. No [centro de conformidade da Microsoft 365](htttps://compliance.microsoft.com), vá para gerenciamento de **risco do insider** e selecione **configurações de risco do insider**  >  **fluxos automáticos de energia**. Você também pode acessar as páginas de painéis de **casos** ou de **usuários** , escolhendo **automatizar**  >  **gerenciar fluxos automáticos de energia**.
2. Na página **fluxos automáticos de energia** , selecione a guia **meus fluxos** ou **enfluxos da equipe** .
3. Selecione o fluxo a ser compartilhado e, em seguida, selecione **compartilhar** no menu opções de fluxo.
4. Na página compartilhamento de fluxo, insira o nome do usuário ou grupo que você deseja adicionar como um proprietário para o fluxo.
5. Na caixa de diálogo **conexão usada** , selecione **OK** para confirmar que o usuário ou grupo adicionado terá acesso total ao fluxo.

### <a name="edit-a-power-automate-flow"></a>Editar um fluxo automatizado de energia

Para editar um fluxo, você usará os controles de configurações na solução de **Gerenciamento de risco do insider** no centro de conformidade da Microsoft 365 ou a opção **gerenciar fluxos de energia automatizada** do controle **automatizado** ao trabalhar diretamente nos painéis **casos** ou **usuários**.

Para editar um fluxo automatizado de energia na área configurações, você deve ser membro do grupo de função *Gerenciamento de risco do insider* ou *administrador de gerenciamento de risco do insider* . Para editar um fluxo automatizado de energia com a opção **gerenciar fluxos de automatização de energia** , você deve ser membro de pelo menos um grupo de funções de gerenciamento de risco do insider.

Conclua as seguintes etapas para editar um fluxo automatizado de energia:

1. No [centro de conformidade da Microsoft 365](htttps://compliance.microsoft.com), vá para gerenciamento de **risco do insider** e selecione **configurações de risco do insider**  >  **fluxos automáticos de energia**. Você também pode acessar as páginas de painéis de **casos** ou de **usuários** , escolhendo **automatizar**  >  **gerenciar fluxos automáticos de energia**.
2. Na página **fluxos automáticos de energia** , selecione um fluxo para editar e selecione **Editar** no menu controle de fluxo.
3. Selecione as configurações de **reticências**  >  **Settings** para alterar uma configuração de componente de fluxo ou **reticências**  >  **delete** para excluir um componente de fluxo.
4. Selecione **salvar** e **fechar** para concluir a edição do fluxo.

### <a name="delete-a-power-automate-flow"></a>Excluir um fluxo automatizado de energia

Para excluir um fluxo, você usará os controles de configurações na solução de **Gerenciamento de risco do insider** no centro de conformidade do Microsoft 365 ou a opção **gerenciar fluxos de energia automatizada** do controle **automatizado** ao trabalhar diretamente nos painéis **casos** ou **usuários**. Quando um fluxo é excluído, ele é removido como uma opção para todos os usuários.

Para excluir um fluxo automatizado de energia na área configurações, você deve ser membro do grupo de função *Gerenciamento de risco do insider* ou *administrador de gerenciamento de risco do insider* . Para excluir um fluxo automatizado de energia com a opção **gerenciar fluxos de automatização de energia** , você deve ser membro de pelo menos um grupo de funções de gerenciamento de risco do insider.

Conclua as seguintes etapas para excluir um fluxo automatizado de energia:

1. No [centro de conformidade da Microsoft 365](htttps://compliance.microsoft.com), vá para gerenciamento de **risco do insider** e selecione **configurações de risco do insider**  >  **fluxos automáticos de energia**. Você também pode acessar as páginas de painéis de **casos** ou de **usuários** , escolhendo **automatizar**  >  **gerenciar fluxos automáticos de energia**.
2. Na página **fluxos automáticos de energia** , selecione um fluxo para excluir e selecione **excluir** no menu controle de fluxo.
3. Na caixa de diálogo de confirmação de exclusão, selecione **excluir** para remover o fluxo ou selecione **Cancelar** para sair da ação de exclusão.

## <a name="microsoft-teams-preview"></a>Microsoft Teams (visualização)

Os analistas e investigadores de conformidade podem facilmente usar o Microsoft Teams para colaboração nos casos de gerenciamento de risco do insider. Eles podem coordenar e se comunicar com outros participantes no Microsoft Teams para:

- Coordenar e revisar atividades de resposta para casos em canais de equipes privadas
- Compartilhar e armazenar arquivos e evidências com segurança relacionados a casos individuais
- Controlar e analisar as atividades de resposta por analistas e investigadores

Depois que o Microsoft Teams está habilitado para o gerenciamento de risco do Insider, uma equipe do Microsoft Teams dedicada é criada sempre que um alerta é confirmado e um caso é criado. Por padrão, a equipe inclui automaticamente todos os membros do grupo de funções *Gerenciamento de risco do insider*, *analistas de gerenciamento de risco*do insider e investigadores de *Gerenciamento* de risco do Insider (até 100 usuários iniciais). Outros colaboradores da organização podem ser adicionados à equipe depois de serem criados e conforme apropriado. Para casos existentes criados antes de habilitar o Microsoft Teams, os analistas e investigadores podem optar por criar uma nova equipe do Microsoft Teams ao trabalhar em um caso necessário.  Depois de resolver o caso associado no gerenciamento de risco do Insider, a equipe é automaticamente arquivada (movida para oculto e somente leitura).

Para obter mais informações sobre como usar equipes e canais no Microsoft Teams, consulte [visão geral de equipes e canais no Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-channels-overview).

Habilitar o suporte do Microsoft Teams para casos é rápido e fácil de configurar. Para habilitar o Microsoft Teams para o gerenciamento de risco do Insider, conclua as seguintes etapas:

1. No [centro de conformidade da Microsoft 365](htttps://compliance.microsoft.com), vá para configurações de risco do **Insider gerenciamento de risco do insider**  >  **Insider risk settings**.
2. Selecione a guia **Microsoft Teams** .
3. Habilitar a integração do Microsoft Teams para gerenciamento de risco de insider.
4. Selecione **salvar** para configurar e sair.

### <a name="create-a-microsoft-teams-team-for-existing-cases"></a>Criar uma equipe do Microsoft Teams para casos existentes

Se você habilitar o suporte do Microsoft Teams para o gerenciamento de risco do insider depois de casos existentes, será necessário criar manualmente uma equipe para cada caso necessário. Após habilitar o suporte do Microsoft Teams nas configurações de gerenciamento de risco do Insider, novos casos criarão automaticamente uma nova equipe do Microsoft Teams.

Os usuários precisam de permissão para criar grupos do Microsoft 365 em sua organização para criar uma equipe do Microsoft Teams a partir de um caso. Para obter mais informações sobre o gerenciamento de permissões para grupos do Microsoft 365, consulte [Manage quem pode criar os grupos do microsoft 365](https://docs.microsoft.com/microsoft-365/solutions/manage-creation-of-groups).

Para criar uma equipe para uma ocorrência, você usará o controle criar Microsoft Team ao trabalhar diretamente em um caso existente. Conclua as seguintes etapas para criar uma nova equipe:

1. No [centro de conformidade da Microsoft 365](htttps://compliance.microsoft.com), vá para casos de gerenciamento de **risco do insider**  >  **Cases** e selecione um caso existente.
2. No menu Ação de caso, selecione **criar Microsoft Team**.
3. No campo **nome da equipe** , digite um nome para a nova equipe do Microsoft Teams.
4. Selecione **criar Microsoft Team** e selecione **fechar**.

Dependendo do número de usuários atribuídos aos grupos de funções de gerenciamento de risco do Insider, pode levar 15 minutos para que todos os investigadores e analistas sejam adicionados à equipe do Microsoft Teams para um caso.
