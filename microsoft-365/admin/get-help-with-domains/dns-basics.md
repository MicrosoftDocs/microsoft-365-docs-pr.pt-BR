---
title: Noções básicas do DNS
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- MET150
- MOE150
- GEA150
- BSA160
ms.assetid: 854b6b2b-0255-4089-8019-b765cff70377
ROBOTS: NOINDEX
description: O sistema de nomes de domínio mapeia os nomes de hosts de computadores para endereços IP e o entendimento básico do DNS e do registrador de domínios pode ajudá-lo a gerenciar domínios.
ms.openlocfilehash: 19fc444c056bbf3e1ea1f601d20a9b9cbd75bec8
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635421"
---
# <a name="dns-basics"></a>Noções básicas do DNS

 Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.yml)**. 
  
::: moniker range="o365-worldwide"

Os nomes de domínio, como contoso.com, são gerenciados usando um sistema mundial de registradores de domínios e bancos de dados. O Sistema de Nomes de Domínio (DNS) fornece um mapeamento entre nomes de host de computador legíveis e os endereços IP usados pelo equipamento de rede. Noções básicas sobre o DNS e o registrador de domínios podem ajudá-lo a gerenciar domínios.

## <a name="watch-domains--dns-an-overview"></a>Assista: Domínios e DNS: uma visão geral
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/c005f2a4-90ad-46fe-b1ab-90f41f2a9d53?autoplay=false]
  
::: moniker-end

::: moniker range="o365-germany"

Os nomes de domínio, como contoso.com, são gerenciados usando um sistema mundial de registradores de domínios e bancos de dados. O Sistema de Nomes de Domínio (DNS) fornece um mapeamento entre nomes de host de computador legíveis e os endereços IP usados pelo equipamento de rede. Noções básicas sobre o DNS e o registrador de domínios podem ajudá-lo a gerenciar domínios.

## <a name="watch-domains--dns-an-overview"></a>Assista: Domínios e DNS: uma visão geral
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/c005f2a4-90ad-46fe-b1ab-90f41f2a9d53?autoplay=false]
  
::: moniker-end

::: moniker range="o365-21vianet"

Os nomes de domínio, como contoso.com, são gerenciados usando um sistema mundial de registradores de domínios e bancos de dados. O Sistema de Nomes de Domínio (DNS) fornece um mapeamento entre nomes de host de computador legíveis e os endereços IP usados pelo equipamento de rede. Noções básicas sobre o DNS e o registrador de domínios ajudarão os administradores a gerenciar domínios.
  
::: moniker-end

## <a name="what-are-domain-names"></a>O que são nomes de domínio?

Os nomes de domínio são usados nas URLs e endereços de email e possuem níveis diferentes. Por exemplo, mail.contoso.com é um nome de domínio com os seguintes três níveis:
  
- **.com** é domínio de primeiro nível 
    
- **contoso** é o domínio de segundo nível 
    
- **mail** é o domínio de terceiro nível 
    
Por que usar um domínio de terceiro nível? Talvez você queira ter nomes de domínio diferentes para marketing ou um blog. Por exemplo, blog.contoso.com. Normalmente, você adicionar um domínio de segundo nível, como contoso.com, para usar com a Microsoft, mas também pode usar domínios de terceiro nível se desejar.
  
Saiba mais sobre o que você pode fazer com domínios para cada tipo de oferta na [descrição do serviço da plataforma Microsoft 365 e Office 365](/office365/servicedescriptions/office-365-platform-service-description/domains).
  
## <a name="understand-dns-record-types"></a>Noções básicas sobre tipos de registro DNS

Registros DNS armazenados em um host DNS do seu domínio são usados para direcionar o tráfego para o seu domínio. A tabela a seguir descreve os registros DNS frequentemente usados e como eles são usados.
  
|**Registro NS (nameserver)**|**Identifica os servidores de nomes que são “nameservers autoritativos” de um domínio. Quando você altera os nameservers do seu domínio, altera também onde seus registros DNS são gerenciados, onde o sistema DNS procura informações sobre servidores de email e assim por diante. A Microsoft tem seus próprios nameservers, ou você pode optar por continuar usando nameservers que já estão configurados com seu domínio.**|
|:-----|:-----|
|Registro A (registro de endereço)  <br/> |Associa um nome de domínio a um endereço IP.  <br/> |
|Registro CNAME (alias ou canônico)  <br/> |Redireciona um domínio para outro no sistema DNS. Quando um servidor de nomes procura um domínio e verifica que ele possui um registro CNAME, o servidor substitui o primeiro nome de domínio pelo CNAME e procura o novo nome.  <br/> |
|Registro MX (mail exchanger)  <br/> |Aponta para o local de destino dos emails. Também contém um campo de prioridade de forma que os emails possam ser enviados para diversos servidores em ordem de prioridade.  <br/> |
|Registro SPF (estrutura de políticas de remetente)  <br/> |Um registro TXT que ajuda a evitar a falsificação e o phishing de emails.  <br/> |
|Registro SRV (serviço)  <br/> |Usado pelo Skype for Business Online e pelo Exchange Online para coordenar o fluxo de informações entre os serviços Microsoft. Por exemplo, os registros SRV são necessários para a visualização da presença no Outlook Web App e para utilizar o Skype for Business, Skype ou outras ferramentas de mensagens instantâneas com pessoas em outras empresas.  <br/> |
|TTL (vida útil)  <br/> |O tempo durante o qual um servidor de nomes mantém um registro DNS antes de procurar uma versão atualizada.  <br/> |
   
