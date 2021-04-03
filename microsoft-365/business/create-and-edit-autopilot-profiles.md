---
title: Criar e editar os perfis do AutoPilot
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5cf7139e-cfa1-4765-8aad-001af1c74faa
description: Aprenda a criar um perfil do AutoPilot e aplicá-lo a um dispositivo, bem como editar ou excluir um perfil ou remover um perfil de um dispositivo.
ms.openlocfilehash: 414243da88fb6f39f8e6067d19d49ffe955f725f
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580245"
---
# <a name="create-and-edit-autopilot-profiles"></a>Crie e edite os perfis do AutoPilot

## <a name="create-a-profile"></a>Criar um perfil

Um perfil aplica-se a um dispositivo ou a um grupo de dispositivos,
  
1. No centro de administração do Microsoft 365, escolha **Dispositivos** \> **AutoPilot**.
  
2. Na página **AutoPilot,** escolha a guia **Perfis** \> **Criar perfil**.
    
3. Na página **Criar perfil,** insira um nome para o perfil que o ajuda a identificá-lo, por exemplo, Marketing. A opção Ativar a configuração que você deseja e, em seguida, escolha **Salvar**. Para obter mais informações sobre as configurações de perfil do AutoPilot, consulte [Sobre configurações do Perfil do AutoPilot.](autopilot-profile-settings.md)
    
    ![Enter name and turn on settings in the Create profile panel.](../media/63b5a00d-6a5d-48d0-9557-e7531e80702a.png)
  
### <a name="apply-profile-to-a-device"></a>Aplicar perfil a um dispositivo

Depois de criar um perfil, você pode aplicá-lo a um dispositivo ou a um grupo de dispositivos. Você pode escolher um perfil existente no guia passo a passo e [aplicá-lo](add-autopilot-devices-and-profile.md) a novos dispositivos ou substituir um perfil existente para um dispositivo ou grupo de dispositivos. 
  
1. Na página **Preparar o Windows**, escolha a guia **Dispositivos**. 
    
2. Marque a caixa de seleção ao lado  de um nome de  dispositivo e, no painel Dispositivo, escolha um perfil na lista de perfis \> **atribuídos Salvar**.
    
    ![In the Device panel, select an Assigned profile to apply it.](../media/ed0ce33f-9241-4403-a5de-2dddffdc6fb9.png)
  
## <a name="edit-delete-or-remove-a-profile"></a>Editar, excluir ou remover um perfil

Após atribuir um perfil a um dispositivo, você poderá atualizá-lo, mesmo que já tenha atribuído o dispositivo a um usuário. Quando o dispositivo se conecta à Internet, ele baixa a versão mais recente do seu perfil durante o processo de configuração. Se o usuário restaurar o dispositivo para as configurações padrão de fábrica, o dispositivo baixará novamente as atualizações mais recentes para seu perfil. 
  
### <a name="edit-a-profile"></a>Editar um perfil

1. Na página **Preparar o Windows**, escolha a guia **Perfis**. 
    
2. Marque a caixa de seleção ao lado  de um nome de dispositivo e, no painel Perfil, atualize qualquer uma das configurações disponíveis \> **Salvar**.
    
    Se você fizer isso antes de um usuário conectar o dispositivo à internet, o perfil será aplicado ao processo de configuração.
    
### <a name="delete-a-profile"></a>Excluir um perfil

1. Na página **Preparar o Windows**, escolha a guia **Perfis**. 
    
2. Marque a caixa de seleção ao lado de um nome de dispositivo e, no **painel** Perfil, selecione Excluir **salvar perfil** \> .
    
    Quando você exclui um perfil, ele é removido de um dispositivo ou grupo de dispositivos ao qual foi atribuído.
    
### <a name="remove-a-profile"></a>Remover um perfil

1. Na página **Preparar o Windows**, escolha a guia **Dispositivos**. 
    
2. Marque a caixa de seleção ao lado  de um nome  de dispositivo e, no painel Dispositivo, escolha **Nenhum** na lista de perfis \> **atribuídos Salvar**.
    
