---
title: Criar registros DNS no WiX para Microsoft
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
ms.assetid: 7173c635-58b3-400f-95e0-97abe915565e
description: Saiba como verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços em WiX para a Microsoft.
ms.openlocfilehash: 6f88cc65ae19f747a9fc3740ea1578f30d18b5e2
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2020
ms.locfileid: "44048850"
---
# <a name="create-dns-records-at-wix-for-microsoft"></a>Criar registros DNS no WiX para Microsoft

 Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**. 
  
Se o WiX for o seu provedor de hospedagem DNS, siga as etapas deste artigo para verificar seu domínio e configurar registros DNS para email, Skype for Business Online e assim por diante.
  
Esses são os principais registros a adicionar. 
  
- [Adicionar um registro txt para verificação](#add-a-txt-record-for-verification).
    
- [Adicionar um registro MX para que o email do seu domínio seja fornecido para a Microsoft](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft).
    
- [Adicione os cinco registros CNAME necessários para a Microsoft](#add-the-five-cname-records-that-are-required-for-microsoft).
    
- [Adicione um registro txt para o SPF para ajudar a evitar spam de email](#add-a-txt-record-for-spf-to-help-prevent-email-spam).
    
- [Adicione os dois registros SRV necessários para a Microsoft](#add-the-two-srv-records-that-are-required-for-microsoft).
    
Depois que você adicionar esses registros no WiX, o domínio será configurado para funcionar com os serviços da Microsoft.
  
> [!NOTE]
>  Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Adicionar um registro TXT para verificação
<a name="BKMK_txt"> </a>

Antes de usar o seu domínio com a Microsoft, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro de DNS prova à Microsoft que você é o proprietário do domínio.
  
> [!NOTE]
> Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar. 
  
1. Para começar, vá até a sua página de domínios no WiX usando [este link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). Será solicitado que você faça logon primeiro.
    
2. Na página **meus domínios** , na área **avançado** , selecione o botão **Editar DNS** . 
    
3. Selecione **+ Adicionar outro** na linha **txt (texto)** do editor DNS. 
    
4. In the boxes for the new record, type or copy and paste the values from the following table. 
    
||||
|:-----|:-----|:-----|
|**Host Name** <br/> |**Valor TXT** <br/> |**TTL** <br/> |
|Preenchido automaticamente  <br/> |MS = ms *XXXXXXXX*  <br/> **Observação**: esse é um exemplo. Use aqui seu valor específico de **Destino ou Pontos de Endereçamento**, retirado da tabela.  [Como localizo isto?](../get-help-with-domains/information-for-dns-records.md)|1 Hour <br/> |          |
   
5. Selecione o botão **salvar DNS** na parte superior do editor de DNS. 
    
6. Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.
    
Agora que você adicionou o registro no site do seu registrador de domínios, retorne à Microsoft e solicite o registro.
  
Quando a Microsoft encontrar o registro TXT correto, seu domínio estará verificado.
  
1. No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.
    
2. Na página **Domínios**, clique no domínio que você está verificando. 
  
  
3. Na página **Configuração**, clique em **Iniciar configuração**.
   
  
4. Na página **Verificar domínio**, marque **Verificar**.
    
    
  
> [!NOTE]
>  Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Adicione um registro MX para que o email do domínio vá para a Microsoft.
<a name="BKMK_mx"> </a>

1. Para começar, vá até a sua página de domínios no WiX usando [este link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). Será solicitado que você faça logon primeiro.
    
2. Na página **meus domínios** , na área **caixas de correio** , selecione o link **configurar seus registros MX** . 
    
3. Escolha **outro** na lista suspensa **provedor de email** . 
    
4. Selecione **+ Adicionar outro**.
    
5. Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela:
    
|**Host Name**|**Aponta para**|**Prioridade**|**TTL**|
|:-----|:-----|:-----|:-----|
|Preenchido automaticamente <br/> | *\<chave-do-domínio\>*  .mail.protection.outlook.com  <br/> **Observação:** Obtenha sua * \<chave\> de domínio* de sua conta da Microsoft.   [Como faço para encontrar isso?](../get-help-with-domains/information-for-dns-records.md) |,0  <br/> Para saber mais sobre prioridade, confira [O que é prioridade MX?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) | 1 Hour|
   
6. Se houver outros registros MX listados, exclua cada um deles. 
    
7. Clique em **OK**.
    
8. Na caixa de diálogo de confirmação, selecione **OK**.
    
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a>Adicionar os cinco registros CNAME necessários para o Microsoft
<a name="BKMK_cname"> </a>

1. Para começar, vá até a sua página de domínios no WiX usando [este link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). You'll be prompted to login first.
    
2. Na página **meus domínios** , na área **avançado** , selecione o botão **Editar DNS** . 
    
3. Selecione **+ Adicionar outro** na linha **CNAME (alias)** do editor DNS para cada registro CNAME. 
    
4. Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela:
    
|**Host Name**|**Pontos de**|**TTL**|
|:-----|:-----|:-----|
|descoberta automática  <br/> |autodiscover.outlook.com  <br/> |1 Hour  <br/> |
|sip  <br/> |sipdir.online.lync.com  <br/> |1 Hour <br/> |
|lyncdiscover  <br/> |webdir.online.lync.com   <br/> |1 Hour  <br/> |
|enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |1 hora <br/> |
|enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |1 Hour  <br/> |
   
5. Selecione o botão **salvar DNS** na parte superior do editor de DNS. 
    
6. Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail
<a name="BKMK_spf"> </a>

> [!IMPORTANT]
> Não é possível ter mais de um registro TXT para SPF para um domínio. Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam. Se você já possui um registro SPF para seu domínio, não crie um novo para a Microsoft. Em vez disso, adicione os valores necessários da Microsoft ao registro atual para que você tenha um *único* registro SPF que inclua os dois conjuntos de valores.  
  
1. Para começar, vá até a sua página de domínios no WiX usando [este link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). Será solicitado que você faça logon primeiro.
    
2. Na página **meus domínios** , na área **avançado** , selecione o botão **Editar DNS** . 
    
3. Selecione **+ Adicionar outro** na linha **txt (texto)** do editor DNS. 
    
4. Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela:
    
|**Host Name**|**Valor TXT**|**TTL**|
|:-----|:-----|:-----|
|[deixe em branco]  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.<br/> |TXT  <br/> | 1 Hour |
   
5. Selecione o botão **salvar DNS** na parte superior do editor de DNS. 
    
6. Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Adicionar os dois registros SRV necessários para a Microsoft
<a name="BKMK_srv"> </a>

1. Para começar, vá até a sua página de domínios no WiX usando [este link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). Será solicitado que você faça logon primeiro.
    
2. Na página **meus domínios** , na área **avançado** , selecione o botão **Editar DNS** . 
    
3. Selecione **+ Adicionar outro** na linha **SRV** do editor de DNS. 
    
4. Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela:
    
|**Serviço**|**Protocolo**|**Nome**|**Espessura**|**Porta**|**Destino**|**Prioridade**|**TTL**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|sip  |tls  |Preenchido automaticamente |1  |443   |sipdir.online.lync.com |100 |1 Hour |
|sipfed|tcp |Preenchido automaticamente|1 |5061 |sipfed.online.lync.com|100 | 1 Hour |
   
5. Selecione o botão **salvar DNS** na parte superior do editor de DNS. 
    
6. Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.
    
> [!NOTE]
>  Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  

