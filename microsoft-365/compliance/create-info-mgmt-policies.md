---
title: Criar e aplicar políticas de gerenciamento de informações
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 5/16/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- OSU150
- OSU160
- MET150
ms.assetid: 8ccac9e4-3a50-49fa-a95b-d186032a6ee3
ms.collection:
- M365-security-compliance
- SPO_Content
description: As políticas de gerenciamento de informações permitem que sua organização controle o tempo de retenção de conteúdo, para auditar o que as pessoas fazem com o conteúdo e adicionar códigos de barras ou rótulos a documentos. Uma política pode ajudar a garantir a conformidade com normas legais e governamentais ou processos corporativos internos. Como administrador, você pode configurar uma política para controlar como controlar documentos e quanto tempo manter documentos.
ms.openlocfilehash: b61c18390dde2e5d2da92189acced42ea5ece64c
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595608"
---
# <a name="create-and-apply-information-management-policies"></a>Criar e aplicar políticas de gerenciamento de informações

As políticas de gerenciamento de informações permitem que sua organização controle o tempo de retenção de conteúdo, para auditar o que as pessoas fazem com o conteúdo e adicionar códigos de barras ou rótulos a documentos. Uma política pode ajudar a garantir a conformidade com normas legais e governamentais ou processos corporativos internos. Como administrador, você pode configurar uma política para controlar como controlar documentos e quanto tempo manter documentos.
  
Você pode criar uma política de gerenciamento de informações em três locais diferentes na hierarquia do site, da mais ampla para a mais estreita:
  
- Criar uma política para usar em vários tipos de conteúdo dentro de um conjunto de sites.
    
- Criar uma política para um tipo de conteúdo de site.
    
- Criar uma política para uma lista ou biblioteca.
    
Confira mais informações em [introdução às políticas de gerenciamento de informações](intro-to-info-mgmt-policies.md).
  
## <a name="create-a-policy-for-multiple-content-types-within-a-site-collection"></a>Criar uma política para vários tipos de conteúdo em um conjunto de sites
<a name="__toc261001590"> </a>

Para garantir que uma política de informações seja aplicada a todos os documentos de um determinado tipo dentro de um conjunto de sites, considere a criação da política no nível do conjunto de sites e, posteriormente, aplique a política aos tipos de conteúdo. Eles são chamados de políticas de conjunto de sites. 
  
1. No botão \> **configurações**![de home page do conjunto de sites do SharePoint 2016, na barra de título.](media/1c22d2d8-39e0-4930-82c6-c3eee44211d3.png) \> **Configurações do site**.
    
    Em um site conectado ao grupo do SharePoint, clique em **configurações**, em **conteúdo do site**e em **configurações do site**. 
    
2. Na página Configurações do site, em **modelos de política de tipo de conteúdo**da administração \> do conjunto de **sites** . 
  
![Link do modelo de política de tipo de conteúdo na página Definições do site](media/26d3466a-23ec-443f-88f0-2aaff38e992b.png)
  
3. Na página \> políticas **criar**. 
    
4. Insira um nome e uma descrição para a política e, em seguida, escreva uma breve declaração de política que explica aos usuários a finalidade da política.
    
5. Consulte a próxima seção sobre como criar políticas para um tipo de conteúdo de site para saber como configurar os recursos que você deseja associar à política. 
    
6. Escolha **OK**.
    
## <a name="create-a-policy-for-a-site-content-type"></a>Criar uma política para um tipo de conteúdo de site
<a name="__create_a_policy"> </a>

A adição de uma política de gerenciamento de informações a um tipo de conteúdo facilita a associação de recursos de política com várias listas ou bibliotecas. Você pode optar por adicionar uma política de gerenciamento de informações existente a um tipo de conteúdo ou criar uma política exclusiva específica para um tipo de conteúdo individual.
  
 Você também pode adicionar uma política de gerenciamento de informações a um tipo de conteúdo específico às listas. Isso tem o efeito de aplicar a política somente aos itens dessa lista que estão usando o tipo de conteúdo. 
  
1. No botão \> **configurações**![de home page do conjunto de sites do SharePoint 2016, na barra de título.](media/1c22d2d8-39e0-4930-82c6-c3eee44211d3.png) \> **Configurações do site**.
    
    Em um site conectado ao grupo do SharePoint, clique em **configurações**, em **conteúdo do site**e em **configurações do site**. 
    
