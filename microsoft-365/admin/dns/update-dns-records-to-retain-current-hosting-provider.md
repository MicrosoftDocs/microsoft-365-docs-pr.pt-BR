---
title: Atualizar registros DNS para manter seu site com seu provedor de hospedagem atual
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 2c4cf347-b897-45c1-a71f-210bdc8f1061
description: Saiba como rotear o tráfego para um site público existente hospedado fora da Microsoft, se você tiver definido a Microsoft para gerenciar registros DNS para seu domínio personalizado.
ms.openlocfilehash: 5d2bf23d4052815fae210d0fdf6635288ff46b57
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645558"
---
# <a name="update-dns-records-to-keep-your-website-with-your-current-hosting-provider"></a>Atualizar registros DNS para manter seu site com seu provedor de hospedagem atual

 **Se você gerenciar os registros microsoft do** seu domínio em seu provedor de hospedagem DNS , você não precisa se preocupar com as etapas neste tópico. Seu site permanecerá no mesmo local e as pessoas ainda vão poder acessá-lo. 
  
 **Se a Microsoft gerenciar seus registros DNS** para rotear o tráfego para um site público existente hospedado fora da Microsoft, depois de adicionar seu domínio à Microsoft, faça o seguinte: 
  
## <a name="update-dns-records-in-the-microsoft-365-admin-center"></a>Atualizar registros DNS no centro de administração do Microsoft 365
1. No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.

2. Na página **Domínios,** selecione o domínio e escolha Registros **DNS.**

3. Em **configurações DNS,** selecione **Registros Personalizados.**

4. Selecione **+ Novo registro personalizado** e insira o seguinte: 
    
   - Para **Tipo DNS**, insira: **A (Endereço)**
    
   - Para **Nome do host ou Alias**, digite o seguinte: **@**
    
   - Para o **Endereço IP**, digite o endereço IP estático no qual seu site está hospedado no momento (por exemplo, 172.16.140.1). 
    
   Esse deve ser um endereço IP  *estático*  do site e não um endereço IP  *dinâmico*  . Verifique com o site o local de hospedagem do seu site para garantir que você pode obter um endereço IP estático para o site público. 
    
5. Selecione **Salvar**. 
    
Além disso, você pode criar um registro CNAME para ajudar os clientes a encontrarem seu site.
  
1. Selecione **+ Novo registro personalizado** e insira o seguinte: 
    
   - Para **Tipo DNS**, insira: **CNAME (Alias)**
    
   - Para **Nome do host ou Alias**, digite: **www**
    
   - Em **Pontos de endereçamento**, digite o FQDN (nome de domínio totalmente qualificado) do seu site (por exemplo, contoso.com). 
    
2. Selecione **Salvar**. 
    
Por último, faça o seguinte:
  
[Atualize os registros NS do seu domínio](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions) para apontar para a Microsoft. 
  
Quando os registros NS tiverem sido atualizados para apontar para a Microsoft, seu domínio será tudo definido. O email será roteado para a Microsoft, e o tráfego para o endereço do seu site continuará a ser encaminhado para o host do site atual.
 
