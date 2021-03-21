---
title: Como configurar o Exchange Server no local para usar a autenticação moderna híbrida
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 06/16/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: cef3044d-d4cb-4586-8e82-ee97bd3b14ad
ms.collection:
- M365-security-compliance
f1.keywords:
- NOCSH
description: Saiba como configurar um Exchange Server local para usar a Autenticação Moderna HÍbrida (HMA), oferecendo a você uma autenticação e autorização de usuário mais seguras.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 46646f35d3b41821424269f66721fbf829d339f7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928197"
---
# <a name="how-to-configure-exchange-server-on-premises-to-use-hybrid-modern-authentication"></a>Como configurar o Exchange Server no local para usar a autenticação moderna híbrida

*Este artigo se aplica tanto ao Microsoft 365 Enterprise quanto ao Office 365 Enterprise.*

A Autenticação Moderna HÍbrida (HMA) é um método de gerenciamento de identidade que oferece autenticação e autorização de usuário mais seguras e está disponível para implantações híbridas locais do servidor Exchange.

## <a name="fyi"></a>FYI

Antes de começar, eu chamarei:

- HMA de autenticação \> moderna híbrida

- EXCH local do Exchange \>

- EXO do Exchange Online \>

Além disso, se um gráfico neste artigo tiver um objeto que seja "esmaecida" ou "esmaecida", isso significa que o elemento mostrado em cinza não está incluído na configuração específica do *HMA.*

## <a name="enabling-hybrid-modern-authentication"></a>Habilitando a autenticação moderna híbrida

A ação do HMA significa:

1. Certifique-se de atender aos pré-requisitos antes de começar.

1. Como muitos **pré-requisitos** são comuns tanto para o Skype for Business quanto para o Exchange, a visão geral da Autenticação Moderna Híbrida e os pré-requisitos para [usá-lo](hybrid-modern-auth-overview.md)com servidores locais do Skype for Business e do Exchange. Faça isso antes de começar qualquer uma das etapas deste artigo.

1. Adicionando URLs do serviço Web local como **SPNs (Service Principal Names)** no Azure AD.

1. Garantir que todos os Diretórios Virtuais sejam habilitados para HMA

1. Verificando o objeto EvoSTS Auth Server

1. Habilitando o HMA no EXCH.

 **Observação** Sua versão do Office dá suporte a MA? Consulte Como funciona a autenticação moderna para aplicativos [cliente do Office 2013 e office 2016.](modern-auth-for-office-2013-and-2016.md)

## <a name="make-sure-you-meet-all-the-prerequisites"></a>Certifique-se de atender a todos os pré-requisitos

Como muitos pré-requisitos são comuns para o Skype for Business e o Exchange, revise a visão geral da Autenticação Moderna Híbrida e os pré-requisitos para [usá-lo](hybrid-modern-auth-overview.md)com servidores locais do Skype for Business e do Exchange. Faça isso  *antes*  de começar qualquer uma das etapas deste artigo.

## <a name="add-on-premises-web-service-urls-as-spns-in-azure-ad"></a>Adicionar URLs de serviço Web locais como SPNs no Azure AD

Execute os comandos que atribuem as URLs do serviço Web local como SPNs do Azure AD. Os SPNs são usados por máquinas e dispositivos cliente durante a autenticação e a autorização. Todas as URLs que podem ser usadas para se conectar do local ao Azure Active Directory (Azure AD) devem ser registradas no Azure AD (isso inclui namespaces internos e externos).

Primeiro, reúna todas as URLs que você precisa adicionar no AAD. Execute estes comandos no local:

```powershell
Get-MapiVirtualDirectory | FL server,*url*
Get-WebServicesVirtualDirectory | FL server,*url*
Get-ClientAccessServer | fl Name, AutodiscoverServiceInternalUri
Get-OABVirtualDirectory | FL server,*url*
Get-AutodiscoverVirtualDirectory | FL server,*url*
Get-OutlookAnywhere | FL server,*url*
```

Verifique se os clientes URLs aos que podem se conectar estão listados como nomes principais do serviço HTTPS no AAD.

1. Primeiro, conecte-se ao AAD com [estas instruções](connect-to-microsoft-365-powershell.md).

   **Observação** Você precisa usar a _opção Connect-MsolService_ nesta página para poder usar o comando abaixo.

2. Para suas URLs relacionadas ao Exchange, digite o seguinte comando:

   ```powershell
   Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 | select -ExpandProperty ServicePrincipalNames
   ```

   Observe (e captura de tela para comparação posterior) a saída deste comando, que deve incluir uma URL https://  *autodiscover.yourdomain.com*  e https://  *mail.yourdomain.com,* mas consiste principalmente em SPNs que começam com 00000002-0000-0ff1-ce00-000000000000/. Se houver https:// URLs do seu local ausentes, será necessário adicionar esses registros específicos a essa lista.

