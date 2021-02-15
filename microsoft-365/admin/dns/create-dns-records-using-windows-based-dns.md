---
title: Criar registros DNS para a Microsoft usando o DNS baseado no Windows
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
description: Aprenda a verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços no DNS baseado no Windows para a Microsoft.
ms.openlocfilehash: 8202ffe10b4a0ff9c94d863d92fc55c47ebb38d3
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/11/2020
ms.locfileid: "49656838"
---
# <a name="create-dns-records-for-microsoft-using-windows-based-dns"></a>Criar registros DNS para a Microsoft usando o DNS baseado no Windows

 Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.yml)**. 
   
Se você hospedar seus próprios registros DNS usando um DNS baseado no Windows, siga as etapas neste artigo para configurar seus registros para email, Skype for Business Online e assim por diante.
  
Para começar, você precisa encontrar seus registros DNS no DNS baseado no Windows para poder [atualizá-los.](#find-your-dns-records-in-windows-based-dns) Além disso, se você estiver planejando sincronizar seu Active Directory local com a Microsoft, consulte o endereço de email não-rouável usado como um UPN em seu [Active Directory local.](#non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory)
  
Problemas com o fluxo de emails ou outros problemas após a adição de registros DNS, consulte Solucionar problemas após alterar o nome de domínio [ou registros DNS.](../get-help-with-domains/find-and-fix-issues.md) 
  
## <a name="find-your-dns-records-in-windows-based-dns"></a>Localize seus registros DNS no DNS baseado no Windows
<a name="BKMK_find_your_dns_1"></a> Vá para a página que tem os registros DNS do seu domínio. Se você estiver trabalhando no Windows Server 2008, vá para **Iniciar**  >  **Executar.** Se você estiver trabalhando no Windows Server 2012, pressione a tecla windows e **r**. Digite **dnsmgmnt.msc** e selecione **OK**. No Gerenciador DNS, **\<DNS server name\> \> expanda Zonas de Pesquisa Encaminhar.** Selecionar seu domínio. Você está pronto para criar os registros DNS.
   
## <a name="add-mx-record"></a>Adicionar registro MX
<a name="BKMK_add_MX"> </a>

Adicione um registro MX para que o email do seu domínio vá para a Microsoft.
- O registro MX que você adicionará  inclui um valor (os pontos para o valor de endereço) que se parece com isto: .mail.protection.outlook.com, onde é um valor como \<MX token\> \<MX token\> MSxxxxxxx. 
- Na linha MX na seção Exchange Online da página Adicionar registros DNS na Microsoft, copie o valor listado em Pontos a tratar. Você usará esse valor no registro que está criando nesta tarefa. 
- Na página Gerenciador DNS do domínio, vá para **Action**  >  **Mail Exchanger (MX).** Para encontrar essa página para o domínio, consulte [Encontrar seus registros DNS no DNS baseado no Windows.](#find-your-dns-records-in-windows-based-dns)  
- Na caixa **de diálogo Registro de Novo** Recurso, certifique-se de que os campos estão definidos com precisão para os seguintes valores: 
    - Nome do Host:  
    - @Address: colar os pontos para o valor de endereço que você acabou de copiar da Microsoft aqui.  
    - Pré-f: 
- Selecione **Salvar Alterações.**
- Remova qualquer registro MX obsoleto. Se você tiver algum registro MX antigo para esse domínio que roteie emails para outro local, marque a caixa de seleção ao lado de cada registro antigo e selecione **Excluir**  >  **OK**. 
   
## <a name="add-cname-records"></a>Adicionar registros CNAME
<a name="BKMK_add_CNAME"> </a>

Adicione os registros CNAME necessários para a Microsoft. Se registros CNAME adicionais estão listados na Microsoft, adicione-os seguindo as mesmas etapas gerais mostradas aqui.
  
> [!IMPORTANT]
> Se você tiver o Gerenciamento de Dispositivo Móvel (MDM) para a Microsoft, deverá criar dois registros CNAME adicionais. Siga o procedimento que você usou para os outros quatro registros CNAME, mas forneça os valores da tabela a seguir. (Se você não tiver o MDM, ignore esta etapa.) 

- Na página do Gerenciador DNS do domínio, vá para  >  **CNAME (CNAME) da Ação.**
- Na caixa **de diálogo Registro de Novo** Recurso, certifique-se de que os campos estão definidos com precisão para os seguintes valores:  
    - Nome do host: autodiscover
    - Tipo: 
    - CNAMEAddress: autodiscover.outlook.com
- Selecione **O** K.

Adicione o registro CNAME SIP. 
- Na página do Gerenciador DNS do  domínio, vá para \> **CNAME (CNAME) da Ação.** 
- Na caixa **de diálogo Registro de Novo** Recurso, certifique-se de que os campos estão definidos com precisão para os seguintes valores:  
    - Nome do Host: sip
    - Tipo: CNAME
    - Endereço: sipdir.online.lync.com
- Selecione **OK**.

Adicione o registro CNAME de Descoberta Automática do Skype for Business Online.  
- Na página Gerenciador DNS do domínio, vá **para** \> **CNAME (CNAME) da Ação.** Na caixa **de diálogo Registro de Novo** Recurso, certifique-se de que os campos estão definidos com precisão para os seguintes valores:  
    - Nome do host: lyncdiscover
    - Tipo: CNAME
    - Endereço: webdir.online.lync.com
- Selecione **OK**.
   
### <a name="add-two-cname-records-for-mobile-device-management-mdm-for-microsoft"></a>Adicionar dois registros CNAME para o Gerenciamento de Dispositivo Móvel (MDM) para a Microsoft

> [!IMPORTANT]
> Se você tiver o Gerenciamento de Dispositivo Móvel (MDM) para a Microsoft, deverá criar dois registros CNAME adicionais. Siga o procedimento que você usou para os outros quatro registros CNAME, mas forneça os valores da tabela a seguir. >(Se você não tiver o MDM, ignore esta etapa.) 
  

Adicione o registro CNAME Enterpriseregistration do MDM.  
- Na página do Gerenciador DNS do  domínio, vá para \> **CNAME (CNAME) da Ação.** 
- Na caixa **de diálogo Registro de Novo** Recurso, certifique-se de que os campos estão definidos com precisão para os seguintes valores:  
- Nome do host: enterpriseregistration
- Tipo: CNAME
- Endereço: enterpriseregistration.windows.net
- Selecione **OK**. 

Adicione o registro CNAME Enterpriseenrollment do MDM. 
-  Na página do Gerenciador DNS do  domínio, vá para \> **CNAME (CNAME) da Ação.** 
-  Na caixa **de diálogo Registro de Novo** Recurso, certifique-se de que os campos estão definidos com precisão para os seguintes valores:  
    - Nome do host: enterpriseenrollment
    - Tipo: CNAME
    - Endereço: enterpriseenrollment-s.manage.microsoft.com
- Selecione **OK**.
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Não é possível ter mais de um registro TXT para SPF para um domínio. Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam. Se você já possui um registro SPF para seu domínio, não crie um novo para a Microsoft. Em vez disso, adicione os valores necessários da Microsoft ao registro atual para que você tenha um único registro  *SPF*  que inclua ambos os conjuntos de valores. 
  
Adicione o registro TXT SPF do seu domínio ajudar a evitar spam de email.
  
- Você pode já ter outras cadeias de caracteres no valor TXT para este registro (como cadeias de caracteres para email de marketing), o que é bom. Deixe essas cadeias de caracteres e adicione este tipo, colocando aspas duplas em cada cadeia para separá-las. 
- Na página Gerenciador DNS do seu domínio, vá para **Texto** \> **da Ação (TXT).** 
-  Na caixa **de diálogo Registro de Novo** Recurso, certifique-se de que os campos estão definidos com precisão para os seguintes valores. 
 > [!IMPORTANT]
> Em algumas versões do Gerenciador DNS do Windows, o domínio pode ter sido definido para que, quando você cria um registro txt, o nome da página principal padrão seja o domínio pai. Nesta situação, ao adicionar um registro TXT, deixe o nome do host em branco (nenhum valor) em vez de defini-lo como @ ou como o nome de domínio. 

-  Tipo de host: @
-  Tipo de registro: TXT
-  Endereço: v=spf1 include:spf.protection.outlook.com -all 
         
-  Selecione **OK**.
   
## <a name="add-srv-records"></a>Adicionar registros SRV
<a name="BKMK_add_SRV"> </a>

Adicione os dois registros SRV necessários para a Microsoft.

Adicione o registro SRV SIP para a Webconferência do Skype for Business Online.  <br/> 
-  Na página Gerenciador DNS do seu domínio, vá para **Ação** \> **Outros Novos Registros.** 
-   Na janela **Tipo de Registro de** Recurso, selecione Local do Serviço **(SRV)** e, em seguida, **selecione Criar Registro.** 
-   Na caixa **de diálogo Registro de Novo** Recurso, certifique-se de que os campos estão definidos com precisão para os seguintes valores:  
    -  Serviço: _sip
    -  Protocolo: _tls
    -  Priority: 100
    -  Peso: 1
    -  Porta: 443
    -  Destino (Nome do host): sipdir.online.lync.com
-  Selecione **OK**. 


Adicione o registro SRV SIP para a federação do Skype for Business Online.  
-  Na página Gerenciador DNS do seu domínio, vá para **Ação** \> **Outros Novos Registros.**  
-  Na janela **Tipo de Registro de** Recurso, selecione Local do Serviço **(SRV)** e, em seguida, **selecione Criar Registro.** 
-   Na caixa **de diálogo Registro de Novo** Recurso, certifique-se de que os campos estão definidos com precisão para os seguintes valores:  
    -  Serviço: _sipfederationtls
    -  Protocolo: _tcp
    -  Priority: 100
    -  Peso: 1
    -  Porta: 5061
    -  Destino (Nome do host): sipfed.online.lync.com
-  Selecione **OK**. 
   
## <a name="add-a-record-to-verify-that-you-own-the-domain-if-you-havent-already"></a>Adicione um registro para verificar se você é o proprietário do domínio, se ainda não fez isso.
<a name="BKMK_verify"> </a>

Antes de adicionar os registros DNS para configurar seus serviços Microsoft, a Microsoft precisa confirmar se você é o domínio que você está adicionando. Para tanto, você adicionará um registro, seguindo as etapas abaixo.
  
> [!NOTE]
> Esse registro só é usado para confirmar que você é proprietário do domínio. Ele não afeta mais nada. 
  

1. Coletar informações da Microsoft.  <br/> 
2. No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>. 
3. Na página **Domínios,** na coluna **Ações** do domínio que você está verificando, selecione **Iniciar configuração.** 
4. Na página **Adicionar um domínio à Microsoft,** selecione Iniciar etapa **1.** 
5. On the **Confirm that you own your domain** page, in the See instructions for performing this step **with** drop-down list, choose **General instructions**. 
6. Na tabela, copie o valor Destino ou Pontos para Endereço. Você precisará dele para a etapa seguinte. É recomendável copiar e colar este valor, para que todo o espaçamento permaneça correto.

Adicione um registro TXT. 
-  Na página Gerenciador DNS do seu domínio, vá para **Texto** \> **da Ação (TXT).** 
-   Na caixa **de diálogo Registro de Novo** Recurso, selecione **Editar**.  
-  Na área Nomes de  **Host Personalizados** da caixa de diálogo Registro de Novo Recurso, certifique-se de que os campos estão definidos com precisão para os seguintes valores. 

> [!IMPORTANT] 
> Em algumas versões do Gerenciador DNS do Windows, o domínio pode ter sido definido para que, quando você cria um registro txt, o nome da página principal padrão seja o domínio pai. Nesta situação, ao adicionar um registro TXT, deixe o nome do host em branco (nenhum valor) em vez de defini-lo como @ ou como o nome de domínio. 

- Nome do host: @
- Tipo: TXT
- Endereço: Colar o valor Destino ou Pontos de Endereço que você acabou de copiar da Microsoft aqui.  
- Selecione **OK**  >  **Feito.**

Verifique seu domínio na Microsoft.  
> [!IMPORTANT]
> Aguarde cerca de 15 minutos antes de fazer isso, para que o registro que você acabou de criar possa ser atualizado pela Internet.       

- Volte para a Microsoft e siga as etapas abaixo para solicitar uma verificação. A verificação procura o registro TXT adicionado na etapa anterior. Quando encontrar o registro TXT correto, o domínio será verificado.  
1. No centro de administração, vá para a página **Configurar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domínios.</a>
2. Na página **Domínios,** na coluna **Ação** do domínio que você está verificando, selecione **Iniciar configuração.** 
3. On the **Confirm that you own your domain** page, select **done, verify now**, and then in the confirmation dialog box, select **Finish**. 
   
> [!NOTE]
>  Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory"></a>Endereço de email não roteável utilizado como um UPN no seu Active Directory local
<a name="BKMK_ADNote"> </a>

Se você estiver planejando sincronizar seu Active Directory local com a Microsoft, certifique-se de que o sufixo upn (nome upn) do Active Directory seja um sufixo de domínio válido e não um sufixo de domínio sem suporte, como @contoso.local. Se você precisar alterar o sufixo UPN, consulte Como preparar um domínio não-rouável [para a sincronização de diretórios.](https://docs.microsoft.com/microsoft-365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization)
  
> [!NOTE]
>  Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
