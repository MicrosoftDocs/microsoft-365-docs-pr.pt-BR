---
title: Criar registros DNS no web.com para Microsoft
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
ms.assetid: 84acd4fc-6eec-4d00-8bed-568f036ae2af
description: Saiba como verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços em web.com para a Microsoft.
ms.openlocfilehash: ec1d0168fb8a9dfb30d47412146777bc88f90a46
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629246"
---
# <a name="create-dns-records-at-webcom-for-microsoft"></a>Criar registros DNS no web.com para Microsoft

 Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**. 
  
Se o web.com for seu provedor de hospedagem DNS, siga as etapas deste artigo para verificar seu domínio e configurar registros DNS para email, Skype for Business Online e assim por diante.
  
Depois que você adicionar esses registros no web.com, o domínio será configurado para funcionar com os serviços da Microsoft.
  
Para saber mais sobre o webhosting e o DNS para sites com a Microsoft, confira [usar um site público com a Microsoft](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).
  
> [!NOTE]
>  Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="change-your-domains-nameserver-ns-records"></a>Alterar os registros de nameserver (NS) de seu domínio
<a name="BKMK_Nameservers"> </a>

> [!IMPORTANT]
> Você deve executar este procedimento no registrador de domínios onde você comprou e registrou seu domínio. 
  
Quando você se inscreveu no web.com, adicionou um domínio usando o processo de **instalação** do Web.com. 
  
Para verificar e criar registros DNS para o seu domínio na Microsoft, primeiro você precisa alterar os nameservers no seu registrador de domínio para que eles usem os nameservers da Web.
  
Para mudar os servidores de nomes do seu domínio por conta própria no site do registrador de domínios, siga essas etapas.
  
1. Localize a área no site do registrador de domínios na qual você pode editar os servidores de nomes do seu domínio.
    
2. Crie dois registros de nameserver usando os valores na tabela a seguir ou edite os registros de nameserver existentes para que eles correspondam a esses valores.
    
    |||
    |:-----|:-----|
    |Primeiro servidor de nome  <br/> |Use o valor de nameserver fornecido pelo web.com.  <br/> |
    |Segundo servidor de nome  <br/> |Use o valor de nameserver fornecido pelo web.com.  <br/> |
   
    > [!TIP]
    > You should use at least two name server records. Se houver outros servidores de nomes listados, exclua-os. 
  
3. Salve suas alterações.
    
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Em seguida, seu email da Microsoft e outros serviços serão configurados para funcionar com seu domínio. 
  
## <a name="add-a-txt-record-for-verification"></a>Adicionar um registro TXT para verificação
<a name="BKMK_verify"> </a>

Antes de usar seu domínio com a Microsoft, precisamos garantir que você o tenha. Sua capacidade de fazer logon em sua conta no registrador de domínios e criar o registro DNS comprova para a Microsoft que você é o proprietário do domínio.
  
> [!NOTE]
> Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar. 
  
