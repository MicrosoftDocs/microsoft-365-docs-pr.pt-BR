---
title: Opções de fim do ciclo de vida para grupos, equipes e Yammer
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
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Opções de fim do ciclo de vida para grupos, equipes e Yammer.
ms.openlocfilehash: 31383287f3288cbab68d6e249f98210dec62af2f
ms.sourcegitcommit: 554755bc9ce40228ce6e34bde6fc6e226869b6a1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2020
ms.locfileid: "48681705"
---
# <a name="end-of-lifecycle-options-for-groups-teams-and-yammer"></a>Opções de fim do ciclo de vida para grupos, equipes e Yammer

Os Grupos do Microsoft 365 e o Microsoft Teams funcionam com uma variedade de serviços conectados. Quando um grupo ou equipe é excluído, a maioria das informações nos serviços conectados também é excluída. Este artigo descreve as opções de retenção de informações, movendo-as do grupo ou da equipe antes da exclusão.

Uma prática comum para grupos ou equipes que não são mais necessários é mover os arquivos para fora da equipe e armazená-los em outro local, como uma biblioteca de documentos do SharePoint atuando como um repositório ou arquivo morto. Essa prática baseia-se em um estilo herdado de trabalho em que as informações são armazenadas em arquivos e pastas, e as comunicações são conduzidas por email.

A tabela a seguir descreve os serviços associados a grupos e equipes e os principais tipos de conteúdo encontrados em cada um deles:

|Serviço|Tipos de conteúdo|
|:------|:---------------|
|Teams|Conversas de canal, arquivos em canais|
|Forms|Estrutura e resultados da pesquisa|
|OneNote|Bloco de anotações|
|Outlook|Email e calendário|
|Planner|Informações de tarefas e status do projeto|
|Power Automate|Fluxos de trabalho|
|Power BI|Dados, relatórios e painéis|
|Project na Web|Planos do project|
|Roteiro|Roteiros|
|SharePoint|Arquivos, listas, dados wiki do canal do Teams|
|Stream|Vídeos|
|Yammer|Conversas|

Ao excluir um grupo ou equipe, a maioria dos recursos associados também é excluída. Algumas das exceções a isso incluem vídeos no Stream– eles permanecem e ainda pertencem à pessoa que as carregou/gravou, assim como os fluxos no Power Automate. Os dados de projeto e mapa no Project na Web permanecem no CDS e podem ser restaurados separadamente.

Grupos e equipes permanecem no estado de exclusão por 30 dias e podem ser restaurados a qualquer momento. No entanto, após os 30 dias, eles e quaisquer recursos associados, como serviços e conteúdo, serão completamente limpos do ambiente do Microsoft 365. Qualquer conteúdo protegido por uma política de retenção permanece disponível por meio de pesquisas de DescobertaScoberta.

## <a name="end-of-life-cycle-considerations-for-group-connected-services"></a>Considerações sobre o fim do ciclo de vida dos serviços conectados ao grupo

Há três áreas principais que os proprietários de equipes e grupos e administradores de IT precisam considerar ao excluir um grupo ou equipe.

**Conteúdo**

O conteúdo precisa ser retido depois que a equipe não está mais funcional ou existente? É suficiente confiar nos recursos de retenção do Microsoft 365 ou parte do conteúdo em aplicativos e serviços que não oferecem retenção? O conteúdo precisa ser retido para fins de gerenciamento de registros, para fins de arquivamento ou para uso futuro e fins de referência?

Essas perguntas devem ser feitas antes que qualquer equipe seja arquivada ou excluída, para evitar possíveis perdas de dados.

**Serviços**

Além do conteúdo em vários aplicativos e serviços, eles precisam permanecer no formulário de trabalho atual? Por exemplo, o relatório do Power BI precisa continuar acessível, os resultados do formulário precisam estar disponíveis na exibição de resumo visual, as listas no SharePoint estão vinculadas ou inseridas em qualquer lugar?

Semelhante às considerações de conteúdo, essas perguntas devem ser feitas antes que o grupo subjacente seja excluído, pois simplesmente exportar o conteúdo pode não ser suficiente.

**Convidados**

