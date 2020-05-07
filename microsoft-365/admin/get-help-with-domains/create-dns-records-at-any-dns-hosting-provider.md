---
title: Criar registros DNS em qualquer provedor de hospedagem de DNS
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 7b7b075d-79f9-4e37-8a9e-fb60c1d95166
description: Aprenda a verificar seu domínio e criar registros DNS em qualquer provedor de hospedagem de DNS para o Microsoft 365.
ms.custom: okr_smb
ms.openlocfilehash: 2cf28cdd3cc2f85e448d512e72f5b022177e8f1e
ms.sourcegitcommit: 83f980927728bc080f97a3e6dc70dc305f3df841
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2020
ms.locfileid: "44053712"
---
# <a name="create-dns-records-at-any-dns-hosting-provider"></a>Criar registros DNS em qualquer provedor de hospedagem de DNS

 Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**. 
  
Confira a nossa lista de [instruções específicas de host](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions) para encontrar seu host e siga as etapas para adicionar todos os registros necessários. 
  
Se você não conhece o provedor de host DNS ou o registrador de domínios para seu domínio, confira [Localizar seu registrador de domínio ou provedor de host DNS](../get-help-with-domains/find-your-domain-registrar.md).
  
Para configurar os registros por conta própria, estes são os registros a adicionar. Observe que o registro de verificação e o registro MX são exclusivos do seu domínio. Para configurá-los, você deve obter e usar um valor de "token" específico para o seu domínio. As etapas a seguir explicam como fazer isso.
  
> [!IMPORTANT]
> O nome exato das caixas ou dos *campos* nos quais você digita ou cola as informações para criar cada tipo de registro DNS é diferente para cada host de DNS. Seu host DNS pode ter ajuda no site do para auxiliar no mapeamento das instruções apresentadas aqui para os campos exatos no site. Lembre-se de verificar se há instruções detalhadas para o seu host DNS em [Criar registros DNS para o Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider). > Alguns hosts DNS não permitem que você crie todos os tipos de registro necessários. Isso [causa limitações de serviço](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) no Microsoft 365. Se o host do seu domínio não oferecer suporte a registros SRV, TXT ou CNAME, por exemplo, recomendamos que você [transfira seu domínio](../get-help-with-domains/buy-a-domain-name.md) para um host DNS que ofereça suporte a todos os registros necessários. Para uma configuração de processos rápida e automatizada com o Microsoft 365, recomendamos transferir seu domínio para o GoDaddy. 
  
> [!NOTE]
> Normalmente, leva apenas alguns minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-or-mx-record-for-verification"></a>Adicionar um registro TXT ou MX para verificação
<a name="BKMK_verify"> </a>

> [!NOTE]
> Você criará apenas um desses registros. O TXT é o tipo de registro preferencial, mas alguns provedores de host DNS não são compatíveis com ele. Nesse caso, você pode criar um registro MX como alternativa. 
  
Antes de usar o seu domínio com o Microsoft 365, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro de DNS prova ao Microsoft 365 que você é o proprietário do domínio.
  
> [!NOTE]
> Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar. 
  
 **Localize a área no site do seu provedor de hospedagem DNS na qual você pode criar um novo registro.**
  
1. Entre no site do seu provedor de hospedagem DNS.
    
2. Escolha seu domínio.
    
3. Localize a página na qual você pode editar registros DNS para o seu domínio.
    
 **Criar o registro.**
  
