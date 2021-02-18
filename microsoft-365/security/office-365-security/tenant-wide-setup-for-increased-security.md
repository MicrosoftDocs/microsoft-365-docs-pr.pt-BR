---
title: Configurar seu locatário do Microsoft 365 para aumentar a segurança
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
description: Este tópico o orienta na configuração recomendada para configurações em todo o locatário que afetam a segurança do seu ambiente do Microsoft 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6eff529a4ab2271df30579af227fe0c28691ae58
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286340"
---
# <a name="configure-your-microsoft-365-tenant-for-increased-security"></a>Configurar seu locatário do Microsoft 365 para aumentar a segurança

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Este tópico o orienta na configuração recomendada para configurações em todo o locatário que afetam a segurança do seu ambiente do Microsoft 365. Suas necessidades de segurança podem exigir mais ou menos segurança. Use essas recomendações como ponto de partida.

## <a name="check-office-365-secure-score"></a>Verificar a Classificação de Segurança do Office 365

O Office 365 Secure Score analisa a segurança da sua organização com base em suas atividades regulares e configurações de segurança e atribui uma pontuação. Comece anotando sua pontuação atual. Ajustar algumas configurações de todo o locatário aumentará sua pontuação. O objetivo não é atingir a pontuação máxima, mas estar ciente das oportunidades para proteger seu ambiente que não afetam negativamente a produtividade dos usuários. Confira [o Microsoft Secure Score.](../mtp/microsoft-secure-score.md)

## <a name="tune-threat-management-policies-in-the-microsoft-365-security-center"></a>Ajustar políticas de gerenciamento de ameaças no centro de segurança do Microsoft 365

A central de segurança do Microsoft 365 inclui recursos que protegem seu ambiente. Ele também inclui relatórios e painéis que você pode usar para monitorar e tomar medidas. Algumas áreas vêm com configurações de política padrão. Algumas áreas não incluem políticas ou regras padrão. Visite essas políticas sob gerenciamento de ameaças para ajustar as configurações de gerenciamento de ameaças para um ambiente mais seguro.

****

