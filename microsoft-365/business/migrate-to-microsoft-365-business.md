---
title: Atualizar para o Microsoft 365 Business Premium a partir do Microsoft 365 Business Standard
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
description: Saiba a diferença entre o Microsoft 365 Business Standard e o Microsoft 365 Business Premium e como você pode atualizar para o Microsoft 365 Business Premium.
ms.openlocfilehash: bdab8165623170926b17efa4cae9408b78a2f5f5
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44401373"
---
# <a name="upgrade-to-microsoft-365-business-premium-from-microsoft-365-business-standard"></a>Atualizar para o Microsoft 365 Business Premium a partir do Microsoft 365 Business Standard

Se você tiver uma assinatura do [Microsoft 365](https://products.office.com/compare-all-microsoft-office-products-4-column?activetab=tab:primaryr2)para empresas, por exemplo, o Microsoft 365 Business Standard, poderá atualizar facilmente para o Microsoft 365 Business Premium. Atualize para o Microsoft 365 Business Premium se quiser adicionar:

- Windows 10 Pro (para computadores que executam o Windows 8 ou posterior)

- Controles simples que gerenciam dados de negócios em dispositivos

- Recursos avançados de segurança.
Saiba mais sobre o Microsoft 365 Business Premium no [Microsoft.com](https://www.microsoft.com/microsoft-365/business)

## <a name="whats-the-difference-between-microsoft-365-business-standard-and-microsoft-365-business-premium"></a>Qual é a diferença entre o Microsoft 365 Business Standard e o Microsoft 365 Business Premium?

Adicionamos uma comparação lado a lado desses dois planos à Descrição de Serviço do [Microsoft 365 Business Premium.](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-business-service-description) 

## <a name="before-you-get-started"></a>Antes de começar

- **Quando devo optar por atualizar?** A atualização é a escolha certa quando você deseja atualizar **todos os usuários** atribuídos a um único plano. Quando você escolhe a atualização, todos os usuários do plano são trocados para outro plano ao mesmo tempo. Se você não quiser atualizar todos os usuários atribuídos a um único plano, compre licenças para o novo plano (neste caso, Microsoft 365 Business Premium) e atribua essas [licenças individualmente](../admin/manage/assign-licenses-to-users.md) a cada usuário que você deseja atualizar.

- **Alguns complementos podem impedir a atualização** Se você tentar iniciar uma atualização e tiver um complemento que o impeça de continuar, você poderá remover o complemento primeiro e adicioná-lo novamente mais tarde se ainda precisar dele.

- **Se você tiver pré-pago seu plano** Não há um caminho de atualização simples para planos pré-pagos. Você vai saber se tem um plano pré-pago porque você configura seu plano usando uma ID de produto que pode ter comprado em uma loja. Entre em contato com um parceiro, vá para a Microsoft Store ou aguarde até que seu plano pré-pago expire para mudar para um novo plano.

## <a name="upgrade-to-microsoft-365-business-premium"></a>Atualizar para o Microsoft 365 Business Premium

1. Entre no centro de administração em <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> .

2. Vá para o painel de navegação e selecione **Cobrança** \> **seus produtos.** Encontre sua assinatura atual e selecione-a para exibir os detalhes.

3. Na próxima página, selecione **Atualizar.**

  > [!NOTE]
  > Se você vir uma mensagem que diz que a atualização da sua assinatura não é suportada com o licenciamento baseado em grupo no **Azure Active Directory,** você pode ignorar isso com segurança, a menos que você tenha uma organização muito grande. As organizações que selecionaram essa opção estarão cientes de que estão usando o licenciamento baseado em grupo.

4. Em seguida, você pode exibir uma lista de planos para os que você pode atualizar. Nesse caso, encontre o plano Microsoft 365 Business Premium. Você pode rolar para baixo se quiser ver todos os aplicativos e serviços incluídos nesse plano. No **Microsoft 365 Business Premium,** selecione **Atualizar** para adicionar o Microsoft 365 Business Premium ao carrinho.

5. No carrinho:

    1. Incluiremos automaticamente licenças para todos os usuários atuais. Se você precisar de mais ou menos licenças, precisará [comprar e atribuir essas licenças individualmente.](../admin/manage/assign-licenses-to-users.md)  
    2. Você pode ajustar como gostaria de pagar: mensalmente ou anualmente. Selecione o menu suspenso para fazer sua escolha.

6. Selecione **Ir para Check-out,** onde você verá um resumo de sua compra, incluindo a forma de pagamento dessa conta. Você também pode adicionar um código promocional aqui se tiver um.

7. Selecione **Fazer pedido** para concluir a compra.\
A Microsoft leva alguns minutos para configurar seus novos planos de serviço. Para verificar o progresso, selecione **Verificar o status da atualização.**

8. Quando seu plano estiver pronto, talvez seja necessário concluir algumas etapas adicionais de configuração no centro de administração. No painel de navegação, selecione **Página Inicial** para concluir as etapas de configuração adicionais.

> [!NOTE]
> Você receberá um reembolso rateado para as licenças do Microsoft 365 que não precisa mais. Sua conta bancária ou cartão de crédito será cobrado cerca de dois dias após a configuração do novo plano.
  
## <a name="protect-user-devices-and-files"></a>Proteger arquivos e dispositivos do usuário

Agora que as licenças do Microsoft 365 Business Premium foram atribuídas, conclua as etapas para começar a proteger dispositivos e arquivos. Você usará algumas novas opções incluídas no painel de navegação do centro de administração.
  
1. No centro de administração, no painel de navegação, vá para Políticas **de** \> **Dispositivos.**

2. Na página **Políticas de dispositivo,** selecione **Adicionar**.

3. No painel **Adicionar política,** dê um nome à política (por exemplo, Proteger arquivos de trabalho) e, em seguida, escolha um tipo de política na lista drop-down. 

    Você pode configurar políticas de aplicativo para proteger arquivos em dispositivos Android e iPhone, bem como o Windows 10, e pode configurar políticas de configuração de dispositivos para dispositivos Windows 10 de propriedade da empresa. Confira os links a seguir para obter detalhes:

    - [Definir configurações de proteção de aplicativo para dispositivos Android ou iOS](app-protection-settings-for-android-and-ios.md)

    - [Definir configurações de proteção de aplicativo para dispositivos Windows 10](protection-settings-for-windows-10-devices.md)

    - [Definir configurações de proteção de dispositivo para computadores com Windows 10](protection-settings-for-windows-10-pcs.md)

4. Depois de configurar políticas, você e seus funcionários podem configurar dispositivos:

    - Se os dispositivos Windows ainda não estão usando a atualização do Windows Pro Creator, você precisará atualizá-los para a Atualização do [Windows Pro para Criadores.](upgrade-to-windows-pro-creators-update.md)

    - Consulte [Configurar dispositivos Windows para usuários do Microsoft 365 Business Premium](set-up-windows-devices.md) para ver as etapas para dispositivos Windows.

    - Consulte [Configurar dispositivos móveis para usuários do Microsoft 365 Business Premium](set-up-mobile-devices.md) para ver as etapas para telefones Android e iPhones.