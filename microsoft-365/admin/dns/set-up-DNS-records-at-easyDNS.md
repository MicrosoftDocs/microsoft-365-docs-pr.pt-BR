---
title: Criar registros DNS no easyDNS para o Office 365
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
- MET150
- MOE150
ms.assetid: 446babfe-2e08-4cc2-bbfb-c05b854933ac
description: Saiba como verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços em easyDNS para o Office 365.
ms.openlocfilehash: f55f39f36b8abaee2d500c87ccf1e0089caecc9d
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42250702"
---
# <a name="create-dns-records-at-easydns-for-office-365"></a>Criar registros DNS no easyDNS para o Office 365

[Verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md) se não encontrar o que você está procurando. 
  
Você precisará adicionar todos os seguintes registros DNS no site do registrador para rotear emails para o Office 365, usar seu domínio para o Microsoft Teams e o Skype for Business e assim por diante.
  
Observação: os registros SRV não estão disponíveis no momento em todos os pacotes de serviço do easyDNS. Talvez seja necessário atualizar para um nível de serviço superior com o easyDNS para adicionar registros SRV necessários para o Office 365 Skype for Business.
  
## <a name="verify-that-you-own-the-domain-with-a-txt-record"></a>Verificar se você é o proprietário do domínio com um registro TXT

1. Vá para [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) e faça logon com suas credenciais. 
    
2. No cabeçalho **todos os domínios** , selecione **DNS.**
    
3. No cabeçalho **registros txt** , selecione o botão Editar (ícone de chave inglesa). 
    
4. Insira os seguintes registros nos campos de texto:
    
    |**Host**|**Text**|
    |:-----|:-----|
    |@  <br/> |MS = msXXXXXXXX (use o valor fornecido na página domínios do centro de administração)  <br/> |
   
5. Selecione **Avançar**. 
    
6. Verifique se o registro está correto e, em seguida, selecione **confirmar**. 
    
7. Aguarde alguns minutos antes de continuar, para que o registro que você acabou de criar possa se propagar pela Internet e seja detectado pelo Office 365.
    
8. Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.
    
9. No centro de administração, vá para a página de <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a> de **configurações** \> .
    
10. Na página **domínios** , selecione o domínio que você está verificando. 
    
11. Na página **configuração** , selecione **Iniciar configuração.**
    
12. Na página **verificar domínio** , selecione **verificar**. 
    
## <a name="add-an-mx-record-to-route-email-to-office-365"></a>Adicionar um registro MX para encaminhar emails para o Office 365

1. Vá para [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) e faça logon com suas credenciais. 
    
2. No cabeçalho **todos os domínios** , selecione **DNS.**
    
3. No cabeçalho **registros MX** , selecione o botão Editar (ícone de chave inglesa). 
    
4. Insira os seguintes registros nos campos de texto:
    
    |**EMAIL PARA A ZONA**|**SERVIDOR DE EMAIL**|**PREF**|
    |:-----|:-----|:-----|
    |@  <br/> |\<Domain-Key\>. mail.Protection.Outlook.com (obter seu \<valor de chave\> de domínio na página domínios do centro de administração)  <br/> |,0  <br/> |
   
2. Se você quiser salvar seus outros registros MX para fins de backup, copie-os para baixo em algum lugar. Antes de prosseguir, remova todos os outros registros MX aqui.
    
5. Selecione **Avançar**. 
    
6. Verifique se o registro está correto e, em seguida, selecione **confirmar**. 
    
## <a name="add-the-required-cname-records"></a>Adicionar os registros CNAME necessários

1. Vá para [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) e faça logon com suas credenciais. 
    
2. No cabeçalho **todos os domínios** , selecione **DNS.**
    
3. No título **registros CNAME/alias** , selecione o botão Editar (ícone de uma chave inglesa). 
    
4. Insira os seguintes registros nos campos de texto:


    |**HOST**|**Endereço (deve terminar com um ".")**|
    |:-----|:-----|
    |autodiscover  <br/> |autodiscover.outlook.com.  <br/> |
    |sip  <br/> |sipdir.online.lync.com.  <br/> |
    |lyncdiscover  <br/> |webdir.online.lync.com.  <br/> |
    |enterpriseregistration  <br/> |enterpriseregistration.windows.net.  <br/> |
    |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> |
   
5. Selecione **Avançar**. 
    
6. Verifique se o registro está correto e, em seguida, selecione **confirmar**. 
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Adicionar registro TXT à SPF para ajudar a evitar spam de email

1. Vá para [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) e faça logon com suas credenciais. 
    
2. No cabeçalho **todos os domínios** , selecione **DNS.**
    
3. No cabeçalho **registros txt** , selecione o botão Editar (ícone de chave inglesa). 
    
4. Insira os seguintes registros nos campos de texto:
    
    |**Host**|**Text**|
    |:-----|:-----|
    |@  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> |
   
5. Selecione **Avançar**. 
    
6. Verifique se o registro está correto e, em seguida, selecione **confirmar**. 
    
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a>Adicionar os dois registros SRV necessários para o Office 365

Observação: os registros SRV não estão disponíveis no momento no easyDNS ' domínio mais nível de serviço. Talvez seja necessário atualizar para um nível de serviço superior com o easyDNS para adicionar registros SRV 
  
1. Vá para [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) e faça logon com suas credenciais. 
    
2. No cabeçalho **todos os domínios** , selecione **DNS.**
    
3. No cabeçalho **Registros SRV** , selecione o botão Editar (ícone de chave inglesa). 
    
4. Insira os seguintes registros nos campos de texto:
    
    |**SERVIÇO**|**PROTOCOLO**|**HOST**|**PRI**|**WGT**|**PORTA**|**TARGET (deve terminar com um ".")**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip  <br/> |TLS  <br/> |@  <br/> |100  <br/> |1  <br/> |443  <br/> |sipdir.online.lync.com.  <br/> |1800  <br/> |
    |_sipfederationtls  <br/> |TCP  <br/> |@  <br/> |100  <br/> |1  <br/> |5061  <br/> |sipfed.online.lync.com.  <br/> |1800  <br/> |
   
5. Selecione **Avançar**. 
    
6. Verifique se o registro está correto e, em seguida, selecione **confirmar**. 
    

