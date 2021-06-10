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
description: 'Resumo: Informações adicionais sobre os serviços do dispositivo ao mudar do Microsoft Cloud Germany (Microsoft Cloud Deutschland) para Office 365 serviços na nova região do datacenter alemão.'
ms.openlocfilehash: 27426a26befab85bf62a0a143861e447dd722724
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861294"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a>Informações adicionais do dispositivo para a migração do Microsoft Cloud Deutschland

Os dispositivos ingressados e registrados no Azure AD conectados ao Microsoft Cloud Deutschland devem ser migrados após a fase 9 e antes da fase 10. A migração de um dispositivo depende do tipo de dispositivo, sistema operacional e relação AAD. 

## <a name="frequently-asked-questions"></a>Perguntas frequentes

**Como posso saber se minha organização foi afetada?**

Os administradores devem verificar se eles têm dispositivos registrados ou `https://portal.microsoftazure.de` ingressados no Azure AD. Se sua organização tiver dispositivos registrados, você será afetado.

**Qual é o impacto nos meus usuários?**

Os usuários de um dispositivo registrado não poderão mais entrar após a conclusão da fase [10](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) de migração e os pontos de extremidade do Microsoft Cloud Deutschland foram desabilitados.  

Verifique se todos os seus dispositivos estão registrados com o ponto de extremidade em todo o mundo antes que sua organização seja desconectada do Microsoft Cloud Deutschland.
  
**Quando meus usuários registram seus dispositivos de novo?**

É fundamental para o seu sucesso que você apenas não registre e registre seus dispositivos após a conclusão da [fase 9.](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) Você deve concluir o recadastramento antes da fase 10 ser iniciada, caso contrário, poderá perder o acesso ao dispositivo.

**Como restaurar meu estado de dispositivo após a migração?**

Para dispositivos de Windows de propriedade da empresa registrados no Azure AD, os administradores poderão gerenciar a migração desses dispositivos por meio de fluxos de trabalho disparados remotamente que não registrarão os estados do dispositivo antigo.
  
Para todos os outros dispositivos, incluindo Windows pessoais registrados no Azure AD, o usuário final deve executar essas etapas manualmente. Para dispositivos ingressados no Azure AD, os usuários precisam ter uma conta de administrador local para não registrar e, em seguida, registrar seus dispositivos.

Consulte instruções detalhadas sobre como restaurar com êxito os estados do dispositivo abaixo. 
 
**Como saber se todos os meus dispositivos estão registrados na nuvem pública?**

