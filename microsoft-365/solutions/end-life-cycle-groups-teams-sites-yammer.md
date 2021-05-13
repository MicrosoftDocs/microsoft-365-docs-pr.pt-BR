---
title: Opções de fim de ciclo de vida para grupos, equipes e Yammer
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
description: Opções de fim de ciclo de vida para grupos, equipes e Yammer.
ms.openlocfilehash: 468f41df747b6cf12d3f6619d79cb97248eba1d1
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "52346421"
---
# <a name="end-of-lifecycle-options-for-groups-teams-and-yammer"></a>Opções de fim de ciclo de vida para grupos, equipes e Yammer

Microsoft 365 Grupos e Microsoft Teams funcionam com vários serviços conectados. Quando um grupo ou equipe é excluída, a maioria das informações nos serviços conectados também é excluída. Este artigo descreve as opções de retenção de informações movendo-as para fora do grupo ou da equipe antes da exclusão.

Uma prática comum para grupos ou equipes que não são mais necessárias é mover os arquivos para fora da equipe e arquivar-os em outro local, como uma biblioteca SharePoint de documentos. Essa prática se baseia em um estilo herdado de trabalho em que as informações são armazenadas em arquivos e pastas, e as comunicações são conduzidas por email.

A tabela a seguir descreve os serviços associados a grupos e equipes e os principais tipos de conteúdo encontrados em cada um deles:

|Serviço|Tipos de conteúdo|
|:------|:---------------|
|Teams|Conversas de canal, arquivos em canais|
|Formulários|Estrutura e resultados da pesquisa|
|OneNote|Notebook|
|Outlook|Email e calendário|
|Planner|Project status e informações de tarefa|
|Power Automate|Fluxos de trabalho|
|Power BI|Dados, relatórios e painéis|
|Project na Web|Project planos|
|Roteiro|Roteiros|
|SharePoint|Arquivos, listas, Teams wiki do canal|
|Stream|Vídeos|
|Yammer|Conversas|

Ao excluir um grupo ou equipe, a maioria dos recursos associados também é excluída. As exceções incluem:

- Os vídeos no Stream permanecem e pertencem à pessoa que os carregou/gravou
- Os fluxos Power Automate permanecem e pertencem à pessoa que os criou.
- Project dados de mapa e Project na Web permanecem no CDS e podem ser restaurados separadamente.

Grupos e equipes permanecem em um estado de exclusão suave por 30 dias e podem ser restaurados a qualquer momento. No entanto, após os 30 dias, eles e todos os recursos associados, como serviços e conteúdo, são limpos do ambiente Microsoft 365. Todo o conteúdo protegido por uma política de retenção permanece disponível por meio de pesquisas de Descoberta e.

## <a name="end-of-life-cycle-considerations-for-group-connected-services"></a>Considerações sobre o fim do ciclo de vida para serviços conectados a grupos

Há três áreas principais que os proprietários de equipe e grupo e administradores de IT precisam considerar ao excluir um grupo ou equipe.

**Conteúdo**

O conteúdo precisa ser mantido depois que a equipe não está mais lá? É suficiente depender dos recursos de retenção do Microsoft 365 ou parte do conteúdo em aplicativos e serviços que não oferecem retenção? O conteúdo precisa ser mantido para fins de gerenciamento de registros, arquivamento ou uso futuro e referência?

Para evitar possíveis perdas de dados, essas perguntas devem ser feitas antes que qualquer equipe seja arquivada ou excluída.

**Serviços**

O conteúdo precisa permanecer em sua forma de trabalho atual? Por exemplo, o relatório Power BI precisa continuar acessível? Os resultados do Formulário precisam estar disponíveis no visualização de resumo visual? As listas em SharePoint estão vinculadas ou inseridas em algum lugar?

Essas perguntas devem ser feitas antes que o grupo subjacente seja excluído porque a exportação do conteúdo pode não ser suficiente.

**Convidados**

