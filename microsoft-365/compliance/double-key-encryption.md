---
title: Criptografia de Chave Dupla (DKE)
description: O DKE permite que você proteja dados altamente confidenciais enquanto mantém o controle total de sua chave.
author: kccross
ms.author: krowley
manager: laurawi
ms.date: 01/29/2021
ms.topic: conceptual
ms.service: information-protection
audience: Admin
ms.reviewer: esaggese
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.openlocfilehash: dc6122bf3a253d5834f5f1c8c7bf935d743357ae
ms.sourcegitcommit: 50f10d83fa21db8572adab90784146e5231e3321
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/30/2021
ms.locfileid: "50058524"
---
# <a name="double-key-encryption-for-microsoft-365"></a>Criptografia de Chave Dupla para o Microsoft 365

> *Aplica-se a: Criptografia de Chave Dupla para Microsoft 365, Conformidade do [Microsoft 365,](https://www.microsoft.com/microsoft-365/business/compliance-management)Proteção de [Informações do Azure](https://azure.microsoft.com/pricing/details/information-protection)*
>
> *Instruções para: cliente [de rotulagem unificada da Proteção](https://docs.microsoft.com/azure/information-protection/faqs#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients) de Informações do Azure para Windows*
>
> *Descrição do serviço para: [Conformidade do Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*

A Criptografia de Chave Dupla (DKE) usa duas chaves juntas para acessar o conteúdo protegido. A Microsoft armazena uma chave no Microsoft Azure e você mantém a outra chave. Você mantém o controle total de uma de suas chaves usando o serviço de Criptografia de Chave Dupla. Você aplica proteção usando o cliente de rotulagem unificada da Proteção de Informações do Azure ao seu conteúdo altamente sensível.

A Criptografia de Chave Dupla dá suporte a implantações na nuvem e locais. Essas implantações ajudam a garantir que os dados criptografados permaneçam opacos onde quer que você armazene os dados protegidos.

Para obter mais informações sobre as chaves raiz de locatário padrão baseadas em nuvem, consulte Planejamento e implementação da chave de locatário da Proteção de Informações do [Azure.](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)

## <a name="when-your-organization-should-adopt-dke"></a>Quando sua organização deve adotar o DKE

A Criptografia de Chave Dupla destina-se aos seus dados mais confidenciais sujeitos aos mais rígidos requisitos de proteção. O DKE não se destina a todos os dados. Em geral, você estará usando a Criptografia de Chave Dupla para proteger apenas uma pequena parte de seus dados gerais. Você deve fazer a devida auditoria na identificação dos dados corretos a abranger com essa solução antes de implantar. Em alguns casos, talvez seja necessário restringir seu escopo e usar outras soluções para a maioria dos seus dados, como a Proteção de Informações da Microsoft com chaves gerenciadas pela Microsoft ou BYOK. Essas soluções são suficientes para documentos que não estão sujeitos a proteções e requisitos regulatórios aprimorados. Além disso, essas soluções permitem que você use os serviços mais poderosos do Office 365; serviços que você não pode usar com conteúdo criptografado DKE. Por exemplo:

- Regras de transporte, incluindo anti-malware e spam que exigem visibilidade do anexo
- Microsoft Delve
- Descoberta eletrônica
- Pesquisa e indexação de conteúdo
- Office Web Apps incluindo a funcionalidade de coautoria

Quaisquer aplicativos ou serviços externos que não estão integrados ao DKE por meio do SDK MIP não poderão executar ações nos dados criptografados.

O SDK 1.7+ da Proteção de Informações da Microsoft dá suporte à Criptografia de Chave Dupla; os aplicativos que se integram ao nosso SDK serão capazes de levar em conta esses dados com permissões e integrações suficientes.

Recomendamos que as organizações usem os recursos de proteção de informações da Microsoft (classificação e rotulagem) para proteger a maioria de seus dados confidenciais e usar somente o DKE para seus dados críticos. A Criptografia de Chave Dupla é relevante para dados confidenciais em setores altamente regulamentados, como serviços financeiros e assistência médica.

Se suas organizações têm qualquer um dos seguintes requisitos, você pode usar o DKE para ajudar a proteger seu conteúdo:

- Você deseja garantir que *apenas você possa* descriptografar o conteúdo protegido, sob todas as circunstâncias.
- Você não quer que a Microsoft tenha acesso a dados protegidos por conta própria.
- Você tem requisitos regulatórios para manter chaves dentro de um limite geográfico. Todas as chaves mantidas para criptografia e descriptografia de dados são mantidas em seu data center.

## <a name="system-and-licensing-requirements-for-dke"></a>Requisitos de sistema e licenciamento para DKE

**A Criptografia de Chave Dupla do Microsoft 365** vem com o Microsoft 365 E5. Se você não tiver uma licença do Microsoft 365 E5, inscreva-se para uma [avaliação.](https://aka.ms/M365E5ComplianceTrial) Para saber mais sobre essas licenças, confira as diretrizes de licenciamento do [Microsoft 365 para](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)segurança e & conformidade.

**Proteção de Informações do Azure.** O DKE funciona com rótulos de sensibilidade e requer a Proteção de Informações do Azure.

Os rótulos de sensibilidade DKE são disponibilizados para os usuários finais por meio da faixa de opções de sensibilidade nos Aplicativos da Área de Trabalho do Office. Instale esses pré-requisitos em cada computador cliente onde você deseja proteger e consumir documentos protegidos.

**Microsoft Office Apps for enterprise** version *.12711 or later (Desktop versions of Word, PowerPoint, and Excel) on Windows.

**Proteção de Informações do Azure Unified Labeling Client** versões 2.7.93.0 ou posterior. Baixe e instale o cliente de Rotulagem Unificada no centro [de download da Microsoft.](https://www.microsoft.com/download/details.aspx?id=53018)

## <a name="supported-environments-for-storing-and-viewing-dke-protected-content"></a>Ambientes com suporte para armazenar e exibir conteúdo protegido por DKE

**Aplicativos com suporte.** [Aplicativos do Microsoft 365 para clientes](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product) corporativos no Windows, incluindo Word, Excel e PowerPoint.

**Suporte a conteúdo online.** Documentos e arquivos armazenados online no Microsoft SharePoint e no OneDrive for Business são suportados. Você pode compartilhar conteúdo criptografado por email, mas não pode exibir documentos e arquivos criptografados online. Em vez disso, você deve exibir o conteúdo protegido usando os aplicativos da área de trabalho no computador local.

## <a name="overview-of-deploying-dke"></a>Visão geral da implantação do DKE

Você seguirá estas etapas gerais para configurar o DKE. Depois de concluir essas etapas, os usuários finais poderão proteger seus dados altamente confidenciais com a Criptografia de Chave Dupla.

1. Implante o serviço DKE conforme descrito neste artigo.

2. Crie um rótulo com Criptografia de Chave Dupla. Navegue até Proteção de Informações no centro [de conformidade do Microsoft 365](https://compliance.microsoft.com) e crie um novo rótulo com Criptografia de Chave Dupla. Confira [Restringir o acesso ao conteúdo usando rótulos de sensibilidade para aplicar criptografia.](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels)

3. Use rótulos de Criptografia de Chave Dupla. Proteja os dados selecionando o rótulo de Chave Dupla Criptografada na faixa de opções Sensibilidade do Microsoft Office.

Há várias maneiras de concluir algumas das etapas para implantar a Criptografia de Chave Dupla. Este artigo fornece instruções detalhadas para que administradores menos experientes implantem o serviço com êxito. Se você estiver confortável em fazer isso, pode optar por usar seus próprios métodos.

## <a name="deploy-dke"></a>Implantar DKE

Este artigo e o vídeo de implantação usam o Azure como o destino de implantação para o serviço DKE. Se estiver implantando em outro local, você precisará fornecer seus próprios valores.

Assista ao [vídeo de implantação](https://youtu.be/vDWfHN_kygg) da Criptografia de Chave Dupla para ver uma visão geral passo a passo dos conceitos deste artigo. O vídeo leva cerca de 18 minutos para ser concluído.

Você seguirá estas etapas gerais para configurar a Criptografia de Chave Dupla para sua organização.

1. [Instalar pré-requisitos de software para o serviço DKE](#install-software-prerequisites-for-the-dke-service)
1. [Clonar o repositório gitHub de criptografia de chave dupla](#clone-the-dke-github-repository)
1. [Modificar configurações do aplicativo](#modify-application-settings)
1. [Gerar chaves de teste](#generate-test-keys)
1. [Criar o projeto](#build-the-project)
1. [Implantar o serviço DKE e publicar o armazenamento de chaves](#deploy-the-dke-service-and-publish-the-key-store)
1. [Validar sua implantação](#validate-your-deployment)
1. [Registrar seu armazenamento de chaves](#register-your-key-store)
1. [Criar rótulos de sensibilidade usando DKE](#create-sensitivity-labels-using-dke)
1. [Habilitar DKE em seu cliente](#enable-dke-in-your-client)
1. [Migrar arquivos protegidos de rótulos HYOK para rótulos DKE](#migrate-protected-files-from-hyok-labels-to-dke-labels)

Quando terminar, você poderá criptografar documentos e arquivos usando ODKE. Para saber mais, confira [Aplicar rótulos de sensibilidade aos seus arquivos e emails no Office.](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)

### <a name="install-software-prerequisites-for-the-dke-service"></a>Instalar pré-requisitos de software para o serviço DKE

Instale esses pré-requisitos no computador onde você deseja instalar o serviço DKE.

**.NET Core 3.1 SDK**. Baixe e instale o SDK do [Download .NET Core 3.1.](https://dotnet.microsoft.com/download/dotnet-core/3.1)

**Visual Studio Code**. Baixe o Visual Studio Code de [https://code.visualstudio.com/](https://code.visualstudio.com) . Depois de instalado, execute o Visual Studio Code e selecione **Exibir** \> **Extensões.** Instale essas extensões.

- C# para Visual Studio Code

- Gerenciador de Pacotes NuGet

**Recursos do Git.** Baixe e instale um dos seguintes.

- [Git](https://git-scm.com/downloads)

- [GitHub Desktop](https://desktop.github.com/)

- [GitHub Enterprise](https://github.com/enterprise)

**OpenSSL** Você deve ter [o OpenSSL instalado](https://slproweb.com/products/Win32OpenSSL.html) para [gerar chaves de teste](#generate-test-keys) depois de implantar o DKE. Certifique-se de que você a está invocando corretamente do caminho das variáveis de ambiente. Por exemplo, consulte "Adicionar o diretório de instalação ao PATH" [https://www.osradar.com/install-openssl-windows/](https://www.osradar.com/install-openssl-windows/) para obter detalhes.

### <a name="clone-the-dke-github-repository"></a>Clonar o repositório DKE do GitHub

A Microsoft fornece os arquivos de origem DKE em um repositório do GitHub. Clone o repositório para criar o projeto localmente para uso da sua organização. O repositório GitHub DKE está localizado em [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService) .

As instruções a seguir destinam-se a usuários não qualificados do Git ou do Visual Studio Code:

1. No navegador, vá para: [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService) .

2. No lado direito da tela, selecione **Código.** Sua versão da interface do usuário pode mostrar um **clone ou botão de download.** Em seguida, no menu suspenso exibido, selecione o ícone de cópia para copiar a URL para sua área de transferência.

    Por exemplo:

   ![Clonar o repositório do serviço de Criptografia de Chave Dupla do GitHub](../media/dke-clone.png)

3. No Visual Studio Code, selecione **Exibir Paleta** \> **de Comandos** e selecione **Git: Clone**. Para ir para a opção na lista, comece a digitar para filtrar as entradas e, em seguida, `git: clone` selecione-a no drop-down. Por exemplo:

   ![Opção GIT:Clone do Visual Studio Code](../media/dke-vscode-clone.png)

4. Na caixa de texto, copie a URL que você copiou do Git e selecione **Clone no GitHub.**

5. Na caixa **de diálogo Selecionar** Pasta exibida, procure e selecione um local para armazenar o repositório. No prompt, selecione **Abrir**.

    O repositório é aberto no Visual Studio Code e exibe a ramificação atual do Git no canto inferior esquerdo. Por exemplo, a ramificação deve ser **principal.** Por exemplo:

   ![Captura de tela do repo DKE no Visual Studio Code exibindo a ramificação principal](../media/dke-vscode-main-branch.jpg)

6. Se você não estiver no branch principal, será necessário selecioná-lo. No Visual Studio Code, selecione a ramificação e escolha **principal** na lista de ramificações exibida.

   > [!IMPORTANT]
   > Selecionar a ramificação principal garante que você tenha os arquivos corretos para criar o projeto. Se você não escolher a ramificação correta, sua implantação falhará.

Agora você tem seu repositório de origem DKE definido localmente. Em seguida, [modifique as configurações do aplicativo](#modify-application-settings) para sua organização.

### <a name="modify-application-settings"></a>Modificar configurações do aplicativo

Para implantar o serviço DKE, você deve modificar os seguintes tipos de configurações de aplicativo:

- [Configurações de acesso de teclas](#key-access-settings)
- [Configurações de locatário e chave](#tenant-and-key-settings)

Modifique as configurações do aplicativo appsettings.jsarquivo on. Esse arquivo está localizado no repo DoubleKeyEncryptionService clonado localmente em DoubleKeyEncryptionService\src\customer-key-store. Por exemplo, no Visual Studio Code, você pode navegar até o arquivo conforme mostrado na imagem a seguir.

![Localizar o appsettings.jsarquivo on para DKE.](../media/dke-appsettingsjson.png)

#### <a name="key-access-settings"></a>Configurações de acesso de teclas

Escolha se quer usar a autorização de email ou função. O DKE dá suporte a apenas um desses métodos de autenticação de cada vez.

- **Autorização de email.** Permite que sua organização autorize o acesso a chaves somente com base em endereços de email.

- **Autorização de função**. Permite que sua organização autorize o acesso a chaves com base em grupos do Active Directory e exige que o serviço Web possa consultar o LDAP.

**Para definir as configurações de acesso de chave para DKE usando autorização de email**

1. Abra o **appsettings.jsno arquivo** e localize a `AuthorizedEmailAddress` configuração.

2. Adicione o endereço de email ou endereços que você deseja autorizar. Separe vários endereços de email com aspas duplas e vírgulas. Por exemplo:

   ```json
   "AuthorizedEmailAddress": ["email1@company.com", "email2@company.com ", "email3@company.com"]
   ```

3. Localize `LDAPPath` a configuração e remova o texto `If you use role authorization (AuthorizedRoles) then this is the LDAP path.` entre aspas duplas. Deixe as aspas duplas no lugar. Quando você terminar, a configuração deve ter esta aparência.

   ```json
   "LDAPPath": ""
   ```

4. Localize `AuthorizedRoles` a configuração e exclua a linha inteira.

Esta imagem mostra o **appsettings.jsno arquivo** formatado corretamente para autorização de email.

   ![O appsettings.json mostrando o método de autorização de email](../media/dke-email-accesssetting.png)

**Para definir as configurações de acesso de teclas para DKE usando a autorização de função**

1. Abra o **appsettings.jsno arquivo** e localize a `AuthorizedRoles` configuração.

2. Adicione os nomes de grupo do Active Directory que você deseja autorizar. Separe vários nomes de grupo com aspas duplas e vírgulas. Por exemplo:

   ```json
   "AuthorizedRoles": ["group1", "group2", "group3"]
   ```

3. Localize `LDAPPath` a configuração e adicione o domínio do Active Directory. Por exemplo:

   ```json
   "LDAPPath": "contoso.com"
   ```

4. Localize `AuthorizedEmailAddress` a configuração e exclua a linha inteira.

Esta imagem mostra o **appsettings.jsno arquivo** formatado corretamente para autorização de função.

   ![appsettings.jsarquivo mostrando o método de autorização de função](../media/dke-role-accesssetting.png)

#### <a name="tenant-and-key-settings"></a>Configurações de locatário e chave

As configurações de locatário e chave do DKE estão localizadas **appsettings.jsarquivo** on.

**Para definir configurações de locatário e chave para DKE**

1. Abra o **appsettings.jsno** arquivo.

2. Localize a `ValidIssuers` configuração e substitua `<tenantid>` pela ID de locatário. Você pode localizar sua ID de locatário indo para o portal do Azure e exibindo as propriedades [de locatário.](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) Por exemplo:

   ```json
   "ValidIssuers": [
     "https://sts.windows.net/9c99431e-b513-44be-a7d9-e7b500002d4b/"
   ]
   ```

Localize o `JwtAudience` . Substitua `<yourhostname>` pelo nome de host do computador onde o serviço DKE será executado. Por exemplo:

  > [!IMPORTANT]
  > O valor para `JwtAudience` deve corresponder exatamente ao nome do seu host. Você pode usar **localhost:5001** durante a depuração. No entanto, quando terminar a depuração, certifique-se de atualizar esse valor para o nome de host do servidor.

- `TestKeys:Name`. Insira um nome para sua chave. Por exemplo: `TestKey1`
- `TestKeys:Id`. Crie um GUID e insira-o como o `TestKeys:ID` valor. Por exemplo, `DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE`. Você pode usar um site como [o Gerador de GUID Online](https://guidgenerator.com/) para gerar aleatoriamente um GUID.

Esta imagem mostra o formato correto para as configurações de locatário e chaves **appsettings.jsem**. `LDAPPath` está configurada para autorização de função.

![Mostra as configurações corretas de locatário e chave para DKE no appsettings.jsarquivo on.](../media/dke-appsettingsjson-tenantkeysettings.png)

### <a name="generate-test-keys"></a>Gerar chaves de teste

Depois de definir as configurações do aplicativo, você estará pronto para gerar chaves de teste públicas e privadas.

Para gerar chaves:

1. No menu Iniciar do Windows, execute o Prompt de Comando do OpenSSL.

2. Altere para a pasta onde você deseja salvar as chaves de teste. Os arquivos que você cria concluindo as etapas dessa tarefa são armazenados na mesma pasta.

3. Gere a nova chave de teste.

   ```dos
   openssl req -x509 -newkey rsa:2048 -keyout key.pem -out cert.pem -days 365
   ```

4. Gere a chave privada.

   ```dos
   openssl rsa -in key.pem -out privkeynopass.pem
   ```

5. Gere a chave pública.

   ```dos
   openssl rsa -in key.pem -pubout > pubkeyonly.pem
   ```

6. Em um editor de texto, **abra pubkeyonly.pem**. Copie todo o conteúdo no **arquivo pubkeyonly.pem,** exceto a primeira e a última linhas, na seção do arquivo `PublicPem`appsettings.js **on.**

7. Em um editor de texto, abra **privkeynopass.pem**. Copie todo o conteúdo no arquivo **privkeynopass.pem,** exceto a primeira e a última linhas, na seção do arquivo `PrivatePem` **appsettings.json.**

8. Remova todos os espaços em branco e linhas novas nas `PublicPem` `PrivatePem` seções e nas seções.

    > [!IMPORTANT]
    > Ao copiar esse conteúdo, não exclua nenhum dos dados PEM.

9. No Visual Studio Code, navegue até o **arquivo Startup.cs** arquivo. Esse arquivo está localizado no repo DoubleKeyEncryptionService clonado localmente em DoubleKeyEncryptionService\src\customer-key-store\.

10. Localize as seguintes linhas:

   ```c#
        #if USE_TEST_KEYS
        #error !!!!!!!!!!!!!!!!!!!!!! Use of test keys is only supported for testing,
        DO NOT USE FOR PRODUCTION !!!!!!!!!!!!!!!!!!!!!!!!!!!!!
        services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
        #endif
   ```

11. Substitua essas linhas pelo seguinte texto:

   ```csharp
   services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
   ```

   Os resultados finais devem ser semelhantes aos seguintes.

   ![startup.cs para visualização pública](../media/dke-startupcs-usetestkeys.png)

Agora você está pronto para [criar seu projeto DKE.](#build-the-project)

### <a name="build-the-project"></a>Compilar o projeto

Use as instruções a seguir para criar o projeto DKE localmente:

1. No Visual Studio Code, no repositório de serviço DKE, selecione **Exibir** Paleta de Comandos e \>  digite **build** no prompt.

2. Na lista, escolha **Tarefas: Executar tarefa de com build.**

   Se não houver nenhuma tarefa de com build encontrada, selecione Configurar Tarefa **de** Com build e crie uma para o .NET Core da seguinte maneira.

   ![Configurar tarefa de com build ausente para .NET](../media/dke-configurebuildtask.png)

   1. Escolha **Criar tasks.jsa partir do modelo.**

      ![Criar tasks.jsno arquivo do modelo para DKE](../media/dke-createtasksjsonfromtemplate.png)

   2. Na lista de tipos de modelo, selecione **.NET Core**.

      ![Selecione o modelo correto para DKE](../media/dke-tasksjsontemplate.png)

   3. Na seção build, localize o caminho para o **arquivo customerkeystore.csproj.** Se não estiver lá, adicione a seguinte linha:

      ```json
      "${workspaceFolder}/src/customer-key-store/customerkeystore.csproj",
      ```

   4. Execute a com build novamente.

3. Verifique se não há erros vermelhos na janela de saída.

   Se houver erros em vermelho, verifique a saída do console. Verifique se você concluiu todas as etapas anteriores corretamente e se as versões de com build corretas estão presentes.

4. Selecione **Executar** \> **Iniciar Depuração** para depurar o processo. Se você for solicitado a selecionar um ambiente, selecione **.NET core**.

O depurador de núcleo do .NET normalmente inicia para `https://localhost:5001` . Para exibir sua chave de teste, vá `https://localhost:5001` para e aende uma barra (/) e o nome da chave. Por exemplo:

```https
https://localhost:5001/TestKey1
```

A chave deve ser exibida no formato JSON.

Sua configuração agora está concluída. Antes de publicar o repositório de chaves, em appsettings.js, para a configuração JwtAudience, certifique-se de que o valor do nome do host corresponde exatamente ao nome do host do Serviço de Aplicativo. Você pode ter alterado para localhost para solucionar problemas de com build.

### <a name="deploy-the-dke-service-and-publish-the-key-store"></a>Implantar o serviço DKE e publicar o armazenamento de chaves

Para implantações de produção, implante o serviço em uma nuvem de terceiros ou [publique em um sistema local.](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&preserve-view=true&tabs=netcore-cli)

Você pode preferir outros métodos para implantar suas chaves. Selecione o método que funciona melhor para sua organização.

Para implantações piloto, você pode implantar no Azure e começar imediatamente.

**Para criar uma instância do Azure Web App para hospedar sua implantação de DKE**

Para publicar o armazenamento de chaves, você criará uma instância do Serviço de Aplicativo do Azure para hospedar sua implantação de DKE. Em seguida, você publicará suas chaves geradas no Azure.

1. No navegador, entre no [portal do Microsoft Azure e](https://ms.portal.azure.com)vá para Adicionar serviços **de**  >  **aplicativo.**

2. Selecione sua assinatura e grupo de recursos e defina seus detalhes de instância.

    - Insira o nome de host do computador onde você deseja instalar o serviço DKE. Certifique-se de que seja o mesmo nome definido para a configuração JwtAudience noappsettings.js [**no**](#tenant-and-key-settings) arquivo. O valor que você fornece para o nome também é WebAppInstanceName.

    - Para **Publicar,** selecionar **código** e pilha **de Tempo de Execução,** selecione **.NET Core 3.1**.

    Por exemplo:

   ![Adicionar seu Serviço de Aplicativo](../media/dke-azure-add-app-service.png)

3. Na parte inferior da página, selecione **Revisar + criar** e, em seguida, selecione **Adicionar**.

4. Faça um dos seguintes para publicar suas chaves geradas:

    - [Publicar via ZipDeployUI](#publish-via-zipdeployui)
    - [Publicar via FTP](#publish-via-ftp)
    - [Publicar por meio do Visual Studio 2019 ou posterior](https://docs.microsoft.com/aspnet/core/tutorials/)

#### <a name="publish-via-zipdeployui"></a>Publicar via ZipDeployUI

1. Vá para `https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`.

    Por exemplo: https://dkeservice.scm.azurewebsites.net/ZipDeployUI

2. Na base de código do repositório de chaves, vá para a pasta **customer-key-store\src\customer-key-store** e verifique se essa pasta contém o arquivo **customerkeystore.csproj.**

3. Executar: **publicação de dotnet**

     A janela de saída exibe o diretório onde a publicação foi implantada.

    Por exemplo: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`

4. Envie todos os arquivos no diretório de publicação para um arquivo .zip. Ao criar o arquivo .zip, certifique-se de que todos os arquivos no diretório estão no nível raiz do arquivo .zip.

5. Arraste e solte o arquivo .zip criado para o site ZipDeployUI aberto acima. Por exemplo: https://dkeservice.scm.azurewebsites.net/ZipDeployUI

O DKE é implantado e você pode navegar até as chaves de teste criadas. Continue [validando sua implantação](#validate-your-deployment) abaixo.

#### <a name="publish-via-ftp"></a>Publicar via FTP

1. Conecte-se ao Serviço de Aplicativo que você [criou acima.](#deploy-the-dke-service-and-publish-the-key-store)

    No navegador, vá para: Painel FTP de Implantação Manual do Centro de Implantação do Serviço de Aplicativo do portal do **Azure.**  >    >    >    >    >  

2. Copie as cadeias de conexão exibidas para um arquivo local. Você usará essas cadeias de caracteres para se conectar ao Serviço de Aplicativo Web e carregar arquivos via FTP.

    Por exemplo:

   ![Copiar cadeias de conexão do painel FTP](../media/dke-ftp-dashboard.png)

3. Na base de código do armazenamento de chaves, vá para **o diretório customer-key-store\src\customer-key-store.**

4. Verifique se esse diretório contém o **arquivo customerkeystore.csproj.**

5. Executar: **publicação de dotnet**

    A saída contém o diretório onde a publicação foi implantada.

    Por exemplo: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`

6. Envie todos os arquivos no diretório de publicação para um arquivo zip. Ao criar o arquivo .zip, certifique-se de que todos os arquivos no diretório estão no nível raiz do arquivo .zip.

7. No cliente FTP, use as informações de conexão que você copiou para se conectar ao Serviço de Aplicativo. Carregue o arquivo .zip que você criou na etapa anterior para o diretório raiz do seu Aplicativo Web.

O DKE é implantado e você pode navegar até as chaves de teste que criou. Em seguida, [valide sua implantação.](#validate-your-deployment)

### <a name="validate-your-deployment"></a>Validar sua implantação

Depois de implantar o DKE usando um dos métodos descritos acima, valide a implantação e as configurações do armazenamento de chaves.

Execute:

src\customer-key-store\scripts\key_store_tester.ps1 dkeserviceurl/mykey

Por exemplo:

key_store_tester.ps1 https://mydkeservice.com/mykey

Certifique-se de que nenhum erro apareça na saída. Quando você estiver pronto, [registre seu armazenamento de chaves.](#register-your-key-store)

O nome da chave faz a resição entre os casos. Insira o nome da chave como ele aparece no appsettings.jsno arquivo.

## <a name="register-your-key-store"></a>Registrar seu armazenamento de chaves

As etapas a seguir permitem que você registre seu serviço DKE. Registrar seu serviço DKE é a última etapa na implantação do DKE antes de começar a criar rótulos.

Para registrar o serviço DKE:

1. No navegador, abra o [portal do Microsoft Azure e](https://ms.portal.azure.com/)vá para Todos os Registros de Aplicativo de  \> **Identidade** \> **de Serviços.**

2. Selecione **Novo registro** e insira um nome significativo.

3. Selecione um tipo de conta nas opções exibidas.

    Se você estiver usando o Microsoft Azure com um domínio não personalizado, como o **onmicrosoft.com**, selecione Contas somente neste diretório organizacional **(somente Microsoft – locatário único).**

    Por exemplo:

   ![Novo Registro de Aplicativo](../media/dke-app-registration.png)

4. Na parte inferior da página, selecione **Registrar** para criar o novo Registro de Aplicativo.

5. No novo Registro de Aplicativo, no painel esquerdo, em **Gerenciar,** selecione **Autenticação.**

6. Selecione **Adicionar uma plataforma.**

7. No **pop-up Configurar plataformas,** selecione **Web**.

8. Em **URIs de redirecionamento,** insira o URI do seu serviço de criptografia de chave dupla. Insira a URL do Serviço de Aplicativo, incluindo o nome do host e o domínio.

    Por exemplo: https://mydkeservicetest.com

    - A URL que você inserir deve corresponder ao nome do host onde seu serviço DKE está implantado.
    - Se você estiver testando localmente com o Visual Studio, use **https://localhost:5001** .
    - Em todos os casos, o esquema deve ser **https**.

    Verifique se o nome do host corresponde exatamente ao nome de host do Serviço de Aplicativo. Talvez você o tenha alterado para `localhost` solucionar problemas de com build. In **appsettings.json**, this value is the hostname you set for `JwtAudience` .

9. Em **Concessão implícita,** marque a caixa de seleção de tokens de **ID.**

10. Clique em **Salvar** para salvar suas alterações.

11. No painel esquerdo, selecione Expor **uma API** e, ao lado do URI da ID do Aplicativo, selecione **Definir.**

12. Ainda na página **Expor uma API,** nos **Escopos definidos por essa** área de API, selecione Adicionar um **escopo.** No novo escopo:

    1. Defina o nome do escopo **como user_impersonation**.

    2. Selecione os administradores e usuários que podem consentir.

    3. Defina os valores restantes necessários.

    4. Selecione **Adicionar escopo**.

    5. Selecione **Salvar** na parte superior para salvar suas alterações.

13. Ainda na página **Expor uma API,** na **área** Aplicativos cliente Autorizados, selecione Adicionar um **aplicativo cliente.**

    No novo aplicativo cliente:

    1. Defina a ID do Cliente como **d3590ed6-52b3-4102-aeff-aad2292ab01c.** Esse valor é a ID de cliente do Microsoft Office e permite que o Office obtenha um token de acesso para seu armazenamento de chaves.

    2. Em **Escopos Autorizados,** selecione **o user_impersonation** escopo.

    3. Selecione **Adicionar aplicativo**.

    4. Selecione **Salvar** na parte superior para salvar suas alterações.

Seu serviço DKE agora está registrado. Continue criando [rótulos usando DKE](#create-sensitivity-labels-using-dke).

## <a name="create-sensitivity-labels-using-dke"></a>Criar rótulos de sensibilidade usando DKE

No centro de conformidade do Microsoft 365, crie um novo rótulo de sensibilidade e aplique criptografia como faria de outra forma. Selecione **Usar Criptografia de Chave** Dupla e insira a URL do ponto de extremidade da chave.

Por exemplo:

![Selecione Usar Criptografia de Chave Dupla no centro de conformidade do Microsoft 365](../media/dke-use-dke.png)

Qualquer rótulo DKE que você adicionar começará a aparecer para os usuários nas versões mais recentes do Microsoft 365 Apps para empresas.

> [!NOTE]
> Pode levar até 24 horas para que os clientes se atualizem com os novos rótulos.

### <a name="enable-dke-in-your-client"></a>Habilitar DKE em seu cliente

Se você for um Office Insider, o DKE será habilitado para você. Caso contrário, habilita o DKE para seu cliente adicionando as seguintes chaves do Registro:

```properties
    [HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIPC\flighting]
    "DoubleKeyProtection"=dword:00000001

    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\flighting]
    "DoubleKeyProtection"=dword:00000001
```

## <a name="migrate-protected-files-from-hyok-labels-to-dke-labels"></a>Migrar arquivos protegidos de rótulos HYOK para rótulos DKE

Se você quiser, depois de terminar de configurar o DKE, poderá migrar o conteúdo que protegeu usando rótulos HYOK para rótulos DKE. Para migrar, você usará o scanner AIP. Para começar a usar o scanner, consulte O que é o scanner de rotulagem unificado da Proteção de Informações do [Azure?](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner).

Se você não migrar o conteúdo, seu conteúdo protegido HYOK permanecerá não afetado.
