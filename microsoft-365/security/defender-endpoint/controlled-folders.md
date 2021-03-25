---
title: Proteger pastas importantes contra ransomware para não criptografar seus arquivos com acesso controlado a pastas
description: Arquivos em pastas padrão podem ser protegidos contra alterações por aplicativos mal-intencionados. Impedir que ransomware criptografe seus arquivos.
keywords: acesso controlado a pastas, windows 10, windows defender, ransomware, protect, files, folders
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
audience: ITPro
ms.date: 02/03/2021
ms.reviewer: v-maave
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.openlocfilehash: ae50d53fbc9bf01d4cd16b939461eecc9ec1a568
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165172"
---
# <a name="protect-important-folders-with-controlled-folder-access"></a>Proteger pastas importantes com acesso controlado a pastas

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="what-is-controlled-folder-access"></a>O que é acesso controlado a pastas?

O acesso controlado a pastas ajuda a proteger seus dados valiosos contra aplicativos mal-intencionados e ameaças, como ransomware. O acesso controlado a pastas protege seus dados verificando aplicativos em uma lista de aplicativos conhecidos e confiáveis. Com suporte nos clientes do Windows Server 2019 e do Windows 10, o acesso controlado a pastas pode ser ligado usando o Aplicativo de Segurança do Windows, o Microsoft Endpoint Configuration Manager ou o Intune (para dispositivos gerenciados). 

> [!NOTE]
> Os mecanismos de script não são confiáveis e você não pode permitir que eles acessem pastas protegidas controladas.  Por exemplo, o PowerShell não é confiável por acesso controlado a pastas, mesmo que você permita com indicadores [de certificado e arquivo.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/indicator-certificates) 

O acesso controlado a pastas funciona melhor com o [Microsoft Defender para Ponto](microsoft-defender-advanced-threat-protection.md)de Extremidade , que fornece relatórios detalhados sobre eventos e blocos de acesso controlado a pastas como parte dos cenários de investigação de [alertas usuais.](investigate-alerts.md)

> [!TIP]
> Os blocos de acesso controlados a pastas não geram alertas na fila [de alertas.](alerts-queue.md) No entanto, você pode exibir informações sobre blocos de acesso controlados a pastas no exibição de linha do tempo do dispositivo [,](investigate-machines.md)ao usar a busca avançada [ou](advanced-hunting-overview.md)com regras de detecção [personalizadas.](custom-detection-rules.md)

## <a name="how-does-controlled-folder-access-work"></a>Como funciona o acesso controlado a pastas?

O acesso controlado a pastas funciona apenas permitindo que aplicativos confiáveis acessem pastas protegidas. As pastas protegidas são especificadas quando o acesso controlado a pastas é configurado. Normalmente, pastas comumente usadas, como as usadas para documentos, imagens, downloads e assim por diante, são incluídas na lista de pastas controladas. 

O acesso controlado a pastas funciona com uma lista de aplicativos confiáveis. Os aplicativos incluídos na lista de softwares confiáveis funcionam conforme o esperado. Os aplicativos que não estão incluídos na lista são impedidos de fazer alterações nos arquivos dentro de pastas protegidas. 

Os aplicativos são adicionados à lista com base em sua prevalência e reputação. Aplicativos altamente predominantes em toda a sua organização e que nunca exibiram nenhum comportamento considerado mal-intencionado são considerados confiáveis. Esses aplicativos são adicionados à lista automaticamente.

