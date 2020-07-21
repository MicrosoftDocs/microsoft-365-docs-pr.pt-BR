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
ms.openlocfilehash: a08d07f574c1cd5463772c803be0d4b3850144f4
ms.sourcegitcommit: a08103bc120bdec7cfeaf67c1be4e221241e69ad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/21/2020
ms.locfileid: "45199531"
---
# <a name="insider-risk-management-policies"></a>Políticas de gerenciamento de risco do insider

As políticas de gerenciamento de risco do insider determinam quais usuários estão no escopo e quais tipos de indicadores de risco estão configurados para alertas. Você pode criar rapidamente uma política que se aplica a todos os usuários em sua organização ou definir usuários individuais ou grupos para gerenciamento em uma política. As políticas dão suporte a prioridades de conteúdo para concentrar as condições de política em várias ou em Microsoft Teams, sites do SharePoint, tipos de confidencialidade de dados e rótulos de dados. Usando modelos, você pode selecionar indicadores de risco específicos e personalizar os limites de eventos para os indicadores de política, personalizando efetivamente as pontuações de risco e o nível e a frequência dos alertas. Além disso, os aceleradores de Pontuação de risco e as detecções de anomalias ajudam a identificar as atividades do usuário que têm maior importância ou mais comuns. Políticas o Windows permite que você defina o intervalo de tempo para aplicar a política às atividades de alerta e é usado para determinar a duração da política após a ativação.

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

Os modelos de gerenciamento de risco do insider são condições de política predefinidas que definem os tipos de indicadores de risco e o modelo de Pontuação de risco usados pela política. Cada política deve ter um modelo atribuído no assistente de criação de política antes que a política seja criada. O gerenciamento de risco do insider oferece suporte a até cinco políticas para cada modelo de política. Ao criar uma nova política de risco de insider com o assistente de política, você escolherá um dos seguintes modelos de política:

### <a name="data-theft-by-departing-users"></a>Roubo de dados por parte de usuários

Quando os usuários saem da sua organização, há indicadores de risco específicos geralmente associados ao roubo de dados, que fazem parte dos usuários. Este modelo de política usa indicadores para a pontuação de risco e focaliza a detecção e os alertas nessa área de risco. O roubo de dados de parte dos usuários pode incluir o download de arquivos do SharePoint Online, a impressão de arquivos e a cópia de dados para serviços de armazenamento e mensagens na nuvem pessoal, perto de suas datas de demissão e término de emprego. Este modelo inicia a pontuação de indicadores de risco relacionados a essas atividades e como elas se relacionam com o status de emprego do usuário.

>[!IMPORTANT]
>Ao usar esse modelo, você deve configurar um conector de RH da Microsoft 365 para importar periodicamente informações de data de demissão e de término para usuários em sua organização. Consulte o artigo [importar dados com o conector de RH](import-hr-data.md) para obter orientações passo a passo para configurar o Microsoft 365 HR Connector para sua organização.

### <a name="general-data-leaks"></a>Vazamentos de dados gerais

A proteção de dados e a prevenção de vazamentos de dados é um desafio constante para a maioria das organizações, especialmente com o rápido aumento de novos dados criados por usuários, dispositivos e serviços. Os usuários são capacitados a criar, armazenar e compartilhar informações entre serviços e dispositivos que tornam o gerenciamento de vazamentos de dados cada vez mais complexo e difícil. Os vazamentos de dados podem incluir o compartilhamento acidental de informações fora de sua organização ou roubo de dados com más intenções. Em conjunto com uma política de prevenção de perda de dados (DLP) atribuída, este modelo inicia a pontuação de detecções em tempo real de downloads suspeitos de dados do SharePoint Online, compartilhamento de arquivos e pastas, impressão de arquivos e cópia de dados para serviços de armazenamento e mensagens na nuvem pessoal.

