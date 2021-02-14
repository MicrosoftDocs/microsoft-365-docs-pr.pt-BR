---
title: Solicitações de rede do Office para Mac
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/9/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365_Setup
- seo-marvel-apr2020
search.appverid: MOM160
ms.assetid: afdae969-4046-44b9-9adb-f1bab216414b
description: Este artigo descreve quais pontos de extremidade e URLs os aplicativos do Office para Mac tentam alcançar e os serviços fornecidos.
ms.openlocfilehash: b777b4ea7e03495cb6389be8fe05e96a26fd9664
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687235"
---
# <a name="network-requests-in-office-for-mac"></a>Solicitações de rede do Office para Mac

Os aplicativos do Office para Mac fornecem uma experiência de aplicativo nativa na plataforma macOS. Cada aplicativo foi projetado para funcionar em uma variedade de cenários, incluindo estados quando não há acesso à rede disponível. Quando um computador está conectado a uma rede, os aplicativos se conectam automaticamente a uma série de serviços baseados na Web para fornecer funcionalidade aprimorada. As informações a seguir descrevem quais pontos de extremidade e URLs os aplicativos tentam alcançar e os serviços fornecidos. Essas informações são úteis ao solucionar problemas de configuração de rede e definir políticas para servidores proxy de rede. Os detalhes neste artigo destinam-se a complementar o artigo de intervalos de endereços e URL do [Office 365,](urls-and-ip-address-ranges.md)que inclui pontos de extremidade para computadores que executam o Microsoft Windows. A menos que seja registrado, as informações neste artigo também se aplicarão ao Office 2019 para Mac e ao Office 2016 para Mac, que estão disponíveis como uma compra única em uma loja de varejo ou por meio de um contrato de licenciamento por volume. 

  
A maioria deste artigo é de tabelas que detalham URLs de rede, tipo e descrição de serviço ou recurso fornecidos por esse ponto de extremidade. Cada um dos aplicativos do Office pode diferir em seu uso de serviço e ponto de extremidade. Os seguintes aplicativos são definidos nas tabelas abaixo:
  
- W: Word
- P: PowerPoint
- X: Excel
- O: Outlook
- N: OneNote
   
O tipo de URL é definido da seguinte forma:
  
- ST: Estático - A URL é codificada no aplicativo cliente.
    
- SS: Semi-Static - a URL é codificada como parte de uma página da Web ou redirecionador.
    
- CS: Serviço de Configuração - a URL é retornada como parte do Serviço de Configuração do Office.

    
## <a name="office-for-mac-default-configuration"></a>Configuração padrão do Office para Mac

 **Instalação e atualizações**
  
Os pontos de extremidade de rede a seguir são usados para baixar o programa de instalação do Office para Mac da CDN (Rede de Distribuição de Conteúdo) da Microsoft.
  
|**URL**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|```https://go.microsoft.com/fwlink/```  <br/> |ST  <br/> |Serviço de link de encaminhamento do Portal de Instalação do Microsoft 365 para os pacotes de instalação mais recentes.  <br/> |
|```https://officecdn-microsoft-com.akamaized.net/```  <br/> |SS  <br/> |Local dos pacotes de instalação na Rede de Distribuição de Conteúdo.  <br/> |
|```https://officecdn.microsoft.com/```  <br/> |SS  <br/> |Local dos pacotes de instalação na Rede de Distribuição de Conteúdo.  <br/> |
|```https://officeci-mauservice.azurewebsites.net/```  <br/> |ST  <br/> |Ponto de extremidade de Controle de Gerenciamento do Microsoft AutoUpdate  <br/> |
   
 **Primeira iniciação do aplicativo**
  
Os pontos de extremidade de rede a seguir são contatados na primeira iniciação de um aplicativo do Office. Esses pontos de extremidade fornecem funcionalidade aprimorada do Office para os usuários, e as URLs são contatas independentemente do tipo de licença (incluindo instalações de Licença de Volume).
  
