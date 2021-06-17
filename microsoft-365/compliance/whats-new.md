---
title: Novidades na Conformidade do Microsoft 365
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
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
ms.openlocfilehash: 1884989abba56a7da68a2a1372132015a81f5e03
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985007"
---
# <a name="whats-new-in-microsoft-365-compliance"></a>Novidades na Conformidade do Microsoft 365

Seja adicionando novas soluções ao centro de conformidade do [Microsoft 365,](microsoft-365-compliance-center.md)atualizando recursos existentes com base em seus comentários ou implantando documentação atualizada e atualizada, o Microsoft 365 ajuda você a manter-se no topo do cenário de conformidade em constante mudança. Confira abaixo o que há de novo na conformidade com o Microsoft 365 hoje.

> [!NOTE]
> Alguns recursos de conformidade são lançados em velocidades diferentes para nossos clientes. Se você ainda não estiver vendo um recurso, tente adicionar a si mesmo à [versão direcionada](/office365/admin/manage/release-options-in-office-365).

> [!TIP]
> Interessado no que está acontecendo em outros centros de administração? Confira estes artigos:<br>[Novidades no centro de administração do Microsoft 365](/office365/admin/whats-new-in-preview)<br>[Novidades no Centro de administração do SharePoint](/sharepoint/what-s-new-in-admin-center)<br>[Novidades no Microsoft 365 Defender](../security/defender/whats-new.md)<br><br>
E visite o Roteiro do [Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap) para saber mais sobre os recursos do Microsoft 365 que foram lançados, estão sendo lançados, estão em desenvolvimento, foram cancelados ou lançados anteriormente.

## <a name="may-2021"></a>Maio de 2021

### <a name="data-loss-prevention"></a>Prevenção contra Perda de Dados

- Novas diretrizes para [planejar sua estratégia de Prevenção contra Perda de](dlp-overview-plan-for-dlp.md) Dados.

### <a name="retention-and-records-management"></a>Gerenciamento de retenção e registros

- Se você liberar uma política de retenção de um site do SharePoint ou conta do OneDrive, não será mais necessário aguardar o período de carência de 30 dias antes de poder excluir o site ou a conta. Uma solicitação popular dos clientes, essa alteração agora está concluída para todos os locatários.
- Na **visualização,** revisão de disposição em vários estágios : [](disposition.md) agora, um administrador pode adicionar até cinco estágios consecutivos de revisão de disposição para um rótulo de retenção, e os revisadores podem adicionar outros usuários ao estágio de revisão de disposição. Você também pode personalizar as notificações e lembretes por email.

### <a name="sensitive-information-types"></a>Tipos de informações confidenciais

- Novas informações adicionadas para ajudá-lo [a modificar um dicionário de palavras-chave](sit-modify-keyword-dictionary.md).

### <a name="sensitivity-labels"></a>Rótulos de confidencialidade