1. Caso esteja criando um registro TXT ou um registro MX, siga um destes procedimentos:
    
   - **Se você criar um registro TXT, use estes valores:**
    
      |||||
      |:-----|:-----|:-----|:-----|
      |**Tipo de registro**|**Alias** ou **Nome do host**|**Valor**|**TTL**|
      |TXT|Siga um destes procedimentos: Digite **@**, deixe o campo vazio ou digite o seu nome de domínio.  <br/> **Observação:**> Hosts DNS diferentes têm requisitos diferentes para este campo. |MS=ms *XXXXXXXX*  <br/> **Observação**: esse é um exemplo. Use seu valor específico de **Destino ou Pontos de Endereçamento** aqui, retirado da tabela no Microsoft 365.  <br/>        [Como localizo isto?](../get-help-with-domains/information-for-dns-records.md)     <br/>     |Defina esse valor como **1 hora** ou o equivalente em minutos ( **60** ), segundos ( **3600** ), etc.  |
   
   - **Se você criar um registro MX, use estes valores:**
    
      ||||||
      |:-----|:-----|:-----|:-----|:-----|
      |**Tipo de registro**|**Alias** ou **Nome do host**|**Valor**|**Prioridade**|**TTL**|
      |MX|Digite **@** ou seu nome de domínio. |MS=ms *XXXXXXXX* <br/> **Observação**: esse é um exemplo. Use seu valor específico de **Destinos ou Pontos de Endereçamento** aqui, da tabela no Office 365.    <br/>       [Como localizo isto?](../get-help-with-domains/information-for-dns-records.md)     <br/>     |Para **Priority**, para evitar conflitos com o registro MX usado para o fluxo de email, use uma prioridade menor do que a prioridade de qualquer registro MX existente. <br/> Para saber mais sobre prioridade, confira [O que é prioridade MX?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) <br/> |Defina esse valor como **1 hora** ou o equivalente em minutos ( **60** ), segundos ( **3600** ), etc. |
   
2. Salve o registro.
    
Agora que você adicionou o registro no site do seu registrador de domínios, retorne ao Microsoft 365 e solicite que o Microsoft 365 procure o registro.
  
Quando o Microsoft 365 encontrar o registros TXT correto, o domínio será verificado.
  
1. No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.
    
2. Na página **Domínios**, clique no domínio que você está verificando. 
  
3. Na página **Configuração**, clique em **Iniciar configuração**.
       
4. Na página **Verificar domínio**, marque **Verificar**.   
  
> [!NOTE]
>  Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-mx-record-to-route-email"></a>Adicionar um registro MX para direcionar emails
<a name="BKMK_add_MX"> </a>

Adicione um registro MX para que o email do domínio vá para o Microsoft 365.  *Quando você atualiza o registro MX do domínio, todos os novos emails das pessoas que usam esse domínio agora vão para o Microsoft 365*. Todos os e-mails existentes permanecem no organizador atual, a menos que você decida [migrar e-mails e contato para o Microsoft 365.](../setup/migrate-email-and-contacts-admin.md)

 **Task**
  
Localize a página na qual você pode criar registros para o seu domínio.
  
1. Entre no site do seu host DNS.
    
2. Escolha seu domínio.
    
3. Localize a página na qual você pode editar registros DNS para o seu domínio.
    
::: moniker range="o365-worldwide"

  O registro MX adicionado inclui um valor (o valor **Aponta para o endereço**) que pode ter esta aparência: \<MX token\>.mail.protection.outlook.com, onde \<MX token\> é um valor, como MSxxxxxxx. 

::: moniker-end

::: moniker range="o365-germany"

  O registro MX adicionado inclui um valor (o valor **Aponta para o endereço**) que pode ter esta aparência: \<<MX token>.mail.protection.outlook.de\>, onde \<MX token\> é um valor, como MSxxxxxxx. 

::: moniker-end

4. No site do seu host DNS, adicione um novo registro MX.
    
    Agora, você vai [obter as informações para o registro MX](../get-help-with-domains/information-for-dns-records.md) do Microsoft 365. 
    
5. Para o registro MX (na etapa acima), copie o valor **Pontos de endereçamento**. 
    
    Você usará esse valor no registro que está criando no site do host DNS, conforme descrito na próxima etapa.
    
6. No novo registro MX no site do host DNS, verifique se os campos estão definidos com precisão para os seguintes valores:
    
   - **Record Type**: **MX**
    
   - **Priority**: defina a prioridade do registro MX para o valor mais alto disponível, que normalmente é **0**.
    
      Para saber mais sobre prioridade, confira [O que é prioridade MX?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)
    
   - **Nome do host**: **@**
    
   - **Pontos de endereçamento**: cole aqui o valor **Pontos de endereçamento** que você acabou de copiar do Microsoft 365. 
    
   - **TTL**: defina esse valor para **1 hora** ou o equivalente em minutos (**60**), segundos (**3600**) etc. 
    
7. Salve o registro.
    
Remova qualquer outro registro MX.
  
Se você tiver algum registro MX para este domínio que envia email para outro local além do Microsoft 365, exclua-o.
  
