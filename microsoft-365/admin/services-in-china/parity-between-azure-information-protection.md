---
title: Suporte à Proteção de Informações do Azure para o Office 365 operado pela 21Vianet
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
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
ms.openlocfilehash: 77790249cbd544b2f11e9a16dd77bab297cac509
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914313"
---
# <a name="azure-information-protection-support-for-office-365-operated-by-21vianet"></a>Suporte à Proteção de Informações do Azure para o Office 365 operado pela 21Vianet

Este artigo aborda as diferenças entre o suporte à Proteção de Informações do Azure (AIP) para o Office 365 operado pela 21Vianet e ofertas comerciais, bem como instruções específicas para configurar a AIP para clientes na China, incluindo como instalar o scanner local do AIP e gerenciar trabalhos de verificação de &mdash; conteúdo.

## <a name="differences-between-aip-for-office-365-operated-by-21vianet-and-commercial-offerings"></a>Diferenças entre a AIP para o Office 365 operado pela 21Vianet e ofertas comerciais

Embora nosso objetivo seja fornecer todos os recursos comerciais e funcionalidades aos clientes na China com nossa oferta AIP para Office 365 operado pela 21Vianet, há algumas funcionalidades ausentes que gostaria de destacar.

A lista a seguir inclui as lacunas existentes entre a AIP para o Office 365 operado pela 21Vianet e nossas ofertas comerciais a partir de janeiro de 2021:

- O IRM (Gerenciamento de Direitos de Informação) só tem suporte para Aplicativos do Microsoft 365 para empresas (build 11731.10000 ou superior). Não há suporte para Office 2010, Office 2013 e outras versões do Office 2016.

- A migração Active Directory Rights Management Services (AD RMS) para a AIP não está disponível no momento.
  
- Há suporte para o compartilhamento de emails protegidos com usuários na nuvem comercial.
  
- O compartilhamento de documentos e anexos de email com usuários na nuvem comercial não está disponível no momento. Isso inclui o Office 365 operado por usuários da 21Vianet na nuvem comercial, não o Office 365 operado por usuários da 21Vianet na nuvem comercial e usuários com uma licença RMS para Indivíduos.
  
- O IRM com o SharePoint (sites e bibliotecas protegidos por IRM) não está disponível no momento.
  
- No momento, a Extensão de Dispositivo Móvel do AD RMS não está disponível.

- O [Visualizador Móvel](/azure/information-protection/rms-client/mobile-app-faq) não é suportado pelo Azure China 21Vianet.

- A área AIP do portal do Azure não está disponível para os clientes na China. Use [comandos do PowerShell](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) em vez de executar ações no portal, como instalar o scanner local e gerenciar seus trabalhos de verificação de conteúdo.

## <a name="configure-aip-for-customers-in-china"></a>Configurar a AIP para clientes na China

