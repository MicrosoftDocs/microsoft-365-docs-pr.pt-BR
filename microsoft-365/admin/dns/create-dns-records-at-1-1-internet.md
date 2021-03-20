---
title: Criar registros DNS em 1&1 IONOS para a Microsoft
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
ms.assetid: 5762c3ca-1de2-4999-bfe5-4c5e25a8957e
description: Saiba como verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços em 1&1 IONOS para Microsoft.
ms.openlocfilehash: 123abd6d1d93f80eb73f187b7ff75ccd90d02980
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910553"
---
# <a name="create-dns-records-at-11-ionos-for-microsoft"></a>Criar registros DNS em 1&1 IONOS para a Microsoft

 Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.yml)**. 
  
> [!CAUTION]
> Observe que 1&IONOS 1 não permite que um domínio tenha um registro MX e um registro CNAME de descoberta automática de nível superior. Isso limita as maneiras pelas quais você pode configurar o Exchange Online para a Microsoft. Há uma solução alternativa, mas recomendamos empresá-la somente se você já tiver experiência com a criação de subdomas em 1&1 IONOS.  > Se, apesar [](../setup/domains-faq.yml) dessa limitação de serviço, você optar por gerenciar seus próprios registros DNS da Microsoft em 1&1 IONOS, siga as etapas deste artigo para verificar seu domínio e configurar registros DNS para email, Skype for Business Online e assim por diante. 
  
Depois de adicionar esses registros em 1&1 IONOS, seu domínio será definido para funcionar com os serviços da Microsoft.
  
  
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-a-txt-record-for-verification"></a>Adicionar um registro TXT para verificação

Antes de usar o seu domínio com a Microsoft, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro de DNS prova à Microsoft que você é o proprietário do domínio.
  
> [!NOTE]
> Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar. 
  
Siga as etapas abaixo ou [assista ao vídeo (início em 0:42)]().
  
