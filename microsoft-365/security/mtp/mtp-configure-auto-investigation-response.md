---
title: Configurar os recursos de investigação e resposta automatizados no Microsoft Threat Protection
description: Configurar investigação e resposta automatizadas com auto-recuperação em proteção contra ameaças da Microsoft
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 09/17/2020
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection: M365-security-compliance.
ms.custom: autoir
ms.reviewer: evaldm, isco
f1.keywords: CSH
ms.openlocfilehash: 81ad3ab0d3bc20a49128fa6ed45ff62195b32bc7
ms.sourcegitcommit: 7c0873d2a804f17697844fb13f1a100fabce86c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2020
ms.locfileid: "47963847"
---
# <a name="configure-automated-investigation-and-response-capabilities-in-microsoft-threat-protection"></a>Configurar os recursos de investigação e resposta automatizados no Microsoft Threat Protection

A proteção contra ameaças da Microsoft inclui recursos avançados de [investigação e resposta automatizados](mtp-autoir.md) que podem economizar muito tempo e esforço na equipe de operações de segurança. Com o auto-recuperação, esses recursos imitam as etapas que um analista de segurança tomaria para investigar e responder a ameaças, mais rápido e com mais capacidade de escalabilidade. Este artigo descreve como configurar a investigação e a resposta automatizadas no Microsoft Threat Protection.

Para configurar os recursos de investigação e resposta automatizados, siga estas etapas:

1. [Examine os pré-requisitos](#prerequisites-for-automated-investigation-and-response-in-microsoft-threat-protection).
2. [Revise ou altere o nível de automação para grupos de dispositivos](#review-or-change-the-automation-level-for-device-groups).
3. [Revise suas políticas de segurança e alerta no Office 365](#review-your-security-and-alert-policies-in-office-365).
4. [Verifique se a proteção contra ameaças da Microsoft está ativada](#make-sure-microsoft-threat-protection-is-turned-on).

Depois que você estiver pronto, [revise as ações pendentes e concluídas na central de ações](#review-pending-and-completed-actions-in-the-action-center). 


## <a name="prerequisites-for-automated-investigation-and-response-in-microsoft-threat-protection"></a>Pré-requisitos para investigação e resposta automatizadas no Microsoft Threat Protection

|Requisito |Detalhes |
|--|--|
|Requisitos de assinatura |Uma das assinaturas: <br/>-Microsoft 365 e5 <br/>-Microsoft 365 a5 <br/>– Segurança da Microsoft 365 e5<br/>– Segurança da Microsoft 365 a5<br/>– Office 365 E5 Plus Enterprise Mobility + Security E5 mais Windows e5<br/><br/>Consulte [requisitos de licenciamento do Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites?#licensing-requirements).|
|Requisitos de rede |- [Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) habilitado<br/>- [Segurança do aplicativo do Microsoft Cloud](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) configurada<br/>- [Microsoft Cloud app Security integrado ao Azure ATP](https://docs.microsoft.com/cloud-app-security/aatp-integration) |
|Requisitos de máquina do Windows |– Windows 10, versão 1709 ou posterior instalado (consulte [informações sobre a versão do Windows 10](https://docs.microsoft.com/windows/release-information/)) com os seguintes serviços de proteção contra ameaças configurados:<br/>- [Microsoft defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) <br/>- [Antivírus Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) |
|Proteção para arquivos de conteúdo de email e do Office |[Proteção avançada contra ameaças do Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) configurada |
|Permissões |– Para configurar recursos de investigação e resposta automatizados, você deve ter a função de administrador global ou administrador de segurança atribuída no Azure Active Directory ( [https://portal.azure.com](https://portal.azure.com) ) ou no centro de administração do Microsoft 365 ( [https://admin.microsoft.com](https://admin.microsoft.com) ).<br/><br/>– Para obter as permissões necessárias para trabalhar com os recursos de investigação e resposta automatizados, como revisar, aprovar ou rejeitar ações pendentes, consulte [Required Permissions for Action Center Tasks](mtp-action-center.md#required-permissions-for-action-center-tasks). |

## <a name="review-or-change-the-automation-level-for-device-groups"></a>Revisar ou alterar o nível de automação para grupos de dispositivos

Se as investigações automatizadas são executadas e se as ações de correção são realizadas automaticamente ou apenas na aprovação de seus dispositivos dependem de determinadas configurações, como as políticas de grupo de dispositivos da sua organização. Revise o nível de automação definido para suas políticas de grupo de dispositivos.

### <a name="to-review-or-change-your-device-group-policies"></a>Para revisar ou alterar suas políticas de grupo de dispositivos

1. Vá para o centro de segurança do Microsoft defender ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ) e entre.

2. Vá para **Settings**  >  **Permissions**  >  **grupos de dispositivos**de permissões de configurações. 

3. Revise as políticas de grupo de dispositivos. Em particular, examine a coluna **nível de correção** . Recomendamos usar **automaticamente as ameaças de correção total**.  Talvez seja necessário criar ou editar seus grupos de dispositivos para obter o nível de automação desejado. Para obter ajuda com essa tarefa, consulte os seguintes artigos:

   - [Como as ameaças são corrigidas](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations#how-threats-are-remediated)
   
   - [Criar e gerenciar grupos de dispositivos](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/machine-groups) 

## <a name="review-your-security-and-alert-policies-in-office-365"></a>Revisar suas políticas de segurança e alerta no Office 365

A Microsoft fornece políticas de [alerta](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) internas que ajudam a identificar determinados riscos. Esses riscos incluem abuso de permissões de administração do Exchange, atividade de malware, ameaças externas e internas potenciais e riscos de governança de informações. Alguns alertas podem disparar [investigação e resposta automatizadas no Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air). Certifique-se de que seus recursos [avançados de proteção contra ameaças do Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) estão configurados corretamente.

Embora determinados alertas e políticas de segurança possam disparar investigações automatizadas, nenhuma ação de correção é executada automaticamente para email e conteúdo. Em vez disso, todas as ações de correção para email e conteúdo de email aguardam aprovação por sua equipe de operações de segurança na [central de ações](mtp-action-center.md).

### <a name="to-view-or-change-your-security-and-alert-policies-in-office-365"></a>Para exibir ou alterar suas políticas de segurança e alerta no Office 365

As configurações de segurança no Office 365 ajudam a proteger o email e o conteúdo. Para exibir ou alterar essas configurações, siga as orientações em [proteção contra ameaças](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats).

1. No centro de segurança do Microsoft 365 ( [https://security.microsoft.com/](https://security.microsoft.com/) ), vá até **políticas**de  >  **proteção contra ameaças**.

2. Verifique se todas as políticas a seguir estão configuradas. Para obter ajuda e recomendações, confira [proteção contra ameaças](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats).

   - [Anti-malware (Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-1---anti-malware-protection)
   - [Anti-phishing ATP (Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-2---anti-phishing-protection)
   - [Anexos seguros de ATP (Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#atp-safe-attachments-policies)
   - [Links seguros de ATP (Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#atp-safe-links-policies)
   - [Anti-spam (Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-3---anti-spam-protection) 

4. Verifique se [o Office 365 ATP para SharePoint, onedrive e Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-5---turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams-workloads) está ativado.

5. Verifique se a [limpeza automática de zero horas para proteção de email](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#zero-hour-auto-purge-for-email-in-eop) está em vigor. 

8. (Isso é opcional) Revise suas [políticas de alerta do Office 365](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) no centro de conformidade da Microsoft 365 ( [https://compliance.microsoft.com/compliancepolicies](https://compliance.microsoft.com/compliancepolicies) ). Várias políticas de alerta padrão estão na categoria gerenciamento de ameaças. Alguns desses alertas podem acionar a investigação e a resposta automatizadas. Para saber mais, confira [Default Alert Policies](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?#default-alert-policies).
 
## <a name="make-sure-microsoft-threat-protection-is-turned-on"></a>Verifique se a proteção contra ameaças da Microsoft está ativada

1. Vá para o centro de segurança do Microsoft 365 ( [https://security.microsoft.com](https://security.microsoft.com) ) e entre.

2. No painel de navegação, procure **incidentes**, a **central de ações**e a **caça**, conforme mostrado na imagem a seguir:<br/> :::image type="content" source="../../media/mtp-enable/mtp-on.png" alt-text="MTP no":::

   - Se você vir **incidentes**, **central de ações**e **caça**, a proteção contra ameaças da Microsoft está ativada. Vá para o próximo procedimento, [revise ou altere o nível de automação para grupos de dispositivos](#review-or-change-the-automation-level-for-device-groups).

   - Se você *não* vir **incidentes**, **central de ações**ou **busca**, então a proteção contra ameaças da Microsoft pode não estar ativada. Nesse caso, prossiga para a próxima etapa.

3. No painel de navegação, escolha **configurações**  >  **proteção contra ameaças da Microsoft**. Confirme se a proteção contra ameaças da Microsoft está ativada. 

   Precisa de ajuda? Consulte [ativar a proteção contra ameaças da Microsoft](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable).

## <a name="review-pending-and-completed-actions-in-the-action-center"></a>Revisar ações pendentes e concluídas na central de ações

Depois de configurar a investigação e a resposta automatizadas na proteção contra ameaças da Microsoft, a próxima etapa é visitar a central de ações ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ). Lá, você pode revisar e aprovar ações pendentes e ver ações de correção realizadas automaticamente. 

[Visite a central de ações](mtp-action-center.md).
