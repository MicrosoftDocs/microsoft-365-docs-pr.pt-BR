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
ms.custom:
- seo-marvel-apr2020
description: Saiba como configurar uma política de gerenciamento de informações para controlar por quanto tempo as informações são mantidas e controlar quem está usando as informações.
ms.openlocfilehash: 2519f039e7495d01a828aee564ce1a6caf41342d
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817990"
---
# <a name="create-and-apply-information-management-policies"></a>Criar e aplicar políticas de gerenciamento de informações

As políticas de gerenciamento de informações permitem que sua organização controle por quanto tempo reter conteúdo, audite o que as pessoas fazem com o conteúdo e adicione códigos de barras ou rótulos a documentos. Uma política pode ajudar a impor a conformidade com regulamentos legais e governamentais ou processos empresariais internos. Como administrador, você pode configurar uma política para controlar como rastrear documentos e por quanto tempo manter os documentos.
  
Você pode criar uma política de gerenciamento de informações em três locais diferentes na hierarquia do site, do mais amplo ao mais estreito:
  
- Crie uma política a ser usada em vários tipos de conteúdo em um conjunto de sites.
    
- Criar uma política para um tipo de conteúdo de site.
    
- Crie uma política para uma lista ou biblioteca.
    
Para obter mais informações, consulte [Introdução às políticas de gerenciamento de informações.](intro-to-info-mgmt-policies.md)
  
## <a name="create-a-policy-for-multiple-content-types-within-a-site-collection"></a>Criar uma política para vários tipos de conteúdo em um conjunto de sites
<a name="__toc261001590"> </a>

Para garantir que uma política de informações seja aplicada a todos os documentos de um determinado tipo em um conjunto de sites, considere a criação da política no nível do conjunto de sites e, posteriormente, aplique a política aos tipos de conteúdo. Eles são chamados de políticas de conjunto de sites. 
  
1. Na home page do conjunto de \> **sites, botão Configurações** ![ do SharePoint 2016 na barra de título.](../media/1c22d2d8-39e0-4930-82c6-c3eee44211d3.png) \> **Configurações do site**.
    
    Em um site conectado ao grupo do SharePoint, clique em **Configurações,** clique em Conteúdo do **Site** e em Configurações **do Site.** 
    
2. Na página Configurações do Site, em **Modelos de** Política de Tipo de Conteúdo de Administração de Conjunto \> **de Sites.** 
  
![Link de Modelo de Política de Tipo de Conteúdo na página Configurações do Site](../media/26d3466a-23ec-443f-88f0-2aaff38e992b.png)
  
3. Na página Políticas, \> **Crie**. 
    
4. Insira um nome e uma descrição para a política e, em seguida, escreva uma breve declaração de política que explique aos usuários para que a política se trata.
    
5. Consulte a próxima seção sobre como criar políticas para um tipo de conteúdo de site para saber como configurar os recursos que você deseja associar à política. 
    
6. Escolha **OK**.
    
## <a name="create-a-policy-for-a-site-content-type"></a>Criar uma política para um tipo de conteúdo de site
<a name="__create_a_policy"> </a>

Adicionar uma política de gerenciamento de informações a um tipo de conteúdo facilita a associação de recursos de política a várias listas ou bibliotecas. Você pode optar por adicionar uma política de gerenciamento de informações existente a um tipo de conteúdo ou criar uma política exclusiva específica para um tipo de conteúdo individual.
  
 Você também pode adicionar uma política de gerenciamento de informações a um tipo de conteúdo específico de listas. Isso tem o efeito de aplicar a política apenas aos itens nessa lista que estão usando o tipo de conteúdo. 
  
1. Na home page do conjunto de \> **sites, botão Configurações** ![ do SharePoint 2016 na barra de título.](../media/1c22d2d8-39e0-4930-82c6-c3eee44211d3.png) \> **Configurações do site**.
    
    Em um site conectado ao grupo do SharePoint, clique em **Configurações,** clique em Conteúdo do **Site** e em Configurações **do Site.** 
    
2. Na página Configurações do Site, em Galerias de **Web Designer,** tipos de conteúdo \> **de site.**
  
![Link de tipos de conteúdo de site na página Configurações do Site](../media/6f6fa51f-15d7-4782-b06f-a7b36e874cd3.png)
  
