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

Os aplicativos do Office para Mac oferecem uma experiência de aplicativo nativo na plataforma macOS. Cada aplicativo foi projetado para funcionar em vários cenários, incluindo Estados quando não há acesso à rede disponível. Quando um computador está conectado a uma rede, os aplicativos se conectam automaticamente a uma série de serviços baseados na Web para fornecer funcionalidade aprimorada. As informações a seguir descrevem quais pontos de extremidade e URLs que os aplicativos tentam alcançar e os serviços fornecidos. Essas informações são úteis para solucionar problemas de configuração de rede e definir políticas para servidores de proxy de rede. Os detalhes neste artigo se destinam a complementar o [artigo URL 365 do Office e intervalos de endereços](urls-and-ip-address-ranges.md), que inclui pontos de extremidade para computadores que executam o Microsoft Windows. A menos que indicado, as informações neste artigo também se aplicam ao Office 2019 para Mac e ao Office 2016 para Mac, que estão disponíveis como uma compra única de uma loja de varejo ou por meio de um contrato de licenciamento por volume. 

  
A maior parte deste artigo é tabelas que detalham URLs de rede, tipo e descrição de serviço ou recurso fornecido por esse ponto de extremidade. Cada um dos aplicativos do Office pode ser diferente em seus usos de serviço e ponto de extremidade. Os seguintes aplicativos estão definidos nas tabelas a seguir:
  
- W: Word
- P: PowerPoint
- X: Excel
- O: Outlook
- N: o OneNote
   
O tipo de URL é definido da seguinte maneira:
  
- ST: static-a URL é embutida em código no aplicativo cliente.
    
- SS: semi-estático-a URL é codificada como parte de uma página da Web ou redirecionador.
    
- CS: config Service-a URL é retornada como parte do serviço de configuração do Office.

    
## <a name="office-for-mac-default-configuration"></a>Configuração padrão do Office para Mac

 **Instalação e atualizações**
  
Os pontos de extremidade de rede a seguir são usados para baixar o programa de instalação do Office para Mac da CDN (rede de distribuição de conteúdo) da Microsoft.
  
|**URL**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|```https://go.microsoft.com/fwlink/```  <br/> |CEP  <br/> |Serviço de link avançado do portal de instalação do Microsoft 365 para os pacotes de instalação mais recentes.  <br/> |
|```https://officecdn-microsoft-com.akamaized.net/```  <br/> |PLANILHA  <br/> |Local dos pacotes de instalação na rede de distribuição de conteúdo.  <br/> |
|```https://officecdn.microsoft.com/```  <br/> |PLANILHA  <br/> |Local dos pacotes de instalação na rede de distribuição de conteúdo.  <br/> |
|```https://officeci-mauservice.azurewebsites.net/```  <br/> |CEP  <br/> |Ponto de extremidade de controle de gerenciamento para o Microsoft AutoUpdate  <br/> |
   
 **Início do primeiro aplicativo**
  
Os pontos de extremidade de rede a seguir são contatados na primeira inicialização de um aplicativo do Office. Esses pontos de extremidade fornecem funcionalidade aprimorada do Office para os usuários, e as URLs são contatadas independentemente do tipo de licença (incluindo instalações de licença de volume).
  
