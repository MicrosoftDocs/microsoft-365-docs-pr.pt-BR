---
title: Criar registros DNS no name.com para Microsoft
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
ms.assetid: 9ddcc2fc-9433-4335-8192-6ffb1f541087
description: Saiba como verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços em name.com para a Microsoft.
ms.openlocfilehash: 8518ca2570b3be1cb3abcd5c57b8309e989481cb
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/29/2020
ms.locfileid: "43938655"
---
# <a name="create-dns-records-at-namecom-for-microsoft"></a>Criar registros DNS no name.com para Microsoft

 **Caso não encontre o conteúdo que está procurando, [verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**. 
  
Se você usa a name.com como provedor de hospedagem DNS, realize os procedimentos deste artigo para verificar o domínio e configurar registros DNS para o Skype for Business Online, email e outros serviços.
  
Depois que você adicionar esses registros no name.com, o domínio será configurado para funcionar com os serviços da Microsoft.

  
> [!NOTE]
> Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Adicionar um registro TXT para verificação
<a name="BKMK_verify"> </a>

Antes de usar o seu domínio com a Microsoft, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro de DNS prova à Microsoft que você é o proprietário do domínio.
  
> [!NOTE]
> Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar. 
  
1. Para iniciar, vá para a sua página de domínios em name.com usando [este link](https://www.name.com/account/domain). Você será solicitado a fazer o logon primeiro.
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. Em **meus domínios**, selecione o nome do domínio que você deseja modificar.
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. Na coluna **detalhes** , selecione **registros DNS**. 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela.
    
    (Choose the **Type** value from the drop-down list.) 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |**Tipo** <br/> |**Host** <br/> |**Atender** <br/> |**TTL** <br/> |
    |TXT  <br/> |(Leave this field empty.)  <br/> |MS=ms *XXXXXXXX*  <br/> **Observação**: esse é um exemplo. Use aqui seu valor específico de **Destino ou Pontos de Endereçamento**, retirado da tabela.           [Como localizo isto?](../get-help-with-domains/information-for-dns-records.md)          |Use the default value (300).  <br/> |
   
    ![Nome-BP-Verify-1-1](../../media/0c352fd3-cf84-439f-a481-0705e225cc54.png)
  
5. Selecione **adicionar registro**.
    
    ![Name-BP-Verify-1-2](../../media/816fc60b-17ab-4982-8849-6c3fcf3ca3d6.png)
  
6. Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.
    
Agora que você adicionou o registro no site do seu registrador de domínios, retorne à Microsoft e solicite o registro.
  
Quando a Microsoft encontrar o registro TXT correto, seu domínio estará verificado.
  
1. No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.
    
2. Na página **Domínios**, clique no domínio que você está verificando. 
    
    
  
3. Na página **Configuração**, clique em **Iniciar configuração**.
    
    
  
4. Na página **Verificar domínio**, marque **Verificar**.
    
    
  
> [!NOTE]
> Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Adicione um registro MX para que o email do domínio vá para a Microsoft.
<a name="BKMK_add_MX"> </a>

1. Para iniciar, vá para a sua página de domínios em name.com usando [este link](https://www.name.com/account/domain). Você será solicitado a fazer o logon primeiro.
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. Em **meus domínios**, selecione o nome do domínio que você deseja modificar.
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. Na coluna **detalhes** , selecione **registros DNS**. 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela.
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Tipo**|**Host**|**Atender**|**TTL**|**Prio**|
    |:-----|:-----|:-----|:-----|:-----|
    |MX  <br/> |(Deixe este campo vazio.)  <br/> | *\<chave-do-domínio\>*  .mail.protection.outlook.com  <br/> **Observação:** Obtenha sua * \<chave\> de domínio* de sua conta da Microsoft.           [Como faço para encontrar isso?](../get-help-with-domains/information-for-dns-records.md)          |Use the default value (300).  <br/> |,0  <br/> Para saber mais sobre prioridade, confira [O que é prioridade MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> |
   
   ![Name-BP-configure-2-1](../../media/11ba2160-fc8e-4196-bb15-2b7c6d49c8fc.png)
  
5. Selecione **adicionar registro**.
    
    ![Name-BP-Configure-2-2](../../media/fd09f161-7cc4-4723-aec2-5fa801bd19e9.png)
  
6. Se houver outros registros MX, exclua cada um deles, usando o procedimento de duas etapas a seguir:
    
    Para cada registro MX, selecione **excluir** na coluna **ações** . 
    
    ![Name-BP-Configure-2-3](../../media/16734a98-31c4-4023-a2a5-10b7c95bc58e.png)
  
    Para confirmar cada exclusão, selecione **excluir** na coluna **ações** novamente. 
    
    ![Name-BP-Configure-2-4](../../media/409c21c5-51f4-4244-bb84-5d32084224b2.png)
  
    Repita esse procedimento de duas etapas até ter excluído todos os registros MX.
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a>Adicionar os registros CNAME necessários para a Microsoft
<a name="BKMK_add_CNAME"> </a>

1. Para iniciar, vá para a sua página de domínios em name.com usando [este link](https://www.name.com/account/domain). Você será solicitado a fazer o logon primeiro.
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. Em **meus domínios**, selecione o nome do domínio que você deseja modificar.
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. Na coluna **detalhes** , selecione **registros DNS**. 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. Adicionar o primeiro registro CNAME.
    
    Nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir.
    
    (Escolha o valor de **Tipo** na lista suspensa.) 
    
    |**Tipo**|**Host**|**Atender**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |CNAME  <br/> |descoberta automática  <br/> |autodiscover.outlook.com  <br/> |Use o valor padrão (300).  <br/> |
    |CNAME  <br/> |sip  <br/> |sipdir.online.lync.com  <br/> |Use o valor padrão (300).  <br/> |
    |CNAME  <br/> |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |Use o valor padrão (300).  <br/> |
    |CNAME  <br/> |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |Use o valor padrão (300).  <br/> |
    |CNAME  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |Use o valor padrão (300).  <br/> |
   
   ![Name-BP-configure-3-1](../../media/4e34caaf-b418-40ec-abfa-fe62175a87c2.png)
  
5. Selecione **adicionar registro** para adicionar o primeiro registro. 
    
    ![Name-BP-Configure-3-2](../../media/1053c2a7-07c3-4c1b-b54a-1c02881fb0ec.png)
  
6. Adicione o segundo registro CNAME.
    
    Use os valores da segunda linha da tabela acima e, em seguida, selecione **adicionar registro** para adicionar o segundo registro. 
    
    Adicione os registros restantes da mesma maneira, usando os valores da terceira, quarta, quinta e sexta linhas da tabela.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Não é possível ter mais de um registro TXT para SPF para um domínio. Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam. Se você já possui um registro SPF para seu domínio, não crie um novo para a Microsoft. Em vez disso, adicione os valores necessários da Microsoft ao registro atual para que você tenha um *único* registro SPF que inclua os dois conjuntos de valores. 
  
1. Para iniciar, vá para a sua página de domínios em name.com usando [este link](https://www.name.com/account/domain). Você será solicitado a fazer o logon primeiro.
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. Em **meus domínios**, selecione o nome do domínio que você deseja modificar.

    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. Na coluna **detalhes** , selecione **registros DNS**. 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela.
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Tipo**|**Host**|**Atender**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |TXT  <br/> |(Leave this field empty.)  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Observação:** é recomendável copiar e colar essa entrada, para que todo o espaçamento permaneça correto.           |Use the default value (300).  <br/> |
   
   ![Name-BP-configure-4-1](../../media/cbbfc071-840a-4ffa-a59e-0dfce03063cc.png)
  
5. Selecione **adicionar registro**.
    
    ![Name-BP-Configure-4-2](../../media/db1e0e09-2b95-4fc1-88bd-e86da536921f.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Adicionar os dois registros SRV necessários para a Microsoft
<a name="BKMK_add_SRV"> </a>

1. Para iniciar, vá para a sua página de domínios em name.com usando [este link](https://www.name.com/account/domain). Você será solicitado a fazer o logon primeiro.
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. Em **meus domínios**, selecione o nome do domínio que você deseja modificar.
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. Na coluna **detalhes** , selecione **registros DNS +**. 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. Adicione o primeiro registro SRV:
    
    Nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir.
    
    (Escolha o valor de **Tipo** na lista suspensa.) 
    
    |**Tipo**|**Serviço**|**Peso**|**TTL**|**Prio**|**Protocolo**|**Porta**|**Destino**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV|sip|1|Use o valor padrão (300).|100|tls|443|sipdir.online.lync.com <br> **Observação:** é recomendável copiar e colar essa entrada, para que todo o espaçamento permaneça correto.           |
    |SRV|sipfederationtls|1|Use o valor padrão (300).|100|tcp|5061|sipfed.online.lync.com <br>**Observação:** é recomendável copiar e colar essa entrada, para que todo o espaçamento permaneça correto.           |
   
   ![Name-BP-configure-5-1](../../media/d9a885fd-7300-45b6-ad4c-0b4bf1067560.png)
  
5. Selecione **adicionar registro**.

    ![Name-BP-Configure-5-2](../../media/a804d51d-8f57-4b0b-8bd6-a52eb1c87a97.png)
  
6. Adicione o segundo registro SRV:

Use os valores da próxima linha da tabela acima e, em seguida, selecione **adicionar registro** para adicionar o segundo registro.

>[!NOTE]
>Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).
