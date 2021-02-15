---
title: Sincronização híbrida de identidade e diretório para o Microsoft 365
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
description: Descreve a sincronização de diretórios com o Microsoft 365, a limpeza dos Serviços de Domínio active Directory e a ferramenta Azure Active Directory Connect.
ms.openlocfilehash: 02b594f9db02df7e855a20dfc65b21ab2dbe91c0
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327374"
---
# <a name="hybrid-identity-and-directory-synchronization-for-microsoft-365"></a>Sincronização híbrida de identidade e diretório para o Microsoft 365

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

Dependendo das suas necessidades comerciais e requisitos técnicos, o modelo de identidade híbrida e a sincronização de diretórios é a opção mais comum para clientes corporativos que estão adotando o Microsoft 365. A sincronização de diretórios permite gerenciar identidades em seus Serviços de Domínio do Active Directory (AD DS) e todas as atualizações de contas de usuário, grupos e contatos são sincronizadas com o locatário do Azure Active Directory (Azure AD) de sua assinatura do Microsoft 365.

>[!Note]
>Quando as contas de usuário do AD DS são sincronizadas pela primeira vez, elas não são atribuídas automaticamente a uma licença do Microsoft 365 e não podem acessar os serviços do Microsoft 365, como email. Primeiro você deve atribuir a eles um local de uso. Em seguida, atribua uma licença a essas contas de usuário, individual ou dinamicamente por meio da associação de grupo.
>

## <a name="authentication-for-hybrid-identity"></a>Autenticação para identidade híbrida

Há dois tipos de autenticação ao usar o modelo de identidade híbrida:

- Autenticação gerenciada

  O Azure AD lida com o processo de autenticação usando uma versão com hashed armazenada localmente da senha ou envia as credenciais para um agente de software local a ser autenticado pelo AD DS local.

- Autenticação federada

  O Azure AD redireciona o computador cliente solicitando autenticação para outro provedor de identidade.

### <a name="managed-authentication"></a>Autenticação gerenciada

Há dois tipos de autenticação gerenciada:

- Sincronização de hash de senha (PHS)

  O Azure AD realiza a própria autenticação.

- Autenticação de passagem (PTA)

  O Azure AD faz o AD DS executar a autenticação.


#### <a name="password-hash-synchronization-phs"></a>Sincronização de hash de senha (PHS)

Com o PHS, você sincroniza suas contas de usuário do AD DS com o Microsoft 365 e gerencia seus usuários no local. Hashes de senhas de usuário são sincronizados do AD DS com o Azure AD para que os usuários tenham a mesma senha no local e na nuvem. Essa é a maneira mais simples de habilitar a autenticação para identidades do AD DS no Azure AD. 

![Sincronização de hash de senha (PHS)](../media/plan-for-directory-synchronization/phs-authentication.png)

Quando as senhas são alteradas ou redefinidas no local, os novos hashes de senha são sincronizados com o Azure AD para que os usuários sempre possam usar a mesma senha para recursos de nuvem e recursos locais. As senhas de usuário nunca são enviadas ao Azure AD ou armazenadas no Azure AD em texto não limpo. Alguns recursos premium do Azure AD, como o Identity Protection, exigem PHS independentemente do método de autenticação selecionado.
  
Veja [como escolher o método de autenticação certo](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) para saber mais.
  
#### <a name="pass-through-authentication-pta"></a>Autenticação de passagem (PTA)

O PTA fornece uma validação de senha simples para serviços de autenticação do Azure AD usando um agente de software em execução em um ou mais servidores locais para validar os usuários diretamente com seu AD DS. Com o PTA, você sincroniza contas de usuário do AD DS com o Microsoft 365 e gerencia seus usuários no local. 

![Autenticação de passagem (PTA)](../media/plan-for-directory-synchronization/pta-authentication.png)

O PTA permite que os usuários se inscrevam em aplicativos e recursos locais e do Microsoft 365 usando sua conta e senha locais. Essa configuração valida senhas de usuários diretamente no AD DS local sem armazenar hashes de senha no Azure AD. 

O PTA também se aplica a organizações com um requisito de segurança para impor imediatamente estados de conta de usuário locais, políticas de senha e horas de logon. 
  
Veja [como escolher o método de autenticação certo](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) para saber mais.
  
### <a name="federated-authentication"></a>Autenticação federada

A autenticação federada é principalmente para grandes organizações empresariais com requisitos de autenticação mais complexos. As identidades do AD DS são sincronizadas com o Microsoft 365 e as contas de usuários são gerenciadas no local. Com a autenticação federada, os usuários têm a mesma senha no local e na nuvem e não precisam entrar novamente para usar o Microsoft 365. 

