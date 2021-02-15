---
title: Criar registros DNS na eNomCentral para a Microsoft
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
ms.assetid: a6626053-a9c8-445b-81ee-eeb6672fae77
description: Aprenda a verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços na eNomCentral para Microsoft.
ms.openlocfilehash: e6e05b987a893da582ea7fb062eafe421861b970
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658106"
---
# <a name="create-dns-records-at-enomcentral-for-microsoft"></a>Criar registros DNS na eNomCentral para a Microsoft

 **Caso não encontre o conteúdo que está procurando, [verifique as perguntas frequentes sobre domínios](../setup/domains-faq.yml)**.

Se você usa a eNomCentral como provedor de hospedagem DNS, siga as etapas neste artigo para verificar o domínio e configurar registros DNS para o Skype for Business Online, email e outros serviços.

Depois que você adicionar esses registros na eNomCentral, seu domínio será definido para funcionar com os serviços Microsoft.

> [!NOTE]
> Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).

## <a name="add-a-txt-record-for-verification"></a>Adicionar um registro TXT para verificação
<a name="BKMK_verify"> </a>

Antes de usar o seu domínio com a Microsoft, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro de DNS prova à Microsoft que você é o proprietário do domínio.

> [!NOTE]
> Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.

Siga as etapas abaixo ou [assista ao vídeo (inicia em 0:46)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).

1. Para iniciar, vá até a página do seu domínio no site eNom Central usando [este link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). Você será solicitado a fazer o logon.

   ![eNom-BP-Configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)

2. Em **meus domínios,** selecione o nome do domínio que você deseja editar.

   ![eNom-BP-Configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)

3. Na lista suspensa **Gerenciar Domínio**, escolha **Registros do Host**.

   ![eNom-BP-Verify-1-1](../../media/6e4184a1-9525-47a6-8a8a-9600126c0db4.png)

4. Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela.

   Escolha o **valor de Tipo** de Registro na lista drop-down.

   |Nome de Host|Record Type|Endereço|
   |---|---|---|
   |@|TXT|MS = ms *XXXXXXXX*  <br/> **Observação**: esse é um exemplo. Use aqui seu valor específico de **Destino ou Pontos de Endereçamento**, retirado da tabela. [Como localizo isto?](../get-help-with-domains/information-for-dns-records.md)|

   ![eNom-BP-Verify-1-2](../../media/e1f95529-46a6-40f9-9709-9fe66f373bcf.png)

5. Selecione **salvar**.

   ![eNom-BP-Verify-1-3](../../media/d6277ab0-5d03-44e0-968f-fd5de1905423.png)

6. Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.

Agora que você adicionou o registro no site do seu registrador de domínios, retorne ao Microsoft 365 e solicite que o Microsoft 365 procure o registro.

Quando a Microsoft encontrar o registro TXT correto, seu domínio estará verificado.

1. No centro do administrador da Microsoft, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.

2. Na página **Domínios**, clique no domínio que você está verificando.

3. Na página **Configuração**, clique em **Iniciar configuração**.

4. Na página **Verificar domínio**, marque **Verificar**.

> [!NOTE]
> Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Adicione um registro MX para que o email do domínio vá para a Microsoft.
<a name="BKMK_add_MX"> </a>

Siga as etapas abaixo ou [assista ao vídeo (inicia em 3:40)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).

1. Para iniciar, vá até a página do seu domínio no site eNom Central usando [este link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). Você será solicitado a fazer o logon.

   ![eNom-BP-Configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)

2. Em **meus domínios,** selecione o nome do domínio que você deseja editar.

   ![eNom-BP-Configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)

3. Na lista suspensa **Gerenciar Domínio**, escolha **Configurações de Email**.

   ![eNom-BP-Configure-1-3](../../media/4b438629-afdf-4a47-ab11-56644cdb6158.png)

4. Na lista suspensa **Seleção de Serviço**, escolha **Usuário (MX)**.

   ![eNom-BP-Configure-1-4](../../media/7680ab48-b8d1-4573-b20f-4745a5d7c079.png)

5. In the boxes for the new record, type or copy and paste the values from the following table.

   |Nome de Host|Endereço|Pref|
   |---|---|---|
   |@| *\<domain-key\>*  .mail.protection.outlook.com.  <br/> **Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)** <br/> **Observação:** Obter o  *\<domain-key\>*  seu da sua conta da Microsoft. [Como faço para encontrar isso?](../get-help-with-domains/information-for-dns-records.md)|10   <br/> Para saber mais sobre prioridade, confira [O que é prioridade MX?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)|

   ![eNom-BP-Configure-2-1](../../media/c32e8954-8209-4f77-a3a8-4b7aeea325d5.png)

6. Selecione **salvar**.

   ![eNom-BP-Configure-2-2](../../media/cf3058ea-9d30-4747-8cf0-2bc13d5ec6be.png)

7. Se houver outros registros MX existentes, marque as caixas de seleção desses registros para escolhê-los.

   ![eNom-BP-Configure-2-3](../../media/5017ed03-ca76-4c5c-93a7-84ffe24125dc.png)

8. Selecione **excluir marcada.**

   ![eNom-BP-Configure-2-4](../../media/072dc039-bddb-4c1f-bb44-5660e77f14b0.png)

