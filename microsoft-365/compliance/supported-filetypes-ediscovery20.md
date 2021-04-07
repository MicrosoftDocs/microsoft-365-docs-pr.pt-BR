---
title: Tipos de arquivo com suporte na Descoberta Avançada da Descoberta
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
description: Uma lista de tipos de arquivos com suporte na Descoberta eDiscoverIa Avançada do Microsoft 365, incluindo tipos de arquivo de imagem suportados pela funcionalidade OCR na Descoberta eDiscoveria Avançada.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 719a0474d45825114cf4ea3fbd19082bb8df7622
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599826"
---
# <a name="supported-file-types-in-advanced-ediscovery"></a>Tipos de arquivo com suporte na Descoberta Avançada da Descoberta

A Descoberta Avançada oferece suporte a muitos tipos de arquivo em vários níveis diferentes. Os tipos de arquivos de suporte são descritos nas tabelas a seguir neste artigo. Esta lista não foi finalizada e adicionaremos novos tipos de arquivo à medida que continuarmos nossos testes de validação. Essas tabelas indicam se há suporte para um tipo de arquivo para extração de texto (e reconhecimento óptico de caracteres ou extração de texto OCR para arquivos de imagem), visualização no visualizador nativo e também suporte no visualizador Anotado na Descoberta Avançada.

## <a name="archive--container"></a>Arquivo morto/contêiner

| Tipo mime | Identificação de arquivo | Extração de metadados | Extração de contêiner | Extensões Possíveis |
|:---- |:---- |:---- |:---- |:---- |
|application/x-7z-compressed | Sim | Sim | Sim | .7z |
|application/x-rar-compressed | Sim | Sim | Sim | .rar |
|application/x-tar | Sim | Sim | Sim | .tar |
|application/zip | Sim | Sim | Sim | .zip |
||||||||

## <a name="audio--video"></a>Áudio/vídeo

| Tipo mime | Identificação de arquivo | Extração de metadados | Extração de texto | Visualizador nativo | Visualizador de anotações | Extensões Possíveis |
|:------| :------| :------| :------| :------| :------| :------|
| application/mp4 | Sim | Sim | Não | Sim | Não | .f4v; .m4a; .m4v; .mp4; .mp4v; .mpeg; .mpeg4 |
|audio/mpeg | Sim | Sim | Não | Sim | Não | .mpeg |
|video/3gpp | Sim | Sim | Não | Sim | Não | .3gp |
|video/3gpp2 | Sim | Sim | Não | Sim | Não | .3g2; .3gp2 |
|vídeo/quicktime | Sim | Sim | Não | Sim | Não | .moov; .mov; .qt |
|video/x-m4v | Sim | Sim | Não | Sim | Não | .m4v |
||||||||

## <a name="database"></a>Database

| Tipo mime | Identificação de arquivo | Extração de metadados | Extração de texto | Visualizador nativo | Visualizador de anotações | Extensões Possíveis |
|:------| :------| :------| :------| :------| :------| :------|
|application/x-msaccess | Sim | Sim | Sim | Não | Não | .mdb |
||||||||

## <a name="email"></a>Email

|Tipo mime |Identificação de arquivo |Extração de metadados |Extração de texto |Visualizador nativo |Visualizador de anotações | Extensões Possíveis |
|:------| :------| :------| :------| :------| :------| :------|
|application/vnd.ms-outlook | Sim | Sim | Sim | Sim | Sim | .msg |
|message/rfc822 | Sim | Sim | Sim | Sim | Sim | .eml |
|text/vcard-contact | Sim | Sim | Sim | Sim | Sim | .vcf |
||||||||

## <a name="email-container"></a>Contêiner de Email

| Tipo mime | Identificação de arquivo | Extração de metadados | Extração de contêiner | Extensões Possíveis |
|:------| :------| :------| :------| :------|
|application/mbox | Sim | Sim | Sim | .mbox |
|application/vnd.ms-outlook-pst | Sim | Sim | Sim | .pst |
||||||||

## <a name="html"></a>HTML

| Tipo mime | Identificação de arquivo | Extração de metadados | Extração de texto | Visualizador nativo | Visualizador de anotações | Extensões Possíveis |
|:------| :------| :------| :------| :------| :------| :------|
|application/xhtml+xml | Sim | Sim | Sim | Sim | Sim | .xhtml |
|application/xml | Sim | Sim | Sim | Sim | Sim | .xml |
|text/html | Sim | Sim | Sim | Sim | Sim | .htm; .html; .shtml |
||||||||

