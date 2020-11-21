---
title: Analisar ameaças detectadas e tomar medidas
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid: MET150
description: Saiba como revisar e gerenciar ameaças detectadas pelo Microsoft Defender Antivirus em seus dispositivos Windows 10.
ms.openlocfilehash: 21830b91bfbb88fdd5d5139ee07c4dfb35f5b875
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376672"
---
# <a name="review-detected-threats-and-take-action"></a>Analisar ameaças detectadas e tomar medidas

Assim que um arquivo mal-intencionado ou software é detectado, o Microsoft Defender Antivirus o bloqueia e impede sua execução. E com a proteção fornecida na nuvem ativada, as ameaças recentemente detectadas são adicionadas ao mecanismo de antivírus e antimalware para que os outros dispositivos e usuários também estejam protegidos.

O Microsoft defender antivírus detecta e protege contra os seguintes tipos de ameaças:

- Vírus, malware e ameaças baseadas na Web em dispositivos
- Tentativas de phishing
- Tentativas de roubo de dados

Como um profissional/administrador de ti, você pode exibir informações sobre as detecções de ameaças em [dispositivos Windows 10 que estão inscritos no Intune](/mem/intune/enrollment/device-enrollment) no centro de administração do Microsoft 365. Você verá informações resumidas, como:

- Quantos dispositivos precisam de proteção antivírus
- Quantos dispositivos não estão em conformidade com as políticas de segurança
- Quantas ameaças estão atualmente ativas, atenuadas ou resolvidas

Você tem várias opções para exibir informações específicas sobre detecções de ameaças e dispositivos:

- A página **dispositivos ativos** no <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">centro de administração do Microsoft 365</a>. Consulte [gerenciar detecções de ameaças na página de dispositivos ativos](#manage-threat-detections-on-the-active-devices-page) neste artigo.
- A página **ameaças ativas** no <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">centro de administração do Microsoft 365</a>. Consulte [gerenciar detecções de ameaças na página de ameaças ativas](#manage-threat-detections-on-the-active-threats-page) neste artigo.
- A página **antivírus** no <a href="https://endpoint.microsoft.com" target="_blank">Microsoft Endpoint Manager</a>. Consulte [gerenciar detecções de ameaças no Microsoft Endpoint Manager](#manage-threat-detections-in-microsoft-endpoint-manager) neste artigo.

Para saber mais, confira [ameaças detectadas pelo Microsoft Defender Antivirus](threats-detected-defender-av.md).

## <a name="manage-threat-detections-on-the-active-devices-page"></a>Gerenciar detecções de ameaças na página de **dispositivos ativos**

O procedimento a seguir se aplica aos clientes que têm o Microsoft 365 Business Premium.

1. Vá para o centro de administração do Microsoft 365 em <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> e entre.

2. Na página de navegação, selecione dispositivos ativos de **dispositivos**  >  **Active devices**. Você verá uma lista de dispositivos ativos e detalhes, como status de proteção, estado de proteção antivírus (AV) e o número de ameaças ativas detectadas.

3. Selecione um dispositivo para exibir mais detalhes sobre o dispositivo e as ações disponíveis. Um submenu abre com recomendações e ações disponíveis, como **política de atualização**, **Atualizar antivírus**, **executar verificação rápida**, **executar verificação completa** e muito mais.

## <a name="manage-threat-detections-on-the-active-threats-page"></a>Gerenciar detecções de ameaças na página de **ameaças ativas**

O procedimento a seguir se aplica aos clientes que têm o Microsoft 365 Business. Os [dispositivos Windows 10 devem ser protegidos](/microsoft-365/business/secure-win-10-pcs) e [registrados no Intune](/mem/intune/enrollment/windows-enrollment-methods).

> [!NOTE]
> A página do **Microsoft Defender Antivirus** e as **ameaças ativas** estão sendo distribuídas em fases, portanto, talvez você não tenha acesso imediato a elas.

1. Vá para o centro de administração do Microsoft 365 em <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> e entre.

2. Na placa **Microsoft defender antivírus** , selecione **Exibir ameaças ativas**. (Como alternativa, no painel de navegação, selecione **integridade**  >  **Ameaças & antivírus**.)

3. Na página **ameaças ativas** , selecione uma ameaça detectada para saber mais sobre isso. Um submenu abre com detalhes sobre essa ameaça, incluindo quais dispositivos são afetados.

4. No submenu, selecione um dispositivo para exibir as ações disponíveis, como **política de atualização**, **Atualizar antivírus**, **executar verificação rápida** e muito mais.

## <a name="actions-you-can-take"></a>Ações que você pode realizar

Ao exibir detalhes sobre ameaças ou dispositivos específicos, você verá recomendações e uma ou mais ações que você pode realizar. A tabela a seguir descreve as ações que podem ser exibidas.<br><br>

| Ação | Descrição |
|--|--|
| Configurar a proteção | Suas políticas de proteção contra ameaças precisam ser configuradas. Selecione o link para ir para a página de configuração da política.<br><br>Precisa de ajuda? Consulte [gerenciar a segurança de dispositivos com políticas de segurança de ponto de extremidade no Microsoft Intune](/mem/intune/protect/endpoint-security-policy). |
| Atualizar política | Suas políticas antivírus e de proteção em tempo real precisam ser atualizadas ou configuradas. Selecione o link para acessar a página de configuração de política.<br><br>Precisa de ajuda? Consulte [gerenciar a segurança de dispositivos com políticas de segurança de ponto de extremidade no Microsoft Intune](/mem/intune/protect/endpoint-security-policy). |
| Executar verificação rápida | Inicia uma verificação antivírus rápida no dispositivo, concentrando-se em locais comuns onde o malware pode ser registrado, como chaves do registro e pastas de inicialização conhecidas do Windows. |
| Executar verificação completa | Inicia uma verificação antivírus completa no dispositivo, concentrando-se em locais comuns onde o malware pode ser registrado e incluindo todos os arquivos e pastas no dispositivo. Os resultados são enviados para [o Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager). |
| Atualizar antivírus | Requer que o dispositivo obtenha [atualizações de inteligência de segurança](https://go.microsoft.com/fwlink/?linkid=2149926) para proteção antivírus e antimalware. |
| Reiniciar dispositivo | Força a reinicialização de um dispositivo Windows 10 em cinco minutos.<br><br>**Importante:** O proprietário do dispositivo ou o usuário não é notificado automaticamente da reinicialização e pode perder trabalho não salvo. |

## <a name="manage-threat-detections-in-microsoft-endpoint-manager"></a>Gerenciar detecções de ameaças no Microsoft Endpoint Manager

Você pode usar o Microsoft Endpoint Manager para gerenciar detecções de ameaças. Os dispositivos Windows 10 devem ser [registrados no Intune](/mem/intune/enrollment/windows-enrollment-methods) (parte do Microsoft Endpoint Manager).

1. Vá para o centro de administração do Microsoft Endpoint Manager em <a href="https://endpoint.microsoft.com" target="_blank">https://endpoint.microsoft.com</a> e entre.

2. No painel de navegação, selecione **segurança do ponto de extremidade**.

3. Em **gerenciar**, selecione **antivírus**. Você verá várias guias, como **Resumo**, pontos de **extremidade não íntegros do Windows 10** e **Windows 10 detectado malware**.

4. Revise as informações nas guias disponíveis e execute as ações necessárias.

Por exemplo, suponha que os dispositivos estão listados na guia **malware detectado no Windows 10** . Ao selecionar um dispositivo, você terá determinadas ações disponíveis, como **reinicializar**, **verificação rápida**, **verificação completa**, **sincronizar** ou **atualizar assinaturas**. Selecione uma ação para o dispositivo.

A tabela a seguir descreve as ações que você pode ver no Microsoft Endpoint Manager.<br><br>

| Ação | Descrição |
|--|--|
| Reiniciar | Força a reinicialização de um dispositivo Windows 10 em cinco minutos.<br><br>**Importante:** O proprietário do dispositivo ou o usuário não é notificado automaticamente da reinicialização e pode perder trabalho não salvo. |
| Verificação rápida | Inicia uma verificação antivírus rápida no dispositivo, concentrando-se em locais comuns onde o malware pode ser registrado, como chaves do registro e pastas de inicialização conhecidas do Windows. Os resultados são enviados para [o Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager). |
| Verificação completa | Inicia uma verificação antivírus completa no dispositivo, concentrando-se em locais comuns onde o malware pode ser registrado e incluindo todos os arquivos e pastas no dispositivo. Os resultados são enviados para [o Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager). |
| Sincronizar | Requer um dispositivo para fazer check-in com o Intune (parte do Microsoft Endpoint Manager). Quando o dispositivo faz check-in, o dispositivo recebe todas as ações ou políticas pendentes atribuídas ao dispositivo. |
| Atualizar assinaturas | Requer que o dispositivo obtenha [atualizações de inteligência de segurança](https://go.microsoft.com/fwlink/?linkid=2149926) para proteção antivírus e antimalware. |

> [!TIP]
> Para obter mais informações, consulte [Remote Actions for Devices](/mem/intune/protect/endpoint-security-manage-devices#remote-actions-for-devices).

## <a name="how-to-submit-a-file-for-malware-analysis"></a>Como enviar um arquivo para análise de malware

Se você tiver um arquivo que acha que foi perdido ou se classificou incorretamente como um malware, você pode enviar esse arquivo para a Microsoft para análise de malware. Os usuários e administradores de ti podem enviar um arquivo para análise. Visita [https://www.microsoft.com/wdsi/filesubmission](https://www.microsoft.com/wdsi/filesubmission) .
