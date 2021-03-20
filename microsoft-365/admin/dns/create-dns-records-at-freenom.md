---
title: Criar registros DNS no Freenom para a Microsoft
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
ms.assetid: d8ff45a2-19e3-413d-aa64-a9982bd6633c
description: Saiba como verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços no Freenom para Microsoft.
ms.openlocfilehash: 8332d63acf34a7f999b549467494b7819cebf092
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910349"
---
# <a name="create-dns-records-at-freenom-for-microsoft"></a>Criar registros DNS no Freenom para a Microsoft

[Verifique as Perguntas Frequentes de ](../setup/domains-faq.yml) Domínios se você não encontrar o que está procurando. 
  
> [!CAUTION]
> O site do Freenom não dá suporte a registros SRV, o que significa que vários recursos do Skype for Business Online e do Outlook Web App não funcionarão. Não importa qual plano da Microsoft você use, há limitações significativas de serviço e talvez você queira alternar para um provedor de hospedagem DNS diferente. 
  
Se, apesar das limitações de serviço, você optar por gerenciar seus próprios registros DNS da Microsoft no Freenom, siga as etapas deste artigo para verificar seu domínio e configurar registros DNS para email e outros serviços.
  
  
> [!NOTE]
> Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Adicionar um registro TXT para verificação
<a name="bkmk_txt"> </a>

Antes de usar o seu domínio com a Microsoft, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro de DNS prova à Microsoft que você é o proprietário do domínio.
  
> [!NOTE]
> Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar. 
  