## <a name="image"></a>Image

|Tipo mime |Identificação de arquivo |Extração de metadados |Extração de texto OCR |Visualizador nativo |Visualizador de anotações |Extensões Possíveis |
|:------| :------| :------| :------| :------| :------| :------|
|image/bmp | Sim | Sim | Sim | Sim | Sim | .bmp |
|image/emf | Sim | Sim | Sim | Sim | Sim | .emf |
|image/gif | Sim | Sim | Sim | Sim | Sim | .gif |
|image/jpeg | Sim | Sim | Sim | Sim | Sim | .jpeg; .jpg |
|image/png | Sim | Sim | Sim | Sim | Sim | .png |
|image/svg+xml | Sim | Sim | Sim | Sim | Não | .svg |
|image/tiff | Sim | Sim | Sim | Sim | Sim | .tif |
|image/vnd.dwg | Sim | Sim | Sim | Sim | Sim | .dwg; .dxf |
|image/wmf | Sim | Sim | Sim | Sim | Sim | .wmf |
||||||||

## <a name="microsoft-excel"></a>Microsoft Excel

| Tipo mime | Identificação de arquivo | Extração de metadados | Extração de texto | Visualizador nativo | Visualizador de anotações | Extensões Possíveis |
|:------| :------| :------| :------| :------| :------| :------|
|application/vnd.ms-excel | Sim | Sim | Sim | Sim | Sim | .dat; .xls |
|application/vnd.ms-excel.sheet.binary.macroenabled.12 | Sim | Sim | Sim | Sim | Não | .xlsb |
|application/vnd.ms-excel.sheet.macroenabled.12 | Sim | Sim | Sim | Sim | Sim | .xlsm |
|application/vnd.ms-excel.template.macroenabled.12 | Sim | Sim | Sim | Não | Não | .xltm |
|application/vnd.openxmlformats-officedocument.spreadsheetml.sheet | Sim | Sim | Sim | Sim | Sim | .xlsx |
|application/vnd.openxmlformats-officedocument.spreadsheetml.template | Sim | Sim | Sim | Sim | Sim | .xltx |
||||||||

## <a name="microsoft-onenote"></a>Microsoft OneNote

| Tipo mime | Identificação de arquivo | Extração de metadados | Extração de texto | Visualizador nativo | Visualizador de anotações | Extensões Possíveis |
|:------| :------| :------| :------| :------| :------| :------|
|application/onenote | Sim | Sim | Sim | Não | Não | .one |
||||||||

## <a name="microsoft-powerpoint"></a>Microsoft PowerPoint

| Tipo mime | Identificação de arquivo | Extração de metadados | Extração de texto | Visualizador nativo | Visualizador de anotações | Extensões Possíveis |
|:------| :------| :------| :------| :------| :------| :------|
|application/vnd.ms-powerpoint | Sim | Sim | Sim | Sim | Sim | .pot; .pps; .ppt |
|application/vnd.openxmlformats-officedocument.presentationml.presentation | Sim | Sim | Sim | Sim | Sim | .pptx |
|application/vnd.openxmlformats-officedocument.presentationml.slideshow | Sim | Sim | Sim | Sim | Sim | .ppsx |
|application/vnd.openxmlformats-officedocument.presentationml.template | Sim | Sim | Sim | Sim | Sim | .potx |
||||||||

## <a name="microsoft-project"></a>Microsoft Project

| Tipo mime | Identificação de arquivo | Extração de metadados | Extração de texto | Visualizador nativo | Visualizador de anotações | Extensões Possíveis |
|:------| :------| :------| :------| :------| :------| :------|
|application/vnd.ms-project | Sim | Sim | Sim | Não | Sim | .mpp |
||||||||

## <a name="microsoft-publisher"></a>Microsoft Publisher

|Tipo mime | Identificação de arquivo | Extração de metadados | Extração de texto | Visualizador nativo | Visualizador de anotações | Extensões Possíveis |
|:------| :------| :------| :------| :------| :------| :------|
|application/x-mspublisher | Sim | Sim | Sim | Sim | Sim | .pub |
||||||||

## <a name="microsoft-visio"></a>Microsoft Visio

| Tipo mime | Identificação de arquivo | Extração de metadados | Extração de texto | Visualizador nativo | Visualizador de anotações | Extensões Possíveis |
|:------| :------| :------| :------| :------| :------| :------|
|application/vnd.ms-visio.drawing | Sim | Sim | Sim | Sim | Não |  |
|application/vnd.visio | Sim | Sim | Sim | Sim | Sim | .vsd |
||||||||