|**URL**|**Aplicativos**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
|```https://config.edge.skype.com/```  <br/> |WXPON  <br/> |ST  <br/> |Configuração de "voo" - permite a a luz do recurso e experimentação.  <br/> |
|```https://ocos-office365-s2s.msedge.net/```  <br/> |WXPON  <br/> |ST  <br/> |Teste de configuração de rede de "voo"  <br/> |
|```https://client-office365-tas.msedge.net/```  <br/> |WXPON  <br/> |ST  <br/> |Teste de configuração de rede de "voo"  <br/> |
|```https://officeclient.microsoft.com/```  <br/> |WXPON  <br/> |ST  <br/> |Serviço de Configuração do Office - Lista mestra de pontos de extremidade de serviço.  <br/> |
|```https://nexusrules.officeapps.live.com/```  <br/> |WXPON  <br/> |ST  <br/> |Download de Telemetria de Regras do Office - Informa o cliente sobre quais dados e eventos carregar no serviço de telemetria.  <br/> |
|```https://mobile.pipe.aria.microsoft.com/```  <br/> |N  <br/> |CS  <br/> |Serviço de Telemetria do OneNote  <br/> |
|```https://nexus.officeapps.live.com/```  <br/> |WXPON  <br/> |ST  <br/> |Relatório de Carregamento de Telemetria do Office - "Heart timet" e eventos de erro que ocorrem no cliente são carregados para o serviço de telemetria.  <br/> |
|```https://templateservice.office.com/```  <br/> |WXP  <br/> |CS  <br/> |Serviço de Modelo do Office - Fornece aos usuários modelos de documento online.  <br/> |
|```https://omextemplates.content.office.net/```  <br/> |WXP  <br/> |CS  <br/> |Downloads de modelos do Office - Armazenamento de imagens de modelo PNG.  <br/> |
|```https://store.office.com/```  <br/> |WXP  <br/> |CS  <br/> |Configuração da Loja para aplicativos do Office.  <br/> |
|```https://odc.officeapps.live.com/```  <br/> |WXPN  <br/> |CS  <br/> |Catálogo de Serviços de Integração de Documentos do Office (lista de serviços e pontos de extremidade) e Descoberta de Realm Inicial.  <br/> |
|```https://cdn.odc.officeapps.live.com/```  <br/> |WXPON  <br/> |CS  <br/> |Recursos para Descoberta de Realm Inicial v2 (15.40 e posterior)  <br/> |
|```https://officecdn.microsoft.com/```  <br/> |WXPON  <br/> |ST  <br/> |Manifestos do Microsoft AutoUpdate – verifica se há atualizações disponíveis  <br/> |
|```https://ajax.aspnetcdn.com/```  <br/> |WXPO  <br/> |SS  <br/> |Biblioteca JavaScript do Microsoft Ajax  <br/> |
|```https://wikipedia.firstpartyapps.oaspapps.com/```  <br/> |W  <br/> |SS  <br/> |Aplicativo Wikipédia para recursos e configuração do Office.  <br/> |
|```https://excelbingmap.firstpartyapps.oaspapps.com/```  <br/> |X  <br/> |SS  <br/> |Aplicativo Bing Map para recursos e configuração do Office.  <br/> |
|```https://peoplegraph.firstpartyapps.oaspapps.com/```  <br/> |X  <br/> |SS  <br/> |Aplicativo Pessoas do Graph para recursos e configuração do Office.  <br/> |
|```https://www.onenote.com/```  <br/> |N  <br/> |ST  <br/> |O que há de novo no conteúdo do OneNote.  <br/> |
|```https://site-cdn.onenote.net/```  <br/> |N  <br/> |ST  <br/> |Novo conteúdo para o OneNote.  <br/> |
|```https://site-cdn.onenote.net/```  <br/> |N  <br/> |SS  <br/> |O que há de novo nas imagens do OneNote.  <br/> |
|```https://acompli.helpshift.com/```  <br/> |O  <br/> |ST  <br/> |Serviço de Suporte no aplicativo.  <br/> |
|```https://prod-global-autodetect.acompli.net/```  <br/> |O  <br/> |ST  <br/> |Serviço de Detecção de Conta de Email.  <br/> |
|```https://autodiscover-s.outlook.com/```  <br/> |WXPO  <br/> |ST  <br/> |Descoberta Automática do Outlook  <br/> |
|```https://outlook.office365.com/```  <br/> |WXPO  <br/> |ST  <br/> |Ponto de extremidade do Outlook para o serviço do Microsoft 365.  <br/> |
|```https://r1.res.office365.com/```  <br/> |O  <br/> |ST  <br/> |Ícones para os complementos do Outlook.  <br/> |
   
> [!NOTE]
> O Serviço de Configuração do Office atua como um serviço de descoberta automática para todos os clientes do Microsoft Office, não apenas para Mac. Os pontos de extremidade retornados na resposta são semiestticos porque a alteração é muito pouco frequente, mas ainda é possível. 
  
 **Entrar**
  
