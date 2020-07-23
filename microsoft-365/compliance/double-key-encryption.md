---
title: DKE (criptografia de chave dupla)
description: O DKE permite proteger dados altamente confidenciais, mantendo o controle total da sua chave.
author: kccross
ms.author: krowley
manager: laurawi
ms.date: 07/21/2020
ms.topic: conceptual
ms.service: information-protection
audience: Admin
ms.reviewer: esaggese
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.openlocfilehash: d9ed155576d69889e53e4e4d1ce03e4233fd08ff
ms.sourcegitcommit: 4789b261eb029d7c965421a1260acc110e6385db
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/23/2020
ms.locfileid: "45387438"
---
# <a name="double-key-encryption-dke"></a>DKE (criptografia de chave dupla)

> *Aplica-se a: chave dupla de criptografia para o Microsoft 365 Public Preview, [microsoft 365 Compliance](https://www.microsoft.com/microsoft-365/business/compliance-management), [proteção de informações do Azure](https://azure.microsoft.com/pricing/details/information-protection)*
>
> *Instruções para: [cliente de rotulação unificada de proteção de informações do Azure para Windows](https://docs.microsoft.com/azure/information-protection/faqs.md#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*
>
> *Descrição do serviço para: conformidade com a [Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*

A criptografia de chave dupla (DKE) usa duas chaves juntas para acessar o conteúdo protegido. Você armazena uma chave no Microsoft Azure e mantém a outra chave. O cliente de rotulação unificado de proteção de informações do Azure protege o conteúdo altamente confidencial enquanto você mantém o controle total de uma de suas chaves.

A criptografia de chave dupla oferece suporte a implantações no local e na nuvem. Essas implantações ajudam a garantir que os dados criptografados permaneçam opaco onde quer você armazene os dados protegidos.

Para obter mais informações sobre as chaves de raiz de locatários padrão baseadas em nuvem, consulte [Planning and Implementing Your Azure Information Protection locatário Key](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key).

O vídeo a seguir mostra como a criptografia de chave dupla funciona para proteger o conteúdo.

> [!VIDEO https://msit.microsoftstream.com/embed/video/f466a1ff-0400-a936-221c-f1eab45dc756]

Se as suas organizações têm qualquer um dos seguintes requisitos, você pode usar o DKE para ajudar a proteger o conteúdo:

- Você quer garantir que *apenas você* possa descriptografar o conteúdo protegido, em todas as circunstâncias.
- Você não deseja que a Microsoft tenha acesso a dados protegidos por conta própria.
- Você tem requisitos normativos para manter chaves dentro de um limite geográfico. Todas as chaves que você mantém para criptografia e descriptografia de dados são mantidas em seu data center.

## <a name="system-and-licensing-requirements-for-dke"></a>Requisitos de sistema e licenciamento para o DKE

Criptografia de chave dupla para a Microsoft 365 parte do Microsoft 365 E5 e Office 365 e5. Se você não tem uma licença do Microsoft 365 e5, é possível inscrever-se em uma [avaliação](https://aka.ms/M365E5ComplianceTrial). Para obter mais informações sobre essas licenças, consulte [diretrizes de licenciamento da Microsoft 365 para segurança & conformidade](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).

**Office Insider** Para usar a visualização pública, você deve ser membro do programa Office Insider. Para ingressar no Office Insider, vá para [https://insider.office.com](https://insider.office.com) . Quando você for membro, prepare o ambiente para implantar o Office Insider compilações escolhendo o método de implantação certo para sua organização. Para obter instruções, consulte [introdução à implantação de compilações do Office Insider](https://insider.office.com/business/deploy).

**Proteção de informações do Azure**. O DKE funciona com rótulos de sensibilidade e requer a proteção de informações do Azure.

## <a name="supported-environments-for-storing-and-viewing-dke-protected-content"></a>Ambientes suportados para armazenar e exibir o conteúdo protegido por DKE

**Aplicativos com suporte**. [Microsoft 365 aplicativos para clientes corporativos](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product) no Windows, incluindo Word, Excel e PowerPoint.

**Suporte a conteúdo online**. Há suporte para documentos e arquivos armazenados online no Microsoft SharePoint e no OneDrive for Business. Você pode compartilhar conteúdo criptografado por email, mas não pode exibir documentos e arquivos criptografados online. Em vez disso, você deve exibir o conteúdo protegido usando os aplicativos de área de trabalho no computador local.

## <a name="about-this-public-preview-article"></a>Sobre este artigo de demonstração pública

Há várias maneiras de realizar algumas das etapas para implantar a criptografia de chave dupla. Este artigo fornece instruções detalhadas para que administradores menos experientes implantem o serviço com êxito. Se você estiver confortável para fazer isso, você pode optar por usar seus próprios métodos.

Este artigo inclui instruções passo a passo sobre como implantar o serviço de criptografia de chave dupla no Azure. Esse cenário não é algo que você provavelmente faria em produção. Para visualização pública, usar o Azure é uma maneira rápida de implantar o DKE. A implantação do Azure permite que você comece a usar a criptografia de chave dupla imediatamente.

Você pode implantar o serviço localmente em sua rede ou com outro provedor. Você precisará publicar o repositório de chaves usando métodos apropriados para esse local.

## <a name="deploy-double-key-encryption"></a>Implantar a criptografia de chave dupla

Este artigo e o vídeo de implantação usam o Azure como o destino de implantação para o serviço DKE. Se você estiver implantando em outro local, precisará fornecer seus próprios valores.

Assista ao [vídeo de implantação de criptografia de duas chaves](https://msit.microsoftstream.com/video/cfdda3ff-0400-a521-1579-f1eacc37fc7e) para ver a visão geral passo a passo dos conceitos no artigo. O vídeo leva cerca de 18 minutos para ser concluído.

Siga estas etapas gerais para configurar a criptografia de chave dupla para sua organização.

1. [Instalar pré-requisitos de software](#install-software-prerequisites)
1. [Clone o repositório do GitHub de criptografia de chave dupla](#clone-the-dke-github-repository)
1. [Modificar configurações do aplicativo](#modify-application-settings)
1. [Gerar chaves de teste](#generate-test-keys)
1. [Compilar o projeto](#build-the-project)
1. [Publicar o repositório de chaves](#publish-the-key-store)
1. [Validar sua implantação](#validate-your-deployment)
1. [Registrar seu repositório de chaves](#register-your-key-store)
1. [Criar rótulos de confidencialidade](#create-labels-using-dke)

Quando tiver concluído, você poderá criptografar documentos e arquivos usando o DKE. Para saber mais, confira [aplicar rótulos de confidencialidade aos seus arquivos e emails no Office](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9).

### <a name="install-software-prerequisites"></a>Instalar pré-requisitos de software

Há dois tipos de pré-requisitos de software para a criptografia de chave dupla

- [Pré-requisitos do serviço de criptografia de chave dupla](#double-key-encryption-service-prerequisites)
- [Pré-requisitos de criptografia de chave dupla para computadores clientes](#double-key-encryption-prerequisites-for-client-computers)

#### <a name="double-key-encryption-service-prerequisites"></a>Pré-requisitos do serviço de criptografia de chave dupla

Instale esses pré-requisitos no computador onde você deseja instalar o serviço DKE.

**SDK do .NET Core 3,1**. Baixe e instale o SDK do [download do .NET Core 3,1](https://dotnet.microsoft.com/download/dotnet-core/3.1).

**Visual Studio Code**. Baixe o Visual Studio Code de [https://code.visualstudio.com/](https://code.visualstudio.com) . Depois de instalado, execute o Visual Studio Code e selecione **View** \> **Extensions**. Instale essas extensões.

- C# para o Visual Studio Code

- Gerenciador de pacotes do NuGet

**Microsoft Office Insider**. Configure pelo menos um [método de implantação](https://insider.office.com/business/deploy).

**Recursos git**. Baixe e instale um dos seguintes.

- [Git](https://git-scm.com/downloads)

- [Área de trabalho do GitHub](https://desktop.github.com/)

- [GitHub corporativo](https://github.com/enterprise)

**OpenSSL** Você deve ter o [OpenSSL](https://slproweb.com/products/Win32OpenSSL.html) instalado para [gerar chaves de teste](#generate-test-keys) depois de implantar o DKE. Certifique-se de que você está invocando-o corretamente de seu caminho de variáveis de ambiente. Por exemplo, consulte "Adicionar o diretório de instalação ao caminho" https://www.osradar.com/install-openssl-windows/ para obter mais detalhes.

#### <a name="double-key-encryption-prerequisites-for-client-computers"></a>Pré-requisitos de criptografia de chave dupla para computadores clientes

Instale esses pré-requisitos em cada computador cliente onde você deseja proteger e consumir documentos protegidos.

**Microsoft Office** versão *. 12711 ou posterior.

Versões **unificadas de rótulo do cliente de proteção de informações do Azure** 2.7.93.0 ou posterior. Baixe e instale o cliente de rotulação unificada da [Microsoft](https://www.microsoft.com/download/details.aspx?id=53018).

### <a name="clone-the-dke-github-repository"></a>Clonar o repositório do GitHub DKE

A Microsoft fornece os arquivos de origem do DKE em um repositório do GitHub. Você clona o repositório para compilar o projeto localmente para uso da sua organização. O repositório do GitHub do DKE está localizado em [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService) .

As instruções a seguir se destinam a usuários do git ou do Visual Studio Code inexperientes:

1. No navegador, acesse:[https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService)

1. No lado direito da tela, selecione **código**. Sua versão da interface do usuário pode mostrar um botão **clone ou download** . Em seguida, na lista suspensa exibida, selecione o ícone Copiar para copiar a URL para a área de transferência.

    Por exemplo:

    :::image type="content" source="../media/dke-clone.png" alt-text="Clonar o repositório de serviço de criptografia de chave dupla do GitHub":::

3. No Visual Studio Code, selecione **Exibir** \> **paleta de comandos** e selecione **git: clonar**. Para ir para a opção na lista, comece a digitar `git: clone` para filtrar as entradas e, em seguida, selecione-a no menu suspenso. Por exemplo:

    :::image type="content" source="../media/dke-vscode-clone.png" alt-text="Visual Studio Code GIT: opção clone":::

4. Na caixa de texto, Cole a URL que você copiou do git e selecione **clonar do GitHub**.

5. Na caixa de diálogo **Selecionar pasta** exibida, procure e selecione um local para armazenar o repositório. No prompt, selecione **abrir**.

    O repositório é aberto no Visual Studio Code e exibe a ramificação atual do git no canto inferior esquerdo. A ramificação deve ser **mestra**.

    Por exemplo:

    :::image type="content" source="../media/dke-vscode-master.png" alt-text="Ramificação do Visual Studio Code Master":::

6. Selecione o Word **Master** e, em seguida, selecione **public_preview** na lista de ramificações.

   > [!IMPORTANT]
   > Selecionar a ramificação public_preview garante que você tenha os arquivos corretos para compilar o projeto. Se você não escolher a ramificação correta, sua implantação falhará.

Agora, o seu repositório de origem do DKE está configurado localmente. Em seguida, [modifique as configurações de aplicativo](#modify-application-settings) para sua organização.

### <a name="modify-application-settings"></a>Modificar configurações do aplicativo

Para implantar o serviço DKE, você deve modificar os seguintes tipos de configurações de aplicativo:

- [Configurações de acesso de chave](#key-access-settings)
- [Definições de locatário e chave](#tenant-and-key-settings)

Você modifica as configurações de aplicativo no appsettings.jsem arquivo. Esse arquivo está localizado no repositório do DoubleKeyEncryptionService que você clonou localmente em DoubleKeyEncryptionService\src\customer-key-store. Por exemplo, no Visual Studio Code, você pode navegar até o arquivo, conforme mostrado na imagem a seguir.

:::image type="content" source="../media/dke-appsettingsjson.png" alt-text="Localizar o appsettings.jsno arquivo do DKE.":::

#### <a name="key-access-settings"></a>Configurações de acesso de chave

Escolha se deseja usar o email ou a autorização de função. O DKE oferece suporte a apenas um desses métodos de autenticação por vez.

- **Autorização de email**. Permite que sua organização autorize o acesso a chaves com base apenas em endereços de email.

- **Autorização de função**. Permite que sua organização autorize o acesso às chaves com base nos grupos do Active Directory e exige que o serviço Web possa consultar o LDAP.

**Para definir as configurações de acesso de chave do DKE usando autorização de email**

1. Abra o **appsettings.jsem** arquivo e localize a `AuthorizedEmailAddress` configuração.

2. Adicione o endereço de email ou endereços que você deseja autorizar. Separe vários endereços de email com aspas duplas e vírgulas. Por exemplo:

   ```json
   "AuthorizedEmailAddress": ["email1@company.com", "email2@company.com ", "email3@company.com"]
   ```

3. Localize a `LDAPPath` configuração e remova o texto `If role authorization is used then this is the LDAP path` entre aspas duplas. Deixe as aspas duplas em vigor. Quando você tiver terminado, a configuração deverá ter a seguinte aparência.

   ```json
   "LDAPPath": ""
   ```

4. Localize a `AuthorizedRoles` configuração e exclua a linha inteira.

Esta imagem mostra o **appsettings.jsem** arquivo formatado corretamente para autorização de email.

   :::image type="content" source="../media/dke-email-accesssetting.png" alt-text="O appsettings.jsem arquivo mostrando o método de autorização de email":::

**Para definir as configurações de acesso de chave para DKE usando autorização de função**

1. Abra o **appsettings.jsem** arquivo e localize a `AuthorizedRoles` configuração.

2. Adicione os nomes de grupo do Active Directory que você deseja autorizar. Separe vários nomes de grupo com aspas duplas e vírgulas. Por exemplo:

   ```json
   "AuthorizedRoles": ["group1", "group2", "group3"]
   ```

3. Localize a `LDAPPath` configuração e adicione o domínio do Active Directory. Por exemplo:

   ```json
   "LDAPPath": "contoso.com"
   ```

4. Localize a `AuthorizedEmailAddress` configuração e exclua a linha inteira.

Esta imagem mostra o **appsettings.jsem** arquivo formatado corretamente para autorização de função.

   :::image type="content" source="../media/dke-role-accesssetting.png" alt-text="appsettings.jsem arquivo mostrando o método de autorização de função":::

#### <a name="tenant-and-key-settings"></a>Definições de locatário e chave

As configurações de locatário e chave do DKE estão localizadas na **appsettings.jsem** arquivo.

**Para definir as configurações de locatário e chave do DKE**

1. Abra o **appsettings.jsem** arquivo.

2. Localize a `ValidIssuers` configuração e substitua `<tenantid>` pela ID do locatário. Você pode localizar sua ID de locatário indo para o portal do Azure e exibindo as [Propriedades do locatário](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties). Por exemplo:

   ```json
   "ValidIssuers": [
     "https://sts.windows.net/9c99431e-b513-44be-a7d9-e7b500002d4b/"
   ]
   ```

Localize o `JwtAudience` . Substitua `<yourhostname>` pelo nome do host do computador em que o serviço DKE será executado. Por exemplo:



  > [!IMPORTANT]
  > O valor de `JwtAudience` deve corresponder *exatamente*ao nome do host. Você pode usar **localhost: 5001** durante a depuração. No entanto, quando você terminar de depurar, certifique-se de atualizar esse valor para o nome de host do servidor.

- `TestKeys:Name`. Insira um nome para a chave. Por exemplo: `TestKey1`
- `TestKeys:Id`. Crie um GUID e insira-o como o `TestKeys:ID` valor. Por exemplo, `DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE`. Você pode usar um site como [gerador de GUID online](https://guidgenerator.com/) para gerar aleatoriamente um GUID.

Esta imagem mostra o formato correto das configurações de locatário e chaves em **appsettings.js**. `LDAPPath`é configurada para autorização de função.

:::image type="content" source="../media/dke-appsettingsjson-tenantkeysettings.png" alt-text="Mostra as configurações de locatário e chave corretas para o DKE no arquivo appsettings.js.":::

### <a name="generate-test-keys"></a>Gerar chaves de teste

Depois de definir as configurações do aplicativo, você estará pronto para gerar chaves de teste públicas e privadas.

Para gerar chaves:

1. No menu Iniciar do Windows, execute o prompt de comando OpenSSL.

1. Vá para a pasta onde você deseja salvar as teclas de teste. Os arquivos que você cria ao concluir as etapas dessa tarefa são armazenados na mesma pasta.

1. Gere a nova chave de teste.

   ```dos
   openssl req -x509 -newkey rsa:2048 -keyout key.pem -out cert.pem -days 365
   ```

2. Gerar a chave privada.

   ```dos
   openssl rsa -in key.pem -out privkeynopass.pem
   ```

1. Gere a chave pública.

   ```dos
   openssl rsa -in key.pem -pubout > pubkeyonly.pem
   ```

1. Em um editor de texto, abra **pubkeyonly. pem**. Copie todo o conteúdo do arquivo **pubkeyonly. pem** , exceto a primeira e a última linha, na `PublicPem` seção do **appsettings.jsem** arquivo.

1. Em um editor de texto, abra **privkeynopass. pem**. Copie todo o conteúdo do arquivo **privkeynopass. pem** , exceto a primeira e a última linha, na `PrivatePem` seção do **appsettings.jsem** arquivo.

1. Remova todos os espaços em branco e novas linhas em ambas as `PublicPem` `PrivatePem` seções e.

    > [!IMPORTANT]
    > Ao copiar esse conteúdo, não exclua nenhum dos dados de PEM.

1. No Visual Studio Code, navegue até o arquivo **Startup.cs** . Esse arquivo está localizado no repositório do DoubleKeyEncryptionService que você clonou localmente em DoubleKeyEncryptionService\src\customer-key-store\.

2. Localize as seguintes linhas:

   ```c#
        #if USE_TEST_KEYS
        #error !!!!!!!!!!!!!!!!!!!!!! Use of test keys is only supported for testing,
        DO NOT USE  FOR PRODUCTION !!!!!!!!!!!!!!!!!!!!!!!!!!!!!
        services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
        #endif
   ```

3. Substitua essas linhas pelo seguinte texto:

   ```csharp
   services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
   ```

   Os resultados finais devem ser semelhantes aos seguintes.

   :::image type="content" source="../media/dke-startupcs-usetestkeys.png" alt-text="arquivo startup.cs para visualização pública":::

Agora você está pronto para [criar seu projeto do DKE](#build-the-project).

### <a name="build-the-project"></a>Compilar o projeto

Use as instruções a seguir para criar o projeto do DKE localmente:

1. No Visual Studio Code, no repositório de serviços do DKE, selecione **Exibir** \> **paleta de comandos** e digite **Compilar** no prompt.

1. Na lista, escolha **tarefas: executar tarefa de compilação**.

   Se não houver tarefas de compilação encontradas, selecione **Configurar tarefa de compilação** e criar uma para o .NET Core da seguinte maneira.

   :::image type="content" source="../media/dke-configurebuildtask.png" alt-text="Configurar a tarefa de compilação ausente para o .NET":::

   1. Escolha **criar tasks.jsno modelo**.

   :::image type="content" source="../media/dke-createtasksjsonfromtemplate.png" alt-text="Criar tasks.jsno arquivo do modelo do DKE":::

   2. Na lista de tipos de modelo, selecione **.NET Core**.

   :::image type="content" source="../media/dke-tasksjsontemplate.png" alt-text="Criar tasks.jsno arquivo do modelo do DKE":::

   3. Na seção criar, localize o caminho para o arquivo **customerkeystore. csproj** . Se ele não estiver lá, adicione a seguinte linha:

      ```json
      "${workspaceFolder}/src/customer-key-store/customerkeystore.csproj",
      ```

  4. Execute novamente a compilação.

1. Verifique se não há nenhum erro vermelho na janela de saída.

   Se houver erros vermelhos, verifique a saída do console. Verifique se você concluiu todas as etapas anteriores corretamente e se as versões de compilação corretas estão presentes.

2. Selecione **executar** \> **Iniciar Depuração** para depurar o processo. Se for solicitado a selecionar um ambiente, selecione **.NET Core**.

O depurador do .NET Core normalmente é iniciado em ' ' https://localhost:5001 `. To view your test key, go to ` https://localhost:5001 ' e acrescenta uma barra (/) e o nome da sua chave. Por exemplo:

```https
https://localhost:5001/TestKey1
```

A chave deve ser exibida no formato JSON.

A configuração já está concluída. Antes de publicar o repositório de chaves, em appsettings.js, para a configuração do JwtAudience, verifique se o valor do nome do host corresponde exatamente ao nome de host do serviço de aplicativo. Você pode ter alterado para localhost para solucionar problemas de compilação.

### <a name="publish-the-key-store"></a>Publicar o repositório de chaves

Para publicar o repositório de chaves, você criará uma instância do serviço de aplicativo do Azure para hospedar sua implantação do DKE. Em seguida, você publicará as chaves geradas no Azure.

**Para criar uma instância do Azure Web App para hospedar sua implantação do DKE**

1. No navegador, entre no [portal do Microsoft Azure](https://ms.portal.azure.com)e vá para a adição de **serviços de aplicativo**  >  **Add**.

1. Selecione sua assinatura e o grupo de recursos e defina os detalhes da instância.

    - Insira o nome de host do computador onde você deseja instalar o serviço DKE. Certifique-se de que é o mesmo nome que o definido para a configuração JwtAudience no arquivo de [**appsettings.js**](#tenant-and-key-settings) . O valor que você fornece para o nome também é o WebAppInstanceName.

    - Para **publicar**, selecione **código**e para **pilha de tempo de execução**, selecione **.NET Core 3,1**.

    Por exemplo:

    :::image type="content" source="../media/dke-azure-add-app-service.png" alt-text="Adicionar seu serviço de aplicativo":::

1. Na parte inferior da página, selecione **revisar + criar**e selecione **Adicionar**.

1. Siga um destes procedimentos para publicar suas chaves geradas no Azure:

    - [Publicar via ZipDeployUI](#publish-via-zipdeployui)
    - [Publicar via FTP](#publish-via-ftp)
    - [Publicar via Visual Studio 2019 ou posterior](https://docs.microsoft.com/aspnet/core/tutorials/)
    - [Publicar em um sistema local](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&tabs=netcore-cli)

    > [!NOTE]
    > Você pode preferir outros métodos para implantar suas chaves. Selecione o método que funciona melhor para a sua organização.

    > [!TIP]
    > A [publicação via Visual Studio](https://docs.microsoft.com/aspnet/core/tutorials/) e para um [sistema local](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&tabs=netcore-cli) é descrita na documentação do [ASP .net](https://docs.microsoft.com/aspnet/core/). Se você usar um desses métodos, abra as instruções em uma guia separada para que você possa retornar aqui facilmente quando tiver concluído.

#### <a name="publish-via-zipdeployui"></a>Publicar via ZipDeployUI

1. Acesse `https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`.

    Por exemplo: https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI

1. Na base de código do armazenamento de chaves, vá para a pasta **Customer-Key-store\src\customer-Key-Store** e verifique se essa pasta contém o arquivo **customerkeystore. csproj** .

1. Executar: **publicação de dotnet**

     A janela saída exibe o diretório onde a publicação foi implantada.

    Por exemplo: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`

1. Envie todos os arquivos no diretório de publicação para um arquivo. zip. Ao criar o arquivo. zip, verifique se todos os arquivos no diretório estão no nível raiz do arquivo. zip.

1. Arraste e solte o arquivo. zip criado no site do ZipDeployUI que você abriu acima. Por exemplo: https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI

O DKE é implantado e você pode navegar até as chaves de teste que você criou. Continue para [validar sua implantação](#validate-your-deployment) abaixo.

#### <a name="publish-via-ftp"></a>Publicar via FTP

1. Conecte-se ao serviço de aplicativo que você criou [acima](#publish-the-key-store).

    Em seu navegador, vá para: centro de implantação do serviço de aplicativo **do portal do Azure**  >  **App Service**  >  **Deployment Center**  >  painel de FTP de**implantação manual**  >  **FTP**  >  **Dashboard**.

1. Copie as cadeias de conexão exibidas para um arquivo local. Você usará essas cadeias de caracteres para se conectar ao serviço do aplicativo Web e carregar arquivos via FTP.

    Por exemplo:

    :::image type="content" source="../media/dke-ftp-dashboard.png" alt-text="Copiar cadeias de conexão do painel de FTP":::

1. Na base de código do armazenamento principal, vá para o **diretório Customer-Key-store\src\customer-Key-Store**

1. Verifique se esse diretório contém o arquivo **customerkeystore. csproj** .

1. Executar: **publicação de dotnet**

    A saída contém o diretório onde a publicação foi implantada.

    Por exemplo: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`

1. Envie todos os arquivos no diretório de publicação para um arquivo zip. Ao criar o arquivo. zip, verifique se todos os arquivos no diretório estão no nível raiz do arquivo. zip.

1. No cliente FTP, use as informações de conexão que você copiou para se conectar ao serviço de aplicativo. Carregue o arquivo. zip que você criou na etapa anterior para o diretório raiz do seu aplicativo Web.

DKE é implantado e você pode navegar para as teclas de teste que você criou. Em seguida, [valide sua implantação](#validate-your-deployment).

### <a name="validate-your-deployment"></a>Validar sua implantação

Depois de implantar o DKE usando um dos métodos descritos acima, valide a implantação e as configurações do armazenamento de chaves.

Sejam

src\customer-key-store\scripts\key_store_tester.ps1 mykeystoreurl/MyKey

Por exemplo:

key_store_tester.ps1https://mycustomerkeystore.com/mykey

Certifique-se de que nenhum erro apareça na saída. Quando estiver pronto, [Registre o repositório de chaves](#register-your-key-store).

## <a name="register-your-key-store"></a>Registrar seu repositório de chaves

As etapas a seguir permitem que você registre seu repositório de chaves. O registro do armazenamento de chaves é a última etapa na implantação do DKE antes que você possa começar a criar rótulos.

Para registrar seu repositório de chave:

1. No navegador, abra o [portal do Microsoft Azure](https://ms.portal.azure.com/)e vá para **todos os** \> registros de aplicativos de **identidade** de serviços \> **App Registrations**.

2. Selecione **novo registro**e insira um nome significativo.

3. Selecione um tipo de conta nas opções exibidas.

    Se você estiver usando o Microsoft Azure com um domínio não personalizado, como **onmicrosoft.com**, selecione **contas nesse diretório organizacional apenas (somente para o Microsoft locatário).**

    Por exemplo:

    :::image type="content" source="../media/dke-app-registration.png" alt-text="Novo registro de aplicativo":::

4. Na parte inferior da página, selecione **registrar** para criar o novo registro de aplicativo.

5. No novo registro de aplicativo, no painel esquerdo, em **gerenciar**, selecione **autenticação**.

6. Selecione **Adicionar uma plataforma**.
 
7. No pop-up **Configurar plataformas** , selecione **Web**.
 
8. Em **URIs de redirecionamento**, insira o URI do serviço de criptografia de chave dupla. Insira a URL do serviço de aplicativo, incluindo o nome do host e o domínio.

    Por exemplo: https://mycustomerkeystoretest.com

    - A URL inserida deve corresponder ao nome de host onde o repositório de chave está implantado.
    - Se você estiver testando localmente com o Visual Studio, use **https://localhost:5001** .
    - Em todos os casos, o esquema deve ser **https**.

    Certifique-se de que o nome do host corresponde exatamente ao nome de host do serviço de aplicativo Você pode ter alterado para `localhost` solucionar problemas de compilação. Em **appsettings.js**, esse valor é o nome de host definido para `JwtAudience` .

6. Em **concessão implícita**, selecione a caixa de seleção **tokens de ID** .

1. Clique em **Salvar** para salvar suas alterações.

7. No painel esquerdo, selecione **expor uma API**e, em seguida, ao lado de URI da ID do aplicativo, selecione **definir**.

9. Ainda na página de **exibir uma API** , na área **escopos definidos por esta API** , selecione **Adicionar um escopo**. No novo escopo:

    1. Defina o nome do escopo como **user_impersonation**.

    2. Selecione os administradores e usuários que podem autorizar.

    3. Defina os valores restantes necessários.

    4. Selecione **Adicionar escopo.**

    Selecione **salvar** na parte superior para salvar as alterações.

10. Ainda na página **expor uma API** , na área **aplicativos cliente autorizados** , selecione **Adicionar um aplicativo cliente**.

    No novo aplicativo cliente:

    1. Defina a ID do cliente como **d3590ed6-52B3-4102-AEFF-aad2292ab01c**. Esse valor é a ID de cliente do Microsoft Office e permite que o Office obtenha um token de acesso para o armazenamento de chaves.

    2. Em **escopos autorizados**, selecione o escopo de **user_impersonation** .

    3. Selecione **Adicionar aplicativo**.

    4. Selecione **salvar** na parte superior para salvar as alterações.

O armazenamento de chave do DKE agora está registrado. Continue [criando rótulos usando o DKE](#create-labels-using-dke).

## <a name="create-labels-using-dke"></a>Criar rótulos usando DKE

No centro de conformidade da Microsoft 365, crie um novo rótulo de confidencialidade e aplique a criptografia como faria de outra forma. Selecione **usar criptografia de chave dupla** e digite a URL do ponto de extremidade da sua chave.

Por exemplo:

:::image type="content" source="../media/dke-use-dke.png" alt-text="Selecione usar criptografia de chave dupla no centro de conformidade do Microsoft 365":::

Quaisquer rótulos do DKE que você adicionar serão iniciados para os usuários nas versões mais recentes dos aplicativos do Microsoft 365 para empresas.

> [!NOTE]
> Pode levar até 24 horas para que os clientes sejam atualizados com os novos rótulos.

### <a name="enable-dke-in-your-client"></a>Habilitar o DKE no cliente

Se os rótulos do DKE não aparecerem na faixa de opções de confidencialidade no Microsoft Office, o cliente pode não ter o DKE habilitado.

Habilite o DKE para o cliente adicionando as seguintes chaves do registro:

```ini
    [HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIPC\flighting]
    "DoubleKeyProtection"=dword:00000001

    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\flighting]
    "DoubleKeyProtection"=dword:00000001
```
