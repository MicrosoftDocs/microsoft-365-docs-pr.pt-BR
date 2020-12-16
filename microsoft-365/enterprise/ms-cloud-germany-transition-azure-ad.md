---
title: Informações adicionais do Azure Active Directory para a migração do Microsoft Cloud Alemanha
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
description: 'Resumo: informações adicionais do Azure Active Directory ao migrar do Microsoft Cloud Alemanha (Microsoft Cloud Alemanha) para os serviços do Office 365 na nova região do datacenter alemão.'
ms.openlocfilehash: 4fc5dda95e5e7afc4d69141a9a4debd0a74c492b
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688696"
---
# <a name="additional-azure-active-directory-information-for-the-migration-from-microsoft-cloud-deutschland"></a>Informações adicionais do Azure Active Directory para a migração do Microsoft Cloud Alemanha

Para concluir a movimentação da nuvem do Azure alemão para a nuvem pública do Azure, recomendamos que o ponto de extremidade de autenticação, o gráfico do Azure Active Directory (Azure AD) e os pontos de extremidade do MS Graph para seus aplicativos sejam atualizados para os da nuvem comercial quando o ponto de extremidade do OpenID Connect (OIDC), `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration` , começa a relatar pontos de extremidade de nuvem comercial. 
 
**Quando devo fazer essa alteração?**

Você receberá uma notificação no portal do Azure/Office quando o locatário concluir a migração da nuvem do alemão para a nuvem comercial. Você tem 30 dias depois de receber essa notificação para concluir essas atualizações, de forma que seu aplicativo continue a trabalhar para locatários migrados da nuvem do Azure na Alemanha para a nuvem pública do Azure.
 
Há três pré-condições para atualizar sua autoridade de entrada:

 - O ponto de extremidade de descoberta do OIDC para seu locatário `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration` retorna pontos de extremidade de nuvem pública do Azure AD.

 - Se o seu locatário estiver configurado para Federação, o AD FS (serviços de Federação do Active Directory) será atualizado para sincronizar com o Azure AD Public. Você pode seguir as instruções para atualizar as configurações do Azure AD Connect para fazer essa alteração.

 - Os aplicativos de recurso, se houver, usados por seus aplicativos são modificados para aceitar tokens que são assinados pelo Azure AD Alemanha e pelo Azure AD público.
 
**Que tipo de aplicativos?**

Um aplicativo pode ser qualquer um dos seguintes:

