---
title: Fim das opções de ciclo de vida para grupos, equipes e Yammer
ms.reviewer: mmclean
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Fim das opções de ciclo de vida para grupos, equipes e Yammer.
ms.openlocfilehash: ab06f06cc65614ee313892a026c2f482d641791f
ms.sourcegitcommit: 66f1f430b3dcae5f46cb362a32d6fb7da4cff5c1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662451"
---
# <a name="end-of-lifecycle-options-for-groups-teams-and-yammer"></a>Fim das opções de ciclo de vida para grupos, equipes e Yammer

Os grupos do Microsoft 365 e o Microsoft Teams trabalham com vários serviços conectados. Quando um grupo ou equipe é excluído, a maioria das informações nos serviços conectados também é excluída. Este artigo descreve as opções para reter informações movendo-as para fora do grupo ou equipe antes da exclusão.

Uma prática comum para grupos ou equipes que não são mais necessários é mover os arquivos para fora da equipe e armazená-los em outro local, como uma biblioteca de documentos do SharePoint que atue como repositório ou arquivo morto. Essa prática se baseia em um estilo herdado de trabalhar onde as informações são armazenadas em arquivos e pastas, e as comunicações são conduzidas por email.

A tabela a seguir descreve os serviços associados a grupos e equipes e tipos de chave de conteúdo encontrados em cada um deles:

|Serviço|Tipos de conteúdo|
|:------|:---------------|
|Teams|Conversas de canal, arquivos em canais|
|Formulários|Estrutura e resultados da pesquisa|
|OneNote|Bloco de anotações|
|Outlook|Email e calendário|
|Planner|Informações de status e tarefas do projeto|
|Power Automate|Fluxos de trabalho|
|Power BI|Dados, relatórios e painéis|
|Projeto na Web|Planos de projeto|
|Roteiro|Roteiros|
|SharePoint|Arquivos, listas, dados do wiki do canal do teams|
|Stream|Vídeos|
|Yammer|Conversas|

Ao excluir um grupo ou uma equipe, a maioria dos recursos associados também é excluída. Algumas das exceções incluem vídeos no Stream – elas permanecem e ainda pertencem à pessoa que as carregou/gravou, como os fluxos de energia automatizar. Os dados de projeto e roteiro no Project na Web permanecem nos CDS e podem ser restaurados separadamente.

Grupos e equipes permanecem em um estado de exclusão reversível por 30 dias e podem ser restaurados a qualquer momento. No entanto, após os 30 dias, todos os recursos associados, como serviços e conteúdo, serão completamente excluídos do ambiente do Microsoft 365. Qualquer conteúdo protegido por uma política de retenção permanece disponível por meio de pesquisas de descoberta eletrônica.

## <a name="end-of-life-cycle-considerations-for-group-connected-services"></a>Considerações de fim de ciclo de vida para serviços conectados ao grupo

Há três áreas principais que os proprietários de equipe e de grupo e os administradores de ti precisam considerar ao excluir um grupo ou uma equipe.

**Conteúdo**

O conteúdo precisa ser retido depois que a equipe não estiver mais funcional ou em existência? É suficiente confiar nos recursos de retenção do Microsoft 365, ou é parte do conteúdo em aplicativos e serviços que não oferecem retenção? O conteúdo precisa ser retido para fins de gerenciamento de registros, para fins de arquivamento ou para fins de referência e uso futuro?

Essas perguntas devem ser solicitadas antes de qualquer equipe ser arquivada ou excluída, para evitar possíveis perdas de dados.

**Serviços**

Na parte superior do conteúdo em vários aplicativos e serviços, eles precisam permanecer no seu formulário de trabalho atual? Por exemplo, o relatório do Power BI precisa continuar a ser acessado, os resultados do formulário precisam estar disponíveis no modo de exibição Visual Summary, as listas no SharePoint vinculadas ou incorporadas em qualquer lugar?

Semelhante às considerações de conteúdo, essas perguntas devem ser solicitadas antes que o grupo subjacente seja excluído, já que exportar o conteúdo pode não ser suficiente.

**Convidados**

