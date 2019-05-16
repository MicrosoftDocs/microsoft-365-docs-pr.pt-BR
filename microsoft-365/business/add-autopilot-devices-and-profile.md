---
title: Use o guia passo a passo para adicionar perfil e dispositivos do Autopilot
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.collection:
- M365-subscription-management
- M365-identity-device-management
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: be5b6d90-3344-4c5e-bf40-5733eb845beb
description: Saiba como usar o Windows AutoPilot para configurar novos dispositivos Windows 10 para sua empresa.
ms.openlocfilehash: 9a70978156fb26ac3aad08f1758b7ee125067d38
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "34072141"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a>Use o guia passo a passo para adicionar perfil e dispositivos do Autopilot

Você pode usar o Windows AutoPilot para configurar **novos** dispositivos Windows 10 para sua empresa, de modo que eles estejam prontos para uso produtivo assim que você os fornecer aos seus funcionários.
  
## <a name="device-requirements"></a>Requisitos do dispositivo

Os dispositivos precisam atender a esses requisitos:
  
- Windows 10, versão 1703 ou posteriores.
    
- Novos dispositivos que ainda não passaram pela configuração inicial pelo usuário do Windows.
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a>Usar o guia de configuração para criar perfis e dispositivos

![Faixa que aponta para https://aka.ms/aboutM365preview.](media/m365admincenterchanging.png)

Se você ainda não tiver perfis ou grupos de dispositivos criados, a melhor maneira de começar é usando o guia passo a passo, mas também pode [adicionar dispositivos](create-and-edit-autopilot-devices.md) e [atribuir perfis](create-and-edit-autopilot-profiles.md) a eles sem usar o guia. 
  
1. Vá para o centro de administração <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>em.

2. Na navegação à esquerda, escolha o **piloto automático**de **dispositivos** \> .

    ![No centro de administração, escolha dispositivos e, em seguida, piloto automático.](media/AutoPilot.png)
  
2. Na página **AutoPilot** , clique ou toque em **iniciar guia**.
    
    ![Click Start guide for step-by-step instructions for Autopilot.](media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. Na página **Carregar arquivo .csv com a lista de dispositivos**, navegue até um local onde está o arquivo .CSV preparado. Em seguida, **Abrir** \> **Avançar**. O arquivo deve ter três cabeçalhos:
    
  - Coluna A: Número de série do dispositivo
    
  - Coluna B: ID do produto Windows
    
  - Coluna C: Hash de hardware
    
    Você encontra essas informações com seu fornecedor de hardware ou pode usar o [script Get-WindowsAutoPilotInfo PowerShell](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) que gerará um arquivo CSV. 
    
    Para saber mais, confira o [Arquivo CSV da lista de dispositivos](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e). Você também pode baixar um exemplo de arquivo na página **Carregar arquivo .csv com uma lista de dispositivos**. 
    
4. Na página **Atribuir um perfil**, você pode escolher perfil existente ou criar um novo. Se você ainda não tiver um, será solicitado a criar um novo. 
    
    Um perfil é um conjunto de configurações que podem ser aplicadas a um único dispositivo ou a um grupo de dispositivos.
    
    Os recursos padrão são necessários e serão definidos automaticamente. Os recursos padrão são:
    
  - São ignorados os registros Cortana, OneDrive e OEM.
    
  - Crie uma experiência de entrada com a marca da sua empresa
    
  - Seus dispositivos serão conectados às contas do Azure Active Directory e inscritos automaticamente para serem gerenciados pelo Microsoft 365 Business.
    
    Para saber mais, confira
    
    [Sobre as configurações de perfil do AutoPilot](autopilot-profile-settings.md) . 
    
5. As outras configurações são **Ignorar as configurações de privacidade** e **Não permitir que o usuário se torne o administrador local**. Por padrão, essas configuração são definidas como **Desativado**. 
    
    Escolha **Avançar**.
    
6. A página **Pronto** indica que o perfil criado (ou escolhido) será aplicado ao grupo de dispositivos que você criou ao carregar a lista de dispositivos. Essas configurações entrarão em vigor quando os usuários do dispositivo fizerem logon na próxima vez. Escolha **Fechar**.
    