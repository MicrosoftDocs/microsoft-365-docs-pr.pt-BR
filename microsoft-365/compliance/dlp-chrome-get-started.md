---
title: Comece a usar a Extensão de Conformidade da Microsoft (visualização)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Prepare-se e implante a Extensão de Conformidade da Microsoft.
ms.openlocfilehash: 5a2fa5958117d14715292245924dce2ff63b09a0
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843825"
---
# <a name="get-started-with-microsoft-compliance-extension"></a>Comece a usar a Extensão de Conformidade da Microsoft

Use estes procedimentos para implementar a Extensão de Conformidade da Microsoft.

## <a name="before-you-begin"></a>Antes de você começar

Para usar a Extensão de Conformidade da Microsoft, o dispositivo deve estar integrado no ponto de extremidade da DLP. Para usar a extensão de conformidade da Microsoft, o dispositivo deve estar integrado no ponto de extremidade da DLP.

- [Saiba mais sobre a Extensão de Conformidade da Microsoft](dlp-chrome-learn-about.md)
- [Saiba mais sobre prevenção contra perda de dados](dlp-learn-about-dlp.md)
- [Criar, testar e ajustar uma política DLP](create-test-tune-dlp-policy.md)
- [Criar uma política DLP a partir de um modelo](create-a-dlp-policy-from-a-template.md)
- [Saiba mais sobre a prevenção contra Perda de Dados de Ponto de Extremidade](endpoint-dlp-learn-about.md)
- [Introdução à Prevenção contra perda de dados do ponto de extremidade](endpoint-dlp-getting-started.md)
- [Ferramentas e métodos de integração para computadores Windows 10](dlp-configure-endpoints.md)
- [Definir as configurações de proxy do dispositivo e conexão à Internet para Ponto de extremidade da DLP](endpoint-dlp-configure-proxy.md)
- [Usando a Prevenção contra perda de dados de ponto de extremidade](endpoint-dlp-using.md)

### <a name="skusubscriptions-licensing"></a>Licenciamento SKU/assinaturas

Antes de começar, você deve confirmar sua [assinatura do Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) e quaisquer complementos. Para acessar e usar a funcionalidade do Endpoint DLP, você deve ter uma dessas assinaturas ou complementos.

- Microsoft 365 E5
- Microsoft 365 A5 (EDU)
- Conformidade do Microsoft 365 E5
- Conformidade do Microsoft 365 A5
- Governança e Proteção de Informações do Microsoft 365 E5
- Governança e Proteção de Informações do Microsoft 365 A5

Para obter orientações de licenciamento detalhadas, confira as [orientações de licenciamento do Microsoft 365 para segurança e conformidade](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection).

- Sua organização deve ser licenciada para ponto de extremidade da DLP
- Seus dispositivos devem estar executando o Windows 10 x64 build 1809 ou posterior.
- O dispositivo deve ter a versão do cliente Antimalware 4.18.2101.9 ou posterior. Verifique sua versão atual abrindo o aplicativo **Segurança do Windows**, selecione o ícone **Configurações** e selecione **Sobre**.


### <a name="permissions"></a>Permissões

Os dados do Ponto de extremidade DLP podem ser exibidos no [Explorador de atividades](data-classification-activity-explorer.md). Existem sete funções que concedem permissão ao explorador de atividades, a conta que você usa para acessar os dados deve ser membro de qualquer uma delas.

- Administrador global
- Administrador de conformidade
- Administrador de segurança
- Administrador de dados de conformidade
- Leitor global
- Leitor de segurança
- Leitor de relatórios

### <a name="overall-installation-workflow"></a>Fluxo de trabalho geral de instalação

A implantação da Extensão de Conformidade da Microsoft é um processo de várias fases. Você pode optar por instalar em uma máquina por vez ou usar o Microsoft Endpoint Manager ou a Política de Grupo para implantações em toda a organização.

