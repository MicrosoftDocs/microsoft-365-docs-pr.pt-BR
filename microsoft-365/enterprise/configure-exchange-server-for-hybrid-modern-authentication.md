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
description: Saiba como configurar um servidor Exchange local para usar a protocolo de autenticação moderna (HMA), oferecendo uma autenticação e autorização de usuário mais segura.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8db74c04335e0846666991d74980648cedb4d9d7
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547125"
---
# <a name="how-to-configure-exchange-server-on-premises-to-use-hybrid-modern-authentication"></a>Como configurar o Exchange Server no local para usar a autenticação moderna híbrida

*Este artigo se aplica tanto ao Microsoft 365 Enterprise quanto ao Office 365 Enterprise.*

A HMA moderna (autenticação moderna híbrida) é um método de gerenciamento de identidades que oferece autenticação e autorização de usuário mais seguras e está disponível para implantações híbridas locais do Exchange Server.

## <a name="fyi"></a>CONHECIMENTO

Antes de começar, chamo:

- HMA de autenticação moderna híbrida \>

- \>Exchange local

- EXO do Exchange Online \>

Além disso, *se um gráfico neste artigo tiver um objeto que é ' esmaecido ' ou ' esmaecido ' que significa que o elemento mostrado em cinza não está incluído na configuração específica da HMA* .

## <a name="enabling-hybrid-modern-authentication"></a>Habilitar a autenticação moderna híbrida

Virar a HMA em significa:

1. Ter certeza de que você atende ao pré antes de começar.

1. Como muitos **pré-requisitos** são comuns para o Skype for Business e o Exchange, a [visão geral da autenticação moderna híbrida e os pré-requisitos para usá-lo com o Skype for Business e servidores do Exchange locais](hybrid-modern-auth-overview.md). Faça isso antes de começar qualquer uma das etapas neste artigo.

1. Adicionar URLs do serviço Web local como **nomes de entidade de serviço (SPNs)** no Azure AD.

1. Garantir que todos os diretórios virtuais estejam habilitados para a HMA

1. Verificando o objeto do servidor de autenticação EvoSTS

1. Habilitando HMA no EXCH.

 **Observação** Sua versão do Office oferece suporte ao MA? Veja [como a autenticação moderna funciona para aplicativos cliente do office 2013 e office 2016](modern-auth-for-office-2013-and-2016.md).

## <a name="make-sure-you-meet-all-the-prerequisites"></a>Verifique se você atende a todos os pré-requisitos

Como muitos pré-requisitos são comuns para o Skype for Business e o Exchange, revise a [visão geral da autenticação moderna híbrida e os pré-requisitos para usá-lo com o Skype for Business e os servidores do Exchange locais](hybrid-modern-auth-overview.md). Faça isso  *antes*  de começar qualquer uma das etapas neste artigo.

## <a name="add-on-premises-web-service-urls-as-spns-in-azure-ad"></a>Adicionar URLs do serviço Web local como SPNs no Azure AD

Execute os comandos que atribuem as URLs do serviço Web local como SPNs do Azure AD. Os SPNs são usados por máquinas clientes e dispositivos durante a autenticação e autorização. Todas as URLs que podem ser usadas para se conectar a partir do local para o Azure Active Directory (Azure AD) devem ser registradas no Azure AD (isso inclui namespaces internos e externos).

Primeiro, reúna todas as URLs que você precisa adicionar no AAD. Execute estes comandos no local:

```powershell
Get-MapiVirtualDirectory | FL server,*url*
Get-WebServicesVirtualDirectory | FL server,*url*
Get-ClientAccessServer | fl Name, AutodiscoverServiceInternalUri
Get-OABVirtualDirectory | FL server,*url*
Get-AutodiscoverVirtualDirectory | FL server,*url*
Get-OutlookAnywhere | FL server,*url*
```

Verifique se os clientes URLs que podem se conectar estão listados como nomes de entidade de serviço HTTPS no AAD.

1. Primeiro, conecte-se ao AAD com [estas instruções](connect-to-microsoft-365-powershell.md).

   **Observação** Você precisa usar a opção _Connect-MsolService_ desta página para poder usar o comando a seguir.

2. Para suas URLs relacionadas ao Exchange, digite o seguinte comando:

   ```powershell
   Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 | select -ExpandProperty ServicePrincipalNames
   ```

   Anote (e captura de tela para comparação posterior) a saída desse comando, que deve incluir uma URL https://  *autodiscover.yourdomain.com*  e https://  *mail.yourdomain.com* , mas que basicamente consiste em SPNs que começam com 00000002-0000-0ff1-ce00-000000000000/. Se houver https://URLs de seu local que estão ausentes, precisaremos adicionar esses registros específicos a essa lista.