3. Na página Configurações de Tipo de Conteúdo de Site, selecione o tipo de conteúdo ao qual deseja adicionar uma política.
    
4. Na página Tipo de Conteúdo de Site, em **Configurações configurações** de política de \> **gerenciamento de informações.**
    
5. Na página Editar Política, insira um nome e uma descrição para a política e, em seguida, escreva uma breve descrição que explique aos usuários para o que a política é.
    
6. Nas próximas seções, selecione os recursos de política individuais que você deseja adicionar à sua política de gerenciamento de informações. 
  
![Tipos de políticas de conteúdo](../media/19fcb8a3-974b-40d3-a13f-b76088d122f8.png)
  
7. Para especificar um período de retenção para documentos e itens sujeitos a essa política, escolha Habilitar Retenção e especifique o período de retenção e as ações que você deseja que ocorram quando os itens expirarem.
    
    Para especificar um período de retenção
    
||||||**1.**|**Choose **Add a retention stage for records...****|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||2.  <br/> | Selecione uma opção de período de retenção para especificar quando os documentos ou itens estão definidos para expirar. Siga um destes procedimentos:  <br/>  Para definir a data de expiração  com base em uma propriedade de data, em Evento Este estágio é baseado em uma propriedade de data no item e selecione o documento ou a ação do item (por exemplo, Criado ou Modificado) e o incremento de tempo após essa ação (por exemplo, o número de dias, meses ou anos) quando você deseja que o \> item expire.  <br/>  Para usar uma fórmula de retenção personalizada para determinar a expiração, escolha Definir por uma fórmula de **retenção personalizada instalada neste servidor.**  <br/> > [!NOTE]> Essa opção só estará disponível se uma fórmula personalizada tiver sido configurada pelo administrador.           |
||||||3.  <br/> |A **opção Iniciar um** fluxo de trabalho só estará disponível se você estiver definindo uma política para uma lista, biblioteca ou tipo de conteúdo que já tenha um fluxo de trabalho associado a ele. Em seguida, você receberá uma opção de fluxos de trabalho para escolher.  <br/> |
||||||4.  <br/> |Na seção **Recorrência, selecione** **Repetir a ação deste estágio...** e insira a frequência com que você deseja que a ação se reaquece.  <br/> > [!NOTE]> Essa opção só estará disponível se a ação selecionada puder ser repetida. Por exemplo, você não pode definir a recorrência para a ação Excluir **Permanentemente.**           |
||||||5.  <br/> |Escolha **OK**.  <br/> |
   
1. Para habilitar a auditoria para os documentos e itens sujeitos a essa política, escolha Habilitar Auditoria e especifique os eventos que você deseja auditar.
    
    Para habilitar a auditoria
    
||||||1.****|Na página Editar Política,** em  **Auditoria** Habilitar auditoria **, marque as caixas de seleção ao lado dos eventos para os quais você deseja manter uma trilha de **\>**  auditoria.****|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||**2.** <br/> |**Para solicitar que os usuários insiram esses códigos de barras em documentos,**  escolha Solicitar que os usuários insiram um código de barras **antes de salvar ou imprimir.**  <br/> |
||||||**3.** <br/> |**Escolha** **OK** ** para aplicar o recurso de auditoria à política. ** <br/> |
|||||||O recurso de Política de Auditoria permite que as organizações criem e analisem trilhas de auditoria para documentos e listem itens como listas de tarefas, listas de problemas, grupos de discussão e calendários. Esse recurso de política fornece um log de auditoria que registra eventos, por exemplo, quando o conteúdo é visualizado, editado ou excluído.  <br/> |
|||||||Quando a auditoria é habilitada como parte de uma política de gerenciamento de informações, os administradores podem exibir os dados de auditoria em relatórios de uso de política baseados no Microsoft Excel e que resumem o uso atual. Os administradores podem usar esses relatórios para determinar como as informações estão sendo utilizadas na organização. Esses relatórios também podem ajudar as organizações a verificar e documentar sua conformidade regulamentar ou investigar possíveis preocupações.  <br/> |
|||||||O log de auditoria registra as seguintes informações: nome do evento, data e hora do evento e nome do sistema do usuário que executou a ação.  <br/> |
   