Quando os convidados são convidados para uma equipe, uma conta de convidado é criada no Azure Active Directory da organização host antes de adi adiá-los à equipe. Quando uma equipe é excluída, os convidados não são removidos Azure Active Directory. Embora os convidados não possam acessar grupos, sites, equipes ou conteúdo que não tenha sido compartilhado com eles, eles ainda podem usar recursos no Microsoft Teams, como iniciar chats, chamadas de voz e vídeo e usar aplicativos.

Um proprietário de equipe ou grupo pode convidar alguém de fora da organização para se tornar um convidado no Azure Active Directory adicionando-o a uma equipe. No entanto, um proprietário de equipe não pode remover o convidado do Azure Active Directory. A exclusão de contas só pode ser executada por um administrador global ou administrador de usuário.

É importante realizar avaliações de convidados e entender se os convidados precisam ser removidos do Azure Active Directory após a exclusão da equipe. Pode haver um caso válido para os convidados permanecerem no diretório, como ser membro de outras equipes ou usar outros Microsoft 365 ou serviços do Azure.

## <a name="teams"></a>Teams

Teams conteúdo específico é principalmente na forma de conversas.

As conversas nos canais não podem ser copiadas ou movidas usando a funcionalidade Microsoft Teams nativa. No entanto, eles podem ser exportados usando Graph API.

Além disso, se uma política de retenção for aplicada ao Teams, as conversas serão mantidas e disponíveis por meio de pesquisas de Descobertas EDiscovery. Usando a Descoberta Digital Avançada, você pode [reconstruir uma conversa Teams chat.](/microsoft-365/compliance/conversation-review-sets)


### <a name="archiving-a-team"></a>Arquivando uma equipe

O benefício do [arquivamento de uma equipe é](/microsoftteams/archive-or-delete-a-team) que ela fornece acesso total à equipe como era. Os usuários ainda podem procurar conversas de canal e abrir arquivos mesmo que não sejam ativos. Além disso, as equipes podem ser desarquivadas se houver a necessidade de continuar trabalhando neles (por exemplo, se um projeto for estendido).

Quando uma equipe é arquivada por um proprietário, ela é definida como somente leitura para membros para conteúdo dentro da equipe e, se selecionada, o site SharePoint associado. O objetivo dessa ação é garantir que as conversas nos canais sejam preservadas em seu estado existente, juntamente com um conteúdo baseado em SharePoint, como arquivos e wikis.

No site SharePoint não há alterações visíveis. No entanto, nenhuma alteração pode ser feita em arquivos ou listas porque as permissões SharePoint do grupo Microsoft 365 são definidas como **visitantes do site.** Isso inclui o bloco OneNote bloco de anotações da equipe, que é armazenado na biblioteca De ativos do site no SharePoint site.

Quando uma equipe é arquivada, o grupo de Microsoft 365 subjacente ainda está sujeito à política de expiração (se definido) e, como tal, o proprietário deve continuar a renovar a equipe.

Embora as conversas de canal da equipe e SharePoint conteúdo do site sejam definidos como somente leitura, o mesmo não é aplicado a outros serviços associados:

- Os buckets e tarefas do Planner ainda podem ser criados, modificados e excluídos.
- Os formulários ainda podem receber envios.
- A Outlook caixa de correio ainda pode receber emails.
- Power BI painéis, relatórios e dados ainda podem ser modificados.
- Projetos e roteiros ainda podem ser editados Project na Web.
- Os vídeos ainda podem ser carregados, modificados e excluídos no Stream.
- Os fluxos Power Automate ainda podem ser criados, modificados, excluídos e continuarão sendo executados. (Eles falharão no entanto, se necessário para postar uma mensagem em um canal da equipe arquivada.)

## <a name="forms"></a>Formulários

Embora um formulário possa ser movido de uma conta individual para um grupo, ele não pode ser movido ou copiado de um grupo para outro. Há três opções disponíveis para um formulário quando uma equipe é excluída.

**Duplicar o formulário**

