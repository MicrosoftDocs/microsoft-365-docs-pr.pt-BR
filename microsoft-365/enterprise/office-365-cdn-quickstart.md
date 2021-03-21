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
ms.openlocfilehash: 3539ad1f11b27c60b5641976ae66a1480ef4be98
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921589"
---
# <a name="office-365-content-delivery-network-cdn-quickstart"></a>Início rápido da Rede de Distribuição de Conteúdo (CDN) do Office 365

Você pode usar a CDN (Rede de Distribuição de Conteúdo) interna do **Office 365** para hospedar ativos estáticos (imagens, JavaScript, folhas de estilo, arquivos WOFF) para fornecer melhor desempenho para suas páginas do SharePoint Online. A CDN do Office 365 melhora o desempenho ao armazenar em cache ativos estáticos mais próximos aos navegadores que os solicitaram, o que ajuda a acelerar downloads e reduzir a latência. Além disso, a CDN do Office 365 usa o protocolo HTTP/2 para compactação aprimorada e pipelinamento HTTP. O serviço de CDN do Office 365 faz parte da assinatura do SharePoint Online.

Para obter orientações mais detalhadas, consulte [Use the Office 365 Content Delivery Network (CDN) with SharePoint Online](use-microsoft-365-cdn-with-spo.md).

>[!NOTE]
>A CDN do Office 365 só está disponível para locatários na nuvem de produção (em todo o mundo). Os locatários nas nuvens do Governo dos EUA, China e Alemanha atualmente não suportam a CDN do Office 365.

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-identify-items-not-in-cdn"></a>Use a ferramenta Diagnóstico de Página do SharePoint para identificar itens que não estão na CDN

Você pode usar a extensão do navegador de ferramentas diagnóstico de página do SharePoint para listar facilmente os ativos em suas páginas do SharePoint Online que podem ser **adicionados** a uma origem da CDN.

A ferramenta Diagnóstico de Página para **SharePoint** é uma extensão do navegador para o novo Microsoft Edge ( e navegadores do Chrome que analisam o portal moderno do SharePoint Online e páginas de site de publicação https://www.microsoft.com/edge) clássicas. A ferramenta fornece um relatório para cada página analisada que mostra o desempenho da página em relação a um conjunto definido de critérios de desempenho. Para instalar e saber mais sobre a ferramenta Diagnóstico de Página para SharePoint, acesse [Usar a ferramenta Diagnóstico de Página para SharePoint Online](./page-diagnostics-for-spo.md).

Ao executar a ferramenta Diagnóstico de Página do SharePoint em uma  página do SharePoint Online, você pode clicar na guia Testes de Diagnóstico para ver uma lista de ativos que não estão sendo hospedados pela CDN. Esses ativos serão listados no título Rede de Entrega de Conteúdo **(CDN),** conforme mostrado na captura de tela abaixo.

![Diagnóstico de página](../media/page-diagnostics-for-spo/pagediag-results-general.PNG)

>[!NOTE]
>A ferramenta de Diagnóstico de Página só funciona com o SharePoint Online e não pode ser usada em uma página do sistema do SharePoint.

## <a name="cdn-overview"></a>Visão geral da CDN

A CDN do Office 365 foi projetada para otimizar o desempenho dos usuários distribuindo objetos acessados com frequência, como imagens e arquivos javascript em uma rede global de alta velocidade, reduzindo o tempo de carregamento da página e fornecendo acesso aos objetos hospedados o mais próximo possível do usuário. A CDN busca seus ativos de um local chamado de _origem_. Uma origem pode ser um site do SharePoint, uma biblioteca de documentos ou uma pasta acessível por uma URL.

A CDN do Office 365 é separada em dois tipos básicos:

- **A CDN** pública foi projetada para ser usada para JS (JavaScript), CSS (StyleSheets), Arquivo de Fonte da Web (WOFF, WOFF2) e imagens não proprietárias, como logotipos da empresa.
- **A CDN privada** foi projetada para ser usada para imagens (PNG, JPG, JPEG, etc.).

Você pode optar por ter origens públicas ou privadas para sua organização. A maioria das organizações optará por implementar uma combinação dos dois. As opções públicas e privadas oferecem ganhos de desempenho semelhantes, mas cada uma delas tem atributos e vantagens exclusivos. Para obter mais informações sobre origens de CDN públicas e privadas, consulte [Choose whether each origin should be public or private](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate).

## <a name="how-to-enable-public-and-private-cdn-with-the-default-configuration"></a>Como habilitar a CDN pública e privada com a configuração padrão
Antes de fazer alterações nas configurações de CDN do locatário, verifique se ela atende às políticas de conformidade, segurança e privacidade da sua organização.

Para obter configurações mais detalhadas ou se você já habilitar a CDN e quiser adicionar locais adicionais (origens), consulte a seção Configurar e configurar a CDN do [Office 365](use-microsoft-365-cdn-with-spo.md#set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell) usando o Shell de Gerenciamento do SharePoint Online

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

[Usar a ferramenta diagnóstico de página para o SharePoint Online](./page-diagnostics-for-spo.md)

[Usar a Rede de Distribuição de Conteúdo (CDN) do Office 365 com o SharePoint Online](use-microsoft-365-cdn-with-spo.md)

[Redes de Distribuição de Conteúdo](./content-delivery-networks.md)

[Planejamento de rede e ajuste de desempenho para o Office 365](./network-planning-and-performance.md)

[Série de desempenho do SharePoint - Série de vídeo CDN do Office 365](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)