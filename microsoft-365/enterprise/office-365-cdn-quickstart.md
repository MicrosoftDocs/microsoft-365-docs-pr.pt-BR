---
title: Início rápido da Rede de Distribuição de Conteúdo (CDN) do Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 06/04/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
- m365initiative-coredeploy
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- SPO160
description: Início rápido da Rede de Distribuição de Conteúdo (CDN) do Office 365
ms.openlocfilehash: e541b2ea63a69644de22329c45bd6963749964f7
ms.sourcegitcommit: d76a4c07f0be2938372bdfae50e0e4d523bd8e9f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/14/2020
ms.locfileid: "48456406"
---
# <a name="office-365-content-delivery-network-cdn-quickstart"></a>Início rápido da Rede de Distribuição de Conteúdo (CDN) do Office 365

Você pode usar a Rede de Distribuição de Conteúdo (CDN) interna do **Office 365** para hospedar ativos estáticos (imagens, JavaScript, folhas de estilo, arquivos WOFF) para fornecer melhor desempenho para suas páginas do SharePoint Online. A CDN do Office 365 melhora o desempenho ao armazenar em cache ativos estáticos mais próximos aos navegadores que os solicitaram, o que ajuda a acelerar downloads e reduzir a latência. Além disso, a CDN do Office 365 usa o protocolo HTTP/2 para maior compactação e canalização HTTP. O serviço de CDN do Office 365 faz parte da assinatura do SharePoint Online.

Para obter orientações mais detalhadas, confira Usar a Rede de Distribuição de Conteúdo [(CDN) do Office 365 com o SharePoint Online.](use-microsoft-365-cdn-with-spo.md)

>[!NOTE]
>A CDN do Office 365 só está disponível para locatários na nuvem de produção (em todo o mundo). Locatários nas nuvens do Governo dos EUA, China e Alemanha não têm suporte atualmente para a CDN do Office 365.

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-identify-items-not-in-cdn"></a>Usar a ferramenta Diagnóstico de Página do SharePoint para identificar itens que não estão na CDN

Você pode usar a extensão do navegador da ferramenta Diagnóstico de Página para SharePoint para listar facilmente ativos em suas páginas do SharePoint Online que podem ser **adicionados** a uma origem de CDN.

A ferramenta Diagnóstico de Página para **SharePoint** é uma extensão de navegador para o novo Microsoft Edge ( e navegadores Chrome que analisam tanto o portal moderno do SharePoint Online quanto as páginas clássicas do site de https://www.microsoft.com/edge) publicação. A ferramenta fornece um relatório para cada página analisada que mostra o desempenho da página em relação a um conjunto definido de critérios de desempenho. Para instalar e saber mais sobre a ferramenta Diagnóstico de Página para SharePoint, acesse [Usar a ferramenta Diagnóstico de Página para SharePoint Online](https://aka.ms/perftool).

Ao executar a ferramenta Diagnóstico de Página para SharePoint em uma  página do SharePoint Online, você pode clicar na guia Testes de Diagnóstico para ver uma lista de ativos que não estão sendo hospedados pela CDN. Esses ativos serão listados sob a verificação da Rede de Distribuição de Conteúdo **(CDN)** do título, conforme mostrado na captura de tela abaixo.

![Diagnóstico de página](../media/page-diagnostics-for-spo/pagediag-results-general.PNG)

>[!NOTE]
>A ferramenta de Diagnóstico de Página só funciona com o SharePoint Online e não pode ser usada em uma página do sistema do SharePoint.

## <a name="cdn-overview"></a>Visão geral da CDN

A CDN do Office 365 foi projetada para otimizar o desempenho dos usuários distribuindo objetos acessados com frequência, como imagens e arquivos javascript, por uma rede global de alta velocidade, reduzindo o tempo de carregamento da página e fornecendo acesso ao mais próximo possível dos objetos hospedados para o usuário. A CDN busca seus ativos de um local chamado _origem._ Uma origem pode ser um site do SharePoint, uma biblioteca de documentos ou uma pasta acessível por uma URL.

A CDN do Office 365 é separada em dois tipos básicos:

- **A CDN** pública foi projetada para ser usada para JS (JavaScript), CSS (StyleSheets), Arquivo de Fonte da Web (WOFF, WOFF2) e imagens não proprietárias, como logotipos da empresa.
- **A CDN** privada foi projetada para ser usada para imagens (PNG, JPG, JPEG, etc.).

Você pode optar por ter origens públicas ou privadas para sua organização. A maioria das organizações optará por implementar uma combinação dos dois. As opções públicas e privadas oferecem ganhos de desempenho semelhantes, mas cada uma tem vantagens e atributos exclusivos. Para obter mais informações sobre origens de CDN públicas e privadas, consulte Escolher se [cada origem deve ser pública ou privada.](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)

## <a name="how-to-enable-public-and-private-cdn-with-the-default-configuration"></a>Como habilitar a CDN pública e privada com a configuração padrão
Antes de fazer alterações nas configurações da CDN do locatário, você deve verificar se ele atende às políticas de conformidade, segurança e privacidade da sua organização.

Para obter configurações mais detalhadas ou se você já habilitar a CDN e quiser adicionar locais adicionais (origens), confira a seção Configurar e configurar a CDN do [Office 365](use-microsoft-365-cdn-with-spo.md#set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell) usando o Shell de Gerenciamento do SharePoint Online

Conecte-se ao seu locatário usando o Shell de Gerenciamento do SharePoint Online:

```PowerShell
Connect-SPOService -Url https://<YourTenantName>-admin.sharepoint.com
```

Para permitir que sua organização use origens públicas e privadas com a configuração padrão, digite o seguinte comando:

```PowerShell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true
```

A saída desses cmdlets deve ter a seguinte aparência:

![Saída de Set-SPOTenantCdnEnabled](../media/O365-CDN/o365-cdn-enable-output.png)

## <a name="see-also"></a>Confira também

[Usar a ferramenta Diagnóstico de Página para SharePoint Online](https://aka.ms/perftool)

[Usar a Rede de Distribuição de Conteúdo (CDN) do Office 365 com o SharePoint Online](use-microsoft-365-cdn-with-spo.md)

[Redes de Distribuição de Conteúdo](https://aka.ms/o365cdns)

[Planejamento de rede e ajuste de desempenho para o Office 365](https://aka.ms/tune)

[Série de desempenho do SharePoint - série de vídeos da CDN do Office 365](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)
