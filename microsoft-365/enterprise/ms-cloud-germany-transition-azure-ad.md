---
title: Informações Azure Active Directory informações adicionais para a migração do Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/15/2020
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
description: 'Resumo: informações Azure Active Directory adicionais ao mudar do Microsoft Cloud Germany (Microsoft Cloud Deutschland) para Office 365 serviços na nova região do datacenter alemão.'
ms.openlocfilehash: 1e3871dc5a8a8a9ecbef29df21431aa3707871d0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923845"
---
# <a name="additional-azure-active-directory-information-for-the-migration-from-microsoft-cloud-deutschland"></a>Informações Azure Active Directory informações adicionais para a migração do Microsoft Cloud Deutschland

Para concluir a movimentação da nuvem alemã do Azure para a nuvem pública do Azure, recomendamos que o ponto de extremidade de autenticação, Azure Active Directory (Azure AD) Graph e pontos de extremidade do MS Graph para seus aplicativos sejam atualizados para os pontos de extremidade da nuvem comercial quando o ponto de extremidade openID Conexão (OIDC) começar a relatar pontos de extremidade de nuvem `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration` comercial. 
 
**Quando devo fazer essa alteração?**

Você receberá uma notificação no portal do Azure/Office quando o locatário concluir a migração da nuvem alemã para a nuvem comercial. Você tem 30 dias após receber essa notificação para concluir essas atualizações para que seu aplicativo continue a funcionar para locatários migrados da nuvem do Azure Germany para a nuvem pública do Azure.
 
Há três pré-condições para atualizar sua autoridade de entrada:

 - O ponto de extremidade de descoberta do OIDC para seu locatário retorna pontos de extremidade de nuvem pública do `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration` Azure AD.

 - Se o locatário estiver definido para federação, os Serviços de Federação do Active Directory (AD FS) serão atualizados para sincronizar com o Azure AD Public. Você pode seguir instruções para atualizar as configurações Conexão do Azure AD para fazer essa alteração.

 - Os aplicativos de recurso, se algum, usados por seus aplicativos são modificados para aceitar tokens assinados pelo Azure AD Germany e pelo Azure AD Public.
 
**Que tipo de aplicativos?**

Um aplicativo pode ser qualquer um dos seguintes:

- [Aplicativo de página única (SPA)](/azure/active-directory/develop/scenario-spa-overview)
- [Aplicativo Web que se ins signa em usuários](/azure/active-directory/develop/scenario-web-app-sign-user-overview)
- [Aplicativo Web que chama APIs da Web](/azure/active-directory/develop/scenario-web-app-call-api-overview)
- [API da Web protegida](/azure/active-directory/develop/scenario-protected-web-api-overview)
- [API Web que chama APIs da Web](/azure/active-directory/develop/scenario-web-api-call-api-overview)
- [Aplicativo da área de trabalho](/azure/active-directory/develop/scenario-desktop-overview)
- [Aplicativo Daemon](/azure/active-directory/develop/scenario-daemon-overview)
- [Aplicativo móvel](/azure/active-directory/develop/scenario-mobile-overview)
 
> [!NOTE] 
> Quando um aplicativo alterna para `login.microsoftonline.com` usar como sua autoridade, os tokens serão assinados por essa nova autoridade. Se você hospedar todos os aplicativos de recurso que outros aplicativos chamarem, você precisará permitir a validação de token de frouxa. Isso significa que seu aplicativo precisa permitir tokens assinados pelas nuvens públicas do Azure AD Germany e do Azure AD. Essa validação de token de frouxa é necessária até que todos os aplicativos cliente que chamam seu serviço sejam totalmente migrados para a nuvem pública do Azure AD. Após a migração, seu aplicativo de recurso só precisa aceitar tokens assinados pela nuvem pública do Azure AD.

**O que preciso atualizar?**

1. Se você estiver hospedando um aplicativo no Azure Alemanha usado para autenticar usuários do Azure Germany ou Office 365 Alemanha, certifique-se de que seja usado como autoridade no contexto de `https://login.microsoftonline.com` autenticação.

    - Consulte contextos de autenticação do Azure AD.
    - Isso se aplica à autenticação ao seu aplicativo, bem como à autenticação a todas as APIs que seu aplicativo possa estar chamando (ou seja, Microsoft Graph, Azure AD Graph, Gerenciador de Recursos do Azure).

2. Atualizar o ponto de extremidade do Azure AD Graph ser `https://graph.windows.net` .

3. Atualize o ponto Graph MS para `https://graph.microsoft.com` ser .

4. Atualize todos os pontos de extremidade de nuvem alemães (como os do Exchange Online e SharePoint Online) que são usados por seus aplicativos para serem os da nuvem pública.

5. Atualizar parâmetros de ambiente `AzurePublic` a serem (em vez `AzureGermany` de ) em ferramentas administrativas e scripts para:

    - [Azure PowerShell](/powershell/azure/install-az-ps)
    - [PowerShell do Azure AD (MSOnline)](/powershell/azure/active-directory/overview)
    - [Azure AD PowerShell (AzureAD)](/powershell/azure/active-directory/install-adv2)
    - [Azure CLI](/cli/azure/install-azure-cli)
 
