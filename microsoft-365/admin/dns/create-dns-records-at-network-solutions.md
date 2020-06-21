---
title: Criar registros DNS no Network Solutions for Microsoft
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1dc55f9f-5309-450f-acc3-b2b4119c8be3
description: Saiba como verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços em soluções de rede para a Microsoft.
ms.openlocfilehash: 25e85bf30527b49ada711af9ba5c418409acd24c
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780332"
---
# <a name="create-dns-records-at-network-solutions-for-microsoft"></a>Criar registros DNS no Network Solutions for Microsoft

 **Caso não encontre o conteúdo que está procurando, [verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**. 
  
Se você usa a Network Solutions como provedor de hospedagem DNS, siga as etapas neste artigo para verificar o domínio e configurar registros DNS para o Skype for Business Online, email e outros serviços.
  
Estes são os registros principais a adicionar. Siga as etapas abaixo ou [assista ao vídeo](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099). 
  
- [Adicionar um registro TXT para verificação](#add-a-txt-record-for-verification)
    
- [Adicione um registro MX para que o email do domínio vá para a Microsoft.](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [Adicionar os registros CNAME necessários para a Microsoft](#add-the-cname-records-that-are-required-for-microsoft)
    
- [Adicionar registro TXT à SPF para ajudar a evitar spam de email](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [Adicionar os dois registros SRV necessários para a Microsoft](#add-the-two-srv-records-that-are-required-for-microsoft)
    
Depois que você adicionar esses registros às soluções de rede, o domínio será configurado para funcionar com os serviços da Microsoft.
  

  
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Adicionar um registro TXT para verificação
<a name="BKMK_verify"> </a>

Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.
  
> [!NOTE]
> This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like. 
  
Siga as etapas abaixo ou [assista ao vídeo (inicia em 0:47)](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).
  
1. Para iniciar, vá até a página do seu domínio em Network Solutions, usando [este link](https://www.networksolutions.com/manage-it). Você será solicitado a fazer o logon.
    
    > [!IMPORTANT]
    > Antes de selecionar o botão de **login** , primeiro escolha **gerenciar meus nomes de domínio** na lista suspensa **fazer logon em:** . 
  
    ![Escolha Gerenciar Meus Nomes de Domínio e entre no Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. Selecione a caixa de seleção ao lado do nome do domínio que você está modificando.
    
    ![Marque a caixa de seleção do domínio](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. Selecione **Editar DNS**.
    
    ![Selecione Editar DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. Selecione **gerenciar registros de DNS avançados**.
    
    (You may have to scroll down.)
    
    ![Selecionar gerenciar registros DNS avançados](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. Role para baixo até a seção **texto (registros txt)** e selecione **editar registros txt**.
    
    ![Selecionar editar registros TXT](../../media/240a01d6-750a-4da6-8554-641b571e4b71.png)
  
6. Nas caixas do novo registro, digite ou copie e cole os valores na tabela seguinte.
    
    |**Host**|**TTL**|**Texto**|
    |:-----|:-----|:-----|
    |@  <br/> (The system will change this value to **@ (None)** when you save the record.)  <br/> |3600  <br/> |MS=ms *XXXXXXXX*  <br/> **Observação**: esse é um exemplo. Use aqui seu valor específico de **Destino ou Pontos de Endereçamento**, retirado da tabela.  [Como localizo isto?](../get-help-with-domains/information-for-dns-records.md)   |
       
    ![Digitar ou colar valores nas caixas do novo registro](../../media/8a76daab-b6ff-4c82-ba68-192b24fbb934.png)
  
7. Selecione **continuar**.
    
    ![Selecione continuar](../../media/89e7fb38-b4d9-4949-a1bb-d0dd10b361e0.png)
  
8. Selecione **salvar alterações**.
    
    ![Selecionar Salvar alterações](../../media/bd4d7cd0-c8a3-497a-b080-cfd5a5c60dc5.png)
  
9. Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.
    
Agora que você adicionou o registro no site do seu registrador de domínios, retorne à Microsoft e solicite o registro.
  
Quando a Microsoft encontrar o registro TXT correto, seu domínio estará verificado.

1. No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.
    
2. Na página **Domínios**, clique no domínio que você está verificando. 
    
    
  
3. Na página **Configuração**, clique em **Iniciar configuração**.
    
    
  
4. Na página **Verificar domínio**, marque **Verificar**.
    
    
  
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Adicione um registro MX para que o email do domínio vá para a Microsoft.
<a name="BKMK_add_MX"> </a>

Siga as etapas abaixo ou [assista ao vídeo (inicia em 3:51)](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).
  
1. Para iniciar, vá até a página do seu domínio em Network Solutions, usando [este link](https://www.networksolutions.com/manage-it). Você será solicitado a fazer o logon.
    
    > [!IMPORTANT]
    > Antes de selecionar o botão de **login** , primeiro escolha **gerenciar meus nomes de domínio** na lista suspensa **fazer logon em:** . 
  
    ![Escolha Gerenciar Meus Nomes de Domínio e entre no Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. Selecione a caixa de seleção ao lado do nome do domínio que você está modificando.
    
    ![Marque a caixa de seleção do domínio](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. Selecione **Editar DNS**.
    
    ![Selecione Editar DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. Selecione **gerenciar registros de DNS avançados**.
    
    (You may have to scroll down.)
    
    ![Selecionar gerenciar registros DNS avançados](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. Role para baixo até a seção **servidores de email (registros MX)** e selecione **editar registros MX**.
    
    ![Selecione Editar registros MX](../../media/74b4e412-9073-4d2d-8710-fe340b223798.png)
  
6. Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela.
    
    |**Prioridade**|**TTL**|**Servidor de Email**|
    |:-----|:-----|:-----|
    |10   <br/> Para saber mais sobre prioridade, confira [O que é prioridade MX?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) <br/> |3600  <br/> | *\<domain-key\>*. mail.protection.outlook.com.  <br/> **This value MUST end with a period (.)** <br/> **Observação:** Acesse sua *\<domain-key\>* conta da Microsoft. [Como localizo isto?](../get-help-with-domains/information-for-dns-records.md)          |
       
    ![Digitar ou colar valores nas caixas do novo registro](../../media/0bb96872-cc6e-4dfa-a649-fb7efbbf0012.png)
  
7. Selecione **continuar**.
    
    ![Selecione continuar](../../media/963f758b-e79d-4452-8340-7eba8a3972c9.png)
  
8. Selecione **salvar alterações**.
    
    ![Selecionar Salvar alterações](../../media/7c2f784a-6dee-4364-866c-ad7202ef1fc2.png)
  
9. Se houver outros registros MX, exclua todos escolhendo **Excluir** para cada registro. 
    
    ![Select the Delete check box for other MX records](../../media/709d6133-9f5d-490a-a91e-95e21ca94695.png)
  
10. Quando estiverem todos selecionados, selecione **continuar**.
    
    ![Selecione continuar](../../media/4710f988-0bbc-4ba7-bf31-ca2392b2900e.png)
  
11. Selecione **salvar alterações**.
    
    ![Selecionar Salvar alterações](../../media/24432ec6-666b-4612-9488-37c06437959b.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a>Adicionar os registros CNAME necessários para a Microsoft
<a name="BKMK_add_CNAME"> </a>

Siga as etapas abaixo ou [assista ao vídeo (inicia em 4:43)](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).
  
1. Para iniciar, vá até a página do seu domínio em Network Solutions, usando [este link](https://www.networksolutions.com/manage-it). Você será solicitado a fazer o logon.
    
    > [!IMPORTANT]
    > Antes de selecionar o botão de **login** , primeiro escolha **gerenciar meus nomes de domínio** na lista suspensa **fazer logon em:** . 
  
    ![Escolha Gerenciar Meus Nomes de Domínio e entre no Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. Selecione a caixa de seleção ao lado do nome do domínio que você está modificando.
    
    ![Marque a caixa de seleção do domínio](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. Selecione **Editar DNS**.
    
    ![Selecione Editar DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. Selecione **gerenciar registros de DNS avançados**.
    
    (You may have to scroll down.)
    
    ![Selecionar gerenciar registros DNS avançados](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. Role para baixo até a seção **aliases de host (registros CNAME)** e selecione **editar registros CNAME**.
    
    ![Selecione Editar registros CNAME em aliases de host](../../media/2d0a4666-8d40-48f4-886c-64a5157baaf5.png)
  
6. Nas caixas dos quatro novos registros, digite ou copie e cole os valores da seguinte tabela.
    
    |**Alias**|**TTL**|**Refere-se ao Nome do host**|**Outro Host          (selecione o botão de opção **Outro Host**)**|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |3600  <br/> |(Sem configuração)  <br/> |autodiscover.outlook.com.  <br/> **This value MUST end with a period (.)** <br/> |
    |sip  <br/> |3600  <br/> |(Sem configuração)  <br/> |sipdir.online.lync.com.  <br/> **Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)** <br/> |
    |lyncdiscover  <br/> |3600  <br/> |(Sem configuração)  <br/> |webdir.online.lync.com.  <br/> **This value MUST end with a period (.)** <br/> |
    |enterpriseregistration  <br/> |3600  <br/> |(Sem configuração)  <br/> |enterpriseregistration.windows.net  <br/> **Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)** <br/> |
    |enterpriseenrollment  <br/> |3600  <br/> |(Sem configuração)  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> **This value MUST end with a period (.)** <br/> |
    
    ![Digitar ou colar valores dos novos registros](../../media/5ce0b30c-b46c-4778-aa5a-fb5e2f0961c1.png)
  
7. Depois de adicionar todos os registros CNAME necessários, selecione **continuar**.
    
    ![Selecione continuar](../../media/4978bd8b-f6a6-458d-9522-ad612b301c4a.png)
  
8. Selecione **salvar alterações**.
    
    ![Selecionar Salvar alterações](../../media/f005c38a-0d8d-4c61-bec6-15e60c89aa5a.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Adicionar registro TXT à SPF para ajudar a evitar spam de email
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Não é possível ter mais de um registro TXT para SPF para um domínio. Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam. Se você já possui um registro SPF para seu domínio, não crie um novo para a Microsoft. Em vez disso, adicione os valores necessários da Microsoft ao registro atual para que você tenha um *único* registro SPF que inclua os dois conjuntos de valores. 
  
Siga as etapas abaixo ou [assista ao vídeo (inicia em 5:35)](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).
  
1. Para iniciar, vá até a página do seu domínio em Network Solutions, usando [este link](https://www.networksolutions.com/manage-it). Você será solicitado a fazer o logon.
    
    > [!IMPORTANT]
    > Antes de selecionar o botão de **login** , primeiro escolha **gerenciar meus nomes de domínio** na lista suspensa **fazer logon em:** . 
  
    ![Escolha Gerenciar Meus Nomes de Domínio e entre no Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. Selecione a caixa de seleção ao lado do nome do domínio que você está modificando.
    
    ![Marque a caixa de seleção do domínio](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. Selecione **Editar DNS**.
    
    ![Selecione Editar DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. Selecione **gerenciar registros de DNS avançados**.
    
    (You may have to scroll down.)
    
    ![Selecionar gerenciar registros DNS avançados](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. Role para baixo até a seção **texto (registros txt)** e selecione **editar registros txt**.
    
    ![Selecionar editar registros TXT em texto](../../media/a69a2631-6da2-4e81-99ab-9a9ab9b30b07.png)
  
6. Nas caixas do novo registro, digite ou copie e cole os seguintes valores.
    
    |**Host**|**TTL**|**Texto**|
    |:-----|:-----|:-----|
    |@  <br/> (The system will change this value to **@ (None)** when you save the record.)  <br/> |3600  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Observação:** é recomendável copiar e colar essa entrada, para que todo o espaçamento permaneça correto. |
       
    ![Digitar ou colar valores para o novo registro](../../media/11564eca-e2ee-4f17-af2b-a00eb7c157db.png)
  
7. Selecione **continuar**.
    
    ![Selecione continuar](../../media/482a8dae-0c79-47c4-8bd8-87965683de24.png)
  
8. Selecione **salvar alterações**.
    
    ![Selecionar Salvar alterações](../../media/600b8c6d-184f-4213-a50e-8f119ebf3ff0.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Adicionar os dois registros SRV necessários para a Microsoft
<a name="BKMK_add_SRV"> </a>

Siga as etapas abaixo ou [assista ao vídeo (inicia em 6:18)](https://support.microsoft.com/office/c49698c2-6991-47fb-b5ac-18e49a505099).
  
1. To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it). You'll be prompted to log in.
    
    > [!IMPORTANT]
    > Antes de selecionar o botão de **login** , primeiro escolha **gerenciar meus nomes de domínio** na lista suspensa **fazer logon em:** . 
  
    ![Escolha Gerenciar Meus Nomes de Domínio e entre no Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. Selecione a caixa de seleção ao lado do nome do domínio que você está modificando.
    
    ![Marque a caixa de seleção do domínio](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. Selecione **Editar DNS**.
    
    ![Selecione Editar DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. Selecione **gerenciar registros de DNS avançados**.
    
    (You may have to scroll down.)
    
    ![Selecionar gerenciar registros DNS avançados](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. Role para baixo até a seção **serviço (Registros SRV)** e selecione **Editar Registros SRV**.
    
    ![Selecione Editar Registros SRV em serviço](../../media/9a9248ea-5de5-4e16-9364-f7600fa371f5.png)
  
6. Nas caixas dos dois novos registros, digite ou copie e cole os valores da seguinte tabela.
    
    Escolha os valores **Serviço** e **Protocolo** nas listas suspensas. 
    
    |**Serviço**|**Protocolo**|**TTL**|**Prioridade**|**Espessura**|**Porta**|**Destino**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip  <br/> |_tls  <br/> |3600  <br/> |100  <br/> |1   <br/> |443  <br/> |sipdir.online.lync.com.  <br/> **Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)** <br/> |
    |_sipfederationtls  <br/> |_tcp  <br/> |3600  <br/> |100  <br/> |1   <br/> |5061  <br/> |sipfed.online.lync.com.  <br/> **This value MUST end with a period (.)** <br/> |
       
    ![Digitar ou colar valores dos novos registros](../../media/86968d1c-8e43-4e61-aeaa-37fc7d7ef7a7.png)
  
7. Selecione **continuar**.
    
    ![Selecione continuar](../../media/bfe2c778-5d2b-4bb6-a79d-c3ff9caf9e1e.png)
  
8. Selecione **salvar alterações**.
    
    ![Selecionar Salvar alterações](../../media/6d323126-0ebe-45ab-8567-c234711d84c7.png)
  
> [!NOTE]
>  Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md). 
  