Os formulários podem [ser compartilhados como modelos,](https://support.microsoft.com/office/82ea9d8a-260a-47a0-afdb-497f3d746e3f)permitindo que outros usuários o copiem para sua própria conta ou grupo. Isso não retém os dados de envios de resultados; somente estrutura de formulário, como perguntas e configurações.

**Exportar resultados para uma planilha**

Se os dados das respostas do formulário precisarem ser mantidos, isso poderá ser obtido exportando-os para uma planilha [Excel .](https://support.office.com/article/02859424-341d-406f-b32a-9a0fbaf357af) Isso só exportará as perguntas e suas respostas como dados – não inclui gráficos criados pelo Forms.

**Excluir o Formulário**

Embora a exclusão do grupo também resulte na exclusão de [](https://support.microsoft.com/office/2207e468-ce1b-4c4a-a256-caf631d87af0) quaisquer formulários associados, os membros do grupo podem excluí-los diretamente sem serem proprietários do grupo. No entanto, essa é uma etapa manual que não oferece nenhum benefício adicional.

## <a name="onenote"></a>OneNote

O OneNote bloco de anotações incluído em um grupo é armazenado na biblioteca De ativos de site no site SharePoint site associado. Embora os arquivos de bloco de anotações possam ser espalhados por vários arquivos individuais, eles não podem ser copiados e abertos independentemente. Em vez disso, o conteúdo do bloco de anotações OneNote deve ser movido ou exportado usando OneNote 2016.

**Mover páginas e seções para outro bloco de anotações**

[Mover páginas ou seções](https://support.office.com/article/c3c8b098-7f9c-4c2a-a0dc-ebb83bc76364) individualmente para outro bloco de anotações oferece aos proprietários a oportunidade de limpar seus dados e levar apenas o que precisa ser mantido.

**Exportar todo o bloco de anotações como um pacote**

Se todo o bloco de anotações precisar ser mantido com sua estrutura existente, ele poderá ser [exportado](https://support.office.com/article/a4b60da5-8f33-464e-b1ba-b95ce540f309) como um arquivo de pacote OneNote e importado para um novo local. Em vez disso, isso pode ser usado como um método para reter o conteúdo em um único arquivo, em vez da estrutura de vários arquivos existente.

**Imprimir para PDF**

Em cenários em que parte do conteúdo do bloco de anotações precisa ser retido apenas para referência ou como registros, páginas individuais podem ser impressas em PDF e [armazenadas em outro lugar.](https://support.office.com/article/13d173b5-7f4c-45a8-94eb-9354d63af5cd)

## <a name="mailbox-and-calendar"></a>Caixa de correio e calendário

Não é incomum que a caixa de correio associada ao grupo seja usada, mesmo que muitas conversas possam ter sido conduzidas em canais de equipe. A caixa de correio armazena apenas emails que foram enviados diretamente para ela e não inclui emails enviados diretamente para canais.

Em alguns casos, os emails armazenados na caixa de correio podem ser notificações de reuniões, atualizações de tarefas do Planner e outros aplicativos ou mensagens geradas pelo sistema. é importante que o conteúdo da caixa de correio seja revisado para determinar se o conteúdo deve ser mantido ou excluído.

Se uma política de retenção for aplicada Exchange, os emails e itens de calendário serão mantidos e disponíveis por meio de pesquisas de Descoberta Eletrônico.

**Exportar email e calendário**

Os membros da equipe ou do grupo podem exportar o conteúdo da caixa de correio e do calendário para um arquivo [Outlook Dados /Pessoal Armazenamento (PST).](https://support.office.com/article/14252b52-3075-4e9b-be4e-ff9ef1068f91) Esse arquivo pode ser armazenado em outro lugar ou o conteúdo pode ser importado para uma caixa de correio diferente. O primeiro não é recomendado, pois o conteúdo do arquivo PST não é pesquisável sem abri-lo no Outlook, e o próprio arquivo pode ficar corrompido com o tempo.

**Migração de conteúdo executada em IT**

Os administradores podem usar ferramentas de terceiros para migrar conteúdos de email e calendário entre caixas de correio sem qualquer intervenção do usuário. Um local de armazenamento em potencial pode ser uma caixa de correio compartilhada criada puramente para servir como um "arquivo morto" do conteúdo da caixa de correio do grupo.

## <a name="planner"></a>Planner

Cada grupo ou equipe pode ter vários planos. É importante durante o processo de off-boarding garantir que os requisitos de retenção sejam abordados para cada plano. Assim como os outros serviços, há várias abordagens para conteúdo off-board no Planner.

**Exportar o plano para uma planilha**

Se for necessário apenas manter uma cópia do plano para fins de manutenção de registros, a abordagem mais simples é exportar o plano para uma planilha [Excel .](https://support.microsoft.com/office/4d850c6e-e548-4aab-83b4-b62b68662d2a) Esta é uma ação de ida - não há opção para importar planos de uma planilha.

> [!IMPORTANT]
> Exportar um plano para Excel levará a maioria das informações dentro do plano, mas não incluirá comentários, links ou arquivos.

**Copiar e mover tarefas para outro Plano**

Embora copiar ou mover tarefas para outro plano pareça uma [](https://support.microsoft.com/office/ad43a5d8-c1ad-42fd-b3da-fe97d72c8a1b) solução, tarefas individuais só podem ser copiadas ou movidas entre planos no mesmo grupo. Isso não irá fazer o back-up dos dados se o grupo associado ao plano estiver sendo excluído.

**Copiar plano inteiro**

Também é possível copiar [todo o plano](https://support.microsoft.com/office/50401e13-a25f-40df-93c6-b608cc28c3d4). A cópia não pode ser feita em um grupo existente. Copiar o plano criará um novo grupo. Além disso, copiar todo o plano não incluirá comentários, atribuições, links, anexos ou datas.

## <a name="power-automate"></a>Power Automate

Os fluxos criados Power Automate e associados a um grupo ou equipe não pertencem ao grupo. Eles são de propriedade do criador e apenas compartilhados com outros usuários e grupos. Dessa forma, eles não serão afetados se um grupo ou equipe for excluído.

**Alterar a propriedade do fluxo**

Se o fluxo precisar continuar operando, qualquer proprietário poderá adicionar outros usuários ou Microsoft 365 grupos como proprietários.

**Exportar o fluxo**

Se o fluxo não precisar continuar operando, mas precisar ser preservado para uso futuro potencial, ele poderá ser [exportado](https://flow.microsoft.com/blog/import-export-bap-packages/) como um arquivo e importado novamente mais tarde.

## <a name="power-bi"></a>Power BI

Power BI dados e espaços de trabalho podem operar independentemente de grupos e equipes e, assim como outras cargas de trabalho, oferecem maneiras diferentes de serem desligados.

**Copiar relatórios para outro espaço de trabalho**

Se você precisar do relatório depois que o grupo ou a equipe for excluído, ele poderá ser copiado do espaço de trabalho existente para outro espaço de trabalho dentro [Power BI](/power-bi/connect-data/service-datasets-copy-reports).

**Exportar dados de um painel ou relatório**

Em vez disso, se o relatório não precisar mais estar ativo, mas os dados precisarem ser mantidos, ele poderá ser [exportado](/power-bi/visuals/power-bi-visualization-export-data)para Excel .

## <a name="project"></a>Project

Projetos e roteiros criados no Project para a Web são associados a grupos Microsoft 365 e têm abordagens para o off-boarding semelhante ao Power BI.

**Atribuir o projeto a outro grupo**

Se o projeto precisar ser preservado em seu estado funcional além da vida útil do grupo ou da equipe, ele poderá ser atribuído a um grupo Microsoft 365 [diferente.](/project-for-the-web/access-a-project-after-group-is-deleted#reassign-the-project) Isso pode ser feito usando o Centro de Administração do Dynamics 365.

**Exportar dados do projeto ou roteiro**

Usando o Centro de Administração do Dynamics 365, é possível exportar dados do usuário do [projeto](/project-for-the-web/export-user-data-from-project-for-the-web) para uma planilha. Os dados também podem ser exportados para Project arquivo (. Formatos de arquivo MPP) e XML usando o PowerShell.

## <a name="sharepoint"></a>SharePoint

Todos os arquivos nos canais de equipe são armazenados SharePoint site do grupo associado. Em alguns casos, o conteúdo diferente de documentos pode existir SharePoint, como listas ou páginas.

Os arquivos geralmente são armazenados em três locais principais em um SharePoint site:

- Páginas - Biblioteca de Páginas do Site
- Imagens usadas em páginas – Biblioteca de Ativos do Site
- Arquivos em canais – Biblioteca de documentos
- Páginas wiki – Teams wiki data library

Se o site tiver um ou mais subsites, o processo de off-boarding precisará ser repetido para cada subsite. Se a equipe contiver canais privados, haverá um site SharePoint separado para cada canal.

É importante ao remover arquivos de um grupo ou equipe para considerar que eles podem ser compartilhados com usuários que não são membros do grupo ou da equipe. Talvez você queira comunicar a alteração iminente a eles.

**Baixar arquivos**

Os arquivos armazenados SharePoint em uma das bibliotecas mencionadas acima podem ser [baixados para um computador local.](https://support.office.com/article/5c7397b7-19c7-4893-84fe-d02e8fa5df05)

**Mover arquivos**

Além disso, os arquivos podem ser movidos para outro local dentro [SharePoint como uma biblioteca em um site diferente.](https://support.office.com/article/00e2f483-4df3-46be-a861-1f5f0c1a87bc)

**Lista de exportação**

Os dados armazenados SharePoint listas podem ser [exportados](https://support.office.com/article/bfb2ea48-6118-4fa9-abb6-cced9424e5d9)para uma planilha Excel e importados novamente para uma lista em outro site.

Como alternativa, uma ferramenta de terceiros pode ser usada para migrar a lista entre sites para manter a função, exibições de lista, formatação e outros atributos.

**"Exportar" arquivos wiki**

Os conteúdos wiki nos canais de equipe são armazenados em um arquivo formatado em HTML em uma biblioteca dedicada do site SharePoint site associado. Eles não podem ser facilmente exportados e importados para outro canal wiki, mas podem ser convertidos em um arquivo HTML e abertos como uma página da Web.

## <a name="microsoft-stream"></a>Microsoft Stream

Como Power Automate, os vídeos no Stream associados a um grupo ou equipe não são realmente de propriedade do grupo e não são excluídos quando o grupo é excluído. Os vídeos no Stream são de propriedade da pessoa que carregou ou criou o vídeo, mesmo que eles adicionem usuários ou grupos como proprietários. As reuniões gravadas em um Teams são de propriedade da pessoa que iniciou a gravação.

**Adicionando outros proprietários**

Como o vídeo é mantido no Stream quando o grupo é excluído, o proprietário original pode compartilhar o vídeo com outros usuários e grupos, inclusive adicionando-os [como proprietários.](/stream/portal-edit-video)

**Baixar o vídeo**

Em cenários em que o vídeo não precisa ser mantido no Stream ou precisa ser armazenado em um local alternativo, como um sistema de gerenciamento de registros, um proprietário pode baixá-lo [localmente.](/stream/portal-download-video)

## <a name="yammer"></a>Yammer

Ao contrário das conversas Microsoft Teams, Yammer oferece aos usuários e administradores opções para mover ou exportar conversas.

**Mover conversas para outro grupo ou comunidade**

As conversas podem ser movidas para outro Yammer grupo por qualquer usuário, não apenas proprietários ou administradores. Isso é possível nos [Yammer](https://support.office.com/article/149c6399-4ac1-4ced-84d7-e0660960a872) e nas novas [interfaces Yammer.](https://support.office.com/article/d63debf1-1c90-4ec5-b5ae-8a00939a1680)

**Exportar dados de rede**

Yammer administradores de rede [exportam dados de rede.](/yammer/manage-security-and-compliance/export-yammer-enterprise-data) No entanto, isso exportará todas as conversas para toda a rede. A exportação resultante lista a ID do Grupo. É possível filtrar conversas com base nessa ID.
