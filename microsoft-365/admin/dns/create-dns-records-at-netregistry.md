---
title: Criar registros DNS no Netregistry para Microsoft
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
- BEA160
ms.assetid: 48e09394-2287-4b3c-9853-21eadf61277e
description: Saiba como verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços no Netregistry para a Microsoft.
ms.openlocfilehash: ed3e3bae232dcbb3c8e4eea3d1a3bc4dd0a88799
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/29/2020
ms.locfileid: "43939150"
---
# <a name="create-dns-records-at-netregistry-for-microsoft"></a>Criar registros DNS no Netregistry para Microsoft

Caso não encontre o conteúdo que está procurando, [verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md). 
  
Se o Netregistry for o seu provedor de hospedagem DNS, siga as etapas deste artigo para verificar seu domínio e configurar registros DNS para email, Skype for Business Online e assim por diante.
  
Estes são os registros principais a adicionar.
  
- [Adicionar um registro TXT para verificação](#add-a-txt-record-for-verification)
    
- [Adicione um registro MX para que o email do domínio vá para a Microsoft.](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)

- [Adicionar os registros CNAME necessários para a Microsoft](#add-the-cname-records-that-are-required-for-microsoft)
    
- [Adicionar registro TXT à SPF para ajudar a evitar spam de email](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [Adicionar os dois registros SRV necessários para a Microsoft](#add-the-two-srv-records-that-are-required-for-microsoft)
    
Depois que você adicionar esses registros ao Netregistry, o domínio será configurado para funcionar com os serviços da Microsoft.
  
  
> [!NOTE]
> Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Adicionar um registro TXT para verificação
<a name="bkmk_txt"> </a>

Antes de usar o seu domínio com a Microsoft, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro de DNS prova à Microsoft que você é o proprietário do domínio.
  
> [!NOTE]
> Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar. 
  
1. Para começar, vá até a sua página de domínios no Netregistry usando [este link](https://theconsole.netregistry.com.au/). You'll be prompted to log in.
    
    ![Netregistry_login](../../media/ed3c785f-01c3-49e7-affd-c04637c0ffe9.png)
  
2. Ao lado do domínio que você deseja gerenciar, selecione **gerenciar**.
    
    ![Netregistry_Manage](../../media/64ad542a-5ec4-4148-96f8-d6e163449352.png)
  
3. Selecione **Gerenciador de zona**.
    
    ![Netregistry_selectZoneManager](../../media/e18c32f9-c1e7-4aa2-9aa6-8dc9c5ea44af.png)
  
4. Em **Adicionar um registro de zona**, escolha **registro txt** na lista e, em seguida, selecione **criar novo registro**.
    
    ![Netregistry_TXT_select](../../media/eb1761e6-9deb-4631-8deb-bc5d09926722.png)
  
    > [!NOTE]
    > Você deve usar aspas antes e depois da entrada na caixa TXT. 
  
    No formulário **novo registro txt** , digite ou copie e cole os valores da tabela a seguir. 
    
    |**Nome**|**TTL (SEG)**|**TXT (aponta para endereço ou valor)**|
    |:-----|:-----|:-----|
    |(deixar em branco)  <br/> |3600 (segundos)  <br/> |"MS = msXXXXXXXX"  <br/> **Observação**: esse é um exemplo. Use aqui seu valor específico de **Destino ou Pontos de Endereçamento**, retirado da tabela. [Como localizo isto?](../get-help-with-domains/information-for-dns-records.md)  |
       
    ![Netregistry_verificationTXTvalues](../../media/cfe8b05a-fa8b-4dba-9554-7a3466e6c012.png)
  
6. Selecione **adicionar registro**.
    
Agora que você adicionou o registro no site do seu registrador de domínios, retorne à Microsoft e solicite o registro.
  
Quando a Microsoft encontrar o registro TXT correto, seu domínio estará verificado.
  
1. No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.
    
2. Na página **Domínios**, clique no domínio que você está verificando. 
    
    
  
3. Na página **Configuração**, clique em **Iniciar configuração**.
    
    
  
4. Na página **Verificar domínio**, marque **Verificar**.
    
    
  
> [!NOTE]
>  Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Adicione um registro MX para que o email do domínio vá para a Microsoft.
<a name="bkmk_mx"> </a>

1. Para começar, vá até a sua página de domínios no Netregistry usando [este link](https://theconsole.netregistry.com.au/). You'll be prompted to log in.
    
    ![Netregistry_login](../../media/80277b0e-547e-4635-aa6a-5d8ebe3fba85.png)
  
2. Ao lado do domínio que você deseja gerenciar, selecione **gerenciar**.
    
    ![Netregistry_Manage](../../media/96e2c6e4-21fd-4405-a4fe-b1188400b985.png)
  
3. Selecione **Gerenciador de zona**.
    
    ![Netregistry_selectZoneManager](../../media/914021f6-dff3-4640-84d6-b83cf8f61cf1.png)
  
4. Em **registros de zona atuais**, remova os registros MX padrão selecionando **remover** ao lado de cada registro MX na lista. 
    
    ![Netregistry_MX_remove](../../media/494670a9-8b8d-46e5-8136-05e82212a115.png)
  
5. Em **Adicionar um registro de zona**, escolha **registro MX** na lista e, em seguida, selecione **criar novo registro**.
    
    ![Netregistry_MX_select](../../media/29b60eb9-6c40-490f-9669-e65b65962f37.png)
  
6. No formulário **novo registro MX** , digite ou copie e cole os valores da tabela a seguir. 
    
    |**Nome**|**TTL (SEG)**|**Exchange (aponta para o endereço ou valor)**|**O host está totalmente qualificado?**|**Preferência (prioridade)**|
    |:-----|:-----|:-----|:-----|:-----|
    |(deixar em branco)  <br/> |3600 (segundos)  <br/> | *\<chave-do-domínio\>*  .mail.protection.outlook.com  <br/> **Observação:** Obtenha sua * \<chave\> de domínio* de sua conta da Microsoft.  [Como localizo isto?](../get-help-with-domains/information-for-dns-records.md)      |(marque a caixa de seleção)  <br/> |10   <br/> For more information about priority, see What is MX priority?  <br/> |
       
    ![Netregistry_MX_values](../../media/518b3da6-4055-4e2d-b5ce-44a0fee25419.png)
  
7. Selecione **adicionar registro**.
    
    ![Netregistry_MX_values_AddRecord](../../media/8194cb38-afa0-48ac-831c-fd34b6ad652e.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a>Adicionar os registros CNAME necessários para a Microsoft
<a name="bkmk_cname"> </a>

1. Para começar, vá até a sua página de domínios no Netregistry usando [este link](https://theconsole.netregistry.com.au/). You'll be prompted to log in.
    
    ![Netregistry_login](../../media/cbf83dce-86d2-4008-9400-56def4b6fcd7.png)
  
2. Ao lado do domínio que você deseja gerenciar, selecione **gerenciar**.
    
    ![Netregistry_Manage](../../media/7bee4b0f-2c1d-43ca-b1bb-9b889ca0c5e4.png)
  
3. Selecione **Gerenciador de zona**.
    
    ![Netregistry_selectZoneManager](../../media/58384add-0a9d-472b-a5d0-51ec8155fd41.png)
  
4. Em **Adicionar um registro de zona**, escolha **registro CNAME** na lista e, em seguida, selecione **criar novo registro**.
    
    ![Netregistry_CNAME_CreateNewRecord](../../media/7b4f133f-45da-48da-93c0-62f57c786165.png)
  
5. Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela.
    
    |**Nome**|**Tipo**|**TTL**|**HOST (aponta para ou valor de endereço)**|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |3600 (segundos)  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |CNAME  <br/> |3600 (segundos)  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |3600 (segundos)  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |3600 (segundos)  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |3600 (segundos)  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
       
    ![Netregistry_CNAME_values](../../media/93c479f0-3ce2-491a-9113-6dde1cd7131b.png)
      
6. Selecione **adicionar registro**.
    
    ![Netregistry_CNAME_values_AddRecord](../../media/046c8c64-ea71-4530-9fc6-69f0c70993b6.png)
  
7. Repita as etapas anteriores para criar os outros cinco registros CNAME.
    
    Para cada registro, digite ou copie e cole os valores da próxima linha da tabela acima nas caixas desse registro.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Adicionar registro TXT à SPF para ajudar a evitar spam de email
<a name="bkmk_spf"> </a>

> [!IMPORTANT]
> Não é possível ter mais de um registro TXT para SPF para um domínio. Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam. Se você já possui um registro SPF para seu domínio, não crie um novo para a Microsoft. Em vez disso, adicione os valores necessários da Microsoft ao registro atual para que você tenha um *único* registro SPF que inclua os dois conjuntos de valores.
  
1. Para começar, vá até a sua página de domínios no Netregistry usando [este link](https://theconsole.netregistry.com.au/). You'll be prompted to log in.
    
    ![Netregistry_login](../../media/a841f11f-1c0f-4926-acea-a2b8bb083984.png)
  
2. Ao lado do domínio que você deseja gerenciar, selecione **gerenciar**.
    
    ![Netregistry_Manage](../../media/4245bbbb-4e2d-49e7-a89c-679949aa3d18.png)
  
3. Selecione **Gerenciador de zona**.
    
    ![Netregistry_selectZoneManager](../../media/372e5918-b6dc-4268-8f9a-0aa71d65deef.png)
  
4. Em **Adicionar um registro de zona**, escolha **registro txt** na lista e, em seguida, selecione **criar novo registro**.
    
    ![Netregistry_TXT_select](../../media/a2930d03-853a-4f1e-9205-d00f25bed35f.png)
  
5. Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela. 
    
    > [!NOTE]
    > Você deve usar aspas antes e depois da entrada na caixa TXT. 
  
    |**Nome**|**Tipo**|**TTL**|**Dados TXT (destino)**|
    |:-----|:-----|:-----|:-----|
    |(deixar em branco)  <br/> |TXT  <br/> |3600 (segundos)  <br/> |"v = spf1 inclui include. Protection. Outlook. com-All"  <br/> **Observação:** é recomendável copiar e colar essa entrada, para que todo o espaçamento permaneça correto.           |
   
    ![Netregistry_SPF-TXTvalues](../../media/a369345a-d774-48bc-8160-b628ab8247f9.png)
  
6. Selecione **adicionar registro**.
    
    ![Netregistry_SPF-TXTvalues_AddRecord](../../media/063bfbaf-940a-489f-970f-29c026b4b312.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Adicionar os dois registros SRV necessários para a Microsoft
<a name="bkmk_srv"> </a>

1. Para começar, vá até a sua página de domínios no Netregistry usando [este link](https://theconsole.netregistry.com.au/). You'll be prompted to log in.
    
    ![Netregistry_login](../../media/accf6584-e5f4-4d68-a641-0f8847f8370f.png)
  
2. Ao lado do domínio que você deseja gerenciar, selecione **gerenciar**.
    
    ![Netregistry_Manage](../../media/e0ddc79e-0123-4e24-8380-9645bdb41aac.png)
  
3. Selecione **Gerenciador de zona**.
    
    ![Netregistry_selectZoneManager](../../media/f122888b-3cc5-40ec-adac-0ede04799d9a.png)
  
4. Em **Adicionar um registro de zona**, escolha **registro SRV** na lista e, em seguida, selecione **criar novo registro**.
    
    ![Netregistry_SRV_select](../../media/e5dab850-acd1-48b8-8b4a-e3b9777cf508.png)
  
5. Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela.
    
    > [!NOTE]
    > O campo nome é uma combinação do serviço (por exemplo, _sip) e o protocolo (por exemplo, _tls). 
  
    |**Tipo**|**Nome**|**TTL (SEG)**|**Prioridade**|**Espessura**|**Porta**|**Destino**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV (serviço)  <br/> |_sip. _tls  <br/> |3600 (segundos)  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
    |SRV (serviço)  <br/> |_sipfederationtls. _tcp  <br/> |3600 (segundos)  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com  <br/> |
       
    ![Netregistry_SRV_values](../../media/49292846-1598-4b8c-9940-db6e10675753.png)
  
6. Selecione **adicionar registro**.
    
    ![Netregistry_SRV_values_AddRecord](../../media/abc82061-939f-4757-87e4-0e8f9e43ebcb.png)
  
7. Repita as etapas anteriores para criar o outro registro SRV.
    
    Digite ou copie e cole os valores da segunda linha da tabela acima nas caixas do segundo registro.
    
> [!NOTE]
> Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  

