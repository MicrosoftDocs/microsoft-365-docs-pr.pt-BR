---
title: Políticas de gerenciamento de riscos internas
description: Saiba mais sobre as políticas internas de gerenciamento de riscos no Microsoft 365
keywords: Microsoft 365, gerenciamento de riscos insider, gerenciamento de riscos, conformidade
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
ms.openlocfilehash: 1093d664e58f77d94db9f6f922a1a5072f4d3982
ms.sourcegitcommit: c0cfb9b354db56fdd329aec2a89a9b2cf160c4b0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2021
ms.locfileid: "50094694"
---
# <a name="insider-risk-management-policies"></a>Políticas de gerenciamento de riscos internas

As políticas de gerenciamento de riscos internas determinam quais usuários estão no escopo e quais tipos de indicadores de risco são configurados para alertas. Você pode criar rapidamente uma política que se aplique a todos os usuários em sua organização ou definir usuários individuais ou grupos para gerenciamento em uma política. As políticas suportam prioridades de conteúdo para focalizar as condições de política em várias ou específicas do Microsoft Teams, sites do SharePoint, tipos de sensibilidade de dados e rótulos de dados específicos. Usando modelos, você pode selecionar indicadores de risco específicos e personalizar limites de eventos para indicadores de política, personalização eficaz de pontuações de risco e nível e frequência de alertas. Além disso, as pontuações de risco e as detecções de anomalias ajudam a identificar a atividade do usuário de maior importância ou mais incomum. As janelas de políticas permitem definir o período de tempo para aplicar a política às atividades de alerta e são usadas para determinar a duração da política depois de ativada.

## <a name="policy-dashboard"></a>Painel de políticas

O **painel política** permite que você veja rapidamente as políticas em sua organização e o status atual dos alertas associados a cada política.

- **Nome da** política: o nome atribuído à política no assistente de política.
- **Alertas ativos:** o número de alertas ativos para cada política.
- **Alertas confirmados:** o número total de alertas que resultaram em casos da política nos últimos 365 dias.
- **Ações tomadas em alertas:** o número total de alertas confirmados ou ignorados nos últimos 365 dias.
- **Eficácia da política:** a porcentagem determinada pelo total de alertas confirmados divididos pelo total de ações tomadas em alertas (que é a soma de alertas confirmados ou ignorados no ano passado).
- **Ativo**: o status da ocorrência, *Sim* ou *Não.*

![Painel de política de gerenciamento de riscos interno](../media/insider-risk-policy-dashboard.png)

## <a name="policy-templates"></a>Modelos de política

Os modelos de gerenciamento de riscos insider são condições de política predefinida que definem os tipos de indicadores de risco e o modelo de pontuação de risco usado pela política. Cada política deve ter um modelo atribuído no assistente de criação de política antes que a política seja criada. O gerenciamento de riscos insider dá suporte a até cinco políticas para cada modelo de política. Ao criar uma nova política de risco interno com o assistente de política, você escolherá entre um dos seguintes modelos de política:

### <a name="data-theft-by-departing-users"></a>Roubo de dados por parte dos usuários

Quando os usuários saem da sua organização, há indicadores de risco específicos normalmente associados ao roubo de dados por parte dos usuários. Esse modelo de política usa indicadores para pontuação de risco e concentra a detecção e alertas nessa área de risco. O roubo de dados para usuários de saída pode incluir o download de arquivos do SharePoint Online, a impressão de arquivos e a cópia de dados para serviços pessoais de mensagens e armazenamento em nuvem perto de suas datas de término e de emprego. Este modelo começa a pontuação para indicadores de risco relacionados a essas atividades e como eles se correlacionam com o status de emprego do usuário.

>[!IMPORTANT]
>Ao usar esse modelo, você deve configurar um conector de RH do Microsoft 365 para importar periodicamente informações de datas de término e de término para usuários em sua organização. Consulte o [artigo Importar dados com o](import-hr-data.md) conector de RH para obter orientação passo a passo para configurar o conector de RH do Microsoft 365 para sua organização.