## <a name="microsoft-word"></a>Microsoft Word

| Tipo mime | Identificação de arquivo | Extração de metadados | Extração de texto | Visualizador nativo | Visualizador de anotações | Extensões Possíveis |
|:------| :------| :------| :------| :------| :------| :------|
|application/msword | Sim | Sim | Sim | Sim | Sim | .dat; .doc |
| application/rtf | Sim | Sim | Sim | Sim | Sim | .doc; .rtf |
|application/vnd.ms-word.document.macroenabled.12 | Sim | Sim | Sim | Sim | Sim | .docm |
|application/vnd.ms-word.template.macroenabled.12 | Sim | Sim | Sim | Sim | Sim | .dotm |
|application/vnd.openxmlformats-officedocument.wordprocessingml.document | Sim | Sim | Sim | Sim | Sim | .docx |
|application/vnd.openxmlformats-officedocument.wordprocessingml.template | Sim | Sim | Sim | Sim | Sim | .dotx |
||||||||

## <a name="microsoft-works"></a>Microsoft Works

| Tipo mime | Identificação de arquivo | Extração de metadados | Extração de texto | Visualizador nativo | Visualizador de anotações | Extensões Possíveis |
|:------| :------| :------| :------| :------| :------| :------|
|application/vnd.ms-works-ss | Sim | Sim | Não | Não | Não | .wps |
|application/vnd.ms-works-wp | Sim | Sim | Não | Não | Não | .wps |
||||||||

## <a name="open-document-format"></a>Abrir Formato de Documento

| Tipo mime | Identificação de arquivo | Extração de metadados | Extração de texto | Visualizador nativo | Visualizador de anotações | Extensões Possíveis |
|:------| :------| :------| :------| :------| :------| :------|
|application/vnd.oasis.opendocument.text | Sim | Sim | Sim | Sim | Sim | .odt |
||||||||

## <a name="other"></a>Outros

| Tipo mime | Identificação de arquivo | Extração de metadados | Extração de texto | Visualizador nativo | Visualizador de anotações | Extensões Possíveis |
|:------| :------| :------| :------| :------| :------| :------|
|application/json | Sim | Sim | Sim | Sim | Sim | n/d |
|application/vnd.ms-graph | Sim | Sim | Não | Não | Não |  |
|application/winhlp | Sim | Sim | Não | Não | Não | .hlp |
|application/x-tnef | Sim | Sim | Não | Não | Não |  |
||||||||

## <a name="plain-text"></a>Texto simples

| Tipo mime | Identificação de arquivo | Extração de metadados | Extração de texto | Visualizador nativo | Visualizador de anotações | Extensões Possíveis |
|:------| :------| :------| :------| :------| :------| :------|
|text/csv | Sim | Sim | Sim | Sim | Sim | .csv |
|texto/simples | Sim | Sim | Sim | Sim | Sim | .con; .css; .csv; .dat; .pl; .txt |
||||||||

## <a name="portable-document-format"></a>Formato de documento portátil

| Tipo mime | Identificação de arquivo | Extração de metadados | Extração de texto | Visualizador nativo | Visualizador de anotações | Extensões Possíveis |
|:------| :------| :------| :------| :------| :------| :------|
|application/pdf | Sim | Sim | Sim | Sim | Sim | .pdf |
||||||||

## <a name="word-perfect"></a>Word Perfect

| Tipo mime | Identificação de arquivo | Extração de metadados | Extração de texto | Visualizador nativo | Visualizador de anotações | Extensões Possíveis |
|:------| :------| :------| :------| :------| :------| :------|
|application/vnd.wordperfect; version=5.0 | Sim | Sim | Sim | Não | Não | .wpd |
|application/vnd.wordperfect; version=5.1 | Sim | Sim | Sim | Não | Não | .wpd |
|application/vnd.wordperfect; version=6.x | Sim | Sim | Sim | Não | Não | .wpd |
||||||||

## <a name="word-pro"></a>Word Pro

| Tipo mime | Identificação de arquivo | Extração de metadados | Extração de texto | Visualizador nativo | Visualizador de anotações | Extensões Possíveis |
|:------| :------| :------| :------| :------| :------| :------|
|application/vnd.lotus-wordpro | Sim | Sim | Não | Não | Não | .lwp |
||||||||
