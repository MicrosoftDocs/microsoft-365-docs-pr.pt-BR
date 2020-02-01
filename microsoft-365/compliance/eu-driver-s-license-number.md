---
title: Número da carteira de motorista da UE
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: 8/17/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: Este tópico mostra o que uma política de prevenção de perda de dados (DLP) procura quando detecta o tipo de informação confidencial do número de licença do driver da UE. Esse tipo de informação confidencial define diferentes padrões, palavras-chave e outras evidências para cada país.
ms.openlocfilehash: c54fcefcda08d0bc2ec500d25c74bb5789e27398
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41592652"
---
# <a name="eu-drivers-license-number"></a>Número da carteira de motorista da UE

Este tópico mostra o que uma política de prevenção de perda de dados (DLP) procura quando detecta o tipo de informação confidencial do número de licença do driver da UE. Esse tipo de informação confidencial define diferentes padrões, palavras-chave e outras evidências para cada país.
  
## <a name="austria"></a>Áustria

### <a name="format"></a>Formatar

Oito dígitos sem espaços e delimitadores
  
### <a name="pattern"></a>Padrão

Oito dígitos
  
### <a name="checksum"></a>Soma de verificação

Não
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A expressão `Regex_austria_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_austria_eu_driver's_license_number` chave de foi encontrada. 
    
```
<!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Match idRef="Keywords_austria_eu_driver's_license_number" />
        </Pattern>
    </Entity>

```

### <a name="keywords"></a>Palavras-chave

| |
|**Keywords_austria_eu_driver ' s_license_number**|
|:-----|
|distribuição #  <br/> driver license  <br/> número de carteira de motorista  <br/> licença de driver  <br/> drivers driver'lic.  <br/> drivers license  <br/> driver's licence  <br/> driver's license  <br/> número da carteira de motorista  <br/> número de licença do driver  <br/>  número da licença de dirigir  <br/> dlno #  <br/> fuhrerschein  <br/> fuhrerschein republik osterreich  <br/> |
   
## <a name="belgium"></a>Bélgica

### <a name="format"></a>Formatar

10 dígitos sem espaços e delimitadores
  
### <a name="pattern"></a>Padrão

10 dígitos
  
### <a name="checksum"></a>Soma de verificação

Não
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A expressão `Regex_belgium_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_belgium_eu_driver's_license_number` chave de foi encontrada. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Match idRef="Keywords_belgium_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a>Palavras-chave

| |
|**Keywords__belgium_eu_driver ' s_license_number**|
|:-----|
|distribuição #  <br/> driver license  <br/> número de carteira de motorista  <br/> licença de driver  <br/> drivers driver'lic.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> número da carteira de motorista  <br/> número de licença do driver  <br/> dlno #  <br/> rijbewijs  <br/> rijbewijsnummer  <br/> führerscheinnummer  <br/> fuhrerscheinnummer  <br/> fuehrerscheinnummer  <br/> führerschein- nr  <br/> fuehrerschein- Nr  <br/> fuehrerschein- nr  <br/> |
   
## <a name="bulgaria"></a>Bulgária

### <a name="format"></a>Formatar

Nove dígitos sem espaços e delimitadores
  
### <a name="pattern"></a>Padrão

Nove dígitos
  
### <a name="checksum"></a>Soma de verificação

Não
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A expressão `Regex_bulgaria_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_bulgaria_eu_driver's_license_number` chave de foi encontrada. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
             <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
        </Pattern> 
</Entity>    

```

### <a name="keywords"></a>Palavras-chave

| |
|**Keywords_bulgaria_eu_driver ' s_license_number**|
|:-----|
|distribuição #  <br/> driver license  <br/> número de carteira de motorista  <br/> licença de driver  <br/> drivers driver'lic.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> número da carteira de motorista  <br/> número de licença do driver  <br/> número da licença de dirigir  <br/> dlno #  <br/> свидетелство за управление на мпс  <br/> свидетелство за управление на моторно превозно средство  <br/> сумпс  <br/> шофьорска книжка  <br/> |
   
## <a name="croatia"></a>Croácia

### <a name="format"></a>Formatar

Oito dígitos sem espaços e delimitadores
  
### <a name="pattern"></a>Padrão

Oito dígitos
  
### <a name="checksum"></a>Soma de verificação

Não
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A expressão `Regex_croatia_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_croatia_eu_driver's_license_number` chave de foi encontrada. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Match idRef="Keywords_croatia_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a>Palavras-chave

