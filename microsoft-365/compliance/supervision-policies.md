---
title: Políticas de supervisão
description: Saiba mais sobre como usar políticas de supervisão no Microsoft 365 para capturar comunicações de funcionários para exame por revisadores designados.
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
ms.custom: seo-marvel-apr2020
titleSuffix: Microsoft 365 Compliance
ms.openlocfilehash: 27c4d4603396089cb58cfed192f09d0db70cac5a
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547581"
---
# <a name="supervision-policies"></a>Políticas de supervisão

>[!IMPORTANT]
>Após o lançamento da conformidade de comunicação no Microsoft 365 Compliance em fevereiro de 2020, a Supervisão no Office 365 será retirada. As políticas de supervisão não estarão mais disponíveis para criação, e as políticas serão eventualmente removidas, após um longo período de acesso somente leitura.
>
>Se você usar a Supervisão, esteja ciente de que:
>
>- A partir de 15 de junho de 2020, os locatários não terão a capacidade de criar novas políticas de Supervisão.
>- A partir de 31 de agosto de 2020, as políticas existentes deixarão de capturar novas mensagens.
>- A partir de 26 de outubro de 2020, as políticas existentes serão excluídas.
>
>Incentivamos ativamente os clientes que estão explorando ou usando a [](communication-compliance.md) Supervisão no Office 365 a usar a nova solução de conformidade de comunicação para atender aos requisitos regulatórios ou de monitoramento de comunicações com um conjunto muito mais rico de recursos inteligentes.

As políticas de supervisão no Microsoft 365 permitem que você capture as comunicações dos funcionários para exame pelos revisadores designados. Você pode definir políticas específicas que capturam emails internos e externos, Microsoft Teams ou comunicações de terceiros em sua organização. Os revisadores podem examinar as mensagens para garantir que estão em conformidade com os padrões de mensagens da sua organização e resolvê-las com o tipo de classificação.

Essas políticas também podem ajudar você a superar muitos desafios modernos de conformidade, incluindo:

- Monitorando tipos crescentes de canais de comunicação
- O volume crescente de dados de mensagens
- A imposição & o risco de multas

Em algumas organizações, pode haver uma separação de funções entre o suporte de IT e o grupo de gerenciamento de conformidade. O Microsoft 365 dá suporte à separação entre a configuração do recurso de política de supervisão e a configuração de políticas para comunicações capturadas. Por exemplo, o grupo de IT de uma organização pode ser responsável por configurar permissões de função e grupos para dar suporte a políticas de supervisão configuradas e gerenciadas pela equipe de conformidade da organização.