## <a name="add-three-cname-records"></a>Adicionar três registros CNAME
<a name="BKMK_add_MX"> </a>

::: moniker range="o365-worldwide"

Siga as etapas abaixo para adicionar os três registros CNAME necessários para o Microsoft 365. Se houver registros CNAME adicionais listados no Microsoft 365, adicione-os seguindo as mesmas etapas gerais mostradas aqui.
  
No site do seu host DNS, você vai criar três registros CNAME novos; normalmente, um de cada vez.
  
1. Nas caixas do novo registro, digite ou copie e cole os valores a seguir. Depois de adicionar os três primeiros novos registros, escolha criar outro registro CNAME.
    
      |||||
      |:-----|:-----|:-----|:-----|
      |**Tipo de Registro** <br/> |**Host** <br/> |**Pontos de** <br/> |**TTL** <br/> |
      |CNAME (Alias)  <br/> |autodiscover  <br/> |autodiscover.outlook.com  <br/> |1 hora  <br/> |
      |CNAME (Alias)  <br/> |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |1 hora  <br/> |
      |CNAME (Alias)  <br/> |sip  <br/> |sipdir.online.lync.com  <br/> |1 hora  <br/> |
   
   > [!NOTE]
   > Para **TTL**: defina esse valor como **1 hora** ou como o equivalente em minutos (**60**), segundos (**3600**), etc. > Esses registros não se aplicam a implantações híbridas do Exchange, do Lync ou do Skype for Business. 
  
2. Quando você terminar, salve os registros.
    
::: moniker-end
::: moniker range="o365-germany"

Siga as etapas abaixo para adicionar os três registros CNAME necessários para o Microsoft 365. Se houver registros CNAME adicionais listados no Microsoft 365, adicione-os seguindo as mesmas etapas gerais mostradas aqui.
  
No site do seu host DNS, você vai criar três registros CNAME novos; normalmente, um de cada vez.
  
1. Nas caixas do novo registro, digite ou copie e cole os valores a seguir. Depois de adicionar os três primeiros novos registros, escolha criar outro registro CNAME.
    
    |||||
    |:-----|:-----|:-----|:-----|
    |**Tipo de Registro** <br/> |**Host** <br/> |**Pontos de** <br/> |**TTL** <br/> |
    |CNAME (Alias)  <br/> |autodiscover  <br/> |autodiscover-outlook.office.de  <br/> |1 hora  <br/> |
    |CNAME (Alias)  <br/> |lyncdiscover  <br/> |webdir.online.skype.de  <br/> |1 hora  <br/> |
    |CNAME (Alias)  <br/> |sip  <br/> |sipdir.online.lync.de  <br/> |1 hora  <br/> |
   
     > [!NOTE]
     > Para **TTL**: defina esse valor como **1 hora** ou como o equivalente em minutos (**60**), segundos (**3600**), etc. > Esses registros não se aplicam a implantações híbridas do Exchange, do Lync ou do Skype for Business. 
  
2. Quando você terminar, salve os registros.
    
::: moniker-end

::: moniker range="o365-21vianet"

Siga as etapas abaixo para adicionar os três registros CNAME necessários para o Microsoft 365. Se houver registros CNAME adicionais listados no Microsoft 365, adicione-os seguindo as mesmas etapas gerais mostradas aqui.
  
No site do seu host DNS, você vai criar três registros CNAME novos; normalmente, um de cada vez.
  
1. Nas caixas do novo registro, digite ou copie e cole os valores a seguir. Depois de adicionar os três primeiros novos registros, escolha criar outro registro CNAME.
    
    |||||
    |:-----|:-----|:-----|:-----|
    |**Tipo de Registro** <br/> |**Host** <br/> |**Pontos de** <br/> |**TTL** <br/> |
    |CNAME (Alias)  <br/> |descoberta automática  <br/> |autodiscover.partner.outlook.cn  <br/> |1 hora  <br/> |
    |CNAME (Alias)  <br/> |lyncdiscover  <br/> |webdir.online.partner.lync.cn  <br/> |1 hora  <br/> |
    |CNAME (Alias)  <br/> |sip  <br/> |sipdir.online.partner.lync.cn  <br/> |1 hora  <br/> |
   
     > [!NOTE]
     > Para **TTL**: defina esse valor como **1 hora** ou como o equivalente em minutos (**60**), segundos (**3600**), etc. > Esses registros não se aplicam a implantações híbridas do Exchange, do Lync ou do Skype for Business. 
  
