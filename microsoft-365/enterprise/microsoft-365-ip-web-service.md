---
title: URL do serviço Web e endereço IP do Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 8/6/2019
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- m365initiative-coredeploy
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.reviewer: pandrew
search.appverid:
- MET150
- MOE150
- BCS160
description: Aprenda como usar o endereço IP e o serviço URL da Web do Office 365 para ajudá-lo a identificar e diferenciar melhor o tráfego de rede do Office 365.
ms.openlocfilehash: 1948491e1d3db724e7b7b6a5275234acab4be08a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918949"
---
# <a name="office-365-ip-address-and-url-web-service"></a>URL do serviço Web e endereço IP do Office 365

A URL do serviço Web e endereço IP do Office 365 ajudam a identificar e diferenciar melhor o tráfego de rede do Office 365, tornando mais fácil para você avaliar, configurar e manter-se atualizado com as alterações. Esse serviço Web baseado em REST substitui os arquivos anteriores do XML para download, que foram desativados em 2 de outubro de 2018.

Como um cliente ou um fornecedor de dispositivos de perímetro de rede, você pode criar com o novo serviço Web baseado em REST para as entradas FQDN e os endereços IP do Office 365. É possível acessar os dados diretamente de um navegador de Web usando essas URLs:

- Para ter a última versão dos intervalos de endereços IP e URLs do Office 365, use [https://endpoints.office.com/version](https://endpoints.office.com/version?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7).
- Para os dados na página de intervalos de endereços IP e URLs do Office 365 para firewalls e servidores proxy, use [https://endpoints.office.com/endpoints/worldwide](https://endpoints.office.com/endpoints/worldwide?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7).
- Para obter as últimas alterações desde julho de 2018, quando o serviço Web foi disponibilizado, use [https://endpoints.office.com/changes/worldwide/0000000000](https://endpoints.office.com/changes/worldwide/0000000000?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7).

Como cliente, você pode usar esse serviço Web para:

- Atualize os seus scripts do Windows PowerShell para obter dados de ponto de extremidade do Office 365 e modificar qualquer formatação dos dispositivos de rede.
- Use essas informações para atualizar os arquivos PAC implantados nos computadores clientes.

Como fornecedor de dispositivos de perímetro de rede, é possível usar esse serviço Web para:

- Criar e testar o software do dispositivo para baixar a lista de configuração automatizada.
- Verificar a versão atual.
- Obter as alterações atuais.

> [!NOTE]
> Se você estiver usando o Azure ExpressRoute para se conectar ao Office 365, confira [Azure ExpressRoute para Office 365](azure-expressroute.md) para se familiarizar com os serviços do Office 365 com suporte no Azure ExpressRoute. Além disso, veja o artigo [URLs e intervalos de endereços IP do Office 365](urls-and-ip-address-ranges.md) para entender quais solicitações de rede para aplicativos do Office 365 exigem conectividade com a Internet. Isso ajudará a configurar melhor seus dispositivos de segurança de perímetro.

Para saber mais, veja:

- [Comunicado de postagem no blog do Fórum da Comunidade de Tecnologia do Office 365](https://techcommunity.microsoft.com/t5/Office-365-Blog/Announcing-Office-365-endpoint-categories-and-Office-365-IP/ba-p/177638)
- [Fórum da Comunidade de Tecnologia do Office 365 para perguntas sobre o uso dos serviços Web](https://techcommunity.microsoft.com/t5/Office-365-Networking/bd-p/Office365Networking)

## <a name="common-parameters"></a>Parâmetros comuns

Estes parâmetros são comuns a todos os métodos de serviço Web:

- **format=<JSON | CSV>** — Por padrão, o formato de dados retornado é JSON. Use este parâmetro opcional para retornar os dados no formato de valores separados por vírgula (CSV).
- **ClientRequestId=\<guid>** — Um GUID necessário que você gera para associação de clientes. Gerar um GUID exclusivo para cada computador que chama um serviço Web (os scripts incluídos na página geram um GUID para você). Não use os GUIDs mostrados nos exemplos a seguir porque eles podem ser bloqueados pelo serviço da Web no futuro. O formato GUID é _xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx_, em que x representa um número hexadecimal.

  Para gerar um GUID, você pode usar o comando [New-Guid](/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6) do PowerShell ou usar um serviço online como [Gerador de GUIDs Online](https://www.guidgenerator.com/).

## <a name="version-web-method"></a>Método da web de versão

A Microsoft atualiza as entradas de FQDN e o endereço IP do Office 365 ao final de cada mês. Atualizações fora de banda às vezes são publicadas por causa de incidentes de suporte, atualizações de segurança ou outros requisitos operacionais.

Os dados de cada instância publicada recebem um número de versão e o método Web de versão permite que você verifique a última versão de cada instância de serviço do Office 365. Recomendamos verificar a versão não mais que uma vez.

Os parâmetros para o método da web de versão são:

- **AllVersions=<true | false>** — Por padrão, a versão retornada é a mais recente. Inclua este parâmetro opcional para solicitar todas as versões publicadas desde que o serviço da Web foi lançado pela primeira vez.
- **Format=<JSON | CSV | RSS>** — Além dos formatos JSON e CSV, o método Web de versão também é compatível com RSS. Você pode usar esse parâmetro opcional junto com o parâmetro _AllVersions=true_ para solicitar um feed RSS que possa ser usado com o Outlook ou outros leitores de RSS.
- **Instance=<Worldwide | China | Germany | USGovDoD | USGovGCCHigh>** — Este parâmetro opcional especifica a instância para o retorno da versão. Se omitido, todas as instâncias serão retornadas. As instâncias válidas são: em todo o mundo, China, Alemanha, USGovDoD, USGovGCCHigh.

O método Web de versão não é limitado por taxa e nunca retornará o código de resposta HTTP 429. A resposta ao método Web de versão inclui um cabeçalho de controle de cache que recomenda o armazenamento em cache dos dados por 1 hora. O resultado do método Web de versão pode ser um único registro ou uma matriz de registros. Os elementos de cada registro são:

- instance — Um nome curto da instância de serviço do Office 365.
- latest — A versão mais recente dos pontos de extremidade da instância especificada.
- versions — Uma lista com todas as versões anteriores da instância especificada. Este elemento só será incluído se o parâmetro _AllVersions_ for verdadeiro.

### <a name="examples"></a>Exemplos:

Exemplo 1 de URI de solicitação: [https://endpoints.office.com/version?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/version?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)

Esse URI retorna a última versão de cada instância de serviço do Office 365. Exemplo de resultado:

```json
[
 {
  "instance": "Worldwide",
  "latest": "2018063000"
 },
 {
  "instance": "USGovDoD",
  "latest": "2018063000"
 },
 {
  "instance": "USGovGCCHigh",
  "latest": "2018063000"
 },
 {
  "instance": "China",
  "latest": "2018063000"
 },
 {
  "instance": "Germany",
  "latest": "2018063000"
 }
]
```

> [!IMPORTANT]
> O GUID para o parâmetro ClientRequestID nesses URIs são apenas um exemplo. Para experimentar os URIs do serviço Web, gere o seu próprio GUID. O GUIDs exibido nesses exemplos pode ser bloqueado pelo serviço Web no futuro.

Exemplo 2 de URI de solicitação: [https://endpoints.office.com/version/Worldwide?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/version/Worldwide?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)

Esse URI retorna a última versão da instância de serviço especificada do Office 365. Exemplo de resultado:

```json
{
 "instance": "Worldwide",
 "latest": "2018063000"
}
```

Exemplo 3 de URI de solicitação: [https://endpoints.office.com/version/Worldwide?Format=CSV&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/version/Worldwide?Format=CSV&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)

Este URI mostra os resultados no formato CSV. Exemplo de resultado:

```csv
instance,latest
Worldwide,2018063000
```

Exemplo 4 de URI de solicitação: [https://endpoints.office.com/version/Worldwide?AllVersions=true&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/version/Worldwide?AllVersions=true&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)

Este URI mostra todas as versões anteriores que foram publicadas para a instância de serviço do Office 365 em todo o mundo. Exemplo de resultado:

```json
{
  "instance": "Worldwide",
  "latest": "2018063000",
  "versions": [
    "2018063000",
    "2018062000"
  ]
}
```

Exemplo 5 de URI de RSS feed: [https://endpoints.office.com/version/worldwide?clientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7&allVersions=true&format=RSS](https://endpoints.office.com/version/worldwide?clientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7&allVersions=true&format=RSS)

Este URI mostra um RSS feed das versões publicadas que contêm links para a lista de alterações de cada versão. Exemplo de resultado:

```xml
<?xml version="1.0" encoding="ISO-8859-1"?>
<rss version="2.0" xmlns:a10="https://www.w3.org/2005/Atom">
<channel>
<link>https://aka.ms/o365ip</link>
<description/>
<language>en-us</language>
<lastBuildDate>Thu, 02 Aug 2018 00:00:00 Z</lastBuildDate>
<item>
<guid isPermaLink="false">2018080200</guid>
<link>https://endpoints.office.com/changes/Worldwide/2018080200?singleVersion&clientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7</link> <description>Version 2018080200 includes 2 changes. IPs: 2 added and 0 removed.</description>
<pubDate>Thu, 02 Aug 2018 00:00:00 Z</pubDate>
</item>
```

## <a name="endpoints-web-method"></a>Método da Web de pontos de extremidade

O método da Web de pontos de extremidade retorna todos os registros para intervalos de endereços IP e URLs que compõem o serviço do Office 365. Os dados mais recentes do método da Web de pontos de extremidade devem ser usados para a configuração de dispositivos de rede. A Microsoft fornece notificações antecipadas 30 dias antes de publicar novas incursões para dar tempo para atualizar listas de controle de acesso e listas de bypass de servidores proxy. Recomendamos que você chame o método da Web de pontos de extremidade o método Web da versão indicar que uma nova versão dos dados que está disponível.

Os parâmetros para o método da Web de pontos de extremidade são:

- **ServiceAreas=<Common | Exchange | SharePoint | Skype>** — Uma lista de áreas de serviço separadas por vírgulas. Os itens válidos são _Common_, _Exchange_, _SharePoint_ e _Skype_. Como os itens da área de serviço _Common_ são um pré-requisito para todas as outras áreas de serviço, o serviço da Web sempre os incluirá. Se você não incluir esse parâmetro, todas as áreas de serviço serão retornadas.
- **TenantName=<tenant_name>** — Seu nome de locatário do Office 365. O serviço da web insere o seu nome fornecido em partes de URLs que incluem o nome do locatário. Se você não fornecer um nome de locatário, essas partes das URLs terão o caractere curinga (\*).
- **NoIPv6=<true | false>** — Defina o valor como _verdadeiro_ para excluir endereços IPv6 dos resultados se você não usar o IPv6 em sua rede.
- **Instance=<Worldwide | China | Germany | USGovDoD | USGovGCCHigh>** — Este parâmetro obrigatório especifica a instância para a qual retornar os terminais. As instâncias válidas são: _Mundialmente_, _China_, _Alemanha_, _USGovDoD_ e _USGovGCCHigh_.

Se você chamar o método Web de pontos de extremidade um grande número de vezes a partir do mesmo endereço IP do cliente, poderá receber o código de resposta HTTP _429 (Excesso de solicitações)_. Se você receber o código de resposta, você deve esperar 1 hora antes de repetir sua solicitação ou gerar um GUID para a solicitação. Como prática recomendada geral, apenas chame o método Web de pontos de extremidade quando o método Web de versão indicar que há uma nova versão disponível.

O resultado do método Web de pontos de extremidade é uma matriz de registros com cada registro representado um conjunto de pontos de extremidade. Os elementos de cada registro são:

- id — O número de ID imutável do conjunto de pontos de extremidade.
- serviceArea — A área de serviço que faz parte do: _Common_, _Exchange_, _SharePoint_ ou _Skype_.
- urls — As URLs do conjunto de pontos de extremidade. Uma matriz JSON de registros DNS. Omitidas caso estejam em branco.
- tcpPorts — As portas TCP para o conjunto de pontos de extremidade. Os elementos de todas as portas são formatados como uma lista separada por vírgulas ou intervalos de portas separados por um hífen (-). As portas se aplicam a todos os endereços IP e todas as URLs do conjunto de pontos de extremidade para essa categoria. Omitidas caso estejam em branco.
- udpPorts — As portas UDP para os intervalos de endereço IP deste conjunto de pontos de extremidade. Omitidas caso estejam em branco.
- ips — Os intervalos de endereço IP associados a esse conjunto de pontos de extremidade conforme associação com as portas TCP ou UDP listadas. Uma matriz JSON de intervalos de endereço IP. Omitidas caso estejam em branco.
- category — A categoria do conjunto de pontos de extremidade. Os valores válidos são _Otimizar_, _Permitir_ e _Padrão_. Se você pesquisar a saída do método Web de pontos de extremidade de um endereço IP ou URL específicos, é possível que sua consulta retornará várias categorias. Nesse caso, siga a recomendação para a categoria de maior prioridade. Por exemplo, se o ponto de extremidade aparecer tanto em _Otimizar_ quanto em _Permitir_, você deve seguir os requisitos de _Otimizar_. Obrigatório.
- expressRoute — _Verdadeiro_ se esse conjunto de pontos de extremidade é roteado sobre ExpressRoute, caso contrário, _falso_.
- required — _Verdadeiro_ se esse conjunto de pontos de extremidade precisar de conectividade com o Office 365 para ter suporte. _Falso_ se o conjunto de pontos de extremidade for opcional.
- notes — Para pontos de extremidade opcionais, este texto descreve a funcionalidade do Office 365 que não estará disponível se os endereços IP ou URLs deste conjunto de pontos de extremidade não puderem ser acessados na camada de rede. Omitidas caso estejam em branco.

### <a name="examples"></a>Exemplos:

Exemplo 1 de URI de solicitação: [https://endpoints.office.com/endpoints/Worldwide?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/endpoints/Worldwide?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)

Esse URI obtém todos os pontos de extremidade da instância do Office 365 em todo o mundo para todas as cargas de trabalho. Exemplo de resultado mostrando um trecho da saída:

```json
[
 {
  "id": 1,
  "serviceArea": "Exchange",
  "serviceAreaDisplayName": "Exchange Online",
  "urls":
   [
    "*.protection.outlook.com"
   ],
  "ips":
   [
    "2a01:111:f403::/48", "23.103.132.0/22", "23.103.136.0/21", "23.103.198.0/23", "23.103.212.0/22", "40.92.0.0/14", "40.107.0.0/17", "40.107.128.0/18", "52.100.0.0/14", "213.199.154.0/24", "213.199.180.128/26", "94.245.120.64/26", "207.46.163.0/24", "65.55.88.0/24", "216.32.180.0/23", "23.103.144.0/20", "65.55.169.0/24", "207.46.100.0/24", "2a01:111:f400:7c00::/54", "157.56.110.0/23", "23.103.200.0/22", "104.47.0.0/17", "2a01:111:f400:fc00::/54", "157.55.234.0/24", "157.56.112.0/24", "52.238.78.88/32"
   ],
  "tcpPorts": "443",
  "expressRoute": true,
  "category": "Allow"
 },
 {
  "id": 2,
  "serviceArea": "Exchange",
  "serviceAreaDisplayName": "Exchange Online",
  "urls":
   [
    "*.mail.protection.outlook.com"
   ],
```

Note que a saída completa da solicitação neste exemplo conteria outros conjuntos de pontos de extremidade.

Exemplo 2 de URI de solicitação: [https://endpoints.office.com/endpoints/Worldwide?ServiceAreas=Exchange&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/endpoints/Worldwide?ServiceAreas=Exchange&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)

Esse exemplo obtém pontos de extremidade da instância do Office 365 em todo o mundo apenas para o Exchange Online e dependências.

A saída para o exemplo 2 é semelhante ao do exemplo 1, exceto que os resultados não incluirão pontos de extremidade do SharePoint Online ou do Skype for Business Online.

## <a name="changes-web-method"></a>Método Web de alterações

O método Web de alterações retorna as atualizações mais recentes publicadas, normalmente as alterações do mês anterior de URLs e dos intervalos de endereços IP.

As alterações mais importantes em dados de pontos de extremidade são novos endereços de URL e de IP. Falha ao adicionar um endereço de IP a uma lista de controle de acesso do firewall a um lista de bypass de servidores proxy pode causar uma interrupção para usuários do Office 365 por trás desse dispositivo de rede. Apesar dos requisitos operacionais, novos pontos de extremidade são publicados no serviço Web 30 dias antes da data que os pontos de extremidades são provisionados para uso para lhe dar tempo de atualizar listas de controle de acesso e listas de bypass de servidores proxy.

O parâmetro necessário para o método da web de alterações é:

- **Version=\<YYYYMMDDNN>** — Parâmetro de rota URL obrigatório. Este valor é a versão que você tem implementada atualmente. O serviço da Web retornará as alterações desde essa versão. O formato é _YYYYMMDDNN_, em que _NN_ é um número natural incrementado, se houver várias versões que precisem ser publicadas em um único dia, com _00_ representando a primeira atualização de um determinado dia. O serviço da web requer que o parâmetro de _versão_ contenha exatamente 10 dígitos.

O método da Web de alterações é limitado por taxa da mesma forma que o método da web de pontos de extremidade. Se você receber um código de resposta HTTP 429, espere 1 hora antes de repetir sua solicitação ou para gerar um novo GUID para a solicitação.

O resultado do método Web de alterações é uma matriz de registros em que cada registro representa uma alteração em uma versão específica dos pontos de extremidade. Os elementos de cada registro são:

- id — A ID imutável do registro de alterações.
- endpointSetId — O ID do registro do conjunto de pontos de extremidade que é alterado.
- disposition — Descreve o que a alteração fez com o registro do conjunto de pontos de extremidade. Os valores são _alterar_, _adicionar_ ou _remover_.
- impact — Nem todas as alterações serão igualmente importantes para todos os ambientes. Isso descreve o impacto esperado para um ambiente de perímetro de rede corporativa como resultado dessa alteração. Este elemento está incluído apenas nos registros de alterações da versão **2018112800** e posterior. As opções para o impacto são: — AddedIp – Um endereço de IP foi adicionado ao Office 365 e estará ativo no serviço em breve. Isso representa uma alteração que você precisa realizar em um firewall ou em outro dispositivo de perímetro de rede de camada 3. Se você não adicionar isso antes de começar a usá-lo, talvez haja uma interrupção.
  — AddedUrl – Uma URL foi adicionada ao Office 365 e estará ativa no serviço em breve. Isso representa uma mudança que você precisa fazer em um servidor de proxy ou dispositivo de perímetro de rede de análise de URL. Se você não adicionar esta URL antes de usá-la, talvez haja uma interrupção.
  — AddedIpAndUrl — Um endereço de IP e URL foram adicionados. Isso representa uma alteração que você precisa realizar em um dispositivo de camada 3 de firewall ou em um servidor proxy ou dispositivo de análise da URL. Se você não adicionar esse par IP/URL antes de começar a usá-lo, você pode observar uma interrupção.
  — RemovedIpOrUrl – Pelo menos um endereço IP ou URL foi removido do Office 365. Remover os pontos de extremidade de rede nos seus dispositivos de perímetro, mas não há nenhuma data limite para você fazer isso.
  — ChangedIsExpressRoute – O atributo de suporte do ExpressRoute foi modificado. Se você usar o ExpressRoute será necessário tomar medidas dependendo da configuração.
  — MovedIpOrUrl – Movemos um endereço IP ou uma Url entre esse conjunto de ponto de extremidade e outro. Geralmente, nenhuma ação é necessária.
  — RemovedDuplicateIpOrUrl – Removemos um endereço IP ou uma URL duplicados, mas ele ainda é publicado para o Office 365. Geralmente, nenhuma ação é necessária.
  — OtherNonPriorityChanges – Alteramos algo menos crítico que todas as opções como um campo de anotações.
- version — A versão do conjunto de pontos de extremidade em que a alteração foi introduzida. Os números de versões estão no formato _YYYYMMDDNN_, em que _NN_ é um número natural incrementado caso existam várias versões a serem publicadas em um único dia.
- previous — Uma subestrutura detalhando os valores anteriores de elementos alterados no conjunto de pontos de extremidade. Isso não será incluído para conjuntos de pontos de extremidade recém-adicionados. Inclui _ExpressRoute_, _serviceArea_, _category_, _required_, _tcpPorts_, _udpPorts_ e _notes_.
- current — Uma subestrutura detalhando valores atualizados de elementos de alterações no conjunto de pontos de extremidade. Inclui _ExpressRoute_, _serviceArea_, _category_, _required_, _tcpPorts_, _udpPorts_ e _notes_.
- add — Uma subestrutura que detalha os itens a serem adicionados às coleções do conjunto de pontos de extremidade. Omitida caso não haja nenhuma adição.
  — effectiveDate — Define os dados de quando as adições estarão disponíveis no serviço.
  — ips — Itens a serem adicionados à matriz _ips_.
  — urls- Itens a serem adicionados à matriz _urls_. 
- remove — Uma subestrutura detalhando itens a serem removidos do conjunto de pontos de extremidade. Omitido se não houver remoções.
  — ips — Itens a serem removidos da matriz _ips_.
  — urls- Itens a serem removidos da matriz _urls_. 

### <a name="examples"></a>Exemplos:

Exemplo 1 de URI de solicitação: [https://endpoints.office.com/changes/worldwide/0000000000?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/changes/worldwide/0000000000?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)

Solicita todas as alterações anteriores da instância do serviço do Office 365 em todo o mundo. Exemplo de resultado:

```json
[
 {
  "id": 424,
  "endpointSetId": 32,
  "disposition": "Change",
  "version": "2018062700",
  "remove":
   {
    "urls":
     [
      "*.api.skype.com", "skypegraph.skype.com"
     ]
   }
 },
 {
  "id": 426,
  "endpointSetId": 31,
  "disposition": "Change",
  "version": "2018062700",
  "add":
   {
    "effectiveDate": "20180609",
    "ips":
     [
      "51.140.203.190/32"
     ]
   },
  "remove":
   {
    "ips":
     [
```

Exemplo 2 de URI de solicitação: [https://endpoints.office.com/changes/worldwide/2018062700?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/changes/worldwide/2018062700?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)

Solicita as alterações desde a versão especificada da instância do Office 365 em todo o mundo. Nesse caso, a versão especificada é a mais recente. Exemplo de resultado:

```json
[
  {
    "id":3,
    "endpointSetId":33,
    "changeDescription":"Removing old IP prefixes",
    "disposition":"Change",
    "version":"2018031301",
    "remove":{
      "ips":["65.55.127.0/24","66.119.157.192/26","66.119.158.0/25",
      "111.221.76.128/25","111.221.77.0/26","207.46.5.0/24"]
    }
  },
  {
    "id":4,
    "endpointSetId":45,
    "changeDescription":"Removing old IP prefixes",
    "disposition":"Change",
    "version":"2018031301",
    "remove":{
      "ips":["13.78.93.8/32","40.113.87.220/32","40.114.149.220/32",
      "40.117.100.83/32","40.118.214.164/32","104.208.31.113/32"]
    }
  }
]
```

## <a name="example-powershell-script"></a>Exemplo de script do PowerShell

Você pode executar esse script do PowerShell para ver se há ações que você precisa tomar para os dados atualizados. Você pode executar esse script como uma tarefa agendada para verificar se há uma atualização da versão. Para evitar a carga excessiva no serviço Web, tente não executar o script mais do que uma vez por hora.

O script faz o seguinte:

- Verifica o número da versão dos pontos de extremidade da instância do Office 365 Worldwide, chamando a API REST do serviço Web.
- Verifica uma versão do arquivo atual em _$Env:TEMP\O365_endpoints_latestversion.txt_. O caminho da variável global **$Env:TEMP** normalmente é _C:\Users\\<username\>\AppData\Local\Temp_.
- Se esta é a primeira vez que o script é executado, o script retorna a versão atual e todos os endereços IP e URLs atuais, grava a versão de pontos de extremidade no arquivo _$Env:TEMP\O365_endpoints_latestversion.txt_ e a saída de dados dos pontos de extremidade para o arquivo _$Env:TEMP\O365_endpoints_data.txt_. Você pode modificar o caminho e/ou o nome do arquivo de saída editando estas linhas:

    ``` powershell
    $versionpath = $Env:TEMP + "\O365_endpoints_latestversion.txt"
    $datapath = $Env:TEMP + "\O365_endpoints_data.txt"
    ```

- Em cada execução subsequente do script, se a versão mais recente do serviço Web for idêntica à versão do arquivo _O365_endpoints_latestversion.txt_, o script sairá sem fazer alterações.
- Quando a versão mais recente do serviço Web é mais recente do que a versão do arquivo _O365_endpoints_latestversion.txt_, o script retorna os pontos de extremidade e os filtros para a categoria de pontos de extremidade **Permitir** e **Otimizar**, atualiza a versão no arquivo _O365_endpoints_latestversion.txt_ e grava os dados atualizados no arquivo _O365_endpoints_data.txt_.

O script gera um _ClientRequestId_ exclusivo para o computador em que ele é executado e reutiliza essa ID em várias chamadas. Essa ID é armazenada no arquivo _O365_endpoints_latestversion.txt_.

### <a name="to-run-the-powershell-script"></a>Para executar o script do PowerShell

1. Copie o script e salve-o no seu disco rígido local ou no local do script como _Get-O365WebServiceUpdates.ps1_.
1. Execute o script em seu editor de script preferido, como o ISE do PowerShell ou o VS Code, ou de um consolo do PowerShell usando o seguinte comando:

    ``` powershell
   powershell.exe -file <path>\Get-O365WebServiceUpdates.ps1
    ```

    Não há parâmetros para passar para o script.

```powershell
<# Get-O365WebServiceUpdates.ps1
From https://aka.ms/ipurlws
v1.1 8/6/2019

DESCRIPTION
This script calls the REST API of the Office 365 IP and URL Web Service (Worldwide instance)
and checks to see if there has been a new update since the version stored in an existing
$Env:TEMP\O365_endpoints_latestversion.txt file in your user directory's temp folder
(usually C:\Users\<username>\AppData\Local\Temp).
If the file doesn't exist, or the latest version is newer than the current version in the
file, the script returns IPs and/or URLs that have been changed, added or removed in the latest
update and writes the new version and data to the output file $Env:TEMP\O365_endpoints_data.txt.

USAGE
Run as a scheduled task every 60 minutes.

PARAMETERS
n/a

PREREQUISITES
PS script execution policy: Bypass
PowerShell 3.0 or later
Does not require elevation
#>

#Requires -Version 3.0

# web service root URL
$ws = "https://endpoints.office.com"
# path where output files will be stored
$versionpath = $Env:TEMP + "\O365_endpoints_latestversion.txt"
$datapath = $Env:TEMP + "\O365_endpoints_data.txt"

# fetch client ID and version if version file exists; otherwise create new file and client ID
if (Test-Path $versionpath) {
    $content = Get-Content $versionpath
    $clientRequestId = $content[0]
    $lastVersion = $content[1]
    Write-Output ("Version file exists! Current version: " + $lastVersion)
}
else {
    Write-Output ("First run! Creating version file at " + $versionpath + ".")
    $clientRequestId = [GUID]::NewGuid().Guid
    $lastVersion = "0000000000"
    @($clientRequestId, $lastVersion) | Out-File $versionpath
}

# call version method to check the latest version, and pull new data if version number is different
$version = Invoke-RestMethod -Uri ($ws + "/version/Worldwide?clientRequestId=" + $clientRequestId)
if ($version.latest -gt $lastVersion) {
    Write-Host "New version of Office 365 worldwide commercial service instance endpoints detected"
    # write the new version number to the version file
    @($clientRequestId, $version.latest) | Out-File $versionpath
    # invoke endpoints method to get the new data
    $endpointSets = Invoke-RestMethod -Uri ($ws + "/endpoints/Worldwide?clientRequestId=" + $clientRequestId)
    # filter results for Allow and Optimize endpoints, and transform these into custom objects with port and category
    # URL results
    $flatUrls = $endpointSets | ForEach-Object {
        $endpointSet = $_
        $urls = $(if ($endpointSet.urls.Count -gt 0) { $endpointSet.urls } else { @() })
        $urlCustomObjects = @()
        if ($endpointSet.category -in ("Allow", "Optimize")) {
            $urlCustomObjects = $urls | ForEach-Object {
                [PSCustomObject]@{
                    category = $endpointSet.category;
                    url      = $_;
                    tcpPorts = $endpointSet.tcpPorts;
                    udpPorts = $endpointSet.udpPorts;
                }
            }
        }
        $urlCustomObjects
    }
    # IPv4 results
    $flatIp4s = $endpointSets | ForEach-Object {
        $endpointSet = $_
        $ips = $(if ($endpointSet.ips.Count -gt 0) { $endpointSet.ips } else { @() })
        # IPv4 strings contain dots
        $ip4s = $ips | Where-Object { $_ -like '*.*' }
        $ip4CustomObjects = @()
        if ($endpointSet.category -in ("Allow", "Optimize")) {
            $ip4CustomObjects = $ip4s | ForEach-Object {
                [PSCustomObject]@{
                    category = $endpointSet.category;
                    ip = $_;
                    tcpPorts = $endpointSet.tcpPorts;
                    udpPorts = $endpointSet.udpPorts;
                }
            }
        }
        $ip4CustomObjects
    }
    # IPv6 results
    $flatIp6s = $endpointSets | ForEach-Object {
        $endpointSet = $_
        $ips = $(if ($endpointSet.ips.Count -gt 0) { $endpointSet.ips } else { @() })
        # IPv6 strings contain colons
        $ip6s = $ips | Where-Object { $_ -like '*:*' }
        $ip6CustomObjects = @()
        if ($endpointSet.category -in ("Optimize")) {
            $ip6CustomObjects = $ip6s | ForEach-Object {
                [PSCustomObject]@{
                    category = $endpointSet.category;
                    ip = $_;
                    tcpPorts = $endpointSet.tcpPorts;
                    udpPorts = $endpointSet.udpPorts;
                }
            }
        }
        $ip6CustomObjects
    }

    # write output to screen
    Write-Output ("Client Request ID: " + $clientRequestId)
    Write-Output ("Last Version: " + $lastVersion)
    Write-Output ("New Version: " + $version.latest)
    Write-Output ""
    Write-Output "IPv4 Firewall IP Address Ranges"
    ($flatIp4s.ip | Sort-Object -Unique) -join "," | Out-String
    Write-Output "IPv6 Firewall IP Address Ranges"
    ($flatIp6s.ip | Sort-Object -Unique) -join "," | Out-String
    Write-Output "URLs for Proxy Server"
    ($flatUrls.url | Sort-Object -Unique) -join "," | Out-String
    Write-Output ("IP and URL data written to " + $datapath)

    # write output to data file
    Write-Output "Office 365 IP and UL Web Service data" | Out-File $datapath
    Write-Output "Worldwide instance" | Out-File $datapath -Append
    Write-Output "" | Out-File $datapath -Append
    Write-Output ("Version: " + $version.latest) | Out-File $datapath -Append
    Write-Output "" | Out-File $datapath -Append
    Write-Output "IPv4 Firewall IP Address Ranges" | Out-File $datapath -Append
    ($flatIp4s.ip | Sort-Object -Unique) -join "," | Out-File $datapath -Append
    Write-Output "" | Out-File $datapath -Append
    Write-Output "IPv6 Firewall IP Address Ranges" | Out-File $datapath -Append
    ($flatIp6s.ip | Sort-Object -Unique) -join "," | Out-File $datapath -Append
    Write-Output "" | Out-File $datapath -Append
    Write-Output "URLs for Proxy Server" | Out-File $datapath -Append
    ($flatUrls.url | Sort-Object -Unique) -join "," | Out-File $datapath -Append
}
else {
    Write-Host "Office 365 worldwide commercial service instance endpoints are up-to-date."
}
```

## <a name="example-python-script"></a>Exemplo de script do Python

Esse é um script do Python, testado com o Python 3.6.3 no Windows 10, que você pode executar para ver se há ações que você precisa realizar em relação aos dados atualizados. Esse script verifica o número da versão dos pontos de extremidade de instâncias do Office 365 em todo o mundo. Quando houver uma alteração, ele baixará os pontos de extremidade e os filtros dos pontos de extremidade das categorias _Permitir_ e _Otimizar_. Ele também usa um ClientRequestId exclusivo em várias chamadas e salva a última versão encontrada em um arquivo temporário. Você deve chamar esse script uma vez por hora para verificar se há alguma atualização da versão.

```python
import json
import tempfile
from pathlib import Path
import urllib.request
import uuid
# helper to call the webservice and parse the response
def webApiGet(methodName, instanceName, clientRequestId):
    ws = "https://endpoints.office.com"
    requestPath = ws + '/' + methodName + '/' + instanceName + '?clientRequestId=' + clientRequestId
    request = urllib.request.Request(requestPath)
    with urllib.request.urlopen(request) as response:
        return json.loads(response.read().decode())
# path where client ID and latest version number will be stored
datapath = Path(tempfile.gettempdir() + '/endpoints_clientid_latestversion.txt')
# fetch client ID and version if data exists; otherwise create new file
if datapath.exists():
    with open(datapath, 'r') as fin:
        clientRequestId = fin.readline().strip()
        latestVersion = fin.readline().strip()
else:
    clientRequestId = str(uuid.uuid4())
    latestVersion = '0000000000'
    with open(datapath, 'w') as fout:
        fout.write(clientRequestId + '\n' + latestVersion)
# call version method to check the latest version, and pull new data if version number is different
version = webApiGet('version', 'Worldwide', clientRequestId)
if version['latest'] > latestVersion:
    print('New version of Office 365 worldwide commercial service instance endpoints detected')
    # write the new version number to the data file
    with open(datapath, 'w') as fout:
        fout.write(clientRequestId + '\n' + version['latest'])
    # invoke endpoints method to get the new data
    endpointSets = webApiGet('endpoints', 'Worldwide', clientRequestId)
    # filter results for Allow and Optimize endpoints, and transform these into tuples with port and category
    flatUrls = []
    for endpointSet in endpointSets:
        if endpointSet['category'] in ('Optimize', 'Allow'):
            category = endpointSet['category']
            urls = endpointSet['urls'] if 'urls' in endpointSet else []
            tcpPorts = endpointSet['tcpPorts'] if 'tcpPorts' in endpointSet else ''
            udpPorts = endpointSet['udpPorts'] if 'udpPorts' in endpointSet else ''
            flatUrls.extend([(category, url, tcpPorts, udpPorts) for url in urls])
    flatIps = []
    for endpointSet in endpointSets:
        if endpointSet['category'] in ('Optimize', 'Allow'):
            ips = endpointSet['ips'] if 'ips' in endpointSet else []
            category = endpointSet['category']
            # IPv4 strings have dots while IPv6 strings have colons
            ip4s = [ip for ip in ips if '.' in ip]
            tcpPorts = endpointSet['tcpPorts'] if 'tcpPorts' in endpointSet else ''
            udpPorts = endpointSet['udpPorts'] if 'udpPorts' in endpointSet else ''
            flatIps.extend([(category, ip, tcpPorts, udpPorts) for ip in ip4s])
    print('IPv4 Firewall IP Address Ranges')
    print(','.join(sorted(set([ip for (category, ip, tcpPorts, udpPorts) in flatIps]))))
    print('URLs for Proxy Server')
    print(','.join(sorted(set([url for (category, url, tcpPorts, udpPorts) in flatUrls]))))

    # TODO send mail (e.g. with smtplib/email modules) with new endpoints data
else:
    print('Office 365 worldwide commercial service instance endpoints are up-to-date')
```

## <a name="web-service-interface-versioning"></a>Controle de versão de interface do serviço da Web

As atualizações dos parâmetros ou resultados para esses métodos de serviço Web podem ser necessárias no futuro. Após a publicação da disponibilidade geral desses serviços Web, a Microsoft tomará medidas razoáveis para oferecer um aviso prévio de atualizações de material para o serviço Web. Quando a Microsoft acredita que uma atualização exigirá mudanças aos clientes usando o serviço Web, a Microsoft manterá a versão anterior (uma versão mais antiga) do serviço Web disponível por pelo menos 12 meses após o lançamento da nova versão. Os clientes que não atualizarem durante esse período poderão não acessar o serviço Web e seus métodos. Os clientes devem garantir que os clientes do serviço Web continuem funcionando sem erro se as seguintes alterações forem feitas na assinatura da interface do serviço Web:

- Adição de um novo parâmetro opcional a um método Web existente que não precise ser fornecido por clientes mais antigos e que não afete os resultados recebidos por um cliente mais antigo.
- Adição de um novo atributo nomeado em um dos itens do REST de resposta ou em colunas adicionais para o CSV de resposta.
- Adição de um novo método Web com um novo nome que não é chamado pelos clientes mais antigos.

## <a name="update-notifications"></a>Notificações de atualização

Você pode usar alguns métodos diferentes para obter notificações por email quando as alterações nos endereços IP e URLs forem publicadas no serviço Web.

- Para usar uma solução Microsoft Flow, consulte [Usar o Microsoft Flow para receber um email de alterações com em endereços IP e URLs do Office 365](https://techcommunity.microsoft.com/t5/Office-365-Networking/Use-Microsoft-Flow-to-receive-an-email-for-changes-to-Office-365/m-p/240651).
- Para implantar um Aplicativo Lógico do Azure usando um modelo ARM, confira [Notificação de atualização do Office 365 (v1.1)](https://aka.ms/ipurlws-updates-template).
- Para escrever um script usando o PowerShell, confira [Send-MailMessage](/powershell/module/microsoft.powershell.utility/send-mailmessage).

## <a name="exporting-a-proxy-pac-file"></a>Exportando um arquivo Proxy PAC

[Get-PacFile](https://www.powershellgallery.com/packages/Get-PacFile) é um script do PowerShell que lê os pontos de extremidade de rede mais recentes da URL do serviço Web e endereço IP do Office 365 e a criação de uma amostra de um arquivo PAC. Para saber mais sobre como usar Get-PacFile, confira [Usar um arquivo PAC para o roteamento direto do tráfego vital o Office 365](managing-office-365-endpoints.md#use-a-pac-file-for-direct-routing-of-vital-office-365-traffic).

## <a name="related-topics"></a>Tópicos Relacionados
  
[URLs e intervalos de endereços IP do Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

[Gerenciar pontos de extremidade do Office 365](managing-office-365-endpoints.md)
  
[Perguntas frequentes sobre pontos de extremidade do Office 365](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)

[Princípios de conectividade de rede do Office 365](microsoft-365-network-connectivity-principles.md)

[Rede do Office 365 e ajuste de desempenho](network-planning-and-performance.md)

[Avaliando a conectividade de rede do Office 365](assessing-network-connectivity.md)
  
[Qualidade da mídia e desempenho de conectividade de rede no Skype for Business Online](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
  
[Como otimizar a sua rede para o Skype for Business Online](https://support.office.com/article/b363bdca-b00d-4150-96c3-ec7eab5a8a43)

[Ajuste de desempenho do Office 365 usando linhas de base e histórico de desempenho](performance-tuning-using-baselines-and-history.md)
  
[Plano de solução de problemas de desempenho do Office 365](performance-troubleshooting-plan.md)