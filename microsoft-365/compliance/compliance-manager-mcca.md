---
title: Analisador de Configuração de Conformidade da Microsoft para Gerenciador de Conformidade
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Entenda como usar o Analisador de Configuração de Conformidade da Microsoft para começar a funcionar rapidamente com o Microsoft Compliance Manager.
ms.openlocfilehash: 5d74d9980daf7f6ff7f013578cb11be83d18948e
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244631"
---
# <a name="microsoft-compliance-configuration-analyzer-for-compliance-manager-preview"></a>Analisador de Configuração de Conformidade da Microsoft para Gerenciador de Conformidade (visualização)

**Neste artigo:** Saiba como instalar e executar a ferramenta Analisador de Conformidade da Microsoft para começar rapidamente com o Microsoft Compliance Manger.

## <a name="microsoft-compliance-configuration-analyzer-mcca-preview-overview"></a>Visão geral do Microsoft Compliance Configuration Analyzer (MCCA) (visualização)

O Microsoft Compliance Configuration Analyzer (MCCA) é uma ferramenta de visualização que pode ajudá-lo a começar a usar o [Microsoft Compliance Manager.](compliance-manager.md) O MCCA é um utilitário baseado no PowerShell que buscará as configurações atuais da sua organização e as validará em relação Microsoft 365 práticas recomendadas. Essas práticas recomendadas se baseiam em um conjunto de controles que incluem os principais regulamentos e padrões de proteção de dados e governança de dados.

O MCCA pode ajudá-lo a ver rapidamente quais ações de melhoria no Gerenciador de Conformidade se aplicam ao seu ambiente Microsoft 365 atual. Cada ação identificada pelo MCCA dará recomendações para implementação, com links diretos para o Gerenciador de Conformidade e a solução aplicável para começar a tomar medidas corretivas.

