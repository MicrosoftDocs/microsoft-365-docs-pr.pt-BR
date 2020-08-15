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
description: Saiba como configurar o Skype for Business no local para usar a protocolo de autenticação moderna (HMA), oferecendo uma autenticação e autorização de usuário mais segura.
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

A autenticação moderna é um método de gerenciamento de identidades que oferece autenticação e autorização de usuário mais seguras, está disponível para o Skype for Business Server local e o Exchange Server local e o Skype-Domain híbridas do Skype for Business.
  
 **Importante** Gostaria de saber mais sobre a autenticação moderna (MA) e por que você pode preferir usá-la em sua empresa ou organização? Consulte [este documento](hybrid-modern-auth-overview.md) para obter uma visão geral. Se você precisa saber quais topologias do Skype for Business são compatíveis com o MA, está documentado aqui!
  
 **Antes de começar**, eu uso estes termos:
  
- Autenticação moderna (MA)

- Autenticação moderna híbrida (HMA)

- Exchange local (EXCH)

- Exchange Online (EXO)

- Skype for Business local (SFB)

- Skype for Business online (SFBO)

Além disso, se um gráfico neste artigo tiver um objeto que está acinzentado ou esmaecido que significa que o elemento mostrado em cinza **não está** incluído na configuração específica do ma.
  
## <a name="read-the-summary"></a>Leia o resumo

Este resumo divide o processo em etapas que podem ser perdidas durante a execução e é bom para uma lista de verificação geral para acompanhar onde você está no processo.
  
1. Primeiro, verifique se você atende a todos os pré-requisitos.

1. Como muitos **pré-requisitos** são comuns para o Skype for Business e o Exchange, [consulte o artigo de visão geral de sua lista de verificação de pré-](hybrid-modern-auth-overview.md)requisito. Faça isso  *antes*  de começar qualquer uma das etapas neste artigo.

1. Colete as informações específicas da HMA necessárias em um arquivo ou no OneNote.

1. Ative a autenticação moderna para o EXO (se ainda não estiver ativada).

1. Ative a autenticação moderna para o SFBO (se ainda não estiver ativada).

1. Ative a autenticação moderna híbrida para o Exchange local.

1. Ative a autenticação moderna híbrida para o Skype for Business no local.

Essas etapas ativam MA para SFB, SFBO, EXCH e EXO-ou seja, todos os produtos que podem participar de uma configuração de HMA de SFB e SFBO (incluindo dependências em EXCH/EXO). Em outras palavras, se seus usuários estiverem hospedados em/têm caixas de correio criadas em qualquer parte do híbrido (EXO + SFBO, EXO + SFB, EXCH + SFBO ou EXCH + SFB), o produto final terá a seguinte aparência:
  
![Uma topologia de HMA 6 do Skype for Business mista tem MA em todos os quatro locais possíveis.](../media/ab89cdf2-160b-49ac-9b71-0160800acfc8.png)
  
Como você pode ver, há quatro lugares diferentes para ativar MA! Para obter a melhor experiência do usuário, recomendamos que você ative o MA nos quatro desses locais. Se você não conseguir ativar o MA em todos esses locais, ajuste as etapas para ativar o MA somente nos locais necessários para o seu ambiente.
  
