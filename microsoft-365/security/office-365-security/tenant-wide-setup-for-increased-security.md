---
title: 'Configure o locatário do Microsoft 365 para aumentar a segurança '
f1.keywords:
- NOCSH
ms.author: bcarter
author: BrendaCarter
manager: laurawi
ms.date: 10/11/2018
audience: ITPro
ms.topic: article
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_IP
- M365-security-compliance
search.appverid: MET150
ms.assetid: 8d274fe3-db51-4107-ba64-865e7155b355
ms.custom:
- seo-marvel-apr2020
description: Este tópico orienta você sobre a configuração recomendada para configurações em todo o locatário que afetam a segurança do seu ambiente Microsoft 365 local.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: fd9d07388386ecc3d5877736e588393cdc38e7bb
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879211"
---
# <a name="configure-your-microsoft-365-tenant-for-increased-security"></a>Configure o locatário do Microsoft 365 para aumentar a segurança 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Este tópico orienta você sobre a configuração recomendada para configurações em todo o locatário que afetam a segurança do seu ambiente Microsoft 365 local. Suas necessidades de segurança podem exigir mais ou menos segurança. Use essas recomendações como ponto de partida.

## <a name="check-office-365-secure-score"></a>Verificar Office 365 Pontuação Segura

Office 365 A Pontuação Segura analisa a segurança da sua organização com base em suas atividades regulares e configurações de segurança e atribui uma pontuação. Comece anotando sua pontuação atual. Ajustar algumas configurações de todo o locatário aumentará sua pontuação. O objetivo não é atingir a pontuação máxima, mas estar ciente das oportunidades de proteger seu ambiente que não afetam negativamente a produtividade de seus usuários. Consulte [Microsoft Secure Score](../defender/microsoft-secure-score.md).

## <a name="tune-threat-management-policies-in-the-microsoft-365-defender-portal"></a>Ajustar políticas de gerenciamento de ameaças no portal Microsoft 365 Defender

O Microsoft 365 do Defender inclui recursos que protegem seu ambiente. Ele também inclui relatórios e painéis que você pode usar para monitorar e tomar medidas. Algumas áreas vêm com configurações de política padrão. Algumas áreas não incluem políticas ou regras padrão. Visite essas políticas em gerenciamento de ameaças para ajustar as configurações de gerenciamento de ameaças para um ambiente mais seguro.

<br>

****