2. Na página Configurações do site, em **tipos de conteúdo de site**de galerias \> do **Web designer** .
  
![Link tipos de conteúdo do site na página Configurações do site](media/6f6fa51f-15d7-4782-b06f-a7b36e874cd3.png)
  
3. Na página Configurações de tipo de conteúdo do site, selecione o tipo de conteúdo ao qual você deseja adicionar uma política.
    
4. Na página tipo de conteúdo do site, **em** \> **configurações da política de gerenciamento de informações**.
    
5. Na página Editar política, insira um nome e uma descrição para a política e, em seguida, escreva uma breve descrição que explique aos usuários o que é a política.
    
6. Nas próximas seções, selecione os recursos de política individuais que você deseja adicionar à política de gerenciamento de informações. 
  
![Tipos de políticas de conteúdo](media/19fcb8a3-974b-40d3-a13f-b76088d122f8.png)
  
7. Para especificar um período de retenção para documentos e itens sujeitos a esta política, escolha **habilitar retenção**e, em seguida, especifique o período de retenção e as ações que você deseja que ocorram quando os itens expirarem.
    
    Para especificar um período de retenção
    
||||||**1.**|* * Escolha * * Adicionar um estágio de retenção para registros... * * * *|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||2.  <br/> | Selecione uma opção de período de retenção para especificar quando documentos ou itens estão definidos para expirar. Siga um destes procedimentos:  <br/>  Para definir a data de vencimento com base em uma propriedade de data, em **evento** \> **este estágio é baseado em uma propriedade de data no item**e, em seguida, selecione a ação de documento ou item (por exemplo, criado ou modificado) e o incremento de tempo após esta ação (por exemplo, o número de dias, meses ou anos) quando você deseja que o item expire.  <br/>  Para usar uma fórmula de retenção personalizada para determinar a expiração, escolha **definir por uma fórmula de retenção personalizada instalada neste servidor**.  <br/> > [!NOTE]> essa opção só estará disponível se uma fórmula personalizada tiver sido configurada pelo administrador.           |
||||||3.  <br/> |A opção **Iniciar um fluxo de trabalho** só estará disponível se você estiver definindo uma política para uma lista, biblioteca ou tipo de conteúdo que já tenha um fluxo de trabalho associado. Você receberá uma opção de fluxos de trabalho para escolher.  <br/> |
||||||4.  <br/> |Na seção **recorrência** , selecione **repetir a ação deste estágio...** e insira com que frequência você deseja que a ação ocorra novamente.  <br/> > [!NOTE]> essa opção só estará disponível se a ação selecionada puder ser repetida. Por exemplo, você não pode definir a recorrência para que a ação seja **excluída permanentemente**.           |
||||||5.  <br/> |Escolha **OK**.  <br/> |
   
1. Para habilitar a auditoria para os documentos e itens sujeitos a esta política, escolha **habilitar auditoria**e especifique os eventos que você deseja auditar.
    
    Para habilitar a auditoria
    
||||||1. * * *|Na página Editar política, * * **em** **auditoria** **\>** **habilitar auditoria** * * e marque as caixas de seleção ao lado dos eventos para os quais você deseja manter uma trilha de auditoria. * * * *|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||**2.** <br/> |**Para solicitar que os usuários insiram esses códigos de barras em documentos,** **escolha** **avisar os usuários para inserir um código de barras antes de salvar ou imprimir** **.** <br/> |
||||||**3.** <br/> |**Escolha** **OK** * * para aplicar o recurso de auditoria à política. ** <br/> |
|||||||O recurso de política de auditoria permite que as organizações criem e analisem trilhas de auditoria para documentos e listem itens como listas de tarefas, listas de problemas, grupos de discussão e calendários. Esse recurso de política fornece um log de auditoria que registra eventos, por exemplo, quando o conteúdo é visualizado, editado ou excluído.  <br/> |
|||||||Quando a auditoria é habilitada como parte de uma política de gerenciamento de informações, os administradores podem exibir os dados de auditoria em relatórios de uso de política baseados no Microsoft Excel e que resumem o uso atual. Os administradores podem usar esses relatórios para determinar como as informações estão sendo utilizadas na organização. Esses relatórios também podem ajudar as organizações a verificar e documentar a conformidade normativa ou a investigar possíveis preocupações.  <br/> |
|||||||O log de auditoria registra as seguintes informações: nome do evento, data e hora do evento e nome do sistema do usuário que executou a ação.  <br/> |
   
