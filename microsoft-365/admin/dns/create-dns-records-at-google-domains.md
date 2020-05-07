---
title: Criar registros DNS no Google Domains para Microsoft
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
ms.assetid: 0db29490-2612-48bc-9b77-1862e7a41a8c
description: Saiba como verificar seu domínio e configurar registros DNS para email, Lync e outros serviços no Google Domains for Microsoft.
ms.openlocfilehash: 6bfe32ba8f77adec97f4ab5ee40e92126be91f10
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049006"
---
# <a name="create-dns-records-at-google-domains-for-microsoft"></a>Criar registros DNS no Google Domains para Microsoft

 **Caso não encontre o conteúdo que está procurando, [verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**. 
  
Se você usa o Google Domains como provedor de hospedagem DNS, realize os procedimentos deste artigo para verificar o domínio e configurar registros DNS para email, Lync e outros serviços.
  
Depois que você adicionar esses registros no Google Domains, o domínio será configurado para funcionar com os serviços da Microsoft.
  

  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você estiver tendo problemas com o fluxo de emails ou com outros problemas após adicionar registros DNS, consulte [Localizar e corrigir problemas após adicionar seu domínio ou registros DNS no Microsoft](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Adicionar um registro TXT para verificação
<a name="BKMK_verify"> </a>

Antes de usar o seu domínio com a Microsoft, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro de DNS prova à Microsoft que você é o proprietário do domínio.
  
> [!NOTE]
> Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar. 
  
1. Para iniciar, vá até a página do seu domínio no Google Domains usando [este link](https://domains.google.com/registrar). Você será solicitado a entrar. Para fazer isso:
    
1. Selecione **entrar**.
    
2. Digite suas credenciais de logon e, em seguida, selecione **entrar**novamente.
    
2. Na página **meus domínios** , localize o domínio que você deseja usar com a Microsoft e selecione o link **gerenciar** ao lado dele. No painel de navegação à esquerda, selecione **DNS**.
    
3. In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (You may have to scroll down.)
    
    (Choose the **Type** value from the drop-down list.) 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |**Nome** <br/> |**Tipo** <br/> |**TTL** <br/> |**Dados** <br/> |
    |@  <br/> |TXT  <br/> |1H  <br/> |MS = ms *XXXXXXXX*  <br/> **Observação**: esse é um exemplo. Use aqui seu valor específico de **Destino ou Pontos de Endereçamento**, retirado da tabela. [Como localizo isto?](../get-help-with-domains/information-for-dns-records.md)          |
   
4. Clique em **Adicionar**.
    
5. Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.
    
Agora que você adicionou o registro no site do seu registrador de domínios, retorne à Microsoft e solicite o registro.
  
Quando a Microsoft encontrar o registro TXT correto, seu domínio estará verificado.
  
1. No centro do administrador da Microsoft, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.

    
2. Na página **Domínios**, clique no domínio que você está verificando. 
    
3. Na página **Configuração**, clique em **Iniciar configuração**.
    
4. Na página **Verificar domínio**, clique em **Verificar**.
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Adicione um registro MX para que o email do domínio vá para a Microsoft.
<a name="BKMK_add_MX"> </a>

1. Para iniciar, vá até a página do seu domínio no Google Domains usando [este link](https://domains.google.com/registrar). Você será solicitado a entrar. Para fazer isso:
    
2. Selecione **entrar**.
    
3. Digite suas credenciais de logon e, em seguida, selecione **entrar**novamente.
4. Na página **domínios** , na seção **domínio** , selecione **Configurar DNS** para o domínio que você deseja editar.
    
    > [!IMPORTANT]
    > Se tiver uma conta de email do G Suite, primeiro você deve excluir os registros MX associados a essa conta. Os registros MX do G Suite impedem que você adicione qualquer outro registro MX, incluindo aqueles necessários para a Microsoft. Excluir os registros do G Suite não exclui sua conta do G Suite. Para excluir os registros MX do G Suite, siga as etapas a seguir. 
  
5. Na seção **registros sintéticos** , na área **G Suite** , selecione **excluir**.
    
    (You may have to scroll down.)
    
    ![Selecione Excluir na seção registros sintéticos](../../media/bd276b5d-5667-4bb1-a233-2dc5194e7ace.png)
  
6. Selecione **Excluir**.
    
    ![Selecione Excluir](../../media/4413a45a-5b82-4ec6-82c6-0091f5be9696.png)
  
7. In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (You may have to scroll down.)
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Nome**|**Tipo**|**TTL**|**Dados**|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |MX  <br/> |1H  <br/> |0  *\<chave-de-domínio\>*  .mail.protection.outlook.com.  <br/> **Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)** <br/> O **0** é o valor de prioridade de MX. Adicione-o ao início do valor de MX, separado do restante do valor por um espaço.  <br/> **Observação:** Obtenha a sua \<*chave-de-domínio*\> através da sua conta Microsoft.  [Como faço para encontrar isso?](../get-help-with-domains/information-for-dns-records.md)          Para saber mais sobre prioridade, consulte [O que é prioridade MX?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) <br/> |
   
    ![Digitar ou colar valores na seção registros de recursos personalizados](../../media/b660ca9e-984d-449f-ae59-a65fe4e2c6bd.png)
  
5. Selecione **Adicionar**.
    
    ![Selecione Adicionar](../../media/32f8f23c-0b80-48da-b08e-4e04052971af.png)
  
6. Se houver outros registros MX personalizados, remova-os:
    
1. Selecione **Editar** na linha do registro MX. 
    
    ![Selecionar Editar na linha do registro MX](../../media/acc53ae9-3b8a-421d-8d11-d4a4108b2353.png)
  
2. Para cada um dos outros registros MX personalizados, selecione a entrada na caixa **dados** e, em seguida, pressione a tecla **delete** no teclado para excluir esse registro. 
    
    Continue até excluir a entrada **Dados** para cada um dos outros registros MX. 
    
    ![Delete entries in the Data box](../../media/28192089-7b38-4d2e-9d52-9b83422c27d5.png)
  
7. Quando tiver excluído a entrada de **dados** de cada um dos outros registros MX, selecione **salvar** para salvar suas alterações. 
    
    ![Selecione salvar](../../media/bf496d01-ccbe-4800-95f4-7b2283f2e5f6.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a>Adicionar os cinco registros CNAME necessários para o Microsoft

1. Para começar, vá até a sua página [Google Domains] (https://domains.google.com/registrar) e entre.
    
2. Na página **domínios** , na seção **domínio** , selecione **Configurar DNS** para o domínio que você deseja editar. 
    
3. Adicione o primeiro registro CNAME.
    
    Na seção **Registros de recursos personalizados**, nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir. 
    
    (You may have to scroll down.)
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Nome**|**Tipo**|**TTL**|**Dados**|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |1H  <br/> |autodiscover.outlook.com.  <br/> **This value MUST end with a period (.)** <br/> |
    |sip  <br/> |CNAME  <br/> |1H  <br/> |sipdir.online.lync.com.  <br/> **This value MUST end with a period (.)** <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |1H  <br/> |webdir.online.lync.com.  <br/> **This value MUST end with a period (.)** <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |1H  <br/> |enterpriseregistration.windows.net.  <br/> **This value MUST end with a period (.)** <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |1H  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> **This value MUST end with a period (.)** <br/> |
   
    ![Digitar ou colar valores na seção registros de recursos personalizados](../../media/cff9832a-6d57-421f-a183-55320974ed87.png)
  
4. Selecione **Adicionar**.
    
    ![Selecione Adicionar](../../media/4a78080a-e0b2-4582-9696-3fe4fea41e91.png)
  
5. Adicione os outros quatro registros CNAME.
    
    Na seção **registros de recursos personalizados** , crie um registro usando os valores da próxima linha na tabela e, em seguida, selecione **Adicionar** para concluir esse registro. 
    
    Repita esse processo até ter criado todos os registros CNAME necessários.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail

> [!IMPORTANT]
> Não é possível ter mais de um registro TXT para SPF para um domínio. Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam. Se você já possui um registro SPF para seu domínio, não crie um novo para a Microsoft. Em vez disso, adicione os valores necessários da Microsoft ao registro atual para que você tenha um único registro SPF que inclua os dois conjuntos de valores. Precisa de exemplos? Confira os [Registros do Sistema de Nomes de Domínios externos para a Microsoft](https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records#bkmk_spfrecords). To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md). 
  
1. Para iniciar, vá até a página do seu domínio no Google Domains usando [este link](https://domains.google.com/registrar). Você será solicitado a entrar. Para fazer isso:
    
1. Selecione **entrar**.
    
2. Digite suas credenciais de logon e, em seguida, selecione **entrar**novamente.
    
3. Na página **domínios** , na seção **domínio** , selecione **Configurar DNS** para o domínio que você deseja editar. 
    
4. Na seção **registros de recursos personalizados** , na linha do registro TXT, selecione **Editar**. 
    
    > [!IMPORTANT]
    > O Google Domains armazena registros TXT como um conjunto que pode conter vários registros. Quando tiver pelo menos um outro registro TXT, como o registro TXT que você usou para verificar seu domínio, adicione novos registros TXT para esse conjunto de registros. Qualquer tentativa inserir registros TXT adicionais como entradas separadas resultará em uma mensagem de erro de **registro duplicado** 
  
    ![Selecionar Editar na linha do registro TXT](../../media/eae14850-8d0c-4f29-8587-df8b36129d5f.png)
  
5. Selecione o controle **(+)** . 
    
    ![Selecione o controle de adição](../../media/628604cc-d2b2-42a5-bb5b-13c327b85d9f.png)
  
6. Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela.
    
    (Pode ser necessário rolar para baixo.)
    
    |**Dados**|
    |:-----|
    |v=spf1 include:spf.protection.outlook.com -all  <br/> 

    > [!NOTE]
    > É recomendável copiar e colar essa entrada, para que todo o espaçamento permaneça correto.           
   
   ![Digitar ou colar valores na seção registros de recursos personalizados](../../media/4645cc4f-9fcc-4626-9674-072ed6fa34c2.png)
  
7. Selecione **Salvar**.
    
    ![Selecione salvar](../../media/20c4c926-f062-4048-9265-bf752be54e0c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Adicionar os dois registros SRV necessários para a Microsoft
<a name="BKMK_add_SRV"> </a>

1. Para iniciar, vá até a página do seu domínio no Google Domains usando [este link](https://domains.google.com/registrar). Você será solicitado a entrar. Para fazer isso:
    
2. Selecione **entrar**.
    
3. Digite suas credenciais de logon e, em seguida, selecione **entrar**novamente.
    
4. Na página **domínios** , na seção **domínio** , selecione **Configurar DNS** para o domínio que você deseja editar. 
    
5. Adicione o primeiro registro SRV.
    
    In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (You may have to scroll down.)
    
    (Choose the **Type** value from the drop-down list.) 
    
    |**Nome**|**Tipo**|**TTL**|**Dados**|
    |:-----|:-----|:-----|:-----|
    |_sip. _tls|SRV|1H|100 1 443 sipdir.online.lync.com. **Esse valor deve terminar com um ponto (.)** **Observação:** É recomendável copiar e colar essa entrada, para que todo o espaçamento permaneça correto.           |
    |_sipfederationtls. _tcp|SRV|1H|100 1 5061 sipfed.online.lync.com. **This value MUST end with a period (.)**

    É recomendável copiar e colar essa entrada, para que todo o espaçamento permaneça correto.       
   
    ![Digitar ou colar valores na seção registros de recursos personalizados](../../media/429d06a9-c0af-4961-b7d2-7a8dea6db37e.png)
  
6. Selecione **Adicionar**.
    
    ![Selecione Adicionar](../../media/89df6efd-e641-4441-baa2-d9a890424569.png)
  
7. Adicione o outro registro SRV.
    
    Na seção **registros de recursos personalizados** , crie um registro usando os valores da segunda linha da tabela e, em seguida, selecione **Adicionar** para concluir esse registro. 
    
    > [!NOTE]
    > Typically it takes about 15 minutes for DNS changes to take effect. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
