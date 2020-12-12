---
title: Criar registros DNS no HostGator para Microsoft
f1.keywords:
- NOCSH
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
- Adm_NonTOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5f0c840e-4140-4571-88ed-cf235ff142d6
description: Saiba como verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços em Hostgator para a Microsoft.
ms.openlocfilehash: 3fe13df9b7e41d88c9bf06149eb894a028c4e350
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658082"
---
# <a name="create-dns-records-at-hostgator-for-microsoft"></a>Criar registros DNS no HostGator para Microsoft

 **Caso não encontre o conteúdo que está procurando, [verifique as perguntas frequentes sobre domínios](../setup/domains-faq.yml)**. 
  
Se você usa a HostGator como provedor de hospedagem DNS, siga as etapas deste artigo para verificar o domínio e configurar registros DNS para o Skype for Business Online, email e outros serviços.
  
> [!IMPORTANT]
> Você deve executar o primeiro procedurebelow, [apontar seu domínio para sua conta de hospedagem](#point-your-domain-to-your-hosting-account), antes de adicionar registros DNS usando qualquer um dos outros procedimentos deste artigo. 

Depois de fazer todas essas alterações em Hostgator, o domínio será configurado para funcionar com os serviços da Microsoft.
  

  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
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
  
Antes de usar o seu domínio com a Microsoft, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro de DNS prova à Microsoft que você é o proprietário do domínio.
  
> [!NOTE]
> Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar. 
  
1. Para começar, vá para a página do cPanel no Hostgator. Será solicitado que você faça logon primeiro.
    
    (É atribuído um endereço cPanel exclusivo a cada conta hospedada no Hostgator. Seu endereço cPanel deve ter esta aparência: https://YourSiteAddress:secure-port-numberçoDoSeuSite:número-de-porta-segura. O email de inscrição que você recebeu do Hostgator especificará esse endereço, e um link cPanel também estará disponível na página de **hospedagem** .)
    
    > [!IMPORTANT]
    > To have a cPanel associated with your domain, you need a hosting account with Hostgator. Para começar a usar a Microsoft, você pode comprar uma conta de hospedagem do Hostgator ou [redelegar seus nameservers para apontar para a Microsoft](change-nameservers-at-hostgator.md). 
  
2. Na página **painel de controle** , na área **domínios** , selecione **Editor de zona avançada**.
    
3. Na página **Editor avançado de zona** , na área **adicionar registro** , nas caixas do novo registro, digite ou copie e cole os valores da tabela a seguir. 
    
    (Selecione o valor **Tipo** na lista suspensa.) 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |**Name** <br/> |**TTL** <br/> |**Tipo** <br/> |**Dados TXT** <br/> |
    |Use o  *domain_name*. (por exemplo, fourthcoffee.com.)  <br/> **Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)** <br/> |1   <br/> |TXT  <br/> |MS = ms *XXXXXXXX*  <br/> **Observação**: esse é um exemplo. Use aqui seu valor específico de **Destino ou Pontos de Endereçamento**, retirado da tabela. [Como localizo isto?](../get-help-with-domains/information-for-dns-records.md)          |
   
4. Selecione **adicionar registro**.
    
5. Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.
    
Agora que você adicionou o registro no site do seu registrador de domínios, retorne à Microsoft e solicite o registro.
  
Quando a Microsoft encontrar o registro TXT correto, seu domínio estará verificado.
  
1. No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.
    
2. Na página **Domínios**, clique no domínio que você está verificando. 
    
3. Na página **Configuração**, clique em **Iniciar configuração**.
    
4. Na página **Verificar domínio**, clique em **Verificar**.
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Adicione um registro MX para que o email do domínio vá para a Microsoft.
<a name="BKMK_add_MX"> </a>

> [!IMPORTANT]
> Antes de executar este procedimento, primeiro você deve executar o procedimento da primeira seção deste artigo, [Aponte seu domínio para sua conta de hospedagem](#point-your-domain-to-your-hosting-account). 
  
1. Para começar, vá para a página do cPanel no Hostgator. Será solicitado que você faça logon primeiro.
    
    (É atribuído um endereço cPanel exclusivo a cada conta hospedada no Hostgator. Seu endereço cPanel deve ter esta aparência: https://YourSiteAddress:secure-port-numberçoDoSeuSite:número-de-porta-segura. O email de inscrição que você recebeu do Hostgator especificará esse endereço, e um link cPanel também estará disponível na página de **hospedagem** .)
    
    > [!IMPORTANT]
    > To have a cPanel associated with your domain, you need a hosting account with Hostgator. Para começar a usar a Microsoft, você pode comprar uma conta de hospedagem do Hostgator ou [redelegar seus nameservers para apontar para a Microsoft](change-nameservers-at-hostgator.md). 
  
2. Na página **painel de controle** , na área **email** , selecione **entrada MX**.
    
 
3. Na área de **Roteamento de Email**, selecione **Mail Exchanger Remoto**.

4. Selecione **Alterar**.
  
5. Na área **Adicionar um novo registro** , nas caixas do novo registro, digite ou copie e cole os valores da tabela a seguir. 
    
    |**Prioridade**|**Destino**|
    |:-----|:-----|
    |,0  <br/> Para saber mais sobre prioridade, confira [O que é prioridade MX?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) <br/> | *\<domain-key\>*  .mail.protection.outlook.com  <br/> **Observação:** Obtenha a sua \< *domain-key*  \> através da sua conta Microsoft.  [Como localizo isto?](../get-help-with-domains/information-for-dns-records.md)          |
  
6. Selecione **Adicionar novo registro**.
   
 
7. Se houver outros registros MX na seção **registros MX** , remova cada um deles. 

    
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>Adicionar os seis registros CNAME necessários para o Microsoft
<a name="BKMK_add_CNAME"> </a>

> [!IMPORTANT]
> Antes de executar este procedimento, primeiro você deve executar o procedimento da primeira seção deste artigo, [Aponte seu domínio para sua conta de hospedagem](#point-your-domain-to-your-hosting-account). 
  
1. Para começar, vá para a página do cPanel no Hostgator. Será solicitado que você faça logon primeiro.
    
    (É atribuído um endereço cPanel exclusivo a cada conta hospedada no Hostgator. Seu endereço cPanel deve ter esta aparência: https://YourSiteAddress:secure-port-numberçoDoSeuSite:número-de-porta-segura. O email de inscrição que você recebeu do Hostgator especificará esse endereço, e um link cPanel também estará disponível na página de **hospedagem** .)
    
    > [!IMPORTANT]
    > To have a cPanel associated with your domain, you need a hosting account with Hostgator. Para começar a usar a Microsoft, você pode comprar uma conta de hospedagem do Hostgator ou [redelegar seus nameservers para apontar para a Microsoft](change-nameservers-at-hostgator.md). 
  
2. Na página **painel de controle** , na área **domínios** , selecione **Editor de zona avançada**.
    
3. Adicione o primeiro dos seis registros CNAME.
    
    Na página **Editor avançado de zona** , na área **adicionar registro** , nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir. 
    
    (Selecione o valor **Tipo** na lista suspensa.) 
    
    |**Name**|**TTL**|**Tipo**|**CNAME**|
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
> Não é possível ter mais de um registro TXT para SPF para um domínio. Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam. Se você já possui um registro SPF para seu domínio, não crie um novo para a Microsoft. Em vez disso, adicione os valores necessários da Microsoft ao registro atual para que você tenha um único registro SPF que inclua os dois conjuntos de valores. Precisa de exemplos? Confira os [Registros do Sistema de Nomes de Domínios externos para a Microsoft](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records#bkmk_spfrecords). To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.yml). 
  
> [!IMPORTANT]
> Antes de executar este procedimento, primeiro você deve executar o procedimento da primeira seção deste artigo, [Aponte seu domínio para sua conta de hospedagem](#point-your-domain-to-your-hosting-account). 
  
1. Para começar, vá para a página do cPanel no Hostgator. Será solicitado que você faça logon primeiro.
    
    (É atribuído um endereço cPanel exclusivo a cada conta hospedada no Hostgator. Seu endereço cPanel deve ter esta aparência: https://YourSiteAddress:secure-port-numberçoDoSeuSite:número-de-porta-segura. O email de inscrição que você recebeu do Hostgator especificará esse endereço, e um link cPanel também estará disponível na página de **hospedagem** .)
    
    > [!IMPORTANT]
    > To have a cPanel associated with your domain, you need a hosting account with Hostgator. Para começar a usar a Microsoft, você pode comprar uma conta de hospedagem do Hostgator ou [redelegar seus nameservers para apontar para a Microsoft](change-nameservers-at-hostgator.md). 
  
2. Na página **painel de controle** , na área **domínios** , selecione **Editor de zona avançada**.
    
3. On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Selecione o valor **Tipo** na lista suspensa.) 
    
    |**Name**|**TTL**|**Tipo**|**Dados TXT**|
    |:-----|:-----|:-----|:-----|
    |Use o  *domain_name*. (por exemplo, fourthcoffee.com.)  <br/> **Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)** <br/> |3600  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.           |
  
4. Selecione **adicionar registro**.
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Adicionar os dois registros SRV necessários para a Microsoft
<a name="BKMK_add_SRV"> </a>

> [!IMPORTANT]
> Antes de executar este procedimento, primeiro você deve executar o procedimento da primeira seção deste artigo, [Aponte seu domínio para sua conta de hospedagem](#point-your-domain-to-your-hosting-account). 
  
1. Para começar, vá para a página do cPanel no Hostgator. Será solicitado que você faça logon primeiro.
    
    (É atribuído um endereço cPanel exclusivo a cada conta hospedada no Hostgator. Seu endereço cPanel deve ter esta aparência: https://YourSiteAddress:secure-port-numberçoDoSeuSite:número-de-porta-segura. O email de inscrição que você recebeu do Hostgator especificará esse endereço, e um link cPanel também estará disponível na página de **hospedagem** .)
    
    > [!IMPORTANT]
    > To have a cPanel associated with your domain, you need a hosting account with Hostgator. Para começar a usar a Microsoft, você pode comprar uma conta de hospedagem do Hostgator ou [redelegar seus nameservers para apontar para a Microsoft](change-nameservers-at-hostgator.md). 
  
2. Na página **painel de controle** , na área **domínios** , selecione **Editor de zona avançada**.

    
3. Adicione o primeiro dos dois registros SRV.
    
    Na página **Editor Avançado de Zona DNS**, na área **Adicionar um Registro**, nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir. 
    
    (Selecione o valor **Tipo** na lista suspensa.) 
    
    |**Name**|**TTL**|**Tipo**|**Prioridade**|**Espessura**|**Porta**|**Destino**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip _sip._tls. *domain_name*. (por exemplo, _sip._tls.fourthcoffee.com.)  <br/> **Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)** <br/> |3600  <br/> |SRV  <br/> |100  <br/> |1   <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
    |_sipfederationtls _sipfederationtls._tcp. *domain_name*. (por exemplo, _sipfederationtls._tcp.fourthcoffee.com.)  <br/> **Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)** <br/> |3600  <br/> |SRV  <br/> |100  <br/> |1   <br/> |5061  <br/> |sipfed.online.lync.com  <br/> |
   

4. Selecione **adicionar registro**.

  
5. Adicione o outro registro SRV.
    
    Na seção **Adicionar um registro** , crie um registro usando os valores da próxima linha na tabela e, em seguida, selecione **adicionar registro** para concluir esse registro. 
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
