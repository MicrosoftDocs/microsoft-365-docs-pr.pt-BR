---
title: Instalar e usar o suplemento relatório de lixo eletrônico para o Microsoft Outlook
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 4650fec1-4ee3-4659-abbc-bf091718cb26
ms.collection:
- M365-security-compliance
description: Saiba como instalar e usar o suplemento relatório de lixo eletrônico da Microsoft para relatar mensagens de spam, não spam e phishing à Microsoft.
ms.openlocfilehash: 6f08c72ae797825695c443848429dcfd2cd485a2
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616423"
---
# <a name="install-and-use-the-junk-email-reporting-add-in-for-microsoft-outlook"></a>Instalar e usar o suplemento relatório de lixo eletrônico para o Microsoft Outlook

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> Se você não estiver usando o suplemento relatório de lixo eletrônico, recomendamos o [suplemento mensagem de relatório](enable-the-report-message-add-in.md) . Para mais informações, confira [Relatar mensagens e arquivos à Microsoft](report-junk-email-messages-to-microsoft.md).

O suplemento relatório de lixo eletrônico para o Microsoft Outlook permite que os usuários enviem falsos positivos (emails em boas condições marcados como spam), falsos negativos (emails inválidos permitidos) e mensagens de phishing para a Microsoft. Se sua organização não usa a proteção do Exchange Online (por exemplo, Exchange ou serviços de email locais, que não seja o Exchange Online), o envio do relatório de lixo eletrônico não afetará a filtragem de spam.

