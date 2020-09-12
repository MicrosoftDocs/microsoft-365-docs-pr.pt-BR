---
title: Visão geral da Autenticação Moderna Híbrida e pré-requisitos para seu uso com servidores locais do Skype for Business e do Exchange
ms.author: kvice
ms.reviewer: smithre4
author: kelleyvice-msft
manager: laurawi
ms.date: 04/15/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.assetid: ef753b32-7251-4c9e-b442-1a5aec14e58d
ms.collection:
- M365-security-compliance
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
description: Neste artigo, você aprenderá sobre a autenticação moderna híbrida e os pré-requisitos para o uso com o Skype for Business e os servidores do Exchange locais.
ms.openlocfilehash: 1e0330bd62d9098f11a12b44b46e9ace30b59420
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546439"
---
# <a name="hybrid-modern-authentication-overview-and-prerequisites-for-using-it-with-on-premises-skype-for-business-and-exchange-servers"></a>Visão geral da Autenticação Moderna Híbrida e pré-requisitos para usá-la com servidores locais do Skype for Business e do Exchange

*Este artigo se aplica tanto ao Microsoft 365 Enterprise quanto ao Office 365 Enterprise.*

A _Autenticação Moderna_ é um método de gerenciamento de identidades que oferece autenticação e autorização de usuários mais seguras. Está disponível para implantações híbridas do Office 365 para servidores do Skype for business e do Exchange no local, e também para híbridos do Skype for Business com domínio dividido. Este artigo contém links para documentos a ele relacionados sobre pré-requisitos, configuração/desativação da autenticação moderna e para algumas informações de clientes relacionados (por exemplo: clientes de Outlook e Skype).

