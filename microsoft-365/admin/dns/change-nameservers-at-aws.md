---
title: Alterar os nameservers para configurar o Office 365 com a AWS (Amazon Web Services)
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
ms.assetid: 0ddbe33c-81ea-4c02-8db9-e71d3810c0ec
description: 'Saiba como você pode configurar o Office 365 para gerenciar seus registros DNS no Amazon Web Services (AWS). '
ms.openlocfilehash: 9500522478c22277c57772ef64b4d0a4b87e8c44
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/02/2020
ms.locfileid: "42352482"
---
# <a name="change-nameservers-to-set-up-office-365-with-amazon-web-services-aws"></a>Alterar os nameservers para configurar o Office 365 com a AWS (Amazon Web Services)

 **Caso não encontre o conteúdo que está procurando, [verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**. 
  
Siga essas instruções se desejar que o Office 365 gerencie os registros DNS do Office 365 para você. Se preferir, [gerencie todos os registros DNS do Office 365 no AWS](create-dns-records-at-aws.md).
  
    
## <a name="add-a-txt-record-for-verification"></a>Adicionar um registro TXT para verificação

Antes de usar o seu domínio com o Office 365, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro DNS prova ao Office 365 que você é o proprietário do domínio.
  
> [!NOTE]
> Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar. 
  
1. Para começar, vá para sua página de domínios no AWS usando [este link](https://console.aws.amazon.com/route53/home). Você será solicitado a fazer logon primeiro.
    
2. Na página **recursos** , selecione **zonas hospedadas**.
    
3. Na página **zonas hospedadas** , na coluna **nome do domínio** , selecione o nome do domínio que você deseja editar. 
    
4. Selecione **criar conjunto de registros**.
    
5. In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Choose the **Type** and **Routing Policy** values from the drop-down lists.) 
    
    > [!TIP]
    > The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually. 
  
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Nome** <br/> |**Tipo** <br/> |**Alias** <br/> |**TTL (Segundos)** <br/> |**Valor** <br/> |**Política de Roteamento** <br/> |
|(Deixe este campo vazio)  <br/> |TXT - Text  <br/> |Não  <br/> |300  <br/> |MS = ms *XXXXXXXX* <br/> **Observação**: esse é um exemplo. Use seu valor específico de **Destinos ou Pontos de Endereçamento** aqui, da tabela no Office 365. [Como localizo isto?](../get-help-with-domains/information-for-dns-records.md)  <br/>  |Simples <br/> |
   
6. Selecione **Criar**.
    
7. Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.
    
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
> Ao alterar os registros NS do domínio para direcionar para os servidores de nome do Office 365, todos os serviços associados atualmente a esse domínio serão afetados. Por exemplo, todos os emails enviados para seu domínio (como paulo@ *seu_domínio*  .com) vão começar a chegar no Office 365, depois que essa alteração for feita. 
  
> [!IMPORTANT]
>  O procedimento a seguir mostrará como excluir outros nameservers indesejados da lista e também como adicionar os nameservers corretos se eles ainda não estiverem listados. > quando você tiver concluído as etapas nesta seção, os únicos nameservers que devem ser listados são estes quatro: > ns1.bdm.microsoftonline.com > ns2.bdm.microsoftonline.com > ns3.bdm.microsoftonline.com > ns4.bdm.microsoftonline.com 
  
1. Para começar, vá para sua página de domínios no AWS usando [este link](https://console.aws.amazon.com/route53/home). Você será solicitado a fazer logon primeiro.
    
2. Na página **recursos** , selecione **zonas hospedadas**.
    
3. Na página **zonas hospedadas** , na coluna **nome do domínio** , selecione o nome do domínio que você deseja editar. 
    
4. Selecione o conjunto de registros **Nameserver**. 
    
    ![Select the recordset](../../media/24e618e4-0a16-43a2-9886-f4f5dac79374.png)
  
5. No conjunto de registros **NS - Name server** na caixa **Valor**, exclua todos os nameservers selecionando todos eles e pressionando a tecla **Delete** no teclado. 
    
    > [!CAUTION]
    > Follow these steps only if you have existing nameservers other than the four correct nameservers. (Ou seja, exclua somente os nameservers atuais que *não* sejam denominados **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **NS3.bdm.microsoftonline.com**ou **NS4.bdm.microsoftonline.com**.) 
  
    ![Select and delete all of the nameservers in the Value box](../../media/ecf1e897-fa7d-4abc-b00b-bf55b8ed2139.png)
  
6. Na área **TTL (segundos):** , selecione **1h** (1 hora). 
    
    ![Selecionar 1H por uma hora](../../media/c70070e1-4bde-41a7-b271-9d22c475edf6.png)
  
7. Ainda no conjunto de registros **NS - Nameserver**, na caixa **Valor**, digite ou copie e cole o valor **Primeira linha** da tabela a seguir, pressione a tecla **Enter** no teclado e digite ou copie e cole o valor da próxima **linha**. 
    
    > [!IMPORTANT]
    > Cada valor de nameserver  *tem que*  estar em sua própria linha separada dentro da caixa **Valor**, conforme mostrado na ilustração a seguir. 
  
|||
|:-----|:-----|
|**Primeira linha** <br/> |ns1.bdm.microsoftonline.com.  <br/> **This value MUST end with a period (.)** <br/> |
|**Segunda linha** <br/> |ns2.bdm.microsoftonline.com.  <br/> **This value MUST end with a period (.)** <br/> |
|**Terceira linha** <br/> |ns3.bdm.microsoftonline.com.  <br/> **Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)** <br/> |
|**Quarta linha** <br/> |ns4.bdm.microsoftonline.com.  <br/> **Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)** <br/> |
   
   ![Digite ou cole o valor da primeira linha na caixa de valor](../../media/b63f41e0-51ef-4ab2-a4b8-ee7380e5ab35.png)
  
8. Selecione **Salvar conjunto de registros**.
    
    ![Selecionar Salvar conjunto de registros](../../media/ab3c0558-bb7c-41e4-871e-ea82f1553476.png)
  
> [!NOTE]
> As atualizações de registro do servidor de nomes poderão levar várias horas para entrarem em vigor no sistema DNS da Internet. Em seguida, os seus emails e outros serviços do Office 365 serão todos configurados para funcionar com seu domínio. 
