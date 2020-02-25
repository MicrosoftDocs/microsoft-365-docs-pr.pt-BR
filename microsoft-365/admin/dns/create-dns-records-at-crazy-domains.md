---
title: Criar registros DNS no site Crazy Domains para o Office 365
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
ms.assetid: 6386d63e-b78f-4736-90e7-b99a2c116a9f
description: Saiba como verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços em domínios malucos para o Office 365.
ms.openlocfilehash: 5b344ebdc4a4608c27c0a84299ea171391c09ba0
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42237869"
---
# <a name="create-dns-records-at-crazy-domains-for-office-365"></a>Criar registros DNS no site Crazy Domains para o Office 365

 **Caso não encontre o conteúdo que está procurando, [verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**. 
  
Se você usa a Crazy Domains como provedor de hospedagem DNS, realize os procedimentos deste artigo para verificar o domínio e configurar registros DNS para o Skype for Business Online, email e outros serviços.
  
Depois que você adicionar esses registros na Crazy Domains, o domínio será configurado para funcionar com os serviços do Office 365.
  
Para saber mais sobre hospedagem na Web e DNS para sites com o Office 365, confira [Usar um site público com o Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).
  
> [!NOTE]
> Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Adicionar um registro TXT para verificação
<a name="BKMK_verify"> </a>

Antes de usar o seu domínio com o Office 365, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro DNS prova ao Office 365 que você é o proprietário do domínio.
  
> [!NOTE]
> Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar. 
  
1. Para iniciar, acesse a sua página de domínios no usando [link](https://manage.crazydomains.com/members/domains/). Será solicitado que você faça logon primeiro.
    
    ![CrazyDomains-BP-configure-1-1](../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. Na seção **minha conta** , selecione **domínios**.
    
    ![CrazyDomains-BP-configure-1-2](../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. Na página **nomes de domínio** , na seção **domínio** , selecione o nome do domínio que você está atualizando. 
    
    ![CrazyDomains-BP-configure-1-3](../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. Na seção **configurações de DNS** , selecione o ícone de lista suspensa. 
    
    ![CrazyDomains-BP-configure-1-4-1](../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. Selecione **adicionar registro**.
    
    ![CrazyDomains-BP-configure-1-4-2](../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. Escolha **Registro TXT** na lista suspensa **Adicionar Registro**. 
    
    ![CrazyDomains-BP-Verify-1-1](../media/f0ffdefb-d7a5-47df-bb5e-bf8a3bcc9b01.png)
  
7. Selecione **Adicionar**.
    
    ![CrazyDomains-BP-Verify-1-2](../media/b0cd623a-67f7-4bae-a5b5-507f5a106123.png)
  
8. Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela.
    
    |**Subdomínio**|**Registro de Texto**|
    |:-----|:-----|
    |(Leave this field empty.)  <br/> |MS = ms *XXXXXXXX*  <br/> **Observação:** Este é um exemplo. Use aqui o valor específico de **Destino ou Pontos de Endereçamento**, retirado da tabela em Office 365.           [Como faço para encontrar isso?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![CrazyDomains-BP-Verify-1-3](../media/3867de97-6a98-4475-9bda-470bac75d483.png)
  
9. Selecione **Atualizar**.
    
    ![CrazyDomains-BP-Verify-1-4](../media/0e416df6-b7a2-4dd7-971c-f1cc31df30da.png)
  
10. Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.
    
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

1. Para iniciar, acesse a sua página de domínios no usando [link](https://manage.crazydomains.com/members/domains/). Será solicitado que você faça logon primeiro.
    
    ![CrazyDomains-BP-configure-1-1](../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. Na seção **minha conta** , selecione **domínios**.
    
    ![CrazyDomains-BP-configure-1-2](../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. Na página **nomes de domínio** , na seção **domínio** , selecione o nome do domínio que você está atualizando. 
    
    ![CrazyDomains-BP-configure-1-3](../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. Na seção **configurações de DNS** , selecione o ícone de lista suspensa. 
    
    ![CrazyDomains-BP-configure-1-4-1](../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. Selecione **adicionar registro**.
    
    ![CrazyDomains-BP-configure-1-4-2](../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. Escolha **Registro MX** na lista suspensa **Adicionar Registro:**. 
    
    ![CrazyDomains-BP-configure-2-1](../media/63f7ab77-e686-4e7b-a3a2-1ac28a02d5f3.png)
  
7. Selecione **Adicionar**.
    
    ![CrazyDomains-BP-configure-2-2](../media/a60680a1-2513-498c-b42f-8ffa575ee48e.png)
  
8. Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela.
    
    (Escolha o valor **prioridade** na lista suspensa.) 
    
    |**Email para a zona**|**Prioridade**|**Atribuído a um servidor**|
    |:-----|:-----|:-----|
    |(Deixe este campo vazio.)  <br/> |1  <br/> Para saber mais sobre prioridade, confira [O que é prioridade MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> | *\<chave-do-domínio\>*  .mail.protection.outlook.com  <br/> **Observação:** Obtenha sua * \<chave\> de domínio* de sua conta do Office 365.           [Como faço para encontrar isso?](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![CrazyDomains-BP-configure-2-3](../media/e27df6a6-19a6-4e58-9716-a74be1c3f8da.png)
  
9. Selecione **Atualizar**.
    
    ![CrazyDomains-BP-configure-2-4](../media/ba25cdef-a436-48bf-b0e9-5dffd03234a4.png)
  
10. Se houver outros registros MX listados na seção **registro MX** , selecione **Modificar** para um desses registros. 
    
    ![CrazyDomains-BP-configure-2-5](../media/9acdda39-33ec-4b24-ad83-91c26f9c599b.png)
  
11. Selecione **excluir**.
    
    ![CrazyDomains-BP-configure-2-6](../media/50b0e263-6f21-41b3-8fa0-7dd55dbe6c2e.png)
  
12. Selecione **Atualizar** para confirmar a exclusão. 
    
    ![CrazyDomains-BP-configure-2-7](../media/db751bfe-31c2-4632-a491-6893eda38a51.png)
  
13. Use o mesmo processo para remover outros registros MX na lista, até que somente o domínio que você adicionou anteriormente neste procedimento permaneça.
    
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a>Adicionar os seis registros CNAME necessários para o Office 365
<a name="BKMK_add_CNAME"> </a>

1. Para iniciar, acesse a sua página de domínios no usando [link](https://manage.crazydomains.com/members/domains/). Será solicitado que você faça logon primeiro.
    
    ![CrazyDomains-BP-configure-1-1](../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. Na seção **minha conta** , selecione **domínios**.
    
    ![CrazyDomains-BP-configure-1-2](../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. Na página **nomes de domínio** , na seção **domínio** , selecione o nome do domínio que você está atualizando. 
    
    ![CrazyDomains-BP-configure-1-3](../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. Na seção **configurações de DNS** , selecione o ícone de lista suspensa. 
    
    ![CrazyDomains-BP-configure-1-4-1](../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. Selecione **adicionar registro**.
    
    ![CrazyDomains-BP-configure-1-4-2](../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. Escolha **Registro CNAME** na lista suspensa **Adicionar Registro:**. 
    
    ![CrazyDomains-BP-configure-3-1](../media/2f02538b-fc79-46d2-a2b7-1022eaf0fb08.png)
  
7. Selecione **Adicionar**.
    
    ![CrazyDomains-BP-configure-3-2](../media/4c5929cf-1c21-4af9-899b-e36091f0f14d.png)
  
8. Adicione o primeiro dos seis registros CNAME.
    
    Nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir.
    
    |**Subdomínio**|**Alias para**|
    |:-----|:-----|
    |autodiscover  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
    ![CrazyDomains-BP-configure-3-3](../media/81a7b837-3f4d-4565-89a9-380e4d318acf.png)
  
9. Selecione **adicionar registro CNAME**.
    
    ![CrazyDomains-BP-configure-3-4](../media/9bcba729-7085-4ebc-8183-ecde82f5c364.png)
  
10. Adicione o segundo registro CNAME.
    
    Nas caixas do novo registro, use os valores da próxima linha na tabela e selecione novamente **adicionar registro CNAME**.
    
    Repita esse processo até ter criado todos os seis registros CNAME.
    
11. Selecione **Atualizar** para salvar suas alterações. 
    
    ![CrazyDomains-BP-configure-3-5](../media/dbe578f6-359c-428c-b296-ca624cecfc3c.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Adicionar registro TXT à SPF para ajudar a evitar spam de email
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. Em vez disso, adicione os valores necessários do Office 365 ao registro atual, de modo que você tenha um  *único*  registro SPF que inclua os dois conjuntos de valores. 
  
1. Para iniciar, acesse a sua página de domínios no usando [link](https://manage.crazydomains.com/members/domains/). Será solicitado que você faça logon primeiro.
    
    ![CrazyDomains-BP-configure-1-1](../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. Na seção **minha conta** , selecione **domínios**.
    
    ![CrazyDomains-BP-configure-1-2](../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. Na página **nomes de domínio** , na seção **domínio** , selecione o nome do domínio que você está atualizando. 
    
    ![CrazyDomains-BP-configure-1-3](../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. Na seção **configurações de DNS** , selecione o ícone de lista suspensa. 
    
    ![CrazyDomains-BP-configure-1-4-1](../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. Selecione **adicionar registro**.
    
    ![CrazyDomains-BP-configure-1-4-2](../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. Escolha **Registro TXT** na lista suspensa **Adicionar Registro:**. 
    
    ![CrazyDomains-BP-configure-4-1](../media/7f2461e2-0468-49bd-9eb0-981e9b2f72d6.png)
  
7. Selecione **Adicionar**.
    
    ![CrazyDomains-BP-configure-4-2](../media/64ef9e1f-676d-46e2-9253-a83d9bcd1c4e.png)
  
8. Nas caixas do novo registro, digite ou cole os valores da seguinte tabela.
    
    |**Subdomínio**|**Registro de Texto**|
    |:-----|:-----|
    |(Deixe este campo vazio.)  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Observação:** É recomendável copiar e colar essa entrada, para que todo o espaçamento permaneça correto.           |
   
    ![CrazyDomains-BP-configure-4-3](../media/e7fd524a-c94b-4cdd-b264-67abb532a71b.png)
  
9. Selecione **Atualizar**.
    
    ![CrazyDomains-BP-configure-4-4](../media/d4f378ee-0f14-46ae-ba32-1596660ecf91.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>Adicionar os dois registros SRV necessários para o Office 365
<a name="BKMK_add_SRV"> </a>

1. Para iniciar, acesse a sua página de domínios no usando [link](https://manage.crazydomains.com/members/domains/). Será solicitado que você faça logon primeiro.
    
    ![CrazyDomains-BP-configure-1-1](../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. Na seção **minha conta** , selecione **domínios**.
    
    ![CrazyDomains-BP-configure-1-2](../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. Na página **nomes de domínio** , na seção **domínio** , selecione o nome do domínio que você está atualizando. 
    
    ![CrazyDomains-BP-configure-1-3](../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. Na seção **configurações de DNS** , selecione o ícone de lista suspensa. 
    
    ![CrazyDomains-BP-configure-1-4-1](../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. Selecione **adicionar registro**.
    
    ![CrazyDomains-BP-configure-1-4-2](../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. Escolha **Registro SRV** na lista suspensa **Adicionar Registro:**. 
    
    ![CrazyDomains-BP-configure-5-1](../media/156acebc-7f6d-4b5e-8493-6bc62ca0ee27.png)
  
7. Selecione **Adicionar**.
    
    ![CrazyDomains-BP-configure-5-2](../media/6a711df7-4215-49b2-b58f-1cf1a242b383.png)
  
8. Adicione o primeiro dos dois registros SRV.
    
    Nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir.
    
    |**Tipo de Registro**|**Subdomínio**|**Prioridade**|**Peso**|**Porta**|**Destino**|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |Registro SRV  <br/> |_sip. _tls  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com  <br/> |
    |Registro SRV  <br/> |_sipfederationtls. _tcp  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com  <br/> |
   
    ![CrazyDomains-BP-configure-5-3](../media/cc0ea6eb-7358-434e-bd1a-2737725c6d41.png)
  
9. Selecione **adicionar registro SRV**.
    
    ![CrazyDomains-BP-configure-5-4](../media/de4ec312-6833-469a-b23a-f376140a35ca.png)
  
10. Adicione o outro registro SRV.
    
    Nas caixas para o novo registro, use os valores da segunda linha na tabela.
    
11. Selecione **Atualizar** para salvar suas alterações. 
    
    ![CrazyDomains-BP-configure-5-5](../media/f0bb1dd6-3772-4293-bf74-710f635e0658.png)
  
> [!NOTE]
> Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
