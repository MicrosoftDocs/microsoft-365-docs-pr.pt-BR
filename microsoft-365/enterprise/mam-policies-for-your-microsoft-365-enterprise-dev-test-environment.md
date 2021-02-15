---
title: Políticas de conformidade do dispositivo para o ambiente de teste do Microsoft 365 para empresas
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
description: Use este Guia de Laboratório de Teste para adicionar políticas de conformidade de dispositivos do Intune ao seu ambiente de teste do Microsoft 365 para empresas.
ms.openlocfilehash: d42c9a603ca581941cb5a8f30b9ecd9d6f780759
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367090"
---
# <a name="device-compliance-policies-for-your-microsoft-365-for-enterprise-test-environment"></a>Políticas de conformidade do dispositivo para o ambiente de teste do Microsoft 365 para empresas

*Este Guia de Laboratório de Teste só pode ser usado para o Microsoft 365 para ambientes de teste corporativos.*

Este artigo descreve como adicionar uma política de conformidade de dispositivo do Intune para dispositivos Windows 10 e aplicativos do Microsoft 365 para empresas ao seu ambiente de teste do Microsoft 365 para empresas.

A adição de uma política de conformidade de dispositivo do Intune envolve duas fases:
- [Fase 1: Criar seu ambiente de teste do Microsoft 365 para empresas](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: Criar uma política de conformidade do dispositivo para dispositivos Windows 10](#phase-2-create-a-device-compliance-policy-for-windows-10-devices)

![Guias de Laboratório de Teste do Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Para ver um mapa visual de todos os artigos da pilha do Guia de Laboratório de Teste do Microsoft 365 para empresas, vá para a Pilha de Guias de Laboratório de Teste do [Microsoft 365](../downloads/Microsoft365EnterpriseTLGStack.pdf)para empresas.

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: Criar seu ambiente de teste do Microsoft 365 para empresas

Se você quiser configurar políticas de MAM de uma maneira simples com os requisitos mínimos, siga as instruções na configuração [de base leve.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
Se você quiser configurar políticas de MAM em uma empresa simulada, siga as instruções na [autenticação de passagem.](pass-through-auth-m365-ent-test-environment.md)
  
> [!NOTE]
> O teste automatizado de licenciamento e associação de grupo não exige o ambiente de teste corporativo simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para uma floresta do AD DS (Serviços de Domínio Active Directory). Ele é fornecido aqui como uma opção para que você possa testar o licenciamento automatizado e a associação a um grupo e fazer testes com ele em um ambiente que representa uma organização típica.
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a>Fase 2: Criar uma política de conformidade do dispositivo para dispositivos Windows 10

Nesta fase, você cria uma política de conformidade de dispositivos para dispositivos Windows 10. Esta fase usa o Microsoft Intune e o centro de administração do [Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) para adicionar um grupo e criar uma política de conformidade.

1. Vá para o Centro de administração do [Microsoft 365](https://admin.microsoft.com)e entre em sua assinatura de laboratório de teste do Microsoft 365 com sua conta de administrador global. Selecione o **centro de administração do Endpoint Manager.** O [centro de administração do Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) é aberto.

    Se uma mensagem semelhante a **Você ainda** não habilitar o gerenciamento de dispositivos for mostrada, selecione Intune como a autoridade MDM. Para as etapas específicas, consulte [Definir a autoridade de gerenciamento de dispositivo móvel.](/mem/intune/fundamentals/mdm-authority-set)

    O centro de administração do Endpoint Manager se concentra no gerenciamento de dispositivos e no gerenciamento de aplicativos. Para um tour por este centro de administração, confira Tutorial: Passo a passo [do Intune no Microsoft Endpoint Manager.](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)

2. Em **Grupos,** adicione um novo Grupo  de Segurança ou **Microsoft 365** chamado usuários de dispositivos Gerenciados **do Windows 10,** com um tipo **de** associação atribuído. Nas próximas etapas, você atribuirá sua política de conformidade a esse grupo. 

    Para obter as etapas específicas e obter informações sobre o **Microsoft 365** ou grupos de **segurança,** confira Adicionar grupos para organizar usuários [e dispositivos.](/mem/intune/fundamentals/groups-add)

3. Em **Dispositivos,** crie uma política de conformidade do Windows 10. Atribua essa política ao grupo **de usuários de dispositivos Gerenciados do Windows 10** que você criou.

    Em sua política, você pode bloquear senhas simples, exigir um firewall, exigir que o serviço microsoft Defender Antimalware seja executado e muito mais. Uma política de conformidade normalmente inclui as configurações básicas ou o mínimo que cada dispositivo deve ter.

    Para obter as etapas específicas e obter informações sobre as configurações de conformidade disponíveis que você pode configurar, consulte Usar políticas de conformidade para definir regras para dispositivos [que você gerencia.](/mem/intune/protect/device-compliance-get-started)

Quando terminar, você terá uma política de conformidade do dispositivo para testar membros no grupo de usuários de **dispositivos Windows 10 gerenciados.**
  
## <a name="next-step"></a>Próxima etapa

Explore recursos [adicionais de gerenciamento de](m365-enterprise-test-lab-guides.md#mobile-device-management) dispositivos móveis em seu ambiente de teste.

## <a name="see-also"></a>Confira também

Guias de laboratório de teste do [Microsoft 365 para empresas.](m365-enterprise-test-lab-guides.md)
  
[Registrar dispositivos iOS e Android no ambiente de teste do Microsoft 365 para empresas](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[Visão geral do Microsoft 365 para empresas](microsoft-365-overview.md)

[Enterprise Mobility + Security (EMS)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
