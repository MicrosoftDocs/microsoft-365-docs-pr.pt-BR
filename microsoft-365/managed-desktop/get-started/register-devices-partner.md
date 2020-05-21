---
title: Etapas para registrar dispositivos de parceiros
description: Como os parceiros podem registrar dispositivos para que possam ser gerenciados pela área de trabalho gerenciada da Microsoft
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: f1b1a8f03b7a11a0467826281bc2b789140dbcee
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2020
ms.locfileid: "44327041"
---
# <a name="steps-for-partners-to-register-devices"></a>Etapas para registrar dispositivos de parceiros


Este tópico descreve as etapas dos parceiros a serem seguidas para registrar dispositivos. O processo de registro de seus próprios dispositivos está documentado em [registrar dispositivos na área de trabalho gerenciada da Microsoft](register-devices-self.md).



## <a name="prepare-for-registration"></a>Preparar para o registro 
Antes de concluir o registro de um cliente, primeiro você deve estabelecer uma relação com eles no [Partner Center](https://partner.microsoft.com/dashboard). Consulte a [documentação de consentimento](https://docs.microsoft.com/windows/deployment/windows-autopilot/registration-auth#csp-authorization) para obter mais detalhes sobre esse processo. Qualquer parceiro de CSP pode adicionar dispositivos em nome de qualquer cliente, desde que o cliente tenha sido enviado. Você também pode saber mais sobre relacionamentos de parceiros e permissões do AutoPilot na [ajuda da central de parceiros](https://docs.microsoft.com/partner-center/customers_revoke_admin_privileges#windows-autopilot).


> [!NOTE]
> Esta documentação destina-se apenas a parceiros e OEMs. O processo de auto-registro está documentado em [registrar dispositivos na área de trabalho gerenciada da Microsoft](register-devices-self.md).


## <a name="register-devices-by-using-partner-center"></a>Registrar dispositivos usando o Partner Center

Depois de estabelecer a relação com seus clientes, você pode aproveitar o Partner Center para adicionar dispositivos ao piloto automático para qualquer um dos clientes com os quais você tem uma relação, seguindo estas etapas:

1. Navegue até a [central de parceiros](https://partner.microsoft.com/dashboard)
2. Selecione **clientes** no menu da central de parceiros e selecione o cliente cujos dispositivos você deseja gerenciar.
3. Na página detalhes do cliente, selecione **dispositivos**.
4. Em **aplicar perfis** a dispositivos, selecione **Adicionar dispositivos**.
5. Insira **Microsoft365Managed_Autopilot** para o nome do grupo e, em seguida, selecione **procurar** para carregar a lista do cliente (em formato de arquivo. csv) para o Partner Center.


> [!IMPORTANT]
> O nome do grupo deve coincidir **Microsoft365Managed_Autopilot** exatamente, incluindo o uso de maiúsculas e caracteres especiais. Isso permitirá que os dispositivos recentemente registrados sejam atribuídos com o perfil AutoPilot da área de trabalho gerenciada da Microsoft.

>[!NOTE]
> Você deve ter recebido esse arquivo. csv com sua compra de dispositivo. Se você não recebeu um arquivo. csv, pode criar um por conta própria seguindo as etapas em [adicionando dispositivos ao Windows AutoPilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/add-devices#collecting-the-hardware-id-from-existing-devices-using-powershell). O script do Windows PowerShell é diferente daquele usado para o [portal de administração de área de trabalho gerenciada da Microsoft](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/register-devices-self?view=o365-worldwide#obtain-the-hardware-hash). Os parceiros devem usar o [Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) para registrar dispositivos para dispositivos de área de trabalho gerenciada da Microsoft no Partner Center.

Se você receber uma mensagem de erro ao tentar carregar o arquivo. csv, verifique o formato do arquivo. Você pode usar somente o hash de hardware ou o nome do OEM, o número de série e o modelo (na ordem da coluna) ou a ID do produto Windows. Você também pode usar o arquivo. csv de exemplo fornecido pelo link próximo a **Adicionar dispositivos** para criar uma lista de dispositivos. 

Para obter mais informações sobre o AutoPilot em cenários de parceiros, consulte [Adicionar dispositivos à conta de um cliente](https://docs.microsoft.com/partner-center/autopilot#add-devices-to-a-customers-account).


## <a name="register-devices-by-using-the-oem-api"></a>Registrar dispositivos usando a API OEM

Antes de concluir o registro de um cliente, primeiro você deve estabelecer uma relação com eles. Você deve ter um link exclusivo para fornecer aos seus respectivos clientes. Confira [como estabelecer uma relação de OEM](https://docs.microsoft.com/windows/deployment/windows-autopilot/registration-auth#oem-authorization).

Depois de estabelecer a relação, você pode iniciar o registro de dispositivos para clientes usando a marca de grupo **Microsoft365Managed_Autopilot**.

> [!IMPORTANT]
> O nome do grupo deve coincidir **Microsoft365Managed_Autopilot** exatamente, incluindo o uso de maiúsculas e caracteres especiais. Isso permitirá que os dispositivos recentemente registrados sejam atribuídos com o perfil AutoPilot da área de trabalho gerenciada da Microsoft.