Ao usar um modelo de **vazamentos de dados** , você deve atribuir uma política de DLP para acionar indicadores na política de risco do insider para alertas de alta gravidade em sua organização. Sempre que um alerta de alta gravidade é gerado por uma regra de política de DLP é adicionada ao log de auditoria do Office 365, as políticas de risco do insider criadas com esse modelo examinam automaticamente o alerta de DLP de alta gravidade. Se o alerta contiver um usuário de escopo definido na política de risco Insider, o alerta será processado pela política de risco Insider como um novo alerta e receberá uma severidade de risco e uma pontuação de risco do insider. Essa política permite avaliar esse alerta em contexto com outras atividades incluídas no caso.

#### <a name="data-leaks-policy-guidelines"></a>Diretrizes de política de vazamentos de dados

Ao criar ou modificar políticas de DLP para uso com políticas de gerenciamento de risco do Insider, considere as seguintes diretrizes:

- Priorizar eventos de exfiltration de dados e ser seletivo ao atribuir configurações de **relatórios de incidentes** como *alto* ao configurar regras em suas políticas de DLP. Por exemplo, o envio de documentos confidenciais por email para um concorrente conhecido deve *ser um evento* de nível de alerta exfiltration. A atribuição de excesso no nível *alto* nas configurações de **relatórios de incidentes** em outras regras de política de DLP pode aumentar o ruído no fluxo de trabalho de alerta de gerenciamento de risco do insider e dificultar a avaliação adequada desses alertas. Por exemplo, a atribuição de *altos* níveis de alerta às atividades de negação de acesso nas políticas de DLP torna mais desafiador avaliar o comportamento e as atividades do usuário verdadeiramente arriscados.
- Verifique se você entendeu e configurou corretamente os usuários no escopo nas políticas de gerenciamento de risco do DLP e do insider. Somente os usuários definidos como dentro do escopo para políticas de gerenciamento de risco do insider usando o modelo de **vazamentos de dados** terão alertas de política de DLP de alta gravidade processados. Além disso, somente usuários definidos como dentro do escopo em uma regra para um alerta de DLP de alta gravidade serão examinados pela política de gerenciamento de risco do insider para fins de avaliação. É importante que você não configure de forma desconhecida os usuários no escopo em suas políticas de risco do DLP e do insider de uma maneira conflitante.

     Por exemplo, se suas regras de política de DLP têm o escopo para apenas os usuários da equipe de vendas e a política de risco do insider criada a partir do modelo de **vazamentos de dados** tiver definido todos os usuários como dentro do escopo, a política de risco do insider só processará alertas de DLP de alta gravidade para os usuários da equipe de vendas. A política de risco Insider não receberá alertas de DLP de alta prioridade para que os usuários processem que não estejam definidos nas regras de DLP neste exemplo. Por outro lado, se sua política de gerenciamento de risco do insider criada a partir de modelos de **vazamentos de dados** tiver o escopo de todos os usuários da equipe de vendas e a política de DLP atribuída estiver delimitada a todos os usuários, a política de riscos Insider só processará alertas de DLP de alta gravidade para membros da equipe de vendas. A política de gerenciamento de risco do insider ignorará alertas de DLP de alta gravidade para todos os usuários que não estão na equipe de vendas.

- Certifique-se de que a configuração de regra **relatórios de incidentes** na política de DLP usada para este modelo de gerenciamento de risco do insider está configurada para alertas de *alto* nível O *alto* nível de severidade é o disparo de eventos e os alertas de gerenciamento de risco do insider não serão gerados de regras nas políticas de DLP com o conjunto de campos **relatórios de incidentes** em *baixo* ou *médio*.

    ![Configuração de alerta de política DLP](../media/insider-risk-DLP-policy-high-severity.png)

     >[!NOTE]
     >Ao criar uma nova política de DLP usando os modelos internos, você precisará selecionar a opção **criar ou personalizar regras de DLP avançadas** para definir a configuração de **relatórios de incidentes** para o nível de severidade *alto* .