|Área|Inclui uma política padrão|Recomendação|
|---|---|---|
|**Anti-phishing**|Sim|Se você tiver um domínio personalizado, configure a política anti-phishing padrão para proteger as contas de email de seus usuários mais importantes, como seu CEO, e para proteger seu domínio. <p> Revise as políticas [anti-phishing no Office 365](set-up-anti-phishing-policies.md) e confira Configurar políticas [anti-phishing](configure-anti-phishing-policies-eop.md) no EOP ou configurar políticas [anti-phishing no Microsoft Defender para Office 365.](configure-atp-anti-phishing-policies.md)|
|**Mecanismo anti-malware**|Sim| Edite a política padrão: <ul><li>Filtro de Tipos de Anexo Comuns: Selecionar Em</li></ul> <p> Você também pode criar políticas personalizadas de filtro de malware e aplicá-las a usuários, grupos ou domínios específicos em sua organização. <p> Mais informações: <ul><li>[Proteção antimalware](anti-malware-protection.md)</li><li>[Configurar políticas antimalware](configure-anti-malware-policies.md)</li></ul>|
|**Anexos seguros no Microsoft Defender para Office 365**|Não|Na página principal para Anexos Seguros, clique em **Configurações Globais** e a ligue esta configuração: <ul><li>**Ativar o Defender para Office 365, para SharePoint, OneDrive e Microsoft Teams.**</li></ul> <p> Crie uma política de Anexos Seguros com estas configurações: <ul><li> **Bloquear:** selecione **Bloquear** como a resposta de malware desconhecida.</li><li>**Habilitar redirecionamento:** marque essa caixa e insira um endereço de email, como uma conta de administrador ou de quarentena.</li><li>**Aplique a seleção acima se a verificação de anexos** de malware e o erro ocorrer: marque esta caixa.</li><li>**_Aplicado a:_* **o domínio do destinatário é** selecionar seu \> domínio.</li></ul> <p> Mais informações: [Anexos seguros para o SharePoint, OneDrive e Microsoft Teams](atp-for-spo-odb-and-teams.md) e [configurar políticas de Anexos Seguros](set-up-atp-safe-attachments-policies.md)|
|**Links seguros no Microsoft Defender para Office 365**|Sim|Na página principal para Links Seguros, clique em **Configurações globais:** <ul><li>**Use Links seguros em: aplicativos do Office 365:** verifique se essa configuração está conexões.</li><li>**Não rastreia quando os usuários clicam em Links Seguros:** desativar essa configuração para controlar os cliques do usuário.</li></ul> <p> Crie uma política de Links seguros com estas configurações: <ul><li>**Selecione a ação para URLs potencialmente mal-intencionadas desconhecidas em mensagens:** Verifique se essa configuração está **Corretamente.**</li><li>**Selecione a ação para URLs desconhecidas** ou potencialmente mal-intencionadas no Microsoft Teams: verifique se essa configuração está **Corretamente.**</li><li>**Aplique verificação de URL em tempo real para links suspeitos e links que apontem para arquivos:** marque esta caixa.</li><li>**Aguarde a conclusão da verificação de URL antes de entregar a mensagem:** marque esta caixa.</li><li>**Aplicar links seguros a mensagens de email enviadas dentro da organização:** marque esta caixa</li><li>**Não permita que os usuários cliquem na URL original:** marque esta caixa.</li><li>**Aplicado a:** **o domínio do destinatário é** selecionar seu \> domínio.</li></ul> <p> Mais informações: [Configurar políticas de Links seguros.](set-up-atp-safe-links-policies.md)|
|**Anti-Spam (Filtragem de email)**|Sim| O que observar: <ul><li>Muito spam Escolha as configurações personalizadas e edite a política de filtro de spam padrão.</li><li>Inteligência contra spoof — Revise os enviadores que estão fazendo a spoofing do seu domínio. Bloquear ou permitir esses envios.</li></ul> <p> Mais informações: Proteção anti-spam de email do [Microsoft 365.](anti-spam-protection.md)|
|***Autenticação de email***|Sim|A autenticação de email usa um DNS (Sistema de Nomes de Domínio) para adicionar informações verificáveis a mensagens de email sobre o remetente de um email. O Microsoft 365 configura a autenticação de email para seu domínio padrão (onmicrosoft.com), mas os administradores do Microsoft 365 também podem usar a autenticação de email para domínios personalizados. Três métodos de autenticação são usados: <ul><li>Sender Policy Framework (ou SPF).</li><ul><li>Para configurar, confira [Configurar o SPF no Microsoft 365 para ajudar a evitar a spoofing.](set-up-spf-in-office-365-to-help-prevent-spoofing.md)</li></ul> <li>DomainKeys Identified Mail (DKIM).</li><ul><li>Consulte [Usar DKIM para validar emails de saída enviados de seu domínio personalizado.](use-dkim-to-validate-outbound-email.md)</li><li>Depois de configurar o DKIM, habilita-o na central de segurança.</li></ul><li>Autenticação, relatórios e conformidade de mensagens baseadas em domínio (DMARC).</li><ul><li>Para configurar o DMARC, [use o DMARC para validar emails no Microsoft 365.](use-dmarc-to-validate-email.md)</li></ul></ul>|
|

> [!NOTE]
> Para implantações não padrão de SPF, implantações híbridas e solução de problemas: como o Microsoft 365 usa a [Sender Policy Framework (SPF) para evitar a spoofing.](how-office-365-uses-spf-to-prevent-spoofing.md)

## <a name="view-dashboards-and-reports-in-the-security-and-compliance-centers"></a>Exibir painéis e relatórios nos centros de segurança e conformidade

Visite esses relatórios e painéis para saber mais sobre a saúde do seu ambiente. Os dados nesses relatórios se tornarão mais ricos à medida que sua organização usa os serviços do Office 365. Por enquanto, familiarizar-se com o que você pode monitorar e tomar medidas. Para saber mais, confira: Relatórios nos centros de conformidade e segurança [do Microsoft 365.](../../compliance/reports-in-security-and-compliance.md)

****