|**URL**|**Aplicativos**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
|```https://config.edge.skype.com/```  <br/> |WXPON  <br/> |CEP  <br/> |Configuração de "vôo"-permite a iluminação e a experimentação do recurso.  <br/> |
|```https://ocos-office365-s2s.msedge.net/```  <br/> |WXPON  <br/> |CEP  <br/> |Teste de configuração de rede de "vôo"  <br/> |
|```https://client-office365-tas.msedge.net/```  <br/> |WXPON  <br/> |CEP  <br/> |Teste de configuração de rede de "vôo"  <br/> |
|```https://officeclient.microsoft.com/```  <br/> |WXPON  <br/> |CEP  <br/> |Serviço de configuração do Office-lista mestra de pontos de extremidade de serviço.  <br/> |
|```https://nexusrules.officeapps.live.com/```  <br/> |WXPON  <br/> |CEP  <br/> |Download de telemetria de regras do Office-informa o cliente sobre quais dados e eventos carregar no serviço de telemetria.  <br/> |
|```https://mobile.pipe.aria.microsoft.com/```  <br/> |N  <br/> |CS  <br/> |Serviço de telemetria do OneNote  <br/> |
|```https://nexus.officeapps.live.com/```  <br/> |WXPON  <br/> |CEP  <br/> |Relatório de carregamento de telemetria do Office-"Heartbeart" e eventos de erro que ocorrem no cliente são carregados no serviço de telemetria.  <br/> |
|```https://templateservice.office.com/```  <br/> |WXP  <br/> |CS  <br/> |Serviço de modelo do Office: fornece aos usuários modelos de documento online.  <br/> |
|```https://omextemplates.content.office.net/```  <br/> |WXP  <br/> |CS  <br/> |Downloads de modelos do Office-armazenamento de imagens de modelo PNG.  <br/> |
|```https://store.office.com/```  <br/> |WXP  <br/> |CS  <br/> |Configuração de repositório para aplicativos do Office.  <br/> |
|```https://odc.officeapps.live.com/```  <br/> |WXPN  <br/> |CS  <br/> |Catálogo dos serviços de integração de documentos do Office (lista de serviços e pontos de extremidade) e descoberta de realm inicial.  <br/> |
|```https://cdn.odc.officeapps.live.com/```  <br/> |WXPON  <br/> |CS  <br/> |Recursos para descoberta de realm inicial v2 (15,40 e posterior)  <br/> |
|```https://officecdn.microsoft.com/```  <br/> |WXPON  <br/> |CEP  <br/> |Manifestos do Microsoft AutoUpdate – verifica se há atualizações disponíveis  <br/> |
|```https://ajax.aspnetcdn.com/```  <br/> |WXPO  <br/> |PLANILHA  <br/> |Biblioteca JavaScript do Microsoft Ajax  <br/> |
|```https://wikipedia.firstpartyapps.oaspapps.com/```  <br/> |Rar  <br/> |PLANILHA  <br/> |Aplicativo da Wikipédia para configuração e recursos do Office.  <br/> |
|```https://excelbingmap.firstpartyapps.oaspapps.com/```  <br/> |X  <br/> |PLANILHA  <br/> |Aplicativo de mapa do Bing para configuração e recursos do Office.  <br/> |
|```https://peoplegraph.firstpartyapps.oaspapps.com/```  <br/> |X  <br/> |PLANILHA  <br/> |Aplicativo gráfico de pessoas para a configuração e recursos do Office.  <br/> |
|```https://www.onenote.com/```  <br/> |N  <br/> |CEP  <br/> |O que há de novo conteúdo para o OneNote.  <br/> |
|```https://site-cdn.onenote.net/```  <br/> |N  <br/> |CEP  <br/> |Novo conteúdo do OneNote.  <br/> |
|```https://site-cdn.onenote.net/```  <br/> |N  <br/> |PLANILHA  <br/> |Quais são as novas imagens do OneNote.  <br/> |
|```https://acompli.helpshift.com/```  <br/> |O  <br/> |CEP  <br/> |Serviço de suporte no aplicativo.  <br/> |
|```https://prod-global-autodetect.acompli.net/```  <br/> |O  <br/> |CEP  <br/> |Serviço de detecção de conta de email.  <br/> |
|```https://autodiscover-s.outlook.com/```  <br/> |WXPO  <br/> |CEP  <br/> |Descoberta automática do Outlook  <br/> |
|```https://outlook.office365.com/```  <br/> |WXPO  <br/> |CEP  <br/> |Ponto de extremidade do Outlook para o Microsoft 365 Service.  <br/> |
|```https://r1.res.office365.com/```  <br/> |O  <br/> |CEP  <br/> |Ícones para suplementos do Outlook.  <br/> |
   
> [!NOTE]
> O serviço de configuração do Office atua como um serviço de descoberta automática para todos os clientes do Microsoft Office, não apenas para Mac. Os pontos de extremidade retornados na resposta são semiestáticos, pois a alteração é muito frequente, mas ainda assim possível. 
  
 **Entrar**
  
Os pontos de extremidade de rede a seguir são contatados ao entrar no armazenamento baseado em nuvem. Dependendo do tipo de conta, diferentes serviços podem ser contatados. Por exemplo:
  
- **MSA: conta da Microsoft** , normalmente usada para cenários de consumidor e de varejo 
    
- **OrgID: conta da organização** – normalmente usada para cenários comerciais 
    
