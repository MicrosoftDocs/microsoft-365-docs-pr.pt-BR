---
title: O que as funções de Prevenção contra Perda de Dados (DLP) pesquisam
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
description: Saiba o que as funções de prevenção contra perda de dados (DLP) pesquisam.
ms.openlocfilehash: b77075b0b31ad5d6e6e2b7062c35e96649fa8365
ms.sourcegitcommit: e56894917d2aae05705c3b9447388d10e2156183
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841442"
---
# <a name="what-the-dlp-functions-look-for"></a>O que as funções DLP procuram

As políticas de prevenção contra perda de dados (DLP) podem usar tipos de informações confidenciais para identificar itens confidenciais. O número do cartão de crédito e o número do cartão de débito da UE são exemplos de tipos de informações confidenciais. Os tipos de informações confidenciais procurarão padrões específicos. Os tipos de informações confidenciais validam os dados observando seu formato, suas verificações e procurando palavras-chave relevantes ou outras informações. Algumas dessas funcionalidades são realizadas por funções internas. Por exemplo, o tipo de informação sensível ao Número do Cartão de Crédito usa uma função para procurar datas formatadas como uma data de vencimento. Isso ajuda a corroborar que um número é um número de cartão de crédito.
  
Este artigo explica o que essas funções procurarão para ajudá-lo a entender como funcionam os tipos de informações confidenciais predefinidos. Para obter mais informações, consulte [Definições de entidade de tipo de informação confidenciais](sensitive-information-type-entity-definitions.md)
  
## <a name="table-of-functions"></a>Tabela de funções

