---
title: Políticas de conformidade de dispositivo para seu ambiente de teste do Microsoft 365 for Enterprise
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
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Use este guia de laboratório de teste para adicionar políticas de conformidade de dispositivo do Intune ao seu ambiente de teste do Microsoft 365 for Enterprise.
ms.openlocfilehash: c1de822e5a97416bd0c672d88f2902d8986638c8
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487407"
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

Nesta fase, crie uma política de conformidade de dispositivo para dispositivos Windows 10.
  
1. Vá para o [centro de administração do microsoft 365](https://admin.microsoft.com) e entre na sua assinatura de laboratório de teste do Microsoft 365 com sua conta de administrador global.
1. Em uma nova guia do navegador, abra o portal do Azure em [https://portal.azure.com](https://portal.azure.com) .
1. Na caixa de pesquisa do portal do Azure, insira o **Intune**e, em seguida, selecione **Intune**.
1. Se você vir uma mensagem de **Gerenciamento de dispositivo ainda não habilitada** no painel do **Microsoft Intune** , selecione-a. No painel **autoridade de gerenciamento de dispositivo móvel** , selecione **autoridade MDM do Intune**e selecione **escolher**.
1. Atualize a guia do navegador.
1. No painel de navegação esquerdo, selecione **grupos**.
1. No painel **grupos-todos os grupos** , selecione **+ novo grupo**.
1. No painel de **grupo** , selecione **Microsoft 365** ou **segurança** para **tipo de grupo?**, insira **usuários do dispositivo gerenciados do Windows 10** em **nome**, selecione **atribuído** em **tipo de associação**e, em seguida, selecione **criar**.
1. Selecione **Microsoft Intune**.
1. No painel do **Microsoft Intune** , na lista **tarefas rápidas** , selecione **criar uma política de conformidade**.
1. No painel **perfis de política de conformidade** , selecione **criar política**.
1. No painel **criar política** , em **nome**, digite **Windows 10**. Em **plataforma**, selecione **Windows 10 e posterior**, selecione **OK** no painel **política de conformidade do Windows 10** e, em seguida, selecione **criar**.
1. Selecione **perfis de política de conformidade**e, em seguida, selecione o nome da política do **Windows 10** .
1. No painel do **Windows 10** , selecione **atribuições**e selecione **grupos para incluir**.
1. No painel **Selecionar grupos para incluir** , selecione o grupo **usuários do dispositivo gerenciado do Windows 10** e selecione **selecionar**.
1. Selecione **salvar**, selecione **Microsoft Intune-visão geral**e, em seguida, selecione **aplicativos cliente** no painel de navegação à esquerda.
1. No painel **aplicativos cliente** , selecione **aplicativos**e, em seguida, selecione **Adicionar**.
1. No painel **Adicionar aplicativo** , selecione **tipo de aplicativo**e, em seguida, selecione **Windows 10** no **Microsoft 365 Suite**.
1. No painel **Adicionar aplicativo** , selecione **informações do pacote de aplicativos**.
1. No painel de **informações do pacote de aplicativos** , digite **Microsoft 365 aplicativos para empresas** em **nome do pacote** e **Descrição do pacote**e, em seguida, selecione **OK**.
1. No painel **Adicionar aplicativo** , selecione **Configurar pacote de aplicativos**e, em seguida, selecione **OK**.
1. No painel **Adicionar aplicativo** , selecione **configurações de pacote de aplicativos**.
1. Em **canal de atualização**, selecione **Enterprise semestral**e, em seguida, selecione **OK**.
1. No painel **Adicionar aplicativo** , selecione **Adicionar**.

Agora você tem uma política de conformidade de dispositivo para testar os aplicativos selecionados na política de conformidade de dispositivo do **Windows 10** e para os membros do grupo de **usuários de dispositivos gerenciados do Windows 10** . Observe que a seleção do **Microsoft 365** como o tipo de grupo cria recursos adicionais.
  
## <a name="next-step"></a>Próxima etapa

Explore recursos de [Gerenciamento de dispositivos móveis](m365-enterprise-test-lab-guides.md#mobile-device-management) e recursos adicionais em seu ambiente de teste.

## <a name="see-also"></a>Confira também

[Guias de laboratório de teste do Microsoft 365 for Enterprise](m365-enterprise-test-lab-guides.md).
  
[Registrar dispositivos iOS e Android em seu ambiente de teste do Microsoft 365 for Enterprise](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[Visão geral do Microsoft 365 para empresas](microsoft-365-overview.md)

[Enterprise Mobility + Security (EMS)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
