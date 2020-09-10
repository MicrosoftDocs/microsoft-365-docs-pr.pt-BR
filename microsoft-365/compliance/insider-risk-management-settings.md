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
ms.openlocfilehash: cec98f979a19c91946564aa402d1880c3ee08d5a
ms.sourcegitcommit: 74ef7179887eedc696c975a82c865b2d4b3808fd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/09/2020
ms.locfileid: "47416775"
---
# <a name="get-started-with-insider-risk-management-settings"></a>Introdução às configurações de gerenciamento de risco do insider

As configurações de gerenciamento de riscos do insider aplicam-se a todas as políticas de gerenciamento de risco do Insider, independentemente do modelo escolhido durante a criação As configurações são definidas usando o controle de **configurações de risco do insider** localizado na parte superior de todas as guias de gerenciamento de risco do insider Estas configurações controlam componentes de política para as seguintes áreas:

- Privacidade
- Indicadores
- Cronogramas de política
- Detecções inteligentes
- Exportar alertas
- Grupos de usuários de prioridade

Antes de começar e criar políticas de gerenciamento de risco do Insider, é importante entender essas configurações e escolher a configuração dos níveis mais adequados para as necessidades de conformidade da sua organização.

## <a name="privacy"></a>Privacidade

A proteção da privacidade dos usuários que têm correspondências de política é importante e pode ajudar a promover o Objectivity em análises de investigação e análise de dados para alertas de risco do insider. Para usuários com uma política de risco de insider correspondência, você pode escolher uma das seguintes configurações:

- **Mostrar versões anonimato de nomes de**usuário: os nomes de usuários são anônimos para impedir que administradores, investigadores de dados e revisores vejam quem está associado a alertas de política. Por exemplo, um "Taylor de cortesia" do usuário apareceria com um pseudonym aleatório, como "AnonIS8-988" em todas as áreas da experiência de gerenciamento de risco do insider. A escolha dessa configuração anonymizes todos os usuários com correspondências de política atuais e anteriores e se aplicam a todas as políticas. As informações de perfil de usuário no alerta de risco do insider e os detalhes do caso não estarão disponíveis quando essa opção for escolhida. No entanto, os nomes de usuário são exibidos ao adicionar novos usuários às políticas existentes ou ao atribuir usuários a novas políticas. Se você optar por desativar essa configuração, os nomes de usuário serão exibidos para todos os usuários que têm correspondências de política atuais ou antigas.
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

1. Habilitar o suporte à API da atividade de gerenciamento do Office 365 nas configurações de gerenciamento de risco do insider. Por padrão, essa configuração é desabilitada para sua organização do Microsoft 365.
2. Filtrar as atividades de auditoria comuns do Office 365 por *SecurityComplianceAlerts*.
3. Filtra *SecurityComplianceAlerts* pela categoria *InsiderRiskManagement* .

![Configurações de alerta de exportação do insider Risk Management](../media/insider-risk-settings-export.png)

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