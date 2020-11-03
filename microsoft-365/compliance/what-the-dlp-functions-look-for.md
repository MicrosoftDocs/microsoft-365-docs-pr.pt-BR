---
title: O que as funções de prevenção de perda de dados (DLP) procuram
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Saiba o que as funções de prevenção de perda de dados (DLP) procuram.
ms.openlocfilehash: b77075b0b31ad5d6e6e2b7062c35e96649fa8365
ms.sourcegitcommit: e56894917d2aae05705c3b9447388d10e2156183
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841442"
---
# <a name="what-the-dlp-functions-look-for"></a>O que as funções DLP procuram

As políticas de prevenção contra perda de dados (DLP) podem usar tipos de informações confidenciais para identificar itens confidenciais. Número do cartão de crédito e número de cartão de débito da UE são exemplos de tipos de informações confidenciais. Os tipos de informações confidenciais procuram padrões específicos. Os tipos de informações confidenciais validam os dados examinando o formato, são somas de verificação e procuram palavras-chave relevantes ou outras informações. Algumas dessas funcionalidades são realizadas por funções internas. Por exemplo, o tipo de informação confidencial número do cartão de crédito usa uma função para procurar datas que são formatadas como uma data de vencimento. Isso ajuda a corroborate que um número é um número de cartão de crédito.
  
Este artigo explica o que essas funções procuram para ajudá-lo a entender como funcionam os tipos de informações confidenciais predefinidos. Para mais informações, consulte [definições de entidade de tipo de informação confidencial](sensitive-information-type-entity-definitions.md)
  
## <a name="table-of-functions"></a>Tabela de funções

