---
title: Ambiente de teste de políticas de conformidade do dispositivo para a sua empresa de 365 da Microsoft
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/14/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Use este guia de laboratório de teste para adicionar o ambiente de teste de políticas de conformidade do dispositivo Intune para sua empresa de 365 da Microsoft.
ms.openlocfilehash: 1d957c5cdc888251224bbca43fe82ab0a15e7a93
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2019
ms.locfileid: "26865308"
---
# <a name="device-compliance-policies-for-your-microsoft-365-enterprise-test-environment"></a>Ambiente de teste de políticas de conformidade do dispositivo para a sua empresa de 365 da Microsoft

Com as instruções deste artigo, você pode adicionar uma política de conformidade do dispositivo Intune ao seu ambiente de teste do Microsoft 365 Enterprise.

![Guias de laboratório de teste da Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Clique [aqui](https://aka.ms/m365etlgstack) para ver um mapa visual de todos os artigos da pilha do Guia de Laboratório de Teste do Microsoft 365 Enterprise.

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: Criar o seu ambiente de teste do Microsoft 365 Enterprise

Se você deseja configurar políticas MAM de forma leve com os requisitos mínimos, siga as instruções na [configuração base leve](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Se você deseja configurar políticas MAM em uma empresa simulada, siga as instruções na [autenticação de passagem](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Testando automatizada de licenciamento e a associação de grupo não requer o ambiente de teste de simulado empresarial, que inclui uma intranet simulada conectada à Internet e a sincronização de diretório para uma floresta do Windows Server AD. Ele é fornecido aqui como uma opção para que você possa testar automatizada de licenciamento e a associação ao grupo e experimentar em um ambiente que representa uma organização típica. 
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a>Fase 2: Criar uma política de conformidade do dispositivo para dispositivos Windows 10

Nesta fase, você deve criar uma política de conformidade do dispositivo para dispositivos Windows 10.
  
1. Vá para o portal do Office em ([https://office.com](https://office.com)) e se conectar à sua assinatura de avaliação do Office 365 com sua conta de administrador global.
    
2. Em uma nova guia do navegador, abra o portal do Windows Azure em [https://portal.azure.com](https://portal.azure.com).

3. Na guia portal Azure no seu navegador, no painel de navegação, clique em **todos os serviços**, digite **Intune**e, em seguida, clique em **Intune**.
    
4. Se você vir uma mensagem que **você não ativou o gerenciamento de dispositivos ainda** no **Microsoft Intune** blade, clique nele. No blade **autoridade de gerenciamento de dispositivos móveis** , clique em **Intune MDM autoridade**e, em seguida, clique em **Escolher**. Atualize o seu guia de navegador.
    
5. No painel de navegação à esquerda, clique em **Grupos**.
    
6. No blade **grupos-All grupos** , clique em **+ novo grupo**.
    
7. No **grupo** blade, selecione **Office 365** para **tipo de grupo?**, digite **gerenciados Windows 10 usuários de dispositivo** em **nome**, selecione **atribuído** no **tipo de associação**e, em seguida, clique em **criar**. 
    
8. Feche a folha **Grupo**.
    
11. Feche o blade **grupos grupos a todos** .
    
12. No **Microsoft Intune** blade, na lista de **Tarefas rápidas** , clique em **criar uma política de conformidade**.
    
13. Na folha **Perfis de Políticas de Conformidade**, clique em **Criar Política**.
    
14. No blade **Criar política** , em **nome**, digite **Windows 10**. Na **plataforma**, selecione **Windows 10 e posterior**, clique **Okey** no blade **política de conformidade do Windows 10** e, em seguida, clique em **criar**. Feche o blade **Windows 10** .
    
15. No blade **Perfis de política de conformidade** , clique no nome de política do **Windows 10** .
    
16. No **Windows 10** blade, clique em **atribuições**e clique em **Selecionar grupos a serem incluídos**.
    
17. No blade **Selecionar grupos a serem incluídos** , clique no grupo de **usuários de dispositivos gerenciados Windows 10** e, em seguida, clique em **Selecionar**.
    
18. Clique em **Salvar**e feche o blade **Windows 10 - atribuições** .
    
19. Feche a folha **Perfis de Políticas de Conformidade**.
    
20. No **Microsoft Intune** blade, clique em **aplicativos cliente** no painel de navegação à esquerda.
    
21. No blade **Aplicativos de cliente** , clique em **aplicativos**e, em seguida, clique em **Adicionar**. 

22. No blade **app adicionar** , selecione **o tipo de aplicativo**e selecione **10 do Windows** em um **Pacote do Office 365**.

23. Clique em **Configurar pacote de aplicativo**e, em seguida, clique em **Okey**.

24. Clique em **Informações do pacote de aplicativo**, digite **Office Apps for Windows 10** em **Nome do pacote**, **aplicativos do Office para o Windows 10** na **Descrição do pacote**e clique em **Okey**.

25. Clique em **Configurações de pacote do App**, selecione **delimitadas anual** no **canal de atualização**e, em seguida, clique em **Okey**.

26. No blade **Add app** , clique em **Adicionar**.

Agora você tem uma política de conformidade do dispositivo para testar os aplicativos selecionados na política de conformidade do dispositivo do **Windows 10** e para membros do grupo **usuários de dispositivos gerenciados Windows 10** . 
  
## <a name="next-step"></a>Próxima etapa

Explore recursos adicionais de [gerenciamento de dispositivos móveis](m365-enterprise-test-lab-guides.md#mobile-device-management) e capacidades no seu ambiente de teste.

## <a name="see-also"></a>Confira também

[Guias de laboratório de teste do Microsoft Enterprise 365](m365-enterprise-test-lab-guides.md).
  
[Registre dispositivos iOS e Android em seu ambiente de teste do Microsoft 365 Enterprise](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[Implantar o Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Mobilidade corporativos + segurança (EMS)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
