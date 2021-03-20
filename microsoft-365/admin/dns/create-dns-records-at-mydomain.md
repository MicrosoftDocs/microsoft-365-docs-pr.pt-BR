---
title: Criar registros DNS no Meu Domínio para Microsoft
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
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
ms.assetid: 9982191d-ed79-46a9-b2e7-317d1a3a9867
description: Aprenda a verificar seu domínio e a configurar registros DNS para emails, Skype for Business Online e outros serviços em Meu Domínio para Microsoft.
ms.openlocfilehash: 1e7f9c5705e535c1558273be5bfdc99841e0ea4b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910157"
---
# <a name="create-dns-records-at-mydomain-for-microsoft"></a>Criar registros DNS no Meu Domínio para Microsoft


  
 Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.yml)**. 
  
> [!CAUTION]
> O site MyDomain não dá suporte a registros SRV, ou seja, vários recursos do Skype for Business Online e do Outlook Web App não funcionarão. Não importa qual plano da Microsoft você utiliza, se você gerenciar seus registros DNS no site Meu Domínio, haverá [limitações de serviço significativas](../setup/domains-faq.yml) e talvez você queira mudar para um provedor de hospedagem de DNS diferente. 
  
Se você quiser gerenciar seus próprios registros DNS da Microsoft na MyDomain apesar das limitações do serviço, siga as etapas deste artigo para configurar os registros DNS para email, Skype for Business Online e assim por diante.
    
Depois que você adicionar esses registros no Meu Domínio, seu domínio será configurado para funcionar com os serviços Microsoft. 
  

  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Adicionar um registro TXT para verificação
<a name="BKMK_verify"> </a>

Antes de usar o seu domínio com a Microsoft, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro de DNS prova à Microsoft que você é o proprietário do domínio.
  
> [!NOTE]
> Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar. 
  
