---
title: Configurar o IRM para usar um servidor RMS do AD local
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/13/2017
audience: End User
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 3ecde857-4b7c-451d-b4aa-9eeffc8a8c61
ms.collection:
- M365-security-compliance
description: Saiba como configurar o IRM (Gerenciamento de Direitos de Informação) Exchange Online usar um servidor do AD RMS (Serviço de Gerenciamento de Direitos do Active Directory).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5e430f9c6ad5d377b568d22e9de53ab79d19165a
ms.sourcegitcommit: 2655bb0ccd66279c35be2fadbd893c937d084109
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2021
ms.locfileid: "51876116"
---
# <a name="configure-irm-to-use-an-on-premises-ad-rms-server"></a>Configurar o IRM para usar um servidor RMS do AD local
  
Para uso com implantações locais, o IRM (Gerenciamento de Direitos de Informação) no Exchange Online usa Active Directory Rights Management Services (AD RMS), uma tecnologia de proteção de informações no Windows Server 2008 e posterior. A proteção do IRM é aplicada ao email por meio da aplicação de um modelo de política de direitos do AD RMS a uma mensagem de email. Os direitos são anexados à própria mensagem para que a proteção ocorra online e offline e dentro e fora do firewall da sua organização.
  
Este tópico mostra como configurar o IRM para usar um servidor AD RMS. Para obter informações sobre como usar os novos recursos para Criptografia de Mensagens do Office 365 com o Azure Active Directory e o Azure Rights Management, consulte Criptografia de Mensagens do Office 365 [perguntas frequentes.](./ome-faq.yml)
  
Para saber mais sobre IRM no Exchange Online, consulte [Gerenciamento de Direitos de Informação no Exchange Online](information-rights-management-in-exchange-online.md).
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Tempo estimado para a conclusão da tarefa: 30 minutos

- Para executar este procedimento ou estes procedimentos, você precisa receber permissões. Para ver de que permissões você precisa, consulte o Entrada "Gerenciamento de Direitos de Informação " no tópico [Messaging policy and compliance permissions](/Exchange/permissions/feature-permissions/policy-and-compliance-permissions). 

- O servidor AD RMS deve estar executando o Windows Server 2008 ou posterior. Para obter informações sobre como implantar o AD RMS, consulte [Instalando um cluster do AD RMS](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc726041(v=ws.11)).

- Para obter detalhes sobre como instalar e configurar o Windows PowerShell e se conectar ao serviço, consulte [Conectar-se ao Exchange Online usando o PowerShell Remoto](/powershell/exchange/connect-to-exchange-online-powershell).

- Para obter informações sobre atalhos de teclado que podem se aplicar aos procedimentos neste tópico, consulte [Atalhos](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)de teclado para o centro de administração Exchange no Exchange Online .

> [!TIP]
> Está enfrentando problemas? Peça ajuda nos fóruns do Exchange. Visite os fóruns em: [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612),[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542), ou [Proteção do Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=285351). 
  
## <a name="how-do-you-do-this"></a>Como fazer isso?
<a name="sectionSection1"> </a>

### <a name="step-1-use-the-ad-rms-console-to-export-a-trusted-publishing-domain-tpd-from-an-ad-rms-server"></a>Etapa 1: Use o console do AD RMS para exportar um domínio de publicação confiável (TPD) de um servidor AD RMS

A primeira etapa é exportar um TPD (domínio de publicação confiável) do servidor AD RMS local para um arquivo XML. O TPD contém as seguintes configurações necessárias para usar recursos do RMS:
  
- O certificado de licenciador de servidor (SLC) usado para assinatura e criptografia de certificados e licenças

- As URLs usadas para licenciamento e publicação

- Os modelos de política de direitos do AD RMS que foram criados com o SLC específico para esse TPD

Ao importar o TPD, ele é armazenado e protegido no Exchange Online.
  
1. Abra o console do Active Directory Rights Management Services e expanda o cluster do AD RMS.

2. Na árvore de console, expanda **Políticas de Confiança** e clique em **Domínios de Publicação Confiáveis**.

