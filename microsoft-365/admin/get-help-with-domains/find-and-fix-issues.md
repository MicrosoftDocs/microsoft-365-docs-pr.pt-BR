---
title: Localizar e corrigir problemas após adicionar seu domínio ou registros DNS no Office 365
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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 40398b0b-bdd0-4afd-ab5e-b5ae6b7990bf
description: Saiba mais sobre os problemas que você tem ao configurar um domínio personalizado certificando-se de que os registros DNS estão configurados corretamente.
ms.openlocfilehash: 00330dea6b3401bce02779437dc047ce324dcece
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/09/2020
ms.locfileid: "43210399"
---
# <a name="find-and-fix-issues-after-adding-your-domain-or-dns-records-in-office-365"></a>Localizar e corrigir problemas após adicionar seu domínio ou registros DNS no Office 365

 Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**. 
  
Fazer com que o seu domínio funcione no Office 365 pode ser desafiador. É complicado trabalhar com o sistema DNS, e a configuração DNS do seu domínio afeta atividades comerciais importantes, como o email!

> [!NOTE]
> Você pode verificar se há problemas com seu domínio verificando seu status. Vá para **Configurar** > **domínios** e exibir as notificações na coluna **status** . Se você vir um problema, selecione mais ações (três pontos) e escolha **verificar integridade**. O painel que será aberto descreverá todos os problemas que ocorrem com o seu domínio.
  
## <a name="whats-going-on"></a>O que está acontecendo?

- [Não é possível verificar seu domínio?](#cant-verify-your-domain)
    
- [O Outlook não está funcionando?](#outlook-isnt-working)
    
- [OS emails de todos os usuários mudaram para o Office 365 e você queria que seu email fosse alterado?](#everyones-email-got-switched-to-office-365-and-you-only-wanted-your-email-to-switch)

- [Não consegue confirmar o status de conta de estudante ou sem fins lucrativos?](#cant-confirm-non-profit-or-school-account-status)

- [Os serviços não estão funcionando com seu domínio?](#services-not-working-with-your-domain)
    
- [O acesso ao seu site não está funcionando?](#accessing-your-website-isnt-working)

## <a name="cant-verify-your-domain"></a>Não consegue verificar o seu domínio?
<a name="BKMK_verify"> </a>

Há alguns motivos comuns para a verificação de domínios não funcionar como deveria:
  
1. **O valor de registro da verificação não está correto.** Verifique se você copiou e colou o valor exato no registro de verificação TXT no seu host DNS. Um problema comum é não incluir a parte "MS=" no registro. Precisamos disso também! 
    
2. **O registro não foi salvo.** Em alguns hosts DNS, você pode ter que executar uma etapa extra para salvar o arquivo de zona (local em que o registro DNS é armazenado) para que o registro seja atualizado na Internet. Certifique-se de salvar as alterações para o Office 365 poder ver e verificar o registro. 
    
3. **O registro não foi atualizado na Internet.** Normalmente, apenas alguns minutos levam alguns minutos para que possamos ver o novo registro, mas, ocasionalmente, pode levar algumas horas. 
    
## <a name="outlook-isnt-working"></a>O Outlook não está funcionando?
<a name="BKMK_OutlookBroken"> </a>

Se você configurou o registro MX e os outros registros DNS corretamente para o seu domínio, mas o seu email não funciona, deixe-nos ajudá-lo a [corrigir os problemas do Outlook](https://support.office.com/article/b3e740b9-171d-4179-bcd1-e279a363fa75.aspx).
  
## <a name="everyones-email-got-switched-to-office-365-and-you-only-wanted-your-email-to-switch"></a>OS emails de todos os usuários mudaram para o Office 365 e você queria que seu email fosse alterado?
<a name="BKMK_EmailSwitched"> </a>

Quando você adiciona seu domínio ao Office 365, normalmente o registro MX do seu domínio é atualizado (por você ou pelo Office 365) para apontar para o Office 365, e todos os emails enviados para esse domínio começarão a ser iniciados no Office 365. Certifique-se de ter criado caixas de correio no Office 365 para todas as pessoas que tenham emails em seu domínio antes de alterar o registro MX.
  
E se você não quiser mover emails para todas as pessoas em seu domínio para o Office 365? Você pode executar etapas para [coordenar o Office 365 com apenas alguns endereços de email](https://support.office.com/article/39cee536-6a03-40cf-b9c1-f301bb6001d7.aspx).
  
## <a name="cant-confirm-non-profit-or-school-account-status"></a>Não consegue confirmar o status de conta de estudante ou sem fins lucrativos?
<a name="BKMK_validateAcct"> </a>

Há alguns cenários em que você só precisa verificar o domínio da sua organização e não configurar nenhum serviço. Por exemplo, para provar ao Office 365 que sua organização é qualificada para uma assinatura escolar.
  
Confira as orientações em [verificar o domínio do Office 365 para provar a propriedade, o status de educação ou não de lucro, ou para ativar o Yammer](https://support.office.com/article/87d1844e-aa47-4dc0-a61b-1b773fd4e590) para garantir que todas as etapas necessárias foram concluídas. É um pouco diferente para cada situação. 
  
## <a name="services-not-working-with-your-domain"></a>Os serviços não estão funcionando com o seu domínio?
<a name="BKMK_Test"> </a>

Podemos ajudá-lo a corrigir problemas com a configuração de DNS do seu domínio. A solução de problemas de domínios no Office 365 mostrará todos os registros que precisam de correção e a forma exata como eles devem ser configurados. 

> [!TIP]
> O DNS foi configurado corretamente, mas o email não funciona no Outlook na sua área de trabalho? Confira os [diversos cenários de fluxo de email do Office 365](https://go.microsoft.com/fwlink/?LinkId=787530) para garantir que você configurou todos os recursos de maneira adequada para sua empresa. Se preferir, obtenha mais soluções de problemas com email aqui: [Corrigir problemas do Outlook](https://support.office.com/article/b3e740b9-171d-4179-bcd1-e279a363fa75.aspx). 
  
## <a name="accessing-your-website-isnt-working"></a>Não consegue acessar o seu site?
<a name="BKMK_Website"> </a>

Caso tenha corrigido os problemas de DNS, mas ainda esteja com dificuldades, tente um dos seguintes procedimentos.
  
- As pessoas não conseguem acessar seu site em www.mydomain.com: [Rastrear problemas do site](https://support.office.com/article/61f34ca1-ca7f-4a65-9348-def20db09ddf.aspx)
    
- Não é possível atualizar o registro A ou o registro CNAME para apontar para seu site: [Atualizar registros DNS personalizados no Office 365](../dns/add-or-edit-custom-dns-records.md)
    
