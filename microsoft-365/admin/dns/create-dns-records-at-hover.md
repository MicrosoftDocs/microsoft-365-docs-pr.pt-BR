---
title: Criar registros DNS no site Hover para o Office 365
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
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
ms.assetid: 46ab4b10-6857-44b1-b08d-d1b5f45a69c6
description: Saiba como verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços em foco para o Office 365.
ms.openlocfilehash: 54ff58963dcd66f692507f1d778fb9a8d24f82fa
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42238942"
---
# <a name="create-dns-records-at-hover-for-office-365"></a>Criar registros DNS no site Hover para o Office 365

 **Caso não encontre o conteúdo que está procurando, [verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**. 
  
Se você usa a Hover como provedor de hospedagem DNS, realize os procedimentos deste artigo para verificar o domínio e configurar registros DNS para o Skype for Business Online, email e outros serviços.
     
Depois que você adicionar esses registros à Hover, o domínio será configurado para funcionar com os serviços do Office 365.
  
Para saber mais sobre hospedagem na Web e DNS para sites com o Office 365, confira [Usar um site público com o Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).
  
> [!NOTE]
>  Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Adicionar um registro TXT para verificação
<a name="BKMK_verify"> </a>

Antes de usar o seu domínio com o Office 365, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro DNS prova ao Office 365 que você é o proprietário do domínio.
  
> [!NOTE]
> Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar. 
  
Siga as etapas abaixo ou [assista ao vídeo](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).
  
1. Para iniciar, vá até a página do seu domínio em Focalizar usando [este link](https://www.hover.com/domains). Você será solicitado a entrar.
    
    ![Entrar](../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. Em **gerenciar seus domínios**, selecione o nome do domínio que você deseja editar.
    
    ![Selecionar um domínio](../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. Selecione a guia **DNS** . 
    
    ![Selecione a guia DNS](../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. Selecione **Adicionar novo**.
    
    ![Selecione Adicionar novo](../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.
    
    ||||
    |:-----|:-----|:-----|
    |Nome do host  <br/> |Tipo de Registro  <br/> |Valor  <br/> |
    |@  <br/> |TXT  <br/> |MS = ms *XXXXXXXX*  <br/> **Observação:** Este é um exemplo. Use aqui o valor específico de **Destino ou Pontos de Endereçamento**, retirado da tabela em Office 365.           [Como faço para encontrar isso?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Digite ou copie e cole valores DNS](../media/3b0d19f9-4138-47a7-aab2-137ad120ded6.png)
  
6. Selecione **Salvar**.
    
    ![Selecione salvar](../media/07dcf68e-34be-47dc-999e-0216de68cc9c.png)
  
7. Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.
    
Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
  
When Office 365 finds the correct TXT record, your domain is verified.
  
1. No centro de administração, vá para a página de <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a> de **configurações** \> .
    
2. Na página **domínios** , selecione o domínio que você está verificando. 
    
    
  
3. Na página **configuração** , selecione **Iniciar configuração**.
    
    
  
4. Na página **verificar domínio** , selecione **verificar**.
    
    
  
> [!NOTE]
>  Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a>Adicionar um registro MX para que o email do domínio vá para o Office 365
<a name="BKMK_add_MX"> </a>

Siga as etapas abaixo ou [assista ao vídeo](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).
  
1. Para iniciar, vá até a página do seu domínio em Focalizar usando [este link](https://www.hover.com/domains). Você será solicitado a entrar.
    
    ![Entrar](../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. Em **gerenciar seus domínios**, selecione o nome do domínio que você deseja editar.
    
    ![Selecionar um domínio](../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. Selecione a guia **DNS** . 
    
    ![Selecione a guia DNS](../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. Selecione **Adicionar novo**.
    
    ![Selecione Adicionar novo](../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. Nas caixas do novo registro, selecione **MX** como o **Tipo de Registro** e digite ou copie e cole os valores da tabela a seguir.
    
    |**Nome do host**|**Tipo de Registro**|**Prioridade**|**Nome do host**|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |MX  <br/> |,0  <br/> Para saber mais sobre prioridade, confira [O que é prioridade MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> | *\<chave-do-domínio\>*  .mail.protection.outlook.com  <br/> **Observação:** Obtenha sua * \<chave\> de domínio* de sua conta do Office 365.           [Como faço para encontrar isso?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Digite ou copie e cole valores DNS](../media/2c8915fa-04a8-4d2a-a8ae-a79de0c8ef99.png)
  
6. Selecione **Salvar**.
    
    ![Selecione salvar](../media/266c30a4-6703-48fb-a919-b510ed966193.png)
  
7. Se houver outros registros MX, use o processo de duas etapas a seguir para remover cada um deles:
    
    Primeiro, passe sobre um registro que você deseja remover, selecione **excluir**.
    
    ![Passe o mouse e selecione Excluir](../media/2ddf4902-8cd2-4969-a418-2cb592741e86.png)
  
    Em segundo lugar, selecione **Sim** para confirmar cada exclusão. 
    
    ![Selecione Sim para confirmar a exclusão](../media/48756bd5-0205-4c4d-9803-9246795dbf4a.png)
  
    Repita esse processo até excluir todos os registros MX, exceto para aquele adicionado anteriormente neste procedimento.
    
## <a name="add-the-cname-records-that-are-required-for-office-365"></a>Adicionar os registros CNAME necessários para o Office 365
<a name="BKMK_add_CNAME"> </a>

Siga as etapas abaixo ou [assista ao vídeo](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).
  
1. Para iniciar, vá até a página do seu domínio em Focalizar usando [este link](https://www.hover.com/domains). Você será solicitado a entrar.
    
    ![Entrar](../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. Em **gerenciar seus domínios**, selecione o nome do domínio que você deseja editar.
    
    ![Selecionar um domínio](../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. Selecione a guia **DNS** . 
    
    ![Selecione a guia DNS](../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. Adicione o primeiro dos seis registros CNAME.
    
    Selecione **Adicionar novo**.
    
    ![Selecione Adicionar novo](../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. Nas caixas vazias do novo registro, selecione **CNAME** como o **Tipo de Registro** e digite ou copie e cole os valores da tabela a seguir.
    
    |**Nome do host**|**Tipo de Registro**|**Host de Destino**|
    |:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |CNAME  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
    ![Digite ou copie e cole valores DNS](../media/6ae607f8-d26e-47f0-a0f2-3487d37e8c7f.png)
  
6. Selecione **Salvar**.
    
    ![Selecione salvar](../media/69aa3546-32de-4c17-a2e2-8c0cd133efaa.png)
  
7. Usando as três etapas anteriores e os valores das outras cinco linhas da tabela, adicione cada um dos outros cinco registros CNAME.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Adicionar registro TXT à SPF para ajudar a evitar spam de email
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. Em vez disso, adicione os valores necessários do Office 365 ao registro atual, de modo que você tenha um  *único*  registro SPF que inclua os dois conjuntos de valores. 
  
Siga as etapas abaixo ou [assista ao vídeo](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).
  
1. Para iniciar, vá até a página do seu domínio em Focalizar usando [este link](https://www.hover.com/domains). Você será solicitado a entrar.
    
    ![Entrar](../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. Em **gerenciar seus domínios**, selecione o nome do domínio que você deseja editar.
    
    ![Selecionar um domínio](../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. Selecione a guia **DNS** . 
    
    ![Selecione a guia DNS](../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. Selecione **Adicionar novo**.
    
    ![Selecione Adicionar novo](../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.
    
    |**Nome do host**|**Tipo de Registro**|**Valor**|
    |:-----|:-----|:-----|
    |@  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/>**Observação:** É recomendável copiar e colar essa entrada, para que todo o espaçamento permaneça correto.           |
   
    ![Digite ou copie e cole valores DNS](../media/ed36b9e0-aaa9-45fb-804d-7d4e82ba0c7f.png)
  
6. Selecione **Salvar**.
    
    ![Selecione salvar](../media/13a395b9-e0e8-4393-b568-5f99b2da39da.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>Adicionar os dois registros SRV necessários para o Office 365
<a name="BKMK_add_SRV"> </a>

Siga as etapas abaixo ou [assista ao vídeo](https://support.office.com/article/Video-Create-DNS-records-at-Hover-for-Office-365-182bd58e-8fe4-4717-9233-3a3546b72ad2?ui=en-US&amp;rs=en-US&amp;ad=US).
  
1. Para iniciar, vá até a página do seu domínio em Focalizar usando [este link](https://www.hover.com/domains). Você será solicitado a entrar.
    
    ![Entrar](../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. Em **gerenciar seus domínios**, selecione o nome do domínio que você deseja editar.
    
    ![Selecionar um domínio](../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. Selecione a guia **DNS** . 
    
    ![Selecione a guia DNS](../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. Adicione o primeiro dos dois registros SRV.
    
    Selecione **Adicionar novo**.
    
    ![Selecione Adicionar novo](../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. Nas caixas vazias do novo registro, selecione **SRV** como o **Tipo de Registro** e digite ou copie e cole os valores da primeira linha na tabela a seguir.
    
    |**Nome do host**|**Tipo de Registro**|**Prioridade**|**Peso**|**Porta**|**Destino**|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip. _tls  <br/> |SRV  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
    |_sipfederationtls. _tcp  <br/> |SRV  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com  <br/> |
   
    ![Digite ou copie e cole valores DNS](../media/67562cd6-c598-4c37-af53-626f153c0197.png)
  
6. Selecione **Salvar**.
    
    ![Selecione salvar](../media/0d7ec216-9277-4709-b637-e94c8662730f.png)
  
7. Usando as três etapas anteriores e os valores da segunda linha da tabela, adicione o outro registro SRV.
    
> [!NOTE]
> Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
