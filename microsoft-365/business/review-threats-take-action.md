---
title: Examine as ameaças detectadas e execute ações
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
description: Saiba como analisar e gerenciar ameaças detectadas por Microsoft Defender Antivírus em seus Windows 10 dispositivos.
ms.openlocfilehash: 15e99fb75e4a3ac1af842ca7d0b900e02cbc6bd4
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50912781"
---
# <a name="review-detected-threats-and-take-action"></a>Examine as ameaças detectadas e execute ações

Assim que um arquivo ou software mal-intencionado for detectado, Microsoft Defender Antivírus-lo e impedir que ele seja executado. E com a proteção entregue na nuvem, as ameaças recém-detectadas são adicionadas ao mecanismo antivírus e antimalware para que seus outros dispositivos e usuários também sejam protegidos.

Microsoft Defender Antivírus detecta e protege contra os seguintes tipos de ameaças:

- Vírus, malware e ameaças baseadas na Web em dispositivos
- Tentativas de phishing
- Tentativas de roubo de dados

Como um profissional/administrador de TI, você pode exibir informações sobre detecções de ameaças em Windows 10 dispositivos que estão inscritos no [Intune](/mem/intune/enrollment/device-enrollment) no centro de administração Microsoft 365 de segurança. Você verá informações resumidas, como:

- Quantos dispositivos precisam de proteção antivírus
- Quantos dispositivos não estão em conformidade com as políticas de segurança
- Quantas ameaças estão ativas, atenuadas ou resolvidas no momento

Você tem várias opções para exibir informações específicas sobre detecções de ameaças e dispositivos:

- A **página Dispositivos ativos** no <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 de administração</a>. Consulte [Gerenciar detecções de ameaças na página Dispositivos ativos](#manage-threat-detections-on-the-active-devices-page) neste artigo.
- A **página Ameaças ativas** no Microsoft 365 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">de administração</a>. Consulte [Gerenciar detecções de ameaças na página Ameaças ativas](#manage-threat-detections-on-the-active-threats-page) neste artigo.
- A **página Antivírus** <a href="https://go.microsoft.com/fwlink/p/?linkid=2150463" target="_blank">em Microsoft Endpoint Manager</a>. Consulte [Gerenciar detecções de ameaças Microsoft Endpoint Manager](#manage-threat-detections-in-microsoft-endpoint-manager) neste artigo.

Para saber mais, confira [Ameaças detectadas por Microsoft Defender Antivírus](threats-detected-defender-av.md).

## <a name="manage-threat-detections-on-the-active-devices-page"></a>Gerenciar detecções de ameaças na página **Dispositivos** ativos

O procedimento a seguir se aplica aos clientes que têm Microsoft 365 Business Premium.

1. Vá para o Microsoft 365 de administração em <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> e entre.

2. Na página de navegação, selecione **Dispositivos**  >  **Ativos dispositivos**. Você verá uma lista de dispositivos ativos e detalhes, como status de proteção, estado de proteção antivírus (AV) e o número de ameaças ativas detectadas.

3. Selecione um dispositivo para exibir mais detalhes sobre esse dispositivo e as ações disponíveis. Um flyout é aberto com recomendações e ações disponíveis, como **Política** de **Atualização,** Atualização **antivírus,** Executar verificação rápida, Executar verificação **completa** e muito mais.

## <a name="manage-threat-detections-on-the-active-threats-page"></a>Gerenciar detecções de ameaças na página **Ameaças ativas**

O procedimento a seguir se aplica aos clientes que têm Microsoft 365 Business Premium. [Windows 10 dispositivos devem ser protegidos](./secure-win-10-pcs.md) [e inscritos no Intune](/mem/intune/enrollment/windows-enrollment-methods).

> [!NOTE]
> A **Microsoft Defender Antivírus** e **a página** Ameaças ativas estão sendo roladas em fases, portanto, talvez você não tenha acesso imediato a eles.

1. Vá para o Microsoft 365 de administração em <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> e entre.

2. No cartão **Microsoft Defender Antivírus,** selecione **Exibir ameaças ativas**. (Como alternativa, no painel de navegação, selecione **Saúde**  >  **Ameaças & antivírus**.)

3. Na página **Ameaças ativas,** selecione uma ameaça detectada para saber mais sobre ela. Um flyout é aberto com detalhes sobre essa ameaça, incluindo quais dispositivos são afetados.

4. No sobrevoo, selecione um dispositivo para exibir ações disponíveis, como **Política** de Atualização, **Atualização** antivírus, **Verificação** rápida e muito mais.

## <a name="actions-you-can-take"></a>Ações que você pode tomar

Quando você exibir detalhes sobre ameaças ou dispositivos específicos, você verá recomendações e uma ou mais ações que você pode tomar. A tabela a seguir descreve as ações que você pode ver.<br><br>

| Ação | Descrição |
|--|--|
| Configurar proteção | Suas políticas de proteção contra ameaças precisam ser configuradas. Selecione o link para ir para a página de configuração de política.<br><br>Precisa de ajuda? Consulte [Gerenciar a segurança do dispositivo com políticas de segurança de](/mem/intune/protect/endpoint-security-policy)ponto de extremidade em Microsoft Intune . |
| Atualizar política | Suas políticas de proteção antivírus e em tempo real precisam ser atualizadas ou configuradas. Selecione o link para ir para a página de configuração de política.<br><br>Precisa de ajuda? Consulte [Gerenciar a segurança do dispositivo com políticas de segurança de](/mem/intune/protect/endpoint-security-policy)ponto de extremidade em Microsoft Intune . |
| Executar uma verificação rápida | Inicia uma verificação rápida de antivírus no dispositivo, concentrando-se em locais comuns onde o malware pode ser registrado, como chaves do Registro e pastas de inicialização Windows conhecidas. |
| Executar a verificação completa | Inicia uma verificação completa de antivírus no dispositivo, concentrando-se em locais comuns onde o malware pode ser registrado e incluindo todos os arquivos e pastas no dispositivo. Os resultados são enviados para [Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager). |
| Atualizar antivírus | Requer que o dispositivo receba atualizações [de inteligência de segurança](https://go.microsoft.com/fwlink/?linkid=2149926) para proteção antivírus e antimalware. |
| Reiniciar dispositivo | Força um Windows 10 a ser reiniciado dentro de cinco minutos.<br><br>**IMPORTANTE:** O proprietário ou usuário do dispositivo não é notificado automaticamente sobre a reinicialização e pode perder o trabalho não saved. |

## <a name="manage-threat-detections-in-microsoft-endpoint-manager"></a>Gerenciar detecções de ameaças em Microsoft Endpoint Manager

Você pode usar Microsoft Endpoint Manager para gerenciar detecções de ameaças. Windows 10 dispositivos devem [estar inscritos no Intune](/mem/intune/enrollment/windows-enrollment-methods) (parte do Microsoft Endpoint Manager).

1. Vá para o Microsoft Endpoint Manager de administração em <a href="https://go.microsoft.com/fwlink/p/?linkid=2150463" target="_blank">https://endpoint.microsoft.com</a> e entre.

2. No painel de navegação, selecione **Segurança do ponto de extremidade**.

3. Em **Gerenciar**, selecione **Antivírus**. Você verá várias guias, como **Resumo,** Windows 10 pontos de extremidade não salubres **e** Windows 10 malware **detectado.**

4. Revise as informações nas guias disponíveis e, em seguida, tome qualquer ação necessária.

Por exemplo, suponha que os dispositivos estão listados **na guia Windows 10 malware** detectado. Ao selecionar um dispositivo, você terá determinadas ações disponíveis, como **Reiniciar,** Verificar **Rapidamente,** Verificação **Completa,** **Sincronização** ou Atualizar **assinaturas**. Selecione uma ação para esse dispositivo.

A tabela a seguir descreve as ações que você pode ver no Microsoft Endpoint Manager.<br><br>

| Ação | Descrição |
|--|--|
| Reiniciar | Força um Windows 10 a ser reiniciado dentro de cinco minutos.<br><br>**IMPORTANTE:** O proprietário ou usuário do dispositivo não é notificado automaticamente sobre a reinicialização e pode perder o trabalho não saved. |
| Verificação Rápida | Inicia uma verificação rápida de antivírus no dispositivo, concentrando-se em locais comuns onde o malware pode ser registrado, como chaves do Registro e pastas de inicialização Windows conhecidas. Os resultados são enviados para [Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager). |
| Verificação completa | Inicia uma verificação completa de antivírus no dispositivo, concentrando-se em locais comuns onde o malware pode ser registrado e incluindo todos os arquivos e pastas no dispositivo. Os resultados são enviados para [Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager). |
| Sincronizar | Requer um dispositivo para fazer check-in com o Intune (parte do Microsoft Endpoint Manager). Quando o dispositivo faz o logons, o dispositivo recebe todas as ações ou políticas pendentes atribuídas ao dispositivo. |
| Atualizar assinaturas | Requer que o dispositivo receba atualizações [de inteligência de segurança](https://go.microsoft.com/fwlink/?linkid=2149926) para proteção antivírus e antimalware. |

> [!TIP]
> Para obter mais informações, consulte [Ações remotas para dispositivos](/mem/intune/protect/endpoint-security-manage-devices#remote-actions-for-devices).

## <a name="how-to-submit-a-file-for-malware-analysis"></a>Como enviar um arquivo para análise de malware

Se você tiver um arquivo que você acha que foi perdido ou classificado incorretamente como malware, você pode enviar esse arquivo à Microsoft para análise de malware. Os usuários e administradores de IT podem enviar um arquivo para análise. Visite [https://www.microsoft.com/wdsi/filesubmission](https://www.microsoft.com/wdsi/filesubmission) .