---
title: Número do Passport da UE
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: 8/16/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: Este tópico mostra o que uma política de prevenção de perda de dados (DLP) procura quando detecta o tipo de informação confidencial do número do Passport da UE. Esse tipo de informação confidencial define diferentes padrões, palavras-chave e outras evidências para cada país.
ms.openlocfilehash: 4afcf7b764eb8976e0588464515256f7cb1bdb8d
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2019
ms.locfileid: "40805944"
---
# <a name="eu-passport-number"></a>Número do Passport da UE

Este tópico mostra o que uma política de prevenção de perda de dados (DLP) procura quando detecta o tipo de informação confidencial do número do Passport da UE. Esse tipo de informação confidencial define diferentes padrões, palavras-chave e outras evidências para cada país.
  
## <a name="austria"></a>Áustria

### <a name="format"></a>Formatar

Uma letra seguida de um espaço opcional e sete dígitos
  
### <a name="pattern"></a>Padrão

Uma combinação de uma letra, sete dígitos e um espaço:
  
- Uma letra (não diferencia maiúscula de minúscula)
    
- Um espaço (opcional)
    
- Sete dígitos
    
### <a name="checksum"></a>Soma de verificação

Não se aplica
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A expressão `Regex_austria_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_austria_eu_passport_number` chave de foi encontrada. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

| |
|**Keywords_austria_eu_passport_number**|
|:-----|
|passport number  <br/> número de passaporte austríaco  <br/> Passport não  <br/> reisepass  <br/> österreichisch reisepass  <br/> |
   
## <a name="belgium"></a>Bélgica

### <a name="format"></a>Formatar

Duas letras seguidas por seis dígitos sem espaços ou delimitadores
  
### <a name="pattern"></a>Padrão

Duas letras e seguidas por seis dígitos
  
### <a name="checksum"></a>Soma de verificação

Não se aplica
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A expressão `Regex_belgium_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_belgium_eu_passport_number` chave de foi encontrada. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

| |
|**Keywords_belgium_eu_passport_number**|
|:-----|
|passport number  <br/> número de passaporte belga  <br/> Passport não  <br/> paspoort  <br/> paspoortnummer  <br/> reisepass kein  <br/> reisepass  <br/> |
   
## <a name="bulgaria"></a>Bulgária

### <a name="format"></a>Formatar

Nove dígitos sem espaços e delimitadores
  
### <a name="pattern"></a>Padrão

 Nove dígitos 
  
### <a name="checksum"></a>Soma de verificação

Não
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A expressão `Regex_bulgaria_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_bulgaria_eu_passport_number` chave de foi encontrada. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

| |
|**Keywords_bulgaria_eu_passport_number**|
|:-----|
|passport number  <br/> número de passaporte búlgaro  <br/> Passport não  <br/> номер на паспорта  <br/> |
   
## <a name="croatia"></a>Croácia

### <a name="format"></a>Formatar

Nove dígitos sem espaços e delimitadores
  
### <a name="pattern"></a>Padrão

 Nove dígitos 
  
### <a name="checksum"></a>Soma de verificação

Não
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A expressão `Regex_croatia_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_croatia_eu_passport_number` chave de foi encontrada. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

| |
|**Keywords_croatia_eu_passport_number**|
|:-----|
|passport number  <br/> número de passaporte Croata  <br/> Passport não  <br/> broj putovnice  <br/> |
   
## <a name="cyprus"></a>Chipre

### <a name="format"></a>Formatar

Uma letra seguida de 6-8 dígitos sem espaços ou delimitadores
  
### <a name="pattern"></a>Padrão

Uma letra seguida de seis a oito dígitos
  
### <a name="checksum"></a>Soma de verificação

Não
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A expressão `Regex_cyprus_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_cyprus_eu_passport_number` chave de foi encontrada. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

| |
|**Keywords_cyprus_eu_passport_number**|
|:-----|
|passport number  <br/> número de passaporte do Chipre  <br/> Passport não  <br/> αριθμό διαβατηρίου  <br/> |
   
## <a name="czech-republic"></a>República Tcheca

### <a name="format"></a>Formatar

Oito dígitos sem espaços ou delimitadores
  
### <a name="pattern"></a>Padrão

Oito dígitos sem espaços ou delimitadores
  
