---
title: Criar registros DNS no Bluehost para Microsoft
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
ms.assetid: 657934ff-d9d2-4563-9ccf-ef4832a03a99
description: Saiba como verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços em Bluehost para a Microsoft.
ms.openlocfilehash: 72a9dc86436c404f874e5c2a4a321ef4d41b87f1
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/29/2020
ms.locfileid: "43939338"
---
# <a name="create-dns-records-at-bluehost-for-microsoft"></a>Criar registros DNS no Bluehost para Microsoft

 **Caso não encontre o conteúdo que está procurando, [verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**. 
  
Se você usa a Bluehost como provedor de hospedagem DNS, siga as etapas deste artigo para verificar o domínio e configurar registros DNS para o Skype for Business Online, email e outros serviços.
  
Depois que você adicionar esses registros no Bluehost, o domínio será configurado para funcionar com os serviços da Microsoft.

> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Adicionar um registro TXT para verificação
<a name="BKMK_verify"> </a>

Antes de usar o seu domínio com a Microsoft, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro de DNS prova à Microsoft que você é o proprietário do domínio.
  
> [!NOTE]
> Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar. 
  
1. Para começar, vá para sua página de domínios no Bluehost usando [este link](https://my.bluehost.com/cgi/dm). Será solicitado que você faça logon primeiro.
    
2. Na página **Domínios**, na área **domínio**, localize a linha do domínio que está sendo alterado e marque a caixa de seleção desse domínio. 
    
    (Pode ser necessário rolar para baixo.)
    
3. Na área ***domain_name*** , na linha **Editor de zona DNS** , selecione **gerenciar registros DNS**.
    
4. On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |**Host Record** <br/> |**TTL** <br/> |**Tipo** <br/> |**TXT Value** <br/> |
    |@  <br/> |14400  <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **Observação**: esse é um exemplo. Use aqui seu valor específico de **Destino ou Pontos de Endereçamento**, retirado da tabela. [Como localizo isto?](../get-help-with-domains/information-for-dns-records.md)          |
   
5. Selecione **adicionar registro**.
    
6. Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.
    
Agora que você adicionou o registro no site do seu registrador de domínio, você voltará para a Microsoft e solicitará uma pesquisa para o registro.
  
Quando a Microsoft encontrar o registro TXT correto, seu domínio estará verificado.
  
1. No centro do administrador da Microsoft, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.

    
2. Na página **Domínios**, clique no domínio que você está verificando. 
    
3. Na página **Configuração**, clique em **Iniciar configuração**.
    
4. Na página **Verificar domínio**, clique em **Verificar**.
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Adicione um registro MX para que o email do domínio vá para a Microsoft.
<a name="BKMK_add_MX"> </a>

1. Para começar, vá para sua página de domínios no Bluehost usando [este link](https://my.bluehost.com/cgi/dm). Será solicitado que você faça logon primeiro.
    
2. Na página **Domínios**, na área **domínio**, localize a linha do domínio que está sendo alterado e marque a caixa de seleção desse domínio. 
    
    (Pode ser necessário rolar para baixo.)
    
3. Na área ***domain_name*** , na linha **Editor de zona DNS** , selecione **gerenciar registros DNS**.
    
4. On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Host Record**|**TTL**|**Tipo**|**Aponta para**|**Prioridade**|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |14400  <br/> |MX  <br/> | *\<chave-do-domínio\>*  .mail.protection.outlook.com  <br/>**Observação:** Obtenha a sua \<*chave-de-domínio*\> através da sua conta Microsoft. [Como faço para encontrar isso?](../get-help-with-domains/information-for-dns-records.md)          |,0  <br/> Para saber mais sobre prioridade, confira [O que é prioridade MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> |
   
   ![Escolha tipo na lista suspensa](../../media/70791420-d83c-4a5d-a46c-5cc3bc67f565.png)
  
5. Selecione **adicionar registro**.
    
    ![Selecionar Adicionar registro](../../media/c7ef9733-1665-4dbf-accc-caadf1574abc.png)
  
6. Se existirem outros registros MX na seção **MX (Mail Exchanger)**, exclua cada um deles. 
    
    Para um dos outros registros MX, selecione **excluir.**
    
    ![Selecione Excluir para cada registro MX adicional](../../media/6be17f54-3f33-47af-a9db-4689141530c2.png)
  
7. Na caixa de diálogo de confirmação, selecione **OK**.
    
    ![Selecione OK](../../media/a50df7a3-2906-4cc0-87d4-1231ab234230.png)
  
8. Use o mesmo processo para excluir todos os outros registros MX que já foram listados.
    
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>Adicionar os seis registros CNAME necessários para o Microsoft
<a name="BKMK_add_CNAME"> </a>

1. Para começar, vá para sua página de domínios no Bluehost usando [este link](https://my.bluehost.com/cgi/dm). Será solicitado que você faça logon primeiro.
    
2. Na página **Domínios**, na área **domínio**, localize a linha do domínio que está sendo alterado e marque a caixa de seleção desse domínio. 
    
    (Pode ser necessário rolar para baixo.)
    
3. Na área ***domain_name*** , na linha **Editor de zona DNS** , selecione **gerenciar registros DNS**.
    
4. Na seção registros **a (host)** , localize a linha do registro de **descoberta automática** e, em seguida, selecione **excluir** para essa linha. 
    
    > [!IMPORTANT]
    > Você deve excluir o registro de **descoberta automática** existente *antes* de adicionar o registro de **descoberta automática** necessário para a Microsoft. Bluehost does not allow you to maintain two **autodiscover** records simultaneously. 
  
    ![Selecione Excluir](../../media/416a447e-3710-4ae7-8bf1-459381af4f6e.png)
  
5. Selecione **OK**.
    
    ![Selecione OK](../../media/0c8f409d-c39f-4ed2-9c95-9af3e61c2411.png)
  
6. Crie o primeiro dos seis registros CNAME.
    
    Na página **Editor de Zona DNS**, na área **Adicionar Registro DNS**, nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Host Record**|**TTL**|**Tipo**|**Aponta para**|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |14400  <br/> |CNAME  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |14400  <br/> |CNAME  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |14400  <br/> |CNAME  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |14400  <br/> |CNAME  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |14400  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
    ![Criar o primeiro registro CNAME](../../media/4f12e9b1-9dec-4bc2-aa15-8bffa71fe131.png)
  
7. Selecione **adicionar registro**.
    
    ![Selecionar Adicionar registro](../../media/c2782250-a9a6-4aee-bb15-f57cb0008587.png)
  
8. Adicione cada um dos outros cinco registros CNAME.
    
    Ainda na seção **adicionar registro DNS** , crie um registro usando os valores da próxima linha na tabela e, em seguida, selecione **adicionar registro** para concluir esse registro. 
    
    Repita esse processo até ter criado todos os seis registros CNAME.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Adicionar registro TXT à SPF para ajudar a evitar spam de email
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Não é possível ter mais de um registro TXT para SPF para um domínio. Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam. Se você já possui um registro SPF para seu domínio, não crie um novo para a Microsoft. Em vez disso, adicione os valores necessários da Microsoft ao registro atual para que você tenha um *único* registro SPF que inclua os dois conjuntos de valores. Precisa de exemplos? Confira os [Registros do Sistema de Nomes de Domínios externos para a Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0). Para validar o registro SPF, você pode usar uma destas[ferramentas de validação de SPF](../setup/domains-faq.md). 
  
1. Para começar, vá para sua página de domínios no Bluehost usando [este link](https://my.bluehost.com/cgi/dm). Será solicitado que você faça logon primeiro.
    
2. Na página **Domínios**, na área **domínio**, localize a linha do domínio que está sendo alterado e marque a caixa de seleção desse domínio. 
    
    (Pode ser necessário rolar para baixo.)
    
3. Na área ***domain_name*** , na linha **Editor de zona DNS** , selecione **gerenciar registros DNS**.
    
4. On the **DNS Zone Editor** page, in the **Add DNS Record** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
        
    |**Host Record**|**TTL**|**Tipo**|**TXT Value**|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |14400  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/>**Observação:** é recomendável copiar e colar essa entrada, para que todo o espaçamento permaneça correto.           |
   
    ![Copiar o valor TXT](../../media/b2dabd7a-ee3d-4209-aa1e-0233eb8cf3b9.png)
  
5. Selecione **adicionar registro**.
    
    ![Selecionar Adicionar registro](../../media/c050e9a2-2274-4640-8f0f-6752d382df5d.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Adicionar os dois registros SRV necessários para a Microsoft
<a name="BKMK_add_SRV"> </a>

1. Para começar, vá para sua página de domínios no Bluehost usando [este link](https://my.bluehost.com/cgi/dm). Será solicitado que você faça logon primeiro.
    
2. Na página **Domínios**, na área **domínio**, localize a linha do domínio que está sendo alterado e marque a caixa de seleção desse domínio. 
    
    (Pode ser necessário rolar para baixo.)
    
3. Na área ***domain_name*** , na linha **Editor de zona DNS** , selecione **gerenciar registros DNS**.
    
4. Crie o primeiro dos dois registros SRV.
    
    Na página **Editor de Zona DNS**, na área **Adicionar Registro DNS**, nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Serviço**|**Protocolo**|**Host**|**TTL**|**Tipo**|**Prioridade**|**Espessura**|**Porta**|**Aponta para**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip  <br/> |_tls  <br/> |@  <br/> |14400  <br/> |SRV  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
    |_sipfederationtls  <br/> |_tcp  <br/> |@  <br/> |14400  <br/> |SRV  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com  <br/> |
   
    ![Copiar o valor do novo registro](../../media/e2911bca-c00b-4b8a-837f-f1d438c474c4.png)
  
5. Selecione **adicionar registro**.
    
    ![Selecionar Adicionar registro](../../media/0fd6a587-03fd-4bce-8321-b14e6ad21f5c.png)
  
6. Adicione o outro registro SRV.
    
    Ainda na seção **adicionar registro DNS** , crie um registro usando os valores da outra linha na tabela e, em seguida, selecione **adicionar registro** para concluir esse registro. 
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  

