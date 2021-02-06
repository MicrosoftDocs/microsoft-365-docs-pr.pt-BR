---
title: Transferir um domínio da Microsoft para outro host
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
description: 'Encontre as etapas aqui para transferir um domínio da Microsoft para outro registrador. '
ms.openlocfilehash: f34e9733ab53c8bdc6f4432c96e6232ecc26ee06
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126342"
---
# <a name="transfer-a-domain-from-microsoft-to-another-host"></a>Transferir um domínio da Microsoft para outro host

Você não pode transferir um domínio do Microsoft 365 para outro registrador por 60 dias após adquirir o domínio da Microsoft.

> [!NOTE]
> A _Whois_   query shows a Microsoft purchased domain registrar as Wild West Domains LLC. No entanto, somente a Microsoft deve ser contata em relação ao seu domínio adquirido do Microsoft 365.

Siga estas etapas para obter um código no Microsoft 365 e, em seguida, vá para o outro site do registrador de domínios para configurar a transferência do seu nome de domínio para o novo registrador.

## <a name="transfer-a-domain"></a>Transferir um domínio

1. No centro de administração, vá para   **Domínios**   >  **de Configurações.**

2. Na página **Domínios,** selecione o domínio do Microsoft 365 que você deseja transferir para outro registrador de domínios e selecione **Verificar a saúde.**

3. Na parte superior da página, selecione **Transferir domínio.**

4. On the **Choose where to transfer your domain** page, select A different **registrar**, and then click **Next**.

5. Na página **Desbloquear transferência de domínio,** selecione **Desbloquear transferência <seu _domínio_ >** e, em seguida, selecione **Próximo**.

6. Verifique suas informações de contato de transferência de domínio e selecione **Próximo.**

7. Copie o código de autorização e aguarde cerca de 30 minutos  para que seu status de transferência de domínio mude para **Desbloqueado** para transferência na guia Registro antes de prosseguir com as próximas etapas.

8. Vá para o site do registrador de domínios que você deseja gerenciar seu nome de domínio no futuro. Siga as instruções para transferir um domínio (procure ajuda em seu site). Isso geralmente significa pagar taxas de transferência e dar a Authcode ao novo registrador para que ele possa iniciar a transferência. A Microsoft enviará um email para confirmar que recebemos a solicitação de transferência, e o domínio será transferido dentro de 5 dias.

    Você pode encontrar a guia Registro do código **de** autorização  **na página Domínios** no Microsoft 365.
    
    > [!TIP]
    > Domínios .uk exigem um procedimento diferente. Entre em contato com o Suporte da Microsoft e solicite uma alteração de **Marca IPS** para corresponder ao registrador que você deseja gerenciar seu domínio no futuro. Depois que a marca é mudada, o domínio é transferido imediatamente para o novo registrador. Em seguida, você precisará trabalhar com o novo registrador para concluir a transferência, provavelmente pagar taxas de transferência e adicionar o domínio transferido à sua conta com seu novo registrador.

9. Após a conclusão da transferência, você renovará seu domínio no novo registrador de domínios.

10. Para concluir o processo, volte para a página **Domínios** no centro de administração e selecione   **Concluir transferência de domínio.** Isso marcará o domínio como não mais adquirido do Microsoft 365 e desabilitará a assinatura de domínio. Ele não removerá o domínio do locatário e não afetará usuários e caixas de correio existentes no domínio.

> [!NOTE]
> Os domínios comprados do Microsoft 365 não estão qualificados para alterações de nameserver ou transferência do domínio entre organizações do Microsoft 365. Se um deles for necessário, o registro de domínio deverá ser transferido para outro registrador.
