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
description: Saiba como configurar o Skype for Business local para usar a Autenticação Moderna Híbrida (HMA), oferecendo autenticação e autorização de usuário mais seguras.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 74c8e3e0514fbfd8779c2f65e9c541c33b281c59
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694999"
---
# <a name="how-to-configure-skype-for-business-on-premises-to-use-hybrid-modern-authentication"></a>Como configurar o Skype for Business no local para usar a autenticação moderna híbrida

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

A Autenticação Moderna é um método de gerenciamento de identidade que oferece autenticação e autorização de usuário mais seguras, está disponível para o skype for Business server local e o servidor exchange local e para híbridos de domínio dividido do Skype for Business.
  
 **Importante** Gostaria de saber mais sobre a Autenticação Moderna (MA) e por que você pode preferir usá-la em sua empresa ou organização? Verifique [este documento para](hybrid-modern-auth-overview.md) ter uma visão geral. Se você precisar saber quais topologias do Skype for Business têm suporte com a ma, isso está documentado aqui!
  
 **Antes de começar,** eu uso estes termos:
  
- Autenticação Moderna (MA)

- HMA (Autenticação Moderna Híbrida)

- Exchange local (EXCH)

- Exchange Online (EXO)

- Skype for Business local (SFB)

- Skype for Business Online (SFBO)

Além disso, se um gráfico neste artigo tiver um objeto esmaecida ou  esmaecida ou esmaecida, isso significa que o elemento mostrado em cinza não está incluído na configuração específica do MA.
  
## <a name="read-the-summary"></a>Ler o resumo

Este resumo divide o processo em etapas que, de outra forma, podem se perder durante a execução e é bom que uma lista de verificação geral acompanhe onde você está no processo.
  
1. Primeiro, certifique-se de atender a todos os pré-requisitos.

1. Como muitos **pré-requisitos são** comuns para o Skype for Business e o Exchange, consulte o artigo de visão geral da lista de verificação [pré-requisitos.](hybrid-modern-auth-overview.md) Faça isso  *antes*  de começar qualquer uma das etapas neste artigo.

1. Colete as informações específicas de HMA de que você precisará em um arquivo ou no OneNote.

1. Ativar a autenticação moderna para EXO (caso ainda não tenha sido turned on).

1. Ativar a autenticação moderna para SFBO (se ainda não estiver ligado).

1. Ativar a autenticação moderna híbrida para o Exchange no local.

1. Ativar a autenticação moderna híbrida para o Skype for Business no local.

Essas etapas ativarão o MA para SFB, SFBO, EXCH e EXO, ou seja, todos os produtos que podem participar de uma configuração HMA de SFB e SFBO (incluindo dependências de EXCH/EXO). Em outras palavras, se os usuários estão em/ter caixas de correio criadas em qualquer parte do Híbrido (EXO + SFBO, EXO + SFB, EXCH + SFBO ou EXCH + SFB), seu produto concluído terá esta aparência:
  
![Uma topologia HMA Mista 6 do Skype for Business tem MA em todos os quatro locais possíveis.](../media/ab89cdf2-160b-49ac-9b71-0160800acfc8.png)
  
Como você pode ver, há quatro lugares diferentes para ativar o ma! Para a melhor experiência do usuário, recomendamos ativar a ma em todos os quatro locais. Se não for possível ativar o ma em todos esses locais, ajuste as etapas para ativar o ma somente nos locais necessários para seu ambiente.
  
