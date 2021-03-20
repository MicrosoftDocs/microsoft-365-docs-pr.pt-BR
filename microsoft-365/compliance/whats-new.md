---
title: Novidades na Conformidade do Microsoft 365
f1.keywords:
- NOCSH
ms.author: brendonb
author: brendonb
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: Se ele está adicionando novas soluções ao centro de conformidade, atualizando recursos existentes com base em seus comentários ou implantando documentação atualizada e atualizada, o Microsoft 365 ajuda você a se manter no topo do cenário de conformidade em constante mudança. Descubra o que estamos fazendo este mês.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ed29ad5186972f56609a596d88a48c7c460f295f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905853"
---
# <a name="whats-new-in-microsoft-365-compliance"></a>Novidades na Conformidade do Microsoft 365

Seja adicionando novas soluções ao centro de conformidade do [Microsoft 365,](microsoft-365-compliance-center.md)atualizando recursos existentes com base em seus comentários ou implantando documentação atualizada e atualizada, o Microsoft 365 ajuda você a manter-se no topo do cenário de conformidade em constante mudança. Confira abaixo o que há de novo na conformidade com o Microsoft 365 hoje.

> [!NOTE]
> Alguns recursos de conformidade são lançados em velocidades diferentes para nossos clientes. Se você ainda não estiver vendo um recurso, tente adicionar a si mesmo à [versão direcionada](/office365/admin/manage/release-options-in-office-365).

