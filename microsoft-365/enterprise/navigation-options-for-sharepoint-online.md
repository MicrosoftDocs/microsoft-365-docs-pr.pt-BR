---
title: Opções de navegação para o SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 4/7/2020
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- SPO160
- MET150
ms.assetid: adb92b80-b342-4ecb-99a1-da2a2b4782eb
description: Este artigo descreve os sites de opções de navegação com a publicação do SharePoint habilitada no SharePoint Online.
ms.openlocfilehash: 86cefc60a26687835fd6a88de7f249143811de4f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695346"
---
# <a name="navigation-options-for-sharepoint-online"></a>Opções de navegação para o SharePoint Online

Este artigo descreve os sites de opções de navegação com a publicação do SharePoint habilitada no SharePoint Online. A escolha e a configuração de navegação impactam significativamente o desempenho e a escalabilidade de sites no SharePoint Online. O modelo de site de publicação do SharePoint deve ser usado somente se necessário para um portal centralizado e o recurso de publicação só deve ser habilitado em sites específicos e apenas quando é absolutamente necessário, pois pode afetar o desempenho quando usado incorretamente.

>[!NOTE]
>Se você estiver usando as opções de navegação modernas do SharePoint, como o menu mega, a navegação em cascata ou a navegação de Hub, este artigo não se aplicará ao seu site. As arquiteturas modernas de sites do SharePoint aproveitam uma hierarquia de sites mais nivelada e um modelo Hub e spoke. Isso permite que muitos cenários sejam alcançados e não exijam o uso do recurso de publicação do SharePoint.

## <a name="overview-of-navigation-options"></a>Visão geral das opções de navegação

A configuração do provedor de navegação pode impactar significativamente o desempenho de todo o site e é necessário fazer uma consideração cuidadosa para escolher um provedor de navegação e uma configuração que sejam dimensionados de forma eficaz para os requisitos de um site do SharePoint. Há dois provedores de navegação prontos para uso, bem como implementações de navegação personalizadas.

