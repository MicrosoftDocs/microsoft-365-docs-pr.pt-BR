---
title: Número de seguro social da UE ou ID equivalente
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: Este tópico mostra o que uma política de prevenção de perda de dados (DLP) procura quando detecta o número de segurança social da UE ou o tipo de informação confidencial de ID equivalente. Esse tipo de informação confidencial define diferentes padrões, palavras-chave e outras evidências para cada país.
ms.openlocfilehash: 276b9f2d20c2c682df2a2072c1103ab9fc67a098
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/29/2020
ms.locfileid: "43938689"
---
# <a name="eu-social-security-number-or-equivalent-id"></a>Número de seguro social da UE ou ID equivalente

Este tópico mostra o que uma política de prevenção de perda de dados (DLP) procura quando detecta o número de segurança social da UE (SSN) ou o tipo de informação confidencial de ID equivalente. Esse tipo de informação confidencial define diferentes padrões, palavras-chave e outras evidências para cada país.
  
## <a name="austria"></a>Áustria

### <a name="format"></a>Formatar

10 dígitos no formato especificado
  
### <a name="pattern"></a>Padrão

10 dígitos:
  
-  Três dígitos que correspondem a um número de série 
    
- Um dígito de verificação
    
- Seis dígitos que correspondem à data de nascimento (DDMMAA)
    
### <a name="checksum"></a>Soma de verificação

Sim
  
### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_austria_eu_ssn_or_equivalent` localiza conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_austria_eu_ssn_or_equivalent` chave de foi encontrada. 
    
Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_austria_eu_ssn_or_equivalent` localiza conteúdo que corresponde ao padrão. 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_austria_eu_ssn_or_equivalent" />
        </Pattern>
<Pattern confidenceLevel="75">
            <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_austria_eu_ssn_or_equivalent"></a>Keywords_austria_eu_ssn_or_equivalent

segurança social não
  
social security number
  
social security code
  
número de seguro
  
SSN austríaco
  
es #
  
es
  
código de seguro
  
código de seguro #
  
socialsecurityno #
  
sozialversicherungsnummer
  
soziale sicherheit kein
  
versicherungsnummer
  
## <a name="belgium"></a>Bélgica

### <a name="format"></a>Formatar

11 dígitos sem espaços ou delimitadores
  
### <a name="pattern"></a>Padrão

11 dígitos
  
### <a name="checksum"></a>Soma de verificação

Sim
  
### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_belgium_eu_ssn_or_equivalent` localiza conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_belgium_eu_ssn_or_equivalent` chave de foi encontrada. 
    
Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_belgium_eu_ssn_or_equivalent` localiza conteúdo que corresponde ao padrão. 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_belgium_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_belgium_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_belgium_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_belgium_eu_ssn_or_equivalent"></a>Keywords_belgium_eu_ssn_or_equivalent

número Nacional belga
  
número nacional
  
social security number
  
nationalnumber #
  
es #
  
es
  
nationalnumber
  
bnn #
  
bnn
  
número de identificação pessoal
  
personalidnumber #
  
nacional Numéro
  
numéro de sécurité
  
numéro d'assuré
  
nacional de identificação
  
identifiantnational #
  
numéronational #
  
## <a name="croatia"></a>Croácia

### <a name="format"></a>Formatar

11 dígitos sem espaços e delimitadores
  
### <a name="pattern"></a>Padrão

 11 dígitos: 
  
-  Dez dígitos 
    
- Um dígito de verificação
    
### <a name="checksum"></a>Soma de verificação

Sim
  
### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_croatia_eu_ssn_or_equivalent` localiza conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_croatia_eu_ssn_or_equivalent` chave de foi encontrada. 
    
Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_croatia_eu_ssn_or_equivalent` localiza conteúdo que corresponde ao padrão. 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_croatia_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_croatia_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_croatia_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_croatia_eu_ssn_or_equivalent"></a>Keywords_croatia_eu_ssn_or_equivalent

número de identificação pessoal
  
número do cidadão mestre
  
national identification number
  
social security number
  
nationalnumber #
  
es #
  
es
  
nationalnumber
  
bnn #
  
bnn
  
número de identificação pessoal
  
personalidnumber #
  
NIB
  
osobni identifikacijski broj
  
## <a name="czech-republic"></a>República Tcheca

### <a name="format"></a>Formatar

Dez dígitos e uma barra invertida no padrão especificado
  
### <a name="pattern"></a>Padrão

Dez dígitos e uma barra invertida:
  
- Seis dígitos que correspondem à data de nascimento (AAMMDD): 
    
- Uma barra invertida
    
- Três dígitos que correspondem a um número de série que separa as pessoas nasceu na mesma data
    
- Um dígito de verificação
    
### <a name="checksum"></a>Soma de verificação

Sim
  
### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_czech_republic_eu_ssn_or_equivalent` localiza conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_czech_republic_eu_ssn_or_equivalent` chave de foi encontrada. 
    
Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_czech_republic_eu_ssn_or_equivalent` localiza conteúdo que corresponde ao padrão. 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_czech_republic_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_czech_republic_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_czech_republic_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_czech_republic_eu_ssn_or_equivalent"></a>Keywords_czech_republic_eu_ssn_or_equivalent

número de nascimento
  
national identification number
  
número de identificação pessoal
  
social security number
  
nationalnumber #
  
es #
  
es
  
número nacional
  
número de identificação pessoal
  
personalidnumber #
  
rč
  
rodné číslo
  
rodne cislo
  
## <a name="denmark"></a>Dinamarca

### <a name="format"></a>Formatar

Dez dígitos e um hífen no padrão especificado
  
### <a name="pattern"></a>Padrão

Dez dígitos e um hífen:
  
- Seis dígitos que correspondem à data de nascimento (DDMMAA) 
    
- Um hífen
    
- Quatro dígitos que correspondem a um número de sequência
    
### <a name="checksum"></a>Soma de verificação

Sim
  
### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_denmark_eu_ssn_or_equivalent` localiza conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_denmark_eu_ssn_or_equivalent` chave de foi encontrada. 
    
Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_denmark_eu_ssn_or_equivalent` localiza conteúdo que corresponde ao padrão. 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_denmark_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_denmark_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_denmark_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_denmark_eu_ssn_or_equivalent"></a>Keywords_denmark_eu_ssn_or_equivalent

número de identificação pessoal
  
national identification number
  
social security number
  
nationalnumber #
  
es #
  
es
  
número nacional
  
número de identificação pessoal
  
personalidnumber #
  
CPR-Nummer
  
personnummer
  
## <a name="finland"></a>Finlândia

### <a name="format"></a>Formatar

Uma combinação de 11 caracteres no formato especificado
  
### <a name="pattern"></a>Padrão

Uma combinação de 11 caracteres no formato especificado:
  
-  Seis dígitos 
    
- Uma instância de um dos seguintes:
    
  - Símbolo de adição
    
  - Símbolo de subtração
    
  - A letra "A" (não diferencia maiúsculas de minúsculas)
    
- Três dígitos
    
- Uma letra ou um dígito
    
### <a name="checksum"></a>Soma de verificação

Sim
  
### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_finland_eu_ssn_or_equivalent` localiza conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_finland_eu_ssn_or_equivalent` chave de foi encontrada. 
    
Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_finland_eu_ssn_or_equivalent` localiza conteúdo que corresponde ao padrão. 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finland_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_finland_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_finland_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_finland_eu_ssn_or_equivalent"></a>Keywords_finland_eu_ssn_or_equivalent

identification number
  
ID pessoal
  
número de identidade
  
número de ID nacional da finlandês
  
personalidnumber #
  
national identification number
  
número de identificação
  
n º de ID nacional
  
número de ID nacional
  
ID não
  
tunnistenumero
  
henkilötunnus
  
yksilöllinen henkilökohtainen tunnistenumero
  
ainutlaatuinen henkilökohtainen tunnus
  
identiteetti numero
  
suomen kansallinen henkilötunnus
  
