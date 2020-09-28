---
title: Adicionar um domínio ao Microsoft 365
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
- Adm_O365_Setup
- Adm_O365
- Adm_TOC
ms.custom:
- TopSMBIssues
- SaRA
- MSStore_Link
- okr_smb
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 6383f56d-3d09-4dcb-9b41-b5f5a5efd611
description: Adicione seu domínio ao Microsoft 365 no centro de administração do Microsoft 365 adicionando um registro DNS no seu host DNS. O assistente de instalação orienta você durante o processo.
ms.openlocfilehash: 09a66b9ac4f97a076d71dd7f259678181378ae48
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295017"
---
# <a name="add-a-domain-to-microsoft-365"></a>Adicionar um domínio ao Microsoft 365

::: moniker range="o365-21vianet"

> [!NOTE]
> O centro de administração está mudando. Se a sua experiência não corresponder aos detalhes apresentados aqui, consulte [Sobre o novo centro de administração do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

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
    
2. Vá para a página de domínios de **configurações**  >  **Domains** . 

3. Selecione **Adicionar domínio**.
    
4. Insira o nome do domínio que você deseja adicionar e, em seguida, selecione **Avançar**.
    
5. Escolha como deseja verificar se você é o proprietário do domínio.
    
    1. Se o seu registrador de domínio usar a [conexão de domínio](#domain-connect-registrars-integrating-with-microsoft-365), [a Microsoft configurará seus registros automaticamente](../get-help-with-domains/domain-connect.md) , fazendo você entrar em seu registrador e confirmar a conexão com o Microsoft 365. Você retornará ao centro de administração e a Microsoft verificará automaticamente o seu domínio.
    2. Use um registro TXT para verificar seu domínio. Selecione-o e selecione **Avançar** para ver instruções sobre como adicionar esse registro DNS ao site do registrador. Isso pode levar até 30 minutos para verificar após você ter adicionado o registro. 
    3. Você pode adicionar um arquivo de texto ao site do seu domínio. Selecione e baixe o arquivo. txt do assistente de instalação e, em seguida, carregue o arquivo para a pasta de nível superior do seu site. O caminho para o arquivo deve ser semelhante a: `http://mydomain.com/ms39978200.txt` . Vamos confirmar que você é o proprietário do domínio encontrando o arquivo no seu site.
    
6. Escolha como você deseja fazer as alterações de DNS necessárias para que a Microsoft use seu domínio.
    
    1. Escolha **adicionar os registros DNS para mim** se o seu registrador oferecer suporte à [conexão de domínio](#domain-connect-registrars-integrating-with-microsoft-365)e a Microsoft [configurar seus registros automaticamente](../get-help-with-domains/domain-connect.md) , fazendo você entrar em seu registrador e confirmar a conexão com o Microsoft 365.
    2. Escolha **eu mesmo adicionarei os registros DNS** se você quiser anexar apenas serviços específicos da Microsoft 365 ao seu domínio ou se quiser ignorar isso por enquanto e fazer isso mais tarde. **Escolha essa opção se você souber exatamente o que está fazendo:**

7. Se você optar por *adicionar registros DNS por conta própria*  , selecione **Avançar** e verá uma página com todos os registros que você precisa adicionar ao site de registradores para configurar seu domínio. 

    Se o portal não reconhecer seu registrador, [siga estas instruções gerais.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)
    
    Confira a nossa lista de [instruções específicas de host](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions) para encontrar seu host e siga as etapas para adicionar todos os registros necessários. 
    
    Se você não conhece o provedor de host DNS ou o registrador de domínios para seu domínio, confira [Localizar seu registrador de domínio ou provedor de host DNS](../get-help-with-domains/find-your-domain-registrar.md).
    
    Se você quiser aguardar mais tarde, desmarque todos os serviços e clique em **continuar**, ou na etapa de conexão de domínio anterior, escolha **mais opções** e selecione **ignorar isso por enquanto**.
    
8. Selecione **concluir** -você terminou!

## <a name="add-or-edit-custom-dns-records"></a>Adicionar ou editar registros DNS personalizados

Siga as etapas abaixo para adicionar um registro personalizado para um site ou serviço de terceiros.

1. Entre no centro de administração da Microsoft em <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .

2. Vá para a página de domínios de **configurações**   >  **Domains** .

3. Selecione um domínio na página **Domínios**. 
    
4. Em **configurações de DNS**, selecione **registros personalizados**; em seguida, selecione **novo registro personalizado**.

5. Selecione o tipo de registro DNS que você deseja adicionar e digite as informações do novo registro.
    
6. Selecione **Salvar**.

## <a name="registrars-with-domain-connect"></a>Registradores com conexão de domínio

Os registradores habilitados para [conexão de domínio](https://www.domainconnect.org/) permitem que você adicione seu domínio ao Microsoft 365 em um processo de três etapas que leva minutos. 
  
No assistente, apenas confirmará que você é o proprietário do domínio e, em seguida, configurar automaticamente os registros do seu domínio, para que os emails sejam da Microsoft 365 e de outros serviços da Microsoft 365, como o Teams, trabalhem com seu domínio.
  
> [!NOTE]
> Desative os bloqueadores de pop-up em seu navegador antes de iniciar o assistente de configuração.
  
### <a name="domain-connect-registrars-integrating-with-microsoft-365"></a>Registradores de conexão de domínio que se integram ao Microsoft 365

- [1 &amp; 1 IONOS](https://www.1and1.com/)
- [EuroDNS](https://www.eurodns.com/)
- [Cloudflare](https://www.cloudflare.com/)
- [GoDaddy](https://www.godaddy.com/)
- [WordPress.com](https://wordpress.com/)
- [Plesk](https://www.plesk.com/)
- [MediaTemple](https://mediatemple.net/)
- SecureServer ou WildWestDomains (GoDaddy revendedores usando o SecureServer de Hospedagem de DNS)
    - Exemplos:
        - [DomainsPricedRight](https://www.domainspricedright.com/products/domain-registration)
        - [DomainRightNow](https://www.domainrightnow.com/)

### <a name="what-happens-to-my-email-and-website"></a>O que acontece com meus emails e sites?

Depois que você concluir a instalação, o registro MX do seu domínio será atualizado para apontar para o Microsoft 365 e todos os emails do seu domínio serão iniciados no Microsoft 365. Verifique se você adicionou usuários e configurou caixas de correio no Microsoft 365 para todas as pessoas que recebem emails no seu domínio!
  
Se você tiver um site que usa com a empresa, ele continuará funcionando onde está. As etapas de configuração de conexão de domínio não afetam o site.

## <a name="related-articles"></a>Artigos relacionados

[Perguntas frequentes sobre domínios](domains-faq.md)

[O que é um domínio?](../get-help-with-domains/what-is-a-domain.md)

[Comprar um nome de domínio no Microsoft 365](../get-help-with-domains/buy-a-domain-name.md)

[Configurar seu domínio (instruções específicas do host)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)
