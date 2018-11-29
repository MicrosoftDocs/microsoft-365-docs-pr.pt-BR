---
title: Políticas MAM para o ambiente de teste do Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/16/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Use este guia de laboratório de teste para adicionar o ambiente de teste de políticas de gerenciamento (MAM) de aplicativo móvel do Intune para sua empresa de 365 da Microsoft.
ms.openlocfilehash: f00379a5e70dce5e07c031a7647b27041d3fa9d1
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865308"
---
# <a name="mam-policies-for-your-microsoft-365-enterprise-test-environment"></a>Políticas MAM para o ambiente de teste do Microsoft 365 Enterprise

Com as instruções deste artigo, você adicionar o ambiente de teste de políticas de gerenciamento (MAM) de aplicativo móvel do Intune para sua empresa de 365 da Microsoft.

![Guias de Laboratório de Teste do Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Clique [aqui](https://aka.ms/m365etlgstack) para ver um mapa visual de todos os artigos da pilha do Guia de Laboratório de Teste do Microsoft 365 Enterprise.

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: Criar o seu ambiente de teste do Microsoft 365 Enterprise

Se você deseja configurar políticas MAM de forma leve com os requisitos mínimos, siga as instruções na [configuração base leve](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Se você deseja configurar políticas MAM em uma empresa simulada, siga as instruções na [autenticação de passagem](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Testando automatizada de licenciamento e a associação de grupo não requer o ambiente de teste de simulado empresarial, que inclui uma intranet simulada conectada à Internet e a sincronização de diretório para uma floresta do Windows Server AD. Ele é fornecido aqui como uma opção para que você possa testar automatizada de licenciamento e a associação ao grupo e experimentar em um ambiente que representa uma organização típica. 
>  

## <a name="phase-2-create-and-deploy-mam-policies-for-ios-and-android-devices"></a>Fase 2: Criar e implantar políticas de MAM para dispositivos iOS e Android

Nesta fase, você criará e implantará duas políticas de MAM diferentes: uma para dispositivos iOS e outra para dispositivos Android.
  
1. Vá para o portal do Office 365 em ([https://portal.office.com](https://portal.office.com)) e se conectar à sua assinatura de avaliação do Office 365 com sua conta de administrador global.
    
2. Em uma nova guia do navegador, abra o portal do Windows Azure em [https://portal.azure.com](https://portal.azure.com).

3. Na guia Azure portal no Internet Explorer, no painel de navegação, clique em **todos os serviços**, digite **Intune**e, em seguida, clique em **Intune**.
    
4. Se você vir uma mensagem que **você não ativou o gerenciamento de dispositivos ainda** no **Microsoft Intune** blade, clique nele. No blade **autoridade de gerenciamento de dispositivos móveis** , clique em **Intune MDM autoridade**e, em seguida, clique em **Escolher**. Atualize o seu guia de navegador.
    
5. No painel de navegação à esquerda, clique em **Grupos**.
    
6. No blade **grupos-All grupos** , clique em **+ novo grupo**.
    
7. No **grupo** blade, selecione **Office 365** para **tipo de grupo?**, digite **gerenciados iOS usuários de dispositivo** em **nome**, selecione **atribuído** no **tipo de associação**e, em seguida, clique em **criar**. 
    
8. Feche a folha **Grupo**.
    
9. No blade **grupos-All grupos** , clique em **Adicionar**.
    
10. No **grupo** blade, selecione **Office 365** para **tipo de grupo?**, digite **gerenciados Android usuário de dispositivo** em **nome**, selecione **atribuído** no **tipo de associação**e, em seguida, clique em **criar**.
    
11. Feche o blade **grupos grupos a todos** .
    
12. Na folha **Intune**, na lista **Tarefas rápidas**, clique em **Crie uma política de conformidade**.
    
13. Na folha **Perfis de Políticas de Conformidade**, clique em **Criar Política**.
    
14. Na folha **Criar Política**, em **Nome**, digite **iOS**. Em **Plataforma**, selecione **iOS**, clique em **OK** na folha **Política de conformidade do iOS** e depois clique em **Criar**.
    
15. Na folha **Perfis de Políticas de Conformidade**, clique em **Criar Política**.
    
16. Na folha **Criar Política**, em **Nome**, digite **Android**. Em **Plataforma**, selecione **Android**, clique em **OK** na folha **Política de conformidade do Android** e depois clique em **Criar**.
    
17. Na folha **Perfis de Políticas de Conformidade**, clique no nome da política **Android**.
    
18. Na navegação à esquerda da folha **Android - Propriedades**, clique em **Atribuições** e depois em **Grupos selecionados**.
    
19. Na folha **Grupos selecionados**, clique no grupo **Usuários de dispositivos Android gerenciados** e depois clique em **Selecionar**.
    
20. Clique em **Salvar**e feche o blade **Android - atribuições** .
    
21. Na folha **Perfis de Políticas de Conformidade**, clique no nome da política **iOS**.
    
22. Na navegação à esquerda da folha **iOS - Propriedades**, clique em **Atribuições** e depois em **Grupos selecionados**.
    
23. Na folha **Grupos selecionados**, clique no grupo **Usuários de dispositivos iOS gerenciados** e depois clique em **Selecionar**.
    
24. Clique em **Salvar**e feche o blade **iOS - atribuições** .
    
25. Feche a folha **Perfis de Políticas de Conformidade**.
    
26. Na folha **Intune**, clique em **Gerenciar aplicativos** na navegação à esquerda.
    
27. Na folha **Aplicativos Móveis**, clique em **Aplicativos**.
    
28. Na lista de aplicativos, clique em **PowerPoint**,  
    
29. Na folha **Visão Geral do PowerPoint**, clique em **Atribuições > Selecionar grupos > Dispositivos iOS gerenciados > Selecionar**. Em **Tipo**, selecione **Disponível** e clique em **Salvar**.
    
30. Repita a etapa 29 para os seguintes aplicativos:
    
    - Outlook para Android
    
    - Word para iOS
    
    - Excel para iOS
    
    - Outlook para iOS
    
    - Microsoft Dynamics CRM no iPad para iOS
    
    - Microsoft Dynamics CRM no iPhone para iOS
    
    - Dynamics CRM para Telefones para Android
    
    - Dynamics CRM para Tablets para Android
    
    - Excel para Android
    
    - Word para Android
    
    - OneNote para iOS
    
31. Feche a folha **Aplicativos Móveis - Aplicativos**.
    
32. Na folha **Aplicativos Móveis**, clique em **Políticas de Proteção de Aplicativo**.
    
33. Na folha **Políticas de Proteção de Aplicativo**, clique em **Adicionar uma política**.
    
34. Na folha **Adicionar uma política**, digite **iOS** e clique em **Selecionar aplicativos necessários**.
    
35. Na folha **Aplicativos**, clique em **PowerPoint**, **Microsoft Dynamics CRM no iPhone**, **Excel**, **Microsoft Dynamics CRM no iPhone**, **Word**, **OneNote** e **Outlook** e depois clique em **Selecionar**.
    
36. Na folha **Adicionar uma política**, clique em **Criar**.
    
37. Na folha **Políticas de Proteção de Aplicativo**, clique em **Adicionar uma política**.
    
38. Na folha **Adicionar uma política**, digite **Android**, selecione **Android** em **Plataforma** e clique em **Selecionar aplicativos necessários**.
    
39. Na folha **Aplicativos**, clique em **PowerPoint**, **Dynamics CRM para tablets**, **Excel**, **Word**, **Outlook** e **Dynamics CRM para telefones**. Em seguida, clique em **Selecionar**.
    
40. Na folha **Adicionar uma política**, clique em **Criar**.
    
Agora, você tem duas políticas de MAM, uma para dispositivos iOS e outra para dispositivos Android, e está pronto para trabalhar com configurações de teste para os aplicativos selecionados. 
  
## <a name="next-step"></a>Próxima etapa

Explore recursos adicionais de [gerenciamento de dispositivos móveis](m365-enterprise-test-lab-guides.md#mobile-device-management) e capacidades no seu ambiente de teste.

## <a name="see-also"></a>Confira também

[Guias de laboratório de teste do Microsoft Enterprise 365](m365-enterprise-test-lab-guides.md).
  
[Registre dispositivos iOS e Android em seu ambiente de teste do Microsoft 365 Enterprise](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[Implantar o Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Mobilidade corporativos + segurança (EMS)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