3. No painel de resultados, selecione o certificado para o domínio que você deseja exportar.

4. No painel **Ações**, clique em **Exportar Domínio de Publicação Confiável**.

5. Na caixa **Arquivo de domínio de publicação**, clique em **Salvar como** para salvar o arquivo em um local específico no computador local. Digite um nome de arquivo e certifique-se de especificar a extensão do nome de arquivo  `.xml` e clique em **Salvar**.

6. Nas caixas **Senha** e **Confirmar Senha**, digite uma senha segura que será usada para criptografar o arquivo de domínio de publicação confiável. Você terá de especificar essa senha quando importar o TPD para a sua organização de email baseada em nuvem. 

### <a name="step-2-use-the-exchange-management-shell-to-import-the-tpd-to-exchange-online"></a>Etapa 2: usar o Shell de Gerenciamento Exchange para importar o TPD para Exchange Online

Depois de exportar o TPD para um arquivo XML, você terá de importá-lo para o Exchange Online. Quando um TPD é importado, os modelos do AD RMS da sua organização também são importados. Quando o primeiro TPD é importado, ele se torna o TPD padrão para sua organização baseada em nuvem. Se você importar outro TPD, poderá usar o botão **Padrão** para torná-lo o TPD padrão que está disponível para os usuários. 
  
Para importar o TPD, execute o seguinte comando no Windows PowerShell:
  
```powershell
Import-RMSTrustedPublishingDomain -FileData $([byte[]](Get-Content -Encoding byte -Path <path to exported TPD file> -ReadCount 0)) -Name "<name of TPD>" -ExtranetLicensingUrl <URL> -IntranetLicensingUrl <URL>
```

Você pode obter os valores para os parâmetros  _ExtranetLicensingUrl_ e  _IntranetLicensingUrl_ no console do Active Directory Rights Management Services. Selecione o cluster do AD RMS na árvore do console. As URLs de licenciamento são exibidas no painel de resultados. Essas URLs são usadas por clientes de email quando o conteúdo deve ser descriptografado e quando o Exchange Online precisa determinar qual TPD usar.
  
Ao executar esse comando, será solicitado que você insira uma senha. Digite a senha especificada quando você exportou o TPD do seu servidor AD RMS.
  
Por exemplo, o comando a seguir importa o TPD, denominado TPD exportado, usando o arquivo XML exportado do seu servidor AD RMS e salvo na área de trabalho da conta Administrador. O parâmetro Name é usado para especificar um nome para o TPD.
  
```powershell
Import-RMSTrustedPublishingDomain -FileData $([byte[]](Get-Content -Encoding byte -Path C:\Users\Administrator\Desktop\ExportTPD.xml -ReadCount 0)) -Name "Exported TPD" -ExtranetLicensingUrl https://corp.contoso.com/_wmcs/licensing -IntranetLicensingUrl https://rmsserver/_wmcs/licensing
```

Para obter informações detalhadas de sintaxes e parâmetros, consulte [Import-RMSTrustedPublishingDomain](/powershell/module/exchange/import-rmstrustedpublishingdomain).
  
#### <a name="how-do-you-know-this-step-worked"></a>Como saber se esta etapa funcionou?

Para verificar se você importou com êxito o TPD, execute o cmdlet **Get-RMSTrustedPublishingDomain** para recuperar TPDs em sua organização do Exchange Online. Para obter detalhes, consulte os exemplos no [Get-RMSTrustedPublishingDomain](/powershell/module/exchange/get-rmstrustedpublishingdomain).
  
### <a name="step-3-use-the-exchange-management-shell-to-distribute-an-ad-rms-rights-policy-template"></a>Etapa 3: usar o Shell de Gerenciamento Exchange para distribuir um modelo de política de direitos do AD RMS

Depois de importar o TPD, você deverá garantir que um modelo de política de direitos do AD RMS seja distribuído. Um modelo distribuído fica visível para Outlook usuários na Web (anteriormente conhecidos como Outlook Web App), que podem aplicar os modelos a uma mensagem de email.
  
Para retornar uma lista de todos os modelos contidos no TPD padrão, execute este comando:
  
