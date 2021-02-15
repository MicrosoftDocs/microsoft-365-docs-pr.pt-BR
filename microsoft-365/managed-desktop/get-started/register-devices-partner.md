---
title: Etapas para registrar dispositivos de parceiros
description: Como os parceiros podem registrar dispositivos para que possam ser gerenciados pela Área de Trabalho Gerenciada da Microsoft
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: 7e40a5eb7144fef3d330e0e8fc3c711af15d4c49
ms.sourcegitcommit: 34ebec8e2bd54ba3d4ccfd9724797665c965c17f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49071438"
---
# <a name="steps-for-partners-to-register-devices"></a>Etapas para registrar dispositivos de parceiros


Este tópico descreve as etapas para parceiros acompanharem o registro de dispositivos. O processo de registro de dispositivos por conta própria está documentado em [Registrar dispositivos na Área de Trabalho Gerenciada da Microsoft](register-devices-self.md)por conta própria.



## <a name="prepare-for-registration"></a>Preparar-se para o registro 
Antes de concluir o registro para um cliente, você deve primeiro estabelecer uma relação com ele no [Partner Center.](https://partner.microsoft.com/dashboard) Consulte a [documentação de consentimento](https://docs.microsoft.com/windows/deployment/windows-autopilot/registration-auth#csp-authorization) para obter mais detalhes sobre esse processo. Qualquer parceiro CSP pode adicionar dispositivos em nome de qualquer cliente, desde que o cliente consenta. Você também pode saber mais sobre relações de parceiros e permissões do Autopilot na [ajuda do Partner Center.](https://docs.microsoft.com/partner-center/customers_revoke_admin_privileges#windows-autopilot)


> [!NOTE]
> Esta documentação é apenas para Parceiros e OEMs. O processo de auto-registro está documentado em Registrar dispositivos [na Área de Trabalho Gerenciada da Microsoft](register-devices-self.md)por conta própria.


## <a name="register-devices-by-using-partner-center"></a>Registrar dispositivos usando o Partner Center

Depois de estabelecer a relação com seus clientes, você pode aproveitar o Partner Center para adicionar dispositivos ao Autopilot para qualquer um dos clientes com quem você tenha um relacionamento seguindo estas etapas:

1. Navegue até [o Partner Center](https://partner.microsoft.com/dashboard)
2. Selecione **Clientes** no menu Partner Center e selecione o cliente cujos dispositivos você deseja gerenciar.
3. Na página de detalhes do cliente, selecione **Dispositivos.**
4. Em **Aplicar perfis** a dispositivos, selecione **Adicionar dispositivos.**
5. Insira **Microsoft365Managed_Autopilot** nome do grupo e selecione **Procurar** para carregar a lista do cliente (no formato de arquivo .csv) para o Partner Center.


> [!IMPORTANT]
> O Nome do Grupo deve corresponder **Microsoft365Managed_Autopilot** exatamente, incluindo maiúsculas e maiúsculas e caracteres especiais. Isso permitirá que os dispositivos recém-registrados sejam atribuídos com o perfil piloto automático da Área de Trabalho Gerenciada da Microsoft.

>[!NOTE]
> Você deve ter recebido esse arquivo .csv com a compra do dispositivo. Se você não recebeu um arquivo .csv, poderá criar um por conta própria seguindo as etapas em Adicionar dispositivos [ao Windows Autopilot.](https://docs.microsoft.com/windows/deployment/windows-autopilot/add-devices#collecting-the-hardware-id-from-existing-devices-using-powershell) O script do Windows PowerShell é diferente do usado para o Portal de Administração da [Área de Trabalho Gerenciada da Microsoft.](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/register-devices-self?view=o365-worldwide#obtain-the-hardware-hash) Os parceiros devem usar [Get-WindowsAutoPilotInfo para](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) registrar dispositivos para dispositivos da Área de Trabalho Gerenciada da Microsoft no Partner Center.

Se você receber uma mensagem de erro ao tentar carregar o arquivo .csv, verifique o formato do arquivo. Certifique-se de que a ordem das colunas corresponde ao que está descrito em Usar perfis do [Windows Autopilot](https://docs.microsoft.com/partner-center/autopilot#add-devices-to-a-customers-account)em novos dispositivos para personalizar a configuração de configuração do cliente. Você também pode usar o arquivo .csv de exemplo fornecido no link ao lado de **Adicionar dispositivos** para criar uma lista de dispositivos. 

Para obter mais informações sobre o Autopilot em cenários de parceiros, [consulte Adicionar dispositivos à conta de um cliente.](https://docs.microsoft.com/partner-center/autopilot#add-devices-to-a-customers-account)


## <a name="register-devices-by-using-the-oem-api"></a>Registrar dispositivos usando a API OEM

Antes de concluir o registro para um cliente, você deve primeiro estabelecer uma relação com ele. Você deve ter um link exclusivo para fornecer aos seus respectivos clientes. Veja [como estabelecer uma relação OEM.](https://docs.microsoft.com/windows/deployment/windows-autopilot/registration-auth#oem-authorization)

Depois de estabelecer a relação, você pode começar a registrar dispositivos para clientes usando a marca de **Microsoft365Managed_Autopilot**.

> [!IMPORTANT]
> O nome do grupo deve corresponder **Microsoft365Managed_Autopilot** exatamente, incluindo maiúsculas e maiúsculas e caracteres especiais. Isso permitirá que os dispositivos recém-registrados sejam atribuídos com o perfil piloto automático da Área de Trabalho Gerenciada da Microsoft.