|nome da função  |ação de função  |é um validador|
|---------|---------|---------|
|Func_Argentina_Unique_Tax_Key|detecta e valida a chave de imposto exclusiva da Argentina|não|
|Func_aba_routing|detecta o número de roteamento ABA| sim|
|Func_alabama_drivers_license_number|detecta o número de carteira de motorista do Ltd.|não|
|Func_alaska_delaware_oregon_drivers_license_number|detecta o número de carteira de motorista de Oregon, Ltd.|não|
|Func_alaska_drivers_license_number|detecta o número de carteira de motorista do Ltd.|não|
|Func_alberta_drivers_license_number|detecta o número de carteira de motorista de Alberta|não|
|Func_Argentina_Unique_Tax_Key|detecta a chave de imposto exclusiva da Argentina|não|
|Func_arizona_drivers_license_number|detecta o número de carteira de motorista de Clara|não|
|Func_arkansas_drivers_license_number|detecta o número de carteira de motorista de RS|não|
|Func_australian_business_number|detecta o número comercial da Austrália|não|
|Func_Australian_Company_Number|detecta o número da empresa da Austrália|não|
|Func_australian_medical_account_number|detecta o número da conta médica da Austrália|não|
|Func_australian_tax_file_number|detecta o número do arquivo fiscal da Austrália|sim|
|Func_austria_eu_ssn_or_equivalent|detecta o número de seguro social da Áustria|não|
|Func_austria_eu_tax_file_number|detecta o número do arquivo fiscal da Áustria|não|
|Func_Austria_Value_Added_Tax|detecta o imposto sobre valor agregado da Áustria|não|
|Func_belgium_national_number|detecta o número nacional da Bélgica|não|
|Func_belgium_value_added_tax_number|detecta o número de imposto adicionado ao valor da Bélgica|não|
|Func_brazil_cnpj|detecta o número de entidade legal do Brasil (CNPJ)|sim|
|Func_brazil_cpf|detecta o CPF do Brasil|sim|
|Func_brazil_rg|detecta o RG do Brasil|não|
|Func_british_columbia_drivers_license_number|detecta o número de carteira de motorista da British British|não|
|Func_bulgaria_eu_national_id_card|detecta o número civil uniforme da Bulgária|não|
|Func_california_drivers_license_number|detecta o número de carteira de motorista da Califórnia|não|
|Func_canadian_sin|detecta o seda do Canadá|sim|
|Func_chile_id_card|detecta o cartão de ID do Chile|não|
|Func_china_resident_id|detecta a ID residente na China|não|
|Func_colorado_drivers_license_number|detecta o número de carteira de motorista da Ela|não|
|Func_connecticut_drivers_license_number|detecta o número de carteira de motorista do Connect ltd.|não|
|Func_credit_card|detecta cartão de crédito|sim|não|
|Func_croatia_id_card|detecta o cartão de ID da Croácia|não|
|Func_croatia_oib_number|detecta o número OIB da Croácia|não|
|Func_cyprus_eu_tax_file_number|detecta o número do arquivo fiscal de Chipre|não|
|Func_czech_id_card|detecta o cartão de ID tcheco|não|
|Func_czech_id_card_new_format|detecta o cartão de ID tcheco no novo formato|não|
|Func_dea_number|detecta o número DEA|sim|
|Func_denmark_eu_tax_file_number|detecta o número de identificação pessoal da Dinamarca|não|
|Func_district_of_columbia_drivers_license_number|detecta o número de carteira de motorista do Distrito de Washington|não|
|Func_estonia_eu_national_id_card|detecta o Código de Identificação Pessoal da Estônia|não|
|Func_eu_debit_card|detecta o cartão de débito da UE|não|
|Func_finnish_national_id|detecta a ID nacional finlandês|não|
|Func_florida_drivers_license_number|detecta o número de carteira de motorista da Ela|não|
|Func_florida_maryland_michigan_minnesota_drivers_license_number|detecta o número de carteira de motorista de Dynamics, Ltd, Ltd.|não|
|Func_formatted_itin|detecta ITIN dos EUA formatado|sim|
|Func_fr_insee|detecta o INSEE da França|não|
|Func_fr_passport|detecta o Passaporte da França|não|
|Func_france_eu_tax_file_number|detecta o número do arquivo fiscal da França|não|
|Func_france_value_added_tax_number|detecta o número de imposto adicionado ao valor da França|não|
|Func_french_drivers_license|detecta a carteira de motorista francesa|não|
|Func_french_insee|detecta o FRANCÊS INSEE|não|
|Func_georgia_drivers_license_number|detecta o número de carteira de motorista da Geórgia|não|
|Func_german_drivers_license|detecta a carteira de motorista da Alemanha|não|
|Func_german_passport|detecta o Passaporte da Alemanha|não|
|Func_german_passport_data|detecta o Passaporte da Alemanha|não|
|Func_germany_eu_tax_file_number|detecta o número do arquivo fiscal da Alemanha|não|
|Func_germany_value_added_tax_number|detecta o número de imposto adicionado ao valor da Alemanha|não|
|Func_greece_eu_ssn|detecta o seda da Grécia (AMKA)|não|
|Func_hawaii_drivers_license_number|detecta o número de carteira de motorista do Havaiano|não|
|Func_hong_kong_id_card |detecta o cartão de ID de Hong Kong|não|
|Func_hungarian_value_added_tax_number|detecta o número de imposto adicionado ao valor da Hungria|não|
|Func_hungary_eu_national_id_card|detecta o número de identificação pessoal da Hungria|não|
|Func_hungary_eu_ssn_or_equivalent|detecta o número de seguro social da Hungria|não|
|Func_hungary_eu_tax_file_number|detecta o número do arquivo fiscal da Hungria|não|
|Func_iban|detecta o IBAN|sim|
|Func_idaho_drivers_license_number|detecta o número de carteira de motorista de Ltda|não|
|Func_illinois_drivers_license_number|detecta o número de carteira de motorista de Gantois|não|
|Func_india_aadhaar|detecta aadhaar da Índia|sim|
|Func_indiana_drivers_license_number|detecta o número de carteira de motorista da Dynamics|não|
|Func_iowa_drivers_license_number|detecta o número de carteira de motorista de Ltda|não|
|Func_ireland_pps|detecta o PPS da Irlanda|não|
|Func_israeli_national_id_number|detecta o número de ID nacional de Israel|não|
|Func_italy_eu_national_id_card |detecta o código fiscal da Itália|não|
|Func_italy_value_added_tax_number|detecta o número de imposto adicionado ao valor da Itália|não|
|Func_japanese_my_number_corporate|detecta o Japão meu número corporativo|sim|
|Func_japanese_my_number_personal|detecta meu número pessoal no Japão|sim|
|Func_jp_bank_account|detecta a conta bancária do Japão|não|
|Func_jp_bank_account_branch_code|detecta o código de ramificação da conta bancária do Japão|não|
|Func_jp_drivers_license_number|detecta o número de carteira de motorista do Japão|não|
|Func_jp_passport|detecta o passaporte do Japão|não|
|Func_jp_resident_registration_number|detecta o número de registro residente no Japão|não|
|Func_jp_sin|detecta o SIN do Japão|não|
|Func_jp_sin_pre_1997|detecta o Seleção do Japão antes de 1997|não|
|Func_kansas_drivers_license_number|detecta o número de carteira de motorista do Driver|não|
|Func_kentucky_drivers_license_number|detecta o número de carteira de motorista de Ltdy|não|
|Func_kentucky_massachusetts_virginia_drivers_license_number|detecta o número de carteira de motorista de Massachusetts, Massachusetts|não|
|Func_latvia_eu_national_id_card|detecta o código pessoal da Letônia|não|
|Func_lithuania_eu_tax_file_number|detecta o código pessoal da Lituânia|não|
|Func_louisiana_drivers_license_number|detecta o número de carteira de motorista do Martins|não|
|Func_luxemburg_eu_tax_file_number|detecta o número de identificação nacional de Luxemburgo (pessoas físicas)|não|
|Func_luxemburg_eu_tax_file_number_non_natural|detecta o número de identificação nacional de Luxemburgo (pessoas não naturais)|não|
|Func_maine_drivers_license_number|detecta o número de carteira de motorista de Ltda|não|
|Func_manitoba_drivers_license_number|detecta o número de carteira de motorista do Manitoba|não|
|Func_maryland_drivers_license_number|detecta o número de carteira de motorista de Ltda|não|
|Func_massachusetts_drivers_license_number|detecta o número de carteira de motorista do Massachusetts|não|
|Func_mexico_population_registry_code|detecta o código de registro da população do México|não|
|Func_michigan_minnesota_drivers_license_number|detecta o número de carteira de motorista de Andrew, Ltd.|não|
|Func_minnesota_drivers_license_number|detecta o número de carteira de motorista da Ltda|não|
|Func_mississippi_oklahoma_drivers_license_number|detecta o número da carteira de motorista Dem, Ltd.|não|
|Func_missouri_drivers_license_number|detecta o número de carteira de motorista de Barcoi|não|
|Func_montana_drivers_license_number|detecta o número de carteira de motorista da Ltda|não|
|Func_nebraska_drivers_license_number|detecta o número de carteira de motorista de Ubera|não|
|Func_netherlands_bsn|detecta o BSN dos Países Baixos|não|
|Func_netherlands_eu_tax_file_number|detecta o número do arquivo fiscal dos Países Baixos|não|
|Func_netherlands_value_added_tax_number|detecta o número de imposto adicionado ao valor dos Países Baixos|não|
|Func_nevada_drivers_license_number|detecta o número de carteira de motorista de Ltda|não|
|Func_new_brunswick_drivers_license_number|detecta o número de carteira de motorista de New Bruns driver|não|
|Func_new_hampshire_drivers_license_number|detecta o número de carteira de motorista de New Ltd|não|
|Func_new_jersey_drivers_license_number |detecta o número de carteira de motorista de Nova York|não|
|Func_new_mexico_drivers_license_number |detecta o número de carteira de motorista do Novo México|não|
|Func_new_york_drivers_license_number   |detecta o número da carteira de motorista de Nova York|não|
|Func_new_zealand_bank_account_number   |detecta o número da conta bancária da Nova Zelândia|não|
|Func_new_zealand_inland_revenue_number |detecta o número de receita da Nova Zelândia|não|
|Func_new_zealand_ministry_of_health_number|detecta o número de saúde do ministério da Nova Zelândia|não|
|Func_newfoundland_labrador_drivers_license_number|detecta o número de carteira de motorista do Newfoundland Labrador|não|
|Func_newzealand_driver_license_number  |detecta o número de carteira de motorista da Nova Zelândia|não|
|Func_newzealand_social_welfare_number  |detecta o número de assistência social da Nova Zelândia|não|
|Func_north_carolina_drivers_license_number|detecta o número de carteira de motorista da North Você|não|
|Func_north_dakota_drivers_license_number|detecta o número de carteira de motorista da North North Ltd|não|
|Func_norway_id_number  |detecta o número de ID da Noruega|não|
|Func_nova_scotia_drivers_license_number|detecta o número de carteira de motorista da Nova Scotia|não|
|Func_ohio_drivers_license_number   |detecta o número de carteira de motorista do Driver|não|
|Func_ontario_drivers_license_number    |detecta o número de carteira de motorista DoLs|não|
|Func_pennsylvania_drivers_license_number|detecta o número de carteira de motorista de Driver|não|
|Func_pesel_identification_number   |detecta a ID nacional polônia (PESEL)|não|
|Func_poland_eu_tax_file_number |detecta o número do arquivo fiscal da Polônia|não|
|Func_polish_national_id    |detecta o cartão de identidade polônia|não|
|Func_polish_passport_number    |detecta o número de passaporte polonês|não|
|Func_polish_regon_number   |detecta o número REGON polonês|não|
|Func_portugal_eu_tax_file_number|detecta o Número de Identificação de Imposto de Portugal|não|
|Func_prince_edward_island_drivers_license_number|detecta o número de carteira de motorista da Ilha Dem|não|
|Func_quebec_drivers_license_number |detecta o número de carteira de motorista do Quebec|não|
|Func_randomized_formatted_ssn  |detecta o SSN dos EUA formatado aleatoriamente|sim|
|Func_randomized_unformatted_ssn|detecta o SSN não formatado aleatório dos EUA|sim|
|Func_rhode_island_drivers_license_number|detecta o número de carteira de motorista da Ilha Deleite|não|
|Func_romania_eu_national_id_card   |detecta código numérico pessoal (CNP) da Romênia|não|
|Func_saskatchewan_drivers_license_number|detecta o número de carteira de motorista de Saskatchewan|não|
|Func_slovakia_eu_national_id_card  |detecta o número pessoal da Eslováquia|não|
|Func_slovenia_eu_national_id_card  |detecta o número de cidadãos mestres exclusivos da Eslovênia|não|
|Func_slovenia_eu_tax_file_number   |detecta o número do arquivo fiscal da Eslovênia|não|
|Func_south_africa_identification_number|detecta o número de identificação da África do Sul|sim|
|Func_south_carolina_drivers_license_number|detecta o número de carteira de motorista do South South Você|não|
|Func_south_dakota_drivers_license_number|detecta o número de carteira de motorista do South South South Park|não|
|Func_south_korea_resident_number   |detecta o número de residentes da Coreia do Sul|não|
|Func_spain_eu_DL_and_NI_number_citizen |detecta o DL e o número de NI da Espanha|não|
|Func_spain_eu_DL_and_NI_number_foreigner|detecta a DL e o número de NI da Espanha|não|
|Func_spain_eu_driver's_license_number  |detecta o número de carteira de motorista da Espanha|não|
|Func_spain_eu_tax_file_number  |detecta o número do arquivo fiscal da Espanha|não|
|Func_spanish_social_security_number|detecta o número do seguro social espanhol|não|
|Func_ssn   |Função para detectar SSN não formatado aleatoriamente nos EUA|sim|
|Func_sweden_eu_tax_file_number|detecta o número de arquivo fiscal da Suécia|não|
|Func_swedish_national_identifier|detecta o identificador nacional sueco|sim|
|Func_swiss_social_security_number_ahv|detecta o número de seguro social da Suíça AHV|não|
|Func_taiwanese_national_id |detecta a ID nacional taiwanesa|não|
|Func_tennessee_drivers_license_number|detecta o número de carteira de motorista de Ltda|não|
|Func_texas_drivers_license_number  |detecta o número de carteira de motorista do Texas|não|
|Func_Thai_Citizen_Id   |detecta a ID de cidadão tailandês|não|
|Func_Turkish_National_Id|detecta a ID nacional turco|sim|
|Func_uk_drivers_license|detecta a carteira de motorista do Reino Unido|não|
|Func_uk_eu_tax_file_number|detecta o número de contribuinte exclusivo do Reino Unido|não|
|Func_uk_nhs_number |detecta o número do NHS do Reino Unido|sim|
|Func_uk_nino   |detecta o UK NINO|não|
|Func_unformatted_canadian_sin|detecta o SIN canadense não formatado|não|
|Func_unformatted_itin  |detecta ITIN dos EUA não formatado|sim|
|Func_unformatted_ssn   |detecta sSN não formatado não aleatório dos EUA|sim|
|Func_usa_uk_passport   |detecta o passaporte dos EUA e do Reino Unido|sim|
|Func_utah_drivers_license_number|detecta o número de carteira de motorista|não|
|Func_vermont_drivers_license_number|detecta o número de carteira de motorista|não|
|Func_virginia_drivers_license_number|detecta o número de carteira de motorista do Driver|não|
|Func_washington_drivers_license_number|detecta o número da carteira de motorista de Washington|não|
|Func_west_virginia_drivers_license_number|detecta o número de carteira de motorista do West West|não|
|Func_wisconsin_drivers_license_number  |detecta o número de carteira de motorista da Ela|não|
|Func_wyoming_drivers_license_number    |detecta o número de carteira de motorista de Ltding|não|


