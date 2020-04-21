---
title: Alterar os nameservers para configurar o Microsoft com o Namecheap
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
ms.assetid: 84f467f6-28cf-40f0-94d0-a2a27ddfc2e7
description: 'Saiba como configurar seu domínio personalizado da Microsoft com o Namecheap se quiser que a Microsoft gerencie seus registros DNS. '
ms.openlocfilehash: 6fdec37e837c74666ada82af81d43faaa0a6d589
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629774"
---
# <a name="change-nameservers-to-set-up-microsoft-with-namecheap"></a>Alterar os nameservers para configurar o Microsoft com o Namecheap

 Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**.
  
Siga estas instruções se quiser que a Microsoft gerencie seus registros DNS para você. Se preferir, [gerencie todos os registros DNS da Microsoft em Namecheap](create-dns-records-at-namecheap.md).
  
    
## <a name="add-a-txt-record-for-verification"></a>Adicionar um registro TXT para verificação

1. Para começar, vá até a sua página de domínios no Namecheap usando [este link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). Você será solicitado a entrar e continuar.
    
    ![Namecheap-BP-configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. Na página de **aterrissagem** , em **conta**, escolha **lista de domínios** na lista suspensa. 
    
    ![Namecheap-BP-configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. Na página **lista de domínios** , localize o nome do domínio que você deseja editar e, em seguida, selecione **gerenciar**.
    
    ![Namecheap-BP-configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. Selecione **DNS avançado**.
    
    ![Namecheap-BP-configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. Na seção **registros de host** , selecione **Adicionar novo registro**.
    
    ![Namecheap-BP-configure-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. Na lista suspensa **tipo** , selecione **registro txt**.
    
    > [!NOTE]
    > O menu suspenso **tipo** aparece automaticamente quando você seleciona **Adicionar novo registro**.
  
    ![Namecheap-BP-Verify-1-1](../../media/a5b40973-19b5-4c32-8e1b-1521aa971836.png)
  
7. Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela.
    
    (Escolha o valor **TTL** na lista suspensa.) 
    
|**Tipo**|**Host**|**Valor**|**TTL**|
|:-----|:-----|:-----|:-----|
|TXT  <br/> |@  <br/> |MS = ms *XXXXXXXX*  <br/> **Observação**: Este é um exemplo. Use o seu **destino específico ou aponte para** o valor de endereço aqui, a partir da tabela.           [Como localizo isto?](../get-help-with-domains/information-for-dns-records.md)          |30 min  <br/> |
   
   ![Namecheap-BP-Verify-1-2](../../media/fe75c0fd-f85c-4bef-8068-edaf9779b7f1.png)
  
8. Selecione o controle **salvar alterações** (marca de seleção). 
    
    ![Namecheap-BP-Verify-1-3](../../media/b48d2c67-66b5-4aa4-8e59-0c764f236fac.png)
  
9. Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.
    
Agora que você adicionou o registro no site do seu registrador de domínio, você voltará para a Microsoft e solicitará uma pesquisa para o registro.
  
Quando a Microsoft encontrar o registro TXT correto, seu domínio será verificado.
  
1. No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.

    
2. Na página **Domínios**, clique no domínio que você está verificando. 
    
    
  
3. Na página **Configuração**, clique em **Iniciar configuração**.
    
    
  
4. Na página **Verificar domínio**, marque **Verificar**.
    
    
  
> [!NOTE]
>  Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="change-your-domains-nameserver-ns-records"></a>Alterar os registros de nameserver (NS) de seu domínio

Para concluir a configuração do seu domínio com a Microsoft, altere os registros NS do seu domínio no seu registrador de domínios para apontar para os servidores de nomes primários e secundários da Microsoft. Isso configura a Microsoft para atualizar os registros DNS do domínio para você. Todos os registros são adicionados para que os seus emails, o Skype for Business Online e os sites públicos funcionem com o seu domínio e você fique com tudo pronto.
  
> [!CAUTION]
> Quando você alterar os registros NS do seu domínio para apontar para os servidores de nomes da Microsoft, todos os serviços associados atualmente ao seu domínio serão afetados. Por exemplo, todos os emails enviados para seu domínio (como rob@ *your_domain* . com) começarão a ser iniciados pela Microsoft depois que você fizer essa alteração. 
  
> [!IMPORTANT]
>  Quando você concluir as etapas desta seção, os  *únicos*  nameservers que deverão estar listados são estes quatro: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com >  O procedimento a seguir mostra como excluir outros nameservers indesejados da lista, além de adicionar os nameservers  *corretos*  se ainda não estiverem na lista. 
  
1. Para começar, vá até a sua página de domínios no Namecheap usando [este link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f). Você será solicitado a entrar e continuar.
    
    ![Namecheap-BP-configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. Na página de **aterrissagem** , em **conta**, escolha **lista de domínios** na lista suspensa. 
    
    ![Namecheap-BP-configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. Na página **lista de domínios** , localize o nome do domínio que você deseja editar e, em seguida, selecione **gerenciar**.
    
    ![Namecheap-BP-configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. Selecione **domínio**.
    
    ![Namecheap-BP-redelegar-1-1](../../media/59588406-794e-4ae4-8526-35e3111b5791.png)
  
5. Encontre a seção **nameservers** e, em seguida, selecione **personalizado** na lista suspensa **Namecheap padrão** . 
    
    ![Namecheap-BP-redelegar-1-2](../../media/7df56295-fdb3-472f-9442-13f780c2c93e.png)
  
6. Dependendo se já existem ou não nameservers listados na página exibida agora, continue com um dos dois procedimentos a seguir.
    
### <a name="if-there-are-no-nameservers-already-listed"></a>Se NÃO houver nameservers listados
<a name="BKMK_ProcedureWithOUT"> </a>

1. Selecione **Adicionar nameserver** duas vezes para adicionar duas novas linhas.
    
    ![Namecheap-BP-redelegar-1-3-1](../../media/e8816bf5-bb59-49d5-bfca-43e502242dc3.png)
  
2. Nas caixas **nameserver** , digite ou copie e cole os valores da tabela a seguir.
    
|||
|:-----|:-----|
|**Nameserver 1** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Nameserver 2** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Nameserver 3** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Nameserver 4** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![Namecheap-BP-redelegar-1-3-2](../../media/21d681b7-4f96-4e96-ac27-9534c388537c.png)
  
3. Selecione o controle **salvar** (marca de seleção). 
    
    ![Namecheap-BP-redelegar-1-5](../../media/07aaf1e5-c24f-4c51-bfe0-f99868b3bf35.png)
  
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Em seguida, seu email da Microsoft e outros serviços serão configurados para funcionar com seu domínio. 
  
### <a name="if-there-are-nameservers-already-listed"></a>Se HOUVER nameservers listados

> [!CAUTION]
> Siga estas etapas  *somente*  se você tiver outros nameservers existentes, além dos quatro nameservers  *corretos*  . Ou seja, exclua  *somente*  nameservers atuais que  *não*  sejam denominados como **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com** ou **ns4.bdm.microsoftonline.com**. 
  
1. Se houver outros nameservers listados nas caixas **nameserver** , exclua cada um selecionando-o e pressionando a tecla **delete** no teclado. 
    
    ![Namecheap-BP-redelegar-1-4](../../media/3270603a-c4f4-40b7-acad-733d56e2f53c.png)
  
2. Selecione **Adicionar nameserver** duas vezes para adicionar duas novas linhas. 
    
    ![Namecheap-BP-redelegar-1-3-1](../../media/e8816bf5-bb59-49d5-bfca-43e502242dc3.png)
  
3. Nas caixas **nameserver** , digite ou copie e cole os valores da tabela a seguir.
 
    
|||
|:-----|:-----|
|**Servidor de nomes 1** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Servidor de nomes 2** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Nameserver 3** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Nameserver 4** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![Namecheap-BP-redelegar-1-3-2](../../media/21d681b7-4f96-4e96-ac27-9534c388537c.png)
  
4. Selecione o controle **salvar** (marca de seleção). 
    
    ![Namecheap-BP-redelegar-1-5](../../media/07aaf1e5-c24f-4c51-bfe0-f99868b3bf35.png)
  
> [!NOTE]
> Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Em seguida, seu email da Microsoft e outros serviços serão configurados para funcionar com seu domínio.
