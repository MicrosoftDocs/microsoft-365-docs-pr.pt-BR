---
title: Registre os dispositivos iOS/iPadOS e Android em seu ambiente de teste do Microsoft 365 for Enterprise
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/19/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 49c7758a-1c01-4153-9b63-5eae3f6305ce
description: Use este guia de laboratório de teste para registrar dispositivos no seu ambiente de teste do Microsoft 365 e gerenciá-los remotamente.
ms.openlocfilehash: 06f83d1ed61bcc530b6aa974d7730f1aadc0ecbd
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367078"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-for-enterprise-test-environment"></a>Registrar dispositivos iOS e Android em seu ambiente de teste do Microsoft 365 for Enterprise

*Este guia de laboratório de teste só pode ser usado para o Microsoft 365 para ambientes de teste corporativos.*

Este artigo descreve como registrar e testar os recursos básicos de gerenciamento de dispositivos móveis para o iOS/iPadOS e dispositivos Android em seu ambiente de teste do Microsoft 365 for Enterprise.

A inscrição do iOS/iPadOS e dispositivos Android em seu ambiente de teste envolve três fases:
- [Fase 1: desenvolver seu ambiente de teste do Microsoft 365 for Enterprise](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: registrar seus dispositivos iOS/iPadOS e Android](#phase-2-enroll-your-ios-and-android-devices)
- [Fase 3: gerenciar o iOS/iPadOS e dispositivos Android remotamente](#phase-3-manage-your-ios-and-android-devices-remotely)

![Guias de Laboratório de Teste do Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> Para obter um mapa Visual para todos os artigos da pilha do guia do laboratório de teste do Microsoft 365 for Enterprise, vá para a [pilha do guia do laboratório de teste da microsoft 365 para empresas](../downloads/Microsoft365EnterpriseTLGStack.pdf).

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: desenvolver seu ambiente de teste do Microsoft 365 for Enterprise

Se você quiser inscrever dispositivos do iOS/iPadOS e Android de forma leve com os requisitos mínimos, siga as instruções em [configuração básica leve](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Se você quiser inscrever dispositivos do iOS/iPadOS e Android em uma empresa simulada, siga as instruções em [autenticação de passagem](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Testar o licenciamento automatizado e a associação de grupo não requer o ambiente de teste corporativo simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para uma floresta dos serviços de domínio Active Directory (AD DS). Ele é fornecido aqui como uma opção para que você possa testar o licenciamento e a associação de grupo automatizados e pode experimentá-lo em um ambiente que representa uma organização típica.

## <a name="phase-2-enroll-your-ios-and-android-devices"></a>Fase 2: registrar seus dispositivos iOS e Android

Se você estiver considerando uma solução de gerenciamento de dispositivo móvel (MDM) para gerenciar seus dispositivos, você pode usar o Microsoft Intune. Ao trabalhar com qualquer provedor de MDM, incluindo o Intune, os dispositivos estão "inscritos". Quando registrados, eles recebem os recursos e configurações que você configura. 

No Intune, há algumas maneiras de registrar seus dispositivos do iOS/iPadOS e Android. Você pode escolher a opção de registro que funciona melhor para a sua organização. Para obter mais informações e orientações, consulte os seguintes artigos:

- [Guia de implantação: registrar dispositivos iOS e iPadOS no Microsoft Intune](/mem/intune/fundamentals/deployment-guide-enrollment-ios-ipados)
- [Guia de implantação: registrar dispositivos Android no Microsoft Intune](/mem/intune/fundamentals/deployment-guide-enrollment-android)

Se você estiver pronto para usar o Intune para gerenciamento de dispositivos e quiser algumas diretrizes, as seguintes informações podem ajudar:

- [Visão geral do gerenciamento de dispositivos](/mem/intune/fundamentals/what-is-device-management)
- [Tutorial: o Intune passo a passo no Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)
- [Guia de implantação: configurar ou mover para o Microsoft Intune](/mem/intune/fundamentals/deployment-guide-intune-setup)

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a>Fase 3: gerenciar seus dispositivos iOS e Android remotamente

O Microsoft Intune fornece o recurso de bloqueio remoto e redefinição de senha. Se alguém perder o dispositivo, você poderá bloquear o dispositivo remotamente. Se alguém esquecer sua senha, você poderá redefini-la remotamente.

- Para bloquear remotamente um dispositivo iOS/iPadOS ou Android, consulte [remotamente bloquear dispositivos com o Intune](/mem/intune/remote-actions/device-remote-lock).
- Para redefinir a senha remotamente, confira [redefinir ou remover uma senha de dispositivo no Intune](/mem/intune/remote-actions/device-passcode-reset).

Para tarefas adicionais que você pode executar remotamente, consulte [Available Device Actions](/mem/intune/remote-actions/device-management#available-device-actions).
    
## <a name="next-step"></a>Próxima etapa

Explore recursos de [Gerenciamento de dispositivos móveis](m365-enterprise-test-lab-guides.md#mobile-device-management) e recursos adicionais em seu ambiente de teste.

## <a name="see-also"></a>Confira também

[Guias do Laboratório de Teste do Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)
  
[Políticas de conformidade de dispositivo para seu ambiente de teste do Microsoft 365 for Enterprise](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[Visão geral do Microsoft 365 para empresas](microsoft-365-overview.md)
