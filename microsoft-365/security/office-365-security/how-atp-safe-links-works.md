---
title: Como funcionam os links seguros de ATP do Office 365
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.date: 05/19/2019
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: O recurso de links seguros oferece verificação de horário de clique de hiperlinks em documentos do Office e em mensagens de email. Leia este artigo para saber como os links seguros de ATP funcionam.
ms.openlocfilehash: bb60d57a422d908b013caf7267f21f390769cfb4
ms.sourcegitcommit: 333ecfb8bfeb34f9f08d82d295b40d37de6ba8b9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/29/2019
ms.locfileid: "37772195"
---
# <a name="how-office-365-atp-safe-links-works"></a>Como funcionam os links seguros de ATP do Office 365
         
## <a name="how-atp-safe-links-works-with-urls-in-email"></a>Como os links seguros de ATP funcionam com URLs em email

Em um nível alto, veja como a proteção de [links de segurança ATP](atp-safe-links.md) funciona para URLs em email (hospedado no Office 365, não no local):
  
1. As pessoas recebem mensagens de email, algumas das quais contêm URLs.
    
2. Todos os emails passam pela proteção do Exchange Online, onde os filtros IP e de envelope, proteção contra malware baseado em assinatura, filtros antispam e antimalware são aplicados. 
    
3. O email chega nas caixas de entrada de pessoas.
    
4. Um usuário entra no Office 365 e vai para a caixa de entrada de email.
    
5. O usuário abre uma mensagem de email e clica em uma URL na mensagem de email.
    
6. O recurso de links seguros de ATP verifica imediatamente a URL antes de abrir o site. A URL é identificada como bloqueada, mal-intencionada ou segura.
    
    - Se a URL for um site que está incluído em uma [lista de URLs "não reconfigurar" personalizada](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) para uma política que se aplica ao usuário, o site será aberto. 
    
    - Se a URL for um site incluído na [lista de URLs bloqueadas](set-up-a-custom-blocked-urls-list-wtih-atp.md)da organização, uma [página de aviso](atp-safe-links-warning-pages.md) será aberta. 
    
    - Se a URL for um site que foi determinado como mal-intencionado, uma [página de aviso](atp-safe-links-warning-pages.md) será aberta. 
    
    - Se a URL for para um arquivo baixável e as políticas de [links seguros ATP](set-up-atp-safe-links-policies.md) da sua organização estiverem configuradas para examinar esse conteúdo, o arquivo baixável será verificado. 
    
    - Se a URL for considerada segura, o site abrirá.
    
## <a name="how-atp-safe-links-works-with-urls-in-office-documents"></a>Como links seguros de ATP funciona com URLs em documentos do Office

Em um nível alto, veja como a proteção de [links seguros ATP](atp-safe-links.md) funciona para URLs nos aplicativos do Office 365 ProPlus ou Business Premium (versões atuais do Word, Excel e PowerPoint no Windows, Mac ou em um navegador, aplicativos do Office em dispositivos IOS ou Android, Visio no Windows, OneNote em um navegador):
  
1. As pessoas instalaram o Office 365 ProPlus ou Business Premium em seu computador, smartphone ou Tablet. (Ou, eles estão usando o Office em seu navegador.)
    
2. Um usuário abre uma palavra, Excel, PowerPoint, OneNote (na Web) ou Visio (na área de trabalho) e entra no Office 365 Enterprise usando sua conta corporativa ou de estudante. O documento contém URLs.
    
3. Quando o usuário clica em uma URL no documento, o link é verificado pelo serviço de links seguros de ATP.
    
      - Se a URL for um site que está incluído em uma [lista de URLs "não reconfigurar" personalizada](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) para uma política que se aplica ao usuário, esse usuário será levado ao site. 
    
      - Se a URL for um site que está incluído na [lista de URLs bloqueados personalizada](set-up-a-custom-blocked-urls-list-wtih-atp.md)da organização, o usuário será levado para uma [página de aviso](atp-safe-links-warning-pages.md).
    
      - Se a URL for um site que foi determinado como mal-intencionado, o usuário será levado para uma [página de aviso](atp-safe-links-warning-pages.md).
    
      - Se a URL for para um arquivo baixável e as [políticas de links seguros de ATP](set-up-atp-safe-links-policies.md) estiverem configuradas para examinar esses downloads, o arquivo baixável será verificado. 
    
      - Se a URL for considerada segura, o usuário será levado para o site.
      
      - Se a verificação de URL falhar, a proteção de links seguros não será disparada. Nos clientes de desktop, o usuário será avisado antes de prosseguir com o site.

