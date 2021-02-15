---
title: Alterar os nameservers para configurar a Microsoft com a Bluehost
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
ms.assetid: 7712b6af-329c-43a0-af7b-c4e4c1befb0e
description: 'Saiba como você pode configurar a Microsoft para gerenciar seus registros DNS na Bluehost. '
ms.openlocfilehash: 78b138a501054a573c2b36cc486dda833be7ae35
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658003"
---
# <a name="change-nameservers-to-set-up-microsoft-with-bluehost"></a>Alterar os nameservers para configurar a Microsoft com a Bluehost

 Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.yml)**. 
  
Siga estas instruções se quiser que a Microsoft gerencie seus registros DNS para você. Se preferir, [gerencie todos os registros DNS na Bluehost.](create-dns-records-at-bluehost.md)
  
## <a name="add-a-txt-record-for-verification"></a>Adicionar um registro TXT para verificação

Antes de usar o seu domínio com a Microsoft, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro de DNS prova à Microsoft que você é o proprietário do domínio.
  
> [!NOTE]
> Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar. 
  
1. Para começar, vá para sua página de domínios no Bluehost usando [este link](https://my.bluehost.com/cgi/dm). Será solicitado que você faça logon primeiro.
    
2. Na página **Domínios**, na área **domínio**, localize a linha do domínio que está sendo alterado e marque a caixa de seleção desse domínio. 
    
    (Pode ser necessário rolar para baixo.) 
    
3. Na área **domain_name,** na linha **Editor de Zona DNS,** selecione **Gerenciar registros DNS.**
    
4. On the **DNS Zone Editor** page, in the Add DNS Record area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Selecione o valor **Tipo** na lista suspensa.) 
    
|||||
|:-----|:-----|:-----|:-----|
|**Host Record** <br/> |**TTL** <br/> |**Tipo** <br/> |**TXT Value** <br/> |
|@  <br/> |14400  <br/> |TXT  <br/> |MS = ms *XXXXXXXX* <br/> **Observação**: esse é um exemplo. Use aqui seu valor específico de **Destino ou Pontos de Endereçamento**, retirado da tabela. [Como localizo isto?](../get-help-with-domains/information-for-dns-records.md) <br/> |

   
5. Selecione **adicionar registro**.
    
6. Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.
    
Agora que você adicionou o registro no site do registrador de domínios, volte para a Microsoft e solicite uma pesquisa para o registro.
  
Quando a Microsoft encontrar o registro TXT correto, seu domínio estará verificado.
  
1. No centro do administrador da Microsoft, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.

    
2. Na página **Domínios**, clique no domínio que você está verificando. 
    
3. Na página **Configuração**, clique em **Iniciar configuração**.
    
4. Na página **Verificar domínio**, clique em **Verificar**.
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="change-your-domains-nameserver-ns-records"></a>Alterar os registros de nameserver (NS) de seu domínio

Para concluir a configuração do domínio com a Microsoft, altere os registros NS do seu domínio no registrador de domínios para apontar para os servidores de nomes primário e secundário. Isso configura a Microsoft para atualizar os registros DNS do domínio para você. Todos os registros são adicionados para que os seus emails, o Skype for Business Online e os sites públicos funcionem com o seu domínio e você fique com tudo pronto.
  
> [!CAUTION]
> Quando você altera os registros NS do seu domínio para apontar para os servidores de nomes da Microsoft, todos os serviços atualmente associados ao seu domínio são afetados. Por exemplo, todos os emails enviados para seu domínio (como rob@ *your_domain*  .com) começarão a chegar na Microsoft depois que você fizer essa alteração. 
  
> [!IMPORTANT]
>  O procedimento a seguir mostrará como excluir quaisquer outros nameservers indesejados da lista e também como adicionar os nameservers corretos se eles ainda não estão listados. > Concluir as etapas desta seção, os únicos nameservers que devem estar listados são estes quatro: > ns1.bdm.microsoftonline.com > ns2.bdm.microsoftonline.com > ns3.bdm.microsoftonline.com > ns4.bdm.microsoftonline.com 
  
