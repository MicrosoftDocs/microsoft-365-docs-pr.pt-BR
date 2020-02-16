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
ms.openlocfilehash: 5861348bb7c447c878f7f203acfd39fdf4c0a5f8
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42078758"
---
# <a name="communication-compliance-feature-reference"></a>Referência do recurso de conformidade de comunicação

## <a name="policies"></a>Políticas

Você cria políticas de conformidade de comunicação para organizações do Microsoft 365 no centro de conformidade da Microsoft 365. Se você tiver uma organização do Office 365, [configurará políticas de supervisão](configure-supervision-policies.md) no centro de conformidade & segurança do Office 365. As políticas de conformidade de comunicação definem quais comunicações e usuários estão sujeitos a revisar em sua organização, definir quais condições personalizadas as comunicações devem atender e especificar quem deve fazer revisões. Os usuários incluídos no grupo de função **administrador de análise de supervisão** podem configurar políticas e qualquer pessoa que tenha essa função atribuída pode acessar a página conformidade de **comunicação** no centro de conformidade da Microsoft 365. Se necessário, você pode exportar o histórico de modificações para uma política para um arquivo. csv que também inclui o status de alertas pendentes de revisão, itens escalonados e itens resolvidos. As políticas não podem ser renomeadas e podem ser excluídas quando não forem mais necessárias.

>[!NOTE]
>Políticas de supervisão criadas no centro de segurança e conformidade do Office 365 para assinaturas 365 do Office não podem migrar para o Microsoft 365. Se você estiver migrando de uma assinatura do Office 365 para uma assinatura do Microsoft 365, será necessário criar novas políticas de conformidade de comunicação para substituir as políticas de supervisão existentes.

## <a name="policy-templates"></a>Modelos de política

Os modelos de política são configurações de política predefinidas que você pode usar para criar rapidamente políticas para lidar com cenários comuns de conformidade. Cada um desses modelos tem diferenças em condições e escopo, e todos os modelos usam os mesmos tipos de sinais de verificação. Você pode escolher entre os seguintes modelos de política:

|**Área**|**Modelo de política**|**Detalhes**|
|:-----|:-----|:-----|
| **Linguagem ofensiva e antiassédio** | Monitorar comunicações para linguagem ofensiva | -Locais: Exchange, Teams, Skype for Business <br> -Direction: entrada, saída, interna <br> – Porcentagem de revisão: 100% <br> -Condições: classificador de idiomas ofensivo |
| **Informações confidenciais** | Monitorar as comunicações para informações confidenciais | -Locais: Exchange, Teams, Skype for Business <br> -Direction: entrada, saída, interna <br> – Porcentagem de revisão: 10% <br> – Condições: informações confidenciais, padrões e tipos de conteúdo prontos, opção de dicionário personalizado, anexos com mais de 1 MB |
| **Conformidade normativa** | Monitorar as comunicações para informações relacionadas à conformidade normativa financeira | -Locais: Exchange, Teams, Skype for Business <br> -Direction: entrada, saída <br> – Porcentagem de revisão: 10% <br> -Condições: opção de dicionário personalizado, anexos com mais de 1 MB |

## <a name="supervised-users"></a>Usuários supervisionados

Antes de começar a usar a conformidade de comunicação, você deve determinar quem precisa de suas comunicações revisadas. Na política, os endereços de email do usuário identificam pessoas ou grupos de pessoas para supervisionar. Alguns exemplos desses grupos são grupos do Office 365, listas de distribuição baseados no Exchange e canais do Microsoft Teams. Você também pode excluir usuários ou grupos específicos da verificação com um grupo de exclusão específico ou uma lista de grupos.

>[!IMPORTANT]
>Os usuários cobertos por políticas de conformidade de comunicação devem ter uma licença de conformidade do Microsoft 365 e5, uma licença do Office 365 Enterprise E3 com o complemento de conformidade avançada ou ser incluído em uma assinatura do Office 365 Enterprise e5. Se você não tem um plano Enterprise E5 existente e deseja tentar a conformidade de comunicação, pode [se inscrever para uma avaliação do Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).

## <a name="reviewers"></a>Revisores

