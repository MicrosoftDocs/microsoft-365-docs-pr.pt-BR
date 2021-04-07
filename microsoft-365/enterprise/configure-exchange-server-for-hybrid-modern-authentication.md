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
ms.openlocfilehash: e0a0e521f4ac81a8aa113b2e945045d31f2c1952
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599494"
---
# <a name="how-to-configure-exchange-server-on-premises-to-use-hybrid-modern-authentication"></a>Como configurar o Exchange Server no local para usar a autenticação moderna híbrida

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

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

1. Adicionando URLs do serviço Web local como **SPNs (Service Principal Names)** no Azure AD. Caso o EXCH seja híbrido com vários **locatários,** essas URLs do serviço Web local devem ser adicionadas como SPNs no Azure AD de todos os locatários que estão híbridos com o EXCH.

1. Garantir que todos os Diretórios Virtuais sejam habilitados para HMA

1. Verificando o objeto EvoSTS Auth Server

1. Habilitando o HMA no EXCH.

> [!NOTE]
> Sua versão do Office dá suporte a MA? Consulte Como funciona a autenticação moderna para aplicativos [cliente do Office 2013 e office 2016.](modern-auth-for-office-2013-and-2016.md)


## <a name="make-sure-you-meet-all-the-prerequisites"></a>Certifique-se de atender a todos os pré-requisitos

Como muitos pré-requisitos são comuns para o Skype for Business e o Exchange, revise a visão geral da Autenticação Moderna Híbrida e os pré-requisitos para [usá-lo](hybrid-modern-auth-overview.md)com servidores locais do Skype for Business e do Exchange. Faça isso  *antes*  de começar qualquer uma das etapas deste artigo.

> [!NOTE]
> O Outlook Web App e o Painel de Controle do Exchange não funcionam com autenticação moderna híbrida.

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

Verifique se os clientes URLs aos que podem se conectar estão listados como nomes principais do serviço HTTPS no AAD. Caso o EXCH seja híbrido com vários **locatários,** esses SPNs HTTPS devem ser adicionados ao AAD de todos os locatários híbridos com o EXCH.

1. Primeiro, conecte-se ao AAD com [estas instruções](connect-to-microsoft-365-powershell.md).

    > [!NOTE]
    > Você precisa usar a _opção Connect-MsolService_ nesta página para poder usar o comando abaixo.

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

> [!NOTE]
> Caso o EXCH seja híbrido com vários **locatários,** sua saída deverá mostrar um AuthServer do Name EvoSts - {GUID} para cada locatário em híbrido com EXCH e o estado 'Habilitado' deve ser True para todos esses objetos AuthServer.

 **Importante** Se você estiver executando o Exchange 2010 em seu ambiente, o provedor de autenticação EvoSTS não será criado.

## <a name="enable-hma"></a>Habilitar HMA

Execute o seguinte comando no Shell de Gerenciamento do Exchange, local:

```powershell
Set-AuthServer -Identity EvoSTS -IsDefaultAuthorizationEndpoint $true
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

Se a versão do EXCH for Exchange 2016 (CU18 ou superior) ou Exchange 2019 (CU7 ou superior) e híbrida tiver sido configurada com HCW baixada após setembro de 2020, execute o seguinte comando no Shell de Gerenciamento do Exchange, local:

```powershell
Set-AuthServer -Identity "EvoSTS - {GUID}" -Domain "Tenant Domain" -IsDefaultAuthorizationEndpoint $true
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

> [!NOTE]
> Caso o EXCH seja híbrido com vários **locatários,** há vários objetos AuthServer presentes no EXCH com domínios correspondentes a cada locatário.  O **sinalizador IsDefaultAuthorizationEndpoint** deve ser definido como true (usando o cmdlet **IsDefaultAuthorizationEndpoint)** para qualquer um desses objetos AuthServer. Esse sinalizador não pode ser definido como true para todos os objetos Authserver e o HMA estaria habilitado, mesmo se um desses sinalizadores do objeto AuthServer **IsDefaultAuthorizationEndpoint** estivesse definido como true.

## <a name="verify"></a>Verify

Depois de habilitar o HMA, o próximo logon de um cliente usará o novo fluxo de auth. Observe que apenas ativar o HMA não disparará uma reauthentication para qualquer cliente. Os clientes reauthenticam com base no tempo de vida dos tokens de autenticação e/ou certificados que eles têm.

Você também deve segurar a tecla CTRL ao mesmo tempo em que clica com o botão direito do mouse no ícone do cliente do Outlook (também na bandeja Notificações do Windows) e clique em "Status da Conexão". Procure o endereço SMTP do cliente em relação a um tipo "Authn" de "Portador", que representa o token de portador usado \* no OAuth.

> [!NOTE]
> Precisa configurar o Skype for Business com HMA? Você precisará de dois artigos: um que lista [topologias](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)com suporte e um que mostra como [fazer a configuração](configure-skype-for-business-for-hybrid-modern-authentication.md).


## <a name="using-hybrid-modern-authentication-with-outlook-for-ios-and-android"></a>Usar autenticação moderna híbrida com o Outlook para iOS e Android

Se você for um cliente local usando o servidor Exchange no TCP 443, ignore o processamento de tráfego para os seguintes intervalos de endereços IP:

```
52.125.128.0/20
52.127.96.0/23
```

O aplicativo do Outlook para iOS e Android foi projetado como a melhor maneira de experimentar o Microsoft 365 ou o Office 365 em seu dispositivo móvel usando os serviços da Microsoft para ajudar a encontrar, planejar e priorizar sua vida diária e trabalho. Para obter mais informações, consulte [Using hybrid Modern Authentication with Outlook for iOS and Android](https://docs.microsoft.com/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth?view=exchserver-2019).

## <a name="related-topics"></a>Tópicos relacionados

[Requisitos de configuração de Autenticação Moderna para transição do Office 365 dedicado/ITAR para vNext](/exchange/troubleshoot/modern-authentication/modern-authentication-configuration)
