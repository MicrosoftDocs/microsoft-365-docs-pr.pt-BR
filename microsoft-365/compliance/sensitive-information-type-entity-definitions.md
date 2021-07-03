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
recommendations: false
description: Há 200 tipos de informações confidenciais que estão prontos para você usar em suas políticas de DLP. Este artigo lista todos esses tipos de informações confidenciais e mostra o que uma política de DLP procura quando detecta cada tipo.
ms.openlocfilehash: 614649367e72766d8df210fccbb4e3cdc9cdb4b6
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287462"
---
# <a name="sensitive-information-type-entity-definitions"></a>Definições da entidade de tipo de informações confidenciais 

Este artigo lista todas as definições de entidade de tipo de informação confidenciais. Cada definição mostra o que uma política de DLP procura para detectar cada tipo. Para saber mais sobre tipos de informações confidenciais, consulte [Tipos de informações confidenciais](sensitive-information-type-learn-about.md)

## <a name="aba-routing-number"></a>Número de roteamento ABA

### <a name="format"></a>Formatar

nove dígitos que podem estar em um padrão formatado ou não formatado

### <a name="pattern"></a>Padrão

- dois dígitos nos intervalos 00-12, 21-32, 61-72 ou 80
- dois dígitos
- um hífen opcional
- quatro dígitos
- um hífen opcional
- um dígito


### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_aba_routing localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_ABA_Routing for encontrada.

Uma política de DLP tem baixa confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_aba_routing localiza conteúdo que corresponde ao padrão.

```xml
    <!-- ABA Routing Number -->
    <Entity id="cb353f78-2b72-4c3c-8827-92ebe4f69fdf" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_aba_routing" />
        <Match idRef="Keyword_ABA_Routing" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_aba_routing" />
      </Pattern>
    </Entity>
```


### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_aba_routing"></a>Keyword_aba_routing

- aba number
- aba #
- aba
- abarouting #
- abaroutingnumber
- americanbankassociationrouting #
- americanbankassociationroutingnumber
- bankrouting #
- bankroutingnumber
- routing #
- roteamento não
- número de roteamento
- routing transit number
- routing #
- RTN


## <a name="argentina-national-identity-dni-number"></a>Número DNI (identidade nacional da Argentina)

### <a name="format"></a>Formatar

Oito dígitos com ou sem períodos

### <a name="pattern"></a>Padrão

Oito dígitos:
- dois dígitos
- um período opcional
- três dígitos
- um período opcional
- três dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular Regex_argentina_national_id encontra conteúdo que corresponde ao padrão.
- Uma palavra-chave Keyword_argentina_national_id é encontrada.

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
- cedula
- cédula
- dni
- documento nacional de identidad
- documento número
- documento numero
- registro nacional de las personas
- rnp

## <a name="argentina-unique-tax-identification-key-cuitcuil"></a>Chave de Identificação Fiscal Exclusiva da Argentina (CUIT/CUIL)

### <a name="format"></a>Formatar

11 dígitos com traço

### <a name="pattern"></a>Padrão

11 dígitos com um traço:
- dois dígitos em 20, 23, 24, 27, 30, 33 ou 34
- um hífen (-)
- oito dígitos
- um hífen (-)
- um dígito de verificação

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função `Func_Argentina_Unique_Tax_Key` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de `Keyword_Argentina_Unique_Tax_Key` é encontrada.

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função `Func_Argentina_Unique_Tax_Key` localiza conteúdo que corresponde ao padrão.

```xml
    <!-- Argentina Unique Tax Identification Key (CUIT/CUIL) -->
      <Entity id="98da3da1-9199-4571-b7c4-b6522980b507" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_Argentina_Unique_Tax_Key" />
          <Match idRef="Keyword_Argentina_Unique_Tax_Key" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_Argentina_Unique_Tax_Key" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_argentina_unique_tax_key"></a>Keyword_Argentina_Unique_Tax_Key

- Clave Unica de Identificacion Tributaria
- CUIT
- código exclusivo de identificação de mão-de-obra 
- Clave Única de Identificación Tributaria
- código de identificação de trabalho exclusivo
- CUIL
- Chave de Identificação Fiscal Exclusiva
- Chave de Identificação de Trabalho Exclusiva
- Chave exclusiva da identificação de mão de obra
- Código de Identificação de Trabalho Exclusivo
- Identificação exclusiva do Código de Trabalho
- Chave de Identificação de Trabalho Exclusiva
- Chave exclusiva da identificação do trabalho
- Código exclusivo de identificação fiscal
- Chave exclusiva de identificação fiscal
- Código de Identificação de Trabalho Exclusivo
- Identificação exclusiva do Código de Trabalho
- Chave de Identificação de Trabalho Exclusiva
- Chave exclusiva de identificação do trabalho
- ID de imposto
- taxID #
- taxId
- taxidnumber
- número de imposto
- tax no
- tax #
- tax #
- ID do contribuinte
- número do contribuinte
- contribuinte não
- taxpayer #
- taxpayer #
- identidade fiscal
- tax identification
- Número de Identificación Fiscal
- número de contribuyente


## <a name="australia-bank-account-number"></a>Número da conta bancária da Austrália

### <a name="format"></a>Formatar

seis a 10 dígitos com ou sem um número de filial de estado do banco

### <a name="pattern"></a>Padrão

O número da conta é de 6 a 10 dígitos.

Número BSB da Austrália:
- três dígitos
- um hífen
- três dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular Regex_australia_bank_account_number encontra conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_australia_bank_account_number for encontrada.
- A expressão regular Regex_australia_bank_account_number_bsb localiza o conteúdo que corresponde ao padrão.

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular Regex_australia_bank_account_number encontra conteúdo que corresponde ao padrão.

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

## <a name="australia-business-number"></a>Número comercial da Austrália
Esse tipo de informação confidenciais só está disponível para uso em:
- políticas de prevenção contra perda de dados
- políticas de conformidade de comunicação
- governança de informações
- gerenciamento de registros
- Segurança do aplicativo na nuvem da Microsoft


### <a name="format"></a>Formatar

11 dígitos com delimitadores opcionais

### <a name="pattern"></a>Padrão

11 dígitos com delimitadores opcionais:

- dois dígitos
- um hífen opcional ou espaço
- três dígitos
- um hífen opcional ou espaço
- três dígitos
- um hífen opcional ou espaço
- três dígitos

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_australian_business_number encontra conteúdo que corresponde ao padrão.
- Uma palavra-chave Keywords_australian_business_number é encontrada.

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_australian_business_number encontra conteúdo que corresponde ao padrão.

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

- australia business no
- número de negócios
- abn #
- businessid #
- id de negócios
- abn
- businessno #

## <a name="australia-company-number"></a>Número da empresa austrália
Esse tipo de informação confidenciais só está disponível para uso em:
- políticas de prevenção contra perda de dados
- políticas de conformidade de comunicação
- governança de informações
- gerenciamento de registros
- Segurança do aplicativo na nuvem da Microsoft

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

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_Australian_Company_Number encontra conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_Australian_Company_Number é encontrada.

Uma política de DLP tem baixa confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_Australian_Company_Number encontra conteúdo que corresponde ao padrão.

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

- pode
- austrália empresa não
- austrália empresa não #
- número da empresa austrália
- australian company no
- australian company no #
- número da empresa australiana

## <a name="australia-drivers-license-number"></a>Número da carteira de motorista da Austrália

### <a name="format"></a>Formatar

nove letras e dígitos

### <a name="pattern"></a>Padrão

nove letras e dígitos:

- dois dígitos ou letras (não sensíveis a maiúsculas e minúsculas)
- dois dígitos
- cinco dígitos ou letras (não sensíveis a maiúsculas e minúsculas)

OU

- uma a duas letras opcionais (não sensíveis a maiúsculas e minúsculas)
- de quatro a nove dígitos

OU

- nove dígitos ou letras (não sensíveis a maiúsculas e minúsculas)

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
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

- aaa
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
- Primeiro dígito está no intervalo de 2 a 6
- O nono dígito é um dígito de verificação
- O décimo dígito é o dígito do problema
- O décimo primeiro dígito (opcional) é o número individual

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
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
- 2016


## <a name="australia-passport-number"></a>Número do passaporte da Austrália

### <a name="format"></a>Formatar

oito ou nove caracteres alfanuméricos

### <a name="pattern"></a>Padrão

- uma letra (N, E, D, F, A, C, U, X) seguida por sete dígitos ou
- Duas letras (PA, PB, PC, PD, PE, PF, PU, PW, PX, PZ) seguidas por sete dígitos.

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular `Regex_australia_passport_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de `Keyword_australia_passport_number` é encontrada.

Uma política de DLP tem baixa confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular `Regex_australia_passport_number` localiza conteúdo que corresponde ao padrão.

```xml
    <!-- Australia Passport Number -->
    <Entity id="29869db6-602d-4853-ab93-3484f905df50" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_passport_number" />
        <Match idRef="Keyword_australia_passport_number" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_australia_passport_number" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_australia_passport_number"></a>Keyword_australia_passport_number

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- números do passport
- passport details
- immigration and citizenship
- commonwealth of australia
- department of immigration
- national identity card
- travel document
- issuing authority


## <a name="australia-tax-file-number"></a>Número do arquivo fiscal da Austrália

### <a name="format"></a>Formatar

oito a nove dígitos

### <a name="pattern"></a>Padrão

oito a nove dígitos normalmente apresentados com espaços da seguinte maneira:
- três dígitos
- um espaço opcional
- três dígitos
- um espaço opcional
- dois a três dígitos onde o último dígito é um dígito de verificação

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
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

## <a name="austria-drivers-license-number"></a>Número da carteira de motorista da Áustria

### <a name="format"></a>Formatar

oito dígitos sem espaços e delimitadores

### <a name="pattern"></a>Padrão

oito dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:

- A expressão regular  `Regex_austria_eu_driver's_license_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave  `Keywords_eu_driver's_license_number` de ou `Keywords_austria_eu_driver's_license_number` é encontrada.

```xml
      <!-- Austria Driver's License Number -->
      <Entity id="682f18ce-44eb-482b-8198-2bcb96a0761e" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_austria_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver'lic
- lics do driver
- driver'license
- driver'licenses
- driver'licence
- driver 'licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- lic do driver
- lics do driver
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver'lic #
- lics do driver #
- driver'license #
- driver'licenses #
- driver'licence #
- driver 'licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- lic do driver #
- lics do driver #
- carteira de motorista #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving licence
- dlno #
- driv lic
- licencia de driv
- licença de driv
- licenças de driv
- driv licence
- licenças de driv
- driver licen
- drivers licen
- licenciador do driver
- lic de direção
- driving licen
- conduzir licenças
- driving licence
- driving licences
- permissão de direção
- dl no
- dlno
- dl number


#### <a name="keywords_austria_eu_drivers_license_number"></a>Keywords_austria_eu_driver s_license_number

- führerschein
- führerschein
- Führerscheine
- Führerscheinnummer
- Führerscheinnummern

## <a name="austria-identity-card"></a>Cartão de identidade da Áustria
Esse tipo de informação confidenciais só está disponível para uso em:
- políticas de prevenção contra perda de dados
- políticas de conformidade de comunicação
- governança de informações
- gerenciamento de registros
- Segurança do aplicativo na nuvem da Microsoft

### <a name="format"></a>Formatar

Uma combinação de 24 caracteres de letras, dígitos e caracteres especiais

### <a name="pattern"></a>Padrão

24 caracteres:

-  22 letras (não sensíveis a maiúsculas e minúsculas), dígitos, backslashes, barras de avanço ou sinais de mais

- duas letras (não sensíveis a maiúsculas e minúsculas), dígitos, backslashes, barras para frente, mais sinais ou sinais de igual

### <a name="checksum"></a>Soma de verificação

Não se aplica

### <a name="definition"></a>Definição

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:

- A expressão regular  `Regex_austria_eu_national_id_card` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de  `Keywords_austria_eu_national_id_card` é encontrada.

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
- national id
- personalausweis republik österreich

## <a name="austria-passport-number"></a>Número do passaporte da Áustria

### <a name="format"></a>Formatar

Uma letra seguida de um espaço opcional e sete dígitos

### <a name="pattern"></a>Padrão

Uma combinação de uma letra, sete dígitos e um espaço:

- uma letra (não sensível a minúsculas)
- um espaço (opcional)
- sete dígitos

### <a name="checksum"></a>Soma de verificação

não se aplica

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_austria_eu_passport_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave  `Keywords_eu_passport_number` de ou `Keywords_austria_eu_passport_number` é encontrada.
- A expressão regular `Regex_eu_passport_date1` localiza a data no formato DD.MM.YYYY ou uma palavra-chave de é `Keywords_eu_passport_date` encontrada

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_austria_eu_passport_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave  `Keywords_eu_passport_number` de ou `Keywords_austria_eu_passport_number` é encontrada.

```xml
      <!-- Austria Passport Number -->
      <Entity id="1c96ae4e-303b-447d-86c7-77113ac266bf" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_austria_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_austria_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- números do passport

#### <a name="keywords_austria_eu_passport_number"></a>Keywords_austria_eu_passport_number

- reisepassnummer
- reisepasse
- No-Reisepass
- Nr-Reisepass
- Reisepass-Nr
- Passnummer
- reisepässe

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- data de emissão
- data de expiração

## <a name="austria-social-security-number"></a>Número da Previdência Social da Áustria

### <a name="format"></a>Formatar

10 dígitos no formato especificado

### <a name="pattern"></a>Padrão

10 dígitos:

- três dígitos que correspondem a um número de série
- um dígito de verificação
- seis dígitos que correspondem à data de nascimento (DDMMYYY)

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_austria_eu_ssn_or_equivalent` localiza conteúdo que corresponde ao padrão.
- uma palavra-chave de  `Keywords_austria_eu_ssn_or_equivalent` é encontrada.

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_austria_eu_ssn_or_equivalent` localiza conteúdo que corresponde ao padrão.

```xml
      <!-- Austria Social Security Number -->
      <Entity id="6896a906-86c9-4d19-a2da-6e43ccd19b7b" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_austria_eu_ssn_or_equivalent" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          <Any minMatches="0" maxMatches="0">
            <Match idRef="Keywords_austria_eu_telephone_number" />
            <Match idRef="Keywords_austria_eu_mobile_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_austria_eu_ssn_or_equivalent"></a>Keywords_austria_eu_ssn_or_equivalent

- ssn austríaca
- número ehic
- ehic no
- código de seguro
- insurancecode #
- número do seguro
- seguro não
- krankenkassennummer
- krankenversicherung
- socialsecurityno
- socialsecurityno #
- social security no
- social security number
- social security code
- sozialversicherungsnummer
- sozialversicherungsnummer #
- soziale sicherheit kein
- sozialesicherheitkein #
- ssn #
- ssn
- versicherungscode
- versicherungsnummer
- zdravstveno zavarovanje

## <a name="austria-tax-identification-number"></a>Número de identificação fiscal da Áustria

### <a name="format"></a>Formatar

nove dígitos com hífen opcional e barra de avanço

### <a name="pattern"></a>Padrão

nove dígitos com hífen opcional e barra de avanço:

- dois dígitos
- um hífen (opcional)
- três dígitos
- uma barra de avanço (opcional)
- quatro dígitos

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_austria_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de  `Keywords_austria_eu_tax_file_number` é encontrada.

Uma política de DLP tem baixa confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
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
- número de identificação fiscal
- tax no #
- tax no
- número de imposto
- número de registro fiscal
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- id de estanho
- tin no
- tin #
- número de imposto

## <a name="austria-value-added-tax"></a>Imposto sobre o valor adicionado da Áustria
Esse tipo de informação confidenciais só está disponível para uso em:
- políticas de prevenção contra perda de dados
- políticas de conformidade de comunicação
- governança de informações
- gerenciamento de registros
- Segurança do aplicativo na nuvem da Microsoft

### <a name="format"></a>Formatar

Padrão alfanumérico de 11 caracteres

### <a name="pattern"></a>Padrão

Padrão alfanumérico de 11 caracteres:

- A ou a
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

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_Austria_Value_Added_Tax localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave Keyword_Austria_Value_Added_Tax é encontrada.

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_Austria_Value_Added_Tax localiza conteúdo que corresponde ao padrão.

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

- número de iva
- vat #
- número de iva austriaca
- vat no.
- vatno #
- valor adicionado número de imposto
- vat austria
- mwst
- umsatzsteuernummer
- mwstnummer
- ust.-identifikationsnummer
- umsatzsteuer-identifikationsnummer
- número de identificação de iva
- número de atu
- número uid


## <a name="azure-documentdb-auth-key"></a>Chave de auth do Azure DocumentDB

### <a name="format"></a>Formatar

A cadeia de caracteres "DocumentDb" seguida pelos caracteres e cadeias de caracteres descritos no padrão abaixo.

### <a name="pattern"></a>Padrão

- A cadeia de caracteres "DocumentDb"
- Qualquer combinação entre 3 a 200 letras minúsculas ou maiúsculas, dígitos, símbolos, caracteres especiais ou espaços
- Um símbolo maior do que >, um sinal de igual (=), uma aspas ("), ou um apóstrofo (')
- Qualquer combinação de 86 letras minúsculas ou maiúsculas, dígitos, barra (/) ou sinal de mais (+)
- Dois sinais iguais (=)

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular CEP_Regex_AzureDocumentDBAuthKey encontra conteúdo que corresponde ao padrão.
- A expressão regular CEP_CommonExampleKeywords não encontra conteúdo que corresponde ao padrão.

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

(Tecnicamente, esse tipo de informação sensível identifica essas palavras-chave usando uma expressão regular, não uma lista de palavras-chave.)

- contoso
- fabrikam
- northwind
- sandbox
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->net

## <a name="azure-iaas-database-connection-string-and-azure-sql-connection-string"></a>Cadeia de conexão de banco de dados iaas do Azure e cadeia de SQL de conexão do Azure

### <a name="format"></a>Formatar

A cadeia de caracteres "Server", "server" ou "data source" seguida pelos caracteres e cadeias de caracteres descritos no padrão abaixo, incluindo a cadeia de caracteres "cloudapp.azure.<!--no-hyperlink-->com" ou "cloudapp.azure.<!--no-hyperlink-->net" ou "database.windows.<!--no-hyperlink-->net", e a cadeia de caracteres "Password" ou "password" ou "pwd".

### <a name="pattern"></a>Padrão

- a cadeia de caracteres "Server", "server" ou "data source"
- zero a dois caracteres de espaço em branco
- um sinal de igual (=)
- zero a dois caracteres de espaço em branco
- qualquer combinação de entre 1 a 200 letras minúsculas ou maiúsculas, dígitos, símbolos, caracteres especiais ou espaços
- A cadeia de caracteres "cloudapp.azure.<!--no-hyperlink-->com", "cloudapp.azure.<!--no-hyperlink-->net", ou "database.windows.<!--no-hyperlink-->net"
- qualquer combinação de entre 1 a 300 letras minúsculas ou maiúsculas, dígitos, símbolos, caracteres especiais ou espaços
- a cadeia de caracteres "Password", "password" ou "pwd"
- zero a dois caracteres de espaço em branco
- um sinal de igual (=)
- zero a dois caracteres de espaço em branco
- um ou mais caracteres que não são ponto-e-vírgula (;), aspas ("), ou apóstrofo (')
- um ponto e vírgula (;), aspas ("), ou apóstrofo (')

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular CEP_Regex_AzureConnectionString encontra conteúdo que corresponde ao padrão.
- A expressão regular CEP_CommonExampleKeywords não encontra conteúdo que corresponde ao padrão.

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

(Tecnicamente, esse tipo de informação sensível identifica essas palavras-chave usando uma expressão regular, não uma lista de palavras-chave.)

- contoso
- fabrikam
- northwind
- sandbox
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->net

## <a name="azure-iot-connection-string"></a>Cadeia de conexão do Azure IoT

### <a name="format"></a>Formatar

A cadeia de caracteres "HostName" seguida pelos caracteres e cadeias de caracteres descritas no padrão abaixo, incluindo as cadeias de caracteres "azure-devices".<!--no-hyperlink-->net" e "SharedAccessKey".

### <a name="pattern"></a>Padrão

- a cadeia de caracteres "HostName"
- zero a dois caracteres de espaço em branco
- um sinal de igual (=)
- zero a dois caracteres de espaço em branco
- qualquer combinação de entre 1 a 200 letras minúsculas ou maiúsculas, dígitos, símbolos, caracteres especiais ou espaços
- a cadeia de caracteres "azure-devices.<!--no-hyperlink-->net"
- qualquer combinação de entre 1 a 200 letras minúsculas ou maiúsculas, dígitos, símbolos, caracteres especiais ou espaços
- a cadeia de caracteres "SharedAccessKey"
- zero a dois caracteres de espaço em branco
- um sinal de igual (=)
- zero a dois caracteres de espaço em branco
- qualquer combinação de 43 letras minúsculas ou maiúsculas, dígitos, barra (/) ou sinal de mais (+)
- um sinal de igual (=)

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular CEP_Regex_AzureIoTConnectionString encontra conteúdo que corresponde ao padrão.
- A expressão regular CEP_CommonExampleKeywords não encontra conteúdo que corresponde ao padrão.

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

(Tecnicamente, esse tipo de informação sensível identifica essas palavras-chave usando uma expressão regular, não uma lista de palavras-chave.)

- contoso
- fabrikam
- northwind
- sandbox
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->net

## <a name="azure-publish-setting-password"></a>Senha de configuração de publicação do Azure

### <a name="format"></a>Formatar

A cadeia de caracteres "userpwd=" seguida de uma cadeia de caracteres alfanumérico.

### <a name="pattern"></a>Padrão

- a cadeia de caracteres "userpwd="
- qualquer combinação de 60 letras minúsculas ou dígitos
- uma aspas (")

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular CEP_Regex_AzurePublishSettingPasswords encontra conteúdo que corresponde ao padrão.
- A expressão regular CEP_CommonExampleKeywords não encontra conteúdo que corresponde ao padrão.


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

(Tecnicamente, esse tipo de informação sensível identifica essas palavras-chave usando uma expressão regular, não uma lista de palavras-chave.)

- contoso
- fabrikam
- northwind
- sandbox
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->net

## <a name="azure-redis-cache-connection-string"></a>Cadeia de conexão de cache do Azure Redis

### <a name="format"></a>Formatar

A cadeia de caracteres "redis.cache.windows.<!--no-hyperlink-->net" seguido pelos caracteres e cadeias de caracteres descritos no padrão abaixo, incluindo a cadeia de caracteres "password" ou "pwd".

### <a name="pattern"></a>Padrão

- a cadeia de caracteres "redis.cache.windows.<!--no-hyperlink-->net"
- qualquer combinação de entre 1 a 200 letras minúsculas ou maiúsculas, dígitos, símbolos, caracteres especiais ou espaços
- a cadeia de caracteres "password" ou "pwd"
- zero a dois caracteres de espaço em branco
- um sinal de igual (=)
- zero a dois caracteres de espaço em branco
- qualquer combinação de 43 caracteres que sejam letras minúsculas ou maiúsculas, dígitos, barra (/) ou sinal de mais (+)
- um sinal de igual (=)

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular CEP_Regex_AzureRedisCacheConnectionString encontra conteúdo que corresponde ao padrão.
- A expressão regular CEP_CommonExampleKeywords não encontra conteúdo que corresponde ao padrão.

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

(Tecnicamente, esse tipo de informação sensível identifica essas palavras-chave usando uma expressão regular, não uma lista de palavras-chave.)

- contoso
- fabrikam
- northwind
- sandbox
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->net

## <a name="azure-sas"></a>Azure SAS

### <a name="format"></a>Formatar

A cadeia de caracteres "sig" seguida pelos caracteres e cadeias de caracteres descritas no padrão abaixo.

### <a name="pattern"></a>Padrão

- a cadeia de caracteres "sig"
- zero a dois caracteres de espaço em branco
- um sinal de igual (=)
- zero a dois caracteres de espaço em branco
- qualquer combinação de entre 43 a 53 caracteres que sejam letras minúsculas ou maiúsculas, dígitos ou o sinal de porcentagem (%)
- a cadeia de caracteres "%3d"
- qualquer caractere que não seja uma letra, dígito ou sinal de porcentagem inferior ou maiúscula (%)

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular CEP_Regex_AzureSAS encontra conteúdo que corresponde ao padrão.

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

A cadeia de caracteres "EndPoint" seguida pelos caracteres e cadeias de caracteres descritas no padrão abaixo, incluindo as cadeias de caracteres "servicebus.windows.<!--no-hyperlink-->net" e "SharedAccesKey".

### <a name="pattern"></a>Padrão

- a cadeia de caracteres "EndPoint"
- zero a dois caracteres de espaço em branco
- um sinal de igual (=)
- zero a dois caracteres de espaço em branco
- qualquer combinação de entre 1 a 200 letras minúsculas ou maiúsculas, dígitos, símbolos, caracteres especiais ou espaços
- a cadeia de caracteres "servicebus.windows.<!--no-hyperlink-->net"
- qualquer combinação de entre 1 a 200 letras minúsculas ou maiúsculas, dígitos, símbolos, caracteres especiais ou espaços
- a cadeia de caracteres "SharedAccessKey"
- zero a dois caracteres de espaço em branco
- um sinal de igual (=)
- zero a dois caracteres de espaço em branco
- qualquer combinação de 43 caracteres que sejam letras minúsculas ou maiúsculas, dígitos, barra (/) ou sinal de mais (+)
- um sinal de igual (=)

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular CEP_Regex_AzureServiceBusConnectionString encontra conteúdo que corresponde ao padrão.
- A expressão regular CEP_CommonExampleKeywords não encontra conteúdo que corresponde ao padrão.

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

(Tecnicamente, esse tipo de informação sensível identifica essas palavras-chave usando uma expressão regular, não uma lista de palavras-chave.)

- contoso
- fabrikam
- northwind
- sandbox
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->net

## <a name="azure-storage-account-key"></a>Chave de conta de armazenamento do Azure

### <a name="format"></a>Formatar

A cadeia de caracteres "DefaultEndpointsProtocol" seguida pelos caracteres e cadeias de caracteres descritos no padrão abaixo, incluindo a cadeia de caracteres "AccountKey".

### <a name="pattern"></a>Padrão

- a cadeia de caracteres "DefaultEndpointsProtocol"
- zero a dois caracteres de espaço em branco
- um sinal de igual (=)
- zero a dois caracteres de espaço em branco
- qualquer combinação de entre 1 a 200 letras minúsculas ou maiúsculas, dígitos, símbolos, caracteres especiais ou espaços
- a cadeia de caracteres "AccountKey"
- zero a dois caracteres de espaço em branco
- um sinal de igual (=)
- zero a dois caracteres de espaço em branco
- qualquer combinação de 86 caracteres que sejam letras minúsculas ou maiúsculas, dígitos, barra para frente (/) ou sinal de mais (+)
- dois sinais iguais (=)

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular CEP_Regex_AzureStorageAccountKey encontra conteúdo que corresponde ao padrão.
- A expressão regular CEP_AzureEmulatorStorageAccountFilter não encontra conteúdo que corresponde ao padrão.
- A expressão regular CEP_CommonExampleKeywords não encontra conteúdo que corresponde ao padrão.

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

(Tecnicamente, esse tipo de informação sensível identifica essas palavras-chave usando uma expressão regular, não uma lista de palavras-chave.)

- Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw==

#### <a name="cep_common_example_keywords"></a>CEP_common_example_keywords

(Tecnicamente, esse tipo de informação sensível identifica essas palavras-chave usando uma expressão regular, não uma lista de palavras-chave.)

- contoso
- fabrikam
- northwind
- sandbox
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->net

## <a name="azure-storage-account-key-generic"></a>Chave de conta do Azure Armazenamento (genérica)

### <a name="format"></a>Formatar

Qualquer combinação de 86 letras minúsculas ou maiúsculas, dígitos, a barra (/) ou sinal de mais (+), precedida ou seguida pelos caracteres descritos no padrão abaixo.

### <a name="pattern"></a>Padrão

- zero para um dos símbolos maior que (>), apóstrofo ('), sinal de igual (=), a aspas ("), ou sinal de número (#)
- qualquer combinação de 86 caracteres que sejam letras minúsculas ou maiúsculas, dígitos, a barra para frente (/) ou sinal de mais (+)
- dois sinais iguais (=)

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular CEP_Regex_AzureStorageAccountKeyGeneric encontra conteúdo que corresponde ao padrão.

```xml
<!--Azure Storage Account Key (Generic)-->
<Entity id="7ff41bd0-5419-4523-91d6-383b3a37f084" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKeyGeneric" />
  </Pattern>
</Entity>
```
## <a name="belgium-drivers-license-number"></a>Número da carteira de motorista belga

### <a name="format"></a>Formatar

10 dígitos sem espaços e delimitadores

### <a name="pattern"></a>Padrão

10 dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_belgium_eu_driver's_license_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave `Keywords_eu_driver's_license_number` de ou `Keywords_belgium_eu_driver's_license_number` é encontrada.

```xml
      <!-- Belgium Driver's License Number -->
      <Entity id="d89fd329-9324-433c-b687-2c37bd5166f3" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_belgium_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave


