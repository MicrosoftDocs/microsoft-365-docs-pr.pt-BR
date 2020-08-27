---
title: Referência do recurso de conformidade de comunicação
description: Referência de recurso para conformidade de comunicação no Microsoft 365. Saiba mais detalhes e especificações de cada um dos componentes de recurso.
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
ms.openlocfilehash: 5fe8e01e24f38ddd62649349575bd38ec37ccae4
ms.sourcegitcommit: b144e8ba1ab0c40fa7e0e8e893b5cb44aa2d8243
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2020
ms.locfileid: "47282669"
---
# <a name="communication-compliance-feature-reference"></a>Referência do recurso de conformidade de comunicação

## <a name="policies"></a>Políticas

>[!Important]
>Não há suporte para o uso do PowerShell para criar e gerenciar políticas de conformidade de comunicação. Para criar e gerenciar essas políticas, você deve usar os controles de gerenciamento de políticas na [solução de conformidade de comunicação do Microsoft 365](https://compliance.microsoft.com/supervisoryreview).

Você cria políticas de conformidade de comunicação para organizações do Microsoft 365 no centro de conformidade da Microsoft 365. As políticas de conformidade de comunicação definem quais comunicações e usuários estão sujeitos a revisar em sua organização, definir quais condições personalizadas as comunicações devem atender e especificar quem deve fazer revisões. Os usuários atribuídos à função de *administrador de conformidade de comunicação* podem configurar políticas e qualquer pessoa que tenha essa função atribuída pode acessar a página conformidade de **comunicação** e as configurações globais no centro de conformidade da Microsoft 365. Se necessário, você pode exportar o histórico de modificações para uma política para um arquivo. csv que também inclui o status de alertas pendentes de revisão, itens escalonados e itens resolvidos. As políticas não podem ser renomeadas e podem ser excluídas quando não forem mais necessárias.

>[!NOTE]
>Políticas de supervisão criadas no centro de segurança & conformidade para assinaturas do Office 365 não podem migrar para a Microsoft 365. Se você estiver migrando de uma assinatura do Office 365 para uma assinatura do Microsoft 365, será necessário criar novas políticas de conformidade de comunicação para substituir as políticas de supervisão existentes.

## <a name="policy-templates"></a>Modelos de política

Os modelos de política são configurações de política predefinidas que você pode usar para criar rapidamente políticas para lidar com cenários comuns de conformidade. Cada um desses modelos tem diferenças em condições e escopo, e todos os modelos usam os mesmos tipos de sinais de verificação. Você pode escolher entre os seguintes modelos de política:

|**Área**|**Modelo de política**|**Detalhes**|
|:-----|:-----|:-----|
| **Linguagem ofensiva e antiassédio** | Monitorar comunicações para linguagem ofensiva | -Locais: Exchange Online, Microsoft Teams, Yammer, Skype for Business <br> -Direction: entrada, saída, interna <br> – Porcentagem de revisão: 100% <br> -Condições: classificador de idiomas ofensivo |
| **Informação confidencial** | Monitorar as comunicações para informações confidenciais | -Locais: Exchange Online, Microsoft Teams, Yammer, Skype for Business <br> -Direction: entrada, saída, interna <br> – Porcentagem de revisão: 10% <br> -Condições: informações confidenciais, padrões de conteúdo prontos e tipos, opção de dicionário personalizado, anexos com mais de 1 MB |
| **Conformidade normativa** | Monitorar as comunicações para informações relacionadas à conformidade normativa financeira | -Locais: Exchange Online, Microsoft Teams, Yammer, Skype for Business <br> -Direction: entrada, saída <br> – Porcentagem de revisão: 10% <br> -Condições: opção de dicionário personalizado, anexos com mais de 1 MB |

## <a name="permissions-preview"></a>Permissões (visualização)

Há cinco funções usadas para configurar permissões para gerenciar recursos de conformidade de comunicação. Para tornar a **conformidade de comunicação** disponível como uma opção de menu no centro de conformidade do Microsoft 365, você deve receber a função de administrador de conformidade de *comunicação* .

Dependendo de como você deseja gerenciar políticas e alertas de comunicação, você precisará criar um ou mais novos grupos de função para administradores, revisores e investigadores. Você tem a opção de atribuir usuários a grupos de função específicos para gerenciar diferentes conjuntos de recursos de conformidade de comunicação. Ou você pode decidir criar um grupo de função e atribuir todas as funções de conformidade de comunicação ao grupo. Crie um único grupo de função ou vários grupos para atender melhor aos seus requisitos de gerenciamento de conformidade.

Escolha uma destas opções de função ao configurar seus grupos de função de conformidade de comunicação:

|**Função**|**Permissões de função**|
|:-----|:-----|
| **Administração de conformidade de comunicação** | Os usuários atribuídos a essa função podem criar, ler, atualizar e excluir políticas de conformidade de comunicação, configurações globais e atribuições de grupos de função. Os usuários atribuídos a essa função não podem exibir alertas de mensagem. |
| **Análise de conformidade de comunicação** | Os usuários atribuídos a essa função podem exibir as políticas em que foram atribuídas como revisores, Exibir metadados de mensagem (não o conteúdo da mensagem), escalonar para revisores adicionais ou enviar notificações aos usuários. Os analistas não podem resolver alertas pendentes. |
| **Investigação de conformidade de comunicação** | Os usuários atribuídos a essa função podem exibir metadados e conteúdo de mensagens, escalonar para revisores adicionais, escalonar para uma ocorrência de descoberta eletrônica avançada, enviar notificações aos usuários e resolver o alerta. |
| **Visualizador de conformidade de comunicação** | Os usuários atribuídos a essa função podem acessar todos os widgets de relatório na home page de conformidade de comunicação e podem exibir todos os relatórios de conformidade de comunicação. |
| **Gerenciamento de casos de conformidade de comunicação** | Os usuários atribuídos a essa função podem gerenciar casos e agir em alertas. Essa função é necessária para criar grupos de funções personalizados para administradores, analistas e investigadores. Os grupos personalizados para visualizadores não precisam dessa função atribuída. |

## <a name="supervised-users"></a>Usuários supervisionados

Antes de começar a usar a conformidade de comunicação, você deve determinar quem precisa de suas comunicações revisadas. Na política, os endereços de email do usuário identificam pessoas ou grupos de pessoas para supervisionar. Alguns exemplos desses grupos são grupos da Microsoft 365, listas de distribuição baseadas no Exchange, comunidades do Yammer e canais do Microsoft Teams. Você também pode excluir usuários ou grupos específicos da verificação com um grupo de exclusão específico ou uma lista de grupos.

>[!IMPORTANT]
>Os usuários cobertos por políticas de conformidade de comunicação devem ter uma licença de conformidade do Microsoft 365 e5, uma licença do Office 365 Enterprise E3 com o complemento de conformidade avançada ou ser incluído em uma assinatura do Office 365 Enterprise e5. Se você não tem um plano Enterprise E5 existente e deseja tentar a conformidade de comunicação, pode [se inscrever para uma avaliação do Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).

## <a name="reviewers"></a>Revisores

Ao criar uma política de conformidade de comunicação, você deve determinar quem revisa as mensagens dos usuários supervisionados. Na política, os endereços de email do usuário identificam pessoas ou grupos de pessoas para analisar comunicações supervisionadas. Todos os revisores devem ter caixas de correio hospedadas no Exchange Online e devem ser atribuídas às funções de *análise de conformidade de Comunicação* ou investigação de conformidade de *comunicação* . Os revisores (analistas ou investigadores) também devem ter a função de *Gerenciamento de casos de conformidade de comunicação* atribuída. Quando os revisores são adicionados a uma política, eles recebem automaticamente uma mensagem de email que os notifica da atribuição à política e fornece links para informações sobre o processo de revisão.

## <a name="groups-for-supervised-users-and-reviewers"></a>Grupos de usuários e revisores supervisionados

Para simplificar a configuração, crie grupos para pessoas que precisam de suas comunicações revisadas e grupos para pessoas que revisam essas comunicações. Se você estiver usando grupos, talvez precise de vários. Por exemplo, se você quiser examinar as comunicações entre dois grupos distintos de pessoas ou se quiser especificar um grupo que não é supervisionado.

Quando você atribui um grupo de distribuição na política, a política monitora todos os emails de cada usuário no grupo de distribuição. Quando você atribui um grupo do Microsoft 365 na política, a política monitora todos os emails enviados para esse grupo, não os emails individuais recebidos por cada membro do grupo.

A adição de grupos e listas de distribuição a políticas de conformidade de comunicação faz parte das condições e dos conjuntos de regras gerais, portanto, o número máximo de grupos e listas de distribuição que uma política oferece suporte varia dependendo do número de condições também adicionadas à política. Cada política deve suportar aproximadamente 20 grupos ou listas de distribuição, dependendo do número de condições adicionais presentes na política.

## <a name="supported-communication-types"></a>Tipos de comunicação com suporte

Com as políticas de conformidade de comunicação, você pode optar por examinar mensagens em uma ou mais das seguintes plataformas de comunicação como um grupo ou como fontes autônomas. As comunicações capturadas entre essas plataformas são mantidas por sete anos para cada política por padrão, mesmo que os usuários saiam da sua organização e suas caixas de correio sejam excluídas.

- **Microsoft Teams**: comunicações de chat em canais públicos e privados do Microsoft Teams e chats individuais podem ser verificados. Quando os usuários são atribuídos a uma política de conformidade de comunicação com a cobertura do Microsoft Teams selecionada, as comunicações de chat para os usuários são automaticamente monitoradas em todas as equipes da Microsoft onde os usuários são membros. A cobertura do Microsoft Teams é automaticamente incluída para modelos de política predefinidos e é selecionada por padrão no modelo de política personalizada. Team chats que correspondem às condições de política de conformidade de comunicação podem levar até 24 horas para serem processadas. Use as configurações de gerenciamento de grupo a seguir para supervisionar chats de usuários individuais e comunicações de canal no Teams:

    - **Para comunicações de chat do teams:** Atribuir usuários individuais ou atribuir um [grupo de distribuição](https://support.office.com/article/Distribution-groups-E8BA58A8-FAB2-4AAF-8AA1-2A304052D2DE) à política de conformidade de comunicação. Essa configuração é para relações de usuário/chat de um-para-um ou um-para-muitos.
    - **Para comunicações de canal do teams:** Atribua todos os canais do Microsoft Teams ou Microsoft 365 que você deseja verificar que contenham um usuário específico à política de conformidade de comunicação. Se você adicionar o mesmo usuário a outros canais do Microsoft Teams ou a grupos do Microsoft 365, certifique-se de adicionar esses novos canais e grupos à política de conformidade de comunicação.
    - **Para comunicações de chat de equipes com ambientes de email híbridos**: a conformidade com comunicação pode monitorar mensagens de chat para usuários de organizações com uma implantação local do Exchange ou um provedor de email externo que tenha habilitado o Microsoft Teams. Você deve criar um grupo de distribuição para os usuários com caixas de correio locais ou externas para monitorar. Ao criar uma política de conformidade de comunicação, você atribuirá esse grupo de distribuição como a seleção de **usuários e grupos supervisionados** no assistente de política.

    >[!IMPORTANT]
    >Você deve arquivar uma solicitação com o suporte da Microsoft para permitir que sua organização Use a interface gráfica do usuário no centro de conformidade de & de segurança para pesquisar dados de chat do teams para usuários locais. Para obter mais informações, consulte [pesquisando caixas de correio baseadas em nuvem para usuários locais](search-cloud-based-mailboxes-for-on-premises-users.md).

Você deve registrar uma solicitação com o suporte da Microsoft para permitir que a sua organização use a interface gráfica do usuário no Centro de Conformidade e Segurança para pesquisar os dados de chat do Teams as caixas de correio baseadas em nuvem para usuários locais.

- **Email do Exchange**: as caixas de correio hospedadas no Exchange Online como parte da sua assinatura do Microsoft 365 ou do Office 365 estão qualificadas para a verificação de mensagens. Mensagens de email e anexos do Exchange as condições de política de conformidade de comunicação podem levar até 24 horas para serem processadas. Os tipos de anexo com suporte para conformidade de comunicação são os mesmos que os [tipos de arquivo suportados para inspeções de conteúdo de regras de fluxo de email do Exchange](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection).

- **Yammer**: mensagens privadas e conversas públicas e anexos associados podem ser verificados. Quando um usuário é adicionado à política de conformidade de comunicação que inclui o Yammer como um canal definido, as comunicações em todas as comunidades do Yammer das quais o usuário é membro estão incluídas no processo de verificação. Chat e anexos do Yammer as condições de política de conformidade de comunicação podem levar até 24 horas para serem processadas. O Yammer deve estar no [modo nativo](https://docs.microsoft.com/yammer/configure-your-yammer-network/overview-native-mode) para políticas de conformidade de comunicação para monitorar comunicações e anexos do Yammer. No modo nativo, todos os usuários do Yammer estão no Azure Active Directory (AAD), todos os grupos são grupos do Office 365 e todos os arquivos são armazenados no SharePoint Online.

- **Skype for Business online**: as comunicações de chat e anexos associados no Skype for Business Online podem ser supervisionados. Conversas do Skype for Business online as condições de política de conformidade de comunicação podem levar até 24 horas para serem processadas. Conversas de chat supervisionadas são originadas de [conversas anteriores salvas no Skype for Business online](https://support.office.com/article/Find-a-previous-Skype-for-Business-conversation-18892eba-5f18-4281-8c87-fd48bd72e6a2).  Use a seguinte configuração de gerenciamento de grupos para supervisionar as comunicações de chat do usuário no Skype for Business Online:

    - **Para comunicações de chat do Skype for Business online**: atribua usuários individuais ou atribua um [grupo de distribuição](https://support.office.com/article/Distribution-groups-E8BA58A8-FAB2-4AAF-8AA1-2A304052D2DE) à política de conformidade de comunicação. Essa configuração é para relações de usuário/chat de um-para-um ou um-para-muitos.

- **Fontes de terceiros**: você pode verificar comunicações de fontes de terceiros para dados importados em caixas de correio em sua organização do Microsoft 365. Os conectores dão suporte aos seguintes recursos de terceiros:

    - [Instant Bloomberg](archive-instant-bloomberg-data.md)
    - [Mensagem da Bloomberg](archive-bloomberg-message-data.md)
    - [Bate-papo ICE](archive-icechat-data.md)

Você deve configurar um conector de terceiros para sua organização do Microsoft 365 antes de poder atribuir o conector a uma política de conformidade de comunicação. A seção de **fontes de terceiros** do assistente de política de conformidade de comunicação só exibe os conectores de terceiros atualmente configurados.

## <a name="transitioning-from-supervision-in-office-365"></a>Transição de supervisão no Office 365

As organizações que usam políticas de supervisão no Office 365 e planejando a transição para políticas de conformidade de comunicação no Microsoft 365 precisam compreender estes pontos importantes:

- Ambas as soluções podem ser usadas lado a lado em sua organização, mas as políticas usadas em cada solução devem ter nomes de política exclusivos. Grupos e dicionários de palavras-chave personalizados podem ser compartilhados entre soluções durante um período de transição.
- Mensagens salvas em supervisão no Office 365 as correspondências de política não podem ser movidas ou compartilhadas na conformidade de comunicação no Microsoft 365.
- A solução de supervisão no Office 365 será totalmente substituída pela solução de conformidade de comunicação no Microsoft 365. Recomendamos a criação de novas políticas de conformidade de comunicação com as mesmas configurações que as políticas de supervisão existentes para usar os novos aprimoramentos de investigação e correção. Ao fazer a transição para conformidade de comunicação no Microsoft 365, você deve planejar a exportação de dados de relatórios da supervisão no Office 365 se tiver requisitos de política de retenção de conformidade interna.

Para obter informações de aposentadoria para supervisão no Office 365, consulte o [mapa de 365 da Microsoft](https://www.microsoft.com/microsoft-365/roadmap) para obter detalhes.

## <a name="policy-settings"></a>Configurações de política

### <a name="users"></a>Usuários

Você tem a opção de selecionar **todos os usuários** ou definir usuários específicos em uma política de conformidade de comunicação. Selecionar **todos os usuários** aplica a política a todos os usuários e a todos os grupos nos quais qualquer usuário está incluído como membro. A definição de usuários específicos aplica a política aos usuários definidos e a todos os grupos dos quais os usuários definidos estão incluídos no como um membro.

### <a name="direction"></a>Direção

Por padrão, a **direção é** a condição é exibida e não pode ser removida. As configurações de direção de comunicação em uma política são escolhidas individualmente ou juntas:

- **Entrada**: você pode escolher a **entrada** para revisar as comunicações enviadas **às** pessoas que você optou por supervisionar.
- **Saída**: você pode escolher **saída** se quiser revisar as comunicações enviadas **de** pessoas que você optou por supervisionar.
- **Interno**: você pode escolher **interno** para revisar as comunicações enviadas **entre** as pessoas que você identificou na política.

### <a name="sensitive-information-types"></a>Tipos de informações confidenciais

Você tem a opção de incluir tipos de informações confidenciais como parte de sua política de conformidade de comunicação. Os tipos de informações confidenciais são tipos de dados predefinidos ou personalizados que podem ajudar a identificar e proteger números de cartão de crédito, números de contas bancárias, números de passaportes e muito mais. Como parte da [DLP (prevenção contra perda de dados)](data-loss-prevention-policies.md), a configuração de informações confidenciais pode usar padrões, proximidade de caracteres, níveis de confiança e até mesmo tipos de dados personalizados para ajudar a identificar e sinalizar conteúdo que possa ser confidencial. Os tipos de informações confidenciais padrão são:

- Financeiro
- Assistência médica e saúde
- Privacidade
- Tipo de informação personalizada

Para saber mais sobre detalhes de informações confidenciais e os padrões incluídos nos tipos padrão, confira [definições de entidade de tipo de informação confidencial](sensitive-information-type-entity-definitions.md).

### <a name="custom-keyword-dictionaries"></a>Dicionários de palavras-chave personalizados

Configure os dicionários de palavras-chave personalizados (ou léxicos) para fornecer gerenciamento simples de palavras-chave específicas para sua organização ou setor. Os dicionários de palavras-chave dão suporte a até 100KB de termos (compressão de post) no dicionário e dão suporte a qualquer idioma. O limite do locatário também é 100KB após a compactação. Se necessário, você pode aplicar vários dicionários de palavras-chave personalizados a uma única política ou ter um único dicionário de palavra-chave por política. Esses dicionários são atribuídos a uma política de conformidade de comunicação e podem ser originados de um arquivo (como uma lista. csv ou. txt) ou de uma lista que pode ser [importada no centro de conformidade](create-a-keyword-dictionary.md). Use os dicionários personalizados quando precisar dar suporte a termos ou idiomas específicos para sua organização e políticas.

### <a name="classifiers"></a>Classificadores

Classificadores internos e classificadores globais verificam mensagens enviadas ou recebidas em todos os canais de comunicação em sua organização para diferentes tipos de problemas de conformidade. Os classificadores usam uma combinação de inteligência artificial e palavras-chave para identificar o idioma das mensagens que provavelmente violam as políticas antiassédio. Atualmente, os classificadores internos oferecem suporte somente a palavras-chave em inglês nas mensagens.

Conformidade de comunicação internas e classificadores globais verificam as comunicações em busca de termos, imagens e informativos para os seguintes tipos de idioma e conteúdo:

- **Ameaça**: verifica se há ameaças para confirmar a violência ou danos físicos a uma pessoa ou a uma propriedade.
- **Assédio almejado**: procura por pessoas de alvo de conduta ofensiva relacionadas à corrida, cor, Religion, origem nacional.
- **Profanação**: procura expressões obscenas que constrangim a maioria das pessoas.
- **Imagens adultas**: verifica imagens que são sexualmente explícitas por natureza.
- **Imagens do Racy**: verifica se há imagens que são obscenas com natureza sexual, mas contêm conteúdo menos explícito do que as imagens consideradas adultas.
- **Imagens do Gory**: verifica se há imagens que representam violência e Gore.

Os classificadores de imagem *adulto*, *Racy*e *Gory* verificam arquivos. JPEG,. PNG,. GIF e. Formatos BMP. O tamanho dos arquivos de imagem deve ser menor do que 4 megabytes (MB) e as dimensões das imagens devem ser maiores que 50x50 pixels e maior que 50 kilobytes (KB) para que a imagem seja qualificada para avaliação. A identificação de imagem é compatível com as mensagens de email do Exchange Online e os canais e chats do Microsoft Teams.

Os classificadores internos e informativos globais não oferecem uma lista abrangente de termos ou imagens nessas áreas. Além disso, os padrões culturais e de idioma mudam continuamente e, em claro, a Microsoft reserva-se o direito de atualizar os classificadores a seu critério. Embora os classificadores possam ajudar sua organização a monitorar essas áreas, os classificadores não são destinados a fornecer o único meio de monitoramento ou endereçamento desses idiomas ou imagens. Sua organização, não a Microsoft, permanece responsável por todas as decisões relacionadas a imagens e idiomas de verificação e bloqueio nessas áreas.

Para obter informações sobre classificadores estagiários no Microsoft 365, confira [introdução aos classificadores estagiários](classifier-getting-started-with.md).

### <a name="conditional-settings"></a>Configurações condicionais
<a name="ConditionalSettings"> </a>

As condições escolhidas para a política se aplicam às comunicações de emails e fontes de terceiros em sua organização (como do Bloomberg ou do DropBox).

A tabela a seguir explica mais sobre cada condição.
  
|**Condição**|**Como usar essa condição**|
|:-----|:-----|
| **O conteúdo corresponde a qualquer um desses classificadores** | Aplica-se à política quando os classificadores são incluídos ou excluídos em uma mensagem. Alguns classificadores são predefinidos no locatário e os classificadores personalizados devem ser configurados separadamente antes de estarem disponíveis para essa condição. Somente um classificador pode ser definido como uma condição em uma política. Para obter mais informações sobre a configuração de classificadores, consulte [classificadores](classifier-getting-started-with.md). |
| **O conteúdo contém qualquer um desses tipos de informações confidenciais** | Aplica-se à política quando qualquer tipo de informação confidencial é incluído ou excluído em uma mensagem. Alguns classificadores são predefinidos no locatário e os classificadores personalizados podem ser configurados separadamente ou como parte do processo de atribuição de condição. Cada tipo de informação confidencial que você escolher será aplicado separadamente e apenas um desses tipos de informações confidenciais deverá ser aplicado à política a ser aplicada à mensagem. Para obter mais informações sobre tipos de informações confidenciais personalizadas, confira [tipos de informações confidenciais personalizados](custom-sensitive-info-types.md). |
| **A mensagem é recebida de qualquer um desses domínios**  <br><br> **A mensagem não é recebida de nenhum desses domínios** | Aplique a política para incluir ou excluir domínios ou endereços de email específicos em mensagens recebidas. Insira cada domínio ou endereço de email e separe vários domínios ou endereços de email com uma vírgula. Cada endereço de domínio ou de email inserido é aplicado separadamente, somente um domínio ou endereço de email deve ser aplicado para que a política seja aplicada à mensagem. <br><br> Se você deseja examinar todos os emails de um domínio específico, mas deseja excluir mensagens que não precisam de revisão (boletins informativos, anúncios e assim por diante), você deve configurar uma **mensagem não é recebida de qualquer uma destas** condições de domínios que exclua o endereço de email (exemplo "newsletter@contoso.com"). |
| **A mensagem é enviada para qualquer um desses domínios**  <br><br> **A mensagem não é enviada a nenhum desses domínios** | Aplique a política para incluir ou excluir domínios ou endereços de email específicos em mensagens enviadas. Insira cada domínio ou endereço de email e separe vários domínios ou endereços de email com uma vírgula. Cada domínio ou endereço de email é aplicado separadamente, apenas um endereço de domínio ou de email deve ser aplicado para que a política seja aplicada à mensagem. <br><br> Se você deseja examinar todos os emails enviados para um domínio específico, mas deseja excluir as mensagens enviadas que não precisam de revisão, você deve configurar duas condições: <br> -Uma **mensagem é enviada a qualquer uma das condições de domínios** que define o domínio ("contoso.com") e <br> -Uma **mensagem não é enviada para qualquer uma dessas condições de domínio** que exclua o endereço de email ("subscriptions@contoso.com"). |
| **A mensagem é classificada com qualquer um desses rótulos**  <br><br> **A mensagem não é classificada com nenhum desses rótulos** | Para aplicar a política quando determinados rótulos de retenção são incluídos ou excluídos em uma mensagem. Os rótulos de retenção devem ser configurados separadamente e os rótulos configurados são escolhidos como parte dessa condição. Cada rótulo escolhido é aplicado separadamente (somente um desses rótulos deve se aplicar à política para aplicar à mensagem). Para obter mais informações sobre rótulos de retenção, consulte [saiba mais sobre políticas de retenção e rótulos de retenção](retention.md).|
| **A mensagem contém qualquer uma destas palavras**  <br><br> **A mensagem não contém nenhuma destas palavras** | Para aplicar a política quando determinadas palavras ou frases forem incluídas ou excluídas em uma mensagem, insira cada palavra separada com uma vírgula. Para frases de duas palavras ou mais, coloque aspas ao redor da frase. Cada palavra ou frase inserida é aplicada separadamente (apenas uma palavra deve ser aplicada à política para ser aplicada à mensagem). Para saber mais sobre como inserir palavras ou frases, consulte a próxima seção [Matching words and phrases to emails or attachments](communication-compliance-feature-reference.md#Matchwords).|
| **O anexo contém qualquer uma destas palavras**  <br><br> **O anexo não contém nenhuma destas palavras** | Para aplicar a política quando determinadas palavras ou frases forem incluídas ou excluídas em um anexo de mensagem (como um documento do Word), insira cada palavra separada com uma vírgula. Para frases de duas palavras ou mais, coloque aspas ao redor da frase. Cada palavra ou frase inserida é aplicada separadamente (apenas uma palavra deve ser aplicada à política a ser aplicada ao anexo). Para saber mais sobre como inserir palavras ou frases, consulte a próxima seção [Matching words and phrases to emails or attachments](communication-compliance-feature-reference.md#Matchwords).|
| **O anexo é qualquer um desses tipos de arquivo**  <br><br> **O anexo não é nenhum desses tipos de arquivo** | Para supervisionar as comunicações que incluem ou excluem tipos específicos de anexos, insira as extensões de arquivo (como. exe ou. pdf). Se você quiser incluir ou excluir várias extensões de arquivo, insira-as em linhas separadas. Somente uma extensão de anexo deve corresponder à política a ser aplicada.|
| **Tamanho da mensagem é maior que**  <br><br> **O tamanho da mensagem não é maior que** | Para revisar mensagens com base em um determinado tamanho, use essas condições para especificar o tamanho máximo ou mínimo que uma mensagem pode ser antes de estar sujeita a revisão. Por exemplo, se você especificar o **tamanho da mensagem é maior que** \> **1,0 MB**, todas as mensagens com 1, 1 MB e maiores estão sujeitas a revisão. Você pode optar por bytes, kilobytes, megabytes ou gigabytes para essa condição.|
| **O anexo é maior que**  <br><br> **O anexo não é maior que** | Para revisar mensagens com base no tamanho de seus anexos, especifique o tamanho máximo ou mínimo que um anexo pode ser antes da mensagem e seus anexos estão sujeitos à revisão. Por exemplo, se você especificar que o **anexo é maior que** \> **2,0 MB**, todas as mensagens com anexos de 2, 1 MB e mais estão sujeitas a revisão. Você pode optar por bytes, kilobytes, megabytes ou gigabytes para essa condição.|
   
#### <a name="matching-words-and-phrases-to-emails-or-attachments"></a>Palavras e frases correspondentes a emails ou anexos
<a name="Matchwords"> </a>

Cada palavra inserida e separada com uma vírgula é aplicada separadamente (apenas uma palavra deve ser aplicada à condição de política a ser aplicada ao email ou anexo). Por exemplo, vamos usar a condição, a **mensagem contém qualquer uma destas palavras**, com as palavras-chave "banco", "confidencial" e "comércio Insider" separada por uma vírgula (banco, confidencial, "comércio Insider"). A política se aplica a qualquer mensagem que inclua a palavra "banco", "confidencial" ou a frase "insider trading". Apenas uma destas palavras ou frases deve ocorrer para que se aplique a condição dessa política. Palavras na mensagem ou anexo devem corresponder exatamente ao que você inserir.

>[!IMPORTANT]
>Ao importar um arquivo de dicionário personalizado, cada palavra ou frase deve ser separada com um retorno de carro e em uma linha separada. <br> Por exemplo: <br><br>
>*banco* <br>
>*acordo* <br>
>*comercialização de insider*

Para verificar as mensagens de email e anexos das mesmas palavras-chave, crie uma [política de prevenção de perda de dados](create-test-tune-dlp-policy.md) com um [dicionário de palavras-chave personalizado](create-a-keyword-dictionary.md) para os termos que você deseja examinar nas mensagens. Essa configuração de política identifica palavras-chave definidas que aparecem na mensagem de email **ou** no anexo de email. Usar as configurações de política condicional padrão (*mensagem contém qualquer uma destas palavras* e *anexos contém qualquer uma destas palavras*) para identificar termos em mensagens e anexos requer os **termos a serem apresentados na mensagem** e no anexo.
  
#### <a name="enter-multiple-conditions"></a>Inserir várias condições

Se você inserir várias condições, a Microsoft 365 usará todas as condições juntas para determinar quando aplicar a política de conformidade de comunicação aos itens de comunicação. Quando você configura várias condições, todas as condições devem ser atendidas para que a política seja aplicada, a menos que você insira uma exceção. Por exemplo, você precisará de uma política que se aplique se uma mensagem contiver a palavra "comércio" e maior que 2 MB. No entanto, se a mensagem também contiver as palavras "aprovadas pela contoso Financial", a política não deverá ser aplicada. Neste exemplo, as três condições seriam definidas da seguinte maneira:
  
- A **mensagem contém qualquer uma destas palavras**, com a palavra-chave "trade"
- O **tamanho da mensagem é maior que**, com o valor 2 MB
- A **mensagem contém nenhuma destas palavras**, com as palavras-chave "aprovadas pela equipe financeira da Contoso"

### <a name="review-percentage"></a>Porcentagem de revisão

Se quiser reduzir a quantidade de conteúdo a ser revisada, você poderá especificar uma porcentagem de todas as comunicações governadas por uma política de conformidade de comunicação. Uma amostra de conteúdo aleatória em tempo real é selecionada da porcentagem total de conteúdo que corresponde às condições de política escolhidas. Se quiser que os revisores Revisem todos os itens, você pode configurar **100%** em uma política de conformidade de comunicação.

## <a name="privacy-preview"></a>Privacidade (versão prévia)

A proteção da privacidade dos usuários que têm correspondências de política é importante e pode ajudar a promover o Objectivity em análises de investigação e análise de dados para alertas de conformidade de comunicação. Essa configuração aplica-se somente aos nomes de usuário exibidos na solução de conformidade de comunicação. Ela não afeta como os nomes são exibidos em outras soluções de conformidade ou centro de administração.

Para usuários com uma correspondência de conformidade de comunicação, você pode escolher uma das configurações a seguir nas **configurações de conformidade de comunicação**:

- **Mostrar versões de nomes de usuário anônimos**: os nomes de usuários são anônimos para impedir que administradores, analistas, investigadores de dados e revisores vejam quem está associado aos alertas de política. Por exemplo, um "Taylor de cortesia" do usuário apareceria com um pseudonym aleatório, como "AnonIS8-988" em todas as áreas da experiência de conformidade de comunicação. A escolha dessa configuração anonymizes todos os usuários com correspondências de política atuais e anteriores e se aplicam a todas as políticas. As informações de perfil de usuário nos detalhes de alerta de conformidade de comunicação não estarão disponíveis quando essa opção for escolhida. No entanto, os nomes de usuários são exibidos ao adicionar novos usuários às políticas existentes ou ao atribuir usuários a novas políticas. Se você optar por desativar essa configuração, os nomes de usuário serão exibidos para todos os usuários que têm correspondências de política atuais ou antigas.
- **Não mostrar versões de nomes de usuário anônimos**: os nomes de usuários são exibidos para todas as correspondências de política atuais e anteriores para alertas de conformidade de comunicação. As informações de perfil de usuário (o nome, título, alias e organização ou departamento) são exibidas para o usuário para todos os alertas e casos de gerenciamento de risco do insider.

## <a name="notice-templates"></a>Modelos de aviso

Você pode criar modelos de aviso se quiser enviar aos usuários um aviso de lembrete por email para correspondências de política como parte do processo de solução de problemas. Os avisos só podem ser enviados ao endereço de email do usuário associado à correspondência de política que gerou o alerta específico para correção. Ao selecionar um modelo de aviso a ser aplicado a uma violação de política como parte do fluxo de trabalho de correção, você pode optar por aceitar os valores de campo definidos no modelo ou substituir os campos conforme necessário.

Avisos os modelos são modelos de email personalizados onde você pode definir os seguintes campos de mensagem na área **configurações de conformidade de comunicação** :

|**Field**|**Required**| **Detalhes** |
|:-----|:-----|:-----|
|**Nome do modelo** | Sim | Nome amigável para o modelo de aviso que você selecionará no fluxo de trabalho notificar durante a correção, suporta caracteres de texto. |
| **Endereço do remetente**. | Sim | O endereço de um ou mais usuários ou grupos que enviam a mensagem para o usuário com uma correspondência de política, selecionado no Active Directory para a sua assinatura. |
| **Endereços CC e Cco** | Não | Usuários ou grupos opcionais a serem notificados sobre a correspondência da política, selecionados no Active Directory para a sua assinatura. |
| **Assunto** | Sim | As informações que aparecem na linha de assunto da mensagem dão suporte a caracteres de texto. |
| **Corpo da mensagem** | Sim | As informações que aparecem no corpo da mensagem dão suporte a valores de texto ou HTML. |

### <a name="html-for-notices"></a>HTML para avisos

Se quiser criar mais de uma mensagem de email baseada em texto simples para notificações, você poderá criar uma mensagem mais detalhada usando HTML no campo corpo da mensagem de um modelo de aviso. O exemplo a seguir fornece o formato de corpo da mensagem para um modelo de notificação de email baseado em HTML básico:

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
>A implementação de atributo HTML href nos modelos de notificação de conformidade de comunicação atualmente suporta apenas aspas simples em vez de aspas duplas para referências de URL.

## <a name="filters"></a>Filtros

Os filtros de conformidade de comunicação permitem que você filtre e classifique mensagens de alerta para investigação e ações de correção mais rápidas. A filtragem está disponível nas guias **pendentes** e **resolvidas** de cada política. Para salvar um filtro ou conjunto de filtro como uma consulta de filtro salva, um ou mais valores devem ser configurados como seleções de filtro. A tabela a seguir descreve os detalhes do filtro:

|**Filter**|**Detalhes**|
|:-----|:-----|
| **Date** | A data em que a mensagem foi enviada ou recebida por um usuário em sua organização. |
| **Classe de arquivo** | A classe da mensagem com base no tipo de mensagem, a *mensagem* ou o *anexo*. |
| **Tem anexo** | A presença de anexo na mensagem. |
| **Classe de item** | A origem da mensagem com base no tipo de mensagem, email, Microsoft Team Chat, Bloomberg, etc. Para obter mais informações sobre tipos de item e classes de mensagens comuns, consulte [tipos de item e classes de mensagens](https://docs.microsoft.com/office/vba/outlook/concepts/forms/item-types-and-message-classes). |
| **Domínios de destinatário** | O domínio para o qual a mensagem foi enviada. Esse domínio normalmente é seu domínio de assinatura do Microsoft 365 por padrão. |
| **Recipiente** | O usuário para o qual a mensagem foi enviada. |
| **Sender** | A pessoa que enviou a mensagem. |
| **Domínio do remetente** | O domínio que enviou a mensagem. |
| **Tamanho** | O tamanho da mensagem em KB. |
| **Assunto/título** | O assunto da mensagem ou o título do chat. |
| **Marcas** | As marcas atribuídas a uma mensagem, seja *questionável*, *compatível*ou *não compatível*. |
| **Escalonado para** | O nome de usuário da pessoa incluída como parte de uma ação de escalonamento de mensagens. |
| **Classificadores** | O nome de classificadores internos e personalizados que se aplicam à mensagem. Alguns exemplos incluem *idioma ofensivo*, *assédio dirigido*, *profanação*, *ameaça*e muito mais.

## <a name="alert-policies"></a>Políticas de alerta

Após configurar uma política, uma política de alerta correspondente é automaticamente criada e os alertas são gerados para mensagens que correspondem às condições definidas na política. Por padrão, todas as políticas correspondem a disparadores de alerta são atribuídos a um nível de severidade de média na política de alerta associada. Os alertas são gerados para uma política de conformidade de comunicação depois que o nível de limite do gatilho de agregação é atendido na política de alerta associada.

Para políticas de conformidade de comunicação, os seguintes valores de política de alerta são configurados por padrão:

|**Gatilho de política de alerta**|**Valor padrão**|
|:-----|:-----|
| Agregação | Agregação simples |
| Limite | 4 atividades |
| Janela | 60 minutos |

>[!Note]
>As configurações do gatilho de limite de política de alerta para atividades dão suporte ao valor mínimo de 3 ou superior para políticas de conformidade de comunicação.

Você pode alterar as configurações padrão para gatilhos no número de atividades, período para as atividades e para usuários específicos em políticas de alerta na página **políticas de alerta** no centro de conformidade de & de segurança.

### <a name="change-the-severity-level-for-an-alert-policy"></a>Alterar o nível de severidade de uma política de alerta

Se quiser alterar o nível de gravidade atribuído em uma política de alerta para uma política de conformidade de comunicação específica, conclua as seguintes etapas:

1. Entre [https://compliance.microsoft.com](https://compliance.microsoft.com) usando as credenciais de uma conta de administrador na sua organização do Microsoft 365.

2. No centro de conformidade da Microsoft 365, vá para **políticas**.

3. Selecione o **alerta do Office 365** na página **políticas** para abrir a página **políticas de alerta** no centro de **conformidade & segurança do Office 365**.

4. Marque a caixa de seleção da política de conformidade de comunicação que você deseja atualizar e, em seguida, selecione **Editar política**.

5. Na guia **Descrição** , selecione o menu suspenso de **gravidade** para configurar o nível de alerta da política.

6. Selecione **salvar** para aplicar o novo nível de severidade à política.

7. Selecione **fechar** para sair da página de detalhes da política de alerta.

## <a name="reports-preview"></a>Relatórios (visualização)

O novo painel de **relatórios** é o local central para exibir todos os relatórios de conformidade de comunicação. Os widgets de relatório fornecem uma visão rápida dos insights mais necessários para uma avaliação geral do status das atividades de conformidade de comunicação. As informações contidas nos widgets de relatório não são exportáveis.

O painel **relatórios** contém os seguintes widgets de relatório:

- **Correspondências de política recentes**: exibe o número de correspondências por política ativa ao longo do tempo.
- **Itens resolvidos pela política**: exibe o número de alertas de correspondência de política resolvidos pela política ao longo do tempo.
- **Usuários com a maioria das correspondências de política**: exibe os usuários (ou nomes de usuário anônimos) e o número de correspondências de política para um determinado período.
- **Política com a maioria das correspondências**: exibe as políticas e o número de correspondências de um determinado período, classificados de maior para mais baixo para correspondências.

## <a name="audit"></a>Auditoria

Em alguns casos, você deve fornecer informações a auditores normativos ou de conformidade para provar a supervisão das atividades e comunicações do usuário. Essas informações podem ser um resumo de todas as atividades associadas a uma política organizacional definida ou a qualquer momento em que uma política de conformidade de comunicação é alterada. As políticas de conformidade de comunicação têm trilhas de auditoria internas para a preparação completa para auditorias internas ou externas. Históricos de auditoria detalhados de cada ação criar, editar e excluir são capturados por suas políticas de comunicação para fornecer provas de procedimentos de supervisão.

>[!Important]
>A auditoria deve estar habilitada para sua organização antes de eventos de conformidade de comunicação serem registrados. Para habilitar a auditoria, confira [habilitar o log de auditoria](communication-compliance-configure.md#step-2-required-enable-the-audit-log).

Para exibir as atividades de atualização de política de conformidade de comunicação, selecione o controle **exportar atualizações de política** na página principal de qualquer política. Você deve receber as funções de administrador *global de administração* ou *conformidade de comunicação* para exportar as atividades de atualização. Esta ação gera um arquivo de auditoria no formato. csv que contém as seguintes informações:

|**Field**|**Detalhes**|
|:-----|:-----|
| **CreationDate** | A data em que a atividade de atualização foi executada em uma política. |
| **UserIds** | O usuário que realizou a atividade de atualização em uma política. |
| **Operations** | As operações de atualização executadas na política. |
| **AuditData** | Este campo é a principal fonte de dados para todas as atividades de atualização de política. Todas as atividades de atualização são registradas e separadas por delimitadores vírgulas. |

Para exibir as atividades de análise de conformidade de comunicação de uma política, selecione o controle **Exportar atividades de revisão** na página **visão geral** de uma política específica. Você deve receber as funções de administrador *global de administração* ou *conformidade de comunicação* para exportar as atividades de revisão. Esta ação gera um arquivo de auditoria no formato. csv que contém as seguintes informações:

|**Field**|**Detalhes**|
|:-----|:-----|
| **CreationDate** | A data em que a atividade de revisão foi executada em uma política. |
| **UserIds** | O usuário que realizou a atividade de revisão em uma política. |
| **Operations** | As operações de análise executadas na política. |
| **AuditData** | Este campo é a fonte de dados principal de todas as atividades de revisão de política. Todas as atividades de revisão são registradas e separadas por delimitadores vírgulas. |

Você também pode exibir as atividades de auditoria no log de auditoria unificada ou com o cmdlet [Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog) do PowerShell.

Por exemplo, o exemplo a seguir retorna as atividades de todas as atividades de análise de supervisão (políticas e regras):

```PowerShell
Search-UnifiedAuditLog -StartDate $startDate -EndDate $endDate -RecordType AeD -Operations SupervisoryReviewTag
```

Este exemplo retorna as atividades de atualização para suas políticas de conformidade de comunicação:

```PowerShell
Search-UnifiedAuditLog -StartDate $startDate -EndDate $endDate -RecordType Discovery -Operations SupervisionPolicyCreated,SupervisionPolicyUpdated,SupervisionPolicyDeleted
```

## <a name="ready-to-get-started"></a>Pronto para começar?

Para configurar a conformidade de comunicação para sua organização do Microsoft 365, confira [Configurar a conformidade de comunicação para a sua organização do microsoft 365](communication-compliance-configure.md).