|Área|Inclui uma política padrão|Recomendação|
|---|---|---|
|**Anti-phishing**|Sim|<ul><li>Proteção contra representação — se você tiver o Defender para Office 365 e um domínio personalizado, configure as configurações de proteção de representação na política anti-phishing padrão para proteger as contas de email de seus usuários mais valiosos, como seu CEO, e proteger seu domínio. Mais informações: [configurações de representação em políticas anti-phishing](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) e [visão de representação](impersonation-insight.md)</li><li>Inteligência de spoof — Revise os envios que estão spoofando seu domínio. Bloqueie ou permita esses envios. Mais informações: [Spoof intelligence insight in EOP](learn-about-spoof-intelligence.md) and [Manage the Tenant Allow/Block List](tenant-allow-block-list.md).</li></ul>|
|**Mecanismo anti-malware**|Sim|Edite a política padrão: <ul><li>Selecione **Habilitar o filtro de anexos comuns**</li></ul> <p> Você também pode criar políticas de filtro de malware personalizadas e aplicá-las a usuários, grupos ou domínios especificados em sua organização. <p> Mais informações: <ul><li>[Proteção antimalware](anti-malware-protection.md)</li><li>[Configurar políticas antimalware](configure-anti-malware-policies.md)</li></ul>|
|**Cofre Anexos no Microsoft Defender para Office 365**|Não|Na página principal para Cofre anexos, clique em **Configurações globais** e a opção Ativar esta configuração: <ul><li>**Ativar o Defender para Office 365, para SharePoint, OneDrive e Microsoft Teams.**</li></ul> <p> Crie uma Cofre de anexos com estas configurações: <ul><li> **Bloquear**: Selecione **Bloquear** como a resposta de malware desconhecida.</li><li>**Habilitar redirecionamento**: marque essa caixa e insira um endereço de email, como uma conta de administrador ou quarentena.</li><li>**Aplique a seleção acima se a verificação de malware** para anexos for o tempo de saída ou se ocorrer um erro : Marque esta caixa.</li><li>**_Aplicado a_*: **O domínio do destinatário é** selecionar seu \> domínio.</li></ul> <p> Mais informações: Cofre anexos para [SharePoint, OneDrive e Microsoft Teams](mdo-for-spo-odb-and-teams.md) e Configurar políticas de Cofre [Anexos](set-up-safe-attachments-policies.md)|
|**Cofre Links no Microsoft Defender para Office 365**|Sim|Na página principal para Cofre Links, clique em **Configurações globais**: <ul><li>**Use Cofre Links em: Office 365 aplicativos**: Verifique se essa configuração está conexões.</li><li>**Não rastreia quando os usuários clicam Cofre Links**: Desativar essa configuração para controlar os cliques do usuário.</li></ul> <p> Crie uma Cofre de links com estas configurações: <ul><li>**Selecione a ação para URLs mal-intencionadas desconhecidas em mensagens**: Verifique se essa configuração está **em**.</li><li>**Selecione a ação para URLs desconhecidas** ou potencialmente mal-intencionadas Microsoft Teams : Verifique se essa configuração está **em**.</li><li>**Aplicar verificação de URL** em tempo real para links suspeitos e links que apontam para arquivos : Marque esta caixa.</li><li>**Aguarde a conclusão da verificação de URL antes de entregar a mensagem**: Marque esta caixa.</li><li>**Aplicar Cofre links para mensagens de email enviadas dentro da organização**: Marque esta caixa</li><li>**Não permita que os usuários cliquem na URL original**: Marque esta caixa.</li><li>**Aplicado a**: **O domínio do destinatário é** selecionar seu \> domínio.</li></ul> <p> Mais informações: [Configurar políticas Cofre Links.](set-up-safe-links-policies.md)|
|**Anti-Spam (Filtragem de email)**|Sim| O que assistir: spam em de mais — Escolha as configurações personalizadas e edite a política de filtro de spam padrão. Mais informações: Microsoft 365 [Email Anti-Spam Protection](anti-spam-protection.md).|
|***Autenticação de Email***|Sim|A autenticação de email usa um DNS (Sistema de Nomes de Domínio) para adicionar informações verificáveis a mensagens de email sobre o remetente de um email. Microsoft 365 configura a autenticação de email para seu domínio padrão (onmicrosoft.com), mas Microsoft 365 administradores também podem usar a autenticação de email para domínios personalizados. Três métodos de autenticação são usados: <ul><li>Estrutura de Política de Remetente (ou SPF).</li><ul><li>Para configurar, consulte [Configurar o SPF no Microsoft 365 para ajudar a evitar a spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</li></ul> <li>DomainKeys Identified Mail (DKIM).</li><ul><li>Consulte [Usar DKIM para validar emails de saída enviados do seu domínio personalizado.](use-dkim-to-validate-outbound-email.md)</li><li>Depois de configurar o DKIM, habilita-o no portal Microsoft 365 Defender.</li></ul><li>Autenticação, Relatório e Conformidade (DMARC) baseado em domínio.</li><ul><li>Para configuração DMARC [Use DMARC para validar emails em Microsoft 365](use-dmarc-to-validate-email.md).</li></ul></ul>|
|

> [!NOTE]
> Para implantações não padrão de SPF, implantações híbridas e solução de problemas: como o Microsoft 365 usa a Estrutura de Política do Remetente (SPF) para impedir a [spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).

## <a name="view-dashboards-and-reports-in-the-security--compliance-center"></a>Exibir painéis e relatórios no Centro de Conformidade & Segurança

Visite esses relatórios e painéis para saber mais sobre a saúde do seu ambiente. Os dados nesses relatórios se tornarão mais ricos à medida que sua organização usa Office 365 serviços. Por enquanto, conheça o que você pode monitorar e tomar medidas. Para obter mais informações, consulte [Reports in the Security & Compliance Center](../../compliance/reports-in-security-and-compliance.md).

<br>

****

|Painel|Descrição|
|---|---|
|[Painel de gerenciamento de ameaças](security-dashboard.md)|Na  seção Gerenciamento de ameaças do portal do Microsoft 365 Defender, use este painel para ver as ameaças que já foram manipuladas e como uma ferramenta útil para relatar aos tomadores de decisão comerciais sobre quais recursos de investigação e resposta de ameaças já fizeram para proteger sua empresa.|
|[Explorador de Ameaças (ou detecções em tempo real)](threat-explorer.md)|Isso também está na seção **Gerenciamento de ameaças** do portal Microsoft 365 Defender. Se você estiver investigando ou enfrentando um ataque contra seu locatário, use o Explorer (ou detecções em tempo real) para analisar ameaças. O Explorer (e o relatório de detecções em tempo real) mostra o volume de ataques ao longo do tempo e você pode analisar esses dados por famílias de ameaças, infraestrutura de invasores e muito mais. Você também pode marcar qualquer email suspeito para a lista Incidentes.|
|Relatórios — Painel|Na seção **Relatórios** do portal Microsoft 365 Defender, consulte relatórios de auditoria para suas organizações SharePoint Online e Exchange Online. Você também pode acessar Azure Active Directory relatórios de entrada do usuário (Azure AD), relatórios de atividades do usuário e o log de auditoria do Azure AD na página **Exibir relatórios.**|
|

![Microsoft 365 Painel do portal do Defender](../../media/870ab776-36d2-49c7-b615-93b2bc42fce5.png)

## <a name="configure-additional-exchange-online-tenant-wide-settings"></a>Configurar configurações Exchange Online de locatários adicionais

Aqui estão algumas configurações adicionais que são recomendadas.

<br>

****

|Área|Inclui uma política padrão|Recomendação|
|---|---|---|
|**Email Flow** (regras de fluxo de emails, também conhecidas como regras de transporte)|Não|Adicione uma regra de fluxo de emails para ajudar a proteger contra ransomware bloqueando tipos de arquivo executáveis e Office tipos de arquivo que contêm macros. Para obter mais informações, [consulte Use mail flow rules to inspect message attachments in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments). <p> Consulte estes tópicos adicionais: <ul><li>[Proteção contra ransomware](../../admin/security-and-compliance/secure-your-business-data.md#5-protect-against-ransomware)</li><li>[Proteção contra malware e ransomware no Microsoft 365](/compliance/assurance/assurance-malware-and-ransomware-protection)</li><li>[Recuperar de um ataque de ransomware no Office 365](recover-from-ransomware.md)</li></ul> <p> Crie uma regra de fluxo de emails para impedir o encaminhamento automático de emails para domínios externos. Para obter mais informações, consulte Mitigando regras de [encaminhamento externo do cliente com pontuação segura.](/archive/blogs/office365security/mitigating-client-external-forwarding-rules-with-secure-score) <p> Mais informações: [Regras de fluxo de email (regras de transporte) no Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)|
|**Habilitar autenticação moderna**|Não|A autenticação moderna é um pré-requisito para usar a autenticação multifatória (MFA). O MFA é recomendado para proteger o acesso a recursos de nuvem, incluindo email. <p> Consulte estes tópicos: <ul><li>[Habilitar ou desabilitar autenticação básica no Exchange Online](/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online)</li><li>[Skype for Business Online: Habilitar seu locatário para autenticação moderna](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)</li></ul> <p> A autenticação moderna é habilitada por padrão para clientes Office 2016, SharePoint Online e OneDrive for Business. <p> Mais informações: [como a autenticação moderna funciona para Office 2013 e Office aplicativos cliente 2016](../../enterprise/modern-auth-for-office-2013-and-2016.md)|
|

## <a name="configure-tenant-wide-sharing-policies-in-sharepoint-admin-center"></a>Configurar políticas de compartilhamento em todo o locatário no SharePoint de administração

Recomendações da Microsoft para configurar SharePoint de equipe em níveis crescentes de proteção, começando com a proteção de linha de base. Para obter mais informações, consulte [Recomendações de política para](sharepoint-file-access-policies.md)proteger SharePoint sites e arquivos .

SharePoint sites de equipe configurados no nível da linha de base permitem o compartilhamento de arquivos com usuários externos usando links de acesso anônimos. Essa abordagem é recomendada em vez de enviar arquivos por email.

Para dar suporte às metas de proteção de linha de base, configure políticas de compartilhamento em todo o locatário conforme recomendado aqui. As configurações de compartilhamento para sites individuais podem ser mais restritivas do que essa política em todo o locatário, mas não mais permissiva.

<br>

****

|Área|Inclui uma política padrão|Recomendação|
|---|---|---|
|**Compartilhamento** (SharePoint Online e OneDrive for Business)|Sim|O compartilhamento externo está habilitado por padrão. Essas configurações são recomendadas: <ul><li>Permitir compartilhamento para usuários externos autenticados e usar links de acesso anônimo (configuração padrão).</li><li>Os links de acesso anônimo expiram em muitos dias. Insira um número, se desejado, como 30 dias.</li><li>Tipo de link padrão — selecione Interno (somente pessoas na organização). Os usuários que desejam compartilhar usando links anônimos devem escolher essa opção no menu de compartilhamento.</li></ul> <p> Mais informações: [Visão geral do compartilhamento externo](/sharepoint/external-sharing-overview)|
|

SharePoint centro de administração e OneDrive for Business de administração incluem as mesmas configurações. As configurações em qualquer centro de administração se aplicam a ambos.

## <a name="configure-settings-in-azure-active-directory"></a>Configurar configurações em Azure Active Directory

Visite essas duas áreas no Azure Active Directory para concluir a instalação em todo o locatário para ambientes mais seguros.

### <a name="configure-named-locations-under-conditional-access"></a>Configurar locais nomeados (em acesso condicional)

Se sua organização incluir escritórios com acesso seguro à rede, adicione os intervalos de endereços IP confiáveis Azure Active Directory como locais nomeados. Esse recurso ajuda a reduzir o número de falsos positivos relatados para eventos de risco de login.

Consulte: [Locais nomeados no Azure Active Directory](/azure/active-directory/active-directory-named-locations)

### <a name="block-apps-that-dont-support-modern-authentication"></a>Bloquear aplicativos que não suportam autenticação moderna

A autenticação multifafação requer aplicativos que suportam autenticação moderna. Os aplicativos que não suportam autenticação moderna não podem ser bloqueados usando regras de acesso condicional.

Para ambientes seguros, certifique-se de desabilitar a autenticação para aplicativos que não suportam autenticação moderna. Você pode fazer isso em Azure Active Directory com um controle que está chegando em breve.

Enquanto isso, use um dos seguintes métodos para fazer isso para SharePoint Online e OneDrive for Business:

- Use o PowerShell, consulte [Bloquear aplicativos que não usam autenticação moderna (ADAL)](/mem/intune/protect/app-modern-authentication-block).

- Configure isso no centro de administração SharePoint na página "acesso ao dispositivo" — "Controlar o acesso de aplicativos que não usam autenticação moderna". Escolha Bloquear.

## <a name="get-started-with-cloud-app-security-or-office-365-cloud-app-security"></a>Começar a Cloud App Security ou Office 365 Cloud App Security

Use Office 365 Cloud App Security para avaliar o risco, para alertar sobre atividades suspeitas e para tomar medidas automaticamente. Requer Office 365 plano E5.

Ou, use o Microsoft Cloud App Security para obter mais visibilidade mesmo após a concessão do acesso, controles abrangentes e proteção aprimorada para todos os aplicativos de nuvem, incluindo Office 365.

Como essa solução recomenda o plano EMS E5, recomendamos que você comece com o Cloud App Security para que você possa usá-lo com outros aplicativos SaaS em seu ambiente. Comece com políticas e configurações padrão.

Mais informações:

- [Implantar o Cloud App Security](/cloud-app-security/getting-started-with-cloud-app-security)
- [Mais informações sobre o Microsoft Cloud App Security](https://www.microsoft.com/cloud-platform/cloud-app-security)
- [O que é o Cloud App Security?](/cloud-app-security/what-is-cloud-app-security)

![Painel do Cloud App Security](../../media/1fb2aa65-54b8-4746-9f5e-c187d339e9f5.png)

## <a name="additional-resources"></a>Recursos adicionais

Estes artigos e guias fornecem informações prescritivas adicionais para proteger seu Microsoft 365 ambiente:

- Diretrizes de segurança da Microsoft para [campanhas políticas,](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md) organizações sem fins lucrativos e outras organizações ágeis (você pode usar essas recomendações em qualquer ambiente, especialmente em ambientes somente na nuvem)

- [Políticas e configurações de segurança recomendadas para identidades e](microsoft-365-policies-configurations.md) dispositivos (essas recomendações incluem ajuda para ambientes do AD FS)
