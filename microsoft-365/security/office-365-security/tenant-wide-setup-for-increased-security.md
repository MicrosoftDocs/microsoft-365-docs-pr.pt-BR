---
title: Configure seu Microsoft 365 locatário para maior segurança
f1.keywords:
- NOCSH
ms.author: bcarter
author: BrendaCarter
manager: laurawi
ms.date: 10/11/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_IP
- M365-security-compliance
search.appverid: MET150
ms.assetid: 8d274fe3-db51-4107-ba64-865e7155b355
ms.custom:
- seo-marvel-apr2020
description: Este tópico o orienta através da configuração recomendada para definições de todos os locatários que afetam a segurança do seu ambiente Microsoft 365.
ms.openlocfilehash: cc1f69663badaa7ae6590bb1d389cb15f13da79d
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357534"
---
# <a name="configure-your-microsoft-365-tenant-for-increased-security"></a>Configure seu Microsoft 365 locatário para maior segurança

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Este tópico o orienta através da configuração recomendada para definições de todos os locatários que afetam a segurança do seu ambiente Microsoft 365. Suas necessidades de segurança podem exigir mais ou menos segurança. Use estas recomendações como ponto de partida.

## <a name="check-office-365-secure-score"></a>Verificar a pontuação segura do Office 365

A pontuação segura do Office 365 analisa a segurança da sua organização com base em suas atividades regulares e configurações de segurança e atribui uma pontuação. Comece anotando sua pontuação atual. O ajuste de algumas configurações de todos os locatários aumentará a sua pontuação. O objetivo não é atingir a pontuação máxima, mas para estar ciente das oportunidades de proteger seu ambiente que não afete negativamente a produtividade dos seus usuários. Confira a [Pontuação segura da Microsoft](../mtp/microsoft-secure-score.md).

## <a name="tune-threat-management-policies-in-the-microsoft-365-security-center"></a>Ajustar as políticas de gerenciamento de ameaças no centro de segurança do Microsoft 365

O centro de segurança do Microsoft 365 inclui recursos que protegem o seu ambiente. Também inclui relatórios e painéis que você pode usar para monitorar e tomar medidas. Algumas áreas vêm com as configurações de política padrão. Algumas áreas não incluem políticas ou regras padrão. Visite estas políticas em gerenciamento de ameaças para ajustar as configurações de gerenciamento de ameaças para um ambiente mais seguro.

****

