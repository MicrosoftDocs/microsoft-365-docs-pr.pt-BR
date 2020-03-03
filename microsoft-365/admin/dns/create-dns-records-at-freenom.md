---
title: Criar registros DNS no Freenom para o Office 365
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
ms.assetid: d8ff45a2-19e3-413d-aa64-a9982bd6633c
description: Saiba como verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços em Freenom para o Office 365.
ms.openlocfilehash: 16348eb03a6507e15d31d5c183bd91125d0236f6
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/02/2020
ms.locfileid: "42350662"
---
# <a name="create-dns-records-at-freenom-for-office-365"></a>Criar registros DNS no Freenom para o Office 365

[Verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md) se não encontrar o que você está procurando. 
  
> [!CAUTION]
> O site do Freenom não dá suporte a registros SRV, o que significa que vários recursos do Skype for Business Online e do Outlook Web App não funcionarão. Independentemente do plano do Office 365 que você usa, há limitações de serviço significativas e você pode querer mudar para um provedor de Hospedagem de DNS diferente. 
  
Se, apesar das limitações de serviço, você optar por gerenciar seus próprios registros DNS do Office 365 no Freenom, siga as etapas deste artigo para verificar seu domínio e configurar registros DNS para email e outros serviços.
  
Para saber mais sobre hospedagem na Web e DNS para sites com o Office 365, confira [Usar um site público com o Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).
  
> [!NOTE]
> Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Adicionar um registro TXT para verificação
<a name="bkmk_txt"> </a>

Antes de usar o seu domínio com o Office 365, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro DNS prova ao Office 365 que você é o proprietário do domínio.
  
> [!NOTE]
> Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar. 
  
