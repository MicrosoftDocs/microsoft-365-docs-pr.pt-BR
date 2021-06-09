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
description: Este artigo descreve quais pontos de extremidade e URLs Office para Mac aplicativos tentam alcançar e os serviços fornecidos.
ms.openlocfilehash: b777b4ea7e03495cb6389be8fe05e96a26fd9664
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687235"
---
# <a name="network-requests-in-office-for-mac"></a>Solicitações de rede do Office para Mac

Office para Mac aplicativos fornecem uma experiência de aplicativo nativa na plataforma macOS. Cada aplicativo foi projetado para funcionar em vários cenários, incluindo estados quando não há acesso à rede disponível. Quando um computador está conectado a uma rede, os aplicativos se conectam automaticamente a uma série de serviços baseados na Web para fornecer funcionalidade aprimorada. As informações a seguir descrevem quais pontos de extremidade e URLs os aplicativos tentam alcançar e os serviços fornecidos. Essas informações são úteis ao solucionar problemas de configuração de rede e definir políticas para servidores proxy de rede. Os detalhes deste artigo se destinam a complementar o artigo Office 365 URL e intervalos de [endereços](urls-and-ip-address-ranges.md), que inclui pontos de extremidade para computadores que executam o Microsoft Windows. A menos que sejam mencionadas, as informações deste artigo também se aplicarão ao Office 2019 para Mac e Office 2016 para Mac, que estão disponíveis como uma compra única de um loja de varejo ou por meio de um contrato de licenciamento por volume. 

  
A maioria deste artigo são tabelas que detalham URLs de rede, tipo e descrição do serviço ou recurso fornecido por esse ponto de extremidade. Cada um dos Office aplicativos pode diferir em seu uso de serviço e ponto de extremidade. Os seguintes aplicativos são definidos nas tabelas abaixo:
  
- W: Word
- P: PowerPoint
- X: Excel
- O: Outlook
- N: OneNote
   
O tipo de URL é definido da seguinte forma:
  
- ST: Static - A URL é codificada no aplicativo cliente.
    
- SS: Semi-Static - A URL é codificada como parte de uma página da Web ou redirecionador.
    
- CS: Serviço de Configuração - A URL é retornada como parte do serviço Office configuração.

    
## <a name="office-for-mac-default-configuration"></a>Office para Mac configuração padrão

 **Instalação e atualizações**
  
Os seguintes pontos de extremidade de rede são usados para baixar o programa Office para Mac de instalação do Microsoft Rede de Distribuição de Conteúdo (CDN).
  
|**URL**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|```https://go.microsoft.com/fwlink/```  <br/> |ST  <br/> |Microsoft 365 Serviço de link de encaminhamento do Portal de Instalação para pacotes de instalação mais recentes.  <br/> |
|```https://officecdn-microsoft-com.akamaized.net/```  <br/> |SS  <br/> |Local dos pacotes de instalação no Rede de Distribuição de Conteúdo.  <br/> |
|```https://officecdn.microsoft.com/```  <br/> |SS  <br/> |Local dos pacotes de instalação no Rede de Distribuição de Conteúdo.  <br/> |
|```https://officeci-mauservice.azurewebsites.net/```  <br/> |ST  <br/> |Ponto de extremidade de Controle de Gerenciamento para Microsoft AutoUpdate  <br/> |
   
 **Primeira iniciação do aplicativo**
  
Os seguintes pontos de extremidade de rede são contatados no primeiro lançamento de um Aplicativo do Office. Esses pontos de extremidade fornecem funcionalidades avançadas Office usuários, e as URLs são contatadas independentemente do tipo de licença (incluindo instalações de Licença de Volume).
  
