---
title: Introdução ao Microsoft 365 Business
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom: OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: 496e690b-b75d-4ff5-bf34-cc32905d0364
description: Saiba como configurar o Microsoft 365 Business.
ms.openlocfilehash: 52e3167986bb7ed835762540e8076a3b9b2a0b56
ms.sourcegitcommit: 6003d6da0a85c97357eb3dba3918eb145f381fe1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "37287626"
---
# <a name="get-started-with-microsoft-365-business"></a>Introdução ao Microsoft 365 Business

## <a name="what-is-microsoft-365-business"></a>O que é o Microsoft 365 Business

O Microsoft 365 Business é um conjunto abrangente de ferramentas de colaboração e produtividade comercial, como Outlook, Word, Excel e outros produtos do Office que estão sempre atualizados. Você pode proteger seus arquivos de trabalho em todos os seus dispositivos iOS, Android e Windows 10 com segurança de nível empresarial que é fácil de gerenciar.
  
O Microsoft 365 Business é destinado a até 300 licenças, se você precisar de mais licenças, consulte a documentação do [Microsoft 365 Enterprise](https://go.microsoft.com/fwlink/p/?linkid=860986) para obter mais informações. 
  
## <a name="get-microsoft-365-business"></a>Obter o Microsoft 365 Business

- Se você tiver um parceiro, ele receberá o Microsoft 365 Business: [Obter o Microsoft 365 Business pelo Microsoft Partner Center](get-microsoft-365-business.md).
    
- Se você não tem um parceiro e deseja obter o Microsoft 365 Business, você pode [comprá-lo aqui](https://www.microsoft.com/en-us/microsoft-365/business).
    
## <a name="set-up-microsoft-365-business"></a>Configurar o Microsoft 365 Business

 **Visão geral da configuração do Microsoft 365 Business Suite**
  
O diagrama a seguir descreve como os administradores configuram o Microsoft 365 Business. Ele também descreve as etapas para preparar os computadores com Windows para Microsoft 365 Business. Você também pode adicionar novos dispositivos no centro de administração do Microsoft 365 Business com o [Windows AutoPilot](add-autopilot-devices-and-profile.md). Você pode usar o AutoPilot para instalar e pré-configurar novos dispositivos preparando-os para uso produtivo assim que o usuário entrar com as credenciais do Microsoft 365 Business.
  
![A diagram that shows the setup and management flow for admins, and also for a user](media/249f81fc-7e79-44c7-8425-3a0b7b651c3b.png)
  
### <a name="1-set-up-microsoft-365-business-admin"></a>1: configurar o Microsoft 365 Business (admin)

Entre no [Centro de administração do Microsoft 365 Business](https://portal.office.com/adminportal/home) com suas credenciais de administrador global e conclua as etapas abaixo para configurar o Microsoft 365 Business. 
  
1. [Pré-requisitos para a proteção de dados em dispositivos com o Microsoft 365 Business](pre-requisites-for-data-protection.md)
    
    Leia os pré-requisitos primeiro para garantir que seus dispositivos estejam prontos para o Microsoft 365 Business.
    
2. [Configurar o Microsoft 365 Business usando o assistente de configuração](set-up.md)
    
    Se você estiver **migrando permanentemente de um Active Directory local para a nuvem**, poderá adicionar seus usuários manualmente no centro de administração de negócios do Microsoft 365 usando o assistente de configuração ou poderá fazer uma sincronização única com o Azure ad Connect. Há duas maneiras de fazer isso: 
    
  - Se você também tiver um servidor Exchange 2010, Exchange 2013 ou Exchange 2016, poderá usar o [mínimo híbrido para migrar rapidamente as caixas de correio do Exchange para o Office 365](https://support.office.com/article/fdecceed-0702-4af3-85be-f2a0013937ef). As etapas da opção híbrida mínima incluem uma sincronização única de usuários para o Azure AD, bem como a migração de emails do local para a nuvem. Após concluir a migração de emails, a sincronização de diretórios será automaticamente desativada nesse método.
    
  - Use o assistente de sincronização de diretórios do Office 365 para sincronizar seus usuários com a nuvem. Siga as etapas em [Configurar a sincronização de diretório no Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846) para concluir esse processo. Após sincronizar seus usuários na nuvem, você terá que [Desativar a sincronização de diretório](https://support.office.com/article/ee5f861e-bd48-4267-83d1-a4ead4b4a00d).
    
    Você também precisa dar a cada usuário que foi adicionado dessa forma uma licença para o Microsoft 365 Business. Você pode fazer isso no [Assistente de configuração](set-up.md)ou [atribuir licenças aos usuários no Office 365 para empresas](https://support.office.com/article/997596B5-4173-4627-B915-36ABAC6786DC).
    
### <a name="2-prepare-mobile-devices"></a>2: preparar dispositivos móveis

Siga as etapas descritas em[set up Mobile Devices for Microsoft 365 business users](set-up-mobile-devices.md) para instalar os aplicativos do Office em dispositivos e verificar se eles estão protegidos pelo Microsoft 365 Business. 
  
### <a name="3-prepare-pcs"></a>3: preparar os computadores

Os administradores podem selecionar previamente as configurações para novos computadores com Windows 10 usando o [Windows AutoPilot](add-autopilot-devices-and-profile.md). Os usuários podem configurar seus dispositivos Windows 10 existentes ou novos, seguindo as etapas descritas neste tópico: [set up Windows PCs for Microsoft 365 business users](set-up-windows-devices.md). Para dispositivos existentes **,** os usuários também podem[mover arquivos para o onedrive for Business](move-files-to-onedrive.md). Eles também podem usar ferramentas de terceiros para mover arquivos associados ao perfil do Windows para o OneDrive.
  
Se sua organização usa o Windows Server Active Directory no local, você pode configurar o Microsoft 365 Business para proteger seus dispositivos Windows 10 e ainda manter o acesso a recursos locais que exigem autenticação local. Siga as etapas em [habilitar dispositivos do Windows 10 associados ao domínio para serem gerenciados pela Microsoft 365 Business](manage-windows-devices.md) para configurar isso. Este é o método preferencial e os dispositivos nesse estado são chamados de **dispositivos do Azure ad associados híbridos**. 
  
Se você mantiver um Active Directory local que contenha alguns recursos locais (como compartilhamentos de arquivos e impressoras), poderá dar aos seus **dispositivos associados ao AD do Azure** acesso a esses recursos seguindo as etapas aqui: [acessar recursos locais de um Dispositivo ingressado no AD do Azure no Microsoft 365 Business](access-resources.md).
  
Depois de configurar os computadores com Windows 10, você pode [instalar o Office automaticamente](auto-install-or-uninstall-office.md) nos dispositivos. 
  
## <a name="contact-support"></a>Contatar o suporte

 **Se for necessário entrar em contato com o suporte:**
  
- Contate o seu parceiro.
    
- Como um administrador de negócios do Microsoft 365, você tem acesso à nossa equipe de suporte ao cliente, ** [entrar em contato com o suporte para produtos de negócios-ajuda para administradores](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)**
    
## <a name="related-topics"></a>Tópicos Relacionados
[Documentação e recursos do Microsoft 365 Business](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[Gerenciar o microsoft 365 Business](manage.md)[migrar para o Microsoft 365 Business](migrate-to-microsoft-365-business.md)
  

