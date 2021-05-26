---
title: Exportar métodos e propriedades de avaliação por dispositivo
description: Fornece informações sobre as APIs que puxam dados "Gerenciamento de Ameaças e Vulnerabilidades". Há diferentes chamadas de API para obter diferentes tipos de dados. Em geral, cada chamada de API contém os dados necessários para dispositivos em sua organização. Como a quantidade de dados pode ser muito grande, há duas maneiras de recuperá-las
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
ms.openlocfilehash: 851c792265375e5905c0c427bfc77a2366bc962d
ms.sourcegitcommit: 727a75b604d5ff5946a0854662ad5a8b049f2874
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2021
ms.locfileid: "52653617"
---
# <a name="export-assessment-methods-and-properties-per-device"></a>Exportar métodos e propriedades de avaliação por dispositivo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="api-description"></a>Descrição da API

Fornece métodos e detalhes de propriedade sobre as APIs que Gerenciamento de Ameaças e Vulnerabilidades dados por dispositivo. Há diferentes chamadas de API para obter diferentes tipos de dados. Em geral, cada chamada de API contém os dados necessários para dispositivos em sua organização.

> [!Note]
>
> A menos que indicado de outra forma, todos os métodos de avaliação de exportação listados são **_exportação completa_** e **_por dispositivo_** (também chamado de **_por dispositivo)._**

Há diferentes chamadas de API para obter diferentes tipos de dados. Como a quantidade de dados pode ser grande, há duas maneiras de recuperá-las:

- **OData**  A API puxa todos os dados da sua organização como respostas Json, seguindo o protocolo OData. Esse método é melhor para _organizações pequenas com menos de 100 mil dispositivos_. A resposta é paginada, portanto, você pode usar o campo odata.nextLink da resposta para \@ buscar os próximos resultados.

- **via arquivos** Essa solução de API permite a retirada de quantidades maiores de dados de forma mais rápida e confiável. Portanto, é recomendado para grandes organizações, com mais de 100 mil dispositivos. Essa API puxa todos os dados da sua organização como arquivos de download. A resposta contém URLs para baixar todos os dados do Azure Armazenamento. Essa API permite baixar todos os dados do Azure Armazenamento a seguir:

  - Chame a API para obter uma lista de URLs de download com todos os dados da sua organização.

  - Baixe todos os arquivos usando as URLs de download e processe os dados conforme quiser.

Os dados coletados (para _OData_ ou por meio de arquivos _)_ são o instantâneo atual do estado atual e não contêm dados históricos. Para coletar dados históricos, os clientes devem salvar os dados em seus próprios armazenamentos de dados.

A menos que indicado de outra forma, todos os métodos de avaliação de exportação listados são **_exportação completa_** e **_por dispositivo_** (também chamado de **_por dispositivo)._**

## <a name="1-export-secure-configurations-assessment"></a>1. Exportar a avaliação de configurações seguras

Retorna todas as configurações e seu status, por dispositivo.

### <a name="11-methods"></a>Métodos 1.1