| |
|**Keywords_croatia_eu_driver ' s_license_number**|
|:-----|
|distribuição #  <br/> driver license  <br/> número de carteira de motorista  <br/> licença de driver  <br/> drivers driver'lic.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> número da carteira de motorista  <br/> número de licença do driver  <br/> número da licença de dirigir  <br/> dlno #  <br/> vozačka dozvola  <br/> |
   
## <a name="cyprus"></a>Chipre

### <a name="format"></a>Formatar

12 dígitos sem espaços e delimitadores
  
### <a name="pattern"></a>Padrão

12 dígitos
  
### <a name="checksum"></a>Soma de verificação

Não
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A expressão `Regex_cyprus_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_cyprus_eu_driver's_license_number` chave de foi encontrada. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

| |
|**Keywords_cyprus_eu_driver ' s_license_number**|
|:-----|
|distribuição #  <br/> driver license  <br/> número de carteira de motorista  <br/> licença de driver  <br/> drivers driver'lic.  <br/> drivers license  <br/> drivers licence  <br/> número da carteira de motorista  <br/> número de licença do driver  <br/> número da licença de dirigir  <br/> dlno #  <br/> άδεια οδήγησης  <br/> |
   
## <a name="czech-republic"></a>República Tcheca

### <a name="format"></a>Formatar

Duas letras seguidas por seis dígitos
  
### <a name="pattern"></a>Padrão

Oito letras e dígitos:
  
- Duas letras (não diferencia maiúsculas de minúsculas)
    
- Um espaço (opcional)
    
- Seis dígitos
    
### <a name="checksum"></a>Soma de verificação

Não
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A expressão `Regex_czech_republic_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_czech_republic_eu_driver's_license_number` chave de foi encontrada. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a>Palavras-chave

| |
|**Keywords_czech_republic_eu_driver ' s_license_number**|
|:-----|
|distribuição #  <br/> driver license  <br/> número de carteira de motorista  <br/> licença de driver  <br/> drivers driver'lic.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> número da carteira de motorista  <br/> número da carteira de motorista  <br/> número de licença do driver  <br/> número da licença de dirigir  <br/> dlno #  <br/> řidičský prúkaz  <br/> |
   
## <a name="denmark"></a>Dinamarca

### <a name="format"></a>Formatar

Oito dígitos sem espaços e delimitadores
  
### <a name="pattern"></a>Padrão

Oito dígitos
  
### <a name="checksum"></a>Soma de verificação

Sim
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A expressão `Regex_denmark_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_denmark_eu_driver's_license_number` chave de foi encontrada. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Match idRef="Keywords_denmark_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a>Palavras-chave

| |
|**Keywords_denmark_eu_driver ' s_license_number**|
|:-----|
|distribuição #  <br/> driver license  <br/> número de carteira de motorista  <br/> licença de driver  <br/> drivers driver'lic.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> número da carteira de motorista  <br/> número de licença do driver  <br/> número da licença de dirigir  <br/> dlno #  <br/> kørekort  <br/> kørekortnummer  <br/> |
   
## <a name="estonia"></a>Estônia

### <a name="format"></a>Formatar

Duas letras seguidas por seis dígitos
  
### <a name="pattern"></a>Padrão

Duas letras e seis dígitos:
  
-  As letras "ET" (não diferencia maiúsculas de minúsculas) 
    
- Seis dígitos
    
### <a name="checksum"></a>Soma de verificação

Não
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A expressão `Regex_estonia_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_estonia_eu_driver's_license_number` chave de foi encontrada. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Match idRef="Keywords_estonia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

| |
|**Keywords_estonia_eu_driver ' s_license_number**|
|:-----|
|distribuição #  <br/> driver license  <br/> número de carteira de motorista  <br/> número de carteira de motorista  <br/> licença de driver  <br/> drivers driver'lic.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> número da carteira de motorista  <br/> número da licença de dirigir  <br/> dlno #  <br/> permis de conduire  <br/> |
   