Um recurso adicional para entender o MCCA é visitar as instruções [README em GitHub](https://github.com/OfficeDev/MCCA#overview). Esta página fornece informações detalhadas sobre pré-requisitos e fornece instruções de instalação completas. Você não precisa de uma conta GitHub para acessar esta página.

**Disponibilidade**: O MCCA está disponível para todas as organizações com licenças Office 365 e Microsoft 365 e clientes do Community (GCC) do Governo dos EUA, moderados, GCC Alto e do Departamento de Defesa (DoD).

## <a name="install-mcca-and-run-a-report"></a>Instalar o MCCA e executar um relatório

Você pode instalar a ferramenta MCCA usando Windows PowerShell. Depois de baixar e instalar a ferramenta, não é necessário repetir essas etapas para executar relatórios. Sempre que você abrir o MCCA, ele solicitará suas credenciais de logon e gerará um novo relatório atualizado.

#### <a name="step-1-install-windows-powershell"></a>Etapa 1: Instalar Windows PowerShell
Para começar, você precisará do módulo Exchange Online PowerShell (v2.0.3 ou superior) que está disponível na galeria do PowerShell. [Obter instruções de instalação](https://www.powershellgallery.com/packages/ExchangeOnlineManagement/2.0.3).

#### <a name="step-2-install-mcca"></a>Etapa 2: Instalar o MCCA

Para instalar o MCCA, comece usando o PowerShell no modo de administrador. Siga as etapas abaixo:

1. Selecione o Windows **botão Iniciar.**
2. Digite **PowerShell**, clique com o botão direito **do mouse Windows PowerShell**, em seguida, selecione Executar como **administrador**.
1. No prompt de comando, digite:

    ```powershell
    Install-Module -Name MCCAPreview
    ```

#### <a name="step-3-run-a-report"></a>Etapa 3: Executar um relatório

Depois de instalar o MCCA, você pode executar o MCCA e gerar um relatório. Para executar um relatório:

1. Abrir o PowerShell
2. Execute o cmdlet:

    ```powershell
    Get-MCCAReport
    ```

   Se você for um cliente GCC Alta, você precisará fornecer um parâmetro de entrada adicional para executar o relatório:

    ```powershell
    Get-MCCAReport -ExchangeEnvironmentName O365USGovGCCHigh
    ```

3. Depois que o MCCA é executado, ele faz uma verificação de versão inicial e solicita credenciais. No prompt De entrada do nome de usuário, entre com o endereço de email da sua conta Microsoft 365 ( exibir as funções[qualificadas para criar relatórios).](#role-based-reporting) Em seguida, insira sua senha no prompt de senha.

Seu relatório levará aproximadamente 2 a 5 minutos para gerar. Quando terminar, uma janela do navegador será aberta e exibirá seu relatório HTML. Sempre que você executar a ferramenta, ela solicitará suas credenciais e gerará um novo relatório. Este relatório é armazenado localmente no seguinte diretório:

C:\Users \<username> \AppData\Local\Microsoft\MCCA. 

Você pode acessar relatórios gerados anteriormente a partir deste diretório.

## <a name="understanding-your-report"></a>Noções básicas sobre seu relatório

Seu relatório reflete dados com base na data e hora em que foram gerados. A seção superior fornece detalhes sobre quando ele foi gerado, o nome da sua organização e a ID do locatário.

#### <a name="geolocation-based-reporting"></a>Relatórios baseados em geolocalização

A **seção Observação** mostra que seu relatório é personalizado com base na localização geográfica do locatário. Recomendações listado na ferramenta será específico para seu país ou região.

Sua seleção de localização geográfica é usada para avaliar os SITs (tipos de informações confidenciais) que são relevantes para essa localização geográfica e gerar um relatório que se alinha ao seu país ou região. Escolha localizações geográficas com base nos dados que você tem em seu locatário.

Para alterar as informações de localização do relatório, você precisa fornecer um parâmetro de entrada de localização geográfica (-Geo). Você pode escolher uma ou várias localizações geográficas aplicáveis ao seu locatário.

Siga estas instruções para executar um relatório com base em um local específico:

1. Abrir o PowerShell
2. Para especificar uma determinada região, você executará um cmdlet usando os números da tabela abaixo que correspondem ao país ou região. Insira vários números separando-os com uma vírgula. Por exemplo, o cmdlet abaixo executará um relatório personalizado para o Asia-Pacific e o Japão:

    ```powershell
    Get-MCCAReport -Geo @(1,7)
    ```
  | Input |  País ou Região | 
  | :------------- | :------------: |
  | 1 | Ásia – Pacífico |
  | 2 | Austrália |
  | 3 | Canadá |
  | 4  | Europa (excluindo a França) / Oriente Médio / África |
  | 5  | França |
  | 6  | Índia |
  | 7  | Japão |
  | 8  | Coreia |
  | 9  | América do Norte (excluindo o Canadá) |
  | 10  | América do Sul |
  | 11 | África do Sul |
  | 12  | Suíça |
  | 13 | Emirados Árabes Unidos |
  | 14  | Reino Unido |


 > [!NOTE]
> O relatório sempre incluirá tipos de informações confidenciais internacionais com suporte da MCCA, como código SWIFT, número de cartão de crédito, etc.

#### <a name="role-based-reporting"></a>Relatórios baseados em função

Seu relatório também será personalizado com base em sua função.

A tabela a seguir mostra quais funções têm acesso a quais seções do relatório. Outras funções em sua organização (não listadas na tabela abaixo) podem não ser capazes de executar a ferramenta, ou podem executar a ferramenta e ter acesso limitado às informações no relatório final.

![MCCA - funções](../media/compliance-manager-mcca-roles.png "Funções MCCA")

Exceções:
1. Os usuários não poderão gerar relatório para IP além da seção "Usar IRM para Exchange Online".
2. Os usuários poderão gerar relatório para IP além da seção "Usar IRM para Exchange Online".
3. Os usuários poderão gerar relatório para IP além da seção "Habilitar a Conformidade de Comunicação no O365".
4. Os usuários não poderão gerar relatório para IP além da seção "Habilitar a auditoria Office 365".
5. Os usuários poderão gerar relatório para IP além da seção "Habilitar a auditoria Office 365".

#### <a name="solutions-summary-section"></a>Seção Resumo de Soluções

A **seção Resumo de** Soluções do relatório fornece uma visão geral das ações de melhoria que sua organização pode tomar no Gerenciador de Conformidade para ajudar a melhorar a postura de conformidade.

![MCCA - resumo das soluções](../media/compliance-manager-mcca-solutions.png "Tela Resumo de Soluções MCCA")

O MCCA avalia suas configurações atuais em relação às ações de melhoria recomendadas no Gerenciador de Conformidade. Qualquer ação de melhoria identificada pela ferramenta MCCA como que precisa de atenção será listada nesta seção.

Ao lado de cada solução da Microsoft estão caixas codificadas por cores indicando o número de itens que correspondem às ações de melhoria no Gerenciador de Conformidade. As ações são divididas em três estados de status:

- **OK**: as ações que atendem às condições recomendadas e não precisam de atenção no momento
- **Aperfeiçoamento**: ações que precisam de atenção
- **Recomendação**: ações que não precisam de atenção, mas para as quais recomendamos práticas recomendadas
 
Selecione uma caixa para exibir melhorias e recomendações.

**Itens com o status De aperfeiçoamento**

Selecione o menu suspenso ao lado do **rótulo De aperfeiçoamento** à direita da ação de melhoria. Você verá um resumo rápido e detalhes sobre suas configurações atuais e as ações de melhoria recomendadas. O resumo inclui links diretos para o Gerenciador de Conformidade, a solução aplicável no Microsoft 365 de conformidade e documentação relevante.

Clicar no link Gerenciador de Conformidade o leva a uma exibição filtrada de todas as ações de melhoria dentro dessa solução que você ainda não implementou. A partir daí, você pode ver o número de pontos que você pode alcançar para aumentar sua pontuação de conformidade [e](compliance-score-calculation.md)as avaliações às que se aplicam e os regulamentos e certificações aplicáveis.

Para DLP, há um botão Script de **Correção** que fornece um script do PowerShell pré-gerado com base no que é recomendado. Você pode copiá-lo e colar diretamente no console do PowerShell. Ele criará uma política DLP no modo de teste

**Itens com status de recomendação**

Selecione o menu suspenso ao lado do rótulo **Recomendação** à direita da ação de melhoria. Você verá um resumo do ambiente de Microsoft 365 atual da sua organização relacionado à ação de melhoria, juntamente com as práticas recomendadas.

## <a name="resources"></a>Recursos

Para obter informações mais detalhadas sobre como instalar, configurar e usar o MCCA, consulte as instruções [README](https://github.com/OfficeDev/MCCA#overview) no GitHub (nenhuma conta GitHub necessária).

Para obter mais informações sobre Windows PowerShell, comece em [Como usar a documentação do PowerShell](/powershell/scripting/how-to-use-docs?view=powershell-7). Consulte também [Starting Windows PowerShell](/powershell/scripting/windows-powershell/starting-windows-powershell?view=powershell-7).