Ao criar uma política de conformidade de comunicação, você deve determinar quem revisa as mensagens dos usuários supervisionados. Na política, os endereços de email do usuário identificam pessoas ou grupos de pessoas para analisar comunicações supervisionadas. Todos os revisores devem ter caixas de correio hospedadas no Exchange Online e devem ser atribuídas ao **Gerenciamento de casos** e às funções de **revisão** .

## <a name="groups-for-supervised-users-and-reviewers"></a>Grupos de usuários e revisores supervisionados

Para simplificar a configuração, crie grupos para pessoas que precisam de suas comunicações revisadas e grupos para pessoas que revisam essas comunicações. Se você estiver usando grupos, talvez precise de vários. Por exemplo, se você quiser examinar as comunicações entre dois grupos distintos de pessoas ou se quiser especificar um grupo que não é supervisionado.

Quando você seleciona um grupo do Office 365 para usuários supervisionados, a política verifica o conteúdo da caixa de correio compartilhada do Office 365 e dos canais do Microsoft Teams associados ao grupo. Quando você seleciona uma lista de distribuição, a política verifica caixas de correio de usuários individuais.

## <a name="supported-communication-types"></a>Tipos de comunicação com suporte

Com as políticas de conformidade de comunicação, você pode optar por examinar mensagens em uma ou mais das seguintes plataformas de comunicação como um grupo ou como fontes autônomas. As comunicações capturadas entre essas plataformas são mantidas por sete anos para cada política por padrão, mesmo que os usuários saiam da sua organização e suas caixas de correio sejam excluídas.

