---
title: Políticas de gerenciamento de riscos insider
description: Saiba mais sobre políticas de gerenciamento de riscos internas no Microsoft 365
keywords: Microsoft 365, gerenciamento de risco interno, gerenciamento de riscos, conformidade
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
ms.openlocfilehash: 17ac5506b6445854b1d9fe8ba6b5f5356f6a3827
ms.sourcegitcommit: 8b1bd7ca8cd81e4270f0c1e06d2b6ca81804a6aa
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/15/2021
ms.locfileid: "50819815"
---
# <a name="insider-risk-management-policies"></a>Políticas de gerenciamento de riscos insider

As políticas de gerenciamento de riscos internas determinam quais usuários estão no escopo e quais tipos de indicadores de risco são configurados para alertas. Você pode criar rapidamente uma política que se aplique a todos os usuários em sua organização ou definir usuários individuais ou grupos para gerenciamento em uma política. As políticas suportam prioridades de conteúdo para focalizar as condições de política em vários ou específicos do Microsoft Teams, sites do SharePoint, tipos de sensibilidade de dados e rótulos de dados. Usando modelos, você pode selecionar indicadores de risco específicos e personalizar limites de eventos para indicadores de política, personalização efetiva de pontuações de risco e nível e frequência de alertas. Além disso, os impulsionadores de pontuação de risco e as detecções de anomalias ajudam a identificar a atividade do usuário de maior importância ou mais incomum. As janelas de política permitem definir o período de tempo para aplicar a política às atividades de alerta e são usadas para determinar a duração da política uma vez ativada.

## <a name="policy-dashboard"></a>Painel de política

O **painel política** permite que você veja rapidamente as políticas em sua organização, a saúde da política, adicionar manualmente usuários a políticas e exibir o status dos alertas associados a cada política.

- **Nome da** política : o nome atribuído à política no assistente de política.
- **Status**: o status de saúde de cada política. Exibe o número de avisos e recomendações de política ou um status de *Healthy* para políticas sem problemas.  Você pode clicar na política para ver os detalhes do status de saúde para quaisquer avisos ou recomendações.
- **Alertas ativos**: O número de alertas ativos para cada política.
- **Alertas confirmados**: O número total de alertas que resultaram em casos da política nos últimos 365 dias.
- **Ações tomadas em alertas**: O número total de alertas que foram confirmados ou ignorados nos últimos 365 dias.
- **Eficácia do alerta de** política : a porcentagem determinada pelo total de alertas confirmados divididos pelo total de ações realizadas em alertas (que é a soma de alertas confirmados ou ignorados no último ano).

![Painel de política de gerenciamento de riscos do Insider](../media/insider-risk-policy-dashboard.png)

## <a name="policy-recommendations-from-analytics-preview"></a>Recomendações de política da análise (visualização)

A análise de risco insider permite que você conduza uma avaliação de possíveis riscos insider em sua organização sem configurar nenhuma política de risco interna. Essa avaliação pode ajudar sua organização a identificar áreas potenciais de maior risco de usuário e ajudar a determinar o tipo e o escopo das políticas de gerenciamento de riscos internas que você pode considerar configurar.