1. Quando códigos de barras são habilitados como parte de uma política, eles são adicionados às propriedades do documento e exibidos na área de header do documento ao qual o código de barras é aplicado. Assim como os rótulos, os códigos de barras também podem ser removidos manualmente de um documento. Você pode especificar se os usuários devem ser solicitados a incluir o código de barras ao  imprimir ou salvar um item ou se o código de barras deve ser inserido manualmente usando a guia Inserir em programas de lançamento do Office 2010. 
    
    Para habilitar códigos de barras
    
||||||1.****|**Na página Editar Política, em Códigos de **Barras,** \> **Habilitar Códigos de Barras.****|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||**2.** <br/> |Para solicitar que os usuários insiram esses códigos de barras em documentos, escolha Solicitar que os usuários insiram um código de barras **antes de salvar ou imprimir.**  <br/> |
||||||**3.** <br/> |Escolha **OK** para aplicar o recurso de código de barras à política.  <br/> |
|||||||
 A política de código de barras gera códigos de barras padrão do Código 39. Cada imagem de código de barras inclui texto abaixo do símbolo de código de barras que representa o valor do código de barras. Isso permite que os dados de código de barras sejam usados mesmo quando a verificação de hardware não estiver disponível. Os usuários podem digitar manualmente o número de código de barras na caixa de pesquisa para localizar o item em um site.  <br/> |
   
1. Para exigir que os documentos sujeitos a essa política tenham rótulos, escolha Habilitar Rótulos e especifique as configurações que você deseja para os rótulos.
    
    Para habilitar rótulos
    
||||||**1.**|**Para exigir que os usuários adicionem um rótulo a um documento, escolha Solicitar que os usuários insiram um **rótulo antes de salvar ou imprimir.**  <br/> > [!NOTE]> Se você quiser que os rótulos sejam opcionais, não marque essa caixa de seleção.        **|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
||||||2.  <br/> |Para bloquear um rótulo de forma que ele não possa ser alterado depois que ele tiver sido inserido, escolha Impedir alterações nos rótulos **depois que eles são adicionados.**  <br/>  Essa configuração impede que o texto do rótulo seja atualizado depois que o rótulo é inserido em um item dentro de um aplicativo cliente, como Word, Excel ou PowerPoint. Se você quiser que o rótulo seja adicionado quando as propriedades desse documento ou item forem atualizadas, não marque essa caixa de seleção.  <br/> |
||||||3.  <br/> |Na caixa Formato do rótulo, insira o texto do rótulo como você deseja que ele seja exibido. Os rótulos podem conter até 10 referências de coluna, sendo que cada uma pode ter até 255 caracteres. Para criar o formato do seu rótulo, faça o seguinte:  <br/> Digite os nomes das colunas que você deseja incluir no rótulo na ordem em que deseja que apareçam. Coloque os nomes das colunas entre colchetes ( ), conforme {} mostrado no exemplo na página Editar Política.  <br/> Digite palavras para identificar as colunas fora dos colchetes, conforme mostrado no exemplo na página Editar Política.  <br/> |
||||||4.  <br/> |Para adicionar uma quebra de linha, insira **\n** onde você deseja que a quebra de linha apareça.  <br/> |
||||||5.  <br/> |Selecione o tamanho e o estilo da fonte que você deseja e especifique se deseja que o rótulo seja posicionado à esquerda, ao centro ou à direita no documento.  <br/>  Selecione uma fonte e um estilo disponíveis nos computadores dos usuários. O tamanho da fonte afeta a quantidade de texto que pode ser exibida no rótulo.  <br/> |
||||||6.  <br/> |Insira a altura e a largura do rótulo. A altura e a largura podem ter de.50 a 63,5 cm. O texto do rótulo sempre é centralizado verticalmente na imagem.  <br/> |
||||||7.  <br/> |Escolha **Atualizar para** visualizar o conteúdo do rótulo.  <br/> |
   
1. Escolha **OK**.
    
## <a name="create-a-policy-for-a-list-library-or-folder-location-based-retention-policy"></a>Criar uma política para uma lista, biblioteca ou pasta (política de retenção com base em local)
<a name="__create_a_policy"> </a>

