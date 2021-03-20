---
title: Adicionar um domínio ao Microsoft 365
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
description: Adicione seu domínio ao Microsoft 365 no Centro de administração do Microsoft 365 adicionando um registro DNS ao host DNS. O assistente de instalação orienta você durante o processo.
ms.openlocfilehash: 30bce7dd207532c441fdfaf572add44baec16d8d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914265"
---
# <a name="add-a-domain-to-microsoft-365"></a>Adicionar um domínio ao Microsoft 365

::: moniker range="o365-21vianet"

> [!NOTE]
> O centro de administração está mudando. Se a sua experiência não corresponder aos detalhes apresentados aqui, consulte [Sobre o novo centro de administração do Microsoft 365](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).

::: moniker-end

 Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](domains-faq.yml)**. 
  
 *Para adicionar, modificar ou remover domínios, você **deve** ser um **Administrador Global** de um [plano empresarial ou corporativo.](https://products.office.com/business/office) Essas alterações afetam todo o locatário, administradores *personalizados* ou *usuários regulares* não poderão fazer essas alterações.*  

 Siga estas etapas para adicionar, configurar ou continuar configurando um domínio. 

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
    
2. Vá para a **página Configurações**  >  **Domínios.** 

3. Selecione **Adicionar domínio**.
    
4. Insira o nome do domínio que você deseja adicionar e selecione **Próximo**.
    
5. Escolha como deseja verificar se você é o próprio domínio.
    
    1. Se o registrador de domínio usar [o Domain Connect,](#domain-connect-registrars-integrating-with-microsoft-365)a [Microsoft](../get-help-with-domains/domain-connect.md) configurará seus registros automaticamente fazendo você entrar no registrador e confirmar a conexão com o Microsoft 365. Você será retornado ao centro de administração e a Microsoft verificará automaticamente seu domínio.
    2. Use um registro TXT para verificar seu domínio. Selecione isso e selecione **Próximo** para ver instruções sobre como adicionar esse registro DNS ao site do registrador. Isso pode levar até 30 minutos para verificar depois que você adicionou o registro. 
    3. Você pode adicionar um arquivo de texto ao site do seu domínio. Selecione e baixe o arquivo .txt do assistente de instalação e carregue o arquivo na pasta de nível superior do seu site. O caminho para o arquivo deve ser semelhante a: `http://mydomain.com/ms39978200.txt` . Confirmaremos se você é o dono do domínio encontrando o arquivo em seu site.
    
6. Escolha como você deseja fazer as alterações dns necessárias para que a Microsoft use seu domínio.
    
    1. Escolha **Adicionar os registros DNS** para mim se o registrador for compatível com o Domain [Connect](#domain-connect-registrars-integrating-with-microsoft-365)e a [Microsoft](../get-help-with-domains/domain-connect.md) configurará seus registros automaticamente, fazendo com que você entre no registrador e confirme a conexão com o Microsoft 365.
    2. Escolha **Eu mesmo adicionarei** os registros DNS se você quiser anexar apenas serviços específicos do Microsoft 365 ao seu domínio ou se quiser ignorar isso por enquanto e fazer isso posteriormente. **Escolha essa opção se você souber exatamente o que está fazendo:**

7. Se você optar por adicionar registros *DNS*  por conta própria, selecione **Próximo** e verá uma página com todos os registros necessários para adicionar ao seu site de registradores para configurar seu domínio. 

    Se o portal não reconhecer seu registrador, [siga estas instruções gerais.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)
    
    Confira a nossa lista de [instruções específicas de host](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) para encontrar seu host e siga as etapas para adicionar todos os registros necessários. 
    
    Se você não conhece o provedor de host DNS ou o registrador de domínios para seu domínio, confira [Localizar seu registrador de domínio ou provedor de host DNS](../get-help-with-domains/find-your-domain-registrar.md).
    
    Se você quiser aguardar mais tarde, desmarque todos os serviços e clique em **Continuar** ou na etapa anterior de conexão de domínio escolha **Mais** Opções e selecione **Ignorar isso por enquanto**.
    
8. Selecione **Concluir** - você terminou!

## <a name="add-or-edit-custom-dns-records"></a>Adicionar ou editar registros DNS personalizados

Siga as etapas abaixo para adicionar um registro personalizado para um site ou serviço de terceiros.

1. Entre no centro de administração da Microsoft em <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .

2. Vá para a **página Configurações**   >  **Domínios.**

3. Selecione um domínio na página **Domínios**. 
    
4. Em **configurações DNS,** selecione Registros **Personalizados;** em seguida, **selecione Novo registro personalizado**.

5. Selecione o tipo de registro DNS que você deseja adicionar e digite as informações do novo registro.
    
6. Selecione **Salvar**.

## <a name="registrars-with-domain-connect"></a>Registradores com Conexão de Domínio

[Registradores habilitados](https://www.domainconnect.org/) para Conexão de Domínio permitem adicionar seu domínio ao Microsoft 365 em um processo de três etapas que leva minutos. 
  
No assistente, apenas confirmaremos se você é o próprio domínio e configurará automaticamente os registros do seu domínio, para que o email venha para o Microsoft 365 e outros serviços do Microsoft 365, como o Teams, trabalhar com seu domínio.
  
> [!NOTE]
> Desative os bloqueadores de pop-up em seu navegador antes de iniciar o assistente de configuração.
  
### <a name="domain-connect-registrars-integrating-with-microsoft-365"></a>Registradores de Conexão de Domínio integrando-se com o Microsoft 365

- [1 &amp; 1 IONOS](https://www.1and1.com/)
- [EuroDNS](https://www.eurodns.com/)
- [Cloudflare](https://www.cloudflare.com/)
- [GoDaddy](https://www.godaddy.com/)
- [WordPress.com](https://wordpress.com/)
- [Plesk](https://www.plesk.com/)
- [MediaTemple](https://mediatemple.net/)
- SecureServer ou WildWestDomains (revendedores godaddy usando hospedagem DNS do SecureServer)
    - Exemplos:
        - [DomainsPricedRight](https://www.domainspricedright.com/products/domain-registration)
        - [DomainRightNow](https://www.domainrightnow.com/)

### <a name="what-happens-to-my-email-and-website"></a>O que acontece com meu email e site?

Depois de concluir a instalação, o registro MX do seu domínio é atualizado para apontar para o Microsoft 365 e todos os emails para seu domínio começarão a chegar ao Microsoft 365. Certifique-se de adicionar usuários e configurar caixas de correio no Microsoft 365 para todos que receberem emails em seu domínio!
  
Se você tiver um site que usa com a empresa, ele continuará funcionando onde está. As etapas de configuração do Domain Connect não afetam seu site.

## <a name="related-articles"></a>Artigos relacionados

[Perguntas frequentes sobre domínios](domains-faq.yml)

[O que é um domínio?](../get-help-with-domains/what-is-a-domain.md)

[Comprar um nome de domínio no Microsoft 365](../get-help-with-domains/buy-a-domain-name.md)

[Configurar seu domínio (instruções específicas do host)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)