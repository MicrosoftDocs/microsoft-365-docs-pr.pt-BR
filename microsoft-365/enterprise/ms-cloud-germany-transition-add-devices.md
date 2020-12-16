---
title: Informações adicionais sobre o dispositivo para a migração do Microsoft Cloud Alemanha
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 'Resumo: informações adicionais sobre o dispositivo em serviços ao migrar do Microsoft Cloud Alemanha (Microsoft Cloud Alemanha) para os serviços do Office 365 na nova região do datacenter alemão.'
ms.openlocfilehash: 1bbb4bf39db61a93844c21cd6062a70699b5d6d7
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688648"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a>Informações adicionais sobre o dispositivo para a migração do Microsoft Cloud Alemanha

## <a name="frequently-asked-questions"></a>Perguntas frequentes

**Como saber se minha organização é afetada?**

Os administradores devem verificar `https://portal.microsoftazure.de` se possuem dispositivos registrados. Se sua organização tiver dispositivos registrados, você será afetado.

**Qual é o impacto nos meus usuários?**

Os usuários de um dispositivo registrado não poderão mais entrar depois que sua migração entrar na fase [finalizar migração do Azure ad](ms-cloud-germany-transition.md#how-is-the-migration-organized) .  

Verifique se todos os seus dispositivos estão registrados com o ponto de extremidade Mundial antes que sua organização seja desconectada do Microsoft Cloud Alemanha.
  
**Quando meus usuários registrarem seus dispositivos novamente?**

É fundamental para o seu sucesso que você só cancele o registro e registre novamente os dispositivos durante a fase [separada da migração do Microsoft Cloud Alemanha](ms-cloud-germany-transition.md#how-is-the-migration-organized) .

**Como faço para restaurar o estado do dispositivo após a migração?**

Para dispositivos do Windows híbridos associados do Azure AD e de propriedade da empresa registrados no Azure AD, os administradores poderão gerenciar a migração desses dispositivos por meio de fluxos de trabalho acionados remotamente que cancelarão o registro dos Estados de dispositivos antigos.
  
Para todos os outros dispositivos, incluindo dispositivos do Windows pessoais registrados no Azure AD, o usuário final deve executar essas etapas manualmente. Para dispositivos associados ao Azure AD, os usuários precisam ter uma conta de administrador local para cancelar o registro e, em seguida, registrar novamente seus dispositivos.

A Microsoft publicará instruções sobre como restaurar o estado do dispositivo com êxito. 
 
**Como saber se todos os meus dispositivos estão registrados na nuvem pública?**

Para verificar se seus dispositivos estão registrados na nuvem pública, você deve exportar e baixar a lista de dispositivos do portal do Azure AD para uma planilha do Excel. Em seguida, filtre os dispositivos registrados (usando a coluna _registeredtime_ ) depois da fase [separada da migração do Microsoft Cloud Alemanha](ms-cloud-germany-transition.md#how-is-the-migration-organized) .

O registro do dispositivo é desativado após a migração do locatário e não pode ser habilitado ou desabilitado. Se o Intune não for usado, entre na sua assinatura e execute este comando para reativar a opção:

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

## <a name="windows-hybrid-azure-ad-join"></a>Ingresso no Azure AD híbrido do Windows

### <a name="windows-down-level"></a>Nível inferior do Windows

Os _dispositivos de nível inferior do Windows_ são dispositivos do Windows que atualmente executam versões anteriores do Windows (como o Windows 8,1 ou Windows 7) ou que executam versões anteriores ao 2019 e 2016 do Windows Server. Se esses dispositivos foram registrados antes, você precisará cancelar o registro e registrar novamente esses dispositivos. 

Para determinar se um dispositivo de nível inferior do Windows foi previamente Unido ao Azure AD, use o seguinte comando no dispositivo:

```console
%programfiles%\Microsoft Workplace Join\autoworkplace /status
```

Se o dispositivo tiver ingressado anteriormente no Azure AD e se o dispositivo tiver conectividade de rede para os pontos de extremidade globais do Azure AD, você verá o seguinte resultado:

```console
+----------------------------------------------------------------------+
| Device Details                                                       |
+----------------------------------------------------------------------+
         DeviceId : AEE2B956-DA62-48D0-BB47-046DD992A110
       Thumbprint : 00fdfa2de5c32feae57489873a13aa6a3ff7433b
             User : user1@<tenantname>.de
Private key state : Okay
     Device state : Unknown
```

Os dispositivos afetados terão o "estado do dispositivo" com o valor "desconhecido". Se a saída for "dispositivo não Unido" ou cujo valor "estado do dispositivo" for "OK", ignore as orientações a seguir.

Somente para dispositivos que mostram que o dispositivo é associado (por meio de DeviceID, impressão digital e assim por diante) e cujo valor de "estado do dispositivo" é "desconhecido", os administradores devem executar o seguinte comando no contexto de um usuário de domínio que faz logon em um dispositivo de nível inferior:

```console
"%programfiles%\Microsoft Workplace Join\autoworkplace /leave"
```

O comando anterior só precisa ser executado uma vez por usuário de logon no dispositivo de nível inferior do Windows. Este comando deve ser executado no contexto da entrada de usuário do domínio. 

Deve-se ter cuidado para não executar este comando quando o usuário entrar subsequentemente. Quando o comando anterior é executado, ele limpa o estado de ingresso do computador local híbrido do Azure AD associado para o usuário que entrou. E, se o computador ainda estiver configurado para ser híbrido o Azure AD – Unido no locatário, ele tentará ingressar quando o usuário entrar novamente.

### <a name="windows-current"></a>Windows atual

#### <a name="unjoin"></a>Não ingressar

Para determinar se o dispositivo Windows 10 foi previamente Unido ao Azure AD, execute o seguinte comando no dispositivo:

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

Se o dispositivo for associado ao Azure AD – híbrido, o administrador veria o seguinte resultado:

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : YES
```

Se a saída for "AzureAdJoined: no", ignore as orientações a seguir.

Somente para dispositivos que mostram que o dispositivo está associado ao Azure AD, execute o seguinte comando como administrador para remover o estado de ingresso do dispositivo.

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

O comando anterior só precisa ser executado uma vez em um contexto administrativo no dispositivo Windows.

#### <a name="hybrid-ad-joinre-registration"></a>ANÚNCIO híbrido Join\Re-Registration

O dispositivo é automaticamente Unido ao Azure AD sem intervenção de usuário ou administrador, desde que o dispositivo tenha conectividade de rede para pontos de extremidade globais do Azure AD. 


## <a name="windows-azure-ad-join"></a>Ingresso no Windows Azure AD

**Importante:** A entidade de serviço do Intune será habilitada após a migração do Commerce, que envolve a ativação do registro de dispositivos do Azure AD. Se você bloqueou o registro de dispositivos do Azure AD antes da migração, você deve desabilitar a entidade de serviço do Intune com o PowerShell para desabilitar o registro de dispositivos do Azure AD com o portal do Azure AD. Você pode desabilitar a entidade de serviço do Intune com este comando no módulo PowerShell do Azure Active Directory para Graph.

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

### <a name="unjoin"></a>Não ingressar

Para determinar se o dispositivo Windows 10 foi previamente Unido ao Azure AD, o usuário ou administrador pode executar o seguinte comando no dispositivo:

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

Se o dispositivo estiver Unido ao Azure AD, o usuário ou administrador veria o seguinte resultado:

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : NO
```

Se a saída for "AzureAdJoined: NO", ignore as orientações a seguir.

Usuário: se o dispositivo for associado ao Azure AD, um usuário pode sair do dispositivo das configurações. Verifique se há uma conta de administrador local no dispositivo antes de não ingressar no dispositivo do Azure AD. A conta de administrador local é necessária para entrar no dispositivo novamente.

Administrador: se o administrador da organização quiser desassociar os dispositivos dos usuários que estão associados ao Azure AD, eles poderão fazê-lo executando o seguinte comando em cada um dos dispositivos usando um mecanismo como diretiva de grupo. O administrador deve verificar se há uma conta de administrador local no dispositivo antes de sair do dispositivo do Azure AD. A conta de administrador local é necessária para entrar no dispositivo novamente.

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

O comando anterior só precisa ser executado uma vez em um contexto administrativo no dispositivo Windows. 

### <a name="azure-ad-joinre-registration"></a>Ingresso/reinscrição do Azure AD

O usuário pode ingressar no dispositivo no Azure AD de configurações do Windows: **configurações > contas > acessar o trabalho ou escola > se conectar**.
 

## <a name="windows-azure-ad-registered-company-owned"></a>Windows Azure AD registrado (pertencente à empresa)

Para determinar se o dispositivo Windows 10 está registrado no Azure AD –, execute o seguinte comando no dispositivo:

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

Se o dispositivo for do Azure AD registrado, você verá o seguinte resultado:

```console
+----------------------------------------------------------------------+
| User State                                                           |
+----------------------------------------------------------------------+
           WorkplaceJoined : YES
          WamDefaultSet : NO
          WamDefaultAuthority : organizations
```

Para remover a conta do Azure AD registrada existente no dispositivo:

- Para remover a conta registrada do Azure AD no dispositivo, use o CleanupWPJ, uma ferramenta para a qual você pode baixar aqui: [CleanupWPJ.zip](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip).

- Extraia o arquivo ZIP e execute o **WPJCleanup. cmd**. Essa ferramenta iniciará o executável correto com base na versão do Windows no dispositivo.

- Usando um mecanismo como diretiva de grupo, o administrador pode executar o comando no dispositivo no contexto de qualquer usuário que esteja conectado ao dispositivo.

Para desabilitar o Gerenciador de contas da Web solicita o registro do dispositivo no Azure AD, adicione esse valor do registro: 

- Local: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin
- Tipo: DWORD (32 bits)
- Nome: BlockAADWorkplaceJoin
- Dados do valor: 1

A presença desse valor do registro deve bloquear o Workplace Join e impedir que os usuários vejam as solicitações para ingressar no dispositivo.

## <a name="android"></a>Android

Para Android, os usuários precisarão cancelar o registro e registrar novamente seus dispositivos. Isso pode ser feito por meio do aplicativo Microsoft Authenticator ou do portal da empresa. 

- No aplicativo Microsoft Authenticator, os usuários podem acessar **configurações > registro de dispositivos**. A partir daí, os usuários podem cancelar o registro e registrar novamente o dispositivo.
 
- No portal da empresa, os usuários podem ir para a guia **dispositivos** e remover o dispositivo. Depois, registre novamente o dispositivo usando o portal da empresa.
 
- Os usuários também podem cancelar o registro e registrar-se novamente, removendo a conta da página de configurações de conta e, em seguida, adicionando novamente a conta de trabalho.

Para cancelar o registro e registrar novamente o dispositivo no Android usando o aplicativo Microsoft Authenticator:

1.  Abra o aplicativo Microsoft Authenticator e vá para **configurações**.
2.  Selecione **registro de dispositivo**.
3.  Cancele o registro do dispositivo selecionando **cancelar o registro**.
4.  Para **registro de dispositivo**, registre novamente o dispositivo digitando seu endereço de email e, em seguida, selecione **registrar**.

Para cancelar o registro e registrar novamente um dispositivo Android com a página Configurações de Android:

1.  Abra **configurações de dispositivo** e vá para **contas**.
2.  Selecione a conta de trabalho que você deseja registrar novamente e selecione **remover conta**.
3.  Depois que a conta for removida, na página **contas** , selecione **adicionar conta > conta de trabalho**.
4.  Para **ingresso no local de trabalho**, digite seu endereço de email e selecione **ingressar** para concluir o registro do dispositivo.

Para cancelar o registro e registrar novamente o dispositivo no Android do portal da empresa:

1.  Inicie o portal da empresa e vá para a guia **dispositivos** .
2.  Selecione o dispositivo para ver os detalhes do dispositivo.
3.  No menu reticências (três pontos), selecione **remover dispositivo** e concluir a remoção confirmando na caixa de diálogo.
4.  Agora você deve estar desconectado do aplicativo portal da empresa. Selecione **entrar** para registrar novamente o dispositivo.

Para obter mais informações sobre as ações necessárias durante a fase de migração dessa carga de trabalho ou o impacto na administração ou no uso, revise as informações sobre o Azure Active Directory (Azure AD) em [informações adicionais sobre o Azure ad para a migração do Microsoft Cloud Alemanha](ms-cloud-germany-transition-azure-ad.md).

## <a name="ios"></a>iOS

Em dispositivos iOS, um usuário precisará remover manualmente todas as contas em cache do Microsoft Authenticator, cancelar o registro do dispositivo e sair de qualquer aplicativo nativo no dispositivo.

### <a name="step-1-if-present-remove-the-account-from-the-microsoft-authenticator-app"></a>Etapa 1: se presente, remova a conta do aplicativo Microsoft Authenticator

1. Toque na conta no aplicativo Microsoft Authenticator.
2. Toque no ícone **configurações** no canto superior direito. Se você não vir o ícone de **configurações** , talvez não esteja usando a versão mais recente do Microsoft Authenticator.
3. Toque no botão **remover conta** .
4. Toque **em todos os aplicativos neste dispositivo**.
 
### <a name="step-2-unregister-the-device-from-the-microsoft-authenticator-app"></a>Etapa 2: cancelar o registro do dispositivo do aplicativo Microsoft Authenticator

1. Toque no ícone de menu no canto superior direito.
2. Toque em **configurações** e em **registro do dispositivo**.
4. Se sua conta for exibida, toque em **Cancelar registro de dispositivo** e **continuar** na caixa de diálogo. Você não deve ver nenhuma conta após isso.
 
### <a name="step-3-sign-out-from-individual-apps-if-necessary"></a>Etapa 3: sair de aplicativos individuais, se necessário

Os usuários podem acessar aplicativos individuais, como o Outlook, o Teams e o OneDrive, e remover contas desses aplicativos.

## <a name="more-information"></a>Mais informações

Introdução:

- [Migração do Microsoft Cloud Alemanha para os serviços do Office 365 nas novas regiões do datacenter alemão](ms-cloud-germany-transition.md)
- [Assistência de Migração do Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Como aceitar a migração](ms-cloud-germany-migration-opt-in.md)
- [Experiência do cliente durante a migração](ms-cloud-germany-transition-experience.md)

Mover-se pela transição:

- [Ações e impactos das fases de migração](ms-cloud-germany-transition-phases.md)
- [Pré-trabalho adicional](ms-cloud-germany-transition-add-pre-work.md)
- Informações adicionais para o [Azure ad](ms-cloud-germany-transition-azure-ad.md), [dispositivos](ms-cloud-germany-transition-add-devices.md), [experiências](ms-cloud-germany-transition-add-experience.md)e [AD FS](ms-cloud-germany-transition-add-adfs.md).

Aplicativos de nuvem:

- [Informações do programa de migração do Dynamics 365](https://aka.ms/d365ceoptin)
- [Informações do programa de migração do Power BI](https://aka.ms/pbioptin)
- [Introdução à atualização do Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
