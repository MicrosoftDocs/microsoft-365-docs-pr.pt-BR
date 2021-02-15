---
title: Configurar um conector para importar dados de badging físicos
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
description: Os administradores podem configurar um conector de dados para importar dados do sistema de badas físicos da organização para o Microsoft 365. Isso permite que você use esses dados em políticas de gerenciamento de riscos internos para ajudá-lo a detectar o acesso aos seus edifícios físicos por usuários específicos que podem indicar uma possível ameaça interna à sua organização.
ms.openlocfilehash: 7e745b42d0df79f5c39f9fa02cb1b63f164ec2a5
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620127"
---
# <a name="set-up-a-connector-to-import-physical-badging-data-preview"></a>Configurar um conector para importar dados de danos físicos (visualização)

Você pode configurar um conector de dados no centro de conformidade do Microsoft 365 para importar dados de danos físicos, como eventos de acesso físico brutos do funcionário ou quaisquer alarmes de acesso físico gerados pelo sistema de badging da sua organização. Exemplos de pontos de acesso físico são uma entrada para um edifício ou uma entrada para sala de servidor ou data center. Os dados de danos físicos podem ser usados pela solução de gerenciamento de riscos [insider](insider-risk-management.md) do Microsoft 365 para ajudar a proteger sua organização contra atividades mal-intencionadas ou roubo de dados dentro da sua organização.

A configuração de um conector de badging físico consiste nas seguintes tarefas:

- Criar um aplicativo no Azure Active Directory (Azure AD) para acessar um ponto de extremidade de API que aceita uma carga JSON que contém dados de danos físicos.

- Criar a carga JSON com um esquema definido pelo conector de dados de badging físico.

- Criar um conector de dados com problemas físicos no centro de conformidade do Microsoft 365.

- Executar um script para levar os dados de selo físico para o ponto de extremidade da API.

- Opcionalmente, o agendamento do script para ser executado automaticamente para importar dados de badging físicos no momento.

## <a name="before-you-set-up-the-connector"></a>Antes de configurar o conector

- O usuário que cria o conector de badging físico na Etapa 3 deve receber a função Importar Exportar Caixa de Correio no Exchange Online. Por padrão, essa função não é atribuída a nenhum grupo de funções no Exchange Online. Você pode adicionar a função Importar Exportar Caixa de Correio ao grupo de função Gerenciamento da Organização no Exchange Online. Ou você pode criar um novo grupo de função, atribuir a função Importar Exportar Caixa de Correio e adicionar os usuários apropriados como membros. Para obter mais informações, consulte [](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) as [seções](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) Criar grupos de função ou Modificar grupos de função no artigo "Gerenciar grupos de função no Exchange Online".

- Você precisa determinar como recuperar ou exportar os dados do sistema de danos físicos da sua organização (diariamente) e criar um arquivo JSON descrito na Etapa 2. O script executado na Etapa 4 irá por push os dados no arquivo JSON para o ponto de extremidade da API.

- O script de exemplo executado na Etapa 4 empurra os dados de selo físico do arquivo JSON para a API do conector para que eles possam ser usados pela solução de gerenciamento de risco interno. Este script de exemplo não tem suporte em nenhum serviço ou programa de suporte padrão da Microsoft. O script de amostra é fornecido COMO ESTÁ, sem garantia de nenhum tipo. A Microsoft também se isenta de todas as garantias implícitas, incluindo, sem limitação, quaisquer garantias implícitas de comercialização ou adequação a uma finalidade específica. Todo o risco decorrente do uso ou desempenho do script de amostra e da documentação permanece com você. De modo algum a Microsoft, seus autores ou qualquer outra pessoa envolvida na criação, produção ou veiculação dos scripts serão considerados responsáveis por quaisquer danos (incluindo sem limitações danos por perda de lucros comerciais, interrupção de negócios, perda de informações comerciais ou outras perdas pecuniárias) resultantes do uso ou da incapacidade de uso da documentação ou scripts de exemplo, mesmo que a Microsoft tenha sido alertada sobre a possibilidade de tais danos.