Os aplicativos também podem ser adicionados manualmente à lista confiável usando o Configuration Manager ou o Intune. Ações adicionais, como [adicionar um indicador](respond-file-alerts.md#add-indicator-to-block-or-allow-a-file) de arquivo para um aplicativo, podem ser executadas no Console da Central de Segurança.

## <a name="why-controlled-folder-access-is-important"></a>Por que o acesso controlado a pastas é importante

O acesso controlado a pastas é especialmente útil para ajudar a proteger seus documentos e informações do [ransomware.](https://www.microsoft.com/wdsi/threats/ransomware) Em um ataque de ransomware, seus arquivos podem ser criptografados e mantidos como reféns. Com o acesso controlado a pastas no local, uma notificação é exibida no computador onde um aplicativo tentou fazer alterações em um arquivo em uma pasta protegida. Você pode [personalizar a notificação com](customize-attack-surface-reduction.md#customize-the-notification) os detalhes da empresa e informações de contato. Você também pode habilitar as regras individualmente para personalizar quais técnicas os monitores de recursos.

As [pastas protegidas incluem](#review-controlled-folder-access-events-in-windows-event-viewer) pastas comuns do sistema (incluindo setores de inicialização) e você pode [adicionar mais pastas](customize-controlled-folders.md#protect-additional-folders). Você também pode [permitir que os aplicativos](customize-controlled-folders.md#allow-specific-apps-to-make-changes-to-controlled-folders) lhes dêem acesso às pastas protegidas.

Você pode usar o [modo de auditoria](audit-windows-defender.md) para avaliar como o acesso controlado a pastas afetaria sua organização se ele estivesse habilitado. Você também pode visitar o site do [](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) Windows Defender de teste no demo.wd.microsoft.com para confirmar se o recurso está funcionando e ver como ele funciona.

O acesso controlado a pastas é suportado nas seguintes versões do Windows:
- [Windows 10, versão 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) e posterior
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

## <a name="windows-system-folders-are-protected-by-default"></a>As pastas do sistema Windows são protegidas por padrão

As pastas do sistema Windows são protegidas por padrão, juntamente com várias outras pastas: 

- `c:\Users\<username>\Documents`
- `c:\Users\Public\Documents`
- `c:\Users\<username>\Pictures`
- `c:\Users\Public\Pictures`
- `c:\Users\Public\Videos`
- `c:\Users\<username>\Videos`
- `c:\Users\<username>\Music`
- `c:\Users\Public\Music`
- `c:\Users\<username>\Favorites`

> [!NOTE]
> Você pode configurar pastas adicionais como protegidas, mas não pode remover as pastas do sistema Windows protegidas por padrão.

## <a name="requirements-for-controlled-folder-access"></a>Requisitos para acesso controlado a pastas

O acesso controlado a pastas requer a habilitação da [proteção em tempo real do Microsoft Defender Antivírus.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus)

## <a name="review-controlled-folder-access-events-in-the-microsoft-defender-security-center"></a>Revisar eventos de acesso controlado a pastas no Centro de Segurança do Microsoft Defender

O Defender for Endpoint fornece relatórios detalhados sobre eventos e blocos como parte de seus [cenários de investigação de alerta.](investigate-alerts.md)

Você pode consultar dados do Microsoft Defender para o Ponto de Extremidade usando [a busca avançada](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/advanced-hunting-windows-defender-advanced-threat-protection). Se você estiver usando o modo [](advanced-hunting-overview.md) [de](audit-windows-defender.md)auditoria, poderá usar a busca avançada para ver como as configurações de acesso controlado a pastas afetariam seu ambiente se elas fossem habilitadas.

Exemplo de consulta:

```PowerShell
DeviceEvents
| where ActionType in ('ControlledFolderAccessViolationAudited','ControlledFolderAccessViolationBlocked')
```

## <a name="review-controlled-folder-access-events-in-windows-event-viewer"></a>Revisar eventos de acesso controlado a pastas no Visualizador de Eventos do Windows

Você pode revisar o log de eventos do Windows para ver eventos criados quando blocos de acesso controlados a pastas (ou auditorias) um aplicativo:

1. Baixe o [Pacote de Avaliação](https://aka.ms/mp7z2w) e extraia o arquivo *cfa-events.xml* para um local facilmente acessível no dispositivo.
2. Digite **Visualizador de eventos** no menu Iniciar para abrir o Visualizador de Eventos do Windows.
3. No painel esquerdo, em **Ações**, selecione **Importar exibição personalizada...**.
4. Navegue até onde você *extraiucfa-events.xml* e selecione-o. Como alternativa, [copie o XML diretamente](event-views.md).
5. Selecione **OK**.

A tabela a seguir mostra eventos relacionados ao acesso controlado a pastas:

|ID de evento | Descrição |
|:---|:---|
|5007 | Evento quando as configurações são alteradas |
|1124 | Evento de acesso controlado a pastas auditadas | 
|1123 | Evento de acesso controlado de pasta bloqueado |

## <a name="view-or-change-the-list-of-protected-folders"></a>Exibir ou alterar a lista de pastas protegidas

Você pode usar o aplicativo segurança do Windows para exibir a lista de pastas protegidas pelo acesso controlado a pastas. 

1. Em seu dispositivo Windows 10, abra o aplicativo segurança do Windows.
2. Selecione **Proteção contra & contra ameaças.**
3. Em **Proteção contra ransomware,** selecione **Gerenciar proteção de ransomware**.
4. Se o acesso controlado à pasta estiver desligado, você precisará au acessá-lo. Selecione **pastas protegidas**.
5. Faça uma das seguintes etapas:
   - Para adicionar uma pasta, selecione **+ Adicionar uma pasta protegida**.
   - Para remover uma pasta, selecione-a e selecione **Remover**. 

> [!NOTE]
> [As pastas do sistema do Windows](#windows-system-folders-are-protected-by-default) são protegidas por padrão e você não pode removê-las da lista.

## <a name="see-also"></a>Confira também

- [Avaliar o acesso controlado a pastas](evaluate-controlled-folder-access.md)
- [Personalizar o acesso controlado a pastas](customize-controlled-folders.md)
- [Proteger mais pastas](customize-controlled-folders.md#protect-additional-folders)