|**URL**|**Aplicativos**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
|```https://login.windows.net/```  <br/> |WXPON  <br/> |CEP  <br/> |Serviço de autorização do Windows  <br/> |
|```https://login.microsoftonline.com/```  <br/> |WXPON  <br/> |CEP  <br/> |Serviço de login 365 da Microsoft (OrgID)  <br/> |
|```https://login.live.com/```  <br/> |WXPON  <br/> |CEP  <br/> |Serviço de login da conta da Microsoft (MSA)  <br/> |
|```https://auth.gfx.ms/```  <br/> |WXPON  <br/> |CS  <br/> |Auxiliar de serviço de logon da conta da Microsoft (MSA)  <br/> |
|```https://secure.aadcdn.microsoftonline-p.com/```  <br/> |WXPON  <br/> |PLANILHA  <br/> |Microsoft 365 login branding (OrgID)  <br/> |
|```https://ocws.officeapps.live.com/```  <br/> |WXPN  <br/> |CS  <br/> |Documento e locais do localizador de armazenamento  <br/> |
|```https://roaming.officeapps.live.com/```  <br/> |WXPN  <br/> |CS  <br/> |Serviço de documento usado mais recentemente (MRU)  <br/> |
   
> [!NOTE]
> Para licenças de varejo e baseadas em assinatura, a assinatura ativa o produto e permite o acesso a recursos de nuvem, como o OneDrive. Para instalações de licença de volume, os usuários ainda são solicitados a entrar (por padrão), mas isso só é necessário para o acesso a recursos na nuvem, pois o produto já está ativado. 
  
 **Ativação do produto**
  
Os pontos de extremidade de rede a seguir se aplicam à assinatura do Microsoft 365 e às ativações de licença de varejo. Especificamente, isso não se aplica a instalações de licença de volume.
  
|**URL**|**Aplicativos**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
|```https://ols.officeapps.live.com/```  <br/> |WXPON  <br/> |CS  <br/> |Serviço de Licenciamento do Office  <br/> |
   
 **Conteúdo novidades**
  
Os pontos de extremidade de rede a seguir aplicam-se apenas à assinatura do Microsoft 365.
  
|**URL**|**Aplicativos**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
|```https://contentstorage.osi.office.net/```  <br/> |WXPO  <br/> |PLANILHA  <br/> |O que há de novo conteúdo de página JSON.  <br/> |
   
 **Pesquisador**
  
Os pontos de extremidade de rede a seguir aplicam-se apenas à assinatura do Microsoft 365.
  
|**URL**|**Aplicativos**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
|```https://entity.osi.office.net/```  <br/> |Rar  <br/> |CS  <br/> |Serviço Web do pesquisador  <br/> |
|```https://cdn.entity.osi.office.net/```  <br/> |Rar  <br/> |CS  <br/> |Conteúdo estático do pesquisador  <br/> |
|```https://www.bing.com/```  <br/> |Rar  <br/> |CS  <br/> |Provedor de conteúdo do pesquisador  <br/> |
   
 **Pesquisa Inteligente**
  
Os pontos de extremidade de rede a seguir se aplicam à assinatura do Microsoft 365 e às ativações de licença de varejo/volume.
  
|**URL**|**Aplicativos**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
|```https://uci.officeapps.live.com/```  <br/> |WXPN  <br/> |CS  <br/> |Serviço Web do insights  <br/> |
|```https://ajax.googleapis.com/```  <br/> |WXPN  <br/> |CS  <br/> |Biblioteca JQuery  <br/> |
|```https://cdnjs.cloudflare.com/```  <br/> |WXPN  <br/> |CS  <br/> |Biblioteca de suporte de JavaScript  <br/> |
|```https://www.bing.com/```  <br/> |WXPN  <br/> |CS  <br/> |Provedor de conteúdo do insights  <br/> |
|```https://tse1.mm.bing.net/```  <br/> |WXPN  <br/> |CS  <br/> |Provedor de conteúdo do insights  <br/> |
   
 **Designer do PowerPoint**
  
Os pontos de extremidade de rede a seguir aplicam-se apenas à assinatura do Microsoft 365.
  
|**URL**|**Aplicativos**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
|```https://pptsgs.officeapps.live.com/```  <br/> |P  <br/> |CS  <br/> |Serviço Web do PowerPoint designer  <br/> |
   
 **Iniciador rápido do PowerPoint**
  
Os pontos de extremidade de rede a seguir aplicam-se apenas à assinatura do Microsoft 365.
  
