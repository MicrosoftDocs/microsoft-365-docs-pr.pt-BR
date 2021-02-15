---
title: Criar registros DNS no Dyn.com para a Microsoft
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
ms.assetid: 34e57a00-2a7d-469c-beec-089423f18369
description: Aprenda a verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços no Dyn.com para a Microsoft.
ms.openlocfilehash: d1b77d6b4f38dd3e0979f448a77b293564841f45
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/11/2020
ms.locfileid: "49657931"
---
# <a name="create-dns-records-at-dyncom-for-microsoft"></a>Criar registros DNS no Dyn.com para a Microsoft

 **[Caso não encontre o conteúdo que está procurando, verifique as perguntas frequentes sobre domínios](../setup/domains-faq.yml)**. 
  
Se você usa a Dyn.com como provedor de hospedagem DNS, siga as etapas deste artigo para verificar o domínio e configurar registros DNS para o Skype for Business Online, email e outros serviços.
 

  
> [!NOTE]
>  Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Adicionar um registro TXT para verificação
<a name="BKMK_verify"> </a>

1. Para iniciar, vá até a sua página de domínios em Dyn.com usando [este link](https://account.dyn.com/dns/). Você será solicitado a fazer o logon pela primeira vez.
    
    ![Captura de tela da opção Convidar mais pessoas](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. Na página **Serviços de Nível de Zona,** selecione **Dyn Standard DNS Service** para o domínio que você deseja editar. 
    
3. Na página **DNS** do seu domínio, selecione **Preferências.**
    
4. Selecione **Habilitar Interface especializada.**
    
5. In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Host**|**TTL**|**Tipo**|**Dados**|
    |:-----|:-----|:-----|:-----|
    |(Leave this field empty.)  <br/> |600  <br/> |TXT  <br/> |MS = ms *XXXXXXXX*  <br/> **Observação**: esse é um exemplo. Use aqui seu valor específico de **Destino ou Pontos de Endereçamento**, retirado da tabela.           [Como localizo isto?](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![Dyn-BP-Verify-1-1](../../media/b3730b15-a313-4b4c-b91e-646eebb649e8.png)
  
6. Selecione **Criar Registro.**
    
    ![Dyn-BP-Verify-1-2](../../media/8b63b4ee-dbd7-44a7-b1e6-c6892b02f13e.png)
  
7. Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.
    
Agora que você adicionou o registro no site do seu registrador de domínios, retorne à Microsoft e solicite o registro.
  
Quando a Microsoft encontrar o registro TXT correto, seu domínio estará verificado.
  
1. No centro do administrador da Microsoft, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.

    
2. Na página **Domínios**, clique no domínio que você está verificando. 
    
    
  
3. Na página **Configuração**, clique em **Iniciar configuração**.
    
    
  
4. Na página **Verificar domínio**, marque **Verificar**.
    
    
  
> [!NOTE]
>  Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Adicione um registro MX para que o email do domínio vá para a Microsoft.
<a name="BKMK_add_MX"> </a>

1. Para iniciar, vá até a sua página de domínios em Dyn.com usando [este link](https://account.dyn.com/dns/). Você será solicitado a fazer o logon pela primeira vez.
    
    ![Captura de tela da opção Convidar mais pessoas](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. Na página **Serviços de Nível de Zona,** selecione **Dyn Standard DNS Service** para o domínio que você deseja editar. 
    
3. Na página DNS do seu domínio, selecione **Preferências.**
    
4. Selecione **Habilitar Interface especializada.**
    
5. In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Host**|**TTL**|**Tipo**|**Dados**|
    |:-----|:-----|:-----|:-----|
    |(Leave this field empty.)  <br/> |600  <br/> |MX  <br/> |10  *\<domain-key\>*  .mail.protection.outlook.com.  <br/> **Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)** <br/> O **10** é o valor de prioridade de MX. Adicione-o ao início do valor de MX, separado do restante do valor por um espaço.  <br/> **Observação:** Obter o  *\<domain-key\>*  seu da sua conta da Microsoft.           [Como localizo isto?](../get-help-with-domains/information-for-dns-records.md)      <br>    Para saber mais sobre prioridade, confira [O que é prioridade MX?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) <br/> |
   
    ![Dyn-BP-Configure-2-1](../../media/62ac77b7-c84d-426d-9ec4-a28d6479ad04.png)
  
6. Selecione **Criar Registro.**
    
    ![Dyn-BP-Configure-2-2](../../media/e84e2cca-75e3-4584-8a98-f2f89cb71bd3.png)
  
7. Caso haja outros registros MX, remova-os marcando a caixa de seleção de cada um na coluna **Excluir**. 
    
    ![flores e texto](../../media/f24f02cc-c0b7-42cf-a2ff-4d0fc203e4de.png)
  
8. Selecione **Aplicar Alterações.**
    
    ![Dyn-BP-Configure-2-4](../../media/0cc23c2b-b6f2-4f58-af20-4c6506de7b43.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>Adicionar os seis registros CNAME necessários para a Microsoft
<a name="BKMK_add_CNAME"> </a>

1. Para iniciar, vá até a sua página de domínios em Dyn.com usando [este link](https://account.dyn.com/dns/). Você será solicitado a fazer o logon pela primeira vez.
    
    ![Captura de tela da opção Convidar mais pessoas](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. Na página **Serviços de Nível de Zona,** selecione **Dyn Standard DNS Service** para o domínio que você deseja editar. 
    
3. Na página **DNS** do seu domínio, selecione **Preferências.**
    
4. Selecione **Habilitar Interface especializada.**
    
5. Adicione o primeiro dos seis registros CNAME.
    
    Na seção **Adicionar um Registro DNS**, nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir. 
    
    (Escolha o valor de **Tipo** na lista suspensa.) 
    
    |**Host**|**TTL**|**Tipo**|**Dados**|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |600  <br/> |CNAME  <br/> |autodiscover.outlook.com.  <br/> **Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)** <br/> |
    |sip  <br/> |600  <br/> |CNAME  <br/> |sipdir.online.lync.com.  <br/> **Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)** <br/> |
    |lyncdiscover  <br/> |600  <br/> |CNAME  <br/> |webdir.online.lync.com.  <br/> **Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)** <br/> |
    |enterpriseregistration  <br/> |600  <br/> |CNAME  <br/> |enterpriseregistration.windows.net.  <br/> **Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)** <br/> |
    |enterpriseenrollment  <br/> |600  <br/> |CNAME  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> **Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)** <br/> |
   
    ![Dyn-BP-Configure-3-1](../../media/1fd80695-d3d7-4298-9ebe-97a69f46f1b2.png)
  
6. Selecione **Criar Registro.**
    
    ![Dyn-BP-Configure-3-2](../../media/89551495-3fa5-44ab-96b2-855f70be0880.png)
  
7. Adicione os cinco registros CNAME restantes.
    
    Na seção **Adicionar Registro DNS,** crie um registro usando os valores da próxima  linha na tabela e selecione Criar Registro novamente para concluir esse registro. 
    
    Repita esse processo até ter criado todos os seis registros CNAME.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Não é possível ter mais de um registro TXT para SPF para um domínio. Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam. Se você já possui um registro SPF para seu domínio, não crie um novo para a Microsoft. Em vez disso, adicione os valores necessários da Microsoft ao registro atual para que você tenha um único registro  *SPF*  que inclua ambos os conjuntos de valores.
  
1. Para iniciar, vá até a sua página de domínios em Dyn.com usando [este link](https://account.dyn.com/dns/). Você será solicitado a fazer o logon pela primeira vez.
    
    ![Captura de tela da opção Convidar mais pessoas](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. Na página **Serviços de Nível de Zona,** selecione **Dyn Standard DNS Service** para o domínio que você deseja editar. 
    
3. Na página **DNS** do seu domínio, selecione **Preferências.**
    
4. Selecione **Habilitar Interface especializada.**
    
5. In the **Add DNS Record** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Host**|**TTL**|**Tipo**|**Dados**|
    |:-----|:-----|:-----|:-----|
    |(Leave this field empty.)  <br/> |600  <br/> |TXT  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.           |
   
    ![Dyn-BP-Configure-4-1](../../media/f8511349-3ea2-40c3-9853-98e1a58a91b5.png)
  
6. Selecione **Criar Registro.**
    
    ![Campo de vários valores](../../media/bbe04835-d3c0-4146-8123-9781bb9eca51.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Adicionar os dois registros SRV necessários para a Microsoft
<a name="BKMK_add_SRV"> </a>

1. Para iniciar, vá até a sua página de domínios em Dyn.com usando [este link](https://account.dyn.com/dns/). Você será solicitado a fazer logon primeiro 
    
    ![Captura de tela da opção Convidar mais pessoas](../../media/77597d44-9b04-43b1-8e23-d4fad238def2.png)
  
2. Na página **Serviços de Nível de Zona,** selecione **Dyn Standard DNS Service** para o domínio que você deseja editar. 
    
3. Na página **DNS** do seu domínio, selecione **Preferências.**
    
4. Selecione **Habilitar Interface especializada.**
    
5. Adicione o primeiro dos dois registros SRV.
    
    Na seção **Adicionar um Registro DNS**, nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir. 
    
    (Escolha o valor de **Tipo** na lista suspensa.) 
    
    |**Host**|**TTL**|**Tipo**|**Dados**|
    |:-----|:-----|:-----|:-----|
    |_sip._tls|600|SRV|100 1 443 sipdir.online.lync.com. **Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**<br>**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.           |
    |_sipfederationtls._tcp|600|SRV|100 1 5061 sipfed.online.lync.com. **Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**<br> **Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.           |
   
    ![Dyn-BP-Configure-5-1](../../media/a6873411-f4ce-4327-9145-02d435930976.png)
  
6. Selecione **Criar Registro.**
    
    ![configurar opções de vídeo](../../media/e6f33452-e527-473b-a645-b31ed70b0d43.png)
  
7. Adicione o outro registro SRV.
    
    Na seção **Adicionar Registro DNS,** crie um registro usando os valores da segunda  linha na tabela e selecione Criar Registro novamente para concluir esse registro. 
    
> [!NOTE]
>  Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
