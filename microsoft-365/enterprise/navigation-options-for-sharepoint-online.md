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
description: Este artigo descreve sites de opções de navegação com a Publicação do SharePoint habilitada no SharePoint Online.
ms.openlocfilehash: b5989bf26ebf7bb1452f983af89a6e6739821d53
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923619"
---
# <a name="navigation-options-for-sharepoint-online"></a>Opções de navegação para o SharePoint Online

Este artigo descreve sites de opções de navegação com a Publicação do SharePoint habilitada no SharePoint Online. A escolha e a configuração da navegação impactam significativamente o desempenho e a escalabilidade dos sites no SharePoint Online. O modelo de site de Publicação do SharePoint só deve ser usado se necessário para um portal centralizado e o recurso de publicação só deve ser habilitado em sites específicos e somente quando absolutamente necessário, pois pode afetar o desempenho quando usado incorretamente.

>[!NOTE]
>Se você estiver usando opções de navegação modernas do SharePoint, como mega menu, navegação em cascata ou navegação de hub, este artigo não se aplica ao seu site. As arquiteturas de site modernas do SharePoint aproveitam uma hierarquia de sites mais achatada e um modelo de hub-and-spoke. Isso permite que muitos cenários sejam atingidos que NÃO exigem o uso do recurso de Publicação do SharePoint.

## <a name="overview-of-navigation-options"></a>Visão geral das opções de navegação

A configuração do provedor de navegação pode afetar significativamente o desempenho de todo o site, e deve ser tomada uma consideração cuidadosa para escolher um provedor de navegação e uma configuração que seja dimensionada efetivamente para os requisitos de um site do SharePoint. Há dois provedores de navegação in-locar, bem como implementações de navegação personalizadas.