1. Quando os códigos de barras são habilitados como parte de uma política, são adicionados às propriedades do documento e exibidos na área de cabeçalho do documento ao qual o código de barras é aplicado. Como rótulos, os códigos de barras também podem ser removidos manualmente de um documento. Você pode especificar se os usuários devem ser solicitados a incluir o código de barras ao imprimir ou salvar um item ou se o código de barras deve ser inserido manualmente usando a guia **Inserir** em programas de lançamento do Office 2010. 
    
    Para habilitar códigos de barras
    
||||||1. * * *|**Na página Editar política, em **códigos de barras** \> , **habilite códigos de barras**.**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||**2.** <br/> |Para solicitar que os usuários insiram esses códigos de barras em documentos, escolha **avisar os usuários para inserir um código de barras antes de salvar ou imprimir**.  <br/> |
||||||**3.** <br/> |Escolha **OK** para aplicar o recurso de código de barras à política.  <br/> |
|||||||
 A política de código de barras gera códigos de barras padrão de código 39. Cada imagem de código de barras inclui texto abaixo do símbolo de código de barras que representa o valor do código de barras. Isso permite que os dados de código de barras sejam usados mesmo quando o hardware de verificação não está disponível. Os usuários podem digitar manualmente o número do código de barras na caixa de pesquisa para localizar o item em um site.  <br/> |
   
1. Para exigir que os documentos que estão sujeitos a essa política tenham rótulos, escolha **habilitar rótulos**e especifique as configurações desejadas para os rótulos.
    
    Para habilitar rótulos
    
||||||**1.**|* * Para exigir que os usuários adicionem um rótulo a um documento, escolha **avisar os usuários para inserir um rótulo antes de salvar ou imprimir**.  <br/> > [!NOTE]> se quiser que os rótulos sejam opcionais, não marque essa caixa de seleção.        **|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||2.  <br/> |Para bloquear um rótulo de modo que ele não possa ser alterado depois de inserido, escolha **impedir alterações nos rótulos depois de adicionados**.  <br/>  Essa configuração impede que o texto do rótulo seja atualizado depois que o rótulo tiver sido inserido em um item de um aplicativo cliente, como Word, Excel ou PowerPoint. Se você quiser que o rótulo seja adicionado quando as propriedades desse documento ou item forem atualizadas, não marque essa caixa de seleção.  <br/> |
||||||3.  <br/> |Na caixa formato do rótulo, insira o texto do rótulo como você deseja que ele seja exibido. Os rótulos podem conter até 10 referências de coluna, cada um deles pode ter até 255 caracteres de comprimento. Para criar o formato do rótulo, faça o seguinte:  <br/> Digite os nomes das colunas que você deseja incluir no rótulo na ordem em que você deseja que eles apareçam. Coloque os nomes das colunas entre chaves ({}), conforme mostrado no exemplo da página Editar política.  <br/> Digite palavras para identificar as colunas fora dos colchetes, conforme mostrado no exemplo da página Editar política.  <br/> |
||||||4.  <br/> |Para adicionar uma quebra de linha, insira **\n** onde você deseja que a quebra de linha apareça.  <br/> |
||||||5.  <br/> |Selecione o tamanho e o estilo da fonte que você deseja e especifique se deseja posicionar o rótulo à esquerda, centralizar ou à direita no documento.  <br/>  Selecione uma fonte e um estilo disponíveis nos computadores dos usuários. O tamanho da fonte afeta a quantidade de texto que pode ser exibida no rótulo.  <br/> |
||||||6.  <br/> |Insira a altura e a largura do rótulo. A altura e a largura podem ter de.50 a 63,5 cm. O texto do rótulo sempre é centralizado verticalmente na imagem.  <br/> |
||||||7.  <br/> |Escolha **Atualizar** para visualizar o conteúdo do rótulo.  <br/> |
   