Os pontos de extremidade de rede a seguir são contatados ao entrar no armazenamento baseado em nuvem. Dependendo do tipo de conta, diferentes serviços podem ser contatados. Por exemplo:
  
- **MSA: Conta da Microsoft** - normalmente usada para cenários de consumidor e varejo 
    
- **OrgID: Conta da Organização** - normalmente usada para cenários comerciais 
    
|**URL**|**Aplicativos**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
|```https://login.windows.net/```  <br/> |WXPON  <br/> |ST  <br/> |Serviço de Autorização do Windows  <br/> |
|```https://login.microsoftonline.com/```  <br/> |WXPON  <br/> |ST  <br/> |Serviço de Logon do Microsoft 365 (OrgID)  <br/> |
|```https://login.live.com/```  <br/> |WXPON  <br/> |ST  <br/> |Serviço de Logon de Conta da Microsoft (MSA)  <br/> |
|```https://auth.gfx.ms/```  <br/> |WXPON  <br/> |CS  <br/> |Microsoft Account Login Service Helper (MSA)  <br/> |
|```https://secure.aadcdn.microsoftonline-p.com/```  <br/> |WXPON  <br/> |SS  <br/> |Identidade Visual de Logon do Microsoft 365 (OrgID)  <br/> |
|```https://ocws.officeapps.live.com/```  <br/> |WXPN  <br/> |CS  <br/> |Document and Places Storage Locator  <br/> |
|```https://roaming.officeapps.live.com/```  <br/> |WXPN  <br/> |CS  <br/> |Serviço de documento mru (usado mais recentemente)  <br/> |
   
> [!NOTE]
> Para licenças de varejo e baseadas em assinatura, a entrada ativa o produto e permite o acesso a recursos de nuvem, como o OneDrive. Para instalações de Licença de Volume, os usuários ainda são solicitados a entrar (por padrão), mas isso só é necessário para acessar recursos de nuvem, pois o produto já está ativado. 
  
 **Ativação do produto**
  
Os pontos de extremidade de rede a seguir se aplicam às ativações de Assinatura e Licença de Varejo do Microsoft 365. Especificamente, isso NÃO se aplica a instalações de Licença de Volume.
  
|**URL**|**Aplicativos**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
|```https://ols.officeapps.live.com/```  <br/> |WXPON  <br/> |CS  <br/> |Serviço de Licenciamento do Office  <br/> |
   
 **Conteúdo novidades**
  
Os pontos de extremidade de rede a seguir se aplicam somente à Assinatura do Microsoft 365.
  
|**URL**|**Aplicativos**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
|```https://contentstorage.osi.office.net/```  <br/> |WXPO  <br/> |SS  <br/> |Conteúdo da página JSON Novidades.  <br/> |
   
 **Pesquisador**
  
Os pontos de extremidade de rede a seguir se aplicam somente à Assinatura do Microsoft 365.
  
|**URL**|**Aplicativos**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
|```https://entity.osi.office.net/```  <br/> |W  <br/> |CS  <br/> |Serviço Web do Pesquisador  <br/> |
|```https://cdn.entity.osi.office.net/```  <br/> |W  <br/> |CS  <br/> |Conteúdo estático do Pesquisador  <br/> |
|```https://www.bing.com/```  <br/> |W  <br/> |CS  <br/> |Provedor de conteúdo do Pesquisador  <br/> |
   
 **Pesquisa Inteligente**
  
Os pontos de extremidade de rede a seguir se aplicam às ativações de Assinatura do Microsoft 365 e de Licença de Varejo/Volume.
  
|**URL**|**Aplicativos**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
|```https://uci.officeapps.live.com/```  <br/> |WXPN  <br/> |CS  <br/> |Serviço Web do Insights  <br/> |
|```https://ajax.googleapis.com/```  <br/> |WXPN  <br/> |CS  <br/> |Biblioteca JQuery  <br/> |
|```https://cdnjs.cloudflare.com/```  <br/> |WXPN  <br/> |CS  <br/> |Suporte à Biblioteca JavaScript  <br/> |
|```https://www.bing.com/```  <br/> |WXPN  <br/> |CS  <br/> |Provedor de Conteúdo do Insights  <br/> |
|```https://tse1.mm.bing.net/```  <br/> |WXPN  <br/> |CS  <br/> |Provedor de Conteúdo do Insights  <br/> |
   
 **Designer do PowerPoint**
  
