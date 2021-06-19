---
title: Exportar métodos e propriedades de avaliação por dispositivo
description: Fornece informações sobre as APIs que puxam dados de "gerenciamento de ameaças e vulnerabilidades". Há diferentes chamadas de API para obter diferentes tipos de dados. Em geral, cada chamada de API contém os dados necessários para dispositivos em sua organização.
keywords: api, apis, avaliação de exportação, avaliação por dispositivo, avaliação por máquina, relatório de avaliação de vulnerabilidade, avaliação de vulnerabilidade de dispositivo, relatório de vulnerabilidade de dispositivo, avaliação de configuração segura, relatório de configuração segura, avaliação de vulnerabilidades de software, relatório de vulnerabilidade de software, relatório de vulnerabilidade por máquina,
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
ms.openlocfilehash: 3e5a91a33a4207daa30f1054f03655c846d297ec
ms.sourcegitcommit: bc64d9f619259bd0a94e43a9010aae5cffb4d6c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2021
ms.locfileid: "53022433"
---
# <a name="export-assessment-methods-and-properties-per-device"></a>Exportar métodos e propriedades de avaliação por dispositivo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="api-description"></a>Descrição da API

Fornece métodos e detalhes de propriedade sobre as APIs que puxam dados de gerenciamento de ameaças e vulnerabilidades por dispositivo. Há diferentes chamadas de API para obter diferentes tipos de dados. Em geral, cada chamada de API contém os dados necessários para dispositivos em sua organização.

> [!Note]
>
> A menos que indicado de outra forma, todos os métodos de avaliação de exportação listados são **_exportação completa_** e **_por dispositivo_** (também chamado de **_por dispositivo)._**

Você pode usar as APIs de avaliação de exportação para recuperar (exportar) diferentes tipos de informações:

- [1. Exportar a avaliação de configurações seguras](#1-export-secure-configurations-assessment)

- [2. Exportar avaliação de inventário de software](#2-export-software-inventory-assessment)

- [3. Avaliação de vulnerabilidades de software de exportação](#3-export-software-vulnerabilities-assessment)

As APIs que correspondem aos tipos de informações de exportação são descritas nas seções 1, 2 e 3.

Para cada método, há chamadas de API diferentes para obter diferentes tipos de dados. Como a quantidade de dados pode ser grande, há duas maneiras de recuperá-las:

- **Resposta JSON**  A API puxa todos os dados da sua organização como respostas JSON. Esse método é melhor para _organizações pequenas com menos de 100 K dispositivos_. A resposta é paginada, portanto, você pode usar o campo odata.nextLink da resposta para \@ buscar os próximos resultados.

- **via arquivos** Essa solução de API permite a retirada de quantidades maiores de dados de forma mais rápida e confiável. Portanto, é recomendado para grandes organizações, com mais de 100 K dispositivos. Essa API puxa todos os dados da sua organização como arquivos de download. A resposta contém URLs para baixar todos os dados do Armazenamento do Azure. Essa API permite baixar todos os dados do Armazenamento do Azure da seguinte forma:

  - Chame a API para obter uma lista de URLs de download com todos os dados da sua organização.

  - Baixe todos os arquivos usando as URLs de download e processe os dados conforme quiser.

Os dados coletados (usando a resposta _JSON_ ou por meio de arquivos _)_ são o instantâneo atual do estado atual e não contêm dados históricos. Para coletar dados históricos, os clientes devem salvar os dados em seus próprios armazenamentos de dados.

## <a name="1-export-secure-configurations-assessment"></a>1. Exportar a avaliação de configurações seguras

Retorna todas as configurações e seu status, por dispositivo.

### <a name="11-methods"></a>Métodos 1.1

Method | Tipo de dados | Descrição
:---|:---|:---
Exportar avaliação de configuração segura **(resposta JSON)** | Configuração segura por conjunto de dispositivos. Consulte: [Propriedades 1.2 (resposta JSON)](#12-properties-json-response) | Retorna uma tabela com uma entrada para cada combinação exclusiva de DeviceId, ConfigurationId. A API puxa todos os dados da sua organização como respostas JSON. Esse método é melhor para organizações pequenas com menos de 100 K dispositivos. A resposta é paginada, portanto, você pode usar o campo @odata.nextLink da resposta para buscar os próximos resultados.
Exportar a avaliação de configuração **segura (por meio de arquivos)** | Configuração segura por conjunto de dispositivos. Consulte: [1.3 Propriedades (por meio de arquivos)](#13-properties-via-files) | Retorna uma tabela com uma entrada para cada combinação exclusiva de DeviceId, ConfigurationId. Essa solução de API permite a retirada de quantidades maiores de dados de forma mais rápida e confiável. Portanto, é recomendado para grandes organizações, com mais de 100 K dispositivos. Essa API puxa todos os dados da sua organização como arquivos de download. A resposta contém URLs para baixar todos os dados do Armazenamento do Azure. Essa API permite baixar todos os dados do Armazenamento do Azure da seguinte forma: 1.  Chame a API para obter uma lista de URLs de download com todos os dados da sua organização. 2.  Baixe todos os arquivos usando as URLs de download e processe os dados conforme quiser.

### <a name="12-properties-json-response"></a>1.2 Propriedades (resposta JSON)

Propriedade (ID) | Tipo de dados | Descrição
:---|:---|:---
ConfigurationCategory | string | Categoria ou agrupamento ao qual a configuração pertence: aplicativo, sistema operacional, rede, contas, controles de segurança
ConfigurationId | string | Identificador exclusivo para uma configuração específica
ConfigurationImpact | string | Impacto avaliado da configuração na classificação total (1-10)
ConfigurationName | string | Exibir o nome da configuração
ConfigurationSubcategory | string | Subcategoria ou subgrupo ao qual a configuração pertence. Em muitos casos, isso descreve capacidades ou recursos específicos.
DeviceId | cadeia de caracteres | Identificador exclusivo do dispositivo no serviço.
DeviceName | cadeia de caracteres | Nome de domínio totalmente qualificado (FQDN) do dispositivo.
IsApplicable | bool | Indica se a configuração ou a política é aplicável
IsCompliant | bool | Indica se a configuração ou política está configurada corretamente
IsExpectedUserImpact | bool | Indica se haverá impacto do usuário se a configuração será aplicada
OSPlatform | cadeia de caracteres | Plataforma do sistema operacional em execução no dispositivo. Isso indica os sistemas operacionais específicos, incluindo variações na mesma família, como o Windows 10 e o Windows 7. Confira sistemas operacionais e plataformas com suporte para TVM para obter detalhes.
RbacGroupName | cadeia de caracteres | O grupo controle de acesso baseado em função (RBAC). Se esse dispositivo não for atribuído a nenhum grupo RBAC, o valor será "Não atribuído". Se a organização não tiver nenhum grupo RBAC, o valor será "None".
RecommendationReference | cadeia de caracteres | Uma referência à ID de recomendação relacionada a este software.
Carimbo de data/hora | cadeia de caracteres | Última vez que a configuração foi vista no dispositivo

### <a name="13-properties-via-files"></a>1.3 Propriedades (por meio de arquivos)

Propriedade (ID) | Tipo de dados | Descrição
:---|:---|:---
Exportar arquivos | cadeia de \[ caracteres de matriz\] | Uma lista de URLs de download para arquivos que segurando o instantâneo atual da organização.
GeneratedTime | cadeia de caracteres | A hora em que a exportação foi gerada.

## <a name="2-export-software-inventory-assessment"></a>2. Exportar avaliação de inventário de software

Retorna todo o software instalado e seus detalhes em cada dispositivo.

### <a name="21-methods"></a>Métodos 2.1

Method | Tipo de dados | Descrição
:---|:---|:---
Avaliação de inventário de software **de exportação (resposta JSON)** | Inventário de software por conjunto de dispositivos. Consulte: [Propriedades 2.2 (resposta JSON)](#22-properties-json-response) | Retorna uma tabela com uma entrada para cada combinação exclusiva de DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion. A API puxa todos os dados da sua organização como respostas JSON. Esse método é melhor para organizações pequenas com menos de 100 K dispositivos. A resposta é paginada, portanto, você pode usar o campo @odata.nextLink da resposta para buscar os próximos resultados.
Exportar avaliação de inventário de software **(por meio de arquivos)** | Inventário de software por arquivos de dispositivo. Consulte: [2.3 Propriedades (por meio de arquivos)](#23-properties-via-files) | Retorna uma tabela com uma entrada para cada combinação exclusiva de DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion. Essa solução de API permite a retirada de quantidades maiores de dados de forma mais rápida e confiável. Portanto, é recomendado para grandes organizações, com mais de 100 K dispositivos. Essa API puxa todos os dados da sua organização como arquivos de download. A resposta contém URLs para baixar todos os dados do Armazenamento do Azure. Essa API permite baixar todos os dados do Armazenamento do Azure da seguinte forma: 1.  Chame a API para obter uma lista de URLs de download com todos os dados da sua organização. 2.  Baixe todos os arquivos usando as URLs de download e processe os dados conforme quiser.

### <a name="22-properties-json-response"></a>Propriedades 2.2 (resposta JSON)

Propriedade (ID) | Tipo de dados | Descrição
:---|:---|:---
DeviceId | cadeia de caracteres | Identificador exclusivo do dispositivo no serviço.
DeviceName | cadeia de caracteres | Nome de domínio totalmente qualificado (FQDN) do dispositivo.
DiskPaths | Array[string]  | Evidência em disco de que o produto está instalado no dispositivo.
EndOfSupportDate | cadeia de caracteres | A data em que o suporte para este software tem ou terminará.
EndOfSupportStatus | cadeia de caracteres | Status do fim do suporte. Pode conter esses valores possíveis: None, Versão EOS, Versão EOS futura, Software EOS, Software EOS futuro.
Id | cadeia de caracteres | Identificador exclusivo do registro.
NumberOfWeaknesses | int|Número de pontos fracos neste software neste dispositivo
OSPlatform | cadeia de caracteres | Plataforma do sistema operacional em execução no dispositivo. Isso indica os sistemas operacionais específicos, incluindo variações na mesma família, como o Windows 10 e o Windows 7. Confira sistemas operacionais e plataformas com suporte para TVM para obter detalhes.
RbacGroupName | cadeia de caracteres | O grupo controle de acesso baseado em função (RBAC). Se esse dispositivo não for atribuído a nenhum grupo RBAC, o valor será "Não atribuído". Se a organização não tiver nenhum grupo RBAC, o valor será "None".
RegistryPaths | Array[string] | Evidência do Registro de que o produto está instalado no dispositivo.
SoftwareFirstSeenTimestamp | cadeia de caracteres | A primeira vez que esse software foi visto no dispositivo.
SoftwareName | cadeia de caracteres | Nome do produto de software.
SoftwareVendor | cadeia de caracteres | Nome do fornecedor de software.
SoftwareVersion | cadeia de caracteres | Número da versão do produto de software.

### <a name="23-properties-via-files"></a>2.3 Propriedades (por meio de arquivos)

Propriedade (ID) | Tipo de dados | Descrição
:---|:---|:---
Exportar arquivos | cadeia de \[ caracteres de matriz\] | Uma lista de URLs de download para arquivos que segurando o instantâneo atual da organização.
GeneratedTime | cadeia de caracteres | A hora em que a exportação foi gerada.

## <a name="3-export-software-vulnerabilities-assessment"></a>3. Avaliação de vulnerabilidades de software de exportação

Retorna todas as vulnerabilidades conhecidas em um dispositivo e seus detalhes, para todos os dispositivos.

### <a name="31-methods"></a>Métodos 3.1

Method | Tipo de dados | Descrição
:---|:---|:---
Avaliação de vulnerabilidades de software **de exportação (resposta JSON)** | Coleção Investigation See: [3.2 Properties (resposta JSON)](#32-properties-json-response) | Retorna uma tabela com uma entrada para cada combinação exclusiva de DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId. A API puxa todos os dados da sua organização como respostas JSON. Esse método é melhor para organizações pequenas com menos de 100 K dispositivos. A resposta é paginada, portanto, você pode usar o campo @odata.nextLink da resposta para buscar os próximos resultados.
Avaliação de vulnerabilidades de software **de exportação (por meio de arquivos)** | Entidade de investigação Consulte: [Propriedades 3.3 (por meio de arquivos)](#33-properties-via-files) | Retorna uma tabela com uma entrada para cada combinação exclusiva de DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId. Essa solução de API permite a retirada de quantidades maiores de dados de forma mais rápida e confiável. Portanto, é recomendado para grandes organizações, com mais de 100 K dispositivos. Essa API puxa todos os dados da sua organização como arquivos de download. A resposta contém URLs para baixar todos os dados do Armazenamento do Azure. Essa API permite baixar todos os dados do Armazenamento do Azure da seguinte forma: 1.  Chame a API para obter uma lista de URLs de download com todos os dados da sua organização. 2.  Baixe todos os arquivos usando as URLs de download e processe os dados conforme quiser.
**Avaliação de** vulnerabilidades de software de exportação delta **(resposta JSON)** | Coleção Investigation Consulte: [3.4 Properties Delta export (resposta JSON)](#34-properties-delta-export-json-response) | Retorna uma tabela com uma entrada para cada combinação exclusiva de: DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId e EventTimestamp. <br><br> A API coleta dados em sua organização como respostas JSON. A resposta é paginada, portanto, você pode usar o campo @odata.nextLink da resposta para buscar os próximos resultados. Ao contrário da avaliação completa de vulnerabilidades de software (resposta JSON) - que é usada para obter um instantâneo inteiro da avaliação de vulnerabilidades de software da sua organização por dispositivo - a chamada da API OData de exportação delta é usada para buscar apenas as alterações que aconteceram entre uma data selecionada e a data atual (a chamada da API "delta"). Em vez de obter uma exportação completa com uma grande quantidade de dados sempre, você só obterá informações específicas sobre vulnerabilidades novas, fixas e atualizadas. A chamada de API OData de exportação delta também pode ser usada para calcular KPIs diferentes, como "quantas vulnerabilidades foram corrigidas?" ou "quantas novas vulnerabilidades foram adicionadas à minha organização?"  <br><br> Como a chamada da API OData de exportação delta para vulnerabilidades de software retorna dados apenas para um intervalo de datas direcionado, ela não é considerada uma _exportação completa._

### <a name="32-properties-json-response"></a>Propriedades 3.2 (resposta JSON)

Propriedade (ID) | Tipo de dados | Descrição
:---|:---|:---
CveId | cadeia de caracteres | Identificador exclusivo atribuído à vulnerabilidade de segurança no sistema CVE (Common Vulnerabilities and Exposures).
CvssScore | cadeia de caracteres | A pontuação CVSS do CVE.
DeviceId | cadeia de caracteres | Identificador exclusivo do dispositivo no serviço.
DeviceName | cadeia de caracteres | Nome de domínio totalmente qualificado (FQDN) do dispositivo.
DiskPaths | Cadeia de \[ caracteres de matriz\] | Evidência em disco de que o produto está instalado no dispositivo.
ExploitabilityLevel | cadeia de caracteres | O nível de exploração dessa vulnerabilidade (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)
FirstSeenTimestamp | cadeia de caracteres | Primeira vez que o CVE deste produto foi visto no dispositivo.
Id | cadeia de caracteres | Identificador exclusivo do registro.
LastSeenTimestamp | cadeia de caracteres | A última vez que o CVE foi visto no dispositivo.
OSPlatform | cadeia de caracteres | Plataforma do sistema operacional em execução no dispositivo. Isso indica os sistemas operacionais específicos, incluindo variações na mesma família, como o Windows 10 e o Windows 7. Confira sistemas operacionais e plataformas com suporte para TVM para obter detalhes.
RbacGroupName | cadeia de caracteres | O grupo controle de acesso baseado em função (RBAC). Se esse dispositivo não for atribuído a nenhum grupo RBAC, o valor será "Não atribuído". Se a organização não tiver nenhum grupo RBAC, o valor será "None".
RecommendationReference | cadeia de caracteres | Uma referência à ID de recomendação relacionada a este software.
RecommendedSecurityUpdate | cadeia de caracteres | Nome ou descrição da atualização de segurança fornecida pelo fornecedor de software para resolver a vulnerabilidade.
RecommendedSecurityUpdateId | cadeia de caracteres | Identificador das atualizações de segurança ou identificador aplicáveis para os artigos de base de conhecimento ou orientação correspondentes (KB)
Cadeia de caracteres da Matriz de Caminhos do \[ Registro\] | Evidência do Registro de que o produto está instalado no dispositivo.
SoftwareName | cadeia de caracteres | Nome do produto de software.
SoftwareVendor | cadeia de caracteres | Nome do fornecedor de software.
SoftwareVersion | cadeia de caracteres | Número da versão do produto de software.
VulnerabilitySeverityLevel | cadeia de caracteres | Nível de severidade atribuído à vulnerabilidade de segurança com base na pontuação cvss e fatores dinâmicos influenciados pelo cenário de ameaças.

### <a name="33-properties-via-files"></a>Propriedades 3.3 (por meio de arquivos)

Propriedade (ID) | Tipo de dados | Descrição
:---|:---|:---
Exportar arquivos | cadeia de \[ caracteres de matriz\]  | Uma lista de URLs de download para arquivos que segurando o instantâneo atual da organização.
GeneratedTime | cadeia de caracteres | A hora em que a exportação foi gerada.

### <a name="34-properties-delta-export-json-response"></a>Propriedades 3.4 (resposta delta de exportação JSON)

Propriedade (ID) | Tipo de dados | Descrição
:---|:---|:---
CveId | cadeia de caracteres | Identificador exclusivo atribuído à vulnerabilidade de segurança no sistema CVE (Common Vulnerabilities and Exposures).
CvssScore | cadeia de caracteres | A pontuação CVSS do CVE.
DeviceId | cadeia de caracteres | Identificador exclusivo do dispositivo no serviço.
DeviceName | cadeia de caracteres | Nome de domínio totalmente qualificado (FQDN) do dispositivo.
DiskPaths | Array[string] | Evidência em disco de que o produto está instalado no dispositivo.
EventTimestamp | String | A hora em que esse evento delta foi encontrado.
ExploitabilityLevel | cadeia de caracteres | O nível de exploração dessa vulnerabilidade (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)
FirstSeenTimestamp | cadeia de caracteres | Primeira vez que o CVE deste produto foi visto no dispositivo.
Id | cadeia de caracteres | Identificador exclusivo do registro.  
LastSeenTimestamp | cadeia de caracteres | A última vez que o CVE foi visto no dispositivo.
OSPlatform | cadeia de caracteres | Plataforma do sistema operacional em execução no dispositivo. Isso indica os sistemas operacionais específicos, incluindo variações na mesma família, como o Windows 10 e o Windows 7. Confira sistemas operacionais e plataformas com suporte para TVM para obter detalhes.
RbacGroupName | cadeia de caracteres | O grupo controle de acesso baseado em função (RBAC). Se esse dispositivo não for atribuído a nenhum grupo RBAC, o valor será "Não atribuído". Se a organização não tiver nenhum grupo RBAC, o valor será "None".
RecommendationReference | cadeia de caracteres | Uma referência à ID de recomendação relacionada a este software.
RecommendedSecurityUpdate  | cadeia de caracteres | Nome ou descrição da atualização de segurança fornecida pelo fornecedor de software para resolver a vulnerabilidade.
RecommendedSecurityUpdateId  | cadeia de caracteres | Identificador das atualizações de segurança ou identificador aplicáveis para os artigos de base de conhecimento ou orientação correspondentes (KB)
RegistryPaths  | Array[string] | Evidência do Registro de que o produto está instalado no dispositivo.
SoftwareName | cadeia de caracteres | Nome do produto de software.
SoftwareVendor | cadeia de caracteres | Nome do fornecedor de software.
SoftwareVersion | cadeia de caracteres | Número da versão do produto de software.
Status | String | **Novo**   (para uma nova vulnerabilidade introduzida em um dispositivo).  **Corrigido**   (para uma vulnerabilidade que não existe mais no dispositivo, o que significa que foi remediado). **Atualizado**   (para uma vulnerabilidade em um dispositivo que foi alterado. As alterações possíveis são: pontuação CVSS, nível de exploração, nível de gravidade, DiskPaths, RegistryPaths, RecommendedSecurityUpdate).
VulnerabilitySeverityLevel | cadeia de caracteres | Nível de severidade atribuído à vulnerabilidade de segurança com base na pontuação cvss e fatores dinâmicos influenciados pelo cenário de ameaças.

## <a name="see-also"></a>Confira também

- [Exportar avaliação de configuração segura por dispositivo](get-assessment-secure-config.md)

- [Exportar avaliação de inventário de software por dispositivo](get-assessment-software-inventory.md)

- [Exportar a avaliação de vulnerabilidades de software por dispositivo](get-assessment-software-vulnerabilities.md)

Outros relacionados

- [Ameaças baseadas em risco & Gerenciamento de Vulnerabilidades](next-gen-threat-and-vuln-mgt.md)

- [Vulnerabilidades em sua organização](tvm-weaknesses.md)
