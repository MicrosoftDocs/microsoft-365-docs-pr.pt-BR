---
title: Configurar um conector para importar dados de RH para a nuvem do Governo dos Eua
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
ROBOTS: NOINDEX, NOFOLLOW
description: Os administradores na nuvem do Governo dos Estados Unidos podem configurar um conector de dados para importar dados de funcionários do sistema de recursos humanos (RH) de sua organização para o Microsoft 365. Isso permite que você use dados de RH em políticas de gerenciamento de riscos internos para ajudá-lo a detectar atividades de usuários específicos que podem representar uma ameaça interna à sua organização.
ms.openlocfilehash: 80998422eba32fe7f9118166f76a61d2d4bd8894
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "49619917"
---
# <a name="set-up-a-connector-to-import-hr-data-in-us-government"></a>Configurar um conector para importar dados de RH no Governo dos Estados Unidos

Você pode configurar um conector de dados no centro de conformidade do Microsoft 365 para importar dados de recursos humanos (RH) para sua organização do Governo dos Eua. Os dados relacionados ao RH incluem a data em que um funcionário enviou seu pedido e a data do último dia do funcionário. Esses dados de RH podem ser usados por soluções de proteção de informações da Microsoft, como a solução de gerenciamento de riscos [interno,](insider-risk-management.md)para ajudar a proteger sua organização contra atividades mal-intencionadas ou roubo de dados dentro da sua organização. Configurar um conector de RH consiste em criar um aplicativo no Azure Active Directory usado para autenticação por conector, criar um arquivo de mapeamento CSV que contenha seus dados de RH, criar um conector de dados no centro de conformidade e executar um script (agendado) que ingere os dados de RH no arquivo CSV para a nuvem da Microsoft. Em seguida, o conector de dados é usado pela ferramenta de gerenciamento de riscos interno para acessar os dados de RH que foram importados para sua organização do Microsoft 365 US Government.

## <a name="before-you-begin"></a>Antes de começar

- O usuário que cria o conector de RH na Etapa 3 deve receber a função Importar Exportar Caixa de Correio no Exchange Online. Por padrão, essa função não é atribuída a nenhum grupo de funções no Exchange Online. Você pode adicionar a função Importar Exportar Caixa de Correio ao grupo de função Gerenciamento da Organização no Exchange Online. Ou você pode criar um novo grupo de função, atribuir a função Importar Exportar Caixa de Correio e adicionar os usuários apropriados como membros. Para obter mais informações, consulte [](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) as [seções](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) Criar grupos de função ou Modificar grupos de função no artigo "Gerenciar grupos de função no Exchange Online".

- Você precisará determinar como recuperar ou exportar os dados do sistema de RH da sua organização (regularmente) e adicioná-los ao arquivo CSV descrito na Etapa 2. O script executado na Etapa 4 carregará os dados de RH no arquivo CSV para a nuvem da Microsoft.

- O script de exemplo executado na Etapa 4 carregará dados de RH na nuvem da Microsoft para que eles possam ser usados por outras ferramentas da Microsoft, como a solução de gerenciamento de riscos insider. Este script de exemplo não tem suporte em nenhum serviço ou programa de suporte padrão da Microsoft. O script de amostra é fornecido COMO ESTÁ, sem garantia de nenhum tipo. A Microsoft também se isenta de todas as garantias implícitas, incluindo, sem limitação, quaisquer garantias implícitas de comercialização ou adequação a uma finalidade específica. Todo o risco decorrente do uso ou desempenho do script de amostra e da documentação permanece com você. De modo algum a Microsoft, seus autores ou qualquer outra pessoa envolvida na criação, produção ou veiculação dos scripts serão considerados responsáveis por quaisquer danos (incluindo sem limitações danos por perda de lucros comerciais, interrupção de negócios, perda de informações comerciais ou outras perdas pecuniárias) resultantes do uso ou da incapacidade de uso da documentação ou scripts de exemplo, mesmo que a Microsoft tenha sido alertada sobre a possibilidade de tais danos.

## <a name="step-1-create-an-app-in-azure-active-directory"></a>Etapa 1: Criar um aplicativo no Azure Active Directory