|**URL**|**Aplicativos**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
|```https://pptcts.officeapps.live.com/```  <br/> |P  <br/> |CS  <br/> |Serviço Web do início rápido do PowerPoint  <br/> |
   
 **Enviar um Smiley/rosto triste**
  
Os pontos de extremidade de rede a seguir se aplicam à assinatura do Microsoft 365 e às ativações de licença de varejo/volume.
  
|**URL**|**Aplicativos**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
|```https://sas.office.microsoft.com/```  <br/> |WXPON  <br/> |CS  <br/> |Enviar um serviço Smiley  <br/> |
   
 **Contatar o suporte**
  
Os pontos de extremidade de rede a seguir se aplicam à assinatura do Microsoft 365 e às ativações de licença de varejo/volume.
  
|**URL**|**Aplicativos**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
|```https://powerlift-frontdesk.acompli.net/```  <br/> |O  <br/> |CS  <br/> |Contatar o serviço de suporte  <br/> |
|```https://acompli.helpshift.com/```  <br/> |O  <br/> |CS  <br/> |Serviço de suporte no aplicativo  <br/> |
   
 **Salvar como PDF**
  
Os pontos de extremidade de rede a seguir se aplicam à assinatura do Microsoft 365 e às ativações de licença de varejo/volume.
  
|**URL**|**Aplicativos**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
|```https://wordcs.officeapps.live.com/```  <br/> |Rar  <br/> |CS  <br/> |Serviço de conversão de documentos do Word (PDF)  <br/> |
   
 **Aplicativos do Office (também conhecidos como suplementos)**
  
Os pontos de extremidade de rede a seguir se aplicam à assinatura do Microsoft 365 e às ativações de licença de varejo/volume quando os suplementos de aplicativo do Office são confiáveis.
  
|**URL**|**Aplicativos**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
|```https://store.office.com/```  <br/> |WXPO  <br/> |CS  <br/> |Configuração da loja de aplicativos do Office  <br/> |
|```https://wikipedia.firstpartyapps.oaspapps.com/```  <br/> |Rar  <br/> |PLANILHA  <br/> |Recursos do aplicativo da Wikipédia  <br/> |
|```https://excelbingmap.firstpartyapps.oaspapps.com/```  <br/> |X  <br/> |PLANILHA  <br/> |Recursos do Bing MAP app  <br/> |
|```https://peoplegraph.firstpartyapps.oaspapps.com```  <br/> |X  <br/> |PLANILHA  <br/> |Recursos do aplicativo gráfico de pessoas  <br/> |
|```https://o15.officeredir.microsoft.com/```  <br/> |WPX  <br/> |PLANILHA  <br/> |Serviço de redirecionamento do Office  <br/> |
|```https://appsforoffice.microsoft.com/```  <br/> |WXP  <br/> |PLANILHA  <br/> |Bibliotecas JavaScript do Office  <br/> |
|```https://telemetry.firstpartyapps.oaspapps.com/```  <br/> |WX  <br/> |PLANILHA  <br/> |Serviço de telemetria e relatório para aplicativos do Office  <br/> |
|```https://ajax.microsoft.com/```  <br/> |Rar  <br/> |PLANILHA  <br/> |Biblioteca JavaScript do Microsoft Ajax  <br/> |
|```https://ajax.aspnetcdn.com/```  <br/> |X  <br/> |PLANILHA  <br/> |Biblioteca JavaScript do Microsoft Ajax  <br/> |
|```https://c.microsoft.com/```  <br/> |WPXO  <br/> |PLANILHA  <br/> |Bibliotecas JavaScript do Office  <br/> |
|```https://c1.microsoft.com/```  <br/> |WPXO  <br/> |PLANILHA  <br/> |Recursos de suporte  <br/> |
|```https://cs.microsoft.com/```  <br/> |WPXO  <br/> |PLANILHA  <br/> |Recursos de suporte  <br/> |
|```https://c.bing.com/```  <br/> |WPXO  <br/> |PLANILHA  <br/> |Recursos de suporte  <br/> |
|```https://*.cdn.optimizely.com/```  <br/> |WPXO  <br/> |PLANILHA  <br/> |Biblioteca JavaScript  <br/> |
|```https://errors.client.optimizely.com/```  <br/> |WPX  <br/> |PLANILHA  <br/> |Relatórios de erros  <br/> |
|```https://*-contentstorage.osi.office.net/```  <br/> |WPXO  <br/> |PLANILHA  <br/> |Recursos de fontes  <br/> |
|```https://nexus.ensighten.com/```  <br/> |WPXO  <br/> |PLANILHA  <br/> |Serviço de telemetria  <br/> |
|```https://browser.pipe.aria.microsoft.com/```  <br/> |WPXO  <br/> |PLANILHA  <br/> |Relatórios de telemetria  <br/> |
|```https://*.vo.msecnd.net/```  <br/> |WPXO  <br/> |PLANILHA  <br/> |Biblioteca de ativos da Microsoft Store  <br/> |
|```https://*.wikipedia.org/```  <br/> |Rar  <br/> |PLANILHA  <br/> |Recursos da página da wikipedia  <br/> |
|```https://upload.wikimedia.org/```  <br/> |Rar  <br/> |PLANILHA  <br/> |Recursos de mídia da Wikipédia  <br/> |
|```https://wikipedia.firstpartyappssandbox.oappseperate.com/```  <br/> |Rar  <br/> |PLANILHA  <br/> |Quadro de área restrita da Wikipédia  <br/> |
|```https://*.virtualearth.net/```  <br/> |X  <br/> |PLANILHA  <br/> |Modelos de mapa  <br/> |
   
 **Links Seguros**
  
