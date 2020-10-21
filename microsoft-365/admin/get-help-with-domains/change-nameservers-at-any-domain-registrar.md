---
title: Alterar os nameservers para configurar o Microsoft 365 com qualquer registrador de domínios
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- okr_smb
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEU150
- GEA150
ms.assetid: a8b487a9-2a45-4581-9dc4-5d28a47010a2
description: Saiba como adicionar e configurar seu domínio no Microsoft 365 para que seus serviços como o email e o Skype for Business online usem seu próprio nome de domínio.
ms.openlocfilehash: f233cc9b2d37e3ee81e52178a7cc045cb3579e42
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645390"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-any-domain-registrar"></a>Alterar os nameservers para configurar o Microsoft 365 com qualquer registrador de domínios

 Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**. 
  
Confira primeiro [configurar seu domínio (instruções específicas do host)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) para ver se temos instruções para o seu registrador. 
  
Siga estas instruções para adicionar e configurar seu domínio no Microsoft 365 para que seus serviços, como o email e o Microsoft Teams, usem seu próprio nome de domínio. Para fazer isso, verifique seu domínio e altere os nameservers do seu domínio para o Microsoft 365 para que os registros DNS corretos possam ser configurados para você. Siga estas etapas se as instruções a seguir descrevem sua situação:
  
- Você tem seu próprio domínio e deseja configurá-lo para funcionar com o Microsoft 365.
    
- Você deseja que a Microsoft 365 gerencie seus registros DNS para você. Se preferir, é possível[ gerenciar seus próprios registros DNS ](../setup/add-domain.md).
    
## <a name="add-a-txt-or-mx-record-for-verification"></a>Adicionar um registro TXT ou MX para verificação
<a name="BKMK_verify"> </a>

> [!NOTE]
> Você criará apenas um desses registros. O TXT é o tipo de registro preferencial, mas alguns provedores de host DNS não são compatíveis com ele. Nesse caso, você pode criar um registro MX como alternativa. 
  
Antes de usar o seu domínio com o Microsoft 365, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro de DNS prova ao Microsoft 365 que você é o proprietário do domínio.
  
> [!NOTE]
> Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar. 
  
### <a name="find-the-area-on-your-dns-hosting-providers-website-where-you-can-create-a-new-record"></a>Encontre a área no site do provedor de Hospedagem de DNS onde você pode criar um novo registro

1. Entre no site do seu provedor de hospedagem DNS.
    
2. Escolha seu domínio.
    
3. Localize a página na qual você pode editar registros DNS para o seu domínio.
    
### <a name="create-the-record"></a>Criar o registro

Caso esteja criando um registro TXT ou um registro MX, siga um destes procedimentos:
  
**Se você criar um registro TXT, use estes valores:**
    
|||||
|:-----|:-----|:-----|:-----|
|**Tipo de registro** <br/> |**Alias** ou **Nome do host** <br/> |**Valor** <br/> |**TTL** <br/> |
|TXT  <br/> |Siga um destes procedimentos: Digite **@**, deixe o campo vazio ou digite o seu nome de domínio.  <br/> > [!NOTE]> Hosts DNS diferentes têm requisitos diferentes para este campo.           
|MS = ms *XXXXXXXX*  <br/> > [!NOTE]> Esse é um exemplo. Use seu valor específico de **Destino ou Pontos de Endereçamento** aqui, retirado da tabela no Microsoft 365.           [Como localizo isto?](../get-help-with-domains/information-for-dns-records.md)          |Defina esse valor como **1 hora** ou o equivalente em minutos ( **60** ), segundos ( **3600** ), etc.  <br/> |
   
**Se você criar um registro MX, use estes valores:**
    
