---
title: Analisador de Configuração de Conformidade da Microsoft para o Gerenciador de Conformidade
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
description: Entenda como usar o Analisador de Configuração de Conformidade da Microsoft para começar a trabalhar rapidamente com o Gerenciador de Conformidade da Microsoft.
ms.openlocfilehash: 86c4b04deb8313f3013a6d9ad349c0f4112db773
ms.sourcegitcommit: 719b89baca1bae14455acf2e517ec18fc473636c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2021
ms.locfileid: "50122391"
---
# <a name="microsoft-compliance-configuration-analyzer-for-compliance-manager-preview"></a>Analisador de Configuração de Conformidade da Microsoft para o Gerenciador de Conformidade (visualização)

**Neste artigo:** Saiba como instalar e executar a ferramenta Analisador de Configuração de Conformidade da Microsoft para começar rapidamente com o Microsoft Compliance Manger.

## <a name="microsoft-compliance-configuration-analyzer-mcca-preview-overview"></a>Visão geral do Microsoft Compliance Configuration Analyzer (MCCA) (visualização)

O Microsoft Compliance Configuration Analyzer (MCCA) é uma ferramenta de visualização que pode ajudá-lo a começar a usar o Gerenciador de [Conformidade da Microsoft.](compliance-manager.md) A MCCA é um utilitário baseado no PowerShell que buscará as configurações atuais da sua organização e as validará em relação às práticas recomendadas do Microsoft 365. Essas práticas recomendadas são baseadas em um conjunto de controles que incluem os principais regulamentos e padrões de proteção de dados e governança de dados.

A MCCA pode ajudá-lo a ver rapidamente quais ações de melhoria no Manger de Conformidade se aplicam ao seu ambiente atual do Microsoft 365. Cada ação identificada pela MCCA lhe dará recomendações para implementação, com links diretos para o Gerenciador de Conformidade e a solução aplicável para começar a tomar medidas corretivas.

