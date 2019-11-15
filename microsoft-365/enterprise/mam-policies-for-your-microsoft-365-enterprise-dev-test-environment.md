---
title: Políticas de conformidade de dispositivo para seu ambiente de teste do Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/14/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Use este guia de laboratório de teste para adicionar políticas de conformidade de dispositivo do Intune ao seu ambiente de teste do Microsoft 365 Enterprise.
ms.openlocfilehash: dbe0592dfcac7090da194c85db8e788e8e64a0e7
ms.sourcegitcommit: 2c2248b03f7753d64490f2f7e56ec644a235b65a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2019
ms.locfileid: "38639801"
---
# <a name="device-compliance-policies-for-your-microsoft-365-enterprise-test-environment"></a>Políticas de conformidade de dispositivo para seu ambiente de teste do Microsoft 365 Enterprise

Com as instruções deste artigo, você adiciona uma política de conformidade de dispositivo do Intune ao seu ambiente de teste do Microsoft 365 Enterprise.

![Guias de laboratório de teste da Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Clique [aqui](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para ver um mapa visual de todos os artigos da pilha do Guia de Laboratório de Teste do Microsoft 365 Enterprise.

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

3. Na guia portal do Azure no navegador, no painel de navegação, clique em **todos os serviços**, digite **Intune**e clique em **Intune**.
    
4. Se você vir uma mensagem de **Gerenciamento de dispositivo que ainda não tenha sido habilitada** na lâmina do **Microsoft Intune** , clique nela. Na folha **autoridade de gerenciamento de dispositivo móvel** , clique em **autoridade MDM do Intune**e, em seguida, clique em **escolher**. Atualize a guia do navegador.
    
5. No painel de navegação à esquerda, clique em **Grupos**.
    
6. Na folha **grupos-todos os grupos** , clique em **+ novo grupo**.
    
7. Na folha **grupo** , selecione **Office 365** ou **segurança** para **tipo de grupo?**, digite **usuários do dispositivo gerenciados do Windows 10** em **nome**, selecione **atribuído** em **tipo de associação**e clique em **criar**. 
    
8. Feche a folha **Grupo**.
    
11. Feche a folha **grupos-todos os grupos** .
    
12. Na folha do **Microsoft Intune** , na lista **tarefas rápidas** , clique em **criar uma política de conformidade**.
    
13. Na folha **Perfis de Políticas de Conformidade**, clique em **Criar Política**.
    
14. Na folha **criar política** , em **nome**, digite **Windows 10**. Em **plataforma**, selecione **Windows 10 e posterior**, clique em **OK** na folha de **política de conformidade do Windows 10** e, em seguida, clique em **criar**. Feche a lâmina do **Windows 10** .
    
15. Na folha **perfis de política de conformidade** , clique no nome da política do **Windows 10** .
    
16. Na folha **Windows 10** , clique em **atribuições**e clique em **Selecionar grupos para incluir**.
    
17. Na folha **Selecionar grupos para incluir** , clique no grupo **usuários do dispositivo gerenciado do Windows 10** e clique em **selecionar**.
    
18. Clique em **salvar**e feche a folha **Windows 10-atribuições** .
    
19. Feche a folha **Perfis de Políticas de Conformidade**.
    
20. Na folha do **Microsoft Intune** , clique em **aplicativos cliente** no painel de navegação à esquerda.
    
21. Na folha **aplicativos cliente** , clique em **aplicativos**e, em seguida, clique em **Adicionar**. 

22. Na folha **Adicionar aplicativo** , selecione **tipo de aplicativo**e, em seguida, selecione **Windows 10** no **pacote do Office 365**.

23. Clique em **Configurar pacote de aplicativos**e, em seguida, clique em **OK**.

24. Clique em **informações do pacote de aplicativos**, digite aplicativos do **Office para Windows 10** no **nome do pacote**, **aplicativos do Office para Windows 10** descrição do **pacote**e clique em **OK**.

25. Clique **em configurações do pacote de aplicativos**, selecione **semestral** no **canal de atualização**e clique em **OK**.

26. Na folha **Adicionar aplicativo** , clique em **Adicionar**.

Agora você tem uma política de conformidade de dispositivo para testar os aplicativos selecionados na política de conformidade de dispositivo do **Windows 10** e para os membros do grupo de **usuários de dispositivos gerenciados do Windows 10** . Observe que a seleção do Office 365 como o tipo de grupo criará recursos adicionais. 
  
## <a name="next-step"></a>Próxima etapa

Explore recursos de [Gerenciamento de dispositivos móveis](m365-enterprise-test-lab-guides.md#mobile-device-management) e recursos adicionais em seu ambiente de teste.

## <a name="see-also"></a>Confira também

[Guias de laboratório de teste do Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md).
  
[Registrar dispositivos iOS e Android em seu ambiente de teste do Microsoft 365 Enterprise](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[Implantar o Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Enterprise Mobility + Security (EMS)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
