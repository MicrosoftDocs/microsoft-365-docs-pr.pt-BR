---
title: Exportar avaliação de inventário de software por dispositivo
description: Retorna uma tabela com uma entrada para cada combinação exclusiva de DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion.
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
ms.openlocfilehash: 5663a17de2e601c506b4d1b9ac44eaab6ae6245f
ms.sourcegitcommit: 82a4d74020cd93ba444006317cfecc178c6d41dc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2021
ms.locfileid: "52689184"
---
# <a name="export-software-inventory-assessment-per-device"></a>Exportar avaliação de inventário de software por dispositivo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]
>
>
Há diferentes chamadas de API para obter diferentes tipos de dados. Como a quantidade de dados pode ser muito grande, há duas maneiras de recuperá-las:

- [Exportar o **OData** de avaliação do inventário de software](#1-export-software-inventory-assessment-odata)  A API puxa todos os dados da sua organização como respostas Json, seguindo o protocolo OData. Esse método é melhor para _organizações pequenas com menos de 100 K dispositivos_. A resposta é paginada, portanto, você pode usar o campo odata.nextLink da resposta para \@ buscar os próximos resultados.

- [Exportar a avaliação do inventário de software **por meio de arquivos**](#2-export-software-inventory-assessment-via-files)  Essa solução de API permite a retirada de quantidades maiores de dados de forma mais rápida e confiável. Portanto, é recomendado para grandes organizações, com mais de 100 K dispositivos. Essa API puxa todos os dados da sua organização como arquivos de download. A resposta contém URLs para baixar todos os dados do Azure Armazenamento. Essa API permite baixar todos os dados do Azure Armazenamento a seguir:

  - Chame a API para obter uma lista de URLs de download com todos os dados da sua organização.

  - Baixe todos os arquivos usando as URLs de download e processe os dados conforme quiser.

Os dados coletados (usando _OData_ ou _por_ meio de arquivos ) são o instantâneo atual do estado atual e não contêm dados históricos. Para coletar dados históricos, os clientes devem salvar os dados em seus próprios armazenamentos de dados.

> [!Note]
>
> A menos que indicado de outra forma, todos os métodos de avaliação de exportação listados são **_exportação completa_** e **_por dispositivo_** (também chamado de **_por dispositivo)._**

## <a name="1-export-software-inventory-assessment-odata"></a>1. Exportar avaliação de inventário de software (OData)

### <a name="11-api-method-description"></a>Descrição do método API 1.1

Esta resposta à API contém todos os dados de software instalado por dispositivo. Retorna uma tabela com uma entrada para cada combinação exclusiva de DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion.

#### <a name="limitations"></a>Limitações

- O tamanho máximo da página é 200.000.

- As limitações de taxa para essa API são 30 chamadas por minuto e 1.000 chamadas por hora.

### <a name="12-permissions"></a>1.2 Permissões

Uma das seguintes permissões é necessária para chamar essa API. Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs para obter detalhes.](apis-intro.md)

Tipo de permissão | Permissão | Nome de exibição de permissão
---|---|---
Aplicativo | Software.Read.All | \'Ler informações de vulnerabilidade de Gerenciamento de Ameaças e Vulnerabilidades\'
Delegada (conta corporativa ou de estudante) | Software.Read | \'Ler informações de vulnerabilidade de Gerenciamento de Ameaças e Vulnerabilidades\'

### <a name="13-url"></a>URL 1.3

```http
GET /api/machines/SoftwareInventoryByMachine
```

### <a name="14-parameters"></a>Parâmetros 1.4

- pageSize (padrão = 50.000) – número de resultados em resposta.

- $top – número de resultados a retornar (não retorna @odata.nextLink e, portanto, não puxa todos os dados)

### <a name="15-properties"></a>1.5 Propriedades

>[!NOTE]
>
>-Cada registro é de aproximadamente 0,5KB de dados. Você deve levar isso em consideração ao escolher o parâmetro pageSize correto para você.

>-As propriedades definidas na tabela a seguir são listadas em ordem alfabética, por ID da propriedade. Ao executar essa API, a saída resultante não será necessariamente retornada na mesma ordem listada nesta tabela.
>
>-Algumas colunas adicionais podem ser retornadas na resposta. Essas colunas são temporárias e podem ser removidas, use apenas as colunas documentadas.

Propriedade (ID) | Tipo de dados | Descrição | Exemplo de um valor retornado
:---|:---|:---|:---
DeviceId | cadeia de caracteres | Identificador exclusivo do dispositivo no serviço. | 9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1
DeviceName | cadeia de caracteres | Nome de domínio totalmente qualificado (FQDN) do dispositivo. | johnlaptop.europe.contoso.com
DiskPaths | Array[string]  | Evidência em disco de que o produto está instalado no dispositivo. | [ "C: \\ Arquivos de Programa (x86) \\ Microsoft \\ Silverlight \\ Application \\silverlight.exe" ]
EndOfSupportDate | cadeia de caracteres | A data em que o suporte para este software tem ou terminará. | 2020-12-30
EndOfSupportStatus | cadeia de caracteres | Status do fim do suporte. Pode conter esses valores possíveis: None, Versão EOS, Versão EOS futura, Software EOS, Software EOS futuro. | EOS futuro
Id | cadeia de caracteres | Identificador exclusivo do registro. | 123ABG55_573AG&mnp!
NumberOfWeaknesses | int | Número de pontos fracos neste software neste dispositivo | 3
OSPlatform | cadeia de caracteres | Plataforma do sistema operacional em execução no dispositivo. Isso indica os sistemas operacionais específicos, incluindo variações na mesma família, como o Windows 10 e o Windows 7. Confira sistemas operacionais e plataformas com suporte para TVM para obter detalhes. | Windows10
RbacGroupName | cadeia de caracteres | O grupo controle de acesso baseado em função (RBAC). Se esse dispositivo não for atribuído a nenhum grupo RBAC, o valor será "Não atribuído". Se a organização não tiver nenhum grupo RBAC, o valor será "None". | Servidores
RegistryPaths | Array[string] | Evidência do Registro de que o produto está instalado no dispositivo. | [ "HKEY_LOCAL_MACHINE \\ SOFTWARE \\ WOW6432Node \\ Microsoft Windows \\ \\ CurrentVersion \\ Desinstalar \\ o Microsoft Silverlight" ]
SoftwareFirstSeenTimestamp | cadeia de caracteres | A primeira vez que esse software foi visto no dispositivo. | 2019-04-07 02:06:47
SoftwareName | cadeia de caracteres | Nome do produto de software. | Silverlight
SoftwareVendor | cadeia de caracteres | Nome do fornecedor de software. | microsoft
SoftwareVersion | cadeia de caracteres | Número da versão do produto de software. | 81.0.4044.138

### <a name="16-examples"></a>1.6 Exemplos

#### <a name="161-request-example"></a>1.6.1 Exemplo de solicitação

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryByMachine?pageSize=5  &sinceTime=2021-05-19T18%3A35%3A49.924Z 
```

#### <a name="162-response-example"></a>Exemplo de resposta 1.6.2

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(contoso.windowsDefenderATP.api.AssetSoftware)",
    "value": [
        {
            "deviceId": "00044f68765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eeb80d086e79dbfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": "windows_10",
            "softwareVersion": "10.0.17763.1637",
            "numberOfWeaknesses": 58,
            "diskPaths": [],
            "registryPaths": [],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "Upcoming EOS Version",
            "endOfSupportDate": "2021-05-11T00:00:00+00:00"
        },
        {
            "deviceId": "00044f68765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eeb80d086e79dbfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": ".net_framework",
            "softwareVersion": "4.0.0.0",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "SOFTWARE\\Microsoft\\NET Framework Setup\\NDP\\v4.0\\Client\\Install"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        },
        {
            "deviceId": "00044f68765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eed80d086e79bdfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": "system_center_2012_endpoint_protection",
            "softwareVersion": "4.7.214.0",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Security Client"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        },
        {
            "deviceId": "00044f68765ddaf71234bde6bd733d6a9c59ad4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eeb80d086e79dbfa178aedfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": "configuration_manager",
            "softwareVersion": "5.0.8634.1000",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\{B7D3A842-E826-4542-B39B-1D883264B279}"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        },
        {
            "deviceId": "00044f38765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2de2f5ea3142726e63f16a.DomainPII_21eeb80d086e79bdfa178eadfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": "system_center_2012_endpoint_protection",
            "softwareVersion": "4.10.209.0",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Security Client"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        }
    ],
    "@odata.nextLink": "https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryByMachine?pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0yNS8wMjAwLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9"
}
```

## <a name="2-export-software-inventory-assessment-via-files"></a>2. Exportar avaliação de inventário de software (por meio de arquivos)

### <a name="21-api-method-description"></a>Descrição do método API 2.1

Esta resposta à API contém todos os dados de software instalado por dispositivo. Retorna uma tabela com uma entrada para cada combinação exclusiva de DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion.

#### <a name="211-limitations"></a>2.1.1 Limitações

As limitações de taxa para essa API são 5 chamadas por minuto e 20 chamadas por hora.

### <a name="22-permissions"></a>2.2 Permissões

Uma das seguintes permissões é necessária para chamar essa API. Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs para obter detalhes.](apis-intro.md)

