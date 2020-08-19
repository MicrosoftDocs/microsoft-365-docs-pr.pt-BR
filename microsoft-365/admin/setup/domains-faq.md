---
title: Perguntas frequentes sobre domínios
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 1272bad0-4bd4-4796-8005-67d6fb3afc5a
description: Saiba mais sobre domínios encontrando respostas para suas perguntas frequentes.
ms.openlocfilehash: bb949dbd4e32bb62f10dfd0323df70697fdc5404
ms.sourcegitcommit: 5c16d270c7651c2080a5043d273d979a6fcc75c6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/19/2020
ms.locfileid: "46804191"
---
# <a name="domains-faq"></a>Perguntas frequentes sobre domínios

::: moniker range="o365-21vianet"

> [!NOTE]
> O centro de administração está mudando. Se a sua experiência não corresponder aos detalhes apresentados aqui, consulte [Sobre o novo centro de administração do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Este artigo contém respostas para perguntas frequentes sobre domínios no Microsoft 365.

Se você não encontrar uma resposta para a sua pergunta, deixe um comentário, e a adicionaremos à lista.

Neste artigo

- [O que é prioridade MX?](#what-is-mx-priority)
- [Como posso validar registros SPF para meu domínio?](#how-can-i-validate-spf-records-for-my-domain)
- [O que é um nome de domínio?](#what-is-a-domain-name)
- [O que acontece se meu provedor de DNS não oferecer suporte a determinados tipos de registro?](#what-happens-if-my-dns-provider-doesnt-support-certain-record-types)
- [Como definir ou alterar o domínio padrão no Microsoft 365?](#how-do-i-set-or-change-the-default-domain-in-microsoft-365)
- [Posso adicionar subdomínios personalizados ou vários domínios ao Microsoft 365?](#can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365)
- [Como faço para transferir um domínio da Microsoft 365 para outro host?]
- [Por que eu tenho um domínio "onmicrosoft.com"?](#why-do-i-have-an-onmicrosoftcom-domain)
- [Por que eu tenho um domínio "onmicrosoft.de"?](#why-do-i-have-an-onmicrosoftde-domain)
- [Como verifico meu status de educação ou sem fins lucrativos?](#how-do-i-verify-my-nonprofit-or-education-status)
    
## <a name="what-is-mx-priority"></a>O que é prioridade MX?

O email é entregue ao servidor de mensagens com o número de preferência mais baixo (prioridade mais alta), portanto, o registro MX que você usa para o roteamento de emails deve ter o número de preferência mais baixo, normalmente 0 ou  *alta*  prioridade. 
  
- Quando você cria um registro MX, a maioria dos provedores de Hospedagem de DNS exige que você defina o número de preferência.
    
- Um rótulo é a  *preferência*  de caixa e uma  *prioridade*  de ti de rótulo. 
    
- Alguns exigem um número e alguns pedem que você selecione  *baixo*  ,  *médio*  ou  *alto*  . 
    
- Se você tiver apenas um registro MX, qualquer valor será adequado para prioridade ou preferência.
    
- Se você tiver mais de um, certifique-se de que o registro MX para roteamento de email seja de prioridade maior do que aquele usado para validar que você é o proprietário do domínio.
    
## <a name="how-can-i-validate-spf-records-for-my-domain"></a>Como posso validar registros SPF para meu domínio?

É importante que você tenha ou crie  **apenas um registro txt para SPF**. Se você já tiver um registro SPF, deverá acrescentar os novos valores do Microsoft 365 a ele, em vez de criar um novo. Após adicionar ou atualizar seu registro SPF para o email da Microsoft, você deve verificar se a sintaxe está correta com uma destas ferramentas: 
  
- [Ferramentas de teste de registro SPF](http://www.kitterman.com/spf/validate.html)
    
- [Surveyor SPF](https://dmarcian.com/spf-survey/)
    
- [Interface Web de busca](http://digwebinterface.com/)

## <a name="what-is-a-domain-name"></a>O que é um nome de domínio?

O domínio é um nome exclusivo que é exibido após o sinal de **@** nos endereços de email e após **www.** nos endereços de site. Normalmente, ela assume a forma do nome da sua organização e um sufixo da Internet padrão, como  *yourbusiness.com*  ou  *StateUniversity.edu.* 
  
Usar um domínio personalizado como "**rob \@ contoso.com**" com o Microsoft 365 pode ajudar a criar credibilidade e reconhecimento para a marca. 
  
Você pode [comprar um domínio no Microsoft 365, configurando-o automaticamente](../get-help-with-domains/buy-a-domain-name.md)ou pode comprar ou trazer um que você já possui de um registrador de domínio.
    
## <a name="what-happens-if-my-dns-provider-doesnt-support-certain-record-types"></a>O que acontece se meu provedor de DNS não oferecer suporte a determinados tipos de registro?

Se você gerenciar seus próprios registros DNS e seu host DNS não oferecer suporte a todos os registros DNS que o Microsoft 365 precisa, alguns recursos do Microsoft 365 não funcionarão. Recomendamos que você transfira seu domínio para um registrador que dê suporte a todos os registros DNS necessários.
  
Provedores que oferecem suporte a todos os registros DNS necessários:
  
- Dynadot
    
- eNomCentral
    
- Europe Registry
    
- GoDaddy
    
- Foco
    
- MyHosting.com
    
- Name.com
    
- Fala quase livre
    
- Nettica
    
- Network Information Center (NIC)
    
- Network Solutions
    
- Register.com
  
## <a name="how-do-i-set-or-change-the-default-domain-in-microsoft-365"></a>Como definir ou alterar o domínio padrão no Microsoft 365?

Você deve ter pelo menos um domínio personalizado que tenha adicionado ao Microsoft 365 antes de poder escolher um domínio padrão.

::: moniker range="o365-worldwide"

1. No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.

::: moniker-end

::: moniker range="o365-germany"

1. No centro do administrador, acesse a página **Configurações de** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">domínios</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. No centro do administrador, acesse a página **Configurações de** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">domínios</a>.

::: moniker-end
    
2. Na página **domínios** , selecione o domínio que você deseja definir como o padrão para novos endereços de email. 
    
3. Selecione **Definir como Padrão**.
    
::: moniker range="o365-worldwide"

Não é possível alterar o nome do seu domínio inicial  *. onmicrosoft.com*  . 

::: moniker-end

::: moniker range="o365-germany"

Não é possível alterar o nome do seu domínio inicial  *. onmicrosoft.de*  . 

::: moniker-end

::: moniker range="o365-21vianet"

Não é possível alterar o nome do seu domínio inicial  *. Partner.onmschina.cn*  . 

::: moniker-end

## <a name="can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365"></a>Posso adicionar subdomínios personalizados ou vários domínios ao Microsoft 365?

::: moniker range="o365-worldwide"

Sim. Para adicionar subdomínios, você deve gerenciar suas próprias configurações de DNS no site do registrador. Se você estiver permitindo que a Microsoft gerencie suas configurações de DNS com registros NS ou se comprou o domínio da Microsoft, não será possível adicionar subdomínios.

::: moniker-end

::: moniker range="o365-germany"

Sim! Para adicionar subdomínios, você deve gerenciar suas próprias configurações de DNS no site do registrador. Se você estiver permitindo que a Microsoft gerencie suas configurações de DNS com registros NS ou se comprou o domínio da Microsoft, não será possível adicionar subdomínios.

::: moniker-end

::: moniker range="o365-21vianet"

Sim! Para adicionar subdomínios, você deve gerenciar suas próprias configurações de DNS no site do registrador. Se você estiver permitindo que a 21Vianet gerencie suas configurações de DNS com registros NS, não será possível adicionar subdomínios.

::: moniker-end

Normalmente, você pode adicionar até 900 domínios à sua assinatura do Microsoft 365.
  
Por exemplo, você pode adicionar os domínios contoso.com e contosomarketing.com e, em seguida, adicionar os subdomínios www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com e assim por diante.
  
Quando você adiciona um subdomínio, ele é verificado automaticamente com base no domínio pai que está sendo verificado.
  
Ao adicionar vários domínios ao Microsoft 365, você pode hospedar qualquer um dos serviços (como email) em qualquer um dos domínios que você adicionou.  *Quando você altera seu email para o Microsoft 365, atualizando o registro MX de um domínio, todos os emails enviados para esse domínio serão iniciados no Microsoft 365.* 
 
::: moniker range="o365-worldwide"

> [!NOTE]
> Se você adicionou um domínio do contoso.com a uma assinatura do Microsoft 365, você também pode adicionar o subdomínio xyz.contoso.com a outra organização do Microsoft 365. Ao adicionar o subdomínio, você será solicitado a adicionar um registro TXT no provedor de Hospedagem de DNS.

## <a name="how-do-i-transfer-a-domain-from-microsoft-365-to-another-host"></a>Como transferir um domínio da Microsoft 365 para outro host?

Para obter o procedimento para transferir um domínio, consulte [transferir um domínio da Microsoft para outro host](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/transfer-a-domain-from-microsoft-to-another-host).

## <a name="pilot-microsoft-365-from-my-custom-domain"></a>Piloto do Microsoft 365 a partir do meu domínio personalizado

Para obter o procedimento para testar a funcionalidade de email do Microsoft 365 de um domínio personalizado para uma caixa de correio do Microsoft 365, consulte [piloto da microsoft 365 em meu domínio personalizado](https://docs.microsoft.com/microsoft-365/admin/misc/pilot-microsoft-365-from-my-custom-domain).

## <a name="why-do-i-have-an-onmicrosoftcom-domain"></a>Por que eu tenho um domínio "onmicrosoft.com"?

O Microsoft 365 cria um domínio para você, como o *contoso.onmicrosoft.com*, quando você se inscreve com o serviço. A ID de usuário que você cria ao se inscrever inclui o domínio, como *Alan@contoso.onmicrosoft.com*. 
  
 **Se você deseja que seu email pareça *Alan \@ contoso.com*:** [compre o domínio](../get-help-with-domains/buy-a-domain-name.md) ou apenas siga as etapas em [adicionar seus usuários e domínio ao Microsoft 365](add-domain.md) , caso já o tenha. 
  
- **Não é possível renomear o domínio onmicrosoft após a inscrição.** Por exemplo, se o domínio inicial escolhido foi fourthcoffee.onmicrosoft.com, não será possível alterá-lo para ser fabrikam.onmicrosoft.com. Para usar um domínio onmicrosoft.com diferente, você precisaria iniciar uma nova assinatura com o Microsoft 365. 
    
- **Não é possível renomear a URL do site de equipe.** A URL do site de equipe se baseia no nome de domínio do onmicrosoft.com. Infelizmente, por causa da forma como a arquitetura do SharePoint Online funciona, não é possível renomear o site de equipe. 
    
- **Não é possível remover seu domínio onmicrosoft.** O Microsoft 365 precisa mantê-lo porque é usado em segundo plano para sua assinatura. Mas você não precisa usar o domínio por conta própria depois de ter adicionado um domínio personalizado. 
    
Você pode continuar usando o domínio onmicrosoft.com inicial, mesmo depois de adicionar seu domínio. Ele ainda funciona para email e outros serviços, portanto, é sua escolha.
  
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-do-i-have-an-onmicrosoftde-domain"></a>Por que eu tenho um domínio "onmicrosoft.de"?

O Microsoft 365 cria um domínio para você, como o *contoso.onmicrosoft.de*, quando você se inscreve com o serviço. A ID de usuário que você cria ao se inscrever inclui o domínio, como *Alan@contoso.onmicrosoft.de*. 
  
 **Se você quiser que seu email pareça *Alan@contoso.de*:** [compre o domínio](../get-help-with-domains/buy-a-domain-name.md) ou apenas siga as etapas em [adicionar seus usuários e domínio ao Microsoft 365](add-domain.md) , caso já o tenha. 
  
- **Não é possível renomear o domínio onmicrosoft após a inscrição.** Por exemplo, se o domínio inicial escolhido foi fourthcoffee.onmicrosoft.de, não será possível alterá-lo para ser fabrikam.onmicrosoft.de. Para usar um domínio onmicrosoft.de diferente, você precisaria iniciar uma nova assinatura com o Microsoft 365. 
    
- **Não é possível renomear a URL do site de equipe.** A URL do site de equipe se baseia no nome de domínio do onmicrosoft.de. Infelizmente, por causa da forma como a arquitetura do SharePoint Online funciona, não é possível renomear o site de equipe. 
    
- **Não é possível remover seu domínio onmicrosoft.** O Microsoft 365 precisa mantê-lo porque é usado em segundo plano para sua assinatura. Mas você não precisa usar o domínio por conta própria depois de ter adicionado um domínio personalizado. 
    
Você pode continuar usando o domínio onmicrosoft.de inicial, mesmo depois de adicionar seu domínio. Ele ainda funciona para email e outros serviços, portanto, é sua escolha.
  
::: moniker-end

## <a name="how-do-i-verify-my-nonprofit-or-education-status"></a>Como verifico meu status de educação ou sem fins lucrativos?

1. Selecione **Configurar** no [centro de administração](https://docs.microsoft.com/microsoft-365/admin/admin-home) para iniciar o assistente. (Certifique-se de entrar no Microsoft 365 primeiro). 
    
2. Para se tornar o administrador da sua escola, selecione a opção  **se tornar um administrador** no Microsoft 365. 
    
3. Você será solicitado a adicionar um registro DNS TXT no site de host DNS do seu domínio. Por quê? Como entrar no host DNS e adicionar um registro para o seu domínio, você prova para a Microsoft 365 que é o nome do domínio.
    
4. Depois de adicionar o registro, você voltará para o portal do Microsoft 365 e confirmará que você o adicionou, de modo que a Microsoft 365 possa verificar.
    
Tem uma entidade sem fins lucrativos e deseja obter o Microsoft 365? [Verifique se a sua organização está qualificada](https://www.microsoft.com/en-us/nonprofits/eligibility) e inscreva-se no serviço. 
  
Quer saber mais sobre tornar-se o administrador da sua escola? [Saiba tudo sobre ele](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
).