Quando os convidados são convidados para uma equipe, o fluxo de trabalho cria sua identidade no Azure Active Directory da organização host antes de adiçá-los à equipe. Quando uma equipe é excluída, os convidados não são removidos do Azure Active Directory e, como tal, ainda existem no ambiente do Microsoft Teams. Embora os convidados não possam acessar grupos, sites, equipes ou conteúdo que não tenha sido compartilhado com eles, eles ainda podem utilizar recursos no Microsoft Teams, como iniciar chats, chamadas de voz e vídeo e usar aplicativos.

Um proprietário de equipe ou grupo pode convidar um usuário externo para se tornar um convidado no Azure Active Directory, adicioná-lo à equipe, bem como removê-lo da equipe. No entanto, um proprietário de equipe não pode remover o convidado do Azure Active Directory – isso só pode ser realizado por um administrador global ou por um administrador de usuários.

Portanto, é importante realizar avaliações de convidados, bem como entender se os convidados precisam ser removidos do Azure Active Directory após a exclusão da equipe. Pode haver um caso válido para os convidados permanecerem no diretório, como ser membro de uma ou mais equipes ou usar outros serviços do Microsoft 365 ou do Azure.

## <a name="teams"></a>Teams

O conteúdo específico do Teams é principalmente na forma de conversas.

As conversas nos canais não podem ser copiadas ou movidas usando a funcionalidade nativa do Microsoft Teams. No entanto, eles podem ser exportados usando a API do Graph.

Além disso, se uma política de retenção for aplicada ao Teams, as conversas serão mantidas e estarão disponíveis por meio de pesquisas de DescobertaScoberta. (Os itens encontrados nas pesquisas de DescobertaScoberta podem ser exportados, no entanto, não há contexto ou estrutura de sua fonte original permanece – eles são simplesmente mensagens individuais.)

### <a name="archiving-a-team"></a>Arquivando uma equipe

