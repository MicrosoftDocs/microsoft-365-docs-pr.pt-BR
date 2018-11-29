---
title: 'Etapa 1: preparação de dispositivos e aplicativos'
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 09/14/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Aprenda a avaliar a preparação de dispositivos e aplicativos no ambiente.
ms.openlocfilehash: a9fa85ea37de06399aa2264b09c61e588edc2107
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865327"
---
# <a name="step-1-device-and-app-readiness"></a>Etapa 1: preparação de dispositivos e aplicativos

Comece seu projeto de implantação da área de trabalho com um inventário dos seus dispositivos e aplicativos, priorize o que você deseja avançar, teste os aplicativos e dispositivos priorizados e corrija o que for preciso para se preparar para a implantação.

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-1.png)

<table>
<thead>
<td><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-3.png" alt="Step 1" height="130" width="130" /></td>
<td><p><strong>Etapa 1: preparação de dispositivos e aplicativos</strong></p>
<p>Comece seu projeto de implantação da área de trabalho com um inventário dos seus dispositivos e aplicativos, priorize o que você deseja avançar, teste os aplicativos e dispositivos priorizados e corrija o que for preciso para se preparar para a implantação.</p></td>
<td><a href="https://aka.ms/ddev1" target="_blank"><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-14.png" alt="Step 1" height="120" width="213" /></a></td>
</thead>
</table>

>[!NOTE]
>A Preparação de Dispositivos e Aplicativos é a primeira etapa na nossa roda de processos de implantação recomendados, cobrindo os aspectos abrangentes da compatibilidade de aplicativos e hardware. Para ver o processo de implantação completo da área de trabalho, acesse o [Centro de implantação do Computador Moderno](https://aka.ms/HowToShift).
>

No passado, um grande desafio para a atualização de computadores dos usuários era a compatibilidade entre aplicativos e hardware. A boa notícia ao planejar sua migração para o Windows 10 e Office 365 ProPlus é que qualquer aplicativo escrito nos últimos 10 anos funciona no Windows 10, e todos os suplementos e macros do VBA que sua organização usou em versões do Office desde o Office 2010 continuam a funcionar em versões mais recentes do Office, sem precisar de modificações.

Dito isto, dependendo do tamanho e da idade da sua organização, verificar a compatibilidade entre aplicativos e hardware provavelmente ainda é uma etapa inicial essencial no nosso processo de implantação recomendado de fase de 8.

Neste artigo, fornecemos orientações sobre esta primeira fase – Preparação de Dispositivos e Aplicativos – usando a nova ferramenta Windows Analytics Upgrade Readiness, uma solução inteligente baseada na nuvem disponível com sua licença do Windows.

Se você atualmente não tem o Windows Analytics configurado para seu ambiente, ou deseja inscrever-se para uma avaliação, acesse a [Página do Windows Analytics](http://www.aka.ms/windowsanalytics) e comece a usar.

## <a name="recommended-tool-windows-analytics-upgrade-readiness"></a>Ferramenta recomendada: Windows Analytics Upgrade Readiness

O Windows Analytics Upgrade Readiness oferece muitas vantagens em relação a sistemas de gerenciamento de área de trabalho tradicionais, e é a nossa ferramenta recomendada. Funciona sem agentes, fornece orientações sobre o que precisa ser feito e utiliza informações de compatibilidade entre aplicativos e drivers, obtidas por meio da atualização de centenas de milhões de PCs de consumidores, para fornecer uma análise detalhada que identifica problemas de compatibilidade que podem impedir sua atualização, com links para correções sugeridas de conhecimento da Microsoft.

Para configurar o Window Analytics Upgrade Readiness, primeiro será preciso configurar uma assinatura do Azure e incluir um espaço de trabalho do Azure Log Analytics para fazer isso. Depois que o serviço Windows Analytics Upgrade Readiness estiver em execução, você poderá inscrever qualquer dispositivo com Windows 7 SP1 ou mais recente conectado à Internet por meio das configurações de Política de Grupo. É simples assim. Não existem agentes para implantar, e o fluxo de trabalho visual do Windows Analytics Upgrade Readiness orienta você desde o teste piloto até à implantação para produção. Se desejar, você pode exportar dados do Windows Analytics Upgrade Readiness para ferramentas de implantação de software como o System Center Configuration Manager, para direcionar a PCs individualmente e criar conjuntos assim que eles estejam prontos para implantação.

## <a name="device-and-app-readiness-process"></a>Preparação de dispositivos e aplicativos

A Preparação de Dispositivos e Aplicativos é composta por quatro etapas: 1. Inventário, 2. Priorizar, 3. Testar, 4. Corrigir. Vamos examiná-las uma de cada vez.

### <a name="1-inventory"></a>1\. Inventário

O serviço do Windows Analytics Upgrade Readiness usa um processo sem agentes para inventariar os computadores, aplicativos e suplementos do Office no seu conjunto de computadores.

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-3.png)

Ele também fornece relatórios sobre sites da Internet, aplicativos e locais da intranet altamente visitados, para ajudá-lo a realizar testes de compatibilidade posteriormente.

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-4.png)

