---
title: Exportar a avaliação de vulnerabilidades de software por dispositivo
description: A resposta da API é por dispositivo e contém software vulnerável instalado em seus dispositivos expostos, bem como quaisquer vulnerabilidades conhecidas nesses produtos de software. Esta tabela também inclui informações sobre o sistema operacional, as IDs do CVE e as informações sobre a severidade da vulnerabilidade.
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
ms.openlocfilehash: 849d1ab2bbc3b8f6d883d6041adda5fe4577741d
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789325"
---
# <a name="export-software-vulnerabilities-assessment-per-device"></a>Exportar a avaliação de vulnerabilidades de software por dispositivo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]
>
>
Retorna todas as vulnerabilidades de software conhecidas e seus detalhes para todos os dispositivos, por dispositivo.

Há diferentes chamadas de API para obter diferentes tipos de dados. Como a quantidade de dados pode ser grande, há duas maneiras de recuperá-las:

- [Exportar a avaliação de vulnerabilidades de software OData](#1-export-software-vulnerabilities-assessment-odata)  A API puxa todos os dados da sua organização como respostas Json, seguindo o protocolo OData. Esse método é melhor para _organizações pequenas com menos de 100 K dispositivos_. A resposta é paginada, portanto, você pode usar o campo odata.nextLink da resposta para \@ buscar os próximos resultados.

- [Exportar a avaliação de vulnerabilidades de software por meio de arquivos](#2-export-software-vulnerabilities-assessment-via-files) Essa solução de API permite a retirada de quantidades maiores de dados de forma mais rápida e confiável. Portanto, é recomendado para grandes organizações, com mais de 100 K dispositivos. Essa API puxa todos os dados da sua organização como arquivos de download. A resposta contém URLs para baixar todos os dados do Azure Armazenamento. Essa API permite baixar todos os dados do Azure Armazenamento a seguir:

  - Chame a API para obter uma lista de URLs de download com todos os dados da sua organização.

  - Baixe todos os arquivos usando as URLs de download e processe os dados conforme quiser.

Os dados coletados (usando _OData_ ou _por_ meio de arquivos ) são o instantâneo atual do estado atual e não contêm dados históricos. Para coletar dados históricos, os clientes devem salvar os dados em seus próprios armazenamentos de dados.

> [!Note]
>
> A menos que indicado de outra forma, todos os métodos de avaliação de exportação listados são **_exportação completa_** e **_por dispositivo_** (também chamado de **_por dispositivo)._**

## <a name="1-export-software-vulnerabilities-assessment-odata"></a>1. Avaliação de vulnerabilidades de software de exportação (OData)

### <a name="11-api-method-description"></a>Descrição do método API 1.1

Esta resposta à API contém todos os dados de software instalado por dispositivo. Retorna uma tabela com uma entrada para cada combinação exclusiva de DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.

#### <a name="limitations"></a>Limitações

>- O tamanho máximo da página é 200.000.
>
>- As limitações de taxa para essa API são 30 chamadas por minuto e 1.000 chamadas por hora.

### <a name="12-permissions"></a>1.2 Permissões

Uma das seguintes permissões é necessária para chamar essa API. Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs para obter detalhes.](apis-intro.md)

Tipo de permissão | Permissão | Nome de exibição de permissão
---|---|---
Aplicativo | Vulnerability.Read.All | \'Ler informações de vulnerabilidade de Gerenciamento de Ameaças e Vulnerabilidades\'
Delegado (conta corporativa ou de estudante) | Vulnerability.Read | \'Ler informações de vulnerabilidade de Gerenciamento de Ameaças e Vulnerabilidades\'

### <a name="13-url"></a>URL 1.3

```http
GET /api/machines/SoftwareVulnerabilitiesByMachine
```

### <a name="14-parameters"></a>Parâmetros 1.4

- pageSize (padrão = 50.000) – número de resultados em resposta
- $top – número de resultados a retornar (não retorna @odata.nextLink e, portanto, não puxa todos os dados)

### <a name="15-properties"></a>1.5 Propriedades
>
>[!Note]
>
>- Cada registro é de aproximadamente 1KB de dados. Você deve levar isso em consideração ao escolher o parâmetro pageSize correto para você.
>
>- Algumas colunas adicionais podem ser retornadas na resposta. Essas colunas são temporárias e podem ser removidas, use apenas as colunas documentadas.
>
>- As propriedades definidas na tabela a seguir são listadas em ordem alfabética, por ID da propriedade.  Ao executar essa API, a saída resultante não será necessariamente retornada na mesma ordem listada nesta tabela.
>

Propriedade (ID) | Tipo de dados | Descrição | Exemplo de um valor retornado
:---|:---|:---|:---
CveId | cadeia de caracteres | Identificador exclusivo atribuído à vulnerabilidade de segurança no sistema CVE (Common Vulnerabilities and Exposures). | CVE-2020-15992
CvssScore | cadeia de caracteres | A pontuação CVSS do CVE. | 6.2
DeviceId | cadeia de caracteres | Identificador exclusivo do dispositivo no serviço. | 9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1
DeviceName | cadeia de caracteres | Nome de domínio totalmente qualificado (FQDN) do dispositivo. | johnlaptop.europe.contoso.com
DiskPaths  | Cadeia de \[ caracteres de matriz\] | Evidência em disco de que o produto está instalado no dispositivo. | [ "C:\Arquivos de Programas (x86)\Microsoft\Silverlight\Application\silverlight.exe" ]
ExploitabilityLevel | cadeia de caracteres | O nível de exploração dessa vulnerabilidade (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit) | ExploitIsInKit
FirstSeenTimestamp | cadeia de caracteres | Primeira vez que o CVE deste produto foi visto no dispositivo. | 2020-11-03 10:13:34.8476880
Id | cadeia de caracteres | Identificador exclusivo do registro. | 123ABG55_573AG&mnp!
LastSeenTimestamp | cadeia de caracteres | A última vez que o CVE foi visto no dispositivo. | 2020-11-03 10:13:34.8476880
OSPlatform | cadeia de caracteres | Plataforma do sistema operacional em execução no dispositivo. Isso indica os sistemas operacionais específicos, incluindo variações na mesma família, como o Windows 10 e o Windows 7. Confira sistemas operacionais e plataformas com suporte para TVM para obter detalhes. | Windows10
RbacGroupName  | cadeia de caracteres | O grupo controle de acesso baseado em função (RBAC). Se esse dispositivo não for atribuído a nenhum grupo RBAC, o valor será "Não atribuído". Se a organização não tiver nenhum grupo RBAC, o valor será "None". | Servidores
RecommendationReference | cadeia de caracteres | Uma referência à ID de recomendação relacionada a este software. | va-_-microsoft-_-silverlight
RecommendedSecurityUpdate (opcional) | cadeia de caracteres | Nome ou descrição da atualização de segurança fornecida pelo fornecedor de software para resolver a vulnerabilidade. | Atualizações de segurança de abril de 2020
RecommendedSecurityUpdateId (opcional) | cadeia de caracteres | Identificador das atualizações de segurança ou identificador aplicáveis para os artigos de base de conhecimento ou orientação correspondentes (KB) | 4550961
RegistryPaths  | Cadeia de \[ caracteres de matriz\] | Evidência do Registro de que o produto está instalado no dispositivo. | [ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\MicrosoftSilverlight" ]
SoftwareName | cadeia de caracteres | Nome do produto de software. | chrome
SoftwareVendor | cadeia de caracteres | Nome do fornecedor de software. | google
SoftwareVersion | cadeia de caracteres | Número da versão do produto de software. | 81.0.4044.138
VulnerabilitySeverityLevel  | cadeia de caracteres | Nível de severidade atribuído à vulnerabilidade de segurança com base na pontuação cvss e fatores dinâmicos influenciados pelo cenário de ameaças. | Médio

### <a name="16-examples"></a>1.6 Exemplos

#### <a name="161-request-example"></a>1.6.1 Exemplo de solicitação

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareVulnerabilitiesByMachine?pageSize=5
```

#### <a name="162-response-example"></a>Exemplo de resposta 1.6.2

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.AssetVulnerability)",
    "value": [
        {
            "id": "00044f612345baf759462dbe6db733b6a9c59ab4_edge_10.0.17763.1637__",
            "deviceId": "00044f612345daf756462bde6bd733b9a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eed224b2de2f5ea3142726e63f16a.DomainPII_21eeb80d089e79bdfa178eabfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "edge",
            "softwareVersion": "10.0.17763.1637",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [],
            "lastSeenTimestamp": "2020-12-30 14:17:26",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-edge"
        },
        {
            "id": "00044f912345baf756462bde6db733b9a9c56ad4_.net_framework_4.0.0.0__",
            "deviceId": "00044f912345daf756462bde6db733b6a9c59ad4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eed224b2be2f5ea3142726e63f16a.DomainPII_21eeb80b086e79bdfa178eabfa25e8de6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": ".net_framework",
            "softwareVersion": "4.0.0.0",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [
                "SOFTWARE\\Microsoft\\NET Framework Setup\\NDP\\v4.0\\Client\\Install"
            ],
            "lastSeenTimestamp": "2020-12-30 13:18:33",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-.net_framework"
        },
        {
            "id": "00044f912345baf756462dbe6db733d6a9c59ab4_system_center_2012_endpoint_protection_4.10.209.0__",
            "deviceId": "00044f912345daf756462bde6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eed224b2be2f5ea3142726e63f16a.DomainPII_21eed80b089e79bdfa178eadfa25e8be6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "system_center_2012_endpoint_protection",
            "softwareVersion": "4.10.209.0",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Security Client"
            ],
            "lastSeenTimestamp": "2020-12-30 14:17:26",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-system_center_2012_endpoint_protection"
        },
        {
            "id": "00044f612345bdaf759462dbe6bd733b6a9c59ab4_onedrive_20.245.1206.2__",
            "deviceId": "00044f91234daf759492dbe6bd733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_189663d45612eed224b2be2f5ea3142729e63f16a.DomainPII_21eed80b086e79bdfa178eadfa25e8de6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "onedrive",
            "softwareVersion": "20.245.1206.2",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_USERS\\S-1-5-21-2944539346-1310925172-2349113062-1001\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\OneDriveSetup.exe"
            ],
            "lastSeenTimestamp": "2020-12-30 13:18:33",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-onedrive"
        },
        {
            "id": "00044f912345daf759462bde6db733b6a9c56ab4_windows_10_10.0.17763.1637__",
            "deviceId": "00044f912345daf756462dbe6db733d6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eeb224d2be2f5ea3142729e63f16a.DomainPII_21eeb80d086e79bdfa178eadfa25e8de6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "windows_10",
            "softwareVersion": "10.0.17763.1637",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [],
            "lastSeenTimestamp": "2020-12-30 14:17:26",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-windows_10"
        }
    ],
    "@odata.nextLink": "https://api.securitycenter.microsoft.com/api/machines/SoftwareVulnerabilitiesByMachine?pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0xMS8xMTAxLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9"
}
```

## <a name="2-export-software-vulnerabilities-assessment-via-files"></a>2. Exportar a avaliação de vulnerabilidades de software (por meio de arquivos)

### <a name="21-api-method-description"></a>Descrição do método API 2.1

Esta resposta à API contém todos os dados de software instalado por dispositivo. Retorna uma tabela com uma entrada para cada combinação exclusiva de DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.

#### <a name="212-limitations"></a>2.1.2 Limitações

As limitações de taxa para essa API são 5 chamadas por minuto e 20 chamadas por hora.

### <a name="22-permissions"></a>2.2 Permissões

Uma das seguintes permissões é necessária para chamar essa API. Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs para obter detalhes.](apis-intro.md)

Tipo de permissão | Permissão | Nome de exibição de permissão
---|---|---
Aplicativo | Vulnerability.Read.All | \'Ler informações de vulnerabilidade de Gerenciamento de Ameaças e Vulnerabilidades\'
Delegado (conta corporativa ou de estudante) | Vulnerability.Read | \'Ler informações de vulnerabilidade de Gerenciamento de Ameaças e Vulnerabilidades\'

### <a name="23-url"></a>URL 2.3

```http
GET /api/machines/SoftwareVulnerabilitiesExport
```

### <a name="24-parameters"></a>Parâmetros 2.4

- sasValidHours – O número de horas em que as URLs de download serão válidas (Máximo de 24 horas)

### <a name="25-properties"></a>2.5 Propriedades

>[!Note]
>
>- Os arquivos são gzip compactados & no formato Json de várias linhas.
>
>- As URLs de download só são válidas por 3 horas; caso contrário, você pode usar o parâmetro.
>
>- Para a velocidade máxima de download de seus dados, você pode garantir que você está baixando da mesma região do Azure que seus dados residem.
>

>[!Note]
>
>- Cada registro é de aproximadamente 1KB de dados. Você deve levar isso em consideração ao escolher o parâmetro pageSize correto para você.
>
>- Algumas colunas adicionais podem ser retornadas na resposta. Essas colunas são temporárias e podem ser removidas, use apenas as colunas documentadas.
>

Propriedade (ID) | Tipo de dados | Descrição | Exemplo de um valor retornado
:---|:---|:---|:---
Exportar arquivos | cadeia de \[ caracteres de matriz\]  | Uma lista de URLs de download para arquivos que segurando o instantâneo atual da organização. | [  “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2”  ]
GeneratedTime | cadeia de caracteres | A hora em que a exportação foi gerada. | 2021-05-20T08:00:00Z

### <a name="26-examples"></a>2.6 Exemplos

#### <a name="261-request-example"></a>2.6.1 Exemplo de solicitação

```http
GET https://api-us.securitycenter.contoso.com/api/machines/SoftwareVulnerabilitiesExport
```

#### <a name="262-response-example"></a>Exemplo de resposta 2.6.2

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.ExportFilesResponse",
    "exportFiles": [
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/VaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-bcc26c4f-e531-48db-9892-c93ac5d72d5c.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A35%3A13Z&se=2021-01-11T14%3A35%3A13Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/VaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-bcc26c4f-e531-48db-9892-c93ac5d72d5c.c001.json.gz?sv=2019-12-12&st=2021-01-11T11%3A35%3A13Z&se=2021-01-11T14%3A35%3A13Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/VaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-bcc26c4f-e531-48db-9892-c93ac5d72d5c.c002.json.gz?sv=2019-12-12&st=2021-01-11T11%3A35%3A13Z&se=2021-01-11T14%3A35%3A13Z&sr=b&sp=r&sig=..."
    ],
    "generatedTime": "2021-01-11T11:01:00Z"
}
```

## <a name="see-also"></a>Confira também

- [Exportar métodos e propriedades de avaliação por dispositivo](get-assessment-methods-properties.md)

- [Exportar avaliação de configuração segura por dispositivo](get-assessment-secure-config.md)

- [Exportar avaliação de inventário de software por dispositivo](get-assessment-software-inventory.md)

Outros relacionados

- [Ameaças baseadas em risco & Gerenciamento de Vulnerabilidades](next-gen-threat-and-vuln-mgt.md)

- [Vulnerabilidades em sua organização](tvm-weaknesses.md)
