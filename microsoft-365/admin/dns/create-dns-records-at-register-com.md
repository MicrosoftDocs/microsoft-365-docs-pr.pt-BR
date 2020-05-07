---
title: Criar registros DNS no Register.com para Microsoft
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
ms.assetid: 55bd8c38-3316-48ae-a368-4959b2c1684e
description: Saiba como verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços em Register.com para a Microsoft.
ms.openlocfilehash: 125baf224cc9f3f21746a2f802b17f2572b65316
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2020
ms.locfileid: "44048898"
---
# <a name="create-dns-records-at-registercom-for-microsoft"></a>Criar registros DNS no Register.com para Microsoft

 **Caso não encontre o conteúdo que está procurando, [verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**. 
  
Se você usa a Register.com como provedor de hospedagem DNS, siga as etapas neste artigo para verificar o domínio e configurar registros DNS para o Skype for Business Online, email e outros serviços.
  
Estes são os registros principais a adicionar. Siga as etapas abaixo ou [assista ao vídeo](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).
  
- [Adicionar um registro TXT ao Register.com para verificar o proprietário do domínio](#add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain)
    
- [Adicione um registro MX para que o email do domínio vá para a Microsoft.](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [Adicionar os registros CNAME necessários para a Microsoft](#add-the-cname-records-that-are-required-for-microsoft)
    
- [Adicionar registro TXT à SPF para ajudar a evitar spam de email](#add-a-txt-record-for-spf-to-help-prevent-email-spam)

- [Adicionar os dois registros SRV necessários para a Microsoft](#add-the-two-srv-records-that-are-required-for-microsoft)
    
Depois que você adicionar esses registros no Register.com, o domínio será configurado para funcionar com os serviços da Microsoft.
  

  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain"></a>Adicionar um registro TXT ao Register.com para verificar o proprietário do domínio
<a name="BKMK_verify"> </a>

Antes de usar o seu domínio com a Microsoft, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro de DNS prova à Microsoft que você é o proprietário do domínio.
  
> [!NOTE]
> Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar. 
  
Siga as etapas abaixo ou [assista ao vídeo (inicia em 0:44)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).
  
1. Para iniciar, vá até a sua página de domínios em Register.com usando [este link](https://www.register.com/myaccount/). Você será solicitado a entrar.
    
2. Escolha **Domínios**.
    
3. Selecione **gerenciar**.
    
4. Localize a linha que contém o nome do domínio que você deseja modificar; e, em seguida, nessa linha, selecione **gerenciar**.
    
5. Role para baixo até a seção **configurações técnicas avançadas** e selecione **editar registros txt (SPF)**.
    
6. In the boxes for the new record, type or copy and paste the values from the following table.
    
    |||
    |:-----|:-----|
    |**Host Name** <br/> |**TXT Record** <br/> |
    |@  <br/> |MS = ms *XXXXXXXX*  <br/> **Observação**: esse é um exemplo. Use aqui seu valor específico de **Destino ou Pontos de Endereçamento**, retirado da tabela. [Como localizo isto?](../get-help-with-domains/information-for-dns-records.md)          |
   
7. Selecione **continuar**.
    
8. Na próxima página, selecione **continuar** novamente para confirmar suas alterações. 
    
9. Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.
    
Agora que você adicionou o registro no site do seu registrador de domínios, retorne à Microsoft e solicite o registro.
  
Quando a Microsoft encontrar o registro TXT correto, seu domínio estará verificado.
  
1. No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.
    
2. Na página **Domínios**, clique no domínio que você está verificando. 
    
3. Na página **Configuração**, clique em **Iniciar configuração**.
    
4. Na página **Verificar domínio**, clique em **Verificar**.
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Adicione um registro MX para que o email do domínio vá para a Microsoft.
<a name="BKMK_add_MX"> </a>

Siga as etapas abaixo ou [assista ao vídeo (inicia em 3:32)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).
  
1. Para iniciar, vá até a sua página de domínios em Register.com usando [este link](https://www.register.com/myaccount/). Você será solicitado a entrar.
    
2. Escolha **Domínios**.
    
3. Selecione **gerenciar**.
    
4. Localize a linha que contém o nome do domínio que você deseja modificar; e, em seguida, nessa linha, selecione **gerenciar**.
    
5. Role até a seção **configurações técnicas avançadas** e, em seguida, selecione **editar registros de servidor de mensagens**.
    
    ![Selecione Editar registros de servidor de mensagens](../../media/366b96a1-9147-4bbb-9f8f-50856466cc61.png)
  
6. Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela.
    
    (Escolha o valor **prioridade** na lista suspensa.) 
    
    |****Nome do host****|****Prioridade****|****Servidor de Email****|
    |:-----|:-----|:-----|
    |@  <br/> |Alto  <br/> Para saber mais sobre prioridade, confira [O que é prioridade MX?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) <br/> | *\<chave-do-domínio\>*  .mail.protection.outlook.com  <br/>  <br/>**Observação:** Obtenha a sua \<*chave-de-domínio*\> através da sua conta Microsoft. <br> [Como localizo isto?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Copiar e colar o valor da tabela](../../media/a1a15a14-c3dc-45dc-adcd-90fdb3f7455d.png)
  
7. Se houver outros registros MX já listados, escolha cada um desses registros a serem excluídos.
    
    ![Select each record to delete](../../media/0708d03e-346f-4ae7-8cc4-01589efc00ce.png)
  
8. Selecione **continuar**.
    
    ![Selecione continuar](../../media/6ef6ce01-ce21-4e3c-8209-4aa9a3dd4b76.png)
  
9. Na próxima página, selecione **continuar** novamente para confirmar e salvar as alterações. 
    
    ![Selecione continuar](../../media/adba4a60-bf61-44fc-9ad9-360e66f8a2ee.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a>Adicionar os registros CNAME necessários para a Microsoft
<a name="BKMK_add_CNAME"> </a>

Siga as etapas abaixo ou [assista ao vídeo (inicia em 4:23)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).
  
1. Para iniciar, vá até a sua página de domínios em Register.com usando [este link](https://www.register.com/myaccount/). Você será solicitado a entrar.
    
2. Escolha **Domínios**.
    
3. Selecione **gerenciar**.
    
4. Localize a linha que contém o nome do domínio que você deseja modificar; e, em seguida, nessa linha, selecione **gerenciar**.
    
5. Role até a seção **configurações técnicas avançadas** e, em seguida, selecione **editar registros de alias de domínio**.
    
    ![Selecione Editar registros de aliases de domínio](../../media/9fbc31ed-d67c-4828-8bd4-b51068f1e0ca.png)
  
6. Selecione **adicionar mais aliases de domínio**.
    
    ![Selecione Adicionar mais aliases de domínios](../../media/b787505f-5566-4879-8552-13f9e89cbf6b.png)
  
7. Adicione os registros CNAME.
    
    Nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir.
    
    |****Primeiro campo (sem rótulo)****|****Pontos de****|
    |:-----|:-----|
    |descoberta automática  <br/> |autodiscover.outlook.com  <br/>  <br/> |
    |sip  <br/> |sipdir.online.lync.com  <br/>  <br/> |
    |lyncdiscover  <br/> |webdir.online.lync.com <br/>  <br/> |
    |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/>  <br/> |
    |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/>  <br/> |
   
     ![Copiar e colar os valores DNS da tabela](../../media/0e2b36b2-8a0b-4019-addf-301763f9a626.png)
  
8. Depois de adicionar todos os registros CNAME necessários, selecione **continuar**.
    
    ![Selecione continuar](../../media/1942612b-338a-48fa-a45d-2d5434516723.png)
  
9. Na próxima página, selecione **continuar** novamente para confirmar e salvar as alterações. 
    
    ![Selecione continuar](../../media/3342b570-0633-49c5-9175-5cc8e4a67b53.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Não é possível ter mais de um registro TXT para SPF para um domínio. Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam. Se você já possui um registro SPF para seu domínio, não crie um novo para a Microsoft. Em vez disso, adicione os valores necessários da Microsoft ao registro atual para que você tenha um único registro SPF que inclua os dois conjuntos de valores.  
  
Siga as etapas abaixo ou [assista ao vídeo (inicia em 5:12)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).
  
1. Para iniciar, vá até a sua página de domínios em Register.com usando [este link](https://www.register.com/myaccount/). Você será solicitado a entrar.
    
2. Escolha **Domínios**.
    
3. Selecione **gerenciar**.
    
4. Localize a linha que contém o nome do domínio que você deseja modificar; e, em seguida, nessa linha, selecione **gerenciar**.
    
5. Role até a seção **configurações técnicas avançadas** e selecione **editar registros txt (SPF)**.
    
    ![Selecionar editar registros TXT (SPF)](../../media/c917577a-8b3a-4210-ab6e-776e84f926d0.png)
  
6. Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela.
    
    |****Nome do Host****|****Registro TXT****|
    |:-----|:-----|
    |@  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.  |
   
     ![Copiar e colar os valores da tabela](../../media/b1dc5036-c13c-4306-b1e3-5a38a74643b7.png)
  
7. Selecione **continuar**.
    
    ![Selecione continuar](../../media/08250c98-1a86-48a8-ad94-f96cf338126b.png)
  
8. Na próxima página, selecione **continuar** novamente para confirmar e salvar as alterações. 
    
    ![Selecione continuar](../../media/56be3b0a-dc71-471c-9be3-6ab927296f67.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Adicionar os dois registros SRV necessários para a Microsoft
<a name="BKMK_add_SRV"> </a>

Siga as etapas abaixo ou [assista ao vídeo (inicia em 5:55)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).
  
1. Para iniciar, vá até a sua página de domínios em Register.com usando [este link](https://www.register.com/myaccount/). Você será solicitado a entrar.
    
2. Escolha **Domínios**.
    
3. Selecione **gerenciar**.
    
4. Localize a linha que contém o nome do domínio que você deseja modificar; e, em seguida, nessa linha, selecione **gerenciar**.
    
5. Role até a seção **configurações técnicas avançadas** e selecione **Editar Registros SRV**.
    
    ![Selecione Editar Registros SRV](../../media/73c149ae-f0d6-460e-880a-7e04a995acc3.png)
  
6. Adicione o primeiro dos dois registros SRV:
    
    Nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir.
    
    (Escolha o valor **prioridade** na lista suspensa.) 
    
    |****Serviço****|****Proto****|****Nome****|****Prioridade****|****Peso****|****Porta****|****Destino****|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip  <br/> |_tls  <br/> |@  <br/> |Alta  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com  <br/>  <br/> |
    |_sipfederationtls  <br/> |_tcp  <br/> |@  <br/> |Alta  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com  <br/>  <br/> |
   
    ![Copiar e colar os valores da tabela](../../media/71304c81-5845-4a8f-b969-d9efc8721184.png)
  
7. Selecione **adicionar mais registros SRV**.
    
    ![Selecione Adicionar mais registros SRV](../../media/823c6bd2-4af7-4079-bf8c-8d35a5c6730f.png)
  
8. Adicione o segundo registro SRV:
    
    Digite ou copie e cole os valores da segunda linha da tabela acima nas caixas do segundo registro.
    
9. Após adicionar ambos os registros SRV, selecione **continuar**.
    
    ![Selecione continuar](../../media/008b255a-42d3-442d-83ea-3ffcb7c8fc5d.png)
  
10. Na próxima página, selecione **continuar** novamente para confirmar e salvar as alterações. 
    
    ![Selecione continuar](../../media/b4166e3d-7e4b-41ef-b616-747e95aefc37.png)
  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