O ponto de extremidade de rede a seguir se aplica a todos os aplicativos do Office somente para a assinatura do Microsoft 365.
  
|**URL**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|```https://*.oscs.protection.outlook.com/```  <br/> |CS  <br/> |Serviço de link seguro da Microsoft  <br/> |
   
 **Relatórios de falhas**
  
O ponto de extremidade de rede a seguir se aplica a todos os aplicativos do Office para a assinatura do Microsoft 365 e as ativações de licença de varejo/volume. Quando um processo falha inesperadamente, um relatório é gerado e enviado ao serviço Watson.
  
|**URL**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|```https://watson.microsoft.com/```  <br/> |CEP  <br/> |Serviço de relatório de erros da Microsoft  <br/> |
|```https://officeci.azurewebsites.net/```  <br/> |CEP  <br/> |Serviço de insights colaborativos do Office  <br/> |
   
## <a name="options-for-reducing-network-requests-and-traffic"></a>Opções para reduzir as solicitações de rede e o tráfego

A configuração padrão do Office para Mac fornece a melhor experiência do usuário, tanto em termos de funcionalidade quanto mantendo a máquina atualizada. Em alguns cenários, talvez você queira impedir que os aplicativos entrem em contato com pontos de extremidade de rede. Esta seção discute as opções para fazer isso.
  
 ### <a name="disabling-cloud-sign-in-and-office-add-ins"></a>Desabilitando a entrada na nuvem e os suplementos do Office
  
Os clientes de licença de volume podem ter políticas rígidas para salvar documentos no armazenamento baseado em nuvem. A preferência por aplicativo a seguir pode ser definida para desabilitar o MSA/OrgID entrar e acessar os suplementos do Office.
  
- ```defaults write com.microsoft.Word UseOnlineContent -integer 0```

- ```defaults write com.microsoft.Excel UseOnlineContent -integer 0```

- ```defaults write com.microsoft.Powerpoint UseOnlineContent -integer 0```

Se os usuários tentarem acessar a função de entrada, eles verão um erro que não está presente em uma conexão de rede. Como essa preferência também bloqueia a ativação do produto online, ela deve ser usada apenas para instalações de licença de volume. Especificamente, o uso dessa preferência impede que os aplicativos do Office acessem os seguintes pontos de extremidade:
  
- ```https://odc.officeapps.live.com```
    
- ```https://*.firstpartyapps.oaspapps.com```
    
- Todos os pontos de extremidade listados na seção "entrar" acima.
    
- Todos os pontos de extremidade listados na seção "Pesquisa inteligente" acima.
    
- Todos os pontos de extremidade listados na seção "ativação do produto" acima.
    
- Todos os pontos de extremidade listados na seção "aplicativos do Office (também conhecidos como suplementos)" acima.
    
Para restabelecer a funcionalidade completa do usuário, defina a preferência como ' 2 ' ou remova-o.
  
> [!NOTE]
> Essa preferência requer o Office para Mac Build 15,25 [160726] ou posterior. 
  
### <a name="telemetry"></a>Telemetria
  
