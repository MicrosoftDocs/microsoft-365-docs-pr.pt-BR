---
title: Isolamento de locatário no Vídeo do Office 365
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: Neste artigo, encontre uma explicação sobre como o isolamento de locatário mantém os vídeos armazenados de cada locatário separados no Vídeo do Office 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 626a995fc5a3ac971c48cc87bec1017134e87b88
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332239"
---
# <a name="tenant-isolation-in-office-365-video"></a>Isolamento de locatário no Vídeo do Office 365

> [!NOTE]
> O Vídeo do Office 365 será substituído pelo Microsoft Stream. Para saber mais sobre o novo serviço de vídeo corporativo que adiciona inteligência à colaboração em vídeo e saiba mais sobre os planos de transição para clientes atuais do Microsoft 365 Video, confira a visão geral da transição de vídeo do [Office 365](https://docs.microsoft.com/stream/migrate-from-office-365)para o Microsoft Stream.

## <a name="introduction"></a>Introdução

O Armazenamento do Azure é usado para armazenar dados de vários serviços do Office 365, incluindo Vídeo do Office 365 e Sway. O Armazenamento do Azure inclui o armazenamento de Blob, que é um armazenamento de objetos de nuvem altamente escalonável, baseado em REST, usado para armazenar dados não estruturados. O Armazenamento do Azure usa um modelo de controle de acesso simples; cada assinatura do Azure pode criar uma ou mais Contas de Armazenamento. Cada Conta de Armazenamento tem uma chave secreta única que é usada para controlar o acesso a todos os dados dessa Conta de Armazenamento. Isso dá suporte ao cenário típico em que o armazenamento está associado a aplicativos e esses aplicativos têm controle total sobre seus dados associados; por exemplo, o Sway que armazenou conteúdo no Armazenamento do Azure. Todo o conteúdo do cliente do Sway é armazenado em contas de armazenamento compartilhadas do Azure. O conteúdo de cada usuário está em uma árvore de diretório separada de blobs no armazenamento do Azure.

Os sistemas que gerenciam o acesso a ambientes do cliente (por exemplo, o Portal do Azure, SMAPI etc.) são isolados dentro de um aplicativo do Azure operado pela Microsoft. Isso separa logicamente a infraestrutura de acesso do cliente dos aplicativos do cliente e da camada de armazenamento.

## <a name="tenant-isolation-in-office-365-video"></a>Isolamento de locatário no Vídeo do Office 365

[O Vídeo do Office 365](https://support.office.com/article/Meet-Office-365-Video-ca1cc1a9-a615-46e1-b6a3-40dbd99939a6) é um portal empresarial que fornece às organizações um destino altamente seguro e em toda a organização para postagem, compartilhamento e descoberta de conteúdo de vídeo. No Vídeo do Office 365, os vídeos de cada locatário são mantidos isolados e criptografados em todos os locais e estão disponíveis apenas para usuários autenticados que têm acesso e permissões para os vídeos da organização. O Vídeo do Office 365 usa uma combinação de tecnologias para fazer isso:

- O SharePoint Online é usado para armazenar o arquivo de vídeo e os metadados (título do vídeo, descrição etc.). Ele também fornece a camada de segurança e conformidade (incluindo autenticação) e os recursos de pesquisa.
- Os Serviços de Mídia do Azure fornece transcodificação, streaming adaptável, entrega segura (usando criptografia AES) e recursos em miniatura.

Os Serviços de Mídia do [Azure](https://azure.microsoft.com/services/media-services/) são uma oferta de plataforma como serviço para permitir fluxos de trabalho de mídia de ponta a ponta na nuvem. A plataforma fornece uma API REST para carregamento, codificação, criptografia (com PlayReady) e entrega de mídia por meio de datacenters do Azure em todo o mundo.

Todos os carregamentos para o Vídeo do Office 365 ocorrem via HTTPS. Quando um arquivo de vídeo é carregado, ele é armazenado no SharePoint Online e uma cópia do arquivo é enviada por meio de um canal criptografado para os Serviços de Mídia do Azure. Os Serviços de Mídia do Azure transcodificam o vídeo em vários formatos otimizados para a experiência de visualização (por exemplo, celular, baixa largura de banda, largura de banda alta etc.). Esses arquivos, juntamente com o arquivo original adquirido durante o upload, são armazenados no armazenamento do Blob do Azure. Os arquivos são criptografados usando AES 128 por algoritmo de empacotamento de Criptografia Comum MPEG (ou uma versão anterior do PlayReady) para reprodução e criptografados usando a criptografia de armazenamento AES 256 antes de serem armazenados no armazenamento de Blob do Azure. (Usando o SDK do Cliente do Azure Media Services, os clientes podem controlar qual criptografia é usada. Por exemplo, um cliente pode aplicar a criptografia de armazenamento dos Serviços de Mídia do Azure (AES 256) a um ativo de mídia de alto valor antes de carregar o armazenamento de Blob do Azure.)

Os Serviços de Mídia do Azure também geram uma miniatura para o vídeo, que ele transmite junto com metadados em miniatura para o SharePoint Online por meio de um canal criptografado.