### <a name="general-data-leaks"></a>Vazamentos gerais de dados

Proteger dados e evitar vazamentos de dados é um desafio constante para a maioria das organizações, especialmente com o rápido aumento de novos dados criados por usuários, dispositivos e serviços. Os usuários podem criar, armazenar e compartilhar informações entre serviços e dispositivos que dificultam o gerenciamento de vazamentos de dados cada vez mais complexos e difíceis. Os vazamentos de dados podem incluir o compartilhamento acidental de informações fora da sua organização ou o roubo de dados com intenção mal-intencionada. Em conjunto com uma política de Prevenção contra Perda de Dados (DLP) atribuída, este modelo começa a pontuar detecções em tempo real de downloads de dados suspeitos do SharePoint Online, compartilhamento de arquivos e pastas, impressão de arquivos e cópia de dados para serviços pessoais de armazenamento e mensagens em nuvem.

Ao usar um **modelo de vazamento de** dados, você deve atribuir uma política de DLP para disparar indicadores na política de risco interno para alertas de alta gravidade em sua organização. Sempre que um alerta de alta gravidade é gerado por uma regra de política de DLP é adicionado ao log de auditoria do Office 365, as políticas de risco interno criadas com esse modelo examinam automaticamente o alerta DLP de alta gravidade. Se o alerta contiver um usuário dentro do escopo definido na política de risco interno, o alerta será processado pela política de risco interno como um novo alerta e atribuído a uma gravidade de risco interno e pontuação de risco. Essa política permite avaliar esse alerta em contexto com outras atividades incluídas no caso.

#### <a name="data-leaks-policy-guidelines"></a>Diretrizes de política de vazamento de dados

Ao criar ou modificar políticas DLP para uso com políticas de gerenciamento de riscos insider, considere as seguintes diretrizes:

- Priorize eventos de exfiltração  de dados e seja seletivo ao atribuir configurações de relatórios de incidentes a *Alta* ao configurar regras em suas políticas de DLP. Por exemplo, enviar emails de documentos confidenciais para uma pessoa conhecida deve ser um *evento de* exfiltração de alto nível de alerta. O excesso de  atribuição  do nível Alto nas configurações de relatórios de incidentes em outras regras de política de DLP pode aumentar o ruído no fluxo de trabalho de alerta de gerenciamento de risco interno e tornar mais difícil para seus investigadores e analistas de dados avaliar corretamente esses alertas. Por exemplo, atribuir níveis *de* alerta Alto para acessar atividades de negação em políticas de DLP torna mais desafiador avaliar atividades e comportamentos realmente arriscados do usuário.
- Certifique-se de entender e configurar corretamente os usuários no escopo nas políticas de gerenciamento de riscos de DLP e insider. Somente usuários definidos como no escopo para políticas de gerenciamento de riscos insider usando o modelo vazamentos de dados terão **alertas** de política DLP de alta gravidade processados. Além disso, somente os usuários definidos como no escopo em uma regra para um alerta DLP de alta gravidade serão examinados pela política de gerenciamento de risco interno para serem considerados. É importante que você não configure sem saber os usuários no escopo em suas políticas de risco interno e DLP de maneira conflitante.

     Por exemplo, se suas regras de política de DLP têm como escopo apenas usuários na Equipe de Vendas e a política de risco interno criada a partir do modelo **vazamentos** de dados definiu todos os usuários como dentro do escopo, a política de risco interno processará apenas alertas de DLP de alta gravidade para os usuários na Equipe de Vendas. A política de risco interno não receberá alertas DLP de alta prioridade para que os usuários processem que não estão definidos nas regras de DLP neste exemplo. Por outro lado, se sua política  de gerenciamento de riscos interno criada a partir de modelos de vazamento de dados tiver como escopo apenas os usuários da Equipe de Vendas e a política de DLP atribuída tiver como escopo todos os usuários, a política de risco interno processará apenas alertas de DLP de alta gravidade para membros da Equipe de Vendas. A política de gerenciamento de risco interno ignorará alertas DLP de alta gravidade para todos os usuários que não estão na Equipe de Vendas.

