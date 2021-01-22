---
title: Referência de recursos de conformidade de comunicação
description: Referência de recursos para conformidade de comunicação no Microsoft 365. Saiba detalhes e especificações para cada um dos componentes do recurso.
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: f9c60088372ab69f890c37ebb0e0dda065ec0c65
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928671"
---
# <a name="communication-compliance-feature-reference"></a>Referência de recursos de conformidade de comunicação

## <a name="policies"></a>Políticas

>[!Important]
>Não há suporte para o uso do PowerShell para criar e gerenciar políticas de conformidade de comunicação. Para criar e gerenciar essas políticas, você deve usar os controles de gerenciamento de política na solução de conformidade de comunicação [do Microsoft 365.](https://compliance.microsoft.com/supervisoryreview)

Você cria políticas de conformidade de comunicação para organizações do Microsoft 365 no centro de conformidade do Microsoft 365. As políticas de conformidade de comunicação definem quais comunicações e usuários estão sujeitos à revisão em sua organização, definem quais condições personalizadas as comunicações devem atender e especificam quem deve fazer avaliações. Os usuários  atribuídos à função Administrador de Conformidade de Comunicação podem configurar  políticas, e qualquer pessoa que tenha essa função atribuída pode acessar a página de conformidade de comunicação e as configurações globais no centro de conformidade do Microsoft 365. Se necessário, você pode exportar o histórico de modificações para uma política para um arquivo .csv que também inclui o status de alertas pendentes revisão, itens escalonados e itens resolvidos. As políticas não podem ser renomeadas e podem ser excluídas quando não são mais necessárias.

>[!NOTE]
>As políticas de supervisão criadas no Centro de Conformidade e Segurança & assinaturas do Office 365 não podem migrar para o Microsoft 365. Se você estiver migrando de uma assinatura do Office 365 para uma assinatura do Microsoft 365, precisará criar novas políticas de conformidade de comunicação para substituir as políticas de Supervisão existentes.

## <a name="policy-templates"></a>Modelos de política

Os modelos de política são configurações de política predefinidas que você pode usar para criar rapidamente políticas para lidar com cenários comuns de conformidade. Cada um desses modelos tem diferenças em condições e escopo, e todos os modelos usam os mesmos tipos de sinais de verificação. Você pode escolher entre os seguintes modelos de política:

|**Área**|**Modelo de Política**|**Detalhes**|
|:-----|:-----|:-----|
| **Linguagem ofensiva e anti-abuso** | Monitorar comunicações para linguagem ofensiva | - Locais: Exchange Online, Microsoft Teams, Yammer, Skype for Business <br> - Direção: Entrada, Saída, Interna <br> - Porcentagem de Revisão: 100% <br> - Condições: classificador de idioma ofensivo |
| **Informação confidencial** | Monitorar comunicações para informações confidenciais | - Locais: Exchange Online, Microsoft Teams, Yammer, Skype for Business <br> - Direção: Entrada, Saída, Interna <br> - Porcentagem de Revisão: 10% <br> - Condições: Informações confidenciais, padrões de conteúdo não disponíveis e tipos, opção de dicionário personalizado, anexos maiores do que 1 MB |
| **Conformidade regulatória** | Monitorar comunicações para obter informações relacionadas à conformidade regulamentar financeira | - Locais: Exchange Online, Microsoft Teams, Yammer, Skype for Business <br> - Direção: Entrada, Saída <br> - Porcentagem de Revisão: 10% <br> - Condições: opção de dicionário personalizado, anexos maiores do que 1 MB |
| **Conflito de interesse** | Monitorar as comunicações entre dois grupos ou dois usuários para ajudar a evitar conflitos de interesse | - Locais: Exchange Online, Microsoft Teams, Yammer, Skype for Business <br> - Direção: Interna <br> - Porcentagem de Revisão: 100% <br> - Condições: Nenhuma |

## <a name="permissions"></a>Permissões

>[!Important]
>Por padrão, os Administradores Globais não têm acesso aos recursos de conformidade de comunicação. As funções atribuídas nesta etapa são necessárias para que todos os recursos de conformidade de comunicação sejam acessíveis.

Há cinco grupos de função usados para configurar permissões para gerenciar recursos de conformidade de comunicação. Para disponibilizar **a** conformidade de comunicação como uma opção de menu no centro de conformidade do  Microsoft 365 e continuar com essas etapas de configuração, você deve ser atribuído aos grupos de funções de Conformidade de Comunicação ou Administrador de Conformidade *de* Comunicação. Para acessar e gerenciar recursos de conformidade de comunicação após a configuração inicial, os usuários devem ser membros de pelo menos um grupo de funções de conformidade de comunicação.

Dependendo de como você deseja gerenciar políticas e alertas de comunicação, você precisará atribuir usuários a grupos de função específicos. Você tem a opção de atribuir usuários com diferentes responsabilidades de conformidade a grupos de função específicos para gerenciar diferentes áreas de recursos de conformidade de comunicação. Ou você pode optar por atribuir todas as contas de usuário para administradores designados, analistas, investigadores e visualizadores ao grupo de função *Conformidade* de Comunicação. Use um único grupo de funções ou vários grupos de função para melhor se adequar aos seus requisitos de gerenciamento de conformidade.

Escolha entre essas opções de grupo de função ao configurar a conformidade de comunicação:

|**Default management role assignments for this role**|**Permissões de grupo de função**|
|:-----|:-----|
| **Conformidade de comunicação** | Use esse grupo de função para gerenciar a conformidade de comunicação para sua organização em um único grupo. Ao adicionar todas as contas de usuário para administradores designados, analistas, investigadores e visualizadores, você pode configurar permissões de conformidade de comunicação em um único grupo. Esse grupo de função contém todas as funções de permissão de conformidade de comunicação. Essa configuração é a maneira mais fácil de começar rapidamente com a conformidade de comunicação e é uma boa opção para organizações que não precisam de permissões separadas definidas para grupos separados de usuários. |
| **Administrador de Conformidade de Comunicação** | Use esse grupo de função para configurar inicialmente a conformidade de comunicação e posteriormente segregar os administradores de conformidade de comunicação em um grupo definido. Os usuários atribuídos a esse grupo de funções podem criar, ler, atualizar e excluir políticas de conformidade de comunicação, configurações globais e atribuições de grupo de função. Os usuários atribuídos a esse grupo de funções não podem exibir alertas de mensagem. |
| **Analista de Conformidade de Comunicação** | Use esse grupo para atribuir permissões aos usuários que atuarão como analistas de conformidade de comunicação. Os usuários atribuídos a esse grupo de funções podem exibir políticas às quais são atribuídos como Revisadores, exibir metadados de mensagem (não conteúdo de mensagem), escalonar para revistores adicionais ou enviar notificações aos usuários. Os analistas não podem resolver alertas pendentes. |
| **Investigador de conformidade de comunicação** | Use esse grupo para atribuir permissões aos usuários que atuarão como investigadores de conformidade de comunicação. Os usuários atribuídos a esse grupo de funções podem exibir metadados e conteúdo de mensagens, escalonar para revistores adicionais, escalonar para um caso de Descoberta Avançada, enviar notificações aos usuários e resolver o alerta. |
| **Visualizador de Conformidade de Comunicação** | Use esse grupo para atribuir permissões a usuários que gerenciarão relatórios de comunicação. Os usuários atribuídos a esse grupo de função podem acessar todos os widgets de relatórios na home page de conformidade de comunicação e podem exibir todos os relatórios de conformidade de comunicação. |

### <a name="for-organizations-using-the-original-permissions-and-role-groups"></a>Para organizações que usam as permissões originais e grupos de funções

A nova estrutura de grupo de função substitui a estrutura inicial do grupo de funções para conformidade de comunicação. Para organizações que já usam a conformidade de comunicação, você precisava ter a função Administrador de Revisão de Supervisão atribuída para começar a conformidade de comunicação no centro de conformidade do Microsoft 365. Além disso, você precisava criar um novo grupo de funções para revisadores com as funções Administrador de Análise de Supervisão, Gerenciamento de Caso, Administrador de Conformidade e Revisão para investigar e remediar mensagens com as políticas de acordo. Essencialmente, todos os administradores e revisadores estavam em um único grupo de funções e todos tinham as mesmas permissões de acesso e gerenciamento. Com as atualizações mais recentes para a conformidade de comunicação, você deve planejar a migração da estrutura anterior do grupo de funções para a nova estrutura de grupo de função. O suporte para a estrutura anterior do grupo de função será desaparado.

Para ajudar no planejamento da migração, considere o exemplo a seguir. Atualmente, você tem três tipos de usuários em sua organização, administradores de TI, triagem e revisadores. Esses três tipos de usuários estão na estrutura de grupo de função anterior e são todos membros de um único grupo de funções com as seguintes funções atribuídas:

- Administrador de Revisão de Supervisão
- Gerenciamento de Casos
- Administrador de Conformidade
- Analisar

Para atualizar as funções desses usuários para a nova estrutura de grupo de função e separar as permissões de acesso e gerenciamento para os usuários, você pode considerar três novos grupos e as novas atribuições de grupo de função associadas:

- **Administradores de IT**: Atribuídos ao novo grupo de função *administrador de conformidade* de comunicação.
- **Triagem**: Atribuído ao grupo de função analista *de conformidade* de comunicação.
- **Revisadores**: Atribuído ao novo grupo de função de *Investigador de* Conformidade de Comunicação.

## <a name="supervised-users"></a>Usuários supervisionados

Antes de começar a usar a conformidade de comunicação, você deve determinar quem precisa de suas comunicações revisadas. Na política, os endereços de email do usuário identificam indivíduos ou grupos de pessoas a supervisionar. Alguns exemplos desses grupos são Grupos do Microsoft 365, listas de distribuição baseadas no Exchange, comunidades do Yammer e canais do Microsoft Teams. Você também pode excluir usuários ou grupos específicos da verificação com um grupo de exclusão específico ou uma lista de grupos.

>[!IMPORTANT]
>Os usuários cobertos por políticas de conformidade de comunicação devem ter uma licença de Conformidade do Microsoft 365 E5, uma licença do Office 365 Enterprise E3 com o complemento de Conformidade Avançada ou estar incluídos em uma assinatura do Office 365 Enterprise E5. Se você não tiver um plano Enterprise E5 existente e quiser tentar a conformidade de comunicação, inscreva-se para uma avaliação do [Office 365 Enterprise E5.](https://go.microsoft.com/fwlink/p/?LinkID=698279)

## <a name="reviewers"></a>Revisores

Ao criar uma política de conformidade de comunicação, você deve determinar quem revisa as mensagens dos usuários supervisionados. Na política, os endereços de email do usuário identificam indivíduos ou grupos de pessoas para revisar as comunicações supervisionadas. Todos os revisadores devem ter caixas de correio hospedadas  no Exchange Online e devem ser atribuídos às funções Análise de Conformidade de Comunicação ou Investigação *de Conformidade de* Comunicação. Os revisadores (analistas ou investigadores) também devem ter a função gerenciamento de *caso* de conformidade de comunicação atribuída. Quando os revisadores são adicionados a uma política, eles recebem automaticamente uma mensagem de email que os notifica sobre a atribuição à política e fornece links para informações sobre o processo de revisão.

## <a name="groups-for-supervised-users-and-reviewers"></a>Grupos para usuários supervisionados e revisadores

Para simplificar sua configuração, crie grupos para pessoas que precisam de suas comunicações revisadas e grupos para pessoas que revisam essas comunicações. Se você estiver usando grupos, talvez precise de vários. Por exemplo, se você quiser verificar as comunicações entre dois grupos distintos de pessoas ou se quiser especificar um grupo que não seja supervisionado.

Quando você atribui um grupo de distribuição na política, a política monitora todos os emails de cada usuário no grupo de distribuição. Quando você atribui um grupo do Microsoft 365 na política, a política monitora todos os emails enviados a esse grupo, não os emails individuais recebidos por cada membro do grupo.

A adição de grupos e listas de distribuição a políticas de conformidade de comunicação faz parte das condições e regras gerais definidas, portanto, o número máximo de grupos e listas de distribuição que uma política suporta varia dependendo do número de condições também adicionadas à política. Cada política deve suportar aproximadamente 20 grupos ou listas de distribuição, dependendo do número de condições adicionais presentes na política.

## <a name="supported-communication-types"></a>Tipos de comunicação com suporte

Com as políticas de conformidade de comunicação, você pode optar por examinar as mensagens em uma ou mais das seguintes plataformas de comunicação como um grupo ou como fontes autônomas. As comunicações capturadas nessas plataformas são mantidas por sete anos para cada política por padrão, mesmo que os usuários saiam da sua organização e suas caixas de correio sejam excluídas.

- **Microsoft Teams:** as comunicações de chat em canais públicos e privados do Microsoft Teams e chats individuais podem ser examinadas. Quando os usuários são atribuídos a uma política de conformidade de comunicação com a cobertura do Microsoft Teams selecionada, as comunicações de chat para os usuários são monitoradas automaticamente em todos os Microsoft Teams onde os usuários são membros. A cobertura do Microsoft Teams é incluída automaticamente para modelos de política predefinida e é selecionada por padrão no modelo de política personalizado. Os chats do Teams correspondentes às condições da política de conformidade de comunicação podem levar até 48 horas para processar. Use as seguintes configurações de gerenciamento de grupo para supervisionar chats de usuários individuais e comunicações de canal no Teams:

    - **Para comunicações de chat do Teams:** Atribua usuários individuais ou atribua [um grupo de distribuição](https://support.office.com/article/Distribution-groups-E8BA58A8-FAB2-4AAF-8AA1-2A304052D2DE) à política de conformidade de comunicação. Essa configuração é para relações de usuário/chat de um para um ou um para muitos.
    - **Para comunicações do Canal do Teams:** Atribua cada canal do Microsoft Teams ou grupo do Microsoft 365 que você deseja verificar que contém um usuário específico para a política de conformidade de comunicação. Se você adicionar o mesmo usuário a outros canais do Microsoft Teams ou grupos do Microsoft 365, certifique-se de adicionar esses novos canais e grupos à política de conformidade de comunicação.
    - Para comunicações de chat do Teams com ambientes de **email híbridos:** a conformidade de comunicação pode monitorar mensagens de chat de usuários para organizações com uma implantação local do Exchange ou um provedor de email externo que tenha habilitado o Microsoft Teams. Você deve criar um grupo de distribuição para os usuários com caixas de correio locais ou externas a monitorar. Ao criar uma política de conformidade de comunicação,  você atribuirá esse grupo de distribuição como a seleção de usuários e grupos supervisionados no assistente de política.

    >[!IMPORTANT]
    >Você deve registrar uma solicitação com o suporte da Microsoft para permitir que a sua organização use a interface gráfica do usuário no Centro de Conformidade e Segurança para pesquisar os dados de chat do Teams para usuários locais. Para obter mais informações, consulte [Pesquisar caixas de correio baseadas em nuvem para usuários locais.](search-cloud-based-mailboxes-for-on-premises-users.md)

Você deve registrar uma solicitação com o suporte da Microsoft para permitir que a sua organização use a interface gráfica do usuário no Centro de Conformidade e Segurança para pesquisar os dados de chat do Teams as caixas de correio baseadas em nuvem para usuários locais.

- **Email do Exchange:** as caixas de correio hospedadas no Exchange Online como parte da sua assinatura do Microsoft 365 ou Office 365 estão qualificadas para verificação de mensagens. Mensagens de email do Exchange e anexos correspondentes às condições da política de conformidade de comunicação podem levar até 24 horas para processar. Tipos de anexo com suporte para conformidade de comunicação são os mesmos tipos de arquivo com suporte para inspeções de conteúdo de regras de fluxo de emails [do Exchange.](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection)

- **Yammer:** mensagens privadas e conversas públicas e anexos associados em comunidades do Yammer podem ser verificados. Quando um usuário é adicionado à política de conformidade de comunicação que inclui o Yammer como um canal definido, as comunicações em todas as comunidades do Yammer das que o usuário é membro são incluídas no processo de verificação. Os chats e anexos do Yammer que coincidem com as condições da política de conformidade de comunicação podem levar até 24 horas para processar. O Yammer deve estar no [Modo Nativo para políticas](https://docs.microsoft.com/yammer/configure-your-yammer-network/overview-native-mode) de conformidade de comunicação para monitorar comunicações e anexos do Yammer. No Modo Nativo, todos os usuários do Yammer estão no Azure Active Directory (AAD), todos os grupos são Grupos do Office 365 e todos os arquivos são armazenados no SharePoint Online.

- **Skype for Business Online**: comunicações de chat e anexos associados no Skype for Business Online podem ser supervisionados. Os chats do Skype for Business Online correspondentes às condições da política de conformidade de comunicação podem levar até 24 horas para processar. As conversas de chat supervisionadas são fornecidas de [conversas anteriores salvas no Skype for Business Online.](https://support.office.com/article/Find-a-previous-Skype-for-Business-conversation-18892eba-5f18-4281-8c87-fd48bd72e6a2)  Use a seguinte configuração de gerenciamento de grupo para supervisionar as comunicações de chat do usuário no Skype for Business Online:

    - **Para comunicações de bate-papo** do Skype for Business Online: atribua usuários individuais ou atribua um grupo [de distribuição](https://support.office.com/article/Distribution-groups-E8BA58A8-FAB2-4AAF-8AA1-2A304052D2DE) à política de conformidade de comunicação. Essa configuração é para relações de usuário/chat de um para um ou um para muitos.

- Fontes de **terceiros:** você pode verificar comunicações de dados importados para caixas de correio em sua organização do Microsoft 365 de fontes de terceiros, como [Instant Bloomberg](archive-instant-bloomberg-data.md), [Slack](archive-slack-data.md), [Zoom](archive-zoommeetings-data.md), SMS e muitos outros. Para uma lista completa de conectores com suporte na conformidade de comunicação, consulte [Arquivar dados de terceiros.](archiving-third-party-data.md)

    Você deve configurar um conector de terceiros para sua organização do Microsoft 365 antes de atribuir o conector a uma política de conformidade de comunicação. A **seção Fontes de Terceiros** do assistente de política de conformidade de comunicação exibe apenas conectores de terceiros configurados no momento.

## <a name="transitioning-from-supervision-in-office-365"></a>Transição da supervisão no Office 365

As organizações que usam políticas de supervisão no Office 365 e planejam fazer a transição para políticas de conformidade de comunicação no Microsoft 365 precisam entender estes pontos importantes:

- Ambas as soluções podem ser usadas lado a lado em sua organização, mas as políticas usadas em cada solução devem ter nomes de política exclusivos. Grupos e dicionários de palavras-chave personalizados podem ser compartilhados entre soluções durante um período de transição.
- As mensagens salvas na supervisão nas políticas do Office 365 não podem ser movidas ou compartilhadas para conformidade de comunicação no Microsoft 365.
- A solução de supervisão no Office 365 será totalmente substituída pela solução de conformidade de comunicação no Microsoft 365. É recomendável criar novas políticas de conformidade de comunicação que tenham as mesmas configurações das políticas de supervisão existentes para usar as novas melhorias de investigação e correção. Ao fazer a transição para a conformidade de comunicação no Microsoft 365, você deve planejar exportar dados de relatórios da supervisão no Office 365 se tiver requisitos de política de retenção de conformidade interna.

Para obter informações sobre a baixa supervisão no Office 365, confira o Mapa do [Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap) para obter detalhes.

## <a name="policy-settings"></a>Configurações de política

### <a name="users"></a>Usuários

Você tem a opção de selecionar **Todos os usuários** ou definir usuários específicos em uma política de conformidade de comunicação. Selecionar **Todos os usuários** aplica a política a todos os usuários e grupos em que qualquer usuário está incluído como membro. A definição de usuários específicos aplica a política aos usuários definidos e a todos os grupos em que os usuários definidos estão incluídos como membros.

### <a name="direction"></a>Direção

Por padrão, **a condição Direção** é exibida e não pode ser removida. As configurações de direção de comunicação em uma política são escolhidas individualmente ou juntas:

- **Entrada**: você pode escolher **Entrada para** revisar as comunicações enviadas **para** as pessoas que você escolheu supervisionar.
- **Saída**: Você pode escolher **Saída** se quiser revisar as comunicações enviadas **das** pessoas que você escolheu supervisionar.
- **Interno**: você pode escolher **Interno** para revisar as comunicações enviadas **entre** as pessoas identificadas na política.

### <a name="sensitive-information-types"></a>Tipos de informações confidenciais

Você tem a opção de incluir tipos de informações confidenciais como parte de sua política de conformidade de comunicação. Os tipos de informações confidenciais são tipos de dados pré-definidos ou personalizados que podem ajudar a identificar e proteger números de cartão de crédito, números de contas bancárias, números de passaporte e muito mais. Como parte da prevenção contra perda de dados [(DLP),](data-loss-prevention-policies.md)a configuração de informações confidenciais pode usar padrões, proximidade de caracteres, níveis de confiança e até mesmo tipos de dados personalizados para ajudar a identificar e sinalizar conteúdo que pode ser sensível. Os tipos de informações confidenciais padrão são:

- Financeiro
- Saúde e saúde
- Privacidade
- Tipo de informação personalizada

Para saber mais sobre detalhes de informações confidenciais e os padrões incluídos nos tipos padrão, consulte Definições de entidade de tipo de informações [confidenciais.](sensitive-information-type-entity-definitions.md)

### <a name="custom-keyword-dictionaries"></a>Dicionários de palavras-chave personalizados

Configure dicionários de palavras-chave personalizados (ou léxicos) para fornecer gerenciamento simples de palavras-chave específicas para sua organização ou setor. Os dicionários de palavras-chave suportam até 100 KB de termos (pós-compactação) no dicionário e suportam qualquer idioma. O limite de locatários também é de 100 KB após a compactação. Se necessário, você pode aplicar vários dicionários de palavras-chave personalizados a uma única política ou ter um único dicionário de palavras-chave por política. Esses dicionários são atribuídos em uma política de conformidade de comunicação e podem ser importados de um arquivo (como uma lista .csv ou .txt) ou de uma lista que você pode importar no Centro de [Conformidade.](create-a-keyword-dictionary.md) Use dicionários personalizados quando precisar dar suporte a termos ou idiomas específicos de sua organização e políticas.

### <a name="classifiers"></a>Classificadores

Classificadores globais e integrados verificam mensagens enviadas ou recebidas em todos os canais de comunicação em sua organização em busca de diferentes tipos de problemas de conformidade. Os classificadores usam uma combinação de inteligência artificial e palavras-chave para identificar o idioma nas mensagens que provavelmente violarão políticas anti-abuso. Os classificadores integrados atualmente suportam apenas palavras-chave em inglês nas mensagens.

Os classificadores globais e integrados de conformidade de comunicação verificam as comunicações em busca de termos, imagens e opiniões para os seguintes tipos de idioma e conteúdo:

- **Ameaça:** verifica se há ameaças para comprometer a violência ou danos físicos a uma pessoa ou propriedade.
- **Ataque direcionado:** procura por conduta ofensiva direcionada às pessoas em relação a corrida, cor, origem nacional.
- **Profanidade:** verifica expressões profanas que mentem a maioria das pessoas.
- **Imagens de adulto:** verifica se há imagens explícitas em sua natureza.
- **Imagens de varredura:** examina imagens que são sugeritivas por natureza, mas que contêm conteúdo menos explícito do que imagens consideradas adulto.
- **Imagens de consulta:** verifica se há imagens que descrevem a violência e a violência.

Os *classificadores de* imagem Adult , *Racy* e *Gory* verificam arquivos em . JPEG, . PNG, . GIF e . Formatos BMP. O tamanho dos arquivos de imagem deve ser menor que 4 megabytes (MB) e as dimensões das imagens devem ser maiores que 50 x 50 pixels e mais de 50 kilobytes (KB) para que a imagem se qualibiliza para avaliação. A identificação de imagem é suportada para mensagens de email do Exchange Online e canais e chats do Microsoft Teams.

Os classificadores globais e de treinamento integrados não fornecem uma lista exaustiva de termos ou imagens nessas áreas. Além disso, os padrões de idioma e cultura mudam continuamente e, à luz dessas pessoas, a Microsoft reserva-se o direito de atualizar os classificadores a seu critério. Embora os classificadores possam ajudar sua organização no monitoramento dessas áreas, os classificadores não têm a intenção de fornecer o único meio de monitoramento ou endereçamento de tais idiomas ou imagens da sua organização. Sua organização, não a Microsoft, permanece responsável por todas as decisões relacionadas ao monitoramento, verificação e bloqueio de idioma e imagens nessas áreas, incluindo a conformidade com a privacidade local e outras leis aplicáveis. A Microsoft incentiva a consultoria com consultoria jurídica antes da implantação e uso.

>[!NOTE]
>As políticas que usam classificadores inspecionarão e avaliarão as mensagens com uma contagem de palavras de seis ou mais. As mensagens que contêm menos de seis palavras não são avaliadas em políticas usando classificadores. Para identificar e tomar medidas em mensagens mais curtas que contenham conteúdo inadequado, recomendamos incluir um dicionário de palavras-chave personalizado para o monitoramento de políticas de conformidade de comunicação para esse tipo de conteúdo.

Para saber mais sobre classificadores de treinamento no Microsoft 365, confira Como começar a trabalhar com [classificadores de treinamento.](classifier-get-started-with.md)

### <a name="conditional-settings"></a>Configurações condicionais
<a name="ConditionalSettings"> </a>

As condições escolhidas para a política se aplicam às comunicações de email e de fontes de terceiros em sua organização (como no Instant Bloomberg).

A tabela a seguir explica mais sobre cada condição.
  
|**Condition**|**Como usar essa condição**|
|:-----|:-----|
| **O conteúdo corresponde a qualquer um desses classificadores** | Aplicar à política quando quaisquer classificadores são incluídos ou excluídos em uma mensagem. Alguns classificadores são pré-definidos em seu locatário, e os classificadores personalizados devem ser configurados separadamente antes de serem disponibilizados para essa condição. Apenas um classificador pode ser definido como uma condição em uma política. Para obter mais informações sobre como configurar classificadores, consulte Saiba mais sobre classificadores de treinamento [(visualização).](classifier-learn-about.md) |
| **O conteúdo contém qualquer um desses tipos de informações confidenciais** | Aplicar à política quando quaisquer tipos de informações confidenciais são incluídos ou excluídos em uma mensagem. Alguns classificadores são pré-definidos em seu locatário, e os classificadores personalizados podem ser configurados separadamente ou como parte do processo de atribuição de condição. Cada tipo de informação sensível que você escolher é aplicado separadamente e apenas um desses tipos de informações confidenciais deve ser aplicado para que a política seja aplicada à mensagem. Para obter mais informações sobre tipos personalizados de informações confidenciais, [consulte Saiba mais sobre tipos de informações confidenciais.](sensitive-information-type-learn-about.md) |
| **A mensagem é recebida de qualquer um desses domínios**  <br><br> **A mensagem não é recebida de nenhum desses domínios** | Aplicar a política para incluir ou excluir domínios ou endereços de email específicos nas mensagens recebidas. Insira cada domínio ou endereço de email e separe vários domínios ou endereços de email com uma vírgula. Cada domínio ou endereço de email inserido é aplicado separadamente, apenas um domínio ou endereço de email deve ser aplicado para que a política seja aplicada à mensagem. <br><br> Se você deseja verificar todos os emails de um domínio específico, mas deseja excluir mensagens que não precisam de revisão (boletins informativos, anúncios e assim por diante), você deve configurar uma mensagem que não é recebida de qualquer uma dessas condições de **domínios** que exclua o endereço de email (exemplo "newsletter@contoso.com"). |
| **A mensagem é enviada a qualquer um desses domínios**  <br><br> **A mensagem não é enviada a nenhum desses domínios** | Aplicar a política para incluir ou excluir domínios específicos ou endereços de email em mensagens enviadas. Insira cada domínio ou endereço de email e separe vários domínios ou endereços de email com uma vírgula. Cada domínio ou endereço de email é aplicado separadamente, apenas um domínio ou endereço de email deve ser aplicado para que a política seja aplicada à mensagem. <br><br> Se você quiser verificar todos os emails enviados para um domínio específico, mas quiser excluir as mensagens enviadas que não precisam de revisão, configure duas condições: <br> - **Uma mensagem é enviada para qualquer uma dessas condições de** domínios que define o domínio ("contoso.com"), AND <br> - **Uma mensagem não é enviada a nenhuma condição desses domínios** que exclua o endereço de email ("subscriptions@contoso.com"). |
| **A mensagem é classificada com qualquer um desses rótulos**  <br><br> **A mensagem não é classificada com nenhum desses rótulos** | Para aplicar a política quando determinados rótulos de retenção são incluídos ou excluídos em uma mensagem. Os rótulos de retenção devem ser configurados separadamente e os rótulos configurados são escolhidos como parte dessa condição. Cada rótulo escolhido é aplicado separadamente (somente um desses rótulos deve ser aplicado para que a política seja aplicada à mensagem). Para obter mais informações sobre rótulos de retenção, [consulte Saiba mais sobre políticas de retenção e rótulos de retenção.](retention.md)|
| **A mensagem contém qualquer uma destas palavras**  <br><br> **A mensagem não contém nenhuma dessas palavras** | Para aplicar a política quando determinadas palavras ou frases são incluídas ou excluídas em uma mensagem, insira cada palavra separada por vírgula. Para frases de duas ou mais palavras, use aspas ao redor da frase. Cada palavra ou frase que você inserir é aplicada separadamente (somente uma palavra deve ser aplicada para que a política seja aplicada à mensagem). Para saber mais sobre como inserir palavras ou frases, consulte a próxima seção [Matching words and phrases to emails or attachments](communication-compliance-feature-reference.md#Matchwords).|
| **O anexo contém qualquer uma destas palavras**  <br><br> **O anexo não contém nenhuma dessas palavras** | Para aplicar a política quando determinadas palavras ou frases são incluídas ou excluídas em um anexo de mensagem (como um documento do Word), insira cada palavra separada por vírgula. Para frases de duas ou mais palavras, use aspas ao redor da frase. Cada palavra ou frase que você inserir é aplicada separadamente (somente uma palavra deve ser aplicada para que a política seja aplicada ao anexo). Para saber mais sobre como inserir palavras ou frases, consulte a próxima seção [Matching words and phrases to emails or attachments](communication-compliance-feature-reference.md#Matchwords).|
| **Anexo é qualquer um desses tipos de arquivo**  <br><br> **Anexo não é nenhum desses tipos de arquivo** | Para supervisionar as comunicações que incluem ou excluem tipos específicos de anexos, insira as extensões de arquivo (como .exe ou .pdf). Se você quiser incluir ou excluir várias extensões de arquivo, insira-as em linhas separadas. Somente uma extensão de anexo deve corresponder à política a ser aplicada.|
| **Tamanho da mensagem é maior que**  <br><br> **O tamanho da mensagem não é maior que** | Para revisar as mensagens com base em um determinado tamanho, use essas condições para especificar o tamanho máximo ou mínimo que uma mensagem pode ter antes de ser sujeita à revisão. Por exemplo, se  você especificar que o tamanho da mensagem seja maior que \> **1,0 MB,** todas as mensagens com 1,01 MB ou mais estão sujeitas à revisão. Você pode optar por bytes, kilobytes, megabytes ou gigabytes para essa condição.|
| **O anexo é maior que**  <br><br> **O anexo não é maior que** | Para revisar mensagens com base no tamanho de seus anexos, especifique o tamanho máximo ou mínimo que um anexo pode ter antes que a mensagem e seus anexos sejam sujeitos à revisão. Por exemplo, se você especificar que **o anexo** é maior que \> **2,0 MB,** todas as mensagens com anexos de 2,01 MB ou mais estão sujeitas à revisão. Você pode optar por bytes, kilobytes, megabytes ou gigabytes para essa condição.|
   
#### <a name="matching-words-and-phrases-to-emails-or-attachments"></a>Palavras e frases correspondentes a emails ou anexos
<a name="Matchwords"> </a>

Cada palavra que você inser e separa com uma vírgula é aplicada separadamente (somente uma palavra deve ser aplicada para que a condição de política seja aplicada ao email ou anexo). Por exemplo, vamos usar a **condição,** Message contém qualquer uma dessas palavras , com as palavras-chave "gerente", "confidencial" e "informação interna" separadas por uma vírgula (bancária, confidencial, "negociação interna"). A política se aplica a qualquer mensagem que inclua a palavra "bancária", "confidencial" ou a frase "informação interna". Apenas uma destas palavras ou frases deve ocorrer para que se aplique a condição dessa política. As palavras na mensagem ou no anexo devem corresponder exatamente ao que você inserir.

>[!IMPORTANT]
>Ao importar um arquivo de dicionário personalizado, cada palavra ou frase deve ser separada com um retorno de carro e em uma linha separada. <br> Por exemplo: <br><br>
>*banco de dados* <br>
>*confidencial* <br>
>*insider trading*

Para verificar mensagens de email e anexos em [](create-test-tune-dlp-policy.md) busca das mesmas [](create-a-keyword-dictionary.md) palavras-chave, crie uma política de prevenção contra perda de dados com um dicionário de palavras-chave personalizado para os termos que você deseja verificar nas mensagens. Essa configuração de política identifica palavras-chave definidas que aparecem na mensagem de email **OU** no anexo de email. O uso das configurações de política condicional *padrão* (a mensagem contém qualquer uma dessas palavras e o anexo contém  qualquer uma dessas *palavras)* para identificar termos em mensagens e em anexos exige que os termos sejam presentes na mensagem e no anexo.
  
#### <a name="enter-multiple-conditions"></a>Inserir várias condições

Se você inserir várias condições, o Microsoft 365 usará todas as condições juntas para determinar quando aplicar a política de conformidade de comunicação aos itens de comunicação. Quando você configura várias condições, todas as condições devem ser atendidas para que a política seja aplicada, a menos que você insira uma exceção. Por exemplo, você precisa de uma política que se aplique se uma mensagem contiver a palavra "comercial" e for maior que 2 MB. No entanto, se a mensagem também contiver as palavras "Aprovada pela Contoso financeira", a política não deverá ser aplicada. Neste exemplo, as três condições seriam definidas da seguinte forma:
  
- **A mensagem contém qualquer uma destas palavras,** com a palavra-chave "comercial"
- **O tamanho da mensagem é maior que**, com o valor de 2 MB
- **A mensagem não contém nenhuma dessas palavras,** com as palavras-chave "Aprovado pela equipe financeira da Contoso"

### <a name="review-percentage"></a>Porcentagem de revisão

Se você quiser reduzir a quantidade de conteúdo a ser revisado, poderá especificar uma porcentagem de todas as comunicações controladas por uma política de conformidade de comunicação. Uma amostra aleatória de conteúdo em tempo real é selecionada na porcentagem total do conteúdo que corresponde às condições de política escolhidas. Se quiser que os revisadores revisem todos os itens, você pode configurar **100%** em uma política de conformidade de comunicação.

## <a name="privacy"></a>Privacidade

Proteger a privacidade dos usuários que têm as políticas de acordo é importante e pode ajudar a promover a o objectivity na investigação de dados e análises para alertas de conformidade de comunicação. Essa configuração se aplica somente aos nomes de usuário exibidos na solução de conformidade de comunicação. Isso não afeta como os nomes são exibidos em outras soluções de conformidade ou centro de administração.

Para usuários com uma combinação de conformidade de comunicação, você pode escolher uma das seguintes configurações nas configurações de conformidade **de comunicação:**

- **Mostrar versões anônimas** de nomes de usuário:  os nomes de usuário são anônimos para impedir que os usuários no grupo de funções Analista de Conformidade de Comunicação veja quem está associado aos alertas de política. Os usuários no grupo *de função Investigador de* Conformidade de Comunicação sempre verão nomes de usuário, não as versões anônimas. Por exemplo, um usuário "Grace Ltd" apareceria com um pseudônimo aleatório, como "AnonIS8-988" em todas as áreas da experiência de conformidade de comunicação. Escolher essa configuração anonimiza todos os usuários com as políticas atuais e passadas e se aplica a todas as políticas. As informações de perfil de usuário nos detalhes do alerta de conformidade de comunicação não estarão disponíveis quando essa opção for escolhida. No entanto, os nomes de usuário são exibidos ao adicionar novos usuários a políticas existentes ou ao atribuir usuários a novas políticas. Se você optar por desativar essa configuração, os nomes de usuário serão exibidos para todos os usuários que possuem as políticas atuais ou anteriores.
- **Não mostre versões anônimas** de nomes de usuário: os nomes de usuário são exibidos para todas as políticas atuais e passadas para alertas de conformidade de comunicação. As informações de perfil de usuário (nome, título, alias e organização ou departamento) são exibidas para o usuário em todos os alertas de conformidade de comunicação.

## <a name="notice-templates"></a>Modelos de aviso

Você pode criar modelos de aviso se quiser enviar aos usuários um aviso de lembrete por email para as diretivas que fazem parte do processo de resolução de problemas. Avisos só podem ser enviados para o endereço de email do usuário associado à política que gerou o alerta específico para correção. Ao selecionar um modelo de aviso a ser aplicado a uma violação de política como parte do fluxo de trabalho de correção, você pode optar por aceitar os valores de campo definidos no modelo ou substituir os campos conforme necessário.

Modelos de avisos são modelos de email personalizados onde você pode definir os seguintes campos de mensagem na área de configurações **de conformidade de** comunicação:

|**Campo**|**Required**| **Detalhes** |
|:-----|:-----|:-----|
|**Nome do modelo** | Sim | Nome amigável para o modelo de aviso que você selecionará no fluxo de trabalho de notificação durante a correção, suporta caracteres de texto. |
| **Endereço do remetente**. | Sim | O endereço de um ou mais usuários ou grupos que enviam a mensagem para o usuário com uma política de match, selecionado no Active Directory para sua assinatura. |
| **Endereços CC e Cc** | Não | Usuários ou grupos opcionais a serem notificados sobre a política de match, selecionados no Active Directory para sua assinatura. |
| **Assunto** | Sim | As informações que aparecem na linha de assunto da mensagem são compatíveis com caracteres de texto. |
| **Corpo da mensagem** | Sim | As informações que aparecem no corpo da mensagem são compatíveis com valores de texto ou HTML. |

### <a name="html-for-notices"></a>HTML para avisos

Se você quiser criar mais do que uma mensagem de email simples baseada em texto para notificações, crie uma mensagem mais detalhada usando HTML no campo do corpo da mensagem de um modelo de aviso. O exemplo a seguir fornece o formato do corpo da mensagem para um modelo básico de notificação de email baseado em HTML:

```HTML
<!DOCTYPE html>
<html>
    <body>
        <h2>Action Required: Contoso Employee Code of Conduct Policy Training</h2>
        <p>A recent message you've sent has generated a policy alert for the Contoso Employee <a href='https://www.contoso.com'>Code of Conduct Policy</a>.</p>
        <p>You are required to attend the Contoso Employee Code of Conduct <a href='https://www.contoso.com'>training</a> within the next 14 days. Please contact <a href='mailto:hr@contoso.com'>Human Resources</a> with any questions about this training request.</p>
        <p>Thank you,</p>
        <p><em>Human Resources</em></p>
    </body>
</html>
```

>[!NOTE]
>A implementação do atributo href HTML nos modelos de notificação de conformidade de comunicação atualmente suporta apenas aspas simples em vez de aspas duplas para referências de URL.

## <a name="filters"></a>Filtros

Os filtros de conformidade de comunicação permitem filtrar e classificar mensagens de alerta para ações mais rápidas de investigação e correção. A filtragem está disponível nas guias **Pendentes** **e** Resolvidos para cada política. Para salvar um filtro ou um conjunto de filtros como uma consulta de filtro salva, um ou mais valores devem ser configurados como seleções de filtro. A tabela a seguir descreve os detalhes do filtro:

|**Filtro**|**Detalhes**|
|:-----|:-----|
| **Date** | A data em que a mensagem foi enviada ou recebida por um usuário em sua organização. Para filtrar um único dia, selecione um intervalo de datas que começa com o dia em que você deseja resultados e termine com o dia seguinte. Por exemplo, se você quiser filtrar os resultados de 20/09/2020, escolha um intervalo de datas de filtro de 20/09/2020-21/09/2020.|
| **Classe file** | A classe da mensagem com base no tipo de mensagem, mensagem *ou* *anexo.* |
| **Tem anexo** | A presença do anexo na mensagem. |
| **Classe item** | A origem da mensagem com base no tipo de mensagem, email, bate-papo do Microsoft Team, Bloomberg, etc. Para obter mais informações sobre tipos de item comuns e classes de mensagens, consulte [Tipos de item e classes de mensagem.](https://docs.microsoft.com/office/vba/outlook/concepts/forms/item-types-and-message-classes) |
| **Domínios de destinatários** | O domínio para o qual a mensagem foi enviada. Esse domínio normalmente é seu domínio de assinatura do Microsoft 365 por padrão. |
| **Recipient** | O usuário para o qual a mensagem foi enviada. |
| **Sender** | A pessoa que enviou a mensagem. |
| **Domínio do remetente** | O domínio que enviou a mensagem. |
| **Tamanho** | O tamanho da mensagem em KB. |
| **Assunto/Título** | O assunto da mensagem ou o título do chat. |
| **Marcas** | As marcas atribuídas a uma mensagem, *seja Questionable*, *Compliant* ou *Non-compliant*. |
| **Escalonado para** | O nome de usuário da pessoa incluída como parte de uma ação de escalonamento de mensagem. |
| **Classificadores** | O nome dos classificadores integrados e personalizados que se aplicam à mensagem. Alguns exemplos *incluem Linguagem Ofensiva*, Ataque *Direcionado,* *Profanação,* *Ameaça* e muito mais.

## <a name="alert-policies"></a>Políticas de alerta

Depois de configurar uma política, uma política de alerta correspondente é criada automaticamente e alertas são gerados para mensagens que correspondem às condições definidas na política. Por padrão, todos os gatilhos de alerta de acordo com a política são atribuídos a um nível de severidade médio na política de alerta associada. Os alertas são gerados para uma política de conformidade de comunicação quando o nível limite do gatilho de agregação é atendido na política de alerta associada.

Para políticas de conformidade de comunicação, os seguintes valores de política de alerta são configurados por padrão:

|**Gatilho de política de alerta**|**Valor padrão**|
|:-----|:-----|
| Agregação | Agregação simples |
| Limite | 4 atividades |
| Janela | 60 minutos |

>[!Note]
>As configurações de gatilho de limite de política de alerta para atividades suportam um valor mínimo de 3 ou mais para políticas de conformidade de comunicação.

Você pode alterar as configurações padrão para gatilhos no número de atividades &,  período para as atividades e para usuários específicos em políticas de alerta na página Políticas de alerta no Centro de Conformidade e Segurança.

### <a name="change-the-severity-level-for-an-alert-policy"></a>Alterar o nível de severidade de uma política de alerta

Se você quiser alterar o nível de severidade atribuído em uma política de alerta para uma política de conformidade de comunicação específica, conclua as seguintes etapas:

1. Entre usando [https://compliance.microsoft.com](https://compliance.microsoft.com) credenciais para uma conta de administrador em sua organização do Microsoft 365.

2. No centro de conformidade do Microsoft 365, vá para **Políticas.**

3. Selecione o alerta do Office  **365** na página Políticas para abrir a página Políticas de **alertas** no Centro de Conformidade e Segurança & do Office **365.**

4. Marque a caixa de seleção da política de conformidade de comunicação que você deseja atualizar e selecione **Editar política.**

5. Na guia **Descrição,** selecione o menu suspenso **Gravidade** para configurar o nível de alerta de política.

6. Selecione **Salvar** para aplicar o novo nível de severidade à política.

7. Selecione **Fechar para** sair da página de detalhes da política de alerta.

## <a name="power-automate-flows"></a>Fluxos do Power Automate

[O Microsoft Power Automate é](https://docs.microsoft.com/power-automate/getting-started) um serviço de fluxo de trabalho que automatiza ações entre aplicativos e serviços. Usando fluxos de modelos ou criados manualmente, você pode automatizar tarefas comuns associadas a esses aplicativos e serviços. Ao habilitar fluxos do Power Automate para conformidade de comunicação, você pode automatizar tarefas importantes para alertas e usuários. Você pode configurar fluxos do Power Automate para notificar gerentes quando os usuários têm alertas de conformidade de comunicação e outros aplicativos.

Os clientes com assinaturas do Microsoft 365 que incluem conformidade de comunicação não precisam de licenças adicionais do Power Automate para usar o modelo do Power Automate de conformidade de comunicação padrão recomendado. O modelo padrão pode ser personalizado para dar suporte à sua organização e abranger os principais cenários de conformidade de comunicação. Se você optar por usar recursos premium do Power Automate nesses modelos, criar um modelo personalizado usando o conector de conformidade do Microsoft 365 ou usar modelos do Power Automate para outras áreas de conformidade no Microsoft 365, talvez você precise de licenças adicionais do Power Automate.

>[!IMPORTANT]
>Você está recebendo solicitações de validação de licença adicionais ao testar fluxos do Power Automate? Sua organização pode não ter recebido atualizações de serviço para esse recurso de visualização ainda. As atualizações estão sendo implantadas e todas as organizações com assinaturas do Microsoft 365 que incluem conformidade de comunicação devem ter suporte de licença para fluxos criados a partir dos modelos recomendados do Power Automate até 30 de outubro de 2020.

![Conformidade de comunicação do Power Automate](../media/communication-compliance-power-automate.png)

O seguinte modelo do Power Automate é fornecido aos clientes para dar suporte à automação de processos para alertas de conformidade de comunicação:

- **Notificar o gerente quando um usuário tiver** um alerta de conformidade de comunicação: algumas organizações talvez precisem ter uma notificação de gerenciamento imediata quando um usuário tiver um alerta de conformidade de comunicação. Quando esse fluxo é configurado e selecionado, o gerente do usuário da ocorrência recebe uma mensagem de email com as seguintes informações sobre todos os alertas:
    - Política aplicável para o alerta
    - Data/hora do alerta
    - Nível de gravidade do alerta

### <a name="create-a-power-automate-flow"></a>Criar um fluxo do Power Automate

Para criar um fluxo do Power Automate a partir de um modelo padrão  recomendado, você usará a opção Gerenciar fluxos do **Power Automate** do controle Automatizado ao trabalhar diretamente em um alerta. Para criar um fluxo do Power Automate com o gerenciamento de fluxos do **Power Automate,** você deve ser membro de pelo menos um grupo de função de conformidade de comunicação.

Conclua as seguintes etapas para criar um fluxo do Power Automate a partir de um modelo padrão:

1. No centro de conformidade do Microsoft 365, vá para Políticas de conformidade de comunicação e selecione a política com o  >   alerta que você deseja analisar.
2. Na política, selecione a guia **Pendente** e selecione um alerta pendente.
3. Selecione **Power Automate** no menu de ação de alerta.
4. Na página **Do Power Automate,** selecione um modelo padrão nos modelos de conformidade de comunicação que **você** talvez adote a seção na página.
5. O fluxo lista as conexões incorporadas necessárias para o fluxo e será exibido se os status da conexão estão disponíveis. Se necessário, atualize as conexões que não são exibidas como disponíveis. Selecione **Continuar**.
6. Por padrão, os fluxos recomendados são pré-configurados com a conformidade de comunicação recomendada e os campos de dados de serviço do Microsoft 365 necessários para concluir a tarefa atribuída para o fluxo. Se necessário, personalize os componentes de fluxo usando o controle Mostrar opções **avançadas** e configurando as propriedades disponíveis para o componente de fluxo.
7. Se necessário, adicione outras etapas ao fluxo selecionando o **botão Nova etapa.** Na maioria dos casos, essa alteração não deve ser necessária para os modelos padrão recomendados.
8. Selecione **Salvar rascunho para** salvar o fluxo para mais configuração posteriormente ou selecione **Salvar** para concluir a configuração do fluxo.
9. Selecione **Fechar** para retornar à página de fluxo do Power Automate. O novo modelo será listado como  um fluxo na guia Meus fluxos e estará automaticamente disponível no controle do Power Automate para o usuário que criou o fluxo ao trabalhar com alertas de conformidade de comunicação.

### <a name="share-a-power-automate-flow"></a>Compartilhar um fluxo do Power Automate

Por padrão, os fluxos do Power Automate criados por um usuário estão disponíveis apenas para esse usuário. Para que outros usuários de conformidade de comunicação tenham acesso e usem um fluxo, o fluxo deve ser compartilhado pelo criador do fluxo. Para compartilhar um fluxo, você usará o **controle do Power Automate** ao trabalhar diretamente em um alerta.

Para compartilhar um fluxo do Power Automate, você deve ser membro de pelo menos um grupo de função de conformidade de comunicação.
Conclua as seguintes etapas para compartilhar um fluxo do Power Automate:

1. No centro de conformidade do Microsoft 365, vá para Políticas de conformidade de comunicação e selecione a política com o  >   alerta que você deseja analisar.
2. Na política, selecione a guia **Pendente** e selecione um alerta pendente.
3. Selecione **Power Automate** no menu de ação de alerta.
4. Na página **Fluxos do Power Automate,** selecione a **guia Meus fluxos** ou **Fluxos de** equipe.
5. Selecione o fluxo a ser compartilhá-lo e, em seguida, **selecione Compartilhar** no menu opções de fluxo.
6. Na página de compartilhamento de fluxo, insira o nome do usuário ou grupo que você deseja adicionar como proprietário do fluxo.
7. Na caixa **de diálogo Conexão Usada,** selecione **OK** para confirmar que o usuário ou grupo adicionado terá acesso total ao fluxo.

### <a name="edit-a-power-automate-flow"></a>Editar um fluxo do Power Automate

Se precisar editar um fluxo, você usará o controle do **Power Automate** ao trabalhar diretamente em um alerta. Para editar um fluxo do Power Automate, você deve ser membro de pelo menos um grupo de função de conformidade de comunicação.

Conclua as seguintes etapas para editar um fluxo do Power Automate:

1. No centro de conformidade do Microsoft 365, vá para Políticas de conformidade de comunicação e selecione a política com o  >   alerta que você deseja analisar.
2. Na política, selecione a guia **Pendente** e selecione um alerta pendente.
3. Selecione **Power Automate** no menu de ação de alerta.
4. Na página **fluxos do Power Automate,** selecione o fluxo para editar. Selecione **Editar** no menu de controle de fluxo.
5. Selecione as **configurações de re**  >  **elipses para** alterar uma configuração de componente de fluxo ou **re elipses** Excluir para excluir um componente de  >   fluxo.
6. Selecione **Salvar** e **Feche para** concluir a edição do fluxo.

### <a name="delete-a-power-automate-flow"></a>Excluir um fluxo do Power Automate

Se precisar excluir um fluxo, você usará o controle do **Power Automate** ao trabalhar diretamente em um alerta. Para excluir um fluxo do Power Automate, você deve ser membro de pelo menos um grupo de função de conformidade de comunicação.

Conclua as seguintes etapas para excluir um fluxo do Power Automate:

1. No centro de conformidade do Microsoft 365, vá para Políticas de conformidade de comunicação e selecione a política com o  >   alerta que você deseja analisar.
2. Na política, selecione a guia **Pendente** e selecione um alerta pendente.
3. Selecione **Power Automate** no menu de ação de alerta.
4. Na página **fluxos do Power Automate,** selecione o fluxo a ser excluído. Selecione **Excluir** no menu de controle de fluxo.
5. Na caixa de diálogo de confirmação de exclusão, selecione **Excluir** para remover o fluxo ou selecione **Cancelar** para sair da ação de exclusão.

## <a name="reports-preview"></a>Relatórios (visualização)

O novo **painel Relatórios** é o local central para exibir todos os relatórios de conformidade de comunicação. Os widgets de relatório fornecem uma exibição rápida das informações mais comumente necessárias para uma avaliação geral do status das atividades de conformidade de comunicação. As informações contidas nos widgets de relatório não são exportáveis. Relatórios detalhados fornecem informações detalhadas relacionadas a áreas de conformidade de comunicação específicas e oferecem a capacidade de filtrar, agrupar, classificar e exportar informações durante a revisão.

O **painel Relatórios** contém os seguintes widgets de relatório e links detalhados de relatórios:

- **A política recente corresponde** ao widget: exibe o número de partidas pela política ativa ao longo do tempo.
- **Itens resolvidos por** widget de política: exibe o número de alertas de política de match resolvidos pela política ao longo do tempo.
- **Usuários com a maioria do** widget de política de match: exibe os usuários (ou nomes de usuário anônimos) e o número de diretivas que corresponde a um determinado período.
- **Política com o** widget mais coincidente: exibe as políticas e o número de partidas para um determinado período, classificados de forma mais alta para menor para as combinações.
- **Escalonamentos por** widget de política: exibe o número de escalonamentos por política em um determinado tempo.
- **Configurações de** política e relatório detalhado de status: fornece uma análise detalhada das configurações e das configurações de política, bem como o status geral de cada política (combinações e ações) nas mensagens. Use a *opção Exportar* para criar um . Arquivo CSV que contém os detalhes do relatório.
- **Itens e ações por relatório detalhado** de política: Revisar e exportar itens correspondentes e ações de correção por política. Use a *opção Exportar* para criar um . Arquivo CSV que contém os detalhes do relatório.
- **Item e ações por relatório** detalhado de local: revisar e exportar itens correspondentes e ações de correção por local do Microsoft 365. Use a *opção Exportar* para criar um . Arquivo CSV que contém os detalhes do relatório.

## <a name="audit"></a>Auditoria

Em alguns casos, você deve fornecer informações aos auditores regulamentadores ou de conformidade para provar a supervisão das atividades e comunicações do usuário. Essas informações podem ser um resumo de todas as atividades associadas a uma política organizacional definida ou sempre que uma política de conformidade de comunicação mudar. As políticas de conformidade de comunicação têm trilhas de auditoria internas para preparação completa para auditorias internas ou externas. Históricos detalhados de auditoria de cada ação de criação, edição e exclusão são capturados por suas políticas de comunicação para fornecer a prova de procedimentos de supervisão.

>[!Important]
>A auditoria deve ser habilitada para sua organização antes que os eventos de conformidade de comunicação sejam registrados. Para habilitar a auditoria, consulte [Habilitar o log de auditoria.](communication-compliance-configure.md#step-2-required-enable-the-audit-log)

Para exibir as atividades de atualização da política de conformidade de comunicação, selecione o **controle** Exportar atualizações de política na página principal de qualquer política. Você deve ter as funções de Administrador *Global* ou Administrador de Conformidade de *Comunicação* para exportar as atividades de atualização. Essa ação gera um arquivo de auditoria no formato .csv que contém as seguintes informações:

|**Campo**|**Detalhes**|
|:-----|:-----|
| **CreationDate** | A data em que a atividade de atualização foi executada em uma política. |
| **UserIds** | O usuário que realizou a atividade de atualização em uma política. |
| **Operations** | As operações de atualização executadas na política. |
| **AuditData** | Esse campo é a principal fonte de dados para todas as atividades de atualização de política. Todas as atividades de atualização são registradas e separadas por delimitadores de vírgula. |

Para exibir as atividades de revisão de conformidade de comunicação de uma política, selecione o **controle** de atividades de revisão de exportação na página **Visão** geral de uma política específica. Você deve ter as funções administrador *global* ou administrador de conformidade *de comunicação* para exportar atividades de revisão. Essa ação gera um arquivo de auditoria no formato .csv que contém as seguintes informações:

|**Campo**|**Detalhes**|
|:-----|:-----|
| **CreationDate** | A data em que a atividade de revisão foi executada em uma política. |
| **UserIds** | O usuário que realizou a atividade de revisão em uma política. |
| **Operations** | As operações de revisão executadas na política. |
| **AuditData** | Esse campo é a principal fonte de dados para todas as atividades de revisão de política. Todas as atividades de revisão são gravadas e separadas por delimitadores de vírgula. |

Você também pode exibir as atividades de auditoria no log de auditoria unificado ou com o cmdlet [Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog) PowerShell.

Por exemplo, o exemplo a seguir retorna as atividades para todas as atividades de revisão de supervisão (políticas e regras):

```PowerShell
Search-UnifiedAuditLog -StartDate $startDate -EndDate $endDate -RecordType AeD -Operations SupervisoryReviewTag
```

Este exemplo retorna as atividades de atualização para suas políticas de conformidade de comunicação:

```PowerShell
Search-UnifiedAuditLog -StartDate $startDate -EndDate $endDate -RecordType Discovery -Operations SupervisionPolicyCreated,SupervisionPolicyUpdated,SupervisionPolicyDeleted
```

## <a name="ready-to-get-started"></a>Pronto para começar?

Para configurar a conformidade de comunicação para sua organização do Microsoft 365, confira Configurar a conformidade de [comunicação para sua organização do Microsoft 365.](communication-compliance-configure.md)
