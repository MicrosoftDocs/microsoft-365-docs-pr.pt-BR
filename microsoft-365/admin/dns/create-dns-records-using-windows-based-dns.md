---
title: Criar registros DNS para o Office 365 usando DNS baseado no Windows
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
ms.assetid: 9eec911d-5773-422c-9593-40e1147ffbde
description: Saiba como verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços em DNS baseado em Windows para o Office 365.
ms.openlocfilehash: ddea5cb95a7f2abef8b68b37de473f936ee08eb5
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42238952"
---
# <a name="create-dns-records-for-office-365-using-windows-based-dns"></a>Criar registros DNS para o Office 365 usando DNS baseado no Windows

 Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**. 
   
Se você hospedar seus próprios registros DNS usando um DNS baseado no Windows, siga as etapas neste artigo para configurar seus registros para email, Skype for Business Online e assim por diante.
  
Para começar, você precisa [localizar seus registros DNS no DNS baseado no Windows](#find-your-dns-records-in-windows-based-dns) para que possa atualizá-los. Além disso, se você estiver planejando sincronizar seu Active Directory local com o Office 365, confira [endereço de email não roteável usado como um UPN no seu Active Directory local](#non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory).
  
Problemas com o fluxo de emails ou outros problemas após a adição de registros DNS, consulte [solucionar problemas após alterar seu nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="find-your-dns-records-in-windows-based-dns"></a>Localize seus registros DNS no DNS baseado no Windows
<a name="BKMK_find_your_dns_1"></a> Vá para a página que tem os registros DNS do seu domínio. Se você estiver trabalhando no Windows Server 2008, vá para **Iniciar** > **executar**. Se você estiver trabalhando no Windows Server 2012, pressione a tecla Windows e **r**. Digite **dnsmgmnt. msc**e, em seguida, selecione **OK**. No Gerenciador DNS, expanda ** \<nome\> \> do servidor DNS zonas de pesquisa direta  **. Selecionar seu domínio. Você está pronto para criar os registros DNS.
   
## <a name="add-mx-record"></a>Adicionar registro MX
<a name="BKMK_add_MX"> </a>

Adicione um registro MX para que o email de seu domínio se torne Office 365.
- O registro MX adicionado inclui um valor (o valor **Aponta para o endereço**) que pode ter esta aparência: \<MX token\>.mail.protection.outlook.com, onde \<MX token\> é um valor, como MSxxxxxxx. 
- Da linha MX na seção Exchange Online da página Adicionar registros DNS no Office 365, copie o valor listado em Pontos de endereçamento. Você usará esse valor no registro que está criando nesta tarefa. 
- Na página Gerenciador DNS para o domínio, vá para **ação** > **servidor de mensagens (MX)**. Para localizar esta página para o domínio, confira [localizar seus registros DNS no DNS baseado no Windows](#find-your-dns-records-in-windows-based-dns).  
- Na caixa de diálogo **novo registro de recurso** , verifique se os campos estão definidos com precisão para os seguintes valores: 
    - Nome do host: 
    - @Address: Cole os pontos no valor de endereço que você acabou de copiar do Office 365 aqui.  
    - Pref 
- Selecione **salvar alterações**.
- Remova qualquer registro MX obsoleto. Se você tiver registros MX antigos para este domínio que encaminhar emails para outro local, marque a caixa de seleção ao lado de cada registro antigo e selecione **excluir** > **OK**. 
   
## <a name="add-cname-records"></a>Adicionar registros CNAME
<a name="BKMK_add_CNAME"> </a>

Adicionar os registros CNAME necessários para o Office 365. Se houver registros CNAME adicionais listados no Office 365, adicione-os seguindo as mesmas etapas gerais mostradas aqui.
  
> [!IMPORTANT]
> Se você tiver o gerenciamento de dispositivo móvel (MDM) para o Office 365, deverá criar dois registros CNAME adicionais. Follow the procedure that you used for the other four CNAME records, but supply the values from the following table. Se você não tiver o MDM, ignore esta etapa. 

- Na página Gerenciador DNS para o domínio, vá para **ação** > **CNAME (CNAME)**.
- Na caixa de diálogo **novo registro de recurso** , verifique se os campos estão definidos com precisão para os seguintes valores:  
    - Nome do host: descoberta automática
    - Tipo: 
    - Cnameendereço: autodiscover.outlook.com
- Selecione **O**K.

Adicione o registro CNAME SIP. 
- Na página Gerenciador DNS para o domínio, vá para **ação** \> **CNAME (CNAME)**. 
- Na caixa de diálogo **novo registro de recurso** , verifique se os campos estão definidos com precisão para os seguintes valores:  
    - Nome do host: SIP
    - Tipo: CNAME
    - Endereço: sipdir.online.lync.com
- Selecione **OK**.

Adicione o registro CNAME de Descoberta Automática do Skype for Business Online.  
- Na página Gerenciador DNS para o domínio, vá para **ação** \> **CNAME (CNAME)**. Na caixa de diálogo **novo registro de recurso** , verifique se os campos estão definidos com precisão para os seguintes valores:  
    - Nome do host: lyncdiscover
    - Tipo: CNAME
    - Endereço: webdir.online.lync.com
- Selecione **OK**.
   
### <a name="add-two-cname-records-for-mobile-device-management-mdm-for-office-365"></a>Adicionar dois registros CNAME para o MDM (gerenciamento de dispositivo móvel) para o Office 365

> [!IMPORTANT]
> Se você tiver o gerenciamento de dispositivo móvel (MDM) para o Office 365, deverá criar dois registros CNAME adicionais. Follow the procedure that you used for the other four CNAME records, but supply the values from the following table. > (se você não tiver o MDM, poderá ignorar esta etapa.) 
  

Adicione o registro CNAME Enterpriseregistration do MDM.  
- Na página Gerenciador DNS para o domínio, vá para **ação** \> **CNAME (CNAME)**. 
- Na caixa de diálogo **novo registro de recurso** , verifique se os campos estão definidos com precisão para os seguintes valores:  
- Nome do host: enterpriseregistration
- Tipo: CNAME
- Endereço: enterpriseregistration.windows.net
- Selecione **OK**. 

Adicione o registro CNAME Enterpriseenrollment do MDM. 
-  Na página Gerenciador DNS para o domínio, vá para **ação** \> **CNAME (CNAME)**. 
-  Na caixa de diálogo **novo registro de recurso** , verifique se os campos estão definidos com precisão para os seguintes valores:  
    - Nome do host: enterpriseenrollment
    - Tipo: CNAME
    - Endereço: enterpriseenrollment-s.manage.microsoft.com
- Selecione **OK**.
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Adicionar registro TXT à SPF para ajudar a evitar spam de email
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. Em vez disso, adicione os valores necessários do Office 365 ao registro atual, de modo que você tenha um  *único*  registro SPF que inclua os dois conjuntos de valores. 
  
Adicione o registro TXT SPF do seu domínio ajudar a evitar spam de email.
  
- Você pode já ter outras cadeias de caracteres no valor TXT para este registro (como cadeias de caracteres para email de marketing), o que é bom. Deixe essas cadeias de caracteres e adicione este tipo, colocando aspas duplas em cada cadeia para separá-las. 
- Na página Gerenciador DNS do seu domínio, vá para **ação** \> **texto (txt)**. 
-  Na caixa de diálogo **novo registro de recurso** , verifique se os campos estão definidos com precisão para os seguintes valores. 
 > [!IMPORTANT]
> Em algumas versões do Gerenciador DNS do Windows, o domínio pode ter sido configurado para que, quando você cria um registro TXT, o nome da página inicial é o domínio pai. Nesta situação, ao adicionar um registro TXT, deixe o nome do host em branco (nenhum valor) em vez de defini-lo como @ ou como o nome de domínio. 

-  Tipo de host: @
-  Tipo de registro: TXT
-  Endereço: v = spf1 inclui include. Protection. Outlook. com-All 
         
-  Selecione **OK**.
   
## <a name="add-srv-records"></a>Adicionar registros SRV
<a name="BKMK_add_SRV"> </a>

Adicionar os dois registros SRV necessários para o Office 365.

Adicione o registro SRV SIP para a Webconferência do Skype for Business Online.  <br/> 
-  Na página Gerenciador DNS do seu domínio, vá para **ação** \> **outros novos registros**. 
-   Na janela **tipo de registro de recurso** , selecione **local do serviço (SRV)** e, em seguida, selecione **criar registro**. 
-   Na caixa de diálogo **novo registro de recurso** , verifique se os campos estão definidos com precisão para os seguintes valores:  
    -  Serviço: _sip
    -  Protocolo: _tls
    -  Priority: 100
    -  Peso: 1
    -  Porta: 443
    -  Destino (nome do host): sipdir.online.lync.com
-  Selecione **OK**. 


Adicione o registro SRV SIP para a federação do Skype for Business Online.  
-  Na página Gerenciador DNS do seu domínio, vá para **ação** \> **outros novos registros**.  
-  Na janela **tipo de registro de recurso** , selecione **local do serviço (SRV)** e, em seguida, selecione **criar registro**. 
-   Na caixa de diálogo **novo registro de recurso** , verifique se os campos estão definidos com precisão para os seguintes valores:  
    -  Serviço: _sipfederationtls
    -  Protocolo: _tcp
    -  Priority: 100
    -  Peso: 1
    -  Porta: 5061
    -  Destino (nome do host): sipfed.online.lync.com
-  Selecione **OK**. 
   
## <a name="add-a-record-to-verify-that-you-own-the-domain-if-you-havent-already"></a>Adicione um registro para verificar se você é o proprietário do domínio, se ainda não fez isso.
<a name="BKMK_verify"> </a>

Antes de adicionar os registros DNS para configurar seus serviços do Office 365, Office 365 terá que confirmar se você é o proprietário do domínio que está adicionando. Para tanto, você adicionará um registro, seguindo as etapas abaixo.
  
> [!NOTE]
> Esse registro só é usado para confirmar que você é proprietário do domínio. Ele não afeta mais nada. 
  

1. Coletar informações do Office 365.  <br/> 
2. No centro de administração, vá para a página de <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a> de **configurações** \> . 
3. Na página **domínios** , na coluna **ações** do domínio que você está verificando, selecione **Iniciar configuração**. 
4. Na página **Adicionar um domínio ao Office 365** , selecione **Iniciar etapa 1**. 
5. Na página **confirmar que você é o proprietário do domínio** , na lista suspensa **consulte as instruções para executar esta etapa com** , escolha **instruções gerais**. 
6. Na tabela, copie o valor Destino ou Pontos para Endereço. Você precisará dele para a etapa seguinte. É recomendável copiar e colar este valor, para que todo o espaçamento permaneça correto.

Adicione um registro TXT. 
-  Na página Gerenciador DNS do seu domínio, vá para **ação** \> **texto (txt)**. 
-   Na caixa de diálogo **novo registro de recurso** , selecione **Editar**.  
-  Na área **nomes de host personalizados** da caixa de diálogo **novo registro de recurso** , verifique se os campos estão definidos com precisão para os seguintes valores. 

> [!IMPORTANT] 
> Em algumas versões do Gerenciador DNS do Windows, o domínio pode ter sido configurado para que, quando você cria um registro TXT, o nome da página inicial é o domínio pai. Nesta situação, ao adicionar um registro TXT, deixe o nome do host em branco (nenhum valor) em vez de defini-lo como @ ou como o nome de domínio. 

- Nome do host: @
- Tipo: TXT
- Endereço: Cole o valor de destino ou pontos para endereço que você acabou de copiar do Office 365 aqui.  
- Selecione **OK** > **concluído**.

Verifique seu domínio no Office 365.  
> [!IMPORTANT]
> Aguarde cerca de 15 minutos antes de fazer isso, para que o registro que você acabou de criar possa ser atualizado na Internet.       

- Volte ao Office 365 e siga as etapas abaixo para solicitar uma seleção de verificação. A verificação procura o registro TXT adicionado na etapa anterior. Quando encontrar o registro TXT correto, o domínio será verificado.  
1. No centro de administração, vá para a página **Configurar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a> .
2. Na página **domínios** , na coluna **ação** para o domínio que você está verificando, selecione **Iniciar configuração**. 
3. Na página **confirmar que você é o proprietário do domínio** , selecione **concluído, verificar agora**e, na caixa de diálogo de confirmação, selecione **concluir**. 
   
> [!NOTE]
>  Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory"></a>Endereço de email não roteável utilizado como um UPN no seu Active Directory local
<a name="BKMK_ADNote"> </a>

Se você pretende sincronizar seu Active Directory local ao Office 365, verifique se o sufixo do nome de usuário principal (UPN) do Active Directory é um sufixo de domínio válido e não um sufixo não suportado, como @contoso.local. Se você precisar alterar seu sufixo UPN, consulte [como preparar um domínio não roteável para a sincronização de diretórios](https://support.office.com/article/e7968303-c234-46c4-b8b0-b5c93c6d57a7).
  
> [!NOTE]
>  Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
