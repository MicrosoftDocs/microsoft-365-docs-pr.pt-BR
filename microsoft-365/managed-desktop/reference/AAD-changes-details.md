---
title: Detalhes do locatário do Azure Active Directory
description: Este tópico descreve as alterações feitas na sua conta do AAD quando você se inscreve na área de trabalho gerenciada da Microsoft
keywords: Área de trabalho gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.openlocfilehash: 6b2b30d8dedba1086bfa9268fb0fdbce20367c20
ms.sourcegitcommit: dd426c686b52cf79325f11022b2d99bc45285577
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2019
ms.locfileid: "35643942"
---
# <a name="azure-active-directory-tenant-details"></a>Detalhes do locatário do Azure Active Directory
{Gory detalhes sobre contas, chamadas de API, perms etc., etc.}


## <a name="data-transmitted-to-and-from-your-aad-account"></a>Dados transmitidos de e para a sua conta do AAD


Dados enviados à sua conta da Microsoft:

- Nomes de grupo
- Configuração de política de segurança
- Pedidos de dispositivos
- Contas de usuário (MSadmin, MSTest, mwaas_soc_ro, mwaas_wdgsoc)
- Atribuição de licença E5 para as contas de usuário
- Diretivas do Windows Update para toques de atualização

Dados enviados à Microsoft da sua conta:

- Dados de atualização de dispositivo, uso e confiabilidade
- Dados de implantação e confiabilidade de aplicativos
- Atualização e dados de implantação de política de segurança
- Usuários atribuídos a dispositivos  

Os dados transmitidos de sua conta são armazenados em bancos de dados SQL do Azure no Microsoft locatário hospedado nos EUA. Os dados são armazenados e manipulados de acordo com as políticas descritas em {segurança do Microsoft Azure}. 

## <a name="api-permissions-and-calls"></a>Permissões e chamadas de API

**Durante o registro:**

Permissões de API:
- DeviceManagementServiceConfig.ReadWrite.All
- Directory.AccessAsUser.All
- User.ReadWrite.All
- DeviceManagementConfiguration.ReadWrite.All
- DeviceManagementManagedDevices.ReadWrite.All
- Group.ReadWrite.All

Chamadas de API:
- POSTAR/organization/{organizationId}/setMobileDeviceManagementAuthority
- GET/POST/directoryRoles/{id}/members
- GET/POST/Users
- GET/POST/groups
- PATCH/groups/{ID}
- GET/POST/deviceManagement/deviceConfigurations
- OBTER/deviceManagement/detectedApps

**Após o registro, durante o gerenciamento comum:**

Permissões de API:
- DeviceManagementManagedDevices.ReadWrite.All
- DeviceManagementApps.ReadWrite.All
- DeviceManagementConfiguration.ReadWrite.All
- Reports.Read.All
- User.ReadWrite.All
- Group.ReadWrite.All
- Directory.AccessAsUser.All

Chamadas de API:
- GET/POST/directoryRoles/{id}/members
- GET/PATCH/POST/Users
- GET/POST/groups
- PATCH/groups/{ID}
- GET/POST/deviceManagement/deviceConfigurations
- GET/POST/deviceAppManagement/mobileApps
- OBTER/deviceManagement/detectedApps
- OBTER/Devices
- POST/Users/{ID | userPrincipalName}/assignLicense
- OBTER/subscribedSkus

## <a name="accounts-used-by-microsoft-managed-desktop"></a>Contas usadas pela área de trabalho gerenciada da Microsoft





| Conta | Descrição  | Acesso condicional  | Multi-factor Authentication  | Por que isso é certo |
|---------|---------|---------|---------|--------------|
| MSadmin @ * onmmicrosoft. com | Conta de serviço limitada com privilégios de administrador, usada como um Microsoft Intune e administrador de usuários {What ' s This?} para definir e configurar o locatário para dispositivos de área de trabalho modernos da Microsoft.Não tem permissões de logon interativas; realiza operações apenas por meio do serviço.  | Excluído, pois ele não é proveniente de sua rede        | Excluído porque não há logon interativo        | Senha armazenada no Azure Key Vault |
| MSTest @ * onmmicrosoft. com     |         |         |         |
| mssupport @ * onmmicrosoft. com     |         |         |         |
| msadminint @ * onmmicrosoft. com     |         |         |         |
