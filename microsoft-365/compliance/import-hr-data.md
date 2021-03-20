---
title: Configurar um conector para importar dados de RH
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: Os administradores podem configurar um conector de dados para importar dados de funcionários do sistema de recursos humanos (RH) de sua organização para o Microsoft 365. Isso permite que você use dados de RH em políticas de gerenciamento de riscos internos para ajudá-lo a detectar atividades por usuários específicos que podem representar uma ameaça interna à sua organização.
ms.openlocfilehash: eb11eb5790ca9c585db8bbb95b41747a72e5c8f1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911371"
---
# <a name="set-up-a-connector-to-import-hr-data"></a>Configurar um conector para importar dados de RH

Você pode configurar um conector de dados no centro de conformidade do Microsoft 365 para importar dados de recursos humanos (RH) relacionados a eventos como a demissão de um usuário ou uma alteração no nível de trabalho de um usuário. Os dados de RH podem ser usados pela solução de gerenciamento de riscos [insider](insider-risk-management.md) para gerar indicadores de risco que podem ajudá-lo a identificar possíveis atividades mal-intencionadas ou roubo de dados por usuários dentro de sua organização.

Configurar um conector para dados de RH que as políticas de gerenciamento de riscos insider podem usar para gerar indicadores de risco consistem em criar um arquivo CSV que contém os dados de RH, criar um aplicativo no Azure Active Directory usado para autenticação, criar um conector de dados de RH no centro de conformidade do Microsoft 365 e, em seguida, executar um script (agendado) que ingere os dados de RH em arquivos CSV para a nuvem da Microsoft para que ele seja disponibilizado para o insider solução de gerenciamento de riscos.

## <a name="before-you-begin"></a>Antes de começar

- Determine quais cenários de RH e dados serão importados para o Microsoft 365. Isso ajudará a determinar quantos arquivos CSV e conectores de RH você precisará criar e como gerar e estruturar os arquivos CSV. Os dados de RH que você importa são determinados pelas políticas de gerenciamento de riscos internas que você deseja implementar. Para obter mais informações, consulte Etapa 1.

- Determine como recuperar ou exportar os dados do sistema de RH da sua organização (e regularmente) e adicioná-los aos arquivos CSV que você criar na Etapa 1. O script executado na Etapa 4 carregará os dados de RH nos arquivos CSV para a nuvem da Microsoft.