Os pontos de extremidade de rede a seguir se aplicam somente à Assinatura do Microsoft 365.
  
|**URL**|**Aplicativos**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
|```https://pptsgs.officeapps.live.com/```  <br/> |P  <br/> |CS  <br/> |Serviço Web do PowerPoint Designer  <br/> |
   
 **Iniciador rápido do PowerPoint**
  
Os pontos de extremidade de rede a seguir se aplicam somente à Assinatura do Microsoft 365.
  
|**URL**|**Aplicativos**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
|```https://pptcts.officeapps.live.com/```  <br/> |P  <br/> |CS  <br/> |Serviço Web do Iniciador Rápido do PowerPoint  <br/> |
   
 **Enviar um rosto feliz/rosto feliz**
  
Os pontos de extremidade de rede a seguir se aplicam às ativações de Assinatura do Microsoft 365 e de Licença de Varejo/Volume.
  
|**URL**|**Aplicativos**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
|```https://sas.office.microsoft.com/```  <br/> |WXPON  <br/> |CS  <br/> |Enviar um Serviço de Smile  <br/> |
   
 **Contatar o Suporte**
  
Os pontos de extremidade de rede a seguir se aplicam às ativações de Assinatura do Microsoft 365 e de Licença de Varejo/Volume.
  
|**URL**|**Aplicativos**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
|```https://powerlift-frontdesk.acompli.net/```  <br/> |O  <br/> |CS  <br/> |Contatar o Serviço de Suporte  <br/> |
|```https://acompli.helpshift.com/```  <br/> |O  <br/> |CS  <br/> |Serviço de Suporte no aplicativo  <br/> |
   
 **Salvar como PDF**
  
Os pontos de extremidade de rede a seguir se aplicam às ativações de Assinatura do Microsoft 365 e de Licença de Varejo/Volume.
  
|**URL**|**Aplicativos**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
|```https://wordcs.officeapps.live.com/```  <br/> |W  <br/> |CS  <br/> |Serviço de conversão de documentos do Word (PDF)  <br/> |
   
 **Aplicativos do Office (também conhecidos como complementos)**
  
Os pontos de extremidade de rede a seguir se aplicam às ativações de Assinatura do Microsoft 365 e licença de varejo/volume quando os complementos do aplicativo do Office são confiáveis.
  
|**URL**|**Aplicativos**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
|```https://store.office.com/```  <br/> |WXPO  <br/> |CS  <br/> |Configuração da Loja de Aplicativos do Office  <br/> |
|```https://wikipedia.firstpartyapps.oaspapps.com/```  <br/> |W  <br/> |SS  <br/> |Recursos de aplicativos da Wikipédia  <br/> |
|```https://excelbingmap.firstpartyapps.oaspapps.com/```  <br/> |X  <br/> |SS  <br/> |Recursos de aplicativo do Bing Map  <br/> |
|```https://peoplegraph.firstpartyapps.oaspapps.com```  <br/> |X  <br/> |SS  <br/> |Recursos do aplicativo Pessoas do Graph  <br/> |
|```https://o15.officeredir.microsoft.com/```  <br/> |WPX  <br/> |SS  <br/> |Serviço de Redirecionamento do Office  <br/> |
|```https://appsforoffice.microsoft.com/```  <br/> |WXP  <br/> |SS  <br/> |Bibliotecas JavaScript do Office  <br/> |
|```https://telemetry.firstpartyapps.oaspapps.com/```  <br/> |WX  <br/> |SS  <br/> |Telemetria e Reporting Service para aplicativos do Office  <br/> |
|```https://ajax.microsoft.com/```  <br/> |W  <br/> |SS  <br/> |Biblioteca JavaScript do Microsoft Ajax  <br/> |
|```https://ajax.aspnetcdn.com/```  <br/> |X  <br/> |SS  <br/> |Biblioteca JavaScript do Microsoft Ajax  <br/> |
|```https://c.microsoft.com/```  <br/> |WPXO  <br/> |SS  <br/> |Bibliotecas JavaScript do Office  <br/> |
|```https://c1.microsoft.com/```  <br/> |WPXO  <br/> |SS  <br/> |Recursos de suporte  <br/> |
|```https://cs.microsoft.com/```  <br/> |WPXO  <br/> |SS  <br/> |Recursos de suporte  <br/> |
|```https://c.bing.com/```  <br/> |WPXO  <br/> |SS  <br/> |Recursos de suporte  <br/> |
|```https://*.cdn.optimizely.com/```  <br/> |WPXO  <br/> |SS  <br/> |Biblioteca JavaScript  <br/> |
|```https://errors.client.optimizely.com/```  <br/> |WPX  <br/> |SS  <br/> |Relatório de erros  <br/> |
|```https://*-contentstorage.osi.office.net/```  <br/> |WPXO  <br/> |SS  <br/> |Recursos de fonte  <br/> |
|```https://nexus.ensighten.com/```  <br/> |WPXO  <br/> |SS  <br/> |Serviço de Telemetria  <br/> |
|```https://browser.pipe.aria.microsoft.com/```  <br/> |WPXO  <br/> |SS  <br/> |Relatórios de Telemetria  <br/> |
|```https://*.vo.msecnd.net/```  <br/> |WPXO  <br/> |SS  <br/> |Biblioteca de Ativos da Microsoft Store  <br/> |
|```https://*.wikipedia.org/```  <br/> |W  <br/> |SS  <br/> |Recursos de página da Wikipédia  <br/> |
|```https://upload.wikimedia.org/```  <br/> |W  <br/> |SS  <br/> |Recursos de mídia da Wikipédia  <br/> |
|```https://wikipedia.firstpartyappssandbox.oappseperate.com/```  <br/> |W  <br/> |SS  <br/> |Quadro da área área de trabalho da Wikipédia  <br/> |
|```https://*.virtualearth.net/```  <br/> |X  <br/> |SS  <br/> |Modelos de mapa  <br/> |
   
 **Links Seguros**
  
