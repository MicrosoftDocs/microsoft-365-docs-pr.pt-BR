---
title: Configurar um conector para importar dados de símbolos físicos
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
description: Os administradores podem configurar um conector de dados para importar dados do sistema físico do símbolos da sua organização para o Microsoft 365. Isso permite que você use esses dados nas políticas de gerenciamento de risco do insider para ajudá-lo a detectar acesso a seus prédios físicos por usuários específicos que podem indicar uma possível ameaça interna à sua organização.
ms.openlocfilehash: 6d52879031c8801191b1a419f38a1167c1bb0688
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48204287"
---
# <a name="set-up-a-connector-to-import-physical-badging-data-preview"></a>Configurar um conector para importar dados de símbolos físicos (versão prévia)

Você pode configurar um conector de dados no centro de conformidade da Microsoft 365 para importar dados de símbolos físicos, como eventos de acesso físico brutos do funcionário ou qualquer alarmes de acesso físico gerados pelo sistema símbolos da sua organização. Exemplos de pontos de acesso físico são uma entrada para um edifício ou uma entrada na sala do servidor ou no Data Center. Os dados do símbolos físico podem ser usados pela solução de gerenciamento de risco do Microsoft 365 [Insider](insider-risk-management.md) para ajudar a proteger sua organização contra atividades mal-intencionadas ou roubo de dados dentro da organização.

A configuração de um conector de símbolos físico consiste nas seguintes tarefas:

- Criar um aplicativo no Azure Active Directory (Azure AD) para acessar um ponto de extremidade da API que aceita uma carga JSON que contém dados de símbolos físicos.

- Criar a carga JSON com um esquema definido pelo conector de dados símbolos físico.

- Criar um conector de dados do símbolos físico no centro de conformidade do Microsoft 365.

- Executar um script para empurrar os dados do símbolos físico para o ponto de extremidade da API.

- Opcionalmente, agendar o script para ser executado automaticamente para importar dados de símbolos físicos no momento.

## <a name="before-you-set-up-the-connector"></a>Antes de configurar o conector

- Sua organização deve ter o consentimento para permitir que o serviço de importação do Office 365 acesse os dados da sua organização. Para concordar com essa solicitação, [acesse a página](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), entre com as credenciais de um administrador global do Microsoft 365 e aceite a solicitação. Você precisa concluir esta etapa para poder criar com êxito o conector símbolos físico na etapa 3.

- O usuário que cria o conector símbolos físico na etapa 3 deve ser atribuído à função de exportação de importação de caixa de correio no Exchange Online. Por padrão, essa função não é atribuída a nenhum grupo de funções no Exchange Online. Você pode adicionar a função de exportação de importação de caixa de correio ao grupo de funções Gerenciamento da organização no Exchange Online. Ou você pode criar um novo grupo de função, atribua a função de exportação de importação de caixa de correio e, em seguida, adicione os usuários apropriados como membros. Para obter mais informações, consulte as seções [criar grupos de função](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) ou [modificar grupos de função](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) no artigo "gerenciar grupos de função no Exchange Online".

- Você precisa determinar como recuperar ou exportar os dados do sistema de símbolos físico da sua organização (em uma base diária) e criar um arquivo JSON descrito na etapa 2. O script executado na etapa 4 enviará os dados do arquivo JSON para o ponto de extremidade da API.

- O script de exemplo executado na etapa 4 envia os dados do símbolos físico do arquivo JSON para a API do conector, de forma que ele possa ser usado pela solução de gerenciamento de risco do insider. Este script de exemplo não tem suporte em nenhum programa ou serviço de suporte padrão da Microsoft. O script de exemplo é fornecido como está sem garantia de qualquer tipo. A Microsoft também se isenta de todas as garantias implícitas, incluindo sem limitações quaisquer garantias aplicáveis de padrões de comercialização ou de adequação a uma finalidade específica. Todo o risco resultante do uso ou do desempenho do script de exemplo e da documentação permanece com você. De modo algum a Microsoft, seus autores ou qualquer outra pessoa envolvida na criação, produção ou veiculação dos scripts serão considerados responsáveis por quaisquer danos (incluindo sem limitações danos por perda de lucros comerciais, interrupção de negócios, perda de informações comerciais ou outras perdas pecuniárias) resultantes do uso ou da incapacidade de uso da documentação ou scripts de exemplo, mesmo que a Microsoft tenha sido alertada sobre a possibilidade de tais danos.

## <a name="step-1-create-an-app-in-azure-active-directory"></a>Etapa 1: criar um aplicativo no Azure Active Directory