- [O que é autenticação moderna?](hybrid-modern-auth-overview.md#BKMK_WhatisModAuth)
- [O que muda quando eu uso a autenticação moderna?](hybrid-modern-auth-overview.md#BKMK_WhatChanges)
- [Verifique o status da autenticação moderna do seu ambiente no local](hybrid-modern-auth-overview.md#BKMK_CheckStatus)
- [Você cumpre os pré-requisitos da autenticação moderna?](#do-you-meet-modern-authentication-prerequisites)
- [O que mais preciso saber antes de começar?](hybrid-modern-auth-overview.md#BKMK_Whatelse)

## <a name="what-is-modern-authentication"></a>O que é autenticação moderna?
<a name="BKMK_WhatisModAuth"> </a>

Autenticação moderna é um termo guarda-chuva para uma combinação de métodos de autenticação e autorização entre um cliente (por exemplo, seu laptop ou seu celular) e um servidor, além de algumas medidas de segurança que confiam em políticas de acesso com as quais talvez você já esteja familiarizado. Ela inclui:

- **Métodos de autenticação**: autenticação multifator (MFA); autenticação por cartão inteligente; autenticação baseada no certificado do cliente
- **Métodos de autorização**: implementação da Open Authorization (OAuth) pela Microsoft
- **Políticas de acesso condicional**: Gerenciamento de Aplicativos Móveis (MAM) e Acesso Condicional ao Azure Active Directory (Azure AD)

O gerenciamento das identidades de usuário com a autenticação moderna proporciona aos administradores muitas ferramentas diferentes que podem ser usadas para a proteção de recursos e oferece métodos mais seguros de gerenciamento de identidades, tanto para o ambiente no local (Exchange e Skype for Business), quanto para os ambientes do Exchange híbrido e do Skype for Business híbrido/com domínio dividido.

Esteja ciente de que, devido ao fato de que o Skype for Business funciona em proximidade com o Exchange, o comportamento de login visto pelos usuários do cliente Skype for Business será afetado pelo status da autenticação moderna do Exchange. Isso também ocorrerá se você tiver uma arquitetura híbrida do Skype for Business com _domínio dividido_, na qual você tenha tanto o Skype for Business Online quanto o Skype for Business no local, com os usuários abrigados em ambos os locais.

Para obter mais informações sobre a autenticação moderna no Office 365, confira o artigo [Suporte aos Aplicativos Clientes do Office 365 — Autenticação Moderna](microsoft-365-client-support-modern-authentication.md).

> [!IMPORTANT]
> A partir de agosto de 2017, todos os locatários do novo Office 365 que incluíam o Skype for Business online e o Exchange online passaram a ter a autenticação moderna habilitada por padrão. Os locatários pré-existentes não tiveram uma alteração no seu estado de AM padrão, mas todos os novos locatários são compatíveis automaticamente com o conjunto de recursos de identidade ampliados que você pode ver listado acima. Para verificar seu status de AM, confira a seção [Verificar o status da autenticação moderna do seu ambiente no local](hybrid-modern-auth-overview.md#BKMK_CheckStatus).

## <a name="what-changes-when-i-use-modern-authentication"></a>O que muda quando eu uso a autenticação moderna?
<a name="BKMK_WhatChanges"> </a>

Quando você usa a autenticação moderna com o Skype for Business ou Exchange Server no local, você continua *autenticando* os usuários no local, mas a forma de *autorizar* seu acesso aos recursos (como arquivos ou emails) muda. Por esta razão, embora a autenticação moderna trate da comunicação entre cliente e servidor, as etapas utilizadas na configuração da AM resultam na configuração do evoSTS (um Serviço de Token de Segurança usado pelo Azure AD) como Auth Server do Skype for Business e do Exchange Server no local.

A mudança para o evoSTS permite que seus servidores no local tirem proveito do OAuth (emissão de token) para autorizar seus clientes, além de permitir que o seu local utilize métodos de segurança que são comuns na nuvem (como a autenticação multifator). Além disso, o evoSTS emite tokens que permitem que os usuários solicitem acesso aos recursos sem fornecer sua senha como parte da solicitação. Independentemente de onde seus usuários estejam abrigados (online ou no local) e de qual dos locais hospede o recurso necessário, o evoSTS se tornará o núcleo da autorização de usuários e clientes após a autenticação moderna ter sido configurada.

Por exemplo, se precisar de acesso ao Exchange Server para obter informações do calendário em nome de um usuário, um cliente do Skype for Business usará a Biblioteca de Autenticação do Active Directory (ADAL) para fazê-lo. A ADAL é a biblioteca de códigos criada para disponibilizar os recursos seguros do seu diretório aos aplicativos clientes usando tokens de segurança OAuth. A ADAL trabalha com o OAuth para verificar reivindicações e trocar tokens (ao invés de senhas) para conceder a um usuário o acesso a um recurso. No passado, a autoridade em uma transação desse tipo — o servidor que sabe como validar as reivindicações de usuários e emitir os tokens necessários — poderia ter sido um Serviço de Tokens de Segurança no local ou até mesmo um Serviço de Federação do Active Directory. A autenticação moderna, porém, centraliza essa autoridade usando o Azure AD.

Isso também significa que, embora seus ambientes do Exchange Server e do Skype for Business possam estar totalmente no local, o servidor de autorização estará online, e seu ambiente local deve ter a capacidade de criar e manter uma conexão com sua assinatura do Office 365 na nuvem (e a instância do Azure AD que sua assinatura usa como diretório).

O que não muda? Não importa se você está em um híbrido de domínio dividido ou usando o Skype for Business e o Exchange Server no local: todos os usuários devem em primeiro lugar autenticar *no local*. Em uma implementação híbrida da autenticação moderna, tanto a _Lyncdiscovery_ quanto a _Autodiscovery_ apontam para um servidor no local.

> [!IMPORTANT]
> Se você precisar saber quais são as topologias específicas do Skype for Business compatíveis com a AM, essa informação está [documentada aqui](https://technet.microsoft.com/library/mt803262.aspx).

## <a name="check-the-modern-authentication-status-of-your-on-premises-environment"></a>Verificar o status da autenticação moderna do seu ambiente no local
<a name="BKMK_CheckStatus"> </a>

Devido ao fato de que a autenticação moderna muda o servidor de autorização utilizado quando os serviços aproveitam o OAuth/S2S, você precisa saber se a autenticação moderna está habilitada ou desabilitada para os seus ambientes do Skype for Business e do Exchange no local. Você pode verificar o status dos seus servidores do Exchange executando o seguinte comando do PowerShell:

```powershell
Get-OrganizationConfig | ft OAuth*
```

Se o valor da propriedade _OAuth2ClientProfileEnabled_ for **False**, isso significa que a autenticação moderna está desabilitada.

Para obter mais informações sobre o cmdlet Get-OrganizationConfig, confira [Get-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/get-organizationconfig).

Você pode fazer uma verificação dos seus servidores do Skype for Business executando o seguinte comando do PowerShell:

```powershell
Get-CSOAuthConfiguration
```

Se o comando retornar uma propriedade _OAuthServers_ vazia ou se o valor da propriedade _ClientADALAuthOverride_ não for **Allowed**, isso significa que a autenticação moderna está desabilitada.

Para obter mais informações sobre o cmdlet Get-CsOAuthConfiguration, veja [Get-CsOAuthConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csoauthconfiguration).

## <a name="do-you-meet-modern-authentication-prerequisites"></a>Você cumpre os pré-requisitos da autenticação moderna?

Verifique e marque esses itens na sua lista de verificação antes de continuar:

- **Específicos para o Skype for Business**
  - Todos os servidores devem ter a atualização cumulativa de maio de 2017 (CU5) do Skype for Business Server 2015 ou posterior
    - **Exceção**: o Survivability Branch Appliance (SBA) pode estar na versão atual (baseada no Lync 2013)
  - Seu domínio SIP foi adicionado como um domínio Federado no Office 365
  - Todos os front-ends do SFB devem ter as conexões de saída com a internet e com os URLs de Autenticação do Office 365 (TCP 443) e CRLs de certificados raiz bem conhecidas (TCP 80) listadas nas Linhas 56 e 125 da seção “Microsoft 365 Common e Office” das [faixas de endereços de IP e URLs do Office 365](urls-and-ip-address-ranges.md). 

- **Skype for Business no local em um ambiente híbrido do Office 365**
  - Uma implantação do Skype for Business 2019 com todos os servidores executando o Skype for Business 2019.
  - Uma implantação do Skype for Business 2015 com todos os servidores executando o Skype for Business 2015.
  - Uma implantação com um máximo de duas versões de servidor diferentes conforme listado abaixo:
    - Skype for Business Server 2015
    - Skype for Business Server 2019
  - Todos os servidores do Skype for Business devem ter as atualizações cumulativas mais recentes instaladas. Consulte as [atualizações de servidor do Skype for Business](https://docs.microsoft.com/skypeforbusiness/sfb-server-updates) para localizar e gerenciar todas as atualizações disponíveis.
  - Não existe nenhum Lync Server 2010 ou 2013 no ambiente híbrido.

>[!NOTE]
>Se os servidores de front-end do seu Skype for Business usam um servidor proxy para ter acesso à internet, o IP e o número da Porta do servidor proxy devem ser inseridos na seção de configuração do arquivo web.config para cada front-end.

- C:\Program Files\Skype for Business Server 2015\Web Components\Web ticket\int\web.config
- C:\Program Files\Skype for Business Server 2015\Web Components\Web ticket\ext\web.config

```xml
<configuration>
  <system.net>
    <defaultProxy>
      <proxy
        proxyaddress="https://192.168.100.60:8080"
        bypassonlocal="true" />
    </defaultProxy>
  </system.net>
</configuration>
```

> [!IMPORTANT]
> Certifique-se de assinar um feed RSS para as [faixas de endereços de IP e URLs do Office 365](urls-and-ip-address-ranges.md) para se manter atualizado quanto às listas mais recentes dos URLs obrigatórios.

- **Específicos para o Exchange Server**
  - Você deve estar usando o Exchange Server 2013 CU19 e acima, o Exchange Server 2016 CU8 e acima ou o Exchange Server 2019 CU1 e acima.
  - Não existe nenhum Exchange Server 2010 no ambiente.
  - O SSL Offloading não está configurado. A terminação SSL e a recriptografia são suportadas.
  - Caso o seu ambiente utilize uma infraestrutura de servidor proxy para permitir que os servidores se conectem à internet, certifique-se de que todos os servidores do Exchange tenham um servidor proxy definido na propriedade [InternetWebProxy](https://technet.microsoft.com/library/bb123716%28v=exchg.160%29.aspx).

- **Exchange Server no local em um ambiente híbrido do Office 365**

  - Se você está usando o Exchange Server 2013, pelo menos um dos servidores deve ter as funções de servidor de Caixa de Correio e de Acesso para Cliente instaladas. Embora seja possível instalar as funções de Caixa de Correio e Acesso para Cliente em servidores separados, recomendamos fortemente que você instale ambas as funções no mesmo servidor para proporcionar maior confiabilidade e um desempenho aprimorado.
  - Se você está usando a versão do Exchange Server 2016 ou posterior, pelo menos um dos servidores deve ter a função de servidor de Caixa de Correio instalada.
  - Não existe nenhum Exchange Server 2007 ou 2010 no ambiente híbrido.
  - Todos os servidores do Exchange devem ter as atualizações cumulativas mais recentes instaladas. Consulte o artigo [Atualizar o Exchange com as atualizações cumulativas mais recentes](https://docs.microsoft.com/exchange/plan-and-deploy/install-cumulative-updates?view=exchserver-2019) para localizar e gerenciar todas as atualizações disponíveis.

- **Requisitos de cliente e de protocolo do Exchange**

  - Os seguintes clientes são compatíveis com a autenticação moderna:

  |**Clientes**|**Protocolo principal**|**Observações**|
  |:-----|:-----|:-----|
  |Outlook 2013 e Outlook 2016  <br/> |MAPI sobre HTTP  <br/> |O MAPI sobre HTTP deve estar habilitado no Exchange para ser possível aproveitar a autenticação moderna com esses clientes (geralmente habilitado ou True para as novas instalações do Exchange 2013 Service Pack 1 e acima). Para obter mais informações, confira o artigo [Como a autenticação moderna funciona para o Office 2013 e para os aplicativos clientes do Office 2016](modern-auth-for-office-2013-and-2016.md).  <br/> Certifique-se de estar rodando o build mínimo obrigatório do Outlook; confira as [Atualizações mais recentes das versões do Outlook que utilizam o Windows Installer (MSI)](https://docs.microsoft.com/officeupdates/outlook-updates-msi).  <br/> |
  |Outlook 2016 para Mac  <br/> |Serviços de Web do Exchange  <br/> |  <br/> |
  |Outlook para iOS e Android  <br/> |  <br/> |Confira o artigo [Como usar a autenticação moderna híbrida com o Outlook para iOS e Android](https://docs.microsoft.com/Exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth) para obter mais informações.  <br/> |
  |Clientes do Exchange ActiveSync (por exemplo, Mail do iOS 11)  <br/> |Exchange ActiveSync  <br/> |Para os clientes do Exchange ActiveSync compatíveis com a autenticação moderna, é preciso recriar o perfil para migrar da autenticação básica para a autenticação moderna.  <br/> |

- **Pré-requisitos gerais**
  - Se você usa o AD FS, é preciso ter o Windows 2012 R2 AD FS 3.0 e acima para os serviços de federação.
  - Suas configurações de identidade devem ser de um dos tipos suportados pelo Azure AD Connect, como a sincronização de criptografia de senha, a autenticação pass-through e um STS no local suportado pelo Office 365.
  - Você deve ter o Azure AD Connect configurado e funcionando para a replicação e sincronização de usuários.
  - Você deve ter verificado que o híbrido foi configurado usando o modo de Topologia Híbrida Clássica do Exchange entre os seus ambientes no local e o Office 365. Uma declaração oficial de suporte do híbrido do Exchange afirma que você deve ter a CU atual ou a CU -1 atual.
    > [!NOTE]
    > A autenticação moderna híbrida não é compatível com o [Agente Híbrido](https://docs.microsoft.com/exchange/hybrid-deployment/hybrid-agent).

  - Certifique-se de que tanto um usuário de teste no local quanto um usuário de teste híbrido abrigado no Office 365 podem entrar no cliente de desktop do Skype for Business (se você quiser usar a autenticação moderna com o Skype) e no Microsoft Outlook (se você quiser usar a autenticação moderna com o Exchange).

## <a name="what-else-do-i-need-to-know-before-i-begin"></a>O que mais preciso saber antes de começar?
<a name="BKMK_Whatelse"> </a>

- Todos os cenários de servidores locais envolvem a configuração da autenticação moderna no local (na verdade, para o Skype for Business existe uma lista de topologias suportadas) de forma que o servidor responsável pela autenticação e autorização esteja na nuvem da Microsoft (o serviço de tokens de segurança do Azure AD, chamado "evoSTS") e a atualização do Azure AD quanto aos URLs ou namespaces usados pela sua instalação local do Skype for Business ou do Exchange. Portanto, os servidores no local devem aceitar uma dependência da nuvem da Microsoft. O fato de se adotar essa medida pode ser considerado como uma configuração de “autorização híbrida”.
- Este artigo contém links para outros que irão ajudá-lo a escolher as topologias compatíveis com a autenticação moderna (necessárias apenas para o Skype for Business) e para artigos do tipo “como fazer” que descrevem as etapas de configuração, ou as etapas para desabilitar a autenticação moderna para o Exchange no local e o Skype for Business no local. Adicione esta página aos favoritos do seu navegador se você acha que irá precisar de uma base inicial para utilizar a autenticação moderna no seu ambiente de servidor.

## <a name="related-topics"></a>Tópicos Relacionados
<a name="BKMK_URLListforMA"> </a>

- [Como configurar o Exchange Server no local para usar a Autenticação Moderna](configure-exchange-server-for-hybrid-modern-authentication.md)
- [Topologias do Skype for Business compatíveis com a Autenticação Moderna](https://technet.microsoft.com/library/mt803262.aspx)
- [Como configurar o Skype for Business no local para usar a Autenticação Moderna](configure-skype-for-business-for-hybrid-modern-authentication.md)
- [Como remover ou desabilitar a Autenticação Moderna Híbrida do Skype for Business e do Exchange](remove-or-disable-hybrid-modern-authentication-from-skype-for-business-and-excha.md)