```powershell
Get-RMSTemplate -Type All | fl
```

Se o valor do parâmetro  _Type_ for  `Archived`, o modelo não ficará visível para os usuários. Somente modelos distribuídos no TPD padrão estão disponíveis Outlook na Web.
  
Para distribuir um modelo, execute este comando:
  
```powershell
Set-RMSTemplate -Identity "<name of the template>" -Type Distributed
```

Por exemplo, o comando a seguir importa o modelo Confidencial da Empresa.
  
```powershell
Set-RMSTemplate -Identity "Company Confidential" -Type Distributed
```

Para obter informações detalhadas sobre sintaxe e parâmetros, consulte [Get-RMSTemplate](/powershell/module/exchange/get-rmstemplate) e [Set-RMSTemplate](/powershell/module/exchange/set-rmstemplate).
  
**O modelo Não Encaminhar**
  
Ao importar o TPD padrão da sua organização local para o Exchange Online, um modelo de política de direitos do AD RMS chamado **Não Encaminhar** será importado. Por padrão, esse modelo é distribuído quando você importa o TPD padrão. Não é possível usar o cmdlet **Set-RMSTemplate** para modificar o modelo **Não Encaminhar**. 
  
Quando o modelo **Não Encaminhar** é aplicado a uma mensagem, somente os destinatários da mensagem podem ler a mensagem. Além disso, os destinatários não podem o seguinte:
  
- Encaminhar a mensagem para outra pessoa.

- Copiar o conteúdo da mensagem.

- Imprimir a mensagem.

> [!IMPORTANT]
> O modelo **Não Encaminhar** não pode evitar que as informações de uma mensagem sejam copiadas com produtos de captura de tela de terceiros, câmeras ou transcrição manual por usuários. 
  
Você pode criar mais modelos de política de direitos do AD RMS no servidor AD RMS, na sua organização local, para atender aos requisitos de proteção de IRM. Se você criar modelos de política de direitos do AD RMS adicionais, terá de exportar o TPD do servidor AD RMS local novamente e atualizar o TPD na organização de email baseada em nuvem.
  
#### <a name="how-do-you-know-this-step-worked"></a>Como saber se esta etapa funcionou?

Para verificar se você distribuiu com êxito um modelo de política de direitos do AD RMS, execute o cmdlet **Get-RMSTemplate** para verificar as propriedades do modelo. Para obter detalhes, consulte os exemplos no [Get-RMSTemplate](/powershell/module/exchange/get-rmstemplate).
  
### <a name="step-4-use-the-exchange-management-shell-to-enable-irm"></a>Etapa 4: usar o Shell de Gerenciamento Exchange para habilitar o IRM

Depois de importar o TPD e distribuir um modelo de política de direitos do AD RMS, execute o comando a seguir para habilitar o IRM para sua organização de email baseada em nuvem.
  
```powershell
Set-IRMConfiguration -InternalLicensingEnabled $true
```

Para obter informações detalhadas de sintaxes e parâmetros, consulte [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration).
  
#### <a name="how-do-you-know-this-step-worked"></a>Como saber se esta etapa funcionou?

Para verificar se você habilitou com êxito o IRM, execute o cmdlet [Get-IRMConfiguration](/powershell/module/exchange/get-irmconfiguration) para verificar a configuração do IRM na organização do Exchange Online.
  
## <a name="how-do-you-know-this-task-worked"></a>Como saber se essa tarefa funcionou?
<a name="sectionSection2"> </a>

Para verificar se você importou com êxito o TPD e se habilitou o IRM, faça o seguinte:
  
- Use o cmdlet do **Test-IRMConfiguration** para testar a funcionalidade do IRM. Para obter detalhes, confira "Exemplo 1" em [Test-IRMConfiguration](/powershell/module/exchange/test-irmconfiguration).

- Componha uma nova mensagem Outlook na Web e proteja-a por IRM selecionando **Definir** permissões no menu estendido ( Ícone ![ de Mais Opções ](../media/ITPro-EAC-MoreOptionsIcon.gif) ).