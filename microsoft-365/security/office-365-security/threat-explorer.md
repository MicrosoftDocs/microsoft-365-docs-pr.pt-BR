---
title: Gerenciador de ameaças e detecções em tempo real
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 82ac9922-939c-41be-9c8a-7c75b0a4e27d
ms.collection:
- M365-security-compliance
description: Saiba como usar o Explorer e as detecções em tempo real no centro de conformidade de segurança &amp; para investigar e responder a ameaças com eficácia e eficiência.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 32ff9f2c8d009b4c9b05c12ba4e785e59cb182e7
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328078"
---
# <a name="threat-explorer-and-real-time-detections"></a>Gerenciador de ameaças e detecções em tempo real

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Se sua organização tem a [proteção avançada contra ameaças do office 365](office-365-atp.md) (Office 365 ATP) e você tem as [permissões necessárias](#required-licenses-and-permissions), você tem as detecções do **Explorer** ou do **tempo real** (anteriormente conhecida como *relatórios em tempo real* , [consulte What ' s New](#new-features-in-threat-explorer-and-real-time-detections)!). No centro de conformidade & segurança, vá para **Gerenciamento de ameaças**e escolha as detecções do **Explorer** _ou_ **em tempo real**.

|Com o plano ATP 2, você vê:|Com o plano ATP 1, você vê:|
|---|---|
|![Explorador de ameaças](../../media/threatmgmt-explorer.png)|![Detecções em tempo real](../../media/threatmgmt-realtimedetections.png)|
|

Com o Explorer (ou detecções em tempo real), você tem um relatório poderoso que permite que sua equipe de operações de segurança investigue e responda às ameaças de forma eficaz e eficiente. O relatório é semelhante à seguinte imagem:

![Vá para o Gerenciador de gerenciamento de ameaças \>](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

Com esse relatório, você pode:

- [Consulte malware detectado pelos recursos de segurança do Microsoft 365](#see-malware-detected-in-email-by-technology)
- [Exibir dados sobre URLs de phishing e clicar em veredicto](#view-data-about-phishing-urls-and-click-verdict)
- [Iniciar um processo de investigação e resposta automatizado de um modo de exibição no Explorer](#start-automated-investigation-and-response) (apenas plano ATP 2)
- ... [Investigue emails mal-intencionados e muito mais](#more-ways-to-use-explorer-or-real-time-detections)!

## <a name="experience-improvements-to-threat-explorer-and-real-time-detections"></a>Aprimoramentos de experiência para o explorador de ameaças e detecções em tempo real

Como parte do aprimoramento do processo de caça, fizemos algumas atualizações no Gerenciador de ameaças e nas detecções em tempo real. Eles são aprimoramentos de "experiência", com o objetivo de tornar a experiência de busca mais consistente. Essas alterações são descritas abaixo:

- [Melhorias de fuso horário](#timezone-improvements)
- [Atualização no processo de atualização](#update-in-the-refresh-process)
- [Detalhamento de gráfico para adicionar a filtros](#chart-drilldown-to-add-to-filters)
- [Atualizações de informações do produto](#in-product-information-updates)

### <a name="timezone-improvements"></a>Melhorias de fuso horário

Mostraremos o fuso horário dos registros de email no portal, bem como os dados exportados. O fuso horário ficará visível em experiências como grade de email, submenu de detalhes, linha do tempo de email e emails semelhantes, para que o fuso horário do conjunto de resultados seja claro para o usuário.

![Exibir fuso horário no Explorer](../../media/TimezoneImprovements.png)

### <a name="update-in-the-refresh-process"></a>Atualização no processo de atualização

Ouvimos comentários em relação à confusão com a atualização automática (por exemplo, para data, assim que você alterar a data, a página seria atualizada) e a atualização manual (para outros filtros). Da mesma forma, remover filtros leva à atualização automática, isso causa situações em que alterar os diferentes filtros enquanto modifica a consulta pode causar experiências de pesquisa inconsistentes. Para resolver isso, estamos migrando para um mecanismo de filtragem manual.
A partir de um ponto de vista da experiência, o usuário pode aplicar e remover o intervalo diferente de filtros (do conjunto de filtros e data) e pressionar o botão atualizar para filtrar os resultados depois que eles forem feitos com a definição da consulta. O botão atualizar também foi atualizado para chamá-lo com clareza na tela. Também atualizamos as dicas de ferramentas e a documentação do produto em torno dessa alteração.

![Clique em atualizar para filtrar resultados](../../media/ManualRefresh.png)

### <a name="chart-drilldown-to-add-to-filters"></a>Detalhamento de gráfico para adicionar a filtros

Agora, você poderá clicar nos valores de legenda do gráfico para adicionar esse valor como um filtro. Observe que você ainda terá que clicar no botão atualizar para filtrar os resultados como parte da alteração descrita acima.

![Análise de gráficos para filtrar](../../media/ChartDrilldown.png)

### <a name="in-product-information-updates"></a>Atualizações de informações do produto

Você também deve ver detalhes adicionais no produto. Por exemplo, o número total de resultados de pesquisa dentro da grade (veja abaixo), bem como melhorias em relação a rótulos, mensagens de erro e dicas de ferramentas, para fornecer mais informações sobre filtros, experiência de pesquisa e conjunto de resultados.

![Exibir informações no produto](../../media/ProductInfo.png)

## <a name="extended-capabilities-in-threat-explorer"></a>Recursos estendidos no explorador de ameaças

### <a name="top-targeted-users"></a>Principais usuários direcionados

Hoje, expostos a lista dos principais usuários direcionados no modo de exibição de malware para emails (na seção principais famílias de malware). Estenderemos a extensão desse modo de exibição no phishing e em todos os modos de exibição de email, onde você poderá ver os cinco principais usuários direcionados junto com o número de tentativas para cada usuário para o modo de exibição correspondente (por exemplo, para o modo de exibição de phishing, você poderá ver o número de tentativas de Phish).
Você também será capaz de exportar a lista de usuários direcionados até um limite de 3000, juntamente com o número de tentativas para a análise offline para cada exibição de email. Além disso, selecione não. de tentativas (por exemplo, 13 tentativas abaixo) abriria um modo de exibição filtrado no explorador de ameaças, para que você possa ver mais detalhes nos emails e ameaças desse usuário.

![Principais usuários direcionados](../../media/Top_Targeted_Users.png)


### <a name="exchange-transport-rules"></a>Regras de transporte do Exchange
Como parte do enriquecimento de dados, você também deve ser capaz de ver todas as diferentes regras de transporte que foram aplicadas a uma mensagem. Essas informações estarão presentes no modo de exibição de grade de email (para exibir isso, selecione opções de coluna na grade e Adicionar regra de transporte do Exchange das opções de coluna na grade), bem como submenu de detalhes no email.
Você poderá ver o GUID, bem como o nome das regras de transporte que foram aplicadas à mensagem. Além disso, você poderá pesquisar as mensagens usando o nome da regra de transporte. Essa seria uma pesquisa "contém", o que significa que você também poderá pesquisar usando pesquisas parciais.

#### <a name="important-note"></a>Observação importante:
A pesquisa e o nome da disponibilidade do ETR dependeriam da função específica que foi atribuída a você. Você precisará ter uma das seguintes funções/permissões para exibir os nomes e a pesquisa do ETR.  Se você não tiver uma das funções a seguir atribuídas a você, não poderá ver os nomes das regras de transporte e pesquisar as mensagens usando os nomes ETR. No entanto, você poderá ver as informações de rótulo e GUID do ETR nos detalhes do email. Suas outras experiências em relação à exibição de registros em grades de email, submenus de email, filtros e exportação não são impactadas.

- EXO-prevenção de perda de dados: ALL
- Somente EXO-O365SupportViewConfig: ALL
- AAD ou EXO-administrador de segurança: todos
- AAD ou EXO-leitor de segurança: todos
- Regras de transporte somente EXO: ALL
- Somente EXO-configuração somente exibição: todas

Na grade de emails, no submenu detalhes e no CSV exportado, o ETRs é apresentado com um nome/GUID, conforme mostrado abaixo.

![Regras de transporte do Exchange](../../media/ETR_Details.png)

### <a name="inbound-connectors"></a>Conectores de entrada

Os conectores são uma coleção de instruções que personalizam a forma como seu email flui para e a partir da sua organização do Microsoft 365 ou do Office 365, com a capacidade de aplicar qualquer restrição de segurança ou controles. No explorador de ameaças, agora você terá a capacidade de exibir os conectores relacionados a um email, bem como Pesquisar emails usando os nomes de conectores.
A pesquisa de conectores é ' Contains ', por natureza, que significa que as pesquisas parciais de palavra-chave também devem funcionar.
Dentro do modo de exibição de grade principal, o submenu detalhes e o CSV exportado, os conectores são mostrados no formato de nome/GUID, conforme mostrado abaixo:

![Detalhes do conector](../../media/Connector_Details.png)

## <a name="new-features-in-threat-explorer-and-real-time-detections"></a>Novos recursos no Gerenciador de ameaças e detecções em tempo real

Três novos recursos adicionados ao Gerenciador de ameaças e às detecções em tempo real:

- [Visualizar o cabeçalho de email e baixar o corpo do email](#preview-email-header-and-download-email-body)
- [Linha do tempo de email](#email-timeline)
- [Exportar URL clique em dados](#export-url-click-data)

Esses novos recursos estão descritos abaixo.

### <a name="preview-email-header-and-download-email-body"></a>Visualizar o cabeçalho de email e baixar o corpo do email

A capacidade de Visualizar um cabeçalho de email e baixar o corpo do email são novos recursos disponíveis no explorador de ameaças. Os administradores poderão analisar os cabeçalhos/mensagens de email baixados para ameaças. Como o download de mensagens de email pode arriscar a exposição de informações, esse processo é controlado pelo controle de acesso baseado em funções (RBAC). Uma nova função, *Visualização*, deve ser adicionada a outro grupo de função (como operações de segurança ou administrador de segurança) para conceder a capacidade de baixar emails e Visualizar cabeçalhos em todas as mensagens de email exibir.

Mas o Explorer (e as detecções em tempo real) também adiciona novos campos criados para fornecer uma imagem mais completa de onde suas mensagens de email estão no terreno. Parte da meta dessa alteração é tornar a busca mais fácil para pessoas de operações de segurança, mas o resultado líquido é saber o local das mensagens de email de problemas em um relance.

Como isso é feito? O status de entrega agora é dividido em duas colunas:

- **Ação de entrega** -Qual é o status desse email?
- **Local de entrega** -onde esse email foi roteado como resultado?

A ação de entrega é a ação realizada em um email devido a políticas ou detecções existentes. Veja a seguir as possíveis ações que um email pode executar:

|Gerados|Lixo eletrônico|Blocked|Devido|
|---|---|---|---|
|O email foi entregue à caixa de entrada ou pasta de um usuário, e o usuário pode acessá-lo diretamente.|O email foi enviado à pasta de lixo eletrônico ou à pasta excluída do usuário, e o usuário tem acesso a emails nessas pastas.|Todos os emails colocados em quarentena, que falharam ou foram descartados. Isso é completamente inacessível pelo usuário!|Qualquer email onde anexos mal-intencionados são substituídos por arquivos. txt que indicam que o anexo era mal-intencionado.|

|Gerados|Lixo eletrônico|Blocked|Devido|
|---|---|---|---|
|O email foi entregue na caixa de entrada do usuário ou em outra pasta, e o usuário pode acessá-lo diretamente.|O email foi enviado para a pasta de lixo eletrônico do usuário ou para a pasta excluída e o usuário tem acesso a mensagens de email nessas pastas.|Qualquer mensagem de email em quarentena, que falhou ou foi interrompida, e não pode ser acessada pelo usuário.|Quaisquer mensagens de email em que anexos mal-intencionados foram substituídos por arquivos. txt que indicam que os anexos foram mal-intencionados.|
|

E aqui está o que o usuário pode ver e o que eles não podem:

|Acessível para os usuários finais|Inacessível para os usuários finais|
|---|---|
|Gerados|Blocked|
|Lixo eletrônico|Devido|

O local de entrega mostra os resultados das políticas e detecções que executam post-Delivery. Ele está vinculado a uma ação de entrega. Este campo foi adicionado para dar informações sobre a ação tomada quando um email de problema é encontrado. Estes são os possíveis valores de local de entrega:

- **Caixa de entrada ou pasta**: o email está na caixa de entrada ou uma pasta (de acordo com suas regras de email).
- **Local ou externo**: a caixa de correio não existe na nuvem, mas está no local.
- **Pasta de lixo eletrônico**: o email está na pasta lixo eletrônico de um usuário.
- **Pasta itens excluídos**: o email na pasta itens excluídos de um usuário.
- **Quarantine**: o email em quarentena e não está na caixa de correio de um usuário.
- **Falha**: o email não pôde chegar à caixa de correio.
- **Descartado**: o email é perdido em algum lugar no fluxo de emails.

### <a name="email-timeline"></a>Linha do tempo de email

A **linha do tempo de email** é outro novo recurso do Explorer destinado a tornar a experiência de busca melhor para administradores. Ele reduz a randomização porque há menos tempo gasto na verificação de locais diferentes para tentar entender o evento. Quando vários eventos ocorrem ou próximos à mesma hora em um email, esses eventos serão exibidos em um modo de exibição de linha do tempo. Na verdade, alguns eventos que acontecerão após a entrega ao seu email serão capturados na coluna "ação especial". A combinação das informações da linha do tempo dos emails com a ação especial tomada no envio de mensagens enviará aos administradores informações sobre como as políticas funcionam, onde o email foi finalmente encaminhado e, em alguns casos, qual era a avaliação final.

Para mais informações sobre a investigação de mensagens de email mal-intencionadas, consulte [investigar e corrigir emails mal-intencionados que foram entregues no Office 365](investigate-malicious-email-that-was-delivered.md).

### <a name="export-url-click-data"></a>Exportar URL clique em dados

Além disso, agora você poderá exportar relatórios para cliques de URL para o Microsoft Excel a fim de exibir a ID da mensagem de rede e o clique em veredicto, tornando a tarefa de compreensão onde sua URL clica em tráfego originado mais facilmente. Veja como funciona. A partir do gerenciamento de ameaças no Office 365 Quick-Launch, clique nesta cadeia:

**Explorer** \> **Exibir Phish** \> **Clica em** \> **Principais URLs ou principais cliques** \> de URL **Clique em qualquer registro para abrir o submenu URL**

Ao clicar em uma URL na lista, você verá um novo botão de exportação no painel de saída. Use este botão para mover dados para uma planilha do Excel para facilitar o relatório.

Você pode obter o mesmo local no relatório de detecções em tempo real da seguinte maneira:

**Explorer** \> Detecções em tempo **real** \> **Exibir Phish** \> **URLs** \> **Principais URLs ou principais cliques** \> **Clique em qualquer registro para abrir o submenu URL** \> **Navegue até a guia cliques.**

> [!TIP]
> Mapeamento de ID de mensagem de rede o clique em voltar para emails específicos quando você pesquisa pelo Explorer ou ferramentas de terceiros associadas via ID de mensagem de rede. A pesquisa da ID da mensagem de rede fornecerá aos administradores o email específico associado a um clique. Na exportação, a identificação de correlação da ID da mensagem de rede realiza uma análise mais rápida e eficiente.

![Guia cliques no Explorer](../../media/tp_ExportClickResultAndNetworkID.png)

## <a name="see-malware-detected-in-email-by-technology"></a>Confira malware detectado em email por tecnologia

Suponha que você queira ver o malware detectado no email, pela tecnologia Microsoft 365. Para fazer isso, use o [>](threat-explorer-views.md#email--malware) modo de exibição de malware de email do Explorer (ou detecções em tempo real).

1. No centro de conformidade e segurança & ( [https://protection.office.com](https://protection.office.com) ), escolha Gerenciador de **Gerenciamento de ameaças**  >  **Explorer** (ou **detecções em tempo real**). (Este exemplo usa o Explorer.)

2. No menu **Exibir** , escolha malware de **email**  >  **Malware**.

   ![Menu Exibir para Explorer](../../media/ExplorerViewEmailMalwareMenu.png)

3. Clique em **remetente**e escolha tecnologia **Basic**de  >  **detecção**básica.

   Agora, suas tecnologias de detecção estão disponíveis como filtros para o relatório.

   ![Tecnologias de detecção de malware](../../media/ExplorerEmailMalwareDetectionTech.png)

4. Selecione uma opção e, em seguida, clique no botão **Atualizar** para aplicar esse filtro.

   ![Tecnologia de detecção selecionada](../../media/ExplorerEmailMalwareDetectionTechATP.png)

O relatório é atualizado para mostrar o malware de resultados detectado no email, usando a opção de tecnologia que você selecionou. A partir daqui, você pode realizar uma análise adicional.

## <a name="view-data-about-phishing-urls-and-click-verdict"></a>Exibir dados sobre URLs de phishing e clicar em veredicto

Suponha que você queira ver as tentativas de phishing por meio de URLs no email, incluindo uma lista de URLs que foram permitidas, bloqueadas e substituídas. A identificação de URLs que foram clicadas exige que os [links seguros](atp-safe-links.md) sejam configurados. Certifique-se de ter configurado [políticas de links seguros](set-up-atp-safe-links-policies.md) para proteção de tempo de clique e log de clique em verdicts por links seguros.

Para examinar as URLs de phishing em mensagens e clicar em URLs nas mensagens de phishing, use a exibição de [Email > Phish](threat-explorer-views.md#email--phish) do Explorer (ou detecções em tempo real).

1. No centro de conformidade e segurança & ( [https://protection.office.com](https://protection.office.com) ), escolha Gerenciador de **Gerenciamento de ameaças**  >  **Explorer** (ou **detecções em tempo real**). (Este exemplo usa o Explorer.)

2. No menu **Exibir** , escolha phishing de **email**  >  **Phish**.

   ![Menu Exibir para Explorer](../../media/ExplorerViewEmailPhishMenu.png)

3. Clique em **remetente**e, em seguida, escolha **URLs**  >  **clique em veredicto**.

4. Selecione uma ou mais opções, como **bloqueado** e **substituído**e, em seguida, clique no botão **Atualizar** que está na mesma linha que as opções para aplicar esse filtro. (Não atualize a janela do navegador.)

   ![URLs e clique em verdicts](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)

    O relatório é atualizado para mostrar duas tabelas de URL diferentes na guia URL no relatório:

   - As **principais URLs** são as URLs contidas nas mensagens que foram filtradas para baixo e a ação de entrega de emails conta para cada URL. No modo de exibição email de phishing, essa lista normalmente conterá URLs legítimas. Os invasores incluem uma mistura de URLs boas e ruins nas mensagens para tentar obtê-las, mas eles farão com que os links mal-intencionados sejam mais interessantes para o usuário clicar. A tabela de URLs é classificada pela contagem total de emails (mas observe que essa coluna está oculta para simplificar o modo de exibição).

   - Os **principais cliques** são as URLs encapsuladas de links seguros que foram clicados, classificados por contagem de clique total (essa coluna também não é exibida para simplificar o modo de exibição). Total de contagens por coluna indicam os links seguros clique em contagem de veredicto para cada URL clicada. No modo de exibição email de phishing, essas URLs são mais frequentes ou mal-intencionadas, mas podem incluir URLs que não são ameaças, mas que estão em mensagens de phishing. Os cliques de URL em links não ajustados não aparecerão aqui.

   As duas tabelas de URL mostram as principais URLs nas mensagens de email de phishing por ação de entrega e local, e mostram cliques de URL que foram bloqueados (ou visitados apesar de um aviso) para que você possa entender quais links defeituosos possíveis foram recebidos por usuários e interagem com os usuários. A partir daqui, você pode realizar uma análise adicional. Por exemplo, abaixo do gráfico, você pode ver as principais URLs nas mensagens de email que foram bloqueadas no ambiente da sua organização.

   ![URLs do Explorer que foram bloqueadas](../../media/ExplorerPhishClickVerdictURLs.png)

   Selecione uma URL para exibir informações mais detalhadas.

   > [!NOTE]
   > Na caixa de diálogo de submenu URL, a filtragem em mensagens de email é removida para mostrar a exibição completa da exposição da URL em seu ambiente. Isso permite que você filtre mensagens de email no Explorer para as quais você está preocupado, encontre URLs específicas que são ameaças potenciais e, em seguida, expanda a compreensão da exposição de URL no seu ambiente (por meio da caixa de diálogo de detalhes da URL) sem ter que adicionar filtros de URL à própria exibição do Explorer.

### <a name="interpretation-of-different-click-verdicts"></a>Interpretação de diferentes clique em verdicts

Dentro dos submenus de email ou URL, principais cliques e em nossas experiências de filtragem, você verá diferentes valores de clique como parte de sua experiência de busca. Veja a seguir os valores possíveis de Click verdicts e sua interpretação:

- **Nenhum**: não foi possível capturar o veredicto para a URL. O usuário pode ter clicado através da URL.
- **Permitido**: o usuário tem permissão para navegar até a URL.
- **Bloqueado**: o usuário foi impedido de navegar para a URL.
- **Veredicto pendente**: o usuário foi apresentado com a página de acionamento pendente.
- **Bloqueado, substituído**: o usuário foi impedido de navegar para a URL; no entanto, o usuário overrode o bloco para navegar até a URL.
- **Veredicto pendente ignorada**: o usuário foi apresentado com a página acionamento; no entanto, o usuário overrode a página para navegar até a URL.
- **Erro**: o usuário foi apresentado com a página de erro. Isso também pode significar que houve um erro ao capturar o veredicto.
- **Falha**: houve uma exceção desconhecida ao capturar o veredicto. O usuário pode ter clicado através da URL.

## <a name="review-email-messages-reported-by-users"></a>Analisar mensagens de email relatadas por usuários

Suponha que você queira ver as mensagens de email que os usuários em sua organização relataram como lixo eletrônico, não lixo eletrônico ou phishing usando o [suplemento de mensagem de relatório para Outlook e Outlook na Web](enable-the-report-message-add-in.md). Para fazer isso, use a exibição de [Email > envios](threat-explorer-views.md#email--submissions) do Explorer (ou detecções em tempo real).

1. No centro de conformidade e segurança & ( [https://protection.office.com](https://protection.office.com) ), escolha Gerenciador de **Gerenciamento de ameaças**  >  **Explorer** (ou **detecções em tempo real**). (Este exemplo usa o Explorer.)

2. No menu **Exibir** , escolha **Email**  >  **envios**de email.

   ![Menu Exibir para Explorer](../../media/explorer-view-menu-email-user-reported.png)

3. Clique em **remetente**e, em seguida, escolha tipo de **Basic**  >  **relatório**básico.

4. Selecione uma opção, como **Phish**, e clique no botão **Atualizar** .

   ![Phishing relatado pelo usuário](../../media/EmailUserReportedReportType.png)

O relatório é atualizado para mostrar dados sobre mensagens de email que as pessoas em sua organização relataram como uma tentativa de phishing. Você pode usar essas informações para realizar mais análises e, se necessário, ajustar as [políticas de anti-phishing da ATP](configure-atp-anti-phishing-policies.md).

## <a name="start-automated-investigation-and-response"></a>Iniciar investigação e resposta automatizadas

> [!NOTE]
> Os recursos de investigação e resposta automatizados estão disponíveis no **office 365 ATP Plan 2** e no **Office 365 E5**.

(Novo!) A [investigação e a resposta automatizadas](automated-investigation-response-office.md) podem salvar sua equipe de operações de segurança muito tempo e esforço na investigação e redução do cyberattacks. Além de configurar alertas que podem acionar um guia de segurança, você pode iniciar um processo de investigação e resposta automatizado de um modo de exibição no Explorer.

Para obter detalhes sobre isso, consulte [example: um administrador de segurança dispara uma investigação do Explorer](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).

## <a name="more-ways-to-use-explorer-or-real-time-detections"></a>Outras maneiras de usar o Explorer (ou detecções em tempo real)

Além dos cenários descritos neste artigo, você tem muito mais opções de relatórios disponíveis com o Explorer (ou detecções em tempo real).

- [Localizar e investigar emails mal-intencionados entregues](investigate-malicious-email-that-was-delivered.md)
- [Relatório de status de proteção contra ameaças](view-email-security-reports.md#threat-protection-status-report)
- [Obter uma visão geral dos modos de exibição no explorador de ameaças (e detecções em tempo real)](threat-explorer-views.md)
- [Investigação e resposta automatizadas na Proteção contra Ameaças da Microsoft](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)

## <a name="required-licenses-and-permissions"></a>Licenças e permissões necessárias

Você deve ter o [Office 365 ATP](office-365-atp.md) para obter as detecções do Explorer ou em tempo real.

- O Explorer está incluído no plano 2 do Office 365 ATP.
- O relatório de detecções em tempo real está incluído no plano 1 de ATP do Office 365.
- Planejar a atribuição de licenças para todos os usuários que devem estar protegidos pelo Office 365 ATP. (As detecções de Explorer ou em tempo real mostram dados de detecção para usuários licenciados.)

Para exibir e usar as detecções do Explorer ou em tempo real, você deve ter as permissões apropriadas, como aquelas concedidas a um administrador de segurança ou leitor de segurança.

- Para o centro de conformidade de segurança &amp; , você deve ter uma das seguintes funções atribuídas:

  - Gerenciamento de Organização
  - Administrador de segurança (pode ser atribuído no centro de administração do Azure Active Directory [https://aad.portal.azure.com](https://aad.portal.azure.com) )
  - Leitor de segurança

- Para o Exchange Online, você deve ter uma das seguintes funções atribuídas no centro de administração do Exchange ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) ) ou com cmdlets do PowerShell (Confira [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)):

  - Gerenciamento de Organização
  - Gerenciamento de Organização Somente para Exibição
  - Função de Destinatários Somente para Exibição
  - Gerenciamento de Conformidade

Para saber mais sobre funções e permissões, confira os seguintes recursos:

- [Permissões no centro de &amp; conformidade de segurança](permissions-in-the-security-and-compliance-center.md)
- [Permissões de recursos no Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)

## <a name="some-differences-between-threat-explorer-and-real-time-detections"></a>Algumas diferenças entre o Gerenciador de ameaças e as detecções em tempo real

- O relatório de **detecções em tempo real** está disponível no Office 365 ATP Plan 1, enquanto o **Explorador de ameaças** está disponível no Office 365 ATP Plan 2.
- O relatório de **detecções em tempo real** permite que você visualize detecções em tempo real. O **Gerenciador de ameaças** também faz isso, mas também permite que você exiba detalhes adicionais de um determinado ataque.
- Um modo de exibição de **todos os emails** está disponível no **Explorador de ameaças** (e não está no relatório de **detecções em tempo real** ).
- Mais recursos de filtragem e ações disponíveis estão incluídos no **Explorador de ameaças**.

Para obter mais detalhes, consulte a [Descrição do serviço do Office 365 ATP: disponibilidade de recursos nos planos de proteção avançada contra ameaças (ATP)](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).