Cada política de gerenciamento de risco do insider criada a partir do modelo de **vazamentos de dados** pode ter apenas uma política de DLP atribuída. Considere a criação de uma política de DLP dedicada que combine as diferentes atividades que você deseja detectar e atue como eventos de acionamento para políticas de risco de insider que usam o modelo de **vazamento de dados** .

Consulte o tópico [criar, testar e ajustar uma política de DLP](create-test-tune-dlp-policy.md) para obter orientações passo a passo para configurar as políticas de DLP para sua organização.

### <a name="data-leaks-by-priority-users-preview"></a>Vazamentos de dados por usuários de prioridade (visualização)

A proteção de dados e a prevenção de vazamentos de dados para usuários em sua organização podem depender de sua posição, nível de acesso a informações confidenciais ou histórico de riscos. Os vazamentos de dados podem incluir o supercompartilhamento acidental de informações altamente confidenciais fora de sua organização ou roubo de dados com más intenções. Em conjunto com uma política de prevenção de perda de dados (DLP) atribuída, este modelo inicia a pontuação de detecções em tempo real de atividades suspeitas e resulta em uma maior probabilidade de alertas de risco e alertas do insider com níveis de severidade mais altos. Prioridade os usuários são definidos em grupos de usuários de prioridade configurados na área configurações de gerenciamento de risco do insider. ADICIONAR LINK

Assim como com o **modelo vazamentos de dados gerais**, você deve atribuir uma política de DLP para acionar indicadores na política de risco do insider para alertas de alta gravidade em sua organização. Siga as diretrizes de política de vazamento de dados acima ao criar uma política usando esse modelo. Além disso, você precisará atribuir grupos de usuários de prioridade criados nos grupos de usuários de prioridade de **Gerenciamento de risco do insider**  >  **Settings**  >  **Priority user groups** à política.

### <a name="data-leaks-by-disgruntled-users-preview"></a>Vazamentos de dados por usuários descontentes (visualização)

Quando os usuários experimentam os aeroestresse de emprego, eles podem se tornar insatisfeitos, o que pode aumentar as chances de atividade de risco do insider. Este modelo inicia a pontuação da atividade do usuário quando um indicador associado a desconter é identificado. Os exemplos incluem notificações de melhoria do desempenho, revisões de desempenho ruins ou alterações no status do nível de trabalho. Vazamentos de dados para usuários insatisfeitos podem incluir o download de arquivos do SharePoint Online e a cópia de dados para serviços de serviço de mensagens de nuvem pessoal e serviços de armazenamento próximos a eventos de estresse de emprego.

Ao usar esse modelo, você também deve configurar um conector de RH da Microsoft 365 para importar periodicamente notificações de melhoria de desempenho, status de análise de desempenho ruim ou informações de alteração de nível de trabalho para usuários em sua organização. Consulte o artigo [importar dados com o conector de RH](import-hr-data.md) para obter orientações passo a passo para configurar o Microsoft 365 HR Connector para sua organização.

### <a name="general-security-policy-violations-preview"></a>Violações de política de segurança geral (versão prévia)

Em muitas organizações, os usuários têm permissões para instalar o software em seus dispositivos ou para modificar as configurações do dispositivo para ajudar com suas tarefas. Inadvertidamente ou com más intenções, os usuários podem instalar malware ou desabilitar recursos de segurança importantes que ajudam a proteger informações em seus dispositivos ou em seus recursos de rede. Este modelo de política usa alertas de segurança da proteção avançada contra ameaças do Microsoft defender (ATP) para começar a pontuação dessas atividades e detecção de foco e alertas para esta área de risco. Use este modelo para fornecer informações sobre violações de política de segurança em cenários quando os usuários podem ter um histórico de violações de política de segurança que podem ser um indicador de risco de insider.

Você precisará ter o Microsoft defender ATP configurado em sua organização e habilitar o Microsoft defender ATP para integração de gerenciamento de risco do insider na central de segurança do defender para importar alertas de violação de segurança. Para obter mais informações sobre como configurar o Microsoft defender ATP para integração do gerenciamento de risco do Insider, consulte [configurar recursos avançados no Microsoft defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center).

