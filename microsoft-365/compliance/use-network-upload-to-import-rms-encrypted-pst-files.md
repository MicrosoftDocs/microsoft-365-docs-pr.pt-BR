---
title: Usar o carregamento de rede para importar arquivos PST criptografados por RMS para o Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 84a595b8-cd77-4f66-ac52-57a33ddd4773
description: Saiba como usar o carregamento de rede para importar arquivos PST criptografados por RMS para caixas de correio de usuário no Office 365.
ms.openlocfilehash: 59aa489d6f4a3dd2545d5a2475f9e70e65529230
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2019
ms.locfileid: "40802286"
---
# <a name="use-network-upload-to-import-rms-encrypted-pst-files-to-office-365"></a>Usar o carregamento de rede para importar arquivos PST criptografados por RMS para o Office 365

**Este artigo é para administradores. Você está tentando importar arquivos PST para sua própria caixa de correio? Confira [importar email, contatos e calendário de um arquivo. pst do Outlook](https://go.microsoft.com/fwlink/p/?LinkID=785075)**
   
Use a opção de carregamento de rede e o serviço de importação do Office 365 para importar arquivos PST para caixas de correio do usuário. O carregamento de rede significa que você carrega os arquivos PST em uma área de armazenamento temporário na nuvem da Microsoft. Em seguida, o serviço de Importação do Office 365 copia os arquivos PST da área armazenamento para as caixas de correio do usuário de destino. Um novo recurso do serviço de importação permite que você criptografe seus arquivos PST antes que eles sejam carregados e armazenados na nuvem da Microsoft. Esses arquivos serão descriptografados, depois de serem importados para as caixas de correio de usuário. 
  
Estas são as etapas necessárias para criptografar e importar arquivos PST para caixas de correio do Office 365:
  
[Etapa 1: configurar o Azure Rights Management para importação de PST](#step-1-set-up-azure-rights-management-for-pst-import)

[Etapa 2: gerar uma chave de criptografia para Importação de PST](#step-2-generate-an-encryption-key-for-pst-import)

[Etapa 3: obter a ID de locatário RMS e a URL de licenciamento](#step-3-obtain-rms-tenant-id-and-licensing-url)

[Etapa 4: baixar as ferramentas de importação de PST e copiar a URL SAS](#step-4-download-the-pst-import-tools-and-copy-the-sas-url)

[Etapa 5: criptografar e carregar os arquivos PST para o Office 365](#step-5-encrypt-and-upload-your-pst-files-to-office-365)

[Opcion Etapa 6: exibir uma lista dos arquivos PST carregados para o Office 365](#optional-step-6-view-a-list-of-the-pst-files-uploaded-to-office-365)

[Etapa 7: criar o arquivo de mapeamento de importação de PST](#step-7-create-the-pst-import-mapping-file)

[Etapa 8: criar um trabalho de Importação de PST no Office 365](#step-8-create-a-pst-import-job-in-office-365)
  
> [!IMPORTANT]
> Você precisa executar a etapa 1 até a etapa 4 apenas uma vez para configurar e configurar sua organização para criptografar e importar arquivos PST para caixas de correio do Office 365. Após executar essas etapas, siga a etapa 5 à etapa 8 cada vez que desejar criptografar, carregar e importar um lote de arquivos PST. 
  
Para obter mais informações sobre como importar dados para o Office 365, consulte [visão geral da importação dos arquivos pst da sua organização para o office 365](importing-pst-files-to-office-365.md).
  
## <a name="before-you-begin"></a>Antes de começar

- A função Exportação Importação da Caixa de Correio no Exchange deve estar Online para importar arquivos PST para as caixas de correio do Office 365. Por padrão, essa função não é atribuída a nenhum grupo de funções no Exchange Online. Você pode adicionar a função Importação e Exportação de Caixa de Correio no grupo de função Gerenciamento da Organização. Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself as a member. Para mais informações, confira as seções "Adicionar uma função a um grupo de funções" ou as seções "Criar um grupo de funções" em [Gerenciar grupos de funções](https://go.microsoft.com/fwlink/p/?LinkId=730688).
    
    Além disso, para criar trabalhos de importação no Centro de Conformidade e Segurança, uma das alternativas a seguir deve ser verdadeira:
    
  - Você precisa ter a função Destinatários de email no Exchange Online. Por padrão, essa função é atribuída aos grupos de funções Gerenciamento da Organização e Gerenciamento de Destinatários.
    
    Ou
    
  - Você precisa ser um administrador global na sua organização do Office 365.
    
  > [!TIP]
  > Considere a criação de um novo grupo de função no Exchange Online destinado especificamente a importar os arquivos PST para o Office 365. Para o nível mínimo de privilégios necessários para importar os arquivos PST, atribua as funções de Exportação Importação de Caixa de Correio e Destinatários de email ao novo grupo de função e, em seguida, adicione membros. 

- Arquivos PST grandes podem impactar o desempenho do processo de importação de PST. Portanto, recomendamos que cada arquivo PST carregado no local de armazenamento do Azure na etapa 2 não tenha mais de 20 GB.
  
- É necessário armazenar os arquivos PST que você deseja importar para o Office 365 em um servidor de arquivos ou uma pasta compartilhada na sua organização.  Na etapa 5, você executará o Office 365 ImportTool, que criptografará e carregará os arquivos PST armazenados neste servidor de arquivos ou pasta compartilhada para o Office 365.
    
- Esse procedimento implica copiar e salvar a cópia de uma chave de criptografia, uma chave de armazenamento e diversas chaves de identificação e URLs. Essas informações serão usadas na etapa 5 para criptografar e carregar os arquivos PST. Não deixe de tomar medidas para proteger esse conteúdo, do mesmo modo que o faria com senhas ou outras informações relacionadas à segurança. Por exemplo, você pode salvá-las em um documento do Microsoft Word protegido por senha ou em uma unidade USB criptografada. Confira a seção [Saiba mais](#more-information) para ver exemplos de chaves, IDs e URLs. 
    
- É possível importar arquivos PST para uma caixa de correio inativa no Office 365. Isso é feito especificando o GUID da caixa de correio inativa no `Mailbox` parâmetro no arquivo de mapeamento de importação de PST. Consulte a [etapa 7](#step-7-create-the-pst-import-mapping-file) para obter mais informações. 
    
- Em uma implantação híbrida do Exchange, você pode importar arquivos PST para uma caixa de correio de arquivo morto baseada na nuvem para um usuário cuja caixa de correio principal esteja no local. Para isso, faça o seguinte no arquivo de mapeamento de Importação de PST:
    
  - Especifique o endereço de email para a caixa de correio local do usuário no `Mailbox` parâmetro. 
    
  - Especifique o valor **VERDADEIRO** no `IsArchive` parâmetro. 
    
    Consulte a [etapa 7](#step-7-create-the-pst-import-mapping-file) para obter mais informações. 
    
- Após a importação dos arquivos PST para uma caixa de correio do Office 365, a configuração de bloqueio de retenção para a caixa de correio é ativada com uma duração indefinida. Isso significa que a política de retenção atribuída à caixa de correio não será processada até que o bloqueio de retenção seja desativado ou que uma data para a desativação seja definida. Por que fazemos isso? Se as mensagens importadas para uma caixa de correio forem antigas, poderão ser excluídas permanentemente (eliminadas) porque o período de retenção expirou com base nas configurações de retenção definidas para a caixa de correio. Colocar a caixa de correio no bloqueio de retenção fornecerá ao proprietário da caixa de correio o tempo para gerenciar essas mensagens importadas recentemente ou dará tempo para alterar as configurações de retenção da caixa de correio. Consulte a seção [mais informações](#more-information) para obter sugestões sobre como gerenciar a retenção. 
    
- Se você não precisar criptografar seus arquivos PST antes de carregá-los no Office 365, confira [usar o carregamento de rede para importar arquivos pst para o Office 365](use-network-upload-to-import-pst-files.md).
    
- Para obter perguntas frequentes sobre como usar o carregamento de rede para importar arquivos PST para o Office 365, consulte [perguntas frequentes sobre a importação de arquivos pst para o office 365](faqimporting-pst-files-to-office-365.md).
  
## <a name="step-1-set-up-azure-rights-management-for-pst-import"></a>Etapa 1: configurar o Azure Rights Management para Importação de PST 

A importação de PST usa a funcionalidade de criptografia fornecida pelo serviço Azure Rights Management (Azure RMS) no Office 365. Isso permite que você criptografe arquivos PST antes de carregá-los no Office 365. 
  
A configuração do Azure RMS para importação de PST consiste em três etapas:
  
- [Ativando o Azure RMS](#activating-azure-rms)
    
- [Configurando o RMS no Exchange Online](#configuring-rms-in-exchange-online)
    
- [Instalando o cliente RMS do Active Directory](#installing-the-active-directory-rms-client)
    
### <a name="activating-azure-rms"></a>Ativando o Azure RMS

O Azure RMS está desabilitado por padrão, mas você ou outro administrador na sua organização pode ter ativado isso. Siga as instruções sobre como [ativar o Azure Rights Management](https://docs.microsoft.com/azure/information-protection/deploy-use/activate-service) para instalar e ativar o Azure DRM.
  
### <a name="configuring-rms-in-exchange-online"></a>Configurando o RMS no Exchange Online

Depois de ter ativado o serviço de gerenciamento de direitos, a próxima etapa é configurar o gerenciamento de direitos de informação (IRM) no Exchange Online para usar o Azure RMS. Para obter mais informações, consulte [Configurar o IRM para usar o Azure Rights Management](https://go.microsoft.com/fwlink/p/?LinkId=394816).
  
1. [Conecte-se ao Exchange Online usando o PowerShell remoto](https://go.microsoft.com/fwlink/p/?LinkId=396554 ).
    
2. Execute o seguinte comando para definir a URL de compartilhamento de chave do RMS.
    
    ```powershell
    Set-IRMConfiguration -RMSOnlineKeySharingLocation <RMS key sharing location>
    ```

    Use a tabela a seguir para determinar o local de compartilhamento correto da chave do RMS para o local da organização.
    
    |**Local**|**Local de compartilhamento de chave do RMS**|
    |:-----|:-----|
    |América do Norte  <br/> | `https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc` <br/> |
    |União Europeia  <br/> | `https://sp-rms.eu.aadrm.com/TenantManagement/ServicePartner.svc` <br/> |
    |Ásia  <br/> | `https://sp-rms.ap.aadrm.com/TenantManagement/ServicePartner.svc` <br/> |
    |América do Sul  <br/> | `https://sp-rms.sa.aadrm.com/TenantManagement/ServicePartner.svc` <br/> |
    |Office 365 para agências governamentais (Nuvem de Comunidade Governamental)  <br/> | `https://sp-rms.govus.aadrm.com/TenantManagement/ServicePartner.svc`<sup>1</sup> <br/> |
   
    > [!NOTE]
    > <sup>1</sup> Apenas os clientes que adquiriram os SKUs do Office 365 para agências governamentais (Nuvem de Comunidade Governamental) devem usar o local de compartilhamento de chaves RMS. 
  
    Por exemplo, este comando configura o local de compartilhamento de chave do RMS online no Exchange Online para um cliente localizado na América do Norte.
    
    ```powershell
    Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc"
    ```

3. Execute o seguinte comando para importar um domínio de publicação confiável (TPD) do RMS online para a sua organização do Office 365. 
    
    ```powershell
    Import-RMSTrustedPublishingDomain -RMSOnline -Name "RMS Online"
    ```

    Um TPD contém as configurações necessárias para usar recursos do RMS na organização, inclusive a criptografia de arquivos PST.  
    
4. Execute o seguinte comando para habilitar o IRM para sua organização do Office 365.
    
    ```powershell
    Set-IRMConfiguration -InternalLicensingEnabled $true
    ```

### <a name="installing-the-active-directory-rms-client"></a>Instalando o cliente RMS do Active Directory

A última etapa desta seção consiste em baixar o Rights Management Services Client 2.1 (RMS). Esse software ajuda a proteger o acesso ao Azure RMS e protege as informações que usam os aplicativos que usam o Azure RMS. Instale o cliente RMS no mesmo computador que você usará para criptografar e carregar arquivos PST na etapa 5. 
  
1. Baixe o [cliente do serviço de gerenciamento de direitos 2,1](https://www.microsoft.com/download/details.aspx?id=38396).
    
2. Execute o assistente do Rights Management Service Client 2.1 do Active Directory para instalar o cliente.

## <a name="step-2-generate-an-encryption-key-for-pst-import"></a>Etapa 2: gerar uma chave de criptografia para Importação de PST

Depois de configurar o Azure RMS, a próxima etapa é gerar uma chave de criptografia (chamada de chave simétrica) que será usada para criptografar os arquivos PST que você carrega no Office 365. Você fará isso adicionando o serviço de importação de PST como uma entidade de serviço no Azure Active Directory. Adicionar este aplicativo como uma entidade de serviço permitirá que o serviço de importação de PST autentique diretamente com o Azure Active Directory quando você carregar arquivos PST criptografados no local de armazenamento do Azure na etapa 5.
  
1. Inicie o módulo do Azure Active Directory para Windows PowerShell.
    
2. Execute o seguinte comando para se conectar ao serviço do Microsoft Online.
    
    ```powershell
    Connect-MsolService
    ```

3. Insira as credenciais de uma conta de administrador na sua organização do Office 365 e clique em **OK**.
    
4. Execute o seguinte comando para gerar uma chave de criptografia ou chave simétrica. Para fazer isso, crie uma nova entidade de criptografia de PST.
    
    ```powershell
    New-MsolServicePrincipal -DisplayName PstEncryptionPrincipal
    ```

    O sistema exibe a chave simétrica e as propriedades da nova entidade de criptografia de PST.
    
    ![Copiar e salvar a chave simétrica que é exibida](media/0003fdea-dace-41d2-b49d-f5c98c6230ca.png)
  
5. Copie a chave simétrica em um arquivo de texto ou no Word. Conforme mencionamos, não deixe de tomar medidas para proteger esse arquivo. Como essa é a única ocasião em que o sistema exibe a chave simétrica, considere fazer uma captura de tela da janela e salvá-la no mesmo arquivo.  
    
    > [!IMPORTANT]
    > Depois de criar a entidade de criptografia de PST, o sistema não permite recuperar a chave simétrica usando o cmdlet **Get-MsolServicePrincipal**. Por isso é importante salvar a chave. 
  
Mantenha o módulo do Azure Active Directory para Windows PowerShell aberto e conectado ao serviço online da Microsoft. Na etapa a seguir, você executará um comando nessa janela.

## <a name="step-3-obtain-rms-tenant-id-and-licensing-url"></a>Etapa 3: obter a ID de locatário RMS e a URL de licenciamento

A próxima etapa é obter a ID do locatário e a URL do local de licenciamento para o serviço do Azure RMS para sua organização. Copie e salve essas informações no mesmo arquivo que contém a chave simétrica da etapa 2. A ID e a URL serão usadas na etapa 5 para criptografar os arquivos PST.
  
1. No módulo do Azure Active Directory para Windows PowerShell (que está conectado ao serviço do Microsoft Online), execute o seguinte comando para se conectar ao serviço do Azure RMS na sua organização do Office 365.
    
    ```powershell
    Connect-AadrmService 
    ```

2. Insira as credenciais de uma conta de administrador na sua organização do Office 365 e clique em **OK**.
    
3. Execute o seguinte comando para exibir a ID de locatário para o serviço do Azure RMS na sua organização do Office 365.
    
    ```powershell
    Get-AadrmConfiguration | FL BPOSId
    ```

    Copie e salve o valor da `BPOSId` propriedade. 
    
4. Execute o comando a seguir para exibir a localização de licenciamento para o serviço do Azure RMS.
    
    ```powershell
    Get-AadrmConfiguration | FL LicensingIntranetDistributionPointUrl
    ```

    Copie e salve o valor da `LicensingIntranetDistributionPointUrl` propriedade. 

## <a name="step-4-download-the-pst-import-tools-and-copy-the-sas-url"></a>Etapa 4: baixar as ferramentas de importação de PST e copiar a URL SAS

Agora que você configurou o Azure RMS e obteve as IDs necessárias para criptografar arquivos PST, a próxima etapa é baixar e instalar as ferramentas que serão executadas na etapa 5 para criptografar e carregar arquivos PST para o Office 365. Essas ferramentas são a ferramenta AzCopy do Azure e a ferramenta de criptografia de dados do Office 365. Você também copiará a URL SAS de sua organização. Essa URL é uma combinação da URL de rede para o local de armazenamento do Azure na nuvem da Microsoft para a sua organização e uma chave de Assinatura de Acesso Compartilhado (SAS). Essa chave fornece as permissões necessárias para carregar arquivos PST no local de armazenamento do Azure. Salve-o no mesmo arquivo em que você copiou as outras informações na etapa 2 e na etapa 3. Conforme mencionado anteriormente, tome precauções para proteger a URL SAS. 
  
> [!IMPORTANT]
> Você precisa usar o Azure AzCopy versão 5,0 para carregar com êxito os arquivos PST para o local de armazenamento do Azure. Versões mais recentes da ferramenta AzCopy não são suportadas para importar arquivos PST para o Office 365. Certifique-se de baixar a ferramenta AzCopy da página **carregar arquivos pela rede** , seguindo os procedimentos nesta etapa. 
  
1. Acesse [https://protection.office.com](https://protection.office.com).
    
2. Entre no Office 365 usando as credenciais de uma conta de administrador na sua organização do Office 365.
    
3. No painel esquerdo, clique em **** \> **importar** \> **arquivos PST de importação**de governança de informações.
    
4. Na página **importar arquivos PST** , clique em **ir para o serviço de importação**.
    
5. Na página **importar dados para o Office 365** , clique em **novo trabalho** ![adicionar](media/ITPro-EAC-AddIcon.gif)ícone e, em seguida, clique em **carregar mensagens de email (arquivos PST)**.
    
6. Na página **carregar arquivos pela rede** , na etapa 2, clique em **Mostrar URL SAS de carregamento de rede**.
    
7. Depois que a URL for exibida, copie-a e salve-a no arquivo em que você salvou as outras chaves. Não deixe de copiar a URL inteira. 
    
8. Na etapa 3, clique em **baixar a ferramenta AzCopy do Azure** para baixar e instalar a ferramenta do Azure AzCopy. 
    
9. Clique em **Executar**, na janela pop-up, para instalar a ferramenta AzCopy do Microsoft Azure. 
    
    > [!IMPORTANT]
    > Certifique-se de instalar a ferramenta AzCopy do Azure no local padrão, que `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy` está em um computador que executa o Windows de 64 bits. Isso ocorre porque quando você executa o O365ImportTool. exe na etapa 5, ele procura a ferramenta AzCopy neste local. 
  
10. Após a instalação da ferramenta AzCopy do Azure, clique em **baixar a ferramenta de criptografia e importação de dados do Office 365**.
    
11. Na janela pop-up, clique em **salvar** \> **salvar como** para salvar o arquivo O365ImportTool. zip em uma pasta no computador local. 
    
12. Extraia o arquivo O365ImportTool.zip.
    
13. Clique em **Cancelar** para fechar a página **carregar arquivos pela rede** . 
 
## <a name="step-5-encrypt-and-upload-your-pst-files-to-office-365"></a>Etapa 5: criptografar e carregar os arquivos PST para o Office 365

Após concluir a etapa 1 até a etapa 4, você está pronto para usar a ferramenta O365ImportTool. exe para criptografar e carregar arquivos PST para o Office 365. Essa ferramenta criptografa seus arquivos PST e, em seguida, carrega e os armazena em um local de armazenamento do Azure na nuvem da Microsoft. Para concluir essa etapa, você deve colocar os arquivos PST em um compartilhamento de arquivos ou servidor de arquivos da organização. Esse local é conhecido como diretório de origem no procedimento a seguir. Sempre que executar a ferramenta O365ImportTool.exe, você pode especificar um diretório de origem diferente. 

> [!NOTE]
> Conforme mencionado anteriormente, cada arquivo PST que você carrega para o local de armazenamento do Azure não deve ser maior do que 20 GB. Arquivos PST maiores que 20 GB podem impactar o desempenho do processo de importação de PST que você iniciou na etapa 8.
  
1. Abra um prompt de comando no computador local.
    
2. Vá para o diretório em que instalou a ferramenta O365ImportTool.exe na etapa 4.
    
3. Execute o seguinte comando para criptografar e carregar arquivos PST para o Office 365.
    
    ```powershell
    O365ImportTool.exe /srcdir:<Location of PST files> /protect-rmsserver:<RMS licensing location> /protect-tenantid:<BPOSId> /protect-key:<Symmetric key> /transfer:upload /upload-dest:<Network upload URL> /upload-destSAS:<SAS key>
    ```

    A tabela a seguir descreve os parâmetros e os valores necessários.  As informações obtidas nas etapas anteriores são usadas nos valores desses parâmetros.
    
    |**Parâmetro**|**Descrição**|**Exemplo**|
    |:-----|:-----|:-----|
    | `/srcdir:` <br/> |Especifica o diretório de origem na organização que contém os arquivos PST a serem carregados no Office365.  <br/> | `/srcdir:\\FILESERVER01\PSTs` <br/> |
    | `/protect-rmsserver:` <br/> |Especifica o local de licenciamento para o serviço do Azure RMS. Use o valor da `LicensingIntranetDistributionPointUrl` propriedade que você obteve na etapa 3. Certifique-se de colocar o valor deste parâmetro com aspas duplas ("")  <br/> | `/protect-rmsserver:"https://afcbd8ec-cb2b-4a1a-8246-0b4bc22d1978.rms.na.aadrm.com/_wmcs/licensing"` <br/> |
    | `/protect-tenantid:` <br/> |Especifica a identidade da sua organização do Azure RMS. Use o valor da `BPOSId` propriedade que você obteve na etapa 3.  <br/> | `/protect-tenantid:42745b33-2a5c-4726-8a2a-ca43caa0f74b` <br/> |
    | `/protect-key:` <br/> |Especifica a chave simétrica obtida na etapa 2. Certifique-se de colocar o valor deste parâmetro entre aspas duplas (" ").  <br/> | `/protect-key:"l+R+Umc5RGmSBh1oW+DoyMxm/h5h2JJXFcNOFiNp867="` <br/> |
    | `/transfer:` <br/> |Especifica se deve carregar os arquivos PST pela rede ou enviá-los em um disco rígido. O valor `upload` indica que você está carregando os arquivos pela rede. O valor `drive` indica que você está enviando PSTs em um disco rígido.  <br/> | `/transfer:upload` <br/> |
    | `/upload-dest:` <br/> |Especifica o destino no Office 365 onde seus arquivos PST serão carregados; Este é o local de armazenamento do Azure para sua organização. O valor desse parâmetro consiste na URL de carregamento de rede da URL SAS que você copiou na etapa 4. Certifique-se de colocar o valor deste parâmetro entre aspas duplas (" ").  <br/><br/> **Dica:** (opcional) você pode especificar uma subpasta no local de armazenamento do Azure para carregar os arquivos PST criptografados para o. Para fazer isso, adicione um local de subpasta (após "ingestiondata") na URL de carregamento de rede. O primeiro exemplo não especifica uma subpasta; Isso significa que os PSTs serão carregados para a raiz (chamada *ingestiondata*) do local de armazenamento do Azure. O segundo exemplo carrega os arquivos PST em uma subpasta (chamada *EncryptedPSTs*) no local de armazenamento do Azure.           | `/upload-dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata"` <br/> Ou  <br/>  `/upload-dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata/EncryptedPSTs"` <br/> |
    | `/upload-destSAS:` <br/> |Especifica a chave SAS para sua organização. O valor desse parâmetro consiste na chave SAS da URL SAS que você copiou na etapa 4. O primeiro caractere da chave SAS é um ponto de interrogação ("?"). Certifique-se de colocar o valor deste parâmetro entre aspas duplas (" ").<br/><br/>**Observação:** Se você usar a URL SAS em um arquivo de script ou de lote, você precisará observar alguns caracteres que precisam ser precedidos. Por exemplo, você precisa `%` alterar para `%%` e alterar `&` para. `^&` | `/upload-destSAS:"?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"` <br/> |
    | `/recurse` <br/> |Essa opção opcional especifica o modo recursivo para que a ferramenta O365ImportTool. exe copie arquivos PST localizados em subpastas no diretório de origem especificado pelo `/srcdir:` parâmetro.  <br/><br/> **Observação:** Se incluir esse botão, os arquivos PST das subpastas terão nomes de caminho de arquivo diferentes, depois de carregá-los no local de armazenamento do Azure. Você terá de especificar o nome de caminho de arquivo exato no arquivo CSV que criar na etapa 7.           | `/recurse` <br/> |
   
    Veja um exemplo da sintaxe para a ferramenta O365ImportTool.exe, que usa valores reais para os parâmetros:
    
    ```powershell
    O365ImportTool.exe /srcdir:\\FILESERVER01\PSTs /protect-rmsserver:"https://afcbd8ec-cb2b-4a1a-8246-0b4bc22d1978.rms.na.aadrm.com/_wmcs/licensing" /protect-tenantid:42745b33-2a5c-4726-8a2a-ca43caa0f74b  /protect-key:"l+R+Umc5RGmSBh1oW+DoyMxm/h5h2JJXFcNOFiNp867=" /transfer:upload /upload-dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata" /upload-destSAS:"?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"
    ```

    Depois de executar o comando, o sistema exibe mensagens de status que mostram o andamento da criptografia e do carregamento dos arquivos PST. Uma mensagem de status final mostra o número total de arquivos que foram criptografados e carregados com êxito.  
    
    > [!TIP]
    > Depois de executar o comando O365ImportTool.exe com êxito e verificar se todos os parâmetros estão corretos, salve uma cópia da sintaxe da linha de comando no mesmo arquivo (protegido) em que copiou as informações obtidas nas etapas anteriores. Em seguida, você pode copiar e colar este comando em um prompt de comando sempre que desejar executar a ferramenta O365ImportTool. exe para criptografar e carregar arquivos PST para o Office 365. Os únicos valores que você pode ter de alterar são aqueles para os `/srcdir:` parâmetros `/upload-dest:` e. 
  
## <a name="optional-step-6-view-a-list-of-the-pst-files-uploaded-to-office-365"></a>Opcion Etapa 6: exibir uma lista dos arquivos PST carregados para o Office 365

Como uma etapa opcional, você pode instalar e usar o Microsoft Azure Storage Explorer (que é uma ferramenta de código aberto gratuita) para exibir a lista dos arquivos PST que você carregou para o blob do Azure. Há três boas razões para fazer isso:
  
- Verifique se os arquivos PST da pasta compartilhada ou servidor de arquivos em sua organização foram carregadas com êxito para o blob do Azure.

- Verifique se os arquivos PST são criptografados. Arquivos PST criptografados têm `.pfile` uma extensão acrescentada ao nome de arquivo PST; por exemplo, `pilarp.pst.pfile`.
    
- Verifique se o nome do arquivo (e o nome do caminho da subpasta, se você incluiu um) para cada arquivo PST carregado para o blob do Azure. Isso será muito útil quando você estiver criando o arquivo de mapeamento PST na próxima etapa porque será preciso especificar o nome do caminho da pasta e o nome do arquivo para cada arquivo PST. Verificar esses nomes pode ajudar a reduzir possíveis erros no arquivo de mapeamento PST.
    
O Gerenciador de Armazenamento do Microsoft Azure está em Prévia. 
  
 > [!IMPORTANT]
>  Não é possível usar o Gerenciador de Armazenamento do Azure para carregar ou modificar arquivos PST. O único método com suporte para a importação de arquivos PST para o Office 365 é o AzCopy. Além disso, não é possível excluir os arquivos PST que você carregou no blob do Azure. Se tentar excluir um arquivo PST, você receberá uma mensagem de erro informando que você não tem as permissões necessárias. Todos os arquivos PST são excluídos automaticamente da sua área de armazenamento do Azure. Se não houver trabalhos de importação em andamento, todos os arquivos PST no contêiner **ingestiondata** serão excluídos 30 dias após a criação do trabalho de importação mais recente. 
  
Para instalar o Gerenciador de Armazenamento do Azure e se conectar à sua área de armazenamento do Azure:
  
1. Baixe e instale a [Ferramenta Gerenciador de Armazenamento do Microsoft Azure ](https://go.microsoft.com/fwlink/p/?LinkId=544842).
    
2. Inicie o Gerenciador de armazenamento do Microsoft Azure, clique com o botão direito do mouse em **Contas de Armazenamento** no painel esquerdo e clique em **Conectar-se ao Armazenamento do Azure**. 
    
    ![Clique com o botão direito em Contas de Armazenamento em Conectar-se ao Armazenamento do Azure](media/75b80cc3-c336-4f96-ad32-54ac9b96a7af.png)
  
3. Na caixa em **conectar ao armazenamento do Azure**, Cole a URL SAS obtida na etapa 4 e clique em **Avançar**. 
    
    ![Cole a URL SAS na caixa na página conectar ao Azure Storage](media/5d034128-e087-48e1-9ebc-4c9fa262d5b7.png)
  
4. Na página **Resumo da conexão**, você pode revisar as informações de conexão e, em seguida, clique em **Conectar**. 
    
5. Em **contas de armazenamento**, expanda o nó **(associações de serviço)** e, em seguida, expanda o nó **contêineres blob** . 
    
6. Clique com o botão direito do mouse em **ingestiondata**e clique em **Abrir Editor de contêiner de blob**.
    
    ![Clique com o botão direito em ingestiondata e clique em Abrir Editor de Contêiner de Blob.](media/f50eee30-9202-4efc-904a-2895a0bc388d.png)
  
    A área de armazenamento do Azure, com uma lista dos arquivos PST carregados na etapa 5, é exibida.
    
    ![O Gerenciador de Armazenamento do Azure exibe uma lista dos arquivos PST que você carregou](media/a448ae43-e744-4153-8304-22b59e93883c.png)
  
7. Ao terminar de usar o Gerenciador de Armazenamento do Azure, clique com botão direito em **ingestiondata** e, em seguida, clique em **Desanexar** para desconectar-se da sua área de armazenamento do Azure. Caso contrário, você receberá uma mensagem de erro na próxima vez que tentar anexar. 
    
    ![Clique com o botão direito em ingestão e clique em Desanexar para desconectar da sua área de armazenamento do Azure](media/1e8e5e95-4215-4ce4-a13d-ab5f826a0510.png)
  
## <a name="step-7-create-the-pst-import-mapping-file"></a>Etapa 7: criar o arquivo de mapeamento de importação de PST

Após os arquivos PST terem sido criptografados e carregados no local de armazenamento do Azure para sua organização do Office 365, a próxima etapa é criar um arquivo de valor separado por vírgula (CSV) que especifica quais caixas de correio de usuário serão importadas. Você enviará esse arquivo CSV na etapa seguinte, quando criar um trabalho de Importação de PST.
  
1. [Baixar uma cópia do arquivo de mapeamento para importação de PST](https://go.microsoft.com/fwlink/p/?LinkId=544717). 
    
2. Abrir ou salvar o arquivo CSV no computador local. O exemplo a seguir mostra um arquivo de mapeamento para Importação de PST concluído (aberto no Bloco de notas). É muito mais fácil usar o Microsoft Excel para editar o arquivo CSV.
    
    ```text
    Workload,FilePath,Name,Mailbox,IsArchive,TargetRootFolder,ContentCodePage,SPFileContainer,SPManifestContainer,SPSiteUrl
    Exchange,,annb.pst.pfile,annb@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,,annb_archive.pst.pfile,annb@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,,donh.pst.pfile,donh@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,,donh_archive.pst.pfile,donh@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,EncryptedPSTs,pilarp.pst.pfile,pilarp@contoso.onmicrosoft.com,FALSE,,,,,
    Exchange,EncryptedPSTs,pilarp_archive.pst.pfile,pilarp@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,EncryptedPSTs,tonyk.pst.pfile,tonyk@contoso.onmicrosoft.com,FALSE,,,,,
    Exchange,EncryptedPSTs,tonyk_archive.pst.pfile,tonyk@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,EncryptedPSTs,zrinkam.pst.pfile,zrinkam@contoso.onmicrosoft.com,FALSE,,,,,
    Exchange,EncryptedPSTs,zrinkam_archive.pst.pfile,zrinkam@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    ```

    A primeira linha ou linha de cabeçalho do arquivo CSV enumera os parâmetros que serão usados pelo serviço de Importação de PST para importar os arquivos PST para as caixas de correio de usuário. Os nomes dos parâmetros são separados por vírgula. Cada linha sob a linha de cabeçalho representa os valores de parâmetro para a importação de um arquivo PST em uma caixa de correio específica. Use uma linha para cada arquivo PST que deseja importar para uma caixa de correio de usuário. Não deixe de substituir os dados de espaço reservado do arquivo de mapeamento pelos dados reais.
    
    > [!NOTE]
    > Não altere o conteúdo da linha de cabeçalho, inclusive os parâmetros SharePoint; eles serão ignorados durante o processo de Importação de PST. 
  
3. Use as informações da tabela a seguir para preencher o arquivo CSV com as informações necessárias.
    
    |**Parâmetro**|**Descrição**|**Exemplo**|
    |:-----|:-----|:-----|
    | `Workload` <br/> |Especifica o serviço do Office 365 para o qual os dados serão importados. Para importar arquivos PST nas caixas de correio de usuário, use o  `Exchange`.  <br/> | `Exchange` <br/> |
    | `FilePath` <br/> |Especifica o local da pasta no local de armazenamento do Azure em que você carregou os arquivos PST na etapa 5.  <br/>  Se você não incluir um nome de subpasta opcional na URL de rede `/upload-dest:` no parâmetro da etapa 5, deixe esse parâmetro em branco no arquivo CSV. Se você tiver incluído um nome de subpasta, especifique-o nesse parâmetro. O valor desse parâmetro diferencia maiúsculas de minúsculas. De qualquer forma, *não* inclua "ingestiondata" no valor do `FilePath` parâmetro.  <br/> <br/>**Importante:** O caso do nome do caminho do arquivo deve ser o mesmo caso que você usou se você tiver incluído um nome de subpasta opcional na URL `/upload-dest:` SAS no parâmetro da etapa 5. Por exemplo, se você usou `EncryptedPSTs` para o nome da subpasta na etapa 5 e `encryptedpsts` usar no `FilePath` parâmetro no arquivo CSV, a importação do arquivo PST falhará. Certifique-se de usar a mesma capitalização nas duas instâncias.           |(deixar em branco)  <br/> Ou  <br/>  `EncryptedPSTs` <br/> |
    | `Name` <br/> |Especifique o nome do arquivo PST que será importado para a caixa de correio do usuário. O valor desse parâmetro diferencia maiúsculas de minúsculas. Como os arquivos PST carregados para o local de armazenamento do Azure são criptografados, `.pfile` uma extensão é adicionada ao nome de arquivo PST. Você deve adicionar a `.pfile` extensão ao nome dos arquivos pst no arquivo CSV.  <br/><br/> **Importante:** O caso do nome de arquivo PST no arquivo CSV deve ser igual ao arquivo PST que foi carregado no local de armazenamento do Azure na etapa 5. Por exemplo, se você usar `annb.pst.pfile` o `Name` no parâmetro no arquivo CSV, mas o nome do arquivo PST atual  para `AnnB.pst`, a importação desse arquivo PST falhará. Certifique-se de que o nome do PST no arquivo CSV usa a mesma capitalização do arquivo PST atual.           | `annb.pst.pfile` <br/> |
    | `Mailbox` <br/> |Especifica o endereço de email da caixa de correio para a qual o arquivo PST será importado.  <br/> Para importar um arquivo PST para uma caixa de correio inativa, é preciso especificar o GUID da caixa de correio para esse parâmetro. Para obter esse GUID, execute o seguinte comando do PowerShell no Exchange Online:  `Get-Mailbox -InactiveMailboxOnly <identity of inactive mailbox> | FL Guid` <br/><br/> **Observação:** Em alguns casos, você pode ter várias caixas de correio com o mesmo endereço de email, em que uma caixa de correio está ativa e a outra caixa de correio está em um estado de exclusão reversível (ou inativa). Nesses casos, você precisa especificar o GUID da caixa de correio para identificar exclusivamente a caixa de correio para a qual o arquivo PST será importado. Para obter esse GUID para caixas de correio ativas, execute o seguinte comando do PowerShell:  `Get-Mailbox - <identity of active mailbox> | FL Guid`. Para obter o GUID das caixas de correio excluídas por software (ou inativo), execute este comando`Get-Mailbox - <identity of soft-deleted or inactive mailbox> -SoftDeletedMailbox | FL Guid`           | `annb@contoso.onmicrosoft.com` <br/> Ou  <br/>  `2d7a87fe-d6a2-40cc-8aff-1ebea80d4ae7` <br/> |
    | `IsArchive` <br/> | Especifica se deve ou não importar o arquivo PST para a caixa de correio de arquivo morto do usuário. Há duas opções:  <br/> **False** Importa o arquivo PST para a caixa de correio principal do usuário.  <br/> **True** Importa o arquivo PST para a caixa de correio de arquivo morto do usuário.  <br/>  Se você deixar este parâmetro em branco, o arquivo PST será importado para a caixa de correio principal do usuário.  <br/><br/> **Observação:** Para importar um arquivo PST para uma caixa de correio de arquivo morto baseado na nuvem para um usuário cuja caixa de correio principal esteja no local, basta especificar **true** para esse parâmetro e especificar o endereço de email da caixa de correio `Mailbox` local do usuário para o parâmetro.           | `FALSE` <br/> Ou  <br/>  `TRUE` <br/> |
    | `TargetRootFolder` <br/> | Especifica a pasta da caixa de correio para a qual o arquivo PST será importado.  <br/>  Se você deixar esse parâmetro em branco, o PST será importado para uma nova pasta denominada **importada** localizada no nível raiz da caixa de correio (o mesmo nível que a pasta caixa de entrada e as outras pastas de caixa de correio padrão).  <br/>  Se você especificar `/`, os itens no arquivo PST serão importados diretamente para a pasta caixa de entrada do usuário.  <br/>  Se você especificar `/<foldername>`, os itens no arquivo PST serão importados para uma subpasta chamada * \<nome_da_pasta\> * . Por exemplo, se você usou `/ImportedPst`, os itens seriam importados para uma subpasta chamada **ImportedPst**. Essa subpasta estará localizada na pasta caixa de entrada do usuário.  <br/><br/> **Dica:** Considere a execução de alguns lotes de teste para experimentar esse parâmetro para que você possa determinar o melhor local da pasta para importar arquivos PST.           |(deixar em branco)  <br/> Ou  <br/>  `/` <br/> Ou  <br/>  `/ImportedPst` <br/> |
    | `ContentCodePage` <br/> |Esse parâmetro opcional especifica um valor numérico para a página do código a ser usado para importar arquivos PST no formato de arquivo ANSI. Esse parâmetro é usado para importar arquivos PST de organizações em chinês, japonês e coreano (CJK) porque esses idiomas geralmente usam um DBCS (conjunto de caracteres de dois bytes) para codificação de caracteres. Se esse parâmetro não for usado para importar arquivos PST para idiomas que usam DBCS para nomes de pasta de caixa de correio, os nomes das pastas geralmente ficam incorretos após a importação. Para obter uma lista de valores com suporte para esse parâmetro, confira [Identificadores de Página de Código](https://go.microsoft.com/fwlink/p/?LinkId=328514).  <br/><br/> **Observação:** Como mencionado anteriormente, esse é um parâmetro opcional, e você não precisa incluí-lo no arquivo CSV. Ou você pode incluí-lo e deixar o valor em branco para uma ou mais linhas.           |(deixar em branco)  <br/> Ou  <br/>  `932` (que é o identificador da página de código para ANSI/OEM japonês)  <br/> |
    | `SPFileContainer` <br/> |Deixe este parâmetro em branco para Importação de PST.  <br/> |Não aplicável  <br/> |
    | `SPManifestContainer` <br/> |Deixe este parâmetro em branco para Importação de PST.  <br/> |Não aplicável  <br/> |
    | `SPSiteUrl` <br/> |Deixe este parâmetro em branco para Importação de PST.  <br/> |Não aplicável  <br/> |
  
## <a name="step-8-create-a-pst-import-job-in-office-365"></a>Etapa 8: criar um trabalho de Importação de PST no Office 365

A última etapa é criar o trabalho de importação de PST no serviço de importação do Office 365. Conforme explicamos, você vai enviar o arquivo de mapeamento para Importação de PST criado na etapa 7. Depois de criar o novo trabalho, o serviço de importação usará as informações no arquivo de mapeamento para descriptografar e importar os arquivos PST (que você carregou para o Office 365 na etapa 5) na caixa de correio do usuário especificado. 
  
1. Acesse [https://protection.office.com](https://protection.office.com).
    
2. Entre no Office 365 usando as credenciais de uma conta de administrador na sua organização do Office 365.
    
3. No painel esquerdo, clique em **governança de informações > importar > importar arquivos PST**.
    
4. Na página **importar arquivos PST** , clique em **ir para o serviço de importação**.
    
5. Na página **importar dados para o Office 365** , clique em **novo trabalho**![adicionar](media/ITPro-EAC-AddIcon.gif)ícone e, em seguida, clique em **carregar mensagens de email (arquivos PST)**.
    
6. Na página **Carregar dados pela rede**, marque as caixas de seleção **Eu acabei de carregar os meus arquivos** e **Eu tenho acesso ao arquivo de mapeamento** e clique em **Avançar**.  
    
7. Digite um nome para o trabalho de Importação de PST e clique em **Avançar**.
    
8. Clique em **Adicionar** ![ícone](media/ITPro-EAC-AddIcon.gif) de adição para selecionar o arquivo de mapeamento de PST que você criou na etapa 7. 
    
9. Quando o nome do arquivo CSV for exibido na lista, selecione-o e clique em **Validar** para verificar se há falhas no arquivo.  
    
    > [!NOTE]
    > Como explicado anteriormente, quando os arquivos PST são criptografados `.pfile` , uma extensão é acrescentada ao nome de arquivo PST. Você deve adicionar a `.pfile` extensão ao nome dos arquivos pst no arquivo CSV. Caso contrário, a validação do arquivo CSV vai apresentar falha. 
  
    Você deve validar o arquivo CSV com êxito para poder criar um trabalho de Importação de PST. Se a validação falhar, clique no link **Inválida**, na coluna **Status**. Uma cópia do arquivo de mapeamento de importação de PST é aberta, com uma mensagem de erro para cada linha no arquivo que falhou. 
    
10. Quando validar o arquivo de mapeamento para Importação de PST com êxito, leia o documento de termos e condições e marque a caixa de seleção.
    
11. Clique em **Concluir** para enviar o trabalho. 
    
    O trabalho é exibido na lista de trabalhos de importação de PST na página **importar dados para o Office 365** . 
    
12. Selecione o trabalho e clique em **Atualizar**![ícone](media/O365-MDM-Policy-RefreshIcon.gif) de atualização para atualizar as informações de status exibidas no painel de detalhes. 
    
13. No painel de detalhes, clique em **Exibir detalhes** para conferir o status mais recente do trabalho escolhido. 
 
## <a name="more-information"></a>Mais informações

- Por que importar arquivos PST para o Office 365?
    
  - É uma boa maneira de migrar o email da sua organização para o Office 365.
    
  - Isso ajuda a atender às necessidades de conformidade da organização, permitindo:
    
  - Habilitar as caixas de correio de arquivo morto para conceder mais espaço de armazenamento de caixa de correio aos usuários.
    
  - Colocar as caixas de correio em retenção para preservar o conteúdo.
    
  - Use as ferramentas de Descoberta Eletrônica da Microsoft para pesquisar conteúdo em caixas de correio.
    
  - Use Políticas de Retenção para controlar o tempo de retenção do conteúdo da caixa de correio.
    
  - Pesquise o log de auditoria do Office 365 para eventos relacionados à caixa de correio.
    
  - Este recurso ajuda na proteção contra perda de dados. Arquivos PST que são importados para as caixas de correio do Office 365 herdam os recursos de alta disponibilidade do Exchange Online, em vez de armazenar os dados no computador de um usuário.
    
  - Os dados ficam disponíveis para o usuário em todos os dispositivos, pois eles são armazenados na nuvem.
    
- Veja um exemplo das chaves, IDs e URLs obtidas nas etapas 2, 3 e 4. Este exemplo também contém a sintaxe do comando executado na ferramenta O365ImportTool. exe para criptografar e carregar arquivos PST para o Office 365. Não deixe de tomar medidas para proteger esse conteúdo, do mesmo modo que o faria com senhas ou outras informações relacionadas à segurança.
    
  ```text
  Symmetric key: l+R+Umc5RGmSBh1oW+DoyMxm/h5h2JJXFcNOFiNp867=

  BPOSId: 42745b33-2a5c-4726-8a2a-ca43caa0f74b

  LicensingIntranetDistributionPointUrl (RMS licensing location): https://afcbd8ec-cb2b-4a1a-8246-0b4bc22d1978.rms.na.aadrm.com/_wmcs/licensing
  
  SAS URL: https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D
  
  O365ImportTool.exe /srcdir:<Location of PST files> /protect-rmsserver:<RMS licensing location> /protect-tenantid:<BPOSId> /protect-key:<Symmetric key> /transfer:upload /upload-dest:<Network upload URL from the SAS URL> /upload-destSAS:<SAS key from the SAS URL>
  
  EXAMPLES
  
  This example uploads PST files to the root of the Azure storage location:

  O365ImportTool.exe /srcdir:\\FILESERVER01\PSTs /protect-rmsserver:"https://afcbd8ec-cb2b-4a1a-8246-0b4bc22d1978.rms.na.aadrm.com/_wmcs/licensing" /protect-tenantid:42745b33-2a5c-4726-8a2a-ca43caa0f74b /protect-ownerid:45beb445-4d06-47df-8e61-6ca1a88a080e /protect-key:"l+R+Umc5RGmSBh1oW+DoyMxm/h5h2JJXFcNOFiNp867=" /transfer:upload /upload-dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata" /upload-destSAS:"?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"
  
  This example uploads PST files to a subfolder named EncryptedPSTs  in the Azure storage location:
  
  O365ImportTool.exe /srcdir:\\FILESERVER01\PSTs /protect-rmsserver:"https://afcbd8ec-cb2b-4a1a-8246-0b4bc22d1978.rms.na.aadrm.com/_wmcs/licensing" /protect-tenantid:42745b33-2a5c-4726-8a2a-ca43caa0f74b /protect-ownerid:45beb445-4d06-47df-8e61-6ca1a88a080e /protect-key:"l+R+Umc5RGmSBh1oW+DoyMxm/h5h2JJXFcNOFiNp867=" /transfer:upload /upload-dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata/EncryptedPSTs" /upload-destSAS:"?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"
  ```

- Como explicado anteriormente, o serviço de importação do Office 365 ativa a configuração de retenção suspensa (para uma duração indefinida) após a importação de arquivos PST para uma caixa de correio. Isso significa que a propriedade *RentionHoldEnabled* é definida `True` para que a política de retenção atribuída à caixa de correio não seja processada. Isso dá ao proprietário da caixa de correio o tempo para gerenciar as novas mensagens importadas, impedindo que uma política de exclusão ou de arquivamento exclua ou arquive mensagens mais antigas. Veja algumas etapas que você pode executar para gerenciar essa retenção: 
    
  - Após um determinado período de tempo, você pode desativar o bloqueio de retenção executando o `Set-Mailbox -RetentionHoldEnabled $false` comando. Para obter instruções, consulte [colocar uma caixa de correio em retenção](https://go.microsoft.com/fwlink/p/?LinkId=544749).
    
  - Você pode configurar a retenção para que ela esteja desativada em alguma data no futuro. Para fazer isso, execute o `Set-Mailbox -EndDateForRetentionHold <date>` comando. Por exemplo, supondo que a data de hoje seja 1º de junho de 2016 e você queira que a retenção tenha sido desativada em 30 dias, execute `Set-Mailbox -EndDateForRetentionHold 7/1/2016`o seguinte comando:. Neste cenário, você deixaria a propriedade *RentionHoldEnabled* definida como `True`. Para obter mais informações, consulte [Set-Mailbox](https://go.microsoft.com/fwlink/p/?LinkId=150317).
    
  - Você pode alterar as configurações da política de retenção atribuída à caixa de correio para que os itens mais antigos que foram importados não sejam imediatamente excluídos ou movidos para a caixa de correio de arquivo morto do usuário. Por exemplo, você poderia estender a idade de retenção para uma política de exclusão ou arquivamento atribuída à caixa de correio. Neste cenário, você desativaria a retenção da caixa de correio depois de alterar as configurações da política de retenção. Para obter mais informações, consulte [Configurar uma política de arquivo morto e exclusão para caixas de correio em sua organização do Office 365](set-up-an-archive-and-deletion-policy-for-mailboxes.md).
