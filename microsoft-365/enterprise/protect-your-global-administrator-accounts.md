---
title: Proteger suas contas de administrador global do Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- m365initiative-coredeploy
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- BCS160
f1.keywords:
- NOCSH
ms.assetid: 6b4ded77-ac8d-42ed-8606-c014fd947560
description: Este artigo fornece informações sobre como proteger o acesso de administrador global à sua assinatura do Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1f84ca33a620c3ea3c24f46eb29c1a39c28840e7
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289634"
---
# <a name="protect-your-microsoft-365-global-administrator-accounts"></a>Proteger suas contas de administrador global do Microsoft 365

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

As violações de segurança de uma assinatura do Microsoft 365, incluindo a coleta de informações e os ataques de phishing, geralmente são feitas comprometendo as credenciais de uma conta de administrador global do Microsoft 365. A segurança na nuvem é uma parceria entre você e a Microsoft:
  
- Os serviços de nuvem da Microsoft são construídos em uma base de confiança e segurança. A Microsoft fornece controles e recursos de segurança para ajudá-lo a proteger seus dados e aplicativos.
    
- Você possui seus dados e identidades e a responsabilidade de protegê-los, a segurança de seus recursos locais e a segurança dos componentes de nuvem que você controla.
    
A Microsoft fornece recursos para ajudar a proteger sua organização, mas eles só serão eficazes se você usá-los. Se você não usá-los, poderá estar vulnerável a ataques. Para proteger suas contas de administrador global, a Microsoft está aqui para ajudá-lo com instruções detalhadas para:
  
1. Crie contas dedicadas de administrador global do Microsoft 365 e use-as somente quando necessário.
    
2. Configure a autenticação multifato para suas contas dedicadas de administrador global do Microsoft 365 e use a forma mais forte de autenticação secundária.
    
> [!Note]
> Embora este artigo se concentre em contas de administradores globais, você deve considerar se contas adicionais com permissões abrangentes para acessar os dados em sua assinatura, como contas de administrador de descoberta e segurança ou conformidade, devem ser protegidas da mesma maneira. <br > Uma conta de administrador global pode ser criada sem adicionar nenhuma licença.
  
## <a name="step-1-create-dedicated-microsoft-365-global-administrator-accounts-and-use-them-only-when-necessary"></a>Etapa 1. Criar contas dedicadas de administrador global do Microsoft 365 e usá-las somente quando necessário

Há relativamente poucas tarefas administrativas, como a atribuição de funções a contas de usuário, que exigem privilégios de administrador global. Portanto, em vez de usar contas de usuário diárias que tenham sido atribuídas à função de administrador global, faça estas etapas:
  
1. Determine o conjunto de contas de usuário que foram atribuídas à função de administrador global. Você pode fazer isso no centro de administração do Microsoft 365 ou com o seguinte comando do PowerShell do Diretório do Azure Active (Azure AD) para Graph:
  
  ```powershell
  Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Global Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```

2. Entre em sua assinatura do Microsoft 365 com uma conta de usuário que tenha sido atribuída à função de administrador global.
    