## <a name="add-the-cname-records-that-are-required-for-microsoft"></a>Adicionar os registros CNAME necessários para a Microsoft
<a name="BKMK_add_CNAME"> </a>

Siga as etapas abaixo ou [assista ao vídeo (inicia em 4:24)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).

1. Para iniciar, vá até a página do seu domínio no site eNom Central usando [este link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). Você será solicitado a fazer o logon.

   ![eNom-BP-Configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)

2. Em **meus domínios,** selecione o nome do domínio que você deseja editar.

   ![eNom-BP-Configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)

3. Na lista suspensa **Gerenciar Domínio**, escolha **Registros do Host**.

   ![eNom-BP-Configure-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)

4. Selecione **nova linha.**

   ![eNom-BP-Configure-3-1](../../media/a30f0a88-7b09-411e-9133-e7965bcf1de0.png)

5. Nas caixas dos seis novos registros, digite ou copie e cole os seguintes valores.

   Escolha o **valor de Tipo** de Registro na lista drop-down.

   |Nome de Host|Record Type|Endereço|
   |---|---|---|
   |descoberta automática|CNAME (Alias)|autodiscover.outlook.com.  <br/> **Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**|
   |sip|CNAME (Alias)|sipdir.online.lync.com.  <br/> **Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**|
   |lyncdiscover|CNAME (Alias)|webdir.online.lync.com.  <br/> **Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**|
   |enterpriseregistration|CNAME (Alias)|enterpriseregistration.windows.net.  <br/> **Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**|
   |enterpriseenrollment|CNAME (Alias)|enterpriseenrollment-s.manage.microsoft.com.  <br/> **Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**|

   ![eNom-BP-Configure-3-2](../../media/672371c0-51af-44ba-bb18-80286b7676c1.png)

6. Selecione **salvar**.

   ![eNom-BP-Configure-3-3](../../media/027b57ce-5699-408b-993b-e46a9ac31090.png)

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> Não é possível ter mais de um registro TXT para SPF para um domínio. Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam. Se você já possui um registro SPF para seu domínio, não crie um novo para a Microsoft. Em vez disso, adicione os valores necessários da Microsoft ao registro atual para que você tenha um único registro  *SPF*  que inclua ambos os conjuntos de valores.

Siga as etapas abaixo ou [assista ao vídeo (inicia em 5:12)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).

1. Para iniciar, vá até a página do seu domínio no site eNom Central usando [este link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). Você será solicitado a fazer o logon.

   ![eNom-BP-Configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)

2. Em **meus domínios,** selecione o nome do domínio que você deseja editar.

   ![eNom-BP-Configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)

3. Na lista suspensa **Gerenciar Domínio**, escolha **Registros do Host**.

   ![eNom-BP-Configure-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)

4. Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela.

   Escolha o **valor de Tipo** de Registro na lista drop-down.

   |Nome de Host|Record Type|Endereço|
   |---|---|---|
   |@|TXT|v=spf1 include:spf.protection.outlook.com -all  <br/>**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.|

   ![eNom-BP-Configure-4-1](../../media/64c68697-258d-4044-84b1-c28f4a402e3b.png)

5. Selecione **salvar**.

   ![eNom-BP-Configure-4-2](../../media/89f4effa-349e-4734-96a5-cd80b0cecd60.png)

## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Adicionar os dois registros SRV necessários para a Microsoft
<a name="BKMK_add_SRV"> </a>

Siga as etapas abaixo ou [assista ao vídeo (inicia em 5:50)](https://support.microsoft.com/office/3766a9e8-77dd-4a42-908d-89b076143e7d).

1. Para iniciar, vá até a página do seu domínio no site eNom Central usando [este link](https://www.enomcentral.com/domains/Domain-Manager.aspx?tab=registered). Você será solicitado a fazer o logon.

   ![eNom-BP-Configure-1-1](../../media/6f754710-fd29-4a0a-b362-fa7a5c5ff74f.png)

2. Em **meus domínios,** selecione o nome do domínio que você deseja editar.

   ![eNom-BP-Configure-1-2](../../media/09d53e84-371c-4704-a8ce-e429ce9e133a.png)

3. Na lista suspensa **Gerenciar Domínio**, escolha **Registros do Host**.

   ![eNom-BP-Configure-1-5](../../media/c92c514c-8166-4cba-97e3-ee1d9847d255.png)

4. À direita da nova **linha, selecione** **adicionar registro SRV ou SPF.**

   ![eNom-BP-Configure-5-1](../../media/c73c154d-5aa0-41ef-be25-f43129eb178c.png)

5. Nas caixas dos dois novos registros, digite ou copie e cole os valores da seguinte tabela.

   |Serviço|Protocolo|Priority|Peso|Porta|Destino (Nome do host)|
   |---|---|---|---|---|---|
   |_sip|_tls|100|1 |443|sipdir.online.lync.com.  <br/> **Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**|
   |_sipfederationtls|_tcp|100|1 |5061|sipfed.online.lync.com.  <br/> **Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**|

   ![eNom-BP-Configure-5-2](../../media/4d478f40-780f-43b9-940b-712b09da8c63.png)

6. Selecionar **salvar**

   ![eNom-BP-Configure-5-3](../../media/d03b6f75-49f2-471d-978d-d32c47cd6aa7.png)

> [!NOTE]
> Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).
