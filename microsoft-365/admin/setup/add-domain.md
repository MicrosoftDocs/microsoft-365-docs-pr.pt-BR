---
title: Adicionar um domínio ao Office 365
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 6383f56d-3d09-4dcb-9b41-b5f5a5efd611
description: Adicione seu domínio ao Office 365 no centro de administração do Microsoft 365 adicionando um registro DNS no seu host DNS. O assistente de instalação orienta você durante o processo.
ms.openlocfilehash: 336e6ee78d7020d73c7e00f639e8f1e1b20c62cd
ms.sourcegitcommit: 98782ee4497d72232462c51a3071fae313282980
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44222334"
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
    
2. Vá para a página **Configurar**  >  **domínios** . 

3. Selecione **Adicionar domínio**.
    
4. Insira o nome do domínio que você deseja adicionar e, em seguida, selecione **Avançar**.
    
5. Escolha como deseja verificar se você é o proprietário do domínio.
    
    1. Se seu domínio estiver registrado em GoDaddy ou 1 &amp; 1, selecione **entrar em**  >  **seguida** e [a Microsoft configurará seus registros automaticamente](../get-help-with-domains/domain-connect.md).
    
    2. É possível enviar um email para o contato registrado do domínio com um código de verificação. Se você não reconhece ou tem acesso ao email no registro, você pode usar a terceira opção.
    
    3. Use um registro TXT para verificar seu domínio. Selecione-o e selecione **Avançar** para ver instruções sobre como adicionar esse registro DNS ao site do registrador. Isso pode levar até 30 minutos para verificar após você ter adicionado o registro. 
    
6. Escolha como você deseja fazer as alterações de DNS necessárias para o Office usar seu domínio.
    
    1. Escolha **adicionar os registros DNS para mim** se quiser que o Office configure o DNS automaticamente. 
    
  
    2. Escolha **eu mesmo adicionará os registros DNS** se você quiser anexar apenas serviços específicos do Office 365 ao seu domínio ou se quiser ignorar isso por enquanto e fazer isso mais tarde. **Escolha essa opção se você souber exatamente o que está fazendo:**
    
7. Se você optar por *adicionar registros DNS por conta própria* , selecione **Avançar** e verá uma página com todos os registros que você precisa adicionar ao site de registradores para configurar seu domínio. 
    
  
  
    Se o portal não reconhecer seu registrador, [siga estas instruções gerais.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)
    
    Confira a nossa lista de [instruções específicas de host](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions) para encontrar seu host e siga as etapas para adicionar todos os registros necessários. 
    
    Se você não conhece o provedor de host DNS ou o registrador de domínios para seu domínio, confira [Localizar seu registrador de domínio ou provedor de host DNS](../get-help-with-domains/find-your-domain-registrar.md).
    
    Se você quiser aguardar mais tarde, role até o final e selecione **ignorar esta etapa**.
    
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
- [123Reg](https://www.123-reg.co.uk/)
- [GoDaddy](https://www.godaddy.com/)
- [WordPress](https://wordpress.com/)
- [Plesk](https://www.plesk.com/)
- [MediaTemple](https://mediatemple.net/)
- SecureServer ou WildWestDomains (GoDaddy revendedores usando o SecureServer de Hospedagem de DNS)
    - [Domínios MadDog](https://www.maddogdomains.com/)
    - [Baratosnames](https://www.cheapnames.com)

### <a name="what-happens-to-my-email-and-website"></a>O que acontece com meus emails e sites?

Depois que você concluir a instalação, o registro MX do seu domínio será atualizado para apontar para o Microsoft 365 e todos os emails do seu domínio serão iniciados no Microsoft 365. Verifique se você adicionou usuários e configurou caixas de correio no Office 365 para todos aqueles que recebem emails em seu domínio!
  
Se você tiver um site que usa com a empresa, ele continuará funcionando onde está. As etapas de configuração de conexão de domínio não afetam o site.

## <a name="related-articles"></a>Artigos relacionados

[Perguntas frequentes sobre domínios](domains-faq.md)

[O que é um domínio?](../get-help-with-domains/what-is-a-domain.md)

[Comprar um nome de domínio no Office 365](../get-help-with-domains/buy-a-domain-name.md)

[Configurar seu domínio (instruções específicas do host)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)

[Obter ajuda com domínios](../get-help-with-domains/get-help-with-domains.md)