A primeira etapa é criar e registrar um novo aplicativo no Azure Active Directory (Azure AD). O aplicativo corresponderá ao conector de RH criado na Etapa 3. A criação desse aplicativo permitirá que o Azure AD autenture o conector de RH quando ele for executado e tentar acessar sua organização. Esse aplicativo também será usado para autenticar o script executado na Etapa 4 para carregar seus dados de RH na nuvem da Microsoft. Durante a criação desse aplicativo do Azure AD, certifique-se de salvar as informações a seguir. Esses valores serão usados em etapas posteriores.

- ID do aplicativo Azure AD (também chamada de *ID do aplicativo* ou *ID do cliente)*

- Segredo do aplicativo Azure AD (também chamado de *segredo do cliente)*

- ID do locatário (também chamada de *ID de diretório)*

Para obter instruções passo a passo para criar um aplicativo no Azure AD, confira Registrar um aplicativo com a [Plataforma de Identidade da Microsoft.](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app)

## <a name="step-2-prepare-a-csv-file-with-your-hr-data"></a>Etapa 2: Preparar um arquivo CSV com seus dados de RH

A próxima etapa é criar um arquivo CSV que contenha informações sobre funcionários que deixaram sua organização. Conforme explicado na seção Antes de Começar, você precisará determinar como gerar esse arquivo CSV a partir do sistema de RH da sua organização. O exemplo a seguir mostra um arquivo CSV concluído (aberto no Bloco de Notas) que contém os três parâmetros necessários (colunas). É muito mais fácil editar o arquivo CSV no Microsoft Excel.

```text
EmailAddress,TerminationDate,LastWorkingDate
sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,2019-04-29T15:18:02.4675041+05:30
pilarp@contoso.com,2019-04-24T09:15:49Z,2019-04-29T15:18:02.7117540
```

A primeira linha, ou linha de título, do arquivo CSV lista os nomes de coluna necessários. O nome usado em cada header de coluna é você (os nomes usados no exemplo anterior são sugestões). No entanto, os mesmos nomes de coluna  que você usa no arquivo CSV devem ser especificados quando você cria o conector de RH na Etapa 3. Não inclua espaços nos nomes das colunas.

A tabela a seguir descreve cada coluna no arquivo CSV:

| Nome da coluna | Descrição |
|:-----|:-----|
| **EmailAddress** <br/> |Especifica o endereço de email do funcionário encerrado.|
| **TerminationDate** <br/> |Especifica a data em que o emprego da pessoa foi encerrado oficialmente em sua organização. Por exemplo, essa pode ser a data em que o funcionário deu um aviso sobre como sair da sua organização. Essa data pode ser diferente da data do último dia de trabalho da pessoa. Use o seguinte formato de data: , que é o formato de data e hora `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm` [ISO 8601.](https://www.iso.org/iso-8601-date-and-time-format.html)|
|**LastWorkingDate**|Especifica o último dia de trabalho do funcionário encerrado. Use o seguinte formato de data: , que é o formato de data e hora `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm` [ISO 8601.](https://www.iso.org/iso-8601-date-and-time-format.html)|
|||

Depois de criar o arquivo CSV com os dados de RH necessários, armazene-o no mesmo sistema que o script executado na Etapa 4. Implemente uma estratégia de atualização para que o arquivo CSV sempre contenha as informações mais atuais. Isso garante que, independentemente do que você executar o script, os dados mais atuais de rescisão de funcionários sejam carregados na nuvem da Microsoft.

## <a name="step-3-create-the-hr-connector"></a>Etapa 3: Criar o conector de RH

A próxima etapa é criar um conector de RH no centro de conformidade do Microsoft 365. Depois de executar o script na Etapa 4, o conector de RH criado ingeri os dados de RH do arquivo CSV para sua organização do Microsoft 365. Nesta etapa, copie a ID de trabalho gerada ao criar o conector. Você usará a ID do trabalho quando executar o script.

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com) e clique em **Conectores de dados** na barra de entrada esquerda.

2. Na página **Conectores de dados** em **RH,** clique em **Exibir.**

3. Na página **RH,** clique em **Adicionar conector.**

4. Na página **Credenciais de autenticação,** faça o seguinte e clique em **Next:**

   1. Digite ou colar a ID de aplicativo do Azure AD para o aplicativo do Azure que você criou na Etapa 1.

   1. Digite um nome para o conector de RH.

5. Na **página** Mapeamento de arquivos, digite os nomes dos três headers de coluna (também chamados de *parâmetros)* do arquivo CSV que você criou na Etapa 2 em cada uma das caixas apropriadas. Os nomes não são sensíveis a minúsculas. Conforme explicado anteriormente, os nomes digitados nessas caixas devem corresponder aos nomes dos parâmetros no arquivo CSV. Por exemplo, a captura de tela a seguir mostra os nomes dos parâmetros do exemplo no arquivo CSV de exemplo mostrado na Etapa 2.

   ![Os nomes dos títulos de colunas são os que estão no arquivo CSV](../media/HRConnectorWizard3.png)

6. Na página **Revisão,** revise suas configurações e clique em **Concluir** para criar o conector.

   Uma página de status é exibida confirmando que o conector foi criado. Esta página contém duas coisas importantes que você precisa para concluir a próxima etapa para executar o script de exemplo para carregar seus dados de RH.

   ![Review page with job ID and link to github for sample script](../media/HRConnector_Confirmation.png)

   1. **ID do trabalho.** Você precisará dessa ID de trabalho para executar o script na próxima etapa. Você pode copiá-lo desta página ou da página do flyout do conector.
   
   1. **Link para script de exemplo.** Clique no link **aqui** para acessar o site do GitHub para acessar o script de exemplo (o link abre uma nova janela). Mantenha essa janela aberta para que você possa copiar o script na Etapa 4. Como alternativa, você pode marcar o destino ou copiar a URL para poder acessá-la novamente na Etapa 4. Esse link também está disponível na página do flyout do conector.

7. Clique em **Concluído**.

   O novo conector é exibido na lista na guia **Conectores.** 

8. Clique no conector de RH que você acabou de criar para exibir a página do flyout, que contém propriedades e outras informações sobre o conector.

   ![Página de flyout para novo conector de RH](../media/HRConnectorWizard7.png)

   Caso ainda não tenha feito isso, você pode copiar os valores para a ID de aplicativo do **Azure** e a ID do trabalho **do Conector.** Você precisará deles para executar o script na próxima etapa. Você também pode baixar o script da página do flyout (ou baixá-lo usando o link na próxima etapa).)

   Você também pode clicar **em Editar** para alterar a ID do Aplicativo do Azure ou os nomes de header de coluna definidos na página mapeamento **de** arquivo.

## <a name="step-4-run-the-sample-script-to-upload-your-hr-data"></a>Etapa 4: Execute o script de exemplo para carregar seus dados de RH