A vantagem [de](https://docs.microsoft.com/microsoftteams/archive-or-delete-a-team) arquivar uma equipe é que ela fornece acesso total à equipe como estava, para que os usuários ainda possam navegar pelas conversas do canal e abrir arquivos, mesmo se não estão ativos. Além disso, as equipes podem ser desarquivadas se houver a necessidade de continuar trabalhando neles (como no caso de uma extensão do projeto).

Quando uma equipe é arquivada por um proprietário, ela é definida como somente leitura para membros para conteúdo dentro da equipe, bem como se selecionada, o site do SharePoint associado. O objetivo desta ação é garantir que as conversas nos canais sejam preservadas em seu estado existente, juntamente com conteúdo baseado no SharePoint, como arquivos e wikis.

No site do SharePoint, não há alterações visíveis, no entanto, nenhuma alteração pode ser feita em nenhum arquivo ou lista, pois o grupo de permissões baseado no SharePoint para o Grupo do Microsoft 365 está definido para o nível visitantes do site. Isso inclui o bloco de anotações do OneNote para a equipe, pois ele é armazenado na biblioteca de Ativos do Site no site do SharePoint.

Quando uma equipe é arquivada, o grupo subjacente do Microsoft 365 ainda está sujeito à política de expiração (se definida) e, dessa forma, o proprietário deve continuar renovando a equipe.

Embora as conversas do canal da equipe e o conteúdo do site do SharePoint sejam definidos como somente leitura, o mesmo não é aplicado a outros serviços associados:

- Buckets e tarefas do Planner ainda podem ser criados, modificados e excluídos
- Os formulários ainda podem receber envios
- A caixa de correio do Outlook ainda pode receber emails
- Painéis, relatórios e dados do Power BI ainda podem ser modificados
- Projetos e roteiros ainda podem ser editados no Project na Web
- Os vídeos ainda podem ser carregados, modificados e excluídos no Stream
- Os fluxos no Power Automate ainda podem ser criados, modificados, excluídos e continuarão a ser executados (eles falharão no entanto, se for necessário postar uma mensagem em um canal da equipe arquivada)

## <a name="forms"></a>Forms

Embora um formulário possa ser movido de uma conta individual para um grupo, ele não pode ser movido ou copiado de um grupo para outro. Há três opções disponíveis para um formulário quando uma equipe é excluída.

**Duplicar o formulário**

Os formulários podem [ser compartilhados como modelos,](https://support.microsoft.com/office/82ea9d8a-260a-47a0-afdb-497f3d746e3f)permitindo que outros usuários os copiem para sua própria conta ou grupo. Isso não mantém os dados dos envios de resultados; somente estrutura de formulário, como perguntas e configurações.

**Exportar resultados para uma planilha**

Se os dados das respostas do formulário precisam ser mantidos, isso pode ser feito exportando os resultados para uma [planilha do Excel.](https://support.office.com/article/02859424-341d-406f-b32a-9a0fbaf357af) Isso só exportará as perguntas e suas respostas como dados – ele não inclui gráficos criados pelo Forms.


**Excluir o formulário**

Embora a exclusão do grupo também resulte na exclusão de [](https://support.microsoft.com/office/2207e468-ce1b-4c4a-a256-caf631d87af0) quaisquer formulários associados, os membros do grupo podem excluí-los diretamente sem serem proprietários do grupo– no entanto, esta é uma etapa manual que não oferece nenhum benefício adicional.

## <a name="onenote"></a>OneNote

O bloco de anotações do OneNote incluído em um grupo é armazenado na biblioteca de Ativos do Site no site do SharePoint associado. Embora os arquivos de bloco de anotações possam ser distribuídos em vários arquivos individuais, eles não podem ser simplesmente copiados e abertos independentemente. Em vez disso, o conteúdo do bloco de anotações do OneNote deve ser movido ou exportado usando o OneNote 2016.

**Mover páginas e seções para outro bloco de anotações**

[Mover páginas ou seções](https://support.office.com/article/c3c8b098-7f9c-4c2a-a0dc-ebb83bc76364) individualmente para outro bloco de anotações oferece aos proprietários a oportunidade de limpar seus dados e levar apenas o que precisa ser mantido.

**Exportar todo o bloco de anotações como um pacote**

Se todo o bloco de anotações precisar ser retido com sua estrutura existente, ele poderá ser exportado como um arquivo de pacote do [OneNote](https://support.office.com/article/a4b60da5-8f33-464e-b1ba-b95ce540f309) e importado para um novo local. Como alternativa, isso pode ser usado como um método para reter o conteúdo em um único arquivo em vez da estrutura de vários arquivos existente.

**Imprimir para PDF**

Em cenários em que parte do conteúdo do bloco de anotações precisa ser retido apenas para referência ou como registros, páginas individuais podem ser impressas em PDF e armazenadas [em outro lugar.](https://support.office.com/article/13d173b5-7f4c-45a8-94eb-9354d63af5cd)

## <a name="mailbox-and-calendar"></a>Caixa de correio e calendário

Não é incomum que a caixa de correio associada ao grupo seja utilizada, mesmo que muitas conversas possam ter sido conduzidas em canais de equipe. A caixa de correio armazena apenas emails que foram enviados diretamente para ela e não inclui emails que foram enviados diretamente para canais.

Em alguns casos, os emails armazenados na caixa de correio podem ser simplesmente notificações de reuniões, atualizações de tarefas do Planner e outras mensagens geradas pelo aplicativo ou pelo sistema. É importante que o conteúdo da caixa de correio seja revisado para determinar se o conteúdo deve ser retido ou excluído.

Se uma política de retenção for aplicada ao Exchange, os emails e itens de calendário serão mantidos e disponibilizados por meio de pesquisas de Descoberta Eletrônico.

**Exportar email e calendário**

Os membros da equipe ou do grupo podem exportar o conteúdo da caixa de correio e do calendário para um arquivo [PST (Armazenamento Pessoal/](https://support.office.com/article/14252b52-3075-4e9b-be4e-ff9ef1068f91)Dados do Outlook). Esse arquivo pode ser armazenado em outro lugar ou o conteúdo pode ser importado para uma caixa de correio diferente. O primeiro não é recomendado, pois o conteúdo do arquivo PST não é pesquisável sem abri-lo no Outlook, e o próprio arquivo pode ficar corrompido ao longo do tempo.

**Migração de conteúdo realizada pela IT**

Os administradores podem usar ferramentas de terceiros para migrar o conteúdo de email e calendário entre caixas de correio sem intervenção do usuário. Um local de armazenamento potencial poderia ser uma caixa de correio compartilhada criada puramente para servir como um "arquivo morto" do conteúdo da caixa de correio do grupo.

## <a name="planner"></a>Planner

Cada grupo ou equipe pode ter vários planos. É importante durante o processo de re transferência para garantir que cada plano seja tratado como se seu conteúdo fosse retido. Assim como os outros produtos, há várias abordagens de redação de conteúdo no Planner.

**Exportar o plano para uma planilha**

Se for necessário apenas manter uma cópia do plano para fins de manutenção de registros, a abordagem mais simples é exportar o plano para uma planilha [do Excel.](https://support.microsoft.com/office/4d850c6e-e548-4aab-83b4-b62b68662d2a) Esta é uma ação de uma via, pois não há opção para importar planos de uma planilha.

> [!IMPORTANT]
> Exportar um plano para o Excel levará a maioria das informações dentro do plano, mas não incluirá comentários, links ou arquivos.

**Copiar e mover tarefas para outro plano**

Embora isso pareça uma solução, tarefas [](https://support.microsoft.com/office/ad43a5d8-c1ad-42fd-b3da-fe97d72c8a1b) individuais só podem ser copiadas ou movidas entre planos dentro do mesmo grupo, o que anula o benefício se o grupo associado ao plano estiver sendo excluído.

**Copiar todo o plano**

Também é possível copiar [o plano inteiro.](https://support.microsoft.com/office/50401e13-a25f-40df-93c6-b608cc28c3d4) No entanto, isso não pode ser para um grupo existente ou mesmo dentro do mesmo grupo. Copiar o plano criará um novo grupo. Além disso, copiar o plano inteiro não incluirá comentários, atribuições, links, anexos ou datas.

## <a name="power-automate"></a>Power Automate

Os fluxos criados no Power Automate e associados a um grupo ou equipe não pertencem ao grupo e, em vez disso, pertencem ao criador e são simplesmente compartilhados com outros usuários e grupos. Dessa forma, eles não serão afetados se um grupo ou equipe for excluído.

**Alterar a propriedade do fluxo**

Se o fluxo de trabalho precisar continuar funcionando, qualquer proprietário poderá simplesmente adicionar outros usuários ou grupos do Microsoft 365 como proprietários.

**Exportar o fluxo**

Se o fluxo de trabalho não precisar continuar a operar, mas precisar ser preservado para uso futuro potencial, ele poderá ser [exportado](https://flow.microsoft.com/blog/import-export-bap-packages/) como um arquivo e importado novamente mais tarde.

## <a name="power-bi"></a>Power BI

Os dados e espaços de trabalho do Power BI podem operar independentemente de grupos e equipes e, como outras cargas de trabalho, oferecem maneiras diferentes de serem desaparadas.

**Copiar relatórios para outro espaço de trabalho**

Se o relatório precisar ser preservado em seu estado funcional além da vida útil do grupo ou da equipe, ele poderá ser copiado do espaço de trabalho existente para outro espaço de trabalho no [Power BI.](https://docs.microsoft.com/power-bi/connect-data/service-datasets-copy-reports)

**Exportar dados de um painel ou relatório**

Como alternativa, se o relatório não precisar mais estar ativo, mas os dados precisam ser mantidos, ele pode ser [exportado para o Excel.](https://docs.microsoft.com/power-bi/visuals/power-bi-visualization-export-data)

## <a name="project"></a>Project

Os projetos e roteiros criados no Project na Web podem ser associados a grupos do Microsoft 365 e oferecem abordagens de replicação semelhantes ao Power BI.

**Atribuir o projeto a outro grupo**

Se o projeto precisar ser preservado em seu estado funcional além da vida útil do grupo ou da equipe, ele poderá ser atribuído a um grupo diferente do [Microsoft 365](https://docs.microsoft.com/project-for-the-web/access-a-project-after-group-is-deleted#reassign-the-project) usando o Centro de Administração do Dynamics 365.

**Exportar dados do projeto ou roteiro**

Usando o Centro de Administração do Dynamics [](https://docs.microsoft.com/project-for-the-web/export-user-data-from-project-for-the-web) 365, é possível exportar dados do usuário do projeto para uma planilha ou se, usando um script do PowerShell, os dados podem ser exportados para o arquivo do Project (. Formatos de arquivo MPP) e XML.

## <a name="sharepoint"></a>SharePoint
Todos os arquivos nos canais de equipe são armazenados na biblioteca de documentos no site do SharePoint do grupo associado. Em alguns casos, outros conteúdos que não são documentos podem existir no SharePoint, como listas ou páginas.
Os arquivos geralmente são armazenados em três locais principais em um site do SharePoint:

- Páginas - Biblioteca de Páginas do Site
- Imagens usadas em páginas – Biblioteca de Ativos do Site
- Arquivos em canais – Biblioteca de documentos
- Páginas wiki – Biblioteca de dados wiki do Teams

Se o site tiver um ou mais subs sites aninhados abaixo dele, o processo de recomplicação precisará ser repetido para cada subs site. Se a equipe contiver canais privados, haverá um site do SharePoint separado para cada canal.

É importante ao remover arquivos de um grupo ou equipe para considerar que eles podem ser compartilhados com usuários que não são membros do grupo ou da equipe (sejam internos ou externos à organização) e, como tal, pode valer a pena comunicar a alteração iminente a eles.

**Baixar arquivos**

No caso de arquivos armazenados no SharePoint em uma das bibliotecas mencionadas acima, eles podem ser [baixados para um computador local.](https://support.office.com/article/5c7397b7-19c7-4893-84fe-d02e8fa5df05)

**Mover arquivos**

Além disso, os arquivos podem ser movidos para outro local no SharePoint, como uma biblioteca em um site diferente.
Referência: https://support.office.com/article/move-or-copy-files-in-sharepoint-00e2f483-4df3-46be-a861-1f5f0c1a87bc

**Exportar lista** Os dados armazenados em listas do SharePoint podem ser [exportados para uma](https://support.office.com/article/bfb2ea48-6118-4fa9-abb6-cced9424e5d9)planilha do Excel e importados novamente para uma lista em outro site.

Como alternativa, uma ferramenta de terceiros pode ser usada para migrar a lista entre sites para manter a função, exibições de lista, formatação e outros atributos.

**"Exportar" arquivos wiki**

O conteúdo wiki nos canais de equipe é armazenado em um arquivo formatado em HTML em uma biblioteca dedicada do site do SharePoint associado. Eles não podem ser prontamente exportados e importados para outro wiki de canal, mas podem ser convertidos em um arquivo HTML e abertos como uma página da Web.

## <a name="microsoft-stream"></a>Microsoft Stream

Como o Power Automate, os vídeos no Stream associados a um grupo ou equipe não são realmente de propriedade do grupo e não são excluídos quando o grupo é excluído. Os vídeos no Stream pertencem à pessoa que carregou ou criou o vídeo, mesmo que eles adicionem usuários ou grupos como proprietários. Esse também é o caso para reuniões registradas em um canal do Teams; eles pertencem à pessoa que iniciou a gravação.

**Adicionando outros proprietários**

Como o vídeo é mantido no Stream independentemente da exclusão do grupo, o proprietário original pode compartilhar o vídeo com outros usuários e grupos, inclusive adicionando-os [como proprietários.](https://docs.microsoft.com/stream/portal-edit-video)

**Baixar o vídeo**

Em cenários em que o vídeo não precisa ser retido no Stream ou precisa ser armazenado em um local alternativo, como um sistema de gerenciamento de registros, um proprietário pode baixá-lo [localmente](https://docs.microsoft.com/stream/portal-download-video)

## <a name="yammer"></a>Yammer

Ao contrário das conversas no Microsoft Teams, o Yammer oferece aos usuários e aos administradores opções para mover ou exportar conversas.

**Mover conversas para outro grupo ou comunidade**

As conversas podem ser movidas para outro grupo do Yammer por qualquer usuário, não apenas por proprietários ou administradores. Isso é possível no [Yammer clássico,](https://support.office.com/article/149c6399-4ac1-4ced-84d7-e0660960a872)bem como nas novas interfaces [do Yammer.](https://support.office.com/article/d63debf1-1c90-4ec5-b5ae-8a00939a1680)

**Exportar dados de rede**

Os administradores de rede do Yammer podem realizar [uma exportação](https://docs.microsoft.com/yammer/manage-security-and-compliance/export-yammer-enterprise-data)de dados de rede, no entanto, fazer isso exportará todas as conversas para toda a rede. No entanto, a exportação resultante lista a ID do Grupo, portanto, é possível filtrar conversas com base nisso.
