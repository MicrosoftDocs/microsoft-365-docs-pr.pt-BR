---
title: Criar registros DNS na GoDaddy para o Office 365
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
ms.assetid: f40a9185-b6d5-4a80-bb31-aa3bb0cab48a
description: Saiba como verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços em GoDaddy para o Office 365.
ms.custom: okr_smb
ms.openlocfilehash: 4a67ef090c2b91c4cf1fdde376ab35e3a4ed4e20
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42237021"
---
# <a name="create-dns-records-at-godaddy-for-office-365"></a>Criar registros DNS na GoDaddy para o Office 365

 **Caso não encontre o conteúdo que está procurando, [verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**.

Se você usa a GoDaddy como provedor de hospedagem DNS, realize os procedimentos deste artigo para verificar o domínio e configurar registros DNS para o Skype for Business Online, email e outros serviços.

Depois que você adicionar esses registros na GoDaddy, o domínio será configurado para funcionar com os serviços do Office 365.

Para saber mais sobre hospedagem na Web e DNS para sites com o Office 365, confira [Usar um site público com o Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).

> [!NOTE]
> Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).

## <a name="add-a-txt-record-for-verification"></a>Adicionar um registro TXT para verificação
<a name="BKMK_verify"> </a>

Antes de usar o seu domínio com o Office 365, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro DNS prova ao Office 365 que você é o proprietário do domínio.

> [!NOTE]
> Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.

Siga as etapas abaixo.

