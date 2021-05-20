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
description: Saiba como direcionar o tráfego para um site público existente hospedado fora da Microsoft, se você definiu a Microsoft para gerenciar registros de DNS para o seu domínio personalizado.
ms.openlocfilehash: 2a1559bbb902375bbc363180cdb4f98ec2b3a939
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572132"
---
# <a name="update-dns-records-to-keep-your-website-with-your-current-hosting-provider"></a>Atualizar registros DNS para manter seu site com seu provedor de hospedagem atual

 **Se você gerenciar os registros microsoft do seu domínio em seu provedor de hospedagem DNS,** você não precisa se preocupar com os passos neste tópico. Seu site permanecerá no mesmo local e as pessoas ainda vão poder acessá-lo. 
  
 **Se a Microsoft gerenciar seus registros de DNS,** para direcionar o tráfego para um site público existente hospedado fora da Microsoft, depois de adicionar seu domínio à Microsoft, faça o seguinte: 
  
## <a name="update-dns-records-in-the-microsoft-365-admin-center"></a>Atualizar registros de DNS no centro administrativo de Microsoft 365
1. No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.

1. Na página **Domínios,** selecione o domínio e escolha **DNS Records**.

1. Selecione **+ Adicionar registro** e digite o seguinte: 
    
   - Para **digitar:** **A (Endereço)**
    
   - Para **Nome do host ou Alias**, digite o seguinte: **@**
    
   - Para o **Endereço IP**, digite o endereço IP estático no qual seu site está hospedado no momento (por exemplo, 172.16.140.1). 
    
   Esse deve ser um endereço IP  *estático*  do site e não um endereço IP  *dinâmico*  . Verifique com o site o local de hospedagem do seu site para garantir que você pode obter um endereço IP estático para o site público. 
    
1. Selecione **Salvar**. 
    
Além disso, você pode criar um registro CNAME para ajudar os clientes a encontrarem seu site.
  
1. Selecione **+ Adicionar registro** e digite o seguinte: 
    
   - Para **digitar:** **CNAME (Alias)**
    
   - Para **Nome do host ou Alias**, digite: **www**
    
   - Em **Pontos de endereçamento**, digite o FQDN (nome de domínio totalmente qualificado) do seu site (por exemplo, contoso.com). 
    
2. Selecione **Salvar**. 
    
Por último, faça o seguinte:
  
[Atualize os registros NS do seu domínio](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) para apontar para a Microsoft. 
  
Quando os registros NS foram atualizados para apontar para a Microsoft, seu domínio está configurado. O e-mail será encaminhado para a Microsoft, e o tráfego para o endereço do seu site continuará a ir para o seu atual host do site.