|nome da função  |ação de função  |é um validador|
|---------|---------|---------|
|Func_Argentina_Unique_Tax_Key|detecta e valida a chave de imposto exclusiva da Argentina|não|
|Func_aba_routing|detecta o número de roteamento ABA| sim|
|Func_alabama_drivers_license_number|detecta o número da carteira de motorista do Alabama|não|
|Func_alaska_delaware_oregon_drivers_license_number|detecta o Alasca, Delaware, número da carteira de motorista do driver de Oregon|não|
|Func_alaska_drivers_license_number|detecta o número da carteira de motorista do Alasca|não|
|Func_alberta_drivers_license_number|detecta o número da carteira de motorista de Alberta|não|
|Func_Argentina_Unique_Tax_Key|detecta a chave de imposto exclusiva da Argentina|não|
|Func_arizona_drivers_license_number|detecta o número da carteira de motorista do Arizona|não|
|Func_arkansas_drivers_license_number|detecta o número da carteira de motorista do Arkansas|não|
|Func_australian_business_number|detecta o número de empresa da Austrália|não|
|Func_Australian_Company_Number|detecta o número da empresa Austrália|não|
|Func_australian_medical_account_number|detecta o número da conta médica da Austrália|não|
|Func_australian_tax_file_number|detecta o número de arquivo de imposto Austrália|sim|
|Func_austria_eu_ssn_or_equivalent|detecta o número de segurança social da Áustria|não|
|Func_austria_eu_tax_file_number|detecta o número de arquivo de imposto da Áustria|não|
|Func_Austria_Value_Added_Tax|detecta o imposto sobre valor agregado da Áustria|não|
|Func_belgium_national_number|detecta o número nacional da Bélgica|não|
|Func_belgium_value_added_tax_number|detecta o número de imposto adicionado ao valor da Bélgica|não|
|Func_brazil_cnpj|detecta o número de entidade legal (CNPJ) do Brasil|sim|
|Func_brazil_cpf|detecta CPF do Brasil|sim|
|Func_brazil_rg|detecta o Brasil RG|não|
|Func_british_columbia_drivers_license_number|detecta o número da carteira de motorista British Columbia|não|
|Func_bulgaria_eu_national_id_card|detecta o número civil uniforme da Bulgária|não|
|Func_california_drivers_license_number|detecta o número da carteira de motorista da Califórnia|não|
|Func_canadian_sin|detecta o Sin do Canadá|sim|
|Func_chile_id_card|detecta o cartão de ID do Chile|não|
|Func_china_resident_id|detecta o ID residente da China|não|
|Func_colorado_drivers_license_number|detecta o número da carteira de motorista da Colorado|não|
|Func_connecticut_drivers_license_number|detecta o número da carteira de motorista do Connecticut|não|
|Func_credit_card|detecta cartão de crédito|sim|não|
|Func_croatia_id_card|detecta o cartão de ID da Croácia|não|
|Func_croatia_oib_number|detecta o número da Croácia NIB|não|
|Func_cyprus_eu_tax_file_number|detecta o número de arquivo de impostos do Chipre|não|
|Func_czech_id_card|detecta o cartão de ID tcheco|não|
|Func_czech_id_card_new_format|detecta o cartão de identificação tcheco no novo formato|não|
|Func_dea_number|detecta o número do DEA|sim|
|Func_denmark_eu_tax_file_number|detecta o número de identificação pessoal da Dinamarca|não|
|Func_district_of_columbia_drivers_license_number|detecta o distrito do número da carteira de motorista da Colúmbia|não|
|Func_estonia_eu_national_id_card|detecta o código de identificação pessoal da Estônia|não|
|Func_eu_debit_card|detecta o cartão de débito da UE|não|
|Func_finnish_national_id|detecta a ID nacional finlandesa|não|
|Func_florida_drivers_license_number|detecta o número da carteira de motorista da Flórida|não|
|Func_florida_maryland_michigan_minnesota_drivers_license_number|detecta o número da carteira de motorista da Flórida, Maryland, Michigan e Minnesota|não|
|Func_formatted_itin|detecta o formato ITIN EUA|sim|
|Func_fr_insee|detecta INSEE da França|não|
|Func_fr_passport|detecta o Passport da França|não|
|Func_france_eu_tax_file_number|detecta o número de arquivo de impostos da França|não|
|Func_france_value_added_tax_number|detecta o número do imposto sobre valor da França|não|
|Func_french_drivers_license|detecta a licença do motorista francês|não|
|Func_french_insee|detecta o INSEE francês|não|
|Func_georgia_drivers_license_number|detecta o número da carteira de motorista da Geórgia|não|
|Func_german_drivers_license|detecta a licença do driver da Alemanha|não|
|Func_german_passport|detecta o Passport da Alemanha|não|
|Func_german_passport_data|detecta o Passport da Alemanha|não|
|Func_germany_eu_tax_file_number|detecta o número de arquivo de imposto da Alemanha|não|
|Func_germany_value_added_tax_number|detecta o número do imposto sobre valor agregado da Alemanha|não|
|Func_greece_eu_ssn|detecta o Grécia sin (AMKA)|não|
|Func_hawaii_drivers_license_number|detecta o número da carteira de motorista do Havaí|não|
|Func_hong_kong_id_card |detecta o cartão de ID de Hong Kong|não|
|Func_hungarian_value_added_tax_number|detecta o número de imposto adicionado ao valor Hungria|não|
|Func_hungary_eu_national_id_card|detecta o número de identificação pessoal da Hungria|não|
|Func_hungary_eu_ssn_or_equivalent|detecta o número de segurança social da Hungria|não|
|Func_hungary_eu_tax_file_number|detecta o número de arquivo de imposto Hungria|não|
|Func_iban|detecta o IBAN|sim|
|Func_idaho_drivers_license_number|detecta o número da carteira de motorista do Idaho|não|
|Func_illinois_drivers_license_number|detecta o número da carteira de motorista de Illinois|não|
|Func_india_aadhaar|detecta o aadhaar da Índia|sim|
|Func_indiana_drivers_license_number|detecta o número da carteira de motorista de Indiana|não|
|Func_iowa_drivers_license_number|detecta o número da carteira de motorista do Iowa|não|
|Func_ireland_pps|detecta PPS da Irlanda|não|
|Func_israeli_national_id_number|detecta o número de ID nacional de Israel|não|
|Func_italy_eu_national_id_card |detecta o código fiscal da Itália|não|
|Func_italy_value_added_tax_number|detecta o número de imposto adicionado ao valor da Itália|não|
|Func_japanese_my_number_corporate|detecta o meu número corporativo do Japão|sim|
|Func_japanese_my_number_personal|detecta o meu número pessoal do Japão|sim|
|Func_jp_bank_account|detecta a conta bancária do Japão|não|
|Func_jp_bank_account_branch_code|detecta o código de filial da conta bancária do Japão|não|
|Func_jp_drivers_license_number|detecta o número da carteira de motorista do Japão|não|
|Func_jp_passport|detecta o passaporte do Japão|não|
|Func_jp_resident_registration_number|detecta o número de registro residente no Japão|não|
|Func_jp_sin|detecta o SIN Japão|não|
|Func_jp_sin_pre_1997|detecta o Japão Sin pre 1997|não|
|Func_kansas_drivers_license_number|detecta o número da carteira de motorista do Kansas|não|
|Func_kentucky_drivers_license_number|detecta o número da carteira de motorista do Kentucky|não|
|Func_kentucky_massachusetts_virginia_drivers_license_number|detecta o Kentucky, Massachusetts, número de carteira de motorista do driver da Virgínia|não|
|Func_latvia_eu_national_id_card|detecta o código pessoal da Letônia|não|
|Func_lithuania_eu_tax_file_number|detecta o código pessoal da Lituânia|não|
|Func_louisiana_drivers_license_number|detecta o número da carteira de motorista do Louisiana|não|
|Func_luxemburg_eu_tax_file_number|detecta o número de identificação nacional do Luxemburg (pessoas naturais)|não|
|Func_luxemburg_eu_tax_file_number_non_natural|detecta o número de identificação nacional do Luxemburg (pessoas não naturais)|não|
|Func_maine_drivers_license_number|detecta o número da carteira de motorista do Maine|não|
|Func_manitoba_drivers_license_number|detecta o número da carteira de motorista do Manitoba|não|
|Func_maryland_drivers_license_number|detecta o número da carteira de motorista do Maryland|não|
|Func_massachusetts_drivers_license_number|detecta o número da carteira de motorista de Massachusetts|não|
|Func_mexico_population_registry_code|detecta o código do registro da população do México|não|
|Func_michigan_minnesota_drivers_license_number|detecta o número de carteira de motorista de Michigan, Minnesota|não|
|Func_minnesota_drivers_license_number|detecta o número da carteira de motorista de Minnesota|não|
|Func_mississippi_oklahoma_drivers_license_number|detecta o número da carteira de motorista do Mississippi, Oklahoma|não|
|Func_missouri_drivers_license_number|detecta o número da carteira de motorista do Missouri|não|
|Func_montana_drivers_license_number|detecta o número da carteira de motorista do Montana|não|
|Func_nebraska_drivers_license_number|detecta o número da carteira de motorista do Nebraska|não|
|Func_netherlands_bsn|detecta BSN Holanda|não|
|Func_netherlands_eu_tax_file_number|detecta o número de arquivo de tributação Holanda|não|
|Func_netherlands_value_added_tax_number|detecta o número do imposto sobre valor da Holanda|não|
|Func_nevada_drivers_license_number|detecta o número da carteira de motorista do Nevada|não|
|Func_new_brunswick_drivers_license_number|detecta o novo número de licença do driver Brunswick|não|
|Func_new_hampshire_drivers_license_number|detecta o novo número de licença do driver Hampshire|não|
|Func_new_jersey_drivers_license_number |detecta o número da licença do novo driver de Jersey|não|
|Func_new_mexico_drivers_license_number |detecta o novo número de carteira de motorista do México|não|
|Func_new_york_drivers_license_number   |detecta o número da carteira de motorista de Nova York|não|
|Func_new_zealand_bank_account_number   |detecta o número da conta bancária da Nova Zelândia|não|
|Func_new_zealand_inland_revenue_number |detecta o número de receita da Nova Zelândia|não|
|Func_new_zealand_ministry_of_health_number|detecta o Ministério do número de integridade da Nova Zelândia|não|
|Func_newfoundland_labrador_drivers_license_number|detecta o número de licença do driver de terra nova|não|
|Func_newzealand_driver_license_number  |detecta o número de licença do driver da Nova Zelândia|não|
|Func_newzealand_social_welfare_number  |detecta o número do Welfare social da Nova Zelândia|não|
|Func_north_carolina_drivers_license_number|detecta o número da carteira de motorista da Carolina do Norte|não|
|Func_north_dakota_drivers_license_number|detecta o número da carteira de motorista da Dakota do Norte|não|
|Func_norway_id_number  |detecta o número de ID da Noruega|não|
|Func_nova_scotia_drivers_license_number|detecta o número de licença de Nova Escócia do driver|não|
|Func_ohio_drivers_license_number   |detecta o número da carteira de motorista de Ohio|não|
|Func_ontario_drivers_license_number    |detecta o número da carteira de motorista do Ontário|não|
|Func_pennsylvania_drivers_license_number|detecta o número da carteira de motorista da Pensilvânia|não|
|Func_pesel_identification_number   |detecta o ID nacional da Polônia (PESEL)|não|
|Func_poland_eu_tax_file_number |detecta o número de arquivo de imposto da Polônia|não|
|Func_polish_national_id    |detecta o cartão de identidade da Polônia|não|
|Func_polish_passport_number    |detecta o número de passaporte em polonês|não|
|Func_polish_regon_number   |detecta o número do REGON polonês|não|
|Func_portugal_eu_tax_file_number|detecta o número de identificação do imposto Portugal|não|
|Func_prince_edward_island_drivers_license_number|detecta o número da carteira de motorista do Príncipe Edward|não|
|Func_quebec_drivers_license_number |detecta o número da carteira de motorista de Quebec|não|
|Func_randomized_formatted_ssn  |detecta o SSN com formato aleatório|sim|
|Func_randomized_unformatted_ssn|detecta NSS não formatados aleatoriamente|sim|
|Func_rhode_island_drivers_license_number|detecta o número da carteira de motorista do Rhode Island|não|
|Func_romania_eu_national_id_card   |detecta o código numérico da Romênia (CNP)|não|
|Func_saskatchewan_drivers_license_number|detecta o número da carteira de motorista do Saskatchewan|não|
|Func_slovakia_eu_national_id_card  |detecta o número pessoal da Eslováquia|não|
|Func_slovenia_eu_national_id_card  |detecta o número principal de cidadãos exclusivos da Eslovênia|não|
|Func_slovenia_eu_tax_file_number   |detecta o número do arquivo de imposto da Eslovênia|não|
|Func_south_africa_identification_number|detecta o número de identificação da África do Sul|sim|
|Func_south_carolina_drivers_license_number|detecta o número da carteira de motorista da Carolina do Sul|não|
|Func_south_dakota_drivers_license_number|detecta o número da carteira de motorista do Sul Dakota|não|
|Func_south_korea_resident_number   |detecta o número residente da Coréia do Sul|não|
|Func_spain_eu_DL_and_NI_number_citizen |detecta o cidadão de número de NI e DL da Espanha|não|
|Func_spain_eu_DL_and_NI_number_foreigner|detecta o Espanha DL e o número de NI estrangeiros|não|
|Func_spain_eu_driver ' s_license_number  |detecta o número da carteira de motorista da Espanha|não|
|Func_spain_eu_tax_file_number  |detecta o número de arquivo de impostos da Espanha|não|
|Func_spanish_social_security_number|detecta o número da segurança social do espanhol|não|
|Func_ssn   |Função para detectar NSS não aleatórios formatados|sim|
|Func_sweden_eu_tax_file_number|detecta o número de arquivo de imposto da Suécia|não|
|Func_swedish_national_identifier|detecta o identificador Nacional Sueco|sim|
|Func_swiss_social_security_number_ahv|detecta o número de segurança social da Suíça AHV|não|
|Func_taiwanese_national_id |detecta a ID nacional do taiwanês|não|
|Func_tennessee_drivers_license_number|detecta o número da carteira de motorista do Tennessee|não|
|Func_texas_drivers_license_number  |detecta o número da carteira de motorista do Texas|não|
|Func_Thai_Citizen_Id   |detecta o ID do cidadão tailandês|não|
|Func_Turkish_National_Id|detecta o ID da Nacional Turco|sim|
|Func_uk_drivers_license|detecta a licença do controlador Reino Unido|não|
|Func_uk_eu_tax_file_number|detecta o número de contribuinte exclusivo do Reino Unido|não|
|Func_uk_nhs_number |detecta o número do Reino Unido NHS|sim|
|Func_uk_nino   |detecta o Reino Unido NINO|não|
|Func_unformatted_canadian_sin|detecta o SIN canadense não formatado|não|
|Func_unformatted_itin  |detecta o não formatado de US ITIN|sim|
|Func_unformatted_ssn   |detecta NSS não-formatados não aleatórios conosco|sim|
|Func_usa_uk_passport   |detecta os EUA e o Passport Reino Unido|sim|
|Func_utah_drivers_license_number|detecta o número da carteira de motorista de Utah|não|
|Func_vermont_drivers_license_number|detecta o número da carteira de motorista de Vermont|não|
|Func_virginia_drivers_license_number|detecta o número da carteira de motorista da Virgínia|não|
|Func_washington_drivers_license_number|detecta o número da carteira de motorista de Washington|não|
|Func_west_virginia_drivers_license_number|detecta o número da carteira de motorista da Virgínia Ocidental|não|
|Func_wisconsin_drivers_license_number  |detecta o número da carteira de motorista de Wisconsin|não|
|Func_wyoming_drivers_license_number    |detecta o número da carteira de motorista do Wyoming|não|