1. Para começar, vá até a sua página de domínios no web.com usando [este link](https://checkout.web.com/manage-it/index.jsp). Faça o logon primeiro.
  
2. Na página **Gerenciador de contas** , selecione **meus nomes de domínio**. 
  
3. Em * * gerenciar * meu domínio * * *, selecione **editar registros DNS avançados**.

  
4. Na página **nomes de domínio** , em **texto (registros txt)**, clique em **editar registros txt**e selecione os valores na tabela a seguir. 
    
    |**Host**|**TTL**|**Texto**|
    |:-----|:-----|:----|
    |@  <br/> |3600  <br/> |MS = ms *XXXXXXXX*  <br/> **Observação**: esse é um exemplo. Use o seu **destino específico ou aponte para** o valor de endereço aqui, a partir da tabela.           [Como localizo isto?](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. Selecione **continuar**.
  
  
6. Aguarde alguns minutos antes de verificar o novo registro TXT, para que o registro que você acabou de criar possa ser atualizado na Internet.
    
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

1. Para começar, vá até a sua página de domínios no web.com usando [este link](https://checkout.web.com/manage-it/index.jsp). Faça o logon primeiro.
  
2. Na página **Gerenciador de contas** , selecione **meus nomes de domínio**. 
  
3. Em * * gerenciar * meu domínio * * *, selecione **editar registros DNS avançados**.

4. Em **servidores de email (registros MX)**, clique em **editar registros MX**e selecione os valores na tabela a seguir. 
    
    |**Prioridade**|**TTL**|**Servidor de email**|
    |:-----|:-----|:-----|
    |1  <br/> Para saber mais sobre prioridade, confira [O que é prioridade MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> |3600  <br/> |*\<chave-do-domínio\>*  .mail.protection.outlook.com  <br/> **Observação:** Obtenha sua * \<chave\> de domínio* de sua conta da Microsoft.   [Como localizo isto?](../get-help-with-domains/information-for-dns-records.md) |
   

5. Selecione **Salvar**.
  
6. Se houver outros registros MX listados na seção **registros MX** , marque a caixa de seleção ao lado do registro em **excluir**e selecione **salvar**. 
  
7. Na tela de confirmação, selecione **salvar alterações**. 

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>Adicionar os seis registros CNAME necessários para o Microsoft
<a name="BKMK_add_CNAME"> </a>

1. Para começar, vá até a sua página de domínios no web.com usando [este link](https://checkout.web.com/manage-it/index.jsp). Será solicitado que você faça logon primeiro.
     
2. Na página **Gerenciador de contas** , selecione **meus nomes de domínio**. 
  
3. Em * * gerenciar * meu domínio * * *, selecione **editar registros DNS avançados**.

4. Adicione o primeiro dos seis registros CNAME.
    
    Em **aliases de host (registros CNAME)**, clique em **editar registros CNAME**e selecione os valores da tabela a seguir.
    
    
    |**Alias**|**TTL**|**Refere-se ao Nome do host**|**Outro host**|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |3600  <br/> |@ (nenhum)  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |3600  <br/> |@ (nenhum)  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |3600  <br/> |@ (nenhum)  <br/> | webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |3600  <br/> |@ (nenhum)  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |3600  <br/> |@ (nenhum)  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
    |msoid  <br/> |3600  <br/> |@ (nenhum)  <br/> |clientconfig.microsoftonline-p.net  <br/> |
    
  
5. Selecione **continuar**.
  
6. Adicione cada um dos outros cinco registros CNAME.

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Não é possível ter mais de um registro TXT para SPF para um domínio. Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam. Se você já tiver um registro SPF para seu domínio, não crie um novo para a Microsoft. Em vez disso, adicione os valores necessários da Microsoft ao registro atual para que você tenha um *único* registro SPF que inclua os dois conjuntos de valores. 
  
1. Para começar, vá até a sua página de domínios no web.com usando [este link](https://checkout.web.com/manage-it/index.jsp). Faça o logon primeiro.
    
  
2. Na página **Gerenciador de contas** , selecione **meus nomes de domínio**. 
  
3. Em * * gerenciar * meu domínio * * *, selecione **editar registros DNS avançados**.

  
4. Na página **nomes de domínio** , em **texto (registros txt)**, clique em **editar registros txt**e selecione os valores na tabela a seguir.   
    
    |**Host**|**TTL**|**Texto**|
    |:-----|:-----|:-----|
    |@  <br/> |3600  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.   |

 
5. Selecione **continuar**.

6. Selecione **Salvar alterações**.
    

  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Adicionar os dois registros SRV necessários para o Microsoft
<a name="BKMK_add_SRV"> </a>

> [!IMPORTANT]
> Tenha em mente que o web.com é responsável por tornar essa funcionalidade disponível. Caso você veja discrepâncias entre as etapas abaixo e a GUI atual do web.com (interface gráfica do usuário), aproveite a [comunidade do Web.com](https://community.web.com.com/). 

1. Para começar, vá até a sua página de domínios no web.com usando [este link](https://checkout.web.com/manage-it/index.jsp). Faça o logon primeiro.
      
2. Na página **Gerenciador de contas** , selecione **meus nomes de domínio**. 
  
3. Em * * gerenciar * meu domínio * * *, selecione **editar registros DNS avançados**.
  
4. Adicione o primeiro dos dois registros SRV.

    Em **serviço (Registros SRV)**, clique em **Editar Registros SRV**e selecione os valores na tabela a seguir. 
        
    |**Serviço**|**Protocolo**|**TTL**|**Prioridade**|**Espessura**|**Porta**|**Destino**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip |_tls |3600 | 100|1 |443 |sipfed.online.lync.com  |
    |_sipfederationtls |_tcp |3600 |100 |1 |5061 | sipfed.online.lync.com |

  
5. Adicione o outro registro SRV escolhendo os valores da segunda linha da tabela. 
  
6. Selecione **continuar**.

7. Selecione **Salvar alterações**.

    
> [!NOTE]
>  Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