Para saber mais sobre análises de risco interno e recomendações de política, consulte [Insider risk management settings: Analytics (preview)](insider-risk-management-settings.md#analytics-preview).

## <a name="policy-templates"></a>Modelos de política

Modelos de gerenciamento de riscos insider são condições de política pré-definidas que definem os tipos de indicadores de risco e o modelo de pontuação de risco usado pela política. Cada política deve ter um modelo atribuído ao assistente de criação de política antes da criação da política. O gerenciamento de riscos insider dá suporte a até cinco políticas para cada modelo de política. Ao criar uma nova política de risco interno com o assistente de política, você escolherá entre um dos seguintes modelos de política:

### <a name="data-theft-by-departing-users"></a>Roubo de dados ao separar usuários

Quando os usuários saem da sua organização, há indicadores de risco específicos normalmente associados ao roubo de dados por parte dos usuários. Este modelo de política usa indicadores de exfiltração para pontuação de risco e se concentra na detecção e alertas nessa área de risco. O roubo de dados para usuários de saída pode incluir o download de arquivos do SharePoint Online, a impressão de arquivos e a cópia de dados para serviços de armazenamento e mensagens de nuvem pessoais perto de suas datas de encerramento e de demissão de emprego. Ao usar o conector de RH do Microsoft 365 ou a opção de monitorar automaticamente a exclusão de conta de usuário no Azure Active Directory para sua organização, esse modelo começa a marcar para indicadores de risco relacionados a essas atividades e como eles se correlacionam com o status de emprego do usuário.

>[!IMPORTANT]
>Ao usar esse modelo, você pode configurar um conector de RH do Microsoft 365 para importar periodicamente informações de data de encerramento e de demissão para usuários em sua organização. Consulte o [artigo Importar dados com](import-hr-data.md) o conector de RH para obter orientações passo a passo para configurar o conector de RH do Microsoft 365 para sua organização. Se você optar por não usar o conector de RH, deverá selecionar a conta de usuário excluída da opção do Azure AD ao configurar eventos de gatilho no assistente de política.

### <a name="general-data-leaks"></a>Vazamentos gerais de dados

Proteger dados e evitar vazamentos de dados é um desafio constante para a maioria das organizações, especialmente com o rápido aumento de novos dados criados por usuários, dispositivos e serviços. Os usuários têm a capacitação para criar, armazenar e compartilhar informações entre serviços e dispositivos que fazem com que o gerenciamento de vazamentos de dados seja cada vez mais complexo e difícil. Os vazamentos de dados podem incluir o compartilhamento acidental de informações fora da sua organização ou roubo de dados com intenção mal-intencionada. Com uma política de Prevenção contra Perda de Dados (DLP) atribuída ou o evento de acionamento interno, este modelo começa a marcar detecções em tempo real de downloads de dados suspeitos do SharePoint Online, compartilhamento de arquivos e pastas, impressão de arquivos e cópia de dados para mensagens de nuvem pessoais e serviços de armazenamento.

Ao usar um *modelo de vazamentos* de dados, você pode atribuir uma política de DLP para disparar indicadores na política de risco interno para alertas de alta gravidade em sua organização. Sempre que um alerta de alta gravidade é gerado por uma regra de política DLP é adicionado ao log de auditoria do Office 365, as políticas de risco interna criadas com esse modelo examinam automaticamente o alerta DLP de alta gravidade. Se o alerta contiver um usuário no escopo definido na política de risco interna, o alerta será processado pela política de risco interna como um novo alerta e atribuído a uma gravidade de risco interno e pontuação de risco. Essa política permite avaliar esse alerta no contexto com outras atividades incluídas no caso. Se você não escolher uma política de DLP, deverá selecionar o evento de disparo integrado.

#### <a name="data-leaks-policy-guidelines"></a>Diretrizes de política de vazamento de dados

Ao criar ou modificar políticas de DLP para uso com políticas de gerenciamento de riscos insider, considere as seguintes diretrizes:

- Priorize eventos de exfiltração  de dados e seja seletivo ao atribuir configurações de relatórios de incidentes a *High* ao configurar regras em suas políticas de DLP. Por exemplo, enviar documentos confidenciais para um concorrente conhecido deve ser um *evento de* exfiltração de alto nível de alerta. Atribuir o nível  Alto nas  configurações de relatórios de incidentes em outras regras de política de DLP pode aumentar o ruído no fluxo de trabalho de alerta de gerenciamento de risco interno e tornar mais difícil para seus investigadores de dados e analistas avaliar corretamente esses alertas. Por exemplo, atribuir níveis de *alerta* alto para acessar atividades de negação em políticas de DLP torna mais desafiador avaliar o comportamento e as atividades do usuário realmente arriscados.
- Certifique-se de entender e configurar corretamente os usuários no escopo nas políticas de gerenciamento de riscos de DLP e insider. Somente usuários definidos como no escopo para políticas de gerenciamento de riscos insider usando o modelo **de vazamentos** de dados terão alertas de política DLP de alta gravidade processados. Além disso, somente os usuários definidos como no escopo em uma regra para um alerta DLP de alta gravidade serão examinados pela política de gerenciamento de riscos insider para consideração. É importante que você não configure usuários no escopo sem saber em suas políticas de risco de DLP e insider de maneira conflitante.

     Por exemplo, se suas regras de política de DLP são escopo apenas para usuários na Equipe de Vendas e a política de risco insider criada a partir do modelo de **vazamentos** de dados definiu todos os usuários como no escopo, a política de risco insider só processará alertas de DLP de alta gravidade para os usuários na Equipe de Vendas. A política de risco interno não receberá alertas de DLP de alta prioridade para os usuários processarem que não estão definidos nas regras de DLP neste exemplo. Por outro lado, se sua política de gerenciamento de riscos internas criada a partir de modelos de **vazamentos** de dados tiver escopo apenas para usuários na Equipe de Vendas e a política DLP atribuída for escopo para todos os usuários, a política de risco interno processará apenas alertas de DLP de alta gravidade para membros da Equipe de Vendas. A política de gerenciamento de risco interno ignorará alertas DLP de alta gravidade para todos os usuários que não estão na Equipe de Vendas.

- Certifique-se **de que a** configuração da regra de relatórios de incidentes na política de DLP usada para esse modelo de gerenciamento de risco interno está configurada para *alertas* de nível de alta gravidade. O *nível* de alta gravidade são os eventos disparados e os alertas de gerenciamento  de riscos insider não serão gerados a partir de regras em políticas de DLP com o campo Relatórios de incidentes definido em *Baixo* ou *Médio.*

    ![Configuração de alerta de política de DLP](../media/insider-risk-DLP-policy-high-severity.png)

     >[!NOTE]
     >Ao criar uma nova política de DLP usando os modelos integrados, você precisará selecionar a  opção Criar ou  personalizar regras **DLP** avançadas para configurar a configuração De relatórios de incidentes para o nível de alta gravidade.

Cada política de gerenciamento de riscos internas criada a partir do modelo **De vazamentos** de dados só pode ter uma política DLP atribuída. Considere a criação de uma política de DLP dedicada que combine as diferentes atividades que você deseja detectar e agir como gatilho de eventos para políticas de risco internas que usam o modelo **De vazamentos de** dados.

Consulte o [artigo Criar, testar e ajustar uma](create-test-tune-dlp-policy.md) política DLP para obter orientações passo a passo para configurar políticas de DLP para sua organização.

### <a name="data-leaks-by-priority-users-preview"></a>Vazamentos de dados por usuários prioritários (visualização)

Proteger dados e evitar vazamentos de dados para usuários em sua organização pode depender de sua posição, nível de acesso a informações confidenciais ou histórico de riscos. Os vazamentos de dados podem incluir o compartilhamento acidental de informações altamente confidenciais fora da sua organização ou roubo de dados com intenção mal-intencionada. Com uma política de Prevenção contra Perda de Dados (DLP) atribuída, este modelo começa a marcar detecções em tempo real de atividades suspeitas e resulta em uma maior probabilidade de alertas e alertas de risco interno com níveis de gravidade mais altos. Os usuários prioritários são definidos [em grupos de usuários prioritários](insider-risk-management-settings.md#priority-user-groups-preview) configurados na área de configurações de gerenciamento de riscos insider.

Assim como no modelo Geral de **vazamentos** de dados, você deve atribuir uma política de DLP para disparar indicadores na política de risco interno para alertas de alta gravidade em sua organização. Siga as diretrizes de política de vazamentos de dados acima ao criar uma política usando este modelo. Além disso, você precisará atribuir grupos de usuários prioritários criados no gerenciamento de riscos **do Insider** Configurações Grupos de usuários  >  **prioritários**  >   à política.

### <a name="data-leaks-by-disgruntled-users-preview"></a>Vazamentos de dados por usuários insatisfeitos (visualização)

Quando os usuários experimentam stressores de emprego, eles podem ficar insatisfeitos, o que pode aumentar as chances de atividade de risco interno. Este modelo inicia a pontuação da atividade do usuário quando um indicador associado à incongruência é identificado. Exemplos incluem notificações de melhoria de desempenho, avaliações de desempenho ruins ou alterações no status do nível de trabalho. Os vazamentos de dados para usuários insatisfeitos podem incluir o download de arquivos do SharePoint Online e a cópia de dados para mensagens de nuvem pessoais e serviços de armazenamento próximos a eventos de estresse de emprego.

Ao usar esse modelo, você também deve configurar um conector de RH do Microsoft 365 para importar periodicamente notificações de melhoria de desempenho, status de revisão de desempenho ruim ou informações de alteração de nível de trabalho para usuários em sua organização. Consulte o [artigo Importar dados com](import-hr-data.md) o conector de RH para obter orientações passo a passo para configurar o conector de RH do Microsoft 365 para sua organização.

### <a name="general-security-policy-violations-preview"></a>Violações gerais da política de segurança (visualização)

Em muitas organizações, os usuários têm permissão para instalar software em seus dispositivos ou modificar as configurações do dispositivo para ajudar com suas tarefas. Inadvertidamente ou com intenção mal-intencionada, os usuários podem instalar malware ou desabilitar recursos de segurança importantes que ajudam a proteger informações em seus dispositivos ou em seus recursos de rede. Este modelo de política usa alertas de segurança do Microsoft Defender para o Ponto de Extremidade para começar a marcar essas atividades e a detecção de foco e alertas para essa área de risco. Use este modelo para fornecer informações sobre violações de política de segurança em cenários em que os usuários podem ter um histórico de violações de política de segurança que podem ser um indicador de risco interno.

Você precisará ter o Microsoft Defender para Ponto de Extremidade configurado em sua organização e habilitar o Defender for Endpoint para integração de gerenciamento de riscos insider no Defender Security Center para importar alertas de violação de segurança. Para obter mais informações sobre como configurar o Defender para o Ponto de Extremidade para integração de gerenciamento de riscos insider, consulte [Configure advanced features in Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center).

### <a name="security-policy-violations-by-departing-users-preview"></a>Violações de política de segurança ao separar usuários (visualização)

A saída dos usuários, seja em termos positivos ou negativos, pode ser um risco maior para violações de política de segurança. Para ajudar a proteger contra violações de segurança inadvertida ou mal-intencionadas para usuários de saída, este modelo de política usa alertas do Defender para Ponto de Extremidade para fornecer informações sobre atividades relacionadas à segurança. Essas atividades incluem o usuário instalando malware ou outros aplicativos potencialmente prejudiciais e desabilitando recursos de segurança em seus dispositivos. Ao usar o conector de RH do [Microsoft 365](import-hr-data.md) ou a opção de monitorar automaticamente a exclusão de conta de usuário no Azure Active Directory para sua organização, esse modelo começa a marcar para indicadores de risco relacionados a essas atividades de segurança e como eles se correlacionam com o status de emprego do usuário.

Você precisará ter o Microsoft Defender para Ponto de Extremidade configurado em sua organização e habilitar o Defender for Endpoint para integração de gerenciamento de riscos insider no Defender Security Center para importar alertas de violação de segurança. Para obter mais informações sobre como configurar o Defender para o Ponto de Extremidade para integração de gerenciamento de riscos insider, consulte [Configure advanced features in Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center).

### <a name="security-policy-violations-by-priority-users-preview"></a>Violações de política de segurança por usuários prioritários (visualização)

A proteção contra violações de segurança para usuários em sua organização pode depender de sua posição, nível de acesso a informações confidenciais ou histórico de riscos. Como as violações de segurança por usuários prioritários podem ter um impacto significativo nas áreas críticas da sua organização, esse modelo de política começa a pontuar nesses indicadores e usa o Microsoft Defender para alertas de ponto de extremidade para fornecer informações sobre atividades relacionadas à segurança para esses usuários. Essas atividades podem incluir os usuários prioritários instalando malware ou outros aplicativos potencialmente prejudiciais e desabilitando recursos de segurança em seus dispositivos. Os usuários prioritários são definidos em grupos de usuários prioritários configurados na área de configurações de gerenciamento de riscos insider.

Você precisará ter o Microsoft Defender para Ponto de Extremidade configurado em sua organização e habilitar o Defender for Endpoint para integração de gerenciamento de riscos insider no Defender Security Center para importar alertas de violação de segurança. Para obter mais informações sobre como configurar o Defender para o Ponto de Extremidade para integração de gerenciamento de riscos insider, consulte [Configure advanced features in Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center). Além disso, você precisará atribuir grupos de usuários prioritários criados no gerenciamento de riscos **do Insider** Configurações Grupos de usuários  >  **prioritários**  >   à política.

### <a name="security-policy-violations-by-disgruntled-users-preview"></a>Violações de política de segurança por usuários insatisfeitos (visualização)

Os usuários que experimentam estresses de emprego podem estar em um risco maior para violações de política de segurança inadvertida ou mal-intencionada. Esses stressores podem incluir o usuário que está sendo colocado em um plano de melhoria de desempenho, status de revisão de desempenho ruim ou ser rebaixado de sua posição atual. Este modelo de política inicia a pontuação de risco com base nesses indicadores e atividades associadas a esses eventos para esses usuários.

Ao usar esse modelo, você também deve configurar um conector de RH do Microsoft 365 para importar periodicamente notificações de melhoria de desempenho, status de revisão de desempenho ruim ou informações de alteração de nível de trabalho para usuários em sua organização. Consulte o [artigo Importar dados com](import-hr-data.md) o conector de RH para obter orientações passo a passo para configurar o conector de RH do Microsoft 365 para sua organização.

Você também precisará ter o Microsoft Defender para Ponto de Extremidade configurado em sua organização e habilitar o Defender for Endpoint para integração de gerenciamento de riscos insider no Defender Security Center para importar alertas de violação de segurança. Para obter mais informações sobre como configurar o Defender para o Ponto de Extremidade para integração de gerenciamento de riscos insider, consulte [Configure advanced features in Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center).

### <a name="policy-template-prerequisites-and-triggering-events"></a>Pré-requisitos do modelo de política e eventos de gatilho

Dependendo do modelo escolhido para uma política de gerenciamento de riscos insider, os eventos disparados e os pré-requisitos de política variam. Acionamento de eventos são pré-requisitos que determinam se um usuário está ativo para uma política de gerenciamento de riscos insider. Se um usuário for adicionado a uma política de gerenciamento de riscos interna, mas não tiver um evento de gatilho, a atividade do usuário não será avaliada pela política, a menos que seja adicionada manualmente no painel Usuários. Os pré-requisitos de política são itens necessários para que a política receba os sinais ou as atividades necessárias para avaliar o risco.

A tabela a seguir lista os eventos disparados e os pré-requisitos para políticas criadas a partir de cada modelo de política de gerenciamento de riscos insider:

| **Modelo de política** | **Disparando eventos para políticas** | **Pré-requisitos** |
| :------------------ | :--------------------------------- | :---------------- |
| Roubo de dados ao separar usuários | Indicador de data de demissão ou término do conector de RH | (opcional) Conector de RH do Microsoft 365 configurado para indicadores de data de encerramento e de demissão ou integração do Azure Active Directory habilitada |
| Vazamentos gerais de dados | Atividade de política de vazamento de dados que cria um alerta de alta gravidade | (opcional) Política de DLP configurada para alertas de alta gravidade ou evento de disparo de exfiltração de dados interna |
| Vazamentos de dados por usuários prioritários | Atividade de política de vazamento de dados que cria um *alerta de alta gravidade* ou gatilhos de evento de exfiltração interna | (opcional) Política de DLP configurada para alertas de alta gravidade <br><br> Grupos de usuários prioritários configurados em configurações de risco interno |
| Vazamentos de dados por usuários insatisfeitos | Melhoria de desempenho, desempenho ruim ou indicadores de alteração de nível de trabalho do conector de RH | Conector de RH do Microsoft 365 configurado para indicadores de incongruência |
| Violações gerais da política de segurança | Evasão defensiva de controles de segurança ou software indesejado detectado pelo Microsoft Defender para Ponto de Extremidade | Assinatura ativa do Microsoft Defender para Ponto de Extremidade <br><br> Integração do Microsoft Defender para Ponto de Extremidade com o centro de conformidade do Microsoft 365 configurado |
| Violações de política de segurança ao separar usuários | Indicadores de data de demissão ou término do conector de RH ou exclusão da conta do Azure Active Directory | (opcional) Conector de RH do Microsoft 365 configurado para indicadores de data de encerramento e de demissão <br><br> Assinatura ativa do Microsoft Defender para Ponto de Extremidade <br><br> Integração do Microsoft Defender para Ponto de Extremidade com o centro de conformidade do Microsoft 365 configurado |
| Violações de política de segurança por usuários prioritários | Evasão defensiva de controles de segurança ou software indesejado detectado pelo Microsoft Defender para Ponto de Extremidade | Assinatura ativa do Microsoft Defender para Ponto de Extremidade <br><br> Integração do Microsoft Defender para Ponto de Extremidade com o centro de conformidade do Microsoft 365 configurado <br><br> Grupos de usuários prioritários configurados em configurações de risco interno |
| Violações de política de segurança por usuário insatisfeito | Melhoria de desempenho, desempenho ruim ou indicadores de alteração de nível de trabalho do conector de RH | Conector de RH do Microsoft 365 configurado para indicadores de incongruência <br><br> Assinatura ativa do Microsoft Defender para Ponto de Extremidade <br><br> Integração do Microsoft Defender para Ponto de Extremidade com o centro de conformidade do Microsoft 365 configurado |

## <a name="prioritize-content-in-policies"></a>Priorizar conteúdo em políticas

As políticas de gerenciamento de riscos insider suportam a especificação de uma prioridade maior para o conteúdo, dependendo de onde ele está armazenado ou de como ele é classificado. A especificação de conteúdo como prioridade aumenta a pontuação de risco para qualquer atividade associada, o que aumenta a chance de gerar um alerta de alta gravidade. No entanto, algumas atividades não gerarão um alerta, a menos que o conteúdo relacionado contenha tipos de informações confidenciais internas ou personalizadas ou tenha sido especificado como prioridade na política.

Por exemplo, sua organização tem um site dedicado do SharePoint para um projeto altamente confidencial. Vazamentos de dados para informações neste site do SharePoint podem comprometer o projeto e teriam um impacto significativo em seu sucesso. Ao priorizar esse site do SharePoint em uma política de vazamentos de dados, as pontuações de risco para atividades de qualificação são aumentadas automaticamente. Essa priorização aumenta a probabilidade de que essas atividades gerem um alerta de risco interno e eleva o nível de gravidade do alerta.

Ao criar uma política de gerenciamento de riscos internas no assistente de política, você pode escolher entre as seguintes prioridades:

- **Sites do SharePoint**: qualquer atividade associada a todos os tipos de arquivo em sites definidos do SharePoint recebe uma pontuação de risco mais alta. 
- **Tipos de informações confidenciais**: qualquer [](sensitive-information-type-entity-definitions.md) atividade associada ao conteúdo que contenha tipos de informações confidenciais recebe uma pontuação de risco maior.
- **Rótulos de sensibilidade**: qualquer atividade [](sensitivity-labels.md) associada ao conteúdo que tenha rótulos de sensibilidade específicos aplicados recebe uma pontuação de risco maior.

## <a name="sequence-detection-preview"></a>Detecção de sequência (visualização)

Atividades arriscadas podem não ocorrer como eventos isolados. Esses riscos são frequentemente parte de uma sequência maior de eventos. Uma sequência é um grupo de duas ou mais atividades de usuário executadas uma após a outra que pode sugerir um risco elevado. Identificar essas atividades relacionadas é uma parte importante da avaliação do risco geral. Quando a detecção de sequência é habilitada para políticas de roubo  de dados ou vazamentos de dados, as percepções das atividades de informações de sequência são exibidas na guia Atividade do usuário dentro de um caso de gerenciamento de risco interno. Os modelos de política a seguir suportam a detecção de sequência:

- Roubo de dados ao separar usuários
- Vazamentos gerais de dados
- Vazamentos de dados por usuários prioritários
- Vazamentos de dados por usuários insatisfeitos

Essas políticas de gerenciamento de riscos internas podem usar indicadores específicos e a ordem que ocorrem para detectar cada etapa em uma sequência de risco. Os nomes de arquivo são usados ao mapear atividades em uma sequência. Esses riscos são organizados em quatro categorias principais de atividade:

- **Coleção**: Essas categorias sinalizam o foco nas atividades de download pelos usuários da política no escopo. Um exemplo de atividade nesta categoria seria baixar arquivos de sites do SharePoint.
- **Exfiltração**: Essas categorias sinalizam o foco em atividades de compartilhamento ou extração para fontes internas e externas por usuários de política no escopo. Um exemplo de atividade nessa categoria seria o envio de emails com anexos de sua organização para destinatários externos.
- **Ofuscação**: Essas categorias sinalizam o foco no mascaramento de atividades arriscadas pelos usuários da política no escopo. Um exemplo de atividade nesta categoria seria renomear arquivos em um dispositivo.
- **Limpeza : essas** categorias sinalizam o foco nas atividades de exclusão por usuários de política no escopo. Um exemplo de atividade nessa categoria seria excluir arquivos de um dispositivo.

>[!NOTE]
>A detecção de sequência usa indicadores habilitados nas configurações globais para o gerenciamento de risco interno e indicadores selecionados em uma política. Se indicadores apropriados não forem selecionados, a detecção de sequência não funcionará.

Você pode personalizar as configurações de limite individuais para cada tipo de detecção de sequência quando configurado na política. Essas configurações de limite ajustam alertas com base no volume de arquivos associados à sequência.

Para saber mais sobre o gerenciamento de detecção de sequência no **exibição Atividade** do usuário, consulte Casos de gerenciamento de riscos do [Insider: Atividade do usuário](insider-risk-management-cases.md#user-activity).

## <a name="cumulative-exfiltration-detection-preview"></a>Detecção cumulativa de exfiltração (visualização)

Os indicadores de risco insider ajudam a identificar níveis incomuns de atividades de risco quando avaliados diariamente para usuários que estão no escopo de políticas de risco internas. A detecção de exfiltração cumulativa usa modelos de aprendizado de máquina para ajudá-lo a identificar quando as atividades de exfiltração do usuário excedem as médias organizacionais quando medidas ao longo do tempo e em vários tipos de atividade de exfiltração. Os analistas e investigadores de gerenciamento de riscos do Insider podem usar informações de detecção cumulativa de exfiltração para ajudar a identificar atividades de exfiltração que normalmente não geram alertas, mas estão acima do que é comum para sua organização. Alguns exemplos podem estar saindo dos usuários lentamente exfiltrando dados em um intervalo de dias ou quando os usuários compartilham dados repetidamente em vários canais mais do que o normal para o compartilhamento de dados para sua organização.

A detecção cumulativa de exfiltração é habilitada por padrão ao usar os seguintes modelos de política:

- Roubo de dados ao separar usuários
- Vazamentos gerais de dados
- Vazamentos de dados por usuários prioritários
- Vazamentos de dados por usuários insatisfeitos

>[!NOTE]
>A detecção de exfiltração cumulativa usa indicadores de exfiltração habilitados nas configurações globais para o gerenciamento de riscos insider e indicadores de exfiltração selecionados em uma política. Dessa forma, a detecção cumulativa de exfiltração é avaliada apenas para os indicadores de exfiltração necessários selecionados.

Quando a detecção cumulativa de exfiltração está habilitada para políticas de roubo  de dados ou vazamento de dados, as informações das atividades de exfiltração cumulativa são exibidas na guia Atividade do usuário dentro de um caso de gerenciamento de risco interno.

Para saber mais sobre o gerenciamento de atividades do usuário, consulte [Insider risk management cases: User activities](insider-risk-management-cases.md#user-activity).

## <a name="policy-health-preview"></a>Saúde da política (visualização)

O status de saúde da política fornece informações sobre possíveis problemas com suas políticas de gerenciamento de riscos internas. A coluna Status na guia Políticas pode alertá-lo sobre problemas de políticas que podem impedir que a atividade do usuário seja relatada ou por que o número de alertas de atividade é incomum. O status de saúde da política também pode confirmar se a política está saudável e não precisa de atenção ou alterações de configuração.

Se houver problemas com uma política, o status de saúde da política exibirá avisos de notificação e recomendações para ajudá-lo a tomar medidas para resolver problemas de política. Essas notificações podem ajudá-lo a resolver os seguintes problemas:

- Políticas com configuração incompleta. Esses problemas podem incluir usuários ou grupos ausentes na política ou em outras etapas de configuração de política incompletas.
- Políticas com problemas de configuração de indicador. Os indicadores são uma parte importante de cada política. Se os indicadores não forem configurados ou se poucos indicadores forem selecionados, a política poderá não avaliar atividades arriscadas conforme esperado.
- Os gatilhos de política não estão funcionando ou os requisitos de gatilho de política não estão configurados corretamente. A funcionalidade da política pode depender de outros serviços ou requisitos de configuração para detectar efetivamente eventos disparados para ativar a atribuição de pontuação de risco aos usuários na política. Essas dependências podem incluir problemas com a configuração do conector, o compartilhamento de alertas do Microsoft Defender for Endpoint ou as configurações da política de prevenção contra perda de dados.
- Os limites de volume estão próximos ou acima dos limites. As políticas de gerenciamento de riscos insider usam vários serviços e pontos de extremidade do Microsoft 365 para agregar sinais de atividade de risco. Dependendo do número de usuários em suas políticas, os limites de volume podem atrasar a identificação e o relatório de atividades de risco. Saiba mais sobre esses limites na seção Limites do modelo de política deste artigo.

Para exibir rapidamente o status de saúde de uma política, navegue pela guia Política e pela coluna Status. Aqui você verá as seguintes opções de status de saúde de política para cada política:

- Saudável: nenhum problema foi identificado com a política.
- Recomendações: Há alguns problemas com a política que podem impedir que a política seja operacional conforme o esperado.
- Avisos: há problemas com a política que a impedirão de identificar atividades arriscadas.

Para obter mais detalhes sobre quaisquer recomendações ou avisos, selecione uma política na guia **Política** para abrir o cartão de detalhes da política. Mais informações sobre as recomendações e avisos, incluindo orientações sobre como resolver esses problemas, serão exibidas na seção Notificações do cartão de detalhes.

![Saúde da política de gerenciamento de riscos do Insider](../media/insider-risk-policy-health.png)

Use a tabela a seguir para saber mais sobre recomendações e notificações de aviso e ações a ser tomadas para resolver possíveis problemas.

|**Mensagens de notificação**|**Modelos de política**|**Causas / Tente corrigir essa ação**|
|:------------------------|:-------------------|:---------------------------|
| Política não está atribuindo pontuações de risco à atividade | Todos os modelos de política | Talvez você queira revisar seu escopo de política e disparar a configuração de evento para que a política possa atribuir pontuações de risco à atividade <br><br> 1. Revise os usuários selecionados para a política. Se você tiver poucos usuários selecionados, talvez você queira selecionar usuários adicionais. <br> 2. Se você estiver usando um conector de RH, verifique se o conector de RH está enviando os dados corretos. <br> 3. Se você estiver usando uma política DLP como seu evento de gatilho, verifique sua configuração de política de DLP para garantir que ela esteja configurada para ser usada nesta política. <br> 4. Para políticas de violação de segurança, revise o status de triagem de alerta do Microsoft Defender for Endpoint selecionado nas configurações de risco do Insider > Detecções inteligentes. Confirme se o filtro de alerta não é muito estreito. |
| A política não gerou alertas | Todos os modelos de política | Talvez você queira revisar sua configuração de política para que você analise a pontuação da atividade com a qual você se importa. <br><br> 1. Confirme se você selecionou indicadores que deseja marcar. Quanto mais indicadores selecionados, mais atividades são atribuídas a pontuações de risco. <br> 2. Revise a personalização de limite para política. Se os limites selecionados não se alinharem à tolerância a riscos da sua organização, ajuste as seleções para que os alertas sejam criados com base nos limites preferenciais. <br> 3. Revise os usuários e grupos selecionados para a política. Confirme se você selecionou todos os usuários e grupos aplicáveis. <br> 4. Para políticas de violação de segurança, confirme se você selecionou o status de triagem de alerta que deseja marcar para alertas do Microsoft Defender para Ponto de Extremidade em Detecções Inteligentes nas configurações.|
| Nenhum usuário ou grupo está incluído nesta política | Todos os modelos de política | Os usuários ou grupos não são atribuídos à política. <br><br> Edite sua política e selecione usuários ou grupos para a política. |
| Nenhum indicador foi selecionado para essa política | Todos os modelos de política | Os indicadores não foram selecionados para a política <br><br> Edite sua política e selecione indicadores de política apropriados para a política. |
| Nenhum grupo de usuários prioritários está incluído nesta política | - Vazamentos de dados por usuários prioritários <br> - Violações de política de segurança por usuários prioritários | Grupos de usuários prioritários não são atribuídos à política. <br><br> Configure grupos de usuários prioritários nas configurações de gerenciamento de risco do Insider e atribua grupos de usuários prioritários à política. |
| Nenhum evento de disparo foi selecionado para essa política | Todos os modelos de política | Um evento de disparo não está configurado para a política <br><br> As pontuações de risco não serão atribuídas às atividades do usuário até que você edite a política e selecione um evento disparador. |
| O conector de RH não está configurado ou funcionando conforme o esperado | - Roubo de dados por usuário de partida <br> - Violações de política de segurança ao partir do usuário <br> - Vazamentos de dados por usuários insatisfeitos <br> - Violações de política de segurança por usuários insatisfeitos | Há um problema com o conector de RH. <br><br> 1. Se você estiver usando um conector de RH, verifique se o conector de RH está enviando dados corretos <br><br> OU <br><br> 2. Selecione o evento de disparo excluído da conta do Azure AD. |
| Nenhum dispositivo está conectado | - Roubo de dados ao separar usuários <br> - Vazamentos gerais de dados <br> - Vazamentos de dados por usuários insatisfeitos <br> - Vazamentos de dados por usuários prioritários | Os indicadores de dispositivo estão selecionados, mas não há dispositivos conectados ao Microsoft 365 <br><br> Verifique se os dispositivos estão conectados e atendem aos requisitos. |
| O conector de RH não carregou dados recentemente | - Roubo de dados por usuário de partida <br> - Violações de política de segurança ao partir do usuário <br> - Vazamentos de dados por usuários insatisfeitos <br> - Violações de política de segurança por usuários insatisfeitos | O conector de RH não importou dados em mais de 7 dias. <br><br> Verifique se o conector de RH está configurado corretamente e enviando dados. |
| Não é possível verificar o status do seu conector de RH agora, verifique novamente mais tarde | - Roubo de dados por usuário de partida <br> - Violações de política de segurança ao partir do usuário <br> - Vazamentos de dados por usuários insatisfeitos <br> - Violações de política de segurança por usuários insatisfeitos | A solução de gerenciamento de risco interno não pode verificar o status do conector de RH. <br><br> Verifique se o conector de RH está configurado corretamente e enviando dados ou volte e verifique o status da política.  |
| A política de DLP não está selecionada como o evento de gatilho | - Vazamentos gerais de dados <br> - Vazamentos de dados por usuários prioritários | Uma política DLP não foi selecionada como um evento de disparo ou a política de DLP selecionada foi excluída. <br><br> Edite a política e selecione uma política DLP ativa ou "O usuário executa uma atividade de exfiltração" como o evento de gatilho na configuração da política. |
| A política de DLP usada nesta política está desligada | - Vazamentos gerais de dados <br> - Vazamentos de dados por usuários prioritários | A política de DLP usada nesta política está desligada. <br><br> 1. Ativar a política DLP atribuída a essa política. <br><br> OU <br><br> 2. Edite essa política e selecione uma nova política de DLP ou "O usuário executa uma atividade de exfiltração" como o evento disparador na configuração da política. |
| A política de DLP não atendem aos requisitos | - Vazamentos gerais de dados <br> - Vazamentos de dados por usuários prioritários | As políticas de DLP usadas como eventos de gatilho devem ser configuradas para gerar alertas de alta gravidade. <br><br>  1. Edite sua política de DLP para atribuir alertas aplicáveis como *Alta gravidade*. <br><br> OU <br><br> 2. Edite essa política e selecione Usuário executa uma atividade *de exfiltração* como o evento de gatilho. |
| Sua organização não tem uma assinatura do Microsoft Defender para Ponto de Extremidade | - Violações gerais da política de segurança <br> - Violações de política de segurança ao separar usuários <br> - Violações de política de segurança por usuários insatisfeitos <br> - Violações de política de segurança por usuários prioritários | Uma assinatura ativa do Microsoft Defender para Ponto de Extremidade não foi detectada para sua organização. <br><br> Até que uma assinatura do Microsoft Defender para Ponto de Extremidade seja adicionada, essas políticas não atribuirão pontuações de risco à atividade do usuário. |
| Os alertas do Microsoft Defenders para Ponto de Extremidade não estão sendo compartilhados com o centro de conformidade | - Violações gerais da política de segurança <br> - Violações de política de segurança ao separar usuários <br> - Violações de política de segurança por usuários insatisfeitos <br> - Violações de política de segurança por usuários prioritários | Os alertas do Microsoft Defender para Ponto de Extremidade não estão sendo compartilhados com o centro de conformidade. <br><br> Configure o compartilhamento do Microsoft Defender para alertas de ponto de extremidade. |
| Você está se aproximando do limite máximo de usuários que estão sendo pontuados ativamente para este modelo de política. | Todos os modelos de política | Cada modelo de política tem um número máximo de usuários no escopo. Consulte os detalhes da seção limite do modelo. <br><br> Revise os usuários na guia Usuários e remova todos os usuários que não precisam mais ser pontuados. |

## <a name="policy-template-limits"></a>Limites do modelo de política

Os modelos de política de gerenciamento de riscos do Insider usam limites para gerenciar o volume e a taxa de processamento para atividades de risco de usuário no escopo e como esse processo é integrado ao suporte aos serviços do Microsoft 365. Cada modelo de política tem um número máximo de usuários que podem ser atribuídos ativamente pontuações de risco para a política que ele pode suportar e processar e relatar efetivamente atividades de risco. Os usuários no escopo são usuários com eventos de gatilho para a política.

O limite para cada política é calculado com base no número total de usuários exclusivos que recebem pontuações de risco por tipo de modelo de política. Se o número de usuários para um tipo de modelo de política estiver próximo ou exceder o limite do usuário, o desempenho da política será reduzido. Para exibir o número atual de usuários de uma política, navegue até a guia Política e a coluna Usuários no escopo. Você pode ter até cinco políticas para qualquer modelo de política. Esses limites máximos se aplicam aos usuários em todas as políticas usando um determinado modelo de política.

Use a tabela a seguir para determinar o número máximo de usuários no escopo com suporte para cada modelo de política:

|**Modelo de política**|**Máximo de usuário no escopo atual**|
|:------------------|:--------------------------------|
| Vazamento geral de dados | 15,000 |
| Vazamento de dados por usuários insatisfeitos | 7,500 |
| Vazamento de dados por usuários prioritários | 1.000 |
| Roubo de dados ao separar usuários | 20,000 |
| Violações gerais da política de segurança | 1.000 |
| Violação de política de segurança por usuários prioritários | 1.000 |
| Violações de política de segurança ao separar usuários | 15,000 |
| Violações de política de segurança por usuários insatisfeitos | 7,500 |

## <a name="create-a-new-policy"></a>Criar uma nova política

Para criar uma nova política de gerenciamento de riscos **insider,** você usará o assistente de política na solução de gerenciamento de riscos do Insider no centro de conformidade do Microsoft 365.

Conclua as etapas a seguir para criar uma nova política:

1. No Centro de conformidade do [Microsoft 365,](https://compliance.microsoft.com)acesse Gerenciamento de riscos **do Insider** e selecione **a guia** Políticas.
2. Selecione **Criar política** para abrir o assistente de política.
3. Na página **Modelo de** Política, escolha uma categoria de política e selecione o modelo da nova política. Esses modelos são feitos de condições e indicadores que definem as atividades de risco que você deseja detectar e investigar. Revise os pré-requisitos do modelo, acionando eventos e atividades detectadas para confirmar que esse modelo de política atende às suas necessidades.

    >[!IMPORTANT]
    >Alguns modelos de política têm pré-requisitos que devem ser configurados para que a política gere alertas relevantes. Se você não configurou os pré-requisitos de política aplicável, consulte **a Etapa 4** acima.

4. Selecione **Próximo** para continuar.
5. Na página **Nome e descrição,** conclua os seguintes campos:
    - **Nome (obrigatório)**: Insira um nome amigável para a política. Esse nome não pode ser alterado após a criação da política.
    - **Descrição (opcional)**: Insira uma descrição para a política.

6. Selecione **Próximo** para continuar.
7. Na página **Usuários** e  grupos, selecione Incluir  todos os usuários e grupos ou Incluir usuários e grupos específicos para definir quais usuários ou grupos estão incluídos na política ou se você escolheu um modelo baseado em usuários prioritários; selecione **Adicionar ou editar grupos de usuários prioritários**. Selecionar **Incluir todos os usuários e grupos** procurará disparar eventos para todos os usuários e grupos em sua organização para começar a atribuir pontuações de risco para a política. Selecionar **Incluir usuários e grupos específicos** permite definir quais usuários e grupos atribuir à política.
8. Selecione **Próximo** para continuar.
9. Na página **Conteúdo para priorizar,** você pode atribuir (se necessário) as fontes a priorizar, o que aumenta a chance de gerar um alerta de alta gravidade para essas fontes. Selecione uma das seguintes opções:

    - **Quero especificar sites do SharePoint, rótulos de sensibilidade e/ou** tipos de informações confidenciais como conteúdo de prioridade. Selecionar essa opção permitirá que páginas de detalhes no assistente configurem esses canais.
    - Não quero especificar o conteúdo de prioridade agora (você poderá fazer isso depois que a **política for criada)**. Selecionar essa opção ignorará as páginas de detalhes do canal no assistente.

10. Selecione **Próximo** para continuar.

11. Se você selecionou Quero especificar sites do SharePoint, rótulos de sensibilidade **e/ou** tipos de informações confidenciais como conteúdo de prioridade na etapa anterior, você verá as páginas de detalhes para sites do *SharePoint,* tipos de informações confidenciais *e* rótulos de *sensibilidade.* Use essas páginas de detalhes para definir o SharePoint, tipos de informações confidenciais e rótulos de sensibilidade para priorizar na política.

    - **Sites do SharePoint**: Selecione **Adicionar site do SharePoint** e selecione as organizações do SharePoint às que você tem acesso e deseja priorizar. Por exemplo, *"group1@contoso.sharepoint.com/sites/group1"*.
    - **Tipo de informação confidenciais**: Selecione **Adicionar tipo de informação confidenciais** e selecione os tipos de sensibilidade que você deseja priorizar. Por exemplo, *"Número da* Conta Bancária dos EUA" e *"Número do Cartão de Crédito"*.
    - **Rótulos de sensibilidade**: **Selecione Adicionar rótulo de** sensibilidade e selecione os rótulos que você deseja priorizar. Por exemplo, *"Confidencial"* e *"Segredo"*.

12. Selecione **Próximo** para continuar.
13. Na página **Indicadores e eventos** de gatilho, você verá os indicadores que você definiu como disponíveis na página Indicadores de configurações de risco do [](insider-risk-management-settings.md#indicators) **Insider.**  >   Se você selecionou um modelo de *vazamentos* de dados no início do assistente, você deve selecionar uma política DLP na lista de menus suspenso de política **DLP** para habilitar indicadores de gatilho para a política ou selecionar o evento de disparo integrado.

    >[!IMPORTANT]
    >Se os indicadores nesta página não puderem ser selecionados, você precisará selecionar os indicadores que deseja habilitar para todas as políticas. Você pode usar o **botão Ativar indicadores** no assistente ou selecionar indicadores na página Indicadores de política de gerenciamento de riscos do **Insider.**  >    >  

    Selecione os indicadores que você deseja aplicar à política. Se você preferir não usar as configurações de limite de política padrão para esses indicadores, desabilite os limites padrão de uso **recomendados** pela Microsoft e insira os valores de limite para cada indicador selecionado.

    - Se você tiver selecionado pelo menos um indicador *do Office* ou *dispositivo,* selecione os impulsionadores de **pontuação** de risco conforme apropriado. Os impulsionadores de pontuação de risco só são aplicáveis para indicadores selecionados.
    - Se você tiver  selecionado um modelo de política de roubo  de dados ou *vazamentos* de dados, selecione um ou mais métodos de detecção de sequência e um método de detecção **cumulativa de exfiltração** a ser aplicado à política.

14. Selecione **Próximo** para continuar.
15. Na página **Limites de indicador,** selecione a opção para usar limites de indicador padrão ou para especificar limites personalizados para indicadores individuais. Para cada indicador, escolha o nível apropriado para gerar o nível desejado de alertas de atividade.
16. Selecione **Próximo** para continuar.
17. Na página **Revisão,** revise as configurações escolhidas para a política e quaisquer sugestões ou avisos para suas seleções. Selecione **Editar** para alterar qualquer um dos valores de política ou selecione **Enviar** para criar e ativar a política.

## <a name="update-a-policy"></a>Atualizar uma política

Para atualizar uma política de gerenciamento de riscos insider existente, você usará o assistente de política na solução de gerenciamento de riscos do **Insider** no centro de conformidade do Microsoft 365.

Conclua as etapas a seguir para gerenciar uma política existente:

1. No Centro de conformidade do [Microsoft 365,](https://compliance.microsoft.com)acesse Gerenciamento de riscos **do Insider** e selecione **a guia** Políticas.
2. No painel de política, selecione a política que deseja gerenciar.
3. Na página detalhes da política, selecione **Editar política**
4. No assistente de política, você não pode editar o seguinte:
    - **Modelo de** política : o modelo usado para definir os tipos de indicadores de risco monitorados pela política.
    - **Nome**: o nome amigável para a política
5. Na página **Nome e descrição,** atualize a descrição da política no campo **Descrição.**
6. Selecione **Próximo** para continuar.
7. Na página **Usuários** e  grupos, selecione Incluir  todos os usuários e grupos ou Incluir usuários e grupos específicos para definir quais usuários ou grupos estão incluídos na política ou se você escolheu um modelo baseado em usuários prioritários; selecione **Adicionar ou editar grupos de usuários prioritários**. Selecionar **Incluir todos os usuários e grupos** procurará disparar eventos para todos os usuários e grupos em sua organização para começar a atribuir pontuações de risco para a política. Selecionar **Incluir usuários e grupos específicos** permite definir quais usuários e grupos atribuir à política.
8. Selecione **Próximo** para continuar.
9. Na página **Conteúdo para priorizar,** você pode atribuir (se necessário) as fontes a priorizar, o que aumenta a chance de gerar um alerta de alta gravidade para essas fontes. Selecione uma das seguintes opções:

    - **Quero especificar sites do SharePoint, rótulos de sensibilidade e/ou** tipos de informações confidenciais como conteúdo de prioridade. Selecionar essa opção permitirá que páginas de detalhes no assistente configurem esses canais.
    - Não quero especificar o conteúdo de prioridade agora (você poderá fazer isso depois que a **política for criada)**. Selecionar essa opção ignorará as páginas de detalhes do canal no assistente.

10. Selecione **Próximo** para continuar.

11. Se você selecionou Quero especificar sites do SharePoint, rótulos de sensibilidade **e/ou** tipos de informações confidenciais como conteúdo de prioridade na etapa anterior, você verá as páginas de detalhes para sites do *SharePoint,* tipos de informações confidenciais *e* rótulos de *sensibilidade.* Use essas páginas de detalhes para definir o SharePoint, tipos de informações confidenciais e rótulos de sensibilidade para priorizar na política.

    - **Sites do SharePoint**: Selecione **Adicionar site do SharePoint** e selecione as organizações do SharePoint às que você tem acesso e deseja priorizar. Por exemplo, *"group1@contoso.sharepoint.com/sites/group1"*.
    - **Tipo de informação confidenciais**: Selecione **Adicionar tipo de informação confidenciais** e selecione os tipos de sensibilidade que você deseja priorizar. Por exemplo, *"Número da* Conta Bancária dos EUA" e *"Número do Cartão de Crédito"*.
    - **Rótulos de sensibilidade**: **Selecione Adicionar rótulo de** sensibilidade e selecione os rótulos que você deseja priorizar. Por exemplo, *"Confidencial"* e *"Segredo"*.

12. Selecione **Próximo** para continuar.
13. Na página **Indicadores e eventos** de gatilho, você verá os indicadores que você definiu como disponíveis na página Indicadores de configurações de risco do [](insider-risk-management-settings.md#indicators) **Insider.**  >   Se você selecionou um modelo de *vazamentos* de dados no início do assistente, você deve selecionar uma política DLP na lista de menus suspenso de política **DLP** para habilitar indicadores de gatilho para a política ou selecionar o evento de disparo integrado.

    >[!IMPORTANT]
    >Se os indicadores nesta página não puderem ser selecionados, você precisará selecionar os indicadores que deseja habilitar para todas as políticas. Você pode usar o **botão Ativar indicadores** no assistente ou selecionar indicadores na página Indicadores de política de gerenciamento de riscos do **Insider.**  >    >  

    Selecione os indicadores que você deseja aplicar à política. Se você preferir não usar as configurações de limite de política padrão para esses indicadores, desabilite os limites padrão de uso **recomendados** pela Microsoft e insira os valores de limite para cada indicador selecionado.

    - Se você tiver selecionado pelo menos um indicador *do Office* ou *dispositivo,* selecione os impulsionadores de **pontuação** de risco conforme apropriado. Os impulsionadores de pontuação de risco só são aplicáveis para indicadores selecionados.
    - Se você tiver  selecionado um modelo de política de roubo  de dados ou *vazamentos* de dados, selecione um ou mais métodos de detecção de sequência e um método de detecção **cumulativa de exfiltração** a ser aplicado à política.

14. Selecione **Próximo** para continuar.
15. Na página **Limites de indicador,** selecione a opção para usar limites de indicador padrão ou para especificar limites personalizados para indicadores individuais. Para cada indicador, escolha o nível apropriado para gerar o nível desejado de alertas de atividade.
16. Selecione **Próximo** para continuar.
17. Na página **Revisão,** revise as configurações escolhidas para a política e quaisquer sugestões ou avisos para suas seleções. Selecione **Editar** para alterar qualquer um dos valores de política ou selecione **Enviar** para criar e ativar a política.

## <a name="copy-a-policy"></a>Copiar uma política

Talvez seja necessário criar uma nova política semelhante a uma política existente, mas que precise de apenas algumas alterações de configuração. Em vez de criar uma nova política do zero, você pode copiar uma política existente e modificar as áreas que precisam ser atualizadas na nova política.

Conclua as etapas a seguir para copiar uma política existente:

1. No centro de conformidade do Microsoft 365, vá para Gerenciamento de riscos do Insider e selecione a guia Políticas.
2. No painel de política, selecione a política que você deseja copiar.
3. Na página detalhes da política, selecione Copiar.
4. No assistente de política, nomee a nova política e atualize a configuração da política conforme necessário.

## <a name="add-users-to-a-policy"></a>Adicionar usuários a uma política

Pode haver cenários em que você precisa adicionar temporariamente usuários às políticas de risco internas depois que um evento incomum é relatado fora do fluxo de trabalho de gerenciamento de riscos insider. Use a atividade iniciar a pontuação para usuários na guia Políticas para adicionar manualmente um usuário (ou usuários) a uma ou mais políticas de risco insider por um período específico de tempo, para começar imediatamente a atribuir pontuações de risco à sua atividade e ignorar o requisito para que um usuário tenha um indicador de disparo (como uma combinação de política de DLP). Você também pode adicionar um motivo para adicionar o usuário à política. Os usuários adicionados manualmente às políticas são exibidos no painel Usuários.

>[!NOTE]
>Pode levar várias horas para que novos usuários adicionados manualmente apareçam no painel Usuários. As atividades dos 90 dias anteriores para esses usuários podem levar até 24 horas para exibição. Para exibir atividades para usuários adicionados manualmente, navegue até a guia Usuários e selecione o usuário no painel Usuários e abra a guia Atividade do usuário no painel de detalhes.

Para adicionar manualmente um(s) usuário(s) a uma ou mais políticas de gerenciamento de riscos insider, conclua as seguintes etapas:

1. No Centro de conformidade do [Microsoft 365,](https://compliance.microsoft.com)acesse Gerenciamento de riscos **do Insider** e selecione **a guia** Políticas.
2. No painel de política, selecione a política ou as políticas às que você deseja adicionar usuários.
3. Selecione **Iniciar atividade de pontuação para usuários**.
4. No campo **Motivo no** painel Adicionar usuários a **várias** políticas, adicione um motivo para adicionar os usuários.
5. No campo Isso deve durar (escolha entre 5 e **30 dias),** defina o número de dias para marcar a atividade do usuário para a política à qual eles são adicionados
6. Para pesquisar usuários no Active Directory, use o **campo Pesquisar usuário para adicionar a políticas.** Digite o nome do usuário que você deseja adicionar às políticas. Selecione o nome de usuário e repita para atribuir usuários adicionais às políticas. A lista de usuários selecionados aparece na seção Usuários do painel Adicionar usuários a várias políticas.
7. Para importar uma lista de usuários para adicionar às políticas, selecione **Importar** para importar um arquivo .csv (valores separados por vírgula). O arquivo deve estar no seguinte formato e você deve listar os nomes principais do usuário no arquivo:

    ```csv
    user principal name
    user1@domain.com
    user2@domain.com
    ```

8. Selecione Adicionar usuários a políticas para aceitar as alterações e adicionar usuários às políticas ou selecione Cancelar para descartar as alterações e fechar a caixa de diálogo.

## <a name="stop-scoring-users-in-a-policy"></a>Parar de pontuar usuários em uma política

Para interromper a pontuação de usuários em uma política, consulte o artigo Usuários de gerenciamento de riscos [do Insider: Remover](insider-risk-management-users.md#remove-users-from-in-scope-assignment-to-policies) usuários da atribuição no escopo para políticas.

## <a name="delete-a-policy"></a>Excluir uma política

>[!NOTE]
>Excluir uma política não exclui alertas ativos ou arquivados gerados da política.

Para excluir uma política de gerenciamento de riscos insider existente, conclua as seguintes etapas:

1. No Centro de conformidade do [Microsoft 365,](https://compliance.microsoft.com)acesse Gerenciamento de riscos **do Insider** e selecione **a guia** Políticas.
2. No painel de política, selecione a política que deseja excluir.
3. Selecione **Excluir** na barra de ferramentas do painel.
4. Na caixa **de diálogo Excluir,** Selecione **Sim** para excluir a política ou selecione **Cancelar** para fechar a caixa de diálogo.
