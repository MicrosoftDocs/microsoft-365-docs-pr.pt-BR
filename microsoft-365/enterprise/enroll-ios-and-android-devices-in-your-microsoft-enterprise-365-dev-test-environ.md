---
title: Registrar dispositivos iOS e Android em seu ambiente de teste do Microsoft 365 for Enterprise
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 49c7758a-1c01-4153-9b63-5eae3f6305ce
description: Use este guia de laboratório de teste para registrar dispositivos no seu ambiente de teste do Microsoft 365 e gerenciá-los remotamente.
ms.openlocfilehash: 3736934dbb62e84aad6a91fcd1d65b4a47ef8637
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487691"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-for-enterprise-test-environment"></a>Registrar dispositivos iOS e Android em seu ambiente de teste do Microsoft 365 for Enterprise

*Este guia de laboratório de teste só pode ser usado para o Microsoft 365 para ambientes de teste corporativos.*

Este artigo descreve como registrar e testar recursos básicos de gerenciamento de dispositivos móveis para dispositivos iOS e Android em seu ambiente de teste do Microsoft 365 for Enterprise.

Registrar dispositivos iOS e Android em seu ambiente de teste envolve três fases:
- [Fase 1: desenvolver seu ambiente de teste do Microsoft 365 for Enterprise](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: registrar seus dispositivos iOS e Android](#phase-2-enroll-your-ios-and-android-devices)
- [Fase 3: gerenciar seus dispositivos iOS e Android remotamente](#phase-3-manage-your-ios-and-android-devices-remotely)

![Guias de Laboratório de Teste do Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> Para obter um mapa Visual para todos os artigos da pilha do guia do laboratório de teste do Microsoft 365 for Enterprise, vá para a [pilha do guia do laboratório de teste da microsoft 365 para empresas](../downloads/Microsoft365EnterpriseTLGStack.pdf).

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: desenvolver seu ambiente de teste do Microsoft 365 for Enterprise

Se você deseja registrar dispositivos iOS e Android de forma leve com os requisitos mínimos, siga as instruções em [configuração básica leve](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Se você deseja registrar dispositivos iOS e Android em uma empresa simulada, siga as instruções em [autenticação de passagem](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Testar o licenciamento automatizado e a associação de grupo não requer o ambiente de teste corporativo simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para uma floresta dos serviços de domínio Active Directory (AD DS). Ele é fornecido aqui como uma opção para que você possa testar o licenciamento e a associação de grupo automatizados e pode experimentá-lo em um ambiente que representa uma organização típica.

## <a name="phase-2-enroll-your-ios-and-android-devices"></a>Fase 2: registrar seus dispositivos iOS e Android

Primeiro, use as instruções em [instalar e entre no aplicativo do portal da empresa](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) para personalizar o aplicativo portal da empresa do Microsoft Intune para seu ambiente de teste.

Em seguida, use as instruções em [Configurar o acesso aos recursos da sua empresa](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) para registrar um dispositivo IOS.

Em seguida, use as instruções em [registrar seu dispositivo Android no Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) para registrar um dispositivo Android.

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a>Fase 3: gerenciar seus dispositivos iOS e Android remotamente

O Microsoft Intune fornece recursos de bloqueio e redefinição de senha remotos. Se alguém perder o dispositivo, você poderá bloquear o dispositivo remotamente. Se alguém esquecer sua senha, você poderá redefini-la remotamente.
  
Para bloquear remotamente um dispositivo iOS ou Android:

1. Entre no portal do Azure [https://portal.azure.com](https://portal.azure.com) com as credenciais de sua conta de administrador global.
2. No portal do Azure, insira o **Intune** na caixa de pesquisa e selecione **Intune**.
3. Clique em **dispositivos > todos os dispositivos**.
4. Na lista de dispositivos, selecione um dispositivo iOS ou Android e, em seguida, selecione a ação de **bloqueio remoto** .
    
Para redefinir a senha remotamente:

1. Se necessário, entre no portal do Azure [https://portal.azure.com](https://portal.azure.com) com as credenciais de sua conta de administrador global.
2. No portal do Azure, insira o **Intune** na caixa de pesquisa e selecione **Intune**.
3. Selecione **dispositivos**  >  **todos os dispositivos**.
4. Na lista de dispositivos que você gerencia, selecione um dispositivo iOS ou Android, selecione **... E, em seguida, selecione**a ação remover o dispositivo de **senha** remoto.

Para experimentação adicional, confira [ações de dispositivo disponíveis](https://docs.microsoft.com/intune/device-management#available-device-actions).
    
## <a name="next-step"></a>Próxima etapa

Explore recursos de [Gerenciamento de dispositivos móveis](m365-enterprise-test-lab-guides.md#mobile-device-management) e recursos adicionais em seu ambiente de teste.

## <a name="see-also"></a>Confira também

[Guias do Laboratório de Teste do Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)
  
[Políticas de conformidade de dispositivo para seu ambiente de teste do Microsoft 365 for Enterprise](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[Visão geral do Microsoft 365 para empresas](microsoft-365-overview.md)