1. Para iniciar, vá até a sua página de domínios no GoDaddy usando [este link](https://account.godaddy.com/products/?go_redirect=disabled). Você será solicitado a fazer o logon.

    ![GoDaddy-BP-configure-1-1](../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. Em **domínios**, selecione DNS no domínio que você deseja editar.

    ![GoDaddy-BP-configure-1-2](../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. Selecione **Adicionar**.

    ![GoDaddy-BP-configure-1-4](../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. Escolha o **TXT (texto)** na lista suspensa. In the boxes for the new record, type or copy and paste the values from the following table.

    |**Tipo de registro** |**Host**|**Valor TXT**|**TTL** |
    |:-----|:-----|:-----|:-----|
    |TXT (Texto)|@|MS = ms *XXXXXXXX*<br>**Observação**: Este é um exemplo. Use aqui o valor específico de **Destino ou Pontos de Endereçamento**, retirado da tabela em Office 365. [Como faço para encontrar isso?](../get-help-with-domains/information-for-dns-records.md)|1 hora  <br>(Selecione um valor na lista suspensa.)|

      ![GoDaddy-BP-Verify-1-0](../media/dns/56526870-d6465780-651a-11e9-9cf0-d6fff71e2f62.png)

5. Selecione **Salvar**.

6. Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.

Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.

When Office 365 finds the correct TXT record, your domain is verified.
  
1. No centro de administração, vá para a página de <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a> de **configurações** \> .

    
2. Na página **domínios** , selecione o domínio que você está verificando. 
    
    
  
3. Na página **configuração** , selecione **Iniciar configuração**.



4. Na página **verificar domínio** , selecione **verificar**.



> [!NOTE]
>  Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a>Adicionar um registro MX para que o email do domínio vá para o Office 365
<a name="BKMK_add_MX"> </a>

Siga as etapas abaixo.

1. Para iniciar, vá até a sua página de domínios no GoDaddy usando [este link](https://account.godaddy.com/products/?go_redirect=disabled). Você será solicitado a fazer o logon.

    ![GoDaddy-BP-configure-1-1](../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. Em **domínios**, selecione DNS no domínio que você deseja editar.

    ![GoDaddy-BP-configure-1-2](../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. Selecione **Adicionar**.

    ![GoDaddy-BP-configure-1-4](../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. Escolha **MX (Mail Exchanger)** na lista suspensa.

    ![GoDaddy-BP-configure-2-0](../media/dns/56528642-85842e00-651d-11e9-8dd8-217f468f9a18.png)

5. Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela.

    (Escolha o valor **TTL** na lista suspensa.)

    |**Tipo de registro**|**Host**|**Aponta para**|**Prioridade**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|
    |Servidor de mensagens (MX)  <br/> |@  <br/> | *\<chave-do-domínio\>*  .mail.protection.outlook.com  <br/> **Observação:** Obtenha sua * \<chave\> de domínio* de sua conta do Office 365.           [Como faço para encontrar isso?](../get-help-with-domains/information-for-dns-records.md)          |10   <br/> Para saber mais sobre prioridade, confira [O que é prioridade MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx) <br/> |1 hour  <br/> |

6. Selecione **Salvar**.

## <a name="add-the-cname-records-that-are-required-for-office-365"></a>Adicionar os registros CNAME necessários para o Office 365
<a name="BKMK_add_CNAME"> </a>

Siga as etapas abaixo.

1. Para iniciar, vá até a sua página de domínios no GoDaddy usando [este link](https://account.godaddy.com/products/?go_redirect=disabled). Você será solicitado a fazer o logon.

    ![GoDaddy-BP-configure-1-1](../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. Em **domínios**, selecione DNS no domínio que você deseja editar.

    ![GoDaddy-BP-configure-1-2](../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. Selecione **Adicionar**.

    ![GoDaddy-BP-configure-1-4](../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)


4. Escolha **CNAME (alias)** na lista suspensa.

    ![GoDaddy-BP-configure-3-0](../media/dns/56528891-e7449800-651d-11e9-8eac-112285b8e38c.png)

5. Criar o primeiro registro CNAME.

    Nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir.

    (Escolha o valor **TTL** na lista suspensa.)

    |**Tipo de registro**|**Host**|**Aponta para**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |CNAME (Alias)  <br/> |autodiscover  <br/> |autodiscover.outlook.com  <br/> |1 hour  <br/> |
    |CNAME (Alias)  <br/> |sip  <br/> |sipdir.online.lync.com  <br/> |1 hora  <br/> |
    |CNAME (Alias)  <br/> |lyncdiscover  <br/> |webdir.online.lync.com  <br/> |1 hora  <br/> |
    |CNAME (Alias)  <br/> |enterpriseregistration  <br/> |enterpriseregistration.windows.net  <br/> |1 hora  <br/> |
    |CNAME (Alias)  <br/> |enterpriseenrollment  <br/> |enterpriseenrollment.manage.microsoft.com  <br/> |1 hour  <br/> |



6. Repita essas etapas para adicionar o próximo registro CNAME até ter criado todos os seis registros CNAME.

## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Adicionar registro TXT à SPF para ajudar a evitar spam de email
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. Em vez disso, adicione os valores necessários do Office 365 ao registro atual, de modo que você tenha um  *único*  registro SPF que inclua os dois conjuntos de valores.

Siga as etapas abaixo.

1. Para iniciar, vá até a sua página de domínios no GoDaddy usando [este link](https://account.godaddy.com/products/?go_redirect=disabled). Você será solicitado a fazer o logon.

    ![GoDaddy-BP-configure-1-1](../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. Em **domínios**, selecione DNS no domínio que você deseja editar.

    ![GoDaddy-BP-configure-1-2](../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. Selecione **Adicionar**.

    ![GoDaddy-BP-configure-1-4](../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. Escolha o **TXT (texto)** na lista suspensa.

    ![GoDaddy-BP-configure-4-0](../media/dns/56529449-c0d32c80-651e-11e9-90e9-895aa1c4bbf1.png)

5. Nas caixas do novo registro, digite ou copie e cole os seguintes valores.

    (Escolha o valor **TTL** nas listas suspensas.)

    |**Tipo de registro**|**Host**|**Valor TXT**|**TTL**|
    |:-----|:-----|:-----|:-----|
    |TXT (Texto)  <br/> |@  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> **Observação:** É recomendável copiar e colar essa entrada, para que todo o espaçamento permaneça correto.           |1 hour  <br/> |

    ![GoDaddy-BP-configure-4-1](../media/7c724f02-c9b3-42ab-b9c0-78959fa6ffad.png)

6. Selecione **Salvar**.


## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>Adicionar os dois registros SRV necessários para o Office 365
<a name="BKMK_add_SRV"> </a>

Siga as etapas abaixo.

1. Para iniciar, vá até a sua página de domínios no GoDaddy usando [este link](https://account.godaddy.com/products/?go_redirect=disabled). Você será solicitado a fazer o logon.

    ![GoDaddy-BP-configure-1-1](../media/d6833ec7-9904-43fd-a877-7c663e5f5c25.png)

2. Em **domínios**, selecione DNS no domínio que você deseja editar.

    ![GoDaddy-BP-configure-1-2](../media/dns/56528038-94b6ac00-651c-11e9-8874-12db60cc7ea6.png)

3. Selecione **Adicionar**.

    ![GoDaddy-BP-configure-1-4](../media/dns/56527673-ffb3b300-651b-11e9-91c2-83dc9fe5ca30.png)

4. Escolha o **SRV (Serviço)** na lista suspensa.

    ![GoDaddy-BP-configure-5-0](../media/dns/56529669-1dcee280-651f-11e9-8ba2-ecf4fc2f6dca.png)

5. Crie o primeiro registro SRV.

    Nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir.

    (Escolha os valores **tipo de registro** e **TTL** nas listas suspensas.)

    |**Tipo de registro**|**Nome**|**Target**|**Protocolo**|**Serviço**|**Prioridade**|**Peso**|**Porta**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |SRV (Serviço)  <br/> |@  <br/> |sipdir.online.lync.com  <br/> |_tls  <br/> |_sip  <br/> |100  <br/> |1  <br/> |443  <br/> |1 hora  <br/> |
    |SRV (Serviço)  <br/> |@  <br/> |sipfed.online.lync.com  <br/> |_tcp  <br/> |_sipfederationtls  <br/> |100  <br/> |1  <br/> |5061  <br/> |1 hora  <br/> |

    ![GoDaddy-BP-configure-5-1](../media/a1b15ab1-eb6a-4672-90d1-7ac3e0beb223.png)


6. Repita a **etapa 5** para criar o outro registro SRV.

7. Selecione **Salvar**.

> [!NOTE]
> Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).