### <a name="checksum"></a>Soma de verificação

Não
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A expressão `Regex_czech_republic_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_czech_republic_eu_passport_number` chave de foi encontrada. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

| |
|**Keywords_czech_republic_eu_passport_number**|
|:-----|
|passport number  <br/> número de passaporte tcheco  <br/> Passport não  <br/> Pas cestovní  <br/> Pas  <br/> |
   
## <a name="denmark"></a>Dinamarca

### <a name="format"></a>Formatar

Nove dígitos sem espaços e delimitadores
  
### <a name="pattern"></a>Padrão

 Nove dígitos 
  
### <a name="checksum"></a>Soma de verificação

Não
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A expressão `Regex_denmark_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_denmark_eu_passport_number` chave de foi encontrada. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

| |
|**Keywords_denmark_eu_passport_number**|
|:-----|
|passport number  <br/> número de passaporte dinamarquês  <br/> Passport não  <br/> Pas  <br/> pasnummer  <br/> |
   
## <a name="estonia"></a>Estônia

### <a name="format"></a>Formatar

Uma letra seguida por sete dígitos sem espaços ou delimitadores
  
### <a name="pattern"></a>Padrão

Uma letra seguida por sete dígitos
  
### <a name="checksum"></a>Soma de verificação

Não
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A expressão `Regex_estonia_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_estonia_eu_passport_number` chave de foi encontrada. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

| |
|**Keywords_estonia_eu_passport_number**|
|:-----|
|passport number  <br/> número de passaporte estoniano  <br/> Passport não  <br/> Eesti kodaniku  <br/> |
   
## <a name="finland"></a>Finlândia

Para obter detalhes, consulte a seção "número de passaporte da Finlândia" em [o que os tipos de informações confidenciais buscam](what-the-sensitive-information-types-look-for.md).
  
## <a name="france"></a>França

Para obter detalhes, consulte a seção "número do passaporte da França" em [o que os tipos de informações confidenciais buscam](what-the-sensitive-information-types-look-for.md).
  
## <a name="germany"></a>Alemanha

Para obter detalhes, consulte a seção "número do passaporte em alemão" em [o que os tipos de informações confidenciais procuram](what-the-sensitive-information-types-look-for.md).
  
## <a name="greece"></a>Grécia

### <a name="format"></a>Formatar

Duas letras seguidas por sete dígitos sem espaços ou delimitadores
  
### <a name="pattern"></a>Padrão

Duas letras seguidas por sete dígitos
  
### <a name="checksum"></a>Soma de verificação

Não
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A expressão `Regex_greece_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_greece_eu_passport_number` chave de foi encontrada. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

| |
|**Keywords_greece_eu_passport_number**|
|:-----|
|passport number  <br/> número de passaporte grego  <br/> Passport não  <br/> διαβατηριο  <br/> |
   
## <a name="hungary"></a>Hungria

### <a name="format"></a>Formatar

Duas letras seguidas por seis ou sete dígitos sem espaços ou delimitadores
  
### <a name="pattern"></a>Padrão

Duas letras seguidas por seis ou sete dígitos
  
### <a name="checksum"></a>Soma de verificação

Não
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A expressão `Regex_hungary_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_hungary_eu_passport_number` chave de foi encontrada. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

| |
|**Keywords_hungary_eu_passport_number**|
|:-----|
|passport number  <br/> número de passaporte húngaro  <br/> Passport não  <br/> útlevél száma  <br/> |
   
## <a name="ireland"></a>Irlanda

### <a name="format"></a>Formatar

Duas letras ou dígitos seguidos de sete dígitos sem espaços ou delimitadores
  
### <a name="pattern"></a>Padrão

Duas letras ou dígitos seguidos por sete dígitos:
  
- Dois dígitos ou letras (não diferenciam maiúsculas de minúsculas)
    
- Sete dígitos
    
### <a name="checksum"></a>Soma de verificação

Não
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A expressão `Regex_ireland_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_ireland_eu_passport_number` chave de foi encontrada. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

| |
|**Keywords_ireland_eu_passport_number**|
|:-----|
|passport number  <br/> número de passaporte do irlandês  <br/> Passport não  <br/> Pas  <br/> Passaport  <br/> passeport  <br/> passeport numero  <br/> |
   
## <a name="italy"></a>Itália

