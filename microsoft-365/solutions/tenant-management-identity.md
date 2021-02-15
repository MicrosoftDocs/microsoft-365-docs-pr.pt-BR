---
title: Etapa 3. Identidade dos locatários do Microsoft 365 para empresas
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
ms.custom:
- Ent_Solutions
description: Implante o modelo de identidade correto para seus locatários do Microsoft 365 e im enforce strong user sign-ins.
ms.openlocfilehash: 40ea67d9b30a385e36af45f57bd33906c10e495d
ms.sourcegitcommit: 99a7354e6a6b4d9d5202674ef57852d52a43fef6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/20/2021
ms.locfileid: "49908432"
---
# <a name="step-3-identity-for-your-microsoft-365-for-enterprise-tenants"></a>Etapa 3. Identidade dos locatários do Microsoft 365 para empresas

Seu locatário do Microsoft 365 inclui um locatário do Azure Active Directory (Azure AD) para gerenciar identidades e autenticação de logins. Configurar a infraestrutura de identidade corretamente é essencial para gerenciar o acesso e as permissões de usuário do Microsoft 365 para sua organização.

## <a name="cloud-only-vs-hybrid"></a>Somente nuvem versus híbrida

Aqui estão os dois tipos de modelos de identidade e seus melhores benefícios e ajuste.


| Modelo | Descrição | Como o Microsoft 365 autentica as credenciais do usuário | Melhor para | Maior benefício |
|:-------|:-----|:-----|:-----|:-----|
| Apenas Nuvem | A conta de usuário existe apenas no locatário do Azure AD para o locatário do Microsoft 365. | O locatário do Azure AD para seu locatário do Microsoft 365 executa a autenticação com a conta de identidade na nuvem. | Organizações que não têm ou precisam de um AD DS local. | Simples de usar. Nenhum servidor ou ferramentas de diretório adicional é necessário. |
| Híbrido |  A conta de usuário existe nos Serviços de Domínio do Active Directory (AD DS) local e uma cópia também está no locatário do Azure AD para o locatário do Microsoft 365. O Azure AD Connect é executado em um servidor local para sincronizar as alterações do AD DS com seu locatário do Azure AD. A conta de usuário no Azure AD também pode incluir uma versão com hashed da senha da conta de usuário do AD DS já com hashed. | O locatário do Azure AD para seu locatário do Microsoft 365 lida com o processo de autenticação ou redireciona o usuário para outro provedor de identidade. | Organizações que usam o AD DS ou outro provedor de identidade. | Os usuários podem usar as mesmas credenciais ao acessar recursos locais ou baseados em nuvem. |
||||||

Aqui estão os componentes básicos da identidade somente na nuvem.
 
![Componentes básicos da identidade somente na nuvem](../media/about-microsoft-365-identity/cloud-only-identity.png)

Nesta ilustração, os usuários locais e remotos entrarão com contas no locatário do Azure AD do locatário do Microsoft 365.

Aqui estão os componentes básicos da identidade híbrida.

![Componentes básicos da identidade híbrida](../media/about-microsoft-365-identity/hybrid-identity.png)

Nesta ilustração, os usuários locais e remotos entrarão em seu locatário do Microsoft 365 com contas no locatário do Azure AD que foram copiadas do AD DS local.

## <a name="synchronizing-your-on-premises-ad-ds"></a>Sincronizando seu AD DS local

Dependendo das suas necessidades comerciais e requisitos técnicos, o modelo de identidade híbrida e a sincronização de diretórios é a opção mais comum para clientes corporativos que estão adotando o Microsoft 365. A sincronização de diretório permite gerenciar identidades no AD DS e todas as atualizações de contas de usuário, grupos e contatos são sincronizadas com o locatário do Azure AD do locatário do Microsoft 365.

>[!Note]
>Quando as contas de usuário do AD DS são sincronizadas pela primeira vez, elas não são atribuídas automaticamente a uma licença do Microsoft 365 e não podem acessar os serviços do Microsoft 365, como email. Primeiro você deve atribuir a eles um local de uso. Em seguida, atribua uma licença a essas contas de usuário, individual ou dinamicamente por meio da associação de grupo.
>

Aqui estão os dois tipos de autenticação ao usar o modelo de identidade híbrida.

| Tipo de autenticação | Descrição |
|:-------|:-----|
| Autenticação gerenciada | O Azure AD lida com o processo de autenticação usando uma versão com hashed armazenada localmente da senha ou envia as credenciais para um agente de software local a ser autenticado pelo AD DS local. <br> <br>  Há dois tipos de autenticação gerenciada: Sincronização de hash de senha (PHS) e autenticação de passagem (PTA). Com o PHS, o Azure AD executa a autenticação em si. Com o PTA, o Azure AD faz com que o AD DS execute a autenticação. |
| Autenticação federada | O Azure AD redireciona o computador cliente solicitando autenticação para outro provedor de identidade. |
|  |  |