2. Quando você terminar, salve os registros.
    
::: moniker-end

## <a name="add-two-cname-records-for-mobile-device-management-mdm-for-microsoft-365"></a>Adicionar dois registros CNAME para o MDM (gerenciamento de dispositivo móvel) para o Microsoft 365
<a name="BKMK_add_MX"> </a>

::: moniker range="o365-worldwide"

> [!IMPORTANT]
> Se você tiver o MDM (gerenciamento de dispositivo móvel) para o Microsoft 365, deverá criar dois registros CNAME adicionais. Siga o procedimento que você usou para os outros quatro registros CNAME, mas forneça os valores da tabela a seguir. > (If you do not have MDM, you can skip this step.) 
  
   |||||
   |:-----|:-----|:-----|:-----|
   |**Tipo de Registro** <br/> |**Host** <br/> |**Pontos de** <br/> |**TTL** <br/> |
   |CNAME (Alias)  <br/> |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |1 hora  <br/> |
   |CNAME (Alias)  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment.manage.microsoft.com  <br/> |1 hora  <br/> |
   
::: moniker-end

::: moniker range="o365-germany"

> [!IMPORTANT]
> Se você tiver o MDM (gerenciamento de dispositivo móvel) para o Microsoft 365, deverá criar dois registros CNAME adicionais. Siga o procedimento que você usou para os outros quatro registros CNAME, mas forneça os valores da tabela a seguir. > (If you do not have MDM, you can skip this step.) 
  
   |||||
   |:-----|:-----|:-----|:-----|
   |**Tipo de Registro** <br/> |**Host** <br/> |**Pontos de** <br/> |**TTL** <br/> |
   |CNAME (Alias)  <br/> |enterpriseregistration  <br/> |enterpriseregistration.microsoftonline.de  <br/> |1 hora  <br/> |
   |CNAME (Alias)  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |1 hora  <br/> |
   
::: moniker-end

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Adicionar registro TXT à SPF para ajudar a evitar spam de email
<a name="BKMK_add_MX"> </a>

::: moniker range="o365-worldwide"

> [!IMPORTANT]
> Não é possível ter mais de um registro TXT para SPF para um domínio. Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam. Se você já possui um registro SPF para seu domínio, não crie um novo para o Microsoft 365. Em vez disso, adicione os valores necessários do Microsoft 365 ao registro atual para que você tenha um *único* registro SPF que inclua os dois conjuntos de valores.
  
No site do seu host DNS, edite o registro SPF existente ou crie um novo registro TXT para SPF.
  
> [!IMPORTANT]
> O SPF foi projetado para ajudar a evitar a falsificação, mas há técnicas de falsificação contra as quais o SPF não pode protegê-lo. Para se proteger contra isso, depois de configurar o SPF, você também deve configurar o DKIM e o DMARC para o Microsoft 365. Para começar, consulte [Usar DKIM para validar emails de saída enviados do seu domínio no Microsoft 365](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx). Em seguida, consulte [Usar DMARC para validar emails no Microsoft 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx). 
  
1. Nas caixas do novo registro, digite ou copie e cole o conjunto de valores a seguir que se apliquem à sua situação.
    
    |||||
    |:-----|:-----|:-----|:-----|
    |**Tipo de Registro** <br/> |**Host** <br/> |**Valor TXT** <br/> |**TTL** <br/> |
    |TXT (Texto)  <br/> |@  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Observação:** é recomendável copiar e colar essa entrada, para que todo o espaçamento permaneça correto.           |1 hora  <br/> |
   
    Para **TTL**: defina esse valor para **1 hora** ou o equivalente em minutos (**60**), segundos (**3600**), etc. 
    
2. Quando você terminar, salve o registro.
    
3. Para validar o registro SPF, você pode usar uma destas [ferramentas de validação de SPF](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain).

::: moniker-end

::: moniker range="o365-germany"

> [!IMPORTANT]
> Não é possível ter mais de um registro TXT para SPF para um domínio. Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam. Se você já possui um registro SPF para seu domínio, não crie um novo para o Microsoft 365. Em vez disso, adicione os valores necessários do Microsoft 365 ao registro atual para que você tenha um *único* registro SPF que inclua os dois conjuntos de valores. 
  
