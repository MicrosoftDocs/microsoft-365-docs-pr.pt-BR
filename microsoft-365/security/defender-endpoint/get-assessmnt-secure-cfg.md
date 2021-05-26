---
title: Exportar avaliação de configuração segura por dispositivo
description: Retorna uma entrada para cada combinação exclusiva de DeviceId, ConfigurationId.
keywords: api, apis, avaliação de exportação, avaliação por dispositivo, relatório de avaliação de vulnerabilidade, avaliação de vulnerabilidade de dispositivo, relatório de vulnerabilidade de dispositivo, avaliação de configuração segura, relatório de configuração segura, avaliação de vulnerabilidades de software, relatório de vulnerabilidade de software, relatório de vulnerabilidade por máquina,
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.custom: api
ms.openlocfilehash: f2e20415cb64903e8dfe2c82646c1970036b8f6b
ms.sourcegitcommit: 727a75b604d5ff5946a0854662ad5a8b049f2874
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2021
ms.locfileid: "52653614"
---
# <a name="export-secure-configuration-assessment-per-device"></a>Exportar avaliação de configuração segura por dispositivo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]
>
>
Retorna todas as configurações e seu status, por dispositivo.

Há diferentes chamadas de API para obter diferentes tipos de dados. Como a quantidade de dados pode ser muito grande, há duas maneiras de recuperá-las:

- **OData**  A API puxa todos os dados da sua organização como respostas Json, seguindo o protocolo OData. Esse método é melhor para _organizações pequenas com menos de 100 mil dispositivos_. A resposta é paginada, portanto, você pode usar o campo odata.nextLink da resposta para \@ buscar os próximos resultados.

- **via arquivos** Essa solução de API permite a retirada de quantidades maiores de dados de forma mais rápida e confiável. Portanto, é recomendado para grandes organizações, com mais de 100 mil dispositivos. Essa API puxa todos os dados da sua organização como arquivos de download. A resposta contém URLs para baixar todos os dados do Azure Armazenamento. Essa API permite baixar todos os dados do Azure Armazenamento a seguir:

  - Chame a API para obter uma lista de URLs de download com todos os dados da sua organização.

  - Baixe todos os arquivos usando as URLs de download e processe os dados conforme quiser.

Os dados coletados (para _OData_ ou por meio de arquivos _)_ são o instantâneo atual do estado atual e não contêm dados históricos. Para coletar dados históricos, os clientes devem salvar os dados em seus próprios armazenamentos de dados.

A menos que indicado de outra forma, todos os métodos de avaliação de exportação listados são **_exportação completa_** e **_por dispositivo_** (também chamado de **_por dispositivo)._**

## <a name="1-export-secure-configuration-assessment-odata"></a>1. Exportar a avaliação de configuração segura (OData)

### <a name="11-api-method-description"></a>Descrição do método API 1.1

Esta resposta à API contém a Avaliação de Configuração Segura em seus dispositivos expostos e retorna uma entrada para cada combinação exclusiva de DeviceId, ConfigurationId.

#### <a name="111-limitations"></a>1.1.1 Limitações

- O tamanho máximo da página é 200.000.

- As limitações de taxa para essa API são 30 chamadas por minuto e 1.000 chamadas por hora.

### <a name="12-permissions"></a>1.2 Permissões

Uma das seguintes permissões é necessária para chamar essa API. Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md) para obter detalhes.

Tipo de permissão | Permissão | Nome de exibição de permissão
---|---|---
Aplicativo | Vulnerability.Read.All | \'Ler informações de vulnerabilidade de Gerenciamento de Ameaças e Vulnerabilidades\'
Delegado (conta corporativa ou de estudante) | Vulnerability.Read | \'Ler informações de vulnerabilidade de Gerenciamento de Ameaças e Vulnerabilidades\'

### <a name="13-url"></a>URL 1.3

```http
GET /api/machines/SecureConfigurationsAssessmentByMachine
```

### <a name="14-parameters"></a>Parâmetros 1.4

- pageSize \( padrão = 50.000 \) – número de resultados em resposta

- \$top – número de resultados a retornar \( não retorna \@ odata.nextLink e, portanto, não puxa todos os dados\)

### <a name="15-properties"></a>1.5 Propriedades

>[!Note]
>
>- As propriedades definidas na tabela a seguir são listadas alfanumericamente, por ID da propriedade.  Ao executar essa API, a saída resultante não será necessariamente retornada na mesma ordem listada nessas tabelas.
>
>- Algumas colunas adicionais podem ser retornadas na resposta. Essas colunas são temporárias e podem ser removidas, use apenas as colunas documentadas.
>

