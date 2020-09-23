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
description: Os administradores podem configurar um conector de dados para importar dados de funcionários do sistema de recursos humanos da organização (RH) para o Microsoft 365. Isso permite que você use dados de RH em políticas de gerenciamento de risco do insider para ajudá-lo a detectar atividades por usuários específicos que possam representar uma ameaça interna à sua organização.
ms.openlocfilehash: 31afa01a518028e7ec25116e947b4e0d6dc94dac
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201540"
---
# <a name="set-up-a-connector-to-import-hr-data"></a>Configurar um conector para importar dados de RH

Você pode configurar um conector de dados no centro de conformidade da Microsoft 365 para importar dados de recursos humanos (RH) relacionados a eventos, como a desistência de um usuário ou uma alteração no nível de trabalho de um usuário. Os dados de RH podem ser usados pela [solução de gerenciamento de risco do insider](insider-risk-management.md) para gerar indicadores de risco que podem ajudá-lo a identificar possíveis atividades mal-intencionadas ou roubo de dados por usuários dentro da sua organização.

Configurar um conector para dados de RH que as políticas de gerenciamento de risco do insider podem usar para gerar indicadores de risco consistem em criar um arquivo CSV que contenha os dados de RH, criar um aplicativo no Azure Active Directory que é usado para autenticação, criar um conector de dados de RH no centro de conformidade do Microsoft 365 e, em seguida, executar um script (de acordo com uma base agendada) que absorve os dados de RH em arquivos CSV para a nuvem da Microsoft, para que ele esteja disponível para o Insider solução de gerenciamento de risco.

## <a name="before-you-begin"></a>Antes de começar

- Determine quais cenários e dados de RH serão importados para o Microsoft 365. Isso ajudará a determinar quantos arquivos CSV e conectores de RH você precisará criar, e como gerar e estruturar os arquivos CSV. Os dados de RH que você importou são determinados pelas políticas de gerenciamento de risco do insider que você deseja implementar. Para obter mais informações, consulte a etapa 1.

- Determine como recuperar ou exportar os dados do sistema de RH da sua organização (e regularmente) e adicioná-los aos arquivos CSV que você criou na etapa 1. O script executado na etapa 4 carregará os dados de RH nos arquivos CSV para a nuvem da Microsoft.

- Sua organização deve ter o consentimento para permitir que o serviço de importação do Office 365 acesse os dados da sua organização. Para concordar com essa solicitação, [acesse a página](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), entre com as credenciais de um administrador global do Microsoft 365 e aceite a solicitação. Você precisa concluir esta etapa para poder criar com êxito o conector de RH na etapa 3.

- O usuário que cria o conector de RH na etapa 3 deve ser atribuído à função de exportação de importação de caixa de correio no Exchange Online. Por padrão, essa função não é atribuída a nenhum grupo de funções no Exchange Online. Você pode adicionar a função de exportação de importação de caixa de correio ao grupo de funções Gerenciamento da organização no Exchange Online. Ou você pode criar um novo grupo de função, atribua a função de exportação de importação de caixa de correio e, em seguida, adicione os usuários apropriados como membros. Para obter mais informações, consulte as seções [criar grupos de função](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) ou [modificar grupos de função](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) no artigo "gerenciar grupos de função no Exchange Online".

- O script de exemplo executado na etapa 4 carregará seus dados de RH na nuvem da Microsoft para que ele possa ser usado pela solução de gerenciamento de risco do insider. Este script de exemplo não tem suporte em nenhum programa ou serviço de suporte padrão da Microsoft. O script de exemplo é fornecido como está sem garantia de qualquer tipo. A Microsoft também se isenta de todas as garantias implícitas, incluindo sem limitações quaisquer garantias aplicáveis de padrões de comercialização ou de adequação a uma finalidade específica. Todo o risco resultante do uso ou do desempenho do script de exemplo e da documentação permanece com você. De modo algum a Microsoft, seus autores ou qualquer outra pessoa envolvida na criação, produção ou veiculação dos scripts serão considerados responsáveis por quaisquer danos (incluindo sem limitações danos por perda de lucros comerciais, interrupção de negócios, perda de informações comerciais ou outras perdas pecuniárias) resultantes do uso ou da incapacidade de uso da documentação ou scripts de exemplo, mesmo que a Microsoft tenha sido alertada sobre a possibilidade de tais danos.

## <a name="step-1-prepare-a-csv-file-with-your-hr-data"></a>Etapa 1: preparar um arquivo CSV com seus dados de RH

