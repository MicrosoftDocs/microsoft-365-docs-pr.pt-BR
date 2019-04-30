<a name="crit-infoprotect-step1"></a>
### <a name="required-security-and-information-protection-levels-for-your-organization-are-defined"></a>Obrigatório: os níveis de segurança e proteção de informações foram definidos em para a sua organização

Você planejou e determinou os níveis de segurança necessários para a sua organização. Esses níveis definem o patamar mínimo de segurança e outros níveis para informações cuja confidencialidade aumenta gradualmente, assim como a segurança de dados exigida para cada uma delas.

No mínimo, você está usando três níveis de segurança:

- Linha de base
- Confidencial
- Altamente controlada

Se necessário, a [Etapa 1](../infoprotect-define-sec-infoprotect-levels.md) pode ajudá-lo a atender a esse requisito. 

<a name="crit-infoprotect-step3"></a>
### <a name="required-increased-security-for-microsoft-365-is-configured"></a>Obrigatório: configuração de segurança aprimorada para Microsoft 365 

As seguintes configurações foram habilitadas para a [segurança aprimorada do Office 365](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security):

- Políticas de gerenciamento de ameaças na Central de segurança do Microsoft 365
- Configurações adicionais para todos os locatários do Exchange Online
- Políticas de compartilhamento de todos os locatários no centro de administração do SharePoint Online
- Configurações do Azure Active Directory (Azure AD)

Você também [habilitou a Proteção Avançada contra Ameaças (ATP) do Office 365 para SharePoint, OneDrive e Microsoft Teams](https://docs.microsoft.com/office365/securitycompliance/turn-on-atp-for-spo-odb-and-teams).

Se necessário, a [Etapa 3](../infoprotect-configure-increased-security-office-365.md) pode ajudá-lo a atender a esse requisito. 

<a name="crit-infoprotect-step2"></a>
### <a name="optional-classification-is-configured-across-your-environment"></a>Opcional: a classificação está configurada em seu ambiente

Você trabalhou com o seu departamento jurídico e de conformidade para desenvolver uma classificação apropriada e um esquema de identificação de governança de dados e políticas de segurança para a sua organização. 

Essa políticas correspondem a configuração e implantação de:

- Tipos de dados confidenciais
- Rótulos de retenção
- Rótulos de confidencialidade
- Rótulos da Proteção de Informações do Azure

Se necessário, a [Etapa 2](../infoprotect-configure-classification.md) pode ajudá-lo a atender a esse requisito. 


<a name="crit-infoprotect-step4"></a>
### <a name="optional-windows-information-protection-is-deployed-across-your-environment"></a>Opcional: Proteção de Informações do Windows implementada em todo o seu ambiente

Seus dispositivos Windows 10 Enterprise registrados têm uma política do Intune implementada e aplicada que define:

- Quais apps para proteger.
- O nível de proteção.
- Onde a proteção se estende.

Se necessário, a [Etapa 4](../infoprotect-deploy-windows-information-protection.md) pode ajudá-lo a atender a esse requisito. 

<a name="crit-infoprotect-step5"></a>
### <a name="optional-office-365-data-loss-prevention-dlp-is-deployed"></a>Opcional: o DLP (Data Loss Prevention) do Office 365 está implantado

Você analisou, testou e depois lançou o conjunto de políticas de DLP - com locais e regras com condições e ações - que sua organização exige para proteger os clientes e outros tipos de dados privados e aderir aos regulamentos e requisitos do setor e regionais.

Sua equipe de conformidade e segurança de dados está usando o Office 365 Security & amp; Painel de conformidade para monitorar incidentes de DLP.

Se necessário, a [Etapa 5](../infoprotect-data-loss-prevention.md) pode ajudá-lo a atender a esse requisito. 


<a name="crit-infoprotect-step6"></a>
### <a name="optional-configure-privileged-access-management-in-office-365"></a>Opcional: configurar o gerenciamento de acesso privilegiado no Office 365

Você usou as informações do tópico [Configurar gerenciamento de acesso privilegiado do Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) para habilitar uma ou mais políticas de acesso privilegiado em sua organização. Você configurou essas políticas e o acesso just-in-time está habilitado para acessar dados confidenciais ou configurações críticas.

Se necessária, a [Etapa 6](../infoprotect-configure-privileged-access-management.md) pode ajudá-lo a atender a esse requisito. 