## <a name="finland"></a>Finlândia

### <a name="format"></a>Formatar

10 dígitos que contêm um hífen
  
### <a name="pattern"></a>Padrão

10 dígitos contendo um hífen:
  
-  Seis dígitos 
    
- Um hífen
    
-  Quatro dígitos 
    
### <a name="checksum"></a>Soma de verificação

Não
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A expressão `Regex_finland_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_finland_eu_driver's_license_number` chave de foi encontrada. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Match idRef="Keywords_finland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

| |
|**Keywords_finland_eu_driver ' s_license_number**|
|:-----|
|distribuição #  <br/> driver license  <br/> número de carteira de motorista  <br/> licença de driver  <br/> drivers driver'lic.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> número da carteira de motorista  <br/> número de licença do driver  <br/> número da licença de dirigir  <br/> dlno #  <br/> ajokortti  <br/> |
   
## <a name="france"></a>França

Para obter detalhes, consulte a seção "número da carteira de motorista do driver da França" em [o que os tipos de informações confidenciais procuram](what-the-sensitive-information-types-look-for.md).
  
## <a name="germany"></a>Alemanha

Para obter detalhes, consulte a seção "número da carteira de motorista do driver alemão" em [o que os tipos de informações confidenciais buscam](what-the-sensitive-information-types-look-for.md).
  
## <a name="greece"></a>Grécia

### <a name="format"></a>Formatar

Nove dígitos sem espaços e delimitadores
  
### <a name="pattern"></a>Padrão

 Nove dígitos 
  
### <a name="checksum"></a>Soma de verificação

Não
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A expressão `Regex_greece_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_greece_eu_driver's_license_number` chave de foi encontrada. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Match idRef="Keywords_greece_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

| |
|**Keywords_greece_eu_driver ' s_license_number**|
|:-----|
|dlL #  <br/> driver license  <br/> número de carteira de motorista  <br/> licença de driver  <br/> drivers driver'lic.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> número da carteira de motorista  <br/> número de licença do driver  <br/> número da licença de dirigir  <br/> dlno #  <br/> δεια οδήγησης  <br/> Adeia odigisis  <br/> |
   
## <a name="hungary"></a>Hungria

### <a name="format"></a>Formatar

Duas letras seguidas por seis dígitos
  
### <a name="pattern"></a>Padrão

Duas letras e seis dígitos:
  
-  Duas letras (não diferencia maiúsculas de minúsculas) 
    
- Seis dígitos
    
### <a name="checksum"></a>Soma de verificação

Não
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A expressão `Regex_hungary_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_hungary_eu_driver's_license_number` chave de foi encontrada. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Match idRef="Keywords_hungary_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

| |
|**Keywords_hungary_eu_driver ' s_license_number**|
|:-----|
|distribuição #  <br/> driver license  <br/> número de carteira de motorista  <br/> licença de driver  <br/> drivers driver'lic.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> número da carteira de motorista  <br/> número de licença do driver  <br/> número da licença de dirigir  <br/> dlno #  <br/> vezetoi engedely  <br/> |
   
## <a name="ireland"></a>Irlanda

### <a name="format"></a>Formatar

Seis dígitos seguidos de quatro letras
  
### <a name="pattern"></a>Padrão

Seis dígitos e quatro letras:
  
- Seis dígitos
    
- Quatro letras (não diferencia maiúsculas de minúsculas)
    
### <a name="checksum"></a>Soma de verificação

Não
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A expressão `Regex_ireland_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_ireland_eu_driver's_license_number` chave de foi encontrada. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Match idRef="Keywords_ireland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

| |
|**Keywords_ireland_eu_driver ' s_license_number**|
|:-----|
|distribuição #  <br/> driver license  <br/> número de carteira de motorista  <br/> licença de driver  <br/> drivers driver'lic.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> número da carteira de motorista  <br/> número de licença do driver  <br/> número da licença de dirigir  <br/> dlno #  <br/> ceadúnas tiomána  <br/> |
   