|Área|Inclui uma política padrão|Recomendação|
|---|---|---|
|**Anti-phishing**|Sim|Se você tiver um domínio personalizado, configure a política anti-phishing padrão para proteger as contas de email de seus usuários mais valiosos, como seu CEO, e para proteger seu domínio. <p> Revisar [políticas anti-phishing no Office 365](set-up-anti-phishing-policies.md) e consulte [Configure anti-phishing Policies in EOP](configure-anti-phishing-policies-eop.md) ou [Configure anti-phishing Policies in Microsoft defender for Office 365](configure-atp-anti-phishing-policies.md).|
|**Mecanismo Antimalware**|Sim| Edite a política padrão: <ul><li>Filtro de tipos de anexo comuns: selecionar ativado</li></ul> <p> Você também pode criar políticas de filtro de malware personalizadas e aplicá-las a usuários, grupos ou domínios especificados em sua organização. <p> Mais informações: <ul><li>[Proteção antimalware](anti-malware-protection.md)</li><li>[Configurar políticas antimalware](configure-anti-malware-policies.md)</li></ul>|
|**Anexos seguros no Microsoft defender para Office 365**|Não|Na página principal de anexos seguros, clique em **configurações globais** e ative esta configuração: <ul><li>**Ativar a ATP para SharePoint, OneDrive e Microsoft Teams**</li></ul> <p> Crie uma política de anexos seguros com estas configurações: <ul><li> **Bloquear**: selecione **Bloquear** como resposta de malware desconhecido.</li><li>**Habilitar redirecionamento**: Marque essa caixa e insira um endereço de email, como uma conta de administrador ou de quarentena.</li><li>**Aplique a seleção acima se a verificação de malware por anexos expirar ou se ocorrer erro**: Marque essa caixa.</li><li>**_Aplicado a_*: **o domínio do destinatário é** \> selecionar seu domínio.</li></ul> <p> Mais informações: [ATP para SharePoint, onedrive e Microsoft Teams](atp-for-spo-odb-and-teams.md) e [configurar as políticas de anexos seguros](set-up-atp-safe-attachments-policies.md)|
|**Links seguros no Microsoft defender para Office 365**|Sim|Na página principal de links seguros, clique em **configurações globais**: <ul><li>**Usar links seguros no: aplicativos do Office 365**: Verifique se essa configuração está ativada.</li><li>**Não rastrear quando os usuários clicarem em links seguros**: desativar essa configuração para controlar cliques do usuário.</li></ul> <p> Crie uma política de links seguros com estas configurações: <ul><li>**Selecione a ação para URLs possivelmente mal-intencionadas desconhecidas nas mensagens**: Verifique se essa configuração está **ativada**.</li><li>**Selecione a ação para URLs desconhecidas ou potencialmente mal-intencionadas no Microsoft Teams**: Verifique se esta configuração está **ativada**.</li><li>**Aplicar verificação de URL em tempo real para links suspeitos e links que apontam para arquivos**: Marque essa caixa.</li><li>**Aguarde a conclusão da verificação de URL antes de entregar a mensagem**: Marque essa caixa.</li><li>**Aplicar links seguros a mensagens de email enviadas dentro da organização**: Marque esta caixa</li><li>**Não permitir que os usuários cliquem na URL original**: Marque essa caixa.</li><li>**Aplicado a**: **o domínio do destinatário é** \> selecionar seu domínio.</li></ul> <p> Mais informações: [Configurar políticas de links seguros](set-up-atp-safe-links-policies.md).|
|**Anti-spam (filtragem de email)**|Sim| O que observar: <ul><li>Excesso de spam — escolha as configurações personalizadas e edite a política de filtro de spam padrão.</li><li>Spoof Intelligence – revise os remetentes que estão falsificando seu domínio. Bloquear ou permitir estes remetentes.</li></ul> <p> Mais informações: [Microsoft 365 email anti-spam Protection](anti-spam-protection.md).|
|**_Autenticação de email_* _|Sim|A autenticação de email usa um DNS (sistema de nomes de domínio) para adicionar informações verificáveis a mensagens de email sobre o remetente de um email. O Microsoft 365 configura a autenticação de email para seu domínio padrão (onmicrosoft.com), mas os administradores do Microsoft 365 também podem usar a autenticação de email para domínios personalizados. Três métodos de autenticação são usados: <ul><li>Estrutura de política de remetente (ou SPF).</li><ul><li>Para a instalação, consulte [Configurar o SPF no Microsoft 365 para ajudar a evitar a falsificação](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</li></ul> <li>DomainKeys identificadas por email (DKIM).</li><ul><li>Confira [usar DKIM para validar emails de saída enviados do seu domínio personalizado](use-dkim-to-validate-outbound-email.md).</li><li>Depois de configurar o DKIM, habilite-o na central de segurança.</li></ul><li>Autenticação, geração de relatórios e conformidade de mensagens baseadas em domínio (DMARC).</li><ul><li>Para a configuração do DMARC, [use o DMARC para validar emails no Microsoft 365](use-dmarc-to-validate-email.md).</li></ul></ul>|
|

> [!NOTE]
> Para implantações não padrão de SPF, implantações híbridas e solução de problemas: [como a Microsoft 365 usa a estrutura de política de remetente (SPF) para evitar falsificação](how-office-365-uses-spf-to-prevent-spoofing.md).

## <a name="view-dashboards-and-reports-in-the-security-and-compliance-centers"></a>Exibir painéis e relatórios nos centros de segurança e conformidade

Visite esses relatórios e painéis para saber mais sobre a integridade de seu ambiente. Os dados desses relatórios ficarão mais sofisticados, pois sua organização usa os serviços do Office 365. Por enquanto, familiarize-se com o que você pode monitorar e tomar ações. Para obter mais informações, consulte: [relatórios nos centros de segurança e conformidade do Microsoft 365](../../compliance/reports-in-security-and-compliance.md).

_***

|Painel|Descrição|
|---|---|
|[Painel de gerenciamento de ameaças](security-dashboard.md)|Na seção **Gerenciamento de ameaças** da central de segurança, use este painel para ver as ameaças que já foram tratadas e como uma ferramenta útil para relatar os tomadores de decisões de negócios sobre quais recursos de investigação e resposta de ameaças já foram feitos para proteger sua empresa.|
|[Explorador de Ameaças (ou detecções em tempo real)](threat-explorer.md)|Isso também está na seção **Gerenciamento de ameaças** da central de segurança. Se você estiver investigando ou experimentando um ataque contra o locatário, use o Explorer (ou detecções em tempo real) para analisar ameaças. O Explorer (e o relatório de detecções em tempo real) mostra o volume de ataques ao longo do tempo, e você pode analisar esses dados por famílias de ameaças, infraestrutura de atacante e muito mais. Você também pode marcar qualquer email suspeito para a lista de incidentes.|
|Relatórios — painel|Na seção **relatórios** da central de segurança, exiba relatórios de auditoria para as organizações do SharePoint Online e do Exchange Online. Você também pode acessar os relatórios de entrada do usuário do Azure Active Directory (Azure AD), relatórios de atividades do usuário e o log de auditoria do Azure AD na página **exibir relatórios** .|
|

![Painel central de segurança](../../media/870ab776-36d2-49c7-b615-93b2bc42fce5.png)

## <a name="configure-additional-exchange-online-tenant-wide-settings"></a>Definir configurações adicionais para todos os locatários do Exchange Online

Muitos dos controles de segurança e proteção no centro de administração do Exchange também estão incluídos na central de segurança. Não é necessário configurá-los nos dois lugares. Aqui estão algumas configurações adicionais recomendadas.

****

|Área|Inclui uma política padrão|Recomendação|
|---|---|---|
|**Fluxo de emails** (regras de fluxo de emails, também conhecidas como regras de transporte)|Não|Adicione uma regra de fluxo de emails para ajudar a proteger contra o ransomware, bloqueando tipos de arquivos executáveis e tipos de arquivo do Office que contenham macros. Para obter mais informações, consulte [usar regras de fluxo de email para inspecionar anexos de mensagens no Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments). <p> Confira estes tópicos adicionais: <ul><li>[Proteção contra ransomware](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/secure-your-business-data#ransomware)</li><li>[Proteção contra malware e ransomware no Office 365](https://docs.microsoft.com/Office365/Enterprise/office-365-malware-and-ransomware-protection)</li><li>[Recuperar de um ataque de ransomware no Office 365](recover-from-ransomware.md)</li></ul> <p> Crie uma regra de fluxo de emails para impedir o encaminhamento automático de emails para domínios externos. Para obter mais informações, consulte [mitigating Client external Forwarding Rules with Secure Score](https://docs.microsoft.com/archive/blogs/office365security/mitigating-client-external-forwarding-rules-with-secure-score). <p> Mais informações: [regras de fluxo de emails (regras de transporte) no Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)|
|**Habilitar a autenticação moderna**|Não|A autenticação moderna é um pré-requisito para usar a MFA (autenticação multifator). A MFA é recomendada para proteger o acesso a recursos de nuvem, incluindo email. <p> Confira estes tópicos: <ul><li>[Habilitar ou desabilitar autenticação básica no Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online)</li><li>[Skype for Business Online: habilitar seu locatário para autenticação moderna](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)</li></ul> <p> A autenticação moderna está habilitada por padrão para clientes do Office 2016, SharePoint Online e OneDrive for Business. <p> Mais informações: [como a autenticação moderna funciona para os aplicativos cliente do office 2013 e do office 2016](https://docs.microsoft.com/microsoft-365/enterprise/modern-auth-for-office-2013-and-2016)|
|

## <a name="configure-tenant-wide-sharing-policies-in-sharepoint-admin-center"></a>Configurar políticas de compartilhamento em todo o locatário no centro de administração do SharePoint

Recomendações da Microsoft para configuração de sites de equipe do SharePoint em níveis de proteção crescentes, começando com proteção de linha de base. Para obter mais informações, consulte [proteger sites e arquivos do SharePoint Online](https://docs.microsoft.com/microsoft-365-enterprise/secure-sharepoint-online-sites-and-files)

Sites de equipe do SharePoint configurados no nível da linha de base permitem compartilhar arquivos com usuários externos usando links de acesso anônimo. Essa abordagem é recomendada em vez de enviar arquivos no email.

Para dar suporte às metas de proteção de linha de base, configure as políticas de compartilhamento em todo o locatário conforme recomendado aqui. As configurações de compartilhamento para sites individuais podem ser mais restritivas que essa política de todo o locatário, mas não mais permissivas.

****

|Área|Inclui uma política padrão|Recomendação|
|---|---|---|
|**Compartilhamento** (SharePoint Online e onedrive for Business)|Sim|O compartilhamento externo está habilitado por padrão. Estas configurações são recomendadas: <ul><li>Permitir o compartilhamento de usuários externos autenticados e o uso de links de acesso anônimo (configuração padrão).</li><li>Os links de acesso anônimo expiram neste número de dias. Insira um número, se desejado, como 30 dias.</li><li>Tipo de link padrão — selecione interno (somente pessoas na organização). Os usuários que desejam compartilhar usando links anônimos devem escolher essa opção no menu compartilhamento.</li></ul> <p> Mais informações: [visão geral do compartilhamento externo](https://docs.microsoft.com/sharepoint/external-sharing-overview)|
|

O centro de administração do SharePoint e o centro de administração do OneDrive for Business incluem as mesmas configurações. As configurações no centro de administração se aplicam a ambos.

## <a name="configure-settings-in-azure-active-directory"></a>Definir configurações no Azure Active Directory

Certifique-se de visitar essas duas áreas no Azure Active Directory para concluir a configuração em todo o locatário para ambientes mais seguros.

### <a name="configure-named-locations-under-conditional-access"></a>Configurar locais nomeados (sob acesso condicional)

Se sua organização incluir escritórios com acesso seguro à rede, adicione os intervalos de endereços IP confiáveis ao Azure Active Directory como locais nomeados. Este recurso ajuda a reduzir o número de falsos positivos informados para eventos de risco de entrada.

Confira: [locais nomeados no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-named-locations)

### <a name="block-apps-that-dont-support-modern-authentication"></a>Bloquear aplicativos que não dão suporte à autenticação moderna

A autenticação multifator requer aplicativos que dão suporte à autenticação moderna. Os aplicativos que não dão suporte à autenticação moderna não podem ser bloqueados usando regras de acesso condicional.

Para ambientes seguros, não deixe de desabilitar a autenticação para aplicativos que não dão suporte à autenticação moderna. Você pode fazer isso no Azure Active Directory com um controle em breve.

Enquanto isso, use um dos seguintes métodos para fazer isso para o SharePoint Online e o OneDrive for Business:

- Use o PowerShell em [bloquear aplicativos que não usam autenticação moderna (Adal)](https://docs.microsoft.com/mem/intune/protect/app-modern-authentication-block).

- Configure isso no centro de administração do SharePoint na página "acesso ao dispositivo" — "controlar o acesso de aplicativos que não usam autenticação moderna". Escolha bloquear.

## <a name="get-started-with-cloud-app-security-or-office-365-cloud-app-security"></a>Introdução ao Cloud app Security ou ao Office 365 Cloud app Security

Use o Office 365 Cloud app Security para avaliar o risco, para alertar sobre atividades suspeitas e para executar ações automaticamente. Requer plano do Office 365 e5.

Ou use o Microsoft Cloud app Security para obter visibilidade mais profunda, mesmo depois que o acesso é concedido, controles abrangentes e proteção aprimorada para todos os aplicativos de nuvem, incluindo o Office 365.

Como esta solução recomenda o plano do EMS e5, recomendamos que você inicie o Cloud app Security para que possa usá-lo com outros aplicativos SaaS em seu ambiente. Comece com políticas e configurações padrão.

Mais informações:

- [Implantar o Cloud App Security](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security)

- [Mais informações sobre o Microsoft Cloud App Security](https://www.microsoft.com/cloud-platform/cloud-app-security)

- [O que é o Cloud app Security?](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)

![Painel do Cloud App Security](../../media/1fb2aa65-54b8-4746-9f5e-c187d339e9f5.png)

## <a name="additional-resources"></a>Recursos adicionais

Estes artigos e guias fornecem informações prescritivas adicionais para proteger seu ambiente do Microsoft 365:

- [Diretrizes de segurança da Microsoft para campanhas políticas, sem fins lucrativos e outras organizações Agile](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md) (você pode usar essas recomendações em qualquer ambiente, especialmente em ambientes de nuvem)

- [Políticas de segurança e configurações recomendadas para identidades e dispositivos](microsoft-365-policies-configurations.md) (estas recomendações incluem ajuda para ambientes do AD FS)