henkilötunnusnumero #
  
kansallisen tunnistenumero
  
tunnusnumero
  
kansallinen tunnus numero
  
hetu
  
## <a name="france"></a>França

Para obter detalhes, consulte a seção "França Social Security Number (INSEE)" em [o que os tipos de informações confidenciais procuram](what-the-sensitive-information-types-look-for.md).
  
## <a name="germany"></a>Alemanha

Para obter detalhes, consulte a seção "número do cartão de identidade da Alemanha" em [o que os tipos de informações confidenciais buscam](what-the-sensitive-information-types-look-for.md).
  
## <a name="greece"></a>Grécia

Para obter detalhes, consulte a seção "cartão de ID nacional da Grécia" em [que os tipos de informações confidenciais buscam](what-the-sensitive-information-types-look-for.md).
  
## <a name="hungary"></a>Hungria

### <a name="format"></a>Formatar

Nove dígitos sem espaços e delimitadores
  
### <a name="pattern"></a>Padrão

Nove dígitos
  
### <a name="checksum"></a>Soma de verificação

Sim
  
### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_hungary_eu_ssn_or_equivalent` localiza conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_hungary_eu_ssn_or_equivalent` chave de foi encontrada. 
    
Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_hungary_eu_ssn_or_equivalent` localiza conteúdo que corresponde ao padrão. 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_hungary_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_hungary_eu_ssn_or_equivalent"></a>Keywords_hungary_eu_ssn_or_equivalent

número de seguro social de seguridade
  
social security number
  
socialsecuritynumber #
  
hssn #
  
socialsecuritynno
  
hssn
  
taj
  
taj #
  
es
  
es #
  
segurança social não
  
áfa
  
közösségi adószám
  
általános forgalmi adó szám
  
hozzáadottérték adó
  
áfa szám
  
magyar áfa szám
  
## <a name="portugal"></a>Portugal

Para obter detalhes, consulte a seção "número de cartão de cidadão da Portugal" em [o que os tipos de informações confidenciais buscam](what-the-sensitive-information-types-look-for.md).
  
## <a name="spain"></a>Espanha

Para obter detalhes, consulte a seção "número de seguridade social da Espanha (SSN)" em [o que os tipos de informações confidenciais procuram](what-the-sensitive-information-types-look-for.md).
  
## <a name="sweden"></a>Suécia

### <a name="format"></a>Formatar

12 dígitos sem espaços e delimitadores
  
### <a name="pattern"></a>Padrão

12 dígitos:
  
-  Oito dígitos que correspondem à data de nascimento (AAAAMMDD) 
    
- Três dígitos que correspondem a um número de série em que: 
    
  - O último dígito no número de série indica sexo pela atribuição de um número ímpar para macho e um número par para o fêmea
    
  - Até 1990, a atribuição de número de série correspondente à região onde o portador do número nasceu ou (se nasceu antes de 1947) em que ele/ela estava em vida, de acordo com os registros de impostos, em 1º de janeiro de 1947, com um código especial (geralmente 9 como o sétimo dígito) para immigrants 
    
- Um dígito de verificação
    
### <a name="checksum"></a>Soma de verificação

Sim
  
### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_sweden_eu_ssn_or_equivalent` localiza conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_sweden_eu_ssn_or_equivalent` chave de foi encontrada. 
    
Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_sweden_eu_ssn_or_equivalent` localiza conteúdo que corresponde ao padrão. 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_sweden_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_sweden_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_sweden_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_sweden_eu_ssn_or_equivalent"></a>Keywords_sweden_eu_ssn_or_equivalent

número de identificação pessoal
  
identification number
  
n º de identificação pessoal
  
identidade não
  
identificação não
  
identificação pessoal não
  
ID personnummer
  
ID Personligt-Nummer
  
ID unikt-Nummer
  
personnummer
  
identifikationsnumret
  
personnummer #
  
identifikationsnumret #
  
## <a name="see-also"></a>Confira também

[O que os tipos de informação confidencial procuram](what-the-sensitive-information-types-look-for.md)