## <a name="step-1-create-an-app-in-azure-active-directory"></a>Etapa 1: Criar um aplicativo no Azure Active Directory

A primeira etapa é criar e registrar um novo aplicativo no Azure Active Directory (Azure AD). O aplicativo corresponderá ao conector de badging físico que você criar na Etapa 3. Criar esse aplicativo permitirá que o Azure AD autentgue a solicitação por push para a carga JSON que contém dados de danos físicos. Durante a criação desse aplicativo do Azure AD, certifique-se de salvar as informações a seguir. Esses valores serão usados em etapas posteriores.

- ID do aplicativo Azure AD (também chamada de *ID do aplicativo* ou *ID do cliente)*

- Segredo do aplicativo Azure AD (também chamado de *segredo do cliente)*

- ID do locatário (também chamada de *ID de diretório)*

Para obter instruções passo a passo para criar um aplicativo no Azure AD, confira Registrar um aplicativo com a [Plataforma de Identidade da Microsoft.](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app)

## <a name="step-2-prepare-a-json-file-with-physical-badging-data"></a>Etapa 2: Preparar um arquivo JSON com dados de badging físicos

A próxima etapa é criar um arquivo JSON que contenha informações sobre os dados de acesso físico dos funcionários. Conforme explicado na seção antes de começar, você precisará determinar como gerar esse arquivo JSON a partir do sistema de badging físico da sua organização.

O arquivo JSON deve estar em conformidade com a definição de esquema exigida pelo conector. Aqui estão as descrições das propriedades de esquema necessárias para o arquivo JSON:

| Propriedade | Descrição | Tipo de dados |
|:-----------|:--------------|:------------|
|UserId|Um funcionário pode ter várias identidades digitais nos sistemas. A entrada precisa ter a ID do Azure AD já resolvida pelo sistema de origem. |UPN ou endereço de email|
|AssetId|A ID de referência do ativo físico ou ponto de acesso físico.| Cadeia alfanumérico|
|AssetName|O nome amigável do ativo físico ou do ponto de acesso físico.|Cadeia alfanumérico|
|EventTime|O carimbo de data/hora do acesso.|Data e hora, no formato UTC|
|AccessStatus|Valor de `Success` ou `Failed`| Cadeia de caracteres|
|||

Aqui está um exemplo de um arquivo JSON que está em conformidade com o esquema necessário:

```json
[
    {
        "UserId":"sarad@contoso.com"
        "AssetId":"Mid-Sec-7",
        "AssetName":"Main Building 1st Floor Mid Section",
        "EventTime":"2019-07-04T01:57:49",
        "AccessStatus":"Failed",
    },
    {
        "UserId":"pilarp@contoso.com",        
        "AssetId":"Mid-Sec-7",
        "AssetName":"Main Building 1st Floor Mid Section",
        "EventTime":"2019-07-04T02:57:49",        
        "AccessStatus":"Success",
    }
]
```
Você também pode baixar a definição de esquema a seguir para o arquivo JSON do assistente ao criar o conector de badging físico na Etapa 3.

```text
{
    "title" : "Physical Badging Signals",
    "description" : "Access signals from physical badging systems",
    "DataType" : {
        "description" : "Identify what is the data type for input signal",
        "type" : "string",
    },
    "type" : "object",
    "properties": {
        "UserId" : {
            "description" : "Unique identifier AAD Id resolved by the source system",
            "type" : "string",
        },
        "AssetId": {
            "description" : "Unique ID of the physical asset/access point",
            "type" : "string",
        },
        "AssetName": {
            "description" : "friendly name of the physical asset/access point",
            "type" : "string",
        },
        "EventTime" : {
            "description" : "timestamp of access",
            "type" : "string",
        },
        "AccessStatus" : {
            "description" : "what was the status of access attempt - Success/Failed",
            "type" : "string",
        },
    }
    "required" : ["UserId", "AssetId", "EventTime" "AccessStatus"]
}
```

