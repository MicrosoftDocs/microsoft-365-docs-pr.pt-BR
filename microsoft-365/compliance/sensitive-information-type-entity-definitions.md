---
title: 'Definições da entidade de tipo de informações confidenciais '
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
search.appverid: MET150
ms.topic: reference
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
hideEdit: true
feedback_system: None
description: A prevenção de perda de dados (DLP) no centro de conformidade de segurança &amp; inclui 80 tipos de informações confidenciais que estão prontos para uso nas suas políticas de DLP. Este tópico lista todos os tipos de informações confidenciais e mostra o que uma política de DLP procura ao detectar cada tipo.
ms.openlocfilehash: 7985d52bcf0cbd4e3e86bc240abb8f692e733743
ms.sourcegitcommit: 327163f70eac0de568ebe3c9a97a744c3ed408cb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48177119"
---
# <a name="sensitive-information-type-entity-definitions"></a>Definições da entidade de tipo de informações confidenciais 

A prevenção de perda de dados (DLP) no centro de conformidade inclui muitos tipos de informações confidenciais que estão prontos para uso nas suas políticas de DLP. Este tópico lista todos os tipos de informações confidenciais e mostra o que uma política de DLP procura ao detectar cada tipo. Um tipo de informação confidencial é definido por um padrão que pode ser identificado por uma função ou uma expressão regular. Além disso, evidências corroborativas, como palavras-chave e somas de verificação, podem ser usadas para identificar um tipo de informação confidencial. O nível de confiança e a proximidade também são usados no processo de avaliação.

Os tipos de informações confidenciais exigem uma destas assinaturas:
- Microsoft 365 E3
- Microsoft 365 E5

Tipos de informações confidenciais podem ser usados em:
- políticas de prevenção contra perda de dados
- polcies de conformidade de comunicação
- Governança de informações
- gerenciamento de registros
- Segurança do aplicativo do Microsoft Cloud

  
## <a name="aba-routing-number"></a>Número de roteamento ABA

### <a name="format"></a>Formatar

nove dígitos que podem estar em um padrão formatado ou não formatado

### <a name="pattern"></a>Padrão

Binário
- quatro dígitos começando com 0, 1, 2, 3, 6, 7 ou 8
- um hífen
- quatro dígitos
- um hífen
- um dígito

Não formatado: nove dígitos consecutivos começando com 0, 1, 2, 3, 6, 7 ou 8 

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_aba_routing localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_ABA_Routing for encontrada.

```xml
<!-- ABA Routing Number -->
<Entity id="cb353f78-2b72-4c3c-8827-92ebe4f69fdf" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_aba_routing" />
        <Match idRef="Keyword_ABA_Routing" />
      </Pattern>
 </Entity>
```


### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_aba_routing"></a>Keyword_aba_routing

- aba
- aba #
- aba routing #
- aba routing number
- aba #
- abarouting #
- aba number
- abaroutingnumber
- american bank association routing #
- american bank association routing number
- americanbankassociationrouting #
- americanbankassociationroutingnumber
- bank routing number
- bankrouting #
- bankroutingnumber
- routing transit number
- RTN 
   
## <a name="argentina-national-identity-dni-number"></a>Número de identidade nacional (DNI) da Argentina

### <a name="format"></a>Formatar

Oito dígitos separados por pontos

### <a name="pattern"></a>Padrão

Oito dígitos:
- dois dígitos
- um período
- três dígitos
- um período
- três dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular Regex_argentina_national_id localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_argentina_national_id for encontrada.

```xml
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_argentina_national_id"></a>Keyword_argentina_national_id

- Número de Identidade Nacional da Argentina 
- Identidade 
- Identificar cartão de identidade nacional 
- DNI 
- Registro Nacional de pessoas da NIC 
- Documento Nacional de Identidad 
- Registro Nacional de las Personas 
- Identidad 
- Identificación 
   
## <a name="australia-bank-account-number"></a>Número da conta bancária da Austrália

### <a name="format"></a>Formatar

seis a TWN dígitos com ou sem um número de filial do estado do banco

### <a name="pattern"></a>Padrão

O número da conta é de seis a dez dígitos.

Número BSB da Austrália:
- três dígitos 
- um hífen 
- três dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular Regex_australia_bank_account_number localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_australia_bank_account_number for encontrada.
- A expressão regular Regex_australia_bank_account_number_bsb localiza o conteúdo que corresponde ao padrão.

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular Regex_australia_bank_account_number localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_australia_bank_account_number for encontrada.

```xml
<!-- Australia Bank Account Number -->
<Entity id="74a54de9-2a30-4aa0-a8aa-3d9327fc07c7" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_australia_bank_account_number" />
        <Match idRef="Keyword_australia_bank_account_number" />
        <Match idRef="Regex_australia_bank_account_number_bsb" />
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_bank_account_number" />
        <Match idRef="Keyword_australia_bank_account_number" />
  </Pattern>
 </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_australia_bank_account_number"></a>Keyword_australia_bank_account_number

- swift bank code
- correspondent bank
- base currency
- usa account
- holder address
- bank address
- information account
- fund transfers
- bank charges
- bank details
- banking information
- full names
- iaea

## <a name="australia-business-number"></a>Número de empresa da Austrália

### <a name="format"></a>Formatar

11 dígitos com delimitadores opcionais

### <a name="pattern"></a>Padrão

11 dígitos com delimitadores opcionais:

- dois dígitos
- um hífen ou espaço opcional
- três dígitos
- um hífen ou espaço opcional
- três dígitos
- um hífen ou espaço opcional
- três dígitos

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_australian_business_number localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keywords_australian_business_number for encontrada.

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_australian_business_number localiza o conteúdo que corresponde ao padrão.

```xml
      <!-- Australia Business Number -->
      <Entity id="76e83b3b-01ee-4530-aced-e667a6609f49" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_australian_business_number" />
          <Match idRef="Keywords_australian_business_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_australian_business_number" />
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_australia_business_number"></a>Keyword_australia_business_number

- ausência comercial na Austrália
- número de negócios
- ABN #
- BusinessID #
- ID de negócios
- ABN
- businessno #

## <a name="australia-company-number"></a>Número da empresa Austrália

### <a name="format"></a>Formatar

nove dígitos com delimitadores

### <a name="pattern"></a>Padrão

nove dígitos com delimitadores:

- três dígitos
- um espaço
- três dígitos
- um espaço
- três dígitos


### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_Australian_Company_Number localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_Australian_Company_Number for encontrada.

Uma política de DLP tem 65% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_Australian_Company_Number localiza o conteúdo que corresponde ao padrão.

```xml
      <!-- Australia Company Number -->
      <Entity id="b1fba4f7-7b3e-4bb9-8f9a-9366df604dbb" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_Australian_Company_Number" />
          <Match idRef="Keyword_Australian_Company_Number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_Australian_Company_Number" />
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_australia_company_number"></a>Keyword_australia_company_number

- Posso
- empresa Austrália não
- empresa Austrália não #
- número da empresa Austrália
- empresa australiano não
- empresa australiano não #
- número da empresa australiano

## <a name="australia-drivers-license-number"></a>Número da carteira de motorista da Austrália

### <a name="format"></a>Formatar

nove letras e dígitos

### <a name="pattern"></a>Padrão

nove letras e dígitos: 

- dois dígitos ou letras (não diferencia maiúsculas de minúsculas) 
- dois dígitos 
- cinco dígitos ou letras (não diferencia maiúsculas de minúsculas)

OU

- uma ou duas letras opcionais (não diferencia maiúsculas de minúsculas) 
- quatro a nove dígitos

OU

- nove dígitos ou letras (não diferencia maiúsculas de minúsculas)

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular Regex_australia_drivers_license_number localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_australia_drivers_license_number for encontrada.
- Nenhuma palavra-chave de Keyword_australia_drivers_license_number_exclusions for encontrada.

```xml
<!-- Australia Drivers License Number -->
<Entity id="1cbbc8f5-9216-4392-9eb5-5ac2298d1356" patternsProximity="300" recommendedConfidence="75">
   <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_drivers_license_number" />
        <Match idRef="Keyword_australia_drivers_license_number" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_australia_drivers_license_number_exclusions" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_australia_drivers_license_number"></a>Keyword_australia_drivers_license_number

- international driving permits
- australian automobile association
- international driving permit
- DriverLicence
- DriverLicences
- Driver Lic
- Driver Licence
- Driver Licences
- DriversLic
- DriversLicence
- DriversLicences
- Drivers Lic
- Drivers Lics
- Drivers Licence
- Drivers Licences
- Driver'Lic
- Driver'Lics
- Driver'Licence
- Driver'Licences
- Driver'Lic
- Driver'Lics
- Driver'Licence
- Driver'Licences
- Driver'sLic
- Driver'sLics
- Driver'sLicence
- Driver'sLicences
- Driver's Lic
- Driver's Lics
- Driver's Licence
- Driver's Licences
- DriverLic #
- DriverLics #
- DriverLicence #
- DriverLicences #
- Driver Lic#
- Driver Lics#
- Driver Licence#
- Driver Licences#
- DriversLic #
- DriversLics #
- DriversLicence #
- DriversLicences #
- Drivers Lic#
- Drivers Lics#
- Drivers Licence#
- Drivers Licences#
- Driver'Lic #
- Driver'Lics #
- Driver'Licence #
- Driver'Licences #
- Driver'Lic#
- Driver'Lics#
- Driver'Licence#
- Driver'Licences#
- Driver'sLic #
- Driver'sLics #
- Driver'sLicence #
- Driver'sLicences #
- Driver's Lic#
- Driver's Lics#
- Driver's Licence#
- Driver's Licences# 

#### <a name="keyword_australia_drivers_license_number_exclusions"></a>Keyword_australia_drivers_license_number_exclusions

- AAA
- DriverLicense
- DriverLicenses
- Driver License
- Driver Licenses
- DriversLicense
- DriversLicenses
- Drivers License
- Drivers Licenses
- Driver'License
- Driver'Licenses
- Driver'License
- Driver'Licenses
- Driver'sLicense
- Driver'sLicenses
- Driver's License
- Driver's Licenses
- DriverLicense #
- DriverLicenses #
- Driver License#
- Driver Licenses#
- DriversLicense #
- DriversLicenses #
- Drivers License#
- Drivers Licenses#
- Driver'License #
- Driver'Licenses #
- Driver'License#
- Driver'Licenses#
- Driver'sLicense #
- Driver'sLicenses #
- Driver's License#
- Driver's Licenses#
   
## <a name="australia-medical-account-number"></a>Número da conta médica da Austrália

### <a name="format"></a>Formatar

10 a 11 dígitos

### <a name="pattern"></a>Padrão

10 a 11 dígitos:
- o primeiro dígito está no intervalo 2-6
- nono dígito é um dígito de verificação
- décimo dígito é o dígito de saída
- o décimo primeiro dígito (opcional) é o número individual

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_australian_medical_account_number localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_Australia_Medical_Account_Number for encontrada.
- A soma de verificação passa.


```xml
  <!-- Australia Medical Account Number -->
<Entity id="104a99a0-3d3b-4542-a40d-ab0b9e1efe63" recommendedConfidence="85" patternsProximity="300">
    <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_australian_medical_account_number"/>
     <Match idRef="Keyword_Australia_Medical_Account_Number"/>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_australia_medical_account_number"></a>Keyword_Australia_Medical_Account_Number

- bank account details
- medicare payments
- mortgage account
- bank payments
- information branch
- credit card loan
- department of human services
- local service
- medicare

   
## <a name="australia-passport-number"></a>Número de passaporte da Austrália

### <a name="format"></a>Formatar

Uma letra seguida por sete dígitos

### <a name="pattern"></a>Padrão

Uma letra (não diferencia maiúsculas de minúsculas) seguida de sete dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular Regex_australia_passport_number localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_passport ou Keyword_australia_passport_number for encontrada.

```xml
<!-- Australia Passport Number -->
<Entity id="29869db6-602d-4853-ab93-3484f905df50" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_passport" />
          <Match idRef="Keyword_australia_passport_number" />
        </Any>
   </Pattern>
</Entity>   
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_passport"></a>Keyword_passport

- Passport Number
- Passport No
- Passport #
- Passaport #
- Passportid
- Passportno
- passportnumber
- パスポート
- パスポート番号
- パスポートのNum
- パスポート ＃ 
- Numéro de passeport
- Passeport n °
- Passeport Non
- Passeport #
- Passeport #
- PasseportNon
- Passeportn °

#### <a name="keyword_australia_passport_number"></a>Keyword_australia_passport_number

- Passaport
- passport details
- immigration and citizenship
- commonwealth of australia
- department of immigration
- residential address
- department of immigration and citizenship
- cartões
- national identity card
- passport number
- travel document
- issuing authority
   
## <a name="australia-tax-file-number"></a>Número de arquivo de imposto Austrália

### <a name="format"></a>Formatar

8 a nove dígitos

### <a name="pattern"></a>Padrão

8 a nove dígitos normalmente apresentados com espaços da seguinte maneira:
- três dígitos 
- um espaço opcional 
- três dígitos 
- um espaço opcional 
- dois a três dígitos onde o último dígito é um dígito de verificação

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_australian_tax_file_number localiza conteúdo que corresponde ao padrão.
- Nenhuma palavra-chave de Keyword_Australia_Tax_File_Number ou Keyword_number_exclusions for encontrada.
- A soma de verificação passa.

```xml
   <!-- Australia Tax File Number -->
    <Entity id="e29bc95f-ff70-4a37-aa01-04d17360a4c5" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_australian_tax_file_number" />
        <Match idRef="Keyword_Australia_Tax_File_Number" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_australia_tax_file_number"></a>Keyword_australia_tax_file_number

- australian business number
- marginal tax rate
- medicare levy
- portfolio number
- service veterans
- withholding tax
- individual tax return
- tax file number
- tfn

## <a name="austria-drivers-license-number"></a>Número da carteira de motorista do Áustria
Essa entidade de tipo de informação confidencial só está disponível no tipo de informações confidenciais do número de licença do driver da UE.

### <a name="format"></a>Formatar

oito dígitos sem espaços e delimitadores
  
### <a name="pattern"></a>Padrão

oito dígitos
  
### <a name="checksum"></a>Soma de verificação

Não
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A expressão regular  `Regex_austria_eu_driver's_license_number` localiza o conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_austria_eu_driver's_license_number` foi encontrada. 
    
```xml
<!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Match idRef="Keywords_austria_eu_driver's_license_number" />
        </Pattern>
    </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_austria_eu_drivers_license_number"></a>Keywords_austria_eu_driver ' s_license_number

- distribuição #
- driver license
- número de carteira de motorista
- licença de driver
- drivers driver'lic.
- drivers license
- driver's licence
- driver's license
- número da carteira de motorista
- número de licença do driver
- número da licença de dirigir
- dlno #
- fuhrerschein
- fuhrerschein republik osterreich

## <a name="austria-identity-card"></a>Cartão de identidade da Áustria

### <a name="format"></a>Formatar

Uma combinação de 24 caracteres de letras, dígitos e caracteres especiais
  
### <a name="pattern"></a>Padrão

24 caracteres:
  
-  22 letras (não diferencia maiúsculas de minúsculas), dígitos, barras invertidas, barras encaminhadas ou sinais de adição 
    
- duas letras (não diferencia maiúsculas de minúsculas), dígitos, barras invertidas, barras invertidas, sinais de adição ou sinais de igual
    
### <a name="checksum"></a>Soma de verificação

Não aplicável
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A expressão regular  `Regex_austria_eu_national_id_card` localiza o conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_austria_eu_national_id_card` foi encontrada. 
   
```xml
      <!-- Austria Identity Card -->
      <Entity id="5ec06c3b-007e-4820-8343-7ff73b889735" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_national_id_card" />
          <Match idRef="Keywords_austria_eu_national_id_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_austria_eu_national_id_card"></a>Keywords_austria_eu_national_id_card

- número de identidade
- 
national id
- personalausweis republik österreich

## <a name="austria-passport-number"></a>Número de passaporte da Áustria
Essa entidade de tipo de informação confidencial só está disponível no tipo sensitiveinformation do número do Passport da UE.

### <a name="format"></a>Formatar

Uma letra seguida de um espaço opcional e sete dígitos
  
### <a name="pattern"></a>Padrão

Uma combinação de uma letra, sete dígitos e um espaço:
  
- uma letra (não diferencia maiúsculas de minúsculas)
- um espaço (opcional)
- sete dígitos
    
### <a name="checksum"></a>Soma de verificação

não aplicável
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_austria_eu_passport_number` localiza o conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_austria_eu_passport_number` foi encontrada. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_austria_eu_passport_number"></a>Keywords_austria_eu_passport_number

- passport number
- número de passaporte austríaco
- Passport não
- reisepass
- österreichisch reisepass

## <a name="austria-social-security-number-or-equivalent-identification"></a>Número de segurança social da Áustria ou identificação equivalente
Essa entidade de tipo de informação confidencial só está disponível no número de seguridade social da UE ou no tipo de informações confidenciais de ID equivalente.

### <a name="format"></a>Formatar

10 dígitos no formato especificado
  
### <a name="pattern"></a>Padrão

10 dígitos:
  
- três dígitos que correspondem a um número de série 
- um dígito de verificação
- seis dígitos que correspondem à data de nascimento (DDMMAA)
    
### <a name="checksum"></a>Soma de verificação

Sim
  
### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função ' Func_austria_eu_
- _or_equivalent ' localiza conteúdo que corresponde ao padrão. 
- uma palavra-chave de  `Keywords_austria_eu_ssn_or_equivalent` foi encontrada. 
    
Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_austria_eu_ssn_or_equivalent` localiza conteúdo que corresponde ao padrão. 
    
```xml
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

- segurança social não
- social security number
- social security code
- número de seguro
- SSN austríaco
- es #
- es
- código de seguro
- código de seguro #
- socialsecurityno #
- sozialversicherungsnummer
- soziale sicherheit kein
- versicherungsnummer

## <a name="austria-tax-identification-number"></a>Número de identificação do imposto da Áustria

### <a name="format"></a>Formatar

nove dígitos com hífen opcional e barra para frente
  
### <a name="pattern"></a>Padrão

nove dígitos com hífen opcional e barra para frente:
  
- dois dígitos
- um hífen (opcional)
- três dígitos
- uma barra (opcional)
- quatro dígitos
    
### <a name="checksum"></a>Soma de verificação

Sim
  
### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_austria_eu_tax_file_number` localiza conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_austria_eu_tax_file_number` foi encontrada. 
    
Uma política de DLP tem 65% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_austria_eu_tax_file_number` localiza conteúdo que corresponde ao padrão. 
    
```xml
      <!-- Austria Tax Identification Number -->
      <Entity id="4fd58d22-af28-4451-b18a-6f722430a56d" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
          <Match idRef="Keywords_austria_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_austria_eu_tax_file_number"></a>Keywords_austria_eu_tax_file_number

- österreich
- st.nr.
- steuernummer
- tax id

- identificação de imposto não
- número de identificação do imposto
- n º do imposto #
- n º do imposto
- número do imposto
- número de registro de imposto
- táxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID do Tin
- Tin não
- Tin #
- número do imposto
 
## <a name="austria-value-added-tax"></a>Imposto sobre valor agregado da Áustria

### <a name="format"></a>Formatar

padrão alfanumérico de 11 caracteres

### <a name="pattern"></a>Padrão

padrão alfanumérico de 11 caracteres:

- A ou uma
- T ou t
- Espaço opcional
- U ou u
- espaço opcional
- dois ou três dígitos
- espaço opcional
- quatro dígitos
- espaço opcional
- um ou dois dígitos

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_Austria_Value_Added_Tax localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_Austria_Value_Added_Tax for encontrada.

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_Austria_Value_Added_Tax localiza o conteúdo que corresponde ao padrão.

```xml
      <!-- Austria Value Added Tax -->
      <Entity id="b6a3eda2-c56c-4b69-a5f7-dca34db00f48" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_Austria_Value_Added_Tax" />
          <Match idRef="Keyword_Austria_Value_Added_Tax" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_Austria_Value_Added_Tax" />
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_austria_value_added_tax"></a>Keyword_austria_value_added_tax

- número de IVA
- IVA #
- número de IVA austríaco
- IVA não.
- vatno #
- número de imposto sobre valor agregado
- VAT austríaca
- mwst
- umsatzsteuernummer
- mwstnummer
- ust.-identifikationsnummer
- umsatzsteuer-identifikationsnummer
- número de identificação do IVA
- número do atu
- número de UID


## <a name="azure-documentdb-auth-key"></a>Chave de autenticação do Azure DocumentDB

### <a name="format"></a>Formatar

A cadeia de caracteres "DocumentDb" seguida dos caracteres e cadeias de caracteres descritos no padrão abaixo.

### <a name="pattern"></a>Padrão