Você pode definir uma política de retenção que se aplica somente a uma lista, biblioteca ou pasta específica. No entanto, se você criar uma política de retenção dessa maneira, não poderá reutilizar essa política em outras listas, bibliotecas, pastas ou sites e não poderá aplicar uma política de conjunto de sites a uma política baseada em local.
  
Se você quiser aplicar uma única política de retenção a todos os tipos de conteúdo em um único local, provavelmente vai querer usar a retenção baseada em local. Na maioria dos outros casos, você vai querer verificar se uma política de retenção é especificada para todos os tipos de conteúdo.
  
 Cada subpasta herda a política de retenção de seu pai, a menos que você opte por quebrar a herança e definir uma nova política de retenção no nível filho. 
  
Se quiser definir uma política de gerenciamento de informações diferente da retenção para uma lista ou biblioteca, você precisará definir uma política de gerenciamento de informações para cada tipo de conteúdo de lista individual associado a essa lista ou biblioteca.
  
 Se, a qualquer momento, você decidir mudar do tipo de conteúdo para políticas baseadas em local para uma lista ou biblioteca, somente a política de retenção será usada como a política baseada em local. Todas as outras políticas de gerenciamento (auditorias, códigos de barras e códigos de barras) serão herdadas dos tipos de conteúdo associados. 
  
 As políticas baseadas em local podem ser desabilitadas para um conjunto de sites desativando o recurso Retenção Baseada em Biblioteca e Pasta. Isso permite que os administradores de conjunto de sites garantam que suas políticas de tipo de conteúdo não sejam substituídos pelas políticas baseadas em local de um administrador de lista. 
  
Você precisa pelo menos da permissão Gerenciar Listas para alterar as configurações de política de gerenciamento de informações de uma lista ou biblioteca.
  
1. Navegue até a lista ou biblioteca para a qual você deseja especificar uma política de gerenciamento de informações. 
    
2. Na faixa de opções, escolha as **configurações da** biblioteca ou **da guia** Biblioteca ou lista ou \>  **configurações de lista.**
    
    No SharePoint Online, clique **em Configurações** e em **Configurações de lista** ou configurações de **Biblioteca.** 
    
3. Em **Permissões e configurações de política de** gerenciamento de Informações de \> **Gerenciamento.**
  
![Link de políticas de gerenciamento de informações na página configurações da biblioteca de documentos](../media/9fa6d366-6aab-49e1-a05c-898ac6f536e6.png)
  
4. Na página Configurações da Política de Gerenciamento de Informações, certifique-se de que a fonte de retenção para a lista ou biblioteca está definida como Biblioteca e Pastas. 
  
Se **o Tipo de** Conteúdo aparecer como origem, clique em Alterar Fonte e, em seguida, clique em Biblioteca e **Pastas.**  Você será alertado de que as políticas de retenção de tipo de conteúdo serão ignoradas. Escolha **OK**. 
    
5. Na página Editar Política, em **Agenda de** Retenção Baseada em Biblioteca, insira uma breve descrição para a política que você está criando. 
    
6. Escolha **Adicionar um estágio de retenção...**
    
     Observe que, em Registros, você pode optar por definir diferentes políticas de retenção para registros selecionando a opção Definir diferentes estágios de retenção para registros. 
    
7. Na caixa de diálogo Propriedades do estágio, selecione uma opção de período de retenção para especificar quando os documentos ou itens estão definidos para expirar. Siga um destes procedimentos:
    
  - Para definir a data de expiração  com base em uma propriedade de data, em Evento Este estágio é baseado em uma propriedade de data no item e selecione o documento ou a ação do item (por exemplo, Criado ou Modificado) e o incremento de tempo após essa ação (por exemplo, o número de dias, meses ou anos) quando você deseja que o \> item expire. 
    
  - Para usar uma fórmula de retenção personalizada para determinar a expiração, escolha Definir por uma fórmula de **retenção personalizada instalada neste servidor.** 
    
    > [!NOTE]
    >  Essa opção só estará disponível se uma fórmula personalizada tiver sido configurada pelo administrador. 
  
  - Em **Ação,** especifique o que você deseja que aconteça quando o documento ou item expirar. Para permitir que uma ação específica aconteça com o documento ou item (como exclusão), selecione uma ação da lista. 
    