1. [Prepare seus dispositivos](#prepare-your-devices).
2. [Configuração Básica de Selfhost de Máquina Única](#basic-setup-single-machine-selfhost)
3. [Implantar usando o Microsoft Endpoint Manager](#deploy-using-microsoft-endpoint-manager)
4. [Implantar usando a Política de Grupo](#deploy-using-group-policy)
5. [Teste a Extensão](#test-the-extension)
6. [Use o painel de gerenciamento de alertas para visualizar os alertas da DLP do Chrome](#use-the-alerts-management-dashboard-to-viewing-chrome-dlp-alerts)
7. [Visualização de dados da DLP do Chrome](#viewing-chrome-dlp-data-in-activity-explorer) no explorador de atividades 

### <a name="prepare-infrastructure"></a>Preparar a infraestrutura

Se você estiver implementando a extensão de conformidade da Microsoft para todos os dispositivos Windows 10 monitorados, deverá remover o Google Chrome das listas de aplicativos e navegadores não permitidos. Para obter mais informações, confira [Navegadores não permitidos](endpoint-dlp-using.md#unallowed-browsers). Se você estiver implementando apenas para alguns dispositivos, poderá deixar o Chrome no navegador não permitido ou nas listas de aplicativos não permitidos. A extensão de conformidade da Microsoft contornará as restrições de ambas as listas dos computadores onde está instalada.  

### <a name="prepare-your-devices"></a>Preparar os dispositivos.

1. Use os procedimentos nestes tópicos para integrar seus dispositivos:
    1. [Introdução à Prevenção contra perda de dados do ponto de extremidade](endpoint-dlp-getting-started.md)
    1. [Ferramentas e métodos de integração para computadores Windows 10](dlp-configure-endpoints.md)
    1. [Definir as configurações de proxy do dispositivo e conexão à Internet para Ponto de extremidade da DLP](endpoint-dlp-configure-proxy.md)

### <a name="basic-setup-single-machine-selfhost"></a>Configuração Básica de Selfhost de Máquina Única

Este e o método recomendado. 

1. Entre no computador Windows 10 no qual deseja instalar a extensão de conformidade da Microsoft e execute este script do PowerShell como administrador. 

   ```powershell
   Get-Item -path "HKLM:\SOFTWARE\Microsoft\Windows Defender\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
   ``` 

2.  Navegue até a [Extensão de Conformidade da Microsoft - Chrome Web Store (google.com)](https://chrome.google.com/webstore/detail/microsoft-compliance-exte/echcggldkblhodogklpincgchnpgcdco).

3.  Instale a extensão usando as instruções na página da Chrome Web Store.

### <a name="deploy-using-microsoft-endpoint-manager"></a>Implantar usando o Microsoft Endpoint Manager

Use este método de configuração para implantações em toda a organização.


##### <a name="enabling-required-registry-key-via-microsoft-endpoint-manager"></a>Habilitando a Chave de Registro Exigida por meio do Microsoft Endpoint Manager

1.  Crie um script Windows PowerShell com o seguinte conteúdo:

    ```powershell
    Get-Item -path "HKLM:\SOFTWARE\Microsoft\Windows Defender\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
    ```

2.  Entre no [Centro de Administração do Microsoft Endpoint Manager](https://endpoint.microsoft.com).

3.  Navegue até **Dispositivos** > **Scripts** e selecione **Adicionar**.

4.  Navegue até o local do script criado quando solicitado.

5.  Selecione as seguintes configurações:
    1. Execute este script usando as credenciais de logon: SIM
    1. Aplicar verificação de assinatura de script: NÃO
    1. Execute o script em Windows PowerShell Host de 64 bits: SIM

6.  Selecione os grupos de dispositivos adequados e aplique a política.

#### <a name="microsoft-endpoint-manager-force-install-steps"></a>Etapas de instalação forçada do Microsoft Endpoint Manager

Antes de adicionar a extensão de Conformidade da Microsoft à lista de Extensões de instalação forçada, é importante ingerir o Chrome ADMX. As etapas para esse processo no Microsoft Endpoint Manager são documentadas pelo Google: [Gerenciar o Navegador Chrome com o Microsoft Intune - Ajuda do Google Chrome Empresa](https://support.google.com/chrome/a/answer/9102677?hl=en#zippy=%2Cstep-ingest-the-chrome-admx-file-into-intune).

 Depois de ingerir o ADMX, as etapas abaixo podem ser seguidas para criar um perfil de configuração para esta extensão.

1.  Entre no Centro de Administração do Microsoft Endpoint Manager (https://endpoint.microsoft.com).

2.  Navegue até Perfis de Configuração.

3.  Selecione **Criar Perfil**.

4.  Selecione **Windows 10** como plataforma.

5.  Selecione **Personalizar** como tipo de perfil.

6.  Selecione a guia **Configurações**.

7.  Selecione **Adicionar**.

8.  Insira as seguintes informações de política.
    
    OMA-URI: `./Device/Vendor/MSFT/Policy/Config/Chrome~Policy~googlechrome~Extensions/ExtensionInstallForcelist`<br/>
    Tipo de dados: `String`<br/>
    Valor: `<enabled/><data id="ExtensionInstallForcelistDesc" value="1&#xF000; echcggldkblhodogklpincgchnpgcdco;https://clients2.google.com/service/update2/crx"/>`

9.  Clique em criar.

### <a name="deploy-using-group-policy"></a>Implantar usando a Política de Grupo

Se não quiser usar o Microsoft Endpoint Manager, você pode usar políticas de grupo para implantar a Extensão de Conformidade da Microsoft em sua organização

1. Seus dispositivos devem ser gerenciáveis por meio da Política de Grupo e você precisa importar todos os ADMXs do Chrome para o Armazenamento Central de Política de Grupo. Para obter mais informações, confira [Como criar e gerenciar o Repositório Central para Modelos Administrativos de Política de Grupo no Windows](/troubleshoot/windows-client/group-policy/create-and-manage-central-store).

2.  Crie um script do PowerShell usando este comando do PowerShell:

    ```powershell
    Get-Item -path "HKLM:\SOFTWARE\Microsoft\Windows Defender\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
    ```

3.  Abra o **Console de Gerenciamento de Política de Grupo** e navegue até sua unidade organizacional (UO).

4.  Clique com o botão direito e selecione **Criar um GPO neste domínio e Vinculá-lo aqui**. Quando solicitado, atribua um nome descritivo a este objeto de política de grupo (GPO) e termine de criá-lo.

5.  Clique com o botão direito no GPO e selecione **Editar**.

6.  Vá para **Configuração do Computador** > **Preferências** > **Configurações do Painel de Controle** > **Tarefas Agendadas**.

7.  Criar uma nova tarefa imediata clicando com o botão direito e selecionando **Nova** > **Tarefa Imediata (pelo menos Windows 7)**.

8.  Dê um nome e uma descrição à tarefa.

9.  Escolha a conta correspondente para executar a tarefa imediata, por exemplo NT Authority

10. Selecione **Executar com privilégios mais altos**.

11. Configure a política para Windows 10.

12. Na guia **Ações**, selecione a ação **Iniciar um programa**.

13. Insira o caminho para o Programa/Script criado na Etapa 1.

14. Selecione **Aplicar**.

#### <a name="adding-the-chrome-extension-to-the-forceinstall-list"></a>Adicionando a Extensão do Chrome à Lista ForceInstall

1.  No Editor de Gerenciamento de Política de Grupo, navegue até sua UO.

2.  Expanda o seguinte caminho **Configuração de Computador/Usuário** > **Políticas** > **Modelos Administrativos** > **Modelos Administrativos Clássicos** > **Google** > **Google Chrome** > **Extensões**. Este caminho pode variar dependendo da sua configuração.

3.  Selecione **Configurar a lista de extensões instaladas por força**.

4.  Clique com o botão direito do mouse e selecione **Editar**.

5.  Selecione **Habilitado**.

6.  Selecione **Mostrar**.

7.  Em **valor**, adicione a seguinte entrada: `echcggldkblhodogklpincgchnpgcdco;https://clients2.google.com/service/update2/crx`

8.  Selecione **OK** e, em seguida, **Aplicar**.

### <a name="test-the-extension"></a>Teste a Extensão

#### <a name="upload-to-cloud-service-or-access-by-unallowed-browsers-cloud-egress"></a>Faça upload para o serviço de nuvem ou acesse por navegadores não permitidos Saída da Nuvem  

1. Crie ou obtenha um item confidencial e tente fazer upload de um arquivo para um dos domínios de serviço restritos da sua organização. Os dados confidenciais devem corresponder a um de nossos [Tipos de Informações Confidenciais](sensitive-information-type-entity-definitions.md) integrados ou a um dos tipos de informações confidenciais da sua organização. Você deve receber uma notificação do sistema DLP no dispositivo que está testando, mostrando que essa ação não é permitida quando o arquivo é aberto.

#### <a name="testing-other-dlp-scenarios-in-chrome"></a>Testar outros cenários DLP no Chrome 

Agora que você removeu o Chrome da lista de navegadores/aplicativos não permitidos, pode testar os cenários abaixo para confirmar se o comportamento atende aos requisitos de sua organização:

- Copie dados de um item confidencial para outro documento usando a Área de transferência
    - Para testar, abra um arquivo que está protegido contra ações de copiar para a área de transferência no navegador Chrome e tente copiar os dados do arquivo.
    - Resultado esperado: uma notificação do sistema DLP mostrando que esta ação não é permitida quando o arquivo está aberto.
- Imprimir documentos
    - Para testar, abra um arquivo que esteja protegido contra ações de impressão no navegador Chrome e tente imprimir o arquivo.
    - Resultado esperado: uma notificação do sistema DLP mostrando que esta ação não é permitida quando o arquivo está aberto.
- Copiar para Mídia Removível USB
    - Para testar, tente salvar o arquivo em um armazenamento de mídia removível.
    - Resultado esperado: uma notificação do sistema DLP mostrando que esta ação não é permitida quando o arquivo está aberto.
- Copiar para Compartilhamento de Rede
    - Para testar, tente salvar o arquivo em um compartilhamento de rede.
    - Resultado esperado: uma notificação do sistema DLP mostrando que esta ação não é permitida quando o arquivo está aberto.


### <a name="use-the-alerts-management-dashboard-to-viewing-chrome-dlp-alerts"></a>Usar o painel de gerenciamento de alertas para visualizar os alertas do Chrome DLP

1. Abra a página **Prevenção contra perda de dados** no [Centro de Conformidade do Microsoft 365](https://compliance.microsoft.com) e selecione **Alertas**.

2. Confira os procedimentos em [Como configurar e exibir alertas para suas políticas de DLP](dlp-configure-view-alerts-policies.md) para exibir alertas das políticas de DLP do Ponto de extremidade.


### <a name="viewing-chrome-dlp-data-in-activity-explorer"></a>Visualização de dados do Chrome DLP no explorador de atividades

1. Abra a [página de classificação de dados](https://compliance.microsoft.com/dataclassification?viewid=overview) para o seu domínio no Centro de conformidade do Microsoft 365 e escolha **Explorador de atividades**.

2. Confira os procedimentos no [Comece a usar o Explorador de atividades](data-classification-activity-explorer.md) para acessar e filtrar todos os dados dos dispositivos de ponto de extremidade.

   > [!div class="mx-imgBorder"]
   > ![filtro do explorador de atividades para dispositivos de ponto de extremidade](../media/endpoint-dlp-4-getting-started-activity-explorer.png)

### <a name="known-issues-and-limitations"></a>Limitações e problemas conhecidos

1. A imposição de substituição de bloqueio para saída da nuvem não é compatível.
2. O modo anônimo não é compatível e deve ser desabilitado.

## <a name="next-steps"></a>Próximas etapas
Agora que você tem dispositivos integrados e pode exibir os dados de atividade no Explorador de atividades, você está pronto para prosseguir para a próxima etapa na qual você cria políticas DLP que protegem seus itens confidenciais.

- [Usando a Prevenção contra perda de dados de ponto de extremidade](endpoint-dlp-using.md)

## <a name="see-also"></a>Confira também

- [Saiba mais sobre a Prevenção contra perda de dados do ponto de extremidade](endpoint-dlp-learn-about.md)
- [Usando a prevenção contra perda de dados do ponto de extremidade](endpoint-dlp-using.md)
- [Saiba mais sobre prevenção contra perda de dados](dlp-learn-about-dlp.md)
- [Criar, testar e ajustar uma política DLP](create-test-tune-dlp-policy.md)
- [Começar a usar o Explorador de atividades](data-classification-activity-explorer.md)
- [Microsoft Defender para Ponto de Extremidade](/windows/security/threat-protection/)
- [Ferramentas e métodos de integração para computadores Windows 10](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [Assinatura do Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [Dispositivos associados ao Microsoft Azure AD](/azure/active-directory/devices/concept-azure-ad-join)
- [Baixar o novo Microsoft Edge baseado em Chromium](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