1. Para começar, vá até a sua página de domínios em MeuDomínio usando [este link](https://www.mydomain.com/controlpanel). Você será solicitado a fazer logon primeiro.
    
2. Na seção **Meus Favoritos**, clique em **Central de domínio**.
    
3. Na opção **Domínio**, clique no nome do domínio que quer editar.
    
4. Na linha **Visão geral**, clique em **DNS**.
    
5. Na lista suspensa **Modificar**, clique em **Registro TXT/SPF**.
    
6. Em **Content**, na caixa do novo registro, digite ou copie e cole os valores da tabela a seguir.
    
    ||
    |:-----|
    |**Conteúdo** <br/> |
    |MS = ms *XXXXXXXX*  <br/> **Observação**: esse é um exemplo. Use aqui seu valor específico de **Destino ou Pontos de Endereçamento**, retirado da tabela. [Como localizo isto?](../get-help-with-domains/information-for-dns-records.md)          |
   
7. Clique em **Adicionar**.
    
8. Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.
    
Agora que você adicionou o registro no site do seu registrador de domínios, retorne à Microsoft e solicite o registro.
  
Quando a Microsoft encontrar o registro TXT correto, seu domínio estará verificado.
  
1. No centro do administrador da Microsoft, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.
    
2. Na página **Domínios**, clique no domínio que você está verificando. 
    
3. Na página **Configuração**, clique em **Iniciar configuração**.
    
4. Na página **Verificar domínio**, clique em **Verificar**.
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Adicione um registro MX para que o email do domínio vá para a Microsoft.
<a name="BKMK_add_MX"> </a>

1. Para começar, vá até a sua página de domínios em MeuDomínio usando [este link](https://www.mydomain.com/controlpanel). Você será solicitado a fazer logon primeiro.
    
2. Na seção **Meus Favoritos**, clique em **Central de domínio**.
    
3. Na opção **Domínio**, clique no nome do domínio que quer editar.
    
4. Na linha **Visão geral**, clique em **DNS**.
    
5. Na lista suspensa **Modificar**, escolha **Registro MX**.
    
    ![MyDomain-BP-Configure-2-1](../../media/bbfba978-8c53-471b-8c9e-8ae62e559d15.png)
  
6. Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela.
    
    |**Prioridade**|**Host**|**Aponta para:**|
    |:-----|:-----|:-----|
    |0  <br/> Para saber mais sobre prioridade, confira [O que é prioridade MX?](../setup/domains-faq.yml) <br/> |@  <br/> | *\<domain-key\>*  .mail.protection.outlook.com  <br/> **Observação:** Obtenha a sua \<*domain-key*\> através da sua conta Microsoft. > [Como localizo isso?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![MyDomain-BP-Configure-2-2](../../media/3e19cec3-7f3b-493d-81f7-cda30ba007d5.png)
  
7. Clique em **Adicionar**.
    
    ![MyDomain-BP-Configure-2-3](../../media/1a1951a8-11d7-405d-bef5-285bbb053ce8.png)
  
8. Se houver outros registros MX, selecione **Remover** na coluna **Ação** em cada um para excluí-los. 
    
    ![MyDomain-BP-Configure-2-4](../../media/42576149-e056-4a81-a5fd-2c5dfac44e2e.png)
  
9. Clique em **OK**.
    
    ![MyDomain-BP-Configure-2-5](../../media/d6b70eb7-b79c-499e-82ff-ecef2e300368.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a>Adicionar os registros CNAME necessários para a Microsoft
<a name="BKMK_add_CNAME"> </a>

1. Para começar, vá até a sua página de domínios em MeuDomínio usando [este link](https://www.mydomain.com/controlpanel). Você será solicitado a fazer logon primeiro.
    
2. Na seção **Meus Favoritos**, clique em **Central de domínio**.
    
3. Na opção **Domínio**, clique no nome do domínio que quer editar.
    
4. Na linha **Visão geral**, clique em **DNS**.
    
5. Na lista suspensa **Modificar**, escolha **Alias CNAME**.
    
    ![MyDomain-BP-Configure-3-1](../../media/628267fc-d37b-42ef-bb92-265284e339ac.png)
  
6. Adicionar o primeiro registro CNAME.
    
    Nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir.
    
    |**Host**|**Aponta para:**|
    |:-----|:-----|
    |descoberta automática  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
    ![MyDomain-BP-Configure-3-2](../../media/3c8660b3-40bb-453d-8b99-4d22032bc4b3.png)
  
7. Clique em **Adicionar** para adicionar o primeiro registro. 
    
    ![MyDomain-BP-Configure-3-3](../../media/103a1d99-70da-4fdf-9291-7dd058ec6c4a.png)
  
8. Adicione o segundo registro CNAME.
    
    Use os valores da segunda linha da tabela acima e clique em **Adicionar** para adicionar o segundo registro. 
    
    Adicione os registros restantes da mesma maneira, usando os valores da terceira, quarta, quinta e sexta linhas da tabela.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Não é possível ter mais de um registro TXT para SPF para um domínio. Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam. Se você já possui um registro SPF para seu domínio, não crie um novo para a Microsoft. Em vez disso, adicione os valores necessários da Microsoft ao registro atual para que você tenha um único registro SPF que inclua os dois conjuntos de valores. Precisa de exemplos? Confira os [Registros do Sistema de Nomes de Domínios externos para a Microsoft](../../enterprise/external-domain-name-system-records.md#bkmk_spfrecords). To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.yml). 
  
1. Para começar, vá até a sua página de domínios em MeuDomínio usando [este link](https://www.mydomain.com/controlpanel). Você será solicitado a fazer logon primeiro.
    
2. Na seção **Meus Favoritos**, clique em **Central de domínio**.
    
3. Na opção **Domínio**, clique no nome do domínio que quer editar.
    
4. Na linha **Visão geral**, clique em **DNS**.
    
5. Na lista suspensa **Modificar**, escolha **Registro TXT/SPF**.
    
    ![MyDomain-BP-Configure-4-1](../../media/c461c762-52e6-4fde-b5bc-4dd5e5d62ed3.png)
  
6. Em **Content**, na caixa do novo registro, digite ou copie e cole os valores da tabela a seguir.
    
    |**Conteúdo**|
    |:-----|
    |v=spf1 include:spf.protection.outlook.com -all  <br/> **Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.           |
   
    ![MyDomain-BP-Configure-4-2](../../media/17d43106-88e6-47e5-aeba-0f18484acf3e.png)
  
7. Clique em **Adicionar**.
    
    ![MyDomain-BP-Configure-4-3](../../media/b3670563-b620-470c-a42b-2c77888981f8.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Adicionar os dois registros SRV necessários para a Microsoft
<a name="BKMK_add_SRV"> </a>

> [!CAUTION]
> O site MyDomain não dá suporte a registros SRV, ou seja, vários recursos do Skype for Business Online e do Outlook Web App não funcionarão. Não importa qual plano da Microsoft você utiliza, se você gerenciar seus registros DNS no site Meu Domínio, haverá [limitações de serviço significativas](../setup/domains-faq.yml) e talvez você queira mudar para um provedor de hospedagem de DNS diferente. 
  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