3. Se você não vir seus registros internos e externos MAPI/HTTP, EWS, ActiveSync, OAB e Descoberta Automática nesta lista, você deverá adicioná-los usando o comando abaixo (as URLs de exemplo são ' e ' ', mas você substituiria as `mail.corp.contoso.com` `owa.contoso.com` **URLs** de exemplo por suas próprias ):

   ```powershell
   $x= Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000
   $x.ServicePrincipalnames.Add("https://mail.corp.contoso.com/")
   $x.ServicePrincipalnames.Add("https://owa.contoso.com/")
   Set-MSOLServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
   ```

4. Verifique se os novos registros foram adicionados executando o comando Get-MsolServicePrincipal da etapa 2 novamente e verificando a saída. Compare a lista/captura de tela de antes com a nova lista de SPNs. Você também pode fazer uma captura de tela da nova lista para seus registros. Se você tiver êxito, verá as duas novas URLs na lista. Em nosso exemplo, a lista de SPNs agora incluirá as URLs específicas  `https://mail.corp.contoso.com`  e  `https://owa.contoso.com` .

## <a name="verify-virtual-directories-are-properly-configured"></a>Verificar se os Diretórios Virtuais estão configurados corretamente

Agora verifique se o OAuth está corretamente habilitado no Exchange em todos os Diretórios Virtuais que o Outlook pode usar executando os seguintes comandos:

```powershell
Get-MapiVirtualDirectory | FL server,*url*,*auth*
Get-WebServicesVirtualDirectory | FL server,*url*,*oauth*
Get-OABVirtualDirectory | FL server,*url*,*oauth*
Get-AutoDiscoverVirtualDirectory | FL server,*oauth*
```

Verifique a saída para verificar se **o OAuth** está habilitado em cada um desses VDirs, ele será parecido com isso (e a chave a ser olhada é 'OAuth'):

```powershell
Get-MapiVirtualDirectory | fl server,*url*,*auth*

Server                        : EX1
InternalUrl                   : https://mail.contoso.com/mapi
ExternalUrl                   : https://mail.contoso.com/mapi
IISAuthenticationMethods      : {Ntlm, OAuth, Negotiate}
InternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
ExternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
```

Se o OAuth estiver ausente de qualquer servidor e de qualquer um dos quatro diretórios virtuais, você precisará adicioná-lo usando os comandos relevantes antes de prosseguir ([Set-MapiVirtualDirectory](/powershell/module/exchange/set-mapivirtualdirectory), [Set-WebServicesVirtualDirectory,](/powershell/module/exchange/set-webservicesvirtualdirectory) [Set-OABVirtualDirectory](/powershell/module/exchange/set-oabvirtualdirectory)e [Set-AutodiscoverVirtualDirectory](/powershell/module/exchange/set-autodiscovervirtualdirectory)).

## <a name="confirm-the-evosts-auth-server-object-is-present"></a>Confirme se o objeto EvoSTS Auth Server está presente

Retorne ao Shell de Gerenciamento do Exchange local para este último comando. Agora você pode validar que seu local tem uma entrada para o provedor de autenticação evoSTS:

```powershell
Get-AuthServer | where {$_.Name -eq "EvoSts"}
```

Sua saída deve mostrar um AuthServer do nome EvoSts e o estado 'Habilitado' deve ser True. Se você não vir isso, baixe e execute a versão mais recente do Assistente de Configuração Híbrida.

 **Importante** Se você estiver executando o Exchange 2010 em seu ambiente, o provedor de autenticação EvoSTS não será criado.

## <a name="enable-hma"></a>Habilitar HMA

Execute o seguinte comando no Shell de Gerenciamento do Exchange, local:

```powershell
Set-AuthServer -Identity EvoSTS -IsDefaultAuthorizationEndpoint $true
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

## <a name="verify"></a>Verify

Depois de habilitar o HMA, o próximo logon de um cliente usará o novo fluxo de auth. Observe que apenas ativar o HMA não disparará uma reauthentication para qualquer cliente. Os clientes reauthenticam com base no tempo de vida dos tokens de autenticação e/ou certificados que eles têm.

Você também deve segurar a tecla CTRL ao mesmo tempo em que clica com o botão direito do mouse no ícone do cliente do Outlook (também na bandeja Notificações do Windows) e clique em "Status da Conexão". Procure o endereço SMTP do cliente em relação a um tipo "Authn" de "Portador", que representa o token de portador usado \* no OAuth.

 **Observação** Precisa configurar o Skype for Business com HMA? Você precisará de dois artigos: um que lista [topologias](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)com suporte e um que mostra como [fazer a configuração](configure-skype-for-business-for-hybrid-modern-authentication.md).

## <a name="using-hybrid-modern-authentication-with-outlook-for-ios-and-android"></a>Usar autenticação moderna híbrida com o Outlook para iOS e Android

Se você for um cliente local usando o servidor Exchange no TCP 443, ignore o processamento de tráfego para os seguintes intervalos DE IP:

```text
52.125.128.0/20
52.127.96.0/23
```

## <a name="related-topics"></a>Tópicos relacionados

[Requisitos de configuração de Autenticação Moderna para transição do Office 365 dedicado/ITAR para vNext](/exchange/troubleshoot/modern-authentication/modern-authentication-configuration)