1. Para começar, vá para sua página de domínios no Freenom usando [este link](https://my.freenom.com/). You'll be prompted to log in.
    
    ![Logon gratuito](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. Selecione **Serviços** e selecione **Meus Domínios.**
    
    ![Freenom selecione Serviços e Meus Domínios](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. Para o domínio que você deseja editar, selecione **Gerenciar Domínio**.
    
    ![Freenom selecione Gerenciar Domínio](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. Selecione **Gerenciar DNS do Freenom**.
    
    ![Freenom Manage Freenom DNS](../../media/9854a511-27e3-4658-8903-34b3d425096d.png)
  
5. Em **Adicionar Registro**, na coluna **Tipo,** escolha **TXT** no menu. 
    
    ![Freenom Add Record type TXT](../../media/7f0e85e7-844f-4962-815e-5d80d9e6efa0.png)
  
6. Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela. 
    
    |**Nome**|**Tipo**|**TTL**|**Target**|
    |:-----|:-----|:-----|:-----|
    |(deixar em branco)  <br/> |TXT  <br/> |3600 (segundos)  <br/> |MS=msXXXXXXXX  <br/> **Observação**: esse é um exemplo. Use aqui seu valor específico de **Destino ou Pontos de Endereçamento**, retirado da tabela.           [Como localizo isto?](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Valores TXT do Freenom para verificação](../../media/650098df-b3aa-47e5-9763-7fde24e34c3f.png)
  
7. Selecione **Salvar Alterações**.
    
    ![Registro TXT do Freenom Salvar Alterações](../../media/b1a63f9a-4578-491a-9554-c40f73b37e09.png)
  
8. Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.
    
Agora que você adicionou o registro no site do seu registrador de domínios, retorne à Microsoft e solicite o registro.
  
Quando a Microsoft encontrar o registro TXT correto, seu domínio estará verificado.
  
1. No centro do administrador da Microsoft, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.

    
2. Na página **Domínios**, clique no domínio que você está verificando. 
    
    
  
3. Na página **Configuração**, clique em **Iniciar configuração**.
    
    
  
4. Na página **Verificar domínio**, marque **Verificar**.
    
    
  
> [!NOTE]
>  Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Adicione um registro MX para que o email do domínio vá para a Microsoft.
<a name="bkmk_mx"> </a>

1. Para começar, vá para sua página de domínios no Freenom usando [este link](https://my.freenom.com/). You'll be prompted to log in.
    
    ![Logon gratuito](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. Selecione **Serviços** e selecione **Meus Domínios.**
    
    ![Freenom selecione Serviços e Meus Domínios](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. Para o domínio que você deseja editar, selecione **Gerenciar Domínio**.
    
    ![Freenom selecione Gerenciar Domínio](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. De definir o nome serve para o seu domínio para os servidores de nome padrão do Freenom. Selecione **Ferramentas de Gerenciamento** e selecione **Nameservers**.
    
    ![Configuração de Nameservers freenom](../../media/a6ae877a-c248-42b9-bae9-210a80cd01e7.png)
  
5. **Certifique-se de usar os nameservers padrão** selecionados e selecione Alterar **Nameservers**.
    
    ![Freenom Change Nameservers](../../media/0ef90d84-c0a0-4ef9-9e4c-43ef0aac3a2e.png)
  
6. Selecione **Gerenciar DNS do Freenom**.
    
    ![Freenom selecione Gerenciar DNS do Freenom](../../media/f55a8053-2411-45da-a357-776c6699f721.png)
  
7. Em **Adicionar Registro**, na coluna **Tipo,** escolha **MX** no menu. 
    
    ![Freenom Add Record type MX](../../media/c728c6ee-786c-4f6a-8ad5-1d9914a5bfcf.png)
  
8. Nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir. 
    
    |**Nome**|**Tipo**|**TTL**|**Target**|**Prioridade**|
    |:-----|:-----|:-----|:-----|:-----|
    |(deixar em branco)  <br/> |Servidor de mensagens (MX)  <br/> |3600 (segundos)  <br/> |\<domain-key\>.mail.protection.outlook.com  <br/> **Observação:** Obter o  *\<domain-key\>*  seu de sua conta da Microsoft.   [Como faço para encontrar isso?](../get-help-with-domains/information-for-dns-records.md)          |10   <br/> Para saber mais sobre prioridade, confira [O que é prioridade MX?](../setup/domains-faq.yml) <br/> |
   
   ![Registro MX do Freenom](../../media/8896c4a9-b3dd-45ed-9916-f7da2715ba8c.png)
  
9. Selecione **Salvar Alterações**.
    
    ![Registro MX do Freenom Salvar Alterações](../../media/7aa0a464-d136-417f-be40-48d3f728eeb7.png)
  
10. Se houver outros registros MX, exclua-os todos. Para cada registro, selecione **Excluir**. Quando a mensagem **Você realmente deseja remover essa entrada?** é exibida, selecione **OK**.
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a>Adicionar os registros CNAME necessários para a Microsoft
<a name="bkmk_cname"> </a>

1. Para começar, vá para sua página de domínios no Freenom usando [este link](https://my.freenom.com/). You'll be prompted to log in.
    
    ![Logon gratuito](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. Selecione **Serviços** e selecione **Meus Domínios.**
    
    ![Freenom selecione Serviços e Meus Domínios](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. Para o domínio que você deseja editar, selecione **Gerenciar Domínio**.
    
    ![Freenom selecione Gerenciar Domínio](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. Selecione **Gerenciar DNS do Freenom**.
    
    ![Freenom selecione Gerenciar DNS do Freenom](../../media/5e7bc3a7-0d5e-431b-bb27-da3b0f316d01.png)
  
5. Em **Adicionar Registro**, na coluna **Tipo,** escolha **CNAME** no menu. 
    
    ![Freenom Add Record type CNAME](../../media/9b204755-ca2a-46d2-bce2-030d82fd1f9e.png)
  
6. Criar o primeiro registro CNAME. Nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir. 
    
    |**Nome**|**Tipo de registro**|**TTL**|**Target**|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |3600 (segundos)  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |CNAME  <br/> |3600 (segundos)  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |3600 (segundos)  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |3600 (segundos)  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |3600 (segundos)  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
    ![Valores CNAME do Freenom](../../media/752fc682-e3f2-4b9c-9253-bf1ba2d414e9.png)
  
7. Selecione **Salvar Alterações**.
    
    ![Freenom CNAME Salvar Alterações](../../media/68103fd2-0f5f-4aac-a875-25157c6bbdd2.png)
  
8. Repita as etapas anteriores para criar os outros cinco registros CNAME. 
    
    Para cada registro, digite ou copie e copie os valores da próxima linha da tabela acima nas caixas desse registro.
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail
<a name="bkmk_spf"> </a>

> [!IMPORTANT]
> Não é possível ter mais de um registro TXT para SPF para um domínio. Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam. Se você já possui um registro SPF para seu domínio, não crie um novo para a Microsoft. Em vez disso, adicione os valores necessários da Microsoft ao registro atual para que você tenha um único registro  *SPF*  que inclua ambos os conjuntos de valores. 

1. Para começar, vá para sua página de domínios no Freenom usando [este link](https://my.freenom.com/). You'll be prompted to log in.
    
    ![Logon gratuito](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. Selecione **Serviços** e selecione **Meus Domínios.**
    
    ![Freenom selecione Serviços e Meus Domínios](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. Para o domínio que você deseja editar, selecione **Gerenciar Domínio**.
    
    ![Freenom selecione Gerenciar Domínio](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. Selecione **Gerenciar DNS do Freenom**.
    
    ![Freenom selecione Gerenciar DNS do Freenom](../../media/94809955-0315-409c-a15d-703a2fe4c4ed.png)
  
5. Em **Adicionar Registro**, na coluna **Tipo,** escolha **TXT** no menu. 
    
    ![Freenom Add Record type TXT](../../media/d8854285-c4ae-416c-a072-72a11ba1cd9a.png)
  
6. In the boxes for the new record, type or copy and paste the following values. 
    
    |**Nome**|**Tipo de registro**|**TTL**|**Target**|
    |:-----|:-----|:-----|:-----|
    |(deixar em branco)  <br/> |TXT  <br/> |3600 (segundos)  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/>**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.           |
   
    ![Valores TXT do Freenom para SPF](../../media/1b3b1199-9104-4ca1-acdb-786d139c21ac.png)
  
7. Selecione **Salvar Alterações**.
    
    ![Registro TXT do Freenom para Alterações de Salvar SPF](../../media/e2fc52b1-0dcb-4595-9a4c-fca5e2ef9f97.png)
