---
title: Alterar os nameservers para configurar o Office 365 com o Google Domains
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
ms.assetid: 68a08e94-26c2-4df2-9216-026b8ec907ca
description: Saiba como você pode configurar o Office 365 para gerenciar os registros DNS do seu domínio personalizado em domínios do Google.
ms.openlocfilehash: f6faaa4a7b6540086752e88da2051a73450f4455
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/02/2020
ms.locfileid: "42351962"
---
# <a name="change-nameservers-to-set-up-office-365-with-google-domains"></a>Alterar os nameservers para configurar o Office 365 com o Google Domains

 **Caso não encontre o conteúdo que está procurando, [verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**. 
  
Siga essas instruções se desejar que o Office 365 gerencie os registros DNS do Office 365 para você. Se preferir, [gerencie todos os registros DNS do Office 365 em Google Domains](create-dns-records-at-google-domains.md).
  
    
## <a name="add-a-txt-record-for-verification"></a>Adicionar um registro TXT para verificação

Antes de usar o seu domínio com o Office 365, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro DNS prova ao Office 365 que você é o proprietário do domínio.
  
> [!NOTE]
>  Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar. 
  
1. Para começar, vá até a sua página de domínios no Google Domains por meio [deste link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:
    
1. Selecione **entrar**.
    
2. Insira suas credenciais de logon e selecione **entrar**novamente.
    
2. Na página **domínios** , na seção **domínio** , selecione **Configurar DNS** para o domínio que você deseja editar. 
    
3. In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (You may have to scroll down.)
    
    (Choose the **Type** value from the drop-down list.) 
    
|||||
|:-----|:-----|:-----|:-----|
|**Nome** <br/> |**Tipo** <br/> |**TTL** <br/> |**Dados** <br/> |
|@  <br/> |TXT  <br/> |1H  <br/> |MS = ms *XXXXXXXX* <br/> **Observação**: esse é um exemplo. Use seu valor específico de **Destinos ou Pontos de Endereçamento** aqui, da tabela no Office 365. [Como localizo isto?](../get-help-with-domains/information-for-dns-records.md)       <br/>  |
   
4. Clique em **Adicionar**.
    
5. Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.
    
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
> Ao alterar os registros NS do domínio para direcionar para os servidores de nome do Office 365, todos os serviços associados atualmente a esse domínio serão afetados. Por exemplo, todos os emails enviados para seu domínio (como rob@ *your_domain.*  com) começará a chegar ao Office 365 depois que você fizer essa alteração. 
  
> [!IMPORTANT]
> The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list. > quando você tiver concluído as etapas nesta seção, os únicos nameservers que devem ser listados são estes quatro: 
  
1. Para iniciar, vá até a página do seu domínio no Google Domains usando [este link](https://domains.google.com/registrar). Você será solicitado a entrar. Para fazer isso:
    
1. Selecione **entrar**.
    
2. Digite suas credenciais de logon e, em seguida, selecione **entrar**novamente.
    
2. Na página **domínios** , na seção **domínio** , selecione **Configurar DNS** para o domínio que você deseja editar. 
    
3. Na página **Domínios**, na seção **Servidores de nomes**, selecione **Usar servidores de nomes personalizados**.
    
    ![Google-Domains-BP-Redelegate-1-1](../../media/e264bc05-5a56-4962-bcaf-e2d999f62278.png)
  
4. Dependendo se há ou não nameservers já listados na página exibida agora, continue para um destes dois procedimentos:
    
  - Se **NÃO HOUVER** nameservers listados, [Se NÃO houver nameservers listados](#if-there-are-no-nameservers-already-listed).
    
  - Se **HOUVER** nameservers listados, [Se HOUVER nameservers listados](#if-there-are-nameservers-already-listed).
    
### <a name="if-there-are-no-nameservers-already-listed"></a>Se NÃO houver nameservers listados

1. Adicione o primeiro nameserver.
    
    Na seção **Servidores de nomes**, na caixa **SERVIDOR DE NOMES**, digite ou copie e cole o primeiro valor da tabela a seguir. 
    
|||
|:-----|:-----|
|**Primeiro servidor de nomes** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Segundo servidor de nomes** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Terceiro servidor de nome** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Quarto servidor de nome** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![Google-Domains-BP-redelegar-1-2](../../media/6d14544d-7783-4ed4-b4dd-691624af7172.png)
  
2. Selecione o controle **+ (Adicionar)** para criar uma linha vazia. 
    
    ![Google-Domains-BP-Redelegate-1-3](../../media/ea23e5fc-07e1-4ffc-b8cf-8526867b752d.png)
  
3. Adicione os outros três registros Nameserver.
    
    Na seção **usar servidores de nomes personalizados** , crie um registro usando os valores da próxima linha na tabela e, em seguida, selecione o controle **+ (Adicionar)** para adicionar outra linha. 
    
    Repita esse processo até ter criado todos os quatro registros Nameserver.
    
4. Selecione **Salvar**.
    
    ![Google-Domains-BP-Redelegate-1-5](../../media/cb954aa2-12ee-4e90-9b67-184cbe898bbb.png)
  
> [!NOTE]
> As atualizações de registro do servidor de nomes poderão levar várias horas para entrarem em vigor no sistema DNS da Internet. Em seguida, os seus emails e outros serviços do Office 365 serão todos configurados para funcionar com seu domínio. 
  
### <a name="if-there-are-nameservers-already-listed"></a>Se HOUVER nameservers listados

1. Se houver outros nameservers listados, selecione **Editar**.
    
    > [!CAUTION]
    > Follow these steps only if you have existing nameservers other than the four correct nameservers. (Ou seja, exclua somente os nameservers atuais que *não* sejam denominados **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **NS3.bdm.microsoftonline.com**ou **NS4.bdm.microsoftonline.com**.) 
  
    ![Google-Domains-BP-Redelegate-1-6-1](../../media/fb45d120-55ab-42c2-bdb6-19b130c3c7db.png)
  
2. Exclua cada um selecionando-o e pressionando a tecla **Delete** no teclado. 
    
    ![Google-Domains-BP-Redelegate-1-6-2](../../media/524e64ad-56e6-4254-8a64-e4a4c3230f89.png)
  
3. Ainda na seção **Servidores de nomes**, nas linhas **SERVIDOR DE NOMES**, digite ou copie e cole os valores da tabela a seguir. 
    
|||
|:-----|:-----|
|**Primeiro servidor de nomes** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Segundo servidor de nomes** <br/> |ns2.bdm.microsoftonline.com  <br/> |
|**Terceiro servidor de nome** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Quarto servidor de nome** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![Google-Domains-BP-redelegar-1-7](../../media/e008dccb-d789-4f52-8ecc-02831b7c6fb2.png)
  
4. Selecione o controle **+ (Adicionar)** para criar uma linha vazia. 
    
    ![Google-Domains-BP-Redelegate-1-8](../../media/6ce40b1e-8464-443f-a64a-825dc8764590.png)
  
5. Adicione os outros dois registros Nameserver.
    
    Na seção **usar servidores de nomes personalizados** , crie um registro usando os valores da próxima linha na tabela e, em seguida, selecione o controle **+ (Adicionar)** para adicionar outra linha. 
    
    Repita esse processo até ter criado todos os quatro registros Nameserver.
    
6. Selecione **Salvar**.
    
    ![Google-Domains-BP-Redelegate-1-5](../../media/cb954aa2-12ee-4e90-9b67-184cbe898bbb.png)
  
> [!NOTE]
> As atualizações de registro do servidor de nomes poderão levar várias horas para entrarem em vigor no sistema DNS da Internet. Em seguida, os seus emails e outros serviços do Office 365 serão todos configurados para funcionar com seu domínio. 
  