|**URL**|**Aplicativos**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
|```https://config.edge.skype.com/```  <br/> |WXPON  <br/> |ST  <br/> |Configuração 'Flighting' - permite a iluminação e a experimentação de recursos.  <br/> |
|```https://ocos-office365-s2s.msedge.net/```  <br/> |WXPON  <br/> |ST  <br/> |Teste de configuração de rede de 'flighting'  <br/> |
|```https://client-office365-tas.msedge.net/```  <br/> |WXPON  <br/> |ST  <br/> |Teste de configuração de rede de 'flighting'  <br/> |
|```https://officeclient.microsoft.com/```  <br/> |WXPON  <br/> |ST  <br/> |Office Serviço de Configuração - Lista mestra de pontos de extremidade do serviço.  <br/> |
|```https://nexusrules.officeapps.live.com/```  <br/> |WXPON  <br/> |ST  <br/> |Office Download de Telemetria de Regras - Informa ao cliente quais dados e eventos serão carregados no serviço de telemetria.  <br/> |
|```https://mobile.pipe.aria.microsoft.com/```  <br/> |N  <br/> |CS  <br/> |OneNote Serviço de Telemetria  <br/> |
|```https://nexus.officeapps.live.com/```  <br/> |WXPON  <br/> |ST  <br/> |Office Telemetria Upload Relatórios - "Heartbeart" e eventos de erro que ocorrem no cliente são carregados no serviço de telemetria.  <br/> |
|```https://templateservice.office.com/```  <br/> |WXP  <br/> |CS  <br/> |Office Serviço de Modelo - Fornece aos usuários modelos de documento online.  <br/> |
|```https://omextemplates.content.office.net/```  <br/> |WXP  <br/> |CS  <br/> |Office Downloads de modelos - Armazenamento de imagens de modelo PNG.  <br/> |
|```https://store.office.com/```  <br/> |WXP  <br/> |CS  <br/> |Configuração da Loja para Office aplicativos.  <br/> |
|```https://odc.officeapps.live.com/```  <br/> |WXPN  <br/> |CS  <br/> |Office Catálogo de Serviços de Integração de Documentos (lista de serviços e pontos de extremidade) e Descoberta de Domínio Inicial.  <br/> |
|```https://cdn.odc.officeapps.live.com/```  <br/> |WXPON  <br/> |CS  <br/> |Recursos para Descoberta de Domínio Inicial v2 (15.40 e posteriores)  <br/> |
|```https://officecdn.microsoft.com/```  <br/> |WXPON  <br/> |ST  <br/> |Manifestos Do Microsoft AutoUpdate - verifica se há atualizações disponíveis  <br/> |
|```https://ajax.aspnetcdn.com/```  <br/> |WXPO  <br/> |SS  <br/> |Biblioteca JavaScript do Microsoft Ajax  <br/> |
|```https://wikipedia.firstpartyapps.oaspapps.com/```  <br/> |W  <br/> |SS  <br/> |Aplicativo wikipédia para Office configuração e recursos.  <br/> |
|```https://excelbingmap.firstpartyapps.oaspapps.com/```  <br/> |X  <br/> |SS  <br/> |Bing Mapeie o aplicativo para Office e recursos.  <br/> |
|```https://peoplegraph.firstpartyapps.oaspapps.com/```  <br/> |X  <br/> |SS  <br/> |As pessoas Graph aplicativo para Office configuração e recursos.  <br/> |
|```https://www.onenote.com/```  <br/> |N  <br/> |ST  <br/> |O que há de novo no OneNote.  <br/> |
|```https://site-cdn.onenote.net/```  <br/> |N  <br/> |ST  <br/> |Novo conteúdo para OneNote.  <br/> |
|```https://site-cdn.onenote.net/```  <br/> |N  <br/> |SS  <br/> |Quais são as novas imagens para OneNote.  <br/> |
|```https://acompli.helpshift.com/```  <br/> |O  <br/> |ST  <br/> |Serviço de Suporte no aplicativo.  <br/> |
|```https://prod-global-autodetect.acompli.net/```  <br/> |O  <br/> |ST  <br/> |Serviço de Detecção de Conta de Email.  <br/> |
|```https://autodiscover-s.outlook.com/```  <br/> |WXPO  <br/> |ST  <br/> |Outlook Descoberta Automática  <br/> |
|```https://outlook.office365.com/```  <br/> |WXPO  <br/> |ST  <br/> |Outlook ponto de extremidade para Microsoft 365 serviço.  <br/> |
|```https://r1.res.office365.com/```  <br/> |O  <br/> |ST  <br/> |Ícones para Outlook de complementos.  <br/> |
   
> [!NOTE]
> O Office de Configuração atua como um serviço de descoberta automática para todos os clientes Microsoft Office, não apenas para Mac. Os pontos de extremidade retornados na resposta são semi-estáticos porque a alteração é muito pouco frequente, mas ainda é possível. 
  
 **Entrar**
  
Os seguintes pontos de extremidade de rede são contatados ao entrar no armazenamento baseado em nuvem. Dependendo do tipo de conta, diferentes serviços podem ser contatados. Por exemplo:
  
