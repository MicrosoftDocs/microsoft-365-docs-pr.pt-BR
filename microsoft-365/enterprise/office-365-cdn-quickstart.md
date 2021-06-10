---
title: Office 365 Rede de Distribuição de Conteúdo (CDN) Início rápido
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
description: Office 365 Rede de Distribuição de Conteúdo (CDN) Início rápido
ms.openlocfilehash: 3539ad1f11b27c60b5641976ae66a1480ef4be98
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921589"
---
# <a name="office-365-content-delivery-network-cdn-quickstart"></a>Office 365 Rede de Distribuição de Conteúdo (CDN) Início rápido

Você pode usar o Office 365 Rede de Distribuição de Conteúdo **(CDN)** para hospedar ativos estáticos (imagens, JavaScript, folhas de estilo, arquivos WOFF) para fornecer melhor desempenho para suas páginas SharePoint Online. A CDN do Office 365 melhora o desempenho ao armazenar em cache ativos estáticos mais próximos aos navegadores que os solicitaram, o que ajuda a acelerar downloads e reduzir a latência. Além disso, o Office 365 CDN usa o protocolo HTTP/2 para compactação aprimorada e pipelização HTTP. O serviço de CDN do Office 365 faz parte da assinatura do SharePoint Online.

Para obter orientações de informações mais detalhadas, [consulte Use the Office 365 Rede de Distribuição de Conteúdo (CDN) with SharePoint Online](use-microsoft-365-cdn-with-spo.md).

>[!NOTE]
>O Office 365 CDN está disponível apenas para locatários na nuvem de produção (em todo o mundo). Os locatários nas nuvens do Governo dos EUA, China e Alemanha atualmente não suportam o Office 365 CDN.

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-identify-items-not-in-cdn"></a>Use a ferramenta Diagnóstico de Página SharePoint para identificar itens que não estão CDN

Você pode usar a extensão diagnóstico de página para SharePoint do navegador de ferramentas para listar facilmente ativos em suas páginas do SharePoint Online que podem ser **adicionados** a uma origem CDN.

A **ferramenta Diagnóstico de Página para** SharePoint é uma extensão do navegador para o novo Microsoft Edge ( e navegadores do Chrome que analisam o portal moderno do SharePoint Online e páginas de sites de publicação https://www.microsoft.com/edge) clássicas. A ferramenta fornece um relatório para cada página analisada que mostra o desempenho da página em relação a um conjunto definido de critérios de desempenho. Para instalar e saber mais sobre a ferramenta Diagnóstico de Página para SharePoint, acesse [Usar a ferramenta Diagnóstico de Página para SharePoint Online](./page-diagnostics-for-spo.md).

Ao executar a ferramenta Diagnóstico de Página para SharePoint em uma página do  SharePoint Online, você pode clicar na guia Testes de Diagnóstico para ver uma lista de ativos que não estão sendo hospedados pelo CDN. Esses ativos serão listados na Rede de Distribuição de Conteúdo **(CDN) conforme** mostrado na captura de tela abaixo.

![Diagnóstico de página](../media/page-diagnostics-for-spo/pagediag-results-general.PNG)

>[!NOTE]
>A ferramenta de Diagnóstico de Página só funciona com o SharePoint Online e não pode ser usada em uma página do sistema do SharePoint.

## <a name="cdn-overview"></a>CDN Visão geral

O Office 365 CDN foi projetado para otimizar o desempenho dos usuários distribuindo objetos acessados com frequência, como imagens e arquivos javascript em uma rede global de alta velocidade, reduzindo o tempo de carregamento da página e fornecendo acesso aos objetos hospedados o mais próximo possível do usuário. O CDN busca seus ativos de um local chamado de _origem_. Uma origem pode ser um site SharePoint, biblioteca de documentos ou pasta acessível por uma URL.

O Office 365 CDN é separado em dois tipos básicos:

- **O CDN** público foi projetado para ser usado para JS (JavaScript), CSS (StyleSheets), Arquivo de Fonte da Web (WOFF, WOFF2) e imagens não proprietárias, como logotipos da empresa.
- **A CDN** privada foi projetada para ser usada para imagens (PNG, JPG, JPEG, etc.).

Você pode optar por ter origens públicas ou privadas para sua organização. A maioria das organizações optará por implementar uma combinação dos dois. As opções públicas e privadas oferecem ganhos de desempenho semelhantes, mas cada uma delas tem atributos e vantagens exclusivos. Para obter mais informações sobre origens CDN públicas e privadas, consulte [Choose whether each origin should be public or private](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate).

## <a name="how-to-enable-public-and-private-cdn-with-the-default-configuration"></a>Como habilitar o serviço público e CDN com a configuração padrão
Antes de fazer alterações nas configurações CDN locatários, verifique se ele atende às políticas de conformidade, segurança e privacidade da sua organização.

Para obter configurações mais detalhadas ou se você já tiver habilitado o CDN e quiser adicionar locais adicionais (origens), consulte a seção Configurar e configurar o Office 365 CDN usando o Shell de Gerenciamento do [SharePoint Online](use-microsoft-365-cdn-with-spo.md#set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell)

Conexão seu locatário usando o Shell de Gerenciamento SharePoint Online:

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

[Use a ferramenta Diagnóstico de Página para SharePoint Online](./page-diagnostics-for-spo.md)

[Usar a Rede de Distribuição de Conteúdo (CDN) do Office 365 com o SharePoint Online](use-microsoft-365-cdn-with-spo.md)

[Redes de Distribuição de Conteúdo](./content-delivery-networks.md)

[Planejamento de rede e ajuste de desempenho para o Office 365](./network-planning-and-performance.md)

[SharePoint Série de desempenho - Office 365 CDN de vídeo](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)