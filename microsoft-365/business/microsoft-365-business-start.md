---
title: Introdução ao Microsoft 365 Business
f1.keywords:
- NOCSH
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
- TRN_SMB
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- TRN_M365B
- OKR_SMB_Videos
search.appverid:
- BCS160
- MET150
ms.assetid: 496e690b-b75d-4ff5-bf34-cc32905d0364
description: Saiba como configurar o Microsoft 365 Business.
ms.openlocfilehash: a353e39b824bae702fa015b0c7d3dd7e6416454c
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41593712"
---
# <a name="get-started-with-microsoft-365-business"></a>Introdução ao Microsoft 365 Business

## <a name="what-is-microsoft-365-business"></a>O que é o Microsoft 365 Business

O Microsoft 365 Business é um conjunto abrangente de ferramentas de colaboração e produtividade de negócios, como Outlook, Word, Excel e outros produtos do Office que estão sempre atualizados. Você pode proteger seus arquivos de trabalho em todos os seus dispositivos iOS, Android e Windows 10 com segurança de nível empresarial que seja simples de gerenciar.

Assista a este vídeo para ver uma rápida visão geral do Microsoft 365 Business.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2mhaA] 
  
O Microsoft 365 Business é destinado a até 300 licenças. Se você precisar de mais licenças, consulte a documentação do [Microsoft 365 Enterprise](https://go.microsoft.com/fwlink/p/?linkid=860986) para obter mais informações. 
  
## <a name="get-microsoft-365-business"></a>Obter o Microsoft 365 Business

- Se você tiver um parceiro, ele receberá o Microsoft 365 Business: [obter o microsoft 365 Business do centro de parceria da Microsoft](get-microsoft-365-business.md).
    
- Se você não tem um parceiro e deseja obter o Microsoft 365 Business, você pode [comprá-lo aqui](https://www.microsoft.com/microsoft-365/business).
    
## <a name="set-up-microsoft-365-business"></a>Configurar o Microsoft 365 Business

 **Visão geral da configuração do Microsoft 365 Business Suite**
  
O diagrama a seguir descreve como os administradores configuram o Microsoft 365 Business. Ele também descreve as etapas para preparar os computadores com Windows para Microsoft 365 Business. Você também pode adicionar novos dispositivos no centro de administração de negócios do Microsoft 365 com o [Windows AutoPilot](add-autopilot-devices-and-profile.md). Você pode usar o AutoPilot para configurar e pré-configurar novos dispositivos para que eles estejam prontos para uso produtivo assim que um usuário entrar com suas credenciais de negócios do Microsoft 365.
  
![A diagram that shows the setup and management flow for admins, and also for a user](media/249f81fc-7e79-44c7-8425-3a0b7b651c3b.png)

Assista a este vídeo para obter uma visão geral da instalação do Microsoft 365 Business.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSM] 

Se você achou esse vídeo útil, Confira as [ séries completas de treinamento para pequenas empresas e as novidades do Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

  
### <a name="1-set-up-microsoft-365-business-admin"></a>1: configurar o Microsoft 365 Business (admin)

Entre no [centro de administração de negócios do Microsoft 365](https://portal.office.com/adminportal/home) com suas credenciais de administrador global e conclua as seguintes etapas para configurar o Microsoft 365 Business. 
  
1. [Pré-requisitos para a proteção de dados em dispositivos com o Microsoft 365 Business](pre-requisites-for-data-protection.md)
    
    Leia os pré-requisitos primeiro para garantir que seus dispositivos estejam prontos para o Microsoft 365 Business.
    
2. [Usar o assistente de configuração para configurar o Microsoft 365 Business](set-up.md)
    
    Se você estiver **migrando permanentemente de um Active Directory local para a nuvem**, poderá ir para o centro de administração de negócios do Microsoft 365 e usar o assistente de configuração para adicionar seus usuários manualmente ou você pode fazer uma sincronização única com o Azure ad Connect. Há duas maneiras de fazer isso: 
    
    - Se você também tiver um servidor Exchange 2010, Exchange 2013 ou Exchange 2016, poderá usar o [mínimo híbrido para migrar rapidamente as caixas de correio do Exchange para o Office 365](https://support.office.com/article/fdecceed-0702-4af3-85be-f2a0013937ef). As etapas híbridas mínimas incluem uma sincronização única dos usuários para o Azure AD e a migração de emails do local para a nuvem. Após a conclusão da migração de email, a sincronização de diretórios será desativada automaticamente quando você usar esse método.
    
    - Use o assistente de sincronização de diretórios do Office 365 para sincronizar seus usuários com a nuvem. Siga as etapas em [Configurar a sincronização de diretório no Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846) para concluir esse processo. Após sincronizar seus usuários com a nuvem, você terá que desativar a [sincronização de diretório do Office 365](https://support.office.com/article/ee5f861e-bd48-4267-83d1-a4ead4b4a00d).
    
    Você também precisará conceder a cada usuário uma licença para o Microsoft 365 Business. Você pode fazer isso no [Assistente de configuração](set-up.md) ou pode [atribuir licenças aos usuários no Office 365 para empresas](https://support.office.com/article/997596B5-4173-4627-B915-36ABAC6786DC).
    
### <a name="2-prepare-mobile-devices"></a>2: preparar dispositivos móveis

Siga as etapas descritas em [set up Mobile Devices for Microsoft 365 business users](set-up-mobile-devices.md) to install Office apps on Devices e verifique se eles estão protegidos pelo Microsoft 365 Business. 
  
### <a name="3-prepare-pcs"></a>3: preparar os computadores

Os administradores podem selecionar previamente configurações para novos computadores com Windows 10 usando o [Windows AutoPilot](add-autopilot-devices-and-profile.md). Os usuários podem configurar seus dispositivos Windows 10 existentes ou novos, seguindo as etapas descritas neste tópico: [set up Windows PCs for Microsoft 365 business users](set-up-windows-devices.md). Para dispositivos existentes, os usuários podem **, opcionalmente** , [mover arquivos para o onedrive for Business](move-files-to-onedrive.md). Eles também podem usar ferramentas de terceiros para mover arquivos associados ao perfil do Windows para o OneDrive.
  
Se sua organização usa o Windows Server Active Directory no local, você pode configurar o Microsoft 365 Business para proteger seus dispositivos Windows 10 e ainda manter o acesso a recursos locais que exigem autenticação local. Siga as etapas em [habilitar dispositivos do Windows 10 associados ao domínio para serem gerenciados pela Microsoft 365 Business](manage-windows-devices.md) para configurar isso. Esse método é preferido, e os dispositivos nesse estado são chamados de **dispositivos do Azure ad associados híbridos**. 
  
Se você mantiver um Active Directory local que contenha alguns recursos locais (como compartilhamentos de arquivos e impressoras), poderá dar aos seus **dispositivos associados ao AD do Azure** acesso a esses recursos seguindo as etapas aqui: [acessar recursos locais de um dispositivo associado ao AD do Azure no Microsoft 365 Business](access-resources.md).
  
  
## <a name="contact-support"></a>Contatar o suporte

 **Se for necessário entrar em contato com o suporte:**
  
- Contate o seu parceiro.
    
- Como um administrador de negócios do Microsoft 365, você tem acesso à nossa equipe de suporte ao cliente: ** [contatar o suporte para produtos de negócios-ajuda para administradores](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)**
    
## <a name="see-also"></a>Confira também

[Documentação e recursos do Microsoft 365 Business](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[Gerenciar o microsoft 365 Business](manage.md)[migrar para o Microsoft 365 Business](migrate-to-microsoft-365-business.md)

[Vídeos de treinamento do Microsoft 365 Business ](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816) 
