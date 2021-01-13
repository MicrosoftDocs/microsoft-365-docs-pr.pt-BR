---
title: Paridade entre a Proteção de Informações do Azure para o Office 365 operado pela 21Vianet e ofertas comerciais
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
ms.reviewer: arthurj
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- GEU150
- GEA150
description: Saiba mais sobre a Proteção de Informações do Azure (AIP) para o Office 365 operado pela 21Vianet e como configurá-la para clientes na China.
monikerRange: o365-21vianet
ms.openlocfilehash: 50269749b5f4e544263f790ec9c7e4474af57219
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840296"
---
# <a name="parity-between-azure-information-protection-for-office-365-operated-by-21vianet-and-commercial-offerings"></a>Paridade entre a Proteção de Informações do Azure para o Office 365 operado pela 21Vianet e ofertas comerciais

Embora nosso objetivo seja fornecer todos os recursos comerciais e funcionalidades aos clientes na China com nossa AIP (Proteção de Informações do Azure) para a oferta do Office 365 operado pela 21Vianet, há algumas funcionalidades ausentes que queremos destacar.

A lista a seguir inclui as lacunas existentes entre a Proteção de Informações do Azure para o Office 365 operado pela 21Vianet e nossas ofertas comerciais a partir de janeiro de 2021:

- O Gerenciamento de Direitos de Informação (IRM) tem suporte apenas para o Microsoft 365 Apps para empresas (build 11731.10000 ou superior). Não há suporte para o Office 2010, o Office 2013 e outras versões do Office 2016.

- A migração do Active Directory Rights Management Services (AD RMS) para a Proteção de Informações do Azure não está disponível no momento.
  
- Há suporte para o compartilhamento de emails protegidos com usuários na nuvem comercial.
  
- O compartilhamento de documentos e anexos de email para usuários na nuvem comercial não está disponível no momento. Isso inclui usuários do Office 365 operados pela 21Vianet na nuvem comercial, usuários que não são operados pela 21Vianet na nuvem comercial e usuários com uma licença rmS para indivíduos.
  
- O IRM com o SharePoint (bibliotecas e sites protegidos por IRM) não está disponível no momento.
  
- A extensão de dispositivo móvel para AD RMS não está disponível no momento.

- O [Visualizador Móvel](/azure/information-protection/rms-client/mobile-app-faq) não é suportado pelo Azure China 21Vianet.

## <a name="configuring-azure-information-protection-for-customers-in-china"></a>Configurando a Proteção de Informações do Azure para clientes na China

### <a name="enable-rights-management-for-the-tenant"></a>Habilitar o Gerenciamento de Direitos para o locatário

Para que a criptografia funcione corretamente, o RMS deve estar habilitado para o locatário.

- Verifique se o RMS está habilitado:
  1. Iniciar o PowerShell como administrador.
  2. Se o módulo AIPService não estiver instalado, `Install-Module AipService` execute.
  3. Importe o módulo usando `Import-Module AipService` .
  4. Conecte-se ao serviço usando `Connect-AipService -environmentname azurechinacloud` .
  5. Execute `(Get-AipServiceConfiguration).FunctionalState` e verifique se o estado é `Enabled` .

- Se o estado funcional for `Disabled` , execute `Enable-AipService` .

### <a name="dns-configuration-for-encryption-windows"></a>Configuração de DNS para criptografia (Windows)

Para que a criptografia funcione corretamente, os aplicativos cliente do Office devem se conectar à instância da China do serviço e inicializar a partir daí. Para redirecionar aplicativos cliente para a instância de serviço correta, o administrador de locatários deve configurar um registro SRV dns com informações sobre a URL do Azure RMS. Sem o registro SRV de DNS, o aplicativo cliente tentará se conectar à instância de nuvem pública por padrão e falhará.

Além disso, a suposição é de que os usuários entrarão com um nome de usuário baseado no domínio de propriedade do locatário (por exemplo, ), e não com o nome de usuário `joe@contoso.cn` `onmschina` (por exemplo, `joe@contoso.onmschina.cn` ). O nome de domínio do nome de usuário é usado para redirecionamento de DNS para a instância de serviço correta.

- Obter a ID do RMS:
  1. Iniciar o PowerShell como administrador.
  2. Se o módulo AIPService não estiver instalado, `Install-Module AipService` execute.
  3. Conecte-se ao serviço usando `Connect-AipService -environmentname azurechinacloud` .
  4. Execute `(Get-AipServiceConfiguration).RightsManagementServiceId` para obter a ID do RMS.