O ponto de extremidade de rede a seguir aplica-se a todos os aplicativos do Office somente para Assinatura do Microsoft 365.
  
|**URL**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|```https://*.oscs.protection.outlook.com/```  <br/> |CS  <br/> |Serviço de Link Seguro da Microsoft  <br/> |
   
 **Relatório de falhas**
  
O ponto de extremidade de rede a seguir se aplica a todos os aplicativos do Office para ativações de Assinatura do Microsoft 365 e licença de varejo/volume. Quando um processo falha inesperadamente, um relatório é gerado e enviado ao serviço Watson.
  
|**URL**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|```https://watson.microsoft.com/```  <br/> |ST  <br/> |Serviço de Relatório de Erros da Microsoft  <br/> |
|```https://officeci.azurewebsites.net/```  <br/> |ST  <br/> |Serviço Insights Colaborativos do Office  <br/> |
   
## <a name="options-for-reducing-network-requests-and-traffic"></a>Opções para reduzir solicitações de rede e tráfego

A configuração padrão do Office para Mac oferece a melhor experiência do usuário, em termos de funcionalidade e mantendo o computador atualizado. Em alguns cenários, você pode querer impedir que os aplicativos contatem pontos de extremidade de rede. Esta seção discute as opções para fazer isso.
  
 ### <a name="disabling-cloud-sign-in-and-office-add-ins"></a>Desabilitando o Cloud Sign-In e o Office Add-Ins
  
Os clientes de Licença de Volume podem ter políticas estritas sobre como salvar documentos no armazenamento baseado em nuvem. A preferência por aplicativo a seguir pode ser definida para desabilitar a entrada MSA/OrgID e o acesso aos Complementos do Office.
  
- ```defaults write com.microsoft.Word UseOnlineContent -integer 0```

- ```defaults write com.microsoft.Excel UseOnlineContent -integer 0```

- ```defaults write com.microsoft.Powerpoint UseOnlineContent -integer 0```

Se os usuários tentarem acessar a Sign-In, verão um erro de que uma conexão de rede não está presente. Como essa preferência também bloqueia a ativação do produto online, ela só deve ser usada para instalações de Licença de Volume. Especificamente, usar essa preferência impedirá que os aplicativos do Office acessem os seguintes pontos de extremidade:
  
- ```https://odc.officeapps.live.com```
    
- ```https://*.firstpartyapps.oaspapps.com```
    
- Todos os pontos de extremidade listados na seção "Entrar" acima.
    
- Todos os pontos de extremidade listados na seção "Smart Lookup" acima.
    
- Todos os pontos de extremidade listados na seção "Ativação do Produto" acima.
    
- Todos os pontos de extremidade listados na seção "Aplicativos do Office (também conhecidos como complementos)" acima.
    
Para restabelecer a funcionalidade completa para o usuário, de definir a preferência como '2' ou removê-la.
  
> [!NOTE]
> Essa preferência requer o Office para Mac build 15.25 [160726] ou posterior. 
  