Para uma rápida visão geral das políticas de Supervisão, consulte o [vídeo de](https://youtu.be/C3Y8WZ7o_dI) política de Supervisão no canal do [Microsoft Mechanics.](https://www.youtube.com/user/OfficeGarageSeries)

## <a name="transitioning-from-supervision"></a>Fazer a transição da supervisão

As organizações que usam políticas de supervisão e planejam fazer a transição para políticas de conformidade de comunicação no [Microsoft 365](communication-compliance.md) precisam entender estes pontos importantes:

- A solução de supervisão no Microsoft 365 será totalmente substituída pela solução de conformidade de comunicação no Microsoft 365. Para organizações que estão fazendo a transição para conformidade de comunicações  a partir de políticas de supervisão, recomendamos criar novas políticas de conformidade de comunicação que tenham as mesmas condições das políticas de supervisão existentes para habilitar novas melhorias de investigação e correção. Ao fazer a transição para a conformidade de comunicação no Microsoft 365, você deve planejar exportar dados de relatórios da supervisão se tiver requisitos de política de retenção de conformidade interna.
- Nesse ínterim, as organizações podem usar as duas soluções lado a lado até a migração completa, mas as políticas usadas em cada solução devem ter nomes de *política exclusivos.* Grupos e dicionários de palavras-chave personalizados podem ser compartilhados entre soluções durante o período de transição.
- As mensagens salvas em supervisão nas políticas do Microsoft 365 não podem ser movidas ou compartilhadas em conformidade de comunicação no Microsoft 365.

Para obter informações sobre a baixa supervisão no Office 365, confira o Mapa do [Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap) para obter detalhes.

## <a name="scenarios-for-supervision-policies"></a>Cenários para políticas de supervisão

As políticas de supervisão podem ajudar no monitoramento das comunicações em sua organização em várias áreas:

- **Políticas corporativas**

    Os funcionários devem estar em conformidade com o uso aceitável, padrões éticos e outras políticas corporativas em todas as comunicações relacionadas aos negócios. As políticas de supervisão podem detectar violações de política e ajudá-lo a tomar ações corretivas para ajudar a mitigar esses tipos de incidentes. Por exemplo, você pode monitorar possíveis violações de recursos humanos, como abuso ou uso de linguagem inadequada ou ofensiva nas comunicações dos funcionários.

- **Gerenciamento de risco**

    As organizações são responsáveis por todas as comunicações distribuídas por toda a infraestrutura e sistemas de rede corporativos. O uso de políticas de supervisão para ajudar a identificar e gerenciar possíveis riscos e exposição legal pode ajudar a minimizar os riscos antes que eles possam danificar as operações corporativas. Por exemplo, você pode monitorar sua organização em busca de comunicações não autorizadas para projetos confidenciais, como aquisições futuras, fusões, divulgação de lucros, reorganizações ou mudanças da equipe de liderança.

- **Conformidade regulatória**

    A maioria das organizações deve estar em conformidade com algum tipo de padrões de conformidade regulamentar como parte de seus procedimentos operacionais normais. Essas regulamentações geralmente exigem que as organizações implementem algum tipo de processo de supervisão ou supervisão para mensagens apropriadas para o setor. A Regra 3110 da FINRA (Autoridade Regulatória do Setor Financeiro) é um bom exemplo de um requisito para que as organizações tenham procedimentos de supervisão no local para monitorar as atividades de seus funcionários e os tipos de empresas nos quais ela se envolve. Outro exemplo pode ser a necessidade de monitorar intermediários em sua organização para proteger contra possíveis atividades de fraudes, trocas de informações internas, colagem ou desassocio. As políticas de supervisão podem ajudar sua organização a atender a esses requisitos fornecendo um processo para monitorar e relatar comunicações corporativas.

## <a name="components"></a>Componentes

### <a name="supervision-policy"></a>Política de supervisão

Você cria políticas de supervisão no Centro de Conformidade. Essas políticas definem quais comunicações e usuários estão sujeitos à revisão em sua organização, definem condições personalizadas que as comunicações devem atender e especificam quem deve realizar avaliações. Os usuários incluídos no grupo de funções Revisão de Supervisão podem configurar políticas e qualquer pessoa que tenha essa função atribuída pode acessar a página Supervisão no Centro de Conformidade.

### <a name="supervised-users"></a>Usuários supervisionados

Antes de começar a usar a supervisão, você deve determinar quem precisa de suas comunicações revisadas. Na política, os endereços de email do usuário identificam indivíduos ou grupos de pessoas a supervisionar. Alguns exemplos desses grupos são Grupos do Microsoft 365, listas de distribuição baseadas no Exchange e canais do Microsoft Teams. Você também pode excluir usuários ou grupos específicos da supervisão com um grupo supervisionado ou uma lista de grupos.

>[!IMPORTANT]
>Os usuários monitorados por políticas de supervisão devem ter uma licença de Conformidade do Microsoft 365 E5, uma licença do Office 365 Enterprise E3 com o complemento de Conformidade Avançada ou estar incluídos em uma assinatura do Office 365 Enterprise E5 ou estar incluídos em uma assinatura do Microsoft 365 E5. Se você não tiver um plano Enterprise E5 existente e quiser tentar a supervisão, inscreva-se para uma avaliação do [Office 365 Enterprise E5.](https://go.microsoft.com/fwlink/p/?LinkID=698279)

### <a name="reviewers"></a>Revisores

Ao criar uma política de supervisão, você deve determinar quem executará as análises das mensagens dos usuários supervisionados. Na política, os endereços de email do usuário identificam indivíduos ou grupos de pessoas para revisar as comunicações supervisionadas. Todos os revisadores devem ter caixas de correio hospedadas no Exchange Online.

### <a name="groups-for-supervised-users-and-reviewers"></a>Grupos para usuários supervisionados e revisadores

Para simplificar sua configuração, crie grupos para pessoas que precisam de suas comunicações revisadas e grupos para pessoas que revisam essas comunicações. Se você estiver usando grupos, talvez precise de vários. Por exemplo, se você quiser monitorar as comunicações entre dois grupos distintos de pessoas ou se quiser especificar um grupo que não seja supervisionado.

Quando você seleciona um grupo do Microsoft 365 para usuários supervisionados, a política monitora o conteúdo da caixa de correio compartilhada e os canais do Microsoft Teams associados ao grupo. Quando você seleciona uma lista de distribuição, a política monitora caixas de correio de usuários individuais.

### <a name="supported-communication-types"></a>Tipos de comunicação com suporte

Com políticas de supervisão, você pode optar por monitorar mensagens em uma ou mais das seguintes plataformas de comunicação:

- **Email do Exchange:** As caixas de correio hospedadas no Exchange Online como parte da sua assinatura do Microsoft 365 estão qualificadas para supervisão de mensagens. Emails e anexos correspondentes às condições da política de supervisão estão disponíveis instantaneamente para monitoramento e em relatórios de supervisão. Os tipos de anexo com suporte para supervisão são os mesmos tipos de arquivo com suporte para inspeções de conteúdo de regras de fluxo de emails [do Exchange.](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection)

- **Microsoft Teams:** As comunicações de chat e anexos associados em canais públicos e privados do Microsoft Teams e chats individuais podem ser supervisionados. Os chats do Teams correspondentes às condições da política de supervisão são processados uma vez a cada 24 horas e ficam disponíveis para monitoramento e em relatórios de supervisão. Use as seguintes configurações de gerenciamento de grupo para supervisionar chats de usuários individuais e comunicações de canal no Teams:

    - **Para supervisão de chat do Teams:** Atribuir usuários individuais ou atribuir um [grupo de distribuição](https://support.office.com/article/Distribution-groups-E8BA58A8-FAB2-4AAF-8AA1-2A304052D2DE) à política de supervisão. Essa configuração é para relações de usuário/chat de 1 para 1 ou 1 para muitos.
    - **Para comunicações do Canal do Teams:** Atribua cada canal do Microsoft Team ou grupo do Microsoft 365 que você deseja monitorar que contenha um usuário específico para a política de supervisão. Se você adicionar o mesmo usuário a outros canais do Microsoft Teams ou grupos do Microsoft 365, certifique-se de adicionar esses novos canais e grupos à política de supervisão.

- **Skype for Business Online:** As comunicações de chat e os anexos associados no Skype for Business Online podem ser supervisionados. Os chats do Skype for Business Online correspondentes às condições da política de supervisão são processados uma vez a cada 24 horas e ficam disponíveis para monitoramento e em relatórios de supervisão. As conversas de chat supervisionadas são fornecidas de [conversas anteriores salvas no Skype for Business Online.](https://support.office.com/article/Find-a-previous-Skype-for-Business-conversation-18892eba-5f18-4281-8c87-fd48bd72e6a2)  Use a seguinte configuração de gerenciamento de grupo para supervisionar as comunicações de chat do usuário no Skype for Business Online:

    - **Para supervisão de bate-papo do Skype for Business Online:** Atribuir usuários individuais ou atribuir um [grupo de distribuição](https://support.office.com/article/Distribution-groups-E8BA58A8-FAB2-4AAF-8AA1-2A304052D2DE) à política de supervisão. Essa configuração é para relações de usuário/chat de 1 para 1 ou 1 para muitos.

- **Fontes de terceiros:** Você pode supervisionar as comunicações de fontes de terceiros (como do Facebook ou do DropBox) para dados importados para caixas de correio em sua organização. [Saiba como importar dados de terceiros.](archiving-third-party-data.md)

As comunicações capturadas nessas plataformas são mantidas por sete anos para cada política por padrão, mesmo que os usuários deixem sua organização e suas caixas de correio sejam excluídas.

### <a name="policy-settings"></a>Configurações de política

#### <a name="direction"></a>Direção

Por padrão, **a condição Direção** é exibida e não pode ser removida. As configurações de direção de comunicação em uma política são escolhidas individualmente ou juntas:

- **Entrada**: você pode escolher **Entrada**  para revisar as comunicações enviadas para as pessoas que você escolheu supervisionar de **pessoas** não incluídas na política.
- **Saída**: Você pode **escolher** Saída se quiser  revisar as comunicações enviadas  das pessoas que você escolheu supervisionar para as pessoas não incluídas na política.
- **Interno**: você pode escolher **Interno** para revisar as comunicações enviadas **entre** as pessoas identificadas na política.

#### <a name="sensitive-information-types"></a>Tipos de informações confidenciais

Você tem a opção de incluir tipos de informações confidenciais como parte da sua política de supervisão. Os tipos de informações confidenciais são tipos de dados pré-definidos ou personalizados que podem ajudar a identificar e proteger números de cartão de crédito, números de contas bancárias, números de passaporte e muito mais. Como parte da prevenção contra perda de dados [(DLP),](data-loss-prevention-policies.md)a configuração de informações confidenciais pode usar padrões, proximidade de caracteres, níveis de confiança e até mesmo tipos de dados personalizados para ajudar a identificar e sinalizar conteúdo que pode ser sensível. Os tipos de informações confidenciais padrão são:

- Financeiro
- Saúde e saúde
- Privacidade
- Tipo de informação personalizada

Para saber mais sobre detalhes de informações confidenciais e os padrões incluídos nos tipos padrão, consulte Definições de entidade de tipo de informações [confidenciais.](sensitive-information-type-entity-definitions.md)

#### <a name="custom-keyword-dictionaries"></a>Dicionários de palavras-chave personalizados

Configure dicionários de palavras-chave personalizados (ou léxicos) para fornecer gerenciamento simples de palavras-chave específicas para sua organização ou setor. Os dicionários de palavras-chave suportam até 100KB de termos (pós-compactação) no dicionário e suportam qualquer idioma. O limite do locatário também é de 100KB após a compactação. Se necessário, você pode aplicar vários dicionários de palavras-chave personalizados a uma única política ou ter um único dicionário de palavras-chave por política. Esses dicionários são atribuídos em uma política de supervisão e podem ser importados de um arquivo (como uma lista .csv ou .txt) ou de uma lista que você pode importar no Centro de [Conformidade.](create-a-keyword-dictionary.md)

#### <a name="offensive-language"></a>Idioma ofensivo

Monitore mensagens de email enviadas ou recebidas em sua organização em busca de idioma ofensivo. O modelo usa uma combinação de aprendizado de máquina, inteligência artificial e palavras-chave para identificar a linguagem em mensagens de email que provavelmente violam políticas antissedio e de abuso. Atualmente, o modelo de idioma ofensivo oferece suporte a palavras-chave em inglês e monitora o corpo das mensagens de email.

>[!NOTE]
>Crie uma [política de prevenção contra](create-test-tune-dlp-policy.md) perda de dados com um dicionário de palavras-chave [personalizado](create-a-keyword-dictionary.md) de termos bloqueados se precisar:
>
>- monitorar as comunicações do Microsoft Teams em sua organização para linguagem ofensiva
>- impedir ou bloquear linguagem ofensiva nas comunicações em sua organização

O modelo não fornece uma lista exaustiva de linguagem ofensiva. Além disso, os padrões de idioma e cultura mudam continuamente e, à luz dessas pessoas, a Microsoft reserva-se o direito de atualizar o modelo a seu critério. Embora o modelo possa ajudar sua organização no monitoramento de linguagem ofensiva, o modelo não se destina a fornecer o único meio de monitoramento ou endereçamento de sua organização. Sua organização, não a Microsoft, permanece responsável por todas as decisões relacionadas ao monitoramento e bloqueio de linguagem ofensiva.

O modelo de linguagem ofensiva monitora emails em busca de opiniões associadas aos seguintes tipos de idioma:

|**Tipo**|**Descrição**|
|:-----|:-----|
| **Profanidades** | Expressões que desamentem a maioria das pessoas. |
| **Insuidades** | Expressões que expressam prejuízo em relação a grupos específicos (por exemplo, corrida, gênero, orientação sexual, deficiência). |
| **100.00** | Expressões que se desmentem, medem, medem ou podem causar violência ou violência. |
| **Expressões mascaradas** | Expressões para as quais o significado ou pronúncia é o mesmo que outro termo mais ofensivo. |

#### <a name="conditional-settings"></a>Configurações condicionais
<a name="ConditionalSettings"> </a>

As condições escolhidas para a política se aplicam às comunicações de email e de fontes de terceiros em sua organização (como do Facebook ou do DropBox).

A tabela a seguir explica mais sobre cada condição.
  
|**Condition**|**Como usar essa condição**|
|:-----|:-----|
| **A mensagem é recebida de qualquer um desses domínios** <br><br> **A mensagem não é recebida de nenhum desses domínios** | Aplicar a política para incluir ou excluir domínios ou endereços de email específicos nas mensagens recebidas. Insira cada domínio ou endereço de email e separe vários domínios ou endereços de email com uma vírgula. Cada domínio ou endereço de email inserido é aplicado separadamente, apenas um domínio ou endereço de email deve ser aplicado para que a política seja aplicada à mensagem. <br><br> Se você deseja monitorar todos os emails de um domínio específico, mas deseja excluir mensagens que não precisam de revisão (boletins informativos, anúncios etc.), você deve configurar a condição de que uma mensagem não é recebida de qualquer uma dessas condições de **domínios** que exclua o endereço de email (exemplo "newsletter@contoso.com"). |
| **A mensagem é enviada a qualquer um desses domínios** <br><br> **A mensagem não é enviada a nenhum desses domínios** | Aplicar a política para incluir ou excluir domínios específicos ou endereços de email em mensagens enviadas. Insira cada domínio ou endereço de email e separe vários domínios ou endereços de email com uma vírgula. Cada domínio ou endereço de email é aplicado separadamente, apenas um domínio ou endereço de email deve ser aplicado para que a política seja aplicada à mensagem. <br><br> Se você quiser monitorar todos os emails enviados para um domínio específico, mas quiser excluir as mensagens enviadas que não precisam de revisão, configure duas condições: <br> - **Uma mensagem é enviada para qualquer uma dessas condições de** domínios que define o domínio ("contoso.com"), AND <br> - **Uma mensagem não é enviada a nenhuma condição desses domínios** que exclua o endereço de email ("subscriptions@contoso.com"). |
| **A mensagem é classificada com qualquer um desses rótulos** <br><br> **A mensagem não é classificada com nenhum desses rótulos** | Para aplicar a política quando determinados rótulos de retenção são incluídos ou excluídos em uma mensagem. Os rótulos de retenção devem ser configurados separadamente e os rótulos configurados são escolhidos como parte dessa condição. Cada rótulo escolhido é aplicado separadamente (somente um desses rótulos deve ser aplicado para que a política seja aplicada à mensagem). Para obter mais informações sobre rótulos de retenção, [consulte Saiba mais sobre políticas de retenção e rótulos de retenção.](retention.md)|
| **A mensagem contém qualquer uma destas palavras** <br><br> **A mensagem não contém nenhuma dessas palavras** | Para aplicar a política quando determinadas palavras ou frases são incluídas ou excluídas em uma mensagem, insira cada palavra ou frase e separe-as com uma vírgula. Cada palavra que você inser é aplicada separadamente (somente uma palavra deve ser aplicada para que a política seja aplicada à mensagem). Para saber mais sobre como inserir palavras ou frases, consulte a próxima seção [Matching words and phrases to emails or attachments](supervision-policies.md#Matchwords).|
| **O anexo contém qualquer uma destas palavras** <br><br> **O anexo não contém nenhuma dessas palavras** | Para aplicar a política quando determinadas palavras ou frases são incluídas ou excluídas em um anexo de mensagem (como um documento do Word), insira cada palavra ou frase e separada com uma vírgula. Cada palavra que você inser é aplicada separadamente (somente uma palavra deve ser aplicada para que a política seja aplicada ao anexo). Para saber mais sobre como inserir palavras ou frases, consulte a próxima seção [Matching words and phrases to emails or attachments](supervision-policies.md#Matchwords).|
| **Anexo é qualquer um desses tipos de arquivo** <br><br> **Anexo não é nenhum desses tipos de arquivo** | Para supervisionar as comunicações que incluem ou excluem tipos específicos de anexos, insira as extensões de arquivo (como .exe ou .pdf). Se você quiser incluir ou excluir várias extensões de arquivo, insira-as em linhas separadas. Somente uma extensão de anexo deve corresponder à política a ser aplicada.|
| **Tamanho da mensagem é maior que** <br><br> **O tamanho da mensagem não é maior que** | Para revisar as mensagens com base em um determinado tamanho, use essas condições para especificar o tamanho máximo ou mínimo que uma mensagem pode ter antes de ser sujeita à revisão. Por exemplo, se  você especificar que o tamanho da mensagem seja maior que \> **1,0 MB,** todas as mensagens com 1,01 MB ou mais estão sujeitas à revisão. Você pode optar por bytes, kilobytes, megabytes ou gigabytes para essa condição.|
| **O anexo é maior que** <br><br> **O anexo não é maior que** | Para revisar mensagens com base no tamanho de seus anexos, especifique o tamanho máximo ou mínimo que um anexo pode ter antes que a mensagem e seus anexos sejam sujeitos à revisão. Por exemplo, se você especificar que **o anexo** é maior que \> **2,0 MB,** todas as mensagens com anexos de 2,01 MB ou mais estão sujeitas à revisão. Você pode optar por bytes, kilobytes, megabytes ou gigabytes para essa condição.|
   
##### <a name="matching-words-and-phrases-to-emails-or-attachments"></a>Palavras e frases correspondentes a emails ou anexos
<a name="Matchwords"></a> Cada palavra que você inser e separa com uma vírgula é aplicada separadamente (somente uma palavra deve ser aplicada para que a condição de política seja aplicada ao email ou anexo). Por exemplo, vamos usar a **condição,** Message contém qualquer uma dessas palavras , com as palavras-chave "gerente" e "informação interna" separadas por uma vírgula (financeiro, troca de informações internas). A política se aplica a qualquer mensagem que inclua a palavra "bancária" ou a frase "informação interna". Apenas uma destas palavras ou frases deve ocorrer para que se aplique a condição dessa política. As palavras na mensagem ou no anexo devem corresponder exatamente ao que você inserir.

Para verificar mensagens de email e anexos em [](create-test-tune-dlp-policy.md) busca das mesmas [](create-a-keyword-dictionary.md) palavras-chave, crie uma política de prevenção contra perda de dados com um dicionário de palavras-chave personalizado para os termos que você deseja monitorar. Essa configuração de política identifica palavras-chave definidas que aparecem na mensagem de email **OU** no anexo de email. Usar as configurações de política condicional *padrão* ( a mensagem contém qualquer uma dessas palavras e *Attachment* contém qualquer  uma dessas palavras ) para identificar termos em mensagens e em anexos exige que os termos estão presentes na mensagem e no anexo.
  
##### <a name="enter-multiple-conditions"></a>Inserir várias condições

Se você inserir várias condições, o Microsoft 365 usará todas as condições juntas para determinar quando aplicar a política aos itens de comunicação. Quando você configura várias condições, todas as condições devem ser atendidas para que a política seja aplicada, a menos que você insira uma exceção. Por exemplo, você precisa de uma política que se aplique se uma mensagem contiver a palavra "comercial" e for maior que 2 MB. No entanto, se a mensagem também contiver as palavras "Aprovada pela Contoso financeira", a política não deverá ser aplicada. Portanto, nesse caso, as três condições seriam as seguinte:
  
- **A mensagem contém qualquer uma destas palavras,** com a palavra-chave "comercial"

- **O tamanho da mensagem é maior que**, com o valor de 2 MB

- **A mensagem não contém nenhuma dessas palavras,** com as palavras-chave "Aprovado pela equipe financeira da Contoso"

#### <a name="review-percentage"></a>Porcentagem de revisão

Se você quiser reduzir a quantidade de conteúdo a ser revisado, poderá especificar uma porcentagem de todas as comunicações controladas por uma política de supervisão. Uma amostra aleatória de conteúdo em tempo real é selecionada na porcentagem total do conteúdo que corresponde às condições de política escolhidas. Se quiser que os revisadores revisem todos os itens, você pode inserir **100%** em uma política de supervisão.

## <a name="monitor--manage"></a>Monitorar & gerenciar

É fácil monitorar os resultados de suas políticas de supervisão e aplicar uma marca de resolução. Você pode ver rapidamente:

- O status dos itens revisados
- Usuários e grupos sob supervisão
- Usuários e grupos designados como revisadores

### <a name="supervision-policy-dashboard"></a>Painel de política de supervisão

Use o painel de política de supervisão para gerenciar os resultados da política de supervisão e resolver itens pendentes. Esse painel permite que os revisadores ex vejam itens que precisam ser revisados, atuem em um item e revisem os resultados de itens revisados e resolvidos anteriormente para cada política de supervisão. Você pode acessar o painel de política de supervisão no Centro de Conformidade em **Supervisão**  >  *sua Política Personalizada*  >  **Aberta.**

#### <a name="dashboard-home"></a>Dashboard Home

A **home** page do painel tem várias seções para ajudá-lo a agir rapidamente em suas políticas de supervisão. Aqui você pode:

- Analisar rapidamente os destaques pendentes e resolvidos da semana
- Ver uma lista dos usuários supervisionados e grupos supervisionados para a política selecionada
- Ver uma lista dos revisadores e analisar as equipes para a política selecionada
- Ver quais plataformas de comunicação têm conteúdo sob supervisão para a política

#### <a name="review-tab"></a>Guia Revisão

A **guia Revisão** é onde os revisadores classificam e resolvem itens identificados pela política selecionada. Aqui você pode:

- Filtrar por itens pendentes, compatíveis, não compatíveis e questionáveis.
- Marque um único item como compatível, não compatível ou questionável. Você também pode gravar um comentário com o item para ajudar a esclarecer a ação de marcação tomada.
- Marque vários itens em massa como compatíveis, não compatíveis ou questionáveis. Você também pode gravar um comentário com vários itens para ajudar a esclarecer a ação de marcação tomada.
- Exibir o histórico da marcação de um único item. Inclui quem resolvido o item, a data e hora da ação, a marca de resolução e quaisquer comentários incluídos.
- Reclassifique os itens revisados anteriormente como compatíveis, não compatíveis ou questionáveis. Você também pode gravar um comentário com um ou vários itens para ajudar a esclarecer a ação de reclassificação tomada.

#### <a name="resolved-items-tab"></a>Guia Itens Resolvidos

A **guia Itens Resolvidos** é onde os revisadores podem exibir todos os itens resolvidos anteriormente para a política selecionada. Aqui você pode:

- Exibir e classificar rapidamente o assunto, o remetente e a data dos itens resolvidos
- Exibir a classificação e o histórico de comentários de qualquer item selecionado

## <a name="reports"></a>Relatórios

Use os relatórios de supervisão para ver a atividade de revisão no nível da política e do revistor. Para cada política, você também pode exibir estatísticas ao vivo sobre o estado atual da atividade de revisão. Você pode usar os relatórios de supervisão para:
  
- Verifique se suas políticas estão funcionando conforme o esperado.
- Descubra quantas comunicações precisam de revisão.
- Descubra quantas comunicações não estão em conformidade e quais estão passando pela revisão. Essas informações podem ajudá-lo a decidir se deve ajustar suas políticas ou alterar o número de revisadores.

### <a name="view-the-supervision-report"></a>Exibir o relatório de Supervisão

1. Entre no Centro [de Conformidade](https://compliance.microsoft.com) com credenciais para uma conta de administrador com permissões para exibir relatórios de supervisão.
2. Vá para o Painel **de Relatórios** ou Supervisão para exibir o widget de relatórios de supervisão para um resumo da atividade de política de supervisão \>  atual. 
3. Selecione o **widget Supervisão** para abrir a página de relatório detalhada.

>[!NOTE]
>Se você não conseguir acessar  a página Relatórios, verifique se você é membro do grupo de funções Revisão de Supervisão, conforme descrito em Tornar a supervisão [disponível em sua organização.](configure-supervision-policies.md) A inclusão nesse grupo de função permite que você crie e gerencie as polícias de supervisão e execute o relatório.
  
### <a name="how-to-use-the-report"></a>Como usar o relatório

Esse relatório lista cada política e o número de comunicações em cada etapa do processo de revisão. Use o relatório para:
  
- Exibir dados para todas as políticas ou políticas específicas.
- Exibir dados agrupados por tipo de marca, revistor ou tipo de mensagem.
- Exportar dados para um arquivo CSV com base na data da atividade, na política e na atividade do revisador.
- Filtrar dados com base na data de atividade, tipo de marca, revistor e tipo de mensagem.

Veja um detalhamento dos valores exibidos na coluna **Tipo de** marca.
  
|**Tipo de marca**|**O que isso significa**|
|:-----|:-----|
| **Não revisado** | O número de emails não revisados ainda. Esses emails estão aguardando análise no painel de supervisão do Microsoft 365.
| **Compliant** | O número de emails revisados e marcados como compatíveis. Essas mensagens ainda precisam de resolução. |
| **Questionável** | O número de emails revisados e marcados como questionáveis. Serve como um sinalizador para que outros revisadores ajudem a verificar se um email precisa de investigação para conformidade. Essas mensagens ainda precisam de resolução. |
| **Não compatível (Ativo)** | O número de emails não compatíveis que os revisadores estão investigando no momento. |
| **Não Compatível (Resolvido)** | O número de emails não compatíveis que os revisadores investigaram e resolveram. |
| **Política de Acertos** | O número total (diário) de mensagens do Exchange, do Teams e de fontes de dados de terceiros que corresponderam a uma ou mais condições definidas em uma política de supervisão |
| **Em Purview** | O número total (diário) de mensagens do Exchange, do Teams e de fontes de dados de terceiros examinadas por uma política de supervisão |
| **Resolvido** | O número total de mensagens do Exchange, do Teams e de fontes de dados de terceiros classificadas como **Resolvidos**|

>[!NOTE]
>As políticas de supervisão devem ser provisionadas antes de aparecerem nos relatórios. Se as políticas são excluídas, os dados históricos ainda são mostrados. No entanto, eles são indicados como uma "política não existente" e a função **Exportar** não está disponível.

## <a name="audit"></a>Auditoria

Em alguns casos, você deve fornecer informações aos auditores regulamentadores ou de conformidade para provar a supervisão das atividades e comunicações dos funcionários. Essas informações podem ser um resumo de todas as atividades de supervisão associadas a uma política definida ou sempre que uma política de supervisão mudar. As políticas de supervisão têm trilhas de auditoria internas para preparação completa para auditorias internas ou externas. Históricos detalhados de auditoria de cada ação monitorada por suas políticas de supervisão fornecem prova de procedimentos de supervisão.

Exibir atividades de auditoria no log de auditoria unificado ou com o cmdlet [Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog) PowerShell.

Por exemplo, o exemplo a seguir retorna as atividades de todas as atividades de revisão de supervisão (políticas e regras) e lista informações detalhadas para cada uma delas:

```PowerShell
Search-UnifiedAuditLog -StartDate 3/1/2019 -EndDate ([System.DateTime]::Now) -RecordType DataGovernance -ResultSize 5000 | Where-Object {$_.Operations -like "*SupervisoryReview*"}  | fl CreationDate,Operations,UserIds,AuditData
```

Este exemplo retorna as atividades de atualização para suas políticas de conformidade de comunicação:

```PowerShell
Search-UnifiedAuditLog -StartDate $startDate -EndDate $endDate -Operations SupervisionPolicyCreated,SupervisionPolicyUpdated,SupervisionPolicyDeletedAuditData
```

Além das informações fornecidas nos relatórios e logs de supervisão, você também pode usar o cmdlet [Get-SupervisoryReviewActivity](https://docs.microsoft.com/powershell/module/exchange/get-supervisoryreviewactivity) PowerShell para retornar uma listagem completa de todas as atividades de política de supervisão.

## <a name="ready-to-get-started"></a>Pronto para começar?

Para configurar políticas de supervisão para sua organização, consulte [Configurar políticas de supervisão.](configure-supervision-policies.md)
