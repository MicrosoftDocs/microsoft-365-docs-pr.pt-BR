---
title: Detecções do Explorador de Ameaças e em Tempo Real
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 82ac9922-939c-41be-9c8a-7c75b0a4e27d
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Use o Explorer e as detecções em tempo real no Centro de Conformidade de Segurança para &amp; investigar e responder a ameaças com eficiência.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: caf795b421ac8e1e6785abff2fc49f0e49c391ca
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931705"
---
# <a name="threat-explorer-and-real-time-detections"></a>Detecções do Explorador de Ameaças e em Tempo Real

Se sua organização tiver o [Microsoft Defender para Office 365](office-365-atp.md) e você tiver as permissões necessárias, terá acesso ao *Explorer* ou às detecções em tempo *real,* que anteriormente eram relatórios em tempo *real.* [](#required-licenses-and-permissions) ([Veja as novidades.](#new-features-in-threat-explorer-and-real-time-detections)) No Centro de Conformidade & segurança, vá para o gerenciamento de ameaças e, em **seguida,** selecione **Explorer** _ou_ **detecções em tempo real.**

|Com o Microsoft Defender para Office 365 Plano 2, você pode ver:|Com o Microsoft Defender para Office 365 Plano 1, você pode ver:|
|---|---|
|![Explorador de ameaças](../../media/threatmgmt-explorer.png)|![Detecções em tempo real](../../media/threatmgmt-realtimedetections.png)|
|

As detecções do Explorer ou em tempo real ajudam a equipe de operações de segurança a investigar e responder a ameaças com eficiência. O relatório se parece com a seguinte imagem:

![Ir para o Explorador de Gerenciamento de \> Ameaças](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

Com esse relatório, você pode:

- [Ver malware detectado pelos recursos de segurança do Microsoft 365](#see-malware-detected-in-email-by-technology)
- [Exibir URL de phishing e clicar em dados de veredito](#view-phishing-url-and-click-verdict-data)
- [Iniciar um processo automatizado de investigação e resposta a](#start-automated-investigation-and-response) partir de uma exibição no Explorer (somente o Defender para Office 365 Plano 2)
- [Investigar emails mal-intencionados e muito mais](#more-ways-to-use-explorer-and-real-time-detections)

## <a name="improvements-to-threat-explorer-and-real-time-detections"></a>Melhorias no Explorador de Ameaças e detecções em tempo real

### <a name="tags-in-threat-explorer"></a>Marcas no Explorador de Ameaças

> [!NOTE]
> O recurso de marcas de usuário está em *Visualização,* não está disponível para todos e está sujeito a alterações. Para obter informações sobre o cronograma de lançamento, confira o mapa do Microsoft 365.

As marcas de usuário identificam grupos específicos de usuários no Microsoft Defender para Office 365. Para obter mais informações sobre marcas, incluindo licenciamento e configuração, consulte [Marcas de usuário.](user-tags.md)

No Explorador de Ameaças, você pode ver informações sobre marcas de usuário nas experiências a seguir.

#### <a name="email-grid-view"></a>Exibição de grade de email

A **coluna Marcas** na grade de email contém todas as marcas que foram aplicadas às caixas de correio do remetente ou do destinatário. Por padrão, as marcas do sistema, como contas prioritárias, são mostradas primeiro.

> [!div class="mx-imgBorder"]
> ![Marcas de filtro na exibição de grade de email](../../media/tags-grid.png)

#### <a name="filtering"></a>Filtragem

Você pode usar marcas como um filtro. Busca apenas em contas prioritárias ou em cenários específicos de marcas de usuário. Você também pode excluir resultados com determinadas marcas. Combine essa funcionalidade com outros filtros para restringir seu escopo de investigação.

[![Marcas de filtro](../../media/tags-filter-normal.png)](../../media/tags-filter-normal.png#lightbox)

> [!div class="mx-imgBorder"]
> ![Não filtrar marcas](../../media/tags-filter-not.png)

#### <a name="email-detail-flyout"></a>Flyout de detalhes do email
Para exibir as marcas individuais do remetente e do destinatário, selecione o assunto para abrir o flyout de detalhes da mensagem. Na guia **Resumo,** as marcas de remetente e destinatário são mostradas separadamente, se elas estão presentes para um email.
As informações sobre marcas individuais para remetente e destinatário também se estendem aos dados CSV exportados, onde você pode ver esses detalhes em duas colunas separadas.

> [!div class="mx-imgBorder"]
> ![Marcas de detalhes de email](../../media/tags-flyout.png)

As informações de marcas também são mostradas no flyout de cliques de URL. Para exibi-lo, vá para a exibição Phish or All Email e, em seguida, para as **URLs ou** **a guia Cliques de URL.** Selecione um flyout de URL individual para exibir detalhes adicionais sobre cliques para essa URL, incluindo marcas associadas a esse clique.

> [!div class="mx-imgBorder"]
> ![Marcas de URL](../../media/tags-urls.png)

## <a name="improvements-to-the-threat-hunting-experience-upcoming"></a>Melhorias na experiência de busca de ameaças (futuras)

### <a name="updated-threat-information-for-emails"></a>Informações atualizadas de ameaças para emails

Nos concentramos nas melhorias de qualidade de dados e plataforma para aumentar a precisão e a consistência dos dados para registros de email. As melhorias incluem consolidação de informações de pré-entrega e pós-entrega, como ações executadas em um email como parte do processo zap, em um único registro. Detalhes adicionais, como veredito de spam, ameaças no nível da entidade (por exemplo, qual URL era mal-intencionada) e locais de entrega mais recentes também estão incluídos.

Após essas atualizações, você verá uma única entrada para cada mensagem, independentemente dos diferentes eventos pós-entrega que afetam a mensagem. As ações podem incluir ZAP, correção manual (o que significa ação do administrador), entrega dinâmica e assim por diante.

Além de mostrar ameaças de malware e phishing, você vê o veredito de spam associado a um email. No email, veja todas as ameaças associadas ao email juntamente com as tecnologias de detecção correspondentes. Um email pode ter zero, uma ou várias ameaças. Você verá as ameaças atuais na seção **Detalhes** do flyout de email. Para várias ameaças (como malware e  phishing), o campo técnico de detecção mostra o mapeamento de detecção de ameaças, que é a tecnologia de detecção que identificou a ameaça.

O conjunto de tecnologias de detecção agora inclui novos métodos de detecção, bem como tecnologias de detecção de spam. Você pode usar o mesmo conjunto de tecnologias de detecção para filtrar os resultados nos diferentes modo de exibição de email (Malware, Phish, Todos os Emails).

> [!NOTE]
> A análise de veredito pode não estar necessariamente vinculada a entidades. Por exemplo, um email pode ser classificado como phishing ou spam, mas não há URLs marcadas com um veredito de phishing/spam. Isso porque os filtros também avaliam o conteúdo e outros detalhes de um email antes de atribuir um veredito.

#### <a name="threats-in-urls"></a>Ameaças em URLs

Agora você pode ver a ameaça específica para uma URL na guia Detalhes do flyout **de** email. A ameaça pode ser *malware,* *phishing,* *spam* ou *nenhum.)*

> [!div class="mx-imgBorder"]
> ![Ameaças de URL](../../media/URL_Threats.png)

### <a name="updated-timeline-view-upcoming"></a>Exibição de linha do tempo atualizada (futura)

> [!div class="mx-imgBorder"]
> ![Exibição de Linha do Tempo Atualizada](../../media/Email_Timeline.png)

A exibição de linha do tempo identifica todos os eventos de entrega e pós-entrega. Ele inclui informações sobre a ameaça identificada nesse momento para um subconjunto desses eventos. O modo de exibição Linha do Tempo também fornece informações sobre qualquer ação adicional realizada (como ZAP ou correção manual), juntamente com o resultado dessa ação. As informações de exibição de linha do tempo incluem:

- **Origem:** Origem do evento. Pode ser administrador/sistema/usuário.
- **Evento:** Inclui eventos de nível superior, como entrega original, correção manual, ZAP, envios e entrega dinâmica.
- **Ação:** A ação específica que foi tomada como parte da ZAP ou ação do administrador (por exemplo, exclusão simples).
- **Ameaças:** Aborda as ameaças (malware, phish, spam) identificadas nesse momento.
- **Resultado/detalhes:** Mais informações sobre o resultado da ação, por exemplo, se ela foi executada como parte da ação zap/administrador.

### <a name="original-and-latest-delivery-location"></a>Local de entrega original e mais recente

Atualmente, vamos aparecer o local de entrega na grade de email e no flyout de email. O **campo Local de** entrega está sendo renomeado * Local de entrega *_original_* _. E estamos apresentando outro campo, o local _*_de entrega mais recente._*_

_ *Local original de entrega** dará mais informações sobre onde um email foi entregue inicialmente. **O local de entrega mais** recente estadoá onde um email foi enviado após ações do sistema como *ZAP* ou ações de administrador, como Mover para *itens excluídos.* O local de entrega mais recente destina-se a dizer aos administradores o último local conhecido após a entrega da mensagem ou qualquer ação de sistema/administrador. Ele não inclui ações do usuário final no email. Por exemplo, se um usuário excluiu uma mensagem ou moveu a mensagem para arquivo morto/pst, o local de "entrega" da mensagem não será atualizado. Mas se uma ação do sistema atualizou o local (por exemplo, ZAP resultando em um email sendo colocado em **quarentena),** o local de entrega mais recente seria "quarentena".

> [!div class="mx-imgBorder"]
> ![Locais de entrega atualizados](../../media/Updated_Delivery_Location.png)

> [!NOTE]
> Há alguns casos em que o local **de entrega e** a ação de **entrega** podem aparecer como "desconhecidos":
>
> - Você pode  ver o local  de entrega como "entregue" e o local de entrega como "desconhecido" se a mensagem foi entregue, mas uma regra de Caixa de Entrada moveu a mensagem para uma pasta padrão (como Rascunho ou Arquivo Morto) em vez de para a pasta Caixa de Entrada ou Lixo Eletrônico.
>
> - **O local de** entrega mais recente poderá ser desconhecido se uma ação de administrador/sistema (como ZAP) tiver sido tentada, mas a mensagem não foi encontrada. Normalmente, a ação ocorre depois que o usuário moveu ou excluiu a mensagem. Nesses casos, verifique a coluna **Resultado/Detalhes** na exibição de linha do tempo. Procure a instrução "Mensagem movida ou excluída pelo usuário".

> [!div class="mx-imgBorder"]
> ![Locais de entrega para linha do tempo](../../media/Updated_Timeline_Delivery_Location.png)

### <a name="additional-actions"></a>Ações adicionais

*Ações adicionais* foram aplicadas após a entrega do email. Eles podem incluir *ZAP*, correção *manual* (ação tomada por um Administrador, como exclusão flexível), entrega dinâmica e *reprocessado* (para um email que foi detectado retroativamente como bom).

> [!NOTE]
> - Como parte das alterações pendentes, o valor "Removido pela ZAP" atualmente em superfície no filtro de Ação de Entrega desaparecerá. Você terá uma maneira de pesquisar todos os emails com a tentativa da ZAP por meio **de ações adicionais.**
>
> - Haverá novos campos e valores para tecnologias **de detecção** e **ações adicionais** (especialmente para cenários zap). Você precisará avaliar suas consultas salvas e as consultas controladas existentes para garantir que elas funcionem com os novos valores.

> [!div class="mx-imgBorder"]

> ![Ações adicionais no Explorer](../../media/Additional_Actions.png)

### <a name="system-overrides"></a>Substituições do sistema

*As substituições do* sistema permitem que você faça exceções ao local de entrega pretendido de uma mensagem. Você substitui o local de entrega fornecido pelo sistema, com base nas ameaças e outras detecções identificadas pela pilha de filtragem. As substituições do sistema podem ser definidas por meio da política de locatário ou usuário para entregar a mensagem conforme sugerido pela política. As substituições podem identificar a entrega não intencional de mensagens mal-intencionadas devido a lacunas de configurações, como uma política de Remetente Seguro muito ampla definida por um usuário. Esses valores de substituição podem ser:

- Permitido pela política de usuário: um usuário cria políticas no nível da caixa de correio para permitir domínios ou destinatários.
- Bloqueado pela política de usuário: um usuário cria políticas no nível da caixa de email para bloquear domínios ou senders.
- Permitido pela política da organização: as equipes de segurança da organização configuram políticas ou regras de fluxo de emails do Exchange (também conhecidas como regras de transporte) para permitir os envios e domínios dos usuários em sua organização. Isso pode ser para um conjunto de usuários ou para toda a organização.
- Bloqueado pela política da organização: as equipes de segurança da organização configuram políticas ou regras de fluxo de emails para bloquear os envios, domínios, idiomas de mensagens ou IPs de origem para usuários em sua organização. Isso pode ser aplicado a um conjunto de usuários ou a toda a organização.
- Extensão de arquivo bloqueada pela política da organização: a equipe de segurança da organização bloqueia uma extensão de nome de arquivo por meio das configurações de política anti-malware. Esses valores agora serão exibidos em detalhes por email para ajudar nas investigações. As equipes Desempesas também podem usar a funcionalidade de filtragem de conteúdo para filtrar extensões de arquivos bloqueados.

[![Substituições do sistema no Explorer](../../media/System_Overrides.png)](../../media/System_Overrides.png#lightbox)

> [!div class="mx-imgBorder"]
> ![Sistema substitui grade no Explorer](../../media/System_Overrides_Grid.png)

### <a name="improvements-for-the-url-and-clicks-experience"></a>Melhorias para a experiência de URL e cliques

As melhorias incluem:

- Mostre a URL clicada completa (incluindo todos os parâmetros de consulta que fazem parte da URL) na seção **Cliques** do flyout da URL. Atualmente, o domínio e o caminho da URL aparecem na barra de título. Estamos estendendo essas informações para mostrar a URL completa.

- Correções entre filtros de URL *(URL* versus domínio da *URL* versus domínio e caminho da *URL):* as atualizações afetam a pesquisa de mensagens que contêm um veredito de URL/clique. Habilitamos o suporte para pesquisas sem diagnóstico de protocolo, para que você possa procurar uma URL sem `http` usar. Por padrão, a pesquisa de URL é mapeada para http, a menos que outro valor seja explicitamente especificado. Por exemplo:

   -  Pesquise com e sem o prefixo nos campos de filtro `http://` **URL,** **DOMÍNIO da URL** e **Caminho.** As pesquisas devem mostrar os mesmos resultados.

   -  Procure o `https://` prefixo na **URL.** Quando nenhum valor é especificado, o `http://` prefixo é assumido.

   - `/` é ignorado no início e no final do caminho da **URL,** domínio da **URL,** **domínio da URL e campos de** caminho. `/` no final do campo **url** é ignorado.

### <a name="phish-confidence-level"></a>Nível de confiança de phishing

O nível de confiança de phishing ajuda a identificar o grau de confiança com o qual um email foi categorizado como "phish". Os dois valores possíveis são *Alta* e *Normal.* Nos estágios iniciais, esse filtro estará disponível somente no ponto de vista de phishing do Explorador de Ameaças.

[![Nível de confiança de phishing no Explorer](../../media/Phish_Confidence_Level.png)](../../media/Phish_Confidence_Level.png#lightbox)

### <a name="zap-url-signal"></a>Sinal de URL da ZAP

O sinal da URL da ZAP normalmente é usado para cenários de alerta de phishing da ZAP, em que um email foi identificado como Phishing e removido após a entrega. Esse sinal conecta o alerta aos resultados correspondentes no Explorer. É um dos IOCs do alerta.

Para melhorar o processo de busca, atualizamos o Explorador de Ameaças e as detecções em tempo real para tornar a experiência de busca mais consistente. As alterações são descritas aqui:

- [Melhorias de timezone](#timezone-improvements)
- [Atualização no processo de atualização](#update-in-the-refresh-process)
- [Detalhamento do gráfico a ser acrescentado aos filtros](#chart-drilldown-to-add-to-filters)
- [Em atualizações de informações do produto](#in-product-information-updates)

### <a name="filter-by-user-tags"></a>Filtrar por marcas de usuário

Agora você pode classificar e filtrar por marcas de usuário do sistema ou personalizadas para entender rapidamente o escopo das ameaças. Para saber mais, consulte [Marcas de usuário.](user-tags.md)

> [!IMPORTANT]
> A filtragem e a classificação por marcas de usuário estão atualmente em visualização pública. Essa funcionalidade pode ser substancialmente modificada antes de ser lançada comercialmente. A Microsoft não faz garantias, expressas ou implícitas, com relação às informações fornecidas sobre ela.

![Coluna Tags no Explorer](../../media/threat-explorer-tags.png)

### <a name="timezone-improvements"></a>Melhorias de timezone

Você verá o fuso horário dos registros de email no Portal, bem como dos dados exportados. Ele ficará visível em experiências como Grade de Email, Detalhes, Linha do Tempo de Email e Emails Semelhantes, para que o fuso horário do conjunto de resultados seja claro.

> [!div class="mx-imgBorder"]
> ![Exibir fuso horário no Explorer](../../media/TimezoneImprovements.png)

### <a name="update-in-the-refresh-process"></a>Atualização no processo de atualização

Alguns usuários comentaram sobre confusão com a atualização automática (por exemplo, assim que você altera a data, a página é atualizada) e a atualização manual (para outros filtros). Da mesma forma, a remoção de filtros leva à atualização automática. Alterar filtros ao modificar a consulta pode causar experiências de pesquisa inconsistentes. Para resolver esses problemas, estamos mudando para um mecanismo de filtragem manual.

Do ponto de vista da experiência, o usuário pode aplicar e remover o intervalo diferente de filtros (do conjunto de filtros e da data) e selecionar o botão atualizar para filtrar os resultados depois de definir a consulta. O botão atualizar agora também é enfatizado na tela. Também atualizamos as dicas de ferramentas relacionadas e a documentação no produto.

> [!div class="mx-imgBorder"]
> ![Selecione Atualizar para filtrar os resultados](../../media/ManualRefresh.png)

### <a name="chart-drilldown-to-add-to-filters"></a>Detalhamento do gráfico a ser acrescentado aos filtros

Agora você pode gráfico de valores de legenda para adicioná-los como filtros. Selecione o **botão Atualizar** para filtrar os resultados.

> [!div class="mx-imgBorder"]
> ![Fazer drill down em gráficos para Filtrar](../../media/ChartDrilldown.png)

### <a name="in-product-information-updates"></a>Atualizações de informações no produto

Detalhes adicionais agora estão disponíveis dentro do produto, como o número total de resultados de pesquisa dentro da grade (veja abaixo). Melhoramos rótulos, mensagens de erro e dicas de ferramentas para fornecer mais informações sobre os filtros, a experiência de pesquisa e o conjunto de resultados.

> [!div class="mx-imgBorder"]
> ![Exibir informações do produto](../../media/ProductInfo.png)

## <a name="extended-capabilities-in-threat-explorer"></a>Recursos estendidos no Explorador de Ameaças

### <a name="top-targeted-users"></a>Principais usuários direcionados

Hoje, expõemos a lista dos principais usuários direcionados na exibição malware para emails, na seção **Principais Famílias de Malware.** Também estenderemos essa exibição nos visualizações de Phish and All Email. Você poderá ver os cinco principais usuários direcionados, juntamente com o número de tentativas de cada usuário para a exibição correspondente. Por exemplo, para o ponto de vista de phishing, você verá o número de tentativas de phishing.

Você poderá exportar a lista de usuários direcionados, até um limite de 3.000, juntamente com o número de tentativas de análise offline para cada modo de exibição de email. Além disso, selecionar o número de tentativas (por exemplo, 13 tentativas na imagem abaixo) abrirá um modo de exibição filtrado no Explorador de Ameaças, para que você possa ver mais detalhes sobre emails e ameaças para esse usuário.

> [!div class="mx-imgBorder"]
> ![Principais usuários direcionados](../../media/Top_Targeted_Users.png)

### <a name="exchange-transport-rules"></a>Regras de transporte do Exchange

Como parte do enriquecimento de dados, você poderá ver todas as diferentes regras de transporte do Exchange (ETR) que foram aplicadas a uma mensagem. Essas informações estarão disponíveis na exibição de grade Email. Para exibi-la, selecione **Opções de coluna** na grade e, em **seguida, adicione a Regra** de Transporte do Exchange nas opções de coluna. Ele também estará visível no flyout **Detalhes** no email.

Você poderá ver o GUID e o nome das regras de transporte que foram aplicadas à mensagem. Você poderá pesquisar as mensagens usando o nome da regra de transporte. Esta é uma pesquisa "Contém", o que significa que você também pode fazer pesquisas parciais.

#### <a name="important-note"></a>Observação importante:

A disponibilidade de nome e pesquisa ETR depende da função específica atribuída a você. Você precisa ter uma das seguintes funções/permissões para exibir os nomes ETR e pesquisar. Se você não tiver nenhuma dessas funções atribuídas a você, não poderá ver os nomes das regras de transporte ou pesquisar mensagens usando nomes ETR. No entanto, você pode ver o rótulo ETR e as informações de GUID nos Detalhes do Email. Outras experiências de visualização de registro em Grades de Email, sub-sub-ções de email, filtros e exportação não são afetadas.

- Somente EXO - Prevenção contra Perda de Dados: Todos
- Somente EXO - O365SupportViewConfig: Todos
- Microsoft Azure Active Directory ou EXO - Administrador de Segurança: Todos
- AAD ou EXO - Leitor de Segurança: Todos
- Somente EXO - Regras de Transporte: Todos
- Somente EXO - configuração View-Only: todos

Na grade de email, no flyout Detalhes e no CSV Exportado, as ETRs são apresentadas com um Nome/GUID, conforme mostrado abaixo.

> [!div class="mx-imgBorder"]
> ![Regras de Transporte do Exchange](../../media/ETR_Details.png)

### <a name="inbound-connectors"></a>Conectores de entrada

Conectores são uma coleção de instruções que personalizam como seu email flui de e para sua organização do Microsoft 365 ou Office 365. Eles permitem que você aplique quaisquer restrições ou controles de segurança. No Explorador de Ameaças, agora você pode exibir os conectores relacionados a um email e procurar emails usando nomes de conectores.

A pesquisa por conectores é "contém" por natureza, o que significa que pesquisas parciais de palavras-chave também devem funcionar. Na exibição de grade Principal, no flyout Detalhes e no CSV Exportado, os conectores são mostrados no formato Nome/GUID, conforme mostrado aqui:

> [!div class="mx-imgBorder"]
> ![Detalhes do conector](../../media/Connector_Details.png)

## <a name="new-features-in-threat-explorer-and-real-time-detections"></a>Novos recursos no Explorador de Ameaças e detecções em tempo real

Três novos recursos estão disponíveis no Explorador de Ameaças e detecções em tempo real:

- [Visualizar o header de email e baixar o corpo do email](#preview-email-header-and-download-email-body)
- [Linha do tempo do email](#email-timeline)
- [Exportar dados de clique de URL](#export-url-click-data)

Esses novos recursos são descritos abaixo.

### <a name="preview-email-header-and-download-email-body"></a>Visualizar o header de email e baixar o corpo do email

Agora você pode visualizar um header de email e baixar o corpo do email nos Administradores do Explorador de Ameaças pode analisar mensagens de email/headers baixadas em busca de ameaças. Como baixar mensagens de email pode correr o risco de exposição de informações, esse processo é controlado pelo controle de acesso baseado em função (RBAC). Uma nova função, *Visualização,* deve ser adicionada a outro grupo de funções (como Operações de Segurança ou Administrador de Segurança) para conceder a capacidade de baixar emails e visualizar os headers na exibição de todas as mensagens de email.

As detecções do Explorer e em tempo real também receberão novos campos que fornecem uma imagem mais completa de onde suas mensagens de email chegarão. Essas alterações facilitam a busca por operações de segurança. Mas o principal resultado é que você pode saber rapidamente o local das mensagens de email com problemas.

Como isso é feito? O status de entrega agora é dividido em duas colunas:

- **Ação de entrega** - Status do email.
- **Local de entrega** - Para onde o email foi roteado.

*A ação de* entrega é a ação realizada em um email devido a políticas ou detecções existentes. Aqui estão as possíveis ações para um email:

|Entregue|Lixo eletrônico|Blocked|Substituído|
|---|---|---|---|
|O email foi entregue na caixa de entrada ou pasta de um usuário, e o usuário pode acessá-lo.|O email foi enviado para a pasta Lixo Eletrônico ou Excluído do usuário, e o usuário pode acessá-lo.|Emails que estão em quarentena, que falharam ou foram descartados. Esses emails estão inacessíveis para o usuário.|Os emails tinham anexos mal-intencionados substituídos por arquivos .txt que afirmam que o anexo era mal-intencionado.|

Veja o que o usuário pode ou não ver:

|Acessível aos usuários finais|Inacessível para usuários finais|
|---|---|
|Entregue|Blocked|
|Lixo eletrônico|Substituído|

**O local de** entrega mostra os resultados de políticas e detecções que são executados após a entrega. Ele está vinculado a **_Ação de entrega_* _. Estes são os valores possíveis:

- _Inbox ou pasta*: o email está na caixa de entrada ou em uma pasta (de acordo com suas regras de email).
- *Local ou externo:* a caixa de correio não existe na nuvem, mas é local.
- *Pasta lixo* eletrônico: o email está na pasta Lixo Eletrônico do usuário.
- *Pasta itens excluídos:* o email na pasta Itens Excluídos de um usuário.
- *Quarentena:* o email está em quarentena e não na caixa de correio de um usuário.
- *Falha:* o email falhou ao alcançar a caixa de correio.
- *Descartado:* o email se perdeu em algum lugar no fluxo de emails.

### <a name="email-timeline"></a>Linha do tempo do email

A **linha do tempo de** email é um novo recurso do Explorer que melhora a experiência de busca de administradores. Isso reduz o tempo gasto verificando locais diferentes para tentar entender o evento. Quando ocorrem vários eventos ao mesmo tempo que um email chega, esses eventos são exibidos em um modo de exibição de linha do tempo. Alguns eventos que ocorrem com seu email após a entrega são capturados na **coluna Ação** especial. Os administradores podem combinar informações da linha do tempo com a ação especial realizada na postagem de email para obter informações sobre como suas políticas funcionam, onde o email foi finalmente roteado e, em alguns casos, qual foi a avaliação final.

Para saber mais, confira [Investigar e remediar emails mal-intencionados que foram entregues no Office 365.](investigate-malicious-email-that-was-delivered.md)

### <a name="export-url-click-data"></a>Exportar dados de clique de URL

Agora você pode exportar relatórios de cliques de URL para o Microsoft Excel para exibir sua **ID** de mensagem de rede e clicar em **veredito,** o que ajuda a explicar de onde o tráfego de clique de URL se originou. Veja como funciona: no Gerenciamento de Ameaças na barra de início rápido do Office 365, siga esta cadeia:

**Explorer** \> **Exibir Phish** \> **Cliques** \> **As URLs principais** ou os **Cliques Principais da URL** \> selecionam qualquer registro para abrir o flyout da URL.

Ao selecionar uma URL na lista, você  verá um novo botão Exportar no painel do sub-painel. Use este botão para mover dados para uma planilha do Excel para facilitar o relatório.

Siga este caminho para chegar ao mesmo local no relatório de detecções em tempo real:

**Explorer** \> **Detecções em tempo real** \> **Exibir Phish** \> **URLs** \> **URLs Principais** ou **Cliques Principais** Selecione qualquer registro para abrir o flyout da URL, navegue \> até a guia \> **Cliques.**

> [!TIP]
> A ID de Mensagem de Rede mapeia o clique de volta para emails específicos quando você pesquisa na ID por meio do Explorer ou ferramentas de terceiros associadas. Essas pesquisas identificam o email associado a um resultado de clique. Ter a ID de Mensagem de Rede correlacionada torna a análise mais rápida e eficiente.

> [!div class="mx-imgBorder"]
> ![Guia Cliques no Explorer](../../media/tp_ExportClickResultAndNetworkID.png)

## <a name="see-malware-detected-in-email-by-technology"></a>Ver malware detectado no email por tecnologia

Suponha que você queira ver malware detectado em emails organizados pela tecnologia do Microsoft 365. Para fazer isso, use o [email >](threat-explorer-views.md#email--malware) exibição malware do Explorer (ou detecções em tempo real).

1. No Centro de Conformidade & segurança ( ), escolha Explorador de gerenciamento de ameaças <https://protection.office.com>  \>  (ou **detecções em tempo real**). (Este exemplo usa o Explorer.)

2. No menu **Exibir,** escolha **Malware de Email.** \> 

   > [!div class="mx-imgBorder"]
   > ![Menu Exibir do Explorer](../../media/ExplorerViewEmailMalwareMenu.png)

3. Clique **em Remetente** e escolha a tecnologia de **Detecção** \> **Básica.**

   Suas tecnologias de detecção agora estão disponíveis como filtros para o relatório.

   > [!div class="mx-imgBorder"]
   > ![Tecnologias de detecção de malware](../../media/ExplorerEmailMalwareDetectionTech.png)

4. Escolha uma opção. Em seguida, **selecione o botão** Atualizar para aplicar esse filtro.

   > [!div class="mx-imgBorder"]
   > ![Tecnologia de detecção selecionada](../../media/ExplorerEmailMalwareDetectionTechATP.png)

O relatório é atualizado para mostrar os resultados que o malware detectou no email, usando a opção de tecnologia selecionada. A partir daqui, você pode realizar análises posteriores.

## <a name="view-phishing-url-and-click-verdict-data"></a>Exibir URL de phishing e clicar em dados de veredito

Suponha que você queira ver tentativas de phishing por meio de URLs por email, incluindo uma lista de URLs que foram permitidas, bloqueadas e substituídos. Para identificar URLs que foram clicadas, os [Links Seguros](atp-safe-links.md) devem ser configurados. Certifique-se de configurar as políticas de [Links](set-up-atp-safe-links-policies.md) seguros para proteção de tempo de clique e registro em log de vereditos de clique por Links seguros.

Para revisar URLs de phishing em mensagens e cliques em URLs em mensagens de phishing, use a exibição [   >  **phishing**](threat-explorer-views.md#email--phish) de email do Explorer ou detecções em tempo real.

1. No Centro de Conformidade & segurança ( ), escolha Explorador de gerenciamento de ameaças <https://protection.office.com>  \>  (ou **detecções em tempo real**). (Este exemplo usa o Explorer.)

2. No menu **Exibir,** escolha **Phishing de Email.** \> 

   > [!div class="mx-imgBorder"]
   > ![Menu Exibir do Explorer no contexto de phishing](../../media/ExplorerViewEmailPhishMenu.png)

3. Clique **em Remetente** e escolha **URLs Clique** em \> **veredito.**

4. Selecione uma ou mais opções, como Bloqueado e Bloqueado,  e selecione o botão Atualizar na mesma linha que as opções para aplicar esse filtro.  (Não atualize a janela do navegador.)

   > [!div class="mx-imgBorder"]
   > ![URLs e vereditos de clique](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)

   O relatório é atualizado para mostrar duas tabelas de URL diferentes na guia URL sob o relatório:

   - **As PRINCIPAIS URLs** são as URLs nas mensagens filtradas para baixo e a ação de entrega de email conta para cada URL. Na exibição de email de phishing, essa lista normalmente contém URLs legítimas. Os invasores incluem uma mistura de URLs boas e ruins em suas mensagens para tentar entregar, mas eles fazem com que os links mal-intencionados pareçam mais interessantes. A tabela de URLs é ordenada por contagem total de emails, mas essa coluna está oculta para simplificar a exibição.

   - **Os cliques principais** são as URLs de links seguros que foram clicadas, ordenadas por contagem total de cliques. Essa coluna também não é exibida, para simplificar a exibição. As contagens totais por coluna indicam a contagem de vereditos de clique de Links seguros para cada URL clicada. Na exibição de email de phishing, geralmente são URLs suspeitas ou mal-intencionadas. Mas a exibição pode incluir URLs que não são ameaças, mas que estão em mensagens de phishing. Os cliques de URL em links não mapeados não aparecem aqui.

   As duas tabelas de URL mostram as principais URLs em mensagens de email de phishing por ação de entrega e local. As tabelas mostram cliques de URL que foram bloqueados ou visitados apesar de um aviso, para que você possa ver quais links inválidos potenciais foram apresentados aos usuários e que o usuário clicou. A partir daqui, você pode realizar análises posteriores. Por exemplo, abaixo do gráfico, você pode ver as principais URLs em mensagens de email que foram bloqueadas no ambiente da sua organização.

   > [!div class="mx-imgBorder"]
   > ![URLs do Explorer que foram bloqueadas](../../media/ExplorerPhishClickVerdictURLs.png)

   Selecione uma URL para exibir informações mais detalhadas.

   > [!NOTE]
   > Na caixa de diálogo do flyout da URL, a filtragem em mensagens de email é removida para mostrar a exibição completa da exposição da URL em seu ambiente. Isso permite filtrar mensagens de email com as que você está preocupado no Explorer, encontrar URLs específicas que são possíveis ameaças e, em seguida, expandir seu entendimento da exposição de URL em seu ambiente (por meio da caixa de diálogo de detalhes da URL) sem precisar adicionar filtros de URL ao próprio exibição do Explorer.

### <a name="interpretation-of-click-verdicts"></a>Interpretação de vereditos de clique

Nos flyouts email ou URL, cliques principais, bem como dentro de nossas experiências de filtragem, você verá valores de veredito de clique diferentes:

- **Nenhuma:** Não é possível capturar o veredito da URL. O usuário pode ter clicado na URL.
- **Permitido:** O usuário teve permissão para navegar até a URL.
- **Bloqueado:** O usuário foi impedido de navegar até a URL.
- **Veredito pendente:** O usuário foi apresentado com a página de detonação pendente.
- **Bloqueado substituído:** O usuário foi impedido de navegar diretamente para a URL. Mas o usuário sobrecarregue o bloco para navegar até a URL.
- **Veredito pendente ignorado:** O usuário foi apresentado com a página de detonação. Mas o usuário overrode a mensagem para acessar a URL.
- **Erro:** O usuário foi apresentado com a página de erro ou ocorreu um erro ao capturar o veredito.
- **Falha:** Ocorreu uma exceção desconhecida durante a captura do veredito. O usuário pode ter clicado na URL.

## <a name="review-email-messages-reported-by-users"></a>Revisar mensagens de email relatadas pelos usuários

Suponha que você queira ver mensagens de email que os usuários em sua [](enable-the-report-message-add-in.md) organização relataram como Lixo Eletrônico *,* Não Lixo Eletrônico ou *Phishing* por meio do complemento Mensagem de Relatório ou do complemento [Phishing de Relatório.](enable-the-report-phish-add-in.md) Para vê-los, use a exibição [   >  **Envios**](threat-explorer-views.md#email--submissions) de Email do Explorer (ou detecções em tempo real).

1. No Centro de Conformidade & segurança ( ), escolha Explorador de gerenciamento de ameaças <https://protection.office.com>  \>  (ou **detecções em tempo real**). (Este exemplo usa o Explorer.)

2. No menu **Exibir,** escolha  \> **Envios de Email.**

   > [!div class="mx-imgBorder"]
   > ![Menu Exibir do Explorer para emails](../../media/explorer-view-menu-email-user-reported.png)

3. Clique **em Remetente** e escolha Tipo de **Relatório** \> **Básico.**

4. Selecione uma opção, como **Phishing,** e selecione o **botão Atualizar.**

   > [!div class="mx-imgBorder"]
   > ![Phishing relatado pelo usuário](../../media/EmailUserReportedReportType.png)

O relatório é atualizado para mostrar dados sobre mensagens de email que as pessoas em sua organização relataram como uma tentativa de phishing. Você pode usar essas informações para realizar análises adicionais e, se necessário, ajustar suas políticas [anti-phishing no Microsoft Defender para Office 365.](configure-atp-anti-phishing-policies.md)

## <a name="start-automated-investigation-and-response"></a>Iniciar investigação e resposta automatizadas

> [!NOTE]
> Recursos automatizados de investigação e resposta estão disponíveis *no Microsoft Defender para Office 365 Plano 2* e Office *365 E5.*

[A investigação e resposta automatizadas](automated-investigation-response-office.md) podem economizar tempo e esforço da equipe de operações de segurança investigando e mitigando ataques cibernéticos. Além de configurar alertas que podem disparar um manual de segurança, você pode iniciar um processo automatizado de investigação e resposta a partir de uma exibição no Explorer. Para obter detalhes, consulte [Exemplo: Um administrador de segurança dispara uma investigação do Explorer](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).

## <a name="more-ways-to-use-explorer-and-real-time-detections"></a>Mais maneiras de usar detecções do Explorer e em tempo real

Além dos cenários descritos neste artigo, você tem muito mais opções de relatório disponíveis com o Explorer (ou detecções em tempo real). Confira os seguintes artigos:

- [Localizar e investigar emails mal-intencionados entregues](investigate-malicious-email-that-was-delivered.md)
- [Exibir arquivos mal-intencionados detectados no SharePoint Online, OneDrive e Microsoft Teams](malicious-files-detected-in-spo-odb-or-teams.md)
- [Obter uma visão geral das exibições no Explorador de Ameaças (e detecções em tempo real)](threat-explorer-views.md)
- [Relatório de status de proteção contra ameaças](view-email-security-reports.md#threat-protection-status-report)
- [Investigação e resposta automatizadas na Proteção contra Ameaças da Microsoft](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)

## <a name="required-licenses-and-permissions"></a>Licenças e permissões necessárias

Você deve ter [o Microsoft Defender para Office 365](office-365-atp.md) para usar o Explorer ou detecções em tempo real.

- O Explorer está incluído no Defender para Office 365 Plano 2.
- O relatório de detecções em tempo real está incluído no Defender para Office 365 Plano 1.
- Planeje atribuir licenças para todos os usuários que devem ser protegidos pelo Defender para Office 365. As detecções do Explorer e em tempo real mostram dados de detecção para usuários licenciados.

Para exibir e usar detecções do Explorer ou em tempo real, você deve ter as permissões apropriadas, como as concedidas a um administrador de segurança ou leitor de segurança.

- Para o Centro de Conformidade & segurança, você deve ter uma das seguintes funções atribuídas:

  - Gerenciamento de Organização
  - Administrador de Segurança (isso pode ser atribuído no centro de administração do Azure Active Directory <https://aad.portal.azure.com> )
  - Leitor de segurança

- Para o Exchange Online, você deve ter uma das seguintes funções atribuídas no Centro de administração do Exchange () ou <https://admin.protection.outlook.com/ecp/> no [PowerShell do Exchange Online:](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)

  - Gerenciamento de Organização
  - Gerenciamento de Organização Somente Exibição
  - Destinatários Somente para Exibição
  - Gerenciamento de Conformidade

Para saber mais sobre funções e permissões, consulte os seguintes recursos:

- [Permissões no Centro de Segurança e Conformidade](permissions-in-the-security-and-compliance-center.md)
- [Permissões de recursos no Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)

## <a name="differences-between-threat-explorer-and-real-time-detections"></a>Diferenças entre o Explorador de Ameaças e detecções em tempo real

- O *relatório de detecções em tempo* real está disponível no Defender para Office 365 Plano 1. *O Explorador de* Ameaças está disponível no Defender para Office 365 Plano 2.
- O relatório de detecções em tempo real permite que você veja detecções em tempo real. O Explorador de Ameaças também faz isso, mas também fornece detalhes adicionais para um determinado ataque.
- Uma *exibição todos os emails* está disponível no Explorador de Ameaças, mas não no relatório de detecções em tempo real.
- Mais recursos de filtragem e ações disponíveis estão incluídos no Explorador de Ameaças. Para obter mais informações, consulte [o Microsoft Defender para Office 365 Service Description:](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)disponibilidade de recursos nos planos do Defender para Office 365.