- Certifique-se **de que a** configuração de regra de relatórios de incidentes na política de DLP usada para esse modelo de gerenciamento de riscos interno está configurada para *alertas* de alto nível de gravidade. O *nível* de alta gravidade são os eventos de disparo e os alertas de gerenciamento  de risco interno não serão gerados a partir de regras em políticas DLP com o campo relatórios de incidentes definido como *Baixo* ou *Médio.*

    ![Configuração de alerta de política de DLP](../media/insider-risk-DLP-policy-high-severity.png)

     >[!NOTE]
     >Ao criar uma nova política DLP usando os modelos integrados, você precisará selecionar a opção  Criar ou personalizar  regras **DLP** avançadas para definir a configuração de relatórios de incidentes para o nível de alta gravidade.

Cada política de gerenciamento de riscos internas criada a partir do modelo **vazamentos** de dados pode ter apenas uma política de DLP atribuída. Considere a criação de uma política DLP dedicada que combine as diferentes atividades que você deseja detectar e agir como gatilho de eventos para políticas de risco interno que usam o modelo **vazamentos de** dados.

Consulte o [artigo Criar, testar](create-test-tune-dlp-policy.md) e ajustar um artigo de política de DLP para obter orientação passo a passo sobre como configurar políticas DLP para sua organização.

### <a name="data-leaks-by-priority-users-preview"></a>Vazamentos de dados por usuários prioritários (visualização)