Método | Tipo de dados | Descrição
:---|:---|:---
[Exportar a avaliação de configuração segura (OData)](get-assessmnt-secure-cfg.md#1-export-secure-configuration-assessment-odata) | Configuração segura por conjunto de dispositivos. Consulte: [Propriedades 1.2 (OData)](#12-properties-odata) | Retorna uma tabela com uma entrada para cada combinação exclusiva de DeviceId, ConfigurationId. Os dados coletados (para _OData_ ou por meio de arquivos _)_ são o instantâneo atual do estado atual e não contêm dados históricos. Para coletar dados históricos, os clientes devem salvar os dados em seus próprios armazenamentos de dados.
[Exportar a avaliação de configuração segura (por meio de arquivos)](get-assessmnt-secure-cfg.md#2-export-secure-configuration-assessment-via-files) | configuração segura por arquivos de dispositivo. Consulte: [1.3 Propriedades (por meio de arquivos)](#13-properties-via-files) | Retorna uma tabela com uma entrada para cada combinação exclusiva de DeviceId, ConfigurationId. Essa solução de API permite a retirada de quantidades maiores de dados de forma mais rápida e confiável. Portanto, é recomendado para grandes organizações, com mais de 100 mil dispositivos. Essa API puxa todos os dados da sua organização como arquivos de download. A resposta contém URLs para baixar todos os dados do Azure Armazenamento. Essa API permite baixar todos os dados do Azure Armazenamento a seguir: 1.  Chame a API para obter uma lista de URLs de download com todos os dados da sua organização. 2.  Baixe todos os arquivos usando as URLs de download e processe os dados conforme quiser.

### <a name="12-properties-odata"></a>Propriedades 1.2 (OData)

Propriedade (ID) | Tipo de dados | Descrição
:---|:---|:---
ConfigurationCategory | string | Categoria ou agrupamento ao qual a configuração pertence: aplicativo, sistema operacional, rede, contas, controles de segurança
ConfigurationId | string | Identificador exclusivo para uma configuração específica
ConfigurationImpact | string | Impacto avaliado da configuração na classificação total (1-10)
ConfigurationName | string | Exibir o nome da configuração
ConfigurationSubcategory | string | Subcategoria ou subgrupo ao qual a configuração pertence. Em muitos casos, isso descreve capacidades ou recursos específicos.
DeviceId | string | Identificador exclusivo do dispositivo no serviço.
DeviceName | string | Nome de domínio totalmente qualificado (FQDN) do dispositivo.
IsApplicable | bool | Indica se a configuração ou a política é aplicável
IsCompliant | bool | Indica se a configuração ou política está configurada corretamente
IsExpectedUserImpact | bool | Indica se haverá impacto do usuário se a configuração será aplicada
OSPlatform | string | Plataforma do sistema operacional em execução no dispositivo. Isso indica os sistemas operacionais específicos, incluindo variações na mesma família, como o Windows 10 e o Windows 7. Confira sistemas operacionais e plataformas com suporte para TVM para obter detalhes.
RbacGroupName | string | O grupo controle de acesso baseado em função (RBAC). Se esse dispositivo não for atribuído a nenhum grupo RBAC, o valor será "Não atribuído". Se a organização não tiver nenhum grupo RBAC, o valor será "None".
RecommendationReference | string | Uma referência à ID de recomendação relacionada a este software.
Carimbo de data/hora | string | Última vez que a configuração foi vista no dispositivo

### <a name="13-properties-via-files"></a>1.3 Propriedades (por meio de arquivos)

Propriedade (ID) | Tipo de dados | Descrição
:---|:---|:---
Exportar arquivos | cadeia de \[ caracteres de matriz\] | Uma lista de URLs de download para arquivos que segurando o instantâneo atual da organização.
GeneratedTime | string | A hora em que a exportação foi gerada.

## <a name="2-export-software-inventory-assessment"></a>2. Exportar avaliação de inventário de software

Retorna todo o software instalado e seus detalhes em cada dispositivo.

### <a name="21-methods"></a>Métodos 2.1

Método | Tipo de dados | Descrição
:---|:---|:---
[Avaliação de inventário de software de exportação (OData)](get-assessmnt-software-inventory.md#1-export-software-inventory-assessment-odata) | Inventário de software por conjunto de dispositivos. Consulte: [Propriedades 2.2 (OData)](#22-properties-odata) | Retorna uma tabela com uma entrada para cada combinação exclusiva de DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion. Os dados coletados (para _OData_ ou por meio de arquivos _)_ são o instantâneo atual do estado atual e não contêm dados históricos. Para coletar dados históricos, os clientes devem salvar os dados em seus próprios armazenamentos de dados.
[Exportar avaliação de inventário de software (por meio de arquivos)](get-assessmnt-software-inventory.md#2-export-software-inventory-assessment-via-files) | Inventário de software por arquivos de dispositivo. Consulte: [2.3 Propriedades (por meio de arquivos)](#23-properties-via-files) | Retorna uma tabela com uma entrada para cada combinação exclusiva de DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion. Essa solução de API permite a retirada de quantidades maiores de dados de forma mais rápida e confiável. Portanto, é recomendado para grandes organizações, com mais de 100 mil dispositivos. Essa API puxa todos os dados da sua organização como arquivos de download. A resposta contém URLs para baixar todos os dados do Azure Armazenamento. Essa API permite baixar todos os dados do Azure Armazenamento a seguir: 1.  Chame a API para obter uma lista de URLs de download com todos os dados da sua organização. 2.  Baixe todos os arquivos usando as URLs de download e processe os dados conforme quiser.

### <a name="22-properties-odata"></a>Propriedades 2.2 (OData)

Propriedade (ID) | Tipo de dados | Descrição
:---|:---|:---
DeviceId | string | Identificador exclusivo do dispositivo no serviço.
DeviceName | string | Nome de domínio totalmente qualificado (FQDN) do dispositivo.
DiskPaths | Array[string]  | Evidência em disco de que o produto está instalado no dispositivo.
EndOfSupportDate | string | A data em que o suporte para este software tem ou terminará.
EndOfSupportStatus | string | Status do fim do suporte. Pode conter esses valores possíveis: None, Versão EOS, Versão EOS futura, Software EOS, Software EOS futuro.
Id | cadeia de caracteres | Identificador exclusivo do registro.
NumberOfWeaknesses | int|Número de pontos fracos neste software neste dispositivo
OSPlatform | string | Plataforma do sistema operacional em execução no dispositivo. Isso indica os sistemas operacionais específicos, incluindo variações na mesma família, como o Windows 10 e o Windows 7. Confira sistemas operacionais e plataformas com suporte para TVM para obter detalhes.
RbacGroupName | string | O grupo controle de acesso baseado em função (RBAC). Se esse dispositivo não for atribuído a nenhum grupo RBAC, o valor será "Não atribuído". Se a organização não tiver nenhum grupo RBAC, o valor será "None".
RegistryPaths | Array[string] | Evidência do Registro de que o produto está instalado no dispositivo.
SoftwareFirstSeenTimestamp | string | A primeira vez que esse software foi visto no dispositivo.
SoftwareName | string | Nome do produto de software.
SoftwareVendor | string | Nome do fornecedor de software.
SoftwareVersion | string | Número da versão do produto de software.

### <a name="23-properties-via-files"></a>2.3 Propriedades (por meio de arquivos)

Propriedade (ID) | Tipo de dados | Descrição
:---|:---|:---
Exportar arquivos | cadeia de \[ caracteres de matriz\] | Uma lista de URLs de download para arquivos que segurando o instantâneo atual da organização.
GeneratedTime | string | A hora em que a exportação foi gerada.

## <a name="3-export-software-vulnerabilities-assessment-per-device"></a>3. Exportar a avaliação de vulnerabilidades de software por dispositivo

Retorna todas as vulnerabilidades conhecidas em um dispositivo e seus detalhes, para todos os dispositivos.

### <a name="31-methods"></a>Métodos 3.1

Método | Tipo de dados | Descrição
:---|:---|:---
[Avaliação de vulnerabilidades de software de exportação (OData)](get-assessmnt-software-vulnerabilities.md#1-export-software-vulnerabilities-assessment-odata) | Coleção Investigation See: [3.2 Properties (OData)](#32-properties-odata) | Retorna uma tabela com uma entrada para cada combinação exclusiva de DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId. Os dados coletados (para _OData_ ou por meio de arquivos _)_ são o instantâneo atual do estado atual e não contêm dados históricos. Para coletar dados históricos, os clientes devem salvar os dados em seus próprios armazenamentos de dados.
[Avaliação de vulnerabilidades de software de exportação (por meio de arquivos)](get-assessmnt-software-vulnerabilities.md#2-export-software-vulnerabilities-assessment-via-files) | Entidade de investigação Consulte: [Propriedades 3.3 (por meio de arquivos)](#33-properties-via-files) | Retorna uma tabela com uma entrada para cada combinação exclusiva de DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId. Essa solução de API permite a retirada de quantidades maiores de dados de forma mais rápida e confiável. Portanto, é recomendado para grandes organizações, com mais de 100 mil dispositivos. Essa API puxa todos os dados da sua organização como arquivos de download. A resposta contém URLs para baixar todos os dados do Azure Armazenamento. Essa API permite baixar todos os dados do Azure Armazenamento a seguir: 1.  Chame a API para obter uma lista de URLs de download com todos os dados da sua organização. 2.  Baixe todos os arquivos usando as URLs de download e processe os dados conforme quiser.

### <a name="32-properties-odata"></a>Propriedades 3.2 (OData)

Propriedade (ID) | Tipo de dados | Descrição
:---|:---|:---
CveId | string | Identificador exclusivo atribuído à vulnerabilidade de segurança no sistema CVE (Common Vulnerabilities and Exposures).
CvssScore | string | A pontuação CVSS do CVE.
DeviceId | string | Identificador exclusivo do dispositivo no serviço.
DeviceName | string | Nome de domínio totalmente qualificado (FQDN) do dispositivo.
DiskPaths | Cadeia de \[ caracteres de matriz\] | Evidência em disco de que o produto está instalado no dispositivo.
ExploitabilityLevel | string | O nível de exploração dessa vulnerabilidade (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)
FirstSeenTimestamp | string | Primeira vez que o CVE deste produto foi visto no dispositivo.
Id | cadeia de caracteres | Identificador exclusivo do registro.
LastSeenTimestamp | string | A última vez que o CVE foi visto no dispositivo.
OSPlatform | string | Plataforma do sistema operacional em execução no dispositivo. Isso indica os sistemas operacionais específicos, incluindo variações na mesma família, como o Windows 10 e o Windows 7. Confira sistemas operacionais e plataformas com suporte para TVM para obter detalhes.
RbacGroupName | string | O grupo controle de acesso baseado em função (RBAC). Se esse dispositivo não for atribuído a nenhum grupo RBAC, o valor será "Não atribuído". Se a organização não tiver nenhum grupo RBAC, o valor será "None".
RecommendationReference | string | Uma referência à ID de recomendação relacionada a este software.
RecommendedSecurityUpdate | string | Nome ou descrição da atualização de segurança fornecida pelo fornecedor de software para resolver a vulnerabilidade.
RecommendedSecurityUpdateId | string | Identificador das atualizações de segurança ou identificador aplicáveis para os artigos de base de conhecimento ou orientação correspondentes (KB)
Cadeia de caracteres da Matriz de Caminhos do \[ Registro\] | Evidência do Registro de que o produto está instalado no dispositivo.
SoftwareName | string | Nome do produto de software.
SoftwareVendor | string | Nome do fornecedor de software.
SoftwareVersion | string | Número da versão do produto de software.
VulnerabilitySeverityLevel | string | Nível de severidade atribuído à vulnerabilidade de segurança com base na pontuação cvss e fatores dinâmicos influenciados pelo cenário de ameaças.

### <a name="33-properties-via-files"></a>Propriedades 3.3 (por meio de arquivos)

Propriedade (ID) | Tipo de dados | Descrição
:---|:---|:---
Exportar arquivos | cadeia de \[ caracteres de matriz\]  | Uma lista de URLs de download para arquivos que segurando o instantâneo atual da organização.
GeneratedTime | string | A hora em que a exportação foi gerada.

## <a name="see-also"></a>Confira também

- [Exportar avaliação de configuração segura por dispositivo](get-assessmnt-secure-cfg.md)

- [Exportar avaliação de inventário de software por dispositivo](get-assessmnt-software-inventory.md)

- [Exportar a avaliação de vulnerabilidades de software por dispositivo](get-assessmnt-software-vulnerabilities.md)

Outros relacionados

- [Ameaças baseadas em risco & Gerenciamento de Vulnerabilidades](next-gen-threat-and-vuln-mgt.md)

- [Vulnerabilidades em sua organização](tvm-weaknesses.md)