## <a name="func_us_date"></a>Func_us_date

Func_us_date procura datas em formatos comuns dos EUA. Os formatos comuns são "mês/dia/ano", "mês-dia-ano" e "ano dia do mês". Os nomes ou abreviações de meses não diferenciam maiúsculas de minúsculas. 
  
Exemplos:
  
- 2 de dezembro de 2016
    
- 2 de dezembro de 2016
    
- Dec 02 2016
    
- 12/2/2016
    
- 12/02/16
    
- Dec-2-2016
    
- 12-2-16
    
Nomes de meses aceitos:
  
- Inglês
    
  - Janeiro, fevereiro, março, abril, maio, junho de julho, agosto, setembro, outubro, novembro de dezembro
    
  - Jan. Fev. mar. abr. Maio de 1º de julho de agosto de setembro. Dec.
    
## <a name="func_eu_date"></a>Func_eu_date

Fund_eu_dates procura datas em comum da UE formatos (e a maioria dos lugares fora dos EUA), como "dia/mês/ano", "dia-mês-ano" e "ano do mês do dia". Os nomes ou abreviações de meses não diferenciam maiúsculas de minúsculas.
  
Exemplos:
  
- 2 Dec 2016
    
- 02 de dezembro de 2016
    
- 2 de dezembro de 16
    
