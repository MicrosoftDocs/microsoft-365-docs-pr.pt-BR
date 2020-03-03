---
title: Alterar os nameservers para configurar o Office 365 com a MyDomain
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
ms.assetid: c5f6140a-4a12-401b-9bbd-7dfb0d6b0ba3
description: Saiba como você pode configurar o Office 365 para gerenciar os registros DNS do seu domínio personalizado em mydomain.
ms.openlocfilehash: 90f1469bdf2f281be14e2a9e15a9fe7ac4a8cbee
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/02/2020
ms.locfileid: "42351612"
---
# <a name="change-nameservers-to-set-up-office-365-with-mydomain"></a>Alterar os nameservers para configurar o Office 365 com a MyDomain

 **Caso não encontre o conteúdo que está procurando, [verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**.
  
Siga essas instruções se desejar que o Office 365 gerencie os registros DNS do Office 365 para você. Se preferir, [gerencie todos os registros DNS do Office 365 na MyDomain](create-dns-records-at-mydomain.md).
  
## <a name="add-a-txt-record-for-verification"></a>Adicionar um registro TXT para verificação

Antes de usar o seu domínio com o Office 365, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro DNS prova ao Office 365 que você é o proprietário do domínio.
  
> [!NOTE]
> Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar. 
  
1. Para começar, vá até a sua página de domínios em MeuDomínio usando [este link](https://www.mydomain.com/controlpanel). Você será solicitado a fazer logon primeiro.
    
2. Na seção **Meus Favoritos**, clique em **Central de domínio**.
    
3. Na opção **Domínio**, clique no nome do domínio que quer editar.
    
4. Na linha **Visão geral**, clique em **DNS**.
    
5. Na lista suspensa **Modificar**, clique em **Registro TXT/SPF**.
    
6. Em **Content**, na caixa do novo registro, digite ou copie e cole os valores da tabela a seguir.
    
||
|:-----|
|**Conteúdo** <br/> |
|MS = ms *XXXXXXXX*  <br/> **Observação**: Este é um exemplo. Use seu valor específico de **Destinos ou Pontos de Endereçamento** aqui, da tabela no Office 365. [Como localizo isto?](../get-help-with-domains/information-for-dns-records.md)          |
   
7. Clique em **Adicionar**.
    
8. Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.
    
Agora que você adicionou o registro no site do seu registrador de domínios, retorne ao Office 365 e solicite que o Office 365 procure o registro.
  
Quando o Office 365 encontrar o registro TXT correto, o domínio será verificado.
  
1. No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.

    
2. Na página **Domínios**, clique no domínio que você está verificando. 
    
3. Na página **Configuração**, clique em **Iniciar configuração**.
    
4. Na página **Verificar domínio**, clique em **Verificar**.
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas após alterar o nome de domínio ou registros DNS no Office 365](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="change-your-domains-nameserver-ns-records"></a>Alterar os registros de nameserver (NS) de seu domínio

Para concluir a configuração do domínio com o Office 365, altere os registros NS do seu domínio no registrador de domínios para apontar para os servidores de nomes primários e secundários do Office 365. Isso configura o Office 365 para atualizar os registros DNS do seu domínio. Todos os registros são adicionados para que os seus emails, o Skype for Business Online e os sites públicos funcionem com o seu domínio e você fique com tudo pronto.
  
> [!CAUTION]
> Ao alterar os registros NS do domínio para direcionar para os servidores de nome do Office 365, todos os serviços associados atualmente a esse domínio serão afetados. Por exemplo, todos os emails enviados para seu domínio (como rob@ *your_domain.* com) começará a chegar ao Office 365 depois que você fizer essa alteração. 
  
> [!IMPORTANT]
> The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list. <br/> When you have completed the steps in this section, the only nameservers that should be listed are these four:
  
1. Para começar, vá até a sua página de domínios em MeuDomínio usando [este link](https://www.mydomain.com/controlpanel). Você será solicitado a fazer logon primeiro.
    
2. Na seção **Meus Favoritos**, clique em **Central de domínio**.
    
3. Na opção **Domínio**, clique no nome do domínio que quer editar.
    
4. Na linha **visão geral** , selecione **nameservers**.
    
    ![Mydomain-BP-redelegar-1-1](../../media/49e91235-44b5-46d6-a82e-8f11329db3d6.png)
  
5. Na seção **Update Name Servers**, selecione **Use different name servers**.
    
    ![Mydomain-BP-redelegar-1-2-1](../../media/f869fb26-54dc-4b66-8378-a78a79b582bd.png)
  
6. Dependendo se já existem ou não nameservers listados na página exibida agora, continue com um dos dois procedimentos a seguir.
    
### <a name="if-the-correct-nameservers-are-already-listed"></a>Se os nameservers corretos já ESTIVEREM listados

- Se os nameservers corretos já estiverem listados, ignore esta etapa.
    
    ![Mydomain-BP-redelegar-1-2-2](../../media/601f6a46-15bd-4a92-b792-ac628ff86628.png)
  
### <a name="if-the-correct-nameservers-are-not-already-listed"></a>Se os nameservers corretos NÃO ESTIVEREM listados

> [!CAUTION]
> Follow these steps only if you have existing nameservers other than the four correct nameservers. (Ou seja, exclua somente os nameservers atuais que *não* sejam denominados **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **NS3.bdm.microsoftonline.com**ou **NS4.bdm.microsoftonline.com**.) 
  
1. Exclua os nameservers existentes selecionado cada entrada no campo **Nameserver:** e, em seguida, pressione a tecla **Delete** no seu teclado. 
    
    ![Mydomain-BP-redelegar-1-3-1](../../media/5024cd27-a2b1-42a2-99e4-5ceb5e6eddb9.png)
  
2. Selecione **adicionar mais** duas vezes para adicionar duas novas linhas de nameserver. 
    
    ![Mydomain-BP-redelegar-1-3-2](../../media/19307893-2f73-4e4d-9221-a5870e09ab48.png)
  
3. Nas caixas dos registros, digite ou copie e cole os valores de nameserver da tabela a seguir.
    
|||
|:-----|:-----|
|**Nameserver 1** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Nameserver 2** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Nameserver 3** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Nameserver 4** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![Mydomain-BP-redelegar-1-4](../../media/7427e99c-49c7-4a2e-a5bf-66fc46900cd1.png)
  
4. Selecione **Salvar**.
    
    ![Mydomain-BP-redelegar-1-5](../../media/48473816-b881-47f0-9344-74622efa3bf8.png)
  
> [!NOTE]
> As atualizações de registro do servidor de nomes poderão levar várias horas para entrarem em vigor no sistema DNS da Internet. Em seguida, os seus emails e outros serviços do Office 365 serão todos configurados para funcionar com seu domínio. 