**E os aplicativos que publico?**

Se você publicar um aplicativo que esteja disponível para usuários que estão fora do seu locatário, talvez seja necessário alterar o registro do aplicativo para garantir a continuidade. Outros locatários que usam seu aplicativo podem ser movidos em um momento diferente do seu locatário. Para garantir que eles nunca percam o acesso ao seu aplicativo, você precisará consentir que seu aplicativo seja sincronizado do Azure Germany para o público do Azure.

## <a name="additional-considerations"></a>Considerações adicionais

Aqui estão algumas considerações adicionais para o Azure AD:

- Para autenticação federada:

  - Você não deve criar, promover ou rebaixar um domínio federado enquanto a transição de locatário estiver em processo. Após a migração para o serviço do Azure AD ser concluída (o locatário está totalmente concluído), você pode continuar a gerenciar domínios federados.

  - Se você estiver usando a autenticação federada com os Serviços de Federação do Active Directory (AD FS), não deverá fazer alterações nas URIs do Emissor usadas para toda a autenticação com os Serviços de Domínio do Active Directory (AD DS) locais durante a migração. Alterar URIs do emissor levará a falhas de autenticação para usuários no domínio. URIs do emissor podem ser alteradas diretamente no AD FS ou quando um domínio é convertido de gerenciado para federado e vice-versa. A Microsoft recomenda que os clientes não adicionem, removam ou convertam um domínio federado no locatário do Azure AD que está sendo migrado. As URIs do emissor podem ser alteradas depois que a migração estiver completa.

- Para rede:

  - A criação de redes nomeadas por IPv6 não funciona no portal do Azure, `http://portal.microsoftazure.de/` . Use o portal do Azure em para criar redes nomeadas `https://portal.azure.com` por IPv6.
 
   - Não é possível criar intervalos de endereços IP confiáveis para configurações de serviço MFA (Autenticação Multifacional) do Azure a partir do portal do Microsoft Cloud Deutschland. Use o portal do Azure AD para Office 365 serviços para criar intervalos de endereços IP confiáveis do Azure MFA.


- Para Acesso Condicional: 

  - As políticas de Acesso Condicional com os seguintes controles de concessão não são suportadas até que a migração para serviços Office 365 seja concluída (após a fase de migração finalizar o [Azure AD):](ms-cloud-germany-transition.md#how-is-the-migration-organized)

    - Exigir dispositivo compatível
    - Exigir aplicativo aprovado
    - Exigir Política de Proteção de Aplicativos
    
  - A interface de política de Acesso Condicional dá um aviso falso sobre os padrões de segurança que estão sendo habilitados para o locatário mesmo quando ele está desabilitado, e as políticas de Acesso Condicional já existem para o locatário. Você deve ignorar o aviso ou usar o portal de serviços Office 365 para gerenciar políticas de Acesso Condicional. 

- Os cenários do Intune só são suportados em pontos de extremidade mundiais após a conclusão da migração de locatários, incluindo todas as migrações de cargas de trabalho do office.

- Os usuários do Microsoft Cloud Deutschland que usam o método de Notificação de Aplicativo Móvel para solicitações MFA veem ObjectId (um GUID) do usuário em vez do nome principal do usuário (UPN) no aplicativo Microsoft Authenticator do usuário. Após a migração do locatário do Azure AD ser concluída e hospedada em serviços Office 365, novas Microsoft Authenticator ativações exibirão os UPNs dos usuários. As contas Microsoft Authenticator existentes continuarão a exibir o objectId do usuário, mas continuarão a funcionar para notificações de aplicativo móvel. 

- Para locatários criados após 22 de outubro de 2019, os padrões de segurança podem ser habilitados automaticamente para o locatário quando migrados para o serviço Office 365. Os administradores de locatários podem optar por deixar os padrões de segurança habilitados e se registrar no MFA, ou podem desabilitar o recurso. Para obter mais informações, consulte [Desabilitando padrões de segurança](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults#disabling-security-defaults). 

  > [!NOTE]
  > As organizações que não estão habilitadas automaticamente durante a migração ainda poderão ser automaticamente inscritas no futuro, pois o recurso para habilitar padrões de segurança é lançado no serviço Office 365 de segurança. Os administradores que optarem por desabilitar ou habilitar explicitamente os padrões de segurança podem fazer isso atualizando o recurso em Azure Active Directory > **Propriedades**. Depois que o recurso for explicitamente habilitado pelo administrador, ele não será habilitado automaticamente.

- Haverá um aviso sobre a versão do Azure AD Conexão no portal Office 365 Alemanha, bem como no portal Office 365 uma vez que o locatário está em migração. Isso pode ser ignorado se o aviso de versão não estiver mais mostrando o aviso após a conclusão da migração. Se houver um aviso, antes ou depois da migração, em qualquer portal, o Azure AD Conexão deve ser atualizado. A mensagem de aviso diz: "Detectamos que você está usando uma ferramenta de sincronização de diretório desatualizada. Recomendamos que você vá para o Centro de Download da Microsoft para obter a versão mais recente do Azure AD Conexão."

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