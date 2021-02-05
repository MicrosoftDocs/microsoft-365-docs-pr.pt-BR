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
description: Seja adicionando novas soluções ao centro de conformidade, atualizando recursos existentes com base em seus comentários ou implantando documentação atualizada e atualizada, o Microsoft 365 ajuda você a se manter informado sobre o cenário de conformidade em constante mudança. Descubra o que estamos fazendo até este mês.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 682f736456ebe822ee5a34de0175003fd7516920
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2021
ms.locfileid: "50113970"
---
# <a name="whats-new-in-microsoft-365-compliance"></a>Novidades na Conformidade do Microsoft 365

Seja adicionando novas soluções ao centro de conformidade do [Microsoft 365,](microsoft-365-compliance-center.md)atualizando recursos existentes com base em seus comentários ou implantando documentação atualizada e atualizada, o Microsoft 365 ajuda você a se manter informado sobre o cenário de conformidade em constante mudança. Dê uma olhada abaixo para ver as novidades na conformidade com o Microsoft 365 hoje.

> [!NOTE]
> Alguns recursos de conformidade são lançados em velocidades diferentes para nossos clientes. Se você ainda não estiver vendo um recurso, tente adicionar a si mesmo ao [lançamento direcionado.](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365)

> [!TIP]
> Interessado no que está acontecendo em outros centros de administração? Confira estes artigos:<br>[Novidades no centro de administração do Microsoft 365](https://docs.microsoft.com/office365/admin/whats-new-in-preview)<br>[Novidades no centro de administração do SharePoint](https://docs.microsoft.com/sharepoint/what-s-new-in-admin-center)<br>[Novidades no Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/whats-new)<br><br>
Visite o Mapa do [Microsoft 365](https://www.microsoft.com/en-us/microsoft-365/roadmap) para saber mais sobre os recursos do Microsoft 365 que foram lançados, estão sendo lançados, estão em desenvolvimento, foram cancelados ou lançados anteriormente.

## <a name="december-2020"></a>Dezembro de 2020

### <a name="spotlight-new-content-for-insider-risk-solutions"></a>Destaque: novo conteúdo para soluções de risco interno

A equipe de conteúdo de conformidade do Microsoft 365 é difícil ao criar documentos de "solução de conteúdo" para promover como os recursos de conformidade podem ser usados juntos para ajudar a cumprir suas metas de conformidade.

Primeiro é o conteúdo que une nossas soluções de risco interno: conformidade de comunicação, gerenciamento de riscos interno, barreiras de informações e gerenciamento de acesso privilegiado. Veja aqui o que você encontrará:

- [Nova página de aterrissagem para soluções de risco interno.](insider-risk-solution-overview.md) Inclui detalhes sobre os riscos que as soluções podem ajudar a atenuar, requisitos de licenciamento, sequência de implantação, ilustrações de arquitetura, recursos de treinamento e muito mais.
- Novos artigos de visão geral para cada solução de risco interno. Diretrizes e links para artigos que ajudam você a aprender sobre, planejar, implantar e gerenciar cada solução:
  - [Conformidade em comunicações](communication-compliance-solution-overview.md)
  - [Gerenciamento de risco interno](insider-risk-management-solution-overview.md)
  - [Barreiras de informações](information-barriers-solution-overview.md)
  - [Gerenciamento de acesso privilegiado](privileged-access-management-solution-overview.md)
  
Mais documentos de solução de conteúdo em breve!

### <a name="advanced-ediscovery"></a>Descoberta Eletrônica Avançada

Melhor fluxo de trabalho e funcionalidade para adicionar [custodiantes](add-custodians-to-case.md) e fontes de dados não [custodial](non-custodial-data-sources.md) a um caso de Descoberta Eletrônico Avançada.

### <a name="data-connectors"></a>Conectores de dados

[Quatro novos conectores Globanet lançados:](archiving-third-party-data.md#third-party-data-connectors)Redtail Speak, Salesforce Connector, ServiceNow e Yieldbroker.

### <a name="encryption"></a>Criptografia

Apresentando [a Chave de Cliente para o Microsoft 365 no nível do locatário.](customer-key-tenant-level.md) Usando chaves fornecidas, você pode criar uma política de criptografia de dados (DEP) e atribuí-la ao locatário. A DEP criptografa dados no locatário para estas cargas de trabalho:

- Mensagens de chat do Teams (chats 1:1, chats em grupo, chats de reunião e conversas de canal)
- Mensagens de mídia do Teams (imagens, trechos de código, vídeos, imagens wiki)
- Gravações de chamada e reunião do Teams armazenadas no armazenamento do Teams
- Notificações de chat do Teams
- Sugestões de chat do Teams da Cortana
- Mensagens de status do Teams
- Informações de usuário e sinal do Exchange Online

### <a name="records-management"></a>Gerenciamento de registros

O [grupo de função de administração de](get-started-with-records-management.md#permissions-required-for-records-management) Gerenciamento de Registros agora concede permissões para todos os recursos de gerenciamento de registros, incluindo a revisão de disposição.

### <a name="sensitivity-labels"></a>Rótulos de confidencialidade

- [Rotule automaticamente os dados no Azure Purview (visualização).](https://docs.microsoft.com/azure/purview/create-sensitivity-label) Agora você pode criar e aplicar automaticamente rótulos de sensibilidade a ativos no Azure Purview, como arquivos no armazenamento de Blob do Azure e colunas de banco de dados no SQL Server.
- [Exigir que os usuários apliquem um rótulo aos itens.](sensitivity-labels-office-apps.md#require-users-to-apply-a-label-to-their-email-and-documents) Também conhecida como "rotulagem obrigatória", essa nova opção exige que os usuários escolham e apliquem um rótulo de sensibilidade nos cenários específicos.

## <a name="november-2020"></a>Novembro de 2020
Apenas um lembrete de que muitas vezes lançamos recursos novos e atualizados em um estado de visualização para saber como eles estão sendo usados para que possamos aprimora-los e melhorá-los antes de liberá-los para disponibilidade geral. Seus comentários são fundamentais durante a visualização (e além), portanto, não deixe de nos dizer o que você acha abrindo o cartão de comentários na parte inferior direita do centro de conformidade.

![comentários](../media/Feedback_card_MCC.JPG)

### <a name="spotlight-endpoint-data-loss-prevention-dlp-released"></a>Destaque: lançamento da DLP (prevenção contra perda de dados) do ponto de extremidade

[O Endpoint DLP amplia](endpoint-dlp-learn-about.md) os recursos de proteção e monitoramento de atividades da DLP para informações confidenciais em dispositivos Windows 10. Depois que os [dispositivos são integrados](dlp-configure-endpoints.md) ao centro de conformidade do Microsoft 365, você pode configurar políticas DLP para proteger as informações confidenciais nesses dispositivos.

### <a name="advanced-ediscovery"></a>Descoberta Eletrônica Avançada

Para facilitar o gerenciamento de conteúdo criptografado no fluxo de trabalho de Descoberta eDiscovery, as ferramentas de Descoberta Eletrônico do Microsoft 365 agora incorporam [a descriptografia](ediscovery-decryption.md) de arquivos criptografados anexados a mensagens de email e enviadas no Exchange. Além disso, os documentos criptografados armazenados no SharePoint e no OneDrive são descriptografados na Descoberta Avançada.

### <a name="compliance-manager"></a>Gerenciador de Conformidade

- [Suporte para assinaturas do Microsoft 365 Government.](compliance-manager.md) O Gerenciador de Conformidade agora está disponível para clientes moderados e altos da Comunidade Governamental dos EUA (GCC).
- [Analisador de Configuração de Conformidade da Microsoft para o Gerenciador de Conformidade.](compliance-manager-mcca.md) Nova ferramenta baseada no PowerShell que ajuda você a começar a usar o Gerenciador de Conformidade, digitalizando as configurações atuais da sua organização e validando-as em relação às práticas recomendadas do Microsoft 365.
- [Novos modelos.](compliance-manager-templates-list.md) Adicionados 56 novos modelos, trazendo o total de modelos do Gerenciador de Conformidade para mais de 230.

### <a name="data-connectors"></a>Conectores de dados

[Cinco novos conectores Globanet na visualização.](archiving-third-party-data.md#third-party-data-connectors) Os novos conectores incluem Reuters Dealing, Reuters FX, CellTrust, XIP, dados genéricos do Banco de Dados SQL do MS.

### <a name="retention-labels-disposition-review"></a>Rótulos de retenção (revisão de disposição)

Para exibir itens durante uma revisão de disposição, os usuários agora devem ser membros dos grupos de função Visualizador de Conteúdo do Explorador de Conteúdo e Visualizador de Lista do Explorador [de Conteúdo.](disposition.md#permissions-for-disposition) Embora seja necessário revisar itens, esses grupos de função não são necessários para concluir a revisão de disposição.

### <a name="sensitivity-labels"></a>Rótulos de confidencialidade

- [(Visualização) Configurações de compartilhamento externo para sites do SharePoint.](sensitivity-labels-teams-groups-sites.md#how-to-configure-groups-and-site-settings) Ao criar um rótulo que será usado para grupos e sites, você verá uma opção para controlar o compartilhamento externo para sites do SharePoint que têm o rótulo aplicado. Você pode especificar que o compartilhamento é permitido para qualquer pessoa, convidados novos e existentes, somente convidados existentes ou apenas para usuários em sua organização. Quando o rótulo é aplicado, as configurações de rótulo substituirão quaisquer configurações de compartilhamento externo configuradas no [centro de administração do SharePoint.](https://docs.microsoft.com/sharepoint/change-external-sharing-site)
- [Remover rótulo e criptografia de um documento rotulado.](sensitivity-labels-sharepoint-onedrive-files.md#remove-encryption-for-a-labeled-document) Para remover um rótulo e a criptografia que ele impõe de um documento rotulado no SharePoint, os administradores globais e administradores do SharePoint podem executar o `Unlock-SPOSensitivityLabelEncryptedFile` novo cmdlet. Esse cmdlet é executado mesmo se o administrador não tiver permissões de acesso ao site ou arquivo ou se o serviço Azure Rights Management não estiver disponível.

## <a name="october-2020"></a>Outubro de 2020

### <a name="advanced-ediscovery"></a>Descoberta Eletrônica Avançada

[Suporte à linguagem CJK.](ediscovery-cjk-support.md) A Descoberta Avançada agora dá suporte a idiomas de conjunto de caracteres de byte duplo, coletivamente conhecidos como idiomas CJK (inclui chinês simplificado, chinês tradicional, japonês e coreano). Eles podem ser usados em vários cenários avançados de conjunto de revisão.

### <a name="sensitivity-labels"></a>Rótulos de confidencialidade

- [Escopo do rótulo.](sensitivity-labels.md#label-scopes) Ao criar um rótulo de sensibilidade, você verá uma nova opção para definir o escopo do rótulo. Essa opção permite configurar rótulos apenas para arquivos e emails, contêineres (como sites do SharePoint e Teams) ou ambos.
- [Marcação de conteúdo dinâmico.](sensitivity-labels-office-apps.md#dynamic-markings-with-variables) Ao configurar a marcação de conteúdo para um rótulo de sensibilidade, agora você pode usar as variáveis dinâmicas, como e na cadeia de caracteres de texto para seu título, rodapé ou marca `${Item.Label}` `${Item.Location}` d'água.

## <a name="september-2020"></a>Setembro de 2020

### <a name="spotlight-compliance-manager"></a>Destaque: Gerenciador de Conformidade

Anunciada no Ignite este ano, a Pontuação de Conformidade foi renomeada como [Gerente de Conformidade.](compliance-manager.md) Esta versão conclui a transição da página anterior do Gerenciador de Conformidade no Portal de Confiança do Serviço e apresenta uma solução de gerenciamento de conformidade de ponta a ponta no centro de conformidade do Microsoft 365.

Assista ao vídeo abaixo para saber como o Gerenciador de Conformidade pode ajudar a simplificar como sua organização gerencia a conformidade.
<br>
<br>
>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4FGYZ]

### <a name="advanced-audit"></a>Auditoria Avançada

- A nova retenção de 10 anos de logs de auditoria ajuda a dar suporte a investigações de longa execução e a responder a obrigações regulatórias, legais e internas.
- [Três novos eventos cruciais.](advanced-audit.md#access-to-crucial-events-for-investigations) Os novos eventos a seguir podem ajudá-lo a investigar possíveis violações e determinar o escopo de comprometimento: Send, SearchQueryInitiatedExchange e SearchQueryInitiatedSharePoint.

### <a name="communication-compliance"></a>Conformidade de comunicações

- [Grupos de função atualizados.](communication-compliance-configure.md#step-1-required-enable-permissions-for-communication-compliance) Os grupos de função de conformidade de comunicação agora corresponderão à estrutura de grupo de função disponível para a solução de gerenciamento de riscos interno.
- [Painel de relatórios.](communication-compliance-feature-reference.md#reports-preview) Seu local central para exibir todos os relatórios de conformidade de comunicação. Os widgets de relatório fornecem uma exibição rápida das informações mais comumente necessárias para uma avaliação geral do status das atividades de conformidade de comunicação.
- [Fluxos do Power Automate.](communication-compliance-feature-reference.md#power-automate-flows) Configurar fluxos para automatizar tarefas para alertas e usuários, notificar gerentes quando os usuários dispararem alertas e muito mais.
- [Ação de correção "Melhorar a classificação".](communication-compliance-investigate-remediate.md#step-3-decide-on-a-remediation-action) Os alertas que contêm itens que corresponderem a classificadores de treinamento podem se beneficiar dos comentários para ajudar a minimizar falsos positivos em sua organização. A **opção Melhorar classificação** permite que você forneça comentários se os itens detectados corresponderem ao classificador configurado na política de conformidade de comunicação relacionada. Você pode até sugerir outros classificadores para associar ao item a fim de melhorar a precisão de match para alertas futuros.

### <a name="data-connectors"></a>Conectores de dados

- [Novos conectores de dados de terceiros.](archiving-third-party-data.md#third-party-data-connectors) 25 novos conectores de dados, incluindo 14 conectores da Globalnet e 8 da Telemessage.
- [Conector de badging físico.](import-physical-badging-data.md) Importe dados de danos físicos, como eventos de acesso físico brutos do funcionário ou quaisquer alarmes de acesso físico gerados pelo sistema de badging da sua organização. Exemplos incluem entradas para edifícios, salas de servidor ou data centers. Os dados de danos físicos podem ser usados pela solução de gerenciamento de riscos interno para ajudar a proteger sua organização contra atividades mal-intencionadas ou roubo de dados dentro da sua organização.

### <a name="insider-risk-management"></a>Gerenciamento de risco interno

- [Integração com o Microsoft Teams.](insider-risk-management-settings.md#microsoft-teams-preview) Quando a integração com o Teams é responsabilidade em configurações de risco interno, você pode coordenar e colaborar com outros participantes no Teams em tarefas como compartilhamento seguro e armazenamento de dados relacionados a casos individuais, rastreamento e revisão de atividades de resposta de analistas e investigadores e muito mais.
- [Fluxos do Power Automate.](insider-risk-management-settings.md#power-automate-flows-preview) Configurar fluxos para automatizar tarefas importantes para casos e usuários, como recuperar informações de usuário, alerta e caso para compartilhar com participantes e outros aplicativos, automatizar ações como postar em anotações de ocorrência e muito mais.
- [Explorador de atividades.](insider-risk-management-alerts.md#activity-explorer-preview) Disponível ao analisar alertas, o explorador de atividades fornece aos investigadores e analistas uma ferramenta de análise abrangente para analisar cada alerta. Revise rapidamente uma linha do tempo de atividade arriscada detectada e identifique e filtre todas as atividades de risco associadas a alertas.

### <a name="retention-policies-and-retention-labels"></a>Políticas de retenção e rótulos de retenção

- [Suporte para Yammer](retention-policies-yammer.md). Agora você pode usar políticas de retenção para reter e excluir mensagens da comunidade do Yammer e mensagens privadas.
- [Aplicar rótulos às gravações de reuniões do Teams.](apply-retention-labels-automatically.md#microsoft-teams-meeting-recordings) Ao criar uma política de rotulagem automática, use o editor de consulta de palavra-chave para identificar as gravações de reunião do Teams armazenadas nas contas do OneDrive dos usuários ou no SharePoint.

### <a name="records-management"></a>Gerenciamento de registros

[Suporte para registros regulatórios.](declare-records.md#how-to-display-the-option-to-mark-content-as-a-regulatory-record) Classificar um rótulo como um registro regulatório aumenta as restrições impostas ao conteúdo ao qual o rótulo é aplicado e limita as ações de gerenciamento disponíveis para o próprio rótulo. Por exemplo, depois que ele for aplicado ao conteúdo, ninguém, nem mesmo um administrador global, poderá remover o rótulo. [Saiba mais](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked) sobre quais ações são permitidas e bloqueadas para registros regulatórios.

### <a name="sensitivity-labels"></a>Rótulos de confidencialidade

[Suporte para clientes do Governo dos Estados Unidos.](https://docs.microsoft.com/enterprise-mobility-security/solutions/ems-aip-premium-govt-service-description) Os rótulos de sensibilidade agora têm suporte para clientes GCC, GCC High e DoD, somente para o cliente e scanner de rotulagem unificada da Proteção de Informações do Azure.

### <a name="trainable-classifiers"></a>Classificadores de treinamento

Os novos recursos de retraining e feedback ajudam a melhorar a precisão e minimizar as falsos positivos para todos os classificadores personalizados e alguns classificadores previamente treinados. Esse fluxo permite que você forneça comentários sobre se os itens corresponderem a determinados classificadores, sugerir outros classificadores para associar aos itens e restringir os classificadores para refinar e melhorar a precisão da combinação.

Esse novo recurso está incluído nos seguintes recursos:

> [!NOTE]
> Para todos os recursos, se você fornecer pelo menos 30 respostas de comentários, criaremos uma versão restrita desse classificador que você pode revisar. Se houver melhorias, você poderá republicar o classificador.

- [Classificadores de treinamento.](classifier-learn-about.md#retraining-classifiers) Para melhorar a precisão dos classificadores publicados, você pode fornecer comentários sobre se os itens detectados corresponderão ao classificador.
- [Conformidade de comunicação.](classifier-how-to-retrain-comms-compliance.md) A nova **ação melhorar** a correção de classificação permite que você forneça comentários se um item de um alerta de conformidade de comunicação corresponde ao classificador configurado na política de conformidade de comunicação.
- [Explorador de conteúdo.](classifier-how-to-retrain-content-explorer.md) Se você configurar uma política de rotulagem automática de retenção para aplicar rótulos automaticamente a mensagens de email que corresponderem a classificadores de treinamento, poderá usar o Explorador de Conteúdo para revisar os itens rotulados e fornecer comentários se os itens corresponderem ao classificador.

## <a name="august-2020"></a>Agosto de 2020

### <a name="spotlight-insider-risk-and-communication-compliance-updates"></a>Destaque: atualizações de conformidade de comunicação e riscos do Insider

Vários recursos novos e aprimorados atingiram a visualização pública este mês:

**Gerenciamento de risco interno**

- Confira nossos seis novos modelos [de política:](insider-risk-management-policies.md#policy-templates)
    - Vazamentos de dados por usuários prioritários
    - Vazamentos de dados por usuários não coerentes
    - Violações gerais da política de segurança
    - Violações da política de segurança por parte dos usuários
    - Violações da política de segurança por usuários prioritários
    - Violações da política de segurança por usuários não coerentes

- A [integração](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) com o Microsoft Defender para Ponto de Extremidade permite importar e filtrar o Microsoft Defender para alertas de ponto de extremidade para atividades detectadas por políticas criadas a partir dos novos modelos de política de violação de segurança. Há também uma configuração de risco interno relacionada onde você pode optar por importar alertas de segurança para o gerenciamento de riscos [insider](insider-risk-management-settings.md#microsoft-defender-for-endpoint-preview) com base no status de triagem de alerta do Microsoft Defender para Ponto de Extremidade.

    > [!NOTE]
    > Para aproveitar a integração do Microsoft Defender para o Ponto de Extremidade (incluindo os novos modelos de violação de política de segurança), você precisará ter o Microsoft Defender para Ponto de Extremidade configurado em sua organização. Você também precisará habilitar o Microsoft Defender para Endpoint para integração de gerenciamento de riscos insider configurando recursos avançados no [Microsoft Defender para Ponto de Extremidade.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center)
 
- Personalizar limites do indicador ao [criar uma política.](insider-risk-management-policies.md#create-a-new-policy)
- Configurar [grupos](insider-risk-management-settings.md#priority-user-groups-preview) de usuários prioritários para definir usuários em sua organização cuja atividade exige uma inspeção mais próxima com base em fatores como sua posição, nível de acesso a informações confidenciais ou histórico de riscos.
- Use as APIs da Atividade [](insider-risk-management-settings.md#export-alerts-preview) de Gerenciamento do Office 365 para exportar detalhes do alerta de risco interno para outros aplicativos que sua organização pode usar para gerenciar ou agregar dados de risco interno.
- As [novas configurações de domínio](insider-risk-management-settings.md#domains-preview) ajudam a definir e controlar níveis de risco para atividades em domínios específicos.

**Conformidade em comunicações**

- Ao [analisar mensagens em um](communication-compliance-investigate-remediate.md#step-3-decide-on-a-remediation-action)alerta, agora você pode remover mensagens inadequadas nos canais do Microsoft Teams, 1:1 e chats em grupo. As mensagens e o conteúdo removidos são substituídos por uma dica de política que explica que ela foi removida devido a conteúdo sensível.
- Novas [funções de](communication-compliance-configure.md#step-1-required-enable-permissions-for-communication-compliance) comunicação (elas também serão incluídas em novos grupos de função de conformidade de comunicação lançados em setembro).
- Nova experiência de configurações de conformidade de comunicação que inclui configurações [de privacidade e](communication-compliance-feature-reference.md#privacy) modelos de [aviso.](communication-compliance-feature-reference.md#notice-templates)
- Novos [classificadores para](communication-compliance-feature-reference.md#classifiers) ajudar a detectar imagens de adulto, racy e consulta.
- A nova notificação "Padrão [](communication-compliance-investigate-remediate.md#step-2-examine-the-message-details) detectado" que aparece ao analisar mensagens em um alerta permite que você saiba sobre instâncias recorrentes do mesmo comportamento por um usuário.

### <a name="sensitivity-labels"></a>Rótulos de confidencialidade

- Para locatários do governo dos Estados Unidos (GCC, GCC-H e DoD) rótulos de confidencialidade possuem suporte somente quando o cliente de rotulagem unificada e digitalização da Proteção de Informações do Microsoft Azure está instalado. Para obter mais informações, confira [Descrição do Serviço Governamental Premium de Proteção de Informações do Microsoft Azure](https://docs.microsoft.com/enterprise-mobility-security/solutions/ems-aip-premium-govt-service-description).
- Agora você pode [usar o PowerShell](create-sensitivity-labels.md#use-powershell-for-sensitivity-labels-and-their-policies) do & Centro de Conformidade e Segurança para criar e definir todas as configurações que você vê no centro de administração de rótulos. Isso significa que, além de usar o PowerShell para configurações que não estão disponíveis nos centros de administração de rotulagem, agora você pode criar um script completo da criação e manutenção de rótulos de sensibilidade e políticas de rótulos de sensibilidade.

### <a name="records-management-content-overhaul"></a>Gerenciamento de registros: revisão de conteúdo

Novos documentos que abrangem etapas de implantação, marcação de conteúdo como registros e registro de versão:

- [Introdução ao gerenciamento de registros](get-started-with-records-management.md)
- [Declarar registros usando rótulos de retenção](declare-records.md)
- [Usar a versão de registro para atualizar registros armazenados no SharePoint ou no OneDrive](record-versioning.md)

### <a name="retention-labels--policies"></a>Rótulos de retenção & políticas

A atividade de administrador relacionada à retenção agora está registrada e disponível para revisão no log de auditoria. Para a lista completa, confira [Política de retenção e atividades do rótulo de retenção](search-the-audit-log-in-security-and-compliance.md#retention-policy-and-retention-label-activities).

### <a name="advanced-ediscovery"></a>Descoberta Eletrônica Avançada

- Ao [adicionar uma coleção a um](add-data-to-review-set.md#define-options-to-scope-your-collection-for-review)conjunto de revisão, agora você pode incluir anexos modernos (também chamados de "anexos de nuvem") e versões de documentos do SharePoint.
- Nova [experiência de exportação de download](export-documents-from-review-set.md)direto, eliminando a necessidade de usar o Azure Storage Explorer para baixar o conteúdo da ocorrência.

## <a name="july-2020"></a>Julho de 2020

### <a name="spotlight-on-help-docs"></a>Destaque nos documentos de ajuda

Para ajudá-lo a entender quais soluções de conformidade são usadas para proteger e reger os dados confidenciais da sua organização, criamos duas novas páginas invasões com visão geral de como as soluções funcionam em conjunto para atingir esses objetivos, incluindo links para documentos relacionados para que você possa se desesincar ainda mais.

[Proteção de Informações da Microsoft no Microsoft 365](information-protection.md)<br>
[Governança de Informações da Microsoft no Microsoft 365](manage-Information-governance.md)

### <a name="advanced-ediscovery-add-non-custodial-data-sources-to-your-cases"></a>Descoberta Avançada: Adicionar fontes de dados não custodial aos seus casos

Adicionar dados a uma ocorrência sem precisar associá-lo a um custodiante (conhecido como fontes de dados não [custodial).](non-custodial-data-sources.md) E se precisar colocar esses dados não custodiais em espera, você poderá fazer isso usando nosso novo recurso de Indexação Avançada.

### <a name="data-connectors-hr-connector-enhancements"></a>Conectores de dados: aprimoramentos do conector de RH

(Na visualização) Uma nova versão do conector [de RH](import-hr-data.md) permite importar dados relacionados a alterações no nível do trabalho, revisões de desempenho e planos de melhoria de desempenho. Esses dados podem ser usados em várias políticas [de risco](insider-risk-management-policies.md) interno para detectar atividades relacionadas.

### <a name="retention-labels-new-support-for-email"></a>Rótulos de retenção: novo suporte para email

Agora você pode criar um [rótulo de retenção](retention.md#retention-labels) para começar a reter emails com base em quando as mensagens foram rotuladas. Isso não se aplica a itens de calendário, que serão retidos com base em quando o item for enviado.

### <a name="sensitivity-labels-new-feature-and-an-improvement"></a>Rótulos de sensibilidade: novo recurso e uma melhoria

- (Na visualização) Ao definir as configurações de criptografia para um [](encryption-sensitivity-labels.md#double-key-encryption) rótulo, procure a nova opção para usar a Criptografia de Chave Dupla para proteger ainda mais os arquivos e emails rotulados.
- Ao criar ou excluir rótulos de sensibilidade ou criar, editar ou excluir suas políticas de rótulo, as alterações agora são sincronizadas em até 1 hora para todos os usuários, aplicativos e serviços.
