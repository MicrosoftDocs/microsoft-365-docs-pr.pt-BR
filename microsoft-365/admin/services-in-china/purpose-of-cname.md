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
description: Saiba mais sobre o registro CNAME 'MSOID' no Office 365 que direciona você para o melhor servidor para processos de autenticação, para que você receba uma resposta mais rápida.
monikerRange: o365-21vianet
ms.openlocfilehash: aea04391768993c40978d94b50817244cd77405c
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/11/2020
ms.locfileid: "49655479"
---
# <a name="whats-the-purpose-of-the-office-365-cname-record-for-msoid"></a>Qual é o propósito do registro CNAME no Office 365 para MSOID?

 Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.yml)**. 
> [!NOTE]
> O exemplo a seguir só se aplica ao **Office 365 operado pela 21Vianet.
  
Você pode estar se perguntando por que precisa adicionar o registro CNAME "MSOID" no Office 365. Este é um registro que deve ser adicionado para todos os domínios personalizados, independentemente de qual assinatura você usa. Por que você precisa disso? É um pouco técnico, mas essencialmente isso ocorre para que você seja direcionado para o melhor servidor melhor para certos processos de autenticação, a fim de receber respostas mais rápidas.
  
Detalhes técnicos: ao executar um aplicativo cliente que funciona com o Office 365, como o Skype for Business Online, o Outlook, o Windows PowerShell ou a ferramenta de sincronização do Microsoft Azure Active Directory, suas credenciais devem ser autenticadas. O Office 365 usa um registro CNAME para apontar para o ponto de extremidade de autenticação adequado ao seu local, o que garante tempos de resposta de autenticação rápidos.
  
Se o registro CNAME estiver faltando em seu domínio, esses aplicativos usarão um ponto final de autenticação padrão nos Estados Unidos, e a autenticação pode ficar mais lenta. Se este registro CNAME não estiver configurado adequadamente, estes aplicativos não poderão fazer a autenticação; por exemplo se houver um erro de digitação em **Pontos de endereçamento**.
  
 **Se o Office 365 gerenciar os registros DNS do seu domínio,** O Office 365 configura esse registro CNAME para você. 
  
 **Se você estiver gerenciando registros DNS para** seu domínio em seu host DNS, crie esse registro por conta própria seguindo as instruções [para seu host DNS.](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)
  
Se você estiver planejando uma implantação do Office 365 e quiser saber mais sobre todos os registros DNS que talvez precise adicionar ou atualizar, leia sobre eles em Referência: registros do Sistema de Nomes de Domínio Externos para [o Office 365.](https://go.microsoft.com/fwlink/?LinkId=579013)
  