### <a name="2-prioritize"></a>2\. Priorizar

Com o inventário realizado, o Windows Analytics Upgrade Readiness ajuda a identificar e priorizar os aplicativos e hardware mais comumente usados na sua organização, e no que se concentrar para desbloquear o máximo de computadores possível para implantação,

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-5.png)

também fornecendo orientações para ajudá-lo a avaliar as atualizações necessárias para resolver problemas durante a próxima etapa: o teste.

### <a name="3-testing"></a>3\. Testar

Você descobrirá que a maioria dos suplementos, aplicativos e drivers inventariados funcionarão sem precisar de alterações. Para os itens que o Windows Analytics Upgrade Readiness avalie como tendo problemas, ele oferece informações conhecidas, incluindo onde encontrar atualizações de versão para resolver problemas de compatibilidade. Em vez de dedicar tempo e recursos para solucionar problemas complexos em aplicativos não essenciais pouco implantados e dispositivos antigos, você pode optar por trabalhar com os usuários para desativar e substituir esses itens.

Você também pode usar o Windows Analytics Upgrade Readiness para avaliar problemas de compatibilidade baseados no navegador, identificar os aplicativos Web e sites acessados por usuários que ainda estão usando controles ActiveX, Objetos de Ajuda do Navegador, VBScript ou outras tecnologias herdadas sem suporte no navegador Microsoft Edge. Seus usuários ainda precisarão usar o Internet Explorer 11 para esses sites, e você pode adicioná-los à [lista de sites do modo Empresarial](https://docs.microsoft.com/pt-BR/microsoft-edge/deploy/emie-to-improve-compatibility) usando o Enterprise Mode Site List Manager.

Além disso, para ajudar na mudança para o Office 365 ProPlus, você pode usar o [Readiness Toolkit for Office](https://docs.microsoft.com/pt-BR/deployoffice/use-the-readiness-toolkit-to-assess-application-compatibility-for-office-365-pro) para testar a compatibilidade dos seus suplementos e macros do Microsoft Visual Basic for Applications (VBA).

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-6.png)

### <a name="4-remediation"></a>4\. Corrigir

Como a fase final da preparação de dispositivos e aplicativos é "corrigir", aqui o seu objetivo será coletar os pacotes de driver ou softwares necessários, que serão usados para substituir ou atualizar as versões mais antigas como parte do processo de implantação.

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-7.png)

Conforme remedia problemas da lista, você verá que mais e mais PCs ficam "Prontos para implantação". Isso significa que os drivers e os aplicativos nos computadores estão listados como compatíveis com a versão de destino para implantação do Windows 10.

## <a name="continued-use-of-telemetry-tools"></a>Uso contínuo de ferramentas de telemetria

O Windows Analytics Upgrade Readiness não é apenas uma ferramenta para ajudá-lo a mudar para o Windows 10 e Office 365 ProPlus. Quando tiver computadores executando o Windows 10 e o Office 365, você poderá usar esta ferramenta para ajudar na manutenção da sua implantação e para gerenciar as Atualizações de Recursos semestrais e manter-se atualizado.

## <a name="next-step"></a>Próxima etapa 

## <a name="step-2-directory-and-network-readinesshttpsakamsmdd2"></a>[Etapa 2: diretório e preparação de rede](https://aka.ms/mdd2)