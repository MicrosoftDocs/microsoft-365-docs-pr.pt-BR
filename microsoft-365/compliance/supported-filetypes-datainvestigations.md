---
title: Tipos de arquivo com suporte em investigações de dados (versão prévia)
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Uma tabela que lista os tipos de arquivo com suporte e quais visualizadores eles podem ser exibidos no para investigações de dados (visualização).
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: dc4b8efb7c4212261e16f1e307c6ca05fea064ec
ms.sourcegitcommit: 9f5b136b96b3af4db4cc6f5b1f35130ae60d6b12
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47817134"
---
# <a name="supported-file-types-in-data-investigations-preview"></a>Tipos de arquivo com suporte em investigações de dados (versão prévia)

A ferramenta de investigações de dados (visualização) oferece suporte a vários tipos de arquivos de várias maneiras diferentes, que são descritas na tabela a seguir. Essa lista não é finalizada e adicionaremos novos tipos de arquivos conforme continuamos com o teste de validação. A tabela também indica se um tipo de arquivo pode ser exibido nos visualizadores disponíveis quando você estiver revisando evidências.

| Tipo MIME | Classe de arquivo | Visualizador nativo | Visualizador de texto | Visualizador de anotações | Extração de contêiner | Extensões |
|:------|:------|:------|:------|:------|:------|:------|
|application/msword | Documento | Sim | Sim | Sim | Não | . doc;. dat |
|application/pdf | Documento | Sim | Sim | Sim | Não | .pdf |
|Application/RTF | Documento | Sim | Sim | Sim | Não | . rtf;. doc |
|application/vnd. MS-Excel | Documento | Sim | Sim | Sim | Não | . xls;. dat |
|application/vnd. MS-Excel. Sheet. Binary. macroenabled. 12 | Formato de produtividade/documento aberto | Sim | Sim | Não | Não | . xlsb |
|application/vnd. MS-Excel. Sheet. macroenabled. 12 | Documento | Sim | Sim | Sim | Não | . xlsm |
|application/vnd. MS-Excel. Template. macroenabled. 12 | Formato de produtividade/documento aberto | Não | Sim | Não | Não | . xltm |
|application/vnd. MS-Outlook | Produtividade | Não | Não | Não | Não | . msg |
|application/vnd. MS-Outlook-PST | Produtividade/colaboração | Não | Não | Não | Sim | . pst |
|application/vnd. ms-PowerPoint | Documento | Sim | Sim | Sim | Não | . ppt;. PPS;. pot |
|Application/vnd.ms-word.document. macroenabled. 12 | Documento | Sim | Sim | Sim | Não | .docm |
|application/vnd. MS-Word. Template. macroenabled. 12 | Documento | Sim | Sim | Sim | Não | . dotm |
|application/vnd. Oasis. OpenDocument. Text | Documento | Sim | Sim | Sim | Não | ODT  |
|application/vnd.openxmlformats-officedocument.presentationml.presentation | Documento | Sim | Sim | Sim | Não | . pptx |
|application/vnd. openxmlformats-officeDocument. presentationml. slideshow | Formato de produtividade/documento aberto | Sim | Sim | Sim | Não | . ppsx |
|application/vnd. openxmlformats-officeDocument. presentationml. Template | Documento | Sim | Sim | Sim | Não | . potx |
| planilha apadsheetml. | Documento | Sim | Sim | Sim | Não | . xlsx |
|application/vnd. openxmlformats-officeDocument. SpreadsheetML. Template | Documento | Sim | Sim | Sim | Não | . xltx |
|aplicativo/vnd.openxmlformats-officedocument.wordproessingml.document | Documento | Sim | Sim | Sim | Não | . docx |
|application/vnd. openxmlformats-officeDocument. WordprocessingML. Template | Documento | Sim | Sim | Sim | Não | . dotx |
|application/vnd. Visio | Documento | Sim | Sim | Sim | Não | . vsd |
|aplicativo/x-7z-compactado | Arquivo morto/contêiner | Não | Não | Não | Sim | .7z |
|aplicativo/XHTML + XML | Documento | Sim | Sim | Sim | Não | . XHTML |
|aplicativo/XML | Documento | Sim | Sim | Sim | Não | . xml |
|application/x-Msaccess | Documento | Sim | Sim | Sim | Não | . mdb |
|aplicativo/x-mspublisher | Documento | Sim | Sim | Sim | Não | . pub |
|application/x-rar-compactado | Arquivo morto/contêiner | Não | Não | Não | Sim | . rar |
| aplicativo/zip | Arquivo morto/contêiner | Não | Não | Não | Sim | .zip |
|imagem/BMP | Imagem | Sim | Sim | Sim | Não | .bmp |
|imagem/EMF | Imagem | Sim | Sim | Sim | Não | . EMF |
|image/gif | Documento | Sim | Sim | Sim | Não | .gif |
|image/jpeg | Imagem | Sim | Sim | Sim | Não | . jpg;. jpeg;. dat;. jpgt |
|image/png | Imagem | Sim | Sim | Sim | Não | .png |
|imagem/TIFF | Imagem | Sim | Sim | Sim | Não | . tif |
|Image/vnd. dwg | Documento | Sim | Sim | Sim | Não | . dwg;. DXF; |
|imagem/WMF | Documento | Sim | Sim | Sim | Não | . wmf |
| mensagem/RFC822 | Produtividade/colaboração | Não | Não | Não | Não | .eml |
|texto/CSV | Documento | Sim | Sim | Sim | Não | . csv |
|texto/HTML | Documento | Sim | Sim | Sim | Não | . html;. shtml;. htm |
|texto/simples | Documento | Sim | Sim | Sim | Não | . txt;. css;. con;. pl;. csv;. dat |
|texto/vCard-contato | Documento | Sim | Sim | Sim | Não | . vcf |
||||||||
