---
title: Criar registros DNS no DNSMadeEasy para o Office 365
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
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
ms.assetid: e158b079-b054-4b7e-8e01-e55169ce18d7
description: Saiba como verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços em DNSMadeEasy para o Office 365.
ms.openlocfilehash: 7b94b8d4b3a02a0f436ba2af314eece8b7606ec2
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42238830"
---
# <a name="create-dns-records-at-dnsmadeeasy-for-office-365"></a>Criar registros DNS no DNSMadeEasy para o Office 365

 **Caso não encontre o conteúdo que está procurando, [verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**. 
  
Se você usa a DNSMadeEasy como provedor de hospedagem DNS, siga as etapas deste artigo para verificar o domínio e configurar registros DNS para o Skype for Business Online, email e outros serviços.
  
Depois que você adicionar esses registros na DNSMadeEasy, o domínio será configurado para funcionar com os serviços do Office 365.
  
Para saber mais sobre hospedagem na Web e DNS para sites com o Office 365, confira [Usar um site público com o Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).
  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. Se você estiver tendo problemas com o fluxo de emails ou com outros problemas após adicionar registros DNS, consulte [Localizar e corrigir problemas após adicionar seu domínio ou registros DNS no Office 365](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Adicionar um registro TXT para verificação
<a name="BKMK_verify"> </a>

Antes de usar o seu domínio com o Office 365, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro DNS prova ao Office 365 que você é o proprietário do domínio.
  
> [!NOTE]
> Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar. 
  
> [!IMPORTANT]
> Para contas do DNSMadeEasy, o domínio adicionado foi comprado de um registrador de domínio separado. O DNSMadeEasy não oferece serviços de registro de domínio. Sua capacidade de fazer logon em DNSMadeEasy e criar o registro DNS é uma prova de propriedade suficiente. 
  
1. Para começar, vá para sua página de domínios no DNSMadeEasy usando [este link](https://cp.dnsmadeeasy.com/). Será solicitado que você faça logon primeiro.
    
2. Na página **console de gerenciamento** , na área **domínios atualizados recentemente** , selecione o domínio que você deseja atualizar. 
    
3. Na página **DNS gerenciado** , na área **registros txt** , selecione o controle ( **+**) ( **Adicionar novo**).
    
    (You may have to scroll down.)
    
4. In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    ||||
    |:-----|:-----|:-----|
    |**Nome** <br/> |**Valor** <br/> |**TTL** <br/> |
    |(Deixe este campo vazio.)  <br/> |MS = ms *XXXXXXXX*  <br/> **Observação:** Este é um exemplo. Use aqui o valor específico de **Destino ou Pontos de Endereçamento**, retirado da tabela em Office 365. [Como faço para encontrar isso?](../get-help-with-domains/information-for-dns-records.md)          |1800  <br/> |
   
5. Selecione **Enviar**.
    
6. Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.
    
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. No centro de administração, vá para a página de <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a> de **configurações** \> .

    
2. Na página **domínios** , selecione o domínio que você está verificando. 
    
3. Na página **configuração** , selecione **Iniciar configuração**.
    
4. Na página **verificar domínio** , selecione **verificar**.
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. Se você estiver tendo problemas com o fluxo de emails ou com outros problemas após adicionar registros DNS, consulte [Localizar e corrigir problemas após adicionar seu domínio ou registros DNS no Office 365](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a>Adicionar um registro MX para que o email do domínio vá para o Office 365
<a name="BKMK_add_MX"> </a>

1. Para começar, vá para sua página de domínios no DNSMadeEasy usando [este link](https://cp.dnsmadeeasy.com/). Será solicitado que você faça logon primeiro.
    
2. Na página **console de gerenciamento** , na área **domínios atualizados recentemente** , selecione o domínio que você deseja atualizar. 
    
    Na página **console de gerenciamento** , na área **domínios atualizados recentemente** , selecione o domínio que você deseja atualizar. 
    
    ![DNSMadeEasy-BP-configure-1-2](../media/8d8f403e-d7cd-429e-913b-dacb1f4644a2.png)
  
3. Na página **DNS gerenciado** , na área **registros MX** , selecione o controle **(+)** ( **Adicionar novo**).
    
    (You may have to scroll down.)
    
    ![DNSMadeEasy-BP-configure-2-1](../media/404c73bf-1db4-4d68-82d8-68303f418ed4.png)
  
4. Na área **Adicionar Registros MX**, nas caixas do novo registro, digite ou copie e cole os valores da tabela a seguir. 
    
    (Pode ser necessário rolar para baixo.)
    
    |**Nome**|**Servidor**|**Nível de MX**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |(Deixe este campo vazio.)  <br/> | *\<chave-do-domínio\>*  .mail.protection.outlook.com  <br/> **Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)** <br/> **Observação:** Obtenha sua \< *chave* \> de domínio de sua conta do Office 365. [Como faço para encontrar isso?](../get-help-with-domains/information-for-dns-records.md)          |10   <br/> Para saber mais sobre prioridade, confira [O que é prioridade MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> |1800  <br/> |
   
    ![DNSMadeEasy-BP-configure-2-2](../media/69b53af9-1eec-435c-8434-1b6058c1ec82.png)
  
5. Selecione **Enviar**.
    
    ![DNSMadeEasy-BP-configure-2-3](../media/381054a6-bb85-4ebb-b576-42cbba78ed1b.png)
  
6. Se houver outros registros MX listados na seção **Registros MX**, exclua todos eles selecionando cada um deles. 
    
    ![DNSMadeEasy-BP-configure-2-4-1](../media/58a07769-0b30-4111-b555-bfc3b82a7d4c.png)
  
7. Quando todos os registros estiverem selecionados, selecione **excluir selecionado**.
    
    ![DNSMadeEasy-BP-configure-2-4-2](../media/e9064c07-1ce7-4387-b47a-90d4193da374.png)
  
8. Na caixa de diálogo **excluir registros MX** , selecione **excluir** para confirmar suas alterações. 
    
    ![DNSMadeEasy-BP-configure-2-5](../media/03c405e5-868f-468f-b6d2-046d27b201fb.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-office-365"></a>Adicionar os cinco registros CNAME necessários para o Office 365
<a name="BKMK_add_CNAME"> </a>

1. Para começar, vá para sua página de domínios no DNSMadeEasy usando [este link](https://cp.dnsmadeeasy.com/). Será solicitado que você faça logon primeiro.
    
2. Na página **console de gerenciamento** , na área **domínios atualizados recentemente** , selecione o domínio que você deseja atualizar. 
    
3. Na página **DNS gerenciado** , na área **registros CNAME** , selecione o controle **(+)** ( **Adicionar novo**).
    
    (Pode ser necessário rolar para baixo.)
    
    ![DNSMadeEasy-BP-configure-3-1](../media/a5feb238-690d-4b64-a625-91a82b3f4068.png)
  
4. Adicione o primeiro dos cinco registros CNAME.
    
    Na área **Adicionar Registros CNAME**, nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir. 
    
    |**Nome**|**Alias para**|**TTL**|
    |:-----|:-----|:-----|
    |autodiscover  <br/> |autodiscover.outlook.com.  <br/> **Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)** <br/> |1800  <br/> |
    |sip  <br/> |sipdir.online.lync.com.  <br/> **Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)** <br/> |1800  <br/> |
    |lyncdiscover  <br/> |webdir.online.lync.com.  <br/> **Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)** <br/> |1800  <br/> |
    |enterpriseregistration  <br/> |enterpriseregistration.windows.net.  <br/> **Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)** <br/> |1800  <br/> |
    |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> **Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)** <br/> |1800  <br/> |
   
    ![DNSMadeEasy-BP-configure-3-2](../media/de6dddcd-bf0a-4993-ab4c-a6d10167bf34.png)
  
5. Selecione **Enviar**.
    
    ![DNSMadeEasy-BP-configure-3-3](../media/e44ef73e-99cb-41ce-a3f2-549cb2f29eef.png)
  
6. Adicione cada um dos outros quatro registros CNAME.
    
    Na seção **registros CNAME** , selecione o controle **(+)** ( **Adicionar novo**), crie um registro usando os valores da próxima linha na tabela e, em seguida, selecione **Enviar** para concluir esse registro. 
    
    Repita esse processo até ter criado todos os cinco registros CNAME.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Adicionar registro TXT à SPF para ajudar a evitar spam de email
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. Em vez disso, adicione os valores necessários do Office 365 ao registro atual, de modo que você tenha um  *único*  registro SPF que inclua os dois conjuntos de valores. Precisa de exemplos? Confira estes [registros de sistema de nomes de domínio externo para o Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0). Para validar o registro SPF, você pode usar uma destas[ferramentas de validação de SPF](../setup/domains-faq.md). 
  
1. Para começar, vá para sua página de domínios no DNSMadeEasy usando [este link](https://cp.dnsmadeeasy.com/). Será solicitado que você faça logon primeiro.
    
2. Na página **console de gerenciamento** , na área **domínios atualizados recentemente** , selecione o domínio que você deseja atualizar. 
    
3. Na página **DNS gerenciado** , na área **registros txt** , selecione o controle **(+)** ( **Adicionar novo**).
    
    (Pode ser necessário rolar para baixo.)
    
    ![DNSMadeEasy-BP-configure-4-1](../media/657b87a5-dcb4-4ae7-8f27-bd857f0f4189.png)
  
4. In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    |**Nome**|**Valor**|**TTL**|
    |:-----|:-----|:-----|
    |(Deixe este campo vazio.)  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Observação:** É recomendável copiar e colar essa entrada, para que todo o espaçamento permaneça correto.           |1800  <br/> |
   
    ![DNSMadeEasy-BP-configure-4-2](../media/b317bcb9-18c6-4609-a8f4-963823032669.png)
  
5. Selecione **Enviar**.
    
    ![DNSMadeEasy-BP-configure-4-3](../media/8a1c53c3-1222-4127-a190-70f6f5059433.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>Adicionar os dois registros SRV necessários para o Office 365
<a name="BKMK_add_SRV"> </a>

1. Para começar, vá para sua página de domínios no DNSMadeEasy usando [este link](https://cp.dnsmadeeasy.com/). Será solicitado que você faça logon primeiro.
    
2. Na página **console de gerenciamento** , na área **domínios atualizados recentemente** , selecione o domínio que você deseja atualizar. 
    
3. Na página **DNS gerenciado** , na área **Registros SRV** , selecione o controle **(+)** ( **Adicionar novo**).
    
    Pode ser necessário rolar para baixo.
    
    ![DNSMadeEasy-BP-configure-5-1](../media/5c9e8f50-adbd-4f23-8ce3-2844b2896f3f.png)
  
4. Adicione o primeiro dos dois registros SRV.
    
    Na área **Adicionar Registros SRV**, nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir. 
    
    |**Nome**|**Prioridade**|**Peso**|**Porta**|**Host**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip. _tls  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com.  <br/> **Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)** <br/> |1800  <br/> |
    |_sipfederationtls. _tcp  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com.  <br/> **Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)** <br/> |1800  <br/> |
   
    ![DNSMadeEasy-BP-configure-5-2](../media/e1155f94-575f-441a-9a61-d948391d42ca.png)
  
5. Selecione **Enviar**.
    
    ![DNSMadeEasy-BP-configure-5-3](../media/7eae54e1-08bd-4902-afdf-fd5cc251ab59.png)
  
6. Adicione o outro registro SRV.
    
    Na seção **Registros SRV** , selecione o controle **(+)** ( **Adicionar novo**), crie um registro usando os valores da próxima linha na tabela e, em seguida, selecione **Enviar** para concluir esse registro. 
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. Se você estiver tendo problemas com o fluxo de emails ou com outros problemas após adicionar registros DNS, consulte [Localizar e corrigir problemas após adicionar seu domínio ou registros DNS no Office 365](../get-help-with-domains/find-and-fix-issues.md). 
  