## <a name="italy"></a>Itália

Para obter detalhes, consulte a seção "número da carteira de motorista do driver da Itália" em [o que os tipos de informações confidenciais procuram](what-the-sensitive-information-types-look-for.md).
  
## <a name="latvia"></a>Letônia

### <a name="format"></a>Formatar

Três letras seguidas por seis dígitos
  
### <a name="pattern"></a>Padrão

Três letras e seis dígitos:
  
-  Três letras (não diferencia maiúsculas de minúsculas) 
    
- Seis dígitos
    
### <a name="checksum"></a>Soma de verificação

Não
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A expressão `Regex_latvia_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_latvia_eu_driver's_license_number` chave de foi encontrada. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Match idRef="Keywords_latvia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

| |
|**Keywords_latvia_eu_driver ' s_license_number**|
|:-----|
|distribuição #  <br/> driver license  <br/> número de carteira de motorista  <br/> licença de driver  <br/> drivers driver'lic.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> número da carteira de motorista  <br/> número de licença do driver  <br/> número da licença de dirigir  <br/> dlno #  <br/> autovadītāja apliecība  <br/> |
   
## <a name="lithuania"></a>Lituânia

### <a name="format"></a>Formatar

Oito dígitos sem espaços e delimitadores
  
### <a name="pattern"></a>Padrão

 Oito dígitos 
  
### <a name="checksum"></a>Soma de verificação

Não
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A expressão `Regex_lithuania_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_lithuania_eu_driver's_license_number` chave de foi encontrada. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

| |
|**Keywords_lithuania_eu_driver ' s_license_number**|
|:-----|
|distribuição #  <br/> driver license  <br/> número de carteira de motorista  <br/> licença de driver  <br/> drivers driver'lic.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> número da carteira de motorista  <br/> número de licença do driver  <br/> número da licença de dirigir  <br/> dlno #  <br/> vairuotojo pažymėjimas  <br/> |
   
## <a name="luxemburg"></a>Luxemburg

### <a name="format"></a>Formatar

Seis dígitos sem espaços e delimitadores
  
### <a name="pattern"></a>Padrão

 Seis dígitos 
  
### <a name="checksum"></a>Soma de verificação

Não
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A expressão `Regex_luxemburg_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_luxemburg_eu_driver's_license_number` chave de foi encontrada. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

| |
|**Keywords_luxemburg_eu_driver ' s_license_number**|
|:-----|
|distribuição #  <br/> driver license  <br/> número de carteira de motorista  <br/> licença de driver  <br/> drivers driver'lic.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> número da carteira de motorista  <br/> número de licença do driver  <br/> número da licença de dirigir  <br/> dlno #  <br/> fahrerlaubnis  <br/> |
   
## <a name="malta"></a>Malta

### <a name="format"></a>Formatar

Combinação de dois caracteres e seis dígitos no padrão especificado
  
### <a name="pattern"></a>Padrão

Combinação de dois caracteres e seis dígitos:
  
- Dois caracteres (dígitos ou letras, não diferenciam maiúsculas de minúsculas)
    
- Um espaço (opcional)
    
- Três dígitos
    
- Um espaço (opcional)
    
- Três dígitos
    
### <a name="checksum"></a>Soma de verificação

Não
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A expressão `Regex_malta_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_malta_eu_driver's_license_number` chave de foi encontrada. 
    
```
<!-- EU Driver's License Number -->
 <Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Match idRef="Keywords_malta_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

| |
|**Keywords_malta_eu_driver ' s_license_number**|
|:-----|
|distribuição #  <br/> driver license  <br/> número de carteira de motorista  <br/> licença de driver  <br/> drivers driver'lic.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> número da carteira de motorista  <br/> número de licença do driver  <br/> número da licença de dirigir  <br/> dlno #  <br/> liċenzja tas-sewqan  <br/> |
   
## <a name="netherlands"></a>Países Baixos

### <a name="format"></a>Formatar

10 dígitos sem espaços e delimitadores
  
### <a name="pattern"></a>Padrão

10 dígitos
  
### <a name="checksum"></a>Soma de verificação

Não
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A expressão `Regex_netherlands_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_netherlands_eu_driver's_license_number` chave de foi encontrada. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