8. A **opção Iniciar um** fluxo de trabalho só estará disponível se você estiver definindo uma política para uma lista, biblioteca ou tipo de conteúdo que já tenha um fluxo de trabalho associado a ele. Em seguida, você receberá uma opção de fluxos de trabalho para escolher. 
    
9. Em **Recorrência,** escolha **Repetir a ação deste estágio...** e insira a frequência com que você deseja que a ação se reaquece. 
    
    > [!NOTE]
    >  Essa opção só estará disponível se a ação selecionada puder ser repetida. Por exemplo, você não pode definir a recorrência para a ação Excluir **Permanentemente.** 
  
10. Escolha **OK**.
    
## <a name="apply-a-site-collection-policy-to-a-content-type"></a>Aplicar uma política de conjunto de sites a um tipo de conteúdo
<a name="__apply_a_site"> </a>

Se as políticas de gerenciamento de informações já foram criadas para seu site como políticas de conjunto de sites, você pode aplicar uma das políticas a um tipo de conteúdo. Ao fazer isso, você pode aplicar a mesma política a vários tipos de conteúdo em um conjunto de sites que não compartilham o mesmo tipo de conteúdo pai.
  
 Se você quiser aplicar políticas a vários tipos de conteúdo em um conjunto de sites e tiver um Serviço de Metadados Gerenciados configurado, poderá usar a Publicação de Tipo de Conteúdo para publicar políticas de gerenciamento de informações em vários conjunto de sites. Consulte a seção [Aplicar uma política entre os conjunto de sites](#apply-a-policy-across-site-collections) para obter mais informações. 
  
1. Navegue até a lista ou biblioteca que contém o tipo de conteúdo ao qual você deseja aplicar uma política.
    
2. Na faixa de opções, escolha as **configurações da** biblioteca ou **da guia** Biblioteca ou lista ou \>  **configurações de lista.**
    
    No SharePoint Online, clique **em Configurações** e em **Configurações de lista** ou configurações de **Biblioteca.** 
    
3. Em **Permissões e configurações de política de** gerenciamento de Informações de \> **Gerenciamento.**
  
![Link de políticas de gerenciamento de informações na página configurações da biblioteca de documentos](../media/9fa6d366-6aab-49e1-a05c-898ac6f536e6.png)
  
4. Verifique se a fonte da política está  definida como Tipos de Conteúdo **e,** em Políticas de Tipo de Conteúdo, selecione o tipo de conteúdo ao qual você deseja aplicar a política. 
    
5. Under **Specify the Policy** Use a site collection \> **policy**, and then select the policy that you want to apply from the list. 
    
    > [!NOTE]
    >  Se a **opção Usar uma política de conjunto** de sites não estiver disponível, nenhuma política de conjunto de sites foi definida para o conjunto de sites. 
  
6. Escolha **OK**.
    
     Se a lista ou biblioteca com a qual você  está trabalhando oferece suporte ao gerenciamento de vários tipos de conteúdo, em Tipos de Conteúdo, você pode escolher o tipo de conteúdo para o qual deseja especificar uma política de gerenciamento de informações. Isso levará você diretamente para a Etapa 5 acima. 
    
## <a name="apply-a-policy-across-site-collections"></a>Aplicar uma política entre os conjunto de sites
<a name="__toc260646789"> </a>

Compartilhe tipos de conteúdo entre os conjunto de sites usando um aplicativo de serviço de Metadados Gerenciados para configurar a publicação de tipo de conteúdo. A publicação de tipo de conteúdo ajuda a gerenciar conteúdo e metadados consistentemente em seus sites, pois os tipos de conteúdo podem ser criados e atualizados centralmente, e as atualizações podem ser publicadas em vários conjunto de sites de assinatura ou aplicativos Web.
  
## <a name="create-a-template-from-an-existing-policy-to-use-across-site-collections"></a>Criar um modelo a partir de uma política existente a ser usada entre os conjunto de sites
<a name="__toc262125409"> </a>

Você pode definir uma política de gerenciamento de informações e, em seguida, criar um modelo a partir dela para usar conforme necessário em vários conjunto de sites. Esse método pode ser usado se você quiser ter um backup de suas políticas de informações ou também pode ser usado como um método alternativo para usar a publicação de tipo de conteúdo para aplicar uma política entre os conjunto de sites. Crie um modelo ou backup da política exportando a política de um conjunto de sites e importando-a para um local salvo ou para outro conjunto de sites.
  
> [!IMPORTANT]
>  Se você estiver usando o recurso de exportação/importação como uma maneira de criar um conjunto de modelos de política, tenha em mente que existe um identificador exclusivo no arquivo .xml da política. Por isso, não é possível importar essa política para um site mais de uma vez sem alterar esse identificador exclusivo. 
  
### <a name="export-a-policy"></a>Exportar uma política
<a name="__toc260646790"> </a>

1. Na home page do conjunto de sites, escolha Configurações de Engrenagem de Configurações Pequenas que ficou no lugar das Configurações do Site. Configurações ![ do ](../media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png) \> **Site.**
    
    Em um site conectado ao grupo do SharePoint, clique em **Configurações,** clique em Conteúdo do **Site** e em Configurações **do Site.** 
    
2. Na página Configurações do Site, em **Modelos de** Política de Tipo de Conteúdo de Administração de Conjunto \> **de Sites.** 
  
![Link de Modelo de Política de Tipo de Conteúdo na página Configurações do Site](../media/26d3466a-23ec-443f-88f0-2aaff38e992b.png)
  
3. Escolha a política que você deseja exportar a \> rolagem para a parte \> **inferior Exportar.**
    
4. No prompt para salvar ou abrir o arquivo, escolha **Salvar** e selecione um local para salvar o arquivo. Certifique-se de selecionar um local que está disponível para os conjunto de sites que estão importando a política.
    
5. Quando a caixa de diálogo Baixar Concluído for exibida, escolha **Fechar**.
    
### <a name="import-a-policy-to-a-different-site-collection"></a>Importar uma política para um conjunto de sites diferente
<a name="__toc260646791"> </a>

Importar uma política de gerenciamento de informações permite aplicá-la a vários tipos de conteúdo no nível do site ou da lista em qualquer conjunto de sites. Os benefícios de fazer isso são duas: você não precisa definir e aplicar a política em cada tipo de conteúdo e pode gerenciar mais facilmente as modificações de política fazendo alterações na política em apenas um local.
  
1. Na home page do conjunto de sites ao qual você deseja aplicar a política, escolha Configurações De engrenagem Configurações Pequenas que ficou no lugar das Configurações do Site. Configurações ![ do ](../media/a47a06c3-83fb-46b2-9c52-d1bad63e3e60.png) \> **Site.**
    
    Em um site conectado ao grupo do SharePoint, clique em **Configurações,** clique em Conteúdo do **Site** e em Configurações **do Site.** 
    
2. Na página Configurações do Site, em **Modelos de** Política de Tipo de Conteúdo de Administração de Conjunto \> **de Sites.**
    
3. Na página Políticas, \> **Importe** \> **Procurar** para encontrar o arquivo XML da política. 
    
4. Selecione o arquivo XML no qual a política foi \> **salva, Open**. 
    
5. Na página Importar uma Política de Conjunto de \> **Sites, importe** para adicionar a política ao conjunto de sites. 
    
Sua política importada agora pode ser aplicada a um ou vários tipos de conteúdo no nível do site ou da lista. 
  
As políticas de gerenciamento de informações permitem que sua organização controle por quanto tempo reter conteúdo, audite o que as pessoas fazem com o conteúdo e adicione códigos de barras ou rótulos a documentos. Uma política pode ajudar a impor a conformidade com regulamentos legais e governamentais ou processos empresariais internos. Como administrador, você pode configurar uma política para controlar como rastrear documentos e por quanto tempo manter os documentos.

Você pode criar uma política de gerenciamento de informações em três locais diferentes na hierarquia do site, do mais amplo ao mais estreito:
- Crie uma política a ser usada em vários tipos de conteúdo em um conjunto de sites.
- Criar uma política para um tipo de conteúdo de site.
- Crie uma política para uma lista ou biblioteca.

Para obter mais informações, consulte [Introdução às políticas de gerenciamento de informações.](intro-to-info-mgmt-policies.md)
  