## <a name="step-3-create-the-physical-badging-connector"></a>Etapa 3: Criar o conector de badging físico

A próxima etapa é criar um conector de badging físico no centro de conformidade do Microsoft 365. Depois de executar o script na Etapa 4, o arquivo JSON que você criou na Etapa 3 será processado e pressionado para o ponto de extremidade da API que você configurou na Etapa 1. Nesta etapa, copie a JobId gerada quando você criar o conector. Você usará a JobId quando executar o script.

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com/) e clique em **Conectores de dados** na barra de entrada esquerda.

2. Na página **Conectores de dados** em **Badging físico,** clique em **Exibir**.

3. Na página **Desacarregamento físico,** clique **em Adicionar conector.**

4. Na página **Credenciais de autenticação,** faça o seguinte e clique em **Next:**
  
   1. Digite ou colar a ID de aplicativo do Azure AD para o aplicativo do Azure que você criou na Etapa 1.
  
   2. Baixe o esquema de exemplo de sua referência para criar o arquivo JSON.
  
   3. Digite um nome exclusivo para o conector de badging físico.

5. Na página **Revisão,** revise suas configurações e clique em **Concluir** para criar o conector.

6. Uma página de status é exibida confirmando que o conector foi criado. Esta página também contém a ID do trabalho. Você pode copiar a ID do trabalho desta página ou da página do flyout do conector. Você precisa dessa ID de trabalho ao executar o script.

   A página de status também contém um link para o script. Confira este script para entender como postar o arquivo JSON no ponto de extremidade da API.

7. Clique em **Concluído**.

   O novo conector é exibido na lista na guia **Conectores.**

8. Clique no conector de badging físico que você acabou de criar para exibir a página do flyout, que contém propriedades e outras informações sobre o conector.

## <a name="step-4-run-the-script-to-post-your-json-file-containing-physical-badging-data"></a>Etapa 4: Execute o script para postar seu arquivo JSON contendo dados de badging físicos

A próxima etapa na configuração de um conector de badging físico é executar um script que colocará os dados de selo físico no arquivo JSON (que você criou na Etapa 2) para o ponto de extremidade da API que você criou na Etapa 1. Fornecemos um script de exemplo para sua referência e você pode optar por usá-la ou criar seu próprio script para postar o arquivo JSON no ponto de extremidade da API.

Depois que você executar o script, o arquivo JSON que contém os dados de danos físicos será pressionado para sua organização do Microsoft 365, onde ele poderá ser acessado pela solução de gerenciamento de riscos interno. Recomendamos que você poste dados de badging físicos diariamente. Você pode fazer isso automatizando o processo para gerar o arquivo JSON todos os dias a partir do seu sistema de badging físico e, em seguida, agendando o script para push os dados.

> [!NOTE]
> O número máximo de registros no arquivo JSON que podem ser processados pela API é de 50.000 registros.