No site do seu host DNS, edite o registro SPF existente ou crie um novo registro TXT para SPF.
  
> [!IMPORTANT]
> O SPF foi projetado para ajudar a evitar a falsificação, mas há técnicas de falsificação contra as quais o SPF não pode protegê-lo. Para se proteger contra isso, depois de configurar o SPF, você também deve configurar o DKIM e o DMARC para o Microsoft 365. Para começar, consulte [Usar DKIM para validar emails de saída enviados do seu domínio no Microsoft 365](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx). Em seguida, consulte [Usar DMARC para validar emails no Microsoft 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx). 
  
1. Nas caixas do novo registro, digite ou copie e cole o conjunto de valores a seguir que se apliquem à sua situação.
    
    |||||
    |:-----|:-----|:-----|:-----|
    |**Tipo de Registro**|**Host**|**Valor TXT**|**TTL**|
    |TXT (Texto)|@|v=spf1 include:spf.protection.outlook.de -all <br/>  É recomendável copiar e colar essa entrada, para que todo o espaçamento permaneça correto.           |1 hora|
   
    Para **TTL**: defina esse valor para **1 hora** ou o equivalente em minutos (**60**), segundos (**3600**), etc. 
    
2. Quando você terminar, salve o registro.
    
3. Para validar o registro SPF, você pode usar uma destas [ferramentas de validação de SPF](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain).
    
::: moniker-end

::: moniker range="o365-21vianet"

> [!IMPORTANT]
> Não é possível ter mais de um registro TXT para SPF para um domínio. Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam. Se você já possui um registro SPF para seu domínio, não crie um novo para o Microsoft 365. Em vez disso, adicione os valores necessários do Microsoft 365 ao registro atual para que você tenha um *único* registro SPF que inclua os dois conjuntos de valores. 
  
No site do seu host DNS, edite o registro SPF existente ou crie um novo registro TXT para SPF.
  
> [!IMPORTANT]
> O SPF foi projetado para ajudar a evitar a falsificação, mas há técnicas de falsificação contra as quais o SPF não pode protegê-lo. Para se proteger contra isso, depois de configurar o SPF, você também deve configurar o DKIM e o DMARC para o Microsoft 365. Para começar, consulte [Usar DKIM para validar emails de saída enviados do seu domínio no Microsoft 365](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx). Em seguida, consulte [Usar DMARC para validar emails no Microsoft 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx). 
  
1. Nas caixas do novo registro, digite ou copie e cole o conjunto de valores a seguir que se apliquem à sua situação.
    
    |||||
    |:-----|:-----|:-----|:-----|
    |**Tipo de Registro**|**Host**|**Valor TXT**|**TTL**|
    |TXT (Texto)|@|v=spf1 include:spf.protection.partner.outlook.cn -all> [!NOTE]> É recomendável copiar e colar essa entrada, para que todo o espaçamento permaneça correto.           |1 hora|
   
    Para **TTL**: defina esse valor para **1 hora** ou o equivalente em minutos (**60**), segundos (**3600**), etc. 
    
2. Quando você terminar, salve o registro.
    
3. Para validar o registro SPF, você pode usar uma destas [ferramentas de validação de SPF](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain).
    
::: moniker-end

## <a name="add-two-srv-records"></a>Adicionar dois registros SRV
<a name="BKMK_add_MX"> </a>

::: moniker range="o365-worldwide"

No site do seu host DNS, você vai criar dois registros SRV novos; normalmente, um de cada vez. Isto é, depois de adicionar o primeiro registro SRV ao site, escolha criar outro registro SRV.
  
