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
description: Saiba como rotear o tráfego para um site público existente hospedado fora do Office 365, se você tiver definido o Office 365 para gerenciar registros DNS para o seu domínio personalizado.
ms.openlocfilehash: 3e71925f9b50e5520bd383aa5318db513202f6ec
ms.sourcegitcommit: ff62dd99fa0d4e780da25dc622f93ddc8f7f95a0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/03/2020
ms.locfileid: "43142534"
---
# <a name="update-dns-records-to-keep-your-website-with-your-current-hosting-provider"></a>Atualizar registros DNS para manter seu site com seu provedor de hospedagem atual

 **Se você gerenciar seus registros de domínio do Office 365 em seu provedor de host DNS**, não precisa se preocupar com as etapas desse tópico. Seu site permanecerá no mesmo local e as pessoas ainda vão poder acessá-lo. 
  
 **Se o Office 365 gerenciar os registros DNS** a fim de rotear o tráfego para um site público existente hospedado fora do Office 365, após adicionar o domínio ao Office 365, faça o seguinte: 
  
## <a name="update-dns-records-in-the-microsoft-365-admin-center"></a>Atualizar registros DNS no centro de administração do Microsoft 365
1. No centro de administração, vá para a página **Configurar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a> .

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
  
[Atualize os registros NS do seu domínio](https://support.office.com/article/a46bec33-2c78-4f45-a96c-b64b2a5bae22.aspx) para apontá-los para o Office 365. 
  
Quando os registros NS estiverem atualizados de forma a apontarem para o Office 365, seu domínio estará totalmente configurado. Os emails serão roteados para o Office 365 e o tráfego para o endereço do seu site vai continuar a ser direcionado para o seu provedor de hospedagem atual.
 