1. Acesse este [site do GitHub para](https://github.com/microsoft/m365-hrconnector-sample-scripts/blob/master/upload_termination_records.ps1) acessar o script de exemplo.

2. Clique no **botão Bruto** para exibir o script na exibição de texto

3. Copie todas as linhas do script de exemplo e salve-as em um arquivo de texto.

4. Modifique o script de exemplo para sua organização, se necessário.

5. Salve o arquivo de texto como um arquivo de script do Windows PowerShell usando um sufixo de nome de arquivo .ps1; por exemplo, PhysicalBadging.ps1.

6. Abra um Prompt de Comando no computador local e vá para o diretório onde você salvou o script.

7. Execute o seguinte comando para levar os dados de badging físicos do arquivo JSON para a nuvem da Microsoft; por exemplo:

   ```powershell
   .\PhysicalBadging.ps1 -tenantId "<Tenant Id>" -appId "<Azure AD App Id>" -appSecret "<Azure AD App Secret>" -jobId "Job Id" -jsonFilePath "<records file path>"
   ```

   A tabela a seguir descreve os parâmetros a usar com esse script e seus valores obrigatórios. As informações obtidas nas etapas anteriores são usadas nos valores desses parâmetros.

   | Parâmetro | Descrição |
   |:-------------|:--------------|
   |tenantId | Essa é a ID da sua organização do Microsoft 365 que você obteve na Etapa 1. Você também pode obter a tenantId da sua organização na folha **Visão** geral no Centro de administração do Azure AD. Isso é usado para identificar sua organização. |
   |appId | Essa é a ID de aplicativo do Azure AD para o aplicativo que você criou no Azure AD na Etapa 1. Isso é usado pelo Azure AD para autenticação quando o script tenta acessar sua organização do Microsoft 365.                    |
   |appSecret | Este é o segredo do aplicativo do Azure AD para o aplicativo que você criou no Azure AD na Etapa 1. Isso também é usado para autenticação.                                                        |
   |jobId | Esta é a ID do trabalho para o conector de badging físico que você criou na Etapa 3. Isso é usado para associar os dados de badging físicos que são pressionados para a nuvem da Microsoft com o conector de badging físico.              |
   |JsonFilePath | Este é o caminho do arquivo no computador local (o que você está usando para executar o script) para o arquivo JSON que você criou na Etapa 2. Esse arquivo deve seguir o esquema de exemplo descrito na Etapa 3.|
   |||

   Aqui está um exemplo da sintaxe para o script do conector de badging físico usando valores reais para cada parâmetro:

   ```powershell
   .\PhysicalBadging.ps1 -tenantId d5723623-11cf-4e2e-b5a5-01d1506273g9 -appId 29ee526e-f9a7-4e98-a682-67f41bfd643e -appSecret MNubVGbcQDkGCnn -jobId b8be4a7d-e338-43eb-a69e-c513cd458eba -csvFilePath 'C:\Users\contosoadmin\Desktop\Data\physical_badging_data.json'
   ```

   Se o carregamento for bem-sucedido, o script exibirá a **mensagem Carregar Com** Êxito.

   Se você tiver vários arquivos JSON, será preciso executar o script para cada arquivo.

> [!NOTE]
> Você também pode optar por levar os dados de selo físico para o ponto de extremidade da API por métodos diferentes de executar o script anterior. Por exemplo, veja um exemplo de como usar o Postman para levar seus dados para o ponto de extremidade da API.

## <a name="step-5-monitor-the-physical-badging-connector"></a>Etapa 5: Monitorar o conector de badging físico

Depois de criar o conector de badging físico e enviar os dados de insuamento físicos, você pode exibir o conector e carregar o status no centro de conformidade do Microsoft 365. Se você agendar o script para ser executado automaticamente regularmente, também poderá exibir o status atual após a última vez em que o script foi executado.

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com/) e clique **em Conectores de dados** na barra de entrada esquerda.

2. Clique na **guia Conectores** e selecione o conector de badging físico para exibir a página do flyout. Esta página contém as propriedades e informações sobre o conector.

   ![Página de status do flyout para o conector de badging físico](..\media\PhysicalBadgingStatusFlyout.png)

3. Em **Última importação,** clique no link **Baixar log** para abrir (ou salvar) o log de status do conector. Esse log contém informações sobre cada vez que o script é executado e carrega os dados do arquivo CSV para a nuvem da Microsoft.

   ![O arquivo de log do conector de badging físico exibe linhas de número do arquivo JSON que foram carregadas](..\media\PhysicalBadgingConnectorLogFile.png)

   O **campo RecordsSaved** indica o número de linhas no arquivo CSV carregado. Por exemplo, se o arquivo CSV contiver quatro linhas, o valor dos campos **RecordsSaved** será 4, se o script tiver carregado com êxito todas as linhas no arquivo CSV.

Se você ainda não tiver executado o script na Etapa 4, um link para baixar o script será exibido em **Última importação.** Você pode baixar o script e seguir as etapas na Etapa 4 para executar o script.

