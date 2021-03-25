---
title: Responder a ameaças da Web no Microsoft Defender ATP
description: Responder a alertas relacionados a sites mal-intencionados e indesejados. Entenda como a proteção contra ameaças da Web informa os usuários finais por meio de seus navegadores da Web e notificações do Windows
keywords: proteção da Web, proteção contra ameaças da Web, navegação na Web, alertas, resposta, segurança, phishing, malware, exploração, sites, proteção de rede, Edge, Internet Explorer, Chrome, Firefox, navegador da Web, notificações, usuários finais, notificações do Windows, página de bloqueio,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a9f3873db4f85cec3f5f1a400dcfb7930c6a4faa
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187536"
---
# <a name="respond-to-web-threats"></a>Responder a ameaças da Web

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

A proteção da Web no Microsoft Defender para Ponto de Extremidade permite investigar e responder com eficiência a alertas relacionados a sites mal-intencionados e sites em sua lista de indicadores personalizados.

## <a name="view-web-threat-alerts"></a>Exibir alertas de ameaça da Web
O Microsoft Defender para Ponto de Extremidade gera os seguintes [alertas](manage-alerts.md) para atividades da Web mal-intencionadas ou suspeitas:
- **Conexão suspeita bloqueada pela** proteção de rede — esse alerta é gerado quando uma  tentativa de acessar um site mal-intencionado ou um site em sua lista de indicadores personalizados é interrompida pela proteção de rede no modo *de* bloqueio
- **Conexão suspeita detectada** pela proteção de rede — esse alerta é gerado quando uma tentativa de acessar um site mal-intencionado ou um site em sua lista de indicadores personalizados é detectada pela proteção de rede no modo somente *auditoria*

Cada alerta fornece as seguintes informações: 
- Dispositivo que tentou acessar o site bloqueado
- Aplicativo ou programa usado para enviar a solicitação da Web
- URL ou URL mal-intencionadas na lista de indicadores personalizados
- Ações recomendadas para respondentes

![Imagem de um alerta relacionado à proteção contra ameaças da Web](images/wtp-alert.png)

>[!Note]
>Para reduzir o volume de alertas, o Microsoft Defender for Endpoint consolida detecções de ameaças da Web para o mesmo domínio no mesmo dispositivo todos os dias para um único alerta. Somente um alerta é gerado e contado no [relatório de proteção da Web.](web-protection-monitoring.md)

## <a name="inspect-website-details"></a>Inspecionar detalhes do site
Você pode mergulhar mais fundo selecionando a URL ou o domínio do site no alerta. Isso abre uma página sobre essa URL ou domínio específico com várias informações, incluindo:
- Dispositivos que tentaram acessar o site
- Incidentes e alertas relacionados ao site
- A frequência com que o site foi visto em eventos em sua organização

    ![Imagem da página de detalhes do domínio ou da entidade URL](images/wtp-website-details.png)

[Saiba mais sobre páginas de URL ou entidade de domínio](investigate-domain.md)

## <a name="inspect-the-device"></a>Inspecionar o dispositivo
Você também pode verificar o dispositivo que tentou acessar uma URL bloqueada. Selecionar o nome do dispositivo na página de alerta abre uma página com informações abrangentes sobre o dispositivo.

[Saiba mais sobre páginas de entidade de dispositivo](investigate-machines.md)

## <a name="web-browser-and-windows-notifications-for-end-users"></a>Navegador da Web e notificações do Windows para usuários finais

Com a proteção da Web no Microsoft Defender para Ponto de Extremidade, seus usuários finais serão impedidos de visitar sites mal-intencionados ou indesejados usando o Microsoft Edge ou outros navegadores. Como o bloqueio é realizado pela proteção [de rede,](network-protection.md)eles verão um erro genérico do navegador da Web. Eles também verão uma notificação do Windows.

![Imagem do Microsoft Edge mostrando um erro 403 e a ameaça web de notificação do Windows ](images/wtp-browser-blocking-page.png)
 *bloqueada no Microsoft Edge*

![Imagem do navegador da Web do Chrome mostrando um aviso de conexão segura e a ameaça web de notificação do Windows ](images/wtp-chrome-browser-blocking-page.png)
 *bloqueada no Chrome*

## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da proteção da Web](web-protection-overview.md)
- [Filtragem de conteúdo da Web](web-content-filtering.md)
- [Proteção contra ameaças da Web](web-threat-protection.md)
- [Monitorar a segurança da Web](web-protection-monitoring.md)
