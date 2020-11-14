---
title: Analisador de configuração de conformidade da Microsoft para o gerente de conformidade
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
description: Saiba como usar o analisador de configuração de conformidade da Microsoft para começar a trabalhar rapidamente com o Gerenciador de conformidade da Microsoft.
ms.openlocfilehash: 1f7d987262a7d390cb9efe2162ae9be9f56c8757
ms.sourcegitcommit: d333d82fd5e4f3265e8b9372094e85875bee6fe5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49071990"
---
# <a name="microsoft-compliance-configuration-analyzer-for-compliance-manager"></a>Analisador de configuração de conformidade da Microsoft para o gerente de conformidade

**Neste artigo:** Saiba como instalar e executar a ferramenta Microsoft Compliance configure Analyzer para começar rapidamente com o Microsoft Compliance Manager.

## <a name="microsoft-compliance-configuration-analyzer-mcca-overview"></a>Visão geral do MCCA (Microsoft Compliance Configuration Analyzer)

O analisador de configuração de conformidade da Microsoft (MCCA) é uma ferramenta que pode ajudá-lo a começar a usar [o gerente de conformidade da Microsoft](compliance-manager.md). O MCCA é um utilitário baseado no PowerShell que buscará as configurações atuais da sua organização e as validará em relação às práticas recomendadas da Microsoft 365. Essas práticas recomendadas baseiam-se em um conjunto de controles que incluem normas e padrões fundamentais para proteção de dados e governança de dados.

O MCCA pode ajudá-lo a ver rapidamente quais ações de melhoria no Gerenciador de conformidade se aplicam ao seu ambiente atual do Microsoft 365. Cada ação identificada por MCCA fornecerá recomendações para implementação, com links diretos para o Gerenciador de conformidade e a solução aplicável para começar a realizar ações corretivas.

