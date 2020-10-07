---
title: Transferir um domínio da Microsoft para outro host
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
description: 'Encontre as etapas aqui para transferir um domínio da Microsoft para outro registrador. '
ms.openlocfilehash: d960b57a2c82b804d61ead1c672c00f0543b3ae8
ms.sourcegitcommit: 33afa334328cc4e3f2474abd611c1411adabd39f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/07/2020
ms.locfileid: "48370319"
---
# <a name="transfer-a-domain-from-microsoft-to-another-host"></a>Transferir um domínio da Microsoft para outro host

Você não pode transferir um domínio do Microsoft 365 para outro registrador por 60 dias após adquirir o domínio da Microsoft.

> [!NOTE]
> Uma consulta _whois_   mostra um registrador de domínio comprado pela Microsoft como domínios com o oeste da West. No entanto, somente a Microsoft deve ser contatada em relação ao seu domínio adquirido pela Microsoft 365.

Siga estas etapas para obter um código no Microsoft 365 e, em seguida, vá para o outro site de registrador de domínio para configurar a transferência do seu nome de domínio para o novo registrador.

## <a name="transfer-a-domain"></a>Transferir um domínio

1. No centro de administração, vá para domínios de  **configurações**   >  **Domains**.

2. Na página **domínios** , selecione o domínio do Microsoft 365 que você deseja transferir para outro registrador de domínios e, em seguida, selecione **verificar integridade**.

3. Na parte superior da página, selecione o **domínio de transferência**.

4. Na página **escolher onde transferir o domínio** , selecione **um registrador diferente**e clique em **Avançar**.

5. Na página **desbloquear transferência de domínio** , selecione **desbloquear transferência para <_seu domínio_ > **e, em seguida, selecione **Avançar**.

6. Verifique suas informações de contato de transferência de domínio e selecione **Avançar**.

7. Copie o código de autorização e aguarde cerca de 30 minutos para que o status da transferência de domínio mude para **desbloqueado para transferência** na guia **registro** antes de prosseguir com as próximas etapas.

8. Vá para o site do registrador de domínio que você deseja gerenciar o nome de seu domínio no futuro. Siga as instruções para transferir um domínio (procure ajuda no site). Isso geralmente significa o pagamento das taxas de transferência e a atribuição do authcode ao novo registrador, para que eles possam iniciar a transferência. A Microsoft enviará um email para confirmar que recebemos a solicitação de transferência e o domínio será transferido dentro de 5 dias.

    Você pode encontrar a guia **registro** de código de autorização na página  **domínios** no Microsoft 365.
    
    > [!TIP]
    > os domínios. uk precisam de um procedimento diferente. Entre em contato com o suporte da Microsoft e solicite uma **alteração na marca IPS** para corresponder ao registrador que você deseja gerenciar o seu domínio no futuro. Após a alteração da marca, o domínio transfere imediatamente para o novo registrador. Você precisará trabalhar com o novo registrador para concluir a transferência, provavelmente pagando as taxas de transferência e adicionando o domínio transferido à sua conta com seu novo registrador.

9. Após a conclusão da transferência, você renovará seu domínio no novo registrador de domínio.

10. Para concluir o processo, volte para a página **domínios** no centro de administração e selecione  **transferência de domínio completo**. Isso marcará o domínio como não mais comprado no Microsoft 365 e desabilitará a assinatura do domínio. Ele não removerá o domínio do locatário e não afetará os usuários e caixas de correio existentes no domínio.

> [!NOTE]
> Os domínios comprados pela Microsoft 365 não estão qualificados para as alterações de nameserver ou para transferir o domínio entre as organizações do Microsoft 365. Se uma dessas opções for obrigatória, o registro de domínio deverá ser transferido para outro registrador.