## <a name="func_us_date"></a>Func_us_date

Func_us_date procura datas em formatos comuns dos EUA. Os formatos comuns são "mês/dia/ano", "mês-dia-ano" e "mês dia ano". Os nomes ou abreviações de meses não são sensíveis a casos. 
  
Exemplos:
  
- 2 de dezembro de 2016
    
- 2 de dezembro de 2016
    
- 02 de dez de 2016
    
- 12/2/2016
    
- 12/02/16
    
- Dec-2-2016
    
- 12-2-16
    
Nomes de meses aceitos:
  
- Inglês
    
  - Janeiro, fevereiro, março, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro
    
  - Jan. Feb. Mar. Abr. May June July Aug. Sept. Oct. Nov. Dec.
    
## <a name="func_eu_date"></a>Func_eu_date

Fund_eu_dates procura datas em E.U. formatos (e a maioria dos lugares fora dos EUA), como "dia/mês/ano", "dia-mês-ano" e "dia mês ano". Os nomes ou abreviações de meses não são sensíveis a casos.
  
Exemplos:
  
- 2 de dezembro de 2016
    
- 02 de dez de 2016
    
- 2 Dezembro 16
    
- 2/12/2016
    
- 02/12/16
    
- 2-Dez-2016
    
- 2-12-16
    