- Na visualização, uma nova configuração **para** o contexto de autenticação agora está disponível quando você configura um rótulo de sensibilidade para grupos [e sites.]( sensitivity-labels-teams-groups-sites.md) Essa opção funciona em conjunto com políticas de Acesso Condicional do Azure AD para impor condições mais rigorosas quando os usuários acessam sites do SharePoint que têm o rótulo aplicado. Leia as [dependências e limitações antes](sensitivity-labels-teams-groups-sites.md#more-information-about-the-dependencies-for-the-authentication-context-option) de configurar essa configuração.
- [As políticas de rotulagem](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange) automática que estão configuradas apenas para o Exchange agora suportam **rótulos** de sensibilidade que aplicam criptografia com Permitir que os usuários atribuam permissões para as opções Não Encaminhar ou Encrypt-Only.
- [A rotulagem obrigatória](sensitivity-labels-office-apps.md#require-users-to-apply-a-label-to-their-email-and-documents) agora está geralmente disponível para todos os aplicativos do Office, em todas as plataformas.

## <a name="april-2021"></a>Abril de 2021

### <a name="advanced-ediscovery"></a>Descoberta Eletrônica Avançada

- [Limites na Descoberta Avançada de EDiscovery](/microsoft-365/compliance/limits-ediscovery20#export-limits---final-export-out-of-review-set). As organizações agora podem exportar até 5 milhões de itens ou 500 MB, o que for menor, em uma única exportação de itens de um conjunto de revisão.

### <a name="data-classification"></a>Classificação de Dados

- [Atividades de rotulagem que estão disponíveis no Explorador de Atividades](/microsoft-365/compliance/data-classification-activity-explorer-available-events)

### <a name="data-connectors"></a>Conectores de dados

- [Configurar um conector para arquivar o Cisco Jabber em dados oracle](/microsoft-365/compliance/archive-ciscojabberonoracle-data)
- [Configurar um conector para arquivar o Cisco Jabber em dados PostgreSQL](/microsoft-365/compliance/archive-ciscojabberonpostgresql-data)

### <a name="data-loss-prevention"></a>Prevenção contra Perda de Dados

- Novo tópico para referência [de dicas de política de prevenção contra](/microsoft-365/compliance/dlp-policy-tips-reference)perda de dados.
- Novo tópico para [Saber mais sobre prevenção contra perda de dados](/microsoft-365/compliance/dlp-learn-about-dlp).
- Novo tópico para [Começar com o painel de alerta de prevenção contra](/microsoft-365/compliance/dlp-alerts-dashboard-get-started)perda de dados .

### <a name="retention-policies-and-retention-label-policies"></a>Políticas de retenção e políticas de rótulo de retenção

- O local dos Grupos do Microsoft 365 agora dá suporte à aplicação das configurações de retenção a apenas caixas de correio do Microsoft 365 ou apenas aos sites conectados do SharePoint usando o cmdlet [Set-RetentionCompliancePolicy PowerShell](/powershell/module/exchange/set-retentioncompliancepolicy) com o parâmetro *Applications.*

### <a name="sensitivity-labels"></a>Rótulos de confidencialidade

Atualizações e versões do Outlook:
- [Configurações diferentes para o rótulo padrão](sensitivity-labels-office-apps.md#outlook-specific-options-for-default-label-and-mandatory-labeling) e rotulagem obrigatória agora são suportadas para rotulagem in-locar. Anteriormente, essas configurações eram suportadas apenas pelo cliente de rotulagem unificada do AIP.
- [Somente criptografia](encryption-sensitivity-labels.md#let-users-assign-permissions) agora é suportado por macOS, iOS e Android.
- [A rotulagem obrigatória](sensitivity-labels-office-apps.md#require-users-to-apply-a-label-to-their-email-and-documents) está sendo implantada nas plataformas restantes.
- [As marcações dinâmicas com todas as variáveis](sensitivity-labels-office-apps.md#dynamic-markings-with-variables) são suportadas em todos os clientes do Outlook.

## <a name="march-2021"></a>Março de 2021

Aqui estão algumas das alterações nas soluções de conformidade e conteúdo do Microsoft 365 para o mês de março.

### <a name="advanced-ediscovery"></a>Descoberta Eletrônica Avançada

- **As coleções avançadas de Descoberta Eletrônico** agora suportam a [nova ferramenta e fluxo de trabalho de coleções.](/microsoft-365/compliance/collections-overview) Outros novos tópicos incluem [criar um conjunto de rascunhos,](/microsoft-365/compliance/create-draft-collection)comprometer uma coleção de [rascunhos em](/microsoft-365/compliance/commit-draft-collection)um conjunto de revisão e estatísticas e relatórios de [coleção.](/microsoft-365/compliance/collection-statistics-reports)
- **Exportar documentos** em um conjunto de revisão para uma [conta de Armazenamento do Azure.](/microsoft-365/compliance/download-export-jobs)
- **Módulo de codificação preditiva para Descoberta Avançada de EDiscovery**. Primeiro, veja a nova [funcionalidade de codificação](/microsoft-365/compliance/predictive-coding-overview) preditiva que substitui o módulo de relevância retirado.

### <a name="data-classification"></a>Classificação de dados

- **Explorador de classificação de dados**. [Começar com o](/microsoft-365/compliance/data-classification-activity-explorer) explorador de classificação de dados.

### <a name="data-connectors"></a>Conectores de dados

- **Chaves privadas**. O suporte para chaves privadas foi adicionado aos dados da [mensagem bloomberg,](/microsoft-365/compliance/archive-bloomberg-message-data#set-up-a-connector-using-public-keys) dados [de chat ICE](/microsoft-365/compliance/archive-icechat-data#set-up-a-connector-using-public-keys) e conectores de dados [instantâneos da Bloomberg.](/microsoft-365/compliance/archive-instant-bloomberg-data#set-up-a-connector-using-public-keys)

### <a name="data-loss-prevention"></a>Prevenção contra perda de dados

- **Suporte do Microsoft Teams**. Suporte à prevenção contra perda de dados estendido ao [Microsoft Teams](/microsoft-365/compliance/dlp-teams-default-policy).
- **Extensão de Conformidade da Microsoft**. Começar com a extensão [de Conformidade da Microsoft](/microsoft-365/compliance/dlp-chrome-get-started).

### <a name="encryption"></a>Criptografia

- **Chave do cliente para o Microsoft 365**. [Visão geral da Chave do](/microsoft-365/compliance/customer-key-tenant-level) Cliente do Microsoft 365 no nível do locatário (visualização pública).
- **Criptografia de Chave Dupla**. Saiba mais sobre a habilitação do suporte para documentos rotulados [e protegidos](/microsoft-365/compliance/double-key-encryption) no SharePoint e no OneDrive for Business.

### <a name="insider-risk-management"></a>Gerenciamento de risco interno

As seguintes atualizações de recursos de gerenciamento de riscos insider foram lançadas para visualização pública em março:

- Novo recurso de análise para identificar riscos antes de criar políticas de risco internas
- Novo suporte e gerenciamento de detecção de sequência de atividades de risco
- Novo suporte para detecção de exfiltração cumulativa
- Novo relatório de política de aplicativo e suporte a recomendações
- Novo recurso de log de auditoria e relatórios
- Aprimoramentos no assistente de criação de política
- Atualizações do explorador de conteúdo
- Novo processo de gerenciamento de usuários/suporte (adicionar/remover usuários de políticas)
- Novo suporte para integração do AAD (suporte à política de usuário)
- Suporte de domínio atualizado em políticas (REGEX)
- Aprimoramentos e aprimoramentos do modelo de política

Os tópicos a seguir foram atualizados ou adicionados para dar suporte a esses novos recursos:

- [Saiba mais sobre o gerenciamento de riscos internos](/microsoft-365/compliance/insider-risk-management)
- [Planejar o gerenciamento de riscos internos](/microsoft-365/compliance/insider-risk-management-plan)
- [Começar com as configurações de gerenciamento de riscos insider](/microsoft-365/compliance/insider-risk-management-settings)
- [Introdução ao gerenciamento de riscos internos](/microsoft-365/compliance/insider-risk-management-configure)
- [Criar e gerenciar políticas de riscos internos](/microsoft-365/compliance/insider-risk-management-policies)
- [Investigar alertas de riscos internos](/microsoft-365/compliance/insider-risk-management-alerts)
- [Tomar medidas em casos de riscos internos](/microsoft-365/compliance/insider-risk-management-cases)
- [Atividades de revisão com o registro de auditoria de risco interno](/microsoft-365/compliance/insider-risk-management-audit-log)
- [Revisar os dados com o explorador de conteúdo de riscos internos](/microsoft-365/compliance/insider-risk-management-content-explorer)
- [Gerenciar o fluxo de trabalho com o Painel de Usuários](/microsoft-365/compliance/insider-risk-management-users)

### <a name="records-management"></a>Gerenciamento de registros

- **Melhorias no plano de arquivos**. Uma atualização para [o plano de arquivos](file-plan-manager.md) remove ou melhora as restrições de comprimento anteriores para importação.
- **Excluir rótulos de retenção para registros**. Uma versão de visualização dá suporte à capacidade de [excluir rótulos de retenção](create-apply-retention-labels.md#deleting-retention-labels) que marcam itens como registros.

### <a name="sensitive-information-types"></a>Tipos de informações confidenciais

O conteúdo foi adicionado ou atualizado nos seguintes tópicos:

- [Começar com o tipo personalizado de informações confidenciais](/microsoft-365/compliance/create-a-custom-sensitive-information-type)
- [Aprenda sobre os tipos de informações confidenciais](/microsoft-365/compliance/sensitive-information-type-learn-about)
- [Criar tipos personalizados de informações confidenciais com classificação baseada em Exact Data Match](/microsoft-365/compliance/create-custom-sensitive-information-types-with-exact-data-match-based-classification)
- [Criar notificações para atividades de combinação de dados exatas](/microsoft-365/compliance/sit-edm-notifications-activities)
- [Definições da entidade Tipo de Informação Confidenciais](/microsoft-365/compliance/sensitive-information-type-entity-definitions)
- [Criar um tipo personalizado de informações confidenciais usando o PowerShell](/microsoft-365/compliance/create-a-custom-sensitive-information-type-in-scc-powershell)
- [Criar um dicionário de palavras-chave](/microsoft-365/compliance/create-a-keyword-dictionary)

### <a name="sensitivity-labels"></a>Rótulos de confidencialidade

- **Suporte a DoD**. Suporte para locatários do governo dos EUA com ambientes DoD.
- **Criptografar somente para o Outlook**. As opções de criptografia para o Outlook agora incluem Encrypt-Only quando você seleciona Permitir que [os usuários atribuam permissões](encryption-sensitivity-labels.md#let-users-assign-permissions).
- **Impor rótulos integrados em aplicativos do Office.** Diretrizes [atualizadas](sensitivity-labels-office-apps.md#office-built-in-labeling-client-and-the-azure-information-protection-client) sobre como impor rótulos integrados em aplicativos do Office quando você tiver o cliente de rotulagem unificado da Proteção de Informações do Azure instalado.

## <a name="february-2021"></a>Fevereiro de 2021

Aqui estão algumas das alterações nas soluções de conformidade e conteúdo do Microsoft 365 para o mês de fevereiro.

### <a name="auditing"></a>Auditoria

- **Gerenciar políticas de retenção de log de auditoria**. Saiba mais sobre o novo [painel políticas de retenção de auditoria.](/microsoft-365/compliance/audit-log-retention-policies#manage-audit-log-retention-policies-1)
- **Pesquise o log de auditoria.** [Use o script do PowerShell para pesquisar o log de auditoria.](/microsoft-365/compliance/audit-log-search-script)

### <a name="data-classification-content-explorer"></a>Explorador de Conteúdo de Classificação de Dados

O conteúdo foi adicionado ou atualizado nos seguintes tópicos:

- [Introdução ao gerenciador de conteúdo ](/microsoft-365/compliance/data-classification-content-explorer)
- [Notas de versão de classificação de dados](/microsoft-365/compliance/data-classification-pub-preview-relnotes)

### <a name="data-loss-prevention"></a>Prevenção contra perda de dados

O conteúdo foi adicionado ou atualizado nos seguintes tópicos:

- [Saiba mais sobre a DLP do Ponto de Extremidade](/microsoft-365/compliance/endpoint-dlp-learn-about)
- [Enviar notificações por email e mostrar dicas para políticas de DLP](/microsoft-365/compliance/use-notifications-and-policy-tips)
- [Saiba mais sobre o scanner local de prevenção contra perda de dados do Microsoft 365](/microsoft-365/compliance/dlp-on-premises-scanner-learn)
- [Começar com o scanner local de prevenção contra perda de dados](/microsoft-365/compliance/dlp-on-premises-scanner-get-started)
- [Criar uma política DLP para proteger documentos com FCI ou outras propriedades](/microsoft-365/compliance/protect-documents-that-have-fci-or-other-properties)
- [Usando a Prevenção contra perda de dados de ponto de extremidade](/microsoft-365/compliance/endpoint-dlp-using)
- [Introdução à Prevenção contra perda de dados do ponto de extremidade](/microsoft-365/compliance/endpoint-dlp-getting-started)

### <a name="ediscovery"></a>Descoberta eletrônica

O conteúdo foi adicionado ou atualizado nos seguintes tópicos:

- [Descriptografia em ferramentas de Descoberta Online do Microsoft 365](/microsoft-365/compliance/ediscovery-decryption)
- [Consultas de palavra-chave e condições da pesquisa](/microsoft-365/compliance/keyword-queries-and-search-conditions#limitations-for-searching-sensitive-data-types)
- [Ressalto do módulo De relevância na Descoberta Avançada da Descoberta Eletrônico](/microsoft-365/compliance/relevance-module-retirement)
- [Usar um script para adicionar usuários a uma responsabilidade em um caso de Descoberta Interna Principal](/microsoft-365/compliance/use-a-script-to-add-users-to-a-hold-in-ediscovery)

### <a name="encryption"></a>Criptografia

O conteúdo foi adicionado ou atualizado nos seguintes tópicos:

#### <a name="azure-rights-management-service-rms"></a>Serviço de Gerenciamento de Direitos do Azure (RMS)

- [Recursos de criptografia de gerenciamento de cliente](/microsoft-365/compliance/office-365-customer-managed-encryption-features)
- [Criptografia de email do Exchange Online com AD RMS](/microsoft-365/compliance/information-rights-management-in-exchange-online). O suporte para esse serviço foi preterido. Você não pode mais usar o AD RMS em um ambiente híbrido do Exchange. Em vez disso, migre para o Azure RMS.

#### <a name="customer-key"></a>Chave de Cliente

- [Chave do cliente para o Microsoft 365 no nível do locatário](/microsoft-365/compliance/customer-key-tenant-level)
- [Visão geral da segurança e conformidade](/microsoftteams/security-compliance-overview)

#### <a name="information-rights-management-irm"></a>Gerenciamento de Direitos de Informação (IRM)

- [Aplicar o IRM (Gerenciamento de Direitos de Informação) a uma lista ou biblioteca.](/microsoft-365/compliance/configure-irm-to-use-an-on-premises-ad-rms-server) Essas nuvens nacionais não suportam essa configuração:
    - Microsoft Cloud para o Governo dos EUA
    - Microsoft Cloud Germany
    - Azure e o Microsoft 365 operados pela 21Vianet na China)
- [Configure o IRM para usar um servidor AD RMS local.](/microsoft-365/compliance/configure-irm-to-use-an-on-premises-ad-rms-server) O suporte a esse serviço em um ambiente híbrido do Exchange foi preterido.

### <a name="sensitive-information-types"></a>Tipos de informações confidenciais

O conteúdo foi adicionado ou atualizado nos seguintes tópicos:

- [Aprenda sobre os tipos de informações confidenciais](/microsoft-365/compliance/sensitive-information-type-learn-about)
- [Criar um tipo de informação confidencial personalizado usando o PowerShell](/microsoft-365/compliance/create-a-custom-sensitive-information-type-in-scc-powershell)
- [Criar tipos de informações confidenciais personalizados com classificação baseada em Exact Data Match](/microsoft-365/compliance/create-custom-sensitive-information-types-with-exact-data-match-based-classification)
- [Definições da entidade do tipo de informações confidenciais](/microsoft-365/compliance/sensitive-information-type-entity-definitions)


### <a name="sensitivity-labels"></a>Rótulos de confidencialidade

O conteúdo foi adicionado ou atualizado nos seguintes tópicos:

- **Compartilhamento externo do SharePoint**. Para [rótulos de contêiner,](sensitivity-labels-teams-groups-sites.md) a opção para compartilhamento externo de sites do SharePoint agora é lançada como geralmente disponível. Além disso, o Centro de administração do Microsoft 365 e o Planner agora suportam a aplicação desses rótulos de sensibilidade. 
- **Coautor e AutoSave**. O suporte [para coautor e AutoSave](sensitivity-labels-coauthoring.md) para arquivos criptografados é lançado como visualização para testes em locatários que não são de produção.

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

Fluxo de trabalho e funcionalidade aprimorados para [adicionar custodiantes](add-custodians-to-case.md) e fontes de dados não [custodiais](non-custodial-data-sources.md) a um Advanced eDiscovery caso.

### <a name="data-connectors"></a>Conectores de dados

[Quatro novos conectores Veritas lançados](archiving-third-party-data.md#third-party-data-connectors): Redtail Speak, Salesforce Chatter, ServiceNow e Yieldbroker.

### <a name="encryption"></a>Criptografia

Apresentando [a Chave do Cliente para Microsoft 365 no nível do locatário.](customer-key-tenant-level.md) Usando chaves fornecidas, você pode criar uma POLÍTICA de criptografia de dados (DEP) e atribuí-la ao locatário. O DEP criptografa dados no locatário para essas cargas de trabalho:

- Teams de chat (chats 1:1, chats de grupo, chats de reunião e conversas de canal)
- Teams de mídia (imagens, trechos de código, vídeos, imagens wiki)
- Teams de chamada e reuniões armazenadas no Teams armazenamento
- Teams de chat
- Teams sugestões de chat por Cortana
- Teams de status
- Informações de usuário e sinal para Exchange Online

### <a name="records-management"></a>Gerenciamento de registros

O [grupo de funções de administrador gerenciamento de](get-started-with-records-management.md#permissions-required-for-records-management) registros agora concede permissões para todos os recursos de gerenciamento de registros, incluindo revisão de disposição.

### <a name="sensitivity-labels"></a>Rótulos de confidencialidade

- [Rotule automaticamente os dados no Azure Purview (visualização)](/azure/purview/create-sensitivity-label). Agora você pode criar e aplicar automaticamente rótulos de sensibilidade a ativos no Azure Purview, como arquivos no armazenamento do Blob do Azure e colunas de banco de dados no SQL Server.
- [Exigir que os usuários apliquem um rótulo a itens](sensitivity-labels-office-apps.md#require-users-to-apply-a-label-to-their-email-and-documents). Também conhecida como "rotulagem obrigatória", essa nova opção exige que os usuários escolham e apliquem um rótulo de sensibilidade nos cenários específicos.
