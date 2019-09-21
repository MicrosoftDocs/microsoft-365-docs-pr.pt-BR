---
title: Tipos de arquivo com suporte na descoberta eletrônica avançada
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 3dbebb20d179f78e97a8ae18fb810a8cb53c45ed
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37073096"
---
# <a name="supported-file-types-in-advanced-ediscovery"></a>Tipos de arquivo com suporte na descoberta eletrônica avançada

A descoberta eletrônica avançada oferece suporte a vários tipos de arquivo para vários níveis diferentes, que são descritos na tabela a seguir. Essa lista não é finalizada e adicionaremos novos tipos de arquivos conforme continuamos com o teste de validação. As tabelas indicam se um tipo de arquivo é suportado para a extração de texto (OCR para imagens), visível no visualizador nativo e também suporte no Visualizador de anotações na descoberta eletrônica avançada.

## <a name="archive--container"></a>Arquivo morto/contêiner

| Tipo MIME | Identificação de arquivo | Extração de metadados | Extração de contêiner | Extensões possíveis |
| :- |  :- |  :- |  :- |  :- |
| aplicativo/x-7z-compactado | Sim | Sim | Sim | .7z |
| application/x-rar-compactado | Sim | Sim | Sim | . rar |
| application/x-tar | Sim | Sim | Sim | . tar |
| aplicativo/zip | Sim | Sim | Sim | . zip |
||||||||

## <a name="database"></a>Banco de dados

| Tipo MIME | Identificação de arquivo | Extração de metadados | Extração de texto | Visualizador nativo | Visualizador de anotações | Extensões possíveis |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| application/x-Msaccess | Sim | Sim | Sim | Não | Não | . mdb |
||||||||

## <a name="email"></a>Email

| Tipo MIME | Identificação de arquivo | Extração de metadados | Extração de texto | Visualizador nativo | Visualizador de anotações | Extensões possíveis |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| application/vnd. MS-Outlook | Sim | Sim | Sim | Sim | Sim | . msg |
| mensagem/RFC822 | Sim | Sim | Sim | Sim | Sim | . eml |
| texto/vCard-contato | Sim | Sim | Sim | Sim | Sim | . vcf |
||||||||

## <a name="email-container"></a>Contêiner de email

| Tipo MIME | Identificação de arquivo | Extração de metadados | Extração de contêiner | Extensões possíveis |
| :- |  :- |  :- |  :- |  :- |
| aplicativo/mbox | Sim | Sim | Sim | .mbox |
| application/vnd. MS-Outlook-PST | Sim | Sim | Sim | . pst |
||||||||

## <a name="html"></a>HTML

| Tipo MIME | Identificação de arquivo | Extração de metadados | Extração de texto | Visualizador nativo | Visualizador de anotações | Extensões possíveis |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| aplicativo/XHTML + XML | Sim | Sim | Sim | Sim | Sim | . XHTML |
| aplicativo/XML | Sim | Sim | Sim | Sim | Sim | . xml |
| texto/HTML | Sim | Sim | Sim | Sim | Sim | . htm;. html;. shtml |
||||||||

## <a name="image"></a>Image

| Tipo MIME | Identificação de arquivo | Extração de metadados | Extração de texto OCR | Visualizador nativo | Visualizador de anotações | Extensões possíveis |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| imagem/BMP | Sim | Sim | Sim | Sim | Sim | .bmp |
| imagem/EMF | Sim | Sim | Sim | Sim | Sim | . EMF |
| image/gif | Sim | Sim | Sim | Sim | Sim | .gif |
| image/jpeg | Sim | Sim | Sim | Sim | Sim | . jpeg;. jpg |
| image/png | Sim | Sim | Sim | Sim | Sim | .png |
| Imagem/SVG + XML | Sim | Sim | Sim | Sim | Não | . svg |
| imagem/TIFF | Sim | Sim | Sim | Sim | Sim | . tif |
| Image/vnd. dwg | Sim | Sim | Sim | Sim | Sim | . dwg;. DXF |
| imagem/WMF | Sim | Sim | Sim | Sim | Sim | . wmf |
||||||||

## <a name="microsoft-excel"></a>Microsoft Excel

| Tipo MIME | Identificação de arquivo | Extração de metadados | Extração de texto | Visualizador nativo | Visualizador de anotações | Extensões possíveis |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| application/vnd. MS-Excel | Sim | Sim | Sim | Sim | Sim | . dat;. xls |
| application/vnd. MS-Excel. Sheet. Binary. macroenabled. 12 | Sim | Sim | Sim | Sim | Não | . xlsb |
| application/vnd. MS-Excel. Sheet. macroenabled. 12 | Sim | Sim | Sim | Sim | Sim | . xlsm |
| application/vnd. MS-Excel. Template. macroenabled. 12 | Sim | Sim | Sim | Não | Não | . xltm |
| application/vnd.openxmlformats-officedocument.spreadsheetml.sheet | Sim | Sim | Sim | Sim | Sim | . xlsx |
| application/vnd. openxmlformats-officeDocument. SpreadsheetML. Template | Sim | Sim | Sim | Sim | Sim | . xltx |
||||||||

## <a name="microsoft-powerpoint"></a>Microsoft Powerpoint