Nomes de meses aceitos:
  
- Inglês
    
  - Janeiro, fevereiro, março, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro
    
  - Jan. Feb. Mar. Abr. May June July Aug. Sept. Oct. Nov. Dec.
    
- Holandês
    
  - januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December
    
  - jan feb maart apr mei jun jul aug sep sept oct okt nov dec
    
- Francês
    
  - janvier, février, mars, avril, mai, juin juillet, août, septembre, octobre, novembre, décembre
    
  - janv. févr. mars avril mai juin juil. aoūt sept. oct. nov. déc.
    
- Alemão
    
  - jänuar, februar, märz, April, mai, juni tai, August, September, oktober, November, dezember
    
  - Jan./Jän. Feb. März Apr. Mai Juni Tai Aug. Sept. Okt. Nov. Dez.
    
- Italiano
    
  - gennaio, febbraio, marzo, aprile, maggio, giugno, lu melissa, agosto, settembre, timebre, novembre, dicembre
    
  - genn. febbr. mar. apr. magg. giugno lugosto ag. sett. ott. nov. dic.
    
- Português
    
  - janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro
    
  - jan fev mar abr mai jun jul ago set out nov dez
    
- Espanhol
    
  - enero, costro, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre
    
  - enero feb. marzo abr. mayo jun. jul. agosto sept./set. oct. nov. dic.
    
