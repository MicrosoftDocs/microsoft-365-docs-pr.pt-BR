---
title: Criar registros DNS para a Microsoft usando DNS baseado no Windows
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
ms.assetid: 9eec911d-5773-422c-9593-40e1147ffbde
description: Saiba como verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços em DNS baseado em Windows para Microsoft.
ms.openlocfilehash: 8202ffe10b4a0ff9c94d863d92fc55c47ebb38d3
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/11/2020
ms.locfileid: "49656838"
---
# <a name="create-dns-records-for-microsoft-using-windows-based-dns"></a>Criar registros DNS para a Microsoft usando DNS baseado no Windows

 Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.yml)**. 
   
Se você hospedar seus próprios registros DNS usando um DNS baseado no Windows, siga as etapas neste artigo para configurar seus registros para email, Skype for Business Online e assim por diante.
  
Para começar, você precisa [localizar seus registros DNS no DNS baseado no Windows](#find-your-dns-records-in-windows-based-dns) para que possa atualizá-los. Além disso, se você estiver planejando sincronizar o Active Directory local com a Microsoft, confira [endereço de email não roteável usado como UPN em seu Active Directory local](#non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory).
  
Problemas com o fluxo de emails ou outros problemas após a adição de registros DNS, consulte [solucionar problemas após alterar seu nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="find-your-dns-records-in-windows-based-dns"></a>Localize seus registros DNS no DNS baseado no Windows
<a name="BKMK_find_your_dns_1"></a> Vá para a página que tem os registros DNS do seu domínio. Se você estiver trabalhando no Windows Server 2008, vá para **Iniciar**  >  **executar**. Se você estiver trabalhando no Windows Server 2012, pressione a tecla Windows e **r**. Digite **dnsmgmnt. msc** e, em seguida, selecione **OK**. No Gerenciador DNS, expanda **\<DNS server name\> \> zonas de pesquisa direta**. Selecionar seu domínio. Você está pronto para criar os registros DNS.
   
## <a name="add-mx-record"></a>Adicionar registro MX
<a name="BKMK_add_MX"> </a>

Adicionar um registro MX para que o email do seu domínio seja fornecido para a Microsoft.
- O registro MX que você adicionará inclui um valor (os **pontos para** o valor do endereço) que tem a seguinte aparência: \<MX token\> . mail.Protection.Outlook.com, onde \<MX token\> é um valor como MSxxxxxxx. 
- Na linha MX na seção Exchange Online da página Adicionar registros DNS no Microsoft, copie o valor listado em pontos para endereço. Você usará esse valor no registro que está criando nesta tarefa. 
- Na página Gerenciador DNS para o domínio, vá para **ação**  >  **servidor de mensagens (MX)**. Para localizar esta página para o domínio, confira [localizar seus registros DNS no DNS baseado no Windows](#find-your-dns-records-in-windows-based-dns).  
- Na caixa de diálogo **novo registro de recurso** , verifique se os campos estão definidos com precisão para os seguintes valores: 
    - Nome do Host:  
    - @Address: Cole o valor de pontos no endereço que você copiou da Microsoft aqui.  
    - Pref 
- Selecione **salvar alterações**.
- Remova qualquer registro MX obsoleto. Se você tiver registros MX antigos para este domínio que encaminhar emails para outro local, marque a caixa de seleção ao lado de cada registro antigo e selecione **excluir**  >  **OK**. 
   
## <a name="add-cname-records"></a>Adicionar registros CNAME
<a name="BKMK_add_CNAME"> </a>

Adicione os registros CNAME necessários para a Microsoft. Se houver registros CNAME adicionais listados no Microsoft, adicione-os seguindo as mesmas etapas gerais mostradas aqui.
  
> [!IMPORTANT]
> Se você tiver o gerenciamento de dispositivo móvel (MDM) para a Microsoft, deverá criar dois registros CNAME adicionais. Siga o procedimento que você usou para os outros quatro registros CNAME, mas forneça os valores da tabela a seguir. Se você não tiver o MDM, ignore esta etapa. 

- Na página Gerenciador DNS para o domínio, vá para **ação**  >  **CNAME (CNAME)**.
- Na caixa de diálogo **novo registro de recurso** , verifique se os campos estão definidos com precisão para os seguintes valores:  
    - Nome do host: descoberta automática
    - Tipo: 
    - Cnameendereço: autodiscover.outlook.com
- Selecione **O** K.

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
   
### <a name="add-two-cname-records-for-mobile-device-management-mdm-for-microsoft"></a>Adicionar dois registros CNAME para o gerenciamento de dispositivo móvel (MDM) para Microsoft

> [!IMPORTANT]
> Se você tiver o gerenciamento de dispositivo móvel (MDM) para a Microsoft, deverá criar dois registros CNAME adicionais. Siga o procedimento que você usou para os outros quatro registros CNAME, mas forneça os valores da tabela a seguir. > (se você não tiver o MDM, poderá ignorar esta etapa.) 
  

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
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Não é possível ter mais de um registro TXT para SPF para um domínio. Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam. Se você já possui um registro SPF para seu domínio, não crie um novo para a Microsoft. Em vez disso, adicione os valores necessários da Microsoft ao registro atual para que você tenha um  *único*  registro SPF que inclua os dois conjuntos de valores. 
  
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

Adicione os dois registros SRV necessários para a Microsoft.

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

Antes de adicionar os registros DNS para configurar seus serviços da Microsoft, a Microsoft precisa confirmar que você é o proprietário do domínio que você está adicionando. Para tanto, você adicionará um registro, seguindo as etapas abaixo.
  
> [!NOTE]
> Esse registro só é usado para confirmar que você é proprietário do domínio. Ele não afeta mais nada. 
  

1. Coletar informações da Microsoft.  <br/> 
2. No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>. 
3. Na página **domínios** , na coluna **ações** do domínio que você está verificando, selecione **Iniciar configuração**. 
4. Na página **Adicionar um domínio à Microsoft** , selecione **Iniciar etapa 1**. 
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
- Endereço: Cole o valor de destino ou aponta para o endereço que você copiou da Microsoft aqui.  
- Selecione **OK**  >  **concluído**.

Verifique seu domínio no Microsoft.  
> [!IMPORTANT]
> Aguarde cerca de 15 minutos antes de fazer isso, para que o registro que você acabou de criar possa ser atualizado na Internet.       

- Volte para a Microsoft e siga as etapas abaixo para solicitar uma verificação de verificação. A verificação procura o registro TXT adicionado na etapa anterior. Quando encontrar o registro TXT correto, o domínio será verificado.  
1. No centro de administração, vá para a página **Configurar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a> .
2. Na página **domínios** , na coluna **ação** para o domínio que você está verificando, selecione **Iniciar configuração**. 
3. Na página **confirmar que você é o proprietário do domínio** , selecione **concluído, verificar agora** e, na caixa de diálogo de confirmação, selecione **concluir**. 
   
> [!NOTE]
>  Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory"></a>Endereço de email não roteável utilizado como um UPN no seu Active Directory local
<a name="BKMK_ADNote"> </a>

Se você estiver planejando sincronizar seu Active Directory local com a Microsoft, verifique se o sufixo UPN (nome principal de usuário) do Active Directory é um sufixo de domínio válido, e não um sufixo de domínio sem suporte, como @contoso. local. Se você precisar alterar seu sufixo UPN, consulte [como preparar um domínio não roteável para a sincronização de diretórios](https://docs.microsoft.com/microsoft-365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization).
  
> [!NOTE]
>  Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
