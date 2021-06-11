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
ms.openlocfilehash: cdb3278e1d96b2ebdced122ab53db716c3195d8c
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/11/2021
ms.locfileid: "52903860"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a>Informações adicionais do dispositivo para a migração do Microsoft Cloud Deutschland

Os dispositivos ingressados e registrados no Azure AD conectados ao Microsoft Cloud Deutschland devem ser migrados após a fase 9 e antes da fase 10. A migração de um dispositivo depende do tipo de dispositivo, do sistema operacional e da relação do Azure AD. 

## <a name="azure-ad-joined-windows-10-devices"></a>Dispositivos Windows 10 Azure AD
Se um Windows 10 for ingressado no Azure AD, ele deverá ser desconectado do Azure AD e deverá ser conectado novamente. 

[![Dispositivo do Azure AD Re-Join Flow ](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png)](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png#lightbox)


Se o usuário for um administrador no dispositivo Windows 10, o usuário poderá desemitir o dispositivo do Azure AD e jun-lo novamente em três etapas. 

### <a name="step-1-determine-if-the-device-is-azure-id-joined"></a>Etapa 1: Determinar se o dispositivo está ingressado no Azure ID
1.  Entre com sua conta corporativa.
2.  Vá para o **Configurações**  >  **contas acessar** o trabalho ou a  >  **escola.** 
3.  Procure uma conta na lista com **[...]' s Azure AD**. 
4.  Se houver uma conta conectada, prossiga com a Etapa 2. 
### <a name="step-2-disconnect-the-device-from-azure-ad"></a>Etapa 2: desconectar o dispositivo do Azure AD
1.  Clique **em Desconectar** no trabalho conectado ou conta escolar. 
2.  Confirme a desconexão duas vezes. 
3.  Insira um nome de usuário e senha de administrador local. O dispositivo está desconectado.
4.  Reinicie o dispositivo.
### <a name="step-3-join-the-device-to-azure-ad"></a>Etapa 3: Associar o dispositivo ao Azure AD
1.  Entre com as credenciais do administrador local.
2.  Vá para o **Configurações**  >  **contas acessar** o trabalho ou a  >  **escola.**
3.  Clique em **Conectar**.
4.  **IMPORTANTE**: Clique **em Ingressar no Azure AD**.
5.  Insira o endereço de email e a senha da sua conta de trabalho. O dispositivo está conectado.
6.  Reinicie o dispositivo.
7.  Entre com o endereço de email e a senha da sua conta de trabalho.

Se o usuário não for um administrador do dispositivo, um administrador global do Azure AD poderá criar a conta de administrador local no dispositivo seguindo esse caminho de configuração e desatar o dispositivo:

*Configurações > Contas > Outras Contas > Credenciais desconhecidas > Adicionar usuário sem Microsoft-Account*

Para ingressar outra vez, as credenciais de qualquer conta de trabalho de sua organização podem ser usadas nesta etapa. 

Considere que a conta de trabalho usada para ingressar no dispositivo será automaticamente promovida como administrador do dispositivo.
Qualquer outra conta de trabalho da organização pode entrar no dispositivo, mas não tem privilégios de administrador.

## <a name="azure-ad-registered-workplace-joined-windows-10-devices"></a>Azure AD registrado (ingressado no local de trabalho) Windows 10 dispositivos
Se um Windows 10 for registrado no Azure AD, ele precisará ser desconectado do Azure AD e conectado novamente.

[![Dispositivo do Azure AD Re-Registration Flow ](../media/ms-cloud-germany-migration-opt-in/AAD-ReRegistration-flow.png)](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png#lightbox)

### <a name="step-1-determine-if-the-device-is-azure-id-registered"></a>Etapa 1: Determinar se o dispositivo é Azure ID registrado
1.  Entre com seu usuário.
2.  Vá para o **Configurações**  >  **contas acessar** o trabalho ou a  >  **escola.** 
3.  Descubra sua conta de trabalho na lista e verifique se ela está **conectada a [...]' s Azure AD**.

    Se sua conta de trabalho estiver na lista, mas NÃO conectada a um Azure AD, prossiga com a etapa 2.

    Caso contrário, seu dispositivo é um dispositivo ingressado no Azure AD e você precisa se referir a dispositivos Windows 10 [Azure AD .](#azure-ad-joined-windows-10-devices)

### <a name="step-2-disconnect-the-device-from-azure-ad"></a>Etapa 2: desconectar o dispositivo do Azure AD
1.  Clique em sua conta de trabalho. Os botões *Informações* e *Desconectar* aparecem.
2.  Clique **em Desconectar**. 
3.  Confirme a remoção da conta do dispositivo clicando em **Sim**.
### <a name="step-3-connect-the-device-to-azure-ad"></a>Etapa 3: Conexão o dispositivo para o Azure AD
1.  Clique em **Conectar**.
2.  Insira o endereço de email da sua conta de trabalho e clique em **Next**.
3.  Insira a senha da sua conta de trabalho e clique **em Entrar**.
4.  Confirme clicando em **Done**. Sua conta de trabalho está listada novamente.

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

## <a name="frequently-asked-questions"></a>Perguntas frequentes

**Como posso saber se minha organização foi afetada?**

Os administradores devem `https://portal.microsoftazure.de` verificar para determinar se eles têm algum Azure AD registrado ou dispositivos ingressados no Azure AD. Se sua organização tiver dispositivos registrados no Azure AD ou no Azure AD, sua organização terá que seguir as instruções nesta página.

**Quando meus usuários registram seus dispositivos de novo?**

É fundamental para o seu sucesso que você apenas não registre e registre seus dispositivos após a conclusão da [fase 9.](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) Você deve concluir o recadastramento antes da fase 10 ser iniciada, caso contrário, poderá perder o acesso ao dispositivo.

**Como saber se todos os meus dispositivos estão registrados na nuvem pública?**

Para verificar se seus dispositivos estão registrados na nuvem pública, você deve exportar e baixar a lista de dispositivos do portal do Azure AD para uma planilha Excel. Em seguida, filtre os dispositivos registrados (usando a coluna _registeredTime)_ após a data em que sua organização passou a [fase 9 do](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization)processo de migração .

## <a name="additional-considerations"></a>Considerações adicionais

> [!IMPORTANT]
> A entidade de serviço do Intune será habilitada após a [fase 3](ms-cloud-germany-transition-phases.md#phase-3-subscription-transfer)do processo de migração , o que implica na ativação do Registro de Dispositivo do Azure AD. Se você bloqueou o Registro de Dispositivo do Azure AD antes da migração, deverá desabilitar a entidade de serviço do Intune com o PowerShell para desabilitar o Registro de Dispositivo do Azure AD com o portal do Azure AD novamente. Você pode desabilitar a entidade de serviço do Intune com esse comando no Azure Active Directory PowerShell para Graph módulo.

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

## <a name="more-information"></a>Mais Informações

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