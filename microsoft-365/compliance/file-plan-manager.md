---
title: Visão geral do gerenciador de planos de arquivo
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: af398293-c69d-465e-a249-d74561552d30
description: O gerenciador de planos de arquivo fornece recursos avançados de gerenciamento de políticas e rótulos de retenção, políticas de rótulos de retenção e oferece uma maneira integrada de percorrer a atividade de rótulos e de rótulo para conteúdo para todo o seu ciclo de vida de conteúdo, desde a criação à colaboração, declaração de registros, retenção e por fim, à disposição.
ms.openlocfilehash: 38bfb1e6a6cde931804e518660ddf6c2b45205b0
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37072745"
---
# <a name="overview-of-file-plan-manager"></a>Visão geral do gerenciador de planos de arquivo

O gerenciador de planos de arquivo fornece recursos avançados de gerenciamento de políticas e rótulos de retenção, políticas de rótulos de retenção e oferece uma maneira integrada de percorrer a atividade de rótulos e de rótulo para conteúdo para todo o seu ciclo de vida de conteúdo, desde a criação à colaboração, declaração de registros, retenção e por fim, à disposição.

![Página de plano de arquivo](media/file-plan-page.png)

## <a name="accessing-file-plan-manager"></a>Acessar o gerenciador de planos de arquivo

Há dois requisitos para acessar o gerenciador de planos de arquivo, que são:
- Uma assinatura do Office 365 Enterprise E5.
- O usuário ter recebido uma das seguintes funções do Centro de Conformidade e Segurança:
    - Gerenciador de Retenção
    - Gerenciador de Retenção somente exibição

## <a name="default-retention-labels-and-label-policy"></a>Rótulos de retenção e política de rótulos padrão

Se não houver rótulos de retenção na Central de Conformidade e Segurança, na primeira vez que você escolher **Planejamento de Arquivos** na navegação à esquerda, será criada uma política de rótulo chamada **Política Padrão de Publicação de Governança de Dados**. 

Esta política de rótulo contém três etiquetas de retenção:

- **Procedimento operacional**
- **Geral de negócios**
- **Contrato**

Estes rótulos de retenção estão configurados apenas para reter conteúdo, e não para excluir conteúdo. Esta política de rótulos será publicada para toda a organização e poderá ser desativada ou removida. 

Você pode determinar quem abriu o gerenciador de planejamento de arquivos e iniciou a primeira experiência de execução examinando as atividades **Política de retenção criada** e **Configuração de retenção criada para uma política de retenção** no log de auditoria.

> [!NOTE]
> Devido aos comentários dos clientes, removemos esse recurso que cria a política de rótulos de retenção e os rótulos de retenção padrão mencionados acima. Você só verá os rótulos de retenção e a política de rótulos de retenção caso tenha aberto o gerenciador de planos de arquivo antes de 11 de abril de 2019.

## <a name="navigating-your-file-plan"></a>Navegar pelo plano de arquivo

O gerente de plano de arquivo torna mais fácil ver todas as configurações dos seus rótulos e políticas de retenção no mesmo modo de exibição.

Observe que os rótulos de retenção criados fora do plano de arquivamento estarão disponíveis no plano de arquivamento e vice-versa.

Na guia **rótulos de plano de arquivo**, as seguintes informações e recursos adicionais estão disponíveis:

### <a name="label-settings-columns"></a>Colunas de configurações de rótulo

- **Com base em** identifica o tipo de gatilho que iniciará o período de retenção. Os valores válidos estão:
    - Evento
    - Data de criação
    - Data da última modificação
    - Data do rótulo
- **Registro** identifica se o item se tornará um registro declarado quando o rótulo for aplicado. Os valores válidos são:
    - Não
    - Sim
    - Sim (Regulatório)
- **Retenção** identifica o tipo de retenção. Os valores válidos são:
    - Manter
    - Manter e excluir
    - Excluir
- **Descarte** identifica o que acontecerá com o conteúdo no final do período de retenção. Os valores válidos são:
    - null
    - Nenhuma ação
    - Excluir automaticamente
    - Revisão obrigatória (também conhecida como revisão de descarte)

![Configurações de rótulos no plano de arquivo](media/file-plan-label-columns.png)

### <a name="retention-label-file-plan-descriptors-columns"></a>Colunas de descritores de plano de arquivo de rótulo de retenção

Agora você pode incluir mais informações na configuração das suas etiquetas de retenção. Inserir descritores de plano de arquivo em rótulos de retenção melhora o gerenciamento e a organização do seu plano de arquivo.

Para começar, o gerenciador de planos de arquivo fornece alguns valores prontos de origem para: Função/departamento, Categoria, Tipo de autoridade e Provisão/citação. Você pode adicionar novos valores descritores de planos de arquivo ao criar ou editar um rótulo de retenção.

Aqui está uma visão geral da etapa de descritores de plano de arquivo ao criar ou editar um rótulo de retenção.

![Descritores de plano de arquivo](media/file-plan-descriptors.png)