Este tópico explica como instalar e usar o suplemento relatório de lixo eletrônico.

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Para instalar o suplemento relatório de lixo eletrônico, confira a seção [instalar o suplemento relatório de lixo eletrônico](#install-the-junk-email-reporting-add-in) mais adiante neste tópico.

- O suplemento relatório de lixo eletrônico funciona com as seguintes versões do Outlook:

  - Outlook 2013 ou posterior
  - Outlook incluído no Microsoft 365 Apps for Enterprise

- Para obter mais informações sobre como relatar mensagens à Microsoft, consulte [relatar mensagens e arquivos para a Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="use-the-junk-email-reporting-add-in-to-report-spam-and-phishing-messages"></a>Usar o suplemento relatório de lixo eletrônico para relatar mensagens de spam e phishing

1. Para mensagens na caixa de entrada ou em qualquer outra pasta de email, exceto lixo eletrônico, use qualquer um dos seguintes métodos para relatar mensagens de spam e phishing:

   - Selecione a mensagem ou abra a mensagem. Na guia **página inicial** ou **mensagem** na faixa de opções, clique em **lixo eletrônico** e selecione **relatar como lixo eletrônico** ou **relatório como phishing**.

     ![Relatar emails de lixo eletrônico ou phishing da faixa de opções](../../media/junk-email-reporting-ribbon.png)

   - Clique com o botão direito do mouse na mensagem, selecione **lixo eletrônico** e, em seguida, selecione **relatar como lixo eletrônico** ou **relatório como phishing**.

     ![Relatar emails de lixo eletrônico ou phishing do clique com o botão direito](../../media/junk-email-reporting-right-click.png)

   - Selecione várias mensagens, clique com o botão direito do mouse e selecione **relatar como lixo eletrônico** ou **relatório como phishing**.

     ![Relatar várias mensagens de email de spam ou phishing do clique com o botão direito](../../media/junk-email-reporting-right-click-multiple.png)

2. Na caixa de diálogo exibida, leia as informações e clique em **relatório**. Se você mudar de ideia, clique em **não relatar**.

   ![Caixa de diálogo relatar como lixo eletrônico](../../media/junk-email-reporting-report-as-junk-dialog.png)

   ![Caixa de diálogo relatar como phishing](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. As mensagens selecionadas serão enviadas para a Microsoft para análise e:

   - Movido para a pasta lixo eletrônico se ele foi relatado como spam.
   - Excluído se foi relatado como phishing.

   Para confirmar se as mensagens foram enviadas, abra sua pasta **Itens Enviados** para exibir as mensagens enviadas.

## <a name="use-the-junk-email-reporting-add-in-to-report-non-spam-and-phishing-messages-from-the-junk-email-folder"></a>Use o suplemento relatório de lixo eletrônico para relatar mensagens que não são spam e phishing da pasta lixo eletrônico

1. Na pasta lixo eletrônico, use qualquer um dos seguintes métodos para relatar falsos positivos de spam ou mensagens de phishing:

   - Selecione a mensagem ou abra a mensagem. Na guia **página inicial** ou de **mensagem** na faixa de opções, clique em **não lixo eletrônico** e selecione **relatar como não lixo eletrônico** ou **relatar como phishing**.

     ![Relatar não é lixo eletrônico ou email de phishing da faixa de opções na pasta lixo eletrônico](../../media/junk-email-reporting-junk-folder-ribbon.png)

   - Clique com o botão direito do mouse na mensagem, clique em **lixo eletrônico** e selecione **relatar como não lixo eletrônico** ou **relatar como phishing**.

     ![Relatar emails não spam ou phishing do clique com o botão direito na pasta lixo eletrônico](../../media/junk-email-reporting-junk-folder-right-click.png)

   - Selecione várias mensagens, clique com o botão direito do mouse e selecione **relatar como não é lixo eletrônico** ou **relatar como phishing**.

     ![Relatar várias mensagens de email de não lixo eletrônico ou phishing do clique com o botão direito na pasta lixo eletrônico](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

2. Na caixa de diálogo exibida, leia as informações e clique em **relatório**. Se você mudar de ideia, clique em **não relatar**.

   ![Relatar como não sendo lixo eletrônico](../../media/junk-email-reporting-report-as-not-junk-dialog.png)

   ![Caixa de diálogo relatar como phishing](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. As mensagens selecionadas serão enviadas para a Microsoft para análise e:

   - Movido para a pasta lixo eletrônico se ele foi relatado como spam.
   - Excluído se foi relatado como phishing.

   Para confirmar se as mensagens foram enviadas, abra sua pasta **Itens Enviados** para exibir as mensagens enviadas.

## <a name="install-the-junk-email-reporting-add-in"></a>Instalar o suplemento relatório de lixo eletrônico

- Você precisa ter privilégios de administrador no computador no qual você está instalando o suplemento.

- Vá para <https://www.microsoft.com/download/details.aspx?id=18275> e baixe o arquivo. msi apropriado para sua versão do Office para um local que seja fácil de encontrar:

  - **32** bits: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`
  - **64** bits: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`

- Para o Outlook 2013 ou posterior, o único pré-requisito é o Microsoft .NET Framework 2,0. No Windows 10, você não instala o .NET Framework 2,0 a partir de um download.

### <a name="install-the-junk-email-reporting-add-in-using-the-setup-wizard"></a>Instalar o suplemento de relatório de lixo eletrônico usando o assistente de configuração

1. Feche o Outlook no computador.

2. No Windows 10, verifique se o .NET Framework 2,0 está habilitado. Para obter instruções, consulte [habilitar o .NET Framework 3,5 no painel de controle](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel).

3. Localize o arquivo. msi que você baixou e clique duas vezes nele.

4. Na página **Bem-vindo à Configuração do Suplemento Relatório de Lixo Eletrônico para Microsoft** e clique em **Próximo**.

5. Revise o contrato de licença, clique em **aceito os termos do contrato de licença** se você concordar com os termos e clique em **Avançar**.

6. Quando o assistente for concluído, clique em **Concluir**.

Inicie o Outlook.

Procure o botão **Lixo Eletrônico** na faixa de opções do Outlook. Agora, você pode relatar mensagens de lixo eletrônico à Microsoft selecionando-as na sua Caixa de Entrada e clicando no botão **Relatar Lixo Eletrônico**.

Selecione a seta para baixo ao lado de **Lixo Eletrônico** para obter mais opções, como **Relatar como Phishing** se você quiser relatar emails de esquemas de phishing para a Microsoft. Na pasta Lixo Eletrônico, você também pode selecionar, **Relatar como não sendo lixo eletrônico** se um email tiver sido identificado incorretamente como lixo eletrônico.

### <a name="install-the-junk-email-reporting-add-in-using-silent-mode"></a>Instalar o Suplemento Relatório de Lixo Eletrônico usando Modo Silencioso

1. Feche o Outlook no computador.

2. No Windows 10, instale o .NET Framework 2,0 executando o seguinte comando:

   ```dos
   DISM /Online /Enable-Feature /FeatureName:NetFx3 /All
   ```

3. Para instalar o suplemento sem qualquer interação do usuário, abra um prompt de comando e use a seguinte sintaxe:

   ```dos
   msiexec /qn /i "<PathToMSIFile>\<MSIFile>" [MaxMessageSelection=<1-50>] [BccEmailAddress="<EmailAddress1>; <EmailAddress2>"...]
   ```

   - `MaxMessageSelection` Especifica o número máximo de mensagens que você pode selecionar para um único envio. Os valores válidos vão de 1 a 50. O valor padrão é 15.

   - `BccEmailAddress` Especifica destinatários Cco adicionais que receberão uma cópia de todos os envios de usuários. O valor padrão é Blank (nenhum destinatário adicional Cco).

   Este exemplo instala a versão de 64 bits do suplemento do caminho especificado com as configurações padrão.

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi"
   ```

   Este exemplo instala a versão de 32 bits do suplemento do caminho especificado com as seguintes configurações adicionais:

   - Até 20 mensagens podem ser selecionadas em um único envio.
   - junkreports@contoso.com e hollyd@treyresearch.net recebem cópias Cco de todos os envios.

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" MaxMessageSelection=20 BccEmailAddress="junkreports@contoso.com; hollyd@treyresearch.net"
   ```

### <a name="how-do-you-know-this-worked"></a>Como saber se funcionou?

Para verificar se você instalou com êxito o suplemento relatório de lixo eletrônico, execute qualquer uma das seguintes etapas no Outlook:

- Selecione a mensagem ou abra a mensagem. Na guia **página inicial** ou de **mensagem** na faixa de opções, clique em **lixo eletrônico** e verifique se as seguintes opções estão disponíveis:

  - **Relatar como lixo eletrônico**
  - **Relatar como phishing**
  - **Opções de relatório de lixo eletrônico**
  - **Relatar a ajuda online do lixo eletrônico**

  ![Relatar emails de lixo eletrônico ou phishing da faixa de opções](../../media/junk-email-reporting-ribbon.png)

- Clique com o botão direito do mouse na mensagem, selecione **lixo eletrônico** e verifique se as seguintes opções estão disponíveis:

  - **Relatar como lixo eletrônico**
  - **Relatar como phishing**
  - **Opções de relatório de lixo eletrônico**
  - **Relatar a ajuda online do lixo eletrônico**

  ![Relatar emails de lixo eletrônico ou phishing do clique com o botão direito](../../media/junk-email-reporting-right-click.png)

- Selecione várias mensagens, clique com o botão direito do mouse e verifique se as seguintes opções estão disponíveis:

  - **Relatar como lixo eletrônico**
  - **Relatar como phishing**

  ![Relatar várias mensagens de email de spam ou phishing do clique com o botão direito](../../media/junk-email-reporting-right-click-multiple.png)

- Execute as ações anteriores na pasta **lixo eletrônico** e verifique se as opções anteriores de relatório de **lixo eletrônico** **não são lixo eletrônico**.

  ![Relatar não é lixo eletrônico ou email de phishing da faixa de opções na pasta lixo eletrônico](../../media/junk-email-reporting-junk-folder-ribbon.png)

  ![Relatar emails não spam ou phishing do clique com o botão direito na pasta lixo eletrônico](../../media/junk-email-reporting-junk-folder-right-click.png)

  ![Relatar várias mensagens de email de não lixo eletrônico ou phishing do clique com o botão direito na pasta lixo eletrônico](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

## <a name="uninstall-the-junk-email-reporting-add-in"></a>Desinstalar o Suplemento Relatório de Lixo Eletrônico

Após fechar o Outlook, use qualquer um dos seguintes procedimentos para desinstalar o suplemento relatório de lixo eletrônico:

- **Painel de controle**: Pressione a tecla Windows + R. Na caixa de diálogo **executar** que é aberta, insira `control appwiz.cpl` e clique em **OK**.

  Localize e selecione o **suplemento relatório de lixo eletrônico da Microsoft** na lista e clique em **desinstalar**.

- **Pacote do Windows Installer**: encontre ou baixe o arquivo. msi apropriado e clique duas vezes nele.

  - **32** bits: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`

  - **64** bits: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`

  Na caixa de diálogo exibida, selecione **remover suplemento relatório de lixo eletrônico da Microsoft para Outlook** e clique em **Avançar**.

- **Modo silencioso**: encontre ou baixe o arquivo. msi apropriado. Em uma janela de prompt de comando, substitua \<PathToFile\> o local do arquivo. msi e execute um dos seguintes comandos:

  - **32** bits:

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

  - **64** bits:

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

Quando você abre o Outlook após a desinstalação, as opções de relatório de lixo eletrônico, não lixo eletrônico e phishing devem ser despercebidas.

## <a name="troubleshooting-the-junk-email-reporting-add-in"></a>Solucionando problemas do suplemento relatório de lixo eletrônico

Ocasionalmente, você pode enfrentar problemas com o Outlook após adicionar o suplemento de relatório de lixo eletrônico. Esta seção descreve os problemas que você pode encontrar, juntamente com as dicas para resolver esses problemas.

### <a name="troubleshooting-for-users"></a>Solucionando problemas de usuários

Você enfrenta um ou mais dos seguintes problemas:

- Nada acontece quando você clica em **Relatar Lixo Eletrônico**
- O Outlook para de responder depois que você selecionar uma mensagem de email
- O lixo eletrônico relatado não pode ser entregue devido a uma resposta "não entregue"

Para corrigir esse problema, siga estas etapas:

1. Feche e reinicie o Outlook.
2. Criar e enviar uma mensagem de teste e verificar se o destinatário recebeu a mensagem.
3. Se o problema persistir, entre em contato com seu administrador.

Para outros métodos que você pode usar para enviar mensagens à Microsoft, confira [mensagens de relatório e arquivos para a Microsoft](report-junk-email-messages-to-microsoft.md).

### <a name="troubleshooting-for-admins"></a>Solucionando problemas de administradores

#### <a name="problem-an-error-message-continually-appears-that-asks-users-to-contact-their-system-administrator"></a>Problema: uma mensagem de erro é exibida continuamente solicitando que os usuários entrem em contato com o administrador do sistema

1. Verifique ou defina a `LoggingLevel` chave do registro com o valor "Verbose":

   - o **Outlook de 32 bits em Windows de 32 bits**:

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - o **Outlook de 32 bits em Windows de 64 bits**:

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Wow6432Node\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - **64-bit Outlook**:

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk E-mail Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

2. Reinicie o Outlook e peça aos usuários para reportá-los quando eles verão a mensagem de erro.

3. Colete as informações de log encontradas no seguinte local:

   `%LOCALAPPDATA%\Microsoft\Junk Email Reporting Add-in\SpamReporterAddinLog.txt`

4. Entre em contato com o suporte técnico do Exchange Online Protection e forneça as informações de log.

#### <a name="problem-users-selected-not-to-receive-a-confirmation-prompt-when-they-report-messages-and-now-they-want-the-prompt-back"></a>Problema: os usuários optaram por não receber um prompt de confirmação ao relatar mensagens e agora eles querem retornar o prompt

1. Crie a `ConfirmReportJunk` chave do registro com o valor "true":

   ```text
   Windows Registry Editor Version 5.00

   HKEY_CURRENT_USER\Software\Microsoft\Junk E-mail Reporting\Preferences]
   "ConfirmReportJunk"="True"
   ```

2. Reinicie o Outlook.
