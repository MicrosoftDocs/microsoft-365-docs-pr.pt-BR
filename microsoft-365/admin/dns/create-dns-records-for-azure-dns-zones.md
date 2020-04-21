---
title: Criar registros DNS para zonas DNS do Azure
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
ms.assetid: fbcef2d7-ebaf-40d0-ba1f-cdaeff9f50ef
description: Saiba como verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços nas zonas de DNS do Azure para a Microsoft.
ms.openlocfilehash: 7104fb18a6581b7ebc853f938b85171ae1886cfd
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629138"
---
# <a name="create-dns-records-for-azure-dns-zones"></a>Criar registros DNS para zonas DNS do Azure

 Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**. 
  
Se o Azure for o seu provedor de hospedagem DNS, siga as etapas deste artigo para verificar seu domínio e configurar registros DNS para email, Skype for Business Online e assim por diante.
  
Esses são os principais registros a adicionar. 
  
- [Alterar os registros de nameserver (NS) de seu domínio](#change-your-domains-nameserver-ns-records)
    
- [Adicionar um registro TXT para verificação](#add-a-txt-record-for-verification)

- [Adicionar um registro MX para que o email do seu domínio seja fornecido para a Microsoft](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [Adicionar os quatro registros CNAME necessários para o Microsoft](#add-the-four-cname-records-that-are-required-for-microsoft)
    
- [Adicionar registro TXT à SPF para ajudar a evitar spam de email](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [Adicionar os dois registros SRV necessários para o Microsoft](#add-the-two-srv-records-that-are-required-for-microsoft)
    
Depois que você adicionar esses registros no Azure, o domínio será configurado para funcionar com os serviços da Microsoft.
  
> [!NOTE]
> Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="change-your-domains-nameserver-ns-records"></a>Alterar os registros de nameserver (NS) de seu domínio
<a name="BKMK_NS"> </a>

> [!IMPORTANT]
> Você deve executar este procedimento no registrador de domínios onde você comprou e registrou seu domínio. 
  
Ao se inscrever no Azure, você criou um grupo de recursos dentro de uma zona DNS e, em seguida, atribuiu o nome de domínio a esse grupo de recursos. Esse nome de domínio é registrado em um registrador de domínio externo; O Azure não oferece serviços de registro de domínio.
  
Para verificar e criar registros DNS para o seu domínio na Microsoft, primeiro você precisa alterar os nameservers no seu registrador de domínio para que eles usem os nameservers do Azure atribuídos ao seu grupo de recursos.
  
Para mudar os servidores de nomes do seu domínio por conta própria no site do registrador de domínios, siga essas etapas.
  
1. Localize a área no site do registrador de domínios na qual você pode editar os servidores de nomes do seu domínio.
    
2. Crie dois registros de nameserver usando os valores na tabela a seguir ou edite os registros de nameserver existentes para que eles correspondam a esses valores. Um exemplo de nameservers atribuídos ao Azure é mostrado abaixo.
    


**Primeiro nameserver:** Use o valor do servidor de nomes atribuído pelo Azure.  
**Segundo nameserver:** Use o valor do servidor de nomes atribuído pelo Azure.  

![Azure-BP-redelegar-1-1](../../media/3e4805ea-608a-4df9-8f68-1fbf70d13d08.png)
  
> [!TIP]
> You should use at least two name server records. Se houver outros servidores de nomes listados no site do registrador de domínio, exclua-os. 
  
3. Salve suas alterações.
    
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Em seguida, seu email da Microsoft e outros serviços serão configurados para funcionar com seu domínio. 
  
## <a name="add-a-txt-record-for-verification"></a>Adicionar um registro TXT para verificação
<a name="BKMK_verify"> </a>

Antes de usar seu domínio com a Microsoft, precisamos garantir que você o tenha. Sua capacidade de fazer logon em sua conta no registrador de domínios e criar o registro DNS comprova para a Microsoft que você é o proprietário do domínio.
  
> [!NOTE]
> Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar. 
  
1. Para começar, vá até a sua página de domínios no Azure usando [este link](https://portal.azure.com ). Será solicitado que você faça logon primeiro.
    
    ![Azure-BP-configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. Usando a **barra de pesquisa** na página do **painel** , digite as **zonas DNS**. Na exibição de resultados, selecione **zonas DNS** na parte de **Serviços** . Depois de Redirecionado, selecione o domínio que você deseja atualizar.
    
    ![Azure-BP-configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. Na página **configurações** do seu domínio, na área **zona DNS** , selecione **+ conjunto de registros**.
    
    ![Azure-BP-configure-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. Na área **Adicionar conjunto de registros** , nas caixas do novo conjunto de registros, selecione os valores da tabela a seguir. 
    
    (Escolha o **tipo** e os valores da **unidade TTL** nas listas suspensas.) 
    
    |**Nome**|**Tipo**|**TTL**|**Unidade TTL**|**Valor**|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |TXT  <br/> |1  <br/> |Horas  <br/> |MS = ms *XXXXXXXX*  <br/> **Observação**: esse é um exemplo. Use o seu **destino específico ou aponte para** o valor de endereço aqui, a partir da tabela.           [Como localizo isto?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Azure-BP-Verify-1-1](../../media/7d5a253c-e88f-4565-a00a-79bba52f9970.png)
  
5. Clique em **OK**.
  
6. Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.
    
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

1. Para começar, vá até a sua página de domínios no Azure usando [este link](https://portal.azure.com ). Será solicitado que você faça logon primeiro.
    
    ![Azure-BP-configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. Na página **painel** , na área **todos os recursos** , selecione o domínio que você deseja atualizar. 
    
    ![Azure-BP-configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. Na página **configurações** do seu domínio, na área **zona DNS** , selecione **+ conjunto de registros**.
    
    ![Azure-BP-configure-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. Na área **Adicionar conjunto de registros** , nas caixas do novo conjunto de registros, selecione os valores da tabela a seguir. 
    
    (Escolha o **tipo** e os valores da **unidade TTL** nas listas suspensas.) 
    
    |**Nome**|**Tipo**|**TTL**|**Unidade TTL**|**Preferência**|**Troca de emails**|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |MX  <br/> |1  <br/> |Horas  <br/> |10   <br/> Para saber mais sobre prioridade, confira [O que é prioridade MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> | *\<chave-do-domínio\>*  .mail.protection.outlook.com  <br/> **Observação:** Obtenha sua * \<chave\> de domínio* de sua conta da Microsoft.   [Como localizo isto?](../get-help-with-domains/information-for-dns-records.md)  
   
    ![Azure-BP-configure-2-1](../../media/712c23ae-9d38-4af2-94e0-0704e70744fe.png)
  
5. Clique em **OK**.
    
    ![Azure-BP-configure-2-2](../../media/2f24225f-69ac-41dc-91c5-93d327360f74.png)
  
6. Se houver outros registros MX listados na seção **registros MX** , você deverá excluí-los. 
    
    Primeiro, na área **zona DNS** , selecione o **conjunto de registros MX**.
    
    ![Azure-BP-configure-2-3](../../media/9890da61-6fcd-4c61-888e-ccbb84f80cd0.png)
  
    Em seguida, selecione o registro MX que você deseja excluir.
    
    ![Azure-BP-configure-2-4](../../media/afe54f12-66d2-4ff3-80e9-427448e4c32c.png)
  
7. Selecione o **menu de contexto (...)** e, em seguida, escolha **remover**.
    
    ![Azure-BP-configure-2-5](../../media/25219e25-bc14-4bc7-84ed-ee65eb28a8ed.png)
  
8. Selecione **Salvar**.
    
    ![Azure-BP-configure-2-6](../../media/c6133096-5e43-4637-9c01-b63ee4b03517.png)
  
## <a name="add-the-four-cname-records-that-are-required-for-microsoft"></a>Adicionar os quatro registros CNAME necessários para o Microsoft
<a name="BKMK_add_CNAME"> </a>

1. Para começar, vá até a sua página de domínios no Azure usando [este link](https://portal.azure.com ). Será solicitado que você faça logon primeiro.
    
    ![Azure-BP-configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. Na página **painel** , na área **todos os recursos** , selecione o domínio que você deseja atualizar. 
    
    ![Azure-BP-configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. Na página **configurações** do seu domínio, na área **zona DNS** , selecione **+ conjunto de registros**.
    
    ![Azure-BP-configure-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. Adicione o primeiro dos quatro registros CNAME.
    
    Na área **Adicionar conjunto de registros** , nas caixas do novo conjunto de registros, digite ou copie e cole os valores da primeira linha na tabela a seguir. 
    
    (Escolha o **tipo** e os valores da **unidade TTL** nas listas suspensas.) 
    
    |**Nome**|**Tipo**|**TTL**|**Unidade TTL**|**Alias**|
    |:-----|:-----|:-----|:-----|:-----|
    |descoberta automática  <br/> |CNAME  <br/> |1  <br/> |Horas  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |CNAME  <br/> |1  <br/> |Horas  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |1  <br/> |Horas  <br/> |webdir.online.lync.com  <br/> |
    
   
    ![Azure-BP-configure-3-1](../../media/a1c4d869-da97-43b3-952c-d513a20231dc.png)
  
5. Clique em **OK**.
    
    ![Azure-BP-configure-3-2](../../media/b89b51da-1c07-43cf-9fab-75d2e5eb3544.png)
  
6. Adicione cada um dos outros três registros CNAME.
    
    Na área **zona DNS** , selecione **+ conjunto de registros**. Em seguida, no conjunto de registros vazio, crie um registro usando os valores da próxima linha na tabela e, em seguida, selecione **OK** para concluir esse registro. 
    
    Repita esse processo até ter criado todos os quatro registros CNAME.
    
7.  Opcion Adicionar dois registros CNAME para MDM.

> [!IMPORTANT]
> Se você tiver o gerenciamento de dispositivo móvel (MDM) para a Microsoft, deverá criar dois registros CNAME adicionais. Siga o procedimento que você usou para os outros quatro registros CNAME, mas forneça os valores da tabela a seguir. Se você não tiver o MDM, ignore esta etapa. 
  
|**Nome**|**Tipo**|**TTL**|**Unidade TTL**|**Alias**|
|:-----|:-----|:-----|:-----|:-----|
|enterpriseregistration  <br/> |CNAME  <br/> |1  <br/> |Horas  <br/> |enterpriseregistration.windows.net  <br/> |
|enterpriseenrollment  <br/> |CNAME  <br/> |1  <br/> |Horas  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Não é possível ter mais de um registro TXT para SPF para um domínio. Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam. Se você já tiver um registro SPF para seu domínio, não crie um novo para a Microsoft. Em vez disso, adicione os valores necessários da Microsoft ao registro atual para que você tenha um *único* registro SPF que inclua os dois conjuntos de valores. 
  
1. Para começar, vá até a sua página de domínios no Azure usando [este link](https://portal.azure.com ). Será solicitado que você faça logon primeiro.
    
    ![Azure-BP-configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. Na página **painel** , na área **todos os recursos** , selecione o domínio que você deseja atualizar. 
    
    ![Azure-BP-configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. Na área **zona DNS** , selecione o **conjunto de registros txt**.
    
    ![Azure-BP-configure-4-1](../../media/03095196-5010-4072-8503-79b812084dbf.png)
  
4. Na área **Propriedades do conjunto de registros** , nas caixas do novo conjunto de registros, selecione os valores da tabela a seguir. 
    
    (Escolha o **tipo** e os valores da **unidade TTL** nas listas suspensas.) 
    
    |**Nome**|**Tipo**|**TTL**|**Unidade TTL**|**Valor**|
    |:-----|:-----|:-----|:-----|:-----|
    |@  <br/> |TXT  <br/> |1  <br/> |Horas  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.           

    ![Azure-BP-configure-4-2](../../media/78e84c43-e0ce-433f-8e74-9157fb093cca.png)
  
5. Selecione **Salvar**.
    
    ![Azure-BP-configure-4-3](../../media/d7421c7f-ea63-4e11-8595-a482b8c165e0.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Adicionar os dois registros SRV necessários para o Microsoft
<a name="BKMK_add_SRV"> </a>

1. Para começar, vá até a sua página de domínios no Azure usando [este link](https://portal.azure.com ). Será solicitado que você faça logon primeiro.
    
    ![Azure-BP-configure-1-1](../../media/ed377cad-0c47-4f9f-b322-c3e06b309b1f.png)
  
2. Na página **painel** , na área **todos os recursos** , selecione o domínio que você deseja atualizar. 
    
    ![Azure-BP-configure-1-2](../../media/eb4baad2-92d7-49c9-95e5-1dd8510d5ec9.png)
  
3. Na página **configurações** do seu domínio, na área **zona DNS** , selecione **+ conjunto de registros**.
    
    ![Azure-BP-configure-1-3](../../media/b04db89a-3dbc-4cd2-aaca-af17fda53a60.png)
  
4. Adicione o primeiro dos dois registros SRV.
    
    Na área **Adicionar conjunto de registros** , nas caixas do novo conjunto de registros, selecione os valores da primeira linha da tabela a seguir. 
    
    (Escolha o **tipo** e os valores da **unidade TTL** nas listas suspensas.) 
    
    |**Nome**|**Tipo**|**TTL**|**Unidade TTL**|**Prioridade**|**Espessura**|**Porta**|**Destino**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip. _tls  <br/> |SRV  <br/> |1  <br/> |Horas  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
    |_sipfederationtls. _tcp  <br/> |SRV  <br/> |1  <br/> |Horas  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com  <br/> 

    ![Azure-BP-configure-5-1](../../media/a436e0b4-8bb8-4a66-9c22-4e3b2dcf54ff.png)
  
5. Clique em **OK**.
    
    ![Azure-BP-configure-5-2](../../media/a35b6c8a-d001-4b3c-8a67-96b4890e564c.png)
  
6. Adicione o outro registro SRV.
    
    Nas caixas do novo registro, digite ou copie e cole os valores da segunda linha da tabela.
    
> [!NOTE]
> Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