||||||
|:-----|:-----|:-----|:-----|:-----|
|**Tipo de registro**|**Alias** ou **Nome do host**|**Valor**|**Prioridade**|**TTL**|
|MX|Digite **@** ou seu nome de domínio. |MS = ms *XXXXXXXX* > [!NOTE]> Esse é um exemplo. Use seu valor específico de **Destino ou Pontos de Endereçamento** aqui, retirado da tabela no Microsoft 365.           [Como localizo isto?](../get-help-with-domains/information-for-dns-records.md)          |Para **Priority**, para evitar conflitos com o registro MX usado para o fluxo de email, use uma prioridade menor do que a prioridade de qualquer registro MX existente. Para saber mais sobre prioridade, confira [O que é prioridade MX?](../setup/domains-faq.md#what-is-mx-priority) |Defina esse valor como **1 hora** ou o equivalente em minutos ( **60** ), segundos ( **3600** ), etc. |
   
### <a name="save-the-record"></a>Salvar o registro

Agora que você adicionou o registro no site do seu registrador de domínios, retorne ao Microsoft 365 e solicite que o Microsoft 365 procure o registro.
  
Quando o Microsoft 365 encontrar o registros TXT correto, o domínio será verificado.
  

1. No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.
    
2. Na página **Domínios**, clique no domínio que você está verificando. 
    
  
3. Na página **Configuração**, clique em **Iniciar configuração**.
 
    
  
4. Na página **Verificar domínio**, marque **Verificar**.
    
    
  
> [!NOTE]
>  Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="change-your-domains-nameserver-ns-records"></a>Alterar os registros de nameserver (NS) de seu domínio
<a name="BKMK_nameservers"> </a>

Ao chegar na última etapa do assistente de configuração de domínios no Microsoft 365, você tem uma tarefa restante. Para configurar seu domínio com os serviços do Microsoft 365, como email, você altera os registros de nameserver (ou NS) do seu domínio no seu registrador de domínio para apontar para os nameservers primários e secundários da Microsoft 365. Então, como a Microsoft 365 hospeda seu DNS, os registros DNS necessários para seus serviços são configurados automaticamente para você. Você pode atualizar os registros de servidor de nomes por conta própria seguindo as etapas que seu registrador de domínio pode fornecer no conteúdo de Ajuda no site deles. Se você não estiver familiarizado com DNS, contate o suporte no registrador de domínios.

::: moniker range="o365-worldwide"
  
Para alterar os servidores de nomes do seu domínio por conta própria no site do registrador de domínios, siga estas etapas:
  
1. Encontre a área no site do registrador de domínio onde você pode alterar os nameservers para seu domínio ou uma área onde você pode usar nameservers personalizados.
    
2. Crie registros nameserver ou edite os registros de nameserver existentes para coincidir com os seguintes valores:
    
|||
|:-----|:-----|
|Primeiro servidor de nome  <br/> |ns1.bdm.microsoftonline.com  <br/> |
|Segundo servidor de nome  <br/> |ns2.bdm.microsoftonline.com  <br/> |
|Terceiro nameserver  <br/> |ns3.bdm.microsoftonline.com  <br/> |
|Quarto nameserver  <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   > [!TIP]
   > É melhor adicionar todos os quatro registros, mas se o registrador suportar apenas dois, adicione **ns1.bdm.microsoftonline.com** e **ns2.bdm.microsoftonline.com**. 
  
3. Salve suas alterações.
    
> [!CAUTION]
> Quando você alterar os registros NS do seu domínio para apontar para os nameservers da Microsoft 365, todos os serviços associados atualmente ao seu domínio serão afetados. Se você tiver ignorado alguma etapa do assistente, como adicionar o endereço de email, ou se estiver usando o seu domínio para blogs, carrinhos de compras ou outros serviços, haverá etapas adicionais necessárias. Caso contrário, esta mudança poderá resultar em tempo de inatividade para os serviços, como perder acesso ao email ou tornar o site atual inacessível. 

::: moniker-end

::: moniker range="o365-21vianet"
  
1. Localize a área no site do registrador de domínios na qual você pode editar os servidores de nomes do seu domínio.
    
2. Crie dois registros de servidor de nomes ou edite os registros de servidor de nomes existentes para que eles correspondam aos seguintes valores:
    
|||
|:-----|:-----|
|Primeiro servidor de nome  <br/> |ns1.dns.partner.microsoftonline.cn  <br/> |
|Segundo servidor de nome  <br/> |ns2.dns.partner.microsoftonline.cn  <br/> |
   
   > [!TIP]
   > Você deve usar pelo menos dois registros de nameserver. Se houver outros nameservers listados, você poderá excluí-los ou alterá-los para **NS3.DNS.Partner.microsoftonline.cn** e **NS4.DNS.Partner.microsoftonline.cn**. 
  
3. Salve suas alterações.
    
> [!CAUTION]
> Quando você alterar os registros NS do seu domínio para apontar para o Office 365 operado pelos nameservers da 21Vianet, todos os serviços associados atualmente ao seu domínio serão afetados. Se você tiver ignorado alguma etapa do assistente, como adicionar o endereço de email, ou se estiver usando o seu domínio para blogs, carrinhos de compras ou outros serviços, haverá etapas adicionais necessárias. Caso contrário, esta mudança poderá resultar em tempo de inatividade para os serviços, como perder acesso ao email ou tornar o site atual inacessível. 

::: moniker-end
  
Por exemplo, aqui estão algumas etapas adicionais que podem ser necessárias para a hospedagem de email e de site:
  
- Mova todos os endereços de email que usam seu domínio para a Microsoft 365 antes de alterar seus registros NS.
    
- Você deseja adicionar um domínio atualmente usado com um site da Web, como www.fourthcoffee.com? Você pode seguir as etapas ao adicionar o domínio para manter seu site hospedado onde o site está hospedado agora para que as pessoas possam acessar o site depois de alterar os registros NS do domínio para apontar para o Microsoft 365.

1. No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.

2. Na página **domínios** , selecione o domínio e, em seguida, escolha **registros DNS**.

3. Em **configurações de DNS**, selecione **registros personalizados**e, em seguida, escolha **novo registro personalizado**.

4. Selecione o tipo de registro DNS que você deseja adicionar e digite as informações do novo registro.

5. Selecione **Salvar**.
    
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Em seguida, seu email da Microsoft e outros serviços serão configurados para funcionar com seu domínio. 
  
