---
title: Atualização para o Microsoft 365 Business Premium da Microsoft 365 Business Standard
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
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 5b4ba843-24b8-4526-8e1f-f9b9eab89d06
description: Saiba mais sobre a diferença entre o Microsoft 365 Business Standard e o Microsoft 365 Business Premium e como é possível atualizar para o Microsoft 365 Business Premium.
ms.openlocfilehash: bdab8165623170926b17efa4cae9408b78a2f5f5
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44401373"
---
# <a name="upgrade-to-microsoft-365-business-premium-from-microsoft-365-business-standard"></a>Atualização para o Microsoft 365 Business Premium da Microsoft 365 Business Standard

Se você tem uma [assinatura do microsoft 365 for Business](https://products.office.com/compare-all-microsoft-office-products-4-column?activetab=tab:primaryr2), por exemplo, o Microsoft 365 Business Standard, é possível atualizar facilmente para o Microsoft 365 Business Premium. Atualize para o Microsoft 365 Business Premium se você quiser adicionar:

- Windows 10 pro (para computadores que executam o Windows 8 ou posterior)

- Controles simples que gerenciam dados corporativos em dispositivos

- Recursos avançados de segurança.
Saiba mais sobre o Microsoft 365 Business Premium em [Microsoft.com](https://www.microsoft.com/microsoft-365/business)

## <a name="whats-the-difference-between-microsoft-365-business-standard-and-microsoft-365-business-premium"></a>Qual é a diferença entre o Microsoft 365 Business Standard e o Microsoft 365 Business Premium?

Adicionamos uma comparação lado a lado desses dois planos à [Descrição do serviço do Microsoft 365 Business Premium](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-business-service-description). 

## <a name="before-you-get-started"></a>Antes de começar

- **Quando devo optar por atualizar?** Atualização é a escolha certa quando você deseja atualizar **todos os usuários** atribuídos a um único plano. Quando você escolhe atualizar, todos os usuários do plano são alternados para outro plano ao mesmo tempo. Se você não quiser atualizar todos os usuários atribuídos a um único plano, compre licenças para o novo plano (neste caso, o Microsoft 365 Business Premium) e [atribua essas licenças individualmente](../admin/manage/assign-licenses-to-users.md) a cada usuário que você deseja atualizar.

- **Alguns complementos podem impedir a atualização** Se você tentar iniciar uma atualização e tiver um complemento que impeça você de continuar, é possível remover o complemento primeiro e, em seguida, adicioná-lo novamente mais tarde, se ainda precisar dele.

- **Se você pagou seu plano** Não há um caminho de atualização direto para planos pré-pagos. Você saberá se tem um plano pré-pago porque configurou seu plano usando uma ID de produto que você pode ter adquirido em uma loja. Entre em contato com um parceiro, acesse a Microsoft Store ou espere até que seu plano pré-pago expire para mudar para um novo plano.

## <a name="upgrade-to-microsoft-365-business-premium"></a>Atualização para o Microsoft 365 Business Premium

1. Entre no centro de administração em <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> .

2. Vá para o painel de navegação e selecione **cobrança** \> **dos produtos**. Encontre sua assinatura atual e selecione-a para exibir os detalhes.

3. Na próxima página, selecione **Atualizar**.

  > [!NOTE]
  > Se você vir uma mensagem informando que **a atualização de sua assinatura não é suportada com o licenciamento baseado em grupo no Azure Active Directory**, você pode ignorá-la com segurança, a menos que tenha uma organização muito grande. As organizações que selecionaram essa opção saberão que estão usando o licenciamento baseado em grupo.

4. Em seguida, você pode exibir uma lista de planos para os quais você pode atualizar. Nesse caso, encontre o plano Microsoft 365 Business Premium. Você pode rolar para baixo se quiser ver todos os aplicativos e serviços incluídos neste plano. No **microsoft 365 Business Premium**, selecione **Atualizar** para adicionar o Microsoft 365 Business Premium ao seu carrinho.

5. No carrinho:

    1. Incluiremos automaticamente licenças para todos os seus usuários atuais. Se você precisar de mais ou menos licenças, precisará [comprar e atribuir essas licenças individualmente](../admin/manage/assign-licenses-to-users.md).  
    2. Você pode ajustar como gostaria de pagar: mensalmente ou anualmente. Selecione o menu suspenso para fazer sua escolha.

6. Selecione **ir para checkout** , onde você verá um resumo da sua compra, incluindo a forma de pagamento para esta conta. Você também pode adicionar um código promocional aqui se tiver um.

7. Selecione **fazer ordem** para concluir sua compra. \
A Microsoft leva alguns minutos para configurar seus novos planos de serviço. Para verificar o progresso, selecione **verificar status da atualização**.

8. Quando o plano estiver pronto, talvez seja necessário concluir algumas etapas adicionais de configuração no centro de administração. No painel de navegação, selecione **página inicial** para concluir as etapas de configuração adicionais.

> [!NOTE]
> Você receberá um reembolso rateado para as licenças do Microsoft 365 que não são mais necessárias. Sua conta bancária ou cartão de crédito serão cobrados de dois dias após a configuração do novo plano.
  
## <a name="protect-user-devices-and-files"></a>Proteger os arquivos e os dispositivos do usuário

Agora que as licenças do Microsoft 365 Business Premium foram atribuídas, conclua as etapas para começar a proteger os dispositivos e arquivos. Você usará algumas novas opções incluídas no painel de navegação do centro de administração.
  
1. No centro de administração, no painel de navegação, vá para **Devices** \> **políticas**de dispositivos.

2. Na página **políticas de dispositivo** , selecione **Adicionar**.

3. No painel **Adicionar política** , dê um nome à política (por exemplo, proteger arquivos de trabalho) e, em seguida, escolha um **tipo de política** na lista suspensa.

    Você pode configurar políticas de aplicativo para proteger arquivos em dispositivos Android e iPhone, bem como Windows 10, e pode configurar políticas de configuração de dispositivo para dispositivos do Windows 10 de propriedade da empresa. Confira os seguintes links para obter detalhes:

    - [Definir configurações de proteção de aplicativo para dispositivos Android ou iOS](app-protection-settings-for-android-and-ios.md)

    - [Definir configurações de proteção de aplicativo para dispositivos Windows 10](protection-settings-for-windows-10-devices.md)

    - [Definir configurações de proteção de dispositivos para computadores com Windows 10](protection-settings-for-windows-10-pcs.md)

4. Depois de configurar as políticas, você e seus funcionários poderão configurar dispositivos:

    - Se seus dispositivos Windows ainda não estiverem usando a atualização do Windows pro Creator, você precisará [atualizá-los para a atualização do Windows pro Creators](upgrade-to-windows-pro-creators-update.md).

    - Consulte [configurar dispositivos Windows para usuários do Microsoft 365 Business Premium](set-up-windows-devices.md) para obter etapas para dispositivos Windows.

    - Confira [configurar dispositivos móveis para usuários do Microsoft 365 Business Premium](set-up-mobile-devices.md) para obter etapas para telefones Android e iPhones.