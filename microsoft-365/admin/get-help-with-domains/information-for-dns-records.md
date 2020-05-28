---
title: Coletar as informações necessárias para criar registros DNS
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
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 77f90d4a-dc7f-4f09-8972-c1b03ea85a67
description: 'Saiba como localizar os valores/informações de que você precisa para criar registros DNS para o Microsoft 365. '
ms.openlocfilehash: fddd1180f2dd80ffeec2aeec49ed821055dd5f15
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399903"
---
# <a name="gather-the-information-you-need-to-create-dns-records"></a>Coletar as informações necessárias para criar registros DNS

 Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**. 
  
### <a name="step-1-find-the-txt-record-value-and-verify"></a>Etapa 1: localizar o valor do registro TXT e verificar

::: moniker range="o365-worldwide"

1. No centro de administração do Microsoft 365, vá para a página **Configurar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a> .

::: moniker-end

::: moniker range="o365-germany"

1. No centro de administração, vá para a página **Configurar** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">domínios</a> .

::: moniker-end

::: moniker range="o365-21vianet"

1. No centro de administração, vá para a página **Configurar** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">domínios</a> .

::: moniker-end
    
2. Na página **domínios** , selecione seu domínio e, em seguida, selecione **Iniciar configuração**. Você precisará voltar para o assistente de configuração de domínios para ver o valor específico que precisa adicionar.
    
3. Na página **verificar domínio** , selecione **Adicionar um registro txt**e, em seguida, selecione **Avançar**.
    
4. Copie o **valor txt** mostrado. Ele tem a seguinte aparência: **MS = msXXXXXXXX**. 
    
5. Vá para [criar registros DNS em qualquer provedor de Hospedagem de DNS](create-dns-records-at-any-dns-hosting-provider.md)e selecione o seu host DNS na lista de registradores para ver as instruções passo a passo.
    
6. Siga as etapas para criar o registro TXT (ou registro MX) no host DNS e verifique o domínio novamente no Microsoft 365.

7. Remova o registro TXT (ou o registro MX) do seu host DNS depois que o domínio for verificado no Microsoft 365.
    
### <a name="step-2-find-the-mx-record-value-for-email-and-more"></a>Etapa 2: localizar o valor de registro MX para email e muito mais

::: moniker range="o365-worldwide"

1. No centro de administração do Microsoft 365, vá para a página **Configurar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a> .

::: moniker-end
    
::: moniker range="o365-germany"

1. No centro de administração, vá para a página **Configurar** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">domínios</a> .

::: moniker-end

::: moniker range="o365-21vianet"

1. No centro de administração, vá para a página **Configurar** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">domínios</a> .

::: moniker-end
    
2. Na página **Domínios**, selecione o seu domínio. 
    
3. Em **Configurações de DNS necessárias**, você verá os registros DNS a serem adicionados.
    
    Você deverá manter essas informações disponíveis enquanto faz alterações em seu host DNS; portanto, copie e cole os valores.
    
    Os grupos de registros DNS listados nessa página dependem das escolhas que você listou em **Objetivo de domínio**.
    
4. Vá para [criar registros DNS em qualquer provedor de Hospedagem de DNS](create-dns-records-at-any-dns-hosting-provider.md)e selecione o seu host DNS na lista de registradores para ver instruções passo a passo para adicionar registros no site do host DNS.
    
5. Siga as etapas para criar os registros em seu host DNS.