### <a name="telemetry"></a>Telemetria
  
O Office para Mac envia informações de telemetria de volta para a Microsoft em intervalos regulares. Os dados são carregados no ponto de extremidade 'Nexus'. Os dados de telemetria ajudam a equipe de engenharia a avaliar a saúde e os comportamentos inesperados de cada aplicativo do Office. Há duas categorias de telemetria:
  
- **A pulsação** contém informações de versão e licença. Esses dados são enviados imediatamente após a iniciação do aplicativo. 
    
- **O** uso contém informações sobre como os aplicativos estão sendo usados e erros não fatais. Esses dados são enviados a cada 60 minutos. 
    
A Microsoft leva sua privacidade muito a sério. Você pode ler sobre a política de coleta de dados da Microsoft em [https://privacy.microsoft.com](https://privacy.microsoft.com) . Para impedir que aplicativos enviem telemetria de "Uso", a preferência **SendAllTelemetryEnabled** pode ser ajustada. A preferência é por aplicativo e pode ser definida por meio dos Perfis de Configuração do macOS ou manualmente no Terminal: 
  
```defaults write com.microsoft.Word SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.Excel SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.Powerpoint SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.Outlook SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.onenote.mac SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.autoupdate2 SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.Office365ServiceV2 SendAllTelemetryEnabled -bool FALSE```

A telemetria de pulsação sempre é enviada e não pode ser desabilitada.
  
### <a name="crash-reporting"></a>Relatório de falhas
  
Quando ocorrer um erro fatal no aplicativo, o aplicativo encerrará inesperadamente e carregará um relatório de falhas no serviço 'Watson'. O relatório de falhas consiste em uma pilha de chamada, que é a lista de etapas que o aplicativo estava processando até a falha. Essas etapas ajudam a equipe de engenharia a identificar a função exata que falhou e por quê.
  
Em alguns casos, o conteúdo de um documento causará uma falha no aplicativo. Se o aplicativo identificar o documento como a causa, ele perguntará ao usuário se não há problema em enviar o documento junto com a pilha de chamada. Os usuários podem fazer uma escolha informada para essa pergunta. Os administradores de IT podem ter requisitos rígidos sobre a transmissão de documentos e tomar a decisão em nome do usuário de nunca enviar documentos. A preferência a seguir pode ser definida para impedir que documentos sejam enviados e suprimir a solicitação para o usuário:
  
```defaults write com.microsoft.errorreporting IsAttachFilesEnabled -bool FALSE```

> [!NOTE]
> Se **SendAllTelemetryEnabled** estiver definido como **FALSO**, todo o relatório de falhas para esse processo será desabilitado. Para habilitar o relatório de falhas sem enviar telemetria de uso, a seguinte preferência pode ser definida: ```defaults write com.microsoft.errorreporting IsMerpEnabled -bool TRUE``` 
  
### <a name="updates"></a>Atualizações
  
A Microsoft lança atualizações do Office para Mac em intervalos regulares (normalmente uma vez por mês). Recomendamos que os usuários e administradores de IT mantenham os máquinas atualizados para garantir que as correções de segurança mais recentes sejam instaladas. Nos casos em que os administradores de IT quiserem controlar e gerenciar atualizações de máquina de perto, a preferência a seguir pode ser definida para impedir que o processo autoUpdate detecte e oferece atualizações de produto automaticamente:
  
```defaults write com.microsoft.autoupdate2 HowToCheck -string 'Manual'```

### <a name="blocking-requests-with-a-firewallproxy"></a>Bloqueio de solicitações com um firewall/proxy
  
Se sua organização bloqueia solicitações para URLs por meio de um firewall ou servidor proxy, configure as URLs listadas neste documento como permitidas ou o bloco listado com uma resposta 40X (por exemplo, 403 ou 404). Uma resposta 40X permitirá que os aplicativos do Office aceitem normalmente a incapacidade de acessar o recurso e fornecerão uma experiência de usuário mais rápida, do que simplesmente soltar a conexão, o que, por sua vez, fará com que o cliente se reestrie.
  
Se o servidor proxy exigir autenticação, uma resposta 407 será retornada ao cliente. Para ter a melhor experiência, certifique-se de que você está usando o Office para Mac builds 15.27 ou posterior, pois eles incluem correções específicas para trabalhar com servidores NTLM e Kerberos.
  
  
## <a name="see-also"></a>Confira também

[URLs e intervalos de endereços IP do Office 365](urls-and-ip-address-ranges.md)