### <a name="security-policy-violations-by-departing-users-preview"></a>Violações de política de segurança por parte dos usuários (visualização)

A desativação de usuários, independentemente de termos positivos ou negativos, pode ser um risco maior para violações de política de segurança. Para ajudar a proteger contra violações de segurança inadvertidas ou mal-intencionadas para a parte dos usuários, este modelo de política usa os alertas do Microsoft defender ATP para fornecer informações sobre atividades relacionadas à segurança. Essas atividades incluem o usuário que está instalando malware ou outros aplicativos potencialmente prejudiciais e desativando os recursos de segurança em seus dispositivos. Os indicadores de política são ativados depois que os usuários têm uma data de demissão ou de término importada do Microsoft 365 HR Connector como um evento de acionamento.

Ao usar esse modelo, você deve configurar um conector de RH da Microsoft 365 para importar periodicamente informações de data de demissão e de término para usuários em sua organização. Consulte o artigo [importar dados com o conector de RH](import-hr-data.md) para obter orientações passo a passo para configurar o Microsoft 365 HR Connector para sua organização.

Você precisará ter o Microsoft defender ATP configurado em sua organização e habilitar o Microsoft defender ATP para integração de gerenciamento de risco do insider na central de segurança do defender para importar alertas de violação de segurança. Para obter mais informações sobre como configurar o Microsoft defender ATP para integração do gerenciamento de risco do Insider, consulte [configurar recursos avançados no Microsoft defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center).

### <a name="security-policy-violations-by-priority-users-preview"></a>Violações de política de segurança por usuários de prioridade (prévia)

A proteção contra violações de segurança para usuários em sua organização pode depender de sua posição, nível de acesso a informações confidenciais ou histórico de riscos. Como as violações de segurança por usuários prioritários podem ter um impacto de baixo tamanho nas áreas críticas da sua organização, esse modelo de política inicia a pontuação nesses indicadores e usa os alertas do Microsoft defender ATP para fornecer informações sobre atividades relacionadas à segurança para esses usuários. Podem incluir a prioridade dos usuários que instalam malware ou outros aplicativos potencialmente prejudiciais e desabilitando recursos de segurança em seus dispositivos. Prioridade os usuários são definidos em grupos de usuários de prioridade configurados na área configurações de gerenciamento de risco do insider.

Você precisará ter o Microsoft defender ATP configurado em sua organização e habilitar o Microsoft defender ATP para integração de gerenciamento de risco do insider na central de segurança do defender para importar alertas de violação de segurança. Para obter mais informações sobre como configurar o Microsoft defender ATP para integração do gerenciamento de risco do Insider, consulte [configurar recursos avançados no Microsoft defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center). Além disso, você precisará atribuir grupos de usuários de prioridade criados nos grupos de usuários de prioridade de **Gerenciamento de risco do insider**  >  **Settings**  >  **Priority user groups** à política.

### <a name="security-policy-violations-by-disgruntled-users-preview"></a>Violações de política de segurança por usuários descontentes (visualização)

Os usuários que experimentarem os aeroestresse podem ser um risco maior para violações de política de segurança inadvertidas ou mal-intencionadas. Esses encargos podem incluir o usuário que está sendo colocado em um plano de melhoria de desempenho, um status de análise de desempenho ruim ou ser rebaixado de sua posição atual. Este modelo de política inicia a pontuação de risco com base nesses indicadores e atividades associados a esses eventos para esses usuários.

Ao usar esse modelo, você também deve configurar um conector de RH da Microsoft 365 para importar periodicamente notificações de melhoria de desempenho, status de análise de desempenho ruim ou informações de alteração de nível de trabalho para usuários em sua organização. Consulte o artigo [importar dados com o conector de RH](import-hr-data.md) para obter orientações passo a passo para configurar o Microsoft 365 HR Connector para sua organização.

