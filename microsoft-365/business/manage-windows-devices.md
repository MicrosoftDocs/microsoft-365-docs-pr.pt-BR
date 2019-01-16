---
title: Permitir que os dispositivos Windows 10 associados a um domínio a ser gerenciado pelo Microsoft 365 Business
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 9b4de218-f1ad-41fa-a61b-e9e8ac0cf993
description: Aprenda a habilitar o Microsoft 365 proteger AD local ingressou dispositivos Windows 10.
ms.openlocfilehash: 6e66a2c5417c9037232c1ada654d4cac3c520607
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2019
ms.locfileid: "26864828"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business"></a>Permitir que os dispositivos Windows 10 associados a um domínio a ser gerenciado pelo Microsoft 365 Business

Se sua organização usa o Windows Server Active Directory local, você pode configurar o Microsoft 365 Business para proteger seus dispositivos Windows 10, e ainda manter o acesso aos recursos locais que exigem autenticação local. Você pode configurar esse primeiro sincronizando seu Active Directory com o Windows Azure Active Directory, seguido pelo registrando os dispositivos Windows 10 com o Azure AD e inscrevendo-los para o gerenciamento de dispositivo móvel pelo Microsoft 365 Business.
  
## <a name="set-up-domain-joined-devices-to-be-managed-by-microsoft-365-business"></a>Configurar os dispositivos de domínio a ser gerenciado pelo Microsoft 365 Business

Para configurar o domínio dispositivos de sua organização para se beneficiar dos recursos fornecidos pelo Windows Azure Active Directory além do Active Directory no local, você pode implementar **híbrida Azure AD ingressou dispositivos**. Esses são dispositivos que são reunidos tanto para seu Active Directory no local e seu Active Directory do Windows Azure. Híbrido Azure AD ingressado dispositivos podem ser protegidos e gerenciados pelo Microsoft 365 Business.. 
  
Conclua as etapas abaixo para tornar seus dispositivos Windows 10 híbrida Azure AD ingressou e gerenciados pelo Microsoft 365 Business.
  
1. Para sincronizar seus usuários, grupos e contatos do Active Directory local para o Windows Azure Active Directory, execute o Assistente de sincronização de diretórios e o Azure Active Directory Connect conforme descrito em [Configurar a sincronização de diretório para o Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).
    
    > [!NOTE]
    > As etapas são exatamente as mesmas para a Microsoft 365 Business. 
  
2. Antes de concluir a etapa 3 para permitir que os dispositivos Windows 10 a ser híbrida ingressou Azure AD, você precisará certificar-se de que você atende aos seguintes pré-requisitos:
    
   - Você estiver executando a versão mais recente do Azure AD se conectar.
    
   - Conecte-se do Azure AD foi sincronizada todos os objetos de computador dos dispositivos que farão parte híbrida ingressou Azure AD. Se os objetos de computador pertencem ao específica (unidade Organizacional), em seguida, verifique se que essas UOs são definidos para a sincronização do Azure AD conecte também.
    
3. Registre os dispositivos de Windows 10 associados a um domínio existentes para ser híbrida ingressado for Azure AD e registrá-los para o gerenciamento de dispositivo móvel pelo Intune (Microsoft 365 Business):
    
4. Siga as instruções passo a passo [como configurar dispositivos do Azure Active Directory ingressou híbrida](https://go.microsoft.com/fwlink/p/?linkid=872870). Isso permitirá a sincronização de seu local Active Directory ingressou computadores Windows 10 e torná-los a ready na nuvem.
    
5. Para registrar um dispositivo Windows 10 para gerenciamento de dispositivos móveis, consulte [registrar um dispositivo Windows 10 com Intune usando uma diretiva de grupo](https://go.microsoft.com/fwlink/p/?linkid=872871) para obter instruções. Você pode definir a diretiva de grupo em um computador local nível ou para operações em massa, você pode criar essa configuração de diretiva de grupo no seu servidor do controlador de domínio. 
    

