---
title: Instalar o Suplemento Relatório de Lixo Eletrônico para o Microsoft Outlook
ms.author: MSFTTracyP
author: tracyp
manager: dansimp
ms.date: 12/9/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 8dcc752f-e22e-44ce-a104-4cc4d7e439f3
ms.collection:
- M365-security-compliance
description: Neste articleSupported LanguagesInstall o relatório de lixo eletrônico adicionar-desintalar o suplemento de relatório de lixo eletrônico-inFor mais informações
ms.openlocfilehash: 508d542be4862a6a06b795fc7a4b97bdc405d430
ms.sourcegitcommit: ba223b4fd069fc6fd09c2a2e34c770a18bc7b2a2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "39865883"
---
# <a name="install-the-junk-email-reporting-add-in-for-microsoft-outlook"></a>Instalar o Suplemento Relatório de Lixo Eletrônico para o Microsoft Outlook
  
Este tópico descreve como instalar e desinstalar o Suplemento Relatório de Lixo Eletrônico da Microsoft para o Outlook nos computadores cliente da organização. A versão atual do suplemento (janeiro de 2016) inclui suporte para o Outlook 2016, Outlook 2013, Outlook 2010 e Outlook 2007. 
  
O suplemento (para todos os idiomas com suporte) permite que você relate lixo eletrônico diretamente da faixa de opções do Outlook. A versão em inglês do suplemento inclui opções adicionais para relatar problemas de email para a Microsoft diretamente da faixa de opções:
  
-  Relatar emails de esquemas de phishing recebidos 
    
- Relate emails identificados incorretamente como lixo eletrônico.
    
## <a name="supported-languages"></a>Idiomas com suporte
<a name="sectionSection0"> </a>

O Suplemento Relatório de Lixo Eletrônico é compatível com os seguintes idiomas: 
  
- Chinês simplificado
    
- Chinês tradicional
    
- Holandês
    
- Inglês
    
- Francês
    
- Alemão
    
- Italiano
    
- Japonês
    
- Coreano
    
- Português
    
- Português (Brasil)
    
- Espanhol
    
## <a name="install-the-junk-email-reporting-add-in"></a>Instalar o Suplemento Relatório de Lixo Eletrônico

Você pode instalar o Suplemento Relatório de Lixo Eletrônico:
  