Para verificar se seus dispositivos estão registrados na nuvem pública, você deve exportar e baixar a lista de dispositivos do portal do Azure AD para uma planilha Excel. Em seguida, filtre os dispositivos registrados (usando a coluna _registeredTime)_ após a fase de migração [Separate from Microsoft Cloud Deutschland.](ms-cloud-germany-transition.md#how-is-the-migration-organized)

## <a name="additional-considerations"></a>Considerações adicionais
O registro do dispositivo é desativado após a migração do locatário e não pode ser habilitado ou desabilitado. 

Se o Intune não for usado, entre em sua assinatura e execute este comando para reativá-lo:

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```
**IMPORTANTE:** A entidade de serviço do Intune será habilitada após a migração do comércio, o que implica na ativação do Registro de Dispositivo do Azure AD. Se você bloqueou o Registro de Dispositivo do Azure AD antes da migração, deverá desabilitar a entidade de serviço do Intune com o PowerShell para desabilitar o Registro de Dispositivo do Azure AD com o portal do Azure AD novamente. Você pode desabilitar a entidade de serviço do Intune com esse comando no Azure Active Directory PowerShell para Graph módulo.

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```


## <a name="azure-ad-join"></a>Ingressar no Azure AD
Isso se aplica a Windows 10 dispositivos. 

Se um dispositivo for ingressado no Azure AD, ele deverá ser desconectado do Azure AD e ser conectado novamente. 

[![Dispositivo do Azure AD Re-Join Flow ](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png)](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png#lightbox)


Se o usuário for um administrador no dispositivo Windows 10, o usuário poderá desaconselhá-lo do Azure AD e jun-lo novamente. Se ele não tiver privilégios de administrador, o usuário precisará de credenciais de uma conta de administrador local neste computador. 


Um Administrador pode criar uma conta de administrador local no dispositivo seguindo este caminho de configuração:

*Configurações > Contas > Outras Contas > Credenciais desconhecidas > Adicionar usuário sem Microsoft-Account*

### <a name="step-1-determine-if-the-device-is-azure-id-joined"></a>Etapa 1: Determinar se o dispositivo está ingressado no Azure ID
1.  Entre com usuários Email e senha.
2.  Vá para Configurações > Contas > Acessar Trabalho ou Escola. 
3.  Procure um usuário na lista com **conectado a ... 's Azure AD**. 
4.  Se houver um usuário conectado, prossiga com a Etapa 2. Caso não seja necessário, nenhuma ação será necessária.
### <a name="step-2-disconnect-the-device-from-azure-ad"></a>Etapa 2: desconectar o dispositivo do Azure AD
1.  Toque **em Desconectar** na conta de trabalho ou de estudante conectada. 
2.  Confirme a desconexão duas vezes. 
3.  Insira o nome de usuário e a senha do administrador local. O dispositivo está desconectado.
4.  Reinicie o dispositivo.
### <a name="step-3-join-the-device-to-azure-ad"></a>Etapa 3: Associar o dispositivo ao Azure AD
1.  o usuário entrar com as credenciais do administrador local
2.  Vá para o **Configurações** **contas em seguida,** **acesse Trabalho ou Escola**
3.  Toque **Conexão**
4.  **IMPORTANTE**: Toque **em Ingressar no Azure AD**
5.  Insira o endereço de email e a senha do usuário. O dispositivo está conectado
6.  Reiniciar o dispositivo 
7.  entrar com seu endereço de email e senha

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

- Extraia o arquivo ZIP e execute **WPJCleanup.cmd**. Esta ferramenta iniciará o executável correto com base na versão Windows no dispositivo.

- Usando um mecanismo como a Política de Grupo, o administrador pode executar o comando no dispositivo no contexto de qualquer usuário conectado ao dispositivo.

Para desabilitar solicitações do Gerenciador de Contas da Web para registrar o dispositivo no Azure AD, adicione esse valor do Registro: 

- Local: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin
- Tipo: DWORD (32 bits)
- Nome: BlockAADWorkplaceJoin
- Dados de valor: 1

A presença desse valor do Registro deve bloquear a participação no local de trabalho e impedir que os usuários visem prompts para ingressar no dispositivo.

## <a name="android"></a>Android

Para Android, os usuários precisarão registrar e registrar seus dispositivos de novo. Isso pode ser feito por meio do aplicativo Microsoft Authenticator ou do Portal da Empresa aplicativo. 

- No aplicativo Microsoft Authenticator, os usuários podem ir **Configurações > Registro de Dispositivos**. A partir daí, os usuários podem se registrar e registrar seus dispositivos de novo.
 
- Na Portal da Empresa, os usuários podem ir até a guia **Dispositivos** e remover o dispositivo. Depois disso, re-inscreva o dispositivo usando Portal da Empresa.
 
- Os usuários também podem registrar-se e re-registrar removendo a conta da página de configurações da conta e, em seguida, adicionando a conta de trabalho.

Para não registrar e registrar o dispositivo no Android usando o Microsoft Authenticator app:

1.  Abra o Microsoft Authenticator aplicativo e vá para **Configurações**.
2.  Selecione **Registro de dispositivo**.
3.  Desaconselhe o dispositivo **selecionando Unregister**.
4.  Para **registro de dispositivo,** registre o dispositivo digitando seu endereço de email e selecione **Registrar**.

Para não registrar e registrar um dispositivo Android com a página Configurações Android:

1.  Abra **o dispositivo Configurações** e vá para **Contas**.
2.  Selecione a conta de trabalho que você deseja registrar e selecione **Remover conta**.
3.  Depois que a conta for removida, na página **Contas,** selecione **Adicionar Conta > Conta de Trabalho**.
4.  Para **Ingressar no Local de Trabalho,** digite seu endereço de email e selecione **Ingressar** para concluir o registro do dispositivo.

Para não registrar e registrar o dispositivo no Android de Portal da Empresa:

1.  Iniciar Portal da Empresa e vá para **a guia Dispositivos.**
2.  Selecione o dispositivo para ver os detalhes do dispositivo.
3.  No menu releitos (três pontos), selecione **Remover** Dispositivo e conclua a remoção confirmando na caixa de diálogo.
4.  Agora você deve estar conectado ao aplicativo Portal da Empresa. Selecione **Entrar para** registrar o dispositivo de novo.

Para obter mais informações sobre as ações necessárias durante a fase de migração dessa carga de trabalho ou impacto na administração ou no uso, revise as informações sobre o Azure Active Directory [(Azure AD)](ms-cloud-germany-transition-azure-ad.md)em Informações adicionais do Azure AD para a migração do Microsoft Cloud Deutschland .

## <a name="ios"></a>iOS

Em dispositivos iOS, um usuário precisará remover manualmente todas as contas armazenadas em cache do Microsoft Authenticator, desa inscrever o dispositivo e sair de qualquer aplicativo nativo no dispositivo.

### <a name="step-1-if-present-remove-the-account-from-the-microsoft-authenticator-app"></a>Etapa 1: se presente, remova a conta do Microsoft Authenticator app

1. Toque na conta no aplicativo Microsoft Authenticator.
2. Toque no **Configurações** no canto superior direito. Se você não vir o **ícone** Configurações, talvez não use a versão mais recente do Microsoft Authenticator.
3. Toque no **botão Remover conta.**
4. Toque **em Todos os aplicativos neste dispositivo**.
 
### <a name="step-2-unregister-the-device-from-the-microsoft-authenticator-app"></a>Etapa 2: Desaconselhe o dispositivo do Microsoft Authenticator app

1. Toque no ícone de menu no canto superior direito.
2. Toque **Configurações** e, em seguida, **Registro de Dispositivo.**
4. Se sua conta for mostrada, toque em Dispositivo de Registro **Não-Registro** e **Continue** na caixa de diálogo. Você não deve ver nenhuma conta depois disso.
 
### <a name="step-3-sign-out-from-individual-apps-if-necessary"></a>Etapa 3: Sair de aplicativos individuais, se necessário

Os usuários podem ir para aplicativos individuais como Outlook, Teams e OneDrive e remover contas desses aplicativos.

## <a name="more-information"></a>Mais informações

Como começar:

- [Migração do Microsoft Cloud Deutschland para serviços Office 365 nas novas regiões do datacenter alemão](ms-cloud-germany-transition.md)
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