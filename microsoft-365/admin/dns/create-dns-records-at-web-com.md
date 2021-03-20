---
title: Criar registros DNS no web.com para a Microsoft
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
ms.assetid: 84acd4fc-6eec-4d00-8bed-568f036ae2af
description: Aprenda a verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços web.com para a Microsoft.
ms.openlocfilehash: b667b2e69822fcd69babda7790a6468b640b073b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909977"
---
# <a name="create-dns-records-at-webcom-for-microsoft"></a>Criar registros DNS no web.com para a Microsoft

 Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.yml)**. 
  
Se web.com for seu provedor de hospedagem DNS, siga as etapas deste artigo para verificar seu domínio e configurar registros DNS para email, Skype for Business Online e assim por diante.
  
Depois de adicionar esses registros web.com, seu domínio será definido para funcionar com os serviços da Microsoft.

  
> [!NOTE]
>  Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="change-your-domains-nameserver-ns-records"></a>Alterar os registros de nameserver (NS) de seu domínio
<a name="BKMK_Nameservers"> </a>

> [!IMPORTANT]
> Você deve executar este procedimento no registrador de domínios onde você comprou e registrou seu domínio. 
  
Quando você se inscreveu no web.com, adicionou um domínio usando o processo web.com **instalação.** 
  
Para verificar e criar registros DNS para seu domínio na Microsoft, primeiro você precisa alterar os nameservers em seu registrador de domínio para que eles usem os nameservers web.com.
  
Para mudar os servidores de nomes do seu domínio por conta própria no site do registrador de domínios, siga essas etapas.
  
1. Localize a área no site do registrador de domínios na qual você pode editar os servidores de nomes do seu domínio.
    
2. Crie dois registros nameserver usando os valores na tabela a seguir ou edite os registros de nameserver existentes para que eles corresponderem a esses valores.
    
    |||
    |:-----|:-----|
    |Primeiro servidor de nome  <br/> |Use o valor nameserver fornecido por web.com.  <br/> |
    |Segundo servidor de nome  <br/> |Use o valor nameserver fornecido por web.com.  <br/> |
   
    > [!TIP]
    > You should use at least two name server records. Se houver outros servidores de nomes listados, exclua-os. 
  
3. Salve suas alterações.
    
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Em seguida, seu email da Microsoft e outros serviços serão definidos para funcionar com seu domínio. 
  
## <a name="add-a-txt-record-for-verification"></a>Adicionar um registro TXT para verificação
<a name="BKMK_verify"> </a>

Antes de usar o seu domínio com a Microsoft, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro de DNS prova à Microsoft que você é o proprietário do domínio.
  
> [!NOTE]
> Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar. 
  
