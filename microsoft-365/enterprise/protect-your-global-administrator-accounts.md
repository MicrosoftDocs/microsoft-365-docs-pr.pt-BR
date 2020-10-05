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
- M365initiative-coredeploy
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
ms.openlocfilehash: bcc1a09ca8e7c57d4d6c69400925df3531c53c4f
ms.sourcegitcommit: 8589323c1b4ab43aab30597ee66303b0a0eb71ed
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/05/2020
ms.locfileid: "48357801"
---
# <a name="protect-your-microsoft-365-global-administrator-accounts"></a>Proteger suas contas de administrador global do Microsoft 365

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

As brechas de segurança de uma assinatura do Microsoft 365, incluindo a coleta de informações e os ataques de phishing, são normalmente realizadas comprometendo as credenciais de uma conta de administrador global do Microsoft 365. A segurança na nuvem é uma parceria entre você e a Microsoft:
  
- Os serviços de nuvem da Microsoft são criados em uma base de confiança e segurança. A Microsoft fornece recursos e controles de segurança para ajudá-lo a proteger seus dados e aplicativos.
    
- Você tem seus próprios dados e identidades e a responsabilidade de protegê-los, a segurança de seus recursos locais e a segurança dos componentes de nuvem que você controla.
    
A Microsoft fornece recursos para ajudar a proteger sua organização, mas elas só serão eficazes se você usá-las. Se você não usá-los, pode estar vulnerável a ataques. Para proteger suas contas de administrador global, a Microsoft está aqui para ajudá-lo com instruções detalhadas para:
  
1. Crie contas de administrador global do Microsoft 365 dedicada e use-as somente quando necessário.
    
2. Configure a autenticação multifator para suas contas de administrador global do Microsoft 365 dedicada e use a forma mais segura de autenticação secundária.
    
> [!Note]
> Embora este artigo se concentre nas contas de administrador global, você deve considerar se as contas adicionais com permissões amplas para acessar os dados em sua assinatura, como administrador de descoberta eletrônica ou contas de administrador de segurança ou conformidade, devem ser protegidas da mesma maneira. <br > Uma conta de administrador global pode ser criada sem adicionar nenhuma licença.
  
## <a name="step-1-create-dedicated-microsoft-365-global-administrator-accounts-and-use-them-only-when-necessary"></a>Etapa 1. Criar contas de administrador global do Microsoft 365 dedicada e usá-las somente quando necessário

Há relativamente poucas tarefas administrativas, como a atribuição de funções a contas de usuário, que exigem privilégios de administrador global. Portanto, em vez de usar contas de usuário diárias às quais a função de administrador global tenha sido atribuída, siga estas etapas:
  
1. Determine o conjunto de contas de usuário que foram atribuídas à função de administrador global. Você pode fazer isso no centro de administração do Microsoft 365 ou no seguinte comando do PowerShell Active Directory (Azure AD) do Azure para Graph:
  
  ```powershell
  Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```

2. Entre em sua assinatura do Microsoft 365 com uma conta de usuário que tenha sido atribuída à função de administrador global.
    
