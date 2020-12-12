---
title: Criar registros DNS no site Google Domains para a Microsoft
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
ms.assetid: 0db29490-2612-48bc-9b77-1862e7a41a8c
description: Aprenda a verificar seu domínio e a configurar registros DNS para emails, Lync e outros serviços no Google Domains para a Microsoft.
ms.openlocfilehash: a20b08d92814865cee5b169cb435b898a6b068ac
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/11/2020
ms.locfileid: "49657858"
---
# <a name="create-dns-records-at-google-domains-for-microsoft"></a>Criar registros DNS no site Google Domains para a Microsoft

 Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.yml)**. 
  
Se você usa o Google Domains como provedor de hospedagem DNS, realize os procedimentos deste artigo para verificar o domínio e configurar registros DNS para email, Lync e outros serviços.
  
Depois que você adicionar esses registros ao Google Domains, o domínio será configurado para funcionar com os serviços Microsoft.
  

  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, confira [Localizar e corrigir problemas após alterar o nome de domínio ou registros DNS na Microsoft](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Adicionar um registro TXT para verificação
<a name="BKMK_verify"> </a>

Antes de usar o seu domínio com a Microsoft, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro de DNS prova à Microsoft que você é o proprietário do domínio.
  
> [!NOTE]
> Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar. 
  
1. Para iniciar, vá até a página do seu domínio no Google Domains usando [este link](https://domains.google.com/registrar). Você será solicitado a entrar. Para fazer isso:
    
1. Selecione **Entrar**.
    
2. Em seguida, insira suas credenciais de login e selecione novamente **Entrar**.
    
2. Na página **Meus domínios**, localize o domínio que você deseja usar com a Microsoft e selecione o link **GERENCIAR** ao lado dele. No painel de navegação esquerdo, selecione **DNS**.
    
3. Na seção **Registros de recursos personalizados**, nas caixas do novo registro, digite ou copie e cole os valores da tabela a seguir. 
    
    (Pode ser necessário rolar para baixo.)
    
    (Selecione o valor **Tipo** na lista suspensa.) 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |**Name** <br/> |**Tipo** <br/> |**TTL** <br/> |**Dados** <br/> |
    |@  <br/> |TXT  <br/> |1H  <br/> |MS=ms *XXXXXXXX*  <br/> **Observação**: esse é um exemplo. Use aqui seu valor específico de **Destino ou Pontos de Endereçamento**, retirado da tabela. [Como localizo isto?](../get-help-with-domains/information-for-dns-records.md)          |
   
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
    
2. Selecione **Entrar**.
    
3. Em seguida, insira suas credenciais de login e selecione novamente **Entrar**.
4. Na página **Domínios**, na seção **Domínio**, escolha **Configurar DNS** para o domínio que você deseja editar.
    
    > [!IMPORTANT]
    > Se tiver uma conta de email do G Suite, primeiro você deve excluir os registros MX associados a essa conta. Os registros MX do G Suite impedem que você adicione outros registros MX, incluindo aqueles necessários para a Microsoft. Excluir os registros do G Suite não exclui sua conta do G Suite. Para excluir os registros MX do G Suite, siga as etapas a seguir. 
  
5. Na seção **Registros sintéticos**, na área **G Suite**, escolha **Excluir**.
    
    (Pode ser necessário rolar para baixo.)
    
    ![Selecione Excluir na seção Registros sintéticos](../../media/bd276b5d-5667-4bb1-a233-2dc5194e7ace.png)
  
6. Selecione **Excluir**.
    
    ![Selecionar Excluir](../../media/4413a45a-5b82-4ec6-82c6-0091f5be9696.png)
  
7. Na seção **Registros de recursos personalizados**, nas caixas do novo registro, digite ou copie e cole os valores da tabela a seguir. 
    
    (Pode ser necessário rolar para baixo.)
    
    (Selecione o valor **Tipo** na lista suspensa.) 
    
    |**Name**|**Tipo**|**TTL**|**Dados**|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |MX  <br/> |1H  <br/> |0  *\<domain-key\>*  .mail.protection.outlook.com.  <br/> **Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)** <br/> O **0** é o valor de prioridade de MX. Adicione-o ao início do valor de MX, separado do restante do valor por um espaço.  <br/> **Observação:** Obtenha a sua \<*domain-key*\> através da sua conta Microsoft.  [Como localizo isto?](../get-help-with-domains/information-for-dns-records.md)          Para saber mais sobre prioridade, confira [O que é prioridade MX?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) <br/> |
   
    ![Digite ou cole os valores na seção de registros de recurso personalizado](../../media/b660ca9e-984d-449f-ae59-a65fe4e2c6bd.png)
  
5. Clique em **Adicionar**.
    
    ![Selecionar Adicionar](../../media/32f8f23c-0b80-48da-b08e-4e04052971af.png)
  
6. Se houver outros registros MX personalizados, remova-os.
    
1. Selecione **Editar** na linha do registro MX. 
    
    ![Selecionar Editar na linha do registro MX](../../media/acc53ae9-3b8a-421d-8d11-d4a4108b2353.png)
  
2. Para cada um dos outros registros MX personalizados, selecione a entrada na caixa **Dados** e pressione a tecla **Delete** do teclado para excluí-los. 
    
    Continue até excluir a entrada **Dados** para cada um dos outros registros MX. 
    
    ![Delete entries in the Data box](../../media/28192089-7b38-4d2e-9d52-9b83422c27d5.png)
  
7. Quando você excluir a entrada **Dados** para cada um dos outros registros MX, selecione **Salvar** para salvar suas alterações. 
    
    ![Selecione Salvar.](../../media/bf496d01-ccbe-4800-95f4-7b2283f2e5f6.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a>Adicionar os cinco registros CNAME necessários para a Microsoft

1. Para começar, vá até a [página Google Domains] (https://domains.google.com/registrar) e entre nela.
    
2. Na página **Domínios**, na seção **Domínio**, escolha **Configurar DNS** para o domínio que você deseja editar. 
    
3. Adicionar o primeiro registro CNAME.
    
    Na seção **Registros de recursos personalizados**, nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir. 
    
    (Pode ser necessário rolar para baixo.)
    
    (Selecione o valor **Tipo** na lista suspensa.) 
    
    |**Name**|**Tipo**|**TTL**|**Dados**|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |1H  <br/> |autodiscover.outlook.com.  <br/> **Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)** <br/> |
    |sip  <br/> |CNAME  <br/> |1H  <br/> |sipdir.online.lync.com.  <br/> **Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)** <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |1H  <br/> |webdir.online.lync.com.  <br/> **Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)** <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |1H  <br/> |enterpriseregistration.windows.net.  <br/> **Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)** <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |1H  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> **Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)** <br/> |
   
    ![Digite ou cole os valores na seção de registros de recurso personalizado](../../media/cff9832a-6d57-421f-a183-55320974ed87.png)
  
