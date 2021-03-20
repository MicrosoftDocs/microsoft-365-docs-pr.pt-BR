---
title: Criar registros DNS no OVH para a Microsoft
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
ms.assetid: 5176feef-36dc-4d84-842f-1f2b5a21ba96
description: Aprenda a verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços na OVH para Microsoft.
ms.openlocfilehash: a43593af80d2f651e4407de64ed9aab51f1c1ecb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910061"
---
# <a name="create-dns-records-at-ovh-for-microsoft"></a>Criar registros DNS no OVH para a Microsoft

Caso não encontre o conteúdo que está procurando, [verifique as perguntas frequentes sobre domínios](../setup/domains-faq.yml). 
  
Se o OVH for seu provedor de hospedagem DNS, siga as etapas deste artigo para verificar seu domínio e configurar registros DNS para email, Skype for Business Online e assim por diante.
  
Esses são os principais registros a adicionar. 
  
- [Criar registros DNS no OVH para a Microsoft](#create-dns-records-at-ovh-for-microsoft)
    
- [Adicione um registro MX para que o email do domínio vá para a Microsoft.](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [Adicionar os registros CNAME necessários para a Microsoft](#add-the-cname-records-that-are-required-for-microsoft)
    
- [Adicionar registro TXT à SPF para ajudar a evitar spam de email](#add-a-txt-record-for-spf-to-help-prevent-email-spam)
    
- [Adicionar os dois registros SRV necessários para a Microsoft](#add-the-two-srv-records-that-are-required-for-microsoft)
    
Depois de adicionar esses registros no OVH, seu domínio será definido para funcionar com os serviços da Microsoft.

  
> [!NOTE]
>  Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Adicionar um registro TXT para verificação
<a name="bkmk_txt"> </a>

Antes de usar o seu domínio com a Microsoft, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro de DNS prova à Microsoft que você é o proprietário do domínio.
  
> [!NOTE]
> Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar. 
  
1. Para começar, vá para sua página de domínios no OVH usando [este link](https://www.ovh.com/manager/). You'll be prompted to log in.
    
    ![Logon OVH](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. Em **Domínios,** selecione o nome do domínio que você deseja editar.
    
    ![OVH Selecione o domínio](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. Selecione **zona DNS**.
    
    ![OVH selecione zona DNS](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. Selecione **Adicionar uma entrada**.
    
    ![OVH Adicionar uma entrada](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. Selecione **TXT**
    
    ![OVH selecione entrada TXT](../../media/3aaa9dae-0b1d-436b-a980-b67a970f31a9.png)
  
6. Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela. Para atribuir um valor TTL, escolha **Personalizado na** listada e digite o valor na caixa de texto. 
    
    |**Tipo de registro**|**Sub-domínio**|**TTL**|**Valor**|
    |:-----|:-----|:-----|:-----|
    |TXT  <br/> |(deixar em branco)  <br/> |3600 (segundos)  <br/> |MS=msxxxxxxxx  <br/> **Observação**: esse é um exemplo. Use aqui seu valor específico de **Destino ou Pontos de Endereçamento**, retirado da tabela.           [Como localizo isto?](../get-help-with-domains/information-for-dns-records.md)          |
   
7. Selecione **Confirmar**. 
    
    ![OVH confirmar TXT para verificação](../../media/bde45596-9a55-4634-b5e7-16d7cde6e1b8.png)
  
8. Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.
    
Agora que você adicionou o registro no site do seu registrador de domínios, retorne à Microsoft e solicite o registro.
  
Quando a Microsoft encontrar o registro TXT correto, seu domínio estará verificado.
  
1. No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.
    
2. Na página **Domínios**, clique no domínio que você está verificando. 
    
    
  
3. Na página **Configuração**, clique em **Iniciar configuração**.
    
    
  
4. Na página **Verificar domínio**, marque **Verificar**.
    
    
  
> [!NOTE]
>  Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Adicione um registro MX para que o email do domínio vá para a Microsoft.
<a name="bkmk_mx"> </a>

1. Para começar, vá para sua página de domínios no OVH usando [este link](https://www.ovh.com/manager/). You'll be prompted to log in.
    
    ![Logon OVH](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. Em **Domínios,** selecione o nome do domínio que você deseja editar.
    
    ![OVH Selecione o domínio](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. Selecione **zona DNS**.
    
    ![OVH selecione zona DNS](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. Selecione **Adicionar uma entrada**.
    
    ![OVH Adicionar uma entrada](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. Selecione **MX**.
    
    ![Tipo de registro OVH MX](../../media/29b5e54e-440a-41f2-9eb9-3de573922ddf.png)
  
6. Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela. Para atribuir um valor TTL, escolha **Personalizado na** listada e digite o valor na caixa de texto. 
    
    > [!NOTE]
    > Por padrão, o OVH usa notação relativa para o destino, que adiciona o nome de domínio ao final do registro de destino. Para usar a notação absoluta, adicione um ponto ao registro de destino, conforme mostrado na tabela abaixo. 
  
    |**Tipo de registro**|**Sub-domínio**|**TTL**|**Prioridade**|**Target**|
    |:-----|:-----|:-----|:-----|:-----|
    |MX  <br/> |(deixar em branco)  <br/> |3600 (segundos)  <br/> |10   <br/> Para saber mais sobre prioridade, confira [O que é prioridade MX?](../setup/domains-faq.yml) <br/> |\<domain-key\>.mail.protection.outlook.com.  <br/> **Observação:** Obter o  *\<domain-key\>*  seu de sua conta da Microsoft.  [Como localizo isto?](../get-help-with-domains/information-for-dns-records.md)  |
   
    ![Registro OVH MX para email](../../media/6e2f5655-93e2-4620-8f19-c452e7edf8f0.png)
  
7. Selecione **Avançar**.
    
    ![Registro OVH MX selecione Next](../../media/4db62d07-0dc4-49f6-bd19-2b4a07fd764a.png)
  
8. Selecione **Confirmar**.
    
    ![Registro OVH MX selecione Confirmar](../../media/090bfb11-a753-4af0-8982-582a4069a169.png)
  
9. Se houver outros registros MX, exclua-os todos na lista na página **de zona DNS.** Selecione cada registro e, na coluna **Ações,**  selecione o ícone Excluir lixeira. 
    
    ![OVH excluir registro MX](../../media/892b328b-7057-4828-b8c5-fe26284dc8c2.png)
  
10. Selecione **Confirmar**.
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a>Adicionar os registros CNAME necessários para a Microsoft
<a name="bkmk_cname"> </a>

1. Para começar, vá para sua página de domínios no OVH usando [este link](https://www.ovh.com/manager/). You'll be prompted to log in.
    
    ![Logon OVH](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. Em **Domínios,** selecione o nome do domínio que você deseja editar.
    
    ![OVH Selecione o domínio](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. Selecione **zona DNS**.
    
    ![OVH selecione zona DNS](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. Selecione **Adicionar uma entrada**.
    
    ![OVH Adicionar uma entrada](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. Selecione **CNAME**.
    
    ![OVH adicionar tipo de registro CNAME](../../media/33c7ac74-18d7-4ae1-9e27-1c0f9773a3c3.png)
  
6. Criar o primeiro registro CNAME.
    
    Nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir. Para atribuir um valor TTL, escolha **Personalizado na** listada e digite o valor na caixa de texto. 
    
    |**Tipo de registro**|**Sub-domínio**|**Destino**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |CNAME  <br/> |autodiscover  <br/> |autodiscover.outlook.com.  <br/> |3600 segundos  <br/> |
    |CNAME  <br/> |sip  <br/> |sipdir.online.lync.com.  <br/> |3600 segundos  <br/> |
    |CNAME  <br/> |lyncdiscover  <br/> |webdir.online.lync.com.  <br/> |3600 segundos  <br/> |
    |CNAME  <br/> |enterpriseregistration  <br/> |enterpriseregistration.windows.net.  <br/> |3600 segundos  <br/> |
    |CNAME  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> |3600 segundos  <br/> |
   
    ![Registro CNAME OVH](../../media/516938b3-0b12-4736-a631-099e12e189f5.png)
  
7. Selecione **Avançar**.
    
    ![OVH Adicionar valores CNAME e selecione Next](../../media/f9481cb1-559d-4da1-9643-9cacb0d80d29.png)
  
8. Selecione **Confirmar**.
    
9. Repita as etapas anteriores para criar os outros cinco registros CNAME.
    
    Para cada registro, digite ou copie e copie os valores da próxima linha da tabela acima nas caixas desse registro.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail
<a name="bkmk_spf"> </a>

> [!IMPORTANT]
> Não é possível ter mais de um registro TXT para SPF para um domínio. Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam. Se você já possui um registro SPF para seu domínio, não crie um novo para a Microsoft. Em vez disso, adicione os valores necessários da Microsoft ao registro atual para que você tenha um único registro  *SPF*  que inclua ambos os conjuntos de valores. 
  
1. Para começar, vá para sua página de domínios no OVH usando [este link](https://www.ovh.com/manager/). You'll be prompted to log in.
    
    ![Logon OVH](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. Em **Domínios,** selecione o nome do domínio que você deseja editar.
    
    ![OVH Selecione o domínio](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. Selecione **zona DNS**.
    
    ![OVH selecione zona DNS](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. Selecione **Adicionar uma entrada**.
    
    ![OVH Adicionar uma entrada](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. Selecione **TXT**.
    
6. In the boxes for the new record, type or copy and paste the following values.
    
    |**Tipo de registro**|**Sub-domínio**|**TTL**|**Valor TXT**|
    |:-----|:-----|:-----|:-----|
    |TXT  <br/> |(deixar em branco)  <br/> |3600 (segundos)  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.           |
   
    ![OVH Adicionar registro TXT para SPF](../../media/f50466e9-1557-4548-8a39-e98978a5ee2e.png)
  
7. Selecione **Avançar**.
    
    ![OVH Adicionar registro TXT para SPF e selecione Next](../../media/7937eb7c-114f-479f-a916-bcbe476d6108.png)
  
8. Selecione **Confirmar**.
    
    ![OVH Adicionar registro TXT para SPF e Confirmar](../../media/649eefeb-3227-49e3-98a0-1ce19c42fa54.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Adicionar os dois registros SRV necessários para a Microsoft
<a name="bkmk_srv"> </a>

1. Para começar, vá para sua página de domínios no OVH usando [este link](https://www.ovh.com/manager/). You'll be prompted to log in.
    
    ![Logon OVH](../../media/1424cc15-720d-49d1-b99b-8ba63b216238.png)
  
2. Em **Domínios,** selecione o nome do domínio que você deseja editar.
    
    ![OVH Selecione o domínio](../../media/fe407909-4ea6-4b92-a3bd-dec4022b1d8d.png)
  
3. Selecione **zona DNS**.
    
    ![OVH selecione zona DNS](../../media/45218cbe-f3f8-4804-87f9-cfcef89ea113.png)
  
4. Selecione **Adicionar uma entrada**.
    
    ![OVH Adicionar uma entrada](../../media/13ded54b-9e48-4c98-8e1b-8c4a99633bc0.png)
  
5. Selecione **SRV**.
    
    ![Tipo de registro SRV selecionado OVH](../../media/66bad536-a531-4a4e-b08d-c0d99f6ea1b2.png)
  
6. Crie o primeiro registro SRV.
    
    Nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir. Para atribuir um valor TTL, escolha **Personalizado na** listada e digite o valor na caixa de texto. 
    
    |**Tipo de registro**|**Sub-domínio**|**Prioridade**|**Espessura**|**Porta**|**TTL**|**Target**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV (Serviço)  <br/> |_sip._tls  <br/> |100  <br/> |1  <br/> |443  <br/> |3600 (segundos)  <br/> |sipdir.online.lync.com.  <br/> |
    |SRV (Serviço)  <br/> |_sipfederationtls._tcp  <br/> |100  <br/> |1  <br/> |5061  <br/> |3600 (segundos)  <br/> |sipfed.online.lync.com.  <br/> |
       
    ![Registro SRV OVH](../../media/73956b9e-9e4f-40a5-803e-c4ead2f77fa6.png)
  
7. Selecione **Avançar**.
    
    ![Registro SRV OVH selecione Next](../../media/cb4ad7e2-a8f0-4ab1-9797-d1b51c1d2da9.png)
  
8. Selecione **Confirmar**.
    
9. Repita as etapas anteriores para criar o outro registro SRV. Digite ou copie e cole os valores da segunda linha da tabela acima nas caixas do segundo registro.
    
> [!NOTE]
>  Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