1. Nas caixas do novo registro, digite ou copie e cole os valores a seguir. **(Confira as observações a seguir para criar registros SRV, caso o host DNS não tenha todos eles como campos separados.) **
    
    ||||||||||
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |**Tipo de Registro** <br/> |**Nome** <br/> |**Destino** <br/> |**Protocolo** <br/> |**Serviço** <br/> |**Prioridade** <br/> |**Espessura** <br/> |**Porta** <br/> |**TTL** <br/> |
    |SRV (Serviço)  <br/> |@  <br/> (Ou deixe em branco, se o símbolo @ não for permitido)  <br/> |sipdir.online.lync.com  <br/> |_tls  <br/> |_sip  <br/> |100  <br/> |1  <br/> |443  <br/> |1 hora  <br/> |
    |SRV (Serviço)  <br/> |@  <br/> (Ou deixe em branco, se o símbolo @ não for permitido)  <br/> |sipfed.online.lync.com  <br/> |_tcp  <br/> |_sipfederationtls  <br/> |100  <br/> |1  <br/> |5061  <br/> |1 hora  <br/> |
   
    > [!NOTE]
    >  Para **Nome**: Se o seu host DNS não permitir essa configuração de **@**, deixe em branco. Use esta abordagem *apenas* quando o host DNS tiver campos separados para os valores Serviço e Protocolo. Caso contrário, consulte as observações a seguir sobre Serviço e Protocolo. 
    > 
    >  Para **Serviço**e **Protocolo**:Caso seu host DNS não forneça esses campos para registros SRV, você deve especificar os valores **Serviço** e **Protocolo** como o valor **Nome** do registro. (Observação: dependendo do seu host DNS, o campo **Nome** pode ser chamado algo mais, como: **Host**, **Hostname** ou **Subdomínio**.) Para configurar o valor combinado, crie uma única cadeia de caracteres e separe os valores com um ponto.  Por exemplo: **Nome**: _sip._tls 
    > 
    >  Para **Prioridade**,**Gramatura**e**Porta**se o host DNS não oferecer esses campos para registros SRV, você deve especificá-los como o valor **Destino** do registro. (Observação: dependendo do seu host DNS, o campo **Destino** pode ser chamado algo mais, como: **Conteúdo**, **Endereço de IP**ou **Host de Destino**.) Para configurar o valor combinado, crie uma única cadeia de caracteres e separe os valores com espaços e termine com um ponto. Os valores devem ser incluídos nesta ordem: Prioridade, Peso, Porta, Destino. Por exemplo: **Destino**: 100 1 443 sipdir.online.lync.com. 
    > 
    >  Variações para **Prioridade**, **Espessura** e **Porta**: Alguns hosts DNS fornecem alguns dos campos necessários separadamente, mas não todos. Para estes sites de host DNS, especifique os valores que não são mostrados separadamente como uma cadeia de caracteres combinada, na ordem, para o valor **Destino** do registro. (Observação: dependendo do seu host DNS, o campo **Destino** pode ser chamado algo mais, como: **Conteúdo**, **Endereço de IP**ou **Host de Destino**.) Para configurar o valor combinado, crie uma única cadeia de caracteres para os campos que não são mostrados individualmente, separando os valores com espaços. Os valores devem ser incluídos *em ordem*, deixando os valores que têm campos separados disponíveis: Prioridade, Espessura, Porta, Destino. Por exemplo, quando Prioridade tiver um campo separado, concatene apenas os valores de Destino, Porta e Espessura: **Destino**: 1 443 sipdir.online.lync.com 
    > 
    > Para **TTL**: defina esse valor para **1 hora** ou o equivalente em minutos (**60**), segundos (**3600**), etc. 
  
2. Quando você terminar, salve os registros.
    
    > [!NOTE]
    >  Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
::: moniker-end


::: moniker range="o365-germany"

No site do seu host DNS, você vai criar dois registros SRV novos; normalmente, um de cada vez. Isto é, depois de adicionar o primeiro registro SRV ao site, escolha criar outro registro SRV.
  
