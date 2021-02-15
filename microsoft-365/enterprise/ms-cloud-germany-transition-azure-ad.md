---
title: Informações adicionais do Azure Active Directory para a migração do Microsoft Cloud Deutschland
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
description: 'Resumo: informações adicionais do Azure Active Directory ao mudar do Microsoft Cloud Alemanha (Microsoft Cloud Deutschland) para os serviços do Office 365 na nova região de datacenter alemã.'
ms.openlocfilehash: 4fc5dda95e5e7afc4d69141a9a4debd0a74c492b
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688696"
---
# <a name="additional-azure-active-directory-information-for-the-migration-from-microsoft-cloud-deutschland"></a>Informações adicionais do Azure Active Directory para a migração do Microsoft Cloud Deutschland

Para concluir a mudança da nuvem alemã do Azure para a nuvem pública do Azure, recomendamos que o ponto de extremidade de autenticação, o Gráfico do Azure Active Directory (Azure AD) e os pontos de extremidade do MS Graph para seus aplicativos sejam atualizados para os pontos de extremidade da nuvem comercial quando o ponto de extremidade do OpenID Connect (OIDC) começar a relatar pontos de extremidade de nuvem `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration` comercial. 
 
**Quando devo fazer essa alteração?**

Você receberá uma notificação no portal do Azure/Office quando o locatário concluir a migração da nuvem alemã para a nuvem comercial. Você tem 30 dias após receber essa notificação para concluir essas atualizações para que seu aplicativo continue a funcionar para locatários migrados da nuvem do Azure Alemanha para a nuvem pública do Azure.
 
Há três pré-condições para atualizar sua autoridade de entrada:

 - O ponto de extremidade de descoberta OIDC para seu locatário retorna pontos de extremidade de nuvem pública `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration` do Azure AD.

 - Se o locatário estiver definido para federação, os Serviços de Federação do Active Directory (AD FS) serão atualizados para sincronização com o Azure AD Público. Você pode seguir instruções para atualizar as configurações do Azure AD Connect para fazer essa alteração.

 - Os aplicativos de recurso, se necessário, usados por seus aplicativos são modificados para aceitar tokens assinados pelo Azure AD Alemanha e pelo Azure AD Public.
 
**Que tipo de aplicativos?**

Um aplicativo pode ser qualquer um dos seguintes:

