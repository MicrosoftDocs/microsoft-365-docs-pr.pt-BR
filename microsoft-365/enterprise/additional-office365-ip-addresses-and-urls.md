---
title: Pontos de extremidade adicionais não incluídos no endereço IP do Office 365 e no serviço Web de URL
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 04/19/2021
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- MOM160
- BCS160
ms.assetid: ''
description: 'Resumo: o novo serviço Web de ponto de extremidade não inclui uma quantidade pequena de pontos de extremidade para cenários específicos.'
hideEdit: true
ms.openlocfilehash: 6c545b6060b44ebe234baaebd3ae1eb2fdb0fb89
ms.sourcegitcommit: 76f3c75413cc960289489d0ca29efadb8a9a5b31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/19/2021
ms.locfileid: "51887204"
---
# <a name="additional-endpoints-not-included-in-the-office-365-ip-address-and-url-web-service"></a>Pontos de extremidade adicionais não incluídos no endereço IP do Office 365 e no serviço Web de URL

Alguns pontos de extremidade de rede foram publicados anteriormente e não foram incluídos no [endereço IP do Office 365 e no serviço Web de URL](microsoft-365-ip-web-service.md). O escopo de serviços Web é de pontos de extremidade de rede que são necessários para conectividade de um usuário final do Office 365 em uma rede de perímetro empresarial. Atualmente, isso não inclui:

1. Conectividade de rede que pode ser requerida de um datacenter da Microsoft para uma rede do cliente (tráfego de rede de servidor de entrada híbrido).
2. Conectividade de rede de servidores em uma rede do cliente no perímetro empresarial (tráfego de rede de servidor de saída).
3. Cenários excepcionais para requisitos de conectividade de rede de um usuário.
4. Requisitos de conectividade de resolução DNS (não listados abaixo).
5. Sites confiáveis do Internet Explorer ou Microsoft Edge.

Exceto pelo DNS, todos estes são opcionais para a maioria dos clientes, a menos que você precise do cenário específico descrito.

