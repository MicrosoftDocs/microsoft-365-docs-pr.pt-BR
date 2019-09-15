Confira também os [pré-requisitos](https://docs.microsoft.com/microsoft-365-enterprise/identity-access-policies#prerequisites) para obter outras recomendações de infraestrutura de identidade.

<a name="crit-identity-user-groups"></a>
### <a name="required-your-users-groups-and-group-memberships-have-been-created"></a>Obrigatório: seus usuários, grupos e membros de grupos terem sido criados

Você deve ter criado contas e grupos de usuários para que:

- Os funcionários da sua organização, assim como os fornecedores, prestadores de serviços e parceiros que trabalham com a sua organização tenham uma conta de usuário correspondente no Azure Active Directory (Azure AD).
- Os grupos do Azure AD e seus membros tenham contas de usuários e outros grupos para diversos propósitos, como o provisionamento de configurações de segurança de serviços de nuvem da Microsoft, o licenciamento automático e outros usos.

Se necessário, a [Etapa 1](../identity-plan-users-groups.md) pode ajudá-lo a atender a esse requisito.

<a name="crit-identity-global-admin"></a>
### <a name="required-your-global-administrator-accounts-are-protected"></a>Obrigatório: As contas de administrador global estarem protegidas 

Você [protegeu suas contas de administrador global do Office 365](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts) para impedir o comprometimento das credenciais por invasores, o que poderia levar a violações da sua assinatura do Microsoft 365.

Se você ignorar esse requisito, suas contas de administrador global podem ficar suscetíveis a ataques e a serem comprometidas, permitindo que um invasor obtenha acesso a todo o sistema e colete, destrua ou utilize seus dados como colateral para pedir um resgate.

Se necessário, a [Etapa 2](../identity-designate-protect-admin-accounts.md#identity-global-admin) pode ajudá-lo a atender a esse requisito.

#### <a name="how-to-test"></a>Como testar

Use estas etapas para verificar se você protegeu suas contas de administrador global:

1. Execute o seguinte comando do Azure Active Directory PowerShell for Graph no prompt de comando do PowerShell. Você verá somente a lista de contas de administradores globais dedicados.
   ```
   Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
   ```
2. Entre no Office 365 usando a cada uma das contas da etapa 1. Cada entrada deve exigir a autenticação multifator e a forma mais segura de autenticação secundária disponível em sua organização.

> [!Note]
> Confira [Conectar-se ao PowerShell do Office 365](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) para obter instruções sobre como instalar o Azure Active Directory PowerShell para o módulo do Graph e entrar no Office 365.

<a name="crit-identity-pim"></a>
### <a name="optional-you-have-set-up-privileged-identity-management-to-support-on-demand-assignment-of-the-global-administrator-role"></a>Opcional: você configurou o Privileged Identity Management para dar suporte à atribuição sob demanda da função de administrador global

Você usou as instruções em [Configurar o Azure AD Privileged Identity Management (PIM)](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure) para habilitar o PIM em seu locatário do Azure AD e configurou suas contas de administrador global como administradores qualificados.

Você também deve usar as recomendações em [Proteger o acesso privilegiado para implantações híbridas e de nuvem no Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices) para desenvolver um roteiro que proteja o acesso privilegiado contra ataques cibernéticos.

Se você ignorar essa opção, as contas de administrador global estarão sujeitas a contínuos ataques cibernéticos e, se forem comprometidas, poderão permitir que um invasor colete, destrua ou use suas informações confidenciais para obter um resgate.

Se necessário, a [Etapa 2](../identity-designate-protect-admin-accounts.md#identity-pim) pode ajudá-lo com essa opção.


<a name="crit-identity-sync"></a>
### <a name="required-users-and-groups-are-synchronized-with-azure-ad"></a>Obrigatório: os usuários e os grupos devem estar sincronizados com o Azure AD

Se houver um Active Directory Domain Services (AD DS) local, é porque você usou o Azure AD Connect para sincronizar as contas de usuário e os grupos de seu AD DS local com o locatário do Azure AD.

Com a sincronização de diretórios, seus usuários poderão entrar no Office 365 e em outros serviços de nuvem da Microsoft usando as mesmas credenciais que usam para entrar em seus computadores e acessar os recursos locais.

Se necessário, a [Etapa 3](../identity-azure-ad-connect.md#identity-sync) pode ajudá-lo a atender a esse requisito.

Se ignorar esse requisito, você terá dois conjuntos de contas de usuários e grupos:

- Contas de usuários e grupos existentes no seu AD DS local
- Contas de usuários e grupos existentes em seu locatário do Azure AD

Nesse estado, os dois conjuntos de contas de usuários e grupos devem ser mantidos manualmente pelos administradores de TI e os usuários. Isso inevitavelmente levará a contas, senhas e grupos não sincronizados.

#### <a name="how-to-test"></a>Como testar
Para verificar se a autenticação com credenciais locais funciona corretamente, entre no portal do Office com suas credenciais locais.

Para verificar se a sincronização de diretórios está funcionando corretamente, faça o seguinte:

1.  Crie um novo grupo de teste no AD DS.
2.  Aguarde o tempo de sincronização.
3.  Confira se o nome do novo grupo de teste aparece no seu locatário do Azure AD.

<a name="crit-identity-sync-health"></a>
### <a name="optional-directory-synchronization-is-monitored"></a>Opcional: A sincronização de diretórios ser monitorada

Você deve usar o artigo [Azure AD Connect Health com sincronização](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) (para sincronização de senhas) ou [Usar o Azure AD Connect Health com o AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) (para autenticação federada) e implantar o Azure AD Connect Health, que envolve:

- Instalar o agente do Azure AD Connect Health em cada servidor de identidade local.
- Usar o portal do Azure AD Connect Health para monitorar o estado da sincronização em andamento.

Se ignorar essa opção, você poderá avaliar com mais precisão o estado da sua infraestrutura de identidade de nuvem.

Se necessário, a [Etapa 3](../identity-azure-ad-connect.md#identity-sync-health) pode ajudá-lo com essa opção.

#### <a name="how-to-test"></a>Como testar
O portal do Azure AD Connect Health mostra o estado atual e correto dos seus controladores de domínio locais e da sincronização em andamento.

<a name="crit-identity-mfa"></a>
### <a name="optional-multi-factor-authentication-is-enabled-for-your-users"></a>Opcional: A autenticação multifator estar habilitada para seus usuários

Você usou o [Plano para a autenticação multifator](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted) e [políticas de acesso condicional](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access) para habilitar a MFA (autenticação multifator) para suas contas de usuário.

Se você ignorar essa opção, as contas de usuários ficarão vulneráveis a terem suas credenciais comprometidas por invasores cibernéticos. Se a senha de uma conta de usuário for comprometida, todos os recursos dessa conta, como funções de administrador, estarão disponíveis para o invasor. Isso permitirá que invasor copie, destrua ou use seus documentos internos e outros dados para pedir resgate.

Se necessário, a [Etapa 4](../identity-multi-factor-authentication.md#identity-mfa) pode ajudá-lo com essa opção.

#### <a name="how-to-test"></a>Como testar

1.  Crie uma conta de usuário de teste e atribua uma licença a ela. 
2.  Configure a autenticação multifator para essa conta de usuário de teste com o método de verificação adicional que você estiver usando para as contas de usuário reais, como enviar uma mensagem de texto para um celular. 
3.  Entre no portal do Office 365 com a conta de usuário de teste.
4.  Confira se a MFA solicita informações adicionais de verificação e resulta em uma autenticação bem-sucedida. 
5.  Exclua a conta de usuário de teste.

<a name="crit-password-prot"></a>
### <a name="optional-azure-ad-password-protection-is-banning-the-use-of-weak-passwords"></a>Opcional: a proteção por senha do Azure AD estar proibindo o uso de senhas fracas

Você ativou a proibição de senhas ruins [na nuvem](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) e para o [Active Directory Domain Services (AD DS) local](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises) com base em senhas proibidas em geral e, opcionalmente, termos personalizados.

Se necessário, a [Etapa 4](../identity-multi-factor-authentication.md#identity-password-prot) pode ajudar você com essa opção.

<a name="crit-identity-ident-prot"></a>
### <a name="optional-azure-ad-identity-protection-is-enabled-to-protect-against-credential-compromise-microsoft-365-enterprise-e5-only"></a>Opcional: o Azure AD Identity Protection estar ativado para proteger você contra o comprometimento de credenciais (Microsoft 365 Enterprise E5 apenas)

Você ativou o Azure AD Identity Protection para:

- Solucionar possíveis vulnerabilidades de identidade.
- Detectar possíveis tentativas de ataque à credencial.
- Investigar e resolver incidentes suspeitos e contínuos relacionados a questões de identidade.

Se você ignorar essa opção, não poderá detectar ou automaticamente eliminar tentativas de comprometer a identidade ou investigar incidentes de segurança relacionado à identidade. Isso possivelmente deixa sua organização vulnerável a ter sua identidade comprometida e à ameaça resultante aos dados confidenciais da sua organização.

Se necessário, a [Etapa 4](../identity-multi-factor-authentication.md#identity-ident-prot) pode ajudá-lo com essa opção.

<a name="crit-identity-pw-reset"></a>
### <a name="optional-users-can-reset-their-own-passwords"></a>Opcional: os usuários podem redefinir suas próprias senhas

Você usou o artigo [Implantação rápida da redefinição da senha autoatendimento do Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) para configurar a redefinição de senha para seus usuários.

Se você não atender a essa condição, os usuários dependerão dos administradores de contas de usuários para redefinir suas senhas, resultando em esforços adicionais para a administração de TI.

Se necessário, a [Etapa 5](../identity-password-reset.md#identity-pw-reset) pode ajudá-lo com essa opção.

#### <a name="how-to-test"></a>Como testar

1. Crie uma conta de usuário de teste com uma senha inicial.
2. Use as etapas em [Permitir que os usuários redefinam suas próprias senhas no Office 365](https://docs.microsoft.com/office365/admin/add-users/let-users-reset-passwords) para redefinir a senha da conta de usuário de teste.
3. Saia e entre novamente na conta de usuário de teste usando a senha redefinida.
4. Exclua a conta de usuário de teste.

<a name="crit-identity-pw-writeback"></a>
### <a name="optional-password-writeback-is-enabled-for-your-users"></a>Opcional: O write-back de senha estar habilitado para seus usuários

Você usou as instruções em [Azure AD SSPR com write-back de senha](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) para habilitar o write-back de senha para o locatário do Azure AD da sua assinatura do Microsoft 365 Enterprise.

Se você ignorar essa opção, os usuários que não estiverem conectados à sua rede local deverão redefinir ou desbloquear as senhas do AD DS por meio do administrador de TI.

Se necessário, a [Etapa 5](../identity-password-reset.md#identity-pw-writeback) pode ajudá-lo com essa opção.

>[!Note]
>O write-back de senha é necessário para utilizar por completo os recursos do Azure AD Identity Protection, por exemplo, para solicitar que os usuários alterem suas senhas locais quando o Azure AD detectar um comprometimento de conta de alto risco.
>

#### <a name="how-to-test"></a>Como testar

Para testar o write-back de senha, você deverá alterar sua senha no Office 365. Você deve conseguir usar sua conta e a nova senha para acessar os recursos do AD DS local.

1. Crie uma conta de usuário de teste no AD DS local, permita que a sincronização de diretórios ocorra e, em seguida, conceda uma licença do Microsoft 365 Enterprise no centro de administração do Microsoft 365.
2. Em um computador remoto ingressado no domínio do AD DS local, entre no computador e no portal do Office usando as credenciais da conta de usuário de teste.
3. Selecione **Configurações > Configurações do Office 365 > Senha > Alterar senha**.
4. Digite a senha atual, digite uma nova senha e a confirme.
5. Saia do portal do Office e do computador remoto e, em seguida, entre no computador usando a conta de usuário de teste e a nova senha. Isso prova que você conseguiu mudar a senha de uma conta de usuário do AD DS local usando o locatário do Azure AD.

<a name="crit-identity-sso"></a>
### <a name="optional-users-can-sign-in-using-azure-ad-seamless-single-sign-on"></a>Opcional: os usuários podem entrar usando o logon único contínuo do Azure AD.

Você deve habilitar o [Azure AD Connect: Logon Único Simplificado](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start) para sua organização para simplificar como os usuários entram em aplicativos baseados na nuvem, como o Office 365.

Se você ignorar essa opção, é possível que seus usuários sejam solicitados a fornecer credenciais quando acessarem outros aplicativos que usam seu locatário do Azure AD.

Se necessário, a [Etapa 5](../identity-password-reset.md#identity-sso) pode ajudá-lo com essa opção.

<a name="crit-identity-custom-sign-in"></a>
### <a name="optional-the-office-365-sign-in-screen-is-personalized-for-your-organization"></a>Opcional: A tela de entrada do Office 365 ser personalizada para sua organização

Você deve usar o artigo [Adicionar a identidade visual da sua empresa às suas páginas de entrada e do Painel de Acesso](http://aka.ms/aadpaddbranding) para adicionar a identidade visual da sua organização à página de entrada do Office 365.

Se você ignorar essa opção, os usuários verão uma tela genérica de entrada do Office 365 e poderão não ter a confiança de que estão entrando no site da sua organização.

Se necessário, a [Etapa 5](../identity-password-reset.md#identity-custom-sign-in) pode ajudá-lo com essa opção.

#### <a name="how-to-test"></a>Como testar

Entre no portal do Office 365 com o nome da sua conta de usuário e a autenticação multifator. Você verá seus elementos de identidade visual personalizados na página de entrada.

<a name="crit-identity-self-service-groups"></a>
### <a name="optional-self-service-group-management-is-enabled-for-specific-azure-ad-security-and-office-365-groups"></a>Opcional: O gerenciamento de grupos por autoatendimento estar habilitado para grupos específicos de segurança do Azure AD e do Office 365

Você deve determinar quais grupos são adequados para o gerenciamento por autoatendimento, instruir seus proprietários sobre o fluxo de trabalho e as responsabilidades do gerenciamento de grupos e [configurar o gerenciamento por autoatendimento no Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management) para esses grupos.

Se você ignorar essa opção, todas as tarefas de gerenciamento de grupos do Azure AD deverão ser realizadas por administradores de TI.

Se necessário, a [Etapa 6](../identity-self-service-group-management.md#identity-self-service-groups) pode ajudá-lo com essa opção.

#### <a name="how-to-test"></a>Como testar
1.  Crie uma conta de usuário de teste no Azure AD com o portal do Azure.
2.  Entre como com a conta de usuário de teste e crie um grupo de segurança de teste do Azure AD.
3.  Saia e, em seguida, entre novamente com sua conta de administrador de TI.
4.  Configure o grupo de segurança de teste para o gerenciamento por autoatendimento para a conta de usuário de teste.
5.  Saia e, em seguida, entre novamente com sua conta de usuário de teste.
6.  Use o portal do Azure para adicionar membros ao grupo de segurança de teste.
7.  Exclua o grupo de segurança de teste e a conta de usuário de teste.

<a name="crit-identity-dyn-groups"></a>
### <a name="optional-dynamic-group-membership-settings-automatically-add-user-accounts-to-groups-based-on-user-account-attributes"></a>Opcional: As configurações de associação de grupo dinâmicas automaticamente adicionarem contas de usuário a grupos com base nos atributos da conta de usuário

Você deve determinar o conjunto de grupos dinâmicos do Azure AD e usar as instruções no artigo [Associação em grupo dinâmica com base em atributos no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal) para criar os grupos e as regras que determinam o conjunto de atributos de conta de usuário e os grupos e valores de associação em grupos.

Se você ignorar essa opção, a associação em grupos deverá ser feita manualmente conforme novas contas forem adicionadas ou conforme os atributos de contas de usuários mudarem ao longo do tempo. Por exemplo, se alguém passar do departamento de vendas para o departamento de contabilidade, você deverá:

- Atualizar o valor do atributo Departamento dessa conta de usuário.
- Remover o usuário manualmente do grupo Vendas.
- Adicionar o usuário manualmente ao grupo Contabilidade.

Se os grupos Vendas e Contabilidade fossem dinâmicos, você só precisaria alterar o valor Departamento da conta do usuário.

Se necessário, a [Etapa 6](../identity-self-service-group-management.md#identity-dyn-groups) pode ajudá-lo com essa opção.

#### <a name="how-to-test"></a>Como testar

1. Crie um grupo dinâmico de teste no Azure AD com o portal do Azure e configure uma regra para o Departamento igual a "teste1".
2. Crie uma conta de usuário de teste no Azure AD e defina a propriedade Departamento como "teste1".
3. Examine as propriedades da conta do usuário para garantir que ele tenha se tornado membro do grupo dinâmico de teste.
4. Altere o valor da propriedade Departamento da conta de usuário de teste para "teste2".
5. Examine as propriedades da conta do usuário para garantir que ele não seja mais membro do grupo dinâmico de teste.
6. Exclua o grupo dinâmico de teste e a conta de usuário de teste.

<a name="crit-identity-group-license"></a>
### <a name="optional-group-based-licensing-to-automatically-assign-and-remove-licenses-to-user-accounts-based-on-group-membership"></a>Opcional: licenciamento baseado em grupo para automaticamente atribuir e remover licenças a contas de usuário de acordo com sua associação em grupos

Você [habilitou o licenciamento baseado em grupos](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal) para os grupos de segurança apropriados do Azure AD para que as licenças do Microsoft Office 365 Enterprise sejam atribuídas ou tenham a atribuição cancelada automaticamente.

Se você ignorar essa opção, será preciso realizar as seguintes tarefas manualmente:

- Atribuir licenças a novos usuários para os quais você pretende conceder acesso.
- Cancelar a atribuição de licenças de usuários que não estejam mais trabalhando com sua organização ou que não tenham acesso.

Se necessário, a [Etapa 6](../identity-self-service-group-management.md#identity-group-license) pode ajudá-lo com essa opção.

#### <a name="how-to-test"></a>Como testar

1. Crie um grupo de segurança de teste no Azure AD com o portal do Azure e configure o licenciamento baseado em grupo para atribuir licenças do Microsoft 265 Enterprise.
2. Crie uma conta de usuário de teste no Azure AD e adicione-a ao grupo de segurança de teste.
3. Examine as propriedades da conta de usuário no centro de administração do Microsoft 365 para garantir que a licença do Microsoft 265 Enterprise tenha sido atribuída a ela.
4. Remova a conta de usuário de teste do grupo de segurança de teste.
5. Examine as propriedades da conta de usuário para garantir que a licença do Microsoft 265 Enterprise não esteja mais atribuída a ela.
6. Exclua o grupo de segurança de teste e a conta de usuário de teste.

<a name="crit-identity-access-reviews"></a>
### <a name="optional-access-reviews-configured-and-being-used-to-monitor-access"></a>Opcional: revisões de acesso configuradas e usadas para monitorar o acesso

Você usou esses artigos para configurar diferentes tipos de revisões de acesso para monitorar associações a grupos, acesso a aplicativos corporativos e atribuições de funções:

- [Grupos e aplicativos](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [Funções do Azure AD](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [Funções de recurso do Azure](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

Se necessário, a [Etapa 7](../identity-governance.md#identity-access-reviews) pode ajudar você com essa opção.