1. Para começar, vá para sua página de domínios no web.com usando [este link](https://checkout.web.com/manage-it/index.jsp). Faça logoff primeiro.
  
2. Na página **Gerenciador de Conta,** selecione **Meus Nomes de Domínio.** 
  
3. Em **Gerenciar *meu domínio***, selecione **Editar Registros DNS Avançados.**

  
4. Na página **Nomes de** Domínio, em **Texto (Registros TXT),** clique em **Editar Registros TXT** e selecione os valores na tabela a seguir. 
    
    |**Host**|**TTL**|**Texto**|
    |:-----|:-----|:----|
    |@  <br/> |3600  <br/> |MS = ms *XXXXXXXX*  <br/> **Observação**: esse é um exemplo. Use aqui seu valor específico de **Destino ou Pontos de Endereçamento**, retirado da tabela.           [Como localizo isto?](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. Selecione **Continuar**.
  
  
6. Aguarde alguns minutos antes de verificar seu novo registro TXT, para que o registro que você acabou de criar possa atualizar na Internet.
    
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

1. Para começar, vá para sua página de domínios no web.com usando [este link](https://checkout.web.com/manage-it/index.jsp). Faça logoff primeiro.
  
2. Na página **Gerenciador de Conta,** selecione **Meus Nomes de Domínio.** 
  
3. Em **Gerenciar *meu domínio***, selecione **Editar Registros DNS Avançados.**

4. Em **Servidores de Email (Registros MX),** clique em Editar Registros **MX** e selecione os valores na tabela a seguir. 
    
    |**Prioridade**|**TTL**|**Servidor de email**|
    |:-----|:-----|:-----|
    |1  <br/> Para saber mais sobre prioridade, confira [O que é prioridade MX?](../setup/domains-faq.yml) <br/> |3600  <br/> |*\<domain-key\>*  .mail.protection.outlook.com  <br/> **Observação:** Obter o  *\<domain-key\>*  seu de sua conta da Microsoft.   [Como localizo isto?](../get-help-with-domains/information-for-dns-records.md) |
   

5. Selecione **Salvar**.
  
6. Se houver outros registros MX listados na seção **Registros MX,** marque a caixa de seleção ao lado do registro em **Excluir** e selecione **Salvar**. 
  
7. Na tela de confirmação, selecione **Salvar alterações**. 

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>Adicionar os seis registros CNAME necessários para a Microsoft
<a name="BKMK_add_CNAME"> </a>

1. Para começar, vá para sua página de domínios no web.com usando [este link](https://checkout.web.com/manage-it/index.jsp). Será solicitado que você faça logon primeiro.
     
2. Na página **Gerenciador de Conta,** selecione **Meus Nomes de Domínio.** 
  
3. Em **Gerenciar *meu domínio***, selecione **Editar Registros DNS Avançados.**

4. Adicione o primeiro dos seis registros CNAME.
    
    Em **Aliases de Host (Registros CNAME),** clique em Editar Registros **CNAME** e selecione os valores na tabela a seguir.
    
    
    |**Alias**|**TTL**|**Refere-se ao Nome do host**|**Outro Host**|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |3600  <br/> |@ (nenhum)  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |3600  <br/> |@ (nenhum)  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |3600  <br/> |@ (nenhum)  <br/> | webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |3600  <br/> |@ (nenhum)  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |3600  <br/> |@ (nenhum)  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
    |msoid  <br/> |3600  <br/> |@ (nenhum)  <br/> |clientconfig.microsoftonline-p.net  <br/> |
    
  
5. Selecione **Continuar**.
  
6. Adicione cada um dos outros cinco registros CNAME.

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Não é possível ter mais de um registro TXT para SPF para um domínio. Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam. Se você já possui um registro SPF para seu domínio, não crie um novo para a Microsoft. Em vez disso, adicione os valores necessários da Microsoft ao registro atual para que você tenha um único registro  *SPF*  que inclua ambos os conjuntos de valores. 
  
1. Para começar, vá para sua página de domínios no web.com usando [este link](https://checkout.web.com/manage-it/index.jsp). Faça logoff primeiro.
    
  
2. Na página **Gerenciador de Conta,** selecione **Meus Nomes de Domínio.** 
  
3. Em **Gerenciar *meu domínio***, selecione **Editar Registros DNS Avançados.**

  
4. Na página **Nomes de** Domínio, em **Texto (Registros TXT),** clique em **Editar Registros TXT** e selecione os valores na tabela a seguir.   
    
    |**Host**|**TTL**|**Texto**|
    |:-----|:-----|:-----|
    |@  <br/> |3600  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.   |

 
5. Selecione **Continuar**.

6. Selecione **Salvar alterações**.
    

  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Adicionar os dois registros SRV necessários para a Microsoft
<a name="BKMK_add_SRV"> </a>

> [!IMPORTANT]
> Lembre-se de que web.com é responsável por disponibilizar essa funcionalidade. Caso você veja discrepâncias entre as etapas abaixo e o gui web.com atual(Interface gráfica do usuário), utilize o [web.com Community](https://community.web.com.com/). 

1. Para começar, vá para sua página de domínios no web.com usando [este link](https://checkout.web.com/manage-it/index.jsp). Faça logoff primeiro.
      
2. Na página **Gerenciador de Conta,** selecione **Meus Nomes de Domínio.** 
  
3. Em **Gerenciar *meu domínio***, selecione **Editar Registros DNS Avançados.**
  
4. Adicione o primeiro dos dois registros SRV.

    Em **Serviço (Registros SRV),** clique em **Editar Registros SRV** e selecione os valores na tabela a seguir. 
        
    |**Serviço**|**Protocolo**|**TTL**|**Prioridade**|**Espessura**|**Porta**|**Destino**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip |_tls |3600 | 100|1 |443 |sipfed.online.lync.com  |
    |_sipfederationtls |_tcp |3600 |100 |1 |5061 | sipfed.online.lync.com |

  
5. Adicione o outro registro SRV escolhendo os valores da segunda linha da tabela. 
  
6. Selecione **Continuar**.

7. Selecione **Salvar alterações**.

    
> [!NOTE]
>  Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