- Entre no provedor DNS, navegue até as configurações de DNS do domínio e adicione um novo registro SRV.
  - Serviço = `_rmsredir`
  - Protocolo = `_http`
  - Nome = `_tcp`
  - Target = `[GUID].rms.aadrm.cn` (onde GUID é a ID do RMS)
  - Prioridade, Peso, Segundos, TTL = valores padrão

- Associe o domínio personalizado ao locatário no [portal do Azure.](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains) Isso adicionará uma entrada no DNS, que pode levar vários minutos para ser verificada depois que você adicionar o valor às configurações de DNS.

- Entre no centro de administração do Microsoft 365 com as credenciais de administrador global correspondentes e adicione o domínio (por exemplo, `contoso.cn` ) para criação do usuário. No processo de verificação, alterações de DNS adicionais podem ser necessárias. Quando a verificação for feita, os usuários poderão ser criados.

### <a name="dns-configuration-for-encryption-mac-ios-android"></a>Configuração dns para criptografia (Mac, iOS, Android)

Entre no provedor DNS, navegue até as configurações de DNS do domínio e adicione um novo registro SRV.

- Serviço = `_rmsdisco`
- Protocolo = `_http`
- Nome = `_tcp`
- Destino = `api.aadrm.cn`
- Porta = `80`
- Prioridade, Peso, Segundos, TTL = valores padrão

### <a name="aip-client-configuration"></a>Configuração do cliente AIP

O cliente AIP unificado pode ser baixado do Centro [de Download da Microsoft.](https://www.microsoft.com/download/details.aspx?id=53018)

Para saber mais, confira:

- [Documentação da Proteção de Informações do Azure](/azure/information-protection/)
- [Histórico de versão do AIP e política de suporte](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [Requisitos do sistema AIP](/azure/information-protection/requirements)
- [Guia de início rápido do AIP: implantar o cliente AIP](/azure/information-protection/quickstart-deploy-client)
- [Guia do administrador do AIP](/azure/information-protection/rms-client/clientv2-admin-guide)
- [Guia do usuário do AIP](/azure/information-protection/rms-client/clientv2-user-guide)
- [Saiba mais sobre os rótulos de sensibilidade do Microsoft 365](/microsoft-365/compliance/sensitivity-labels)

### <a name="aip-apps-configuration-unified-labeling-client-only"></a>Configuração de aplicativos AIP (apenas cliente de rotulagem unificada)

Para a solução de rotulagem unificada, os aplicativos AIP no Windows precisam da seguinte chave do Registro para apontar para a nuvem soberana correta para o Azure China:

- Nó do Registro = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`
- Nome = `CloudEnvType`
- Valor = `6` (padrão = 0)
- Tipo = `REG_DWORD`

> [!IMPORTANT]
> Certifique-se de não excluir a chave do Registro após uma desinstalação. Se a chave estiver vazia, incorreta ou inexistente, a funcionalidade se comportará como o valor padrão (valor padrão = 0 para a nuvem comercial). Se a chave estiver vazia ou incorreta, um erro de impressão também será adicionado ao log.

### <a name="manage-azure-information-protection-content-scan-jobs"></a>Gerenciar trabalhos de verificação de conteúdo da Proteção de Informações do Azure

Para gerenciar seus trabalhos de verificação de conteúdo da Proteção de Informações do Azure com um servidor de verificação do Azure China, use os seguintes cmdlets em vez do portal do Azure:<br><br>

| Cmdlet | Descrição |
|--|--|
| [Add-AIPScannerRepository](/powershell/module/azureinformationprotection/add-aipscannerrepository) | Adiciona um novo repositório ao seu trabalho de verificação de conteúdo. |
| [Get-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | Obtém detalhes sobre seu trabalho de verificação de conteúdo. |
| [Get-AIPScannerRepository](/powershell/module/azureinformationprotection/get-aipscannerrepository) | Obtém detalhes sobre repositórios definidos para seu trabalho de verificação de conteúdo. |
| [Remove-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | Exclui seu trabalho de verificação de conteúdo. |
| [Remove-AIPScannerRepository](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | Remove um repositório do trabalho de verificação de conteúdo. |
| [Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | Define configurações para seu trabalho de verificação de conteúdo. |
| [Set-AIPScannerRepository](/powershell/module/azureinformationprotection/set-aipscannerrepository) | Define configurações para um repositório existente em seu trabalho de verificação de conteúdo. |

Para obter mais informações, consulte [Gerenciar seus trabalhos de verificação de conteúdo usando apenas o PowerShell.](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer)