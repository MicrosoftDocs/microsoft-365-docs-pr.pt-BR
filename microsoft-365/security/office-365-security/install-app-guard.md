---
title: Application Guard para Office 365 para administradores
keywords: application guard, protection, isolation, isolated container, hardware isolation
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Obter o mais recente no isolamento baseado em hardware. Impedir que ataques atuais e emergentes, como explorações ou links mal-intencionados, atrapalhem a produtividade dos funcionários e a segurança corporativa.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a13196080aa0084411b737bfc157bbdb4b243a40
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907163"
---
# <a name="application-guard-for-office-for-admins"></a>Application Guard for Office para administradores

**Aplica-se a:** Word, Excel e PowerPoint para Microsoft 365, Windows 10 Enterprise

O Microsoft Defender Application Guard for Office (Application Guard for Office) ajuda a impedir que arquivos não confiáveis acessem recursos confiáveis, mantendo sua empresa segura contra ataques novos e emergentes. Este artigo orienta os administradores através da configuração de dispositivos para uma visualização do Application Guard para Office. Ele fornece informações sobre os requisitos do sistema e as etapas de instalação para habilitar o Application Guard for Office em um dispositivo.

## <a name="prerequisites"></a>Pré-requisitos

### <a name="minimum-hardware-requirements"></a>Requisitos mínimos de hardware

* **CPU**: 64 bits, 4 núcleos (físico ou virtual), extensões de virtualização (Intel VT-x OU AMD-V), Core i5 equivalente ou superior recomendado
* **Memória física**: RAM de 8 GB
* **Disco rígido**: 10 GB de espaço livre na unidade do sistema (SSD recomendado)

### <a name="minimum-software-requirements"></a>Requisitos mínimos de software