- **Microsoft Teams**: comunicações de chat e anexos associados em canais do Microsoft Teams públicos e privados e chats individuais podem ser verificados. Team chats que correspondem às condições de conformidade de comunicação são processadas uma vez a cada 24 horas e, em seguida, estão disponíveis nos relatórios de conformidade de comunicação. Use as configurações de gerenciamento de grupo a seguir para supervisionar chats de usuários individuais e comunicações de canal no Teams:

    - **Para comunicações de chat do teams:** Atribuir usuários individuais ou atribuir um [grupo de distribuição](https://support.office.com/article/Distribution-groups-E8BA58A8-FAB2-4AAF-8AA1-2A304052D2DE) à política de conformidade de comunicação. Essa configuração é para relações de usuário/chat de um-para-um ou um-para-muitos.
    - **Para comunicações de canal do teams:** Atribua cada grupo do Microsoft Team Channel ou Office 365 que você deseja verificar que contenha um usuário específico à política de conformidade de comunicação. Se você adicionar o mesmo usuário a outros canais do Microsoft Teams ou grupos do Office 365, certifique-se de adicionar esses novos canais e grupos à política de conformidade de comunicação.

- **Email do Exchange**: as caixas de correio hospedadas no Exchange Online como parte da sua assinatura do Microsoft 365 ou do Office 365 estão qualificadas para a verificação de mensagens. Os emails e anexos que correspondem às condições de política de conformidade de comunicação estão disponíveis instantaneamente nos relatórios de conformidade de comunicação. Os tipos de anexo com suporte para conformidade de comunicação são os mesmos que os [tipos de arquivo suportados para inspeções de conteúdo de regras de fluxo de email do Exchange](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection).

- **Skype for Business online**: as comunicações de chat e anexos associados no Skype for Business Online podem ser supervisionados. Conversas do Skype for Business online as condições de política de conformidade de comunicação são processadas uma vez a cada 24 horas e, em seguida, estão disponíveis nos relatórios de conformidade de comunicação. Conversas de chat supervisionadas são originadas de [conversas anteriores salvas no Skype for Business online](https://support.office.com/article/Find-a-previous-Skype-for-Business-conversation-18892eba-5f18-4281-8c87-fd48bd72e6a2).  Use a seguinte configuração de gerenciamento de grupos para supervisionar as comunicações de chat do usuário no Skype for Business Online:

    - **Para comunicações de chat do Skype for Business online**: atribua usuários individuais ou atribua um [grupo de distribuição](https://support.office.com/article/Distribution-groups-E8BA58A8-FAB2-4AAF-8AA1-2A304052D2DE) à política de conformidade de comunicação. Essa configuração é para relações de usuário/chat de um-para-um ou um-para-muitos.

- **Fontes de terceiros**: você pode verificar comunicações de fontes de terceiros para dados importados em caixas de correio em sua organização do Microsoft 365. Os conectores dão suporte aos seguintes recursos de terceiros:

    - [Bloomberg instantâneo](archive-instant-bloomberg-data.md)
    - [Facebook](archive-facebook-data-with-sample-connector.md)
    - [LinkedIn](archive-linkedin-data.md)
    - SAP SuccessFactors
    - [Twitter](archive-twitter-data-with-sample-connector.md)
    - [Conector de dados personalizado](archiving-third-party-data.md)

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

Você tem a opção de incluir tipos de informações confidenciais como parte de sua política de conformidade de comunicação. Os tipos de informações confidenciais são tipos de dados predefinidos ou personalizados que podem ajudar a identificar e proteger números de cartão de crédito, números de contas bancárias, números de passaportes e muito mais. Como parte da [DLP (prevenção de perda de dados)](data-loss-prevention-policies.md)do Office 365, a configuração de informações confidenciais pode usar padrões, proximidade de caracteres, níveis de confiança e até mesmo tipos de dados personalizados para ajudar a identificar e sinalizar conteúdo que possa ser confidencial. Os tipos de informações confidenciais padrão são:

- Financeiro
- Assistência médica e saúde
- Privacidade
- Tipo de informação personalizada

Para saber mais sobre detalhes de informações confidenciais e os padrões incluídos nos tipos padrão, confira [quais tipos de informações confidenciais](what-the-sensitive-information-types-look-for.md)há.

### <a name="custom-keyword-dictionaries"></a>Dicionários de palavras-chave personalizados

Configure os dicionários de palavras-chave personalizados (ou léxicos) para fornecer gerenciamento simples de palavras-chave específicas para sua organização ou setor. Os dicionários de palavras-chave suportam até 100.000 termos por dicionário e dão suporte a qualquer idioma. Se necessário, você pode aplicar vários dicionários de palavras-chave personalizados a uma única política ou ter um único dicionário de palavra-chave por política. Esses dicionários são atribuídos a uma política de conformidade de comunicação e podem ser originados de um arquivo (como uma lista. csv ou. txt) ou de uma lista que pode ser [importada no centro de conformidade](create-a-keyword-dictionary.md). Use os dicionários personalizados quando precisar dar suporte a termos ou idiomas específicos para sua organização e políticas.

### <a name="classifiers"></a>Classificadores

Classificadores internos verificam mensagens enviadas ou recebidas em todos os canais de comunicação em sua organização para diferentes tipos de problemas de conformidade. Os classificadores usam uma combinação de inteligência artificial e palavras-chave para identificar o idioma das mensagens que provavelmente violam as políticas antiassédio. Atualmente, os classificadores internos oferecem suporte somente a palavras-chave em inglês nas mensagens.

Os classificadores incorporados de conformidade de comunicação verificam os termos e os seguintes tipos de idioma em comunicações.

- **Ameaça**: verifica se há ameaças para confirmar a violência ou danos físicos a uma pessoa ou a uma propriedade.
- **Assédio**: procura por pessoas de alvo de conduta ofensiva relacionadas à corrida, cor, Religion, origem nacional.
- **Profanação**: procura expressões obscenas que constrangim a maioria das pessoas.

Os classificadores internos não fornecem uma lista exaustiva de termos para essas áreas. Além disso, os padrões culturais e de idioma mudam continuamente e, em claro, a Microsoft reserva-se o direito de atualizar os classificadores a seu critério. Embora os classificadores possam ajudar sua organização a monitorar essas áreas, os classificadores não são destinados a fornecer o único meio de monitoramento ou endereçamento de tal linguagem. Sua organização, não a Microsoft, permanece responsável por todas as decisões relacionadas ao idioma de verificação e bloqueio nessas áreas.

Para obter informações sobre classificadores no Microsoft 365, consulte [classificadores](classifier-getting-started-with.md).

### <a name="conditional-settings"></a>Configurações condicionais
<a name="ConditionalSettings"> </a>

As condições escolhidas para a política se aplicam às comunicações de emails e fontes de terceiros em sua organização (como no Facebook ou no DropBox).

A tabela a seguir explica mais sobre cada condição.
  
|**Condição**|**Como usar essa condição**|
|:-----|:-----|
| **O conteúdo corresponde a qualquer um desses classificadores** | Aplica-se à política quando os classificadores são incluídos ou excluídos em uma mensagem. Alguns classificadores são predefinidos no locatário e os classificadores personalizados devem ser configurados separadamente antes de estarem disponíveis para essa condição. Somente um classificador pode ser definido como uma condição em uma política. Para obter mais informações sobre a configuração de classificadores, consulte [classificadores](classifier-getting-started-with.md). |
| **O conteúdo contém qualquer um desses tipos de informações confidenciais** | Aplica-se à política quando qualquer tipo de informação confidencial é incluído ou excluído em uma mensagem. Alguns classificadores são predefinidos no locatário e os classificadores personalizados podem ser configurados separadamente ou como parte do processo de atribuição de condição. Cada tipo de informação confidencial que você escolher será aplicado separadamente e apenas um desses tipos de informações confidenciais deverá ser aplicado à política a ser aplicada à mensagem. Para obter mais informações sobre tipos de informações confidenciais personalizadas, confira [tipos de informações confidenciais personalizados](custom-sensitive-info-types.md). |
| **A mensagem é recebida de qualquer um desses domínios**  <br><br> **A mensagem não é recebida de nenhum desses domínios** | Aplique a política para incluir ou excluir domínios ou endereços de email específicos em mensagens recebidas. Insira cada domínio ou endereço de email e separe vários domínios ou endereços de email com uma vírgula. Cada endereço de domínio ou de email inserido é aplicado separadamente, somente um domínio ou endereço de email deve ser aplicado para que a política seja aplicada à mensagem. <br><br> Se você deseja examinar todos os emails de um domínio específico, mas deseja excluir mensagens que não precisam de revisão (boletins informativos, anúncios e assim por diante), você deve configurar uma **mensagem não é recebida de qualquer uma destas** condições de domínios que exclua o endereço de email (exemplo "newsletter@contoso.com"). |
| **A mensagem é enviada para qualquer um desses domínios**  <br><br> **A mensagem não é enviada a nenhum desses domínios** | Aplique a política para incluir ou excluir domínios ou endereços de email específicos em mensagens enviadas. Insira cada domínio ou endereço de email e separe vários domínios ou endereços de email com uma vírgula. Cada domínio ou endereço de email é aplicado separadamente, apenas um endereço de domínio ou de email deve ser aplicado para que a política seja aplicada à mensagem. <br><br> Se você deseja examinar todos os emails enviados para um domínio específico, mas deseja excluir as mensagens enviadas que não precisam de revisão, você deve configurar duas condições: <br> -Uma **mensagem é enviada a qualquer uma das condições de domínios** que define o domínio ("contoso.com") e <br> -Uma **mensagem não é enviada para qualquer uma dessas condições de domínio** que exclua o endereço de email ("subscriptions@contoso.com"). |
| **A mensagem é classificada com qualquer um desses rótulos**  <br><br> **A mensagem não é classificada com nenhum desses rótulos** | Para aplicar a política quando determinados rótulos de retenção são incluídos ou excluídos em uma mensagem. Os rótulos de retenção devem ser configurados separadamente e os rótulos configurados são escolhidos como parte dessa condição. Cada rótulo escolhido é aplicado separadamente (somente um desses rótulos deve se aplicar à política para aplicar à mensagem). Para obter mais informações sobre a configuração de rótulos de retenção, consulte [Overview of Retention Labels](labels.md).|
| **A mensagem contém qualquer uma destas palavras**  <br><br> **A mensagem não contém nenhuma destas palavras** | Para aplicar a política quando determinadas palavras ou frases forem incluídas ou excluídas em uma mensagem, insira cada palavra ou frase e separe-as com vírgula. Cada palavra inserida é aplicada separadamente (apenas uma palavra deve ser aplicada para que a política seja aplicada à mensagem). Para saber mais sobre como inserir palavras ou frases, consulte a próxima seção [Matching words and phrases to emails or attachments](communication-compliance-feature-reference.md#Matchwords).|
| **O anexo contém qualquer uma destas palavras**  <br><br> **O anexo não contém nenhuma destas palavras** | Para aplicar a política quando determinadas palavras ou frases forem incluídas ou excluídas em um anexo de mensagem (como um documento do Word), insira cada palavra ou frase e separe-as com uma vírgula. Cada palavra inserida é aplicada separadamente (apenas uma palavra deve ser aplicada para que a política seja aplicada ao anexo). Para saber mais sobre como inserir palavras ou frases, consulte a próxima seção [Matching words and phrases to emails or attachments](communication-compliance-feature-reference.md#Matchwords).|
| **O anexo é qualquer um desses tipos de arquivo**  <br><br> **O anexo não é nenhum desses tipos de arquivo** | Para supervisionar as comunicações que incluem ou excluem tipos específicos de anexos, insira as extensões de arquivo (como. exe ou. pdf). Se você quiser incluir ou excluir várias extensões de arquivo, insira-as em linhas separadas. Somente uma extensão de anexo deve corresponder à política a ser aplicada.|
| **Tamanho da mensagem é maior que**  <br><br> **O tamanho da mensagem não é maior que** | Para revisar mensagens com base em um determinado tamanho, use essas condições para especificar o tamanho máximo ou mínimo que uma mensagem pode ser antes de estar sujeita a revisão. Por exemplo, se você especificar o **tamanho da mensagem é maior que** \> **1,0 MB**, todas as mensagens com 1, 1 MB e maiores estão sujeitas a revisão. Você pode optar por bytes, kilobytes, megabytes ou gigabytes para essa condição.|
| **O anexo é maior que**  <br><br> **O anexo não é maior que** | Para revisar mensagens com base no tamanho de seus anexos, especifique o tamanho máximo ou mínimo que um anexo pode ser antes da mensagem e seus anexos estão sujeitos à revisão. Por exemplo, se você especificar que o **anexo é maior que** \> **2,0 MB**, todas as mensagens com anexos de 2, 1 MB e mais estão sujeitas a revisão. Você pode optar por bytes, kilobytes, megabytes ou gigabytes para essa condição.|
   
#### <a name="matching-words-and-phrases-to-emails-or-attachments"></a>Palavras e frases correspondentes a emails ou anexos
<a name="Matchwords"> </a>

Cada palavra inserida e separada com uma vírgula é aplicada separadamente (apenas uma palavra deve ser aplicada à condição de política a ser aplicada ao email ou anexo). Por exemplo, vamos usar a condição, a **mensagem contém qualquer uma destas palavras**, com as palavras-chave "banco" e "comércio Insider" separada por uma vírgula (banco, comércio Insider). A política se aplica a qualquer mensagem que inclua a palavra "banco" ou a frase "insider trading". Apenas uma destas palavras ou frases deve ocorrer para que se aplique a condição dessa política. Palavras na mensagem ou anexo devem corresponder exatamente ao que você inserir.

Para verificar as mensagens de email e anexos das mesmas palavras-chave, crie uma [política de prevenção de perda de dados](create-test-tune-dlp-policy.md) com um [dicionário de palavras-chave personalizado](create-a-keyword-dictionary.md) para os termos que você deseja examinar nas mensagens. Essa configuração de política identifica palavras-chave definidas que aparecem na mensagem de email **ou** no anexo de email. Usar as configurações de política condicional padrão (*mensagem contém qualquer uma destas palavras* e *anexos contém qualquer uma destas palavras*) para identificar termos em mensagens e anexos requer os **termos a serem apresentados na mensagem** e no anexo.
  
#### <a name="enter-multiple-conditions"></a>Inserir várias condições

Se você inserir várias condições, a Microsoft 365 usará todas as condições juntas para determinar quando aplicar a política de supervisão a itens de comunicação. Quando você configura várias condições, todas as condições devem ser atendidas para que a política seja aplicada, a menos que você insira uma exceção. Por exemplo, você precisará de uma política que se aplique se uma mensagem contiver a palavra "comércio" e maior que 2 MB. No entanto, se a mensagem também contiver as palavras "aprovadas pela contoso Financial", a política não deverá ser aplicada. Neste exemplo, as três condições seriam definidas da seguinte maneira:
  
- A **mensagem contém qualquer uma destas palavras**, com as palavras-chave "trade"
- O **tamanho da mensagem é maior que**, com o valor 2 MB
- A **mensagem contém nenhuma destas palavras**, com as palavras-chave "aprovadas pela equipe financeira da Contoso"

### <a name="review-percentage"></a>Porcentagem de revisão

Se quiser reduzir a quantidade de conteúdo a ser revisada, você poderá especificar uma porcentagem de todas as comunicações governadas por uma política de supervisão. Uma amostra de conteúdo aleatória em tempo real é selecionada da porcentagem total de conteúdo que corresponde às condições de política escolhidas. Se quiser que os revisores Revisem todos os itens, você pode configurar **100%** em uma política de conformidade de comunicação.

## <a name="notices"></a>Avisos

Você pode criar modelos de aviso se quiser enviar aos usuários um aviso de lembrete por email para correspondências de política como parte do processo de solução de problemas. Os avisos só podem ser enviados ao endereço de email do funcionário associado à correspondência de política que gerou o alerta específico para correção. Ao selecionar um modelo de aviso a ser aplicado a uma violação de política como parte do fluxo de trabalho de correção, você pode optar por aceitar os valores de campo definidos no modelo ou substituir os campos conforme necessário.

Os modelos de avisos são modelos de email personalizados onde você pode definir os seguintes campos de mensagem:

|**Field**|**Required**| **Detalhes** |
|:-----|:-----|:-----|
|**Nome do modelo** | Sim | Nome amigável para o modelo de aviso que você selecionará no fluxo de trabalho notificar durante a correção, suporta caracteres de texto. |
| **Endereço do remetente** | Sim | O endereço de um ou mais usuários ou grupos que enviam a mensagem para o funcionário com uma correspondência de política, selecionado no Active Directory para a sua assinatura. |
| **Endereços CC e Cco** | Não | Usuários ou grupos opcionais a serem notificados sobre a correspondência da política, selecionados no Active Directory para a sua assinatura. |
| **Subject** | Sim | As informações que aparecem na linha de assunto da mensagem dão suporte a caracteres de texto. |
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
| **Classe de item** | A origem da mensagem com base no tipo de mensagem, email, Microsoft Team Chat, Bloonmberg, etc. |
| **Domínios de destinatário** | O domínio para o qual a mensagem foi enviada. Esse domínio normalmente é seu domínio de assinatura do Microsoft 365 por padrão. |
| **Recipient** | O usuário para o qual a mensagem foi enviada. |
| **Sender** | A pessoa que enviou a mensagem. |
| **Domínio do remetente** | O domínio que enviou a mensagem. |
| **Tamanho** | O tamanho da mensagem em KB. |
| **Assunto/título** | O assunto da mensagem ou o título do chat. |
| **Marcas** | As marcas atribuídas a uma mensagem, seja *questionável*, *compatível*ou *não compatível*. |
| **Escalonado para** | O nome de usuário da pessoa incluída como parte de uma ação de escalonamento de mensagens. |
| **Classificadores** | O nome de classificadores internos e personalizados que se aplicam à mensagem. Alguns exemplos incluem *idioma ofensivo*, *assédio dirigido*, *profanação*, *ameaça*e muito mais.

## <a name="alert-policies"></a>Políticas de alerta

Após configurar uma política, uma política de alerta correspondente é automaticamente criada e os alertas são gerados para mensagens que correspondem às condições definidas na política. Por padrão, todas as políticas correspondem a disparadores de alerta são atribuídos a um nível de severidade de média na política de alerta associada. Os alertas são gerados para uma política de conformidade de comunicação depois que o nível de limite do gatilho de agregação é atendido na política de alerta do Office 365 associada.

Para políticas de conformidade de comunicação, os seguintes valores de política de alerta são configurados por padrão:

|**Gatilho de política de alerta**|**Valor padrão**|
|:-----|:-----|
| Agregação | Agregação simples |
| Limite | 4 atividades |
| Janela | 60 minutos |

>[!Note]
>As configurações do gatilho de limite de política de alerta para atividades dão suporte ao valor mínimo de 3 ou superior para políticas de conformidade de comunicação.

Você pode alterar as configurações padrão para gatilhos no número de atividades, período para as atividades e para usuários específicos em políticas de alerta na página **políticas de alerta** no centro de conformidade & segurança do Office 365.

### <a name="change-the-severity-level-for-an-alert-policy"></a>Alterar o nível de severidade de uma política de alerta

Se quiser alterar o nível de gravidade atribuído em uma política de alerta para uma política de conformidade de comunicação específica, conclua as seguintes etapas:

1. Entre [https://compliance.microsoft.com](https://compliance.microsoft.com) usando as credenciais de uma conta de administrador na sua organização do Microsoft 365.

2. No centro de conformidade da Microsoft 365, vá para **políticas**.

3. Selecione o **alerta do Office 365** na página **políticas** para abrir a página **políticas de alerta** no centro de **conformidade & segurança do Office 365**.

4. Marque a caixa de seleção da política de conformidade de comunicação que você deseja atualizar e, em seguida, selecione **Editar política**.

5. Na guia **Descrição** , selecione o menu suspenso de **gravidade** para configurar o nível de alerta da política.

6. Selecione **salvar** para aplicar o novo nível de severidade à política.

7. Selecione **fechar** para sair da página de detalhes da política de alerta.

## <a name="audit"></a>Faça

Em alguns casos, você deve fornecer informações para auditores regulamentares ou de conformidade para provar a supervisão de atividades e comunicações de funcionários. Essas informações podem ser um resumo de todas as atividades associadas a uma política organizacional definida ou a qualquer momento em que uma política de conformidade de comunicação é alterada. As políticas de conformidade de comunicação têm trilhas de auditoria internas para a preparação completa para auditorias internas ou externas. Históricos de auditoria detalhados de cada ação criar, editar e excluir são capturados por suas políticas de comunicação para fornecer provas de procedimentos de supervisão.

>[!Important]
>A auditoria deve estar habilitada para sua organização antes de eventos de conformidade de comunicação serem registrados. Para habilitar a auditoria, confira [habilitar o log de auditoria do Office 365](communication-compliance-configure.md#step-2-required-enable-the-office-365-audit-log).

Para exibir as atividades de política de conformidade de comunicação, selecione o controle **Exportar atividades de revisão** na página principal de qualquer política. Esta ação gera um arquivo de auditoria no formato. csv que contém as seguintes informações:

|**Field**|**Detalhes**|
|:-----|:-----|
| **CreationDate** | A data em que a atividade foi realizada em uma política. |
| **UserIds** | O usuário que realizou a atividade em uma política. |
| **Operations** | As operações executadas na política. |
| **AuditData** | Este campo é a principal fonte de dados para todas as atividades de política. Todas as atividades são registradas e separadas por delimitadores vírgulas. |

Você também pode exibir as atividades de auditoria no log de auditoria unificada ou com o cmdlet [Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-unifiedauditlog) do PowerShell.

Por exemplo, o exemplo a seguir retorna as atividades para todas as atividades de análise de supervisão (políticas e regras) e lista informações detalhadas de cada:

```PowerShell
Search-UnifiedAuditLog -StartDate 3/1/2019 -EndDate ([System.DateTime]::Now) -RecordType DataGovernance -ResultSize 5000 | Where-Object {$_.Operations -like "*SupervisoryReview*"}  | fl CreationDate,Operations,UserIds,AuditData
```

Este exemplo retorna as atividades de atualização para suas políticas de conformidade de comunicação:

```PowerShell
Search-UnifiedAuditLog -StartDate $startDate -EndDate $endDate -Operations SupervisionPolicyCreated,SupervisionPolicyUpdated,SupervisionPolicyDeletedAuditData
```

## <a name="ready-to-get-started"></a>Pronto para começar?

Para configurar a conformidade de comunicação para sua organização do Microsoft 365, confira [Configurar a conformidade de comunicação para a sua organização do microsoft 365](communication-compliance-configure.md).