## <a name="func_eu_date1-deprecated"></a>Func_eu_date1 (preterido)

> [!NOTE]
> Essa função foi preterida porque dá suporte apenas a nomes de meses em português, que agora estão incluídos na  `Func_eu_date` função acima. 
  
Essa função procura uma data no formato comumente usado em português. O formato para essa função é o mesmo  `Func_eu_date` que , diferente somente no idioma usado.
  
Exemplos:
  
- 2 Dez de 2016
    
- 02 dez 2016
    
- 2 Dez 16
    
- 2/12/2016
    
- 02/12/16
    
- 2-Dez-2016
    
- 2-12-16
    
Nomes de meses aceitos:
  
- Português
    
  - janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro
    
  - jan fev mar abr mai jun jul ago set out nov dez
    
## <a name="func_eu_date2-deprecated"></a>Func_eu_date2 (preterido)

> [!NOTE]
> Essa função foi preterida porque dá suporte apenas a nomes de meses holandês, que agora estão incluídos na  `Func_eu_date` função acima. 
  
Essa função procura uma data no formato comumente usado em holandês. O formato para essa função é o mesmo  `Func_eu_date` que , diferente somente no idioma usado.
  
Exemplos:
  
- 2 Mei 2016
    
- 02 mei 2016
    