- A cadeia de caracteres "DocumentDb"
- Qualquer combinação entre 3-200 letras minúsculas ou maiúsculas, dígitos, símbolos, caracteres especiais ou espaços
- Um símbolo maior que (>), um sinal de igual (=), uma aspa (") ou um apóstrofo (')
- Qualquer combinação de 86 letras minúsculas ou maiúsculas, dígitos, barra de avanço (/) ou sinal de adição (+)
- Dois sinais de igual (=)

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular CEP_Regex_AzureDocumentDBAuthKey localiza o conteúdo que corresponde ao padrão.
- A expressão regular CEP_CommonExampleKeywords não **localiza o** conteúdo que corresponde ao padrão.

```xml
<!-- Azure Document DB Auth Key -->
<Entity id="0f587d92-eb28-44a9-bd1c-90f2892b47aa" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureDocumentDBAuthKey" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
          </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="cep_commonexamplekeywords"></a>CEP_CommonExampleKeywords

(Observe que tecnicamente, esse tipo de informação confidencial identifica essas palavras-chave usando uma expressão regular, não uma lista de palavras-chave.)

- contoso
- fabrikam
- Northwind
- área restrita
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->suplementos
- s-int.<!--no-hyperlink-->Netlogon

## <a name="azure-iaas-database-connection-string-and-azure-sql-connection-string"></a>Cadeia de conexão de banco de dados Azure IAAS e cadeia de conexão do Azure SQL

### <a name="format"></a>Formatar

A cadeia de caracteres "Server", "Server" ou "Data Source" seguida dos caracteres e cadeias de caracteres descritos no padrão abaixo, incluindo a cadeia de caracteres "cloudapp. Azure.<!--no-hyperlink-->com "ou" cloudapp. Azure.<!--no-hyperlink-->NET "ou" Database. Windows.<!--no-hyperlink-->NET ", e a cadeia de caracteres" password "ou" password "ou" pwd ".

### <a name="pattern"></a>Padrão

- a cadeia de caracteres "Server", "Server" ou "Data Source"
- zero a dois caracteres de espaço em branco
- um sinal de igual (=)
- zero a dois caracteres de espaço em branco
- qualquer combinação entre 1-200 letras minúsculas ou maiúsculas, dígitos, símbolos, caracteres especiais ou espaços
- A cadeia de caracteres "cloudapp. Azure.<!--no-hyperlink-->com "," cloudapp. Azure.<!--no-hyperlink-->NET "ou" Database. Windows.<!--no-hyperlink-->Netlogon
- qualquer combinação entre 1-300 letras minúsculas ou maiúsculas, dígitos, símbolos, caracteres especiais ou espaços
- a cadeia de caracteres "password", "password" ou "pwd"
- zero a dois caracteres de espaço em branco
- um sinal de igual (=)
- zero a dois caracteres de espaço em branco
- um ou mais caracteres que não são ponto-e-vírgula (;), aspas (") ou apóstrofo (')
- um ponto e vírgula (;), aspas (") ou apóstrofo (')

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular CEP_Regex_AzureConnectionString localiza o conteúdo que corresponde ao padrão.
- A expressão regular CEP_CommonExampleKeywords não **localiza o** conteúdo que corresponde ao padrão.

```xml
<!--Azure IAAS Database Connection String and Azure SQL Connection String-->
<Entity id="ce1a126d-186f-4700-8c0c-486157b953fd" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

(Observe que tecnicamente, esse tipo de informação confidencial identifica essas palavras-chave usando uma expressão regular, não uma lista de palavras-chave.)

- contoso
- fabrikam
- Northwind
- área restrita
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->suplementos
- s-int.<!--no-hyperlink-->Netlogon

## <a name="azure-iot-connection-string"></a>Cadeia de conexão IoT do Azure

### <a name="format"></a>Formatar

A cadeia de caracteres "HostName" seguida dos caracteres e cadeias de caracteres descritos no padrão abaixo, incluindo as cadeias de caracteres "Azure-Devices.<!--no-hyperlink-->NET "e" SharedAccessKey ".

### <a name="pattern"></a>Padrão

- a cadeia de caracteres "HostName"
- zero a dois caracteres de espaço em branco
- um sinal de igual (=)
- zero a dois caracteres de espaço em branco
- qualquer combinação entre 1-200 letras minúsculas ou maiúsculas, dígitos, símbolos, caracteres especiais ou espaços
- a cadeia de caracteres "Azure-Devices.<!--no-hyperlink-->Netlogon
- qualquer combinação entre 1-200 letras minúsculas ou maiúsculas, dígitos, símbolos, caracteres especiais ou espaços
- a cadeia de caracteres "SharedAccessKey"
- zero a dois caracteres de espaço em branco
- um sinal de igual (=)
- zero a dois caracteres de espaço em branco
- qualquer combinação de 43 letras minúsculas ou maiúsculas, dígitos, barra de avanço (/) ou sinal de adição (+)
- um sinal de igual (=)

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular CEP_Regex_AzureIoTConnectionString localiza o conteúdo que corresponde ao padrão.
- A expressão regular CEP_CommonExampleKeywords não **localiza o** conteúdo que corresponde ao padrão.

```xml
<!--Azure IoT Connection String-->
<Entity id="0b34bec3-d5d6-4974-b7b0-dcdb5c90c29d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureIoTConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

(Observe que tecnicamente, esse tipo de informação confidencial identifica essas palavras-chave usando uma expressão regular, não uma lista de palavras-chave.)

- contoso
- fabrikam
- Northwind
- área restrita
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->suplementos
- s-int.<!--no-hyperlink-->Netlogon

## <a name="azure-publish-setting-password"></a>Senha de configuração de publicação do Azure

### <a name="format"></a>Formatar

A cadeia de caracteres "userpwd =" seguida de uma cadeia de caracteres alfanumérica.

### <a name="pattern"></a>Padrão

- a cadeia de caracteres "userpwd ="
- qualquer combinação de letras minúsculas ou dígitos de 60
- aspas (")

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular CEP_Regex_AzurePublishSettingPasswords localiza o conteúdo que corresponde ao padrão.
- A expressão regular CEP_CommonExampleKeywords não **localiza o** conteúdo que corresponde ao padrão.


```xml
<!--Azure Publish Setting Password-->
<Entity id="75f4cc8a-a68e-49e5-89ce-fa8f03d286a5" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
       <IdMatch idRef="CEP_Regex_AzurePublishSettingPasswords" />
       <Any minMatches="0" maxMatches="0">
           <Match idRef="CEP_CommonExampleKeywords" />
       </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

(Observe que tecnicamente, esse tipo de informação confidencial identifica essas palavras-chave usando uma expressão regular, não uma lista de palavras-chave.)

- contoso
- fabrikam
- Northwind
- área restrita
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->suplementos
- s-int.<!--no-hyperlink-->Netlogon

## <a name="azure-redis-cache-connection-string"></a>Cadeia de conexão do cache do Redis do Azure

### <a name="format"></a>Formatar

A cadeia de caracteres "Redis. cache. Windows.<!--no-hyperlink-->NET "seguido pelos caracteres e cadeias de caracteres descritos no padrão abaixo, incluindo a cadeia de caracteres" password "ou" pwd ".

### <a name="pattern"></a>Padrão

- a cadeia de caracteres "Redis. cache. Windows.<!--no-hyperlink-->Netlogon
- qualquer combinação entre 1-200 letras minúsculas ou maiúsculas, dígitos, símbolos, caracteres especiais ou espaços
- a cadeia de caracteres "password" ou "pwd"
- zero a dois caracteres de espaço em branco
- um sinal de igual (=)
- zero a dois caracteres de espaço em branco
- qualquer combinação de 43 caracteres que sejam letras minúsculas ou maiúsculas, dígitos, barra de avanço (/) ou sinal de adição (+)
- um sinal de igual (=)

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular CEP_Regex_AzureRedisCacheConnectionString localiza o conteúdo que corresponde ao padrão..
- A expressão regular CEP_CommonExampleKeywords não **localiza o** conteúdo que corresponde ao padrão.

```xml
<!--Azure Redis Cache Connection String-->
<Entity id="095a7e6c-efd8-46d5-af7b-5298d53a49fc" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureRedisCacheConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

(Observe que tecnicamente, esse tipo de informação confidencial identifica essas palavras-chave usando uma expressão regular, não uma lista de palavras-chave.)

- contoso
- fabrikam
- Northwind
- área restrita
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->suplementos
- s-int.<!--no-hyperlink-->Netlogon

## <a name="azure-sas"></a>SAS do Azure

### <a name="format"></a>Formatar

A cadeia de caracteres "SIG" seguida pelos caracteres e cadeias de caracteres descritos no padrão abaixo.

### <a name="pattern"></a>Padrão

- a cadeia de caracteres "SIG"
- zero a dois caracteres de espaço em branco
- um sinal de igual (=)
- zero a dois caracteres de espaço em branco
- qualquer combinação entre 43-53 caracteres que são letras minúsculas ou maiúsculas, dígitos ou o sinal de porcentagem (%)
- a cadeia de caracteres "% 3D"
- qualquer caractere que não seja letras minúsculas, dígitos ou sinal de porcentagem (%)

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular CEP_Regex_AzureSAS localiza o conteúdo que corresponde ao padrão.

```xml
<!--Azure SAS-->
<Entity id="4d235014-e564-47f4-a6fb-6ebb4a826834" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureSAS" />
  </Pattern>
</Entity>
```

## <a name="azure-service-bus-connection-string"></a>Cadeia de conexão do barramento de serviço do Azure

### <a name="format"></a>Formatar

A cadeia de caracteres "EndPoint" seguida dos caracteres e cadeias de caracteres descritos no padrão abaixo, incluindo as cadeias de caracteres "ServiceBus. Windows.<!--no-hyperlink-->NET "e" SharedAccesKey ".

### <a name="pattern"></a>Padrão

- a cadeia de caracteres "EndPoint"
- zero a dois caracteres de espaço em branco
- um sinal de igual (=)
- zero a dois caracteres de espaço em branco
- qualquer combinação entre 1-200 letras minúsculas ou maiúsculas, dígitos, símbolos, caracteres especiais ou espaços
- a cadeia de caracteres "ServiceBus. Windows.<!--no-hyperlink-->Netlogon
- qualquer combinação entre 1-200 letras minúsculas ou maiúsculas, dígitos, símbolos, caracteres especiais ou espaços
- a cadeia de caracteres "SharedAccessKey"
- zero a dois caracteres de espaço em branco
- um sinal de igual (=)
- zero a dois caracteres de espaço em branco
- qualquer combinação de 43 caracteres que sejam letras minúsculas ou maiúsculas, dígitos, barra de avanço (/) ou sinal de adição (+)
- um sinal de igual (=)

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular CEP_Regex_AzureServiceBusConnectionString localiza o conteúdo que corresponde ao padrão..
- A expressão regular CEP_CommonExampleKeywords não **localiza o** conteúdo que corresponde ao padrão.

```xml
<!--Azure Service Bus Connection String-->
<Entity id="b9a6578f-a83f-4fcd-bf44-2130bae49a6f" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureServiceBusConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

(Observe que tecnicamente, esse tipo de informação confidencial identifica essas palavras-chave usando uma expressão regular, não uma lista de palavras-chave.)

- contoso
- fabrikam
- Northwind
- área restrita
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->suplementos
- s-int.<!--no-hyperlink-->Netlogon

## <a name="azure-storage-account-key"></a>Chave da conta de armazenamento do Azure

### <a name="format"></a>Formatar

A cadeia de caracteres "DefaultEndpointsProtocol" seguida dos caracteres e cadeias de caracteres descritos no padrão abaixo, incluindo a cadeia de caracteres "AccountKey".

### <a name="pattern"></a>Padrão

- a cadeia de caracteres "DefaultEndpointsProtocol"
- zero a dois caracteres de espaço em branco
- um sinal de igual (=)
- zero a dois caracteres de espaço em branco
- qualquer combinação entre 1-200 letras minúsculas ou maiúsculas, dígitos, símbolos, caracteres especiais ou espaços
- a cadeia de caracteres "AccountKey"
- zero a dois caracteres de espaço em branco
- um sinal de igual (=)
- zero a dois caracteres de espaço em branco
- qualquer combinação de 86 caracteres que sejam letras minúsculas ou maiúsculas, dígitos, barra de avanço (/) ou sinal de adição (+)
- dois sinais de igual (=)

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular CEP_Regex_AzureStorageAccountKey localiza o conteúdo que corresponde ao padrão.
- A expressão regular CEP_AzureEmulatorStorageAccountFilter não **localiza o** conteúdo que corresponde ao padrão.
- A expressão regular CEP_CommonExampleKeywords não **localiza o** conteúdo que corresponde ao padrão.

```xml
<!--Azure Storage Account Key-->
<Entity id="c7bc98e8-551a-4c35-a92d-d2c8cda714a7" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKey" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_AzureEmulatorStorageAccountFilter" />
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="cep_azure_emulator_storage_account_filter"></a>CEP_azure_emulator_storage_account_filter

(Observe que tecnicamente, esse tipo de informação confidencial identifica essas palavras-chave usando uma expressão regular, não uma lista de palavras-chave.)

- Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw = =

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

(Observe que tecnicamente, esse tipo de informação confidencial identifica essas palavras-chave usando uma expressão regular, não uma lista de palavras-chave.)

- contoso
- fabrikam
- Northwind
- área restrita
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->suplementos
- s-int.<!--no-hyperlink-->Netlogon

## <a name="azure-storage-account-key-generic"></a>Chave da conta de armazenamento do Azure (genérico)

### <a name="format"></a>Formatar

Qualquer combinação de letras maiúsculas ou minúsculas de 86, dígitos, barra (/) ou sinal de adição (+), precedida ou seguida dos caracteres descritos no padrão abaixo.

### <a name="pattern"></a>Padrão

- zero para um dos símbolos maior que (>), apóstrofo ('), sinal de igual (=), aspas (") ou sinal de número (#)
- qualquer combinação de 86 caracteres que sejam letras minúsculas ou maiúsculas, dígitos, a barra (/) ou sinal de adição (+)
- dois sinais de igual (=)

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular CEP_Regex_AzureStorageAccountKeyGeneric localiza o conteúdo que corresponde ao padrão.

```xml
<!--Azure Storage Account Key (Generic)-->
<Entity id="7ff41bd0-5419-4523-91d6-383b3a37f084" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKeyGeneric" />
  </Pattern>
</Entity>
```
## <a name="belgium-drivers-license-number"></a>Número da carteira de motorista do Bélgica
Essa entidade de tipo de informação confidencial só está disponível no tipo de informações confidenciais do número de licença do driver da UE.

### <a name="format"></a>Formatar

dez dígitos sem espaços e delimitadores
  
### <a name="pattern"></a>Padrão

dez dígitos
  
### <a name="checksum"></a>Soma de verificação

Não
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_belgium_eu_driver's_license_number` localiza o conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_belgium_eu_driver's_license_number` foi encontrada.
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Match idRef="Keywords_belgium_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

**Keywords__belgium_eu_driver ' s_license_number**

- distribuição #
- driver license
- número de carteira de motorista
- licença de driver
- drivers driver'lic.
- drivers license
- drivers licence
- driver's license
- número da carteira de motorista
- número de licença do driver
- dlno #
- rijbewijs
- rijbewijsnummer
- führerscheinnummer
- fuhrerscheinnummer
- fuehrerscheinnummer
- führerschein- nr
- fuehrerschein- Nr
- fuehrerschein- nr

## <a name="belgium-national-number"></a>Número nacional da Bélgica

### <a name="format"></a>Formatar

11 dígitos mais delimitadores opcionais

### <a name="pattern"></a>Padrão

11 dígitos mais delimitadores.
- seis dígitos e dois períodos opcionais no formato YY. Principal. DD para data de nascimento 
- Um delimitador opcional de ponto, traço, espaço 
- três dígitos sequenciais (ímpares para homens, mesmo para mulheres) 
- Um delimitador opcional de ponto, traço, espaço 
- dois dígitos de verificação

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_belgium_national_number localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_belgium_national_number for encontrada.
- A soma de verificação passa.

Uma política de DLP tem 65% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_belgium_national_number localiza o conteúdo que corresponde ao padrão.
- A soma de verificação passa.

```xml
<!-- Belgium National Number -->
       <Entity id="fb969c9e-0fd1-4b18-8091-a2123c5e6a54" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_belgium_national_number" />
          <Match idRef="Keyword_belgium_national_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_belgium_national_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_belgium_national_number"></a>Keyword_belgium_national_number

- aantal de última
- bnn #
- bnn
- d'identité carte
- nacional de identificação
- identifiantnational #
- identificatie
- identificador
- identifikation
- identifikationsnummer
- identifizierung
- identité
- identiteit
- identiteitskaart
- ladrões
- inscription
- número nacional
- Registro Nacional
- nationalnumber #
- nationalnumber
- nse #
- nse
- numéro d'assuré
- Numéro de Registro Nacional
- numéro de sécurité

- numéro d'identification
- numéro d'immatriculation
- nacional Numéro
- numéronational #
- número de identificação pessoal
- personalausweis
- personalidnumber #
- registratie
- registro
- registrationsnumme
- registrierung
- social security number

- es #
- es
- steuernummer
- tax id

- identificação de imposto não
- número de identificação do imposto
- n º do imposto #
- n º do imposto
- número do imposto
- número de registro de imposto
- táxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID do Tin
- Tin não
- Tin #

## <a name="belgium-passport-number"></a>Número de passaporte da Bélgica
Essa entidade de tipo de informação confidencial só está disponível no tipo de informação confidencial do número do Passport da UE.

### <a name="format"></a>Formatar

duas letras seguidas por seis dígitos sem espaços ou delimitadores
  
### <a name="pattern"></a>Padrão

duas letras e seguidas por seis dígitos
  
### <a name="checksum"></a>Soma de verificação

não aplicável
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_belgium_eu_passport_number` localiza o conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_belgium_eu_passport_number` foi encontrada.

```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_belgium_eu_passport_number"></a>Keywords_belgium_eu_passport_number

- passport number
- número de passaporte belga
- Passport não
- paspoort
- paspoortnummer
- reisepass kein
- reisepass

## <a name="belgium-social-security-number-or-equivalent-identification"></a>Número da segurança social da Bélgica ou identificação equivalente
Essa entidade de tipo de informação confidencial só está disponível no número de seguridade social da UE ou no tipo de informações confidenciais de ID equivalente.

### <a name="format"></a>Formatar

11 dígitos sem espaços ou delimitadores
  
### <a name="pattern"></a>Padrão

11 dígitos
  
### <a name="checksum"></a>Soma de verificação

Sim
  
### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função  `Func_belgium_eu_ssn_or_equivalent` localiza conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_belgium_eu_ssn_or_equivalent` foi encontrada. 
    
Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_belgium_eu_ssn_or_equivalent` localiza conteúdo que corresponde ao padrão. 
    
```xml
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

- número Nacional belga
- número nacional
- social security number
- nationalnumber #
- es #
- es
- nationalnumber
- bnn #
- bnn
- número de identificação pessoal
- personalidnumber #
- nacional Numéro
- numéro de sécurité
- numéro d'assuré
- nacional de identificação
- identifiantnational #
- numéronational #


## <a name="belgium-value-added-tax-number"></a>Número de imposto adicionado ao valor da Bélgica

### <a name="format"></a>Formatar

padrão alfanumérico de 12 caracteres

### <a name="pattern"></a>Padrão

padrão alfanumérico de 12 caracteres:

- uma letra B ou B
- uma letra E ou E
- um dígito 0
- um dígito de 1 a 9
- um ponto ou hífen opcional ou espaço
- quatro dígitos
- um ponto ou hífen opcional ou espaço
- quatro dígitos


### <a name="checksum"></a>Soma de verificação

Sim


### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_belgium_value_added_tax_number localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keywords_belgium_value_added_tax_number for encontrada.

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_belgium_value_added_tax_number localiza o conteúdo que corresponde ao padrão.

```xml
      <!-- Belgium Value Added Tax Number -->
      <Entity id="85b5b3c3-f2de-4ae8-ac46-fd3cb38bf9ed" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_belgium_value_added_tax_number" />
          <Match idRef="Keywords_belgium_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_belgium_value_added_tax_number" />
        </Pattern>
      </Entity>
    </Version>
```
### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_belgium_value_added_tax_number"></a>Keyword_belgium_value_added_tax_number

- n º TVA
- número de IVA
- IVA não
- Numéro t. v. a
- umsatzsteuer-identifikationsnummer
- umsatzsteuernummer
- btw
- btw #
- IVA #


## <a name="brazil-cpf-number"></a>Número de CPF do Brasil

### <a name="format"></a>Formatar

11 dígitos que incluem um dígito de verificação e podem ser formatados ou não formatados

### <a name="pattern"></a>Padrão

Binário
- três dígitos
- um período
- três dígitos
- um período
- três dígitos
- um hífen
- dois dígitos que são dígitos de verificação

Não formatado
- 11 dígitos em que os dois últimos dígitos são dígitos de verificação

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_brazil_cpf localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_brazil_cpf for encontrada.
- A soma de verificação passa.

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_brazil_cpf localiza o conteúdo que corresponde ao padrão.
- A soma de verificação passa.

```xml
<!-- Brazil CPF Number -->
<Entity id="78e09124-f2c3-4656-b32a-c1a132cd2711" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_cpf"/>
     <Match idRef="Keyword_brazil_cpf"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_cpf"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_brazil_cpf"></a>Keyword_brazil_cpf

- CPF
- Identificador
- Registro
- Participação
- Cadastro de Pessoas Físicas 
- Imposto 
- Identificação 
- Inscrição 
- Receita 

   
## <a name="brazil-legal-entity-number-cnpj"></a>Número de entidade legal (CNPJ) do Brasil

### <a name="format"></a>Formatar

14 dígitos que incluem um número de registro, o número da ramificação e dígitos de verificação, além de delimitadores de seleção

### <a name="pattern"></a>Padrão

14 dígitos mais delimitadores:

- dois dígitos 
- um período 
- três dígitos 
- um período 
- três dígitos (estes primeiros oito dígitos são o número de registro) 
- uma barra 
- número de filial de quatro dígitos 
- um hífen 
- dois dígitos que são dígitos de verificação

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_brazil_cnpj localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_brazil_cnpj for encontrada.
- A soma de verificação passa.

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_brazil_cnpj localiza o conteúdo que corresponde ao padrão.
- A soma de verificação passa.

```xml
<!-- Brazil Legal Entity Number (CNPJ) -->
<Entity id="9b58b5cd-5e90-4df6-b34f-1ebcc88ceae4" recommendedConfidence="85" patternsProximity="300">
   <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_cnpj"/>
     <Match idRef="Keyword_brazil_cnpj"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_cnpj"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_brazil_cnpj"></a>Keyword_brazil_cnpj

- CNPJ 
- CNPJ/MF 
- CNPJ-MF 
- Registro Nacional de Pessoas Jurídicas 
- Registro de Contribuintes 
- Pessoa jurídica 
- Pessoas jurídicas 
- Status do Registro 
- Business 
- Empresa
- CNPJ 
- Cadastro Nacional da Pessoa Jurídica 
- Cadastro Geral de Contribuintes 
- CGC 
- Pessoa jurídica 
- Pessoas jurídicas 
- Situação cadastral 
- Inscrição 
- Empresa 

   
## <a name="brazil-national-identification-card-rg"></a>Cartão de identificação nacional do Brasil (RG)

### <a name="format"></a>Formatar

Registro geral (formato antigo): nove dígitos

Registro de identidade (RIC) (novo formato): 11 dígitos

### <a name="pattern"></a>Padrão

Registro Geral (formato antigo):
- dois dígitos 
- um período 
- três dígitos 
- um período 
- três dígitos 
- um hífen 
- um dígito que é um dígito de verificação

Registro de identidade (RIC) (novo formato):
- dez dígitos 
- um hífen 
- um dígito que é um dígito de verificação

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_brazil_rg localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_brazil_rg for encontrada.
- A soma de verificação passa.

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_brazil_rg localiza o conteúdo que corresponde ao padrão.
- A soma de verificação passa.

```xml
<!-- Brazil National ID Card (RG) -->
<Entity id="486de900-db70-41b3-a886-abdf25af119c" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_rg"/>
     <Match idRef="Keyword_brazil_rg"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_rg"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_brazil_rg"></a>Keyword_brazil_rg

- Cédula de identidade
- cartão de identidade
- national id 
- número de registro
- registro de identidade 
- registro geral
- RG (esta palavra-chave diferencia maiúsculas de minúsculas) 
- RIC (esta palavra-chave diferencia maiúsculas de minúsculas) 


## <a name="bulgaria-drivers-license-number"></a>Número da carteira de motorista do Bulgária
Essa entidade de tipo de informação confidencial só está disponível no tipo de informações confidenciais do número de licença do driver da UE.

### <a name="format"></a>Formatar

nove dígitos sem espaços e delimitadores
  
### <a name="pattern"></a>Padrão

nove dígitos
  
### <a name="checksum"></a>Soma de verificação

Não
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_bulgaria_eu_driver's_license_number` localiza o conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_bulgaria_eu_driver's_license_number` foi encontrada. 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
             <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
        </Pattern> 
</Entity>    
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_bulgaria_eu_drivers_license_number"></a>Keywords_bulgaria_eu_driver ' s_license_number
- distribuição #
- driver license
- número de carteira de motorista
- licença de driver
- drivers driver'lic.
- drivers license
- drivers licence
- driver's license
- número da carteira de motorista
- número de licença do driver
- número da licença de dirigir
- dlno #
- свидетелство за управление на мпс
- свидетелство за управление на моторно превозно средство
- сумпс
- шофьорска книжка


## <a name="bulgaria-uniform-civil-number"></a>Número civil uniforme da Bulgária

### <a name="format"></a>Formatar

dez dígitos sem espaços e delimitadores
  
### <a name="pattern"></a>Padrão

dez dígitos sem espaços e delimitadores
  
- seis dígitos que correspondem à data de nascimento (AAMMDD) 
- dois dígitos que correspondem à ordem de nascimento
- um dígito que corresponde ao gênero: um dígito par para macho e um dígito estranho para o fêmea
- um dígito de verificação

### <a name="checksum"></a>Soma de verificação

Sim
  
### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_bulgaria_eu_national_id_card` localiza conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_bulgaria_eu_national_id_card` foi encontrada. 

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_bulgaria_eu_national_id_card` localiza conteúdo que corresponde ao padrão. 
    
```xml
      <!-- Bulgaria Uniform Civil Number -->
      <Entity id="100d58b1-0a35-4fb1-aa89-e4a86fb53fcc" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_bulgaria_eu_national_id_card" />
          <Match idRef="Keywords_bulgaria_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_bulgaria_eu_national_id_card" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_bulgaria_eu_telephone_number" />
            <Match idRef="Keywords_bulgaria_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_bulgaria_eu_national_id_card"></a>Keywords_bulgaria_eu_national_id_card

- bnn #
- bnn
- bucn #
- bucn
- edinen grazhdanski de nome
- egn #
- egn
- identification number

- 
national id
- número nacional
- nationalnumber #
- nationalnumber
- ID pessoal
- pessoal não
- número pessoal
- personalidnumber #
- social security number

- es #
- es
- ID civil uniforme
- Nenhum civil uniforme
- número civil uniforme
- uniformcivilno #
- uniformcivilno
- uniformcivilnumber #
- uniformcivilnumber
- número exclusivo de cidadania
- егн #
- егн
- единен граждански номер
- идентификационен номер
- личен номер
- лична идентификация
- лично не
- национален номер
- номер на гражданството
- ID униформ
- ID de граждански униформ
- униформ граждански не
- униформ граждански номер
- униформгражданскиid #
- униформгражданскине. #


## <a name="bulgaria-passport-number"></a>Número de passaporte da Bulgária
Essa entidade de tipo de informação confidencial só está disponível no tipo de informação confidencial do número do Passport da UE.

### <a name="format"></a>Formatar

nove dígitos sem espaços e delimitadores
  
### <a name="pattern"></a>Padrão

nove dígitos 
  
### <a name="checksum"></a>Soma de verificação

Não
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_bulgaria_eu_passport_number` localiza o conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_bulgaria_eu_passport_number` foi encontrada. 

```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```
### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_bulgaria_eu_passport_number"></a>Keywords_bulgaria_eu_passport_number

- passport number
- número de passaporte búlgaro
- Passport não
- номер на паспорта


## <a name="canada-bank-account-number"></a>Número de conta bancária do Canadá

### <a name="format"></a>Formatar

sete ou doze dígitos

### <a name="pattern"></a>Padrão

Um número de conta bancária do Canadá tem sete ou doze dígitos.

Um número de trânsito de conta bancária do Canadá tem:
- cinco dígitos 
- um hífen 
- três dígitos ou
- um zero "0" 
- oito dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular Regex_canada_bank_account_number localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_canada_bank_account_number for encontrada.
- A expressão regular Regex_canada_bank_account_transit_number localiza o conteúdo que corresponde ao padrão.

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular Regex_canada_bank_account_number localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_canada_bank_account_number for encontrada.

```xml
<!-- Canada Bank Account Number -->
<Entity id="552e814c-cb50-4d94-bbaa-bb1d1ffb34de" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_canada_bank_account_number" />
        <Match idRef="Keyword_canada_bank_account_number" />
        <Match idRef="Regex_canada_bank_account_transit_number" />
   </Pattern>
   <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_bank_account_number" />
        <Match idRef="Keyword_canada_bank_account_number" />
   </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_canada_bank_account_number"></a>Keyword_canada_bank_account_number

- canada savings bonds
- canada revenue agency
- canadian financial institution
- direct deposit form
- canadian citizen
- legal representative
- notary public
- commissioner for oaths
- child care benefit
- universal child care
- canada child tax benefit
- income tax benefit
- harmonized sales tax
- social insurance number
- income tax refund
- child tax benefit
- territorial payments
- institution number
- deposit request
- banking information
- direct deposit

   
## <a name="canada-drivers-license-number"></a>Número da carteira de motorista do Canadá

### <a name="format"></a>Formatar

Varia por província

### <a name="pattern"></a>Padrão

Vários padrões que abrangem Alberta, Columbia Britânica, Manitoba, New Brunswick, Newfoundland/Labrador, Nova Escócia, Ontário, Ilha do Príncipe Eduardo, Quebec e Saskatchewan

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_[province_name]_drivers_license_number localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_[province_name]_drivers_license_name for encontrada.
- Uma palavra-chave de Keyword_canada_drivers_license for encontrada.

```xml
<!-- Canada Driver's License Number -->
    <Entity id="37186abb-8e48-4800-ad3c-e3d1610b3db0" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_alberta_drivers_license_number" />
        <Match idRef="Keyword_alberta_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_british_columbia_drivers_license_number" />
        <Match idRef="Keyword_british_columbia_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_manitoba_drivers_license_number" />
        <Match idRef="Keyword_manitoba_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_new_brunswick_drivers_license_number" />
        <Match idRef="Keyword_new_brunswick_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_newfoundland_labrador_drivers_license_number" />
        <Match idRef="Keyword_newfoundland_labrador_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_nova_scotia_drivers_license_number" />
        <Match idRef="Keyword_nova_scotia_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_ontario_drivers_license_number" />
        <Match idRef="Keyword_ontario_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_prince_edward_island_drivers_license_number" />
        <Match idRef="Keyword_prince_edward_island_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_quebec_drivers_license_number" />
        <Match idRef="Keyword_quebec_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_saskatchewan_drivers_license_number" />
        <Match idRef="Keyword_saskatchewan_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_province_name_drivers_license_name"></a>Keyword_ [province_name] _drivers_license_name

- A abreviação da província, por exemplo AB
- O nome da província, por exemplo, Alberta

#### <a name="keyword_canada_drivers_license"></a>Keyword_canada_drivers_license

- DISTRIBUIÇÃO
- DL
- CDL
- CDLS
- DriverLic
- DriverLics
- DriverLicense
- DriverLicenses
- DriverLicence
- DriverLicences
- Driver Lic
- Driver Lics
- Driver License
- Driver Licenses
- Driver Licence
- Driver Licences
- DriversLic
- DriversLics
- DriversLicence
- DriversLicences
- DriversLicense
- DriversLicenses
- Drivers Lic
- Drivers Lics
- Drivers License
- Drivers Licenses
- Drivers Licence
- Drivers Licences
- Driver'Lic
- Driver'Lics
- Driver'License
- Driver'Licenses
- Driver'Licence
- Driver'Licences
- Driver'Lic
- Driver' Lics
- Driver' License
- Driver'Licenses
- Driver'Licence
- Driver'Licences
- Driver'sLic
- Driver'sLics
- Driver'sLicense
- Driver'sLicenses
- Driver'sLicence
- Driver'sLicences
- Driver's Lic
- Driver's Lics
- Driver's License
- Driver's Licenses
- Driver's Licence
- Driver's Licences
- Permis de Conduire
- id
- ids
- idcard number
- idcard numbers
- idcard #
- idcard #s
- idcard card
- idcard cards
- idcard
- identification number
- identification numbers
- identification #
- identification #s
- identification card
- identification cards
- identificador 
- DISTRIBUIÇÃO #
- DL # 
- CDL # 
- CDLS # 
- DriverLic # 
- DriverLics # 
- DriverLicense # 
- DriverLicenses # 
- DriverLicence # 
- DriverLicences # 
- Driver Lic#
- Driver Lics# 
- Driver License# 
- Driver Licenses# 
- Driver License# 
- Driver Licences# 
- DriversLic # 
- DriversLics # 
- DriversLicense # 
- DriversLicenses # 
- DriversLicence # 
- DriversLicences # 
- Drivers Lic# 
- Drivers Lics# 
- Drivers License# 
- Drivers Licenses# 
- Drivers Licence# 
- Drivers Licences# 
- Driver'Lic # 
- Driver'Lics # 
- Driver'License # 
- Driver'Licenses # 
- Driver'Licence # 
- Driver'Licences # 
- Driver'Lic# 
- Driver' Lics# 
- Driver' License# 
- Driver'Licenses# 
- Driver'Licence# 
- Driver'Licences# 
- Driver'sLic # 
- Driver'sLics # 
- Driver'sLicense # 
- Driver'sLicenses # 
- Driver'sLicence # 
- Driver'sLicences # 
- Driver's Lic# 
- Driver's Lics# 
- Driver's License# 
- Driver's Licenses# 
- Driver's Licence# 
- Driver's Licences# 
- Permis de Conduire# 
- ID # 
- código # 
- idcard card# 
- idcard cards# 
- idcard # 
- identification card# 
- identification cards# 
- identificador # 

   
## <a name="canada-health-service-number"></a>Número do serviço de integridade do Canadá

### <a name="format"></a>Formatar

dez dígitos

### <a name="pattern"></a>Padrão

dez dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular Regex_canada_health_service_number localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_canada_health_service_number for encontrada.

```xml
<!-- Canada Health Service Number -->
<Entity id="59c0bf39-7fab-482c-af25-00faa4384c94" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_health_service_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_canada_health_service_number" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_canada_health_service_number"></a>Keyword_canada_health_service_number

- personal health number
- patient information
- health services
- speciality services
- automobile accident
- patient hospital
- psychiatrist
- workers compensation
- Deficiência

      
## <a name="canada-passport-number"></a>Número de passaporte do Canadá

### <a name="format"></a>Formatar

duas letras maiúsculas seguidas de seis dígitos

### <a name="pattern"></a>Padrão

duas letras maiúsculas seguidas de seis dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular Regex_canada_passport_number localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_canada_passport_number ou Keyword_passport for encontrada.

```xml 
<!-- Canada Passport Number -->
<Entity id="14d0db8b-498a-43ed-9fca-f6097ae687eb" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_canada_passport_number" />
          <Match idRef="Keyword_passport" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_canada_passport_number"></a>Keyword_canada_passport_number

- canadian citizenship
- canadian passport
- passport application
- passport photos
- certified translator
- canadian citizens
- processing times
- renewal application

#### <a name="keyword_passport"></a>Keyword_passport

- Passport Number
- Passport No
- Passport #
- Passaport #
- Passportid
- Passportno
- passportnumber
- パスポート
- パスポート番号
- パスポートのNum
- パスポート＃
- Numéro de passeport
- Passeport n °
- Passeport Non
- Passeport #
- Passeport #
- PasseportNon
- Passeportn °

   
## <a name="canada-personal-health-identification-number-phin"></a>Número de identificação de saúde pessoal do Canadá (PHIN)

### <a name="format"></a>Formatar

nove dígitos

### <a name="pattern"></a>Padrão

nove dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular Regex_canada_phin localiza o conteúdo que corresponde ao padrão.
- São encontradas pelo menos duas palavras-chave de Keyword_canada_phin ou Keyword_canada_provinces.

```xml
<!-- Canada PHIN -->
<Entity id="722e12ac-c89a-4ec8-a1b7-fea3469f89db" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_phin" />
        <Any minMatches="2">
          <Match idRef="Keyword_canada_phin" />
          <Match idRef="Keyword_canada_provinces" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_canada_phin"></a>Keyword_canada_phin

- social insurance number
- health information act
- income tax information
- manitoba health
- health registration
- prescription purchases
- benefit eligibility
- personal health
- power of attorney
- registration number
- personal health number
- practitioner referral
- wellness professional
- patient referral
- health and wellness

#### <a name="keyword_canada_provinces"></a>Keyword_canada_provinces

- Nunavut
- Quebec
- Northwest Territories
- Ontário
- British Columbia
- Alberta
- Saskatchewan
- Manitoba
- Yukon
- Newfoundland and Labrador
- New Brunswick
- Nova Scotia
- Prince Edward Island
- Canadá

   
## <a name="canada-social-insurance-number"></a>Número de seguro social do Canadá

### <a name="format"></a>Formatar

nove dígitos com hifens ou espaços opcionais

### <a name="pattern"></a>Padrão

Binário
- três dígitos 
- um hífen ou espaço 
- três dígitos 
- um hífen ou espaço 
- três dígitos

Não formatado: nove dígitos

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_canadian_sin localiza conteúdo que corresponde ao padrão.
- Pelo menos duas de qualquer combinação do seguinte:
    - Uma palavra-chave de Keyword_sin for encontrada.
    - Uma palavra-chave de Keyword_sin_collaborative for encontrada.
    - A função Func_eu_date encontra uma data no formato de data à direita.
- A soma de verificação passa.

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_unformatted_canadian_sin localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_sin for encontrada.
- A soma de verificação passa.

```xml
<!-- Canada Social Insurance Number -->
<Entity id="a2f29c85-ecb8-4514-a610-364790c0773e" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_canadian_sin" />
        <Any minMatches="2">
          <Match idRef="Keyword_sin" />
          <Match idRef="Keyword_sin_collaborative" />
          <Match idRef="Func_eu_date" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_canadian_sin" />
        <Match idRef="Keyword_sin" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_sin"></a>Keyword_sin

- sin 
- social insurance 
- numero d'assurance sociale 
- capitais 
- es 
- CPFs 
- social security 
- numero d'assurance social 
- national identification number 
- national id 
- Sin # 
- soc ins 
- social ins 

#### <a name="keyword_sin_collaborative"></a>Keyword_sin_collaborative

- driver's license 
- drivers license 
- driver's licence 
- drivers licence 
- DOB 
- Data de Nascimento 
- Birthday 
- Date of Birth 

   
## <a name="chile-identity-card-number"></a>Número do cartão de identidade do Chile

### <a name="format"></a>Formatar

sete a oito dígitos mais delimitadores um dígito ou letra de verificação

### <a name="pattern"></a>Padrão

sete a oito dígitos mais delimitadores:
- um a dois dígitos 
- um período 
- três dígitos 
- um período 
- três dígitos 
- um traço 
- um dígito ou letra (não diferencia maiúscula de minúscula), que é um dígito de verificação

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_chile_id_card localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_chile_id_card for encontrada.
- A soma de verificação passa.

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_chile_id_card localiza o conteúdo que corresponde ao padrão.
- A soma de verificação passa.

```xml
<!-- Chile Identity Card Number -->
<Entity id="4e979794-49a0-407e-a0b9-2c536937b925" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_chile_id_card"/>
     <Match idRef="Keyword_chile_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_chile_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_chile_id_card"></a>Keyword_chile_id_card

- Número de Identificação Nacional 
- Cartão de identidade 
- ID 
- Identificador 
- Rol Único Nacional 
- SEJAM 
- Rol Único Tributario 
- ROTINA 
- Cédula de Identidad 
- Número De Identificación Nacional 
- Tarjeta de identificación 
- Identificación 

   
## <a name="china-resident-identity-card-prc-number"></a>Número do cartão de identidade residente (PRC) da China

### <a name="format"></a>Formatar

18 dígitos

### <a name="pattern"></a>Padrão

18 dígitos:
- seis dígitos que são um código de endereço 
- oito dígitos no formato AAAAMMDD que são a data de nascimento 
- três dígitos que são um código de pedido 
- um dígito que é um dígito de verificação

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_china_resident_id localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_china_resident_id for encontrada.
- A soma de verificação passa.

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_china_resident_id localiza o conteúdo que corresponde ao padrão.
- A soma de verificação passa.

```xml
<!-- China Resident Identity Card (PRC) Number -->
<Entity id="c92daa86-2d16-4871-901f-816b3f554fc1" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_china_resident_id"/>
     <Match idRef="Keyword_china_resident_id"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_china_resident_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

### <a name="keyword_china_resident_id"></a>Keyword_china_resident_id

- Cartão de Identidade da Polônia 
- POPULAR 
- Cartão de Identificação Nacional 
- 身份证 
- 居民 身份证 
- 居民身份证 
- 鉴定 
- 身分證 
- 居民 身份證
- 鑑定 

   
## <a name="credit-card-number"></a>Número do cartão de crédito

### <a name="format"></a>Formatar

14 a 16 dígitos que podem ser formatados ou não formatados (dddddddddddddddd) e que devem passar no teste Luhn.

### <a name="pattern"></a>Padrão

Padrão muito complexo e robusto que detecta cartões de todas as principais marcas em todo o mundo, incluindo Visa, MasterCard, Discover Card, JCB, American Express, vales-presentes e cartões diner.

### <a name="checksum"></a>Soma de verificação

Sim, a soma de verificação Luhn

### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_credit_card localiza conteúdo que corresponde ao padrão.
- Uma das seguintes opções for verdadeira:
    - Uma palavra-chave de Keyword_cc_verification for encontrada.
    - Uma palavra-chave de Keyword_cc_name for encontrada.
    - A função Func_expiration_date encontra uma data no formato de data à direita.
- A soma de verificação passa.

Uma política de DLP tem 65% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_credit_card localiza conteúdo que corresponde ao padrão.
- A soma de verificação passa.

```xml
<!-- Credit Card Number -->
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_cc_verification" />
          <Match idRef="Keyword_cc_name" />
          <Match idRef="Func_expiration_date" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_credit_card" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_cc_verification"></a>Keyword_cc_verification

- 
card verification

- card identification number
- cvn
- CID
- cvc2
- cvv2
- 
pin block
- security code

- security number

- security no

- issue number

- issue no
- cryptogramme
- 
numéro de sécurité
- numero de securite
- kreditkartenprüfnummer
- kreditkartenprufnummer
- prüfziffer
- prufziffer
- sicherheits Kode
- sicherheitscode
- sicherheitsnummer
- verfalldatum
- codice di verifica
- COD.sicurezza
- 
cod sicurezza
- n autorizzazione
- CFOP
- codigo
- COD.seg
- 
cod seg
- código de segurança

- codigo de seguranca

- codigo de segurança

- código de seguranca
- cód.segurança
- COD.seguranca
- COD.segurança
- cód.seguranca
- segurança do Cód
- seguranca c.o.d.
- segurança de COD
- cód seguranca
- número de verificação

- numero de verificacao
- ablauf
- gültig bis
- gültigkeitsdatum
- gultig bis
- gultigkeitsdatum
- scadenza
- 
data scad
- fecha de expiracion

- fecha de venc
- vencimiento
- 
válido hasta
- valido hasta
- vto
- 
data de expiração
- data de expiracao

- data em que expira
- validade
- coragem
- vencimento
- transação
- número da transação
- número de referência
- セキュリティコード
- セキュリティ コード
- セキュリティナンバー
- セキュリティ ナンバー
- セキュリティ番号

#### <a name="keyword_cc_name"></a>Keyword_cc_name

- amex
- american express
- americanexpress
- americano espresso

- Cartões
- MasterCard
- master card
- MC
- MasterCards
- 
master cards
- Clube do Diner
- diners club
- dinersclub
- tect
- discover card
- discovercard
- discover cards
- JCB
- BrandSmart
- japanese card bureau

- carte blanche
- carteblanche
- credit card
- colocado #
- CC #:
- Data de vencimento
- exp date

- 
expiry date
- 
date d’expiration
- 
date d'exp
- 
date expiration
- bank card
- bankcard
- 
card number
- card num
- cardnumber
- cardnumbers
- card numbers
- CreditCard
- credit cards
- creditcards
- CCN
- card holder
- aos
- card holders
- titulares de cartões
- check card
- checkcard
- check cards
- checkcards
- debit card
- debitcard
- debit cards
- debitcards
- atm card
- atmcard
- atm cards
- atmcards
- encaminhar
- 
en route
- card type

- Cardmember acct
- conta Cardmember
- Cardno
- Cartão corporativo
- Cartões corporativos
- Tipo de cartão
- número da conta de cartão
- conta de membro do cartão
- Cardmember acct.
- card no.

- n º do cartão
- card number

- carte bancaire

- carte de crédit

- carte de credit

- numéro de carte

- numero de carte

- nº de la carte

- nº de carte
- kreditkarte
- karte
- karteninhaber
- karteninhabers
- kreditkarteninhaber
- kreditkarteninstitut
- kreditkartentyp
- eigentümername
- kartennr
- kartennummer
- kreditkartennummer
- kreditkarten-nummer
- 
carta di credito
- carta credito
- n.n.n..carta
- n carta
- nr.carta
- 
nr carta
- numero carta

- numero della carta

- numero di carta

- tarjeta credito

- tarjeta de credito

- 
tarjeta crédito
- 
tarjeta de crédito
- tarjeta de atm

- tarjeta atm

- tarjeta debito

- tarjeta de debito

- 
tarjeta débito
- 
tarjeta de débito
- nº de tarjeta
- Não.de tarjeta
- nenhum de tarjeta
- numero de tarjeta

- número de tarjeta

- tarjeta no
- tarjetahabiente
- 
cartão de crédito
- cartão de credito

- cartao de crédito

- cartao de credito

- cartão de débito

- cartao de débito

- cartão de debito

- cartao de debito

- débito automático
- debito automatico

- 
número do cartão
- numero do cartão

- número do cartao

- numero do cartao

- número de cartão

- numero de cartão

- número de cartao

- numero de cartao

- n º do cartão
- nº do cartao
- n º.do cartão
- n º do cartão
- Não da carta
- Não.do cartão
- Não.do cartao
- クレジットカード番号
- クレジットカードナンバー
- クレジットカード＃
- クレジットカード
- クレジット
- クレカ
- カード番号
- カードナンバー
- カード＃
- アメックス
- アメリカンエクスプレス
- アメリカン エクスプレス
- Visaカード
- カード da visa
- マスターカード
- マスター カード
- マスター
- ダイナースクラブ
- ダイナース クラブ
- ダイナース
- 有効期限
- 期限
- キャッシュカード
- キャッシュ カード
- カード名義人
- カードの名義人
- カードの名義
- デビット カード
- デビットカード


## <a name="croatia-drivers-license-number"></a>Número da carteira de motorista da Croácia
Essa entidade de tipo de informação confidencial só está disponível no tipo de informações confidenciais do número de licença do driver da UE.

### <a name="format"></a>Formatar

oito dígitos sem espaços e delimitadores
  
### <a name="pattern"></a>Padrão

oito dígitos
  
### <a name="checksum"></a>Soma de verificação

Não
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A expressão regular  `Regex_croatia_eu_driver's_license_number` localiza o conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_croatia_eu_driver's_license_number` foi encontrada. 

```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Match idRef="Keywords_croatia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_croatia_eu_drivers_license_number"></a>Keywords_croatia_eu_driver ' s_license_number

- distribuição #
- driver license
- número de carteira de motorista
- licença de driver
- drivers driver'lic.
- drivers license
- drivers licence
- driver's license
- número da carteira de motorista
- número de licença do driver
- número da licença de dirigir
- dlno #
- vozačka dozvola


## <a name="croatia-identity-card-number"></a>Número do cartão de identidade da Croácia
Essa entidade de tipo de informação confidencial está incluída no tipo de informação confidencial do número de identificação nacional da UE e está disponível como uma entidade de tipo de informação confidencial autônoma.

### <a name="format"></a>Formatar

nove dígitos

### <a name="pattern"></a>Padrão

nove dígitos consecutivos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_croatia_id_card localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_croatia_id_card for encontrada.

```xml
<!--Croatia Identity Card Number-->
<Entity id="ff12f884-c20a-4189-b185-34c8e7258d47" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_id_card"/>
     <Match idRef="Keyword_croatia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_croatia_id_card"></a>Keyword_croatia_id_card

- majstorski broj građana
- número do cidadão mestre
- nacionalni identifikacijski broj
- número de identificação nacional
- NIB #
- NIB
- osobna iskaznica
- ID Osobni
- osobni identifikacijski broj
- número de identificação pessoal
- porezni broj
- porezni identifikacijski broj
- tax id

- identificação de imposto não
- número de identificação do imposto
- n º do imposto #
- n º do imposto
- número do imposto
- número de registro de imposto
- táxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID do Tin
- Tin não
- Tin #


## <a name="croatia-passport-number"></a>Número de passaporte da Croácia
Essa entidade de tipo de informação confidencial só está disponível no tipo de informação confidencial do número do Passport da UE.

### <a name="format"></a>Formatar

nove dígitos sem espaços e delimitadores
  
### <a name="pattern"></a>Padrão

nove dígitos 
  
### <a name="checksum"></a>Soma de verificação

Não
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_croatia_eu_passport_number` localiza o conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_croatia_eu_passport_number` foi encontrada. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```
### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_croatia_eu_passport_number"></a>Keywords_croatia_eu_passport_number

- passport number
- número de passaporte Croata
- Passport não
- broj putovnice

   
## <a name="croatia-personal-identification-oib-number"></a>Número de identificação pessoal da Croácia (NIB)

### <a name="format"></a>Formatar

11 dígitos

### <a name="pattern"></a>Padrão

11 dígitos:
- dez dígitos 
- o dígito final é um dígito de verificação

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_croatia_oib_number localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keywords_croatia_eu_tax_file_number for encontrada.
- A soma de verificação passa.

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_croatia_oib_number localiza o conteúdo que corresponde ao padrão.
- A soma de verificação passa.

```xml
      <!-- Croatia Personal Identification (OIB) Number -->
      <Entity id="31983b6d-db95-4eb2-a630-b44bd091968d" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_croatia_oib_number" />
          <Match idRef="Keywords_croatia_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_croatia_oib_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_croatia_oib_number"></a>Keyword_croatia_oib_number

- majstorski broj građana
- número do cidadão mestre
- nacionalni identifikacijski broj
- número de identificação nacional
- NIB #
- NIB
- osobna iskaznica
- ID Osobni
- osobni identifikacijski broj
- número de identificação pessoal
- porezni broj
- porezni identifikacijski broj
- tax id

- identificação de imposto não
- número de identificação do imposto
- n º do imposto #
- n º do imposto
- número do imposto
- número de registro de imposto
- táxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID do Tin
- Tin não
- Tin #

## <a name="croatia-social-security-number-or-equivalent-identification"></a>Número da segurança social da Croácia ou identificação equivalente
Essa entidade de tipo de informação confidencial só está disponível no número de seguridade social da UE ou no tipo de informações confidenciais de ID equivalente.

### <a name="format"></a>Formatar

11 dígitos sem espaços e delimitadores
  
### <a name="pattern"></a>Padrão

11 dígitos:
  
- dez dígitos
- um dígito de verificação
    
### <a name="checksum"></a>Soma de verificação

Sim
  
### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função  `Func_croatia_eu_ssn_or_equivalent` localiza conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_croatia_eu_ssn_or_equivalent` foi encontrada. 
    
Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função  `Func_croatia_eu_ssn_or_equivalent` localiza conteúdo que corresponde ao padrão. 
    
```xml
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

- número de identificação pessoal
- número do cidadão mestre
- national identification number
- social security number
- nationalnumber #
- es #
- es
- nationalnumber
- bnn #
- bnn
- número de identificação pessoal
- personalidnumber #
- NIB
- osobni identifikacijski broj

   
## <a name="cyprus-drivers-license-number"></a>Número de licença de drivers de Chipre
Essa entidade de tipo de informação confidencial só está disponível no tipo de informações confidenciais do número de licença do driver da UE.

### <a name="format"></a>Formatar

12 dígitos sem espaços e delimitadores
  
### <a name="pattern"></a>Padrão

12 dígitos
  
### <a name="checksum"></a>Soma de verificação

Não
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_cyprus_eu_driver's_license_number` localiza o conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_cyprus_eu_driver's_license_number` foi encontrada.

```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_cyprus_eu_drivers_license_number"></a>Keywords_cyprus_eu_driver ' s_license_number

- distribuição #
- driver license
- número de carteira de motorista
- licença de driver
- drivers driver'lic.
- drivers license
- drivers licence
- número da carteira de motorista
- número de licença do driver
- número da licença de dirigir
- dlno #
- άδεια οδήγησης


## <a name="cyprus-identity-card"></a>Cartão de identidade do Chipre

### <a name="format"></a>Formatar

dez dígitos sem espaços e delimitadores
  
### <a name="pattern"></a>Padrão

dez dígitos 
  
### <a name="checksum"></a>Soma de verificação

não aplicável
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_cyprus_eu_national_id_card` localiza o conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_cyprus_eu_national_id_card` foi encontrada. 
    
```xml 
      <!-- Cyprus Identity Card -->
      <Entity id="3ba8afe5-7a6c-4929-8247-0001b6878438" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_national_id_card" />
          <Match idRef="Keywords_cyprus_eu_national_id_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_cyprus_eu_national_id_card"></a>Keywords_cyprus_eu_national_id_card

- número do cartão de identificação
- número do cartão de identidade
- kimlik karti
- número de identificação nacional
- número de identificação pessoal
- ταυτοτητασ


## <a name="cyprus-passport-number"></a>Número de passaporte do Chipre
Essa entidade de tipo de informação confidencial só está disponível no tipo de informação confidencial do número do Passport da UE.

### <a name="format"></a>Formatar

uma letra seguida de 6-8 dígitos sem espaços ou delimitadores
  
### <a name="pattern"></a>Padrão

uma letra seguida de seis a oito dígitos
  
### <a name="checksum"></a>Soma de verificação

Não
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_cyprus_eu_passport_number` localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de  `Keywords_cyprus_eu_passport_number` foi encontrada. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_cyprus_eu_passport_number"></a>Keywords_cyprus_eu_passport_number

- passport number
- número de passaporte do Chipre
- Passport não
- αριθμό διαβατηρίου


## <a name="cyprus-tax-identification-number"></a>Número de identificação do imposto do Chipre

### <a name="format"></a>Formatar

oito dígitos e uma letra no padrão especificado
  
### <a name="pattern"></a>Padrão

oito dígitos e uma letra:
  
- um "0" ou "9"
- sete dígitos
- uma letra (não diferencia maiúsculas de minúsculas)
    
### <a name="checksum"></a>Soma de verificação

não aplicável
  
### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_cyprus_eu_tax_file_number` localiza conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_cyprus_eu_tax_file_number` foi encontrada. 
    
Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_cyprus_eu_tax_file_number` localiza conteúdo que corresponde ao padrão. 
    
```xml
      <!-- Cyprus Tax Identification Number -->
      <Entity id="40e64bd9-55f3-4a09-9bd6-1db18dced9dd" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
          <Match idRef="Keywords_cyprus_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_cyprus_eu_tax_file_number"></a>Keywords_cyprus_eu_tax_file_number

- tax id

- código de identificação de imposto
- identificação de imposto não
- número de identificação do imposto
- n º do imposto #
- n º do imposto
- número do imposto
- número de registro de imposto
- táxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- tic #
- tic
- ID do Tin
- Tin não
- Tin #
- vergi kimlik kodu
- vergi kimlik numarası
- αριθμός φορολογικού μητρώου
- κωδικός φορολογικού μητρώου
- φορολογική ταυτότητα
- φορολογικού κωδικού


## <a name="czech-drivers-license-number"></a>Número da carteira de motorista do tcheco
Essa entidade de tipo de informação confidencial só está disponível no tipo de informações confidenciais do número de licença do driver da UE.

### <a name="format"></a>Formatar

duas letras seguidas por seis dígitos
  
### <a name="pattern"></a>Padrão

oito letras e dígitos:
  
- duas letras (não diferencia maiúsculas de minúsculas)
- um espaço (opcional)
- seis dígitos

### <a name="checksum"></a>Soma de verificação

Não
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_czech_republic_eu_driver's_license_number` localiza o conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_czech_republic_eu_driver's_license_number` foi encontrada. 

```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_czech_republic_eu_drivers_license_number"></a>Keywords_czech_republic_eu_driver ' s_license_number

- distribuição #
- driver license
- número de carteira de motorista
- licença de driver
- drivers driver'lic.
- drivers license
- drivers licence
- driver's license
- número da carteira de motorista
- número da carteira de motorista
- número de licença do driver
- número da licença de dirigir
- dlno #
- řidičský prúkaz


## <a name="czech-passport-number"></a>Número de passaporte tcheco
Essa entidade de tipo de informação confidencial só está disponível no tipo de informação confidencial do número do Passport da UE.

### <a name="format"></a>Formatar

oito dígitos sem espaços ou delimitadores
  
### <a name="pattern"></a>Padrão

oito dígitos sem espaços ou delimitadores
  
### <a name="checksum"></a>Soma de verificação

Não
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_czech_republic_eu_passport_number` localiza o conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_czech_republic_eu_passport_number` foi encontrada. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_czech_republic_eu_passport_number"></a>Keywords_czech_republic_eu_passport_number

- passport number
- número de passaporte tcheco
- Passport não
- Pas cestovní
- Pas


## <a name="czech-personal-identity-number"></a>Número de identidade pessoal tcheco

### <a name="format"></a>Formatar

nove dígitos com barra de avanço opcional (formato antigo) dez dígitos com barra de avanço opcional (novo formato)

### <a name="pattern"></a>Padrão

nove dígitos (formato antigo):
- seis dígitos que representam a data de nascimento
- uma barra de avanço opcional
- três dígitos

dez dígitos (novo formato):
- seis dígitos que representam a data de nascimento
- uma barra de avanço opcional 
- quatro dígitos onde o último dígito é um dígito de verificação

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:

- A função Func_czech_id_card localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_czech_id_card for encontrada.
- A soma de verificação passa.

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:

- A função Func_czech_id_card_new_format localiza o conteúdo que corresponde ao padrão.
- A soma de verificação passa.

```xml
<!-- Czech Personal Identity Number -->
      <!-- Czech Personal Identity Number -->
      <Entity id="60c0725a-4eb6-455b-9dda-05d8a7396497" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_czech_id_card" />
          <Match idRef="Keyword_czech_id_card" />
        </Pattern>
        <Version minEngineVersion="15.20.3000.000">
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Func_czech_id_card_new_format" />
          </Pattern>
        </Version>
      </Entity>
```
### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_czech_id_card"></a>Keyword_czech_id_card

- número de nascimento
- ID da República Tcheca
- czechidno #
- daňové číslo
- identifikační číslo
- identidade não
- número de identidade
- identityno #
- identityno
- número de seguro
- número de identificação nacional
- nationalnumber #
- número nacional
- osobní číslo
- personalidnumber #
- número de identificação pessoal
- número de identificação pessoal
- número pessoal
- atos #
- atos
- pojištění číslo
- rč
- rodne cislo
- rodné číslo
- es
- es #
- social security number

- tax id

- identificação de imposto não
- número de identificação do imposto
- n º do imposto #
- n º do imposto
- número do imposto
- número de registro de imposto
- táxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID do Tin
- Tin não
- Tin #
- número de identificação exclusivo


## <a name="czech-social-security-number-or-equivalent-identification"></a>Número de seguro social ou identificação equivalente

Essa entidade de tipo de informação confidencial só está disponível no número de seguridade social da UE ou no tipo de informações confidenciais de ID equivalente.

### <a name="format"></a>Formatar

dez dígitos e uma barra invertida no padrão especificado
  
### <a name="pattern"></a>Padrão

dez dígitos e uma barra invertida:
  
- seis dígitos que correspondem à data de nascimento (AAMMDD): 
- uma barra invertida
- três dígitos que correspondem a um número de série que separa as pessoas nasceu na mesma data
- um dígito de verificação
    
### <a name="checksum"></a>Soma de verificação

Sim
  
### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_czech_republic_eu_ssn_or_equivalent` localiza conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_czech_republic_eu_ssn_or_equivalent` foi encontrada. 
    
Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_czech_republic_eu_ssn_or_equivalent` localiza conteúdo que corresponde ao padrão. 

```xml
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

- número de nascimento
- national identification number
- número de identificação pessoal
- social security number
- nationalnumber #
- es #
- es
- número nacional
- número de identificação pessoal
- personalidnumber #
- rč
- rodné číslo
- rodne cislo


## <a name="denmark-drivers-license-number"></a>Número da carteira de motorista da Dinamarca
Essa entidade de tipo de informação confidencial só está disponível no tipo de informações confidenciais do número de licença do driver da UE.

### <a name="format"></a>Formatar

oito dígitos sem espaços e delimitadores
  
### <a name="pattern"></a>Padrão

oito dígitos
  
### <a name="checksum"></a>Soma de verificação

Sim
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_denmark_eu_driver's_license_number` localiza o conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_denmark_eu_driver's_license_number` foi encontrada. 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Match idRef="Keywords_denmark_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_denmark_eu_drivers_license_number"></a>Keywords_denmark_eu_driver ' s_license_number

- | DL #
- driver license
- número de carteira de motorista
- licença de driver
- drivers driver'lic.
- drivers license
- drivers licence
- driver's license
- número da carteira de motorista
- número de licença do driver
- número da licença de dirigir
- dlno #
- kørekort
- kørekortnummer


## <a name="denmark-passport-number"></a>Número de passaporte da Dinamarca
Essa entidade de tipo de informação confidencial só está disponível no tipo de informação confidencial do número do Passport da UE.

### <a name="format"></a>Formatar

nove dígitos sem espaços e delimitadores
  
### <a name="pattern"></a>Padrão

nove dígitos 
  
### <a name="checksum"></a>Soma de verificação

Não
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_denmark_eu_passport_number` localiza o conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_denmark_eu_passport_number` foi encontrada. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_denmark_eu_passport_number"></a>Keywords_denmark_eu_passport_number

- passport number
- número de passaporte dinamarquês
- Passport não
- Pas
- pasnummer


## <a name="denmark-personal-identification-number"></a>Número de identificação pessoal da Dinamarca
Essa entidade de tipo de informação confidencial está incluída no tipo de informação confidencial do número de identificação nacional da UE e está disponível como uma entidade de tipo de informação confidencial autônoma.

### <a name="format"></a>Formatar

dez dígitos contendo um hífen

### <a name="pattern"></a>Padrão

dez dígitos:
- seis dígitos no formato DDMMAA que são a data de nascimento 
- um hífen 
- quatro dígitos em que o último dígito é um dígito de verificação

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular Func_denmark_eu_tax_file_number localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_denmark_id for encontrada.
- A soma de verificação passa.

Uma política de DLP tem 65% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular Func_denmark_eu_tax_file_number localiza o conteúdo que corresponde ao padrão.
- A soma de verificação passa.

```xml
<!-- Denmark Personal Identification Number -->
      <!-- Denmark Personal Identification Number -->
      <Entity id="6c4f2fef-56e1-4c00-8093-88d7a01cf460" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
          <Match idRef="Keyword_denmark_id" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_denmark_id"></a>Keyword_denmark_id

- centrale personregister
- registreringssystem civil
- pedir
- pedir #
- gesundheitskarte nummer
- gesundheitsversicherungkarte nummer
- cartão de saúde
- número do cartão de seguro de saúde
- número de seguro de saúde
- identification number

- identifikationsnummer
- identifikationsnummer #
- número de identidade
- krankenkassennummer
- nationalid #
- nationalnumber #
- número nacional
- personalidnumber #
- personalidentityno #
- número de identificação pessoal
- personnummer
- personnummer #
- reisekrankenversicherungskartenummer
- rejsesygesikringskort
- es
- es #
- ID Skat
- skat kode
- skat nummer
- skattenummer
- social security number

- sundhedsforsikringskort
- sundhedsforsikringsnummer
- sundhedskort
- sundhedskortnummer
- sygesikring
- sygesikringkortnummer
- código de imposto
- cartão de seguro de saúde de viagem
- uniqueidentityno #
- número do imposto
- número de registro de imposto
- tax id

- número de identificação do imposto
- táxi #
- taxnumber #
- n º do imposto
- taxno #
- taxnumber
- identificação de imposto não
- Tin #
- taxidno #
- taxidnumber #
- n º do imposto #
- ID do Tin
- Tin não
- cpr.nr
- cprnr
- cprnummer
- personnr
- personregister
- sygesikringsbevis
- sygesikringsbevisnr
- sygesikringsbevisnummer
- sygesikringskort
- sygesikringskortnr
- sygesikringskortnummer
- sygesikringsnr
- sygesikringsnummer


## <a name="denmark-social-security-number-or-equivalent-identification"></a>Número da segurança social da Dinamarca ou identificação equivalente
Essa entidade de tipo de informação confidencial só está disponível no número de segurança social da UE ou no tipo de informação confidencial de ID equivalente.

### <a name="format"></a>Formatar

dez dígitos e um hífen no padrão especificado
  
### <a name="pattern"></a>Padrão

dez dígitos e um hífen:
  
- seis dígitos que correspondem à data de nascimento (DDMMAA) 
- um hífen
- quatro dígitos que correspondem a um número de sequência

### <a name="checksum"></a>Soma de verificação

Sim
  
### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_denmark_eu_ssn_or_equivalent` localiza conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_denmark_eu_ssn_or_equivalent` foi encontrada. 
    
Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_denmark_eu_ssn_or_equivalent` localiza conteúdo que corresponde ao padrão. 
    
```xml
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

- número de identificação pessoal
- national identification number
- social security number
- nationalnumber #
- es #
- es
- número nacional
- número de identificação pessoal
- personalidnumber #
- CPR-Nummer
- personnummer


## <a name="drug-enforcement-agency-dea-number"></a>Número da Agência de aplicação de medicamentos (DEA)

### <a name="format"></a>Formatar

duas letras seguidas por sete dígitos

### <a name="pattern"></a>Padrão

O padrão deve incluir todos os seguintes itens:
- uma letra (não diferencia maiúsculas de minúsculas) desse conjunto de possíveis letras: abcdefghjklmnprstux, que é um código inscrito 
- uma letra (não diferencia maiúsculas de minúsculas), que é a primeira letra do sobrenome do inscrito 
- sete dígitos, o último que é o dígito de verificação

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_dea_number localiza conteúdo que corresponde ao padrão.
- A soma de verificação passa.

```xml
<!-- DEA Number -->
<Entity id="9a5445ad-406e-43eb-8bd7-cac17ab6d0e4" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_dea_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

Nenhuma


## <a name="estonia-drivers-license-number"></a>Número da carteira de motorista do Estônia
Essa entidade de tipo de informação confidencial só está disponível no tipo de informações confidenciais do número de licença do driver da UE.

### <a name="format"></a>Formatar

duas letras seguidas por seis dígitos
  
### <a name="pattern"></a>Padrão

duas letras e seis dígitos:
  
- as letras "ET" (não diferencia maiúsculas de minúsculas) 
- seis dígitos
    
### <a name="checksum"></a>Soma de verificação

Não
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_estonia_eu_driver's_license_number` localiza o conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_estonia_eu_driver's_license_number` foi encontrada. 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Match idRef="Keywords_estonia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_estonia_eu_drivers_license_number"></a>Keywords_estonia_eu_driver ' s_license_number

- distribuição #
- driver license
- número de carteira de motorista
- número de carteira de motorista
- licença de driver
- drivers driver'lic.
- drivers license
- drivers licence
- driver's license
- número da carteira de motorista
- número da licença de dirigir
- dlno #
- permis de conduire


## <a name="estonia-personal-identification-code"></a>Estônia código de identificação pessoal

### <a name="format"></a>Formatar

11 dígitos sem espaços e delimitadores
  
### <a name="pattern"></a>Padrão

11 dígitos:
  
- um dígito que corresponde ao sexo e ao século de nascimento (número ímpar masculino, mesmo número fêmea; 1-2:19 Century; 3-4:20 Century; 5-6:21 século)
- seis dígitos que correspondem à data de nascimento (AAMMDD)
- três dígitos que correspondem a um número de série separando as pessoas que nasceu na mesma data
- um dígito de verificação
    
### <a name="checksum"></a>Soma de verificação

Sim
  
### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_estonia_eu_national_id_card` localiza conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_estonia_eu_national_id_card` foi encontrada. 
    
Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_estonia_eu_national_id_card` localiza conteúdo que corresponde ao padrão. 
    
```xml
      <!-- Estonia Personal Identification Code -->
      <Entity id="bfb26de6-dad5-4d48-ab72-4789cdd0654c" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_estonia_eu_national_id_card" />
          <Match idRef="Keywords_estonia_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_estonia_eu_national_id_card" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_estonia_eu_telephone_number" />
            <Match idRef="Keywords_estonia_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_estonia_eu_national_id_card"></a>Keywords_estonia_eu_national_id_card

- ID-kaart
- IKMover
- isikukood #
- isikukood
- ID maksu
- maksukohustuslase identifitseerimisnumber
- maksunumber
- número de identificação nacional
- número nacional
- código pessoal
- número de identificação pessoal
- código de identificação pessoal
- número de identificação pessoal
- personalidnumber #
- tax id

- identificação de imposto não
- número de identificação do imposto
- n º do imposto #
- n º do imposto
- número do imposto
- número de registro de imposto
- táxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID do Tin
- Tin não
- Tin #


## <a name="estonia-passport-number"></a>Número de passaporte da Estônia
Essa entidade de tipo de informação confidencial só está disponível no tipo de informação confidencial do número do Passport da UE.

### <a name="format"></a>Formatar

uma letra seguida por sete dígitos sem espaços ou delimitadores
  
### <a name="pattern"></a>Padrão

uma letra seguida por sete dígitos
  
### <a name="checksum"></a>Soma de verificação

Não
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_estonia_eu_passport_number` localiza o conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_estonia_eu_passport_number` foi encontrada. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_estonia_eu_passport_number"></a>Keywords_estonia_eu_passport_number

- passport number
- número de passaporte estoniano
- Passport não
- Eesti kodaniku

## <a name="eu-debit-card-number"></a>Número de cartão de débito da UE

### <a name="format"></a>Formatar

16 dígitos

### <a name="pattern"></a>Padrão

Padrão muito complexo e robusto

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_eu_debit_card localiza conteúdo que corresponde ao padrão.
- Pelo menos uma das seguintes opções for verdadeira:
    - Uma palavra-chave de Keyword_eu_debit_card for encontrada.
    - Uma palavra-chave de Keyword_card_terms_dict for encontrada.
    - Uma palavra-chave de Keyword_card_security_terms_dict for encontrada.
    - Uma palavra-chave de Keyword_card_expiration_terms_dict for encontrada.
    - A função Func_expiration_date encontra uma data no formato de data à direita.
- A soma de verificação passa.

```xml
    <!-- EU Debit Card Number -->
    <Entity id="0e9b3178-9678-47dd-a509-37222ca96b42" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_eu_debit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_eu_debit_card" />
          <Match idRef="Keyword_card_terms_dict" />
          <Match idRef="Keyword_card_security_terms_dict" />
          <Match idRef="Keyword_card_expiration_terms_dict" />
          <Match idRef="Func_expiration_date" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_eu_debit_card"></a>Keyword_eu_debit_card

- account number 
- card number 
- card no. 
- security number 
- colocado # 

#### <a name="keyword_card_terms_dict"></a>Keyword_card_terms_dict

- acct nbr 
- acct num 
- acct no 
- american express 
- americanexpress 
- americano espresso 
- amex 
- atm card 
- atm cards 
- atm kaart 
- atmcard 
- atmcards 
- atmkaart 
- atmkaarten 
- bancontact 
- bank card 
- bankkaart 
- card holder 
- card holders 
- card num 
- card number 
- card numbers 
- card type 
- cardano numerico 
- aos 
- titulares de cartões 
- cardnumber 
- cardnumbers 
- carta bianca 
- carta credito 
- carta di credito 
- cartao de credito 
- cartao de crédito 
- cartao de debito 
- cartao de débito 
- carte bancaire 
- carte blanche 
- carte bleue 
- carte de credit 
- carte de crédit 
- carte di credito 
- carteblanche 
- cartão de credito 
- cartão de crédito 
- cartão de debito 
- cartão de débito 
- cb 
- CCN 
- check card 
- check cards 
- checkcard
- checkcards 
- chequekaart 
- Cirrus 
- Cirrus-EDC-maestro 
- controlekaart 
- controlekaarten 
- credit card 
- credit cards 
- CreditCard 
- creditcards 
- debetkaart 
- debetkaarten 
- debit card 
- debit cards 
- debitcard 
- debitcards 
- debito automatico 
- diners club 
- dinersclub 
- tect 
- discover card 
- discover cards 
- discovercard 
- discovercards 
- débito automático
- edc 
- eigentümername 
- european debit card 
- hoofdkaart 
- hoofdkaarten 
- in viaggio 
- japanese card bureau 
- japanse kaartdienst 
- JCB 
- kaart 
- kaart num 
- kaartaantal 
- kaartaantallen 
- kaarthouder 
- kaarthouders 
- karte  
- karteninhaber 
- karteninhabers
- kartennr 
- kartennummer 
- kreditkarte 
- kreditkarten-nummer 
- kreditkarteninhaber 
- kreditkarteninstitut 
- kreditkartennummer 
- kreditkartentyp 
- Maestro 
- master card 
- master cards 
- MasterCard 
- MasterCards 
- MC 
- mister cash 
- n carta 
- carta 
- no de tarjeta 
- no do cartao 
- no do cartão 
- Não. de tarjeta 
- Não. do cartao 
- Não. do cartão 
- nr carta 
- nr. carta 
- numeri di scheda 
- numero carta 
- numero de cartao 
- numero de carte 
- numero de cartão 
- numero de tarjeta
- numero della carta 
- numero di carta 
- numero di scheda 
- numero do cartao 
- numero do cartão 
- numéro de carte 
- nº carta 
- nº de carte 
- nº de la carte 
- nº de tarjeta 
- nº do cartao 
- nº do cartão 
- n º. do cartão 
- número de cartao 
- número de cartão 
- número de tarjeta 
- número do cartao 
- scheda dell'assegno 
- scheda dell'atmosfera 
- scheda dell'atmosfera 
- scheda della banca 
- scheda di controllo 
- scheda di debito 
- scheda matrice 
- schede dell'atmosfera 
- schede di controllo 
- schede di debito 
- schede matrici 
- scoprono la scheda 
- scoprono le schede 
- individual 
- supporti di scheda 
- supporto di scheda 
- Vá 
- tarjeta atm 
- tarjeta credito 
- tarjeta de atm 
- tarjeta de credito 
- tarjeta de debito 
- tarjeta debito 
- tarjeta no
- tarjetahabiente 
- tipo della scheda 
- ufficio giapponese della 
- scheda 
- v pay 
- v-Pay 
- cartões 
- visa plus 
- visa electron 
- previsto 
- visum 
- vpay   

#### <a name="keyword_card_security_terms_dict"></a>Keyword_card_security_terms_dict

- card identification number
- card verification 
- cardi la verifica 
- CID 
- cod seg 
- cod seguranca 
- cod segurança 
- cod sicurezza 
- COD. seg 
- COD. seguranca 
- COD. segurança 
- COD. sicurezza 
- codice di sicurezza 
- codice di verifica 
- codigo 
- codigo de seguranca 
- codigo de segurança 
- crittogramma 
- cryptogram 
- cryptogramme 
- cv2 
- cvc 
- cvc2 
- cvn 
- cvv 
- cvv2 
- cód seguranca 
- cód segurança 
- cód. seguranca 
- cód. segurança 
- CFOP 
- código de seguranca 
- código de segurança 
- de kaart controle 
- geeft nr uit 
- issue no 
- issue number 
- kaartidentificatienummer 
- kreditkartenprufnummer 
- kreditkartenprüfnummer 
- kwestieaantal 
- Não. dell'edizione 
- Não. di sicurezza 
- numero de securite 
- numero de verificacao 
- numero dell'edizione 
- numero di identificazione della 
- scheda 
- numero di sicurezza 
- numero van veiligheid 
- numéro de sécurité 
- nº autorizzazione 
- número de verificação 
- perno il blocco 
- pin block 
- prufziffer 
- prüfziffer 
- security code 
- security no 
- security number 
- sicherheits kode 
- sicherheitscode 
- sicherheitsnummer 
- speldblok 
- veiligheid nr 
- veiligheidsaantal 
- veiligheidscode 
- veiligheidsnummer 
- verfalldatum 

#### <a name="keyword_card_expiration_terms_dict"></a>Keyword_card_expiration_terms_dict

- ablauf 
- data de expiracao 
- data de expiração 
- data del exp 
- data di exp 
- data di scadenza 
- data em que expira 
- data scad 
- data scadenza 
- date de validité 
- datum afloop 
- datum van exp 
- de afloop 
- espira 
- espira 
- exp date 
- exp datum 
- validade 
- expirar 
- expira 
- expiração 
- fecha de expiracion 
- fecha de venc 
- gultig bis 
- gultigkeitsdatum 
- gültig bis 
- gültigkeitsdatum 
- la scadenza 
- scadenza 
- valable 
- validade 
- valido hasta 
- coragem 
- venc 
- vencimento 
- vencimiento 
- verloopt 
- vervaldag 
- vervaldatum 
- vto 
- válido hasta 


## <a name="eu-drivers-license-number"></a>Número da carteira de motorista da UE

Estas são as entidades no tipo de informação confidencial do número da carteira de motorista da UE.

- [Áustria ](#austria-drivers-license-number) 
- [Bélgica](#belgium-drivers-license-number)
- [Bulgária](#bulgaria-drivers-license-number)
- [Croácia ](#croatia-drivers-license-number)
- [Chipre](#cyprus-drivers-license-number)
- [Tcheco](#czech-drivers-license-number)
- [Dinamarca](#denmark-drivers-license-number)
- [Estônia](#estonia-drivers-license-number)
- [Finlândia ](#finland-drivers-license-number)
- [França ](#france-drivers-license-number) 
- [Alemanha ](#germany-drivers-license-number)
- [Grécia](#greece-drivers-license-number)
- [Hungria](#hungary-drivers-license-number)
- [Irlanda](#ireland-drivers-license-number)
- [Itália](#italy-drivers-license-number)
- [Letônia](#latvia-drivers-license-number)
- [Lituânia ](#lithuania-drivers-license-number)
- [Luxemburg](#luxemburg-drivers-license-number)
- [Malta](#malta-drivers-license-number)
- [Países Baixos](#netherlands-drivers-license-number)
- [Polônia](#poland-drivers-license-number) 
- [Portugal](#portugal-drivers-license-number)
- [Romênia](#romania-drivers-license-number)
- [Eslováquia](#slovakia-drivers-license-number)
- [Eslovênia](#slovenia-drivers-license-number)
- [Espanha](#spain-drivers-license-number)
- [Suécia](#sweden-drivers-license-number)
- [britânico](#uk-drivers-license-number)


## <a name="eu-national-identification-number"></a>Número de identificação nacional da UE

Estas são as entidades no tipo de informação confidencial do número de identificação nacional da UE.

- [Áustria ](#austria-identity-card)
- [Bélgica](#belgium-national-number)
- [Bulgária](#bulgaria-uniform-civil-number)
- [Croácia ](#croatia-identity-card-number)
- [Chipre](#cyprus-identity-card)
- [Tcheco](#czech-personal-identity-number)
- [Dinamarca](#denmark-personal-identification-number)
- [Estônia](#estonia-personal-identification-code)
- [Finlândia ](#finland-national-id)
- [França ](#france-national-id-card-cni)
- [Alemanha ](#germany-identity-card-number)
- [Grécia](#greece-national-id-card)
- [Hungria](#hungary-personal-identification-number)
- [Irlanda](#ireland-personal-public-service-pps-number)
- [Itália](#italy-fiscal-code)
- [Letônia](#latvia-personal-code)
- [Lituânia ](#lithuania-personal-code)
- [Luxemburg](#luxemburg-national-identification-number-natural-persons)
- [Malta](#malta-identity-card-number)
- [Países Baixos](#netherlands-citizens-service-bsn-number)
- [Polônia](#poland-national-id-pesel)
- [Portugal](#portugal-citizen-card-number)
- [Romênia](#romania-personal-numeric-code-cnp)
- [Eslováquia](#slovakia-personal-number)
- [Eslovênia](#slovenia-unique-master-citizen-number)
- [Espanha](#spain-dni)
- [britânico](#uk-national-insurance-number-nino)                                        


## <a name="eu-passport-number"></a>Número do Passport da UE 

Estas são as entidades no número do Passport da UE informações confidenciais typeThese são as entidades no pacote de números do Passport da UE.

- [Áustria ](#austria-passport-number)
- [Bélgica](#belgium-passport-number)
- [Bulgária](#bulgaria-passport-number)
- [Croácia ](#croatia-passport-number)
- [Chipre](#cyprus-passport-number)
- [Tcheco](#czech-passport-number)
- [Dinamarca](#denmark-passport-number)
- [Estônia](#estonia-passport-number)
- [Finlândia ](#finland-passport-number)
- [França ](#france-passport-number)
- [Alemanha ](#germany-passport-number)
- [Grécia](#greece-passport-number)
- [Hungria](#hungary-passport-number)
- [Irlanda](#ireland-passport-number)
- [Itália](#italy-passport-number)
- [Letônia](#latvia-passport-number)
- [Lituânia ](#lithuania-passport-number)
- [Luxemburg](#luxemburg-passport-number)
- [Malta](#malta-passport-number)
- [Países Baixos](#netherlands-passport-number)
- [Polônia](#poland-passport-number)
- [Portugal](#portugal-passport-number)
- [Romênia](#romania-passport-number)
- [Eslováquia](#slovakia-passport-number)
- [Eslovênia](#slovenia-passport-number)
- [Espanha](#spain-passport-number)
- [Suécia](#sweden-passport-number)
- [britânico](#us--uk-passport-number)


## <a name="eu-social-security-number-or-equivalent-identification"></a>Número de seguro social da UE ou identificação equivalente

Estas são as entidades que estão no número de segurança social da UE ou tipo de informação confidencial de identificação equivalente.

- [Áustria ](#austria-social-security-number-or-equivalent-identification)
- [Bélgica](#belgium-social-security-number-or-equivalent-identification)
- [Croácia ](#croatia-social-security-number-or-equivalent-identification)
- [Tcheco](#czech-social-security-number-or-equivalent-identification)
- [Dinamarca](#denmark-social-security-number-or-equivalent-identification)
- [Finlândia ](#finland-social-security-number-or-equivalent-identification)
- [França ](#france-social-security-number-insee-or-equivalent-identification)
- [Alemanha ](#germany-identity-card-number)
- [Grécia](#greece-national-id-card)
- [Hungria](#hungary-social-security-number-or-equivalent-identification)
- [Portugal](#portugal-citizen-card-number)
- [Espanha](#spain-social-security-number-ssn)
- [Suécia](#sweden-social-security-number-or-equivalent-identification)


## <a name="eu-tax-identification-number"></a>Número de identificação do imposto da UE

Essas entidades estão no tipo de informação confidencial do número de identificação de imposto da UE.

- [Áustria ](#austria-tax-identification-number)
- [Bélgica](#belgium-national-number)
- [Bulgária](#bulgaria-uniform-civil-number)
- [Croácia ](#croatia-identity-card-number)
- [Chipre](#cyprus-tax-identification-number)
- [Tcheco](#czech-personal-identity-number)
- [Dinamarca](#denmark-personal-identification-number)
- [Estônia](#estonia-personal-identification-code)
- [Finlândia ](#finland-national-id)
- [França ](#france-tax-identification-number)
- [Alemanha ](#germany-tax-identification-number)
- [Grécia](#greece-tax-identification-number)
- [Hungria](#hungary-tax-identification-number)
- [Irlanda](#ireland-personal-public-service-pps-number)
- [Itália](#italy-fiscal-code)
- [Letônia](#latvia-personal-code)
- [Lituânia ](#lithuania-personal-code)
- [Luxemburg](#luxemburg-national-identification-number-non-natural-persons)
- [Malta](#malta-tax-identification-number)
- [Países Baixos](#netherlands-tax-identification-number)
- [Polônia](#poland-tax-identification-number)
- [Portugal](#portugal-tax-identification-number)
- [Romênia](#romania-personal-numeric-code-cnp)
- [Eslováquia](#slovakia-personal-number)
- [Eslovênia](#slovenia-tax-identification-number)
- [Espanha](#spain-tax-identification-number)
- [Suécia](#sweden-tax-identification-number)
- [britânico](#uk-unique-taxpayer-reference-number)


## <a name="finland-drivers-license-number"></a>Número da carteira de motorista do Finlândia
Essa entidade de tipo de informação confidencial só está disponível no tipo de informações confidenciais do número de licença do driver da UE.

### <a name="format"></a>Formatar

dez dígitos contendo um hífen
  
### <a name="pattern"></a>Padrão

dez dígitos contendo um hífen:
  
- seis dígitos 
- um hífen
- quatro dígitos 
    
### <a name="checksum"></a>Soma de verificação

Não
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_finland_eu_driver's_license_number` localiza o conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_finland_eu_driver's_license_number` foi encontrada. 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Match idRef="Keywords_finland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_finland_eu_drivers_license_number"></a>Keywords_finland_eu_driver ' s_license_number

- distribuição #
- driver license
- número de carteira de motorista
- licença de driver
- drivers driver'lic.
- drivers license
- drivers licence
- driver's license
- número da carteira de motorista
- número de licença do driver
- número da licença de dirigir
- dlno #
- ajokortti


## <a name="finland-european-health-insurance-number"></a>Número de seguro de saúde da Finlândia

### <a name="format"></a>Formatar

número de 20 dígitos

### <a name="pattern"></a>Padrão

número de 20 dígitos:

- dez dígitos-8024680246
- um espaço ou hífen opcional
- dez dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A Regex_Finland_European_Health_Insurance_Number Regex localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_Finland_European_Health_Insurance_Number for encontrada.

```xml
      <!-- Finland European Health Insurance Number -->
      <Entity id="60f75aed-81bf-4625-89b0-0846b9248ee7" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_Finland_European_Health_Insurance_Number"/>
          <Match idRef="Keyword_Finland_European_Health_Insurance_Number"/>
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_finland_european_health_insurance_number"></a>Keyword_finland_european_health_insurance_number

- ehic #
- ehic
- finlandehicnumber #
- finska sjukförsäkringskort
- cartão de saúde
- cartão de seguro de saúde
- número de seguro de saúde
- hälsokort
- sairaanhoitokortin
- sairausvakuutuskortti
- sairausvakuutusnumero
- sjukförsäkring nummer
- sjukförsäkringskort
- suomen sairausvakuutuskortti
- terveyskortti


## <a name="finland-national-id"></a>ID nacional da Finlândia

### <a name="format"></a>Formatar

seis dígitos mais um caractere indicando um século mais três dígitos mais um dígito de verificação

### <a name="pattern"></a>Padrão

O padrão deve incluir todos os seguintes itens:
- seis dígitos no formato de formato DDMMAA que são uma data de nascimento 
- marcador de século ('-', ' + ' ou ' a ') 
- número de identificação pessoal de três dígitos 
- um dígito ou letra (não diferencia maiúsculas de minúsculas), que é um dígito de verificação

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- a função Func_finnish_national_id localiza o conteúdo que corresponde ao padrão
- uma palavra-chave de Keyword_finnish_national_id for encontrada
- o checksum passa

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- a função Func_finnish_national_id localiza o conteúdo que corresponde ao padrão
- o checksum passa

```xml
      <!-- Finnish National ID-->
      <Entity id="338FD995-4CB5-4F87-AD35-79BD1DD926C1" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finnish_national_id" />
          <Match idRef="Keyword_finnish_national_id" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_finnish_national_id" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

- ainutlaatuinen henkilökohtainen tunnus
- henkilökohtainen tunnus
- henkilötunnus
- henkilötunnusnumero #
- henkilötunnusnumero
- hetu
- ID não
- número de identificação
- identification number

- identiteetti numero
- número de identidade
- idnumber
- kansallinen henkilötunnus
- kansallisen henkilökortin
- cartão de ID nacional
- n º de ID nacional
- ID pessoal
- código de identidade pessoal
- personalidnumber #
- personbeteckning
- personnummer
- social security number

- sosiaaliturvatunnus
- tax id

- identificação de imposto não
- número de identificação do imposto
- n º do imposto #
- n º do imposto
- número do imposto
- número de registro de imposto
- táxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID do Tin
- Tin não
- Tin #
- tunnistenumero
- tunnus numero
- tunnusluku
- tunnusnumero
- verokortti
- veronumero
- verotunniste
- verotunnus


## <a name="finland-passport-number"></a>Número de passaporte da Finlândia
Essa entidade de tipo de informação confidencial está disponível no tipo de informação confidencial do número do Passport da UE e está disponível como uma entidade de tipo de informação confidencial autônoma.

### <a name="format"></a>Formatar
combinação de nove letras e dígitos

### <a name="pattern"></a>Padrão
combinação de nove letras e dígitos:
- duas letras (não diferencia maiúsculas de minúsculas) 
- sete dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular Regex_finland_passport_number localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_finland_passport_number for encontrada.

```xml
<!-- Finland Passport Number -->
<Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_finland_passport_number"/>
     <Match idRef="Keyword_finland_passport_number"/>
  </Pattern>
</Entity>
```
### <a name="keywords"></a>Palavras-chave

- Keyword_finland_passport_number
- Passaport
- Passi


## <a name="finland-social-security-number-or-equivalent-identification"></a>Número de segurança social da Finlândia ou identificação equivalente
Essa entidade de tipo de informação confidencial só está disponível no número de seguridade social da UE ou no tipo de informações confidenciais de ID equivalente.

### <a name="format"></a>Formatar

Uma combinação de 11 caracteres no formato especificado
  
### <a name="pattern"></a>Padrão

uma combinação de 11 caracteres no formato especificado:
  
- seis dígitos 
- uma instância de um dos seguintes:
  - símbolo de adição
  - símbolo de subtração
  - a letra "A" (não diferencia maiúsculas de minúsculas)
- três dígitos
- uma letra ou um dígito
    
### <a name="checksum"></a>Soma de verificação

Sim
  
### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_finland_eu_ssn_or_equivalent` localiza conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_finland_eu_ssn_or_equivalent` foi encontrada. 
    
Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_finland_eu_ssn_or_equivalent` localiza conteúdo que corresponde ao padrão. 
    
```xml
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

- identification number
- ID pessoal
- número de identidade
- número de ID nacional da finlandês
- personalidnumber #
- national identification number
- número de identificação
- n º de ID nacional
- número de ID nacional
- ID não
- tunnistenumero
- henkilötunnus
- yksilöllinen henkilökohtainen tunnistenumero
- ainutlaatuinen henkilökohtainen tunnus
- identiteetti numero
- suomen kansallinen henkilötunnus
- henkilötunnusnumero #
- kansallisen tunnistenumero
- tunnusnumero
- kansallinen tunnus numero
- hetu


## <a name="france-drivers-license-number"></a>Número da carteira de motorista da França
Essa entidade de tipo de informação confidencial está disponível no tipo de informação confidencial do número de carteira do driver da UE e está disponível como uma entidade de tipo de informação confidencial autônoma.

### <a name="format"></a>Formatar

12 dígitos

### <a name="pattern"></a>Padrão

12 dígitos com a validação para descontar padrões similares, como números de telefone em francês

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- a função Func_french_drivers_license localiza o conteúdo que corresponde ao padrão.
- pelo menos uma das seguintes opções é verdadeira:
- uma palavra-chave de Keyword_french_drivers_license for encontrada.
- a função Func_eu_date localiza uma data no formato de data à direita.

```xml
<!-- France Driver's License Number -->
<Entity id="18e55a36-a01b-4b0f-943d-dc10282a1824" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_french_drivers_license" />
        <Any minMatches="1">
          <Match idRef="Keyword_french_drivers_license" />
          <Match idRef="Func_eu_date" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_french_drivers_license"></a>Keyword_french_drivers_license

- drivers licence
- drivers license
- driving licence
- driving licence
- permis de conduire
- licence number
- license number
- licence numbers
- license numbers


## <a name="france-health-insurance-number"></a>Número de seguro de saúde da França

### <a name="format"></a>Formatar

número de 21 dígitos

### <a name="pattern"></a>Padrão

número de 21 dígitos:

- dez dígitos
- um espaço opcional
- dez dígitos
- um espaço opcional
- um dígito


### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- a Regex_France_Health_Insurance_Number Regex localiza o conteúdo que corresponde ao padrão.
- uma palavra-chave de Keyword_France_Health_Insurance_Number for encontrada.

```xml
      <!-- France Health Insurance Number -->
      <Entity id="9bc2069e-76df-4ff9-ac02-2f519469e236" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_France_Health_Insurance_Number"/>
          <Match idRef="Keyword_France_Health_Insurance_Number"/>
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_france_health_insurance_number"></a>Keyword_France_health_insurance_number

- cartão de seguro
- Vitale carte
- d'assuré-social carte


## <a name="france-national-id-card-cni"></a>Cartão de ID nacional da França (CNI)

### <a name="format"></a>Formatar

12 dígitos

### <a name="pattern"></a>Padrão

12 dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem 65% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular Regex_france_cni localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keywords_france_eu_national_id_card for encontrada.

```xml
    <!-- France CNI -->
    <Entity id="f741ac74-1bc0-4665-b69b-f0c7f927c0c4" patternsProximity="300" recommendedConfidence="65">
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_france_cni" />
        <Match idRef="Keywords_france_eu_national_id_card" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_france_eu_national_id_card"></a>Keywords_france_eu_national_id_card

- card number

- Nationale carte d'identité
- Nationale carte d'idenite
- CNI #
- CNI
- compte bancaire
- número de identificação nacional
- identidade nacional
- nationalidno #
- numéro d'assurance maladie
- Numéro de Carte Vitale

   
## <a name="france-passport-number"></a>Número de passaporte da França
Essa entidade de tipo de informação confidencial está disponível no tipo de informação confidencial do número do Passport da UE e está disponível como uma entidade de tipo de informação confidencial autônoma.

### <a name="format"></a>Formatar

nove dígitos e letras

### <a name="pattern"></a>Padrão

nove dígitos e letras:
- dois dígitos 
- duas letras (não diferencia maiúsculas de minúsculas) 
- cinco dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_fr_passport localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_passport for encontrada.

```xml
<!-- France Passport Number -->
<Entity id="3008b884-8c8c-4cd8-a289-99f34fc7ff5d" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_fr_passport" />
        <Match idRef="Keyword_passport" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_passport"></a>Keyword_passport

- Passport Number
- Passport No
- Passport #
- Passaport #
- Passportid
- Passportno
- passportnumber
- パスポート
- パスポート番号
- パスポートのNum
- パスポート ＃ 
- Numéro de passeport
- Passeport n °
- Passeport Non
- Passeport #
- Passeport #
- PasseportNon
- Passeportn °

      
## <a name="france-social-security-number-insee-or-equivalent-identification"></a>Número de segurança social da França (INSEE) ou identificação equivalente
Essa entidade de tipo de informação confidencial está incluída no número de segurança social da UE e o tipo de informação confidencial de ID equivalente e está disponível como uma entidade de tipo de informação confidencial autônoma.

### <a name="format"></a>Formatar

15 dígitos

### <a name="pattern"></a>Padrão

Deve corresponder a um dos dois padrões:
- 13 dígitos seguidos de um espaço seguido de dois dígitos<br/>
ou
- 15 dígitos consecutivos

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política de DLP tem 95% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_french_insee ou Func_fr_insee localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_fr_insee for encontrada.
- A soma de verificação passa.

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_french_insee ou Func_fr_insee localiza o conteúdo que corresponde ao padrão.
- Nenhuma palavra-chave de Keyword_fr_insee for encontrada.
- A soma de verificação passa.

```xml
<!-- France INSEE -->
<Entity id="71f62b97-efe0-4aa1-aa49-e14de253619d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="95">
        <IdMatch idRef="Func_french_insee" />
        <Match idRef="Func_fr_insee" />
        <Any minMatches="1">
          <Match idRef="Keyword_fr_insee" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_french_insee" />
        <Match idRef="Func_fr_insee" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_fr_insee" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_fr_insee"></a>Keyword_fr_insee

- INSEE
- securité sociale
- securite sociale
- national id
- national identification
- numéro d'identité
- no d'identité
- Não. d'identité
- numero d'identite
- no d'identite
- Não. d'identite
- social security number
- social security code
- social insurance number
- le numéro d'identification nationale
- d'identité nationale
- numéro de sécurité sociale
- le code de la sécurité sociale
- numéro d'assurance sociale
- numéro de sécu
- code sécu 

## <a name="france-tax-identification-number"></a>Número de identificação de imposto da França

### <a name="format"></a>Formatar

13 dígitos
  
### <a name="pattern"></a>Padrão

13 dígitos
  
- Um dígito que deve ser 0, 1, 2 ou 3
- 1 dígito
- Um espaço (opcional)
- 2 dígitos 
- Um espaço (opcional)
- 3 dígitos 
- Um espaço (opcional)
- 3 dígitos 
- Um espaço (opcional)
- 3 dígitos de verificação 

  
### <a name="checksum"></a>Soma de verificação

Sim
  
### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_france_eu_tax_file_number` localiza conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_france_eu_tax_file_number` foi encontrada. 
    
Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_france_eu_tax_file_number` localiza conteúdo que corresponde ao padrão. 
    
```xml
      <!-- France Tax Identification Number (numéro SPI.) -->
      <Entity id="ed59e77e-171d-442c-9ec1-88e2ebcb5b0a" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
          <Match idRef="Keywords_france_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_france_eu_telephone_number" />
            <Match idRef="Keywords_france_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>

```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_france_eu_tax_file_number"></a>Keywords_france_eu_tax_file_number

- Numéro d'identification fiscal
- tax id

- identificação de imposto não
- número de identificação do imposto
- n º do imposto #
- n º do imposto
- número do imposto
- número de registro de imposto
- táxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID do Tin
- Tin não
- Tin #


## <a name="france-value-added-tax-number"></a>Número de imposto adicionado ao valor da França

### <a name="format"></a>Formatar

padrão de 13 caracteres alfanuméricos

### <a name="pattern"></a>Padrão

padrão de 13 caracteres alfanuméricos:

- duas letras-FR (não diferencia maiúsculas de minúsculas)
- um espaço ou hífen opcional
- duas letras ou dígitos
- um espaço, ponto, hífen ou vírgula opcional
- três dígitos
- um espaço, ponto, hífen ou vírgula opcional
- três dígitos
- um espaço, ponto, hífen ou vírgula opcional
- três dígitos

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_france_value_added_tax_number localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keywords_france_value_added_tax_number for encontrada.

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_france_value_added_tax_number localiza o conteúdo que corresponde ao padrão.

```xml
      <!-- France Value Added Tax Number -->
      <Entity id="949121e6-ad9f-4379-8731-710342baea78" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_france_value_added_tax_number" />
          <Match idRef="Keywords_france_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_france_value_added_tax_number" />
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_france_value_added_tax_number"></a>Keyword_France_value_added_tax_number

- número de IVA
- IVA não
- IVA #
- imposto sobre valor agregado
- identificação de Siren no Numéro d'identification taxe sur valeur ajoutée
- taxe valeur ajoutée
- taxe sur la valeur ajoutée
- n ° TVA
- Numéro de TVA
- Numéro d'identification Siren


## <a name="germany-drivers-license-number"></a>Número da carteira de motorista da Alemanha
Essa entidade de tipo de informação confidencial está incluída no tipo de informação confidencial do número de carteira do driver da UE e está disponível como uma entidade de tipo de informação confidencial autônoma.

### <a name="format"></a>Formatar

combinação de 11 dígitos e letras

### <a name="pattern"></a>Padrão

11 dígitos e letras (não diferenciam maiúsculas de minúsculas):
- um dígito ou letra 
- dois dígitos 
- seis dígitos ou letras 
- um dígito 
- um dígito ou letra

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_german_drivers_license localiza conteúdo que corresponde ao padrão.
- Pelo menos uma das seguintes opções for verdadeira:
    - Uma palavra-chave de Keyword_german_drivers_license_number for encontrada.
    - Uma palavra-chave de Keyword_german_drivers_license_collaborative for encontrada.
    - Uma palavra-chave de Keyword_german_drivers_license for encontrada.
- A soma de verificação passa.

```xml
<!-- Germany Driver's License Number -->
<Entity id="91da9335-1edb-45b7-a95f-5fe41a16c63c" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_german_drivers_license" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_drivers_license_number" />
          <Match idRef="Keyword_german_drivers_license_collaborative" />
          <Match idRef="Keyword_german_drivers_license" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_german_drivers_license_number"></a>Keyword_german_drivers_license_number

- Führerschein
- Fuhrerschein
- Fuehrerschein
- Führerscheinnummer
- Fuhrerscheinnummer
- Fuehrerscheinnummer
- Führerschein- 
- Fuhrerschein- 
- Fuehrerschein- 
- FührerscheinnummerNr
- FuhrerscheinnummerNr
- FuehrerscheinnummerNr
- FührerscheinnummerKlasse
- FuhrerscheinnummerKlasse
- FuehrerscheinnummerKlasse
- Führerschein- Nr
- Fuhrerschein- Nr
- Fuehrerschein- Nr 
- Führerschein- Klasse 
- Fuhrerschein- Klasse 
- Fuehrerschein- Klasse
- FührerscheinnummerNr 
- FuhrerscheinnummerNr 
- FuehrerscheinnummerNr 
- FührerscheinnummerKlasse 
- FuhrerscheinnummerKlasse 
- FuehrerscheinnummerKlasse 
- Führerschein- Nr 
- Fuhrerschein- Nr 
- Fuehrerschein- Nr 
- Führerschein- Klasse 
- Fuhrerschein- Klasse 
- Fuehrerschein- Klasse 
- DISTRIBUIÇÃO 
- DL
- Driv Lic 
- Driv Licen 
- Driv License
- Driv Licenses 
- Driv Licence 
- Driv Licences 
- Driv Lic 
- Driver Licen 
- Driver License 
- Driver Licenses 
- Driver Licence 
- Driver Licences 
- Drivers Lic 
- Drivers Licen 
- Drivers License 
- Drivers Licenses 
- Drivers Licence 
- Drivers Licences 
- Driver's Lic 
- Driver's Licen 
- Driver's License 
- Driver's Licenses 
- Driver's Licence 
- Driver's Licences 
- Driving Lic 
- Driving Licen 
- Driving License 
- Driving Licenses 
- Driving Licence 
- Driving Licences

#### <a name="keyword_german_drivers_license_collaborative"></a>Keyword_german_drivers_license_collaborative

- Nr-Führerschein 
- Nr-Fuhrerschein 
- Nr-Fuehrerschein 
- No-Führerschein 
- No-Fuhrerschein 
- No-Fuehrerschein 
- N-Führerschein 
- N-Fuhrerschein 
- N-Fuehrerschein
- Nr-Führerschein 
- Nr-Fuhrerschein 
- Nr-Fuehrerschein 
- No-Führerschein 
- No-Fuhrerschein 
- No-Fuehrerschein 
- N-Führerschein 
- N-Fuhrerschein 
- N-Fuehrerschein 

#### <a name="keyword_german_drivers_license"></a>Keyword_german_drivers_license

- ausstellungsdatum
- ausstellungsort
- ausstellende behöde
- ausstellende behorde
- ausstellende behoerde


## <a name="germany-identity-card-number"></a>Número do cartão de identidade da Alemanha

### <a name="format"></a>Formatar

desde 1 de novembro de 2010: nove letras e dígitos

de 1 de abril de 1987 até 31 de outubro de 2010:10 dígitos

### <a name="pattern"></a>Padrão

desde 1 de novembro de 2010:
- uma letra (não diferencia maiúsculas de minúsculas) 
- oito dígitos

de 1 de abril de 1987 até 31 de outubro de 2010:
- dez dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem 65% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular Regex_germany_id_card localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_germany_id_card for encontrada.

```xml
<!-- Germany Identity Card Number -->
<Entity id="e577372f-c42e-47a0-9d85-bebed1c237d4" recommendedConfidence="65" patternsProximity="300">
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Regex_germany_id_card"/>
     <Match idRef="Keyword_germany_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_germany_id_card"></a>Keyword_germany_id_card

- ausweis
- gpid
- identificador
- identifikation
- identifizierungsnummer
- cartão de identidade
- número de identidade
- ID-Nummer
- ID pessoal
- personalausweis
- Persönliche ID Nummer
- persönliche identifikationsnummer
- Persönliche-ID-Nummer


## <a name="germany-passport-number"></a>Número de passaporte da Alemanha
Essa entidade de tipo de informação confidencial está incluída no tipo de informação confidencial do número do Passport da UE e está disponível como uma entidade de tipo de informação confidencial autônoma.

### <a name="format"></a>Formatar

dez dígitos ou letras

### <a name="pattern"></a>Padrão

O padrão deve incluir todos os seguintes itens:
- o primeiro caractere é um dígito ou uma letra desse conjunto (C, F, G, H, J, K) 
- três dígitos 
- cinco dígitos ou letras desse conjunto (C,-H, J-N, P, R, T, V-Z) 
- um dígito

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_german_passport localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de qualquer uma das cinco listas de palavras-chave for encontrada.
- A soma de verificação passa.

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_german_passport_data localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de qualquer uma das cinco listas de palavras-chave for encontrada.
- A soma de verificação passa.

```xml
<!-- Germany Passport Number -->
<Entity id="2e3da144-d42b-47ed-b123-fbf78604e52c" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_german_passport" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_passport" />
          <Match idRef="Keyword_german_passport_collaborative" />
          <Match idRef="Keyword_german_passport_number" />
          <Match idRef="Keyword_german_passport1" />
          <Match idRef="Keyword_german_passport2" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_german_passport_data" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_passport" />
          <Match idRef="Keyword_german_passport_collaborative" />
          <Match idRef="Keyword_german_passport_number" />
          <Match idRef="Keyword_german_passport1" />
          <Match idRef="Keyword_german_passport2" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_german_passport"></a>Keyword_german_passport

- reisepass
- reisepasse
- reisepassnummer
- Passaport
- Passports

#### <a name="keyword_german_passport_collaborative"></a>Keyword_german_passport_collaborative

- geburtsdatum
- ausstellungsdatum
- ausstellungsort

#### <a name="keyword_german_passport_number"></a>Keyword_german_passport_number

No-Reisepass NR-Reisepass

#### <a name="keyword_german_passport1"></a>Keyword_german_passport1

Reisepass-Nr

#### <a name="keyword_german_passport2"></a>Keyword_german_passport2

bnationalit. t


## <a name="germany-tax-identification-number"></a>Número de identificação do imposto da Alemanha

### <a name="format"></a>Formatar

11 dígitos sem espaços e delimitadores
  
### <a name="pattern"></a>Padrão

11 dígitos:
  
- Dois dígitos 
- Um espaço opcional
- Três dígitos 
- Um espaço opcional
- Três dígitos 
- Um espaço opcional
- Dois dígitos
- um dígito de verificação
    
### <a name="checksum"></a>Soma de verificação

Sim
  
### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_germany_eu_tax_file_number` localiza conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_germany_eu_tax_file_number` foi encontrada. 
    
Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_germany_eu_tax_file_number` localiza conteúdo que corresponde ao padrão. 
    
```xml
      <!-- Germany Tax Identification Number -->
      <Entity id="43316a89-9880-40cf-b980-04bc7eefcec5" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_germany_eu_tax_file_number" />
          <Match idRef="Keywords_germany_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_germany_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_germany_eu_tax_file_number"></a>Keywords_germany_eu_tax_file_number

- identifikationsnummer
- ID Steuer
- steueridentifikationsnummer
- steuernummer
- tax id

- identificação de imposto não
- número de identificação do imposto
- n º do imposto #
- n º do imposto
- número do imposto
- número de registro de imposto
- táxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID do Tin
- Tin não
- Tin #
- zinn #
- zinn
- zinnnummer


## <a name="germany-value-added-tax-number"></a>Número de imposto adicionado ao valor da Alemanha

### <a name="format"></a>Formatar

padrão de 11 caracteres alfanuméricos

### <a name="pattern"></a>Padrão

padrão alfanumérico de 11 caracteres:

- uma letra D ou d
- uma letra E ou E
- um espaço opcional
- três dígitos
- um espaço ou vírgula opcional
- três dígitos
- um espaço ou vírgula opcional
- três dígitos

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_germany_value_added_tax_number localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keywords_germany_value_added_tax_number for encontrada.

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_germany_value_added_tax_number localiza o conteúdo que corresponde ao padrão.

```xml
      <!-- Germany Value Added Tax Number -->
      <Entity id="db177eb2-8811-4842-bffc-128c14aa219f" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_germany_value_added_tax_number" />
          <Match idRef="Keywords_germany_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_germany_value_added_tax_number" />
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_germany_value_added_tax_number"></a>Keyword_germany_value_added_tax_number

- número de IVA
- IVA não
- IVA #
- VAT # mehrwertsteuer
- mwst
- mehrwertsteuer identifikationsnummer
- mehrwertsteuer nummer


## <a name="greece-drivers-license-number"></a>Número da carteira de motorista do Grécia
Essa entidade de tipo de informação confidencial está incluída no tipo de informação confidencial do número de carteira do driver da UE e está disponível como uma entidade de tipo de informação confidencial autônoma.

### <a name="format"></a>Formatar

nove dígitos sem espaços e delimitadores
  
### <a name="pattern"></a>Padrão

nove dígitos 
  
### <a name="checksum"></a>Soma de verificação

Não
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_greece_eu_driver's_license_number` localiza o conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_greece_eu_driver's_license_number` foi encontrada. 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Match idRef="Keywords_greece_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_greece_eu_drivers_license_number"></a>Keywords_greece_eu_driver ' s_license_number

- dlL #
- driver license
- número de carteira de motorista
- licença de driver
- drivers driver'lic.
- drivers license
- drivers licence
- driver's license
- número da carteira de motorista
- número de licença do driver
- número da licença de dirigir
- dlno #
- δεια οδήγησης
- Adeia odigisis


## <a name="greece-national-id-card"></a>Cartão de identificação nacional da Grécia

### <a name="format"></a>Formatar

Combinação de 7 a 8 letras e números mais um traço

### <a name="pattern"></a>Padrão

Sete letras e números (formato antigo):
- Uma letra (qualquer letra do alfabeto grego)  
- Um traço 
- Seis dígitos

Oito letras e números (novo formato):
- Duas letras cujos caracteres maiúsculos ocorre em alfabetos latino e grego (ABEZHIKMNOPTYX)  
- Um traço 
- Seis dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular Regex_greece_id_card localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_greece_id_card for encontrada.

Uma política de DLP tem 65% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular Regex_greece_id_card localiza o conteúdo que corresponde ao padrão.

```xml
      <!-- Greece National ID Card -->
      <Entity id="82568215-1da1-46d3-874a-d2294d81b5ac" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_greece_id_card" />
          <Match idRef="Keyword_greece_id_card" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_greece_id_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_greece_id_card"></a>Keyword_greece_id_card

- ID grego
- ID nacional grego
- cartão grego de ID pessoal
- ID de polícia grego
- cartão de identidade
- tautotita
- ταυτότητα
- ταυτότητας


## <a name="greece-passport-number"></a>Número de passaporte da Grécia

Essa entidade de tipo de informação confidencial só está disponível no tipo de informação confidencial do número do Passport da UE.

### <a name="format"></a>Formatar

Duas letras seguidas por sete dígitos sem espaços ou delimitadores
  
### <a name="pattern"></a>Padrão

Duas letras seguidas por sete dígitos
  
### <a name="checksum"></a>Soma de verificação

Não
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A expressão regular  `Regex_greece_eu_passport_number` localiza o conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_greece_eu_passport_number` foi encontrada. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_greece_eu_passport_number"></a>Keywords_greece_eu_passport_number

- passport number
- número de passaporte grego
- Passport não
- διαβατηριο

## <a name="greece-tax-identification-number"></a>Número de identificação de imposto Grécia

### <a name="format"></a>Formatar

Nove dígitos sem espaços e delimitadores
  
### <a name="pattern"></a>Padrão

Nove dígitos
  
### <a name="checksum"></a>Soma de verificação

Não aplicável
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A expressão regular  `Regex_greece_eu_tax_file_number` localiza o conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_greece_eu_tax_file_number` foi encontrada. 
    
```xml
      <!-- Greek Tax Identification Number -->
      <Entity id="15a54a5a-53d4-4080-ad43-a2a4fe1d3bf7" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_tax_file_number" />
          <Match idRef="Keywords_greece_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_greece_eu_tax_file_number"></a>Keywords_greece_eu_tax_file_number

- AFM #
- AFM
- aφμ | aφμ αριθμός
- aφμ
- tax id

- identificação de imposto não
- número de identificação do imposto
- n º do imposto #
- n º do imposto
- número do imposto
- número de registro de imposto
- registro de imposto não
- número do registro de imposto
- táxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- taxregistryno #
- ID do Tin
- Tin não
- Tin #
- αριθμός φορολογικού μητρώου
- τον αριθμό φορολογικού μητρώου
- φορολογικού μητρώου νο


## <a name="hong-kong-identity-card-hkid-number"></a>Número do cartão de identidade de Hong Kong (HKID)

### <a name="format"></a>Formatar

Combinação de 8 a 9 letras e números mais parênteses opcionais ao redor do caractere final

### <a name="pattern"></a>Padrão

Combinação de 8 a 9 letras:
- 1 a 2 letras (não diferenciam maiúsculas de minúsculas) 
- Seis dígitos 
- O caractere final (qualquer dígito ou a letra A), que é o dígito de verificação e é opcionalmente colocado entre parênteses.

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_hong_kong_id_card localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_hong_kong_id_card for encontrada.
- A soma de verificação passa.

Uma política de DLP tem 65% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_hong_kong_id_card localiza o conteúdo que corresponde ao padrão.
- A soma de verificação passa.

```xml
<!-- Hong Kong Identity Card (HKID) number -->
<Entity id="e63c28a7-ad29-4c17-a41a-3d2a0b70fd9c" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_hong_kong_id_card"/>
     <Match idRef="Keyword_hong_kong_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Func_hong_kong_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_hong_kong_id_card"></a>Keyword_hong_kong_id_card

- hkid
- cartão de identidade de Hong Kong
- HKIDC
- id card
- cartão de identidade
- cartão de identidade HK
- ID de Hong Kong
- 香港身份證
- 香港永久性居民身份證
- 身份證
- 身份証
- 身分證
- 身分証
- 香港身份証
- 香港身分證
- 香港身分証
- 香港身份證
- 香港居民身份證
- 香港居民身份証
- 香港居民身分證
- 香港居民身分証
- 香港永久性居民身份証
- 香港永久性居民身分證
- 香港永久性居民身分証
- 香港永久性居民身份證
- 香港非永久性居民身份證
- 香港非永久性居民身份証
- 香港非永久性居民身分證
- 香港非永久性居民身分証
- 香港特別行政區永久性居民身份證
- 香港特別行政區永久性居民身份証
- 香港特別行政區永久性居民身分證
- 香港特別行政區永久性居民身分証
- 香港特別行政區非永久性居民身份證
- 香港特別行政區非永久性居民身份証
- 香港特別行政區非永久性居民身分證
- 香港特別行政區非永久性居民身分証

   
## <a name="hungary-drivers-license-number"></a>Número da carteira de motorista do Hungria

Essa entidade de tipo de informação confidencial só está disponível no tipo de informações confidenciais do número de licença do driver da UE.

### <a name="format"></a>Formatar

Duas letras seguidas por seis dígitos
  
### <a name="pattern"></a>Padrão

Duas letras e seis dígitos:
  
- Duas letras (não diferencia maiúsculas de minúsculas) 
- Seis dígitos
    
### <a name="checksum"></a>Soma de verificação

Não
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A expressão regular  `Regex_hungary_eu_driver's_license_number` localiza o conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_hungary_eu_driver's_license_number` foi encontrada. 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Match idRef="Keywords_hungary_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_hungary_eu_drivers_license_number"></a>Keywords_hungary_eu_driver ' s_license_number

- distribuição #
- driver license
- número de carteira de motorista
- licença de driver
- drivers driver'lic.
- drivers license
- drivers licence
- driver's license
- número da carteira de motorista
- número de licença do driver
- número da licença de dirigir
- dlno #
- vezetoi engedely


## <a name="hungary-personal-identification-number"></a>Número de identificação pessoal da Hungria

### <a name="format"></a>Formatar

11 dígitos
  
### <a name="pattern"></a>Padrão

11 dígitos:
  
- Um dígito que corresponde ao gênero (1-macho, 2-fêmea, outros números também são possíveis para o cidadãos nasceu antes 1900 ou cidadãos com cidadania dupla) 
- Seis dígitos que correspondem à data de nascimento (AAMMDD)
- Três dígitos que correspondem a um número de série
- Um dígito de verificação
    
### <a name="checksum"></a>Soma de verificação

Sim
  
### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função  `Func_hungary_eu_national_id_card` localiza conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_hungary_eu_national_id_card` foi encontrada. 
    
Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função  `Func_hungary_eu_national_id_card` localiza conteúdo que corresponde ao padrão. 
    
```xml
      <!-- Hungary Personal Identification Number -->
      <Entity id="7b5cc218-7046-47d9-80c9-f325b50896ca" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_national_id_card" />
          <Match idRef="Keywords_hungary_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_national_id_card" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_hungary_eu_telephone_number" />
            <Match idRef="Keywords_hungary_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_hungary_eu_national_id_card"></a>Keywords_hungary_eu_national_id_card

- número de identificação
- identification number

- sz IG
- v.IG.
- sz. ig.
- személyazonosító igazolvány
- személyi igazolvány


## <a name="hungary-passport-number"></a>Número de passaporte da Hungria

Essa entidade de tipo de informação confidencial só está disponível no tipo de informação confidencial do número do Passport da UE.

### <a name="format"></a>Formatar

Duas letras seguidas por seis ou sete dígitos sem espaços ou delimitadores
  
### <a name="pattern"></a>Padrão

Duas letras seguidas por seis ou sete dígitos
  
### <a name="checksum"></a>Soma de verificação

Não
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A expressão regular  `Regex_hungary_eu_passport_number` localiza o conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_hungary_eu_passport_number` foi encontrada. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```
### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_hungary_eu_passport_number"></a>Keywords_hungary_eu_passport_number

- passport number
- número de passaporte húngaro
- Passport não
- útlevél száma


## <a name="hungary-social-security-number-or-equivalent-identification"></a>Número da segurança social da Hungria ou identificação equivalente

Essa entidade de tipo de informação confidencial só está disponível no número de seguridade social da UE ou no tipo de informações confidenciais de ID equivalente.

### <a name="format"></a>Formatar

Nove dígitos sem espaços e delimitadores
  
### <a name="pattern"></a>Padrão

Nove dígitos
  
### <a name="checksum"></a>Soma de verificação

Sim
  
### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função  `Func_hungary_eu_ssn_or_equivalent` localiza conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_hungary_eu_ssn_or_equivalent` foi encontrada. 
    
Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função  `Func_hungary_eu_ssn_or_equivalent` localiza conteúdo que corresponde ao padrão. 
    
```xml
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

- número de seguro social de seguridade
- social security number
- socialsecuritynumber #
- hssn #
- socialsecuritynno
- hssn
- taj
- taj #
- es
- es #
- segurança social não
- áfa
- közösségi adószám
- általános forgalmi adó szám
- hozzáadottérték adó
- áfa szám
- magyar áfa szám


## <a name="hungary-tax-identification-number"></a>Número de identificação do imposto Hungria

### <a name="format"></a>Formatar

Dez dígitos sem espaços ou delimitadores
  
### <a name="pattern"></a>Padrão

Dez dígitos:
  
- Um dígito que deve ser "8" 
- Oito dígitos
- Um dígito de verificação
    
### <a name="checksum"></a>Soma de verificação

Sim
  
### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função  `Func_hungary_eu_tax_file_number` localiza conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_hungary_eu_tax_file_number` foi encontrada. 
    
Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função  `Func_hungary_eu_tax_file_number` localiza conteúdo que corresponde ao padrão. 
    
```xml
      <!-- Hungary Tax Identification Number -->
      <Entity id="ede42eb4-59d9-49eb-9603-d7853fbda91d" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
          <Match idRef="Keywords_hungary_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_hungary_eu_telephone_number" />
            <Match idRef="Keywords_hungary_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_hungary_eu_tax_file_number"></a>Keywords_hungary_eu_tax_file_number

- adóazonosító szám
- adóhatóság szám
- adószám
- Tin húngaro
- hungatiantin #
- autoridade de imposto não
- tax id

- identificação de imposto não
- número de identificação do imposto
- n º do imposto #
- n º do imposto
- número do imposto
- número de registro de imposto
- táxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID do Tin
- Tin não
- Tin #
- número de IVA


## <a name="hungary-value-added-tax-number"></a>Número de imposto adicionado ao valor Hungria

### <a name="format"></a>Formatar

padrão de 10 caracteres alfanuméricos

### <a name="pattern"></a>Padrão

padrão de 10 caracteres alfanuméricos:

- 2 letras-HU ou Hu
- espaço opcional
- 8 dígitos

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:

- A função Func_hungarian_value_added_tax_number localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keywords_hungarian_value_added_tax_number for encontrada.

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:

- A função Func_hungarian_value_added_tax_number localiza o conteúdo que corresponde ao padrão.

```xml
      <!-- Hungarian Value Added Tax Number -->
      <Entity id="976349a0-683b-477a-90f8-ff0a220d5592" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungarian_value_added_tax_number" />
          <Match idRef="Keywords_hungarian_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungarian_value_added_tax_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_hungary_value_added_tax_number"></a>Keyword_Hungary_value_added_tax_number

- IVA
- número de imposto sobre valor agregado
- IVA #
- vatno #
- hungarianvatno #
- n º do imposto
- áfa de imposto sobre valor agregado
- közösségi adószám
- általános forgalmi adó szám
- hozzáadottérték adó
- áfa szám


## <a name="india-permanent-account-number-pan"></a>Número da conta permanente da Índia (PAN)

### <a name="format"></a>Formatar

10 letras ou dígitos

### <a name="pattern"></a>Padrão

10 letras ou dígitos.
- Cinco letras (não diferenciam maiúsculas de minúsculas) 
- Quatro dígitos 
- Uma letra que é um dígito de verificação alfabético

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular Regex_india_permanent_account_number localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_india_permanent_account_number for encontrada.
- A soma de verificação passa.

```xml
<!-- India Permanent Account Number -->
<Entity id="2602bfee-9bb0-47a5-a7a6-2bf3053e2804" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_india_permanent_account_number"/>
     <Match idRef="Keyword_india_permanent_account_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_india_permanent_account_number"></a>Keyword_india_permanent_account_number

- Número da Conta Permanente 
- APLICAR 
   
## <a name="india-unique-identification-aadhaar-number"></a>Número de identificação exclusiva da Índia (Aadhaar)

### <a name="format"></a>Formatar

12 dígitos contendo espaços opcionais ou traços

### <a name="pattern"></a>Padrão

12 dígitos:
- Quatro dígitos 
- Um espaço ou um traço opcional  
- Quatro dígitos 
- Um espaço ou um traço opcional  
- O dígito final que é o dígito de verificação

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_india_aadhaar localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_india_aadhar for encontrada.
- A soma de verificação passa.
- 
Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:

- A função Func_india_aadhaar localiza o conteúdo que corresponde ao padrão.
- A soma de verificação passa.

```xml
<!-- India Unique Identification (Aadhaar) number -->
<Entity id="1ca46b29-76f5-4f46-9383-cfa15e91048f" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_india_aadhaar"/>
     <Match idRef="Keyword_india_aadhar"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_india_aadhaar"/>
  </Pattern>
</Entity>
```
### <a name="keywords"></a>Palavras-chave
   
#### <a name="keyword_india_aadhar"></a>Keyword_india_aadhar
- Aadhar
- Aadhaar
- UID
- आधार
   
## <a name="indonesia-identity-card-ktp-number"></a>Número do cartão de identidade da Indonésia (KTP)

### <a name="format"></a>Formatar

16 dígitos contendo pontos opcionais

### <a name="pattern"></a>Padrão

16 dígitos:
- Código de província de dois dígitos  
- Um ponto (opcional)  
- Código de dois dígitos da regência ou da cidade  
- Código de dois dígitos do subdistrito  
- Um ponto (opcional)  
- Seis dígitos no formato DDMMAA que são a data de nascimento 
- Um ponto (opcional)  
- Quatro dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:

- A expressão regular Regex_indonesia_id_card localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_indonesia_id_card for encontrada.

```xml
<!-- Indonesia Identity Card (KTP) Number -->
<Entity id="da68fdb0-f383-4981-8c86-82689d3b7d55" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_indonesia_id_card"/>
     <Match idRef="Keyword_indonesia_id_card"/>
</Entity>
```

### <a name="keywords"></a>Palavras-chave
   
#### <a name="keyword_indonesia_id_card"></a>Keyword_indonesia_id_card

- KTP
- Kartu Tanda Penduduk 
- Nomor Induk Kependudukan 
   
## <a name="international-banking-account-number-iban"></a>Número de conta bancária internacional (IBAN)

### <a name="format"></a>Formatar

Código do país (duas letras) mais dígitos de verificação (dois dígitos) mais Bban número (até 30 caracteres)

### <a name="pattern"></a>Padrão

O padrão deve incluir todos os seguintes itens:

- Código de país de duas letras
- Dois dígitos de verificação (seguidos por um espaço opcional) 
- 1-7 grupos de quatro letras ou dígitos (podem ser separados por espaços)
- 1 a 3 letras ou dígitos

O formato de cada país é um pouco diferente. O tipo de informação confidencial do IBAN cobre estes 60 países:

AD, AE, Al, at, AZ, BA, or, BG, BH, ch, CR, Cy, cz, de, DK, do, EE, es, Fi, fo, FR, GB, GE, GI, GL, GA, HR, Hu, IE, Il, is, it, kW, KZ, lb, li, lt, Lu, LV, MC, MD, me, MK, Sr, MT, MU, NL, não, pl, pt,, RS, SK, SM, TN

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:

- A função Func_iban localiza conteúdo que corresponde ao padrão.
- A soma de verificação passa.

```xml
<Entity id="e7dc4711-11b7-4cb0-b88b-2c394a771f0e" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_iban" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

Nenhum

   
## <a name="international-classification-of-diseases-icd-10-cm"></a>Classificação internacional do Diseases (ICD-10-CM)

### <a name="format"></a>Formatar

Dictionary

### <a name="pattern"></a>Padrão

Palavra-chave

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- Uma palavra-chave de Dictionary_icd_10_updated for encontrada.
- Uma palavra-chave de Dictionary_icd_10_codes for encontrada.

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- Uma palavra-chave de Dictionary_icd_10_ atualizada é encontrada.

```xml
      <!-- ICD-10 CM -->
      <Entity id="3356946c-6bb7-449b-b253-6ffa419c0ce7" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_10_updated" />
          <Match idRef="Dictionary_icd_10_codes" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Dictionary_icd_10_updated" />
        </Pattern>

```

### <a name="keywords"></a>Palavras-chave

Qualquer termo do dicionário de palavra-chave Dictionary_icd_10_updated, que se baseia na [classificação internacional do Diseases, décimo revisão, modificação clínica (ICD-10-cm)](https://go.microsoft.com/fwlink/?linkid=852604). Esse tipo procura apenas o termo, não os códigos de seguro.

Qualquer termo do dicionário de palavra-chave Dictionary_icd_10_codes, que se baseia na [classificação internacional do Diseases, décimo revisão, modificação clínica (ICD-10-cm)](https://go.microsoft.com/fwlink/?linkid=852604). Este tipo procura apenas por códigos de seguro, não a descrição.

## <a name="international-classification-of-diseases-icd-9-cm"></a>Classificação internacional do Diseases (ICD-9-CM)

### <a name="format"></a>Formatar

Dictionary

### <a name="pattern"></a>Padrão

Palavra-chave

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- Uma palavra-chave de Dictionary_icd_9_updated for encontrada.
- Uma palavra-chave de Dictionary_icd_9_codes for encontrada.

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- Uma palavra-chave de Dictionary_icd_9_updated for encontrada.

```xml
    <Entity id="fa3f9c74-ee07-4c52-b5f2-085d6b2c0ec4" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_9_updated" />
          <Match idRef="Dictionary_icd_9_codes" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Dictionary_icd_9_updated" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

Qualquer termo do dicionário de palavra-chave Dictionary_icd_9_updated, que se baseia na [classificação internacional do Diseases, Nona revisão, modificação clínica (ICD-9-cm)](https://go.microsoft.com/fwlink/?linkid=852605). Esse tipo procura apenas o termo, não os códigos de seguro.

Qualquer termo do dicionário de palavra-chave Dictionary_icd_9_codes, que se baseia na [classificação internacional do Diseases, Nona revisão, modificação clínica (ICD-9-cm)](https://go.microsoft.com/fwlink/?linkid=852605). Este tipo procura apenas por códigos de seguro, não a descrição.

## <a name="ip-address"></a>Endereço IP

### <a name="format"></a>Formatar

#### <a name="ipv4"></a>IPv4
Padrão complexo que é responsável por versões formatadas (pontos) e não formatadas (sem pontos) dos endereços IPv4

#### <a name="ipv6"></a>IPv6
Padrão complexo que é responsável por números IPv6 formatados (que incluem dois pontos)

### <a name="pattern"></a>Padrão

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Para IPv6, uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular Regex_ipv6_address localiza o conteúdo que corresponde ao padrão.
- Nenhuma palavra-chave de Keyword_ipaddress for encontrada.

Para IPv4, uma política de DLP tem 95% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular Regex_ipv4_address localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_ipaddress for encontrada.

Para IPv6, uma política de DLP tem 95% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular Regex_ipv6_address localiza o conteúdo que corresponde ao padrão.
- Nenhuma palavra-chave de Keyword_ipaddress for encontrada.

```xml
    <!-- IP Address -->
    <Entity id="1daa4ad5-e2dd-4ca4-a788-54722c09efb2" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_ipv6_address" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="95">
        <IdMatch idRef="Regex_ipv4_address" />
        <Any minMatches="1">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="95">
        <IdMatch idRef="Regex_ipv6_address" />
        <Any minMatches="1">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_ipaddress"></a>Keyword_ipaddress

- IP (esta palavra-chave diferencia maiúsculas de minúsculas)
- ip address 
- endereços ip
- internet protocol
- IP כתובת ה 

## <a name="ireland-drivers-license-number"></a>Número da carteira de motorista da Irlanda

Essa entidade de tipo de informação confidencial só está disponível no tipo de informações confidenciais do número de licença do driver da UE.

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
  
- A expressão regular  `Regex_ireland_eu_driver's_license_number` localiza o conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_ireland_eu_driver's_license_number` foi encontrada. 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Match idRef="Keywords_ireland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_ireland_eu_drivers_license_number"></a>Keywords_ireland_eu_driver ' s_license_number

- distribuição #
- driver license
- número de carteira de motorista
- licença de driver
- drivers driver'lic.
- drivers license
- drivers licence
- driver's license
- número da carteira de motorista
- número de licença do driver
- número da licença de dirigir
- dlno #
- ceadúnas tiomána


## <a name="ireland-passport-number"></a>Número de passaporte da Irlanda

Essa entidade de tipo de informação confidencial só está disponível no tipo de informação confidencial do número do Passport da UE.

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
  
- A expressão regular  `Regex_ireland_eu_passport_number` localiza o conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_ireland_eu_passport_number` foi encontrada. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_ireland_eu_passport_number"></a>Keywords_ireland_eu_passport_number

- passport number
- número de passaporte do irlandês
- Passport não
- Pas
- Passaport
- passeport
- passeport numero

## <a name="ireland-personal-public-service-pps-number"></a>Número de serviço público pessoal (PPS) da Irlanda

### <a name="format"></a>Formatar

Formato antigo (até 31 de dezembro de 2012):
- sete dígitos seguidos por 1-2 letras 

Novo formato (1 Jan 2013 e posterior):
- sete dígitos seguidos de duas letras

### <a name="pattern"></a>Padrão

Formato antigo (até 31 de dezembro de 2012):
- sete dígitos 
- uma ou duas letras (não diferencia maiúsculas de minúsculas) 

Novo formato (1 Jan 2013 e posterior):
- sete dígitos 
- uma letra (não diferencia maiúsculas de minúsculas) que é um dígito de verificação alfabética 
- Uma letra opcional no intervalo A-I ou "W"

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_ireland_pps localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keywords_ireland_eu_national_id_card for encontrada.
- A soma de verificação passa.

Uma política de DLP tem 65% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_ireland_pps localiza o conteúdo que corresponde ao padrão.
- A soma de verificação passa.

```xml
      <!-- Ireland Personal Public Service (PPS) Number -->
      <Entity id="1cdb674d-c19a-4fcf-9f4b-7f56cc87345a" patternsProximity="300" recommendedConfidence="85" relaxProximity="true">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_ireland_pps" />
          <Match idRef="Keywords_ireland_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_ireland_pps" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_ireland_eu_national_id_card"></a>Keywords_ireland_eu_national_id_card

- serviço de identidade do cliente
- identification number

- número de identificação pessoal
- número de serviço público pessoal
- serviço pessoal não
- phearsanta seirbhíse poiblí
- PPS não
- número PPS
- número PPS
- serviço PPS não
- ppsn
- ppsno #
- ppsno
- PSP
- serviço público não
- publicserviceno #
- publicserviceno
- número da receita e do seguro social
- RSI não
- número do RSI
- rsin
- cliente do seirbhís aitheantais
- uimh
- uimhir aitheantais chánach
- uimhir aitheantais phearsanta
- uimhir phearsanta seirbhíse poiblí
- tax id

- identificação de imposto não
- número de identificação do imposto
- n º do imposto #
- n º do imposto
- número do imposto
- número de registro de imposto
- táxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID do Tin
- Tin não
- Tin #


## <a name="israel-bank-account-number"></a>Número de conta bancária de Israel

### <a name="format"></a>Formatar

13 dígitos

### <a name="pattern"></a>Padrão

Binário
- dois dígitos 
- um traço 
- três dígitos 
- um traço 
- oito dígitos

Não formatado
- 13 dígitos consecutivos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular Regex_israel_bank_account_number localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_israel_bank_account_number for encontrada.

```xml
<!-- Israel Bank Account Number -->
<Entity id="7d08b2ff-a0b9-437f-957c-aeddbf9b2b25" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_israel_bank_account_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_israel_bank_account_number" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_israel_bank_account_number"></a>Keyword_israel_bank_account_number

- Bank Account Number 
- Bank Account 
- Account Number 
- מספר חשבון בנק 
   
## <a name="israel-national-identification-number"></a>Número de identificação nacional de Israel

### <a name="format"></a>Formatar

nove dígitos

### <a name="pattern"></a>Padrão

nove dígitos consecutivos

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_israeli_national_id_number localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_Israel_National_ID for encontrada.
- A soma de verificação passa.

```xml
<!-- Israel National ID Number -->
<Entity id="e05881f5-1db1-418c-89aa-a3ac5c5277ee" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_israeli_national_id_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_Israel_National_ID" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_israel_national_id"></a>Keyword_Israel_National_ID

- מספר זהות 
- Número de identificação nacional
   
## <a name="italy-drivers-license-number"></a>Número da carteira de motorista da Itália
Essa entidade de tipo de informação confidencial está incluída no tipo de informação confidencial do número de carteira do driver da UE e está disponível como uma entidade de tipo de informação confidencial autônoma.

### <a name="format"></a>Formatar

uma combinação de 10 letras e dígitos

### <a name="pattern"></a>Padrão

- uma combinação de 10 letras e dígitos:
- uma letra (não diferencia maiúsculas de minúsculas) 
- a letra "A" ou "V" (não diferencia maiúsculas de minúsculas) 
- sete letras (não diferencia maiúsculas de minúsculas), dígitos ou o caractere de sublinhado 
- uma letra (não diferencia maiúsculas de minúsculas)

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular Regex_italy_drivers_license_number localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_italy_drivers_license_number for encontrada.

```xml
<!-- Italy Driver's license Number -->
<Entity id="97d6244f-9157-41bd-8e0c-9d669a5c4d71" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_italy_drivers_license_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_italy_drivers_license_number" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_italy_drivers_license_number"></a>Keyword_italy_drivers_license_number

- numero di patente di guida 
- patente di guida 

## <a name="italy-fiscal-code"></a>Código fiscal da Itália

### <a name="format"></a>Formatar

uma combinação de 16 caracteres de letras e dígitos no padrão especificado
  
### <a name="pattern"></a>Padrão

Uma combinação de letras e dígitos de 16 caracteres:
- três letras que correspondem às três primeiras consoantes no nome da família
- três letras que correspondem à primeira, terceira e quarta consoantes no primeiro nome
- dois dígitos que correspondem aos últimos dígitos do ano de nascimento
- uma letra que corresponde à carta para o mês de nascimento-as letras são usadas em ordem alfabética, mas apenas as letras de a a E, H, L, M, P, R a T são usadas (dessa forma, Janeiro é A e outubro é R)
- dois dígitos que correspondem ao dia do mês de nascimento — para diferenciar entre sexos, 40 é adicionado ao dia de nascimento para mulheres
- quatro dígitos que correspondem ao código de área específico do município onde a pessoa nasceu (códigos de todo o país são usados para países estrangeiros)
- um dígito de paridade
    
### <a name="checksum"></a>Soma de verificação

Sim
  
### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_italy_eu_national_id_card` localiza conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_italy_eu_national_id_card` foi encontrada. 
    
Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_italy_eu_national_id_card` localiza conteúdo que corresponde ao padrão. 
    
```xml
      <!-- Italy Fiscal Code -->
      <Entity id="4cd79172-8da9-4ff5-9188-98b1e7e2eca6" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_italy_eu_national_id_card" />
          <Match idRef="Keywords_italy_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_italy_eu_national_id_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_italy_eu_national_id_card"></a>Keywords_italy_eu_national_id_card

- fiscal codice
- fiscalização codice
- pessoal da ID codice
- pessoal do Codice
- código fiscal
- numero certificato pessoal
- numero di IDENTIFICAZIONE fiscal
- pessoal da ID numero
- pessoal do numero
- número do certificado pessoal
- código pessoal
- código de ID pessoal
- número de identificação pessoal
- personalcodeno #
- código de imposto
- tax id

- identificação de imposto não
- número de identificação do imposto
- número de identidade do imposto
- n º do imposto #
- n º do imposto
- número do imposto
- número de registro de imposto
- táxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID do Tin
- Tin não
- Tin #


## <a name="italy-passport-number"></a>Número de passaporte da Itália
Essa entidade de tipo de informação confidencial só está disponível no tipo de informação confidencial do número do Passport da UE.

### <a name="format"></a>Formatar

duas letras ou dígitos seguidos de sete dígitos sem espaços ou delimitadores
  
### <a name="pattern"></a>Padrão

duas letras ou dígitos seguidos por sete dígitos:
  
- dois dígitos ou letras (não diferencia maiúsculas de minúsculas)
- sete dígitos
    
### <a name="checksum"></a>Soma de verificação

não aplicável
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_italy_eu_passport_number` localiza o conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_italy_eu_passport_number` foi encontrada. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_italy_eu_passport_number"></a>Keywords_italy_eu_passport_number

- número de passaporte italiano
- repubblica italiana passaporto
- passaporto
- passaporto italiana
- passport number
- italiana passaporto numero
- passaporto numero
- numéro passeport italien
- numéro passeport


## <a name="italy-value-added-tax-number"></a>Número de imposto adicionado ao valor da Itália

### <a name="format"></a>Formatar

padrão de 13 caracteres alfanuméricos com delimitadores opcionais

### <a name="pattern"></a>Padrão

padrão de 13 caracteres alfanuméricos com delimitadores opcionais:

- I ou i
- T ou t
- espaço, ponto, hífen ou vírgula opcional
- 11 dígitos

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_italy_value_added_tax_number localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keywords_italy_value_added_tax_number for encontrada.

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_italy_value_added_tax_number localiza o conteúdo que corresponde ao padrão.

```xml
      <!-- Italy Value Added Tax -->
      <Entity id="26a8cc07-2283-4a2a-ab1d-4ab643c4c67f" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_italy_value_added_tax_number" />
          <Match idRef="Keywords_italy_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_italy_value_added_tax_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_italy_value_added_tax_number"></a>Keyword_italy_value_added_tax_number

- número de IVA
- IVA não
- IVA #
- iva
- iva #


## <a name="japan-bank-account-number"></a>Número de conta bancária do Japão

### <a name="format"></a>Formatar

sete ou oito dígitos

### <a name="pattern"></a>Padrão

número da conta bancária:
- sete ou oito dígitos
- código da filial da conta bancária:
- quatro dígitos 
- um espaço ou um traço (opcional) 
- três dígitos

Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_jp_bank_account localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_jp_bank_account for encontrada.
- Uma das seguintes opções for verdadeira:
- A função Func_jp_bank_account_branch_code localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_jp_bank_branch_code for encontrada.

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_jp_bank_account localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_jp_bank_account for encontrada.

```xml
<!-- Japan Bank Account Number -->
<Entity id="d354f95b-96ee-4b80-80bc-4377312b55bc" patternsProximity="300" recommendedConfidence="75">
  <Version minEngineVersion="15.01.0131.000">
    <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_jp_bank_account" />
          <Match idRef="Keyword_jp_bank_account" />
          <Any minMatches="1">
            <Match idRef="Func_jp_bank_account_branch_code" />
            <Match idRef="Keyword_jp_bank_branch_code" />
          </Any>
      </Pattern>
  </Version>    
     <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_bank_account" />
        <Match idRef="Keyword_jp_bank_account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_jp_bank_account"></a>Keyword_jp_bank_account

- Checking Account Number 
- Checking Account 
- Checking Account # 
- Checking Acct Number 
- Checking Acct # 
- Checking Acct No. 
- Checking Account No. 
- Bank Account Number 
- Bank Account 
- Bank Account # 
- Bank Acct Number 
- Bank Acct # 
- Bank Acct No. 
- Bank Account No. 
- Savings Account Number 
- Savings Account 
- Savings Account # 
- Savings Acct Number 
- Savings Acct # 
- Savings Acct No. 
- Savings Account No. 
- Debit Account Number 
- Debit Account 
- Debit Account # 
- Debit Acct Number 
- Debit Acct # 
- Debit Acct No. 
- Debit Account No. 
- 口座番号を当座預金口座の確認 
- #アカウントの確認 、 勘定番号の確認 
- #勘定の確認 
- 勘定番号の確認 
- 口座番号の確認 
- 銀行口座番号 
- 銀行口座 
- 銀行口座＃ 
- 銀行の勘定番号 
- 銀行のacct＃ 
- 銀行の勘定いいえ 
- 銀行口座番号
- 普通預金口座番号 
- 預金口座 
- 貯蓄口座＃ 
- 貯蓄勘定の数 
- 貯蓄勘定＃ 
- 貯蓄勘定番号 
- 普通預金口座番号 
- 引き落とし口座番号 
- 口座番号 
- 口座番号＃ 
- デビットのacct番号 
- デビット勘定＃ 
- デビットACCTの番号 
- デビット口座番号 

#### <a name="keyword_jp_bank_branch_code"></a>Keyword_jp_bank_branch_code

Otemachi

## <a name="japan-drivers-license-number"></a>Número da carteira de motorista do Japão

### <a name="format"></a>Formatar

12 dígitos

### <a name="pattern"></a>Padrão

12 dígitos consecutivos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_jp_drivers_license_number localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_jp_drivers_license_number for encontrada.

```xml
<!-- Japan Driver's License Number -->
<Entity id="c6011143-d087-451c-8313-7f6d4aed2270" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_drivers_license_number" />
        <Match idRef ="Keyword_jp_drivers_license_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_jp_drivers_license_number"></a>Keyword_jp_drivers_license_number

- distribuição # 
- DISTRIBUIÇÃO 
- DL # 
- DL 
- driver license 
- driver licenses 
- drivers license 
- driver's license 
- drivers licenses 
- driver's licenses 
- driving licence 
- driver'lic # 
- DRIVER'LIC 
- driver'lics # 
- state id 
- state identification 
- state identification number 
- 低所得国＃ 
- 免許証 
- 状態ID
- 状態の識別 
- 状態の識別番号 
- 運転免許 
- 運転免許証 
- 運転免許証番号 


## <a name="japan-my-number---corporate"></a>Meu número do Japão-corporativo

### <a name="format"></a>Formatar

número de 13 dígitos

### <a name="pattern"></a>Padrão

número de 13 dígitos:

- um dígito de um a nove
- 12 dígitos

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_japanese_my_number_corporate localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keywords_japanese_my_number_corporate for encontrada.

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_japanese_my_number_corporate localiza o conteúdo que corresponde ao padrão.

```xml
      <!-- Japanese My Number – Corporate -->
      <Entity id="9e0eaf79-ff20-4ffb-b3e4-e7368d5db6ff" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_japanese_my_number_corporate" />
          <Match idRef="Keywords_japanese_my_number_corporate" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_japanese_my_number_corporate" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_japan_my_number_corporate"></a>Keyword_japan_my_number_corporate

- número corporativo
- マイナンバー
- 共通番号
- マイナンバーカード
- マイナンバーカード番号
- 個人番号カード
- 個人識別番号
- 個人識別ナンバー
- 法人番号
- 指定通知書


## <a name="japan-my-number---personal"></a>Japão meu número-pessoal

### <a name="format"></a>Formatar

número de 12 dígitos

### <a name="pattern"></a>Padrão

número de 12 dígitos:

- quatro dígitos
- um espaço, um ponto ou hífen opcional
- quatro dígitos
- um espaço, um ponto ou hífen opcional
- quatro dígitos

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_japanese_my_number_personal localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keywords_japanese_my_number_personal for encontrada.

Uma política de DLP tem 65% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_japanese_my_number_personal localiza o conteúdo que corresponde ao padrão.

```xml
      <!-- Japanese My Number – Personal -->
      <Entity id="98da8e66-7299-4ebd-9f82-c871ab37d3ef" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_japanese_my_number_personal" />
          <Match idRef="Keywords_japanese_my_number_personal" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_japanese_my_number_personal" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_japan_my_number_personal"></a>Keyword_japan_my_number_personal

- meu número
- マイナンバー
- 個人番号
- 共通番号
- マイナンバーカード
- マイナンバーカード番号
- 個人番号カード
- 個人識別番号
- 個人識別ナンバー
- 通知カード

   
## <a name="japan-passport-number"></a>Número de passaporte do Japão

### <a name="format"></a>Formatar

duas letras seguidas por sete dígitos

### <a name="pattern"></a>Padrão

duas letras (não diferencia maiúsculas de minúsculas) seguidas por sete dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_jp_passport localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_jp_passport for encontrada.

```xml
<!-- Japan Passport Number -->
<Entity id="75177310-1a09-4613-bf6d-833aae3743f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_passport" />
        <Match idRef="Keyword_jp_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_jp_passport"></a>Keyword_jp_passport

- パスポート 
- パスポート番号 
- パスポートのNum 
- パスポート＃ 

## <a name="japan-residence-card-number"></a>Número do cartão de residência do Japão

### <a name="format"></a>Formatar

12 letras e dígitos

### <a name="pattern"></a>Padrão

12 letras e dígitos:
- duas letras (não diferencia maiúsculas de minúsculas)
- oito dígitos 
- duas letras (não diferencia maiúsculas de minúsculas)

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular Regex_jp_residence_card_number localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_jp_residence_card_number for encontrada.

```xml
<!--Japan Residence Card Number-->
-<Entity id="ac36fef2-a289-4e2c-bb48-b02366e89fc0" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_jp_residence_card_number"/>
      <Match idRef="Keyword_jp_residence_card_number"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_jp_residence_card_number"></a>Keyword_jp_residence_card_number

- Número do cartão de residência
- Número do cartão de residência
- Cartão de residência #
- 在留カード番号

## <a name="japan-resident-registration-number"></a>Número de registro residente no Japão

### <a name="format"></a>Formatar

11 dígitos

### <a name="pattern"></a>Padrão

11 dígitos consecutivos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_jp_resident_registration_number localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_jp_resident_registration_number for encontrada.

```xml
<!-- Japan Resident Registration Number -->
<Entity id="01c1209b-6389-4faf-a5f8-3f7e13899652" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_resident_registration_number" />
        <Match idRef ="Keyword_jp_resident_registration_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_jp_resident_registration_number"></a>Keyword_jp_resident_registration_number

- Resident Registration Number
- Resident Register Number 
- Residents Basic Registry Number 
- Resident Registration No. 
- Resident Register No. 
- Residents Basic Registry No. 
- Basic Resident Register No. 
- 住民登録番号、登録番号をレジデント 
- 住民基本登録番号、登録番号 
- 住民基本レジストリ番号を常駐 
- 登録番号を常駐住民基本台帳登録番号 

   
## <a name="japan-social-insurance-number-sin"></a>Número de seguro social (SIN) do Japão

### <a name="format"></a>Formatar

7 a 12 dígitos

### <a name="pattern"></a>Padrão

7 a 12 dígitos:
- quatro dígitos 
- um hífen (opcional) 
- seis dígitos ou
- 7 a 12 dígitos consecutivos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_jp_sin localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_jp_sin for encontrada.

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_jp_sin_pre_1997 localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_jp_sin for encontrada.

```xml
<!-- Japan Social Insurance Number -->
<Entity id="c840e719-0896-45bb-84fd-1ed5c95e45ff" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_jp_sin" />
        <Match idRef="Keyword_jp_sin" />
    </Pattern>
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_sin_pre_1997" />
        <Match idRef="Keyword_jp_sin" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_jp_sin"></a>Keyword_jp_sin

- Social Insurance No. 
- Social Insurance Num 
- Social Insurance Number 
- 社会保険のテンキー 
- 社会保険番号 

## <a name="latvia-drivers-license-number"></a>Número da carteira de motorista da Letônia
Essa entidade de tipo de informação confidencial só está disponível no tipo de informações confidenciais do número de licença do driver da UE.

### <a name="format"></a>Formatar

três letras seguidas por seis dígitos
  
### <a name="pattern"></a>Padrão

três letras e seis dígitos:
  
- três letras (não diferencia maiúsculas de minúsculas) 
- seis dígitos
    
### <a name="checksum"></a>Soma de verificação

Não
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_latvia_eu_driver's_license_number` localiza o conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_latvia_eu_driver's_license_number` foi encontrada. 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Match idRef="Keywords_latvia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_latvia_eu_drivers_license_number"></a>Keywords_latvia_eu_driver ' s_license_number

- distribuição #
- driver license
- número de carteira de motorista
- licença de driver
- drivers driver'lic.
- drivers license
- drivers licence
- driver's license
- número da carteira de motorista
- número de licença do driver
- número da licença de dirigir
- dlno #
- autovadītāja apliecība

## <a name="latvia-personal-code"></a>Código pessoal da Letônia

### <a name="format"></a>Formatar

11 dígitos e um hífen opcional
  
### <a name="pattern"></a>Padrão

Formato antigo

11 dígitos e um hífen:
  
- seis dígitos que correspondem à data de nascimento (DDMMAA) 
- um hífen
- um dígito que corresponde ao século de nascimento ("0" para o século 19, "1" para o século 20 e "2" para o século 21)
- quatro dígitos, gerados aleatoriamente

Novo formato

11 dígitos

- Dois dígitos "32"
- Nove dígitos
    
### <a name="checksum"></a>Soma de verificação

Sim
  
### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_latvia_eu_national_id_card` ou Regex `Regex_latvia_eu_national_id_card_new_format` localiza conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_latvia_eu_national_id_card` foi encontrada. 
    
Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_latvia_eu_national_id_card` ou Regex `Regex_latvia_eu_national_id_card_new_format` localiza conteúdo que corresponde ao padrão. 
    
```xml
      <!-- Latvia Personal Code -->
      <Entity id="03fcf763-27c2-49ed-9422-2641c6c895c9" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_latvia_eu_national_id_card" />
          <Match idRef="Keywords_latvia_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_latvia_eu_national_id_card" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_latvia_eu_telephone_number" />
            <Match idRef="Keywords_latvia_eu_mobile_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_latvia_eu_national_id_card_new_format" />
          <Match idRef="Keywords_latvia_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_national_id_card_new_format" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_latvia_eu_telephone_number" />
            <Match idRef="Keywords_latvia_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>

```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_latvia_eu_national_id_card"></a>Keywords_latvia_eu_national_id_card

- número administrativo
- alvas nē
- número de nascimento
- número do cidadão
- número civil
- número do dos censo eletrônico
- número eletrônico
- código fiscal
- número de usuário da assistência médica
- ID #
- ID-código
- identification number

- identifikācijas numurs
- ID-número
- número individual
- latvija alva
- ID nacionālais
- 
national id
- número de identificação nacional
- número de identidade nacional
- national insurance number

- número do Registro Nacional
- nodokļa numurs
- ID nodokļu
- nodokļu identifikācija numurs
- número do certificado pessoal
- código pessoal
- código de ID pessoal
- número de identificação pessoal
- código de identificação pessoal
- identificador pessoal
- número de identidade pessoal
- número pessoal
- código numérico pessoal
- personalcodeno #
- Kods personas
- código de identificação de população
- número de serviço público
- 
registration number
- número de receita
- número de seguro social
- social security number

- código de imposto estadual
- número do arquivo de imposto
- tax id

- identificação de imposto não
- número de identificação do imposto
- n º do imposto #
- n º do imposto
- número do imposto
- táxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID do Tin
- Tin não
- Tin #
- número do eleitor

## <a name="latvia-passport-number"></a>Número de passaporte da Letônia
Essa entidade de tipo de informação confidencial só está disponível no tipo de informação confidencial do número do Passport da UE.

### <a name="format"></a>Formatar

duas letras ou dígitos seguidos de sete dígitos sem espaços ou delimitadores
  
### <a name="pattern"></a>Padrão

duas letras ou dígitos seguidos por sete dígitos:
  
- dois dígitos ou letras (não diferencia maiúsculas de minúsculas)
- sete dígitos
    
### <a name="checksum"></a>Soma de verificação

Não
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_latvia_eu_passport_number` localiza o conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_latvia_eu_passport_number` foi encontrada. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_latvia_eu_passport_number"></a>Keywords_latvia_eu_passport_number

- passport number
- número de passaporte da Letão
- Passport não
- pase numurs    


## <a name="lithuania-drivers-license-number"></a>Número da carteira de motorista da Lituânia
Essa entidade de tipo de informação confidencial só está disponível no tipo de informações confidenciais do número de licença do driver da UE.

### <a name="format"></a>Formatar

oito dígitos sem espaços e delimitadores
  
### <a name="pattern"></a>Padrão

oito dígitos 
  
### <a name="checksum"></a>Soma de verificação

Não
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_lithuania_eu_driver's_license_number` localiza o conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_lithuania_eu_driver's_license_number` foi encontrada. 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_lithuania_eu_drivers_license_number"></a>Keywords_lithuania_eu_driver ' s_license_number

- distribuição #
- driver license
- número de carteira de motorista
- licença de driver
- drivers driver'lic.
- drivers license
- drivers licence
- driver's license
- número da carteira de motorista
- número de licença do driver
- número da licença de dirigir
- dlno #
- vairuotojo pažymėjimas

## <a name="lithuania-personal-code"></a>Código pessoal da Lituânia

### <a name="format"></a>Formatar

11 dígitos sem espaços e delimitadores
  
### <a name="pattern"></a>Padrão

11 dígitos sem espaços e delimitadores:
  
- um dígito (1-6) que corresponde ao sexo da pessoa e ao século de nascimento
- seis dígitos que correspondem à data de nascimento (AAMMDD) 
- três dígitos que correspondem ao número de série da data de nascimento
- um dígito de verificação
    
### <a name="checksum"></a>Soma de verificação

Sim
  
### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_lithuania_eu_tax_file_number` localiza conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_lithuania_eu_tax_file_number` foi encontrada. 
    
Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_lithuania_eu_tax_file_number` localiza conteúdo que corresponde ao padrão. 
    
```xml
      <!-- Lithuania Personal Code -->
      <Entity id="cd6d3786-8ec3-4524-a2cf-1e0095379171" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
          <Match idRef="Keywords_lithuania_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_lithuania_eu_telephone_number" />
            <Match idRef="Keywords_lithuania_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_lithuania_eu_national_id_card"></a>Keywords_lithuania_eu_national_id_card

- asmeninis skaitmeninis kodas
- kodas
- número do serviço do cidadão
- ID mokesčių
- mokesčių identifikavimas numeris
- mokesčių identifikavimo numeris
- mokesčių numeris
- número de identificação nacional
- código pessoal
- código numérico pessoal
- piliečio paslaugos numeris
- tax id

- identificação de imposto não
- número de identificação do imposto
- n º do imposto #
- n º do imposto
- número do imposto
- número de registro de imposto
- táxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID do Tin
- Tin não
- Tin #
- unikalus identifikavimo kodas
- unikalus identifikavimo numeris
- número de identificação exclusivo
- número de identidade exclusivo
- uniqueidentityno #

## <a name="lithuania-passport-number"></a>Número de passaporte da Lituânia
Essa entidade de tipo de informação confidencial só está disponível no tipo de informação confidencial do número do Passport da UE.

### <a name="format"></a>Formatar

oito dígitos ou letras sem espaços ou delimitadores
  
### <a name="pattern"></a>Padrão

oito dígitos ou letras (não diferencia maiúsculas de minúsculas)
  
### <a name="checksum"></a>Soma de verificação

não aplicável
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_lithuania_eu_passport_number` localiza o conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_lithuania_eu_passport_number` foi encontrada. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_lithuania_eu_passport_number"></a>Keywords_lithuania_eu_passport_number

- passport number
- número de passaporte lithunian
- Passport não
- paso numeris


## <a name="luxemburg-drivers-license-number"></a>Número da carteira de motorista do Luxemburg
Essa entidade de tipo de informação confidencial só está disponível no tipo de informações confidenciais do número de licença do driver da UE.

### <a name="format"></a>Formatar

seis dígitos sem espaços e delimitadores
  
### <a name="pattern"></a>Padrão

seis dígitos 
  
### <a name="checksum"></a>Soma de verificação

Não
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_luxemburg_eu_driver's_license_number` localiza o conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_luxemburg_eu_driver's_license_number` foi encontrada. 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_luxemburg_eu_drivers_license_number"></a>Keywords_luxemburg_eu_driver ' s_license_number

- distribuição #
- driver license
- número de carteira de motorista
- licença de driver
- drivers driver'lic.
- drivers license
- drivers licence
- driver's license
- número da carteira de motorista
- número de licença do driver
- número da licença de dirigir
- dlno #
- fahrerlaubnis

## <a name="luxemburg-national-identification-number-natural-persons"></a>Número de identificação nacional do Luxemburg (pessoas naturais)

### <a name="format"></a>Formatar

13 dígitos sem espaços ou delimitadores
  
### <a name="pattern"></a>Padrão

13 dígitos:
  
- 11 dígitos 
- dois dígitos de verificação
    
### <a name="checksum"></a>Soma de verificação

sim
  
### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_luxemburg_eu_tax_file_number` localiza conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_luxemburg_eu_national_id_card` foi encontrada. 

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_luxemburg_eu_tax_file_number` localiza conteúdo que corresponde ao padrão. 


```xml
      <!-- Luxemburg National Identification Number (Natural persons) -->
      <Entity id="aaf661ed-29ec-426d-8bf9-880cad298ebb" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
          <Match idRef="Keywords_luxemburg_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_luxemburg_eu_telephone_number" />
            <Match idRef="Keywords_luxemburg_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_luxemburg_eu_national_id_card"></a>Keywords_luxemburg_eu_national_id_card

- ID eindeutige
- ID eindeutige-Nummer
- eindeutigeid #
- ID personnelle
- idpersonnelle #
- idpersonnelle
- código individual
- ID individual
- identificação individual
- identidade individual
- Numéro d'identification
- ID pessoal
- identificação pessoal
- identidade pessoal
- personalidno #
- personalidnumber #
- persönliche identifikationsnummer
- ID exclusiva
- identidade exclusiva
- uniqueidkey #

## <a name="luxemburg-passport-number"></a>Número de passaporte Luxemburg
Essa entidade de tipo de informação confidencial só está disponível no tipo de informação confidencial do número do Passport da UE.

### <a name="format"></a>Formatar

oito dígitos ou letras sem espaços ou delimitadores
  
### <a name="pattern"></a>Padrão

oito dígitos ou letras (não diferencia maiúsculas de minúsculas)
  
### <a name="checksum"></a>Soma de verificação

Não
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_nation_eu_passport_number` localiza o conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_nation_eu_passport_number` foi encontrada. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_nation_eu_passport_number"></a>Keywords_nation_eu_passport_number

- passport number
- número de passaporte da Letão
- Passport não
- passnummer

## <a name="luxemburg-national-identification-number-non-natural-persons"></a>Número de identificação nacional do Luxemburg (pessoas não naturais)

### <a name="format"></a>Formatar

11 dígitos
  
### <a name="pattern"></a>Padrão

11 dígitos
  
- dois dígitos
- um espaço opcional 
- três dígitos 
- um espaço opcional
- três dígitos 
- um espaço opcional
- dois dígitos
- um dígito de verificação
    
### <a name="checksum"></a>Soma de verificação

Sim
  
### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_luxemburg_eu_tax_file_number_non_natural` localiza conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_luxemburg_eu_tax_file_number` foi encontrada. 
    
Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_luxemburg_eu_tax_file_number_non_natural` localiza conteúdo que corresponde ao padrão. 
    
```xml
      <!-- Luxemburg National Identification Number (Non-natural persons) -->
      <Entity id="84bffa3a-d805-4788-a613-b1e4df3804cf" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number_non_natural" />
          <Match idRef="Keywords_luxemburg_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number_non_natural" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_luxemburg_eu_telephone_number" />
            <Match idRef="Keywords_luxemburg_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_luxemburg_eu_tax_file_number"></a>Keywords_luxemburg_eu_tax_file_number

- carte de sécurité
- Étain não
- étain #
- d'impôt de identificação
- identifikatiounsnummer de imposto de Luxemburgo
- numéro d'étain
- Numéro d'identification fiscal do Luxembourgeois
- Numéro d'identification fiscal
- segurança social
- sozialunterstützung
- sozialversécherung
- sozialversicherungsausweis
- ID steier
- steier identifikatiounsnummer
- steier nummer
- ID Steuer
- steueridentifikationsnummer
- steuernummer
- tax id

- identificação de imposto não
- número de identificação do imposto
- n º do imposto #
- n º do imposto
- número do imposto
- número de registro de imposto
- táxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID do Tin
- Tin não
- Tin #
- zinn #
- zinn
- zinnzahl


## <a name="malaysia-identification-card-number"></a>Número do cartão de identificação da Malásia

### <a name="format"></a>Formatar

12 dígitos contendo hifens opcionais

### <a name="pattern"></a>Padrão

12 dígitos:
- seis dígitos no formato AAMMDD que são a data de nascimento 
- um traço (opcional) 
- código de local de nascimento de duas letras 
- um traço (opcional) 
- três dígitos aleatórios 
- código sexo de um dígito

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular Regex_malaysia_id_card_number localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_malaysia_id_card_number for encontrada.

```xml
<!-- Malaysia ID Card Number -->
</Entity>
      <Entity id="7f0e921c-9677-435b-aba2-bb8f1013c749" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
            <IdMatch idRef="Regex_malaysia_id_card_number" />
            <Match idRef="Keyword_malaysia_id_card_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave
   
#### <a name="keyword_malaysia_id_card_number"></a>Keyword_malaysia_id_card_number

- cartão de aplicativo digital
- e/c
- e/c não
- Liga
- IC não
- id card
- Cartão de identificação
- cartão de identidade
- k/p
- n/p não
- kad akuan diri
- kad aplikasi digital
- kad pengenalan Malásia
- KP
- KP não
- mykad
- mykas
- mykid
- mypr
- mytentera
- cartão de identidade da Malásia
- cartão de identidade do Malasiano
- nric
- cartão de identificação pessoal

## <a name="malta-drivers-license-number"></a>Número da carteira de motorista do driver de Malta
Essa entidade de tipo de informação confidencial só está disponível no tipo de informações confidenciais do número de licença do driver da UE.

### <a name="format"></a>Formatar

Combinação de dois caracteres e seis dígitos no padrão especificado
  
### <a name="pattern"></a>Padrão

combinação de dois caracteres e seis dígitos:
  
- dois caracteres (dígitos ou letras, não diferenciam maiúsculas de minúsculas)
- um espaço (opcional)
- três dígitos
- um espaço (opcional)
- três dígitos
    
### <a name="checksum"></a>Soma de verificação

Não
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_malta_eu_driver's_license_number` localiza o conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_malta_eu_driver's_license_number` foi encontrada. 
    
```xml
<!-- EU Driver's License Number -->
 <Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Match idRef="Keywords_malta_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_malta_eu_drivers_license_number"></a>Keywords_malta_eu_driver ' s_license_number

- distribuição #
- driver license
- número de carteira de motorista
- licença de driver
- drivers driver'lic.
- drivers license
- drivers licence
- driver's license
- número da carteira de motorista
- número de licença do driver
- número da licença de dirigir
- dlno #
- liċenzja tas-sewqan

## <a name="malta-identity-card-number"></a>Número do cartão de identidade de Malta

### <a name="format"></a>Formatar

sete dígitos seguidos de uma letra
  
### <a name="pattern"></a>Padrão

sete dígitos seguidos de uma letra:
  
- sete dígitos 
- uma letra em "M, G, A, P, L, H, B, Z" (não diferencia maiúsculas de minúsculas)
    
### <a name="checksum"></a>Soma de verificação

Não aplicável
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_malta_eu_national_id_card` localiza o conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_malta_eu_national_id_card` foi encontrada. 
    
Uma política de DLP tem 65% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_malta_eu_national_id_card` localiza o conteúdo que corresponde ao padrão. 
    
```xml
      <!-- Malta Identity Card Number -->
      <Entity id="854b36b3-a388-4ac8-a4ec-677c2b5e4356" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_national_id_card" />
          <Match idRef="Keywords_malta_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_national_id_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_malta_eu_national_id_card"></a>Keywords_malta_eu_national_id_card

- número do serviço do cidadão
- ID tat-taxxa
- identifika numru tal-biljett
- Kodiċi numerali pessoali
- numru ta ' identifikazzjoni pessoal
- numru ta ' identifikazzjoni tat-taxxa
- numru ta ' identifikazzjoni uniku
- numru ta ' Identità uniku
- numru tas-servizz taċ-ċittadin
- numru tat-taxxa
- código numérico pessoal
- número de identificação exclusivo
- número de identidade exclusivo
- uniqueidentityno #


## <a name="malta-passport-number"></a>Número de passaporte de Malta
Essa entidade de tipo de informação confidencial só está disponível no tipo de informação confidencial do número do Passport da UE.

### <a name="format"></a>Formatar

sete dígitos sem espaços ou delimitadores
  
### <a name="pattern"></a>Padrão

sete dígitos 
  
### <a name="checksum"></a>Soma de verificação

Não
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_malta_eu_passport_number` localiza o conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_malta_eu_passport_number` foi encontrada. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_malta_eu_passport_number"></a>Keywords_malta_eu_passport_number

- passport number
- número de passaporte Maltês
- Passport não
- numru tal-passaport

## <a name="malta-tax-identification-number"></a>Número de identificação do imposto de Malta

### <a name="format"></a>Formatar

Para as nacionalidades maltês:
- sete dígitos e uma letra no padrão especificado
  
Entidades nacionais e Maltês que não são maltês:
- nove dígitos
  
### <a name="pattern"></a>Padrão

Nacionalidades maltês: sete dígitos e uma letra
  
- sete dígitos 
- uma letra (não diferencia maiúsculas de minúsculas)
    
Entidades de cidadãos e Maltês que não são maltês: nove dígitos
  
- nove dígitos 
    
### <a name="checksum"></a>Soma de verificação

Não aplicável
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- O Regex  `Regex_malta_eu_tax_file_number`  ou `Regex_malta_eu_tax_file_number_non_maltese_national` localiza conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_malta_eu_tax_file_number` foi encontrada. 
    
Uma política de DLP tem 65% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- O Regex  `Regex_malta_eu_tax_file_number` ou `Regex_malta_eu_tax_file_number_non_maltese_national` localiza conteúdo que corresponde ao padrão. 
    
```xml
      <!-- Malta Tax ID Number -->
      <Entity id="ec830c63-65f4-45d0-9d8c-910dc8334b20" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_tax_file_number" />
          <Match idRef="Keywords_malta_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_tax_file_number_non_maltese_national" />
          <Match idRef="Keywords_malta_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_tax_file_number_non_maltese_national" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_malta_eu_tax_file_number"></a>Keywords_malta_eu_tax_file_number

- número do serviço do cidadão
- ID tat-taxxa
- identifika numru tal-biljett
- Kodiċi numerali pessoali
- numru ta ' identifikazzjoni pessoal
- numru ta ' identifikazzjoni tat-taxxa
- numru ta ' identifikazzjoni uniku
- numru ta ' Identità uniku
- numru tas-servizz taċ-ċittadin
- numru tat-taxxa
- código numérico pessoal
- tax id

- identificação de imposto não
- número de identificação do imposto
- n º do imposto #
- n º do imposto
- número do imposto
- número de registro de imposto
- táxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID do Tin
- Tin não
- Tin #
- número de identificação exclusivo
- número de identidade exclusivo
- uniqueidentityno #

## <a name="netherlands-citizens-service-bsn-number"></a>Número do serviço do cidadão (BSN) Holanda

### <a name="format"></a>Formatar

oito e nove dígitos contendo espaços opcionais

### <a name="pattern"></a>Padrão

oito-nove dígitos:
- três dígitos 
- um espaço (opcional) 
- três dígitos 
- um espaço (opcional) 
- dois-três dígitos

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_netherlands_bsn localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_netherlands_bsn for encontrada.
- A soma de verificação passa.

```xml
      <!-- Netherlands Citizen's Service (BSN) Number -->
      <Entity id="c5f54253-ef7e-44f6-a578-440ed67e946d" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_bsn" />
          <Match idRef="Keywords_netherlands_eu_national_id_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_netherlands_eu_national_id_card"></a>Keywords_netherlands_eu_national_id_card
  
- BSN #
- BSN
- burgerservicenummer
- número do serviço do cidadão
- número de pessoa
- número pessoal
- código numérico pessoal
- número relacionado à pessoa
- persoonlijk nummer
- código de numerieke persoonlijke
- persoonsgebonden
- persoonsnummer
- sociaal-fiscaal nummer
- social-número fiscal
- sofi
- sofinummer
- uniek identificatienummer
- uniek identiteitsnummer
- número de identificação exclusivo
- número de identidade exclusivo
- uniqueidentityno #

## <a name="netherlands-drivers-license-number"></a>Número da carteira de motorista da Holanda
Essa entidade de tipo de informação confidencial só está disponível no tipo de informações confidenciais do número de licença do driver da UE.

### <a name="format"></a>Formatar

dez dígitos sem espaços e delimitadores
  
### <a name="pattern"></a>Padrão

dez dígitos
  
### <a name="checksum"></a>Soma de verificação

Não
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_netherlands_eu_driver's_license_number` localiza o conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_netherlands_eu_driver's_license_number` foi encontrada. 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_netherlands_eu_drivers_license_number"></a>Keywords_netherlands_eu_driver ' s_license_number

- distribuição #
- driver license
- número de carteira de motorista
- licença de driver
- drivers driver'lic.
- drivers license
- drivers licence
- driver's license
- número da carteira de motorista
- número de licença do driver
- número da licença de dirigir
- dlno #
- permis de conduire
- rijbewijs
- rijbewijsnummer


## <a name="netherlands-passport-number"></a>Número de passaporte Holanda
Essa entidade de tipo de informação confidencial só está disponível no tipo de informação confidencial do número do Passport da UE.

### <a name="format"></a>Formatar

nove letras ou dígitos sem espaços ou delimitadores
  
### <a name="pattern"></a>Padrão

nove letras ou dígitos
  
### <a name="checksum"></a>Soma de verificação

não aplicável
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_netherlands_eu_passport_number` localiza o conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_netherlands_eu_passport_number` foi encontrada. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_netherlands_eu_passport_number"></a>Keywords_netherlands_eu_passport_number

- número de passaporte holandês
- passport number
- número de passaporte Holanda
- nederlanden paspoort nummer
- paspoort
- nederlanden paspoortnummer
- paspoortnummer

## <a name="netherlands-tax-identification-number"></a>Número de identificação do imposto Holanda

### <a name="format"></a>Formatar

nove dígitos sem espaços ou delimitadores
  
### <a name="pattern"></a>Padrão

nove dígitos 
  
### <a name="checksum"></a>Soma de verificação

Sim
  
### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_netherlands_eu_tax_file_number` localiza conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_netherlands_eu_tax_file_number` foi encontrada. 
    
Uma política de DLP tem 65% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_netherlands_eu_tax_file_number` localiza conteúdo que corresponde ao padrão. 
    
```xml
      <!-- Netherlands Tax Identification Number -->
      <Entity id="01f42a64-eba7-4892-a67b-398237e4ade2" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
          <Match idRef="Keywords_netherlands_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_netherlands_eu_tax_file_number"></a>Keywords_netherlands_eu_tax_file_number

- btw nummer
- identificação de imposto hollânske
- hulandes número de ID de impuesto
- hulandes impuesto de identificação
- identificatienummer a última
- identificatienummer Van é última
- número de identificação do impuesto
- número do impuesto
- Países Baixos Nummer ID da última vez
- Países Baixos identificatie
- Países Baixos identificatienummer
- Países Baixos belastingnummer
- Nederlandse identificatie
- identificação de imposto Holanda
- identificação de imposto do Netherland
- Tin Holanda
- Tin do Netherland
- tax id

- identificação de imposto não
- número de identificação do imposto
- tal de identificação de imposto
- n º do imposto #
- n º do imposto
- número do imposto
- número de registro de imposto
- tal de imposto
- táxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID do Tin
- Tin não
- Tin #


## <a name="netherlands-value-added-tax-number"></a>Número de imposto sobre valor Holanda adicionado

### <a name="format"></a>Formatar

padrão de 14 caracteres alfanuméricos

### <a name="pattern"></a>Padrão

padrão alfanumérico de 14 caracteres:

- N ou n
- L ou l
- espaço, ponto ou hífen opcional
- nove dígitos
- espaço, ponto ou hífen opcional
- B ou b
- dois dígitos

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_netherlands_value_added_tax_number localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keywords_netherlands_value_added_tax_number for encontrada.

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_netherlands_value_added_tax_number localiza o conteúdo que corresponde ao padrão.

```xml
      <!-- Netherlands Value Added Tax Number -->
      <Entity id="4f320d9b-4972-41ae-b337-88d499bb1ade" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_value_added_tax_number" />
          <Match idRef="Keywords_netherlands_value_added_tax_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_netherlands_value_added_tax_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_netherlands_value_added_tax_number"></a>Keyword_netherlands_value_added_tax_number

- número de IVA
- IVA não
- IVA #
- wearde tafoege de imposto de getal
- btw nûmer
- btw-nummer


## <a name="new-zealand-bank-account-number"></a>Número de conta bancária da Nova Zelândia

### <a name="format"></a>Formatar

padrão de 14 a 16 dígitos com delimitador opcional

### <a name="pattern"></a>Padrão

padrão de 14 a 16 dígitos com delimitador opcional:

- dois dígitos
- um hífen ou espaço opcional
- três a quatro dígitos
- um hífen ou espaço opcional
- sete dígitos
- um hífen ou espaço opcional
- dois a três dígitos
- um hífen ou espaço de opções

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_new_zealand_bank_account_number localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keywords_new_zealand_bank_account_number for encontrada.

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_new_zealand_bank_account_number localiza o conteúdo que corresponde ao padrão.

```xml
      <!-- New Zealand Bank Account Number -->
      <Entity id="1a97fc2b-dd2f-48f1-bc4e-2ddf25813956" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_new_zealand_bank_account_number" />
          <Match idRef="Keywords_new_zealand_bank_account_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_new_zealand_bank_account_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_new_zealand_bank_account_number"></a>Keyword_new_zealand_bank_account_number

- número da conta
- conta bancária
- bank_acct_id
- bank_acct_branch
- bank_acct_nbr


## <a name="new-zealand-drivers-license-number"></a>Número da carteira de motorista da Nova Zelândia

### <a name="format"></a>Formatar

padrão de oito caracteres alfanuméricos

### <a name="pattern"></a>Padrão

padrão de oito caracteres alfanuméricos

- duas letras 
- seis dígitos

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_newzealand_driver_license_number localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keywords_newzealand_driver_license_number for encontrada.

Uma política de DLP tem 65% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_newzealand_driver_license_number localiza o conteúdo que corresponde ao padrão.

```xml
      <!-- New Zealand Driver License Number -->
      <Entity id="1924b377-d287-49c9-a737-cfe7a8a2615a" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_newzealand_driver_license_number" />
          <Match idRef="Keywords_newzealand_driver_license_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_newzealand_driver_license_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_new_zealand_drivers_license_number"></a>Keyword_new_zealand_drivers_license_number

- driverlicence
- driverlicences
- Driver de driver'lic
- licença de driver
- licenças de driver
- driverslic
- driverslicence
- driverslicences
- drivers de driver'lic
- drivers de driver'lics
- licença de drivers
- licenças de drivers
- driver'lic
- driver'lics
- driver'licence
- driver'licences
- Driver ' driver'lic
- Driver ' driver'lics
- licença do driver
- licenças do driver
- driver'slic
- driver'slics
- driver'slicence
- driver'slicences
- driver'lic do driver
- driver'lics do driver
- licença do driver
- licenças do driver
- driverlic #
- driverlics #
- driverlicence #
- driverlicences #
- Driver de driver'lic #
- Driver de driver'lics #
- licença de driver #
- licenças de driver #
- driverslic #
- driverslics #
- driverslicence #
- driverslicences #
- drivers de driver'lic #
- drivers de driver'lics #
- licença de drivers #
- licenças de drivers #
- driver'lic #
- driver'lics #
- driver'licence #
- driver'licences #
- Driver ' driver'lic #
- Driver ' driver'lics #
- licença do driver #
- licenças do driver #
- driver'slic #
- driver'slics #
- driver'slicence #
- driver'slicences #
- driver'lic do driver #
- driver'lics do driver #
- licença do driver #
- licenças do driver #
- 
international driving permit
- international driving permits
- Associação de automóvel do NZ
- Nova Zelândia Associação de automóvel


## <a name="new-zealand-inland-revenue-number"></a>Número de receita da Nova Zelândia

### <a name="format"></a>Formatar

oito ou nove dígitos com delimitadores opcionais

### <a name="pattern"></a>Padrão

oito ou nove dígitos com delimitadores opcionais

- dois ou três dígitos
- um espaço ou hífen opcional
- três dígitos
- um espaço ou hífen opcional
- três dígitos

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_new_zealand_inland_revenue_number localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keywords_new_zealand_inland_revenue_number for encontrada.

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_new_zealand_inland_revenue_number localiza o conteúdo que corresponde ao padrão.

```xml
      <!-- New Zealand Inland Revenue Number -->
      <Entity id="dd0fe2bc-7bcf-455f-bac1-83b1e3eb25fd" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_new_zealand_inland_revenue_number" />
          <Match idRef="Keywords_new_zealand_inland_revenue_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_new_zealand_inland_revenue_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_new_zealand_inland_revenue_number"></a>Keyword_new_zealand_inland_revenue_number

- IRD não.
- IRD não #
- IRD NZ
- Nova Zelândia IRD
- número do IRD
- número de receita Inland


## <a name="new-zealand-ministry-of-health-number"></a>Ministério do número de integridade da Nova Zelândia

### <a name="format"></a>Formatar

três letras, um espaço (opcional) e quatro dígitos

### <a name="pattern"></a>Padrão

três letras (não diferencia maiúsculas de minúsculas) um espaço (opcional) quatro dígitos

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_new_zealand_ministry_of_health_number localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_nz_terms for encontrada.
- A soma de verificação passa.

```xml
<!-- New Zealand Health Number -->
<Entity id="2b71c1c8-d14e-4430-82dc-fd1ed6bf05c7" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_new_zealand_ministry_of_health_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_nz_terms" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_nz_terms"></a>Keyword_nz_terms

- NHI 
- Nova Zelândia 
- Integridade 
- tratamento 


## <a name="new-zealand-social-wlefare-number"></a>Número de wlefare social da Nova Zelândia

### <a name="format"></a>Formatar

nove dígitos

### <a name="pattern"></a>Padrão

nove dígitos

- três dígitos
- um hífen opcional
- três dígitos
- um hífen opcional
- três dígitos

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_newzealand_social_welfare_number localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keywords_newzealand_social_welfare_number for encontrada.

Uma política de DLP tem 65% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_newzealand_social_welfare_number localiza o conteúdo que corresponde ao padrão.

```xml
      <!-- Newzealand Social Welfare Number -->
      <Entity id="20f3c48d-4ac1-4cd2-86bd-34ecc1826e9d" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_newzealand_social_welfare_number" />
          <Match idRef="Keywords_newzealand_social_welfare_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_newzealand_social_welfare_number" />
        </Pattern>
      </Entity>
    </Version>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_new_zealand_social_welfare_number"></a>Keyword_new_zealand_social_welfare_number

- Welfare social #
- Welfare social #
- Welfare social não.
- número do Welfare social
- swn #

   
## <a name="norway-identification-number"></a>Número de identificação da Noruega

### <a name="format"></a>Formatar

11 dígitos

### <a name="pattern"></a>Padrão

11 dígitos:
- seis dígitos no formato DDMMAA que são a data de nascimento 
- número individual de três dígitos 
- dois dígitos de verificação

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_norway_id_number localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_norway_id_number for encontrada.
- A soma de verificação passa.

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_norway_id_numbe localiza o conteúdo que corresponde ao padrão.
- A soma de verificação passa.

```xml
<!-- Norway Identification Number -->
<Entity id="d4c8a798-e9f2-4bd3-9652-500d24080fc3" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_norway_id_number"/>
     <Match idRef="Keyword_norway_id_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_norway_id_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_norway_id_number"></a>Keyword_norway_id_number

- Número de identificação pessoal
- Número de Identificação Norueguês
- Número de Identificação
- Identificador
- Personnummer
- Fødselsnummer

   
## <a name="philippines-unified-multi-purpose-identification-number"></a>Número de identificação de multiuso unificado Filipinas

### <a name="format"></a>Formatar

12 dígitos separados por hifens

### <a name="pattern"></a>Padrão

12 dígitos:
- quatro dígitos 
- um hífen 
- sete dígitos 
- um hífen 
- um dígito

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular Regex_philippines_unified_id localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_philippines_id for encontrada.

```xml
<!-- Philippines Unified Multi-Purpose ID number -->
<Entity id="019b39dd-8c25-4765-91a3-d9c6baf3c3b3" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_philippines_unified_id"/>
     <Match idRef="Keyword_philippines_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave
   
#### <a name="keyword_philippines_id"></a>Keyword_philippines_id

- Identificação Multiuso Unificada 
- UMID 
- Cartão de Identidade 
- Pinag-isang Multi-Layunin ID

## <a name="poland-drivers-license-number"></a>Número da carteira de motorista do Polônia
Essa entidade de tipo de informação confidencial só está disponível no tipo de informações confidenciais do número de licença do driver da UE.

### <a name="format"></a>Formatar

14 dígitos contendo 2 barras
  
### <a name="pattern"></a>Padrão

14 dígitos e 2 barras de avanço:
  
- cinco dígitos 
- uma barra
- dois dígitos
- uma barra
- sete dígitos
    
### <a name="checksum"></a>Soma de verificação

Não
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_poland_eu_driver's_license_number` localiza o conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_poland_eu_driver's_license_number` foi encontrada. 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Match idRef="Keywords_poland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_poland_eu_drivers_license_number"></a>Keywords_poland_eu_driver ' s_license_number

- distribuição #
- driver license
- número de carteira de motorista
- licença de driver
- drivers driver'lic.
- drivers license
- drivers licence
- driver's license
- número da carteira de motorista
- número de licença do driver
- número da licença de dirigir
- dlno #
- prawo jazdy

## <a name="poland-identity-card"></a>Cartão de identidade da Polônia

### <a name="format"></a>Formatar

três letras e seis dígitos

### <a name="pattern"></a>Padrão

três letras (não diferencia maiúsculas de minúsculas) seguidas de seis dígitos

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_polish_national_id localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_polish_national_id_passport_number for encontrada.
- A soma de verificação passa.

```xml
<!-- Poland Identity Card-->
<Entity id="25E64989-ED5D-40CA-A939-6C14183BB7BF" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_national_id" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_poland_national_id_passport_number"></a>Keyword_poland_national_id_passport_number

- Dowód osobisty
- Numer dowodu osobistego
- Nazwa i numer dowodu osobistego
- Nazwa i NR dowodu osobistego
- Nazwa i nr dowodu tożsamości
- Dowód Tożsamości
- Dow. Opera.

   
## <a name="poland-national-id-pesel"></a>ID nacional da Polônia (PESEL)

### <a name="format"></a>Formatar

11 dígitos

### <a name="pattern"></a>Padrão

- 6 dígitos representando data de nascimento no formato AAMMDD
- 4 dígitos
- 1 dígito de verificação

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_pesel_identification_number localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_pesel_identification_number for encontrada.
- A soma de verificação passa.

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_pesel_identification_number localiza conteúdo que corresponde ao padrão.
- A soma de verificação passa.

```xml
      <!-- Poland National ID (PESEL) -->
      <Entity id="E3AAF206-4297-412F-9E06-BA8487E22456" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_pesel_identification_number" />
          <Match idRef="Keyword_pesel_identification_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_pesel_identification_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_pesel_identification_number"></a>Keyword_pesel_identification_number

- dowód osobisty
- dowódosobisty
- niepowtarzalny numer
- niepowtarzalnynumer
- Nr.-PESEL
- NR-PESEL
- numer identyfikacyjny
- PESEL
- tożsamości narodowej

   
## <a name="poland-passport-number"></a>Número de passaporte da Polônia
Essa entidade de tipo de informação confidencial está incluída no tipo de informação confidencial do número do Passport da UE e está disponível como uma entidade de tipo de informação confidencial autônoma.

### <a name="format"></a>Formatar

duas letras e sete dígitos

### <a name="pattern"></a>Padrão

Duas letras (não diferencia maiúsculas de minúsculas) seguidas de sete dígitos

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_polish_passport_number localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_polish_national_id_passport_number for encontrada.
- A soma de verificação passa.

```xml
<!-- Poland Passport Number -->
<Entity id="03937FB5-D2B6-4487-B61F-0F8BFF7C3517" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_passport_number" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
</Version>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_poland_national_id_passport_number"></a>Keyword_poland_national_id_passport_number

- Numer paszportu
- Nr. Paszportu
- Paszport

## <a name="poland-regon-number"></a>Número da Polônia REGON

### <a name="format"></a>Formatar

número de nove dígitos ou 14 dígitos

### <a name="pattern"></a>Padrão

número de nove dígitos ou 14 dígitos:

- nove dígitos ou 
- nove dígitos
- hífen
- cinco dígitos

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_polish_regon_number localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keywords_polish_regon_number for encontrada.

Uma política de DLP tem 65% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_polish_regon_number localiza o conteúdo que corresponde ao padrão.

```xml
      <!-- Polish REGON Number  -->
      <Entity id="fc87b421-f437-4f8b-b739-29a735ead0d9" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_regon_number" />
          <Match idRef="Keywords_polish_regon_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_polish_regon_number" />
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_poland_regon_number"></a>Keywords_poland_regon_number

- ID REGON
- número estatístico
- ID estatística
- estatística não
- número do REGON
- regonid #
- regonno #
- ID da empresa
- CompanyID #
- companyidno #
- numer statystyczny
- numeru regon
- numerstatystyczny #
- numeruregon #


## <a name="poland-tax-identification-number"></a>Número de identificação de imposto da Polônia

### <a name="format"></a>Formatar

11 dígitos sem espaços ou delimitadores
  
### <a name="pattern"></a>Padrão

11 dígitos
  
### <a name="checksum"></a>Soma de verificação

Sim
  
### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_poland_eu_tax_file_number` localiza conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_poland_eu_tax_file_number` foi encontrada. 
    
  
```xml
      <!-- Poland Tax Identification Number -->
      <Entity id="1ff28b4d-40f2-49e9-b677-9606a88e2bca" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_poland_eu_tax_file_number" />
          <Match idRef="Keywords_poland_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_poland_eu_tax_file_number"></a>Keywords_poland_eu_tax_file_number

- nip #
- nip
- numer identyfikacji podatkowej
- numeridentyfikacjipodatkowej #
- tax id

- identificação de imposto não
- número de identificação do imposto
- n º do imposto #
- n º do imposto
- número do imposto
- número de registro de imposto
- táxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID do Tin
- Tin não
- Tin #
- ID de IVA #
- ID de IVA
- IVA não
- número de IVA
- vatid #
- vatid
- vatno #
   

## <a name="portugal-citizen-card-number"></a>Número de cartão de cidadão da Portugal

### <a name="format"></a>Formatar

oito dígitos

### <a name="pattern"></a>Padrão

oito dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular Regex_portugal_citizen_card localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_portugal_citizen_card for encontrada.

```xml
<!-- Portugal Citizen Card Number -->
<Entity id="91a7ece2-add4-4986-9a15-c84544d81ecd" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_portugal_citizen_card"/>
     <Match idRef="Keyword_portugal_citizen_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_portugal_citizen_card"></a>Keyword_portugal_citizen_card

- bilhete de identidade
- cartão de cidadão
- cartão de cidadão
- número do documento
- documento de identificação
- número de identificação
- identificação não
- identification number

- cartão de identidade não
- número do cartão de identidade
- cartão de ID nacional
- placa
- número bi de Portugal
- número de identificação civil
- número de identificação fiscal
- número do documento
- número de bi de Portugal


## <a name="portugal-drivers-license-number"></a>Número da carteira de motorista de Portugal
Essa entidade de tipo de informação confidencial só está disponível no tipo de informações confidenciais do número de licença do driver da UE.

### <a name="format"></a>Formatar

duas letras seguidas por sete números no padrão especificado
  
### <a name="pattern"></a>Padrão

duas letras seguidas por sete números com caracteres especiais:
  
- duas letras (não diferencia maiúsculas de minúsculas) 
- um hífen
- seis dígitos
- um espaço
- um dígito
    
### <a name="checksum"></a>Soma de verificação

Não
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_portugal_eu_driver's_license_number` localiza o conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_portugal_eu_driver's_license_number` foi encontrada. 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Match idRef="Keywords_portugal_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_portugal_eu_drivers_license_number"></a>Keywords_portugal_eu_driver ' s_license_number

- distribuição #
- driver license
- número de carteira de motorista
- licença de driver
- drivers driver'lic.
- drivers license
- drivers licence
- driver's license
- número da carteira de motorista
- número de licença do driver
- número da licença de dirigir
- dlno #
- carteira de motorista

## <a name="portugal-passport-number"></a>Número de passaporte de Portugal
Essa entidade de tipo de informação confidencial só está disponível no tipo de informação confidencial do número do Passport da UE.

### <a name="format"></a>Formatar

uma letra seguida de seis dígitos sem espaços ou delimitadores
  
### <a name="pattern"></a>Padrão

uma letra seguida por seis dígitos:
  
- uma letra (não diferencia maiúsculas de minúsculas)
- seis dígitos
    
### <a name="checksum"></a>Soma de verificação

Não
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_portugal_eu_passport_number` localiza o conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_portugal_eu_passport_number` foi encontrada. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_portugal_eu_passport_number"></a>Keywords_portugal_eu_passport_number

- passport number
- número de passaporte Português
- Passport não
- número do passaporte

## <a name="portugal-tax-identification-number"></a>Número de identificação do imposto Portugal

### <a name="format"></a>Formatar

nove dígitos com espaços opcionais
  
### <a name="pattern"></a>Padrão

- 3 dígitos
- um espaço opcional
- 3 dígitos
- um espaço opcional
- 3 dígitos
  
### <a name="checksum"></a>Soma de verificação

Sim
  
### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_portugal_eu_tax_file_number` localiza conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_portugal_eu_tax_file_number` foi encontrada. 
    
Uma política de DLP tem 65% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_portugal_eu_tax_file_number` localiza conteúdo que corresponde ao padrão. 
    
```xml
      <!-- Portugal Tax Identification Number -->
      <Entity id="65372402-3131-4f1e-9983-4439841d1f15" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_portugal_eu_tax_file_number" />
          <Match idRef="Keywords_portugal_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_portugal_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_portugal_eu_tax_file_number"></a>Keywords_portugal_eu_tax_file_number

- CPF #
- CPF
- nse #
- nse
- número de identificação fisca
- fiscal numero
- tax id

- identificação de imposto não
- número de identificação do imposto
- n º do imposto #
- n º do imposto
- número do imposto
- número de registro de imposto
- táxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID do Tin
- Tin não
- Tin #


## <a name="romania-drivers-license-number"></a>Número da carteira de motorista do Romênia
Essa entidade de tipo de informação confidencial só está disponível no tipo de informações confidenciais do número de licença do driver da UE.

### <a name="format"></a>Formatar

um caractere seguido por oito dígitos
  
### <a name="pattern"></a>Padrão

um caractere seguido por oito dígitos:
  
- uma letra (não diferencia maiúsculas de minúsculas) ou dígito 
- oito dígitos
    
### <a name="checksum"></a>Soma de verificação

Não
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_romania_eu_driver's_license_number` localiza o conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_romania_eu_driver's_license_number` foi encontrada. 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Match idRef="Keywords_romania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_romania_eu_drivers_license_number"></a>Keywords_romania_eu_driver ' s_license_number

- distribuição #
- driver license
- número de carteira de motorista
- licença de driver
- drivers driver'lic.
- drivers license
- drivers licence
- driver's license
- número da carteira de motorista
- número de licença do driver
- número da licença de dirigir
- dlno #
- permé de conducere

## <a name="romania-personal-numeric-code-cnp"></a>Código numérico da Romênia (CNP)

### <a name="format"></a>Formatar

13 dígitos sem espaços e delimitadores
  
### <a name="pattern"></a>Padrão

- 1 dígito de 1-9
- 6 dígitos representando data de nascimento (AAMMDD)
- 2 dígitos que podem ser 01-52 ou 99
- 4 dígitos

### <a name="checksum"></a>Soma de verificação

Sim
  
### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_romania_eu_national_id_card` localiza conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_romania_eu_national_id_card` foi encontrada. 
    
Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_romania_eu_national_id_card` localiza conteúdo que corresponde ao padrão. 
    
```xml
      <!-- Romania Personal Numerical Code (CNP) -->
      <Entity id="eb5fa399-fe28-4c67-8188-d63a616ed89c" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_romania_eu_national_id_card" />
          <Match idRef="Keywords_romania_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_romania_eu_national_id_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_romania_eu_national_id_card"></a>Keywords_romania_eu_national_id_card

- cnp #
- cnp
- identificare de c.o.d. pessoal
- c.o.d. numérico pessoal
- UNIC de c.o.d. identificare
- codnumericpersonal #
- codul fiscal do Nr.
- identificarea fiscală nr #
- ID-UL Taxei
- número de seguro
- insurancenumber #
- ID nacional #
- 
national id
- número de identificação nacional
- număr identificare pessoal
- număr identitate
- număr pessoal do UNIC
- număridentitate #
- număridentitate
- numărpersonalunic #
- numărpersonalunic
- număru de identificare Fiscală
- numărul de identificare Fiscală
- código numérico pessoal
- pessoal #
- pessoal
- arquivo de imposto não
- número do arquivo de imposto
- tax id

- identificação de imposto não
- número de identificação do imposto
- n º do imposto #
- n º do imposto
- número do imposto
- número de registro de imposto
- táxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID do Tin
- Tin não
- Tin #
- número de identificação exclusivo
- número de identidade exclusivo
- uniqueidentityno #
- uniqueidentityno

## <a name="romania-passport-number"></a>Número de passaporte da Romênia
Essa entidade de tipo de informação confidencial só está disponível no tipo de informação confidencial do número do Passport da UE.

### <a name="format"></a>Formatar

oito ou nove dígitos sem espaços e delimitadores
  
### <a name="pattern"></a>Padrão

oito ou nove dígitos
  
### <a name="checksum"></a>Soma de verificação

Não
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_romania_eu_passport_number` localiza o conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_romania_eu_passport_number` foi encontrada. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_romania_eu_passport_number"></a>Keywords_romania_eu_passport_number

- passport number
- número de passaporte romeno
- Passport não
- numărul pașaportului


## <a name="russia-passport-number-domestic"></a>Número de passaporte nacional da Rússia

### <a name="format"></a>Formatar

número de dez dígitos

### <a name="pattern"></a>Padrão

número de dez dígitos:

- dois dígitos
- um espaço ou hífen opcional
- dois dígitos
- um espaço opcional
- seis dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A Regex_Russian_Passport_Number_Domestic Regex localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_Russian_Passport_Number for encontrada.

```xml
      <!-- Russian Passport Number Domestic -->
      <Entity id="76ec2f5d-cedb-48e1-8070-1998794af445" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_Russian_Passport_Number_Domestic" />
          <Match idRef="Keyword_Russian_Passport_Number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_russia_passport_number_domestic"></a>Keyword_russia_passport_number_domestic

- número de passaporte
- Passport não
- Passaport #
- ID do passaporte
- passportno #
- passportnumber #
- паспорт нет
- ID паспорт
- pоссийской паспорт
- pусский номер паспорта
- паспорт #
- паспортid #
- номер паспорта
- номерпаспорта #


## <a name="russia-passport-number-international"></a>Número internacional do Passport da Rússia

### <a name="format"></a>Formatar

número de nove dígitos

### <a name="pattern"></a>Padrão

número de nove dígitos:

- dois dígitos
- um espaço ou hífen opcional
- sete dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A Regex_Russian_Passport_Number_International Regex localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_Russian_Passport_Number for encontrada.

```xml
      <!-- Russian Passport Number International -->
      <Entity id="ac5f4878-75e4-4b82-af2d-02e13ea9f411" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_Russian_Passport_Number_International" />
          <Match idRef="Keyword_Russian_Passport_Number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_russia_passport_number_international"></a>Keywords_russia_passport_number_international

- número de passaporte
- Passport não
- Passaport #
- ID do passaporte
- passportno #
- passportnumber #
- паспорт нет
- ID паспорт
- pоссийской паспорт
- pусский номер паспорта
- паспорт #
- паспортid #
- номер паспорта
- номерпаспорта #


## <a name="saudi-arabia-national-id"></a>ID nacional da Arábia Saudita

### <a name="format"></a>Formatar

dez dígitos

### <a name="pattern"></a>Padrão

dez dígitos consecutivos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular Regex_saudi_arabia_national_id localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_saudi_arabia_national_id for encontrada.

```xml
<!-- Saudi Arabia National ID -->
<Entity id="8c5a0ba8-404a-41a3-8871-746aa21ee6c0" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_saudi_arabia_national_id" />
        <Any minMatches="1">
          <Match idRef="Keyword_saudi_arabia_national_id" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_saudi_arabia_national_id"></a>Keyword_saudi_arabia_national_id

- Identification Card 
- I card number 
- ID number 
- الوطنية الهوية بطاقة رقم 

   
## <a name="singapore-national-registration-identity-card-nric-number"></a>Número do cartão de identidade do Registro Nacional (NRIC) da Cingapura

### <a name="format"></a>Formatar

nove letras e dígitos

### <a name="pattern"></a>Padrão

- nove letras e dígitos:
- a letra "F", "G", "S" ou "T" (não diferencia maiúsculas de minúsculas) 
- sete dígitos 
- um dígito de verificação alfabética

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular Regex_singapore_nric localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_singapore_nric for encontrada.
- A soma de verificação passa.

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular Regex_singapore_nric localiza o conteúdo que corresponde ao padrão.
- A soma de verificação passa.

```xml
<!-- Singapore National Registration Identity Card (NRIC) Number -->
<Entity id="cead390a-dd83-4856-9751-fb6dc98c34da" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_singapore_nric"/>
     <Match idRef="Keyword_singapore_nric"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_singapore_nric"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave
   
#### <a name="keyword_singapore_nric"></a>Keyword_singapore_nric

- Número do Cartão de Identidade do Registro Nacional 
- Número do Cartão de Identidade 
- NRIC 
- Liga 
- Número de Identificação Estrangeira 
- ALETA 
- 身份证 
- 身份證 

## <a name="slovakia-drivers-license-number"></a>Número da carteira de motorista do Eslováquia
Essa entidade de tipo de informação confidencial só está disponível no tipo de informações confidenciais do número de licença do driver da UE.

### <a name="format"></a>Formatar

um caractere seguido por sete dígitos
  
### <a name="pattern"></a>Padrão

um caractere seguido por sete dígitos
  
- uma letra (não diferencia maiúsculas de minúsculas) ou dígito
- sete dígitos 
    
### <a name="checksum"></a>Soma de verificação

Não
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_slovakia_eu_driver's_license_number` localiza o conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_slovakia_eu_driver's_license_number` foi encontrada. 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovaknia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_slovakia_eu_drivers_license_number"></a>Keywords_slovakia_eu_driver ' s_license_number

- distribuição #
- driver license
- número de carteira de motorista
- licença de driver
- drivers driver'lic.
- drivers license
- drivers licence
- driver's license
- número da carteira de motorista
- número de licença do driver
- número da licença de dirigir
- dlno #
- vodičský preukaz

## <a name="slovakia-personal-number"></a>Número pessoal da Eslováquia

### <a name="format"></a>Formatar

nove ou dez dígitos contendo barra invertida opcional
  
### <a name="pattern"></a>Padrão

- 6 dígitos representando data de nascimento
- barra opcional (/)
- 3 dígitos
- 1 dígito de verificação opcional
  
### <a name="checksum"></a>Soma de verificação

Sim
  
### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_slovakia_eu_national_id_card` localiza conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_slovakia_eu_national_id_card` foi encontrada. 
    
Uma política de DLP tem 65% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_slovakia_eu_national_id_card` localiza conteúdo que corresponde ao padrão. 
    
```xml
      <!-- Slovakia Personal Number -->
      <Entity id="951c26b7-3b35-4f73-924b-15dd599cb9ab" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovakia_eu_national_id_card" />
          <Match idRef="Keywords_slovakia_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_slovakia_eu_national_id_card" />
        </Pattern>
      </Entity>
    </Version>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_slovakia_eu_national_id_card"></a>Keywords_slovakia_eu_national_id_card

- azonosító szám
- número de nascimento
- číslo národnej identifikačnej karty
- číslo občianského preukazu
- daňové číslo
- número de identificação
- identificação não
- identification number

- identifikačná karta č
- identifikačné číslo
- cartão de identidade não
- número do cartão de identidade
- národná identifikačná značka č
- número nacional
- nationalnumber #
- nemzeti személyazonosító igazolvány
- personalidnumber #
- rč
- rodne cislo
- rodné číslo
- social security number

- es #
- es
- személyi igazolvány szám
- személyi igazolvány száma
- személyigazolvány szám
- arquivo de imposto não
- número do arquivo de imposto
- tax id

- identificação de imposto não
- número de identificação do imposto
- n º do imposto #
- n º do imposto
- número do imposto
- número de registro de imposto
- táxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID do Tin
- Tin não
- Tin #

## <a name="slovakia-passport-number"></a>Número de passaporte da Eslováquia
Essa entidade de tipo de informação confidencial só está disponível no tipo de informação confidencial do número do Passport da UE.

### <a name="format"></a>Formatar

um dígito ou letra seguido por sete dígitos sem espaços ou delimitadores
  
### <a name="pattern"></a>Padrão

um dígito ou letra (não diferencia maiúsculas de minúsculas) seguido por sete dígitos
  
### <a name="checksum"></a>Soma de verificação

Não
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_slovakia_eu_passport_number` localiza o conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_slovakia_eu_passport_number` foi encontrada. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_slovakia_eu_passport_number"></a>Keywords_slovakia_eu_passport_number

- passport number
- número de passaporte eslovaco
- Passport não
- číslo pasu


## <a name="slovenia-drivers-license-number"></a>Número da carteira de motorista do Eslovênia
Essa entidade de tipo de informação confidencial só está disponível no tipo de informações confidenciais do número de licença do driver da UE.

### <a name="format"></a>Formatar

nove dígitos sem espaços e delimitadores
  
### <a name="pattern"></a>Padrão

nove dígitos
  
### <a name="checksum"></a>Soma de verificação

Não
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_slovenia_eu_driver's_license_number` localiza o conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_slovenia_eu_driver's_license_number` foi encontrada. 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_slovenia_eu_drivers_license_number"></a>Keywords_slovenia_eu_driver ' s_license_number

- distribuição #
- driver license
- número de carteira de motorista
- licença de driver
- drivers driver'lic.
- drivers license
- drivers licence
- driver's license 
- número da carteira de motorista
- número de licença do driver
- número da licença de dirigir
- dlno #
- vozniško dovoljenje

## <a name="slovenia-unique-master-citizen-number"></a>Número de cidadão mestre exclusivo da Eslovênia

### <a name="format"></a>Formatar

13 dígitos sem espaços ou delimitadores
  
### <a name="pattern"></a>Padrão

13 dígitos no padrão especificado:
  
- sete dígitos que correspondem à data de nascimento (DDMMLLL), onde "LLL" corresponde aos últimos três dígitos do ano de nascimento 
- dois dígitos que correspondem à área de nascimento "50"
- três dígitos que correspondem a uma combinação de sexo e número de série para pessoas nasceu no mesmo dia (000-499 para macho e 500-999 para fêmea)
- um dígito de verificação
    
### <a name="checksum"></a>Soma de verificação

Sim
  
### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_slovenia_eu_national_id_card` localiza conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_slovenia_eu_national_id_card` foi encontrada. 
    
Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_slovenia_eu_national_id_card` localiza conteúdo que corresponde ao padrão. 
    
```xml
      <!-- Slovenia Unique Master Citizen Number -->
      <Entity id="68948b27-803d-41e4-adf1-13e05eb541bb" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovenia_eu_national_id_card" />
          <Match idRef="Keywords_slovenia_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovenia_eu_national_id_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_slovenia_eu_national_id_card"></a>Keywords_slovenia_eu_national_id_card

- edinstvena številka glavnega državljana
- emšo
- enotna maticna številka obcana
- cartão de identificação
- identification number

- identifikacijska številka
- cartão de identidade
- ID Nacionalna
- lista de potni nacionalni
- 
national id
- osebna izkaznica
- osebni koda
- osebni ne
- osebni številka
- código pessoal
- número pessoal
- código numérico pessoal
- številka državljana
- número exclusivo do cidadão
- número de identificação exclusivo
- número de identidade exclusivo
- número de cidadão mestre exclusivo
- número de registro exclusivo
- uniqueidentityno #
- uniqueidentityno #

## <a name="slovenia-passport-number"></a>Número de passaporte da Eslovênia
Essa entidade de tipo de informação confidencial só está disponível no tipo de informação confidencial do número do Passport da UE.

### <a name="format"></a>Formatar

duas letras seguidas por sete dígitos sem espaços ou delimitadores
  
### <a name="pattern"></a>Padrão

duas letras seguidas por sete dígitos:
  
- a letra "P"
- uma letra maiúscula
- sete dígitos
    
### <a name="checksum"></a>Soma de verificação

Não
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_slovenia_eu_passport_number` localiza o conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_slovenia_eu_passport_number` foi encontrada. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_slovenia_eu_passport_number"></a>Keywords_slovenia_eu_passport_number

- passport number
- número de passaporte esloveno
- Passport não
- lista de številka potnega

## <a name="slovenia-tax-identification-number"></a>Número de identificação do imposto da Eslovênia

### <a name="format"></a>Formatar

oito dígitos sem espaços ou delimitadores
  
### <a name="pattern"></a>Padrão

- um dígito de 1-9
- seis dígitos
- um dígito de verificação
  
### <a name="checksum"></a>Soma de verificação

Sim
  
### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_slovenia_eu_tax_file_number` localiza conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_slovenia_eu_tax_file_number` foi encontrada. 
    
Uma política de DLP tem 65% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_slovenia_eu_tax_file_number` localiza conteúdo que corresponde ao padrão. 
    
```xml
      <!-- Slovenia Tax Identification Number -->
      <Entity id="e47b071e-c352-4d70-8241-8c215ad65505" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovenia_eu_tax_file_number" />
          <Match idRef="Keywords_slovenia_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_slovenia_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_slovenia_eu_tax_file_number"></a>Keywords_slovenia_eu_tax_file_number

- davčna številka
- identifikacijska številka davka
- številka davčne datoteke
- arquivo de imposto não
- número do arquivo de imposto
- tax id

- identificação de imposto não
- número de identificação do imposto
- n º do imposto #
- n º do imposto
- número do imposto
- número de registro de imposto
- táxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID do Tin
- Tin não
- Tin #


## <a name="south-africa-identification-number"></a>Número de identificação da África do Sul

### <a name="format"></a>Formatar

13 dígitos que podem conter espaços

### <a name="pattern"></a>Padrão

13 dígitos:
- seis dígitos no formato AAMMDD que são a data de nascimento 
- quatro dígitos 
- um indicador de cidadania de um único dígito 
- o dígito "8" ou "9" 
- um dígito que é um dígito de soma de verificação

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_south_africa_identification_number localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_south_africa_identification_number for encontrada.
- A soma de verificação passa.

```xml
<!-- South Africa Identification Number -->
<Entity id="e2adf7cb-8ea6-4048-a2ed-d89eb65f2780" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_africa_identification_number"/>
     <Match idRef="Keyword_south_africa_identification_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave
   
#### <a name="keyword_south_africa_identification_number"></a>Keyword_south_africa_identification_number

- Cartão de identidade
- ID
- Identificador 
   
## <a name="south-korea-resident-registration-number"></a>Número de registro residente da Coréia do Sul

### <a name="format"></a>Formatar

13 dígitos que contém um hifen

### <a name="pattern"></a>Padrão

13 dígitos:
- seis dígitos no formato AAMMDD que são a data de nascimento 
- um hífen 
- um dígito determinado pelo século e sexo 
- código de região de nascimento de quatro dígitos 
- um dígito usado para diferenciar pessoas para as quais os números anteriores são idênticos 
- um dígito de verificação.

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_south_korea_resident_number localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_south_korea_resident_number for encontrada.
- A soma de verificação passa.

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_south_korea_resident_number localiza o conteúdo que corresponde ao padrão.
- A soma de verificação passa.

```xml
<!-- South Korea Resident Registration Number -->
<Entity id="5b802e18-ba80-44c4-bc83-bf2ad36ae36a" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_korea_resident_number"/>
     <Match idRef="Keyword_south_korea_resident_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_south_korea_resident_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave
   
#### <a name="keyword_south_korea_resident_number"></a>Keyword_south_korea_resident_number

- Cartão de identidade nacional 
- Número de Registro do Cidadão 
- Jumin deungnok beonho 
- RRN 
- 주민등록번호

## <a name="spain-drivers-license-number"></a>Número da carteira de motorista da Espanha
Essa entidade de tipo de informação confidencial só está disponível no tipo de informações confidenciais do número de licença do driver da UE.

### <a name="format"></a>Formatar

oito dígitos seguidos de um caractere
  
### <a name="pattern"></a>Padrão

oito dígitos seguidos de um caractere:
  
- oito dígitos 
- um dígito ou letra (não diferencia maiúsculas de minúsculas)
    
### <a name="checksum"></a>Soma de verificação

Sim
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_spain_eu_driver's_license_number` localiza conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_spain_eu_driver's_license_number` foi encontrada. 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_driver's_license_number" />
          <Match idRef="Keywords_spain_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_spain_eu_drivers_license_number"></a>Keywords_spain_eu_driver ' s_license_number

- dlno #
- distribuição #
- drivers driver'lic.
- licença de driver
- driver license
- drivers licence
- drivers license
- driver's licence
- driver's license
- driving licence
- driving licence
- número de licença de driver
- número de carteira de motorista
- número de licença de drivers
- número de licença de drivers
- número de licença do driver
- número da carteira de motorista
- número da licença de dirigir
- número da licença de dirigir
- permissão de condução
- número de permissão de dirigir
- permiso de conducción
- permiso conducción
- número licencia conducir
- número de Carnet de conducir
- número Carnet conducir
- licencia conducir
- número de permiso de conducir
- número de permiso conducir
- número permiso conducir
- permiso conducir
- licencia de manejo
- El Carnet de conducir
- carnet conducir

## <a name="spain-dni"></a>Espanha DNI

### <a name="format"></a>Formatar

oito dígitos seguidos de um caractere
  
### <a name="pattern"></a>Padrão

sete dígitos seguidos de um caractere
  
- oito dígitos
- Um espaço ou hífen opcional
- uma letra de verificação (não diferencia maiúsculas de minúsculas)
    
### <a name="checksum"></a>Soma de verificação

Sim
  
### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_spain_eu_DL_and_NI_number_citizen` ou `Func_spain_eu_DL_and_NI_number_foreigner` localiza o conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_spain_eu_national_id_card"` foi encontrada. 

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_spain_eu_DL_and_NI_number_citizen` ou `Func_spain_eu_DL_and_NI_number_foreigner` localiza o conteúdo que corresponde ao padrão. 

    
```xml
      <!-- Spain DNI -->
      <Entity id="8e6251b9-47b4-40e8-a42b-0f80876be192" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
          <Match idRef="Keywords_spain_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
        </Pattern>
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_foreigner" />
          <Match idRef="Keywords_spain_eu_national_id_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_foreigner" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_spain_eu_national_id_card"></a>Keywords_spain_eu_national_id_card

- Carné de Identidad
- dni #
- dni
- dninúmero #
- documento nacional de Identidad
- identidad único
- identidadúnico #
- número de seguro
- número de identificação nacional
- identidade nacional
- nationalid #
- nationalidno #
- nie #
- nie
- nienúmero #
- número de Identificación
- número nacional identidad
- número de identificação pessoal
- identidade pessoal não
- número de identidade exclusivo
- UniqueId #

## <a name="spain-passport-number"></a>Número de passaporte da Espanha
Essa entidade de tipo de informação confidencial só está disponível no tipo de informação confidencial do número do Passport da UE.

### <a name="format"></a>Formatar

uma combinação de letras e números de oito ou nove caracteres sem espaços ou delimitadores
  
### <a name="pattern"></a>Padrão

uma combinação de letras e números de oito ou nove caracteres:
  
- dois dígitos ou letras 
- um dígito ou letra (opcional)
- seis dígitos
    
### <a name="checksum"></a>Soma de verificação

Não aplicável
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_spain_eu_passport_number` localiza o conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_spain_eu_passport_number` foi encontrada. 
    
```xml
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_spain_eu_passport_number"></a>Keywords_spain_eu_passport_number

- Passaport
- o Passport da Espanha
- Catálogo do Passport
- passport number
- Passport não
- libreta pasaporte
- número pasaporte
- españa pasaporte
- pasaporte


## <a name="spain-social-security-number-ssn"></a>Número da segurança social da Espanha (SSN)
Essa entidade de tipo de informação confidencial está incluída no número de segurança social da UE ou tipo de informação confidencial de ID equivalente e está disponível como uma entidade de tipo de informação confidencial autônoma.

### <a name="format"></a>Formatar

11 a 12 dígitos

### <a name="pattern"></a>Padrão

11-12 dígitos:
- dois dígitos 
- uma barra (opcional) 
- sete a oito dígitos 
- uma barra (opcional) 
- dois dígitos

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_spanish_social_security_number localiza conteúdo que corresponde ao padrão.
- A soma de verificação passa.

```xml
<!-- Spain SSN -->
<Entity id="5df987c0-8eae-4bce-ace7-b316347f3070" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_spanish_social_security_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

Nenhum

## <a name="spain-tax-identification-number"></a>Número de identificação de imposto da Espanha

### <a name="format"></a>Formatar

sete ou oito dígitos e uma ou duas letras no padrão especificado
  
### <a name="pattern"></a>Padrão

Pessoas naturais do espanhol com um cartão de identidade nacional da Espanha:
  
- oito dígitos 
- uma letra maiúscula (diferencia maiúsculas de minúsculas) 
    
Spaniards não residente sem um cartão de identidade nacional da Espanha
  
- uma letra maiúscula "L" (diferencia maiúsculas de minúsculas)
- sete dígitos
- uma letra maiúscula (diferencia maiúsculas de minúsculas) 
    
Spaniards residentes sob a idade de 14 anos sem um cartão de identidade nacional da Espanha:
  
- uma letra maiúscula "K" (diferencia maiúsculas de minúsculas)
- sete dígitos 
- uma letra maiúscula (diferencia maiúsculas de minúsculas)
    
Foreigners com o número de identificação do estrangeiro
  
- uma letra maiúscula que é "X", "Y" ou "Z" (diferencia maiúsculas de minúsculas) 
- sete dígitos
- uma letra maiúscula (diferencia maiúsculas de minúsculas) 
    
Foreigners sem um número de identificação do estrangeiro
  
- uma letra maiúscula que é "M" (diferencia maiúsculas de minúsculas) 
- sete dígitos
- uma letra maiúscula (diferencia maiúsculas de minúsculas) 
    
### <a name="checksum"></a>Soma de verificação

Sim
  
### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_spain_eu_tax_file_number` ou `Func_spain_eu_DL_and_NI_number_citizen` localiza o conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_spain_eu_tax_file_number` foi encontrada. 
    
Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_spain_eu_tax_file_number` ou `Func_spain_eu_DL_and_NI_number_citizen` localiza o conteúdo que corresponde ao padrão. 
    
```xml
      <!-- Spain Tax Identification Number -->
      <Entity id="10f0d113-b0e1-47dc-872a-a4f45b9376a3" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
          <Match idRef="Keywords_spain_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
          <Match idRef="Keywords_spain_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_spain_eu_tax_file_number"></a>Keywords_spain_eu_tax_file_number

- CIF
- cifid #
- cifnúmero #
- número de contribuyente
- número de Identificación fiscal
- número de impuesto corporativo
- spanishcifid #
- spanishcifid
- spanishcifno #
- spanishcifno
- arquivo de imposto não
- número do arquivo de imposto
- tax id

- identificação de imposto não
- número de identificação do imposto
- n º do imposto #
- n º do imposto
- número do imposto
- número de registro de imposto
- táxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID do Tin
- Tin não
- Tin #


## <a name="sql-server-connection-string"></a>Cadeia de caracteres de conexão do SQL Server

### <a name="format"></a>Formatar

A cadeia de caracteres "User ID", "User ID", "UID" ou "UserId" seguida dos caracteres e cadeias de caracteres descritos no padrão abaixo.

### <a name="pattern"></a>Padrão

- a cadeia de caracteres "User ID", "User ID", "UID" ou "UserId"
- qualquer combinação entre 1-200 letras minúsculas ou maiúsculas, dígitos, símbolos, caracteres especiais ou espaços
- a cadeia de caracteres "password" ou "pwd", onde "pwd" não é precedida por uma letra minúscula
- um sinal de igual (=)
- qualquer caractere que não seja um cifrão ($), símbolo de porcentagem (%), maior que símbolo (>), no símbolo (@), aspas ("), ponto e vírgula (;), chave esquerda ([) ou colchete esquerdo ({)
- qualquer combinação de 7-128 caracteres que não seja um ponto-e-vírgula (;), barra (/) ou aspas (")
- um ponto e vírgula (;) ou aspas (")

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular CEP_Regex_SQLServerConnectionString localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de CEP_GlobalFilter **não** é encontrada.
- A expressão regular CEP_PasswordPlaceHolder não **localiza o** conteúdo que corresponde ao padrão.
- A expressão regular CEP_CommonExampleKeywords não **localiza o** conteúdo que corresponde ao padrão.

```sql
<!---SQL Server Connection String>
<Entity id="e76b6205-d3cb-46f2-bd63-c90153f2f97d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_SQLServerConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_GlobalFilter" />
            <Match idRef="CEP_PasswordPlaceHolder" />
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="cep_globalfilter"></a>CEP_GlobalFilter

- algumas-senha
- somepassword
- secretPassword
- ISV

#### <a name="cep_passwordplaceholder"></a>CEP_PasswordPlaceHolder

(Observe que tecnicamente, esse tipo de informação confidencial identifica essas palavras-chave usando uma expressão regular, não uma lista de palavras-chave.)

- Senha ou pwd seguidos por 0-2 espaços, um sinal de igual (=), 0-2 espaços e um asterisco (*)--ou--
- Senha ou pwd seguido por:
    - Sinal de igual (=)
    - Sinal de menor que (<)
    - Qualquer combinação de 1-200 caracteres que sejam letras maiúsculas ou minúsculas, dígitos, um asterisco (*), hífen (-), sublinhado (_) ou caractere de espaço em branco
    - Símbolo maior que (>)

#### <a name="cep_commonexamplekeywords"></a>CEP_CommonExampleKeywords

(Observe que tecnicamente, esse tipo de informação confidencial identifica essas palavras-chave usando uma expressão regular, não uma lista de palavras-chave.)

- contoso
- fabrikam
- Northwind
- área restrita
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->suplementos
- s-int.<!--no-hyperlink-->Netlogon

## <a name="sweden-drivers-license-number"></a>Número da carteira de motorista do Suécia
Essa entidade de tipo de informação confidencial só está disponível no tipo de informações confidenciais do número de licença do driver da UE.

### <a name="format"></a>Formatar

dez dígitos contendo um hífen
  
### <a name="pattern"></a>Padrão

dez dígitos contendo um hífen:
  
- seis dígitos 
- um hífen
- quatro dígitos
    
### <a name="checksum"></a>Soma de verificação

Não
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_sweden_eu_driver's_license_number` localiza o conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_sweden_eu_driver's_license_number` foi encontrada. 
    
```xml
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Match idRef="Keywords_sweden_eu_driver's_license_number" />
        </Pattern>
</Entity> 
```

### <a name="keywords"></a>Palavras-chave

**Keywords_sweden_eu_driver ' s_license_number**

- distribuição #
- driver license
- número de carteira de motorista
- licença de driver
- drivers driver'lic.
- drivers license
- drivers licence
- driver's license
- número da carteira de motorista
- número de licença do driver
- número da licença de dirigir
- dlno #
- körkort

## <a name="sweden-national-id"></a>ID nacional da Suécia

### <a name="format"></a>Formatar

10 ou 12 dígitos e um delimitador opcional

### <a name="pattern"></a>Padrão

10 ou 12 dígitos e um delimitador opcional:
- dois dígitos (opcional) 
- Seis dígitos no formato de data AAMMDD 
- delimitador de "-" ou "+" (opcional)
- quatro dígitos

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função `Func_swedish_national_identifier` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de `Keywords_swedish_national_identifier` foi encontrada
- A soma de verificação passa.

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função `Func_swedish_national_identifier` localiza conteúdo que corresponde ao padrão.
- A soma de verificação passa.


```xml
    <!-- Sweden National ID -->
    <Entity id="f69aaf40-79be-4fac-8f05-fd1910d272c8" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_swedish_national_identifier" />
        <Match idRef="Keywords_swedish_national_identifier" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_swedish_national_identifier" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_swedish_national_identifier"></a>Keywords_swedish_national_identifier

- ID não
- número de identificação
- ID #
- identificação não
- identification number

- identifikationsnumret #
- identifikationsnumret
- identitetshandling
- documento de identidade
- identidade não
- número de identidade
- ID-Nummer
- ID pessoal
- personnummer #
- personnummer
- skatteidentifikationsnummer
   
## <a name="sweden-passport-number"></a>Número de passaporte da Suécia
Essa entidade de tipo de informação confidencial está incluída no tipo de informação confidencial do número do Passport da UE e está disponível como uma entidade de tipo de informação confidencial autônoma.

### <a name="format"></a>Formatar

oito dígitos

### <a name="pattern"></a>Padrão

oito dígitos consecutivos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- a expressão regular Regex_sweden_passport_number localiza o conteúdo que corresponde ao padrão.
- uma das seguintes opções é verdadeira:
    - uma palavra-chave de Keyword_passport for encontrada.
    - uma palavra-chave de Keyword_sweden_passport for encontrada.

```xml
<!-- Sweden Passport Number -->
<Entity id="ba4e7456-55a9-4d89-9140-c33673553526" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_sweden_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_passport" />
          <Match idRef="Keyword_sweden_passport" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave
   
#### <a name="keyword_sweden_passport"></a>Keyword_sweden_passport

- visa requirements 
- Alien Registration Card 
- Schengen visas 
- Schengen visa 
- Visa Processing 
- Visa Type 
- Single Entry 
- Multiple Entry 
- G3 Processing Fees 

#### <a name="keyword_passport"></a>Keyword_passport

- Passport Number 
- Passport No 
- Passport # 
- Passaport # 
- Passportid 
- Passportno 
- passportnumber 
- パスポート 
- パスポート番号 
- パスポートのNum 
- パスポート＃ 
- Numéro de passeport 
- Passeport n ° 
- Passeport Non 
- Passeport # 
- Passeport # 
- PasseportNon 
- Passeportn ° 

## <a name="sweden-social-security-number-or-equivalent-identification"></a>Número da segurança social da Suécia ou identificação equivalente
Essa entidade de tipo de informação confidencial só está disponível no número de seguridade social da UE ou no tipo de informações confidenciais de ID equivalente.

### <a name="format"></a>Formatar

12 dígitos sem espaços e delimitadores
  
### <a name="pattern"></a>Padrão

12 dígitos:
  
- oito dígitos que correspondem à data de nascimento (AAAAMMDD) 
- três dígitos que correspondem a um número de série em que: 
  - o último dígito no número de série indica sexo pela atribuição de um número ímpar para macho e um número par para o fêmea
  - até 1990, a atribuição de número de série correspondente à região onde o portador do número nasceu ou (se nasceu antes de 1947) em que ele/ela estava em vida, de acordo com os registros de impostos, em 1º de janeiro de 1947, com um código especial (geralmente 9 como o sétimo dígito) para immigrants 
- um dígito de verificação
    
### <a name="checksum"></a>Soma de verificação

Sim
  
### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_sweden_eu_ssn_or_equivalent` localiza conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_sweden_eu_ssn_or_equivalent` foi encontrada. 
    
Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_sweden_eu_ssn_or_equivalent` localiza conteúdo que corresponde ao padrão. 
    
```xml
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

- número de identificação pessoal
- identification number
- n º de identificação pessoal
- identidade não
- identificação não
- identificação pessoal não
- ID personnummer
- ID Personligt-Nummer
- ID unikt-Nummer
- personnummer
- identifikationsnumret
- personnummer #
- identifikationsnumret #

## <a name="sweden-tax-identification-number"></a>Número de identificação do imposto da Suécia

### <a name="format"></a>Formatar

dez dígitos e um símbolo no padrão especificado
  
### <a name="pattern"></a>Padrão

dez dígitos e um símbolo:
  
- seis dígitos que correspondem à data de nascimento (AAMMDD) 
- um sinal de mais ou sinal de menos
- três dígitos que tornam o número de identificação exclusivo, onde: 
  - para números emitidos antes de 1990, o sétimo e oitavo dígito identificam o Condado de nascimento ou pessoas de nasceu
  - o dígito na nona posição indica sexo por tanto ímpar para masculino ou par para fêmea
- um dígito de verificação
    
### <a name="checksum"></a>Soma de verificação

Sim
  
### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_sweden_eu_tax_file_number` localiza conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_sweden_eu_tax_file_number` foi encontrada. 
    
Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_sweden_eu_tax_file_number` localiza conteúdo que corresponde ao padrão. 
    
```xml
      <!-- Sweden Tax Identification Number -->
      <Entity id="139acba0-a5bc-4fbb-876d-f7a493ae8a40" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
          <Match idRef="Keywords_sweden_eu_tax_file_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_sweden_eu_telephone_number" />
            <Match idRef="Keywords_sweden_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_sweden_eu_tax_file_number"></a>Keywords_sweden_eu_tax_file_number

- número de identificação pessoal
- personnummer
- skatt ID Nummer
- skatt identifikation
- skattebetalarens identifikationsnummer
- Tin Sverige
- arquivo de imposto
- tax id

- identificação de imposto não
- número de identificação do imposto
- n º do imposto #
- n º do imposto
- número do imposto
- número de registro de imposto
- táxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID do Tin
- Tin não
- Tin #


## <a name="swift-code"></a>Código SWIFT

### <a name="format"></a>Formatar

quatro letras seguidas por 5-31 letras ou dígitos

### <a name="pattern"></a>Padrão

quatro letras seguidas por 5-31 letras ou dígitos:
- código bancário de quatro letras (não diferencia maiúscula de minúscula) 
- um espaço opcional 
- 4 a 28 letras ou dígitos (o número de conta bancária básica (BBAN)) 
- um espaço opcional 
- uma ou três letras ou dígitos (restante do BBAN)

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular Regex_swift localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_swift for encontrada.

```xml
<Entity id="cb2ab58c-9cb8-4c81-baf8-a4e106791df4" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_swift" />
        <Match idRef="Keyword_swift" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave
   
#### <a name="keyword_swift"></a>Keyword_swift

- international organization for standardization 9362 
- iso 9362 
- iso9362 
- Swift\# 
- swiftcode 
- swiftnumber 
- swiftroutingnumber 
- swift code 
- swift number # 
- swift routing number 
- bic number 
- bic code 
- bic \# 
- bic\# 
- bank identifier code 
- 標準化 9362 
- 迅速＃ 
- SWIFTコード 
- SWIFT番号 
- 迅速なルーティング番号 
- BIC番号 
- BICコード 
- 銀行識別コードのための国際組織 
- Organisation internationale de normalisation 9362 
- rápida \# 
- code SWIFT 
- le numéro de swift 
- swift numéro d'acheminement 
- le numéro BIC 
- \# BIC 
- code identificateur de banque 


## <a name="swiss-ssn-ahv-number"></a>Número do AHV SSN suíço

### <a name="format"></a>Formatar

número de 13 dígitos

### <a name="pattern"></a>Padrão

número de 13 dígitos:

- três dígitos-756
- um ponto opcional
- quatro dígitos
- um ponto opcional
- quatro dígitos
- um ponto opcional
- dois dígitos

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_swiss_social_security_number_ahv localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keywords_swiss_social_security_number_ahv for encontrada.

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_swiss_social_security_number_ahv localiza o conteúdo que corresponde ao padrão.

```xml
      <!-- Swiss SSN AHV Number -->
      <Entity id="277cfa4b-6eaa-4a1b-9492-099dec849971" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_swiss_social_security_number_ahv" />
          <Match idRef="Keywords_swiss_social_security_number_ahv" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_swiss_social_security_number_ahv" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_swiss_ssn_ahv_number"></a>Keyword_swiss_ssn_AHV_number

- ahv
- es
- atos
- número de seguro
- personalidno #
- social security number

- número de identificação pessoal
- n º de identificação pessoal
- insuranceno #
- uniqueidno #
- n º de identificação exclusiva
- número AVS
- identidade pessoal sem versicherungsnummer
- identifikationsnummer
- einzigartige identität nicht
- sozialversicherungsnummer
- identificação personnelle ID
- 
numéro de sécurité sociale

   
## <a name="taiwan-national-identification-number"></a>Número de identificação nacional de Taiwan

### <a name="format"></a>Formatar

uma letra (em inglês) seguida de nove dígitos

### <a name="pattern"></a>Padrão

uma letra (em inglês) seguida de nove dígitos:
- uma letra (em inglês, não diferencia maiúscula de minúscula) 
- o dígito "1" ou "2" 
- oito dígitos

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_taiwanese_national_id localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_taiwanese_national_id for encontrada.
- A soma de verificação passa.

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_taiwanese_national_id localiza conteúdo que corresponde ao padrão.
- A soma de verificação passa.

```xml
<!-- Taiwanese National ID -->
<Entity id="4C7BFC34-8DD1-421D-8FB7-6C6182C2AF03" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_taiwanese_national_id" />
          <Match idRef="Keyword_taiwanese_national_id" />
      </Pattern>
       <Pattern confidenceLevel="75">
         <IdMatch idRef="Func_taiwanese_national_id" />
       </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_taiwan_national_id"></a>Keyword_taiwan_national_id

- 身份證字號 
- 身份證 
- 身份證號碼 
- 身份證號 
- 身分證字號 
- 身分證 
- 身分證號碼 
- 身份證號 
- 身分證統一編號 
- 國民身分證統一編號 
- 簽名 
- 蓋章 
- 簽名或蓋章 
- 簽章   
   
## <a name="taiwan-passport-number"></a>Número de passaporte de Taiwan

### <a name="format"></a>Formatar

- número de passaporte biométrico: nove dígitos
- número de passaporte não biométrico: nove dígitos

### <a name="pattern"></a>Padrão
número de passaporte biométrico:
- o caractere "3" 
- oito dígitos

número de passaporte não biométrico:
- nove dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular Regex_taiwan_passport localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_taiwan_passport for encontrada.

```xml
<!-- Taiwan Passport Number -->
<Entity id="e7251cb4-4c2c-41df-963e-924eb3dae04a" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_passport"/>
     <Match idRef="Keyword_taiwan_passport"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_taiwan_passport"></a>Keyword_taiwan_passport

- Número de passaporte ROC 
- Número de passaporte 
- Nº de passaporte 
- Núm de Passaporte 
- Passport # 
- 护照 
- 中華民國護照 
- Zhōnghuá Mínguó hùzhào
   
## <a name="taiwan-resident-certificate-arctarc-number"></a>Número de certificado residente (arco/TARC) de Taiwan

### <a name="format"></a>Formatar

Dez letras e dígitos

### <a name="pattern"></a>Padrão

Dez letras e dígitos:
- duas letras (não diferencia maiúsculas de minúsculas) 
- oito dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular Regex_taiwan_resident_certificate localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_taiwan_resident_certificate for encontrada.

```xml
<!-- Taiwan Resident Certificate (ARC/TARC) -->
<Entity id="48269fec-05ea-46ea-b326-f5623a58c6e9" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_resident_certificate"/>
     <Match idRef="Keyword_taiwan_resident_certificate"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_taiwan_resident_certificate"></a>Keyword_taiwan_resident_certificate

- Certificado de Residente 
- Cert de Residente 
- Cert. de Residente
 
- Cartão de identificação 
- Certificado de Residente Alien 
- ARC 
- Certificado de Residente da Área de Taiwan 
- TARC 
- 居留證 
- 外僑居留證 
- 台灣地區居留證 

## <a name="thai-population-identification-code"></a>Código de identificação de população em tailandês

### <a name="format"></a>Formatar

13 dígitos

### <a name="pattern"></a>Padrão

13 dígitos:
- o primeiro dígito não é zero ou nove 
- 12 dígitos

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_Thai_Citizen_Id localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_Thai_Citizen_Id for encontrada.

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_Thai_Citizen_Id localiza o conteúdo que corresponde ao padrão.

```xml
<!-- Thai Citizen ID -->
-<Entity id="44ca9e86-ead7-4c5d-884a-e2eaa401515e" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="85">
      <IdMatch idRef="Func_Thai_Citizen_Id"/>
      <Match idRef="Keyword_Thai_Citizen_Id"/>
   </Pattern>
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Func_Thai_Citizen_Id"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_thai_citizen_id"></a>Keyword_thai_citizen_Id

- Número de Identificação
- Número de identificação
- บัตรประชาชน
- รหัสบัตรประชาชน
- บัตรประชาชน
- รหัสบัตรประชาชน
  
## <a name="turkish-national-identification-number"></a>Número de identificação nacional turco

### <a name="format"></a>Formatar

11 dígitos

### <a name="pattern"></a>Padrão

11 dígitos

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_Turkish_National_Id localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_Turkish_National_Id for encontrada.

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_Turkish_National_Id localiza o conteúdo que corresponde ao padrão.

```xml
<!-- Turkish National Identity -->
-<Entity id="fb621f20-3876-4cfc-acec-8c8e73ca32c7" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="85">
      <IdMatch idRef="Func_Turkish_National_Id"/>
      <Match idRef="Keyword_Turkish_National_Id"/>
   </Pattern>
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Func_Turkish_National_Id"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_turkish_national_id"></a>Keyword_turkish_national_id

- Kimlik TC não
- TC Kimlik numarası
- Vatandaşlık numarası
- Vatandaşlık não

## <a name="uk-drivers-license-number"></a>britânico número da carteira de motorista
Essa entidade de tipo de informação confidencial está incluída no tipo de informação confidencial do número de carteira do driver da UE e está disponível como uma entidade de tipo de informação confidencial autônoma.

### <a name="format"></a>Formatar

Combinação de 18 letras e dígitos no formato especificado

### <a name="pattern"></a>Padrão

18 letras e dígitos:
- cinco letras (não diferencia maiúsculas de minúsculas) ou o dígito "9" em vez de uma letra 
- um dígito 
- cinco dígitos no formato de data MMDDY para data de nascimento (o sétimo caractere é incrementado por 50 se o driver for fêmea, ou seja, 51 a 62 em vez de 01 a 12)
- duas letras (não diferencia maiúsculas de minúsculas) ou o dígito "9" em vez de uma letra 
- cinco dígitos

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_uk_drivers_license localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_uk_drivers_license for encontrada.
- A soma de verificação passa.

```xml
<!-- U.K. Driver's License Number -->
<Entity id="f93de4be-d94c-40df-a8be-461738047551" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_drivers_license" />
        <Match idRef="Keyword_uk_drivers_license" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_uk_drivers_license"></a>Keyword_uk_drivers_license

- DVLA 
- light vans 
- quadbikes 
- motor cars 
- 125cc 
- sidecar 
- tricycles 
- motorcycles 
- photocard licence 
- learner drivers 
- licence holder 
- licence holders 
- driving licences 
- driving licence 
- dual control car 
   
## <a name="uk-electoral-roll-number"></a>britânico número de rolo electoral

### <a name="format"></a>Formatar

duas letras seguidas por 1-4 dígitos

### <a name="pattern"></a>Padrão

duas letras (não diferencia maiúsculas de minúsculas) seguidas por números de 1-4

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular Regex_uk_electoral localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_uk_electoral for encontrada.

```xml
<!-- U.K. Electoral Number -->
<Entity id="a3eea206-dc0c-4f06-9e22-aa1be3059963" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_uk_electoral" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_electoral" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_uk_electoral"></a>Keyword_uk_electoral

- council nomination 
- nomination form 
- electoral register 
- electoral roll

   
## <a name="uk-national-health-service-number"></a>britânico número do serviço de integridade nacional

### <a name="format"></a>Formatar

10 a 17 dígitos separados por espaços

### <a name="pattern"></a>Padrão

10 a 17 dígitos:
- três ou dez dígitos 
- um espaço 
- três dígitos 
- um espaço 
- quatro dígitos

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_uk_nhs_number localiza conteúdo que corresponde ao padrão.
- Uma das seguintes opções for verdadeira:
    - Uma palavra-chave de Keyword_uk_nhs_number for encontrada.
    - Uma palavra-chave de Keyword_uk_nhs_number1 for encontrada.
    - Uma palavra-chave de Keyword_uk_nhs_number_dob for encontrada.
- A soma de verificação passa.

```xml
<!-- U.K. NHS Number -->
<Entity id="3192014e-2a16-44e9-aa69-4b20375c9a78" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_uk_nhs_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_nhs_number" />
          <Match idRef="Keyword_uk_nhs_number1" />
          <Match idRef="Keyword_uk_nhs_number_dob" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave
   
#### <a name="keyword_uk_nhs_number"></a>Keyword_uk_nhs_number

- national health service 
- NHS 
- health services authority 
- health authority

#### <a name="keyword_uk_nhs_number1"></a>Keyword_uk_nhs_number1

- patient id 
- patient identification 
- patient no 
- patient number

#### <a name="keyword_uk_nhs_number_dob"></a>Keyword_uk_nhs_number_dob

- GP 
- DOB 
- D. O. B 
- Date of Birth 
- Birth Date 
   
## <a name="uk-national-insurance-number-nino"></a>britânico número de seguro nacional (NINO)
Essa entidade de tipo de informação confidencial está incluída no tipo de informação confidencial do número Identificaiton nacional da UE e está disponível como uma entidade de tipo de informação confidencial autônoma.

### <a name="format"></a>Formatar

sete caracteres ou nove caracteres separados por espaços ou traços

### <a name="pattern"></a>Padrão

dois padrões possíveis:

- duas letras (NINOs válidas usam apenas determinados caracteres neste prefixo, que esse padrão valida; não diferencia maiúsculas de minúsculas)
- seis dígitos
- "A", "B", "C" ou "(como o prefixo, apenas determinados caracteres são permitidos no sufixo; não diferencia maiúsculas de minúsculas)

OU

- duas letras
- um espaço ou um traço
- dois dígitos
- um espaço ou um traço
- dois dígitos
- um espaço ou um traço
- dois dígitos
- um espaço ou um traço
- ' A ', ' B ', ' C' ou ' d'

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_uk_nino localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_uk_nino for encontrada.

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_uk_nino localiza conteúdo que corresponde ao padrão.
- Nenhuma palavra-chave de Keyword_uk_nino for encontrada.

```xml
<!-- U.K. NINO -->
<Entity id="16c07343-c26f-49d2-a987-3daf717e94cc" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_uk_nino" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_nino" />
        </Any>
    </Pattern>    
     <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_nino" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_uk_nino" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_uk_nino"></a>Keyword_uk_nino

- national insurance number

- national insurance contributions

- protection act
- seguro
- social security number

- insurance application

- medical application

- social insurance

- medical attention

- segurança social
- great britain

- Número de NI
- N º de NI
- NI #
- NI #
- seguro #
- insurancenumber
- nationalinsurance #
- nationalinsurancenumber

    
## <a name="uk-unique-taxpayer-reference-number"></a>britânico Número de referência de contribuidor exclusivo

### <a name="format"></a>Formatar

10 dígitos sem espaços e delimitadores
 
  
### <a name="pattern"></a>Padrão

10 dígitos
  
### <a name="checksum"></a>Soma de verificação

Não
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_uk_eu_tax_file_number` localiza conteúdo que corresponde ao padrão. 
- Uma palavra-chave de  `Keywords_uk_eu_tax_file_number` foi encontrada. 
    
```xml
      <!-- U.K. Unique Taxpayer Reference Number -->
      <Entity id="ad4a8116-0db8-439a-b545-6d967642f0ec" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_uk_eu_tax_file_number" />
          <Match idRef="Keywords_uk_eu_tax_file_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_uk_eu_tax_file_number"></a>Keywords_uk_eu_tax_file_number

- número do imposto
- arquivo de imposto
- tax id

- identificação de imposto não
- número de identificação do imposto
- n º do imposto #
- n º do imposto
- número de registro de imposto
- táxi #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- ID do Tin
- Tin não
- Tin #

## <a name="us-bank-account-number"></a>Número de conta bancária dos EUA

### <a name="format"></a>Formatar

8 a 17 dígitos

### <a name="pattern"></a>Padrão

8 a 17 dígitos consecutivos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A expressão regular Regex_usa_bank_account_number localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_usa_Bank_Account for encontrada.

```xml
<!-- U.S. Bank Account Number -->
<Entity id="a2ce32a8-f935-4bb6-8e96-2a5157672e2c" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_usa_bank_account_number" />
        <Match idRef="Keyword_usa_Bank_Account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_usa_bank_account"></a>Keyword_usa_Bank_Account

- Checking Account Number 
- Checking Account 
- Checking Account # 
- Checking Acct Number 
- Checking Acct # 
- Checking Acct No. 
- Checking Account No. 
- Bank Account Number 
- Bank Account # 
- Bank Acct Number 
- Bank Acct # 
- Bank Acct No. 
- Bank Account No. 
- Savings Account Number 
- Savings Account. 
- Savings Account # 
- Savings Acct Number 
- Savings Acct # 
- Savings Acct No. 
- Savings Account No. 
- Debit Account Number 
- Debit Account 
- Debit Account # 
- Debit Acct Number 
- Debit Acct # 
- Debit Acct No. 
- Debit Account No. 

## <a name="us-drivers-license-number"></a>Número da carteira de motorista dos EUA

### <a name="format"></a>Formatar

Depende do estado

### <a name="pattern"></a>Padrão

depende do estado – por exemplo, Nova York:
- nove dígitos formatados como DDD DDD DDD corresponderão.
- nove dígitos como ddddddddd não serão correspondentes.

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_new_york_drivers_license_number localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_[state_name]_drivers_license_name for encontrada.
- Uma palavra-chave de Keyword_us_drivers_license for encontrada.

Uma política de DLP tem 65% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_new_york_drivers_license_number localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_[state_name]_drivers_license_name for encontrada.
- Uma palavra-chave de Keyword_us_drivers_license_abbreviations for encontrada.
- Nenhuma palavra-chave de Keyword_us_drivers_license for encontrada.

```xml
<Entity id="dfeb356f-61cd-459e-bf0f-7c6d28b458c6 patternsProximity="300">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_new_york_drivers_license_number" />
        <Match idRef="Keyword_new_york_drivers_license_name" />
        <Match idRef="Keyword_us_drivers_license" />
    </Pattern>
    <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_new_york_drivers_license_number" />
        <Match idRef="Keyword_new_york_drivers_license_name" />
        <Match idRef="Keyword_us_drivers_license_abbreviations" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_us_drivers_license" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_us_drivers_license_abbreviations"></a>Keyword_us_drivers_license_abbreviations

- DISTRIBUIÇÃO 
- DL 
- CDL 
- CDLS 
- ID 
- Código 
- DISTRIBUIÇÃO # 
- DL # 
- CDL # 
- CDLS # 
- ID #
- Código # 
- ID number 
- ID numbers 
- DRIVER'LIC 
- DRIVER'LIC # 

#### <a name="keyword_us_drivers_license"></a>Keyword_us_drivers_license

- DriverLic 
- DriverLics 
- DriverLicense 
- DriverLicenses 
- Driver Lic 
- Driver Lics 
- Driver License 
- Driver Licenses 
- DriversLic 
- DriversLics 
- DriversLicense 
- DriversLicenses 
- Drivers Lic 
- Drivers Lics 
- Drivers License 
- Drivers Licenses 
- Driver'Lic 
- Driver'Lics 
- Driver'License 
- Driver'Licenses 
- Driver' Lic 
- Driver' Lics 
- Driver' License 
- Driver' Licenses
- Driver'sLic 
- Driver'sLics 
- Driver'sLicense 
- Driver'sLicenses 
- Driver's Lic 
- Driver's Lics 
- Driver's License 
- Driver's Licenses 
- identification number 
- identification numbers 
- identification # 
- id card 
- id cards 
- identification card 
- identification cards 
- DriverLic # 
- DriverLics # 
- DriverLicense # 
- DriverLicenses # 
- Driver Lic# 
- Driver Lics# 
- Driver License# 
- Driver Licenses# 
- DriversLic # 
- DriversLics # 
- DriversLicense # 
- DriversLicenses # 
- Drivers Lic# 
- Drivers Lics# 
- Drivers License# 
- Drivers Licenses# 
- Driver'Lic # 
- Driver'Lics # 
- Driver'License # 
- Driver'Licenses # 
- Driver' Lic# 
- Driver' Lics# 
- Driver' License# 
- Driver' Licenses# 
- Driver'sLic # 
- Driver'sLics # 
- Driver'sLicense # 
- Driver'sLicenses # 
- Driver's Lic# 
- Driver's Lics# 
- Driver's License# 
- Driver's Licenses# 
- id card# 
- id cards# 
- identification card# 
- identification cards# 


#### <a name="keyword_state_name_drivers_license_name"></a>Keyword_ [state_name] _drivers_license_name

- abreviatura de estado (por exemplo, "NY") 
- nome do estado (por exemplo, "Nova York")

## <a name="us-individual-taxpayer-identification-number-itin"></a>Número de identificação de contribuinte individual (ITIN)

### <a name="format"></a>Formatar

nove dígitos que começam com um "9" e contêm um "7" ou "8" como o quarto dígito, opcionalmente formatado com espaços ou traços

### <a name="pattern"></a>Padrão

binário
- o dígito "9" 
- dois dígitos 
- um espaço ou um traço 
- um "7" ou "8" 
- um dígito 
- um espaço ou um traço 
- quatro dígitos

não formatado
- o dígito "9" 
- dois dígitos 
- um "7" ou "8" 
- cinco dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_formatted_itin localiza conteúdo que corresponde ao padrão.
- Pelo menos uma das seguintes opções for verdadeira:
    - Uma palavra-chave de Keyword_itin for encontrada.
    - A função Func_us_address encontrar um endereço no formato de data à direita.
    - A função Func_us_date encontra uma data no formato de data à direita.
    - Uma palavra-chave de Keyword_itin_collaborative for encontrada.

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_unformatted_itin localiza conteúdo que corresponde ao padrão.
- Pelo menos uma das seguintes opções for verdadeira:
    - Uma palavra-chave de Keyword_itin_collaborative for encontrada.
    - A função Func_us_address encontrar um endereço no formato de data à direita.
    - A função Func_us_date encontra uma data no formato de data à direita.

```xml
<!-- U.S. Individual Taxpayer Identification Number (ITIN) -->
<Entity id="e55e2a32-f92d-4985-a35d-a0b269eb687b" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_formatted_itin" />
        <Any minMatches="1">
          <Match idRef="Keyword_itin" />
          <Match idRef="Func_us_address" />
          <Match idRef="Func_us_date" />
          <Match idRef="Keyword_itin_collaborative" />
        </Any>
    </Pattern>
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_itin" />
        <Match idRef="Keyword_itin" />
        <Any minMatches="1">
          <Match idRef="Keyword_itin_collaborative" />
          <Match idRef="Func_us_address" />
          <Match idRef="Func_us_date" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_itin"></a>Keyword_itin

- contribui 
- tax id 
- tax identification 
- itin 
- es 
- Tin 
- social security 
- tax payer 
- itins 
- táxi 
- individual taxpayer 

#### <a name="keyword_itin_collaborative"></a>Keyword_itin_collaborative

- Licença 
- DISTRIBUIÇÃO 
- DOB 
- Data de Nascimento 
- Birthday 
- Date of Birth 

## <a name="us-social-security-number-ssn"></a>Número de CPF (cadastro social dos EUA)

### <a name="format"></a>Formatar

nove dígitos, que podem estar em um padrão formatado ou não formatado

> [!NOTE]
> Se emitido antes de meados de 2011, um SSN tem uma formatação forte, onde determinadas partes do número devem estar dentro de determinados intervalos para serem válidos (mas não há nenhum checksum).

### <a name="pattern"></a>Padrão

quatro funções procuram CPFs em quatro padrões diferentes:
- Func_ssn localiza CPFs com formatação forte de 2011 formatada com traços ou espaços (DDD-DD-dddd ou DDD DD dddd)
- Func_unformatted_ssn localiza CPFs com uma formatação forte anterior à 2011 que não são formatadas como nove dígitos consecutivos (ddddddddd)
- Func_randomized_formatted_ssn localiza CPFs post-2011 que são formatados com traços ou espaços (DDD-DD-dddd ou DDD DD dddd)
- Func_randomized_unformatted_ssn localiza CPFs post-2011 que não estão formatados como nove dígitos consecutivos (ddddddddd)

### <a name="checksum"></a>Soma de verificação

Não


### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_ssn localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_ssn for encontrada.

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_unformatted_ssn localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_ssn for encontrada.

Uma política de DLP tem 65% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_randomized_formatted_ssn localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_ssn for encontrada.

Uma política de DLP tem 55% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_randomized_unformatted_ssn localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_ssn for encontrada.


```xml
<!-- U.S. Social Security Number (SSN) -->
  <Entity id="a44669fe-0d48-453d-a9b1-2cc83f2cba77" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_randomized_formatted_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
      <Pattern confidenceLevel="55">
        <IdMatch idRef="Func_randomized_unformatted_ssn" />
        <Match idRef="Keyword_ssn" />
      </Pattern>
  </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_ssn"></a>Keyword_ssn

- Número do SSA
- social security number
- segurança social #
- segurança social #
- segurança social não
- Social Security#
- Soc Sec
- ES
- CPFs
- ES #
- PLANILHA #
- SSID
   
## <a name="us--uk-passport-number"></a>EUA/REINO UNIDO passport number
O Reino Unido a entidade de tipo de informação confidencial do número do Passport está disponível no tipo de informação confidencial do número do Passport da UE e está disponível como uma entidade de tipo de informação confidencial autônoma.

### <a name="format"></a>Formatar

nove dígitos

### <a name="pattern"></a>Padrão

nove dígitos consecutivos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A função Func_usa_uk_passport localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_passport for encontrada.

```xml
<Entity id="178ec42a-18b4-47cc-85c7-d62c92fd67f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_usa_uk_passport" />
        <Match idRef="Keyword_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_passport"></a>Keyword_passport

- Passport Number 
- Passport No 
- Passport # 
- Passaport # 
- Passportid 
- Passportno 
- passportnumber 
- パスポート 
- パスポート番号 
- パスポートのNum 
- パスポート＃ 
- Numéro de passeport 
- Passeport n ° 
- Passeport Non 
- Passeport # 
- Passeport # 
- PasseportNon 
- Passeportn ° 

## <a name="ukraine-passport-domestic"></a>Ucrânia Passport doméstico

### <a name="format"></a>Formatar

nove dígitos

### <a name="pattern"></a>Padrão

nove dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A Regex_Ukraine_Passport_Domestic Regex localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_Ukraine_Passport_Domestic for encontrada.

```xml
      <!-- Ukraine Passport Domestic -->
      <Entity id="1817a540-221f-4459-9202-3bd78b81d803" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_Ukraine_Passport_Domestic"/>
          <Match idRef="Keyword_Ukraine_Passport_Domestic"/>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_ukraine_passport_domestic"></a>Keyword_ukraine_passport_domestic

- passaporte da Ucrânia
- número de passaporte
- Passport não
- паспорт України
- номер паспорта
- персональний


## <a name="ukraine-passport-international"></a>Ucrânia Passport internacional

### <a name="format"></a>Formatar

padrão alfanumérico de oito caracteres

### <a name="pattern"></a>Padrão

padrão alfanumérico de oito caracteres:
- duas letras ou dígitos
- seis dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
- A Regex_Ukraine_Passport_International Regex localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_Ukraine_Passport_International for encontrada.

```xml
      <!-- Ukraine Passport International -->
      <Entity id="cfbe032d-22e0-4f28-ab68-d66e9641f1e2" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_Ukraine_Passport_International"/>
          <Match idRef="Keyword_Ukraine_Passport_International"/>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_ukraine_passport_international"></a>Keyword_ukraine_passport_international

- passaporte da Ucrânia
- número de passaporte
- Passport não
- паспорт України
- номер паспорта
