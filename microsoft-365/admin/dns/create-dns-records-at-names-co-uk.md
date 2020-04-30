---
title: Criar registros DNS no Names.co.uk para Microsoft
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
ms.assetid: b6c15128-b456-49b4-8b5e-5b823c700f26
description: Saiba como verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços em Names.co.uk para a Microsoft.
ms.openlocfilehash: 91c328877d583f415ffd2b8312ff1dc899a05bcc
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/29/2020
ms.locfileid: "43939162"
---
# <a name="create-dns-records-at-namescouk-for-microsoft"></a>Criar registros DNS no Names.co.uk para Microsoft

 **Caso não encontre o conteúdo que está procurando, [verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**. 
  
Se você usa a Names.co.uk como provedor de hospedagem DNS, siga as etapas deste artigo para verificar o domínio e configurar registros DNS para o Skype for Business Online, email e outros serviços.
    
Depois que você adicionar esses registros no Names.co.uk, o domínio será configurado para funcionar com os serviços da Microsoft.
  

  
> [!NOTE]
>  Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Adicionar um registro TXT para verificação
<a name="BKMK_verify"> </a>

Antes de usar o seu domínio com a Microsoft, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro de DNS prova à Microsoft que você é o proprietário do domínio.
  
> [!NOTE]
> Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar. 
  
1. Para começar, vá para a página de domínios em Names.co.uk usando [este link](https://account.names.co.uk/dashboard#/). Será solicitado que você faça logon primeiro.
    
    ![NamesUK-BP-configure-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list. 
    
    (You may have to scroll down.)
    
    ![NamesUK-BP-configure-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    (Se você precisar adicionar uma linha, selecione **adicionar registros a/CNAME (+)**.)
    
    (You may have to scroll down.)
        
    |**Nome do host**|**Tipo**|**Resultado**|
    |:-----|:-----|:-----|
    |(Leave this field empty.)  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **Observação**: esse é um exemplo. Use aqui seu valor específico de **Destino ou Pontos de Endereçamento**, retirado da tabela.           [Como localizo isto?](../get-help-with-domains/information-for-dns-records.md)    |
       
    ![NamesUK-BP-Verify-1-1](../../media/91ed1f22-a796-418d-bbb0-345e2cd99bde.png)
  
4. Selecione **Salvar**.
    
    (You may have to scroll down.)
    
    ![NamesUK-BP-Verify-1-2](../../media/40e991f9-2209-4210-8762-981cca670d70.png)
  
5. Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.
    
Agora que você adicionou o registro no site do seu registrador de domínios, retorne à Microsoft e solicite o registro.
  
Quando a Microsoft encontrar o registro TXT correto, seu domínio estará verificado.
  
1. No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.
    
2. Na página **Domínios**, clique no domínio que você está verificando. 
    
    
  
3. Na página **Configuração**, clique em **Iniciar configuração**.
    
    
  
4. Na página **Verificar domínio**, marque **Verificar**.
    
    
  
> [!NOTE]
>  Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Adicione um registro MX para que o email do domínio vá para a Microsoft.
<a name="BKMK_add_MX"> </a>

1. Para começar, vá para a página de domínios em Names.co.uk usando [este link](https://account.names.co.uk/dashboard#/). Será solicitado que você faça logon primeiro.
    
    ![NamesUK-BP-configure-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list. 
    
    (You may have to scroll down.)
    
    ![NamesUK-BP-configure-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. Na página **Adicionar/Modificar Zona DNS**, na seção **Registros mail exchange**, digite ou copie e cole os valores nas caixas do novo registro, a partir da tabela a seguir. 
    
    (You may have to scroll down.)
    
    |**Nome do host**|**Prioridade**|**Resultado**|
    |:-----|:-----|:-----|
    |(Deixe este campo vazio.)  <br/> |1  <br/> Para saber mais sobre prioridade, confira [O que é prioridade MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> | *\<chave-do-domínio\>*  .mail.protection.outlook.com  <br/> > [!NOTE]> obter sua * \<chave\> de domínio* de sua conta da Microsoft.           [Como localizo isto?](../get-help-with-domains/information-for-dns-records.md)          |
       
    ![NamesUK-BP-configure-2-1](../../media/e211d73d-864f-4114-864b-8e636c69f595.png)
  
4. Selecione **Salvar**.
    
    (You may have to scroll down.)
    
    ![NamesUK-BP-configure-2-2](../../media/01e6c801-daa2-40ca-84f9-dcac6422257c.png)
  
5. Se houver outros registros MX listados na seção **Registros mail exchange**, selecione cada um deles e pressione a tecla **Delete** no teclado para excluí-los. 
    
    ![NamesUK-BP-configure-2-3](../../media/f8e43926-b724-4690-94e7-ec4b8d7a8da5.png)
  
6. Selecione **Salvar**.
    
    (You may have to scroll down.)
    
    ![NamesUK-BP-configure-2-4](../../media/cd705919-d0bd-408f-82be-b54e732cb05c.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>Adicionar os seis registros CNAME necessários para o Microsoft
<a name="BKMK_add_CNAME"> </a>

1. Para começar, vá para a página de domínios em Names.co.uk usando [este link](https://account.names.co.uk/dashboard#/). Será solicitado que você faça logon primeiro.
    
    ![NamesUK-BP-configure-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list. 
    
    (You may have to scroll down.)
    
    ![NamesUK-BP-configure-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    (Se você precisar adicionar uma linha, selecione **adicionar registros a/CNAME (+)**.)
    
    (You may have to scroll down.)
    
    |**Nome do Host**|**Tipo**|**Resultado**|
    |:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |CNAME  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
       
    ![NamesUK-BP-configure-3-1](../../media/392772bf-2ed3-4959-9a9a-bb1611905e86.png)
  
4. Selecione **Salvar**.
    
    ![NamesUK-BP-configure-3-2](../../media/c009795e-7eef-4804-bf23-556f498306cc.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Adicionar registro TXT à SPF para ajudar a evitar spam de email
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Não é possível ter mais de um registro TXT para SPF para um domínio. Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam. Se você já possui um registro SPF para seu domínio, não crie um novo para a Microsoft. Em vez disso, adicione os valores necessários da Microsoft ao registro atual para que você tenha um *único* registro SPF que inclua os dois conjuntos de valores.
  
1. Para começar, vá para a página de domínios em Names.co.uk usando [este link](https://account.names.co.uk/dashboard#/). Será solicitado que você faça logon primeiro.
    
    ![NamesUK-BP-configure-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list. 
    
    (You may have to scroll down.)
    
    ![NamesUK-BP-configure-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. Na página **zonas DNS na conta** , na coluna **nome do domínio** , selecione o nome do domínio que você está atualizando. 
    
    ![NamesUK-BP-configure-1-2-1](../../media/20254eec-6952-47ba-b12b-da32860ee7ef.png)
  
4. On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    (Se você precisar adicionar uma linha, selecione **adicionar registros a/CNAME (+)**.)
    
    (You may have to scroll down.)
    
    |**Nome do host**|**Tipo**|**Resultado**|
    |:-----|:-----|:-----|
    |(Leave this field empty.)  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Observação:** é recomendável copiar e colar essa entrada, para que todo o espaçamento permaneça correto.           |
       
    ![NamesUK-BP-configure-4-1](../../media/cfc61387-630e-4aa0-8762-ef36eaeda44a.png)
  
5. Selecione **Salvar**.
    
    (You may have to scroll down.)
    
    ![NamesUK-BP-configure-4-2](../../media/b4d445a1-09c0-46c3-8141-672cc2831a9b.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Adicionar os dois registros SRV necessários para a Microsoft
<a name="BKMK_add_SRV"> </a>

1. Para começar, vá para a página de domínios em Names.co.uk usando [este link](https://account.names.co.uk/dashboard#/). Será solicitado que você faça logon primeiro.
    
    ![NamesUK-BP-configure-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list. 
    
    (You may have to scroll down.)
    
    ![NamesUK-BP-configure-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. Na página **Adicionar/Modificar Zona DNS**, na seção **Registros de serviço**, digite ou copie e cole os valores da tabela a seguir nas caixas do novo registro. 
    
    (Pode ser necessário rolar para baixo.)
    
    |**Nome**|**Prioridade**|**Espessura**|**Porta**|**Resultado**|
    |:-----|:-----|:-----|:-----|:-----|
    |_sip. _tls  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
    |_sipfederationtls. _tcp  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com  <br/> |
       
    ![NamesUK-BP-configure-5-1](../../media/97a96523-005a-4058-9e12-19f6c3bf9b3b.png)
  
4. Selecione **Salvar**.
    
    (Pode ser necessário rolar para baixo.)
    
    ![NamesUK-BP-configure-5-2](../../media/bb617a5f-14f9-44b7-9256-bdef34d22d6b.png)
  
> [!NOTE]
>  Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