Propriedade (id) | Tipo de dados | Descrição | Exemplo de um valor retornado
:---|:---|:---|:---
ConfigurationCategory | string | Categoria ou agrupamento ao qual a configuração pertence: aplicativo, sistema operacional, rede, contas, controles de segurança | Controles de segurança
ConfigurationId | string | Identificador exclusivo para uma configuração específica | scid-10000
ConfigurationImpact | string | Impacto avaliado da configuração na classificação total (1-10) | 9 
ConfigurationName | string | Exibir o nome da configuração | Dispositivos integrados ao Microsoft Defender para Ponto de Extremidade
ConfigurationSubcategory | string | Subcategoria ou subgrupo ao qual a configuração pertence. Em muitos casos, isso descreve capacidades ou recursos específicos. | Dispositivos de integração
DeviceId | string | Identificador exclusivo do dispositivo no serviço. | 9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1
DeviceName | string | Nome de domínio totalmente qualificado (FQDN) do dispositivo. | johnlaptop.europe.contoso.com
IsApplicable | bool | Indica se a configuração ou a política é aplicável | verdadeiro
IsCompliant | bool | Indica se a configuração ou política está configurada corretamente | falso
IsExpectedUserImpact | bool | Indica se haverá impacto do usuário se a configuração será aplicada | verdadeiro
OSPlatform | string | Plataforma do sistema operacional em execução no dispositivo. Isso indica os sistemas operacionais específicos, incluindo variações na mesma família, como o Windows 10 e o Windows 7. Confira sistemas operacionais e plataformas com suporte para TVM para obter detalhes. | Windows10
RbacGroupName | string | O grupo controle de acesso baseado em função (RBAC). Se esse dispositivo não for atribuído a nenhum grupo RBAC, o valor será "Não atribuído". Se a organização não tiver nenhum grupo RBAC, o valor será "None". | Servidores
RecommendationReference | string | Uma referência à ID de recomendação relacionada a este software. | sca-_-scid-20000
Carimbo de data/hora | string | Última vez que a configuração foi vista no dispositivo | 2020-11-03 10:13:34.8476880

### <a name="16-examples"></a>1.6 Exemplos

#### <a name="161-request-example"></a>1.6.1 Exemplo de solicitação

```http
GET https://api.securitycenter.microsoft.com/api/machines/SecureConfigurationsAssessmentByMachine?pageSize=5 
```

#### <a name="162-response-example"></a>Exemplo de resposta 1.6.2

```json
{
    "@odata.context": "api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.AssetConfiguration)",
    "value": [
        {
            "deviceId": "00013ee62c6b12345b10214e1801b217b50ab455c293d",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_5d96860d69c73fdd06fc8d1679e1eb73eceb8330",
            "osPlatform": "Windows10",
            "osVersion": "NT kernel 6.x",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-10000",
            "configurationCategory": "Network",
            "configurationSubcategory": "",
            "configurationImpact": 5,
            "isCompliant": true,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Disable insecure administration protocol – Telnet",
            "recommendationReference": "sca-_-scid-10000"
        },
        {
            "deviceId": "0002a1be533813b9a8c6de739785365bce7910",
            "rbacGroupName": "hhh",
            "deviceName": null,
            "osPlatform": "Windows10",
            "osVersion": "10.0",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-20000",
            "configurationCategory": "Security controls",
            "configurationSubcategory": "Onboard Devices",
            "configurationImpact": 9,
            "isCompliant": false,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Onboard devices to Microsoft Defender for Endpoint",
            "recommendationReference": "sca-_-scid-20000"
        },
        {
            "deviceId": "0002a1de123456a8c06de736785395d4ce7610",
            "rbacGroupName": "hhh",
            "deviceName": null,
            "osPlatform": "Windows10",
            "osVersion": "10.0",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-10000",
            "configurationCategory": "Network",
            "configurationSubcategory": "",
            "configurationImpact": 5,
            "isCompliant": true,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Disable insecure administration protocol – Telnet",
            "recommendationReference": "sca-_-scid-10000"
        },
        {
            "deviceId": "00044f912345bdaf756492dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663d45912eed224b2be2f5ea3142726e63f16a.DomainPII_21eeb80b086e76bdfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-39",
            "configurationCategory": "OS",
            "configurationSubcategory": "",
            "configurationImpact": 5,
            "isCompliant": true,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Enable 'Domain member: Digitally sign secure channel data (when possible)'",
            "recommendationReference": "sca-_-scid-39"
        },
        {
            "deviceId": "00044f912345daf759462bde6bd733d6a9c56ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45612eeb224d2de2f5ea3142726e63f16a.DomainPII_21eed80d086e76dbfa178eadfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-6093",
            "configurationCategory": "Security controls",
            "configurationSubcategory": "Antivirus",
            "configurationImpact": 5,
            "isCompliant": false,
            "isApplicable": false,
            "isExpectedUserImpact": false,
            "configurationName": "Enable Microsoft Defender Antivirus real-time behavior monitoring for Linux",
            "recommendationReference": "sca-_-scid-6093"
        }
    ],
    "@odata.nextLink": "https://api.securitycenter.microsoft.com/api/machines/SecureConfigurationsAssessmentByMachine?pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0xMS8xMTAxLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9"
}
```