A primeira etapa é criar um arquivo CSV que contenha os dados de RH que o conector irá importar para o Microsoft 365. Esses dados serão usados pela solução de risco Insider para gerar possíveis indicadores de risco. Os dados dos seguintes cenários de RH podem ser importados para o Microsoft 365:

- Demissão de funcionários. Informações sobre usuários que saíram da sua organização.

- Alterações no nível do trabalho. Informações sobre alterações de nível de trabalho para usuários, como promoções e rebaixamentos.

- Revisões de desempenho. Informações sobre o desempenho do usuário.

- Planos de melhoria de desempenho. Informações sobre planos de melhoria de desempenho para usuários.

O tipo de dados de RH a ser importado depende da política de gerenciamento de risco do insider e do modelo de política correspondente que você deseja implementar. A tabela a seguir mostra qual tipo de dados de RH é necessário para cada modelo de política:

| **Modelo de política**| **Tipo de dados HR**|
|:-----------------------------------------------|:---------------------------------------------------------------------|
| Roubo de dados por parte de usuários                   | Reatribuições de funcionários                                                 |
| Vazamentos de dados gerais                              | Não aplicável                                                        |
| Vazamentos de dados por usuários de prioridade                    | Não aplicável                                                        |
| Vazamentos de dados por usuários descontentes                 | Alterações no nível do trabalho, revisões de desempenho, planos de melhoria de desempenho |
| Violações de política de segurança geral              | Não aplicável                                                        |
| Violações de política de segurança por parte dos usuários   | Reatribuições de funcionários                                                 |
| Violações de política de segurança por usuários de prioridade    | Não aplicável                                                        |
| Violações de política de segurança por usuários descontentes | Alterações no nível do trabalho, revisões de desempenho, planos de melhoria de desempenho |
| Idioma ofensivo no email                     | Não aplicável                                                        |