Você também precisará ter o Microsoft defender ATP configurado em sua organização e habilitar o Microsoft defender ATP para integração de gerenciamento de risco do insider na central de segurança do defender para importar alertas de violação de segurança. Para obter mais informações sobre como configurar o Microsoft defender ATP para integração do gerenciamento de risco do Insider, consulte [configurar recursos avançados no Microsoft defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center).

### <a name="offensive-language-in-email"></a>Idioma ofensivo no email

Detectar e realizar ações para impedir o comportamento ofensivo e abusivo é um componente essencial da prevenção de riscos. Classificadores internos no Microsoft 365 Scan mensagens de email de caixas de correio do Exchange Online em sua organização para diferentes tipos de problemas de conformidade. Esses classificadores usam uma combinação de inteligência artificial e palavras-chave para identificar o idioma em que o email provavelmente viola as políticas antiassédio. Use este modelo para criar rapidamente uma política que use esses classificadores para detectar automaticamente o conteúdo de mensagens de email que pode ser considerado abusivo ou ofensivo. O gerenciamento de risco do insider usa classificadores que verificam as mensagens de email enviadas para termos do idioma inglês e uma inversão para linguagem ofensiva.

### <a name="policy-template-prerequisites-and-triggering-events"></a>Pré-requisitos de modelo de política e eventos de disparo

Dependendo do modelo escolhido para uma política de gerenciamento de risco do Insider, os eventos de acionamento e os pré-requisitos de política variam. Eventos de acionamento são pré-requisitos que determinam se um usuário está ativo para uma política de gerenciamento de risco do insider. Se um usuário for adicionado a uma política de gerenciamento de risco do Insider, mas não tiver um evento de disparo, a atividade do usuário não será avaliada pela política, a menos que sejam adicionadas manualmente no painel usuários. Os pré-requisitos de política são itens obrigatórios para que a política receba os sinais ou as atividades necessárias para avaliar o risco.

A tabela a seguir lista os eventos de acionamento e os pré-requisitos para políticas criadas a partir de cada modelo de política de gerenciamento de risco do insider:

| **Modelo de política** | **Disparando eventos para políticas** | **Pré-requisitos** |
| :------------------ | :--------------------------------- | :---------------- |
| Roubo de dados por parte de usuários | Indicador de data de demissão ou demissão do conector de RH | Conector de RH da Microsoft 365 configurado para indicadores de data de término e demissão |
| Vazamentos de dados gerais | Atividade de política de perda de dados que cria um alerta de alta gravidade | Política de DLP configurada para alertas de alta gravidade |
| Vazamentos de dados por usuários de prioridade | Atividade de política de perda de dados que cria um alerta de alta gravidade | Política de DLP configurada para alertas de alta gravidade <br><br> Grupos de usuários de prioridade definidos nas configurações de risco do insider |
| Vazamentos de dados por usuários descontentes | Melhoria do desempenho, desempenho ruim ou indicadores de alteração no nível do trabalho do conector de RH | Conector de RH da Microsoft 365 configurado para indicadores de insatisfeito |
| Violações de política de segurança geral | Evasion defensiva de controles de segurança ou softwares indesejados detectados pelo Microsoft defender ATP | Assinatura ATP do Microsoft defender ativa <br><br> Integração do Microsoft defender ATP com o centro de conformidade da Microsoft 365 configurado |
| Violações de política de segurança por parte dos usuários | Indicadores de data de demissão ou demissão do conector de RH | Conector de RH da Microsoft 365 configurado para indicadores de data de término e demissão <br><br> Assinatura ATP do Microsoft defender ativa <br><br> Integração do Microsoft defender ATP com o centro de conformidade da Microsoft 365 configurado |
| Violações de política de segurança por usuários de prioridade | Evasion defensiva de controles de segurança ou softwares indesejados detectados pelo Microsoft defender ATP | Assinatura ATP do Microsoft defender ativa <br><br> Integração do Microsoft defender ATP com o centro de conformidade da Microsoft 365 configurado <br><br> Grupos de usuários de prioridade definidos nas configurações de risco do insider |
| Violações de política de segurança por usuário descontente | Melhoria do desempenho, desempenho ruim ou indicadores de alteração no nível do trabalho do conector de RH | Conector de RH da Microsoft 365 configurado para indicadores de insatisfeito <br><br> Assinatura ATP do Microsoft defender ativa <br><br> Integração do Microsoft defender ATP com o centro de conformidade da Microsoft 365 configurado |
| Idioma ofensivo no email | Profanação, ameaças ou idioma assédio em mensagens de email | Assinatura ativa do Exchange Online |