Quando convidados são convidados para uma equipe, o fluxo de trabalho cria sua identidade no Azure Active Directory da organização do host antes de adicioná-los à equipe. Quando uma equipe é excluída, os convidados não são removidos do Azure Active Directory e, como tal, ainda existem no ambiente do Microsoft Teams. Embora os convidados não possam acessar grupos, sites, equipes ou conteúdo que não tenha sido compartilhado com eles, eles ainda podem usar recursos no Microsoft Teams, como iniciar chats, chamadas de voz e vídeo e usar aplicativos.

Um proprietário de equipe ou grupo pode convidar um usuário externo para se tornar um convidado no Azure Active Directory, adicioná-lo à equipe, bem como removê-los da equipe. No entanto, um proprietário de equipe não pode remover o convidado do Azure Active Directory – isso só pode ser realizado por um administrador global ou administrador de usuário.

Portanto, é importante realizar revisões de convidados, bem como para entender se os convidados precisam ser removidos do Azure Active Directory após a exclusão da equipe. Pode haver um caso válido para que os convidados permaneçam no diretório, como ser membro de uma ou mais outras equipes ou usar outros serviços do Microsoft 365 ou do Azure.

## <a name="teams"></a>Teams

O conteúdo específico de equipes é principalmente na forma de conversas.

Conversas em canais não podem ser copiadas ou movidas usando a funcionalidade nativa do Microsoft Teams. No entanto, eles podem ser exportados usando a API do Graph.

Além disso, se uma política de retenção for aplicada ao Teams, as conversas serão mantidas e estarão disponíveis por meio de pesquisas de descoberta eletrônica. (Os itens encontrados nas pesquisas de descoberta eletrônica podem ser exportados, mas não há contexto ou estrutura de sua fonte original, são simplesmente mensagens individuais.)

### <a name="archiving-a-team"></a>Arquivando uma equipe