1. Escolha **OK**.
    
## <a name="create-a-policy-for-a-list-library-or-folder-location-based-retention-policy"></a>Criar uma política para uma lista, biblioteca ou pasta (política de retenção com base em local)
<a name="__create_a_policy"> </a>

Você pode definir uma política de retenção que se aplica apenas a uma lista, uma biblioteca ou uma pasta específica. No entanto, se você criar uma política de retenção dessa maneira, não será possível reutilizar essa política em outras listas, bibliotecas, pastas ou sites, e não será possível aplicar uma política de conjunto de sites a uma política baseada em local.
  
Se você deseja aplicar uma única política de retenção a todos os tipos de conteúdo em um único local, você provavelmente vai querer usar a retenção baseada em local. Na maioria dos outros casos, você desejará verificar se uma política de retenção está especificada para todos os tipos de conteúdo.
  
 Cada subpasta herda a política de retenção de seu pai, a menos que você opte por interromper a herança e definir uma nova política de retenção no nível filho. 
  
Se você quiser definir uma política de gerenciamento de informações diferente da retenção para uma lista ou biblioteca, precisará definir uma política de gerenciamento de informações para cada tipo de conteúdo de lista individual associado a essa lista ou biblioteca.
  
 Se, a qualquer momento, você decidir mudar de tipo de conteúdo para políticas baseadas em local para uma lista ou biblioteca, somente a política de retenção será usada como a política baseada em local. Todas as outras políticas de gerenciamento (auditorias, códigos de barras e códigos de barras) serão herdadas dos tipos de conteúdo associados. 
  
 As políticas baseadas em local podem ser desabilitadas para um conjunto de sites por meio da desativação do recurso de retenção baseado em pasta e biblioteca. Isso permite que os administradores do conjunto de sites garantam que suas políticas de tipo de conteúdo não sejam substituídas pelas políticas baseadas no local de um administrador de listas. 
  
Você precisa de pelo menos a permissão gerenciar listas para alterar as configurações de política de gerenciamento de informações de uma lista ou biblioteca.
  
1. Navegue até a lista ou biblioteca para a qual você deseja especificar uma política de gerenciamento de informações. 
    
2. Na faixa de opções, escolha as **configurações** da biblioteca \> de guias de **biblioteca** ou de **lista** ou **configurações de lista**.
    
    No SharePoint Online, clique em **configurações** e, em seguida, clique em configurações da **lista** ou **configurações da biblioteca**. 
    
3. Em **permissões e configurações de política de gerenciamento de informações de gerenciamento** \> ****.
  
![Link de políticas de gerenciamento de informações na página de configurações da biblioteca de documentos](media/9fa6d366-6aab-49e1-a05c-898ac6f536e6.png)
  
4. Na página Configurações de política de gerenciamento de informações, certifique-se de que a fonte de retenção da lista ou biblioteca está definida como biblioteca e pastas. 
  
Se **tipo de conteúdo** aparecer como origem, clique em **Alterar fonte**e em **biblioteca e pastas**. Você é alertado de que as políticas de retenção de tipo de conteúdo serão ignoradas. Escolha **OK**. 
    
5. Na página Editar política, em **agendamento de retenção baseado em biblioteca**, insira uma breve descrição para a política que você está criando. 
    
6. Escolha **Adicionar um estágio de retenção...**
    
     Observe que, em registros, você pode optar por definir diferentes políticas de retenção para registros, selecionando a opção definir diferentes estágios de retenção para registros. 
    
7. Na caixa de diálogo Propriedades do estágio, selecione uma opção de período de retenção para especificar quando os documentos ou itens estão definidos para expirar. Siga um destes procedimentos:
    
  - Para definir a data de vencimento com base em uma propriedade de data, em **evento** \> **este estágio é baseado em uma propriedade de data no item**e, em seguida, selecione a ação de documento ou item (por exemplo, criado ou modificado) e o incremento de tempo após esta ação (por exemplo, o número de dias, meses ou anos) quando você deseja que o item expire. 
    
  - Para usar uma fórmula de retenção personalizada para determinar a expiração, escolha **definir por uma fórmula de retenção personalizada instalada neste servidor**. 
    
    > [!NOTE]
    >  Essa opção estará disponível somente se uma fórmula personalizada tiver sido configurada pelo administrador. 
  
  - Em **ação**, especifique o que você deseja que aconteça quando o documento ou item expirar. Para permitir que uma ação específica ocorra para o documento ou item (como exclusão), selecione uma ação na lista. 
    