## <a name="2-export-secure-configuration-assessment-via-files"></a>2. Exportar a avaliação de configuração segura (por meio de arquivos)

### <a name="21-api-method-description"></a>Descrição do método API 2.1

Esta resposta à API contém a Avaliação de Configuração Segura em seus dispositivos expostos e retorna uma entrada para cada combinação exclusiva de DeviceId, ConfigurationId.

#### <a name="212-limitations"></a>2.1.2 Limitações

As limitações de taxa para essa API são 5 chamadas por minuto e 20 chamadas por hora.

### <a name="22-permissions"></a>2.2 Permissões

Uma das seguintes permissões é necessária para chamar essa API. Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs para obter detalhes.](apis-intro.md)

Tipo de permissão | Permissão | Nome de exibição de permissão
---|---|---
Aplicativo | Vulnerability.Read.All | \'Ler informações de vulnerabilidade "Gerenciamento de Ameaças e Vulnerabilidades"\'
Delegado (conta corporativa ou de estudante) | Vulnerability.Read | \'Ler informações de vulnerabilidade "Gerenciamento de Ameaças e Vulnerabilidades"\'

### <a name="23-url"></a>URL 2.3

```http
GET /api/machines/SecureConfigurationsAssessmentExport
```

### <a name="parameters"></a>Parâmetros

- sasValidHours – O número de horas em que as URLs de download serão válidas (Máximo de 24 horas).

### <a name="25-properties"></a>2.5 Propriedades

>[!Note]
>
>- Os arquivos são gzip compactados & no formato Json de várias linhas.
>
>- As URLs de download só são válidas por 3 horas; caso contrário, você pode usar o parâmetro.
>
>- Para a velocidade máxima de download de seus dados, você pode garantir que você está baixando da mesma região do Azure na qual seus dados residem.
>
Propriedade (id) | Tipo de dados | Descrição | Exemplo de um valor retornado
:---|:---|:---|:---
Exportar arquivos | cadeia de \[ caracteres de matriz\] | Uma lista de URLs de download para arquivos que segurando o instantâneo atual da organização | [  Https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2” ]
GeneratedTime | string | A hora em que a exportação foi gerada. | 2021-05-20T08:00:00Z ]

### <a name="26-examples"></a>2.6 Exemplos

#### <a name="261-request-example"></a>2.6.1 Exemplo de solicitação

```http
GET https://api.securitycenter.microsoft.com/api/machines/SecureConfigurationsAssessmentExport
```

#### <a name="262-response-example"></a>Exemplo de resposta 2.6.2

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#contoso.windowsDefenderATP.api.ExportFilesResponse",
    "exportFiles": [
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/ScaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/ScaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/ScaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c001.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=..."
    ],
    "generatedTime": "2021-01-11T11:01:00Z"
}
```

## <a name="see-also"></a>Confira também

- [Exportar métodos e propriedades de avaliação por dispositivo](get-assessmnt-1methods-properties.md)

- [Exportar avaliação de inventário de software por dispositivo](get-assessmnt-software-inventory.md)

- [Exportar a avaliação de vulnerabilidades de software por dispositivo](get-assessmnt-software-vulnerabilities.md)

Outros relacionados

- [Ameaças baseadas em risco & Gerenciamento de Vulnerabilidades](next-gen-threat-and-vuln-mgt.md)

- [Vulnerabilidades em sua organização](tvm-weaknesses.md)