A primeira etapa é criar e registrar um novo aplicativo no Azure Active Directory (Azure AD). O aplicativo corresponderá ao conector físico do símbolos que você criou na etapa 3. A criação deste aplicativo permitirá que o Azure AD autentique a solicitação de envio por push para o Payload JSON contendo dados de símbolos físicos. Durante a criação deste aplicativo do Azure AD, certifique-se de salvar as informações a seguir. Esses valores serão usados nas etapas posteriores.

- ID de aplicativo do Azure AD (também chamada de *ID do aplicativo* ou *ID do cliente*)

- Segredo do aplicativo do Azure AD (também chamado de *segredo do cliente*)

- ID do locatário (também chamado de *ID de diretório*)

Para obter instruções detalhadas sobre a criação de um aplicativo no Azure AD, consulte [registrar um aplicativo com a plataforma de identidade da Microsoft](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).

## <a name="step-2-prepare-a-json-file-with-physical-badging-data"></a>Etapa 2: preparar um arquivo JSON com dados do símbolos físico

A próxima etapa é criar um arquivo JSON que contenha informações sobre os dados de acesso físico dos funcionários. Conforme explicado na seção antes de começar, você precisará determinar como gerar esse arquivo JSON no sistema físico do símbolos da sua organização.

O arquivo JSON deve estar em conformidade com a definição de esquema exigida pelo conector. Aqui estão as descrições das propriedades de esquema necessárias para o arquivo JSON:

|**Property**|**Descrição**|**Tipo de dados**|
|:-----------|:--------------|:------------|
|UserId|Um funcionário pode ter várias identidades digitais nos sistemas. A entrada precisa ter a ID do Azure AD já resolvida pelo sistema de origem. |UPN ou endereço de email|
|AssetId|A ID de referência do ativo físico ou do ponto de acesso físico.| Cadeia alfanumérica|
|Assetname|O nome amigável do ativo físico ou do ponto de acesso físico.|Cadeia alfanumérica|
|EventTime|O carimbo de data/hora do Access.|Data e hora, no formato UTC|
|AccessStatus|Valor de `Success` ou `Failed`| String|
|||

Veja um exemplo de um arquivo JSON que está em conformidade com o esquema necessário:

