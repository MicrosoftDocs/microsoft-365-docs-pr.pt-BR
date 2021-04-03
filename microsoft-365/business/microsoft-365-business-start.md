---
title: Começar com o Microsoft 365 para empresas
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- TRN_SMB
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- TRN_M365B
- OKR_SMB_Videos
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 496e690b-b75d-4ff5-bf34-cc32905d0364
description: Saiba mais sobre o Microsoft 365 para empresas, como defini-lo e como preparar os dispositivos e os PCs dos usuários para garantir que eles estão protegidos pelo Microsoft 365 para empresas.
ms.openlocfilehash: 83bd2ff87683c1ad810d20658ba20f3229408968
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580085"
---
# <a name="get-started-with-microsoft-365-for-business"></a>Começar com o Microsoft 365 para empresas

## <a name="what-is-microsoft-365-for-business"></a>O que é o Microsoft 365 para empresas

O Microsoft 365 para empresas é um conjunto abrangente de ferramentas de produtividade e colaboração de negócios, como Outlook, Word, Excel e outros produtos do Office, que estão sempre atualizados. Você pode proteger seus arquivos de trabalho em todos os dispositivos iOS, Android e Windows 10 com segurança de nível empresarial simples de gerenciar.

Assista a este vídeo para uma visão geral rápida do Microsoft 365 para empresas.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2mhaA] 
  
O Microsoft 365 para empresas é destinado a até 300 licenças. Se precisar de mais licenças, confira a documentação do[Microsoft 365 Enterprise ](../enterprise/index.yml) para saber mais. 
  
## <a name="get-microsoft-365-for-business"></a>Obter o Microsoft 365 para empresas

- Se você tiver um parceiro, ele obterá o Microsoft 365 para empresas: [Obter o Microsoft 365 para](get-microsoft-365-business.md)empresas a partir do Microsoft Partner Center .
    
- Se você não tiver um parceiro e quiser obter o Microsoft 365 para empresas, poderá [comprá-lo aqui](https://www.microsoft.com/microsoft-365/business).
    
## <a name="set-up-microsoft-365-for-business"></a>Configurar o Microsoft 365 para empresas

 **Visão geral da configuração do Microsoft 365 for business Suite**
  
O diagrama a seguir descreve como os administradores configuram o Microsoft 365 para empresas. Ele também descreve as etapas para preparar computadores Windows para o Microsoft 365 para empresas. Você também pode adicionar novos dispositivos no Centro de administração do Microsoft 365 com [o Windows AutoPilot](add-autopilot-devices-and-profile.md). Você pode usar o AutoPilot para configurar e pré-configurar novos dispositivos para que eles estão prontos para uso produtivo assim que um usuário entrar com suas credenciais do Microsoft 365 para empresas.
  
![A diagram that shows the setup and management flow for admins, and also for a user](../media/249f81fc-7e79-44c7-8425-3a0b7b651c3b.png)

Assista a este vídeo para ver uma visão geral da configuração do Microsoft 365 para empresas.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSM] 

