---
title: Criar registros DNS no Cloudflare para a Microsoft
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
description: Aprenda a verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços na Cloudflare para Microsoft.
ms.openlocfilehash: 8d5dd7779f07fd42dd230ee33c40849da3519d26
ms.sourcegitcommit: ba830e85899f247e5a1e117d63e09e4d5b8a8020
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49939267"
---
# <a name="create-dns-records-at-cloudflare-for-microsoft"></a>Criar registros DNS no Cloudflare para a Microsoft

 Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.yml)**. 
  
Se o Cloudflare for seu provedor de hospedagem DNS, siga as etapas deste artigo para verificar o domínio e configurar registros DNS para o Skype for Business Online, email e outros serviços.
  
Depois que você adicionar esses registros na Cloudflare, seu domínio será definido para funcionar com os serviços do Microsoft 365.
  
  
> [!NOTE]
>  Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="change-your-domains-nameserver-ns-records"></a>Alterar os registros de nameserver (NS) de seu domínio
<a name="BKMK_Nameservers"> </a>

> [!IMPORTANT]
> Você deve executar este procedimento no registrador de domínios onde você comprou e registrou seu domínio. 
  
Quando você se inscreveu no Cloudflare, adicionou  um domínio usando o processo de instalação cloudflare. 
  
O domínio que você adicionou foi adquirido do Cloudflare ou de um registrador de domínios separado. Para verificar e criar registros DNS para seu domínio no Microsoft 365, primeiro você precisa alterar os nameservers no registrador de domínios para que eles usem os nameservers do Cloudflare.
  
Para mudar os servidores de nomes do seu domínio por conta própria no site do registrador de domínios, siga essas etapas.
  
1. Localize a área no site do registrador de domínios na qual você pode editar os servidores de nomes do seu domínio.
    
2. Crie dois registros de nameserver usando os valores da tabela a seguir ou edite os registros de nameserver existentes para que eles corresponderem a esses valores.
    
    |||
    |:-----|:-----|
    |Primeiro servidor de nome  <br/> |Use o valor de nameserver fornecido pelo Cloudflare.  <br/> |
    |Segundo servidor de nome  <br/> |Use o valor de nameserver fornecido pelo Cloudflare.  <br/> |
   
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
  
1. To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login). Será solicitado que você faça logon primeiro.
  
2. Na **home** page, selecione o domínio que você deseja atualizar. 
  
3. Na página **Visão** geral do seu domínio, selecione **DNS.**

  
4. Na página **de gerenciamento DNS,** clique **em Adicionar registro** e selecione os valores da tabela a seguir. 
    
    | Tipo | Nome | TTL automática | Conteúdo |
    |:-----|:-----|:-----|:----|
    |TXT  <br/> |@  <br/> |30 minutos  <br/> |MS = ms *XXXXXXXX*  <br/> **Observação**: esse é um exemplo. Use aqui seu valor específico de **Destino ou Pontos de Endereçamento**, retirado da tabela.           [Como localizo isto?](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. Selecione **Salvar**.
  
  
9. Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.
    
Agora que você adicionou o registro no site do registrador de domínios, volte para a Microsoft e procure o registro.
  
Quando a Microsoft encontrar o registro TXT correto, seu domínio estará verificado.
  
1. No centro do administrador da Microsoft, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.

    
2. Na página **Domínios**, clique no domínio que você está verificando. 
    
    
  
3. Na página **Configuração**, clique em **Iniciar configuração**.
    
    
  
4. Na página **Verificar domínio**, marque **Verificar**.
    
    
  
> [!NOTE]
>  Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Adicione um registro MX para que o email do domínio vá para a Microsoft.
<a name="BKMK_add_MX"> </a>

1. To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login). Será solicitado que você faça logon primeiro.
  
2. Na **home** page, selecione o domínio que você deseja atualizar. 
  
3. Na página **Visão** geral do seu domínio, selecione **DNS.**

  
4. Na página **de gerenciamento DNS,** clique **em Adicionar registro** e selecione os valores da tabela a seguir. 
    
    | Tipo | Nome | Servidor de email | Prioridade | TTL |
    |:-----|:-----|:-----|:-----|:-----|
    |MX  <br/> |@  <br/> |*\<domain-key\>*  .mail.protection.outlook.com  <br/> **Observação:** Obter o  *\<domain-key\>*  seu na sua conta do Microsoft 365.   [Como faço para encontrar isso?](../get-help-with-domains/information-for-dns-records.md) |1   <br/> Para saber mais sobre prioridade, confira [O que é prioridade MX?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) <br/>|30 minutos  <br/> |
   

  
