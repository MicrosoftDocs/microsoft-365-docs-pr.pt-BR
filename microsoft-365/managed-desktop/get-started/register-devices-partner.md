---
title: Etapas para registrar dispositivos de parceiros
description: Como os parceiros podem registrar dispositivos para que possam ser gerenciados pela Área de Trabalho Gerenciada da Microsoft
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: baf15ca4b83052af84d2b22b3d2604c6022ac900
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445585"
---
# <a name="steps-for-partners-to-register-devices"></a>Etapas para registrar dispositivos de parceiros


Este tópico descreve as etapas para parceiros seguirem para registrar dispositivos. O processo de registro de dispositivos por conta própria está documentado em [Registrar dispositivos na Área de Trabalho Gerenciada da Microsoft.](register-devices-self.md)



## <a name="prepare-for-registration"></a>Preparar para registro 
Antes de concluir o registro de um cliente, você deve primeiro estabelecer um relacionamento com ele no [Partner Center](https://partner.microsoft.com/dashboard). Consulte a [documentação de consentimento](/windows/deployment/windows-autopilot/registration-auth#csp-authorization) para obter mais detalhes sobre esse processo. Qualquer parceiro CSP pode adicionar dispositivos em nome de qualquer cliente, desde que o cliente consenta. Você também pode saber mais sobre as relações de parceiros e permissões do Piloto Automático na ajuda [do Partner Center.](/partner-center/customers_revoke_admin_privileges#windows-autopilot)


> [!NOTE]
> Esta documentação é somente para Parceiros e OEMs. O processo de auto-registro é documentado em [Registrar dispositivos na Área de Trabalho Gerenciada da Microsoft.](register-devices-self.md)


## <a name="register-devices-by-using-partner-center"></a>Registrar dispositivos usando o Partner Center

Depois de estabelecer o relacionamento com seus clientes, você pode aproveitar o Partner Center para adicionar dispositivos ao Autopilot para qualquer um dos clientes com os que você tem uma relação seguindo estas etapas:

1. Navegue até [o Partner Center](https://partner.microsoft.com/dashboard)
2. Selecione **Clientes** no menu Partner Center e selecione o cliente cujos dispositivos você deseja gerenciar.
3. Na página de detalhes do cliente, selecione **Dispositivos**.
4. Em **Aplicar perfis** a dispositivos, selecione **Adicionar dispositivos**.
5. Insira **Microsoft365Managed_Autopilot** nome do grupo e selecione **Procurar** para carregar a lista do cliente (no formato de arquivo .csv) para o Partner Center.


> [!IMPORTANT]
> O Nome do Grupo deve corresponder **Microsoft365Managed_Autopilot,** incluindo maiúsculas e caracteres especiais. Isso permitirá que os dispositivos recém-registrados sejam atribuídos ao perfil do Microsoft Managed Desktop Autopilot.

>[!NOTE]
> Você deve ter recebido esse arquivo .csv com a compra do dispositivo. Se você não recebeu um arquivo .csv, pode criar um sozinho seguindo as etapas em Adicionar dispositivos [ao Windows Autopilot](/windows/deployment/windows-autopilot/add-devices#collecting-the-hardware-id-from-existing-devices-using-powershell). O Windows PowerShell script é diferente do usado para o portal de Administração da [Área de Trabalho Gerenciada da Microsoft.](./register-devices-self.md?view=o365-worldwide#obtain-the-hardware-hash) Os parceiros devem usar [Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) para registrar dispositivos para dispositivos da Área de Trabalho Gerenciada da Microsoft no Partner Center.

Se você receber uma mensagem de erro ao tentar carregar o arquivo .csv, verifique o formato do arquivo. Certifique-se de que a ordem de coluna corresponde ao descrito em Use Windows Autopilot profiles in new devices to customize [a customer's out-of-box experience](/partner-center/autopilot#add-devices-to-a-customers-account). Você também pode usar o arquivo .csv de exemplo fornecido no link ao lado de **Adicionar dispositivos** para criar uma lista de dispositivos. 

Para obter mais informações sobre o Autopilot em cenários de parceiros, consulte [Adicionar dispositivos à conta de um cliente](/partner-center/autopilot#add-devices-to-a-customers-account).


## <a name="register-devices-by-using-the-oem-api"></a>Registrar dispositivos usando a API OEM

Antes de concluir o registro de um cliente, você deve primeiro estabelecer um relacionamento com ele. Você deve ter um link exclusivo para fornecer aos seus respectivos clientes. Consulte [Como estabelecer relação OEM](/windows/deployment/windows-autopilot/registration-auth#oem-authorization).

Depois de estabelecer a relação, você pode começar a registrar dispositivos para clientes usando a marca de **grupo Microsoft365Managed_Autopilot**.

> [!IMPORTANT]
> O nome do grupo deve corresponder **Microsoft365Managed_Autopilot,** incluindo maiúsculas e caracteres especiais. Isso permitirá que os dispositivos recém-registrados sejam atribuídos ao perfil do Microsoft Managed Desktop Autopilot.