---
title: Qual é o propósito do registro CNAME no Office 365 para MSOID?
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.collection:
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- BCS160
- MET150
- MOE150
ROBOTS: NOINDEX
description: Saiba mais sobre o registro CNAME 'MSOID' no Office 365 que direciona você para o melhor servidor para processos de autenticação, para obter uma resposta mais rápida.
monikerRange: o365-21vianet
ms.openlocfilehash: a1d587abc9db03c9a1f7c5f66711fde3648a0e96
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914301"
---
# <a name="whats-the-purpose-of-the-office-365-cname-record-for-msoid"></a>Qual é o propósito do registro CNAME no Office 365 para MSOID?

 Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.yml)**. 
> [!NOTE]
> O seguinte aplica-se somente a **Office 365 operado pela 21Vianet.
  
Você pode estar se perguntando por que precisa adicionar o registro CNAME "MSOID" no Office 365. Este é um registro que deve ser adicionado para todos os domínios personalizados, independentemente de qual assinatura você usa. Por que você precisa disso? É um pouco técnico, mas essencialmente isso ocorre para que você seja direcionado para o melhor servidor melhor para certos processos de autenticação, a fim de receber respostas mais rápidas.
  
Detalhes técnicos: ao executar um aplicativo cliente que funciona com o Office 365, como o Skype for Business Online, o Outlook, o Windows PowerShell ou a ferramenta de sincronização do Microsoft Azure Active Directory, suas credenciais devem ser autenticadas. O Office 365 usa um registro CNAME para apontar para o ponto de extremidade de autenticação adequado ao seu local, o que garante tempos de resposta de autenticação rápidos.
  
Se o registro CNAME estiver faltando em seu domínio, esses aplicativos usarão um ponto final de autenticação padrão nos Estados Unidos, e a autenticação pode ficar mais lenta. Se este registro CNAME não estiver configurado adequadamente, estes aplicativos não poderão fazer a autenticação; por exemplo se houver um erro de digitação em **Pontos de endereçamento**.
  
 **Se Office 365 gerencia os** registros DNS do seu domínio, Office 365 configura esse registro CNAME para você. 
  
 **Se você estiver gerenciando registros DNS para** seu domínio em seu host DNS, crie esse registro por conta própria seguindo as instruções para seu [host DNS](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).
  
Se você estiver planejando uma implantação de Office 365 e quiser saber mais sobre todos os registros DNS que talvez seja necessário adicionar ou atualizar, leia sobre eles em [Referência:](../../enterprise/external-domain-name-system-records.md)Registros do Sistema de Nomes de Domínio Externo para Office 365 .
