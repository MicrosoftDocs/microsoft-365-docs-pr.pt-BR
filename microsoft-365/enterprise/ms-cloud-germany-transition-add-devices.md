---
title: Informações adicionais do dispositivo para a migração do Microsoft Cloud Deutschland
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
description: 'Resumo: Informações adicionais sobre os serviços do dispositivo ao mudar do Microsoft Cloud Germany (Microsoft Cloud Deutschland) para os serviços do Office 365 na nova região do datacenter alemão.'
ms.openlocfilehash: 21188372f03af394fe1c0e227c1adeabbad02a85
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928151"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a>Informações adicionais do dispositivo para a migração do Microsoft Cloud Deutschland

## <a name="frequently-asked-questions"></a>Perguntas frequentes

**Como posso saber se minha organização foi afetada?**

Os administradores devem `https://portal.microsoftazure.de` verificar para determinar se eles têm dispositivos registrados. Se sua organização tiver dispositivos registrados, você será afetado.

**Qual é o impacto nos meus usuários?**

Os usuários de um dispositivo registrado não poderão mais entrar depois que a migração entrar na fase de migração finalizar o [Azure AD.](ms-cloud-germany-transition.md#how-is-the-migration-organized)  

Verifique se todos os seus dispositivos estão registrados com o ponto de extremidade em todo o mundo antes que sua organização seja desconectada do Microsoft Cloud Deutschland.
  
**Quando meus usuários registram seus dispositivos de novo?**

É fundamental para o seu sucesso que você apenas não registre e registre seus dispositivos durante a fase de migração [Separate from Microsoft Cloud Deutschland.](ms-cloud-germany-transition.md#how-is-the-migration-organized)

**Como restaurar meu estado de dispositivo após a migração?**

Para dispositivos Windows híbridos ingressados no Azure AD e pertencentes à empresa que estão registrados no Azure AD, os administradores poderão gerenciar a migração desses dispositivos por meio de fluxos de trabalho disparados remotamente que não registrarão os estados do dispositivo antigo.
  
Para todos os outros dispositivos, incluindo dispositivos Windows pessoais registrados no Azure AD, o usuário final deve executar essas etapas manualmente. Para dispositivos ingressados no Azure AD, os usuários precisam ter uma conta de administrador local para não registrar e, em seguida, registrar seus dispositivos.

A Microsoft publicará instruções sobre como restaurar com êxito o estado do dispositivo. 
 
**Como saber se todos os meus dispositivos estão registrados na nuvem pública?**

Para verificar se seus dispositivos estão registrados na nuvem pública, você deve exportar e baixar a lista de dispositivos do portal do Azure AD para uma planilha do Excel. Em seguida, filtre os dispositivos registrados (usando a coluna _registeredTime)_ após a fase de migração [Separate from Microsoft Cloud Deutschland.](ms-cloud-germany-transition.md#how-is-the-migration-organized)

O registro do dispositivo é desativado após a migração do locatário e não pode ser habilitado ou desabilitado. Se o Intune não for usado, entre em sua assinatura e execute este comando para reativá-lo:

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

## <a name="hybrid-azure-ad-join"></a>Ingresso no Azure AD híbrido

### <a name="windows-down-level"></a>Nível inferior do Windows

Dispositivos de nível inferior do _Windows_ são dispositivos Windows que atualmente são executados versões anteriores do Windows (como Windows 8.1 ou Windows 7) ou que executem versões do Windows Server anteriores a 2019 e 2016. Se esses dispositivos tiverem sido registrados anteriormente, você precisará deso registrar e registrar esses dispositivos. 

Para determinar se um dispositivo de nível inferior do Windows foi ingressado anteriormente no Azure AD, use o seguinte comando no dispositivo:

```console
%programfiles%\Microsoft Workplace Join\autoworkplace /status
```

Se o dispositivo tiver sido ingressado anteriormente no Azure AD e se o dispositivo tiver conectividade de rede com pontos de extremidade globais do Azure AD, você verá a seguinte saída:

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

Os dispositivos afetados terão o "estado do dispositivo" com o valor "Desconhecido". Se a saída for "Dispositivo não ingressado" ou cujo valor "Estado do dispositivo" for "Ok", ignore as seguintes diretrizes.

Somente para dispositivos que mostram que o dispositivo está ingressado (em virtude de deviceId, impressão digital e assim por diante) e cujo valor "Estado do dispositivo" é "Desconhecido", os administradores devem executar o seguinte comando no contexto de um usuário de domínio que faz logon em um dispositivo de nível inferior:

```console
"%programfiles%\Microsoft Workplace Join\autoworkplace /leave"
```

O comando anterior só precisa ser executado uma vez por usuário de domínio que entre no dispositivo de nível inferior do Windows. Esse comando deve ser executado no contexto da sessão do usuário de domínio. 

É necessário ter cuidado suficiente para não executar esse comando quando o usuário entrar posteriormente. Quando o comando anterior for executado, ele limpará o estado ingressado do computador híbrido local do Azure AD ingressado para o usuário que entrou. E, se o computador ainda estiver configurado para ser híbrido do Azure AD- ingressado no locatário, ele tentará ingressar quando o usuário entrar novamente.

### <a name="windows-current"></a>Windows Current

#### <a name="unjoin"></a>Unjoin

Para determinar se o dispositivo Windows 10 foi ingressado anteriormente no Azure AD, execute o seguinte comando no dispositivo:

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

Se o dispositivo for híbrido ingressado no Azure AD, o administrador verá a seguinte saída:

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : YES
```

Se a saída for "AzureAdJoined : Não", ignore as seguintes diretrizes.

Somente para dispositivos que mostram que o dispositivo está ingressado no Azure AD, execute o seguinte comando como administrador para remover o estado ingressado do dispositivo.

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

O comando anterior só precisa ser executado uma vez em um contexto administrativo no dispositivo Windows.

#### <a name="hybrid-ad-joinre-registration"></a>Junção AD Híbrida\Recadastramento

O dispositivo é automaticamente ingressado no Azure AD sem intervenção de usuário ou administrador, desde que o dispositivo tenha conectividade de rede com pontos de extremidade globais do Azure AD. 


## <a name="azure-ad-join"></a>Ingressar no Azure AD

**IMPORTANTE:** A entidade de serviço do Intune será habilitada após a migração do comércio, o que implica na ativação do Registro de Dispositivo do Azure AD. Se você bloqueou o Registro de Dispositivo do Azure AD antes da migração, deverá desabilitar a entidade de serviço do Intune com o PowerShell para desabilitar o Registro de Dispositivo do Azure AD com o portal do Azure AD novamente. Você pode desabilitar a entidade de serviço do Intune com esse comando no módulo PowerShell do Azure Active Directory para Graph.

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

### <a name="unjoin"></a>Unjoin

Para determinar se o dispositivo Windows 10 foi ingressado anteriormente no Azure AD, o usuário ou administrador pode executar o seguinte comando no dispositivo:

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

Se o dispositivo for ingressado no Azure AD, o usuário ou administrador verá a seguinte saída:

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : NO
```

Se a saída for "AzureAdJoined : NO", ignore as seguintes diretrizes.

Usuário: se o dispositivo for ingressado no Azure AD, um usuário poderá desagrecar o dispositivo das configurações. Verifique se há uma conta de administrador local no dispositivo antes de desatar o dispositivo do Azure AD. A conta de administrador local é necessária para entrar novamente no dispositivo.

Administrador: se o administrador da organização quiser desagrecar os dispositivos dos usuários que estão ingressados no Azure AD, eles poderão fazer isso executando o seguinte comando em cada um dos dispositivos usando um mecanismo como a Política de Grupo. O administrador deve verificar se há uma conta de administrador local no dispositivo antes de desatar o dispositivo do Azure AD. A conta de administrador local é necessária para entrar novamente no dispositivo.

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

O comando anterior só precisa ser executado uma vez em um contexto administrativo no dispositivo Windows. 

### <a name="azure-ad-joinre-registration"></a>Azure AD Join/Re-Registration

O usuário pode ingressar o dispositivo no Azure AD a partir das configurações do Windows: Configurações > Contas > **Access Work or School > Connect**.
 

## <a name="azure-ad-registered-company-owned"></a>Azure AD Registered (Empresa de propriedade)

Para determinar se o dispositivo Windows 10 é registrado no Azure AD, execute o seguinte comando no dispositivo:

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

Se o dispositivo for Registrado no Azure AD, você verá a seguinte saída:

```console
+----------------------------------------------------------------------+
| User State                                                           |
+----------------------------------------------------------------------+
           WorkplaceJoined : YES
          WamDefaultSet : NO
          WamDefaultAuthority : organizations
```

Para remover a conta existente registrada no Azure AD no dispositivo:

- Para remover a conta registrada no Azure AD no dispositivo, use CleanupWPJ, uma ferramenta que você pode baixar [ aqui:CleanupWPJ.zip](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip).

- Extraia o arquivo ZIP e execute **WPJCleanup.cmd**. Esta ferramenta iniciará o executável correto com base na versão do Windows no dispositivo.

- Usando um mecanismo como a Política de Grupo, o administrador pode executar o comando no dispositivo no contexto de qualquer usuário conectado ao dispositivo.

Para desabilitar solicitações do Gerenciador de Contas da Web para registrar o dispositivo no Azure AD, adicione esse valor do Registro: 

- Local: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin
- Tipo: DWORD (32 bits)
- Nome: BlockAADWorkplaceJoin
- Dados de valor: 1

A presença desse valor do Registro deve bloquear a participação no local de trabalho e impedir que os usuários visem prompts para ingressar no dispositivo.

## <a name="android"></a>Android

Para Android, os usuários precisarão registrar e registrar seus dispositivos de novo. Isso pode ser feito por meio do aplicativo Microsoft Authenticator ou do aplicativo Portal da Empresa. 

- No aplicativo Microsoft Authenticator, os usuários podem ir para **Configurações > Registro de Dispositivo.** A partir daí, os usuários podem se registrar e registrar seus dispositivos de novo.
 
- No Portal da Empresa, os usuários podem ir até a guia **Dispositivos** e remover o dispositivo. Depois disso, rescrente o dispositivo usando o Portal da Empresa.
 
- Os usuários também podem registrar-se e re-registrar removendo a conta da página de configurações da conta e, em seguida, adicionando a conta de trabalho.

Para não registrar e registrar o dispositivo no Android usando o aplicativo Microsoft Authenticator:

1.  Abra o aplicativo Microsoft Authenticator e vá para **Configurações**.
2.  Selecione **Registro de dispositivo**.
3.  Desaconselhe o dispositivo **selecionando Unregister**.
4.  Para **registro de dispositivo,** registre o dispositivo digitando seu endereço de email e selecione **Registrar**.

Para não registrar e registrar um dispositivo Android com a página Configurações do Android:

1.  Abra **Configurações do Dispositivo e** vá para **Contas**.
2.  Selecione a conta de trabalho que você deseja registrar e selecione **Remover conta**.
3.  Depois que a conta for removida, na página **Contas,** selecione **Adicionar Conta > Conta de Trabalho**.
4.  Para **Ingressar no Local de Trabalho,** digite seu endereço de email e selecione **Ingressar** para concluir o registro do dispositivo.

Para não registrar e registrar o dispositivo no Android no Portal da Empresa:

1.  Iniciar o Portal da Empresa e ir para **a guia Dispositivos.**
2.  Selecione o dispositivo para ver os detalhes do dispositivo.
3.  No menu releitos (três pontos), selecione **Remover** Dispositivo e conclua a remoção confirmando na caixa de diálogo.
4.  Agora, você deve estar conectado ao aplicativo Portal da Empresa. Selecione **Entrar para** registrar o dispositivo de novo.

Para obter mais informações sobre as ações necessárias durante a fase de migração dessa carga de trabalho ou impacto para a administração ou uso, revise as informações sobre o Azure Active Directory (Azure AD) em Informações adicionais do [Azure AD](ms-cloud-germany-transition-azure-ad.md)para a migração do Microsoft Cloud Deutschland .

## <a name="ios"></a>iOS

Em dispositivos iOS, um usuário precisará remover manualmente quaisquer contas armazenadas em cache do Microsoft Authenticator, desatuar o dispositivo e sair de qualquer aplicativo nativo no dispositivo.

### <a name="step-1-if-present-remove-the-account-from-the-microsoft-authenticator-app"></a>Etapa 1: se presente, remova a conta do aplicativo Microsoft Authenticator

1. Toque na conta no aplicativo Microsoft Authenticator.
2. Toque no **ícone Configurações** no canto superior direito. Se você não vir o ícone **Configurações,** talvez não use a versão mais recente do Microsoft Authenticator.
3. Toque no **botão Remover conta.**
4. Toque **em Todos os aplicativos neste dispositivo**.
 
### <a name="step-2-unregister-the-device-from-the-microsoft-authenticator-app"></a>Etapa 2: Não registro o dispositivo do aplicativo Microsoft Authenticator

1. Toque no ícone de menu no canto superior direito.
2. Toque **em Configurações** e, em seguida, **registro de dispositivo.**
4. Se sua conta for mostrada, toque em Dispositivo de Registro **Não-Registro** e **Continue** na caixa de diálogo. Você não deve ver nenhuma conta depois disso.
 
### <a name="step-3-sign-out-from-individual-apps-if-necessary"></a>Etapa 3: Sair de aplicativos individuais, se necessário

Os usuários podem ir para aplicativos individuais, como Outlook, Teams e OneDrive, e remover contas desses aplicativos.

## <a name="more-information"></a>Mais informações

Como começar:

- [Migração do Microsoft Cloud Deutschland para serviços do Office 365 nas novas regiões do datacenter alemão](ms-cloud-germany-transition.md)
- [Assistência de Migração do Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Como aceitar a migração](ms-cloud-germany-migration-opt-in.md)
- [Experiência do cliente durante a migração](ms-cloud-germany-transition-experience.md)

Movendo-se pela transição:

- [Ações e impactos das fases de migração](ms-cloud-germany-transition-phases.md)
- [Pré-trabalho adicional](ms-cloud-germany-transition-add-pre-work.md)
- Informações adicionais para [o Azure AD,](ms-cloud-germany-transition-azure-ad.md) [dispositivos, experiências](ms-cloud-germany-transition-add-experience.md)e [AD FS](ms-cloud-germany-transition-add-adfs.md). [](ms-cloud-germany-transition-add-devices.md)

Aplicativos de nuvem:

- [Informações do programa de migração do Dynamics 365](/dynamics365/get-started/migrate-data-german-region)
- [Informações do programa de migração do Power BI](/power-bi/admin/service-admin-migrate-data-germany)
- [Introdução à atualização do Microsoft Teams](/microsoftteams/upgrade-start-here)