3. Crie até um máximo de quatro contas de usuário de administrador global dedicadas. **Use senhas fortes com pelo menos 12 caracteres.** Consulte [Criar uma senha forte](https://support.microsoft.com/help/4026406/microsoft-account-create-a-strong-password) para obter mais informações. Armazene as senhas das novas contas em um local seguro. 
    
4. Atribua a função de administrador global a cada uma das novas contas de usuário de administrador global dedicadas.
    
5. Saia do Microsoft 365.
    
6. Entre com uma das novas contas de usuário de administrador global dedicadas.
    
7. Para cada conta de usuário existente que tenha sido atribuída a função de administrador global da etapa 1:
    
  - Remova a função de administrador global.
    
  - Atribua funções de administrador à conta apropriada à função e responsabilidade do trabalho desse usuário. Para saber mais sobre várias funções de administrador no Microsoft 365, confira [Sobre funções de administrador.](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)
    
8. Saia do Microsoft 365.
    
Os resultados devem ser:
  
- As únicas contas de usuários que possuem a função de administrador global em sua assinatura fazem parte do novo conjunto de contas de administradores globais dedicadas. Verifique isso com o seguinte comando do PowerShell:
    
  ```powershell
  Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```

- Todas as outras contas de usuários comuns que gerenciam sua assinatura têm funções de administrador atribuídas que estão associadas às responsabilidades de trabalho deles.
    
A partir deste momento em diante, você pode entrar com as contas de administrador global dedicadas apenas para tarefas que exigem privilégios de administrador global. Todas as outras administração do Microsoft 365 devem ser feitas atribuindo outras funções de administração a contas de usuário.
  
> [!NOTE]
> Isso exige etapas adicionais para sair como sua conta de usuário do dia a dia e entrar com uma conta de administrador global dedicada. Mas isso só precisa ser feito ocasionalmente para operações de administrador global. Considere que recuperar sua assinatura do Microsoft 365 após uma violação de conta de administrador global requer muito mais etapas.
  
## <a name="step-2-configure-multi-factor-authentication-for-your-dedicated-microsoft-365-global-administrator-accounts"></a>Etapa 2. Configurar a autenticação multifaionária para suas contas dedicadas de administrador global do Microsoft 365

A MFA (autenticação multifatória) exige informações adicionais além do nome e da senha da conta. O Microsoft 365 dá suporte a estes métodos de verificação adicionais:
  
- O aplicativo Microsoft Authenticator

- Uma chamada telefônica
    
- Um código de verificação gerado aleatoriamente enviado por meio de uma mensagem de texto
    
- Um cartão inteligente (físico ou virtual)
    
- Um dispositivo biométrico
    
>[!Note]
>Para organizações que devem aderir aos padrões do Instituto Nacional de Padrões e Tecnologia (NIST), o uso de uma chamada telefônica ou métodos de verificação adicionais baseados em mensagem de texto são restritos. Clique [aqui](https://pages.nist.gov/800-63-FAQ/#q-b01) para obter os detalhes.
>

Se você for uma pequena empresa que usa contas de usuário armazenadas somente na nuvem (o modelo de identidade somente na nuvem), configure a MFA para configurar a [MFA](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication) usando uma chamada telefônica ou um código de verificação de mensagem de texto enviado a um smartphone para cada conta de administrador global dedicada.
    
Se você for uma organização maior que está usando um modelo de identidade híbrida do Microsoft 365, terá mais opções de verificação. Se você já tiver a infraestrutura de segurança para um método de autenticação secundário mais forte, configure a [MFA](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication) e configure cada conta de administrador global dedicada para o método de verificação apropriado.
  
Se a infraestrutura de segurança para o método de verificação mais forte desejado não estiver em funcionamento para o Microsoft 365 MFA, recomendamos que você configure contas de administrador global dedicadas com a MFA usando o aplicativo Microsoft Authenticator, uma chamada telefônica ou um código de verificação de mensagem de texto enviado a um smartphone para suas contas de administrador global como uma medida de segurança provisória. Não deixe suas contas dedicadas de administrador global sem a proteção adicional fornecida pela MFA.
  
Para saber mais, confira [MFA para o Microsoft 365.](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/multi-factor-authentication-microsoft-365)
  
Para se conectar aos serviços do Microsoft 365 com a MFA e o PowerShell, confira estes artigos:

- [PowerShell para Microsoft 365 para contas de usuário, grupos e licenças](connect-to-microsoft-365-powershell.md)
- [Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-powershell-install)
- [Exchange Online](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-using-mfa)
- [SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online#to-connect-with-multifactor-authentication-mfa)
- [Skype for Business Online](manage-skype-for-business-online-with-microsoft-365-powershell.md#connect-using-an-admin-account-with-multi-factor-authentication)

## <a name="additional-protections-for-enterprise-organizations"></a>Proteções adicionais para organizações corporativas

Use esses métodos adicionais para garantir que sua conta de administrador global e a configuração que você executa usando-a sejam o mais seguras possível.
  
### <a name="privileged-access-workstation"></a>Estação de trabalho de acesso privilegiado

Para garantir que a execução de tarefas altamente privilegiadas seja o mais segura possível, use uma estação de trabalho de acesso privilegiado (PAW). A PAW é um computador dedicado que só é usado para tarefas de configuração confidenciais, como a configuração do Microsoft 365 que requer uma conta de administrador global. Como esse computador não é usado diariamente para navegação ou email na Internet, ele está melhor protegido contra ameaças e ataques à Internet.
  
Para obter instruções sobre como configurar uma PAW, consulte [https://aka.ms/cyberpaw](https://aka.ms/cyberpaw) .

Para habilitar o Azure PIM para seu locatário do Azure AD e as contas de administrador global, confira as [etapas para configurar o PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).

Para desenvolver um roteiro abrangente para proteger o acesso privilegiado contra invasores cibernéticos, confira [Proteger o acesso privilegiado para implantações híbridas e nuvem no Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).

### <a name="azure-ad-privileged-identity-management"></a>Azure AD Privileged Identity Management

Em vez de ter suas contas de administrador global atribuídas permanentemente à função de administrador global, você pode usar o Azure AD Privileged Identity Management (PIM) para habilitar a atribuição just-in-time sob demanda da função de administrador global quando necessário.
  
Suas contas de administrador global vão de administradores permanentes para administradores qualificados. A função de administrador global fica inativa até que alguém precise dela. Em seguida, conclua um processo de ativação para adicionar a função de administrador global à conta de administrador global por um período predeterminado. Quando o tempo expira, o PIM remove a função de administrador global da conta de administrador global.
  
Usar o PIM e esse processo reduz significativamente o tempo que suas contas de administrador global ficam vulneráveis a ataques e uso por usuários mal-intencionados.

O PIM está disponível com o Azure Active Directory Premium P2, que vem incluso no Microsoft 365 Enterprise E5. Como alternativa, você pode adquirir licenças do Azure Active Directory Premium P2 individuais para suas contas de administrador.
  
Para saber mais, confira [O Azure AD Privileged Identity Management.](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)
  

### <a name="privileged-access-management"></a>Gerenciamento de acesso privilegiado

O gerenciamento do acesso privilegiado é habilitado pela configuração de políticas que especificam o acesso pontual a atividades baseadas em tarefas em seu locatário. Ele pode ajudar a proteger sua organização contra violações que podem usar contas de administrador existentes com acesso permanente a dados confidenciais ou acesso a definições críticas de configuração. Por exemplo, você pode configurar uma política de gerenciamento de acesso privilegiado que requer a aprovação explícita para acessar e alterar configurações de caixas de correio da organização em seu locatário.

Nesta etapa, você vai habilitar o gerenciamento do acesso privilegiado em seu locatário e configurar políticas de acesso privilegiado que proporcionam segurança adicionar para o acesso aos dados baseado em tarefas e definições de configuração em sua organização. Existem três etapas básicas para iniciar o acesso privilegiado em sua organização:

- Criar um grupo de aprovadores
- Habilitar o acesso privilegiado
- Criar políticas de aprovação

O gerenciamento de acesso privilegiado permite que sua organização opere com zero privilégios permanentes e forneça uma camada de defesa contra vulnerabilidades decorrentes desse acesso administrativo permanente. O acesso privilegiado requer aprovações para executar qualquer tarefa que tenha uma política de aprovação associada definida. Os usuários que precisam executar tarefas incluídas na política de aprovação devem solicitar e ter a aprovação de acesso concedida.

Para habilitar o gerenciamento de acesso privilegiado, consulte [Configurar o gerenciamento de acesso privilegiado.](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration)

Para obter mais informações, consulte [Gerenciamento de acesso privilegiado.](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview)

### <a name="security-information-and-event-management-siem-software-for-microsoft-365-logging"></a>Software de gerenciamento de eventos e informações de segurança (SIEM) para registro em log do Microsoft 365

O software SIEM executado em um servidor executa a análise em tempo real de alertas e eventos de segurança criados por aplicativos e hardware de rede. Para permitir que seu servidor SIEM inclua alertas e eventos de segurança do Microsoft 365 em suas funções de análise e relatório, integre o Azure AD ao SEU SEIM. Confira [a introdução à integração de log do Azure.](https://docs.microsoft.com/azure/security/security-azure-log-integration-overview)

## <a name="next-step"></a>Próxima etapa

Se você estiver configurando a identidade da sua assinatura do Microsoft 365, confira:

- [Identidades somente na nuvem](cloud-only-identities.md) se você estiver usando a identidade somente na nuvem
- [Prepare-se para a sincronização de](prepare-for-directory-synchronization.md) diretório se estiver usando a identidade híbrida

  
## <a name="see-also"></a>Confira também

[Roteiro de segurança do Microsoft 365](https://docs.microsoft.com/office365/securitycompliance/security-roadmap)
