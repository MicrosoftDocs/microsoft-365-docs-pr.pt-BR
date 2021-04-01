---
title: Referência do recurso de conformidade de comunicação
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
ms.openlocfilehash: dbfe1d4aaa821714bac68692d3be38ba8aad8e7f
ms.sourcegitcommit: 7ebed5810480d7c49f8ca03207b5ea84993d253f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "51488218"
---
# <a name="communication-compliance-feature-reference"></a>Referência do recurso de conformidade de comunicação

## <a name="policies"></a>Políticas

>[!Important]
>Não há suporte para usar o PowerShell para criar e gerenciar políticas de conformidade de comunicação. Para criar e gerenciar essas políticas, você deve usar os controles de gerenciamento de política na solução de conformidade de comunicação [do Microsoft 365.](https://compliance.microsoft.com/supervisoryreview)

Você cria políticas de conformidade de comunicação para organizações do Microsoft 365 no centro de conformidade do Microsoft 365. As políticas de conformidade de comunicação definem quais comunicações e usuários estão sujeitos a revisão em sua organização, definem quais condições personalizadas as comunicações devem atender e especificam quem deve fazer avaliações. Os usuários atribuídos à função Administrador de *Conformidade* de Comunicação podem configurar  políticas, e qualquer pessoa que tenha essa função atribuída pode acessar a página de conformidade de comunicação e as configurações globais no centro de conformidade do Microsoft 365. Se necessário, você pode exportar o histórico de modificações para uma política para um arquivo .csv (valores separados por vírgulas) que também inclui o status de alertas pendentes de revisão, itens escalonados e itens resolvidos. As políticas não podem ser renomeadas e podem ser excluídas quando não são mais necessárias.

>[!NOTE]
>As políticas de supervisão criadas no Centro de Conformidade & segurança para assinaturas do Office 365 não podem migrar para o Microsoft 365. Se você estiver migrando de uma assinatura do Office 365 para uma assinatura do Microsoft 365, precisará criar novas políticas de conformidade de comunicação para substituir as políticas de Supervisão existentes.

## <a name="policy-templates"></a>Modelos de política

Os modelos de política são configurações de política pré-definidas que você pode usar para criar políticas rapidamente para resolver cenários comuns de conformidade. Cada um desses modelos tem diferenças em condições e escopo, e todos os modelos usam os mesmos tipos de sinais de verificação. Você pode escolher entre os seguintes modelos de política:

|**Área**|**Modelo de Política**|**Detalhes**|
|:-----|:-----|:-----|
| **Idioma ofensivo e anti-assédio** | Monitorar comunicações para linguagem ofensiva | - Locais: Exchange Online, Microsoft Teams, Yammer, Skype for Business <br> - Direção: Entrada, Saída, Interno <br> - Percentual de revisão: 100% <br> - Condições: classificador de idioma ofensivo |
| **Informação confidencial** | Monitorar comunicações para obter informações confidenciais | - Locais: Exchange Online, Microsoft Teams, Yammer, Skype for Business <br> - Direção: Entrada, Saída, Interno <br> - Percentual de revisão: 10% <br> - Condições: informações confidenciais, padrões de conteúdo in-loco e tipos, opção de dicionário personalizado, anexos maiores do que 1 MB |
| **Conformidade regulamentar** | Monitorar comunicações para obter informações relacionadas à conformidade regulatória financeira | - Locais: Exchange Online, Microsoft Teams, Yammer, Skype for Business <br> - Direção: Entrada, Saída <br> - Percentual de revisão: 10% <br> - Condições: opção de dicionário personalizada, anexos maiores do que 1 MB |
| **Conflito de interesses** | Monitorar comunicações entre dois grupos ou dois usuários para ajudar a evitar conflitos de interesse | - Locais: Exchange Online, Microsoft Teams, Yammer, Skype for Business <br> - Direção: Interna <br> - Percentual de revisão: 100% <br> - Condições: Nenhuma |

As comunicações são examinadas a cada 24 horas a partir do momento em que as políticas são criadas. Por exemplo, se você criar uma política de idioma ofensivo às 11:00, a política reunirá sinais de conformidade de comunicação a cada 24 horas às 11:00 diariamente. Editar uma política não muda desta vez. Para exibir a última data e hora de verificação de uma política, navegue até a *coluna* Última verificação de política na página **Política.** Depois de criar uma nova política, pode levar até 24 horas para exibir a primeira data e hora de verificação de política. A data e a hora da última verificação serão convertidas no fuso horário do sistema local.

## <a name="permissions"></a>Permissões

>[!Important]
>Por padrão, os Administradores Globais não têm acesso aos recursos de conformidade de comunicação. As funções atribuídas nesta etapa são necessárias para que todos os recursos de conformidade de comunicação sejam acessíveis.

Há cinco grupos de função usados para configurar permissões para gerenciar recursos de conformidade de comunicação. Para disponibilizar **a** conformidade de comunicação como uma opção de menu no Centro de conformidade do  Microsoft 365 e para continuar com essas etapas de configuração, você deve ser atribuído aos grupos de função de Administrador de Conformidade de Comunicação ou Conformidade de Comunicação.  Para acessar e gerenciar recursos de conformidade de comunicação após a configuração inicial, os usuários devem ser membros de pelo menos um grupo de função de conformidade de comunicação.

Dependendo de como você deseja gerenciar políticas de comunicação e alertas, você precisará atribuir usuários a grupos de função específicos. Você tem a opção de atribuir usuários com responsabilidades de conformidade diferentes a grupos de função específicos para gerenciar diferentes áreas de recursos de conformidade de comunicação. Ou você pode optar por atribuir todas as contas de usuário para administradores, analistas, investigadores e visualizadores designados ao grupo de função *Conformidade* de Comunicação. Use um único grupo de funções ou vários grupos de função para melhor se ajustar aos seus requisitos de gerenciamento de conformidade.

Escolha entre essas opções de grupo de função ao configurar a conformidade de comunicação:

|**Default management role assignments for this role**|**Permissões de grupo de função**|
|:-----|:-----|
| **Conformidade de comunicação** | Use esse grupo de funções para gerenciar a conformidade de comunicação para sua organização em um único grupo. Ao adicionar todas as contas de usuário para administradores designados, analistas, investigadores e visualizadores, você pode configurar permissões de conformidade de comunicação em um único grupo. Esse grupo de função contém todas as funções de permissão de conformidade de comunicação. Essa configuração é a maneira mais fácil de começar rapidamente com a conformidade de comunicação e é um bom ajuste para organizações que não precisam de permissões separadas definidas para grupos separados de usuários. |
| **Administrador de Conformidade de Comunicação** | Use esse grupo de funções para configurar inicialmente a conformidade de comunicação e posteriormente para segregar os administradores de conformidade de comunicação em um grupo definido. Os usuários atribuídos a esse grupo de funções podem criar, ler, atualizar e excluir políticas de conformidade de comunicação, configurações globais e atribuições de grupo de função. Os usuários atribuídos a esse grupo de funções não podem exibir alertas de mensagens. |
| **Analista de Conformidade de Comunicação** | Use esse grupo para atribuir permissões aos usuários que atuarão como analistas de conformidade de comunicação. Os usuários atribuídos a esse grupo de funções podem exibir políticas nas quais são atribuídos como Revistores, exibir metadados de mensagens (não conteúdo de mensagem), escalonar para outros revisadores ou enviar notificações aos usuários. Os analistas não podem resolver alertas pendentes. |
| **Pesquisador de Conformidade de Comunicação** | Use esse grupo para atribuir permissões aos usuários que atuarão como investigadores de conformidade de comunicação. Os usuários atribuídos a esse grupo de funções podem exibir metadados de mensagens e conteúdo, escalonar para outros revisadores, escalonar para um caso de Descoberta Avançada da Descoberta E, enviar notificações aos usuários e resolver o alerta. |
| **Visualizador de Conformidade de Comunicação** | Use esse grupo para atribuir permissões aos usuários que gerenciarão relatórios de comunicação. Os usuários atribuídos a esse grupo de funções podem acessar todos os widgets de relatório na home page de conformidade de comunicação e podem exibir todos os relatórios de conformidade de comunicação. |

### <a name="for-organizations-using-the-original-permissions-and-role-groups"></a>Para organizações que usam as permissões originais e grupos de função

A nova estrutura do grupo de funções substitui a estrutura inicial do grupo de funções para conformidade de comunicação. Para organizações que já usam a conformidade de comunicação, você precisava receber a função Administrador de Revisão de Supervisão para começar a conformidade de comunicação no centro de conformidade do Microsoft 365. Além disso, você precisava criar um novo grupo de funções para revisadores com as funções Administrador de Revisão de Supervisão, Gerenciamento de Caso, Administrador de Conformidade e Revisão para investigar e remediar mensagens com as combinações de política. Essencialmente, todos os administradores e revisadores estavam em um único grupo de funções e todos tinham as mesmas permissões de acesso e gerenciamento. Com as atualizações mais recentes para a conformidade de comunicação, você deve planejar migrar da estrutura anterior do grupo de funções para a nova estrutura de grupo de funções. O suporte para a estrutura de grupo de função anterior será eliminado em fases.

Para ajudar no planejamento de migração, considere o exemplo a seguir. Atualmente, você tem três tipos de usuários em sua organização, administradores de TI, triagem e revisadores. Esses três tipos de usuários estão na estrutura de grupo de função anterior e são todos membros de um único grupo de funções com as seguintes funções atribuídas:

- Administrador de Revisão de Supervisão
- Gerenciamento de Casos
- Administrador de Conformidade
- Analisar

Para atualizar as funções desses usuários para a nova estrutura de grupo de funções e separar as permissões de acesso e gerenciamento para os usuários, você pode considerar três novos grupos e as novas atribuições de grupo de função associadas:

- **Administradores de** IT : Atribuído ao novo grupo de função administrador de *conformidade* de comunicação.
- **Triagem**: Atribuído ao grupo de função Analista de *Conformidade de* Comunicação.
- **Revisadores**: Atribuído ao novo grupo de função Pesquisador *de Conformidade* de Comunicação.

## <a name="supervised-users"></a>Usuários supervisionados

Antes de começar a usar a conformidade de comunicação, você deve determinar quem precisa de suas comunicações revisadas. Na política, os endereços de email do usuário identificam indivíduos ou grupos de pessoas a supervisionar. Alguns exemplos desses grupos são Grupos do Microsoft 365, listas de distribuição baseadas no Exchange, comunidades do Yammer e canais do Microsoft Teams. Você também pode excluir usuários ou grupos específicos da verificação com um grupo de exclusão específico ou uma lista de grupos. Para obter mais informações sobre tipos de grupos com suporte em políticas de conformidade de comunicação, consulte [Get started with communication compliance](communication-compliance-configure.md#step-3-optional-set-up-groups-for-communication-compliance).

>[!IMPORTANT]
>Os usuários cobertos por políticas de conformidade de comunicação devem ter uma licença de Conformidade do Microsoft 365 E5, uma licença do Office 365 Enterprise E3 com o complemento conformidade avançada ou serem incluídos em uma assinatura do Office 365 Enterprise E5. Se você não tiver um plano Enterprise E5 existente e quiser tentar a conformidade de comunicação, inscreva-se para uma avaliação do [Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).

## <a name="reviewers"></a>Revisores

Ao criar uma política de conformidade de comunicação, você deve determinar quem revisa as mensagens dos usuários supervisionados. Na política, os endereços de email do usuário identificam indivíduos ou grupos de pessoas para revisar as comunicações supervisionadas. Todos os revisadores devem ter caixas de correio hospedadas no Exchange Online e devem ser atribuídas às funções Análise de *Conformidade* de Comunicação ou Investigação *de Conformidade de* Comunicação. Os revisadores (analistas ou investigadores) também devem ter a função *gerenciamento* de caso de conformidade de comunicação atribuída. Quando os revisadores são adicionados a uma política, eles recebem automaticamente uma mensagem de email que os notifica sobre a atribuição à política e fornece links para informações sobre o processo de revisão.

## <a name="groups-for-supervised-users-and-reviewers"></a>Grupos para usuários supervisionados e revisadores

Para simplificar sua instalação, crie grupos para pessoas que precisam de suas comunicações revisadas e grupos para pessoas que revisam essas comunicações. Se você estiver usando grupos, poderá precisar de vários. Por exemplo, se você quiser examinar as comunicações entre dois grupos distintos de pessoas ou se quiser especificar um grupo que não seja supervisionado.

Quando você atribui um grupo de Distribuição na política, a política monitora todos os emails de cada usuário no grupo de Distribuição. Quando você atribui um grupo do Microsoft 365 na política, a política monitora todos os emails enviados a esse grupo, não os emails individuais recebidos por cada membro do grupo.

Adicionar grupos e listas de distribuição a políticas de conformidade de comunicação faz parte das condições gerais e regras definidas, portanto, o número máximo de grupos e listas de distribuição que uma política suporta varia dependendo do número de condições também adicionadas à política. Cada política deve dar suporte a aproximadamente 20 grupos ou listas de distribuição, dependendo do número de condições adicionais presentes na política.

## <a name="supported-communication-types"></a>Tipos de comunicação com suporte

Com as políticas de conformidade de comunicação, você pode optar por examinar mensagens em uma ou mais das seguintes plataformas de comunicação como um grupo ou como fontes autônomas. As comunicações capturadas nessas plataformas são mantidas por sete anos para cada política por padrão, mesmo que os usuários deixem sua organização e suas caixas de correio sejam excluídas.

- **Microsoft Teams**: Comunicações de chat em canais públicos e privados do Microsoft Teams e chats individuais podem ser verificados. Quando os usuários são atribuídos a uma política de conformidade de comunicação com a cobertura do Microsoft Teams selecionada, as comunicações de chat para os usuários são monitoradas automaticamente em todos os Microsoft Teams onde os usuários são membros. A cobertura do Microsoft Teams é incluída automaticamente para modelos de política pré-definidos e é selecionada por padrão no modelo de política personalizada. Os chats do Teams que coincidem com as condições da política de conformidade de comunicação podem levar até 48 horas para ser processado. Use as seguintes configurações de gerenciamento de grupo para supervisionar chats individuais de usuários e comunicações de canal no Teams:

    - **Para comunicações de chat do Teams:** Atribua usuários individuais ou atribua um [grupo de distribuição](https://support.office.com/article/Distribution-groups-E8BA58A8-FAB2-4AAF-8AA1-2A304052D2DE) à política de conformidade de comunicação. Essa configuração é para relações de usuário/chat de um para um ou um para muitos.
    - **Para comunicações do Teams Channel:** Atribua cada canal do Microsoft Teams ou grupo do Microsoft 365 que você deseja verificar que contém um usuário específico para a política de conformidade de comunicação. Se você adicionar o mesmo usuário a outros canais do Microsoft Teams ou grupos do Microsoft 365, adicione esses novos canais e grupos à política de conformidade de comunicação. Se qualquer membro do canal for um usuário  supervisionado dentro de uma política e a direção de entrada estiver configurada em uma política, todas as mensagens enviadas dentro do canal estão sujeitas a análises e possíveis combinações de política (mesmo para usuários no canal que não são explicitamente supervisionados). Por exemplo, o Usuário A é o proprietário ou membro de um canal. Os usuários B e User C são membros do mesmo canal e usam idioma que é corresponde à política de idioma ofensivo que supervisiona apenas o Usuário A. O usuário B e o usuário C criam jogos de política para conversas dentro do canal, mesmo que não sejam supervisionados diretamente na política de idioma ofensivo. As conversas do Teams entre o Usuário B e o Usuário C que estão fora do canal que inclui o Usuário A não estariam sujeitas à política de idioma ofensivo que inclui o Usuário A. Para excluir membros do canal da supervisão quando outros membros do  canal são explicitamente supervisionados, desligue a configuração de direção de comunicação de entrada na política de conformidade de comunicação aplicável.
    - Para comunicações de chat do Teams com ambientes de **email híbridos:** a conformidade de comunicação pode monitorar mensagens de chat para usuários para organizações com uma implantação local do Exchange ou um provedor de email externo que tenha habilitado o Microsoft Teams. Você deve criar um grupo de distribuição para os usuários com caixas de correio locais ou externas para monitorar. Ao criar uma política de conformidade de comunicação,  você atribuirá esse grupo de distribuição como a seleção usuários supervisionados e grupos no assistente de política.

- **Email do Exchange**: As caixas de correio hospedadas no Exchange Online como parte da sua assinatura do Microsoft 365 ou do Office 365 estão qualificadas para verificação de mensagens. As mensagens de email e anexos do Exchange que coincidem com as condições da política de conformidade de comunicação podem levar até 24 horas para ser processadas. Os tipos de anexo com suporte para conformidade de comunicação são os mesmos que os tipos de arquivo com suporte para inspeções de conteúdo da regra de fluxo de emails [do Exchange.](/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection)

- **Yammer**: Mensagens privadas e conversas públicas e anexos associados em comunidades do Yammer podem ser verificados. Quando um usuário é adicionado à política de conformidade de comunicação que inclui o Yammer como um canal definido, as comunicações em todas as comunidades do Yammer de que o usuário é membro são incluídas no processo de verificação. Os chats e anexos do Yammer que coincidem com as condições da política de conformidade de comunicação podem levar até 24 horas para ser processado. O Yammer deve estar no [Modo Nativo para políticas](/yammer/configure-your-yammer-network/overview-native-mode) de conformidade de comunicação para monitorar as comunicações e anexos do Yammer. No Modo Nativo, todos os usuários do Yammer estão no Azure Active Directory (AAD), todos os grupos são Grupos do Office 365 e todos os arquivos são armazenados no SharePoint Online.

- **Skype for Business Online**: Comunicações de chat e anexos associados no Skype for Business Online podem ser supervisionados. Os chats do Skype for Business Online que coincidem com as condições da política de conformidade de comunicação podem levar até 24 horas para ser processada. As conversas de chat supervisionadas são origem de [conversas anteriores salvas no Skype for Business Online](https://support.office.com/article/Find-a-previous-Skype-for-Business-conversation-18892eba-5f18-4281-8c87-fd48bd72e6a2).  Use a seguinte configuração de gerenciamento de grupo para supervisionar as comunicações de chat do usuário no Skype for Business Online:

    - **Para comunicações de chat do Skype for Business Online**: Atribua usuários individuais ou atribua um grupo de [distribuição](https://support.office.com/article/Distribution-groups-E8BA58A8-FAB2-4AAF-8AA1-2A304052D2DE) à política de conformidade de comunicação. Essa configuração é para relações de usuário/chat de um para um ou um para muitos.

- Fontes de terceiros **:** Você pode verificar comunicações de dados importados para caixas de correio em sua organização do Microsoft 365 de fontes de terceiros, como [Instant Bloomberg,](archive-instant-bloomberg-data.md) [Slack,](archive-slack-data.md) [Zoom,](archive-zoommeetings-data.md)SMS e muitas outras. Para uma lista completa de conectores com suporte na conformidade de comunicação, consulte [Arquivar dados de terceiros](archiving-third-party-data.md).

    Você deve configurar um conector de terceiros para sua organização do Microsoft 365 antes de poder atribuir o conector a uma política de conformidade de comunicação. A **seção Fontes de terceiros** do assistente de política de conformidade de comunicação exibe apenas conectores de terceiros configurados no momento.

## <a name="policy-settings"></a>Configurações de política

### <a name="users"></a>Usuários

Você tem a opção de selecionar **Todos os usuários** ou definir usuários específicos em uma política de conformidade de comunicação. Selecionar **Todos os usuários** aplica a política a todos os usuários e a todos os grupos em que qualquer usuário está incluído como membro. A definição de usuários específicos aplica a política aos usuários definidos e a todos os grupos nos quais os usuários definidos são incluídos como membros.

### <a name="direction"></a>Direção

Por padrão, **a condição Direction** é exibida e não pode ser removida. As configurações de direção de comunicação em uma política são escolhidas individualmente ou juntas:

- **Entrada**: Você pode escolher **Entrada para** revisar as comunicações enviadas **às** pessoas que você escolheu para supervisionar.
- **Saída**: Você pode escolher **Saída se** quiser revisar as comunicações enviadas **das** pessoas que você escolheu para supervisionar.
- **Interno**: Você pode escolher **Interno** para revisar as comunicações enviadas **entre** as pessoas identificadas na política.

### <a name="sensitive-information-types"></a>Tipos de informações confidenciais

Você tem a opção de incluir tipos de informações confidenciais como parte da política de conformidade de comunicação. Os tipos de informações confidenciais são tipos de dados pré-definidos ou personalizados que podem ajudar a identificar e proteger números de cartão de crédito, números de conta bancária, números de passaporte e muito mais. Como parte da prevenção contra perda de dados [(DLP),](data-loss-prevention-policies.md)a configuração de informações confidenciais pode usar padrões, proximidade de caracteres, níveis de confiança e até mesmo tipos de dados personalizados para ajudar a identificar e sinalizar o conteúdo que pode ser sensível. Os tipos de informações confidenciais padrão são:

- Financeiro
- Saúde e saúde
- Privacidade
- Tipo de informação personalizado

Para saber mais sobre detalhes de informações confidenciais e os padrões incluídos nos tipos padrão, consulte [Definições de](sensitive-information-type-entity-definitions.md)entidade de tipo de informação confidenciais.

### <a name="custom-keyword-dictionaries"></a>Dicionários de palavras-chave personalizados

Configure dicionários de palavras-chave personalizados (ou lexicons) para fornecer gerenciamento simples de palavras-chave específicas para sua organização ou setor. Os dicionários de palavras-chave suportam até 100 KB de termos (pós-compactação) no dicionário e suportam qualquer idioma. O limite de locatários também é de 100 KB após a compactação. Se necessário, você pode aplicar vários dicionários de palavras-chave personalizados a uma única política ou ter um único dicionário de palavras-chave por política. Esses dicionários são atribuídos em uma política de conformidade de comunicação e podem ser de origem de um arquivo (como uma lista .csv ou .txt) ou de uma lista que você pode importar no Centro de [Conformidade](create-a-keyword-dictionary.md). Use dicionários personalizados quando precisar dar suporte a termos ou idiomas específicos de sua organização e políticas.

### <a name="classifiers"></a>Classificadores

Classificadores integrados e globais verificam mensagens enviadas ou recebidas em todos os canais de comunicação em sua organização para diferentes tipos de problemas de conformidade. Os classificadores usam uma combinação de inteligência artificial e palavras-chave para identificar o idioma em mensagens que provavelmente violarão políticas anti-assédio. Os classificadores integrados atualmente suportam a identificação da palavra-chave de mensagem em vários idiomas:

- Chinês (simplificado)
- Inglês
- Francês
- Alemão
- Italiano
- Japonês
- Português
- Espanhol

Os classificadores globais e de conformidade de comunicação interna verificam as comunicações para termos, imagens e sentimentos para os seguintes tipos de idioma e conteúdo:

- **Ameaça**: verifica se há ameaças para cometer violência ou danos físicos a uma pessoa ou propriedade.
- **Assédio direcionado**: verifica se há conduta ofensiva direcionada a pessoas em relação a raça, cor, religião, origem nacional.
- **Profanidade**: verifica expressões profanas que a maior parte das pessoas se envergonhe.
- **Imagens de adulto**: verifica imagens que são sexualmente explícitas na natureza.
- **Imagens cícilas**: verifica imagens que são sugestivas sexualmente na natureza, mas contêm conteúdo menos explícito do que imagens consideradas Como Adulto.
- **Imagens gory**: verifica imagens que representam a violência e a gore.

Os *classificadores de* imagem Adult , *Racy* e *Gory* verificam arquivos nos formatos .jpeg, .png, .gif e .bmp. O tamanho dos arquivos de imagem deve ter menos de 4 megabytes (MB) e as dimensões das imagens devem ser maiores que 50 x 50 pixels e mais de 50 quilobytes (KB) para que a imagem se qualibiliza para avaliação. A identificação de imagem é suportada para mensagens de email do Exchange Online e canais e chats do Microsoft Teams.

Os classificadores integrados e globais não fornecem uma lista exaustiva de termos ou imagens nessas áreas. Além disso, os padrões de idioma e cultura mudam continuamente e, à luz dessas realidades, a Microsoft reserva o direito de atualizar classificadores a seu critério. Embora os classificadores possam ajudar sua organização no monitoramento dessas áreas, os classificadores não se destinam a fornecer os únicos meios de monitoramento ou endereçamento desse idioma ou imagens da sua organização. Sua organização, não a Microsoft, permanece responsável por todas as decisões relacionadas ao monitoramento, verificação e bloqueio de idiomas e imagens nessas áreas, incluindo a conformidade com a privacidade local e outras leis aplicáveis. A Microsoft incentiva a consultoria com consultoria jurídica antes da implantação e do uso.

>[!NOTE]
>As políticas que usam classificadores inspecionarão e avaliarão mensagens com uma contagem de palavras de seis ou mais. As mensagens que contêm menos de seis palavras não são avaliadas em políticas usando classificadores. Para identificar e tomar medidas em mensagens mais curtas que contenham conteúdo inadequado, recomendamos incluir um dicionário de palavras-chave personalizado para monitoramento de políticas de conformidade de comunicação para esse tipo de conteúdo.

Para obter informações sobre classificadores com treinamento no Microsoft 365, consulte [Getting started with trainable classifiers](classifier-get-started-with.md).

### <a name="optical-character-recognition-ocr-preview"></a>Reconhecimento óptico de caracteres (OCR) (visualização)

Configure políticas de conformidade de comunicação internas ou personalizadas para verificar e identificar texto impresso ou manuscrito de imagens que podem ser inadequadas em sua organização. Os Serviços Cognitivos integrados do Azure e o suporte à verificação óptica para identificar texto em imagens ajudam os analistas e investigadores a detectar e agir em instâncias em que a conduta inadequada pode ser perdida em comunicações que são principalmente não textuais.

Você pode habilitar o OCR (reconhecimento óptico de caracteres) em novas políticas de modelos, políticas personalizadas ou atualizar políticas existentes para expandir o suporte para o processamento de imagens e anexos incorporados. Quando habilitada em uma política criada a partir de um modelo de política, a verificação automática é suportada para imagens incorporadas ou anexadas em emails e mensagens de chat do Microsoft Teams. Para políticas personalizadas, uma ou mais configurações condicionais associadas a palavras-chave, classificadores integrados ou tipos de informações confidenciais devem ser configuradas na política para habilitar a seleção da verificação OCR.

Imagens de 50 KB a 4 MB nos seguintes formatos de imagem são digitalizados e processados:

- .jpg/.jpeg (grupo de especialistas em fotos conjuntas)
- .png (gráficos de rede portáteis)
- .bmp (bitmap)
- .tiff (formato de arquivo de imagem de marca)
- .pdf (formato de documento portátil)

>[!NOTE]
>No momento, a verificação e a extração de imagens .pdf incorporadas e anexadas só são suportadas para mensagens de email.

Ao analisar alertas pendentes para políticas com OCR habilitadas, as imagens identificadas e associadas às condições da política são exibidas como itens filho para alertas associados. Você pode exibir a imagem original para avaliar o texto identificado no contexto com a mensagem original. Pode levar até 48 horas para que as imagens detectadas sejam disponibilizadas com alertas.

### <a name="conditional-settings"></a>Configurações condicionais
<a name="ConditionalSettings"> </a>

As condições escolhidas para a política se aplicam às comunicações de email e de fontes de terceiros em sua organização (como no Instant Bloomberg).

A tabela a seguir explica mais sobre cada condição.
  
|**Condition**|**Como usar essa condição**|
|:-----|:-----|
| **O conteúdo corresponde a qualquer um desses classificadores** | Aplique-se à política quando todos os classificadores são incluídos ou excluídos em uma mensagem. Alguns classificadores são pré-definidos em seu locatário, e os classificadores personalizados devem ser configurados separadamente antes de estar disponíveis para essa condição. Somente um classificador pode ser definido como uma condição em uma política. Para obter mais informações sobre como configurar classificadores, consulte [Learn about trainable classifiers (preview)](classifier-learn-about.md). |
| **O conteúdo contém qualquer um desses tipos de informações confidenciais** | Aplique-se à política quando quaisquer tipos de informações confidenciais são incluídos ou excluídos em uma mensagem. Alguns classificadores são pré-definidos em seu locatário e os classificadores personalizados podem ser configurados separadamente ou como parte do processo de atribuição de condição. Cada tipo de informação sensível escolhido é aplicado separadamente e apenas um desses tipos de informações confidenciais deve ser aplicado à política a ser aplicada à mensagem. Para obter mais informações sobre tipos de informações confidenciais personalizados, [consulte Saiba mais sobre tipos de informações confidenciais.](sensitive-information-type-learn-about.md) |
| **A mensagem é recebida de qualquer um desses domínios**  <br><br> **A mensagem não é recebida de nenhum desses domínios** | Aplique a política para incluir ou excluir domínios específicos ou endereços de email em mensagens recebidas. Insira cada domínio ou endereço de email e separe vários domínios ou endereços de email com uma vírgula. Cada domínio ou endereço de email inserido é aplicado separadamente, apenas um domínio ou endereço de email deve ser aplicado à política a ser aplicada à mensagem. <br><br> Se você quiser examinar todos os emails de um domínio específico, mas quiser excluir mensagens que não precisam de revisão (boletins informativos, comunicados e assim por diante), você deve configurar uma Mensagem não é recebida de qualquer uma dessas condições de **domínios** que exclua o endereço de email (exemplo "newsletter@contoso.com"). |
| **A mensagem é enviada para qualquer um desses domínios**  <br><br> **A mensagem não é enviada a nenhum desses domínios** | Aplique a política para incluir ou excluir domínios específicos ou endereços de email em mensagens enviadas. Insira cada domínio ou endereço de email e separe vários domínios ou endereços de email com uma vírgula. Cada domínio ou endereço de email é aplicado separadamente, apenas um domínio ou endereço de email deve ser aplicado à política a ser aplicada à mensagem. <br><br> Se você quiser examinar todos os emails enviados para um domínio específico, mas quiser excluir mensagens enviadas que não precisam de revisão, configure duas condições: <br> - Uma **mensagem é enviada para qualquer um desses domínios** que define o domínio ("contoso.com"), AND <br> - Uma **mensagem não é enviada a nenhuma destas condições de** domínio que exclua o endereço de email ("subscriptions@contoso.com"). |
| **A mensagem é classificada com qualquer um desses rótulos**  <br><br> **A mensagem não é classificada com nenhum desses rótulos** | Para aplicar a política quando determinados rótulos de retenção são incluídos ou excluídos em uma mensagem. Os rótulos de retenção devem ser configurados separadamente e os rótulos configurados são escolhidos como parte dessa condição. Cada rótulo escolhido é aplicado separadamente (apenas um desses rótulos deve ser aplicado à política a ser aplicada à mensagem). Para obter mais informações sobre rótulos de retenção, [consulte Saiba mais sobre políticas de retenção e rótulos de retenção.](retention.md)|
| **A mensagem contém qualquer uma dessas palavras**  <br><br> **A mensagem não contém nenhuma dessas palavras** | Para aplicar a política quando determinadas palavras ou frases são incluídas ou excluídas em uma mensagem, insira cada palavra separada com uma vírgula. Para frases de duas palavras ou mais, use aspas ao redor da frase. Cada palavra ou frase que você inserir é aplicada separadamente (apenas uma palavra deve ser aplicada à política a ser aplicada à mensagem). Para saber mais sobre como inserir palavras ou frases, consulte a próxima seção [Matching words and phrases to emails or attachments](communication-compliance-feature-reference.md#Matchwords).|
| **Attachment contém qualquer uma dessas palavras**  <br><br> **O anexo não contém nenhuma dessas palavras** | Para aplicar a política quando determinadas palavras ou frases são incluídas ou excluídas em um anexo de mensagem (como um documento do Word), insira cada palavra separada com uma vírgula. Para frases de duas palavras ou mais, use aspas ao redor da frase. Cada palavra ou frase que você inserir é aplicada separadamente (apenas uma palavra deve ser aplicada à política a ser aplicada ao anexo). Para saber mais sobre como inserir palavras ou frases, consulte a próxima seção [Matching words and phrases to emails or attachments](communication-compliance-feature-reference.md#Matchwords).|
| **Attachment é qualquer um desses tipos de arquivo**  <br><br> **O anexo não é nenhum desses tipos de arquivo** | Para supervisionar comunicações que incluam ou excluam tipos específicos de anexos, insira as extensões de arquivo (como .exe ou .pdf). Se você quiser incluir ou excluir várias extensões de arquivo, insira-as em linhas separadas. Somente uma extensão de anexo deve corresponder à política a ser aplicada.|
| **Tamanho da mensagem é maior que**  <br><br> **O tamanho da mensagem não é maior do que** | Para revisar mensagens com base em um determinado tamanho, use essas condições para especificar o tamanho máximo ou mínimo que uma mensagem pode ter antes de ser submetida à revisão. Por exemplo, se  você especificar o tamanho da mensagem é maior que \> **1,0 MB**, todas as mensagens de 1,01 MB ou maiores estão sujeitas a revisão. Você pode optar por bytes, kilobytes, megabytes ou gigabytes para essa condição.|
| **O anexo é maior do que**  <br><br> **O anexo não é maior do que** | Para revisar mensagens com base no tamanho de seus anexos, especifique o tamanho máximo ou mínimo que um anexo pode ter antes que a mensagem e seus anexos sejam sujeitos à revisão. Por exemplo, se você especificar **Attachment** é maior que 2,0 MB , todas as mensagens com \> anexos de 2,01 MB ou superior estão sujeitas a revisão. Você pode optar por bytes, kilobytes, megabytes ou gigabytes para essa condição.|
   
#### <a name="matching-words-and-phrases-to-emails-or-attachments"></a>Palavras e frases correspondentes a emails ou anexos
<a name="Matchwords"> </a>

Cada palavra que você inserir e separar com uma vírgula é aplicada separadamente (apenas uma palavra deve ser aplicada à condição de política a ser aplicada ao email ou anexo). Por exemplo, vamos usar a condição, **Message** contém qualquer uma dessas palavras , com as palavras-chave "banker", "confidential" e "insider trading" separadas por uma vírgula (banqueiro, confidencial,"insider trading"). A política se aplica a qualquer mensagem que inclua a palavra "banqueiro", "confidencial" ou a frase "insider trading". Apenas uma destas palavras ou frases deve ocorrer para que se aplique a condição dessa política. As palavras na mensagem ou anexo devem corresponder exatamente ao que você inserir.

>[!IMPORTANT]
>Ao importar um arquivo de dicionário personalizado, cada palavra ou frase deve ser separada com um retorno de carro e em uma linha separada. <br> Por exemplo: <br><br>
>*banker* <br>
>*confidencial* <br>
>*insider trading*

Para verificar mensagens de email e anexos para [](create-test-tune-dlp-policy.md) as mesmas palavras-chave, crie uma política de prevenção contra perda de dados com um dicionário de palavras-chave personalizado para os termos que você deseja examinar nas mensagens. [](create-a-keyword-dictionary.md) Essa configuração de política identifica palavras-chave definidas que aparecem na mensagem de email **OU** no anexo de email. Usar as configurações de política condicional padrão *(* Message contém qualquer uma dessas palavras e *Attachment* contém qualquer uma  dessas palavras ) para identificar termos em mensagens e em anexos exige que os termos sejam presentes na mensagem e no anexo.
  
#### <a name="enter-multiple-conditions"></a>Insira várias condições

Se você inserir várias condições, o Microsoft 365 usará todas as condições em conjunto para determinar quando aplicar a política de conformidade de comunicação a itens de comunicação. Quando você configura várias condições, todas as condições devem ser atendidas para que a política seja aplicada, a menos que você insira uma exceção. Por exemplo, você precisa de uma política que se aplique se uma mensagem contiver a palavra "trade" e for maior que 2 MB. No entanto, se a mensagem também contiver as palavras "Aprovado pela Contoso financeira", a política não deverá ser aplicada. Neste exemplo, as três condições seriam definidas da seguinte forma:
  
- **A mensagem contém qualquer uma dessas palavras**, com a palavra-chave "trade"
- **O tamanho da mensagem é maior do** que , com o valor 2 MB
- **A mensagem não contém nenhuma dessas palavras**, com as palavras-chave "Aprovado pela equipe financeira da Contoso"

### <a name="review-percentage"></a>Porcentagem de revisão

Se você quiser reduzir a quantidade de conteúdo a ser revisado, especifique uma porcentagem de todas as comunicações governadas por uma política de conformidade de comunicação. Uma amostra aleatória de conteúdo em tempo real é selecionada a partir da porcentagem total de conteúdo que corresponde às condições de política escolhidas. Se você quiser que os revisadores revisem todos os itens, você pode configurar **100%** em uma política de conformidade de comunicação.

## <a name="privacy"></a>Privacidade

Proteger a privacidade de usuários que possuem jogos de política é importante e pode ajudar a promover a objetividade em análises de análise e investigação de dados para alertas de conformidade de comunicação. Essa configuração se aplica apenas aos nomes de usuário exibidos na solução de conformidade de comunicação. Ele não afeta como os nomes são exibidos em outras soluções de conformidade ou centro de administração.

Para usuários com uma combinação de conformidade de comunicação, você pode escolher uma das seguintes configurações em **Configurações de conformidade de comunicação:**

- **Mostrar versões** anonimizadas de nomes de usuário  : os nomes de usuário são anonimizados para impedir que os usuários no grupo de função analista de conformidade de comunicação veja quem está associado a alertas de política. Os usuários do grupo *de função Pesquisador de Conformidade* de Comunicação sempre verão nomes de usuário, não as versões anônimas. Por exemplo, um usuário "Grace Taylor" apareceria com um pseudônimo aleatório, como "AnonIS8-988" em todas as áreas da experiência de conformidade de comunicação. A escolha dessa configuração manterá todos os usuários com as políticas atuais e anteriores e se aplicará a todas as políticas. As informações do perfil do usuário nos detalhes do alerta de conformidade de comunicação não estarão disponíveis quando essa opção for escolhida. No entanto, os nomes de usuário são exibidos ao adicionar novos usuários a políticas existentes ou ao atribuir usuários a novas políticas. Se você optar por desativar essa configuração, os nomes de usuário serão exibidos para todos os usuários que tenham as configurações de política atual ou passada.
- **Não mostre versões anonimizadas** de nomes de usuário : os nomes de usuário são exibidos para todas as versões atuais e passadas de políticas para alertas de conformidade de comunicação. As informações de perfil de usuário (nome, título, alias e organização ou departamento) são exibidas para o usuário para todos os alertas de conformidade de comunicação.

## <a name="notice-templates"></a>Modelos de aviso

Você pode criar modelos de aviso se quiser enviar aos usuários um aviso de lembrete de email para as partidas de política como parte do processo de resolução de problemas. Os avisos só podem ser enviados para o endereço de email do usuário associado à diretiva que gerou o alerta específico para correção. Ao selecionar um modelo de aviso para aplicar a uma violação de política como parte do fluxo de trabalho de correção, você pode optar por aceitar os valores de campo definidos no modelo ou substituir os campos conforme necessário.

Modelos de avisos são modelos de email personalizados onde você pode definir os seguintes campos de mensagem na área **Configurações de conformidade de** comunicação:

|**Field**|**Required**| **Detalhes** |
|:-----|:-----|:-----|
|**Nome do modelo** | Sim | Nome amigável para o modelo de aviso que você selecionará no fluxo de trabalho de notificação durante a correção, suporta caracteres de texto. |
| **Endereço do remetente**. | Sim | O endereço de um ou mais usuários ou grupos que enviam a mensagem para o usuário com uma combinação de política, selecionado no Active Directory para sua assinatura. |
| **Endereços CC e CC** | Não | Usuários ou grupos opcionais a serem notificados da combinação de política, selecionados no Active Directory para sua assinatura. |
| **Assunto** | Sim | As informações que aparecem na linha de assunto da mensagem suportam caracteres de texto. |
| **Corpo da mensagem** | Sim | Informações que aparecem no corpo da mensagem, suportam valores de texto ou HTML. |

### <a name="html-for-notices"></a>HTML para avisos

Se você quiser criar mais do que uma mensagem de email simples baseada em texto para notificações, você pode criar uma mensagem mais detalhada usando HTML no campo corpo da mensagem de um modelo de aviso. O exemplo a seguir fornece o formato do corpo da mensagem para um modelo básico de notificação de email baseado em HTML:

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

Os filtros de conformidade de comunicação permitem filtrar e classificar mensagens de alerta para ações mais rápidas de investigação e correção. A filtragem está disponível nas guias **Pendentes** e **Resolvidos** para cada política. Para salvar um filtro ou um conjunto de filtros como uma consulta de filtro salva, um ou mais valores devem ser configurados como seleções de filtro. A tabela a seguir descreve detalhes do filtro:

|**Filtro**|**Detalhes**|
|:-----|:-----|
| **Date** | A data em que a mensagem foi enviada ou recebida por um usuário em sua organização. Para filtrar um único dia, selecione um intervalo de datas que começa com o dia para o que você deseja resultados e termine com o dia a seguir. Por exemplo, se você quisesse filtrar os resultados para 20/9/2020, poderia escolher um intervalo de datas de filtro de 20/09/2020-21/09/2020.|
| **Classe File** | A classe da mensagem com base no tipo de mensagem, *mensagem* ou *anexo*. |
| **Tem anexo** | A presença de anexo na mensagem. |
| **Classe Item** | A origem da mensagem com base no tipo de mensagem, email, chat da Equipe da Microsoft, Bloomberg, etc. Para obter mais informações sobre tipos de item comuns e classes de mensagem, consulte [Tipos de Item e Classes de Mensagem.](/office/vba/outlook/concepts/forms/item-types-and-message-classes) |
| **Domínios de destinatário** | O domínio para o qual a mensagem foi enviada. Esse domínio normalmente é seu domínio de assinatura do Microsoft 365 por padrão. |
| **Recipiente** | O usuário para o qual a mensagem foi enviada. |
| **Sender** | A pessoa que enviou a mensagem. |
| **Domínio do remetente** | O domínio que enviou a mensagem. |
| **Tamanho** | O tamanho da mensagem em KB. |
| **Assunto/Título** | O assunto da mensagem ou o título do chat. |
| **Marcas** | As marcas atribuídas a uma mensagem, *questionável,* *compatível* ou *não compatível*. |
| **Escalonado para** | O nome de usuário da pessoa incluída como parte de uma ação de escalonamento de mensagens. |
| **Classificadores** | O nome dos classificadores integrados e personalizados que se aplicam à mensagem. Alguns exemplos *incluem Linguagem Ofensiva,* *Assédio Direcionado,* *Profanidade,* *Ameaça* e muito mais.

## <a name="alert-policies"></a>Políticas de alerta

Depois de configurar uma política, uma política de alerta correspondente é criada automaticamente e alertas são gerados para mensagens que correspondem às condições definidas na política. Por padrão, todos os gatilhos de alerta de diretivas coincidem com um nível de gravidade médio na política de alerta associada. Os alertas são gerados para uma política de conformidade de comunicação quando o nível limite do gatilho de agregação é atendido na política de alerta associada.

Para políticas de conformidade de comunicação, os seguintes valores de política de alerta são configurados por padrão:

|**Gatilho de política de alerta**|**Valor padrão**|
|:-----|:-----|
| Agregação | Agregação simples |
| Limite | 4 atividades |
| Janela | 60 minutos |

>[!Note]
>As configurações de gatilho de limite de política de alerta para atividades suportam um valor mínimo de 3 ou mais para políticas de conformidade de comunicação.

Você pode alterar as configurações padrão para gatilhos no número de atividades, período  para as atividades e para usuários específicos em políticas de alerta na página Políticas de alerta no Centro de Conformidade & Segurança.

### <a name="change-the-severity-level-for-an-alert-policy"></a>Alterar o nível de gravidade de uma política de alerta

Se você quiser alterar o nível de gravidade atribuído em uma política de alerta para uma política de conformidade de comunicação específica, conclua as seguintes etapas:

1. Entre [https://compliance.microsoft.com](https://compliance.microsoft.com) usando credenciais para uma conta de administrador em sua organização do Microsoft 365.

2. No centro de conformidade do Microsoft 365, vá para **Políticas**.

3. Selecione o alerta do Office  **365** na página Políticas para abrir a página Políticas de **Alertas** no Centro de Conformidade e Segurança & do Office **365.**

4. Selecione a caixa de seleção da política de conformidade de comunicação que você deseja atualizar e selecione **Editar política**.

5. Na guia **Descrição,** selecione o menu suspenso **Gravidade** para configurar o nível de alerta de política.

6. Selecione **Salvar** para aplicar o novo nível de gravidade à política.

7. Selecione **Fechar para** sair da página de detalhes da política de alerta.

## <a name="power-automate-flows"></a>Fluxos do Power Automate

[O Microsoft Power Automate é](/power-automate/getting-started) um serviço de fluxo de trabalho que automatiza ações entre aplicativos e serviços. Usando fluxos de modelos ou criados manualmente, você pode automatizar tarefas comuns associadas a esses aplicativos e serviços. Ao habilitar fluxos do Power Automate para conformidade com a comunicação, você pode automatizar tarefas importantes para alertas e usuários. Você pode configurar fluxos do Power Automate para notificar os gerentes quando os usuários têm alertas de conformidade de comunicação e outros aplicativos.

Os clientes com assinaturas do Microsoft 365 que incluem conformidade de comunicação não precisam de licenças adicionais do Power Automate para usar o modelo de Power Automate de conformidade de comunicação padrão recomendado. O modelo padrão pode ser personalizado para dar suporte à sua organização e abranger os principais cenários de conformidade de comunicação. Se você optar por usar recursos premium do Power Automate nesses modelos, crie um modelo personalizado usando o conector de conformidade do Microsoft 365 ou use modelos do Power Automate para outras áreas de conformidade no Microsoft 365, talvez você precise de licenças adicionais do Power Automate.

>[!IMPORTANT]
>Você está recebendo prompts para validação de licença adicional ao testar fluxos do Power Automate? Sua organização pode não ter recebido atualizações de serviço para esse recurso de visualização ainda. As atualizações estão sendo implantadas e todas as organizações com assinaturas do Microsoft 365 que incluem conformidade de comunicação devem ter suporte de licença para fluxos criados a partir dos modelos recomendados do Power Automate até 30 de outubro de 2020.

![Conformidade de comunicação Power Automate](../media/communication-compliance-power-automate.png)

O modelo Power Automate a seguir é fornecido aos clientes para dar suporte à automação de processos para alertas de conformidade de comunicação:

- **Notificar o gerente quando um usuário tiver** um alerta de conformidade de comunicação : Algumas organizações podem precisar ter uma notificação de gerenciamento imediata quando um usuário tiver um alerta de conformidade de comunicação. Quando esse fluxo é configurado e selecionado, o gerente do usuário do caso é enviado uma mensagem de email com as seguintes informações sobre todos os alertas:
    - Política aplicável para o alerta
    - Data/hora do alerta
    - Nível de gravidade do alerta

### <a name="create-a-power-automate-flow"></a>Criar um fluxo do Power Automate

Para criar um fluxo do Power Automate a partir de um modelo padrão recomendado, você usará a opção Gerenciar fluxos do **Power Automate** do controle **Automate** ao trabalhar diretamente em um alerta. Para criar um fluxo do Power Automate com Gerenciar fluxos do **Power Automate,** você deve ser membro de pelo menos um grupo de função de conformidade de comunicação.

Conclua as etapas a seguir para criar um fluxo do Power Automate a partir de um modelo padrão:

1. No Centro de conformidade do Microsoft 365, acesse Políticas de conformidade de comunicação e selecione a política com  >   o alerta que você deseja revisar.
2. Na política, selecione a guia **Pendente** e selecione um alerta pendente.
3. Selecione **Power Automate** no menu ação de alerta.
4. Na página **Power Automate,** selecione um modelo padrão nos modelos de conformidade **de comunicação** que você pode gostar na página.
5. O fluxo lista as conexões incorporadas necessárias para o fluxo e será exibido se os status da conexão estão disponíveis. Se necessário, atualize quaisquer conexões que não sejam exibidas como disponíveis. Selecione **Continuar**.
6. Por padrão, os fluxos recomendados são pré-configurados com a conformidade de comunicação recomendada e os campos de dados de serviço do Microsoft 365 necessários para concluir a tarefa atribuída para o fluxo. Se necessário, personalize os componentes de fluxo usando o controle Mostrar opções **avançadas** e configurando as propriedades disponíveis para o componente de fluxo.
7. Se necessário, adicione quaisquer etapas adicionais ao fluxo selecionando o **botão Nova etapa.** Na maioria dos casos, essa alteração não deve ser necessária para os modelos padrão recomendados.
8. Selecione **Salvar rascunho para** salvar o fluxo para mais configuração posteriormente ou selecione **Salvar** para concluir a configuração do fluxo.
9. Selecione **Fechar** para retornar à página Fluxo do Power Automate. O novo modelo será listado como  um fluxo na guia Meus fluxos e estará disponível automaticamente no controle Power Automate para o usuário que criou o fluxo ao trabalhar com alertas de conformidade de comunicação.

### <a name="share-a-power-automate-flow"></a>Compartilhar um fluxo do Power Automate

Por padrão, os fluxos do Power Automate criados por um usuário estão disponíveis apenas para esse usuário. Para que outros usuários de conformidade de comunicação tenham acesso e usem um fluxo, o fluxo deve ser compartilhado pelo criador do fluxo. Para compartilhar um fluxo, você usará o **controle Power Automate** ao trabalhar diretamente em um alerta.

Para compartilhar um fluxo do Power Automate, você deve ser membro de pelo menos um grupo de função de conformidade de comunicação.
Conclua as etapas a seguir para compartilhar um fluxo do Power Automate:

1. No Centro de conformidade do Microsoft 365, acesse Políticas de conformidade de comunicação e selecione a política com  >   o alerta que você deseja revisar.
2. Na política, selecione a guia **Pendente** e selecione um alerta pendente.
3. Selecione **Power Automate** no menu ação de alerta.
4. Na página **Fluxos do Power Automate,** selecione a **guia Meus fluxos** ou **Fluxos de** equipe.
5. Selecione o fluxo a ser compartilhá-lo e selecione **Compartilhar** no menu opções de fluxo.
6. Na página de compartilhamento de fluxo, insira o nome do usuário ou grupo que você deseja adicionar como proprietário do fluxo.
7. Na caixa **de diálogo Conexão Usada,** selecione **OK** para confirmar que o usuário ou grupo adicionado terá acesso total ao fluxo.

### <a name="edit-a-power-automate-flow"></a>Editar um fluxo do Power Automate

Se você precisar editar um fluxo, usará o controle **Power Automate** ao trabalhar diretamente em um alerta. Para editar um fluxo do Power Automate, você deve ser membro de pelo menos um grupo de função de conformidade de comunicação.

Conclua as etapas a seguir para editar um fluxo do Power Automate:

1. No Centro de conformidade do Microsoft 365, acesse Políticas de conformidade de comunicação e selecione a política com  >   o alerta que você deseja revisar.
2. Na política, selecione a guia **Pendente** e selecione um alerta pendente.
3. Selecione **Power Automate** no menu ação de alerta.
4. Na página **Fluxos do Power Automate,** selecione fluxo para editar. Selecione **Editar** no menu de controle de fluxo.
5. Selecione as **Configurações de reellipse** para alterar uma configuração de componente de fluxo ou  >   **reellipse**  >  **Excluir** para excluir um componente de fluxo.
6. Selecione **Salvar** e **feche para** concluir a edição do fluxo.

### <a name="delete-a-power-automate-flow"></a>Excluir um fluxo do Power Automate

Se você precisar excluir um fluxo, usará o controle **Power Automate** ao trabalhar diretamente em um alerta. Para excluir um fluxo do Power Automate, você deve ser membro de pelo menos um grupo de função de conformidade de comunicação.

Conclua as etapas a seguir para excluir um fluxo do Power Automate:

1. No Centro de conformidade do Microsoft 365, acesse Políticas de conformidade de comunicação e selecione a política com  >   o alerta que você deseja revisar.
2. Na política, selecione a guia **Pendente** e selecione um alerta pendente.
3. Selecione **Power Automate** no menu ação de alerta.
4. Na página **Fluxos do Power Automate,** selecione fluxo a ser excluído. Selecione **Excluir** no menu de controle de fluxo.
5. Na caixa de diálogo de confirmação de exclusão, selecione **Excluir** para remover o fluxo ou selecione **Cancelar** para sair da ação de exclusão.

## <a name="reports"></a>Relatórios

O novo **painel relatórios** é o local central para exibir todos os relatórios de conformidade de comunicação. Os widgets de relatório fornecem uma visão rápida dos insights mais comumente necessários para uma avaliação geral do status das atividades de conformidade de comunicação. As informações contidas nos widgets de relatório não são exportáveis. Relatórios detalhados fornecem informações detalhadas relacionadas a áreas de conformidade de comunicação específicas e oferecem a capacidade de filtrar, agrupar, classificar e exportar informações durante a revisão.

![Painel de relatórios de conformidade de comunicação](../media/communication-compliance-reports-dashboard.png)

O **painel Relatórios** contém os seguintes widgets de relatório e links detalhados de relatórios:

- **Política recente corresponde ao** widget: exibe o número de combinações por política ativa ao longo do tempo.
- **Itens resolvidos por** widget de política: exibe o número de alertas de diretiva de match resolvidos pela política ao longo do tempo.
- **Usuários com a maioria dos** widgets de match de política: exibe os usuários (ou nomes de usuário anônimos) e número de jogos de política para um determinado período.
- **Política com a maioria dos** widgets de corresponde: exibe as políticas e o número de partidas para um determinado período, classificado de mais alto para o mais baixo para as partidas.
- **Escalonamentos por** widget de política: exibe o número de escalonamentos por política ao longo de um determinado tempo.
- **Configurações de política** e relatório detalhado de status: fornece uma análise detalhada das configurações e das configurações da política, bem como o status geral de cada uma das políticas (combinações e ações) em mensagens. Inclui informações de política e como as políticas são associadas a usuários e grupos, locais, porcentagens de revisão, revisadores, status e quando a política foi modificada pela última vez. Use a *opção Exportar* para criar um arquivo .csv contendo os detalhes do relatório.
- **Itens e ações por relatório** detalhado da política: Revisar e exportar itens correspondentes e ações de correção por política. Inclui informações de política e como as políticas são associadas:

    - Itens matched
    - Itens escalonados
    - Itens resolvidos
    - Marcado como compatível
    - Marcado como não compatível
    - Marcado como questionável
    - Revisão de itens pendentes
    - Usuário notificado
    - Caso criado
    
    Use a *opção Exportar* para criar um arquivo .csv contendo os detalhes do relatório.
- **Item e ações por local** relatório detalhado: Revisar e exportar itens correspondentes e ações de correção por local do Microsoft 365. Inclui informações sobre como as plataformas de carga de trabalho são associadas:

    - Itens matched
    - Itens escalonados
    - Itens resolvidos
    - Marcado como compatível
    - Marcado como não compatível
    - Marcado como questionável
    - Revisão de itens pendentes
    - Usuário notificado
    - Caso criado

    Use a *opção Exportar* para criar um arquivo .csv contendo os detalhes do relatório.
- **Atividade por relatório** detalhado do usuário: Revisar e exportar itens correspondentes e ações de correção por usuário. Inclui informações sobre como os usuários estão associados:

    - Itens matched
    - Itens escalonados
    - Itens resolvidos
    - Marcado como compatível
    - Marcado como não compatível
    - Marcado como questionável
    - Revisão de itens pendentes
    - Usuário notificado
    - Caso criado

    Use a *opção Exportar* para criar um arquivo .csv contendo os detalhes do relatório.

## <a name="audit"></a>Auditoria

Em alguns casos, você deve fornecer informações aos auditores regulatórios ou de conformidade para comprovar a supervisão das atividades e comunicações do usuário. Essas informações podem ser um resumo de todas as atividades associadas a uma política organizacional definida ou sempre que uma política de conformidade de comunicação muda. As políticas de conformidade de comunicação têm trilhas de auditoria internas para preparação completa para auditorias internas ou externas. Os históricos de auditoria detalhados de cada ação de criação, edição e exclusão são capturados por suas políticas de comunicação para fornecer uma prova dos procedimentos de supervisão.

>[!Important]
>A auditoria deve ser habilitada para sua organização antes que os eventos de conformidade de comunicação sejam gravados. Para habilitar a auditoria, consulte [Enable the audit log](communication-compliance-configure.md#step-2-required-enable-the-audit-log).

Para exibir as atividades de atualização da política de conformidade de comunicação, selecione o **controle Exportar** atualizações de política na página principal de qualquer política. Você deve receber as funções *Administrador Global* de Conformidade ou Administrador de *Conformidade* de Comunicação para exportar atividades de atualização. Essa ação gera um arquivo de auditoria no formato .csv que contém as seguintes informações:

|**Field**|**Detalhes**|
|:-----|:-----|
| **CreationDate** | A data em que a atividade de atualização foi executada em uma política. |
| **UserIds** | O usuário que realizou a atividade de atualização em uma política. |
| **Operations** | As operações de atualização realizadas na política. |
| **AuditData** | Este campo é a principal fonte de dados para todas as atividades de atualização de política. Todas as atividades de atualização são gravadas e separadas por delimitadores de vírgulas. |

Para exibir atividades de revisão de conformidade de comunicação para uma política, selecione o **controle Exportar** atividades de revisão na página **Visão** geral de uma política específica. Você deve ter as funções *Administrador Global* de Conformidade ou Administrador de Conformidade de *Comunicação* para exportar atividades de revisão. Essa ação gera um arquivo de auditoria no formato .csv que contém as seguintes informações:

|**Field**|**Detalhes**|
|:-----|:-----|
| **CreationDate** | A data em que a atividade de revisão foi executada em uma política. |
| **UserIds** | O usuário que realizou a atividade de revisão em uma política. |
| **Operations** | As operações de revisão realizadas na política. |
| **AuditData** | Este campo é a principal fonte de dados para todas as atividades de revisão de política. Todas as atividades de revisão são gravadas e separadas por delimitadores de vírgulas. |

Você também pode exibir atividades de auditoria no log de auditoria unificado ou com o cmdlet [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog) PowerShell. Para saber mais sobre políticas de retenção de log de auditoria, consulte [Gerenciar políticas de retenção de log de auditoria.](audit-log-retention-policies.md)

Por exemplo, o exemplo a seguir retorna as atividades de todas as atividades de revisão de supervisão (políticas e regras):

```PowerShell
Search-UnifiedAuditLog -StartDate $startDate -EndDate $endDate -RecordType AeD -Operations SupervisoryReviewTag
```

Este exemplo retorna as atividades de atualização para suas políticas de conformidade de comunicação:

```PowerShell
Search-UnifiedAuditLog -StartDate $startDate -EndDate $endDate -RecordType Discovery -Operations SupervisionPolicyCreated,SupervisionPolicyUpdated,SupervisionPolicyDeleted
```

Este exemplo retorna atividades que corresponderem às políticas atuais de conformidade de comunicação:

```PowerShell
Search-UnifiedAuditLog -StartDate $startDate -EndDate $endDate -Operations SupervisionRuleMatch 
```

As correspondências da política de conformidade de comunicação são armazenadas em uma caixa de correio de supervisão para cada política. Em alguns casos, talvez seja necessário verificar o tamanho da sua caixa de correio de supervisão para uma política para garantir que você não está se aproximando do limite atual de 50 GB. Se o limite de caixa de correio for atingido, as correspondências de política não serão capturadas e você precisará criar uma nova política (com as mesmas configurações) para continuar a capturar correspondências para as mesmas atividades.

Para verificar o tamanho de uma caixa de correio de supervisão para uma política, conclua o seguinte:

1. Use o cmdlet [Connect-ExchangeOnline](/powershell/module/exchange/connect-exchangeonline) no módulo Do PowerShell V2 do Exchange Online para se conectar ao PowerShell do Exchange Online usando a autenticação moderna.
2. Execute o seguinte no PowerShell:

    ```PowerShell
    ForEach ($p in Get-SupervisoryReviewPolicyV2 | Sort-Object Name) 
    {
       "<Name of your communication compliance policy>: " + $p.Name
       Get-MailboxStatistics $p.ReviewMailbox | ft ItemCount,TotalItemSize
    }
    ```

## <a name="transitioning-from-supervision-in-office-365"></a>Transição da Supervisão no Office 365

As organizações que usam políticas de supervisão no Office 365 devem planejar imediatamente a transição para políticas de conformidade de comunicação no Microsoft 365 e precisam entender esses pontos importantes:

- A solução de supervisão no Office 365 foi totalmente substituída pela solução de conformidade de comunicação no Microsoft 365. Recomendamos a criação de novas políticas em conformidade com a comunicação que tenham as mesmas configurações que as políticas de supervisão existentes para usar as novas melhorias de investigação e correção.
- As mensagens salvas em supervisão nas combinações de política do Office 365 não podem ser movidas ou compartilhadas em conformidade com a comunicação no Microsoft 365.
- Para organizações com ambas as soluções usadas lado a lado durante o processo de transição, as políticas usadas em cada solução devem ter nomes de política exclusivos. Grupos e dicionários de palavras-chave personalizados podem ser compartilhados entre soluções durante um período de transição.

Para obter informações de aposentadoria para supervisão no Office 365, consulte o Roteiro do [Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap) para obter detalhes.

## <a name="ready-to-get-started"></a>Pronto para começar?

Para configurar a conformidade de comunicação para sua organização do Microsoft 365, consulte [Configure communication compliance for your Microsoft 365 organization](communication-compliance-configure.md).
