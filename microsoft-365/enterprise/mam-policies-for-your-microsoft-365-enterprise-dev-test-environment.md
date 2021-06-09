---
title: Políticas de conformidade de dispositivos para seu Microsoft 365 para ambiente de teste empresarial
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
description: Use este Guia de Laboratório de Teste para adicionar políticas de conformidade de dispositivo do Intune ao seu Microsoft 365 para ambiente de teste empresarial.
ms.openlocfilehash: d42c9a603ca581941cb5a8f30b9ecd9d6f780759
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367090"
---
# <a name="device-compliance-policies-for-your-microsoft-365-for-enterprise-test-environment"></a>Políticas de conformidade de dispositivos para seu Microsoft 365 para ambiente de teste empresarial

*Este Guia de Laboratório de Teste só pode ser usado para Microsoft 365 ambientes de teste corporativos.*

Este artigo descreve como adicionar uma política de conformidade de dispositivo Intune para dispositivos Windows 10 e Microsoft 365 Apps para Grandes Empresas ao seu Microsoft 365 para ambiente de teste corporativo.

A adição de uma política de conformidade de dispositivo do Intune envolve duas fases:
- [Fase 1: criar seu Microsoft 365 para ambiente de teste empresarial](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: Criar uma política de conformidade de dispositivo para Windows 10 dispositivos](#phase-2-create-a-device-compliance-policy-for-windows-10-devices)

![Guias de Laboratório de Teste do Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Para um mapa visual de todos os artigos na pilha Microsoft 365 guia do laboratório de teste empresarial, vá para o Microsoft 365 para a pilha de guias de laboratório [de teste corporativos.](../downloads/Microsoft365EnterpriseTLGStack.pdf)

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: criar seu Microsoft 365 para ambiente de teste empresarial

Se você quiser configurar as políticas de MAM de forma leve com os requisitos mínimos, siga as instruções em [Configuração base leve.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
Se você quiser configurar políticas de MAM em uma empresa simulada, siga as instruções em [Autenticação passagem](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Testar o licenciamento automatizado e a associação ao grupo não exige o ambiente de teste empresarial simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para uma floresta dos Serviços de Domínio do Active Directory (AD DS). Ele é fornecido aqui como uma opção para que você possa testar o licenciamento automatizado e a associação ao grupo e experimentá-lo em um ambiente que representa uma organização típica.
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a>Fase 2: Criar uma política de conformidade de dispositivo para Windows 10 dispositivos

Nesta fase, você cria uma política de conformidade de dispositivo para Windows 10 dispositivos. Essa fase usa Microsoft Intune e o Microsoft Endpoint Manager [de](https://go.microsoft.com/fwlink/?linkid=2109431) administração para adicionar um grupo e criar uma política de conformidade.

1. Vá para o [Microsoft 365 de](https://admin.microsoft.com)administração e entre na assinatura do laboratório de Microsoft 365 de teste com sua conta de administrador global. Selecione o **Endpoint Manager** de administração. O [Endpoint Manager de administração é](https://go.microsoft.com/fwlink/?linkid=2109431) aberto.

    Se uma mensagem semelhante a **You haven't enabled device management** yet message for mostrada, selecione Intune como a autoridade MDM. Para as etapas específicas, consulte Definir a autoridade de gerenciamento [de dispositivo móvel](/mem/intune/fundamentals/mdm-authority-set).

    O Endpoint Manager de administração se concentra no gerenciamento de dispositivos e no gerenciamento de aplicativos. Para ver um tour pelo centro de administração, consulte Tutorial: Passo a [passo do Intune no Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager).

2. Em **Grupos**, adicione um novo **Microsoft 365** ou **grupo** de segurança chamado **Usuários** de dispositivos gerenciados Windows 10 , com um **tipo de** associação Atribuído. Nas próximas etapas, você atribuirá sua política de conformidade a esse grupo. 

    Para obter as etapas específicas e para obter informações sobre Microsoft 365 **ou** **grupos de** segurança, consulte Adicionar grupos para organizar usuários [e dispositivos.](/mem/intune/fundamentals/groups-add)

3. Em **Dispositivos**, crie uma Windows 10 de conformidade. Atribua essa política ao **grupo De Windows 10 de dispositivos gerenciados** que você criou.

    Em sua política, você pode bloquear senhas simples, exigir um firewall, exigir que o serviço Microsoft Defender Antimalware seja executado e muito mais. Uma política de conformidade normalmente inclui as configurações base ou o mínimo que cada dispositivo deve ter.

    Para obter as etapas específicas e para obter informações sobre as configurações de conformidade disponíveis que você pode configurar, consulte Usar políticas de conformidade para definir regras para dispositivos [que você gerencia](/mem/intune/protect/device-compliance-get-started).

Quando terminar, você terá uma política de conformidade de dispositivo para testar membros no grupo Usuários Windows 10 **dispositivos** gerenciados.
  
## <a name="next-step"></a>Próxima etapa

Explore recursos e [recursos adicionais de gerenciamento](m365-enterprise-test-lab-guides.md#mobile-device-management) de dispositivo móvel em seu ambiente de teste.

## <a name="see-also"></a>Confira também

[Microsoft 365 para guias de laboratório de teste corporativos.](m365-enterprise-test-lab-guides.md)
  
[Registrar dispositivos iOS e Android em seu Microsoft 365 para ambiente de teste empresarial](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[Visão geral do Microsoft 365 para empresas](microsoft-365-overview.md)

[Enterprise Mobility + Security (EMS)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