- O usuário que cria o conector de RH na Etapa 3 deve receber a função de Exportação de Importação de Caixa de Correio no Exchange Online. Por padrão, essa função não é atribuída a nenhum grupo de funções no Exchange Online. Você pode adicionar a função Exportar Importação de Caixa de Correio ao grupo de função Gerenciamento da Organização no Exchange Online. Ou você pode criar um novo grupo de funções, atribuir a função De Exportação de Importação de Caixa de Correio e adicionar os usuários apropriados como membros. Para obter mais informações, consulte as seções Criar grupos de [função](/Exchange/permissions-exo/role-groups#create-role-groups) ou [Modificar](/Exchange/permissions-exo/role-groups#modify-role-groups) grupos de função no artigo "Gerenciar grupos de função no Exchange Online".

- O script de exemplo executado na Etapa 4 carregará seus dados de RH na nuvem da Microsoft para que possam ser usados pela solução de gerenciamento de riscos insider. Este script de exemplo não é suportado em nenhum programa ou serviço de suporte padrão da Microsoft. O script de amostra é fornecido COMO ESTÁ, sem garantia de nenhum tipo. A Microsoft também se isenta de todas as garantias implícitas, incluindo, sem limitação, quaisquer garantias implícitas de comercialização ou adequação a uma finalidade específica. Todo o risco decorrente do uso ou desempenho do script de amostra e da documentação permanece com você. De modo algum a Microsoft, seus autores ou qualquer outra pessoa envolvida na criação, produção ou veiculação dos scripts serão considerados responsáveis por quaisquer danos (incluindo sem limitações danos por perda de lucros comerciais, interrupção de negócios, perda de informações comerciais ou outras perdas pecuniárias) resultantes do uso ou da incapacidade de uso da documentação ou scripts de exemplo, mesmo que a Microsoft tenha sido alertada sobre a possibilidade de tais danos.

## <a name="step-1-prepare-a-csv-file-with-your-hr-data"></a>Etapa 1: preparar um arquivo CSV com seus dados de RH

A primeira etapa é criar um arquivo CSV que contenha os dados de RH que o conector importará para o Microsoft 365. Esses dados serão usados pela solução de risco insider para gerar indicadores de risco em potencial. Os dados para os seguintes cenários de RH podem ser importados para o Microsoft 365:

- Renúncia de funcionários. Informações sobre usuários que deixaram sua organização.

- O nível do trabalho muda. Informações sobre alterações no nível de trabalho para usuários, como promoções e rebaixamentos.

- Avaliações de desempenho. Informações sobre o desempenho do usuário.

- Planos de melhoria de desempenho. Informações sobre planos de melhoria de desempenho para usuários.

O tipo de dados de RH a ser importado depende da política de gerenciamento de riscos insider e do modelo de política correspondente que você deseja implementar. A tabela a seguir mostra qual tipo de dados de RH é necessário para cada modelo de política:

|  Modelo de política |  Tipo de dados de RH |
|:-----------------------------------------------|:---------------------------------------------------------------------|
| Roubo de dados ao separar usuários                   | Renúncias de funcionários                                                 |
| Vazamentos gerais de dados                              | Não aplicável                                                        |
| Vazamentos de dados por usuários prioritários                    | Não aplicável                                                        |
| Vazamentos de dados por usuários insatisfeitos                 | Alterações no nível do trabalho, avaliações de desempenho, planos de melhoria de desempenho |
| Violações gerais da política de segurança              | Não aplicável                                                        |
| Violações de política de segurança ao separar usuários   | Renúncias de funcionários                                                 |
| Violações de política de segurança por usuários prioritários    | Não aplicável                                                        |
| Violações de política de segurança por usuários insatisfeitos | Alterações no nível do trabalho, avaliações de desempenho, planos de melhoria de desempenho |
| Idioma ofensivo no email                     | Não aplicável                                                        |

Para obter mais informações sobre modelos de política para gerenciamento de riscos insider, consulte Políticas de gerenciamento de riscos [do Insider.](insider-risk-management-policies.md#policy-templates)

Para cada cenário de RH, você precisará fornecer os dados de RH correspondentes em um ou mais arquivos CSV. O número de arquivos CSV a ser usado para sua implementação de gerenciamento de riscos insider é discutido posteriormente nesta seção.

Depois de criar o arquivo CSV com os dados de RH necessários, armazene-o no computador local em que você executará o script na Etapa 4. Você também deve implementar uma estratégia de atualização para garantir que o arquivo CSV sempre contenha as informações mais atuais para que, independentemente da execução do script, os dados de RH mais atuais sejam carregados na nuvem da Microsoft e acessíveis à solução de gerenciamento de riscos internas.

> [!IMPORTANT]
> Os nomes de coluna descritos nas seções a seguir não são parâmetros necessários, mas apenas exemplos. Você pode usar qualquer nome de coluna em seus arquivos CSV. No entanto, os nomes de coluna  que você usa em um arquivo CSV devem ser mapeados para o tipo de dados ao criar o conector de RH na Etapa 3. Observe também que os arquivos CSV de exemplo nas seções a seguir são show no exibição Bloco de Notas. É muito mais fácil exibir e editar arquivos CSV no Microsoft Excel.

As seções a seguir descrevem os dados CSV necessários para cada cenário de RH.

### <a name="csv-file-for-employee-resignation-data"></a>Arquivo CSV para dados de demissão de funcionários

Aqui está um exemplo de um arquivo CSV para dados de demissão de funcionários.

```text
EmailAddress,ResignationDate,LastWorkingDate
sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,2019-04-29T15:18:02.4675041+05:30
pilarp@contoso.com,2019-04-24T09:15:49Z,2019-04-29T15:18:02.7117540
```

A tabela a seguir descreve cada coluna no arquivo CSV para dados de demissão de funcionários.

|  Coluna   |   Descrição |
|:------------|:----------------|
|**EmailAddress**| Especifica o endereço de email (UPN) do usuário encerrado.|
| **DesaudadoDate** | Especifica a data em que o emprego do usuário foi encerrado oficialmente em sua organização. Por exemplo, essa pode ser a data em que o usuário deu sua notificação sobre a saída da sua organização. Essa data pode ser diferente da data do último dia de trabalho da pessoa. Use o seguinte formato de data: , que é o formato de data e `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm` [hora ISO 8601.](https://www.iso.org/iso-8601-date-and-time-format.html)|
| **LastWorkingDate** | Especifica o último dia de trabalho do usuário encerrado. Use o seguinte formato de data: , que é o formato de data e `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm` [hora ISO 8601.](https://www.iso.org/iso-8601-date-and-time-format.html)|
|||

### <a name="csv-file-for-job-level-changes-data"></a>Arquivo CSV para nível de trabalho altera dados

Aqui está um exemplo de um arquivo CSV para nível de trabalho que altera dados.

```text
EmailAddress,EffectiveDate,OldLevel,NewLevel
sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,Level 61 – Sr. Manager,Level 60- Manager
pillar@contoso.com,2019-04-23T15:18:02.4675041+05:30,Level 62 – Director,Level 60- Sr. Manager
```

A tabela a seguir descreve cada coluna no arquivo CSV para o nível de trabalho altera os dados.

|  Coluna | Descrição |
|:--------- |:------------- |
| **EmailAddress**  | Especifica o endereço de email do usuário (UPN).|
| **EffectiveDate** | Especifica a data em que o nível de trabalho do usuário foi alterado oficialmente. Use o seguinte formato de data: , que é o formato de data e `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm` [hora ISO 8601.](https://www.iso.org/iso-8601-date-and-time-format.html)|
| **Comentários**| Especifica os comentários que o avaliador forneceu sobre a alteração do nível de trabalho. Você pode inserir um limite de 200 caracteres. Esse parâmetro é opcional. Não é preciso incluí-lo no arquivo CSV.|
| **OldLevel**| Especifica o nível de trabalho do usuário antes de ser alterado. Esse é um parâmetro de texto livre e pode conter taxonomia hierárquica para sua organização. Esse parâmetro é opcional. Não é preciso incluí-lo no arquivo CSV.|
| **NewLevel**| Especifica o nível de trabalho do usuário após a alteração. Esse é um parâmetro de texto livre e pode conter taxonomia hierárquica para sua organização. Esse parâmetro é opcional. Não é preciso incluí-lo no arquivo CSV.|
|||

### <a name="csv-file-for-performance-review-data"></a>Arquivo CSV para dados de revisão de desempenho

Veja um exemplo de um arquivo CSV para dados de desempenho.

```text
EmailAddress,EffectiveDate,Remarks,Rating
sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,Met expectations but bad attitude,2-Below expectation
pillar@contoso.com,2019-04-23T15:18:02.4675041+05:30, Multiple conflicts with the team
```

A tabela a seguir descreve cada coluna no arquivo CSV para dados de revisão de desempenho.

|  Coluna | Descrição |
|:----------|:--------------|
| **EmailAddress**  | Especifica o endereço de email do usuário (UPN).|
| **EffectiveDate** | Especifica a data em que o usuário foi informado oficialmente sobre o resultado da revisão de desempenho. Essa pode ser a data em que o ciclo de revisão de desempenho terminou. Use o seguinte formato de data: , que é o formato de data e `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm` [hora ISO 8601.](https://www.iso.org/iso-8601-date-and-time-format.html)|
| **Comentários**| Especifica quaisquer comentários que o avaliador tenha fornecido ao usuário para a revisão de desempenho. Este é um parâmetro de texto com um limite de 200 caracteres. Esse parâmetro é opcional. Não é preciso incluí-lo no arquivo CSV.|
| **Classificação**| Especifica a classificação fornecida para a revisão de desempenho. Esse é um parâmetro de texto e pode conter qualquer texto de forma livre que sua organização usa para reconhecer a avaliação. Por exemplo, "3 Expectativas atendidas" ou "2 Abaixo da média". Este é um parâmetro de texto com um limite de 25 caracteres. Esse parâmetro é opcional. Não é preciso incluí-lo no arquivo CSV.|
|||

### <a name="csv-file-for-performance-improvement-plan-data"></a>Arquivo CSV para dados do plano de melhoria de desempenho

Aqui está um exemplo de um arquivo CSV para os dados dos dados do plano de melhoria de desempenho.

```text
EmailAddress,EffectiveDate,ImprovementRemarks,PerformanceRating
sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,Met expectation but bad attitude,2-Below expectation
pillar@contoso.com,2019-04-23T15:18:02.4675041+05:30, Multiple conflicts with the team
```

A tabela a seguir descreve cada coluna no arquivo CSV para dados de revisão de desempenho.

|  Coluna |  Descrição |
|:----------|:---------------|
| **EmailAddress**  | Especifica o endereço de email do usuário (UPN).|
| **EffectiveDate** | Especifica a data em que o usuário foi informado oficialmente sobre seu plano de melhoria de desempenho. Você deve usar o seguinte formato de data: , que é o formato de data e `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm` [hora ISO 8601.](https://www.iso.org/iso-8601-date-and-time-format.html)|
| **Comentários**| Especifica quaisquer comentários que o avaliador tenha fornecido sobre o plano de melhoria de desempenho. Este é um parâmetro de texto com um limite de 200 caracteres. Esse é um parâmetro opcional. Não é preciso incluí-lo no arquivo CSV. |
| **Classificação**| Especifica qualquer classificação ou outras informações relacionadas à revisão de desempenho. plano de melhoria de desempenho. Esse é um parâmetro de texto e pode conter qualquer texto de formulário gratuito que sua organização usa para reconhecer a avaliação. Por exemplo, "3 Expectativas atendidas" ou "2 Abaixo da média". Este é um parâmetro de texto com limite de 25 caracteres. Esse é um parâmetro opcional. Não é preciso incluí-lo no arquivo CSV.|
|||

### <a name="determining-how-many-csv-files-to-use-for-hr-data"></a>Determinando quantos arquivos CSV usar para dados de RH

Na Etapa 3, você pode optar por criar conectores separados para cada tipo de dados de RH ou pode optar por criar um único conector para todos os tipos de dados. Você pode usar arquivos CSV separados que contenham dados para um cenário de RH (como os exemplos dos arquivos CSV descritos nas seções anteriores). Como alternativa, você pode usar um único arquivo CSV que contém dados para dois ou mais cenários de RH. Aqui estão algumas diretrizes para ajudá-lo a determinar quantos arquivos CSV usar para dados de RH.

- Se a política de gerenciamento de riscos internas que você deseja implementar exigir vários tipos de dados de RH, considere usar um único arquivo CSV que contenha todos os tipos de dados necessários.

- O método para gerar ou coletar os dados de RH pode determinar o número de arquivos CSV. Por exemplo, se os diferentes tipos de dados de RH usados para configurar um conector de RH estão localizados em um único sistema de RH em sua organização, você poderá exportar os dados para um único arquivo CSV. Mas se os dados são distribuídos em diferentes sistemas de RH, então pode ser mais fácil exportar dados para arquivos CSV diferentes. Por exemplo, os dados de renúncia de funcionários podem estar localizados em um sistema de RH diferente do nível de trabalho ou dados de revisão de desempenho. Nesse caso, pode ser mais fácil ter arquivos CSV separados em vez de ter que combinar manualmente os dados em um único arquivo CSV. Portanto, a forma como você recupera ou exporta dados de seus sistemas de RH pode determinar como o número de arquivos CSV que você precisará.

- Como regra geral, o número de conectores de RH que você precisará criar é determinado pelos tipos de dados em um arquivo CSV. Por exemplo, se um arquivo CSV contiver todos os tipos de dados necessários para dar suporte à implementação de gerenciamento de riscos insider, você precisará apenas de um conector de RH. Mas se você tiver dois arquivos CSV separados que contêm um único tipo de dados, será preciso criar dois conectores de RH. Uma exceção a isso é que, se você adicionar uma coluna **HRScenario** a um arquivo CSV (consulte a próxima seção), você pode configurar um único conector de RH que pode processar arquivos CSV diferentes.

### <a name="configuring-a-single-csv-file-for-multiple-hr-data-types"></a>Configurando um único arquivo CSV para vários tipos de dados de RH

Você pode adicionar vários tipos de dados de RH a um único arquivo CSV. Isso será útil se a solução de gerenciamento de riscos internas que você está implementando exigir vários tipos de dados de RH ou se os tipos de dados estão localizados em um único sistema de RH em sua organização. Ter menos arquivos CSV sempre permite que você tenha menos conectores de RH para criar e gerenciar.

Aqui estão os requisitos para configurar um arquivo CSV com vários tipos de dados:

- Você precisa adicionar as colunas necessárias (e opcional se usá-las) para cada tipo de dados e o nome da coluna correspondente na linha do header. Se um tipo de dados não corresponder a uma coluna, você poderá deixar o valor em branco.

- Para usar um arquivo CSV com vários tipos de dados de RH, o conector de RH precisa saber quais linhas no arquivo CSV contêm quais tipos de dados de RH. Isso é feito adicionando uma **coluna HRScenario** adicional ao arquivo CSV. Os valores nesta coluna identificam o tipo de dados de RH em cada linha. Por exemplo, os valores que correspondem aos quatro cenários de RH podem ser Renúncia, Alteração no nível do trabalho, revisão de desempenho e plano de melhoria \` \` de \` \` \` \` \` \` desempenho.

- Se você tiver vários arquivos CSV que contenham uma coluna HRScenario**, certifique-se de que cada arquivo use o mesmo nome de coluna e os mesmos valores que identificam os cenários específicos de RH.

O exemplo a seguir mostra um arquivo CSV que contém a **coluna HRScenario.** Os valores na coluna HRScenario identificam o tipo de dados na linha correspondente.

```text
HRScenario,EmailAddress,ResignationDate,LastWorkingDate,EffectiveDate,Remarks,Rating,OldLevel,NewLevel
Resignation,sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,2019-04-29T15:18:02.4675041+05:30,,,,
Resignation,pilarp@contoso.com,2019-04-24T09:15:49Z,2019-04-29T15:18:02.7117540,,,,
Job level change,sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,,,,,Level 61 Sr. Manager, Level 60 Manager
Job level change,pillarp@contoso.com,2019-04-23T15:18:02.4675041+05:30,,,,,Level 62 Director,Level 60 Sr Manager
Performance review,sarad@contoso.com,,,2019-04-23T15:18:02.4675041+05:30,Met expectation but bad attitude,2 Below expectations,,
Performance review,pillarp@contoso.com,,,2019-04-23T15:18:02.4675041+05:30, Multiple conflicts with the team,,
Performance improvement plan,sarad@contoso.com,,,2019-04-23T15:18:02.4675041+05:30,Met expectations but bad attitude,2 Below expectations,,
Performance improvement plan,pillarp@contoso.com,,,2019-04-23T15:18:02.4675041+05:30,Multiple conflicts with the team,,
```

> [!NOTE]
> Você pode usar qualquer nome para a coluna que identifique o tipo de dados de RH porque você mapeará o nome da coluna em seu arquivo CSV como a coluna que identifica o tipo de dados de RH ao configurar o conector na Etapa 3. Você também mapeará os valores usados para a coluna de tipo de dados quando configurar o conector.

### <a name="adding-the-hrscenario-column-to-a-csv-file-that-contains-a-single-data-type"></a>Adicionando a coluna HRScenario a um arquivo CSV que contém um único tipo de dados

Com base nos sistemas de RH da sua organização e como você exportará dados de RH para o arquivo CSV, talvez seja preciso criar vários arquivos CSV que contenham um único tipo de dados de RH. Nesse caso, você ainda pode criar um único conector de RH para importar dados de arquivos CSV diferentes. Para fazer isso, basta adicionar uma coluna HRScenario ao arquivo CSV e especificar o tipo de dados de RH. Em seguida, você pode executar o script para cada arquivo CSV, mas usar a mesma ID de trabalho para o conector. Consulte [Etapa 4](#step-4-run-the-sample-script-to-upload-your-hr-data).

## <a name="step-2-create-an-app-in-azure-active-directory"></a>Etapa 2: Criar um aplicativo no Azure Active Directory

A próxima etapa é criar e registrar um novo aplicativo no Azure Active Directory (Azure AD). O aplicativo corresponderá ao conector de RH criado na Etapa 3. A criação desse aplicativo permitirá que o Azure AD autenture o conector de RH quando ele for executado e tentar acessar sua organização. Este aplicativo também será usado para autenticar o script executado na Etapa 4 para carregar seus dados de RH na nuvem da Microsoft. Durante a criação deste aplicativo do Azure AD, salve as informações a seguir. Esses valores serão usados nas Etapas 3 e Etapa 4.

- ID do aplicativo do Azure AD (também chamada de *ID do aplicativo* ou *ID do cliente)*

- Segredo do aplicativo do Azure AD (também chamado *de segredo do cliente)*

- ID do locatário (também chamada de *ID de diretório*)

Para obter instruções passo a passo para criar um aplicativo no Azure AD, consulte [Register an application with the Microsoft identity platform](/azure/active-directory/develop/quickstart-register-app).

## <a name="step-3-create-the-hr-connector"></a>Etapa 3: Criar o conector de RH

A próxima etapa é criar um conector de RH no centro de conformidade do Microsoft 365. Depois de executar o script na Etapa 4, o conector de RH criado ingerirá os dados de RH do arquivo CSV para sua organização do Microsoft 365. Antes de criar um conector, certifique-se de ter uma lista dos cenários de RH e dos nomes de coluna CSV correspondentes para cada um deles. Você precisa mapear os dados necessários para cada cenário para os nomes de coluna reais no arquivo CSV ao configurar o conector. Como alternativa, você pode carregar um arquivo CSV de exemplo ao configurar o conector e o assistente o ajudará a mapear o nome das colunas para os tipos de dados necessários.

Depois de concluir essa etapa, copie a ID do trabalho gerada ao criar o conector. Você usará a ID do trabalho quando executar o script.

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com/) e clique em **Conectores de dados** na nav esquerda.

2. Na página **Conectores de dados** em **RH,** clique em **Exibir**.

3. Na página **Hr Custom,** clique em **Adicionar conector**.

4. Na página **Configurar a conexão,** faça o seguinte e clique em **Próximo**:

   1. Digite ou colar a ID do aplicativo do Azure AD para o aplicativo do Azure que você criou na Etapa 2.

   1. Digite um nome para o conector de RH.

5. Na página Cenários de RH, selecione um ou mais cenários de RH para os qual você deseja importar dados e clique em **Próximo**.

6. Na página método de mapeamento de arquivos, selecione uma das seguintes opções e clique em **Próximo**.

   - **Carregar um arquivo de exemplo**. Se você selecionar essa opção, clique em Carregar arquivo **de** exemplo para carregar o arquivo CSV que você preparou na Etapa 1. Essa opção permite selecionar rapidamente nomes de coluna no arquivo CSV de uma listada para mapeá-los para os tipos de dados dos cenários de RH selecionados anteriormente.

   OU

   - **Forneça manualmente os detalhes do mapeamento.** Se você selecionar essa opção, será preciso digitar o nome das colunas no arquivo CSV para mapeá-las para os tipos de dados dos cenários de RH selecionados anteriormente.

7. Na página Detalhes do mapeamento de arquivos, faça um dos seguintes, dependendo se você carregou um arquivo CSV de exemplo e se você está configurando o conector para um único cenário de RH ou para vários cenários. Se você tiver carregado um arquivo de exemplo, não será preciso digitar os nomes das colunas. Escolha-os em uma lista lista listada.

    - Se você selecionou um único cenário de RH na etapa anterior, digite os nomes de header de coluna (também chamados de parâmetros ) do arquivo CSV que você criou na Etapa 1 em cada uma das caixas *apropriadas.* Os nomes de coluna que você digita não são sensíveis a minúsculas, mas não se esqueça de incluir espaços se os nomes de coluna em seu arquivo CSV incluir espaços. Conforme explicado anteriormente, os nomes digitados nessas caixas devem corresponder aos nomes de parâmetros no arquivo CSV. Por exemplo, a captura de tela a seguir mostra os nomes de parâmetros do arquivo CSV de exemplo para o cenário de RH de demissão de funcionários mostrado na Etapa 1.

    - Se você selecionou vários tipos de dados na etapa acima, precisará inserir o nome da coluna do identificador que identificará o tipo de dados de RH no arquivo CSV. Depois de inserir o nome da coluna do identificador, digite o valor que identifica esse tipo de dados de RH e digite os nomes de header de coluna para os tipos de dados selecionados dos arquivos CSV que você criou na Etapa 1 em cada uma das caixas apropriadas para cada tipo de dados selecionado. Conforme explicado anteriormente, os nomes que você digitar nessas caixas devem corresponder aos nomes de coluna em seu arquivo CSV.

8. Na página **Revisão,** revise suas configurações e clique em **Concluir** para criar o conector.

   Uma página de status é exibida confirmando que o conector foi criado. Esta página contém duas coisas importantes que você precisa para concluir a próxima etapa para executar o script de exemplo para carregar seus dados de RH.

   ![Analisar página com iD de trabalho e link para github para script de exemplo](../media/HRConnector_Confirmation.png)

   1. **ID do trabalho.** Você precisará dessa ID de trabalho para executar o script na próxima etapa. Você pode copiá-lo desta página ou da página de sobrevoo do conector.

   1. **Link para script de exemplo.** Clique no link **aqui** para acessar o site do GitHub para acessar o script de exemplo (o link abre uma nova janela). Mantenha essa janela aberta para que você possa copiar o script na Etapa 4. Como alternativa, você pode marcar o destino ou copiar a URL para poder acessá-la novamente ao executar o script. Esse link também está disponível na página de sobrevoo do conector.

9. Clique em **Concluído**.

   O novo conector é exibido na lista na guia **Conectores.**

10. Clique no conector de RH que você acabou de criar para exibir a página de sobrevoo, que contém propriedades e outras informações sobre o conector.

   ![Página de sobrevoo para novo conector de RH](../media/HRConnectorWizard7.png)

Se você ainda não tiver feito isso, poderá copiar os valores para a ID do **aplicativo do Azure** e a **ID** do trabalho do Conector. Você precisará deles para executar o script na próxima etapa. Você também pode baixar o script na página de sobrevoo (ou baixá-lo usando o link na próxima etapa).)

Você também pode clicar em **Editar** para alterar a ID do Aplicativo do Azure ou os nomes de header de coluna que você definiu na página **mapeamento de** arquivo.

## <a name="step-4-run-the-sample-script-to-upload-your-hr-data"></a>Etapa 4: Executar o script de exemplo para carregar seus dados de RH

A última etapa na configuração de um conector de RH é executar um script de exemplo que carregará os dados de RH no arquivo CSV (criado na Etapa 1) para a nuvem da Microsoft. Especificamente, o script carrega os dados no conector de RH. Depois de executar o script, o conector de RH criado na Etapa 3 importa os dados de RH para sua organização do Microsoft 365, onde ele pode ser acessado por outras ferramentas de conformidade, como a solução de gerenciamento de riscos do Insider. Depois de executar o script, considere agendar uma tarefa para que ela seja executado automaticamente diariamente para que os dados de rescisão do funcionário mais atuais são carregados na nuvem da Microsoft. Consulte [Agendar o script para ser executado automaticamente](#optional-step-6-schedule-the-script-to-run-automatically).

1. Vá para a janela que você deixou aberta na etapa anterior para acessar o site do GitHub com o script de exemplo. Como alternativa, abra o site com indicador ou use a URL copiada.

2. Clique no **botão Bruto** para exibir o script no exibição de texto.

3. Copie todas as linhas do script de exemplo e salve-as em um arquivo de texto.

4. Modifique o script de exemplo para sua organização, se necessário.

5. Salve o arquivo de texto como um Windows PowerShell de script usando um sufixo de nome de arquivo `.ps1` de ; por exemplo, `HRConnector.ps1` .

6. Abra um Prompt de Comando no computador local e vá para o diretório onde você salvou o script.

7. Execute o seguinte comando para carregar os dados de RH no arquivo CSV na nuvem da Microsoft; por exemplo:

    ```powershell
    .\HRConnector.ps1 -tenantId <tenantId> -appId <appId>  -appSecret <appSecret>  -jobId <jobId>  -csvFilePath '<csvFilePath>'
    ```

   A tabela a seguir descreve os parâmetros a ser usado com esse script e seus valores necessários. As informações obtidas nas etapas anteriores são usadas nos valores desses parâmetros.

   | Parâmetro | Descrição |
   |:-----|:-----|:-----|
   |`tenantId`|Esta é a ID da sua organização do Microsoft 365 obtida na Etapa 2. Você também pode obter a ID do locatário para sua organização na folha **Visão** geral no centro de administração do Azure AD. Isso é usado para identificar sua organização.|
   |`appId` |Esta é a ID do aplicativo do Azure AD para o aplicativo que você criou no Azure AD na Etapa 2. Isso é usado pelo Azure AD para autenticação quando o script tenta acessar sua organização do Microsoft 365. | 
   |`appSecret`|Este é o segredo do aplicativo do Azure AD para o aplicativo que você criou no Azure AD na Etapa 2. Isso também é usado para autenticação.|
   |`jobId`|Esta é a ID do trabalho para o conector de RH que você criou na Etapa 3. Isso é usado para associar os dados de RH carregados na nuvem da Microsoft com o conector de RH.|
   |`csvFilePath`|Esse é o caminho do arquivo CSV (armazenado no mesmo sistema que o script) que você criou na Etapa 1. Tente evitar espaços no caminho do arquivo; caso contrário, use aspas simples.|
   |||

   Veja um exemplo da sintaxe do script do conector de RH usando valores reais para cada parâmetro:

   ```powershell
    .\HRConnector.ps1 -tenantId d5723623-11cf-4e2e-b5a5-01d1506273g9 -appId 29ee526e-f9a7-4e98-a682-67f41bfd643e -appSecret MNubVGbcQDkGCnn -jobId b8be4a7d-e338-43eb-a69e-c513cd458eba -csvFilePath 'C:\Users\contosoadmin\Desktop\Data\employee_termination_data.csv'
    ```

   Se o carregamento for bem-sucedido, o script exibirá a **mensagem Carregar bem-sucedida.**

   > [!NOTE]
   > Se você tiver problemas para executar o comando anterior por causa de políticas de execução, consulte [About Execution Policies](/powershell/module/microsoft.powershell.core/about/about_execution_policies) e [Set-ExecutionPolicy](/powershell/module/microsoft.powershell.security/set-executionpolicy) para obter orientações sobre como definir políticas de execução.

## <a name="step-5-monitor-the-hr-connector"></a>Etapa 5: Monitorar o conector de RH

Depois de criar o conector de RH e executar o script para carregar seus dados de RH, você poderá exibir o conector e carregar o status no centro de conformidade do Microsoft 365. Se você agendar o script para ser executado automaticamente regularmente, você também poderá exibir o status atual após a última vez em que o script foi executado.

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com) e clique **em Conectores de dados** na nav esquerda.

2. Clique na **guia Conectores** e selecione o conector de RH para exibir a página de sobrevoo. Esta página contém as propriedades e informações sobre o conector.

   ![Página do flyout do conector de RH com propriedades e status](../media/HRConnectorFlyout1.png)

3. Em **Progresso**, clique no link **Baixar log** para abrir (ou salvar) o log de status do conector. Esse log contém informações sobre cada vez que o script é executado e carrega os dados do arquivo CSV para a nuvem da Microsoft. 

   ![Arquivo de log do conector de RH exibe linhas de número do arquivo CSV que foram carregadas](../media/HRConnectorLogFile.png)

   O `RecordsSaved` campo indica o número de linhas no arquivo CSV carregado. Por exemplo, se o arquivo CSV contiver quatro linhas, o valor dos campos será 4, se o script tiver carregado com êxito todas as linhas no `RecordsSaved` arquivo CSV.

Se você não tiver executado o script na Etapa 4, um link para baixar o script será exibido em **Last import**. Você pode baixar o script e seguir as etapas para executar o script.

## <a name="optional-step-6-schedule-the-script-to-run-automatically"></a>(Opcional) Etapa 6: Agendar o script para ser executado automaticamente

Para garantir que os dados de RH mais recentes da sua organização estão disponíveis para ferramentas como a solução de gerenciamento de riscos insider, recomendamos que você agende o script para ser executado automaticamente de forma recorrente, como uma vez por dia. Isso também exige que você atualize os dados de RH no arquivo CSV em um cronograma semelhante (se não o mesmo) para que ele contenha as informações mais recentes sobre os funcionários que saem da sua organização. O objetivo é carregar os dados de RH mais atuais para que o conector de RH possa torná-los disponíveis para a solução de gerenciamento de riscos insider.

Você pode usar o aplicativo Agendador de Tarefas no Windows para executar automaticamente o script todos os dias.

1. No computador local, clique no botão **Iniciar** do Windows e digite **Agendador de Tarefas.**

2. Clique no **aplicativo Agendador de** Tarefas para abri-lo.

3. Na seção **Ações,** clique em **Criar Tarefa**.

4. Na guia **Geral,** digite um nome descritivo para a tarefa agendada; por exemplo, **Script do Conector de RH**. Você também pode adicionar uma descrição opcional.

5. Em **Opções de segurança,** faça o seguinte:

   1. Determine se o script será executado somente quando você estiver conectado ao computador ou execute-o quando estiver conectado ou não.

   1. Verifique se a caixa **de seleção Executar com os privilégios mais altos** está selecionada.

6. Selecione a **guia Gatilhos,** clique em **Novo** e faça o seguinte:

   1. Em **Configurações,** selecione **a opção Diário** e escolha uma data e hora para executar o script pela primeira vez. O script será todos os dias no mesmo horário especificado.

   1. Em **Configurações avançadas,** verifique se a caixa **de seleção** Habilitado está selecionada.

   1. Clique em **OK**.

7. Selecione a **guia Ações,** clique em **Novo** e faça o seguinte:

   ![Configurações de ação para criar uma nova tarefa agendada para o script do conector de RH](../media/HRConnectorScheduleTask1.png)

   1. Na lista **suspenso Ação,** certifique-se de que **Iniciar um programa** está selecionado.

   1. Na caixa **Programa/script,** clique em **Procurar** e vá para o seguinte local e selecione-o para que o caminho seja exibido na caixa: `C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe` .

   1. Na caixa **Adicionar argumentos (opcional),** colar o mesmo comando de script que você correu na Etapa 4. Por exemplo, `.\HRConnector.ps1 -tenantId "d5723623-11cf-4e2e-b5a5-01d1506273g9" -appId "c12823b7-b55a-4989-faba-02de41bb97c3" -appSecret "MNubVGbcQDkGCnn"  -jobId "e081f4f4-3831-48d6-7bb3-fcfab1581458" -csvFilePath "C:\Users\contosoadmin\Desktop\Data\employee_termination_data.csv"`

   1. Na caixa **Iniciar em (opcional),** colar o local da pasta do script que você correu na Etapa 4. Por exemplo, `C:\Users\contosoadmin\Desktop\Scripts`.

   1. Clique **em Ok** para salvar as configurações da nova ação.

8. Na janela **Criar Tarefa,** clique em **Ok** para salvar a tarefa agendada. Você pode ser solicitado a inserir suas credenciais de conta de usuário.

   A nova tarefa é exibida na Biblioteca do Agendador de Tarefas.

   ![A nova tarefa é exibida na Biblioteca do Agendador de Tarefas](../media/HRConnectorTaskSchedulerLibrary.png)

   A última vez que o script foi executado e a próxima vez que ele está agendado para ser executado é exibido. Você pode clicar duas vezes na tarefa para editá-la.

   Você também pode verificar a última vez que o script foi em uma página de sobrevoo do conector de RH correspondente no centro de conformidade.

## <a name="existing-hr-connectors"></a>Conectores de RH existentes

Em 20 de julho de 2020, lançamos cenários adicionais compatíveis com conectores de RH. Esses são os cenários de RH descritos anteriormente neste artigo. Qualquer conector de RH criado antes dessa data só dá suporte ao cenário de demissão de funcionários. Se você criou um conector de RH antes de 20 de julho de 2020, nós o migramos para que ele continue a migrar seus dados de RH para a nuvem da Microsoft. Não é preciso fazer nada para manter essa funcionalidade. Você pode continuar usando o conector sem qualquer interrupção.

Se você quiser implementar cenários de RH adicionais, crie um novo conector de RH e configure-o para os cenários de RH adicionais que foram lançados. Você também precisará criar um ou mais novos arquivos CSV que contenham os dados para dar suporte aos cenários de RH adicionais. Depois de criar um novo conector de RH, execute o script usando a ID de trabalho do novo conector e arquivos CSV com os dados para seus cenários de RH adicionais.