1. Nas caixas do novo registro, digite ou copie e cole os valores a seguir. **(Confira as observações a seguir para criar registros SRV, caso o host DNS não tenha todos eles como campos separados.) **
    
    ||||||||||
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |**Tipo de Registro** <br/> |**Nome** <br/> |**Destino** <br/> |**Protocolo** <br/> |**Serviço** <br/> |**Prioridade** <br/> |**Espessura** <br/> |**Porta** <br/> |**TTL** <br/> |
    |SRV (Serviço)  <br/> |@  <br/> (Ou deixe em branco, se o símbolo @ não for permitido)  <br/> |sipdir.online.lync.de  <br/> |_tls  <br/> |_sip  <br/> |100  <br/> |1  <br/> |443  <br/> |1 hora  <br/> |
    |SRV (Serviço)  <br/> |@  <br/> (Ou deixe em branco, se o símbolo @ não for permitido)  <br/> |sipfed.online.lync.de  <br/> |_tcp  <br/> |_sipfederationtls  <br/> |100  <br/> |1  <br/> |5061  <br/> |1 hora  <br/> |
   
    > [!NOTE]
    >  Para **Nome**: Se o seu host DNS não permitir essa configuração de **@**, deixe em branco. Use esta abordagem *apenas* quando o host DNS tiver campos separados para os valores Serviço e Protocolo. Caso contrário, consulte as observações a seguir sobre Serviço e Protocolo. 
    > 
    >  Para **Serviço**e **Protocolo**:Caso seu host DNS não forneça esses campos para registros SRV, você deve especificar os valores **Serviço** e **Protocolo** como o valor **Nome** do registro. (Observação: dependendo do seu host DNS, o campo **Nome** pode ser chamado algo mais, como: **Host**, **Hostname** ou **Subdomínio**.) Para configurar o valor combinado, crie uma única cadeia de caracteres e separe os valores com um ponto. > Por exemplo: **Nome**: _sip._tls 
    > 
    >  Para **Prioridade**,**Gramatura**e**Porta**se o host DNS não oferecer esses campos para registros SRV, você deve especificá-los como o valor **Destino** do registro. (Observação: dependendo do seu host DNS, o campo **Destino** pode ser chamado algo mais, como: **Conteúdo**, **Endereço de IP**ou **Host de Destino**.) Para configurar o valor combinado, crie uma única cadeia de caracteres e separe os valores com espaços e termine com um ponto. Os valores devem ser incluídos nesta ordem: Prioridade, Peso, Porta, Destino. > Por exemplo: **Destino**: 100 1 443 sipdir.online.lync.de. 
    > 
    >  Variações para **Prioridade**, **Espessura** e **Porta**: Alguns hosts DNS fornecem alguns dos campos necessários separadamente, mas não todos. Para estes sites de host DNS, especifique os valores que não são mostrados separadamente como uma cadeia de caracteres combinada, na ordem, para o valor **Destino** do registro. (Observação: dependendo do seu host DNS, o campo **Destino** pode ser chamado algo mais, como: **Conteúdo**, **Endereço de IP**ou **Host de Destino**.) Para configurar o valor combinado, crie uma única cadeia de caracteres para os campos que não são mostrados individualmente, separando os valores com espaços. Os valores devem ser incluídos *em ordem*, deixando os valores que têm campos separados disponíveis: Prioridade, Espessura, Porta, Destino. > Por exemplo, quando Prioridade tiver um campo separado, concatene apenas os valores de Destino, Porta e Espessura: **Destino**: 1 443 sipdir.online.lync.de 
    > 
    >  Para **TTL**: defina esse valor para **1 hora** ou o equivalente em minutos (**60**), segundos (**3600**), etc. 
  
2. Quando você terminar, salve os registros.
    
    > [!NOTE]
    >  Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
::: moniker-end


::: moniker range="o365-21vianet"

No site do seu host DNS, você vai criar dois registros SRV novos; normalmente, um de cada vez. Isto é, depois de adicionar o primeiro registro SRV ao site, escolha criar outro registro SRV.
  