1. Para começar, vá para sua página de domínios no Bluehost usando [este link](https://my.bluehost.com/cgi/dm). Será solicitado que você faça logon primeiro.
    
2. Na página **domínios,** na área **domain_name,** marque a caixa de seleção do seu domínio e selecione servidores **de nomes.**
    
    ![Bluehost-BP-Redelegate-1-1](../../media/8f384386-197c-4272-9675-82037922dac4.png)
  
3. Na área **domain_name,** selecione **Usar Nameservers Personalizados.**
    
    ![Aprimoramentos nas trajetórias de animação](../../media/9fb47d21-c4ce-4eee-af90-c9569870a329.png)
  
4. Dependendo se há ou não nameservers já listados na página exibida agora, continue para um destes dois procedimentos:
    
  - Se **NÃO HOUVER** nameservers listados, [Se NÃO houver nameservers listados](#if-there-are-no-nameservers-already-listed).
    
  - Se **HOUVER** nameservers listados, [Se HOUVER nameservers listados](#if-there-are-nameservers-already-listed).
    
### <a name="if-there-are-no-nameservers-already-listed"></a>Se NÃO houver nameservers listados

1. Na seção **Usar Nameservers Personalizados**, digite ou copie e cole os valores da tabela a seguir. 
    
|||
|:-----|:-----|
|**Primeira linha vazia** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Segunda linha vazia** <br/> |ns2.bdm.microsoftonline.com  <br/> |
   
   ![Bluehost-BP-Redelegate-1-3-1](../../media/07b13d6d-a34e-45b5-afd5-48ebd4c1344f.png)
  
2. Selecione **Adicionar Linha**.
    
    ![Bluehost-BP-Redelegate-1-3-2](../../media/db34b632-1d10-44b7-aa1f-44bd27bf09e3.png)
  
3. Ainda na seção **Usar Servidores de Nomes Personalizados**, digite ou copie e cole os valores da primeira linha da tabela a seguir para a nova linha vazia. 
    
|||
|:-----|:-----|
|**Terceira linha vazia** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Quarta linha vazia** <br/> |ns4.bdm.microsoftonline.com  <br/> |
  
4. Para adicionar o quarto registro Nameserver, selecione **Adicionar Linha** novamente e crie um registro usando os valores da última linha da tabela acima. 
    
5. Selecione **salvar configurações de nameserver.**
    
    ![Teta](../../media/b24a4cfd-924b-4b6d-ad3d-2dea148fc77f.png)
  
> [!NOTE]
> As atualizações de registro do servidor de nomes poderão levar várias horas para entrarem em vigor no sistema DNS da Internet. Em seguida, seu email da Microsoft e outros serviços serão definidos para funcionar com seu domínio. 
  
### <a name="if-there-are-nameservers-already-listed"></a>Se HOUVER nameservers listados

> [!CAUTION]
> Follow these steps only if you have existing nameservers other than the four correct nameservers. (Ou seja, exclua apenas todos  os nameservers atuais que não são nomeados **ns1.bdm.microsoftonline.com,** **ns2.bdm.microsoftonline.com,** **ns3.bdm.microsoftonline.com** ou **ns4.bdm.microsoftonline.com**.) 
  
1. Se houver outros nameservers listados na área, exclua cada um deles selecionando-os e pressionando a tecla **Delete** no teclado. 
    
    ![Bluehost-BP-Redelegate-1-5](../../media/d1051c43-f8ff-46d7-af26-3975d3f0f621.png)
  
2. Ainda na seção **Usar Nameservers Personalizados**, digite ou copie e cole os valores da tabela a seguir. 
    
|||
|:-----|:-----|
|**Primeira linha vazia** <br/> |ns1.bdm.microsoftonline.com  <br/> |
|**Segunda linha vazia** <br/> |ns2.bdm.microsoftonline.com  <br/> |
   
   ![Bluehost-BP-Redelegate-1-3](../../media/1523debf-5eb0-4765-8e05-bcd56e375c20.png)
  
3. Selecione **Adicionar Linha**.
    
    ![Bluehost-BP-Redelegate-1-3-2](../../media/db34b632-1d10-44b7-aa1f-44bd27bf09e3.png)
  
4. Ainda na seção **Usar Servidores de Nomes Personalizados**, digite ou copie e cole os valores da primeira linha da tabela a seguir para a nova linha vazia. 
    
|||
|:-----|:-----|
|**Terceira linha vazia** <br/> |ns3.bdm.microsoftonline.com  <br/> |
|**Quarta linha vazia** <br/> |ns4.bdm.microsoftonline.com  <br/> |
   
   ![Bluehost-BP-Redelegate-1-3-3](../../media/480b32bb-af27-40a5-90c5-5617ed02bb41.png)
  
5. Para adicionar o quarto registro Nameserver, selecione **Adicionar Linha** novamente e crie um registro usando os valores da última linha da tabela acima. 
    
6. Selecione **salvar configurações de nameserver.**
    
    ![Teta](../../media/b24a4cfd-924b-4b6d-ad3d-2dea148fc77f.png)
  
> [!NOTE]
> As atualizações de registro do servidor de nomes poderão levar várias horas para entrarem em vigor no sistema DNS da Internet. Em seguida, seu email da Microsoft e outros serviços serão definidos para funcionar com seu domínio. 
  
