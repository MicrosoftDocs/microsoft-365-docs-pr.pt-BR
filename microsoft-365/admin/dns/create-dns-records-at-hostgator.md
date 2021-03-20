---
title: Criar registros DNS no Hostgator para a Microsoft
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
description: Aprenda a verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços no Hostgator para Microsoft.
ms.openlocfilehash: 790a7d77c9dbab37b87f8e7533515e75d2018e92
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910193"
---
# <a name="create-dns-records-at-hostgator-for-microsoft"></a>Criar registros DNS no Hostgator para a Microsoft

 **Caso não encontre o conteúdo que está procurando, [verifique as perguntas frequentes sobre domínios](../setup/domains-faq.yml)**. 
  
Se você usa a HostGator como provedor de hospedagem DNS, siga as etapas deste artigo para verificar o domínio e configurar registros DNS para o Skype for Business Online, email e outros serviços.
  
> [!IMPORTANT]
> Você deve executar o primeiro procedimento [abaixo,](#point-your-domain-to-your-hosting-account)Aponte seu domínio para sua conta de hospedagem , antes de adicionar registros DNS usando qualquer um dos outros procedimentos neste artigo. 

Depois de fazer todas essas alterações no Hostgator, seu domínio será definido para funcionar com os serviços da Microsoft.
  

  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="point-your-domain-to-your-hosting-account"></a>Aponte seu domínio para sua conta de hospedagem
<a name="BKMK_PointDomain"> </a>

> [!IMPORTANT]
> Você deve executar esse procedimento antes de executar qualquer um dos outros procedimentos neste artigo. 
  
Siga estas etapas para associar seu domínio e as contas de hospedagem.
  
1. Para começar, vá até a sua página de gerenciamento de domínios no HostGator, usando [este link](https://portal.hostgator.com/). Você será solicitado a fazer logon primeiro.
    
2. Selecione **Domínios** à esquerda.
  
3. Na página **Gerenciar Domínios,** selecione o domínio que você deseja atualizar. 
  
4. No menu pop-out à esquerda, selecione **Servidores de Nomes**.
  
5. Na página **Servidores de Nomes** para  o seu domínio, na lista lista de lista de espera automaticamente para minha conta de hospedagem, escolha a conta de hospedagem associada ao seu domínio. 
  
6. Selecione **Salvar Servidores de Nomes**.
    
  
## <a name="add-a-txt-record-for-verification"></a>Adicionar um registro TXT para verificação
<a name="BKMK_verify"> </a>

> [!IMPORTANT]
> Antes de executar este procedimento, primeiro você deve executar o procedimento da primeira seção deste artigo, [Aponte seu domínio para sua conta de hospedagem](#point-your-domain-to-your-hosting-account). 
  
Antes de usar o seu domínio com a Microsoft, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro de DNS prova à Microsoft que você é o proprietário do domínio.
  
> [!NOTE]
> Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar. 
  
1. Para começar, vá para a página do cPanel no Hostgator. Será solicitado que você faça logon primeiro.
    
    (É atribuído um endereço cPanel exclusivo a cada conta hospedada no Hostgator. Seu endereço cPanel deve ter esta aparência: https://YourSiteAddress:secure-port-numberçoDoSeuSite:número-de-porta-segura. O email de inscrição recebido do Hostgator especificará esse endereço e um link  cPanel também estará disponível na página Hospedagem.)
    
    > [!IMPORTANT]
    > To have a cPanel associated with your domain, you need a hosting account with Hostgator. Para começar a usar a Microsoft, você pode comprar uma conta de hospedagem do Hostgator ou [relegar seus nameservers](change-nameservers-at-hostgator.md)para apontar para a Microsoft . 
  
2. Na página **Painel de Controle,** na área **Domínios,** selecione **Editor de Zona Avançada**.
    
3. Na página **Editor de Zona Avançada,** na área **Adicionar** um Registro, nas caixas do novo registro, digite ou copie e copie e copie os valores da tabela a seguir. 
    
    (Selecione o valor **Tipo** na lista suspensa.) 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |**Name** <br/> |**TTL** <br/> |**Tipo** <br/> |**Dados TXT** <br/> |
    |Use seu  *domain_name*. (por exemplo, fourthcoffee.com.)  <br/> **Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)** <br/> |1  <br/> |TXT  <br/> |MS = ms *XXXXXXXX*  <br/> **Observação**: esse é um exemplo. Use aqui seu valor específico de **Destino ou Pontos de Endereçamento**, retirado da tabela. [Como localizo isto?](../get-help-with-domains/information-for-dns-records.md)          |
   
4. Selecione **Adicionar Registro**.
    
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
    
    (É atribuído um endereço cPanel exclusivo a cada conta hospedada no Hostgator. Seu endereço cPanel deve ter esta aparência: https://YourSiteAddress:secure-port-numberçoDoSeuSite:número-de-porta-segura. O email de inscrição recebido do Hostgator especificará esse endereço e um link  cPanel também estará disponível na página Hospedagem.)
    
    > [!IMPORTANT]
    > To have a cPanel associated with your domain, you need a hosting account with Hostgator. Para começar a usar a Microsoft, você pode comprar uma conta de hospedagem do Hostgator ou [relegar seus nameservers](change-nameservers-at-hostgator.md)para apontar para a Microsoft . 
  
2. Na página **Painel de Controle,** na área **Email,** selecione **Entrada MX**.
    
 
3. Na área de **Roteamento de Email**, selecione **Mail Exchanger Remoto**.

4. Selecione **Alterar**.
  
5. Na área **Adicionar um Novo Registro,** nas caixas do novo registro, digite ou copie e copie e colar os valores da tabela a seguir. 
    
    |**Prioridade**|**Destino**|
    |:-----|:-----|
    |0  <br/> Para saber mais sobre prioridade, confira [O que é prioridade MX?](../setup/domains-faq.yml) <br/> | *\<domain-key\>*  .mail.protection.outlook.com  <br/> **Observação:** Obtenha a sua \< *domain-key*  \> através da sua conta Microsoft.  [Como localizo isto?](../get-help-with-domains/information-for-dns-records.md)          |
  
6. Selecione **Adicionar Novo Registro**.
   
 
7. Se houver outros registros MX na seção **Registros MX,** remova cada um deles. 

    
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>Adicionar os seis registros CNAME necessários para a Microsoft
<a name="BKMK_add_CNAME"> </a>

> [!IMPORTANT]
> Antes de executar este procedimento, primeiro você deve executar o procedimento da primeira seção deste artigo, [Aponte seu domínio para sua conta de hospedagem](#point-your-domain-to-your-hosting-account). 
  
1. Para começar, vá para a página do cPanel no Hostgator. Será solicitado que você faça logon primeiro.
    
    (É atribuído um endereço cPanel exclusivo a cada conta hospedada no Hostgator. Seu endereço cPanel deve ter esta aparência: https://YourSiteAddress:secure-port-numberçoDoSeuSite:número-de-porta-segura. O email de inscrição recebido do Hostgator especificará esse endereço e um link  cPanel também estará disponível na página Hospedagem.)
    
    > [!IMPORTANT]
    > To have a cPanel associated with your domain, you need a hosting account with Hostgator. Para começar a usar a Microsoft, você pode comprar uma conta de hospedagem do Hostgator ou [relegar seus nameservers](change-nameservers-at-hostgator.md)para apontar para a Microsoft . 
  
2. Na página **Painel de Controle,** na área **Domínios,** selecione **Editor de Zona Avançada**.
    
3. Adicione o primeiro dos seis registros CNAME.
    
    Na página Editor de **Zona** Avançada, na área Adicionar um Registro, nas caixas do novo registro, digite ou copie e copie e copie os valores da primeira linha da tabela **a** seguir. 
    
    (Selecione o valor **Tipo** na lista suspensa.) 
    
    |**Name**|**TTL**|**Tipo**|**CNAME**|
    |:-----|:-----|:-----|:-----|
    |autodiscover. *domain_name*. (por exemplo, autodiscover.fourthcoffee.com.)  <br/> **Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)** <br/> |3600  <br/> |CNAME  <br/> |autodiscover.outlook.com  <br/> |
    |sip. *domain_name*. (por exemplo, sip.fourthcoffee.com.)  <br/> **Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)** <br/> |3600  <br/> |CNAME  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover. *domain_name*. (por exemplo, lyncdiscover.fourthcoffee.com.)  <br/> **Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)** <br/> |3600  <br/> |CNAME  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration. *domain_name*. (por exemplo, enterpriseregistration.fourthcoffee.com.)  <br/> **Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)** <br/> |3600  <br/> |CNAME  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment. *domain_name*. (por exemplo, enterpriseregistration.fourthcoffee.com.)  <br/> **Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)** <br/> |3600  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |

  
4. Selecione **Adicionar Registro**.

5. Adicione cada um dos outros cinco registros CNAME.
    
    Na seção **Adicionar um Registro,** crie um registro usando os valores da próxima linha da tabela e selecione Adicionar **Registro** novamente para concluir esse registro. 
    
    Repita esse processo até ter criado todos os seis registros CNAME.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Não é possível ter mais de um registro TXT para SPF para um domínio. Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam. Se você já possui um registro SPF para seu domínio, não crie um novo para a Microsoft. Em vez disso, adicione os valores necessários da Microsoft ao registro atual para que você tenha um único registro SPF que inclua os dois conjuntos de valores. Precisa de exemplos? Confira os [Registros do Sistema de Nomes de Domínios externos para a Microsoft](../../enterprise/external-domain-name-system-records.md#bkmk_spfrecords). To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.yml). 
  
> [!IMPORTANT]
> Antes de executar este procedimento, primeiro você deve executar o procedimento da primeira seção deste artigo, [Aponte seu domínio para sua conta de hospedagem](#point-your-domain-to-your-hosting-account). 
  
1. Para começar, vá para a página do cPanel no Hostgator. Será solicitado que você faça logon primeiro.
    
    (É atribuído um endereço cPanel exclusivo a cada conta hospedada no Hostgator. Seu endereço cPanel deve ter esta aparência: https://YourSiteAddress:secure-port-numberçoDoSeuSite:número-de-porta-segura. O email de inscrição recebido do Hostgator especificará esse endereço e um link  cPanel também estará disponível na página Hospedagem.)
    
    > [!IMPORTANT]
    > To have a cPanel associated with your domain, you need a hosting account with Hostgator. Para começar a usar a Microsoft, você pode comprar uma conta de hospedagem do Hostgator ou [relegar seus nameservers](change-nameservers-at-hostgator.md)para apontar para a Microsoft . 
  
2. Na página **Painel de Controle,** na área **Domínios,** selecione **Editor de Zona Avançada**.
    
3. On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Selecione o valor **Tipo** na lista suspensa.) 
    
    |**Name**|**TTL**|**Tipo**|**Dados TXT**|
    |:-----|:-----|:-----|:-----|
    |Use seu  *domain_name*. (por exemplo, fourthcoffee.com.)  <br/> **Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)** <br/> |3600  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.           |
  
4. Selecione **Adicionar Registro**.
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Adicionar os dois registros SRV necessários para a Microsoft
<a name="BKMK_add_SRV"> </a>

> [!IMPORTANT]
> Antes de executar este procedimento, primeiro você deve executar o procedimento da primeira seção deste artigo, [Aponte seu domínio para sua conta de hospedagem](#point-your-domain-to-your-hosting-account). 
  
1. Para começar, vá para a página do cPanel no Hostgator. Será solicitado que você faça logon primeiro.
    
    (É atribuído um endereço cPanel exclusivo a cada conta hospedada no Hostgator. Seu endereço cPanel deve ter esta aparência: https://YourSiteAddress:secure-port-numberçoDoSeuSite:número-de-porta-segura. O email de inscrição recebido do Hostgator especificará esse endereço e um link  cPanel também estará disponível na página Hospedagem.)
    
    > [!IMPORTANT]
    > To have a cPanel associated with your domain, you need a hosting account with Hostgator. Para começar a usar a Microsoft, você pode comprar uma conta de hospedagem do Hostgator ou [relegar seus nameservers](change-nameservers-at-hostgator.md)para apontar para a Microsoft . 
  
2. Na página **Painel de Controle,** na área **Domínios,** selecione **Editor de Zona Avançada**.

    
3. Adicione o primeiro dos dois registros SRV.
    
    Na página **Editor Avançado de Zona DNS**, na área **Adicionar um Registro**, nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir. 
    
    (Selecione o valor **Tipo** na lista suspensa.) 
    
    |**Name**|**TTL**|**Tipo**|**Prioridade**|**Espessura**|**Porta**|**Destino**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip._tls. *domain_name*. (por exemplo, _sip._tls.fourthcoffee.com.)  <br/> **Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)** <br/> |3600  <br/> |SRV  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
    |_sipfederationtls._tcp. *domain_name*. (por exemplo, _sipfederationtls._tcp.fourthcoffee.com.)  <br/> **Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)** <br/> |3600  <br/> |SRV  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com  <br/> |
   

4. Selecione **Adicionar Registro**.

  
5. Adicione o outro registro SRV.
    
    Na seção **Adicionar um Registro,** crie um registro usando os valores da próxima linha da tabela e selecione Adicionar **Registro** novamente para concluir esse registro. 
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).