1. Para começar, vá até a sua página de domínios no Freenom usando [este link](https://my.freenom.com/). You'll be prompted to log in.
    
    ![Login do Freenom](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. Selecione **Serviços**e, em seguida, selecione **meus domínios**.
    
    ![Freenom selecionar serviços e meus domínios](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. Para o domínio que você deseja editar, selecione **gerenciar domínio**.
    
    ![Freenom selecionar Gerenciar domínio](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. Selecione **gerenciar FREENOM DNS**.
    
    ![Freenom gerenciar Freenom DNS](../../media/9854a511-27e3-4658-8903-34b3d425096d.png)
  
5. Em **adicionar registro**, na coluna **tipo** , escolha **txt** no menu. 
    
    ![Freenom adicionar tipo de registro TXT](../../media/7f0e85e7-844f-4962-815e-5d80d9e6efa0.png)
  
6. Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela. 
    
    |**Nome**|**Tipo**|**TTL**|**Destino**|
    |:-----|:-----|:-----|:-----|
    |(deixar em branco)  <br/> |TXT  <br/> |3600 (segundos)  <br/> |MS = msXXXXXXXX  <br/> **Observação**: esse é um exemplo. Use seu valor específico de **Destinos ou Pontos de Endereçamento** aqui, da tabela no Office 365.           [Como localizo isto?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Freenom valores TXT para verificação](../../media/650098df-b3aa-47e5-9763-7fde24e34c3f.png)
  
7. Selecione **salvar alterações**.
    
    ![Registro TXT do Freenom salvar alterações](../../media/b1a63f9a-4578-491a-9554-c40f73b37e09.png)
  
8. Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.
    
Agora que você adicionou o registro no site do seu registrador de domínios, retorne ao Office 365 e solicite que o Office 365 procure o registro.
  
Quando o Office 365 encontrar o registro TXT correto, o domínio será verificado.
  
1. No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.

    
2. Na página **Domínios**, clique no domínio que você está verificando. 
    
    
  
3. Na página **Configuração**, clique em **Iniciar configuração**.
    
    
  
4. Na página **Verificar domínio**, marque **Verificar**.
    
    
  
> [!NOTE]
>  Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a>Adicionar um registro MX para que o e-mail do domínio vá para o Office 365
<a name="bkmk_mx"> </a>

1. Para começar, vá até a sua página de domínios no Freenom usando [este link](https://my.freenom.com/). You'll be prompted to log in.
    
    ![Login do Freenom](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. Selecione **Serviços**e, em seguida, selecione **meus domínios**.
    
    ![Freenom selecionar serviços e meus domínios](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. Para o domínio que você deseja editar, selecione **gerenciar domínio**.
    
    ![Freenom selecionar Gerenciar domínio](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. Definir o nome serve para o seu domínio para os servidores de nomes padrão do Freenom. Selecione **ferramentas de gerenciamento**e, em seguida, selecione **nameservers**.
    
    ![Configuração de nameservers do Freenom](../../media/a6ae877a-c248-42b9-bae9-210a80cd01e7.png)
  
5. Certifique-se de que **usar nameservers padrão** está selecionado e selecione **alterar nameservers**.
    
    ![Freenom alterar nameservers](../../media/0ef90d84-c0a0-4ef9-9e4c-43ef0aac3a2e.png)
  
6. Selecione **gerenciar FREENOM DNS**.
    
    ![Freenom selecione Gerenciar Freenom DNS](../../media/f55a8053-2411-45da-a357-776c6699f721.png)
  
7. Em **adicionar registro**, na coluna **tipo** , escolha **MX** no menu. 
    
    ![Freenom adicionar tipo de registro MX](../../media/c728c6ee-786c-4f6a-8ad5-1d9914a5bfcf.png)
  
8. Nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir. 
    
    |**Nome**|**Tipo**|**TTL**|**Destino**|**Prioridade**|
    |:-----|:-----|:-----|:-----|:-----|
    |(deixar em branco)  <br/> |Servidor de mensagens (MX)  <br/> |3600 (segundos)  <br/> |\<Domain-Key\>. mail.Protection.Outlook.com  <br/> **Observação:** Obtenha sua * \<chave\> de domínio* de sua conta do Office 365.   [Como faço para encontrar isso?](../get-help-with-domains/information-for-dns-records.md)          |10   <br/> Para saber mais sobre prioridade, confira [O que é prioridade MX?](https://support.office.com/article/17d415c1-067e-4974-84d5-aaeaf3a0c0a9) <br/> |
   
   ![Registro MX Freenom](../../media/8896c4a9-b3dd-45ed-9916-f7da2715ba8c.png)
  
9. Selecione **salvar alterações**.
    
    ![Registro MX Freenom salvar alterações](../../media/7aa0a464-d136-417f-be40-48d3f728eeb7.png)
  
10. Se houver outros registros MX, exclua todos. Para cada registro, selecione **excluir**. Quando a mensagem **você realmente deseja remover essa entrada?** é exibida, selecione **OK**.
    
## <a name="add-the-cname-records-that-are-required-for-office-365"></a>Adicionar os registros CNAME necessários do Office 365
<a name="bkmk_cname"> </a>

1. Para começar, vá até a sua página de domínios no Freenom usando [este link](https://my.freenom.com/). You'll be prompted to log in.
    
    ![Login do Freenom](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. Selecione **Serviços**e, em seguida, selecione **meus domínios**.
    
    ![Freenom selecionar serviços e meus domínios](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. Para o domínio que você deseja editar, selecione **gerenciar domínio**.
    
    ![Freenom selecionar Gerenciar domínio](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. Selecione **gerenciar FREENOM DNS**.
    
    ![Freenom selecione Gerenciar Freenom DNS](../../media/5e7bc3a7-0d5e-431b-bb27-da3b0f316d01.png)
  
5. Em **adicionar registro**, na coluna **tipo** , escolha **CNAME** no menu. 
    
    ![Freenom adicionar tipo de registro CNAME](../../media/9b204755-ca2a-46d2-bce2-030d82fd1f9e.png)
  
6. Criar o primeiro registro CNAME. Nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir. 
    
    |**Nome**|**Tipo de registro**|**TTL**|**Destino**|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |3600 (segundos)  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |CNAME  <br/> |3600 (segundos)  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |3600 (segundos)  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |3600 (segundos)  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |3600 (segundos)  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
    ![Freenom valores CNAME](../../media/752fc682-e3f2-4b9c-9253-bf1ba2d414e9.png)
  
7. Selecione **salvar alterações**.
    
    ![Freenom CNAME salvar alterações](../../media/68103fd2-0f5f-4aac-a875-25157c6bbdd2.png)
  
8. Repita as etapas anteriores para criar os outros cinco registros CNAME. 
    
    Para cada registro, digite ou copie e cole os valores da próxima linha da tabela acima nas caixas desse registro.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail
<a name="bkmk_spf"> </a>

> [!IMPORTANT]
> Não é possível ter mais de um registro TXT para SPF para um domínio. Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam. If you already have an SPF record for your domain, don't create a new one for Office 365. Em vez disso, adicione os valores necessários do Office 365 ao registro atual, de modo que você tenha um  *único*  registro SPF que inclua os dois conjuntos de valores. 

1. Para começar, vá até a sua página de domínios no Freenom usando [este link](https://my.freenom.com/). You'll be prompted to log in.
    
    ![Login do Freenom](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. Selecione **Serviços**e, em seguida, selecione **meus domínios**.
    
    ![Freenom selecionar serviços e meus domínios](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. Para o domínio que você deseja editar, selecione **gerenciar domínio**.
    
    ![Freenom selecionar Gerenciar domínio](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. Selecione **gerenciar FREENOM DNS**.
    
    ![Freenom selecione Gerenciar Freenom DNS](../../media/94809955-0315-409c-a15d-703a2fe4c4ed.png)
  
5. Em **adicionar registro**, na coluna **tipo** , escolha **txt** no menu. 
    
    ![Freenom adicionar tipo de registro TXT](../../media/d8854285-c4ae-416c-a072-72a11ba1cd9a.png)
  
6. In the boxes for the new record, type or copy and paste the following values. 
    
    |**Name**|**Tipo de registro**|**TTL**|**Destino**|
    |:-----|:-----|:-----|:-----|
    |(deixar em branco)  <br/> |TXT  <br/> |3600 (segundos)  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/>**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.           |
   
    ![Freenom valores TXT para SPF](../../media/1b3b1199-9104-4ca1-acdb-786d139c21ac.png)
  
7. Selecione **salvar alterações**.
    
    ![Freenom registro TXT para alterações de salvamento de SPF](../../media/e2fc52b1-0dcb-4595-9a4c-fca5e2ef9f97.png)
  