#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver'lic
- lics do driver
- driver'license
- driver'licenses
- driver'licence
- driver 'licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- lic do driver
- lics do driver
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver'lic #
- lics do driver #
- driver'license #
- driver'licenses #
- driver'licence #
- driver 'licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- lic do driver #
- lics do driver #
- carteira de motorista #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving licence
- dlno #
- driv lic
- licencia de driv
- licença de driv
- licenças de driv
- driv licence
- licenças de driv
- driver licen
- drivers licen
- licenciador do driver
- lic de direção
- driving licen
- conduzir licenças
- driving licence
- driving licences
- permissão de direção
- dl no
- dlno
- dl number

#### <a name="keywords_belgium_eu_drivers_license_number"></a>Keywords_belgium_eu_driver s_license_number

- rijbewijs
- rijbewijsnummer
- führerschein
- führerscheinnummer
- füehrerscheinnummer
- führerschein
- fuehrerschein
- führerscheinnummer
- fuehrerscheinnummer
- permis de conduire
- numéro permis conduire


## <a name="belgium-national-number"></a>Número nacional belga

### <a name="format"></a>Formatar

11 dígitos mais delimitadores opcionais

### <a name="pattern"></a>Padrão

11 dígitos mais delimitadores.
- seis dígitos e dois períodos opcionais no formato YY. MM.DD para data de nascimento
- Umlimiter opcional de ponto, traço, espaço
- três dígitos sequenciais (ímpar para homens, mesmo para mulheres)
- Umlimiter opcional de ponto, traço, espaço
- dois dígitos de verificação

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_belgium_national_number localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave Keyword_belgium_national_number é encontrada.
- A soma de verificação passa.

Uma política de DLP tem baixa confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_belgium_national_number localiza conteúdo que corresponde ao padrão.
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

- belasting aantal
- bnn #
- bnn
- carte d'identité
- identifiant nacional
- identifiantnational #
- identificatie
- identification
- identifikation
- identifikationsnummer
- identifizierung
- identité
- identiteit
- identiteitskaart
- identity
- inscrição
- número nacional
- registro nacional
- nationalnumber #
- nationalnumber
- nif #
- nif
- numéro d'assuré
- numéro de registre nacional
- numéro de sécurité
- numéro d'identification
- numéro d'immatriculation
- numéro nacional
- numéronational #
- número de ID pessoal
- personalausweis
- personalidnumber #
- registratie
- registration
- registrationsnumme
- registrierung
- social security number
- ssn #
- ssn
- steuernummer
- tax id
- identificação de imposto não
- número de identificação fiscal
- tax no #
- tax no
- número de imposto
- número de registro fiscal
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- id de estanho
- tin no
- tin #

## <a name="belgium-passport-number"></a>Número do passaporte belga

### <a name="format"></a>Formatar

duas letras seguidas por seis dígitos sem espaços ou delimitadores

### <a name="pattern"></a>Padrão

duas letras e seguidas por seis dígitos

### <a name="checksum"></a>Soma de verificação

não se aplica

### <a name="definition"></a>Definição

 Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_belgium_eu_passport_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave  `Keywords_eu_passport_number` de ou `Keywords_belgium_eu_passport_number` é encontrada.
- A expressão regular `Regex_eu_passport_date2` localiza data no formato DD MM YY ou uma palavra-chave de ou é `Keywords_eu_passport_date` `Keywords_belgium_eu_passport_number` encontrada

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_belgium_eu_passport_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave  `Keywords_eu_passport_number` de ou `Keywords_belgium_eu_passport_number` é encontrada.

```xml
      <!-- Belgium Passport Number -->
      <Entity id="d7b1315b-21ca-4774-a32a-596010ff78fd" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_belgium_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_belgium_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date2" />
            <Match idRef="Keywords_eu_passport_date" />
            <Match idRef="Keywords_belgium_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_belgium_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>

```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- números do passport

#### <a name="keywords_belgium_eu_passport_number"></a>Keywords_belgium_eu_passport_number

- numéro passeport
- paspoort nr
- paspoort-nr
- paspoortnummer
- paspoortnummers
- Passeport carte
- Passeport livre
- Pass-Nr
- Passnummer
- kein reisepass

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- data de emissão
- data de expiração

## <a name="belgium-value-added-tax-number"></a>Número de imposto adicionado ao valor belga
Esse tipo de informação confidenciais só está disponível para uso em:
- políticas de prevenção contra perda de dados
- políticas de conformidade de comunicação
- governança de informações
- gerenciamento de registros
- Segurança do aplicativo na nuvem da Microsoft

### <a name="format"></a>Formatar

Padrão alfanumérico de 12 caracteres

### <a name="pattern"></a>Padrão

Padrão alfanumérico de 12 caracteres:

- uma letra B ou b
- uma letra E ou e
- um dígito 0
- um dígito de 1 a 9
- um ponto opcional ou hífen ou espaço
- quatro dígitos
- um ponto opcional ou hífen ou espaço
- quatro dígitos


### <a name="checksum"></a>Soma de verificação

Sim


### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_belgium_value_added_tax_number encontra conteúdo que corresponde ao padrão.
- Uma palavra-chave Keywords_belgium_value_added_tax_number é encontrada.

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_belgium_value_added_tax_number encontra conteúdo que corresponde ao padrão.

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

- nº tva
- número de iva
- vat no
- numéro t.v.a
- umsatzsteuer-identifikationsnummer
- umsatzsteuernummer
- btw
- btw #
- vat #


## <a name="brazil-cpf-number"></a>Número de CPF do Brasil

### <a name="format"></a>Formatar

11 dígitos que incluem um dígito de verificação e podem ser formatados ou não formatados

### <a name="pattern"></a>Padrão

Formatado:
- três dígitos
- um ponto
- três dígitos
- um ponto
- três dígitos
- um hífen
- dois dígitos que são dígitos de verificação

Não formatado:
- 11 dígitos em que os dois últimos dígitos são dígitos de verificação

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_brazil_cpf localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_brazil_cpf é encontrada.
- A soma de verificação passa.

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_brazil_cpf localiza conteúdo que corresponde ao padrão.
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
- Identificação
- Registro
- Receita
- Cadastro de Pessoas Físicas
- Imposto
- Identificação
- Inscrição
- Receita


## <a name="brazil-legal-entity-number-cnpj"></a>Número da entidade jurídica do Brasil (CNPJ)

### <a name="format"></a>Formatar

14 dígitos que incluem um número de registro, o número da ramificação e dígitos de verificação, além de delimitadores de seleção

### <a name="pattern"></a>Padrão

14 dígitos mais delimitadores:

- dois dígitos
- um ponto
- três dígitos
- um ponto
- três dígitos (esses primeiros oito dígitos são o número de registro)
- uma barra de avanço
- número de filial de quatro dígitos
- um hífen
- dois dígitos que são dígitos de verificação

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_brazil_cnpj localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave Keyword_brazil_cnpj é encontrada.
- A soma de verificação passa.

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_brazil_cnpj localiza conteúdo que corresponde ao padrão.
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


## <a name="brazil-national-identification-card-rg"></a>RG (Cartão de Identificação Nacional do Brasil)

### <a name="format"></a>Formatar

Registro Geral (formato antigo): Nove dígitos

Registro de Identidade (RIC) (novo formato): 11 dígitos

### <a name="pattern"></a>Padrão

Registro Geral (formato antigo):
- dois dígitos
- um ponto
- três dígitos
- um ponto
- três dígitos
- um hífen
- um dígito que é um dígito de verificação

Registro de Identidade (RIC) (novo formato):
- 10 dígitos
- um hífen
- um dígito que é um dígito de verificação

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_brazil_rg encontra conteúdo que corresponde ao padrão.
- Uma palavra-chave Keyword_brazil_rg é encontrada.
- A soma de verificação passa.


```xml
      <!-- Brazil National ID Card (RG) -->
      <Entity id="486de900-db70-41b3-a886-abdf25af119c" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_brazil_rg" />
          <Match idRef="Keyword_brazil_rg" />
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
- RG (essa palavra-chave é sensível a minúsculas)
- RIC (essa palavra-chave é sensível a casos)


## <a name="bulgaria-drivers-license-number"></a>Número da carteira de motorista da Bulgária

### <a name="format"></a>Formatar

nove dígitos sem espaços e delimitadores

### <a name="pattern"></a>Padrão

nove dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_bulgaria_eu_driver's_license_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave  `Keywords_eu_driver's_license_number` de ou `Keywords_bulgaria_eu_driver's_license_number` é encontrada.

```xml
      <!-- Bulgaria Driver's License Number -->
      <Entity id="66d39258-94c2-43b2-804b-aa312258e54b" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver'lic
- lics do driver
- driver'license
- driver'licenses
- driver'licence
- driver 'licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- lic do driver
- lics do driver
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver'lic #
- lics do driver #
- driver'license #
- driver'licenses #
- driver'licence #
- driver 'licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- lic do driver #
- lics do driver #
- carteira de motorista #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving licence
- dlno #
- driv lic
- licencia de driv
- licença de driv
- licenças de driv
- driv licence
- licenças de driv
- driver licen
- drivers licen
- licenciador do driver
- lic de direção
- driving licen
- conduzir licenças
- driving licence
- driving licences
- permissão de direção
- dl no
- dlno
- dl number


#### <a name="keywords_bulgaria_eu_drivers_license_number"></a>Keywords_bulgaria_eu_driver s_license_number

- свидетелство за управление на мпс
- свидетелство за управление на моторно превозно средство
- сумпс
- шофьорска книжка
- шофьорски книжки

## <a name="bulgaria-uniform-civil-number"></a>Número civil uniforme da Bulgária
Esse tipo de informação confidenciais só está disponível para uso em:
- políticas de prevenção contra perda de dados
- políticas de conformidade de comunicação
- governança de informações
- gerenciamento de registros
- Segurança do aplicativo na nuvem da Microsoft

### <a name="format"></a>Formatar

10 dígitos sem espaços e delimitadores

### <a name="pattern"></a>Padrão

10 dígitos sem espaços e delimitadores

- seis dígitos que correspondem à data de nascimento (YYMMDD)
- dois dígitos que correspondem à ordem de nascimento
- um dígito que corresponde ao sexo: um dígito único para o sexo masculino e um dígito ímpar para o sexo feminino
- um dígito de verificação

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_bulgaria_eu_national_id_card` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de  `Keywords_bulgaria_eu_national_id_card` é encontrada.

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
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
- nomeador de edinen grazhdanski
- egn #
- egn
- identification number
- national id
- número nacional
- nationalnumber #
- nationalnumber
- id pessoal
- personal no
- número pessoal
- personalidnumber #
- social security number
- ssn #
- ssn
- ID civil uniforme
- uniforme civil não
- número civil uniforme
- uniformcivilno #
- uniformcivilno
- uniformcivilnumber #
- uniformcivilnumber
- número de cidadania exclusivo
- егн #
- егн
- единен граждански номер
- идентификационен номер
- личен номер
- лична идентификация
- лично не
- национален номер
- номер на гражданството
- униформ id
- унижорм граждански id
- униформ граждански не
- униформ граждански номер
- унижормгражданскиid #
- униформгражданскине. #


## <a name="bulgaria-passport-number"></a>Número do passaporte da Bulgária

### <a name="format"></a>Formatar

nove dígitos sem espaços e delimitadores

### <a name="pattern"></a>Padrão

nove dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_bulgaria_eu_passport_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave  `Keywords_eu_passport_number` de ou `Keywords_bulgaria_eu_passport_number` é encontrada.
- A expressão regular `Regex_eu_passport_date1` localiza a data no formato DD.MM.YYYY ou uma palavra-chave de é `Keywords_eu_passport_date` encontrada

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_bulgaria_eu_passport_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave  `Keywords_eu_passport_number` de ou `Keywords_bulgaria_eu_passport_number` é encontrada.

```xml
      <!-- Bulgaria Passport Number -->
      <Entity id="f7172b82-c588-4216-845e-4e54e397f29a" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_bulgaria_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_bulgaria_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- números do passport

#### <a name="keywords_bulgaria_eu_passport_number"></a>Keywords_bulgaria_eu_passport_number

- номер на паспорта
- номер на паспорт
- паспорт No

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- data de emissão
- data de expiração

## <a name="canada-bank-account-number"></a>Número da conta bancária do Canadá

### <a name="format"></a>Formatar

7 ou 12 dígitos

### <a name="pattern"></a>Padrão

Um Número de Conta Bancária do Canadá tem 7 ou 12 dígitos.

Um número de trânsito de conta bancária do Canadá tem:
- cinco dígitos
- um hífen
- OR de três dígitos
- zero "0"
- oito dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular Regex_canada_bank_account_number localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_canada_bank_account_number for encontrada.
- A expressão regular Regex_canada_bank_account_transit_number localiza o conteúdo que corresponde ao padrão.

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
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

Vários padrões que abrangem:
- Alberta
- British Columbia
- Manitoba
- New Brunswick
- Newfoundland/Labrador
- Nova Scotia
- Ontário
- Prince Edward Island
- Quebec
- Saskatchewan

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
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

#### <a name="keyword_province_name_drivers_license_name"></a>Keyword_[province_name]_drivers_license_name

- A abreviação da província, por exemplo AB
- O nome da província, por exemplo, Alberta

#### <a name="keyword_canada_drivers_license"></a>Keyword_canada_drivers_license

- DL
- DLS
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
- identification
- DL #
- DLS #
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
- id #
- ids #
- idcard card#
- idcard cards#
- idcard #
- identification card#
- identification cards#
- identification #


## <a name="canada-health-service-number"></a>Número do serviço de saúde do Canadá

### <a name="format"></a>Formatar

 10 dígitos

### <a name="pattern"></a>Padrão

10 dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
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
- psicanalista
- workers compensation
- Deficiência


## <a name="canada-passport-number"></a>Número do passaporte do Canadá

### <a name="format"></a>Formatar

duas letras maiúsculas seguidas por seis dígitos

### <a name="pattern"></a>Padrão

duas letras maiúsculas seguidas por seis dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular Regex_canada_passport_number localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_canada_passport_number ou Keyword_passport é encontrada.

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
- Passport #
- PassportID
- Passportno
- passportnumber
- パスポート
- パスポート番号
- パ ポトiNum
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

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular Regex_canada_phin localiza o conteúdo que corresponde ao padrão.
- Pelo menos duas palavras-chave de Keyword_canada_phin ou Keyword_canada_provinces são encontradas.

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


## <a name="canada-social-insurance-number"></a>Número do seguro social do Canadá

### <a name="format"></a>Formatar

nove dígitos com hifens opcionais ou espaços

### <a name="pattern"></a>Padrão

Formatado:
- três dígitos
- um hífen ou espaço
- três dígitos
- um hífen ou espaço
- três dígitos

Não formatado: nove dígitos

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_canadian_sin localiza conteúdo que corresponde ao padrão.
- Pelo menos dois dos seguintes padrões:
    - Uma palavra-chave de Keyword_sin for encontrada.
    - Uma palavra-chave de Keyword_sin_collaborative for encontrada.
    - A função Func_eu_date encontra uma data no formato de data à direita.
- A soma de verificação passa.

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
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
- sins
- ssn
- ssns
- social security
- numero d'assurance social
- national identification number
- national id
- sin #
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

sete a oito dígitos mais delimitadores de um dígito de verificação ou letra

### <a name="pattern"></a>Padrão

sete a oito dígitos mais delimitadores:
- de um a dois dígitos
- um período opcional
- três dígitos
- um período opcional
- três dígitos
- um traço
- um dígito ou letra (não sensível a minúsculas), que é um dígito de verificação

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_chile_id_card localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_chile_id_card é encontrada.
- A soma de verificação passa.

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_chile_id_card localiza conteúdo que corresponde ao padrão.
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

- cédula de identidad
- identificación
- national identification
- national identification number
- national id
- número de identificación nacional
- rol único nacional
- rol único tributario
- EXECUTAR
- RUT
- tarjeta de identificación
- Rol Unico Nacional
- Rol Unico Tributario
- EXECUTAR #
- RUT #
- nationaluniqueroleID #
- nacional identidad
- número identificación
- identidad número
- numero identificacion
- identidad numero
- Identidade chilena não.
- Número de identidade chileno
- Identidade chilena #
- Registro Fiscal Exclusivo
- Função afluente exclusiva
- Função fiscal exclusiva
- Número tributário exclusivo
- Número Nacional Exclusivo
- Função Nacional Exclusiva
- Função exclusiva nacional
- Identidade chilena não.
- Número de identidade do Chile
- Identidade do Chile #


## <a name="china-resident-identity-card-prc-number"></a>Número do cartão de identidade de residente da China (PRC)

### <a name="format"></a>Formatar

18 dígitos

### <a name="pattern"></a>Padrão

18 dígitos:
- seis dígitos que são um código de endereço
- oito dígitos no formato YYYYMMDD, que são a data de nascimento
- três dígitos que são um código de ordem
- um dígito que é um dígito de verificação

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_china_resident_id encontra conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_china_resident_id é encontrada.
- A soma de verificação passa.

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_china_resident_id encontra conteúdo que corresponde ao padrão.
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
- PRC
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

14 a 16 dígitos que podem ser formatados ou não formatados (ddddddd) e que devem passar no teste luhn.

### <a name="pattern"></a>Padrão

Detecta cartões de todas as principais marcas em todo o mundo, incluindo Visa, MasterCard, Discover Card, JCB, American Express, cartões de presente e cartões de lanchonete.

### <a name="checksum"></a>Soma de verificação

Sim, a soma de verificação Luhn

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_credit_card localiza conteúdo que corresponde ao padrão.
- Uma das seguintes opções for verdadeira:
    - Uma palavra-chave de Keyword_cc_verification for encontrada.
    - Uma palavra-chave de Keyword_cc_name for encontrada.
    - A função Func_expiration_date encontra uma data no formato de data à direita.
- A soma de verificação passa.

Uma política de DLP tem baixa confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
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

- card verification
- card identification number
- cvn
- cid
- cvc2
- cvv2
- pin block
- security code
- security number
- security no
- issue number
- issue no
- cryptogramme
- numéro de sécurité
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
- cod. sicurezza
- cod sicurezza
- n autorizzazione
- código
- codigo
- cod. seg
- cod seg
- código de segurança
- codigo de seguranca
- codigo de segurança
- código de seguranca
- 
cód. segurança
- cod. seguranca

- cod. segurança

- cód. seguranca
- cód segurança
- cod seguranca
- cod segurança
- cód seguranca
- número de verificação
- numero de verificacao
- ablauf
- gültig bis
- gültigkeitsdatum
- gultig bis
- gultigkeitsdatum
- scadenza
- data scad
- fecha de expiracion
- fecha de venc
- vencimiento
- válido hasta
- valido hasta
- vto
- data de expiração
- data de expiracao
- data em que expira
- validade
- valor
- vencimento
- transaction
- número da transação
- número de referência
- セキュリティコード
- セキュリティ コード
- セキュリティナンバー
- セキュリティ ナンバー
- セキュリティ番号

#### <a name="keyword_cc_name"></a>Keyword_cc_name

- amex
- american express
- americanexpress
- americano espresso
- Visa
- mastercard
- master card
- mc
- mastercards
- master cards
- diner's Club
- diners club
- dinersclub
- discover
- discover card
- discovercard
- discover cards
- JCB
- BrandSmart
- japanese card bureau
- carte blanche
- carteblanche
- credit card
- cc #
- cc#:
- expiration date
- exp date
- expiry date
- date d’expiration
- date d'exp
- date expiration
- bank card
- bankcard
- card number
- card num
- cardnumber
- cardnumbers
- card numbers
- creditcard
- credit cards
- creditcards
- ccn
- card holder
- cardholder
- card holders
- cardholders
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
- enroute
- en route
- card type
- Cardmember Acct
- conta cardmember
- Cardno
- Cartão Corporativo
- Cartões corporativos
- Tipo de cartão
- número da conta de cartão
- conta membro do cartão
- Cardmember Acct.
- card no.
- card no
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
- carta di credito
- carta credito
- n. carta
- n carta
- nr. carta
- nr carta
- numero carta
- numero della carta
- numero di carta
- tarjeta credito
- tarjeta de credito
- tarjeta crédito
- tarjeta de crédito
- tarjeta de atm
- tarjeta atm
- tarjeta debito
- tarjeta de debito
- tarjeta débito
- tarjeta de débito
- nº de tarjeta
- Não. de tarjeta
- no de tarjeta
- numero de tarjeta
- número de tarjeta
- tarjeta no
- tarjetahabiente
- cartão de crédito
- cartão de credito
- cartao de crédito
- cartao de credito
- cartão de débito
- cartao de débito
- cartão de debito
- cartao de debito
- débito automático
- debito automatico
- número do cartão
- numero do cartão
- número do cartao
- numero do cartao
- número de cartão
- numero de cartão
- número de cartao
- numero de cartao
- nº do cartão
- nº do cartao
- nº. do cartão
- no do cartão
- no do cartao
- Não. do cartão
- no. do cartao

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
- アメリカン エクスプレス
- Visaカ ド
- Visa カ ド
- マスターカード
- マスター カード
- マスター
- ダイナースクラブ
- ダイナース クラブ
- ダイナース
- 有効期限
- 期限
- キャッシュカード
- キャッシュ カード
- カード名義人
- カードの名義人
- カードの名義
- デビット カード
- デビットカード


## <a name="croatia-drivers-license-number"></a>Número da carteira de motorista da Croácia

### <a name="format"></a>Formatar

oito dígitos sem espaços e delimitadores

### <a name="pattern"></a>Padrão

oito dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:

- A expressão regular  `Regex_croatia_eu_driver's_license_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave `Keywords_eu_driver's_license_number` de ou `Keywords_croatia_eu_driver's_license_number` é encontrada.

```xml
      <!-- Croatia Driver's License Number -->
      <Entity id="005b3ef1-47dd-4e68-bb02-c6db484d00f2" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_croatia_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver'lic
- lics do driver
- driver'license
- driver'licenses
- driver'licence
- driver 'licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- lic do driver
- lics do driver
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver'lic #
- lics do driver #
- driver'license #
- driver'licenses #
- driver'licence #
- driver 'licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- lic do driver #
- lics do driver #
- carteira de motorista #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving licence
- dlno #
- driv lic
- licencia de driv
- licença de driv
- licenças de driv
- driv licence
- licenças de driv
- driver licen
- drivers licen
- licenciador do driver
- lic de direção
- driving licen
- conduzir licenças
- driving licence
- driving licences
- permissão de direção
- dl no
- dlno
- dl number


#### <a name="keywords_croatia_eu_drivers_license_number"></a>Keywords_croatia_eu_driver s_license_number

- vozačka dozvola
- vozačke dozvole


## <a name="croatia-identity-card-number"></a>Número do cartão de identidade croata
Essa entidade está incluída no tipo de informação confidenciais número de identificação nacional da UE. Ele está disponível como uma entidade de tipo de informação independente e sensível.

### <a name="format"></a>Formatar

nove dígitos

### <a name="pattern"></a>Padrão

nove dígitos consecutivos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_croatia_id_card encontra conteúdo que corresponde ao padrão.
- Uma palavra-chave Keyword_croatia_id_card é encontrada.

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

- majstorski broj građana
- número mestre de cidadãos
- nacionalni identifikacijski broj
- national identification number
- oib #
- oib
- osobna iskaznica
- osobni id
- osobni identifikacijski broj
- número de identificação pessoal
- porezni broj
- porezni identifikacijski broj
- tax id
- identificação de imposto não
- número de identificação fiscal
- tax no #
- tax no
- número de imposto
- número de registro fiscal
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- id de estanho
- tin no
- tin #


## <a name="croatia-passport-number"></a>Número do passaporte croata

### <a name="format"></a>Formatar

nove dígitos sem espaços e delimitadores

### <a name="pattern"></a>Padrão

nove dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_croatia_eu_passport_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave  `Keywords_eu_passport_number` de ou `Keywords_croatia_eu_passport_number` é encontrada.
- A expressão regular `Regex_eu_passport_date1` localiza a data no formato DD.MM.YYYY ou uma palavra-chave de é `Keywords_eu_passport_date` encontrada

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_croatia_eu_passport_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave  `Keywords_eu_passport_number` de ou `Keywords_croatia_eu_passport_number` é encontrada.

```xml
      <!-- Croatia Passport Number -->
      <Entity id="7d7a729d-32d8-4204-8d01-d5e6a6c25581" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_croatia_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_croatia_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- números do passport

#### <a name="keywords_croatia_eu_passport_number"></a>Keywords_croatia_eu_passport_number

- broj putovnice
- br. Putovnice
- br putovnice

## <a name="croatia-personal-identification-oib-number"></a>Número de identificação pessoal da Croácia (OIB)

### <a name="format"></a>Formatar

11 dígitos

### <a name="pattern"></a>Padrão

11 dígitos:
- 10 dígitos
- dígito final é um dígito de verificação

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_croatia_oib_number localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keywords_croatia_eu_tax_file_number é encontrada.
- A soma de verificação passa.

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_croatia_oib_number localiza conteúdo que corresponde ao padrão.
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

- majstorski broj građana
- número mestre de cidadãos
- nacionalni identifikacijski broj
- national identification number
- oib #
- oib
- osobna iskaznica
- osobni id
- osobni identifikacijski broj
- número de identificação pessoal
- porezni broj
- porezni identifikacijski broj
- tax id
- identificação de imposto não
- número de identificação fiscal
- tax no #
- tax no
- número de imposto
- número de registro fiscal
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- id de estanho
- tin no
- tin #

## <a name="cyprus-drivers-license-number"></a>Número da licença de drivers chipre

### <a name="format"></a>Formatar

12 dígitos sem espaços e delimitadores

### <a name="pattern"></a>Padrão

12 dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_cyprus_eu_driver's_license_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave  `Keywords_eu_driver's_license_number` de ou `Keywords_cyprus_eu_driver's_license_number` é encontrada.

```xml
      <!-- Cyprus Driver's License Number -->
      <Entity id="356fa104-f9ac-4aff-a0e4-2e6e65ea06c4" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver'lic
- lics do driver
- driver'license
- driver'licenses
- driver'licence
- driver 'licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- lic do driver
- lics do driver
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver'lic #
- lics do driver #
- driver'license #
- driver'licenses #
- driver'licence #
- driver 'licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- lic do driver #
- lics do driver #
- carteira de motorista #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving licence
- dlno #
- driv lic
- licencia de driv
- licença de driv
- licenças de driv
- driv licence
- licenças de driv
- driver licen
- drivers licen
- licenciador do driver
- lic de direção
- driving licen
- conduzir licenças
- driving licence
- driving licences
- permissão de direção
- dl no
- dlno
- dl number

#### <a name="keywords_cyprus_eu_drivers_license_number"></a>Keywords_cyprus_eu_driver s_license_number

- άδεια οδήγησης
- αριθμό άδειας οδήγησης
- άδειες οδήγησης


## <a name="cyprus-identity-card"></a>Cartão de identidade chipre
Esse tipo de informação confidenciais só está disponível para uso em:
- políticas de prevenção contra perda de dados
- políticas de conformidade de comunicação
- governança de informações
- gerenciamento de registros
- Segurança do aplicativo na nuvem da Microsoft

### <a name="format"></a>Formatar

10 dígitos sem espaços e delimitadores

### <a name="pattern"></a>Padrão

10 dígitos

### <a name="checksum"></a>Soma de verificação

não se aplica

### <a name="definition"></a>Definição

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_cyprus_eu_national_id_card` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de  `Keywords_cyprus_eu_national_id_card` é encontrada.

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

- Número do cartão de identificação
- número do cartão de identidade
- kimlik karti
- national identification number
- número de ID pessoal
- ταυτοτητασ


## <a name="cyprus-passport-number"></a>Número do passaporte chipre

### <a name="format"></a>Formatar

uma letra seguida de 6 a 8 dígitos sem espaços ou delimitadores

### <a name="pattern"></a>Padrão

uma letra seguida de seis a oito dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_cyprus_eu_passport_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave  `Keywords_eu_passport_number` de ou `Keywords_cyprus_eu_passport_number` é encontrada.
- A expressão regular `Regex_cyprus_eu_passport_date` localiza a data no formato DD/MM/YYYY ou uma palavra-chave de é `Keywords_cyprus_eu_passport_date` encontrada

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_cyprus_eu_passport_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave  `Keywords_eu_passport_number` de ou `Keywords_cyprus_eu_passport_number` é encontrada.

```xml
      <!-- Cyprus Passport Number -->
      <Entity id="9193e2e8-7f8c-43c1-a274-ac40d651936f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_cyprus_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_cyprus_eu_passport_date" />
            <Match idRef="Keywords_cyprus_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_cyprus_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- números do passport

#### <a name="keywords_cyprus_eu_passport_number"></a>Keywords_cyprus_eu_passport_number

- αριθμό διαβατηρίου
- pasaportu
- Αριθμός Διαβατηρίου
- κυπριακό διαβατήριο
- διαβατήριο #
- διαβατήριο
- αριθμός διαβατηρίου
- Pasaport Kimliği
- pasaport numarası
- Pasaport no.
- Αρ. Διαβατηρίου

