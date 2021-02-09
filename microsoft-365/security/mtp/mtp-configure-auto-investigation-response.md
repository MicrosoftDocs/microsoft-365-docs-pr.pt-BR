---
title: Configurar recursos automatizados de investigação e resposta no Microsoft 365 Defender
description: Configurar investigação e resposta automatizadas com auto-recuperação no Microsoft 365 Defender
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.date: 02/08/2021
ms.custom: autoir
ms.reviewer: evaldm, isco
f1.keywords: CSH
ms.technology: m365d
ms.openlocfilehash: 311b5e85055d48fb653c4ca42826f0a92267b00e
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/08/2021
ms.locfileid: "50144979"
---
# <a name="configure-automated-investigation-and-response-capabilities-in-microsoft-365-defender"></a>Configurar recursos automatizados de investigação e resposta no Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

O Microsoft 365 [](mtp-autoir.md) Defender inclui poderosos recursos automatizados de investigação e resposta que podem economizar muito tempo e esforço para sua equipe de operações de segurança. Com [a autorrerecução,](mtp-autoir.md#how-automated-investigation-and-self-healing-works)esses recursos simulam as etapas que um analista de segurança tomaria para investigar e responder a ameaças, apenas mais rápido e com mais capacidade de dimensionar. Este artigo descreve como configurar a investigação e resposta automatizadas no Microsoft 365 Defender.

Para configurar recursos automatizados de investigação e resposta, siga estas etapas:

1. [Revise os pré-requisitos.](#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
2. [Revise ou altere o nível de automação para grupos de dispositivos.](#review-or-change-the-automation-level-for-device-groups)
3. [Revise suas políticas de segurança e alerta no Office 365.](#review-your-security-and-alert-policies-in-office-365)
4. [Certifique-se de que o Microsoft 365 Defender está ligado.](#make-sure-microsoft-365-defender-is-turned-on)

Em seguida, depois de configurar tudo, veja [e gerencie ações na Central de ações.](mtp-autoir-actions.md)

## <a name="prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender"></a>Pré-requisitos para investigação e resposta automatizadas no Microsoft 365 Defender

|Requisito |Detalhes |
|:----|:----|
|Requisitos de assinatura |Uma destas assinaturas: <br/>- Microsoft 365 E5<br/>- Microsoft 365 A5<br/>– Segurança do Microsoft 365 E5<br/>– Segurança do Microsoft 365 A5<br/>– Office 365 E5 mais Enterprise Mobility + Security E5 mais Windows E5<p> Confira os requisitos de licenciamento do [Microsoft 365 Defender.](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites?#licensing-requirements)|
|Requisitos de rede |- [Microsoft Defender for Identity](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) habilitado<br/>- [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) configurado<br/>- [Integração do Microsoft Defender for Identity](https://docs.microsoft.com/cloud-app-security/mdi-integration) |
|Requisitos de máquina do Windows |- Windows 10, versão 1709 ou posterior instalado (Confira[Informações sobre a versão do Windows 10](https://docs.microsoft.com/windows/release-information/)) <br/>- Os seguintes serviços de proteção contra ameaças configurados:<br/>- [Microsoft Defender para Ponto de Extremidade](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)<br/>- [Microsoft Defender Antivírus](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) |
|Proteção para conteúdo de email e arquivos do Office |[Microsoft Defender para Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) configurado |
|Permissões | Para configurar recursos automatizados de investigação e resposta, você deve ter a função administrador global ou administrador de segurança atribuída no Azure Active Directory ( ) ou no centro de administração do [https://portal.azure.com](https://portal.azure.com) Microsoft 365 ( [https://admin.microsoft.com](https://admin.microsoft.com) ).<p>Para obter as permissões necessárias para trabalhar com recursos automatizados de investigação e resposta, como revisão, aprovação ou rejeição de ações [pendentes,](mtp-action-center.md#required-permissions-for-action-center-tasks)consulte Permissões necessárias para tarefas da Central de ações. |

## <a name="review-or-change-the-automation-level-for-device-groups"></a>Revisar ou alterar o nível de automação para grupos de dispositivos

Se as investigações automatizadas são realizadas e se as ações de correção são realizadas automaticamente ou somente mediante aprovação para seus dispositivos dependem de determinadas configurações, como as políticas de grupo de dispositivos da sua organização. Revise o nível de automação definido para as políticas de grupo de dispositivos.

1. Vá para a Central de Segurança do Microsoft Defender ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ) e entre.
2. Vá para **Configurações**  >  **permissões grupos** de  >  **dispositivos**.
3. Revise as políticas de grupo de dispositivos. Em particular, veja a coluna **de nível de correção.** Recomendamos usar **Full - remediar ameaças automaticamente.**  Talvez seja necessário criar ou editar seus grupos de dispositivos para obter o nível de automação que você deseja. Para obter ajuda com essa tarefa, consulte os seguintes artigos:
   - [Como as ameaças são remediadas](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations#how-threats-are-remediated)
   - [Criar e gerenciar grupos de dispositivos](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/machine-groups)

## <a name="review-your-security-and-alert-policies-in-office-365"></a>Revise suas políticas de segurança e alerta no Office 365

A Microsoft fornece políticas de [alerta internas](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) que ajudam a identificar determinados riscos. Esses riscos incluem abuso de permissões de administrador do Exchange, atividade de malware, possíveis ameaças externas e internas e riscos de governança de informações. Alguns alertas podem disparar [investigação e resposta automatizadas no Office 365.](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) Certifique-se [de que seus recursos do Microsoft Defender para Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) estão configurados corretamente.

Embora certos alertas e políticas de segurança possam disparar investigações automatizadas, nenhuma ação de correção é realizada automaticamente para email e conteúdo. Em vez disso, todas as ações de correção para email e conteúdo de email aguardam aprovação da sua equipe de operações de segurança na [Central de ações.](mtp-action-center.md)

As configurações de segurança no Office 365 ajudam a proteger o email e o conteúdo. Para exibir ou alterar essas configurações, siga as orientações em [Proteger contra ameaças.](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)

1. No centro de segurança do Microsoft 365 ( [https://security.microsoft.com](https://security.microsoft.com) ), acesse **Políticas** de Proteção  >  **contra Ameaças**.
2. Certifique-se de que todas as políticas a seguir estão configuradas. Para obter ajuda e recomendações, consulte [Proteger contra ameaças.](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)
   - [Anti-malware (Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-1---anti-malware-protection)
   - [Anti-phishing no Defender para Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-2---anti-phishing-protection)
   - [Anexos seguros (Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#atp-safe-attachments-policies)
   - [Links seguros (Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#atp-safe-links-policies)
   - [Anti-spam (Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-3---anti-spam-protection)
3. [Certifique-se de que o Microsoft Defender para Office 365 para SharePoint, OneDrive](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-5---turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams-workloads) e Microsoft Teams está ligado.
4. Certifique-se [de que a limpeza automática zero hora para proteção](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#zero-hour-auto-purge-for-email-in-eop) de email está em vigor.
5. (Esta etapa é opcional.) Revise suas [políticas de alerta do Office 365](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) no centro de conformidade do Microsoft 365 ( [https://compliance.microsoft.com/compliancepolicies](https://compliance.microsoft.com/compliancepolicies) ). Várias políticas de alerta padrão estão na categoria Gerenciamento de ameaças. Alguns desses alertas podem disparar investigação e resposta automatizadas. Para saber mais, consulte [Políticas de alerta padrão.](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?#default-alert-policies)

## <a name="make-sure-microsoft-365-defender-is-turned-on"></a>Certifique-se de que o Microsoft 365 Defender está ligado

:::image type="content" source="../../media/mtp-enable/mtp-on.png" alt-text="MTP on":::

1. Vá para a central de segurança do Microsoft 365 ( [https://security.microsoft.com](https://security.microsoft.com) ) e entre.
2. No painel de navegação, procure **por Incidentes,** **Central** de Ações e **Busca,** conforme mostrado na imagem anterior.
   - Se você vir **Incidentes,** **Central de Ações** e **Busca,** o Microsoft 365 Defender está ligado. Consulte o procedimento, [Revise ou altere o nível de automação para grupos de dispositivos](#review-or-change-the-automation-level-for-device-groups) (neste artigo).
   - Se você não *vir* **Incidentes,** Central **de** Ações ou **Busca,** o Microsoft 365 Defender pode não estar ligado. Nesse caso, vá para a [Central de Ações.](mtp-action-center.md)
3. No painel de navegação, escolha **Configurações**  >  **do Microsoft 365 Defender.** Confirme se o Microsoft 365 Defender está ligado. 

> [!TIP]
> Precisa de ajuda? Consulte [Ativar o Microsoft 365 Defender.](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable)

## <a name="next-steps"></a>Próximas etapas

- [Ações de correção no Microsoft 365 Defender](mtp-remediation-actions.md)
- [Visite a Central de Ações](mtp-action-center.md)