Um recurso adicional para entender a MCCA é visitar as instruções [LEIAME no GitHub.](https://github.com/OfficeDev/MCCA#overview) Esta página fornece informações detalhadas sobre pré-requisitos e fornece instruções completas de instalação. Você não precisa de uma conta do GitHub para acessar esta página.

**Disponibilidade**: A MCCA está disponível para todas as organizações com licenças do Office 365 e microsoft 365 e clientes moderados da US Government Community (GCC), com planos em andamento para expandir o serviço para clientes GCC High.

## <a name="install-mcca-and-run-a-report"></a>Instalar o MCCA e executar um relatório

Você pode instalar a ferramenta MCCA usando o Windows PowerShell. Depois de baixar e instalar a ferramenta, você não precisará repetir essas etapas para executar relatórios. Sempre que você abrir o MCCA, ele solicitará suas credenciais de logon e gerará um novo relatório atualizado.

#### <a name="step-1-install-windows-powershell"></a>Etapa 1: Instalar o Windows PowerShell
Para começar, você precisará do módulo do PowerShell do Exchange Online (v2.0.3 ou superior) que está disponível na galeria do PowerShell. [Obter instruções de instalação.](https://www.powershellgallery.com/packages/ExchangeOnlineManagement/2.0.3)

#### <a name="step-2-install-mcca"></a>Etapa 2: Instalar o MCCA

Para instalar o MCCA, comece usando o PowerShell no modo de administrador. Siga as etapas abaixo:

1. Selecione o botão **Iniciar do** Windows.
2. Digite **PowerShell**, clique com o botão direito do mouse **no Windows PowerShell**, em seguida, selecione Executar como **administrador**.
1. No prompt de comando, digite:

    ```powershell
    Install-Module -Name MCCAPreview
    ```

#### <a name="step-3-run-a-report"></a>Etapa 3: Executar um relatório

Depois de instalar o MCCA, você pode executar o MCCA e gerar um relatório. Para executar um relatório:

1. Abra o PowerShell
2. Execute o cmdlet:

    ```powershell
    Get-MCCAReport
    ```
3. Depois que o MCCA é executado, ele faz uma verificação de versão inicial e solicita credenciais. No prompt de entrada do nome de usuário, entre com seu endereço de email da conta do Microsoft 365 (veja as funções qualificadas[para criar relatórios).](#role-based-reporting) Em seguida, insira sua senha no prompt de senha.

Seu relatório levará aproximadamente de 2 a 5 minutos para ser gerado. Quando terminar, uma janela do navegador abre e exibe seu relatório HTML. Sempre que você executar a ferramenta, ela solicitará suas credenciais e gerará um novo relatório. Esse relatório é armazenado localmente no seguinte diretório:

C:\Users \<username> \AppData\Local\Microsoft\MCCA. 

Você pode acessar relatórios gerados anteriormente a partir desse diretório.

## <a name="understanding-your-report"></a>Noções básicas sobre seu relatório

Seu relatório reflete os dados com base na data e hora em que ele foi gerado. A seção superior fornece detalhes sobre quando ela foi gerada, o nome da sua organização e a ID do locatário.

#### <a name="geolocation-based-reporting"></a>Relatórios baseados em geolocalização

A **seção** Observação mostra que seu relatório é personalizado com base na localização geográfica do seu locatário. As recomendações listadas na ferramenta serão específicas para seu país ou região.

Sua seleção de geolocalização é usada para avaliar os sits (tipos de informações confidenciais) que são relevantes para essa localização geográfica e gerar um relatório que se alinha ao seu país ou região. Escolha localizações geográficas com base nos dados que você tem em seu locatário.

Para alterar as informações de localização do seu relatório, você precisa fornecer um parâmetro de entrada de geolocalização (-Geo). Você pode escolher uma ou várias localizações geográficas aplicáveis ao seu locatário.

Siga estas instruções para executar um relatório com base em um local específico:

1. Abra o PowerShell
2. Para especificar uma determinada região, você executará um cmdlet usando os números da tabela abaixo que correspondem ao país ou região. Insira vários números separando-os com uma vírgula. Por exemplo, o cmdlet abaixo executará um relatório personalizado para o Asia-Pacific e o Japão:

    ```powershell
    Get-MCCAReport -Geo @(1,7)
    ```
  | Input |  País ou Região | 
  | :------------- | :------------: |
  | 1  | Ásia – Pacífico |
  | 2  | Austrália |
  | 3  | Canadá |
  | 4  | Europa (excluindo a França) / Oriente Médio /África |
  | 5  | França |
  | 6  | Índia |
  | 7  | Japão |
  | 8  | Coreia |
  | 9  | América do Norte (excluindo o Canadá) |
  | 10  | América do Sul |
  | 11  | África do Sul |
  | 12  | Suíça |
  | 13  | Emirados Árabes Unidos |
  | 14  | Reino Unido |


 > [!NOTE]
> O relatório sempre incluirá tipos de informações confidenciais internacionais com suporte da MCCA, como código SWIFT, número de cartão de crédito etc.

#### <a name="role-based-reporting"></a>Relatórios baseados em função

Seu relatório também será personalizado com base em sua função.

A tabela a seguir mostra quais funções têm acesso a quais seções do relatório. Outras funções em sua organização (não listadas na tabela abaixo) podem não ser capazes de executar a ferramenta ou podem executar a ferramenta e ter acesso limitado às informações no relatório final.

![MCCA - funções](../media/compliance-manager-mcca-roles.png "Funções MCCA")

Exceções:
1. O usuário não poderá gerar relatório para IP além da seção "Usar IRM para Exchange Online".
2. O usuário poderá gerar relatório para IP além da seção "Usar IRM para Exchange Online".
3. O usuário poderá gerar relatório para IP além da seção "Habilitar Conformidade de Comunicação no O365".
4. O usuário não poderá gerar relatório para IP além da seção "Habilitar Auditoria no Office 365".
5. O usuário poderá gerar relatório para IP além da seção "Habilitar Auditoria no Office 365".

#### <a name="solutions-summary-section"></a>Seção Resumo de Soluções

A **seção Resumo de** Soluções do relatório fornece uma visão geral das ações de melhoria que sua organização pode tomar no Gerenciador de Conformidade para ajudar a melhorar a postura de conformidade.

![MCCA - resumo de soluções](../media/compliance-manager-mcca-solutions.png "Tela Resumo de Soluções MCCA")

A MCCA avalia suas configurações atuais em relação às ações de melhoria recomendadas no Gerenciador de Conformidade. Qualquer ação de melhoria identificada pela ferramenta MCCA como precisando de atenção será listada nesta seção.

Ao lado de cada solução da Microsoft, há caixas codificadas por cores indicando o número de itens que correspondem às ações de melhoria no Gerenciador de Conformidade. As ações são divididas em três estados de status:

- **OK**: as ações que atendem às condições recomendadas e não precisam de atenção no momento
- **Melhoria**: ações que precisam de atenção
- **Recomendação:** ações que não precisam de atenção, mas para as quais recomendamos as práticas recomendadas
 
Selecione uma caixa para exibir as melhorias e recomendações.

**Itens com o status de melhoria**

Selecione o menu suspenso ao lado do **rótulo melhoria** à direita da ação de melhoria. Você verá um resumo rápido e detalhes sobre suas configurações atuais e as ações de melhoria recomendadas. O resumo inclui links diretos para o Gerenciador de Conformidade, a solução aplicável no centro de conformidade do Microsoft 365 e documentação relevante.

Clicar no link do Gerenciador de Conformidade leva você a uma exibição filtrada de todas as ações de melhoria nessa solução que você ainda não implementou. A partir daí, você pode ver o número [](compliance-score-calculation.md)de pontos que você pode alcançar para aumentar sua pontuação de conformidade e as avaliações às que elas se aplicam e os regulamentos e certificações aplicáveis.

Para DLP, há um botão **de Script** de Correção que oferece um script do PowerShell pré-gerado com base no que é recomendado. Você pode copiá-lo e colar diretamente no console do PowerShell. Ele criará uma política de DLP no modo de teste

**Itens com status de recomendação**

Selecione o menu suspenso ao lado do rótulo **Recomendação** à direita da ação de melhoria. Você verá um resumo do ambiente atual do Microsoft 365 da sua organização relacionado à ação de melhoria, juntamente com as práticas recomendadas.

## <a name="resources"></a>Recursos

Para obter informações mais detalhadas sobre como instalar, configurar e usar o MCCA, consulte as instruções LEIAME no [GitHub](https://github.com/OfficeDev/MCCA#overview) (nenhuma conta do GitHub é necessária).

Para obter mais informações sobre o Windows PowerShell, comece em [Como usar a documentação do PowerShell.](https://docs.microsoft.com/powershell/scripting/how-to-use-docs?view=powershell-7) Consulte também [Iniciando o Windows PowerShell.](https://docs.microsoft.com/powershell/scripting/windows-powershell/starting-windows-powershell?view=powershell-7)
