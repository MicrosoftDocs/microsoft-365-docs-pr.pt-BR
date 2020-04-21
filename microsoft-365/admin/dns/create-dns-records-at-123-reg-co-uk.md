---
title: Criar registros DNS no 123-reg.co.uk para Microsoft
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
ms.assetid: 1f2d08c9-2a88-4d2f-ae1f-e39f9e358b17
description: Saiba como verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços em 123-reg.co.uk para a Microsoft.
ms.openlocfilehash: 887e7e6fc42fb55d4cc09ba66b68a2bb9702bbb9
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629738"
---
# <a name="create-dns-records-at-123-regcouk-for-microsoft"></a>Criar registros DNS no 123-reg.co.uk para Microsoft

 **Caso não encontre o conteúdo que está procurando, [verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**. 
  
Se você usa a 123-reg.co.uk como provedor de hospedagem DNS, siga as etapas deste artigo para verificar o domínio e configurar registros DNS para o Skype for Business Online, email e outros serviços.
  
Depois que você adicionar esses registros no 123-reg.co.uk, o domínio será configurado para funcionar com os serviços da Microsoft.
  
Para saber mais sobre o webhosting e o DNS para sites com a Microsoft, confira [usar um site público com a Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).
  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você estiver tendo problemas com o fluxo de emails ou com outros problemas após adicionar registros DNS, consulte [Localizar e corrigir problemas após adicionar seu domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Adicionar um registro TXT para verificação
<a name="BKMK_verify"> </a>

Antes de usar seu domínio com a Microsoft, precisamos garantir que você o tenha. Sua capacidade de fazer logon em sua conta no registrador de domínios e criar o registro DNS comprova para a Microsoft que você é o proprietário do domínio.
  
> [!NOTE]
> Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar. 
  
1. Para começar, vá para sua página de domínios em 123-reg.co.uk usando [este link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). Será solicitado que você faça logon primeiro.
    
2. On the **Domain name overview** page, select the name of the domain that you want to edit. 
    
3. Choose **DNS** from the **Select action** drop-down list. 
    
4. Na página **gerenciar seu DNS** , selecione a guia **DNS avançado** . 
    
5. In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    ||||
    |:-----|:-----|:-----|
    |**Nome do host** <br/> |**Tipo** <br/> |**Destination TXT/SPF** <br/> |
    |@  <br/> |TXT/SPF  <br/> |MS = ms *XXXXXXXX*  <br/> **Observação**: esse é um exemplo. Use o seu **destino específico ou aponte para** o valor de endereço aqui, a partir da tabela. [Como localizo isto?](../get-help-with-domains/information-for-dns-records.md)          |
   
6. Clique em **Adicionar**.
    
7. Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.
    
Agora que você adicionou o registro no site do seu registrador de domínio, você voltará para a Microsoft e solicitará uma pesquisa para o registro.
  
Quando a Microsoft encontrar o registro TXT correto, seu domínio será verificado.
  
1. No centro de administração da Microsoft, vá para a página de <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a> de **configurações** \> .

    
2. Na página **Domínios**, clique no domínio que você está verificando. 
    
3. Na página **Configuração**, clique em **Iniciar configuração**.
    
4. Na página **Verificar domínio**, clique em **Verificar**.
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você estiver tendo problemas com o fluxo de emails ou com outros problemas após adicionar registros DNS, consulte [Localizar e corrigir problemas após adicionar seu domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Adicionar um registro MX para que o email do seu domínio seja fornecido para a Microsoft
<a name="BKMK_add_MX"> </a>

1. Para começar, vá para sua página de domínios em 123-reg.co.uk usando [este link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). Será solicitado que você faça logon primeiro.
    
2. On the **Domain name overview** page, select the name of the domain that you want to edit. 
    
3. Choose **DNS** from the **Select action** drop-down list. 
    
4. Na página **gerenciar seu DNS** , selecione a guia **DNS avançado** . 
    
5. In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Nome do host**|**Tipo**|**Prioridade**|**MX de destino**|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |MX  <br/> |1  <br/> Para saber mais sobre prioridade, confira [O que é prioridade MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> | *\<domain-key\>*  .mail.protection.outlook.com.  <br/> **This value MUST end with a period (.)** <br/> **Observação:** Obtenha sua \<chave\> de domínio de sua conta da Microsoft. [Como localizo isto?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Copiar e colar valores da tabela](../../media/65366165-85a6-4a39-b9a7-6c5f47fbe790.png)
  
6. Clique em **Adicionar**.
    
    ![Selecione Adicionar](../../media/a8ae6c0c-4365-4137-af8a-6e003996e3d0.png)
  
7. Se houver outros registros MX, remova cada um deles escolhendo o ícone **Excluir (Lixeira)** do registro. 
    
    ![Selecionar Delete (o ícone lixeira)](../../media/3be635e6-b591-49af-8430-a158272834b4.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>Adicionar os seis registros CNAME necessários para o Microsoft
<a name="BKMK_add_CNAME"> </a>

1. Para começar, vá para sua página de domínios em 123-reg.co.uk usando [este link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). Será solicitado que você faça logon primeiro.
    
2. On the **Domain name overview** page, select the name of the domain that you want to edit. 
    
3. Choose **DNS** from the **Select action** drop-down list. 
    
4. Na página **gerenciar seu DNS** , selecione a guia **DNS avançado** . 
    
5. Adicione o primeiro dos seis registros CNAME.
    
    In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Nome do host**|**Tipo**|**CNAME de destino**|
    |:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |autodiscover.outlook.com.  <br/> **This value MUST end with a period (.)** <br/> |
    |sip  <br/> |CNAME  <br/> |sipdir.online.lync.com.  <br/> **This value MUST end with a period (.)** <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |webdir.online.lync.com.  <br/> **This value MUST end with a period (.)** <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |enterpriseregistration.windows.net.  <br/> **Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)** <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> **Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)** <br/> |
   
    ![Copiar e colar os valores da tabela](../../media/24bf388c-5f7f-4fc0-b4ec-4b17226b6246.png)
  
6. Clique em **Adicionar**.
    
    ![Selecione Adicionar](../../media/825a9854-559d-4a22-90ac-5e7a0a54269a.png)
  
7. Adicione os outros cinco registros CNAME.
    
    Na seção **DNS avançado** , crie um registro usando os valores da próxima linha na tabela e, em seguida, selecione **Adicionar** para concluir esse registro. 
    
    Repita esse processo até ter criado todos os seis registros CNAME.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Não é possível ter mais de um registro TXT para SPF para um domínio. Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam. Se você já tiver um registro SPF para seu domínio, não crie um novo para o Microsfot. Em vez disso, adicione os valores necessários da Microsoft ao registro atual para que você tenha um *único* registro SPF que inclua os dois conjuntos de valores. Precisa de exemplos? Confira estes [registros de sistema de nomes de domínio externo para a Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords). Para validar o seu registro SPF, use uma destas [ferramentas de validação de SPF](../setup/domains-faq.md). 
  
1. Para começar, vá para sua página de domínios em 123-reg.co.uk usando [este link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). Será solicitado que você faça logon primeiro.
    
2. On the **Domain name overview** page, select the name of the domain that you want to edit. 
    
3. Choose **DNS** from the **Select action** drop-down list. 
    
4. Na página **gerenciar seu DNS** , selecione a guia **DNS avançado** . 
    
5. In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Nome do host**|**Tipo**|**Destination TXT/SPF**|
    |:-----|:-----|:-----|
    |@  <br/> |TXT/SPF  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.           |
   
    ![123Reg-BP-configure-4-1](../../media/4697701c-eba0-4b03-8d75-4f7fc3bef94a.png)
  
6. Clique em **Adicionar**.
    
    ![Selecione Adicionar](../../media/7906dd91-fd23-44c3-bb37-ef185655c6eb.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Adicionar os dois registros SRV necessários para o Microsoft
<a name="BKMK_add_SRV"> </a>

1. Para começar, vá para sua página de domínios em 123-reg.co.uk usando [este link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). Será solicitado que você faça logon primeiro.
    
2. On the **Domain name overview** page, select the name of the domain that you want to edit. 
    
3. Choose **DNS** from the **Select action** drop-down list. 
    
4. Na página **gerenciar seu DNS** , selecione a guia **DNS avançado** . 
    
5. Adicione o primeiro dos dois registros SRV:
    
    In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    ||||||
    |:-----|:-----|:-----|:-----|:-----|
    |Nome do host|Tipo|Prioridade|TTL|SRV de destino|
    |_sip. _tls|SRV|100|3600|1 443 sipdir.online.lync.com. **This value MUST end with a period (.)**<br> **Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.           |
    |_sipfederationtls. _tcp|SRV|100|3600|1 5061 sipfed.online.lync.com. **This value MUST end with a period (.)** <br> **Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.           |
   
    ![Copiar e colar os valores da tabela](../../media/c1786b86-52ef-4dca-8b99-b479554fa531.png)
  
6. Clique em **Adicionar**.
    
    ![Selecione Adicionar](../../media/5fd9d3a2-a8bb-466b-829f-b3a6e54b5104.png)
  
7. Para adicionar o outro registro SRV:
    
    Na seção **DNS avançado** , crie um registro usando os valores da segunda linha na tabela e, em seguida, selecione **Adicionar** para concluir esse registro. 
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você estiver tendo problemas com o fluxo de emails ou com outros problemas após adicionar registros DNS, consulte [Localizar e corrigir problemas após adicionar seu domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
