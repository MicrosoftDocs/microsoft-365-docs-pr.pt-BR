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
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: be5b6d90-3344-4c5e-bf40-5733eb845beb
description: Saiba como usar o Windows AutoPilot para configurar novos dispositivos Windows 10 para sua empresa.
ms.openlocfilehash: 5f40dac57285b83da57d4506bac58e562475522c
ms.sourcegitcommit: 8193b7da5b1a415835d02ca96883c351df7326ed
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/14/2019
ms.locfileid: "38323086"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a>Use o guia passo a passo para adicionar perfil e dispositivos do Autopilot

Você pode usar o Windows AutoPilot para configurar **novos** dispositivos Windows 10 para sua empresa, de modo que eles fiquem prontos para uso quando você os conceder aos seus funcionários.
  
## <a name="device-requirements"></a>Requisitos do dispositivo

Os dispositivos devem atender a estes requisitos:
  
- Windows 10, versão 1703 ou posterior
    
- Novos dispositivos que não foram transferidos pela experiência inicial pelo Windows
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a>Usar o guia de configuração para criar perfis e dispositivos

[![Rótulo para informar que o centro de administração está mudando e você pode encontrar mais detalhes em aka.ms/aboutM365preview.](media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)

Se você ainda não criou grupos ou perfis de dispositivos, a melhor maneira de começar é usando o guia passo a passo. Você também pode [Adicionar dispositivos](create-and-edit-autopilot-devices.md) e [atribuir perfis](create-and-edit-autopilot-profiles.md) a eles sem usar o guia. 
  
1. Vá para o centro de administração do<a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.

2. No painel de navegação esquerdo, escolha **dispositivos** \> **AutoPilot**.

    ![No centro de administração, escolha dispositivos e, em seguida, piloto automático.](media/AutoPilot.png)
  
2. Na página **AutoPilot** , clique ou toque em **iniciar guia**.
    
    ![Click Start guide for step-by-step instructions for Autopilot.](media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. Na página **carregar arquivo. csv com a lista de dispositivos** , navegue até um local onde você está preparado. CSV e, em seguida, **abra** \> **Avançar**. O arquivo deve ter três cabeçalhos:
    
    - Coluna A: Número de série do dispositivo
    
    - Coluna B: ID do produto Windows
    
    - Coluna C: Hash de hardware
    
    Você pode obter essas informações do seu fornecedor de hardware ou pode usar o [script Get-WindowsAutoPilotInfo do PowerShell](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) para gerar um arquivo CSV. 
    
    Para saber mais, confira o [Arquivo CSV da lista de dispositivos](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e). Você também pode baixar um exemplo de arquivo na página **Carregar arquivo .csv com uma lista de dispositivos**. 
    
4. Na página **atribuir um perfil** , você pode escolher um perfil existente ou criar um novo. Se você ainda não tiver um, você será solicitado a criar um. 
    
    Um perfil é um conjunto de configurações que podem ser aplicadas a um único dispositivo ou a um grupo de dispositivos.
    
    Os recursos padrão são necessários e são definidos automaticamente. Os recursos padrão são:
    
    - Ignorar o registro de Cortana, OneDrive e OEM.
    
    - Crie uma experiência de entrada com a marca da sua empresa
    
    - Conecte seus dispositivos às contas do Azure Active Directory e registre-os automaticamente para serem gerenciados pelo Microsoft 365 Business.
    
    Para obter mais informações, consulte [sobre as configurações de perfil do AutoPilot](autopilot-profile-settings.md). 
    
5. As outras configurações são **Ignorar as configurações de privacidade** e **Não permitir que o usuário se torne o administrador local**. Por padrão, essas configuração são definidas como **Desativado**. 
    
    Escolha **Avançar**.
    
6. **Você concluiu** indica que o perfil criado (ou escolhido) será aplicado ao grupo de dispositivos que você criou carregando a lista de dispositivos. As configurações entrarão em vigor quando os usuários do dispositivo entrarem em seguida. Escolha **Fechar**.
    