3. Se você não vir seus registros internos e externos de MAPI/HTTP, EWS, ActiveSync, OAB e descoberta automática nesta lista, você deve adicioná-los usando o comando a seguir (as URLs de exemplo são ' `mail.corp.contoso.com` ' e ' `owa.contoso.com` ', mas você **substituirá as URLs de exemplo por suas próprias** ):

   ```powershell
   $x= Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000
   $x.ServicePrincipalnames.Add("https://mail.corp.contoso.com/")
   $x.ServicePrincipalnames.Add("https://owa.contoso.com/")
   Set-MSOLServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
   ```

4. Verifique se os novos registros foram adicionados executando o comando Get-MsolServicePrincipal da etapa 2 novamente e examinando a saída. Compare a lista/captura de tela antes da nova lista de SPNs (você também pode capturar a nova lista para seus registros). Se você tiver êxito, verá as duas novas URLs na lista. Indo em nosso exemplo, a lista de SPNs agora incluirá as URLs específicas  `https://mail.corp.contoso.com`  e  `https://owa.contoso.com` .

## <a name="verify-virtual-directories-are-properly-configured"></a>Verificar se os diretórios virtuais estão configurados corretamente

Agora, verifique se o OAuth está habilitado corretamente no Exchange em todos os diretórios virtuais que o Outlook pode usar executando os seguintes comandos:

```powershell
Get-MapiVirtualDirectory | FL server,*url*,*auth*
Get-WebServicesVirtualDirectory | FL server,*url*,*oauth*
Get-OABVirtualDirectory | FL server,*url*,*oauth*
Get-AutoDiscoverVirtualDirectory | FL server,*oauth*
```

Verifique a saída para certificar-se de que o **OAuth** está habilitado em cada um desses VDirss, ele terá a seguinte aparência (e o principal aspecto a ser examinado é ' OAuth '):

```powershell
Get-MapiVirtualDirectory | fl server,*url*,*auth*

Server                        : EX1
InternalUrl                   : https://mail.contoso.com/mapi
ExternalUrl                   : https://mail.contoso.com/mapi
IISAuthenticationMethods      : {Ntlm, OAuth, Negotiate}
InternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
ExternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
```

Se o OAuth estiver ausente de qualquer servidor e de qualquer um dos quatro diretórios virtuais, você precisará adicioná-lo usando os comandos relevantes antes de proceder ([set-MapiVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-mapivirtualdirectory), [Set-WebServicesVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-webservicesvirtualdirectory), [Set-OABVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-oabvirtualdirectory)e [Set-AutoDiscoverVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-autodiscovervirtualdirectory)).

## <a name="confirm-the-evosts-auth-server-object-is-present"></a>Confirmar se o objeto de servidor de autenticação EvoSTS está presente

Retorne ao Shell de gerenciamento do Exchange local para este último comando. Agora você pode validar que seu local tem uma entrada para o provedor de autenticação do evoSTS:

```powershell
Get-AuthServer | where {$_.Name -eq "EvoSts"}
```

A saída deve mostrar um AuthServer do nome EvoSts e o estado ' Enabled ' deve ser true. Se você não vir isso, baixe e execute a versão mais recente do assistente de configuração híbrida.

 **Importante** Se você estiver executando o Exchange 2010 em seu ambiente, o provedor de autenticação do EvoSTS não será criado.

## <a name="enable-hma"></a>Habilitar HMA

Execute o seguinte comando no Shell de gerenciamento do Exchange, no local:

```powershell
Set-AuthServer -Identity EvoSTS -IsDefaultAuthorizationEndpoint $true
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

## <a name="verify"></a>Verify

Depois de habilitar a HMA, o próximo login de um cliente usará o novo fluxo de autenticação. Observe que apenas a ativação da HMA não acionará uma nova autenticação para qualquer cliente. Os clientes são autenticados novamente com base no tempo de vida dos tokens de autenticação e/ou certs que possuem.

Você também deve manter pressionada a tecla CTRL enquanto clica com o botão direito do mouse no ícone do cliente Outlook (também na bandeja de notificações do Windows) e clique em "status da conexão". Procure o endereço SMTP do cliente em relação a um tipo "Authn" de "portador \* ", que representa o token de portador usado no OAuth.

 **Observação** Precisa configurar o Skype for Business com a HMA? Você precisará de dois artigos: um que lista as [topologias suportadas](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)e uma que mostra [como fazer a configuração](configure-skype-for-business-for-hybrid-modern-authentication.md).

## <a name="using-hybrid-modern-authentication-with-outlook-for-ios-and-android"></a>Usar autenticação moderna híbrida com o Outlook para iOS e Android

Se você for um cliente local usando o Exchange Server no TCP 443, leia os seguintes intervalos IP:

```text
52.125.128.0/20
52.127.96.0/23
```

## <a name="related-topics"></a>Tópicos relacionados

[Requisitos de configuração de autenticação moderna para transição do Office 365 dedicada/ITAR para o vNext](https://docs.microsoft.com/exchange/troubleshoot/modern-authentication/modern-authentication-configuration)