Um recurso adicional para entender o MCCA é visitar as [instruções Leiame no GitHub](https://github.com/OfficeDev/MCCA#overview). Esta página fornece informações detalhadas sobre os pré-requisitos e fornece instruções de instalação completas. Você não precisa de uma conta do GitHub para acessar essa página.

## <a name="install-mcca-and-run-a-report"></a>Instalar o MCCA e executar um relatório

Você pode instalar a ferramenta MCCA usando o Windows PowerShell. Depois de baixar e instalar a ferramenta, não será necessário repetir essas etapas para executar relatórios. Cada vez que você abrir o MCCA, ele solicitará suas credenciais de login e gerará um relatório novo e atualizado.

#### <a name="step-1-install-windows-powershell"></a>Etapa 1: instalar o Windows PowerShell
Para começar, você precisará do módulo do PowerShell do Exchange Online (v 2.0.3 ou superior) que está disponível na galeria do PowerShell. [Obtenha instruções de instalação](https://www.powershellgallery.com/packages/ExchangeOnlineManagement/2.0.3).

#### <a name="step-2-install-mcca"></a>Etapa 2: instalar o MCCA

Para instalar o MCCA, comece usando o PowerShell no modo de administrador. Siga as etapas abaixo:

1. Selecione o botão **Iniciar** do Windows.
2. Digite **PowerShell** , clique com o botão direito do mouse no **Windows PowerShell** e selecione **Executar como administrador**.
1. No prompt de comando, digite:

    ```powershell
    Install-Module -Name MCCAPreview
    ```

#### <a name="step-3-run-a-report"></a>Etapa 3: executar um relatório

Após instalar o MCCA, você pode executar o MCCA e gerar um relatório. Para executar um relatório:

1. Abrir o PowerShell
2. Execute o cmdlet:

    ```powershell
    Get-MCCAReport
    ```
3. Após o MCCA ser executado, uma versão inicial verifica e solicita credenciais. No prompt de entrada de nome de usuário, entre com seu endereço de email da conta do Microsoft 365 ([exiba as funções qualificadas para criar relatórios](#role-based-reporting)). Em seguida, insira sua senha no prompt de senha.

O relatório levará aproximadamente 2-5 minutos para ser gerado. Quando ela é concluída, uma janela do navegador abre e exibe o relatório HTML. Toda vez que você executar a ferramenta, ela solicitará suas credenciais e gerará um novo relatório. Esse relatório é armazenado localmente no seguinte diretório:

C:\Users \<username> \AppData\Local\Microsoft\MCCA. 

Você pode acessar os relatórios gerados anteriormente desse diretório.

## <a name="understanding-your-report"></a>Noções básicas sobre o relatório

O relatório reflete os dados com base na data e hora em que foi gerado. A seção superior fornece detalhes sobre quando ele foi gerado, o nome da sua organização e a ID do locatário.

#### <a name="geolocation-based-reporting"></a>Relatórios baseados em geolocalização

A seção **Observação** mostra que o relatório é personalizado com base na localização geográfica do seu locatário. As recomendações listadas na ferramenta serão específicas do seu país ou região.

A seleção de localização geográfica é usada para avaliar os tipos de informações confidenciais (no) que são relevantes para a localização geográfica e gerar um relatório que se alinhe ao seu país ou região. Escolha geolocations com base nos dados que você tem em seu locatário.

Para alterar as informações de local de seu relatório, você precisa fornecer um parâmetro de entrada de localização geográfica (-GEO). Você pode escolher uma ou várias geolocalidades aplicáveis ao seu locatário.

Siga estas instruções para executar um relatório baseado em um local específico:

1. Abrir o PowerShell
2. Para especificar uma determinada região, você executará um cmdlet usando os números da tabela abaixo que correspondem ao país ou à região. Insira vários números separando-os com uma vírgula. Por exemplo, o cmdlet abaixo executará um relatório personalizado para o Asia-Pacific e o Japão:

    ```powershell
    Get-MCCAReport -Geo @(1,7)
    ```
  | Input |  País ou Região | 
  | :------------- | :------------: |
  | 1 | Ásia – Pacífico |
  | duas | Austrália |
  | 3D | Canadá |
  | 4  | Europa (exceto França)/Oriente Médio/África |
  | 5  | França |
  | 6  | Índia |
  | 7  | Japão |
  | 8  | Coreia |
  | 9  | América do Norte (exceto Canadá) |
  | 10  | América do Sul |
  | 11  | África do Sul |
  | 12  | Suíça |
  | 13  | Emirados Árabes Unidos |
  | 14  | Reino Unido |


 > [!NOTE]
> O relatório sempre incluirá tipos de informações confidenciais internacionais suportados, como código SWIFT, número de cartão de crédito, etc.

#### <a name="role-based-reporting"></a>Relatórios baseados em função

O relatório também será personalizado com base em sua função.

A tabela abaixo mostra quais funções têm acesso a quais seções do relatório. Outras funções dentro da sua organização (não listadas na tabela abaixo) podem não ser capazes de executar a ferramenta ou podem executar a ferramenta e ter acesso limitado às informações no relatório final.

![MCCA-funções](../media/compliance-manager-mcca-roles.png "Funções MCCA")

Exceções
1. O usuário não conseguirá gerar relatórios de IP separados da seção "usar o IRM para Exchange Online".
2. O usuário poderá gerar relatórios de IP separados da seção "usar o IRM para Exchange Online".
3. O usuário poderá gerar o relatório de IP separado da seção "Habilitar conformidade de comunicação no O365".
4. O usuário não conseguirá gerar relatórios de IP separados da seção "habilitar auditoria no Office 365".
5. O usuário poderá gerar o relatório para o IP separado da seção "habilitar auditoria no Office 365".

#### <a name="solutions-summary-section"></a>Seção Resumo de soluções

A seção **Resumo das soluções** do relatório fornece uma visão geral das ações de aperfeiçoamento que sua organização pode executar no gerente de conformidade para ajudar a melhorar a postura de conformidade.

![Resumo do MCCA-Solutions](../media/compliance-manager-mcca-solutions.png "Tela de Resumo de soluções do MCCA")

O MCCA avalia suas configurações atuais em relação às ações de melhoria recomendadas no Gerenciador de conformidade. Qualquer ação de melhoria identificada pela ferramenta MCCA como precisa de atenção será listada nesta seção.

Ao lado de cada solução da Microsoft são caixas com códigos de cores que indicam o número de itens que correspondem às ações de melhoria no Gerenciador de conformidade. As ações são divididas em três Estados de status:

- **OK** : as ações que atendem às condições recomendadas e não precisam de atenção no momento
- **Melhoria** : ações que precisam de atenção
- **Recomendação** : ações que não precisam de atenção, mas para as quais recomendamos práticas recomendadas
 
Selecione uma caixa para exibir melhorias e recomendações.

**Itens com o status de melhoria**

Selecione o menu suspenso ao lado do rótulo de **melhoria** à direita da ação de aprimoramento. Você verá um resumo rápido e detalhes sobre as configurações atuais e as ações de melhoria recomendadas. O resumo inclui links diretos no gerente de conformidade, a solução aplicável no centro de conformidade da Microsoft 365 e a documentação relevante.

Clicar no link do Gerenciador de conformidade leva você a uma exibição filtrada de todas as ações de aprimoramento dentro dessa solução que você ainda não tenha implementado. A partir daí, você pode ver o número de pontos que você pode alcançar para aumentar sua [Pontuação de conformidade](compliance-score-calculation.md)e as avaliações às quais eles se aplicam e as regulamentações e certificações aplicáveis.

Para DLP, há um botão de **script de correção** que fornece um script do PowerShell gerado previamente com base no que é recomendado. Você pode copiá-lo e colá-lo diretamente no console do PowerShell. Ele criará uma política de DLP no modo de teste

**Itens com status de recomendação**

Selecione o menu suspenso ao lado do rótulo de **recomendação** à direita da ação de aprimoramento. Você verá um resumo do ambiente atual do Microsoft 365 da sua organização relacionado à ação de melhoria, juntamente com as práticas recomendadas.

## <a name="resources"></a>Recursos

Para obter informações mais detalhadas sobre como instalar, configurar e usar o MCCA, consulte as [instruções de Leiame no GitHub](https://github.com/OfficeDev/MCCA#overview) (nenhuma conta do GitHub necessária).

Para obter mais informações sobre o Windows PowerShell, comece a [usar a documentação do PowerShell](https://docs.microsoft.com/powershell/scripting/how-to-use-docs?view=powershell-7). Consulte também [iniciando o Windows PowerShell](https://docs.microsoft.com/powershell/scripting/windows-powershell/starting-windows-powershell?view=powershell-7).