A primeira opção, [**navegação estrutural**](#using-structural-navigation-in-sharepoint-online), é a opção de navegação recomendada no SharePoint Online para sites clássicos do SharePoint, **se você ativar o cache estrutural de navegação para seu site**. Este provedor de navegação exibe os itens de navegação abaixo do site atual e, opcionalmente, o site atual e seus irmãos. Ele fornece recursos adicionais como filtragem de segurança e enumeração de estrutura do site. Se o cache estiver desabilitado, isso causará impacto negativo no desempenho e na escalabilidade e poderá estar sujeito à limitação.

A segunda opção, [**navegação gerenciada (metadados)**](#using-managed-navigation-and-metadata-in-sharepoint-online), representa itens de navegação usando um conjunto de termos de metadados gerenciados. Recomendamos que a filtragem de segurança seja desabilitada, a menos que seja necessário. O aparamento de segurança está habilitado como uma configuração segura por padrão para este provedor de navegação; no entanto, muitos sites não exigem a sobrecarga da filtragem de segurança, já que os elementos de navegação freqüentemente são consistentes para todos os usuários do site. Com a configuração recomendada para desabilitar a filtragem de segurança, esse provedor de navegação não requer a enumeração da estrutura do site e é altamente escalável com impacto de desempenho aceitável.

Além dos provedores de navegação prontos para uso, muitos clientes implementaram com êxito implementações de navegação personalizada alternativas. Confira [scripts do lado do cliente orientados por pesquisa](#using-search-driven-client-side-scripting) neste artigo.
  
## <a name="pros-and-cons-of-sharepoint-online-navigation-options"></a>Prós e contras das opções de navegação do SharePoint Online

A tabela a seguir resume os prós e contras de cada opção.

|Navegação estrutural  |Navegação gerenciada  |Navegação orientada por pesquisa  |Provedor de navegação personalizada  |
|---------|---------|---------|---------|
|Prós<br/><br/>Fácil de manter<br/>Segurança cortada<br/>Atualiza automaticamente dentro de 24 horas quando o conteúdo é alterado<br/>     |Prós<br/><br/>Fácil de manter<br/>|Prós<br/><br/>Segurança cortada<br/>Atualiza automaticamente à medida que os sites são adicionados<br/>Tempo de carregamento rápido e estrutura de navegação em cache local<br/>|Prós<br/><br/>Escolha mais ampla de opções disponíveis<br/>Carregamento rápido quando o cache é usado corretamente<br/>Muitas opções funcionam bem com o design de página responsivo<br/>|
|Contras<br/><br/>**Impacta o desempenho se o cache estiver desabilitado**<br/>Sujeito à limitação<br/>|Contras<br/><br/>Não atualizado automaticamente para refletir a estrutura do site<br/>**Impacta o desempenho se a filtragem de segurança estiver habilitada** ou quando a estrutura de navegação for complexa<br/>|Contras<br/><br/>Sem capacidade para encomendar facilmente sites<br/>Requer a personalização da página mestra (habilidades técnicas obrigatórias)<br/>|Contras<br/><br/>O desenvolvimento personalizado é necessário<br/>A fonte de dados externa/cache armazenado é necessária, por exemplo, o Azure<br/>|

A opção mais apropriada para seu site dependerá dos requisitos do seu site e do seu recurso técnico. Se você quiser um provedor de navegação fácil de configurar que seja atualizado automaticamente quando o conteúdo for alterado, a navegação estrutural [com cache habilitado](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43) será uma boa opção.

>[!NOTE]
>Aplicar o mesmo princípio de sites modernos do SharePoint simplificando a estrutura geral do site para uma estrutura não hierárquica do Flatter, melhora o desempenho e simplifica a movimentação para sites modernos do SharePoint. Isso significa que, em vez de ter um único conjunto de sites com centenas de sites (subwebs), uma abordagem melhor é ter muitos conjuntos de sites com muito poucos subsites (subwebs).

## <a name="analyzing-navigation-performance-in-sharepoint-online"></a>Analisando o desempenho de navegação no SharePoint Online

A [ferramenta diagnóstico de página do SharePoint](https://aka.ms/perftool) é uma extensão de navegador para o Microsoft Edge e navegadores Chrome que analisa o portal moderno do SharePoint Online e as páginas do site de publicação clássica. Essa ferramenta só funciona no SharePoint Online e não pode ser usada em uma página de sistema do SharePoint.

A ferramenta gera um relatório para cada página analisada mostrando como a página é executada em um conjunto de regras predefinido e exibe informações detalhadas quando os resultados de um teste ficam fora do valor da linha de base. Os administradores e designers do SharePoint Online podem usar a ferramenta para solucionar problemas de desempenho a fim de garantir que as novas páginas sejam otimizadas antes da publicação.

**SPRequestDuration** em particular é o tempo que o SharePoint leva para processar a página. Uma navegação intensa (como a inclusão de páginas na navegação), hierarquias de sites complexos e outras opções de configuração e topologia podem ser comparadas drasticamente a durações mais longas.

## <a name="using-structural-navigation-in-sharepoint-online"></a>Usando a navegação estrutural no SharePoint Online

Esta é a navegação pronta para uso, usada por padrão e é a solução mais direta. Não requer personalização e um usuário não técnico também pode facilmente adicionar itens, ocultar itens e gerenciar a navegação na página Configurações. É recomendável [habilitar o cache](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43), caso contrário, haverá uma compensação de desempenho dispendiosa.

### <a name="how-to-implement-structural-navigation-caching"></a>Como implementar o cache de navegação estrutural

Em **configurações do site**  >  **Look and Feel**  >  **navegação**de aparência, é possível validar se a navegação estrutural está selecionada para navegação global ou navegação atual. Selecionar **Mostrar páginas** terá um impacto negativo no desempenho.

![Navegação estrutural com mostrar subsites selecionados](../media/SPONavOptionsStructuredShowSubsites.png)

O armazenamento em cache pode ser habilitado ou desabilitado no nível do conjunto de sites e no nível do site e é habilitado por padrão. Para habilitar no nível do conjunto de sites, em **configurações do site**  >  **Site Collection Administration**  >  **navegação do conjunto de sites**da administração do conjunto de sites, marque a caixa de diálogo **Habilitar cache**.

![Habilitar o cache no nível do site](../media/structural-nav/structural-nav-caching-site-coll.png)

Para habilitar no nível do site, em **Site Settings**  >  **navegação**de configurações do site, marque a caixa para **habilitar o cache**.

![Habilitar o cache no nível do site](../media/structural-nav/structural-nav-caching-site.png)

## <a name="using-managed-navigation-and-metadata-in-sharepoint-online"></a>Usando a navegação gerenciada e metadados no SharePoint Online

A navegação gerenciada é outra opção pronta para uso, que você pode usar para recriar a maior parte da mesma funcionalidade que a navegação estrutural. Os metadados gerenciados podem ser configurados para que o aparamento de segurança seja habilitado ou desabilitado. Quando configurado com o aparamento de segurança desabilitado, a navegação gerenciada é bastante eficiente, pois carrega todos os links de navegação com um número constante de chamadas do servidor. No entanto, a habilitação da filtragem de segurança elimina algumas das vantagens de desempenho da navegação gerenciada.

Se você precisar habilitar a filtragem de segurança, recomendamos que você:

- Atualizar todos os links de URL amigáveis para links simples
- Adicionar nós de filtragem de segurança necessários como URLs amigáveis
- Limitar o número de itens de navegação para não mais do que 100 e não mais de três níveis de profundidade

Muitos sites não exigem filtragem de segurança, já que a estrutura de navegação é geralmente consistente para todos os usuários do site. Se a filtragem de segurança estiver desabilitada e um link for adicionado à navegação à qual nem todos os usuários tenham acesso, o link ainda será mostrado, mas levará a uma mensagem de acesso negado. Não há risco de acesso inadvertido ao conteúdo.

### <a name="how-to-implement-managed-navigation-and-the-results"></a>Como implementar a navegação gerenciada e os resultados

Há vários artigos no docs.microsoft.com sobre os detalhes da navegação gerenciada. Por exemplo, confira [visão geral da navegação gerenciada no SharePoint Server](https://docs.microsoft.com/sharepoint/administration/overview-of-managed-navigation).

Para implementar a navegação gerenciada, você configura termos com URLs correspondentes à estrutura de navegação do site. A navegação gerenciada pode até ser organizada manualmente para substituir a navegação estrutural em muitos casos. Por exemplo:

![Estrutura do site do SharePoint Online](../media/SPONavOptionsListOfSites.png))

## <a name="using-search-driven-client-side-scripting"></a>Usando scripts do lado do cliente orientados por pesquisa

Uma classe comum de implementações de navegação personalizadas engloba padrões de design renderizados pelo cliente que armazenam um cache local de nós de navegação.

Esses provedores de navegação têm algumas vantagens importantes:

- Em geral, eles funcionam bem com designs de página responsivos.
- Eles são extremamente escalonáveis e de desempenho porque podem renderizar sem custo de recurso (e atualizar em segundo plano após um tempo limite).
- Esses provedores de navegação podem recuperar dados de navegação usando várias estratégias, variando de configurações estáticas simples para vários provedores de dados dinâmicos.

Um exemplo de um provedor de dados é usar uma **navegação orientada por pesquisa**, o que permite flexibilidade para enumerar nós de navegação e manipular a filtragem de segurança com eficiência.

Há outras opções populares para criar **provedores de navegação personalizados**. Revise as [soluções de navegação para portais do SharePoint Online](https://docs.microsoft.com/sharepoint/dev/solution-guidance/portal-navigation) para obter mais orientações sobre a criação de um provedor de navegação personalizado.

Usando a pesquisa você pode aproveitar os índices criados em segundo plano usando o rastreamento contínuo. Os resultados da pesquisa são extraídos do índice de pesquisa e os resultados são cortados de segurança. Isso é geralmente mais rápido do que os provedores de navegação prontos quando o aparamento de segurança é necessário. Usando a pesquisa para navegação estrutural, especialmente se você tiver uma estrutura de site complexa, acelerará consideravelmente o tempo de carregamento da página. A principal vantagem disso sobre a navegação gerenciada é que você se beneficia da filtragem de segurança.

Essa abordagem envolve a criação de uma página mestra personalizada e a substituição do código de navegação pronto com HTML personalizado. Siga este procedimento descrito no exemplo a seguir para substituir o código de navegação no arquivo `seattle.html` . Neste exemplo, você abrirá o `seattle.html` arquivo e substituirá o elemento inteiro `id="DeltaTopNavigation"` pelo código HTML personalizado.

### <a name="example-replace-the-out-of-the-box-navigation-code-in-a-master-page"></a>Exemplo: substituir o código de navegação pronto em uma página mestra

1. Navegue até a página Configurações do site.
2. Abra a Galeria de páginas mestras clicando em **páginas mestras**.
3. Aqui você pode navegar pela biblioteca e baixar o arquivo `seattle.master` .
4. Edite o código usando um editor de texto e exclua o bloco de código na captura de tela a seguir.<br/>![Excluir o bloco de código mostrado](../media/SPONavOptionsDeleteCodeBlock.png)<br/>
5. Remova o código entre as `<SharePoint:AjaxDelta id="DeltaTopNavigation">` `<\SharePoint:AjaxDelta>` marcas e e substitua-o pelo seguinte trecho:<br/>

```javascript
<div id="loading">
  <!--Replace with path to loading image.-->
  <div style="background-image: url(''); height: 22px; width: 22px; ">
  </div>
</div>
<!-- Main Content-->
<div id="navContainer" style="display:none">
    <div data-bind="foreach: hierarchy" class="noindex ms-core-listMenu-horizontalBox">
        <a class="dynamic menu-item ms-core-listMenu-item ms-displayInline ms-navedit-linkNode" data-bind="attr: { href: item.Url, title: item.Title }">
            <span class="menu-item-text" data-bind="text: item.Title">
            </span>
        </a>
        <ul id="menu" data-bind="foreach: $data.children" style="padding-left:20px">
            <li class="static dynamic-children level1">
                <a class="static dynamic-children menu-item ms-core-listMenu-item ms-displayInline ms-navedit-linkNode" data-bind="attr: { href: item.Url, title: item.Title }">

                 <!-- ko if: children.length > 0-->
                    <span aria-haspopup="true" class="additional-background ms-navedit-flyoutArrow dynamic-children">
                        <span class="menu-item-text" data-bind="text: item.Title">
                        </span>
                    </span>
                <!-- /ko -->
                <!-- ko if: children.length == 0-->
                    <span aria-haspopup="true" class="ms-navedit-flyoutArrow dynamic-children">
                        <span class="menu-item-text" data-bind="text: item.Title">
                        </span>
                    </span>
                <!-- /ko -->
                </a>

                <!-- ko if: children.length > 0-->
                <ul id="menu"  data-bind="foreach: children;" class="dynamic  level2" >
                    <li class="dynamic level2">
                        <a class="dynamic menu-item ms-core-listMenu-item ms-displayInline  ms-navedit-linkNode" data-bind="attr: { href: item.Url, title: item.Title }">

          <!-- ko if: children.length > 0-->
          <span aria-haspopup="true" class="additional-background ms-navedit-flyoutArrow dynamic-children">
           <span class="menu-item-text" data-bind="text: item.Title">
           </span>
          </span>
           <!-- /ko -->
          <!-- ko if: children.length == 0-->
          <span aria-haspopup="true" class="ms-navedit-flyoutArrow dynamic-children">
           <span class="menu-item-text" data-bind="text: item.Title">
           </span>
          </span>
          <!-- /ko -->
                        </a>
          <!-- ko if: children.length > 0-->
         <ul id="menu" data-bind="foreach: children;" class="dynamic level3" >
          <li class="dynamic level3">
           <a class="dynamic menu-item ms-core-listMenu-item ms-displayInline ms-navedit-linkNode" data-bind="attr: { href: item.Url, title: item.Title }">
            <span class="menu-item-text" data-bind="text: item.Title">
            </span>
           </a>
          </li>
         </ul>
           <!-- /ko -->
                    </li>
                </ul>
                <!-- /ko -->
            </li>
        </ul>
    </div>
</div>
```

<br/>
6. Substitua a URL na marca de âncora carregar imagem no início, com um link para uma imagem de carregamento no seu conjunto de sites. Depois de fazer as alterações, renomeie o arquivo e carregue-o na Galeria de páginas mestras. Isso gera um novo arquivo. master.<br/>
7. Este HTML é a marcação básica que será preenchida pelos resultados da pesquisa retornados do código JavaScript. Você precisará editar o código para alterar o valor de var root = "URL do conjunto de sites", conforme demonstrado no seguinte trecho de código:<br/>

```javascript
var root = "https://spperformance.sharepoint.com/sites/NavigationBySearch";
```

<br/>
8. Os resultados são atribuídos à matriz Self. Nodes e uma hierarquia é criada a partir dos objetos usando linq.js atribuindo a saída a uma hierarquia de matriz própria. Esta matriz é o objeto que está vinculado ao HTML. Isso é feito na função toggleView (), passando o autoobjeto para a função ko. applybinding ().<br/>Isso faz com que a matriz de hierarquia seja vinculada ao seguinte HTML:<br/>

```javascript
<div data-bind="foreach: hierarchy" class="noindex ms-core-listMenu-horizontalBox">
```

Os manipuladores de eventos para `mouseenter` e `mouseexit` são adicionados à navegação de nível superior para lidar com os menus suspensos de subsites que é feito na `addEventsToElements()` função.

No nosso exemplo de navegação complexa, uma nova carga de página sem o cache local mostra que o tempo gasto no servidor foi reduzido da navegação estrutural de benchmark para obter um resultado semelhante à abordagem de navegação gerenciada.

### <a name="about-the-javascript-file"></a>Sobre o arquivo JavaScript...

>[!NOTE]
>Se estiver usando JavaScript personalizado, verifique se a CDN pública está habilitada e se o arquivo está em um local de CDN.

O arquivo JavaScript inteiro é o seguinte:

```javascript
//Models and Namespaces
var SPOCustom = SPOCustom || {};
SPOCustom.Models = SPOCustom.Models || {}
SPOCustom.Models.NavigationNode = function () {

    this.Url = ko.observable("");
    this.Title = ko.observable("");
    this.Parent = ko.observable("");

};

var root = "https://spperformance.sharepoint.com/sites/NavigationBySearch";
var baseUrl = root + "/_api/search/query?querytext=";
var query = baseUrl + "'contentClass=\"STS_Web\"+path:" + root + "'&trimduplicates=false&rowlimit=300";

var baseRequest = {
    url: "",
    type: ""
};


//Parses a local object from JSON search result.
function getNavigationFromDto(dto) {
    var item = new SPOCustom.Models.NavigationNode();
    if (dto != undefined) {

        var webTemplate = getSearchResultsValue(dto.Cells.results, 'WebTemplate');

        if (webTemplate != "APP") {
            item.Title(getSearchResultsValue(dto.Cells.results, 'Title')); //Key = Title
            item.Url(getSearchResultsValue(dto.Cells.results, 'Path')); //Key = Path
            item.Parent(getSearchResultsValue(dto.Cells.results, 'ParentLink')); //Key = ParentLink
        }

    }
    return item;
}

function getSearchResultsValue(results, key) {

    for (i = 0; i < results.length; i++) {
        if (results[i].Key == key) {
            return results[i].Value;
        }
    }
    return null;
}

//Parse a local object from the serialized cache.
function getNavigationFromCache(dto) {
    var item = new SPOCustom.Models.NavigationNode();

    if (dto != undefined) {

        item.Title(dto.Title);
        item.Url(dto.Url);
        item.Parent(dto.Parent);
    }

    return item;
}

/* create a new OData request for JSON response */
function getRequest(endpoint) {
    var request = baseRequest;
    request.type = "GET";
    request.url = endpoint;
    request.headers = { ACCEPT: "application/json;odata=verbose" };
    return request;
};

/* Navigation Module*/
function NavigationViewModel() {
    "use strict";
    var self = this;
    self.nodes = ko.observableArray([]);
    self.hierarchy = ko.observableArray([]);;
    self.loadNavigatioNodes = function () {
        //Check local storage for cached navigation datasource.
        var fromStorage = localStorage["nodesCache"];
        if (false) {
            var cachedNodes = JSON.parse(localStorage["nodesCache"]);

            if (cachedNodes && timeStamp) {
                //Check for cache expiration. Currently set to 3 hrs.
                var now = new Date();
                var diff = now.getTime() - timeStamp;
                if (Math.round(diff / (1000 * 60 * 60)) < 3) {

                    //return from cache.
                    var cacheResults = [];
                    $.each(cachedNodes, function (i, item) {
                        var nodeitem = getNavigationFromCache(item, true);
                        cacheResults.push(nodeitem);
                    });

                    self.buildHierarchy(cacheResults);
                    self.toggleView();
                    addEventsToElements();
                    return;
                }
            }
        }
        //No cache hit, REST call required.
        self.queryRemoteInterface();
    };

    //Executes a REST call and builds the navigation hierarchy.
    self.queryRemoteInterface = function () {
        var oDataRequest = getRequest(query);
        $.ajax(oDataRequest).done(function (data) {
            var results = [];
            $.each(data.d.query.PrimaryQueryResult.RelevantResults.Table.Rows.results, function (i, item) {

                if (i == 0) {
                    //Add root element.
                    var rootItem = new SPOCustom.Models.NavigationNode();
                    rootItem.Title("Root");
                    rootItem.Url(root);
                    rootItem.Parent(null);
                    results.push(rootItem);
                }
                var navItem = getNavigationFromDto(item);
                results.push(navItem);
            });
            //Add to local cache
            localStorage["nodesCache"] = ko.toJSON(results);

            localStorage["nodesCachedAt"] = new Date().getTime();
            self.nodes(results);
            if (self.nodes().length > 0) {
                var unsortedArray = self.nodes();
                var sortedArray = unsortedArray.sort(self.sortObjectsInArray);

                self.buildHierarchy(sortedArray);
                self.toggleView();
                addEventsToElements();
            }
        }).fail(function () {
            //Handle error here!!
            $("#loading").hide();
            $("#error").show();
        });
    };
    self.toggleView = function () {
        var navContainer = document.getElementById("navContainer");
        ko.applyBindings(self, navContainer);
        $("#loading").hide();
        $("#navContainer").show();

    };
    //Uses linq.js to build the navigation tree.
    self.buildHierarchy = function (enumerable) {
        self.hierarchy(Enumerable.From(enumerable).ByHierarchy(function (d) {
            return d.Parent() == null;
        }, function (parent, child) {
            if (parent.Url() == null || child.Parent() == null)
                return false;
            return parent.Url().toUpperCase() == child.Parent().toUpperCase();
        }).ToArray());

        self.sortChildren(self.hierarchy()[0]);
    };


    self.sortChildren = function (parent) {

        // sjip processing if no children
        if (!parent || !parent.children || parent.children.length === 0) {
            return;
        }

        parent.children = parent.children.sort(self.sortObjectsInArray2);

        for (var i = 0; i < parent.children.length; i++) {
            var elem = parent.children[i];

            if (elem.children && elem.children.length > 0) {
                self.sortChildren(elem);
            }
        }
    };

    // ByHierarchy method breaks the sorting in chrome and firefox
    // we need to resort  as ascending
    self.sortObjectsInArray2 = function (a, b) {
        if (a.item.Title() > b.item.Title())
            return 1;
        if (a.item.Title() < b.item.Title())
            return -1;
        return 0;
    };


    self.sortObjectsInArray = function (a, b) {
        if (a.Title() > b.Title())
            return -1;
        if (a.Title() < b.Title())
            return 1;
        return 0;
    }
}

//Loads the navigation on load and binds the event handlers for mouse interaction.
function InitCustomNav() {
    var viewModel = new NavigationViewModel();
    viewModel.loadNavigatioNodes();
}

function addEventsToElements() {
    //events.
      $("li.level1").mouseover(function () {
          var position = $(this).position();
          $(this).find("ul.level2").css({ width: 100, left: position.left + 10, top: 50 });
      })
   .mouseout(function () {
     $(this).find("ul.level2").css({  left: -99999, top: 0 });
   
    });
   
     $("li.level2").mouseover(function () {
          var position = $(this).position();
          console.log(JSON.stringify(position));
          $(this).find("ul.level3").css({ width: 100, left: position.left + 95, top:  position.top});
      })
   .mouseout(function () {
     $(this).find("ul.level3").css({  left: -99999, top: 0 });
    });
} _spBodyOnLoadFunctionNames.push("InitCustomNav");

```

Para resumir o código mostrado acima na `jQuery $(document).ready` função, há uma `viewModel object` criada e, em seguida, a `loadNavigationNodes()` função desse objeto é chamada. Essa função carrega a hierarquia de navegação criada anteriormente armazenada no armazenamento local do HTML5 do navegador cliente ou chama a função `queryRemoteInterface()` .

`QueryRemoteInterface()` Cria uma solicitação usando a `getRequest()` função com o parâmetro de consulta definido anteriormente no script e, em seguida, retorna dados do servidor. Esses dados são essencialmente uma matriz de todos os sites no conjunto de sites representados como objetos de transferência de dados com várias propriedades.

Esses dados são analisados nos objetos previamente definidos `SPO.Models.NavigationNode` que usam `Knockout.js` para criar propriedades observáveis para uso por dados associando os valores no HTML que definimos anteriormente.

Os objetos são então colocados em uma matriz de resultados. Essa matriz é analisada no JSON usando vazar e armazenada no armazenamento de navegador local para melhorar o desempenho em cargas de página futuras.

### <a name="benefits-of-this-approach"></a>Benefícios dessa abordagem

Uma das principais vantagens dessa [abordagem](#example-replace-the-out-of-the-box-navigation-code-in-a-master-page) é que, usando o armazenamento local do HTML5, a navegação é armazenada localmente para o usuário na próxima vez que ele carregar a página. Obtemos grandes aprimoramentos de desempenho ao usar a API de pesquisa para navegação estrutural; no entanto, ele leva algum recurso técnico para executar e personalizar essa funcionalidade.

Na [implementação de exemplo](#example-replace-the-out-of-the-box-navigation-code-in-a-master-page), os sites são classificados da mesma maneira que a navegação estrutural pronta para uso; ordem alfabética. Se você quisesse se desviar dessa ordem, seria mais complicado desenvolver e manter. Além disso, essa abordagem exige que você se desvie das páginas mestras com suporte. Se a página mestra personalizada não for mantida, seu site perderá as atualizações e melhorias que a Microsoft faz nas páginas mestras.

O [código acima](#about-the-javascript-file) tem as seguintes dependências:

- jQuery https://jquery.com/
- KnockoutJS - https://knockoutjs.com/
- Linq.js- https://linqjs.codeplex.com/ ou github.com/neuecc/linq.js

A versão atual do LinqJS não contém o método ByHierarchy usado no código acima e quebrará o código de navegação. Para corrigir isso, adicione o seguinte método ao arquivo de Linq.js antes da linha `Flatten: function ()` .

```javascript
ByHierarchy: function(firstLevel, connectBy, orderBy, ascending, parent) {
     ascending = ascending == undefined ? true : ascending;
     var orderMethod = ascending == true ? 'OrderBy' : 'OrderByDescending';
     var source = this;
     firstLevel = Utils.CreateLambda(firstLevel);
     connectBy = Utils.CreateLambda(connectBy);
     orderBy = Utils.CreateLambda(orderBy);

     //Initiate or increase level
     var level = parent === undefined ? 1 : parent.level + 1;

    return new Enumerable(function() {
         var enumerator;
         var index = 0;

        var createLevel = function() {
                 var obj = {
                     item: enumerator.Current(),
                     level : level
                 };
                 obj.children = Enumerable.From(source).ByHierarchy(firstLevel, connectBy, orderBy, ascending, obj);
                 if (orderBy !== undefined) {
                     obj.children = obj.children[orderMethod](function(d) {
                         return orderBy(d.item); //unwrap the actual item for sort to work
                     });
                 }
                 obj.children = obj.children.ToArray();
                 Enumerable.From(obj.children).ForEach(function(child) {
                     child.getParent = function() {
                         return obj;
                     };
                 });
                 return obj;
             };

        return new IEnumerator(

        function() {
             enumerator = source.GetEnumerator();
         }, function() {
             while (enumerator.MoveNext()) {
                 var returnArr;
                 if (!parent) {
                     if (firstLevel(enumerator.Current(), index++)) {
                         return this.Yield(createLevel());
                     }

                } else {
                     if (connectBy(parent.item, enumerator.Current(), index++)) {
                         return this.Yield(createLevel());
                     }
                 }
             }
             return false;
         }, function() {
             Utils.Dispose(enumerator);
         })
     });
 },

```
  
## <a name="related-topics"></a>Tópicos relacionados

[Visão geral da navegação gerenciada no SharePoint Server](https://docs.microsoft.com/sharepoint/administration/overview-of-managed-navigation)

[Desempenho e cache de navegação estrutural](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43)