3. Crie até um máximo de quatro contas de usuário de administrador global dedicadas. **Use senhas fortes pelo menos 12 caracteres.** Consulte [criar uma senha forte](https://support.microsoft.com/help/4026406/microsoft-account-create-a-strong-password) para obter mais informações. Armazene as senhas das novas contas em um local seguro. 
    
4. Atribua a função de administrador global a cada uma das novas contas de usuário de administrador global dedicadas.
    
5. Saia do Microsoft 365.
    
6. Entre com uma das novas contas de usuário do administrador global dedicado.
    
7. Para cada conta de usuário existente que tenha sido atribuída à função de administrador global da etapa 1:
    
  - Remova a função de administrador global.
    
  - Atribuir funções de administrador à conta que são apropriadas para a função e responsabilidade do trabalho do usuário. Para obter mais informações sobre várias funções de administrador no Microsoft 365, consulte [about admin Roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles).
    
8. Saia do Microsoft 365.
    
Os resultados devem ser:
  
- As únicas contas de usuários que possuem a função de administrador global em sua assinatura fazem parte do novo conjunto de contas de administradores globais dedicadas. Verifique isso com o seguinte comando do PowerShell:
    
  ```powershell
  Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```

- Todas as outras contas de usuários comuns que gerenciam sua assinatura têm funções de administrador atribuídas que estão associadas às responsabilidades de trabalho deles.
    
Desse momento em diante, você entra com as contas de administrador global dedicadas apenas para tarefas que exigem privilégios de administrador global. Todas as outras administração do Microsoft 365 devem ser feitas por meio da atribuição de outras funções de administração às contas de usuário.
  
> [!NOTE]
> Isso requer etapas adicionais para sair como sua conta de usuário diária e entrar com uma conta de administrador global dedicada. Mas isso só precisa ser feito ocasionalmente para operações de administrador global. Considere a recuperação de sua assinatura do Microsoft 365 após uma violação de conta de administrador global exigir muito mais etapas.
  
## <a name="step-2-configure-multi-factor-authentication-for-your-dedicated-microsoft-365-global-administrator-accounts"></a>Etapa 2. Configurar a autenticação multifator para suas contas de administrador global do Microsoft 365

A MFA (autenticação multifator) requer informações adicionais além do nome da conta e senha. O Microsoft 365 suporta estes métodos de verificação adicionais:
  
- O aplicativo Microsoft Authenticator

- Uma chamada telefônica
    
- Um código de verificação gerado aleatoriamente enviado por meio de uma mensagem de texto
    
- Um cartão inteligente (físico ou virtual)
    
- Um dispositivo biométrico
    
>[!Note]
>Para organizações que precisam cumprir os padrões do Instituto Nacional de padrões e tecnologia (NIST), o uso de um telefonema ou de métodos de verificação adicionais baseados em mensagem de texto é restrito. Clique [aqui](https://pages.nist.gov/800-63-FAQ/#q-b01) para obter os detalhes.
>

Se você é uma pequena empresa que está usando contas de usuário armazenadas apenas na nuvem (modelo de identidade somente na nuvem), [Configure o MFA](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication) para configurar o MFA usando uma chamada telefônica ou um código de verificação de mensagem de texto enviado a um telefone inteligente para cada conta de administrador global dedicada.
    
Se você é uma organização maior que usa um modelo de identidade híbrida do Microsoft 365, você tem mais opções de verificação. Se você já tiver a infraestrutura de segurança em vigor para um método de autenticação secundário mais seguro, [Configure o MFA](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication) e configure cada conta de administrador global dedicada para o método de verificação apropriado.
  
Se a infraestrutura de segurança para o método de verificação mais forte desejado não estiver em vigor e estiver funcionando para o Microsoft 365 MFA, recomendamos enfaticamente que você configure contas de administrador global dedicadas com o MFA usando o aplicativo Microsoft Authenticator, uma chamada telefônica ou um código de verificação de mensagem de texto enviado a um telefone inteligente para suas contas de administrador global como uma medida de segurança provisória. Não deixe suas contas de administrador global dedicadas sem a proteção adicional fornecida pela MFA.
  
Para obter mais informações, consulte [MFA for Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/multi-factor-authentication-microsoft-365).
  
Para se conectar aos serviços do Microsoft 365 com MFA e PowerShell, consulte estes artigos:

- [PowerShell para Microsoft 365 para contas de usuário, grupos e licenças](connect-to-microsoft-365-powershell.md)
- [Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-powershell-install)
- [Exchange Online](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-using-mfa)
- [SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online#to-connect-with-multifactor-authentication-mfa)
- [Skype for Business Online](manage-skype-for-business-online-with-microsoft-365-powershell.md#connect-using-an-admin-account-with-multi-factor-authentication)

## <a name="additional-protections-for-enterprise-organizations"></a>Proteções adicionais para organizações empresariais

Use esses métodos adicionais para garantir que sua conta de administrador global, e a configuração que você executa usando ele, sejam o mais seguras possível.
  
### <a name="privileged-access-workstation"></a>Estação de trabalho de acesso privilegiado

Para garantir que a execução de tarefas altamente privilegiadas seja o mais segura possível, use uma estação de trabalho privilegiada (pata). Um pata é um computador dedicado que é usado apenas para tarefas de configuração confidenciais, como a configuração do Microsoft 365 que requer uma conta de administrador global. Como este computador não é usado diariamente para navegação na Internet ou email, é melhor proteger contra ataques e ameaças da Internet.
  
Para obter instruções sobre como configurar um pata, consulte [https://aka.ms/cyberpaw](https://aka.ms/cyberpaw) .

Para habilitar o Azure PIM para seu locatário do Azure AD e as contas de administrador global, confira as [etapas para configurar o PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).

Para desenvolver um roteiro abrangente para proteger o acesso privilegiado contra invasores cibernéticos, confira [Proteger o acesso privilegiado para implantações híbridas e nuvem no Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).

### <a name="azure-ad-privileged-identity-management"></a>Azure AD Privileged Identity Management

Em vez de ter suas contas de administrador global atribuídas permanentemente à função de administrador global, você pode usar o gerenciamento de identidade privilegiada do Azure AD para habilitar a atribuição sob demanda e Just-in-time da função de administrador global quando for necessário.
  
Suas contas de administrador global vão de administradores permanentes para administradores qualificados. A função de administrador global está inativa até que alguém precise dela. Em seguida, conclua um processo de ativação para adicionar a função de administrador global à conta de administrador global para uma quantidade de tempo predeterminada. Quando o tempo expira, o PIM remove a função de administrador global da conta de administrador global.
  
Usar o PIM e esse processo reduz significativamente a quantidade de tempo que suas contas de administrador global estão vulneráveis a ataques e uso por usuários mal-intencionados.

O PIM está disponível com o Azure Active Directory Premium P2, que vem incluso no Microsoft 365 Enterprise E5. Como alternativa, você pode adquirir licenças do Azure Active Directory Premium P2 individuais para suas contas de administrador.
  
Para obter mais informações, consulte [Azure ad Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).
  

### <a name="privileged-access-management"></a>Gerenciamento de acesso privilegiado

O gerenciamento do acesso privilegiado é habilitado pela configuração de políticas que especificam o acesso pontual a atividades baseadas em tarefas em seu locatário. Ele pode ajudar a proteger sua organização contra violações que podem usar contas de administrador existentes com acesso permanente a dados confidenciais ou acesso a definições críticas de configuração. Por exemplo, você pode configurar uma política de gerenciamento de acesso privilegiado que requer a aprovação explícita para acessar e alterar configurações de caixas de correio da organização em seu locatário.

Nesta etapa, você vai habilitar o gerenciamento do acesso privilegiado em seu locatário e configurar políticas de acesso privilegiado que proporcionam segurança adicionar para o acesso aos dados baseado em tarefas e definições de configuração em sua organização. Existem três etapas básicas para iniciar o acesso privilegiado em sua organização:

- Criar um grupo de aprovadores
- Habilitar o acesso privilegiado
- Criar políticas de aprovação

O gerenciamento de acesso privilegiado permite que sua organização opere com nenhum privilégio de pé e forneça uma camada de defesa contra vulnerabilidades decorrentes por esse acesso administrativo em posição. O acesso privilegiado requer aprovações para executar qualquer tarefa com uma política de aprovação associada definida. Os usuários que precisam executar tarefas incluídas na política de aprovação devem solicitar e receber aprovação de acesso.

Para habilitar o gerenciamento de acesso privilegiado, consulte [Configurar o gerenciamento de acesso privilegiado](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration).

Para obter mais informações, consulte [Gerenciamento de acesso privilegiado](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview).

### <a name="security-information-and-event-management-siem-software-for-microsoft-365-logging"></a>Software de gerenciamento de eventos e informações de segurança (SIEM) para log do Microsoft 365

O software SIEM executado em um servidor realiza análises em tempo real de alertas e eventos de segurança criados por aplicativos e hardware de rede. Para permitir que seu servidor SIEM inclua alertas e eventos de segurança da Microsoft 365 em suas funções de análise e relatórios, integre o Azure AD no SEIM. Confira [introdução à integração de logs do Azure](https://docs.microsoft.com/azure/security/security-azure-log-integration-overview).

## <a name="next-step"></a>Próxima etapa

Se estiver configurando a identidade para sua assinatura do Microsoft 365, confira:

- [Identidades somente na nuvem](cloud-only-identities.md) se você estiver usando a identidade somente na nuvem
- [Preparar a sincronização de diretórios](prepare-for-directory-synchronization.md) se você estiver usando a identidade híbrida

  
## <a name="see-also"></a>Confira também

[Mapa de segurança do Microsoft 365](https://docs.microsoft.com/office365/securitycompliance/security-roadmap)