Para obter mais informações sobre modelos de política para o gerenciamento de risco do Insider, consulte [Insider Risk Management Policies](insider-risk-management-policies.md#policy-templates).

Para cada cenário de RH, você precisará fornecer os dados de RH correspondentes em um ou mais arquivos CSV. O número de arquivos CSV a ser usado para sua implementação de gerenciamento de risco do Insider é discutido posteriormente nesta seção.

Depois de criar o arquivo CSV com os dados de RH necessários, armazene-os no computador local em que você executa o script na etapa 4. Você também deve implementar uma estratégia de atualização para certificar-se de que o arquivo CSV sempre contenha as informações mais atuais para que seja o que você executar o script, os dados de RH mais atuais serão carregados para a nuvem da Microsoft e acessíveis à solução de gerenciamento de risco do insider.

> [!IMPORTANT]
> Os nomes de coluna descritos nas seções a seguir não são parâmetros obrigatórios, mas apenas exemplos. Você pode usar qualquer nome de coluna em seus arquivos CSV. No entanto, os nomes de coluna usados em um arquivo CSV *devem* ser mapeados para o tipo de dados quando você cria o conector de RH na etapa 3. Observe também que os arquivos CSV de amostra nas seções a seguir são mostrados no modo de exibição do bloco de notas. É muito mais fácil exibir e editar arquivos CSV no Microsoft Excel.

As seções a seguir descrevem os dados de CSV necessários para cada cenário de RH.

### <a name="csv-file-for-employee-resignation-data"></a>Arquivo CSV para dados de demissão de funcionários

Veja um exemplo de um arquivo CSV para dados de demissão de funcionários.

```text
EmailAddress,ResignationDate,LastWorkingDate
sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,2019-04-29T15:18:02.4675041+05:30
pilarp@contoso.com,2019-04-24T09:15:49Z,2019-04-29T15:18:02.7117540
```

A tabela a seguir descreve cada coluna no arquivo CSV para dados de demissão de funcionários.

| **Coluna**  |  **Descrição**|
|:------------|:----------------|
|**EmailAddress**| Especifica o endereço de email (UPN) do usuário terminado.|
| **ResignationDate** | Especifica a data em que o emprego do usuário foi oficialmente demitido em sua organização. Por exemplo, essa pode ser a data em que o usuário deu o aviso de sair da sua organização. Essa data pode ser diferente da data do último dia de trabalho da pessoa. Use o seguinte formato de data: `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm` , que é o [formato de data e hora ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html).|
| **LastWorkingDate** | Especifica o último dia de trabalho para o usuário demitido. Use o seguinte formato de data: `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm` , que é o [formato de data e hora ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html).|
|||

### <a name="csv-file-for-job-level-changes-data"></a>Arquivo CSV para dados de alterações de nível de trabalho

Veja um exemplo de um arquivo CSV para dados de alterações de nível de trabalho.

```text
EmailAddress,EffectiveDate,OldLevel,NewLevel
sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,Level 61 – Sr. Manager,Level 60- Manager
pillar@contoso.com,2019-04-23T15:18:02.4675041+05:30,Level 62 – Director,Level 60- Sr. Manager
```

A tabela a seguir descreve cada coluna no arquivo CSV para dados de alterações de nível de trabalho.

| **Coluna**|**Descrição**|
|:--------- |:------------- |
| **EmailAddress**  | Especifica o endereço de email do usuário (UPN).|
| **EffectiveDate** | Especifica a data em que o nível de trabalho do usuário foi oficialmente alterado. Use o seguinte formato de data: `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm` , que é o [formato de data e hora ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html).|
| **Comentários**| Especifica o comentários que o avaliador forneceu sobre a alteração do nível de trabalho. Você pode inserir um limite de 200 caracteres. Esse parâmetro é opcional. Você não precisa incluí-lo no arquivo CSV.|
| **OldLevel**| Especifica o nível de trabalho do usuário antes de ser alterado. Este é um parâmetro de texto livre e pode conter uma taxonomia hierárquica para sua organização. Esse parâmetro é opcional. Você não precisa incluí-lo no arquivo CSV.|
| **NewLevel**| Especifica o nível de trabalho do usuário após sua alteração. Este é um parâmetro de texto livre e pode conter uma taxonomia hierárquica para sua organização. Esse parâmetro é opcional. Você não precisa incluí-lo no arquivo CSV.|
|||

### <a name="csv-file-for-performance-review-data"></a>Arquivo CSV para dados de avaliação de desempenho

Veja um exemplo de um arquivo CSV para dados de desempenho.

```text
EmailAddress,EffectiveDate,Remarks,Rating
sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,Met expectations but bad attitude,2-Below expectation
pillar@contoso.com,2019-04-23T15:18:02.4675041+05:30, Multiple conflicts with the team
```

A tabela a seguir descreve cada coluna no arquivo CSV para dados de revisão de desempenho.

| **Coluna**|**Descrição**|
|:----------|:--------------|
| **EmailAddress**  | Especifica o endereço de email do usuário (UPN).|
| **EffectiveDate** | Especifica a data em que o usuário foi oficialmente informado sobre o resultado de sua avaliação de desempenho. Esta pode ser a data em que o ciclo de revisão de desempenho terminou. Use o seguinte formato de data: `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm` , que é o [formato de data e hora ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html).|
| **Comentários**| Especifica qualquer comentários que o avaliador forneceu ao usuário para a avaliação de desempenho. Este é um parâmetro de texto com um limite de 200 caracteres. Esse parâmetro é opcional. Você não precisa incluí-lo no arquivo CSV.|
| **Classificação**| Especifica a classificação fornecida para a revisão de desempenho. Este é um parâmetro de texto e pode conter qualquer texto de forma livre que sua organização usa para reconhecer a avaliação. Por exemplo, "3 expectativas atendidas" ou "2 abaixo da média". Este é um parâmetro de texto com um limite de 25 caracteres. Esse parâmetro é opcional. Você não precisa incluí-lo no arquivo CSV.|
|||

### <a name="csv-file-for-performance-improvement-plan-data"></a>Arquivo CSV para dados do plano de melhoria de desempenho

Veja um exemplo de um arquivo CSV para os dados dos dados do plano de melhoria de desempenho.

```text
EmailAddress,EffectiveDate,ImprovementRemarks,PerformanceRating
sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,Met expectation but bad attitude,2-Below expectation
pillar@contoso.com,2019-04-23T15:18:02.4675041+05:30, Multiple conflicts with the team
```

A tabela a seguir descreve cada coluna no arquivo CSV para dados de revisão de desempenho.

| **Coluna**| **Descrição**|
|:----------|:---------------|
| **EmailAddress**  | Especifica o endereço de email do usuário (UPN).|
| **EffectiveDate** | Especifica a data em que o usuário foi oficialmente informado sobre o plano de melhoria de desempenho. Você deve usar o seguinte formato de data: `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm` , que é o [formato de data e hora ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html).|
| **Comentários**| Especifica qualquer comentários que o avaliador forneceu sobre o plano de melhoria de desempenho. Este é um parâmetro de texto com um limite de 200 caracteres. Esse é um parâmetro opcional. Você não precisa incluí-lo no arquivo CSV. |
| **Classificação**| Especifica qualquer classificação ou outras informações relacionadas à avaliação de desempenho. plano de melhoria de desempenho. Este é um parâmetro de texto e pode conter qualquer texto de forma livre que sua organização usa para reconhecer a avaliação. Por exemplo, "3 expectativas atendidas" ou "2 abaixo da média". Este é um parâmetro de texto com limite de 25 caracteres. Esse é um parâmetro opcional. Você não precisa incluí-lo no arquivo CSV.|
|||

### <a name="determining-how-many-csv-files-to-use-for-hr-data"></a>Determinar quantos arquivos CSV usar para dados de RH

Na etapa 3, você pode optar por criar conectores separados para cada tipo de dados de RH ou pode optar por criar um único conector para todos os tipos de dados. Você pode usar arquivos CSV separados que contenham dados para um cenário de RH (como os exemplos dos arquivos CSV descritos nas seções anteriores). Como alternativa, você pode usar um único arquivo CSV que contém dados para dois ou mais cenários de RH. Aqui estão algumas diretrizes para ajudá-lo a determinar quantos arquivos CSV usar para dados de RH.

- Se a política de gerenciamento de risco do insider que você deseja implementar requer vários tipos de dados de RH, considere usar um único arquivo CSV que contenha todos os tipos de dados necessários.

- O método para gerar ou coletar os dados de RH pode determinar o número de arquivos CSV. Por exemplo, se os diferentes tipos de dados de RH usados para configurar um conector de RH estão localizados em um único sistema de RH em sua organização, então você poderá exportar os dados para um único arquivo CSV. Mas se os dados forem distribuídos entre sistemas de RH diferentes, talvez seja mais fácil exportar dados para arquivos CSV diferentes. Por exemplo, os dados de demissão de funcionários podem estar localizados em um sistema de RH diferente do nível de trabalho ou dados de avaliação de desempenho. Nesse caso, talvez seja mais fácil ter arquivos CSV separados em vez de ter que combinar manualmente os dados em um único arquivo CSV. Portanto, o modo como você recupera ou exporta dados de seus sistemas de RH pode determinar como o número de arquivos CSV que você precisará.

- Como regra geral, o número de conectores de RH que você precisará criar é determinado pelos tipos de dados em um arquivo CSV. Por exemplo, se um arquivo CSV contiver todos os tipos de dados necessários para suportar sua implementação de gerenciamento de risco do Insider, você só precisará de um conector de RH. Porém, se você tiver dois arquivos CSV separados que contenham um único tipo de dados, será necessário criar dois conectores de RH. Uma exceção é que, se você adicionar uma coluna **HRScenario** a um arquivo CSV (consulte a próxima seção), você pode configurar um único conector de RH que possa processar diferentes arquivos CSV.

### <a name="configuring-a-single-csv-file-for-multiple-hr-data-types"></a>Configurando um único arquivo CSV para vários tipos de dados de RH

Você pode adicionar vários tipos de dados de RH a um único arquivo CSV. Isso é útil se a solução de gerenciamento de risco do insider que você está implementando requer vários tipos de dados de RH ou se os tipos de dados estão localizados em um único sistema de RH em sua organização. Ter menos arquivos CSV sempre permite que você tenha menos conectores de RH para criar e gerenciar.

Aqui estão os requisitos para configurar um arquivo CSV com vários tipos de dados:

- Você precisa adicionar as colunas obrigatórias (e opcional se as usar) para cada tipo de dados e o nome de coluna correspondente na linha de cabeçalho. Se um tipo de dados não corresponder a uma coluna, você poderá deixar o valor em branco.

- Para usar um arquivo CSV com vários tipos de dados de RH, o conector de RH precisa saber quais linhas no arquivo CSV contêm que tipo de dados de RH. Isso é feito adicionando uma coluna **HRScenario** adicional ao arquivo CSV. Os valores nesta coluna identificam o tipo de dados de RH em cada linha. Por exemplo, os valores que correspondem aos quatro cenários de RH podem ser \` desistência \` , \` alteração no nível \` de trabalho, \` revisão \` de desempenho e plano de melhoria de \` desempenho \` .

- Se você tiver vários arquivos CSV que contenham uma coluna HRScenario * *, certifique-se de que cada arquivo use o mesmo nome de coluna e os mesmos valores que identifiquem os cenários de RH específicos.

O exemplo a seguir mostra um arquivo CSV que contém a coluna **HRScenario** . Os valores na coluna HRScenario identificam o tipo de dados na linha correspondente.

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
> Você pode usar qualquer nome para a coluna que identifica o tipo de dados de RH, pois você irá mapear o nome da coluna no arquivo CSV como a coluna que identifica o tipo de dados de RH ao configurar o conector na etapa 3. Você também mapeará os valores usados para a coluna tipo de dados ao configurar o conector.

### <a name="adding-the-hrscenario-column-to-a-csv-file-that-contains-a-single-data-type"></a>Adicionar a coluna HRScenario a um arquivo CSV que contém um único tipo de dados

Com base nos sistemas de RH da sua organização e como você irá exportar dados de RH para o arquivo CSV, talvez seja necessário criar vários arquivos CSV que contenham um único tipo de dados de RH. Nesse caso, você ainda pode criar um único conector de RH para importar dados de arquivos CSV diferentes. Para fazer isso, basta adicionar uma coluna HRScenario ao arquivo CSV e especificar o tipo de dados HR. Em seguida, você pode executar o script para cada arquivo CSV, mas usar a mesma ID de trabalho para o conector. Consulte a [etapa 4](#step-4-run-the-sample-script-to-upload-your-hr-data).

## <a name="step-2-create-an-app-in-azure-active-directory"></a>Etapa 2: criar um aplicativo no Azure Active Directory

A próxima etapa é criar e registrar um novo aplicativo no Azure Active Directory (Azure AD). O aplicativo corresponderá ao conector de RH que você criou na etapa 3. A criação deste aplicativo permitirá que o Azure AD autentique o conector de RH quando executado e tente acessar sua organização. Este aplicativo também será usado para autenticar o script executado na etapa 4 para carregar seus dados de RH na nuvem da Microsoft. Durante a criação deste aplicativo do Azure AD, certifique-se de salvar as informações a seguir. Esses valores serão usados na etapa 3 e na etapa 4.

- ID de aplicativo do Azure AD (também chamada de *ID do aplicativo* ou *ID do cliente*)

- Segredo do aplicativo do Azure AD (também chamado de *segredo do cliente*)

- ID do locatário (também chamado de *ID de diretório*)

Para obter instruções detalhadas sobre a criação de um aplicativo no Azure AD, consulte [registrar um aplicativo com a plataforma de identidade da Microsoft](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).

## <a name="step-3-create-the-hr-connector"></a>Etapa 3: criar o conector de RH

A próxima etapa é criar um conector de RH no centro de conformidade da Microsoft 365. Depois de executar o script na etapa 4, o conector de RH que você cria receberá os dados de RH do arquivo CSV para sua organização do Microsoft 365. Antes de criar um conector, certifique-se de ter uma lista dos cenários de RH e os nomes de coluna CSV correspondentes para cada um. Você deve mapear os dados necessários para cada cenário para os nomes de coluna reais no seu arquivo CSV ao configurar o conector. Como alternativa, você pode carregar um arquivo CSV de exemplo ao configurar o conector e o assistente o ajudará a mapear o nome das colunas para os tipos de dados necessários.

Depois de concluir esta etapa, certifique-se de copiar o ID do trabalho que é gerado quando você cria o conector. Você usará a ID do trabalho ao executar o script.

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com/) e clique em **conectores de dados** no painel de navegação esquerdo.

2. Na página **conectores de dados** em **RH**, clique em **Exibir**.

3. Na página **personalizada de RH** , clique em **Adicionar conector**.

4. Na página **Configurar a conexão** , faça o seguinte e clique em **Avançar**:

   a. Digite ou cole a ID de aplicativo do Azure AD para o aplicativo do Azure que você criou na etapa 2.

   b. Digite um nome para o conector de RH.

5. Na página cenários de RH, selecione um ou mais cenários de RH para os quais você deseja importar dados e, em seguida, clique em **Avançar**.

6. Na página método de mapeamento de arquivos, selecione uma das opções a seguir e clique em **Avançar**.

   - **Carregar um arquivo de exemplo**. Se você selecionar essa opção, clique em **carregar arquivo de exemplo** para carregar o arquivo CSV que você preparou na etapa 1. Essa opção permite que você selecione rapidamente nomes de coluna no arquivo CSV de uma lista suspensa para mapeá-los para os tipos de dados dos cenários de RH selecionados anteriormente.

   OU

   - **Forneça manualmente os detalhes do mapeamento**. Se você selecionar essa opção, será necessário digitar o nome das colunas no arquivo CSV para mapeá-las para os tipos de dados dos cenários de RH selecionados anteriormente.

7. Na página detalhes do mapeamento de arquivos, execute um dos seguintes procedimentos, dependendo se você carregou um arquivo CSV de exemplo e se está configurando o conector para um único cenário de RH ou para vários cenários. Se você carregou um arquivo de exemplo, não precisará digitar os nomes das colunas. Você os escolhe em uma lista suspensa.

    - Se você selecionou um cenário de RH único na etapa anterior, digite os nomes de cabeçalho de coluna (também chamados de *parâmetros*) do arquivo CSV que você criou na etapa 1 em cada uma das caixas apropriadas. Os nomes de coluna que você digita não diferenciam maiúsculas de minúsculas, mas não se esqueça de incluir espaços se os nomes de coluna no arquivo CSV incluírem espaços. Como explicado anteriormente, os nomes digitados nessas caixas devem coincidir com os nomes de parâmetro no arquivo CSV. Por exemplo, a captura de tela a seguir mostra os nomes de parâmetro do arquivo CSV de exemplo para o cenário de renovação de RH do funcionário mostrado na etapa 1.

    - Se você tiver selecionado vários tipos de dados na etapa acima, precisará inserir o nome de coluna de identificador que identificará o tipo de dados de RH no arquivo CSV. Depois de inserir o nome da coluna identificador, digite o valor que identifica esse tipo de dados de RH e digite os nomes de cabeçalho de coluna para tipos de dados selecionados dos arquivos CSV que você criou na etapa 1 em cada uma das caixas apropriadas para cada tipo de dados selecionado. Como explicado anteriormente, os nomes digitados nessas caixas devem coincidir com os nomes de coluna no arquivo CSV.

8. Na página **revisão** , revise suas configurações e clique em **concluir** para criar o conector.

   Uma página de status é exibida para confirmar que o conector foi criado. Esta página contém duas coisas importantes que você precisa para concluir a próxima etapa para executar o script de exemplo para carregar seus dados de RH.

   ![Consultar a página com ID do trabalho e vincular ao GitHub para obter o script de exemplo](../media/HRConnector_Confirmation.png)

   a. **ID de trabalho.** Você precisará dessa ID de trabalho para executar o script na próxima etapa. Você pode copiá-lo desta página ou da página do submenu conector.

   b. **Link para script de amostra.** Clique no link **aqui** para ir para o site do GitHub para acessar o script de exemplo (o link abre uma nova janela). Mantenha essa janela aberta para que você possa copiar o script na etapa 4. Como alternativa, é possível indicar o destino ou copiar a URL para que você possa acessá-la novamente quando executar o script. Este link também está disponível na página do submenu conector.

9. Clique em **Concluído**.

   O novo conector é exibido na lista na guia **conectores** .

10. Clique no conector de RH que você acabou de criar para exibir a página de submenu, que contém propriedades e outras informações sobre o conector.

   ![Página de menu do novo conector de RH](../media/HRConnectorWizard7.png)

Se ainda não tiver feito isso, você poderá copiar os valores para a **ID do aplicativo do Azure** e a **ID do trabalho do conector**. Você precisará deles para executar o script na próxima etapa. Você também pode baixar o script da página do menu de atalho (ou baixá-lo usando o link na próxima etapa.)

Você também pode clicar em **Editar** para alterar a ID do aplicativo do Azure ou os nomes de cabeçalho de coluna definidos na página **mapeamento de arquivo** .

## <a name="step-4-run-the-sample-script-to-upload-your-hr-data"></a>Etapa 4: executar o script de exemplo para carregar seus dados de RH

A última etapa na configuração de um conector de RH é executar um script de exemplo que irá carregar os dados de RH no arquivo CSV (que você criou na etapa 1) para a nuvem da Microsoft. Especificamente, o script carrega os dados para o conector de RH. Depois de executar o script, o conector de RH que você criou na etapa 3 importa os dados de RH para a sua organização do Microsoft 365, onde pode ser acessado por outras ferramentas de conformidade, como a solução de gerenciamento de risco do insider. Depois de executar o script, considere agendar uma tarefa para executá-la automaticamente, de modo que os dados de encerramento de funcionários mais atuais sejam carregados para a nuvem da Microsoft. Confira [agendar o script para ser executado automaticamente](#optional-step-6-schedule-the-script-to-run-automatically).

1. Vá para a janela que você deixou de abrir da etapa anterior para acessar o site do GitHub com o script de exemplo. Como alternativa, abra o site marcado ou use a URL que você copiou.

2. Clique no botão **RAW** para exibir o script no modo de exibição de texto.

3. Copie todas as linhas no script de exemplo e salve-as em um arquivo de texto.

4. Modifique o script de exemplo para sua organização, se necessário.

5. Salve o arquivo de texto como um arquivo de script do Windows PowerShell usando um sufixo de nome de arquivo `.ps1` ; por exemplo, `HRConnector.ps1` .

6. Abra um prompt de comando no computador local e vá para o diretório onde você salvou o script.

7. Execute o seguinte comando para carregar os dados de RH no arquivo CSV para a nuvem da Microsoft; por exemplo:

    ```powershell
    .\HRConnector.ps1 -tenantId <tenantId> -appId <appId>  -appSecret <appSecret>  -jobId <jobId>  -csvFilePath '<csvFilePath>'
    ```

   A tabela a seguir descreve os parâmetros a serem usados com esse script e seus valores necessários. As informações obtidas nas etapas anteriores são usadas nos valores desses parâmetros.

   |**Parâmetro**|**Descrição**
   |:-----|:-----|:-----|
   |`tenantId`|Esta é a ID da sua organização do Microsoft 365 que você obteve na etapa 2. Você também pode obter a ID do locatário para sua organização na folha **visão geral** no centro de administração do Azure AD. Isso é usado para identificar sua organização.|
   |`appId` |Esta é a ID de aplicativo do Azure AD para o aplicativo que você criou no Azure AD na etapa 2. Isso é usado pelo Azure AD para autenticação quando o script tenta acessar sua organização do Microsoft 365. | 
   |`appSecret`|Este é o segredo do aplicativo do Azure AD para o aplicativo que você criou no Azure AD na etapa 2. Isso também é usado para autenticação.|
   |`jobId`|Esta é a ID do trabalho do conector de RH que você criou na etapa 3. Isso é usado para associar os dados de RH que são carregados para a nuvem da Microsoft com o conector de RH.|
   |`csvFilePath`|Este é o caminho do arquivo para o arquivo CSV (armazenado no mesmo sistema que o script) que você criou na etapa 1. Tente evitar espaços no caminho do arquivo; caso contrário, use aspas simples.|
   |||

   Veja um exemplo da sintaxe do script do conector de RH usando valores reais para cada parâmetro:

   ```powershell
    .\HRConnector.ps1 -tenantId d5723623-11cf-4e2e-b5a5-01d1506273g9 -appId 29ee526e-f9a7-4e98-a682-67f41bfd643e -appSecret MNubVGbcQDkGCnn -jobId b8be4a7d-e338-43eb-a69e-c513cd458eba -csvFilePath 'C:\Users\contosoadmin\Desktop\Data\employee_termination_data.csv'
    ```

   Se o upload for bem-sucedido, o script exibirá a mensagem de **upload bem-sucedida** .

   > [!NOTE]
   > Se você tiver problemas para executar o comando anterior por causa das políticas de execução, consulte [sobre políticas de execução](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies) e [Set-ExecutionPolicy](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy) para obter orientação sobre como configurar as políticas de execução.

## <a name="step-5-monitor-the-hr-connector"></a>Etapa 5: monitorar o conector de RH

Depois de criar o conector de RH e executar o script para carregar seus dados de RH, você pode exibir o conector e o status de upload no centro de conformidade da Microsoft 365. Se você agendar o script para ser executado automaticamente regularmente, também poderá exibir o status atual após a última vez que o script foi executado.

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com) e clique em **conectores de dados** no painel de navegação esquerdo.

2. Clique na guia **conectores** e selecione o conector de RH para exibir a página de submenu, que contém as propriedades e informações sobre o conector.

   ![Página de submenu do conector de RH com propriedades e status](../media/HRConnectorFlyout1.png)

3. Em **andamento**, clique no link **baixar log** para abrir (ou salvar) o log de status do conector. Esse log contém informações sobre cada vez que o script é executado e carrega os dados do arquivo CSV para a nuvem da Microsoft. 

   ![Arquivo de log do conector de RH exibe linhas de número do arquivo CSV que foram carregadas](../media/HRConnectorLogFile.png)

   O `RecordsSaved` campo indica o número de linhas no arquivo CSV que foram carregadas. Por exemplo, se o arquivo CSV contiver quatro linhas, o valor dos `RecordsSaved` campos será 4, se o script tiver carregado com êxito todas as linhas no arquivo CSV.

Se você não tiver executado o script na etapa 4, um link para baixar o script será exibido em **última importação**. Você pode baixar o script e seguir as etapas para executar o script.

## <a name="optional-step-6-schedule-the-script-to-run-automatically"></a>Opcion Etapa 6: agendar o script para ser executado automaticamente

Para verificar se os dados de RH mais recentes da sua organização estão disponíveis para ferramentas como a solução de gerenciamento de risco do Insider, recomendamos agendar o script para ser executado automaticamente de forma recorrente, como uma vez por dia. Isso também exige que você atualize os dados de RH no arquivo CSV de forma semelhante (se não o mesmo), para que ele contenha as informações mais recentes sobre funcionários que saem da sua organização. O objetivo é carregar os dados de RH mais atuais para que o conector de RH possa disponibilizá-lo para a solução de gerenciamento de risco do insider.

Você pode fazer com que o aplicativo Agendador de tarefas do Windows execute o script automaticamente todos os dias.

1. No computador local, clique no botão **Iniciar** do Windows e digite **Agendador de tarefas**.

2. Clique no aplicativo **Agendador de tarefas** para abri-lo.

3. Na seção **ações** , clique em **criar tarefa**.

4. Na guia **geral** , digite um nome descritivo para a tarefa agendada; por exemplo, **script do conector de RH**. Você também pode adicionar uma descrição opcional.

5. Em **Opções de segurança**, faça o seguinte:

   a. Determine se o script deve ser executado somente quando você estiver conectado ao computador ou executá-lo quando estiver conectado ou não.

   b. Verifique se a caixa de seleção **executar com os privilégios mais altos** está selecionada.

6. Selecione a guia **acionadores** , clique em **novo**e faça o seguinte:

   a. Em **configurações**, selecione a opção **diariamente** e, em seguida, escolha uma data e hora para executar o script pela primeira vez. O script será todos os dias no mesmo horário especificado.

   b. Em **Configurações avançadas**, certifique-se de que a caixa de seleção **habilitado** esteja marcada.

   c. Clique em **OK**.

7. Selecione a guia **ações** , clique em **novo**e faça o seguinte:

   ![Configurações de ação para criar uma nova tarefa agendada para o script do conector de RH](../media/HRConnectorScheduleTask1.png)

   a. Na lista suspensa **ação** , verifique se **Iniciar um programa** está selecionado.

   b. Na caixa **programa/script** , clique em **procurar**e vá para o local a seguir e selecione-o para que o caminho seja exibido na caixa: `C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe` .

   c. Na caixa **adicionar argumentos (opcional)** , Cole o mesmo comando de script executado na etapa 4. Por exemplo, `.\HRConnector.ps1 -tenantId "d5723623-11cf-4e2e-b5a5-01d1506273g9" -appId "c12823b7-b55a-4989-faba-02de41bb97c3" -appSecret "MNubVGbcQDkGCnn"  -jobId "e081f4f4-3831-48d6-7bb3-fcfab1581458" -csvFilePath "C:\Users\contosoadmin\Desktop\Data\employee_termination_data.csv"`

   d. Na caixa **Iniciar em (opcional)** , Cole o local da pasta do script executado na etapa 4. Por exemplo, `C:\Users\contosoadmin\Desktop\Scripts`.

   e. Clique em **OK** para salvar as configurações da nova ação.

8. Na janela **criar tarefa** , clique em **OK** para salvar a tarefa agendada. Você pode ser solicitado a inserir suas credenciais de conta de usuário.

   A nova tarefa é exibida na biblioteca do Agendador de tarefas.

   ![A nova tarefa é exibida na biblioteca do Agendador de tarefas](../media/HRConnectorTaskSchedulerLibrary.png)

   A última vez em que o script foi executado e a próxima vez em que ele está agendado para ser executado é exibida. Você pode clicar duas vezes na tarefa para editá-la.

   Você também pode verificar a última vez que o script foi executado na página de submenu do respectivo conector de RH no centro de conformidade.

## <a name="existing-hr-connectors"></a>Conectores de RH existentes

No dia 20 de julho de 2020, lançamos outros cenários suportados pelos conectores de RH. Estes são os cenários de RH descritos anteriormente neste artigo. Todos os conectores de RH criados antes dessa data só dão suporte ao cenário de demissão de funcionários. Se você criou um conector de RH antes de 20 de julho de 2020, nós o migramos para que ele continue migrar seus dados de RH para a nuvem da Microsoft. Você não precisa fazer nada para manter essa funcionalidade. Você pode continuar usando o conector sem qualquer interrupção.

Se você quiser implementar cenários de RH adicionais, crie um novo conector de RH e configure-o para os cenários de RH adicionais lançados. Você também precisará criar um ou mais arquivos CSV novos que contenham os dados para dar suporte aos cenários de RH adicionais. Após criar um novo conector de RH, execute o script usando a ID do trabalho do novo conector e arquivo (s) CSV com os dados dos cenários de RH adicionais.
