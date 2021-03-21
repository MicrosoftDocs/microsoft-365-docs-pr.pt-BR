---
title: Usar a CdN (Rede de Distribuição de Conteúdo) do Office 365 com o SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 2/19/2020
audience: ITPro
ms.topic: article
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
- MET150
- SPO160
ms.assetid: bebb285f-1d54-4f79-90a5-94985afc6af8
description: Saiba como usar a CdN (Rede de Entrega de Conteúdo) do Office 365 para acelerar a entrega dos ativos do SharePoint Online.
ms.openlocfilehash: 6b740fc1429613627e0597dc6ecf2e150c015989
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924811"
---
# <a name="use-the-office-365-content-delivery-network-cdn-with-sharepoint-online"></a>Usar a Rede de Distribuição de Conteúdo (CDN) do Office 365 com o SharePoint Online

Você pode usar a Rede de Distribuição de Conteúdo (CDN) do Office 365 integrado para proporcionar melhor desempenho a suas páginas do SharePoint Online. A CDN do Office 365 melhora o desempenho ao armazenar em cache ativos estáticos mais próximos aos navegadores que os solicitaram, o que ajuda a acelerar downloads e reduzir a latência. Além disso, a CDN do Office 365 usa o [protocolo HTTP/2](https://en.wikipedia.org/wiki/HTTP/2) para compactação aprimorada e pipelinamento HTTP. O serviço de CDN do Office 365 faz parte da assinatura do SharePoint Online.

> [!NOTE]
> A CDN do Office 365 só está disponível para locatários na nuvem **produção** (em todo o mundo). Os locatários nas nuvens do Governo dos EUA, China e Alemanha atualmente não suportam a CDN do Office 365.

A CDN do Office 365 é composta por várias CDNs que permitem que você hospede ativos estáticos em vários locais ou _origens_ e sirva-os de redes globais de alta velocidade. Dependendo do tipo de conteúdo você quiser hospedar na CDN do Office 365, você pode adicionar origens **públicas**, origens **privadas** ou ambas. Confira [Escolher se cada origem deve ser pública](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate) ou privada para obter mais informações sobre a diferença entre origens públicas e privadas.

![Diagrama conceitual da CDN do Office 365](../media/O365-CDN/o365-cdn-flow-transparent.svg "Diagrama conceitual da CDN do Office 365")

Se você já estiver familiarizado com a maneira como as CDNs funcionam, você só precisa concluir algumas etapas para habilitar a CDN do Office 365 para seu locatário. Este tópico descreve como. Leia para obter informações sobre como começar a hospedar seus ativos estáticos.

> [!TIP]
> Há outras CDNs hospedadas pela Microsoft que podem ser usadas com o Office 365 para cenários de uso especializados, mas não são discutidas neste tópico porque elas estão fora do escopo da CDN do Office 365. Para obter mais informações, consulte [Outras CDNs da Microsoft](content-delivery-networks.md#other-microsoft-cdns).

 **Volte para [o planejamento de rede e ajuste de desempenho do Office 365](./network-planning-and-performance.md).**

## <a name="overview-of-working-with-the-office-365-cdn-in-sharepoint-online"></a>Visão geral do trabalho com a CDN do Office 365 no SharePoint Online

Para configurar a CDN do Office 365 para sua organização, siga estas etapas básicas:

+ [Planejar a implantação da CDN do Office 365](use-microsoft-365-cdn-with-spo.md#plan-for-deployment-of-the-office-365-cdn)

  + [Determine quais ativos estáticos você deseja hospedar na CDN](use-microsoft-365-cdn-with-spo.md#CDNAssets).
  + [Determine onde deseja armazenar seus ativos.](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets) Esse local pode ser um site, biblioteca ou pasta do SharePoint e é chamado de _origem._
  + [Escolha se cada origem deve ser pública ou privada.](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate) Você pode adicionar várias origens de tipos públicos e privados.

+ Configurar e configurar a CDN usando o PowerShell ou a CLI do SharePoint Online

  + [Configurar e configurar a CDN usando o Shell de Gerenciamento do SharePoint Online](use-microsoft-365-cdn-with-spo.md#CDNSetupinPShell)
  + [Configurar e configurar a CDN usando o PnP PowerShell](use-microsoft-365-cdn-with-spo.md#CDNSetupinPnPPosh)
  + [Configurar e configurar a CDN usando a CLI do Office 365](use-microsoft-365-cdn-with-spo.md#CDNSetupinCLI)

  Ao concluir esta etapa, você terá:

  + Habilitada a CDN para sua organização.
  + Adicionada suas origens, identificando cada origem como pública ou privada.

Depois de terminar a instalação, você poderá Gerenciar a CDN do [Office 365](use-microsoft-365-cdn-with-spo.md#CDNManage) ao longo do tempo:
  
+ Adicionar, atualizar e remover ativos
+ Adicionar e remover origens
+ Configurando políticas de CDN
+ Se necessário, desabilitar a CDN

Por fim, [consulte Usando seus ativos CDN](use-microsoft-365-cdn-with-spo.md#using-your-cdn-assets) para saber mais sobre como acessar seus ativos cdn de origens públicas e privadas.

Consulte [Solução de problemas da CDN do Office 365](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting) para obter orientações sobre como resolver problemas comuns.

## <a name="plan-for-deployment-of-the-office-365-cdn"></a>Planejar a implantação da CDN do Office 365

Antes de implantar a CDN do Office 365 para seu locatário do Office 365, considere os seguintes fatores como parte do seu processo de planejamento.

  + [Determinar quais ativos estáticos você deseja hospedar na CDN](use-microsoft-365-cdn-with-spo.md#CDNAssets)
  + [Determinar onde você deseja armazenar seus ativos](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets)
  + [Escolha se cada origem deve ser pública ou privada](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)

<a name="CDNAssets"> </a>
### <a name="determine-which-static-assets-you-want-to-host-on-the-cdn"></a>Determinar quais ativos estáticos você deseja hospedar na CDN

Em geral, as CDNs são mais eficazes para hospedar ativos _estáticos_ ou ativos que não mudam com muita frequência. Uma boa regra geral é identificar arquivos que atendem a algumas ou todas essas condições:

+ Arquivos estáticos inseridos em uma página (como scripts e imagens) que podem ter um impacto incremental significativo nos tempos de carregamento da página
+ Arquivos grandes, como executáveis e arquivos de instalação
+ Bibliotecas de recursos que suportam código do lado do cliente

Por exemplo, arquivos pequenos que são solicitados repetidamente, como imagens de site e scripts, podem melhorar significativamente o desempenho de renderização de site e reduzir incrementalmente a carga em seus sites do SharePoint Online quando você os adiciona a uma origem de CDN. Arquivos maiores, como executáveis de instalação, podem ser baixados da CDN, fornecendo um impacto positivo no desempenho e redução subsequente da carga em seu site do SharePoint Online, mesmo que eles não sejam acessados com a mesma frequência.

A melhoria de desempenho por arquivo depende de muitos fatores, incluindo a proximidade do cliente com o ponto de extremidade cdn mais próximo, condições transitórias na rede local e assim por diante. Muitos arquivos estáticos são muito pequenos e podem ser baixados do Office 365 em menos de um segundo. No entanto, uma página da Web pode conter muitos arquivos incorporados com um tempo de download cumulativo de vários segundos. Atender a esses arquivos da CDN pode reduzir significativamente o tempo de carregamento geral da página. Veja [Quais ganhos de desempenho uma CDN fornece?](content-delivery-networks.md#what-performance-gains-does-a-cdn-provide) para um exemplo.

<a name="CDNStoreAssets"> </a>
### <a name="determine-where-you-want-to-store-your-assets"></a>Determinar onde você deseja armazenar seus ativos

A CDN busca seus ativos de um local chamado de _origem_. Uma origem pode ser um site do SharePoint, uma biblioteca de documentos ou uma pasta acessível por uma URL. Você tem uma grande flexibilidade ao especificar origens para sua organização. Por exemplo, você pode especificar várias origens ou uma única origem onde deseja colocar todos os ativos cdn. Você pode optar por ter origens públicas ou privadas para sua organização. A maioria das organizações optará por implementar uma combinação dos dois.

Você pode criar um novo contêiner para suas origens, como pastas ou bibliotecas de documentos, e adicionar arquivos que deseja disponibilizar a partir da CDN. Essa é uma boa abordagem se você tiver um conjunto específico de ativos que deseja estar disponível na CDN e quiser restringir o conjunto de ativos CDN apenas para esses arquivos no contêiner.

Você também pode configurar um conjunto de sites, site, biblioteca ou pasta existente como uma origem, o que disponibiliza todos os ativos qualificados no contêiner da CDN. Antes de adicionar um contêiner existente como origem, é importante ter certeza de que está ciente de seu conteúdo e permissões para que você não exponha inadvertidamente os ativos a acesso anônimo ou usuários não autorizados.

Você pode definir _políticas de CDN_ para excluir conteúdo em suas origens da CDN. As políticas de CDN excluem ativos  em origens públicas ou privadas por atributos como tipo de arquivo e classificação de _site_ e são aplicadas a todas as origens do CdnType (privado ou público) especificado na política. Por exemplo, se você adicionar uma origem privada consistindo em um site que contenha  vários subsites, poderá definir uma política para excluir sites marcados como Confidencial para que o conteúdo de sites com essa classificação aplicada não seja atendido da CDN. A política se aplicará ao conteúdo de _todas as_ origens privadas adicionadas à CDN.
  
Lembre-se de que quanto maior o número de origens, maior será o impacto no tempo que o serviço CDN leva para processar solicitações. Recomendamos que você limite o número de origens o máximo possível.
  
<a name="CDNOriginChoosePublicPrivate"> </a>
### <a name="choose-whether-each-origin-should-be-public-or-private"></a>Escolha se cada origem deve ser pública ou privada

Ao identificar uma origem, especifique se ela deve ser _pública_ ou _privada._ O acesso aos ativos cdn em origens públicas é anônimo, e o conteúdo da CDN em origens privadas é protegido por tokens gerados dinamicamente para maior segurança. Independentemente de qual opção você escolher, a Microsoft faz todo o trabalho pesado para você quando se trata de administração da PRÓPRIA CDN. Além disso, você pode mudar de ideia mais tarde, depois de configurar a CDN e identificar suas origens.

As opções públicas e privadas oferecem ganhos de desempenho semelhantes, mas cada uma delas tem atributos e vantagens exclusivos.

**As** origens públicas na CDN do Office 365 são acessíveis anonimamente e os ativos hospedados podem ser acessados por qualquer pessoa que tenha a URL do ativo. Como o acesso ao conteúdo de origens públicas é anônimo, você só deve usá-lo para o armazenamento em cache de conteúdo genérico e não sensível como arquivos javascript, scripts, ícones e imagens.

**As** origens privadas na CDN do Office 365 fornecem acesso privado ao conteúdo do usuário, como bibliotecas de documentos do SharePoint Online, sites e imagens proprietárias. O acesso ao conteúdo em origens privadas é protegido por tokens gerados dinamicamente para que ele só possa ser acessado por usuários com permissões para a biblioteca de documentos original ou o local de armazenamento. As origens privadas na CDN do Office 365 só podem ser usadas para conteúdo do SharePoint Online e você só pode acessar ativos em origens privadas por meio do redirecionamento do locatário do SharePoint Online.

Você pode ler mais sobre como o acesso de CDN a ativos em uma origem privada funciona em [Usar ativos em origens privadas.](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins)

#### <a name="attributes-and-advantages-of-hosting-assets-in-public-origins"></a>Atributos e vantagens de hospedar ativos em origens públicas
  
+ Os ativos exibidos em uma origem pública são acessíveis por todos os usuários anonimamente.
    > [!IMPORTANT]
    > Você nunca deve colocar recursos que contenham informações do usuário ou sejam considerados confidenciais para sua organização em uma origem pública.
+ Se você remover um ativo de uma origem pública, ele pode seguir disponível em cache por até 30 dias; contudo, invalidaremos os links para o ativo na CDN em 15 minutos.
+ Quando você hospeda folhas de estilo (arquivos CSS) em uma origem pública, você pode usar os caminhos relativos e URIs dentro do código. Isso significa que você pode referenciar o local das imagens de fundo e outros objetos em relação ao local do ativo que faz a chamada.
+ Embora você possa construir uma URL de origem pública, você deve prosseguir com cautela e garantir que você utilize a propriedade de contexto de página e siga as diretrizes para fazer isso. O motivo é que se o acesso à CDN ficar indisponível, a URL não resolverá automaticamente para a sua organização no SharePoint Online e pode resultar em links quebrados e outros erros. A URL também está sujeita a alterações, razão pela qual ela não deve ser codificada apenas para seu valor atual.
+ Os tipos de arquivo padrão incluídos para origens públicas são .css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff e .woff2. Você pode especificar tipos de arquivo adicionais.
+ Você pode configurar uma política para excluir ativos que foram identificados pelas classificações de site que você especificar. Por exemplo, você pode optar por excluir todos os ativos marcados como "restrito" ou "confidencial", mesmo que sejam um tipo de arquivo permitido e estejam localizados em uma origem pública.

#### <a name="attributes-and-advantages-of-hosting-assets-in-private-origins"></a>Atributos e vantagens de hospedar ativos em origens privadas

+ As origens privadas só podem ser usadas para ativos do SharePoint Online.
+ Os usuários só poderão acessar os ativos de origem privada se eles têm permissões para acessar o contêiner. O acesso anônimo a esses ativos é vetado.
+ Os ativos de origem privada devem ser referenciados do locatário do SharePoint Online. O acesso direto a ativos CDN privados não funciona.
+ Se você remover um ativo da origem privada, o ativo poderá continuar disponível por até uma hora do cache; no entanto, invalidaremos links para o ativo na CDN dentro de 15 minutos após a remoção do ativo.
+ Os tipos de arquivo padrão incluídos para origens privadas são .gif, .ico, .jpeg, .jpg, .js e .png. Você pode especificar tipos de arquivo adicionais.
+ Assim como com origens públicas, você pode configurar uma política para excluir ativos que foram identificados por classificações de site que você especifica, mesmo que você use curingas para incluir todos os ativos em uma pasta ou biblioteca de documentos.

Para obter mais informações sobre por que usar a CDN do Office 365, os conceitos gerais da CDN e outras CDNs da Microsoft que você pode usar com seu locatário do Office 365, consulte [Redes](content-delivery-networks.md)de Entrega de Conteúdo.

### <a name="default-cdn-origins"></a>Origens padrão da CDN

A menos que você especifique o contrário, o Office 365 configura algumas origens padrão para você ao habilitar a CDN do Office 365. Se você optar inicialmente por não provisioná-las, poderá adicionar essas origens após concluir a instalação. A menos que você entenda as consequências de ignorar a configuração de origens padrão e ter um motivo específico para fazer isso, você deve permitir que eles sejam criados quando você habilitar a CDN.
  
Origens da CDN privada padrão:
  
+ \*/userphoto.aspx
+ \*/siteassets

Origens de CDN pública padrão:
  
+ \*/masterpage
+ \*/style library
+ \*/clientsideassets

> [!NOTE]
> _clientsideassets_ é uma origem pública padrão que foi adicionada ao serviço CDN do Office 365 em dezembro de 2017. Essa origem deve estar presente para que as soluções da Estrutura do SharePoint na CDN funcionem. Se você habilitar a CDN do Office 365 antes de dezembro de 2017 ou se você ignorou a configuração de origens padrão ao habilitar a CDN, poderá adicionar manualmente essa origem. Para obter mais informações, consulte [My client-side web part or SharePoint Framework solution isn't working](use-microsoft-365-cdn-with-spo.md#my-client-side-web-part-or-sharepoint-framework-solution-isnt-working).

<a name="CDNSetupinPShell"> </a>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell"></a>Configurar e configurar a CDN do Office 365 usando o Shell de Gerenciamento do SharePoint Online

Os procedimentos nesta seção exigem que você use o Shell de Gerenciamento do SharePoint Online para se conectar ao SharePoint Online. Para obter instruções, [consulte Connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).

Conclua estas etapas para configurar e configurar a CDN para hospedar seus ativos no SharePoint Online usando o Shell de Gerenciamento do SharePoint Online.

<details>
  <summary>Clique para expandir</summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a>Permitir que sua organização use a CDN do Office 365

Antes de fazer alterações nas configurações de CDN do locatário, você deve recuperar o status atual da configuração da CDN privada em seu locatário do Office 365. Conecte-se ao seu locatário usando o Shell de Gerenciamento do SharePoint Online:

``` powershell
Connect-SPOService -Url https://contoso-admin.sharepoint.com
```

Agora use o cmdlet **Get-SPOTenantCdnEnabled** para recuperar as configurações de status da CDN do locatário:

``` powershell
Get-SPOTenantCdnEnabled -CdnType <Public | Private>
```

O status da CDN do CdnType especificado será exibido na tela.

Use o cmdlet **Set-SPOTenantCdnEnabled** para permitir que sua organização use a CDN do Office 365. Você pode permitir que sua organização use origens públicas, origens privadas ou ambas ao mesmo tempo. Você também pode configurar a CDN para ignorar a configuração de origens padrão ao habilita-la. Você sempre pode adicionar essas origens mais tarde, conforme descrito neste tópico.
  
No Windows Powershell para SharePoint Online:

``` powershell
Set-SPOTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

Por exemplo, para permitir que sua organização use origens públicas e privadas, digite o seguinte comando:

``` powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true
```

Para permitir que sua organização use origens públicas e privadas, mas ignore a configuração das origens padrão, digite o seguinte comando:

``` powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

Consulte Origens de [CDN](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) padrão para obter informações sobre as origens provisionadas por padrão quando você habilita a CDN do Office 365 e o impacto potencial de ignorar a configuração de origens padrão.

Para permitir que sua organização use origens públicas, digite o seguinte comando:

``` powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $true
```

Para permitir que sua organização use origens privadas, digite o seguinte comando:

``` powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $true
```

Para obter mais informações sobre esse cmdlet, consulte [Set-SPOTenantCdnEnabled](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled).

<a name="Office365CDNforSPOFileType"> </a>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a>Alterar a lista de tipos de arquivo a incluir na CDN do Office 365 (Opcional)

> [!TIP]
> Ao definir tipos de arquivo usando o cmdlet **Set-SPOTenantCdnPolicy,** você substitui a lista definida no momento. Se você quiser adicionar tipos de arquivo adicionais à lista, use o cmdlet primeiro para descobrir quais tipos de arquivo já são permitidos e incluí-los na lista juntamente com os novos.
  
Use o cmdlet **Set-SPOTenantCdnPolicy** para definir tipos de arquivo estáticos que podem ser hospedados por origens públicas e privadas na CDN. Por padrão, os tipos de ativos comuns são permitidos, por exemplo .css, .gif, .jpg e .js.

Em Windows PowerShell para SharePoint Online:

``` powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

Por exemplo, para habilitar a CDN para hospedar arquivos .css e .png, você inseriria o comando:

``` powershell
Set-SPOTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

Para ver quais tipos de arquivo atualmente são permitidos pela CDN, use o cmdlet **Get-SPOTenantCdnPolicies:**

``` powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

Para obter mais informações sobre esses cmdlets, consulte [Set-SPOTenantCdnPolicy](/powershell/module/sharepoint-online/) e [Get-SPOTenantCdnPolicies](/powershell/module/sharepoint-online/).

<a name="Office365CDNforSPOSiteClassification"> </a>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a>Alterar a lista de classificações de site que você deseja excluir da CDN do Office 365 (Opcional)

> [!TIP]
> Ao excluir classificações de site usando o cmdlet **Set-SPOTenantCdnPolicy,** você substitui a lista definida no momento. Se você quiser excluir classificações de site adicionais, use o cmdlet primeiro para descobrir quais classificações já estão excluídas e, em seguida, adicioná-las junto com as novas.

Use o cmdlet **Set-SPOTenantCdnPolicy** para excluir as classificações de site que não deseja disponibilizar na CDN. Por padrão, nenhuma classificação de sites é excluída.

Em Windows PowerShell para SharePoint Online:

``` powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications >"
```

Para ver quais classificações de site estão restritas no momento, use o cmdlet **Get-SPOTenantCdnPolicies:**

``` powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

As propriedades que serão retornadas _são IncludeFileExtensions,_ _ExcludeRestrictedSiteClassifications_ e _ExcludeIfNoScriptDisabled_.

A _propriedade IncludeFileExtensions_ contém a lista de extensões de arquivo que serão servidas da CDN.

> [!NOTE]
> As extensões de arquivo padrão são diferentes entre público e privado.

A _propriedade ExcludeRestrictedSiteClassifications_ contém as classificações de site que você deseja excluir da CDN. Por exemplo, você pode excluir sites marcados como **Confidencial** para que o conteúdo de sites com essa classificação aplicada não seja servido da CDN.

A _propriedade ExcludeIfNoScriptDisabled_ exclui o conteúdo da CDN com base nas configurações de atributo _NoScript_ no nível do site. Por padrão, o atributo _NoScript_ é definido como **Habilitado para** Sites _Modernos_ e **Desabilitado** para sites _clássicos._ Isso depende das configurações do locatário.

Para obter mais informações sobre esses cmdlets, consulte [Set-SPOTenantCdnPolicy](/powershell/module/sharepoint-online/) e [Get-SPOTenantCdnPolicies](/powershell/module/sharepoint-online/).

<a name="Office365CDNforSPOOriginPosh"> </a>
### <a name="add-an-origin-for-your-assets"></a>Adicionar uma origem para seus ativos

Use o cmdlet **Add-SPOTenantCdnOrigin** para definir uma origem. Você pode definir várias origens. A origem é uma URL que aponta para uma biblioteca ou pasta do SharePoint contendo os ativos que você deseja hospedar na CDN.
  
> [!IMPORTANT]
> Você nunca deve colocar recursos que contenham informações do usuário ou sejam considerados confidenciais para sua organização em uma origem pública.

``` powershell
Add-SPOTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

O valor do _caminho_ é o caminho relativo para a biblioteca ou pasta que contém os ativos. Você pode usar caracteres curinga, além de caminhos relativos. As origens suportam curingas pré-anexados à URL. Isso permite que você crie origens que abrangem vários sites. Por exemplo, para incluir todos os ativos na pasta páginas mestras de todos os seus sites como uma origem pública dentro da CDN, digite o seguinte comando:

``` powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ O modificador de caractere curinga * só pode ser usado no início do caminho e corresponderá a todos os **/** segmentos de URL na URL especificada.
+ O caminho pode apontar para uma biblioteca de documentos, pasta ou site. Por exemplo, o caminho _*/site1_ corresponderá a todas as bibliotecas de documentos no site.

Você pode adicionar uma origem com um caminho relativo específico. Não é possível adicionar uma origem usando o caminho completo.

Este exemplo adiciona uma origem privada da biblioteca de sitesassets em um site específico:

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

Este exemplo adiciona uma origem privada da _pasta1_ na biblioteca de ativos de site do conjunto de sites:

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

Se houver um espaço no caminho, você poderá cercar o caminho entre aspas duplas ou substituir o espaço pela codificação de URL %20. Os exemplos a seguir adicionam uma origem privada da pasta _1_ na biblioteca de ativos de site do conjunto de sites:

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

Para obter mais informações sobre esse comando e sua sintaxe, consulte [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).

> [!NOTE]
> Em origens privadas, os ativos compartilhados de uma origem devem ter uma versão principal publicada antes de serem acessados pela CDN.
  
Depois de executar o comando, o sistema sincroniza a configuração no datacenter. Isso pode levar até 15 minutos.

<a name="ExamplePublicOrigin"> </a>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a>Exemplo: configurar uma origem pública para suas páginas mestras e para sua biblioteca de estilos para o SharePoint Online

Normalmente, essas origens são configuradas para você por padrão quando você habilita a CDN do Office 365. No entanto, se você quiser habilita-los manualmente, siga estas etapas.
  
+ Use o cmdlet **Add-SPOTenantCdnOrigin** para definir a biblioteca de estilos como uma origem pública.

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ Use o cmdlet **Add-SPOTenantCdnOrigin** para definir as páginas mestras como uma origem pública.

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

Para obter mais informações sobre esse comando e sua sintaxe, consulte [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).

Depois de executar o comando, o sistema sincroniza a configuração no datacenter. Isso pode levar até 15 minutos.

<a name="ExamplePrivateOrigin"> </a>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a>Exemplo: configurar uma origem privada para seus ativos de site, páginas de site e imagens de publicação para o SharePoint Online

+ Use o cmdlet **Add-SPOTenantCdnOrigin** para definir a pasta de ativos do site como uma origem privada.

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ Use o cmdlet **Add-SPOTenantCdnOrigin** para definir a pasta de páginas do site como uma origem privada.

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ Use o cmdlet **Add-SPOTenantCdnOrigin** para definir a pasta de imagens de publicação como uma origem privada.

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

Para obter mais informações sobre esse comando e sua sintaxe, consulte [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).

Depois de executar o comando, o sistema sincroniza a configuração no datacenter. Isso pode levar até 15 minutos.

<a name="ExamplePrivateOriginSiteCollection"> </a>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a>Exemplo: configurar uma origem privada para um conjunto de sites para o SharePoint Online

Use o cmdlet **Add-SPOTenantCdnOrigin** para definir um conjunto de sites como uma origem privada. Por exemplo:

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

Para obter mais informações sobre esse comando e sua sintaxe, consulte [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).
  
Depois de executar o comando, o sistema sincroniza a configuração no datacenter. Você pode ver uma _mensagem de configuração_ pendente que é esperada à medida que o locatário do SharePoint Online se conecta ao serviço CDN. Isso pode levar até 15 minutos.

<a name="CDNManage"> </a>
### <a name="manage-the-office-365-cdn"></a>Gerenciar a CDN do Office 365

Depois de configurar a CDN, você pode fazer alterações na configuração conforme atualiza o conteúdo ou conforme suas necessidades mudam, conforme descrito nesta seção.
  
<a name="Office365CDNforSPOaddremoveasset"> </a>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a>Adicionar, atualizar ou remover ativos da CDN do Office 365

Depois de concluir as etapas de instalação, você pode adicionar novos ativos e atualizar ou remover ativos existentes sempre que quiser. Basta fazer suas alterações nos ativos na pasta ou na biblioteca do SharePoint que você identificou como uma origem. Se você adicionar um novo ativo, ele estará disponível por meio da CDN imediatamente. No entanto, se você atualizar o ativo, levará até 15 minutos para que a nova cópia se propague e se torne disponível na CDN.
  
Se você precisar recuperar o local da origem, poderá usar o cmdlet **Get-SPOTenantCdnOrigins.** Para obter informações sobre como usar esse cmdlet, consulte [Get-SPOTenantCdnOrigins](/powershell/module/sharepoint-online/Get-SPOTenantCdnOrigins).

<a name="Office365CDNforSPORemoveOriginPosh"> </a>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a>Remover uma origem da CDN do Office 365

Você pode remover o acesso a uma pasta ou biblioteca do SharePoint que você identificou como uma origem. Para fazer isso, use o cmdlet **Remove-SPOTenantCdnOrigin.**

``` powershell
Remove-SPOTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

Para obter informações sobre como usar esse cmdlet, consulte [Remove-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Remove-SPOTenantCdnOrigin).

<a name="Office365CDNforSPOModifyOrigin"> </a>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a>Modificar uma origem na CDN do Office 365

Não é possível modificar uma origem criada. Em vez disso, remova a origem e adicione um novo. Para obter mais informações, consulte Para remover uma origem da CDN do [Office 365](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPosh) e Para adicionar uma [origem para seus ativos](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPosh).

<a name="Office365CDNforSPODisable"> </a>
#### <a name="disable-the-office-365-cdn"></a>Desabilitar a CDN do Office 365

Use o cmdlet **Set-SPOTenantCdnEnabled para** desabilitar a CDN da sua organização. Se você tiver as origens públicas e privadas habilitadas para a CDN, será necessário executar o cmdlet duas vezes, conforme mostrado nos exemplos a seguir.
  
Para desabilitar o uso de origens públicas na CDN, insira o seguinte comando:

``` powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $false
```

Para desabilitar o uso das origens privadas na CDN, insira o seguinte comando:

``` powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $false
```

Para obter mais informações sobre esse cmdlet, consulte [Set-SPOTenantCdnEnabled](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled).

</details>

<a name="CDNSetupinPnPPosh"> </a>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-pnp-powershell"></a>Configurar e configurar a CDN do Office 365 usando o PnP PowerShell

Os procedimentos nesta seção exigem que você use o PnP PowerShell para se conectar ao SharePoint Online. Para obter instruções, consulte [Getting started with PnP PowerShell](https://github.com/SharePoint/PnP-PowerShell#getting-started).

Conclua estas etapas para configurar e configurar a CDN para hospedar seus ativos no SharePoint Online usando o PnP PowerShell.

<details>
  <summary>Clique para expandir</summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a>Permitir que sua organização use a CDN do Office 365

Antes de fazer alterações nas configurações de CDN do locatário, você deve recuperar o status atual da configuração da CDN privada em seu locatário do Office 365. Conecte-se ao locatário usando o PnP PowerShell:

``` powershell
Connect-PnPOnline -Url https://contoso-admin.sharepoint.com -UseWebLogin
```

Agora use o cmdlet **Get-PnPTenantCdnEnabled** para recuperar as configurações de status da CDN do locatário:

``` powershell
Get-PnPTenantCdnEnabled -CdnType <Public | Private>
```

O status da CDN do CdnType especificado será exibido na tela.

Use o cmdlet **Set-PnPTenantCdnEnabled** para permitir que sua organização use a CDN do Office 365. Você pode permitir que sua organização use origens públicas, origens privadas ou ambas ao mesmo tempo. Você também pode configurar a CDN para ignorar a configuração de origens padrão ao habilita-la. Você sempre pode adicionar essas origens mais tarde, conforme descrito neste tópico.
  
No PnP PowerShell:

``` powershell
Set-PnPTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

Por exemplo, para permitir que sua organização use origens públicas e privadas, digite o seguinte comando:

``` powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true
```

Para permitir que sua organização use origens públicas e privadas, mas ignore a configuração das origens padrão, digite o seguinte comando:

``` powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

Consulte Origens de [CDN](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) padrão para obter informações sobre as origens provisionadas por padrão quando você habilita a CDN do Office 365 e o impacto potencial de ignorar a configuração de origens padrão.

Para permitir que sua organização use origens públicas, digite o seguinte comando:

``` powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $true
```

Para permitir que sua organização use origens privadas, digite o seguinte comando:

``` powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $true
```

Para obter mais informações sobre esse cmdlet, consulte [Set-PnPTenantCdnEnabled](/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled).

<a name="Office365CDNforPnPPoshFileType"> </a>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a>Alterar a lista de tipos de arquivo a incluir na CDN do Office 365 (Opcional)

> [!TIP]
> Ao definir tipos de arquivo usando o cmdlet **Set-PnPTenantCdnPolicy,** você substitui a lista definida no momento. Se você quiser adicionar tipos de arquivo adicionais à lista, use o cmdlet primeiro para descobrir quais tipos de arquivo já são permitidos e incluí-los na lista juntamente com os novos.
  
Use o cmdlet **Set-PnPTenantCdnPolicy** para definir tipos de arquivo estáticos que podem ser hospedados por origens públicas e privadas na CDN. Por padrão, os tipos de ativos comuns são permitidos, por exemplo .css, .gif, .jpg e .js.

No PnP PowerShell:

``` powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

Por exemplo, para habilitar a CDN para hospedar arquivos .css e .png, você inseriria o comando:

``` powershell
Set-PnPTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

Para ver quais tipos de arquivo atualmente são permitidos pela CDN, use o cmdlet **Get-PnPTenantCdnPolicies:**

``` powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

Para obter mais informações sobre esses cmdlets, consulte [Set-PnPTenantCdnPolicy](/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) e [Get-PnPTenantCdnPolicies](/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies).

<a name="Office365CDNforPnPPoshSiteClassification"> </a>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a>Alterar a lista de classificações de site que você deseja excluir da CDN do Office 365 (Opcional)

> [!TIP]
> Quando você exclui classificações de site usando o cmdlet **Set-PnPTenantCdnPolicy,** substitui a lista definida no momento. Se você quiser excluir classificações de site adicionais, use o cmdlet primeiro para descobrir quais classificações já estão excluídas e, em seguida, adicioná-las junto com as novas.

Use o cmdlet **Set-PnPTenantCdnPolicy** para excluir classificações de site que você não deseja disponibilizar pela CDN. Por padrão, nenhuma classificação de sites é excluída.

No PnP PowerShell:

``` powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications>"
```

Para ver quais classificações de site estão restritas no momento, use o cmdlet **Get-PnPTenantCdnPolicies:**

``` powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

As propriedades que serão retornadas _são IncludeFileExtensions,_ _ExcludeRestrictedSiteClassifications_ e _ExcludeIfNoScriptDisabled_.

A _propriedade IncludeFileExtensions_ contém a lista de extensões de arquivo que serão servidas da CDN.

> [!NOTE]
> As extensões de arquivo padrão são diferentes entre público e privado.

A _propriedade ExcludeRestrictedSiteClassifications_ contém as classificações de site que você deseja excluir da CDN. Por exemplo, você pode excluir sites marcados como **Confidencial** para que o conteúdo de sites com essa classificação aplicada não seja servido da CDN.

A _propriedade ExcludeIfNoScriptDisabled_ exclui o conteúdo da CDN com base nas configurações de atributo _NoScript_ no nível do site. Por padrão, o atributo _NoScript_ é definido como **Habilitado para** Sites _Modernos_ e **Desabilitado** para sites _clássicos._ Isso depende das configurações do locatário.

Para obter mais informações sobre esses cmdlets, consulte [Set-PnPTenantCdnPolicy](/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) e [Get-PnPTenantCdnPolicies](/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies).

<a name="Office365CDNforSPOOriginPnPPosh"> </a>
### <a name="add-an-origin-for-your-assets"></a>Adicionar uma origem para seus ativos

Use o cmdlet **Add-PnPTenantCdnOrigin** para definir uma origem. Você pode definir várias origens. A origem é uma URL que aponta para uma biblioteca ou pasta do SharePoint contendo os ativos que você deseja hospedar na CDN.
  
> [!IMPORTANT]
> Você nunca deve colocar recursos que contenham informações do usuário ou sejam considerados confidenciais para sua organização em uma origem pública.

``` powershell
Add-PnPTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

O valor do _caminho_ é o caminho relativo para a biblioteca ou pasta que contém os ativos. Você pode usar caracteres curinga, além de caminhos relativos. As origens suportam curingas pré-anexados à URL. Isso permite que você crie origens que abrangem vários sites. Por exemplo, para incluir todos os ativos na pasta páginas mestras de todos os seus sites como uma origem pública dentro da CDN, digite o seguinte comando:

``` powershell
Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ O modificador de caractere curinga * só pode ser usado no início do caminho e corresponderá a todos os **/** segmentos de URL na URL especificada.
+ O caminho pode apontar para uma biblioteca de documentos, pasta ou site. Por exemplo, o caminho _*/site1_ corresponderá a todas as bibliotecas de documentos no site.

Você pode adicionar uma origem com um caminho relativo específico. Não é possível adicionar uma origem usando o caminho completo.

Este exemplo adiciona uma origem privada da biblioteca de ativos do site em um site específico:

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

Este exemplo adiciona uma origem privada da _pasta1_ na biblioteca de ativos de site do conjunto de sites:

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

Se houver um espaço no caminho, você poderá cercar o caminho entre aspas duplas ou substituir o espaço pela codificação de URL %20. Os exemplos a seguir adicionam uma origem privada da pasta _1_ na biblioteca de ativos de site do conjunto de sites:

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

Para obter mais informações sobre esse comando e sua sintaxe, consulte [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).

> [!NOTE]
> Em origens privadas, os ativos compartilhados de uma origem devem ter uma versão principal publicada antes de serem acessados pela CDN.
  
Depois de executar o comando, o sistema sincroniza a configuração no datacenter. Isso pode levar até 15 minutos.

<a name="ExamplePublicOriginPnPPosh"> </a>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a>Exemplo: configurar uma origem pública para suas páginas mestras e para sua biblioteca de estilos para o SharePoint Online

Normalmente, essas origens são configuradas para você por padrão quando você habilita a CDN do Office 365. No entanto, se você quiser habilita-los manualmente, siga estas etapas.
  
+ Use o cmdlet **Add-PnPTenantCdnOrigin** para definir a biblioteca de estilos como uma origem pública.

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ Use o cmdlet **Add-PnPTenantCdnOrigin** para definir as páginas mestras como uma origem pública.

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

Para obter mais informações sobre esse comando e sua sintaxe, consulte [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).

Depois de executar o comando, o sistema sincroniza a configuração no datacenter. Isso pode levar até 15 minutos.

<a name="ExamplePrivateOriginPnPPosh"> </a>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a>Exemplo: configurar uma origem privada para seus ativos de site, páginas de site e imagens de publicação para o SharePoint Online

+ Use o cmdlet **Add-PnPTenantCdnOrigin** para definir a pasta de ativos do site como uma origem privada.

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ Use o cmdlet **Add-PnPTenantCdnOrigin** para definir a pasta de páginas do site como uma origem privada.

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ Use o cmdlet **Add-PnPTenantCdnOrigin** para definir a pasta de imagens de publicação como uma origem privada.

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

Para obter mais informações sobre esse comando e sua sintaxe, consulte [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).

Depois de executar o comando, o sistema sincroniza a configuração no datacenter. Isso pode levar até 15 minutos.

<a name="ExamplePrivateOriginSiteCollectionPnPPosh"> </a>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a>Exemplo: configurar uma origem privada para um conjunto de sites para o SharePoint Online

Use o cmdlet **Add-PnPTenantCdnOrigin** para definir um conjunto de sites como uma origem privada. Por exemplo:

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

Para obter mais informações sobre esse comando e sua sintaxe, consulte [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).
  
Depois de executar o comando, o sistema sincroniza a configuração no datacenter. Você pode ver uma _mensagem de configuração_ pendente que é esperada à medida que o locatário do SharePoint Online se conecta ao serviço CDN. Isso pode levar até 15 minutos.

<a name="CDNManagePnPPosh"> </a>
### <a name="manage-the-office-365-cdn"></a>Gerenciar a CDN do Office 365

Depois de configurar a CDN, você pode fazer alterações na configuração conforme atualiza o conteúdo ou conforme suas necessidades mudam, conforme descrito nesta seção.
  
<a name="Office365CDNforSPOaddremoveassetPnPPosh"> </a>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a>Adicionar, atualizar ou remover ativos da CDN do Office 365

Depois de concluir as etapas de instalação, você pode adicionar novos ativos e atualizar ou remover ativos existentes sempre que quiser. Basta fazer suas alterações nos ativos na pasta ou na biblioteca do SharePoint que você identificou como uma origem. Se você adicionar um novo ativo, ele estará disponível por meio da CDN imediatamente. No entanto, se você atualizar o ativo, levará até 15 minutos para que a nova cópia se propague e se torne disponível na CDN.
  
Se você precisar recuperar o local da origem, poderá usar o cmdlet **Get-PnPTenantCdnOrigin.** Para obter informações sobre como usar esse cmdlet, consulte [Get-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/get-pnptenantcdnorigin).

<a name="Office365CDNforSPORemoveOriginPnPPosh"> </a>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a>Remover uma origem da CDN do Office 365

Você pode remover o acesso a uma pasta ou biblioteca do SharePoint que você identificou como uma origem. Para fazer isso, use o cmdlet **Remove-PnPTenantCdnOrigin.**

``` powershell
Remove-PnPTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

Para obter informações sobre como usar esse cmdlet, consulte [Remove-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/remove-pnptenantcdnorigin).

<a name="Office365CDNforSPOModifyOriginPnPPosh"> </a>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a>Modificar uma origem na CDN do Office 365

Não é possível modificar uma origem criada. Em vez disso, remova a origem e adicione um novo. Para obter mais informações, consulte Para remover uma origem da CDN do [Office 365](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPnPPosh) e Para adicionar uma [origem para seus ativos](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPnPPosh).

<a name="Office365CDNforSPODisable"> </a>
#### <a name="disable-the-office-365-cdn"></a>Desabilitar a CDN do Office 365

Use o cmdlet **Set-PnPTenantCdnEnabled** para desabilitar a CDN da sua organização. Se você tiver as origens públicas e privadas habilitadas para a CDN, será necessário executar o cmdlet duas vezes, conforme mostrado nos exemplos a seguir.
  
Para desabilitar o uso de origens públicas na CDN, insira o seguinte comando:

``` powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $false
```

Para desabilitar o uso das origens privadas na CDN, insira o seguinte comando:

``` powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $false
```

Para obter mais informações sobre esse cmdlet, consulte [Set-PnPTenantCdnEnabled](/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled).

</details>

<a name="CDNSetupinCLI"> </a>
## <a name="set-up-and-configure-the-office-365-cdn-using-the-office-365-cli"></a>Instalação e configuração da CDN do Office 365 usando a CLI do Office 365

Os procedimentos nesta seção exigem que você tenha instalado a CLI do [Office 365](https://aka.ms/o365cli). Em seguida, conecte-se ao locatário do Office 365 usando o [comando de logon.](https://pnp.github.io/office365-cli/cmd/login/)

Conclua estas etapas para configurar e configurar a CDN para hospedar seus ativos no SharePoint Online usando a CLI do Office 365.

<details>
  <summary>Clique para expandir</summary>

### <a name="enable-the-office-365-cdn"></a>Habilitar a CDN do Office 365

Você pode gerenciar o estado da CDN do Office 365 no locatário usando o comando [spo cdn set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-set/).

Para habilitar a CDN pública do Office 365 no locatário:

```sh
spo cdn set --type Public --enabled true
```

Para habilitar a CDN do SharePoint do Office 365, execute:

```sh
spo cdn set --type Private --enabled true
```

#### <a name="view-the-current-status-of-the-office-365-cdn"></a>Exiba o status atual da CDN do Office 365

Para verificar se o tipo específico de CDN do Office 365 está habilitado ou desabilitado, use o comando [spo cdn get.](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-get/)

Para verificar se a CDN pública do Office 365 está habilitada:

```sh
spo cdn get --type Public
```

### <a name="view-the-office-365-cdn-origins"></a>Exibir as origens da CDN do Office 365

Para exibir as origens de CDN pública do Office 365 configuradas no momento:

```sh
spo cdn origin list --type Public
```

Consulte [Origens padrão da CDN](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) para obter informações sobre as origens provisionadas por padrão ao habilitar a CDN do Office 365.

### <a name="add-an-office-365-cdn-origin"></a>Adicionar uma origem cdn do Office 365

> [!IMPORTANT]
> Você nunca deve colocar recursos considerados confidenciais para sua organização em uma biblioteca de documentos do SharePoint configurada como uma origem pública.

Use o adicionar comando [spo cdn origem ](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-add/) para definir uma origem de CDN. Você pode definir várias origens. A origem é uma URL que aponta para uma biblioteca ou pasta do SharePoint contendo os ativos que você deseja hospedar na CDN.

```sh
spo cdn origin add --type [Public | Private] --origin <path>
```

Onde `path` está o caminho relativo para a pasta que contém os ativos. Você pode usar caracteres curinga, além de caminhos relativos.

Para incluir todos os ativos na **Galeria de Páginas Mestras** de todos os sites como uma origem pública, execute:

```sh
spo cdn origin add --type Public --origin */masterpage
```

Para configurar uma origem privada para um conjunto de sites específico:

```sh
spo cdn origin add --type Private --origin sites/site1/siteassets
```

> [!NOTE]
> Após adicionar uma origem de CDN, pode levar até 15 minutos para que você possa recuperar arquivos por meio do serviço de CDN. Você pode verificar se a origem específica já foi ativada usando o comando [spo cdn origin list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/).

### <a name="remove-an-office-365-cdn-origin"></a>Remover uma origem da CDN do Office 365

Use o comando [spo cdn origin remove](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-remove/) para remover uma origem de CDN para o tipo de CDN especificado.

Para remover uma origem pública da configuração da CDN, execute:

```sh
spo cdn origin remove --type Public --origin */masterpage
```

> [!NOTE]
> Remover uma origem da CDN não afeta os arquivos armazenados em qualquer biblioteca de documentos que corresponde a essa origem. Se esses ativos foram referenciados usando a URL do SharePoint, o SharePoint alterna automaticamente para a URL original apontando para a biblioteca de documentos. No entanto, se os ativos foram referenciados usando uma URL de CDN pública, remover a origem quebrará o link e você precisará alterá-los manualmente.

### <a name="modify-an-office-365-cdn-origin"></a>Modificar uma origem da CDN do Office 365

Não é possível alterar uma origem de CDN. Em vez disso, você deve remover a origem de CDN definida anteriormente usando o comando `spo cdn origin remove` e adicionar outro usando o comando `spo cdn origin add`.

### <a name="change-the-types-of-files-to-include-in-the-office-365-cdn"></a>Alterar os tipos de arquivos a incluir na CDN do Office 365

Por padrão, os seguintes tipos de arquivo são incluídos na CDN: _.css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff e .woff2_. Se precisar incluir outros tipos de arquivo na CDN, você pode alterar a configuração de CDN usando o comando [spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/).

> [!NOTE]
> Ao alterar a lista de tipos de arquivo, você substitui a lista definida no momento. Se quiser incluir outros tipos de arquivo, primeiro use o comando [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) para descobrir quais tipos de arquivo estão configurados no momento.

Para adicionar o _tipo de arquivo JSON_ à lista padrão de tipos de arquivo incluídos na CDN pública, execute:

```sh
spo cdn policy set --type Public --policy IncludeFileExtensions --value "CSS,EOT,GIF,ICO,JPEG,JPG,JS,MAP,PNG,SVG,TTF,WOFF,JSON"
```

### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn"></a>Altere a lista de classificações de site que você deseja excluir da CDN do Office 365

Use o comando [spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) para excluir as classificações de site que não deseja disponibilizar na CDN. Por padrão, nenhuma classificação de sites é excluída.

> [!NOTE]
> Ao alterar a lista de classificações de sites excluída, você substitui a lista definida no momento. Se desejar excluir outras classificações, primeiro use o comando [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-list/) para descobrir quais classificações estão configuradas no momento.

Para excluir sites classificados como _HBI_ da CDN pública, execute

```sh
spo cdn policy set --type Public --policy ExcludeRestrictedSiteClassifications --value "HBI"
```

### <a name="disable-the-office-365-cdn"></a>Desabilitar a CDN do Office 365

Para desabilitar a CDN do Office 365, use o comando `spo cdn set`, por exemplo:

```sh
spo cdn set --type Public --enabled false
```

</details>

## <a name="using-your-cdn-assets"></a>Usando seus ativos CDN

Agora que você habilitar a CDN e configurou origens e políticas, você pode começar a usar seus ativos cdn.

Esta seção ajudará você a entender como usar URLs de CDN em suas páginas e conteúdo do SharePoint para que o SharePoint redirecione solicitações de ativos em origens públicas e privadas para a CDN.

+ [Atualizando links para ativos CDN](use-microsoft-365-cdn-with-spo.md#updating-links-to-cdn-assets)
+ [Usando ativos em origens públicas](use-microsoft-365-cdn-with-spo.md#using-assets-in-public-origins)
+ [Usando ativos em origens privadas](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins)

Para obter informações sobre como usar a CDN para hospedar web parts do lado do cliente, consulte o tópico Hospedar sua Web Part do lado do cliente da CDN do [Office 365 (Hello World part 4)](/sharepoint/dev/spfx/web-parts/get-started/hosting-webpart-from-office-365-cdn).

> [!NOTE]
> Se você adicionar a _pasta ClientSideAssets_ à lista de origens da **CDN** privada, as Web Parts personalizadas hospedadas pela CDN falharão ao renderizar. Os arquivos usados pelas Web Parts SPFX só podem utilizar a CDN pública e a pasta ClientSideAssets é uma origem padrão para a CDN pública. 

### <a name="updating-links-to-cdn-assets"></a>Atualizando links para ativos CDN

Para usar ativos adicionados a uma origem, basta atualizar links para o arquivo original com o caminho para o arquivo na origem.

+ Edite a página ou o conteúdo que contém links para ativos que você adicionou a uma origem. Você também pode usar um dos vários métodos para pesquisar globalmente e substituir links em um site de entrada ou conjunto de sites se quiser atualizar o link para um determinado ativo em todos os lugares em que ele aparecer.
+ Para cada link para um ativo em uma origem, substitua o caminho pelo caminho para o arquivo na origem da CDN. Você pode usar caminhos relativos.
+ Salve a página ou o conteúdo.

Por exemplo, considere a imagem _/site/SiteAssets/images/image.png_, que você copiou para a pasta da biblioteca de documentos _/site/CDN_origins/public/_. Para usar o ativo CDN, substitua o caminho original para o local do arquivo de imagem pelo caminho para a origem para tornar a nova URL _/site/CDN_origins/public/image.png_.

Se você quiser usar a URL completa para o ativo em vez de um caminho relativo, construa o link assim:

`https://<TenantHostName>.sharepoint.com/sites/site/CDN_origins/public/image.png`

> [!NOTE]
> Em geral, você não deve codificar URLs diretamente para ativos na CDN. No entanto, você pode construir manualmente URLs para ativos em origens públicas, se necessário. Para obter mais informações, consulte [Hardcoding CDN URLs for public assets](use-microsoft-365-cdn-with-spo.md#hardcoding-cdn-urls-for-public-assets).

Para saber mais sobre como verificar se os ativos estão sendo atendidos na CDN, consulte Como confirmar se os ativos estão sendo atendidos pela [CDN?](use-microsoft-365-cdn-with-spo.md#CDNConfirm) na seção Solução de problemas da CDN do [Office 365.](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting)

### <a name="using-assets-in-public-origins"></a>Usando ativos em origens públicas

O **recurso de** publicação no SharePoint Online regrava automaticamente URLs de ativos armazenados em origens públicas para seus equivalentes de CDN para que os ativos sejam atendidos do serviço CDN em vez do SharePoint.

Se sua origem estiver em um site com o recurso de Publicação habilitado e os ativos que você deseja descarregar para a CDN estão em uma das seguintes categorias, o SharePoint reescreverá automaticamente URLs para ativos na origem, desde que o ativo não tenha sido excluído por uma política de CDN.

Mostramos a seguir uma visão geral dos links reescritos automaticamente pelo recurso de Publicação do SharePoint:

+ URLs IMG/LINK/CSS em respostas de HTML de página de publicação clássica
  + Incluem-se imagens adicionadas por autores no conteúdo HTML de uma página
+ URLs de imagem da web part Apresentação de Slides da Biblioteca de Imagens
+ Campos de imagem nos resultados da API REST SPList (RenderListDataAsStream)
  + Use a nova _propriedade ImageFieldsToTryRewriteToCdnUrls_ para fornecer uma lista separada de vírgulas de campos
  + Oferece suporte a campos de hiperlink e campos PublishingImage
+ Representações de imagem do SharePoint

O diagrama a seguir ilustra o fluxo de trabalho quando o SharePoint recebe uma solicitação de uma página contendo ativos de origem pública.

![Diagrama de fluxo de trabalho: recuperando ativos cdn do Office 365 de origem pública](../media/O365-CDN/o365-cdn-public-steps-transparent.svg "Fluxo de trabalho: recuperando ativos cdn do Office 365 de origem pública")

> [!TIP]
> Se você quiser desabilitar a reescrita automática para URLs específicas em uma página, pode fazer check-out da página e adicionar o parâmetro de cadeia de caracteres de **consulta? NoAutoReWrites=true** até o final de cada link que você deseja desabilitar.

#### <a name="constructing-cdn-urls-for-public-assets"></a>Construir URLs de CDN para ativos públicos

Se o recurso _de_ Publicação não estiver habilitado para uma origem pública ou o ativo não for um dos tipos de link suportados pelo recurso de reescrita automática do serviço CDN, você poderá construir manualmente URLs para o local da CDN dos ativos e usar essas URLs em seu conteúdo.

> [!NOTE]
> Você não pode codificar ou construir URLs de CDN para ativos em uma origem privada porque o token de acesso necessário que forma a última seção da URL é gerado no momento em que o recurso é solicitado. Você pode construir a URL para CDN pública e a URL não deve ser codificada com dificuldade, pois ela está sujeita a alterações.

Para ativos públicos de CDN, o formato URL terá a seguinte aparência:

``` html
https://publiccdn.sharepointonline.com/<TenantHostName>/sites/site/library/asset.png
```

Substitua **TenantHostName** pelo nome do locatário. Exemplo:

``` html
https://publiccdn.sharepointonline.com/contoso.sharepoint.com/sites/site/library/asset.png
```
> [!NOTE]
> A propriedade de contexto de página deve ser usada para construir o prefixo em vez de codificação " https://publiccdn.sharepointonline.com ". A URL está sujeita a alterações e não deve ser codificada. Se você estiver usando modelos de exibição com o SharePoint Online clássico, poderá usar a propriedade "window._spPageContextInfo.publicCdnBaseUrl" em seu modelo de exibição para o prefixo da URL. Se você for Web Parts SPFx para o SharePoint moderno e clássico, poderá utilizar a propriedade "this.context.pageContext.legacyPageContext.publicCdnBaseUrl". Isso fornecerá o prefixo para que, se for alterado, sua implementação será atualizada com ele. Como exemplo para SPFx, a URL pode ser construída usando a propriedade "this.context.pageContext.legacyPageContext.publicCdnBaseUrl" + "/" + "host" + "/" + "relativeURL para o item". Confira [Usando a CDN no código do lado](https://youtu.be/IH1RbQlbhIA) do cliente que faz parte da série de desempenho da [1ª temporada](https://aka.ms/sppnp-perfvideos)


### <a name="using-assets-in-private-origins"></a>Usando ativos em origens privadas

Nenhuma configuração adicional é necessária para usar ativos em origens privadas. O SharePoint Online reescreve automaticamente URLs para ativos em origens privadas, portanto, as solicitações para esses ativos sempre serão atendidas da CDN. Você não pode criar manualmente URLs para ativos CDN em origens privadas porque essas URLs contêm tokens que devem ser gerados automaticamente pelo SharePoint Online no momento em que o ativo é solicitado.

O acesso a ativos em origens privadas é protegido por tokens gerados dinamicamente com base nas permissões do usuário para a origem, com as advertências descritas nas seções a seguir. Os usuários devem ter pelo menos **acesso de** leitura às origens da CDN para renderizar o conteúdo.

O diagrama a seguir ilustra o fluxo de trabalho quando o SharePoint recebe uma solicitação de uma página contendo ativos de origem privada.

![Diagrama de fluxo de trabalho: recuperando ativos cdn do Office 365 de origem privada](../media/O365-CDN/o365-cdn-private-steps-transparent.svg "Fluxo de trabalho: recuperando ativos cdn do Office 365 de origem privada")

#### <a name="token-based-authorization-in-private-origins"></a>Autorização baseada em token em origens privadas

O acesso a ativos em origens privadas na CDN do Office 365 é concedido por tokens gerados pelo SharePoint Online. Os usuários que já têm permissão para acessar a pasta ou biblioteca designada pela origem são automaticamente concedidos tokens que permitem que o usuário acesse o arquivo com base em seu nível de permissão. Esses tokens de acesso são válidos de 30 a 90 minutos depois que são gerados para ajudar a evitar ataques de repetição de token.

Depois que o token de acesso é gerado, o SharePoint Online retorna um URI personalizado para o cliente que contém dois _parâmetros_ de autorização como (token de autorização de borda) e _aveia_ (token de autorização de origem). A estrutura de cada token é< tempo de expiração no formato época de _>__<'secure signature'>_. Por exemplo:

``` html
https://privatecdn.sharepointonline.com/contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg?eat=1486154359_cc59042c5c55c90b26a2775323c7c8112718431228fe84d568a3795a63912840&oat=1486154359_7d73c2e3ba4b7b1f97242332900616db0d4ffb04312
```

> [!NOTE]
> Qualquer pessoa que tenha o token pode acessar o recurso na CDN. No entanto, as URLs que contêm esses tokens de acesso são compartilhadas somente por HTTPS, portanto, a menos que a URL seja explicitamente compartilhada por um usuário final antes que o token expire, o ativo não estará acessível a usuários não autorizados.

#### <a name="item-level-permissions-are-not-supported-for-assets-in-private-origins"></a>Permissões de nível de item não são suportadas para ativos em origens privadas

É importante observar que o SharePoint Online não dá suporte a permissões de nível de item para ativos em origens privadas. Por exemplo, para um arquivo localizado em , os usuários têm acesso efetivo ao `https://contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg` arquivo dadas as seguintes condições:

|User  |Permissões  |Acesso efetivo  |
|---------|---------|---------|
|Usuário 1     |Tem acesso à pasta1         |Pode acessar image1.jpg da CDN         |
|Usuário 2     |Não tem acesso à pasta1         |Não é possível acessar image1.jpg da CDN         |
|Usuário 3     |Não tem acesso à pasta1, mas tem permissão explícita para acessar image1.jpg no SharePoint Online         |Pode acessar o ativo image1.jpg diretamente do SharePoint Online, mas não da CDN         |
|Usuário 4     |Tem acesso à pasta1, mas foi explicitamente negado o acesso image1.jpg no SharePoint Online         |Não é possível acessar o ativo do SharePoint Online, mas pode acessar o ativo da CDN apesar de ter sido negado o acesso ao arquivo no SharePoint Online         |

<a name="CDNTroubleshooting"> </a>
## <a name="troubleshooting-the-office-365-cdn"></a>Solução de problemas da CDN do Office 365

<a name="CDNConfirm"> </a>
### <a name="how-do-i-confirm-that-assets-are-being-served-by-the-cdn"></a>Como confirmar se os ativos estão sendo atendidos pela CDN?

Depois de adicionar links a ativos cdn a uma página, você pode confirmar se o ativo está sendo servido da CDN navegando até a página, clicando com o botão direito do mouse na imagem depois que ele renderizou e revisou a URL da imagem.

Você também pode usar as ferramentas de desenvolvedor do navegador para exibir a URL de cada ativo em uma página ou usar uma ferramenta de rastreamento de rede de terceiros.

> [!NOTE]
> Se você usar uma ferramenta de rede como o Fiddler para testar seus ativos fora da renderização do ativo de uma página do SharePoint, você deve adicionar manualmente o header do referer "Referer: " à solicitação GET onde a URL é a URL raiz do locatário do `https://yourdomain.sharepoint.com` SharePoint Online.

Não é possível testar URLs de CDN diretamente em um navegador da Web porque você deve ter um referer vindo do SharePoint Online. No entanto, se você adicionar a URL do ativo CDN a uma página do SharePoint e abrir a página em um navegador, você verá o ativo CDN renderizado na página.

Para obter mais informações sobre como usar as ferramentas de desenvolvedor no navegador do Microsoft Edge, consulte [Microsoft Edge Developer Tools](/microsoft-edge/devtools-guide).

Para assistir a um vídeo curto hospedado no canal do [SharePoint Developer Patterns and Practices do YouTube](https://aka.ms/sppnp-videos) demonstrando como verificar se a CDN está funcionando, consulte Verifying your [CDN usage](https://www.youtube.com/watch?v=ClCtBAtGjE8&list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA&index=5)and ensuring optimal network connectivity .

### <a name="why-are-assets-from-a-new-origin-unavailable"></a>Por que os ativos de uma nova origem estão indisponíveis?
Os ativos em novas origens não estarão disponíveis imediatamente para uso, pois leva tempo para que o registro se propague pela CDN e para que os ativos sejam carregados da origem para o armazenamento da CDN. O tempo necessário para que os ativos sejam disponibilizados na CDN depende de quantos ativos e tamanhos de arquivos.

### <a name="my-client-side-web-part-or-sharepoint-framework-solution-isnt-working"></a>Minha web part do lado do cliente ou a solução da Estrutura do SharePoint não está funcionando

Quando você habilita a CDN do Office 365 para origens públicas, o serviço CDN cria automaticamente essas origens padrão:

+ */MASTERPAGE
+ BIBLIOTECA */STYLE
+ */CLIENTSIDEASSETS

Se a origem */clientsideassets estiver ausente, as soluções da Estrutura do SharePoint falharão e nenhuma mensagem de aviso ou erro será gerada. Essa origem pode estar ausente porque a CDN foi habilitada com o parâmetro _-NoDefaultOrigins_ definido como $true , ou porque **a** origem foi excluída manualmente.

Você pode verificar quais origens estão presentes com o seguinte comando do PowerShell:

``` powershell
Get-SPOTenantCdnOrigins -CdnType Public
```

Ou você pode verificar com a CLI do Office 365:

``` powershell
spo cdn origin list
```

Para adicionar a origem no PowerShell:

``` powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */CLIENTSIDEASSETS
```

Para adicionar a origem na CLI do Office 365:

``` powershell
spo cdn origin add --origin */CLIENTSIDEASSETS
```

### <a name="what-powershell-modules-and-cli-shells-do-i-need-to-work-with-the-office-365-cdn"></a>Quais módulos e shells de CLI do PowerShell preciso para trabalhar com a CDN do Office 365?

Você pode optar por trabalhar com a CDN do Office 365 usando o módulo do Shell de Gerenciamento do **SharePoint Online** do PowerShell ou a **CLI do Office 365.**

+ [Introdução ao Shell de Gerenciamento do SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)
+ [Instalar a CLI do Office 365](https://pnp.github.io/office365-cli/user-guide/installing-cli/)

## <a name="see-also"></a>Confira também

[Redes de Distribuição de Conteúdo](./content-delivery-networks.md)

[Planejamento de rede e ajuste de desempenho para o Office 365](./network-planning-and-performance.md)

[Série de desempenho do SharePoint - Série de vídeo CDN do Office 365](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)