Veja [como escolher o método de autenticação correto](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) para saber mais.

## <a name="enforcing-strong-sign-ins"></a>Impor logins fortes

Para aumentar a segurança das ins loções do usuário, use os recursos e funcionalidades na tabela a seguir.

| Funcionalidade | Descrição | Mais informações | Requisitos de licença |
|:-------|:-----|:-----|:-----|:-----|
| Windows Hello para Empresas | Substitui senhas por autenticação forte de dois fatores ao entrar em um dispositivo Windows. O recurso de dois fatores é um novo tipo de credencial de usuário vinculado a um dispositivo e a uma leitura biométrica ou a um PIN. | [Visão geral do Windows Hello para Empresas](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview) | Microsoft 365 E3 ou E5 |
| Proteção por senha do Microsoft Azure AD | Detecta e bloqueia senhas fracas conhecidas e suas variantes e também pode bloquear termos fracos adicionais específicos para sua organização. | [Configurar a proteção por senha do Azure AD](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) | Microsoft 365 E3 ou E5 |
| Use a autenticação multifator (MFA) | A MFA exige que as entrada do usuário sejam sujeitas a uma verificação adicional além da senha da conta do usuário, como verificação com um aplicativo de smartphone ou uma mensagem de texto enviada para um smartphone. Veja [este vídeo para](https://support.microsoft.com/office/set-up-multi-factor-authentication-in-microsoft-365-business-a32541df-079c-420d-9395-9d59354f7225) obter instruções sobre como os usuários configuram a MFA. | [MFA para Microsoft 365 para empresas](../enterprise/microsoft-365-secure-sign-in.md#mfa) | Microsoft 365 E3 ou E5 |
| Identidade e configurações de acesso ao dispositivo | Configurações e políticas que consistem em recursos de pré-requisito recomendados e suas configurações combinadas com as políticas de Acesso Condicional, Intune e Azure AD Identity Protection que determinam se uma determinada solicitação de acesso deve ser concedida e sob quais condições.  | [Configurações de identidade e acesso a dispositivos](../security/office-365-security/microsoft-365-policies-configurations.md) | Microsoft 365 E3 ou E5 |
| Azure AD Identity Protection | Proteja-se contra o comprometimento de credenciais, em que um invasor determina o nome e a senha da conta de um usuário para obter acesso aos dados e serviços de nuvem de uma organização. | [Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection) | Microsoft 365 E5 ou Microsoft 365 E3 com a Identidade & proteção contra ameaças |
|  |  |  |



## <a name="results-of-step-3"></a>Resultados da Etapa 3

Para identidade do locatário do Microsoft 365, você determinou:

- Qual modelo de identidade usar.
- Como você imporá o acesso forte de usuários e dispositivos.

Aqui está um exemplo de um locatário com os novos elementos de identidade híbrida destacados.

![Exemplo de identidade híbrida para um locatário](../media/tenant-management-overview/tenant-management-tenant-build-step3.png)

Nesta ilustração, o locatário tem:

- Uma floresta do AD DS que está sendo sincronizada com o locatário do Azure AD usando um servidor DirSync e o Azure AD Connect.
- Uma cópia das contas de usuário do AD DS e outros objetos da floresta do AD DS.
- Um conjunto de políticas de Acesso Condicional para impor acesso e entrada de usuário seguro com base na conta do usuário. 

## <a name="ongoing-maintenance-for-identity"></a>Manutenção contínua da identidade

Em uma base contínua, talvez seja necessário:

- Adicionar ou modificar contas de usuário e grupos. Para identidade somente na nuvem, você mantém seus usuários e grupos baseados em nuvem com as ferramentas do Azure AD, como o Centro de administração do Microsoft 365 ou o PowerShell. Para identidade híbrida, você mantém seus usuários e grupos locais com ferramentas do AD DS.
- Adicione ou modifique sua configuração de acesso a identidades e dispositivos para impor os requisitos de segurança de entrada.

## <a name="next-step"></a>Próxima etapa

[![Etapa 4. Migrar seus dados e servidores do Office locais](../media/tenant-management-overview/tenant-management-step-grid-migration.png)](tenant-management-migration.md)

Continue com [a](tenant-management-migration.md) migração para migrar seus servidores locais do Office e seus dados para o Microsoft 365.