O benefício do [arquivamento de uma equipe](https://docs.microsoft.com/microsoftteams/archive-or-delete-a-team) é que ele oferece acesso completo à equipe, assim que os usuários ainda podem navegar por conversas de canal e abrir arquivos, mesmo que eles não estejam ativos. Além disso, o Microsoft Teams pode ser não arquivado se houver a necessidade de continuar a trabalhar neles (como no caso de uma extensão de projeto).

Quando uma equipe é arquivada por um proprietário, ela é definida como somente leitura para os membros tanto para o conteúdo da equipe, quanto se estiver selecionada, o site do SharePoint associado. O objetivo desta ação é garantir que as conversas nos canais sejam preservadas no estado existente, juntamente com o conteúdo baseado no SharePoint, como arquivos e wikis.

No site do SharePoint, não há alterações visíveis, no entanto, não é possível fazer alterações em nenhum arquivo ou lista como o grupo de permissões baseado no SharePoint para o grupo do Microsoft 365 é definido como o nível de visitantes do site. Isso inclui o bloco de anotações do OneNote para a equipe, pois isso é armazenado na biblioteca de ativos do site no site do SharePoint.

Quando uma equipe é arquivada, o grupo subjacente da Microsoft 365 ainda está sujeito à política de expiração (se definida) e, como tal, o proprietário deve continuar a renovar a equipe.

Enquanto as conversas de canal e o conteúdo do site do SharePoint da equipe são definidos como somente leitura, o mesmo não é aplicado a outros serviços associados:

- Os buckets e as tarefas do Planner ainda podem ser criados, modificados e excluídos
- Os formulários ainda podem receber envios
- A caixa de correio do Outlook ainda pode receber emails
- Os painéis, relatórios e dados do Power BI ainda podem ser modificados
- Os projetos e mapas ainda podem ser editados no Project na Web
- Os vídeos ainda podem ser carregados, modificados e excluídos no Stream
- Os fluxos de energia automatizada ainda podem ser criados, modificados, excluídos e continuar a ser executados (eles falharão no entanto, se for necessário postar uma mensagem em um canal da equipe arquivada)

## <a name="forms"></a>Formulários

Enquanto um formulário pode ser movido de uma conta individual para um grupo, ele não pode ser movido ou copiado de um grupo para outro. Há três opções disponíveis para um formulário quando uma equipe é excluída.

**Duplicar o formulário**

Os formulários podem ser [compartilhados como modelos](https://support.microsoft.com/office/82ea9d8a-260a-47a0-afdb-497f3d746e3f), permitindo que outros usuários o copiem para sua própria conta ou um grupo. Isso não mantém os dados de envios de resultados; somente estrutura de formulários, como perguntas e configurações.

**Exportar resultados para uma planilha**

Se os dados das respostas do formulário precisarem ser retidos, isso pode ser obtido [exportando os resultados para uma planilha do Excel](https://support.office.com/article/02859424-341d-406f-b32a-9a0fbaf357af). Isso só exportará as perguntas e suas respostas como dados – ele não inclui gráficos criados por formulários.


**Excluir o formulário**

Embora a exclusão do grupo também resulte na exclusão de qualquer formulário associado, os membros do grupo podem [excluí-los diretamente](https://support.microsoft.com/office/2207e468-ce1b-4c4a-a256-caf631d87af0) sem ser um proprietário do grupo, no entanto, esta é uma etapa manual que não fornece nenhum benefício adicional.

## <a name="onenote"></a>OneNote

O bloco de anotações do OneNote incluído em um grupo é armazenado na biblioteca de ativos do site no site do SharePoint associado. Enquanto os arquivos de bloco de anotações podem, às vezes, ser distribuídos em vários arquivos individuais, eles não podem ser simplesmente copiados e abertos de forma independente. Em vez disso, o conteúdo do bloco de anotações do OneNote deve ser movido ou exportado usando o OneNote 2016.

**Mover páginas e seções para outro bloco de anotações**

A [movimentação individual de páginas ou seções para outro bloco de anotações](https://support.office.com/article/c3c8b098-7f9c-4c2a-a0dc-ebb83bc76364) fornece aos proprietários uma oportunidade de limpar seus dados e levar apenas o que precisa ser mantido.

**Exportar o bloco de anotações inteiro como um pacote**

Se todo o bloco de anotações precisar ser mantido com sua estrutura existente, ele poderá ser [exportado como um](https://support.office.com/article/a4b60da5-8f33-464e-b1ba-b95ce540f309) arquivo de pacote do OneNote e importado para um novo local. Como alternativa, isso pode ser usado como um método para reter o conteúdo em um único arquivo, em vez da estrutura de vários arquivos existente.

**Imprimir para PDF**

Em cenários em que parte do conteúdo do bloco de anotações só precisa ser retido para referência ou como registros, páginas individuais podem ser [impressas em PDF e armazenadas em outro lugar](https://support.office.com/article/13d173b5-7f4c-45a8-94eb-9354d63af5cd).

## <a name="mailbox-and-calendar"></a>Caixa de correio e calendário

Não é incomum que a caixa de correio associada ao grupo seja utilizada, mesmo que muitas conversas possam ter sido conduzidas nos canais da equipe. A caixa de correio armazena apenas emails que foram enviados diretamente para ele e não inclui emails que foram enviados diretamente aos canais.

Em alguns casos, os emails armazenados na caixa de correio podem ser apenas notificações de reuniões, atualizações de tarefas do Planner e outras mensagens geradas por aplicativos ou sistemas. É importante que o conteúdo da caixa de correio seja revisado para determinar se o conteúdo deve ser mantido ou excluído.

Se uma política de retenção for aplicada ao Exchange, os emails e os itens de calendário serão mantidos e disponibilizados por meio de pesquisas de descoberta eletrônica.

**Exportar email e calendário**

Membros de equipe ou grupo podem [exportar o conteúdo da caixa de correio e calendário para um arquivo de dados do Outlook/armazenamento pessoal (PST)](https://support.office.com/article/14252b52-3075-4e9b-be4e-ff9ef1068f91). Esse arquivo pode ser armazenado em outro lugar, ou o conteúdo pode ser importado para uma caixa de correio diferente. O primeiro não é recomendável, pois o conteúdo do arquivo PST não pode ser pesquisado sem ser aberto no Outlook, e o próprio arquivo pode ser corrompido ao longo do tempo.

**Migração de conteúdo executada pelo ti**

Os administradores podem usar ferramentas de terceiros para migrar o conteúdo de email e calendário entre caixas de correio sem qualquer intervenção do usuário. Um possível local de armazenamento pode ser uma caixa de correio compartilhada criada puramente para servir como um "arquivo morto" do conteúdo da caixa de correio do grupo.

## <a name="planner"></a>Planner

Cada grupo ou equipe pode ter vários planos. É importante durante o processo de remoção para garantir que cada plano seja tratado como se seu conteúdo seja mantido. Como os outros produtos, há várias abordagens para o conteúdo do externamente no Planner.

**Exportar o plano para uma planilha**

Se for necessário apenas manter uma cópia do plano para fins de manutenção de registros, a abordagem mais simples é [exportar o plano para uma planilha do Excel](https://support.microsoft.com/office/4d850c6e-e548-4aab-83b4-b62b68662d2a). Esta é uma ação unilateral, já que não há opção para importar planos de uma planilha.

> [!IMPORTANT]
> Exportar um plano para o Excel assumirá a maior parte das informações dentro do plano, mas não incluirá comentários, links ou arquivos.

**Copiar e mover tarefas para outro plano**

Embora pareça uma solução, as tarefas individuais só podem ser [copiadas ou movidas entre os planos](https://support.microsoft.com/office/ad43a5d8-c1ad-42fd-b3da-fe97d72c8a1b) no mesmo grupo, o que nega o benefício em se o grupo associado ao plano estiver sendo excluído.

**Copiar todo o plano**

Também é possível [copiar todo o plano](https://support.microsoft.com/office/50401e13-a25f-40df-93c6-b608cc28c3d4). No entanto, isso não pode ser um grupo existente ou mesmo dentro do mesmo grupo. A cópia do plano criará um novo grupo. Além disso, a cópia do plano inteiro não incluirá comentários, atribuições, links, anexos ou datas.

## <a name="power-automate"></a>Power Automate

Os fluxos criados na automatização de energia e associados a um grupo ou equipe não pertencem ao grupo e, em vez disso, são pertencentes ao criador e são simplesmente compartilhados com outros usuários e grupos. Como tal, elas não serão afetadas se um grupo ou equipe for excluído.

**Alterar a propriedade do fluxo**

Se o fluxo de trabalho precisar continuar operando, qualquer proprietário poderá simplesmente adicionar outros usuários ou grupos do Microsoft 365 como proprietários.

**Exportar o fluxo**

Se o fluxo de trabalho não precisar continuar operando, mas precisar ser preservado para uso futuro em potencial, ele poderá ser [exportado como um arquivo](https://flow.microsoft.com/blog/import-export-bap-packages/) e importado novamente mais tarde.

## <a name="power-bi"></a>Power BI

Os dados e os espaços de trabalho do Power BI podem operar de forma independente de grupos e equipes, e como outras cargas de trabalho oferecem diferentes maneiras de serem offboarded.

**Copiar relatórios para outro espaço de trabalho**

Se o relatório precisar ser preservado em seu estado funcional além da vida útil do grupo ou equipe, ele poderá ser [copiado do espaço de trabalho existente para outro espaço de trabalho no Power bi](https://docs.microsoft.com/power-bi/connect-data/service-datasets-copy-reports).

**Exportar dados de um painel ou relatório**

Como alternativa, se o relatório não precisa mais estar ativo, mas os dados precisam ser retidos, eles podem ser [exportados para o Excel](https://docs.microsoft.com/power-bi/visuals/power-bi-visualization-export-data).

## <a name="project"></a>Project

Os projetos e mapas criados no Project na Web podem ser associados a grupos do Microsoft 365 e oferecem abordagens à remoção semelhante ao Power BI.

**Atribuir o projeto a outro grupo**

Se o projeto precisar ser preservado em seu estado funcional além da vida útil do grupo ou equipe, ele poderá ser [atribuído a um grupo do Microsoft 365 diferente](https://docs.microsoft.com/project-for-the-web/access-a-project-after-group-is-deleted#reassign-the-project) usando o centro de administração do Dynamics 365.

**Exportar dados do projeto ou roteiro**

Usando o centro de administração do Dynamics 365, é possível [exportar dados do usuário do projeto](https://docs.microsoft.com/project-for-the-web/export-user-data-from-project-for-the-web) para uma planilha ou, se estiver usando um script do PowerShell, os dados podem ser exportados para o arquivo de projeto (. MPP) e formatos de arquivo XML.

## <a name="sharepoint"></a>SharePoint
Todos os arquivos em canais de equipe são armazenados na biblioteca de documentos no site do SharePoint do grupo associado. Em alguns casos, os conteúdos que não sejam documentos podem existir no SharePoint, como listas ou páginas.
Geralmente, os arquivos são armazenados em três locais principais dentro de um site do SharePoint:

- Páginas-biblioteca de páginas do site
- Imagens usadas em páginas – biblioteca de ativos do site
- Arquivos em canais – biblioteca de documentos
- Páginas wiki – biblioteca de dados do wiki do teams

Se o site tiver um ou mais subsites aninhados abaixo dele, o processo de remoção precisará ser repetido para cada subsite. Se a equipe contiver canais privados, haverá um site do SharePoint separado para cada canal.

É importante ao remover arquivos de um grupo ou de uma equipe para considerar que eles podem ser compartilhados com usuários que não são membros do grupo ou equipe (seja interno ou externo à organização) e, como tal, pode valer a pena comunicar as alterações iminentes a eles.

**Baixar arquivos**

No caso de arquivos armazenados no SharePoint em uma das bibliotecas mencionadas acima, eles podem ser [baixados para um computador local](https://support.office.com/article/5c7397b7-19c7-4893-84fe-d02e8fa5df05).

**Mover arquivos**

Além disso, os arquivos podem ser movidos para outro local no SharePoint, como uma biblioteca em um site diferente.
Indicação https://support.office.com/en-us/article/move-or-copy-files-in-sharepoint-00e2f483-4df3-46be-a861-1f5f0c1a87bc

**Exportar lista** Os dados armazenados nas listas do SharePoint podem ser [exportados para uma planilha do Excel](https://support.office.com/article/bfb2ea48-6118-4fa9-abb6-cced9424e5d9)e importados novamente para uma lista em outro site.

Como alternativa, uma ferramenta de terceiros pode ser usada para migrar a lista entre sites, a fim de manter funções, modos de exibição de lista, formatação e outros atributos.

**"Exportar" arquivos wiki**

O conteúdo do wiki dentro de canais de equipe é armazenado em um arquivo formatado em HTML em uma biblioteca dedicada do site do SharePoint associado. Eles não podem ser facilmente exportados e importados para outro wiki de canal, mas podem ser convertidos em um arquivo HTML e abertos como uma página da Web.

## <a name="microsoft-stream"></a>Microsoft Stream

Como a automatização de energia, os vídeos no Stream associados a um grupo ou equipe não são pertencentes ao grupo e não são excluídos quando o grupo é excluído. Os vídeos no Stream pertencem à pessoa que carregou ou criou o vídeo, mesmo que eles adicionem usuários ou grupos como proprietários. Este também é o caso das reuniões registradas em um canal do teams; Eles pertencem à pessoa que iniciou a gravação.

**Adicionando outros proprietários**

Como o vídeo é mantido no fluxo independentemente da exclusão do grupo, o proprietário original pode [compartilhar o vídeo com outros usuários e grupos, mesmo adicionando-os como proprietários](https://docs.microsoft.com/stream/portal-edit-video).

**Baixar o vídeo**

Em cenários em que o vídeo não precisa ser retido no fluxo ou precisa ser armazenado em um local alternativo, como um sistema de gerenciamento de registros, um proprietário pode [baixá-lo localmente](https://docs.microsoft.com/stream/portal-download-video)

## <a name="yammer"></a>Yammer

Ao contrário das conversas no Microsoft Teams, o Yammer oferece opções de usuários e administradores para mover ou exportar conversas.

**Mover conversas para outro grupo ou comunidade**

As conversas podem ser movidas para outro grupo do Yammer por qualquer usuário, não apenas por proprietários ou administradores. Isso é possível no [Yammer clássico](https://support.office.com/article/149c6399-4ac1-4ced-84d7-e0660960a872), bem como nas novas interfaces do [Yammer](https://support.office.com/article/d63debf1-1c90-4ec5-b5ae-8a00939a1680) .

**Exportar dados de rede**

Os administradores de rede do Yammer podem executar uma [exportação de dados de rede](https://docs.microsoft.com/yammer/manage-security-and-compliance/export-yammer-enterprise-data), mas fazer isso exportará todas as conversas de toda a rede. No entanto, a exportação resultante lista a ID do grupo, portanto, é possível filtrar conversas com base nesse.