### <a name="format"></a>Formatar

Duas letras ou dígitos seguidos de sete dígitos sem espaços ou delimitadores
  
### <a name="pattern"></a>Padrão

Duas letras ou dígitos seguidos por sete dígitos:
  
- Dois dígitos ou letras (não diferenciam maiúsculas de minúsculas)
    
- Sete dígitos
    
### <a name="checksum"></a>Soma de verificação

Não se aplica
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A expressão `Regex_italy_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_italy_eu_passport_number` chave de foi encontrada. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

| |
|**Keywords_italy_eu_passport_number**|
|:-----|
|número de passaporte italiano  <br/> repubblica italiana passaporto  <br/> passaporto  <br/> passaporto italiana  <br/> passport number  <br/> italiana passaporto numero  <br/> passaporto numero  <br/> numéro passeport italien  <br/> numéro passeport  <br/> |
   
## <a name="latvia"></a>Letônia

### <a name="format"></a>Formatar

Duas letras ou dígitos seguidos de sete dígitos sem espaços ou delimitadores
  
### <a name="pattern"></a>Padrão

Duas letras ou dígitos seguidos por sete dígitos:
  
- Dois dígitos ou letras (não diferenciam maiúsculas de minúsculas)
    
- Sete dígitos
    
### <a name="checksum"></a>Soma de verificação

Não
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A expressão `Regex_latvia_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_latvia_eu_passport_number` chave de foi encontrada. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

| |
|**Keywords_latvia_eu_passport_number**|
|:-----|
|passport number  <br/> número de passaporte da Letão  <br/> Passport não  <br/> pase numurs  <br/> |
   
## <a name="lithuania"></a>Lituânia

### <a name="format"></a>Formatar

Oito dígitos ou letras sem espaços ou delimitadores
  
### <a name="pattern"></a>Padrão

Oito dígitos ou letras (não diferencia maiúsculas de minúsculas)
  
### <a name="checksum"></a>Soma de verificação

Não se aplica
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A expressão `Regex_lithuania_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_lithuania_eu_passport_number` chave de foi encontrada. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

| |
|**Keywords_lithuania_eu_passport_number**|
|:-----|
|passport number  <br/> número de passaporte lithunian  <br/> Passport não  <br/> paso numeris  <br/> |
   
## <a name="luxemburg"></a>Luxemburg

### <a name="format"></a>Formatar

Oito dígitos ou letras sem espaços ou delimitadores
  
### <a name="pattern"></a>Padrão

Oito dígitos ou letras (não diferencia maiúsculas de minúsculas)
  
### <a name="checksum"></a>Soma de verificação

Não
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A expressão `Regex_nation_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_nation_eu_passport_number` chave de foi encontrada. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

| |
|**Keywords_nation_eu_passport_number**|
|:-----|
|passport number  <br/> número de passaporte da Letão  <br/> Passport não  <br/> passnummer  <br/> |
   
## <a name="malta"></a>Malta

### <a name="format"></a>Formatar

Sete dígitos sem espaços ou delimitadores
  
### <a name="pattern"></a>Padrão

 Sete dígitos 
  
### <a name="checksum"></a>Soma de verificação

Não
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A expressão `Regex_malta_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_malta_eu_passport_number` chave de foi encontrada. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

| |
|**Keywords_malta_eu_passport_number**|
|:-----|
|passport number  <br/> número de passaporte Maltês  <br/> Passport não  <br/> numru tal-passaport  <br/> |
   
## <a name="netherlands"></a>Países Baixos

### <a name="format"></a>Formatar

Nove letras ou dígitos sem espaços ou delimitadores
  
### <a name="pattern"></a>Padrão

Nove letras ou dígitos
  
### <a name="checksum"></a>Soma de verificação

Não se aplica
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A expressão `Regex_netherlands_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_netherlands_eu_passport_number` chave de foi encontrada. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

| |
|**Keywords_netherlands_eu_passport_number**|
|:-----|
|número de passaporte holandês  <br/> passport number  <br/> número de passaporte Holanda  <br/> nederlanden paspoort nummer  <br/> paspoort  <br/> nederlanden paspoortnummer  <br/> paspoortnummer  <br/> |
   
## <a name="poland"></a>Polônia