- 2/12/2016
    
- 02/12/16
    
- 2-dez-2016
    
- 2-12-16
    
Nomes de meses aceitos:
  
- Inglês
    
  - Janeiro, fevereiro, março, abril, maio, junho de julho, agosto, setembro, outubro, novembro de dezembro
    
  - Jan. Fev. mar. abr. Maio de 1º de julho de agosto de setembro. Dec.
    
- Holandês
    
  - januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December
    
  - Jan fevereiro de maart de abril de Mei jun jul setembro de agosto de dezembro de Okt de Nov
    
- Francês
    
  - Janvier, Février, Mars, Avril, Mai, Juin Juillet, Août, Septembre, outubro, Novembre, décembre
    
  - janv. févr. Mars Avril Mai Juin Juil. Août set. Outubro. Nov. déc.
    
- Alemão
    
  - jänuar, februar, März, abril, Mai, Juni Juli, agosto, setembro, Oktober, novembro de Dezember
    
  - Jan./Jän. Fev. März abr. Mai Juni Juli ago. set. Okt. Nov. dez.
    
- Italiano
    
  - gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre
    
  - genn. febbr. mar. abr. magg. giugno Luglio AG. definida. ott. Nov. DIC.
    
- Português
    
  - janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro
    
  - Jan fev mar abr mai jun jul atrás Set out nov dez
    
