---
title: Registrar dispositivos iOS e Android em seu ambiente de teste do Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/11/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 49c7758a-1c01-4153-9b63-5eae3f6305ce
description: Use este guia de laboratório de teste para registrar dispositivos no seu ambiente de teste do Microsoft 365 e gerenciá-los remotamente.
ms.openlocfilehash: e653b3e6cafb6ee2eb492709a2d060c7b92a6904
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32281242"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-enterprise-test-environment"></a>Registrar dispositivos iOS e Android em seu ambiente de teste do Microsoft 365 Enterprise

Seguindo as instruções fornecidas neste artigo, você poderá registrar e testar recursos básicos de gerenciamento de dispositivos móveis para dispositivos iOS e Android em seu ambiente de teste do Microsoft 365 Enterprise.

![Guias de laboratório de teste da Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> Clique [aqui](https://aka.ms/m365etlgstack) para ver um mapa visual de todos os artigos da pilha do Guia de Laboratório de Teste do Microsoft 365 Enterprise.

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: criar seu ambiente de teste do Microsoft 365 Enterprise

Se você só quiser inscrever dispositivos iOS e Android de forma leve com os requisitos mínimos, siga as instruções em [configuração básica leve](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Se você deseja registrar dispositivos iOS e Android em uma empresa simulada, siga as instruções em [autenticação de passagem](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Testar o licenciamento automatizado e a associação de grupo não requer o ambiente de teste corporativo simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para uma floresta dos serviços de domínio Active Directory (AD DS). Ele é fornecido aqui como uma opção para que você possa testar o licenciamento e a associação de grupo automatizados e experimentá-lo em um ambiente que representa uma organização típica. 
>  

## <a name="phase-2-enroll-your-ios-and-android-devices"></a>Fase 2: registrar seus dispositivos iOS e Android

Primeiro, use as instruções em [instalar e entre no aplicativo do portal da empresa](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) para personalizar o aplicativo portal da empresa do Microsoft Intune para seu ambiente de teste.

Em seguida, use as instruções em [Configurar o acesso aos recursos da sua empresa](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) para registrar um dispositivo IOS.

Em seguida, use as instruções em [registrar seu dispositivo Android no Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) para registrar um dispositivo Android.

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a>Fase 3: gerenciar seus dispositivos iOS e Android remotamente

O Microsoft Intune fornece recursos de bloqueio e redefinição de senha remotos. Se alguém perder um dispositivo, você poderá bloqueá-lo remotamente. Se alguém esquecer sua senha, você poderá redefini-la remotamente.
  
Para bloquear um dispositivo iOS ou Android remotamente:

1. Entre no portal do Azure [https://portal.azure.com](https://portal.azure.com) com as credenciais de sua conta de administrador global.
2. Clique em **todos os serviços**, digite **Intune**e clique em **Intune**.
3. Clique em **dispositivos _GT_ todos os dispositivos**.
4. Na lista de dispositivos, clique em um dispositivo iOS ou Android e, em seguida, clique na ação de **bloqueio remoto** .

    
Para redefinir a senha remotamente:

1. Se necessário, entre no portal do Azure [https://portal.azure.com](https://portal.azure.com) com as credenciais de sua conta de administrador global.
2. Clique em **todos os serviços**, digite **Intune**e clique em **Intune**.
3. Clique em **dispositivos _GT_ todos os dispositivos**.
4. Na lista de dispositivos que você gerencia, clique em um dispositivo iOS ou Android e escolha **... Mais**. Em seguida, escolha a ação de remover dispositivo de **senha** remoto.

Para experimentação adicional, confira [ações de dispositivo disponíveis](https://docs.microsoft.com/intune/device-management#available-device-actions).

    
## <a name="next-step"></a>Próxima etapa

Explore recursos de [Gerenciamento de dispositivos móveis](m365-enterprise-test-lab-guides.md#mobile-device-management) e recursos adicionais em seu ambiente de teste.

## <a name="see-also"></a>Confira também

[Guias do Laboratório de Teste do Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)
  
[Políticas de conformidade de dispositivo para seu ambiente de teste do Microsoft 365 Enterprise](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[Implantar o Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Enterprise Mobility + Security (EMS)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