Para obter detalhes, consulte a seção "número de passaporte da Polônia" em [o que os tipos de informações confidenciais procuram](what-the-sensitive-information-types-look-for.md).
  
## <a name="portugal"></a>Portugal

### <a name="format"></a>Formatar

Uma letra seguida de seis dígitos sem espaços ou delimitadores
  
### <a name="pattern"></a>Padrão

Uma letra seguida por seis dígitos:
  
- Uma letra (não diferencia maiúscula de minúscula)
    
- Seis dígitos
    
### <a name="checksum"></a>Soma de verificação

Não
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A expressão `Regex_portugal_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_portugal_eu_passport_number` chave de foi encontrada. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

| |
|**Keywords_portugal_eu_passport_number**|
|:-----|
|passport number  <br/> número de passaporte Português  <br/> Passport não  <br/> número do passaporte  <br/> |
   
## <a name="romania"></a>Romênia

### <a name="format"></a>Formatar

Oito ou nove dígitos sem espaços e delimitadores
  
### <a name="pattern"></a>Padrão

Oito ou nove dígitos
  
### <a name="checksum"></a>Soma de verificação

Não
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A expressão `Regex_romania_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_romania_eu_passport_number` chave de foi encontrada. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

| |
|**Keywords_romania_eu_passport_number**|
|:-----|
|passport number  <br/> número de passaporte romeno  <br/> Passport não  <br/> numărul pașaportului  <br/> |
   
## <a name="slovakia"></a>Eslováquia

### <a name="format"></a>Formatar

Um dígito ou letra seguido por sete dígitos sem espaços ou delimitadores
  
### <a name="pattern"></a>Padrão

Um dígito ou letra (não diferencia maiúsculas de minúsculas) seguido por sete dígitos
  
### <a name="checksum"></a>Soma de verificação

Não
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A expressão `Regex_slovakia_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_slovakia_eu_passport_number` chave de foi encontrada. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

| |
|**Keywords_slovakia_eu_passport_number**|
|:-----|
|passport number  <br/> número de passaporte eslovaco  <br/> Passport não  <br/> číslo pasu  <br/> |
   
## <a name="slovenia"></a>Eslovênia

### <a name="format"></a>Formatar

Duas letras seguidas por sete dígitos sem espaços ou delimitadores
  
### <a name="pattern"></a>Padrão

Duas letras seguidas por sete dígitos:
  
- A letra "P"
    
- Uma letra maiúscula
    
- Sete dígitos
    
### <a name="checksum"></a>Soma de verificação

Não
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A expressão `Regex_slovenia_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_slovenia_eu_passport_number` chave de foi encontrada. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

| |
|**Keywords_slovenia_eu_passport_number**|
|:-----|
|passport number  <br/> número de passaporte esloveno  <br/> Passport não  <br/> lista de številka potnega  <br/> |
   
## <a name="spain"></a>Espanha

### <a name="format"></a>Formatar

Uma combinação de letras e números de oito ou nove caracteres sem espaços ou delimitadores
  
### <a name="pattern"></a>Padrão

Uma combinação de letras e números de oito ou nove caracteres:
  
-  Dois dígitos ou letras 
    
- Um dígito ou letra (opcional)
    
- Seis dígitos
    
### <a name="checksum"></a>Soma de verificação

Não se aplica
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A expressão `Regex_spain_eu_passport_number` regular localiza o conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_spain_eu_passport_number` chave de foi encontrada. 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

| |
|**Keywords_spain_eu_passport_number**|
|:-----|
|Passaport  <br/> o Passport da Espanha  <br/> Catálogo do Passport  <br/> passport number  <br/> Passport não  <br/> libreta pasaporte  <br/> número pasaporte  <br/> españa pasaporte  <br/> pasaporte  <br/> |
   
## <a name="sweden"></a>Suécia

Para obter detalhes, consulte a seção "número de passaporte da Suécia" em [o que os tipos de informações confidenciais buscam](what-the-sensitive-information-types-look-for.md).
  
## <a name="uk"></a>Reino Unido

Para obter detalhes, consulte a seção "U.S./Reino Unido Número do Passport "no [que os tipos de informações confidenciais procuram](what-the-sensitive-information-types-look-for.md).
  
## <a name="see-also"></a>Confira também

[O que os tipos de informação confidencial procuram](what-the-sensitive-information-types-look-for.md)

