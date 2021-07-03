---
title: Como configurar o Skype for Business no local para usar a autenticação moderna híbrida
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/3/2019
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 522d5cec-4e1b-4cc3-937f-293570717bc6
ms.collection:
- M365-security-compliance
f1.keywords:
- NOCSH
description: Saiba como configurar o Skype for Business local para usar a HMA (Autenticação Moderna Híbrida), oferecendo a você uma autenticação e autorização de usuário mais seguras.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9695815d0a085931b10f7f64b9fca2e997af9077
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286052"
---
# <a name="how-to-configure-skype-for-business-on-premises-to-use-hybrid-modern-authentication"></a>Como configurar o Skype for Business no local para usar a autenticação moderna híbrida

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

Autenticação Moderna, é um método de gerenciamento de identidade que oferece autenticação e autorização de usuário mais seguras Skype for Business, está disponível para um servidor local e um servidor Exchange local e híbridos de domínio dividido Skype for Business.

 **Importante** Gostaria de saber mais sobre a Autenticação Moderna (MA) e por que você pode preferir usá-la em sua empresa ou organização? Verifique [se este documento](hybrid-modern-auth-overview.md) tem uma visão geral. Se você precisar saber quais Skype for Business as topologias são suportadas com MA, isso está documentado aqui!

 **Antes de começar,** uso estes termos:

- Autenticação Moderna (MA)

- HMA (Autenticação Moderna HÍbrida)

- Exchange local (EXCH)

- Exchange Online (EXO)

- Skype for Business local (SFB)

- Skype for Business Online (SFBO)

Além disso, se um gráfico neste artigo tiver um objeto que está esmaecida ou esmaecida, isso significa que o elemento mostrado em cinza não está incluído na configuração específica do MA. 

## <a name="read-the-summary"></a>Ler o resumo

Este resumo divide o processo em etapas que podem ser perdidas durante a execução e é bom para uma lista de verificação geral manter o controle de onde você está no processo.

1. Primeiro, certifique-se de atender a todos os pré-requisitos.

1. Como muitos **pré-requisitos** são comuns para Skype for Business e Exchange, consulte o artigo de visão geral para sua lista de verificação de [pré-req](hybrid-modern-auth-overview.md). Faça isso  *antes*  de começar qualquer uma das etapas deste artigo.

1. Colete as informações específicas do HMA que você precisará em um arquivo ou OneNote.

1. Ativar a autenticação moderna para EXO (se ela ainda não estiver 2016).

1. Ativar a autenticação moderna para SFBO (se ainda não estiver ligado).

1. Ativar a autenticação moderna híbrida para Exchange local.

1. Ativar a autenticação moderna híbrida para Skype for Business local.

Essas etapas ativarão o MA para SFB, SFBO, EXCH e EXO - ou seja, todos os produtos que podem participar de uma configuração de HMA de SFB e SFBO (incluindo dependências do EXCH/EXO). Em outras palavras, se seus usuários estão em casa/têm caixas de correio criadas em qualquer parte do Híbrido (EXO + SFBO, EXO + SFB, EXCH + SFBO ou EXCH + SFB), seu produto final terá esta aparência:

![Uma topologia Mista 6 Skype HMA para empresas tem MA em todos os quatro locais possíveis.](../media/ab89cdf2-160b-49ac-9b71-0160800acfc8.png)

Como você pode ver, há quatro lugares diferentes para ativar o MA! Para a melhor experiência do usuário, recomendamos ativar o MA em todos os quatro locais. Se você não puder ativar o MA em todos esses locais, ajuste as etapas para ativar o MA somente nos locais necessários para seu ambiente.

Consulte o [tópico Suporte para Skype for Business com MA](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported) para topologias com suporte.

 **Importante** Verifique se você encontrou todos os pré-requisitos antes de começar. Você encontrará essas informações em Visão geral de [autenticação moderna híbrida e pré-requisitos.](hybrid-modern-auth-overview.md)

## <a name="collect-all-hma-specific-info-youll-need"></a>Coletar todas as informações específicas do HMA que você precisará

Depois de verificar duas vezes se [](hybrid-modern-auth-overview.md) você está de acordo com os pré-requisitos para usar a Autenticação Moderna (consulte a observação acima), você deve criar um arquivo para manter as informações necessárias para configurar o HMA nas etapas a seguir. Exemplos usados neste artigo:

- **Domínio SIP/SMTP**

  - Ex. contoso.com (é federado com Office 365)

- **ID do locatário**

  - O GUID que representa seu Office 365 locatário (no logon do contoso.onmicrosoft.com).

- **URLs do Serviço Web do SFB 2015 CU5**

Você precisará de URLs de serviço Web internas e externas para todos os pools SfB 2015 implantados. Para obter isso, execute o seguinte no Shell de Gerenciamento Skype for Business:

```powershell
Get-CsService -WebServer | Select-Object PoolFqdn, InternalFqdn, ExternalFqdn | FL
```

- Ex. Interno: https://lyncwebint01.contoso.com

- Ex. Externo: https://lyncwebext01.contoso.com

Se você estiver usando um servidor Edição Standard, a URL interna ficará em branco. Nesse caso, use o fqdn do pool para a URL interna.

## <a name="turn-on-modern-authentication-for-exo"></a>Ativar autenticação moderna para EXO

