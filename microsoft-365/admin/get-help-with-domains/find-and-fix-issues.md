---
title: Localizar e corrigir problemas após a adição do seu domínio ou de registros DNS
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 40398b0b-bdd0-4afd-ab5e-b5ae6b7990bf
description: Saiba mais sobre os problemas que você tem ao configurar um domínio personalizado certificando-se de que os registros DNS estão configurados corretamente.
ms.openlocfilehash: e3c66e10a673d840cfddad81a057739b6dfac721
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399939"
---
# <a name="find-and-fix-issues-after-adding-your-domain-or-dns-records"></a>Localizar e corrigir problemas após a adição do seu domínio ou de registros DNS

 Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**. 
  
Obter o seu domínio configurado para funcionar com o Microsoft 365 pode ser desafiador. É complicado trabalhar com o sistema DNS, e a configuração DNS do seu domínio afeta atividades comerciais importantes, como o email!

> [!NOTE]
> Você pode verificar se há problemas com seu domínio verificando seu status. Vá para **Configurar**  >  **domínios** e exibir as notificações na coluna **status** . Se você vir um problema, selecione mais ações (três pontos) e escolha **verificar integridade**. O painel que será aberto descreverá todos os problemas que ocorrem com o seu domínio.
  
## <a name="whats-going-on"></a>O que está acontecendo?

- [Não é possível verificar seu domínio?](#cant-verify-your-domain)
    
- [O Outlook não está funcionando?](#outlook-isnt-working)
    
- [OS emails de todos os usuários mudaram para o Microsoft 365 e você só queria que seu email trocasse?](#everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch)

- [Não consegue confirmar o status de conta de estudante ou sem fins lucrativos?](#cant-confirm-non-profit-or-school-account-status)

- [Os serviços não estão funcionando com seu domínio?](#services-not-working-with-your-domain)
    
- [O acesso ao seu site não está funcionando?](#accessing-your-website-isnt-working)

## <a name="cant-verify-your-domain"></a>Não consegue verificar o seu domínio?
<a name="BKMK_verify"> </a>

Há alguns motivos comuns para a verificação de domínios não funcionar como deveria:
  
1. **O valor de registro da verificação não está correto.** Verifique se você copiou e colou o valor exato no registro de verificação TXT no seu host DNS. Um problema comum é não incluir a parte "MS=" no registro. Precisamos disso também! 
    
2. **O registro não foi salvo.** Em alguns hosts DNS, você pode ter que executar uma etapa extra para salvar o arquivo de zona (local em que o registro DNS é armazenado) para que o registro seja atualizado na Internet. Certifique-se de ter salvo suas alterações para que o Microsoft 365 possa ver e verificar o registro. 
    
3. **O registro não foi atualizado na Internet.** Normalmente, apenas alguns minutos levam alguns minutos para que possamos ver o novo registro, mas, ocasionalmente, pode levar algumas horas. 
    
## <a name="outlook-isnt-working"></a>O Outlook não está funcionando?
<a name="BKMK_OutlookBroken"> </a>

Se você configurou o registro MX e os outros registros DNS corretamente para o seu domínio, mas o seu email não funciona, deixe-nos ajudá-lo a [corrigir os problemas do Outlook](https://docs.microsoft.com/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues).
  
## <a name="everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch"></a>OS emails de todos os usuários mudaram para o Microsoft 365 e você só queria que seu email trocasse?
<a name="BKMK_EmailSwitched"> </a>

Quando você adiciona seu domínio ao Microsoft 365, normalmente o registro MX do seu domínio é atualizado (por você ou pelo Microsoft 365) para apontar para o Microsoft 365, e todos os emails enviados para esse domínio começarão a ser o Microsoft 365. Certifique-se de ter criado caixas de correio no Microsoft 365 para todos que têm emails no seu domínio antes de alterar o registro MX.
  
E se você não quiser mover emails para todas as pessoas em seu domínio para a Microsoft 365? Você pode executar etapas para [o Microsoft 365 piloto com apenas alguns endereços de email](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq).
  
## <a name="cant-confirm-non-profit-or-school-account-status"></a>Não consegue confirmar o status de conta de estudante ou sem fins lucrativos?
<a name="BKMK_validateAcct"> </a>

Há alguns cenários em que você só precisa verificar o domínio da sua organização e não configurar nenhum serviço. Por exemplo, para provar à Microsoft 365 que sua organização é qualificada para uma assinatura escolar.
  
Confira as orientações em [verificar o seu domínio do Microsoft 365 para provar a propriedade, o status de educação ou não de lucro, ou para ativar o Yammer](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) para garantir que todas as etapas necessárias foram concluídas. É um pouco diferente para cada situação. 
  
## <a name="services-not-working-with-your-domain"></a>Os serviços não estão funcionando com o seu domínio?
<a name="BKMK_Test"> </a>

Podemos ajudá-lo a corrigir problemas com a configuração de DNS do seu domínio. A solução de problemas de domínios no Microsoft 365 mostrará todos os registros que precisam de correção e exatamente o que os registros precisam ser definidos. 

> [!TIP]
> O DNS foi configurado corretamente, mas o email não funciona no Outlook na sua área de trabalho? Confira os [diferentes cenários de fluxo de mensagens que você pode ter com o Microsoft 365](https://www.microsoft.com/?ref=go) para garantir que você tenha as coisas configuradas corretamente para sua empresa. Se preferir, obtenha mais soluções de problemas com email aqui: [Corrigir problemas do Outlook](https://docs.microsoft.com/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues). 
  
## <a name="accessing-your-website-isnt-working"></a>Não consegue acessar o seu site?
<a name="BKMK_Website"> </a>

Caso tenha corrigido os problemas de DNS, mas ainda esteja com dificuldades, tente um dos seguintes procedimentos.
  
- As pessoas não conseguem acessar seu site em www.mydomain.com: [Rastrear problemas do site](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)
    
- Você não pode atualizar seu registro A ou CNAME para apontar para seu site: [atualizar registros DNS personalizados no Microsoft 365](../dns/add-or-edit-custom-dns-records.md)
    