## <a name="prioritize-content-in-policies"></a>Priorizar o conteúdo nas políticas

As políticas de gerenciamento de risco do insider oferecem suporte à especificação de uma prioridade mais alta para o conteúdo, dependendo de onde estejam armazenadas ou como são classificadas. A especificação de conteúdo como prioridade aumenta a pontuação de risco para qualquer atividade associada, o que, por sua vez, aumenta a chance de gerar um alerta de alta gravidade. No entanto, algumas atividades não gerarão nenhum alerta, a menos que o conteúdo relacionado contenha tipos de informações confidenciais internas ou personalizadas ou tenha sido especificado como uma prioridade na política.

Por exemplo, sua organização tem um site dedicado do SharePoint para um projeto altamente confidencial. Os vazamentos de dados para informações neste site do SharePoint podem comprometer o projeto e ter um impacto significativo em seu sucesso. Ao priorizar esse site do SharePoint em uma política de vazamento de dados, a pontuação de risco para atividades de qualificação é aumentada automaticamente. Isso aumenta a probabilidade de que essas atividades gerem um alerta de risco Insider e aumentam o nível de severidade para o alerta.

Ao criar uma política de gerenciamento de risco do insider no assistente de política, você pode escolher entre as seguintes prioridades:

- **Sites do SharePoint**: qualquer atividade associada a todos os tipos de arquivo em sites do SharePoint definidos é atribuída uma pontuação de risco maior. 
- **Tipos de informações confidenciais**: qualquer atividade associada ao conteúdo que contenha [tipos de informações confidenciais](sensitive-information-type-entity-definitions.md) é atribuída uma pontuação de risco maior.
- **Rótulos de sensibilidade**: qualquer atividade associada ao conteúdo que tenha [Rótulos de confidencialidade](sensitivity-labels.md) específicos aplicados recebe uma pontuação de risco mais alta.

## <a name="create-a-new-policy"></a>Criar uma nova política

Para criar uma nova política de gerenciamento de risco do Insider, você usará o assistente de política na solução de **Gerenciamento de risco do insider** no centro de conformidade da Microsoft 365.

Conclua as seguintes etapas para criar uma nova política:

