---
title: Coletar as informações necessárias para criar registros DNS
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
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 77f90d4a-dc7f-4f09-8972-c1b03ea85a67
description: Reúna os valores/informações necessários para criar registros DNS para conectar seu domínio à Microsoft 365 assinatura.
ms.openlocfilehash: c8ff30c27e67c8a29b7122ea80a6a33f0594b1b9
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2021
ms.locfileid: "52582951"
---
# <a name="gather-the-information-you-need-to-create-dns-records"></a>Coletar as informações necessárias para criar registros DNS

 Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.yml)**. 
  
### <a name="step-1-find-the-txt-record-value-and-verify"></a>Etapa 1: encontre o valor do registro TXT e verifique

::: moniker range="o365-worldwide"

1. No centro Microsoft 365 de administração,  vá para a página \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domínios de</a> Instalação.

::: moniker-end

::: moniker range="o365-germany"

1. No centro de administração,  vá para a página > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domínios de</a> Instalação.

::: moniker-end

::: moniker range="o365-21vianet"

1. No centro de administração,  vá para a página > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domínios de</a> Instalação.

::: moniker-end
    
2. Na página **Domínios,** selecione seu domínio e selecione **Iniciar configuração**. Você precisará voltar para o assistente de configuração de domínios para ver o valor específico que precisa adicionar.
    
3. Na página **Verificar domínio,** selecione Adicionar um registro **TXT** em vez disso e selecione **Próximo**.
    
4. Copie o **valor TXT** mostrado. É assim: **MS=msXXXXXXXX**. 
    
5. Vá para [Criar registros DNS em](create-dns-records-at-any-dns-hosting-provider.md)qualquer provedor de hospedagem DNS e selecione seu host DNS na lista de registradores para ver as instruções passo a passo.
    
6. Siga as etapas para criar o registro TXT (ou registro MX) em seu host DNS e verifique o domínio de volta Microsoft 365.

7. Remova o registro TXT (ou registro MX) do host DNS depois que o domínio for verificado Microsoft 365.
    
### <a name="step-2-find-the-mx-record-value-for-email-and-more"></a>Etapa 2: Encontrar o valor do registro MX para email e muito mais

::: moniker range="o365-worldwide"

1. No centro Microsoft 365 de administração,  vá para a página \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domínios de</a> Instalação.

::: moniker-end
    
::: moniker range="o365-germany"

1. No centro de administração,  vá para a página > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domínios de</a> Instalação.

::: moniker-end

::: moniker range="o365-21vianet"

1. No centro de administração,  vá para a página > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domínios de</a> Instalação.

::: moniker-end
    
2. Na página **Domínios**, selecione o seu domínio. 
    
3. Em **Configurações de DNS necessárias**, você verá os registros DNS a serem adicionados.
    
    Você deverá manter essas informações disponíveis enquanto faz alterações em seu host DNS; portanto, copie e cole os valores.
    
    Os grupos de registros DNS listados nessa página dependem das escolhas que você listou em **Objetivo de domínio**.
    
4. Vá para Criar registros DNS em qualquer provedor de hospedagem [DNS](create-dns-records-at-any-dns-hosting-provider.md)e selecione seu host DNS na lista de registradores para ver instruções passo a passo para adicionar registros no site desse host DNS.
    
5. Siga as etapas para criar os registros em seu host DNS.

## <a name="related-content"></a>Conteúdo relacionado

[Perguntas frequentes sobre domínios](../setup/domains-faq.yml) (artigo)

[Localizar e corrigir problemas após adicionar o seu domínio ou registros DNS](find-and-fix-issues.md) (artigo)

[Gerenciar domínios](index.yml) (página de link)