- [Aplicativo de página única (SPA)](https://docs.microsoft.com/azure/active-directory/develop/scenario-spa-overview)
- [Aplicativo Web que entra nos usuários](https://docs.microsoft.com/azure/active-directory/develop/scenario-web-app-sign-user-overview)
- [Aplicativo Web que chama APIs da Web](https://docs.microsoft.com/azure/active-directory/develop/scenario-web-app-call-api-overview)
- [API Web protegida](https://docs.microsoft.com/azure/active-directory/develop/scenario-protected-web-api-overview)
- [API Web que chama APIs da Web](https://docs.microsoft.com/azure/active-directory/develop/scenario-web-api-call-api-overview)
- [Aplicativo da área de trabalho](https://docs.microsoft.com/azure/active-directory/develop/scenario-desktop-overview)
- [Aplicativo daemon](https://docs.microsoft.com/azure/active-directory/develop/scenario-daemon-overview)
- [Aplicativo móvel](https://docs.microsoft.com/azure/active-directory/develop/scenario-mobile-overview)
 
> [!NOTE] 
> Quando um aplicativo alterna para usar `login.microsoftonline.com` como sua autoridade, os tokens serão assinados por essa nova autoridade. Se você hospedar qualquer aplicativo de recurso chamado por outros aplicativos, será necessário permitir a validação de token LAX. Isso significa que seu aplicativo precisa permitir tokens assinados pelo Azure AD Alemanha e pelas nuvens públicas do Azure AD. Essa validação de token LAX é necessária até que todos os aplicativos clientes que ligam seu serviço sejam totalmente migrados para a nuvem pública do Azure AD. Após a migração, o aplicativo de recurso precisa apenas aceitar tokens assinados pela nuvem pública do Azure AD.

**O que preciso atualizar?**

1. Se você estiver hospedando um aplicativo no Azure Alemanha que é usado para autenticar os usuários do Azure Alemanha ou Office 365 Alemanha, assegure-se de que `https://login.microsoftonline.com` seja usado como autoridade no contexto de autenticação.

    - Confira os contextos de autenticação do Azure AD.
    - Isso se aplica à autenticação em seu aplicativo, bem como à autenticação de qualquer API que seu aplicativo pode estar chamando (ou seja, Microsoft Graph, Azure AD Graph, Azure Resource Manager).

2. Atualize o ponto de extremidade do Azure AD Graph para ser `https://graph.windows.net` .

3. Atualize o ponto de extremidade do MS Graph para ser `https://graph.microsoft.com` .

4. Atualize todos os pontos de extremidade da nuvem do alemão (como os do Exchange Online e do SharePoint Online) que são usados por seus aplicativos para serem aqueles da nuvem pública.

5. Atualizar parâmetros de ambiente para serem `AzurePublic` (em vez de `AzureGermany` ) em ferramentas administrativas e scripts para:

    - [Azure PowerShell](https://docs.microsoft.com/powershell/azure/install-az-ps)
    - [PowerShell do Azure AD (MSOnline)](https://docs.microsoft.com/powershell/azure/active-directory/overview)
    - [PowerShell do Azure AD (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?)
    - [CLI do Azure](https://docs.microsoft.com/cli/azure/install-azure-cli)
 
**E os aplicativos que eu publicar?**

Se você publicar um aplicativo que está disponível para usuários que estão fora do seu locatário, talvez seja necessário alterar seu registro de aplicativo para garantir a continuidade. Outros locatários que usam seu aplicativo podem ser movidos em um horário diferente do seu locatário. Para garantir que eles nunca percam o acesso ao seu aplicativo, você precisará consentir o aplicativo que está sendo sincronizado do Azure Alemanha para o Azure Public.

## <a name="additional-considerations"></a>Considerações adicionais

Veja algumas considerações adicionais para o Azure AD:

- Para autenticação federada:

  - Você não deve criar, promover ou rebaixar um domínio federado enquanto a transição do locatário estiver em andamento. Após a migração para o serviço Azure AD ser concluída (o locatário está totalmente completo), você pode retomar o gerenciamento de domínios federados.

  - Se você estiver usando a autenticação federada com o AD FS (serviços de Federação do Active Directory), não deverá fazer alterações nos URIs de emissor usados para todas as autenticações com os serviços de domínio do Active Directory (AD DS) local durante a migração. Alterar URIs de emissor levará a falhas de autenticação para usuários no domínio. URIs de emissor podem ser alterados diretamente no AD FS ou quando um domínio é convertido de gerenciado para federado e vice-versa. A Microsoft recomenda que os clientes não adicionem, removam ou convertam um domínio federado no locatário do Azure AD que está sendo migrado. Os URIs de emissor podem ser alterados após a conclusão da migração.

- Para rede:

  - A criação de redes nomeadas por IPv6 não funciona no portal do Azure, `http://portal.microsoftazure.de/` . Use o portal do Azure em `https://portal.azure.com` para criar redes nomeadas por IPv6.
 
   - Você não pode criar intervalos de endereços IP confiáveis para as configurações do serviço de autenticação multifator do Azure (MFA) do portal Alemanha do Microsoft Cloud. Use o portal do Azure AD para serviços do Office 365 para criar intervalos de endereços IP confiáveis do Azure MFA.


- Para acesso condicional: 

  - As políticas de acesso condicional com os seguintes controles de concessão não são suportadas até que a migração para os serviços do Office 365 seja concluída (após a fase de migração [do Azure Active Directory](ms-cloud-germany-transition.md#how-is-the-migration-organized) ):

    - Exigir dispositivo em conformidade
    - Exigir aplicativo aprovado
    - Exigir política de proteção de aplicativos
    
  - A interface de política de acesso condicional fornece um falso aviso sobre os padrões de segurança sendo habilitados para o locatário, mesmo quando ele está desabilitado, e as políticas de acesso condicional já existem para o locatário. Você deve ignorar o aviso ou usar o portal de serviços do Office 365 para gerenciar as políticas de acesso condicional. 

- Os cenários do Intune têm suporte apenas em pontos de extremidade mundiais após a conclusão da migração do locatário, incluindo todas as migrações de cargas de trabalho do Office.

- Microsoft Cloud Alemanha os usuários que usam o método de notificação de aplicativo móvel para solicitações de MFA confiram o ObjectId do usuário (um GUID) em vez do nome principal do usuário (UPN) no aplicativo Microsoft Authenticator. Após a migração do locatário do Azure AD ser concluída e hospedada nos serviços do Office 365, as novas ativações do Microsoft Authenticator exibirão os UPNs dos usuários. As contas do Microsoft Authenticator existentes continuarão a exibir o ObjectId do usuário, mas continuarão a funcionar para notificações de aplicativos móveis. 

- Para locatários criados após 22 de outubro de 2019, os padrões de segurança podem ser habilitados automaticamente para o locatário quando ele for migrado para o serviço do Office 365. Os administradores de locatários podem optar por deixar os padrões de segurança habilitados e registrá-los na MFA ou podem desabilitar o recurso. Para obter mais informações, consulte [desabilitação de padrões de segurança](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults#disabling-security-defaults). 

  > [!NOTE]
  > As organizações que não são habilitadas automaticamente durante a migração ainda podem ser registradas automaticamente no futuro, pois o recurso para habilitar os padrões de segurança é implantado no serviço do Office 365. Os administradores que optam por desabilitar ou habilitar explicitamente os padrões de segurança podem fazê-lo atualizando o recurso no **Azure Active Directory > Propriedades**. Depois que o recurso for explicitamente habilitado pelo administrador, ele não será habilitado automaticamente.

- Haverá aviso sobre a versão do Azure AD Connect no portal do Office 365 Alemanha, bem como no portal do Office 365, depois que o locatário estiver em migração. Isso pode ser ignorado se o aviso de versão não estiver mais mostrando o aviso após a conclusão da migração. Se houver um aviso, antes ou depois da migração, em qualquer um dos portal, o Azure AD Connect deverá ser atualizado. A mensagem de aviso diz: "Detectamos que você está usando uma ferramenta de sincronização de diretório desatualizada. Recomendamos que você vá para o centro de download da Microsoft para obter a versão mais recente do Azure AD Connect. "

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