1. Nas caixas do novo registro, digite ou copie e cole os valores a seguir. **(Confira as observações a seguir para criar registros SRV, caso o host DNS não tenha todos eles como campos separados.) **
    
    ||||||||||
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |**Tipo de Registro** <br/> |**Nome** <br/> |**Destino** <br/> |**Protocolo** <br/> |**Serviço** <br/> |**Prioridade** <br/> |**Espessura** <br/> |**Porta** <br/> |**TTL** <br/> |
    |SRV (Serviço)  <br/> |@  <br/> (Ou deixe em branco, se o símbolo @ não for permitido)  <br/> |sipdir.online.partner.lync.cn  <br/> |_tls  <br/> |_sip  <br/> |100  <br/> |1  <br/> |443  <br/> |1 hora  <br/> |
    |SRV (Serviço)  <br/> |@  <br/> (Ou deixe em branco, se o símbolo @ não for permitido)  <br/> |sipfed.online.partner.lync.cn  <br/> |_tcp  <br/> |_sipfederationtls  <br/> |100  <br/> |1  <br/> |5061  <br/> |1 hora  <br/> |
   
    > [!NOTE]
    >  Para **Nome**: Se o seu host DNS não permitir essa configuração de **@**, deixe em branco. Use esta abordagem *apenas* quando o host DNS tiver campos separados para os valores Serviço e Protocolo. Caso contrário, consulte as observações a seguir sobre Serviço e Protocolo. 
    > 
    >  Para **Serviço**e **Protocolo**:Caso seu host DNS não forneça esses campos para registros SRV, você deve especificar os valores **Serviço** e **Protocolo** como o valor **Nome** do registro. (Observação: dependendo do seu host DNS, o campo **Nome** pode ser chamado algo mais, como: **Host**, **Hostname** ou **Subdomínio**.) Para configurar o valor combinado, crie uma única cadeia de caracteres e separe os valores com um ponto. > Por exemplo: **Nome**: _sip._tls 
    > 
    >  Para **Prioridade**,**Gramatura**e**Porta**se o host DNS não oferecer esses campos para registros SRV, você deve especificá-los como o valor **Destino** do registro. (Observação: dependendo do seu host DNS, o campo **Destino** pode ser chamado algo mais, como: **Conteúdo**, **Endereço de IP**ou **Host de Destino**.) Para configurar o valor combinado, crie uma única cadeia de caracteres e separe os valores com espaços e termine com um ponto. Os valores devem ser incluídos nesta ordem: Prioridade, Peso, Porta, Destino. > Por exemplo: **Destino**: 100 1 443 sipdir.online.partner.lync.cn. 
    > 
    >  Variações para **Prioridade**, **Espessura** e **Porta**: Alguns hosts DNS fornecem alguns dos campos necessários separadamente, mas não todos. Para estes sites de host DNS, especifique os valores que não são mostrados separadamente como uma cadeia de caracteres combinada, na ordem, para o valor **Destino** do registro. (Observação: dependendo do seu host DNS, o campo **Destino** pode ser chamado algo mais, como: **Conteúdo**, **Endereço de IP**ou **Host de Destino**.) Para configurar o valor combinado, crie uma única cadeia de caracteres para os campos que não são mostrados individualmente, separando os valores com espaços. Os valores devem ser incluídos *em ordem*, deixando os valores que têm campos separados disponíveis: Prioridade, Espessura, Porta, Destino. > Por exemplo, quando Prioridade tiver um campo separado, concatene apenas os valores de Destino, Porta e Espessura: **Destino**: 1 443 sipdir.online.partner.lync.cn. 
    > 
    >  Para **TTL**: defina esse valor para **1 hora** ou o equivalente em minutos (**60**), segundos (**3600**), etc. 
  
2. Quando você terminar, salve os registros.
    
    > [!NOTE]
    >  Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
::: moniker-end

## <a name="more-about-updating-dns-records"></a>Saiba mais sobre como atualizar os registros DNS
<a name="BKMK_MoreAbout"> </a>

 **Se você souber como atualizar os registros DNS no host DNS do seu domínio**, use os valores de DNS do Microsoft 365 para editar os registros de host DNS do seu domínio, por exemplo, para configurar um registro MX ou SPF. Encontre os valores específicos para uso [seguindo estas etapas](../get-help-with-domains/information-for-dns-records.md), ou exiba-os no assistente de configuração de domínios ao longo do processo.
  
 **Se você precisar de ajuda para descobrir como adicionar os registros DNS necessários**, confira [Configura seu domínio (instruções específicas do host)](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions?view=o365-worldwide), primeiro [colete as informações necessárias para criar os registros de DNS do Microsoft 365](../get-help-with-domains/information-for-dns-records.md). Em seguida, use as etapas gerais deste tópico para configurar os registros DNS do seu domínio, para que você possa usar o seu domínio com os serviços do Microsoft 365, como email.
  
 **Se você não tiver um site usado com o seu domínio personalizado**, o Microsoft 365 pode configurar e gerenciar registros DNS do seu domínio por você em vez de ter que fazer toda a configuração por conta própria. Saiba mais sobre as [duas opções para configurar e gerenciar registros DNS de um domínio personalizado](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) no Microsoft 365. 
  