## <a name="how-does-dns-work"></a>Como o DNS funciona?

Parte da configuração do domínio com um serviço de nuvem como o Microsoft 365 inclui alterar ou adicionar [registros DNS](dns-basics.md) para o domínio. Essas alterações são necessárias devido a como a Internet trabalha com o DNS (Sistema de Nomes de Domínio) e nomes de domínio para saber para onde enviar ou encontrar coisas, como emails e sites. 
  
A Internet é configurada para usar o DNS, o que nos permite usar nomes comuns, como contoso.com, para localizar locais específicos da Internet que, na verdade, são rotulados nos bastidores com números difíceis de lembrar, chamados endereços IP (protocolo de Internet).  Os endereços IP são algo como 70.42.241.42, assim, como você pode ver, é muito mais fácil usar um nome de domínio para identificar locais como hosts de email e sites.
  
Esta é a resposta curta: os registros DNS indicam para a Internet onde enviar emails (como Paulo@contoso.com) ou localizar sites (como www.contoso.com) que usam seu nome de domínio. Quando você coloca as informações corretas nos registros DNS corretos do seu domínio, o sistema DNS roteia tudo corretamente para que seu email, por exemplo, chegue no Microsoft 365, em vez de chegar em outro lugar.
  
Os registros DNS de um domínio também podem ser úteis de outras maneiras. Por exemplo, o Exchange verifica um registro DNS que permite que o Outlook configure automaticamente uma conexão ao servidor Exchange correto.
  
### <a name="dns-records-help-the-internet-send-email-to-the-right-place"></a>Os registros DNS ajudam a Internet a enviar emails ao locais corretos

Como você leu acima, o DNS essencialmente direciona o tráfego da Internet, mapeando nomes de domínio amigáveis para os endereços IP difíceis de lembrar.  Um registro DNS, chamado de registro MX, é usado especificamente para enviar emails ao host correto.
  
Os registros DNS são como um banco de dados de informações sobre seu domínio. Os registros e seus valores são mantidos em algo chamado de arquivo de zona, que inclui uma lista de cada registro para seu domínio e o valor dele. Os registradores de domínio e outras empresas de hospedagem de DNS fornecem uma interface de usuário em seus sites, para que você possa editar os registros no arquivo de zona do seu domínio. Esse é o local onde você atualiza o registro MX do seu domínio para enviar mensagens de email para o Microsoft 365.
  
 *Quando você alterar seu email para o Microsoft 365, ao atualizar o seu registro MX do seu domínio na etapa seguinte, TODOS os emails enviados para esse domínio serão enviados para o Microsoft 365.*  Se outras pessoas utilizarem seu domínio para enviar e receber emails, você deverá configurar caixas de correio do Microsoft 365 para cada uma dessas pessoas. 
  
Parece complicado? Bem, pode ser, mas vamos orientá-lo ao longo de cada etapa na configuração de domínio da Microsoft.
  
### <a name="dns-tells-the-internet-where-to-look-for-websites-too"></a>O DNS também informa à Internet onde localizar os sites

Quando você digita um endereço de email, por exemplo, www.contoso.com, a Internet primeiro verifica um dos servidores DNS para algo chamado registro de servidor de nomes (NS) para (neste caso) contoso.com. O registro NS informa à Internet onde ele deve procurar o arquivo de zona que tem todos os valores de registro DNS desse domínio. Há muitos servidores DNS, todos conectados uns aos outros. Os servidores trabalham juntos para acompanhar todos os nomes de domínio registrados, que devem ser exclusivos e o local onde os arquivos de zona do domínio estão.
  
::: moniker range="o365-worldwide"