|Painel|Descrição|
|---|---|
|[Painel de gerenciamento de ameaças](security-dashboard.md)|Na  seção Gerenciamento de ameaças do centro de segurança, use esse painel para ver as ameaças que já foram tratadas e como uma ferramenta útil para relatar aos tomadores de decisão de negócios sobre quais recursos de investigação e resposta de ameaças já foram feitos para proteger seus negócios.|
|[Explorador de Ameaças (ou detecções em tempo real)](threat-explorer.md)|Isso também está na seção **Gerenciamento de** ameaças da central de segurança. Se você estiver investigando ou enfrentando um ataque contra seu locatário, use o Explorer (ou detecções em tempo real) para analisar ameaças. O Explorer (e o relatório de detecções em tempo real) mostra o volume de ataques ao longo do tempo e você pode analisar esses dados por famílias de ameaças, infraestrutura de invasores e muito mais. Você também pode marcar qualquer email suspeito para a lista de incidentes.|
|Relatórios — Painel|Na seção **Relatórios da** central de segurança, veja relatórios de auditoria para suas organizações do SharePoint Online e do Exchange Online. Você também pode acessar relatórios de entrada do usuário do Azure Active Directory (Azure AD), relatórios de atividades do usuário e o log de auditoria do Azure AD na página Exibir **relatórios.**|
|

![Painel do Centro de Segurança](../../media/870ab776-36d2-49c7-b615-93b2bc42fce5.png)

## <a name="configure-additional-exchange-online-tenant-wide-settings"></a>Definir configurações adicionais para todo o locatário do Exchange Online

Muitos dos controles de segurança e proteção no Centro de administração do Exchange também estão incluídos no centro de segurança. Você não precisa configurá-los em ambos os lugares. Aqui estão algumas configurações adicionais recomendadas.

****