> [!TIP]
> Interessado no que está acontecendo em outros centros de administração? Confira estes artigos:<br>[Novidades no centro de administração do Microsoft 365](/office365/admin/whats-new-in-preview)<br>[Novidades no Centro de administração do SharePoint](/sharepoint/what-s-new-in-admin-center)<br>[Novidades no Microsoft 365 Defender](../security/mtp/whats-new.md)<br><br>
E visite o Roteiro do [Microsoft 365](https://www.microsoft.com/en-us/microsoft-365/roadmap) para saber mais sobre os recursos do Microsoft 365 que foram lançados, estão sendo lançados, estão em desenvolvimento, foram cancelados ou lançados anteriormente.

## <a name="january-2021"></a>Janeiro de 2021

### <a name="support-for-card-content-in-teams"></a>Suporte para conteúdo de cartão no Teams

As seguintes soluções de conformidade do Microsoft 365 agora suportam a detecção de conteúdo de cartão [gerado](/microsoftteams/platform/task-modules-and-cards/what-are-cards) por meio de aplicativos em mensagens do Teams:

- **Descoberta Básica e Avançada.** O conteúdo do cartão agora pode [ser colocado em espera](create-ediscovery-holds.md#preserve-card-content) ou incluído em pesquisas (também se aplica à pesquisa de conteúdo). [](/microsoftteams/ediscovery-investigation#search-for-card-content)
- **Auditoria**. A atividade do cartão agora [está registrada no log de auditoria.](/microsoftteams/audit-log-events#teams-activities)
- **Políticas de retenção**. Agora é possível usar políticas de retenção para [reter e excluir conteúdo de cartão.](retention-policies-teams.md#whats-included-for-retention-and-deletion)

### <a name="information-governance-and-records-management"></a>Gerenciamento de registros e governança de informações

[Nova avaliação](retention-regulatory-requirements.md#new-zealand-public-records-act) para lidar com o uso da governança de informações e gerenciamento de registros para ajudar a cumprir as obrigações de conformidade para a Lei de Registros Públicos da Nova Zelândia.

### <a name="sensitivity-labels"></a>Rótulos de confidencialidade

- Os rótulos de sensibilidade agora são suportados para locatários do Governo dos EUA (GCC e GCC-H).
- Novo [suporte de rotulagem automática](sensitivity-labels-office-apps.md) para macOS.

## <a name="december-2020"></a>Dezembro de 2020

### <a name="spotlight-new-content-for-insider-risk-solutions"></a>Destaque: novo conteúdo para soluções de risco internas

A equipe de conteúdo de conformidade do Microsoft 365 está trabalhando duro ao criar documentos de "solução de conteúdo" para promover como os recursos de conformidade podem ser usados juntos para ajudar a cumprir suas metas de conformidade.

O primeiro é o conteúdo que une nossas soluções de risco insider: conformidade de comunicação, gerenciamento de riscos insider, barreiras de informações e gerenciamento de acesso privilegiado. Veja aqui o que você encontrará:

- [Nova página de aterrissagem para soluções de risco insider.](insider-risk-solution-overview.md) Inclui detalhes sobre os riscos que as soluções podem ajudar a reduzir, requisitos de licenciamento, sequência de implantação, ilustrações de arquitetura, recursos de treinamento e muito mais.
- Novos artigos de visão geral para cada solução de risco interno. Diretrizes e links para artigos que ajudam você a aprender sobre, planejar, implantar e gerenciar cada solução:
  - [Conformidade em comunicações](communication-compliance-solution-overview.md)
  - [Gerenciamento de risco interno](insider-risk-management-solution-overview.md)
  - [Barreiras de informações](information-barriers-solution-overview.md)
  - [Gerenciamento de acesso privilegiado](privileged-access-management-solution-overview.md)
  
Mais documentos de solução de conteúdo em breve!

### <a name="advanced-ediscovery"></a>Descoberta Eletrônica Avançada

Fluxo de trabalho e funcionalidade aprimorados para a adição [de custodiantes](add-custodians-to-case.md) e fontes de dados não custodiais a um caso de Descoberta Avançada. [](non-custodial-data-sources.md)

### <a name="data-connectors"></a>Conectores de dados

[Quatro novos conectores Globanet lançados](archiving-third-party-data.md#third-party-data-connectors): Redtail Speak, Salesforce Chatter, ServiceNow e Yieldbroker.

### <a name="encryption"></a>Criptografia

Apresentando [a Chave do Cliente para o Microsoft 365 no nível do locatário.](customer-key-tenant-level.md) Usando chaves fornecidas, você pode criar uma POLÍTICA de criptografia de dados (DEP) e atribuí-la ao locatário. O DEP criptografa dados no locatário para essas cargas de trabalho:

- Mensagens de chat do Teams (chats 1:1, chats de grupo, chats de reunião e conversas de canal)
- Mensagens de mídia do Teams (imagens, trechos de código, vídeos, imagens wiki)
- Gravações de chamada e reunião do Teams armazenadas no armazenamento do Teams
- Notificações de chat do Teams
- Sugestões de chat do Teams pela Cortana
- Mensagens de status do Teams
- Informações de usuário e sinal para o Exchange Online

### <a name="records-management"></a>Gerenciamento de registros

O [grupo de funções de administrador gerenciamento de](get-started-with-records-management.md#permissions-required-for-records-management) registros agora concede permissões para todos os recursos de gerenciamento de registros, incluindo revisão de disposição.

### <a name="sensitivity-labels"></a>Rótulos de confidencialidade

- [Rotule automaticamente os dados no Azure Purview (visualização)](/azure/purview/create-sensitivity-label). Agora você pode criar e aplicar automaticamente rótulos de sensibilidade a ativos no Azure Purview, como arquivos no armazenamento do Blob do Azure e colunas de banco de dados no SQL Server.
- [Exigir que os usuários apliquem um rótulo a itens](sensitivity-labels-office-apps.md#require-users-to-apply-a-label-to-their-email-and-documents). Também conhecida como "rotulagem obrigatória", essa nova opção exige que os usuários escolham e apliquem um rótulo de sensibilidade nos cenários específicos.

## <a name="november-2020"></a>Novembro de 2020
Apenas um lembrete de que geralmente lançamos recursos novos e atualizados em um estado de visualização para saber como eles estão sendo usados para que possamos aprimora-los e melhorá-los antes de liberá-los para disponibilidade geral. Seus comentários são críticos durante a visualização (e além), portanto, certifique-se de nos dizer o que você acha abrindo o cartão de feedback na parte inferior direita do centro de conformidade.

![comentários](../media/Feedback_card_MCC.JPG)

### <a name="spotlight-endpoint-data-loss-prevention-dlp-released"></a>Destaque: Prevenção contra perda de dados do ponto de extremidade (DLP) lançada

[A DLP do ponto de](endpoint-dlp-learn-about.md) extremidade amplia os recursos de monitoramento e proteção de atividades da DLP para informações confidenciais em dispositivos Windows 10. Depois que os [dispositivos são integrados](dlp-configure-endpoints.md) ao centro de conformidade do Microsoft 365, você pode configurar políticas de DLP para proteger as informações confidenciais nesses dispositivos.

### <a name="advanced-ediscovery"></a>Descoberta Eletrônica Avançada

Para facilitar o gerenciamento de conteúdo criptografado no fluxo de trabalho de Descoberta Eletrônico, as ferramentas de Descoberta Eletrônico do Microsoft 365 agora incorporam [a descriptografia](ediscovery-decryption.md) de arquivos criptografados anexados a mensagens de email e enviadas no Exchange. Além disso, documentos criptografados armazenados no SharePoint e no OneDrive são descriptografados em Descoberta Avançada.

### <a name="compliance-manager"></a>Gerenciador de Conformidade

- [Suporte para assinaturas do Microsoft 365 Government.](compliance-manager.md) O Gerenciador de Conformidade agora está disponível para clientes moderados e altos da Comunidade Governamental dos EUA (GCC).
- [Analisador de Configuração de Conformidade da Microsoft para o Gerenciador de Conformidade.](compliance-manager-mcca.md) Nova ferramenta baseada no PowerShell que ajuda você a começar a usar o Gerenciador de Conformidade, digitalizando as configurações atuais da sua organização e validando-as em relação às práticas recomendadas do Microsoft 365.
- [Novos modelos](compliance-manager-templates-list.md). Foram adicionados 56 novos modelos, trazendo o total de modelos do Gerenciador de Conformidade para mais de 230.

### <a name="data-connectors"></a>Conectores de dados

[Cinco novos conectores Globanet na visualização](archiving-third-party-data.md#third-party-data-connectors). Os novos conectores incluem Reuters Dealing, Reuters FX, CellTrust, XIP, MS genéricos SQL Dados de Banco de Dados.

### <a name="retention-labels-disposition-review"></a>Rótulos de retenção (revisão de disposição)

Para exibir itens durante uma revisão de disposição, os usuários agora devem ser membros dos grupos de função Visualizador de Conteúdo do Explorador de Conteúdo e Visualizador de Lista do Explorador [de Conteúdo.](disposition.md#permissions-for-disposition) Embora seja necessário revisar itens, esses grupos de funções não são necessários para concluir a revisão de disposição.

### <a name="sensitivity-labels"></a>Rótulos de confidencialidade

- [(Visualização) Configurações de compartilhamento externo para sites do SharePoint](sensitivity-labels-teams-groups-sites.md#how-to-configure-groups-and-site-settings). Ao criar um rótulo que será usado para grupos e sites, você verá uma opção para controlar o compartilhamento externo para sites do SharePoint que tenham o rótulo aplicado. Você pode especificar que o compartilhamento é permitido para qualquer pessoa, convidados novos e existentes, somente convidados existentes ou apenas usuários em sua organização. Quando o rótulo for aplicado, as configurações de rótulo substituirão as configurações de compartilhamento externo configuradas no centro de [administração do SharePoint.](/sharepoint/change-external-sharing-site)
- [Remova rótulo e criptografia de um documento rotulado.](sensitivity-labels-sharepoint-onedrive-files.md#remove-encryption-for-a-labeled-document) Para remover um rótulo e a criptografia que ela impõe de um documento rotulado no SharePoint, os administradores globais e os administradores do SharePoint podem executar o `Unlock-SPOSensitivityLabelEncryptedFile` novo cmdlet. Esse cmdlet é executado mesmo se o administrador não tiver permissões de acesso ao site ou arquivo ou se o serviço de Gerenciamento de Direitos do Azure estiver indisponível.

## <a name="october-2020"></a>Outubro de 2020

### <a name="advanced-ediscovery"></a>Descoberta Eletrônica Avançada

[Suporte a idioma CJK](ediscovery-cjk-support.md). A Descoberta Avançada agora dá suporte a idiomas de conjunto de caracteres de byte duplo, coletivamente conhecidos como idiomas CJK (inclui chinês simplificado, chinês tradicional, japonês e coreano). Eles podem ser usados em vários cenários de conjunto de revisão avançada.

### <a name="sensitivity-labels"></a>Rótulos de confidencialidade

- [Escopo do rótulo](sensitivity-labels.md#label-scopes). Ao criar um rótulo de sensibilidade, você verá uma nova opção para definir o escopo do rótulo. Essa opção permite configurar rótulos apenas para arquivos e emails, contêineres (como sites do SharePoint e Teams) ou ambos.
- [Marcação dinâmica de conteúdo](sensitivity-labels-office-apps.md#dynamic-markings-with-variables). Ao configurar a marcação de conteúdo para um rótulo de sensibilidade, agora você pode usar as variáveis dinâmicas, como e na cadeia de caracteres de texto para seu header, rodapé ou marca `${Item.Label}` `${Item.Location}` d'água.

## <a name="september-2020"></a>Setembro de 2020

### <a name="spotlight-compliance-manager"></a>Destaque: Gerenciador de Conformidade

Anunciada no Ignite este ano, a Pontuação de Conformidade é renomeada como [Gerenciador de Conformidade.](compliance-manager.md) Esta versão conclui a transição da casa anterior do Gerenciador de Conformidade no Portal de Confiança de Serviço e introduz uma solução de gerenciamento de conformidade de ponta a ponta no centro de conformidade do Microsoft 365.

Assista ao vídeo abaixo para saber como o Gerenciador de Conformidade pode ajudar a simplificar como sua organização gerencia a conformidade.
<br>
<br>
>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4FGYZ]

### <a name="advanced-audit"></a>Auditoria Avançada

- A nova retenção de 10 anos de logs de auditoria ajuda a dar suporte a investigações de longa duração e responder a obrigações regulatórias, legais e internas.
- [Três novos eventos cruciais](advanced-audit.md#access-to-crucial-events-for-investigations). Os novos eventos a seguir podem ajudá-lo a investigar possíveis violações e determinar o escopo de comprometimento: Send, SearchQueryInitiatedExchange e SearchQueryInitiatedSharePoint.

### <a name="communication-compliance"></a>Conformidade de comunicações

- [Grupos de função atualizados](communication-compliance-configure.md#step-1-required-enable-permissions-for-communication-compliance). Os grupos de função de conformidade de comunicação agora combinam com a estrutura de grupo de função disponível para a solução de gerenciamento de riscos insider.
- [Painel relatórios](communication-compliance-feature-reference.md#reports). Seu local central para exibir todos os relatórios de conformidade de comunicação. Os widgets de relatório fornecem uma visão rápida dos insights mais comumente necessários para uma avaliação geral do status das atividades de conformidade de comunicação.
- [Fluxos do Power Automate](communication-compliance-feature-reference.md#power-automate-flows). Configurar fluxos para automatizar tarefas para alertas e usuários, notificar gerentes quando os usuários dispararem alertas e muito mais.
- [Ação de correção "Melhorar classificação".](communication-compliance-investigate-remediate.md#step-3-decide-on-a-remediation-action) Os alertas que contêm itens que corresponderem a classificadores treináveis podem se beneficiar dos comentários para ajudar a minimizar falsos positivos em sua organização. A **opção Melhorar classificação** permite que você forneça comentários se os itens detectados corresponderão ao classificador configurado na política de conformidade de comunicação relacionada. Você pode até sugerir que outros classificadores se associem ao item para melhorar a precisão da combinação para alertas futuros.

### <a name="data-connectors"></a>Conectores de dados

- [Novos conectores de dados de terceiros.](archiving-third-party-data.md#third-party-data-connectors) 25 novos conectores de dados, incluindo 14 conectores da Globalnet e 8 da Telemessage.
- [Conector de badging físico](import-physical-badging-data.md). Importe dados de danos físicos, como eventos de acesso físico bruto do funcionário ou quaisquer alarmes de acesso físico gerados pelo sistema de badging da sua organização. Exemplos incluem entradas para edifícios, salas de servidor ou data centers. Os dados de danos físicos podem ser usados pela solução de gerenciamento de riscos insider para ajudar a proteger sua organização contra atividades mal-intencionadas ou roubo de dados dentro da sua organização.

### <a name="insider-risk-management"></a>Gerenciamento de risco interno

- [Integração do Microsoft Teams](insider-risk-management-settings.md#microsoft-teams-preview). Quando a integração do Teams estiver ligada em configurações de risco interno, você poderá coordenar e colaborar com outras partes interessadas no Teams em tarefas como compartilhamento seguro e armazenamento de dados relacionados a casos individuais, acompanhamento e revisão de atividades de resposta de analistas e investigadores e muito mais.
- [Fluxos do Power Automate](insider-risk-management-settings.md#power-automate-flows-preview). Configurar fluxos para automatizar tarefas importantes para casos e usuários, como recuperar informações de usuário, alerta e caso para compartilhar com as partes interessadas e outros aplicativos, automatizar ações como postar em anotações de caso e muito mais.
- [Explorador de atividades](insider-risk-management-alerts.md#activity-explorer-preview). Disponível ao analisar alertas, o explorador de atividades fornece aos investigadores e analistas uma ferramenta de análise abrangente para detalhar cada alerta. Revise rapidamente uma linha do tempo de atividade arriscada detectada e identifique e filtre todas as atividades de risco associadas a alertas.

### <a name="retention-policies-and-retention-labels"></a>Políticas de retenção e rótulos de retenção

- [Suporte para o Yammer](retention-policies-yammer.md). Agora você pode usar políticas de retenção para reter e excluir mensagens da comunidade do Yammer e mensagens privadas.
- [Aplicar rótulos às gravações de reuniões do Teams.](apply-retention-labels-automatically.md#microsoft-teams-meeting-recordings) Ao criar uma política de rotulagem automática, use o editor de consulta de palavra-chave para identificar as gravações de reunião do Teams armazenadas nas contas do OneDrive dos usuários ou no SharePoint.

### <a name="records-management"></a>Gerenciamento de registros

[Suporte para registros regulatórios](declare-records.md#how-to-display-the-option-to-mark-content-as-a-regulatory-record). Classificar um rótulo como um registro regulamentar aumenta as restrições colocadas no conteúdo ao qual o rótulo é aplicado e limita as ações de gerenciamento disponíveis para o próprio rótulo. Por exemplo, depois que ele for aplicado ao conteúdo, ninguém, nem mesmo um administrador global, poderá remover o rótulo. [Saiba mais](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked) sobre quais ações são permitidas e bloqueadas para registros regulatórios.

### <a name="sensitivity-labels"></a>Rótulos de confidencialidade

[Suporte para clientes do Governo dos EUA.](/enterprise-mobility-security/solutions/ems-aip-premium-govt-service-description) Os rótulos de sensibilidade agora são suportados para clientes GCC, GCC High e DoD, apenas para o cliente e scanner unificados da Proteção de Informações do Azure.

### <a name="trainable-classifiers"></a>Classificadores de treinamento

Os novos recursos de retreinamento e comentários ajudam a melhorar a precisão e minimizar as combinações de falsos positivos para todos os classificadores personalizados e alguns classificadores pré-treinados. Esse fluxo permite que você forneça comentários sobre se os itens corresponderão a determinados classificadores, sugerir outros classificadores para associar aos itens e retreinar classificadores para refinar e melhorar a precisão da combinação.

Esse novo recurso está incluído nos seguintes recursos:

> [!NOTE]
> Para todos os recursos, se você fornecer pelo menos 30 respostas de comentários, criaremos uma versão retreinada desse classificador que você pode revisar. Se houver melhorias, você poderá republicar o classificador.

- [Classificadores com treinamento.](classifier-learn-about.md#retraining-classifiers) Para melhorar a precisão dos classificadores publicados, você pode fornecer comentários sobre se os itens detectados corresponderão ao classificador.
- [Conformidade de comunicação](classifier-how-to-retrain-comms-compliance.md). A nova **ação Melhorar** correção de classificação permite que você forneça comentários se um item de um alerta de conformidade de comunicação corresponde ao classificador configurado na política de conformidade de comunicação.
- [Explorador de conteúdo](classifier-how-to-retrain-content-explorer.md). Se você configurar uma política de rotulagem automática de retenção para aplicar rótulos automaticamente a mensagens de email que corresponderem a classificadores treináveis, você poderá usar o explorador de conteúdo para revisar os itens rotulados e fornecer comentários se os itens corresponderem ao classificador.

## <a name="august-2020"></a>Agosto de 2020

### <a name="spotlight-insider-risk-and-communication-compliance-updates"></a>Destaque: Atualizações de conformidade de comunicação e riscos do Insider

Vários recursos novos e aprimorados atingiram a visualização pública este mês:

**Gerenciamento de risco interno**

- Confira nossos seis novos modelos [de política:](insider-risk-management-policies.md#policy-templates)
    - Vazamentos de dados por usuários prioritários
    - Vazamentos de dados por usuários insatisfeitos
    - Violações gerais da política de segurança
    - Violações de política de segurança ao separar usuários
    - Violações de política de segurança por usuários prioritários
    - Violações de política de segurança por usuários insatisfeitos

- A integração com o [Microsoft Defender para Ponto](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) de Extremidade permite importar e filtrar alertas do Microsoft Defender para Endpoint para atividades detectadas pelas políticas criadas a partir dos novos modelos de política de violação de segurança. Há também uma [](insider-risk-management-settings.md#microsoft-defender-for-endpoint-preview) configuração de risco interno relacionada em que você pode optar por importar alertas de segurança para o gerenciamento de riscos insider com base no status de triagem de alerta do Microsoft Defender for Endpoint.

    > [!NOTE]
    > Para aproveitar a integração do Microsoft Defender para Ponto de Extremidade (incluindo os novos modelos de violação de política de segurança), você precisará ter o Microsoft Defender para Ponto de Extremidade configurado em sua organização. Você também precisará habilitar o Microsoft Defender para Endpoint para integração de gerenciamento de riscos insider configurando recursos avançados no Microsoft Defender para Ponto de [Extremidade.](/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center)
 
- Personalizar limites de indicador ao [criar uma política](insider-risk-management-policies.md#create-a-new-policy).
- Configurar grupos [de usuários](insider-risk-management-settings.md#priority-user-groups-preview) prioritários para definir usuários em sua organização cuja atividade exija uma inspeção mais próxima com base em fatores como sua posição, nível de acesso a informações confidenciais ou histórico de riscos.
- Use AS APIs de Atividade de Gerenciamento do Office 365 para [exportar](insider-risk-management-settings.md#export-alerts-preview) detalhes do alerta de risco interno para outros aplicativos que sua organização pode usar para gerenciar ou agregar dados de risco interno.
- As [novas configurações de domínio](insider-risk-management-settings.md#domains-preview) ajudam você a definir e controlar níveis de risco para atividades em domínios específicos.

**Conformidade em comunicações**

- Ao [analisar mensagens em um alerta,](communication-compliance-investigate-remediate.md#step-3-decide-on-a-remediation-action)agora você pode remover mensagens inadequadas nos canais do Microsoft Teams, 1:1 e chats de grupo. As mensagens removidas e o conteúdo são substituídos por uma dica de política que explica que ela foi removida devido a conteúdos confidenciais.
- Novas [funções de comunicação](communication-compliance-configure.md#step-1-required-enable-permissions-for-communication-compliance) (elas também serão incluídas em novos grupos de função de conformidade de comunicação lançados em setembro).
- Nova experiência de configurações de conformidade de comunicação que inclui configurações para modelos [de](communication-compliance-feature-reference.md#privacy) privacidade e [aviso.](communication-compliance-feature-reference.md#notice-templates)
- Novos [classificadores para](communication-compliance-feature-reference.md#classifiers) ajudar a detectar imagens de adulto, racy e gory.
- Nova notificação 'Padrão detectado' que aparece ao revisar mensagens em um [alerta](communication-compliance-investigate-remediate.md#step-2-examine-the-message-details) permite que você saiba sobre instâncias recorrentes do mesmo comportamento por um usuário.

### <a name="sensitivity-labels"></a>Rótulos de confidencialidade

- Para locatários do governo dos Estados Unidos (GCC, GCC-H e DoD) rótulos de confidencialidade possuem suporte somente quando o cliente de rotulagem unificada e digitalização da Proteção de Informações do Microsoft Azure está instalado. Para obter mais informações, confira [Descrição do Serviço Governamental Premium de Proteção de Informações do Microsoft Azure](/enterprise-mobility-security/solutions/ems-aip-premium-govt-service-description).
- Agora você pode usar o Centro de Conformidade & Segurança do [PowerShell](create-sensitivity-labels.md#use-powershell-for-sensitivity-labels-and-their-policies) para criar e configurar todas as configurações que você vê no centro de administração de rotulagem. Isso significa que, além de usar o PowerShell para configurações que não estão disponíveis nos centros de administração de rotulagem, agora você pode criar e manter totalmente a criação e a manutenção de rótulos de sensibilidade e políticas de rótulo de sensibilidade.

### <a name="records-management-content-overhaul"></a>Gerenciamento de registros: revisão de conteúdo

Novos documentos que abrangem etapas de implantação, marcação de conteúdo como registros e versão de registro:

- [Introdução ao gerenciamento de registros](get-started-with-records-management.md)
- [Declarar registros usando rótulos de retenção](declare-records.md)
- [Usar a versão de registro para atualizar registros armazenados no SharePoint ou no OneDrive](record-versioning.md)

### <a name="retention-labels--policies"></a>Rótulos de retenção & políticas

A atividade de administrador relacionada à retenção agora está registrada e disponível para revisão no log de auditoria. Para a lista completa, confira [Política de retenção e atividades do rótulo de retenção](search-the-audit-log-in-security-and-compliance.md#retention-policy-and-retention-label-activities).

### <a name="advanced-ediscovery"></a>Descoberta Eletrônica Avançada

- Ao [adicionar uma coleção a](add-data-to-review-set.md#define-options-to-scope-your-collection-for-review)um conjunto de revisão, agora você pode incluir anexos modernos (também chamados de "anexos de nuvem") e versões de documento do SharePoint.
- Nova [experiência de exportação de download direto,](export-documents-from-review-set.md)eliminando a necessidade de usar o Explorador de Armazenamento do Azure para baixar conteúdo de caso.