- 2 Mei 16
    
- 2/12/2016
    
- 02/12/16
    
- 2-Mei-2016
    
- 2-12-16
    
Nomes de meses aceitos:
  
- Holandês
    
  - januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December
    
  - jan feb maart apr mei jun jul aug sep set out okt nov dec
    
## <a name="func_expiration_date"></a>Func_expiration_date

Func_expiration_date procura datas que estão em formatos comumente usados por cartões de crédito e débito. Esta função corresponderá às datas no formato "mês/ano", "mês-ano", "[nome do mês] ano" e "[abreviação do mês] ano". Os nomes ou abreviações de meses não são sensíveis a casos.
  
Exemplos:
  
- MM/AA -- por exemplo, 01/11 ou 1/11
    
- MM/AAAA -- por exemplo, 01/2011 ou 1/2011
    
- MM-AA -- por exemplo, 01-22 ou 1-11
    
- MM-AAAA -- por exemplo, 01-2000 ou 1-2000
    
Os seguintes formatos dão suporte a AA ou AAAA:
  
- Month-AAAA – por exemplo Jan-2010 ou janeiro-2010 ou Jan-10 ou janeiro-10
    
- Mês AAAA – por exemplo, 'janeiro 2010' ou 'jan 2010' ou 'janeiro 10' ou 'jan 10'
    
- MêsAAAA – por exemplo, 'janeiro2010' ou 'Jan2010' ou 'janeiro10' ou 'Jan10'
    
- Mês/AAAA – por exemplo, 'janeiro/2010' ou 'jan/2010' ou 'janeiro/10' ou 'jan/10'
    
Nomes de meses aceitos:
  
- Inglês
    
  - Janeiro, fevereiro, março, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro
    
  - Jan Feb Mar Abr May June July Aug Sept Oct Nov Dec
    
## <a name="func_us_address"></a>Func_us_address

Func_us_address procura um nome de estado dos EUA ou abreviação postal seguido por um CEP válido. O CEP deve ser um dos CEPs corretos associados ao nome ou sigla do estado americano. O nome do estado americano e o CEP não podem ser separados por pontos ou letras.
  
Exemplos:
  
- Washington 98052
    
- Washington 98052-9998
    
- WA 98052
    
- WA 98052-9998