- **MSA: Conta da Microsoft** - normalmente usada para cenários de consumidor e varejo 
    
- **OrgID: Conta da Organização** - normalmente usada para cenários comerciais 
    
|**URL**|**Aplicativos**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
|```https://login.windows.net/```  <br/> |WXPON  <br/> |ST  <br/> |Windows Serviço de Autorização  <br/> |
|```https://login.microsoftonline.com/```  <br/> |WXPON  <br/> |ST  <br/> |Microsoft 365 Serviço de Logon (OrgID)  <br/> |
|```https://login.live.com/```  <br/> |WXPON  <br/> |ST  <br/> |Microsoft Account Login Service (MSA)  <br/> |
|```https://auth.gfx.ms/```  <br/> |WXPON  <br/> |CS  <br/> |Ajuda do Serviço de Logon da Conta da Microsoft (MSA)  <br/> |
|```https://secure.aadcdn.microsoftonline-p.com/```  <br/> |WXPON  <br/> |SS  <br/> |Microsoft 365 Identidade visual de logon (OrgID)  <br/> |
|```https://ocws.officeapps.live.com/```  <br/> |WXPN  <br/> |CS  <br/> |Document and Places Armazenamento Locator  <br/> |
|```https://roaming.officeapps.live.com/```  <br/> |WXPN  <br/> |CS  <br/> |Serviço de documento usado mais recentemente (MRU)  <br/> |
   
> [!NOTE]
> Para licenças baseadas em assinatura e varejo, entrar ativa o produto e permite o acesso a recursos de nuvem, como OneDrive. Para instalações de Licença de Volume, os usuários ainda são solicitados a entrar (por padrão), mas isso só é necessário para acesso a recursos de nuvem, pois o produto já está ativado. 
  
 **Ativação do produto**
  
Os seguintes pontos de extremidade de rede se aplicam Microsoft 365 assinatura e ativações de Licença de Varejo. Especificamente, isso NÃO se aplica a instalações de Licença de Volume.
  
|**URL**|**Aplicativos**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
|```https://ols.officeapps.live.com/```  <br/> |WXPON  <br/> |CS  <br/> |Serviço de Licenciamento do Office  <br/> |
   
 **O que há de novo no conteúdo**
  
Os pontos de extremidade de rede a seguir aplicam-se Microsoft 365 somente assinatura.
  
|**URL**|**Aplicativos**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
|```https://contentstorage.osi.office.net/```  <br/> |WXPO  <br/> |SS  <br/> |O que há de novo conteúdo de página JSON.  <br/> |
   
 **Pesquisador**
  
Os pontos de extremidade de rede a seguir aplicam-se Microsoft 365 somente assinatura.
  
|**URL**|**Aplicativos**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
|```https://entity.osi.office.net/```  <br/> |W  <br/> |CS  <br/> |Serviço Web pesquisador  <br/> |
|```https://cdn.entity.osi.office.net/```  <br/> |W  <br/> |CS  <br/> |Conteúdo Estático do Pesquisador  <br/> |
|```https://www.bing.com/```  <br/> |W  <br/> |CS  <br/> |Provedor de Conteúdo de Pesquisador  <br/> |
   
 **Pesquisa Inteligente**
  
Os pontos de extremidade de rede a seguir aplicam-se Microsoft 365 assinatura e ativações de Licença de Varejo/Volume.
  
|**URL**|**Aplicativos**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
|```https://uci.officeapps.live.com/```  <br/> |WXPN  <br/> |CS  <br/> |Insights Web Service  <br/> |
|```https://ajax.googleapis.com/```  <br/> |WXPN  <br/> |CS  <br/> |Biblioteca JQuery  <br/> |
|```https://cdnjs.cloudflare.com/```  <br/> |WXPN  <br/> |CS  <br/> |Dando suporte à Biblioteca JavaScript  <br/> |
|```https://www.bing.com/```  <br/> |WXPN  <br/> |CS  <br/> |Provedor de Conteúdo do Insights  <br/> |
|```https://tse1.mm.bing.net/```  <br/> |WXPN  <br/> |CS  <br/> |Provedor de Conteúdo do Insights  <br/> |
   
 **Designer do PowerPoint**
  
Os pontos de extremidade de rede a seguir aplicam-se Microsoft 365 somente assinatura.
  