O Office para Mac envia informações de telemetria de volta para a Microsoft em intervalos regulares. Os dados são carregados para o ponto de extremidade ' Nexus '. Os dados de telemetria ajudam a equipe de engenharia a avaliar a integridade e todos os comportamentos inesperados de cada aplicativo do Office. Há duas categorias de telemetria:
  
- A **pulsação** contém informações de versão e licença. Esses dados são enviados imediatamente após o início do aplicativo. 
    
- O **uso** contém informações sobre como os aplicativos estão sendo usados e erros não fatais. Esses dados são enviados a cada 60 minutos. 
    
A Microsoft leva sua privacidade muito séria. Você pode ler sobre a política de coleta de dados da Microsoft em [https://privacy.microsoft.com](https://privacy.microsoft.com) . Para impedir que os aplicativos enviem a telemetria de "uso", a preferência **SendAllTelemetryEnabled** pode ser ajustada. A preferência é por aplicativo e pode ser definida por meio de perfis de configuração do macOS ou manualmente do terminal: 
  
```defaults write com.microsoft.Word SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.Excel SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.Powerpoint SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.Outlook SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.onenote.mac SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.autoupdate2 SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.Office365ServiceV2 SendAllTelemetryEnabled -bool FALSE```

A telemetria da pulsação é sempre enviada e não pode ser desabilitada.
  
### <a name="crash-reporting"></a>Relatórios de falhas
  
Quando ocorre um erro fatal de aplicativo, o aplicativo é encerrado inesperadamente e carrega um relatório de falhas para o serviço "Watson". O relatório de falhas consiste em uma pilha de chamadas, que é a lista de etapas que o aplicativo estava processando levando à falha. Estas etapas ajudam a equipe de engenharia a identificar a função exata que falhou e por quê.
  
Em alguns casos, o conteúdo de um documento fará com que o aplicativo falhe. Se o aplicativo identificar o documento como a causa, ele perguntará ao usuário se ele também pode enviar o documento junto com a pilha de chamadas. Os usuários podem fazer uma escolha informada nesta pergunta. Os administradores de ti podem ter requisitos estritos sobre a transmissão de documentos e tomar a decisão em nome do usuário para nunca enviar documentos. A preferência a seguir pode ser definida para impedir que documentos sejam enviados e para suprimir a solicitação ao usuário:
  
```defaults write com.microsoft.errorreporting IsAttachFilesEnabled -bool FALSE```

> [!NOTE]
> Se **SendAllTelemetryEnabled** estiver definido como **false**, todos os relatórios de falha desse processo serão desabilitados. Para habilitar o relatório de falhas sem enviar telemetria de uso, é possível definir a seguinte preferência: ```defaults write com.microsoft.errorreporting IsMerpEnabled -bool TRUE``` 
  
### <a name="updates"></a>Atualizações
  
A Microsoft lança atualizações do Office para Mac em intervalos regulares (normalmente uma vez por mês). Recomendamos que os usuários e administradores de ti mantenham as máquinas atualizadas para garantir que as correções de segurança mais recentes estejam instaladas. Nos casos em que os administradores de ti desejam controlar de perto e gerenciar atualizações de máquina, a preferência a seguir pode ser definida para impedir que o processo de atualização automática detecte automaticamente e ofereça atualizações de produtos:
  
```defaults write com.microsoft.autoupdate2 HowToCheck -string 'Manual'```

### <a name="blocking-requests-with-a-firewallproxy"></a>Bloqueando solicitações com um firewall/proxy
  
Se sua organização bloqueia solicitações para URLs por meio de um firewall ou servidor proxy, certifique-se de configurar as URLs listadas neste documento como permitido ou em bloco listado com uma resposta 40X (por exemplo, 403 ou 404). Uma resposta 40X permitirá que os aplicativos do Office aceitem normalmente a incapacidade de acessar o recurso e oferecerá uma experiência mais rápida do usuário do que simplesmente descartar a conexão, o que, por sua vez, fará com que o cliente tente novamente.
  
Se o seu servidor proxy exigir autenticação, uma resposta 407 será retornada ao cliente. Para obter a melhor experiência, certifique-se de que você está usando o Office para Mac Builds 15,27 ou posterior, já que eles incluem correções específicas para trabalhar com servidores NTLM e Kerberos.
  
  
## <a name="see-also"></a>Confira também

[URLs e intervalos de endereços IP do Office 365](urls-and-ip-address-ranges.md)

