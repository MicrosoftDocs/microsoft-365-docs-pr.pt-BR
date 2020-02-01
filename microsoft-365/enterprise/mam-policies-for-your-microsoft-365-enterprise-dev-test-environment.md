---
title: Políticas de conformidade de dispositivo para seu ambiente de teste do Microsoft 365 Enterprise
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
description: Use este guia de laboratório de teste para adicionar políticas de conformidade de dispositivo do Intune ao seu ambiente de teste do Microsoft 365 Enterprise.
ms.openlocfilehash: f5d258dd9b4e0ff8799534cce64818a7fdaf663e
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600898"
---
# <a name="device-compliance-policies-for-your-microsoft-365-enterprise-test-environment"></a>Políticas de conformidade de dispositivo para seu ambiente de teste do Microsoft 365 Enterprise

*Este Guia de Laboratório de Testes pode ser usado apenas em ambientes de teste do Microsoft 365 Enterprise.*

Com as instruções deste artigo, você adiciona uma política de conformidade de dispositivo do Intune para dispositivos Windows 10 e Office 365 ProPlus ao seu ambiente de teste do Microsoft 365 Enterprise.

![Guias do Laboratório de Teste do Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Clique [aqui](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para ver um mapa visual de todos os artigos na pilha do Guia do Test Lab do Microsoft 365 Enterprise.

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: Criar o ambiente de teste do Microsoft 365 Enterprise

Se você só quiser configurar as políticas de MAM de forma leve com os requisitos mínimos, siga as instruções em [configuração básica leve](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Se você quiser configurar as políticas de MAM em uma empresa simulada, siga as instruções em [autenticação de passagem](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Testar o licenciamento automatizado e a associação de grupo não requer o ambiente de teste corporativo simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para uma floresta dos serviços de domínio Active Directory (AD DS). Ele é fornecido aqui como uma opção para que você possa testar o licenciamento e a associação de grupo automatizados e experimentá-lo em um ambiente que representa uma organização típica. 
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a>Fase 2: criar uma política de conformidade de dispositivo para dispositivos Windows 10

Nesta fase, você cria uma política de conformidade de dispositivo para dispositivos Windows 10.
  
1. Vá para o portal do Office 365 em[https://portal.office.com](https://portal.office.com)() e entre na sua assinatura de laboratório de teste do Office 365 com sua conta de administrador global.
    
2. Em uma nova guia do navegador, abra o portal do Azure em [https://portal.azure.com](https://portal.azure.com).

3. Na guia portal do Azure no navegador, digite **Intune** na caixa de pesquisa e clique em **Intune**.
    
4. Se você vir uma mensagem de **Gerenciamento de dispositivo ainda não habilitada** no painel do **Microsoft Intune** , clique nela. No painel **autoridade de gerenciamento de dispositivo móvel** , clique em **autoridade MDM do Intune**e, em seguida, clique em **escolher**. Atualize a guia do navegador.
    
5. No painel de navegação à esquerda, clique em **Grupos**.
    
6. No painel **grupos-todos os grupos** , clique em **+ novo grupo**.
    
7. No painel de **grupo** , selecione **Office 365** ou **segurança** para **tipo de grupo?**, digite **usuários do dispositivo gerenciados do Windows 10** em **nome**, selecione **atribuído** em **tipo de associação**e clique em **criar**. 
    
8. Clique em **Microsoft Intune**. No painel do **Microsoft Intune** , na lista **tarefas rápidas** , clique em **criar uma política de conformidade**.
    
9. No painel **perfis de política de conformidade** , clique em **criar política**.
    
10. No painel **criar política** , em **nome**, digite **Windows 10**. Em **plataforma**, selecione **Windows 10 e posterior**, clique em **OK** no painel de **política de conformidade do Windows 10** e, em seguida, clique em **criar**. 
    
11. Clique em **perfis de política de conformidade**e, em seguida, clique no nome da política do **Windows 10** .
    
12. No painel do **Windows 10** , clique em **atribuições**e, em seguida, clique em **Selecionar grupos para incluir**.
    
13. No painel **Selecionar grupos para incluir** , clique no grupo **usuários do dispositivo gerenciado do Windows 10** e clique em **selecionar**.
    
14. Clique em **salvar**, clique em **Microsoft Intune-visão geral**e, em seguida, clique em **aplicativos cliente** no painel de navegação à esquerda.
    
15. No painel **aplicativos cliente** , clique em **aplicativos**e, em seguida, clique em **Adicionar**. 

16. No painel **Adicionar aplicativo** , selecione **tipo de aplicativo**e, em seguida, selecione **Windows 10** no **pacote do Office 365**.

17. No painel **Adicionar aplicativo** , selecione **informações do pacote de aplicativos**.
 
18. No painel de **informações do App Suite** , digite **Office 365 ProPlus** em **nome** e **Descrição**do pacote.
Clique em OK.

19. No painel **Adicionar aplicativo** , selecione **Configurar pacote de aplicativos**e clique em **OK**.

20. No painel **Adicionar aplicativo** , selecione **configurações de pacote de aplicativos**.

21. Em **canal de atualização**, selecione **semestral**e clique em **OK**.

22. No painel **Adicionar aplicativo** , clique em **Adicionar**.

Agora você tem uma política de conformidade de dispositivo para testar os aplicativos selecionados na política de conformidade de dispositivo do **Windows 10** e para os membros do grupo de **usuários de dispositivos gerenciados do Windows 10** . Observe que a seleção do Office 365 como o tipo de grupo criará recursos adicionais. 
  
## <a name="next-step"></a>Próxima etapa

Explore recursos de [Gerenciamento de dispositivos móveis](m365-enterprise-test-lab-guides.md#mobile-device-management) e recursos adicionais em seu ambiente de teste.

## <a name="see-also"></a>Confira também

[Guias de laboratório de teste do Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md).
  
[Registrar dispositivos iOS e Android em seu ambiente de teste do Microsoft 365 Enterprise](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[Implantar o Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Enterprise Mobility + Security (EMS)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