Aqui está um modo de exibição das colunas de descritores de plano de arquivo na guia Rótulos do gerenciador de planos de arquivo.

![file-plan-descriptors-on-labels-tab.png](media/file-plan-descriptors-on-labels-tab.png)

## <a name="export-all-existing-retention-labels-to-analyze-andor-perform-offline-reviews"></a>Exportar todos os rótulos de retenção existentes para analisar e/ou executar revisões offline

No gerenciador de planos de arquivo, você pode exportar os detalhes de todos os rótulos de retenção para um arquivo .csv, para ajudá-lo a facilitar as avaliações de conformidade periódicas com os participantes de governança de dados na sua organização.

Para exportar todos os rótulos de retenção, acesse **gerenciador de planos de arquivo** \> **ações de plano de arquivo** \> **exportar rótulos**.

![Opção para exportar o plano de arquivo](media/file-plan-export-labels-option.png)

Um arquivo *.csv que contém todos os rótulos de retenção existentes será aberto.

![Arquivo CSV mostrando todas as etiquetas de retenção](media/file-plan-csv-file.png)

## <a name="import-retention-labels-into-your-file-plan"></a>Importar rótulos de retenção para seu plano de arquivo

No gerenciador de planos de arquivo, você pode importar em massa novos rótulos de retenção, bem como modificar rótulos de retenção existentes.

Para importar novos rótulos de retenção e atualizar rótulos de retenção existentes, acesse **gerenciador de planos de arquivo** \> **ações de plano de arquivo** \> **importar rótulos**.

![Opção para importar plano de arquivo](media/file-plan-import-labels-option.png)

![Opção para baixar um modelo de plano de arquivo em branco](media/file-plan-blank-template-option.png)

Baixar um modelo em branco (ou começar com base em uma exportação do seu plano de arquivo atual).

![Modelo de plano de arquivo em branco aberto no Excel](media/file-plan-blank-template.png)

Preencher o modelo. Esta tabela fornece valores válidos.

|**Propriedade**|**Tipo**|**Valores válidos**|
|:-----|:-----|:-----|
|LabelName|String|Se o valor contiver espaços, coloque-o entre aspas (").|
|Comentário|String|Se o valor contiver espaços, coloque-o entre aspas ("). |
|Observações|String|Personalizado|
|IsRecordLabel|String|$true: O rótulo é um rótulo de registro.</br>$false: O rótulo não é um rótulo de registro. Esse é o valor padrão.|
|RetentionAction|String|Excluir</br>Manter</br>KeepAndDelete |
|RetentionDuration|String|Esta propriedade especifica o número de dias para reter o conteúdo. Os valores válidos são:</br>Um inteiro positivo.</br>O valor é ilimitado.|
|RetentionType|String|Esta propriedade especifica se a duração da retenção é calculada a partir da data de criação de conteúdo, da data rotulada (marcada) ou da data da última modificação. Os valores válidos são:</br>CreationAgeInDays</br>EventAgeInDays</br>ModificationAgeInDays</br>TaggedAgeInDays |
|ReviewerEmail|SmtpAddress[]|Esta propriedade especifica o endereço de email de um revisor para as ações de retenção Excluir e KeepAndDelete. Você pode especificar vários endereços de email separados por vírgulas.|
|ReferenceId|String|Personalizado|
|DepartmentName|String|Personalizado|
|Categoria|String|Personalizado|
|SubCategory|String|Personalizado|
|AuthorityType|String|Personalizado|
|CitationName|String|Personalizado|
|CitationUrl|String|Personalizado|
|CitationJurisdiction|String|Personalizado|
|Regulatório|String|Personalizado|
|EventType|String|Esta propriedade especifica a regra de retenção associada ao rótulo. É possível usar qualquer valor que identifique a regra com exclusividade. Por exemplo:</br>Nome</br>DN (nome diferenciado)</br>GUID </br>Você pode usar o cmdlet [Get-RetentionComplianceRule](https://docs.microsoft.com/pt-BR/powershell/module/exchange/policy-and-compliance-retention/get-retentioncompliancerule?view=exchange-ps) para exibir as regras de retenção disponíveis.|

![Modelo de plano de arquivo com as informações preenchidas](media/file-plan-filled-out-template.png)

Carregue o modelo preenchido, e o gerenciador de plano de arquivo validará as entradas e exibirá as estatísticas de importação.

![Estatísticas de importação de plano de arquivo](media/file-plan-import-statistics.png)

Caso haja um erro de validação, a importação do plano de arquivo continuará a validar todas as entradas no arquivo de importação e exibirá todos os erros ao referenciar números de linha no arquivo de importação, copiar os resultados de erros exibidos para que você possa retornar facilmente ao arquivo de importação e corrigir os erros. 

Quando a importação for concluída, volte para o gerenciador de planos de arquivo para associar os novos rótulos de retenção a políticas de rótulos de retenção novas ou existentes.

![Opção para publicar rótulos](media/file-plan-publish-labels-option.png)