* **Windows 10**: windows 10 Enterprise edition, com build do cliente versão 2004 (20H1) build 19041 ou posterior
* **Office**: Office Current Channel Build versão 2011 16.0.13530.10000 ou posterior. Há suporte para versões de 32 e 64 bits do Office.
* **Pacote de atualização**: Atualização cumulativa de segurança mensal do Windows 10 [KB4571756](https://support.microsoft.com/help/4571756/windows-10-update-KB4571756)

Para requisitos detalhados do sistema, consulte [System requirements for Microsoft Defender Application Guard](/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard). Para saber mais sobre os canais de atualização do Office, consulte [Visão geral dos canais de atualização do Microsoft 365](/deployoffice/overview-update-channels).

### <a name="licensing-requirements"></a>Requisitos de licença

* Microsoft 365 E5 ou Microsoft 365 E5 Security

## <a name="deploy-application-guard-for-office"></a>Implantar o Application Guard para Office

### <a name="enable-application-guard-for-office"></a>Habilitar o Application Guard para Office

1. Baixe e instale atualizações cumulativas de segurança mensal do **Windows 10 KB4571756**.

2. Selecione **Microsoft Defender Application Guard** em Recursos do Windows e selecione **OK**. A habilitação do recurso Application Guard solicitará uma reinicialização do sistema. Você pode optar por reiniciar agora ou após a etapa 3.

   ![Caixa de diálogo Recursos do Windows mostrando AG](../../media/ag03-deploy.png)

   O recurso também pode ser habilitado executando o seguinte comando do PowerShell como administrador:

   ```powershell
   Enable-WindowsOptionalFeature -online -FeatureName Windows-Defender-ApplicationGuard
   ```

3. Pesquise o **Microsoft Defender Application Guard no Modo Gerenciado**, uma política de grupo em Configuração do Computador Modelos **\\ Administrativos \\ componentes \\** do Windows Microsoft Defender Application Guard . Aciona essa política definindo o valor em Opções como **2** ou **3** e selecionando **OK** ou **Aplicar**.

   ![Ativar AG no Modo Gerenciado](../../media/ag04-deploy.png)

   Em vez disso, você pode definir a política CSP correspondente:

   > OMA-URI: **./Device/Vendor/MSFT/WindowsDefenderApplicationGuard/Settings/AllowWindowsDefenderApplicationGuard** <br> Tipo de dados: **Integer** <br> Valor: **2**

4. Reinicie o sistema.

### <a name="set-diagnostics--feedback-to-send-full-data"></a>Definir diagnósticos & comentários para enviar dados completos

Esta etapa garante que os dados necessários para identificar e corrigir problemas estão chegando à Microsoft. Siga estas etapas para habilitar diagnósticos em seu dispositivo Windows:

1. Abra **Configurações** no menu Iniciar.

   ![Menu Iniciar](../../media/ag05-diagnostic.png)

2. Em **Configurações do Windows,** selecione **Privacidade**.

   ![Menu Configurações do Windows](../../media/ag06-diagnostic.png)

3. Em Privacidade, selecione **Diagnósticos & comentários e** selecione **Dados de diagnóstico opcionais.**

   ![Menu diagnósticos e comentários](../../media/ag07a-diagnostic.png)

Para obter mais informações sobre como configurar as configurações de diagnóstico do Windows, consulte [Configuring Windows diagnostic data in your organization](/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enterprise-management).

### <a name="confirm-that-application-guard-for-office-is-enabled-and-working"></a>Confirme se o Application Guard para Office está habilitado e funcionando

Antes de confirmar se o Application Guard para Office está habilitado, iniciar o Word, o Excel ou o PowerPoint em um dispositivo em que as políticas foram implantadas. Certifique-se de que o Office está ativado. Talvez seja necessário usar sua identidade de trabalho para ativar o produto do Office primeiro.

Para confirmar se o Application Guard para Office está habilitado, abra o Word, o Excel ou o PowerPoint e abra um documento não falso. Por exemplo, você pode abrir um documento que foi baixado da Internet ou um anexo de email de alguém de fora da sua organização.

Quando você abre um arquivo não falso pela primeira vez, você pode ver uma tela inicial do Office como o exemplo a seguir. Ele pode ser exibido por algum tempo enquanto o Application Guard for Office está sendo ativado e o arquivo está sendo aberto. As aberturas subsequentes de arquivos não confirmados devem ser mais rápidas.

![Tela inicial do aplicativo do Office](../../media/ag08-confirm.png)

Ao ser aberto, o arquivo deve exibir alguns indicadores visuais que o arquivo foi aberto dentro do Application Guard para Office:

* Um callout na faixa de opções

  ![Arquivo Doc mostrando pequena nota do App Guard](../../media/ag09-confirm.png)

* O ícone do aplicativo com um escudo na barra de tarefas

  ![Ícone na barra de tarefas](../../media/ag12-limitations.png)

## <a name="configure-application-guard-for-office"></a>Configurar o Application Guard para Office

O Office dá suporte às seguintes políticas para permitir que você configure os recursos do Application Guard para Office. Essas políticas podem ser configuradas por meio de políticas de grupo ou por meio do serviço de política de nuvem do Office.

> [!NOTE]
> A configuração dessas políticas pode desabilitar algumas funcionalidades para arquivos abertos no Application Guard para Office.

|Política|Descrição|
|---|---|
|Não use o Application Guard para Office|A habilitação dessa política força o Word, o Excel e o PowerPoint a usar o contêiner de isolamento do Exibição Protegido em vez do Application Guard para Office. Essa política pode ser usada para desabilitar temporariamente o Application Guard para Office quando houver problemas ao deixá-lo habilitado para o Microsoft Edge.|
|Configurar o Application Guard para a pré-criação do contêiner do Office|Esta política determina se o contêiner do Application Guard para Office, para isolar arquivos não-confidenciais, é pré-criado para melhorar o desempenho em tempo de execução. Se você habilitar essa configuração, poderá especificar o número de dias para continuar a pré-criação de um contêiner ou permitir que o heurístico integrado do Office pré-crie o contêiner.
|Não permitir cópia/colar para documentos do Office abertos no Application Guard para Office|A habilitação dessa política impedirá que um usuário copie e colar conteúdo de um documento aberto no Application Guard for Office para um documento aberto fora dele.|
|Desabilitar a aceleração de hardware no Application Guard para Office|Essa política controla se o Application Guard para Office usa aceleração de hardware para renderizar gráficos. Se você habilitar essa configuração, o Application Guard para Office usará a renderização baseada em software (CPU) e não carregará drivers gráficos de terceiros ou interagirá com qualquer hardware gráfico conectado.
|Desabilitar a proteção de tipos de arquivo sem suporte no Application Guard para Office|Essa política controla se o Application Guard for Office bloqueará a abertura de tipos de arquivos sem suporte ou se ele permitirá o redirecionamento para o Modo de Exibição Protegido.
|Desativar o acesso de câmera e microfone para documentos abertos no Application Guard para Office|A habilitação dessa política removerá o acesso do Office à câmera e ao microfone dentro do Application Guard para Office.|
|Restringir a impressão de documentos abertos no Application Guard para Office|A habilitação dessa política limitará as impressoras que um usuário pode imprimir a partir de um arquivo aberto no Application Guard para Office. Por exemplo, você pode usar essa política para restringir os usuários a imprimir somente em PDF.|
|Impedir que os usuários removam o Application Guard para a proteção do Office em arquivos|A habilitação dessa política removerá a opção (dentro da experiência do aplicativo do Office) para desabilitar o Application Guard para a proteção do Office ou abrir um arquivo fora do Application Guard para Office. <p> **Observação:** Os usuários ainda podem ignorar essa política removendo manualmente a propriedade mark-of-the-web do arquivo ou movendo um documento para um local confiável.|
|

> [!NOTE]
> As políticas a seguir exigirão que o usuário saia e entre novamente no Windows para entrar em vigor:
>
> * Desabilitar a cópia/colar para documentos abertos no Application Guard para Office
> * Restringir a impressão para documentos abertos no Application Guard para Office
> * Desativar o acesso de câmera e microfone a documentos abertos no Application Guard para Office

## <a name="submit-feedback"></a>Enviar comentários

### <a name="submit-feedback-via-feedback-hub"></a>Enviar comentários por meio do Hub de Feedback

Se você encontrar algum problema ao iniciar o Application Guard para o Office, será incentivado a enviar seus comentários por meio do Hub de Feedback:

1. Abra o **aplicativo Hub de Feedback** e entre.

2. Se você receber uma caixa de diálogo de erro ao iniciar o Application Guard, selecione Relatar à **Microsoft** na caixa de diálogo de erro para iniciar um novo envio de comentários. Caso contrário, navegue até <https://aka.ms/mdagoffice-fb> selecionar a categoria correta para o Application Guard e selecione Adicionar novos **+ &nbsp; comentários** à direita superior.

3. Insira um resumo na caixa **Resumir seus comentários** se ele ainda não estiver preenchido para você.

4. Insira uma descrição detalhada do problema que você experimentou e quais etapas você tomou na caixa **Explicar** em mais detalhes e selecione **Próximo**.

5. Selecione a bolha ao lado de **Problema**. Certifique-se de que a categoria selecionada **seja Segurança e Privacidade do Microsoft Defender Application Guard – \> Office** e selecione **Próximo**.

6. Selecione **Novo feedback,** em **seguida, Próximo**.

7. Coletar rastreamentos sobre o problema:

   1. Expanda **o azulejo Recriar meu** problema.

   2. Se o problema que você está enfrentando ocorrer enquanto o Application Guard está em execução, abra uma instância do Application Guard. Abrir uma instância permite que rastreamentos adicionais sejam coletados de dentro do contêiner do Application Guard.

   3. Selecione **Iniciar gravação** e aguarde que o azulejo pare de girar e diga Parar a *gravação*.

   4. Reproduza totalmente o problema com o Application Guard. A reprodução pode incluir a tentativa de iniciar uma instância do Application Guard e aguardar até que ela falhe ou reproduzir um problema em uma instância do Application Guard em execução.

   5. Selecione o **azulejo Parar gravação.**

   6. Mantenha todas as instâncias do Application Guard em execução abertas, mesmo por alguns minutos após o envio, para que os diagnósticos de contêiner também possam ser coletados.

8. Anexe quaisquer capturas de tela ou arquivos relevantes relacionados ao problema.

9. Selecione **Enviar**.

### <a name="submit-feedback-via-office-customer-voice"></a>Enviar comentários por meio do Office Customer Voice

Você também pode enviar comentários de dentro do Office se o problema acontecer quando os documentos do Office são abertos no Application Guard. Consulte o Manual [do Office Insider](https://insider.office.com/handbook) para enviar comentários.

## <a name="integration-with-microsoft-defender-for-endpoint-and-microsoft-defender-for-office-365"></a>Integração com o Microsoft Defender para Ponto de Extremidade e o Microsoft Defender para Office 365

O Application Guard para Office é integrado ao Microsoft Defender para Endpoint para fornecer monitoramento e alerta sobre atividades mal-intencionadas que ocorrem no ambiente isolado.

O Microsoft Defender for Endpoint é uma plataforma de segurança projetada para ajudar as redes corporativas a evitar, detectar, investigar e responder a ameaças avançadas. Para obter mais detalhes sobre essa plataforma, consulte [Microsoft Defender for Endpoint](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp). Para saber mais sobre a integração de dispositivos nessa plataforma, consulte [Onboard devices to the Microsoft Defender for Endpoint service](/windows/security/threat-protection/microsoft-defender-atp/onboard-configure).

Você também pode configurar o Microsoft Defender para Office 365 para trabalhar com o Defender para Ponto de Extremidade. Para obter mais informações, consulte [Integrar o Defender para Office 365 com o Microsoft Defender para Ponto de Extremidade](integrate-office-365-ti-with-wdatp.md).

## <a name="limitations-and-considerations"></a>Limitações e considerações

* O Application Guard para Office é um modo restrito que isola documentos não confiáveis para que eles não possam acessar recursos corporativos confiáveis, uma intranet, a identidade do usuário e arquivos arbitrários no computador. Como resultado, se um usuário tentar acessar um recurso que tenha uma dependência desse acesso, por exemplo, inserindo uma imagem de um arquivo local no disco, o acesso falhará e produzirá um prompt como o exemplo a seguir. Para habilitar um documento não confiável para acessar recursos confiáveis, os usuários devem remover a proteção do Application Guard do documento.

  ![Caixa de diálogo dizendo Para ajudá-lo a manter a segurança, esse recurso não está disponível](../../media/ag10-limitations.png)

  > [!NOTE]
  > Aconselhá os usuários a removerem a proteção apenas se confiarem no arquivo e em sua origem ou de onde ele veio.

* O conteúdo ativo em documentos como macros e controles ActiveX está desabilitado no Application Guard para Office. Os usuários precisam remover a proteção do Application Guard para habilitar o conteúdo ativo.

* Arquivos não confirmados de compartilhamentos de rede ou arquivos compartilhados do OneDrive, OneDrive for Business ou SharePoint Online de uma organização diferente aberta como somente leitura no Application Guard. Os usuários podem salvar uma cópia local desses arquivos para continuar trabalhando no contêiner ou remover a proteção para trabalhar diretamente com o arquivo original.

* Os arquivos protegidos pelo IRM (Gerenciamento de Direitos de Informação) são bloqueados por padrão. Se os usuários quiserem abrir esses arquivos no Modo de Exibição Protegido, um administrador deve configurar as configurações de política para tipos de arquivos sem suporte para a organização.

* Quaisquer personalizações para aplicativos do Office no Application Guard para Office não persistirão depois que um usuário sair e entrar novamente ou depois que o dispositivo for reiniciado.

* Somente as ferramentas de acessibilidade que usam a estrutura UIA podem fornecer uma experiência acessível para arquivos abertos no Application Guard para Office.

* A conectividade de rede é necessária para o primeiro lançamento do Application Guard após a instalação. A conectividade é necessária para que o Application Guard valide a licença.

* Na seção informações do documento, a propriedade *Last Modified By* pode exibir **WDAGUtilityAccount** como o usuário. WDAGUtilityAccount é o usuário anônimo configurado no Application Guard. A identidade do usuário da área de trabalho não é compartilhada dentro do contêiner do Application Guard.

## <a name="performance-optimizations-for-application-guard-for-office"></a>Otimizações de desempenho para o Application Guard para Office

Esta seção fornece uma visão geral das otimizações de desempenho usadas no Application Guard para Office. Essas informações podem ajudar os administradores a diagnosticar relatórios de usuários relacionados ao desempenho do Office ou do sistema geral quando o Application Guard está habilitado.

O Application Guard usa um contêiner virtualizado para isolar documentos não falsos do sistema. O processo de criação de um contêiner e configuração do contêiner do Application Guard para abrir documentos do Office tem uma sobrecarga de desempenho que pode afetar negativamente a experiência do usuário quando os usuários abrem um documento não falso.

Para fornecer aos usuários a experiência esperada de abertura de arquivo, o Application Guard usa a lógica para pré-criar um contêiner quando a seguinte heurística é atendida em um sistema: um usuário abriu um arquivo no Protected View ou no Application Guard nos últimos 28 dias.

Quando essa heurística é atendida, o Office pré-criará um contêiner do Application Guard para o usuário depois de entrar no Windows. Enquanto essa operação de pré-criação está em andamento, o sistema pode ter um desempenho lento, mas o efeito será resolvido assim que a operação for concluída.

> [!NOTE]
> As dicas necessárias para a heurística para pré-criar o contêiner são geradas por aplicativos do Office à medida que um usuário os usa. Se um usuário instalar o Office em um novo sistema em que o Application Guard está habilitado, o Office não criará o contêiner antes da primeira vez que um usuário abrir um documento não falso no sistema. O usuário observará que esse primeiro arquivo leva mais tempo para ser aberto no Application Guard.

## <a name="known-issues"></a>Problemas conhecidos

* Selecionar links da Web ( `http` ou ) não abre o `https` navegador.
* Não há suporte para colar conteúdo ou imagens RTF (rich text format) em documentos do Office abertos com o Application Guard no momento.
* Atualizações para o .NET causam falha na abertura de arquivos no Application Guard. Como solução alternativa, os usuários podem reiniciar o dispositivo quando se deparar com essa falha. Saiba mais sobre o problema em Receber uma mensagem de erro ao tentar abrir Windows Defender [Application Guard ou Windows Sandbox](https://support.microsoft.com/help/4575917/receiving-an-error-message-when-attempting-to-open-windows-defender-ap).