| Linha | Objetivo | Destino | Tipo |
|:-----|:-----|:-----|:-----|
| 1  | [Serviço de importação](https://support.office.com/article/use-network-upload-to-import-your-organization-pst-files-to-office-365-103f940c-0468-4e1a-b527-cc8ad13a5ea6) para PST e ingestão de arquivos | Confira o [Serviço de Importação](https://support.office.com/article/use-network-upload-to-import-your-organization-pst-files-to-office-365-103f940c-0468-4e1a-b527-cc8ad13a5ea6) para requisitos adicionais. | Cenários excepcionais de saída |
| 2  | [Assistente de Recuperação e Suporte da Microsoft para o Office 365](https://diagnostics.office.com/#/)  | https<span>://</span>autodiscover.outlook.com <BR> <span>https://</span>officecdn.microsoft.com <BR> <span>https://</span>api.diagnostics.office.com <BR> <span>https://</span>apibasic.diagnostics.office.com <BR> <span>https://</span>autodiscover-s.outlook.com <BR> <span>https://</span>cloudcheckenabler.azurewebsites.net <BR> <span>https://</span>login.live.com <BR> <span>https://</span>login.microsoftonline.com <BR> <span>https://</span>login.windows.net <BR> <span>https://</span>o365diagtelemetry.trafficmanager.net <BR> <span>https://</span>odc.officeapps.live.com <BR> <span>https://</span>offcatedge.azureedge.net <BR> <span>https://</span>officeapps.live.com <BR> <span>https://</span>outlook.office365.com <BR> <span>https://</span>outlookdiagnostics.azureedge.net | Tráfego do servidor de saída |
| 3  | Azure AD Connect (com opção de SSO) – WinRM e PowerShell remoto | Ambiente de STS do cliente (servidor do AD FS e Proxy do AD FS) \| portas TCP 80 e 443 | Tráfego do servidor de entrada |
| 4   | STS, como servidor (es) Proxy do AD FS (somente para clientes federados) | STS do cliente (como Proxy do AD FS) \| portas TCP 443 ou TCP 49443 com ClientTLS | Tráfego do servidor de entrada |
| 5   | [Mensagens unificadas no Exchange Online/Integração de SBC](/exchange/voice-mail-unified-messaging/telephone-system-integration-with-um/configuration-notes-for-session-border-controllers) | Bidirecional entre controlador de borda de sessão local e *. um.outlook.com | Somente o tráfego de servidor de saída |
| 6   | Migração de caixa de correio. Quando a migração de caixa de correio é iniciada a partir do [Exchange Híbrido](/exchange/exchange-deployment-assistant) para o Office 365, o Office 365 se conectará a seu servidor publicado de Serviços Web do Exchange (EWS)/Serviços de Replicação da Caixa de Correio (MRS). Se você precisar que os endereços IP NAT usados pelos servidores Exchange Online restrinjam conexões de entrada de intervalos IP de fontes específicas, eles se encontram listados em [Intervalos IP e de URL do Office 365](urls-and-ip-address-ranges.md) na área do serviço “Exchange Online”. Tome cuidado para garantir que o acesso a pontos de extremidade EWS publicados como OWA não seja impactado, certificando-se de que o proxy de MRS seja resolvido em um FQDN separado e em um endereço IP público antes de restringir as conexões TCP 443 de intervalos IP de fontes específicas. | Proxy de EWS/MRS local do cliente<br> Porta TCP 443 | Tráfego do servidor de entrada |
| 7   | A coexistência do [Exchange Híbrido](/exchange/exchange-deployment-assistant) funciona como um compartilhamento de disponibilidade. | Servidor Exchange local do cliente | Tráfego do servidor de entrada |
| 8   | Autenticação de proxy do [Exchange Híbrido](/exchange/exchange-deployment-assistant) | STS local do cliente | Tráfego do servidor de entrada |
| 9   | Usado para configurar o [Exchange Híbrido](/exchange/exchange-deployment-assistant), usando o [Assistente de Configuração do Exchange Híbrido](/exchange/hybrid-configuration-wizard) <br> Observação: esses pontos de extremidade só são necessários para configurar o Exchange híbrido  | domains.live.com em portas TCP 80 e 443, exigido apenas para o Assistente de Configuração do Exchange 2010 SP3 Híbrido.<BR> <BR> Endereços de IP DoD GCC High: 40.118.209.192/32; 168.62.190.41/32 <BR> <BR> Parceiros comerciais & GCC: *.store.core.windows.net; asl.configure.office.com; tds.configure.office.com; mshybridservice.trafficmanager.net; <BR> aka.ms/hybridwizard; <BR> \*shcwreleaseprod.blob.core.windows.net/shcw/;<BR>  | Somente o tráfego de servidor de saída |
| 10   | O serviço de detecção automática é usado em cenários do [Exchange Híbrido](/exchange/exchange-deployment-assistant) com [Autenticação Híbrida Moderna com Outlook para iOS e Android](/Exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth) <BR> <BR> ```*.acompli.net``` <BR> <BR> ```*.outlookmobile.com``` <BR> <BR> ```*.outlookmobile.us``` <BR> <BR> ```52.125.128.0/20``` <BR> ```52.127.96.0/23``` <BR> | Servidor Exchange local do cliente em TCP 443 | Tráfego do servidor de entrada |
| 11  | Exchange autenticação Híbrida do Azure AD | *.msappproxy.net | Tráfego somente de servidor de saída TCP |
| 12   | O Skype for Business no Office 2016 inclui o compartilhamento de tela baseado em vídeo que usa portas UDP. Os clientes mais antigos do Skype for Business no Office 2013 e em versões anteriores usavam a porta 443 RDP em vez da TCP. | Porta 443 TCP aberta para 52.112.0.0/14 | Versões de cliente mais antigas do Skype for Business no Office 2013 e em versões anteriores |
| 13  | Conectividade entre o servidor híbrido local do Skype for Business e o Skype for Business Online | 13.107.64.0/18, 52.112.0.0/14  <BR> Portas UDP 50.000-59.999 <BR>  Portas TCP 50.000-59.999; 5061 | Conectividade de saída de servidor local no Skype for Business |
| 14   | O PSTN na nuvem sem conectividade híbrida local requer conectividade aberta ao host local. Para saber mais sobre as configurações híbridas do Skype for Business Online  | Confira [Planejar conectividade híbrida entre o Skype for Business Server e o Office 365](/skypeforbusiness/hybrid/plan-hybrid-connectivity). | Entrada híbrida local do Skype for Business |
| 15  | **FQDNs de autenticação e identidade** <br> O FDQN ```secure.aadcdn.microsoftonline-p.com```precisa estar no Internet Explorer (IE) ou na Zona de Sites Confiáveis de Borda para funcionar. |  | Sites confiáveis |
| 16   |  **FDQNs do Microsoft Teams** <br> Se estiver usando o Internet Explorer ou o Microsoft Edge, é necessário habilitar os cookies primários e de terceiros, adicionar os FQDNs do Teams aos Sites Confiáveis, além de todo o pacote de FQDNs, CDNs e telemetria relacionados na linha 14. Para saber mais, confira o artigo [Problemas conhecidos do Microsoft Teams](/microsoftteams/known-issues). |  | Sites confiáveis |
| 17   |  **FDQNs do SharePoint Online e do OneDrive for Business** <br> Todos os FQDNs do ".sharepoint.com" com o "\<tenant>" no FQDN devem estar no IE do seu cliente ou na Zona de Sites Confiáveis do Edge para funcionar. Além de todo o pacote de FQDNs, CDNs e telemetria listados na linha 14, também é necessário adicionar esses pontos de extremidade. |  | Sites confiáveis |
| 18   | **Yammer**  <br> O Yammer só está disponível no navegador e exige que o usuário esteja autenticado através de um proxy. Todos os FQDNs do Yammer devem estar no IE ou Zona de Sites confiáveis de Borda do cliente para funcionar. |  | Sites confiáveis |
| 19  | Use o [Azure AD Connect](/azure/active-directory/hybrid/) para sincronizar contas de usuários locais com o Azure AD. | Consulte [Portas e Protocolos de Identidade Híbrida Necessários](/azure/active-directory/hybrid/reference-connect-ports), [Solucionar problemas de conectividade do Azure AD](/azure/active-directory/hybrid/tshoot-connect-connectivity) e [Instalação do Agente de Integridade do Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-health-agent-install#outbound-connectivity-to-the-azure-service-endpoints). | Somente o tráfego de servidor de saída |
| 20  | [Azure AD Connect](/azure/active-directory/hybrid/) com 21 ViaNet na China para sincronizar contas de usuários locais com o Azure AD. | \*digicert.com:80 <BR> \*entrust.net:80 <BR> \*chinacloudapi.cn:443 <BR> secure.aadcdn.partner.microsoftonline-p.cn:443 <BR>*.partner.microsoftonline.cn:443 <BR> <BR>Consulte também [Solucionar problemas de ingresso com problemas de conectividade com o Azure AD](https://docs.azure.cn/zh-cn/active-directory/hybrid/tshoot-connect-connectivity). | Somente o tráfego de servidor de saída |
|  21   | Microsoft Stream (necessário o token de usuário do Azure AD). <BR> Office 365 no Mundo (incluindo o GCC) | \*cloudapp.net <BR> \*api.microsoftstream.com <BR> \*notification.api.microsoftstream.com <BR> amp.azure.net <BR> api.microsoftstream.com <BR> az416426.vo.msecnd.net <BR> s0.assets-yammer.com <BR> vortex.data.microsoft.com <BR> web.microsoftstream.com <BR> Porta TCP 443  | Tráfego do servidor de entrada |
| 22  | Use o servidor MFA para solicitações de autenticação multifator; as novas instalações e configurações do servidor com o AD DS (Active Directory Domain Services). | Consulte Como começar com o Servidor de Autenticação [Multifa factor do Azure AD.](/azure/active-directory/authentication/howto-mfaserver-deploy#plan-your-deployment)  | Somente o tráfego de servidor de saída |
| 23  | Notificações de Alteração do Microsoft Graph | Os desenvolvedores podem aproveitar as [notificações de alteração](/graph/webhooks?context=graph%2fapi%2f1.0&view=graph-rest-1.0) para se inscreverem em eventos no Microsoft Graph. | *.cloudapp.net<BR> 104.43.130.21, 137.116.169.230, 13.79.38.63, 104.214.39.228, Public Cloud: 168.63.250.205, 52.161.9.202, 40.68.103.62, 13.89.60.223, 23.100.95.104, 40.113.95.219, 104.214.32.10, 168.63.237.145, 52.161.110.176, 52.174.177.183, 13.85.192.59, 13.85.192.123, 13.86.37.15, 13.89.108.233, 13.89.104.147, 20.44.210.83, 20.44.210.146, 40.76.162.99, 40.76.162.42, 40.74.203.28, 40.74.203.27, 51.104.159.213, 51.104.159.181, 51.124.75.43, 51.124.73.177, 51.138.90.7, 51.138.90.52, 52.139.153.222, 52.139.170.157, 52.139.170.47, 52.142.114.29, 52.142.115.31, 52.147.213.251, 52.147.213.181, 52.148.24.136, 52.148.27.39, 52.148.115.48, 52.148.114.238, 52.154.246.238, 52.159.23.209, 52.159.17.84, 52.184.94.140 <BR> Microsoft Cloud for US Government: 52.244.231.173, 52.238.76.151, 52.244.250.211, 52.238.78.108, 52.243.147.249, 52.243.148.19, 52.243.157.104, 52.243.157.105, 52.244.33.45, 52.244.35.174, 52.244.111.156, 52.244.111.170 <BR> Microsoft Cloud Germany: 51.4.231.136, 51.5.243.223, 51.4.226.154, 51.5.244.215, 51.4.150.206, 51.4.150.235, 51.5.147.130, 51.5.148.103 <BR> Microsoft Cloud China operado pela 21Vianet: 139.219.15.33, 42.159.154.223, 42.159.88.79, 42.159.155.77, 40.72.155.199, 40.72.155.216, 40.125.138.23, 40.125.136.69, 42.159.72.35, 42.159.72.47, 42.159.180.55, 42.159.180.560<BR> Porta TCP 443 <BR> Observação: Os desenvolvedores podem especificar portas diferentes ao criar as assinaturas.  | Tráfego do servidor de entrada |
|||||

## <a name="related-topics"></a>Tópicos Relacionados

[Gerenciar pontos de extremidade do Office 365](managing-office-365-endpoints.md)
  
[Monitorar a conectividade do Microsoft 365](./monitor-connectivity.md)
  
[Conectividade de cliente](https://support.office.com/article/client-connectivity-4232abcf-4ae5-43aa-bfa1-9a078a99c78b)
  
[Redes de distribuição de conteúdo](https://support.office.com/article/content-delivery-networks-0140f704-6614-49bb-aa6c-89b75dcd7f1f)
  
[Intervalos de IP e marcas de serviço do Azure – Nuvem Pública](https://www.microsoft.com/download/details.aspx?id=56519)

[Intervalos de IP e marcas de serviço do Azure – Nuvem governamental dos EUA](https://www.microsoft.com/download/details.aspx?id=57063)

[Intervalos de IP e marcas de serviço do Azure – Nuvem da Alemanha](https://www.microsoft.com/download/details.aspx?id=57064)

[Intervalos de IP e marcas de serviço do Azure – Nuvem da China](https://www.microsoft.com/download/details.aspx?id=57062)
  
[Grupos de notícias públicos da Microsoft](https://www.microsoft.com/download/details.aspx?id=53602)