---
title: Office 365 operado pela 21Vianet
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: mnirkhe
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
search.appverid:
- MET150
- GEU150
- GEA150
description: Saiba mais sobre o Azure Information Protection para Office 365 operado pela 21Vianet e como configurá-lo para os clientes da China.
monikerRange: o365-21vianet
ms.openlocfilehash: a4eb8c3370a123b939fdccc53eec3905f79ee806
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42237814"
---
# <a name="parity-between-azure-information-protection-for-office-365-operated-by-21vianet-and-commercial-offerings"></a>Paridade entre a proteção de informações do Azure para Office 365 operado pela 21Vianet e ofertas comerciais

Enquanto o nosso objetivo é fornecer todos os recursos e funcionalidades comerciais aos clientes da China com nossa proteção de informações do Azure para Office 365 operado pela 21Vianet, há algumas funcionalidades que gostaríamos de destacar.

Essas são as lacunas existentes entre a proteção de informações do Azure para Office 365 operado pela 21Vianet e nossas ofertas comerciais a partir de julho de 2019:

- O gerenciamento de direitos de informação (IRM) só tem suporte no Office 365 ProPlus (Build 11731,10000 ou superior). O Office 2010, o Office 2013 e outras versões do Office 2016 não têm suporte.

- A migração do Active Directory Rights Management Services (AD RMS) para a proteção de informações do Azure não está disponível no momento.
  
- Há suporte para o compartilhamento de emails protegidos para os usuários na nuvem comercial.
  
- O compartilhamento de documentos e anexos de email para usuários na nuvem comercial não está disponível no momento. Isso inclui o Office 365 operado pela 21Vianet Users na nuvem comercial, não-Office 365 operado pela 21Vianet Users na nuvem comercial e usuários com um RMS para licença de pessoas.
  
- O IRM com o SharePoint (sites e bibliotecas protegidas por IRM) não está disponível no momento.
  
- O conector de gerenciamento de direitos não está disponível no momento.
  
- A extensão do dispositivo móvel para AD RMS não está disponível no momento.

## <a name="configuring-azure-information-protection-for-customers-in-china"></a>Configurando a proteção de informações do Azure para clientes na China

### <a name="enable-rights-management-for-the-tenant"></a>Habilitar o gerenciamento de direitos para o locatário

Para que a criptografia funcione corretamente, o RMS deve estar habilitado para o locatário.

- Verifique se o RMS está habilitado:
  1. Inicie o PowerShell como administrador.
  2. Se o módulo AIPService não estiver instalado, execute `Install-Module AipService`.
  3. Importe o módulo usando `Import-Module AipService`o.
  4. Conecte-se ao serviço `Connect-AipService -environmentname azurechinacloud`usando.
  5. Executar `(Get-AipServiceConfiguration).FunctionalState` e verificar se o estado é `Enabled`.

- Se o estado funcional for `Disabled`, execute `Enable-AipService`.

### <a name="dns-configuration-for-encryption-windows"></a>Configuração de DNS para criptografia (Windows)

Para que a criptografia funcione corretamente, os aplicativos clientes do Office devem se conectar à instância da China do serviço e inicializar a partir daí. Para redirecionar aplicativos cliente para a instância de serviço correta, o administrador de locatários deve configurar um registro SRV de DNS com informações sobre a URL do Azure RMS. Sem o registro SRV do DNS, o aplicativo cliente tentará se conectar à instância da nuvem pública por padrão e falhará.

Além disso, a pressuposição é que os usuários farão logon com um nome de usuário com base no domínio de Propriedade do `joe@contoso.cn`locatário (por exemplo, `onmschina` ) e não no nome `joe@contoso.onmschina.cn`de usuário (por exemplo,). O nome de domínio do nome de usuário é usado para o redirecionamento de DNS para a instância de serviço correta.

- Obter a ID do RMS:
  1. Inicie o PowerShell como administrador.
  2. Se o módulo AIPService não estiver instalado, execute `Install-Module AipService`.
  3. Conecte-se ao serviço `Connect-AipService -environmentname azurechinacloud`usando.
  4. Execute `(Get-AipServiceConfiguration).RightsManagementServiceId` para obter a ID do RMS.

- Faça logon no seu provedor de DNS, navegue até as configurações de DNS para o domínio e, em seguida, adicione um novo registro SRV.
  - Serviço = `_rmsredir`
  - Protocolo = `_http`
  - Nome = `_tcp`
  - Target = `[GUID].rms.aadrm.cn` (onde GUID é a ID do RMS)
  - Prioridade, peso, segundos, TTL = valores padrão

- Associe o domínio personalizado ao locatário no [portal do Azure](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains). Isso adicionará uma entrada no DNS, que pode levar alguns minutos para ser verificada depois que você adicionar o valor às configurações de DNS.

- Faça logon no centro de administração do Microsoft 365 com as credenciais de administrador global correspondentes e adicione o domínio (por `contoso.cn`exemplo,) para a criação de usuários. No processo de verificação, alterações adicionais de DNS podem ser necessárias. Após a verificação ser concluída, os usuários podem ser criados.

### <a name="dns-configuration-for-encryption-mac-ios-android"></a>Configuração de DNS para criptografia (Mac, iOS, Android)

- Faça logon no seu provedor de DNS, navegue até as configurações de DNS para o domínio e, em seguida, adicione um novo registro SRV.
  - Serviço = `_rmsdisco`
  - Protocolo = `_http`
  - Nome = `_tcp`
  - Target = `api.aadrm.cn`
  - Porta = `80`
  - Prioridade, peso, segundos, TTL = valores padrão