A autenticação federada pode dar suporte a requisitos de autenticação adicionais, como a autenticação baseada em cartão inteligente ou uma autenticação multifatória de terceiros, e normalmente é necessária quando as organizações têm um requisito de autenticação que não tem suporte nativo do Azure AD.
 
Veja [como escolher o método de autenticação certo](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) para saber mais.
  
#### <a name="third-party-authentication-and-identity-providers"></a>Provedores de identidade e autenticação de terceiros

Os objetos de diretório local podem ser sincronizados com o Microsoft 365 e o acesso a recursos na nuvem é gerenciado principalmente por um IdP (provedor de identidade) de terceiros. Se sua organização usa uma solução de federação de terceiros, você pode configurar o login com essa solução para o Microsoft 365, desde que a solução de federação de terceiros seja compatível com o Azure AD.
  
Confira a lista de compatibilidade de federação do [Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-federation-compatibility) para saber mais.
  
## <a name="ad-ds-preparation"></a>Preparação do AD DS

Para ajudar a garantir uma transição perfeita para o Microsoft 365 usando a sincronização, você deve preparar sua floresta do AD DS antes de iniciar a implantação de sincronização de diretórios do Microsoft 365.
  
A preparação do diretório deve se concentrar nas seguintes tarefas:

- Remova os **atributos proxyAddress e** **userPrincipalName duplicados.**
- Atualize atributos **userPrincipalName em** branco e inválidos com atributos **válidos userPrincipalName.**
- Remova caracteres inválidos e questionáveis nos atributos **givenName**, surname ( **sn** ), **sAMAccountName**, **displayName**, **mail**, **proxyAddresses**, **mailNickname** e **userPrincipalName.** Para obter detalhes sobre como preparar atributos, consulte Lista de atributos que são sincronizados pela Ferramenta de Sincronização do [Azure Active Directory.](https://go.microsoft.com/fwlink/p/?LinkId=396719)

    > [!NOTE]
    > Esses são os mesmos atributos que o Azure AD Connect sincroniza. 
  
## <a name="multi-forest-deployment-considerations"></a>Considerações sobre a implantação de várias florestas

Para várias florestas e opções de SSO, use uma [instalação personalizada do Azure AD Connect.](https://go.microsoft.com/fwlink/p/?LinkId=698430)
  
Se sua organização tiver várias florestas para autenticação (florestas de logon), recomendamos o seguinte:
  
- **Considere a consolidação de suas florestas.** Em geral, há mais sobrecarga necessária para manter várias florestas. A menos que sua organização tenha restrições de segurança que ditam a necessidade de florestas separadas, considere simplificar seu ambiente local.
- **Use somente em sua floresta de logon principal.** Considere a implantação do Microsoft 365 somente em sua floresta de logon principal para a distribuição inicial do Microsoft 365. 

Se você não puder consolidar sua implantação do AD DS de várias florestas ou estiver usando outros serviços de diretório para gerenciar identidades, poderá sincronisá-los com a ajuda da Microsoft ou de um parceiro.
  
Consulte [Topologias do Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-topologies) para obter mais informações.
  
## <a name="features-that-are-dependent-on-directory-synchronization"></a>Recursos que dependem da sincronização de diretórios
  
A sincronização de diretórios é necessária para os seguintes recursos e funcionalidades:
  
- SSO (single Sign-On) contínuo do Azure AD
- Coexistência do Skype
- Implantação híbrida do Exchange, incluindo:
  - Gal (lista de endereços global) totalmente compartilhada entre seu ambiente local do Exchange e o Microsoft 365.
  - Sincronizar informação de GAL de sistemas de email diferentes.
  - A capacidade de adicionar e remover usuários das ofertas de serviço do Microsoft 365. Isto exige o seguinte:
  - A sincronização de duas vias deve ser configurada durante a configuração de sincronização de diretórios. Por padrão, as ferramentas de sincronização de diretórios só gravarão informações de diretório na nuvem. Ao configurar a sincronização de duas vias, você habilita a funcionalidade de write-back para que um número limitado de atributos de objeto sejam copiados da nuvem e, em seguida, gravados de volta no AD DS local. Write-back também é conhecido como modo híbrido do Exchange. 
  - Uma implantação híbrida do Exchange local
  - A capacidade de mover algumas caixas de correio de usuário para o Microsoft 365 enquanto mantém outras caixas de correio do usuário no local.
  - Os envios seguros e bloqueados no local são replicados para o Microsoft 365.
  - Delegação básica e funcionalidade de email enviar em nome de.
  - Você tem um cartão inteligente local integrado ou uma solução de autenticação multifafa.
- Sincronização de fotos, miniaturas, salas de conferência e grupos de segurança

## <a name="next-step"></a>Próxima etapa

Quando você estiver pronto para implantar a identidade híbrida, [consulte preparar-se para a sincronização de diretórios.](prepare-for-directory-synchronization.md)
  