| |
|**Keywords_netherlands_eu_driver ' s_license_number**|
|:-----|
|distribuição #  <br/> driver license  <br/> número de carteira de motorista  <br/> licença de driver  <br/> drivers driver'lic.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> número da carteira de motorista  <br/> número de licença do driver  <br/> número da licença de dirigir  <br/> dlno #  <br/> permis de conduire  <br/> rijbewijs  <br/> rijbewijsnummer  <br/> |
   
## <a name="poland"></a>Polônia

### <a name="format"></a>Formatar

14 dígitos contendo 2 barras
  
### <a name="pattern"></a>Padrão

14 dígitos e 2 barras de avanço:
  
-  Cinco dígitos 
    
- Uma barra
    
- Dois dígitos
    
- Uma barra
    
- Sete dígitos
    
### <a name="checksum"></a>Soma de verificação

Não
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A expressão `Regex_poland_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_poland_eu_driver's_license_number` chave de foi encontrada. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Match idRef="Keywords_poland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

| |
|**Keywords_poland_eu_driver ' s_license_number**|
|:-----|
|distribuição #  <br/> driver license  <br/> número de carteira de motorista  <br/> licença de driver  <br/> drivers driver'lic.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> número da carteira de motorista  <br/> número de licença do driver  <br/> número da licença de dirigir  <br/> dlno #  <br/> prawo jazdy  <br/> |
   
## <a name="portugal"></a>Portugal

### <a name="format"></a>Formatar

Duas letras seguidas por sete números no padrão especificado
  
### <a name="pattern"></a>Padrão

Duas letras seguidas por sete números com caracteres especiais:
  
-  Duas letras (não diferencia maiúsculas de minúsculas) 
    
- Um hífen
    
- Seis dígitos
    
- Um espaço
    
- Um dígito
    
### <a name="checksum"></a>Soma de verificação

Não
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A expressão `Regex_portugal_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_portugal_eu_driver's_license_number` chave de foi encontrada. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Match idRef="Keywords_portugal_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

| |
|**Keywords_portugal_eu_driver ' s_license_number**|
|:-----|
|distribuição #  <br/> driver license  <br/> número de carteira de motorista  <br/> licença de driver  <br/> drivers driver'lic.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> número da carteira de motorista  <br/> número de licença do driver  <br/> número da licença de dirigir  <br/> dlno #  <br/> carteira de motorista  <br/> |
   
## <a name="romania"></a>Romênia

### <a name="format"></a>Formatar

Um caractere seguido por oito dígitos
  
### <a name="pattern"></a>Padrão

Um caractere seguido por oito dígitos:
  
-  Uma letra (não diferencia maiúsculas de minúsculas) ou dígito 
    
- Oito dígitos
    
### <a name="checksum"></a>Soma de verificação

Não
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A expressão `Regex_romania_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_romania_eu_driver's_license_number` chave de foi encontrada. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Match idRef="Keywords_romania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

| |
|**Keywords_romania_eu_driver ' s_license_number**|
|:-----|
|distribuição #  <br/> driver license  <br/> número de carteira de motorista  <br/> licença de driver  <br/> drivers driver'lic.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> número da carteira de motorista  <br/> número de licença do driver  <br/> número da licença de dirigir  <br/> dlno #  <br/> permé de conducere  <br/> |
   
## <a name="slovakia"></a>Eslováquia

### <a name="format"></a>Formatar

Um caractere seguido por sete dígitos
  
### <a name="pattern"></a>Padrão

Um caractere seguido por sete dígitos
  
- Uma letra (não diferencia maiúsculas de minúsculas) ou dígito
    
-  Sete dígitos 
    
### <a name="checksum"></a>Soma de verificação

Não
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A expressão `Regex_slovakia_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_slovakia_eu_driver's_license_number` chave de foi encontrada. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovaknia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

| |
|**Keywords_slovakia_eu_driver ' s_license_number**|
|:-----|
|distribuição #  <br/> driver license  <br/> número de carteira de motorista  <br/> licença de driver  <br/> drivers driver'lic.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> número da carteira de motorista  <br/> número de licença do driver  <br/> número da licença de dirigir  <br/> dlno #  <br/> vodičský preukaz  <br/> |
   
