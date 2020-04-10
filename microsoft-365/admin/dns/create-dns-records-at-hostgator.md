---
title: Criar registros DNS na HostGator para Office 365
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
- Adm_NonTOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5f0c840e-4140-4571-88ed-cf235ff142d6
description: Saiba como verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços em Hostgator para o Office 365.
ms.openlocfilehash: a5a41e5c1eba9d99d1927192472da7746277dd38
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211710"
---
# <a name="create-dns-records-at-hostgator-for-office-365"></a>Criar registros DNS na HostGator para Office 365

 **Caso não encontre o conteúdo que está procurando, [verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**. 
  
Se você usa a HostGator como provedor de hospedagem DNS, siga as etapas deste artigo para verificar o domínio e configurar registros DNS para o Skype for Business Online, email e outros serviços.
  
> [!IMPORTANT]
> Você deve executar o primeiro procedurebelow, [apontar seu domínio para sua conta de hospedagem](#point-your-domain-to-your-hosting-account), antes de adicionar registros DNS usando qualquer um dos outros procedimentos deste artigo. 

Depois de fazer todas essas alterações na HostGator, seu domínio será configurado para trabalhar com os serviços do Office 365.
  
Para saber mais sobre hospedagem na Web e DNS para sites com o Office 365, confira [Usar um site público com o Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).
  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas após alterar o nome de domínio ou registros DNS no Office 365](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="point-your-domain-to-your-hosting-account"></a>Aponte seu domínio para sua conta de hospedagem
<a name="BKMK_PointDomain"> </a>

> [!IMPORTANT]
> Você deve executar esse procedimento antes de executar qualquer um dos outros procedimentos neste artigo. 
  
Siga estas etapas para associar seu domínio e as contas de hospedagem.
  
1. Para começar, vá até a sua página de gerenciamento de domínios no HostGator, usando [este link](https://portal.hostgator.com/). Você será solicitado a fazer logon primeiro.
    
2. Selecione **domínios** à esquerda.
  
3. Na página **gerenciar domínios** , selecione o domínio que você deseja atualizar. 
  
4. No menu pop-up à esquerda, selecione servidores de **nomes**.
  
5. Na página **servidores de nomes** do seu domínio, na lista suspensa **apontar automaticamente este domínio para minha conta de hospedagem** , escolha a conta de hospedagem associada ao seu domínio. 
  
6. Selecione **salvar servidores de nomes**.
    
  
## <a name="add-a-txt-record-for-verification"></a>Adicionar um registro TXT para verificação
<a name="BKMK_verify"> </a>

> [!IMPORTANT]
> Antes de executar este procedimento, primeiro você deve executar o procedimento da primeira seção deste artigo, [Aponte seu domínio para sua conta de hospedagem](#point-your-domain-to-your-hosting-account). 
  
Antes de usar o seu domínio com o Office 365, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro DNS prova ao Office 365 que você é o proprietário do domínio.
  
> [!NOTE]
> Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar. 
  
1. To get started, go to your cPanel page at Hostgator. You'll be prompted to log in first.
    
    (Each hosted account at Hostgator is assigned a unique cPanel address. Seu endereço cPanel deve ter esta aparência: https://YourSiteAddress:secure-port-numberçoDoSeuSite:número-de-porta-segura. O email de inscrição que você recebeu do Hostgator especificará esse endereço, e um link cPanel também estará disponível na página de **hospedagem** .)
    
    > [!IMPORTANT]
    > Para ter um cPanel associado ao seu domínio, você precisa de uma conta de hospedagem do Hostgator. Para começar a usar o Office 365, você pode adquirir uma conta de hospedagem do Hostgator ou [delegar novamente seus servidores de nome para que apontem para o Office 365](change-nameservers-at-hostgator.md). 
  
2. Na página **painel de controle** , na área **domínios** , selecione **Editor de zona avançada**.
    
3. Na página **Editor avançado de zona** , na área **adicionar registro** , nas caixas do novo registro, digite ou copie e cole os valores da tabela a seguir. 
    
    (Escolha o valor de **Tipo** na lista suspensa.) 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |**Nome** <br/> |**TTL** <br/> |**Tipo** <br/> |**Dados TXT** <br/> |
    |Use o *domain_name*. (por exemplo, fourthcoffee.com.)  <br/> **This value MUST end with a period (.)** <br/> |1  <br/> |TXT  <br/> |MS = ms *XXXXXXXX*  <br/> **Observação**: esse é um exemplo. Use seu valor específico de **Destinos ou Pontos de Endereçamento** aqui, da tabela no Office 365. [Como localizo isto?](../get-help-with-domains/information-for-dns-records.md)          |
   
4. Selecione **adicionar registro**.
    
5. Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.
    
Agora que você adicionou o registro no site do seu registrador de domínios, retorne ao Office 365 e solicite que o Office 365 procure o registro.
  
Quando o Office 365 encontrar o registro TXT correto, o domínio será verificado.
  
1. No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.
    
2. Na página **Domínios**, clique no domínio que você está verificando. 
    
3. Na página **Configuração**, clique em **Iniciar configuração**.
    
4. Na página **Verificar domínio**, clique em **Verificar**.
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas após alterar o nome de domínio ou registros DNS no Office 365](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a>Adicionar um registro MX para que o e-mail do domínio vá para o Office 365
<a name="BKMK_add_MX"> </a>

> [!IMPORTANT]
> Antes de executar este procedimento, primeiro você deve executar o procedimento da primeira seção deste artigo, [Aponte seu domínio para sua conta de hospedagem](#point-your-domain-to-your-hosting-account). 
  
1. Para começar, vá para a página do cPanel no Hostgator. Será solicitado que você faça logon primeiro.
    
    (É atribuído um endereço cPanel exclusivo a cada conta hospedada no Hostgator. Seu endereço cPanel deve ter esta aparência: https://YourSiteAddress:secure-port-numberçoDoSeuSite:número-de-porta-segura. O email de inscrição que você recebeu do Hostgator especificará esse endereço, e um link cPanel também estará disponível na página de **hospedagem** .)
    
    > [!IMPORTANT]
    > Para ter um cPanel associado ao seu domínio, você precisa de uma conta de hospedagem do Hostgator. Para começar a usar o Office 365, você pode adquirir uma conta de hospedagem do Hostgator ou [delegar novamente seus servidores de nome para que apontem para o Office 365](change-nameservers-at-hostgator.md). 
  
2. Na página **painel de controle** , na área **email** , selecione **entrada MX**.
    
 
3. Na área de **Roteamento de Email**, selecione **Mail Exchanger Remoto**.

4. Selecione **alterar**.
  
5. Na área **Adicionar um novo registro** , nas caixas do novo registro, digite ou copie e cole os valores da tabela a seguir. 
    
    |**Prioridade**|**Destino**|
    |:-----|:-----|
    |,0  <br/> Para saber mais sobre prioridade, confira [O que é prioridade MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> | *\<chave-do-domínio\>*  .mail.protection.outlook.com  <br/> **Observação:** Obtenha sua \< *chave* \> de domínio de sua conta do Office 365.    [Como localizo isto?](../get-help-with-domains/information-for-dns-records.md)          |
  
6. Selecione **Adicionar novo registro**.
   
 
7. Se houver outros registros MX na seção **registros MX** , remova cada um deles. 

    
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a>Adicionar os seis registros CNAME necessários para o Office 365
<a name="BKMK_add_CNAME"> </a>

> [!IMPORTANT]
> Antes de executar este procedimento, primeiro você deve executar o procedimento da primeira seção deste artigo, [Aponte seu domínio para sua conta de hospedagem](#point-your-domain-to-your-hosting-account). 
  
1. Para começar, vá para a página do cPanel no Hostgator. Será solicitado que você faça logon primeiro.
    
    (É atribuído um endereço cPanel exclusivo a cada conta hospedada no Hostgator. Seu endereço cPanel deve ter esta aparência: https://YourSiteAddress:secure-port-numberçoDoSeuSite:número-de-porta-segura. O email de inscrição que você recebeu do Hostgator especificará esse endereço, e um link cPanel também estará disponível na página de **hospedagem** .)
    
    > [!IMPORTANT]
    > Para ter um cPanel associado ao seu domínio, você precisa de uma conta de hospedagem do Hostgator. Para começar a usar o Office 365, você pode adquirir uma conta de hospedagem do Hostgator ou [delegar novamente seus servidores de nome para que apontem para o Office 365](change-nameservers-at-hostgator.md). 
  
2. Na página **painel de controle** , na área **domínios** , selecione **Editor de zona avançada**.
    
3. Adicione o primeiro dos seis registros CNAME.
    
    Na página **Editor avançado de zona** , na área **adicionar registro** , nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir. 
    
    (Escolha o valor de **Tipo** na lista suspensa.) 
    
    |**Nome**|**TTL**|**Tipo**|**CNAME**|
    |:-----|:-----|:-----|:-----|
    |autodiscover. *domain_name*. (por exemplo, autodiscover.fourthcoffee.com.)  <br/> **Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)** <br/> |3600  <br/> |CNAME  <br/> |autodiscover.outlook.com  <br/> |
    |sip. *domain_name*. (por exemplo, sip.fourthcoffee.com.)  <br/> **Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)** <br/> |3600  <br/> |CNAME  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover. *domain_name*. (por exemplo, lyncdiscover.fourthcoffee.com.)  <br/> **Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)** <br/> |3600  <br/> |CNAME  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration. *domain_name*. (por exemplo, enterpriseregistration.fourthcoffee.com.)  <br/> **Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)** <br/> |3600  <br/> |CNAME  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment. *domain_name*. (por exemplo, enterpriseregistration.fourthcoffee.com.)  <br/> **Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)** <br/> |3600  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |

  
4. Selecione **adicionar registro**.

5. Adicione cada um dos outros cinco registros CNAME.
    
    Na seção **Adicionar um registro** , crie um registro usando os valores da próxima linha na tabela e, em seguida, selecione **adicionar registro** para concluir esse registro. 
    
    Repita esse processo até ter criado todos os seis registros CNAME.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Não é possível ter mais de um registro TXT para SPF para um domínio. Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam. If you already have an SPF record for your domain, don't create a new one for Office 365. Em vez disso, adicione os valores necessários do Office 365 ao registro atual, de modo que você tenha um único registro SPF que inclua os dois conjuntos de valores. Precisa de exemplos? Confira os [Registros do sistema de nomes de domínios externos do Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords).  To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md). 
  
> [!IMPORTANT]
> Antes de executar este procedimento, primeiro você deve executar o procedimento da primeira seção deste artigo, [Aponte seu domínio para sua conta de hospedagem](#point-your-domain-to-your-hosting-account). 
  
1. Para começar, vá para a página do cPanel no Hostgator. Será solicitado que você faça logon primeiro.
    
    (É atribuído um endereço cPanel exclusivo a cada conta hospedada no Hostgator. Seu endereço cPanel deve ter esta aparência: https://YourSiteAddress:secure-port-numberçoDoSeuSite:número-de-porta-segura. O email de inscrição que você recebeu do Hostgator especificará esse endereço, e um link cPanel também estará disponível na página de **hospedagem** .)
    
    > [!IMPORTANT]
    > Para ter um cPanel associado ao seu domínio, você precisa de uma conta de hospedagem do Hostgator. Para começar a usar o Office 365, você pode adquirir uma conta de hospedagem do Hostgator ou [delegar novamente seus servidores de nome para que apontem para o Office 365](change-nameservers-at-hostgator.md). 
  
2. Na página **painel de controle** , na área **domínios** , selecione **Editor de zona avançada**.
    
3. On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Escolha o valor de **Tipo** na lista suspensa.) 
    
    |**Nome**|**TTL**|**Tipo**|**Dados TXT**|
    |:-----|:-----|:-----|:-----|
    |Use o *domain_name*. (por exemplo, fourthcoffee.com.)  <br/> **Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)** <br/> |3600  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.           |
  
4. Selecione **adicionar registro**.
    
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>Adicionar os dois registros SRV necessários do Office 365
<a name="BKMK_add_SRV"> </a>

> [!IMPORTANT]
> Antes de executar este procedimento, primeiro você deve executar o procedimento da primeira seção deste artigo, [Aponte seu domínio para sua conta de hospedagem](#point-your-domain-to-your-hosting-account). 
  
1. Para começar, vá para a página do cPanel no Hostgator. Será solicitado que você faça logon primeiro.
    
    (É atribuído um endereço cPanel exclusivo a cada conta hospedada no Hostgator. Seu endereço cPanel deve ter esta aparência: https://YourSiteAddress:secure-port-numberçoDoSeuSite:número-de-porta-segura. O email de inscrição que você recebeu do Hostgator especificará esse endereço, e um link cPanel também estará disponível na página de **hospedagem** .)
    
    > [!IMPORTANT]
    > Para ter um cPanel associado ao seu domínio, você precisa de uma conta de hospedagem do Hostgator. Para começar a usar o Office 365, você pode adquirir uma conta de hospedagem do Hostgator ou [delegar novamente seus servidores de nome para que apontem para o Office 365](change-nameservers-at-hostgator.md). 
  
2. Na página **painel de controle** , na área **domínios** , selecione **Editor de zona avançada**.

    
3. Adicione o primeiro dos dois registros SRV.
    
    Na página **Editor Avançado de Zona DNS**, na área **Adicionar um Registro**, nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir. 
    
    (Escolha o valor de **Tipo** na lista suspensa.) 
    
    |**Nome**|**TTL**|**Tipo**|**Prioridade**|**Espessura**|**Porta**|**Destino**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip. _tls. *domain_name*. (por exemplo, _sip._tls.fourthcoffee.com.)  <br/> **Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)** <br/> |3600  <br/> |SRV  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
    |_sipfederationtls. _tcp. *domain_name*. (por exemplo, _sipfederationtls._tcp.fourthcoffee.com.)  <br/> **Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)** <br/> |3600  <br/> |SRV  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com  <br/> |
   

4. Selecione **adicionar registro**.

  
5. Adicione o outro registro SRV.
    
    Na seção **Adicionar um registro** , crie um registro usando os valores da próxima linha na tabela e, em seguida, selecione **adicionar registro** para concluir esse registro. 
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas após alterar o nome de domínio ou registros DNS no Office 365](../get-help-with-domains/find-and-fix-issues.md). 