1. No [centro de conformidade da Microsoft 365](https://compliance.microsoft.com), vá para gerenciamento de **risco do insider** e selecione a guia **políticas** .
2. Selecione **criar política** para abrir o assistente de política
3. Na página **nova política de riscos de insider** , preencha os seguintes campos:
    - **Nome (obrigatório)**: Insira um nome amigável para a política.
    - **Descrição (opcional)**: Insira uma descrição para a política.
    - **Escolher modelo de política (obrigatório)**: selecione um dos [modelos de política](insider-risk-management-policies.md#policy-templates) para definir os tipos de indicadores de risco são monitorados pela política.

    >[!IMPORTANT]
    >A maioria dos modelos de política tem pré-requisitos que devem ser configurados para que a política Gere alertas relevantes. Se você não tiver configurado os pré-requisitos de política aplicáveis, confira [introdução ao gerenciamento de riscos do insider](insider-risk-management-configure.md#step-3-configure-prerequisites-for-templates).

4. Selecione **Avançar** para continuar.
5. Na página **usuários** , selecione **Adicionar usuário ou grupo** ou **escolha prioridade grupos de usuários** para definir quais usuários ou grupos de usuários de prioridade estão incluídos na política, dependendo do modelo de política que você selecionou. Marque a caixa **de seleção todos os usuários e grupos habilitados para email,** se aplicável (se você não tiver selecionado um modelo com prioridade de usuário). Selecione **Avançar** para continuar.
6. Na página **especificar qual conteúdo priorizar (opcional)** , você pode atribuir as fontes a serem priorizadas para maiores pontuações de risco. No entanto, algumas atividades não gerarão nenhum alerta, a menos que o conteúdo relacionado contenha tipos de informações confidenciais internas ou personalizadas ou tenha sido especificado como uma prioridade nesta página:
    - **Sites do SharePoint**: selecione **Adicionar site do SharePoint** e selecione as organizações do SharePoint que você deseja priorizar. Por exemplo, *"group1@contoso.sharepoint.com/sites/group1"*.
    - **Tipo de informação confidencial**: selecione **Adicionar tipo de informações confidenciais** e selecione os tipos de sensibilidade que você deseja priorizar. Por exemplo, *"número de conta bancária dos EUA"* e *"número do cartão de crédito"*.
    - **Rótulos de sensibilidade**: selecione **Adicionar rótulo de confidencialidade** e selecione os rótulos que você deseja priorizar. Por exemplo, *"confidencial"* e *"segredo"*.
7. Selecione **Avançar** para continuar.
8. Na página **selecionar indicadores de política** , você verá os [indicadores](insider-risk-management-settings.md#indicators) definidos como disponíveis na página indicadores de configurações de **risco do insider**  >  **Indicators** . Se você selecionou um modelo de *vazamentos de dados* no início do assistente, deverá selecionar uma política de DLP na lista suspensa **política de DLP** para habilitar os indicadores de disparo para a política. Selecione os indicadores que você deseja aplicar à política. Se preferir não usar as configurações de limite de política padrão para esses indicadores, desabilite o **uso de limiares padrão recomendados pela Microsoft** e insira os valores de limite para cada indicador selecionado. Se você tiver selecionado pelo menos um indicador do *Office* ou *dispositivo* , selecione os **aceleradores de Pontuação de risco** conforme apropriado. Os aumentos de Pontuação de risco só se aplicam aos indicadores selecionados.

    >[!IMPORTANT]
    >Se os indicadores nesta página não puderem ser selecionados, você precisará selecionar os indicadores que deseja habilitar para todas as políticas na página de indicadores de política de configurações de **Gerenciamento de risco do insider**  >  **Settings**  >  **Policy indicators** .

9. Selecione **Avançar** para continuar.
10. Na página **políticas de tempo de política** , você verá as [condições da janela de ativação](insider-risk-management-settings.md#policy-timeframes) para a política que na página períodos de tempo da política de configurações de risco do **Insider**  >  **Policy timeframes** .
11. Selecione **Avançar** para continuar.
12. Na página **revisão** , revise as configurações escolhidas para a política. Selecione **Editar** para alterar qualquer um dos valores da política ou selecione **Enviar** para criar e ativar a política.

## <a name="update-a-policy"></a>Atualizar uma política

Para atualizar uma política de gerenciamento de risco do insider existente, você usará o assistente de política na solução de **Gerenciamento de risco do insider** no centro de conformidade da Microsoft 365.

Conclua as seguintes etapas para gerenciar uma política existente:

1. No [centro de conformidade da Microsoft 365](https://compliance.microsoft.com), vá para gerenciamento de **risco do insider** e selecione a guia **políticas** .
2. No painel de políticas, selecione a política que você deseja gerenciar.
3. Na página detalhes da política, selecione **Editar política**
4. No assistente de política, não é possível editar os seguintes campos:
    - **Nome**: o nome amigável da política
    - **Escolha modelo de política**: o modelo usado para definir os tipos de indicadores de risco monitorados pela política.
5. Insira uma nova descrição para a política no campo **Descrição** . 
6. Selecione **Avançar** para continuar.
7. Na página **usuários** , selecione **Adicionar usuário ou grupo** ou **escolha prioridade grupos de usuários** para definir quais usuários ou grupos de usuários de prioridade estão incluídos na política, dependendo do modelo de política que você selecionou. Marque a caixa **de seleção todos os usuários e grupos habilitados para email,** se aplicável (se você não tiver selecionado um modelo com prioridade de usuário). Selecione **Avançar** para continuar.
8. Na página **especificar qual conteúdo priorizar (opcional)** , você pode atribuir as fontes a serem priorizadas para maiores pontuações de risco. No entanto, algumas atividades não gerarão nenhum alerta, a menos que o conteúdo relacionado contenha tipos de informações confidenciais internas ou personalizadas ou tenha sido especificado como uma prioridade nesta página:
    - **Sites do SharePoint**: selecione **Adicionar site do SharePoint** e selecione as organizações do SharePoint que você deseja priorizar. Por exemplo, *"group1@contoso.sharepoint.com/sites/group1"*.
    - **Tipo de informação confidencial**: selecione **Adicionar tipo de informações confidenciais** e selecione os tipos de sensibilidade que você deseja priorizar. Por exemplo, *"número de conta bancária dos EUA"* e *"número do cartão de crédito"*.
    - **Rótulos de sensibilidade**: selecione **Adicionar rótulo de confidencialidade** e selecione os rótulos que você deseja priorizar. Por exemplo, *"confidencial"* e *"segredo"*.
9. Selecione **Avançar** para continuar.
10. Na página **selecionar indicadores de política** , você verá os [indicadores](insider-risk-management-settings.md#indicators) definidos como disponíveis na página indicadores de configurações de **risco do insider**  >  **Indicators** . Se você selecionou um modelo de *vazamentos de dados* no início do assistente, deverá selecionar uma política de DLP na lista suspensa **política de DLP** para habilitar os indicadores de disparo para a política. Selecione os indicadores que você deseja aplicar à política. Se preferir não usar as configurações de limite de política padrão para esses indicadores, desabilite o **uso de limiares padrão recomendados pela Microsoft** e insira os valores de limite para cada indicador selecionado. Se você tiver selecionado pelo menos um indicador do *Office* ou *dispositivo* , selecione os **aceleradores de Pontuação de risco** conforme apropriado. Os aumentos de Pontuação de risco só se aplicam aos indicadores selecionados.

    >[!IMPORTANT]
    >Se os indicadores nesta página não puderem ser selecionados, você precisará selecionar os indicadores que deseja habilitar para todas as políticas na página de indicadores de política de configurações de **Gerenciamento de risco do insider**  >  **Settings**  >  **Policy indicators** .

11. Selecione **Avançar** para continuar.
12. Na página **políticas de tempo de política** , você verá as [condições da janela de ativação](insider-risk-management-settings.md#policy-timeframes) para a política que na página períodos de tempo da política de configurações de risco do **Insider**  >  **Policy timeframes** .
13. Selecione **Avançar** para continuar.
14. Na página **revisão** , revise as configurações que você atualizou para a política. Selecione **Editar** para alterar qualquer um dos valores da política ou selecione **Enviar** para atualizar e ativar a política.

## <a name="delete-a-policy"></a>Excluir uma política

>[!NOTE]
>A exclusão de uma política não exclui alertas ativos ou arquivados gerados da política.

Para excluir uma política de gerenciamento de risco do insider existente, conclua as seguintes etapas:

1. No [centro de conformidade da Microsoft 365](https://compliance.microsoft.com), vá para gerenciamento de **risco do insider** e selecione a guia **políticas** .
2. No painel de políticas, selecione a política que deseja excluir.
3. Selecione **excluir** na barra de ferramentas do painel.
4. Na caixa de diálogo **excluir** , selecione **Sim** para excluir a política ou selecione **Cancelar** para fechar a caixa de diálogo.