Siga as instruções aqui: [Exchange Online: como habilitar seu locatário para autenticação moderna.](https://social.technet.microsoft.com/wiki/contents/articles/32711.exchange-online-how-to-enable-your-tenant-for-modern-authentication.aspx)

## <a name="turn-on-modern-authentication-for-sfbo"></a>Ativar autenticação moderna para SFBO

Siga as instruções aqui: [Skype for Business Online: Habilitar seu locatário para autenticação moderna](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx).

## <a name="turn-on-hybrid-modern-authentication-for-exchange-on-premises"></a>Ativar a Autenticação Moderna Híbrida para Exchange local

Siga as instruções aqui: Como configurar Exchange Server local para [usar a Autenticação Moderna Híbrida.](configure-exchange-server-for-hybrid-modern-authentication.md)

## <a name="turn-on-hybrid-modern-authentication-for-skype-for-business-on-premises"></a>Ativar a Autenticação Moderna Híbrida para Skype for Business local

### <a name="add-on-premises-web-service-urls-as-spns-in-azure-active-directory"></a>Adicionar URLs de serviço Web locais como SPNs no Azure Active Directory

Agora você precisará executar comandos para adicionar as URLs (coletadas anteriormente) como Entidades de Serviço no SFBO.

 **Observação** Os nomes de entidades de serviço (SPNs) identificam os serviços Web e os associam a uma entidade de segurança (como um nome de conta ou grupo) para que o serviço possa agir em nome de um usuário autorizado. Os clientes que estão autenticando em um servidor usam informações contidas em SPNs.

1. Primeiro, conecte-se ao Azure Active Directory (Azure AD) com [estas instruções](/powershell/azure/active-directory/overview).

2. Execute este comando, local, para obter uma lista de URLs do serviço Web SFB.

   Observe que AppPrincipalId começa com `00000004` . Isso corresponde ao Skype for Business Online.

   Anote (e captura de tela para comparação posterior) a saída deste comando, que incluirá um ES e UMA URL WS, mas consiste principalmente em SPNs que começam com `00000004-0000-0ff1-ce00-000000000000/` .

```powershell
Get-MsolServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 | Select -ExpandProperty ServicePrincipalNames
```

3. Se as  URLs SFB internas ou externas do local estão ausentes (por exemplo, e precisamos adicionar esses registros específicos https://lyncwebint01.contoso.com a essa https://lyncwebext01.contoso.com) lista.

    Certifique-se de substituir  *as URLs de* exemplo abaixo por suas URLs reais nos comandos Adicionar!

```powershell
$x= Get-MsolServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
$x.ServicePrincipalnames.Add("https://lyncwebint01.contoso.com/")
$x.ServicePrincipalnames.Add("https://lyncwebext01.contoso.com/")
Set-MSOLServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
```

4. Verifique se os novos registros foram adicionados executando **o comando Get-MsolServicePrincipal** da etapa 2 novamente e verificando a saída. Compare a lista ou a captura de tela de antes com a nova lista de SPNs. Você também pode fazer uma captura de tela da nova lista para seus registros. Se você tiver êxito, verá as duas novas URLs na lista. Em nosso exemplo, a lista de SPNs agora incluirá as URLs específicas https://lyncwebint01.contoso.com e https://lyncwebext01.contoso.com/ .

### <a name="create-the-evosts-auth-server-object"></a>Criar o objeto EvoSTS Auth Server

Execute o seguinte comando no Shell Skype for Business Gerenciamento.

```powershell
New-CsOAuthServer -Identity evoSTS -MetadataURL https://login.windows.net/common/FederationMetadata/2007-06/FederationMetadata.xml -AcceptSecurityIdentifierInformation $true -Type AzureAD
```

### <a name="enable-hybrid-modern-authentication"></a>Habilitar autenticação moderna híbrida

Esta é a etapa que realmente liga o MA. Todas as etapas anteriores podem ser executados com antecedência sem alterar o fluxo de autenticação do cliente. Quando estiver pronto para alterar o fluxo de autenticação, execute este comando no Shell de Gerenciamento Skype for Business.

```powershell
Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity evoSTS
```

## <a name="verify"></a>Verify

Depois de habilitar o HMA, o próximo logon de um cliente usará o novo fluxo de auth. Observe que apenas ativar o HMA não disparará uma reauthentication para qualquer cliente. Os clientes reauthenticam com base no tempo de vida dos tokens de autenticação e/ou certificados que eles têm.

Para testar se o HMA está funcionando depois de habilita-lo, saia de um cliente SFB de teste Windows e clique em "excluir minhas credenciais". Entre novamente. O cliente agora deve usar o fluxo de Auth Moderno e seu logon agora incluirá um **prompt** de Office 365 para uma conta "Trabalho ou escola", visto logo antes de o cliente entrar em contato com o servidor e fazer logon.

Você também deve verificar as "Informações de Configuração" para Skype for Business clientes para uma "Autoridade OAuth". Para fazer isso no computador cliente, segure a tecla CTRL ao mesmo tempo em que você clica com o botão direito do mouse no ícone Skype for Business na bandeja De notificação Windows. Clique **em Informações de** Configuração no menu exibido. Na janela "Skype for Business informações de configuração" que aparecerá na área de trabalho, procure o seguinte:

![As informações de configuração de um cliente Skype for Business usando Autenticação Moderna mostram uma URL de autoridade OAUTH do Lync e do EWS de https://login.windows.net/common/oauth2/authorize .](../media/4e54edf5-c8f8-4e7f-b032-5d413b0232de.png)

Você também deve segurar a tecla CTRL ao mesmo tempo em que clica com o botão direito do mouse no ícone do cliente Outlook (também na bandeja Windows Notificações) e clique em "Status da Conexão". Procure o endereço SMTP do cliente em relação a um tipo AuthN de "Portador", que representa o token de portador usado \* no OAuth.

## <a name="related-articles"></a>Artigos relacionados

[Link back to the Modern Authentication overview](hybrid-modern-auth-overview.md).

Você precisa saber como usar a Autenticação Moderna (ADAL) para seus Skype for Business clientes? Temos etapas [aqui.](./hybrid-modern-auth-overview.md)