- [Aplicativo de página única (SPA)](https://docs.microsoft.com/azure/active-directory/develop/scenario-spa-overview)
- [Aplicativo Web que entre em usuários](https://docs.microsoft.com/azure/active-directory/develop/scenario-web-app-sign-user-overview)
- [Aplicativo Web que chama APIs da Web](https://docs.microsoft.com/azure/active-directory/develop/scenario-web-app-call-api-overview)
- [API Web protegida](https://docs.microsoft.com/azure/active-directory/develop/scenario-protected-web-api-overview)
- [API Web que chama APIs da Web](https://docs.microsoft.com/azure/active-directory/develop/scenario-web-api-call-api-overview)
- [Aplicativo da área de trabalho](https://docs.microsoft.com/azure/active-directory/develop/scenario-desktop-overview)
- [Aplicativo Daemon](https://docs.microsoft.com/azure/active-directory/develop/scenario-daemon-overview)
- [Aplicativo móvel](https://docs.microsoft.com/azure/active-directory/develop/scenario-mobile-overview)
 
> [!NOTE] 
> Quando um aplicativo alterna para `login.microsoftonline.com` usar como sua autoridade, os tokens serão assinados por essa nova autoridade. Se você hospedar qualquer aplicativo de recurso que outros aplicativos chamarem, será necessário permitir a validação de token de token de token de token. Isso significa que seu aplicativo precisa permitir tokens assinados pelas nuvens públicas do Azure AD Alemanha e do Azure AD. Essa validação de token de token é necessária até que todos os aplicativos cliente que chamam seu serviço sejam totalmente migrados para a nuvem pública do Azure AD. Após a migração, seu aplicativo de recurso só precisa aceitar tokens assinados pela nuvem pública do Azure AD.

**O que preciso atualizar?**

1. Se você estiver hospedando um aplicativo no Azure Alemanha usado para autenticar os usuários do Azure Alemanha ou do Office 365 Germany, certifique-se de que ele seja usado como autoridade no contexto de `https://login.microsoftonline.com` autenticação.

    - Confira os contextos de autenticação do Azure AD.
    - Isso se aplica à autenticação ao seu aplicativo, bem como à autenticação de quaisquer APIs que seu aplicativo possa estar chamando (ou seja, o Microsoft Graph, o Azure AD Graph, o Gerenciador de Recursos do Azure).

2. Atualize o ponto de extremidade do Azure AD Graph para `https://graph.windows.net` ser.

3. Atualize o ponto de extremidade do MS Graph para `https://graph.microsoft.com` ser.

4. Atualize todos os pontos de extremidade de nuvem alemães (como os do Exchange Online e do SharePoint Online) que são usados por seus aplicativos para serem aqueles da nuvem pública.

5. Atualize parâmetros de ambiente `AzurePublic` para estar (em vez de) em ferramentas `AzureGermany` administrativas e scripts para:

    - [Azure PowerShell](https://docs.microsoft.com/powershell/azure/install-az-ps)
    - [Azure AD PowerShell (MSOnline)](https://docs.microsoft.com/powershell/azure/active-directory/overview)
    - [Azure AD PowerShell (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?)
    - [Azure CLI](https://docs.microsoft.com/cli/azure/install-azure-cli)
 
**E quanto aos aplicativos que publico?**

Se você publicar um aplicativo que esteja disponível para usuários que estão fora do seu locatário, talvez seja necessário alterar o registro do aplicativo para garantir a continuidade. Outros locatários que usam seu aplicativo podem ser movidos em um momento diferente do locatário. Para garantir que eles nunca percam o acesso ao seu aplicativo, você precisará consentir com o seu aplicativo que está sendo sincronizado do Azure Alemanha para o público do Azure.

## <a name="additional-considerations"></a>Considerações adicionais

Aqui estão algumas considerações adicionais para o Azure AD:

- Para autenticação federada:

  - Você não deve criar, promover ou rebaixar um domínio federado enquanto a transição de locatário estiver em processo. Depois que a migração para o serviço do Azure AD for concluída (o locatário está totalmente concluído), você poderá retomar o gerenciamento de domínios federados.

  - Se você estiver usando a autenticação federada com os Serviços de Federação do Active Directory (AD FS), não faça alterações nos URIs do Emissor usados para toda a autenticação com seus Serviços de Domínio do Active Directory (AD DS) local durante a migração. Alterar URIs de emissores levará a falhas de autenticação para usuários no domínio. Os URIs do emissor podem ser alterados diretamente no AD FS ou quando um domínio é convertido de gerenciado para federado e vice-versa. A Microsoft recomenda que os clientes não adicionem, removam ou convertam um domínio federado no locatário do Azure AD que está sendo migrado. Os URIs do emissor podem ser alterados após a conclusão completa da migração.

- Para rede:

  - Criar redes nomeadas por IPv6 não funciona no portal do Azure. `http://portal.microsoftazure.de/` Use o portal do Azure para `https://portal.azure.com` criar redes nomeadas por IPv6.
 
   - Não é possível criar intervalos de endereços IP confiáveis para as configurações do serviço MFA (Autenticação Multifacional) do Azure no portal do Microsoft Cloud Deutschland. Use o portal do Azure AD para serviços do Office 365 para criar intervalos de endereços IP confiáveis do Azure MFA.


- Para acesso condicional: 

  - As políticas de Acesso Condicional com os seguintes controles de concessão não são suportadas até que a migração para os serviços do Office 365 seja concluída (após a fase de migração finalizar o [Azure AD):](ms-cloud-germany-transition.md#how-is-the-migration-organized)

    - Exigir dispositivo compatível
    - Exigir Aplicativo Aprovado
    - Exigir Política de Proteção de Aplicativo
    
  - A interface de política de Acesso Condicional fornece um falso aviso sobre os padrões de segurança que estão sendo habilitados para o locatário mesmo quando ele está desabilitado, e as políticas de Acesso Condicional já existem para o locatário. Você deve ignorar o aviso ou usar o portal de serviços do Office 365 para gerenciar políticas de Acesso Condicional. 

- Os cenários do Intune só são suportados em pontos de extremidade em todo o mundo após a conclusão da migração de locatários, incluindo todas as migrações de cargas de trabalho do Office.

- Os usuários do Microsoft Cloud Deutschland que usam o método de Notificação de Aplicativo Móvel para solicitações MFA veem a ObjectId (um GUID) do usuário em vez do nome UPN no aplicativo Microsoft Authenticator. Depois que a migração do locatário do Azure AD for concluída e hospedada nos serviços do Office 365, as novas ativações do Microsoft Authenticator exibirão os UPNs dos usuários. As contas existentes do Microsoft Authenticator continuarão a exibir o usuário ObjectId, mas continuarão a funcionar para notificações de aplicativo móvel. 

- Para locatários criados após 22 de outubro de 2019, os padrões de segurança podem ser habilitados automaticamente para o locatário quando ele é migrado para o serviço do Office 365. Os administradores de locatários podem optar por deixar os padrões de segurança habilitados e se registrar na MFA ou podem desabilitar o recurso. Para obter mais informações, [consulte Desabilitando os padrões de segurança.](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults#disabling-security-defaults) 

  > [!NOTE]
  > As organizações que não são habilitadas automaticamente durante a migração ainda podem ser inscritas automaticamente no futuro, pois o recurso para habilitar padrões de segurança é lançado no serviço do Office 365. Os administradores que optam por desabilitar ou habilitar explicitamente os padrões de segurança podem fazer isso atualizando o recurso em Propriedades > **Azure Active Directory.** Depois que o recurso for explicitamente habilitado pelo administrador, ele não será habilitado automaticamente.

- Haverá um aviso sobre a versão do Azure AD Connect no portal do Office 365 Germany, bem como no portal do Office 365, assim que o locatário for migrado. Isso poderá ser ignorado se o aviso de versão não estiver mais exibindo o aviso após a conclusão da migração. Se houver um aviso, antes ou depois da migração, em qualquer portal, o Azure AD Connect deverá ser atualizado. A mensagem de aviso diz: "Detectamos que você está usando uma ferramenta de sincronização de diretório desatualizada. Recomendamos que você acesse o Centro de Download da Microsoft para obter a versão mais recente do Azure AD Connect."

## <a name="more-information"></a>Mais informações

Iniciando:

- [Migração do Microsoft Cloud Deutschland para os serviços do Office 365 nas novas regiões de datacenter alemãs](ms-cloud-germany-transition.md)
- [Assistência de Migração do Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Como aceitar a migração](ms-cloud-germany-migration-opt-in.md)
- [Experiência do cliente durante a migração](ms-cloud-germany-transition-experience.md)

Passando pela transição:

- [Ações e impactos das fases de migração](ms-cloud-germany-transition-phases.md)
- [Pré-trabalho adicional](ms-cloud-germany-transition-add-pre-work.md)
- Informações adicionais para [o Azure AD](ms-cloud-germany-transition-azure-ad.md), [dispositivos,](ms-cloud-germany-transition-add-devices.md) [experiências](ms-cloud-germany-transition-add-experience.md)e [AD FS](ms-cloud-germany-transition-add-adfs.md).

Aplicativos em nuvem:

- [Informações do programa de migração do Dynamics 365](https://aka.ms/d365ceoptin)
- [Informações do programa de migração do Power BI](https://aka.ms/pbioptin)
- [Introdução à atualização do Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
