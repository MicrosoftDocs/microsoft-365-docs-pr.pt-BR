---
title: Registre dispositivos iOS e Android em seu ambiente de teste do Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/11/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 49c7758a-1c01-4153-9b63-5eae3f6305ce
description: Use este guia de laboratório de teste para registrar os dispositivos em seu ambiente de teste do Microsoft 365 e gerenciá-los remotamente.
ms.openlocfilehash: 98696104ee8453adb7449980cf439eeb152aeea9
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26864816"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-enterprise-test-environment"></a>Registre dispositivos iOS e Android em seu ambiente de teste do Microsoft 365 Enterprise

Seguindo as instruções fornecidas neste artigo, você poderá registrar e testar os recursos de gerenciamento de dispositivo móvel básica para dispositivos com Android e iOS em seu ambiente de teste do Microsoft 365 Enterprise.

![Guias de Laboratório de Teste do Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> Clique [aqui](https://aka.ms/m365etlgstack) para ver um mapa visual de todos os artigos da pilha do Guia de Laboratório de Teste do Microsoft 365 Enterprise.

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: Criar o seu ambiente de teste do Microsoft 365 Enterprise

Se você deseja registrar os dispositivos com Android e iOS de forma leve com os requisitos mínimos, siga as instruções na [configuração base leve](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Se você deseja registrar iOS e dispositivos com Android em uma empresa simulado, siga as instruções na [autenticação de passagem](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Testando automatizada de licenciamento e a associação de grupo não requer o ambiente de teste de simulado empresarial, que inclui uma intranet simulada conectada à Internet e a sincronização de diretório para uma floresta do Windows Server AD. Ele é fornecido aqui como uma opção para que você possa testar automatizada de licenciamento e a associação ao grupo e experimentar em um ambiente que representa uma organização típica. 
>  

## <a name="phase-2-enroll-your-ios-and-android-devices"></a>Fase 2: Registrar seus dispositivos com Android e iOS

Primeiro, use as instruções em [instalar e acesse o aplicativo de Portal da empresa](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) para personalizar o aplicativo Microsoft Intune Portal da empresa para o seu ambiente de teste.

Em seguida, use as instruções em [Configurar o acesso aos seus recursos de empresa](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) para registrar um dispositivo iOS.

Em seguida, use as instruções em [registrar seu dispositivo Android no Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) para registrar um dispositivo Android.

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a>Fase 3: Gerenciar seus dispositivos com Android e iOS remotamente

Microsoft Intune fornece recursos de redefinição de bloqueio remoto e uma senha. Se alguém perder seus dispositivos, você pode bloquear o dispositivo remotamente. Se alguém esquecer sua senha, é possível redefini-lo remotamente.
  
Para bloquear um dispositivo Android ou o iOS remotamente:

1. Entrar no portal do Windows Azure em [https://portal.azure.com](https://portal.azure.com) com as credenciais da sua conta de administrador global.
2. Clique em **todos os serviços**, digite **Intune**e clique em **Intune**.
3. Clique em **dispositivos > todos os dispositivos**.
4. Na lista de dispositivos, clique em um iOS ou um dispositivo Android e, em seguida, clique na ação de **bloqueio remoto** .

    
Para redefinir a senha remotamente:

1. Se necessário, entrar no portal do Windows Azure em [https://portal.azure.com](https://portal.azure.com) com as credenciais da sua conta de administrador global.
2. Clique em **todos os serviços**, digite **Intune**e clique em **Intune**.
3. Clique em **dispositivos > todos os dispositivos**.
4. Da lista de dispositivos você gerenciar, clique em um iOS ou um dispositivo Android e escolha **… Mais**. Escolha a ação remota dispositivo **Remover a senha** .

Experimentação adicionais, consulte [ações de dispositivo disponível](https://docs.microsoft.com/intune/device-management#available-device-actions).

    
## <a name="next-step"></a>Próxima etapa

Explore recursos adicionais de [gerenciamento de dispositivos móveis](m365-enterprise-test-lab-guides.md#mobile-device-management) e capacidades no seu ambiente de teste.

## <a name="see-also"></a>Confira também

[Guias do Laboratório de Teste do Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)
  
[Políticas MAM para o ambiente de teste do Microsoft 365 Enterprise](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[Implantar o Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Mobilidade corporativos + segurança (EMS)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