Para configurar a AIP para clientes na China:
1. [Habilitar o Gerenciamento de Direitos para o locatário](#step-1-enable-rights-management-for-the-tenant).

2. [Configurar criptografia DNS](#step-2-configure-dns-encryption).

3. [Instale e configure o cliente de rotulagem unificada do AIP.](#step-3-install-and-configure-the-aip-unified-labeling-client)

4. [Configurar aplicativos AIP no Windows](#step-4-configure-aip-apps-on-windows).

5. [Instale o scanner local do AIP e gerencie trabalhos de verificação de conteúdo.](#step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) 

### <a name="step-1-enable-rights-management-for-the-tenant"></a>Etapa 1: Habilitar o Gerenciamento de Direitos para o locatário

Para que a criptografia funcione corretamente, o RMS deve estar habilitado para o locatário.

1. Verifique se o RMS está habilitado:

    1. Iniciar o PowerShell como administrador.
    2. Se o módulo AIPService não estiver instalado, execute `Install-Module AipService` .
    3. Importar o módulo usando `Import-Module AipService` .
    4. Conecte-se ao serviço usando `Connect-AipService -environmentname azurechinacloud` .
    5. Execute `(Get-AipServiceConfiguration).FunctionalState` e verifique se o estado é `Enabled` .

2. Se o estado funcional for `Disabled` , execute `Enable-AipService` .

### <a name="step-2-configure-dns-encryption"></a>Etapa 2: Configurar criptografia DNS

Para que a criptografia funcione corretamente, os aplicativos cliente do Office devem se conectar à instância da China do serviço e inicializar a partir daí. Para redirecionar aplicativos cliente para a instância de serviço correta, o administrador do locatário deve configurar um registro SRV DNS com informações sobre a URL do Azure RMS. Sem o registro SRV DNS, o aplicativo cliente tentará se conectar à instância de nuvem pública por padrão e falhará.

Além disso, a suposição é de que os usuários entrarão com um nome de usuário com base no domínio de propriedade do locatário (por exemplo), e não o nome de usuário `joe@contoso.cn` `onmschina` (por exemplo, `joe@contoso.onmschina.cn` ). O nome de domínio do nome de usuário é usado para redirecionamento DNS para a instância de serviço correta.

#### <a name="configure-dns-encryption---windows"></a>Configurar criptografia DNS - Windows

1. Obter a ID do RMS:

    1. Iniciar o PowerShell como administrador.
    2. Se o módulo AIPService não estiver instalado, execute `Install-Module AipService` .
    3. Conecte-se ao serviço usando `Connect-AipService -environmentname azurechinacloud` .
    4. Execute `(Get-AipServiceConfiguration).RightsManagementServiceId` para obter a ID do RMS.

2. Faça logoff no provedor DNS, navegue até as configurações DNS do domínio e adicione um novo registro SRV.

    - Serviço = `_rmsredir`
    - Protocolo = `_http`
    - Nome = `_tcp`
    - Target = `[GUID].rms.aadrm.cn` (onde GUID é a ID RMS)
    - Prioridade, Peso, Segundos, TTL = valores padrão

3. Associe o domínio personalizado ao locatário no [portal do Azure.](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains) Isso adicionará uma entrada no DNS, que pode levar vários minutos para ser verificada depois que você adicionar o valor às configurações dns.

4. Faça logoff no Centro de administração do Microsoft 365 com as credenciais de administrador global correspondentes e adicione o domínio (por exemplo, `contoso.cn` ) para criação do usuário. No processo de verificação, alterações de DNS adicionais podem ser necessárias. Depois que a verificação for feita, os usuários poderão ser criados.

#### <a name="configure-dns-encryption---mac-ios-android"></a>Configurar criptografia DNS - Mac, iOS, Android

Faça logoff no provedor DNS, navegue até as configurações DNS do domínio e adicione um novo registro SRV.

- Serviço = `_rmsdisco`
- Protocolo = `_http`
- Nome = `_tcp`
- Target = `api.aadrm.cn`
- Porta = `80`
- Prioridade, Peso, Segundos, TTL = valores padrão

### <a name="step-3-install-and-configure-the-aip-unified-labeling-client"></a>Etapa 3: Instalar e configurar o cliente de rotulagem unificada do AIP

Baixe o cliente de rotulagem unificada do AIP no [Centro de Download da Microsoft.](https://www.microsoft.com/download/details.aspx?id=53018)

Para mais informações, confira:

- [Documentação do AIP](/azure/information-protection/)
- [Política de suporte e histórico de versão do AIP](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [Requisitos do sistema AIP](/azure/information-protection/requirements)
- [Início rápido da AIP: Implantar o cliente AIP](/azure/information-protection/quickstart-deploy-client)
- [Guia de administrador do AIP](/azure/information-protection/rms-client/clientv2-admin-guide)
- [Guia do usuário AIP](/azure/information-protection/rms-client/clientv2-user-guide)
- [Saiba mais sobre rótulos de sensibilidade do Microsoft 365](../../compliance/sensitivity-labels.md)

### <a name="step-4-configure-aip-apps-on-windows"></a>Etapa 4: Configurar aplicativos AIP no Windows

Os aplicativos AIP no Windows precisam da seguinte chave do Registro para apontar para a nuvem soberana correta para o Azure China:

- Nó do Registro = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`
- Nome = `CloudEnvType`
- Valor = `6` (padrão = 0)
- Tipo = `REG_DWORD`

> [!IMPORTANT]
> Certifique-se de não excluir a chave do Registro após uma desinstalação. Se a chave estiver vazia, incorreta ou não existente, a funcionalidade se comportará como o valor padrão (valor padrão = 0 para a nuvem comercial). Se a chave estiver vazia ou incorreta, um erro de impressão também será adicionado ao log.

### <a name="step-5-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs"></a>Etapa 5: instalar o scanner local do AIP e gerenciar trabalhos de verificação de conteúdo

Instale o scanner local do AIP para verificar seus compartilhamentos de rede e conteúdo para dados confidenciais e aplicar rótulos de classificação e proteção conforme configurado na política da sua organização.

Ao instalar o scanner e gerenciar seus trabalhos de verificação de conteúdo, use os seguintes cmdlets em vez da interface do portal do Azure usada pelas ofertas comerciais:<br><br>

| Cmdlet | Descrição |
|--|--|
| [Add-AIPScannerRepository](/powershell/module/azureinformationprotection/add-aipscannerrepository) | Adiciona um novo repositório ao trabalho de verificação de conteúdo. |
| [Get-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | Obtém detalhes sobre seu trabalho de verificação de conteúdo. |
| [Get-AIPScannerRepository](/powershell/module/azureinformationprotection/get-aipscannerrepository) | Obtém detalhes sobre repositórios definidos para seu trabalho de verificação de conteúdo. |
| [Remove-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | Exclui seu trabalho de verificação de conteúdo. |
| [Remove-AIPScannerRepository](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | Remove um repositório do trabalho de verificação de conteúdo. |
| [Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | Define configurações para seu trabalho de verificação de conteúdo. |
| [Set-AIPScannerRepository](/powershell/module/azureinformationprotection/set-aipscannerrepository) | Define configurações para um repositório existente em seu trabalho de verificação de conteúdo. |

Para obter mais informações, consulte O que é o scanner unificado de rotulagem da Proteção de Informações do [Azure?](/azure/information-protection/deploy-aip-scanner) e Gerenciar seus trabalhos de verificação de conteúdo usando apenas [o PowerShell](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).