A última etapa na configuração de um conector de RH é executar um script de exemplo que carregará os dados de RH no arquivo CSV (criado na Etapa 2) para a nuvem da Microsoft. Especificamente, o script carrega os dados para o conector de RH. Depois de executar o script, o conector de RH criado na Etapa 3 importa os dados de RH para sua organização do Microsoft 365, onde ele pode ser acessado por outras ferramentas de conformidade, como a solução de gerenciamento de riscos do Insider. Depois de executar o script, considere agendar uma tarefa para executar automaticamente diariamente para que os dados mais atuais de rescisão de funcionários seja carregados na nuvem da Microsoft. Consulte [Agendar o script para ser executado automaticamente.](#optional-step-6-schedule-the-script-to-run-automatically)

1. Vá para a janela que você deixou aberta na etapa anterior para acessar o site do GitHub com o script de exemplo. Como alternativa, abra o site marcado ou use a URL que você copiou.

2. Clique no **botão Bruto** para exibir o script na exibição de texto.

3. Copie todas as linhas do script de exemplo e salve-as em um arquivo de texto.

4. Modifique o script de exemplo para sua organização, se necessário.

5. Salve o arquivo de texto como um arquivo de script do Windows PowerShell usando um sufixo de nome de `.ps1` arquivo de ; por exemplo, `HRConnector.ps1` .

6. Abra um Prompt de Comando no computador local e vá para o diretório onde você salvou o script.

7. Execute o seguinte comando para carregar os dados de RH no arquivo CSV para a nuvem da Microsoft; por exemplo:

    ```powershell
    .\HRConnector.ps1 -tenantId <tenantId> -appId <appId>  -appSecret <appSecret>  -jobId <jobId>  -csvFilePath '<csvFilePath>'
    ```

   A tabela a seguir descreve os parâmetros a usar com esse script e seus valores obrigatórios. As informações obtidas nas etapas anteriores são usadas nos valores desses parâmetros.

   | Parâmetro | Descrição |
   |:-----|:-----|:-----|
   |`tenantId`|A ID da sua organização do Microsoft 365 obtida na Etapa 1. Você também pode obter a ID de locatário para sua organização na folha **Visão** geral no centro de administração do Azure AD. Isso é usado para identificar sua organização.|
   |`appId` |A ID de aplicativo do Azure AD para o aplicativo que você criou no Azure AD na Etapa 1. Isso é usado pelo Azure AD para autenticação quando o script tenta acessar sua organização do Microsoft 365. |
   |`appSecret`|O segredo do aplicativo do Azure AD para o aplicativo que você criou no Azure AD na Etapa 1. Isso também é usado para autenticação.|
   |`jobId`|A ID do trabalho para o conector de RH que você criou na Etapa 3. Isso é usado para associar os dados de RH carregados na nuvem da Microsoft com o conector de RH.|
   |`csvFilePath`|O caminho do arquivo CSV (armazenado no mesmo sistema que o script) que você criou na Etapa 2. Tente evitar espaços no caminho do arquivo; caso contrário, use aspas simples.|
   |||
   
   Aqui está um exemplo da sintaxe para o script do conector DE RH usando valores reais para cada parâmetro:

   ```powershell
    .\HRConnector.ps1 -tenantId d5723623-11cf-4e2e-b5a5-01d1506273g9 -appId 29ee526e-f9a7-4e98-a682-67f41bfd643e -appSecret MNubVGbcQDkGCnn -jobId b8be4a7d-e338-43eb-a69e-c513cd458eba -csvFilePath 'C:\Users\contosoadmin\Desktop\Data\employee_termination_data.csv'
    ```

   Se o carregamento for bem-sucedido, o script exibirá a **mensagem Carregar Com** Êxito.

   > [!NOTE]
   > Se você tiver problemas ao executar o comando anterior devido a políticas de execução, consulte [Sobre](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies) políticas de execução e [Set-ExecutionPolicy](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy) para obter orientação sobre como definir políticas de execução.

## <a name="step-5-monitor-the-hr-connector"></a>Etapa 5: Monitorar o conector de RH

Depois de criar o conector de RH e executar o script para carregar seus dados de RH, você pode exibir o conector e carregar o status no centro de conformidade do Microsoft 365. Se você agendar o script para ser executado automaticamente regularmente, também poderá exibir o status atual após a última vez em que o script foi executado.

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com) e clique **em Conectores de dados** na barra de entrada esquerda.

2. Clique na **guia Conectores** e selecione o conector de RH para exibir a página do flyout. Esta página contém as propriedades e informações sobre o conector.

   ![Página do flyout do conector de RH com propriedades e status](../media/HRConnectorFlyout1.png)

3. Em **Progresso,** clique no link **Baixar log** para abrir (ou salvar) o log de status do conector. Esse log contém informações sobre cada vez que o script é executado e carrega os dados do arquivo CSV para a nuvem da Microsoft. 

   ![O arquivo de log do conector de RH exibe linhas de número do arquivo CSV que foram carregadas](../media/HRConnectorLogFile.png)

   O `RecordsSaved` campo indica o número de linhas no arquivo CSV carregado. Por exemplo, se o arquivo CSV contiver quatro linhas, o valor dos campos será 4, se o script tiver carregado com êxito todas as linhas no `RecordsSaved` arquivo CSV.

