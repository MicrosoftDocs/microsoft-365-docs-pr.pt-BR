---
title: Políticas de conformidade de dispositivo para seu ambiente de teste do Microsoft 365 for Enterprise
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
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Use este guia de laboratório de teste para adicionar políticas de conformidade de dispositivo do Intune ao seu ambiente de teste do Microsoft 365 for Enterprise.
ms.openlocfilehash: d42c9a603ca581941cb5a8f30b9ecd9d6f780759
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367090"
---
# <a name="device-compliance-policies-for-your-microsoft-365-for-enterprise-test-environment"></a>Políticas de conformidade de dispositivo para seu ambiente de teste do Microsoft 365 for Enterprise

*Este guia de laboratório de teste só pode ser usado para o Microsoft 365 para ambientes de teste corporativos.*

Este artigo descreve como adicionar uma política de conformidade de dispositivo do Intune para dispositivos Windows 10 e aplicativos da Microsoft 365 para empresas ao seu ambiente de teste do Microsoft 365 para empresas.

A adição de uma política de conformidade de dispositivo do Intune envolve duas fases:
- [Fase 1: desenvolver seu ambiente de teste do Microsoft 365 for Enterprise](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: criar uma política de conformidade de dispositivo para dispositivos Windows 10](#phase-2-create-a-device-compliance-policy-for-windows-10-devices)

![Guias de Laboratório de Teste do Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Para obter um mapa Visual para todos os artigos da pilha do guia do laboratório de teste do Microsoft 365 for Enterprise, vá para a [pilha do guia do laboratório de teste da microsoft 365 para empresas](../downloads/Microsoft365EnterpriseTLGStack.pdf).

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: desenvolver seu ambiente de teste do Microsoft 365 for Enterprise

Se você quiser configurar as políticas de MAM de forma simples com os requisitos mínimos, siga as instruções em [configuração básica leve](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Se você quiser configurar as políticas de MAM em uma empresa simulada, siga as instruções em [autenticação de passagem](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Testar o licenciamento automatizado e a associação de grupo não requer o ambiente de teste corporativo simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para uma floresta dos serviços de domínio Active Directory (AD DS). Ele é fornecido aqui como uma opção para que você possa testar o licenciamento e a associação de grupo automatizados e experimentá-lo em um ambiente que representa uma organização típica.
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a>Fase 2: criar uma política de conformidade de dispositivo para dispositivos Windows 10

Nesta fase, você cria uma política de conformidade de dispositivo para dispositivos Windows 10. Esta fase usa o Microsoft Intune e o [centro de administração do gerente de ponto de extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431) para adicionar um grupo e criar uma política de conformidade.

1. Vá para o [centro de administração do microsoft 365](https://admin.microsoft.com)e entre na sua assinatura de laboratório de teste do Microsoft 365 com sua conta de administrador global. Selecione o centro de administração do **Gerenciador de pontos de extremidade** . O [centro de administração do Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) é aberto.

    Se uma mensagem semelhante à **que você ainda não habilitou o gerenciamento de dispositivos** for exibida, selecione o Intune como autoridade de MDM. Para obter as etapas específicas, consulte [set the Mobile Device Management Authority](/mem/intune/fundamentals/mdm-authority-set).

    O centro de administração do Endpoint Manager enfoca o gerenciamento de dispositivos e o gerenciamento de aplicativos. Para obter um tour desse centro de administração, consulte [tutorial: passo a passo do Intune no Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager).

2. Em **grupos**, adicione um novo **Microsoft 365** ou grupo de **segurança** chamado **usuários gerenciados do dispositivo Windows 10**, com um tipo de associação **atribuído** . Nas próximas etapas, você atribuirá sua política de conformidade a esse grupo. 

    Para obter as etapas específicas e informações sobre o **Microsoft 365** ou grupos de **segurança** , consulte [Add groups to organizar Users and Devices](/mem/intune/fundamentals/groups-add).

3. Em **dispositivos**, crie uma política de conformidade do Windows 10. Atribua essa política ao grupo de **usuários do dispositivo do Windows 10 gerenciado** que você criou.

    Em sua política, você pode bloquear senhas simples, exigir um firewall, exigir que o serviço Microsoft Defender Antimalware esteja em execução e muito mais. Uma política de conformidade normalmente inclui as configurações básicas ou o mínimo que cada dispositivo deve ter.

    Para obter as etapas específicas e obter informações sobre as configurações de conformidade disponíveis que você pode configurar, consulte [usar políticas de conformidade para definir regras para dispositivos que você gerencia](/mem/intune/protect/device-compliance-get-started).

Quando terminar, você tem uma política de conformidade de dispositivo para testar Membros no grupo de **usuários de dispositivos gerenciados do Windows 10** .
  
## <a name="next-step"></a>Próxima etapa

Explore recursos de [Gerenciamento de dispositivos móveis](m365-enterprise-test-lab-guides.md#mobile-device-management) e recursos adicionais em seu ambiente de teste.

## <a name="see-also"></a>Também consulte

[Guias de laboratório de teste do Microsoft 365 for Enterprise](m365-enterprise-test-lab-guides.md).
  
[Registrar dispositivos iOS e Android em seu ambiente de teste do Microsoft 365 for Enterprise](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[Visão geral do Microsoft 365 para empresas](microsoft-365-overview.md)

[Enterprise Mobility + Security (EMS)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