```text
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
Você também pode baixar a seguinte definição de esquema para o arquivo JSON do assistente quando você cria o conector símbolos físico na etapa 3.

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

## <a name="step-3-create-the-physical-badging-connector"></a>Etapa 3: criar o conector símbolos físico

A próxima etapa é criar um conector de símbolos físico no centro de conformidade da Microsoft 365. Após executar o script na etapa 4, o arquivo JSON que você criou na etapa 3 será processado e enviado para o ponto de extremidade da API que você configurou na etapa 1. Nesta etapa, certifique-se de copiar o JobId que é gerado quando você cria o conector. Você usará o JobId quando executar o script.

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com/) e clique em **conectores de dados** no painel de navegação esquerdo.

2. Na página **conectores de dados** em **símbolos físico**, clique em **Exibir**.

3. Na página **símbolos físico** , clique em **Adicionar conector**.

4. Na página **credenciais de autenticação** , faça o seguinte e clique em **Avançar**:
  
   1. Digite ou cole a ID de aplicativo do Azure AD para o aplicativo do Azure que você criou na etapa 1.
  
   2. Baixe o esquema de exemplo para sua referência para criar o arquivo JSON.
  
   3. Digite um nome exclusivo para o conector símbolos físico.

5. Na página **revisão** , revise suas configurações e clique em **concluir** para criar o conector.

6. Uma página de status é exibida para confirmar que o conector foi criado. Esta página também contém a ID do trabalho. Você pode copiar a ID do trabalho dessa página ou da página do menu de atalho para o conector. Você precisa desta ID de trabalho ao executar o script.

   A página de status também contém um link para o script. Consulte este script para entender como postar o arquivo JSON no ponto de extremidade da API.

7. Clique em **Concluído**.

   O novo conector é exibido na lista na guia **conectores** .

8. Clique no conector símbolos físico que você acabou de criar para exibir a página de menu suspenso, que contém propriedades e outras informações sobre o conector.

## <a name="step-4-run-the-script-to-post-your-json-file-containing-physical-badging-data"></a>Etapa 4: executar o script para postar o arquivo JSON contendo dados de símbolos físicos

A próxima etapa na configuração de um conector de símbolos físico é executar um script que enviará os dados do símbolos físico no arquivo JSON (que você criou na etapa 2) para o ponto de extremidade da API que você criou na etapa 1. Fornecemos um script de exemplo para sua referência e você pode optar por usá-lo ou criar seu próprio script para postar o arquivo JSON para o ponto de extremidade da API.

Depois de executar o script, o arquivo JSON que contém os dados do símbolos físico é enviado à sua organização do Microsoft 365, onde pode ser acessado pela solução de gerenciamento de risco do insider. Recomendamos que você publique dados de símbolos físicos diariamente. Você pode fazer isso automatizando o processo para gerar o arquivo JSON todos os dias no sistema de símbolos físico e agendar o script para empurrar os dados.

> [!NOTE]
> O número máximo de registros no arquivo JSON que podem ser processados pela API é de 50.000 registros.

1. Vá para [este site do GitHub](https://github.com/microsoft/m365-hrconnector-sample-scripts/blob/master/upload_termination_records.ps1) para acessar o script de exemplo.

2. Clique no botão **RAW** para exibir o script no modo de exibição de texto

3. Copie todas as linhas no script de exemplo e salve-as em um arquivo de texto.

4. Modifique o script de exemplo para sua organização, se necessário.

5. Salve o arquivo de texto como um arquivo de script do Windows PowerShell usando um sufixo de nome de arquivo. ps1; por exemplo, PhysicalBadging.ps1.

6. Abra um prompt de comando no computador local e vá para o diretório onde você salvou o script.

7. Execute o seguinte comando para empurrar os dados do símbolos físico no arquivo JSON para a nuvem da Microsoft; por exemplo:

   ```powershell
   .\PhysicalBadging.ps1 -tenantId "<Tenant Id>" -appId "<Azure AD App Id>" -appSecret "<Azure AD App Secret>" -jobId "Job Id" -jsonFilePath "<records file path>"
   ```

   A tabela a seguir descreve os parâmetros a serem usados com esse script e seus valores necessários. As informações obtidas nas etapas anteriores são usadas nos valores desses parâmetros.

   | **Parâmetro**|**Descrição**|
   |:-------------|:--------------|
   |tenantId | Esta é a ID da sua organização do Microsoft 365 que você obteve na etapa 1. Você também pode obter o tenantid para sua organização na folha **visão geral** no centro de administração do Azure AD. Isso é usado para identificar sua organização. |
   |appId | Esta é a ID de aplicativo do Azure AD para o aplicativo que você criou no Azure AD na etapa 1. Isso é usado pelo Azure AD para autenticação quando o script tenta acessar sua organização do Microsoft 365.                    |
   |Appsecret pela | Este é o segredo do aplicativo do Azure AD para o aplicativo que você criou no Azure AD na etapa 1. Isso também é usado para autenticação.                                                        |
   |ID | Esta é a ID do trabalho do conector símbolos físico que você criou na etapa 3. Isso é usado para associar os dados do símbolos físico que são enviados para a nuvem da Microsoft com o conector símbolos físico.              |
   |JsonFilePath | Este é o caminho do arquivo no computador local (aquele que você está usando para executar o script) para o arquivo JSON que você criou na etapa 2. Este arquivo deve seguir o esquema de exemplo descrito na etapa 3.|
   |||

   Veja um exemplo da sintaxe do script do conector símbolos físico usando valores reais para cada parâmetro:

   ```powershell
   .\PhysicalBadging.ps1 -tenantId d5723623-11cf-4e2e-b5a5-01d1506273g9 -appId 29ee526e-f9a7-4e98-a682-67f41bfd643e -appSecret MNubVGbcQDkGCnn -jobId b8be4a7d-e338-43eb-a69e-c513cd458eba -csvFilePath 'C:\Users\contosoadmin\Desktop\Data\physical_badging_data.json'
   ```

   Se o upload for bem-sucedido, o script exibirá a mensagem de **upload bem-sucedida** .

   Se você tiver vários arquivos JSON, será necessário executar o script para cada arquivo.

> [!NOTE]
> Você também pode optar por empurrar os dados do símbolos físico para o ponto de extremidade da API por métodos diferentes de executar o script anterior. Por exemplo, aqui está um exemplo para usar o postmaster para empurrar seus dados para o ponto de extremidade da API.

## <a name="step-5-monitor-the-physical-badging-connector"></a>Etapa 5: monitorar o conector do símbolos físico

Depois de criar o conector de símbolos físico e enviar seus dados de símbolos físicos, você pode exibir o conector e o status de upload no centro de conformidade da Microsoft 365. Se você agendar o script para ser executado automaticamente regularmente, também poderá exibir o status atual após a última vez que o script foi executado.

1. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com/) e clique em **conectores de dados** no painel de navegação esquerdo.

2. Clique na guia **conectores** e selecione o conector símbolos físico para exibir a página de submenu, que contém as propriedades e informações sobre o conector.

   ![Página de submenu de status do conector símbolos físico](..\media\PhysicalBadgingStatusFlyout.png)

3. Em **última importação**, clique no link **baixar log** para abrir (ou salvar) o log de status do conector. Esse log contém informações sobre cada vez que o script é executado e carrega os dados do arquivo CSV para a nuvem da Microsoft.

   ![Arquivo de log físico do conector símbolos exibe linhas de número do arquivo JSON que foram carregadas](..\media\PhysicalBadgingConnectorLogFile.png)

   O campo **RecordsSaved** indica o número de linhas no arquivo CSV que foram carregadas. Por exemplo, se o arquivo CSV contiver quatro linhas, o valor dos campos **RecordsSaved** será 4, se o script tiver carregado com êxito todas as linhas no arquivo CSV.

Se você não tiver executado o script na etapa 4, um link para baixar o script será exibido em **última importação**. Você pode baixar o script e seguir as etapas na etapa 4 para executá-lo.

## <a name="optional-step-6-schedule-the-script-to-run-automatically"></a>Opcion Etapa 6: agendar o script para ser executado automaticamente

Para garantir que os dados de símbolos físicos mais recentes da sua organização estejam disponíveis para ferramentas como a solução de gerenciamento de risco do Insider, recomendamos que você agende o script para ser executado automaticamente de forma recorrente, como uma vez por dia. Isso também exige que você atualize os dados do símbolos físico para o arquivo JSON de forma semelhante (se não for o mesmo), para que ele contenha as informações mais recentes sobre funcionários que saem da sua organização. O objetivo é carregar os dados de símbolos físicos mais atuais para que o conector símbolos físico possa disponibilizá-lo para a solução de gerenciamento de risco do insider.

Você pode fazer com que o aplicativo Agendador de tarefas do Windows execute o script automaticamente todos os dias.

1. No computador local, clique no botão **Iniciar** do Windows e digite **Agendador de tarefas**.

2. Clique no aplicativo **Agendador de tarefas** para abri-lo.

3. Na seção **ações** , clique em **criar tarefa**.

4. Na guia **geral** , digite um nome descritivo para a tarefa agendada; por exemplo, **script do conector símbolos físico**. Você também pode adicionar uma descrição opcional.

5. Em **Opções de segurança**, faça o seguinte:

   1. Determine se o script deve ser executado somente quando você estiver conectado ao computador ou executá-lo quando estiver conectado ou não.

   2. Verifique se a caixa de seleção **executar com os privilégios mais altos** está selecionada.

6. Selecione a guia **acionadores** , clique em **novo**e faça o seguinte:

   1. Em **configurações**, selecione a opção **diariamente** e, em seguida, escolha uma data e hora para executar o script pela primeira vez. O script será todos os dias no mesmo horário especificado.

   2. Em **Configurações avançadas**, certifique-se de que a caixa de seleção **habilitado** esteja marcada.

   3. Clique em **OK**.

7. Selecione a guia **ações** , clique em **novo**e faça o seguinte:

   ![Configurações de ação para criar uma nova tarefa agendada para o script do conector do símbolos físico](..\media\SchedulePhysicalBadgingScript1.png)

   1. Na lista suspensa **ação** , verifique se **Iniciar um programa** está selecionado.

   2. Na caixa **programa/script** , clique em **procurar**e vá para o local a seguir e selecione-o para que o caminho seja exibido na caixa: C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe.

   3. Na caixa **adicionar argumentos (opcional)** , Cole o mesmo comando de script executado na etapa 4. Por exemplo, .\PhysicalBadging.ps1-tenantid "d5723623-11CF-4E2E-b5a5-01d1506273g9"-appId "c12823b7-b55a-4989-faba-02de41bb97c3"-appsecret pela "MNubVGbcQDkGCnn"-jobId "e081f4f4-3831-48d6-7bb3-fcfab1581458"-jsonFilePath "C:\Users\contosoadmin\Desktop\Data\physical_badging_data.csv"

   4. Na caixa **Iniciar em (opcional)** , Cole o local da pasta do script executado na etapa 4. Por exemplo, C:\Users\contosoadmin\Desktop\Scripts.

   5. Clique em **OK** para salvar as configurações da nova ação.

8. Na janela **criar tarefa** , clique em **OK** para salvar a tarefa agendada. Você pode ser solicitado a inserir suas credenciais de conta de usuário.

   A nova tarefa é exibida na biblioteca do Agendador de tarefas.

   ![A nova tarefa é exibida na biblioteca do Agendador de tarefas](..\media\SchedulePhysicalBadgingScript2.png)

A última vez em que o script foi executado e a próxima vez em que ele está agendado para ser executado é exibida. Você pode clicar duas vezes na tarefa para editá-la.

Você também pode verificar a última vez que o script foi executado na página de submenu do conector físico símbolos correspondente no centro de conformidade.