Se você ainda não tiver executado o script na Etapa 4, um link para baixar o script será exibido em **Última importação.** Você pode baixar o script e seguir as etapas na Etapa 4 para executar o script.

## <a name="optional-step-6-schedule-the-script-to-run-automatically"></a>(Opcional) Etapa 6: Agendar o script para ser executado automaticamente

Para garantir que os dados de RH mais recentes da sua organização estão disponíveis para ferramentas como a solução de gerenciamento de riscos insider, recomendamos que você agende o script para ser executado automaticamente de forma recorrente, como uma vez por dia. Isso também requer que você atualize os dados de RH no arquivo CSV em um agendamento semelhante (se não o mesmo) para que ele contenha as informações mais recentes sobre os funcionários que saem da sua organização. O objetivo é carregar os dados de RH mais atuais para que o conector de RH possa torná-los disponíveis para a solução de gerenciamento de riscos interno.

Você pode usar o aplicativo Agendador de Tarefas no Windows para executar automaticamente o script todos os dias.

1. No computador local, clique no botão **Iniciar** do Windows e digite **Agendador de Tarefas.**

2. Clique no **aplicativo Agendador de** Tarefas para abri-lo.

3. Na seção **Ações,** clique em **Criar Tarefa.**

4. Na guia **Geral,** digite um nome descritivo para a tarefa agendada; por exemplo, **o Script do Conector de RH.** Você também pode adicionar uma descrição opcional.

5. Em **Opções de segurança,** faça o seguinte:

   1. Determine se você deve executar o script somente quando estiver conectado ao computador ou quando estiver conectado ou não.
   
   1. Verifique se a caixa **de seleção Executar com os privilégios mais altos** está marcada.

6. Selecione a **guia Gatilhos,** clique em **Novo** e faça o seguinte:

   1. Em **Configurações,** selecione a **opção** Diário e, em seguida, escolha uma data e hora para executar o script pela primeira vez. O script será todos os dias no mesmo horário especificado.
   
   1. Em **Configurações Avançadas,** verifique se **a caixa de seleção** Habilitado está marcada.
   
   1. Clique em **OK**.

7. Selecione a **guia Ações,** clique **em Novo** e faça o seguinte:

   ![Configurações de ação para criar uma nova tarefa agendada para o script do conector de RH](../media/HRConnectorScheduleTask1.png)

   1. Na lista **suspenso** Ação, certifique-se de que **Iniciar um programa** está selecionado.

   1. Na caixa **Programa/script,** clique em Procurar **e** vá para o seguinte local e selecione-o para que o caminho seja exibido na caixa: `C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe` .

   1. Na caixa **Adicionar argumentos (opcional),** colar o mesmo comando de script que você fez na Etapa 4. Por exemplo, `.\HRConnector.ps1 -tenantId "d5723623-11cf-4e2e-b5a5-01d1506273g9" -appId "c12823b7-b55a-4989-faba-02de41bb97c3" -appSecret "MNubVGbcQDkGCnn"  -jobId "e081f4f4-3831-48d6-7bb3-fcfab1581458" -csvFilePath "C:\Users\contosoadmin\Desktop\Data\employee_termination_data.csv"`

   1. Na caixa **Iniciar em (opcional),** colar o local da pasta do script que você fez na Etapa 4. Por exemplo, `C:\Users\contosoadmin\Desktop\Scripts`.

   1. Clique **em Ok** para salvar as configurações da nova ação.

8. Na janela **Criar Tarefa,** clique em **Ok** para salvar a tarefa agendada. Você pode ser solicitado a inserir suas credenciais de conta de usuário.

   A nova tarefa é exibida na Biblioteca do Agendador de Tarefas.

   ![A nova tarefa é exibida na Biblioteca do Agendador de Tarefas](../media/HRConnectorTaskSchedulerLibrary.png)

   A última vez em que o script foi executado e da próxima vez que ele está agendado para ser executado é exibido. Você pode clicar duas vezes na tarefa para editá-la.

   Você também pode verificar a última vez em que o script foi atualizado na página do flyout do conector de RH correspondente no centro de conformidade.
