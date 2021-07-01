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
description: Saiba como rotear o tráfego para um site público existente hospedado fora da Microsoft, se você definiu a Microsoft para gerenciar registros DNS para seu domínio personalizado.
ms.openlocfilehash: d54aa4583862ce19907a3b8494a333bbb925e436
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228118"
---
# <a name="update-dns-records-to-keep-your-website-with-your-current-hosting-provider"></a>Atualizar registros DNS para manter seu site com seu provedor de hospedagem atual

 **Se você gerenciar os registros microsoft do** seu domínio em seu provedor de hospedagem DNS, não será necessário se preocupar com as etapas neste tópico. Seu site permanecerá no mesmo local e as pessoas ainda vão poder acessá-lo. 
  
 **Se a Microsoft gerenciar** seus registros DNS , para rotear o tráfego para um site público existente hospedado fora da Microsoft, depois de adicionar seu domínio à Microsoft, faça o seguinte: 
  
## <a name="update-dns-records-in-the-microsoft-365-admin-center"></a>Atualizar registros DNS no Centro de administração do Microsoft 365
1. No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.

1. Na página **Domínios,** selecione o domínio e escolha **Registros DNS**.

1. Selecione **+ Adicionar registro** e insira o seguinte: 
    
   - Para **digite** enter: **A (Address)**
    
   - Para **Nome do host ou Alias**, digite o seguinte: **@**
    
   - Para o **Endereço IP**, digite o endereço IP estático no qual seu site está hospedado no momento (por exemplo, 172.16.140.1). 
    
   Esse deve ser um endereço IP  *estático*  do site e não um endereço IP  *dinâmico*  . Verifique com o site o local de hospedagem do seu site para garantir que você pode obter um endereço IP estático para o site público. 
    
1. Selecione **Salvar**. 
    
Além disso, você pode criar um registro CNAME para ajudar os clientes a encontrarem seu site.
  
1. Selecione **+ Adicionar registro** e insira o seguinte: 
    
   - Para **digite** enter: **CNAME (Alias)**
    
   - Para **Nome do host ou Alias**, digite: **www**
    
   - Em **Pontos de endereçamento**, digite o FQDN (nome de domínio totalmente qualificado) do seu site (por exemplo, contoso.com). 
    
2. Selecione **Salvar**. 
    
Por último, faça o seguinte:
  
[Atualize os registros NS do seu domínio](../setup/add-domain.md) para apontar para a Microsoft. 
  
Quando os registros NS foram atualizados para apontar para a Microsoft, seu domínio é todo definido. O email será roteado para a Microsoft, e o tráfego para seu endereço de site continuará a ir para o host do site atual.