1. Para começar, vá para sua página de domínios em 1&1 IONOS usando [este link](https://my.1and1.com/). You'll be prompted to log in.
    
2. Selecione **Gerenciar domínios**.
    
3. Na página **Centro de** Domínio, localize o domínio que você deseja atualizar e selecione o controle **Painel** ( **v**) para esse domínio.
    
4. Na área **Configurações de** Domínio, selecione **Editar Configurações de DNS**.
    
5. Na seção **Registros TXT e SRV,** selecione **Adicionar Registro**.
    
6. In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table. 
    
    (Selecione o valor **Tipo** na lista suspensa.) 
    
    ||||
    |:-----|:-----|:-----|
    |**Tipo** <br/> |**Prefixo** <br/> |**Valor do Nome** <br/> |
    |TXT  <br/> |(Deixe este campo em branco)  <br/> |MS = ms *XXXXXXXX*  <br/> OBSERVAÇÃO: Este é um exemplo. Use aqui seu valor específico de **Destino ou Pontos de Endereçamento**, retirado da tabela. [Como localizo isto?](../get-help-with-domains/information-for-dns-records.md)          |
   
7. Selecione **Salvar**.
    
8. Selecione **Salvar** novamente. 
    
9. Na caixa **de diálogo Editar Configurações** de DNS, selecione **Sim**.
    
10. Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.
    
Agora que você adicionou o registro no site do seu registrador de domínios, retorne ao Microsoft 365 e solicite que o Microsoft 365 procure o registro.
  
Quando a Microsoft encontrar o registro TXT correto, seu domínio estará verificado.
  
1. No centro do administrador da Microsoft, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.

    
2. Na página **Domínios**, clique no domínio que você está verificando. 
    
3. Na página **Configuração**, clique em **Iniciar configuração**.
    
4. Na página **Verificar domínio**, clique em **Verificar**.
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Adicione um registro MX para que o email do domínio vá para a Microsoft.
<a name="BKMK_add_MX"> </a>

Siga as etapas abaixo ou [assista ao vídeo (início em 3:22)]().
  
> [!NOTE]
> Se você se registrou com 1und1.de, [entre aqui](https://go.microsoft.com/fwlink/?linkid=859152). 
  
1. Para começar, vá para sua página de domínios em 1&1 IONOS usando [este link](https://my.1and1.com/). You'll be prompted to log in.
    
2. Selecione **Gerenciar domínios**.
    
3. Na página **Centro de** Domínio, localize o domínio que você deseja atualizar e selecione o controle **Painel** ( **v**) para esse domínio.
    
4. Na área **Configurações de** Domínio, selecione **Editar Configurações de DNS**.
    
5. Na seção **Registros MX,** na área **Mail Exchanger (Registro MX),** selecione **Outro servidor de email**.<br/>(Pode ser necessário rolar para baixo.)<br/>![1 &amp; 1-BP-Configure-2-1](../../media/b0db72ae-9431-460f-ba7a-3268590b892e.png) <br/>
  
6. Se houver registros MX já listados, exclua-os selecionando o registro e pressionando a tecla **Delete** no teclado.<br/>(Se não houver nenhum registro MX já listado, continue na próxima etapa.)<br/>![1 &amp; 1-BP-Configure-2-2](../../media/4a39bac7-7310-481d-bda4-1dd5c220c60f.png)<br/>
  
7. Nas caixas do registro **MX 1**, digite ou copie e cole os valores da tabela a seguir. 
    
    |**MX 1**|**Prioridade**|
    |:-----|:-----|
    | *\<domain-key\>*  .mail.protection.outlook.com  <br/>  OBSERVAÇÃO: Receba sua \<domain-key\> conta da Microsoft. [Como faço para encontrar isso?](../get-help-with-domains/information-for-dns-records.md)          |10   <br/> Para saber mais sobre prioridade, confira [O que é prioridade MX?](../setup/domains-faq.yml) <br/> | 
    
    ![1 e 1 - configurar 2 e 3](../../media/3afb04d1-7bbf-4147-89ae-561e14ded26d.png)<br/>
  
8. Selecione **Salvar**.<br/>(Pode ser necessário rolar para baixo.)<br/>![1 &amp; 1-BP-Configure-2-4](../../media/355b3ba7-4d2b-45ed-aa17-ac4affb54fe3.png)
  
9. Na caixa **de diálogo Editar Configurações** de DNS, selecione **Sim**.<br/>![Selecionar Sim na caixa de diálogo Editar Configurações de DNS](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a>Adicionar os seis registros CNAME necessários para a Microsoft
<a name="BKMK_add_CNAME"> </a>

1&IONOS 1 requer uma solução alternativa para que você possa usar um registro MX juntamente com os registros CNAME necessários para os serviços de email da Microsoft. Essa solução alternativa exige que você crie um conjunto de subdomas em 1&1 IONOS e atribua-os aos registros CNAME.
  
> [!IMPORTANT]
> Verifique se você tem pelo menos dois subdomínios disponíveis antes de iniciar esse procedimento. Recomendamos essa solução somente se você já tiver experiência com a criação de subdomas em 1&1 IONOS. 
  
### <a name="basic-cname-records"></a>Registros CNAME básicos

Siga as etapas abaixo ou [assista ao vídeo (início em 3:57)]().
  
> [!NOTE]
> Se você se registrou com 1und1.de, [entre aqui](https://go.microsoft.com/fwlink/?linkid=859152). 
  
1. Para começar, vá para sua página de domínios em 1&1 IONOS usando [este link](https://my.1and1.com/). You'll be prompted to log in.
    
2. Selecione **Gerenciar domínios**.
    
3. Na página **Centro de** Domínio, localize o domínio que você deseja atualizar e selecione **Gerenciar Subdomas**.<br/>![1 &amp; 1-BP-Configure-3-0](../../media/d570d03f-5c38-463d-809e-5bb9e4fb2777.png) <br/>Agora, você vai criar dois subdomínios e definir um valor **Alias** para cada um.<br/>(Isso é necessário porque 1&1 IONOS suporta apenas um registro CNAME de nível superior, mas a Microsoft requer vários registros CNAME.)<br/>Primeiro, você criará o subdomínio Descoberta Automática.
    
4. Na seção **Visão Geral do Subdomínio,** selecione **Criar Subdomínio**.
    
    ![1&amp;1-BP-Configure-3-1](../../media/95c63639-eb80-443d-8951-98e8b6cdcc4f.png)
  
5. Na caixa **Criar Subdomínio** para o novo subdomínio, digite ou copie e cole somente o valor de **Criar Subdomínio** da tabela a seguir. (Você adicionará o valor **Alias** em uma etapa posterior.)

    |**Criar subdomínio**|**Alias**|
    |:-----|:-----|
    |descoberta automática  <br/> |autodiscover.outlook.com   | 

    ![1 &amp; 1-BP-Configure-3-2](../../media/9be45113-ebaf-48e6-983c-a7e6ff9eea45.png)
  
6. Selecione **Criar Subdomínio**.<br/>![1 &amp; 1-BP-Configure-3-3](../../media/1e7bc874-f174-4597-8c08-df611d16a74d.png)
  
7. Na seção **Visão Geral do Subdomínio,** localize o **subdomínio** de descoberta automática que você acabou de criar e selecione o controle Painel **(v)** para esse subdomínio. <br/>![1 &amp; 1-BP-Configure-3-4](../../media/10e2e446-3e54-4fb2-8a29-8c442536cc31.png)
  
8. Na área **Configurações de Subdomínio,** selecione **Editar Configurações DNS**. <br/>![1 &amp; 1-BP-Configure-3-5](../../media/5c602118-b89b-4897-9faf-0736be8a6a0d.png)
  
9. Na seção **Registros A/AAAA (Endereços IP),** na área **Endereço IP (Registro),** selecione **CNAME**.<br/>![1 &amp; 1-BP-Configure-3-6](../../media/7f57f468-fbee-4440-a53d-3e334d8e5b71.png)
  
10. Na caixa **Alias:**, digite o copie e cole somente o valor **Alias** da tabela a seguir.<br/> 
    
    |**Criar subdomínio**|**Alias**|
    |:-----|:-----|
    |descoberta automática  <br/> |autodiscover.outlook.com   |

    ![1 &amp; 1-BP-Configure-3-7](../../media/afac3118-3337-4f99-98dd-a7ca930230ce.png)
  
11. Marque a caixa de seleção para a isenção de responsabilidade **Estou ciente**.<br/>![1 &amp; 1-BP-Configure-3-8-1](../../media/6c4cac1a-23f2-4ff3-b2d1-3dca908638d2.png)
  
12. Selecione **Salvar**.<br/>![1 &amp; 1-BP-Configure-3-8-2](../../media/ea1dfc06-c175-4146-ab40-da4d162097e1.png)
  
  
### <a name="additional-cname-records"></a>Registros CNAME adicionais

Os registros CNAME adicionais criados no procedimento a seguir habilitam os serviços do Skype for Business Online. Você usará as mesmas etapas que usou para criar os dois registros CNAME já criados.
  
1. Crie o terceiro subdomínio (Lyncdiscover).<br/>Na seção **Visão Geral do Subdomínio,** selecione **Criar Subdomínio**.
    
2. Na caixa **Criar Subdomínio** para o novo subdomínio, digite ou copie e cole somente o valor de **Criar Subdomínio** da tabela a seguir. (Você adicionará o valor **Alias** em uma etapa posterior.)<br/> 
    
    |**Criar subdomínio**|**Alias**|
    |:-----|:-----|
    |lyncdiscover   |webdir.online.lync.com  |
   
3. Selecione **Criar Subdomínio**.
    
4. Na página **Centro de** Domínios, selecione **Gerenciar Subdomas**.
    
5. Na seção **Visão geral do subdomínio,** localmente o subdomínio de descoberta de **lyncdiscover** que você acabou de criar e selecione o controle **Painel (v)** para esse subdomínio. <br/>Na área **Configurações de Subdomínio,** selecione **Editar Configurações DNS**.
    
6. Na seção **Registros A/AAAA (Endereços IP),** na área **Endereço IP (Registro),** selecione **CNAME**.
    
7. Na caixa **Alias:**, digite o copie e cole somente o valor **Alias** da tabela a seguir. <br/>
    
    |**Criar subdomínio**|**Alias**|
    |:-----|:-----|
    |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |
   
8. Marque a caixa de seleção para **o** aviso de isenção de responsabilidade ciente e selecione **Salvar**.
    
9. Na caixa **de diálogo Editar Configurações** de DNS, selecione **Sim**.
    
10. Crie o quarto subdomínio (SIP): <br/>Na seção **Visão Geral do Subdomínio,** selecione **Criar Subdomínio**.
    
11. Na caixa **Criar Subdomínio** para o novo subdomínio, digite ou copie e cole somente o valor de **Criar Subdomínio** da tabela a seguir. (Você adicionará o valor **Alias** em uma etapa posterior.)<br/>
    
    |**Criar subdomínio**|**Alias**|
    |:-----|:-----|
    |sip  <br/> |sipdir.online.lync.com  <br/> |
   
12. Selecione **Criar Subdomínio**.
    
13. Na página **Centro de** Domínios, selecione **Gerenciar Subdomas**.
    
14. Na seção **Visão geral do subdomínio,** encontre o subdomínio **sip** que você acabou de criar e selecione o controle **Painel (v)** para esse subdomínio. <br/>Na área **Configurações de Subdomínio,** selecione **Editar Configurações DNS**.
    
15. Na seção **Registros A/AAAA (Endereços IP),** na área **Endereço IP (Registro),** selecione **CNAME**.
    
16. Na caixa **Alias:**, digite o copie e cole somente o valor **Alias** da tabela a seguir. 
    
    |**Criar subdomínio**|**Alias**|
    |:-----|:-----|
    |sip  <br/> |sipdir.online.lync.com  <br/> |
   
17. Marque a caixa de seleção para **o** aviso de isenção de responsabilidade ciente e selecione **Salvar**.
    
18. Na caixa **de diálogo Editar Configurações** de DNS, selecione **Sim**.
    
### <a name="cname-records-needed-for-mdm"></a>Registros CNAME necessários para o MDM

> [!IMPORTANT]
> Siga o procedimento que você usou para os outros quatro registros CNAME, mas forneça os valores da tabela a seguir. 
  
|**Criar subdomínio**|**Alias**|
|:-----|:-----|
|enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |
|enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Adicionar registro TXT à SPF para ajudar a evitar spam de email

> [!IMPORTANT]
> Não é possível ter mais de um registro TXT para SPF para um domínio. Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam. Se você já possui um registro SPF para seu domínio, não crie um novo para a Microsoft. Em vez disso, adicione os valores necessários da Microsoft ao registro atual para que você tenha um único registro  *SPF*  que inclua ambos os conjuntos de valores. Precisa de exemplos? Confira os [Registros do Sistema de Nomes de Domínios externos para a Microsoft](../../enterprise/external-domain-name-system-records.md). Para validar seu registro SPF, você pode usar uma dessas ferramentas de validação[SPF.](../setup/domains-faq.yml) 
  
Siga as etapas abaixo ou [assista ao vídeo (início em 5:09)]().
  
> [!NOTE]
> Se você se registrou com 1und1.de, [entre aqui](https://go.microsoft.com/fwlink/?linkid=859152). 
  
1. Para começar, vá para sua página de domínios em 1&1 IONOS usando [este link](https://my.1and1.com/). You'll be prompted to log in.
    
2. Selecione **Gerenciar domínios**.
    
3. Na página **Centro de** Domínio, localize o domínio que você deseja atualizar e selecione o controle **Painel** (**v**) para esse domínio.
    
4. Na área **Configurações de** Domínio, selecione **Editar Configurações de DNS**.
    
5. Na seção **Registros TXT e SRV,** selecione **Adicionar Registro**. <br/>(Pode ser necessário rolar para baixo.)
    
6. In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table. <br/>(Selecione o valor **Tipo** na lista suspensa.) <br/>
    
    |**Tipo**|**Prefixo**|**Valor do Nome**|
    |:-----|:-----|:-----|
    |TXT  <br/> |(Leave this field empty.)  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.           | 
    
    ![Registro TXT](../../media/0b3ba3b4-64b9-4d68-9ee1-04eb3a17d4c5.png)
  
7. Selecione **Salvar**.<br/>![Adicionar registro](../../media/0f222eb9-3bfd-4908-9a99-516cc6fb1d0e.png)
  
8. Selecione **Salvar**.<br/>![Salvar registro](../../media/86ed1b59-31b2-4094-9cd4-32b94eb09e35.png)
  
9. Na caixa **de diálogo Editar Configurações** de DNS, selecione **Sim**.<br/>![Selecionar Sim na caixa de diálogo Editar Configurações de DNS](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Adicionar os dois registros SRV necessários para a Microsoft

Siga as etapas abaixo ou [assista ao vídeo (início em 5:51)]().
  
> [!NOTE]
> Se você se registrou com 1und1.de, [entre aqui](https://go.microsoft.com/fwlink/?linkid=859152). 
  
1. Para começar, vá para sua página de domínios em 1&1 IONOS usando [este link](https://my.1and1.com/). You'll be prompted to log in.
    
2. Selecione **Gerenciar domínios**.
    
3. Na página **Centro de** Domínio, localize o domínio que você deseja atualizar e selecione o controle **Painel** ( **v**) para esse domínio.
    
4. Na área **Configurações de** Domínio, selecione **Editar Configurações de DNS**.
    
5. Na seção **Registros TXT e SRV,** selecione **Adicionar Registro**.
    
6. Adicione o primeiro dos dois registros SRV.<br/>Na área **Adicionar Registro**, nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir. <br/>(Escolha os **valores Type** e **TTL** na listada.) 
    
    |**Tipo**|**Serviço**|**Protocolo**|**Nome**|**Host**|**Prioridade**|**Espessura**|**Porta**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV  <br/> |sip  <br/> |tls  <br/> |(Deixe este campo vazio.)  <br/> |sipdir.online.lync.com  <br/> |100  <br/> |1  <br/> |443  <br/> |3.600 (1 hora)  <br/> |
    |SRV  <br/> |sipfederationtls  <br/> |tcp  <br/> |(Deixe este campo vazio.)  <br/> |sipfed.online.lync.com  <br/> |100  <br/> |1  <br/> |5061  <br/> |3.600 (1 hora)  <br/> |  
    
    ![1 &amp; 1-BP-Configure-5-1](../../media/087e337d-926b-42ff-b11d-b449cfaed76c.png)
  
7. Selecione **Salvar**. <br/>![1 &amp; 1-BP-Configure-5-2](../../media/aa5f803d-fb24-48e0-976a-6759c5fd252c.png)
  
8. Selecione **Salvar**. <br/>![1 &amp; 1-BP-Configure-5-3](../../media/097e7e95-4899-4878-b6e7-c3abd8193c52.png)
  
9. Na caixa **de diálogo Editar Configurações** de DNS, selecione **Sim**. <br/>![Selecionar Sim na caixa de diálogo Editar Configurações de DNS](../../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)
  
10. Adicione o outro registro SRV. <br/>Na seção **Registros TXT e SRV,** selecione **Adicionar Registro**. <br/>Na área **Adicionar Registro,** crie um registro usando os valores da outra linha da tabela e selecione Adicionar **,** Salvar **e** **Sim** para concluir o registro. 
    
> [!NOTE]
> Typically it takes about 15 minutes for DNS changes to take effect. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas ou registros DNS](../get-help-with-domains/find-and-fix-issues.md). 
