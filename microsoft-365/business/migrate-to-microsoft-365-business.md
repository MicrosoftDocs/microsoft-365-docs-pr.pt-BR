---
title: Migrar para o Microsoft 365 Business do Office 365 Business Premium
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 5b4ba843-24b8-4526-8e1f-f9b9eab89d06
description: Saiba como mover sua empresa para o Microsoft 365 Business.
ms.openlocfilehash: 3e45ba13e4cfe772829f545219bf86a9a3317d59
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32285616"
---
# <a name="migrate-to-microsoft-365-business-from-office-365-business-premium"></a>Migrar para o Microsoft 365 Business do Office 365 Business Premium

Se você já tem uma assinatura do Office 365 for Business, por exemplo, o Office 365 Business Premium, é possível adicionar licenças facilmente ao Microsoft 365 Business e atribuí-las a alguns ou todos os usuários.
  
> [!NOTE]
> Você não pode usar o botão [mudar de plano](https://support.office.com/article/73318661-8f33-478b-bcc7-fb8d69dbb22a?.aspx#switchbutton) para atualizar para o Microsoft 365 Business ainda. 
  
## <a name="add-microsoft-365-business-licenses"></a>Adicionar licenças de negócios do Microsoft 365

Você tem duas maneiras de obter o Microsoft 365 Business. Se você tiver um parceiro, ele poderá comprar o Microsoft 365 Business para você pelo [Microsoft Partner Center](get-microsoft-365-business.md). Seu parceiro também pode ajudá-lo a migrar para o Microsoft 365 Business.
  
Se você gerenciar sua própria assinatura, poderá [entrar em contato com a venda](https://www.microsoft.com/microsoft-365/business) para comprar as licenças de negócios do Microsoft 365. 
  
Consulte [Adicionar, alterar ou excluir um parceiro do supervisor de assinatura](https://support.office.com/article/f86e8177-936e-491e-9024-44dea2b296ff) para descobrir como começar a trabalhar com um parceiro. 
  
Se você receber um link para comprar suas licenças, passará por um assistente como este abaixo. Escolha **Sim, adicionar à minha conta**. Você também pode escolher o número de licenças e o método de pagamento.
  
![No link comprar do Microsoft 365 Business Direct, escolha Adicionar à sua conta atual ou Inscreva-se em uma nova conta.](media/8bc54fd1-9cab-44d5-af91-c471e89aea46.png)
  
## <a name="assign-microsoft-365-licenses"></a>Atribuir licenças do Microsoft 365

1. Após adquirir novas licenças e esta é a primeira vez que você fez, a faixa de instalação do Microsoft 365 Business será exibida na parte superior do centro de administração.
    
    > [!NOTE]
    > A faixa de instalação é uma oportunidade de adicionar novos usuários, de um novo domínio e de migrar emails para novos usuários. Se você não planeja fazer isso, você ainda deve passar pelo assistente e escolher opções padrão para torná-la desaparecer da home page do administrador. 
  
   ![Escolha Iniciar configuração no Microsoft 365 Business está pronto para configurar a faixa.](media/8d3b0d97-7cca-497f-9364-4b00ad670209.png)
  
    Escolha **Iniciar a configuração**.
    
2. Na página **personalizar sua entrada e email** , você pode adicionar um domínio escolhendo **conectar um domínio que você já possui** , se quiser usar essa oportunidade para adicionar outro domínio à sua assinatura. 
    
    Se você já configurou um domínio, o segundo campo indicará que o e a usará para **continuar usando** \< _o nome_ \> **de domínio para email e entrar**.   se você ainda não configurou um domínio com sua assinatura, diga **continuar usando** \< _sua empresa name.onmicrosoft.com_ \> **para email e entrar**.  
    
    Escolha **Avançar**.
    
    ![Na página personalizar sua entrada e email, escolha Adicionar um domínio ou use aquele que você está usando..](media/c3f5cfb2-1189-4d2f-803b-c9feb008a7a3.png)
  
3. Na página **Adicionar novos usuários** , você pode adicionar novos usuários, caso tenha novos funcionários aos quais você deseja atribuir as licenças de negócios do Microsoft 365. 
    
    Se você não tiver novos funcionários para adicionar e quiser atribuir licenças a usuários existentes, escolha **Avançar**.
    
4. Na página * * migrar mensagens de email * *, você pode optar por migrar emails de qualquer um dos novos usuários adicionados na etapa 3. Você também pode ignorar esta etapa. Escolha **Avançar**.
    
5. Na última página, escolha **ir para o centro de administração**e continuar a instalação.
    
6. No centro de administração, vá para usuários **ativos**do **usuário** \> .
    
7. Selecione o usuário ao qual você deseja atribuir a licença do **Microsoft 365 Business** e, em seguida, escolha **Editar** ao lado de **licenças de produto**.
    
    ![No cartão do usuário, escolha Editar ao lado de licenças de produto.](media/be0fe2d8-7ff8-447c-88f6-d212ed78451c.png)
  
8. em **licenças de produto** , deslize **Microsoft 365 Business** to **** \> **Save**e **Close**.
    
após adquirir a licença inicial para o Microsoft 365 Business, agora você pode também adicionar mais nos **serviços de compra**de **cobrança** \> . Na página **comprar serviços** , você pode clicar nas reticências no cartão de **visita do Microsoft 365** e escolher **alterar a quantidade de licenças** para comprar mais. 
  
## <a name="protect-user-devices-and-files"></a>Proteger os arquivos e os dispositivos do usuário

Após ter atribuído licenças para o Microsoft 365 Business, você pode começar a proteger os dispositivos e arquivos dos usuários.
  
1. No centro de administração, na navegação à esquerda, vá para **** \> **políticas**de dispositivos.
    
2. Na página **políticas de dispositivo** , escolha **Adicionar**.
    
3. No painel **Adicionar política** , dê um nome à política e, em seguida, escolha um **tipo de política** na lista suspensa. 
    
    Você pode configurar políticas de aplicativo para proteger arquivos em dispositivos Android e iPhone, bem como Windows 10, e pode configurar políticas de configuração de dispositivo para dispositivos do Windows 10 de propriedade da empresa. ConFira os seguintes links para obter detalhes:
    
  - [Definir configurações de proteção de aplicativo para dispositivos Android ou iOS](app-protection-settings-for-android-and-ios.md)
    
  - [Definir configurações de proteção de aplicativo para dispositivos Windows 10](protection-settings-for-windows-10-devices.md)
    
  - [Definir configurações de proteção de dispositivos para computadores com Windows 10](protection-settings-for-windows-10-pcs.md)
    
   ![No painel Adicionar política, digite um nome para ele e escolha o tipo de política no menu suspenso.](media/76ef37e4-1d18-4f34-8a0f-391ab1d0ae2b.png)
  
4. Depois de configurar as políticas, você e seus funcionários poderão configurar dispositivos:
    
  - Se o Windows ainda não estiver na atualização do Windows pro Creator, será necessário [atualizá-lo para a atualização do Windows pro Creators](upgrade-to-windows-pro-creators-update.md).
    
  - ConFira [configurar dispositivos Windows para usuários do Microsoft 365 Business](set-up-windows-devices.md) para obter etapas para dispositivos Windows. 
    
  - ConFira [configurar dispositivos móveis para usuários do Microsoft 365 Business](set-up-mobile-devices.md) para obter etapas para telefones Android e iPhones. 
    
5. Para instalar automaticamente os aplicativos cliente do Office, consulte [preparar para a implantação do cliente do Office pela Microsoft 365 Business](prepare-for-office-client-deployment.md) e [instalar ou desinstalar automaticamente o Office em dispositivos Windows 10](auto-install-or-uninstall-office.md).
    