8. A opção **Iniciar um fluxo de trabalho** só estará disponível se você estiver definindo uma política para uma lista, biblioteca ou tipo de conteúdo que já tenha um fluxo de trabalho associado. Você receberá uma opção de fluxos de trabalho para escolher. 
    
9. Em **recorrência**, escolha **repetir a ação deste estágio...** e insira com que frequência você deseja que a ação ocorra novamente. 
    
    > [!NOTE]
    >  Essa opção só estará disponível se a ação selecionada puder ser repetida. Por exemplo, você não pode definir a recorrência para que a ação seja **excluída permanentemente**. 
  
10. Escolha **OK**.
    
## <a name="apply-a-site-collection-policy-to-a-content-type"></a>Aplicar uma política de conjunto de sites a um tipo de conteúdo
<a name="__apply_a_site"> </a>

Se as políticas de gerenciamento de informações já tiverem sido criadas para seu site como políticas de conjunto de sites, você poderá aplicar uma das políticas a um tipo de conteúdo. Fazendo isso, você pode aplicar a mesma política a vários tipos de conteúdo em um conjunto de sites que não compartilham o mesmo tipo de conteúdo pai.
  
 Se você quiser aplicar políticas a vários tipos de conteúdo em um conjunto de sites e tiver um serviço de metadados gerenciados configurado, você pode usar a publicação de tipo de conteúdo para publicar políticas de gerenciamento de informações para vários conjuntos de sites. Consulte a seção [aplicar uma política nos conjuntos de sites](#apply-a-policy-across-site-collections) para obter mais informações. 
  
1. Navegue até a lista ou biblioteca que contém o tipo de conteúdo ao qual você deseja aplicar uma política.
    
2. Na faixa de opções, escolha as **configurações** da biblioteca \> de guias de **biblioteca** ou de **lista** ou **configurações de lista**.
    
    No SharePoint Online, clique em **configurações** e, em seguida, clique em configurações da **lista** ou **configurações da biblioteca**. 
    
3. Em **permissões e configurações de política de gerenciamento de informações de gerenciamento** \> ****.
  
![Link de políticas de gerenciamento de informações na página de configurações da biblioteca de documentos](media/9fa6d366-6aab-49e1-a05c-898ac6f536e6.png)
  
4. Verifique se a fonte de política está definida como **tipos de conteúdo**e em políticas de tipo de **conteúdo** selecione o tipo de conteúdo ao qual você deseja aplicar a política. 
    
5. Em **especificar a política** \> , **use uma política de conjunto de sites**e, em seguida, selecione a política que você deseja aplicar a partir da lista. 
    
    > [!NOTE]
    >  Se a opção **usar uma política de conjunto de sites** não estiver disponível, nenhuma política de conjunto de sites foi definida para o conjunto de sites. 
  
6. Escolha **OK**.
    
     Se a lista ou biblioteca que você está trabalhando com suporte para o gerenciamento de vários tipos de conteúdo, em **tipos de conteúdo** , você pode escolher o tipo de conteúdo para o qual deseja especificar uma política de gerenciamento de informações. Isso levará você diretamente para a etapa 5 acima. 
    
## <a name="apply-a-policy-across-site-collections"></a>Aplicar uma política nos conjuntos de sites
<a name="__toc260646789"> </a>

Compartilhar tipos de conteúdo entre conjuntos de sites usando um aplicativo de serviço de metadados gerenciados para configurar a publicação de tipo de conteúdo. A publicação de tipo de conteúdo ajuda você a gerenciar conteúdo e metadados de forma consistente em seus sites, pois os tipos de conteúdo podem ser criados e atualizados centralmente, e as atualizações podem ser publicadas em vários conjuntos de sites de inscrição ou aplicativos Web.
  
## <a name="create-a-template-from-an-existing-policy-to-use-across-site-collections"></a>Criar um modelo de uma política existente para usar nos conjuntos de sites
<a name="__toc262125409"> </a>

Você pode definir uma política de gerenciamento de informações e, em seguida, criar um modelo a partir dela para usá-lo conforme necessário em vários conjuntos de sites. Este método pode ser usado se você quiser ter um backup de suas políticas de informações ou também pode ser usado como um método alternativo para usar a publicação de tipo de conteúdo para aplicar uma política nos conjuntos de sites. Você cria um modelo ou backup da política exportando a política de um conjunto de sites e, em seguida, importando-o para um local salvo ou para outro conjunto de sites.
  
> [!IMPORTANT]
>  Se você estiver usando o recurso de exportação/importação como uma maneira de criar um conjunto de modelos de política, lembre-se de que existe um identificador exclusivo no arquivo Policy. xml. Por causa disso, não é possível importar essa política para um site mais de uma vez sem alterar esse identificador exclusivo. 
  
### <a name="export-a-policy"></a>Exportar uma política
<a name="__toc260646790"> </a>

1. Na home page do conjunto de sites, escolha **configurações**![pequenas de configurações de engrenagem que tomaram o lugar das configurações do site. ](media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png) **site.** \>
    
    Em um site conectado ao grupo do SharePoint, clique em **configurações**, em **conteúdo do site**e em **configurações do site**. 
    
2. Na página Configurações do site, em **modelos de política de tipo de conteúdo**da administração \> do conjunto de **sites** . 
  
![Link do modelo de política de tipo de conteúdo na página Definições do site](media/26d3466a-23ec-443f-88f0-2aaff38e992b.png)
  
3. Escolha a política que você deseja exportar \> rolar para a \> **exportação**inferior.
    
4. No prompt para salvar ou abrir o arquivo, escolha **salvar**e selecione um local para salvar o arquivo. Certifique-se de selecionar um local que esteja disponível para os conjuntos de sites que estão importando a política.
    
5. Quando a caixa de diálogo baixar completo for exibida, escolha **fechar**.
    
### <a name="import-a-policy-to-a-different-site-collection"></a>Importar uma política para um conjunto de sites diferente
<a name="__toc260646791"> </a>

A importação de uma política de gerenciamento de informações permite que você a aplique a vários tipos de conteúdo no site ou nível de lista em um determinado conjunto de sites. Os benefícios de fazer isso são duplos: não é necessário redefinir e aplicar a política em cada tipo de conteúdo, e você pode gerenciar mais facilmente as modificações de política fazendo alterações na política em apenas um local.
  
1. Na home page do conjunto de sites ao qual você deseja aplicar a política, escolha **configurações**![pequenas engrenagens que levaram o local das configurações do site. ](media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png) **site.** \>
    
    Em um site conectado ao grupo do SharePoint, clique em **configurações**, em **conteúdo do site**e em **configurações do site**. 
    
2. Na página Configurações do site, em **modelos de política de tipo de conteúdo**da administração \> do conjunto de **sites** .
    
3. Na página \> políticas, **importe** \> **procurar** para localizar o arquivo XML da política. 
    
4. Selecione o arquivo XML no qual a política foi salva \> **aberta**. 
    
5. Na \> **página Importar** política de conjunto de sites para adicionar a política ao conjunto de sites. 
    
A política importada agora pode ser aplicada a um ou vários tipos de conteúdo no nível do site ou da lista. 
  
As políticas de gerenciamento de informações permitem que sua organização controle o tempo de retenção de conteúdo, para auditar o que as pessoas fazem com o conteúdo e adicionar códigos de barras ou rótulos a documentos. Uma política pode ajudar a garantir a conformidade com normas legais e governamentais ou processos corporativos internos. Como administrador, você pode configurar uma política para controlar como controlar documentos e quanto tempo manter documentos.

Você pode criar uma política de gerenciamento de informações em três locais diferentes na hierarquia do site, da mais ampla para a mais estreita:
- Criar uma política para usar em vários tipos de conteúdo dentro de um conjunto de sites.
- Criar uma política para um tipo de conteúdo de site.
- Criar uma política para uma lista ou biblioteca.

Confira mais informações em [introdução às políticas de gerenciamento de informações](intro-to-info-mgmt-policies.md).
  