#### <a name="keywords_cyprus_eu_passport_date"></a>Keywords_cyprus_eu_passport_date

- expira em
- emitido em


## <a name="cyprus-tax-identification-number"></a>Número de identificação fiscal de Chipre
Esse tipo de informação confidenciais só está disponível para uso em:
- políticas de prevenção contra perda de dados
- políticas de conformidade de comunicação
- governança de informações
- gerenciamento de registros
- Segurança do aplicativo na nuvem da Microsoft

### <a name="format"></a>Formatar

oito dígitos e uma letra no padrão especificado

### <a name="pattern"></a>Padrão

oito dígitos e uma letra:

- um "0" ou "9"
- sete dígitos
- uma letra (não sensível a minúsculas)

### <a name="checksum"></a>Soma de verificação

não se aplica

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_cyprus_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de  `Keywords_cyprus_eu_tax_file_number` é encontrada.

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
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
- código de identificação fiscal
- identificação de imposto não
- número de identificação fiscal
- tax no #
- tax no
- número de imposto
- número de registro fiscal
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- tic #
- tic
- id de estanho
- tin no
- tin #
- vergi kimlik kodu
- vergi kimlik numarası
- αριθμός φορολογικού μητρώου
- κωδικός φορολογικού μητρώου
- φορολογική ταυτότητα
- φορολογικού κωδικού


## <a name="czech-drivers-license-number"></a>Número da carteira de motorista tcheca

### <a name="format"></a>Formatar

duas letras seguidas por seis dígitos

### <a name="pattern"></a>Padrão

oito letras e dígitos:

- letra 'E' (não sensitivo para minúsculas)
- uma carta
- um espaço (opcional)
- seis dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_czech_republic_eu_driver's_license_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave  `Keywords_eu_driver's_license_number` de ou `Keywords_czech_republic_eu_driver's_license_number` é encontrada.

```xml
      <Entity id="86b40d3b-d8ea-4c36-aab0-ef9416a6769c" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>

```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver'lic
- lics do driver
- driver'license
- driver'licenses
- driver'licence
- driver 'licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- lic do driver
- lics do driver
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver'lic #
- lics do driver #
- driver'license #
- driver'licenses #
- driver'licence #
- driver 'licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- lic do driver #
- lics do driver #
- carteira de motorista #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving licence
- dlno #
- driv lic
- licencia de driv
- licença de driv
- licenças de driv
- driv licence
- licenças de driv
- driver licen
- drivers licen
- licenciador do driver
- lic de direção
- driving licen
- conduzir licenças
- driving licence
- driving licences
- permissão de direção
- dl no
- dlno
- dl number

#### <a name="keywords_czech_republic_eu_drivers_license_number"></a>Keywords_czech_republic_eu_driver s_license_number

- řidičský prúkaz
- řidičské průkazy
- číslo řidičského průkazu
- čísla řidičských průkazů


## <a name="czech-passport-number"></a>Número do passaporte tcheco

### <a name="format"></a>Formatar

oito dígitos sem espaços ou delimitadores

### <a name="pattern"></a>Padrão

oito dígitos sem espaços ou delimitadores

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_czech_republic_eu_passport_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave  `Keywords_eu_passport_number` de ou `Keywords_czech_republic_eu_passport_number` é encontrada.
- A expressão regular `Regex_eu_passport_date1` localiza a data no formato DD.MM.YYYY ou uma palavra-chave de é `Keywords_eu_passport_date` encontrada

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_czech_republic_eu_passport_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave  `Keywords_eu_passport_number` de ou `Keywords_czech_republic_eu_passport_number` é encontrada.

```xml
      <!-- Czech Republic Passport Number -->
      <Entity id="7bcd8ce8-5e92-4bbe-bc92-fa669f0369fa" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_czech_republic_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_czech_republic_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- números do passport

#### <a name="keywords_czech_republic_eu_passport_number"></a>Keywords_czech_republic_eu_passport_number

- edvní pas
- číslo pasu
- moscondávní pasu
- passeport no
- čísla pasu

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- data de emissão
- data de expiração


## <a name="czech-personal-identity-number"></a>Número da identidade pessoal tcheca

### <a name="format"></a>Formatar

nove dígitos com barra de avanço opcional (formato antigo) 10 dígitos com barra de avanço opcional (novo formato)

### <a name="pattern"></a>Padrão

nove dígitos (formato antigo):
- seis dígitos que representam a data de nascimento
- uma barra de avanço opcional
- três dígitos

10 dígitos (novo formato):
- seis dígitos que representam a data de nascimento
- uma barra de avanço opcional
- quatro dígitos em que o último dígito é um dígito de verificação

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:

- A função Func_czech_id_card localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave Keyword_czech_id_card é encontrada.
- A soma de verificação passa.

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:

- A função Func_czech_id_card_new_format encontra conteúdo que corresponde ao padrão.
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
- daňové číslo
- identifikační číslo
- identity no
- número de identidade
- identityno #
- identityno
- número do seguro
- national identification number
- nationalnumber #
- número nacional
- osobní číslo
- personalidnumber #
- número de ID pessoal
- número de identificação pessoal
- número pessoal
- pid #
- pid
- pojištění číslo
- rč
- rodne cislo
- rodné číslo
- ssn
- ssn #
- social security number
- tax id
- identificação de imposto não
- número de identificação fiscal
- tax no #
- tax no
- número de imposto
- número de registro fiscal
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- id de estanho
- tin no
- tin #
- número de identificação exclusivo


## <a name="denmark-drivers-license-number"></a>Número da carteira de motorista da Dinamarca

### <a name="format"></a>Formatar

oito dígitos sem espaços e delimitadores

### <a name="pattern"></a>Padrão

oito dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_denmark_eu_driver's_license_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave  `Keywords_eu_driver's_license_number` de ou `Keywords_denmark_eu_driver's_license_number` é encontrada.

```xml
      <!-- Denmark Driver's License Number -->
      <Entity id="98a95812-6203-451a-a220-d39870ebef0e" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_denmark_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver'lic
- lics do driver
- driver'license
- driver'licenses
- driver'licence
- driver 'licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- lic do driver
- lics do driver
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver'lic #
- lics do driver #
- driver'license #
- driver'licenses #
- driver'licence #
- driver 'licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- lic do driver #
- lics do driver #
- carteira de motorista #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving licence
- dlno #
- driv lic
- licencia de driv
- licença de driv
- licenças de driv
- driv licence
- licenças de driv
- driver licen
- drivers licen
- licenciador do driver
- lic de direção
- driving licen
- conduzir licenças
- driving licence
- driving licences
- permissão de direção
- dl no
- dlno
- dl number

#### <a name="keywords_denmark_eu_drivers_license_number"></a>Keywords_denmark_eu_driver s_license_number

- kørekort
- kørekortnummer


## <a name="denmark-passport-number"></a>Número do passaporte dinamarca

### <a name="format"></a>Formatar

nove dígitos sem espaços e delimitadores

### <a name="pattern"></a>Padrão

nove dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_denmark_eu_passport_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave  `Keywords_eu_passport_number` de ou `Keywords_denmark_eu_passport_number` é encontrada.
- A expressão regular `Regex_eu_passport_date2` localiza a data no formato DD MM YY ou uma palavra-chave de é `Keywords_eu_passport_date` encontrada

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_denmark_eu_passport_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave  `Keywords_eu_passport_number` de ou `Keywords_denmark_eu_passport_number` é encontrada.

```xml
      <!-- Denmark Passport Number -->
      <Entity id="25e8c47e-e6fe-4884-a211-74898f8c0196" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_denmark_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date2" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_denmark_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>

```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- números do passport

#### <a name="keywords_denmark_eu_passport_number"></a>Keywords_denmark_eu_passport_number

- pasnummer
- Passeport n°
- pasnumre

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- data de emissão
- data de expiração


## <a name="denmark-personal-identification-number"></a>Número de identificação pessoal da Dinamarca

### <a name="format"></a>Formatar

10 dígitos que contêm um hífen

### <a name="pattern"></a>Padrão

10 dígitos:
- seis dígitos no formato DDMMYYY, que são a data de nascimento
- um hífen
- quatro dígitos onde o dígito final é um dígito de verificação

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular Func_denmark_eu_tax_file_number encontra conteúdo que corresponde ao padrão.
- Uma palavra-chave Keyword_denmark_id é encontrada.
- A soma de verificação passa.

Uma política de DLP tem baixa confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular Func_denmark_eu_tax_file_number encontra conteúdo que corresponde ao padrão.
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

- personregister centrale
- civilt registreringssystem
- cpr
- cpr #
- nummer gesundheitskarte
- gesundheitsversicherungkarte nummer
- cartão de saúde
- número do cartão de seguro de saúde
- número do seguro de saúde
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
- número de ID pessoal
- personnummer
- personnummer #
- reisekrankenversicherungskartenummer
- rejsesygesikringskort
- ssn
- ssn #
- id skat
- skat kode
- nummer skat
- skattenummer
- social security number
- sundhedsforsikringskort
- sundhedsforsikringsnummer
- sundhedskort
- sundhedskortnummer
- sygesikring
- sygesikringkortnummer
- tax code
- cartão de seguro de saúde de viagem
- uniqueidentityno #
- número de imposto
- número de registro fiscal
- tax id
- número de identificação fiscal
- taxid #
- taxnumber #
- tax no
- taxno #
- taxnumber
- identificação de imposto não
- tin #
- taxidno #
- taxidnumber #
- tax no #
- id de estanho
- tin no
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


## <a name="drug-enforcement-agency-dea-number"></a>Número da Agência de Imposição de Drogas (DEA)

### <a name="format"></a>Formatar

duas letras seguidas por sete dígitos

### <a name="pattern"></a>Padrão

O padrão deve incluir todos os seguintes itens:
- uma letra (não sensível a maiúsculas e minúsculas) desse conjunto de letras possíveis: abcdefghjklmnprstux, que é um código de registro
- uma letra (não sensível a minúsculas), que é a primeira letra do sobrenome ou dígito do registro '9'
- sete dígitos, o último dos quais é o dígito de verificação

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_dea_number localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave `Keyword_dea_number` de é encontrada
- A soma de verificação passa.

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_dea_number localiza conteúdo que corresponde ao padrão.
- A soma de verificação passa.

```xml
    <!-- DEA Number -->
    <Entity id="9a5445ad-406e-43eb-8bd7-cac17ab6d0e4" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_dea_number" />
      </Pattern>
      <Version minEngineVersion="15.20.1207.000" maxEngineVersion="15.20.3134.000">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_dea_number" />
        </Pattern>
      </Version>
      <Version minEngineVersion="15.20.3135.000">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_dea_number" />
          <Match idRef="Keyword_dea_number" />
        </Pattern>
      </Version>
    </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_dea_number"></a>Keyword_dea_number

- dea
- dea #
- administração de imposição de drogas
- agência de aplicação de drogas


## <a name="estonia-drivers-license-number"></a>Número da carteira de motorista da Estônia

### <a name="format"></a>Formatar

duas letras seguidas por seis dígitos

### <a name="pattern"></a>Padrão

duas letras e seis dígitos:

- as letras "ET" (não sensíveis a maiúsculas e minúsculas)
- seis dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_estonia_eu_driver's_license_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave  `Keywords_eu_driver's_license_number` de ou `Keywords_estonia_eu_driver's_license_number` é encontrada.

```xml
      <!-- Estonia Driver's License Number -->
      <Entity id="51da8171-da70-4cc1-9d65-055a59ca4f83" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_estonia_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver'lic
- lics do driver
- driver'license
- driver'licenses
- driver'licence
- driver 'licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- lic do driver
- lics do driver
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver'lic #
- lics do driver #
- driver'license #
- driver'licenses #
- driver'licence #
- driver 'licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- lic do driver #
- lics do driver #
- carteira de motorista #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving licence
- dlno #
- driv lic
- licencia de driv
- licença de driv
- licenças de driv
- driv licence
- licenças de driv
- driver licen
- drivers licen
- licenciador do driver
- lic de direção
- driving licen
- conduzir licenças
- driving licence
- driving licences
- permissão de direção
- dl no
- dlno
- dl number

#### <a name="keywords_estonia_eu_drivers_license_number"></a>Keywords_estonia_eu_driver s_license_number

-- permis de conduire
- juhilubade numbrid
- número de juhiloa
- juhiluba


## <a name="estonia-personal-identification-code"></a>Código de Identificação Pessoal da Estônia
Esse tipo de informação confidenciais só está disponível para uso em:
- políticas de prevenção contra perda de dados
- políticas de conformidade de comunicação
- governança de informações
- gerenciamento de registros
- Segurança do aplicativo na nuvem da Microsoft

### <a name="format"></a>Formatar

11 dígitos sem espaços e delimitadores

### <a name="pattern"></a>Padrão

11 dígitos:

- um dígito que corresponde ao sexo e ao século de nascimento (número ímpar do sexo masculino, número par do sexo feminino; 1-2: século 19; 3-4: século 20; 5-6: século 21)
- seis dígitos que correspondem à data de nascimento (YYMMDD)
- três dígitos que correspondem a um número de série separando as pessoas que nasceram na mesma data
- um dígito de verificação

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_estonia_eu_national_id_card` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de  `Keywords_estonia_eu_national_id_card` é encontrada.

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
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

- id-kaart
- ik
- isikukood #
- isikukood
- maksu id
- maksukohustuslase identifitseerimisnumber
- maksunumber
- national identification number
- número nacional
- código pessoal
- número de ID pessoal
- código de identificação pessoal
- número de identificação pessoal
- personalidnumber #
- tax id
- identificação de imposto não
- número de identificação fiscal
- tax no #
- tax no
- número de imposto
- número de registro fiscal
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- id de estanho
- tin no
- tin #


## <a name="estonia-passport-number"></a>Número do passaporte da Estônia

### <a name="format"></a>Formatar

uma letra seguida por sete dígitos sem espaços ou delimitadores

### <a name="pattern"></a>Padrão

uma letra seguida por sete dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_estonia_eu_passport_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave  `Keywords_eu_passport_number` de ou `Keywords_estonia_eu_passport_number` é encontrada.
- A expressão regular `Regex_eu_passport_date1` localiza a data no formato DD.MM.YYYY ou uma palavra-chave de é `Keywords_eu_passport_date` encontrada

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_estonia_eu_passport_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave  `Keywords_eu_passport_number` de ou `Keywords_estonia_eu_passport_number` é encontrada.

```xml
      <!-- Estonia Passport Number -->
      <Entity id="61f7073a-509e-425b-a754-bc01bb5d5b8c" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_estonia_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_estonia_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- números do passport

#### <a name="keywords_estonia_eu_passport_number"></a>Keywords_estonia_eu_passport_number

eesti kodaniku passi number passinumbrid document no dokumendi nr

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- data de emissão
- data de expiração


## <a name="eu-debit-card-number"></a>Número do cartão de débito da UE

### <a name="format"></a>Formatar

16 dígitos

### <a name="pattern"></a>Padrão

Padrão complexo e robusto

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
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
- cc #

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
- cardholder
- cardholders
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
- ccn
- check card
- check cards
- checkcard
- checkcards
- chequekaart
- cirrus
- cirrus-edc-maestro
- controlekaart
- controlekaarten
- credit card
- credit cards
- creditcard
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
- discover
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
- jcb
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
- maestro
- master card
- master cards
- mastercard
- mastercards
- mc
- mister cash
- n carta
- carta
- no de tarjeta
- no do cartao
- no do cartão
- no. de tarjeta

- no. do cartao

- no. do cartão

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
- nº. do cartão

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
- solo
- supporti di scheda
- supporto di scheda
- switch
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
- v-pay
- visa
- visa plus
- visa electron
- visto
- visum
- vpay

#### <a name="keyword_card_security_terms_dict"></a>Keyword_card_security_terms_dict

- card identification number
- card verification
- cardi la verifica
- cid
- cod seg
- cod seguranca
- cod segurança
- cod sicurezza
- cod. seg

- cod. seguranca

- cod. segurança

- cod. sicurezza

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

- código
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
- no. dell'edizione

- no. di sicurezza

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
- expiration
- expire
- expira
- expiry
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
- valor
- venc
- vencimento
- vencimiento
- verloopt
- vervaldag
- vervaldatum
- vto
- válido hasta


## <a name="eu-drivers-license-number"></a>Número da carteira de motorista da UE

