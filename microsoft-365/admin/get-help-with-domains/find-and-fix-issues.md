---
title: Localizar e corrigir problemas após a adição do seu domínio ou de registros DNS
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
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 40398b0b-bdd0-4afd-ab5e-b5ae6b7990bf
description: Saiba como rastrear todos os problemas que você encontrar durante a configuração de um domínio personalizado, certifique-se de que os registros DNS estão definidos corretamente.
ms.openlocfilehash: 70beb877251c333766a0963316287796eb81d595
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52623960"
---
# <a name="find-and-fix-issues-after-adding-your-domain-or-dns-records"></a>Localizar e corrigir problemas após a adição do seu domínio ou de registros DNS

 Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.yml)**. 
  
A configuração do domínio para trabalhar com Microsoft 365 pode ser um desafio. É complicado trabalhar com o sistema DNS, e a configuração DNS do seu domínio afeta atividades comerciais importantes, como o email!

> [!NOTE]
> Você pode verificar se há problemas com seu domínio verificando seu status. Vá até **Setup**  >  **Domains** e veja as notificações na **coluna Status.** Se você vir um problema, selecione os três pontos (mais ações) e escolha **Verificar a saúde**. O painel aberto descreverá todos os problemas que ocorrem com seu domínio.
  
## <a name="whats-going-on"></a>O que está acontecendo?

- [Não é possível verificar seu domínio?](#cant-verify-your-domain)
    
- [Outlook não está funcionando?](#outlook-isnt-working)
    
- [O email de todos foi alternado para Microsoft 365 e você só queria que seu email alternando?](#everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch)

- [Não é possível confirmar o status da conta escolar ou sem fins lucrativos?](#cant-confirm-non-profit-or-school-account-status)

- [Serviços que não estão funcionando com seu domínio?](#services-not-working-with-your-domain)
    
- [Acessar seu site não está funcionando?](#accessing-your-website-isnt-working)

## <a name="cant-verify-your-domain"></a>Não consegue verificar o seu domínio?
<a name="BKMK_verify"> </a>

Há alguns motivos comuns para a verificação de domínios não funcionar como deveria:
  
1. **O valor de registro da verificação não está correto.** Verifique se você copiou e colou o valor exato no registro de verificação TXT no seu host DNS. Um problema comum é não incluir a parte "MS=" no registro. Precisamos disso também! 
    
2. **O registro não foi salvo.** Em alguns hosts DNS, você pode ter que executar uma etapa extra para salvar o arquivo de zona (local em que o registro DNS é armazenado) para que o registro seja atualizado na Internet. Verifique se você salvou suas alterações para que Microsoft 365 possa ver e verificar o registro. 
    
3. **O registro não foi atualizado na Internet.** Normalmente, leva apenas alguns minutos para que possamos ver o novo registro, mas, ocasionalmente, pode levar até algumas horas. 
    
## <a name="outlook-isnt-working"></a>O Outlook não está funcionando?
<a name="BKMK_OutlookBroken"> </a>

Se você configurou o registro MX e os outros registros DNS corretamente para o seu domínio, mas o seu email não funciona, deixe-nos ajudá-lo a [corrigir os problemas do Outlook](/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues).
  
## <a name="everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch"></a>O email de todos foi alternado para Microsoft 365 e você só queria que seu email alternando?
<a name="BKMK_EmailSwitched"> </a>

Quando você adiciona seu domínio ao Microsoft 365, normalmente o registro MX do seu domínio é atualizado (por você ou Microsoft 365) para apontar para Microsoft 365, e TODOS os emails enviados para esse domínio começarão Microsoft 365. Certifique-se de ter criado caixas de correio no Microsoft 365 para todos que têm email em seu domínio ANTES de alterar o registro MX.
  
E se você não quiser mover emails para todos em seu domínio para Microsoft 365? Você pode tomar medidas para [Microsoft 365 com apenas alguns endereços de email.](../setup/domains-faq.yml)
  
## <a name="cant-confirm-non-profit-or-school-account-status"></a>Não é possível confirmar o status da conta escolar ou sem fins lucrativos?
<a name="BKMK_validateAcct"> </a>

Há alguns cenários quando você só precisa verificar o domínio da sua organização e não configurar nenhum serviço. Por exemplo, para provar Microsoft 365 sua organização se qualifica para uma assinatura escolar.
  
Confira as diretrizes em Verificar seu domínio Microsoft 365 para provar a [propriedade,](../setup/domains-faq.yml) a entidade sem fins lucrativos ou o status de educação ou Yammer ativar o Yammer para garantir que você tenha concluído todas as etapas necessárias. É um pouco diferente para cada situação. 
  
## <a name="services-not-working-with-your-domain"></a>Os serviços não estão funcionando com o seu domínio?
<a name="BKMK_Test"> </a>

Podemos ajudá-lo a corrigir problemas com a configuração de DNS do seu domínio. O solucionador de problemas de domínios Microsoft 365 mostrará todos os registros que precisem de correção e exatamente o que os registros precisam ser definidos. 

> [!TIP]
> O DNS foi configurado corretamente, mas o email não funciona no Outlook na sua área de trabalho? Confira os [diferentes cenários de](/exchange/mail-flow-best-practices/mail-flow-best-practices) fluxo de emails que você pode ter com Microsoft 365 para garantir que você tenha as coisas configuradas corretamente para sua empresa. Se preferir, obtenha mais soluções de problemas com email aqui: [Corrigir problemas do Outlook](/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues). 
  
## <a name="accessing-your-website-isnt-working"></a>Não consegue acessar o seu site?
<a name="BKMK_Website"> </a>

Caso tenha corrigido os problemas de DNS, mas ainda esteja com dificuldades, tente um dos seguintes procedimentos.
  
- As pessoas não conseguem acessar seu site em www.mydomain.com: [Rastrear problemas do site](../setup/add-domain.md)
    
- Você não pode atualizar seu registro A ou CNAME para apontar para seu site: Atualizar registros [DNS personalizados em Microsoft 365](../setup/add-domain.md)

## <a name="related-content"></a>Conteúdo relacionado

[Solução de problemas: Auditar dados em alteração de domínio verificada](/azure/active-directory/reports-monitoring/troubleshoot-audit-data-verified-domain) (artigo)\
[Perguntas frequentes sobre domínios](../setup/domains-faq.yml) (artigo)