- Espanhol
    
  - enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre
    
  - Enero Fev. Marzo abr. Mayo Jun. Jul. agosto set./set. Outubro. Nov. DIC.
    
## <a name="func_eu_date1-deprecated"></a>Func_eu_date1 (preterido)

> [!NOTE]
> Essa função foi preterida porque dá suporte apenas a nomes de meses em Português, que agora estão incluídos na  `Func_eu_date` função acima. 
  
Essa função procura uma data no formato comumente usado em português. O formato dessa função é o mesmo que  `Func_eu_date` , diferente somente no idioma usado.
  
Exemplos:
  
- 2 dez 2016
    
- 02 dez 2016
    
- 2 dez 16
    
- 2/12/2016
    
- 02/12/16
    
- 2-dez-2016
    
- 2-12-16
    
Nomes de meses aceitos:
  
- Português
    
  - janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro
    
  - Jan fev mar abr mai jun jul atrás Set out nov dez
    
## <a name="func_eu_date2-deprecated"></a>Func_eu_date2 (preterido)

> [!NOTE]
> Essa função foi preterida porque dá suporte apenas a nomes de meses em Holandês, que agora estão incluídos na  `Func_eu_date` função acima. 
  
Essa função procura uma data no formato comumente usado em holandês. O formato dessa função é o mesmo que  `Func_eu_date` , diferente somente no idioma usado.
  