Digamos que o registro NS de contoso.com seja “godaddy.com.” Agora, a Internet sabe que GoDaddy.com é o local onde procurar o arquivo de zona listando todos os outros registros DNS para contoso.com. Esses registros DNS incluem o registro MX que informa para onde enviar os emails de contoso.com e outros registros. Se o registro MX possui um valor que informa (mas em termos técnicos) “enviar um email para o Microsoft 365,” esse local é onde todas as mensagens de email enviadas para um endereço de email da contoso.com (como paulo@contoso.com) serão enviadas. Em seguida, desde que haja uma caixa de correio chamada “Paulo” nesse local, o email será entregue.

::: moniker-end

::: moniker range="o365-germany"

Digamos que o registro NS de contoso.com seja “godaddy.com.” Agora, a Internet sabe que GoDaddy.com é o local onde procurar o arquivo de zona listando todos os outros registros DNS para contoso.com. Esses registros DNS incluem o registro MX que informa para onde enviar os emails de contoso.com e outros registros. Se o registro MX possui um valor que informa (mas em termos técnicos) “enviar um email para o Microsoft 365,” esse local é onde todas as mensagens de email enviadas para um endereço de email da contoso.com (como paulo@contoso.com) serão enviadas. Em seguida, desde que haja uma caixa de correio chamada “Paulo” nesse local, o email será entregue.

::: moniker-end

::: moniker range="o365-21vianet"

Digamos que o registro NS de contoso.com seja “hichina.com.” Agora, a Internet sabe que hichina.com é o local onde procurar o arquivo de zona listando todos os outros registros DNS para contoso.com. Esses registros DNS incluem o registro MX que informa para onde enviar os emails de contoso.com e outros registros. Se o registro MX possui um valor que informa (mas em termos técnicos) “enviar um email para o Microsoft 365,” esse local é onde todas as mensagens de email enviadas para um endereço de email da contoso.com (como paulo@contoso.com) serão enviadas. Em seguida, desde que haja uma caixa de correio chamada “Paulo” nesse local, o email será entregue.

::: moniker-end

Os valores reais que você deve inserir para que tudo isso funcione no Microsoft 365 são listados quando você configura seu domínio, nas etapas de configuração de domínio. Se você estiver executando a configuração manualmente, copie e cole os valores nos registros DNS corretos (registro MX, registros CNAME e assim por diante) em seu host DNS, que pode ser seu registrador de domínio, mas não precisa ser.
  
::: moniker range="o365-worldwide"

Por que o arquivo de zona do seu domínio pode estar em outro lugar além do seu registrador de domínios? Você pode registrar seu nome de domínio em um registrador de domínio, como GoDaddy, mas seus registros DNS podem ser gerenciados em outro local, em uma empresa de hospedagem de DNS ou em uma empresa de hospedagem na Web. Os registros NS de seu domínio armazenam essas informações para que todos os servidores DNS saibam onde procurar.

::: moniker-end

::: moniker range="o365-germany"

Por que o arquivo de zona do seu domínio pode estar em outro lugar além do seu registrador de domínios? Você pode registrar seu nome de domínio em um registrador de domínio, como GoDaddy, mas seus registros DNS podem ser gerenciados em outro local, em uma empresa de hospedagem de DNS ou em uma empresa de hospedagem na Web. Os registros NS de seu domínio armazenam essas informações para que todos os servidores DNS saibam onde procurar.

::: moniker-end

::: moniker range="o365-21vianet"

Por que o arquivo de zona do seu domínio pode estar em outro lugar além do seu registrador de domínios? Você pode registrar o seu nome de domínio em um registrador de domínio, como HiChina, mas seus registros DNS podem ser gerenciados em outro local, em uma empresa de hospedagem de DNS ou em uma empresa de hospedagem na Web. Os registros NS de seu domínio armazenam essas informações para que todos os servidores DNS saibam onde procurar.

::: moniker-end

::: moniker range="o365-worldwide"
## <a name="why-add-a-domain-in-microsoft-365"></a>Por que adicionar um domínio no Microsoft 365?


Adicionar um domínio personalizado, como fourthcoffee.com ao Microsoft 365 permite que você use um endereço de email e uma ID de usuário mais curtos e familiares no serviço.  Você [receberá um domínio para usar](../setup/domains-faq.yml) ao se inscrever em uma conta do Microsoft 365, mas ele inclui “onmicrosoft.com.” Muitas pessoas preferem adicionar o domínios de suas organizações ou empresas quando planejam usar o Microsoft 365 para emails. 
  
> [!NOTE]
> Se você quer apenas baixar e usar aplicativos da Microsoft, como Outlook ou Word, não precisa adicionar um domínio: [Instalar o Office no seu computador ou Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658). 
  
É possível utilizar seu nome de domínio no Microsoft 365 com seu email, site público e endereço do sistema de mensagens instantâneas.
  