Se você achou este vídeo útil, consulte as [séries completas de treinamento para pequenas empresas e as novidades para o Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

  
### <a name="1-set-up-microsoft-365-for-business-admin"></a>1: Configurar o Microsoft 365 para empresas (Administrador)

Entre no Centro de administração do [Microsoft 365](https://portal.office.com/adminportal/home) com suas credenciais de administrador global e conclua as etapas a seguir para configurar o Microsoft 365 para empresas. 
  
1. [Pré-requisitos para proteger dados em dispositivos com o Microsoft 365 para empresas](pre-requisites-for-data-protection.md)
    
    Leia os pré-requisitos primeiro para garantir que seus dispositivos estão prontos para o Microsoft 365 para empresas.
    
2. [Usar o assistente de instalação para configurar o Microsoft 365 para empresas](set-up.md)
    
    Se você estiver mudando permanentemente de um **Active Directory local** para a nuvem, poderá ir para o Centro de administração do Microsoft 365 e usar o assistente de instalação para adicionar seus usuários manualmente ou pode fazer uma sincronização única com o Azure AD Connect. Há duas maneiras de fazer isso: 
    
    - Se você também tiver um servidor Exchange 2010, Exchange 2013 ou Exchange 2016, poderá usar o Híbrido Mínimo para migrar rapidamente caixas de correio do Exchange para o [Microsoft 365](/Exchange/mailbox-migration/use-minimal-hybrid-to-quickly-migrate). As etapas híbridas mínimas incluem uma sincronização única de usuários com o Azure AD e a migração de email do local para a nuvem. Depois que a migração de email é concluída, a sincronização de diretório é automaticamente desligada quando você usa esse método.
    
    - Use o assistente de sincronização de diretórios para sincronizar seus usuários com a nuvem. Siga as etapas em [Configurar a sincronização de diretórios do Microsoft 365](../enterprise/set-up-directory-synchronization.md) para concluir esse processo. Depois de sincronizar seus usuários com a nuvem, você terá que Desativar a sincronização de [diretórios para o Microsoft 365](../enterprise/turn-off-directory-synchronization.md).
    
    Você também terá que dar a cada usuário adicionado dessa forma uma licença ao Microsoft 365 para empresas. Você pode fazer isso no assistente [de instalação](set-up.md) ou atribuir [licenças aos usuários.](../admin/manage/assign-licenses-to-users.md)
    
### <a name="2-prepare-mobile-devices"></a>2: Preparar dispositivos móveis

Siga as etapas em Configurar dispositivos móveis para [o Microsoft 365](set-up-mobile-devices.md) para usuários comerciais para instalar aplicativos do Office em dispositivos e garantir que eles estão protegidos pelo Microsoft 365 para empresas. 
  
### <a name="3-prepare-pcs"></a>3: Preparar PCs

Os administradores podem pré-selecionar configurações para novos computadores do Windows 10 usando [o Windows AutoPilot](add-autopilot-devices-and-profile.md). Os usuários podem configurar seus dispositivos Windows 10 existentes ou novos seguindo as etapas neste tópico: Configurar computadores windows para [o Microsoft 365 para](set-up-windows-devices.md)usuários comerciais. Para dispositivos existentes, os usuários **podem, opcionalmente,** [mover arquivos para o OneDrive for Business.](move-files-to-onedrive.md) Eles também podem usar ferramentas de terceiros para mover arquivos associados ao perfil do Windows para o OneDrive.
  
Se sua organização usa o Windows Server Active Directory no local, você pode configurar o Microsoft 365 para empresas para proteger seus dispositivos Windows 10, enquanto ainda mantém o acesso a recursos locais que exigem autenticação local. Siga as etapas em Habilitar dispositivos Windows 10 ingressados no domínio a serem gerenciados pelo [Microsoft 365 para](manage-windows-devices.md) empresas para configurar isso. Esse método é preferencial e os dispositivos nesse estado são chamados de dispositivos **ingressados no Azure AD híbridos.** 
  
Se você manter um Active Directory local que contenha alguns recursos locais (como compartilhamentos de arquivos e impressoras), poderá dar aos dispositivos ingressados no **Azure AD** acesso a esses recursos seguindo as etapas aqui: Acessar recursos locais de um dispositivo ingressado no [Azure AD no Microsoft 365 para empresas](access-resources.md).
  
  
## <a name="contact-support"></a>Contatar o suporte

 **Se for necessário entrar em contato com o suporte:**
  
- Contate o seu parceiro.
    
- Como administrador do Microsoft 365 para empresas, você tem acesso à nossa equipe de suporte ao cliente: Contate o suporte para produtos de negócios **[- Ajuda do administrador](../admin/contact-support-for-business-products.md)**
    
## <a name="see-also"></a>Confira também

[Recursos e documentação do Microsoft 365 para empresas](./index.yml)
  
[Gerenciar o Microsoft 365 para empresas](manage.md)[Migrar para o Microsoft 365 para empresas](migrate-to-microsoft-365-business.md)

[Vídeos de treinamento do Microsoft 365 Business ](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)