Proteger dados e evitar vazamentos de dados para usuários em sua organização pode depender de sua posição, nível de acesso a informações confidenciais ou histórico de riscos. Os vazamentos de dados podem incluir o compartilhamento acidental de informações altamente confidenciais fora da sua organização ou o roubo de dados com intenção mal-intencionada. Em conjunto com uma política de Prevenção contra Perda de Dados (DLP) atribuída, esse modelo começa a pontuar detecções em tempo real de atividades suspeitas e resulta em uma maior probabilidade de alertas e alertas de risco interno com níveis de gravidade mais altos. Os usuários prioritários são definidos em grupos [de usuários](insider-risk-management-settings.md#priority-user-groups-preview) prioritários configurados na área de configurações de gerenciamento de risco interno.

Assim como no modelo geral de **vazamentos** de dados, você deve atribuir uma política de DLP para disparar indicadores na política de risco interno para alertas de alta gravidade em sua organização. Siga as diretrizes de política de vazamentos de dados acima ao criar uma política usando esse modelo. Além disso, você precisará atribuir grupos de usuários prioritários criados em grupos de usuários de Prioridade de Configurações de Gerenciamento de Risco do **Insider**  >    >   à política.

### <a name="data-leaks-by-disgruntled-users-preview"></a>Vazamentos de dados por usuários não coerentes (visualização)

Quando os usuários experimentam stressores de emprego, eles podem ficar descontenados, o que pode aumentar as chances de atividade de risco interno. Esse modelo começa a pontuar a atividade do usuário quando um indicador associado a descongrupo é identificado. Exemplos incluem notificações de melhoria de desempenho, revisões de desempenho ruins ou alterações no status do nível do trabalho. Os vazamentos de dados para usuários não congruentes podem incluir o download de arquivos do SharePoint Online e a cópia de dados para mensagens pessoais na nuvem e serviços de armazenamento próximos a eventos de stressor de emprego.

Ao usar esse modelo, você também deve configurar um conector de RH do Microsoft 365 para importar periodicamente notificações de melhoria de desempenho, status de revisão de desempenho ruim ou informações de alteração de nível de trabalho para usuários em sua organização. Consulte o [artigo Importar dados com o](import-hr-data.md) conector de RH para obter orientação passo a passo para configurar o conector de RH do Microsoft 365 para sua organização.

### <a name="general-security-policy-violations-preview"></a>Violações gerais da política de segurança (visualização)

Em muitas organizações, os usuários têm permissões para instalar software em seus dispositivos ou modificar as configurações do dispositivo para ajudar em suas tarefas. Inadvertidamente ou com intenção mal-intencionada, os usuários podem instalar malware ou desabilitar recursos de segurança importantes que ajudam a proteger informações em seus dispositivos ou em seus recursos de rede. Esse modelo de política usa alertas de segurança do Microsoft Defender para o Ponto de Extremidade para começar a pontuar essas atividades e a detecção de foco e alertas para essa área de risco. Use este modelo para fornecer informações sobre violações de política de segurança em cenários em que os usuários podem ter um histórico de violações de política de segurança que podem ser um indicador de riscos de informações internas.

Você precisará ter o Microsoft Defender para Ponto de Extremidade configurado em sua organização e habilitar o Defender para Ponto de Extremidade para integração de gerenciamento de riscos insider na Central de Segurança do Defender para importar alertas de violação de segurança. Para obter mais informações sobre como configurar o Defender para Endpoint para integração de gerenciamento de riscos insider, consulte Configurar recursos avançados no [Defender para Ponto de Extremidade.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center)

### <a name="security-policy-violations-by-departing-users-preview"></a>Violações da política de segurança ao separar usuários (visualização)

Sair dos usuários, deixando termos positivos ou negativos, pode ser um risco maior para violações da política de segurança. Para ajudar a proteger contra violações de segurança inadvertida ou mal-intencionadas para usuários departativos, esse modelo de política usa o Defender para alertas de ponto de extremidade para fornecer informações sobre atividades relacionadas à segurança. Essas atividades incluem o usuário instalando malware ou outros aplicativos potencialmente prejudiciais e desabilitando recursos de segurança em seus dispositivos. Os indicadores de política são ativados depois que os usuários têm uma data de cancelamento ou de cancelamento importada do Conector de RH do Microsoft 365 como um evento de disparo.

Ao usar esse modelo, você deve configurar um conector de RH do Microsoft 365 para importar periodicamente informações de datas de término e de término para usuários em sua organização. Consulte o [artigo Importar dados com o](import-hr-data.md) conector de RH para obter orientação passo a passo para configurar o conector de RH do Microsoft 365 para sua organização.

Você precisará ter o Microsoft Defender para Ponto de Extremidade configurado em sua organização e habilitar o Defender para Ponto de Extremidade para integração de gerenciamento de riscos insider na Central de Segurança do Defender para importar alertas de violação de segurança. Para obter mais informações sobre como configurar o Defender para Endpoint para integração de gerenciamento de riscos insider, consulte Configurar recursos avançados [no Defender para Ponto de Extremidade.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center)

### <a name="security-policy-violations-by-priority-users-preview"></a>Violações de política de segurança por usuários prioritários (visualização)

A proteção contra violações de segurança para usuários em sua organização pode depender de sua posição, nível de acesso a informações confidenciais ou histórico de riscos. Como as violações de segurança por prioridade dos usuários podem ter um impacto maior nas áreas críticas da sua organização, esse modelo de política começa a pontuar esses indicadores e usa o Microsoft Defender para alertas de ponto de extremidade para fornecer informações sobre atividades relacionadas à segurança para esses usuários. Isso pode incluir os usuários prioritários instalando malware ou outros aplicativos potencialmente prejudiciais e desabilitando recursos de segurança em seus dispositivos. Os usuários prioritários são definidos em grupos de usuários prioritários configurados na área de configurações de gerenciamento de risco interno.

Você precisará ter o Microsoft Defender para Ponto de Extremidade configurado em sua organização e habilitar o Defender para Ponto de Extremidade para integração de gerenciamento de riscos insider na Central de Segurança do Defender para importar alertas de violação de segurança. Para obter mais informações sobre como configurar o Defender para Endpoint para integração de gerenciamento de riscos insider, consulte Configurar recursos avançados [no Defender para Ponto de Extremidade.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center) Além disso, você precisará atribuir grupos de usuários prioritários criados em grupos de usuários de Prioridade de Configurações de Gerenciamento de Risco do **Insider**  >    >   à política.

### <a name="security-policy-violations-by-disgruntled-users-preview"></a>Violações da política de segurança por usuários não coerentes (visualização)

Os usuários que experimentam estresseres de emprego podem estar em um risco mais alto por violações de política de segurança inadvertida ou mal-intencionada. Esses stressores podem incluir o usuário sendo colocado em um plano de melhoria de desempenho, status de revisão de desempenho ruim ou rebaixado de sua posição atual. Este modelo de política inicia a pontuação de risco com base nesses indicadores e atividades associadas a esses eventos para esses usuários.

Ao usar esse modelo, você também deve configurar um conector de RH do Microsoft 365 para importar periodicamente notificações de melhoria de desempenho, status de revisão de desempenho ruim ou informações de alteração de nível de trabalho para usuários em sua organização. Consulte o [artigo Importar dados com o](import-hr-data.md) conector de RH para obter orientação passo a passo para configurar o conector de RH do Microsoft 365 para sua organização.

Você também precisará ter o Microsoft Defender para Ponto de Extremidade configurado em sua organização e habilitar o Defender para Ponto de Extremidade para integração de gerenciamento de riscos insider na Central de Segurança do Defender para importar alertas de violação de segurança. Para obter mais informações sobre como configurar o Defender para Endpoint para integração de gerenciamento de riscos insider, consulte Configurar recursos avançados [no Defender para Ponto de Extremidade.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center)

### <a name="policy-template-prerequisites-and-triggering-events"></a>Pré-requisitos de modelo de política e eventos de disparo

Dependendo do modelo escolhido para uma política de gerenciamento de riscos interno, os eventos de disparo e os pré-requisitos de política variam. Eventos de disparo são pré-requisitos que determinam se um usuário está ativo para uma política de gerenciamento de riscos interno. Se um usuário for adicionado a uma política de gerenciamento de riscos interno, mas não tiver um evento de disparo, a atividade do usuário não será avaliada pela política, a menos que seja adicionada manualmente no painel Usuários. Os pré-requisitos de política são itens necessários para que a política receba os sinais ou as atividades necessárias para avaliar o risco.

A tabela a seguir lista os eventos de disparo e pré-requisitos para políticas criadas a partir de cada modelo de política de gerenciamento de risco interno:

| **Modelo de política** | **Disparando eventos para políticas** | **Pré-requisitos** |
| :------------------ | :--------------------------------- | :---------------- |
| Roubo de dados por parte dos usuários | Indicador de data de rescisão ou de rescisão do conector de RH | Conector de RH do Microsoft 365 configurado para indicadores de data de término e de demissão |
| Vazamentos gerais de dados | Atividade de política de vazamento de dados que cria um alerta de alta gravidade | Política DLP configurada para alertas de alta gravidade |
| Vazamentos de dados por usuários prioritários | Atividade de política de vazamento de dados que cria um alerta de alta gravidade | Política DLP configurada para alertas de alta gravidade <br><br> Grupos de usuários de prioridade configurados nas configurações de risco interno |
| Vazamentos de dados por usuários não coerentes | Melhoria de desempenho, desempenho ruim ou indicadores de alteração no nível do trabalho do conector de RH | Conector de RH do Microsoft 365 configurado para indicadores de inconsiência |
| Violações gerais da política de segurança | 100.000 por usuário | Assinatura ativa do Microsoft Defender para Ponto de Extremidade <br><br> Integração do Microsoft Defender for Endpoint com o centro de conformidade do Microsoft 365 configurado |
| Violações da política de segurança por parte dos usuários | Indicadores de data de cancelamento ou de rescisão do conector de RH | Conector de RH do Microsoft 365 configurado para indicadores de data de término e de demissão <br><br> Assinatura ativa do Microsoft Defender para Ponto de Extremidade <br><br> Integração do Microsoft Defender for Endpoint com o centro de conformidade do Microsoft 365 configurado |
| Violações da política de segurança por usuários prioritários | Fraude de controles de segurança ou software indesejado detectado pelo Microsoft Defender para Ponto de Extremidade | Assinatura ativa do Microsoft Defender para Ponto de Extremidade <br><br> Integração do Microsoft Defender for Endpoint com o centro de conformidade do Microsoft 365 configurado <br><br> Grupos de usuários de prioridade configurados nas configurações de risco interno |
| Violações da política de segurança por usuário não coerente | Melhoria de desempenho, desempenho ruim ou indicadores de alteração no nível do trabalho do conector de RH | Conector de RH do Microsoft 365 configurado para indicadores de inconsiência <br><br> Assinatura ativa do Microsoft Defender para Ponto de Extremidade <br><br> Integração do Microsoft Defender for Endpoint com o centro de conformidade do Microsoft 365 configurado |

## <a name="prioritize-content-in-policies"></a>Priorizar conteúdo em políticas

As políticas de gerenciamento de riscos insider suportam a especificação de uma prioridade mais alta para o conteúdo, dependendo de onde ele está armazenado ou de como ele é classificado. Especificar o conteúdo como prioridade aumenta a pontuação de risco para qualquer atividade associada, o que, por sua vez, aumenta a chance de gerar um alerta de alta gravidade. No entanto, algumas atividades não gerarão um alerta, a menos que o conteúdo relacionado contenha tipos de informações confidenciais internas ou personalizadas ou tenha sido especificado como prioridade na política.

Por exemplo, sua organização tem um site dedicado do SharePoint para um projeto altamente confidencial. Vazamentos de dados para informações neste site do SharePoint poderiam comprometer o projeto e teriam um impacto significativo em seu sucesso. Ao priorizar esse site do SharePoint em uma política de vazamento de dados, as pontuações de risco para atividades de qualificação são aumentadas automaticamente. Essa priorização aumenta a probabilidade de que essas atividades gerem um alerta de risco interno e eleva o nível de gravidade do alerta.

Ao criar uma política de gerenciamento de riscos interno no assistente de política, você pode escolher entre as seguintes prioridades:

- **Sites do SharePoint:** qualquer atividade associada a todos os tipos de arquivo em sites definidos do SharePoint recebe uma pontuação de risco mais alta. 
- **Tipos de informações confidenciais:** qualquer atividade associada ao conteúdo que contenha [tipos](sensitive-information-type-entity-definitions.md) de informações confidenciais recebe uma pontuação de risco maior.
- **Rótulos de sensibilidade:** qualquer atividade associada [](sensitivity-labels.md) ao conteúdo que tenha rótulos de sensibilidade específicos aplicados recebe uma pontuação de risco mais alta.

## <a name="create-a-new-policy"></a>Criar uma nova política

Para criar uma nova política de gerenciamento de riscos **insider,** você usará o assistente de política na solução de gerenciamento de riscos do Insider no centro de conformidade do Microsoft 365.

Conclua as seguintes etapas para criar uma nova política:

1. No centro [de conformidade do Microsoft 365,](https://compliance.microsoft.com)vá para o gerenciamento de riscos do **Insider** e selecione a **guia** Políticas.
2. Selecione **Criar política para** abrir o assistente de política
3. Na página **Nova política de risco interno,** preencha os seguintes campos:
    - **Nome (obrigatório)**: insira um nome amigável para a política.
    - **Descrição (opcional)**: insira uma descrição para a política.
    - **Choose policy template (required)**: Select one of the [policy templates](insider-risk-management-policies.md#policy-templates) to define the types of risk indicators are monitored by the policy.

    >[!IMPORTANT]
    >A maioria dos modelos de política tem pré-requisitos que devem ser configurados para que a política gere alertas relevantes. Se você ainda não configurou os pré-requisitos de política aplicável, consulte Começar a trabalhar com [o gerenciamento de riscos insider.](insider-risk-management-configure.md#step-3-configure-prerequisites-for-templates)

4. Selecione **Próximo** para continuar.
5. Na página **Usuários,** selecione Adicionar  usuário ou grupo ou Escolher Grupos de Usuários de Prioridade para definir quais usuários ou grupos de usuários prioritários serão incluídos na política, dependendo do modelo de política selecionado.  Marque **a caixa de seleção Todos** os usuários e grupos habilitados para email, se aplicável (se você não tiver selecionado um modelo com prioridade baseada no usuário). Selecione **Próximo** para continuar.
6. Na página **Especificar qual conteúdo priorizar (opcional),** você pode atribuir as fontes para priorizar pontuações de risco maiores. No entanto, algumas atividades não gerarão um alerta, a menos que o conteúdo relacionado contenha tipos de informações confidenciais integrados ou personalizados ou tenha sido especificado como prioridade nesta página:
    - **Sites do SharePoint:** selecione **Adicionar site do SharePoint** e selecione as organizações do SharePoint que você deseja priorizar. Por exemplo, *"group1@contoso.sharepoint.com/sites/group1".*
    - **Tipo de informação confidenciais:** selecione **Adicionar tipo de informação sensível** e selecione os tipos de sensibilidade que você deseja priorizar. Por exemplo, *"Número de Conta Bancária dos EUA"* e *"Número de Cartão de Crédito"*.
    - **Rótulos de sensibilidade:** **selecione Adicionar rótulo de** sensibilidade e selecione os rótulos que você deseja priorizar. Por exemplo, *"Confidencial"* e *"Segredo"*.
7. Selecione **Próximo** para continuar.
8. Na página **Selecionar indicadores de** política, você verá os indicadores definidos como disponíveis na página Indicadores de configurações de risco do [](insider-risk-management-settings.md#indicators) **Insider.**  >   Se você selecionou um modelo de vazamento *de* dados no início do assistente, você deve selecionar uma política DLP na lista de lista suspenso de política **de DLP** para habilitar os indicadores de disparo para a política. Selecione os indicadores que você deseja aplicar à política. Se você preferir não usar as configurações de limite de política padrão para esses indicadores, desabilite os limites padrão de uso **recomendados** pela Microsoft e insira os valores de limite para cada indicador selecionado. Se você tiver selecionado pelo menos um indicador *do Office* ou do *Dispositivo,* selecione as pontuações de risco **conforme** apropriado. Os indicadores de pontuação de risco só são aplicáveis aos indicadores selecionados.

    >[!IMPORTANT]
    >Se os indicadores nesta página não puderem ser selecionados, você precisará selecionar os indicadores que deseja habilitar para todas as políticas na página Indicadores de Política de Configurações de gerenciamento de riscos do **Insider.**  >    >  

9. Selecione **Próximo** para continuar.
10. Na página **Policy timeframes,** você [](insider-risk-management-settings.md#policy-timeframes) verá as condições da janela de ativação para a política que, na página De períodos de política de configurações de risco do **Insider.**  >  
11. Selecione **Próximo** para continuar.
12. Na página **Revisão,** revise as configurações escolhidas para a política. Selecione **Editar** para alterar qualquer um dos valores de política ou **selecione Enviar** para criar e ativar a política.

## <a name="update-a-policy"></a>Atualizar uma política

Para atualizar uma política existente de gerenciamento de riscos insider, você usará o assistente de política na solução de gerenciamento de riscos do **Insider** no centro de conformidade do Microsoft 365.

Conclua as seguintes etapas para gerenciar uma política existente:

1. No centro [de conformidade do Microsoft 365,](https://compliance.microsoft.com)vá para o gerenciamento de riscos do **Insider** e selecione a **guia** Políticas.
2. No painel de políticas, selecione a política que você deseja gerenciar.
3. Na página de detalhes da política, selecione **Editar política**
4. No assistente de política, você não pode editar os seguintes campos:
    - **Nome**: o nome amigável da política
    - **Escolha o modelo de** política: o modelo usado para definir os tipos de indicadores de risco monitorados pela política.
5. Insira uma nova descrição para a política no campo **Descrição.** 
6. Selecione **Próximo** para continuar.
7. Na página **Usuários,** selecione Adicionar  usuário ou grupo ou Escolher grupos de usuários de Prioridade para definir quais usuários ou grupos de usuários prioritários serão incluídos na política, dependendo do modelo de política selecionado.  Marque **a caixa de seleção Todos** os usuários e grupos habilitados para email, se aplicável (se você não tiver selecionado um modelo com prioridade baseada no usuário). Selecione **Próximo** para continuar.
8. Na página **Especificar qual conteúdo priorizar (opcional),** você pode atribuir as fontes para priorizar pontuações de risco maiores. No entanto, algumas atividades não gerarão um alerta, a menos que o conteúdo relacionado contenha tipos de informações confidenciais integrados ou personalizados ou tenha sido especificado como prioridade nesta página:
    - **Sites do SharePoint:** selecione **Adicionar site do SharePoint** e selecione as organizações do SharePoint que você deseja priorizar. Por exemplo, *"group1@contoso.sharepoint.com/sites/group1".*
    - **Tipo de informação confidenciais:** selecione **Adicionar tipo de informação sensível** e selecione os tipos de sensibilidade que você deseja priorizar. Por exemplo, *"Número de Conta Bancária dos EUA"* e *"Número de Cartão de Crédito"*.
    - **Rótulos de sensibilidade:** **selecione Adicionar rótulo de** sensibilidade e selecione os rótulos que você deseja priorizar. Por exemplo, *"Confidencial"* e *"Segredo"*.
9. Selecione **Próximo** para continuar.
10. Na página **Selecionar indicadores de** política, você verá os indicadores definidos como disponíveis na página Indicadores de configurações de risco do [](insider-risk-management-settings.md#indicators) **Insider.**  >   Se você selecionou um modelo de vazamento *de* dados no início do assistente, você deve selecionar uma política de DLP na lista suspenso de política **de DLP** para habilitar os indicadores de disparo para a política. Selecione os indicadores que você deseja aplicar à política. Se você preferir não usar as configurações de limite de política padrão para esses indicadores, desabilite os limites padrão de uso **recomendados** pela Microsoft e insira os valores de limite para cada indicador selecionado. Se você tiver selecionado pelo menos um indicador *do Office* ou *do Dispositivo,* selecione as pontuações **de** risco conforme apropriado. Os indicadores de pontuação de risco só são aplicáveis aos indicadores selecionados.

    >[!IMPORTANT]
    >Se os indicadores nesta página não puderem ser selecionados, você precisará selecionar os indicadores que deseja habilitar para todas as políticas na página Indicadores de Política de Configurações de gerenciamento de riscos do **Insider.**  >    >  

11. Selecione **Próximo** para continuar.
12. Na página **Policy timeframes,** você [](insider-risk-management-settings.md#policy-timeframes) verá as condições da janela de ativação para a política que, na página De períodos de política de configurações de risco do **Insider.**  >  
13. Selecione **Próximo** para continuar.
14. Na página **Revisão,** revise as configurações que você atualizou para a política. Selecione **Editar** para alterar qualquer um dos valores de política ou **selecione Enviar** para atualizar e ativar a política.

## <a name="delete-a-policy"></a>Excluir uma política

>[!NOTE]
>Excluir uma política não exclui alertas ativos ou arquivados gerados da política.

Para excluir uma política existente de gerenciamento de riscos insider, conclua as seguintes etapas:

1. No centro [de conformidade do Microsoft 365,](https://compliance.microsoft.com)vá para o gerenciamento de riscos do **Insider** e selecione a **guia** Políticas.
2. No painel de políticas, selecione a política que você deseja excluir.
3. Selecione **Excluir** na barra de ferramentas do painel.
4. Na caixa **de diálogo** Excluir, selecione **Sim** para excluir a política ou selecione **Cancelar** para fechar a caixa de diálogo.
