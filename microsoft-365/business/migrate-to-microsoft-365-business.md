---
title: Atualização para o Microsoft 365 Business do Office 365 Business Premium
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
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
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: 5b4ba843-24b8-4526-8e1f-f9b9eab89d06
description: Etapas que atualizam sua empresa do Office 365 Business Premium para a Microsoft 365 Business.
ms.openlocfilehash: e17ac2658c7276ba4a77de371847343866815c42
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42065252"
---
# <a name="upgrade-to-microsoft-365-business-from-office-365-business-premium"></a>Atualização para o Microsoft 365 Business do Office 365 Business Premium

Se você tiver uma [assinatura do office 365 for Business](https://products.office.com/compare-all-microsoft-office-products-4-column?activetab=tab:primaryr2), por exemplo, o Office 365 Business Premium, é possível atualizar facilmente para o Microsoft 365 Business. Atualize para o Microsoft 365 Business se você quiser adicionar: 
- Windows 10 pro (para computadores que executam o Windows 8 ou posterior)
- Controles simples que gerenciam dados corporativos em dispositivos
- Recursos avançados de segurança.
Saiba mais sobre o Microsoft 365 Business em [Microsoft.com](https://www.microsoft.com/microsoft-365/business)

## <a name="whats-the-difference-between-office-365-business-premium-and-microsoft-365-business"></a>Qual é a diferença entre o Office 365 Business Premium e o Microsoft 365 Business?
Adicionamos uma comparação lado a lado desses dois planos à [Descrição do serviço de negócios 365 da Microsoft](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-business-service-description). 

## <a name="before-you-get-started"></a>Antes de começar

- **Quando devo optar por atualizar?** Atualização é a escolha certa quando você deseja atualizar **todos os usuários** atribuídos a um único plano. Quando você escolhe atualizar, todos os usuários do plano são alternados para outro plano ao mesmo tempo. Se você não quiser atualizar todos os que foram atribuídos a um único plano, compre licenças para o novo plano (neste caso, o Microsoft 365 Business) e [atribua essas licenças individualmente](https://docs.microsoft.com/office365/admin/manage/assign-licenses-to-users) a cada usuário que você deseja atualizar. 
- **Alguns complementos podem impedir a atualização** Se você tentar iniciar uma atualização e tiver um complemento que impeça você de continuar, é possível remover o complemento primeiro e, em seguida, adicioná-lo novamente mais tarde, se ainda precisar dele. 
- **Se você pagou seu plano** Não há um caminho de atualização direto para planos pré-pagos. Você saberá se tem um plano pré-pago porque configurou seu plano usando uma ID de produto que você pode ter adquirido em uma loja. Entre em contato com um parceiro, acesse a Microsoft Store ou espere até que seu plano pré-pago expire para mudar para um novo plano.

## <a name="upgrade-to-microsoft-365-business"></a>Atualização para o Microsoft 365 Business
Compre suas licenças seguindo estas etapas no [novo centro de administração](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview):
1. Entre no centro de administração em <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.
2. Vá para o painel de navegação e selecione produtos de **cobrança** \> **& Services**. Encontre sua assinatura do Office 365 e selecione-a para exibir os detalhes. 

    ![Uma captura de tela mostra como localizar e selecionar sua assinatura no centro de administração.](../media/FindYourSubscription.png)

3. Na próxima página, selecione **Atualizar**. 

      ![Uma captura de tela mostra onde selecionar a atualização no centro de administração.](../media/SelectUpgrade.png)

  > [!NOTE]
  > Se você vir uma mensagem informando que **a atualização de sua assinatura não é suportada com o licenciamento baseado em grupo no Azure Active Directory**, você pode ignorá-la com segurança, a menos que tenha uma organização muito grande. As organizações que selecionaram essa opção saberão que estão usando o licenciamento baseado em grupo.

4. Em seguida, você pode exibir uma lista de planos do Office para os quais você pode atualizar. Nesse caso, encontre o plano de negócios do Microsoft 365. Você pode rolar para baixo se quiser ver todos os aplicativos e serviços do Office incluídos neste plano. Em **microsoft 365 Business**, selecione **upgrade** para adicionar o Microsoft 365 Business ao seu carrinho.
5. No carrinho:
    1. Incluiremos automaticamente licenças para todos os seus usuários atuais. Se você precisar de mais ou menos licenças, precisará [comprar e atribuir essas licenças individualmente](https://docs.microsoft.com/office365/admin/manage/assign-licenses-to-users).  
    2. Você pode ajustar como gostaria de pagar: mensalmente ou anualmente. Selecione o menu suspenso para fazer sua escolha.
6. Selecione **ir para checkout** , onde você verá um resumo da sua compra, incluindo a forma de pagamento para esta conta. Você também pode adicionar um código promocional aqui se tiver um.
7. Selecione **fazer ordem** para concluir a compra.
A Microsoft leva alguns minutos para configurar seus novos planos de serviço. Para verificar o progresso, selecione **verificar status da atualização**. 
1. Quando o plano estiver pronto, talvez seja necessário concluir algumas etapas adicionais de configuração no centro de administração. No painel de navegação, selecione **página inicial** para concluir as etapas de configuração adicionais.

> [!NOTE]
> Você receberá um reembolso rateado para as licenças do Office 365 que não são mais necessárias. Sua conta bancária ou cartão de crédito serão cobrados de dois dias após a configuração do novo plano.
  
## <a name="protect-user-devices-and-files"></a>Proteger os arquivos e os dispositivos do usuário

Agora que as licenças de negócios da Microsoft 365 foram atribuídas, conclua as etapas para começar a proteger os dispositivos e arquivos. Você usará algumas novas opções incluídas no painel de navegação do centro de administração.
  
1. No centro de administração, no painel de navegação, vá para **** \> **políticas**de dispositivos.
    
2. Na página **políticas de dispositivo** , selecione **Adicionar**.
    
3. No painel **Adicionar política** , dê um nome à política (por exemplo, proteger arquivos de trabalho) e, em seguida, escolha um **tipo de política** na lista suspensa. 
    
    Você pode configurar políticas de aplicativo para proteger arquivos em dispositivos Android e iPhone, bem como Windows 10, e pode configurar políticas de configuração de dispositivo para dispositivos do Windows 10 de propriedade da empresa. Confira os seguintes links para obter detalhes:
    
  - [Definir configurações de proteção de aplicativo para dispositivos Android ou iOS](app-protection-settings-for-android-and-ios.md)
    
  - [Definir configurações de proteção de aplicativo para dispositivos Windows 10](protection-settings-for-windows-10-devices.md)
    
  - [Definir configurações de proteção de dispositivos para computadores com Windows 10](protection-settings-for-windows-10-pcs.md)
    
  
4. Depois de configurar as políticas, você e seus funcionários poderão configurar dispositivos:
    
  - Se seus dispositivos Windows ainda não estiverem usando a atualização do Windows pro Creator, você precisará [atualizá-los para a atualização do Windows pro Creators](upgrade-to-windows-pro-creators-update.md).
    
  - Confira [configurar dispositivos Windows para usuários do Microsoft 365 Business](set-up-windows-devices.md) para obter etapas para dispositivos Windows. 
    
  - Confira [configurar dispositivos móveis para usuários do Microsoft 365 Business](set-up-mobile-devices.md) para obter etapas para telefones Android e iPhones. 