## <a name="optional-step-6-schedule-the-script-to-run-automatically"></a>(Opcional) Etapa 6: Agendar o script para ser executado automaticamente

Para garantir que os dados de danos físicos mais recentes da sua organização estão disponíveis para ferramentas como a solução de gerenciamento de riscos insider, recomendamos que você agende o script para ser executado automaticamente de forma recorrente, como uma vez por dia. Isso também requer que você atualize os dados de danos físicos para o arquivo JSON em um agendamento semelhante (se não o mesmo) para que ele contenha as informações mais recentes sobre os funcionários que saem da sua organização. O objetivo é carregar os dados de danos físicos mais recentes para que o conector de badging físico possa torná-los disponíveis para a solução de gerenciamento de riscos interno.

Você pode usar o aplicativo Agendador de Tarefas no Windows para executar automaticamente o script todos os dias.

1. No computador local, clique no botão **Iniciar** do Windows e digite **Agendador de Tarefas.**

2. Clique no **aplicativo Agendador de** Tarefas para abri-lo.

3. Na seção **Ações,** clique em **Criar Tarefa.**

4. Na guia **Geral,** digite um nome descritivo para a tarefa agendada; por exemplo, **script do conector de badging físico.** Você também pode adicionar uma descrição opcional.

5. Em **Opções de segurança,** faça o seguinte:

   1. Determine se você deve executar o script somente quando estiver conectado ao computador ou quando estiver conectado ou não.

   2. Verifique se a caixa **de seleção Executar com os privilégios mais altos** está marcada.

6. Selecione a **guia Gatilhos,** clique em **Novo** e faça o seguinte:

   1. Em **Configurações,** selecione a **opção** Diário e, em seguida, escolha uma data e hora para executar o script pela primeira vez. O script será todos os dias no mesmo horário especificado.

   2. Em **Configurações Avançadas,** verifique se **a caixa de seleção** Habilitado está marcada.

   3. Clique em **OK**.

7. Selecione a **guia Ações,** clique **em Novo** e faça o seguinte:

   ![Configurações de ação para criar uma nova tarefa agendada para o script do conector físico de badging](..\media\SchedulePhysicalBadgingScript1.png)

   1. Na lista **suspenso** Ação, certifique-se de que **Iniciar um programa** está selecionado.

   2. Na caixa **Programa/script,** clique em Procurar **e** vá para o seguinte local e selecione-o para que o caminho seja exibido na caixa: C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe.

   3. In the **Add arguments (optional)** box, paste the same script command that you ran in Step 4. Por exemplo, .\PhysicalBadging.ps1-tenantId "d5723623-11cf-4e2e-b5a5-01d1506273g9" -appId "c12823b7-b55a-4989-faba-02de41bb97c3" -appSecret "MNubVGbcQDkGCnn" -jobId "e081f4f4-3831-48d6-7bb3-fcfab1581458" -jsonFilePath "C:\Users\contosoadmin\Desktop\Data\physical_badging_data.csv"

   4. Na caixa **Iniciar em (opcional),** colar o local da pasta do script que você fez na Etapa 4. Por exemplo, C:\Users\contosoadmin\Desktop\Scripts.

   5. Clique **em Ok** para salvar as configurações da nova ação.

8. Na janela **Criar Tarefa,** clique em **Ok** para salvar a tarefa agendada. Você pode ser solicitado a inserir suas credenciais de conta de usuário.

   A nova tarefa é exibida na Biblioteca do Agendador de Tarefas.

   ![A nova tarefa é exibida na Biblioteca do Agendador de Tarefas](..\media\SchedulePhysicalBadgingScript2.png)

A última vez em que o script foi executado e da próxima vez que ele está agendado para ser executado é exibido. Você pode clicar duas vezes na tarefa para editá-la.

Você também pode verificar a última vez em que o script foi atualizado na página do flyout do conector de badging físico correspondente no centro de conformidade.
