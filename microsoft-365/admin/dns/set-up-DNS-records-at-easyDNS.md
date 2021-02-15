---
title: Criar registros DNS no easyDNS para a Microsoft
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
- MET150
- MOE150
ms.assetid: 446babfe-2e08-4cc2-bbfb-c05b854933ac
description: Aprenda a verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços no easyDNS para a Microsoft.
ms.openlocfilehash: a971a722f071ef5df9ce0fba387cfacfeb409f5b
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/11/2020
ms.locfileid: "49656814"
---
# <a name="create-dns-records-at-easydns-for-microsoft"></a>Criar registros DNS no easyDNS para a Microsoft

[Verifique as perguntas frequentes sobre ](../setup/domains-faq.yml) domínios se você não encontrar o que está procurando. 
  
Você precisará adicionar todos os seguintes registros DNS no site do registrador para roteá-los para a Microsoft, usar seu domínio para o Teams e o Skype for Business e assim por diante.
  
OBSERVAÇÃO: No momento, os registros SRV NÃO estão disponíveis em todos os pacotes de serviço easyDNS. Talvez seja necessário atualizar para um nível de serviço superior com easyDNS para adicionar registros SRV necessários para o Skype for Business.
  
## <a name="verify-that-you-own-the-domain-with-a-txt-record"></a>Verifique se você é o próprio domínio com um registro TXT

1. Vá para [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) e entre com suas credenciais. 
    
2. No título **de todos os domínios,** selecione **dns.**
    
3. Sob o **título de registros TXT,** selecione o botão de edição (ícone chave inglesa). 
    
4. Insira os seguintes registros nos campos de texto:
    
    |**Host**|**Text**|
    |:-----|:-----|
    |@  <br/> |MS=msXXXXXXXX (use o valor fornecido na página Domínios do centro de administração)  <br/> |
   
5. Selecione **NEXT**. 
    
6. Verifique se o registro está correto e selecione **CONFIRMAR.** 
    
7. Aguarde alguns minutos antes de continuar, para que o registro que você acabou de criar possa se propagar pela Internet e ser detectado pela Microsoft.
    
8. Agora que você adicionou o registro no site do seu registrador de domínios, retorne à Microsoft e solicite o registro.
    
9. No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.
    
10. Na página **Domínios**, clique no domínio que você está verificando. 
    
11. Na página **Configuração,** selecione **Iniciar configuração.**
    
12. Na página **Verificar domínio**, clique em **Verificar**. 
    
## <a name="add-an-mx-record-to-route-email-to-microsoft"></a>Adicionar um registro MX para rotear emails para a Microsoft

1. Vá para [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) e entre com suas credenciais. 
    
2. No título **de todos os domínios,** selecione **dns.**
    
3. Sob o **título de registros MX,** selecione o botão editar (ícone chave inglesa). 
    
4. Insira os seguintes registros nos campos de texto:
    
    |**EMAIL PARA ZONA**|**SERVIDOR DE EMAIL**|**PREF**|
    |:-----|:-----|:-----|
    |@  <br/> |\<domain-key\>.mail.protection.outlook.com (Obter seu \<domain-key\> valor na página Domínios do centro de administração)  <br/> |0  <br/> |
   
2. Se você quiser salvar seus outros registros MX para fins de backup, copie-os em algum lugar. Antes de continuar, remova todos os outros registros MX aqui.
    
5. Selecione **NEXT**. 
    
6. Verifique se o registro está correto e selecione **CONFIRMAR.** 
    
## <a name="add-the-required-cname-records"></a>Adicionar os registros CNAME necessários

1. Vá para [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) e entre com suas credenciais. 
    
2. No título **de todos os domínios,** selecione **dns.**
    
3. Sob o **título de registros CNAME/Alias,** selecione o botão de edição (ícone chave inglesa). 
    
4. Insira os seguintes registros nos campos de texto:


    |**HOST**|**Endereço (deve terminar com um ".")**|
    |:-----|:-----|
    |autodiscover  <br/> |autodiscover.outlook.com.  <br/> |
    |sip  <br/> |sipdir.online.lync.com.  <br/> |
    |lyncdiscover  <br/> |webdir.online.lync.com.  <br/> |
    |enterpriseregistration  <br/> |enterpriseregistration.windows.net.  <br/> |
    |enterpriseenrollment  <br/> |enterpriseenrollment-s.manage.microsoft.com.  <br/> |
   
5. Selecione **NEXT**. 
    
6. Verifique se o registro está correto e selecione **CONFIRMAR.** 
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail

1. Vá para [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) e entre com suas credenciais. 
    
2. No título **de todos os domínios,** selecione **dns.**
    
3. Sob o **título de registros TXT,** selecione o botão de edição (ícone chave inglesa). 
    
4. Insira os seguintes registros nos campos de texto:
    
    |**Host**|**Text**|
    |:-----|:-----|
    |@  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/> |
   
5. Selecione **NEXT**. 
    
6. Verifique se o registro está correto e selecione **CONFIRMAR.** 
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a>Adicionar os dois registros SRV necessários para a Microsoft

OBSERVAÇÃO: No momento, os registros SRV NÃO estão disponíveis no nível de serviço Do Domínio Plus do easyDNS. Talvez seja necessário atualizar para um nível de serviço superior com easyDNS para adicionar registros SRV 
  
1. Vá para [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) e entre com suas credenciais. 
    
2. No título **de todos os domínios,** selecione **dns.**
    
3. Sob o **título de registros SRV,** selecione o botão editar (ícone chave inglesa). 
    
4. Insira os seguintes registros nos campos de texto:
    
    |**SERVIÇO**|**PROTO**|**HOST**|**PRI**|**WGT**|**PORTA**|**TARGET(Deve terminar com ".")**|**TTL**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |_sip  <br/> |TLS  <br/> |@  <br/> |100  <br/> |1   <br/> |443  <br/> |sipdir.online.lync.com.  <br/> |1800  <br/> |
    |_sipfederationtls  <br/> |TCP  <br/> |@  <br/> |100  <br/> |1   <br/> |5061  <br/> |sipfed.online.lync.com.  <br/> |1800  <br/> |
   
5. Selecione **NEXT**. 
    
6. Verifique se o registro está correto e selecione **CONFIRMAR.** 
    