- **Email:** seu nome de domínio permite que você personalize seu email para que seja possível utilizar um endereço mais curto e mais fácil de lembrar que [o endereço de email inicial onmicrosoft.com](../setup/domains-faq.yml) que acompanha sua conta.  Portanto, em vez de paulo@contoso.onmicrosoft.com, o endereço de email (que também é a conta corporativa que você utiliza para entrar no Microsoft 365) poderia ser paulo@contoso.com. 
    
- **Website:** Se você possui uma assinatura do Microsoft 365 que inclui um site público do SharePoint Online (não está mais disponível para compra), seu site público é fornecido com um endereço inicial como este: contoso-public.sharepoint.com. Se você configurar seu site para sua empresa, poderá usar um nome de domínio personalizado para renomear o endereço do site para algo como www.contoso.com. 
    
- **Sistema de mensagens instantâneas:** seu endereço do Skype for Business Online também pode ser personalizado para utilizar seu nome de domínio, de modo que as pessoas em sua organização possam conectar-se umas com as outras no Skype for Business Online utilizando um endereço mais curto e mais fácil de lembrar (como paulo@contoso.com). 
    
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-add-a-domain-in-microsoft-365"></a>Por que adicionar um domínio no Microsoft 365?


Adicionar um domínio personalizado, como fourthcoffee.com ao Microsoft 365 permite que você use um endereço de email e uma ID de usuário mais curtos e familiares no serviço.  Você [receberá um domínio para usar](../setup/domains-faq.yml) ao se inscrever em uma conta do Microsoft 365, mas ele inclui “onmicrosoft.com.” Muitas pessoas preferem adicionar o domínios de suas organizações ou empresas quando planejam usar o Microsoft 365 para emails. 
  
> [!NOTE]
> Você não precisa adicionar um domínio se deseja apenas baixar e usar os aplicativos do Microsoft 365, como o Outlook ou o Word: [Instalar o Office no seu computador ou Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658). 
  
É possível utilizar seu nome de domínio no Microsoft 365 com seu email, site público e endereço do sistema de mensagens instantâneas.
  
- **Email:** seu nome de domínio permite que você personalize seu email para que seja possível utilizar um endereço mais curto e mais fácil de lembrar que [o endereço de email inicial onmicrosoft.com](../setup/domains-faq.yml) que acompanha sua conta.  Portanto, em vez de paulo@contoso.onmicrosoft.com, o endereço de email (que também é a conta corporativa que você utiliza para entrar no Microsoft 365) poderia ser paulo@contoso.com. 
    
- **Website:** Se você tiver uma assinatura que inclua um site público do SharePoint Online (não está mais disponível para compra), seu site público será exibido com um endereço inicial como o seguinte: contoso-public.sharepoint.com. Se você configurar seu site para sua empresa, poderá usar um nome de domínio personalizado para renomear o endereço do site para algo como www.contoso.com. 
    
- **Sistema de mensagens instantâneas:** seu endereço do Skype for Business Online também pode ser personalizado para utilizar seu nome de domínio, de modo que as pessoas em sua organização possam conectar-se umas com as outras no Skype for Business Online utilizando um endereço mais curto e mais fácil de lembrar (como paulo@contoso.com). 
    
::: moniker-end

## <a name="the-dns-records-required-for-microsoft-365"></a>Os registros DNS necessários para o Microsoft 365

Há vários registros DNS necessários para que o Microsoft 365 funcione com seu domínio. Além de configurar o registro MX do seu domínio para que os emails sejam enviados para o Microsoft 365, existem registros para ajudá-lo com tarefas como garantir que o Outlook possa se conectar automaticamente ao servidor do Exchange correto, configurar o sistema de mensagens instantâneas e ajudar a evitar mensagens de spam.
  
Você pode [encontrar uma lista de valores](information-for-dns-records.md) para configurar seu domínio. Eles estão incluídos diretamente no centro de administração do Microsoft 365. 
  
Ou, se estiver planejando uma implantação, convém analisar uma lista de todos os registros DNS necessários para o Microsoft 365, a função deles e os valores de exemplo. Confira os [Registros do Sistema de Nomes de Domínio Externo do Microsoft 365](../../enterprise/external-domain-name-system-records.md).
  
## <a name="next-steps"></a>Próximas etapas

Confira um dos seguintes tópicos: 
  
- Não sabe onde seu domínio está registrado? [Obtenha ajuda para encontrar o seu registrador de domínio.](find-your-domain-registrar.md)
- Descubra [por que você deve concluir as etapas do assistente](../setup/add-domain.md) antes de usar seu domínio com o Microsoft 365.

## <a name="related-content"></a>Conteúdo relacionado

[Perguntas frequentes sobre domínios](../setup/domains-faq.yml) (artigo)\
[Localizar e corrigir problemas após adicionar seu domínio ou registros DNS ](find-and-fix-issues.md) (artigo)\
[Gerenciar domínios](index.yml) (página de link)