Consulte o [tópico sobre capacidade de suporte para o Skype for Business com ma](https://technet.microsoft.com/library/mt803262.aspx) para topologias suportadas.
  
 **Importante** Verifique se você atendeu a todos os pré-requisitos antes de começar. Você encontrará essas informações na [visão geral da autenticação moderna híbrida e nos pré-requisitos](hybrid-modern-auth-overview.md).
  
## <a name="collect-all-hma-specific-info-youll-need"></a>Coletar todas as informações específicas da HMA necessárias

Depois de verificar novamente se você atende aos [pré-requisitos](hybrid-modern-auth-overview.md) para usar a autenticação moderna (consulte a observação acima), você deve criar um arquivo para armazenar as informações necessárias para configurar a HMA nas etapas adiante. Exemplos usados neste artigo:
  
- **SIP/domínio SMTP**

  - Ex. contoso.com (é federado com o Office 365)

- **ID do locatário**

  - O GUID que representa o locatário do Office 365 (no logon de contoso.onmicrosoft.com).

- **SFB 2015 CU5 Web Service URLs**

Você precisará de URLs de serviços Web internos e externos para todos os pools do SfB 2015 implantados. Para obtê-los, execute o seguinte no Shell de gerenciamento do Skype for Business:
  
```powershell
Get-CsService -WebServer | Select-Object PoolFqdn, InternalFqdn, ExternalFqdn | FL
```

- Ex. Internamente https://lyncwebint01.contoso.com

- Ex. Externo https://lyncwebext01.contoso.com

Se você estiver usando um servidor Standard Edition, a URL interna ficará em branco. Nesse caso, use o FQDN do pool para a URL interna.
  
## <a name="turn-on-modern-authentication-for-exo"></a>Ativar a autenticação moderna para o EXO

Siga as instruções aqui: [Exchange Online: como habilitar seu locatário para autenticação moderna.](https://social.technet.microsoft.com/wiki/contents/articles/32711.exchange-online-how-to-enable-your-tenant-for-modern-authentication.aspx)
  
## <a name="turn-on-modern-authentication-for-sfbo"></a>Ativar a autenticação moderna para o SFBO

Siga as instruções aqui: [Skype for Business Online: habilitar seu locatário para autenticação moderna](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx).
  
## <a name="turn-on-hybrid-modern-authentication-for-exchange-on-premises"></a>Ativar a autenticação moderna híbrida para o Exchange local

Siga as instruções aqui: [como configurar o Exchange Server no local para usar a autenticação moderna híbrida](configure-exchange-server-for-hybrid-modern-authentication.md).
  
## <a name="turn-on-hybrid-modern-authentication-for-skype-for-business-on-premises"></a>Ativar a autenticação moderna híbrida para o Skype for Business no local

### <a name="add-on-premises-web-service-urls-as-spns-in-azure-active-directory"></a>Adicionar URLs de serviços Web locais como SPNs no Azure Active Directory

Agora, você precisará executar comandos para adicionar as URLs (coletadas anteriormente) como entidades de serviço no SFBO.
  
 **Observação** Os SPNs (nomes de entidade de serviço) identificam os serviços Web e os associam a um objeto de segurança (como um nome de conta ou grupo) para que o serviço possa atuar em nome de um usuário autorizado. Os clientes que se autenticam em um servidor fazem uso de informações contidas em SPNs.
  
1. Primeiro, conecte-se ao Azure Active Directory (Azure AD) com [estas instruções](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).

2. Execute este comando, no local, para obter uma lista de URLs de serviços Web do SFB.

   Observe que o AppPrincipalId começa com `00000004` . Isso corresponde ao Skype for Business online.

   Anote (e captura de tela para comparação posterior) a saída desse comando, que incluirá uma URL SE e um WS, mas que basicamente consiste em SPNs que começam com `00000004-0000-0ff1-ce00-000000000000/` .

```powershell
Get-MsolServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 | Select -ExpandProperty ServicePrincipalNames
```

3. Se as URLs de SFB internas **ou** externas do local estiverem ausentes (por exemplo, https://lyncwebint01.contoso.com e https://lyncwebext01.contoso.com) precisaremos adicionar esses registros específicos a essa lista.

    Certifique-se de substituir  *as URLs de exemplo* abaixo por suas URLs reais nos comandos Add!
  
```powershell
$x= Get-MsolServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
$x.ServicePrincipalnames.Add("https://lyncwebint01.contoso.com/")
$x.ServicePrincipalnames.Add("https://lyncwebext01.contoso.com/")
Set-MSOLServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
```
  
4. Verifique se os novos registros foram adicionados executando o comando **Get-MsolServicePrincipal** da etapa 2 novamente e examinando a saída. Compare a lista ou captura de tela antes da nova lista de SPNs. Você também pode capturar a nova lista para seus registros. Se você tiver êxito, verá as duas novas URLs na lista. Indo em nosso exemplo, a lista de SPNs agora incluirá as URLs específicas https://lyncwebint01.contoso.com e https://lyncwebext01.contoso.com/ .

### <a name="create-the-evosts-auth-server-object"></a>Criar o objeto de servidor de autenticação EvoSTS

Execute o seguinte comando no Shell de gerenciamento do Skype for Business.
  
```powershell
New-CsOAuthServer -Identity evoSTS -MetadataURL https://login.windows.net/common/FederationMetadata/2007-06/FederationMetadata.xml -AcceptSecurityIdentifierInformation $true -Type AzureAD
```

### <a name="enable-hybrid-modern-authentication"></a>Habilitar a autenticação moderna híbrida

Esta é a etapa que realmente ativa MA. Todas as etapas anteriores podem ser executadas antecipadamente sem alterar o fluxo de autenticação do cliente. Quando estiver pronto para alterar o fluxo de autenticação, execute este comando no Shell de gerenciamento do Skype for Business.

```powershell
Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity evoSTS
```

## <a name="verify"></a>Verify

Depois de habilitar a HMA, o próximo login de um cliente usará o novo fluxo de autenticação. Observe que apenas a ativação da HMA não acionará uma nova autenticação para qualquer cliente. Os clientes são autenticados com base no tempo de vida dos tokens de autenticação e/ou certs que eles têm.
  
Para testar se a HMA está funcionando depois de tê-la habilitado, saia do SFB de teste do cliente Windows e certifique-se de clicar em excluir minhas credenciais. Entre novamente. Agora, o cliente deve usar o fluxo de autenticação moderna e seu logon incluirá um prompt do **Office 365** para uma conta de ' trabalho ou escola ', visto imediatamente antes de o cliente entrar em contato com o servidor e fizer o login.
  
Você também deve verificar as ' informações de configuração ' para clientes do Skype for Business para uma ' autoridade OAuth '. Para fazer isso no computador cliente, pressione a tecla CTRL ao mesmo tempo em que você clica com o botão direito do mouse no ícone do Skype for Business na bandeja de notificação do Windows. Clique em **informações de configuração** no menu exibido. Na janela ' informações de configuração do Skype for Business ' que aparecerá na área de trabalho, procure o seguinte:
  
![As informações de configuração de um cliente Skype for Business usando a autenticação moderna mostra uma URL de autoridade OAUTH do Lync e EWS de https://login.windows.net/common/oauth2/authorize .](../media/4e54edf5-c8f8-4e7f-b032-5d413b0232de.png)
  
Você também deve manter pressionada a tecla CTRL ao mesmo tempo em que clicar com o botão direito do mouse no ícone do cliente Outlook (também na bandeja de notificações do Windows) e clicar em "status da conexão". Procure o endereço SMTP do cliente em relação a um tipo Authn de ' portador \* ', que representa o token de portador usado no OAuth.
  
## <a name="related-articles"></a>Artigos relacionados

[Link de volta para a visão geral da autenticação moderna](hybrid-modern-auth-overview.md).
  
Você precisa saber como usar a ADAL (autenticação moderna) para os clientes do Skype for Business? Temos as etapas [aqui](https://technet.microsoft.com/library/mt710548.aspx).
