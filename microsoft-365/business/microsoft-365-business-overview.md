---
title: Introdução ao Microsoft 365 Business
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.date: 9/20/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 496e690b-b75d-4ff5-bf34-cc32905d0364
description: Saiba como configurar o Microsoft 365 Business.
ms.openlocfilehash: ee15ffa98de032d7936d950124cdf772335949bd
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865081"
---
# <a name="get-started-with-microsoft-365-business"></a>Introdução ao Microsoft 365 Business

## <a name="what-is-microsoft-365-business"></a>O que é o Microsoft 365 Business

O Microsoft 365 Business é um conjunto abrangente de ferramentas de colaboração e produtividade comercial, como Outlook, Word, Excel e outros produtos do Office que estão sempre atualizados. Você pode proteger seus arquivos de trabalho em todos os seus dispositivos iOS, Android e Windows 10 com segurança de nível empresarial que é fácil de gerenciar.
  
Microsoft Business de 365 é destinado a até 300 licenças, se precisar de mais licenças, consulte a documentação do [Microsoft 365 Enterprise](https://go.microsoft.com/fwlink/p/?linkid=860986) para obter mais informações. 
  
## <a name="get-microsoft-365-business"></a>Obter o Microsoft 365 Business

- Se você tiver um parceiro, ele receberá o Microsoft 365 Business: [Obter o Microsoft 365 Business pelo Microsoft Partner Center](get-microsoft-365-business.md).
    
- Se você não tiver um parceiro e deseja obter Microsoft 365 Business, você pode [comprar aqui](https://www.microsoft.com/en-us/microsoft-365/business).
    
## <a name="set-up-microsoft-365-business"></a>Configurar o Microsoft 365 Business

 **Visão geral do Microsoft 365 Business Suite configurar**
  
O diagrama a seguir descreve como os administradores configurar Microsoft 365 Business. Também descreve as etapas para preparar o Windows PCs para Microsoft 365 Business. Você também pode adicionar novos dispositivos no Centro de administração do Microsoft 365 Business com o [Piloto automático do Windows](add-autopilot-devices-and-profile.md). Você pode usar o piloto automático para instalar e configurar previamente novos dispositivos, preparando-se para um uso produtivo-los assim que um usuário se conecta com suas credenciais do Microsoft 365 Business.
  
![A diagram that shows the setup and management flow for admins, and also for a user](media/249f81fc-7e79-44c7-8425-3a0b7b651c3b.png)
  
### <a name="1-set-up-microsoft-365-business-admin"></a>1: configurar o Microsoft 365 Business (Admin)

Entre no [Centro de administração do Microsoft 365 Business](https://portal.office.com/adminportal/home) com suas credenciais de administrador global e conclua as etapas abaixo para configurar o Microsoft 365 Business. 
  
1. [Pré-requisitos para a proteção de dados em dispositivos com o Microsoft 365 Business](pre-requisites-for-data-protection.md)
    
    Leia os pré-requisitos primeiro para garantir que seus dispositivos estejam prontos para o Microsoft 365 Business.
    
2. [Configurar o Microsoft 365 Business usando o assistente de configuração](set-up.md)
    
    Se você estiver **permanentemente mudando de um Active Directory local para a nuvem**, você pode adicionar seus usuários manualmente no Centro de administração do Microsoft Business de 365 usando o Assistente de instalação, ou você pode fazer uma sincronização ocasional com Connect do Azure AD. Há duas maneiras de fazer isso: 
    
  - Se você também tiver um Exchange 2010, Exchange 2013 ou 2016 do Exchange server, você pode [Híbrida mínima de uso rapidamente migrar caixas de correio do Exchange para o Office 365](https://support.office.com/article/fdecceed-0702-4af3-85be-f2a0013937ef). As etapas mínimas híbrida incluem uma única sincronização de usuários para o Windows Azure AD, bem como migração no local para a nuvem de email. Após a conclusão da migração do email, a sincronização de diretório automaticamente está desativada ao usar esse método.
    
  - Use o assistente de sincronização de diretórios do Office 365 para sincronizar seus usuários com a nuvem. Siga as etapas em [Configurar a sincronização de diretório no Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846) para concluir esse processo. Após sincronizar seus usuários na nuvem, você terá que [Desativar a sincronização de diretório](https://support.office.com/article/ee5f861e-bd48-4267-83d1-a4ead4b4a00d).
    
    Você também precisará dar a cada usuário que foi adicionado dessa maneira uma licença ao Microsoft 365 Business. Você pode fazer isso, no [Assistente de instalação](set-up.md)ou na [Atribuir licenças aos usuários no Office 365 para empresas](https://support.office.com/article/997596B5-4173-4627-B915-36ABAC6786DC).
    
### <a name="2-prepare-mobile-devices"></a>2: preparar a dispositivos móveis

Siga as etapas em[Configurar dispositivos móveis para usuários comerciais de 365 da Microsoft](set-up-mobile-devices.md) para instalar aplicativos do Office em dispositivos e verificando-se de que elas são protegidas pela Microsoft 365 Business. 
  
### <a name="3-prepare-pcs"></a>3: preparar PCs

Admins previamente pode selecionar configurações para novos dispositivos Windows 10 PCs usando [Piloto automático do Windows](add-autopilot-devices-and-profile.md). Os usuários poderão configurar seus dispositivos de Windows 10 novos ou existentes seguindo as etapas neste tópico: [Configurar PCs do Windows para usuários do Microsoft 365 Business](set-up-windows-devices.md). Para dispositivos existentes usuários também podem **, opcionalmente,**[mova os arquivos ao OneDrive for Business](move-files-to-onedrive.md). Eles também podem usar ferramentas de terceiros para mover arquivos associados ao perfil do Windows para o OneDrive.
  
Se sua organização usa o Windows Server Active Directory local, você pode configurar o Microsoft 365 Business para proteger seus dispositivos Windows 10, e ainda manter o acesso aos recursos locais que exigem autenticação local. Siga as etapas em [Permitir que os dispositivos Windows 10 associados a um domínio a ser gerenciado pelo Microsoft 365 Business](manage-windows-devices.md) configurar isso. Este é o método preferencial e dispositivos nesse estado são chamados **híbrida Azure AD ingressou dispositivos**. 
  
Se você mantiver um local do Active Directory que contém alguns recursos (por exemplo, compartilhamentos de arquivos e impressoras) local, você pode conceder acesso do **Azure dispositivos AD associados** a esses recursos seguindo as etapas aqui: [acesso a recursos do local um Um dispositivo Azure AD ingressaram no Microsoft 365 Business](access-resources.md).
  
Depois que você definiu Windows 10 PCs, você pode [instalar o Office automaticamente](auto-install-or-uninstall-office.md) os dispositivos. 
  
## <a name="contact-support"></a>Contatar o suporte

 **Se for necessário entrar em contato com o suporte:**
  
- Contate o seu parceiro.
    
- Como um administrador do Microsoft 365 Business, você tem acesso a nossa equipe de suporte do cliente, [contate o suporte para produtos de negócios - ajuda de Admin](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) de ****
    

