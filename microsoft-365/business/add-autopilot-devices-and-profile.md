---
title: Use o guia passo a passo para adicionar perfil e dispositivos do Autopilot
f1.keywords:
- NOCSH
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
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: be5b6d90-3344-4c5e-bf40-5733eb845beb
description: Saiba como usar o Windows AutoPilot para configurar novos dispositivos Windows 10 para sua empresa para que eles estão prontos para uso do funcionário.
ms.openlocfilehash: f263cc90656ae5e7be1a89e3c7f56bfb2d0e3651
ms.sourcegitcommit: 3b369a44b71540c8b8214ce588a7aa6f47c3bb1e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2021
ms.locfileid: "50099741"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a>Use o guia passo a passo para adicionar perfil e dispositivos do Autopilot

Você pode usar o Windows AutoPilot para configurar novos dispositivos **Windows** 10 para sua empresa para que eles ficam prontos para uso quando você os entrega aos funcionários.
  
## <a name="device-requirements"></a>Requisitos do dispositivo

Os dispositivos devem atender a estes requisitos:
  
- Windows 10, versão 1703 ou posterior
    
- Novos dispositivos que não passaram pela configuração de configuração do Windows
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a>Usar o guia de configuração para criar perfis e dispositivos

[![Rótulo para informar que o centro de administração está mudando e você pode encontrar mais detalhes em aka.ms/aboutM365preview.](../media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)

Se você ainda não criou grupos de dispositivos ou perfis, a melhor maneira de começar é usando o guia passo a passo. Você também pode [adicionar dispositivos](create-and-edit-autopilot-devices.md) [e atribuir perfis](create-and-edit-autopilot-profiles.md) a eles sem usar o guia. 
  
1. Vá para o centro de administração do<a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.

2. No painel de navegação esquerdo, escolha **Dispositivos** \> **AutoPilot.**

    ![No centro de administração, escolha os dispositivos e o AutoPilot.](../media/AutoPilot.png)
  
2. Na página **AutoPilot,** clique ou toque no **guia Iniciar.**
    
    ![Click Start guide for step-by-step instructions for Autopilot.](../media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. No arquivo **Upload .csv com a lista** de dispositivos, navegue até um local onde você preparou. Arquivo CSV **e,** em seguida, Abrir \> **Próximo**. O arquivo deve ter três headers:
    
    - Coluna A: Número de série do dispositivo
    
    - Coluna B: ID do produto Windows
    
    - Coluna C: Hash de hardware
    
    Você pode obter essas informações do fornecedor de hardware ou usar o [script Get-WindowsAutoPilotInfo powerShell](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) para gerar um arquivo CSV. 
    
    Para saber mais, confira o [Arquivo CSV da lista de dispositivos](https://docs.microsoft.com/microsoft-365/admin/misc/device-list). Você também pode baixar um exemplo de arquivo na página **Carregar arquivo .csv com uma lista de dispositivos**. 
    
> [!NOTE]
> Esse script usa WMI para recuperar as propriedades necessárias para que um cliente registre um dispositivo com o Windows Autopilot. Observe que é normal que o arquivo CSV resultante não colete um valor de ID de Produto (PKID) do Windows, pois isso não é necessário para registrar um dispositivo e o PKID sendo NULL no CSV de saída é totalmente bom. Somente o número de série e o hash de hardware serão preenchidos.
    
4. Na página **Atribuir um perfil,** você pode escolher um perfil existente ou criar um novo. Se você ainda não tiver um, será solicitado a criar um. 
    
    Um perfil é um conjunto de configurações que podem ser aplicadas a um único dispositivo ou a um grupo de dispositivos.
    
    Os recursos padrão são necessários e são definidos automaticamente. Os recursos padrão são:
    
    - Ignore o registro da Cortana, do OneDrive e do OEM.
    
    - Crie uma experiência de entrada com a marca da sua empresa
    
    - Conecte seus dispositivos às contas do Azure Active Directory e inscreva-os automaticamente para serem gerenciados pelo Microsoft 365 Business Premium.
    
    Para obter mais informações, consulte Sobre as configurações do [Perfil do AutoPilot.](autopilot-profile-settings.md) 
    
5. As outras configurações são **Ignorar as configurações de privacidade** e **Não permitir que o usuário se torne o administrador local**. Por padrão, essas configuração são definidas como **Desativado**. 
    
    Escolha **Avançar**.
    
6. **Você terminou indica que** o perfil que você criou (ou escolheu) será aplicado ao grupo de dispositivos que você criou carregando a lista de dispositivos. As configurações entrarão em vigor quando os usuários do dispositivo entrarem em seguida. Escolha **Fechar**.
    