|**URL**|**Aplicativos**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
|```https://pptsgs.officeapps.live.com/```  <br/> |P  <br/> |CS  <br/> |Designer do PowerPoint web  <br/> |
   
 **Iniciador rápido do PowerPoint**
  
Os pontos de extremidade de rede a seguir aplicam-se Microsoft 365 somente assinatura.
  
|**URL**|**Aplicativos**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
|```https://pptcts.officeapps.live.com/```  <br/> |P  <br/> |CS  <br/> |PowerPoint Serviço Web Do QuickStarter  <br/> |
   
 **Enviar um Smile/Frown**
  
Os pontos de extremidade de rede a seguir aplicam-se Microsoft 365 assinatura e ativações de Licença de Varejo/Volume.
  
|**URL**|**Aplicativos**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
|```https://sas.office.microsoft.com/```  <br/> |WXPON  <br/> |CS  <br/> |Enviar um serviço de smile  <br/> |
   
 **Contatar o Suporte**
  
Os pontos de extremidade de rede a seguir aplicam-se Microsoft 365 assinatura e ativações de Licença de Varejo/Volume.
  
|**URL**|**Aplicativos**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
|```https://powerlift-frontdesk.acompli.net/```  <br/> |O  <br/> |CS  <br/> |Serviço de Suporte de Contato  <br/> |
|```https://acompli.helpshift.com/```  <br/> |O  <br/> |CS  <br/> |Serviço de Suporte no aplicativo  <br/> |
   
 **Salvar como PDF**
  
Os pontos de extremidade de rede a seguir aplicam-se Microsoft 365 assinatura e ativações de Licença de Varejo/Volume.
  
|**URL**|**Aplicativos**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
|```https://wordcs.officeapps.live.com/```  <br/> |W  <br/> |CS  <br/> |Serviço de conversão de documento do Word (PDF)  <br/> |
   
 **Office Aplicativos (também conhecidos como complementos)**
  
Os seguintes pontos de extremidade de rede se aplicam Microsoft 365 assinatura e ativações de Licença de Varejo/Volume quando os Office de aplicativos são confiáveis.
  
|**URL**|**Aplicativos**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|:-----|
|```https://store.office.com/```  <br/> |WXPO  <br/> |CS  <br/> |Aplicativo do Office de armazenamento  <br/> |
|```https://wikipedia.firstpartyapps.oaspapps.com/```  <br/> |W  <br/> |SS  <br/> |Recursos de aplicativos da Wikipédia  <br/> |
|```https://excelbingmap.firstpartyapps.oaspapps.com/```  <br/> |X  <br/> |SS  <br/> |Bing Mapear recursos do aplicativo  <br/> |
|```https://peoplegraph.firstpartyapps.oaspapps.com```  <br/> |X  <br/> |SS  <br/> |Pessoas Graph recursos do aplicativo  <br/> |
|```https://o15.officeredir.microsoft.com/```  <br/> |WPX  <br/> |SS  <br/> |Office Serviço de Redirecionamento  <br/> |
|```https://appsforoffice.microsoft.com/```  <br/> |WXP  <br/> |SS  <br/> |Office Bibliotecas JavaScript  <br/> |
|```https://telemetry.firstpartyapps.oaspapps.com/```  <br/> |WX  <br/> |SS  <br/> |Telemetria e Serviço de Relatórios para Office aplicativos  <br/> |
|```https://ajax.microsoft.com/```  <br/> |W  <br/> |SS  <br/> |Biblioteca JavaScript do Microsoft Ajax  <br/> |
|```https://ajax.aspnetcdn.com/```  <br/> |X  <br/> |SS  <br/> |Biblioteca JavaScript do Microsoft Ajax  <br/> |
|```https://c.microsoft.com/```  <br/> |WPXO  <br/> |SS  <br/> |Office Bibliotecas JavaScript  <br/> |
|```https://c1.microsoft.com/```  <br/> |WPXO  <br/> |SS  <br/> |Recursos de suporte  <br/> |
|```https://cs.microsoft.com/```  <br/> |WPXO  <br/> |SS  <br/> |Recursos de suporte  <br/> |
|```https://c.bing.com/```  <br/> |WPXO  <br/> |SS  <br/> |Recursos de suporte  <br/> |
|```https://*.cdn.optimizely.com/```  <br/> |WPXO  <br/> |SS  <br/> |Biblioteca JavaScript  <br/> |
|```https://errors.client.optimizely.com/```  <br/> |WPX  <br/> |SS  <br/> |Relatório de erros  <br/> |
|```https://*-contentstorage.osi.office.net/```  <br/> |WPXO  <br/> |SS  <br/> |Recursos de fonte  <br/> |
|```https://nexus.ensighten.com/```  <br/> |WPXO  <br/> |SS  <br/> |Serviço de Telemetria  <br/> |
|```https://browser.pipe.aria.microsoft.com/```  <br/> |WPXO  <br/> |SS  <br/> |Relatórios de Telemetria  <br/> |
|```https://*.vo.msecnd.net/```  <br/> |WPXO  <br/> |SS  <br/> |Microsoft Store Biblioteca de Ativos  <br/> |
|```https://*.wikipedia.org/```  <br/> |W  <br/> |SS  <br/> |Recursos de página da Wikipédia  <br/> |
|```https://upload.wikimedia.org/```  <br/> |W  <br/> |SS  <br/> |Recursos de mídia da Wikipédia  <br/> |
|```https://wikipedia.firstpartyappssandbox.oappseperate.com/```  <br/> |W  <br/> |SS  <br/> |Quadro de área de área de trabalho da Wikipédia  <br/> |
|```https://*.virtualearth.net/```  <br/> |X  <br/> |SS  <br/> |Modelos de mapa  <br/> |
   
 **Links Seguros**
  