| Tipo MIME | Identificação de arquivo | Extração de metadados | Extração de texto | Visualizador nativo | Visualizador de anotações | Extensões possíveis |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| application/vnd. ms-PowerPoint | Sim | Sim | Sim | Sim | Sim | . pot;. PPS;. ppt |
| application/vnd.openxmlformats-officedocument.presentationml.presentation | Sim | Sim | Sim | Sim | Sim | . pptx |
| application/vnd. openxmlformats-officeDocument. presentationml. slideshow | Sim | Sim | Sim | Sim | Sim | . ppsx |
| application/vnd. openxmlformats-officeDocument. presentationml. Template | Sim | Sim | Sim | Sim | Sim | . potx |
||||||||

## <a name="microsoft-publisher"></a>Microsoft Publisher

| Tipo MIME | Identificação de arquivo | Extração de metadados | Extração de texto | Visualizador nativo | Visualizador de anotações | Extensões possíveis |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| aplicativo/x-mspublisher | Sim | Sim | Sim | Sim | Sim | . pub |
||||||||

## <a name="microsoft-visio"></a>Microsoft Visio

| Tipo MIME | Identificação de arquivo | Extração de metadados | Extração de texto | Visualizador nativo | Visualizador de anotações | Extensões possíveis |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| application/vnd. MS-Visio. Drawing | Sim | Sim | Sim | Sim | Não |  |
| application/vnd. Visio | Sim | Sim | Sim | Sim | Sim | . vsd |
||||||||

## <a name="microsoft-word"></a>Microsoft Word

| Tipo MIME | Identificação de arquivo | Extração de metadados | Extração de texto | Visualizador nativo | Visualizador de anotações | Extensões possíveis |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| application/msword | Sim | Sim | Sim | Sim | Sim | . dat;. doc |
| Application/RTF | Sim | Sim | Sim | Sim | Sim | . doc;. rtf |
| application/vnd. MS-Word. Document. macroenabled. 12 | Sim | Sim | Sim | Sim | Sim | .docm |
| application/vnd. MS-Word. Template. macroenabled. 12 | Sim | Sim | Sim | Sim | Sim | . dotm |
| application/vnd.openxmlformats-officedocument.wordprocessingml.document | Sim | Sim | Sim | Sim | Sim | . docx |
| application/vnd. openxmlformats-officeDocument. WordprocessingML. Template | Sim | Sim | Sim | Sim | Sim | . dotx |
||||||||

## <a name="microsoft-works"></a>Microsoft Works

| Tipo MIME | Identificação de arquivo | Extração de metadados | Extração de texto | Visualizador nativo | Visualizador de anotações | Extensões possíveis |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| application/vnd. ms-Works-SS | Sim | Sim | Não | Não | Não | . WPS |
| application/vnd. ms-Works-wp | Sim | Sim | Não | Não | Não | . WPS |
||||||||

## <a name="open-document-format"></a>Formato de documento aberto

| Tipo MIME | Identificação de arquivo | Extração de metadados | Extração de texto | Visualizador nativo | Visualizador de anotações | Extensões possíveis |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| application/vnd. Oasis. OpenDocument. Text | Sim | Sim | Sim | Sim | Sim | . odt |
||||||||

## <a name="other"></a>Other

| Tipo MIME | Identificação de arquivo | Extração de metadados | Extração de texto | Visualizador nativo | Visualizador de anotações | Extensões possíveis |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| application/json | Sim | Sim | Sim | Sim | Sim | n/d |
| application/vnd. ms-Graph | Sim | Sim | Não | Não | Não |  |
| aplicativo/winhlp | Sim | Sim | Não | Não | Não | . hlp |
| aplicativo/x-TNEF | Sim | Sim | Não | Não | Não |  |
||||||||

## <a name="plain-text"></a>Texto simples

| Tipo MIME | Identificação de arquivo | Extração de metadados | Extração de texto | Visualizador nativo | Visualizador de anotações | Extensões possíveis |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| texto/CSV | Sim | Sim | Sim | Sim | Sim | . csv |
| texto/simples | Sim | Sim | Sim | Sim | Sim | . con;. css;. csv;. dat;. pl;. txt |
||||||||

## <a name="portable-document-format"></a>Formato de documento portátil

| Tipo MIME | Identificação de arquivo | Extração de metadados | Extração de texto | Visualizador nativo | Visualizador de anotações | Extensões possíveis |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| application/pdf | Sim | Sim | Sim | Sim | Sim | .pdf |
||||||||

## <a name="word-perfect"></a>Word Perfect

| Tipo MIME | Identificação de arquivo | Extração de metadados | Extração de texto | Visualizador nativo | Visualizador de anotações | Extensões possíveis |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| application/vnd. WordPerfect; versão = 5.0 | Sim | Sim | Sim | Não | Não | . wpd |
| application/vnd. WordPerfect; versão = 5.1 | Sim | Sim | Sim | Não | Não | . wpd |
| application/vnd. WordPerfect; versão = 6. x | Sim | Sim | Sim | Não | Não | . wpd |
||||||||

## <a name="word-pro"></a>Word Pro

| Tipo MIME | Identificação de arquivo | Extração de metadados | Extração de texto | Visualizador nativo | Visualizador de anotações | Extensões possíveis |
| :- |  :- |  :- |  :- |  :- |  :- |  :- |
| application/vnd. Lotus-Wordpro | Sim | Sim | Não | Não | Não | . lwp |
||||||||
