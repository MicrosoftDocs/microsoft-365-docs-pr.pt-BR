---
title: Adicionar um domínio ao Office 365
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365_Setup
- Adm_O365
- Adm_TOC
ms.custom:
- TopSMBIssues
- SaRA
- MSStore_Link
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 6383f56d-3d09-4dcb-9b41-b5f5a5efd611
description: Adicione seu domínio ao Office 365 no centro de administração do Microsoft 365 adicionando um registro DNS no seu host DNS. O assistente de instalação orienta você durante o processo.
ms.openlocfilehash: 4170fd74ae734a6fda9e535c17086997b1db6f6b
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42237809"
---
# <a name="add-a-domain-to-office-365"></a>Adicionar um domínio ao Office 365

 Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](domains-faq.md)**. 
  
 *Para adicionar, modificar ou remover domínios, você **deve** ser um **administrador global** de um [plano comercial ou empresarial](https://products.office.com/business/office). Essas alterações afetam todo o locatário, *os administradores personalizados* ou *os usuários regulares* não poderão fazer essas alterações.*  

 Siga estas etapas para adicionar, configurar ou continuar a configurar um domínio. 

::: moniker range="o365-worldwide"
  
::: moniker-end

::: moniker range="o365-germany"

> [!VIDEO https://www.microsoft.com/videoplayer/embed/dda6df6d-37b0-41ff-905b-089448355a31?autoplay=false]
  
::: moniker-end

::: moniker range="o365-worldwide"

1. Vá para o centro de administração do<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.

::: moniker-end
::: moniker range="o365-germany"

1. Vá para o centro de administração do<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. Vá para o centro de administração do<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.

::: moniker-end
    
2. Vá para a página de**domínios** de **configurações** > . 

3. Selecione **Adicionar domínio**.
    
4. Insira o nome do domínio que você deseja adicionar e, em seguida, selecione **Avançar**.
    
5. Escolha como deseja verificar se você é o proprietário do domínio.
    
    1. Se seu domínio estiver registrado no GoDaddy ou 1&amp;1, selecione **entrar em** > **Avançar** e o Office 365 [configurará os registros automaticamente](../get-help-with-domains/domain-connect.md).
    
    2. É possível enviar um email para o contato registrado do domínio com um código de verificação. Se você não reconhece ou tem acesso ao email no registro, você pode usar a terceira opção.
    
    3. Use um registro TXT para verificar seu domínio. Selecione-o e selecione **Avançar** para ver instruções sobre como adicionar esse registro DNS ao site do registrador. Isso pode levar até 30 minutos para verificar após você ter adicionado o registro. 
    
6. Escolha como você deseja fazer as alterações de DNS necessárias para o Office usar seu domínio.
    
    1. Escolha **adicionar os registros DNS para mim** se quiser que o Office configure o DNS automaticamente. 
    
  
    2. Escolha **eu mesmo adicionará os registros DNS** se você quiser anexar apenas serviços específicos do Office 365 ao seu domínio ou se quiser ignorar isso por enquanto e fazer isso mais tarde. **Escolha essa opção se você souber exatamente o que está fazendo:**
    
7. Se você optar por *adicionar registros DNS por conta própria* , selecione **Avançar** e verá uma página com todos os registros que você precisa adicionar ao site de registradores para configurar seu domínio. 
    
  
  
    Se o portal não reconhecer seu registrador, [siga estas instruções gerais.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)
    
    Confira a nossa lista de [instruções específicas de host](https://support.office.com/article/ae950c9e-e8d9-4108-b0cb-449156998580) para encontrar seu host e siga as etapas para adicionar todos os registros necessários. 
    
    Se você não conhece o provedor de host DNS ou o registrador de domínios para seu domínio, confira [Localizar seu registrador de domínio ou provedor de host DNS](../get-help-with-domains/find-your-domain-registrar.md).
    
    Se você quiser aguardar mais tarde, role até o final e selecione **ignorar esta etapa**.
    
8. Selecione **concluir** -você terminou! 

## <a name="related-articles"></a>Artigos relacionados

[Perguntas frequentes sobre domínios](domains-faq.md)

[O que é um domínio?](../get-help-with-domains/what-is-a-domain.md)

[Comprar um nome de domínio no Office 365](../get-help-with-domains/buy-a-domain-name.md)

[Configurar seu domínio (instruções específicas do host)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)

[Obter ajuda com os domínios do Office 365](../get-help-with-domains/get-help-with-domains.md)
