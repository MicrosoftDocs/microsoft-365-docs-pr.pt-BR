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
ms.openlocfilehash: 7e00f5ae2c36a06803a3f7a8acd825dcab90805c
ms.sourcegitcommit: 6fb2a1c404ea3c3573b0f7803bf17459a9387891
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/18/2020
ms.locfileid: "46788971"
---
# <a name="transfer-a-domain-from-microsoft-to-another-host"></a>Transferir um domínio da Microsoft para outro host

Você não pode transferir um domínio do Microsoft 365 para outro registrador por 60 dias após adquirir o domínio da Microsoft.

> [!NOTE]
> Uma consulta _whois_   mostra um registrador de domínio comprado pela Microsoft como domínios com o oeste da West. No entanto, somente a Microsoft deve ser contatada em relação ao seu domínio adquirido pela Microsoft 365.

Siga estas etapas para obter um código no Microsoft 365 e, em seguida, vá para o outro site de registrador de domínio para configurar a transferência do seu nome de domínio para o novo registrador.

## <a name="transfer-a-domain"></a>Transferir um domínio

1. No centro de administração, vá para domínios de  **configurações**   >  **Domains**.

2. <na página **domínios** , selecione o domínio do Microsoft 365 que você deseja transferir para outro registrador de domínios e, em seguida, selecione **verificar integridade**.

3. Na parte superior da página, selecione o **domínio de transferência**.

4. Na página **escolher onde transferir o domínio** , selecione **um registrador diferente**e clique em **Avançar**.

5. Na página **desbloquear transferência de domínio** , selecione **desbloquear transferência para <_seu domínio_ > **e, em seguida, selecione **Avançar**.

6. Verifique suas informações de contato de transferência de domínio e selecione **Avançar**.

7. Copie o código de autorização e aguarde cerca de 30 minutos para que o status da transferência de domínio mude para **desbloqueado para transferência** na guia **registro** antes de prosseguir com as próximas etapas.

8. Vá para o site do registrador de domínio que você deseja gerenciar o nome de seu domínio no futuro. Siga as instruções para transferir um domínio (procure ajuda no site).

Você pode encontrar a guia **registro** de código de autorização na página  **domínios** no Microsoft 365.

9. Após a conclusão da transferência, você renovará seu domínio no novo registrador de domínio.

10. Para concluir o processo, volte para a página **domínios** no centro de administração e selecione  **transferência de domínio completo**.

> [!NOTE]
> Os domínios comprados pela Microsoft 365 não estão qualificados para as alterações de nameserver ou para transferir o domínio entre as organizações do Microsoft 365. Se uma dessas opções for obrigatória, o registro de domínio deverá ser transferido para outro registrador.
