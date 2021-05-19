---
title: Suporte à Proteção de Informações do Azure para Office 365 operado pela 21Vianet
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
description: Saiba mais sobre a Proteção de Informações do Azure (AIP) para Office 365 operado pela 21Vianet e como configurá-la para clientes na China.
monikerRange: o365-21vianet
ms.openlocfilehash: 8b85ae43df31bb1947b841d616cc83c3a0b614e4
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52535837"
---
# <a name="azure-information-protection-support-for-office-365-operated-by-21vianet"></a>Suporte à Proteção de Informações do Azure para Office 365 operado pela 21Vianet

Este artigo aborda as diferenças entre o suporte à Proteção de Informações do Azure (AIP) para o Office 365 operado pela 21Vianet e ofertas comerciais, bem como instruções específicas para configurar o AIP para clientes na China, incluindo como instalar o scanner local do AIP e gerenciar trabalhos de verificação de &mdash; conteúdo.

## <a name="differences-between-aip-for-office-365-operated-by-21vianet-and-commercial-offerings"></a>Diferenças entre a AIP para Office 365 operado pela 21Vianet e ofertas comerciais

Embora nosso objetivo seja fornecer todos os recursos comerciais e funcionalidades aos clientes na China com nosso AIP para Office 365 operado pela oferta da 21Vianet, há algumas funcionalidades ausentes que gostaria de destacar.

A lista a seguir inclui as lacunas existentes entre a AIP para Office 365 operado pela 21Vianet e nossas ofertas comerciais a partir de janeiro de 2021:

- O IRM (Gerenciamento de Direitos de Informação) só tem suporte para Microsoft 365 Apps para Grandes Empresas (build 11731.10000 ou superior). Office 2010, Office 2013 e outras versões Office 2016 não são suportadas.

- A migração Active Directory Rights Management Services (AD RMS) para a AIP não está disponível no momento.
  
- Há suporte para o compartilhamento de emails protegidos com usuários na nuvem comercial.
  
- O compartilhamento de documentos e anexos de email com usuários na nuvem comercial não está disponível no momento. Isso inclui Office 365 operado por usuários da 21Vianet na nuvem comercial Office 365, não operados por usuários da 21Vianet na nuvem comercial e usuários com uma licença RMS para Indivíduos.
  
- O IRM com SharePoint (bibliotecas e sites protegidos por IRM) não está disponível no momento.
  
- No momento, a Extensão de Dispositivo Móvel do AD RMS não está disponível.

- O [Visualizador Móvel](/azure/information-protection/rms-client/mobile-app-faq) não é suportado pelo Azure China 21Vianet.