## <a name="slovenia"></a>Eslovênia

### <a name="format"></a>Formatar

Nove dígitos sem espaços e delimitadores
  
### <a name="pattern"></a>Padrão

Nove dígitos
  
### <a name="checksum"></a>Soma de verificação

Não
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A expressão `Regex_slovenia_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_slovenia_eu_driver's_license_number` chave de foi encontrada. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

| |
|**Keywords_slovenia_eu_driver ' s_license_number**|
|:-----|
|distribuição #  <br/> driver license  <br/> número de carteira de motorista  <br/> licença de driver  <br/> drivers driver'lic.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> número da carteira de motorista  <br/> número de licença do driver  <br/> número da licença de dirigir  <br/> dlno #  <br/> vozniško dovoljenje  <br/> |
   
## <a name="spain"></a>Espanha

### <a name="format"></a>Formatar

Oito dígitos seguidos de um caractere
  
### <a name="pattern"></a>Padrão

Oito dígitos seguidos de um caractere:
  
-  Oito dígitos 
    
- Um dígito ou letra (não diferencia maiúsculas de minúsculas)
    
### <a name="checksum"></a>Soma de verificação

Sim
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_spain_eu_driver's_license_number` localiza conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_spain_eu_driver's_license_number` chave de foi encontrada. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_driver's_license_number" />
          <Match idRef="Keywords_spain_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

| |
|**Keywords_spain_eu_driver ' s_license_number**|
|:-----|
|dlno #  <br/> distribuição #  <br/> drivers driver'lic.  <br/> licença de driver  <br/> driver license  <br/> drivers licence  <br/> drivers license  <br/> driver's licence  <br/> driver's license  <br/> driving licence  <br/> driving licence  <br/> número de licença de driver  <br/> número de carteira de motorista  <br/> número de licença de drivers  <br/> número de licença de drivers  <br/> número de licença do driver  <br/> número da carteira de motorista  <br/> número da licença de dirigir  <br/> número da licença de dirigir  <br/> permissão de condução  <br/> número de permissão de dirigir  <br/> permiso de conducción  <br/> permiso conducción  <br/> número licencia conducir  <br/> número de Carnet de conducir  <br/> número Carnet conducir  <br/> licencia conducir  <br/> número de permiso de conducir  <br/> número de permiso conducir  <br/> número permiso conducir  <br/> permiso conducir  <br/> licencia de manejo  <br/> El Carnet de conducir  <br/> carnet conducir  <br/> |
   
## <a name="sweden"></a>Suécia

### <a name="format"></a>Formatar

Dez dígitos contendo um hífen
  
### <a name="pattern"></a>Padrão

Dez dígitos contendo um hífen:
  
-  Seis dígitos 
    
- Um hífen
    
- Quatro dígitos
    
### <a name="checksum"></a>Soma de verificação

Não
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A expressão `Regex_sweden_eu_driver's_license_number` regular localiza o conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_sweden_eu_driver's_license_number` chave de foi encontrada. 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Match idRef="Keywords_sweden_eu_driver's_license_number" />
        </Pattern>
</Entity> 
```

### <a name="keywords"></a>Palavras-chave

| |
|**Keywords_sweden_eu_driver ' s_license_number**|
|:-----|
|distribuição #  <br/> driver license  <br/> número de carteira de motorista  <br/> licença de driver  <br/> drivers driver'lic.  <br/> drivers license  <br/> drivers licence  <br/> driver's license  <br/> número da carteira de motorista  <br/> número de licença do driver  <br/> número da licença de dirigir  <br/> dlno #  <br/> körkort  <br/> |
   
## <a name="uk"></a>Reino Unido

Para obter detalhes, consulte a seção "Reino Unido Número da carteira de motorista "em [que os tipos de informações confidenciais procuram](what-the-sensitive-information-types-look-for.md).
  
## <a name="see-also"></a>Confira também

[O que os tipos de informação confidencial procuram](what-the-sensitive-information-types-look-for.md)