4. Clique em **Adicionar**.
    
    ![Selecionar Adicionar](../../media/4a78080a-e0b2-4582-9696-3fe4fea41e91.png)
  
5. Adicione os outros quatro registros CNAME.
    
    Na seção **Registros de recursos personalizados**, crie um registro usando os valores da próxima linha na tabela e, em seguida, selecione novamente **Adicionar** para concluir esse registro. 
    
    Repita esse processo até ter criado todos os registros CNAME necessários.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Adicionar registro TXT à SPF para ajudar a evitar spam de email

> [!IMPORTANT]
> Não é possível ter mais de um registro TXT para SPF para um domínio. Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam. Se você já possui um registro SPF para seu domínio, não crie um novo para a Microsoft. Em vez disso, adicione os valores necessários da Microsoft ao registro atual para que você tenha um único registro SPF que inclua os dois conjuntos de valores. Precisa de exemplos? Confira os [Registros do Sistema de Nomes de Domínios externos para a Microsoft](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records#bkmk_spfrecords). To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.yml). 
  
1. Para iniciar, vá até a página do seu domínio no Google Domains usando [este link](https://domains.google.com/registrar). Você será solicitado a entrar. Para fazer isso:
    
1. Selecione **Entrar**.
    
2. Em seguida, insira suas credenciais de login e selecione novamente **Entrar**.
    
3. Na página **Domínios**, na seção **Domínio**, escolha **Configurar DNS** para o domínio que você deseja editar. 
    
4. Na seção **Registros de recursos personalizados**, na linha do registro TXT, selecione **Editar**. 
    
    > [!IMPORTANT]
    > O Google Domains armazena registros TXT como um conjunto que pode conter vários registros. Quando tiver pelo menos um outro registro TXT, como o registro TXT que você usou para verificar seu domínio, adicione novos registros TXT para esse conjunto de registros. Qualquer tentativa inserir registros TXT adicionais como entradas separadas resultará em uma mensagem de erro de **registro duplicado** 
  
    ![Selecionar Editar na linha do registro TXT](../../media/eae14850-8d0c-4f29-8587-df8b36129d5f.png)
  
5. Selecione o controle **(+)**. 
    
    ![Selecionar o controle de adição](../../media/628604cc-d2b2-42a5-bb5b-13c327b85d9f.png)
  
6. Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela.
    
    (Pode ser necessário rolar para baixo.)
    
    |**Dados**|
    |:-----|
    |v=spf1 include:spf.protection.outlook.com -all  <br/> 

    > [!NOTE]
    > É recomendável copiar e colar essa entrada, para que todo o espaçamento permaneça correto.           
   
   ![Digite ou cole os valores na seção de registros de recurso personalizado](../../media/4645cc4f-9fcc-4626-9674-072ed6fa34c2.png)
  
7. Selecione **Salvar**.
    
    ![Selecione Salvar.](../../media/20c4c926-f062-4048-9265-bf752be54e0c.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Adicionar os dois registros SRV necessários para a Microsoft
<a name="BKMK_add_SRV"> </a>

1. Para iniciar, vá até a página do seu domínio no Google Domains usando [este link](https://domains.google.com/registrar). Você será solicitado a entrar. Para fazer isso:
    
2. Selecione **Entrar**.
    
3. Em seguida, insira suas credenciais de login e selecione novamente **Entrar**.
    
4. Na página **Domínios**, na seção **Domínio**, escolha **Configurar DNS** para o domínio que você deseja editar. 
    
5. Adicione o primeiro registro SRV.
    
    Na seção **Registros de recursos personalizados**, nas caixas do novo registro, digite ou copie e cole os valores da tabela a seguir. 
    
    (Pode ser necessário rolar para baixo.)
    
    (Selecione o valor **Tipo** na lista suspensa.) 
    
    |**Name**|**Tipo**|**TTL**|**Dados**|
    |:-----|:-----|:-----|:-----|
    |_sip._tls|SRV|1H|100 1 443 sipdir.online.lync.com. **Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)** **Observação:** é recomendável copiar e colar essa entrada, para que todo o espaçamento permaneça correto.           |
    |_sipfederationtls._tcp|SRV|1H|100 1 5061 sipfed.online.lync.com. **Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**

    É recomendável copiar e colar essa entrada, para que todo o espaçamento permaneça correto.       
   
    ![Digite ou cole os valores na seção de registros de recurso personalizado](../../media/429d06a9-c0af-4961-b7d2-7a8dea6db37e.png)
  
6. Clique em **Adicionar**.
    
    ![Selecionar Adicionar](../../media/89df6efd-e641-4441-baa2-d9a890424569.png)
  
7. Adicione o outro registro SRV.
    
    Na seção **Registros de recursos personalizados**, crie um registro usando os valores da segunda linha na tabela e, em seguida, selecione novamente **Adicionar** para concluir esse registro. 
    
    > [!NOTE]
    > Typically it takes about 15 minutes for DNS changes to take effect. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