Essas entidades estão no Número de Licença de Motorista da UE e são tipos de informações confidenciais.

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
- [Luxemburgo](#luxemburg-drivers-license-number)
- [Malta](#malta-drivers-license-number)
- [Países Baixos](#netherlands-drivers-license-number)
- [Polônia](#poland-drivers-license-number)
- [Portugal](#portugal-drivers-license-number)
- [Romênia](#romania-drivers-license-number)
- [Eslováquia](#slovakia-drivers-license-number)
- [Eslovênia](#slovenia-drivers-license-number)
- [Espanha](#spain-drivers-license-number)
- [Suécia](#sweden-drivers-license-number)
- [Reino Unido](#uk-drivers-license-number)


## <a name="eu-national-identification-number"></a>Número de identificação nacional da UE

Essas entidades estão no Número de Identificação Nacional da UE e são tipos de informações confidenciais.

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
- [Luxemburgo](#luxemburg-national-identification-number-natural-persons)
- [Malta](#malta-identity-card-number)
- [Países Baixos](#netherlands-citizens-service-bsn-number)
- [Polônia](#poland-national-id-pesel)
- [Portugal](#portugal-citizen-card-number)
- [Romênia](#romania-personal-numeric-code-cnp)
- [Eslováquia](#slovakia-personal-number)
- [Eslovênia](#slovenia-unique-master-citizen-number)
- [Espanha](#spain-dni)
- [Reino Unido](#uk-national-insurance-number-nino)


## <a name="eu-passport-number"></a>Número do passaporte da UE

Essas entidades estão no número de passaporte da UE e são tipos de informações confidenciais. Essas entidades estão no pacote de números de passaporte da UE.

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
- [Luxemburgo](#luxemburg-passport-number)
- [Malta](#malta-passport-number)
- [Países Baixos](#netherlands-passport-number)
- [Polônia](#poland-passport-number)
- [Portugal](#portugal-passport-number)
- [Romênia](#romania-passport-number)
- [Eslováquia](#slovakia-passport-number)
- [Eslovênia](#slovenia-passport-number)
- [Espanha](#spain-passport-number)
- [Suécia](#sweden-passport-number)
- [Reino Unido](#us--uk-passport-number)


## <a name="eu-social-security-number-or-equivalent-identification"></a>Número de segurança social da UE ou identificação equivalente

Essas entidades que estão no Número de Segurança Social da UE ou identificação equivalente e são tipos de informações confidenciais.

- [Áustria ](#austria-social-security-number)
- [Bélgica](#belgium-national-number)
- [Croácia ](#croatia-personal-identification-oib-number)
- [Tcheco](#czech-personal-identity-number)
- [Dinamarca](#denmark-personal-identification-number)
- [Finlândia ](#finland-national-id)
- [França ](#france-social-security-number-insee)
- [Alemanha ](#germany-identity-card-number)
- [Grécia](#greece-national-id-card)
- [Hungria](#hungary-social-security-number-taj)
- [Portugal](#portugal-citizen-card-number)
- [Espanha](#spain-social-security-number-ssn)
- [Suécia](#sweden-national-id)


## <a name="eu-tax-identification-number"></a>Número de identificação de imposto da UE

Essas entidades estão no tipo de informação confidenciais do número de identificação do imposto da UE.

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
- [Luxemburgo](#luxemburg-national-identification-number-non-natural-persons)
- [Malta](#malta-tax-identification-number)
- [Países Baixos](#netherlands-tax-identification-number)
- [Polônia](#poland-tax-identification-number)
- [Portugal](#portugal-tax-identification-number)
- [Romênia](#romania-personal-numeric-code-cnp)
- [Eslováquia](#slovakia-personal-number)
- [Eslovênia](#slovenia-tax-identification-number)
- [Espanha](#spain-tax-identification-number)
- [Suécia](#sweden-tax-identification-number)
- [Reino Unido](#uk-unique-taxpayer-reference-number)


## <a name="finland-drivers-license-number"></a>Número da carteira de motorista da Finlândia

### <a name="format"></a>Formatar

10 dígitos que contêm um hífen

### <a name="pattern"></a>Padrão

10 dígitos contendo um hífen:

- seis dígitos
- um hífen
- três dígitos
- um dígito ou uma letra

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_finland_eu_driver's_license_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave  `Keywords_eu_driver's_license_number` de ou `Keywords_finland_eu_driver's_license_number` é encontrada.

```xml
      <!-- Finland Driver's License Number -->
      <Entity id="bb3b27a3-79bd-4ac4-81a7-f9fca3c7d1a7" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_finland_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver'lic
- lics do driver
- driver'license
- driver'licenses
- driver'licence
- driver 'licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- lic do driver
- lics do driver
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver'lic #
- lics do driver #
- driver'license #
- driver'licenses #
- driver'licence #
- driver 'licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- lic do driver #
- lics do driver #
- carteira de motorista #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving licence
- dlno #
- driv lic
- licencia de driv
- licença de driv
- licenças de driv
- driv licence
- licenças de driv
- driver licen
- drivers licen
- licenciador do driver
- lic de direção
- driving licen
- conduzir licenças
- driving licence
- driving licences
- permissão de direção
- dl no
- dlno
- dl number


#### <a name="keywords_finland_eu_drivers_license_number"></a>Keywords_finland_eu_driver s_license_number

- ajokortti
- permis de conduire
- ajokortin numero
- kuljettaja lic.
- körkort
- körkortnummer
- förare lic.
- ajokortit
- ajokortin numerot


## <a name="finland-european-health-insurance-number"></a>Número do seguro de saúde europeu da Finlândia
Esse tipo de informação confidenciais só está disponível para uso em:
- políticas de prevenção contra perda de dados
- políticas de conformidade de comunicação
- governança de informações
- gerenciamento de registros
- Segurança do aplicativo na nuvem da Microsoft

### <a name="format"></a>Formatar

Número de 20 dígitos

### <a name="pattern"></a>Padrão

Número de 20 dígitos:

- 10 dígitos - 8024680246
- um espaço opcional ou hífen
- 10 dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- O regex Regex_Finland_European_Health_Insurance_Number o conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_Finland_European_Health_Insurance_Number é encontrada.

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
- finska sjukförsäkringskort
- cartão de saúde
- cartão de seguro de saúde
- número do seguro de saúde
- hälsokort
- sairaanhoitokortin
- sairausvakuutuskortti
- sairausvakuutusnumero
- Nummer sjukförsäkring
- sjukförsäkringskort
- suomen sairausvakuutuskortti
- terveyskortti


## <a name="finland-national-id"></a>ID nacional da Finlândia

### <a name="format"></a>Formatar

seis dígitos mais um caractere indicando um século mais três dígitos mais um dígito de verificação

### <a name="pattern"></a>Padrão

O padrão deve incluir todos os seguintes itens:
- seis dígitos no formato DDMMYYY, que são uma data de nascimento
- marcador de século ('-', '+' ou 'a')
- número de identificação pessoal de três dígitos
- um dígito ou uma letra (insensível a maiúsculas e minúsculas), que é um dígito de verificação

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- a função Func_finnish_national_id encontra conteúdo que corresponde ao padrão
- uma palavra-chave de Keyword_finnish_national_id é encontrada
- o checksum passa

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- a função Func_finnish_national_id encontra conteúdo que corresponde ao padrão
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

- ainutlaatuinen henkilökohtainen tunnus
- henkilökohtainen tunnus
- henkilötunnus
- henkilötunnusnumero #
- henkilötunnusnumero
- hetu
- id no
- número de id
- identification number
- identiteetti numero
- número de identidade
- idnumber
- kansallinen henkilötunnus
- kansallisen henkilökortin
- cartão de identificação nacional
- id nacional não.
- id pessoal
- código de identidade pessoal
- personalidnumber #
- personbeteckning
- personnummer
- social security number
- sosiaaliturvatunnus
- tax id
- identificação de imposto não
- número de identificação fiscal
- tax no #
- tax no
- número de imposto
- número de registro fiscal
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- id de estanho
- tin no
- tin #
- tunnistenumero
- tunnus numero
- tunnusluku
- tunnusnumero
- verokortti
- veronumero
- verotunniste
- verotunnus


## <a name="finland-passport-number"></a>Número do passaporte finlandês

Essa entidade está disponível no tipo de informação confidenciais número de passaporte da UE e está disponível como uma entidade de tipo de informação independente e confidenciais.

### <a name="format"></a>Formatar
combinação de nove letras e dígitos

### <a name="pattern"></a>Padrão
combinação de nove letras e dígitos:
- duas letras (não sensíveis a maiúsculas e minúsculas)
- sete dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular `Regex_finland_passport_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave `Keywords_eu_passport_number` de ou `Keyword_finland_passport_number` é encontrada.
- A expressão regular `Regex_eu_passport_date1` localiza a data no formato DD.MM.YYYY ou uma palavra-chave de é `Keywords_eu_passport_date` encontrada

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular `Regex_finland_passport_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave `Keywords_eu_passport_number` de ou `Keyword_finland_passport_number` é encontrada.

```xml
      <!-- Finland Passport Number -->
      <Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_finland_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keyword_finland_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keyword_finland_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- números do passport

#### <a name="keyword_finland_passport_number"></a>Keyword_finland_passport_number

- suomalainen passi
- passin numero
- passin numero. #
- passin numero #
- passin numero.
- passi #
- número passi

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- data de emissão
- data de expiração

## <a name="france-drivers-license-number"></a>Número da carteira de motorista da França

Essa entidade está disponível no tipo de informação confidenciais número de licença de motorista da UE e está disponível como uma entidade de tipo de informação independente e confidenciais.

### <a name="format"></a>Formatar

12 dígitos

### <a name="pattern"></a>Padrão

12 dígitos com a validação para descontar padrões similares, como números de telefone em francês

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- a função Func_french_drivers_license encontra conteúdo que corresponde ao padrão.
- uma palavra-chave de Keyword_french_drivers_license é encontrada.

```xml
    <!-- France Driver's License Number -->
    <Entity id="18e55a36-a01b-4b0f-943d-dc10282a1824" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_french_drivers_license" />
        <Match idRef="Keyword_french_drivers_license" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_french_drivers_license"></a>Keyword_french_drivers_license

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver'lic
- lics do driver
- driver'license
- driver'licenses
- driver'licence
- driver 'licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- lic do driver
- lics do driver
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver'lic #
- lics do driver #
- driver'license #
- driver'licenses #
- driver'licence #
- driver 'licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- lic do driver #
- lics do driver #
- carteira de motorista #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving licence
- dlno #
- driv lic
- licencia de driv
- licença de driv
- licenças de driv
- driv licence
- licenças de driv
- driver licen
- drivers licen
- licenciador do driver
- lic de direção
- driving licen
- conduzir licenças
- driving licence
- driving licences
- permissão de direção
- dl no
- dlno
- dl number
- permis de conduire
- licence number
- license number
- licence numbers
- license numbers
- numéros de licence


## <a name="france-health-insurance-number"></a>Número do seguro de saúde da França
Esse tipo de informação confidenciais só está disponível para uso em:
- políticas de prevenção contra perda de dados
- políticas de conformidade de comunicação
- governança de informações
- gerenciamento de registros
- Segurança do aplicativo na nuvem da Microsoft

### <a name="format"></a>Formatar

Número de 21 dígitos

### <a name="pattern"></a>Padrão

Número de 21 dígitos:

- 10 dígitos
- um espaço opcional
- 10 dígitos
- um espaço opcional
- um dígito


### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- o regex Regex_France_Health_Insurance_Number o conteúdo que corresponde ao padrão.
- uma palavra-chave Keyword_France_Health_Insurance_Number é encontrada.

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
- carte vitale
- carte d'assuré social


## <a name="france-national-id-card-cni"></a>CNI (National ID Card) da França

### <a name="format"></a>Formatar

12 dígitos

### <a name="pattern"></a>Padrão

12 dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem baixa confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular Regex_france_cni localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave Keywords_france_eu_national_id_card é encontrada.

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
- carte nationale d'identité
- carte nationale d'idenite no
- cni #
- cni
- compte bancaire
- national identification number
- identidade nacional
- nationalidno #
- numéro d'assurance maladie
- numéro de carte vitale


## <a name="france-passport-number"></a>Número do passaporte francês
Essa entidade está disponível no tipo de informação confidenciais número de passaporte da UE. Ele também está disponível como uma entidade de tipo de informação independente e confidenciais.

### <a name="format"></a>Formatar

nove dígitos e letras

### <a name="pattern"></a>Padrão

nove dígitos e letras:
- dois dígitos
- duas letras (não sensíveis a maiúsculas e minúsculas)
- cinco dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função `Func_fr_passport` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave `Keywords_eu_passport_number` de ou `Keywords_france_eu_passport_number` é encontrada.
- A expressão regular `Regex_eu_passport_date3` localiza data no formato DD MM YYYY ou uma palavra-chave de é `Keywords_eu_passport_date` encontrada

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função `Func_fr_passport` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave `Keywords_eu_passport_number` de ou `Keywords_france_eu_passport_number` é encontrada.


```xml
    <!-- France Passport Number -->
    <Entity id="3008b884-8c8c-4cd8-a289-99f34fc7ff5d" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_fr_passport" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_france_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date3" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_fr_passport" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_france_eu_passport_number" />
          </Any>
        </Pattern>
    </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- números do passport

#### <a name="keywords_france_eu_passport_number"></a>Keywords_france_eu_passport_number

- numéro de passeport
- passeport n °
- passeport non
- passeport #
- passeport #
- passeportnon
- passeportn °
- passeport français
- passeport livre
- passeport carte
- numéro passeport
- passeport n°
- n° du passeport
- n° passeport

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- data de emissão
- data de expiração


## <a name="france-social-security-number-insee"></a>Número de segurança social da França (INSEE)

### <a name="format"></a>Formatar

15 dígitos

### <a name="pattern"></a>Padrão

Deve corresponder a um dos dois padrões:
- 13 dígitos seguidos por um espaço seguido por dois dígitos<br/>
ou
- 15 dígitos consecutivos

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função `Func_french_insee` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_fr_insee for encontrada.
- A soma de verificação passa.

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_french_insee ou Func_fr_insee o conteúdo que corresponde ao padrão.
- A soma de verificação passa.

```xml
    <!-- France INSEE -->
    <Entity id="71f62b97-efe0-4aa1-aa49-e14de253619d" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_french_insee" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_fr_insee" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_french_insee" />
        <Match idRef="Keyword_fr_insee" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_fr_insee"></a>Keyword_fr_insee

- code sécu
- d'identité nationale
- insee
- fssn #
- le numéro d'identification nationale
- le code de la sécurité sociale
- national id
- national identification
- no d'identité
- 
no. d'identité
- numéro d'assurance
- numéro d'identité
- numero d'identite
- numéro de sécu
- numéro de sécurité sociale
- no d'identite
- 
no. d'identite
- ssn
- ssn #
- sécurité sociale
- securité sociale
- securite sociale
- socialsecuritynumber
- social security number
- social security code
- social insurance number


## <a name="france-tax-identification-number"></a>Número de identificação fiscal da França

### <a name="format"></a>Formatar

13 dígitos

### <a name="pattern"></a>Padrão

13 dígitos

- Um dígito que deve ser 0, 1, 2 ou 3
- Um dígito
- Um espaço (opcional)
- Dois dígitos
- Um espaço (opcional)
- Três dígitos
- Um espaço (opcional)
- Três dígitos
- Um espaço (opcional)
- Três dígitos de verificação


### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_france_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de  `Keywords_france_eu_tax_file_number` é encontrada.

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
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

- numéro d'identification fiscale
- tax id
- identificação de imposto não
- número de identificação fiscal
- tax no #
- tax no
- número de imposto
- número de registro fiscal
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- id de estanho
- tin no
- tin #


## <a name="france-value-added-tax-number"></a>Número de imposto adicionado ao valor da França
Esse tipo de informação confidenciais só está disponível para uso em:
- políticas de prevenção contra perda de dados
- políticas de conformidade de comunicação
- governança de informações
- gerenciamento de registros
- Segurança do aplicativo na nuvem da Microsoft

### <a name="format"></a>Formatar

Padrão alfanumérico de 13 caracteres

### <a name="pattern"></a>Padrão

Padrão alfanumérico de 13 caracteres:

- duas letras - FR (insensível a maiúsculas e minúsculas)
- um espaço opcional ou hífen
- duas letras ou dígitos
- um espaço opcional, ponto, hífen ou vírgula
- três dígitos
- um espaço opcional, ponto, hífen ou vírgula
- três dígitos
- um espaço opcional, ponto, hífen ou vírgula
- três dígitos

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_france_value_added_tax_number encontra conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keywords_france_value_added_tax_number é encontrada.

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_france_value_added_tax_number encontra conteúdo que corresponde ao padrão.

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

- número de iva
- vat no
- vat #
- value added tax
- identificação de sirene nenhum numéro d'identification taxe sur valeur ajoutée
- taxe valeur ajoutée
- taxe sur la valeur ajoutée
- n° tva
- numéro de tva
- numéro d'identification siren


## <a name="germany-drivers-license-number"></a>Número da carteira de motorista da Alemanha

Essa entidade de tipo de informação confidenciais está incluída no tipo de informação confidenciais do Número de Licença do Driver da UE. Ele também está disponível como uma entidade de tipo de informação independente e confidenciais.

### <a name="format"></a>Formatar

combinação de 11 dígitos e letras

### <a name="pattern"></a>Padrão

11 dígitos e letras (não sensíveis a maiúsculas e minúsculas):
- um dígito ou uma letra
- dois dígitos
- seis dígitos ou letras
- um dígito
- um dígito ou uma letra

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_german_drivers_license localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_german_drivers_license_number for encontrada.
- A soma de verificação passa.

```xml
    <!-- German Driver's License Number -->
    <Entity id="91da9335-1edb-45b7-a95f-5fe41a16c63c" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_german_drivers_license" />
        <Match idRef="Keyword_german_drivers_license" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_german_drivers_license_number"></a>Keyword_german_drivers_license_number

- ausstellungsdatum
- ausstellungsort
- ausstellende behöde
- ausstellende behorde
- ausstellende behoerde
- führerschein
- führerschein
- fuehrerschein
- führerscheinnummer
- führerscheinnummer
- fuehrerscheinnummer
- führerschein- 
- führerschein- 
- fuehrerschein- 
- führerscheinnummernr
- führerscheinnummernr
- fuehrerscheinnummernr
- führerscheinnummerklasse
- führerscheinnummerklasse
- fuehrerscheinnummerklasse
- nr-führerschein
- nr-führerschein
- nr-fuehrerschein
- no-führerschein
- no-hrerschein
- no-fuehrerschein
- n-führerschein
- n-führerschein
- n-fuehrerschein
- permis de conduire
- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver'lic
- lics do driver
- driver'license
- driver'licenses
- driver'licence
- driver 'licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- lic do driver
- lics do driver
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver'lic #
- lics do driver #
- driver'license #
- driver'licenses #
- driver'licence #
- driver 'licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- lic do driver #
- lics do driver #
- carteira de motorista #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving licence
- dlno #
- driv lic
- licencia de driv
- licença de driv
- licenças de driv
- driv licence
- licenças de driv
- driver licen
- drivers licen
- licenciador do driver
- lic de direção
- driving licen
- conduzir licenças
- driving licence
- driving licences
- permissão de direção
- dlno


## <a name="germany-identity-card-number"></a>Número do cartão de identidade da Alemanha

### <a name="format"></a>Formatar

desde 1º de novembro de 2010: Nove letras e dígitos

de 1º de abril de 1987 a 31 de outubro de 2010: 10 dígitos

### <a name="pattern"></a>Padrão

desde 1º de novembro de 2010:
- uma letra (não sensível a minúsculas)
- oito dígitos

de 1º de abril de 1987 a 31 de outubro de 2010:
- 10 dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem baixa confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular Regex_germany_id_card encontra conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_germany_id_card é encontrada.

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
- identification
- identifikation
- identifizierungsnummer
- cartão de identidade
- número de identidade
- id-nummer
- id pessoal
- personalausweis
- persönliche id nummer
- persönliche identifikationsnummer
- persönliche-id-nummer


## <a name="germany-passport-number"></a>Número do passaporte da Alemanha

Essa entidade está incluída no tipo de informação confidenciais número de passaporte da UE e está disponível como uma entidade de tipo de informação independente e confidenciais.

### <a name="format"></a>Formatar

10 dígitos ou letras

### <a name="pattern"></a>Padrão

O padrão deve incluir todos os seguintes itens:
- primeiro caractere é um dígito ou uma letra deste conjunto (C, F, G, H, J, K)
- três dígitos
- cinco dígitos ou letras deste conjunto (C, -H, J-N, P, R, T, V-Z)
- um dígito

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_german_passport localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave `Keyword_german_passport` de ou `Keywords_eu_passport_number_common` é encontrada.
- A soma de verificação passa.

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_german_passport_data localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave `Keyword_german_passport` de ou `Keywords_eu_passport_number_common` é encontrada.
- A soma de verificação passa.

```xml
    <!-- German Passport Number -->
    <Entity id="2e3da144-d42b-47ed-b123-fbf78604e52c" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_german_passport" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_passport" />
          <Match idRef="Keywords_eu_passport_number_common" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_german_passport_data" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_passport" />
          <Match idRef="Keywords_eu_passport_number_common" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_german_passport"></a>Keyword_german_passport

- reisepasse
- reisepassnummer
- No-Reisepass
- Nr-Reisepass
- Reisepass-Nr
- Passnummer
- reisepässe
- passeport no.
- passeport no

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- números do passport


## <a name="germany-tax-identification-number"></a>Número de identificação fiscal da Alemanha

### <a name="format"></a>Formatar

11 dígitos sem espaços e delimitadores

### <a name="pattern"></a>Padrão

11 dígitos

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

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_germany_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de  `Keywords_germany_eu_tax_file_number` é encontrada.

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
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
- steuer id
- steueridentifikationsnummer
- steuernummer
- tax id
- identificação de imposto não
- número de identificação fiscal
- tax no #
- tax no
- número de imposto
- número de registro fiscal
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- id de estanho
- tin no
- tin #
- zinn #
- zinn
- zinnnummer


## <a name="germany-value-added-tax-number"></a>Número de imposto adicionado ao valor da Alemanha
Esse tipo de informação confidenciais só está disponível para uso em:
- políticas de prevenção contra perda de dados
- políticas de conformidade de comunicação
- governança de informações
- gerenciamento de registros
- Segurança do aplicativo na nuvem da Microsoft

### <a name="format"></a>Formatar

Padrão alfanumérico de 11 caracteres

### <a name="pattern"></a>Padrão

Padrão alfanumérico de 11 caracteres:

- uma letra D ou d
- uma letra E ou e
- um espaço opcional
- três dígitos
- um espaço opcional ou vírgula
- três dígitos
- um espaço opcional ou vírgula
- três dígitos

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_germany_value_added_tax_number encontra conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keywords_germany_value_added_tax_number é encontrada.

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_germany_value_added_tax_number encontra conteúdo que corresponde ao padrão.

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

- número de iva
- vat no
- vat #
- vat# mehrwertsteuer
- mwst
- mehrwertsteuer identifikationsnummer
- nummer mehrwertsteuer


## <a name="greece-drivers-license-number"></a>Número da carteira de motorista da Grécia

Essa entidade está incluída no tipo de informação confidenciais do Número de Licença de Motorista da UE. Ele também está disponível como uma entidade de tipo de informação independente e confidenciais.

### <a name="format"></a>Formatar

nove dígitos sem espaços e delimitadores

### <a name="pattern"></a>Padrão

nove dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_greece_eu_driver's_license_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave  `Keywords_eu_driver's_license_number` de ou `Keywords_greece_eu_driver's_license_number` é encontrada.

```xml
      <!-- Greece Driver's License Number -->
      <Entity id="7a2200b5-aacf-4e3c-ab36-136d3e68b7da" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_greece_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver'lic
- lics do driver
- driver'license
- driver'licenses
- driver'licence
- driver 'licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- lic do driver
- lics do driver
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver'lic #
- lics do driver #
- driver'license #
- driver'licenses #
- driver'licence #
- driver 'licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- lic do driver #
- lics do driver #
- carteira de motorista #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving licence
- dlno #
- driv lic
- licencia de driv
- licença de driv
- licenças de driv
- driv licence
- licenças de driv
- driver licen
- drivers licen
- licenciador do driver
- lic de direção
- driving licen
- conduzir licenças
- driving licence
- driving licences
- permissão de direção
- dl no
- dlno
- dl number


#### <a name="keywords_greece_eu_drivers_license_number"></a>Keywords_greece_eu_driver s_license_number

- δεια οδήγησης
- Adeia odigisis
- Άδεια οδήγησης
- Δίπλωμα οδήγησης


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

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular Regex_greece_id_card encontra conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_greece_id_card é encontrada.

Uma política de DLP tem baixa confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular Regex_greece_id_card encontra conteúdo que corresponde ao padrão.

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

- id grego
- id nacional grego
- cartão de ID pessoal grego
- id da polícia grega
- cartão de identidade
- tautotita
- ταυτότητα
- ταυτότητας


## <a name="greece-passport-number"></a>Número do passaporte grego

### <a name="format"></a>Formatar

Duas letras seguidas por sete dígitos sem espaços ou delimitadores

### <a name="pattern"></a>Padrão

Duas letras seguidas por sete dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_greece_eu_passport_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave  `Keywords_eu_passport_number` de ou `Keywords_greece_eu_passport_number` é encontrada.
- A expressão regular localiza a data no `Regex_greece_eu_passport_date` formato DD MMM YY (Exemplo - 28 de agosto de 19) ou uma palavra-chave de `Keywords_greece_eu_passport_date` é encontrada

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_greece_eu_passport_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave  `Keywords_eu_passport_number` de ou `Keywords_greece_eu_passport_number` é encontrada.

```xml
      <!-- Greece Passport Number -->
      <Entity id="7e65eb47-cdf9-4f52-8f90-2a27d5ee67e3" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_greece_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_greece_eu_passport_date" />
            <Match idRef="Keywords_greece_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_greece_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- números do passport

#### <a name="keywords_greece_eu_passport_number"></a>Keywords_greece_eu_passport_number

- αριθμός διαβατηρίου
- αριθμούς διαβατηρίου
- αριθμός διαβατηριο


## <a name="greece-social-security-number-amka"></a>Número de Segurança Social da Grécia (AMKA)
Esse tipo de informação confidenciais só está disponível para uso em:
- políticas de prevenção contra perda de dados
- políticas de conformidade de comunicação
- governança de informações
- gerenciamento de registros
- Segurança do aplicativo na nuvem da Microsoft

### <a name="format"></a>Formatar

11 dígitos sem espaços e delimitadores

### <a name="pattern"></a>Padrão

- Seis dígitos como data de nascimento YYMMDD
- Quatro dígitos
- um dígito de verificação

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_greece_eu_ssn` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de  `Keywords_greece_eu_ssn_or_equivalent` é encontrada.

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_greece_eu_ssn` localiza conteúdo que corresponde ao padrão.

```xml
      <!-- Greece Social Security Number (AMKA) -->
      <Entity id="e39b03f4-50ea-41ae-af7a-a4b9539596ad" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_greece_eu_ssn" />
          <Match idRef="Keywords_greece_eu_ssn_or_equivalent" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_greece_eu_ssn" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_greece_eu_ssn_or_equivalent"></a>Keywords_greece_eu_ssn_or_equivalent

- ssn
- ssn #
- social security no
- socialsecurityno #
- social security number
- amka
- a.m.k.a.
- Αριθμού Μητρώου Κοινωνικής Ασφάλισης


## <a name="greece-tax-identification-number"></a>Número de identificação fiscal da Grécia
Esse tipo de informação confidenciais só está disponível para uso em:
- políticas de prevenção contra perda de dados
- políticas de conformidade de comunicação
- governança de informações
- gerenciamento de registros
- Segurança do aplicativo na nuvem da Microsoft

### <a name="format"></a>Formatar

Nove dígitos sem espaços e delimitadores

### <a name="pattern"></a>Padrão

Nove dígitos

### <a name="checksum"></a>Soma de verificação

Não se aplica

### <a name="definition"></a>Definição

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:

- A expressão regular  `Regex_greece_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de  `Keywords_greece_eu_tax_file_number` é encontrada.

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

- afm #
- afm
- aφμ|aφμ αριθμός
- aφμ
- tax id
- identificação de imposto não
- número de identificação fiscal
- tax no #
- tax no
- número de imposto
- número de registro fiscal
- tax registry no
- número do registro fiscal
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- taxregistryno #
- id de estanho
- tin no
- tin #
- αριθμός φορολογικού μητρώου
- τον αριθμό φορολογικού μητρώου
- φορολογικού μητρώου νο


## <a name="hong-kong-identity-card-hkid-number"></a>Número do cartão de identidade de Hong Kong (HKID)

### <a name="format"></a>Formatar

Combinação de 8 a 9 letras e números mais parênteses opcionais ao redor do caractere final

### <a name="pattern"></a>Padrão

Combinação de 8 a 9 letras:
- 1-2 letras (não sensíveis a maiúsculas e minúsculas)
- Seis dígitos
- O caractere final (qualquer dígito ou a letra A), que é o dígito de verificação e é opcionalmente colocado entre parênteses.

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_hong_kong_id_card localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_hong_kong_id_card é encontrada.
- A soma de verificação passa.

Uma política de DLP tem baixa confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_hong_kong_id_card localiza conteúdo que corresponde ao padrão.
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
- cartão de identidade de hong kong
- HKIDC
- id card
- cartão de identidade
- cartão de identidade hk
- id de hong kong
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


## <a name="hungary-drivers-license-number"></a>Número da carteira de motorista da Hungria

### <a name="format"></a>Formatar

Duas letras seguidas por seis dígitos

### <a name="pattern"></a>Padrão

Duas letras e seis dígitos:

- Duas letras (não sensíveis a maiúsculas e minúsculas)
- Seis dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:

- A expressão regular  `Regex_hungary_eu_driver's_license_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave  `Keywords_eu_driver's_license_number` de ou `Keywords_hungary_eu_driver's_license_number` é encontrada.

```xml
      <Entity id="9d31c46b-6e6b-444c-aeb1-6dd7e604bb24" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_hungary_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver'lic
- lics do driver
- driver'license
- driver'licenses
- driver'licence
- driver 'licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- lic do driver
- lics do driver
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver'lic #
- lics do driver #
- driver'license #
- driver'licenses #
- driver'licence #
- driver 'licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- lic do driver #
- lics do driver #
- carteira de motorista #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving licence
- dlno #
- driv lic
- licencia de driv
- licença de driv
- licenças de driv
- driv licence
- licenças de driv
- driver licen
- drivers licen
- licenciador do driver
- lic de direção
- driving licen
- conduzir licenças
- driving licence
- driving licences
- permissão de direção
- dl no
- dlno
- dl number


#### <a name="keywords_hungary_eu_drivers_license_number"></a>Keywords_hungary_eu_driver s_license_number

- vezetoi engedely
- vezetői engedély
- vezetői engedélyek


## <a name="hungary-personal-identification-number"></a>Número de identificação pessoal da Hungria
Esse tipo de informação confidenciais só está disponível para uso em:
- políticas de prevenção contra perda de dados
- políticas de conformidade de comunicação
- governança de informações
- gerenciamento de registros
- Segurança do aplicativo na nuvem da Microsoft

### <a name="format"></a>Formatar

11 dígitos

### <a name="pattern"></a>Padrão

11 dígitos:

- Um dígito que corresponde ao sexo, 1 para o sexo masculino, 2 para o sexo feminino. Outros números também são possíveis para cidadãos nascidos antes de 1900 ou cidadãos com dupla cidadania.
- Seis dígitos que correspondem à data de nascimento (YYMMDD)
- Três dígitos que correspondem a um número de série
- Um dígito de verificação

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:

- A função  `Func_hungary_eu_national_id_card` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de  `Keywords_hungary_eu_national_id_card` é encontrada.

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:

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

- número de id
- identification number
- sz ig
- sz. ig.
- sz.ig.
- személyazonosító igazolvány
- személyi igazolvány


## <a name="hungary-passport-number"></a>Número do passaporte húngaro

### <a name="format"></a>Formatar

Duas letras seguidas por seis ou sete dígitos sem espaços ou delimitadores

### <a name="pattern"></a>Padrão

Duas letras seguidas por seis ou sete dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_hungary_eu_passport_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave  `Keywords_eu_passport_number` de ou `Keywords_hungary_eu_passport_number` é encontrada.
- A expressão regular localiza a data no formato `Regex_hungary_eu_passport_date` DD MMM/MMM YY (Exemplo - 01 MÁR/MAR 12) ou uma palavra-chave de `Keywords_eu_passport_date` é encontrada

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_hungary_eu_passport_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave  `Keywords_eu_passport_number` de ou `Keywords_hungary_eu_passport_number` é encontrada.

```xml
      <!-- Hungary Passport Number -->
      <Entity id="5b483910-9aa7-4c99-9917-f4001464bda7" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_hungary_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_hungary_eu_passport_date" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_hungary_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```
### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- números do passport

#### <a name="keywords_hungary_eu_passport_number"></a>Keywords_hungary_eu_passport_number

- útlevél száma
- Útlevelek száma
- útlevél szám

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- data de emissão
- data de expiração


## <a name="hungary-social-security-number-taj"></a>Número de segurança social da Hungria (TAD)

### <a name="format"></a>Formatar

Nove dígitos sem espaços e delimitadores

### <a name="pattern"></a>Padrão

Nove dígitos

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:

- A função  `Func_hungary_eu_ssn_or_equivalent` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de  `Keywords_hungary_eu_ssn_or_equivalent` é encontrada.

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:

- A função  `Func_hungary_eu_ssn_or_equivalent` localiza conteúdo que corresponde ao padrão.

```xml
      <!-- Hungarian Social Security Number (TAJ) -->
      <Entity id="0de78315-9537-47f5-95ab-b3e77eba3993" patternsProximity="300" recommendedConfidence="85">
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

- número de segurança social húngaro
- social security number
- socialsecuritynumber #
- hssn #
- socialsecuritynno
- hssn
- tadji
- tadji #
- ssn
- ssn #
- social security no
- áfa
- közösségi adószám
- általános forgalmi adó szám
- hozzáadottérték adó
- áfa szám
- magyar áfa szám


## <a name="hungary-tax-identification-number"></a>Número de identificação fiscal da Hungria
Esse tipo de informação confidenciais só está disponível para uso em:
- políticas de prevenção contra perda de dados
- políticas de conformidade de comunicação
- governança de informações
- gerenciamento de registros
- Segurança do aplicativo na nuvem da Microsoft

### <a name="format"></a>Formatar

10 dígitos sem espaços ou delimitadores

### <a name="pattern"></a>Padrão

10 dígitos:

- Um dígito que deve ser "8"
- Oito dígitos
- Um dígito de verificação

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:

- A função  `Func_hungary_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de  `Keywords_hungary_eu_tax_file_number` é encontrada.

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:

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

- adóazonosító szám
- adóhatóság szám
- adószám
- tin húngaro
- hungatiantin #
- autoridade fiscal não
- tax id
- identificação de imposto não
- número de identificação fiscal
- tax no #
- tax no
- número de imposto
- número de registro fiscal
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- id de estanho
- tin no
- tin #
- número de iva


## <a name="hungary-value-added-tax-number"></a>Número de imposto adicionado ao valor húngaro
Esse tipo de informação confidenciais só está disponível para uso em:
- políticas de prevenção contra perda de dados
- políticas de conformidade de comunicação
- governança de informações
- gerenciamento de registros
- Segurança do aplicativo na nuvem da Microsoft

### <a name="format"></a>Formatar

Padrão alfanumérico de 10 caracteres

### <a name="pattern"></a>Padrão

Padrão alfanumérico de 10 caracteres:

- duas letras - HU ou hu
- espaço opcional
- oito dígitos

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:

- A função Func_hungarian_value_added_tax_number encontra conteúdo que corresponde ao padrão.
- Uma palavra-chave Keywords_hungarian_value_added_tax_number é encontrada.

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:

- A função Func_hungarian_value_added_tax_number encontra conteúdo que corresponde ao padrão.

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

- vat
- valor adicionado número de imposto
- vat #
- vatno #
- húngarovatno #
- tax no.
- value added tax áfa
- közösségi adószám
- általános forgalmi adó szám
- hozzáadottérték adó
- áfa szám


## <a name="india-permanent-account-number-pan"></a>Número da conta permanente da Índia (PAN)

### <a name="format"></a>Formatar

10 letras ou dígitos

### <a name="pattern"></a>Padrão

10 letras ou dígitos.
- Três letras (não sensíveis a maiúsculas e minúsculas)
- Uma letra em C, P, H, F, A, T, B, L, J, G (não sensível a minúsculas)
- Uma carta
- Quatro dígitos
- Uma letra que é um dígito de verificação alfabética

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular Regex_india_permanent_account_number encontra conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_india_permanent_account_number é encontrada.

Uma política de DLP tem baixa confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular Regex_india_permanent_account_number encontra conteúdo que corresponde ao padrão.


```xml
      <!-- India Permanent Account Number -->
      <Entity id="2602bfee-9bb0-47a5-a7a6-2bf3053e2804" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_india_permanent_account_number" />
          <Match idRef="Keyword_india_permanent_account_number" />
        </Pattern>
        <Version minEngineVersion="15.20.3520.000">
          <Pattern confidenceLevel="65">
            <IdMatch idRef="Regex_india_permanent_account_number" />
          </Pattern>
        </Version>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_india_permanent_account_number"></a>Keyword_india_permanent_account_number

- Número da Conta Permanente
- PAN

## <a name="india-unique-identification-aadhaar-number"></a>Número de identificação exclusiva da Índia (Aadhaar)

### <a name="format"></a>Formatar

12 dígitos contendo espaços opcionais ou traços

### <a name="pattern"></a>Padrão

12 dígitos:
- Um dígito que não é 0 ou 1
- Três dígitos
- Um espaço ou um traço opcional 
- Quatro dígitos
- Um espaço ou um traço opcional 
- O dígito final, que é o dígito de verificação

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_india_aadhaar encontra conteúdo que corresponde ao padrão.
- Uma palavra-chave Keyword_india_aadhar é encontrada.
- A soma de verificação passa.
-
Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:

- A função Func_india_aadhaar encontra conteúdo que corresponde ao padrão.
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
- aadhaar
- aadhar
- aadhar #
- uid
- आधार
- uidai

## <a name="indonesia-identity-card-ktp-number"></a>Número de cartão de identidade da Indonésia (KTP)

### <a name="format"></a>Formatar

16 dígitos contendo pontos opcionais

### <a name="pattern"></a>Padrão

16 dígitos:
- Código de província de dois dígitos 
- Um ponto (opcional) 
- Código de dois dígitos da regência ou da cidade 
- Código de dois dígitos do subdistrito 
- Um ponto (opcional) 
- Seis dígitos no formato DDMMYYY, que são a data de nascimento
- Um ponto (opcional) 
- Quatro dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:

- A expressão regular Regex_indonesia_id_card encontra conteúdo que corresponde ao padrão.
- Uma palavra-chave Keyword_indonesia_id_card é encontrada.

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

Código de país (duas letras) mais dígitos de verificação (dois dígitos) mais número bban (até 30 caracteres)

### <a name="pattern"></a>Padrão

O padrão deve incluir todos os seguintes itens:

- Código de país de duas letras
- Dois dígitos de verificação (seguidos de um espaço opcional)
- 1 a 7 grupos de quatro letras ou dígitos (podem ser separados por espaços)
- 1 a 3 letras ou dígitos

O formato para cada país é ligeiramente diferente. O tipo de informação confidenciais do IBAN abrange esses 60 países:

- ad
- ae
- al
- at
- az
- ba
- be
- bg
- bh
- ch
- cr
- cy
- cz
- de
- dk
- do
- ee
- sd
- fi
- fo
- fr
- gb
- ge
- gi
- gl
- gr
- hr
- hu
- ie
- il
- é
- it
- kw
- kz
- lb
- li
- lt
- lu
- lv
- mc
- md
- me
- mk
- mr
- mt
- mu
- nl
- não
- pl
- pt
- ro
- rs
- sa
- se
- si
- sk
- sm
- tn
- tr
- vg

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:

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

Nenhuma


## <a name="international-classification-of-diseases-icd-10-cm"></a>Classificação internacional de doença (ICD-10-CM)

### <a name="format"></a>Formatar

Dictionary

### <a name="pattern"></a>Padrão

Palavra-chave

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- Uma palavra-chave de Dictionary_icd_10_updated é encontrada.
- Uma palavra-chave de Dictionary_icd_10_codes é encontrada.

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- Uma palavra-chave Dictionary_icd_10_ atualizada é encontrada.

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

Qualquer termo do dicionário Dictionary_icd_10_updated palavra-chave, que se baseia na Classificação Internacional de Doença, Décima Revisão, Modificação Clínica [(ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604). Esse tipo procura apenas o termo, não os códigos de seguro.

Qualquer termo do dicionário Dictionary_icd_10_codes palavra-chave, que se baseia na Classificação Internacional de Doença, Décima Revisão, Modificação Clínica [(ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604). Esse tipo procura apenas códigos de seguro, não a descrição.

## <a name="international-classification-of-diseases-icd-9-cm"></a>Classificação internacional de doença (ICD-9-CM)

### <a name="format"></a>Formatar

Dictionary

### <a name="pattern"></a>Padrão

Palavra-chave

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- Uma palavra-chave de Dictionary_icd_9_updated é encontrada.
- Uma palavra-chave de Dictionary_icd_9_codes é encontrada.

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- Uma palavra-chave de Dictionary_icd_9_updated é encontrada.

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

Qualquer termo do dicionário Dictionary_icd_9_updated palavra-chave, que se baseia na Classificação Internacional de Doença, Nona Revisão, Modificação Clínica [(ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605). Esse tipo procura apenas o termo, não os códigos de seguro.

Qualquer termo do dicionário Dictionary_icd_9_codes palavra-chave, que se baseia na Classificação Internacional de Doença, Nona Revisão, Modificação Clínica [(ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605). Esse tipo procura apenas códigos de seguro, não a descrição.

## <a name="ip-address"></a>Endereço IP

### <a name="format"></a>Formatar

#### <a name="ipv4"></a>IPv4:
Padrão complexo que responde por versões formatadas (períodos) e não formatadas (sem períodos) dos endereços IPv4

#### <a name="ipv6"></a>IPv6:
Padrão complexo que representa números IPv6 formatados (que incluem dois pontos)

### <a name="pattern"></a>Padrão

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Para IPv6, uma política de DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular Regex_ipv6_address localiza o conteúdo que corresponde ao padrão.
- Nenhuma palavra-chave de Keyword_ipaddress for encontrada.

Para IPv4, uma política de DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular Regex_ipv4_address localiza o conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_ipaddress for encontrada.

Para IPv6, uma política de DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
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

- IP (essa palavra-chave é sensível a minúsculas)
- ip address
- endereços ip
- internet protocol
- IP כתובת ה

## <a name="ireland-drivers-license-number"></a>Número da carteira de motorista da Irlanda

### <a name="format"></a>Formatar

Seis dígitos seguidos por quatro letras

### <a name="pattern"></a>Padrão

Seis dígitos e quatro letras:

- Seis dígitos
- Quatro letras (não sensíveis a maiúsculas e minúsculas)

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:

- A expressão regular  `Regex_ireland_eu_driver's_license_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave  `Keywords_eu_driver's_license_number` de ou `Keywords_ireland_eu_driver's_license_number` é encontrada.

```xml
      <!-- Ireland Driver's License Number -->
      <Entity id="e01bccd9-eb4d-414f-ace1-e9b6a4c4a2ca" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_ireland_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver'lic
- lics do driver
- driver'license
- driver'licenses
- driver'licence
- driver 'licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- lic do driver
- lics do driver
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver'lic #
- lics do driver #
- driver'license #
- driver'licenses #
- driver'licence #
- driver 'licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- lic do driver #
- lics do driver #
- carteira de motorista #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving licence
- dlno #
- driv lic
- licencia de driv
- licença de driv
- licenças de driv
- driv licence
- licenças de driv
- driver licen
- drivers licen
- licenciador do driver
- lic de direção
- driving licen
- conduzir licenças
- driving licence
- driving licences
- permissão de direção
- dl no
- dlno
- dl number


#### <a name="keywords_ireland_eu_drivers_license_number"></a>Keywords_ireland_eu_driver s_license_number

- ceadúnas tiomána
- ceadúnais tiomána

## <a name="ireland-passport-number"></a>Número do passaporte da Irlanda

### <a name="format"></a>Formatar

Duas letras ou dígitos seguidos por sete dígitos sem espaços ou delimitadores

### <a name="pattern"></a>Padrão

Duas letras ou dígitos seguidos por sete dígitos:

- Dois dígitos ou letras (não sensíveis a maiúsculas e minúsculas)
- Sete dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_ireland_eu_passport_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave  `Keywords_eu_passport_number` de ou `Keywords_ireland_eu_passport_number` é encontrada.
- A expressão regular localiza a data no formato `Regex_ireland_eu_passport_date` DD MMM/MMM YYYY (Exemplo - 01 BEA/MAIO de 1988) ou uma palavra-chave de é `Keywords_eu_passport_date` encontrada

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_ireland_eu_passport_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave  `Keywords_eu_passport_number` de ou `Keywords_ireland_eu_passport_number` é encontrada.

```xml
      <!-- Ireland Passport Number -->
      <Entity id="a2130f27-9ee2-4103-84f9-a6b1ee7d0cbf" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_ireland_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_ireland_eu_passport_date" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_ireland_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- números do passport

#### <a name="keywords_ireland_eu_passport_number"></a>Keywords_ireland_eu_passport_number

- passeport numero
- uimhreacha pasana
- uimhir pas
- uimhir phas
- uimhreacha pas
- uimhir cárta
- uimhir chárta

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- data de emissão
- data de expiração


## <a name="ireland-personal-public-service-pps-number"></a>Número pps (serviço público pessoal) da Irlanda

### <a name="format"></a>Formatar

Formato antigo (até 31 de dezembro de 2012):
- sete dígitos seguidos de 1 a 2 letras

Novo formato (1º de janeiro de 2013 e depois):
- sete dígitos seguidos por duas letras

### <a name="pattern"></a>Padrão

Formato antigo (até 31 de dezembro de 2012):
- sete dígitos
- uma a duas letras (sem maiúsculas e minúsculas)

Novo formato (1º de janeiro de 2013 e depois):
- sete dígitos
- uma letra (não sensível a minúsculas) que é um dígito de verificação alfabética
- Uma letra opcional no intervalo A-I ou "W"

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_ireland_pps encontra conteúdo que corresponde ao padrão.
- Uma palavra-chave Keywords_ireland_eu_national_id_card é encontrada.
- A soma de verificação passa.

Uma política de DLP tem baixa confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_ireland_pps encontra conteúdo que corresponde ao padrão.
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
- número de ID pessoal
- número de serviço público pessoal
- serviço pessoal não
- phearsanta seirbhíse poiblí
- pps no
- pps number
- pps num
- pps service no
- ppsn
- ppsno #
- ppsno
- psp
- serviço público não
- publicserviceno #
- publicserviceno
- receita e número do seguro social
- rsi no
- número rsi
- rsin
- cliente seirbhís aitheantais
- uimh
- uimhir aitheantais chánach
- uimhir aitheantais phearsanta
- uimhir phearsanta seirbhíse poiblí
- tax id
- identificação de imposto não
- número de identificação fiscal
- tax no #
- tax no
- número de imposto
- número de registro fiscal
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- id de estanho
- tin no
- tin #


## <a name="israel-bank-account-number"></a>Número da conta bancária de Israel

### <a name="format"></a>Formatar

13 dígitos

### <a name="pattern"></a>Padrão

Formatado:
- dois dígitos
- um traço
- três dígitos
- um traço
- oito dígitos

Não formatado:
- 13 dígitos consecutivos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
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

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
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

-   מספר זהות
-   מספר זיה וי
-   מספר זיהוי ישר אלי      
-   זהותישר אלית
-   هو ية اسرائيل ية عدد
-   هوية إسرائ يلية
-   رقم الهوية
-   عدد هوية فريدة من نوعها
-   idnumber #
-   número de id
-   identity no        
-   identitynumber #
-   número de identidade
-   israelidentitynumber       
-   id pessoal
-   id exclusiva  


## <a name="italy-drivers-license-number"></a>Número da carteira de motorista da Itália

Essa entidade de tipo está incluída no tipo de informação confidenciais número de licença de driver da UE. Ele também está disponível como uma entidade de tipo de informação independente e confidenciais.

### <a name="format"></a>Formatar

uma combinação de 10 letras e dígitos

### <a name="pattern"></a>Padrão

uma combinação de 10 letras e dígitos:
- uma letra (não sensível a minúsculas)
- a letra "A" ou "V" (não sensitivo para minúsculas)
- sete dígitos
- uma letra (não sensível a minúsculas)

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular `Regex_italy_drivers_license_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave `Keywords_eu_driver's_license_number` de ou `Keyword_italy_drivers_license_number` é encontrada.

```xml
    <!-- Italy Driver's license Number -->
    <Entity id="97d6244f-9157-41bd-8e0c-9d669a5c4d71" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_italy_drivers_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keyword_italy_drivers_license_number" />
          </Any>
        </Pattern>
    </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver'lic
- lics do driver
- driver'license
- driver'licenses
- driver'licence
- driver 'licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- lic do driver
- lics do driver
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver'lic #
- lics do driver #
- driver'license #
- driver'licenses #
- driver'licence #
- driver 'licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- lic do driver #
- lics do driver #
- carteira de motorista #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving licence
- dlno #
- driv lic
- licencia de driv
- licença de driv
- licenças de driv
- driv licence
- licenças de driv
- driver licen
- drivers licen
- licenciador do driver
- lic de direção
- driving licen
- conduzir licenças
- driving licence
- driving licences
- permissão de direção
- dl no
- dlno
- dl number

#### <a name="keyword_italy_drivers_license_number"></a>Keyword_italy_drivers_license_number

- numero di patente
- patente di guida
- patente guida
- patenti di guida
- patenti guida


## <a name="italy-fiscal-code"></a>Código fiscal da Itália
Esse tipo de informação confidenciais só está disponível para uso em:
- políticas de prevenção contra perda de dados
- políticas de conformidade de comunicação
- governança de informações
- gerenciamento de registros
- Segurança do aplicativo na nuvem da Microsoft

### <a name="format"></a>Formatar

uma combinação de 16 caracteres de letras e dígitos no padrão especificado

### <a name="pattern"></a>Padrão

Uma combinação de 16 caracteres de letras e dígitos:
- três letras que correspondem às três primeiras consoantes no nome da família
- três letras que correspondem à primeira, terceira e quarta consoantes no primeiro nome
- dois dígitos que correspondem aos últimos dígitos do ano de nascimento
- uma letra que corresponde à letra do mês de nascimento: as letras são usadas em ordem alfabética, mas apenas as letras A a E, H, L, M, P, R a T são usadas (portanto, janeiro é A e outubro é R)
- dois dígitos que correspondem ao dia do mês de nascimento para diferenciar entre os sexos, 40 é adicionado ao dia de nascimento para as mulheres
- quatro dígitos que correspondem ao código de área específico do município em que a pessoa nasceu (códigos em todo o país são usados para países estrangeiros)
- um dígito de paridade

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_italy_eu_national_id_card` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de  `Keywords_italy_eu_national_id_card` é encontrada.

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
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

- codice fiscal
- codice fiscale
- id de códice personale
- codice personale
- código fiscal
- numero certificato personale
- numero di identificazione fiscale
- numero id personale
- numero personale
- número de certificado pessoal
- código pessoal
- código de id pessoal
- número de ID pessoal
- personalcodeno #
- tax code
- tax id
- identificação de imposto não
- número de identificação fiscal
- número da identidade fiscal
- tax no #
- tax no
- número de imposto
- número de registro fiscal
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- id de estanho
- tin no
- tin #


## <a name="italy-passport-number"></a>Número do passaporte da Itália

### <a name="format"></a>Formatar

duas letras ou dígitos seguidos por sete dígitos sem espaços ou delimitadores

### <a name="pattern"></a>Padrão

duas letras ou dígitos seguidos por sete dígitos:

- dois dígitos ou letras (não sensíveis a maiúsculas e minúsculas)
- sete dígitos

### <a name="checksum"></a>Soma de verificação

não se aplica

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_italy_eu_passport_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave  `Keywords_eu_passport_number` de ou `Keywords_italy_eu_passport_number` é encontrada.
- A expressão regular localiza a data no formato `Regex_italy_eu_passport_date` DD MMM/MMM YYYY (Exemplo - 01 GEN/JAN 1988) ou uma palavra-chave de é `Keywords_eu_passport_date` encontrada

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_italy_eu_passport_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave  `Keywords_eu_passport_number` de ou `Keywords_italy_eu_passport_number` é encontrada.

```xml
      <!-- Italy Passport Number -->
      <Entity id="39811019-4750-445f-b26d-4c0e6c431544" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_italy_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_italy_eu_passport_date" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_italy_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- números do passport

#### <a name="keywords_italy_eu_passport_number"></a>Keywords_italy_eu_passport_number

- italiana passaporto
- passaporto italiano
- passaporto numero
- numéro passeport
- numero di passaporto
- numeri del passaporto
- passeport italien

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- data de emissão
- data de expiração


## <a name="italy-value-added-tax-number"></a>Número de imposto adicionado ao valor da Itália
Esse tipo de informação confidenciais só está disponível para uso em:
- políticas de prevenção contra perda de dados
- políticas de conformidade de comunicação
- governança de informações
- gerenciamento de registros
- Segurança do aplicativo na nuvem da Microsoft

### <a name="format"></a>Formatar

Padrão alfanumérico de 13 caracteres com delimitadores opcionais

### <a name="pattern"></a>Padrão

Padrão alfanumérico de 13 caracteres com delimitadores opcionais:

- I ou i
- T ou t
- espaço opcional, ponto, hífen ou vírgula
- 11 dígitos

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_italy_value_added_tax_number encontra conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keywords_italy_value_added_tax_number é encontrada.

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_italy_value_added_tax_number encontra conteúdo que corresponde ao padrão.

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

- número de iva
- vat no
- vat #
- iva
- iva #


## <a name="japan-bank-account-number"></a>Número da conta bancária do Japão

### <a name="format"></a>Formatar

sete ou oito dígitos

### <a name="pattern"></a>Padrão

número da conta bancária:
- sete ou oito dígitos
- código de filial de conta bancária:
- quatro dígitos
- um espaço ou traço (opcional)
- três dígitos

Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_jp_bank_account localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_jp_bank_account for encontrada.
- Uma das seguintes opções for verdadeira:
- A função Func_jp_bank_account_branch_code localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_jp_bank_branch_code for encontrada.

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
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
- 口座番号
- 銀行口座
- 銀行口座番号
- 総合口座
- 普通預金口座
- 普通口座
- 当座預金口座
- 当座口座
- 預金口座
- 振替口座
- 銀行
- バンク

#### <a name="keyword_jp_bank_branch_code"></a>Keyword_jp_bank_branch_code

- 支店番号
- 支店コード
- 店番号

## <a name="japan-drivers-license-number"></a>Número da carteira de motorista do Japão

### <a name="format"></a>Formatar

12 dígitos

### <a name="pattern"></a>Padrão

12 dígitos consecutivos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
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

- driverlicense
- driverslicense
- driver'slicense
- driverslicenses
- driver'slicenses
- driverlicenses
- dl #
- dls #
- lic #
- lics #
- 運転免許証
- 運転免許
- 免許証
- 免許
- 運転免許証番号
- 運転免許番号
- 免許証番号
- 免許番号
- 運転免許証ナンバー
- 運転免許ナンバー
- 免許証ナンバー
- 運転免許証no
- 運転免許no
- 免許証no
- 免許no
- 運転経歴証明書番号
- 運転経歴証明書
- 運転免許証No.
- 運転免許No.
- 免許証No.
- 免許No.
- 運転免許証 #
- 運転免許 #
- 免許証 #
- 免許 #


## <a name="japan-my-number---corporate"></a>Japão Meu Número - Corporativo
Esse tipo de informação confidenciais só está disponível para uso em:
- políticas de prevenção contra perda de dados
- políticas de conformidade de comunicação
- governança de informações
- gerenciamento de registros
- Segurança do aplicativo na nuvem da Microsoft

### <a name="format"></a>Formatar

Número de 13 dígitos

### <a name="pattern"></a>Padrão

Número de 13 dígitos:

- um dígito de um a nove
- 12 dígitos

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_japanese_my_number_corporate encontra conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keywords_japanese_my_number_corporate é encontrada.

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_japanese_my_number_corporate encontra conteúdo que corresponde ao padrão.

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


## <a name="japan-my-number---personal"></a>Japão Meu Número - Pessoal
Esse tipo de informação confidenciais só está disponível para uso em:
- políticas de prevenção contra perda de dados
- políticas de conformidade de comunicação
- governança de informações
- gerenciamento de registros
- Segurança do aplicativo na nuvem da Microsoft

### <a name="format"></a>Formatar

Número de 12 dígitos

### <a name="pattern"></a>Padrão

Número de 12 dígitos:

- quatro dígitos
- um espaço opcional, ponto ou hífen
- quatro dígitos
- um espaço opcional, ponto ou hífen
- quatro dígitos

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_japanese_my_number_personal encontra conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keywords_japanese_my_number_personal é encontrada.

Uma política de DLP tem baixa confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_japanese_my_number_personal encontra conteúdo que corresponde ao padrão.

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


## <a name="japan-passport-number"></a>Número do passaporte do Japão

### <a name="format"></a>Formatar

duas letras seguidas por sete dígitos

### <a name="pattern"></a>Padrão

duas letras (não sensíveis a maiúsculas e minúsculas) seguidas por sete dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
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

- Passport
- Passport Number
- Passport No.
- Passport #
- パスポート
- パスポート番号
- パスポートナンバー
- パスポート＃
- パスポート #
- パ ポ トNo.
- 旅券番号
- 旅券番号＃
- 旅券番号♯
- 旅券ナンバー


## <a name="japan-residence-card-number"></a>Número do cartão de residência do Japão

### <a name="format"></a>Formatar

12 letras e dígitos

### <a name="pattern"></a>Padrão

12 letras e dígitos:
- duas letras (não sensíveis a maiúsculas e minúsculas)
- oito dígitos
- duas letras (não sensíveis a maiúsculas e minúsculas)

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular Regex_jp_residence_card_number encontra conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_jp_residence_card_number é encontrada.

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
- Cartão de residência não
- Cartão de residência #
- 在留カード番号
- 在留カード
- 在留番号

## <a name="japan-resident-registration-number"></a>Número de registro de residente no Japão

### <a name="format"></a>Formatar

11 dígitos

### <a name="pattern"></a>Padrão

11 dígitos consecutivos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
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
- Residents Basic Registry Number
- Resident Registration No.
- Resident Register No.
- Residents Basic Registry No.
- Basic Resident Register No.
- 外国人登録証明書番号
- 証明書番号
- 登録番号
- 外国人登録証


## <a name="japan-social-insurance-number-sin"></a>Número de seguro social do Japão (SIN)

### <a name="format"></a>Formatar

7 a 12 dígitos

### <a name="pattern"></a>Padrão

7 a 12 dígitos:
- quatro dígitos
- um hífen (opcional)
- OR de seis dígitos
- 7 a 12 dígitos consecutivos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_jp_sin localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_jp_sin for encontrada.

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
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
- 健康保険被保険者番号
- 健保番号
- 基礎年金番号
- 雇用保険被保険者番号
- 雇用保険番号
- 保険証番号
- 社会保険番号
- 社会保険No.
- 社会保険
- 介護保険
- 介護保険被保険者番号
- 健康保険被保険者整理番号
- 雇用保険被保険者整理番号
- 厚生年金
- 厚生年金被保険者整理番号


## <a name="latvia-drivers-license-number"></a>Número da carteira de motorista da Letônia

### <a name="format"></a>Formatar

três letras seguidas por seis dígitos

### <a name="pattern"></a>Padrão

três letras e seis dígitos:

- três letras (não sensíveis a maiúsculas e minúsculas)
- seis dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_latvia_eu_driver's_license_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave  `Keywords_eu_driver's_license_number` de ou `Keywords_latvia_eu_driver's_license_number` é encontrada.

```xml
      <!-- Latvia Driver's License Number -->
      <Entity id="ec996de0-30f2-46b1-b192-4d2ff8805fa7" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_latvia_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver'lic
- lics do driver
- driver'license
- driver'licenses
- driver'licence
- driver 'licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- lic do driver
- lics do driver
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver'lic #
- lics do driver #
- driver'license #
- driver'licenses #
- driver'licence #
- driver 'licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- lic do driver #
- lics do driver #
- carteira de motorista #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving licence
- dlno #
- driv lic
- licencia de driv
- licença de driv
- licenças de driv
- driv licence
- licenças de driv
- driver licen
- drivers licen
- licenciador do driver
- lic de direção
- driving licen
- conduzir licenças
- driving licence
- driving licences
- permissão de direção
- dl no
- dlno
- dl number


#### <a name="keywords_latvia_eu_drivers_license_number"></a>Keywords_latvia_eu_driver s_license_number

- autovadītāja apliecība
- autovadītāja apliecības
- vadītāja apliecība

## <a name="latvia-personal-code"></a>Código pessoal da Letônia

### <a name="format"></a>Formatar

11 dígitos e um hífen opcional

### <a name="pattern"></a>Padrão

Formato antigo

11 dígitos e um hífen:

- seis dígitos que correspondem à data de nascimento (DDMMYYY)
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

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_latvia_eu_national_id_card` ou o regex `Regex_latvia_eu_national_id_card_new_format` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de  `Keywords_latvia_eu_national_id_card` é encontrada.

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_latvia_eu_national_id_card` ou o regex `Regex_latvia_eu_national_id_card_new_format` localiza conteúdo que corresponde ao padrão.

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
- alvas nē
- número de nascimento
- número do cidadão
- número civil
- número do censo eletrônico
- número eletrônico
- código fiscal
- número do usuário de saúde
- id #
- id-code
- identification number
- numurs identifikācijas
- id-number
- número individual
- latvija alva
- nacionālais id
- national id
- número de identificação nacional
- número de identidade nacional
- national insurance number
- número do registro nacional
- nodokļa numurs
- nodokļu id
- nodokļu identifikācija numurs
- número de certificado pessoal
- código pessoal
- código de id pessoal
- número de ID pessoal
- código de identificação pessoal
- identificador pessoal
- número de identidade pessoal
- número pessoal
- código numérico pessoal
- personalcodeno #
- personas kods
- código de identificação da população
- número do serviço público
- registration number
- número de receita
- social insurance number
- social security number
- state tax code
- tax file number
- tax id
- identificação de imposto não
- número de identificação fiscal
- tax no #
- tax no
- número de imposto
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- id de estanho
- tin no
- tin #
- número do eleitor

## <a name="latvia-passport-number"></a>Número do passaporte da Letônia

### <a name="format"></a>Formatar

duas letras ou dígitos seguidos por sete dígitos sem espaços ou delimitadores

### <a name="pattern"></a>Padrão

duas letras ou dígitos seguidos por sete dígitos:

- dois dígitos ou letras (não sensíveis a maiúsculas e minúsculas)
- sete dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_latvia_eu_passport_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave  `Keywords_eu_passport_number` de ou `Keywords_latvia_eu_passport_number` é encontrada.
- A expressão regular `Regex_eu_passport_date1` localiza a data no formato DD.MM.YYYY ou uma palavra-chave de é `Keywords_eu_passport_date` encontrada

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_latvia_eu_passport_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave  `Keywords_eu_passport_number` de ou `Keywords_latvia_eu_passport_number` é encontrada.

```xml
      <!-- Latvia Passport Number -->
      <Entity id="23ae25ec-cc28-421b-b77a-3054eadf1ede" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_latvia_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_latvia_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_eu_passport_number_common"></a>Keywords_eu_passport_number_common

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- números do passport

#### <a name="keywords_latvia_eu_passport_number"></a>Keywords_latvia_eu_passport_number

- pase numurs
- pase numur
- pases numuri
- pases nr
- passeport no
- n° du Passeport

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- data de emissão
- data de expiração


## <a name="lithuania-drivers-license-number"></a>Número da carteira de motorista da Lituânia

### <a name="format"></a>Formatar

oito dígitos sem espaços e delimitadores

### <a name="pattern"></a>Padrão

oito dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_lithuania_eu_driver's_license_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave  `Keywords_eu_driver's_license_number` de ou `Keywords_lithuania_eu_driver's_license_number` é encontrada.

```xml
      <!-- Lithuania Driver's License Number -->
      <Entity id="86f7628b-e0f4-4dc3-9fbc-e4300e4c7d78" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver'lic
- lics do driver
- driver'license
- driver'licenses
- driver'licence
- driver 'licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- lic do driver
- lics do driver
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver'lic #
- lics do driver #
- driver'license #
- driver'licenses #
- driver'licence #
- driver 'licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- lic do driver #
- lics do driver #
- carteira de motorista #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving licence
- dlno #
- driv lic
- licencia de driv
- licença de driv
- licenças de driv
- driv licence
- licenças de driv
- driver licen
- drivers licen
- licenciador do driver
- lic de direção
- driving licen
- conduzir licenças
- driving licence
- driving licences
- permissão de direção
- dl no
- dlno
- dl number


#### <a name="keywords_lithuania_eu_drivers_license_number"></a>Keywords_lithuania_eu_driver s_license_number

- vairuotojo pažymėjimas
- vairuotojo pažymėjimo numeris
- vairuotojo pažymėjimo numeriai

## <a name="lithuania-personal-code"></a>Código pessoal da Lituânia
Esse tipo de informação confidenciais só está disponível para uso em:
- políticas de prevenção contra perda de dados
- políticas de conformidade de comunicação
- governança de informações
- gerenciamento de registros
- Segurança do aplicativo na nuvem da Microsoft

### <a name="format"></a>Formatar

11 dígitos sem espaços e delimitadores

### <a name="pattern"></a>Padrão

11 dígitos sem espaços e delimitadores:

- um dígito (1 a 6) que corresponde ao sexo e ao século de nascimento da pessoa
- seis dígitos que correspondem à data de nascimento (YYMMDD)
- três dígitos que correspondem ao número de série da data de nascimento
- um dígito de verificação

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_lithuania_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de  `Keywords_lithuania_eu_tax_file_number` é encontrada.

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
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

- asmeninis skaitmeninis kodas
- kodas asmens
- número de serviço do cidadão
- mokesčių id
- mokesčių identifikavimas numeris
- mokesčių identifikavimo numeris
- mokesčių numeris
- national identification number
- código pessoal
- código numérico pessoal
- piliečio paslaugos numeris
- tax id
- identificação de imposto não
- número de identificação fiscal
- tax no #
- tax no
- número de imposto
- número de registro fiscal
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- id de estanho
- tin no
- tin #
- unikalus identifikavimo kodas
- unikalus identifikavimo numeris
- número de identificação exclusivo
- número de identidade exclusivo
- uniqueidentityno #

## <a name="lithuania-passport-number"></a>Número do passaporte lituano

### <a name="format"></a>Formatar

oito dígitos ou letras sem espaços ou delimitadores

### <a name="pattern"></a>Padrão

oito dígitos ou letras (não sensíveis a maiúsculas e minúsculas)

### <a name="checksum"></a>Soma de verificação

não se aplica

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_lithuania_eu_passport_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave  `Keywords_eu_passport_number` de ou `Keywords_lithuania_eu_passport_number` é encontrada.
- A expressão regular `Regex_eu_passport_date3` localiza data no formato DD MM YYYY ou uma palavra-chave de é `Keywords_eu_passport_date` encontrada

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_lithuania_eu_passport_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave  `Keywords_eu_passport_number` de ou `Keywords_lithuania_eu_passport_number` é encontrada.

```xml
      <!-- Lithuania Passport Number -->
      <Entity id="1b79900f-047b-4c3f-846f-7d73b5534bce" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_lithuania_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date3" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_lithuania_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- números do passport

#### <a name="keywords_lithuania_eu_passport_number"></a>Keywords_lithuania_eu_passport_number

- numeris de passo a passo
- numeriai de numeriai
- nr de passo a passo

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- data de emissão
- data de expiração


## <a name="luxemburg-drivers-license-number"></a>Número da carteira de motorista de Luxemburgo

### <a name="format"></a>Formatar

seis dígitos sem espaços e delimitadores

### <a name="pattern"></a>Padrão

seis dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_luxemburg_eu_driver's_license_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave  `Keywords_eu_driver's_license_number` de ou `Keywords_luxemburg_eu_driver's_license_number` é encontrada.

```xml
      <!-- Luxemburg Driver's License Number -->
      <Entity id="89daf717-1544-4860-9a2e-fc9166dd8852" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver'lic
- lics do driver
- driver'license
- driver'licenses
- driver'licence
- driver 'licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- lic do driver
- lics do driver
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver'lic #
- lics do driver #
- driver'license #
- driver'licenses #
- driver'licence #
- driver 'licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- lic do driver #
- lics do driver #
- carteira de motorista #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving licence
- dlno #
- driv lic
- licencia de driv
- licença de driv
- licenças de driv
- driv licence
- licenças de driv
- driver licen
- drivers licen
- licenciador do driver
- lic de direção
- driving licen
- conduzir licenças
- driving licence
- driving licences
- permissão de direção
- dl no
- dlno
- dl number


#### <a name="keywords_luxemburg_eu_drivers_license_number"></a>Keywords_luxemburg_eu_driver s_license_number

- fahrerlaubnis
- Führerschäin

## <a name="luxemburg-national-identification-number-natural-persons"></a>Número de identificação nacional de Luxemburgo (pessoas físicas)
Esse tipo de informação confidenciais só está disponível para uso em:
- políticas de prevenção contra perda de dados
- políticas de conformidade de comunicação
- governança de informações
- gerenciamento de registros
- Segurança do aplicativo na nuvem da Microsoft

### <a name="format"></a>Formatar

13 dígitos sem espaços ou delimitadores

### <a name="pattern"></a>Padrão

13 dígitos:

- 11 dígitos
- dois dígitos de verificação

### <a name="checksum"></a>Soma de verificação

sim

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_luxemburg_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de  `Keywords_luxemburg_eu_national_id_card` é encontrada.

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
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

- id eindeutige
- eindeutige id-nummer
- eindeutigeid #
- id personnelle
- idpersonnelle #
- idpersonnelle
- código individual
- id individual
- identificação individual
- identidade individual
- numéro d'identification personnel
- id pessoal
- identificação pessoal
- identidade pessoal
- personalidno #
- personalidnumber #
- persönliche identifikationsnummer
- id exclusiva
- identidade exclusiva
- uniqueidkey #

## <a name="luxemburg-passport-number"></a>Número do passaporte luxemburgues

### <a name="format"></a>Formatar

oito dígitos ou letras sem espaços ou delimitadores

### <a name="pattern"></a>Padrão

oito dígitos ou letras (não sensíveis a maiúsculas e minúsculas)

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_luxemburg_eu_passport_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave  `Keywords_eu_passport_number` de ou `Keywords_luxemburg_eu_passport_number` é encontrada.
- A expressão regular `Regex_eu_passport_date3` localiza data no formato DD MM YYYY ou uma palavra-chave de é `Keywords_eu_passport_date` encontrada

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_luxemburg_eu_passport_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave  `Keywords_eu_passport_number` de ou `Keywords_luxemburg_eu_passport_number` é encontrada.

```xml
      <!-- Luxemburg Passport Number -->
      <Entity id="81d5c027-bed9-4421-91a0-3b2e55b3eb85" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_luxemburg_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_luxemburg_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date3" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_luxemburg_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- números do passport

#### <a name="keywords_luxemburg_eu_passport_number"></a>Keywords_luxemburg_eu_passport_number
- ausweisnummer
- luxemburgues pass
- luxemburgues passeport
- passport luxemburgues
- no passeport
- no-reisepass
- nr-reisepass
- numéro de passeport
- pass net
- passar nr
- passnummer
- passeport nombre
- reisepässe
- reisepass-nr
- reisepassnummer

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- data de emissão
- data de expiração


## <a name="luxemburg-national-identification-number-non-natural-persons"></a>Número de identificação nacional de Luxemburgo (pessoas não naturais)

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

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_luxemburg_eu_tax_file_number_non_natural` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de  `Keywords_luxemburg_eu_tax_file_number` é encontrada.

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
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

- carte de sécurité sociale
- étain non
- étain #
- identifiant d'impôt
- luxemburgues tax identifikatiounsnummer
- numéro d'étain
- numéro d'identification fiscal luxembourgeois
- numéro d'identification fiscale
- social security
- sozialunterstützung
- sozialversécherung
- sozialversicherungsausweis
- steier id
- steier identifikatiounsnummer
- númem steier
- steuer id
- steueridentifikationsnummer
- steuernummer
- tax id
- identificação de imposto não
- número de identificação fiscal
- tax no #
- tax no
- número de imposto
- número de registro fiscal
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- id de estanho
- tin no
- tin #
- zinn #
- zinn
- zinnzahl


## <a name="malaysia-identification-card-number"></a>Número do cartão de identificação da Malásia

### <a name="format"></a>Formatar

12 dígitos contendo hifens opcionais

### <a name="pattern"></a>Padrão

12 dígitos:
- seis dígitos no formato YYMMDD, que são a data de nascimento
- um traço (opcional)
- código de local de nascimento de duas letras
- um traço (opcional)
- três dígitos aleatórios
- código de gênero de um dígito

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular Regex_malaysia_id_card_number encontra conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_malaysia_id_card_number é encontrada.

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
- i/c
- i/c no
- ic
- ic no
- id card
- cartão de identificação
- cartão de identidade
- k/p
- k/p no
- kad akuan diri
- kad aplikasi digital
- kad pengenalan malásia
- kp
- kp no
- mykad
- mykas
- mykid
- mypr
- mytentera
- cartão de identidade malaio
- cartão de identidade malaio
- nric
- cartão de identificação pessoal

## <a name="malta-drivers-license-number"></a>Número da carteira de motorista de Malta

### <a name="format"></a>Formatar

Combinação de dois caracteres e seis dígitos no padrão especificado

### <a name="pattern"></a>Padrão

combinação de dois caracteres e seis dígitos:

- dois caracteres (dígitos ou letras, não sensíveis a maiúsculas e minúsculas)
- um espaço (opcional)
- três dígitos
- um espaço (opcional)
- três dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_malta_eu_driver's_license_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave  `Keywords_eu_driver's_license_number` de ou `Keywords_malta_eu_driver's_license_number` é encontrada.

```xml
      <!-- Malta Driver's License Number -->
      <Entity id="a3bdaa4a-8371-4735-8fa5-56ee0fb4afc4" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_malta_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver'lic
- lics do driver
- driver'license
- driver'licenses
- driver'licence
- driver 'licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- lic do driver
- lics do driver
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver'lic #
- lics do driver #
- driver'license #
- driver'licenses #
- driver'licence #
- driver 'licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- lic do driver #
- lics do driver #
- carteira de motorista #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving licence
- dlno #
- driv lic
- licencia de driv
- licença de driv
- licenças de driv
- driv licence
- licenças de driv
- driver licen
- drivers licen
- licenciador do driver
- lic de direção
- driving licen
- conduzir licenças
- driving licence
- driving licences
- permissão de direção
- dl no
- dlno
- dl number


#### <a name="keywords_malta_eu_drivers_license_number"></a>Keywords_malta_eu_driver s_license_number

- liċenzja tas-sewqan
- liċenzji tas-sewwieq


## <a name="malta-identity-card-number"></a>Número do cartão de identidade de Malta
Esse tipo de informação confidenciais só está disponível para uso em:
- políticas de prevenção contra perda de dados
- políticas de conformidade de comunicação
- governança de informações
- gerenciamento de registros
- Segurança do aplicativo na nuvem da Microsoft

### <a name="format"></a>Formatar

sete dígitos seguidos por uma letra

### <a name="pattern"></a>Padrão

sete dígitos seguidos por uma letra:

- sete dígitos
- uma letra em "M, G, A, P, L, H, B, Z" (maiúsculas de minúsculas)

### <a name="checksum"></a>Soma de verificação

Não se aplica

### <a name="definition"></a>Definição

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_malta_eu_national_id_card` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de  `Keywords_malta_eu_national_id_card` é encontrada.

Uma política de DLP tem baixa confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_malta_eu_national_id_card` localiza conteúdo que corresponde ao padrão.

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

- número de serviço do cidadão
- id tat-taxxa
- identifika numru tal-biljett
- kodiċi numerali personali
- numru ta 'identifikazzjoni personali
- numru ta 'identifikazzjoni tat-taxxa
- numru ta 'identifikazzjoni uniku
- numru ta' identità uniku
- numru tas-servizz taċ-ċittadin
- numru tat-taxxa
- código numérico pessoal
- número de identificação exclusivo
- número de identidade exclusivo
- uniqueidentityno #


## <a name="malta-passport-number"></a>Número do passaporte de Malta

### <a name="format"></a>Formatar

sete dígitos sem espaços ou delimitadores

### <a name="pattern"></a>Padrão

sete dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_malta_eu_passport_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave  `Keywords_eu_passport_number` de ou `Keywords_malta_eu_passport_number` é encontrada.
- Uma palavra-chave `Keywords_eu_passport_date` de é encontrada

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_malta_eu_passport_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave  `Keywords_eu_passport_number` de ou `Keywords_malta_eu_passport_number` é encontrada.

```xml
      <!-- Malta Passport Number -->
      <Entity id="b2b21198-48f9-4d13-b2a5-03969bff0fb8" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_malta_eu_passport_number" />
          </Any>
          <Match idRef="Keywords_eu_passport_date" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_malta_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- números do passport

#### <a name="keywords_malta_eu_passport_number"></a>Keywords_malta_eu_passport_number

- numru tal-passaport
- numri tal-passaport
- Nru tal-passaport

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- data de emissão
- data de expiração


## <a name="malta-tax-identification-number"></a>Número de identificação fiscal de Malta

### <a name="format"></a>Formatar

Para nacionais malteses:
- sete dígitos e uma letra no padrão especificado

Entidades não maltesas e nacionais maltesas:
- nove dígitos

### <a name="pattern"></a>Padrão

Nacionais malteses: sete dígitos e uma letra

- sete dígitos
- uma letra (não sensível a minúsculas)

Nacionais não malteses e entidades maltesas: nove dígitos

- nove dígitos

### <a name="checksum"></a>Soma de verificação

Não se aplica

### <a name="definition"></a>Definição

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- O regex  `Regex_malta_eu_tax_file_number`  ou localiza conteúdo que corresponde ao `Regex_malta_eu_tax_file_number_non_maltese_national` padrão.
- Uma palavra-chave de  `Keywords_malta_eu_tax_file_number` é encontrada.

Uma política de DLP tem baixa confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- O regex  `Regex_malta_eu_tax_file_number` ou localiza conteúdo que corresponde ao `Regex_malta_eu_tax_file_number_non_maltese_national` padrão.

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

- número de serviço do cidadão
- id tat-taxxa
- identifika numru tal-biljett
- kodiċi numerali personali
- numru ta 'identifikazzjoni personali
- numru ta 'identifikazzjoni tat-taxxa
- numru ta 'identifikazzjoni uniku
- numru ta' identità uniku
- numru tas-servizz taċ-ċittadin
- numru tat-taxxa
- código numérico pessoal
- tax id
- identificação de imposto não
- número de identificação fiscal
- tax no #
- tax no
- número de imposto
- número de registro fiscal
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- id de estanho
- tin no
- tin #
- número de identificação exclusivo
- número de identidade exclusivo
- uniqueidentityno #


## <a name="medicare-beneficiary-identifier-mbi-card"></a>Cartão de Identificador de Beneficiário do Medicare (MBI)

### <a name="format"></a>Formatar

Padrão alfanumérico de 11 caracteres

### <a name="pattern"></a>Padrão

- um dígito entre 1 e 9
- uma letra excluindo S, L, O, I, B, Z
- um dígito ou letra excluindo S, L, O, I, B, Z
- um dígito
- um Hífen opcional
- uma letra excluindo S, L, O, I, B, Z
- um dígito ou letra excluindo S, L, O, I, B, Z
- um dígito
- um Hífen opcional
- duas letras excluindo S, L, O, I, B, Z
- dois dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_mbi_card` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de  `Keyword_mbi_card` é encontrada.

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_mbi_card` localiza conteúdo que corresponde ao padrão.

```xml
    <!-- Medicare Beneficiary Identifier (MBI) card -->
      <Entity id="f753a286-f5cc-47e6-a592-4be25fd02591" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_mbi_card" />
          <Match idRef="Keyword_mbi_card" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_mbi_card" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_mbi_card"></a>Keyword_mbi_card

- mbi
- mbi #
- beneficiário do plano de saúde #
- identificador do beneficiário do plano de saúde
- não do beneficiário do plano de saúde
- número do beneficiário do plano de saúde
- beneficiário do plano de saúde #


## <a name="mexico-unique-population-registry-code-curp"></a>Código de Registro de População Exclusivo do México (CURP)

### <a name="format"></a>Formatar

Padrão alfanumérico de 18 caracteres

### <a name="pattern"></a>Padrão

- quatro letras (sem maiúsculas e minúsculas)
- seis dígitos indicando uma data válida
- uma letra - H/h ou M/m
- duas letras indicando um código de estado mexicano válido
- três letras
- uma letra ou dígito
- um dígito

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_mexico_population_registry_code` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de  `Keyword_mexico_population_registry_code` é encontrada.

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_mexico_population_registry_code` localiza conteúdo que corresponde ao padrão.

```xml
    <!-- Mexico Unique Population Registry Code (CURP) -->
      <Entity id="e905ad4d-5a74-406d-bf36-b1efca798af4" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_mexico_population_registry_code" />
          <Match idRef="Keyword_mexico_population_registry_code" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_mexico_population_registry_code" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_mexico_population_registry_code"></a>Keyword_mexico_population_registry_code

- Clave Única de Registro de Población
- Clave Unica de Registro de Poblacion
- Código exclusivo do Registro de População 
- código de população exclusivo
- CURP
- ID Pessoal
- ID exclusiva
- personalid
- personalidnumber
- uniqueidkey
- uniqueidnumber
- clave única
- clave unica
- clave personal Identidad
- personal Identidad Clave
- ClaveÚnica
- claveunica
- clavepersonalIdentidad


## <a name="netherlands-citizens-service-bsn-number"></a>Número do serviço de cidadãos (BSN) dos Países Baixos

### <a name="format"></a>Formatar

oito ou nove dígitos que contêm espaços opcionais

### <a name="pattern"></a>Padrão

oito e nove dígitos:
- três dígitos
- um espaço (opcional)
- três dígitos
- um espaço (opcional)
- dois a três dígitos

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_netherlands_bsn localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_netherlands_bsn é encontrada.
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

- bsn #
- bsn
- hamburgerservicenummer
- número de serviço do cidadão
- número da pessoa
- número pessoal
- código numérico pessoal
- número relacionado à pessoa
- nummer persoonlijk
- código numerieke persoonlijke
- persoonsgebonden
- persoonsnummer
- nummer sociaal-fiscaal
- número social-fiscal
- sofi
- sofinummer
- uniek identificatienummer
- uniek identiteitsnummer
- número de identificação exclusivo
- número de identidade exclusivo
- uniqueidentityno #

## <a name="netherlands-drivers-license-number"></a>Número da carteira de motorista dos Países Baixos

### <a name="format"></a>Formatar

10 dígitos sem espaços e delimitadores

### <a name="pattern"></a>Padrão

10 dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_netherlands_eu_driver's_license_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave  `Keywords_eu_driver's_license_number` de ou `Keywords_netherlands_eu_driver's_license_number` é encontrada.

```xml
      <!-- Netherlands Driver's License Number -->
      <Entity id="6247fbea-ab80-4be5-8233-308b7c031401" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
            </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver'lic
- lics do driver
- driver'license
- driver'licenses
- driver'licence
- driver 'licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- lic do driver
- lics do driver
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver'lic #
- lics do driver #
- driver'license #
- driver'licenses #
- driver'licence #
- driver 'licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- lic do driver #
- lics do driver #
- carteira de motorista #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving licence
- dlno #
- driv lic
- licencia de driv
- licença de driv
- licenças de driv
- driv licence
- licenças de driv
- driver licen
- drivers licen
- licenciador do driver
- lic de direção
- driving licen
- conduzir licenças
- driving licence
- driving licences
- permissão de direção
- dl no
- dlno
- dl number


#### <a name="keywords_netherlands_eu_drivers_license_number"></a>Keywords_netherlands_eu_driver s_license_number

- permis de conduire
- rijbewijs
- rijbewijsnummer
- rijbewijzen
- nummer rijbewijs
- rijbewijsnummers


## <a name="netherlands-passport-number"></a>Número do passaporte holandês

### <a name="format"></a>Formatar

nove letras ou dígitos sem espaços ou delimitadores

### <a name="pattern"></a>Padrão

nove letras ou dígitos

### <a name="checksum"></a>Soma de verificação

não se aplica

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_netherlands_eu_passport_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave  `Keywords_eu_passport_number` de ou `Keywords_netherlands_eu_passport_number` é encontrada.
- A expressão regular localiza a data no `Regex_netherlands_eu_passport_date` formato DD MMM/MMM YYYY (Exemplo - 26 MAA/MAR 2012)

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_netherlands_eu_passport_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave  `Keywords_eu_passport_number` de ou `Keywords_netherlands_eu_passport_number` é encontrada.

```xml
      <!-- Netherlands Passport Number -->
      <Entity id="61786727-bafd-45f6-94d9-888d815e228e" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Regex_netherlands_eu_passport_date" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_netherlands_eu_passport_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_netherlands_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- números do passport

#### <a name="keywords_netherlands_eu_passport_number"></a>Keywords_netherlands_eu_passport_number

- nummer paspoort
- paspoortnummers
- paspoortnummer
- paspoort nr

## <a name="netherlands-tax-identification-number"></a>Número de identificação fiscal dos Países Baixos
Esse tipo de informação confidenciais só está disponível para uso em:
- políticas de prevenção contra perda de dados
- políticas de conformidade de comunicação
- governança de informações
- gerenciamento de registros
- Segurança do aplicativo na nuvem da Microsoft

### <a name="format"></a>Formatar

nove dígitos sem espaços ou delimitadores

### <a name="pattern"></a>Padrão

nove dígitos

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_netherlands_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de  `Keywords_netherlands_eu_tax_file_number` é encontrada.

Uma política de DLP tem baixa confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
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

- btw nummer
- Identificação de imposto hollânske
- hulandes impuesto id number
- hulandes impuesto identification
- identificatienummer belasting
- identificatienummer van belasting
- número de identificação impuesto
- número impuesto
- nederlands belasting id nummer
- nederlands belasting identificatie
- nederlands belasting identificatienummer
- nederlands belastingnummer
- nederlandse belasting identificatie
- identificação fiscal dos Países Baixos
- identificação fiscal da Holanda
- países baixos tin
- tin holandês
- tax id
- identificação de imposto não
- número de identificação fiscal
- tal de identificação fiscal
- tax no #
- tax no
- número de imposto
- número de registro fiscal
- tax tal
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- id de estanho
- tin no
- tin #


## <a name="netherlands-value-added-tax-number"></a>Número de imposto adicionado ao valor holandês
Esse tipo de informação confidenciais só está disponível para uso em:
- políticas de prevenção contra perda de dados
- políticas de conformidade de comunicação
- governança de informações
- gerenciamento de registros
- Segurança do aplicativo na nuvem da Microsoft

### <a name="format"></a>Formatar

Padrão alfanumérico de 14 caracteres

### <a name="pattern"></a>Padrão

Padrão alfanumérico de 14 caracteres:

- N ou n
- L ou l
- espaço opcional, ponto ou hífen
- nove dígitos
- espaço opcional, ponto ou hífen
- B ou b
- dois dígitos

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_netherlands_value_added_tax_number encontra conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keywords_netherlands_value_added_tax_number é encontrada.

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_netherlands_value_added_tax_number encontra conteúdo que corresponde ao padrão.

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

- número de iva
- vat no
- vat #
- getal de imposto do wearde tafoege
- btw nûmer
- btw-nummer


## <a name="new-zealand-bank-account-number"></a>Número da conta bancária da Nova Zelândia
Esse tipo de informação confidenciais só está disponível para uso em:
- políticas de prevenção contra perda de dados
- políticas de conformidade de comunicação
- governança de informações
- gerenciamento de registros
- Segurança do aplicativo na nuvem da Microsoft

### <a name="format"></a>Formatar

Padrão de 14 a 16 dígitos com o delimiter opcional

### <a name="pattern"></a>Padrão

Padrão de 14 a 16 dígitos com o delimiter opcional:

- dois dígitos
- um hífen opcional ou espaço
- de três a quatro dígitos
- um hífen opcional ou espaço
- sete dígitos
- um hífen opcional ou espaço
- dois a três dígitos
- um hífen de opções ou espaço

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_new_zealand_bank_account_number encontra conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keywords_new_zealand_bank_account_number é encontrada.

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_new_zealand_bank_account_number encontra conteúdo que corresponde ao padrão.

```xml
      <!-- New Zealand Bank Account Number -->
      <Entity id="1a97fc2b-dd2f-48f1-bc4e-2ddf25813956" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_new_zealand_bank_account_number" />
          <Match idRef="Keywords_new_zFealand_bank_account_number" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_new_zealand_bank_account_number" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_new_zealand_bank_account_number"></a>Keyword_new_zealand_bank_account_number

- account number
- conta bancária
- bank_acct_id
- bank_acct_branch
- bank_acct_nbr


## <a name="new-zealand-drivers-license-number"></a>Número da carteira de motorista da Nova Zelândia
Esse tipo de informação confidenciais só está disponível para uso em:
- políticas de prevenção contra perda de dados
- políticas de conformidade de comunicação
- governança de informações
- gerenciamento de registros
- Segurança do aplicativo na nuvem da Microsoft

### <a name="format"></a>Formatar

padrão alfanumérico de oito caracteres

### <a name="pattern"></a>Padrão

padrão alfanumérico de oito caracteres

- duas letras
- seis dígitos

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_newzealand_driver_license_number encontra conteúdo que corresponde ao padrão.
- Uma palavra-chave Keywords_newzealand_driver_license_number é encontrada.

Uma política de DLP tem baixa confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_newzealand_driver_license_number encontra conteúdo que corresponde ao padrão.

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
- driver lic
- driver licence
- driver licences
- driverslic
- driverslicence
- driverslicences
- drivers lic
- drivers lics
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'licence
- driver'licences
- driver'lic
- lics do driver
- driver'licence
- driver 'licences
- driver'slic
- driver'slics
- driver'slicence
- driver'slicences
- lic do driver
- lics do driver
- driver's licence
- driver's licences
- driverlic #
- driverlics #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver licence #
- driver licences #
- driverslic #
- driverslics #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'licence #
- driver'licences #
- driver'lic #
- lics do driver #
- driver'licence #
- driver 'licences #
- driver'slic #
- driver'slics #
- driver'slicence #
- driver'slicences #
- lic do driver #
- lics do driver #
- driver's licence #
- driver's licences #
- international driving permit
- international driving permits
- Associação de automóveis nz
- Associação de automóveis da Nova Zelândia


## <a name="new-zealand-inland-revenue-number"></a>Número de receita do interior da Nova Zelândia
Esse tipo de informação confidenciais só está disponível para uso em:
- políticas de prevenção contra perda de dados
- políticas de conformidade de comunicação
- governança de informações
- gerenciamento de registros
- Segurança do aplicativo na nuvem da Microsoft

### <a name="format"></a>Formatar

oito ou nove dígitos com delimitadores opcionais

### <a name="pattern"></a>Padrão

oito ou nove dígitos com delimitadores opcionais

- dois ou três dígitos
- um espaço opcional ou hífen
- três dígitos
- um espaço opcional ou hífen
- três dígitos

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_new_zealand_inland_revenue_number localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave Keywords_new_zealand_inland_revenue_number é encontrada.

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_new_zealand_inland_revenue_number localiza conteúdo que corresponde ao padrão.

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

- ird não.
- ird no #
- nz ird
- new zealand ird
- número ird
- número de receita no interior


## <a name="new-zealand-ministry-of-health-number"></a>Número do Ministério da Saúde da Nova Zelândia

### <a name="format"></a>Formatar

três letras, um espaço (opcional) e quatro dígitos

### <a name="pattern"></a>Padrão

- três letras (não sensíveis a maiúsculas e minúsculas), exceto 'I' e 'O'
- um espaço (opcional)
- quatro dígitos

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_new_zealand_ministry_of_health_number localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_nz_terms for encontrada.
- A soma de verificação passa.

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_new_zealand_ministry_of_health_number localiza conteúdo que corresponde ao padrão.
- A soma de verificação passa.

```xml
    <!-- New Zealand Health Number -->
    <Entity id="2b71c1c8-d14e-4430-82dc-fd1ed6bf05c7" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_new_zealand_ministry_of_health_number" />
          <Match idRef="Keyword_nz_terms" />
      </Pattern>
      <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_new_zealand_ministry_of_health_number" />
       </Pattern>
    </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_nz_terms"></a>Keyword_nz_terms

- NHI
- Nova Zelândia
- Integridade
- treatment
- Número do Índice Nacional de Saúde
- nhi number
- nhi no.
- NHI #
- Índice Nacional de Saúde Não.
- ID do Índice Nacional de Saúde
- Índice Nacional de Saúde #

## <a name="new-zealand-social-welfare-number"></a>Número do bem-estar social da Nova Zelândia

Esse tipo de informação confidenciais só está disponível para uso em:
- políticas de prevenção contra perda de dados
- políticas de conformidade de comunicação
- governança de informações
- gerenciamento de registros
- Segurança do aplicativo na nuvem da Microsoft

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

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_newzealand_social_welfare_number localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave Keywords_newzealand_social_welfare_number é encontrada.

Uma política de DLP tem baixa confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_newzealand_social_welfare_number localiza conteúdo que corresponde ao padrão.

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

- bem-estar social #
- bem-estar social #
- bem-estar social Não.
- número de bem-estar social
- swn #


## <a name="norway-identification-number"></a>Número de identificação da Noruega

### <a name="format"></a>Formatar

11 dígitos

### <a name="pattern"></a>Padrão

11 dígitos:
- seis dígitos no formato DDMMYYY, que são a data de nascimento
- número individual de três dígitos
- dois dígitos de verificação

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_norway_id_number encontra conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_norway_id_number é encontrada.
- A soma de verificação passa.

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_norway_id_numbe encontra conteúdo que corresponde ao padrão.
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
- Identificação
- Personnummer
- Fødselsnummer


## <a name="philippines-unified-multi-purpose-identification-number"></a>Número de identificação multiuso unificado das Filipinas

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

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular Regex_philippines_unified_id encontra conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_philippines_id é encontrada.

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

## <a name="poland-drivers-license-number"></a>Número da carteira de motorista da Polônia

### <a name="format"></a>Formatar

14 dígitos contendo duas barras à frente

### <a name="pattern"></a>Padrão

14 dígitos e duas barras à frente:

- cinco dígitos
- uma barra de avanço
- dois dígitos
- uma barra de avanço
- sete dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_poland_eu_driver's_license_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave  `Keywords_eu_driver's_license_number` de ou `Keywords_poland_eu_driver's_license_number` é encontrada.

```xml
      <!-- Poland Driver's License Number -->
      <Entity id="24d51f99-ee9e-4060-a077-cae58cab1ee4" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_poland_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver'lic
- lics do driver
- driver'license
- driver'licenses
- driver'licence
- driver 'licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- lic do driver
- lics do driver
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver'lic #
- lics do driver #
- driver'license #
- driver'licenses #
- driver'licence #
- driver 'licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- lic do driver #
- lics do driver #
- carteira de motorista #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving licence
- dlno #
- driv lic
- licencia de driv
- licença de driv
- licenças de driv
- driv licence
- licenças de driv
- driver licen
- drivers licen
- licenciador do driver
- lic de direção
- driving licen
- conduzir licenças
- driving licence
- driving licences
- permissão de direção
- dl no
- dlno
- dl number


#### <a name="keywords_poland_eu_drivers_license_number"></a>Keywords_poland_eu_driver s_license_number

- prawo jazdy
- prawa jazdy

## <a name="poland-identity-card"></a>Cartão de identidade da Polônia

### <a name="format"></a>Formatar

três letras e seis dígitos

### <a name="pattern"></a>Padrão

três letras (não sensíveis a maiúsculas e minúsculas) seguidas por seis dígitos

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
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

- Osobisty do Dowód
- Numer dowodu osobistego
- Nazwa i numer dowodu osobistego
- Nazwa i nr dowodu osobistego
- Nazwa i nr dowodu tożsamości
- Dowód Tożsamości
- dow. os.



## <a name="poland-national-id-pesel"></a>ID nacional da Polônia (PESEL)

### <a name="format"></a>Formatar

11 dígitos

### <a name="pattern"></a>Padrão

- seis dígitos que representam a data de nascimento no formato YYMMDD
- quatro dígitos
- um dígito de verificação

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_pesel_identification_number localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_pesel_identification_number for encontrada.
- A soma de verificação passa.

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
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

- osobisty dowód
- dowódosobisty
- numer niepowtarzalny
- niepowtarzalnynumer
- nr.-pesel
- nr-pesel
- númer identyfikacyjny
- pesel
- tożsamości narodowej


## <a name="poland-passport-number"></a>Número do passaporte polonês
Essa entidade de tipo de informação confidenciais está incluída no tipo de informação confidenciais número de passaporte da UE. Ele também está disponível como uma entidade de tipo de informação independente e confidenciais.

### <a name="format"></a>Formatar

duas letras e sete dígitos

### <a name="pattern"></a>Padrão

Duas letras (não sensíveis a maiúsculas e minúsculas) seguidas por sete dígitos

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função `Func_polish_passport_number_v2` localiza conteúdo que corresponde ao padrão.
- A soma de verificação passa.
- Uma palavra-chave `Keywords_eu_passport_number` de ou `Keyword_polish_national_passport_number` é encontrada.
- Uma palavra-chave de `Keywords_eu_passport_date` é encontrada.

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função `Func_polish_passport_number_v2` localiza conteúdo que corresponde ao padrão.
- A soma de verificação passa.
- Uma palavra-chave `Keywords_eu_passport_number` de ou `Keyword_polish_national_passport_number` é encontrada.

Uma política de DLP tem baixa confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função `Func_polish_passport_number_v2` localiza conteúdo que corresponde ao padrão.
- A soma de verificação passa.

```xml
      <!-- Poland Passport Number -->
      <Entity id="03937FB5-D2B6-4487-B61F-0F8BFF7C3517" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_passport_number_v2" />
          <Match idRef="Keywords_eu_passport_date" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keyword_polish_national_passport_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_polish_passport_number_v2" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keyword_polish_national_passport_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_polish_passport_number_v2" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- números do passport

#### <a name="keyword_polish_national_passport_number"></a>Keyword_polish_national_passport_number

- numer paszportu
- numery paszportów
- numery paszportowe
- nr paszportu
- nr. paszportu
- nr paszportów
- n° passeport
- passeport n°

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- data de emissão
- data de expiração


## <a name="poland-regon-number"></a>Número REGON da Polônia
Esse tipo de informação confidenciais só está disponível para uso em:
- políticas de prevenção contra perda de dados
- políticas de conformidade de comunicação
- governança de informações
- gerenciamento de registros
- Segurança do aplicativo na nuvem da Microsoft

### <a name="format"></a>Formatar

Número de 9 dígitos ou 14 dígitos

### <a name="pattern"></a>Padrão

nove dígitos ou número de 14 dígitos:

- nove dígitos ou
- nove dígitos
- hifen
- cinco dígitos

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_polish_regon_number encontra conteúdo que corresponde ao padrão.
- Uma palavra-chave Keywords_polish_regon_number é encontrada.

Uma política de DLP tem baixa confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_polish_regon_number encontra conteúdo que corresponde ao padrão.

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

- id regon
- número estatístico
- id estatística
- statistical no
- número de regon
- regonid #
- regonno #
- id da empresa
- companyid #
- companyidno #
- numer statystyczny
- numeru regon
- numerstatystyczny #
- numeruregon #


## <a name="poland-tax-identification-number"></a>Número de identificação fiscal da Polônia
Esse tipo de informação confidenciais só está disponível para uso em:
- políticas de prevenção contra perda de dados
- políticas de conformidade de comunicação
- governança de informações
- gerenciamento de registros
- Segurança do aplicativo na nuvem da Microsoft

### <a name="format"></a>Formatar

11 dígitos sem espaços ou delimitadores

### <a name="pattern"></a>Padrão

11 dígitos

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_poland_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de  `Keywords_poland_eu_tax_file_number` é encontrada.


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
- numer identyfikacji podatkowej
- numeridentyfikacjipodatkowej #
- tax id
- identificação de imposto não
- número de identificação fiscal
- tax no #
- tax no
- número de imposto
- número de registro fiscal
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- id de estanho
- tin no
- tin #
- id de iva #
- id de iva
- vat no
- número de iva
- vatid #
- vatid
- vatno #


## <a name="portugal-citizen-card-number"></a>Número do cartão de cidadão de Portugal

### <a name="format"></a>Formatar

oito dígitos

### <a name="pattern"></a>Padrão

oito dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular Regex_portugal_citizen_card encontra conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_portugal_citizen_card é encontrada.

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
- número de id
- identificação não
- identification number
- identity card no
- número do cartão de identidade
- cartão de identificação nacional
- nic
- número bi de portugal
- número de identificação civil
- número de identificação fiscal
- número do documento
- número bi portugal


## <a name="portugal-drivers-license-number"></a>Número da carteira de motorista de Portugal

### <a name="format"></a>Formatar

dois padrões - duas letras seguidas por 5 a 8 dígitos com caracteres especiais

### <a name="pattern"></a>Padrão

Padrão 1: Duas letras seguidas por 5/6 com caracteres especiais:
- Duas letras (não sensíveis a maiúsculas e minúsculas)
- Um hífen
- Cinco ou seis dígitos
- Um espaço
- Um dígito

Padrão 2: Uma letra seguida de 6/8 dígitos com caracteres especiais:
- Uma letra (não sensível a minúsculas)
- Um hífen
- Seis ou oito dígitos
- Um espaço
- Um dígito


### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_portugal_eu_driver's_license_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave  `Keywords_eu_driver's_license_number` de ou `Keywords_portugal_eu_driver's_license_number` é encontrada.

```xml
      <!-- Portugal Driver's License Number -->
      <Entity id="977f1e5a-2c33-4bcc-b516-95bb275cff23" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_portugal_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver'lic
- lics do driver
- driver'license
- driver'licenses
- driver'licence
- driver 'licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- lic do driver
- lics do driver
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver'lic #
- lics do driver #
- driver'license #
- driver'licenses #
- driver'licence #
- driver 'licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- lic do driver #
- lics do driver #
- carteira de motorista #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving licence
- dlno #
- driv lic
- licencia de driv
- licença de driv
- licenças de driv
- driv licence
- licenças de driv
- driver licen
- drivers licen
- licenciador do driver
- lic de direção
- driving licen
- conduzir licenças
- driving licence
- driving licences
- permissão de direção
- dl no
- dlno
- dl number


#### <a name="keywords_portugal_eu_drivers_license_number"></a>Keywords_portugal_eu_driver s_license_number

- carteira de motorista
- carteira motorista
- carteira de habilitação
- carteira habilitação
- número de licença
- número licença
- dados de condução
- autoridade condução
- Licença condução Portugal
- carta de condução

## <a name="portugal-passport-number"></a>Número do passaporte de Portugal

### <a name="format"></a>Formatar

uma letra seguida por seis dígitos sem espaços ou delimitadores

### <a name="pattern"></a>Padrão

uma letra seguida por seis dígitos:

- uma letra (não sensível a minúsculas)
- seis dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_portugal_eu_passport_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave  `Keywords_eu_passport_number` de ou `Keywords_portugal_eu_passport_number` é encontrada.
- A expressão regular `Regex_eu_passport_date1` localiza a data no formato DD.MM.YYYY ou uma palavra-chave de é `Keywords_eu_passport_date` encontrada

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_portugal_eu_passport_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave  `Keywords_eu_passport_number` de ou `Keywords_portugal_eu_passport_number` é encontrada.

```xml
      <!-- Portugal Passport Number -->
      <Entity id="080a52fd-a7bc-431e-b54d-51f08f59db11" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_portugal_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_portugal_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- números do passport

#### <a name="keywords_portugal_eu_passport_number"></a>Keywords_portugal_eu_passport_number

- número do passaporte
- passaporte português
- portuguese passeport
- portuguese passaporte
- passaporte nº
- passeport nº
- números de passaporte
- passaportes portugueses
- número passaporte
- números passaporte

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- data de emissão
- data de expiração


## <a name="portugal-tax-identification-number"></a>Número de identificação fiscal de Portugal

### <a name="format"></a>Formatar

nove dígitos com espaços opcionais

### <a name="pattern"></a>Padrão

- três dígitos
- um espaço opcional
- três dígitos
- um espaço opcional
- três dígitos

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_portugal_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de  `Keywords_portugal_eu_tax_file_number` é encontrada.

Uma política de DLP tem baixa confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
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

- cpf #
- cpf
- nif #
- nif
- número de identificação fisca
- numero fiscal
- tax id
- identificação de imposto não
- número de identificação fiscal
- tax no #
- tax no
- número de imposto
- número de registro fiscal
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- id de estanho
- tin no
- tin #


## <a name="romania-drivers-license-number"></a>Número da carteira de motorista da Romênia

### <a name="format"></a>Formatar

um caractere seguido por oito dígitos

### <a name="pattern"></a>Padrão

um caractere seguido por oito dígitos:
- uma letra (não sensível a minúsculas) ou dígito
- oito dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_romania_eu_driver's_license_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave  `Keywords_eu_driver's_license_number` de ou `Keywords_romania_eu_driver's_license_number` é encontrada.

```xml
      <!-- Romania Driver's License Number -->
      <Entity id="b5511ace-2fd8-4ae4-b6fc-c7c6e4689e3c" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_romania_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver'lic
- lics do driver
- driver'license
- driver'licenses
- driver'licence
- driver 'licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- lic do driver
- lics do driver
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver'lic #
- lics do driver #
- driver'license #
- driver'licenses #
- driver'licence #
- driver 'licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- lic do driver #
- lics do driver #
- carteira de motorista #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving licence
- dlno #
- driv lic
- licencia de driv
- licença de driv
- licenças de driv
- driv licence
- licenças de driv
- driver licen
- drivers licen
- licenciador do driver
- lic de direção
- driving licen
- conduzir licenças
- driving licence
- driving licences
- permissão de direção
- dl no
- dlno
- dl number


#### <a name="keywords_romania_eu_drivers_license_number"></a>Keywords_romania_eu_driver s_license_number

- permis de conducere
- permisului de conducere
- permisului conducere
- permisele de conducere
- permisele conducere
- permis conducere

## <a name="romania-personal-numeric-code-cnp"></a>Código numérico pessoal da Romênia (CNP)
Esse tipo de informação confidenciais só está disponível para uso em:
- políticas de prevenção contra perda de dados
- políticas de conformidade de comunicação
- governança de informações
- gerenciamento de registros
- Segurança do aplicativo na nuvem da Microsoft

### <a name="format"></a>Formatar

13 dígitos sem espaços e delimitadores

### <a name="pattern"></a>Padrão

- um dígito de 1 a 9
- seis dígitos que representam a data de nascimento (YYMMDD)
- dois dígitos, que podem ser 01-52 ou 99
- quatro dígitos

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_romania_eu_national_id_card` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de  `Keywords_romania_eu_national_id_card` é encontrada.

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
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
- cod identificare personal
- cod numeric personal
- cod unic identificare
- codnumericpersonal #
- codul fiscal nr.
- identificarea fiscală nr #
- id-ul taxei
- número do seguro
- insurancenumber #
- id nacional #
- national id
- national identification number
- număr identificare personal
- númăr identitate
- număr personal unic
- număridentitate #
- număridentitate
- numărpersonalunic #
- numărpersonalunic
- număru de identificare fiscală
- numărul de identificare fiscală
- código numérico pessoal
- pin #
- pin
- arquivo fiscal não
- tax file number
- tax id
- identificação de imposto não
- número de identificação fiscal
- tax no #
- tax no
- número de imposto
- número de registro fiscal
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- id de estanho
- tin no
- tin #
- número de identificação exclusivo
- número de identidade exclusivo
- uniqueidentityno #
- uniqueidentityno

## <a name="romania-passport-number"></a>Número do passaporte romeno

### <a name="format"></a>Formatar

oito ou nove dígitos sem espaços e delimitadores

### <a name="pattern"></a>Padrão

oito ou nove dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_romania_eu_passport_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave  `Keywords_eu_passport_number` de ou `Keywords_romania_eu_passport_number` é encontrada.
- A expressão regular localiza a data no formato `Regex_romania_eu_passport_date` DD MMM/MMM YY (Exemplo- 01 FEB/FEB 10) ou uma palavra-chave de `Keywords_eu_passport_date` é encontrada

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_romania_eu_passport_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave  `Keywords_eu_passport_number` de ou `Keywords_romania_eu_passport_number` é encontrada.

```xml
      <!-- Romania Passport Number -->
      <Entity id="5d31b90c-7fe2-4a76-a14b-767b8fd19d6c" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_romania_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_romania_eu_passport_date" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_romania_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- números do passport

#### <a name="keywords_romania_eu_passport_number"></a>Keywords_romania_eu_passport_number

numărul paşaportului numarul pasaportului numerele paşaportului Paşaport nr

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- data de emissão
- data de expiração


## <a name="russia-passport-number-domestic"></a>Número do passaporte russo doméstico
Esse tipo de informação confidenciais só está disponível para uso em:
- políticas de prevenção contra perda de dados
- políticas de conformidade de comunicação
- governança de informações
- gerenciamento de registros
- Segurança do aplicativo na nuvem da Microsoft

### <a name="format"></a>Formatar

Número de 10 dígitos

### <a name="pattern"></a>Padrão

Número de 10 dígitos:

- dois dígitos
- um espaço opcional ou hífen
- dois dígitos
- um espaço opcional
- seis dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- O Regex_Russian_Passport_Number_Domestic regex localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave Keyword_Russian_Passport_Number é encontrada.

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

- passport number
- passport no
- passport #
- id do passport
- passportno #
- passportnumber #
- паспорт нет
- паспорт id
- pоссийской паспорт
- pусский номер паспорта
- паспорт #
- паспортid #
- номер паспорта
- номерпаспорта #


## <a name="russia-passport-number-international"></a>Número de passaporte russo internacional
Esse tipo de informação confidenciais só está disponível para uso em:
- políticas de prevenção contra perda de dados
- políticas de conformidade de comunicação
- governança de informações
- gerenciamento de registros
- Segurança do aplicativo na nuvem da Microsoft

### <a name="format"></a>Formatar

número de nove dígitos

### <a name="pattern"></a>Padrão

número de nove dígitos:

- dois dígitos
- um espaço opcional ou hífen
- sete dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- O regex Regex_Russian_Passport_Number_International o conteúdo que corresponde ao padrão.
- Uma palavra-chave Keyword_Russian_Passport_Number é encontrada.

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

- passport number
- passport no
- passport #
- id do passport
- passportno #
- passportnumber #
- паспорт нет
- паспорт id
- pоссийской паспорт
- pусский номер паспорта
- паспорт #
- паспортid #
- номер паспорта
- номерпаспорта #


## <a name="saudi-arabia-national-id"></a>ID nacional da Arábia Saudita

### <a name="format"></a>Formatar

10 dígitos

### <a name="pattern"></a>Padrão

10 dígitos consecutivos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
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


## <a name="singapore-national-registration-identity-card-nric-number"></a>Número do NRIC (cartão de identidade de registro nacional) de Cingapura

### <a name="format"></a>Formatar

nove letras e dígitos

### <a name="pattern"></a>Padrão

- nove letras e dígitos:
- a letra "F", "G", "S" ou "T" (não sensível a minúsculas)
- sete dígitos
- um dígito de verificação alfabética

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular Regex_singapore_nric encontra conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_singapore_nric é encontrada.
- A soma de verificação passa.

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular Regex_singapore_nric encontra conteúdo que corresponde ao padrão.
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
- IC
- Número de Identificação Estrangeira
- FIN
- 身份证
- 身份證

## <a name="slovakia-drivers-license-number"></a>Número da carteira de motorista da Eslováquia

### <a name="format"></a>Formatar

um caractere seguido por sete dígitos

### <a name="pattern"></a>Padrão

um caractere seguido por sete dígitos

- uma letra (não sensível a minúsculas) ou dígito
- sete dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_slovakia_eu_driver's_license_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave  `Keywords_eu_driver's_license_number` de ou `Keywords_slovakia_eu_driver's_license_number` é encontrada.

```xml
      <!-- Slovakia Driver's License Number -->
      <Entity id="14240c22-b6de-4ce5-a90b-137f74252513" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver'lic
- lics do driver
- driver'license
- driver'licenses
- driver'licence
- driver 'licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- lic do driver
- lics do driver
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver'lic #
- lics do driver #
- driver'license #
- driver'licenses #
- driver'licence #
- driver 'licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- lic do driver #
- lics do driver #
- carteira de motorista #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving licence
- dlno #
- driv lic
- licencia de driv
- licença de driv
- licenças de driv
- driv licence
- licenças de driv
- driver licen
- drivers licen
- licenciador do driver
- lic de direção
- driving licen
- conduzir licenças
- driving licence
- driving licences
- permissão de direção
- dl no
- dlno
- dl number


#### <a name="keywords_slovakia_eu_drivers_license_number"></a>Keywords_slovakia_eu_driver s_license_number

- vodičský preukaz
- vodičské preukazy
- vodičského preukazu
- vodičských preukazov

## <a name="slovakia-personal-number"></a>Número pessoal da Eslováquia
Esse tipo de informação confidenciais só está disponível para uso em:
- políticas de prevenção contra perda de dados
- políticas de conformidade de comunicação
- governança de informações
- gerenciamento de registros
- Segurança do aplicativo na nuvem da Microsoft

### <a name="format"></a>Formatar

nove ou 10 dígitos que contêm backslash opcional

### <a name="pattern"></a>Padrão

- seis dígitos que representam a data de nascimento
- barra opcional (/)
- três dígitos
- um dígito de verificação opcional

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_slovakia_eu_national_id_card` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de  `Keywords_slovakia_eu_national_id_card` é encontrada.

Uma política de DLP tem baixa confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
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

- azonosító szám
- número de nascimento
- číslo národnej identifikačnej karty
- číslo občianského preukazu
- daňové číslo
- número de id
- identificação não
- identification number
- identifikačná karta č
- identifikačné číslo
- identity card no
- número do cartão de identidade
- národná identifikačná značka č
- número nacional
- nationalnumber #
- nemzeti személyazonosító igazolvány
- personalidnumber #
- rč
- rodne cislo
- rodné číslo
- social security number
- ssn #
- ssn
- személyi igazolvány szám
- személyi igazolvány száma
- személyigazolvány szám
- arquivo fiscal não
- tax file number
- tax id
- identificação de imposto não
- número de identificação fiscal
- tax no #
- tax no
- número de imposto
- número de registro fiscal
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- id de estanho
- tin no
- tin #

## <a name="slovakia-passport-number"></a>Número do passaporte da Eslováquia

### <a name="format"></a>Formatar

um dígito ou letra seguido por sete dígitos sem espaços ou delimitadores

### <a name="pattern"></a>Padrão

um dígito ou letra (não sensível a minúsculas) seguido por sete dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_slovakia_eu_passport_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave  `Keywords_eu_passport_number` de ou `Keywords_slovakia_eu_passport_number` é encontrada.
- A expressão regular `Regex_eu_passport_date1` localiza a data no formato DD.MM.YYYY ou uma palavra-chave de é `Keywords_eu_passport_date` encontrada

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_slovakia_eu_passport_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave  `Keywords_eu_passport_number` de ou `Keywords_slovakia_eu_passport_number` é encontrada.

```xml
      <!-- Slovakia Passport Number -->
      <Entity id="238e1f08-d80e-4793-af33-9b57918335b7" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_slovakia_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_slovakia_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- números do passport

#### <a name="keywords_slovakia_eu_passport_number"></a>Keywords_slovakia_eu_passport_number

- číslo pasu
- čísla passo a passo
- pas č.
- Passeport n°
- n° Passeport

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- data de emissão
- data de expiração


## <a name="slovenia-drivers-license-number"></a>Número da carteira de motorista da Eslovênia

### <a name="format"></a>Formatar

nove dígitos sem espaços e delimitadores

### <a name="pattern"></a>Padrão

nove dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_slovenia_eu_driver's_license_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave  `Keywords_eu_driver's_license_number` de ou `Keywords_slovenia_eu_driver's_license_number` é encontrada.

```xml
      <!-- Slovenia Driver's License Number -->
      <Entity id="d5bc089a-f2ee-433d-a6b1-5c253051d6f2" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver'lic
- lics do driver
- driver'license
- driver'licenses
- driver'licence
- driver 'licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- lic do driver
- lics do driver
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver'lic #
- lics do driver #
- driver'license #
- driver'licenses #
- driver'licence #
- driver 'licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- lic do driver #
- lics do driver #
- carteira de motorista #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving licence
- dlno #
- driv lic
- licencia de driv
- licença de driv
- licenças de driv
- driv licence
- licenças de driv
- driver licen
- drivers licen
- licenciador do driver
- lic de direção
- driving licen
- conduzir licenças
- driving licence
- driving licences
- permissão de direção
- dl no
- dlno
- dl number


#### <a name="keywords_slovenia_eu_drivers_license_number"></a>Keywords_slovenia_eu_driver s_license_number

- vozniško dovoljenje
- vozniška številka licence
- vozniških dovoljenj
- številka vozniškega dovoljenja
- številke vozniških dovoljenj

## <a name="slovenia-unique-master-citizen-number"></a>Número de cidadão mestre exclusivo da Eslovênia
Esse tipo de informação confidenciais só está disponível para uso em:
- políticas de prevenção contra perda de dados
- políticas de conformidade de comunicação
- governança de informações
- gerenciamento de registros
- Segurança do aplicativo na nuvem da Microsoft

### <a name="format"></a>Formatar

13 dígitos sem espaços ou delimitadores

### <a name="pattern"></a>Padrão

13 dígitos no padrão especificado:

- sete dígitos que correspondem à data de nascimento (DDMMLLL) em que "LLL" corresponde aos últimos três dígitos do ano de nascimento
- dois dígitos que correspondem à área de nascimento "50"
- três dígitos que correspondem a uma combinação de sexo e número de série para pessoas que nasceram no mesmo dia. 000-499 para homens e 500-999 para mulheres.
- um dígito de verificação

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_slovenia_eu_national_id_card` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de  `Keywords_slovenia_eu_national_id_card` é encontrada.

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
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

- edinstvena številka glavnega državljana
- emšo
- enotna maticna številka obcana
- id card
- identification number
- identifikacijska številka
- cartão de identidade
- nacionalna id
- lista nacionalni potni
- national id
- osebna izkaznica
- osebni koda
- osebni ne
- osebni številka
- código pessoal
- número pessoal
- código numérico pessoal
- številka državljana
- número de cidadão exclusivo
- número de ID exclusivo
- número de identidade exclusivo
- número de cidadão mestre exclusivo
- número de registro exclusivo
- uniqueidentityno #
- uniqueidentityno #

## <a name="slovenia-passport-number"></a>Número do passaporte eslovênia

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

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_slovenia_eu_passport_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave  `Keywords_eu_passport_number` de ou `Keywords_slovenia_eu_passport_number` é encontrada.
- A expressão regular `Regex_eu_passport_date1` localiza a data no formato DD.MM.YYYY ou uma palavra-chave de é `Keywords_eu_passport_date` encontrada

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_slovenia_eu_passport_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave  `Keywords_eu_passport_number` de ou `Keywords_slovenia_eu_passport_number` é encontrada.

```xml
      <!-- Slovenia Passport Number -->
      <Entity id="235b7976-7bbe-4df5-bb40-08678e749d1a" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_slovenia_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_eu_passport_date1" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_slovenia_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- números do passport

#### <a name="keywords_slovenia_eu_passport_number"></a>Keywords_slovenia_eu_passport_number

- številka potnega lista
- potek veljavnosti
- lista potni #
- datum rojstva
- lista potni
- številke potnih listov

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- data de emissão
- data de expiração


## <a name="slovenia-tax-identification-number"></a>Número de identificação fiscal da Eslovênia
Esse tipo de informação confidenciais só está disponível para uso em:
- políticas de prevenção contra perda de dados
- políticas de conformidade de comunicação
- governança de informações
- gerenciamento de registros
- Segurança do aplicativo na nuvem da Microsoft

### <a name="format"></a>Formatar

oito dígitos sem espaços ou delimitadores

### <a name="pattern"></a>Padrão

- um dígito de 1 a 9
- seis dígitos
- um dígito de verificação

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_slovenia_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de  `Keywords_slovenia_eu_tax_file_number` é encontrada.

Uma política de DLP tem baixa confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
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

- davčna številka
- identifikacijska številka davka
- številka davčne datoteke
- arquivo fiscal não
- tax file number
- tax id
- identificação de imposto não
- número de identificação fiscal
- tax no #
- tax no
- número de imposto
- número de registro fiscal
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- id de estanho
- tin no
- tin #


## <a name="south-africa-identification-number"></a>Número de identificação da África do Sul

### <a name="format"></a>Formatar

13 dígitos que podem conter espaços

### <a name="pattern"></a>Padrão

13 dígitos:
- seis dígitos no formato YYMMDD, que são a data de nascimento
- quatro dígitos
- um indicador de cidadania de um único dígito
- o dígito "8" ou "9"
- um dígito, que é um dígito checksum

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_south_africa_identification_number encontra conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_south_africa_identification_number é encontrada.
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
- Identificação

## <a name="south-korea-resident-registration-number"></a>Número de registro de residente da Coreia do Sul

### <a name="format"></a>Formatar

13 dígitos que contém um hifen

### <a name="pattern"></a>Padrão

13 dígitos:
- seis dígitos no formato YYMMDD, que são a data de nascimento
- um hífen
- um dígito determinado pelo século e pelo gênero
- código de região de nascimento de quatro dígitos
- um dígito usado para diferenciar pessoas para as quais os números anteriores são idênticos
- um dígito de verificação.

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_south_korea_resident_number localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave Keyword_south_korea_resident_number é encontrada.
- A soma de verificação passa.

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_south_korea_resident_number localiza conteúdo que corresponde ao padrão.
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

### <a name="format"></a>Formatar

oito dígitos seguidos por um caractere

### <a name="pattern"></a>Padrão

oito dígitos seguidos por um caractere:

- oito dígitos
- um dígito ou uma letra (não sensitivo para minúsculas)

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_spain_eu_DL_and_NI_number_citizen` ou localiza conteúdo que corresponde ao `Func_spain_eu_DL_and_NI_number_foreigner` padrão.
- Uma palavra-chave  `Keywords_eu_driver's_license_number` de ou `Keywords_spain_eu_driver's_license_number` é encontrada.

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_spain_eu_DL_and_NI_number_citizen` ou localiza conteúdo que corresponde ao `Func_spain_eu_DL_and_NI_number_foreigner` padrão.

```xml
      <!-- Spain Driver's License Number -->
      <Entity id="d5a82922-b501-4f40-8868-341321146aa2" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_spain_eu_driver's_license_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_citizen" />
        </Pattern>
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_foreigner" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_spain_eu_driver's_license_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_DL_and_NI_number_foreigner" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver'lic
- lics do driver
- driver'license
- driver'licenses
- driver'licence
- driver 'licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- lic do driver
- lics do driver
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver'lic #
- lics do driver #
- driver'license #
- driver'licenses #
- driver'licence #
- driver 'licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- lic do driver #
- lics do driver #
- carteira de motorista #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving licence
- dlno #
- driv lic
- licencia de driv
- licença de driv
- licenças de driv
- driv licence
- licenças de driv
- driver licen
- drivers licen
- licenciador do driver
- lic de direção
- driving licen
- conduzir licenças
- driving licence
- driving licences
- permissão de direção
- dl no
- dlno
- dl number


#### <a name="keywords_spain_eu_drivers_license_number"></a>Keywords_spain_eu_driver s_license_number

- permiso de conducción
- permiso conducción
- licencia de conducir
- licencia conducir
- permiso conducir
- permiso de conducir
- permisos de conducir
- permisos conducir
- carnet conducir
- carnet de conducir
- licencia de manejo
- licencia manejo

## <a name="spain-dni"></a>DNI da Espanha
Esse tipo de informação confidenciais só está disponível para uso em:
- políticas de prevenção contra perda de dados
- políticas de conformidade de comunicação
- governança de informações
- gerenciamento de registros
- Segurança do aplicativo na nuvem da Microsoft

### <a name="format"></a>Formatar

oito dígitos seguidos por um caractere

### <a name="pattern"></a>Padrão

sete dígitos seguidos por um caractere

- oito dígitos
- Um espaço opcional ou hífen
- uma letra de verificação (não sensível a minúsculas)

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_spain_eu_DL_and_NI_number_citizen` ou localiza conteúdo que corresponde ao `Func_spain_eu_DL_and_NI_number_foreigner` padrão.
- Uma palavra-chave de  `Keywords_spain_eu_national_id_card"` é encontrada.

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_spain_eu_DL_and_NI_number_citizen` ou localiza conteúdo que corresponde ao `Func_spain_eu_DL_and_NI_number_foreigner` padrão.


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

- carné de identidad
- dni #
- dni
- dninúmero #
- documento nacional de identidad
- identidad único
- identidadúnico #
- número do seguro
- national identification number
- identidade nacional
- nationalid #
- nationalidno #
- nie #
- nie
- nienúmero #
- número de identificación
- número nacional identidad
- número de identificação pessoal
- identidade pessoal não
- número de identidade exclusivo
- uniqueid #

## <a name="spain-passport-number"></a>Número do passaporte espanhol

### <a name="format"></a>Formatar

uma combinação de oito ou nove caracteres de letras e números sem espaços ou delimitadores

### <a name="pattern"></a>Padrão

uma combinação de oito ou nove caracteres de letras e números:

- dois dígitos ou letras
- um dígito ou letra (opcional)
- seis dígitos

### <a name="checksum"></a>Soma de verificação

Não se aplica

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_spain_eu_passport_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave  `Keywords_eu_passport_number` de ou `Keywords_spain_eu_passport_number` é encontrada.
- A expressão regular `Regex_spain_eu_passport_date` localiza a data no formato DD-MM-YYYY ou uma palavra-chave de é `Keywords_eu_passport_date` encontrada

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_spain_eu_passport_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave  `Keywords_eu_passport_number` de ou `Keywords_spain_eu_passport_number` é encontrada.

```xml
      <!-- Spain Passport Number -->
      <Entity id="d17a57de-9fa5-4e9f-85d3-85c26d89686e" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_spain_eu_passport_number" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_spain_eu_passport_date" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_spain_eu_passport_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- números do passport

#### <a name="keywords_spain_eu_passport_number"></a>Keywords_spain_eu_passport_number

- libreta pasaporte
- número pasaporte
- españa pasaporte
- números de pasaporte
- número de pasaporte
- números pasaporte
- pasaporte no
- Passeport n°
- n° Passeport
- pasaporte no.
- pasaporte n°
- espanha passport

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- data de emissão
- data de expiração


## <a name="spain-social-security-number-ssn"></a>Número de segurança social da Espanha (SSN)


### <a name="format"></a>Formatar

11 a 12 dígitos

### <a name="pattern"></a>Padrão

11 a 12 dígitos:
- dois dígitos
- uma barra de avanço (opcional)
- sete a oito dígitos
- uma barra de avanço (opcional)
- dois dígitos

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_spanish_social_security_number localiza conteúdo que corresponde ao padrão.
- A soma de verificação passa.
- - Uma palavra-chave de  `Keywords_spain_eu_ssn_or_equivalent` é encontrada.

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_spanish_social_security_number localiza conteúdo que corresponde ao padrão.
- A soma de verificação passa.

```xml
    <!-- Spain SSN -->
    <Entity id="5df987c0-8eae-4bce-ace7-b316347f3070" patternsProximity="300" recommendedConfidence="85" relaxProximity="true" >
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spanish_social_security_number" />
          <Match idRef="Keywords_spain_eu_ssn_or_equivalent" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spanish_social_security_number" />
        </Pattern>
    </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_spain_eu_passport_number"></a>Keywords_spain_eu_passport_number

- ssn
- ssn #
- socialsecurityno
- social security no
- social security number
- número de la seguridad social

## <a name="spain-tax-identification-number"></a>Número de identificação fiscal da Espanha
Esse tipo de informação confidenciais só está disponível para uso em:
- políticas de prevenção contra perda de dados
- políticas de conformidade de comunicação
- governança de informações
- gerenciamento de registros
- Segurança do aplicativo na nuvem da Microsoft

### <a name="format"></a>Formatar

sete ou oito dígitos e uma ou duas letras no padrão especificado

### <a name="pattern"></a>Padrão

Pessoas Naturais da Espanha com um Cartão de Identidade Nacional da Espanha:

- oito dígitos
- uma letra maiúscula (sensível a maiúsculas e minúsculas)

Não residentes em espanhol sem um Cartão de Identidade Nacional da Espanha

- uma letra maiúscula "L" (sensível a maiúsculas e minúsculas)
- sete dígitos
- uma letra maiúscula (sensível a maiúsculas e minúsculas)

Residentes espanheses menores de 14 anos sem um Cartão de Identidade Nacional da Espanha:

- uma letra maiúscula "K" (sensível a maiúsculas e minúsculas)
- sete dígitos
- uma letra maiúscula (sensível a maiúsculas e minúsculas)

Estrangeiros com um número de identificação de estrangeiro

- uma letra maiúscula que é "X", "Y" ou "Z" (sensível a maiúsculas e minúsculas)
- sete dígitos
- uma letra maiúscula (sensível a maiúsculas e minúsculas)

Estrangeiros sem um Número de Identificação de Estrangeiro

- uma letra maiúscula que é "M" (sensível a maiúsculas e minúsculas)
- sete dígitos
- uma letra maiúscula (sensível a maiúsculas e minúsculas)

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_spain_eu_tax_file_number` ou localiza conteúdo que corresponde ao `Func_spain_eu_DL_and_NI_number_citizen` padrão.
- Uma palavra-chave de  `Keywords_spain_eu_tax_file_number` é encontrada.

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_spain_eu_tax_file_number` ou localiza conteúdo que corresponde ao `Func_spain_eu_DL_and_NI_number_citizen` padrão.

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

- cif
- cifid #
- cifnúmero #
- número de contribuyente
- número de identificación fiscal
- número de impuesto corporativo
- spanishcifid #
- spanishcifid
- spanishcifno #
- spanishcifno
- arquivo fiscal não
- tax file number
- tax id
- identificação de imposto não
- número de identificação fiscal
- tax no #
- tax no
- número de imposto
- número de registro fiscal
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- id de estanho
- tin no
- tin #


## <a name="sql-server-connection-string"></a>SQL Server de conexão

### <a name="format"></a>Formatar

A cadeia de caracteres "ID do usuário", "ID do usuário", "uid" ou "UserId" seguida pelos caracteres e cadeias de caracteres descritos no padrão abaixo.

### <a name="pattern"></a>Padrão

- a cadeia de caracteres "ID do usuário", "ID do usuário", "uid" ou "UserId"
- qualquer combinação de entre 1 a 200 letras minúsculas ou maiúsculas, dígitos, símbolos, caracteres especiais ou espaços
- a cadeia de caracteres "Password" ou "pwd" onde "pwd" não é precedida por uma letra minúscula
- um sinal de igual (=)
- qualquer caractere que não seja um sinal de dólar ($), símbolo de porcentagem (%), maior que o símbolo (>), em símbolo (@), ponto de aspas ("), ponto e vírgula (;), chave esquerda([) ou colchete esquerdo ({)
- qualquer combinação de 7 a 128 caracteres que não sejam ponto e vírgula (;), barra (/) ou aspas (")
- um ponto e vírgula (;) ou aspas (")

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular CEP_Regex_SQLServerConnectionString encontra conteúdo que corresponde ao padrão.
- Uma palavra-chave CEP_GlobalFilter não foi encontrada.
- A expressão regular CEP_PasswordPlaceHolder não encontra conteúdo que corresponde ao padrão.
- A expressão regular CEP_CommonExampleKeywords não encontra conteúdo que corresponde ao padrão.

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

- some-password
- somepassword
- secretPassword
- sample

#### <a name="cep_passwordplaceholder"></a>CEP_PasswordPlaceHolder

Esse tipo de informação sensível identifica essas palavras-chave usando uma expressão regular, não uma lista de palavras-chave.

- Senha ou pwd seguido por espaços 0-2, um sinal de igual (=), espaços de 0-2 e um asterisco (*) -OR-
- Senha ou pwd seguido por:
    - Sinal de igual (=)
    - Menor que o símbolo (<)
    - Qualquer combinação de 1 a 200 caracteres que sejam letras maiúsculas ou minúsculas, dígitos, um asterisco (*), hífen (-), sublinhado (_) ou caractere de espaço em branco
    - Maior que o símbolo (>)

#### <a name="cep_commonexamplekeywords"></a>CEP_CommonExampleKeywords

Esse tipo de informação sensível identifica essas palavras-chave usando uma expressão regular, não uma lista de palavras-chave.

- contoso
- fabrikam
- northwind
- sandbox
- onebox
- localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->com
- s-int.<!--no-hyperlink-->net

## <a name="sweden-drivers-license-number"></a>Número da carteira de motorista da Suécia

### <a name="format"></a>Formatar

10 dígitos que contêm um hífen

### <a name="pattern"></a>Padrão

10 dígitos contendo um hífen:

- seis dígitos
- um hífen
- quatro dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular  `Regex_sweden_eu_driver's_license_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave  `Keywords_eu_driver's_license_number` de ou `Keywords_sweden_eu_driver's_license_number` é encontrada.

```xml
      <!-- Sweden Driver's License Number -->
      <Entity id="70088720-90dd-47f5-805e-5525f3567391" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_driver's_license_number" />
            <Match idRef="Keywords_sweden_eu_driver's_license_number" />
          </Any>
        </Pattern>
      </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver'lic
- lics do driver
- driver'license
- driver'licenses
- driver'licence
- driver 'licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- lic do driver
- lics do driver
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver'lic #
- lics do driver #
- driver'license #
- driver'licenses #
- driver'licence #
- driver 'licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- lic do driver #
- lics do driver #
- carteira de motorista #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving licence
- dlno #
- driv lic
- licencia de driv
- licença de driv
- licenças de driv
- driv licence
- licenças de driv
- driver licen
- drivers licen
- licenciador do driver
- lic de direção
- driving licen
- conduzir licenças
- driving licence
- driving licences
- permissão de direção
- dl no
- dlno
- dl number


#### <a name="keywords_sweden_eu_drivers_license_number"></a>Keywords_sweden_eu_driver s_license_number

- ajokortti
- permis de conducere
- ajokortin numero
- kuljettajat lic.
- drivere lic.
- körkort
- numărul permisului de conducere
-  שאָפער דערלויבעניש נומער
- förare lic.
-  דריווערס דערלויבעניש
- körkortsnummer

## <a name="sweden-national-id"></a>ID nacional da Suécia

### <a name="format"></a>Formatar

10 ou 12 dígitos e um delimitador opcional

### <a name="pattern"></a>Padrão

10 ou 12 dígitos e um delimitador opcional:
- dois dígitos (opcional)
- Seis dígitos no formato de data AAMMDD
- delimiter de "-" ou "+" (opcional)
- quatro dígitos

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função `Func_swedish_national_identifier` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave `Keywords_swedish_national_identifier` de é encontrada
- A soma de verificação passa.

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
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

- id no
- número de id
- id #
- identificação não
- identification number
- identifikationsnumret #
- identifikationsnumret
- identitetshandling
- documento de identidade
- identity no
- número de identidade
- id-nummer
- id pessoal
- personnummer #
- personnummer
- skatteidentifikationsnummer

## <a name="sweden-passport-number"></a>Número do passaporte da Suécia

### <a name="format"></a>Formatar

oito dígitos

### <a name="pattern"></a>Padrão

oito dígitos consecutivos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- a expressão regular Regex_sweden_passport_number encontra conteúdo que corresponde ao padrão.
- uma palavra-chave `Keywords_eu_passport_number` de ou `Keyword_sweden_passport` é encontrada.
- a expressão regular localiza uma data no formato `Regex_sweden_eu_passport_date` DD MMM/MMM YY (01 JAN/JAN 12) ou uma palavra-chave de `Keywords_eu_passport_date` é encontrada.

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- a expressão regular Regex_sweden_passport_number encontra conteúdo que corresponde ao padrão.
- uma palavra-chave `Keywords_eu_passport_number` de ou `Keyword_sweden_passport` é encontrada.


```xml
    <!-- Sweden Passport Number -->
    <Entity id="ba4e7456-55a9-4d89-9140-c33673553526" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Regex_sweden_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keyword_sweden_passport" />
          </Any>
          <Any minMatches="1">
            <Match idRef="Regex_sweden_eu_passport_date" />
            <Match idRef="Keywords_eu_passport_date" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_passport_number" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keyword_sweden_passport" />
          </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- números do passport

#### <a name="keyword_sweden_passport"></a>Keyword_sweden_passport

- cartão de registro alien
- Taxas de processamento g3
- multiple entry
- Numéro de passeport
- passeport n °
- passeport non
- passeport #
- passeport #
- passeportnon
- passeportn °
- passnummer
- passar nr
- Visto schengen
- Vistos schengen
- entrada única
- Sverige pass
- visa requirements
- processamento de vistos
- tipo de visto

#### <a name="keywords_eu_passport_date"></a>Keywords_eu_passport_date

- data de emissão
- data de expiração


## <a name="sweden-tax-identification-number"></a>Número de identificação fiscal da Suécia
Esse tipo de informação confidenciais só está disponível para uso em:
- políticas de prevenção contra perda de dados
- políticas de conformidade de comunicação
- governança de informações
- gerenciamento de registros
- Segurança do aplicativo na nuvem da Microsoft

### <a name="format"></a>Formatar

10 dígitos e um símbolo no padrão especificado

### <a name="pattern"></a>Padrão

10 dígitos e um símbolo:

- seis dígitos que correspondem à data de nascimento (YYMMDD)
- um sinal de a mais ou sinal de menos
- três dígitos que fazem com que o número de identificação seja exclusivo em que:
  - para números emitidos antes de 1990, o sétimo e oitavo dígito identificam o município de nascimento ou pessoas de origem estrangeira
  - o dígito na nona posição indica o sexo por ímpar para o sexo masculino ou até mesmo para mulheres
- um dígito de verificação

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_sweden_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de  `Keywords_sweden_eu_tax_file_number` é encontrada.

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
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

- número de ID pessoal
- personnummer
- Númem de id skatt
- skatt identifikation
- skattebetalarens identifikationsnummer
- sverige tin
- arquivo fiscal
- tax id
- identificação de imposto não
- número de identificação fiscal
- tax no #
- tax no
- número de imposto
- número de registro fiscal
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- id de estanho
- tin no
- tin #


## <a name="swift-code"></a>Código SWIFT

### <a name="format"></a>Formatar

quatro letras seguidas de 5 a 31 letras ou dígitos

### <a name="pattern"></a>Padrão

quatro letras seguidas de 5 a 31 letras ou dígitos:
- código bancário de quatro letras (não sensível a minúsculas)
- um espaço opcional
- 4 a 28 letras ou dígitos (o número de conta bancária básica (BBAN))
- um espaço opcional
- de uma a três letras ou dígitos (restante do BBAN)

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
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
- swift #
- swiftcode
- swiftnumber
- swiftroutingnumber
- swift code
- swift number #
- swift routing number
- bic number
- bic code
- bic #
- bic #
- bank identifier code
- Organisation internationale de normalisation 9362
- rapide #
- code SWIFT
- le numéro de swift
- swift numéro d'acheminement
- le numéro BIC
- # <a name="bic"></a>BIC
- code identificateur de banque
- SWIFTコ ド
- SWIFT番号
- BIC番号
- BICコ ド
- SWIFT コ ド
- SWIFT 番号
- BIC 番号
- BIC コ ド
- 金融機関識別コード
- 金融機関コード
- 銀行コード

## <a name="switzerland-ssn-ahv-number"></a>Número SSN AHV da Suíça
Esse tipo de informação confidenciais só está disponível para uso em:
- políticas de prevenção contra perda de dados
- políticas de conformidade de comunicação
- governança de informações
- gerenciamento de registros
- Segurança do aplicativo na nuvem da Microsoft

### <a name="format"></a>Formatar

Número de 13 dígitos

### <a name="pattern"></a>Padrão

Número de 13 dígitos:

- três dígitos - 756
- um ponto opcional
- quatro dígitos
- um ponto opcional
- quatro dígitos
- um ponto opcional
- dois dígitos

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_swiss_social_security_number_ahv encontra conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keywords_swiss_social_security_number_ahv é encontrada.

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_swiss_social_security_number_ahv encontra conteúdo que corresponde ao padrão.

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
- ssn
- pid
- número do seguro
- personalidno #
- social security number
- número de ID pessoal
- identificação pessoal não.
- insuranceno #
- uniqueidno #
- identificação exclusiva não.
- número avs
- identidade pessoal nenhum versicherungsnummer
- identifikationsnummer
- einzigartige identität nicht
- sozialversicherungsnummer
- id de equipe de identificação
- numéro de sécurité sociale


## <a name="taiwan-national-identification-number"></a>Número de identificação nacional de Taiwan

### <a name="format"></a>Formatar

uma letra (em inglês) seguida de nove dígitos

### <a name="pattern"></a>Padrão

uma letra (em inglês) seguida de nove dígitos:
- uma letra (em inglês, não sensível a minúsculas)
- o dígito "1" ou "2"
- oito dígitos

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_taiwanese_national_id localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_taiwanese_national_id for encontrada.
- A soma de verificação passa.

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
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

## <a name="taiwan-passport-number"></a>Número do passaporte de Taiwan

### <a name="format"></a>Formatar

- número do passaporte biométrico: nove dígitos
- número do passaporte não biométrico: nove dígitos

### <a name="pattern"></a>Padrão
número do passaporte biométrico:
- o caractere "3"
- oito dígitos

número do passaporte não biométrico:
- nove dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular Regex_taiwan_passport encontra conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_taiwan_passport é encontrada.

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

## <a name="taiwan-resident-certificate-arctarc-number"></a>Número de certificado residente em Taiwan (ARC/TARC)

### <a name="format"></a>Formatar

10 letras e dígitos

### <a name="pattern"></a>Padrão

10 letras e dígitos:
- duas letras (não sensíveis a maiúsculas e minúsculas)
- oito dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular Regex_taiwan_resident_certificate encontra conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_taiwan_resident_certificate é encontrada.

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

## <a name="thai-population-identification-code"></a>Código de identificação da população tailandesa

### <a name="format"></a>Formatar

13 dígitos

### <a name="pattern"></a>Padrão

13 dígitos:
- primeiro dígito não é zero ou nove
- 12 dígitos

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_Thai_Citizen_Id localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_Thai_Citizen_Id é encontrada.

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_Thai_Citizen_Id localiza conteúdo que corresponde ao padrão.

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

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_Turkish_National_Id localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_Turkish_National_Id é encontrada.

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_Turkish_National_Id localiza conteúdo que corresponde ao padrão.

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

- TC Kimlik No
- TC Kimlik numarası
- Vatandaşlık numarası
- Vatandaşlık no

## <a name="uk-drivers-license-number"></a>Reino Unido número da licença do driver

### <a name="format"></a>Formatar

Combinação de 18 letras e dígitos no formato especificado

### <a name="pattern"></a>Padrão

18 letras e dígitos:
- Cinco letras (não sensíveis a maiúsculas e minúsculas) ou o dígito "9" no lugar de uma letra.
- Um dígito.
- Cinco dígitos no formato de data MMDDY para a data de nascimento. O sétimo caractere será incrementado em 50 se driver for do sexo feminino; para exame, 51 a 62 em vez de 01 a 12.
- Duas letras (não sensíveis a maiúsculas e minúsculas) ou o dígito "9" no lugar de uma letra.
- Cinco dígitos.

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função `Func_uk_drivers_license` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de `Keywords_eu_driver's_license_number` é encontrada.
- A soma de verificação passa.

Uma política de DLP tem baixa confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função `Func_uk_drivers_license` localiza conteúdo que corresponde ao padrão.
- A soma de verificação passa.

```xml
    <!-- U.K. Driver's License Number -->
    <Entity id="f93de4be-d94c-40df-a8be-461738047551" patternsProximity="300" recommendedConfidence="75" relaxProximity="true" >
      <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_uk_drivers_license" />
          <Match idRef="Keywords_eu_driver's_license_number" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Func_uk_drivers_license" />
        </Pattern>
    </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_eu_drivers_license_number"></a>Keywords_eu_driver s_license_number

- driverlic
- driverlics
- driverlicense
- driverlicenses
- driverlicence
- driverlicences
- driver lic
- driver lics
- driver license
- driver licenses
- driver licence
- driver licences
- driverslic
- driverslics
- driverslicence
- driverslicences
- driverslicense
- driverslicenses
- drivers lic
- drivers lics
- drivers license
- drivers licenses
- drivers licence
- drivers licences
- driver'lic
- driver'lics
- driver'license
- driver'licenses
- driver'licence
- driver'licences
- driver'lic
- lics do driver
- driver'license
- driver'licenses
- driver'licence
- driver 'licences
- driver'slic
- driver'slics
- driver'slicense
- driver'slicenses
- driver'slicence
- driver'slicences
- lic do driver
- lics do driver
- driver's license
- driver's licenses
- driver's licence
- driver's licences
- dl #
- dls #
- driverlic #
- driverlics #
- driverlicense #
- driverlicenses #
- driverlicence #
- driverlicences #
- driver lic #
- driver lics #
- driver license #
- driver licenses #
- driver licences #
- driverslic #
- driverslics #
- driverslicense #
- driverslicenses #
- driverslicence #
- driverslicences #
- drivers lic #
- drivers lics #
- drivers license #
- drivers licenses #
- drivers licence #
- drivers licences #
- driver'lic #
- driver'lics #
- driver'license #
- driver'licenses #
- driver'licence #
- driver'licences #
- driver'lic #
- lics do driver #
- driver'license #
- driver'licenses #
- driver'licence #
- driver 'licences #
- driver'slic #
- driver'slics #
- driver'slicense #
- driver'slicenses #
- driver'slicence #
- driver'slicences #
- lic do driver #
- lics do driver #
- carteira de motorista #
- driver's licenses #
- driver's licence #
- driver's licences #
- driving licence 
- driving licence
- dlno #
- driv lic
- licencia de driv
- licença de driv
- licenças de driv
- driv licence
- licenças de driv
- driver licen
- drivers licen
- licenciador do driver
- lic de direção
- driving licen
- conduzir licenças
- driving licence
- driving licences
- permissão de direção
- dl no
- dlno
- dl number


## <a name="uk-electoral-roll-number"></a>Reino Unido número de rolagem de eleitores

### <a name="format"></a>Formatar

duas letras seguidas de 1 a 4 dígitos

### <a name="pattern"></a>Padrão

duas letras (não sensíveis a maiúsculas e minúsculas) seguidas de números de 1 a 4

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
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


## <a name="uk-national-health-service-number"></a>Reino Unido número do serviço de saúde nacional

### <a name="format"></a>Formatar

10 a 17 dígitos separados por espaços

### <a name="pattern"></a>Padrão

10 a 17 dígitos:
- 3 ou 10 dígitos
- um espaço
- três dígitos
- um espaço
- quatro dígitos

### <a name="checksum"></a>Soma de verificação

Sim

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
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
- nhs
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
- D.O.B
- Date of Birth
- Birth Date

## <a name="uk-national-insurance-number-nino"></a>Reino Unido número de seguro nacional (NINO)
Essa entidade de tipo de informação confidenciais está incluída no tipo de informação confidenciais número de identificação nacional da UE. Ele também está disponível como uma entidade de tipo de informação independente e confidenciais.

### <a name="format"></a>Formatar

sete caracteres ou nove caracteres separados por espaços ou traços

### <a name="pattern"></a>Padrão

dois padrões possíveis:

- duas letras (NINOs válidos usam apenas determinados caracteres neste prefixo, que esse padrão valida; não é sensível a maiúsculas e minúsculas)
- seis dígitos
- 'A', 'B', 'C' ou 'D' (como o prefixo, apenas determinados caracteres são permitidos no sufixo; não são sensíveis a minúsculas)

OU

- duas letras
- um espaço ou traço
- dois dígitos
- um espaço ou traço
- dois dígitos
- um espaço ou traço
- dois dígitos
- um espaço ou traço
- 'A', 'B', 'C' ou 'D'

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_uk_nino localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_uk_nino for encontrada.

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_uk_nino localiza conteúdo que corresponde ao padrão.

```xml
    <!-- U.K. NINO -->
    <Entity id="16c07343-c26f-49d2-a987-3daf717e94cc" patternsProximity="300" recommendedConfidence="75" relaxProximity="true">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_uk_nino" />
        <Match idRef="Keyword_uk_nino" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_nino" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_uk_nino"></a>Keyword_uk_nino

- national insurance number
- national insurance contributions
- protection act
- insurance
- social security number
- insurance application
- medical application
- social insurance
- medical attention
- social security
- great britain
- Número de NI
- NI No.
- NI #
- NI #
- insurance #
- insurancenumber
- nationalinsurance #
- nationalinsurancenumber


## <a name="uk-unique-taxpayer-reference-number"></a>Reino Unido Número de referência exclusivo do contribuinte
Esse tipo de informação confidenciais só está disponível para uso em:
- políticas de prevenção contra perda de dados
- políticas de conformidade de comunicação
- governança de informações
- gerenciamento de registros
- Segurança do aplicativo na nuvem da Microsoft

### <a name="format"></a>Formatar

10 dígitos sem espaços e delimitadores


### <a name="pattern"></a>Padrão

10 dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função  `Func_uk_eu_tax_file_number` localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de  `Keywords_uk_eu_tax_file_number` é encontrada.

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

- número de imposto
- arquivo fiscal
- tax id
- identificação de imposto não
- número de identificação fiscal
- tax no #
- tax no
- número de registro fiscal
- taxid #
- taxidno #
- taxidnumber #
- taxno #
- taxnumber #
- taxnumber
- id de estanho
- tin no
- tin #

## <a name="us-bank-account-number"></a>Número da conta bancária dos EUA

### <a name="format"></a>Formatar

6 a 17 dígitos

### <a name="pattern"></a>Padrão

6 a 17 dígitos consecutivos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
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

depende do estado - por exemplo, Nova York:
- nove dígitos formatados como ddd ddd ddd corresponderão.
- nove dígitos como dddddddddd não corresponderão.

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_new_york_drivers_license_number localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_[state_name]_drivers_license_name for encontrada.
- Uma palavra-chave Keyword_us_drivers_license é encontrada.

Uma política de DLP tem baixa confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
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

- DL
- DLS
- CDL
- CDLS
- ID
- IDs
- DL #
- DLS #
- CDL #
- CDLS #
- ID #
- IDs #
- ID number
- ID numbers
- LIC
- LIC #

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


#### <a name="keyword_state_name_drivers_license_name"></a>Keyword_[state_name]_drivers_license_name

- abreviação de estado (por exemplo, "NY")
- nome do estado (por exemplo, "Nova York")

## <a name="us-individual-taxpayer-identification-number-itin"></a>NÚMERO DE IDENTIFICAÇÃO individual do contribuinte (ITIN) dos EUA

### <a name="format"></a>Formatar

nove dígitos que começam com um "9" e contêm "7" ou "8" como o quarto dígito, opcionalmente formatados com espaços ou traços

### <a name="pattern"></a>Padrão

formatado:
- o dígito "9"
- dois dígitos
- um espaço ou traço
- um "7" ou "8"
- um dígito
- um espaço ou traço
- quatro dígitos

não formatado:
- o dígito "9"
- dois dígitos
- um "7" ou "8"
- cinco dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_formatted_itin localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_itin for encontrada.

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_unformatted_itin localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_itin for encontrada.

Uma política de DLP tem baixa confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_formatted_itin ou Func_unformatted_itin o conteúdo que corresponde ao padrão.

```xml
    <!-- U.S. Individual Taxpayer Identification Number (ITIN) -->
    <Entity id="e55e2a32-f92d-4985-a35d-a0b269eb687b" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_formatted_itin" />
        <Match idRef="Keyword_itin" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_itin" />
        <Match idRef="Keyword_itin" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_formatted_itin" />
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_unformatted_itin" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_itin"></a>Keyword_itin

- taxpayer
- tax id
- tax identification
- itin
- i.t.i.n.
- ssn
- tin
- social security
- tax payer
- itins
- taxid
- individual taxpayer


## <a name="us-social-security-number-ssn"></a>Número de segurança social dos EUA (SSN)

### <a name="format"></a>Formatar

nove dígitos, que podem estar em um padrão formatado ou não formatado

> [!NOTE]
> Se emitido antes de meados de 2011, um SSN tem uma formatação forte onde determinadas partes do número devem estar dentro de determinados intervalos para serem válidas (mas não há nenhum checksum).

### <a name="pattern"></a>Padrão

quatro funções procurar por SSNs em quatro padrões diferentes:
- Func_ssn localiza SSNs com formatação forte pré-2011 formatada com traços ou espaços (ddd-dddd OR ddd ddd ddd)
- Func_unformatted_ssn localiza SSNs com formatação forte pré-2011 que não são formatados como nove dígitos consecutivos (dddddddd)
- Func_randomized_formatted_ssn localiza SSNs post-2011 que são formatados com traços ou espaços (ddd-dd-dddd OR ddd dddd)
- Func_randomized_unformatted_ssn localiza SSNs pós-2011 não formatados como nove dígitos consecutivos (dddddddddd)

### <a name="checksum"></a>Soma de verificação

Não


### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_ssn localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_ssn for encontrada.

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_unformatted_ssn encontra conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_ssn for encontrada.

Uma política de DLP tem baixa confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_randomized_formatted_ssn localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_ssn for encontrada.

Uma política de DLP tem baixa confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
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

- Número SSA
- social security number
- segurança social #
- segurança social #
- social security no
- Social Security#
- Soc Sec
- SSN
- SSNS
- SSN #
- SS #
- SSID

## <a name="us--uk-passport-number"></a>EUA / Reino Unido. passport number

### <a name="format"></a>Formatar

nove dígitos

### <a name="pattern"></a>Padrão

nove dígitos consecutivos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política DLP tem alta confiança de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_usa_uk_passport localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave `Keywords_eu_passport_number` de ou `Keywords_uk_eu_passport_number` é encontrada.
- Uma palavra-chave `Keywords_eu_passport_date` de é encontrada

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A função Func_usa_uk_passport localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave `Keywords_eu_passport_number` de ou `Keywords_uk_eu_passport_number` é encontrada.

```xml
    <!-- U.S. / U.K. Passport Number -->
    <Entity id="178ec42a-18b4-47cc-85c7-d62c92fd67f8" patternsProximity="300" recommendedConfidence="75">
       <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_usa_uk_passport" />
          <Match idRef="Keywords_eu_passport_date" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_uk_eu_passport_number" />
          </Any>
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_usa_uk_passport" />
          <Any minMatches="1">
            <Match idRef="Keywords_eu_passport_number" />
            <Match idRef="Keywords_uk_eu_passport_number" />
          </Any>
        </Pattern>
    </Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_eu_passport_number"></a>Keywords_eu_passport_number

- passport #
- passport #
- passportid
- passports
- passportno
- passport no
- passportnumber
- passport number
- passportnumbers
- números do passport

#### <a name="keywords_uk_eu_passport_number"></a>Keywords_uk_eu_passport_number

- passaporte britânico
- uk passport


## <a name="ukraine-passport-domestic"></a>Passaporte ucraniano doméstico
Esse tipo de informação confidenciais só está disponível para uso em:
- políticas de prevenção contra perda de dados
- políticas de conformidade de comunicação
- governança de informações
- gerenciamento de registros
- Segurança do aplicativo na nuvem da Microsoft

### <a name="format"></a>Formatar

nove dígitos

### <a name="pattern"></a>Padrão

nove dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- O Regex_Ukraine_Passport_Domestic regex localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_Ukraine_Passport_Domestic é encontrada.

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

- passaporte ucraniano
- passport number
- passport no
- паспорт України
- номер паспорта
- персональний


## <a name="ukraine-passport-international"></a>Passaporte ucraniano internacional
Esse tipo de informação confidenciais só está disponível para uso em:
- políticas de prevenção contra perda de dados
- políticas de conformidade de comunicação
- governança de informações
- gerenciamento de registros
- Segurança do aplicativo na nuvem da Microsoft

### <a name="format"></a>Formatar

padrão alfanumérico de oito caracteres

### <a name="pattern"></a>Padrão

padrão alfanumérico de oito caracteres:
- duas letras ou dígitos
- seis dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- O Regex_Ukraine_Passport_International regex localiza conteúdo que corresponde ao padrão.
- Uma palavra-chave de Keyword_Ukraine_Passport_International é encontrada.

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

- passaporte ucraniano
- passport number
- passport no
- паспорт України
- номер паспорта
