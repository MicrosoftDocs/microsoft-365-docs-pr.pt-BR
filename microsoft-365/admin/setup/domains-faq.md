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
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 1272bad0-4bd4-4796-8005-67d6fb3afc5a
description: Saiba mais sobre domínios encontrando respostas para suas perguntas em perguntas frequentes.
ms.custom: okr_smb
ms.openlocfilehash: 1af20ed0052a7bb4f98072a7142bf7e112b8305e
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2020
ms.locfileid: "44327107"
---
# <a name="domains-faq"></a>Perguntas frequentes sobre domínios

::: moniker range="o365-21vianet"

> [!NOTE]
> O centro de administração está mudando. Se a sua experiência não corresponder aos detalhes apresentados aqui, consulte [Sobre o novo centro de administração do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Este artigo contém respostas para perguntas frequentes sobre domínios no Office 365.

Se você não encontrar uma resposta para a sua pergunta, deixe um comentário, e a adicionaremos à lista.
    
## <a name="what-is-mx-priority"></a>O que é prioridade MX?

O email é entregue ao servidor de mensagens com o número de preferência mais baixo (prioridade mais alta), portanto, o registro MX que você usa para o roteamento de emails deve ter o número de preferência mais baixo, normalmente 0 ou *alta* prioridade. 
  
- Quando você cria um registro MX, a maioria dos provedores de Hospedagem de DNS exige que você defina o número de preferência.
    
- Um rótulo é a *preferência* de caixa e uma *prioridade* de ti de rótulo. 
    
- Alguns exigem um número e alguns pedem que você selecione *baixo* , *médio* ou *alto* . 
    
- Se você tiver apenas um registro MX, qualquer valor será adequado para prioridade ou preferência.
    
- Se você tiver mais de um, certifique-se de que o registro MX para roteamento de email seja de prioridade maior do que aquele usado para validar que você é o proprietário do domínio.
    
## <a name="how-can-i-validate-spf-records-for-my-domain"></a>Como posso validar registros SPF para meu domínio?

É importante que você tenha ou crie **apenas um registro txt para SPF**. Se você já tiver um registro SPF, deverá acrescentar os novos valores do Office 365 a ele, em vez de criar um novo. Após adicionar ou atualizar seu registro SPF para o email da Microsoft, você deve verificar se a sintaxe está correta com uma destas ferramentas: 
  
- [Ferramentas de teste de registro SPF](http://www.kitterman.com/spf/validate.html)
    
- [Surveyor SPF](https://dmarcian.com/spf-survey/)
    
- [Interface Web de busca](http://digwebinterface.com/)
    
## <a name="how-does-office-365-manage-my-dns-records"></a>Como o Office 365 gerencia meus registros de DNS?

Há duas opções para o gerenciamento de DNS com o Office 365:
  
1. Você altera os registros de nameserver (NS) e a Microsoft cuida de todos os registros específicos de serviço, como configurar seu registro MX para email. **Recomenda**
    
2. Você mesmo adiciona registros DNS para email e outros serviços do Office 365 no seu host DNS. **(Apenas especialistas)**
    
### <a name="office-365-creates-and-hosts-the-dns-records"></a>O Office 365 cria e hospeda os registros DNS 
**Vantagens** 
- Você não precisa se preocupar em cometer erros nos valores inseridos para os registros DNS dos serviços do Office 365.  
- Você tem mais flexibilidade em sua escolha de registradores de domínio e host DNS. 
- Qualquer provedor que permita alterar os registros de nameserver funcionará, mesmo se o provedor não oferecer suporte a todos os tipos de registros necessários.   
- Quando o Office 365 adiciona novos registros DNS, não é necessário fazer atualizações.  

#### <a name="disadvantages"></a>Desvantagens 
- Não é possível alterar seus registros DNS para hospedar email fora do Office 365. 
- Se você já usa um site público com seu domínio para seu endereço, como o www.fourthcoffee.com, você deve redirecionar as pessoas para esse endereço do Office 365. 
- Configurar o redirecionamento requer um endereço IP estático, que nem sempre é facilmente disponível para sites públicos. – Se seu registrador de domínio atual não permitir que você altere os registros de nameserver do seu domínio, você terá que alternar para um registrador diferente para usar essa opção de gerenciamento de DNS.  

 ### <a name="you-manage-the-dns-records-yourself"></a>Você mesmo gerencia os registros DNS 
 #### <a name="advantages"></a>Vantagens
- Você controla os registros DNS dos serviços do Office 365.   
- Se você tiver um site público com seu domínio para seu endereço, como o www.fourthcoffee.com, não precisará se preocupar em usar o redirecionamento para garantir que as pessoas ainda possam acessar seu site depois de configurar seu domínio no Office 365.    
- Você tem a flexibilidade de hospedar emails em outro lugar, como com um servidor Exchange local.  
 
#### <a name="disadvantages"></a>Desvantagens
Você precisa configurar os registros DNS para os serviços do Office 365 por conta própria (a menos que tenha um domínio GoDaddy). 
-  Se o seu host DNS atual não oferecer suporte a todos os tipos de registros necessários para o Microsoft 365, alguns recursos não estarão disponíveis e talvez seja necessário mudar para um host DNS diferente. 
- Quando o Office 365 altera os requisitos para registros DNS ou adiciona novos serviços, você precisa fazer as atualizações em seu host DNS. 
   
## <a name="what-is-a-domain-name"></a>O que é um nome de domínio?


O domínio é um nome exclusivo que é exibido após o sinal de **@** nos endereços de email e após **www.** nos endereços de site. Normalmente, ela assume a forma do nome da sua organização e um sufixo da Internet padrão, como *yourbusiness.com* ou *StateUniversity.edu.* 
  
Usar um domínio personalizado como "**rob \@ contoso.com**" com o Office 365 pode ajudar a criar credibilidade e reconhecimento para a marca. 
  
Você pode [comprar um domínio no Office 365 e o configuraremos automaticamente](../get-help-with-domains/buy-a-domain-name.md), ou você pode comprar ou trazer um que você já possui de um registrador de domínio.
  
## <a name="can-i-transfer-a-domain-i-purchased-from-microsoft-to-another-provider"></a>É possível transferir um domínio que comprei da Microsoft para outro provedor?

Sim, mas não é possível transferir um domínio do Office 365 para outro registrador até 60 dias após você comprá-lo com o Office 365.

Observe que uma consulta *whois* mostrará um registrador de domínios comprados do Office 365 como domínios com o selvagem LLC. No entanto, somente o Office 365 deve ser contatado em relação ao seu domínio do Office 365 comprado.
  
Siga as etapas abaixo para obter o código no Office 365 e, em seguida, vá para o site do outro registrador de domínio para configurar a transferência do seu nome de domínio para esse registrador.

::: moniker range="o365-worldwide"

1. No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.

::: moniker-end

::: moniker range="o365-germany"

1. No centro do administrador, acesse a página **Configurações de** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">domínios</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. No centro de administração, vá para a página de licenças de **configurações** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a> .

::: moniker-end
    
2. Na página **domínios** , selecione o domínio do Office 365 que você deseja transferir para outro registrador de domínio e, em seguida, selecione **transferência**de domínio  >  **habilitar transferência**de domínio.
       
4. Siga as etapas para se preparar para transferir seu domínio.
    
5. Depois de obter o código, vá para o site do registrador de domínio no qual você deseja gerenciar o nome de domínio em frente e siga as instruções para transferir um domínio (pesquise ajuda no site).
    
6. Se você precisar ver o código novamente, na página **configurações de domínio** no Office 365, selecione **Exibir código de autorização para transferência de domínio**.
    
7. Após a conclusão da transferência, você renovará seu domínio no novo registrador de domínio.
    
8. Para concluir o processo, volte para a página **domínios** do centro de administração e selecione **completa transferência de domínio**. 

*Observação: Observe que os domínios comprados do Office 365 não estão qualificados para alterações no servidor de nomes ou transferência do domínio entre os locatários do Office 365.  Se uma dessas opções for obrigatória, o registro de domínio precisará ser transferido para outro registrador.*
    
## <a name="how-do-i-change-how-my-dns-records-are-managed-in-office-365"></a>Como alterar a forma como os registros DNS são gerenciados no Office 365?

### <a name="change-dns-management-to-a-dns-host-outside-office-365"></a>Alterar o gerenciamento de DNS para um host DNS fora do Office 365
   
1. Entre no registrador de domínio do seu domínio.
    
2. Encontre a área no site do registrador onde você atualiza os registros Nameservers e atualize os nameservers para apontar para o host DNS do seu domínio. (Geralmente, o host DNS é o registrador de domínio).
    
3. Siga um link para acessar o assistente de configuração de domínios:

::: moniker range="o365-worldwide"

4. No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.

::: moniker-end

::: moniker range="o365-germany"

4. No centro do administrador, acesse a página **Configurações de** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">domínios</a>.

::: moniker-end

::: moniker range="o365-21vianet"

4. No centro do administrador, acesse a página **Configurações de** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">domínios</a>.

::: moniker-end
    
5. Na página **domínios** , selecione o domínio que você está alternando e selecione **Gerenciamento de DNS**.
    
6. No assistente de configuração de domínios, na página **configurar seus serviços online** , selecione **gerenciar meus próprios registros DNS**e, em seguida, selecione **Avançar**.
    
7. Adicionar os registros DNS sugeridos pelo assistente na página **Atualizar configurações de DNS** para o site do registrador. 
    
8. Depois de adicionar os registros, volte para o Office 365 e selecione **verificar**.
    

### <a name="change-dns-management-to-office-365"></a>Alterar o gerenciamento de DNS para o Office 365

::: moniker range="o365-worldwide"

1. No centro de administração, vá para a página de domínios de **configurações** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> ..

::: moniker-end

::: moniker range="o365-germany"

1. No centro do administrador, acesse a página **Configurações de** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">domínios</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. No centro do administrador, acesse a página **Configurações de** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">domínios</a>.

::: moniker-end
    
2. Na página **domínios** , selecione o domínio que você está alternando e selecione **Gerenciamento de DNS**.
    
3. No assistente de configuração de domínios, na página **configurar seus serviços online** , selecione **Configurar meus serviços online para mim. (Recomendado)** e, em seguida, selecione **Avançar**.
    
4. Se você ainda não verificou o domínio, siga as etapas para fazer isso primeiro.
    
5. Na página **Atualizar configurações de DNS** , listamos os nameservers para o Office 365. Vá para o registrador de domínio do seu domínio e atualize os nameservers para os nameservers do Office 365. 
    
4. Depois de atualizar os nameservers, **aguarde pelo menos uma hora**. Em seguida, novamente no assistente do Office 365, selecione **verificar**.
    
## <a name="what-happens-if-my-dns-provider-doesnt-support-certain-record-types"></a>O que acontece se meu provedor de DNS não oferecer suporte a determinados tipos de registro?

Se você gerenciar seus próprios registros DNS e seu host DNS não oferecer suporte a todos os registros DNS que o Office 365 precisa, alguns recursos do Office 365 não funcionarão. Recomendamos que você transfira seu domínio para um registrador que dê suporte a todos os registros DNS necessários.
  
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
    
 **Se não houver suporte para registros SRV**, os seguintes recursos do Office 365 não estarão disponíveis: 
  
- Integração de IM e presença do Skype for Business online com o Outlook Web App
    
- Comunicação externa (Federação) com usuários do Skype for Business online em outras organizações.
    
- Public Internet Connectivity (PIC) com usuários do Skype for Business online conectados com uma conta da Microsoft (conhecida anteriormente como Windows Live ID).
    
 **Se não houver suporte para vários registros CNAME,** você terá que escolher entre os seguintes recursos para o Skype for Business Online: 
  
- Os clientes de área de trabalho de email e clientes móveis podem usar a descoberta automática para localizar automaticamente o serviço do Exchange Online, de modo que os usuários possam entrar sem precisar inserir um nome de servidor.
    
- Os clientes de área de trabalho do Skype for Business Online podem usar a descoberta automática para localizar automaticamente o serviço Skype for Business Online, de modo que os usuários possam entrar sem precisar inserir um nome de servidor.
    
- Os clientes móveis do Skype for Business Online podem usar a descoberta automática para localizar automaticamente o serviço Skype for Business Online, de modo que os usuários possam entrar sem precisar inserir um nome de servidor.

- Federação do Microsoft Teams com o Skype for Business, seja no local ou online. Para obter mais informações, consulte [preparar a rede da sua organização para o Microsoft Teams](https://docs.microsoft.com/microsoftteams/prepare-network).
    
 **Se não houver suporte para registros SPF/txt**, outras pessoas poderão usar seu domínio para enviar spam ou outros emails mal-intencionados. Os registros SPF funcionam identificando os servidores que estão autorizados a enviar emails do seu domínio. 
  
## <a name="how-do-i-set-or-change-the-default-domain-in-office-365"></a>Como faço para definir ou alterar o domínio padrão no Office 365?

Você deve ter pelo menos um domínio personalizado que tenha adicionado ao Office 365 antes de poder escolher um domínio padrão.

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

Não é possível alterar o nome do seu domínio inicial *. onmicrosoft.com* . 

::: moniker-end

::: moniker range="o365-germany"

Não é possível alterar o nome do seu domínio inicial *. onmicrosoft.de* . 

::: moniker-end

::: moniker range="o365-21vianet"

Não é possível alterar o nome do seu domínio inicial *. Partner.onmschina.cn* . 

::: moniker-end

## <a name="can-i-add-custom-subdomains-or-multiple-domains-to-office-365"></a>Posso adicionar subdomínios personalizados ou vários domínios ao Office 365?

::: moniker range="o365-worldwide"

Sim! Para adicionar subdomínios, você deve gerenciar suas próprias configurações de DNS no site do registrador. Se você estiver permitindo que a Microsoft gerencie suas configurações de DNS com registros NS ou se comprou o domínio da Microsoft, não será possível adicionar subdomínios.

::: moniker-end

::: moniker range="o365-germany"

Sim! Para adicionar subdomínios, você deve gerenciar suas próprias configurações de DNS no site do registrador. Se você estiver permitindo que a Microsoft gerencie suas configurações de DNS com registros NS ou se comprou o domínio da Microsoft, não será possível adicionar subdomínios.

::: moniker-end

::: moniker range="o365-21vianet"

Sim! Para adicionar subdomínios, você deve gerenciar suas próprias configurações de DNS no site do registrador. Se você estiver permitindo que a 21Vianet gerencie suas configurações de DNS com registros NS, não será possível adicionar subdomínios.

::: moniker-end

Normalmente, você pode adicionar até 900 domínios à sua assinatura do Office 365.
  
Por exemplo, você pode adicionar os domínios contoso.com e contosomarketing.com e, em seguida, adicionar os subdomínios www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com e assim por diante.
  
Quando você adiciona um subdomínio, ele é verificado automaticamente com base no domínio pai que está sendo verificado.
  
Ao adicionar vários domínios ao Office 365, você pode hospedar qualquer um dos serviços (como email) em qualquer um dos domínios que você adicionou.  *Quando você altera seu email para o Office 365, atualizando o registro MX de um domínio, todos os emails enviados para esse domínio serão iniciados no Office 365.* 
 
::: moniker range="o365-worldwide"

> [!NOTE]
> Se você já tiver adicionado um domínio do contoso.com a um locatário do Office 365, você também pode adicionar o subdomínio xyz.contoso.com a outro locatário do Office 365. Ao adicionar o subdomínio, você será solicitado a adicionar um registro TXT no provedor de Hospedagem de DNS.

## <a name="why-do-i-have-an-onmicrosoftcom-domain"></a>Por que eu tenho um domínio "onmicrosoft.com"?

O Office 365 cria um domínio para você, como o *contoso.onmicrosoft.com*, quando você se inscreve com o serviço. A ID de usuário que você cria ao se inscrever inclui o domínio, como *Alan@contoso.onmicrosoft.com*. 
  
 **Se você deseja que seu email pareça *Alan \@ contoso.com*:** [compre o domínio](../get-help-with-domains/buy-a-domain-name.md) ou apenas siga as etapas em [adicionar seus usuários e domínio ao Office 365,](add-domain.md) se você já o possui. 
  
- **Não é possível renomear o domínio onmicrosoft após a inscrição.** Por exemplo, se o domínio inicial escolhido foi fourthcoffee.onmicrosoft.com, não será possível alterá-lo para ser fabrikam.onmicrosoft.com. Para usar um domínio onmicrosoft.com diferente, você terá que iniciar uma nova assinatura com o Office 365. 
    
- **Não é possível renomear a URL do site de equipe.** A URL do site de equipe se baseia no nome de domínio do onmicrosoft.com. Infelizmente, por causa da forma como a arquitetura do SharePoint Online funciona, não é possível renomear o site de equipe. 
    
- **Não é possível remover seu domínio onmicrosoft.** O Office 365 precisa mantê-lo por conta própria, pois é usado em segundo plano para sua assinatura. Mas você não precisa usar o domínio por conta própria depois de ter adicionado um domínio personalizado. 
    
Você pode continuar usando o domínio onmicrosoft.com inicial, mesmo depois de adicionar seu domínio. Ele ainda funciona para email e outros serviços, portanto, é sua escolha.
  
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-do-i-have-an-onmicrosoftde-domain"></a>Por que eu tenho um domínio "onmicrosoft.de"?

O Office 365 cria um domínio para você, como o *contoso.onmicrosoft.de*, quando você se inscreve com o serviço. A ID de usuário que você cria ao se inscrever inclui o domínio, como *Alan@contoso.onmicrosoft.de*. 
  
 **Se você deseja que seu email pareça *Alan@contoso.de*:** [compre o domínio](../get-help-with-domains/buy-a-domain-name.md) ou apenas siga as etapas em [adicionar seus usuários e domínio ao Office 365](add-domain.md) , se você já o possui. 
  
- **Não é possível renomear o domínio onmicrosoft após a inscrição.** Por exemplo, se o domínio inicial escolhido foi fourthcoffee.onmicrosoft.de, não será possível alterá-lo para ser fabrikam.onmicrosoft.de. Para usar um domínio onmicrosoft.de diferente, você terá que iniciar uma nova assinatura com o Office 365. 
    
- **Não é possível renomear a URL do site de equipe.** A URL do site de equipe se baseia no nome de domínio do onmicrosoft.de. Infelizmente, por causa da forma como a arquitetura do SharePoint Online funciona, não é possível renomear o site de equipe. 
    
- **Não é possível remover seu domínio onmicrosoft.** O Office 365 precisa mantê-lo por conta própria, pois é usado em segundo plano para sua assinatura. Mas você não precisa usar o domínio por conta própria depois de ter adicionado um domínio personalizado. 
    
Você pode continuar usando o domínio onmicrosoft.de inicial, mesmo depois de adicionar seu domínio. Ele ainda funciona para email e outros serviços, portanto, é sua escolha.
  
::: moniker-end

## <a name="how-do-i-verify-my-nonprofit-or-education-status"></a>Como verifico meu status de educação ou sem fins lucrativos?

1. Selecione **Configurar** no [centro de administração](https://docs.microsoft.com/microsoft-365/admin/admin-home) para iniciar o assistente. (Certifique-se de entrar no Office 365 primeiro.) 
    
2. Para se tornar o administrador da sua escola, selecione a opção **se tornar um administrador** no Office 365. 
    
3. Você será solicitado a adicionar um registro DNS TXT no site de host DNS do seu domínio. Por quê? Como entrar no host DNS e adicionar um registro para seu domínio, você prova ao Office 365 que é o proprietário do nome de domínio.
    
4. Depois de adicionar o registro, você voltará para o portal do Office 365 e confirmará que você o adicionou, para que o Office 365 possa verificar.
    
Tem uma entidade sem fins lucrativos e deseja obter o Office 365? [Verifique se a sua organização está qualificada](https://www.microsoft.com/en-us/nonprofits/eligibility) e inscreva-se no serviço. 
  
Quer saber mais sobre tornar-se o administrador da sua escola? [Saiba tudo sobre ele](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
).
  
## <a name="can-i-pilot-office-365-with-just-a-few-email-addresses-from-my-custom-domain"></a>Posso fazer um piloto do Office 365 com apenas alguns endereços de email do meu domínio personalizado?

Você pode, mas há limitações:
  
- Seu provedor de email atual deve fornecer encaminhamento de email.
    
- Você precisa gerenciar seus registros DNS relacionados ao Office 365 em seu provedor de hospedagem DNS, em vez de ter o Office 365 gerenciá-los para você. Para saber o que isso envolve, confira adicionar seu domínio ao Office 365 quando quiser gerenciar seus próprios registros DNS.
    
- Alguns recursos do Office 365 não estarão disponíveis:
- Os usuários não conseguirão ver as informações de disponibilidade dos usuários que estão no outro provedor de email.
- Os administradores não conseguirão administrar as contas de todos os usuários de um só lugar.
- Os usuários podem não conseguir usar o filtro de spam do Office 365

### <a name="how-to-set-up-an-office-365-pilot"></a>Como configurar um piloto do Office 365
    
1. Entre no centro de administração do Microsoft 365
    
    1. Entre no Office 365 com uma conta corporativa ou de estudante.
        
    2. Vá para **Settings** \> **domínios**de configurações. 
    
2. Verifique se você é o proprietário do domínio que deseja usar
    
    1. Na página **domínios** , selecione **Adicionar domínio**. 
        
    2. No painel, digite o domínio, neste exemplo, cohowinery.com, e selecione **Avançar**. 
        
    3. Na página **verificar** domínio, siga as instruções passo a passo. 
        
    4. Na lista suspensa, selecione seu provedor de Hospedagem de DNS e siga as instruções para mostrar que você é o proprietário do domínio.
        
    5. Selecione **verificar**. Leva alguns minutos e 72 horas para que as alterações de DNS entrem em vigor. 
        
    6. Quando a verificação for bem-sucedida, você será solicitado a modificar seus registros DNS.
    
3. Marcar o domínio como compartilhado no Exchange Online
    
    1. Vá para o **centro de administração do Exchange** (Eat). 
        
    2. Na seção **fluxo de emails** , selecione **domínios aceitos**. 
        
    3. Clique duas vezes no domínio que você deseja modificar.
        
    4. Na janela que é aberta, selecione **retransmissão interna**. 
        
    5. Selecione **Salvar**. Essa configuração pode exigir alguns minutos para entrar em vigor. 
    
4. Opcionalmente, desbloqueie o servidor de email existente
    
    1. O Office 365 usa o proteção do Exchange Online (EOP) para proteção contra spam. Se o EOP detectar um alto volume de spam sendo encaminhado pelo servidor de email atual, ele poderá bloqueá-lo, o que impediria o encaminhamento de trabalho. Se você estiver confiante com a proteção contra spam que seu outro provedor de email usa, poderá listar seus servidores no Office 365. No entanto, isso também permitirá que qualquer spam que chega ao servidor original seja enviado às caixas de correio do Office 365, e você não poderá avaliar como o Office 365 impede spam.
    
    2. Vá para o centro de administração do Exchange (Eat).
        
    3. No Eat, selecione **proteção**e selecione filtro de **conexão**. 
        
    4. Na **lista de permissões de IP**, selecione **+** e adicione o endereço IP do servidor de email que você pode obter de seu provedor de email atual. 
    
5. Criar contas de usuário e definir o endereço principal (responder a)
    
    1. Vá para o centro de administração do Microsoft 365.
        
    2. Na barra de navegação esquerda, selecione usuários ativos do **usuário** \> **Active Users**. 
        
    3. Crie as contas de usuário.
        
    4. Para cada conta, selecione **+ (novo)** e preencha as informações necessárias. 
        
    5. Para manter o mesmo email do usuário, o campo **nome de usuário** deve ser exatamente o mesmo que o endereço de email existente do usuário. 
        
    6. Ao lado de nome de usuário, selecione seu nome de domínio personalizado na lista suspensa.
        
    7. Selecione **criar** \> **Fechar**. 
        
6. Atualizar registros DNS no seu provedor de Hospedagem de DNS
    
    1. Entre no site do provedor de Hospedagem de DNS e siga as [etapas de criar registros DNS em qualquer provedor de Hospedagem de DNS para o Office 365](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md). **Faça as seguintes exceções:**
    
        1. Não crie um novo registro MX ou altere seu registro MX existente.
            
        2. Se você já tiver um registro SPF (Sender Policy Framework) para seu provedor de emails anterior, em vez de criar um novo registro SPF (TXT) para o Exchange Online, basta adicionar "include include. Protection. Outlook. com" ao registro TXT atual. Por exemplo, "v = spf1 mx inclui:adatum. com include include. Protection. Outlook. com ~ All".
            
        3. Se você ainda não tem um registro SPF, modifique o que é recomendado pelo Office 365 para incluir o domínio para seu provedor de email atual, mais spf.protection.outlook.com. Isso autoriza mensagens de saída de ambos os sistemas de email.
            
7. Configurar o encaminhamento de emails no provedor atual
    
    1. No seu provedor de email atual, configure o encaminhamento de contas de email dos usuários para seu domínio do onmicrosoft.com:
        
    2. A caixa de correio do usuário A deve encaminhar para usera@yourcompany.onmicrosoft.com
        
    3. A caixa de correio do usuário B deve encaminhar para userb@yourcompany.onmicrosoft.com
        
    4. Ao concluir esta etapa:
        
    5. Todos os emails enviados para usera@yourcompany.com e userb@yourcompany.com estarão disponíveis no Office 365.
    
    6. Observações:
        
        - Entre em contato com seu provedor de email atual para obter as etapas exatas para configurar o encaminhamento.
            
        - Você não precisa manter uma cópia das mensagens no provedor de emails atual.
            
        - A maioria dos provedores encaminham o endereço para resposta do remetente intacto, para que as respostas vá para o remetente original.
    
8. Testar o fluxo de mensagens
    
    1. Entre no Outlook Web App usando as credenciais do usuário A.
        
    2. Execute os seguintes testes:
        
    3. Teste o email local da Microsoft. Por exemplo, envie um email para o usuário B. Esse email deve ser entregue imediatamente. Neste cenário, a mensagem não será encaminhada para a caixa de correio do usuário B no seu servidor original porque o Office 365 vê a caixa de correio como local.
        
    4. Teste o email para alguém que está no outro sistema de email. Por exemplo, envie um email para o usuário C. Este email deve ser entregue na caixa de correio do usuário C no seu servidor de email original.
        
    5. A partir de uma conta externa ou da conta de email de um funcionário no outro sistema de email, verifique se o encaminhamento foi configurado corretamente no outro sistema de email. Por exemplo, da conta de servidor original do usuário C ou de uma conta do hotmail, envie um email para o usuário e verifique se ele chega à caixa de correio do Office 365 do usuário A.
        
9. Mover conteúdo da caixa de correio
    
    1. Como há apenas dois usuários a serem movidos, e como o usuário A e o usuário B já estão usando o Outlook, o email pode ser movido abrindo o antigo. PST no novo perfil do Outlook e copiar as mensagens, itens de calendário, contatos, etc., conforme mostrado em importar itens do Outlook de um arquivo de dados do Outlook (. pst). Depois de organizado nos locais apropriados da caixa de correio do Office 365, todos os itens podem ser acessados de qualquer dispositivo, em qualquer lugar.
        
    2. Quando mais caixas de correio estiverem envolvidas ou se os funcionários ainda não estiverem usando o Outlook, você poderá usar as ferramentas de migração disponíveis no centro de administração do Exchange. Para começar, vá para o centro de administração do Exchange e siga as instruções em migrar email de um servidor IMAP para caixas de correio do Exchange Online.
    