Tipo de permissão | Permissão | Nome de exibição de permissão
---|---|---
Aplicativo | Software.Read.All | \'Ler informações de vulnerabilidade de Gerenciamento de Ameaças e Vulnerabilidades\'
Delegada (conta corporativa ou de estudante) | Software.Read | \'Ler informações de vulnerabilidade de Gerenciamento de Ameaças e Vulnerabilidades\'

### <a name="23-url"></a>URL 2.3

```http
GET /api/machines/SoftwareInventoryExport
```

### <a name="parameters"></a>Parâmetros

- sasValidHours – O número de horas em que as URLs de download serão válidas (Máximo de 24 horas)

### <a name="25-properties"></a>2.5 Propriedades

>[!Note]
>
>- Os arquivos são gzip compactados & no formato Json de várias linhas.
>
>- As URLs de download só são válidas por 3 horas. Caso contrário, você pode usar o parâmetro.
>
>_ Para a velocidade máxima de download de seus dados, você pode garantir que você está baixando da mesma região do Azure que seus dados residem.
>
Propriedade (ID) | Tipo de dados | Descrição | Exemplo de um valor retornado
:---|:---|:---|:---
Exportar arquivos | cadeia de \[ caracteres de matriz\] | Uma lista de URLs de download para arquivos que segurando o instantâneo atual da organização | [  Https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2” ]
GeneratedTime | cadeia de caracteres | A hora em que a exportação foi gerada. | 2021-05-20T08:00:00Z ]

### <a name="26-examples"></a>2.6 Exemplos

#### <a name="261-request-example"></a>2.6.1 Exemplo de solicitação

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryExport
```

#### <a name="262-response-example"></a>Exemplo de resposta 2.6.2

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.ExportFilesResponse",
    "exportFiles": [
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/SoftwareInventory/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/SoftwareInventory/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/SoftwareInventory/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c001.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=..."
    ],
    "generatedTime": "2021-01-11T11:01:00Z"
}
```

## <a name="see-also"></a>Confira também

- [Exportar métodos e propriedades de avaliação por dispositivo](get-assessmnt-1methods-properties.md)

- [Exportar avaliação de configuração segura por dispositivo](get-assessmnt-secure-cfg.md)

- [Exportar a avaliação de vulnerabilidades de software por dispositivo](get-assessmnt-software-vulnerabilities.md)

Outros relacionados

- [Ameaças baseadas em risco & Gerenciamento de Vulnerabilidades](next-gen-threat-and-vuln-mgt.md)

- [Vulnerabilidades em sua organização](tvm-weaknesses.md)
