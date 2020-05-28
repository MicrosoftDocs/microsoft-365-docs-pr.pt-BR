---
title: Alterar os nameservers para configurar o Microsoft com o Hostgator
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: f3bd3c62-0477-48e4-b2b5-21e329d67985
description: Saiba como você pode configurar a Microsoft para gerenciar os registros DNS do seu domínio personalizado em Hostgator.
ms.openlocfilehash: 787fe5f5e768d9d93cfca9d1644037142822216e
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400636"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-hostgator"></a>Alterar os nameservers para configurar o Microsoft 365 com o Hostgator

 Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**.
  
Siga estas instruções se quiser que a Microsoft gerencie seus registros DNS para você. Se preferir, [gerencie todos os registros DNS da Microsoft em Hostgator](create-dns-records-at-hostgator.md).
  
    
## <a name="point-your-domain-to-your-hosting-account"></a>Aponte o seu domínio para sua conta de hospedagem.

> [!IMPORTANT]
> Você deve executar esse procedimento antes do procedimento na seção a seguir, **Adicionar um registro TXT para verificação**.
  
Siga estas etapas para associar seu domínio e as contas de hospedagem.
  
1. Para começar, vá até a sua página de gerenciamento de clientes na Hostgator usando [este link](https://portal.hostgator.com/domain/manage). Você será solicitado a fazer logon primeiro.
    
    ![Conectando a lista de tarefas ao Outlook](../../media/6749ac23-4832-4daf-8f3b-bc3b9b1b979c.png)
  
2. Selecione a guia **domínios** .
    
    ![Faixa de Opções do Office 14](../../media/56d12bfd-3549-4033-90dc-077c76ca798c.png)
  
3. Na página **gerenciar domínios** , na área **meus domínios** , selecione o domínio que você deseja atualizar.
    
    ![Hostgator-BP-Redelegate-1-2](../../media/2c2f8530-26a1-4e62-bb04-b3874bc1cf36.png)
  
4. Na página **visão geral de domínios** , na área **servidores de nomes** , selecione **alterar**.
    
    ![Imagem do botão Definir cor transparente](../../media/c8979d8a-ee96-4064-a8df-c5b01054cb16.png)
  
5. Na página **servidores de nomes** do seu domínio, na lista suspensa **selecionar conta de hospedagem** , escolha a conta de **hospedagem** associada ao seu domínio.
    
    ![Painéis do Power BI](../../media/4cf61060-1e8a-4758-9892-32059ffc90c2.png)
  
6. Selecione **salvar servidores de nomes**.
    
    ![Hostgator-BP-Redelegate-1-9](../../media/b52a825a-6d54-49ba-87c8-52f770fdfa0c.png)
  
## <a name="add-a-txt-record-for-verification"></a>Adicionar um registro TXT para verificação

> [!IMPORTANT]
> Antes de executar este procedimento, você deve primeiro executar o procedimento na primeira seção deste artigo, [aponte seu domínio para sua conta de hospedagem.](#point-your-domain-to-your-hosting-account).
  
Antes de usar o seu domínio com a Microsoft, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro de DNS prova à Microsoft que você é o proprietário do domínio.
  
> [!NOTE]
> Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.
  
1. Para começar, vá para a página do cPanel no Hostgator. Será solicitado que você faça logon primeiro.
    
    (É atribuído um endereço cPanel exclusivo a cada conta hospedada no Hostgator. Seu endereço cPanel deve ter esta aparência: https://YourSiteAddress:secure-port-numberçoDoSeuSite:número-de-porta-segura. O email de inscrição recebido do Hostgator especificará esse endereço.)
    
    > [!IMPORTANT]
    > To have a cPanel associated with your domain, you need a hosting account with Hostgator. Para começar, você pode comprar uma conta de hospedagem do Hostgator ou [alterar os registros de nameserver (ns) do seu domínio](#change-your-domains-nameserver-ns-records) para apontar para a Microsoft. 
  
2. Na página **painel de controle** , na área **domínios** , selecione **Editor de zona de DNS avançado**.
    
    (You may have to scroll down.) 
    
3. On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Escolha o valor de **Tipo** na lista suspensa.) 
    
|||||
|:-----|:-----|:-----|:-----|
|**Nome** <br/> |**TTL** <br/> |**Tipo** <br/> |**Dados TXT** <br/> |
|Use seu  *domain_name*  . (por exemplo, fourthcoffee.com.)  <br/> **Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)** <br/> |1   <br/> |TXT  <br/> |MS=ms *XXXXXXXX*  <br/> **Observação**: esse é um exemplo. Use aqui seu valor específico de **Destino ou Pontos de Endereçamento**, retirado da tabela. [Como localizo isto?](../get-help-with-domains/information-for-dns-records.md)     <br/>  |
   
4. Selecione **adicionar registro**.
    
5. Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.
    
Agora que você adicionou o registro no site do seu registrador de domínio, você voltará para a Microsoft e solicitará uma pesquisa para o registro.
  
Quando a Microsoft encontrar o registro TXT correto, seu domínio estará verificado.
  
1. No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.

    
2. Na página **Domínios**, clique no domínio que você está verificando. 
    
3. Na página **Configuração**, clique em **Iniciar configuração**.
    
4. Na página **Verificar domínio**, clique em **Verificar**.
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="change-your-domains-nameserver-ns-records"></a>Alterar os registros de nameserver (NS) de seu domínio

Para concluir a configuração do seu domínio com a Microsoft, altere os registros NS do seu domínio no seu registrador de domínios para apontar para os servidores de nomes primários e secundários da Microsoft. Isso configura a Microsoft para atualizar os registros DNS do domínio para você. Todos os registros são adicionados para que os seus emails, o Skype for Business Online e os sites públicos funcionem com o seu domínio e você fique com tudo pronto.
  
> [!CAUTION]
> Quando você alterar os registros NS do seu domínio para apontar para os servidores de nomes da Microsoft, todos os serviços associados atualmente ao seu domínio serão afetados. Por exemplo, todos os emails enviados para seu domínio (como rob@ *your_domain* . com) começarão a ser iniciados pela Microsoft depois que você fizer essa alteração.
  
> [!IMPORTANT]
> O procedimento a seguir mostrará como excluir outros nameservers indesejados da lista e também como adicionar os nameservers corretos se eles ainda não estiverem listados. Quando você tiver concluído as etapas nesta seção, os únicos nameservers que devem ser listados são estes quatro: **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **NS3.bdm.microsoftonline.com**e **NS4.bdm.microsoftonline.com**.
  
1. Para começar, vá até a sua página de gerenciamento de clientes na Hostgator usando [este link](https://portal.hostgator.com/domain/manage). Você será solicitado a fazer logon primeiro.
    
    ![Conectando a lista de tarefas ao Outlook](../../media/6749ac23-4832-4daf-8f3b-bc3b9b1b979c.png)
  
2. Selecione a guia **domínios** . 
    
    ![Faixa de Opções do Office 14](../../media/56d12bfd-3549-4033-90dc-077c76ca798c.png)
  
3. Na página **gerenciar domínios** , na área **meus domínios** , selecione o domínio que você deseja atualizar. 
    
    ![Hostgator-BP-Redelegate-1-2](../../media/2c2f8530-26a1-4e62-bb04-b3874bc1cf36.png)
  
4. Na página **visão geral do domínio** , na área **servidores de nomes** , selecione **alterar**.
    
    ![Imagem do botão Definir cor transparente](../../media/c8979d8a-ee96-4064-a8df-c5b01054cb16.png)
  
5. Na página **servidores de nomes** do seu domínio, na lista suspensa **selecionar conta de hospedagem** , escolha a conta de **hospedagem** associada ao seu domínio. 
    
    ![Painéis do Power BI](../../media/4cf61060-1e8a-4758-9892-32059ffc90c2.png)
  
6. Selecione **definir manualmente os meus servidores de nomes**.
    
    ![Hostgator-BP-Redelegate-1-5](../../media/5b73ae32-f26e-48aa-b5ad-6da20f1c491a.png)
  
7.   **Cuidado**: Siga estas etapas somente se você tiver nameservers existentes além dos quatro nameservers corretos. (Ou seja, exclua somente os nameservers atuais que *não* sejam denominados **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **NS3.bdm.microsoftonline.com**ou **NS4.bdm.microsoftonline.com**.)
  
        Ainda na página **Servidores de Nomes** do domínio, na lista de servidores de nomes, exclua cada nameserver na lista selecionando-o e pressionando a tecla **Delete** no teclado. 
    
   ![O365_Adddomain_wizard_1_7a](../../media/fa9820e7-28bb-4792-b16c-51e54d83feb1.png)
  
8. Ainda na lista de servidores de nomes, digite ou copie e cole os dois primeiros valores da tabela a seguir.
    
|||
|:-----|:-----|
|**Servidor de nomes 1:** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Servidor de nomes 2:** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Servidor de Nomes 3:** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Servidor de Nomes 4:** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![Hostgator-BP-redelegar-1-7-1](../../media/a8c10aa7-30b0-4bc8-9596-20256d396274.png)
  
9. Adicione outros valores de nameserver.
    
    Selecione **(+)** adicionar e, em seguida, digite ou copie e cole o valor da próxima linha da tabela na caixa do registro. 
    
    Repita esse processo até ter criado todos os quatro registros nameserver.
    
    ![Hostgator-BP-Redelegate-1-7-2](../../media/92159a39-e498-4220-9b0d-ae2e718c7fb9.png)
  
10. Selecione **salvar servidores de nomes**.
    
    ![Hostgator-BP-Redelegate-1-8](../../media/bd6b0dfa-5d39-4805-970d-7ab153cff117.png)
  
> [!NOTE]
> As atualizações de registro do servidor de nomes poderão levar várias horas para entrarem em vigor no sistema DNS da Internet. Em seguida, seu email da Microsoft e outros serviços serão configurados para funcionar com seu domínio.