- A área AIP do portal do Azure não está disponível para os clientes na China. Use [comandos do PowerShell em](#step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) vez de executar ações no portal, como gerenciar e executar trabalhos de verificação de conteúdo.

## <a name="configure-aip-for-customers-in-china"></a>Configurar a AIP para clientes na China

Para configurar a AIP para clientes na China:
1. [Habilitar o Gerenciamento de Direitos para o locatário](#step-1-enable-rights-management-for-the-tenant).

1. Adicione a entidade de serviço do Serviço de [Sincronização de Proteção de Informações da Microsoft.](#step-2-add-the-microsoft-information-protection-sync-service-service-principal)

1. [Configurar criptografia DNS](#step-3-configure-dns-encryption).

1. [Instale e configure o cliente de rotulagem unificada do AIP.](#step-4-install-and-configure-the-aip-unified-labeling-client)

1. [Configurar aplicativos AIP em Windows](#step-5-configure-aip-apps-on-windows).

1. [Instale o scanner local do AIP e gerencie trabalhos de verificação de conteúdo.](#step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs) 

### <a name="step-1-enable-rights-management-for-the-tenant"></a>Etapa 1: Habilitar o Gerenciamento de Direitos para o locatário

Para que a criptografia funcione corretamente, o RMS deve estar habilitado para o locatário.

1. Verifique se o RMS está habilitado:

    1. Iniciar o PowerShell como administrador.
    2. Se o módulo AIPService não estiver instalado, execute `Install-Module AipService` .
    3. Importar o módulo usando `Import-Module AipService` .
    4. Conexão ao serviço usando `Connect-AipService -environmentname azurechinacloud` .
    5. Execute `(Get-AipServiceConfiguration).FunctionalState` e verifique se o estado é `Enabled` .

2. Se o estado funcional for `Disabled` , execute `Enable-AipService` .

### <a name="step-2-add-the-microsoft-information-protection-sync-service-service-principal"></a>Etapa 2: Adicionar a entidade de serviço do Serviço de Sincronização de Proteção de Informações da Microsoft

A **entidade de** serviço do Serviço de Sincronização de Proteção de Informações da Microsoft não está disponível nos locatários do Azure China por padrão e é necessária para a Proteção de Informações do Azure.

1. Crie essa entidade de serviço manualmente usando o cmdlet [New-AzADServicePrincipal](/powershell/module/az.resources/new-azadserviceprincipal) e a ID do aplicativo para o Serviço de Sincronização de Proteção de Informações `870c4f2e-85b6-4d43-bdda-6ed9a579b725` da Microsoft. 

    ```powershell 
    New-AzADServicePrincipal -ApplicationId 870c4f2e-85b6-4d43-bdda-6ed9a579b725
    ```

1. Depois de adicionar a entidade de serviço, adicione as permissões relevantes necessárias ao serviço.

### <a name="step-3-configure-dns-encryption"></a>Etapa 3: Configurar criptografia DNS

Para que a criptografia funcione corretamente, Office aplicativos cliente devem se conectar à instância da China do serviço e inicializar a partir daí. Para redirecionar aplicativos cliente para a instância de serviço correta, o administrador do locatário deve configurar um registro SRV DNS com informações sobre a URL do Azure RMS. Sem o registro SRV DNS, o aplicativo cliente tentará se conectar à instância de nuvem pública por padrão e falhará.

Além disso, a suposição é de que os usuários entrarão com um nome de usuário com base no domínio de propriedade do locatário (por exemplo), e não o nome de usuário `joe@contoso.cn` `onmschina` (por exemplo, `joe@contoso.onmschina.cn` ). O nome de domínio do nome de usuário é usado para redirecionamento DNS para a instância de serviço correta.

#### <a name="configure-dns-encryption---windows"></a>Configurar criptografia DNS - Windows

1. Obter a ID do RMS:

    1. Iniciar o PowerShell como administrador.
    2. Se o módulo AIPService não estiver instalado, execute `Install-Module AipService` .
    3. Conexão ao serviço usando `Connect-AipService -environmentname azurechinacloud` .
    4. Execute `(Get-AipServiceConfiguration).RightsManagementServiceId` para obter a ID do RMS.

2. Faça logoff no provedor DNS, navegue até as configurações DNS do domínio e adicione um novo registro SRV.

    - Serviço = `_rmsredir`
    - Protocolo = `_http`
    - Nome = `_tcp`
    - Target = `[GUID].rms.aadrm.cn` (onde GUID é a ID RMS)
    - Prioridade, Peso, Segundos, TTL = valores padrão

3. Associe o domínio personalizado ao locatário no [portal do Azure.](https://portal.azure.cn/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Domains) Isso adicionará uma entrada no DNS, que pode levar vários minutos para ser verificada depois que você adicionar o valor às configurações dns.

4. Entre no centro de administração Microsoft 365 com as credenciais de administrador global correspondentes e adicione o domínio (por exemplo, `contoso.cn` ) para criação do usuário. No processo de verificação, alterações de DNS adicionais podem ser necessárias. Depois que a verificação for feita, os usuários poderão ser criados.

#### <a name="configure-dns-encryption---mac-ios-android"></a>Configurar criptografia DNS - Mac, iOS, Android

Faça logoff no provedor DNS, navegue até as configurações DNS do domínio e adicione um novo registro SRV.

- Serviço = `_rmsdisco`
- Protocolo = `_http`
- Nome = `_tcp`
- Target = `api.aadrm.cn`
- Porta = `80`
- Prioridade, Peso, Segundos, TTL = valores padrão


### <a name="step-4-install-and-configure-the-aip-unified-labeling-client"></a>Etapa 4: Instalar e configurar o cliente de rotulagem unificada do AIP

Baixe e instale o cliente de rotulagem unificada do AIP no [Centro de Download da Microsoft.](https://www.microsoft.com/download/details.aspx?id=53018)

Para mais informações, confira:

- [Documentação do AIP](/azure/information-protection/)
- [Política de suporte e histórico de versão do AIP](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)
- [Requisitos do sistema AIP](/azure/information-protection/requirements)
- [Início rápido da AIP: Implantar o cliente AIP](/azure/information-protection/quickstart-deploy-client)
- [Guia de administrador do AIP](/azure/information-protection/rms-client/clientv2-admin-guide)
- [Guia do usuário AIP](/azure/information-protection/rms-client/clientv2-user-guide)
- [Saiba mais sobre Microsoft 365 rótulos de sensibilidade](../../compliance/sensitivity-labels.md)

### <a name="step-5-configure-aip-apps-on-windows"></a>Etapa 5: Configurar aplicativos AIP em Windows

Os aplicativos AIP Windows a chave do Registro a seguir para apontar para a nuvem soberana correta para o Azure China:

- Nó do Registro = `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIP`
- Nome = `CloudEnvType`
- Valor = `6` (padrão = 0)
- Tipo = `REG_DWORD`

> [!IMPORTANT]
> Certifique-se de não excluir a chave do Registro após uma desinstalação. Se a chave estiver vazia, incorreta ou não existente, a funcionalidade se comportará como o valor padrão (valor padrão = 0 para a nuvem comercial). Se a chave estiver vazia ou incorreta, um erro de impressão também será adicionado ao log.

### <a name="step-6-install-the-aip-on-premises-scanner-and-manage-content-scan-jobs"></a>Etapa 6: instalar o scanner local do AIP e gerenciar trabalhos de verificação de conteúdo

Instale o scanner local do AIP para verificar seus compartilhamentos de rede e conteúdo para dados confidenciais e aplicar rótulos de classificação e proteção conforme configurado na política da sua organização.

Ao configurar e gerenciar seus trabalhos de verificação de conteúdo, use o procedimento a seguir, em vez da interface do portal do [Azure](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only) usada pelas ofertas comerciais.

Para obter mais informações, consulte O que é o scanner unificado de rotulagem da Proteção de Informações do [Azure?](/azure/information-protection/deploy-aip-scanner) e Gerenciar seus trabalhos de verificação de conteúdo usando apenas [o PowerShell](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).

**Para instalar e configurar o scanner**:

1. Entre no computador do Windows Server que executará o scanner. Use uma conta que tenha direitos de administrador local e que tenha permissões para gravar no banco de dados SQL Server mestre.

1. Comece com o PowerShell fechado. Se você instalou o cliente e o scanner AIP anteriormente, certifique-se de que o **serviço AIPScanner** foi interrompido.

1. Abra uma Windows PowerShell com a opção **Executar como** administrador.

1. Execute o cmdlet [Install-AIPScanner,](/powershell/module/azureinformationprotection/Install-AIPScanner) especificando sua instância de SQL Server na qual criar um banco de dados para o scanner da Proteção de Informações do Azure e um nome significativo para o cluster do scanner.

    ```PowerShell
    Install-AIPScanner -SqlServerInstance <name> -Cluster <cluster name>
    ```

    > [!TIP]
    > Você pode usar o mesmo nome de cluster no [comando Install-AIPScanner](/powershell/module/azureinformationprotection/install-aipscanner) para associar vários nós de scanner ao mesmo cluster. Usar o mesmo cluster para vários nós de scanner permite que vários scanners trabalhem juntos para executar suas verificações.
    > 

1. Verifique se o serviço agora está instalado usando o **Administrative Tools**  >  **Services**.

    O serviço instalado chama-se Scanner de Proteção de Informações do **Azure** e é configurado para ser executado usando a conta de serviço de scanner que você criou.

1. Obter um token do Azure a ser usado com o scanner. Um token do Azure AD permite que o scanner se autenture no serviço de Proteção de Informações do Azure, permitindo que o scanner seja executado de forma não interativa. 

    1. Abra o portal do Azure e crie um aplicativo do Azure AD para especificar um token de acesso para autenticação. Para obter mais informações, [consulte How to label files non-interactively for Azure Information Protection](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection).
    
        > [!TIP]
        > Ao criar e configurar **aplicativos** do Azure AD para o comando [Set-AIPAuthentication,](/powershell/module/azureinformationprotection/set-aipauthentication) o painel Permissões de API de Solicitação mostra as **APIs** que minha organização usa guia em vez da guia **APIs** da Microsoft. Selecione as **APIs que minha organização usa** para selecionar os Serviços de Gerenciamento de Direitos do **Azure.** 
        >

    1. No computador Windows Server, se sua conta de serviço de scanner tiver sido concedida o **Logon** localmente à direita para a instalação, entre com essa conta e inicie uma sessão do PowerShell. 
    
        Se sua conta de serviço de scanner não puder ser concedida ao **Log** localmente correto para a instalação, use o parâmetro *OnBehalfOf* com [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication), conforme descrito em Como rotular arquivos de forma não interativa para a Proteção de Informações do [Azure.](/azure/information-protection/rms-client/clientv2-admin-guide-powershell#how-to-label-files-non-interactively-for-azure-information-protection)

    1. Execute [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication), especificando valores copiados do seu aplicativo do Azure AD:

      ```PowerShell
      Set-AIPAuthentication -AppId <ID of the registered app> -AppSecret <client secret sting> -TenantId <your tenant ID> -DelegatedUser <Azure AD account>
      ```

      Por exemplo:

      ```PowerShell
      $pscreds = Get-Credential CONTOSO\scanner
      Set-AIPAuthentication -AppId "77c3c1c3-abf9-404e-8b2b-4652836c8c66" -AppSecret "OAkk+rnuYc/u+]ah2kNxVbtrDGbS47L4" -DelegatedUser scanner@contoso.com -TenantId "9c11c87a-ac8b-46a3-8d5c-f4d0b72ee29a" -OnBehalfOf $pscreds
      Acquired application access token on behalf of CONTOSO\scanner.
      ```

    O scanner agora tem um token para autenticar no Azure AD. Esse token é válido por um ano, dois anos ou nunca, de acordo com a configuração do segredo do cliente do **aplicativo Web /API** no Azure AD. Quando o token expirar, você deverá repetir este procedimento.

1. Execute o cmdlet [Set-AIPScannerConfiguration](/powershell/module/azureinformationprotection/set-aipscannerconfiguration) para definir o scanner para funcionar no modo offline. Executar:

    ```powershell
    Set-AIPScannerConfiguration -OnlineConfiguration Off
    ```

1. Execute o cmdlet [Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) para criar um trabalho de verificação de conteúdo padrão.

    O único parâmetro necessário no cmdlet **Set-AIPScannerContentScanJob** é **Enforce**. No entanto, talvez você queira definir outras configurações para seu trabalho de verificação de conteúdo no momento. Por exemplo:

    ```powershell
    Set-AIPScannerContentScanJob -Schedule Manual -DiscoverInformationTypes PolicyOnly -Enforce Off -DefaultLabelType PolicyDefault -RelabelFiles Off -PreserveFileDetails On -IncludeFileTypes '' -ExcludeFileTypes '.msg,.tmp' -DefaultOwner <account running the scanner>
    ```

    A sintaxe acima configura as seguintes configurações enquanto você continua a configuração:

    - Mantém o agendamento de executar o scanner para *manual*
    - Define os tipos de informações a serem descobertos com base na política de rotulagem de sensibilidade
    - Não *impõe* uma política de rotulagem de sensibilidade
    - Rotula automaticamente arquivos com base no conteúdo, usando o rótulo padrão definido para a política de rotulagem de sensibilidade
    - Não *permite* o relabeleamento de arquivos
    - Preserva os detalhes do arquivo durante a verificação e rotulagem automática, incluindo a data *modificada*, *a última* modificação e *a modificação por* valores
    - Define o scanner para excluir arquivos .msg e .tmp ao executar
    - Define o proprietário padrão como a conta que você deseja usar ao executar o scanner

1. Use o cmdlet [Add-AIPScannerRepository](/powershell/module/azureinformationprotection/add-aipscannerrepository) para definir os repositórios que você deseja examinar no trabalho de verificação de conteúdo. Por exemplo, execute:

    ```powershell
    Add-AIPScannerRepository -OverrideContentScanJob Off -Path 'c:\repoToScan'
    ```
    
    Use uma das seguintes sintaxes, dependendo do tipo de repositório que você está adicionando:

    - Para um compartilhamento de rede, use `\\Server\Folder` .
    - Para uma SharePoint, use `http://sharepoint.contoso.com/Shared%20Documents/Folder` .
    - Para um caminho local: `C:\Folder`
    - Para um caminho UNC: `\\Server\Folder`

    > [!NOTE]
    > Não há suporte para caracteres curinga e locais WebDav não são suportados.
    >
    > Para modificar o repositório posteriormente, use o cmdlet [Set-AIPScannerRepository.](/powershell/module/azureinformationprotection/set-aipscannerrepository) 


Continue com as seguintes etapas conforme necessário:

- [Executar um ciclo de descoberta e exibir relatórios do scanner](/azure/information-protection/deploy-aip-scanner-manage#run-a-discovery-cycle-and-view-reports-for-the-scanner)
- [Usar o PowerShell para configurar o scanner para aplicar classificação e proteção](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only#use-powershell-to-configure-the-scanner-to-apply-classification-and-protection)
- [Usar o PowerShell para configurar uma política de DLP com o scanner](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=azure-portal-only#use-powershell-to-configure-a-dlp-policy-with-the-scanner)

A tabela a seguir lista os cmdlets do PowerShell relevantes para instalar o scanner e gerenciar seus trabalhos de verificação de conteúdo:

| Cmdlet | Descrição |
|--|--|
| [Add-AIPScannerRepository](/powershell/module/azureinformationprotection/add-aipscannerrepository) | Adiciona um novo repositório ao trabalho de verificação de conteúdo. |
| [Get-AIPScannerConfiguration](/powershell/module/azureinformationprotection/get-aipscannerconfiguration)|Retorna detalhes sobre seu cluster. |
| [Get-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/get-aipscannercontentscanjob) | Obtém detalhes sobre seu trabalho de verificação de conteúdo. |
| [Get-AIPScannerRepository](/powershell/module/azureinformationprotection/get-aipscannerrepository) | Obtém detalhes sobre repositórios definidos para seu trabalho de verificação de conteúdo. |
| [Remove-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/remove-aipscannercontentscanjob) | Exclui seu trabalho de verificação de conteúdo. |
| [Remove-AIPScannerRepository](/powershell/module/azureinformationprotection/remove-aipscannerrepository) | Remove um repositório do trabalho de verificação de conteúdo. |
| [Set-AIPScannerContentScanJob](/powershell/module/azureinformationprotection/set-aipscannercontentscanjob) | Define configurações para seu trabalho de verificação de conteúdo. |
| [Set-AIPScannerRepository](/powershell/module/azureinformationprotection/set-aipscannerrepository) | Define configurações para um repositório existente em seu trabalho de verificação de conteúdo. |
| | |

Para mais informações, confira:

- [O que é o scanner unificado de rotulagem da Proteção de Informações do Azure?](/azure/information-protection/deploy-aip-scanner)
- [Configurando e instalando o scanner unificado de rotulagem da Proteção de Informações do Azure (AIP)](/azure/information-protection/deploy-aip-scanner-configure-install?tabs=powershell-only)
- [Gerencie seus trabalhos de verificação de conteúdo usando apenas o PowerShell](/azure/information-protection/deploy-aip-scanner-prereqs#use-powershell-with-a-disconnected-computer).
