---
title: Início rápido da rede de distribuição de conteúdo (CDN) do Office 365
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
description: Início rápido da rede de distribuição de conteúdo (CDN) do Office 365
ms.openlocfilehash: e541b2ea63a69644de22329c45bd6963749964f7
ms.sourcegitcommit: d76a4c07f0be2938372bdfae50e0e4d523bd8e9f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/14/2020
ms.locfileid: "48456406"
---
# <a name="office-365-content-delivery-network-cdn-quickstart"></a>Início rápido da rede de distribuição de conteúdo (CDN) do Office 365

Você pode usar a **rede de distribuição de conteúdo (CDN) do Office 365** interna para hospedar ativos estáticos (imagens, JavaScript, folhas de estilos, arquivos do WOFF) para fornecer melhor desempenho para suas páginas do SharePoint Online. A CDN do Office 365 melhora o desempenho ao armazenar em cache ativos estáticos mais próximos aos navegadores que os solicitaram, o que ajuda a acelerar downloads e reduzir a latência. Além disso, a CDN do Office 365 usa o protocolo HTTP/2 para maior compactação e canalização HTTP. O serviço de CDN do Office 365 faz parte da assinatura do SharePoint Online.

Para obter diretrizes de informações mais detalhadas, consulte [usar a rede de distribuição de conteúdo (CDN) do Office 365 com o SharePoint Online](use-microsoft-365-cdn-with-spo.md).

>[!NOTE]
>A CDN do Office 365 só está disponível para locatários na nuvem de produção (internacional). Os locatários nas nuvens do governo dos EUA, da China e da Alemanha não suportam atualmente a CDN do Office 365.

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-identify-items-not-in-cdn"></a>Usar a ferramenta diagnóstico de página para SharePoint para identificar os itens que não estão na CDN

Você pode usar a extensão de **diagnóstico de página para a ferramenta do SharePoint** para listar facilmente os ativos em suas páginas do SharePoint Online que podem ser adicionadas a uma origem de CDN.

A **ferramenta diagnóstico de página do SharePoint** é uma extensão de navegador para o novo Microsoft Edge ( https://www.microsoft.com/edge) e navegadores Chrome que analisa o portal moderno do SharePoint Online e as páginas do site de publicação clássica. A ferramenta fornece um relatório para cada página analisada que mostra o desempenho da página em relação a um conjunto definido de critérios de desempenho. Para instalar e saber mais sobre a ferramenta Diagnóstico de Página para SharePoint, acesse [Usar a ferramenta Diagnóstico de Página para SharePoint Online](https://aka.ms/perftool).

Ao executar a ferramenta diagnóstico de página para SharePoint em uma página do SharePoint Online, você pode clicar na guia **testes de diagnóstico** para ver uma lista de ativos que não estão sendo hospedados pela CDN. Esses ativos serão listados na lista de **CDN (rede de distribuição de conteúdo)** de título, conforme mostrado na captura de tela abaixo.

![Diagnóstico de página](../media/page-diagnostics-for-spo/pagediag-results-general.PNG)

>[!NOTE]
>A ferramenta de Diagnóstico de Página só funciona com o SharePoint Online e não pode ser usada em uma página do sistema do SharePoint.

## <a name="cdn-overview"></a>Visão geral da CDN

A CDN do Office 365 foi projetada para otimizar o desempenho de usuários, distribuindo objetos acessados com frequência, como imagens e arquivos JavaScript, em uma rede global de alta velocidade, reduzindo o tempo de carregamento da página e fornecendo acesso a objetos hospedados o mais próximo possível do usuário. A CDN busca seus ativos de um local chamado _origem_. Uma origem pode ser um site do SharePoint, uma biblioteca de documentos ou uma pasta que possa ser acessada por uma URL.

A CDN do Office 365 é separada em dois tipos básicos:

- A **CDN pública** foi projetada para ser usada para o JS (JavaScript), CSS (folhas de estilo), arquivo de fontes da Web (WOFF, WOFF2) e imagens não proprietárias, como logotipos da empresa.
- A **CDN privada** foi projetada para ser usada para imagens (png, jpg, JPEG, etc.).

Você pode optar por ter origens públicas ou privadas para sua organização. A maioria das organizações optará por implementar uma combinação dos dois. As opções pública e privada fornecem ganhos de desempenho semelhantes, mas cada um tem atributos e vantagens exclusivos. Para obter mais informações sobre origens de CDN públicas e privadas, consulte [escolher se cada origem deve ser pública ou privada](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate).

## <a name="how-to-enable-public-and-private-cdn-with-the-default-configuration"></a>Como habilitar a CDN pública e privada com a configuração padrão
Antes de fazer alterações nas configurações de CDN do locatário, verifique se ela atende às políticas de conformidade, segurança e privacidade da sua organização.

Para saber mais sobre definições de configuração ou se você já habilitou a CDN e deseja adicionar locais adicionais (origens), confira a seção [configurar e configurar a CDN do Office 365 usando o Shell de gerenciamento do SharePoint Online](use-microsoft-365-cdn-with-spo.md#set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell)

Conecte-se ao seu locatário usando o Shell de gerenciamento do SharePoint Online:

```PowerShell
Connect-SPOService -Url https://<YourTenantName>-admin.sharepoint.com
```

Para permitir que sua organização Use origens públicas e privadas com a configuração padrão, digite o seguinte comando:

```PowerShell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true
```

A saída desses cmdlets deve ser semelhante à seguinte:

![Saída de Set-SPOTenantCdnEnabled](../media/O365-CDN/o365-cdn-enable-output.png)

## <a name="see-also"></a>Confira também

[Usar a ferramenta diagnóstico de página para o SharePoint Online](https://aka.ms/perftool)

[Usar a Rede de Distribuição de Conteúdo (CDN) do Office 365 com o SharePoint Online](use-microsoft-365-cdn-with-spo.md)

[Redes de Distribuição de Conteúdo](https://aka.ms/o365cdns)

[Planejamento de rede e ajuste de desempenho para o Office 365](https://aka.ms/tune)

[Série de desempenho do SharePoint-série de vídeo de CDN do Office 365](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)