5. Selecione **Salvar**.
  
9. Se houver outros registros MX listados na seção **Registros MX,** exclua-os selecionando o ícone **Excluir (X).** 
  
10. Na caixa de diálogo de confirmação, selecione **Excluir** para confirmar suas alterações. 

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>Adicionar os seis registros CNAME necessários para a Microsoft
<a name="BKMK_add_CNAME"> </a>

1. To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login). Será solicitado que você faça logon primeiro.
    
  
2. Na **home** page, selecione o domínio que você deseja atualizar. 
  
3. Na página **Visão** geral do seu domínio, selecione **DNS.**

  
4. Adicione o primeiro dos cinco registros CNAME.
    
    Na página **de gerenciamento DNS,** clique **em Adicionar registro** e selecione os valores da tabela a seguir.
    
    
    | Tipo | Nome | Target | TTL |
    |:-----|:-----|:-----|:-----|
    |CNAME  <br/> |descoberta automática  <br/> |autodiscover.outlook.com  <br/> |30 minutos  <br/> |
    |CNAME  <br/> |sip  <br/> |sipdir.online.lync.com  <br/> |30 minutos  <br/> |
    |CNAME  <br/> |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |30 minutos  <br/> |
    |CNAME  <br/> |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |30 minutos  <br/> |
    |CNAME  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |30 minutos  <br/> |
    |CNAME  <br/> |msoid  <br/> |clientconfig.microsoftonline-p.net  <br/> |30 minutos  <br/> |
    
  
5. Selecione o **ícone de Tráfego DNS** (alterar a nuvem laranja para cinza) para ignorar os servidores Cloudflare.
  
6. Selecione **Salvar**.
  
7. Adicione cada um dos outros cinco registros CNAME.

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Não é possível ter mais de um registro TXT para SPF para um domínio. Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam. Se você já possui um registro SPF para seu domínio, não crie um novo para o Microsoft 365. Em vez disso, adicione os valores necessários do Microsoft 365 ao registro atual para que você tenha um *único* registro SPF que inclua os dois conjuntos de valores. 
  
1. To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login). Será solicitado que você faça logon primeiro.
    
  
2. Na **home** page, selecione o domínio que você deseja atualizar. 
  
3. Na página **Visão** geral do seu domínio, selecione **DNS.**

  
4. Na página **de gerenciamento DNS,** clique **em Adicionar registro** e selecione os valores da tabela a seguir.  
    
    | Tipo | Nome | TTL | Conteúdo |
    |:-----|:-----|:-----|:-----|
    |TXT  <br/> |@  <br/> |30 minutos  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.   |

 
5. Selecione **Salvar**.
    

  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Adicionar os dois registros SRV necessários para a Microsoft
<a name="BKMK_add_SRV"> </a>

> [!IMPORTANT]
> Lembre-se de que o Cloudflare é responsável por disponibilizar essa funcionalidade. Caso você veja discrepâncias entre as etapas abaixo e a GUI cloudflare atual (Interface gráfica do usuário), aproveite a [comunidade Cloudflare.](https://community.cloudflare.com/) 

1. To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login). Será solicitado que você faça logon primeiro.
      
2. Na **home** page, selecione o domínio que você deseja atualizar. 
  
3. Na página **Visão** geral do seu domínio, selecione **DNS.**
  
4. Adicione o primeiro dos dois registros SRV.

    Na página **de gerenciamento DNS,** clique em **Adicionar registro** e selecione os valores da primeira linha da tabela a seguir.
        
    | Tipo | Serviço | Protocolo | Nome | TTL | Priority | Peso | Porta | Target |
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV|_sip |TLS |Use seu *domain_name*; por exemplo, contoso.com  |30 minutos | 100|1  |443 |sipfed.online.lync.com  |
    |SRV|_sipfederationtls | TCP|Use seu *domain_name*; por exemplo, contoso.com   |30 minutos |100 |1  |5061 | sipfed.online.lync.com |

  
5. Selecione **Salvar**.

  
6. Adicione o outro registro SRV escolhendo os valores da segunda linha da tabela. 

    
> [!NOTE]
>  Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