A primeira opção, [**Navegação**](#using-structural-navigation-in-sharepoint-online)estrutural , é a opção de navegação recomendada no SharePoint Online para sites clássicos do Sharepoint, se você ativar o cache de navegação estrutural **para seu site**. Este provedor de navegação exibe os itens de navegação abaixo do site atual e, opcionalmente, o site atual e seus irmãos. Ele fornece recursos adicionais, como corte de segurança e enumeração de estrutura de site. Se o cache estiver desabilitado, isso afetará negativamente o desempenho e a escalabilidade e poderá estar sujeito à avaliação.

A segunda opção, [**navegação Gerenciada (Metadados),**](#using-managed-navigation-and-metadata-in-sharepoint-online)representa itens de navegação usando um conjunto de termos de Metadados Gerenciados. Recomendamos que a recortação de segurança seja desabilitada, a menos que seja necessário. A aparação de segurança está habilitada como uma configuração segura por padrão para este provedor de navegação; no entanto, muitos sites não exigem a sobrecarga de corte de segurança, pois os elementos de navegação geralmente são consistentes para todos os usuários do site. Com a configuração recomendada para desabilitar o corte de segurança, esse provedor de navegação não exige a enumeração da estrutura do site e é altamente escalonável com impacto de desempenho aceitável.

Além dos provedores de navegação fora da caixa, muitos clientes implementaram implementações de navegação personalizada alternativa com êxito. Consulte [Scripts do lado do](#using-search-driven-client-side-scripting) cliente orientados pela pesquisa neste artigo.
  
## <a name="pros-and-cons-of-sharepoint-online-navigation-options"></a>Prós e contras das opções de navegação do SharePoint Online

A tabela a seguir resume os prós e contras de cada opção.

|Navegação estrutural  |Navegação gerenciada  |Navegação orientada por pesquisa  |Provedor de navegação personalizada  |
|---------|---------|---------|---------|
|Pros:<br/><br/>Fácil de manter<br/>Segurança cortada<br/>Atualiza automaticamente dentro de 24 horas quando o conteúdo é alterado<br/>     |Pros:<br/><br/>Fácil de manter<br/>|Pros:<br/><br/>Segurança cortada<br/>Atualizações automáticas à medida que os sites são adicionados<br/>Tempo de carregamento rápido e estrutura de navegação em cache local<br/>|Pros:<br/><br/>Escolha mais ampla das opções disponíveis<br/>Carregamento rápido quando o cache é usado corretamente<br/>Muitas opções funcionam bem com o design de página responsivo<br/>|
|Cons:<br/><br/>**Afeta o desempenho se o cache estiver desabilitado**<br/>Sujeito à throttling<br/>|Cons:<br/><br/>Não atualizado automaticamente para refletir a estrutura do site<br/>**Impacta o desempenho se a recortação de segurança estiver habilitada** ou quando a estrutura de navegação for complexa<br/>|Cons:<br/><br/>Nenhuma capacidade de solicitar facilmente sites<br/>Requer personalização da página mestra (habilidades técnicas necessárias)<br/>|Cons:<br/><br/>O desenvolvimento personalizado é necessário<br/>A fonte de dados externa/ o cache armazenado é necessário, por exemplo, o Azure<br/>|

A opção mais apropriada para seu site dependerá dos requisitos de seu site e de sua capacidade técnica. Se você quiser um provedor de navegação fácil de configurar que atualiza automaticamente quando o conteúdo é alterado, a navegação estrutural com [o cache](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43) habilitado é uma boa opção.

>[!NOTE]
>Aplicar o mesmo princípio dos sites modernos do SharePoint simplificando a estrutura geral do site para uma estrutura simples e não hierárquica melhora o desempenho e simplifica a movimentação para sites modernos do SharePoint. Isso significa que, em vez de ter um único conjunto de sites com centenas de sites (subwebs), uma abordagem melhor é ter muitos conjunto de sites com muito poucos subsites (subwebs).

## <a name="analyzing-navigation-performance-in-sharepoint-online"></a>Analisando o desempenho da navegação no SharePoint Online

A ferramenta Diagnóstico de Página para [SharePoint](./page-diagnostics-for-spo.md) é uma extensão do navegador para navegadores do Microsoft Edge e do Chrome que analisa o portal moderno do SharePoint Online e páginas de site de publicação clássicas. Essa ferramenta só funciona para o SharePoint Online e não pode ser usada em uma página do sistema do SharePoint.

A ferramenta gera um relatório para cada página analisada mostrando como a página se executa em relação a um conjunto de regras pré-definido e exibe informações detalhadas quando os resultados de um teste estão fora do valor da linha de base. Os administradores e designers do SharePoint Online podem usar a ferramenta para solucionar problemas de desempenho para garantir que novas páginas sejam otimizadas antes da publicação.

**SPRequestDuration** em particular é o tempo necessário para o SharePoint processar a página. A navegação intensa (como incluir páginas na navegação), hierarquias de site complexas e outras opções de configuração e topologia podem contribuir drasticamente para durações mais longas.

## <a name="using-structural-navigation-in-sharepoint-online"></a>Usando a navegação estrutural no SharePoint Online

Essa é a navegação completa usada por padrão e é a solução mais simples. Ele não exige nenhuma personalização e um usuário não técnico também pode facilmente adicionar itens, ocultar itens e gerenciar a navegação na página de configurações. Recomendamos [habilenciar o cache,](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43)caso contrário, há uma troca de desempenho cara.

### <a name="how-to-implement-structural-navigation-caching"></a>Como implementar o cache de navegação estrutural

Em **Configurações do Site,** procure e sinta navegação , você pode validar se a navegação estrutural estiver selecionada para navegação  >    >  global ou navegação atual. Selecionar **Mostrar páginas** terá impacto negativo no desempenho.

![Navegação estrutural com Mostrar Subsites selecionados](../media/SPONavOptionsStructuredShowSubsites.png)

O cache pode ser habilitado ou desabilitado no nível do conjunto de sites e no nível do site e está habilitado para ambos por padrão. Para habilitar no nível do conjunto de sites, em **Configurações** do Site Administração do Conjunto de Sites Navegação do Conjunto de Sites , marque a caixa  >    >   **para Habilitar cache**.

![Habilitar o cache no nível do site](../media/structural-nav/structural-nav-caching-site-coll.png)

Para habilitar no nível do site, em Navegação de Configurações **do Site,** marque a  >  caixa **Habilitar cache**.

![Habilitar o cache no nível do site](../media/structural-nav/structural-nav-caching-site.png)

## <a name="using-managed-navigation-and-metadata-in-sharepoint-online"></a>Usando navegação gerenciada e metadados no SharePoint Online

A navegação gerenciada é outra opção que você pode usar para recriar a maior parte da mesma funcionalidade que a navegação estrutural. Os metadados gerenciados podem ser configurados para que a recortação de segurança seja habilitada ou desabilitada. Quando configurada com a recortação de segurança desabilitada, a navegação gerenciada é bastante eficiente, pois carrega todos os links de navegação com um número constante de chamadas de servidor. A habilitação da recortação de segurança, no entanto, nega algumas das vantagens de desempenho da navegação gerenciada.

Se você precisar habilitar o corte de segurança, recomendamos que você:

- Atualizar todos os links de URL amigáveis para links simples
- Adicionar nós de corte de segurança necessários como URLs amigáveis
- Limitar o número de itens de navegação a no máximo 100 e não mais de 3 níveis de profundidade

Muitos sites não exigem aparação de segurança, pois a estrutura de navegação geralmente é consistente para todos os usuários do site. Se a recortação de segurança estiver desabilitada e um link for adicionado à navegação à que nem todos os usuários têm acesso, o link ainda será show, mas levará a uma mensagem de acesso negado. Não há risco de acesso inadvertido ao conteúdo.

### <a name="how-to-implement-managed-navigation-and-the-results"></a>Como implementar a navegação gerenciada e os resultados

Há vários artigos sobre o docs.microsoft.com sobre os detalhes da navegação gerenciada. Por exemplo, consulte [Visão geral da navegação gerenciada no SharePoint Server](/sharepoint/administration/overview-of-managed-navigation).

Para implementar a navegação gerenciada, você configura os termos com URLs correspondentes à estrutura de navegação do site. A navegação gerenciada pode até ser feita manualmente para substituir a navegação estrutural em muitos casos. Por exemplo:

![Estrutura de site do SharePoint Online](../media/SPONavOptionsListOfSites.png))

## <a name="using-search-driven-client-side-scripting"></a>Usando scripts do lado do cliente orientados pela pesquisa

Uma classe comum de implementações de navegação personalizadas abrange padrões de design renderizados pelo cliente que armazenam um cache local de nós de navegação.

Esses provedores de navegação têm algumas vantagens principais:

- Eles geralmente funcionam bem com designs de página responsivos.
- Eles são extremamente escalonáveis e performáveis porque podem renderizar sem custo de recurso (e atualizar em segundo plano após um tempo de execução).
- Esses provedores de navegação podem recuperar dados de navegação usando várias estratégias, desde configurações estáticas simples a vários provedores dinâmicos de dados.

Um exemplo de um provedor de dados é usar uma navegação orientada por pesquisa **,** o que permite a flexibilidade para enumerar nós de navegação e manipular a recortação de segurança com eficiência.

Há outras opções populares para criar **provedores de navegação personalizados.** Confira [soluções de navegação para portais do SharePoint Online](/sharepoint/dev/solution-guidance/portal-navigation) para obter mais orientações sobre como criar um provedor de navegação personalizado.

Usando a pesquisa, você pode aproveitar os índices que são construídos em segundo plano usando rastreamento contínuo. Os resultados da pesquisa são retirados do índice de pesquisa e os resultados são aparados com segurança. Isso geralmente é mais rápido do que os provedores de navegação in-locar quando a recortação de segurança é necessária. O uso da pesquisa de navegação estrutural, especialmente se você tiver uma estrutura de site complexa, acelerará consideravelmente o tempo de carregamento da página. A principal vantagem disso em relação à navegação gerenciada é que você se beneficia da aparação de segurança.

Essa abordagem envolve a criação de uma página mestra personalizada e a substituição do código de navegação fora da caixa por HTML personalizado. Siga este procedimento descrito no exemplo a seguir para substituir o código de navegação no arquivo `seattle.html` . Neste exemplo, você abrirá o arquivo `seattle.html` e substituirá todo o elemento `id="DeltaTopNavigation"` pelo código HTML personalizado.

### <a name="example-replace-the-out-of-the-box-navigation-code-in-a-master-page"></a>Exemplo: Substitua o código de navegação fora da caixa em uma página mestra

1. Navegue até a página Configurações do Site.
2. Abra a galeria de páginas mestras clicando em **Páginas Mestras.**
3. A partir daqui, você pode navegar pela biblioteca e baixar o arquivo `seattle.master` .
4. Edite o código usando um editor de texto e exclua o bloco de código na captura de tela a seguir.<br/>![Excluir o bloco de código mostrado](../media/SPONavOptionsDeleteCodeBlock.png)<br/>
5. Remova o código entre as `<SharePoint:AjaxDelta id="DeltaTopNavigation">` marcas `<\SharePoint:AjaxDelta>` e e substitua-o pelo seguinte trecho:<br/>

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
6. Substitua a URL na marca de âncora de imagem de carregamento no início, por um link para uma imagem de carregamento em seu conjunto de sites. Depois de fazer as alterações, renomeie o arquivo e carregue-o na galeria de páginas mestras. Isso gera um novo arquivo .master.<br/>
7. Este HTML é a marcação básica que será preenchida pelos resultados da pesquisa retornados do código JavaScript. Você precisará editar o código para alterar o valor da raiz var = "URL do conjunto de sites", conforme demonstrado no seguinte trecho:<br/>

```javascript
var root = "https://spperformance.sharepoint.com/sites/NavigationBySearch";
```

<br/>
8. Os resultados são atribuídos à matriz self.nodes e uma hierarquia é criada a partir dos objetos usando linq.js atribuir a saída a uma matriz self.hierarchy. Essa matriz é o objeto que está vinculado ao HTML. Isso é feito na função toggleView() passando o auto-objeto para a função ko.applyBinding().<br/>Isso faz com que a matriz de hierarquia seja vinculada ao seguinte HTML:<br/>

```javascript
<div data-bind="foreach: hierarchy" class="noindex ms-core-listMenu-horizontalBox">
```

Os manipuladores de eventos para e são adicionados à navegação de nível superior para manipular os menus suspensos de subsite que são `mouseenter` feitos na `mouseexit` `addEventsToElements()` função.

Em nosso exemplo de navegação complexo, uma nova carga de página sem o cache local mostra que o tempo gasto no servidor foi cortado da navegação estrutural de referência para obter um resultado semelhante ao da abordagem de navegação gerenciada.

### <a name="about-the-javascript-file"></a>Sobre o arquivo JavaScript...

>[!NOTE]
>Se estiver usando JavaScript personalizado, verifique se a CDN pública está habilitada e se o arquivo está em um local de CDN.

Todo o arquivo JavaScript é o seguinte:

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

Para resumir o código mostrado acima na `jQuery $(document).ready` função, há um criado e, em seguida, a `viewModel object` função nesse objeto é `loadNavigationNodes()` chamada. Essa função carrega a hierarquia de navegação anteriormente criada armazenada no armazenamento local HTML5 do navegador cliente ou chama a função `queryRemoteInterface()` .

`QueryRemoteInterface()` cria uma solicitação usando a função com o parâmetro de consulta definido anteriormente no script e `getRequest()` retorna dados do servidor. Esses dados são essencialmente uma matriz de todos os sites no conjunto de sites representados como objetos de transferência de dados com várias propriedades.

Esses dados são analisados nos objetos definidos anteriormente que usam para criar propriedades observáveis para uso, vinculando os valores ao `SPO.Models.NavigationNode` `Knockout.js` HTML que definimos anteriormente.

Em seguida, os objetos são colocados em uma matriz de resultados. Essa matriz é analisado em JSON usando Knockout e armazenado no armazenamento do navegador local para melhorar o desempenho em futuras cargas de página.

### <a name="benefits-of-this-approach"></a>Benefícios dessa abordagem

Um dos principais benefícios [dessa](#example-replace-the-out-of-the-box-navigation-code-in-a-master-page) abordagem é que, usando o armazenamento local HTML5, a navegação é armazenada localmente para o usuário na próxima vez que carregar a página. Nós temos melhorias de desempenho principais do uso da API de pesquisa para navegação estrutural; no entanto, é necessário algum recurso técnico para executar e personalizar essa funcionalidade.

Na implementação [de exemplo,](#example-replace-the-out-of-the-box-navigation-code-in-a-master-page)os sites são ordenados da mesma forma que a navegação estrutural fora da caixa; ordem alfabética. Se você quisesse desviar dessa ordem, seria mais complicado desenvolver e manter. Além disso, essa abordagem exige que você se desvie das páginas mestras com suporte. Se a página mestra personalizada não for mantida, seu site não receberá atualizações e melhorias feitas pela Microsoft nas páginas mestras.

O [código acima](#about-the-javascript-file) tem as seguintes dependências:

- jQuery - https://jquery.com/
- KnockoutJS - https://knockoutjs.com/
- Linq.js - https://linqjs.codeplex.com/ ou github.com/neuecc/linq.js

A versão atual do LinqJS não contém o método ByHierarchy usado no código acima e quebrará o código de navegação. Para corrigir isso, adicione o método a seguir ao arquivo Linq.js antes da linha `Flatten: function ()` .

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

[Visão geral da navegação gerenciada no SharePoint Server](/sharepoint/administration/overview-of-managed-navigation)

[Cache e desempenho de navegação estrutural](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43)