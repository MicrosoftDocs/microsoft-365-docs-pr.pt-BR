---
title: Atualizar registros DNS para manter seu site com seu provedor de hospedagem atual
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 2c4cf347-b897-45c1-a71f-210bdc8f1061
description: Saiba como rotear o tráfego para um site público existente hospedado fora da Microsoft, se você tiver configurado o Microsoft para gerenciar registros DNS para o seu domínio personalizado.
ms.openlocfilehash: 58b58479a2c880cc0193058abc328cc5feea4af1
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2020
ms.locfileid: "44048826"
---
# <a name="update-dns-records-to-keep-your-website-with-your-current-hosting-provider"></a>Atualizar registros DNS para manter seu site com seu provedor de hospedagem atual

 **Se você gerencia os registros da Microsoft do seu domínio em seu provedor de Hospedagem de DNS**, não precisa se preocupar com as etapas deste tópico. Seu site permanecerá no mesmo local e as pessoas ainda vão poder acessá-lo. 
  
 **Se a Microsoft gerencia seus registros DNS**, para rotear o tráfego para um site público existente hospedado fora da Microsoft, após adicionar seu domínio à Microsoft, faça o seguinte: 
  
## <a name="update-dns-records-in-the-microsoft-365-admin-center"></a>Atualizar registros DNS no centro de administração do Microsoft 365
1. No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.

2. Na página **Domínios**, selecione o domínio que você usa para o site na lista de domínios e selecione **Configurações de DNS**, no Painel Gerenciamento. 
    
3. Selecione **+ Novo registro personalizado** e insira o seguinte: 
    
  - Para **Tipo DNS**, insira: **A (Endereço)**
    
  - Para **Nome do host ou Alias**, digite o seguinte: **@**
    
  - Para o **Endereço IP**, digite o endereço IP estático no qual seu site está hospedado no momento (por exemplo, 172.16.140.1). 
    
    Esse deve ser um endereço IP  *estático*  do site e não um endereço IP  *dinâmico*  . Verifique com o site o local de hospedagem do seu site para garantir que você pode obter um endereço IP estático para o site público. 
    
3. Selecione **Salvar**. 
    
Além disso, você pode criar um registro CNAME para ajudar os clientes a encontrarem seu site.
  
1. Selecione **+ Novo registro personalizado** e insira o seguinte: 
    
  - Para **Tipo DNS**, insira: **CNAME (Alias)**
    
  - Para **Nome do host ou Alias**, digite: **www**
    
  - Em **Pontos de endereçamento**, digite o FQDN (nome de domínio totalmente qualificado) do seu site (por exemplo, contoso.com). 
    
2. Selecione **Salvar**. 
    
Por último, faça o seguinte:
  
[Atualize os registros ns do seu domínio](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions) para apontar para a Microsoft. 
  
Quando os registros NS foram atualizados para apontar para a Microsoft, seu domínio é configurado. Os emails serão roteados para a Microsoft, e o tráfego para o seu endereço de site continuará a ir para o host do site atual.
 
