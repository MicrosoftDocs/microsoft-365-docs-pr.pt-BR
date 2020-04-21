---
title: Criar registros DNS no Register365 para Microsoft
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
ms.assetid: 004030b4-10ad-4026-96e7-011b6afc7e73
description: Saiba como verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços em Register365 para a Microsoft.
ms.openlocfilehash: 08db53df7510de76c6c5c33d2047cba4203324d8
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629258"
---
# <a name="create-dns-records-at-register365-for-microsoft"></a>Criar registros DNS no Register365 para Microsoft

 **Caso não encontre o conteúdo que está procurando, [verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**. 
  
Se você usa o Register365 como provedor de hospedagem DNS, realize os procedimentos deste artigo para verificar o domínio e configurar registros DNS para o Skype for Business Online, email e outros serviços. 
  
Esses são os principais registros a adicionar.  
  
- [Adicionar um registro TXT para verificação](#add-a-txt-record-for-verification)
    
- [Adicionar um registro MX para que o email do seu domínio seja fornecido para a Microsoft](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [Adicionar os seis registros CNAME necessários para o Microsoft](#add-the-six-cname-records-that-are-required-for-microsoft)
    
- [Adicionar registro TXT à SPF para ajudar a evitar spam de email](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [Adicionar os dois registros SRV necessários para o Microsoft](#add-the-two-srv-records-that-are-required-for-microsoft)
    
Depois que você adicionar esses registros à Microsoft, o domínio será configurado para funcionar com os serviços da Microsoft.
  
Para saber mais sobre o webhosting e o DNS para sites com a Microsoft, confira [usar um site público com a Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).
  
> [!NOTE]
>  Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Adicionar um registro TXT para verificação
<a name="BKMK_verify"> </a>

Antes de usar seu domínio com a Microsoft, precisamos garantir que você o tenha. Sua capacidade de fazer logon em sua conta no registrador de domínios e criar o registro DNS comprova para a Microsoft que você é o proprietário do domínio.
  
> [!NOTE]
> Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar. 
  
1. Para iniciar, vá até a sua página de domínios em Register365, usando [este link](https://admin.register365.com/dns/). Será solicitado que você faça logon primeiro.
    
    ![Página de entrada do Painel de Controle](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. Na página **Painel**, procure o nome do domínio que será atualizado e escolha **Configurações de DNS**, na lista suspensa. 
    
    Pode ser necessário rolar a tela para baixo.
    
    ![Selecionar configurações de DNS na lista](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    (Se você precisar adicionar uma linha, selecione **adicionar registros a/CNAME (+)**.)
    
    (You may have to scroll down.)
    
    |**Nome do host**|**Tipo**|**Resultado**|
    |:-----|:-----|:-----|
    |(Leave this field empty.)  <br/> |TXT  <br/> |MS = ms *XXXXXXXX*  <br/> **Observação**: esse é um exemplo. Use o seu **destino específico ou aponte para** o valor de endereço aqui, a partir da tabela.           [Como localizo isto?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Inserindo valores na página Adicionar/modificar zona DNS](../../media/22326005-de95-464d-8e33-08ea31a89b2d.png)
  
4. Selecione **Salvar**.
    
    (You may have to scroll down.)
    
    ![Selecione salvar](../../media/157cfb98-d5d0-48a3-8dd1-c4e759c2f8a8.png)
  
5. Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.
    
Agora que você adicionou o registro no site do seu registrador de domínio, você voltará para a Microsoft e solicitará o registro.
  
Quando a Microsoft encontrar o registro TXT correto, seu domínio será verificado.
  
1. No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.
    
2. Na página **Domínios**, clique no domínio que você está verificando. 
    
    
  
3. Na página **Configuração**, clique em **Iniciar configuração**.
    
    
  
4. Na página **Verificar domínio**, marque **Verificar**.
    
    
  
> [!NOTE]
>  Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Adicionar um registro MX para que o email do seu domínio seja fornecido para a Microsoft
<a name="BKMK_add_MX"> </a>

1. Para iniciar, vá até a sua página de domínios em Register365, usando [este link](https://admin.register365.com/dns/). Será solicitado que você faça logon primeiro.
    
    ![Página de entrada do Painel de Controle](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. Na página **Painel**, procure o nome do domínio que será atualizado e escolha **Configurações de DNS**, na lista suspensa. 
    
    Pode ser necessário rolar a tela para baixo.
    
    ![Selecionar configurações de DNS na lista](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. Na página **Adicionar/Modificar Zona DNS**, na seção **Registros MX**, digite ou copie e cole os valores nas caixas do novo registro, a partir da tabela a seguir. 
    
    (Pode ser necessário rolar para baixo.)
    
    |**Nome do host**|**Prioridade**|**Resultado**|
    |:-----|:-----|:-----|
    |(Deixe este campo vazio.)  <br/> |1  <br/> Para saber mais sobre prioridade, confira [O que é prioridade MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> | *\<chave-do-domínio\>*  .mail.protection.outlook.com  <br/> **Observação:** Obtenha sua * \<chave\> de domínio* de sua conta da Microsoft.  [Como localizo isto?](../get-help-with-domains/information-for-dns-records.md)     |
   
    ![Inserindo valores na página Adicionar/modificar zona DNS](../../media/2d3645a8-9cb8-435e-b895-5535b6b1fffd.png)
  
4. Selecione **Salvar**.
    
    (You may have to scroll down.)
    
    ![Selecione salvar](../../media/0e565fb0-a126-4a48-8ff7-2c2d79d4af32.png)
  
5. Se houver outros registros MX na seção **Registros MX**, selecione cada um deles e pressione a tecla **Delete** no teclado para excluí-los. 
    
    ![Deleting records in the Mail exchange records section](../../media/8cc37e4f-2e85-4242-af0e-78149434167f.png)
  
6. Selecione **Salvar**.
    
    (You may have to scroll down.)
    
    ![Selecione salvar](../../media/1fb69bb5-b5df-4060-adf1-eb26cfaa6c4f.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>Adicionar os seis registros CNAME necessários para o Microsoft
<a name="BKMK_add_CNAME"> </a>

1. Para iniciar, vá até a sua página de domínios em Register365, usando [este link](https://admin.register365.com/dns/). Será solicitado que você faça logon primeiro.
    
    ![Página de entrada do Painel de Controle](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. Na página **Painel**, procure o nome do domínio que será atualizado e escolha **Configurações de DNS**, na lista suspensa. 
    
    Pode ser necessário rolar a tela para baixo.
    
    ![Selecionar configurações de DNS na lista](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. Na página **Adicionar/Modificar Zona DNS**, na seção **Registros A, CNAME, AAAA, TXT e NS**, digite ou copie e cole os valores nas caixas dos novos registros, a partir da tabela a seguir. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    (Se você precisar adicionar uma linha, selecione **adicionar registros a/CNAME (+)**.)
    
    (Pode ser necessário rolar para baixo.)
    
    |****Nome do host****|****Tipo****|****Resultado****|
    |:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |CNAME  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
    ![Inserindo valores na página Adicionar/modificar zona DNS](../../media/3b79f0de-9cab-4c98-8fa8-c92b35241e8b.png)
  
4. Selecione **Salvar**.
    
    ![Selecione salvar](../../media/8ded6428-af97-4fd8-9104-477fa22a5586.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Não é possível ter mais de um registro TXT para SPF para um domínio. Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam. Se você já tiver um registro SPF para seu domínio, não crie um novo para a Microsoft. Em vez disso, adicione os valores necessários da Microsoft ao registro atual para que você tenha um *único* registro SPF que inclua os dois conjuntos de valores. 
  
1. Para iniciar, vá até a sua página de domínios em Register365, usando [este link](https://admin.register365.com/dns/). Será solicitado que você faça logon primeiro.
    
    ![Página de entrada do Painel de Controle](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. Na página **Painel**, procure o nome do domínio que será atualizado e escolha **Configurações de DNS**, na lista suspensa. 
    
    Pode ser necessário rolar a tela para baixo.
    
    ![Selecionar configurações de DNS na lista](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    (Se você precisar adicionar uma linha, selecione **adicionar registros a/CNAME (+)**.)
    
    (You may have to scroll down.)
    
    |**Nome do host**|**Tipo**|**Resultado**|
    |:-----|:-----|:-----|
    |(Leave this field empty.)  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/>**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.           |
   
    ![Inserindo valores na página Adicionar/modificar zona DNS](../../media/33976398-da8a-439b-8e3d-534503b20ee0.png)
  
4. Selecione **Salvar**.
    
    (You may have to scroll down.)
    
    ![Selecione salvar](../../media/1d8da122-4861-4ca3-bc9b-d01f18557d4c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Adicionar os dois registros SRV necessários para o Microsoft
<a name="BKMK_add_SRV"> </a>

1. Para iniciar, vá até a sua página de domínios em Register365, usando [este link](https://admin.register365.com/dns/). Será solicitado que você faça logon primeiro.
    
    ![Página de entrada do Painel de Controle](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. Na página **Painel**, procure o nome do domínio que será atualizado e escolha **Configurações de DNS**, na lista suspensa. 
    
    Pode ser necessário rolar a tela para baixo.
    
    ![Selecionar configurações de DNS na lista](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. Na página **Adicionar/Modificar Zona DNS**, na seção **Registros de serviço**, digite ou copie e cole os valores nas caixas dos novos registros, a partir da tabela a seguir. 
    
    (Pode ser necessário rolar para baixo.)
    
    |**Nome**|**Prioridade**|**Espessura**|**Porta**|**Resultado**|
    |:-----|:-----|:-----|:-----|:-----|
    |_sip. _tls  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
    |_sipfederationtls. _tcp  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com  <br/> |
   
    ![Inserindo valores na seção registros de serviço](../../media/56bb1813-90e2-40c8-98bf-750e2dc3f8b6.png)
  
4. Selecione **Salvar**.
    
    (You may have to scroll down.)
    
    ![Selecione salvar](../../media/3b80757c-01e1-492d-b2ce-f721d71f7235.png)
  
> [!NOTE]
>  Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
