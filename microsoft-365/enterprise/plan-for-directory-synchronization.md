---
title: Identidade híbrida e sincronização de diretórios para o Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.date: 09/30/2020
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MOE150
- MET150
ms.assetid: d3577c90-dda5-45ca-afb0-370d2889b10f
description: Descreve a sincronização de diretórios com o Microsoft 365, limpeza de serviços de domínio do Active Directory e a ferramenta Azure Active Directory Connect.
ms.openlocfilehash: 02b594f9db02df7e855a20dfc65b21ab2dbe91c0
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327374"
---
# <a name="hybrid-identity-and-directory-synchronization-for-microsoft-365"></a>Identidade híbrida e sincronização de diretórios para o Microsoft 365

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

Dependendo das necessidades de negócios e dos requisitos técnicos, o modelo de identidade híbrida e a sincronização de diretórios é a opção mais comum para clientes corporativos que estão adotando o Microsoft 365. A sincronização de diretórios permite gerenciar identidades em seus serviços de domínio do Active Directory (AD DS) e todas as atualizações de contas de usuário, grupos e contatos são sincronizadas com o locatário do Azure Active Directory (Azure AD) de sua assinatura do Microsoft 365.

>[!Note]
>Quando as contas de usuário do AD DS são sincronizadas pela primeira vez, elas não recebem automaticamente uma licença do Microsoft 365 e não podem acessar os serviços do Microsoft 365, como email. Primeiro você deve atribuir um local de uso a eles. Em seguida, atribua uma licença a essas contas de usuário, individualmente ou dinamicamente por meio da Associação de grupo.
>

## <a name="authentication-for-hybrid-identity"></a>Autenticação para identidade híbrida

Há dois tipos de autenticação ao usar o modelo de identidade híbrida:

- Autenticação gerenciada

  O Azure AD lida com o processo de autenticação usando uma versão de hash armazenada localmente da senha ou envia as credenciais para um agente de software local para ser autenticado pelo AD DS local.

- Autenticação federada

  O Azure AD redireciona o computador cliente solicitando autenticação para outro provedor de identidade.

### <a name="managed-authentication"></a>Autenticação gerenciada

Há dois tipos de autenticação gerenciada:

- Sincronização de hash de senha (PHS)

  O Azure AD realiza a própria autenticação.

- Autenticação de passagem (PTA)

  O Azure AD faz o AD DS executar a autenticação.


#### <a name="password-hash-synchronization-phs"></a>Sincronização de hash de senha (PHS)

Com o PHS, você sincroniza suas contas de usuário do AD DS com o Microsoft 365 e gerencia seus usuários no local. Hashes de senhas de usuário são sincronizados do AD DS para o Azure AD para que os usuários tenham a mesma senha no local e na nuvem. Essa é a maneira mais simples de habilitar a autenticação para identidades do AD DS no Azure AD. 

![Sincronização de hash de senha (PHS)](../media/plan-for-directory-synchronization/phs-authentication.png)

Quando as senhas são alteradas ou redefinidas no local, os novos hashes de senha são sincronizados com o Azure AD para que os usuários sempre possam usar a mesma senha para recursos de nuvem e recursos locais. As senhas do usuário nunca são enviadas para o Azure AD ou armazenadas no Azure AD em texto não criptografado. Alguns recursos premium do Azure AD, como proteção de identidade, exigem PHS independentemente do método de autenticação selecionado.
  
Consulte [escolher o método de autenticação certo](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) para saber mais.
  
#### <a name="pass-through-authentication-pta"></a>Autenticação de passagem (PTA)

O PTA fornece uma validação de senha simples para os serviços de autenticação do Azure AD usando um agente de software em execução em um ou mais servidores locais para validar os usuários diretamente com o AD DS. Com o PTA, você sincroniza contas de usuário do AD DS com o Microsoft 365 e gerencia seus usuários no local. 

![Autenticação de passagem (PTA)](../media/plan-for-directory-synchronization/pta-authentication.png)

O PTA permite que os usuários entrem em recursos e aplicativos locais e do Microsoft 365 usando sua conta e senha local. Essa configuração valida senhas de usuários diretamente em seu AD DS local sem armazenar hashes de senha no Azure AD. 

PTA também é para organizações com um requisito de segurança para impor imediatamente os Estados de conta de usuário local, as diretivas de senha e o horário de logon. 
  
Consulte [escolher o método de autenticação certo](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) para saber mais.
  
### <a name="federated-authentication"></a>Autenticação federada

A autenticação federada é principalmente para grandes organizações corporativas com requisitos de autenticação mais complexos. As identidades do AD DS são sincronizadas com o Microsoft 365 e as contas de usuários são gerenciadas no local. Com a autenticação federada, os usuários têm a mesma senha no local e na nuvem, e não precisam entrar novamente para usar o Microsoft 365. 