- Ao executar o pacote do Windows Installer da mesma forma que você faria com qualquer outro arquivo .msi. Quando você instala o suplemento, uma interface GUI é exibida e leva você pelas telas de instalação. Para saber mais, confira [Instalar o Suplemento Relatório de Lixo Eletrônico usando o Assistente de Configuração](#install-the-junk-email-reporting-add-in-using-the-setup-wizard). OU
    
- Ao executar uma instalação silenciosa que elimina a interface do usuário de instalação. Em vez disso, você pode especificar opções de linha de comando que executam um script de instalação. Quando você instala o suplemento, há opções de configuração adicionais que ficam disponíveis e que não estão disponíveis na interface GUI. Para saber mais, confira [Instalar o Suplemento Relatório de Lixo Eletrônico usando Modo Silencioso](#install-the-junk-email-reporting-add-in-using-silent-mode).
    
### <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

A instalação do Suplemento Relatório de Lixo Eletrônico para o Microsoft Outlook requer:
  
- Um dos seguintes sistemas operacionais: Windows 10, Windows 8.1, Windows 8, Windows 7 Service Pack 1, Windows 10 Server, Windows Server 2012 R2, Windows Server 2012, ou Windows Server 2008 R2
    
- Outlook 2016, Outlook 2013, Outlook 2010 ou Outlook 2007 (Service Pack 2 ou superior)
    
- Assemblies de Interoperabilidade Primários do Microsoft Office: 
    
  - Para baixar os Assemblies de Interoperabilidade Primários do Microsoft Office 2010 ou superior, vá para [Centro de Downloads da Microsoft](https://go.microsoft.com/fwlink/?LinkID=166026).
    
  - Para baixar os Assemblies de Interoperabilidade Primários do Microsoft Office 2007, vá para [Centro de Downloads da Microsoft](https://go.microsoft.com/fwlink/?LinkId=72637).
    
- Microsoft .NET Framework [Versão 2.0](https://go.microsoft.com/fwlink/?LinkID=208706).
    
> [!NOTE]
> Você deve ter privilégios de administrador no computador em que está instalando o suplemento. 
  
### <a name="install-the-junk-email-reporting-add-in-using-the-setup-wizard"></a>Instalar o Suplemento Relatório de Lixo Eletrônico usando o Assistente de Configuração

1. Feche o Outlook no computador.
    
2. Acesse a página do Centro de Downloads da Microsoft e localize o Suplemento Relatório de Lixo Eletrônico para Microsoft [https://go.microsoft.com/fwlink/?LinkID=147248](https://go.microsoft.com/fwlink/?LinkID=147248) e baixe o arquivo .msi. 
    
3. Clique duas vezes no arquivo .msi. 
    
4. Na página **Bem-vindo à Configuração do Suplemento Relatório de Lixo Eletrônico para Microsoft** e clique em **Próximo**. 
    
5. Analise o contrato de licença e clique em **Aceito os termos do Contrato de Licença** se concordar com os termos da instalação (necessário para continuar a instalação). Clique em **Próximo** para continuar. 
    
6. Quando o assistente for concluído, clique em **Concluir**. 
    
7. Inicie o Outlook.
    
8. Procure o botão **Lixo Eletrônico** na faixa de opções do Outlook. Agora, você pode relatar mensagens de lixo eletrônico à Microsoft selecionando-as na sua Caixa de Entrada e clicando no botão **Relatar Lixo Eletrônico**. 
    
9. Selecione a seta para baixo ao lado de **Lixo Eletrônico** para obter mais opções, como **Relatar como Phishing** se você quiser relatar emails de esquemas de phishing para a Microsoft. Na pasta Lixo Eletrônico, você também pode selecionar, **Relatar como não sendo lixo eletrônico** se um email tiver sido identificado incorretamente como lixo eletrônico. 
    
### <a name="install-the-junk-email-reporting-add-in-using-silent-mode"></a>Instalar o Suplemento Relatório de Lixo Eletrônico usando Modo Silencioso

1. Feche o Outlook no computador.
    
2. Abra um prompt de comando.
    
3. Se você quiser fazer uma instalação diretamente do suplemento, sem quaisquer parâmetros opcionais, especifique o seguinte:
    
  - Computadores que executam o Outlook x86:  `msiexec /qn /i JunkReportingAdd-in.x86-en.msi`
    
  - Computadores que executam o Outlook x64:  `msiexec /qn /i JunkReportingAdd-in.x64-en.msi`
    
    Você também pode especificar os parâmetros opcionais MaxMessageSelection e BccEmailAddress:
    
  - MaxMessageSelection Permite que os administradores definam o número máximo de mensagens que podem ser selecionadas pelos usuários para envio com um único clique. O intervalo é de 1 a 50 mensagens e o valor padrão é de 10 mensagens.
    
    Exemplo: Se você deseja definir o número máximo de mensagens que podem ser selecionadas pelos usuários para envio com um único clique para 16, use a opção a seguir como parte do comando de instalação:  `MaxMessageSelection=16`
    
  - BccEmailAddress Permite que os administradores configurem uma caixa de correio para receber uma cópia de todos os envios de usuário por meio da definição de um endereço de email Cco. Após configurar a caixa de correio, uma cópia de todos emails enviados será mandada para o BccEmailAddress. Caso contrário, a configuração padrão será o endereço de email sem Cco.
    
    Exemplo: Se você quiser usar junkReports@contoso.com como o endereço de email de Cco para todos os envios, use o comando a seguir:  `BccEmailAddress="junkReports@contoso.com"`
    
    > [!NOTE]
    > Você pode definir vários endereços de email de Cco inserindo-os com um delimitador de ponto e vírgula. Exemplo:  `BccEmailAddress="junkReports@contoso.com; hollyd@treyresearch.net"`
  
    Para adicionar ambos os parâmetros opcionais com base nos exemplos acima, você deve especificar os itens a seguir para um computador que está executando o Outlook x86: 
    
      ```
      msiexec /qn /i JunkReportingAdd-in.x86-en.msi. MaxMessageSelection=16 BccEmailAddress="junkReports@contoso.com; hollyd@treyresearch.net"
      ```

4. Após concluir a instalação, inicie o Outlook.
    
5. Procure o botão **Lixo Eletrônico** na faixa de opções do Outlook. Agora, você pode relatar mensagens de lixo eletrônico à Microsoft selecionando-as na sua Caixa de Entrada e clicando no botão **Relatar Lixo Eletrônico**. 
    
6. Selecione a seta para baixo ao lado de **Lixo Eletrônico** para obter mais opções, como **Relatar como Phishing** se você quiser relatar emails de esquemas de phishing para a Microsoft. Na pasta Lixo Eletrônico, você também pode selecionar, **Relatar como não sendo lixo eletrônico** se um email tiver sido identificado incorretamente como lixo eletrônico. 
    
## <a name="uninstall-the-junk-email-reporting-add-in"></a>Desinstalar o Suplemento Relatório de Lixo Eletrônico

Use uma dessas opções para desinstalar o Suplemento Relatório de Lixo Eletrônico:
  
- Remova o suplemento usando o Painel de Controle do Windows. Para saber mais, confira [Desinstalar o Suplemento Relatório de Lixo Eletrônico no Painel de Controle](#uninstall-the-junk-email-reporting-add-in-from-control-panel).
    
- Execute o pacote do Windows Installer e selecione a opção desinstalar. Confira mais informações [em desinstalar o suplemento relatório de lixo eletrônico executando o pacote do Windows Installer](#uninstall-the-junk-email-reporting-add-in-by-running-the-windows-installer-package).
    
- Execute uma instalação silenciosa usando a opção de desinstalação. Para saber mais, confira [Desinstalar o Suplemento Relatório de Lixo Eletrônico em Modo Silencioso](#uninstall-the-junk-email-reporting-add-in-in-silent-mode).
    
> [!NOTE]
> Você deve ter privilégios de administrador no computador em que você está desinstalando o suplemento. 
  
### <a name="uninstall-the-junk-email-reporting-add-in-from-control-panel"></a>Desinstalar o Suplemento Relatório de Lixo Eletrônico no Painel de Controle

1. Feche o Outlook no computador.
    
2. No menu Iniciar do computador, selecione **Painel de Controle**.
    
3. Selecione **Programas e Recursos**.
    
4. Selecione **Suplemento Relatório de Lixo Eletrônico para Microsoft Office Outlook**.
    
5. Selecione **Desinstalar**.
    
6. Inicie o Outlook novamente para confirmar se o suplemento não está mais sendo exibido na faixa de opções do Outlook.
    
### <a name="uninstall-the-junk-email-reporting-add-in-by-running-the-windows-installer-package"></a>Desinstalar o Suplemento Relatório de Lixo Eletrônico Executando o Pacote do Windows Installer

1. Feche o Outlook no computador.
    
    > [!NOTE]
    > Se o Outlook estiver em execução durante o processo de desinstalação, será necessário reiniciá-lo para que o suplemento seja completamente desinstalado. 
  
2. Execute novamente o arquivo .msi executado anteriormente para instalar o suplemento. 
    
    (Acesse a página do Centro de Downloads da Microsoft e localize o Suplemento Relatório de Lixo Eletrônico para Microsoft Outlook [https://go.microsoft.com/fwlink/?LinkId=147248](https://go.microsoft.com/fwlink/?LinkId=147248), baixe o arquivo .msi e, em seguida, clique duas vezes no arquivo .msi.) 
    
3. Siga os prompts para desinstalar o suplemento.
    
4. Inicie o Outlook novamente para confirmar se o suplemento não está mais sendo exibido na faixa de opções do Outlook.
    
### <a name="uninstall-the-junk-email-reporting-add-in-in-silent-mode"></a>Desinstalar o Suplemento Relatório de Lixo Eletrônico em Modo Silencioso

1. Feche o Outlook no computador.
    
    > [!NOTE]
    > Se o Outlook estiver em execução durante o processo de desinstalação, será necessário reiniciá-lo para que o suplemento seja completamente desinstalado. 
  
2. Abra um prompt de comando.
    
3. Especifique o seguinte parâmetro de linha de comando:
    
    Computadores que executam o Outlook x86:  `msiexec /x JunkReportingAdd-in.x86-en.msi /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"`
    
    Computadores que executam o Outlook x64:  `msiexec /x JunkReportingAdd-in.x64-en.msi /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"`
    
4. Inicie o Outlook novamente para confirmar se o suplemento não está mais sendo exibido na faixa de opções do Outlook.
    
## <a name="for-more-information"></a>Para saber mais

[Relatar mensagens de lixo eletrônico à Microsoft](report-junk-email-messages-to-microsoft.md)
  
[Solução de problemas e informações de suporte](troubleshooting-and-support-information.md)
  