O ponto de extremidade de rede a seguir se aplica a todos os aplicativos Office somente Microsoft 365 assinatura.
  
|**URL**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|```https://*.oscs.protection.outlook.com/```  <br/> |CS  <br/> |Serviço Cofre Link da Microsoft  <br/> |
   
 **Relatório de falhas**
  
O ponto de extremidade de rede a seguir se aplica a todos os aplicativos Office para as ativações de Assinatura Microsoft 365 De Varejo/Volume. Quando um processo falha inesperadamente, um relatório é gerado e enviado para o serviço Watson.
  
|**URL**|**Tipo**|**Descrição**|
|:-----|:-----|:-----|
|```https://watson.microsoft.com/```  <br/> |ST  <br/> |Serviço de Relatório de Erros da Microsoft  <br/> |
|```https://officeci.azurewebsites.net/```  <br/> |ST  <br/> |Office Serviço de Insights Colaborativos  <br/> |
   
## <a name="options-for-reducing-network-requests-and-traffic"></a>Opções para reduzir solicitações de rede e tráfego

A configuração padrão do Office para Mac fornece a melhor experiência do usuário, tanto em termos de funcionalidade quanto em manter o computador atualizado. Em alguns cenários, talvez você queira impedir que os aplicativos contatem pontos de extremidade de rede. Esta seção discute opções para fazer isso.
  
 ### <a name="disabling-cloud-sign-in-and-office-add-ins"></a>Desabilitando a nuvem Sign-In e Office Add-Ins
  
Os clientes de Licença por Volume podem ter políticas estritas sobre como salvar documentos no armazenamento baseado em nuvem. A preferência a seguir por aplicativo pode ser definida para desabilitar a entrada do MSA/OrgID e o acesso a Office Desprogramas.
  
- ```defaults write com.microsoft.Word UseOnlineContent -integer 0```

- ```defaults write com.microsoft.Excel UseOnlineContent -integer 0```

- ```defaults write com.microsoft.Powerpoint UseOnlineContent -integer 0```

Se os usuários tentarem acessar a função Sign-In, eles verão um erro de que uma conexão de rede não está presente. Como essa preferência também bloqueia a ativação do produto online, ela só deve ser usada para instalações de Licença de Volume. Especificamente, usar essa preferência impedirá que Office aplicativos acessem os seguintes pontos de extremidade:
  
- ```https://odc.officeapps.live.com```
    
- ```https://*.firstpartyapps.oaspapps.com```
    
- Todos os pontos de extremidade listados na seção 'Entrar' acima.
    
- Todos os pontos de extremidade listados na seção "Smart Lookup" acima.
    
- Todos os pontos de extremidade listados na seção 'Ativação do Produto' acima.
    
- Todos os pontos de extremidade listados na seção 'Office Aplicativos (também conhecidos como complementos)' acima.
    
Para restabelecer a funcionalidade completa para o usuário, de definir a preferência como '2' ou removê-la.
  
> [!NOTE]
> Essa preferência requer Office para Mac build 15.25 [160726] ou posterior. 
  
### <a name="telemetry"></a>Telemetria
  