Consulte o [tópico Suporte do Skype for Business com MA](https://technet.microsoft.com/library/mt803262.aspx) para ver as topologias com suporte.
  
 **Importante** Verifique se você atendeu a todos os pré-requisitos antes de começar. Você encontrará essas informações na visão geral e pré-requisitos da autenticação moderna [híbrida.](hybrid-modern-auth-overview.md)
  
## <a name="collect-all-hma-specific-info-youll-need"></a>Coletar todas as informações específicas de HMA de que você precisará

Depois de verificar se você está [](hybrid-modern-auth-overview.md) de acordo com os pré-requisitos para usar a Autenticação Moderna (veja a observação acima), crie um arquivo para manter as informações necessárias para configurar o HMA nas etapas a seguir. Exemplos usados neste artigo:
  
- **Domínio SIP/SMTP**

  - Por ex. contoso.com (é federado com o Office 365)

- **ID do locatário**

  - O GUID que representa seu locatário do Office 365 (no logon do contoso.onmicrosoft.com).

- **URLs de serviço Web do SFB 2015 CU5**

você precisará de URLs de serviço Web internos e externos para todos os pools do SfB 2015 implantados. Para obter essas informações, execute o seguinte a partir do Shell de Gerenciamento do Skype for Business:
  
```powershell
Get-CsService -WebServer | Select-Object PoolFqdn, InternalFqdn, ExternalFqdn | FL
```

- Por ex. Interno: https://lyncwebint01.contoso.com

- Por ex. Externo: https://lyncwebext01.contoso.com

Se você estiver usando um servidor Standard Edition, a URL interna ficará em branco. Nesse caso, use o fqdn do pool para a URL interna.
  
## <a name="turn-on-modern-authentication-for-exo"></a>Ativar a autenticação moderna para EXO

Siga as instruções aqui: [Exchange Online: como habilitar seu locatário para autenticação moderna.](https://social.technet.microsoft.com/wiki/contents/articles/32711.exchange-online-how-to-enable-your-tenant-for-modern-authentication.aspx)
  
## <a name="turn-on-modern-authentication-for-sfbo"></a>Ativar a autenticação moderna para SFBO

Siga as instruções aqui: [Skype for Business Online: habilitar seu locatário para autenticação moderna.](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)
  
## <a name="turn-on-hybrid-modern-authentication-for-exchange-on-premises"></a>Ativar a autenticação moderna híbrida para o Exchange local

Siga as instruções aqui: Como configurar o Exchange Server local para [usar a Autenticação Moderna Híbrida.](configure-exchange-server-for-hybrid-modern-authentication.md)
  
## <a name="turn-on-hybrid-modern-authentication-for-skype-for-business-on-premises"></a>Ativar a autenticação moderna híbrida para o Skype for Business local

### <a name="add-on-premises-web-service-urls-as-spns-in-azure-active-directory"></a>Adicionar URLs de serviço Web local como SPNs no Azure Active Directory

Agora você precisará executar comandos para adicionar as URLs (coletadas anteriormente) como Entidades de Serviço no SFBO.
  
 **Observação** Os nomes de entidades de serviço (SPNs) identificam serviços Web e os associam a uma entidade de segurança (como um nome de conta ou grupo) para que o serviço possa agir em nome de um usuário autorizado. Os clientes que fazem a autenticação em um servidor usam as informações contidas nos SPNs.
  
1. Primeiro, conecte-se ao Azure Active Directory (Azure AD) com [estas instruções.](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0)

2. Execute este comando, no local, para obter uma lista de URLs de serviço Web SFB.

   Observe que AppPrincipalId começa com `00000004` . Isso corresponde ao Skype for Business Online.

   Anote (e captura de tela para comparação posterior) a saída desse comando, que incluirá uma URL de SE e WS, mas, principalmente, consiste em SPNs que começam com `00000004-0000-0ff1-ce00-000000000000/` .

```powershell
Get-MsolServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 | Select -ExpandProperty ServicePrincipalNames
```

3. Se as  URLs SFB internas ou externas do local não tiverem (por exemplo, e precisaremos adicionar esses registros específicos https://lyncwebint01.contoso.com a essa https://lyncwebext01.contoso.com) lista).

    Certifique-se de  *substituir as URLs de* exemplo abaixo por suas URLs reais nos comandos Adicionar!
  
```powershell
$x= Get-MsolServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
$x.ServicePrincipalnames.Add("https://lyncwebint01.contoso.com/")
$x.ServicePrincipalnames.Add("https://lyncwebext01.contoso.com/")
Set-MSOLServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
```
  
4. Verifique se os novos registros foram adicionados executando o comando **Get-MsolServicePrincipal** da etapa 2 novamente e verificando a saída. Compare a lista ou a captura de tela de antes com a nova lista de SPNs. Você também pode fazer uma captura de tela da nova lista para seus registros. Se você foi bem-sucedido, verá as duas novas URLs na lista. No nosso exemplo, a lista de SPNs agora incluirá as URLs específicas https://lyncwebint01.contoso.com https://lyncwebext01.contoso.com/ e.

### <a name="create-the-evosts-auth-server-object"></a>Criar o objeto de servidor de auth do EvoSTS

Execute o seguinte comando no Shell de Gerenciamento do Skype for Business.
  
```powershell
New-CsOAuthServer -Identity evoSTS -MetadataURL https://login.windows.net/common/FederationMetadata/2007-06/FederationMetadata.xml -AcceptSecurityIdentifierInformation $true -Type AzureAD
```

### <a name="enable-hybrid-modern-authentication"></a>Habilitar a autenticação moderna híbrida

Esta é a etapa que realmente liga a ma. Todas as etapas anteriores podem ser executados com antecedência sem alterar o fluxo de autenticação do cliente. Quando estiver pronto para alterar o fluxo de autenticação, execute este comando no Shell de Gerenciamento do Skype for Business.

```powershell
Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity evoSTS
```

## <a name="verify"></a>Verify

Depois de habilitar o HMA, o próximo logon do cliente usará o novo fluxo de auth. Observe que apenas ativar o HMA não disparará uma nova autenticação para qualquer cliente. Os clientes são autenticados com base no tempo de vida dos tokens de autenticação e/ou certificados que eles têm.
  
Para testar se o HMA está funcionando depois que você o habilitar, saia de um cliente SFB do Windows de teste e clique em 'excluir minhas credenciais'. Entre novamente. Agora, o cliente deve usar o fluxo de Auth Moderno e seu logon incluirá um prompt do **Office 365** para uma conta "Trabalho ou escola", visto logo antes de o cliente entrar em contato com o servidor e fazer logon.
  
Você também deve verificar as "Informações de Configuração" para clientes do Skype for Business em busca de uma "Autoridade OAuth". Para fazer isso no computador cliente, mantenha a tecla CTRL no mesmo momento em que clicar com o botão direito do mouse no ícone do Skype for Business na bandeja de notificação do Windows. Clique **em Informações de** Configuração no menu exibido. Na janela "Informações de Configuração do Skype for Business" que aparecerá na área de trabalho, procure o seguinte:
  
![As informações de configuração de um cliente Skype for Business usando a Autenticação Moderna mostram uma URL de autoridade OAUTH do Lync e do EWS de https://login.windows.net/common/oauth2/authorize .](../media/4e54edf5-c8f8-4e7f-b032-5d413b0232de.png)
  
Você também deve segurar a tecla CTRL ao mesmo tempo em que clica com o botão direito do mouse no ícone do cliente do Outlook (também na bandeja Notificações do Windows) e clique em 'Status da Conexão'. Procure o endereço SMTP do cliente em relação a um tipo de AuthN de "Portador", que representa o token de portador usado \* no OAuth.
  
## <a name="related-articles"></a>Artigos relacionados

[Link de volta para a visão geral da Autenticação Moderna.](hybrid-modern-auth-overview.md)
  
Você precisa saber como usar a Autenticação Moderna (ADAL) para seus clientes do Skype for Business? Temos etapas [aqui.](https://technet.microsoft.com/library/mt710548.aspx)