A autenticação federada pode dar suporte a requisitos de autenticação adicionais, como a autenticação com base em Smartcard ou uma autenticação multifator de terceiros e geralmente é necessária quando as organizações têm um requisito de autenticação não suportado nativamente pelo Azure AD.
 
Consulte [escolher o método de autenticação certo](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) para saber mais.
  
#### <a name="third-party-authentication-and-identity-providers"></a>Provedores de autenticação e identidade de terceiros

Os objetos de diretório no local podem ser sincronizados com o Microsoft 365 e o acesso a recursos em nuvem é basicamente gerenciado por um provedor de identidade de terceiros (IdP). Se sua organização usa uma solução de Federação de terceiros, você pode configurar o logon com essa solução para o Microsoft 365, desde que a solução de Federação de terceiros seja compatível com o Azure AD.
  
Consulte a [lista de compatibilidade de Federação do Azure ad](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-federation-compatibility) para saber mais.
  
## <a name="ad-ds-preparation"></a>Preparação do AD DS

Para ajudar a garantir uma transição contínua para o Microsoft 365 usando a sincronização, você deve preparar sua floresta do AD DS antes de começar sua implantação de sincronização de diretório do Microsoft 365.
  
A preparação do diretório deve se concentrar nas seguintes tarefas:

- Remover os atributos **ProxyAddress** e **userPrincipalName** duplicados.
- Atualizar atributos **userPrincipalName** em branco e inválidos com atributos **userPrincipalName** válidos.
- Remover caracteres inválidos e questionáveis nos atributos **repassado**, sobrenome ( **SN** ), **sAMAccountName**, **DisplayName**, **mail**, **proxyAddresses**, **mailNickname**e **userPrincipalName** . Para obter detalhes sobre como preparar atributos, consulte [lista de atributos que são sincronizados pela ferramenta de sincronização do Azure Active Directory](https://go.microsoft.com/fwlink/p/?LinkId=396719).

    > [!NOTE]
    > Estes são os mesmos atributos que o Azure AD Connect sincroniza. 
  
## <a name="multi-forest-deployment-considerations"></a>Considerações de implantação de várias florestas

Para várias florestas e opções de SSO, use uma [instalação personalizada do Azure ad Connect](https://go.microsoft.com/fwlink/p/?LinkId=698430).
  
Se sua organização tiver várias florestas para autenticação (florestas de logon), recomendamos enfaticamente o seguinte:
  
- **Considere a consolidação de suas florestas.** Em geral, há mais sobrecarga necessária para manter várias florestas. A menos que sua organização tenha restrições de segurança que ditem a necessidade de florestas separadas, considere simplificar o ambiente local.
- **Use somente na floresta de logon principal.** Considere a implantação do Microsoft 365 somente em sua floresta de logon principal para a sua distribuição inicial do Microsoft 365. 

Se você não puder consolidar sua implantação do AD DS de várias florestas ou se estiver usando outros serviços de diretório para gerenciar identidades, talvez seja possível sincronizá-las com a ajuda da Microsoft ou de um parceiro.
  
Consulte [topologias para o Azure ad Connect](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-topologies) para obter mais informações.
  
## <a name="features-that-are-dependent-on-directory-synchronization"></a>Recursos que dependem da sincronização de diretório
  
A sincronização de diretórios é necessária para os seguintes recursos e funcionalidade:
  
- Logon único (SSO) contínuo do Azure AD
- Coexistência do Skype
- Implantação híbrida do Exchange, incluindo:
  - GAL (lista de endereços global) totalmente compartilhada entre o seu ambiente do Exchange local e o Microsoft 365.
  - Sincronizar informação de GAL de sistemas de email diferentes.
  - A capacidade de adicionar usuários e remover usuários das ofertas de serviço do Microsoft 365. Isto exige o seguinte:
  - A sincronização bidirecional deve ser configurada durante a configuração de sincronização de diretório. Por padrão, as ferramentas de sincronização de diretório gravam informações de diretório somente na nuvem. Ao configurar a sincronização bidirecional, você habilita a funcionalidade de write-back para que um número limitado de atributos de objeto seja copiado da nuvem e, em seguida, os escreveu novamente no AD DS local. O Write-back também é conhecido como modo híbrido do Exchange. 
  - Uma implantação híbrida local do Exchange
  - A capacidade de mover algumas caixas de correio do usuário para a Microsoft 365 enquanto mantém outras caixas de correio do usuário no local.
  - Remetentes confiáveis e remetentes bloqueados no local são replicados para o Microsoft 365.
  - Delegação básica e funcionalidade de email enviar em nome de.
  - Você tem uma solução integrada de cartão inteligente ou de autenticação multifator no local.
- Sincronização de fotos, miniaturas, salas de conferência e grupos de segurança

## <a name="next-step"></a>Próxima etapa

Quando estiver pronto para implantar a identidade híbrida, confira [preparar para a sincronização de diretórios](prepare-for-directory-synchronization.md).
  
