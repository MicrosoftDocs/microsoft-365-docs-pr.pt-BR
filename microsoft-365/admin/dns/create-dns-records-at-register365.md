---
title: Criar registros DNS no site Register365 para a Microsoft
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
ms.assetid: 004030b4-10ad-4026-96e7-011b6afc7e73
description: Aprenda a verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços no Register365 para Microsoft.
ms.openlocfilehash: 6cefdeff3da1256911d80066b55b00f5bef24055
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/11/2020
ms.locfileid: "49656910"
---
# <a name="create-dns-records-at-register365-for-microsoft"></a>Criar registros DNS no site Register365 para a Microsoft

 **Caso não encontre o conteúdo que está procurando, [verifique as perguntas frequentes sobre domínios](../setup/domains-faq.yml)**. 
  
Se você usa o Register365 como provedor de hospedagem DNS, realize os procedimentos deste artigo para verificar o domínio e configurar registros DNS para o Skype for Business Online, email e outros serviços. 
  
Esses são os principais registros a adicionar.  
  
- [Adicionar um registro TXT para verificação](#add-a-txt-record-for-verification)
    
- [Adicione um registro MX para que o email do domínio vá para a Microsoft.](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [Adicionar os seis registros CNAME necessários para a Microsoft](#add-the-six-cname-records-that-are-required-for-microsoft)
    
- [Adicionar registro TXT à SPF para ajudar a evitar spam de email](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [Adicionar os dois registros SRV necessários para a Microsoft](#add-the-two-srv-records-that-are-required-for-microsoft)
    
Depois que você adicionar esses registros à Microsoft, seu domínio será definido para funcionar com os serviços Microsoft.
  
> [!NOTE]
>  Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Adicionar um registro TXT para verificação
<a name="BKMK_verify"> </a>

Antes de usar o seu domínio com a Microsoft, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro de DNS prova à Microsoft que você é o proprietário do domínio.
  
> [!NOTE]
> Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar. 
  
1. Para iniciar, vá até a sua página de domínios em Register365, usando [este link](https://admin.register365.com/dns/). Será solicitado que você faça logon primeiro.
    
    ![Página de entrada do Painel de Controle](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. Na página **Painel**, procure o nome do domínio que será atualizado e escolha **Configurações de DNS**, na lista suspensa. 
    
    Pode ser necessário rolar a tela para baixo.
    
    ![Selecionando configurações dns na lista](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Selecione o valor **Tipo** na lista suspensa.) 
    
    (Se você precisar adicionar uma linha, selecione **ADICIONAR REGISTROS A/CNAME (+)**.)
    
    (Pode ser necessário rolar para baixo.)
    
    |**Nome do host**|**Tipo**|**Resultado**|
    |:-----|:-----|:-----|
    |(Leave this field empty.)  <br/> |TXT  <br/> |MS = ms *XXXXXXXX*  <br/> **Observação**: esse é um exemplo. Use aqui seu valor específico de **Destino ou Pontos de Endereçamento**, retirado da tabela.           [Como localizo isto?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Inserindo valores na página Adicionar/Modificar Zona DNS](../../media/22326005-de95-464d-8e33-08ea31a89b2d.png)
  
4. Selecione **Salvar**.
    
    (Pode ser necessário rolar para baixo.)
    
    ![Selecione Salvar.](../../media/157cfb98-d5d0-48a3-8dd1-c4e759c2f8a8.png)
  
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

1. Para iniciar, vá até a sua página de domínios em Register365, usando [este link](https://admin.register365.com/dns/). Será solicitado que você faça logon primeiro.
    
    ![Página de entrada do Painel de Controle](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. Na página **Painel**, procure o nome do domínio que será atualizado e escolha **Configurações de DNS**, na lista suspensa. 
    
    Pode ser necessário rolar a tela para baixo.
    
    ![Selecionando configurações dns na lista](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. Na página **Adicionar/Modificar Zona DNS**, na seção **Registros MX**, digite ou copie e cole os valores nas caixas do novo registro, a partir da tabela a seguir. 
    
    (Pode ser necessário rolar para baixo.)
    
    |**Nome do host**|**Prioridade**|**Resultado**|
    |:-----|:-----|:-----|
    |(Deixe este campo vazio.)  <br/> |1   <br/> Para saber mais sobre prioridade, confira [O que é prioridade MX?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) <br/> | *\<domain-key\>*  .mail.protection.outlook.com  <br/> **Observação:** Obter o  *\<domain-key\>*  seu da sua conta da Microsoft.  [Como localizo isto?](../get-help-with-domains/information-for-dns-records.md)     |
   
    ![Inserindo valores na página Adicionar/Modificar Zona DNS](../../media/2d3645a8-9cb8-435e-b895-5535b6b1fffd.png)
  
4. Selecione **Salvar**.
    
    (Pode ser necessário rolar para baixo.)
    
    ![Selecione Salvar.](../../media/0e565fb0-a126-4a48-8ff7-2c2d79d4af32.png)
  
5. Se houver outros registros MX na seção **Registros MX**, selecione cada um deles e pressione a tecla **Delete** no teclado para excluí-los. 
    
    ![Deleting records in the Mail exchange records section](../../media/8cc37e4f-2e85-4242-af0e-78149434167f.png)
  
6. Selecione **Salvar**.
    
    (Pode ser necessário rolar para baixo.)
    
    ![Selecione Salvar.](../../media/1fb69bb5-b5df-4060-adf1-eb26cfaa6c4f.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>Adicionar os seis registros CNAME necessários para a Microsoft
<a name="BKMK_add_CNAME"> </a>

1. Para iniciar, vá até a sua página de domínios em Register365, usando [este link](https://admin.register365.com/dns/). Será solicitado que você faça logon primeiro.
    
    ![Página de entrada do Painel de Controle](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. Na página **Painel**, procure o nome do domínio que será atualizado e escolha **Configurações de DNS**, na lista suspensa. 
    
    Pode ser necessário rolar a tela para baixo.
    
    ![Selecionando configurações dns na lista](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. Na página **Adicionar/Modificar Zona DNS**, na seção **Registros A, CNAME, AAAA, TXT e NS**, digite ou copie e cole os valores nas caixas dos novos registros, a partir da tabela a seguir. 
    
    (Selecione o valor **Tipo** na lista suspensa.) 
    
    (Se você precisar adicionar uma linha, selecione **ADICIONAR REGISTROS A/CNAME (+)**.)
    
    (Pode ser necessário rolar para baixo.)
    
    |****Nome do host****|****Tipo****|****Resultado****|
    |:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |CNAME  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
    ![Inserindo valores na página Adicionar/Modificar Zona DNS](../../media/3b79f0de-9cab-4c98-8fa8-c92b35241e8b.png)
  
4. Selecione **Salvar**.
    
    ![Selecione Salvar.](../../media/8ded6428-af97-4fd8-9104-477fa22a5586.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Não é possível ter mais de um registro TXT para SPF para um domínio. Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam. Se você já possui um registro SPF para seu domínio, não crie um novo para a Microsoft. Em vez disso, adicione os valores necessários da Microsoft ao registro atual para que você tenha um único registro  *SPF*  que inclua ambos os conjuntos de valores. 
  
1. Para iniciar, vá até a sua página de domínios em Register365, usando [este link](https://admin.register365.com/dns/). Será solicitado que você faça logon primeiro.
    
    ![Página de entrada do Painel de Controle](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. Na página **Painel**, procure o nome do domínio que será atualizado e escolha **Configurações de DNS**, na lista suspensa. 
    
    Pode ser necessário rolar a tela para baixo.
    
    ![Selecionando configurações dns na lista](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Selecione o valor **Tipo** na lista suspensa.) 
    
    (Se você precisar adicionar uma linha, selecione **ADICIONAR REGISTROS A/CNAME (+)**.)
    
    (Pode ser necessário rolar para baixo.)
    
    |**Nome do host**|**Tipo**|**Resultado**|
    |:-----|:-----|:-----|
    |(Leave this field empty.)  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/>**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.           |
   
    ![Inserindo valores na página Adicionar/Modificar Zona DNS](../../media/33976398-da8a-439b-8e3d-534503b20ee0.png)
  
4. Selecione **Salvar**.
    
    (Pode ser necessário rolar para baixo.)
    
    ![Selecione Salvar.](../../media/1d8da122-4861-4ca3-bc9b-d01f18557d4c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Adicionar os dois registros SRV necessários para a Microsoft
<a name="BKMK_add_SRV"> </a>

1. Para iniciar, vá até a sua página de domínios em Register365, usando [este link](https://admin.register365.com/dns/). Será solicitado que você faça logon primeiro.
    
    ![Página de entrada do Painel de Controle](../../media/d7ec9791-d03f-45dd-b080-8aaae5d19ea6.png)
  
2. Na página **Painel**, procure o nome do domínio que será atualizado e escolha **Configurações de DNS**, na lista suspensa. 
    
    Pode ser necessário rolar a tela para baixo.
    
    ![Selecionando configurações dns na lista](../../media/57944802-3f6b-49bb-971a-b1d20936cba3.png)
  
3. Na página **Adicionar/Modificar Zona DNS**, na seção **Registros de serviço**, digite ou copie e cole os valores nas caixas dos novos registros, a partir da tabela a seguir. 
    
    (Pode ser necessário rolar para baixo.)
    
    |**Nome**|**Prioridade**|**Espessura**|**Porta**|**Resultado**|
    |:-----|:-----|:-----|:-----|:-----|
    |_sip._tls  <br/> |100  <br/> |1   <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
    |_sipfederationtls._tcp  <br/> |100  <br/> |1   <br/> |5061  <br/> |sipfed.online.lync.com  <br/> |
   
    ![Inserindo valores na seção Registros de serviço](../../media/56bb1813-90e2-40c8-98bf-750e2dc3f8b6.png)
  
4. Selecione **Salvar**.
    
    (Pode ser necessário rolar para baixo.)
    
    ![Selecione Salvar.](../../media/3b80757c-01e1-492d-b2ce-f721d71f7235.png)
  
> [!NOTE]
>  Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