|Área|Inclui uma política padrão|Recomendação|
|---|---|---|
|**Fluxo de Emails** (regras de fluxo de emails, também conhecidas como regras de transporte)|Não|Adicione uma regra de fluxo de emails para ajudar a proteger contra ransomware bloqueando tipos de arquivo executáveis e tipos de arquivo do Office que contenham macros. Para obter mais informações, [consulte Usar regras de fluxo de emails para inspecionar anexos de mensagens no Exchange Online.](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments) <p> Consulte estes tópicos adicionais: <ul><li>[Proteção contra ransomware](../../admin/security-and-compliance/secure-your-business-data.md#5-protect-against-ransomware)</li><li>[Proteção contra malware e ransomware no Microsoft 365](https://docs.microsoft.com/compliance/assurance/assurance-malware-and-ransomware-protection)</li><li>[Recuperar-se de um ataque de ransomware no Office 365](recover-from-ransomware.md)</li></ul> <p> Crie uma regra de fluxo de emails para evitar o encaminhamento automático de emails para domínios externos. Para obter mais informações, consulte [Mitigando regras de encaminhamento externo do cliente com a Classificação de Segurança.](https://docs.microsoft.com/archive/blogs/office365security/mitigating-client-external-forwarding-rules-with-secure-score) <p> Mais informações: Regras [de fluxo de emails (regras de transporte) no Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)|
|**Habilitar a autenticação moderna**|Não|A autenticação moderna é um pré-requisito para usar a MFA (autenticação multifatória). A MFA é recomendada para proteger o acesso a recursos de nuvem, incluindo email. <p> Consulte estes tópicos: <ul><li>[Habilitar ou desabilitar autenticação básica no Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online)</li><li>[Skype for Business Online: habilitar seu locatário para autenticação moderna](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)</li></ul> <p> A autenticação moderna é habilitada por padrão para clientes do Office 2016, SharePoint Online e OneDrive for Business. <p> Mais informações: como a autenticação moderna funciona para aplicativos clientes do [Office 2013 e do Office 2016](../../enterprise/modern-auth-for-office-2013-and-2016.md)|
|

## <a name="configure-tenant-wide-sharing-policies-in-sharepoint-admin-center"></a>Configurar políticas de compartilhamento em todo o locatário no Centro de administração do SharePoint

Recomendações da Microsoft para configurar sites de equipe do SharePoint em níveis crescentes de proteção, começando com a proteção de linha de base. Para saber mais, confira Recomendações de política para proteger arquivos e [sites do SharePoint.](sharepoint-file-access-policies.md)

Os sites de equipe do SharePoint configurados no nível da linha de base permitem o compartilhamento de arquivos com usuários externos usando links de acesso anônimo. Essa abordagem é recomendada em vez de enviar arquivos por email.

Para dar suporte às metas de proteção de linha de base, configure as políticas de compartilhamento em todo o locatário conforme recomendado aqui. As configurações de compartilhamento para sites individuais podem ser mais restritivas do que essa política de todos os locatários, mas não mais permissivas.

****

|Área|Inclui uma política padrão|Recomendação|
|---|---|---|
|**Compartilhamento** (SharePoint Online e OneDrive for Business)|Sim|O compartilhamento externo é habilitado por padrão. Estas configurações são recomendadas: <ul><li>Permitir o compartilhamento com usuários externos autenticados e o uso de links de acesso anônimo (configuração padrão).</li><li>Os links de acesso anônimo expiram neste número de dias. Insira um número, se desejado, como 30 dias.</li><li>Tipo de link padrão — selecione Interno (somente pessoas da organização). Os usuários que desejam compartilhar usando links anônimos devem escolher essa opção no menu de compartilhamento.</li></ul> <p> Mais informações: Visão [geral do compartilhamento externo](https://docs.microsoft.com/sharepoint/external-sharing-overview)|
|

O Centro de administração do SharePoint e o Centro de administração do OneDrive for Business incluem as mesmas configurações. As configurações em qualquer centro de administração se aplicam a ambos.

## <a name="configure-settings-in-azure-active-directory"></a>Definir configurações no Azure Active Directory

Certifique-se de visitar essas duas áreas no Azure Active Directory para concluir a configuração de todos os locatários para ambientes mais seguros.

### <a name="configure-named-locations-under-conditional-access"></a>Configurar locais nomeados (sob acesso condicional)

Se sua organização incluir escritórios com acesso seguro à rede, adicione os intervalos de endereços IP confiáveis ao Azure Active Directory como locais nomeados. Esse recurso ajuda a reduzir o número de falsos positivos relatados para eventos de risco de login.

Confira: [Locais nomeados no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-named-locations)

### <a name="block-apps-that-dont-support-modern-authentication"></a>Bloquear aplicativos que não suportam autenticação moderna

A autenticação multifa factor requer aplicativos que suportam a autenticação moderna. Aplicativos que não suportam autenticação moderna não podem ser bloqueados usando regras de acesso condicional.

Para ambientes seguros, certifique-se de desabilitar a autenticação para aplicativos que não suportam autenticação moderna. Você pode fazer isso no Azure Active Directory com um controle que estará disponível em breve.

In the meantime, use one of the following methods to accomplish this for SharePoint Online and OneDrive for Business:

- Use o PowerShell, confira [Bloquear aplicativos que não usam autenticação moderna (ADAL).](https://docs.microsoft.com/mem/intune/protect/app-modern-authentication-block)

- Configure isso no Centro de administração do SharePoint na página "acesso ao dispositivo" — "Controlar o acesso de aplicativos que não usam autenticação moderna". Escolha Bloquear.

## <a name="get-started-with-cloud-app-security-or-office-365-cloud-app-security"></a>Começar a trabalhar com o Cloud App Security ou o Office 365 Cloud App Security

Use o Office 365 Cloud App Security para avaliar o risco, alertar sobre atividades suspeitas e agir automaticamente. Requer o plano Office 365 E5.

Ou use o Microsoft Cloud App Security para obter uma visibilidade mais profunda mesmo depois que o acesso for concedido, controles abrangentes e proteção aprimorada para todos os seus aplicativos de nuvem, incluindo o Office 365.

Como essa solução recomenda o plano EMS E5, recomendamos começar com o Cloud App Security para que você possa usá-lo com outros aplicativos SaaS em seu ambiente. Comece com políticas e configurações padrão.

Mais informações:

- [Implantar o Cloud App Security](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security)

- [Mais informações sobre o Microsoft Cloud App Security](https://www.microsoft.com/cloud-platform/cloud-app-security)

- [O que é o Cloud App Security?](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)

![Painel do Cloud App Security](../../media/1fb2aa65-54b8-4746-9f5e-c187d339e9f5.png)

## <a name="additional-resources"></a>Recursos adicionais

Estes artigos e guias fornecem informações prescritivas adicionais para proteger seu ambiente do Microsoft 365:

- Diretrizes de segurança da Microsoft para [campanhas políticas,](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md) instituições sem fins lucrativos e outras organizações ágeis (você pode usar essas recomendações em qualquer ambiente, especialmente em ambientes somente na nuvem)

- [Políticas e configurações de segurança recomendadas para identidades e](microsoft-365-policies-configurations.md) dispositivos (essas recomendações incluem ajuda para ambientes do AD FS)