Office para Mac envia informações de telemetria de volta à Microsoft em intervalos regulares. Os dados são carregados no ponto de extremidade 'Nexus'. Os dados de telemetria ajudam a equipe de engenharia a avaliar a saúde e os comportamentos inesperados de cada Aplicativo do Office. Há duas categorias de telemetria:
  
- **Heartbeat** contém informações de versão e licença. Esses dados são enviados imediatamente após o início do aplicativo. 
    
- **O** uso contém informações sobre como os aplicativos estão sendo usados e erros não fatais. Esses dados são enviados a cada 60 minutos. 
    
A Microsoft leva sua privacidade muito a sério. Você pode ler sobre a política de coleta de dados da Microsoft em [https://privacy.microsoft.com](https://privacy.microsoft.com) . Para impedir que os aplicativos enviem telemetria 'Uso', a preferência **SendAllTelemetryEnabled** pode ser ajustada. A preferência é por aplicativo e pode ser definida por meio de Perfis de Configuração do macOS ou manualmente do Terminal: 
  
```defaults write com.microsoft.Word SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.Excel SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.Powerpoint SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.Outlook SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.onenote.mac SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.autoupdate2 SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.Office365ServiceV2 SendAllTelemetryEnabled -bool FALSE```

A telemetria de pulsação sempre é enviada e não pode ser desabilitada.
  
### <a name="crash-reporting"></a>Relatório de falhas
  
Quando ocorrer um erro fatal do aplicativo, o aplicativo encerrará inesperadamente e carregará um relatório de falha no serviço 'Watson'. O relatório de falha consiste em uma pilha de chamada, que é a lista de etapas que o aplicativo estava processamento que antecede a falha. Essas etapas ajudam a equipe de engenharia a identificar a função exata que falhou e por quê.
  
Em alguns casos, o conteúdo de um documento fará com que o aplicativo falha. Se o aplicativo identificar o documento como a causa, ele perguntará ao usuário se não há problema em também enviar o documento junto com a pilha de chamada. Os usuários podem fazer uma escolha informada para essa pergunta. Os administradores de IT podem ter requisitos estritos sobre a transmissão de documentos e tomar a decisão em nome do usuário de nunca enviar documentos. A seguinte preferência pode ser definida para impedir que documentos sejam enviados e suprimir o prompt para o usuário:
  
```defaults write com.microsoft.errorreporting IsAttachFilesEnabled -bool FALSE```

> [!NOTE]
> Se **SendAllTelemetryEnabled** estiver definido como **FALSE**, todos os relatórios de falha desse processo estão desabilitados. Para habilitar o relatório de falha sem enviar telemetria de uso, a seguinte preferência pode ser definida: ```defaults write com.microsoft.errorreporting IsMerpEnabled -bool TRUE``` 
  
### <a name="updates"></a>Atualizações
  
A Microsoft lança Office para Mac atualizações em intervalos regulares (normalmente uma vez por mês). Incentivamos fortemente os usuários e administradores de IT a manter as máquinas atualizadas para garantir que as correções de segurança mais recentes sejam instaladas. Nos casos em que os administradores de IT quiserem controlar e gerenciar atualizações de máquina de perto, a seguinte preferência pode ser definida para impedir que o processo AutoUpdate detecte e ofereço atualizações do produto automaticamente:
  
```defaults write com.microsoft.autoupdate2 HowToCheck -string 'Manual'```

### <a name="blocking-requests-with-a-firewallproxy"></a>Bloqueando solicitações com um Firewall/Proxy
  
Se sua organização bloquear solicitações para URLs por meio de um firewall ou servidor proxy, configure as URLs listadas neste documento como permitidas ou bloqueados listados com uma resposta 40X (por exemplo, 403 ou 404). Uma resposta 40X permitirá que os aplicativos Office aceitem normalmente a incapacidade de acessar o recurso e fornecerão uma experiência de usuário mais rápida, do que simplesmente soltar a conexão, o que, por sua vez, fará com que o cliente reaimente.
  
Se o servidor proxy exigir autenticação, uma resposta 407 será retornada ao cliente. Para ter a melhor experiência, verifique se você está usando Office para Mac builds 15.27 ou posteriores, pois elas incluem correções específicas para trabalhar com servidores NTLM e Kerberos.
  
  
## <a name="see-also"></a>Confira também

[URLs e intervalos de endereços IP do Office 365](urls-and-ip-address-ranges.md)

