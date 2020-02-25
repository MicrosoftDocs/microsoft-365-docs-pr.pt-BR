---
title: Qual é o propósito do registro CNAME no Office 365 para MSOID?
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.collection:
- Adm_O365
- Adm_NonTOC
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- BCS160
- MET150
- MOE150
ROBOTS: NOINDEX
description: Saiba mais sobre o registro CNAME ' MSOID ' no Office 365 que o direciona para o melhor servidor para processos de autenticação, portanto, você terá um elemento de resposta mais rápido.
monikerRange: o365-21vianet
ms.openlocfilehash: fdf728dcaebf65485b1eaed9b41e49f5327e9a41
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42251373"
---
# <a name="whats-the-purpose-of-the-office-365-cname-record-for-msoid"></a>Qual é o propósito do registro CNAME no Office 365 para MSOID?

 Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**. 
> [!NOTE]
> Os itens a seguir aplicam-se apenas ao * * Office 365 operado pela 21Vianet.
  
Você pode estar se perguntando por que precisa adicionar o registro CNAME "MSOID" no Office 365. Este é um registro que deve ser adicionado para todos os domínios personalizados, independentemente de qual assinatura você usa. Por que você precisa disso? É um pouco técnico, mas essencialmente isso ocorre para que você seja direcionado para o melhor servidor melhor para certos processos de autenticação, a fim de receber respostas mais rápidas.
  
Detalhes técnicos: ao executar um aplicativo cliente que funciona com o Office 365, como o Skype for Business Online, o Outlook, o Windows PowerShell ou a ferramenta de sincronização do Microsoft Azure Active Directory, suas credenciais devem ser autenticadas. O Office 365 usa um registro CNAME para apontar para o ponto de extremidade de autenticação adequado ao seu local, o que garante tempos de resposta de autenticação rápidos.
  
Se o registro CNAME estiver faltando em seu domínio, esses aplicativos usarão um ponto final de autenticação padrão nos Estados Unidos, e a autenticação pode ficar mais lenta. Se este registro CNAME não estiver configurado adequadamente, estes aplicativos não poderão fazer a autenticação; por exemplo se houver um erro de digitação em **Pontos de endereçamento**.
  
 **Se o Office 365 gerencia os registros DNS do seu domínio,** O Office 365 configura esse registro CNAME para você. 
  
 **Se você estiver Gerenciando registros DNS para seu domínio no seu host DNS,** crie este registro por conta própria [seguindo as instruções para o seu host DNS](https://support.office.com/article/b0f3fdca-8a80-4e8e-9ef3-61e8a2a9ab23.aspx).
  
Se você estiver planejando uma implantação do Office 365 e quiser saber mais sobre todos os registros DNS que talvez precise adicionar ou atualizar, leia sobre eles em [referência: registros de sistema de nomes de domínio externo do Office 365](https://go.microsoft.com/fwlink/?LinkId=579013).
  