Exemplos:
  
- 2 Mei 2016
    
- 02 Mei 2016
    
- 2 Mei 16
    
- 2/12/2016
    
- 02/12/16
    
- 2-Mei-2016
    
- 2-12-16
    
Nomes de meses aceitos:
  
- Holandês
    
  - januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December
    
  - Jan Fev maart Apr Mei jun jul ago set out Okt Nov
    
## <a name="func_expiration_date"></a>Func_expiration_date

Func_expiration_date procura datas que estão em formatos comumente usados por cartões de crédito e débito. Essa função coincidirá datas no formato de "mês/ano", "Mês-Year", "[month Name] Year" e "[month abreviation] Year". Os nomes ou abreviações de meses não diferenciam maiúsculas de minúsculas.
  
Exemplos:
  
- MM/AA -- por exemplo, 01/11 ou 1/11
    
- MM/AAAA -- por exemplo, 01/2011 ou 1/2011
    
- MM-AA -- por exemplo, 01-22 ou 1-11
    
- MM-AAAA -- por exemplo, 01-2000 ou 1-2000
    
Os seguintes formatos dão suporte a AA ou AAAA:
  
- Month-aaaa--por exemplo Jan-2010 ou Janeiro-2010 ou Jan-10 ou janeiro-10
    
- Mês AAAA – por exemplo, 'janeiro 2010' ou 'jan 2010' ou 'janeiro 10' ou 'jan 10'
    
- MêsAAAA – por exemplo, 'janeiro2010' ou 'Jan2010' ou 'janeiro10' ou 'Jan10'
    
- Month/aaaa--por exemplo, ' Janeiro/2010 ' ou ' Jan/2010 ' ou ' janeiro/10 ' ou ' Jan/10 '
    
Nomes de meses aceitos:
  
- Inglês
    
  - Janeiro, fevereiro, março, abril, maio, junho de julho, agosto, setembro, outubro, novembro de dezembro
    
  - Jan fev mar de junho de julho de agosto de agosto de abril de dezembro
    
## <a name="func_us_address"></a>Func_us_address

Func_us_address procura um nome de estado americano ou abreviatura de postal seguida de um código postal válido. O CEP deve ser um dos CEPs corretos associados ao nome ou sigla do estado americano. O nome do estado americano e o CEP não podem ser separados por pontos ou letras.
  
Exemplos:
  
- Washington 98052
    
- Washington 98052-9998
    
- WA 98052
    
- WA 98052-9998
